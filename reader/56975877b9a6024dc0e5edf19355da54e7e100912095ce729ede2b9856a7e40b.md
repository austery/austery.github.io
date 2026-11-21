---
author: AI Engineer
date: '2026-11-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZZ19zhYnDKY
speaker: AI Engineer
tags:
  - ai-engineering
  - coding-agents
  - vibe-coding
  - conference
title: AI Engineer Code Summit 2026 开幕致辞与闭幕总结
summary: 文章记录了 2026 年 AI 工程师代码峰会的开幕与闭幕环节。主持人 Corey Quinn 介绍了 AIE 团队扩张及 2027 年规划，演讲者探讨了 AI 代理的恢复机制（Evo undo）、Vibe coding 在 3D 游戏开发中的突破，以及软件工程师在 AI 时代面临的挑战与预测复盘。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Corey Quinn
  - Leah
companies_orgs:
  - DuckBill Group
  - AIE
  - Swix
  - Major League Hacking
  - Neo4j
  - Google
products_models:
  - Claude
  - Opus 5.5
  - Gemini 4 carbon
  - Evo undo
media_books: []
status: evergreen
---
<!-- chunk 1/50 -->

### 开幕致辞与活动介绍

早上好，欢迎来到 2026 年 AI 工程师代码峰会（AI Engineer Code Summit 2026）。

<details><summary>Original English</summary>
Good morning and welcome to AI Engineer Code Summit 2026.
</details>

我们非常激动能将 AI 工程领域最聪明的头脑汇聚一堂，度过充满新想法、新视角以及塑造我们未来软件构建方式的交流对话的一天。为了正式揭开今天的序幕并带领我们进入今日的主题演讲，请大家用热烈的掌声欢迎我们的主持人——DuckBill Group 的首席云经济学家 Corey Quinn。

<details><summary>Original English</summary>
We're excited to bring together some of the brightest minds in AI engineering for a day of fresh ideas, new perspectives, and conversations shaping the future of how we build software. To officially kick things off and lead us through today's keynotes, please put your hands together for our MC, Corey Quinn, chief cloud economist at the Duck Bill Group.
</details>

感谢各位的到来。这是今年 AI 工程领域的最后一场旗舰活动。额，大家目前感觉如何？

<details><summary>Original English</summary>
Thank you all for coming. This is the last flagship event of the year for AI engineering. Uh how are folks feeling so far?
</details>

>> 耶。太令人振奋了。我们学到了什么？有什么好东西吗？有什么令人兴奋的事吗？有什么糟糕的事吗？

<details><summary>Original English</summary>
>> Yay. That's exciting. What have we learned? Anything good? Anything exciting? anything terrible.
</details>

>> 本体论（Ontology）。

<details><summary>Original English</summary>
>> Ontology.
</details>

>> 来咯。没错。本体论。这是什么意思？我们先把它搁置一下。我们稍后会回过头来聊它。我是 Corey Quinn。如果你从未听说过我，第一，你就是我们通常认为的那种过得挺幸福的人；第二，额，如果你好奇的话，你可以在我的网站 shitposting 查看我做的各种事情。

<details><summary>Original English</summary>
>> There we go. That's right. Ontology. What does it mean? We're going to put a pin in that. We're going to come back to it. I am Corey Quinn. If you've never heard of me, you're a what we tend to think of as being happy and b uh if you are curious, you can look at all the various things I do at my site shitposting.
</details>

这本身就说明了你需要了解的关于我所做的一切。那么今天，我们要开启序幕，并与那些有有趣、有价值的话要说的人进行一些愉快的对话，而不是看我在这里空费唇舌。额，我们首先要请出我们来自 Swix 的朋友们。Swix，你现在有空了吗？还是你还躲在后面？太棒了。请出来吧。还有 Leah 也一起来。

<details><summary>Original English</summary>
Which in itself tells you everything you need to know about what I do. So today we are going to be kicking things off and having some fun talks with people who have interesting, useful things to say rather than me flopping my gums up here. Uh we're going to start by bringing up our friends from Swix. Swix, are you available yet or are you still hiding back there? Terrific. Come on out, please. And Leah as well.
</details>

>> 我抢先了吗？

<details><summary>Original English</summary>
>> Did I jump the gun?
</details>

>> 没有，请。请自便。Swix，谢谢你。

<details><summary>Original English</summary>
>> No, please. By all means. Swix, thank you.
</details>

>> 抱歉。

<details><summary>Original English</summary>
>> Sorry.
</details>

>> 谢谢你。

<details><summary>Original English</summary>
>> Thank you.
</details>

>> 我很久没有……而且，额，能让他来担任主持真是太好了，同时热烈欢迎 AIE 总经理 Leah。

<details><summary>Original English</summary>
>> I didn't a long time and uh it's so nice to have him MC as well and give a warm welcome to Leah, general manager of AIE.
</details>

>> 嗨，早上好。

<details><summary>Original English</summary>
>> Hi, morning.
</details>

>> 嗯，额，是的，大家知道，我们非常高兴能为大家揭开本次大会的序幕。嗯，向所有在网上观看的人打个招呼。AIE Code 算是我们的垂直领域、非常聚焦的较小形式，额，额，大家知道，关于编码 Agent 的形式。而且我认为今年在编码 Agent 领域是非常重大的一年。

<details><summary>Original English</summary>
>> Um uh yeah, you know, we we're so happy to to open the show for you. Um and hi to everyone watching along online. AIE code is uh kind of our vertical very focused smaller format uh uh you know format on on um coding agents and I think it's been such a huge year in coding agents.
</details>

嗯，在我们如何思考编码的使命究竟是什么方面，也发生了额许多不同的演变。额，我们以前有，额，大家知道，在具体的主题分会场标题中，像编码 Agent、软件工厂以及所有这些内容，但现在我谈论的是像系统一思维（System 1 thinking）以及，额，以及提高你的抱负，还有所有这些非常高端、更高层级的工作抽象。所以我很兴奋能看到，额，让你们看到，并且我个人也很期待参加额接下来要举行的所有这些演讲。

<details><summary>Original English</summary>
Um there's also been uh a lot of different evolutions in terms of like how we think about what the the mission of coding is. uh we used to have uh you know and in specific track titles like coding agents and software factories and all these things but now I'm talking about like system one thinking and and uh and raising your ambition and all these like very fancy higher level extractions of of work. So I'm excited to see uh for you to see and excited to me personally to attend uh all these talks that are coming along.
</details>

>> 嗯，我打算简单谈一下 2026 年，嗯，关于 AIE 的情况。我们今年度过了非常充实的一年。我们在伦敦举办了首场活动。额，我们还将世博会（world's fair）升级到了 Moscone。嗯，我们还举办了一系列……噢，来啦。我不知道它之前是不是在我们身后。嗯，我们，额，我们举办了，嗯，多场合作伙伴活动，如果你们中有人去过的话，额，我们很希望能收到相关的反馈，因为这是我们正在运作的一个非常棒的计划。嗯，我们团队也有了大幅的，嗯，增长。我想之前某处是有一张幻灯片的。

<details><summary>Original English</summary>
>> Um and I'm just going to talk a little bit 2026 um with AIE. So we've had a really big year this year. We had our first event in London. Uh we also graduated up into Moscone for our world's fair. Um we also had a bunch Oh, here we go. I don't know if it was behind us. Um we uh we had um multiple partner events which if any of you went to uh we'd love to hear feedback there because it's a great program that we're running. Um we've also grown our team um substantially. So I think there was a slide somewhere.
</details>

噢，我不知道。我觉得他们已经……

<details><summary>Original English</summary>
Oh, I don't know. I think they've
</details>

>> 美丽的人们。有人对点击翻过所有内容感到非常兴奋。

<details><summary>Original English</summary>
>> beautiful people. Someone's very excited about clicking through everything.
</details>

>> 嗯，是的。我们，额，我们在这一页。所以，额，就是这样。是的，我们的团队壮大了。我们今年团队从，嗯，4 个人增加到了 20 个人，额，这非常令人激动。所以，这是所有人。向团队致以巨大的感谢。嗯，正如你们所见，项目正在扩大，而且，嗯，这里的每个人都功不可没。

<details><summary>Original English</summary>
>> Um, yep. We, uh, here we are. So, uh, there we go. So, yeah, we've grown our team. We went from, um, four in the team to 20 this year, uh, which was very exciting. So, this is everyone. A big shout out to the team. Um, as you can see, the program is growing and, um, everyone here is responsible for that.
</details>

>> 嗯，

<details><summary>Original English</summary>
>> Um,
</details>

>> 我慢慢插一句，比如我们为什么要扩张？是因为我们想为各位提供一个始终如一的产品。额，这样无论在你们工作的各大城市中，额，你们都有一个 AIE 可以去参加。嗯，并且我们尽量铺开，大家知道，我们每年大约举办四场旗舰大会，以及在全球各地举办大量的合作伙伴大会。

<details><summary>Original English</summary>
>> and I'll slowly interject like why are we growing? It's because we want to provide a consistent product for the rest of you. uh that like wherever in instead of the major cities that you're working in uh you have an AIE to go to. Um and we try to spread out you know we're doing something like four flagship conferences a year and a lot of partner conference around the world.
</details>

>> 是的。嗯，我们还有，我想我刚才看到，嗯，我们最受欢迎的演讲（刚才正好显示在那里），额，在 YouTube 上有将近两百万次观看，但要点没显示出来。然后我们也即将宣布 2027 年，嗯，带有更广泛的项目规划。我们有望在大概 3 周后公布。嗯，我们正在做更多的合作伙伴活动。我们正在进入一些不同的地区。对于 2027 年来说非常令人振奋。嗯，我们今年还做了其他几件事，包括我们与 Major League Hacking 建立了合作。嗯，他们明年将在我们的每场活动中与我们一起举办黑客松。嗯，我们本周五实际上就有一场。所以如果大家还没报名并且想来的话，额，请查看网站。额，我们还与 Neo4j 合作开展了一个儿童活动系列。嗯，那场活动就在本周六举行。所以如果你有大概 6 到 14 岁之间的孩子，额，欢迎过来。同样，你可以在网站上找到这些信息，

<details><summary>Original English</summary>
>> Yep. Um we also I think I just saw that um our most popular talk which just came up there uh has almost two million views on YouTube but points not coming up. And then we are also just about to announce 2027 um with a wider program. We're going to hopefully announce that in about 3 weeks time. Um we are doing more partner events. We're entering into some different regions. It's very exciting for 2027. Um a couple other things we've done this year is we've partnered with Major League Hacking. Um and they are going to be running a hackathon with us at every event next year. Um we actually have one this Friday. So if you guys haven't signed up and you want to come u please look on the website. Uh we are also working with Neo4j on a kids event series also. Um and that is happening this Saturday. So if you have got any kids between the age of kind of six to 14 uh feel free to come down. Again you can find that on the website
</details>

>> 或者访问 aie.kids。额，我正处于我的域名抢购时代。所以我们搞到了一个 kids 域名给儿童项目，还有一个 asec 域名放日程表。

<details><summary>Original English</summary>
>> or aie.kids. Uh I'm in my domain buying era. So we got a kids for kids and asec for the schedule.
</details>

>> 是的。嗯，是的。那么，接下来我们今年还有最后一场活动，那就是悉尼的活动。Swix 会去那里。我不会去。嗯，那就结束了 2026 年。所以，是的，非常感谢大家的到来，我们希望你们享受接下来的这几天。

<details><summary>Original English</summary>
>> Yeah. Um yes. So and then we have one final event for the year which is a Sydney event. Swix will be there. I will not. Um, and that closes out 2026. So, yeah, thank you so much for coming everyone and we hope you enjoy the the next couple of days.
</details>

>> 好的，

<details><summary>Original English</summary>
>> All right,
</details>

>> 祝大家观展愉快。

<details><summary>Original English</summary>
>> enjoy our show.
</details>

### 赞助商鸣谢与首场演讲介绍

多棒的开场方式啊。额，我们在这里发现的是，没有来自我们众多合作伙伴的帮助，这类活动是办不起来的。他们能来到这里支持我们是极其重要的。我们想为此向他们致谢。首先从我们的主赞助商，额，Google DeepMind 开始。能不能为他们送上一阵热烈的掌声？

<details><summary>Original English</summary>
What a great way to get us started. Uh what we have found here is that events like this don't happen without help from a lot of our partners. It is incredibly important that they are there and support us. We want to thank them for it. Beginning with our presenting sponsor, uh Google DeepMind. Could we get a round of applause for them please?
</details>

搞定啦。

<details><summary>Original English</summary>
There we are.
</details>

视听设备方面的问题，在这点上总是充满乐趣和刺激。

<details><summary>Original English</summary>
AV challenges always fun and exciting on that one.
</details>

拖延时间。挺好的。额，我也想感谢我们的支持合作伙伴，没有他们，我们同样无法来到这里。

<details><summary>Original English</summary>
Stall. It's great. Uh I also want to thank our supporting partners as well about whom we would again not be able to be here.
</details>

通常它会显示在那边。噢，那里，抱歉，看错边了。我往左看，应该是往右转。如果我们能同样为他们送上一阵掌声。感谢各位的支持。非常感激。

<details><summary>Original English</summary>
Normally it shows up there. Oh there sorry wrong side. I look left. It's right turn. If we get a round of applause for them as well. Thank you all for your support. It's appreciated.
</details>

是的。当然还有金牌赞助商，再次强调，没有他们我们同样无法来到这里，至少无法来到这个场馆。我们基本上就得在街角对着人们大喊大叫了，虽然这并非闻所未闻，但通常不是你希望为这种活动打造的高级体验。我们的银牌赞助商，同样也要感谢他们。请再为他们送上一轮掌声。

<details><summary>Original English</summary>
Yes. And of course the gold sponsors as well, which without whom again we would not be able to be here, at least not in this venue. We'd basically be yelling out on a street corner at people, which while not unheard of, is generally not the premier experience you try to have for something like this. Our silver sponsors also, thank you for them as well. One more round of applause for them, please.
</details>

应对现代 AI 时代的一大难处在于，感觉今年在技术上就像过了大约 10 年。我们回看一月份我们在做的事情，感觉几乎像是中世纪一样。当时作为最佳实践并且合情合理的事情，现在看来完全不可思议。事情发展得太快了，以至于你基本上打个盹，醒来就会觉得被你睡觉时发生的事情吓了一跳。一切都在变得更快，而这正是我们第一场演讲的主题，因为大家不是来听我漫谈胡扯的。嗯，Natalie Serero 是 Gimlet Labs 的联合创始人，现在将为我们讲述当 AI 提速 10 倍时会发生什么。Natalie，非常感谢你。请上台来。

<details><summary>Original English</summary>
One of the hard things about dealing with the modern era in AI is it feels like this year has been about 10 years in technology. We look back at what we were doing in January and it feels like it was almost medieval times. It the things that were best practices and made sense then now just seem absolutely bizarre. It's things get moving so quickly and it's easy to basically take a nap and feel like you've woken up and gotten like surprised by what happened while you were sleeping. Everything's moving faster and that is the theme of our first talk that we're going to have because you're not here to listen to me ramble. Um, Natalie Serero is the co-founder of Gimlet Labs and is going to talk to us now about what happens when AI becomes 10 times faster. Natalie, thank you very much. Please come on out here.
</details>

大家好。

<details><summary>Original English</summary>
Hello everyone.
</details>

能来到这里真是太棒了。感谢大家今天早上与我聚在这里。今天的第一场分会。我看这里的各位都是习惯早起的人。那么我来到这里是要和大家探讨：当 AI 提速 10 倍时，你们会构建什么？我们这里全都是构建者。所以我们都在思考下一步是什么。

<details><summary>Original English</summary>
It's so good to be here. Thank you for being with me this morning. First session of the day. I see everyone here is a morning person. So I'm here to talk to you about what will you build when AI is 10 times faster. We're all builders here. So we're all thinking about what's next.
</details>

简单介绍一下我自己。嗯，我的名字是 Natalie。我是 Gimlet Labs 的联合创始人。在 Gimlet，我们正在构建一个推理云，旨在利用不同门类和类型的芯片，以高效率产生快得多的 Token。在 Gimlet，我负责跨不同硬件类型的内核生成端的工作。嗯，关于我的另一件事是，我热爱 Agent。我所有的工作都使用我的编码 Agent，但我真的、真的非常讨厌等待。

<details><summary>Original English</summary>
Just a bit about me. Um my name is Natalie. I'm a co-founder of Gimlet Labs. At Gimlet, we're building an inference cloud that's designed to produce much, much faster tokens at high efficiency, leveraging different categories and types of chips. At Gimlet, I work on our kernel generation side of things across different hardware types. Um, another thing about me is I love agents. I use my coding agents for everything, but I really, really hate waiting.
</details>

鉴于这一点，让我有点惊讶的一件事是，当你在构建一个超快推理云时，人们其实经常问我这个问题。他们会说，推理难道不是已经够快了吗？

<details><summary>Original English</summary>
And one thing that given that kind of surprises me is when you're building an ultra fast inference cloud, people ask me this all the time actually. They're like, isn't inference already fast enough?
</details>

然后我就心想，什么？

<details><summary>Original English</summary>
And I'm like, what?
</details>

但他们说得有道理，对吧？因为我能做的事情，以及我们所有人使用我们的 Agent 能做的事情，比我们以前能做的要快得多。例如，额，这里这张幻灯片，我其实用我的 Agent 把它做得挺漂亮的

<details><summary>Original English</summary>
But they have a point, right? Because I can do things and we can all do things with our agents so much faster than we could have done before. For example, uh this slide here, I actually made pretty using my agent
</details>

<!-- chunk 2/50 -->

而且我和我的 Agent 一起完成这件事，花的时间比我自己去做要少得多。我不太擅长设计。所以我觉得从端到端的角度来看，我们显然完成了更多事情，但就速度是否足够快而言，这仍然是一个问号。我们来看一下当我用 Agent 把那张幻灯片变美观时发生了什么。你可以在右侧看到之前那张难看的幻灯片。

<details><summary>Original English</summary>
and it took me with my agent much less time than it would take me to do that by myself. I'm not very good at design. And so I think that from an endto-end perspective, obviously we're getting more done, but in terms of is it fast enough, like that's still a question. So let's take a look at what happened when I used my agent to make that slide look pretty. You can see the ugly before slide on the right.
</details>

我们要在这里点击播放。我对我的 Agent 说：“你能改善这张幻灯片的视觉效果吗？”我非常喜欢 Figma，什么都用 Figma。所以，我自然也会在 Agent 身上使用它。我们在底部这里能看到的是发生过程的时间线。上面的文字有点小，看不太清，但红色代表推理，红色是模型处于推理中所花费的时间。绿色是它进行工具调用所花费的时间，而蓝色是它接收我的输入所花费的时间。我们可以看到，这个 Agent 确实做得不错，做了很多思考，但我在这里一直在等待。

<details><summary>Original English</summary>
So, we're going to press play here. And I said to my agent, can you improve the visual look of this slide? I love Figma. I use Figma for everything. So, of course, I'm going to use it with my agents. So, what we can see on the bottom here is the timeline of what happened. And it the text is a little small to see, but red is inference. Red is the time spent that the model is in inference. Green is the time it's spent making tool calls. and blue is the time that it's spent taking my input. And we can see that, you know, this this agent's doing good work. It's doing a lot of thinking, but I'm waiting here.
</details>

实际上我等了太久，以至于我把这段视频加速了 9 倍，因为我不想让你们大家非得等完整的一轮交互结束。那一轮最终大概持续了 2 分钟。但我们可以在最后看到，在我给了一次输入之后，最后得到了这张漂亮精美的幻灯片。所以，一方面，这其实比人类去做的速度快得多；但另一方面，在那大概两分钟的时间里，我可能已经转去处理另一项任务了。我不再真正专注于这件事，我已经进行了上下文切换。

<details><summary>Original English</summary>
I'm actually waiting so long I sped up this video 9x because I didn't want all of you to have to wait for the full turn to end. It ended up being about 2 minutes long. But we can see at the end of this after my one input, we have this nice pretty slide at the end. So, you know, on one hand, this is actually much faster than a human can do. But on the other hand, in those about two minutes, I have probably moved on to another task. I'm not really focused on this anymore. I've context switched.
</details>

### 从 Web 时代看速度的价值

当我们着眼于推理变得越来越快这一必然发展趋势时，我认为回顾历史、回顾互联网时代是很有帮助的。嗯，我的意思是，我们现在仍然处于互联网中，但就像大家通常所称的 Web 时代那样。在每一次新的转变中我们总能看到，伴随着每一次新的重大浪潮，新的能力被解锁。于是我们做出了在那项技术出现之前无法做到的事情，比如使用 Agent 来修改我的幻灯片。所以我觉得我们应该退回一步，回到 2000 年互联网的早期。我想这里的许多人当时甚至都还没出生，所以这对你们来说会是一堂历史课。我们要来看一个叫做 Squirrel Mail 的小应用程序。Squirrel Mail 实际上是开源的，所以你今天也能运行它。它是当年用来处理电子邮件的一个 Web 应用程序。

<details><summary>Original English</summary>
And when we look to, you know, the inevitable progression of inference getting faster and faster, I think it helps to look back in time and look back to the internet era. Um, I mean, we're still in the internet, but like you know what people canonically call the web era. And what we always see with a new shift is that with each new major wave, new capabilities are unlocked. And so we do things that weren't possible before that technology, like using an agent to edit my slide. So I think we should take a step back to 2000 in the early days of the internet. I think many people here weren't even alive, so it'll be a history lesson for you. And we're going to look at a little application called Squirrel Mail. Squirrel Mail is actually open source, so you can run it today. It was a web application for uh you know doing your email back then.
</details>

在左边我们展示的是我运行 Squirrel Mail，并且是用模拟的 2000 年拨号上网速度运行；然后在右边，它将以 2026 年的速度运行，也就是我们如今习惯的速度。两侧执行的操作是相同的，但在左侧，我使用的是模拟的较慢网络速度。

<details><summary>Original English</summary>
So on the left what we have here is I'm running squirrel mail and I'm running it with simulated 2000 dialup speed and then on the right it'll run with 2026 speed. So the speed that we're used to today. So the both sides are going to take the same actions but um the left side I'm using it with that simulated lower uh speed internet
</details>

我们可以看到，它正在完成自己的任务。在 2000 年，像这样加载一张图片会让人们感到震撼，但以我们现代人的眼光来看，会觉得“哇，这也太久才显示出来了”。我们可以看到这些延迟，能看到很明显的现象；但在当时，2000 年的某些人可能会看着这个说：“这已经够快了，我其实不需要它更快。”

<details><summary>Original English</summary>
and we can see that you know it's doing its job. Back in 2000 loading an image like this would have blown people's minds but our modern eyes are like wow that took forever to show up. And so we can see these lags. we can see a noticeable thing, but on the same time, someone might have looked at this back in 2000 and said, "This is fast enough. I don't actually need this to be faster."
</details>

然而事实是，那个时代所有的巨头都发现速度至关重要。几乎每一家大公司，从 Amazon 到 Yahoo，到 Google，再到 Bing——或者说作为微软一部分的 Bing——所有这些公司都发现，即使是非常微小的延迟，也会让他们损失用户，损失回头客，损失用户的点击量，带来真金白银的损失。在常规体验中即使只增加 100 毫秒的延迟，也会对最终净利润产生明显的影响。而且即使消除了这种延迟，那些用户回到平台的频率也比不上从未遭遇过延迟时的频率。

<details><summary>Original English</summary>
The thing is though, all of the major giants back in that era did find out it mattered. Pretty much every major company from Amazon to Yahoo to Google to Bing, all of or being at part of Microsoft like all of them found that even very small delays cost them users. It cost them people coming back. It cost them people doing as many clicks. It cost them literal money. Even a hundred milliseconds of delay added on to the typical experience had a demonstrable impact on the bottom line. And even when you got rid of that delay, those same users didn't come back to the platform as often as they did without that delay.
</details>

这是合乎逻辑的，因为快速的产品能让我们保持心流状态，能提供粘性更高的用户体验。大约 100 毫秒在我们感觉中是即时的。1 秒的等待，我仍然能保持思路，这不是什么大问题，我并不会真正注意到。到了 10 秒，从心理学角度来看，我们就会开始转向其他事情，也许会拿出手机，也许会切换到另一个 Agent。然而在今天，根据 6 月份的数据，编程 Agent 的单轮交互时间中位数是 63 秒。

<details><summary>Original English</summary>
And this makes sense because fast products keep us in flow state. They provide a stickier UX. About 100 milliseconds feels instant to us. One seconds, one second of weight, I still keep my train of thought. It's not a big deal. I don't really notice it. 10 seconds, we're going to start turning to something else from a psychology perspective. Maybe we pull out our phone, maybe switch to another agent. But today, from data from June, the median coding agent turn is 63 seconds.
</details>

不同的工作负载有不同的速度需求。我们并非对所有事情都需要相同的速度。但随着时间的推移，我们的期望确实在提高。在 Squirrel Mail 时代的极速网络，如今在我们看来会慢得难以置信，我们完全可以预料到，推理速度也会延续这一趋势。

<details><summary>Original English</summary>
Each workload has different speed requirements. We don't need the same speed for everything. But over time, our expectations do rise in the fastest days of fastest internet in the squirrel mail days would feel incredibly slow to us and we can keep we can expect that trend to continue for inference speed as well.
</details>

### 算力短缺下的权衡与突破

然而存在一个问题，这个问题就是众所周知的大规模算力短缺。今天的基础设施承受着难以置信的压力，需要同时交付两样东西：更多的 token 和更快的 token。不幸的是，这两个目标在根本上是相互冲突的，因为生成更快的 token 比生成较慢的 token 需要消耗更多能量。因此在相同的能耗限制下，你无法生成那么多数量的 token。

<details><summary>Original English</summary>
There's a problem though and the problem is everyone knows that we have massive compute scarcity. Today's infrastructure is under incredible pressure to deliver two things at the same time. More tokens and faster tokens. Unfortunately, these goals are fundamentally at odds because faster tokens require more energy to produce than slower tokens. So, with the same energy footprint, you can't make as many of them.
</details>

在这次分享之前它还只是个普通分会场演讲而不是主题演讲，感谢大家把它升级为了主题演讲。嗯，我们本来打算玩一个我做的小游戏，叫做“Token 铸造工厂”（Token Mint Factory）。大家其实现在就可以玩。哪怕你现在就在玩，我也不会介意，但顺便提醒一下，它无法在手机上运行，只能在你的笔记本电脑上运行。基本上在这个游戏里，你经营着一家 token 铸造工厂，你是在实实在在地印制 token。游戏有不同的模式：你可以选择以最大化单枚 token 的产出速度为目标来进行游戏；或者你可以最大化 60 秒内产出的 token 数量；或者你可以玩 SLA 模式，在该模式下你必须让每枚 token 保持 20 秒的 SLA 才算有效，但你依然要在达标的前提下尽可能多地生产。

<details><summary>Original English</summary>
Back before this was a session and not a keynote, thanks to upgrading this to a keynote everyone. Um, we uh we're going to play a game that I made uh called Token Mint Factory. And you can actually play this. I will not be offended if you play it right now even, but just so you know, it does not work on phones. It only works on your laptop. And basically in this game, you're running a token mint factory. You're printing literal tokens. And there's different modes. The modes are you can play to maximize how quickly you can put out one single token. Or you can maximize how many tokens you can put out in 60 seconds. Or you can play the SLA mode where you have to maintain a 20 second SLA on each token for it to count, but you're still trying to put out as many as you can.
</details>

在你玩的过程中，你会很快发现，产出更快的 token 和产出较慢的 token，策略是极其不同的。从决策的角度来看，两者其实并没有好坏之分，这完全取决于应用的需求以及你的工厂适合采取什么方案。

<details><summary>Original English</summary>
And as you play, you'll quickly see that the strategy is extremely different for doing fast tokens versus doing slow tokens. And neither one is actually better or worse from a decision perspective. It's just a matter of what the application needs and what makes sense for your factory.
</details>

于是我从我公司玩过这个游戏的人那里采集了实际运行数据，并基于游戏中的这些 token 绘制了一条帕累托前沿。我们可以看到，现实生活中这个游戏同样存在一条帕累托前沿。如果我们追求更快的 token，数量就没有那么多；而如果我们要更多的 token，它们的速度就没有那么快。但是有一种方法可以向右上角移动，而右上角正是我们想要达到的方向。我们想要更多且更快的 token。我不想妥协，我两样都要。所以这个游戏中有一个为设备添加升级的概念。我们所能看到的是，与没有升级的基线相比，这些技术创新有助于推动我们向右上角移动，获得更多、同时也更快的 token。

<details><summary>Original English</summary>
So I took real runs from people at my company that played this game and I made a paro frontier of these tokens in the game. And we can see there's a real life paro frontier of this game as well. If we have faster tokens, we don't have as many. And if we have more tokens, they're not as fast. But there is a way to get more up and to the right. And up and to the right is where we want to go. We want more faster tokens. I don't want to compromise. I want both. So the game has a concept of adding upgrades to your equipment. And what we can see is that compared to the no upgrade baseline, these technological innovations help drive us up into the right and get more tokens and faster tokens.
</details>

那么我们如何升级现实生活中的“流水线”，让实际生产 token 的速度更快呢？在 Gimlet 我们为此采取的一个做法是：我们坚信必须针对合适的任务使用合适的加速器。因此我们实际上会将模型拆分成不同的部分，并把每个部分运行在不同类别的加速器上。比如，我们可能会将一部分工作负载运行在 GPU 上，而将另一部分工作负载运行在类似 SRAM 为中心的加速器上。我们发现，即使存在网络开销，这也能带来显著更快的 token。当你让加速器与任务更好地匹配时，这在本质上就等同于 token 工厂中的设备升级。不幸的是，晶体管规模扩展带来免费午餐的时代已经终结了，对吧？所以现在我们必须寻求其他方法来让事情变快。

<details><summary>Original English</summary>
So how do we upgrade our real life assembly lines so to speak to make making our actual tokens faster? Uh one thing that we do at Gimlet for this is we really believe that you have to use the right accelerator for the right job. And so we actually take models and we split them up into different pieces and we run each piece on a different category of accelerator. So we might run one piece of the workload on a GPU and another piece of the workload on something like an SRM ccentric accelerator. And we find that even with the network overhead, this delivers dramatically faster tokens. It's essentially like the same thing as the upgrade to the equipment in the token factory when you better match the accelerator to the job. Unfortunately, we have ended the time of free lunch transistor scaling, right? So now we have to look to other approaches to make things faster.
</details>

通过这张图——虽然有点难辨认，但我们能看到前沿模型在现实中有着同样的帕累托前沿。如果看纯粹的同构 GPU 推理，它的吞吐量非常高。然后延迟会有所下降，你无法让它那么快，因为纵轴代表我能产出多少 token，横轴代表对每个用户而言这些 token 的生成速度有多快。我们可以看到，取决于你如何拆分模型（因为有不同的拆分方式），在相同的功耗下你可以获得明显更快的 token。

<details><summary>Original English</summary>
And so with this, it's a little hard to read, but we can see the same real life paro frontier for a frontier model. If you look at, you know, simple homogeneous GPU inference, it's very high throughput. And then the latency drops off a little bit. You don't you can't get it as fast because the y-axis is how many tokens that I can make and the x-axis how fast these tokens are for each user. And we can see that depending on how you split the model up because there's different ways of doing it. You can get much faster tokens for the same power footprint.
</details>

你可以在保持相同速度的情况下获得多得多的 token，或者你可以同时获得更多、更快的 token。所以作为

<details><summary>Original English</summary>
You can get many more tokens for the same speed or you can get more and faster tokens. So as an
</details>

<!-- chunk 3/50 -->

行业，我们需要在这个方向上继续推进、推进、推进，因为否则的话，我们可怜的数据中心就直接吃不消趴下了。

<details><summary>Original English</summary>
industry
we
need

to
continue
pushing
pushing
pushing
on

this
because
otherwise
our
poor
data

centers
are
just
going
to
keel
over.
</details>

所以我只想对此做个快速的演示。嗯，使用编程智能体构建同一个应用，采用利用不同芯片类型的异构推理，来对比传统的推理方式。

<details><summary>Original English</summary>
So
I
just
wanted
to
show
a
quick
demo
of

this.
So
um
using
a
coding
agent
build

the
same
app
using
heterogeneous

inference
that
leverages
different
chip

types
versus
the
traditional
one.
</details>

这要做的是贪吃蛇游戏。我们可以看到左边这个采用异构的快速版本已经完成了。我能在我的心流状态中看到我可以继续添加东西，我可以继续玩，但在右边，它还在运行。顺便说一句，我仍然觉得左边的还是太慢了。我们需要让它变得更快。

<details><summary>Original English</summary>
So
this
is
going
to
be
the
game
snake.

And
we
can
see
on
the
left
the

heterogeneous
fast
one's
done.
I
can
see

in
my
flow
state
I
can
keep
adding

things.
I
can
keep
playing
but
on
the

right
side
it's
still
going.
And
by
the

way
I
still
think
the
left
side's
too

slow.
We
need
to
make
that
even
faster.
</details>

然后我们可以给游戏添加一个对手，我们能看到即使有工具调用，即使有着它正在做的一切事情，它也会完成，而另一个则依然会卡在那里，因为这根本上关乎你如何用相同的资源获得更高的效率和更好的性能。它还会继续运行下去。我不会让大家干等着这个。

<details><summary>Original English</summary>
And
then
we
can
add
a
competitor
to
the

game
and
we
can
see
even
with
the
tool

calls,
even
with
all
the
things
that

it's
doing,
it's
going
to
complete
and

then
the
other
one
will
still
be
hanging

because
it's
fundamentally
about
how
can

you
drive
more
efficiency
and
better

performance
with
the
same
resources.

It's
going
to
go
on.
I'm
not
going
to

make
you
guys
wait
for
this.
</details>

人们经常指出的另一件事是：推理是瓶颈吗？工具调用是瓶颈吗？我认为这是一个很好的切入点。如果我们回顾刚才我花时间更新幻灯片时的轮次时间线，我们可以看到其中 80% 是推理，18% 是工具调用。如果我们模拟完全相同的情况，并实现 10 倍更快的推理速度，我们可以看到，如果我们不对工具调用进行优化，届时将有 67% 是工具调用。

<details><summary>Original English</summary>
One
thing
that
people
often
point
out

too
is
is
inference
the
bottleneck?
Our

tool
calls
the
bottleneck.
And
I
think

this
is
a
great
point.
If
we
look
back

to
the
turn
timeline
from
the
time
that

I
was
spending
updating
my
slide,
we
can

see
that
80%
of
it
was
inference
and
18%

of
it
was
tool
calls.
If
we
simulate

that
same
exact
thing
and
have
10x

faster
inference,
we
can
see
that
67%
of

that
will
be
tool
calls
at
that
point
if

we
don't
optimize
the
tool
calls.
</details>

这就是为什么我们必须不断去解决应用的瓶颈，并在可能的地方去摘取触手可得的果实。如今，人们专注于推理速度，而我们可能还没有针对工具调用这块以及工具调用的方式进行同样程度的优化，因为它现在还不是瓶颈。如果我把上面那个工具调用砍掉，它对最终应用其实根本算不上有什么影响。但一旦我们的推理变得快得多，我们就必须思考如何以更高效、更高性能的方式来调用这些工具，因为否则的话，它们就会成为我们所有人都在傻等的罪魁祸首。

<details><summary>Original English</summary>
That's
why
it's
important
that
we
have
to

constantly
attack
the
bottlenecks
of
the

application
and
get
the
lowhanging
fruit

where
we
can.
Today,
people
are
focused

on
inference
speed
and
maybe
we
haven't

optimized
the
tool
call
side
and
how

tools
are
called
as
much
because
it's

not
the
bottleneck.
If
I
cut
away
the

tool
calls
on
the
upper
one,
it
wouldn't

even
really
matter
to
the
end

application.
But
once
we
get
much

faster,
we
have
to
think
about
how
to

call
these
tools
much
more
efficiently

and
much
more
performantly
because

otherwise
they're
going
to
be
the
reason

that
we're
all
waiting
around.
</details>

我认为好消息是，优化这些速度以及我们作为整个行业齐心协力在做的事情，是一个可验证的任务。如果我知道我的输入和输出应该是什么，我就可以让智能体以非常非常全栈的方式来做这件事。这也正是我们日益迈向的方向。我们正让这些智能体拥有自我改进回路，以在推理运行的过程中实时提升效率。在 Gimlet，我们正在为此构建递归式的自我优化，从数据中心的底层遥测一直拉取到模型层，并尝试利用所有这一切来提高工作负载的整体效率，因为如果你只优化一小部分，可能起不到太大作用。

<details><summary>Original English</summary>
I
think
the
good
news
is
that
optimizing

these
speeds
and
what
we're
all

collectively
doing
as
an
industry
is
a

verifiable
task.
If
I
know
what
my

inputs
and
outputs
should
be,
I
can
have

agents
do
this
very
very
full
stack.
And

that's
where
we're
increasingly
moving

to.
We're
having
self-improvement
loops

with
these
agents
to
drive
better

efficiency
on
the
fly
as
our
inference

is
running.
And
at
Gimlet,
we're

building
recursive
self-optimization
for

this
that
pulls
from
low-level
telemetry

from
our
data
centers
all
the
way
up
to

the
model
layer
and
trying
to
use
all
of

it
to
in
to
improve
the
overall

efficiency
of
the
workload
because
if

you
just
optimize
one
small
piece,
it

might
not
make
that
much
of
a
dent.
</details>

我想再展示一个演示，因为我觉得网络安全现在是每个人都在关注的事情。嗯，我们都看到人工智能令人难以置信的巨大进步提升了大家的意识，让大家意识到我们的软件中存在着所有这些漏洞，而且我认为这是更快推理真正能够大显身手的一个领域。

<details><summary>Original English</summary>
I
want
to
show
another
demo
because
I

think
that
cyber
security
is
on

everyone's
mind
right
now.
Um,
we're
all

seeing
like
the
huge
incredible
advances

in
AI
driving
awareness
that
there's
all

these
vulnerabilities
in
our
software

and
I
think
that
this
is
an
area
where

faster
inference
can
really
really
help.
</details>

所以这是一个虚构出来的假场景，但它是一个真实的应用，也是一个真实的演示。设想你在运营狗狗俱乐部（dog club），这是一个供爱狗人士上传狗狗图片并进行投票的网站。然而不幸的是，正如我们经常见到的那样，你的一个 node 依赖项存在漏洞，而且这是一个真正的漏洞。这确实是 node-tar，而你在你的应用上运行了一个安全智能体，它正试图监控实时流量，看看是否有自己不知道的异常情况。这个智能体并不知道这个漏洞，但它确实知道自己的工作是保护你的应用。

<details><summary>Original English</summary>
So
this
is
a
dumb
fake
scenario
but
it's

a
real
application
and
a
real
demo
where

imagine
that
you're
running
the
dog

club
and
that's
a
website
for
dog

lovers
to
upload
and
vote
on
pictures

of
dogs.
However,
unfortunately,
like

we
often
see,
one
of
your
node

dependencies
has
a
vulnerability
and

this
is
a
real
vulnerability.
This
is

really
a
node
tar
and
you're
running

a
security
agent
on
your
application

and
it's
trying
to
monitor
live
traffic

and
see
is
there
anything
going
wrong

that
I
don't
know
about.
This
agent

doesn't
know
about
this
vulnerability,

but
it
does
know
its
job
is
to
protect

your
application.
</details>

那么，我们来用正常的用户流量走一个快速的轮次。我们要上传一块狗饼干。

<details><summary>Original English</summary>
So,
let's
do
a
quick
turn
with
normal

user
traffic.
We're
going
to
upload
a

dog
biscuit.
</details>

在上方，我们有应用日志。在下方，我们有防御者。防御者正在进行监控，但它不在关键路径上，因为它不够快，无法真正在线实时响应每一个用户请求。它是在异步监控各项事务。我们可以看到饼干被上传了，我们看到这是一个正常的、你知道的、正常的上传。防御者没有发现任何问题。

<details><summary>Original English</summary>
And
on
the
upper
side,
we
have
the

application
logs.
And
on
the
bottom,
we

have
the
defender.
And
the
defender
is

monitoring,
but
it's
not
in
the
critical

path
because
it's
not
fast
enough
to

actually
respond
to
every
user
request

live.
It's
monitoring
things
async.

And
we
can
see
biscuit
gets
uploaded
and

we
see
that
this
is
an
okay,
you
know,

this
is
an
okay
upload.
The
defender

doesn't
see
any
problem.
</details>

但现在我们要让这个防御者在遭遇恶意上传时进行运作。这次上传利用了一个真正的漏洞：在 node-tar 中曾经有一个版本，你基本上可以根据被解压内容的解压目标路径，去覆写那些本不应该被你覆写的文件。

<details><summary>Original English</summary>
But
now
what
we're
going
to
do
is
have

this
defender
operating
when
there's
a

malicious
upload.
And
this
upload
is

exploiting
the
real
vulnerability
where

in
node
tar
there
was
a
release
where

you
could
basically
overwrite
files
that

you
weren't
supposed
to
overwrite
based

on
the
destinations
of
what
was
being

unzipped.
</details>

所以在这个示例中，我们有名叫 Ranger 的一条假的、坏的、恶意的狗。不是一条真正的狗。我们将看到防御者会判断出这是一个恶意行为。智能体足够聪明，能检测出它正在做一件不应该做的事情，即便它以前从未见过这个确切的漏洞。但不幸的是，Cat 的恶意上传已经接管了系统。所以你的网站瘫痪了。太迟了。你没能及时做出反应。

<details><summary>Original English</summary>
So
in
this
one
we
have
Ranger,
a
fake

bad
uh
malicious
dog.
Not
really
a
dog.

And
what
we're
going
to
see
is
that
the

defender
is
going
to
figure
out
that

this
is
a
malicious
thing.
The
agent
is

smart
enough
to
detect
that
it's
doing

something
that
it
shouldn't
be
doing,

even
though
it
hasn't
seen
this
exact

vulnerability
before.
But
unfortunately,

Cat's
malicious
upload
has
taken
over.

So
your
website's
gone.
It's
too
late.

You
didn't
react
in
time.
</details>

但如果我们用超快速的防御者重试这同一个恶意上传——同样，这是一个真实的演示，一个虚构的用例。嗯，我们可以看到凭借超快速的推理，我们能够做出反应，并以在线方式快得多的速度处理事务。这应该会改变我们最初思考如何使用智能体的方式。我们所有人都在思考如何以异步方式使用它们，但我们也应该思考如何以在线方式来使用它们。所以我们可以在底部看到工作器拦截了他们的请求，并且就像是在说：你在干什么？这显然是不对的。

<details><summary>Original English</summary>
But
if
we
retry
this
same
exact

malicious
upload,
but
this
time
with
an

ultra
fast
defender,
and
again,
this
is

a
real
a
real
demo
fake
use
case.
Um,
we

can
see
that
with
ultra
fast
inference,

we
can
react
to
things
and
do
things

online
much
more
quickly.
And
this

should
change
the
way
that
we
think
of

how
to
use
agents
in
the
first
place.

We're
all
thinking
about
how
to
use
them

in
an
async
way,
but
we
should
think

about
how
to
use
them
in
online
ways
as

well.
So
we
can
see
on
the
bottom
that

the
worker
blocked
their
request
and
it

was
like
what
are
you
doing?
This
is

obviously
wrong.
</details>

### 推理速度的未来

更快的互联网让我们从 SquirrelMail 走向了按需高清流媒体，对吧？就像你对比一下这个和这个，太不可思议了。如果你把这个展示给像我 5 岁时候的样子之类看，我一定会觉得大为震撼。而这仅仅是我能挑选的众多事物之一。那么，每秒 1 万个 token 的世界会是什么样子？我们今天大概处于几百的水平。当我们达到每秒 100 万个 token 时会是什么样子？那能为我们解锁什么？

<details><summary>Original English</summary>
So
faster
internet
took
us
from
squirrel

mail
to
ondemand
highresolution

streaming,
right?
Like
if
you
just
look

from
this
to
this,
it's
crazy.
If
you

showed
this
to
my
like
5-year-old
self

or
something,
I
would
have
been
like
my

mind
would
have
been
blown.
And
this
is

just
one
of
many
things
that
I
can

select.
So,
like
what
does
a
10,000

token
per
second
world
look
like?
We're

at
in
the
like
low
hundreds
today.
What

does
it
look
like
when
we
get
to
a

million
tokens
per
second?
Like
what

does
that
unlock
for
us?
</details>

我认为我们大家都应该问问自己这个问题。在人工智能领域，滑向冰球将要去的位置非常重要，对吧？变化太快了。我们需要做好准备。我们需要大胆思考。光做我们一直在做的事情是不够的。我认为我们都有过这样的经历：向我们的智能体提出一个大胆的要求，而在最新模型发布后，它就直接能运行了。延迟方面也会是同样的情况。

<details><summary>Original English</summary>
And
I
think
that
we
should
all
ask

ourselves
this
too.
It's
important
in
AI

to
skate
to
where
the
puck
is
moving,

right?
It's
changing
so
fast.
We
need
to

be
ready.
We
need
to
think
boldly.
It's

not
enough
to
just
do
what
we've
always

been
doing.
I
think
we've
all
had
the

experience
where
we
make
an
audacious

request
to
our
agent
and
after
the

latest
model
release,
it
just
works.
And

it's
going
to
be
the
same
thing
with

latency.
</details>

所以我觉得我们既可以去思考那些即将到来的想法——当我们达到某个延迟阈值时我们能做什么，也可以去思考那些真正科幻级别的事物。比如你看看像贾维斯之类的东西，当今的推理绝无可能快到能为钢铁侠提供那种体验。但我们会达到那个阶段的。因此，我对在线用例、在线安全、在线交互感到非常兴奋，比如我只想告诉我的智能体我想构建什么，它就在我面前直接构建出来，我甚至连字都不用打。

<details><summary>Original English</summary>
And
so
I
think
that
we
can

think
about
ideas
that
are
both
coming

soon
when
we
hit
a
certain
latency

threshold,
what
we
can
do,
but
also
the

stuff
that
is
real
life
sci-fi.
Like
if

you
look
at
something
like
Jarvis
or

something,
there's
no
way
today's

inference
could
be
fast
enough
to
power

that
experience
for
Iron
Man.
But
we

will
get
there.
So,
I'm
really
excited

about
online
use
cases,
online
security,

online
things
of
like
I
want
to
just

tell
my
agent
what
I
want
to
build
and

it's
building
it
right
in
front
of
me

and
I
don't
even
have
to
type
anything.
</details>

我认为我们将迎来全新的交互模式。你想想万物皆可按 Tab 键补全。我们如何能让用户侧的操作尽可能快捷、即时，因为推理侧也同样迅速以满足这种需求。我们将会拥有多得多的智能体。我们甚至可能会有由 Transformer 驱动的机器人，对吧？当这个门槛被打破时，我们能构建的东西实在太多了。而且我认为，作为这里的最前沿构建者，我们大家也应该去思考这个问题。

<details><summary>Original English</summary>
I
think
we're
going
to
have
new
patterns

of
interaction.
You
know,
think
tab

complete
for
everything.
How
can
we
have

the
user
side
of
things
be
as
quick
and

immediate
as
possible
because
the

inference
side
is
also
just
as
fast
to

accommodate
it.
And
we're
going
to
have

so
many
more
agents.
We're
going
to
have

even
maybe
transformers
driving
robots,

right?
There's
so
much
that
we
can
build

when
this
gets
unlocked.
And
I
think
as

builders
on
the
frontier
here,
we
should

all
be
thinking
about
this,
too.
</details>

非常感谢大家今天上午与我共度这段时光。嗯，大家可以在 X 上找到我，账号是 NSino。嗯，Gimlet 正在招人。非常希望能和大家交流。然后如果大家想玩那个 token mint 游戏，呃，你们也可以在这里找到那个二维码。非常感谢大家。

<details><summary>Original English</summary>
Thank
you
so
much
for
being
with
me
um

this
morning.
Uh
you
can
find
me
on
X
at

NSino.
Um
we're
hiring
at
Gimlet.
Would

love
to
talk
to
you
all.
And
then
if
you

want
to
play
the
token
mint
game,
uh
you

can
also
find
that
QR
here.
Thank
you
so

much
everyone.
</details>

### 与 Claude Code 协同的新思考

随着人工智能模型变得越来越好，我们过去的老旧最佳实践是否正在阻碍我们前进？为了重新思考我们如何使用 Claude Code 开展工作，有请 Anthropic 技术人员 Lydia Halley。

<details><summary>Original English</summary>
As
AI
models
get
better,
are
our
old

best
practices
holding
us
back?
To

rethink
how
we
work
with
Claude
Code,

please
welcome
Lydia
Halley,
member
of

technical
staff
at
Anthropic.
</details>

大家好。噢，我的麦克风已经有声音了。抱歉，今天早上我们遇到了一些技术故障。所以希望一切都能顺利运作。

<details><summary>Original English</summary>
Hi
everyone.
Oh,
my
microphone
already

works.
Sorry,
we
have
some
technical

issues
this
morning.
So
hopefully

everything
works.
</details>

我们在看下面那里。

<details><summary>Original English</summary>
We're
looking
down
there.
</details>

Scream start。

<details><summary>Original English</summary>
Scream
start.
</details>

对。你们都试过 Fable 52 了吗？

<details><summary>Original English</summary>
Yeah.
Have
you
all
tried
Fable
52
yet?
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

<!-- chunk 4/50 -->

有人吗？感觉怎么样？喜欢吗？

<details><summary>Original English</summary>
Anyone?

How

is

it?

Like

it?
</details>

>> 挺好的。Opus 55 更好，还是更差？不同用例吧，对吧？

<details><summary>Original English</summary>
>> Yeah.

Opus

55

better,

worse,

different

use

cases,

right?
</details>

>> 是的，肯定更便宜。

<details><summary>Original English</summary>
>> Yeah.

Cheaper

for

sure.
</details>

>> 决定把信号隐藏起来。全都……应该没问题了。

<details><summary>Original English</summary>
>> Decided

to

hide

the

signal.

It's

all

It

should

be

good.
</details>

>> 那么，这个应该显示在那个屏幕上。

<details><summary>Original English</summary>
>> So,

this

should

be

on

that

screen.
</details>

>> 对。但我们是在往下看，

<details><summary>Original English</summary>
>> Yes.

But

we're

looking

down,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 你看到了吗……让我看看。

<details><summary>Original English</summary>
>> Are

you

seeing

Let

me

see.
</details>

>> 所以这个必须开着。

<details><summary>Original English</summary>
>> So

this

has

to

be

on.
</details>

>> 我们需要给它弄个云端。先把这个隐藏起来。

<details><summary>Original English</summary>
>> We

need

a

cloud

for

it.

Let's

make

sure

to

hide

this.
</details>

>> 我想把这个缩小，这样我们就可以重新拖过来了。

<details><summary>Original English</summary>
>> I

want

this

to

go

small

so

we

can

drag

over

again.
</details>

>> 你可以拖动它。开始放你的幻灯片吧。启动你的幻灯片放映。然后它就会在下面显示出来。能看到什么了吗，J？我照你说的做了。天哪。好的。你能看到什么吗？我刚才顺便问一下。它刚刚是死机了吗？

<details><summary>Original English</summary>
>> You

can

drag

it.

Start

your

slides.

Start

your

slideshow.

And

then

it's

going

to

show

up

down

there.

Can

you

see

anything

yet,

J?

I

did

what

you

said.

Oh

my

god.

Okay.

Are

you

seeing

anything?

I

was

asking

real

quick.

Did

it

just

die?
</details>

>> 我能赶紧拔掉它吗？

<details><summary>Original English</summary>
>> Can

I

unplug

it

real

quick?
</details>

>> 好，请拔吧。

<details><summary>Original English</summary>
>> Yeah,

please.
</details>

>> 刚才是我死机了吗？

<details><summary>Original English</summary>
>> Did

I

just

die?
</details>

>> 我想它刚刚死机了。

<details><summary>Original English</summary>
>> I

think

it

just

died.
</details>

>> 天哪。我是说，我不知道该怎么办了。不是我不该死机吗？

<details><summary>Original English</summary>
>> Oh

my

gosh.

I

mean,

I

don't

know

what

to

do.

Shouldn't

I

die?
</details>

>> 是啊。现在，现在它就……

<details><summary>Original English</summary>
>> Yeah.

Now,

now

it's

it's

just
</details>

>> 要不我今天晚点再演讲？我们根据你的日程安排调整一下。下一次中间有一点休息时间。

<details><summary>Original English</summary>
>> Should

I

just

do

my

talk

later

today?

We

fix

me

with

your

schedule.

A

little

break

in

the

next.
</details>

>> 好的大家，我的笔记本电脑刚刚坏了。所以，我……没有任何反应。我不知道该怎么办。我们，呃，噢，它刚刚重启了。无论如何，我觉得自己刚才在这里等了整整 20 分钟，我不想耽误下一位的时间。简而言之（TLDDR），我们从最初在 cloud code 会话中高度人工介入（in the loop），转变为，你知道的，在云端运行这些持续数小时的长时间运行会话，使用像 Opus 55、Fable 52 这样非常擅长自我验证的模型，以至于人类的角色真的发生了转变。让我们看看。我觉得这行不通。

<details><summary>Original English</summary>
>> Okay,

y'all.

My

laptop

just

died.

So,

I

Nothing

is

happening.

I

don't

know

what

to

do.

We

uh

Oh,

it

just

restarted.

Anyway,

I

I

feel

like

I've

just

spent

20

minutes

just

waiting

here

and

I

don't

want

to

take

the

next

guy.

that

TLDDR,

we

went

from

being

super

in

the

loop

with

our

cloud

code

sessions

to,

you

know,

running

these

long

running

sessions

that

run

for

hours

in

the

cloud

with

these

models

like

Opus

55,

Fable

52

that

are

so

good

at

verifying

themselves

that

the

role

as

a

human

has

really

shifted.

Let's

see.

I

don't

think

this

is

going

to

work.
</details>

>> 太奇怪了。

<details><summary>Original English</summary>
>> That's

so

weird.
</details>

>> 我知道。我不知道它在搞什么。另外今天，请大家务必顺道去我们的 Anthropic 展位看看。我们整天都在那里。我们有很棒的周边商品。我们还有很棒的演示和很多好玩的东西。我们在那里还有一个照相亭之类的，很有趣。如果你有任何问题，也会在那里见到我。但首先得把这个弄好。忽略我的……它为什么重启了？我不知道。Windows 服务器遇到问题。为什么……噢，Apple。好吧。我只是得……我只是想确保我不是……

<details><summary>Original English</summary>
>> I

know.

I

don't

know

what

that's

doing.

Also

today,

make

sure

you

come

by

our

anthropic

booth.

We're

there

all

day.

We

have

good

merch.

We

also

have

good

demos

and

just

fun

stuff.

We

have

like

a

photo

booth

there

as

well

which

is

fun.

You'll

see

me

there

as

well

if

you

have

any

questions.

But

first

you

got

to

make

this

work.

Ignore

my

Why

did

it

restart?

I

don't

know.

Windows

server

experience

a

problem.

Why

do

Oh,

Apple.

Okay.

I

just

got

to

I

just

want

to

make

sure

I'm

not
</details>

>> 人们常常想知道，这个领域的工程未来背后的故事到底是什么。呃，结果发现是修电脑并让它跑起来。这向来是个很有趣的故事，比如技术越先进，基本上就越难让它听你的使唤。会议就是会议，视听设备就是视听设备，笔记本电脑也永远都是笔记本电脑的德行。呃，有人跟我说，这可能是 Anthropic 员工第一次没有在背后驱使智能体（agent）来让电脑听命行事。

<details><summary>Original English</summary>
>> People

often

wonder

what

the

story

is

behind

what's

the

future

of

engineering

in

this

space.

Uh

and

it

turns

out

that

fixing

the

computer

and

making

it

go.

It's

it's

always

a

fun

story

like

the

more

advanced

technology

gets

the

harder

it

is

to

basically

make

it

do

your

bidding.

And

conferences

are

conferences

AV

is

AV

and

laptops

are

always

going

to

the

laptop.

Uh,

I'm

told

that

this

might

be

the

first

time

that

an

anthropic

employee

has

not

been

proddding

an

agent

to

wind

up

getting

a

computer

to

do

that

bidding.
</details>

>> 我就是这个意思。我们需要在云端弄这个。我只需要一个小小的云端机器人在旁边帮我。让我瞧瞧。

<details><summary>Original English</summary>
>> That's

what

I'm

saying.

We

need

cloud

for

it.

I

just

need

a

little

cloud

robot

helping

me

here.

Let's

see.
</details>

>> 确实。我不想抢你的风头，但我也可以继续在这儿耍嘴皮子。

<details><summary>Original English</summary>
>> Exactly.

I

don't

want

to

step

on

your

toes,

but

I

can

also

keep

running

my

mouth.
</details>

>> 有些人运行智能体，我是在耍嘴皮子。这里面肯定有个关于生产环境的笑话，但我太累了想不出来。事情在理论上都行得通，但在生产环境中却不行。

<details><summary>Original English</summary>
>> Some

people

run

agents.

I

run

my

mouth.

it.

There's

a

production

joke

in

there

somewhere,

but

I'm

too

tired

to

find

it.

Things

work

in

theory,

but

not

in

production.
</details>

>> 那呃就是为什么我把暂存环境（staging environment）称为“理论环境”。

<details><summary>Original English</summary>
>> That's

uh

why

I

call

the

staging

environment

theory.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 能请你在 DSM 里给我们展示一下吗？

<details><summary>Original English</summary>
>> Can

you

show

us

in

the

DSM,

please?
</details>

>> 不过看起来你好像准备好了。也许吧。

<details><summary>Original English</summary>
>> But

it

looks

like

you're

up.

Maybe.
</details>

>> 我得看一下。我没带眼镜。

<details><summary>Original English</summary>
>> I

just

have

to

see.

I

don't

have

my

glasses

with

me.
</details>

>> 记住，只要你是个足够讨厌的混蛋，每一次代码审查都是对抗性的。是的。

<details><summary>Original English</summary>
>> Remember,

every

code

review

is

adversarial

if

you're

a

big

enough

jerk.

Yes.
</details>

>> 等等。不，不，不，不。

<details><summary>Original English</summary>
>> Wait.

No,

no,

no,

no.
</details>

>> 噢，那是……

<details><summary>Original English</summary>
>> Oh,

that's
</details>

>> 抱歉。那是……对。

<details><summary>Original English</summary>
>> Sorry.

It

was

Yeah.
</details>

>> 当然，创立公司头号理由就是：作为联合创始人，主分支（main）就成了你的特性分支（feature branch）。

<details><summary>Original English</summary>
>> And

of

course,

the

number

one

reason

to

found

a

company

is

that

as

a

co-founder,

Maine

becomes

your

feature

branch.
</details>

>> 祝其他人好运吧。好吧。我能……我想在我的屏幕上马上看一下。抱歉。因为呃我不知道为什么它不显示。我该开始了吗？我们将……我只是不想……你能关掉我们的麦克风吗，免得大家都听到我们说话？

<details><summary>Original English</summary>
>> Good

luck,

everyone

else.

All

right.

Can

I

I

want

to

see

that

on

my

screen

real

quick.

Sorry.

Because

um

I

don't

know

why

it's

not

showing.

Should

I

go?

We're

转

I

just

don't

want

to

Can

you

close

our

mic

so

everyone

can't

hear

us

talking?
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay,
</details>

>> 稍后见。希望我还能回来。你们会听到我的消息的。

<details><summary>Original English</summary>
>> I'll

see

you

later.

Hopefully

I'll

come

back.

You'll

hear

from

me.
</details>

### 会程调整与下一位演讲者入场

这里的议程稍作调整。我相信我们的下一位演讲者是 Michelle Chen。如果我说错了，请纠正我。没人去拔那根呃那根线。如果您能给我们大约三分钟时间，我们将呃在此稍作停顿。此外，你们都在这里听这个干嘛呢？你们不应该去戳戳点点驱动各种智能体，看看还能让多少个运转起来吗？这些 token 可不会自己烧掉。

<details><summary>Original English</summary>
Slight

change

in

programming

here.

I

believe

our

next

speaker

is

Michelle

Chen.

Correct

me

if

I'm

wrong

on

that.

No

one

is

yanking

the

uh

the

cord

there.

If

you

can

give

us

about

three

minutes,

we

will

uh

take

a

small

pause

here.

Besides,

what

are

you

all

doing

listening

to

this?

You

shouldn't

be

poking

and

proddding

agents

and

seeing

how

many

more

you

can

wind

up

going.

The

tokens

aren't

going

to

burn

themselves.
</details>

>> 我们需要更多带宽。

<details><summary>Original English</summary>
>> We

need

more

bandwidth.
</details>

噢，本地推理的用例突然变得格外清晰起来。会议室 Wi-Fi，就是这么回事。我以前在飞机上搞过，当时有趣的是我的笔记本电脑听起来突然像喷气式飞机的第三台发动机，但它确实跑通了，而且写的代码比我写的还好。呃那虽然不是什么很高的标准，但这确实意味着我不用倒退回去像个古老的耕作农夫那样手工把东西敲出来了。所以，就是这样。

好了，接下来由 Michelle Chen 带来演讲，主题是 Cloudflare 作为一个新形态实验室（Neolab）。呃，我个人认为它其实是一个数据库，因为我觉得任何东西只要你拿法不对，它都是个数据库，但出于某种原因他们并没有征求我的意见。不管怎样，Michelle，非常感谢你。请上台吧。

<details><summary>Original English</summary>
Oh,

suddenly

the

use

case

for

local

inference

makes

itself

extraordinarily

clear.

Conference

Wi-Fi.

There

we

go.

I

I've

done

it

on

planes

before

and

what

made

that

fun

was

suddenly

my

laptop

became

what

sounded

like

the

third

engine

on

the

jet,

but

it

worked

and

it

wrote

better

code

than

I

did.

Uh

that's

not

a

high

bar,

but

it

does

mean

I'm

not

going

back

in

time

to

be

the

oldtimey

uh

typing

things

out

by

hand

like

some

sort

of

agrarian

farmer.

So,

there's

that.

All

right,

next

up

we

have

Michelle

Chen

talking

about

Cloudflare

is

a

Neolab.

Uh,

personally

I

believe

that

it's

a

database

instead

because

I

think

everything's

a

database

when

you

hold

it

wrong,

but

for

some

reason

I

wasn't

consulted.

Anyway,

Michelle,

thank

you

very

much.

Please

come

on

up.
</details>

### Michelle Chen：Cloudflare 走向新形态 AI 实验室之路

对 Cloudflare 来说，成为一种新型 AI 实验室意味着什么？为了探索新模型、边缘 AI，以及成为智能体云（agent cloud）的雄心，请热烈欢迎 Cloudflare 团队产品经理 Michelle Chen。

<details><summary>Original English</summary>
What

does

it

mean

for

Cloudflare

to

be

a

new

kind

of

AI

lab?

To

explore

new

models,

edge

AI,

and

the

ambition

to

become

the

agent

cloud,

please

welcome

Michelle

Chen,

group

product

manager

at

Cloudflare.
</details>

大家好，我叫 Michelle Chen。今天非常高兴来到 AI Engineer Code Summit，聊一聊为什么 Cloudflare 变成了一个 Neolab。在 Cloudflare，我是这里的产品组产品经理。我在产品团队负责像 Workers AI、AI Search 以及 AI Gateway 这些产品。所以今天我们将一起回顾 Cloudflare 的成长历程。

大家可能听说了我们最近发布并训练了一些模型。我将向大家进一步介绍原因以及大家可以用它来做什么。我们将踏上一段略带哲学意味的旅程。呃当我在准备这次演讲时，本来想引用这句话，结果 Anthropic 上周末发了一篇博客文章用了我的这句引言，但我不管怎样还是打算用它。嗯，这句引言是这样的……

稍等一秒。嗯，这句引言出自克尔凯郭尔（Kierkegaard），它是说：“生活唯有向后回顾才能被理解，但生活必须向前践行。”我认为这句引言对我们来说真的非常非常贴切，因为 Cloudflare 是一家拥有 16 年历史的公司，这些年来我们做了很多事情，但不知怎的，我们做对了一些事情，最终走到了必须成为一个 Neolab 的阶段。

所以我们要经历一段小小的历程。我们要做的第一件事就是向后回顾，讲讲为什么 Cloudflare 不得不……呃，变成了一个 Neolab。

给我一秒钟。

太好了。我们将向后回顾，讲讲为什么 Cloudflare 变成了一个 Neolab。Cloudflare 是一家成立了 16 年的 CDN 公司。我们今年 9 月份刚在生日周庆祝了我们的 16 岁生日。

而我们最早是从 CDN 起家的。作为一家 CDN 公司，你必须做的事情就是尽快向用户提供内容。你位于用户请求与源站之间，你在中间提供协助，你可以做像缓存、防护、安全之类的事情。Cloudflare 大致就是这样起步的。

但 Cloudflare 的基础设施必须具备适应性，才能成为 CDN。所以我们在 16 年前的 2010 年，推出了我们自己的基础设施。我们快速的 CDN 必须无处不在。这与计算集中在 US-East-1 或 US-West-1 的传统超大规模云厂商（hyperscaler）截然不同。Cloudflare 的基础设施是一个完全不同的范式。我们在世界各地都设有尽可能靠近用户的数据中心。这在成为 CDN 的过程中至关重要。

但现在我们拥有了这些基本上尽可能靠近用户运行的计算机。所以我们当时自问：人们还会希望用这些计算机来构建什么呢？于是应运而生。我们也开始推出这些计算原语（compute primitives）。

于是在 2017 年，我们推出了一款名为 Workers 的产品，它基本上就像你可以运行的无服务器函数（serverless functions）。它与当时的虚拟机（VM）形成了对比，那时你必须租用整台机器，并为整台机器付费。不管你用不用，都要付钱。而使用 Workers，你只需执行一些代码，然后 worker 就会消失。你不需要为它付费。它需要……

<details><summary>Original English</summary>
Hi

everyone,

my

name

is

Michelle

Chen.

I'm

so

excited

to

be

here

today

at

AI

Engineer

Code

Summit

chatting

a

little

bit

more

about

why

Cloudflare

became

a

Neolab.

So

at

Cloudflare

I

am

the

group

PM

here.

I

run

on

the

product

team

working

on

products

like

workers

AI,

AI

search,

AI

gateway

as

well.

And

so

today

we're

going to

go

through

this

little

journey

of

how

Cloudflare

came

to

be.

You

might

have

heard

that

we

launched

and

trained

some

models

recently.

I'm

going

to

tell

you

a

little bit

more

about

why

and

what

you

can

be

doing

with

it.

And

so

we're

going to

go

through

a

little bit

of

a

philosophical

journey.

Uh

when

I

was

preparing

for

this

talk,

I

wanted

to

use

this

quote

and

then

Anthropic

like

launched

a

blog

post

last

weekend

and

used

my

quote,

but

I'm

still

going

to

use

it

anyways.

Um

so

the

quote

goes

in

one

second.

Um

the

quote

is

from

Kirkagard

and

it

says,

"Life

can

only

be

understood

backwards,

but

it

must

be

lived

forwards."

And

I

think

this

is

really

really

apt

quote

here

for

us

because

at

Cloudflare

we're

a

16-year-old

company

and

we've

done

so

many

things

over

the

years

but

somehow

we

got

all

some

of

the

pieces

right

and

we

ended

up

having

to

become

a

Neolab.

So

we're

going to

go

through

a

little

bit

journey.

The

first

thing

we're

going

to

do

is

look

backwards

and

talk

through

why

Cloudflare

had

to

uh

became

a

Neolab.

Give

me

one

second

here.

Perfect.

We're

going

to

go

backwards

and

talk

through

why

Cloudflare

became

a

Neolab.

So,

Cloudflare

is

a

16-year-old

CDN

company.

We

just

celebrated

our

16th

birthday

uh

at

birthday

week

this

year

uh

in

September.

And

we

first

started

as

a

CDN.

So,

as

a

CDN

company,

what

you

have

to

do

is

you

have

to

serve

content

as

quick

to

your

users

as

possible.

you

sit

between

the

users

request

and

the

origin

and

you

help

uh

sit

in

the

middle

and

you

can

do

things

like

cache

and

protect

do

security

and

things

like

that.

So

that's

kind

of

how

Cloudflare

started.

But

Cloudflare's

infrastructure

had

to

be

adaptable

in

order

to

become

the

CDN.

And

so

what

we

did

was

16

years

ago

in

2010,

we

launched

with

our

own

infrastructure.

Our

fast

CDN

had

to

be

everywhere.

And

this

looks

really

different

than

a

traditional

hyperscaler

where

compute

is

centralized

in

US-

East

one

or

US

West

one.

Cloudflare's

infrastructure

is

a

completely

different

paradigm.

We

have

data

centers

all

around

the

world

as

close

to

the

user

as

possible.

And

this

is

really

important

in

becoming

a

CDN.

But

now

we

have

these

computers

basically

running

as

close

to

the

user

as

possible.

So

we

thought

to

ourselves,

what

else

can

we

be

doing

with

these

computers

that

people

would

want

to

build

with?

And

so

came.

We

started

launching

these

compute

primitives

as

well.

And

so

in

2017,

we

launched

a

product

called

workers,

which

is

basically

like

serverless

functions

that

you

can

run.

It

contrasted

VMs

at

that

time

where

you

had

to

rent

a

whole

machine

and

pay

for

the

whole

machine.

Either

you're

using

it

or

not

using

it.

And

so

with

workers,

you

just

execute

some

code

and

then

the

worker

goes

away.

You

don't

have

to

pay

for

it.

It

takes
</details>

<!-- chunk 5/50 -->

启动只需几毫秒，而不是几秒钟。紧接着我们又推出了其他计算原语，比如更有状态特性的 Durable Objects。然后在 2025 年，我们同样推出了容器服务，因为确实存在一些需要类似于虚拟机环境的工作负载，而我们希望所有这些工作负载都能在 Cloudflare 上运行。所以你看，从 2017 年我们开发者平台的起步阶段开始，我们就有了这些计算原语，大家开始使用它，开始构建诸如静态网站之类的东西。于是我们暗自思索：我们该如何提升它、把它带到下一个高度？于是我们同样引入了存储功能。因此在 Cloudflare 的开发者平台上，我们拥有了这些存储原语：我们有 KV，有用于对象存储的 R2，同样也有像 D1 这样的数据库。这里的核心构想是，人们应该能够完全在 Cloudflare 上构建全栈应用——那些能够持续运行并构建完整应用、Web 应用和平台的有状态应用。所以我们拥有了这一基础设施，向其中加入了计算原语，又加入了存储原语。接着时间来到了 2023 年。如果大家还记得 2023 年发生了什么的话，ChatGPT 可以说一下子爆发了，它改变了我们思考 AI 的方式，对吧？我记得当时正值 Birthday Week（周年庆周），在 Birthday Week 前三周，我们许多人坐在一间会议室里，心想：既然 ChatGPT 正在兴起，我们现在该做些什么？Cloudflare 凭借我们的基础设施和原语，能在这里扮演什么角色，从而加入这场 AI 角逐？于是在 2023 年，我们推出了一款名为 Workers AI 的产品，将 GPU 引入了我们的网络。再次强调，这是真正高度分布式的，GPU 的运行位置尽可能地贴近用户。它不像美国东部 US-East-1 的超大规模云厂商那样高度集中，而是尽可能地在靠近边缘的位置运行。我们在启动 Workers AI 时有一个假设：我们的假设是模型会变得越来越小，因此网络延迟将会变得越来越重要。我们上线时搭载的是能够适配分布在全球各地的小型硬件上的小模型。我们当时认为模型会变得更好、更快、更聪明，而网络延迟将在这里产生巨大得多的影响。

<details><summary>Original English</summary>
milliseconds to start up, not seconds as well. And then we followed with other compute primitives like durable objects which are more stateful. And then in 2025, we launched containers as well because there are some workloads that do need something like a VM and we want all of those workloads to be able to run on Cloudflare. So now you know 2017 start of our developer platform we have these compute primitives people started using it people started building more like static websites and things like that so we thought to ourselves how do we elevate this and take it to the next level so we introduced storage as well and so we have these storage primitives on cloudflare's developer platform we have KV we have R2 do object storage we have databases like D1 as well and the idea here is that people should be able to build full stack applications all on Cloudflare stateful applications where people can go on and start building um full applications and web apps and platforms on Cloudflare's developer platform. So we have this infrastructure, we added compute primitives to it, we added storage primitives to it and then came 2023. And if you guys remember what happened in 2023, chat GPT kind of blew up a little bit and it changed how we think about AI, right? And I remember it being birthday week and uh three weeks before birthday week a lot of us sat together in a room and we were like what should we do now that chat GPT is on the rise? What can Cloudflare play in here with our infrastructure and our primitives in order to be in this AI game? So in 2023 we launched a product called workers AI where we added GPUs to our network. And so again this is really distributed where GPUs are running as close to the user as possible. It's not centralized like a US East1 hyperscaler for example, but it's running as close to the edge as possible. And we had a hypothesis when we started workers AI. Our hypothesis was that models were going to get smaller, so that network latency was going to become more and more important. We launched with small models that could fit on our small hardware around the world that were super distributed. And we thought that people would have models get better and faster and smarter and that network latency was going to play a much more bigger impact here.
</details>

结果实际发生的情况恰恰相反，模型变得越来越大。我们从当时属于前沿规模的大约 70 亿（7B）参数，一路发展到陆续推出的 3 万亿（3T）参数模型。我认为回过头来看这并不令人震惊，因为你知道，在我们通往 AGI 的道路上，如果你遵循缩放定律（scaling law），随着你在更多数据上进行训练、随着模型变得更大，它们的泛化能力也更强。因此在通往 AGI 的道路上，我们为了获得越来越大、越来越聪明的模型而不断推进前沿研究，这是完全合乎逻辑的。

<details><summary>Original English</summary>
Well, uh actually the opposite happened and models got larger and larger. So we went from something like 7 billion parameters which was frontier scale at the time to being the three trillion parameter models that were getting launched. And I think this is not so shocking when you look back in time because you know as we're on the way to AGI um if you're following scaling law as you train on more data as the models get larger they're more generalizable and so on the path to AGI it makes sense that we're pushing the frontier of research here in order to get larger and larger and smarter models.
</details>

所以这与我们的假设背道而驰，对吧——原本假设模型会变小，结果模型实际上越来越大，网络延迟变得越来越无足轻重。那我们是怎么做的呢？

<details><summary>Original English</summary>
So this goes against our hypothesis right that the models were going to get smaller. the models actually ended up being larger and the network latency mattered less and less. So what did we do?
</details>

### 从大模型到 System 1

我们最终进行了转向。Cloudflare 在托管这些庞大模型方面也变得非常擅长。所以在 2026 年 3 月，我们上线了 Kimi，随后又接入了 GLM 和 DeepSeek，以及这些托管在我们基础设施上的万亿参数大模型。这是无服务器化的。用户发起一次 API 调用，就能获得返回的 token。其实我们花了不少时间才决定这么做，对吧？2026 年 3 月才去托管这些模型，在这场竞争中其实已经相当晚了，但我们当时试图做出清醒的权衡：我们去托管它到底合不合理？它并不完全契合我们原本的基础设施定位，但它与开发者平台的契合度极高。

<details><summary>Original English</summary>
We ended up pivoting. So cloud got really good at serving these giant models as well. So in March 2026, we launched Kimmy and then we followed up with GLM and DeepSeek and these large trillion parameter models um hosted on our infrastructure. And so this is serverless. People hit an API call and get a token back. It actually took us a while in order to decide to do this, right? We March 2026 is actually pretty late in the game to to serving these model, but we were trying to make a conscious decision here on does this actually make sense for us to be serving it. It didn't really fit with our infrastructure story, but it fit very well with the developer platform.
</details>

所以在 2026 年，我们备齐了所有这些原语：我们拥有贴近用户运行的 Cloudflare 独特基础设施；拥有可供大家在上面构建 Agent 的计算原语，即 Workers 和 Durable Objects，当你的 Agent 需要完成任务时便启动执行，不需要时就休眠；我们拥有存储原语，以便你的 Agent 能够切实与数据和存储交互；接着我们拥有了模型，也就是驱动 Agent 的这些大型模型。所有这一切都契合了 Cloudflare 的 Agent 云图景。于是我们开始讲述这样一个故事：我们希望成为 Agent 云平台，希望 Agent 能部署在我们这里，由我们这里托管的模型提供动力，使用我们的计算和数据原语，全部构建在我们的基础设施和网络之上。但总觉得哪里不太对劲。我们总觉得这里始终缺少了一块拼图，因为现有的基础设施模式并不一定契合 Workers AI 最初的设计初衷。

<details><summary>Original English</summary>
So in 2026, we had all these primitives in place. We had the infrastructure which is unique to Cloudflare running close to users. We had compute primitives where people were building agents on top of so workers and durable objects right as your agent needs to complete a task it goes on and it spins and does a task and then sleeps when it doesn't. We had storage primitives so your agents can actually interact with data and storage and then we had models these large models that were powering agents. And so all of this fit into the Cloudflare agent cloud story. And so we started telling this narrative that we want to be the agent cloud. We want agents to be deployed on us powered by models on us using our compute and data primitives all built on our infrastructure and our network. But it never felt quite right. We felt like we were always missing a piece here because the infrastructure pattern didn't necessarily fit in with what workers AI was designed for.
</details>

所以我想坐在这里分享我的第二句富有哲理的引言——考虑到作为一名身处 AI 领域的中国女孩，这多少有点冒险，但我还是要把这句中国古话送给你们。它大体上是说……

它的意思是这里万事俱备，只欠东风。

关于这一点有一件事是：你无法真正预测风会从何处来，或者会以何种方式吹来，但当它发生时，你必须能够迅速做出反应。而在 2026 年 9 月，东风来了。

<details><summary>Original English</summary>
And so I'm going to sit here and give you my second philosophical quote which is a risk considering that I'm a girl in Chinese and AI, but I'm going to give you this Chinese quote anyways. Um, and uh, it basically says, which means everything is ready here. All that's missing is the east wind. And one of the things uh about this is like you can't really predict where the wind is going to come from or how it's going to come, but you need to be very reactive when it happens. And so in September 2026, the east wind came.
</details>

Typesafe 推出了一款名为 Jev 的模型，并引入了“System 1 模型”这一概念，这与我们通常所了解的 LLM 形成了鲜明对比——传统的 LLM 是自回归的，生成 token 需要耗费很长时间，其计算呈二次方扩展等等。而 System 1 模型是截然不同的范式，它实际上只需对输入进行一次前向传播（forward pass），就能生成可供你据此做出决策的输出。

<details><summary>Original English</summary>
Typesafe launched a model called Jev and introduced this idea of system one models and it contrasted what we typically knew with LLMs which were auto regressive and taking a long time to generate tokens. It scales quadratically etc. A system one model is a completely different paradigm where it actually just takes one forward pass through the inputs and generates an output that you can use to make decisions with it.
</details>

我真切地认为这归结于完美的时机。我认为大家开始对 LLM 有点厌倦了，因为它们太昂贵了。它消耗了太多的 token，太耗费时间。我不知道你们感觉如何，但当我自己阅读推理轨迹（reasoning trace）时，有时看到 LLM 算不对东西，我的血压都会升高。因此，我认为过去我们把所有的东西都一股脑发给 LLM，已经开始对此感到沮丧了。所以当这种 System 1 和 Jev 的范式开始出现时，我们觉得对我们来说采纳它简直太合乎情理了，对吧？我们不必把每个请求都发送给 LLM。我们可以把其中一部分发送给 System 1 模型。这样一来，System 1 模型实际上最终分担了庞大 LLM 的工作量，你把任务交由小巧而快速的模型处理，这两者本就应当协同工作。它们应当互为补充，从而更快地达到最终目标。所以你看，我们又回到了这些小巧而快速的模型上，对吧？这正是最初 Workers AI 的假设。

<details><summary>Original English</summary>
And so I really think that this came down to perfect timing. I think people were starting to get fed up a little bit with LLMs because they were so costly. It cost so many tokens. It's s time consuming. And I don't know about you, but when I read a reasoning trace, sometimes my blood pressure rises when the LLM doesn't get the right the things right. And so I think we were sending everything to LLMs and started getting frustrated with it. And so when this system one and Jev paradigm started coming on board, we were like this makes so much sense for us to adopt, right? We don't have to send every request to an LLM. We can send some of it to a system one model. And so the system one models actually end up taking work off of the giant LLMs and you give it to the small fast models and the two are supposed to work in tandem. They're supposed to complement each other and get to the end goal faster. And so if you look we are back at these small and fast models right this was the original workers AI hypothesis
</details>

所以 Cloudflare 在这里并没有错，我们实际上只是在这些小巧快速的模型上走得太超前了。网络延迟再次变得重要起来：我们不仅希望模型响应敏捷，而且希望网络延迟更加低速快捷。因此我们决定在此有所作为，但 Jev 是闭源的，Cloudflare 无法直接托管 Jev 模型来发挥我们基础设施的优势。那我们决定怎么做呢？我们构建了自己的 Jev 版本。Jev 是在 9 月 15 日发布的。仅仅三天之后的 9 月 18 日，我们就开始试验，并推出了我们版本的 Jev——我们针对它的第一次实验。接着我们经历了一周的深思熟虑，来权衡我们是否真的要涉足这个新实验室（Neolab）领域。这对我们来说完全是全新的。我们不知道自己需要了解什么。你知道，我们是否会树立起一种“我们想成为 Neolab”的预期，而我们又能否达到这些预期？但我们决定放手一搏。我记得在一个周五晚上，大家说：就这么干吧。我们做到了。我们在周末连续 48 小时训练了该模型，随后在接下来的一周将其发布。最终我们得到了一个名为 KFF 的模型。

<details><summary>Original English</summary>
and so Cloudflare was not wrong here we actually were just early with these small and fast models the network latency became important again we want the model to be responding fast but also the network latency to be even faster and so we decided to do something here but Jev was closed source cloudflare couldn't actually host the Jev models and take advantage of our infrastructure. So what did we decide to do? We built our own version of Jev. So Jev launched on September 15th. Um on September 18th, just three days later, we started experimenting and we launched our version of Jev. Uh our first experiment of it. And then it took us a week of deliberation to decide do we actually want to be going into this Neolab territory. It's completely new to us. We don't know what we need to know it. you know, are we going to set the expectation that we're want to be a Neolab and are we going to live up to those expectations? But we decided to do it. I remember on a Friday evening, we were like, let's just go for it. And we did it. And we ended up training the model over 48 hours over the weekend. And then we launched it the following week. And so we ended up with a model called KFF.
</details>

KFF 把自主决策的能力重新赋予了 Agent。这样一来，Agent 能够更加自主地行动。你不再需要让 LLM 花费数分钟去推导究竟是否应该做出这项决定。你也不再需要引入人类在环（human-in-the-loop），当你想让 Agent 保持全天候 24/7 运转时，也不会被人类的睡眠作息所打断。所以……

<details><summary>Original English</summary>
KFF gave power back to the agents to be able to make decisions on their own. So agents could ask act more autonomously. You didn't need to have a LLM reason through for minutes on if it should make this decision or not. You also didn't need to put a human in the loop and be interrupted by like a human's sleep schedule when you want your agents to be running 24/7. So
</details>

<!-- chunk 6/50 -->

现在你可以在代码中以编程方式做出决策，让你的智能体去执行。

<details><summary>Original English</summary>
you can now programmatically in code decide make decisions for your agent to take action on.
</details>

这些决策模型与大语言模型抗衡，因为它们速度快得多，成本也低得多。作为推理提供方，这也极大地减轻了大语言模型的压力，因为大语言模型被保留用于有意义的工作，而 cleft 和决策模型则可以用于快速、直觉式的思考和工作。

<details><summary>Original English</summary>
So these decision models countered LLM models because they were a lot faster and they were also a lot cheaper as well. And so it actually as an inference provider takes a lot of pressure off the LLMs as well because the LLMs were reserved for work for meaningful work whereas the cleft and uh decision models could be used for fast um intuitive thinking and work right
</details>

于是我们回过头来想，智能体和人们还在把大语言模型用在哪些大材小用的地方？我们想到了决策，而且肯定还有其他工作负载不适合大语言模型，原因要么是成本太高、耗时太长，要么可能仅仅是因为大语言模型的自回归特性会导致幻觉，从而给出错误答案。

<details><summary>Original English</summary>
and so we also went back and thought to ourselves you know what else do agents and people use for LLMs for that are overkill. So we came up with decisions and um there must be other workloads out there that are unsuitable for an LLM both because they are either too expensive or take too long or maybe that it just would get the answer wrong because the auto reggressive nature of an LLM means that it would hallucinate.
</details>

### 新范式：提取模型 Cleric

因此我们在三周后又推出了一个名为 cleric 的模型。实际上我们在三周内一共推出了四个模型。作为一个新实验室，我觉得我们做得相当不错。但 cleric 是一种全新的模型范式。它是完全崭新的。我们称之为提取模型，但在速度同样快、成本同样低这个层面上，它是一个“系统一”模型，而且它也只对输入执行单次前向传播。

<details><summary>Original English</summary>
So we also launched a model 3 weeks later called cleric. We actually ended up launching four models in the span of three weeks. So I think we did pretty good job as a new lab. Um but cleric is a new model paradigm. So it's completely new. We're calling it an extraction model, but it's a system one model in that in the sense that it is just as fast and just as cheap, but it is also doing like one forward pass through the user.
</details>

cleric 的用途在于，当你与现实世界交互时，你交互的对象并不是类型完美的 JSON 对象，对吧？有时你收到一封电子邮件、一条推文、一条 Slack 消息，但那些人并没有为你填好完美的表单以供提取输入。cleric 的作用就是获取非结构化输入，从中提取、计算、估算和预测数值，并向你返回类型完美的 JSON 对象，这意味着智能体能够据此开展工作。所以我们相当于在这里赋予了智能体阅读的能力，并结合 cleft 来采取行动。

<details><summary>Original English</summary>
And the purpose of cleric is when you're interacting with the world, you're not interacting in perfectly typed JSON objects, right? Sometimes you're getting an email, a tweet, a slack message, but those people are not filling out perfect forms for you to extract inputs in out of. So what cleric does is it can take unstructured input and it can extract, compute, estimate and forecast values from those inputs and it gives you back a perfectly typed JSON objects which means the agents are able to do things with it. So we're kind of giving agents the ability to read here and take action with cleft as well.
</details>

所以在代码中，你同样是让 cleric 从非结构化数据中给出类型化数值。你可以传给它任何类型的非结构化数据。它也可以接收图像输入。你可以直接让它读取这里的文本，传给 KFT，决定如何处理这段文本，然后再传给大语言模型来决定如何指示智能体行事。

<details><summary>Original English</summary>
And so in code again you're giving cleric you know typed values from unstructured data. You can pass it in whatever kind of unstructured data. It can also take image input as well. And so you can just tell it to read basically what's in text here, pass it to KFT, decide what to do with this text, and then pass it to an LLM to decide what to do with the agent.
</details>

因此 Cloudflare 在这里必须成为一个新实验室。这是我们缺失的部分。我们拥有基础设施，拥有计算原语，拥有数据原语，也拥有为智能体提供支持的大模型。但为了充分利用所有这些以及我们赖以构建的基础设施，我们必须成为一个新实验室，交付这些与我们基础设施完美契合的系统一模型。

<details><summary>Original English</summary>
And so Cloudflare had to become a neolab here. This was our missing bit. We had the infrastructure. We had the compute primitives. We had the data primitives. We had the large models powering the agents. But in order to take advantage of all of that and our infrastructure that we were built on, we had to be a new lab and ship these system one models that fit perfectly with our infrastructure.
</details>

我认为更重要的一点是，我们并不局限于此。成为一个新实验室意味着我们可以去创造我们所缺失的东西，对吧？这意味着，如果我们因为闭源风险、监管风险等原因缺少某个系统一模型，我们实际上可以去创造和发明。所以，我认为成为一个新实验室确实为 Cloudflare 在 AI 领域开展更多作为打开了许多大门。

<details><summary>Original English</summary>
And I think one of the more important things is that we're not limited to this. Being a new lab means that we can create what we are missing, right? It means that we're not uh if we're missing a system one model because we're um at risk of it things being closed sourced or regulatory risks or things like that, we can actually create and invent things. So I think being a Neolab has actually opened a lot of doors for Cloudflare to do more in the AI world.
</details>

### 工作流实战演示

我们回顾了过去，上一了一点历史课。我也想向前看。我想告诉大家，你们可以用 KF 和 Cleric 做些什么。我也清楚意识到自己是在 AI 工程师代码峰会上。那么在满屋子的开发者和工程师面前，你们如何利用 KFF、cleric 和系统一模型来更好地改进你们的工作流呢？

<details><summary>Original English</summary>
So we went through backwards. We went through a little bit of a history lesson. I want to go forwards as well. I want to teach you guys what you guys can be doing with KF and Cleric. And I'm cognizant that I am at AI engineer code summit. So in a in a room full of developers and engineers, how can you guys leverage KFF and cleric and system one models in order to better use your workflows?
</details>

我们在这里做一个快速演示。设想你有一个正在排查 CI 构建失败问题的智能体，对吧。假设这个智能体有 40 个可用工具，你有出问题的 PR，然后你有你的智能体，也许它是在 Durable Object 上运行 Durable，所有这一切都构建在 Cloudflare 之上。

<details><summary>Original English</summary>
So we'll do a quick demo here. Um it is an let's think you have an agent you're triaging like a CI build that went wrong right um let's say you have 40 tool tools that are available to this agent you have your PR that went wrong um and then you have your agent maybe it's running PI durable on a durable object says all of this is built on Cloudflare
</details>

这就是这里的配置。通常你的做法是：拿一个大语言模型，大语言模型进行一次工具调用，工具调用结果返回给大语言模型，大语言模型再进行另一次工具调用，如此反复，直到问题解决。

<details><summary>Original English</summary>
so this is the setup here tech typically what you would do is you would take an LLM and in the LLM would take a tool make a tool call the tool call would go back to the LLM the LM would make another tool call etc etc until the issue is resolved
</details>

这就好比与 GLM 5.3 进行了五次回合交互。你每次都要发送 40 个工具，可能还会撑爆上下文，对吧？因为你在不断向大语言模型来回发送同样类型的输入。那么，如果我们用系统一模型来增强它呢？

<details><summary>Original English</summary>
So this is like five back and forths with GLM 5.3. You're sending 40 tools every single time and maybe you're blowing up the context, right? Because you're sending the same kind of inputs back and forth to the LLM. And so what if we augment this with system one models
</details>

用系统一模型，情况可能会大不相同。假设我们追求速度，所以我们选择了 cleft flash。Cle 实际上可以帮你剪枝工具列表。也许在 40 个可用工具中它只需要 10 个，所以你只需要挑选其中的 10 个。

<details><summary>Original English</summary>
with system one models? Uh this could look a lot different. And so let's say we were we want speed. So we pick cleft flash. Cle can actually help you prune your tool list. Maybe it only needs 10 out of the 40 tools that are available. So you only need to pick 10 of those.
</details>

接着假设你用 cleric 从输入中提取数值。这样它无需长时间推理和思考就能拿到 PR 编号。然后假设你在这里编排一些代码来执行这些 API 调用，你就可以直接拿到那些返回的答案。

<details><summary>Original English</summary>
Then let's say you take cleric and you use it to extract the values from the input. So it can get the PR number without reasoning and thinking about it too long. Um and then let's say you just you know orchestrate some code here to execute these API calls and uh you can actually just you know get those answers back.
</details>

然后你再次让 cleric 从日志中拉取数据。通常当你使用大语言模型时，你可能会直接粘贴全部日志，对吧，比如整整 300 到 600 行日志。但 Cleric 实际上可以直接去通读这些日志并指出：“具体错误在这里，这是错误消息，这是受影响的代码行。”你基本上大幅缩减了上下文。最后，你再使用大语言模型去采取行动、做出决策并提取数值。同一个智能体可以运行系统一。

<details><summary>Original English</summary>
Then you ask cleric again um to pull the data from the logs. So normally when you're using with working with an LLM you probably just paste in all of the logs right like all 300 600 lines of logs. But Cleric can actually just go through and read those and say, "Here's the exact error. Here's the error message. Here are the lines of code it's affecting." And you're basically shrinking your context a lot. And then finally, you use an LLM to actually do take action and um make decisions and take action and extract values altogether. This same agent can run the system one.
</details>

我们来做个现场演示，看看效果如何。我们要在这里点击“同时运行两者”。这是一个现场演示。我想说的是，Cloudflare 我们的 Workers AI 有着非常明显的昼夜使用规律。我们现在正处于工作日中间，所以我们看看效果如何。但这会给你们展示一个直观的例子，看看它是怎样运行的。而且我们还在用会场的 Wi-Fi，所以请大家多包涵。

<details><summary>Original English</summary>
Let's do a little bit of a live demo. Let's see how it goes. We're going to have to click run both here. And this is a live demo. And uh I will say that Cloudflare our workers AI is uh has a very dal usage pattern. So we're in the middle of the workday. So we'll see how this how this goes. But it'll give you some illustrative example here of how it goes. Uh and we're also dealing with conference Wi-Fi. So so bear with me here.
</details>

好了，系统一模型这边已经完成了，而全用大语言模型的那边还在运行。所以我觉得即使从直观上看，你也能发现系统一模型组要快得多。即使仅看这个简单的瀑布图，你也能看到系统一部分所花的时间比实际生成（即这里的紫色条）要少得多。而且我想它们最终都得出了答案，所以质量没有受到影响，但用时少得多，成本也低得多。

<details><summary>Original English</summary>
All right. The system one model side finished already and the all LLM one is is going. So I think even illustratively you can see that the uh system one set of models is a lot faster. Even by just this simple waterfall chart, you can see that the system one part takes so much less time than the uh actual generation which is the purple bars here. And I think they both ended up getting to the answer at the end. So the quality was not affected, but it took a lot less time. It was a lot cheaper.
</details>

6 次大语言模型调用对 1 次。40,000 个大语言模型 token 对 1,800 个。你可以看到，即使在开发者工作流中，你也可以怎样利用这类系统一和系统二模型，让你更快地获得答案。

<details><summary>Original English</summary>
Six LLM calls versus one. 40,000 LLM tokens versus 1,800. And so you can see how you can use these kind of system one and system two models even in like developer workflows in order to get you to your answer faster.
</details>

答案相同，但只花了由大语言模型处理时的一小部分时间和成本，对吧？我在不用会场 Wi-Fi 时跑过这个测试，当时系统一大约花了 9.2 秒，大语言模型大约花了 17.2 秒。速度几乎快了两倍，成本低了 72%。我们把大语言模型调用次数从五次缩减到一次，token 消耗减少了大约 94%。

<details><summary>Original English</summary>
So the same answer but it took a fraction of the LLM time and cost. Right? I ran this when we were not doing conference Wi-Fi but we had about 9.2 seconds and 17.2 seconds on the LLM. It was almost two times faster. It was 72% less expensive. We shrunk our LLM calls from five down to one and it was about 94% less tokens.
</details>

这就是一个直观的例子，展示了你可以如何协同使用这些系统一和系统二模型。它并不是为了完全取代你对大语言模型的使用，而是可以对其进行增强并使其更好，让你能够为其他更重要的任务腾出时间和算力。并且你现在可以处理更高并发的任务，因为这些模型有能力胜任更多工作。

<details><summary>Original English</summary>
And so this is an illustrative example of how you could be using these system one and system 2 models in tandem. It's not intended to completely replace your LLM usage, but it can augment it and make it better by making allowing you to free up time and compute for your other more important tasks here. And you can h now do you know higher concurrency tasks because these models are able and capable to do so much more.
</details>

这是其中一个直观的例子。我也想在屏幕上快速展示一下，人们还在用 cleft 和 cleric 构建什么，对吧？你可以构建很多路由，并在那里做决策。我们看到很多欺诈场景，比如垃圾信息或网络钓鱼，它可以在那些场景中做决策。对于 Cleric，你可以用它从网页或工单等内容中提取数据。我很高兴看到，我们实际上即将为 Cleric 发布一个新版本。我们发布了早期预览版，但正式版即将推出。随着大家尝试得越来越多，我认为这些用例还会增加。但核心想法是，世界上有太多的东西……

<details><summary>Original English</summary>
And so that was one illustrative example. I just wanted to flash on the screen really quickly as well. What else are people building with cleft and cleric right? There's a lot of um routers that you can build and in making decisions there. Um there's fraud that we've been seeing a lot like spam or fishing. It can make decisions on there. With Cleric, you can use it to extract data from like web pages or support tickets and things like that. So, I'm excited to see uh we actually have a new launch coming out for Cleric. Uh we released an early preview, but it's coming out. So, I think these use cases will grow as uh people are trying it out more and more. But the idea is that there's so much in the world.
</details>

<!-- chunk 7/50 -->

我们不仅限于大语言模型。如今，这些新范式已被引入，我认为我们都应该充分利用这一点，并尝试基于它进行构建。我们经历过倒退，也经历过前进。但我认为这里最重要的是我们要继续向前，对吧？在这个行业中，我们必须具备高度的反应能力。不论喜欢与否，情况瞬息万变。比如早些年作为 Cloudflare，如果发现我们的假设是错的，我们就必须实际调整方向，开始提供这些庞大的大语言模型服务，以利用我们想要成为智能体云（agent cloud）这一事实，而且这符合我们的发展愿景。当一股东风吹来，我们由于与自身基础设施愿景完美契合而需要决策模型时，我们也必须调整方向，成为一家 neolab。因此，坐在那里回顾过去是一回事，但更重要的是我们能够坦然接受既有现实，并向前迈进。

<details><summary>Original English</summary>
We're not limited to just LLMs. Now, these new paradigms have been introduced and I think we should all take advantage of that and try building with it. And so we went backwards, we went forwards. But I think the most important thing here is that we go onwards, right? We have to be very reactive in this industry. Love it or hate it. Things just change on a whim. You know, if we as Cloudflare um back in the day said our hypothesis was wrong, uh we have to go and actually pivot and start serving these giant LLMs in order to take advantage of the fact that we want to be an agent cloud and that it makes sense for our story. when an east wing wind comes and we need to um have decision models because it fit perfectly with our infrastructure story, we had to pivot and be a neolab as well. So it's not it's one thing to sit here and look back but the more important thing is that we took what we had in stride and moved forwards.
</details>

最后，我用一句话来结束：这是一个来自托尔斯泰（tool story）的故事。请记住，最重要的时间只有一个，那就是当下。这是最重要的时间，因为这是我们拥有任何权力的唯一时刻。所以，我留下这句话，以及一个问题：你今天打算构建什么？

<details><summary>Original English</summary>
So I'll leave you with one last quote here which is a story from tool story. Uh remember then there's only one time that is important now. It is most important time because the only time when we have any power and so I'll leave you with this quote and a question of what are you going to build today?
</details>

每天数百个 Pull Request，而且没人能全部读完。那么，代码质量是如何持续提升的？为了分享 Grockbot 团队如何将劣质代码（slop）转化为黄金，有请 SpaceX Super Intelligence 首席工程师 Lauren Tan。

<details><summary>Original English</summary>
Hundreds of pull requests a day and nobody reads them all. So, how does code quality keep improving? To share how the Grockbot team turns slop into gold, please welcome Lauren Tan, principal engineer at SpaceX Super Intelligence.
</details>

大家好。

<details><summary>Original English</summary>
Hello everyone.
</details>

不知道大家能否看到我的幻灯片，不过我叫 Potato，大家也叫我 Lauren，今天非常高兴能与大家交流。也许大家可以为帮助我调试笔记本电脑的技术团队热烈鼓掌。

<details><summary>Original English</summary>
Don't know if you can see my slides, but uh my name is Potato, also known as Lauren, and I'm very excited to chat with all of you today. Maybe you can get a big round of applause for our tech team helping me with my laptop.
</details>

很好。

<details><summary>Original English</summary>
Good.
</details>

我没看到。

<details><summary>Original English</summary>
I don't see it.
</details>

>> 啊，出来了。

<details><summary>Original English</summary>
>> Ah, there you go.
</details>

好的。再次介绍一下，我叫 Potato。我在 SpaceXsi 负责 Grabbot 工作。

<details><summary>Original English</summary>
All right. Um, so again, I'm my name is Potato. Uh, I work on Grabbot at SpaceXsi.
</details>

能请大家举个手吗？你们当中有多少人曾看过别人写的代码，然后心里想“这全是烂代码”？

<details><summary>Original English</summary>
And can I just get a quick show of hands? How many of you have ever looked at code that somebody else wrote and you thought that's all slap?
</details>

其实我也遇到过，但今天我要说服大家，你们完全可以化腐朽为神奇，将这些烂代码变成黄金。

<details><summary>Original English</summary>
Well, I have too, but today I'm going to convince you that you can turn that slop into gold.
</details>

上个月我做了一件很疯狂的事：向生产环境发布了 3,000 个 Pull Request（ploy crust）。在智能体出现之前，除了少数特例，我们从未真正关心过产出数量。

<details><summary>Original English</summary>
Uh, and so I did something crazy last month and I shipped 3,000 ploy crust to production. Now, before agents, we never really cared about volume. Uh, except for the outliers.
</details>

在我上一家公司，我们把这些人称为“编程机器”。比如 Bret Taylor，他因在一个周末重写了整个 Google 地图而闻名，是一位生产力惊人的工程师。而如今有了智能体，任何人都可以成为编程机器。我的核心论点是：软件工程师的工作，或者说作为软件工程师的元逻辑（meta），在于弄清楚如何在大幅提高生产力的同时，维持甚至提升代码质量。

<details><summary>Original English</summary>
And at my previous company, we called these people coding machines. people like Brett Taylor who famously rewrote all of Google Maps uh in the weekend just an insanely productive engineer. Uh and well with agents anyone can now be a coding machine. And my thesis is that the job of a software engineer the meta of being a software engineer is figuring out how to maintain or even improve the quality of your code while massively increasing your productivity.
</details>

### 构建高信任环境与代码库基础

为了实现这一目标，有人喜欢将其称为“软件工厂”。但我喜欢保持简单，我认为它的核心全在于信任。

<details><summary>Original English</summary>
To get there, some people like to call this a software factory. Uh, but I like to keep it simple and I think of it as all about trust.
</details>

不是盲目的信任，而是对智能体运行环境进行投入，以便让你确信智能体能把事情做对。要达到这种状态需要付出很多努力。我花了六个月的时间，才达到能够交付数千个 Pull Request 的水平，其中很多是在我睡觉时完成的。但这是完全可行的，而且你们所花费的时间会比我少得多。那么，让我们首先谈谈如何从低信任环境过渡到高信任环境。

<details><summary>Original English</summary>
Not blind trust, but investing in your agents environment so you can trust that your agents are going to do the right thing. Now, it takes quite a lot of effort to get there. Um, and it took me six months to get to a point where I could ship thousands of pull requests, a lot of them in my sleep, but it's certainly possible and it will take you much less time than I did. So let's start by talking about how we move from a low trust environment to a high trust one.
</details>

这个倒金字塔模型代表了我对于在智能体环境哪些部分投入时间的思考方式。

<details><summary>Original English</summary>
So this inverse pyramid is how I think about where to spend time on your agents environment.
</details>

前两层是确定性的。首先是使用代码本身，例如良好的 API 设计、架构、重构；或者是使用代码检查规则（lint rules）、类型系统、编译器，或是不同类型的测试。你可以将这两层结合起来使用，以约束智能体的行为，并强制它们默认采取正确的做法。

<details><summary>Original English</summary>
The first two layers are deterministic. So using your code itself. So things like good API design, architecture, refactoring or using lint rules, type systems, compilers or you know different kinds of testing. And you can use both of these layers together to constrain what agents can do and force them to do the right thing by default.
</details>

验证工具（包括运行时验证和形式化验证）是非常适合叠加引入的手段，可用于发现漏洞，检查系统中你希望保持成立的属性与不变式，并帮助你检查智能体是否理解了你的目标和意图。

<details><summary>Original English</summary>
Verification, both runtime and formal, are great tools to layer on to find bugs and check properties and the invariance in your system that you want to hold true and also help you check whether or not the agent understood your goals and your intent.
</details>

最后，再叠加上少许文字规则，比如规则文件、技能（skills）、agents.md 等需要主观判断的内容。

<details><summary>Original English</summary>
And then finally, you want to layer with a little bit of pros. So things like rules, skills, agents.mmd, things that require judgment.
</details>

但我们还是从你的代码库谈起。智能体是根据输入生成输出的。因此，输入的质量至关重要。恰好，你的代码库就是最大的输入源之一。所以，每当你在纠正智能体时，请思考如何将其变成一种确定性的检查，而不是在规则或 agents.md 中再追加一行，因为落在代码中时的可复现性要高得多，也能让你对其更加信任。

<details><summary>Original English</summary>
But let's start with your codebase. Agents generate their outputs based on their inputs. And so the the quality of the input really matters. And it just so happens that your codebase is one of the largest inputs. So whenever you're correcting your agent, think about how you can make that a deterministic check instead of adding another line to your rules or your agents.mmd because it's far more reproducible when it's in code and it lets you trust it more.
</details>

我喜欢用的一个比喻是：你的代码库有点像一座花园。过去，代码是一次提交几个 Pull Request。我记得在 2024 年去上班时，只需要审查同事们写的三个 Pull Request，而今天这个数字更接近 300 个。现在每个工程师都相当于一个由数百甚至数千个智能体组成的团队，代码提交如此之快，感觉就像一条源源不断的溪流，甚至带有一种有机感，犹如一个活生生的生命体。

<details><summary>Original English</summary>
And the analogy that I like to use is that your codebase is kind of like a garden. You know, code used to arrive a few pull requests at a time. And uh I remember going into work in 2024 and reviewing the three pull requests that my colleagues wrote colleagues wrote and today that number is more like 300. So uh you know every engineer is now a team of hundreds or even thousands of agents and code is arriving so rapidly that it almost feels like a continuous stream and it almost feels organic like a living thing.
</details>

在这个比喻中，你的代码库、你施加的约束、你建立的安全护栏，就是坚固的混凝土基础，智能体编写的新代码就围绕着它们生长，正如这张图片中的建筑物一样。

<details><summary>Original English</summary>
And in this analogy, your codebase, the constraints that you impose, the guardrails that you put up are the concrete foundations that the new code that your agents write grow around just like uh the building in this picture.
</details>

因此在很多方面，软件工程师的工作正变得类似于园艺。因为代码是智能体最大的输入源，这意味着任何变通方案（workarounds）、反模式、废弃代码或技术债，现在都很可能直接被下一个智能体复制，因为在它们看来这是代码库中既有的模式。这就像花园里长出了一些杂草或害虫，在不知不觉中便已蔓延得到处都是。

<details><summary>Original English</summary>
And so in many ways, the job of being a software engineer is kind of becoming like gardening because code is the biggest input for agents. It means that any workarounds um anti-atterns deprecated code tech is now likely to be just copied by the next agent since it looks like the established pattern in your codebase and uh it's like you have some weeds or pests growing in your garden and then they spread everywhere before you know it.
</details>

所以你需要让代码库尽可能纯净，从而让智能体始终复制好的代码。

<details><summary>Original English</summary>
So you want to make your codebase as pristine as possible so that agents are always copying the good stuff.
</details>

### 实践案例与架构约束

好了，我们来看一些实际的例子。Dune 是我们为 graphbot 创建的一个客户端框架，旨在践行这种有机架构理念。它在技术上其实并没有那么高深，你可以把 Dune 粗略理解为 Electron 应用领域的 Next.js。但 Dune 的亮点在于它具备大量的约束和 lint 规则，其中固化了我们在构建桌面应用程序过程中吸取的许多经验教训。

<details><summary>Original English</summary>
All right, let's look at some real examples. Uh so Dune is a client framework that we created for graphbot to implement this idea for organic architecture. It's not really that interesting technically. Uh you can kind of think of Dune as um kind of like Nex.js for Electron apps. But the interesting part of Dune is that it has a lot of constraints and lit rules that we've encoded uh a lot of the lessons that we've learned building desktop applications.
</details>

其中一个教训是：任何需要精细把控（nuance）才能用好的东西，往往会导致劣质代码。经典例子就是 React 中的 `useEffect`，对吧？它确实有其应用场景，但经常被滥用。有人开玩笑说你需要一个博士学位才能用好 `useEffect`。换句话说，要用好它确实需要极高的把握，而智能体并不擅长使用它。因此我们的解决方案是：直接在业务代码中予以禁用，仅在 Dune 内部 API 的少数地方被允许使用。

<details><summary>Original English</summary>
And one such lesson is that anything that requires nuance to use well often leads to slop. Uh you know your classic example is uh you know use effect in React, right? It has its use cases uh but it's often misused. You know some people joke that you need a PhD to use use effect. Um and in in other words, it really requires a lot of nuance to use ball and agents are not good at using it. Um so our solution has been to just ban it in product code and it's really only allowed in some places inside of Dune APIs
</details>

这样一来，这个问题在本质上就被彻底消除了，我们在代码审查时再也不需要去抓取此类问题。

<details><summary>Original English</summary>
and effectively this problem has now been categorically eliminated and we never need to catch that during code review again.
</details>

我们使用的另一个有趣模式是通过目录结构传递上下文。我们在 Cursor（一款 Electron 应用）中观察到的一个反模式是：智能体经常会将主线程代码引入到渲染线程中，从而导致长任务和界面卡顿。

<details><summary>Original English</summary>
Another interesting pattern that we use is context through directory structure. Uh so one antiattern that we saw with cursor which is an electron app is that agents would often import main thread code into the renderer thread which would cause long tasks and jank.
</details>

因此在 grapot 和 Dune 中，我们将其规范得非常明确。我们设立了两个顶层目录，直接命名为 `electron renderer` 和 `electron main`，而它们之间的相互引用被我们的依赖图分析器和一些 lint 规则严格禁止。同样，设置这些 lint 规则很简单，但它意味着我们在代码审查期间又少了一件需要审查和操心的事情。

<details><summary>Original English</summary>
So in uh grapot and in dunes we've made this very very conventional. Uh we have these two top level directories literally called electron renderer and electron main and imports between them are forbidden or banned by our dependency graph analyzer and some lint rules. And again you know these are simple lint rules to set up but it means one less thing that we need to review and think about uh you know during code review.
</details>

我还观察到了另一件更令人吃惊的事情：智能体使用 Markdown。例如文档、代码注释、规则或技能，它们会利用这些地方写下自己不采取正确做法的辩解。或者（不知大家是否见过）它们会对你提出的某项微小指正产生过度反应，将其视作永远不能打破的硬性规则。

<details><summary>Original English</summary>
And then one more surprising thing that I've seen is agents using markdown. So things like documentation, uh, code comments, rules or skills, and they use this as a place to write down their justifications for not doing the right thing. Or, I don't know if you've ever seen this, but they'll over rotate on some small correction that you made, and they treat it like a hard rule that can never be broken ever again.
</details>

这里还有一个来自 Cursor 的例子。智能体非常热衷于使用命令式定时器，例如 `setTimeout`、`requestAnimationFrame`、`requestIdleCallback`。它们[中断]

<details><summary>Original English</summary>
And here's another example from cursor. So agents really loved using imperative timers. So things like set timeout, request animation frame, request idle call back. And they
</details>

<!-- chunk 8/50 -->

### 架构冲突与注释问题

我们当时把这些当作权宜之计，因为它们实际上是在掩盖 VS Code 的命令式风格与 React 的声明式风格之间的架构冲突。

<details>
<summary>Original English</summary>
 were using these as quick fixes because they were really patching over an architecture clash between uh VS Code's imperative style and React's declarative style.
</details>

所以我们的架构选择实际上让客户端和 agent 的性能都变得糟糕得多。如果你曾经做过任何 JavaScript 性能优化工作，你就会知道，当大量定时器被快速创建和销毁时，会引发大量的重大垃圾回收，从而导致大量的卡顿和掉帧。但最糟糕的部分是，agent 写了大量代码注释（就像你在这里红色部分看到的那样），解释为什么这种权宜之计是合理的；不知不觉中，定时器蔓延到了各处，应用的性能确实受到了严重影响。

<details>
<summary>Original English</summary>
So our choice of architecture actually made both the client and the agent performance much worse. And if you've ever done any performance work in JavaScript, you'll know that when you have tons of timers being rapidly created and destroyed causes a lot of uh major garbage collection, which causes a lot of lag and jen. Uh but the worst part is that agents wrote a lot of code comments like you can see in red here explaining why this quick fix was justified and before you know it, we had timers spreading everywhere and the you know the performance of the app really suffered.
</details>

### 用确定性检查取代注释

现在在 Grockbot 中，我们吸取了教训，决定直接禁止 99% 的注释，因为它们很容易过时。人类反正是真的懒得去读那些注释废话的。而且再说一次，这给了 agent 一个逃避借口，去辩解因为事情困难所以不去做正确的事。不过注释最糟糕的地方在于它们是无法强制执行的。因此，那些看似出于好意的做法——比如“我要告诉下一个 agent 不要去做某件事”——最终从来不是你可以信赖的东西。所以在 Grockbot 和 Dune 中，我们现在有了 lint 规则，提供良好且非常有帮助的错误提示，告诉 agent 去修复根本原因、真正的根源问题，而不是仅仅做一些修修补补。

<details>
<summary>Original English</summary>
Now in Grockbot uh we learned our lesson there and we decided to just ban 99% of comments uh because they go stale easily. Uh you know humans just really don't bother reading the comment slop anyway. And again it gives an agent the an escape hatch to justify not doing the right thing because it's hard. Um and the worst part about comments though is that they're not enforcable. So what seems well-intentioned, you know, like I'm going to tell the the next agent not to do something, never ends up actually being anything that you can trust. So in Grockbot and Dune and in Dune, uh we now have lint rules that give uh good and very helpful error messages telling the agent to fix the root cause, the real problem, uh rather than just patch around it.
</details>

因此我们的一般原则是：每次我们纠正我们的 agent 时，要么将其转化为这些确定性检查之一，要么思考如何通过更好的 API 设计、更好的架构在代码中彻底消除该问题。如果你这样做的次数足够多，你就会发现代码审查中需要注意的事情变少了。到某个时候，你会意识到已经没有什么需要审查的了，你完全可以让 agent 自行合并它们的大部分拉取请求。

<details>
<summary>Original English</summary>
And so our general principle is that every time we correct our agents, it turns into one of these deterministic checks or we think about how to categorically eliminate that problem in the code through better API design, through better uh architecture. And if you do this enough times, you'll find that you have just less things to look out for in code review. And at some point, you'll realize there's there's nothing left to review, and you can just let agents merge their most of their own pull requests.
</details>

### 验证体系与代码审查演进

好了，继续往下讲。验证也是我们让 agent 更加自主、同时增加对其工作信心和信任的非常重要的组成部分。我们的代码审查流程现在实际上已经缩减为查看验证产物。比如视频、截图、图表、形式化验证等内容。

<details>
<summary>Original English</summary>
All right. Uh, moving on. Verification is also a really big part of how we make our agents more autonomous and also increase our confidence and trust in their work. And our code review process has now really shrunk into looking at verification artifacts instead. So things like videos, screenshots, diagrams, formal verification.
</details>

这方面最基本的例子是运行时验证。这只是一种更高级的说法，意思就是让你的 agent 能够自己运行代码，并使用人类开发者也会使用的调试工具，比如 Chrome DevTools 协议。在我们运行时验证的技能中，有这样一个我们称为 feature map 的东西，基本上有点像从用户视角出发的、包含应用中所有可用功能的功能地图。有了它，当你提到“左侧边栏里的那个小东西”时，agent 就不需要去猜了。它为你提供了一些共通的词汇，而且我们还在这些技能中利用了自定义 CLI，让 agent 每次都能复用该 CLI 和驱动程序，这既减少了 token 消耗，又是可测试的。

<details>
<summary>Original English</summary>
Um, and the most basic example of this is runtime verification. uh which is just a fancy way of saying giving your agent a way to run the code for itself and use debugging tools that you know human developers use as well like the Chrome DevTools protocol. Um in our runtime verification skills we have this thing that we call a feature map and that's basically kind of like a site map of all of the features that are available in your application from the user's point of view. And so with this agents don't need to guess when you say you know the thingy in the left sidebar. It gives you some shared vocabulary and we also make use of custom CLIs inside these skills so that uh agents can reuse the the CLI and the driver every time which cuts down on token usage and is also testable.
</details>

### 形式化验证与基于属性的测试

最近我们也开始研究形式化验证。所以我们现在使用 TLA+ 对主要的用户流程进行一些模型检验，例如跨多个设备和平台的通知。我们也使用 Lean 来证明某些算法。例如，我们编写了我们自己的自定义虚拟化库，我们就在那里使用 Lean 来检验我们不会出现闪烁或抖动问题。我们仍在对这种方法进行实验。总体来看它非常有前景。借助形式化验证，我们已经发现了相当多的 bug。但这当然不是灵丹妙药，我们把它当作另一个工具，当作我们 agent 环境中的另一层。

<details>
<summary>Original English</summary>
Um and then recently we've also started looking at formal verification. Uh so we now use TA plus to do some model checking of major user flows such as uh notifications across multiple devices and platforms. Uh we use a lean as well for proving certain algorithms. Uh for example, we have our own we wrote our own custom virtualization library and we use lean there to check that we don't have you know flickering or jittering problems. Um and we're still experimenting with this approach. Overall it seems very promising. Uh we've already found quite a few bugs uh with formal verification. uh but it's certainly not a silver bullet and we're treating it as another tool, another layer in our agents uh environment.
</details>

这个视频播放得非常快，不过我们刚开始探索的另一项技术是针对 UI 的基于属性的测试。我们使用了这个名为 Bombadil 的库。这已经为我们捕获了几个 UI bug。

<details>
<summary>Original English</summary>
Uh and then this is a very fast video but uh another thing that we just started looking at is property based testing as well for UIs. Uh so we use this library called Bombadil. Um and this has also caught a few UI bugs for us already.
</details>

### 验证的经济效益与工具支持

退一步来看，我看到了 Cindy 发的这条推文。六个月前，她说……或者说她在谈论因为合入了一些隐蔽的 bug 而无法信任她的 agent。

<details>
<summary>Original English</summary>
Okay, so zooming out, I saw this tweet from Cindy and six months ago she she said that she was or she was talking about not being able to trust her agents because of subtle bugs that were getting merged.
</details>

让她无法信任自己的 agent 所缺失的关键，实际上正是验证流程。而现在 6 个月后，她说她每天 70% 的 token 都花在了验证上。我认为这与我所观察到的情况也是吻合的，我大部分的 token 消耗也用于验证。

<details>
<summary>Original English</summary>
And really what was missing for her in being able to trust her agents was the verification process. And now 6 months later, she says that 70% of her daily tokens go into verification. And I'd say that that tracks with what I see as well, that most of my token usage goes to verification.
</details>

如果你仔细观察我们的流程，这里的技术没有一项是我们以前从未有过的新方法或新奇技术。

<details>
<summary>Original English</summary>
And if you really look closely at our process, none of these things here are new or novel techniques that we've never had before.
</details>

这些都只是优秀的软件工程工具，但以前可能因为难以理解、编写或维护，使用成本高得令人望而却步。但 agent 大幅削减了这笔成本。实际上，我们正在进入软件测试和验证的黄金时代，因为 agent 让我们能够以远超过去经济可行水平的深度去测试一切。

<details>
<summary>Original English</summary>
These are just good software engineering tools, but ones that might have been prohibitively expensive to use before as they were hard to understand or write or maintain. But agents drastically cut this cost down. And really, we're entering a golden age of software testing and verification because agents let us test everything to a much greater degree than used to be economical.
</details>

形式化验证还可以帮助你更好地推敲你的产品应该如何运作，以及你的 agent 是否真正理解了你的意图和目标。我在我的插件 PAC potato stack 中制作了这个名为 state chart 的新技能，它可以帮助你从用户的视角可视化状态机。我发现配合我们提供的视频和截图一起查看，这个更容易进行审查。所以这效果很棒。抱歉闪到了大家。好的，现在让我们看看应许之地是什么样子的。付出这一切投入，你换来了什么回报？

<details>
<summary>Original English</summary>
And then formal verification can also help you better reason about how your product should work and whether your agents really understand your intent and goals. Uh I made this new skill called state chart uh in my plug-in PAC potato stack uh which helps you visualize state machines from uh from the user's point of view. Uh, and it's I find this much easier to review alongside the videos and screenshots that we provide. Um, and so that's been great. Sorry for the flashbang. Uh, okay. Now, let's look at what the promised land looks like. What do you get in return for all of this uh, you know, investment?
</details>

### 研发效能与质量指标

在 Graphbot 团队，我们的研发速度正在起飞并迅速增长。上个月，我们团队向生产环境交付了惊人的 11,000 个拉取请求，这是一个极其惊人的数字。而且我们发布客户端的节奏也加快了，大约每天发布一次新的稳定版本。

<details>
<summary>Original English</summary>
So, on the graphbot team, our velocity is uh, taking off and rapidly increasing. And last month, our team shipped a ridiculous 11,000 pull requests to production, which is a wild number. And our pace of releasing the client has also increased. And we cut a new stable version about once a day.
</details>

核心团队的交付量大大增加。我们也有了更多偶然参与或顺手提交的贡献者，他们并不总是有很多上下文背景，但他们也在做出贡献。在 10 月份，我们大约有 227 人贡献了至少一个拉取请求。

<details>
<summary>Original English</summary>
And then the core team is also shipping much more. And we also have uh a lot more casual or driveby contributors who don't always have a lot of context uh but they're also contributing. Um, and in October we had about 227 people who contributed at least one pull request.
</details>

尽管这种研发速度在加快，你可能会心想：这难道不会变成一片混乱吗？这难道不会产生一堆粗制滥造的垃圾吗？但实际上，被回滚的 PR 数量相对而言其实变少了，并且稳定在大约 0.5% 左右。

<details>
<summary>Original English</summary>
So despite this velocity accelerating, you might be thinking to yourself like, isn't this going to be chaos? You know, isn't this going to be a bunch of slop? But actually, the number of uh PRs that get reverted has actually gotten lower on a relative basis and is steady at about half a percent.
</details>

但我认为关于这种交付节奏和拉取请求数量，真正有趣的事情在于，Grathbot 的性能不仅保持稳定，而且与我们发布时相比，在多个维度上都有所提升。启动、输入、打开新对话、切换对话，所有这些都变得更快了；要记住，目前 Grathbot 仍然是一个 Electron 应用。所以它是有上限的，对吧？但它已经比市面上许多其他的 agent UI 快得多了。对于一个具有如此高的研发速度、有这么多人贡献的 Electron 应用来说，我认为这已经相当不错了。

<details>
<summary>Original English</summary>
But I think the really interesting thing about this shipping pace and this volume of pull requests is that the performance of Grathbot has stayed not just stable but has improved on multiple dimensions compared to when we launched. So startup typing, opening new chats, switching chats, all of this has gotten faster and keep in mind Grathbot is still an Electron app for now. Uh so there is a ceiling, right? But it's already much faster than many other agent UIs out there. And for an Electron app with this high velocity and this many people contributing, I'd say that's pretty good.
</details>

### 构建软件工厂的底层基础

因此，在急于构建软件工厂并尽可能将一切自动化之前，每当纠正你的 agent 时，尽量先通过改进你的代码库来解决。比如从一条用于防止反模式再次出现的 lint 规则开始，然后清理掉那些旧的模式，接着确保你的验证机制真正过硬。

<details>
<summary>Original English</summary>
So before you jump into building out a software factory and you know automating everything that you can, whenever you correct your agent, try and do it by improving your codebase first. you know, start with a lint rule to prevent new occurrences of anti-atterns and then clean up those uh old patterns as well and then make sure that your verification story is really strong.
</details>

无论如何，很多这类工作都是实现自动化的前提条件。如果你的内部编码循环产出的是粗劣废品，那么把这个循环自动化只会产生更多的粗劣废品，你就需要向这个问题砸入越来越多的 token，而大家都知道这非常昂贵。

<details>
<summary>Original English</summary>
A lot of this work is a prerequisite to automation anyway. And if your inner coding loop uh produces slop, then automating that loop just produces more slop and you need to throw more and more and more tokens at the problem, which we all know is very expensive.
</details>

一旦你对代码、代码库、静态分析以及运行时非形式化验证做出了这些投入，你就会开始发现，有了这些基础，许多事情变得可行，而且你完全可以在这些基础之上轻松构建自己的工厂。

<details>
<summary>Original English</summary>
And once you've made these investments into, you know, code into your codebase, static analysis, runtime informal verification, you'll start to find that many things become possible with these foundations and that you can really easily build your own factory on top of these foundations.
</details>

当你准备就绪时，Grabbot 是构建那个外层循环的绝佳途径。我们拥有大量的连接器和例程，可以启动 Cursor 云端 agent 和项目，让你能够编排成百上千甚至数以千计的 agent。作为一个简短的……

<details>
<summary>Original English</summary>
And when you're ready, Grabbot is a great way to build that uh outer loop. We have tons of connectors, routines that can kick off cursor cloud agents and projects uh which let you orchestrate thousands of hundreds or even thousands of agents. And as a quick
</details>

<!-- chunk 9/50 -->

例如，你知道的，现在每当我们发布一个新版本，Grockbot 就会自动为我们启动一个新的 Cursor 项目，对整个应用程序、整个构建版本进行模糊测试（fuzz），它会通过运行该应用并像真实用户一样使用它来发现 bug。然后，针对它发现的每一个 bug，它会开启修复 PR，并且——尽管这听起来很疯狂——它会自动合并这些 PR。而之所以能这样，是因为我们的代码库已经足够优秀，Pull Request 往往默认就是良好的。我们合入的大多数产品代码，实际上不再需要深度的人工审查。

<details><summary>Original English</summary>
example, you know, whenever we cut a new release now, Grockbot will automatically spin up a new cursor project for us that will fuzz the entire application, the entire build, and it will find bugs uh by running the app and using it like a real user. And then it's going to open fixed PRs for each of those bugs that it finds and it's going to automerge it as uh crazy as that sounds. And that's because our code base is good enough that pull requests tend to just be good by default. And most product code that we land no longer really requires deep human review.
</details>

所以，当你拥有坚实的基础和良好的有机架构时，你就能化粗制滥造为神奇（turn slop into gold），并且可以在不牺牲质量的前提下实现高质量、高速度的交付。我叫 Potato，也被称为 Lauren。再次感谢大家聆听我的演讲。

<details><summary>Original English</summary>
So when you have solid foundations and good organic architecture, you can turn slop into gold and you can ship with high quality uh high velocity without compromising on quality. My name is Potato, also known as Lauren. Thanks you again for listening to my talk.
</details>

### 上午主题演讲结束与致谢赞助商

今天上午的主题演讲就到此结束。感谢大家在面对各种技术挑战时的耐心等待。根本原因当然是 GitHub 故障。呃，其实不是。但事实是，没有人会想到去质疑这一点，这确实说明了些什么。我能这么说是因为他们不是赞助商。但你知道谁是吗？没错。冠名赞助商 Google DeepMind。请大家再次为他们鼓掌。没有他们，这一切就办不成。

<details><summary>Original English</summary>
That concludes this morning's uh keynote sessions. Thank you for your patience with the various technical challenges. The root cause was of course a GitHub outage. Uh, not really. But the fact that no one would think to question that does say something. I can say that because they're not sponsors. But you know who is? That's right. Presenting sponsor, Google DeepMind. Another round of applause for them, please. Without them, this would not be doable.
</details>

当然，还有我们的休息区（lounge）赞助商和白金赞助商。正是他们打造了那边的休息区和白金展区。难得一次，我不被允许说关于 AWS 的风凉话。所以，我们要微笑着点头，继续往下走。我们的黄金赞助商同样对各种事务给予了不可思议的支持。虽然不支持我的胡言乱语，但你知道的，他们支持了其余大部分精彩的内容。绝对是的。让我们也为我们的白银赞助商喝彩。

<details><summary>Original English</summary>
Of course, our lounge and platinum sponsors as well. Make the lounges and platinum things there. I am not allowed to say snarky things about AWS for once. So, we're going to smile, nod, and keep it rolling. Our gold sponsors as well have been incredibly supportive of various things. Not my nonsense, but you know, most of the rest of the good stuff. Absolutely. And let's give it up for our silver sponsors, too.
</details>

谢谢大家。

<details><summary>Original English</summary>
Thank you.
</details>

最后，还有我们所有的支持合作伙伴。还有呃，当然，引用我童年看 PBS 时常说的一句话，还有“像你们一样的观众”。嗯，我年纪大了，回到当年我们还在用电报看电视的年代。呃，现在有一些分论坛（breakout sessions）。其中我最喜欢的一点是，如果你擦掉字母 B 的一部分，它读起来就是“抓狂论坛（freakout sessions）”。你想怎么理解就怎么理解吧。今天晚些时候 4:30 开始还有另一组闭幕主题演讲。届时我会在这里与大家再次相见，如果主办方没有最后在后门垃圾箱旁拿着碎啤酒瓶找我“谈话”的话。感谢大家的到来。

<details><summary>Original English</summary>
And finally, all of our supporting partners as well. There are uh and of course, viewers like you, to quote PBS from my childhood. Um, I'm old back when we used to watch it on the Telegraph. Uh, there are now some breakout sessions. My favorite part of those, if you erase part of the letter B, it reads freakout sessions. You can read into that what you'd like. There are another series of closing keynotes later today starting at 4:30. And I'll see you all back here then if they don't wind up having a conversation from me out back next to the dumpsters with some broken beer bottles. Thank you all for coming.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

### 利用 KV Cache 构建 Agent 安全信号

大家好，我是 Pinter AI 的创始人 Ari Zerus。嗯，这场演讲是面向那些构建智能体并运行自己的推理技术栈，或计划这样做的人。如果你是其中之一，你通常会把 KV cache——现代推理引擎的立身之本——通常仅仅看作一种吞吐量优化手段：每个 token 计算出的键（keys）和值（values）会被保留下来，这样模型就不必再次计算它们。今天我想从一个不同的视角来展示 KV cache。

<details><summary>Original English</summary>
Hi, I'm Ari Zerus, founder of Pinter AI. Um this talk is for people who build agents and run their own inference stack or plan to and if that's you you associate typically the KB cache the bread and butter of modern inference engines usually as a throughput optimization the keys and values computed per token kept so the model doesn't compute them again today I'll like to show KV cache in a different light
</details>

AI 智能体应用可能出错或持续滋生问题的方式，对吧，提示词注入、越狱、破损的工具调用、敏感工具调用、敏感数据暴露、隐藏后门以及漂移等等，对吧？所以，目前针对这些 AI 智能体应用可能出错的诸多方式，我们通常的防御做法是在边缘进行防护，比如通过引入一个裁判模型（judge model），根据你的策略去检查提示词输入和响应输出。对吧？或者你针对每种情况分别构建一个分类器。但这里提供了一个不同的视角：模型在行动之前、在解码之前、在生成响应之前、在响应变成另一次工具调用之前，都会把每一个输入转化为一次计算。KV cache 就是你的引擎对该计算的记录，现代推理引擎免费对其进行着使用和读取。因此，在这场演讲中，我想建议：作为对你现已采用的自身护栏（guardrails）方式的补充，去使用这些数据并与 KV cache 基础设施相集成。我将此称为“KV-first 安全信号”，这主要有三个重要原因，对吧。

<details><summary>Original English</summary>
the way agents agent AI agent application could go wrong or keep growing right prom injection jails broken tool calls, sensitive tool calls, sensitive exposures, hidden back doors and drifts and so forth, right? So the way right now we typically guard against against these numerous ways that an AI agent application could go wrong is by guarding the edge by perhaps passing a judge model that checks the prompts, the inputs and the response outputs against your policy. All right? Or you build a classifier for each case. But here is a different light. The model turns every input into a computation before it acts before it decodes before it generates the response before that response becomes another tool call the KV cache is your engine's record of that computation that modern inference engine for free are using it and reading it and therefore in this talk I would like to suggest as as a complement to the way you're already using your own guardrails to use this data and integrated with KV cache infrastructure. I refer to this as a KB first security signals and basically three reasons that matters right.
</details>

第一，数据已经存在于那里。你可以从你的推理技术栈原本就已经扔掉的废料堆里拾取明珠。第二，它覆盖了护栏的盲区，因为任何溜过那些护栏的东西，仍然会转化为计算并留存到位。第三，它非常适合数据隐私应用，适用于那些你无法奢侈地读取输入和输出内容的场景。而且它的实现配方非常直接明确，对吧，包含三个步骤：你针对你的 AI 工作负载、针对你的 AI 推理流量学习出一个基线（baseline），了解你的 KV 页面通常是什么样子；然后找出那些相比于你的基线而言罕见的 KV 页面，这些通常就是你的异常；接着你甚至可以对这些异常进行分类和解释。那么首先，让我们先来看看在这个技术栈上的什么位置可以进行这种集成。

<details><summary>Original English</summary>
So the data is already there. You pick the gems from the pile your inference stack already was throwing away. It covers the guardrails blind spots because whatever slips past those guardrails it still becomes computation and it stays in place. So it's perfect for data privacy application for cases where you do not have the luxury to read the inputs and outputs. And the recipe is pretty straightforward right has three steps. You learn a baseline for your AI workload for your AI inference traffic how your KV page typically look like and then find the KV pages that are rare against your baseline typically your anomalies and then you can even classify and explain those. So first let's start with where on this stack this integration could happen.
</details>

关于 KV cache 很有趣的一点是，在某种程度上，它们的存在使得推理在某种意义上变成了有状态的（stateful）。对吧？举例来说，像 LM-Cache 这样的 KV cache 管理层会将它们从 GPU 存储转存到远端存储；或者像 LLM-D 和 Nvidia Dynamo 这样的路由层，会将每个新请求路由到可能已经持有该缓存 KV 页面的 worker 上。所以这里有两个集成点：你可以将这些异常检测或分类器集成到——要么你直接在推理引擎内部实现，比如 vLLM 等等。这种方式的妙处在于它是实时的，而且它可能生成的告警可以伴随你的后续工具调用或后续策略一起运行。所以你基本上可以通过仅仅生成你在推理引擎内部观察到的计算异常，来加固你的策略算法。或者，你也许可以将其作为一种威胁发现的方式进行集成，在某种意义上，你可以与你的 LM-Cache 进行集成，让它读取存储的 KV 页面，并找出那些不属于其余常规内容的东西，对吧。

<details><summary>Original English</summary>
The interesting thing about the KB cache is that in a way existence of those had made the inference in a way stateful. Right? So for example, things like KBK cache management layers such as LM cache stores them from GPU down to a remote storage or LLMD and Nvidia dynamo route each new request towards the worker that already holds perhaps that cached KV page. So there are two integration points you you you can integrate those anomaly detection or those classifiers into either you can implement it directly inside of your inference engine vg line and so forth. The beauty of this approach is that it's real time and and the the the alert that it would perhaps generate could ride along your future tool calls or your future policies. So you can harden basically your polic algorith but just generating the computational anomalies that you observe within your inference engines and perhaps you can integrate it with as a as a way of thread discovery in a sense so you can integrate with your LM cache so it reads the stored KB pages and find things that don't belong with the rest right
</details>

现在我想给大家看一些数据，以及一个非常简单的 Hello World 用例，看看这是否真正有效、是否是一种可行的方法。为此，让我以一个完全没有文本可供过滤的用例开始——一个语音智能体（voice agent）。这里是一个语音智能体的案例研究。在这个案例中，使用的是 Gemma 4 E4B。我们的基线是 72 个普通音频片段，由四种声音讲出。我们观察的是 16 token 的页面。显然，这个粒度是可以改变的，但在这里我们只是使用较短的页面，以便在基线中拥有更多的数据。然后，在测试集上我们有不同的声音，其中一个是纯净的声音，另一个则包含隐藏在其中的指令。正如这里所展示的，你不仅可以使用简单的异常检测来发现这些情况，而且你还能知道具体是哪一部分——哪一个页面、你的请求中的哪一部分出现了这个异常事件。我们甚至更进一步，训练了一个将 KV 页面作为特征的模型，我们并没有尝试去解释它或用有用的东西对其打标签。在这种情况下，尽管该模型甚至没有在音频上进行过训练，但它能够生成关于个人信息、家庭住址、位置数据、出行信息和目的地的正确信息。

<details><summary>Original English</summary>
so now I want to show you some numbers and and just a very simple hello world use case if this is actually working and this is a valid approach and for that let me use with a use case that has no text to filter at all a voice agent. So here's a case study of a voice agent. In this case it was a gem for E4B. Our baseline was 72 ordinary clips and spoken four voices. We're looking at 16 token pages. Obviously this granular granularity could change but here we just use shorter pages so we could have more data in the baseline. And then on the test we have different voices and one clean voice and the other one has a hidden instruction within it. And as you can as is shown here not only you can detect these cases just using simple anomaly detection but also you would know which part of um which page which part of your request had this anomalous event. We even went further and we trained a model that uses the KV pages as features and we didn't try to explain it or tag it with things that are useful. In this case, although it wasn't even trained on audio is able to generate correct information about personal information, home address, location data, travel information, and destination.
</details>

现在回到文本智能体。在这个案例中，使用的是一个带有实时 unveil cache 的 Qwen 3 14B 模型。左边的图向你展示了攻击流量与正常流量通常会如何彼此分离。而右边的图可能更有意义，它使用的是来自 Hugging Face 的 AgentBench。它有其自己的良性智能体轨迹基线，以及从注入的工具描述到虚假信息等八种智能体故障类型。我们观察了异常检测生成的 Top 10 告警，这些告警中大约有十分之七到八实际上是具有实际意义且有用的异常活动。我们甚至更进一步，观察了是否存在任何比其余异常更为突出的异常事件。

<details><summary>Original English</summary>
So now back to text agents. In this case, it was a quan 3 14 billion ser live unveil cache. The one on the left shows you an idea of how attacks and normal traffic would typically separate from each other. And then the one on the right, which is perhaps more meaningful, it was using the at bench and hogging face. It has its own baseline of benign agent traces and eight kind of agent failure from injected tools description to misinformation and so forth. We look at the top 10 alerts that anomalous anomaly detection would generate and about seven to eight times of out of 10 of these alerts are actually anomalous meaningful and useful anomalous activities. We even went further and we looked at whether there's any kind of anomalous events that stand out more than the rest.
</details>

嗯，有两点让生产环境中的落地变得困难。第一，模型会发生变化。微调和新版本的发布，不仅如此，还包括每个运行在不同模型上的智能体，以及针对每个请求挑选专用模型的路由机制。这意味着每个模型都会以自己的坐标系来写入它的页面。因此，要么你去学习每一个基线、分类器和解释器——这在计算成本上是不可行的；要么你必须找到一种方法，将它们全部映射到一个共享的表示空间中。

第二，实时性意味着需要传输大对象。例如，Qwen 3 14B 的一个 1256 token 的分块，其 KV 压缩大约是 40 MB，像 HashGen 这样的流式传输可能会有所帮助，但传输这个……

<details><summary>Original English</summary>
Um, two make things hard in production. First, models change. fine tunes and new releases, but also agents that each run on a different model and routers that pick a specialist model per request. That means each model writes its pages its own coordinates. So either you learn every baseline, classifier, and explainer, which is computationally prohibitive, or you have to find a way to map them all into one shared representation space. Second, real time means moving big objects. For example, a 1256 token chunk of quen 314 billion is about 40 megabytes of KV compression and streaming like hashgen could help but moving that for
</details>

<!-- chunk 10/50 -->

安全分析与实时响应目前仍然很慢，这正是我们在 AI 领域所要解决的问题。我们正在寻找那些在构建自己的推理技术栈时，将安全视为基础设计决策的团队。希望这些内容对大家有所帮助。非常感谢大家的聆听。

<details>
<summary>Original English</summary>
security analysis and acting in real times is still a slow and that's what we solve at in AI. We are looking for teams building their own inference stacks who treat security as a foundational design decision. I hope this was helpful for you. Thank you so much for listening.
</details>

>> 让我先从上个月的一个数据说起。平均每分钟，无论白天还是黑夜，我们的平台上都会启动不止一个 agent。

<details>
<summary>Original English</summary>
>> Let me start with one number from last month. On average, more than one agent has started on our platform every single minute, day and night.
</details>

老实说，agent 本身还是简单的部分。

<details>
<summary>Original English</summary>
And honestly, the agents were the easy part.
</details>

大家好，我是 Joey。我负责构建我们在 Harvey 内部搭建的云端 agent 平台。

<details>
<summary>Original English</summary>
Hi, I'm Joey. I bu the cloud agent platform we built inside Harvey.
</details>

在经历了 10,000 个 PR 之后，我能分享的最大教训就是：出问题的不是 agent，而是它们周围的一切。

<details>
<summary>Original English</summary>
After 10,000 PRs, the biggest lesson I can share is this. The thing that broke was an agent. It was everything around them.
</details>

那么，每一次提交累积起来意味着什么？那就是 agent 编写的 10,000 个 PR。这不仅仅是技术团队在玩玩具。

<details>
<summary>Original English</summary>
So what does one submit add up to? 10,000 PRs that an agent wrote. And it isn't just Tax team playing with a toy.
</details>

上个月，Harvey 大约有 460 位不同的人在使用它。到了夏天，它已经不再仅仅局限于代码。人们开始在 Slack 里提数据问题，并收到回复。我最近最喜欢的一个例子是，我们市场团队的某位同事在 Slack 里发了一个原型和一个演讲要点，请求为产品视频制作一个 storybook。一旦基础设施建立起来，人们就会带来你从未计划过的工作。

<details>
<summary>Original English</summary>
Last month about 460 different people at Harvey use it. And over the summer it stopped being only about code. People started asking a data question in Slack and getting answers back. My favorite recently someone on our marketing team drop a prototype and a talk track into Slack and ask for a story book for a product video. Once the harness exists, people bring the work that you never plan for.
</details>

所以先在此说明：这不是一场关于模型、评测或排行榜的演讲。这是一场关于执行框架、关于模型周围零散事务的演讲——拉取代码仓库、持有密钥、提交 PR，以及促成代码合并。

<details>
<summary>Original English</summary>
So a promise up front. This is not a talk about models, Evos or leaderboard. This is talk about hardness, odd things around the model, checking out the ripple, holding the key, opening the PR, getting the merged.
</details>

当我们早在四月份第一次撰文介绍 Spectre 时，我们是这样描述的：在某个节点上，执行框架本身就变成了产品。

<details>
<summary>Original English</summary>
When we first wrote about Spectre back in April, we put it like this. At some point, a harness become the product.
</details>

现在，每当我向人们说起这个，都会收到同样的问题：既然已经有了 Claude 或 Cursor，你们究竟为什么还要做这个？

<details>
<summary>Original English</summary>
Now, whenever I tell people this, I get the same question. Why on earth would you build this when clock or cursor already exist?
</details>

我的回答是：我们不与它们竞争，我们运行它们。我个人的看法是这样的：笔记本电脑上的 agent 很强大，但它们无法扩展。实际上你只能运行 5 到 10 个。超过这个数量，你就需要云端。而云端需要我们的密钥、我们真实的系统技术栈、我们的告警和工单、一套统一的规则，以及足够的容量以确保没人被饿死。没有任何单一工具能为我们包揽这一切。所以我们构建了这一层，而恰恰正是那一层出了问题。因此，我今天想讲三个故事：我们如何不再在编写代码上竞争、我们如何让任何 agent 都能驱动，以及一旦它们运作起来，哪里被搞垮了。

<details>
<summary>Original English</summary>
My answer, we don't compete with it. We run them. And here's how I see it as my own view. Agents on your laptop are powerful, but they don't scale. You can realistically run five to 10 of them. Pass that you need a cloud. And cloud needs our secrets, our real stack, our alerts and tickets, one set of rules and enough capacity that nobody gets starved. Those single two owns that for us. So we build layer and that layer exactly what broke. So I want to tell three stories today. How we stop competing on writing code. How we let any agent drive and were broke once they did.
</details>

### 第一个故事：让任何 Agent 都能驱动

第一个故事始于我们不断听到的那个问题。

<details>
<summary>Original English</summary>
The first story start with the question we keep hearing.
</details>

我们越来越多的工程师开始使用 Cursor，他们问：我怎么把我们的密钥放进去？我怎么针对真实的系统技术栈进行测试？我们本可以在 Cursor 内部将这些全部重构一遍，然后为下一个工具再重构一次，之后出来的工具再来一遍。

<details>
<summary>Original English</summary>
More of our engineers were using cursor and they ask how do I get our secret there? How do I test against our real stack? We could have rebuilt all that inside cursor and then again for next two and the one after that.
</details>

相反，答案变成了一句话：让 Cursor 去使用 Spectre 就行了。这其实就是全部的思路所在。人们总会有自己最喜欢的 agent，而且偏好一直在变。所以选择你喜欢的就好：Claude、Codex、Cursor、devin、Slack，或者你自己的双手。

<details>
<summary>Original English</summary>
Instead answer became one sentence just ask cursor to use spectre and that's really the whole idea. People will always have a favorite agent and the favorite keeps changing. So pick yours clock codeex cursor dot slack are your own hands.
</details>

在你的笔记本电脑上开启任务，将会话推送到云端，再拉回来。Spectre 就是这样坐镇于这一切之下。

<details>
<summary>Original English</summary>
Start on your laptop push the session to the cloud. Put it back. That's how spectra sits underneath all of that.
</details>

因为一旦代码写完了，真正的工作才刚刚开始。

<details>
<summary>Original English</summary>
Because once the code was written the real work starts
</details>

想象这样一个场景：凌晨 2 点，Slack 里触发了一条告警。一个 agent 接下了任务，没有人在打字。它编写修复代码，启动我们技术栈的真实副本，并在 PR 上贴出验证证明。

<details>
<summary>Original English</summary>
picture appears day alert fires in Slack at 2 in the morning. An agent picks up nobody typing. It writes a fix, spins up real copy of our stack and post the proof on the PR.
</details>

当 CI 失败时，后续跟踪闭环会读取失败信息并推送另一个修复，而此时大家仍在睡觉。到了早晨，PR 已经停留在同一个审查队列中，遵循着与其他 PR 相同的规则，不论是哪一个 agent 写的。负责人会收到一条提醒，且只在他们的工作日开始时才提醒；一旦获得批准，agent 就可以将其自动合并。

<details>
<summary>Original English</summary>
When C fails, the follow-up loop reads the failure and pushes another fix while everyone still sleep. By morning the PR sits in one review queue under the same rule as other PR whichever agents wrote it. The owner gets a notch and only once they are working day starts and once approved a agent can automerge it.
</details>

如果你在上述我描述的所有阶段中只能构建一个，那就构建后续跟踪闭环。我们在 10 月初向所有人开启了这项功能，而在那个月里，合并进我们后端的 agent PR 中，有五分之四都经历过这个流程。

<details>
<summary>Original English</summary>
If you only build one of those stages that I described build a follow-up loop. We switched it on for everyone in early October and that months. Four out of five agent PRs merge into our backend PR had been through it.
</details>

这就是只会写代码的 agent 与能把工作完成到底的 agent 之间的差距。

<details>
<summary>Original English</summary>
That's the difference between agent that write code and an agent that finished the job.
</details>

此外还有知识层面的问题。每个团队都有那么一个人，他清楚地知道如何去测试那个棘手的服务、哪些 flag 是绝对不能动的。而那些知识都留存在他们的脑海里，或者他们的笔记本电脑上。

<details>
<summary>Original English</summary>
And then there's the knowledge. Every team has that one person who knows exactly how to test the tricky service which flag you never touch. And that knowledge leaves in their head. of their laptop.
</details>

因此我们给它提供了一个归宿：项目。人们写下关键事项，agent 写下它们学到的东西，团队固定下值得信赖的技能，并且留有谁运行了什么的记录。任何在该项目中工作的 agent 都会读取相同的页面。我个人的看法是：无论你选择哪种 agent，审计轨迹和运行痕迹都应当是一致的。

<details>
<summary>Original English</summary>
So we gave it a hope projects. People write down what matters. Adrian write down what they learn. Team pings the skills you trust and there's a record of who rent what. Any agent working in the project read the same page. My personal view whichever agent you pick the audit trail and the tracks should be the same.
</details>

### 第二个故事：规则与 CLI 调用

第二个故事关乎规则。

<details>
<summary>Original English</summary>
The second story is about rule.
</details>

早在 5 月份的时候，如果你想让 Spectre 做点什么，你需要打开一个浏览器标签页，或者在 Slack 里发消息。整整一个月里，来自终端的任务正好只有一个。

<details>
<summary>Original English</summary>
Back in May, if you want a spectctor to do something, you open a browser tab or tacking Slack. The whole mouse, exactly one task came out from terminal.
</details>

于是我们定了一条规则：只要人类可以点击的操作，agent 就可以调用——启动任务、打开后续跟踪闭环、启用自动合并、发布页面，这一切全都可以通过 CLI 完成。

<details>
<summary>Original English</summary>
So, we made a rule. If a person can click it, an agent can call it start a task, turn on the follow-up loop, arm, automerge, publish a page, all from CLI,
</details>

这意味着你笔记本电脑上的 agent 可以调用它，沙箱内部的 agent 也可以调用它，甚至连 CI 也可以调用它。然后大家都开始用起来了。到了 10 月份，命令行每月启动大约 6,500 个任务。Web 端应用并没有萎缩，其他所有场景只是围绕着它一同增长。从终端启动的任务和在浏览器中启动的任务一样都在合并。并且出现了一种新型用户：他们每月启动数百个任务，却完全不打开 Web 应用。

<details>
<summary>Original English</summary>
which means your laptop agent can call it A agent inside the sandbox can also call it. Even CI can call it too. And then people ran with it. By October, the command line was starting about 6500 ts a month. The web app didn't shrink. Everyone else just grew around it. Task started from the terminal were merging and task started in browser. And the new kind of user showed up. people who start hundreds of tasks a month and never open the app at all.
</details>

有趣的地方就在这里。在 10 月份，我手头有一个大任务。所以我启动了一个编码会话，让它担任协调员。

<details>
<summary>Original English</summary>
And this is where it gets fun. In October, I had a big task. So I bought code session and asked to be the coordinator.
</details>

它把工单拆分成了 10 个不同的里程碑。留了一个给我，其余的分配给 Spectre，派生出数百个任务。每一个都有独立的沙箱来进行端到端的验证。然后到了 10 月底，我们的系统给每个人都分配了追踪节点。现在我的那个节点在帮我盯 Spectre。它列出 Spectre 正在等待的问题，起草好我的回复，一旦我确认同意，就发送回去。

<details>
<summary>Original English</summary>
It split the tickets into 10 different milestones. Get one for me and the rest to spectre with hundreds of tasks. Each has its own sandbox to validate end to end. Then at the end of the October, our it give everyone tragic dots. Mind now watch Spectre for me. It list the question Spectre is waiting on. Draft my answers and once I say yes, send them back.
</details>

我其实给朋友发私信就是这么说的：我只是用 Cursor、Claude、Codex 或者随便什么东西去轰炸 Spectre。

<details>
<summary>Original English</summary>
I actually DM to my friend like that. I just use cursor clock code or whatever to spam spectre. Now
</details>

### 第三个故事：系统崩溃与容量治理

这是理想的状态，但它同样也是问题所在。稍作展开：当我们去查看任务时间实际消耗在哪里时，发现最慢的步骤并不是模型思考，而是 Git——光是拉取我们名下的每一个代码仓库，平均就要花费超过一分钟。解决办法就是在每台机器上保留每一个仓库的副本，让每个测试去复用它。

<details>
<summary>Original English</summary>
well that's the dream, but it's also the problem. A quick detour. When we look at where our task time actually went, the slowest step wasn't model syncing. It was get just checking out every ripple we own took over a minute on average. The fix keep a copy of every ripple on every machine and let each test borrow it.
</details>

第三个故事就是系统被搞崩的故事。在 8 月中旬，一个带有 bug 的版本发布上线了。那个 bug 触发了一条告警，每个工作区都会触发一次。于是，一个 bug 变成了数百条告警，全部涌进同一个 Slack 频道。有人配置了一个工作流，在每条告警上都@我们的 agent，而每一次@都会启动一个任务。在平时，这些任务大概启动 50 个；而那天，在大概 4 小时内，它们启动了大约 900 个。

<details>
<summary>Original English</summary>
The third story is the one where it broke in mid August. A release goes out with a bug. That bug triggers alert that fires once per workspace. So one bug become hundreds of alerts all landing in one single sack channel. Someone has set up workflow that tag our agent on every alert and every tag started task. On normal day those task started about 50 task. That day in about 4 hours they started around 900
</details>

900 个 agent 全都在排查同一个 bug，直到整个系统连容纳单个节点的空间都没有了。

<details>
<summary>Original English</summary>
900 agents all chasing the same bug until that wasn't room left for a single note.
</details>

修复方案几乎称得上枯燥：重复的告警现在会直接合并进已经开启的排查流程中。

<details>
<summary>Original English</summary>
The fix was almost boring. A repeat alert now joins the investigation that's already open.
</details>

两个月后，类似的事情又发生了一次，而且这次并不是机器人引发的。在 10 月份，那位工程师完全按照我们一直在要求大家做的那样去做了：把工作交给 Spectre。

<details>
<summary>Original English</summary>
Two months later it happened again and this time it wasn't a bot. On October, the engineer did exactly what we've been asking everyone to do. Hand work to Spectre.
</details>

他在大约 3 小时内从命令行启动了约 950 个测试。我们平台上的一切都无法运转了。集群被占满，其他所有人的工作全都排在这一台笔记本电脑后面。这不是用户的问题，这是我们的问题。

<details>
<summary>Original English</summary>
About 950 test from the command line in about 3 hours. Nothing in our platform can work. The cluster filled up and everyone else work set in line behind one laptop. That's not a user problem. That's our problem.
</details>

四天之后，我们拿出了一个真正的解决方案：一个公平调度启动队列。现在启动任务会为你分配一个排队位置，调度器在有空间时才予以启动。坐在键盘前的人优先，每个人都享有公平的份额，并且可以在集群空闲时借用更多资源。无论何时启动任务，你都可以看到我们的排队位置。当我们用 300 个任务的突发负载对其进行压力测试时，任务启动延迟从接近两秒降到了 70 毫秒。

<details>
<summary>Original English</summary>
Four days later, we had a real fix. A fail launch queue. Now starting a task gives you a place in line. And the dispatcher started when there's room. People sitting at a keyboard goes first. Everyone gets a fair share and can borrow more than the cluster is quite. And whenever you start a task, you can see our placing line. When we hit it with a 300 task bursting low test, the task lit went from almost two second to 70 milliseconds.
</details>

那么，这见效了吗？

<details>
<summary>Original English</summary>
So did it work?
</details>

回到 8 月份每周最繁忙的那天，大约有两千多个任务，其中大约百分之十未能完成。随后到了 11 月 4 日，任务量翻了两倍以上，完成率大为改善，不过我们依然有提升的空间。

<details>
<summary>Original English</summary>
When it's the busiest day of every week back in August, two certain task and about one in hand didn't finish. Then in November 4th, more than twice that and much better in the finish line, but we still have some room to grow.
</details>

谦虚一点说，我们同时改动了好几项内容，所以我无法确切告诉你哪个修复措施起到的作用最大；但突发流量越来越大，平台确实顶住了。

<details>
<summary>Original English</summary>
I will be modest, we change several things at once, so I cannot tell you which fix mattered the most, but the birds kept getting bigger and the platform kept up.
</details>

正当这一处刚刚扛过难关时，瓶颈又转移了。

<details>
<summary>Original English</summary>
And just when that was on the crunch, the model neck moves.
</details>

10 月底，我们的研发平台团队发出了警报：全公司的 PR 在单个月内激增了约 60%。过去只需 15 到 30 分钟的合并，现在要花费一个多小时。合并队列不断地被迫关闭。所以现在的流程是，PR 先 rebase 到 main 分支，重新运行 CI，如果测试通过则予以合并。如果 main 分支被搞崩，所有人的 CI 都会跟着崩掉。坦率地说，我们目前还没有攻克这个问题。

<details>
<summary>Original English</summary>
At the end of October, our dev platform team raised an alarm. PRS across the company had jumped at around 60% in a single month. A merge that used to take 15 to 30 minutes was taking over an hour now. And merge Q kept having to be switched off. So now a PR rebase onto main rerun CI and merge if it's green. If main breaks, everyone CI breaks with it. Alterately, we haven't cracked this one yet.
</details>

但在我结束之前，还有一件事。当我们在……

<details>
<summary>Original English</summary>
But before I go, there's one more thing. While we were
</details>

<!-- chunk 11/50 -->

在我们忙着修整这一切的同时，另一件事物正在悄然生长。我之前给你们展示的大多数内容，都是从一个人发起询问开始的；但在 Spectre 上增长最快的工作来源并非如此。这些是自动化智能体，它们按计划或事件被唤醒，然后直接执行工作：分类告警、审查 PR、撰写帖子。

<details><summary>Original English</summary>
busy fixing all it, something else was quite growing. Most of what I've been showing you start with a person asking the fastest growing source of the work on Spectre doesn't. These are automations agent that wake up on schedule on an event and just do the work tri alert review the PR write the post.
</details>

上个月大约有 110 人运行了自动化，我们吸取的教训是在第一天就给它们设置护栏。如果一个智能体连续失败五次，它就会自行关闭，并且它可以带有预算或过期时间；因为在无人看管时，一个智能体也可以发起数千个任务。

<details><summary>Original English</summary>
Last month about 110 people had automation running and we learned to give them a guardrail on day one. If one fails five times in a row, it switch itself off and it can carry a budget or expiry date because when no one's watching, an agent can start thousands of tasks, too.
</details>

所以，这就是我接下来要探索的，坦白说，我目前还没有答案。

<details><summary>Original English</summary>
So, here's what I'm chasing next, and I don't have an answer yet, honestly.
</details>

如果每个 Slack 频道都有自己永不下线的智能体呢？一个能关注竞争并在自主状态下开展工作的智能体。如果每个 PR 在人类查看之前都能证明其有效呢？如今只有二十分之一的合并带有这种证明。

<details><summary>Original English</summary>
What if every Slack channel had its own agent that never locks off? One that follows competition and start work on its own. What if every pure proof it works before a human even look at it? Today only one merge in 20 carries that kind of proof.
</details>

而且当智能体不停地发起 PR 时，你该如何进行合并呢？

<details><summary>Original English</summary>
And how do you merge when agents never stop opening PRs?
</details>

六个月后再问我吧。到时候我会告诉你什么地方崩溃了。如果你在工作中也在构建类似的东西，这里有三点我会再次践行的做法：关注代码写完之后会发生什么；让每一项操作都成为智能体可以调用的东西；以及在它们发现自己能用它做什么之前，限制智能体、人类或告警所能启动的操作上限。

<details><summary>Original English</summary>
Ask me again six months. I will tell you what broke. If you're building something like this when you work, here's three things I do again. Oh, what happens after code is written. Make Eric action something an agent can call and cap what an agent, human or alert can start before they find out what they can do with it.
</details>

最后还有一个想法，这是我自己的看法。工程师们可以用他们喜欢的任何智能体来编写代码。真正沉淀下来的工作，是运行它、检查它并使其完成合并的测试脚手架与调度体系。

<details><summary>Original English</summary>
And one last thought, that's my own view. Engineers can write code with whichever agent they like. The work that's lost is the harness that runs it, checks it, and get it merged.
</details>

非常感谢大家的观看。如果你也在构建类似的东西，欢迎在领英上找我。

<details><summary>Original English</summary>
Thank you so much for watching. Come find me on linking if you are building similar things.
</details>

### 基于形式化方法的规范分析

>> 大家好，我叫 Rajat Kotial。我是 AWS 自动推理小组的一员，今天我要讲的是我最近参与的一个项目，名为 KO 规范分析器。我们使用包含形式化方法和自动推理的特定技术，在你的编码智能体编写代码之前，证明送交给它的规范。

<details><summary>Original English</summary>
>> Hi everyone, my name is Rajat Kotial. I'm part of the automated reasoning group at AWS and today I'm going to talk about a project I worked on recently called KO specification analyzer and u we use certain techniques which involves formal methods and automated reasoning to prove specification that goes to your coding agent before it writes code.
</details>

我们来看某个特定的缺陷。这是一段规范片段，例如这里有两条规则。规则二说明，当提交订单且库存不足时（假设这是一个通用的电子商务网站），我们将订单置为延期交货状态。单独阅读这一条时，它是合情合理的。

<details><summary>Original English</summary>
So let's take a certain bug right this is a specification uh snippet and there are two rules for example and uh the rule two says when an order is submitted and this is for a a general e-commerce website let's say when an order is submitted and the inventory is unavailable we place the order as a back order which makes sense when you read it individually and
</details>

而在你交给编码智能体的同一份规范文件中，还有另一条规则说明，任何订单都不得置为延期交货状态，这是我们设定的规则。单独阅读这两行时都是合理的，对吧？但当 LLM 同时阅读这两条规则时，两者无法同时成立。因此我们需要确保消除 LLM 所观察到的这种歧义。

<details><summary>Original English</summary>
there's also another rule in the same specification file uh which you hand to the coding agent which says u no order shall be placed as a back order and this is a rule we've set so individually read these two lines make sense right but in when an LLM reads this reads both the rules together both cannot hold true at the same time so we need to make sure the we resolve this ambiguity that the LLM is observing
</details>

我们在这个项目上投入精力的范围和原因在于，基于公开研究和最近的研究，我们观察到不清晰的提示词会导致 LLM 生成代码的准确性下降 20% 到 40%，并且有效代码在编写完成后仍有 60% 到 90% 存在错误。此外，在那种情况下，我们在部署该代码时会观察到两倍的回归缺陷。

<details><summary>Original English</summary>
and uh the scope and the reason we uh put an effort into this project is based on public research and recent research we've observed there's a 20 to 40% drop with unclear prompts on the accuracy the LLM uh generates on the code accuracy right and 60 to 90% % of valid code is still wrong after it writes it and also in that case we observe two times the more more regressions when we uh deploy that code
</details>

那么像这样的缺陷隐藏在哪里呢？我们希望在这些缺陷进入代码库之前检测出它们。唯一的做法类似于我们撰写设计文档、绘制图表和流程图，以确保在编写任何代码之前流程就已经确立。我们希望在没有任何人类或其他人员将这些文件作为第一审查人阅读的情况下对其进行验证。

<details><summary>Original English</summary>
so where do bugs like these hide right we want to detect these bugs before they reach the code base and the way only way to do that it's similar to how we write design docs similar to how we draw diagrams and flowcharts to make sure the flow is set before we write any code. We want to verify that without a human or anyone reading these files as the first reviewer.
</details>

在一句话的层面上，可能存在歧义、措辞不当以及细节层级错误；但在跨句子的层面上，我们能观察到规范或规则中的冲突与空白，句子之间需要揭示其关联并进行歧义检索。

<details><summary>Original English</summary>
In one sentence, let's say the ambiguity and wording wrong level of detail, but across sentences, we can observe conflicts and gaps in the specification or rules, right? Sentences need reveals that need search and between them and ambiguity searches.
</details>

因此我们有一个包含三步的过程来处理这项工作：LLM 首先会对其进行精炼，尝试自行清理措辞，如果成功了那固然很好；但如果无法做到，我们就会将英语语言形式化为 SMT 公式。SMT-LIB 是一组特定类型的函数，我们会将其传递给 SAT 求解器（即可满足性检查器），它将输出一个布尔值，表明你给我的这个表达式是有效（真）还是无效（假）。

<details><summary>Original English</summary>
So we have a three-step process to do this where the LLM will first refine it. It will try to clean up the wording on its own and um if it succeeds then well and good but if it cannot we then formalize the um English language into SMT formulas. So SMT lib is a certain set of type of function which we pass to a SAT solver a satisfiability checker where it's going to give out a boolean saying this expression that you've given me is valid true or false invalid
</details>

一旦求解器向我们返回结果，如果该表达式是有效的，我们就不做任何处理。但如果它检测到两个句子之间存在任何歧义，或者单个句子内部存在两种含义，我们就会检测出来并告知 LLM 重新检查该句子，它将就此展开重新迭代。

<details><summary>Original English</summary>
and then once the solver gets back to us if that expression is valid then we don't do anything. But if it detects any ambiguity between two sentences or within a sentence where there's two meanings to a sentence, then we detect that and tell the LLM to recheck that sentence and it's going to reiterate on that.
</details>

例如我们看到的规则：“当订单提交且库存不可用时，我们应将订单置为延期交货”。在 SMT 格式下，它看起来大致是这种形式，就像一个数学公式，对吧？

<details><summary>Original English</summary>
For example, the rules we saw, we've seen when order is submitted and inventory is unavailable, we shall place the order as a back order. And in SMT format, it kind of looks like this. This is like a mass formula, right?
</details>

一旦我们进一步深入，一旦检测到这种情况，我们还会再次执行一个三步过程：对翻译进行反复采样。我们让 LLM 翻译 7 次或 10 次，以理解该 LLM 表现出这种行为是基于其固有能力，还是有某种因素在影响它导致其表现成这样。

<details><summary>Original English</summary>
Once we go deeper, we once we detect this, we also do a three-step process again where we sample the translations again and again. We ask the LLM to translate it seven times or 10 times and to understand whether this LLM is behaving this way uh based on its inherent capabilities or is something affecting it to behave this way
</details>

随后，基于 LLM 这 7 组或 10 组不同解释的逻辑等价性，我们按逻辑等价性对它们进行聚类——区分哪些条目归入 LLM 为自身设立的哪些假设之下。然后我们接受它，或者要求用户消除歧义，亦或放弃在代码库中实现该部分。

<details><summary>Original English</summary>
and then based on logical equivalence of these seven or 10 um different set of interpretations by the LLM we cluster them on logical equivalence which sets which uh um entries came under which uh assumptions that the LLM made for itself and then we accept or ask the user to clear out the ambiguity or abstain from implementing that in the codebase.
</details>

这是一个向人类询问如何处理那条可能存在矛盾的规范规则的示例。“删除记录”（remove the record）是一句非常模糊的表述。LLM 可以随意解释，但我们不应该允许这种情况发生。我们要么给出两个选项——保持原样（记录被删除），要么保留它但对用户隐藏——让用户选择哪一个。

<details><summary>Original English</summary>
This is an example of asking the human um what you want to do with that spec rule that was um perhaps contradicting. remove the record is very a very vague statement. The LLM cannot can interpret anything it wants but we shouldn't allow that to happen and we either give two options we keep it as is the record is deleted or we retain it and but hide it from the users which one does the user.
</details>

冲突是指像我们看到的示例中，规则一与规则三相冲突；而空白则是指没有任何规则覆盖空闲订单的情况。在这个示例中，LLM 实际检测到——抱歉，是流程或管线检测到——该规则不存在条目，说明遗漏了某些内容。

<details><summary>Original English</summary>
Um a conflict is when the examples we example we saw rule one it's conflicting with rule three and a gap is where no rule covers an idle order in this example where the LLM detected an actual sorry process or pipeline detected there's no um entry for this rule where you are missing something
</details>

总的来说，它有很多事情是做不到的。归根结底，我们希望确保除了用户之外，没有任何用于规范正确性的终极裁决标准（oracle）。用户需要确保在将规则手册的各个代码片段部分发送给 LLM 之前对其进行检查。

<details><summary>Original English</summary>
all in Well, it cannot do a lot of things. End of the day, we want to make sure there is no oracle uh for for specification correctness other than the user. User needs to make sure to check every part of the snippet part of the rule book before sending it to the LLM.
</details>

作为工具，我们只能提供辅助，而用户在这里更为关键，因为存在隐性领域知识。LLM 并不了解大量的领域知识，而且不存在保证——我的意思是，只有用户才能给出这种保证。目前关于形式化及其在智能体中如何应用的证据还很单薄，我们正在这项技术中逐步探索。

<details><summary>Original English</summary>
And um we as a tool only can help them and the user is more important here because of implicit domain knowledge. The LLM doesn't know a lot of domain knowledge and there's no guarantee I mean LLM only uh user can give that guarantee right and there's thin evidence right now for formalization and how it can be used in agents we are emerging in this technology
</details>

我们能从这次演讲中获得什么启发呢？在将规范传递给智能体之前，务必先检查规范；对翻译进行聚类——我们所做的是按逻辑等价性对翻译进行聚类，以确定不同的 LLM 解释以及它究竟在何处出错。LLM 进行翻译，求解器进行检查，人类做出决定。我们给人类提供选项，如果对此没有答案，我们就使用 LLM 评审员，或者放弃实现那一部分。

<details><summary>Original English</summary>
what do we take back from this um talk check the spec always before you pass it down to the agent uh cluster the translation We what we do is we cluster the translation by logical equivalent to determine the different LLM interpretations and where it's genuinely going wrong. The LLM translates the solver checks and the human decide. We give give the human uh options and if there's no answer to that we use LLM judges or abstain from implementing that piece.
</details>

这里是参考资料，这项工作主要由我的团队贡献，包括 Anda、Jin、Stefan、Nia 和 Delmos。你们可以通过提供的网站链接查看他们的博客，并对此进行更深入的了解。谢谢大家。

<details><summary>Original English</summary>
Here are the references and um this work has been majorly contributed by my team um Anda Jin, Stefan, Nia and Delmos. You can check out their blog in the website link provided and um del deeper into this. Thank you.
</details>

### 构建全天候 AI 值班队员

>> 大家好，我是 Chinme，与我一同前来的还有 Swapnika 和 Vlad。我们很高兴能分享我们在 Meta 构建 AI 值班队员的过程与心得，它现在每天、全天候运行着真实的值班轮换。

<details><summary>Original English</summary>
>> Hi, I'm Chinme and with me are Swapnika and Vlad. We're excited to share our journey as well as our learnings around building an AI on call teammate at Meta that now runs real on call rotations every day and around the clock.
</details>

我们隶属于在 Meta 负责构建突发事件响应、值班体验和缓解措施所需的工具平台与基础设施的工程团队。随着 AI 能力的提升，这一领域正在迅速演变。

<details><summary>Original English</summary>
We are part of the engineering team that builds the tooling platform and infrastructure for incident response on call experience and mitigations at meta. That space is evolving rapidly with the increase in AI capabilities.
</details>

AI 改变了我们编写代码的速度。现在大约有四分之三的新代码是用 AI 编写的。每天都有更多 AI 生成的变更进入生产环境。而其中一些代码变更可能像其他任何代码变更一样，引发生产故障。

<details><summary>Original English</summary>
AI changed how fast we write code. About 3/4 of new code is now written with AI. And more AI generated changes reach production every single day. And some of it can cause production failures just like any other code change can.
</details>

但值班并没有随之加速。高质量的代码可以通过审查，但仍会在生产环境中发生故障。而当它发生故障时，仍然会有人在凌晨 2 点被呼叫唤醒。瓶颈已经从

<details><summary>Original English</summary>
But on call did not speed up with it. Highquality code can pass review and still break in production. and when it does, someone still gets paged at 2 a.m. The bottleneck moved from
</details>

<!-- chunk 12/50 -->

从编写代码到在生产环境中运行它。而值班正是承载这些运维负荷的地方。所以我们提出疑问：既然 AI 正在编写代码，AI 是否也能协助运维？我们认为答案是肯定的。现在让我们通过一个简化示例，快速梳理一次典型的值班报警。

<details><summary>Original English</summary>
writing code to operating it in production. And on call is where that operational load lands. So we asked if AI is writing the code, can AI also help operate it? And we think it can. Now let's quickly run through one of those on call pages with a simplified example.
</details>

现在是凌晨 2 点，有 12 个警报正在触发。同一夜，事情可以有两种截然不同的走向。左侧是我们大多数人今天采用的做法。注意，我们这时已经有了不错的 AI。首先，你自己给这些警报排序：结账、支付、磁盘，先选哪一个？假设你选了结账。接着你向助手询问为什么 P99 延迟偏高。它确实很有用：拉取指标，并在 1:49 发现了那次部署。当你提问时，它会读取变更内容并核对操作手册（runbook）。

<details><summary>Original English</summary>
It's 2:00 a.m. and 12 alerts are firing. Same night, it can go two different ways. On the left is how most of us do this today. And notice we already have good AI. First, you sort the alerts by yourself. Checkout, payments, disk, which one to pick first. Let's say you pick checkout. Then you ask your assistant why P99 latency is high. It's genuinely useful. It pulls the metrics and finds the deployment at 149. And when you ask, it reads what changed and checks the runbook.
</details>

它查明时间配置被改为了较小的值。根据操作手册，它建议进行回滚，这一切都非常有帮助。然而，如果看一下整个过程的形态，它是处于被动等待提问的状态。每一步后续动作都由你来挑选。你成了各个问题之间的粘合剂；一旦它回答完毕，就又进入休眠。到了 2:39，你虽然知道了原因，但回滚、各项改动和后续跟进仍然由你亲自完成。

<details><summary>Original English</summary>
It figured out that the time config was changed to a lower value. And based on the runbook, it suggests to roll back, which is all very helpful. However, if you look at the shape of it, it waited to be asked. You picked every next step. You were the glue between the questions and once it answered, it went dormant. At 239, you know the cause, but the roll back, the changes, and the follow-ups are still yours.
</details>

现在看右侧，同样的 12 个警报，但在你醒来之前，AI 队友就已经开始介入了。它已经给它们排了序：结账排第一，支付因归结为同一原因被合并进来，其余 10 个则单独处理。它查看了仪表盘，对比了过去的两次故障事件。你获得了一个假设、一种 30 秒即可完成验证的方法，以及一份等待你审核的修复方案。在 2:11，你完成验证，然后回去继续睡觉。这种差距正是本场演讲的主题所在。

<details><summary>Original English</summary>
Now, on the right, the same 12 alerts, but an AI teammate started before you woke up. It had already ranked them. Checkouts first, payments merged in as the same cause, and the other 10 handled separately. It read the dashboards, difficed two past incidents. You get a hypothesis, a 30-cond way to verify it, and a fix waiting for your review. At 2011, you verified it and you're back to sleep. That gap is what this talk is about.
</details>

那么，为什么此前必须由你来充当粘合剂？因为每个团队都在各自的孤岛中，一次一个地把自动化硬拼到值班流程上：警报脚本用于警报，分诊机器人（triage bot）用于工单，部署机器人用于部署，修复 agent 用于故障处理。每一个都解决自己的切片，保留自己的上下文，随后又将其遗忘。现在复盘你凌晨 2 点收到的报警：警报脚本检测到 P99 延迟超过 2 秒；分诊机器人看到三张表示结账缓慢的工单；部署机器人知晓 1:49 有一次配置变更；而故障历史记录中有两次类似的既往事件。每一个线索都存在，但没有任何东西把它们串联起来。于是值班人员就变成了粘合剂，正如我们在前一张幻灯片左侧看到的那样。

<details><summary>Original English</summary>
So why were you the glue? Every team was bolting automation onto on call one silo at a time. An alert script for alerts, a triage bot for tickets, a deploy bot for deploys, a fix it agent for incidents. Each one solves its slice, keeps its own context, and forgets it. Now replaying your 2 AM page, the alert script saw P99 latency above 2 seconds. The triage bot saw three tickets saying checkout is slow. The deploy bot knew about a config change at 149 and the incident history had two similar past incidents. Every clue existed, but nothing connected them. So the on call became the glue exactly as we saw on the left side of the previous slide.
</details>

我们的下注则是为每个轮值轮换配备一名 AI 队友。一个贯穿所有信号的闭环，一段在每个班次不断学习的团队记忆，它自己的身份以便它以独立实体行事，以及一道人工把关门槛，从而让你负责审批而非亲自操作。但是，赋予单个 agent 如此多的上下文和权限也会提高风险。这正是自主权必须循序渐进赢得的原因。

<details><summary>Original English</summary>
Our bet was one AI teammate per rotation instead. One loop across every signal, one team memory that learns every shift, its own identity so it acts as itself and a human gate so you approve instead of operate. But giving one agent all that context and reach raises the stakes. Which is why autonomy has to be earned.
</details>

在底层，这个队友——或者说 AI 队友——是结构最简单的 agent。就是一个模型在闭环中使用工具，对环境采取行动，并读取反馈。本场演讲中涉及的所有其他内容，都是围绕该闭环所构建的保障，以确保让它持续运行是安全的。接下来我将交给 Swapnika 和 Vlad，由他们深入探讨其具体的运作细节。

<details><summary>Original English</summary>
Under the hood, the teammate or the AI teammate is the simplest agent. There is model using tools in a loop acting on an environment and reading the feedback. Everything else in this talk is what we build around that loop to make it safe to leave it running. And for that I will hand over to Swapnikai and Vlad next to get into the actual details of how it works.
</details>

### 自主权阶梯

为了实现这一点，我们首先设计了自主权阶梯。想想你是如何指导一名新工程师上手值班的：起初是跟班观摩（shadow），调查并提出建议，但不触碰生产环境；接着是结对，编写修复方案，由另一名工程师进行审批；随着时间的推移，他们积累了知识。我们赋予 agent 完全相同的阶梯。在一级，它进行调查并告诉你它的发现，不做任何更改。在二级，它在经受批准的前提下采取行动：起草修复方案，但在人工批准前，任何内容都不会进入生产环境。在三级，它独立清理由它负责的较低关键性工作，只在遇到重要事务时才打扰你。高关键性工作依然由人工负责。

<details><summary>Original English</summary>
To achieve this we started with an autonomy ladder. Think about how you onboard a new engineer to on call. First the shadow. The investigators suggest but they don't touch production. Then the pair the right to fix and another engineer approves it. With time they gain knowledge. We give our agent exactly the same ladder. At level one, it investigates and tells you what it found. It changes nothing. At level two, it acts with approval. It drafts the fix, but nothing reaches production until a human approves. At level three, it clears lower criticality work on its own and only interrupts you for what matters. High criticality work stays with humans.
</details>

那么，怎样才能登上下一级台阶？我们采用了一个简单的测试：犯错的代价有多高，以及抓住错误有多容易？因此，只有当犯错代价很低、能够被测试、CI 或代码审查拦截，并且该 agent 在该特定操作上已具备良好记录时，该操作才能向上晋升。正因如此，agent 可以独立关闭一条噪音警报，而生产环境的缓解措施仍需等待人工介入。

<details><summary>Original English</summary>
So what earns the next run? We use a simple test. How costly is a mistake and how easy is it to catch? So an action climbs only when mistakes are cheap. They're caught by tests, CI or review. and the agent already has a track record on that exact action. That's why the agent can close a noisy alert on its own while a production mitigation still waits for a human.
</details>

在一级，调查呈分层推进，并在获得第一个有把握的答案处停止。agent 利用团队的记忆库和操作手册调查问题，它还分享了根本原因分析，但必须由人工应用修复。在二级，它会附带根本原因和测试计划编写修复方案。它会回复审查者的意见并修复 CI，但在人类批准前，任何内容都不会进入生产环境。

<details><summary>Original English</summary>
At level one, the investigation is layered and stops at the first confident answer. The agent investigated the issue using the team's memory and runbook. It also shared the root cause analysis, but human had to apply the fix. At level two, it writes the fix with the root cause and a test plan. It answers reviewer's comments and fixes CI, but nothing reaches production until a human approves.
</details>

大多数草案并没有合入，这完全没问题。代码审查就是过滤器。在这两个层级上，agent 完成了前期功课，但你仍然不得不批改每一份作业。协助虽然大幅改善，但需要人类投入的任务总量并未减少。三级则缩减了堆积的任务。看这个例子：涌入了 23 个事项，但只有 3 个需要你。在右侧，agent 处理了长尾部分：噪音警报、重复项，以及经过常规审查和 CI 的日常修复。另外还有两项仍在进行中。你不必推进每一项直至完成。中间是你大大缩减的决策队列。每个事项都明确指出了需要你做什么，并配有一个附带行动号召的“运行此操作”按钮。还记得我们凌晨 2 点的结账报警吗？那依然保留给人工处理。agent 负责提供调查成果，人类负责把控关键决策。这再次体现了新层级阶梯：值得信赖地处理日常工作，在需要帮助时备齐功课。不仅每项工作的量减少了，等待你处理的事项总数也更少了。

<details><summary>Original English</summary>
Most drafts don't land, and that's fine. Review is the filter. At both levels, the agent does the homework, but you still had to grade every single paper. The help got much better, but the tasks requiring human input didn't get smaller. Level three shrinks the pile. Look at this example. 23 items came in, but only three need you. On the right, the agent handled the long tail, noisy alerts, duplicates, routine fixes that went through normal review and CI. Two more are still being worked. You don't have to drive each one to completion. In the middle is your much smaller decision queue. Each item makes clear what it needs from you with a run this button that has a call to action. And remember our 2 a.m. check out page that still stays human owned. The agent brings the investigation. The human owns the critical decision. It's the new high ladder again. Trusted to handle routine work, ready with the homework when it needs help. Not just less work per item, but fewer items waiting on you.
</details>

那个看板是工作汇总呈现的地方。但没有人会一直盯着看板看，对吧？因此，该 agent 还分布在许多界面中，比如聊天工具和原生故障处理界面。每天早晨 9 点，它会发布一份摘要：收到 23 项，3 项需要你，18 项已处理完毕。每一项需要你的事务都配有一键式的后续操作步骤。因此，从手机上批准配额提升只需轻点一下。它处理完毕的 18 项进行的是汇总说明，而非逐一罗列。仍在进行的两项则告知你它正在就此采取什么措施。当你想要深入了解时，只需在对话串中回复即可。正如你在右侧看到的，你打开结账故障事件并要求提供证据，它已经准备好了：错误从 8:41 开始，发生在一次降低了支付客户端超时时长的配置推送 2 分钟后，与过去的两次事件模式完全相同。你继续跟进提问：“仅仅是欧盟区吗？”它给出了明细解答。它起草了回滚方案，你就在那里批准，错误随之开始恢复。你从未打开过仪表盘，也无需解释上下文，因为这些早已就位。这就是队友带来的体验：一份晨间交接，一位随时供你询问的同事。

<details><summary>Original English</summary>
That board is where the work lives. But nobody stares at a board all the time, right? So the agent is also available across many surfaces like chat and native incident surfaces. At 9 every morning, it posts a digest. 23 came in, three need you, 18 handled. Each thing that needs you come with a one-click next step. So approving the quota bump takes one tap from your phone. The 18 it handled are summarized, not listed. And the two that are still in progress tell you what it's doing about them. And when you want to dig in, you just reply in the thread. As you see on the right here, you open the checkout incident and ask for the evidence. It already has it. Errors start at 8:41, 2 minutes after a config push cut the payment client timeout. The same pattern as two past incidents. You ask a follow-up, is it only EU? And it answers with a breakdown. It drafts the roll back. You approve it right there and errors start recovering. You never opened a dashboard and you never had to explain the context because it was already there. That's what a teammate feels like. A morning hand off a colleague you can ask.
</details>

现在来看这个 AI 队友的底层架构，它是由若干 AI 自动化机制构成的。第一种负责调查：每当出现新信号，自动分诊机制对其进行分类，检查其关键性，并触发对应的 agent。警报交给故障调查员，任务交给团队自有的 agent，测试失败交给编码 agent，查询操作交给记忆与代码搜索。第二种负责维持系统健康。无人看管的自动化往往会无声无息地失效。因此，它按既定计划检查卡住或失败的运行实例，重试并修复受损的调度日程，只有当它自己无法修复时，才会向人类发送传呼报警。没有任何任务会静默停滞。

<details><summary>Original English</summary>
Now under the hood of this AI teammate, it's AI automations. The first investigates on every new signal auto triage classifies it, checks its criticality and kicks off the right agent. An alert goes to the incident investigator, a task to the team's own agent, a test failure to a coding agent, a look up to memory and code search. The second keeps the system healthy. Unattended automation fails quietly. So on a schedule, it looks for stuck or failed runs, retrace and repairs broken schedules, and it only pages a human if it can't fix it itself. Nothing stalls silently.
</details>

第三种负责在每次班次轮换时进行交接，并在每天早晨 9 点总结整个班次的情况：将哪些事项需要你并备好修复方案、哪些事项由它自行处理发布到团队聊天群中。不仅在早晨，而且每当有紧急问题需要用户关注时，都会在聊天中附带调查发现和修复草案发出通知。在交接期间，它还会在聊天中 @ 提醒下一位值班人员。整个循环依旧持续运转。

<details><summary>Original English</summary>
The third hands off at every shift change and every morning at 9, it summarizes the shift. What needs you with the fix ready and what it handled on its own posted to the team chat. Not only in the morning, but every urgent issue that needs user attention gets notified in chat with findings and draft fixes. It also tags the next on call in the chat during handoff. The entire cycle still continues
</details>

因为它是归属于团队的，所以它运行的是团队早已信任的 agent 和技能。这就是中间的插槽：自带 agent，添加你自己的技能。如果团队已经拥有一个掌握团队操作手册和知识库的 agent，自动化机制就会加以利用。除此之外，它还配备了我们自己的故障调查员和深度编码会话支持。工作任务来自警报、工单、故障、团队发帖和聊天。agent 本身是通用的。让它胜任值班轮换工作的，是团队所赋予的 agents、技能、记忆和操作指南。并且每次运行都有日志记录，因此团队中的任何人都可以检查运行轨迹或恢复对话。

<details><summary>Original English</summary>
and because it belongs to the team, it runs the agents and the skills the team already trusts. That's the slot in the middle. Bring your own agent, add your own skills. If a team already has an agent that has the team's runbooks and the knowledge base, the automations leverage it. Alongside that, it has our own incident investigator and a deep dive coding session. Work comes in from alerts, tickets, incidents, team posts, and chat. The agent itself is generic. What makes it good at an on call rotation is the team's agents skills, memory, and playbook. And every run is logged, so anyone on the team can inspect the trajectory or resume the conversation.
</details>

现在，我将交给我的队友 Vlad，由他进一步探讨共享 agent 的话题。值班 agent 不能只属于单个人，因为值班本身就不是单打独斗的。因此它属于……

<details><summary>Original English</summary>
Now, I'm handing off to my teammate Vlad to talk more on the shared agent. An uncle agent can't belong to just a single person because the uncle itself doesn't. So it belongs to the
</details>

<!-- chunk 13/50 -->

团队。

<details><summary>Original English</summary>
 team.
</details>

每个轮班组在一个面板上配备一名队友。无论谁在值班，都可以让它进行纠偏，或者在排查中途接手工作。它将团队的 on-call 专门经验、运行手册（playbook）、负载画像（lord profiles）以及过去的决策从一个班次传递到下一个班次，正如一次优质的交接所应当做的那样。

<details><summary>Original English</summary>
There's one teammate per rotation on one board. Wherever's on call can ask it to correct it or pick up its work mid investigation. It carries the team's uncle expertise, the playbook, lord profiles and past decisions from one shift to the next one the way a good handoff should.
</details>

具体过程是这样的。周一凌晨 2 点，Sam 在值班，告诉它记住：如果配置推送后结账超时，先回滚配置。它把这条记入记忆。三天后，Jordan 值班遇到完全相同的告警，直接向它寻求修复方案。Agent 回答了某种修复方法，说明了其来源，并起草好了回滚方案。教它一次，下一次电话值班就能直接受益。

<details><summary>Original English</summary>
Here's what that looks like. Monday at 2 am, Sam is on call and tells it remember if checkout time is out after a config push, roll back the config first. It saves it to the memory. Three days later, Jordan is on call hits the exact same alert and just asks for a fix. The agent answers with some fix, says where it came from, and has the roll back drafted. Teach it once, the next phone call gets it.
</details>

而且它作为团队访问，拥有自身由轮班组所掌管的身份，且仅具备团队乐意授予它的访问权限。

<details><summary>Original English</summary>
And it access the team its own identity owned by the rotation with only the access the team is comfortable granting it.
</details>

它还会从每一次 on-call 轮班中学习。交接记录、决策和纠错都会流入记忆。因此第 30 次轮班的表现优于第 1 次轮班，就像新值班人员每周都会进步一样。但记忆会随着时间退化，所以我们的记忆条目必须靠实力立足。它采用语义化检索，使用所查找到的内容，评估哪些内容切实起到了帮助，并自动晋升或停用相关条目。

<details><summary>Original English</summary>
And it learns from every uncle shift. Handoffs, decisions, and corrections all flow into memory. So ship number 30 is better than the ship number one. The same way a new uncle gets better every week. But memory erodess over time. So ours has to earn its place. It retrieves semantically uses what it finds, scores where it actually helped and promotes or retires entries automatically.
</details>

当有人指出“那是错的”时，该事项会重新开启，纠错内容随即转化为记忆。

<details><summary>Original English</summary>
When someone says that was wrong, the item reopens and the correction becomes memory.
</details>

有三点让这套方案得以推广至我们团队之外：

第一，一个永不停止倾听的闭环。每一条反馈或方向修正都会重新开启该事项，并最终被吸收到记忆中。反馈是系统的输入项，而不是每个季度才读一次的故事。

第二，定制而非分叉（fork）。各团队自带各自的运行手册和技能工作流，而底层依旧是同一个队友。

第三，我们称之为从单一轮班到 N 的扩展。身份、配置和记忆都按团队独立划分。因此，增加一个轮班组只是一次设置过程，而不是立项一个新工程。Agent 本身是通用的，而专业经验则归各团队所有。

<details><summary>Original English</summary>
Three things made this work beyond our team.

First, a loop that never stops listening. Every piece of feedback or course correction reopens the item and ultimately gets absorbed into memory. Feedback is an input to the system, not a story read once a quarter. Second, customize instead of forking. Teams bring their own playbooks and skill workflows, and it's still the same teammate underneath.

Third, what we call one rotation to end. Identity, config, and memory are per team. So, add a rotation becomes a setup, not a new project. The agent is generic while the expertise is owned by the team.
</details>

那么，值班人员的工作发生了哪些变化呢？

首先，他们的工作重心从主导深入排查转变为做出关键决策。他们从附带关联证据的假说出发，而不是面对空白的任务或仪表板。

其次，负担正在减轻。对于让其自主运行的团队，值班负担减轻的早期迹象令人鼓舞，我们希望在给出具体数字前对其进行严谨的衡量。

第三，Agent 编写的每一次变更仍会经由人工审核。修复方案唯有通过常规审查和持续集成才能合入代码库，且绝大多数草案并不会合入。重点就在于此：审查就是过滤器。On-call 不再是一种负担，而是变成了一个审查队列。

<details><summary>Original English</summary>
So what has changed for the people on call? Well, first their job shifted from driving deep investigations to making key decisions. They start from a hypothesis with linked evidence, not a blank task or dashboard.

Second, the load is getting lighter. Early signs of on call load reduction are promising for teams that run it automatic autonomously and we want to measure it rigorously before we put a number on it.

And the third every change that agent writes still meets a human. Fixes land only through normal review and continuous integration. And most drafts don't land. That's the point. Review is the filter. Uncle stops being attacks and becomes a review cube.
</details>

以下是我们下一步关注的重点：

第一，获得批准而不仅仅是起草的缓解措施。我们对 Agent 提出的每一项缓解措施进行评分，并反馈其结果，让它凭借表现晋级到下一阶段，而不是直接被赋予特权。

第二，直接从聊天中编写技能，使团队无需编写任何代码即可将运行手册（runbooks）转化为技能。

第三，妥善衡量我们所节省的时间，通过对节省的 on-call 时间开展严谨研究，而非单纯统计使用次数。

天梯上的下一个台阶，则是凭借扎实证据赢得中等关键度的自主权。

说到这里，非常感谢大家的聆听，希望这些内容对大家有所帮助。再见。

<details><summary>Original English</summary>
Here's what we're focusing on next. First, mitigations that get approved, not just drafted. We great every mitigation that agent proposes and feed the outcome back so it earns its next level instead of being handed it. Second, skills are written from the chat so a team can turn its runbooks into skills without writing any code. And third, measuring the time we give back properly with a rigorous study of uncall time saved rather than usage counts.

And the next rung on the ladder is uh earning medium criticality autonomy with evidence. On that, thank you so much for listening to us and hopefully that was helpful. Bye.
</details>

Heat. Heat.

Heat. Heat.

Heat.

Heat.

Hey,

hey, hey.

Heat. Heat. N.

<details><summary>Original English</summary>
Heat.
Heat.

Heat. Heat.

Heat.

Heat.

Hey,

hey, hey.

Heat. Heat. N.
</details>

### Gemini 模型迭代与轻量化 Agent 框架

以及利用工具框架（harness），我们需要的代码就越少。

如果我们审视一下 Google DeepMind 过去 6 个月里所做的事情——5 月份我们举办了 Google I/O，而今天是 11 月 11 日，我们一直在马不停蹄地发布成果。

基本上就在今天早些时候，我们通过 Gemini Decision 1 发布了我们的首个决策模型。昨天我们推出了 Gemini 4 Carbon。如果纵观过去六个月，我们基本上每隔几周就会发布新模型。

正如之前提到的，Gemini Carbon 现在已经可供大家使用。如果你是 Google AI Ultra 订阅用户，你可以在 Antigravity 中使用它，可以在 Gemini 应用中使用它，也可以在 AI Studio 中使用它。Carbon 在 CursorBench 评测中名列第一，在 Perplexity 基准测试中也位列第一。在 Google 内部，我们已经大量使用它了。

更令人兴奋的是，我很高兴地宣布，我们在大约一小时前通过新的 Gemini Decision 1 模型推出了 Gemini Decisions API。这是一个类似于 Chef 的模型。你可以提供所有现有的 Gemini 输入方式，这意味着它是多模态的。因此你可以原生提供文本、音频、图像、视频以及 PDF，然后在单个请求中最多提供 1,000 个问题。包含所有网络开销在内的平均端到端延迟在 150 到 250 毫秒之间，成本为每 100 万 token 10 美分。

<details><summary>Original English</summary>
and harness and the less code we need.

And if we look at um what we have been doing at Google deepmind for the last 6 months. So at May we had Google IO IO and today it's uh November 11 and we have been shipping relentlessly.

Basically just earlier today we announced our first decision model with Gemini decision one. Yesterday we made Gemini 4 carbon available and then if we just look at the last six months we basically ship now models every few weeks. Um as already said Gemini Carbon is now available for you. So if you are a Google AI ultra subscriber, you can use it in anti-gravity, you can use it in the Gemini app, you can use it in AI studio. Uh carbon is number one on the cursor bench uh eval and also number one on the perlexity benchmark and internally at Google. We have been using it already a lot and much more exciting is that I'm happy to share that we launched the Gemini decisions API roughly one hour ago with our new Gemini decision one model. So it's a similar model to Chef. You can provide all of the existing Gemini inputs, meaning it's multimodal. So you can provide text, audio, images, video, and also PDFs natively, and then provide up to 1,000 questions in a single request. The average end to-end latency, including all of the network overhead, is between 150 to 250 milliseconds, and it costs 10 cents per 1 million token.
</details>

那么模型是如何在工作中变强的呢？这就是关于后训练（post-training）运作方式的粗略概述。

我们有一项任务。我们有我们的模型。模型拥有一组特定的工具，然后我们有某种计算环境。最后，我们有一个验证器（verifier）。模型基本上尝试通过使用不同的工具来解决该任务。接着，根据验证器给出的分数，我们对模型进行更新。但是没有人指示模型使用哪些工具，它基本上仅仅接收那个奖励反馈。

<details><summary>Original English</summary>
So how do models get good at work? And that's a rough overview on how post- training works.

So we have a task. We have our model. The model has a certain set of tools and then we have some kind of compute environment. And at the end we have some verifier. And the model tries to basically solve that task to use different tools. And then based on the score from the verifier, we update the model. But no one is telling the model which tools to use. And basically it only receives that reward feedback.
</details>

如果我们看两个关于模型如何借助工具执行某些任务的例子：路径 A 中，我们有专门用于文件系统控制的工具。大家大概都用过代码编写 Agent，也见过 read_file 调用或 edit_file 调用。这是一种实现方式。而另一种实现方式则是仅使用单个内联 bash 脚本来完成所有更改。

在左侧路径中，对代码仓库进行相同的更改大约需要 10 个轮次；相比之下，右侧路径仅使用 bash 只需要 2 个轮次。这同样体现在我们所需的 token 数量上：左侧路径消耗的 token 大约是右侧路径的 10 倍，而它们最终为模型实现该任务所达成的效果完全相同。

<details><summary>Original English</summary>
So if we look at two examples on how a model can do a certain tasks with tools, we have the path A where we have dedicated tools for file system control. So you all have probably used uh coding agents and you have seen a read uh file call or an edit file call. So that's one way of doing it and the other way of doing it would be just using a single inline bash script for all of the changes.

So on the left side we roughly need around 10 turns to make the same changes to a coding um repository compared to the two ch uh turns on the right side just using bash and it also reflects in the amount of tokens we need. So the left path takes around 10x more tokens than the life uh the right path and it's doing the exact same thing uh at the end for the model to achieve that task.
</details>

所以在我的实验中，大约每 6 个月我都会尝试从头构建一个新的代码 Agent 工具框架，并且我总是问自己：好的，为了完成相同的任务，我到底真正需要多少工具框架？对模型来说哪些是开销、哪些我们已不再需要？

如果我们回顾一下 2025 年的代码 Agent 工具框架，我们当时大约有 10 到 15 到 20 个工具。我们有专门用于文件编辑的工具，有专门用于规划、用于待办事项列表的工具，而且我们在系统提示词中还写了大量专门的规则，指导模型该做什么、不该做什么。这当然有效，但自那以后我们做出了很多改变。

在我的实验中——第一个实验大约是在两年前的 2 月份做的——当时我们还没有真正意义上的 Agent，对吧？我们当时用的是工作流，基本都是预定义的步骤。当时 RAG 应用非常流行，我们有一个规划器，有搜索，对检索到的内容进行反思，然后生成回答。之后我们开始看到第一代 Agent，针对各种细粒度操作配备了非常多的工具。随之而来的是代码编写 Agent，配备了大约 10 到 20 个工具。

<details><summary>Original English</summary>
So in my experiment every roughly 6 months I try to build a new coding agent harness from scratch and I always ask myself okay how much of the harness do I really need to achieve the same tasks and what is overhead to the model and we no longer need.

So if we look at the coding agent harness which um from 2025 we had a roughly around 10 to 15 to 20 tools. We had dedicated tools for um file editing. We had dedicated tools for planning, for to-do lists and also we had a lot of dedicated rules in our system prompt which told the model what to do and what not to do and that worked of course but since then we made a lot of changes.

So in my experiments uh first one was done roughly now two years ago uh in February where we did not really had agents right we had workflows we basically had predefined steps rock applications back then were very popular we had a planner we had search we reflected on whatever was found and then we generated an answer then we started to see our first agents we had many many different tools for all sorts of fine cular actions um and then came the coding agents where we had those roughly 10 to 20 tools
</details>

现在，在我最近的实验中，我试图探索：好的，如果我只为 Agent 提供单一工具，会发生什么？结果对我而言相当令人兴奋。

这个单工具 Agent 的工作方式与其它所有 Agent 相同，区别仅在于它只有一个工具，那就是 bash。模型可以使用该工具来完成各类任务。而且这个 bash 工具非常简单：它在单独、干净的子 shell 中运行，支持 command 参数。我还添加了一个 description，以便更直观、更轻松地向用户展示模型实际在做什么；此外还有一些异步参数。

基本上，当模型运行 bash 命令时，该参数会告知模型：好的，如果命令运行时间超过指定的毫秒数，工具调用就会解析返回，模型将收到一个本地文件句柄，后续可以借此查看进程是否仍在运行。例如在进行各类 Web 开发时，这就非常实用。单一 bash 工具实际上适用于我们使用 Agent 进行的所有操作，因此我们可以处理长时间运行的工作——可以在前台启动，然后自动转入后台。模型会收到某些文件

<details><summary>Original English</summary>
And now in my last experiment I tried to see okay what's going to happen if I provide only one tool to my agent and the outcome is was pretty exciting to me.

So this one tool agent works the same way as every other agent except that it only has one tool which is bash and the model can use that tool for any sorts of task and the bash tool is very simple. So it runs in a se a se separate clean subshell and it supports the command argument. I also added a description so that it's nice and easier to display to the user what the model is actually doing and then like some async parameters.

So basically when the model runs a bash command uh the parameter tells the model okay if it is uh the command longer running than this um milliseconds it's being um that the tool call resolves and the model receives uh a local file handle where it can look up later okay if the process is still running that's very interesting if you do like all sorts of like uh web development for example and the single batch tool actually works for all of the things we are using Asian so we can have longunning work where we can start on the foreground and then automatically move it to the background. The model receives some file
</details>

<!-- chunk 14/50 -->

handle，而且既然它可以使用 bash，如果我们把它存入文件系统中，它就能读取正在流式传输的日志。如果 Agent 本身就是一个 CLI，它就可以利用 bash 调用自身。因此，实际上根本不需要为它创建子 Agent 工具，因为它可以调用自己。当然，我们也不需要专门的规划或记忆工具，因为我们有现成的文件系统。我们可以为模型提供一些上下文，这样模型就可以利用文件系统并使用 bash 工具来跟踪自己的工作进度。

<details><summary>Original English</summary>
handle and since it has bash available, if we store it to a file system, it can read the logs which are being streamed. If the agent itself is a CLI, it can call itself using bash. So there's practically no need to create sub aent tools for it because it can invoke itself. And then of course we don't need dedicated planning or memory tools because we have our file system available. We can provide some context to the model. So the model can keep track of its own work with the file system and using the bash tools.
</details>

当然，除了工具之外，我们还有系统提示词，并且与工具类似，系统提示词随着时间的推移也在不断演进。这里的每个点大致代表约 100 个 token，你可以看到在 2025 年中期的代码生成 Agent 中，我们每次请求都需要发送大量的上下文。当然，这一点后来也得到了改进，这里的情况也类似：好吧，我究竟需要为我的 Agent 提供什么才能让它成功运行，以及过去我们拥有的所有系统信息和细节中，有哪些现在基本上已经成为模型的一部分了？那么，测试框架到底起到了多大帮助，又有多少成了阻碍呢？为了弄清这一点，我针对许多不同的 Agent 测试框架配合多种不同工具运行了大量的评估。

<details><summary>Original English</summary>
In addition of course to our tools we have system prompts and similar to tools uh system prompts evolved over time. Um every dot here is roughly around 100 tokens and you can see that coding agents mid2025 had a lot of context we needed to send in every request. Of course, this also improved and similar story here is like, okay, what do I really need to provide to my agent to make it successful and work and what of all of the system information and details we had in the past are now basically part of the model. So, how much of the harness helps and how much is in the way and to find that out I was running a lot of different evaluations of a lot of different agent harnesses with a lot of different tools.
</details>

这里我想展示一个例子，它是用 Gemini 4 Carbon 针对 deep sv 的一个评估任务完成的。比如：好吧，如果我为现有的代码生成 Agent 工具提供 read、write、search、grep，以及我仅使用 bash 的工具，会发生什么？我认为大家可以非常清楚地看到，顶上的那条线消耗了多得多的 token、多得多的轮次以及多得多的时间来完成相同的任务。其中非常显眼的一点是：好吧，读取操作在最开始是并行完成的，但一旦我们开始进行代码修改，就会看到相同的行为，即模型逐轮进行单次编辑，这当然会消耗大量的时间和大量的 token。

<details><summary>Original English</summary>
And one example I like to show here which was done with Gemini 4 carbon from an eval task from deep sv is like okay what happens if I provide my existing coding agent tools with read write search crap and my bash only tool and I think you can pretty clearly see that the top line is taking a lot of more tokens a lot of more turns and a lot of more times to achieve the same task and what stood out really well is that Okay, reading is done in parallel in the beginning, but as soon as we start going into making code changes, we see that same behavior that the model is making turn by turn a single edit, which of course consumes a lot of time and a lot of tokens.
</details>

### 测试框架评估与效率对比

那么，在更大的范围来看，情况又是怎样的呢？我自己有一套针对编码知识工作和终端命令的大约 350 个任务的评估集，这里全部由 Gemini 4 Argon 以及四种不同的 Agent 测试框架运行。一种是纯 bash 测试框架，然后好吧，使用 bash 我们仍然面临那个问题，即我该如何读取图像，对吧？如果我不能 cat screenshot.png，它会返回二进制内容，这会填满我的上下文，而模型却看不到图像。我添加了一个 view media 工具，它基本上能以模型可以看清的方式返回图像。然后我们有两个针对文件系统操作带有结构化工具的不同 Agent 测试框架。如果我们只看得分这一列，它们看起来都大致相同，对吧？所以如果我们只通过看得分来评估我们的模型和 Agent 测试框架，我们选择其中哪一个基本上都没有太大区别。当然，得分上存在轻微的差异，但我对每个任务只运行了一次，所以可能只是一些噪声，或者可能是别的什么原因。因此，针对每个测试框架你可能需要多运行几个样本，但得分看起来大致是一样的。

<details><summary>Original English</summary>
So how does this look at a protoscope? So I have my own eval set of around 350 tasks for coding knowledge work uh and terminal commands all run with Gemini 4 argan here and four different agent harnesses. One is the bash only harness and then okay with bash we still have that issue on how can I read images right if I'm I cannot cut screenshot.png it would return a binary and it will fill my context and the model cannot see the image. I added uh a view media tool which basically returns the image in a way the model can see. Then we have uh two different agent harnesses with structure tools uh for file system operations. And if we just look at the score column, all of them look roughly identical, right? So if we would just evaluate our model in ancient harness looking at the score, it would basically not really matter which one of those we would pick. Of course, there's a slight variance in the scores, but I only ran uh each task one time. So, might be just some noise or maybe something else. So, you would probably need to run a few more samples per per harness, but the score looks roughly the same.
</details>

那么我们现在怎么知道应该选择哪个测试框架呢？如果我们只看展示的所有评估，它几乎总是在关注得分。但如果我们看 token 列，或者更进一步看每个任务花费的美元数，情况就开始发生改变了。因此，每个任务的 token 数量正在降低。有趣的是，如果我们仅仅使用 bash，缓存命中率也会随之增加。所以如果我们就以 bash media 作为基准来进行对比，与更复杂、工具更多的 Agent 测试框架相比，任务成本几乎便宜了 2 倍。而如果我们只盯着得分看，是无法发现这一点的。为了向大家展示几个例子，我准备了一些演示。

<details><summary>Original English</summary>
So, how would we now know which harness should I choose? If we just look all at all of the evol being shown, it's always mostly about score. But if we look at the token column or even more at a dollar per task, there's a picture which is changing. So the token per task is getting lower. Interestingly, if we just use bash and then also the cash hit rate increases. So if we just compare like the bash media as the the baseline, the tasks are almost 2x cheaper compared to more complex more tools agent harnesses. And we would not see it if we just look at the score. And to show you a few examples, I prepared some demos.
</details>

这里我使用的是 pi 测试框架，它让你基本上可以非常简单地定义想要使用的工具。对于大约 6 个月前发布的 3.5 Flash，我在使用所有工具（即 pi 开箱即用的任何工具）的情况下使用了相同的提示词。然后是纯 bash 的情况，接着是对于 Carbon……抱歉，是对于使用了默认工具的 Carbon，以及使用了纯 bash 的 Carbon。由于我们现在大概只有 20 分钟左右，这些正在运行，所以我把这些全都录制了下来，并点击了这里那个非常棒的加速按钮。我们在右侧可以看到，同样的范式基本适用：当模型变得更好时，它们大致需要更少的工具。因此在 3.5 Flash 中，我们看到使用默认工具与纯 bash 相比，模型调用次数是一样的。所以我们拥有相同数量的工具调用，并且 token 数量也大致相同。如果我们看执行轨迹，可以看到对于纯 bash，我们有一些用来读取不同文件的 cat 命令，有一些用于进行修改的内联脚本，然后还有一些 git 修改操作。如果我们看默认工具，可以看到情况大致相同：我们有 read file 命令，使用了 edit 工具，然后有一些 git 命令来做出这些更改。

<details><summary>Original English</summary>
So here I'm um using the PI harness, which makes it super simple to basically define what tools you want to use. I have the the same prompt for 3.5 flash, which we released roughly 6 months ago, uh for all tools. So like whatever pi ships out of the box. Then we have it for uh bash only and then we have it for carbon and uh sorry for carbon with the default tools and then with with um bash only. This runs now since we only have roughly around 20 minutes. I recorded all of that and clicked that very nice accelerate button here. And what we can see on the right side is that the same paradigma basically applies. when models get better, they roughly need less tools. So with 3.5 flash, we see with the default tools uh compared to bash only, we had the same amount of model calls. So we had the same amount of tool calls and we had roughly the same amount of tokens. And if we look at the traces, we can see for bash only, we have some cut commands to read different files. We have some inline scripts to make uh changes and then like some git changes. If we look at the default tools, we can see roughly the same. We had uh read file commands. We used the edit tool and then had some git commands to make those changes.
</details>

如果我们现在看使用了默认工具的 Carbon，它使用的工具调用和模型调用已经少得多了。所以它基本上是在并行开展工作，但也在努力减少调用。例如，我们仍然有相同的写入、读取调用以及编辑调用。但如果我们深入观察 bash，情况就开始变得有趣了，在 bash 中，我们的工具调用和模型调用甚至更少，这里有趣的部分在于，模型编写了一个单独的 Python 脚本来一次性完成所有这些更改，而不再需要调用多个工具。因此，如果我们进一步探讨这对这里的 Carbon 意味着什么，以及 bash 是如何发挥效益的，那就是模型变得越好，或者它获得的推理能力及类似的能力越强，bash 就能越好地帮助模型在单次调用中链接更多命令。对于 Carbon，每次 bash 调用大约执行 2.2 到 3.7 个命令，而对于 Flash，只有 1.3 到 1.8 个命令。因此我们看到，为了完成相同的任务，Carbon 所消耗的 token 减少了多达 3 倍，相比于我们需要使用同样那些工具的情况而言。

<details><summary>Original English</summary>
If we now look at carbon with the default tools, it already used way less uh tool calls and model calls. So it it's basically doing work in parallel but also trying to reduce it. So we had for example the still same for write read calls and also the edit calls. But what starts to get interesting if we are going to look into bash and in bash we had even less tool calls and model calls and the interesting part here is that the model writes a single Python script to make all of that changes in one go and no longer needs to call multiple tools. So if we go further what does it means in terms for for carbon here and how bash pays off is that uh the better the model gets or the more reasoning and like capability it gets bash helps the model to be able to chain more commands in the single call for carbon it was roughly 2.2 to 3.7 uh commands per bash call and for flash it was only 1.3 to 1.8 eight. So we are seeing up to 3x less tokens uh by carbon to achieve the same task compared to having the same tools we need to use.
</details>

再看另外两个例子也是同样的情况：左边是使用默认工具的 Carbon。我们可以看到我们的代码生成 Agent 工具带有写入、带有编辑，我们看到好吧，它在第 2 轮做了一些并行工作，在第 3 轮和第 4 轮做了一些并行工作，然后我们完成了所有的更改；而在右边它只有 bash 工具的地方，它使用 Python 编写了一个内联脚本，以极少的 token 同时完成了所有这些更改。如果我们对比 Gemini 3.5 Flash 和 Gemini 4 Carbon，结论也是一样的：仅使用 bash 的 Flash 并不会去链接那些命令。所以在这种情况下，拥有读取工具、写入工具、编辑工具和 bash 工具，还是仅仅只有一个 bash 工具，其实并没有太大影响，因为 3.5 Flash 过去总是将 bash 用于单轮命令，因此它在读取上用了一个单轮，在写入上也用了一个单轮。但如果我们看 Carbon（在这个例子中是完全相同的任务），它需要的等待轮次更少，因此在读取方面不需要去完整读取所有不同的文件，它仅仅使用 ripgrep 和类似的一些智能搜索来定位我们需要做出更改的地方，然后它编写一条单独的 Python 内联 bash 命令一次性完成所有这些编辑，为我们节省了大量的 token。

<details><summary>Original English</summary>
So two more examples to look at it as well is like we have on the left side carbon with the default tools. So we see our coding agent tools with write with edit and we see okay it does some parallel work in turn two some parallel work in turn three and four and then we have all of the changes and on the right side where it just has the bash tool it uses Python to write an inline script to make all of that changes at the same time with much less token and the same counts for if we compare Gemini 3.5 flesh to Gemini 4 carbon flesh with bash only is not chaining those commands. So here it it's not really it doesn't matter if I'm having a a retool a write tool edit tool and a bash tool or if I have just a bash tool because 3.5 flesh used to use bash for single turn command so it had a single turn for reading it had a single turn for writing but if we look at carbon which in here in this example is the exact same task it needs less weight turns so the reading is not needed to read all of the different files and uh completely it just uses rip trap and like some intelligent searching to find where we need to make changes and then it writes a single Python inline bash command to make all of those edits in one go saving us a lot of tokens.
</details>

那么这给我们带来了什么启示呢？模型将继续蚕食测试框架的功能，而且我非常确信，2027 年的重点也将更多地放在解决一项任务需要多少 token 上。即使是在我们对 Argon 和 Carbon 之间所做的少量改进中，更好的模型在每个任务上需要的 token 也更少，这对我们所有人来说当然是非常令人兴奋的，因为这样我们就可以更多地去使用它。此外，测试框架所提供的内容也非常关键，如果我们仅仅关注准确率，可能根本察觉不到这一点。开始衡量 token 效率也是极其重要的，因为既然我们现在的模型已经非常出色，各种测试框架在准确率上看起来可能别无二致。因此，如果你的测试框架使用起来更为复杂，模型会变通处理，会找到变通方案，但需要更多的轮次和更多的 token 才能达到相同的结果，还有随之而来的后续开销。所以我打算在 6 个月后尝试进行同样的实验，而目前我们看到的趋势正在慢慢升温，至少在社交媒体和类似……

<details><summary>Original English</summary>
So what does it bring us? Models will keep eating the harness and I'm pretty sure that 2027 will also be a lot more about how many tokens do we need to solve a task. Even for the few uh improvements we made between Argan and Carbon is the the better model needs less tokens per task which of course is very exciting for all of us because then we can use it more and also it matters a lot what the harness provides and we will might not see it if we just look at the accuracy. It's also very important that we start measuring the token efficiency because harnesses can look the same on accuracy because our models are now very good. So if your harness is more complex to use the model will work around it will find solutions around it but needs more turns and more tokens to achieve the same results and then also what comes afterwards. So I will try to do the same experiment 6 months from now and currently the trend we see slowly um rising at least on like social media and like the
</details>

<!-- chunk 15/50 -->

行业的趋势可能是，我们会回到某种代码模式（code mode）工具，不再写 Bash 命令，而是直接写 TypeScript 或 Python，MCP 也会重新受到重视。我非常喜欢 MCP，他们正在做出重大改进，让它变得更容易使用。对于所有代码模式的工作来说，特别有意思的一点是，现在的 MCP 服务器允许返回结构化输出，这样模型就能写出更好的脚本，在单轮交互中采取更多行动；这也让我们能在安全性方面做更好的代理控制。因为 Bash 调用非常难以理解，但如果我在 TypeScript 中有一层抽象层，我就能监控正在执行的所有命令，确保它们是安全的。要建立一种机制，在模型删除你的代码之前先去删除你的代码。给你的模型配备一台电脑，而不是一个工具箱。当新模型发布时，我绝对建议大家尝试跳出思维定势，更有抱负一些，真正去看看：如果我去掉整个脚手架（harness），只给它一个工具，会怎么样？另外也请扫描这个二维码，大家会获得免费额度。我们会在 AI 工程活动结束后发给大家，用于试用 Carbon，以及试用新的 Gemini Decisions API。所以如果大家今天有时间，我真的非常推荐去了解一下新的 Decisions 模型 Carbon。非常感谢大家的时间。

<details><summary>Original English</summary>industry is that we might go back to some code mode tool that we instead of writing a bash commands that we write TypeScript or Python directly that MCP will come back. I'm a big fan of MCP and like they are making great changes to make it more uh easy easily usable especially uh interesting for all of that code mode work is uh MCP servers now return allow you to return structured output so the model can write better scripts to take more actions in the single turn and it's also allows us to do some better proxy around the security because bash calls are very hard to understand but if I have some abstractive layer in typescript I can uh watch all of the commands being um executed and make sure those are secure and for you build to delete your code before the model does. give your model uh to a computer, not a toolbox. And when a new model ships, I definitely recommend you um trying to think a little bit outside of the box, be more ambitious, try to really see, okay, what if I remove my complete harness and just give it one tool and then also please scan the QR code. You will get free credits. Uh we will send them out after the AI engineering event to try out Carbon and also to try out the new Gemini decisions API. So if you have some time today, I really can recommend checking out the new decisions model carbon and thank you for your time.</details>

Heat.

Hey, heat. Hey, heat.

Hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey, hey.

Heat.

Heat.

Heat. Heat.

Heat.

Heat.

Heat. Hey. Hey. Hey.

Heat. Heat.

Heat. Heat.

Heat.

Hey, heat. Hey, heat.

Hey, hey, hey.

<details><summary>Original English</summary>Heat.

Hey, heat. Hey, heat.

Hey,

hey, hey, hey, hey, hey, hey, hey, hey,
hey, hey,
 hey,
 hey,
 hey, hey,
 hey,
 hey,

hey, hey,
 hey.

Heat.

Heat.

Heat. Heat.

Heat.

Heat.

Heat.
 Hey. Hey. Hey.

Heat. Heat.

Heat.
 Heat.

Heat.

Hey, heat. Hey, heat.

Hey,
 hey, hey.</details>

### 构建面向下一代智能体的基础设施

好的。来到这里我感到非常兴奋。我叫 Ankit，来自 Databricks，在那里负责 AI 基础设施方面的工作。今天我将要分享智能体工作力量的兴起，以及我们如何构建自身的智能体基础设施，来支持我们所认为的下一代智能体。

<details><summary>Original English</summary>All right. Uh well, super excited to be here. My name is Ankit. I'm from Data Bricks. Uh I work on AI infrastructure there. And today I'm going to talk about uh the rise of the agent workforce and how we're building our agent infrastructure to support what we think is the next generation of agents.</details>

我想先退一步，思考一下我们是如何帮助计算机在其他事情上变得擅长、甚至超越人类的。我从小经常玩的游戏之一就是国际象棋。这是计算机很久以前就远超人类的一个绝佳范例。但我认为去思考为什么会发生这种情况、以及我们今天如何应用这些经验教训是很重要的。在高层次上总结一下，当时人们付出了大量工作。智能体能够做到的、或者说计算机能够做到的最重要的一点，就是比人类更有效地探索决策空间。对于大多数复杂问题，其实都有许多种不同的解决途径。在每一个回合，你基本上都能想到可以做出另外三个决策。实际上，正是对那个空间的探索，把我们所有人都卷入其中。我们所有解决棘手问题的人，都在一个搜索空间里寻找：什么是出色的产品？这个数学问题的正确解法是什么？等等，对吧？我认为我们已经看到 Anthropic、OpenAI 和 Google 等实验室在解决规范良构（well-formed）的问题上取得了一些非常令人振奋的进展。如果以国际象棋为例，它可以被有效地建模，你可以评估自己的局面，实际上可以进行对弈模拟，可以尝试不同的走法，并安全地考虑所有不同的备选方案。同样地，对于数学问题，智能体通常非常擅长解决的那些，你实际上可以验证得到的结果是否正确。那么我们该如何把这种思维方式应用到我们日常实际面对的问题中呢？

<details><summary>Original English</summary>I wanted to start by taking a step back and and thinking about how we help computers become good at other things uh better even than humans. And one of the games I grew up playing a lot was chess. Uh it's one of the great examples of something where computers became way better than humans a long time ago. But I think it's important to think about why that happened and how we can apply those lessons today. One of the biggest, you know, to summarize at a high level, a lot of work went into it. The biggest thing that agents were able to do, that computers were able to do was explore the space of decisions much more effectively than humans. For most complex problems, there's actually a bunch of different ways you can solve the problem. And at each turn, you can kind of think of three more decisions that you can make. And really, it's the exploration of that space that all of us are engaged in. All of us who solve hard problems are engaged in the search space for what's an amazing product, what's the right solution to this math problem, and etc., right? uh and I think we've seen some really exciting progress from the labs like Enthropic, OpenAI and Google on solving problems that are wellformed. So, you know, if you think about chess, it can be modeled effectively. You can evaluate your position. Uh you can actually play simulate it. You can try different moves and safely think about all the different alternatives. Similarly, with math problems, often the ones that agents are really good at solving, they you can actually verify if you got the result right. uh and how do we then take that mindset and apply it to the problems that we actually face day-to-day.</details>

我想这里的各位很多人都是工程师，那我们就把它落到工程领域来聊一聊。如果在 AI 出现之前的时代，大多数人都是想着解决单一问题，在写代码的那段时间里，他们基本上在这个问题上是单线程的。作为一家公司或一个产品，如果你想解决更多问题，就会招揽更多的人；而智能体最基础的版本，只是帮助那位工程师创造杠杆效应。现在你可以同时在三件事上保持单线程，最终这有助于你探索新产品的想法、更快地交付、更快地迭代，这显然非常令人兴奋。但这其实还远远没有达到我们在国际象棋或任何其他这类问题上获胜所需要做到的程度。我们在绝对前沿看到的是这样一些智能体团队：它们能够通过更有效地探索决策空间来取得重大进展。那么，我们该如何走向这样一个实际拥有协调一致尝试解决问题的智能体团队的世界呢？这其实相当复杂，而且我们认为这需要稍微不同类型的基础设施。

<details><summary>Original English</summary>I think like let's a lot everyone here is an engineer. So let's take it to engineering for a bit. Uh I think you know if you take it to the preai days uh most people think about solving a single problem and they're kind of singlethreaded on that problem for the time that they're writing code on it. uh and you know as a company if or a product if you wanted to solve more problems you brought in more people and the very basic version of agents just helps create leverage for that engineer. Now you can be singlethreaded on three things at the same time and ultimately that helps you explore new product ideas, ship faster, iterate faster and that's obviously very exciting. But it's it's not actually close to what we needed to do to win at chess or any of these other problems. What we're seeing at the absolute frontier are these teams of agents that are able to make significant progress by exploring the decision space more effectively. So how do we move towards that world where we actually have these teams of agents that are coherently attempting to solve problems? It's actually quite complex and we think it requires a little bit different type of infrastructure.</details>

具体而言，我认为一个需要问的重要问题是：我们如何给智能体一个逼真的世界去探索？因为在其他问题中，我们能够非常有效地帮助定义那个世界。但即使是在软件工程中，我们实际上也非常难以做到这一点。就拿如今迈向软件工厂的趋势来说，对吧？在那里你脱离了智能体，实际上是在调度操作一批致力于解决某个问题的智能体。你如何验证这些智能体是有效的呢？比如在以前，你有一个分支，你从 main 分支拉出自己的 PR 分支，可能有一个智能体在这个 PR 上工作，你有一些合理的断言说明这大致是一个模拟，或者有一些测试之类的东西帮助指导开发。但如果你实际上每分钟都在合并数十个甚至更多的 PR，对吧？如果你去推演智能体工厂构建代码和软件的未来，你的 PR 从你拉分支的那一刻起就已经过时了。从你开始的那一刻起，你就已经过时了。所以这需要一种不同的思考模式：我们如何去验证这些东西？你实际上可能需要把大部分验证移到合入之后（postmerge）。

<details><summary>Original English</summary>Specifically, I think an important question to ask is how do we give agents a realistic world to explore? Because in other problems, we're able to help define that world very effectively. But even in software engineering, we actually really struggle to do that. Like just consider this movement towards software factories, right? Where you're away from the from the agents and you're actually operating a bunch of agents that are working on a problem. How do you validate that those agents are effective? Like before you had a branch uh you had main, you branched your PR off of that. Maybe you have an agent working on that PR and you have some reasonable assertion that this is kind of a sim, you know, you have some ass like some tests or something like that that help you guide your development. But if you're actually merging tens of PRs a minute or even more, right? Like if you play out the future of factories of agents building code and software, your PR is just out of date the moment you branched. The the moment you started, you're already out of date. So it demands a different mindset of thinking of how do we verify these things? You actually might want to move most of your verification to postmerge.</details>

这就引出了我这个稍微有点激进的想法。我认为我们不应该尝试去编写成百上千个单元测试。相反，我想探索这种模拟现实的想法。我能否为我的智能体如实还原在现实世界中、在我的生产环境代码中、在我的生产环境智能体中实际存在的状态，并让它在此之上工作？一旦你能做到这一点，你实际上就可以规模化地去实现。如果你找到了一种模拟现实的方法，那么你实际上就可以跨越许多不同的探索途径去展开工作。

<details><summary>Original English</summary>And so that kind of brings me to this a little bit radical idea. I I don't think we should try to write hundreds or thousands of unit tests. Instead, I want to explore this idea of simulating reality. Can I give my agent a faithful reproduction of what's actually there in the real world in my production code in my production agent and let it work on that? And with when you can do that, you can actually do that at scale. If you find a way to simulate reality, then you can actually do that across lots of different explorations.</details>

在 Databricks，人们在我们平台上做的一件大事就是构建数据管道。Databricks 上有成万上万个数据管道，而管道发生的最大问题就是它们会损坏出故障。在智能体时代，人们想要的是用智能体来修复这些损坏的管道，因为这些都是由于管道故障引发的严重业务问题。如果管道坏了，企业那天就无法运转，所以这会变成重大的紧急事件。

<details><summary>Original English</summary>At data bricks, one of the big things that people do on our platform is build data pipelines. We've got tens of thousands of data pipelines on data bricks. Uh and the biggest problem that happens with pipelines is that they break. Um and in this era of agents, what people want is they want to fix those broken pipelines with agents because these are serious business problems that they that are, you know, uh caused by a broken pipeline. If a pipeline breaks, that business can't operate that day. Uh and so this becomes a major emergency.</details>

但你实际上如何用智能体来验证这一点呢？你会信任它在你的生产数据管道上操作吗？这是相当危险的，因为写入操作可能并非幂等……故障。它只是部分损坏。我们开始做的事情之一就是构建在可分支基础设施（branchable infrastructure）之上。我们所做的就是对整个数据平台进行分支。我们对表、算力、治理规则进行了分支，给智能体提供了一个可以让它们真正在数据平台上操作并探索不同假设的场所。这些假设可以非常有抱负，比如：我能否去调查上游管道是否健康？也许我可以通过修改管道代码并再次运行来做到这一点。在任何合理的数据平台上，除非有一群工程师介入审查并确保绝对安全，否则你是不会对上游管道这么做的。在我们分支化的数据平台上，你现在实际上可以这样做了。所以它可以去调查许多不同的事情。我们就可以利用我们的智能体并行调查 10 个想法，真正就其是否修复了真实的数据管道得出可靠的结论，然后将做出的假设、做出的断言反馈给主智能体或人类。而我们之前看到发生的情况是

<details><summary>Original English</summary>But like how do you actually validate this with an agent? Do you trust it on your production data pipeline? It's pretty risky because writes might not be identy broken. It's just partially broken. One of the things we started doing was building on top of branchable infrastructure. And so what we did was we branched the entire data platform. We branched the tables, the compute, the governance and we gave the agents a place where they can actually play with the data platform and explore different hypotheses. And these hypotheses can be ambitious like can I investigate that the upstream pipeline is healthy? Maybe I can do that by changing the pipeline code and running it again. In any reasonable data platform, you wouldn't do that with an upstream pipeline unless you had a bunch of engineers take a look at it and make sure it was super safe. with our branched data platform. You can actually do that now. So it can investigate a bunch of different things. So we can investigate 10 ideas in parallel with our agents actually get to a faithful conclusion about whether it fixed the real data pipeline and then make that assumption made that assertion back either to a main agent or to a human. And what we saw before was happening was</details>

<!-- chunk 16/50 -->

人们原本只是让大语言模型给我们返回文本，由人工来看一眼，觉得这可能是一个有意思的推论，然后去以某种方式应用那个推论。最终，这变成了更多是通过 AI 辅助来修复数据流水线。但我们真正想达到的，是针对这类问题实现无需人工干预的全自动处理。而如果没有这种支持分支的基础设施，我们很难做到这一点。那么我们到底是怎么实现的呢？我会在本次演讲中稍微聊一聊。

<details><summary>Original English</summary>
that people would just like LLM would give us text back some human would take a look at it and be like okay this might be an interesting theory. then they would go apply that theory in some way. And ultimately that became more of this like AI assisted version of fixing the data pipeline. But really where we want to go is is is hands-off full auto for this kind of problem. And we were we were struggling to do it without this branchable infrastructure. So how do we do it? I'm going to talk a little bit about that in this talk.
</details>

我们把它构建在我们的 Postgres 原生智能体平台之上，该平台最初基于 Neon 数据库，它是一个支持分支的数据库，为我们提供了一个真正可同时用于服务和智能体的单一位置。接着，我们加入了一堆非常核心的智能体原语，使我们能够构建不同类型的复杂智能体。大家可能对这些原语都很熟悉，比如记忆、沙箱、文件系统，以及托管这些智能体的方式。借助这些底层原语，我们可以进行构建。但关键在于，我们将它们全部做成了可分支的。因此，你可以为我们自己把构建在该平台上的一切现实环境进行分支。

<details><summary>Original English</summary>
Uh we built this on top of our Postgress native agent platform which started with the Neon database which is a branchable database that gives us a single place that we can actually use for our services and for our agents. And then we added in a bunch of really core agent primitives that allow us to build sophisticated different types of agents. Uh and those are ones that are probably familiar to all of you. Things like memory, things like sandboxes, file systems, and ways to host those agents. And these low-level primitives we can build we can build with them. But the key is that we made just all of them branchable. So you can branch the entire reality of stuff that's built on this platform for us for ourselves.
</details>

那么我们到底是怎么做到的呢？让我来逐个场景讲解一下。首先就是数据库。大家知道，我们可以拿应用服务来举例，但在这里我甚至只想谈谈为智能体存储对话状态这件事。当你分叉或分支一个智能体时，你可能其实希望继承历史记录。甚至如果你有一队智能体，你可能希望让团队中的某个成员能够访问团队其他成员正在做的事情。我们发现数据库是实现这一目标的便捷抽象。关键在于，当分支出来的智能体收到新回复时，并不一定会改变另一个智能体的任何东西。而这之所以成为可能，是因为 Neon 拥有支持分支的数据库。

<details><summary>Original English</summary>
Uh so how do we actually do that? Well, let me walk it through like kind of case by case. The first thing is just the database, right? And you know we can take an example of application services. But here I'm going to talk about just even storing the conversation state for for an agent. When you fork or branch an agent, you actually might want to inherit the history. And you might even if you have a team of agents give access to a given member of that team to what the other members of the team are doing. Uh and we found the database to be a convenient abstraction for this. Uh the key was that hey like when a new reply comes in on the on the branched agent it shouldn't necessarily change anything about the other one. Uh and this is possible because Neon has a branched database.
</details>

### 记忆系统与分支

但随后我们实际发现，智能体需要的不仅仅是结构化数据库。它们当然需要结构化数据库，但也喜欢编写所谓的“记忆”，从很高维度来看，这些记忆最终会编译为智能体的非结构化数据库。记忆的生成方式有两种：第一种仅仅是通过综合整理之前有人与它们进行过的上下文和对话；第二种则是由智能体实际显式地将内容保存到非结构化位置。这里的关键在于，你实际上希望合并并提炼这些信息。传入其中的信息非常庞大，如果你任由其自行发展，就会遇到陈旧性问题，遇到信息冲突，而所有这些都会对团队造成极其严重的损害。因此，我们设置了一个基本上在夜间“做梦”的机制，利用离线计算，由另一个智能体提取对话，主要标出存在冲突的地方，并合并团队各个成员写下的临时笔记，然后团队所有成员就都能实际从该记忆数据库中进行检索。

<details><summary>Original English</summary>
But then we actually found that agents need more than just structured databases. Of course they need structured databases but they also like to do this you know write these things called memories and memories are you know at a very high level they compile down to an unstructured database for agents. There are two ways that memories get generated. The first is just by synthesizing the context and the conversations that someone's already had with them and the second by agents actually explicitly saving content to an unstructured place. The key thing here is that you actually want to consolidate and distill that information. there's a ton of information coming in through there and if you just give that you know if you just let it kind of go on its own you have problems of staleness you have conflicts in the information and all of those can be extremely damaging to teams so we have this thing that basically dreams overnight we use offline compute uh and it takes the conversations a different agent essentially highlights things that are conflicts and consolidates the ad hoc notes that were written by various members of the team and then all members of the team can actually recall from that memory database.
</details>

你可以通过很多不同的方式来使用它。我们在 Slack 智能体内部使用它，而且例如在数据平台中启动一组并行智能体去排查深度故障时，我们也会用到它。那么，分支是如何融入其中的呢？在许多使用场景中，部分智能体会提议记忆，而目前尚不清楚这些记忆是能推广到更广泛的智能体群体，还是仅仅针对该特定智能体。因此，借助基于 Neon 数据库构建的记忆可分支数据库，我们实际上可以直接把该记忆提议在其中的某个位置，让该分支继续迭代，在必要时，我们可以在某个时刻找到将其合并回来的方法。

<details><summary>Original English</summary>
And you can use this in a bunch of different ways. We use this within our Slack agents, but we also use this when we're launching a parallel set of agents to investigate a deep issue, for example, in the data platform. Now, how does branching come into this? Well, some of the agents like in many of the use cases, they propose memories and it's not clear whether those memories generalize to the actual broader set of agents or if that's a specific thing for just that agent. And so with the branchable database for memory which is built on top of this neon database, we can actually just propose that memory somewhere in there and that branch can continue to iterate and at some point we can find a way to merge it back in if it's necessary.
</details>

我们发现这是一层重要的灵活性，因为如果不具备完全分支记忆的能力，我们发现要为一队智能体维护记忆是非常困难的，尤其是当我们提高并行度时。如果所有智能体都在追求不同的目标，实际可能会出现质量显著下降的情况。我喜欢把它想象得有点类似于动态规划。如果你已经探索了一条探索分支，然后另一个智能体刚好踏上了同一条路径，总是重新探访那条路径是非常有害的，但有时你又确实想这么做，因此提议记忆的能力对我们来说极其重要。

<details><summary>Original English</summary>
uh we found this to be a flex an important layer of flexibility because without the ability to completely branch the memory we found it was very hard to maintain the memory for a team of agents especially as we increase parallelism you can actually experience like significantly reduced quality if all the agents are pursuing different goals uh I I I like to think a little bit of it as as like kind of similar to dynamic programming right if you've explored a branch of exploration and then you have a different agent that happens upon that same pathway It's very damaging to like always revisit that but sometimes you want to and so the ability to propose a memory is extremely important to us.
</details>

### 可分支基础设施的底层实现与沙箱

所有这类可分支数据库究竟是如何实现的呢？Neon 的实现方式是计算与存储分离。Postgres 的计算运行在某个独立的地方，然后我们在不同的层拥有共享的历史记录和存储，这使我们能够利用写时复制（copy-on-write）来进行分支。因此，当数据库有分支版本时，计算 A 的写入实际上可以与计算 B 分离，而这正是允许我们在该数据库之上构建这些应用的核心基础设施层。

<details><summary>Original English</summary>
How is all of this kind of branchable database possible? Well, the way that Neon does is it is it separates compute from storage. Compute uh for Postgress is running in some separate place and then we actually have the shared history and the storage in a different layer and what that lets us do is copy on write for branching. So when we have a branched version of the database, you can actually have A's uh you know compute A's rights separated from compute B and that's the kind of the core layer of infrastructure that allows us to build these applications on top of that database.
</details>

但接着我们发现，很明显智能体远不止是存储，仅有存储分支是不够的。我们还发现，智能体在沙箱中运行时，喜欢对事物做笔记、写下脚本，并利用这些脚本去对各类问题进行实际迭代。这是我发现的智能体最令人兴奋的事情之一：它们能够将原本可能用于测试代码等类似场景的能力进行泛化，并利用同样的构件去解决其他更广泛的通用问题。

<details><summary>Original English</summary>
But then we found you know obviously agents are far more than storage and and branching storage wasn't enough. We also found that as they were running in sandboxes, agents like to take notes on stuff and write down scripts and use those to actually iterate on various kinds of problems. It it it's one of the most exciting things about agents that I've found that they are able to generalize this capability that's needed maybe for testing code and and things like that and solve other more broader general problems using that same con construct.
</details>

但当你对其进行分支时，实际上需要给未来的智能体提供类似的上下文。我们发现，如果在启动分支智能体时没有带上该智能体最初拥有的相同文件，效果就是不如之前。例如，当你与某个智能体一起排查宕机事故时，你可能会有笔记和方案，而该智能体未来的分支可能会更新这些笔记，可能会发现新事物，但我们不希望这些内容回写，因为我们实际上是在同时探索 10 条不同的路径。

<details><summary>Original English</summary>
But then when you branch it, you actually need to give the future agent a similar context. If you we found that when we started the branched agents without the same files that that agent had to begin with it just wasn't as effective. So when you're investigating an outage for example with an agent you might have notes and plans and a future branch of that agent might update those notes. It might find new things but we don't want that to go back because we're actually exploring 10 different pathways at the same time.
</details>

因此，构建可分支的文件系统极为重要，这使我们能够构建所谓的“可分支沙箱”。因为这样一来我们能做的就是启动那个沙箱计算——这本身就是一个难题，今天我们不打算讨论这个问题——但该计算可以挂载到存储上，而且关键在于智能体实际上非常频繁地极度重度依赖文件。因此，将所有存储完全变成远程存储可能会非常痛苦。所以我们在这里构建的真正核心部分，是一个在我们所说的本地缓存与远程缓存之间进行同步的过程。这使得我们在取得进展时，如果要进行分支，实际上可以分支第二个沙箱，使用那个类似的文件系统，从而降低分支的延迟，同时保持常规智能体的合理性能。

<details><summary>Original English</summary>
Uh so building a branchable file system was extremely important and allowed us to build what we call a branchable sandbox because then what we can do is we can launch that sandbox compute and and that's a hard problem in and of itself. It's not one we're going to talk about today but that compute can be attached to storage and critically the agents actually really aggressively leverage files very often. Uh and so it can be very painful to make all your storage fully remote. Uh and so the really core piece of what we've been building here is a syncing process between what we call a local cache and the remote cache. Uh and then what that allows us to do is as we're able to make progress on that when we want to branch we can actually branch a second sandbox use that similar file system and it reduces our latency for for branching while also keeping performance of the regular agent reasonable.
</details>

### 工作状态分支与安全性

因此，从高维度来看，这使我们能够对整个工作状态进行分支。这也为我们提供了真正去实现这一目标的平台层。显然目前这还不够，你还会希望分支更多的东西。如果你是在软件之上构建，你也会想找到一种将软件也进行分支的方法。这正是我们思考的方向，对吧？比如，数据平台是在其中部分构件之上构建的，但我们在那里也已经能够分支更多的东西。不过对于仅仅用来构建智能体来说，我们对这一层感到非常兴奋。

<details><summary>Original English</summary>
So what this allows us to do at a high level is branch the entire working state. And this gives us the platform layer to actually go do that. Now this isn't obviously sufficient. You're going to want to branch even more. If you're building on top of software, you want to find a way to branch that too. And so this is along the lines of how we're thinking, right? Like we the data platform was built on top of some of these things, but there's a lot more that we've been able to branch there as well. Uh but we're really excited about this layer for just even building agents.
</details>

稍微脱离一下软件开发本身，我们许多人花大量时间思考的另一件事就是安全。退一步讲，我认为在现阶段，这可能是任何人销售的任何产品中最为重要的一点，因为当我们与其他人合作时，信任基本上是我们销售的最重要的东西。而且，随着智能体成为

<details><summary>Original English</summary>
And just to like kind of separate a little bit even from software development like another thing a lot of us are spending a lot of time thinking about is security. Uh, I mean just taking a step back, I think this is probably the single most important thing for any product that anyone sells at this point because trust is kind of the most important thing that we're selling when we work with other people. And uh, with agents being the ones who
</details>

<!-- chunk 17/50 -->

产生漏洞，呃，除了让智能体来监控代码中的那些确切漏洞之外，几乎找不到其他解决方案。所以大家应该思考如何构建一个智能体工厂，用来检测代码库中的安全问题。嗯，这也是我们花大量时间、花很多时间在做的事情。

<details><summary>Original English</summary>
 generate

 the

 vulnerabilities,





uh,

 it's

 kind

 of

 impossible

 to

 find

 a





different

 solution

 than

 having

 agents

 be





the

 ones

 who

 are

 monitoring

 for

 those





exact

 vulnerabilities

 in

 your

 code.

 So





you

 should

 be

 thinking

 about

 how

 you

 can





build

 an

 agent

 factory

 that's

 detecting





security

 issues

 in

 your

 codebase.

 Um

 and





so

 this

 is

 something

 we

 spending

 a

 lot





of

 time

 out

 spending

 a

 lot

 of

 time

 on.
</details>

那么通常在安全事件中会发生什么呢？比方说你怀疑有什么异常，智能体可能一直在寻找它：“为什么、为什么控制平面突然流出这种网络流量？”我可以整理出一份事件时间线，这显然是调查的第一步。但任何参与过严重安全调查的人都知道，时间至关重要。这是一个非常适合并行的典型问题。

<details><summary>Original English</summary>
So

 typically

 what

 happens

 in

 a

 security





incident?

 Well,

 let's

 say

 you

 suspect





something.

 An

 agent

 might

 be

 always





looking

 for

 it.

 Why

 why

 is

 there

 this





like

 network

 traffic

 that's

 erressing





all

 of

 a

 sudden

 from

 my

 control

 plane?





Well,

 I

 can

 assemble

 an

 incident





timeline

 and

 that's

 obviously

 the

 first





step

 in

 an

 investigation.

 But

 anyone





who's

 been

 a

 part

 of

 a

 serious

 security





investig

 investigation

 knows

 that

 time





is

 of

 the

 essence.

 It's

 a

 perfect





problem

 for

 parallelism.
</details>

当安全事件发生时，你正是这么做的：让所有人同时上线，这样就能同时探索 10 个、15 个、20 个不同的假设，因为你能早一小时发现真正的问题，你就实际上多安全了一小时。那么，如果我们用一个可分支的智能体来做这事会怎样？假设有两条调查路径。智能体整理出了事件时间线，现在你可以问两个问题：“嘿，最近的一次部署是否引入了某种新的集成？也许我可以去看看代码”，或者“我可以探索一个完全不同的假设：是否有受损的身份在访问这些数据？”

<details><summary>Original English</summary>
And

 that's





exactly

 what

 you

 do

 when

 a

 security





incident

 happens.

 You

 bring

 everyone





online

 so

 you

 can

 explore

 10,

 15,

 20





different

 theories

 at

 once

 because

 an





hour

 earlier

 that

 you

 can

 you

 can

 detect





the

 real

 issue

 is

 an

 hour

 that

 you're





actually

 more

 safe.

 So

 okay,

 what

 if

 we





did

 that

 with

 a

 branchable

 agent?

 Let's





say

 there's

 two

 paths

 to

 investigate.

 Uh





so

 you

 know

 the

 agents

 assembled

 the





incident

 timeline

 and

 now

 you

 can

 ask





two

 questions.

 Hey

 did

 a

 recent





deployment

 in

 introduce

 some

 kind

 of

 new





integration

 like

 maybe

 I

 can

 go

 look

 at





the

 code

 or

 I

 can

 explore

 a

 totally





different

 theory.

 Is

 a

 compromised





identity

 accessing

 this

 data
</details>

我们能在这里做的核心事情，就是将最初启动调查的整个原始智能体进行分支，然后新的智能体就能在一个完全隔离的世界副本中工作。在某些情况下，只要条件允许，我们甚至可以对正在调查的实际服务本身进行分支。

<details><summary>Original English</summary>
and

 the





core

 thing

 that

 we

 are

 able

 to

 do

 here





is

 we

 branch

 that

 whole

 original

 agent





that

 was

 starting

 the

 investigation





and

 then

 the

 new

 one

 is

 able

 to

 work

 in





a

 completely

 isolated

 copy

 of

 the

 world.





And

 in

 some

 cases

 when

 we're

 able

 to,

 we





can

 even

 branch

 the

 actual

 service

 that





we're

 investigating.
</details>

当你拥有这样一个包含了对话、记忆和存储的隔离副本时，你就可以全面探索该安全风险，并让智能体自主循环迭代。这可以说是这里的关键所在。这些智能体的优势就在于它们能够反复循环、验证并尝试新的假设。我认为 Andrej Karpathy 说得非常精辟：它们远比软件历史上可能存在的任何人类都更加顽强。

<details><summary>Original English</summary>
Uh,

 and

 so

 when

 you





have

 this

 isolated

 copy

 of

 conversation,





memory,

 and

 storage,

 you

 can

 fully





explore

 that

 security

 risk

 and

 and

 let





the

 agent

 loop

 on

 its

 own.

 And

 that's





kind

 of

 the

 key

 thing

 here.

 The

 way

 that





these

 agents

 are

 good

 is

 that

 they're





able

 to

 loop,

 verify,

 try

 new

 theories.





I

 think

 Andre

 Karpathy

 said

 it

 really





well.

 They're

 far

 more

 tenacious

 than





any

 human

 probably

 in

 the

 history

 of





software.
</details>

因此它们能够直接……但我们总是把自己作为审批层插入其中，从而碍手碍脚。我们认为这是一个有助于解决该问题的方案：只需在一定程度上消除犯错的后果。将整个状态进行分支，这样你就不用真正去担心同样的风险。然后我们发现这样其实也能得出合理的结论。

<details><summary>Original English</summary>
And

 so

 they're

 able

 to

 just





but

 like

 we

 keep

 getting

 in

 the

 way

 by





inserting

 ourselves

 as

 an

 approval





layer.

 Uh

 and

 so

 this

 is

 a

 solution

 that





we

 think

 helps

 with

 that.

 Just

 like

 take





away

 the

 consequences

 of

 making

 a





mistake

 a

 little

 bit.

 Branch

 the

 entire





state

 so

 that

 you're

 not

 actually

 you





know

 worrying

 about

 that

 same

 risk.

 And





then

 you

 we

 you

 we've

 been

 able

 to

 find





this

 to

 actually

 uh

 come

 to

 a

 reasonable





conclusion

 as

 well.
</details>

那么对我们来说这一切意味着什么呢？我们认为你的基础设施需要是可分支的，这也正是我们正在与 Neon 以及 Databricks 一起构建的东西。我们对那个可分支的未来感到无比兴奋，因为我们认为团队将成为下一代智能体，无论是在软件方面，还是在我们实际构建产品的方式上。谢谢大家。

<details><summary>Original English</summary>
So

 what

 does

 this





all

 add

 up

 to

 for

 us?

 We

 think

 that

 your





infrastructure

 needs

 to

 be

 branchable





and

 that's

 what

 we're

 building

 with

 Neon





with

 data

 bricks.

 Uh

 and

 we're

 super





excited

 about

 that

 branchable

 future





because

 we

 think

 that

 teams

 are

 going

 to





be

 the

 next

 generation

 of

 agents

 both





for

 software

 and

 the

 way

 that

 we





actually

 build

 products.

 Thank

 you.
</details>

Heat。Heat。

Heat。

嘿，Heat。嘿，Heat。

Heat。Heat。

Heat。嘿，Heat。

加油。

Heat。

好的。

大家能听到我说话吗？

<details><summary>Original English</summary>
Heat. Heat.





Heat.





Hey, heat. Hey, heat.





Heat. Heat.





Heat.

 Hey, Heat.





Come

 on.





Heat.





Okay.





All

 right.

 Can

 y'all

 hear

 me?
</details>

### 安全软件工厂

>> 好的。我叫 Andrew，我想我们现在开始了。我不知道到处有没有计时器。我叫 Andrew，今天很高兴能和大家聊聊安全软件工厂。不过首先简单自我介绍一下。我是 Sonar 的主任软件工程师。我负责 guitar，这是 Sonar 的 AI 代码审查产品。在此之前，我曾在 Uber 工作，负责司机行程体验和导航。

<details><summary>Original English</summary>
>> All right.

 My

 name

 is

 Andrew

 and

 I

 think





we're

 starting

 now.

 I

 don't

 know if





there's

 a

 timer

 anywhere.

 Uh

 my

 name

 is





Andrew

 and

 I'm

 excited

 to

 talk

 to

 you





today

 about

 the

 safe

 software

 factory.





Uh

 but

 first

 a

 little

 bit

 about

 me.

 Uh

 I





am

 a

 staff

 software

 engineer

 at

 Sonar.

 I





work

 on

 guitar

 which

 is

 Sonar's

 AI

 code





review

 products.

 Uh

 and

 previously

 I

 was





at

 uh

 Uber

 working

 on

 the

 driver

 trip





experience

 and

 navigation.
</details>

在那之后，我在一家名为 Forward 的医疗健康科技初创公司待了一小段时间，构建一种具备 AI 能力的基础医疗保健系统。

<details><summary>Original English</summary>
Uh

 and

 then

 after

 that

 I

 was

 at

 a

 health





tech

 startup

 called

 forward

 for

 a

 little





while

 uh

 building

 a

 sort

 of

 an

 AI





enabled

 primary

 health

 care

 system.
</details>

好的。关于软件工厂：这可以说是目前我们行业中最热门的流行词了。每个人都在谈论软件工厂，每个人都在试图构建软件工厂。

<details><summary>Original English</summary>
Okay.

 So

 the

 software

 factory

 this

 is





like

 the

 hottest

 buzzword

 in

 our





industry

 right

 now.

 Everyone's

 talking





about

 software

 factories.

 Everyone's





trying

 to

 build

 a

 software

 factory.
</details>

问题就在于，嗯，首先，你们大多数人可能已经知道这是什么了。但如果你还不知道，我来做一个非常简短的概述。这算是 AI 时代之前就存在的主要软件开发生命周期循环。我们有各种输入，基本上就是产品规格、功能需求、工单之类的内容。如果有复杂的输入，特别是针对复杂的内容，我们会把它们带入规划步骤。

<details><summary>Original English</summary>
And

 the

 question

 is,

 well,

 oh

 well,

 so





first

 of

 all,





um,





most

 of

 you

 probably

 know

 what

 this

 is





already.

 Um,

 but

 if

 you

 don't,

 I'll

 just





give

 a

 really

 quick

 overview.

 Uh,

 this





is

 sort

 of

 the

 the

 main

 software





development

 life

 cycle

 loop

 uh,

 as

 it





existed

 before

 the

 AI

 era.

 So

 we

 have

 uh





inputs

 basically

 product

 specs,

 feature





requests,

 tickets,

 things

 like

 that.

 Um





we

 take

 those

 into

 the

 planning

 step

 if





they're

 especially

 if

 they're





complicated.
</details>

然后我们进行构建，编写代码，然后提出 PR。那个 PR 会接受审查并走 CI，最终合并，然后我们将其部署到生产环境。接着用户与我们的软件互动，向我们提供反馈或发现 Bug；或者我们也可能收到一些监控与警报。随后这些信息又作为更多的输入重新进入循环，循环周而复始。

<details><summary>Original English</summary>
Uh

 and

 then

 we

 then

 we

 build

 then

 we





write

 the

 code





uh

 and

 then

 we

 um

 uh

 put

 up

 a

 PR

 and





that

 PR

 gets

 uh

 reviewed

 and

 it

 goes





through

 CI

 and

 then

 it

 eventually

 merges





uh

 and

 then

 we

 deploy

 that

 to

 production





and

 then

 users

 interact

 with

 our





software

 and

 they

 give

 us

 feedback

 or





they

 find

 bugs





um

 or

 we

 might

 also

 get

 some

 monitoring





and

 alerts

 as

 well.

 And

 then

 those

 go





back

 in

 as

 more

 inputs

 and

 the

 the

 cycle





continues
</details>

在智能体编码和 AI 时代，自动化跟随着每一个瓶颈。过去瓶颈往往是编码和构建部分，现在有了编码智能体，这部分已经被自动化了。如今瓶颈在一定程度上转移到了审查步骤，我们正在开始为此引入 AI 代码审查系统。接着我们看到 AI 系统和自动化现在确实正在发生在这个过程的每一步。

<details><summary>Original English</summary>
and

 and

 so

 um

 in

 the

 in

 the

 era

 of





agentic

 coding

 and

 AI

 automation

 has





followed

 every

 bottleneck.

 So

 the





bottleneck

 used

 to

 be

 the

 the

 coding





part

 the

 building

 um

 now

 with

 coding





agents

 that's

 been

 automated.

 Um,

 and





now

 the

 bottleneck

 has

 sort

 of

 shifted





over

 to

 the

 that

 review

 step

 and

 we're





starting

 to

 introduce

 uh

 AI

 code

 review





systems

 for

 that.

 Um,

 and

 then

 and

 we're





seeing

 uh

 AI

 systems

 and

 automation





happen

 really

 at

 every

 step

 of

 this

 now.
</details>

我们开始看到用于监控部署、控制发布、分流工单和事件、以及规划的 AI 系统。因此，眼前的这个就是我们正在创建的软件工厂。

<details><summary>Original English</summary>
Uh

 so

 we're

 starting

 to

 see

 AI

 systems





for

 monitoring

 deployments,

 controlling





rollouts,

 triaging

 uh

 triaging,

 you





know,

 tickets

 and

 incidents,

 planning.





And

 so

 this

 this

 here

 is

 the

 sort

 of





software

 factory

 that

 we're

 that

 we're





creating.
</details>

所以我们现在面临的共同问题是：我们如何让这个工厂变得安全？换句话说，我们如何能在其中引入足够多的验证层，从而能够确信从中产出的软件能如预期工作，没有 Bug，也没有安全漏洞。我们 CEO Tar 最近说过：“代码充裕，信心匮乏。”

<details><summary>Original English</summary>
And

 and

 so

 the

 question

 that

 we

 all

 have





now

 is

 how

 do

 we

 make

 this

 factory

 safe,





right?

 Uh

 in

 other

 words,

 how

 can

 we





introduce

 enough

 layers

 of

 verification





into

 this

 so

 that

 we

 can

 trust

 that

 the





software

 coming

 out

 of

 it

 is

 it

 works

 as





expected.

 It's

 free

 of

 bugs,

 free

 of





security

 vulnerabilities.





Um,

 our

 CEO





Tar

 said

 recently,

 "Code

 is

 abundant,





confidence

 is

 not."
</details>

所以我今天想讲的，就是我们 Sonar 一直在思考的：如何在这个软件工厂内部的各个不同节点引入信心。我们正在通过增加更多循环的纵深防御方式来应对这一挑战，听到这里你可能并不感到意外。我今天特别想讲其中的四个循环。

<details><summary>Original English</summary>
So,

 what

 I'm

 going

 to

 talk

 about

 today





is

 just

 how

 we

 at

 Sonar

 have

 been





thinking

 about

 uh

 how

 to

 introduce

 uh





confidence





uh

 at

 at

 all

 sort

 of

 all

 different





points

 within

 this

 software

 factory.





And

 uh

 we're

 approaching

 this

 this





challenge

 with

 a

 defense

 and

 depth





approach

 that

 comes

 from

 adding

 more





loops.

 You

 might

 not

 be

 surprised

 to





hear





and

 I'm

 going

 to

 talk

 about

 four

 of

 them





today

 in

 particular.
</details>

首先是循环一，即 PR 检查循环；循环二，即部署后验证循环；循环三，即维护循环；以及循环四，即知识循环，这是一个比较特殊的循环。首先我要讲讲循环一：PR 检查循环。

<details><summary>Original English</summary>
So

 there's

 the

 loop





one

 which

 is

 the

 PR

 checks

 loop.





Uh

 loop

 two

 uh

 which

 is

 the

 post

 deploy





verifications

 loop.





loop

 three

 uh

 which

 is

 the

 maintenance





loop





and

 loop

 four

 which

 is

 the

 knowledge





loop

 and

 this

 is

 kind

 of

 a

 kind

 of

 a





special

 loop.

 Uh

 so

 first

 I'm

 going

 to





talk

 about

 loop

 one

 the

 PR

 checks

 loop.
</details>

这是我们大家大概都以某种形式拥有的一套循环。你提一个 PR，它经历一些 CI 检查，接受代码审查。现如今它可能还会接受 AI 代码审查。但我们开始看到这里也引入了多得多的自动化。比如，我们开始看到智能体通过推送修复来响应代码审查意见。这个循环周而复始地运行，直到 PR 变绿。

<details><summary>Original English</summary>
So

 this

 is

 the

 loop

 that

 we

 probably

 all





have

 in

 some

 form.

 Uh

 you

 put

 up

 a

 PR,





it

 goes

 through

 some

 CI

 checks,

 it

 gets





a

 code

 review.

 Nowadays

 it's

 probably





getting

 an

 AI

 code

 review

 as

 well.

 Um,





but

 we're

 starting

 to

 see

 a

 lot

 more





automation

 being

 introduced

 here

 as





well.

 So,

 we're

 starting

 to

 see

 agents





pushing

 fixes

 to

 respond

 to

 the

 code





review

 comments.

 Um,

 and

 this

 loop

 kind





of

 goes

 around

 and

 round

 until

 the

 PR





turns

 green.
</details>

实际上我们在这一步能做的事情还有很多。因为在此时发现问题，仍然比合并进代码库之后再发现要划算得多。所以我们在这里有一个真正的机会，将这种审查拓展到大多数人所做的常规测试和代码审查之外。

<details><summary>Original English</summary>
And

 there's

 actually

 a

 lot

 more

 that

 we





can

 be

 doing

 here.

 um

 because

 catching

 a





problem

 at

 this

 point

 is

 still

 cheaper





than

 after

 it

 merges

 into

 the

 codebase.





Uh

 so

 we

 have

 a

 real

 opportunity

 here

 to





widen

 this

 review

 past

 the

 sort

 of





normal

 tests

 and

 code

 review

 that

 most





of

 us

 do.
</details>

因此我们当然有 AI 代码审查；我们也可以在这里做静态分析，我们当中的许多人都这么做。我们可以进行所谓的“功能验证”，即查看工单的要求，看该 PR 是否确实解决了这些事项。

<details><summary>Original English</summary>
So

 of

 course

 we

 have

 AI

 code





review.

 We

 can

 also

 do

 static

 analysis





here.

 Many

 of

 us

 do

 that.





Uh

 we

 could

 do

 what's

 called

 functional





validation.

 So

 this

 is

 where

 we

 can

 look





at

 uh

 what

 the

 ticket

 asks

 for

 and

 see





if

 the

 PR

 actually

 addresses

 those





things.
</details>

我们可以查看团队可能为编码约定设定的规则，查看最佳实践之类的内容，看看 PR 是否遵循了这些规则。我们可以查阅知识，这可以是从公司文档、以往代码审查或过去故障中吸取沉淀的知识。

<details><summary>Original English</summary>
Um

 we

 can

 look

 at

 rules

 that

 the

 team





may

 set

 for

 coding

 conventions





uh

 see

 if

 best

 practices

 things

 like





that

 see

 if

 the

 PR

 is

 adhering

 to

 those.





We

 can

 look

 at

 knowledge.

 So

 this

 can

 be





knowledge

 accumulated

 from

 company





documentation,





from

 things

 that

 have

 been

 learned

 on





past

 code

 reviews

 or

 past

 outages.
</details>

我们可以做跨仓库检查。我们可以实际查看其他代码库，看看此 PR 中的任何内容是否会破坏或导致另一个代码库中的内容被破坏。我们可以做跨 PR 分析。我们也可以查看所有其他开放的 PR，看看此 PR 中是否有任何内容与其中某一个发生冲突。我们可以做安全审查，检查……

<details><summary>Original English</summary>
Uh

 we

 could

 do

 cross

 repo

 checks.

 So

 we





could

 actually

 look

 at

 other





repositories

 and

 see

 if

 anything

 in

 in





this

 PR

 uh

 will

 break

 or

 cause

 something





to

 break

 in

 another

 repository.





Uh

 we

 could

 do

 cross

 PR

 analysis.

 So,

 we





can

 look

 at

 all

 the

 other

 open

 PRs

 as





well

 and

 see

 if

 there's

 anything

 uh

 in





this

 PR

 that

 conflicts

 with

 one

 of





those.





We

 could

 do

 security

 review,

 check

 for
</details>

<!-- chunk 18/50 -->

漏洞、密钥、依赖项。

<details><summary>Original English</summary>
vulnerabilities,
 secrets,
 dependencies.
</details>

我们可以进行端到端测试。举例来说，如果这是一个 Web 应用，我们可以在浏览器中打开它，点一点看它的运行是否符合预期。

<details><summary>Original English</summary>
We
 could
 do
 endto-end
 testing.
 So,
 for
example,
 if
 this
 is
 a
 web
 app,
 we
 could
open
 up
 in
 a
 browser
 and
 and
 click
around
 and
 see
 if
 it
 works
 as
 expected.
</details>

最后，我们可以进行风险评估。我们可以评估并计算它的影响范围（blast radius），把它分类为低、中或高风险。这实际上能帮助我们确定这是否是一个甚至需要人工介入查看的 PR。

<details><summary>Original English</summary>
Um
 and
 finally
 we
 can
 do
 risk
assessment.
 So
 we
 could
 sort
 of
 uh
 look
at
 this
 and
 compute
 uh
 the
 blast
 radius
and
 sort
 of
 categorize
 this
 into
 like
low,
 medium
 or
 high
 risk.
 And
 that
 can
actually
 help
 us
 determine
 if
 this
 is
 a
PR
 that
 a
 human
 even
 needs
 to
 look
 at
 at
all.
</details>

所有这些信息都可以汇入这个决策流程——这个合并门禁（merge gate），即决定该 PR 是否可合并的决策机制。当然，每次推送修复时，所有这些检查至少都会在某种程度上重新运行。

<details><summary>Original English</summary>
And
 so
 all
 of
 these
 things
 can
 flow
 into
this
 the
 sort
 of
 decision
 this
 merge
gate
 this
 decision
 of
 whether
 this
 PR
 is
mergeable.
 And
 of
 course
 uh
 every
 time
 a
fix
 is
 pushed
 all
 of
 these
 run
 again
 at
least
 in
 some
 degree.
</details>

在所有这些过程中，很关键的一点是，不要仅仅依据测试已运行或测试已通过的事实来把关合并决策，而要基于证据。这包括实际的代码审查发现、质量门禁的结果、任何漏洞、风险等级等。所有这些基本上都可以输入到这个合并门禁中，并对照团队为“可合并 PR”设定的标准进行核验。

<details><summary>Original English</summary>
And
 and
 with
 all
 of
 this
 it's
 important
to
 gate
 the
 that
 merge
 decision
 not
 just
on
 the
 fact
 that
 a
 test
 ran
 or
 that
 it
passed
 but
 on
 the
 evidence.
 So
 that
would
 be
 things
 like
 the
 actual
 code
review
 findings,
 the
 results
 of
 the
quality
 gates,
uh
 any
 vulnerabilities,
um
 the
 risk
 level.
 So
 all
 of
 that
 can
 be
uh
 basically
 fed
 into
 this
 merge
 gate
and
 checked
 against
 criteria
 that
 the
team
 can
 set
 for
 what
 is
 a
 mergeable
 PR.
</details>

当把这些证据记录到 PR 中时，能让合并门禁变得牢固得多。

<details><summary>Original English</summary>
And
 when
 you
 record
 that
 evidence
 uh
 to
the
 PR,
 it
 just
 makes
 this
 uh
 the
 merge
gate
 much
 stronger.
</details>

我们现在看到，那些在这方面做得很好的团队，实际上可以在 PR 审查中将越来越多的信任委托给这类自动化系统。我们看到有些团队不仅开启了自动拦截合并，在某些情况下对于低风险变更还会开启自动批准，甚至对某些已批准的低风险 PR 开启自动合并。这可以为人工审查人员释放出大量的审查精力，去审查那些高风险的变更。

<details><summary>Original English</summary>
And
 so
 what
 we're
 seeing
 now
 uh
 with
teams
 who
 do
 this
 well
 uh
 is
 that
 they
can
 actually
 delegate
 more
 and
 more
trusts
 uh
 to
 this
 type
 of
 automation
 on
the
 PR
 review.
 Uh
 so
 we're
 seeing
 teams
begin
 to
 turn
 on
 not
 just
 automatic
merge
 blocking
 but
 uh
 even
 auto
 approve
in
 some
 cases
 for
 low-risk
 changes
 and
and
 even
 automerge
 for
 certain
 types
 of
PRs
 that
 are
 that
 are
 lowrisk
 and
approved
and
 this
 can
 just
 free
 up
 a
 lot
 of
review
 bandwidth
 for
 human
 reviewers
 to
review
 the
 the
 more
 high-risisk
 changes.
</details>

### 环二：部署后验证环

接下来我要讲讲环二，也就是我们的部署后验证环（post deploy verification loop）。我认为这目前在很大程度上还处于早期阶段，大家都在这里进行各种尝试。但其核心思想是，一旦代码完成部署，你可以构建 AI 系统来读取生产日志、链路追踪（traces）和指标等数据，查看你的代码在生产环境中的实际运行表现是否符合预期。

<details><summary>Original English</summary>
Okay.
 So
 now
 um
 I'm
 going
 to
 talk
 about
loop
 two
 which
 is
 our
 post
 deploy
verification
 loop.
 Uh
 so
 this
 is
 I
 would
say
 very
 much
 in
 its
 early
 stages
 right
now.
 People
 are
 experimenting
 with
 all
kinds
 of
 things
 here.
 Um
 but
 the
 idea
 is
that
 once
 your
 code
 is
 deployed
 uh
 you
can
 have
 you
 you
 can
 build
 AI
 systems
 to
check
 uh
 to
 read
 like
 production
 logs,
traces,
 metrics
 and
 see
 if
 your
 code
 is
actually
 behaving
 as
 you
 expect
 it
 to
 in
production.
</details>

在此基础上，我们开始看到像智能体驱动发布（agentic rollout）这样的机制，智能体可以决定是扩大发布范围还是执行回滚、关闭特性开关（feature flag）。你还可以进行 AI 故障监控，即监控告警并使用 AI 系统协助排查故障根因并修复故障。

<details><summary>Original English</summary>
And
 then
 from
 there
 you
 can
 actually
 um
uh
 we're
 starting
 to
 see
 things
 like
agentic
 rollout
 where
 agents
 can
 decide
whether
 to
 widen
 a
 roll
 out
 or
 roll
 back
turn
 a
 feature
 flag
 off
and
 you
 can
 also
 do
 uh
 AI
 outage
monitoring.
 So
 you
 can
 uh
 monitor
 alerts
and
 uh
 use
 AI
 systems
 to
 help
 you
 uh
root
 cause
 and
 fix
 outages.
</details>

### 环三：维护环

进入环三，这就是我所说的维护环（maintenance loop）。这是一个与你的主软件开发生命周期环并行运行的环节。

<details><summary>Original English</summary>
Okay.
 Uh
 so
 moving
 on
 to
 loop
 three.
 Uh
so
 this
 is
 what
 I
 call
 the
 maintenance
loop.
 Uh
 this
 is
 kind
 of
 a
 a
 parallel
loop
 that
 runs
 alongside
 your
 main
software
 development
 uh
 life
 cycle
 loop.
</details>

在这里，我们会按照某种预设周期对代码库进行持续扫描，检查许多与在 PR 阶段相同的项目。我们可以进行代码审查、静态分析、安全检查等。如果发现了问题，我们可以发起一个修复 PR 来解决它。这让我们能够捕获在 PR 阶段无法捕获的问题。例如，可以设想在代码合并之后引入了新规则，或者在代码合并之后披露了新的安全漏洞。

<details><summary>Original English</summary>
And
 this
 is
 where
 we
 continuously
 scan
the
 codebase
 on
 some
 schedule.
 And
 we
check
 for
 a
 lot
 of
 the
 same
 things
 that
we
 check
 for
 on
 the
 PR.
 We
 we
 could
 do
code
 review,
 static
 analysis,
 security
checks,
 etc.
 And
 then
 we
 can
 if
 we
 find
an
 issue,
 we
 can
 open
 up
 a
 remediation
PR
 to
 address
 that.
 And
 this
 lets
 us
catch
 things
 that
 we
 couldn't
 catch
 in
the
 PR.
 So
 for
 example,
 you
 could
imagine
um
 maybe
 a
 new
 rule
 was
 introduced
 after
code
 merged
 or
 a
 new
 vulnerability
 was
published
 after
 code
 merged.
</details>

或者像缓慢漂移（slow drift）这类情况——重复代码或复杂度在悄然累积，你在单个 PR 上很难真正察觉。通过对代码库的持续扫描，你就可以捕获到这一类问题。

<details><summary>Original English</summary>
um
 or
 even
 something
 like
 slow
 drift
where
 you
 you
 slowly
 get
 duplication
 or
complexity
 building
 up
 that
 you
 can't
really
 see
 on
 a
 single
 PR.
 Uh
 you
 can
catch
 these
 kinds
 of
 things
 here
with
 these
 uh
 with
 the
 continuous
codebase
 scans.
</details>

### 环四：知识环

最后，我们转向知识环（knowledge loop），我们看到这对许多公司来说正变得非常重要。每家公司都有大量的知识文档、产品规格说明、业务决策等信息，如果智能体拥有这些知识，就能把工作做得更好，对吧？所以这个环基本上是从不同来源收集所有这些知识，以及从以往的代码审查和故障中吸取的经验。

<details><summary>Original English</summary>
Okay.
 Okay.
 And
 so
 finally
 we
 move
 over
to
 the
 knowledge
 loop
 and
 and
 this
 is
becoming
 we're
 seeing
 this
 become
 a
 very
important
 uh
 loop
 for
 a
 lot
 of
companies.
 Um
 every
 company
 has
 a
 lot
 of
knowledge
 documentation
 product
 specs
um
 business
 decisions
um
 and
 the
 agents
 do
 a
 better
 job
 if
they
 have
 that
 knowledge.
 Right?
 So
 this
loop
 basically
 collects
 all
 that
knowledge
 from
 different
 sources
 as
 well
as
 things
 that
 were
 learned
 on
 prior
code
 reviews
 and
 from
 prior
 outages.
</details>

经过整理提炼后，这些知识可以输入到所有其他环、所有这些其他智能体中，以便它们能把工作做得更好。例如，这对你的编码智能体非常有用，因为如果它们具备其中的一部分知识，第一次编写时很可能就会完成得更好，问题也更少。这样你在审查阶段经历的审查轮次基本上就会更少。

<details><summary>Original English</summary>
It's
 curated
 and
 then
 it
 can
 be
 uh
 fed
into
 all
 of
 the
 other
 loops,
 all
 of
these
 other
 agents
 um
 so
 they
 can
 uh
 do
a
 better
 job.
And
 and
 for
 example,
 this
 is
 really
powerful
 with
 your
 coding
 agents
 because
if
 they
 have
 some
 of
 this
 knowledge,
they
 can
 probably
 do
 a
 better
 job
 the
first
 time,
 fewer
 issues.
Um,
 and
 then
 you'll
 you'll
 wind
 up
 with
basically
 fewer
 review
 laps
 at
 the
 uh
review
 stage.
</details>

### 人类软件工程师在软件工厂中的角色

那么，这对于我们作为人类软件工程师在这座工厂中的角色意味着什么？大家可能会问：好吧，如果我们把所有这些都做扎实了，我们能直接关上灯，运行一座“黑灯工厂”（dark factory）吗？

<details><summary>Original English</summary>
Okay.
 So,
 what
 does
 this
 mean
 for
 our
role
 as
 human
 software
 engineers
 in
 this
factory?
 Uh,
 you
 might
 be
 asking,
 okay,
so
 if
 if
 we
 nail
 all
 of
 this,
 can
 we
just
 uh
 turn
 the
 lights
 out
 and
 run
 a
dark
 factory?
</details>

我认为可能不行，至少目前还不行。我更愿意说，工厂是“微光运行，而非黑灯”（runs dim, not dark）。在我们专业经验真正重要的那些环节，由我们来进行干预仍然非常关键。

<details><summary>Original English</summary>
Uh,
 and
 I
 would
 say
 probably
 not.
 Not
right
 now.
 Uh,
 I
 like
 to
 say
 the
 factory
runs
 dim,
 not
 dark.
 It's
 still
 very
important
 for
 us
 to
intervene
 in
 places
 where
 our
 expertise
is
 is
 really
 important.
</details>

具体包括审计高风险代码；核验证据，核实各项机制是否确实按预期运行；处理回滚和突发事件等异常情况；审查架构——我认为智能体目前在架构审查方面还不是很擅长；以及提供背后的缘由（the why），或者帮助构建驱动所有这些智能体和流程环的知识体系，提供产品意图、权衡考量、业务决策等内容。

<details><summary>Original English</summary>
Uh
 so
 that
 would
 be
 things
 like
 auditing
risky
 code.
Um
 verifying
 that
 evidence,
 verifying
things
 are
 actually
 working
 as
 expected.
Handling
 exceptions
 like
 rollbacks
 and
incidents.
Uh
 reviewing
 architecture.
Agents
 are
 not
 very
 good
 at
 this
 yet,
 I
would
 argue.
um
 and
 supplying
 the
 why
 or
 or
 helping
to
 build
 that
 knowledge
 that
 that
 powers
all
 these
 agents
 and
 all
 these
 loops,
supplying
 the
 product
 intent,
 the
trade-offs,
 the
 business
 decisions,
things
 like
 that.
</details>

当然，我们自己本身也在工程化构建这座工厂，对吧？我们已经跨入了构建整座软件工厂的时代。

<details><summary>Original English</summary>
And
 of
 course,
 we
 engineer
 the
 factory
ourselves,
 right?
 We're
 we've
 sort
 of
moved
 into
 this
 era
 where
 we're
 we're
building
 the
 software
 factory
 as
 a
whole.
</details>

至此，我希望这为大家提供了一个思考框架，不仅关乎如何构建软件工厂，也关乎如何构建一个安全的软件工厂。谢谢大家，我的分享就到这里。

<details><summary>Original English</summary>
So
 with
 that,
 I
 hope
 that
 gave
 you
 sort
of
 a
 framework
 for
 how
 to
 think
 about
 um
not
 just
 how
 to
 build
 your
 software
factory
 uh
 but
 how
 to
 build
 a
 safe
software
 factory.
 So
 thank
 you.
 That's
all
 for
 me.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat.
 Heat.
</details>

真漂亮。

<details><summary>Original English</summary>
That's
pretty.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat.
 Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

到上面来。Heat. Heat. N. 下来。

<details><summary>Original English</summary>
Heat
up
here.
 Heat. Heat. N.
down.
</details>

I

<details><summary>Original English</summary>
I
</details>

到上面来。

<details><summary>Original English</summary>
Heat
up here.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

来吧。

<details><summary>Original English</summary>
Come
on.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat.
 Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat.
 Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

嘿，Heat。

<details><summary>Original English</summary>
Hey, Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat.
 Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. 嘿。嘿。嘿。

<details><summary>Original English</summary>
Heat.
 Hey. Hey. Hey.
</details>

准备就绪。

<details><summary>Original English</summary>
All
 set.
</details>

>> 大家好。我是 Luke，在 Factory 带领我们的核心智能体团队。今天我想谈谈自主性，以及为什么从编码智能体中获益最多的团队，实际上并不是那些从第一天起就交接最多工作的人。相反，是那些逐步提升自主性、一次推进一个检查点的人，直到他们所拥有的形态开始初具软件工厂的雏形。

<details><summary>Original English</summary>
>> Hi
 everyone.
 Uh
 I'm
 Luke.
 I
 lead
 our
core
 agent
 team
 here
 at
 Factory.
 Uh
today
 I
 want
 to
 talk
 about
 autonomy
 and
why
 uh
 the
 teams
 that
 are
 getting
 the
most
 out
 of
 coding
 agents
 are
 not
actually
 the
 ones
 that
 are
 handing
 over
like
 the
 most
 work
 on
 day
 one.
 It's
instead
 the
 folks
 who
 are
 ramping
 up
autonomy
 gradually,
 one
 checkpoint
 at
 a
time
 until
 what
 they
 have
 starts
 to
resemble
 a
 software
 factory.
</details>

对于还不了解我们的人，Factory 是一个构建 Droid 以及构建在这一编码智能体之上的整套软件工程与软件构建界面的平台。全球成千上万的开发者在像 Nvidia、T-Mobile 和 Adobe 这样的公司使用我们的产品。这些公司的工程师与我们一起构建的，实际上正是一座软件工厂——一个全天候 24 小时运行且处于公司控制之下构建软件的系统。

<details><summary>Original English</summary>
So
 for
 those
 who
 don't
 know
 us,
 a
factory
 is
 a
 platform
 uh
 that
 builds
droid
 and
 then
 a
 a
 whole
 like
 surface
for
 software
 engineering
 and
 building
software
 on
 top
 of
 that
 coding
 agent.
Hundreds
 of
 thousands
 of
 developers
 use
us
 around
 the
 world
 at
 companies
 like
Nvidia,
 T-Mobile,
 uh
 and
 Adobe.
 What
these
 companies
 engineers
 are
 building
with
 us
 is
 is
 really
 like
 a
 software
factory,
 a
 system
 that
 runs
 24/7
 and
builds
 software
 under
 the
 company's
control.
</details>

这是一个从任何已有信息处接收信号、将信号转化为变更、验证变更、然后从生产环境的表现中学习的闭环。所谓信号，实际上就是任何告诉你软件该如何演进的信息。这可以是一个 Sentry 告警，也可以是某人在 Slack 上提出的一个想法。每个信号都经历相同的阶段。因此，你标准化的是流程，而不是产出。

<details><summary>Original English</summary>
And
 that's
 a
 loop
 that
 takes
 in
signals
 from
 wherever
 information
 is
already
 available,
 turns
 them
 into
changes,
 validates
 them,
 uh,
 and
 then
learns
 from
 what
 production
 shows.
 A
signal
 is
 really
 like
 anything
 that
tells
 you
 how
 your
 software
 should
evolve.
 So
 that
 could
 be,
 you
 know,
 a
sentry
 alert
 or
 someone's
 idea
 on
 Slack.
Every
 signal
 goes
 through
 the
 same
stages.
 So
 you
 standardize
 you
standardize
 the
 the
 process
 not
 the
output.
</details>

我们在五个基石之上构建了该平台：它必须具备透明性、模块化、可治理性、高效性，并且保持前沿。

<details><summary>Original English</summary>
So
 we
 built
 that
 platform
 on
 five
foundations.
 It
 has
 to
 be
 transparent,
modular,
 governable,
 efficient
 and
frontier.
</details>

大多数人把软件工厂想象成这样一种“黑灯建筑”——里面空无一人，一端输入需求，另一端输出合并完成的 PR。而我们在第一线亲眼所见的实际情况并非如此。最好的软件工厂并不是那样搭建的。相反，它们是围绕人构建的。由人类来决定什么最重要，以及随着时间的推移给予 Droid 多少信任。而这些 Droid 则通过交付更多、更高质量的工作来证明自身的价值。

<details><summary>Original English</summary>
Most
 people
 picture
 a
 software
 factory
as
 this
 kind
 of
 like
 lights
 out
 building
where
 uh
 there's
 no
 people
 inside
 of
 it.
Requirements
 come
 in
 one
 end
 and
 merged
PRs
 come
 out
 the
 other.
 And
 and
 really
what
 we
 saw
 firsthand
 in
 the
 field
 is
that
 that's
 not
 the
 case.
 The
 best
 ones
aren't
 set
 up
 like
 that.
 They're
 built
around
 people
 instead.
 Uh,
 humans
 decide
what
 matters
 and
 how
 much
 to
 trust
droids
 over
 time.
 And
 those
 droids
 earn
their
 keep
 as
 they
 deliver
 more
 work
that's
 higher
 quality.
</details>

每家公司的软件工厂彼此之间都大相径庭。因此，我们销售的实际上并不是这座工厂本身，而是用来组装它们的工具和构件。

<details><summary>Original English</summary>
Every
 company's
 software
 factory
 looks
very
 different
 to
 each
 other.
 So,
 what
we
 what
 we
 sell
 is
 not
 really
 this
factory,
 it's
 the
 tools
 and
 the
 building
blocks
 to
 compose
 them.
</details>

现在，回顾一下我们最初是如何走到这一步的，是很有价值的。早在四月份，我们的旗舰产品之一是 Missions，那是首批真正开始缓解软件工程中存在的人类注意力瓶颈的多智能体产品之一。你会……

<details><summary>Original English</summary>
Now,
 it's
 it's
 worth
 kind
 of
 looking
 at
how
 we
 got
 here
 in
 the
 first
 place.
 Back
in
 April,
 one
 of
 our
 flagship
 products
was
 Missions,
 which
 was
 one
 of
 like
 the
first
 multi-
 aent
 uh
 products
 to
 really
take
 like
 a
 bite
 out
 of
 the
 human
attention
 bottleneck
 that
 existed
 in
 in
software
 engineering.
 You'd
</details>

<!-- chunk 19/50 -->

描述一个目标，你得跟编排器来回沟通直到达成共识，然后你批准方案，接着它就会去负责执行数天甚至数周。当目标明确且可验证时，你确实能相当稳定地回来看到已经完成的工作。

<details><summary>Original English</summary>
describe a goal, you'd like argue with the orchestrator until you were aligned, you'd approve the plan, and then it would go handle implementation for like days or even weeks. When the goal was clear and verifiable, you really could come back to like completed work pretty consistently.
</details>

但随着更多团队采用它，我们收到了一些一致的反馈意见。首先是 missions 要求你的工作方式。该产品假定你可以在前期规划好一切，然后它就能直接运转。呃，并且其用户体验有点暗示你不应该去打断它们。Missions 实际上不会向你提问，一旦它开始执行，也不会为你和 agent 之间的沟通提供某种交互界面。所以这适用于像迁移和大型编码特性项目这类工作，但它确实不太符合大多数其他类型工作的需求。

<details><summary>Original English</summary>
But as more teams adopted it, we heard some consistent like pieces of feedback. The first was how missions asked you to work. The product assumed that you could plan everything up front and then it would just work. Uh and the UX sort of suggested that you shouldn't interrupt them. Missions didn't really like ask you any questions or provide like an interactive surface for that uh communication between you and the agent once it was starting implementation. So this suits like migrations and big uh big coding like feature projects but it didn't really fit fit the bill for like most kinds of other work.
</details>

第二点是成本和时间，坦白说，这源于模型变得非常非常出色。我相信大家现在都看到了对抗性审查（adversarial review）在发现代码问题方面极其擅长。因此，呃，当时我们在每个里程碑的边界都加入了对抗性审查。这就直接将那个 mission 的范围从大约 60 个特性扩大到了 200 多个。结果你最终付出的 token 账单和时间线也与之相称。最后一点则是 missions 会将上下文局限在一个人身上。因此这在单个项目里没问题，但这意味着团队的其他人无法真正基于该 mission 所学到的内容继续构建。

<details><summary>Original English</summary>
The second was cost and time and that came from honestly like the models getting really really good. I'm sure you've all seen now adversarial review is really really good at finding these issues in your code. And so, uh, at the time we were adding adversarial review into every milestone's boundary. That just kind of like grew the scope of that mission from something like 60 features to over 200. And so you ended up having a token bill and a timeline that matched that. And then the last one was that missions were keeping their context to one person. So that was fine for like a single project, but it meant that the rest of the team couldn't really build on what that mission had learned.
</details>

### 将操作系统思想引入 Agent 架构

于是我们重新审视，一种心智模型不断浮现。当一个组织在特定时间点运行数十个或数百个 agent 时，你实际上遇到了很多当年操作系统所解决的问题：如何调度工作、如何安全地同时运行多项任务，以及如何共享状态。

<details><summary>Original English</summary>
So we went back to the drawing board and one mental model kept on coming up. When you have like an org that is running dozens or hundreds of agents at a given point in time, you actually have like a lot of the the problems that operating systems back in the day solved. How to schedule work, how to run what many things at once safely, and how to share state.
</details>

所以每个操作系统都是从实际执行工作的核心开始的，我们也想重新审视 agent 本身。长周期（long horizon）agent 会运行数千轮对话，其中的每一处低效都会被成倍放大。因此，你可能会遇到不必要的额外推理请求、相当臃肿的工具调用结果，或是 prompt cache 未命中。随着时间推移，所有这些问题都会复合叠加并导致浪费。

<details><summary>Original English</summary>
So every operating system starts with the thing that actually does the work and we wanted to revisit the agent itself. Long horizon agents run for thousands of turns and every inefficiency across of those gets multiplied. So you could have, you know, an extra inference request that's unnecessary or a a tool result that's pretty bloated or a prompt cache miss. All those things compound over time and lead to waste.
</details>

因此我们决定对 harness 本身做一些相当重大的调整。其中最大的变化是程序化工具调用（programmatic tool calling），也被称为代码模式（code mode）。我们不再是调用一个工具、等待模型响应、然后再调用下一个，而是让模型编写一个简短的程序来一次性执行所有这些工具，并且只打印出相关的内容。

<details><summary>Original English</summary>
So we decided to make some pretty significant changes to the harness itself. The biggest one was programmatic tool calling, also known as code mode. Instead of calling one tool, waiting on the model, and then calling the next, we have the model write a small program that executes all those tools in one go, and then prints out only what's relevant.
</details>

这里有一个例子：有 150 个 Linear ticket 要从一个项目移到另一个项目。按照常规方式处理，大概需要 30 次推理请求、100 万个 token；但如果作为一段模型生成的程序，实际上只需要大约 6 万个 token。它的运行速度要快得多，而且模型只看到与任务实际相关的信息——即操作是否成功的事实。

<details><summary>Original English</summary>
So there's this example here where you have 150 linear tickets that are getting moved from one project to another. done the normal way that's like 30 inference requests, a million tokens, but as one model generated program, you actually only have like 60k tokens. It runs much faster and the model only sees what is actually relevant to the task that the the fact whether it was like successful or not.
</details>

因此操作系统的这一层，正是前沿性与高效性最为关键的地方。每隔几周就会有新模型推出，而且没有两个模型的失败方式是相同的。所以我们以一种能够抚平所有这些不同模型不均衡性（jaggedness）的方式来调优我们的 harness。其结果就是，Droid 目前在市场上相比其他所有编程 agent，都具有更高的质量和更低的成本。

<details><summary>Original English</summary>
So this layer of the OS is where being frontier and efficient matters the most. A new model lands every few weeks and no two fail fail the same way. So we tune our harness in such a way that evens out this jaggedness across all these different models. The result is that Droid is now, you know, higher quality at a lower cost than every other coding agent on the market.
</details>

### 计算环境与 Workstreams

现在你有了一个更快的 agent，但这并没有真正让系统内部完成的工作量产生阶跃式增长。为此，你需要有多个 agent 同时运行，并且它们需要有运行的场所。远程 missions 某种程度上受限于系统中的这个根本限制：也就是由单台计算机来处理所有工作。但要运行一个软件工厂，你需要计算资源能够随着系统中的工作量进行扩展。否则，每个 agent 都会争夺相同的文​​件或系统资源。

<details><summary>Original English</summary>
Now you have a faster agent, but that that doesn't really give you like a step function increase in in how much work gets done inside of your system. For that, you need many agents running at once, and they need somewhere to run. remote missions were kind of held back that by this like fundamental limitation in the system where there was one computer that handled all the work. But to run a software factory, you need uh compute that scales with the volume of work in the system. Otherwise, every agent is is fighting for the same files or system resources.
</details>

这就是为什么我们构建了 environments，它们是你的 droids 所需沙箱的可复用定义，完整包含了它们开始工作所需的仓库、工具和依赖项。该系统是可治理的。因此存在一个统一的控制平面，无论你在何处需要这些沙箱，它都能协同编排它们。它们可以在你自己的 VPC 内运行在 EC2、Kubernetes，或者你已在运营的任何计算环境之上。因此你的代码、数据和网络都在你的掌控之中。计算资源变得可插拔，正如我们提供 BY 选项和 auto-model 选项所构建的可插拔模型层一样。

<details><summary>Original English</summary>
And so that's why we build environments which are reusable definitions of the sandboxes that your droids need, complete with the repos, tools, and dependencies that they that they need to get started with. The system is governable. So there's one comp control plane that orchestrates all of these sandboxes together wherever you need them. They can run inside of your own VPC on on EC2, Kubernetes, whatever compute you already operate. So your code, your data and your network are in your control. Compute becomes pluggable just like we made the BY options and automodel uh options that we provide uh make that provide sort of like this like model pluggable layer.
</details>

现在我们有了便宜到可以一直运行的 agent，以及同时运行多个 agent 的计算能力。那么接下来的问题就是：我们如何编排所有这些工作？起初我们尝试构建一个非常复杂的 agent DAG 系统，通过这些非常严格的规则组合在一起，但并没有奏效。你最终会遇到很多起初困扰 missions 的相同问题，因为它太死板了，结果导致运行成本过高，并且泛化能力较差。

<details><summary>Original English</summary>
So now we had agents that were cheap enough to run all the time and the compute to run many at once. And so then the next question was how do we orchestrate all of this work? At first we tried making like this DAG very complex system of agents composed together by like these very like strong rules and it didn't really work. You end up having a lot of the same problems that plagued missions uh in the first place because it was too rigid and as a result it was too expensive to run and it didn't generalize well.
</details>

所以我们最终确定下来的方案被称为 workstream。它是一个长期存在的目标，并由一组 agent 团队提供支持。它具备这个目标，具备身份、运行其上的环境以及记忆。一个新的 workstream 会以你的身份运行并拥有你的访问权限。当它发展到超出单人规模时，可以被迁移到拥有独立凭据的 service account 上。因此你依然作为成员保留在其中，但工作会持续在一个组织真正控制的身份下进行。

<details><summary>Original English</summary>
So what we landed on instead is something that we call a workstream. It's a standing goal with a team of agents to support it. It has this goal. It has an identity, a an environment that it runs on and memory. A new workstream runs as you and it has your access. When it outgrows one person, it can be moved to a service account with its own credentials. So you stay on as a member, but the work keeps h happening under an identity that the the org actually controls.
</details>

每个 workstream 的核心都是一个编排器，它的工作非常像操作系统中的调度器。与我们最初采用的 graph 不同，它以对模型来说最自然的方式来组装其 agent。所以指令非常简短，对吧？就像是：优先委托。给每个 agent 一个负责的领域，然后对于能够归入现有负责领域的任务，委托给它们。

<details><summary>Original English</summary>
At the center of every workstream is an orchestrator and its job looks a lot like a scheduler in an OS. Unlike the graph that we started with, it assembles its agents in whatever way is most natural for the model. So the instructions are pretty short, right? It's like uh delegate first. Give each agent an area of ownership and then for tasks that can fall into an existing area of ownership, delegate to those.
</details>

你从与它对话开始。你只是把自己想到的事情交接过去，然后它将工作扇出（fans out），以便随后能把控制权交还给你。Agent 会在完成时、受阻时，或者当发生会改变整体计划的事情时向它汇报。

<details><summary>Original English</summary>
You start by talking to it. uh you just kind of hand things over as you think of them and then it fans out the work so that then uh you can get the the control back to you. Uh agents report back when they finish, when they get blocked, when there's something that changes the plan overall.
</details>

### 自主层级与共享状态

但 workstream 并不仅限于此，因为它会自主承担更多事情，并从你的习惯中学习。在某些时候，编排器可能会询问你如何决定该做什么工作，并且它会了解到缺陷可能是来自两个 Slack 频道。

<details><summary>Original English</summary>
But the work stream doesn't just stop there because it takes on more on its own and it learns from your habits. At some point the orchestrator may ask you how you decide what to work on and it learns that maybe bugs are coming from two Slack channels.
</details>

因此在这里它可以设置一个接入和分流监听器。每隔 30 分钟，它可以去拉取来自这些频道的报告，针对现有的 Linear issues 或已存在的 Sentry 告警进行去重，然后对照 workstream 的目标权衡每一项。这样一来，一条 Slack 抱怨和一份客户错误报告就变成了一处变更。分流的输出是一份由你审查的 spec，你有能力在编写任何代码之前介入评估。一旦你批准了 spec，同一个 worker 就会提交 PR，对其进行跟进照看直到满足合并条件，并确保审查意见已处理且 CI 通过。

<details><summary>Original English</summary>
So here it can set up an intake and a triage listener. Every 30 minutes it can go in and pull in those reports from those channels, ddup them against you know existing linear issues or uh sentry sentry alerts that already exist and then weigh each of those against the workstream's goal. So a Slack complaint and a customer error report become one change. The output of triage is a spec that you review and uh you're capable of like weighing in on before any code gets written. Once you approve a spec, the same worker opens a PR, stewards it until it's merge ready uh and then make sure that you know review uh comments and CI are passing.
</details>

所以其中的每一个阶段实际上都对应着该系统中的一个自主层级。在 L1 级别，workstream 会在 spec 创建时、在提交 PR 时以及点击合并前暂停以等待人工审查。但是，随着你提升这些自主层级，你可以达到 L4，即默认自动合并一切。所有者可以设定该层级，但提高层级的信心来自对工作的观察。因此，当提议的变更准确无误，或者 PR 持续以你期望的质量合并时，那实际上就是你进入下一个检查点的信号。这也成为了你的调节旋钮。你不需要在第一天就决定是否一开始就信任一个编程 agent 来接管你的 CI 健康状况 workstream。你只需要信任它去解锁下一个检查点即可。

<details><summary>Original English</summary>
So each one of those stages actually maps to an autonomy level in this system. At L1, the workstream posits for human review at the spec creation, at the PR, and before hitting merge. But you know, as you level up that th those levels of autonomy, you can get to L4 where you're automerging everything by default. The owner gets to set the level, but the confidence to raise it comes from watching the work. So when proposed changes are accurate or PRs consistently merge at the quality that you'd expect, that's actually your cue to move to the next checkpoint. And so that becomes the dial for you. You don't need to decide on day one whether you trust a coding agent to own, you know, your like CI health workstream off the bat. You just need to trust it to to like unlock the next checkpoint.
</details>

因此在工厂中，一个从零开始的 agent 会重复前一个 agent 已经犯过的相同错误。所以我们构建了带有共享文件系统的 workstreams。Agent 正在……

<details><summary>Original English</summary>
So in a factory, an agent that starts from scratch repeats the same mistakes the last one already did. And so we built workstreams to have a shared file system. Agents are are
</details>

<!-- chunk 20/50 -->

鼓励它们保存记忆和版本化技能，因此它们的 PR 随着时间推移会变得越来越好。它们还会主动去寻找自己所缺失的上下文。举个例子，假设你的工作检测到其他人正在发布相关的变更。它就会建立一个自动化流程，把他们的 PR 拉取进来，分析他们一直在做什么工作、他们在那些 PR 中收到了什么评审意见，然后把这些内容融入自己的记忆和技能中。这样一来，一个 Agent 学到的东西，其他 Agent 也可以使用，没有任何事情是从零开始冷启动的。

<details><summary>Original English</summary>
encouraged to keep memory and version skills and so their PRs get better over time. They're also proactive and they go looking for context that they're missing. So for example, say that your work notices that other people are shipping related changes. It sets up an automation that pulls in their PRs, analyzes what they've been working on and what comments they've been receiving in those PRs, and then incorporates them into their memory and skills. So, what one agent learns, others can use, and nothing starts cold.
</details>

那个文件夹也是 Agent 们在一个项目上协同工作的方式。当 Orchestrator 生成一个 Agent 时，它能够告诉每个 Agent 它的结果大致应该存放在这个共享文件夹的什么位置。这样每个 Agent 都可以读写同一个地方。例如，如果你向一个工作流询问为什么结账变慢了，它可以派去几十个 Agent 去排查你掌握的所有不同线索。最终每一个 Agent 都可以把它的发现写进文件夹，然后 Orchestrator 可以把它们合并起来。

<details><summary>Original English</summary>
That folder is also how agents work together on a project. When the orchestrator spawns an agent, it's capable of telling, you know, each agent where does it where where does its result sort of belong inside of this shared folder. And so every agent can read and write to the same place. If you ask it a workstream why checkout got slower, for example, it can send dozens of agents out to track down all those different leads that you have. And then ultimately each one can write its findings to the folder and the orchestrator can merge them.
</details>

现在，在实现与合并之间你仍然需要一道屏障。对我们来说，那道屏障就是平台级校验。每个 PR 都会接受代码审查、安全审查，以及针对实时预览环境的专门 QA。一旦每个审查讨论串都得到解决，风险裁决器随后就会介入，判定批准它是否安全。裁决器会获取精确的 diff 以及该分支的检出代码，以便能够对其进行构建和测试。但最终，它从我们的主线分支读取其策略规则，这样变更就无法篡改判定它时所依据的规则。

<details><summary>Original English</summary>
Now you still need a barrier between implementation and merging. And for us that barrier is platform level validation. Every PR gets code review, security review, and dedicated QA against the live preview. And so once every review thread is resolved, a risk judge then goes in and decides whether it's safe to approve or not. The judge gets the exact if and a check out of the branch so it can like build and test it. Uh but ultimately it reads its policy from our mainline branch so that the change can't rewrite the rules that it's being judged by.
</details>

每周都会有一个 Droid 去挖掘审查意见，逐一梳理出作者们实际针对哪些意见采取了行动，然后把那些内容提取到类似于审查准则的规范中，从而让这个闭环随着时间推移不断改进。我们还有每天运行的 Droid，去分析例如回滚、热修复、新的 Sentry 报错，并将它们追溯到引发它们的 PR。因此，那也是输入到这同一个闭环中的一个信号。

<details><summary>Original English</summary>
Every week a droid minds the review comments and goes through figures out which one authors have actually acted on and then pulls them pulls those into like review guidelines so that the the loop sort of improves over time. We also have droids that every day run and analyze reverts, hot fixes, new sentry errors, for example, and traces them back to the PRs that that caused them. And so that also is a signal into this same loop.
</details>

我们在这里真正全力以赴提升的指标，是无悔合并率（regret-free merge rate），也就是合并之后永远不需要回滚或后续修复的变更比例。我们对 Droid 编写的 PR 和人类编写的 PR 并排进行测量。这与我们允许自动驾驶汽车上路的方式是一样的。我们并不是直接给它们放行。我们只有在它们发生事故的频率低于人类驾驶车辆时，才会这么做。所以，一旦 AI 编写的变更破坏系统的频率低于人类编写的变更，并且你确实能够测量出这一点，那么你就可以允许它们合并，而那就是将一个工作流转向 L4 级别的门槛。

<details><summary>Original English</summary>
What we're really hell climbing on here is the regretfree merge rate, the share of changes that merge and never need a revert or a follow-up fix. We measure it for droid ridden and humanridden PRs side by side. And it's the same way that we let like self-driving cars onto the road. We didn't just give them the green light. We only uh did so once they crashed less often than human-driven ones did. And so once AI written changes break things less often than human ones and you can actually measure that then you can let them merge and that's the bar for turning a workstream to L4.
</details>

工作流现在就像是我们构建新功能所基于的平台。Migrate 是第一个。它在我们的产品框架中填补了一个定位，即 Missions 曾经承担的角色，也就是这种专门的单次迁移体验；而持续修复（Continuous Remediation）是第二个，它遵循工作流最适合的那种循环形态，因为在那里面工作是永无止境的。

<details><summary>Original English</summary>
Workstream is now like the platform that we build new features on top of. So migrate is the first one. It sort of fulfills a niche in our product um like framework for for what missions used to be this like dedicated oneshot migration experience and continuous remediation is the second where it follows that circular shape that workstreams are best suited for because there the work never ends.
</details>

我们自己在工作流之上运行 Factory，这就是它在生产环境中的实际样子。在刚刚过去的十月份的一个周末里，我们在 dev 分支中发布了大约 800 个 Pull Request，其中 Droid 编写了 99%，并且审查了所有这些 PR。现在，工作落地有两种途径之一：要么是人工手动捕捉到一个信号；或者如今越来越常见的是，由工作流自动捕捉它，对照工作流的目标进行分类评估，最终编写出 Spec 并将其合并。

<details><summary>Original English</summary>
We run factory uh on top of workstreams ourselves and so this is what it actually looks like in production. In a weekend this past October, we shipped about 800 poll requests in our dev branch and Droid wrote 99% of them and reviewed all of them. Now, work landed in one of two ways. It was either a human picking up a signal manually uh or increasingly nowadays, it's a workstream picking it up uh automatically triaging it against the goal of the workstream and then ultimately writing a spec and merging it.
</details>

我们目前发布的 PR 中有 52% 直接来自工作流本身，其中一些是在完全自主运行。例如，从专门的 Slack 频道修复 Bug 报告的那个工作流，每周合并 53 个 PR。另一个是我们的不稳定测试（Flaky Test）工作流，大约合并 40 个。

<details><summary>Original English</summary>
52% of PRs that we ship right now are coming from workshops themselves and some of these are operating on full autonomy. So for example, the one that uh fixes bug reports from a dedicated Slack channel merges 53 PRs per week. Another one is our flaky test work stream which merges about 40.
</details>

不过，完全自主的 PR 并不是唯一值得追踪的事物。更重要的其实是进展过程：你的工作中有多少比例流经工作流，以及每一个工作流仍需要多少个检查点。随着更多的工作不受限制地流转，你们的工程师就成了这个系统的管理者。他们决定关注哪些信号、那些信号的目标和负责人是谁、为了保持代码的高质量你需要哪些技能和审查准则，以及每个工作流获得多少自主权。

<details><summary>Original English</summary>
Fully autonomous PRs aren't really the only thing worth tracking though. It what matters a lot more is the progression. how much of your work flows through work streams and how many checkpoints does each one still need. As more work flows unrestricted, your engineers become the regulators of this system. They decide, you know, what signals to watch, uh what are the goals and the owners of those, what are the skills and review guidelines that you need in order to keep this code high quality and how much autonomy each workstream gets.
</details>

所以，只要问一个问题，就能让你知道自己拥有的究竟是一个软件工厂，还是一群更快的工程师，那就是：你能够指明并追踪自己的信号吗？每个团队其实都已经有了这些信号。你在 Slack 里有 Bug 报告，有失败的 CI 任务、错误突增、从未有人认领的工单，但它们大多数都在等待人工去注意到。因此，我对大家的要求是把它们写下来，然后挑选出你浪费时间最多的那一个，把它交给处于 L1 级别的工作流，接着配置好我们的校验体验，这样你就在打造能够利用你选择追踪的所有信号进行自我改进的软件道路上顺利起步了。谢谢大家，我今天都会在附近回答任何问题。

<details><summary>Original English</summary>
And so there's just one question that tells you, you know, whether whether you have a software factory or faster engineers, and that is, can you name and track your signals? Every team already has them. You have bug reports in Slack, you know, failing CI jobs, error spikes, tickets that nobody ever picks up, but most of them wait on a person to notice. And so my ask to all of you is to write them down and then pick the one that you waste the most time on. give it to workstream on L1 and then set up our validation experience and then you're well on your way to building software that improves itself with all the signals that you choose to track. Thanks everyone and I'll be around to answer any questions today.
</details>

Heat. Heat.

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.

Heat. Heat.
</details>

### 递归自改进编程 Agent

大家好，我是 Era。我是 Cline 的创始工程师，今天我将要谈论递归自改进编程 Agent（RSI）。在某种意义上这是一场非常有趣的对话，因为每个人都想了解什么是 RSI、我们如何实现它、我们如何经历这个过程，以及它如何影响我们的职业生涯。所以，我首先向大家介绍整个对话的三个目标。仅仅三个简单的目标，那将有助于大家理解我们能从中收获什么，以及这方面的未来是什么样子。

<details><summary>Original English</summary>
Uh, hey guys, this is Era. I'm a founding engineer at Klein and today I'm going to be talking about recursively self-improving coding agents. So this is a very interesting conversation in the sense that everyone wants to understand what RSI is, how we accomplish it, how we go through it and how it affects our career. So I'm going to start with giving you just three goals of this entire conversation. Just three simple goals and that would help you understand like what what we get out of it and what the future uh for this looks like.
</details>

第一个目标是理解前沿实验室的意图，对吧？每一个在前沿实验室之外的人总是在揣测，比如“OpenAI 的主题是什么”或者“DeepMind 打算推出什么”或者“他们正在试图制造什么、未来会是什么样子、谁已经攻克了 RSI”。所以这有点像是能帮你大致了解他们的路线图是什么样子。第二点是，如果模型改进得如此之快，你该如何看待你的职业生涯或接下来的几年，对吧？这确实是我们想要了解的。我们想要弄明白，事情变化得如此之快，仿佛我们脚下的地面正在迅速发生位移。

<details><summary>Original English</summary>
So the goal number first is that understanding the intent of Frontier Labs, right? Everyone who's outside of the frontier lab is always trying to speculate like hey what what is the topic in open or what is deep mind going to come out with or what what are they trying to make and what's the future going to look like who has cracked the RSI so like this kind of helps you get get a rough outline of what their road map looks like and the second thing is that like if the models are improving so fast like how do you think about your career or the next few years right that is really what we want to understand we want to understand like okay things are changing so fast like the ground underneath us is shifting so quickly.
</details>

现在，曾经有段时间你可以在个人网站或 GitHub 上展示你的业余项目，而现在你简直可以使用任何前沿编程引擎单次提示直接生成它们。随之而来的感觉就是，“哎呀，我们该如何展示工作成果？我们该如何证明自己知道自己在做什么，以及我们该如何思考未来几年的职业生涯，对吧？”所以我们正生活在一个非常有趣的时代。

<details><summary>Original English</summary>
Right now like it's like uh there used to be a time when you could like demonstrate your side projects on your personal website or GitHub and now it's just like you could literally oneshot them using any Frontier Coding Engine and with that it's like it's like oh well how how do we demonstrate proof of work? How do we demonstrate you know that that that we know what we're doing and how do we think of our career for the next coming years, right? So it's a very interesting times that we're living in.
</details>

然后第三个、也是整场对话最重要的目标，就是摆脱成为永久底层阶级，对吧？我知道这听起来像是在开玩笑，但这确实是人们正在深思的一个非常现实的可能性。每个人都在想：“好吧，如果凡是我们要想做的事情，前沿模型都有可能轻而易举地完成，那我们还有什么用处？软件将何去何从？技术的未来将走向何方？随着事物演进得如此迅速，我们又该做些什么，对吧？”所以，我认为这里面存在大量的制造恐慌，但也有一些非常合理的担忧，大家担心如果地球上的所有营收都将流向几家制造前沿 GPU 的硬件公司，以及制造最佳模型的少数几家 AI 公司，那我们其余的人该如何参与进来，我们在这里该做些什么？因此，我想我将带大家了解几个例子和几种思路，它们将切实帮助大家重新审视自己正在做出的职业选择和生活抉择，以及大家所选择去解决的问题。进而那将帮助大家重新校准我们应该致力于什么，以及大家可以去从事哪些能够经受住时间考验的工作，从而帮助大家不仅在……

<details><summary>Original English</summary>
And then the third and the most important goal of the conversation is escaping the permanent underclass, right? So I know this seems like a joke, but this really is a very valid possibility that people are contemplating, everyone's like, "Oh well, if everything that we want to be doing can potentially easily done by a frontier model, like what are we what are we good for?" And like where does software go? Where where does the future of technology going to go? And what are we going to do as as things evolve so fast, right? So I think that there's like a lot of like fear-mongering but also there's like some very valid merge where people are concerned that like if all the revenue of the planet is going to go to um a few hardware companies that make frontier GPUs and then a few few uh AI companies that that make the best models like how are we how are the rest of us going to throw in what what are we going to do here? So, I think I'll I'll walk you through a few examples and a few ideas that will like really really help you reconsider the career choices and and and the life choices you're making and what your problems you're picking up. And then and then that will help you like realign what it is that we should be working on and what it is that you you know would would that you could work on that will stand the test of time and help you both just not just like on a
</details>

<!-- chunk 21/50 -->

……心理层面，但也包括财务以及其他层面。

<details>
<summary>Original English</summary>
psychological but like financial and other levels as well.
</details>

为了给大家举一个非常具体的例子，让我们从我做过的一件非常具体的事情讲起。几个月前，我想出了针对编程测试运行环境（coding harness）的递归改进方案。这可能是自动化评测改进的第一个公开示例。

<details>
<summary>Original English</summary>
So uh to give you a very precise example, let's start with something very precise that I had done. So a couple months ago I uh came up with recursive improve improvements on a coding harness. So this was the first probably public example of uh an automatic eval improvement.
</details>

举个例子，我们过去常常通过评测得分来衡量编程智能体的质量。在 Terminal Bench 2.1 上，Kimi K1.5（Kim K3）配合客户端通常会拿到诸如 60%、70% 左右的成绩；随着模型能力的提升，你在 Terminal Bench 2.1 上会得到更好的分数。我们注意到，当 Kimi K1.5 发布时，我们的得分是 77.5%，这是个不错的分数。但我们当时在想：这真的……这真的是这个模型在该基准测试上能拿到的最高分吗？还有，该模型的发布论文声称他们能达到的最高分是多少？模型的发布论文说他们可以拿高达 85% 甚至更高的分数。

<details>
<summary>Original English</summary>
So to give you an example u we used to do this thing where we would measure the quality of a coding agent using evaluation scores. on terminal bench 2.1 Kim K3 with client would score um usually like you know um 60 70% and then depending on like how good the model is like you get better scores on on terminal bench 2.1 so we noticed that when Kim K3 came out our score was 77.5% which is a good score but we were like oh is this is this truly is it truly the best score that this model can get on this benchmark and also like what does the model release paper claim about what their best score is so the model release paper said that they could score up to 85% or even more.
</details>

所以我们就觉得，好吧，既然我们没有拿到那种分数，而通常我们在客户端针对新发布的模型所做的工作，就是努力优化得分，尽力榨取该模型的最大潜能。因此，当我们开始针对该模型进行爬山算法式（hill climbing）优化时，我们意识到，为了体面地解决问题、为了确保我们瞄准正确类型的问题并以正确的方式处理，我们做了大量的步骤。我们便开始思考：既然这里有大量的基础工作，我们该如何将其自动化？这就是我们如何将其自动化的演示。我先把它作为一个占位符放在这里，稍后我们会详细探讨客户端测试运行环境的这种自动化改进闭环究竟是如何运作的。这基本上意味着，你拥有了一个可以自我改进、并在同一组问题上变得越来越好的编程测试框架。

<details>
<summary>Original English</summary>
So we were just like okay okay so we are not getting the sort of score and often what we do with model releases in client is that we try to like optimize your score and try to get the best out of the model. So when we started hill climbing on the on the model like we we realized is we realized that like you know there's a lot of steps that we do says that we do it gracefully says that we pursue the right kind of problems and do it the right way and we started thinking like okay if we there's a lot of ground work here how do we automate it and this is a demonstration of like how we automated it. So I'll I'll just leave that as a placeholder for now and we'll get get back to it later where we talk about in detail of like how does like this automatic improvement loop of a client harness work. So this basically means that like you have a coding a harness that could just like basically improve itself and become better on on the same set of problems.
</details>

### 递归自我改进与发展脉络

让我们从基本概念讲起。什么是递归自我改进？递归自我改进是指这样一个理念：一个 AI 系统能够帮助构建出一个能力更强劲的后继系统，而该后继系统不断重复这个过程，直到达到通用人工智能（AGI）。系统越来越好，改进越来越大，系统愈发强大，然后就达到了技术奇点。一个典型的例子就是自我迭代进化的编程智能体；自我进化的编程智能体就是一种能够改进自身的编程智能体。大家都知道，这在过去完全是一个空中楼阁式的设想，大家会觉得：“对，这看起来很酷，但它是怎么一步步演进出来的？我们到底是怎么走到今天这一步的？”

<details>
<summary>Original English</summary>
So let's start with the ground terms. What is recursive self? Recursive self-improvement is the idea that an AI system that helps build a more capable successor which repeats the process you know until you hit artificial general intelligence right you have better systems you have better improvements you have a better system and then you know you have singularity so a classic example is like a self-reing coding agent right self-reving coding agent is just like a coding agent that can improve itself so you know this this is all like a pie in the sky idea like it's like it's like you know yeah sure this looks cool but how how did this even come out to be like how we even get to here.
</details>

如果你注意到 Anthropic 在 2021 年的发展路线图，他们在 2021 年的路线图中非常明确地表示，他们希望开发出一款通用 AI 助手，能够以对话的方式与用户互动，从而创建、编辑并解释软件。它将展现出作为一名软件工程师同事所具备的一切能力：它能编写函数、发现缺陷、设计 API，并讨论代码风格和最佳实践。我们并不指望能立即达成这个目标，但这正是我们努力的方向。

<details>
<summary>Original English</summary>
So if you notice in topics road map in 2021 in 2021's road map they very specifically said that uh uh they wanted to develop a general AI assistant that can interact conversationally with a user to create edit and explain software. It would display all the capabilities of a software engineer colleague. It would write functions. It would identify bugs. It would design an API discuss style and best practices. Right? So we don't expect to reach this goal right away but it's in the direction which we're striving.
</details>

很有意思的是，这已经是五年多前的事情了。五年多前，人们就预言终有一天会出现一个能够完全充当人类同事的成熟通用助手，而我们现在确实拥有了这样的助手。随后在 2022 年，ChatGPT 发布了。我们都知道那是如何发生的，那是一个令人兴奋的时刻，是火花第一次在我们身边点燃。

<details>
<summary>Original English</summary>
It's interesting how this was more than five years ago. More than five years ago, people had predicted that there exist a day where you will have like a full-blown journal assistant that can basically act like a colleague, which we do have right now. Um, then in 2022, Chad Deputy got released. We all know how that happened. It was it was a fun moment. It was like the first time things got sparked for us.
</details>

到了 2023 年、2024 年，对话模型第一次具备了调用函数的能力。这些函数都是些简单的函数，比如查询天气，或者计算某个 Python 运算的结果。最终在 2024 年，随着 Claude 3.5 Sonnet 的发布，智能体终于能够真正调用我们传统认知中的各种工具了，比如读取文件、编辑文件、在网络上搜索信息、列出目录内容、在文件系统中进行搜索和 grep 等等。

<details>
<summary>Original English</summary>
Um, then in 2023, 2024, there was the first time chat models could call functions. These functions would be simple functions like hey what's the weather or you know what's the what's you know what's this competition over this computations result in Python. Um and then finally in 2024 when s 345 was released that was when the agents could like truly call like actual tools the way we call like think of tools. So it's like reading a file editing a file you know reading searching something on web uh listing listing a folder searching and grapping through you know uh a file system things like that.
</details>

在 2024 年，我们产生了一种直觉：如果聊天机器人之间能够相互对话会怎样？于是那是我们第一次拥有多智能体对话。当时这些方案非常简陋，它们只是以极其古怪别扭的方式拼凑在一起，堆砌着各种类、依赖关系和类层次结构。这一切都像是非常蹩脚的尝试，试图让我们觉得这些模型形成了一个可以相互通信的响应流水线。其中很多基本上是确定性的，并不像现在这样行云流水。

<details>
<summary>Original English</summary>
So and in 2024 we had the intuition that like chatbot what if chatbox could actually talk to each other you know so then that's was the first time when we had like you know uh multi-agent conversations now at the time these things were very janky right like they were just like taped together in this like weird weird uh bizarre ways where you have just like these classes and these links and then like these hierarchies of classes and it was like it was all like kind of like a very janky attempt to like make us think that like these these models to like have these pipeline of flows of responses that can all communicate with each other. A lot of it was like mostly deterministic and it was like you know it was not as free flowing as it is right now.
</details>

这就是 AutoGen 项目。但在 2025 年，我们开始设想：要是智能体不断变得更强、更快、更便宜呢？如果这种趋势一直持续下去会怎样？接着在 2026 年，我们又有了新的直觉：要是智能体能够改进自身呢？这就是整个演进过程的终局。

<details>
<summary>Original English</summary>
So and you know we started getting the intention. So this was the autogen project but like in only in 2025 we we started getting the like what if the agents just kept getting better and faster and cheaper like what what if that just kept happening and then in 2026 uh we we had the intuition that like what if what if the agent could improve itself which is like the final you know the final part of the whole process.
</details>

### 智能体评测与基准测试

让我举个例子说明智能体自我改进到底意味着什么。很多时候，当我们谈到评估一个智能体时，我们起初习惯将其视为单轮对话的评估形式。比如我们会给智能体提一个简单的问题：“某某动物有多少个脚趾？”比如说，问猫有多少个脚趾，然后模型便去处理并组织回答，接着我们得到回复：猫可能有 10 个脚趾、18 个脚趾，或者不管多少个——我其实并不知道猫到底有多少个脚趾。无论如何，然后我们就将该回答判定为对或错。

<details>
<summary>Original English</summary>
So let me give an example like what does it mean for an agent to improve itself right? So like it's like a lot of times when we think of like evaluating an agent, we initially used to think of evaluating an agent in the form of like just a single turn conversation. So we would tell we would tell like um um agents that like ask a simple question like how many toes does a dash animal has? It's like it could be let's say how many toes does a cat have and then al would go through and the element would like prepare response and then we would get the response. So like a cat has maybe 10 toes, 18 toes, however many. I don't I actually don't know how many toes a cat has. But anyway, um yeah. So then we create the response as like a yes or no.
</details>

但是当你在实际中使用智能体时，你要做的事情有非常多。举个例子，比如你要求智能体：“帮我配置这个 MCP。”此时这不再是简简单单一次成型（oneshotable）的简单任务了：它需要去网上搜索，弄清楚什么是 MCP、配置文件是什么样的；接着下载并编辑一些软件配置文件；可能需要添加数据库或更新 MCP 工具；可能需要读取和编辑某些文件；可能还需要运行一些 bash 命令。完成了这一切之后，智能体回复说：“我已经做好了。”接下来你需要用一系列测试来进行打分，以此评估：智能体是否真的完成了它声称要做到的事情？

<details>
<summary>Original English</summary>
But like when you work with an agent, there's a ton of things that you're doing. So let me give an example. Let me give an example. So for example, you're going to ask an agent like hey set up this MCP for me. So now it's not just like it's not just like you know a trivial oneshotable like thing like it will like search online and go what's the MCP? what is the config? So, I'll like edit and download some soft files. Like maybe I need to add database update the MCB tool. Maybe I need to read and edit some files. Maybe I need to run some bash commands. Right? So, you do all of that and then the agent response like, hey, I did it. And then you grade that with a bunch of tests to gauge like, hey, did the agent actually accomplish the thing that it said it would do?
</details>

为了完成第二部分——即更复杂的、真正最大限度测试智能体能力的部分——我们使用了一个叫作 Terminal Bench 的工具。Terminal Bench 是一个针对终端环境中的 AI 智能体的基准评测体系，我们在客户端在这方面积累了大量的经验。这是真正衡量你的编程智能体大体上是否在完成你希望对应模型所做任务的最佳方式之一。

<details>
<summary>Original English</summary>
So to do that thing the second part which is like more intricate where you're actually like truly you know testing agents like uh to their best extent like it's like you know um we use this thing called terminal bench. terminal bench is a benchmark for you know AI agents in terminal environments and that is something that we are we have a lot of like experience with at client and uh it's like a it's like one of the best ways to like really gauge like is your coding agent accomplishing uh in general the task that you're doing uh that you want to be doing with age model.
</details>

评测套件由很多不同的部分组成。理想情况下，你希望它在独立的沙箱环境中运行。然后你需要独立的评分器来检查所有的指标，比如花费了多少轮交互、消耗了多少 token、产生了多高的延迟、发起了多少次工具调用、整个执行轨迹是怎样的；接着评估所有的结果，核查是否存在为了获取奖励而钻空子作弊（reward hacking）、是否在解法中投机取巧，或者是否仅仅是在网上查找答案等等。基本上，很多此类评测问题的数据集都包含一组任务。在 Terminal Bench 2.1 中，他们有 89 个任务。

<details>
<summary>Original English</summary>
So there's a couple there's a many different parts of evaluation suit. So ideally you want that to run in um you know you you want that to run in um individual sandboxes. Then you have like independent graders that like check everything like how many turns it took, how many tokens it took, how much latency it took, how many how many how many tool calls did it make, what was the trajectory looking like and then grading all the results for things like hey did you not reward hack? Did you not cheat through the solution? Did you not just like look up the solution online? Things like that. Um so we we basically like a lot of these uh data sets of evaluation problems have a set of tasks. So when a terminal bench 2.1 they have 89 tasks.
</details>

<!-- chunk 22/50 -->

### 评估与测试框架自动优化

所以我们的做法是，启动 89 个并行容器，它们全部在线运行，并行运作且彼此沙盒隔离，然后各自尝试解决一个问题。这样它们就完全处于并行状态，并且相互独立。最后我们会得到一个分数。这个分数能为我们提供一些衡量指标，比如模型表现是否良好，以及出现了哪些类型的故障。你运行评估，得到一个分数，也就是一个综合总分，而这个综合总分能揭示一系列故障。故障可以是任何类型的，比如：read file 工具无法正常工作；有时则是推理太慢，智能体虽然在工作、在推进、可能在兜圈子，但速度实在太慢，以至于彻底超时——耗尽了为该任务分配的比如 45 分钟左右的时间，然后就直接停止工作了。一旦你完成了这一步，弄清楚了“我们运行了这些任务、遇到了这些故障”，我们就会把故障分门别类归入不同类别。比如，某类工具调用出现 10 次故障，推理失效或其他原因出现 10 次、20 次故障。将故障归类后，我们就尝试对测试框架（harness）进行改进，因为如果测试框架本身存在问题，我们对其进行修改，模型的得分说不定就能提高。如此周而复始。

<details><summary>Original English</summary>
So what we do is like we spin up 89 parallel containers where they all run online and they run in parallel and they're sandbox and then they each try to solve a problem. So then they're all uh in parallel and independent of each other. And then at the end we get get a score. So our score could like give us measures like is is a is this is the model performing well and what kind of failures it has right so like you run the evaluation you get a score so you get an aggregate score and there aggregate score could reveal a set of failures okay failures could be of any kind failures could be hey the read file tool is not working sometimes the entrance is so slow that like you know the agent's working it's doing it's making progress maybe it's running a circle but it's so slow that it literally like runs out of time it runs out of like 45 minutes or where that were given for the task and just like stop working. So once you do that once you understand hey this is what we ran this is what the failures we got we bucket the failures in different categories. So like 10 failures of you know this kind of tool called 10 10 20 failures of like say inference not working or something else right and then we once we bucket the failures into different categories where like we try to make an improvement to the harness because like what if there's like something wrong with the harness that we could change such that the model score would improve right and on and on and on
</details>

你反复迭代这个过程，这需要花不少时间。爬山算法（hill climbing）就是一种非常磨人的基础性工作。通常我们过去要花很多时间做这件事，但这对我们来说是学习如何改进模型的一个极佳途径。

<details><summary>Original English</summary>
and you do this iteratively it takes a while it's just like you know hill climbing is like a very groundworky kind of process and you know usually usually we we took we used to take a lot of time trying to do this but it was a great way for us to like learn how to improve models.
</details>

在此基础上进行爬山优化的一种方法是：我们能不能做这样一个东西，就是设置一个长时间运行的智能体，让它持续运行一段时间并自动提升模型分数？我们确实这样做了。我们运行了 GPT-5.6 来主导这项工作，它充当主智能体，然后由 Ky K3 专门负责运行评估。它的工作机制是：GPT-5.6 会发出指令：“去运行这些评测，拿到这些分数，让我看看具体的故障，看看哪里出了问题；然后我会对客户端的测试框架进行修改，再重新运行这些评估，继续不断尝试。”

<details><summary>Original English</summary>
So one way to hill climb on top is that like you know we we could have a thing where you know we started doing this thing where we could just like what if we could have like a longunning agent that runs for a while and automatically improves the model score and that's what we did. So we ran GPD 5.6 soul that led the work and that was like the main agent and then uh Ky K3 was just running eval. So what it was doing is that like GBD 5.6 was like hey run these events get these cores let me look at the failures let me look at where where it went wrong and then I'll make changes to client's harness and then I'll run these eval again and then I'll keep trying.
</details>

所以再次说明，你可以看到这个过程很容易失控，因为运行一次评估本身就要花大约一个小时。接着你必须阅读反馈，然后看自己是否正确理解了反馈，以便对测试框架做出合理的修改——这些修改不能是奖励黑客行为（reward hacking），而必须是实实在在的真正改进——然后再重新运行评估。我们让它运行了 17 个小时。当运行了 17 个小时后，确实出现了实质性的爬山式提升。我们发现了一个非常有趣的现象，这是在一段完成此任务的极其详尽的提示词引导下实现的：我们的基准得分是 27%，然后我们发现了一些问题，比如循环检测（循环检测是指测试框架在某个问题上反复兜圈子）、后台进程过度消耗（后台进程运行时间过长），此外还发现了一些文件索引问题等等。我说“我们”时，实际上指的是 5.6 独立完成的。它发现了这些问题，并将它们归类，然后像是在说：“要不我对测试框架做些修改，再跑一次评估。”它完全自主地、独立地、无需我介入就逐步构建起了爬山优化过程。13 个小时后我回来看，它已经在诸多方面提升了测试框架的性能。

<details><summary>Original English</summary>
So again, you can see how like very quickly this can like go off the rails because this is supposed to be like the running and evaluation itself takes like an hour. Then you have to read the feedback. Then you have to like see if you're properly interpreting the feedback to make reasonable changes to the harness that are like not reward hacking that are just like actual genuine improvements and then run the eval again. So we ran that for 17 hours and uh when we ran that for 17 hours there was like a legitimate hell climbing and what we found that was very interesting. This happened with a very detailed prompt that accomplished this is that like we had baseline score of 27% and then you know we we found issues like loop detection loop detection is when a harness just runs in circles around a problem right uh we found like background process grinding where background processes would run too long uh we found some file index issues and other things as well I mean when I say we what I actually me 5.6 solve right so that found those issues that found and bucketed those issues it's like hey how about I make those changes in the harness and I run the eval again and it iteratively built the hill climbing process completely autonomously on its own without my interference and 13 hours later when I come back to it like it has improved the harness's performance in so many ways
</details>

这说明了什么？它的根本含义在于，我们已经达到了这样一个阶段：经验可以让测试框架变得更好。这里存在一个工具层面的学习循环——测试框架执行某种操作，与环境交互，理解自己做对了还是做错了，并获得一定的奖励；同时几乎就像有一个元智能体（meta agent）在观察主测试框架，找出需要对其进行的改动，直接融入这些改动并实现自我改进。我个人认为，在实时环境下做这件事要难得多，因为如果是实时进行，你很容易在解决某些特定问题上过度拟合，或者局限在某个具体的事情上。但我确实认为，这种机制在大规模场景下是行得通的，适用于更广泛的问题域；并且你希望能够证明所做修改具备更广泛的适用性，这样在此处所做的改动也能应用到更宽泛的问题上。

<details><summary>Original English</summary>
so see what does that mean what does that mean it just it just basically means that like we're at a point where the experience could make the harness better that like there's like a tool level learning loop where the harness does some action, interacts with the environment, understands whether or not it did the right thing or the wrong thing and gets some reward and and like almost and then has there's like a meta agent that's observing the main harness and finding the changes to it and just like incorporating those changes and improving. Now it's I think in my personal opinion it's much harder to do in real time because if you do it in real time you overindex on solving certain problems or you're just like too cartel to a specific thing. But I do think that this is something that works like on a broader scale of like working on a wider range of problems and you want to be able to like you want you want to be able to justify the changes you're making on a broader applicability so that the changes you make here will apply to a broader range of problems as well.
</details>

### 全栈自我改进与底层算子优化

那么这意味着什么？我这里到底想表达什么观点？我想说的核心观点是，目前的模型已经非常强大，如果它们能够改进测试框架，它们就能够改进许多其他东西。那么，它们还能改进什么呢？

<details><summary>Original English</summary>
So what does that mean? Like what am I trying to get at here? The point I'm trying to get at is that the models are so good right now that they can if they can improve the harness, they can improve a lot of other things. So then what else can they improve?
</details>

这是一篇主要来自 OpenAI 的发帖：GPT-5.6 自主重写并优化了其自身的生产内核（production kernels），这些生产内核的改进将端到端服务成本降低了 20%，同时 token 生成效率也提升了 15%，而这完全是 5.6 独立搞定的。这意味着推理正在变得便宜得多；对于像 OpenAI 这样的公司来说，前沿模型的服务成本降低 20%，可能意味着数十亿美元的成本优化，而在你自己的模型上你同样可以做到这一点。

<details><summary>Original English</summary>
So this is this is a this is a post uh primarily from OpenAI where GP 5.6 autonomously rewrote and optimized its own production kernels and those production kernel improvements remove the end to-end serving costs by 20%. you know it also had 15% higher to token generation efficiency and this was like completely done by 5.6 soul on itself, right? So what that means is that like inference is becoming much cheaper and that means that like if on if if for a company like OpenAI if you're having 20% low lower serving cost for a frontier model that could be a billions of dollars of improvement in price and you could you could do that as well for your own models.
</details>

另一个有趣的现象是，当人们举办算子编写比赛时——CoreWeave 是一家举办算子编写比赛的公司——你会注意到他们提到，赢得该算子编写比赛的人明确表示：“我从未手写过 GPU 算子，全是靠大语言模型和智能体驱动的。”所以请注意，目前最顶尖的推理改进、内核优化，已经完全、纯粹是由智能体集群完成的，或者说普遍是由智能体施展某种魔法来奇迹般地改进内核代码，从而实现更快、更便宜的推理。

<details><summary>Original English</summary>
Um another interesting thing is that like when people have kernel writing uh competitions so core auto is a company which has a kernel writing competitions and you'll notice that like they they mentioned that like the person who won the kernel writing competition the explic said that I have never handwritten a GPU operator it's all ALM and agent driven so notice that like how like the best uh inference improvements kernel improvements are at this point completely exclusively done by a swarm of agents or generally like agents doing some magic to you know magically improve like the kernel kernel code and have faster inference cheaper inference.
</details>

所以基本上，你所考虑的改进层面绝不仅仅是测试框架的改进，而是贯穿整套技术栈：从评估、到测试框架改进、到训练数据、到后训练（post-training）、到与现实世界交互、再到推理，可以说是整个流水线的所有环节。从电流穿过你的机器，到发起网络请求、流经模型、模型执行推理、生成响应并返回给你——流水线的每一个环节，我们都可以进行优化。

<details><summary>Original English</summary>
Um yeah so basically like the improvement surface that you think of is not just like the harness improvement it's literally the whole surface stack right so the whole stack from like evaluation to harness improvements to training data to post training to world interaction to inference like literally the entire pip part of the pipeline like all the way from like electricity going through your machine to like making a network request going through the model models doing inference um making a response and getting back to you like every single part of the pipeline we can optimize it.
</details>

整个 RSI 循环包含几个不同的部分：比如预训练，有通过 AI 策展的高质量预训练数据这类例子；还有后训练的例子，比如宪法 AI（Constitutional AI）这类后训练改进的例子；然后是推理，我刚才给你们举了 GPT-5.6 的例子；至于评估生成，我举了我们自己如何在自己的评估基准上提升自我的例子。总体来说，你要考虑的是，任何时候模型试图做某件事却无法做到或无法完成时的情况。举个例子，假设你正在进行一段漫长的对话，你向模型询问一个显而易见的问题——或者说是你觉得未必显而易见、确实有难度，但你认为模型有可能做到的事情。举个例子，假设你想在数据库中添加一个新列，然后填充该列的数据，接着在它前面加上缓存。结果发生的情况是，它把整个流程都做了一遍，但出于某种原因，它把缓存置于整个数据库前面的方式似乎并没有达到预期

<details><summary>Original English</summary>
So the whole RSI loop has like um there's a couple different parts so it's like pre-training um uh neatron examples of like you know AI curated uh pre-training data that was good um there's like post- training examples which are you know where there's like constitutional AI examples of like post- training uh improvements then inference I gave you the example of GP 5.6 So for eval generation, I give you our own example of how we improved ourselves on our own eval. Um, in general, what you want to think of is that like anytime a model is trying to do something and it's like not able to do it or not able to accomplish it. So for example, like imagine you're having a long conversation where you ask the model something obvious. So like it's like or something that you think is not necessarily obvious, but it's like it's hard, but you would assume that the model could potentially do it. So to give an example, let's say you want to make add a new column to a database and then fill that column, right? And then put a cache in front of it. So what happens is it does the whole thing, but for some reason the way it pushes the cache in front of the whole uh database like it kind of doesn't do it
</details>

<!-- chunk 23/50 -->

对吧。所以在那个节点上，你就会说：“噢不，把这个缓存设成别的方式，把这个设为 TTL。”然后你给出类似纠正信号的反馈，这就大致解决了你的问题，接着你就能继续忙自己的事了。

<details><summary>Original English</summary>
right.

So at that point you're like, "Oh no, set this cache differently. Set this as the TTL." And then you give like a correction signal and then that kind of like fixes your problem and you kind of go about your day.
</details>

我想把它理解为：人类对数字环境的每一次纠正，都是一段需要被弥合的增量差距（delta）的一部分。这意味着，每次你发现模型能力的边界——比如它在推理上能推进多远、在这件事上能推进多少、在解决你的问题上能推进多少——你都想找到那个差距，而我们希望把这个前沿一步步推得更远一点、再远一点。这就是后训练（post training）所做的事，对吧？后训练就是这样，在后训练中，我们为编程智能体或其他类型的问题找到这些非常有趣且非常硬核的远期问题，然后在这些问题上慢慢对模型进行爬山式优化（hill climb）。

<details><summary>Original English</summary>
The way I want to think of it is that I want to think of like every single time like a human correction to the digital landscape is a part of a delta that needs to be covered. And what that means is that like every single time you're finding like the edge of model capabilities of like how far it can push for infants, how much it can push for this, how much it can push for, you know, solving your problems. You want to find that delta and we want to like push that frontier a little bit further. a little bit further and that's what post training does, right? So post training is is this is in that post training we find these like really interesting and really hard long horizon problems for uh for coding agents or for other kinds of problems and then just like slowly hill climb the models on on those kind of problems.
</details>

因此，任何拥有可验证闭环的事物都可以被优化，但这并不仅限于软件，甚至物理世界本身也可以拥有可验证闭环。举个例子，让我给大家举一个非常好笑、有点离奇的例子。你看这个，你看这个机器人，它正在打字，而且它打出的内容真的非常非常有趣。

<details><summary>Original English</summary>
So anything that has a verifiable loop can be optimized but is this is not just limited to software like literally like the physical world itself could have a verifiable loop. So to give an example like let me let me give you a very funny kind of bizarre example where like it's like you you look at this and uh you um um look at this uh like robot and it's it's typing something and it's like really really like interesting what the robot is typing.
</details>

注意看机器人自己是在打字输入它想如何解决机器人学问题。想象一下，如果机器人自身能够解读这些答案的结果并不断自我改进，那就意味着这基本上就像是一个 ASI（人工超级智能）机器人了。

<details><summary>Original English</summary>
So notice how like notice how the robot is itself typing like how it wants to like solve robotics and imagine if the robot itself could like interpret the results of of like the answers and just like keep improving then that means that like this is you know basically like an ASI robot.
</details>

我可以从我个人生活中举的另一个例子是：我手头有这么一块芯片，它具备视觉能力，里面还有一个扬声器和一个麦克风。我当时正试着用我的电脑把它设置好，这是我送给我女朋友的礼物。而在设置过程中我发现非常有意思的一点是，它运行非常缓慢，响应很慢，延迟较高，它本身内部就带有一个智能体，对吧？于是我做的是把这块芯片连接到我的电脑上，让编程智能体在这个硬件上运行，基本上就是在这个硬件上自动对其进行测试。

<details><summary>Original English</summary>
Another example that I could give you for my uh personal life is that like um I have this um chip that has the ability to see and has a speaker and has a microphone inside of it. So I was trying to set up this uh with my machine and it was um a gift that I had for my girlfriend. And uh what I found very interesting about this is as I was trying to set it up, it was very slow. It was slow to respond. It had higher latency. It had an agent in and of itself. Right? So what I did was I connected the step to my um computer and I let um I let um putting agents run on this hardware and basically run on this hardware automatically make tests to it.
</details>

我的电脑会与我的硬件对话，给它一些测试，比如“嘿，做这个，做那个”，以及“你现在看到了什么？”接着它就会注意到端到端延迟，也就是推理响应的耗时，看我的硬件响应到底有多快。随后我发现，它能够分解出出现高延迟、响应变慢或者算法不对的每一种具体用例与场景。然后我就可以建立一个递归闭环：固件、工具调用、所使用的推理模型、所使用的语音转文本模型，所有这些都可以通过我给编程智能体的一个 OpenRouter 密钥自动完成改进。接着在一夜之间，通过对硬件进行的自主运行实验，我拥有的这个精巧漂亮的小硬件得到了深度优化。所以说，连硬件都可以成为 RSI（递归自我改进）闭环的一部分。

<details><summary>Original English</summary>
So like my computer would talk to my hardware give it some tests like hey do this do that and just like what do you see right now? So then it would notice the end to end latency of like the inference response of like how fast uh my hardware is responding and then um what I found is that like it was able to do the breakdown of like every single case and scenario where there was like high latency um slower response or or just the algorithm wasn't right and I could then set up a recursive loop where both the firmware could be updated the um the tool calls the inference model used um the speech to text model used all of those could be improved automatically with like an open router key which I'd given to a coding agent and then overnight with self-running experiments with the hardware uh my um this tiny little piece of beautiful hardware that I have was like deeply optimized so this also like even hardware could be a part of the RSI loop
</details>

### 靠近 RSI 闭环与选题思考

那么当你把这些闭环串联起来时会发生什么呢？对吧，这就是下一个问题。你可以拥有更廉价的推理，可以拥有更多的实验预算，你还能拥有更好的数据与更好的模型。所以，这是奇点吗？这是一个非常值得探讨的问题。我认为这个闭环的各个部分已经很离奇了，对吧？我们真的已经非常接近 RSI 闭环的部分环节了，对吧？面对这种情况我们该怎么做？从我们的职业生涯角度该如何看待它？从我们的生活角度又该如何看待它？我们接下来想要做什么？

<details><summary>Original English</summary>
so what happens when you connect these loops right that's the next question like you could have cheaper inference you could have like more experiments budget you have like you know better data and better models. So, is it singularity? It's a very question to ask and I think that the part of the parts of the loop are already weird, right? Like we're we we are really we really are very close to parts of the RSI loop, right? And what do we do like what do we do about this and it's like how do we think of that in terms of like our career and how do you think of that in terms of you know our lives and what do we want to do next?
</details>

所以我给所有看这个视频的人的建议是：请大家、请务必尽量靠近 RSI 闭环。对吧，现在人们正在做所有这些各色各样的软件，比如做给建筑业的智能体、做给这个的智能体、做给那个的智能体。而在我看来，我认为这就像是一叶障目、只见树木不见森林，真的就是这样。你手里握着这种能够改变人类局部面貌的、极具开创性的神级技术，然而我们却没有足够的雄心去攻克最顶级的问题，真的没有。而且我认为问题不仅在于我们缺乏雄心，也在于我们所追求的方向。其中很多东西距离被完全淘汰，仅仅就差下一次模型发布而已，对吧？

<details><summary>Original English</summary>
So here's my advice to everyone who is watching this like please please please please move closer to the RS group right so it's like right now like people are working on all these like different kinds of software which is like you know a agents for you know construction agents for this agents for that and it's like I think that you're you know what the way I see those things is that like I think of those as like you're missing the forest for the for the trees you really are and it's like you have this like very interesting godlike technology that can change parts of humanity. And then we're not ambitious enough to pursue the best problems. We really are not. And we're just like I think that it's not just like the problem isn't just that we're not ambitious and we're also like what we're pursuing. A lot of those things are just like one model release away from like being completely like wiped out, right?
</details>

而且在智力上也可能没那么有启发性，因为基本上我们整天做的全部事情就只是坐在那里：“嘿 Claude，帮我做这个；嘿 Claude，帮我做那个。”我不知道这算不算一个人时间的最具智力启发性或最有深度的用法。也许我们本应该去解决更困难、更前沿的问题，而且我认为这个上限取决于我们的雄心。

<details><summary>Original English</summary>
So like it's also like it's also like it may not be that intellectually simulating because like all you're essentially all we're essentially doing is like sitting all day. It's like hey cloud do this for me. Hey cloud do this for me. And I don't know if that's like I don't know if that's like the most intellectual stimulating or like or like um thoughtful use of a person's time like maybe maybe you know we're supposed to be solving harder and more uh more frontier problems and I think that like it's like the ceiling is like our ambition.
</details>

因此，我的建议不是去做这一类事情，当然这不用多说，你应该做自己坚信的事情；而且我也只是互联网上的一个普通人，但请去做那些能帮助你更靠近 RSI 闭环的事情，对吧？做任何能够触及端到端流水线的事情，去找到“看，这就是模型所欠缺的地方”——无论那是推理、是后训练，还是切切实实的物理交互；无论是任何类型的端到端流水线；无论那是硬件问题、网络问题，还是构建感知社区；去做那些能帮助你作为一名工程师更直接享受到模型改进带来的收益的事情。

<details><summary>Original English</summary>
So instead of like working on these kind of things my suggestion to people is to like you know do things that of course like goes without saying but you should do things you believe in and you know I'm just a guy on the internet but do things that help you move closer to the RSI loop right? So like anything that just like the end to end pipeline of like hey this is where like the models are lacking like it's like whether that's inference whether that's post training whether that's literally like physical interaction whether that could be you know send sending end to-end pipelines of truly any kind you know whether that's hardware problems whether that's um networking problems whether that's um building a sense community things that just you know um things that just like help um you as an engineer get closer to the benefit benefits of the improvements um in uh in uh um in in the model.
</details>

这是来自 Sasha 的一张非常有趣的幻灯片。他们提到，你正处在这样一个空间里：你只剩下一到五年的时间来为世界贡献力量了。你该怎么做？对吧？他们给出了极好的建议，比如：优先选择雄心勃勃、目标明确且注重过往经验的合作，对吧？总的来说，在你给自己的所有时间线上，都应该被彻底压缩，必须被彻底压缩。因为很多时候你也必须想清楚：如果你正在攻克的问题过于宏大，那么等待下一个前沿模型的发布是不是可能会更好？这也是你必须权衡的事情，对吧。

<details><summary>Original English</summary>
So this is a very interesting slide from Sasha topic. So um um they mentioned that like you want to have like this you're in this space where it's like you know you only you only have like one to five years left to contribute to luxury to the world. What do you do? Right? So it's like um they they gave great suggestions were like prefer ambitious targeted and past collaborations right and you know in general like the time scale like all the timelines that you give to yourself like they should be just like completely squeezed out should be completely squeezed out because it's like a lot of times and you also have to think through that like if if the model if the problem that you're working on is too ambitious like it's like is it probably is it probably better to wait for just like the next next frontier model to come out or not like that's that's something you also have to weigh through Right.
</details>

在理想情况下，你希望去解决能从规模化中获益的问题；同时，你也希望避开那些仅靠规模化就能解决的问题，因为否则的话，哪怕你在做一个问题，一旦下一个模型版本发布，它就把问题解决了。所以那可能并不是一件好事。你必须从哲学层面去思考：什么样的探索能够极大地受益于自动改进，但又不会被其彻底冲垮？在理想情况下，如果这项探索本身也能成为改进流水线的一部分，那就太棒了。所以你会看到许多公司在诸如构建数据流水线等方向上进行融资，那里有大量的资金；也有很多公司在从事物理硬件等方面的研发。因此我认为，如果你是一名正在观看本视频的软件工程师

<details><summary>Original English</summary>
And uh you you ideally want to work on problems that benefit from scale and you know you also at the same time want to avoid problems that can be solved by sale alone because then you know if even if you like it's like if you're working on a problem and then the next model release comes out it solves the problem. So that's not that's probably not a good thing to do. So it's very like you have to like think philosophically of like what is the endeavor that benefits uh greatly from auto improvements but like isn't also completely wiped out from it. And then ideally like it's like if the if the endeavor could also uh be a part of the the like the improvement pipeline uh that could be amazing. So you see a lot of companies raising on say um making data pipelines and there's a lot of money there. There's a a lot of companies working on physical hardware and stuff. So I think if you're a software engineer watching
</details>

<!-- chunk 24/50 -->

这些……我认为，如果你觉得在日常工作中，你的智力和能力的增量并没有产生贡献——也就是说你虽然具备智力，能够带来改变，但如果 Claude 在你的日常工作中直接一步搞定所有那些问题，而你只是逐渐变成了一个代理人的话，那是值得去仔细想清楚的。退一步好好想清楚：究竟在哪些问题上，你才真正做出了贡献，且这些贡献能够经受住时间的考验。我认为，眼下进行这种反思和调整，长远来看会为你带来非常深远的影响。

<details><summary>Original English</summary>
 these,

 it's





like

 I

 think

 that

 if

 you're

 if

 you

 feel





like

 you're

 like

 here

 the

 delta

 of

 your





intellect

 and

 ability

 in

 your





day-to-day,

 it's

 like

 not

 contributing





as

 in

 like

 you

 have

 the

 intellect,

 you





can

 make

 a

 difference.

 But

 like

 if

 cloud





is

 just

 like

 oneshotting

 all

 those





problems

 like

 in

 your

 day-to-day

 and





you're

 just

 like

 kind

 of

 like

 becoming

 a





me

 proxy,

 it's

 worth

 to

 think

 through.





Take

 a

 step

 back

 and

 think

 through.

 like





okay

 where

 are

 the

 problems

 where

 where





you're

 actually

 truly

 uh

 contributing





and

 that

 they

 will

 stand

 the

 test

 of





time

 and

 then

 that

 kind

 of

 reflection





and

 realignment

 right

 now

 would

 I

 think





like

 have

 like

 very

 interesting





consequences

 for

 you

 um

 in

 the

 long

 term
</details>

所以，非常感谢大家抽出时间。我想，如果你正在观看这个视频，而且已经看到这里，我认为你肯定正在思考人类进程中最有趣的进展之一。这里面存在许多哲学上的争论。有些人可能会说：“嘿，我觉得我可能在时间线上判断有误，或者我也许只是太悲观了，又或者我太乐观了。”但我很想听听所有的这些想法。这是我的二维码，请随意扫描，把你们的所有想法告诉我。非常感谢，非常感谢大家抽出宝贵的时间。

<details><summary>Original English</summary>
um

 so

 yeah

 so

 thank

 you

 so

 much

 you

 know





thank

 you

 so

 much

 for

 your

 time

 like

 I





think

 that

 uh

 I

 think

 that

 if

 you're





watching

 this

 and

 if

 you've

 gone

 this





far

 I

 think

 that

 you're

 definitely





contemplating

 like

 one

 of

 the

 most





interesting

 improvements

 in

 the

 course





of

 humanity

 And

 uh

 you

 know

 there's

 many





philosophical

 arguments

 here.

 Some





people

 might

 say

 hey

 you

 know

 I

 I

 think





I'm

 maybe

 I'm

 off

 on

 the

 timelines

 or





maybe

 maybe

 I'm

 I'm

 just

 being

 too





pessimistic

 or

 maybe

 I'm

 being

 too





optimistic.

 But

 I

 would

 love

 to

 hear

 all





those

 thoughts.

 So

 this

 is

 you

 know

 my





QR

 code.

 Please

 feel

 free

 to

 scan

 it

 and





let

 me

 know

 all

 your

 thoughts.

 Uh

 thank





you

 so

 much.

 Very

 kind

 of

 you

 to

 give

 me





your

 time.
</details>

### 代码智能体缺失的“撤销”按钮

>> 大家好，我是 Tme。今天 Dolly 也和我一起，我们将为大家带来《代码智能体缺失的“撤销”按钮》。

<details><summary>Original English</summary>
>> Hi

 everyone.

 I

 am

 Tme.





Today

 joining

 me

 is

 Dolly

 and

 we

 will

 be





presenting

 the

 missing

 undo

 button

 for





coding

 agents.
</details>

试想一个代码智能体正在处理代码仓库中的某个 issue。它打上补丁、运行测试，所有测试都通过了。它甚至创建了一个发布标签，但紧接着下游集成失败了。现在问题来了：智能体到底能不能把所有东西恢复到之前的状态？

<details><summary>Original English</summary>
So

 imagine

 a

 coding

 agent

 working

 on

 a





repository

 issue.

 It

 applies

 patch

 run





the

 tests

 and

 everything

 passes.

 It

 even





creates

 a

 release

 tag

 but

 then

 a





downstream

 integration

 fails.

 Now

 here





is

 the

 question.

 Can

 the

 agent

 actually





get

 everything

 back

 to

 the

 state

 it

 was





in

 before?
</details>

Git 可以告诉我们仓库内部发生了什么变化。但是 Git 之外的更改呢？比如外部 API 调用、运行时配置，或者发出的通知。

<details><summary>Original English</summary>
So

 git

 can

 tell

 us

 what

 changed

 in

 the





repository.

 But

 what

 about

 changes





outside

 git

 such

 as

 external

 API

 calls





or

 runtime

 configurations

 or





notifications.
</details>

单纯重试某项操作并不一定会撤销已经发生的事情。因此，我们不仅想了解智能体是否能够完成任务，更想了解它们在出现问题时能否实现恢复。

<details><summary>Original English</summary>
And

 simply

 retrying

 an

 operation

 does





not

 necessarily

 undo

 what

 already





happened.

 So

 we

 wanted

 to

 understand

 not





just

 whether

 agents

 can

 complete

 task





but

 whether

 they

 can

 recover

 when





something

 goes

 wrong.
</details>

这引出了我们的第一项研究工作：UndoBench。我们想探究智能体完成任务的能力是否也能转化为其从故障中恢复的能力。我们在 2,880 组配对试验中评估了智能体，将正常执行与注入故障下的执行进行了对比。在正常条件下，智能体实现了 84% 的成功率。但当我们引入故障时，通常成功的试验中只有 47% 成功恢复。请注意，这两个百分比的分母是不同的。

<details><summary>Original English</summary>
This

 brings

 us

 to

 our

 first

 research





work

 undo

 bench.

 We

 wanted

 to





investigate

 whether

 an

 agent's

 ability





to

 complete

 a

 task

 also

 translates

 into





its

 ability

 to

 recover

 from

 failure.

 We





evaluated

 agents

 across

 2,880





paired

 trials

 comparing

 normal

 execution





with

 execution

 under

 an

 injected





failure.

 So

 under

 normal

 conditions,

 the





agent

 achieved

 an

 84%

 success

 rate.

 But





when

 we

 introduced

 failures

 only

 47%





of

 the

 normally

 successful

 trials





recovered

 successfully.

 Notice

 that





these

 two

 percentage

 though

 have





different

 denominators.
</details>

不过即便智能体能够成功完成任务，恢复依然是一项重大挑战。

<details><summary>Original English</summary>
But

 yeah

 so

 even

 when

 an

 agent





uh

 can

 complete

 a

 task

 successfully





recovery

 remains

 a

 significant





challenge.
</details>

现在我们来看一个具体的故障场景。试想一个代码智能体向外部系统发送请求以创建工单。请求已经发出，智能体正在等待响应。

<details><summary>Original English</summary>
Now

 let's

 look

 at

 a

 specific

 failure





scenario.

 Imagine

 a

 coding

 agent

 sending





a

 request

 to

 an

 external

 system

 to





create

 a

 ticket.

 The

 request

 has

 been





sent

 and

 the

 agent

 is

 waiting

 for

 a





response.
</details>

随后，服务器接收到了请求，并成功创建了编号为 781 的工单。

<details><summary>Original English</summary>
Next,

 the

 server

 receives

 the

 request





and

 successfully

 creates

 ticket

 number





781.
</details>

但确认消息在返回给智能体的途中丢失了。

<details><summary>Original English</summary>
But

 the

 acknowledgement

 gets

 lost

 on

 its





way

 to

 the

 agent.
</details>

从智能体的角度来看，请求超时了，但智能体并不知道该工单其实已经创建完成。超时只告诉我们响应没有送达，并不意味着操作失败了。

<details><summary>Original English</summary>
From

 the

 agent's

 perspective,

 the





request

 has

 timed

 out,

 but

 the

 agent





does

 not

 know

 that

 the

 ticket

 has





already

 been

 created.

 A

 timeout

 tells

 us





that

 the

 response

 didn't

 arrive,

 not





that

 the

 operation

 failed.
</details>

于是智能体在没有检查第一项操作是否已提交的情况下重试了请求，结果我们现在有了两张工单，尽管智能体的本意只是创建一张。

<details><summary>Original English</summary>
So

 the

 agent

 tries

 the

 request

 without





checking

 whether

 the

 oper

 whether

 the





first

 operation

 committed





and

 now

 we

 have

 two

 tickets

 even

 though





the

 agent

 intended

 to

 create

 only

 one.
</details>

在 UndoBench 中，幼稚做法（naive 做法）在这类试验中有 54% 产生了重复效应。这就是为什么我们需要将失败的响应与失败的操作区分开来。

<details><summary>Original English</summary>
So

 in

 undo

 bench

 knives





produced

 duplicate

 effects

 in

 54%

 of





these

 kind

 of

 trials.

 That's

 why

 we

 need





to

 distinguish

 a

 failed

 response

 from

 a





failed

 operations.
</details>

此外，故障发生的阶段也会改变应对方式。我的意思是，恢复同样取决于故障发生在何时。在变更之前，重试通常是安全的，因为还没有发生任何改变；但在变更期间，系统可能已经被部分修改，所以我们需要检查其状态；而在变更之后，即便确认消息丢失，操作也可能已经提交了。正如我们刚才所见，盲目重试可能会产生重复。因此，我们需要根据故障发生的阶段采取不同的恢复策略。

<details><summary>Original English</summary>
Now





the

 failure

 phase

 also

 changes

 the





answer.

 What

 do

 I

 mean

 is

 that

 recovery





also

 depends

 on

 when

 the

 failure





happens.

 Before

 the

 mutation

 retrying

 is





generally

 safe

 because

 nothing

 has





changed

 but

 during

 the

 mutation

 the





system

 had

 may

 be

 partially

 modified.

 So





we

 need

 to

 inspect

 its

 state

 and

 after





the

 mutation

 the

 operation

 may

 have





committed

 even

 if

 the

 acknowledgement





was

 lost.

 As

 we

 just

 saw,

 retrying

 could





create

 duplicates.

 So,

 we

 need

 different





recovery

 strategies

 depending

 on

 the





failure

 phase.
</details>

那么，为什么我们不能直接使用 git revert 呢？Git 确实可以恢复仓库中的更改，但代码智能体还会修改它们的运行时状态，包括工具注册表、中间件和配置。它们还可以触发外部效应，例如部署或数据库写入。因此，git revert 并不能撤销所有这些变更。恢复机制必须与智能体所产生的效应类型相匹配。

<details><summary>Original English</summary>
Now,





why

 can't

 we

 just

 use

 get

 reward?

 So,





Git

 can

 restore

 repository

 changes,

 but





coding

 agents

 also

 modify

 their

 runtime





state

 including

 tool

 registries,





middleware

 and

 configurations.

 They

 can





also

 trigger

 external

 effects

 such

 as





deployment

 or

 database

 rights.

 So,

 get





rever

 does

 not

 reverse

 all

 these





changes.

 The

 recovery

 mechanism

 has

 to





match

 the

 type

 of

 effect

 the

 agent





created.
</details>

当代码智能体开始修改自身的执行环境（即我们所说的 agent harness）时，这一点变得尤为重要。这包括提示词、工具、中间件、事件监听器、资源以及路由配置。

<details><summary>Original English</summary>
And

 this

 becomes

 particularly

 important





when

 coding

 agents

 start

 modifying

 their





own

 execution

 environment

 or

 what

 we





call

 the

 agent

 hardness.

 This

 includes





prompts,

 tools,

 middleware,

 event





listeners,

 resources,

 and

 routing





configurations.
</details>

此类变更可能会提高智能体的性能，但也可能使恢复变得更加困难。换句话说，智能体可能在变得更有能力的同时，变得更难恢复。

<details><summary>Original English</summary>
Such

 changes

 may

 improve

 the

 agent's





performance,

 but

 they

 can

 also

 make





recovery

 more

 difficult.

 In

 other

 words,





an

 agent

 can

 become

 more

 capable

 while





becoming

 less

 recoverable.
</details>

这就是为什么撤销操作需要的不仅仅是一条逆向命令。撤销一项变更并不总是像执行一条反向命令那么简单。假设一个智能体将超时时间从 30 改为了 60。要撤销这项变更，它需要知道原始值是 30。这就是为什么 EvoUndo 在应用变更之前会捕获前置状态见证（pre-state witness），该见证提供了用于恢复原始状态并在随后验证恢复是否真正起效的信息。

<details><summary>Original English</summary>
Uh

 that's

 why

 uh

 that's

 why

 undo

 needs





more

 than

 an

 inverse

 command.

 Uh

 now





like

 undoing

 a

 change

 is

 not

 always

 as





simple

 as

 reversing

 a

 command.

 Suppose





an

 agent

 changes

 a

 timeout

 from

 30

 to





60.

 To

 undo

 that

 change,

 it

 needs

 to





know

 that

 the

 original

 value

 was

 30.





That's

 why

 EVO

 undo

 captures

 a

 pre-state





witness

 before

 applying

 the

 mutation

 and





that

 witness

 provides

 the

 information

 to





restore

 the

 original

 state

 and

 later





verify

 that

 uh

 verify

 that

 recovery





actually

 worked.
</details>

现在问题来了：改进后的 harness 出错的频率有多高？在 EvoUndo 中，我们评估了 600 个自我演化任务。其中 478 个带来了能力上的提升，但这些提升中有 197 个存在恢复缺陷。这大约占到了能力提升案例的 42%。因此，这里的核心结论是：一项变更可以提升智能体的能力，但仍可能导致系统无法可靠地恢复。

<details><summary>Original English</summary>
Now





question

 comes





how

 often

 uh

 do

 improved

 hardnesses





fail?

 So

 in

 Evo

 Undo,

 we

 evaluated

 600





self-

 evvolution

 tasks.

 Out

 of

 those

 478





produced

 capability

 improvements,

 but





197

 of

 those

 improvements

 had

 recovery





defects.

 That

 is

 around

 42%

 of

 the





capability

 positive

 cases.

 So

 here

 key





takeaway

 is

 that

 a

 mutation

 can

 improve





an

 agent's

 capability

 and

 still

 leave





the

 system

 unable

 to

 recover

 reliably.
</details>

现在我们来解释为什么单纯说“请修复撤销”起不到作用。很自然地，我们曾想过使用提示词，直接告诉智能体：“嘿，你能不能直接修复所有这些恢复失败？”于是我们测试了四种由验证器引导的修复策略，但在原始恢复语言下，没有一种能够恢复这 197 个自然发生的故障。问题并不一定在于智能体的推理能力。在某些情况下，智能体缺乏关于原始状态的精确信息；而在其他情况下，恢复语言无法表达撤销该变更所需的操作。因此，我们分别调查了这两种局限性。

<details><summary>Original English</summary>
Now

 now

 we

 can

 say

 that

 why

 please

 fix





the

 undo

 did

 not

 work.

 So

 naturally

 we





wanted

 to

 use

 prompting

 and

 wanted

 to





tell

 agent

 that

 hey

 could

 you

 simply





repair

 all

 these

 recovery

 failures.

 So





we

 tested

 four

 verifier

 guided

 repair





strategies

 but

 under

 the

 original





recovery

 language

 none

 recovered

 the

 197





naturally

 occurring

 failures.

 The





problem

 was

 not

 necessarily





the

 agent's

 reasoning.

 In

 some

 cases,





the

 agent

 lacked

 precise

 information





about

 the

 original

 state.

 In

 uh

 in





others,

 the

 recovery

 language

 could

 not





express

 the

 operation

 needed

 to

 reverse





the

 change.

 So,

 we

 investigated

 these





two

 limitations

 separately.
</details>

两个瓶颈：首先是状态溯源（state grounding），另一个是恢复表达力（recovery expressivity）。

<details><summary>Original English</summary>
So,

 two

 bottlenecks.





First

 is

 state

 grounding

 and

 another

 one





is

 recovery

 expressivity.
</details>

当我们提供了关于改变了什么以及发生在哪里的精确信息时，恢复成功数从 0 提升到了 48 例中的 38 例。第二个是恢复表达力：当我们引入更丰富的撤销操作时，恢复效果显著提升，从 0 提高到了 143 例中的 142 例。虽然这些结果来自两组不同的实验设置，但它们共同表明，为什么恢复既需要准确的状态信息，又需要执行所需端到端操作的能力。

<details><summary>Original English</summary>
The

 when

 we

 provided

 like

 precise





information

 about

 what

 had

 changed

 and





where

 then

 recovery

 improved

 from

 0

 to





38

 out

 of

 48

 cases.

 And

 the

 second

 is





recovery

 expressivity.

 So

 when

 we





introduced

 richer

 undo

 operation





recovery

 improved

 significantly

 from





zero

 to

 142

 out

 of

 143

 cases.

 So

 these





results

 come

 from

 the

 two

 different





experimental

 tubros

 but

 together

 they





show

 why

 recovery

 needs

 both

 accurate





state

 information

 and

 ability

 to

 perform





the

 required

 end

 to

 operation.
</details>

现在我们脑海中浮现出一个问题：更好的撤销机制能否挽救失败的变更？

<details><summary>Original English</summary>
Now

 question

 comes

 to

 our

 mind

 that

 can





better

 undo

 mechanism

 rescue

 failed





mutations.
</details>

那么，当我们赋予智能体更强的恢复能力时会发生什么呢？使用原始的恢复语言，那 197 个具有恢复缺陷的变更没有一个能够被还原。但在扩展了恢复语言之后，我们在 197 例中成功恢复了 180 例，大约占 92%。结果，在 600 个任务中，可接纳的改进数量从 281 个增加到了 461 个，提升了 30 个百分点。

<details><summary>Original English</summary>
So

 what

 happens

 like

 when

 we

 give

 the





agent

 better

 recovery

 capabilities.

 So





with

 the

 original

 recovery

 language

 none





of

 the

 197

 recovery

 defective

 mutations





could

 be

 restored.

 But

 after

 extending





the

 recovery

 language,

 we

 successfully





recovered

 180

 out

 of

 197

 cases.

 That

 is





around

 92%.

 As

 a

 result,

 the

 number

 of





admissible

 improvement

 increased

 from





281

 to

 461





out

 of

 600

 task.

 That

 is

 a

 30

 percentage





point

 improvement.
</details>

这就引出了下一个问题：我们如何将这些恢复检查构建到智能体的演化过程中？我现在把时间交给 Dolly，由她来详细讲解 EvoUndo 算法。

<details><summary>Original English</summary>
And

 that

 brings

 us

 to

 the

 next

 question.

 How





do

 we

 build

 these

 recovery

 checks

 into





the

 agent's

 evolution

 process?

 I

 will





now

 hand

 it

 over

 to

 Dolly

 to

 walk





through

 the

 EVO

 undo

 algorithm.
</details>

>> 好的，谢谢 San。那么让我们进入关于 EvoUndo 究竟如何运行的工作机制。首先我们从智能体处理流程开始。首先智能体会处理当前处于哪个状态下的变更，以及效果契约和恢复计划。在应用变更之前，我们会捕获代表原始状态的状态见证；甚至在此之前……接着在测试环境中，智能体将应用变更并执行恢复计划；一个独立的验证器也会去验证原始状态，验证以检查原始状态是否已被……

<details><summary>Original English</summary>
All

 right,

 thanks

 San.

 Uh

 so

 let's

 get





into

 the

 working

 on

 how

 Evo

 and

 actually





works.

 So

 first

 we

 will

 start

 with

 the





agent

 pro.

 Uh

 first





the

 agent

 will

 start

 the

 agent

 pro





processes

 the

 mutation

 on

 which

 state

 it





is

 currently

 in

 along

 with

 the

 effect





contract

 and

 the

 recovery

 plan.

 And





before

 applying

 the

 mutation





we

 captured

 the

 state

 witness





representing

 the

 original

 state





and

 even

 before

 that

 the

 then

 a

 testing





in

 the

 testing

 environment

 agent

 will





apply

 the

 mutation

 and

 execute

 the





recovery

 plant

 uh

 an

 independent





verifier

 will

 also

 verify

 the

 original





if

 uh

 verify

 to

 check

 if

 the

 original





state

 has

 been
</details>

<!-- chunk 25/50 -->

restored or not. If the mutation improves uh the capability based on the userdefined criteria and passes the recovery um check the agents admit the changes otherwise well uh the agent attempt to repair or the verifier itself rejects the mutation altogether. This way the recoveryability becomes a part of the admission decision rather than something that we strategize or even plan once we are uh deployed the deployed the AI agent.

<details><summary>Original English</summary>
 restored

 or

 not.

 If

 the





mutation

 improves

 uh

 the

 capability





based

 on

 the

 userdefined

 criteria

 and





passes

 the

 recovery

 um

 check

 the

 agents





admit

 the

 changes

 otherwise

 well





uh

 the

 agent

 attempt

 to

 repair

 or

 the





verifier

 itself

 rejects

 the

 mutation





altogether.

 This

 way

 the

 recoveryability





becomes

 a

 part

 of

 the

 admission

 decision





rather

 than

 something

 that

 we

 strategize





or

 even

 plan

 once

 we

 are

 uh

 deployed

 the





deployed

 the

 AI

 agent.
</details>

Okay. So with next next we will walk through as as Tan have already explained in given an example let let me walk through how the ex uh how that example of a timer changing from 30 to 60 would look like in action.

<details><summary>Original English</summary>
Okay.

 So

 with

 next





next

 we

 will

 walk

 through

 as

 as

 Tan

 have





already

 explained

 in

 given

 an

 example





let

 let

 me

 walk

 through

 how

 the

 ex

 uh





how

 that

 example

 of

 a

 timer

 changing





from

 30

 to

 60

 would

 look

 like

 in

 action.
</details>

So let's take let's start with the original state the simple example that uh simple example of um our agent having the time value of 30 before changing anything the evoando would first read the original value and then it will save the it will capture the original value as a state witness. We know exact we so we know exactly what need to be restored when when and when if we have to restore it we would know what what need to be restored or which state would be the true state to return back to. Now the agent so next come the mutation. Now the agent changes the timeout from 30 to 60 as we want it to do. And if recovery is required uh if recovery is required the undo uses the saved witness to restore the timeout to 60.

<details><summary>Original English</summary>
So

 let's

 take

 let's

 start

 with

 the





original

 state

 the

 simple

 example

 that





uh

 simple

 example

 of

 um

 our

 agent

 having





the

 time

 value

 of

 30

 before

 changing





anything

 the

 evoando

 would

 first

 read





the

 original

 value





and

 then

 it

 will

 save

 the

 it

 will





capture

 the

 original

 value

 as

 a

 state





witness.

 We

 know

 exact

 we

 so

 we

 know





exactly

 what

 need

 to

 be

 restored

 when





when

 and

 when

 if

 we

 have

 to

 restore

 it





we

 would

 know

 what

 what

 need

 to

 be





restored

 or

 which

 state

 would

 be

 the





true

 state

 to

 return

 back

 to.

 Now

 the





agent

 so

 next

 come

 the

 mutation.

 Now

 the





agent

 changes

 the

 timeout

 from

 30

 to

 60





as

 we

 want

 it

 to

 do.

 And

 if

 recovery

 is





required

 uh

 if

 recovery

 is

 required

 the





undo

 uses

 the

 saved

 witness

 to

 restore





the

 timeout

 to

 60.
</details>

Now independently the verifier finally an independent verifier would also confirm that the uh recovered value matches the original value. So the recovery isn't considered successful simply because an undo command was run but also the verifier would verify the resulting state to make sure that we are in fact doing the uh recovery those in the state we want it to be.

<details><summary>Original English</summary>
Now

 independently

 the

 verifier

 finally





an

 independent

 verifier

 would

 also





confirm

 that

 the

 uh

 recovered

 value





matches

 the

 original

 value.

 So

 the





recovery

 isn't

 considered

 successful





simply

 because

 an

 undo

 command

 was

 run





but

 also

 the

 verifier

 would

 verify

 the





resulting

 state

 to

 make

 sure

 that

 we

 are





in

 fact

 doing

 the

 uh

 recovery

 those

 in





the

 state

 we

 want

 it

 to

 be.
</details>

Well now comes the bigger question. So so we have this capability of recovery in our arsenal. Should we be using it for uniformly and applying the recovery mechanism to all the failures? Well, of course not. Um, not every failures can be recovered the same way. If nothing has changed, then the then simply if if nothing has changed in the in the system, we would simply want it to um recover uh we we would simply want it to safely retry. we would want the agent to simply retry if uh and try to achieve the state that we want to be. However, if we have the original state uh once we have the original state, we can restore it. If the external action has already been committed and we need uh it's then when we would need a compensation mechanism, compensation action to comp compensating action to reverse its effect. And if we cannot recover the recovery uh and we cannot if if and if we cannot the cannot verify that recovery is safe or the verifier have rejected the recovery then the agent should stop and escalate. The right response definitely depends on what actually happened and what we what can be safely reversed or not.

<details><summary>Original English</summary>
Well

 now

 comes

 the

 bigger

 question.

 So





so

 we

 have

 this

 capability

 of

 recovery





in

 our

 arsenal.

 Should

 we

 be

 using

 it





for

 uniformly

 and

 applying

 the

 recovery





mechanism

 to

 all

 the

 failures?

 Well,

 of





course

 not.

 Um,

 not

 every

 failures

 can





be

 recovered

 the

 same

 way.

 If

 nothing





has

 changed,

 then

 the

 then

 simply

 if

 if





nothing

 has

 changed

 in

 the

 in

 the





system,

 we

 would

 simply

 want

 it

 to

 um





recover

 uh

 we

 we

 would

 simply

 want

 it

 to





safely

 retry.

 we

 would

 want

 the

 agent

 to





simply

 retry

 if

 uh

 and

 try

 to

 achieve





the

 state

 that

 we

 want

 to

 be.

 However,





if

 we

 have

 the

 original

 state

 uh

 once

 we





have

 the

 original

 state,

 we

 can

 restore





it.

 If

 the

 external

 action

 has

 already





been

 committed

 and

 we

 need

 uh





it's

 then

 when

 we

 would

 need

 a





compensation

 mechanism,

 compensation





action

 to

 comp

 compensating

 action

 to





reverse

 its

 effect.

 And

 if

 we

 cannot





recover

 the

 recovery

 uh

 and

 we

 cannot

 if





if

 and

 if

 we

 cannot

 the

 cannot

 verify





that

 recovery

 is

 safe

 or

 the

 verifier





have

 rejected

 the

 recovery

 then

 the





agent

 should

 stop

 and

 escalate.

 The





right

 response

 definitely

 depends

 on





what

 actually

 happened

 and

 what

 we

 what





can

 be

 safely

 reversed

 or

 not.
</details>

That brings me to the almost the last slide which is about bringing everything together on our two paper undo bench and ebo undo. The so the key takeaways here are first the undo bench shows the successful task execution. Uh the undo bench shows that the successful task execution doesn't guarantee doesn't always guarantee the successful recovery of it. Uh secondly, the EVO undo algorithm provides a structured process. Capture the original state, apply the mutation, recover independently, verify and restoration. So the EVO undo algorithm does work in the in the fash in the way we intended it to. And third, we should admit self-evolution changes only when the when both the capability and the recoverability requirements are met. So ultimately as we give agent more autonomy, we should also give them more uh reliable ways to recover from their actions.

<details><summary>Original English</summary>
That

 brings

 me





to

 the

 almost

 the

 last

 slide

 which

 is





about

 bringing

 everything

 together

 on





our

 two

 paper

 undo

 bench

 and

 ebo

 undo.





The

 so

 the

 key

 takeaways

 here

 are

 first





the

 undo

 bench

 shows

 the

 successful

 task





execution.





Uh

 the

 undo

 bench

 shows

 that

 the





successful

 task

 execution

 doesn't





guarantee

 doesn't

 always

 guarantee

 the





successful

 recovery

 of

 it.

 Uh

 secondly,





the

 EVO

 undo

 algorithm

 provides

 a





structured

 process.

 Capture

 the

 original





state,

 apply

 the

 mutation,

 recover





independently,

 verify

 and

 restoration.





So

 the

 EVO

 undo

 algorithm

 does

 work

 in





the

 in

 the

 fash

 in

 the

 way

 we

 intended





it

 to.

 And

 third,

 we

 should

 admit





self-evolution

 changes

 only

 when

 the





when

 both

 the

 capability

 and

 the





recoverability

 requirements

 are

 met.

 So





ultimately

 as

 we

 give

 agent

 more





autonomy,

 we

 should

 also

 give

 them

 more





uh

 reliable

 ways

 to

 recover

 from

 their





actions.
</details>

All right. So and finally I hope you remember the agent from the beginning. It was looking for an undo button. Well, now it has one. We have started building this capability through our research project Evo undo. And you can explore the work through the in in the GitHub repository. can scan the QR code on the screen to get to the page. Our goal is to make the recovery a fundamental capability of AI agent so that we not only have the the agent does not even execute the action but also recover when something goes wrong as well. Thank you so much.

<details><summary>Original English</summary>
All right.

 So

 and

 finally

 I

 hope

 you





remember

 the

 agent

 from

 the

 beginning.





It

 was

 looking

 for

 an

 undo

 button.

 Well,





now

 it

 has

 one.

 We

 have

 started

 building





this

 capability

 through

 our

 research





project

 Evo

 undo.

 And

 you

 can

 explore





the

 work

 through

 the

 in

 in

 the

 GitHub





repository.

 can

 scan

 the

 QR

 code

 on

 the





screen

 to

 get

 to

 the

 page.

 Our

 goal

 is





to

 make

 the

 recovery

 a

 fundamental





capability

 of

 AI

 agent

 so

 that

 we

 not





only

 have

 the

 the

 agent

 does

 not

 even





execute





the

 action

 but

 also

 recover

 when





something

 goes

 wrong

 as

 well.

 Thank

 you





so

 much.
</details>

### 多邻国 iOS 测试用例生成与交付实践

Hey everyone, thanks for tuning in. Today I'm going to walk you through how we use AI agents at Dualingo to write and ship more than 200,000,000 lines of unit tests on iOS codebase. I'll share what we built and what we learned along the way. Uh I'm Kush. I'm a staff engineer on the platform team here at Dualingo. My job is to build developer tooling and AI assisted workflows for the 100 plus engineers who contribute to our client apps. Before Duelingo, I spent close to a decade at Stripe and Uber working across a few teams there.

<details><summary>Original English</summary>
Hey

 everyone,

 thanks

 for

 tuning

 in.





Today

 I'm

 going

 to

 walk

 you

 through

 how





we

 use

 AI

 agents

 at

 Dualingo

 to

 write





and

 ship

 more

 than

 200,000,000

 lines

 of





unit

 tests

 on

 iOS

 codebase.

 I'll

 share





what

 we

 built

 and

 what

 we

 learned

 along





the

 way.

 Uh

 I'm

 Kush.

 I'm

 a

 staff





engineer

 on

 the

 platform

 team

 here

 at





Dualingo.

 My

 job

 is

 to

 build

 developer





tooling

 and

 AI

 assisted

 workflows

 for





the

 100

 plus

 engineers

 who

 contribute

 to





our

 client

 apps.

 Before

 Duelingo,

 I





spent

 close

 to

 a

 decade

 at

 Stripe

 and





Uber

 working

 across

 a

 few

 teams

 there.
</details>

Let's start with some background on the scale of mobile at Dualingo. Uh we ship our apps to the app store every week. Um we're also a very experiment-driven company. So at any given point of time, we have more than 600 AB tests running live. And our code bases are pretty mature. Both the iOS and Android apps have been around for more than 10 years at this point.

<details><summary>Original English</summary>
Let's

 start

 with

 some

 background

 on

 the





scale

 of

 mobile

 at

 Dualingo.

 Uh

 we

 ship





our

 apps

 to

 the

 app

 store

 every

 week.

 Um





we're

 also

 a

 very

 experiment-driven





company.

 So

 at

 any

 given

 point

 of

 time,





we

 have

 more

 than

 600

 AB

 tests

 running





live.

 And

 our

 code

 bases

 are

 pretty





mature.

 Both

 the

 iOS

 and

 Android

 apps





have

 been

 around

 for

 more

 than

 10

 years





at

 this

 point.
</details>

Here's also the number of executable lines of app code in our iOS repository. So, as you can see, back in 2019, we were at about 200,000 lines, and today we're hit close to 2 million. And as AI assisted coding picks up, you can see that curve starting to bend upward. And it's not just the amount of code that's changing, it's also who's writing it. So, last year about 200 people contributed to the iOS repository. And this year, we've already crossed 250. And a lot of these folks aren't even iOS engineers. We have backend engineers, Android engineers, even PMs and designers all shipping code to the iOS app and that's mostly been unlocked by AI coding tools like cursor and cloud code. Um, another thing to note about our codebase is that it's a codebased in transition. So a few years ago we standardized on the MVVM architecture pattern. Today about half the code in our repository follows that pattern and the other half is still legacy code that we're in the process of migrating. Since the MVVM half is the easiest to test, that's where we focused on this project.

<details><summary>Original English</summary>
Here's

 also

 the

 number

 of

 executable





lines

 of

 app

 code

 in

 our

 iOS

 repository.





So,

 as

 you

 can

 see,

 back

 in

 2019,

 we





were

 at

 about

 200,000

 lines,

 and

 today





we're

 hit

 close

 to

 2

 million.

 And

 as

 AI





assisted

 coding

 picks

 up,

 you

 can

 see





that

 curve

 starting

 to

 bend

 upward.

 And





it's

 not

 just

 the

 amount

 of

 code

 that's





changing,

 it's

 also

 who's

 writing

 it.





So,

 last

 year

 about

 200

 people





contributed

 to

 the

 iOS

 repository.

 And





this

 year,

 we've

 already

 crossed

 250.





And

 a

 lot

 of

 these

 folks

 aren't

 even

 iOS





engineers.

 We

 have

 backend

 engineers,





Android

 engineers,

 even

 PMs

 and





designers

 all

 shipping

 code

 to

 the

 iOS





app

 and

 that's

 mostly

 been

 unlocked

 by





AI

 coding

 tools

 like

 cursor

 and

 cloud





code.

 Um,

 another

 thing

 to

 note

 about





our

 codebase

 is

 that

 it's

 a

 codebased

 in





transition.

 So

 a

 few

 years

 ago

 we





standardized

 on

 the

 MVVM

 architecture





pattern.

 Today

 about

 half

 the

 code

 in





our

 repository

 follows

 that

 pattern

 and





the

 other

 half

 is

 still

 legacy

 code

 that





we're

 in

 the

 process

 of

 migrating.

 Since





the

 MVVM

 half

 is

 the

 easiest

 to

 test,





that's

 where

 we

 focused

 on

 this

 project.
</details>

Here's where we started back in March of this year. We were at overall unit test coverage of 11%. The MVVM layers were a bit lower. Repositories were at 11%, view models at 9, data sources at five, and combined we are about 9% for the MBVM slice of the app.

<details><summary>Original English</summary>
Here's

 where

 we

 started

 back

 in

 March

 of





this

 year.

 We

 were

 at

 overall

 unit

 test





coverage

 of

 11%.

 The

 MVVM

 layers

 were

 a





bit

 lower.

 Repositories

 were

 at

 11%,





view

 models

 at

 9,

 data

 sources

 at

 five,





and

 combined

 we

 are

 about

 9%

 for

 the





MBVM

 slice

 of

 the

 app.
</details>

So why does this matter now more than it used to? As agents and humans write more code and write it faster, writing code isn't the hard part anymore. Verifying it is. So when someone puts up a PR, how do you know that it's actually safe to ship? The bottleneck is really shifting from writing to verifying. And that's where unit tests come in. They make up the base of the testing pyramid. They're pretty cheap to write and fast to run. And they also act as guardrails for agents. So when an agent's change breaks a test in CI, it gets immediate feedback on what to fix. They also act as living documentation on what the code is supposed to do. And here's where we ended up 8 months later. Overall unit test coverage went from 11% to 24%, repositories went from 11 to 72, view models from 9 to 58, data sources from 5 to 41, and the combined MVVM slice of the app went from 9% to 59%. So what do we actually end up building? On paper, it's a pretty simple loop. First you identify the files that need tests. Then you write those tests with an agent. You verify that the tests are good quality and they pass CI. Then you resolve the PR which means getting reviewed by an engineer merged. And finally iterate on the feedback so that the next batch of PRs is better than the last one. When production it's a little messier. This is what our system ended up looking like. I won't go through every box right now, but at a high level it's a few temporal workflows that coordinate through shared state stored in S3. And every box you see here maps back to one of the five steps I just talked about.

<details><summary>Original English</summary>
So

 why

 does

 this

 matter

 now

 more

 than

 it





used

 to?

 As

 agents

 and

 humans

 write

 more





code

 and

 write

 it

 faster,

 writing

 code





isn't

 the

 hard

 part

 anymore.

 Verifying





it

 is.

 So

 when

 someone

 puts

 up

 a

 PR,

 how





do

 you

 know

 that

 it's

 actually

 safe

 to





ship?

 The

 bottleneck

 is

 really

 shifting





from

 writing

 to

 verifying.

 And

 that's





where

 unit

 tests

 come

 in.

 They

 make

 up





the

 base

 of

 the

 testing

 pyramid.

 They're





pretty

 cheap

 to

 write

 and

 fast

 to

 run.





And

 they

 also

 act

 as

 guardrails

 for





agents.

 So

 when

 an

 agent's

 change

 breaks





a

 test

 in

 CI,

 it

 gets

 immediate

 feedback





on

 what

 to

 fix.

 They

 also

 act

 as

 living





documentation

 on

 what

 the

 code

 is





supposed

 to

 do.

 And

 here's

 where

 we





ended

 up

 8

 months

 later.

 Overall

 unit





test

 coverage

 went

 from

 11%

 to

 24%,





repositories

 went

 from

 11

 to

 72,

 view





models

 from

 9

 to

 58,

 data

 sources

 from

 5





to

 41,

 and

 the

 combined

 MVVM

 slice

 of





the

 app

 went

 from

 9%

 to

 59%.

 So

 what

 do





we

 actually

 end

 up

 building?

 On

 paper,





it's

 a

 pretty

 simple

 loop.

 First

 you





identify

 the

 files

 that

 need

 tests.

 Then





you

 write

 those

 tests

 with

 an

 agent.

 You





verify

 that

 the

 tests

 are

 good

 quality





and

 they

 pass

 CI.

 Then

 you

 resolve

 the





PR

 which

 means

 getting

 reviewed

 by

 an





engineer

 merged.

 And

 finally

 iterate

 on





the

 feedback

 so

 that

 the

 next

 batch

 of





PRs

 is

 better

 than

 the

 last

 one.

 When





production

 it's

 a

 little

 messier.

 This





is

 what

 our

 system

 ended

 up

 looking





like.

 I

 won't

 go

 through

 every

 box

 right





now,

 but

 at

 a

 high

 level

 it's

 a

 few





temporal

 workflows

 that

 coordinate





through

 shared

 state

 stored

 in

 S3.

 And





every

 box

 you

 see

 here

 maps

 back

 to

 one





of

 the

 five

 steps

 I

 just

 talked

 about.
</details>

Here are the building blocks that we ended up using. Temporal handles workflow orchestration and execution. Cloud code acts as the coding agent. S3 holds the shared

<details><summary>Original English</summary>
Here

 are

 the

 building

 blocks

 that

 we





ended

 up

 using.

 Temporal

 handles





workflow

 orchestration

 and

 execution.





Cloud

 code

 acts

 as

 the

 coding

 agent.

 S3





holds

 the

 shared
</details>

<!-- chunk 26/50 -->

保持我们工作流同步的状态。我们使用 GitHub 来处理 actions、标签和 PR。Datadog 作为可观测性层，用来监控我们流水线的健康状况。

<details><summary>Original English</summary>
state that keeps our workflows in sync. And we use GitHub for actions, labels, and PRs. Data dogs acts as an observability layer where we keep an eye on the health of our pipelines.
</details>

如果你之前没有用过 Temporal，它基本上是一个持久化工作流执行引擎。你可以用普通的 Python 代码编写工作流，如果某个 worker 崩溃了，工作流会直接从中断的地方继续执行。这非常适合 agent。一个 agent 会话可以运行几秒到几小时不等，并且它可以调用像 GitHub、CI、S3 和 Claude 这样的工具。我们也依赖 Temporal 的一些内置功能：有 schedules，基本上就是为我们任务提供的类似 cron 的定时调度；有可组合的工作流，方便我们并行分发工作；还有对重试、超时和幂等性的一等支持，确保我们绝不会对同一个文件重复触发运行。

<details><summary>Original English</summary>
If you haven't used temporal before, it's basically a durable workflow execution engine. You write your workflows as normal Python code, and if a worker crashes, the workflow just picks up right where it left off. This fits agents really well. An agent session can run for seconds to hours and it can call out to tools like GitHub, CI, S3 and Claude. We also lean on a few built-in features of temporal. There are schedules which are basically crown-like schedules for our jobs. There are composible workflows so that we can fan out work in parallel. Then there's first class support for retries and timeouts and item potency so that we never kick off duplicate runs of the same file.
</details>

为了拆解这项工作，我们把这个项目分成了四个里程碑：第一个是本地验证，基本上就是看这个项目到底是否可行；第二个是定时回填工作流，为已有代码编写测试；第三个是 PR 生命周期工作流，真正把这些 PR 合并进去；第四个是标签触发器，让工程师可以为他们正在编写的新代码获取测试。

<details><summary>Original English</summary>
To split up this work, we split this project into four milestones. The first was local validation. Basically, is this project even viable? The second was a scheduled backfield workflow to write tests for existing code. The third was a PR life cycle workflow to actually get those PRs merged. And the fourth was a label trigger so engineers can get tests for the new code that they're writing.
</details>

### 里程碑 1：本地验证

现在，我们将按顺序逐一展开。在构建任何真正的东西之前，我们希望尽可能做最少的工作量，以判断 agent 是否真能做好这项工作，以及能否规模化进行。我们从一个非常简单的本地 Claude Code 设置开始，其中有一个 Claude Code 命令充当编排器。它运行一个 Xcode 构建脚本以在本地生成代码覆盖率报告，然后把该报告输入给我们编写的文件选择脚本，接着把选出的每个文件分发给两个 sub-agent：一个编写测试，另一个发起 PR。我们在循环中运行这个流程，生成了一批 PR。我们基本上分两个批次运行：第一批有 17 个 PR，我们合并了其中的 8 个；第二批有 40 个 PR，我们合并了 19 个。所以这大概是 50% 的合并率。但这里的目的并不是合并大量 PR，而是了解 agent 是如何失败的，并在进行任何生产化改造之前解决这些微小痛点。

<details><summary>Original English</summary>
Now, we'll go through each of these in order. Before building anything real, we wanted to do the least amount of work possible that would tell us whether an agent could actually do this job well and do it at scale. We started with a very simple local clot code setup where we had one cloud code command that acted as an orchestrator. It ran an Xcode build script to generate a code coverage report locally. Then it fed that report through a file selection script that we wrote and then it handed each selected file off of sub two sub aents. One wrote the tests and the other one opened the PR. We ran this in a loop and generated a bunch of PRs. We basically ran this in two batches. The first batch had 17 PRs and we merged eight of them. The second had 40 PRs and we merged 19. So that's roughly a 50% merge rate. But the goal here wasn't to merge a lot of PRs. It was to learn how the agents fail and to fix those paper cuts before productionizing anything.
</details>

以下是我们观察到的一些失败模式：由于我们是一个大型遗留代码库，同时包含 XCTest 和 Swift Testing，agent 有时会产生混淆，在一个文件中将两者混用。我们通过为 agent 提供明确的规则来规定何时使用哪一种，解决了这个问题。我们还有一个庞大的用户客户端单例类，一些代码传递该类的具体实现版本，这非常难 mock，而其他代码则传递面向协议的版本。因此，我们将整个代码库迁移到了面向协议的版本，并添加了 lint 规则来进行强制约束。这使得一大批文件无论对 agent 还是对人类来说都更容易进行测试。我们还遇到了六个与并发相关的问题，以及 agent 编写基于时序的测试，而这正是 CI 中不稳定测试（flakiness）的一大来源。因此，我们通过在测试 skills 中提供更好的规则和示例，改善了这两方面的情况。

<details><summary>Original English</summary>
Here are some of the failure modes that we saw. Since we're a large legacy code base with both XC test and swift testing, the agents would sometimes get confused and mix the two in one file. We fixed that by giving the agents clear rules on when to use each. We also had a giant user client singleton class. Some code passed around the concrete version of this class which is really hard to mock whereas others passed around a protocolized version. So we migrated the entire code base over to the protocolized version and added lint rule to enforce it. This made the whole host of files easier to test for agents and for humans. We also ran to six concurrency related issues and agents writing timing based tests which are a big source of flakiness in CI. So we improved the state for both of these with better rules and examples in our testing skills.
</details>

### 里程碑 2：定时回填工作流

现在这把我们引向了里程碑 2。既然我们在代码覆盖率上落后这么多，我们看到的最大杠杆就是为已经合入的代码回填测试。这就是定时回填工作流发挥作用的地方。这是我们工作流在生产环境中运行的系统设计图。它本质上承担两项工作：左半部分是识别（identify），也就是挑选需要测试的文件；右半部分是编写（write），也就是让 agent 实际编写这些测试。

<details><summary>Original English</summary>
Now this brings us to milestone 2. Since we're so far behind on code coverage, the biggest leverage that we saw was backfilling tests for code that was already merged in. That's where the scheduled backfill workflow comes in. This is a system design diagram of our workflow as it runs in production. And it essentially does two jobs. The left half is to identify which is picking the files that need tests and the right half is right which is having the agents actually write those tests.
</details>

我们从“识别”开始。每当一个 PR 合并到 iOS 仓库的 main 分支时，我们就会触发一个 GitHub Actions 任务，生成 Xcode 覆盖率报告并上传到 S3，这便成了最新代码覆盖率的单一事实来源。接着，回填工作流拉取该报告，并将其输入给一个选择器脚本，该脚本挑出下一批要测试的文件。

<details><summary>Original English</summary>
Let's start with identify. Every time a PR merges to the main branch in the iOS repo, we kick off a GitHub access job that generates an Xcode coverage report and uploads it to S3 that becomes a source of truth for the latest code coverage. The backfield workflow then fetches that report and runs it through a selector script which picks the next set of files to test.
</details>

让我们对选择器脚本做更深入的了解。它的工作本质上是根据我们对 agent 能否为其写出优质测试的置信度，为每个 Swift 文件打分。最强的信号是文件类型：ViewModel、Repository 和 DataSource 会获得 2.5 倍的权重提升，而遗留文件则被降权。我们目前完全跳过了 UI 代码，因为快照测试在那边更合适；较大的文件也会受到扣分惩罚。通过这种方式，我们优先处理那些我们有信心能够做好测试的代码。

<details><summary>Original English</summary>
Let's get a deeper a little deeper into the selector script. Its job is essentially to score every Swift file based on how confident we are that an agent can write a good test for it. The strongest signal is file type. So view models, repositories, and data sources get a 2.5x boost while legacy files get pushed down. We skipped UI code completely for now since snapshot tests are better fit there and larger files also get a penalty. So we prioritize code that we're confident that we can test well.
</details>

下一步就是实际编写测试。我们为每个文件启动一个子工作流，全部并行运行。在每一次运行中，agent 都会克隆 iOS 仓库，读取我们保留在仓库中的测试 skill——里面详述了如何编写优质的测试。然后它编写测试，以及所需的任何 mock 和 fake，并发起一个带有 generated test 标签的 PR，以便我们稍后轻松识别。

<details><summary>Original English</summary>
The next step is to actually write the tests. We kick off one child workflow per file all running in parallel. In each one of these runs, the agent clones the iOS repository, reads the testing skill that we keep in the repo, which spells out how to write a good test. Then it writes the test plus any mocks and fakes it needs and opens a PR with a generated test label so we can identify it easily later.
</details>

这些 agent 运行在 Duolingo 的云端编码 agent 平台上，该平台也是运行在 Temporal 之上。最简单的理解方式是把它看作运行在云端的 Claude Code 和 Codex 之上的一层抽象。我们可以从 Slack、Temporal 或 GitHub 调用它。它通过 MCP 与我们的许多内部工具通信，并记录大量事件，以便我们查看每个 agent 运行在做什么以及消耗了多少成本。我们一开始是在 Linux 机器上运行这些，后来迁移到了 Mac runner 上，这一点待会儿会变得很重要。这就是生成的测试 PR 的样子：每个 PR 描述都遵循相同的模板，并明确标明该 PR 是由 AI 生成的。审查人员有四个选项：他们可以直接批准并让 PR 自动合并；可以直接向其推送修改；可以重新指派给更合适的人；或者可以通过提供其为何不可合并的反馈来关闭它。

<details><summary>Original English</summary>
These agents run on Dualingo's cloud coding agent which is a platform that also runs on Nepor. The simplest way to think about it is as an abstraction on top of cloud code and codex running in the cloud. We can invoke it from slack, temporal or github. It talks to a bunch of our internal tools for MCP and it logs a bunch of events so we can see what each agent run is doing and how much it costs. We started running these on Linux machines and then later move them to MacRunners which will become important in a minute. Here's what a generated test PR looks like. Every PR description follows the same template and it says explicitly that the PR is AI generated. The reviewer has four options. They can approve it in the PR auto modes. They can push changes to it directly. They can reassign it to someone better suited or they can close it out with feedback on why it isn't mergeable.
</details>

### 里程碑 3：PR 生命周期工作流

一旦回填流程在生产环境中跑起来，我们就遇到了一个稍显全新的问题：我们突然积压了数十到上百个处于开启状态的 PR，没人能手动处理得过来。那么我们该如何把所有这些 PR 推至可合并状态，并推到合适的审查人员面前呢？

<details><summary>Original English</summary>
Now once we had the backfill running in production, we had a slightly new problem. We suddenly had tens of tens to hundreds of open PRs that nobody could manage by hand. So how do we get all of these to a mergeable state and in front of the right reviewer?
</details>

这就是 PR 生命周期工作流发挥作用的地方。你可以把它看作一个状态机。它每隔几小时运行一次，查看每一个处于开启状态的生成测试 PR，并对每个 PR 采取恰好一项操作。它涵盖了我们闭环中的接下来两步：验证（verify），即该 PR 是否通过 CI 以及质量是否过关；以及解决（resolve），即让审核人员审查并将其合并。这个工作流的逻辑是一个简单的决策树：如果存在任何合并冲突，或者该 PR 已经开启了大约 3 周，我们就将其关闭并标记为陈旧；如果 CI 仍在运行，或者已经有审查人员在处理，我们就跳过它；如果 CI 通过且没有审查人员，我们就寻找一位并进行指派；如果 CI 失败，我们就尝试修复它；而如果审查人员拒绝了该 PR，该文件就会进入 30 天的冷却期，这样我们就不会用同一个 PR 一遍又一遍地打扰工程师了。

<details><summary>Original English</summary>
That's where the PR life cycle workflow comes in. You can think of it as a state machine. It runs every couple of hours, looks through every open generated test PR and takes exactly one action on each. It covers the next two steps of our loop. Verify, which is does this PR pass CI and is it high quality and resolve, which is getting a human to review it and merge it. The logic for this workflow is a simple decision tree. If there are any merge conflicts or the PR has been open for about 3 weeks, we close it out and mark it as still. If CI is still running or a reviewer is already on it, we skip it. If CI is green and there's no reviewers, we find one and sign them. If CI is red, we try to fix it. And if the reviewer rejects the PR, the file goes into 30-day cool down. So we're not spamming engineers with the same PR again and again.
</details>

当 CI 失败时，我们首先检查的是哪一个任务失败了。如果是 pre-commit 失败，会由一个 GitHub Action 来应用修复。这很便宜、确定性高，且不需要 agent。如果是真正的测试失败，我们会启动另一个 agent，它会读取 CI 日志并向该 PR 推送修复。我们将这整个循环上限限制在五次尝试，超过这个次数我们就会关闭该 PR，而不是永远无休止地尝试修复它。

<details><summary>Original English</summary>
When CI fails, the first thing we check is which job failed. If it's pre-comit, a GitHub action applies the fix. It's cheap, it's deterministic, and there's no agent needed. If it's a real test failure, we kick off another agent that reads the CI logs and pushes a fix to the PR. We cap that whole loop at five attemps. Pass that we close the PR rather than trying to fix it forever.
</details>

一旦 CI 通过，我们就需要找到合适的审查人员。我们的做法是对正在被测试的源文件运行 git blame，找出贡献最多的人并指派给他们，同时开启自动合并。如果他们批准，PR 就会被合并；如果他们拒绝，该文件就会进入我之前提到的 30 天冷却期。

<details><summary>Original English</summary>
Once CI is green, we need to find the right reviewer. What we do is we run get blame on the source file being tested. find the top contributor and assign it to them and turn on auto merge. If they approve it, the PR gets merged. If they reject it, the file goes into the 30-day cool down which I previously mentioned.
</details>

### 里程碑 4：标签触发器与挑战

这把我们引向了里程碑 4。一旦这一切都能为已有代码回填测试，我们就希望让工程师同样能轻松地为他们正在编写的新代码获取测试。现在，任何工程师都可以在自己的 PR 上添加 write test 标签。它接入了我们刚才梳理过的同一套 Temporal 基础设施。唯一真正的区别在于选择机制：我们不再使用选择器脚本，而是直接从工程师的 PR 中提取文件。agent 编写测试，随后你会得到一个链接回原始 PR 的草稿 PR。现在让我们谈谈我们遇到的一些挑战。我们的 agent 最初运行在 Linux 机器上，上面没有安装 Xcode 或 SwiftLint。因此当 agent 发起一个 PR

<details><summary>Original English</summary>
This brings us to milestone four. Once all of this was back filling tests for existing code, we wanted to make it just as easy to get tests for the new code engineers were writing. Now, any engineer can add or write test label to their own PR. It hooks into the same temporal infrastructure we just walked through. The only real difference is selection. Instead of the selection script, we take the file straight from the engineer's PR. The agent writes the test and you get a draft SPR link back to your original one. Now let's talk about some of the challenges that we ran into. Our agents originally ran on Linux machines which don't have X code of Lint installed. So when an agent would open a PR
</details>

<!-- chunk 27/50 -->

### 解决 Lint 与 PR 质量问题

在大约 20 到 30 分钟后，CI 经常会在 Lint 阶段失败。这既浪费了 Agent 的时间，也浪费了 CI 时间——而 CI 资源正变得日益稀缺。曾有一段时间，我们 30.6% 的 PR 都因 Lint 失败；而当我们深入调查时，发现其中 62% 的失败仅仅源自两条 Lint 规则。我们分层解决了这个问题：第一层是在 Prompt 中提供更好的示例，并列出需要避开的陷阱；第二层是一个在 CI 中自动修复 Lint 错误的 GitHub Action；第三层则是审查那些无法自动修复的规则，我们基本移除了那些信号价值不高的规则，这让 Agent 和人类工程师的工作都变得更轻松；最后，真正的解决办法是在我们把 Agent 迁移到 Mac runner 之后——这样 Agent 现在可以在提交 PR 之前在本地构建并检查（Lint）代码。

<details><summary>Original English</summary>
after about 20 or 30 minutes CI would fail frequently on Lint. This waste the agents time and CI time as well which is an increasingly scarce resource. For a while 30.6% of our PRs were failing due to lint and then when we dug into it 62% of those failures came from just two lint rules. We fixed this in layers. The first was better examples in the prompt along with pitfalls to avoid. The second was a GitHub action that autofixes lint errors in CI. The third was an audit of the rules that couldn't be autofixed. We essentially removed the ones that weren't high signal. And this made life easier for both agents and human engineers. And finally, the real fix came when we moved the agents to Mac runners. So now the agents could build and lend the code locally before opening up PR.
</details>

第二个挑战是 PR 的质量。当我们把一个 PR 分配给人类时，我们希望它是人类真正能放心批准的东西。但 Agent 有时会选择通往 CI 绿灯的最短路径：我们见过 Agent 修改业务代码来让失败的测试通过；也见过它们修改、删除或静音现有的测试；还见过它们在测试中加入漫长的等待时间，这会导致 CI 变得不稳定（flaky）。

<details><summary>Original English</summary>
The second challenge was PR quality. When we assign a PR to a human, we want it to be something they'd actually feel comfortable proving. But agents sometimes take the shortest path to green CI. We saw agents editing production code to make a failing test pass. We also saw them modifying, deleting or silencing existing tests. And then we saw them adding long weight to tests which can make CI flicky.
</details>

同样地，这里也没有单一的灵丹妙药，因此我们构建了三层防线：第一层是确定性规则——如果一个 PR 触碰了任何不是测试、Mock、Fake 或 Stub 的文件，我们就直接将其关闭；第二层融入了我们的 AI 代码审查——在 Duolingo，我们使用 Claude 和 Codex 来审查每一个 PR，这些机器人经常会留下评论，因此我们构建了一个 Agent，在人类查看 PR 之前先解决所有 P0 级别的评论；第三层则是以大语言模型作为裁判（LLM as a judge）——这是一个专为这些测试 PR 构建的审查 Agent，它会读取 PR diff，并拒绝业务代码修改、被更改或删除的测试、被禁用的测试以及漫长的等待时间。随着我们了解得更多，我们也在不断向它添加额外的检查项。

<details><summary>Original English</summary>
Again, there was no single fix here. So we built three layers. The first is the deterministic rule. If a PR touches any file that isn't a test, a mock, a fake or a stop, we close it out. The second builds in our AI code review. At Dualingo, we use Claude and Codex to review every PR and those bots often leave comments. So we built an agent that resolves any P 0 comments before a human ever looks at the PR. And the third is an LLM as a judge. It's a reviewer agent built just for these test PRs. It reads the PR diff and rejects production edits, changed or deleted tests, disabled tests, and long weights. And as you learn more, we keep adding additional checks to it.
</details>

### 成效与推广

到目前为止，这个 LLM 裁判已经审查了大约 1,200 个 PR，并拒绝了其中的 73 个。每一次拒绝都会附带一条像这样的评论，准确说明为什么该 PR 会被拒绝。然后我们会读取这些反馈，并将其反哺回我们的 Prompt 和技能中，这样同样的错误每次出现的概率就会降低。

<details><summary>Original English</summary>
So far, the LLM as a judge has reviewed about,200 PRs and rejected 73 of them. Every rejection comes with a comment like this one saying exactly why the PR was rejected. We then read that feedback and fold it back into our prompts and skills so the same mistakes get less likely each time.
</details>

那么，让我们来看看所有这些努力带来的成果。自我们启动以来，该流水线已合并了 700 多个测试 PR，新增了约 225,000 行测试代码。其中的每一个 PR 都经过了人类的审查与批准。MVVM 的测试覆盖率从 9% 提升到了 59%，整体覆盖率从 11% 提升到了 24%。最重要的是，我们现在拥有的代码库让工程师和 Agent 能够更快、更有信心地交付。

<details><summary>Original English</summary>
So, let's talk about what all of this added up to. Since we started, the pipeline has merged more than 700 test PRs, adding about 225,000 lines of test code. Every one of those PRs was reviewed and approved by a human. MVVM test coverage went from 9% to 59% and overall coverage went from 11% to 24%. Most importantly, we now have a code base so engineers and agents can ship faster and with more confidence.
</details>

这里还有一些更有趣的统计数据：自 3 月以来，该流水线编写了代码库中所有新增测试文件的 34%、所有新增测试用例的 44%，以及添加到代码库中每条脚本行的 10%。有趣的是，在过去的几周里，这个份额实际上有所下降，因为工程师们现在自己开始编写更多的测试了——老实说，这才是最终目标。

<details><summary>Original English</summary>
Here's a few more interesting stats. Since March, the pipeline has written 34% of all new test files in the repo, 44% of all new test cases, and 10% of every strip line added to the codebase. And interestingly, that share has actually dripped in the last few weeks because engineers are now writing a lot more tests themselves, which is honestly the end goal.
</details>

嗯，这里是自 4 月份回填（backfill）开始按计划运行以来的覆盖率曲线。你可以看到它在 6 月和 7 月左右略微向上弯曲，那是我们真正加速推进流水线的时候。

<details><summary>Original English</summary>
Um, and here's the coverage curve since April when the backfield started running on a schedule. You can see it bend slightly upward around June and July, which is when we really wrapped up the pipeline.
</details>

那么，在做这个项目的过程中，我们学到了什么？第一点是，这种模式是可以推广的——我们谈到的闭环（识别、编写、验证、解决、迭代）并不局限于测试。单元测试只是最容易摘到的果子，任何符合这种形态的工作都可以在相同的基础设施上运行。这正是我们作为一家公司开始在做的事情：我们正在将同样的闭环应用于现代化改造——将屏幕重构成 MVVM 和 SwiftUI、在 Android 上将代码迁移到 Coroutine，以及生成快照测试。

<details><summary>Original English</summary>
So, what have we learned while doing this project? The first thing is that this pattern generalizes the loop we talked about identify, write, verify, resolve, iterate, it isn't specific to testing. Unit tests were just the lowest hanging fruit and any job that fits the shape can run on the same infrastructure. And that's exactly what we're starting to do as a company. We're applying the same loop to modernization to modernizing screens to MVBM and Swift UI, migrating code uh on Android to Corines and generating snapshot tests.
</details>

所以在结束之前，我想留给大家一个思想实验：现在出现了一类像 Jev 这样快速、通用的分类器，它们接收某种状态，并在毫秒级内输出一个动作。那么，如果我们把 PR 生命周期工作流中的手写决策树替换为这类分类器会怎样？输入 PR 状态，分类器挑选下一个动作，我们全部在毫秒级内执行完毕。

<details><summary>Original English</summary>
So before I wrap up, I want to leave you with a thought experiment. There's a new class of fast general purpose classifiers like Jev. They take in some state and output an action in milliseconds. So what if we replace a handwritten decision tree in the VR life cycle workflow with one of these? PR state goes in, the classifier picks the next action and we execute it all in milliseconds.
</details>

我还要感谢几位与我一起开展这项工作的同事：Jesse、Guadalupe、Hunter 和 Jiha。他们构建了这个项目所依附的许多平台组件，并帮助审查了大量此类代码。以上就是我的全部内容。非常感谢大家一路坚持听到这里。如果您想进一步了解，我们在 Duolingo 工程博客上撰写了关于该流水线的文章。如果您也在构建类似的东西，我也很想与您交流。您可以在 LinkedIn 或 X 上找到我。

<details><summary>Original English</summary>
I also want to thank a few folks who worked on this with me. Jesse, Gordalup, Hunter, and Jiha. They built a lot of the platform pieces this project stands on and helped review a lot of this code. That's it for me. Thank you so much for making it this far. If you want to go deeper, we've written about this pipeline on the dual engineering blog. And I'd also love to hear from you if you're building something similar. You can find me on LinkedIn or next.
</details>

### 引爆 Agent Skills

>> 大家好，欢迎来到我的演讲，主题是当你引爆数千个 Agent Skill 时会发生什么。这是对我们 Agent 引爆室内部的一次探秘，以及当我们把 Skill 放入其中时所观察到的情况。我叫 Roi，是 Zenity 的一名主任工程师（Staff Engineer），也是一名研究员。我经常探讨应用安全（AppSec）与安全议题。欢迎在 Twitter 和 LinkedIn 上关注我。

<details><summary>Original English</summary>
>> Hi everyone, welcome to my talk about what happens when you detonate thousands of agent skills. This is a look inside our agent detonation chamber and what we saw when we put skills in there. My name is Rowi. I'm a staff engineer at Zenity and I'm a M research fellow. I talk a lot about AFD and security. Follow me on Twitter and LinkedIn.
</details>

在正式开始我们的议程之前，我们需要先谈谈什么是 Agent Skill。从本质上讲，Agent Skill 就是按需提供的能力。它包含了一组指令、资源和新的行为，可以包含脚本，甚至可以包含代码。问题在于，它是由别人编写的——而这正是问题开始的地方。

<details><summary>Original English</summary>
Before we even start our uh session, we need to talk about what an agent skill is. Well, essentially an agent skill is capability capability on demand. It has a bunch of instructions, resources, new behavior. It can contain scripts and it can even contain code. The problem is that it was written by someone else. And this is exactly where the problem start.
</details>

那么我们来看看这个 Skill 的执行轨迹（trajectory）。举个例子，如果我们观察这里的轨迹，我们可以看到该 Skill 会读取云配置和 Kubernetes 配置，它会联系身份服务，甚至还会探测实例元数据端点。现在我并不知道这个 Skill 的原始意图是什么，但我可以告诉你，许多信息窃取程序（info-stealers）也是以相同的方式运作的——它们扫描各种机密和身份文件夹。然而在本例中，它却是一个官方的 Azure 诊断 Skill。而这正是我们很难去识别一个 Skill 究竟是恶意的还是良性的关键所在：我们必须根据其行为来理解该 Skill 的原始意图。

<details><summary>Original English</summary>
So let's take a look at the skills trajectory. For instance, if you look at this, if we look at the trajectory over here, we can see that the skill reads through um the cloud configuration and Kubernetes configuration. It contacts the identity service and it even props the int the instance metadata endpoint. Now I don't know what was the original intent of the skill but I can tell you that a lot of um info stealers are operating in the same way. They scan for the different secret and identity folders. In this case however it was an official Azure diagnostic skill. And this is exactly the point where it's kind of hard for us to identify whether a skill is malicious or benign. And we have to understand the original intent of the skills according to its actions.
</details>

看到这里你可能会问：好吧，那我们直接扫描这个 Skill 不就行了吗？嗯，事情比这更复杂。我们注意到的第一个问题是，有效载荷（payload）完全存在于别处。在许多 Skill 中，`skill.md` 仅仅是一个入口点：它可以调用另一个包含其余 Prompt 的端点；可以作为其安装脚本的一部分下载另一个包；而且它可能还包含另一个脚本或代码，去下载其他的载荷和其他包。因此，如果你只使用静态扫描器并阅读 `skills.md`，你就会遗漏所有这些内容，如果不希望漏掉它们，你就必须创建某种机制来追踪所有这些载荷。

<details><summary>Original English</summary>
And at this point you might ask, okay, so we can just like scan the skill, right? Well, it's it's it's more complicated than that. The first problem problem that we've noticed is that the payload just lives elsewhere. In a lot of the skills, skill.md is just the entry point. It can invoke another endpoint that contains the rest of the prompt. It can download another package as part of as part of its installation script and it might have another script or code that downloads other payloads and other packages. So if you use just a static scanner and read through skills MD, you would lose all of that and you would have to create some sort of mechanism to track all of these payloads if you don't want to lose them.
</details>

我们注意到的第二个问题是，大语言模型分析器是可以被欺骗的。Trail of Bits 进行过一项非常有趣的研究，他们在其中展示了一个 Skill：该 Skill 篡改了其中一个项目的包注册表，并且附带了一条简短的注释，声称应用安全团队已经批准了这一变更，而这完全骗过了分析器。

<details><summary>Original English</summary>
The second problem that we've noticed is that LM analyzers can be tricked. Um there was a really interesting research by trail of bits in which they showcased a skill that manipulated the package registry of one of of one of the projects and it had like a small comment that said that the appsec team appro approved this uh change and it completely worked on the analyzer.
</details>

因此，鉴于扫描并非万无一失，我们采取了一种不同的做法——我们实际上决定直接让 Agent 运行该 Skill。多年来，恶意软件研究人员一直在使用这种技术，它被称为引爆——引爆室。于是我们针对 Agent 和 Skill 创建了同样的东西。

<details><summary>Original English</summary>
So given that scans are not bulletproof we've resorted to a different kind of action and we actually decided to just run the skin with the agent. Um this is a technique employed by malware researchers for years now. Uh and it's called detonation a detonation chamber. So we created the same one but for agent for for agents and skills.
</details>

这就是我们的第一个版本。在我们的第一版中，我们创建了一个任务 Prompt，将一个 Agent 和一个 Skill 放入沙盒中，让它运行几分钟或几小时，直到完成任务，带着未被观测的 Agent 轨迹并对其进行分析。你可以想象，这还远远不够。我们的第一个问题在于，环境大部分时间都是缺失的。许多 Skill 依赖于 CLI 工具，依赖于特定服务，甚至依赖于项目的存在。举例来说，你可以想象一个 Notion Skill，它必须有一个可用的 Notion 服务来与之通信。因此，我们添加了一个环境构建器（world builder），它会审视 Skill 并相应地构建合适的环境。

<details><summary>Original English</summary>
And this was our first version. In our first version uh we created a task prompt. We put an agent and a skill inside a sandbox. We let it operate over like minutes or or hours until until it completed a task. with unobserved agent traces and analyzed it. You can imagine that it wasn't enough. Our first problem was that the environment was missing most of the time. A lot of skills rely on CLIs. They rely on specific services and even on on existence of the pro of projects. You can imagine notion skill for instance. This will have to have a notion service available to talk to. So, we've added a world builder that looks at a skill and builds the appropriate environment accordingly.
</details>

但接着我们又遇到了另一个问题：通用的任务 Prompt 可能并不适用于所有 Skill。我是说，想想看吧：你可能会有一个需要制作演示文稿的演示文稿 Skill，或者……

<details><summary>Original English</summary>
But then we'll cover another issue. A generic task prompt might not be enough for all skills. I mean, think about it. You can have a presentation skill uh that needs to create a deck or
</details>

<!-- chunk 28/50 -->

部署技能需要发布一项服务，头脑风暴技能需要探索一个想法。它们每一个的运作方式都完全不同。以发布服务为例：你需要学习如何配置它，需要学习如何部署它，需要通过快照告诉它如何从快照中恢复。它们每一个都需要不同的一套提示词，而且你还需要确保覆盖该技能中的每一条路径，因为其中某一条可能具有恶意。所以我们创建了专门做这件事的操作器。它通读技能，并试图分析我们应该调用哪些不同的轨迹。虽然它运行得相当不错，但如果你跟智能体打过交道，尤其是在安全领域，你就能评估出我们遇到了大量的安全护栏、合规限制。我们收到了很多拒绝，智能体不愿意解码，而当它愿意解码时，它又不愿意执行。所以我们不得不给它一个无法拒绝的条件，从本质上创建一个对抗性操作器来促使智能体运行；如果它没能运行，甚至可以从头开始重新运行。

<details><summary>Original English</summary>deployment skill that need to ship a service, a brainstorming skill that needs to explore an idea. Each and every one of them has an entirely different modus operandi. Let's take shipping shipping a service for instance. You need to learn how to configure it. You need to learn to deploy it. You need to tell it to recover from snapshots using snapshots. Um each and every one of them uh requires different set of prompts and you also need to need to make sure that you um cover every route in the in that skill because one of them can be malicious. So we created the operator that does just that. It reads through the skill and tries to analyze what are the different trajectories um that we should invoke. And while it worked pretty well, if you worked with agent, you can especially in the security domain, you can um assess that we went through a lot of uh safeguards, safeguard legals. Um we we got a lot of refusals. um the agents wasn't willing to decode and and when it was willing to decode it wasn't willing to execute. So we had to give him an offer it can't refuse and essentially create an adversarial operator that convinces the agents to run and uh in case it didn't run even like start the run from the beginning.</details>

现在我想强调的是，我们在这里做的是安全研究。这是一个容器环境，这里面没有任何恶意的东西。但为了让它正常运行，这是我们必须做的事情之一。我还想指出，很多时候安全防护机制所针对的对象，完全是……

<details><summary>Original English</summary>Now I would I would emphasize that we're doing a security research here. This is a container environment. Nothing is malicious in here. But this is one of the thing that we had to do in order to make it run properly. I would also note that a lot of the time safeguards are being run on something which is definitely</details>

Heat. Heat.

<details><summary>Original English</summary>Heat. Heat.</details>

All right.

<details><summary>Original English</summary>All right.</details>

Heat. Heat. Heat. out of Heat. Heat. Heat. Heat.

<details><summary>Original English</summary>Heat. Heat. Heat. out of Heat. Heat. Heat. Heat.</details>

### AI 的自动化困境与双重幻象

给我一秒钟确认这个是否正常工作。太棒了。我是 Diego Almeida，这场演讲的题目是《I love you so jeving much》。这是引用了 Glass Animals 的梗，我们并不是什么怪人。就像我说的，我是 Diego Almeida。我被称为“Jev guy”，有时也叫“Jevy Pinkman”。我也共同开创了 ChatGPT、RLHF 和 InstructGPT，但我猜今天的观众大体上都知道我是谁。我有一堆关于 AI 的具体内容想聊，但我喜欢先切入我在 AI 领域最喜欢的话题。第一个是：究竟正在发生什么，以及所有的自动化到底都在哪里？如果你以前听我说过这个，我很抱歉，但这确实是必须反复灌输给这个领域的一件极重要的事情，因为人们仍然不理解，我需要大声疾呼，直到每个人都真正明白究竟是怎么回事。如果你是搞 AI 的，你应该有一个非常好的答案，来解释为什么 AI 可以做那么多极其出色的事情，却在一大堆其他事情上仍然如此毫无用处。

<details><summary>Original English</summary>Give me a sec to make sure this is working. Heck yeah. I'm Diego Almeida and this talk is I love you so jeving much. Um glass animals reference. We're not just weird. Um like I said, I'm Diego Almeida. I'm known as the Jev guy, sometimes Jevy Pinkman. Um, also co-created chat GPT, RLHF, and Instruct GPT, but I assume that for the crowd today, you all know who I am, at least mostly. Um, I have like a bunch of AI specific stuff I want to get to, but I like going into my favorite topics in AI. First one is what the is actually going on and where is all the automation. If you've heard me say this before, I'm sorry, but it's such an important thing to beat into the field because people still do not get it and I need to yell this until everyone really understands what the is going on. And if you're an AI, you should have a really good answer about why AI can do so many awesome things and yet still be so useless for a bunch of other ones.</details>

我与 ChatGPT 的关系有些独特。我是为数不多既参与创造了 ChatGPT 又对其提出批评的人。澄清一下，我并不讨厌 ChatGPT。我很喜欢使用智能体，很喜欢使用编程智能体，也喜欢聊天机器人。它们只是相当受限。特别是，我认为令人稍感遗憾的是，它们在多大程度上把这个领域分化成了过度承诺与交付不足。在我看来，这给世界带来了非常、非常糟糕的影响。我想聊聊 AI 领域的两个狂热阵营，以及我们如何化解这种认知失调——我认为每个人除非有一个非常好的解释，否则都应该体会到这种失调。

<details><summary>Original English</summary>My relationship to chat GPT is somewhat unique. One of the few people who hates on chat GPT who made it. I don't hate chat GPT to be clear. I love using agents. I love using coding agents. I love chat bots. They're just quite limited. And in particular, I think it's a little tragic how much they've bifurcated the field into overpromise, underdeliver. Really, really terrible stuff for the world in my opinion. And I like to talk about like the two cults in AI and how we can resolve the cognitive dissonance that everyone I think should be having unless they have a very good answer.</details>

第一个阵营，你们知道的，就是像有效利他主义者（EA）那样的阵营。他们看着所有的基准测试，然后说大语言模型不仅在几乎每一个基准上都超越了人类水平，而且两年来一直如此；从类似 03 的时代开始，我们这两年来一直在宣布 AGI 还有三个月就要到来——大家还记得那个模型吗？现在甚至已经没人关心那个模型了，而那曾经是 OpenAI 内部对 AGI 狂热炒作的顶峰。而在另一边，你去看非基准测试的事物，你去看看现实，你看看世界上的其他地方——特别是如果你们走出旧金山去外面看看——尽管 AI 这么酷，世界上很大一部分依然没什么改变。我认为 AI 具有变革性。真正认为 AI 很酷、具有变革性，同时又觉得它目前在现实世界中令人大失所望，这是一种少见的视角。

<details><summary>Original English</summary>There's cult one, which is, you know, the cult of like EAs. They look at all the benchmarks and they say like not only are LM surpassing human level on basically every benchmark they have been for two years we've been announcing AGI three months away for two years now even since like the 03 days do people remember that no one even car cares about that model anymore and it was that that was like peak internal to openai AGI hype and on the other hand you look at the nonbenchmarks and you look at the reality and you see the rest of the world especially if you guys go outside and leave San Francisco a lot of the world is like really unchanged despite AI being so cool. And I think AI is transformative. It's a rare point of view to actually think AI is cool and transformative and also like underwhelming the world right now.</details>

棘手的地方在于，这是同一个领域，我们看到的也都是同样的事实。那么究竟是怎么回事？为什么 AI 会呈现出所谓的锯齿状特征？为什么它能在某些事情上表现得如此出色，而在其他事情上却如此不灵，对此符合奥卡姆剃刀原理的解释是什么？我会飞快地过幻灯片，不好意思，也许我可以为拍照的人慢下来一点，但我注意到这会进行得很快，我先说明这点。所以我认为，我们作为一个领域，应该有一个符合奥卡姆剃刀原理的解释：为什么有些事情它们不仅表现好，而且好得令人难以置信，达到了超人级别，比如数学领域的千禧年大奖难题；但在另一方面，它们不仅表现差，而且毫无用处到连做会计都碰不了。那听起来可比数学里的千禧年难题简单得多，对吧？后者我能做，前者我绝对做不了，而我曾经还是个数学竞赛选手。那么这里的问题出在哪里？造成这种情况的原因是什么？

<details><summary>Original English</summary>And the tricky part is this is the same field and we are all seeing the same facts. So what gives you know why is AI jagged so to speak like why can it be so good at some things and so not good at other things and what is the aams razor explanation for that um I will be blasting through my slides fast I'm sorry maybe I could slow down for people taking pictures um but uh I'm noticing that uh this is going to go fast is all I'm saying so I think that we as a field should have an aams razor explanation for why are there some things that are Not just good, they're unbelievably good, superhuman, like millennium price problems in math. But on the other hand, they're not just bad, they're so useless, they can't even be used to touch accounting. That sounds way easier than million prize problems in math, right? I could do the latter. I definitely could not do the former. And I was a mathlete. So what gives here? What is the reason for this?</details>

我平时很喜欢把这里作为一个互动环节，但我今天打算直接告诉你们我的答案。抱歉造成了这种自上而下的局面。左边的所有任务，本质上都是需要人参与其中的任务。比如深度研究，我做不了比深度研究更好的结果，模型在这方面太强了。但要是拿枪指着我或指着你的头，让你在我和深度研究之间选一个，而且答案必须是正确的，而不是写得漂亮的，你可能每一次都会选我。这就是针对自动化进行优化的区别所在，自动化往往要容易得多、简单得多。然而 AI 却一再在这上面失败。每年都会出现一些臭名昭著的失败案例，AI 甚至连汽车穿梭餐厅的自动化都做不成。这应该会让大家感到有些震惊。我的观点实际上是，对于这些任务来说，讨好人类与完成任务毫无关系。你真正想做的是基本上保持一层抽象；你希望做出决策，然后重新回到执行自动化上，而代码正是自动化的语言。因此，你需要与代码进行整合。

<details><summary>Original English</summary>And I normally love this as an interactive thing, but I will instead just tell you my answer. Sorry for the power dynamic. Um, everything on the left side is intrinsically a human in the loop task. Like deep research, I could not do better than deep research. The models are so good at that. But if gun to my head or gun to your head, you had to pick between me and deep research. And the answer had to be correct, not well written, you'd probably pick me every time. And that's the distinction between like optimizing for automation, which tends to be a lot easier and a lot simpler. Yet m AI keeps failing at this. Every year there's like an infamous failure of AI failing to even automate drive-throughs. And that should be kind of shocking to people. And my claim is actually for these tasks pleasing a human is nothing to do with doing the task. What you want to do is basically be an abstraction away. You want the decision to be made and you want to get back into doing automation and code is the language of automation. Therefore, you need to integrate with code.</details>

### 从辅助型 AI 转向机器原生自动化

这里包含很多内容，但我会再总结一次。我明白这其中的讽刺意味：大家都知道我参与共同创造了 RLHF，而我确实认为 RLHF 是问题的一部分；特别是 RLHF 正是如今所有的 AI 都需要人类参与其中的原因——带一个星号，除非任务本身琐碎易验并且能够自行运行，但之后仍需要人在回路中进行验证。这是因为我们确实把它加了进去，这正是 RLHF 中“HF”（人类反馈）的含义。我的观点是，存在一条更好的路径。我对现状的总结是：如今 100% 的大语言模型都是为提供辅助而优化的。你可能会提到 RLVR，但如果 RLVR 模型没有经过 RLHF，与之交互的体验会非常糟糕。其结果是大语言模型在提供辅助方面变得好到令人难以置信。它们确实太强了。比如，针对你的 ChatGPT 提问，你绝不应该选我不选 ChatGPT。但对于实际执行那些在后台运行的认知工作，你根本不该信任大语言模型，因为它们并未针对这一点进行优化，这就是为什么它们在自动化任务上表现得如此糟糕。而且我推测，自动化的价值要远远高于辅助，因为你可以做酷得多、深刻得多的事情。我稍后会深入探讨这一点，但我认为有太多事情是我们能做的，而我们现在仅仅触及了皮毛，这就是目前 AI 的状态对我而言令人遗憾的地方。

<details><summary>Original English</summary>This is a lot but I will summarize it again. I get the irony that uh you know I've co-created RHF and I do believe RLHF is part of the problem and RHF in particular is why all AI today does require a human in the loop with an asterisk unless the task is like very trivially verifiable and can run on its own but still requires a human in the loop to verify it afterwards. It is because we literally put it in that is what the HF is in RHF. And my claim is that there's a better way. You know, my summary of the state is 100% of LMS today are optimized for assistance. You might talk about RLVR, but the RLVR models are very bad to interact with if they've not been RHFed. The result is LMS become too good to be true at assistance. They are just so good. Like, you should never pick me over chat GPT for your chat GPT queries. But for actually doing like you know run in the background cognitive work you should not trust LMS at all because they have not been optimized for that which is why they're so bad at the tasks of automation and I would also guess that automation is a lot more valuable than assistants because you can do way cooler deeper I'm going to get into this later but I think there's going to be so much stuff that we can do and we are just scratching the surface of that right now and that's the tragic thing about AI uh the state of AI for me</details>

我们来聊聊这种演变。我不知道放这个合不合适，但已经太迟了。天哪，别给这一页拍照。太好了，我看到有人竖大拇指了，好的，太棒了。所以我们不再去做 RLHF，我们必须去做别的事情。我们需要从第一性原理去思考：如何针对机器原生 AI 进行优化？希望你们大家了解 Jev 的界面，那就是我们正在做的事。比优化其界面更重要的，是我们正在重新思考 AI 应该如何去构建，因为这就是我们当初为 RLHF、为萨顿的“惨痛教训”所做的事情。为了让我的观点更容易表述，我作一个宽泛的意译：扩展规模和计算算力比算法更重要。这就是为什么人们会变成被规模参数蛊惑的信徒。而我认为，存在着一个比这更加惨痛的教训

<details><summary>Original English</summary>let's talk about the evolution Um, I I can't tell if this is appropriate, but it's too late. Um, oh god, don't take pictures of this one. Um, cool. Oh, I'm getting a thumbs up. Yeah. Uh, excellent. So, we're we instead of doing RHF, we just have to do something else. We need to think from first principles. How do we optimize for machine native AI? You guys hopefully know the interface of Jev and that is what we are doing. more important than optimizing for its interface, we are uh rethinking how AI should be done because this is what we did again for Arlf for Sutton's bitter lesson. I'm going to loosely paraphrase to make my point easier to say is that scaling um and compute matters more than algorithms. This is why people become like scaling pill jironies. And I would argue that there's an even bitter lesson than that</details>

<!-- chunk 29/50 -->

也就是说，数据永远比算力更重要。现在我们领域内已经相当深刻地认识到这一点了，但其实从一开始这就显而易见。

<details><summary>Original English</summary>
which is data always matters more than compute. We are learning that quite a bit in the field now, but it has been obvious since the beginning of time.
</details>

我会告诉你什么时候——这张才是大家该拍照记录的一张。我认为最苦涩的教训在于：选对任务。而“选对任务”是一个很奇特的思考维度，尤其是对做机器学习的人来说，因为他们喜欢算法，希望数值往下走、往上走，或者往任何代表好的方向变化，却不想去考虑现实世界。然而，这恰恰向来是获取巨大性能提升的方式，重大突破正是这样发生的。每一次、百分之百都是源自于此，这对于传统的强化学习游戏同样适用。

<details><summary>Original English</summary>
I'll tell you when the this is the one you should be photographing. I would argue that the the bitterest lesson is doing the right task. And doing the right task is like a weird thing to think about especially for ML people because they like algorithms. They want number goes down or up or whichever is good direction. They don't want to think about the real world. But this is always how you make gigantic gains in performance. This is how the big breakthroughs happen. 100% of the time it comes from this and this is true for classical RL games.
</details>

这就是为什么萨顿得出了他的苦涩教训：在做采样回放（rollouts）时，数据是由算力衍生出来的，比如在下国际象棋之类的场景中，你为什么会需要策略外（off-policy）数据呢？而什么是正确的任务，规则本身就定义好了。

<details><summary>Original English</summary>
This is why Sutton had his bitter lesson it which is data is derived by compute when you're doing rollouts like there's there's why would you need off policy data when playing chess or something like that and doing the right task is defined by the rules.
</details>

因此，在做强化学习时，你甚至根本不需要去思考什么是正确的任务。而对于预训练，作为整个领域，我们其实不得不对“正确的任务”进行了大量的思考。我不知道大家还记不记得采用掩码语言模型（masked language modeling）的早期阶段，但当时花了不少时间，而且很不明确，最终才弄明白预测下一个词元（next token prediction）非常厉害。这并不是因为它在掩码语言建模上表现更好。要知道，这些目标函数本身并没有什么特别之处，关键在于你随后能用它们来做什么。事实证明，预测下一个词元在生成文本序列上有着不可思议的表现，而这正是这些预训练模型所极其擅长的。

<details><summary>Original English</summary>
So actually when you're doing RL you don't even need to think about the right task for pre-training we actually as a field had to do a lot of thinking about the right task. I don't know if people remember the birth days with um masked language modeling, but it took a while and it was very unclear to figure out that next pro token prediction was super cool. Not because it was better at masked language modeling. You know, the objectives on their own aren't special. It's about what you can do with them afterwards. And it turns out next token prediction is incredible at generating strings, which is what these pre-trained models were so good at.
</details>

所以，无论采用多高水平的掩码语言模型，即使拥有今天的算力和算法，它也绝不可能像 GPT-3 那样引人注目，因为那纯粹是在做一个不同的任务。至于数据，显而易见，互联网本身就是一个巨大的瓶颈。现在大家就像在为了获取更多数据去焚书或做什么似的。但数据的重要性显然远超算力，人们只是不断在重新发现并想通这一点。在让大语言模型真正发挥用处这件事上，更是如此。

<details><summary>Original English</summary>
So no level of mass language modeling even if you had today's compute and algorithms would make it as interesting as GPT3 was because it was just doing a different task and data you know the internet is obviously a giant bottleneck. Now we're like you know burning books or whatever in order to get more data but data obviously matters a lot more than compute and people keep like rediscovering this and figuring this out. It's extra true for making LLMs useful.
</details>

在 RLHF 出现之前，用于 RLHF 的数据甚至都不存在，两者带来的差异可谓天壤之别。我给大家看下一张幻灯片，这大概是相关的部分。这是 RLHF 论文里的研究工作，宏观层面的结论是：即使采用世界上最笨拙的算法，哪怕只用 GPT-2 规模的模型，你也能得到类似 GPT-9 级别的表现——真正的 GPT-9，而不是今天那些虚标的 GPT 数字。以前这些数字意味着在预训练的有效算力上有 100 倍的扩展，而现在他们已经放弃了这种命名，因为已经无法再这样扩展了。即便如此，在遵循指令的任务上，可能需要像 GPT-7 到 9 那样的模型，才能匹敌 2018 年左右的那个 GPT-2 级模型。

<details><summary>Original English</summary>
um before RHF even existed the data for RHF didn't exist and you could like it was night and day I'll just show you the next slide this is the probably the relevant part this is what this was the work in the RHF paper and the high level was that even with the dumbest algorithms in the world even with a GPT2 sized model you got something like GPT9 level performance like real GPT9 not today's like fake GPT numbers like the numbers used to mean like a 100x scaling and effective compute for pre-training and they've given up on that because it just can't scale anymore. And still even with that, it would take something like GPT7 to9 to match GPT to the model from like 2018 or whatever it was at the task of instruction following.
</details>

这确实有些不可思议，因为大家总觉得大模型对这至关重要——它们确实重要，但与“选对任务”所带来的巨大跃升相比，那并不是最核心的事物。剧透一下，这就是我们对 Jev 所做的事情，对吧？我们在该领域实现了没人预料到会到来的巨大飞跃，正是因为我们在针对某项任务进行优化，而很少有人会去思考什么是正确的任务。

<details><summary>Original English</summary>
That is kind of wild because you think big LMS are so important for this and they are, but that is not the most important thing compared to even the gigantic jump of doing the right task. And spoilers, this is what we did for Jeff, right? like we made this gigantic leap in the field that no one realized could be coming because we were optimizing for a task and very few people think about the right task.
</details>

这也是为什么 Jev 拥有一种特有的难以言表的特质（Jeb Nissiqua）。我觉得这是个非常巧妙的双关语。虽然大家只是同情地笑了笑，但还是谢谢你们。

<details><summary>Original English</summary>
Um this is why Jev has the Jeb Nissiqua. Um that's a really smart bun I think. Um little bit of a pity laugh, but thank you.
</details>

### 可靠的智能与软件重塑

你针对什么做优化，就会得到什么。我一直在找一个比“可靠”更贴切的词，如果大家有建议请告诉我。在大模型中，真正缺失的是一种智能的可靠性。我常把这形容为：你有 95% 的时间得到的是爱因斯坦，却有 5% 的时间得到的是憨豆先生。如果你分不清谁是谁，你到底怎么去实现任何自动化？既然如此，与其去押注那些偶尔灵光一现、需要事后验证的聪明，为什么不专注于极致、极致狭窄的可靠性，从而让你每次都能稳妥地获得这种智能呢？

<details><summary>Original English</summary>
Um you get what you optimize for. I I'm looking for a better word than reliable. So if you guys have suggestions, let me know. But there's there's this reliability of intelligence that's really missing in LLMs. I often call it you get Einstein 95% of the time, but Mr. Bean 5% of the time. And if you can't sell which is which, how the are you going to automate anything? And instead, instead of like focusing on like sometimes occasional smarts that you can then verify, what if you focused on extreme extreme narrow focused reliability so you can get that smarts every time?
</details>

这一点在基准测试中是体现不出来的，而这正是人们喜爱 Jev 的原因。事后我也意识到，我们显然并没有为面向开发者的“ChatGPT 时刻”做准备。但它之所以发生了，是因为 AI 领域的人开空头支票、交差不足的情况太严重了，以至于有一款真正不画大饼的模型出现时，反倒成了令人惊喜的意外。这不是因为速度、成本，甚至也不是因为界面。我的团队曾告诉我，这些东西我不应该对外人讲，这样我们才能保持长期优势，但我就是太在乎这件事了。核心就是可靠的智能。请大家做出真正厉害的模型吧，哪怕完全不用我们的模型也没关系。

<details><summary>Original English</summary>
And this doesn't show up on benchmarks. It is the reason why people love Jev. And this is also I realized in hindsight we obviously didn't prepare for a chat GPT moment for developers. But it happened because people in the AI space just overpromise underdel so much that having a model that actually don't do that was a surprise. And it is not the speed cost or even interface. This is something that you know my team tells me I shouldn't be telling people so that we can have a long-term advantage and I just care too much. Like it's reliable intelligence. Make sick models please. even if we, you know, if it doesn't involve our models.
</details>

我们把 Jev 视作智能软件的基础构件。接下来的这部分我先全部跳过，但我认为软件即将迎来强势回归。我认为所谓的“SaaS 末日论”显然不可能发生；不仅如此，即便把它称作“SaaS 盛宴”，我认为都是一种轻描淡写，稍后我会对此展开谈谈。理想情况下，你们正是听这部分内容的完美听众。我对这一部分感到非常兴奋，因为这对我来说也是全新的思考。

<details><summary>Original English</summary>
Um, we see that Jev as like a foundation for smart software. I'm going to skip all over this, but I think software is going to be so back. I think the narrative of SAS apocalypse is obviously not going to happen, but I think that even calling it a SAS Palooa is like an understatement and I will get into that a bit and you guys ideally are the perfect crowd for this. I'm so excited for this part because that's the part that's new to me.
</details>

我想区分一下“智能软件”与“即时生成软件”。疯狂的地方在于，AI 具有如此巨大的变革性，然而尽管 AI 如此了不起，在过去十年里，软件除了编写成本变得更便宜之外，本质上并没有发生改变。这难道不奇怪吗？我们在软件上能做到的最极限状态，居然只是在旁边放一个聊天机器人，偶尔与软件交互，却无法为你做任何代价高昂的决策，这难道不奇怪吗？如果 AI 真的那么具有颠覆性，这着实是一件有些奇怪的事情。

<details><summary>Original English</summary>
Um, I want to make the distinction between smart software and just in time software. The the crazy part is AI is so transformative and yet somehow despite AI being so awesome, software has essentially unchanged in the last decade except being cheaper to write. Isn't that weird? Isn't the it weird that the best we can do in software is having a chatbot to the side that sometimes interacts with a software but cannot take expensive decisions for you. That is kind of like a a weird thing if AI was really that transformative.
</details>

我认为问题在于我们对编程智能体关注得太多，而没有给予足够的关注去把智能嵌入到内部循环（inner loop）中，关于这一点我稍后会进一步深入探讨。大家都在使用 Jev，也取得了大量的成功，我们不需要去炫耀这些。酷炫的成果非常多，但我的“AIE 秘密”在于：整个领域在推行 Jev 上的力度还远远不够。

<details><summary>Original English</summary>
And I think the problem is we're focusing too much on coding agents and not enough about putting the intelligence into the inner loop, which I'm going to get more into a bit. And people are jeving. There's been tons of successes. We don't need to flex this. There's so many cool things, but my AIE secret is going to be that the field isn't jeving hard enough.
</details>

正如 Swix 所说，我可以向大家提出一个独一无二的行动号召。希望我还有足够的时间来阐述这一点。我认为整个世界依然患有大模型的斯德哥尔摩综合征，我们依然站在一个被大模型完全主导（LLM-pilled）的立场去思考，我认为这是令人遗憾的。大家知道，我很认同一句关于软件的格言：你使用的工具会改变你的思维方式。而我认为它对我们思维方式的改变已经太过了，我们并没有真正去重新审视软件本身，而我认为这个领域恰恰需要这种反思。我们本来完全可以做到多得多的事情。希望在接下来的剩余时间里，我能尽最大努力让大家信服这一点。

<details><summary>Original English</summary>
And this is what Swix said that I can make a call to action for you guys that's unique. And hopefully I have enough time for this. I think the world still has LLM Stockholm syndrome. We are still thinking from a really LLM pill place which is I think tragic you know like I I I love the software saying the tools you use change the way you think and I think that it's changed the way we think way too much and we're not really rethinking software like I think the field needs. I think that we could just do be doing so much more. Hopefully I can try to do my best for my remaining time to convince you guys of that.
</details>

那么，让我们向未来进发吧。

<details><summary>Original English</summary>
Um so let's Jev to the future.
</details>

我非常喜欢的一个类比——请容我啰嗦几句——是关于 LED 的。在蓝光 LED 诞生之前，只有红色和绿色的 LED。它们的能力非常受限，被用于像简单的指示灯以及时钟之类的地方。后来蓝光 LED 被制造或发现了——其实我对计算机科学之外的运作方式并不太懂——但当它问世之后，它所带来的不仅仅是增加 50% 的用例（就像你预期把颜色从两种增加到三种那样），它所实现的远比这多得多。比如，现在 LED 可以用来发出白光，可以用于我们大家现在都在看的显示屏，在照明领域引发了一场革命。LED 拓展出的能力规模之大，令人难以想象；而这仅仅是通过增加一个新的基元，并将其与旧基元组合在一起。

<details><summary>Original English</summary>
Um I an analogy I love bear with me is about LEDs. Before there was the blue LED there was red and green LEDs. These were really limited in capability and they were used for like simple indicators and you know like clocks and stuff like that. And when the blue LED was made discovered I actually don't really know how things outside of computer science work. Um, but when it existed, I guess, um, it enabled not just like 50% more use cases, which what you'd expect about like changing colors from two to three, it enabled so many more. Like now LEDs could be used for white light. It could be used for like the displays that we all use right now. And it created a revolution in lighting. And it's it's it's unfathomable how much bigger the capabilities of LEDs were. Just ex, you know, adding a new primitive that composes together with a old primitive.
</details>

所以你或许能看出我接下来的思路了。我认为软件也是类似的情况。软件是如此不可思议。先抛开过去这半个年代的 AI 不谈，软件本身已经完成了太多极其酷炫的事情。我们用它做了大量的事情。要知道，我很喜欢用 SaaS 吗？其实并不见得。但它解决问题了吗？绝对解决了。而且令人惊叹的是，仅仅依靠三个基本逻辑门，我们竟然做出了如此多的成果。我们只通过简单的二进制运算，做着大于、小于、等于之类的事情；从这样简单的基元中构建出如此庞大的软件世界，简直不可思议。

<details><summary>Original English</summary>
So you can see where I'm going here. maybe. And I think it's a similar story for software. Software is so incredible. Ignore AI for the last, you know, half decade. But software has done so many insanely cool things. We've done a lot of stuff, you know, like do I love using SAS? Not really. But does it solve problems? Abso lutely. And it's incredible how much we've done with three fundamental logic gates. You know, like we are doing this with like simple binary operations that can do things like greater than, less than, equal. It's kind of nuts how much software has been built from such simple primitives.
</details>

而我的观点是，我们现在借助 AI、让智能成为机器原生所做的事情，从概念上讲，相当于添加了第四个语义逻辑门。如果我们能够用常识、意图、人类理解力来编程呢？我们是否还需要……

<details><summary>Original English</summary>
And my claim is that what we are doing with AI now when we're making a intelligence machine native this is kind of conceptually adding a fourth semantic logic gate. What if we can program with common sense with intention with human understanding? Like do we still
</details>

<!-- chunk 30/50 -->

我们需要写带各种疯狂限制的正则表达式，还是说直接声明想要一个 Gmail 邮箱地址或看起来真实的地址就行？为了把事情做成，我们能做的事情非常多，以至于我们需要把低成本、高智能、高速度的边界向前推进。但我认为这里将会出现非常多的新东西。而且我觉得就像蓝光 LED 一样，它的影响将远远不止让软件的表征能力提升 33%。因为它实际上是增加了另一种逻辑门。而这种科幻般的前景，我认为是无法预测的。就像当初谁能预料到互联网会变得如此强大一样，因为它需要更加草根、更加去中心化，需要赋予人们去做那些不可思议之事的权利。

<details><summary>Original English</summary>
need reexes with like crazy things or can we just say like we want a Gmail email address or a real looking one? There's so much that we can do that we're going to need to push the f, you know, push the frontiers of cheap, smart, fast in order to get done. But I think that there's going to be like so many things here. And I think just like the blue LED, it's going to be way bigger than just increasing the representational ability of software by 33%. Because it's adding effectively another kind of sort of logic gate. And this sci-fi is the stuff that I think will be impossible to predict. Just like who could predict how powerful the internet would have been because it requires it's like much more grassroots and decentralized and it requires people to be empowered to do insane stuff.
</details>

我把这称为“软件研究”。这不是开玩笑。但我认为软件能做的事情将会迎来一场大爆发，我们会希望人们去探索软件的那些边界。不一定是因为它有价值，而是因为他们能做到。因为我们有了新的前沿领域去探索，而早期的互联网也是这个样子。当年所有的那些网站都应该存在吗？可能并不应该。但那非常酷，我们从中发现了很多极棒的东西。我认为我们又有了这样一次机会。所以我们不应该继续活在这样一个小鱼缸里，任由 OpenAI、Anthropic 发布什么就受制于什么，只能做所谓的 LLM 套壳。

<details><summary>Original English</summary>
Um I call this software research. Um that's not a joke. Um but uh I I think that there's going to be like an explosion of what software can do and we will want people to be exploring those boundaries of software. Not necessarily because it's valuable, but because they can. Because we have like new frontiers to explore and this is what the early internet was like. Should all of those websites existed? Probably not. But like it was very cool and we found a lot of awesome stuff from that. And I think we we, you know, we have another opportunity for that. So we should not just keep living in this little, you know, fish tank that we are the victims of open anthropic on whatever they ship and we just have to be like LM rappers.
</details>

### 软件研究与真正的软件工程

所以我在这里提出将“软件研究”作为一个方向。其主题将是真正的软件工程，而不仅仅是氛围写代码（vibe coding）。它将会包含只要你做过软件工程师就都知道的那类东西。分解问题，拆分任务。我们需要考虑各个阶段，最好是可验证的阶段，这样我们才能拥有真正的封装。而且我们需要切实做好状态管理，而不是假定所有东西都是 KV 缓存里的全局状态。主题将是那些非常在乎最终结果的人所做的真正工程。它不一定非要有商业价值。理想情况下，它会酷得不行。而且我们应该不断突破极限。

<details><summary>Original English</summary>
So I'm going to pitch software research as a direction here. The theme is going to be real software engineering, not just vibe coding. There's it's going to be like the kind of stuff that everyone has known if you've been a software engineer. Decomposition, breaking tasks down. We need to think about stages, ideally ones that can be verified so we have real encapsulation. And we need to actually do state management instead of assuming everything is global state within a KV cache. And the theme is just going to be like real engineering by people who care a lot about the end result. It doesn't have to be valuable. Ideally, it's sick as Um, and you know, we should be pushing the limits.
</details>

我要讲几个我最喜欢的想法，我想搞清楚如何在世界上推动这些想法。这是我的第一步。我就先聊一聊。我们筹集了一笔资金。所以我想弄清楚如何资助这件事情，但我们还没有做这件事的运营支持。不过这里有一些现成的想法。我认为智能体非常酷，但由于 KV 缓存的束缚，它们在设计上非常不灵活。如果照这个计时器来看，我时间不够了，但请相信我，很多人尝试过做很多事情却失败了，因为与 KV 缓存产生冲突，最终变得效率低下。

<details><summary>Original English</summary>
I'm going to go into a couple of like my favorite ideas and I want to figure out how to encourage these in the world. So, this is my first step at this. I'm just going to talk about it. We have raised a bunch of money. So, I would like to figure out how to fund this, but we don't have the operations help to do that. But here are just some ideas out there. Um, I think agents are they're very cool, but like they're they're so inflexible in their design because of the tyranny of the KV cache. I don't have the time for this if this timer is to be believed, but believe me that there's so much that people have tried to do but failed at because it ends up becoming inefficient because it fights against the KV cache.
</details>

但我认为还有很多事情可以做。为什么记忆开销是 O(NaN)，对吧？为什么我们不能在每次新调用中始终包含编程智能体的所有历史记录？持续学习就是这样运作的，对吧？我们有可用的内存空间。只是我们缺乏在记忆上做 MapReduce 的智慧，无法找出哪些该记住、哪些不该记住。我认为有很多方法可以实现对数级或者更好的查找。为什么在同时创建多个智能体时，它们不能共享状态？为什么它们需要一遍又一遍地重新探索代码库中的相同模式？为什么非朴素路由和子智能体行不通？连朴素路由都行不通，但为什么我们不能做到这些？为什么那些大实验室在子智能体到底行不行的问题上反复摇摆？我认为从工程角度来看它有其优雅之处，但它们与 KV 缓存产生了冲突，而且我认为如果我们围绕这一点来设计智能体，我们能做到的远不止于此。

<details><summary>Original English</summary>
But I think there's a lot more to do. Why is memory o of nan, right? Like why can't we have all of our history of coding agents always included in every new call? That is how continual learning works, right? And we have the memory available. It's just that we don't have the smarts to map produce over the memory to find out like what you should what you should remember, what should you shouldn't. Um I think there's many ways to do login or even better lookups. Why when you're making many agents at once, why can't they not share state? Why do they need to rediscover the same patterns of the codebase over and over and over again? And why can't non-naive routing and sub agents work? Like even naive routing doesn't work, but like why can't we do these things? And why does like the you know the big labs keep going back and forth on whether or not sub agents work? Um I think that like from an engineering perspective there's elegance to it but they fight against the KV cache and I think that if we design agents around that we could do so much more.
</details>

这个方向可能是我所有方向中最模糊的一个，但我对它深有感触。世界上充满了委托代理问题。这是指当你在……你知道，这指的不是代码智能体，而是任何代理人之间存在不可告人的动机。经典例子是公民与民选官员。我不想在这里发表过于政治化的言论，但社会各阶层都存在这种不对齐。这导致了诸如浪费、欺诈等坏事，并且对于一个追求公平的社会来说，会导致过度强调字面规定而忽视精神实质，进而在世界上滋生出漏洞和“充钱就能赢”的利益博弈机制。我认为那个问题的根源在于我们无法把精神实质编码进去。就像软件一样，我们受限于编码比特，而不是我们在那种场景下真正想要表达的意思。我认为通过在方方面面真正对精神实质进行编码，可以让许多组织和社会得到改变。

<details><summary>Original English</summary>
This one's the the probably the most vague of my directions but I feel very strongly about it. Um the world is full of principal agent problems. This is when you have like you know ulterior motives between this is not a coding agent but like any agent. The the classic example is citizens versus elected officials. I don't want to make a too political claim here, but like there's misalignment in all levels of society. And this results in like waste, fraud, bad things, and it it results in for a society that wants fairness, you need to overemphasize the letter over the spirit, which then results in loopholes and play uh pay to-win dynamics in the world. And I think the root of that problem is we can't encode the spirit. Just like with software, we're constrained to encoding bits instead of what we actually meant in that situation. And I think so many organization, society could be transformed by really encoding the spirit all over the place.
</details>

显然，实时智能安全领域，我们能不能防止 OpenAI Hugging Face 沙盒等等事件的发生？为什么他们当初没能防住？并不是因为他们没有相应的智能。我认为找出有人在干坏事要比真正去干坏事容易得多。这是因为当时它还不够快、不够便宜、不够可靠，无法真正做到实时运行。而当每家企业都拥有真正智能的自身实时安全防御时，会发生什么？那该有多酷？关于生成式 UI 我不能多讲，因为后面有人会讲到。我不想抢他们的风头，但这酷极了，相信我。

<details><summary>Original English</summary>
Obviously, real-time intelligence security, can we prevent the OpenAI hugging face sandbox, blah blah blah. Um, why did why couldn't they prevent it? It is not because they didn't have the intelligence. I would argue it's a lot easier to figure out they're doing a naughty thing than to actually do the naughty thing. It is because it was not fast, cheap, and reliable enough to actually run real time. And what happens when every corporation has their own real-time security that's actually smart? How cool would that be? I can't talk about generative UIs because people are going to be talking about it afterwards. I don't want to steal their thunder, but it's cool as Trust me.
</details>

比如语义依值类型（semantic dependent typing）。为什么我们不能拥有一个真正具备语义的类型系统，对吧？为什么我们不能声明我们想要的局部属性，这样我们就不必深入阅读一长串底层依赖项？这些全都是应该做到的。设想一下，如果你能在你的代码检查器（lint checker）里运行一个小模型来检查一切是否类型安全，并且它能够维持语义属性，那该有多酷。之前 Twitter 上有一个关于语音界面的极好视频，总的来说我觉得新界面太令人兴奋了。对我来说，这是……通过智能体软件展现出“做我所想”（do what I mean）的回归。这曾经很流行，但以前从未真正奏效过，因为要真正搞清楚我想表达什么，需要太多的硬编码规则。

<details><summary>Original English</summary>
Um, like semantic dependent typing. Why can't we have like a type system that actually is semantic, right? like why can't we like declare what local properties we want so we don't have to read a chain of dependencies deep down these all should be possible and imagine if you could like run a jeike model in your lint checker to check if you're it's all type safe and it could you know uphold semantic properties it would be so cool there's there was a great Twitter video on um like a voice interface in general I think new interfaces are so exciting this is to me the return of like this is going to show by agent software like do what I mean. This used to be like a popular thing but it never really worked because you it was it was too many hard-coded rules to really figure out what I mean.
</details>

还有遏制垃圾内容（slop），这显然是这里的一个大主题，但我们对此深信不疑。这是我的道具。我有一个为了类型安全准备的“遏制生成式 AI”棒球棒。它非常非常棒。我想谈谈垃圾内容的根源。垃圾内容的根源在于 AI 是不可靠的。因此，作为一家公司，或者作为做事的人，它不能被用于会让你承担成本的决策。但把成本推给别人其实完全没有问题，这很糟糕。这就是所谓的外部化成本，最终就变成了垃圾内容。如果人们真的去阅读这些内容、去过滤、去在乎质量，它就不是垃圾内容了，但现在世界上充斥着这些，因为那些不在乎的恶意行为者拥有不对称的优势。所以我认为我们至少可以把世界从入站垃圾地狱以及很多其他问题中拯救出来，那会非常酷。

<details><summary>Original English</summary>
Um there's stopping slop obviously a big theme of here but like we definitely believe this. This is my props. I have to we have a stop geni baseball bat for type safe. It is very very awesome. I want to talk about the root of slop. Um the the root of slop is that AI is unreliable. Therefore, you as a company or you as you know like someone who's doing stuff, it can't be used for decisions that costs you stuff. But it's actually totally fine to push the costs into other people, which is horrible. You know, externalized costs and then this is what ends up becoming stop. You know, if people actually read the stuff and filter it and like care about the quality, it becomes not slop, but now the world is full of this because there's an asymmetric advantage for people who are like bad actors and don't give a So, I think that we can save the world from at least inbound hell among many other things and that would be very cool.
</details>

甚至我觉得有一件超级厉害的事，就是搞怪软件（cursed software）。如果你们逛过 Reddit 上的 badUIbattles 版块，就会觉得它太酷了。尽管他们制作出极其糟糕的界面，比如整场游戏里像“您是否想要注销账户”这样的操作变成了某种随机事件。而且我其实认为，仅仅因为我们能做到而去做，这就是软件工程的真谛所在，因为谁知道呢，说不定这些想法里有 1% 真的会导向某种超级棒的东西。我认为真正去孕育哪怕是糟糕的想法，才是一个爱玩的黑客的本色，还有通常意义上的把一切自动化。这就是后续……这是一张垃圾图片，但……抱歉，logo 有点不对劲，但别盯着看。那是有点奇怪。这就是后续许多演讲将要讨论的内容。谢谢大家。而且，如果你是一名软件工程师，

<details><summary>Original English</summary>
Um, and even something I think is super sick is cursed software. Like why if you guys have ever seen the subreddit bad UI battles, it is so cool. Even though they make the horrible interfaces like this whole game of like would you like to delete your account becomes you know a random thing. And and I actually think doing things because we can is what software engineering is about because who knows maybe 1% of these ideas actually lead to something super awesome. And I think like really cultivating even bad ideas is kind of what being like this you know playful hacker is all about and generally just automating everything. This is what the followup this is this is a slop image but uh sorry logo is a little bit wrong but don't stare at that. That's a little weird. Um, this is what a lot of the follow-up talks are going to be about. Thank you. Um, and and if you're a software engineer,
</details>

<!-- chunk 31/50 -->

你们几乎肯定生活在比特的世界里思考。如果你懂一点软件，接触过软件，你就会知道有些事情软件能做，有些事情软件做不到，因为这太显而易见了，对吧？比如你知道有些事情必须自己去做，因为它们与软件不兼容。但是，如果这些限制不再成立呢？也许不是今天，但可能在六个月或一年后。有什么是我们无法自动化的？这就是我想结束整个分享的地方，因为我认为很有可能会迎来这样一个未来：问题不再是我们能不能自动化某件事，而在于这需要多少工作量——就像现在那些能够被自动化的事情一样。那将会非常酷。所以，太棒了。谢谢大家。

<details><summary>Original English</summary>
you almost certainly think in the world of bits. If you know anything about software, uh, and you've interacted with software, you know that there are things software can do and software cannot do because that is just only obvious, right? Like there's some things that you know you need to do because that is not compatible with software. But what if those constraints were no longer true? Maybe not today, but maybe in like six months or a year. What couldn't we automate? And that's kind of where I want to leave this whole thing because I think there is very likely to be a future where it's not a question of whether or not we can automate something. It's going to be a question of like how much work is it, which is how it is right now for the stuff that can be automated. And that would be cool as So, hell yeah. Thank you. Um,
</details>

我已经严重超时了，但还是要感谢早期的笃信者们。要知道，我们当初完全没想到会有这么多人产生共鸣。我们曾以为自己才是疯子，但事实证明，我们其实是世界上意识到人工智能潜力远不止于此的多数派。感谢那些对可靠性保持务实态度的人。大家都知道我讨厌基准测试（benchmarks），很多其他人也都在大声呼吁基准测试有多糟糕。实际上，它们对那些除了基准测试外没有时间顾及其他的人伤害最大。这很可悲。对于那些正在突破软件极限的人，没错，我们希望与你们并肩作战，帮助大家做到这一点。那些梦想家，以及那些不愿被迄今为止发生的一切所束缚的人，我们真心想为你们而战，我们希望这能像第 4 逻辑门（fourth logic gate）一样可靠，这是一个非常高的门槛，我们还有很多工作要做。所以，谢谢大家。谢谢。

<details><summary>Original English</summary>
I'm super overtime, but thank you to the early believers. You know, we had no idea so many people would resonate with this. We thought we were the insane ones, but it turns out like we were actually the majority of the world who realized AI could be so much more. Thank you to like the people who are like really realistic about reliability. Everyone knows I hate benchmarks and a lot of other people are really screaming out like benchmarks suck. They're actually they hurt the people who do not have time for anything other than benchmarks most. It's tragic. And for the people who are pushing the limits of software, like yes. And we want to be there with you helping you all do that. The the dreamers and the people who don't want to be limited by everything that has happened so far. We want to really fight for you and we want this to be as reliable as a fourth logic gate and that is a very high bar and we have like a lot of work to do. So thank you. Thank you.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Hey, heat. Hey, heat.

<details><summary>Original English</summary>
Hey, heat. Hey, heat.
</details>

### Glean 的决策模型实践

大家好。呃，我叫 Chennme，是 Glean 的一名软件工程师。我在 Glean 助手的产品工程团队工作。

<details><summary>Original English</summary>
Hi everyone. Uh my name is Chennme and I am a software engineer at clean. I work on the product engineering side of Glean assistant.
</details>

今天我将带来一场关于 Glean 如何使用 Jev 的演讲。演讲的题目是《超越生成：使用 Jev 实现快速且结构化的人工智能决策》。

<details><summary>Original English</summary>
Today I'm going to give a talk on how lean uses Jeff. The title of the talk is beyond generation fast and structured AI decisions with jean.
</details>

如果你仔细观察，会发现大多数 AI 产品步骤其实都是有界决策（bounded decisions），而不是生成问题。举几个例子：用户查询意图分类、排序器从 n 个选项中挑选建议、检查引用是否有效、路由到正确的模型或专家等等。到目前为止，为了获取这些有界问题的答案，我们一直在支付完整的大语言模型（LLM）成本和延迟。

<details><summary>Original English</summary>
If you look at it, most AI product steps are bounded decisions and not generation problems. So to give a couple of examples, user query intent classification, a ranker picking a suggestion out of n options, checking whether a citation is valid or not, routing to the correct model or expert, so on so forth. Till now we have been paying the full L&M cost and latency to get an answer to all these bounded problems.
</details>

Glean 的 Jev 填补了通用大语言模型与微调分类器之间的空白。分类本身并不是一个新问题，大家从很早以前就一直在尝试解决它。我们有多种解决方法。我们尝试过的一些方案包括：使用通用 LLM、使用开源模型（比如 LIA）、微调该开源模型，或者使用 Jev。

<details><summary>Original English</summary>
Jeff at Glean fills the gap between general LLMs and fine-tuned classifiers. Classification itself isn't a new problem like people have been trying to solve it uh since forever. We can have multiple ways to solve it. Some of the things that we have tried out include using a general purpose LLM, using an open model, something like LIA, fine-tuning that open model or using Jeff.
</details>

现在，所有这些方法和途径各有优缺点。使用通用 LLM，我们会产生大量的成本和延迟；而使用像 Jev 这样的方案，我们不会得到生成的文本输出。

<details><summary>Original English</summary>
Now all these approaches and all these uh different ways have their pros and cons. With a general purpose LLM we incur a lot of cost and latency while with something like Jev we get no generated text output.
</details>

我们看到的 Jev 的另一个优势是，随着决策空间的分类体系（taxonomy）发生变化，我们无需一次又一次地微调这些模型。我们只需要稍微修改一下提示词，然后，瞧，它就能开箱即用。

<details><summary>Original English</summary>
Another advantage that we've been seeing with Jev is that as the taxonomy of the decision space changes, we don't have to fine-tune these models again and again. We can just change our prompt a bit and boom, it works out of the box.
</details>

现在我将向大家介绍我们是如何集成并使用 Jev 来解决 Glean 中的这些分类问题陈述的。我将详细深入探讨其中的一些问题。

<details><summary>Original English</summary>
Now I'll walk you through how we have integrated gen or these classification uh pro how we have used Javit glean to solve these classification problem statements. I'll go into some of these problems in great detail.
</details>

在我们深入探讨这些具体问题之前，我想先谈谈我们是如何评估这些变更的。比如我们拥有庞大的客户群，涵盖数百万用户。因此我们不希望所做的任何改动导致产品发生退化。对于我们正在进行的任何变更，我们都采用多阶段的灰度发布（rollout）流程。呃，这包括几乎对所有可能的事物都准备一套黄金评测集（golden eval set）——比如任何涉及生成式 AI 的地方、任何涉及某种形式的智能的地方，我们在该领域都有黄金评测集。我们会让所有这些变更在内部用例中经过相当长时间的充分验证（soak）。比如 Glean 目前大约有 1500 名员工。我们让所有这些变更在我们的 Glean 实例内部经过两周左右的充分验证。我们会收到积极的反馈。我们与内部用户之间有非常活跃的反馈闭环。我们在此基础上进行迭代，然后才面向客户进行 A/B 测试。

<details><summary>Original English</summary>
Before we go into these uh individual problems, I wanted to touch upon how we evaluate these changes. Like we have a huge customer base having millions of users. So we don't want any of the change that we make to regress our product. We have a multi-phase approach, a rollout approach to any change that we are making. Uh this includes having a golden eval set for almost every possible thing like any place where we have generative AI, any place where we have any form of intelligence involved, we have a golden eval set for that space. We soak all of these changes for a significant amount of time for our internal use case. like we have around 1500 people at Glean right now. We soak all of these changes within our Glean instance for like couple of weeks. We get active feedback. We have a very active feedback loop from our internal users. We work upon that and then we go for an AB testing uh with our customers.
</details>

我们使用决策模型尝试的第一个问题是查询分类。

<details><summary>Original English</summary>
The first problem that we tried out with a decision pro uh decision model was query classification.
</details>

查询分类是指我们想要了解用户查询的性质。这有助于我们了解用户使用 Glean 是为了什么样的查询、执行什么样的工作任务。比方说，如果人们更多地将其用于销售类查询，我们就会更多地关注那方面；如果人们更多地将其用于工程类型的用例，我们就会更多地关注这方面。我们在这里尝试了三种不同的方法，这些是我们测试平台上的数据。呃，我们使用了一个开源的 LIA 模型；接着我们尝试了 Jev；然后我们在自己的计算资源上对 LIA 模型进行了微调。

<details><summary>Original English</summary>
Query classification is when we want to know the nature of user queries. This helps us realize what kind of query what kind of uh jobs are people using clean for what kind of say for example if people are using more for sales like queries we focus more on that. If people are using more for engineering type use cases we focus more on that. We tried out three different approaches over here and this is uh data from our test bed. Uh we used an open source layer model. Then we tried out Jev and then we fine-tuned the liar model on our own compute resources.
</details>

在我们看来，Jev 是最佳的免训练选项。它几乎使基础 LIA 模型的输出质量翻倍，并且能够达到微调后 LIA 模型 90% 的质量表现。

<details><summary>Original English</summary>
Jev is the best no training option in our opinion. It nearly doubles the output quality of a base layer model and is 90 is able to perform at 90% quality in comparison to a fine-tuned model fine-tuned layer.
</details>

使用 Jev，我们不必经历数据收集、数据清洗、承担计算成本（比如训练模型），以及随着分类体系的变化一次又一次地微调模型的极其繁琐的过程。与此同时，我们不必担心托管模型或承担推理成本。

<details><summary>Original English</summary>
With Jeff, we don't have to go through the very tedious process of data collection, data cleaning, incurring the cost for compute, like training the model, fine-tuning the model again and again as the taxonomy changes. And at the same time, we don't have to worry about hosting the model or uh incuring the inference cost.
</details>

我们转向的下一个问题是专家路由。这在目前的行业中是一个非常普遍的问题陈述，比如：当用户查询进来时，我们应该将其路由到哪位专家？比如我们如何确保给用户的响应具有尽可能最好的质量？Glean 目前的解决方式是：Glean 接收用户查询，然后决定由哪位最佳专家来回答该查询。到目前为止，我们一直在使用通用 LLM 来路由到正确的专家。针对 Jev，我们搭建了一个测试平台，搭建了一个包含 n 个专家的测试平台。我们的实验发现，使用 Jev 时精确率显著提高，而且延迟降低了将近 8 倍。

<details><summary>Original English</summary>
The next problem we went to is expert routing. This is a pretty problem common problem statement in the industry right now like hey when the user query comes in what expert do we route it to like how do we ensure that the user uh user the response to the user is of the best possible quality glean receives the way we have been solving this is glean receives the user query and then decides what's the best expert to answer the query till now we have been using a general purpose LLM to route to the correct expert we set up a test bed uh for Jeff we set up a test bed with n experts and Our experiments found a significantly high precision when using jev and that to at an almost 8x reduction in latency.
</details>

为了将 Jev 集成到我们产品的这一特定阶段，我们必须大幅改变我们的实现或基础设施。但是延迟的降低证明了系统引入这种固有复杂性的合理性。我们在 Glean 一直尝试以最简单的方式构建系统。这是我们认为值得引入复杂性的极少数环节之一。

<details><summary>Original English</summary>
We had to change our implementation or our infrastructure significantly to integrate je into this specific stage of our product. But the reduction in latency justifies that inherent complexity in the system. We at glean have been trying to build systems in the most in the simplest possible manners. This is one of the rare pieces where we believe complexity is worth it.
</details>

接下来，我将向大家介绍我之前谈到的排序器问题陈述。

<details><summary>Original English</summary>
Next, I'll walk you through the ranker problem statement that I talked about.
</details>

当我们收到用户查询时，我们也希望为用户生成最佳的跟进建议。这有助于提高我们产品的可发现性，有助于确保用户获得尽可能最好的体验。我们也希望推荐或者说预先推测用户的下一个查询可能会是什么。这同样是整个行业一直在努力解决的一个非常普遍的问题陈述。

<details><summary>Original English</summary>
When we receive a user query, we also want to generate the best follow-up suggestions for the user. Like this helps us in getting discoverability for our product. This helps us in ensuring that the user has the best possible experience. We also want to recommend or say preempt what the next user query might be. Again a pretty pro common problem statement that the entire industry has been trying to solve for.
</details>

在内部，我们将这个系统称为 Q，就是字母 Q。它的工作方式是：我们有大约 10 到 15 个不同的来源，或者说 10 到 15 种不同的方式，有 10 到 15 个彼此独立生成建议的不同来源。这些建议由自然语言 LLM 生成，呈现为规整的自然语言查询。一旦这些建议生成完毕，我们就会进入排序步骤。排序器会接收所有这些建议，接收第一个用户查询，接收 Glean 给出的输出，以及处于该上下文中的所有这些建议。然后由排序器来做决定，比如：你手上有这些建议，你认为哪一个是最好的？我们在这里遇到了一个非常有趣的瓶颈：我们希望响应非常敏捷迅速。我不能、我们不能出现这样一种状态：给用户提供了文本响应，然后还要再等 5 秒钟来生成跟进建议。我们必须反应迅速。这就是为什么我们有时间限制在……

<details><summary>Original English</summary>
Internally we call this system Q like Q as in the literal Q. The way this works we have like 10 or 15 different sources or 10 or 15 different ways uh 10 or 15 different sources that are generating suggestions independently of each other. Once those suggest these suggestions are generated by natural language LLMs and it's like a proper natural language query. Once these suggestions are in we have a ranking step. So the ranker takes in all these suggestions takes in the you uh the first user query takes in the output uh that glean gave and then all these suggestions in that context. The ranker is then asked to decide like hey you have these suggestions what do you think is the best one. A pretty interesting bottleneck that we had over here is we want the response to be snappy. I cannot we cannot have a state where we give the textual response to the user and then wait 5 seconds for generating the follow-up suggestion. We have to be snappy. That's why we have time limits on
</details>

<!-- chunk 32/50 -->

这些建议。所以眼下这个步骤有 1.5 到 2 秒的时间限制。

<details><summary>Original English</summary>
these suggestions. So right now this step had a time limit of 1 1.5 to 2 seconds.
</details>

毫无疑问，Jev 给了我们更好的质量，以及远好于我们使用通用大语言模型时的延迟。但其中有两点尤为突出。第一，我们在 99.2% 的情况下都能在时间限制内给出建议。而使用通用大语言模型时，这个比例几乎只有 90%。因此，这确保了我们能拥有用户参与度以及多得多的用户查询量。第二点是，在 Glean，每当我们使用这些大语言模型时，都会设置护栏。所谓护栏，意思是说大语言模型可能不擅长生成某种回答，或者大语言模型可能会犯某些特定类型的错误。因此，针对我们看到的所有那些可能出现的错误，我们都设有制衡机制。我们对任何时候产生的这些检查都保留一份日志。使用通用大语言模型时，我们在几乎 90% 的用……呃，90% 的情况下能够生成有效的建议。我们仍然会遇到一些情况：大语言模型要么在用不同的语言生成回答，呃，输出没有达到我们通过程序设定的某些其他标准。而使用 Jev，我们发现输出无效的情况为零。现在一个很自然的问题是，嘿，但你用的提示词肯定不一样吧。是的，提示词确实有些不同，但我们尽量在两种情况下最大程度地拟合提示词，以免出现分歧。就像刚才说的，我们在 Glean 希望保持系统尽可能简单。

<details><summary>Original English</summary>
Jeff no doubt gave us a better quality than better quality and far better latency than what we had with a general purpose LLM. But two things stood out over there. First, we were able to give a suggestion within our time bounds in 99.2% cases. With the general purpose LM, this was almost 90%. So this ensures that we have user engagement and far more user queries. Now the second thing is at the glean whenever we use these LLMs we have guardrails. Guardrails in the sense that hey LLM might not be good at generating a response or LLM might be making some specific kind of mistakes. So we have checks and balances for all those possible mistakes that we see. We keep a log of like we keep a log of all these checks that are incurred at any point of time. With a general purpose LLM, we were able to generate a valid suggestion in almost 90% of the use uh 90% of the cases. We still had some places where LLM was either generating a langu generating a response in a different language uh the output did not uh meet certain other criterias that we had uh that we had written programmatically. With Jev, we found zero cases to be there when the output was invalid. Now a natural question is like hey but you would have used a different prompt. Yes the prompt was somewhat different but we tried to mimic the prompt in the two cases to the largest extent possible so that we don't have a divergence. Like again we at glean want to keep the system as simple as possible.
</details>

我们看到的另一个使用决策模型的好处是，我们能够控制阈值，因为在这个排序器问题陈述中，我们获得了每个输出的具体概率。我们不再局限于二元的“是”或“否”回答。我们得到的是，比如这五个选项，以及这五个选项各自的概率。有了这个，我们就能根据具体的部署情况对阈值进行微调。我们接入了自学习系统，该系统会根据客户的部署情况以及特定客户的使用性质，自行对阈值进行微调。这确保了每个客户获得的体验都是基于他们如何使用 Glean 的最佳可能体验，而不是一个一刀切的通用解决方案。

<details><summary>Original English</summary>
Another benefit we see with using a decision model is how we can control the thresholds because in this ranker problem statement we are getting specific probabilities of each output. We are not restricted to a binary yes or no response. We get like hey these were the five options and these are the probabilities of these five options. With this we are able to fine-tune the thresholds based on the deployment. We have put in self-arning systems which based on the user based on the customer deployment and the uh nature of usage that the specific customer has fine-tunes the thresholds by itself. This ensures that the experience in each and every customer out there is the best possible based on how they use glean not a general purpose solution that fits all.
</details>

### 在评估流水线中使用 Jev 作为裁判

好的，这个很有意思。现在从我们如何改善最终用户的生活或体验讲开去，我们还尝试在开发流水线的其他一些部分中使用 Jev。其中之一就是我们如何使用大语言模型作为裁判（LLM-as-a-judge），就像我们大家使用大语言模型作为裁判已经有一段时间了。有一个输入，有一个输出，然后我们用大语言模型来评判输出的质量如何。现在很自然地，每当我们使用大语言模型作为裁判时，我们都会多次重复实验，以考虑到回答中的波动性。

<details><summary>Original English</summary>
Okay, this is an interesting one. Now moving on from how we have been making the lives or the experience of our end users better, we also tried using Jev and some of the some some other parts of our uh development pipeline. One of them was how we use LLM as judges like all of us have been using LLM as judges for quite some time now. There's an input, there's an output and we use an LLM to judge how the quality of the output is. Now naturally whenever we use LLM as a judge we repeat the experiment multiple times because to account for the variability in the response.
</details>

在 Glean，我们将 Jev 用于评估流水线中一个非常特定的部分。Glean 的回答，或者说市面上任何其他 AI 产品的回答，都有引用。人们就是通过这种方式来确信 Glean 的答案是正确的，并且立足于正确的文档。我们对这些引用保持着非常高的标准，并且在评估流水线中有一个特定的环节，用于检查所引用的文档是否真正支持回答中提出的主张。这看起来又是一个非常简单的“是”或“否”的问题，比如该主张是否得到了支持。使用 Jev，毫无疑问我们在延迟和成本上都有极大的改善，正如这里幻灯片上所展示的。我们在这里注意到的有趣之处在于，与 Luna 之类的模型相比，Jev 的结果是多么一致且可复现——在我们拥有的 28 或 30 个用例中，只有一次运行出现了回答上的差异。除此之外的一切都是一致的。但这为我们作为工程师、或者我们在 Glean 的开发者确保了两件事。我们不仅是在提高产品的质量，或者说我们不再仅仅是以线性方式改进 Glean。在开发流水线中达到这种程度的任何改进，都会使我们改进产品的方式产生指数级增长。

<details><summary>Original English</summary>
At Glean we used Jeff for a very specific part of our evaluation pipeline. Glean responses or like any other AI product out there has like citations. This is how people trust that Glean Glean's answer was correct and it it is grounded in the correct document. Now these site we hold these citations to a very high bar and we have a specific part in our evaluation pipeline where we check whether the cited document really supports the claim made in the answer or not. This again seems to be a pretty simple yes or no question like hey whether the claim is uh supported or not. With Jev no doubt we had a far better latency and cost like visible in the slide uh over here. The interesting thing we noticed over here is how consistent and reproducible Jeff results were in comparison to something like say Luna in the 28 or 30 use cases that we had like only one run had like a difference in response. Apart from that everything was consistent but this ensure this this ensures two things for us as engineers or us as developers at glean. We are not only improving the quality of our product or we are not only improving glean in a linear fashion anymore. Any improvement of this extent in the development pipeline leads to an exponential increase in how we can improve the product.
</details>

所以如果我作为一名开发者，能够把交付速度提升大约 5 倍，这就代表着延迟的大幅降低。如果我在成千上万个条目上运行这个实验，这会节省大量时间；而且同样地，我不需要多次运行相同的输入输出对，因为 Jev 的结果相当一致。因此，如果我能将自己的生产力提高 5 倍或 6 倍，我就可以向我们的客户多交付 6 倍的功能，而这发生在 Glean 的大约 500 名或 300 名工程师身上。所以一个好的决策模型所带来的影响不再是线性的，它在我们改进产品的方式上是指数级的。

<details><summary>Original English</summary>
So if I'm if I as a developer I'm able to ship things like 5x faster like this is a significant reduction in latency. like if I run this experiment across thousands and thousands of entries, this is a lot of time and again I don't have to run the same uh input output pair multiple times because the result from J are quite consistent. So if I'm able to increase my own productivity by like 5x or 6x I can ship 6x times the features to our customers and this happens across like 500 engineers or 300 engineers at clean. So the impact of a a good decision model is no longer linear. it is exponential on how we can improve the product.
</details>

### 数据安全与分类器优化

好的。现在从产品和作为裁判的大语言模型继续往下，关于我们如何使用客户数据，有一个非常重要的部分。安全是所有客户对我们的期望。因此举例来说，我们对来自工具的所有输入和输出、来自大语言模型的所有输入和输出都设有制衡机制。

<details><summary>Original English</summary>
Okay. Now, moving on from product and uh LLM as judges, there's a pretty important this this is a pretty important part of how we use our customer data. Like security is something that all our customers expect from us. So, for example, we have checks and balances on all the inputs and outputs coming from a tool. all the inputs and outputs uh from an LLM.
</details>

到目前为止，我们在 Glean 采用的是多阶段方法。这分为两个阶段：第一个阶段偏重于召回，第二个阶段是最终的高负载大语言模型。所有这些调用都是与实际的工具输入输出调用并行进行的。到目前为止，我们过去是在所有客户中通过 T4 GPU 托管一个虚拟分类器。Glean 是单租户解决方案，我们不会跨客户使用或共享资源。每个客户都会获得自己的部署、获得自己的实例并获得所有资源。因此，假设我们市面上有 1000 家客户，我们必须在这 1000 家客户中维护虚拟分类器，这本身就变成了一个相当困难的问题陈述，消耗了 Glean 工程师的大量时间。

<details><summary>Original English</summary>
Till now we at glean have like a multi-phase approach. There is like there are two phases to this. The first one is like recall heavy phase and the second one is the final heavy loaded L&M. All these calls are made in parallel to like the actual tool input output calls. Till now we used to host a virtue classifier using T4 GPUs across all our customers. So glean is a single tenant solution like we don't use or share resources across customers. Every customer gets gets its own deployment gets its own instance and gets all the resources. So assuming we have thousand customers out there we had to maintain like virtue classifiers across all these thousand customers which becomes a pretty difficult problem statement in itself which takes up a lot of time from glean engineers.
</details>

从这里的结果来看，我们过去拥有虚拟分类器的第一阶段的整体召回率——在我们用 Jev 替换之后——从 31.5% 上升到了 90.2%。与此同时，我们看到了成本的大幅降低。这里提到的成本仅仅是资源成本，但我们在这里也节省了工程师和资源的成本。我们不必投入两到三名工程师全职维护跨客户的那些虚拟分类器或那些 T4 GPU。我们获得的改进或节省远超 50%。

<details><summary>Original English</summary>
So looking at the results over here the overall recall of the first phase where we used to have a virtual classifier we replace that with jev went from 31.5% to 90.2%. At the same time we are seeing a significant reduction in cost. Now this cost is only the resource cost mentioned over here but we are also saving cost on the engineer and resources over here. We don't have to invest like two or three engineers who are full-time maintaining those virtual classifiers or those T4 GPUs across customers. The the improvement or the savings that we have are far more than 50%.
</details>

这张幻灯片总结了我到现在为止谈到的所有结果。Jev 在 Glean 能够影响用户的产品体验，能够影响我们在 Glean 作为开发者的工作方式，而且最重要的是，它对我们向客户提供的安全性也有着非常好的积极影响。

<details><summary>Original English</summary>
This slide concludes all the results I have talked about till now. Jev at Glean has been able to influence the product experience of the users has been able to uh impact how we as developers have been working at Glean and most importantly it also has a very good positive impact on the security that we provide to our customers.
</details>

我们一直在使用的一个简单规则是——总的来说，我们在 Glean 一直使用的简单规则是：输出能够提前列出吗？如果不能，那么它就是一个自由形式的生成式文本问题陈述，请回到能够生成自由形式文本的方案；如果能，那就使用 Jev。标签是否稳定且数据量是否很大？如果属于标签稳定的情况（现在这种情况已经很少见了），你也可以微调模型；但如果标签会发生变化（在我看来现在这很普遍），那么就再次使用类似 Jev 的方案。显然，如果你需要动态文本，可以随时尝试更多混合方法，比如将 Jev 与自由形式文本大语言模型结合使用。

<details><summary>Original English</summary>
A simple rule that we have been using is can the out in conclusion a simple rule that we have been using at glean is can the output be listed in advance if no then it's a free form gener generative text problem statement go back to something that can generate free form text if yes then use jev are labels stable and volume high if this is the case where the labels are stable which is rarely the case anymore uh you can also fine-tune a model but if the labels change which in my opinion is quite frequent these is then again use something like jev. Obviously if you need dynamic text we can like feel free to try out more hybrid approaches like jev along with uh free form text lms.
</details>

我的演讲到此结束。谢谢大家的倾听。呃，我已经添加了博客文章的链接，我们在博客文章中非常详细地发布了完全相同的结果。呃，如果大家有更多问题，欢迎在会场外找我交流。谢谢。

<details><summary>Original English</summary>
This ends my presentation. So thank you everyone for listening. Uh I have added uh a blog like a link to the blog post where we have posted the exact same results in great detail. Uh, feel free to catch me on the outside if you have more questions. Thank you.
</details>

Heat。Heat。

<details><summary>Original English</summary>
Heat. Heat.
</details>

祝你好运，伙计。

<details><summary>Original English</summary>
Good luck, bud.
</details>

### UiPath：自动化是否过度思考

大家好。呃，我叫 Si，呃，和我一起登台的是 Kevin。呃，我们今天想聊聊为什么我们认为大家的自动化过度思考了。

<details><summary>Original English</summary>
Hello everyone. Um my name is Si and uh I'm joined on stage by Kevin. Uh we're here to talk about how we believe that uh your automations are overthinking it.
</details>

那么，简单介绍一下我们自己。我们来自一家叫 UiPath 的公司。呃，过去 20 年我们一直专注于自动化领域。呃，我们以前做 RPA，并且我们为全球超过 10,000 家机构提供服务。嗯

<details><summary>Original English</summary>
So um tell us a little bit about ourselves. We are from a company called UiPath. Uh we have been doing automation for the last 20 years. uh we've been doing uh RPA before and uh we service more than 10,000 organizations around the around the world. Um
</details>

<!-- chunk 33/50 -->

我们构建了一个智能体流程编排层，它基本上将智能体、机器人和人汇集在一起相互协作，并构建可运行数天和数周的极具可扩展性的自动化。我们受到了大家现在看到的这张特定幻灯片的启发，今天在我们发言之前大家也看到了这张幻灯片。3个月前 Diego 展示同一张幻灯片时，它在我们心中引起了强烈的共鸣，因为我们也是这样看待自动化的。

<details><summary>Original English</summary>
 and we build uh an agentic process orchestration layer which basically brings agents, robots and people together to interact with each other and uh build extremely scalable uh automations that run for days and weeks. So we were inspired by this particular slide that you're seeing right now and you saw today today before us as well. Uh when uh Diego presented it 3 months ago the same slide uh it resonated really well with us because this is how we see automation as well.
</details>

传统的软件基本上就是 RPA。它就是机器人流程自动化，if else 只是执行某些任务，然后继续运行。其控制流是确定性的。它就这么一直运行下去。后来当大语言模型面世时，我们都竞相去构建即时软件，在其中我们拥有这样一个智能体。我们给它一堆工具。我们给它一个任务并让它完成。然后我们看到了好的结果、坏的结果，随后我们添加了评估来逐步提升结果。最后我们落脚到了智能体流程编排上，它有点像是通过一个逻辑决策层将这种认知决策编织进来。这样你就拥有了确定性的调用和清晰的认知决策点，在这些决策点上你会使用大语言模型来控制控制流，而不是把一切完全交给智能体。因此在这个时候，我们看清了 J 可以应用在何处，当 Diego 谈论 Je 时我们非常兴奋，因为我们看到 Je 契合一个非常细分的领域。

<details><summary>Original English</summary>
So the traditional software was is basically RPA. It's just robotic process automation if else just executes some task and then keeps going. And the control flow is deterministic. It just keeps going. And then when the LLMs came out, uh we all raced to go and build the just in time software where we have this one agent. We give it a bunch of tools. We give it a task and ask it to finish. And then we were seeing good results, bad results, and then we added evaluations to slowly build the results up. And then finally we landed on agentic process orchestration which kind of weaves in this cognitive decision through a logical uh decision layer. So you have deterministic calls and clear cognitive decision points where you would use an LLM to control the control flow rather than leaving it all in the hands of an agent. So at this time we we saw where J would fit in and when uh Diego was talking about Je we were really excited because we saw Je fit in in a very particular niche area.
</details>

在这里我们看到 Je 是一个非常强大的工具，正如 Diego 所说，它是一个我们能够集成到所有自动化中的基础工具。它恰好契合在确定性情况与智能体情况之间。Jev 非常快，你们大多数人应该都试用过了，我们对其运行速度之快、并行处理能力之强以及它的智能程度感到惊讶。因此，我们能够围绕它与大语言模型相比的表现来进行基准测试，它表现相当不错，虽然不是一个完整的大语言模型，但在智能方面也相当不错。所以它介于两者之间，我们可以通过很多方式来使用 je，我想把发言交给 Kevin，带大家看一个我们在 UiPath Maestro Flow 中使用 Jev 的场景。

<details><summary>Original English</summary>
So u here we see that Je is a very powerful tool as Diego was saying it's a foundational tool that we would be able to integrate into all automation. Uh and it fit right in between a deterministic case and an agent case. So, Jev is extremely fast and most of you guys would have tried it and we were surprised by how fast and how parallel we could make it work and uh and how intelligent it was. So, we were able to benchmark it around how good it was compared to an LLM and was pretty good uh not as a full LM but it was pretty good at in terms of intelligence as well. So it falls in between and there are so many ways we could use je and uh I want to hand it off to Kevin to take you uh take you guys through a scenario where uh we use Jev in uh UiPath Maestro Flow.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### UiPath Maestro Flow 欺诈检测演示

>> 谢谢 Chibi。大家好。今天我其实想带大家稍微了解一下 UiPath 正在通过 UiPath Maestro Flow 构建的内容，并稍微探讨一下我们如何在一个画布内协调人、机器人和智能体。我们今天要过一遍的内容，本质上是一个将演示我们如何把所有这些东西编织在一起的流程。我们的处理方式是，我们最终会拥有系统 1 智能体，它们将能够在我们的流程中实现快速的智能判断。想想诸如“这笔交易是否属于欺诈？”之类的事情。此外，我们还将运行系统 2 智能体，在其中我们将进行更具条理、更深入的调查，智能体会去调用工具。我们将看到这类模式开始出现，我们能够在彼此之间进行交接。那么接下来，我将进入一个实际的演示，我们将演示一个账户欺诈场景。

<details><summary>Original English</summary>
>> Thanks Chibi. Um so hi everybody. Uh today I want to actually walk us through a little bit about what UiPath is building with UiPath Maestro Flow and talk through a little bit of how we would go through and coordinate humans, robots, and agents all together inside of one canvas. Uh what we're going to walk through today is essentially um you know essentially a flow that will demonstrate how we kind of weave all these things together. And the way that we're approaching this is that we're going to end up having system one agents which are going to be able to make quick intelligence happen within our process. Think about things like, hey, is this transaction fraud or not? Um, additionally, we'll have u system 2 agents running where we're going to have more of methodical deeper investigation that's going on where agents are going off and calling tools. And we'll see kind of this pattern these patterns start to emerge where we're able to hand off from one to the next. And so with that, I'll I'll jump into an actual demo where we're going to demonstrate a account fraud uh scenario.
</details>

我们的演示从这里开始，实际上是一笔 48,000 美元的交易进来了。这不是我们预料之中的事情。因此，当我在这个银行门户中进行审查时，我将直接把它报告为欺诈交易。现在这最终会将其提交到我们的 UiPath Maestro 流程中，这将基本上充当该端到端工作流去开始处理的触发器。我们所看到的是各种不同节点的集合，它们各自都将从画布左侧向右侧被编排。我们将主要结合使用系统 1 和系统 2 模型来实际处理它，并分析这是否属于欺诈。

<details><summary>Original English</summary>
And so our demo starts here with uh effectively a transaction coming in for $48,000. And this wasn't something that we were expecting. And so uh as I'm reviewing my bank portal here, I'm going to go ahead and report this as a fraudulent transaction. And so now this would end up smitting it off into our UiPath Maestro flow where this would act as essentially the trigger for this endto-end workflow to to go off and start processing. What we're looking at is a collection of various different nodes that are each going to kind of uh be orchestrated from the left side of the canvas over to the right. And we're going to use uh essentially a combination of system one and system two models to actually process this uh and do analysis of this is fraud or not.
</details>

首先实际发生的是我们要去获取账户活动。我们将把这个发送给 Jev，基本上从最近进行的信用卡消费中提取 60 笔交易，并逐一分析它们是否属于欺诈。这是实时发生的，Jev 能够在几分之一秒内处理这些交易并询问“这是否属于欺诈”。现在，我们发现最近出现的交易中有大约 4 笔被它认为是欺诈。与此同时，我们能够启动流程的另一部分，即对整个账户进行更多的语义分析。我们正在查看进来的那一笔被标记的 48,000 美元交易。我们向 Jev 提出了一个问题：“这里的证据是否足以让我们判断这到底是不是欺诈？”正如我们之前听 Diego 谈到的那样，出现这种新型范式和逻辑，我们最终从这里发现进行了一个评分，而我们需要更多信息。我们当时在问一个问题：我们是否有足够的欺诈信息？为此，我们最终要做的就是启动一个系统 2 智能体，它将启动并运行更长时间，调用银行 API 并发现存在一笔向收款人转账的 48,000 美元交易，对方基本上是在其手机上创建了一个新账户，并且该账户是在当天早些时候创建的。这是高度欺诈的指标。我们绕回来，现在向 Jev 询问同一个问题，问它：“我们现在是否有足够的证据了？”Jev 表示同意，并且发现了 100% 的可疑活动，我们实际上会把它交接给另一个评分模型，该模型将我们发现的所有这些交易与系统有效载荷结合起来，然后发现在这个特定用例中确实存在欺诈。在 1 到 5 分的范围内，我们得到了 4.97 分。

<details><summary>Original English</summary>
And so the first thing that actually takes place is we're going to go through and get account activity. We're going to send this off to Jev to basically pull 60 transactions from the most recent uh credit card purchases that were made and analyze each one of those individually whether or not these are fraud. And this is happening in real time where Jev's able to process these transactions and ask that question of hey is this fraud or not within fractions of a second. Now, we found that there's about four transactions that recently appeared that it thinks are fraud. Now, in parallel to that, we're able to kick off another part of our flow, which is doing more of a semantic analysis on the entire account. We're looking at that one transaction that came in for $48,000, which was flagged. And we're asking a question to Jev is, hey, is there enough information here for us to determine whether or not this is actually fraud? And just as we heard Dieago talk about this earlier where you have these new kind of paradigms and logic come up, we ended up uh finding from this that there's uh a scoring that took place and we needed more information. Um we were asking the question, do we have enough information for fraud? And for that what we're going to end up doing is kicking off a system 2 agent that's going to go spin up and run for much larger longer calling a bank API and finding that you know there was a $48,000 transaction from a payee. uh basically creating a new account on his phone and it was earlier that day that that account got created. So high indicator of fraud. We circle back and ask that same question now to Jev and ask hey do we have enough evidence now? Jev agrees and it finds 100% sufficious activity and we would hand that off effectively to another grading model that combines all those transactions that we found with the system payload and then finds that you know there is fraud in this particular use case. um squared of you know one to five we got 4.97.
</details>

现在跳出这个场景，通常从此刻开始会转入由人工来审查。我们会让人去同时审查系统 1 和系统 2 的日志，然后发现存在潜在的欺诈并冻结账户。但实际上，我们在那些正在将 Jev 实施到其工作流中的客户身上看到的是，他们能够替换在后台进行的常规大语言模型调用。在此过程中，我们节省了大约 50 倍——我们将速度提高了大约 50 倍，同时比调用传统大语言模型便宜大约 7.1 倍。

<details><summary>Original English</summary>
Now stepping out of this um you know typically what would happen from this point onwards is that we'd go off to a human to review. We'd have somebody kind of review both the system one and system two logs and then find that there was you know potential fraud and freeze the account. But you know effectively what we're seeing from customers that are going through and implementing Jev inside of their workflows is that they're able to replace the typical LLM calls that are going on behind the scenes. And in in process, we're saving about 50 uh times uh we're we're increasing the speed about 50 times while also being 7.1 uh times cheaper um than calling a traditional LLM.
</details>

现在，我们已经展示了客户如何在我们的技术中使用它，但我们也在反求诸己，试图探讨 UiPath 如何在我们提供的产品和服务中使用它来帮助客户。我们在 Jev 上正在探索多种不同的模式。今天我们要讨论一个重排序问题，以及我们在邮件挖掘中所使用的内容。为了给重排序做个铺垫，我们实际上试图做的是，在我们的检索增强生成中、在我们的智能体中运行并增加一种能力，让我们能够找到更合适的数据块提供给我们的智能体。我们实现这一点的方式基本上是先找到相关文档，然后通常使用大语言模型来做这件事情。但我们也在尝试使用 Jev 来遍历并找出与回答问题最相关的各种不同数据块，然后将这些数据块作为上下文提供给大语言模型。我们现在已经对此进行了几项实验。我想把发言交还给 Chibi，由他来进一步向我们介绍我们所发现的内容。

<details><summary>Original English</summary>
Now, we we've gone through and and kind of shown how customers would use this within our technology, but we're also pointing the finger back inwards where we're trying to ask the question of how can UiPath use this within the products and services that we offer to be able to help customers out. And there's a number of different patterns that we're kind of exploring with Jev. Um, and today we're going to talk about um a re-ranking problem as well as uh what we're using inside of email mining. And so to set the stage for for kind of reranking um effectively what we're trying to do is run and add uh within our retrieval augmented generation within our agents the ability for us to find more appropriate chunks to be able to provide to our agent. And we do that by basically finding relevant documents first and then using um typically an LLM to do this. But we're experimenting with also using Jev to go through and find the various different chunks that make are most relevant to answering the question and then providing those as as context to the LLM. And we've run a couple exper experiments on this now. And I'd like to hand it back off to Chibi who's going to end up telling us a little bit more about what we were able to find.
</details>

>> 是的。这就是事情对我们来说变得真正有趣的地方了。这大概是 Jev 推出的第一周。我们拿到了 Je，我们手头有这些用于重排序的极其强大的基准测试和评估集，我们一直在运行

<details><summary>Original English</summary>
>> Yeah. So this is where things got really interesting for us. This is like the first week of Jev. We had got our hands on Je and we have these extremely strong benchmarks and uh eval sets that we had for reranking that we have been running
</details>

<!-- chunk 34/50 -->

### 锦标赛策略与小模型挖掘

一段时间了，比如当我们从一个模型换到另一个模型时，我们都需要这些评测集。我们意识到，为什么不把这些评测集拿出来，构建一个爬山算法测试框架，然后让 Astra 去做：告诉它这就是我用大语言模型能拿到的分数，这里是 Jev，这里有三个 API，请找出一个能达到那个分数的策略。然后让它运行。它在一次运行中整整跑了一整夜，持续了 14 个小时，探索出了非常多不同的策略——哪些行得通，哪些行不通。接着我们就慢慢看到数字在上升。每隔两个小时，就会出现一个表现略好一点的策略。这让我们太吃惊了，因为之前我们以为 Jev 作为一个 API，如果你只是直接调用它，直接发送所有的内容……

<details><summary>Original English</summary>
for some time and we need those for like when we change from one model to another. uh and we realized okay why not take these eval sets and build a hill climbing harness and ask Astra to say okay this is my score I can get with NLLM here is Jeff here are the three APIs find a strategy which can achieve that score and let it run and it ran for the entire night for 14 hours in a session and it came up with so many different strategies where it worked, where it didn't work and then we were slowly seeing the number go up. Every two hours there will be one strategy would perform slightly better. This was so surprising for us because what we thought was Jeb as an API if you just call it like when you just send all of
</details>

是的。所以当我们调用它时，最初只得到了 866 分，在当时我们尝试并思考如何提高它的时候，这个分数是非常非常低的。然后，当它不断尝试新策略时，分数慢慢达到了 889 分。那个策略被称为“锦标赛”（tournament）。我想向大家展示这个由爬山模型实际构想出的策略，以及我们是如何仅仅通过在不同架构和不同调用方式中应用 Jev，就从中榨取出智能的。现在我想带大家了解一下“锦标赛”策略。

<details><summary>Original English</summary>
Yeah. So when we call it uh we were getting only 866 which was very very low at that point when we were trying it out when we were thinking how do we increase it and then it slowly got got to the number of 889 while it was uh trying out new strategies and that strategy is called tournament and I want to showcase that strategy which it which these hill climbing models actually come up with and how we were able to see the intelligence squeaked out of Jev just by applying JV in a different architecture and different call method. Uh and I want to take you through tournament now.
</details>

“锦标赛”所做的，实际上是对重排（reranking）进行了全新的重塑。它不是去审视每一个分块（chunk）并评估它与我的问题的相关度有多高，而是将这些分块划分成不同的小组（cohorts），通过为每个分块发送成千上万次 Jev 调用，让它们彼此竞争以决出最佳、最相关的分块。它会在这些特定的分组中找出优胜者，然后胜出者晋级到下一轮；接着在这些胜出者中，我们再次从那些分块里找出顶尖优胜者，随后逐步推进、筛选最顶层——精华部分会浮出水面，最终你就能从整个列表中找出最相关的分块。

<details><summary>Original English</summary>
So what tournament did is that it actually reimagined reanking differently. Instead of looking at every chunk and saying that it is how good relevant is it for my question, it created cohorts of different u different groups of these chunks and made them fight between each other to be the best most relevant chunk by sending thousands and thousands of Jews for each and every one of them and it found leaders in those particular cohorts and then the winners would be promoted to the next round and then in from those winners we would again find like top winners from those chunks and then we'll slowly increase and find the top most the cream will rise to the top and you'll find the uh the most relevant chunks on the whole list.
</details>

这套方案效果极其出色。我们在进行测试时惊讶地发现，即便进行了数千次 Jev 调用、使用了数百万上下文，我们在不到一秒的时间内依然能够完成所有这些调用。这对我们来说是一个巨大的发现。我们意识到，Jev 是一个我们可以调配的积木，我们必须去寻找这些能够应用这一积木的新策略；它单独拿出来看可能显得没那么聪明，但借助这些策略和模式，即使利用我们现有的 Jev 模型，我们也能获得更高的智能。这为我们带来了大约 15 倍的速度提升。我们在实际的实时索引上进行了测试，观察了它的表现，大家都对此感到极其惊艳。

<details><summary>Original English</summary>
So this worked extremely well and we were testing it and uh we were surprised to see that even with thousands of Jev calls and thou uh many millions of contexts being used uh we were still under a second we were able to make all of these calls right and uh this was a huge uh revelation for us and we realized that gel is a building block that we can adjust and we are we have to find these new strategies where we would be able to apply this building block and it might look less intelligent on its own but with these strategies and patterns we can get more intelligent with even the current job model that we have right and that's that gave us like 15x speed and we tested it out on uh our our live um indexes and saw how it performed and uh people were extremely surprised by this one
</details>

接下来，我们观察了如何将 Jev 用于数据挖掘。挖掘包含很多阶段，我这里只谈分类阶段。实际情况是，我们有些客户的支持邮箱里有数百万封邮件，他们希望进行分析并深挖这些邮件中发生的情况，以便采取后续行动。我相信你们每个人也都有这样的邮箱。问题在于，如果不通读所有这些邮件，是很难找到合适的分类和归类方式的。

<details><summary>Original English</summary>
and next we saw how uh Jio could be used um uh for mining. So mining is has a lot of stages. I'm going to talk only about the classification stage. And uh what happens is we have customers who have millions of emails in a support uh email box and uh what happens is they want to analyze and they want to dig into what happened in these emails so that they can take some actions. I'm sure every one of you guys have one of those email boxes. uh what happens is that like it's so hard to find the right categories and bucketizations without reading all of these emails.
</details>

所以我们过去的做法是，去针对分类场景进行微调，以搞出一个能够对它们进行分类的模型，这往往需要花费数小时甚至数天的时间。但我们发现——这同样是通过爬山法发现的模式：我们使用大语言模型找出一个初始的候选类别列表，它会给出比如 15 个它认为邮件符合的类别；接着我们要做的，就是用 Jev 将所有数百万封邮件全跑一遍，观察各个分类桶的填充情况。借助这种方式，我们能切实验证出哪些桶填充得不妥、哪些出现了过拟合、哪些桶完全没有被填充，然后再让大语言模型回头重新优化这些桶。

<details><summary>Original English</summary>
So what we used to do is that we would go and create uh fine-tuning to figure out a model that classifies them and it would take hours and maybe day to fine-tune the particular model for the classification story. But what we found was this is again through hill climbing we found this pattern where we use we use an LLM to find an initial candidate list of categories and then it would say that okay these are all the 15 categories uh that I think the emails will fit then what we would do is that we'll use je and run all the million emails through it and see if where the buckets fill up and with that we can actually see which buckets are not filled properly which gets overfitted, which buckets are never filled out, and then we ask the LLM to go back and optimize those buckets again.
</details>

重新排列好这些桶之后，我们会对这数百万封邮件再次进行一轮分类。由于 Jev 的成本极低，我们能够反复进行这个过程，最终你就会得到一个与你所处理的邮箱极度契合的分类列表——因为不同的邮箱之间情况各不相同，类别也是截然不同的。但真正厉害的地方在于，一旦你利用大语言模型完成了所有这些梳理并找出类别的工作，你就不再需要大语言模型了，因为你已经拥有了这些类别，你已经将所有的智能提炼沉淀进了这些类别中。

<details><summary>Original English</summary>
And then once the buckets are rearranged, we'll do another classification of all the all the millions of emails one more time. Because Je is so cheap, we were able to do this multiple times and eventually you'll end up with a category list which is extremely fit towards the mailbox that you are dealing with because it's not the same across different different mailboxes. The categories are completely different. But the powerful thing is once you did all of this work with an LLM going through and finding these categories, you don't need the LM anymore because you have the categories which you where you have distilled down all the intelligence into these categories.
</details>

现在你只需构建一个仅使用这些类别和 Jev 的 Maestro 流程。每当有新邮件进来，它只需要 Jev，直接查看邮件并匹配类别，我们基本上就有一套后续处理清单：只要匹配到这个类别，就会发出通知邮件；这个团队会收到邮件，或者那个团队会收到邮件，处理起来非常简便。在这个环节上，我们基本上彻底去掉了大语言模型。我们在邮件处理上看到了巨大的速度提升——几乎做到了实时：邮件一到达，某人立刻就能收到通知。看到这个成果真是令人惊叹。

<details><summary>Original English</summary>
Now you can just build a maestro flow which basically takes just the categories alone and uses gel. So whenever a new email comes, it only needs gel. It just looks at the uh looks at the email and fits the categories and we basically have a list of uh follow through. So if this matches this category, you are going to get an email. This team is going to get an email or that team is going to get an email so easily and we basically removed LM completely from the picture on this one. So and we saw a humongous speed increase on on just email processing. It was almost like at real time an email comes and suddenly somebody will get notified. So that was an amazing uh um amazing thing to see as well.
</details>

所以在过去的几个月里，我们非常兴奋地去探索 Jev。每天公司各处的 Slack 讨论串都会热闹非凡，有人说“我发现了这种模式”，有人说“我发现了那种模式”。过去的这三个月真是一段令人激动的时光。我想告诉大家，还有更多模式和策略等待去发掘，我们目前仅仅触及了皮毛。我希望我们大家能去尝试，分享彼此找到的策略，并在这里展开合作。

<details><summary>Original English</summary>
So over the few months we were so excited to play around with Jev and every day the Slack threads would light up everywhere in the in the company that I found this pattern, I found that pattern and uh it was such an exciting time uh during these last three months and I wanted to share that there are so much more patterns and strategies to be found. We are only scratching the surface of this and I want us to try out and like share the strategies that we all find and collaborate here.
</details>

>> 如果大家有兴趣试用 UiPath Flow，我们现在提供免费版本。扫描屏幕上的二维码，它会带你进入一个门户，你可以在那里将你的编码智能体接入它，获得完整的访问权限并在上面构建你的首批自动化流程。感谢大家的宝贵时间。

<details><summary>Original English</summary>
>> And if you're interested in trying out UiPath Flow um we have it available for free right now. Scan the QR code on the screen here and we'll be able it'll take you into a portal where you can basically point your coding agent at it and get complete access to build your first automations there. Thank you for your time everyone.
</details>

>> 谢谢。

<details><summary>Original English</summary>
>> Thank you.
</details>

嗨。嗨。

<details><summary>Original English</summary>
Heat. Heat.
</details>

嗨。嗨。

<details><summary>Original English</summary>
Heat. Heat.
</details>

嗨。嗨。

<details><summary>Original English</summary>
Heat. Heat.
</details>

嗨。嗨。

<details><summary>Original English</summary>
Heat. Heat.
</details>

嗨。

<details><summary>Original English</summary>
Heat.
</details>

嗨。嗨。

<details><summary>Original English</summary>
Hey. Hey.
</details>

### 智能体执行与裁判验证的失效

好的。大家下午好。我是 Brian Kennedy，是 ZoomInfo 智能体平台的一名工程师。

<details><summary>Original English</summary>
All right. Good afternoon, everybody. I am Brian Kennedy. I'm an engineer on Zoom Info's Agentic platform.
</details>

现在，我想先给大家看一样我们某个智能体写出的东西。这是来自我们产品的真实输出。该智能体的任务是为客户安排发送一封电子邮件。这是它汇报回来的内容：它声称已经安排好了邮件，已经排入队列，并将在周二发送出去。不过，我们并不会只听信智能体的一面之词。会有第二个模型来检查智能体的工作，我把这个模型称为“裁判”（judge）。裁判读了这份汇报并接受了它。非常好。

<details><summary>Original English</summary>
Now, I want to start with showing you something one of our agents wrote. This is a real output from our product. The agent's job was to schedule an email for a customer. And this is what it reported back. It said it scheduled the email. It queued it up and that it was going to go out on Tuesday. We don't just trust the agent, though. A second model checks the agent's work. I'm going to call this one the judge. The judge read this and it accepted it. Great.
</details>

然而问题来了。实际发生的情况是这样的：这些是工具的执行结果，也就是智能体调用工具时实际运行的记录，我称之为“回执”（receipts）。智能体曾试图在 Salesforce 中创建一条记录，但失败了。返回的错误信息表明记录未被创建，并且告诉智能体不要报告成功，甚至不要捏造记录——我们专门针对这种情况自己编写了这条提示信息。智能体又试了一次，它创建了一个任务（task），也就是一个待办事项（to-do）。

<details><summary>Original English</summary>
Now, here's the problem. And this is what it actually happened there. Uh, these are the tool results. The record of what actually ran when the agent called the tools. I'm going to call these the receipts. The agent tried to create a record in Salesforce and it failed. The error message that came back says the record was not created and it tells the agent not to report a success or even make up a record. We wrote this message ourselves for exactly this situation. The agent tried again. It created a task which is a to-do.
</details>

根本没有任何邮件被排期发送。该智能体甚至连一个能发送邮件的工具都没有。智能体完全是凭空捏造的，而裁判却批准了它。所以这里存在两处失效：智能体伪造了一次发送，而裁判闭着眼睛盖章放行，批准了一项实际上从未核实过的声称。如果你也在构建智能体，你很可能遇到过这种情况，并且你的系统中很可能也有这样一个裁判：它可能是一个代码审查员，或是评估测试中的打分器，或是循环机制中的监督者。任何时候，只要是由一个模型来裁决另一个模型的工作质量，这种情况就可能发生。但在接下来的 10 分钟里，我将向大家展示我们是如何发现这个问题的，以及我们针对它采取了什么措施。首先简要介绍一些背景，我所在的团队……

<details><summary>Original English</summary>
No email was ever scheduled. The agent doesn't even have a tool that can send an email. The agent made it up and the judge approved it. So that's two failures. The agent fabricated a send and the judge rubber stamped it, approved uh a claim that never actually checked. So if you build agents, you probably have run into this and you probably have a judge like this. It might be a code reviewer or a greater of your evals or a supervisor in your loop. Anytime a model decides whether another model's work is good, this can happen. But for the next 10 minutes, I'll show you how we caught this and what we did about it. First, some quick background. My team at
</details>

<!-- chunk 35/50 -->

ZoomInfo 的这个东西叫做 Agent Teams。我们上周刚发布了它。它是一个多智能体编排层，运行在 ZoomInfo 的 GTM studio 中。它负责协调跨越公司各个系统的专业智能体团队，以执行 GTM（走向市场）工作流。例如：寻找目标公司、调研它们、撰写邮件、将其记录到客户的 CRM 中。每个智能体都有自己的角色和指令，以及像 Salesforce、HubSpot、Slack 这样的工具。这些智能体在客户的系统中做出真正的决策并采取实际行动。它们写入记录，也发送消息。

<details><summary>Original English</summary>
Zoom Info um is called Agent Teams. We announced this last week. Uh it's a multi- aent orchestration layer that lives in Zoom Info's GTM studio. It coordinates a team of specialized agents across a company's systems to run GTM workflows. For example, find companies, research them, write an email, log it into their CRM. Each agent has its own roles and instructions like and tools like Salesforce, HubSpot, Slack. These agents make real uh decisions and take real actions in a customer's systems. They write records and they send messages.
</details>

每个团队、每个智能体在完成一个步骤后，都会有第二个模型来检查其工作。那就是裁判（judge）。它有三个选项：进入下一步、重做这一步，或者彻底终止该任务。你可能听说过这种做法，叫作“LLM 作为裁判”（LLM as a judge）。这与代码审查员或评测（eval）是同样的思路。

<details><summary>Original English</summary>
Every team and every agent finishes a step. A second model checks its work. That's the judge. And it has three options. To move on, to redo the step, or to stop the job altogether. You've probably heard this called LLM as a judge. It's the same idea as a code reviewer or an eval.
</details>

对我们来说，难点在于它只是单一模型，却必须为我们通过它运行的每一种智能体打分。我们的客户可以使用任何智能体、任何工具、以任何顺序来构建他们自己的工作流。因此，排列组合几乎是无限的。裁判要处理的任务清单也必须随之增加。裁判能看出这项工作看起来是否完成了，但它看不出这项工作是否正确，因为那取决于对每项任务而言“正确”究竟意味着什么。而我们对所有任务问的都是同一个问题。

<details><summary>Original English</summary>
Now, the hard part for us is that it's one model and it has to grade every kind of agent that we're running through it. Our customers build their own workflows with any agent and any tool in any order. So the permutations are almost infinite. So the list of jobs for the judge has to grow with it. The judge can tell whether the work was looks finished, but what it can't tell is whether the work was right because that depends on what right means for each job. And we're asking it the same question for all of them.
</details>

### 评测裁判模型

所以接下来我们要讲这些内容。首先，我会谈谈我们在检查这个裁判时发现了什么。

<details><summary>Original English</summary>
So here's where we're going. First, I'll talk about what we found when we checked the judge.
</details>

然后是我们选择了什么来替代它，以及你今天可以用你自己的智能体做些什么。

<details><summary>Original English</summary>
Then what we chose instead and what you can to do today with your own agents.
</details>

首先，我们运行了离线评测。我们从生产环境中抽取了 500 个真实的步骤，每个步骤都带有一个裁判当时做出的决定。然后我们使用了一个更大的前沿模型，对其中的每一个重新打分，得出接受还是退回的结果。接着我们人工核对了这些样本中的每一个，并在我们与模型产生分歧的地方核对了评分。最终以我们的人工判断为准。这让我们为全部 500 个步骤都获得了一个参考标签。

<details><summary>Original English</summary>
To start, we ran offline evals. We took 500 real steps from production, each with a decision that the judge had made. Then we took a larger frontier model and regraded every one of those to come back with an accept or a send back. Then we hand checked each of those samples and we checked the grades where we disagreed with the model. We went with our call. This gave us a reference label for all 500 steps.
</details>

结果发现，裁判的正确率只有 65%。基本上就跟抛硬币差不多。它接受了 118 个本该退回的步骤。在它接受的所有内容中，这占了超过四分之一。

<details><summary>Original English</summary>
And it turned out the judge was right 65% of the time. So more or less a coin flip. It accepted 118 steps that it should have sent back. That's more than one in four of everything that it accepted.
</details>

相当糟糕。当我们通读这些案例时，最常见的问题是，类似于开头提到的那封邮件，智能体报告说自己做了某事（比如发送了消息），但实际上根本没有任何工具调用执行过该操作。

<details><summary>Original English</summary>
Pretty bad. And when we read through those, the most common problem was that similar to the email at the start, the agent reported that it did something like send a message and no tool call had ever done that.
</details>

为了弄明白裁判为什么会接受它，我们回到那封邮件，看看给裁判输入了什么。左边是智能体自己的总结。把它想象成一个故事。它很自信，写得很好。上面写着邮件已排期发送。而在右边，你有凭证（receipts）。这是实际的工具返回结果。里面有报错，提示创建消息失败，告诉智能体不要伪造记录。裁判同时拿到了这两份内容，但它相信了那个故事。表面上看这项工作没问题，于是它就接受了。

<details><summary>Original English</summary>
So to see why the judge had accepted it, let's go back to the email and look at what the judge was given. On the left, you have what the agent's own summary. Think of it as like a story. It's confident. It's well written. It says the email was scheduled. Now on the right you have the receipts. This is the actual tool results. There are errors failed to create messages uh telling the agent not to make up the record. Now the judge had both of these and it went with the story. The work looked fine on the surface so it accepted it.
</details>

这不仅发生在我们裁判身上。你可以想象一个代码审查智能体，它在查看 diff 之前先读了 PR 描述。这是类似的问题。如果描述里写着“我修复了 bug，添加了测试”，智能体在读代码时就会偏向于相信这一点。

<details><summary>Original English</summary>
Now this isn't only our judge. You can think of a code review agent that reads the PR description before it looks at the diff. It's a similar kind of problem. If the description says, "I fixed the bug, added tests," the agent is going to lean on that when it reads the code.
</details>

### 从宏观问题转向明确检查

所以，一开始显而易见的解决办法是去微调裁判并写出更好的 prompt。对我们来说，这将是一笔巨大的工作量。我们的智能体写销售邮件、更新 CRM、做调研，而要评判其中的每一项——嗯，我们必须搞清楚用户到底在要求什么。为每一种工作给裁判设定正确的规则，并保持它们全部最新。这基本上等于为每个用例都定制一个专属裁判。

<details><summary>Original English</summary>
So, the obvious fix at the start was to tune the judge and write a better prompt. For us, that was going to be a significant amount of work. Our agents write sales emails, update CRM, do research, and to judge each of these. Well, we'd have to figure out what it was that the user was asking. Give the judge the right rules for every kind of work and keep it all up to date. That's basically a custom judge for every use case.
</details>

我们的做法是走向了一个不同的方向。我们不再去问一个笼统的大问题：“这好不好？”而是开始去问一份包含简短“是/否”问题的清单。对于每一个步骤，问的都是相同的问题。而且每一个问题都足够小，只要看一眼工具凭证就能回答。

<details><summary>Original English</summary>
What we went with, we went a different direction. We stopped asking one big general question. Is this good? And we started asking a short list of small yes or no questions. They are the same questions for every step. And each one is small enough to answer by looking at the receipts.
</details>

这里的第一种选择基本上是一个永无止境的 prompt 微调项目。而第二种选择只是一小组简单的检查。

<details><summary>Original English</summary>
The first option here is basically a prompt tuning project that never ends. Whereas the second one is a small handful of small checks.
</details>

为了回答这些问题，我们使用了 Jev。今天你们已经听到了很多关于 Jev 的介绍，所以我就跳过那些，简单讲讲。它是一个严密的决策模型，不是生成式模型。呃，对于在家里观看的妈妈们来说，直接问 Claude 就行。

<details><summary>Original English</summary>
Now to answer those questions, we use Jev. You've heard a lot about Jev today, so I'll skip that and keep that short. It's a tight decision model, not a generative model. Uh for mom at home watching, just ask Claude.
</details>

我们会向它发送结构化的事实，也就是关于该步骤的信息，以及一系列定型问题（typed questions）。定型问题就是一个“是/否”问题，或者从固定选项列表中做出选择。它会返回每个答案的概率，并且在一次调用中回答所有问题。

<details><summary>Original English</summary>
and we'll send it structured facts, you know, about the step and a listed a type questions. A typed question is a yes or no question or a choice with from a fixed list of options. It sends back a probability for each answer and it answers all the questions in one call.
</details>

我们给它输入了四样东西：指令、输入、凭证（意味着每一次工具调用及其成功还是失败），以及智能体的报告。然后我们要求做出一个选择，即接受、重做或终止，由该选择做出最终决定。但接着我们还会问七个“是/否”问题。这七个问题告诉我们原因。它们用于在重做和终止之间做出抉择，并且当智能体确实需要重做某个步骤时，它们会被纳入给智能体的反馈中。

<details><summary>Original English</summary>
We gave it four things. the instructions, the uh input, the receipts and meaning every tool call and whether it was successful or it failed and the agents report. Then we asked for one choice which was accept, redo or stop and that choice makes the decision. But then we also ask seven yes or no questions. Those seven questions tell us the why. They decide between a redo and a stop and they go into the feedback that the agent gets when it actually has to redo a step.
</details>

现在回到那封邮件。LLM 裁判接受了它，耗时大约两秒半。Jev 给出了每个选项的概率。对于这一步，它给出接受的概率是 0%，重做是 97%，终止是 3%。而且耗时大约五分之一秒。

<details><summary>Original English</summary>
Now back to the email. The LLM judge accepted it and it took about 2 and a half seconds. Jev gave us a probability for each option. For this step, it accepted 0%. Redo 97% and stop at 3%. And it took about a fifth of a second.
</details>

我们根据接受的概率来做决定。在 30% 或更高时，我们予以接受。在 5% 或更低时，我们选择重做或终止。介于两者之间的任何情况都意味着 Jev 不确定，因此我们会将其转交给 LLM 裁判。我们是通过测试最初拥有的那 500 个标签来选定这些阈值的。

<details><summary>Original English</summary>
We make the decision from the probability of accept. At 30% or higher, we accept that. At 5% or lower, we redo or stop. And anything in between means Jev isn't sure. So, we kick it to an LLM judge. We picked those cuto offs from testing the 500 labels that we had at the beginning.
</details>

### 测试与对比结果

现在，为了测试这是否更有效，我们采取了两种不同的途径。第一项测试使用了离线评测中的那 500 个生产步骤，对其中大约十分之七的步骤足够有把握。在这些步骤中，LLM 裁判接受了 82 个本应退回的步骤。这里的每一个红方块代表其中一个。Jev 成功抓出了其中的 74 个。蓝方块是 Jev 本会退回的步骤。

<details><summary>Original English</summary>
Now, to test whether what whether or not this works better, we took two different routes. The first test used the same 500 production steps from the offline eval was confident enough in about seven out of 10 of them. One of those steps uh the LM judge had accepted 82 that should have been sent back. Each red square here is one of those. Jev successfully caught 74 of those. The blue squares are the ones that Jeb would have sent back.
</details>

第二项测试就是我们所称的影子模式（shadow mode）。两个裁判都会查看每一个步骤，但只有 LLM 裁判的决定算数。因此我们记录了 Jev 本会做出的决定，而不让它影响实际运行。这为我们提供了 37,000 个决定来挖掘洞察。

<details><summary>Original English</summary>
Now the second test is what we call shadow mode. Both judges look at every step but only the LLM judge uh that decision counts. So we saved Jev what would have done and we don't let it affect the actual run. That gave us 37,000 decisions to mine for insights.
</details>

在那段时间里，有 728 个步骤出现了工具明显失败的情况。LLM 抓出了其中的 294 个。Jev 抓出了 623 个。

<details><summary>Original English</summary>
And in that time there were 728 steps where a tool had clearly failed. The LLM caught 294 of them. Jev caught 623.
</details>

而开头提到的那封虚假邮件，也绝非个例。同一个步骤运行了 1,081 次。几乎每一次智能体声称自己已经排期发送了邮件，LLM 裁判只抓出过一次。Jev 抓出了 876 次。

<details><summary>Original English</summary>
And the fake email from the beginning, it wasn't a one-off thing either. The same step ran 1,081 times. And almost every time the agent said it had scheduled an email, the LLM judge only caught it once. Jev caught that 876 times.
</details>

当你有一个裁判时，每一个步骤都在等待。Jev 速度快了 10 倍，成本便宜了 40 倍。在这种规模下，这个优势非常巨大。

<details><summary>Original English</summary>
And when you have a judge, every step waits. Jev was 10 times faster and 40 times cheaper. At this scale, it is massive.
</details>

或者终止。不过接下来我们要添加后置条件检查，这些问题取决于该步骤内调用了哪种工具。这样我们就不必去猜了。我们预先就知道这一步，因为工具会告诉我们。如果一个步骤调用了（比方说）发送工具，我们还会询问消息是否已送达。如果它写入了记录，我们就问该记录是否存在。这些检查会与那七个问题一起，在同一次调用中输入给 Jev。

<details><summary>Original English</summary>
or stop. But next we're adding post condition checks which are questions that depend on which tool called uh was within the step. So we don't have to guess. Uh we know the step up front because the tool tells us. If a step called let's say a send tool, we also ask whether the message was delivered. If it wrote a record, we ask whether the record exists. And those go into Jev with the same seven questions in the same call.
</details>

### 给智能体开发者的建议

那么，今天你可以用你的智能体做些什么呢？

<details><summary>Original English</summary>
Now, what can you do today with your agents?
</details>

第一，挑选一个判定场景。在你系统的某个地方，正有一个 LLM 在决定某件事好还是不好。它可能是在审查代码，也可能是在给评测打分。挑选其中的一个，把它重写为几个简单的“是/否”问题，这些问题可以通过证据来回答。

<details><summary>Original English</summary>
First, pick one judgment. Somewhere in your systems, there is an LLM deciding whether or not something is good. It might be reviewing code, grading an eval. Pick one of those and rewrite it as a few simple yes or no questions that can be answered from the evidence.
</details>

第二，把它构建出来。这是容易的部分。坦白讲，我们用了 Jev，我们的也只有七个问题。然后第三，以影子模式上线它。让它与你现有的系统并排运行，但先别让它做决定。只是把它保存下来。呃，之后你再去分析它。

<details><summary>Original English</summary>
Second is build it. This is the easy part. Honestly, we used Jev and ours was seven questions. Then the third, ship it in shadow mode. run it next to what you already have, but don't let it make the decisions yet. Just save it. Uh, and then you can analyze it later.
</details>

然后阅读那些案例，看看两者在哪些地方不一致。别想得太复杂。从小处着手就行。

<details><summary>Original English</summary>
Then read the cases and see where the two disagree. And don't overthink it. Just start small.
</details>

我们在衡量我们的裁判之前，一直对它深信不疑。去衡量你自己的吧。运行一次复查。在影子模式下运行它，看看它在哪些地方存在分歧。你可能会对自己的发现感到惊讶。谢谢大家。

<details><summary>Original English</summary>
We had trusted our judge until we measured it. Measure yours. Run a second check. Run it in shadow mode and see where it disagrees. You may be surprised with what you find. Thank you.
</details>

Heat。

<details><summary>Original English</summary>
Heat.
</details>

Heat。

<details><summary>Original English</summary>
Heat.
</details>

>> 好的。大家好。

<details><summary>Original English</summary>
All right. Hey everyone.
</details>

我保证我是最后一个在 Jev 的宣传列车上的人了。呃，我是 Scott。我来自——呃，我来自 Workday，接下来我将介绍我们如何利用 Jev 进行实验，呃，以推动 HR 和财务任务中的新创新。呃，非常令人兴奋的内容。

<details><summary>Original English</summary>
I promise I'm the last uh person on the hype train for Jev. Uh I'm Scott. I'm from uh I'm from Workday and I'm going to go through how we're experimenting with Jev uh to drive uh new innovations in HR and finance tasks. Uh exciting stuff.
</details>

<!-- chunk 36/50 -->

在 Workday，有超过 11,000 家不同的组织使用我们的工具。我们处理的很多问题大致可以归为两类：一类是用户必须执行的非常快捷的操作，比如“我想看我的薪资”、“我想请一天假”；另一类则是我必须深入海量数据中逐一筛选，试图弄清楚究竟发生了什么。

<details><summary>Original English</summary>
So, uh, at Workday, we have over 11,000 different organizations that use our tools. And a lot of the problems that we deal with break down into kind of two different categories. So, one is very quick actions they have to take. I want to see my pay. I want to ask for a day off. The other ones are I have to dive into a ton of data, weed through it, try to figure out what's going on.
</details>

和你们很多公司一样，我们也在尝试围绕这些构建智能体工作流。如果只看一个非常简单的智能体循环：我们接收用户请求，尝试决定该做什么，运行工具，判断我们做得好不好，然后一次又一次重复，直到最终得到结果。

<details><summary>Original English</summary>
And like many of your companies as well, we're trying to, you know, put agentic workflows around this. And so if you look at just a a very simple uh agentic loop, you know, we have a user request. We try to decide what to do. We're running tools. We're judging did we do a good job? Uh and then over and over again until we finally get a result.
</details>

这里的一个问题在于，我们在其中每一个步骤都在调用 LLM，而这存在两大问题。其一是智能化过度。如果参考系统一与系统二思维，我们在每一个步骤都在进行大量缓慢、深思熟虑且极其昂贵的思考过程。

<details><summary>Original English</summary>
Uh now one of the problems here is that on each one of those we're doing LLM calls and there's two major problems with that. So one is there's too much intelligence. So if we look at the system one versus system two thinking uh we're doing a lot of slow deliberate very expensive thought processes at each one of those steps.
</details>

另一个问题是它根本就是用错了工具。很多时候 LLM 就像是拿着锤子找钉子。我们希望弄清楚我们实际需要什么，因为很明显 LLM 并不适合。所以我们需要某种速度快、聪明、易于使用、通用且非常非常廉价的方案。

<details><summary>Original English</summary>
Another problem is it's just the wrong tool for the job. So you know LLMs a lot of times are just a hammer uh looking for a nail. And you know we want to figure out like what do we actually need? Uh because clearly LLMs are not doing it. So we want something that is fast uh smart easy to use uh it's generalized and it's very very cheap.
</details>

### Jev 模型的机制与优势

从代码的角度来看，类似 Jev 的模型到底是什么？它本质上就是一个条件判断：“如果发生这个，就应该发生那个。这些情况中，哪一个是我想要探索的？”

<details><summary>Original English</summary>
So when we look at like from a code perspective you know what are we really looking at from a from a jevlike model it's really just a conditional if this happens this should happen. Which one of these cases are the ones that I want to explore?
</details>

大家在之前的很多演讲中也已经见过了。Jev 具备让我们做到这一点的原语：有概率判断，即到底是这个还是那个，概率是多少；有这件具体事物可能归入的不同分类；还有评分机制，基本上就是排序后的概率。

<details><summary>Original English</summary>
And you know you've seen it among many of these presentations already. Uh but Jev has the primitives to allow us to do this. Uh there's the probability is it you know this or that and what's the probability? Uh what are the different categories that this uh particular thing could fall into? And then you have the uh the scoring mechanism which is basically probability and sorted.
</details>

这一点之前也曾被提及。当我初次看到 Jev 模型时，我的第一反应是：“我们已经有分类器了，我做这个已经很久了，它到底有什么不同？”

<details><summary>Original English</summary>
So you know this has been brought up as well. You know, my first thought when I saw, you know, the Jev models was, well, we already have classifiers. I've been doing this for a long time. How is it actually different?
</details>

正如前面许多演讲者所谈到的，使用传统分类器时，我需要弄清楚我的黄金数据集是什么，必须去训练它；新数据出来后，我又必须反反复复迭代。而使用 Jev，开箱即用，直接就能运转。我们接入问题，完成分类，几乎不需要做什么额外操作，它直接泛化到了我们的问题上。

<details><summary>Original English</summary>
And as many of the speakers have talked about already, you know, with classifiers, I need to figure out, you know, what's my golden data set. I have to train it. New data comes out. I have to iterate over and over. With Jev, just out of the box, it just worked. We plugged in our question. We classified it. we didn't really have to do anything. It generalized to our question.
</details>

因此我们开始将其用于大家在一些演示者那里见过的许多用例中。我们把它用于路由，这是最典型的例子；或者作为裁判来判断这一步是否有效；我们也看过了简历，比如“这个人是否符合从事 ML 工作的资质？”

<details><summary>Original English</summary>
Uh and so we started using it for a lot of the use cases that you've seen from some of the presenters already. Uh so we use it for routing. That's kind of the canonical example. Um you know figuring out did this step work you know as a judge. Uh we looked at uh you know resumes you know is this person qualified for ML work?
</details>

我还想举一个过于简化的例子。没有人教过 Jev 鱼是什么。这也是我们实际问过的一个问题：“鱼是宠物吗？”结果是 50/50，有时候可能是宠物，有时候可能不是。如果我遇到这种情况，就必须弄清楚接下来该做什么。也许我可以给它补充更多上下文：“鱼缸里的鱼是宠物吗？”20 毫秒后，我就可以再次提问。很好，完全可行。“我盘子里的鱼是宠物吗？”显然不是。这项能力并非经过专门训练，在数秒之内开箱即用，直接就能运转。

<details><summary>Original English</summary>
Uh, and I want to do kind of an overly simplified example as well. Um, so no one taught Jev like what a fish is. And so this is actually a question we asked like is a fish a pet? Well, 50/50 might be a pet sometimes, might not be. Um, and so, you know, if I ran into this, then I have to figure out um, what do I do next? Maybe I can give it some more context. Oh, is a fishing a bowl a pet? You know, and after 20 milliseconds, I can ask this again. All right, that's great. Oh, is a fish on my plate a pet? Clearly not. Uh, so this is something that wasn't trained out of the box in seconds. It just worked.
</details>

### Workday 演示用例

接下来看一些我们在 Workday 制作的演示。先做一个说明：这些并不是真实数据，我们没有使用各位的任何简历或薪酬数据；它们目前也并未投入生产环境，未来可能会也可能不会上线——这是我们法务要求我声明的。下面进入演示环节。

<details><summary>Original English</summary>
All right, so now on to some of the demos that we're do that um, you know, we've done at workday. So just a caveat on some of these. Um, it's not real data, so we're not using any of your you know, resumes or payroll data. Uh, these are also not in production now and may or may not be in the future. So that's something our legal asked me to say. So let's get into, you know, some of the uh the demos.
</details>

首先是自动补全。自动补全开始预测你想要问什么。它仅仅是在预测问题，并不能帮你获取答案。随着你输入的字数增多，它会猜测：“哦，我想确认这个人是不是想请假。”很好，你猜出了问题，但实际上并没有帮我拿到答案。

<details><summary>Original English</summary>
All right. So starting with autocomplete. So autocomplete starts to predict what you're trying to ask. It's just predicting the question. It's not helping you get to the answer. So as you start to type more, it's going to guess like, oh, I want to figure out if this person wants to take a day off work. Great. You've guessed the question, but you really haven't, you know, helped me get to the answer.
</details>

因此我们想要做的，是从仅仅预测下一个词或下一段代码，转变为切实帮助你完成任务。我们准备的一个演示最能说明这一点：我们从预测你想说什么，转向预测你想做什么。希望视频能够顺利播放。好的，出来了。

<details><summary>Original English</summary>
So what we want to do is move from just predicting the word or the next block of code and actually help you finish the task. And so this is best shown with a a demo that we have where we go from predicting what you want to say to predicting what you want to do. So hopefully the video play. There we go.
</details>

好的，我下周需要请假。当我开始输入这个问题时，Jev 实际上在后台分析：“好的，我目前掌握了哪些更多上下文？我该如何根据正在获取的信息来调整这个 UI？”这不是我们用 LLM 能够做到的事情。在有人提问的过程中，我们是在循环中实时执行这一过程。

<details><summary>Original English</summary>
All right. So I need to take time off of off of uh next week. And as I start to ask this, Jev is actually figuring out under the hood, okay, what what more context do I have? How can I adjust this UI based on the information that I'm that I'm getting? This is not something that we could have done with an LLM. We're getting, you know, we're we're doing this, you know, in a loop while someone's asking.
</details>

关于工资单，你不应该非得去询问一个智能体：“嘿，你能去查一下我发了多少工资吗？”你完全可以直接在搜索框输入“我上个周期的薪水是多少”。页面会弹出一个界面，允许你取消隐藏以查看上个周期的工资，非常简单，直接带你完成操作。

<details><summary>Original English</summary>
Um the pay slip, you know, you shouldn't have to go in and ask an agent, hey, can you go find out how much I was paid? Uh what you can do is just in the search say what was my pay last period pops up an interface allows you to unhide it you know see what your pay was in the last period very simple gets you to the action
</details>

再比如预订会议。我知道我想预订一个会议，时间定在下周五下午两点。我想和我老板开会，确保把我的老板加进来——Logan McNeel。搞定，会议预订成功。

<details><summary>Original English</summary>
book a meeting. So I know that I want to book a meeting and uh I'm going to want to do it for next Friday. Let me do it at 2 PM. Oh, I want to do it with my boss. Make sure that I get my, you know, my boss on this. Uh, Logan McNeel. There we go. Meeting's booked.
</details>

在这个示例中最后演示的一个是找人，当然还有很多其他例子。在这一项中，我可能掌握一些语义信息，比如“找出负责组织这部分业务的人”，或者直接输入“谁是 Ashanti？我想联系她”。卡片弹出来，点击邮件，就可以直接发送了。

<details><summary>Original English</summary>
And then a final one that we have just for this example, but there's many more. Uh, is finding a person. So, in this one, I may have some semantic knowledge like find the person who owns this part of the organization or just like who's Ashanti? I want to contact her. uh pop it up. Click on email. Good to go.
</details>

底层是如何运作的呢？因为 Jev 既快速又便宜，就像输入联想一样，我们能够以相同的节奏开始渲染 UI；我们可以在文字不断输入的当下预测意图，并开始渲染界面。我们能够以大约 100 万次判定约 20 美元的成本来实现这一点。

<details><summary>Original English</summary>
All right. So, what's happening under the hood? So, because Jev is fast and cheap, uh just like a type ahead, we can start to render a UI on this on that same cadence, we can look at as the words are coming, do a prediction of intent and start to render an interface. And you know we could do this at you know about 20 bucks for a million judgments.
</details>

我们的实现方式大致可以分为两部分。首先，Jev 挑选出对应的卡片来确定意图：“好的，有这样一张卡片能帮到你”；接着，负责该业务领域的团队便可以决定通过哪些问题来逐步填满该卡片。所以这算是一个两步流程：第一步是把人迎进前门，调出正确的卡片；第二步是确保填满那张卡片，帮助他们完成所追求的任务。

<details><summary>Original English</summary>
Uh and the way that we're doing it is kind of twofold um or two parts I should say. So first Jev is picking the card of saying what's the intent. All right there's a card that's going to help you out and then the team that's responsible in that domain then can decide what are the questions to progressively fill out that card. And so there's sort of this two-step process. Uh the first step is getting people in the front door, getting the right card up, and then the second one is making sure that you fill in that card to help them accomplish the task that they're after.
</details>

在合并任何卡片之前，我们这里都设有一项评估，以确保它不会与任何其他卡片发生冲突。至少在我们的初期实验中，我们测试了七张卡片或者仅进行闲聊——因为如果确实没有卡片可以解决该问题，它应该允许你继续聊天——在这个测试中，我们能够达到 96% 的准确率。

<details><summary>Original English</summary>
Now, we have an eval on here before we merge any card. We want to make sure that it doesn't collide with any other one. And at least in our initial experiments, you know, we we've done seven cards or a just chat because it should if there's no card to actually solve it, it should allow you to just continue chatting. uh we were able to get you know 96% accuracy on that.
</details>

### 招聘人员用例

好的，现在转向招聘人员。我们来谈谈招聘人员所面临的问题。这并不是一项能够快速完成的任务。招聘人员手头有一大堆数百份简历，必须从中找出最适合完成或填补目标职位空缺的人选。

<details><summary>Original English</summary>
All right. So now on to the recruiter. So let's talk about the recruiter problem. All right. So this is not like a fast uh task. It's something where recruiter has a pile of hundreds of resumes and has to figure out who has the best resume to accomplish the uh or fill the wreck that they're trying to fill.
</details>

我想先回顾一下我们以前会怎么做：我们会生成嵌入，将向量存入向量数据库，接着设置一个检索层，再配上一个重排器，然后根据重排器的结果确定哪些候选人要呈现在招聘人员面前。一个值得一提的有趣现象是，Quinn 重排器与 Jev 的处理流程惊人地相似。如果你以前用过那个，这是一个挺有趣的对照。不过有了 Jev，我们基本上采用……

<details><summary>Original English</summary>
Now I first want to look at like how we would have done this before. uh we would have done you know an embedding put the vectors in a vector DB then had a retrieval layer then have a reranker and then figure out based on the reranker which ones that we want to put in front of uh the recruiter. Uh one interesting call out is the Quinn reranker uh looks surprisingly similar to uh the uh the Jev process as well. Uh and so that that's kind of an interesting correlary if you've used that one before. Uh but with Jev, we basically take
</details>

<!-- chunk 37/50 -->

省去了所有嵌入步骤。我不需要训练任何东西，不需要做嵌入，也不需要把东西存进向量数据库。嗯，我能做的就是在数据库上执行一个函数。也就是把所有简历放入数据库，呃，用自然语言去查询它，遍历其中的每一份简历，然后直接找出哪些符合我的标准。

<details><summary>Original English</summary>
out all the embedding steps. I don't have to train anything up. I don't have to do embedding. I don't have to put things in a vector database. Um what I can do is just do a function on my database. So put all the resumes into a database. Uh use natural language to query it, iterate over every single one of them, and then just figure out which ones match my criteria.
</details>

所以，呃，我来做一个呃，你们知道的，完全相同的实际演示。这里我们有一个 select 语句，这是针对 DuckDB 的，我们有一个函数会调用 Jev 来算出某人符合这个条件的概率是多少。我们会得到一个分数，然后按照这个分数排序。现在我要查大概 20 条，正如我所说，这些都是伪造的数据，我保证里面没有任何人的真实简历。然后在这里我们看到，呃，这些也是非常偏向机器学习的合成数据。所以如果针对在欺诈、信任与安全问题领域工作过的人有非常高的命中率，这并不奇怪。

<details><summary>Original English</summary>
So uh I'll go into an uh you know an actual demo of this exact same one. So here we have a select statement and so this is against a duct db where we have a function that is going to call jev to figure out what's the probability that someone matches this criteria. We're going to get it a score and then we're going to order by that score. Now I'm going to do about 20 and as I said these are all fakes and none of your resumes are in here I promise. And then here we see uh these are very uh ML focused uh synthetic data as well. So it's not a surprise that we would have uh very high hit rates against someone who's worked in fraud, trust, safety problems.
</details>

嗯，但我们来看看——我们换个问题。我们在这上面稍微增加点对抗性。很多这些简历里都有 pipeline 这个词。所以不管它是数据管线还是 AI 管线，呃，“管子”这个词都会出来。所以我们直接问，比如这个人是否有资格做管道工？如果你只是做词法搜索，它可能会匹配到其中的一些。所以我们把它输入 Jev 并询问，在所有这些机器学习简历中——我们把 limit 调低到五条。呃，直接运行它。

<details><summary>Original English</summary>
Um but let's look at let's change this question. Let's uh be a little bit more adversarial on this one. So a lot of these résumés have the word pipeline in them. So whether it's a data pipeline or an AI pipeline, uh pipe's going to come out. So let's just ask like is this person qualified to do plumbing? If you were going to just do a lexical search, it might pick up some of these. So we put it into Jev and asked, you know, of all these ML res resume résumés, let's, you know, trim the limit down to five here. Uh go ahead and run it.
</details>

我们可以看到，在这些上面概率非常非常低。所以这些几乎肯定是我们会剔除掉的。你可以看到速度。我们遍历了 117 条记录，呃，我们用了 2.3 秒的时钟时间，并且在这次查询上几乎没有花什么钱就遍历了一切。呃，所以 Jev 真的在某种程度上为我们改变了局面，因为每一个我们过去觉得要么太昂贵、要么太慢的地方，我们都想到了将 Jev 注入我们管线的新场景。

<details><summary>Original English</summary>
And we can see, you know, that um very very low probability on these. So these are ones that we would almost definitely throw out. And you can see the speed. So we went over 117 records. Uh we had 2.3 seconds of wall time and spend almost nothing on this query to just iterate over everything. Uh so Jev really kind of changed the game for us because every every place where we're thinking either either this is too expensive or it's too slow, we thought of new places to inject Jev into our pipeline.
</details>

总结一下，我刚才介绍的两个领域是：第一，我们在哪里可以非常快速地做出决策、切中意图并让用户继续他们的流程？第二个则是削减一部分真正深入的工作，我们如何为客户把那些过滤出来？我希望这能让大家获得一些启发，带回各自的公司，去设想利用 Jev 以及决策模型能做些什么。我的时间到了。非常感谢。

<details><summary>Original English</summary>
And so just to summarize, you know, the two areas that I went through are one, where can we decide very quickly and get to the intent and get the person on their way? And then the second one is to cut down on some of the, you know, really deep work. How do we filter those out for, you know, our customers? And so I hope this that that this gave you a little bit of insight into the things that you can take back to you know your own companies and how and you know imagine the things that you can do with Jev and decision models as well. And that's my time. Thank you very much.
</details>

大家好，我是 Gish，微软的主任软件工程师。工作之余，我为 AI agent 构建开源工具。其中之一是 MCP pacemaker，一个让 MCP 服务器保持运行的受监管桥接工具。

<details><summary>Original English</summary>
Heat. Heat. Heat. Heat. Hey folks, this is Gish, a principal software engineer at Microsoft. Outside my job, I build open source tools for AI agents. One of them is MCP pacemaker, a supervised bridge that keeps MCP servers running.
</details>

在我们开始之前，先作一个简短声明。本演讲中的观点仅代表我自己，不代表我的雇主。

<details><summary>Original English</summary>
Before we start, a small disclosure. The views in this talk are my own and doesn't represent my employer.
</details>

### 子 agent 属于分布式系统

子 agent 就是分布式系统。在过去一年里，我一直将 agent 和子 agent 应用于实际工程工作中：开发会话、代码审查、突发事件分流……这场演讲讲的是当一个 agent 把工作交给另一个 agent 时会发生什么。

<details><summary>Original English</summary>
So sub agents are a distributed system. Over the past year, I have been using agents and sub agents on real engineering work, dev sessions, code reviews, instant trashing what this talk is about what happens when one agent hands work to another.
</details>

这里展示了一个架构。协调器拆分一个任务，并将各个部分分派给三个不同的子 agent。它们全都同时运行。它们全都读取相同的共享状态：会话、记忆文件、仓库工作树、issue、向量存储。而且它们不只是思考，它们还向真实系统发起工具调用，触及数据库、API、CI 工具、部署管线。

<details><summary>Original English</summary>
So here's an architecture. The orchestrator splits a task and hands the pieces to three different sub aents. They all run at the same time. They all read from the same shared state. Consization, memory files, repo, working trees, issues, vector stores. And they don't just think, they make tool calls to real systems which touch databases, APIs, CI tools, deployment pipelines
</details>

结果返回后，协调器将它们合并为一个单一的答案。协调器、工作节点、共享的可变状态，以及来自并发执行的结果合并——这构成了一个典型的分布式系统。

<details><summary>Original English</summary>
and the results come back and orchestrator merges them into a single answer and orchestrator workers shared mutable state and results merge from concurrent executions. This represents a classic distributed system.
</details>

几十年来我都知道该如何对分布式系统进行逻辑推理，但当前的这套体系并没有自带任何相关的机制。你所拿到的只是一个接收字符串并返回字符串的函数。我们遇到的故障并不新鲜，也不是特定于 AI agent 的。它们是典型的分布式系统故障。

<details><summary>Original English</summary>
I have known how to reason with dispute systems for decades, but none of the setup came with it. What you get is a function that takes a string and returns a string. Failures we hit are not new, are not specific to a agents. They're classic distributed system failures.
</details>

部分失败：一个正常的调用在执行到一半时失败，并返回一个异常错误代码。但在子 agent 的场景下，它返回的文本看起来却像是成功。

<details><summary>Original English</summary>
partial failure. A normal call that fails halfway through and returns an exception error code. In a sub aent case, it returns text that looks like a success.
</details>

脏读：通常我们有隔离级别。在这里，每个工作节点都读取同一个共享上下文，包括其他工作节点仅仅是猜测出来的内容。

<details><summary>Original English</summary>
Dirty reads normally we have isolations versions. Here every worker reads one shade context including things other worker only guessed.
</details>

无限制扇出：一个繁忙的服务会通过队列、429、503 进行反压。在 agent 中，协调器根本看不到这些中的任何一个，它直接在工作节点中开始。

<details><summary>Original English</summary>
Unbounded fan out. A busy service pushes back with the cues 429's 503s. In agents, orchestrator does not see any of this. It just starts in the worker.
</details>

重试：在正常的分布式系统中，我们构建幂等性以使重试可靠。在 agent 中，一个重试的子 agent 会连同副作用一起把整个任务重新跑一遍。

<details><summary>Original English</summary>
Retries. In normal distute systems, we build potency to make retries reliable. in agents a retrate sub agent and the whole task again with side effects included
</details>

针对上述每种情况，我会先指出它原本所对应的概念，然后将它们组合成我正在提议的一致性模型，并逐一梳理每个部分存在的原因。

<details><summary>Original English</summary>
for each of these case I'll name the concept it already is then I'll put them together as a consistency model I'm proposing and walk through why each part is there
</details>

先从故障模型开始，因为其他一切都依赖于它。友好的一种情况是崩溃停机：一个原本正常运行的进程停止并保持停止状态。子 agent 在这个方框里抛出一个错误。这很容易处理。

<details><summary>Original English</summary>
start with the failure model because everything else depends on it a friendly case is a crash stop a process it was running correctly stops and stays is stopped. The sub agent throws an error in this box. It's easy to handle.
</details>

接下来是无回复：调用丢失了，或者严重超时。我们很快会回到这一点。

<details><summary>Original English</summary>
Next, no reply. The call is lost or it's very late. We'll come back to this soon.
</details>

棘手的情况是拜占庭将军论文里的那种情况：一个给出冲突信息的组件。进程给出了回答，但回答是错的。一个执行到一半的子 agent 离这个方框最近。它没有恶意，但从外部看效果是一样的。它没有崩溃，它的回答很流畅。我们深入来看这一点：一个半途而废的子 agent 并不会抛出异常，它返回看起来正常的文本，带有与成功相同的类型签名。

<details><summary>Original English</summary>
The hot case is the one from Baantine general's paper. A component that gives conflicting information. The process answers and the answer is wrong. A half finished sub agent sits closest to the box. It is not malicious but from the outside it looks the same. It does not crash. It answers fluently. Let's jump into this. A sub agent that half finished does not raise. It returns normal looking text with the same type signature as success.
</details>

我在之前的一次演讲中讲过这种情形的一个版本。我们将一个 agent 指向警报队列。这是我当时用过的图示，展示了给出相同答案的三条不同路径。第一条路径，它拉取了遥测数据并与已知基准集进行了比对，它实际完成了工作。第二条路径，它与之前见过的标题进行匹配并给出了回复。第三个警报，它什么都没做，凭空捏造出来的。三者都被分类为良性，且具有相同的置信度，下游没有任何东西能将它们区分开来。协调器可以读取结论，但它无法读取结论背后完成了多少工作。

<details><summary>Original English</summary>
I talked about one version of this in one of my talks. We pointed an agent at an LQ. Here's an illustration I used there with three different paths which gave the same answer. The first one it pulled the telemetry and compared with a known brand set. It actually did the work. The second one it matched against the title. It has seen before and gave the response. The third alert it didn't do anything. It just originated. All three are categorized as benign with the same level of confidence and nothing downstream can dull this apart. The orchestrator can read the conclusion. It cannot read how much work was behind it.
</details>

现在来看调用得不到回复的情况。协调器发送了工作，然后超时触发了。从这里看，三种情况表现得一模一样：子 agent 仍在工作；它崩溃了；回复丢失了。

<details><summary>Original English</summary>
Now the call gets no reply. The orchestrator send work and a timeout fired. From here three volts look the same. The sub agent is still working. It crashed and the reply was lost.
</details>

这是一个本质限制，而不是工具缺陷。1985 年的 FLP 论文表明，在异步系统中只要存在哪怕一个故障进程，共识就可能无法达成。Chandra 和 Toueg 在 1996 年给出的答案是允许出错的故障检测器：它们是怀疑，并非确知。

<details><summary>Original English</summary>
It's a hall limit, not a tooling gap. The FLP paper from 1985 showed that in a synchronous system with even one faulty process, agreement can fail to finish. Chundra and 2x answer in 1996 was failure detectors that can make mistakes. They suspect did not know.
</details>

在我自己的开源项目 MCP pacemaker 监管桥接中，我遇到了这两个方向的问题。一个在首次运行时需要自我下载的服务器触碰了 30 秒的调用超时，看起来像是坏掉了。它只是慢，并没有死。我们通过给 initialize 单独分配超时时间解决了这个问题。

<details><summary>Original English</summary>
I hit both directions in my own open source project MCP pacemaker supervised bridge. A server whose first run downloads itself hit the 30 secondond call time out and look broken. It was slow not dead. We fixed it by giving initialize its own time out.
</details>

现在看反方向：服务器在调用期间崩溃了。随后调用超时，这个超时覆盖了本可以解释崩溃原因的退出代码。我们通过仅在进程存活时记录超时修复了这个问题。所以，超时只是一种怀疑。把它记录为未知，并保留真实原因。

<details><summary>Original English</summary>
Now the other way the server crashed during a call. The call then timed out and the timeout overrode the exit code that explained the crash. We fixed it by recording the time out only when it was alive. So time out is a suspicion. Record it as unknown and keep the real cause.
</details>

现在，把失败当作一等值对待。我们来看看这个图示。子 agent 返回一个状态：它做了什么，没做什么，证据，以及任何副作用。在这里，“部分完成”是一个正常的回答。

<details><summary>Original English</summary>
And now make failure a value. Let's take this illustration. A sub agent returns a status. What it did, what it did not do, the evidence, and any side effects. Partial is a normal answer here.
</details>

现有协议已经为此预留了位置。在 A2A 中，任务可以以 completed、failed、canceled 或 rejected 结束，或者停止并请求输入。在 MCP 中，调用结果可以声明 isError 为 true。但子 agent 依然可以在文本表达其他内容的同时说 completed。而仅读取文本的循环永远看不出区别。

<details><summary>Original English</summary>
The protocols already have a slot for this. In A2A, a task can end as completed, failed, canceled or rejected or stop and ask for input. In MCP, a dual result can say is error true. But a sub agent can still say completed while its text says something else. And a loop that only reads the text never sees a difference.
</details>

另一个维度：检查一项条件并得到否定结果，与根本无法进行检查是不同的事实。我自己关于评估状态的个人网络草案中就谈到了这一点。如果把两者混为一谈，就会改变哪些内容会被重试、谁会被传呼报警，以及后续审计报告会如何记录。

<details><summary>Original English</summary>
Another spirit. Checking a condition and getting no is a different fact from not being able to check at all. My own individual internet draft on evaluation states talks about this. Collapse the two and you change what gets retrieded and who gets ped and what the audit says later.
</details>

接下来是脏读。我们来看我之前演讲中的这个虚构示例。子 agent 在临时空间中向共享上下文写入内容，声称错误率下降了 80%。它并没有对此进行测量，而是推断出来的。现在，

<details><summary>Original English</summary>
Next dirty reads. Let's take this madeup example from one of my talk. The sub agent the scratch it writes into a shade context saying that error rate fell by 80%. It did not measure that it inferred it. Now two
</details>

<!-- chunk 38/50 -->

其他子智能体从同一个共享上下文中读取。

<details><summary>Original English</summary>other sub aents read from the same shade context.</details>

第二个子智能体写了一篇审查说明，并采纳了同一个句子。

<details><summary>Original English</summary>The second sub agent writes a review note and picks the same sentenc.</details>

第三个智能体写了一个操作手册步骤，并将其作为继续执行的理由。

<details><summary>Original English</summary>The third agent writes a runbook step and uses it as a reason to proceed.</details>

编排器将所有这些——所有这三个产物合并，它们全都一致。这是一个未经证实的一句话，被读取了三次。

<details><summary>Original English</summary>The orchestrator merges all the all these three three artifacts agree. It is once unsupported sentence read three different times.</details>

### 一致性模型与共享上下文中的脏读

1995年对 SQL 隔离级别的批判将脏读定义为：你在写入者提交或回滚之前读取了一个值。在共享上下文中，猜测在写入的那一刻就是可读的，没有任何东西将其标记为未经核对。

<details><summary>Original English</summary>The 1995 critique of SQL isolation levels define a dirty read as you read a value before the writer commits or rolls back. In a shared context, a guess is readable the moment it is written and nothing marks it as unchecked.</details>

一个常规的解决办法是询问三个子智能体并获得法定人数（Quorum）。

<details><summary>Original English</summary>A regular fix to is to ask three sub agents and get a quorum.</details>

法定人数之所以有效，是有特定原因的。在1979年的加权投票中，读法定人数加上写法定人数大于总数。

<details><summary>Original English</summary>Corums do work for a specific reason. In weighted voting from 1979, the read corum plus right corum is greater than total.</details>

因此每次读取都会与最新的写入重叠。这种重叠就是保证。

<details><summary>Original English</summary>So every read overlaps the latest right. The overlap is the guarantee.</details>

在子智能体的情况下，读取同一共享上下文的三个子智能体并不能为你提供这种保证。它们不是独立的副本。它们读取的是同一个猜测。它们的共识只是单一来源被计算了三次。我们来选一个一致性模型。

<details><summary>Original English</summary>In sub aent's case, the three sub aents that read the same shared context does not give you that. They are not independent copies. They read the same guess. Their agreement is one source counted three different times. Let's pick a consistency model.</details>

在数据库中，我们有专门的词汇来描述这个。

<details><summary>Original English</summary>In databases, we have vocabulary for this.</details>

线性化（Linearizable）。所有操作似乎都按照实时顺序发生在一个点上。顺序一致性（Sequential）。遵循每个进程自身单一顺序的全局全序。因果一致性（Causal）。存在因果关系的操作在所有地方都以相同顺序呈现。

<details><summary>Original English</summary>Linearizable. Every operation appears to happen at one point in real time order. Sequential. One total order that respects each process one order. Causal operations that are causally related appear in the same order everywhere.</details>

会话保证（Session guarantees）。这是给单个客户端的承诺，比如读你所写（read your writes）和单调读（monotonic reads）。最终一致性（Eventual）。如果没有新的更新，读取最终会返回最新值。

<details><summary>Original English</summary>Session guarantees. There are promises to one client like read your rights and monotonic reads eventual. If no new updates are made, reads eventually return the lost value.</details>

共享上下文不会给你其中的任何一个。根本没有任何明文保证。

<details><summary>Original English</summary>A shared context gives you none of these. There's no stated guarantee at all.</details>

而且你也不需要最高级别的一致性模型。

<details><summary>Original English</summary>And you don't need the top consistency models.</details>

最强的一致性模型在网络分区时无法保持可用。

<details><summary>Original English</summary>The strongest models cannot stay available when the network splits.</details>

因果保证和会话保证则可以，只要每个客户端固定在一个地方——对子智能体而言，那个地方就是编排器。

<details><summary>Original English</summary>Causal end session guarantees can as long as each clients stick to one place for sub agents that place the orchestrator.</details>

### SAFE 移交模型

因此，这里有一个我用于子智能体的一致性模型。我称之为安全移交（SAFE handoffs）。

<details><summary>Original English</summary>So here's a consistency model I use for sub agents. I call it safe handoffs.</details>

S 代表源读取（source reads）。工作者移交的每个事实都带有其来源版本、截至时间与修订版本，决策仅读取新鲜的源事实。

<details><summary>Original English</summary>S stands for source fees. Every fact a worker hands on carries its source version as of time and revision and decisions read only fresh source facts.</details>

A 代表至多一次副作用（at-most-once effects）。每次写入都有唯一标识，并具有针对该确切操作的一次性授权。结果被回读，绝不重放。

<details><summary>Original English</summary>A at most once effects every right has identity and a single use approval for that exact action. An outcome is read back never replayed.</details>

F 代表扇出预算（fan-out budgets）。每个下游都会获得一个门控和有界的等待时间，拒绝会被计为失败。

<details><summary>Original English</summary>F fan out budgets. Each downstream gets a gate and a bounded weight and refusal counts as a fail.</details>

E 代表明确结果（explicit outcomes）。每次移交都以具名状态结束，超时属于未知状态并带有其成本。

<details><summary>Original English</summary>E stands for explicit outcomes. Every handoff ends in a name state and a timeout is unknown with its cost script.</details>

这个一致性模型是我用于自己的子智能体的模型。它不是一个通用模型。它基于我自己的公开工作。其中一部分在我的 MCP Pacemaker 桥接器中，还有一些基于我的其他文档和我自己的互联网草案。

<details><summary>Original English</summary>This consistency model is the one I use for my own sub agents. It's not a universal model. It's based off my own public work. Some of it is in my FCP pacemaker bridge and some are based on my other docs and my own internet draft.</details>

### S：源读取与新鲜度检验

现在让我们看看每个字母背后是什么。

<details><summary>Original English</summary>Now let's see what's behind each letter.</details>

是的，源读取。它是解决一个工作者的猜测变成另一个工作者事实的脏读问题的答案。有帮助的做法是将每个事实视为一条记录，而不是一个句子。

<details><summary>Original English</summary>Yes, source reads it's the answer to that reads where one worker's guess becomes another worker's fact. What helps is to treat every fact as a record not a sentence.</details>

Lamport 1978年的论文定义了一个事件何时先于另一个事件发生。事实的来源就是那条记录：它是从哪里读取的，以及何时读取的。

<details><summary>Original English</summary>Lampot's 1978 paper define when one event happened before another. The facts provenence is that record. What it was read from and when.</details>

我们来看这个虚构的例子。

<details><summary>Original English</summary>Let's take this madeup example.</details>

记录列出了断言及其修订版本、来源及其版本、作用域，以及三个不同的时间：数据何时有效、我们何时读取它，以及我们何时使用它。

<details><summary>Original English</summary>the record names, the claim and its revision, the source and its version, the scope and three different times, when the data was current, when we read it and when we used it.</details>

新鲜度是在使用事实时进行检查的。

<details><summary>Original English</summary>Freshness is checked with the fact is used.</details>

在这个图示中，数据截至 9:05。我们在 9:06 读取了它，并在 9:07 做出了决定。

<details><summary>Original English</summary>In this illustration, the data ends at 9:05. We read it at 9:06 and we decided at 9:07.</details>

在这种情况下，我们选了5分钟的限制。所以在 9:07 做出的数据决策是没有问题的。

<details><summary>Original English</summary>In this case, we picked a 5 minute limit. So the data decision at 9:07, it's fine.</details>

现在到了 9:15，第二个版本进来了，因为我们设定的新鲜度限制是五分钟。这是一条陈旧的记录。

<details><summary>Original English</summary>Now at 9:15, the second edition came in because our freshness limit is five. This is a stale record.</details>

我们拒绝它，并声明下一个站点需要再次读取。

<details><summary>Original English</summary>We reject it and we say that the next station needs another read.</details>

这就是你区分观察与推断的方式。观察有来源和读取时间，而推断则没有。

<details><summary>Original English</summary>This is how you separate an observation from an inference. An observation has a source and a read time. An inference has none.</details>

### A：至多一次副作用与幂等性

至多一次副作用是关于重试的。

<details><summary>Original English</summary>A most effect is about retries.</details>

这是我关于 MCPmaker 桥接器文章中的一个插图。

<details><summary>Original English</summary>This is an illustration from my article about MCPmaker bridge.</details>

编排器委派了一个任务。子智能体调用了一个工具，该工具执行了实际的写入操作。

<details><summary>Original English</summary>The orchestrator delegates a task. The sub agent calls a tool which does a real right.</details>

比如创建一个 PR，但回复丢失了。

<details><summary>Original English</summary>like creating a PR, the reply is lost.</details>

编排器只知道一件事：结果是未知的。

<details><summary>Original English</summary>The orchestrator knows one thing, the outcome is unknown.</details>

所以它重试了整个任务，写入操作再次发生。

<details><summary>Original English</summary>So it retries the whole task, the right happens again.</details>

这是一个经典问题。在1984年的 RPC 论文中提到：如果调用返回，该过程精确运行了一次；如果你收到异常，它运行了一次或根本没运行。

<details><summary>Original English</summary>This is a classic problem. In 1984 RPC paper, it says that if the call returns, the procedure ran precisely once. If you get an exception, it ran once or not at all.</details>

而系统并没有告诉你究竟是哪种情况。

<details><summary>Original English</summary>And you are not told which.</details>

所以你需要选择一种交付语义。

<details><summary>Original English</summary>So you pick a delivery semantic.</details>

至多一次：不重试，并接受它可能会丢失的事实。至少一次：重试，并接受可能存在重复。

<details><summary>Original English</summary>At most once don't retry and accept the fact that it may be lost. At least once. Retry and accept that duplicates are possible.</details>

精确一次：它发生过至少一次，并且我们有办法去重，也许是通过使用幂等键。在 MCP 中，幂等提示仅仅是一个提示，是 true 还是 false。如果你需要它，你就得自己构建。这里是我桥接器中关于如何处理它的小设计。

<details><summary>Original English</summary>Exactly once. It happened at least once. And there's a way we can dduplicate maybe by using an item potency key. In MCP item potent hint is only a hint and da or false. If you need it, you build it. Here's a small design from my bridge on how I handle it.</details>

当客户端在重启后重新连回时，桥接器会针对全新的服务器重放该客户端的初始化记录。这是安全的。这只是握手，不会恢复工具状态。

<details><summary>Original English</summary>When a client comes back after a restart, the bridge replace the client's record initialize against a fresh server. That's safe. It's just a handshake and it does not restore tool state.</details>

它绝不重放的是处于不确定状态的工具调用。当共享服务器被回收时，桥接器会清空它，并将在截止时间前仍未得到答复的调用标记为可能已执行失败。

<details><summary>Original English</summary>What it never replace is an uncertain tool call. When a shared server is recycled, the bridge drains it and calls till unanswered at the deadline fail as potentially excluded.</details>

这种状态是诚实的。它告诉调用者去进行核查。

<details><summary>Original English</summary>That status is honest. It tells the caller to go and check.</details>

有帮助的做法是为每个副作用赋予一个唯一标识。授权绑定到那个确切的操作上，它只被使用一次。

<details><summary>Original English</summary>What helped is giving every side effect an identity. Approval binds to that exact action. It's only used once.</details>

调用之后，通过该标识进行回读。

<details><summary>Original English</summary>After the call, read back by that identity.</details>

已提交不等于已确认。已确认意味着你观察到了该效果。

<details><summary>Original English</summary>Submitted is not confirmed. Confirmed means you observe the effect.</details>

A 的最后一部分体现在工作暂停和恢复时。租约就是带有超时的锁。

<details><summary>Original English</summary>The last part of a it shows up when work passes and resumes. A lease is a lock with a timeout.</details>

Martin Kleppmann 关于分布式锁的博文展示了这个问题。

<details><summary>Original English</summary>Martin Clipman's post about distributed locking shows this problem.</details>

客户端在持有锁时发生了暂停。租约到期。其他人获取了锁，随后第一个客户端唤醒并照样执行了写入。

<details><summary>Original English</summary>A client passes while holding it. The lease expense. Someone else takes out and the first client wakes up and writes anyway.</details>

他提出的修复方案是一个防护令牌（fencing token）。这是一个每次锁被授予时都会递增的数字。

<details><summary>Original English</summary>The fix he proposes a fencing token. A number that goes up every time the lock is granted.</details>

存储层会记住它所见过的最高令牌，并拒绝带有旧令牌的任何写入。

<details><summary>Original English</summary>The storage remembers the highest token it has seen and rejects any right with the old one.</details>

子智能体一直在暂停和恢复。正如我在另一个演讲中所说的：恢复上下文，而不是副作用。所以要像对待防护令牌一样对待授权。

<details><summary>Original English</summary>Sub agents pause and resume all the time. In my other talk, as I put it, restore context, not side effects. So treat an approval like a fencing token.</details>

一个操作，一次使用。在关口进行检验，而不是记录在提示词对话中。

<details><summary>Original English</summary>One action, one use. Checked at the gate, not remembered in the prompt. A conversation.</details>

我的桥接器修复了同一类缺陷。陈旧的退出或延迟的恢复再也不能移除或带回替代会话。

<details><summary>Original English</summary>My bridge fixed the same class of bug. A stale exit or a deleted resume can no longer remove or bring back a replacement session.</details>

### F：扇出预算与冷启动门控

扇出预算针对的是无界扇出问题。这是流量控制，或者说是缺乏流量控制的问题。在给冷启动设置限制之前，我自己在 MCV 桥接器中就遇到了这个问题。

<details><summary>Original English</summary>Fan out budgets is about unbounded fan out. This is flow control or the lack of it. I hit this issue in my own MCV bridge before it had a limit on cold starts.</details>

许多会话同时通过 npx 启动它们的服务。

<details><summary>Original English</summary>Many sessions start their service at the same time through npx.</details>

它们共享同一个包缓存。结果每一个都因为 npm 的锁损坏而失败了。

<details><summary>Original English</summary>They share one package cache. Every one of them failed with npm's lock compromis.</details>

单次请求本身没有任何问题。失败源自并发本身。

<details><summary>Original English</summary>Nothing in any single request was wrong. The failures was the concurrency itself.</details>

当下游确实反推拒绝时，它可能以纯文本形式返回。这是 MCP 规范中工具执行错误的一个例子。

<details><summary>Original English</summary>And when a downstream does push back, it can arrive as a plain text. This is MCP specs one example of a tool execution error.</details>

限制只是一句话。模型读到了这句话。编排器代码可能根本不看，下一个工作者依然照常启动。

<details><summary>Original English</summary>limit as one sentence. The model reads a sentence. The orchestrator code may never look the next worker starts anyway.</details>

因此，我在桥接器中引入了配额预算。

<details><summary>Original English</summary>So I introduce a kota budget in my bridge.</details>

使用包管理器的冷启动默认通过一个门控，一次允许两个。其他所有人都等待，等待时间上限为15秒。超过该时间，启动将在没有门控的情况下直接进行。

<details><summary>Original English</summary>Cole starts that use a package manager go through a gate two at a time by default. Everyone else waits and the weight is born at 15 seconds. Pass that the start goes ahead without a gate.</details>

我记录了原因：损坏的缓存是一种风险，而挂起的客户端请求则是必然发生的事实。这是出于可用性做出的明确选择，并且被记录了下来。

<details><summary>Original English</summary>And I documented why a corrupted cache is a risk while a hung client request is certainity. There is a choice for availability made on purpose and written down.</details>

而且我还对会话设置了上限。

<details><summary>Original English</summary>And I also built a cap on sessions.</details>

达到上限时，新的会话最多等待10秒，然后被拒绝。

<details><summary>Original English</summary>At the cap, a new a new session waits up to 10 seconds and then it's refused.</details>

这种拒绝现在被计入健康检查中的失败。另外，容量必须在同步启动之前预留，而不是在启动之后；否则，排队的启动会超出上限，这就是检查后再操作（check-then-act）的竞态条件。对于子智能体，给编排器每个下游设定一个数量、有界的等待时间，并将拒绝视作一致性违背。

<details><summary>Original English</summary>That refusal now counts as a failure in health. Another book capacity has to be reserved before the synchronous start not after otherwise cued starts or book the cap that is a check then act race for sub agents give the orchestrator a number per downstream a bounded weight and a refusate consent.</details>

### E：明确结果与代码级检验

现在是 E，明确结果。每次移交都以具名状态结束，例如陈旧（stale）或未知（unknown），而不仅仅是文本。最后一部分是谁来判定该状态：将智能体的输出视为不可信输入，就像你对待来自互联网的请求体一样。

<details><summary>Original English</summary>Now e the explicit outcomes every hand of ends in a name state like stale or unknown not just text. The last piece is who decided that state treats the agent output as untrusted input the same way you treat a request body from the internet.</details>

编排器在代码中拥有检验逻辑。结果是否符合模式（Schema）？证据是否存在？它是否足够新鲜？重新计算时数字是否依然成立？如果某项检验失败，该步骤将返回带有原因的拒绝。它不会把文本连同下方附带的警告段落一起传递下去。如果同一个模型能够跳过检验并宣布其通过，那你拥有的只是一个请求，而不是边界。

<details><summary>Original English</summary>The orchestrator owns the checks in code. Does the result match the schema? Is the evidence there? Is it fresh enough? the numbers hold when you recmp compute them. If a check fails, the step returns a refusal with a reason. It does not pass the text along with a warning paragraph underneath. If the same model can skip a check and declare it past, you have a request, not a boundary.</details>

这是另一个演讲中的虚构例子。一个子

<details><summary>Original English</summary>Here's a madeup example from another talk. A sub</details>

<!-- chunk 39/50 -->

Agent 称比率下降了。此前是 1,000 次请求中有 10 次错误，之后是 600 次请求中有 6 次错误。错误数从 10 降到了 6，它就声称我们的比率下降了。但当我们计算比率时，两者都是 1%。我们重新计算后，该声明就被拒绝了。

<details><summary>Original English</summary>
agent says that a rate fell. Before it was 10 errors in,000 requests. after it was six errors with 600 requests. It went from 10 to six and it claimed that our rate fell. But when we computed the rate, it's both 1%. We recomputed it and then the claim is refused.
</details>

有依据的回答是没问题的。审慎地移交给人工也是没问题的。自信的猜测则不行。

<details><summary>Original English</summary>
A supported answer is fine. A deliberate handoff to a person is fine. A confident guess it's not.
</details>

### 一致性模型的边界与权衡

接下来谈谈局限性，因为一致性模型只有在你知道我们应该从何处着手时才有用。

<details><summary>Original English</summary>
So limitations because a consistency model is only useful when you know where we should start.
</details>

以下是安全模型（safe model）所不做的事情：它不会让事实成真；源事实是可检验的，但并不等同于正确。它不会为你提供精确一次（exactly-once）的交付；丢失的回复在你重新读取它之前一直处于未知状态。它不会进行任何回滚；撤销部分任务是你需要去设计的一项补偿步骤，就像 1987 年关于 Saga 的那篇论文一样。最后，跨 worker 之间不存在全局顺序，只对事实存在因果顺序。

<details><summary>Original English</summary>
So here's what safe model does not do. It does not make facts true. A source fact is checkable, not correct. It does not give you exactly once delivery. A lost reply stays unknown until you read it back. It does not roll anything back. Undoing a partial task is a compensation step you design. like the Saga's paper from 1987. And finally, there's no global order across workers, only causal order for a fact.
</details>

并且这是有代价的。CAP 定理指出，当网络分区发生时，你需要在可用性与一致性之间进行权衡。我的 bridge 特意在冷启动时选择了可用性。对于写操作，safe 选择了强一致性而非可用性。它宁可拒绝也不去猜测。PACELC 进一步补充道，即使没有发生故障，你也需要在延迟与一致性之间权衡。每一次新鲜度检查都是又一次读取，而每一次拒绝都需要有顺序。

<details><summary>Original English</summary>
And it has a price. CAP theorem says that when the network splits, you trade off availability against consistency. My bridge chose availability for cold starts on purpose. For rights, safe picks consistency over availability. It refuses rather than guesses. Packlac adds that even without failures, you trade latency for consistency. Every freshness check is another read and and every refusal needs an order.
</details>

那么它在哪些场景下不适用？如果 sub-agent 仅仅是起草文本，并在任何事情发生之前都先由人工来阅读，那么这其中的大部分都属于额外开销。它还假设存在一个单一的编排器。如果你有多个编排器，这就不适用了。对于那些没有单一依附位置的纯 Agent，需要的是别的东西。这是我用于自己那些接触实际真正生产系统的 Agent 的一致性模型。它并非普适的。

<details><summary>Original English</summary>
So where does not fit? If a sub agent only drafts text that a person reads before anything happens, most of this is a overhead. It also assumes that there's one single orchestrator. If you have more, this does not fit. Pure agents with no single place to stick to need something else. This is the consistency model I use for my own agents that touch actual real production systems. It's not universal.
</details>

总结一下，这里有三点核心收获：把每次向 sub-agent 的交接都视为一次网络调用；它可能会半途失败，可能会很慢，也可能会返回两次。返回状态，而不仅仅是文本；如果结果无法表示部分、陈旧或未知，编排器就会把它读作……从我们的安全一致性模型开始，并在代码中予以执行。保留适用的部分，更改不适用的部分。我们已经知道如何构建分布式系统，我们只是必须意识到自己正在构建的就是一个分布式系统。

<details><summary>Original English</summary>
So wrapping up, here's three key takeaways. Treat every handoff to a sub agent as a network call. It can fail halfway. It can be slow and it can come back twice. Return a status, not just text. If the result cannot say partial, stale or unknown, the orchestrator will read it as start with our safe consistency model and enforce it in code. Keep what fits and change what does not. We already know how to build distribute systems. We just have to notice that we are building one.
</details>

这些是本场演讲背后的一些资料来源。左侧是我自己的工作、我的开源项目、我的文章、互联网草案以及我的演讲。右侧则是各概念背后的规范、标准以及一系列论文。谢谢大家。

<details><summary>Original English</summary>
So these are some of the sources behind this talk. On the left side, it's my own work, my open source projects, my articles, internet drafts and my talks. On the right side, specs and standards and bunch of papers behind each concept. Thank you.
</details>

### Skill 的知识与评估

>> 大家好，我叫 Nikolai Petro，我们将要讨论 skills 以及 agents 对这些 skills 的知识。

<details><summary>Original English</summary>
>> Hello, my name is Nikolai Petro and we will be talking about skills and agents knowledge of those skills.
</details>

我们最初是从简单的提示词开始的，当时我们尝试着让 agents 完成新东西、新工作，一遍又一遍地重复那些提示词。接着我们开始将它们打包成 skills，创建出可重复、可复现、可移植的这类功能或能力，以此教会 agents 来使用它们。其中一些 skills 非常重要，在 GitHub 上获得了数百颗星。

<details><summary>Original English</summary>
We'll start it with the simple prompts where we've been playing with the new stuff, new work being done by the agents, repeating those prompts over and over again. And then we start packing those into the skills, creating repeatable, reproducible, portable type of their functionality or capabilities that we can teach agents to work with. And some of those skills are very important. hundreds of the stars on GitHub.
</details>

Skills 有不同的类型。有些会教给模型新的东西，为模型带来新的知识或能力。但也有一些仅仅属于引导或流程性质的 skills，其中我们并没有引入任何额外的信息，而只是获得我们希望 agents 执行的操作的可重复流程。两者都很有用。在本次会议中，我们将讨论新知识类型的 skills，并看看我们能从模型对这些 skills 的理解中获得什么。

<details><summary>Original English</summary>
There are different types of their skills. Some teach models something new bringing new knowledge or capabilities to the model. But there are also types of their just steering or process skills where we do not bring any additional information but just getting repeatable flow of the actions that we want agents to perform. both are useful. In this session, we will be talking about new knowledge type of the skills and we'll see what we can get from the models understanding of those skills.
</details>

所以，我们将最初的几个 skills 打包好并开始使用它们，基本上是从“它起不起作用”这种直觉感受开始的。但要检查 skills 是否有效以及这些 skills 会带来什么影响，还有一种更技术化、更确定性的方式，那就是 evals。Evals 可以定义成不同的格式，但从本质上讲，这就是你希望你的 agent 能够解决的任务定义。

<details><summary>Original English</summary>
So, we get our first skills packed, start using them. Um, basically starting with the the feel of does it work or not. But there is also the more technical way and more deterministic way for the checking if skills are working or not and what's the impacts of those skills are evolves. There are different formats where evolves can be defined. But at the sense this is task definition that you want your agent to be able to solve.
</details>

你把它部署好，最好是更加确定性的方式，以便我们能够验证它，并且我们可以检查两个分支：一个是未加载 skill 的分支，第二个是我们加载了 skill 并向上下文提供该额外信息的分支；然后我们对比运行情况。这里有多个考量因素：其一是解决了多少个 evals。在当前案例中，未加载 skill 时我们五道题解决了三道，加载 skill 时我们解决了全部五道，这意味着我们多完成了两项任务。此外还会对 token 使用量、完成这些任务所花费的时间以及其他因素产生影响。但归根结底，我们是在对它们进行比较，看看哪些合理、哪些不合理。这是评估 skills 的主要方式之一，以此说明它们不仅仅是不错的想法，更是切实为 agents 发挥作用的指令和上下文。

<details><summary>Original English</summary>
You put it in the place ideally more deterministic so we can uh validate it and we can check two arms one there no skill loaded and there second one where we're loading the skill and providing this additional information to the context and we compare how the runs there are multiple things one is how many evolves been solved in this case with no skill we're solving three out of five with skill we're solving all five meaning that we get two more tasks. There also would be implications on the tokens usage or time that it took those tasks to be completed and other factors. But at the end we are comparing those and seeing what makes sense, what not. And this is one of the mains for evaluating the skills and uh saying that they not just nice ideas but actually working pieces of instructions and context for the agents.
</details>

但接下来呢？我们到了拥有可用 skill 的阶段。它解决了一些 evals。但我们知道应该有更好的方法。模型在不断演进。在某些情况下，我们可能希望让 skill 更加高效，也就是说消耗更少的 token。那么那里有哪些选择呢？一种是逐行修改，尝试暴力穷举所有不同的组合。另一种则是思考什么才是合理的做法，例如利用用户对 skills 的反馈，来看看这些 skills 在哪些方面表现良好，在哪些方面不行。而面对新模型，仅仅是运行 skill 并观察其效果，这其中有哪些选择？以及这些修改应该有多大范围——仅仅是几行、几个句子，还是整套思路？

<details><summary>Original English</summary>
But what next? We get to the stage where we have their working skill. It solves some evolves. But we know that there should be a better way. We have models evolving. We have u some might be cases where we want to get skill more efficient meaning consuming less tokens. So what's their the options there? One is just change line by line and try brute force all the different combinations. Another would be to think through what makes sense. So maybe use something as the user feedback on the skills to see where the skills perform well. Uh there it's not. And with new models just running skill and seeing how it works, what's the options there? and how large those modifications should be just lines, sentences, ideas.
</details>

### 基于 FActScore 条目的评估矩阵

因此我们发现有用的做法是，与其依赖运气，不如借鉴 FActScore 中条目（items）的概念，在这里建立起一个更加确定性的流程。我们可以把 skill 和指令拆解成这些条目，并针对每个条目配备一组我们预期的问答对。这些既可以是通用理念（比如此处的命题），也可以是契约（我们在其中对其操作提出更明确的预期）。总的来说，我们每个 skill 会获得一定预定数量的条目，比如说每个 skill 会有 25 或 30 个条目分支。

<details><summary>Original English</summary>
So what we found to be useful is instead of relying on their luck, we can put more deterministic process here using idea of their items from their fact score. uh we can split their skill and instructions into those items and for each of those had the pair of question and answer that we expect. This could be either general ideas like proposition in this case or contracts there we put more definitive expectation on their action and in general we will be getting their some predefined amount of the items per skill and we will have let's say 25 or 30 items arms per skill.
</details>

随后针对每个条目，我们同样会运行两个分支：一个未加载 skill，一个加载了 skill。我们将配备一个裁判或裁判小组来评估模型的回答。我们将这些问题提给我们感兴趣的模型。我们用裁判来评估这些问题，理想情况下采用不同家族的模型或裁判小组，这也能确保问题不会泄露答案。根据具体情况，我们可以在没有工具或额外信息的情况下进行对比，以检查模型的内在理解；或者为其提供诸如网络访问等工具，这样会更具实用性。

<details><summary>Original English</summary>
Then for each of the items, we will again run two arms, one without skill and one with skill. And we will have judge or panel of judges that will be evaluating model answers. So we asking those questions to the model that we're interested in. We evalating those questions with the judge ideally different family of the models or panel of judges also ensures that the question do not leak answers. We depending on the case can compare with no tools or additional um information to check their internal model understanding or provided with their some tools like web access. So uh it would be more practical
</details>

我们基本上可以得到一个简单的四种结果矩阵：在其中我们检查模型知道还是不知道某件事，以及这如何映射到 skill 对此产生的影响上。最简单的情况是模型即使在没有 skill 或者加载了 skill 的情况下都能够回答该特定问题。这意味着 skill 对此没有产生影响，并且这本就已经是模型知识的一部分了。第二种情况是，在没有 skill 的情况下模型实际上能够正确回答，而通过添加 skill，我们观察到了性能下降，模型在陈述或解释特定方面的能力退步了。

<details><summary>Original English</summary>
and we can get the simple four outcomes matrix basically where we are checking that the model uh knows or do not know something and how this maps to their skill impact on this. So the simplest option is where model was able to answer this particular questions even without skill or with skill. This means that skill have no impact on this and this was already part of the model's knowledge. The second one is where without skill actual model was able to answer this correctly and by adding skill we saw degradation in performance and model capability to talk or explain particular aspects.
</details>

理想的情况是，在没有 skill 的情况下模型无法回答某些问题，而随着引入 skill，我们开始看到它能够回答那些新类型的问题和场景，这也正是我们所追求的——教会模型新的东西。但还可能存在第四种情况，即 skills 写得不够理想，或者可能写得不够清晰，导致模型无论在没有 skill 还是加载了 skill 的情况下都无法回答它。尽管这个主题可能对模型是相关且重要的，但它在某种程度上仍然遗漏了其中的一些概念。

<details><summary>Original English</summary>
The ideal case is where without skill model wasn't able to answer something and with skill we start seeing that it can answer those new type of the questions and scenarios and this is what we were aiming for teach model something new but there also can be the fourth option where skills were written not ideally or in some maybe not clean way where model wasn't able to answer it either without skill or with skill. And while this topic might be relevant and important for the model, it still sort of misses some of those concepts.
</details>

最容易修复的，就是那些实际上损害了性能的指令或条目。对于热门的 skills，这些构成了衡量标准。在下方的框中你可以看到，在 Anthropic 的 skills 的将近 400 个条目中只有 1 个这样的案例，其他条目则没有。但对于那些没那么热门的小型 skills，你可能会遇到更多这样的情况。这是我们在自己的一些实验中所观察到的。这恰恰是要去修复的最直接、最简单的事情，以确保你的 skill 不会削弱模型的能力和性能，并且只带入相关的上下文。而我们……

<details><summary>Original English</summary>
The simplest thing to fix are instructions or items that actually hurt performance. And for popular skills, those are criteria. So in the uh box below you see that it's just one case out of the mostly 400 items in entropic skills and others don't have those. But for their smaller skills that are less popular, you probably having more of those. This is what we're seeing with some of our experiments. And this is just straightforward the simplest thing to fix to ensure that your skill do not reduce model capabilities and performance and bring only relevant context there. And we
</details>

<!-- chunk 40/50 -->

也可以对这个进行着色。在当前这种场景下，这是按行来划分的，但实际上细化到内部的原子单元。单行或单句可能会有不同的颜色标注。这只是给你们展示一个可视化示例：在哪些地方会提供有用的细节和指令，以此说明你给模型带来了哪些新内容，以及哪些是模型已经掌握的知识。

<details><summary>Original English</summary>
also can actually color this. In this scenario, this is done by lines but actually going with it atoms. You might have their uh different coloring for a single line or a single sentence. And this just gives your example of their uh visualization where this would be helpful details and instructions in terms what new stuff you bring to the model and what is something that model already knows.
</details>

从成本上来说，我们运行了所有这些问题并向模型提问，但整体依然相对便宜——针对 29 个技能，这套评测花费了 14 美元，使用了 Sonnet 作为裁判调用。

<details><summary>Original English</summary>
Costwise we are running all those questions and asking model but still relatively this is uh cheap for 29 skills 14 bucks of their set and ha calls with their sonet used as a judge
</details>

并且我们也有几种方法来检验某些知识的严格程度。我们有宽松和严格的检验方式，前者考察宽泛的概念，而后者检验精确的细节。你可以将其视为对主题的常识与理解，与对确切键名、参数、精确数值或步骤的理解之间的差异。

<details><summary>Original English</summary>
and there are couple ways how we also can check their strictness of their some knowledge. Um we have uh lang and strict ways of the checking this where first checks the general idea while the second one is checking for exact details and you can think about the difference between general knowledge and understanding of the topic to the understanding of the exact keys parameters and exact values or steps.
</details>

我们在各模型上看到的是差距非常大，尤其是在前沿大模型上，在宏观理解层面的技能理解度能达到近 70%，而到了具体细节则骤降至仅 22%。

<details><summary>Original English</summary>
And what we see across the models is the difference is large especially with the um larger frontier models where we see almost dropping from 70% understanding of their skill in case of the general understanding to just 22% of the specific details.
</details>

这与我们的预期非常吻合。我们看到新模型在概念理解上泛化得非常好，但提供有助于解决这些问题的确切细节和数据依然很有帮助。

<details><summary>Original English</summary>
And this is much our expectations. We see that new models are pretty well generalized to understand concepts but it's still helpful to provide their with exact details and data that will be useful for their solving those problems.
</details>

这里展示了在不同模型间对比那三个包含技能的热门代码仓库的概况。这里一个有趣的观察是，较小的模型通常对技能的理解度较低，而较大的 Sonnet 理解度更好，这也正是我们为什么需要更大模型的原因。但我们同时也看到，总体而言，这些模型已经理解了那些技能的大量细节和上下文。而且大家可以预料到，随着更新的模型以及训练能力的进一步提升，模型所理解的内容会越来越多。

<details><summary>Original English</summary>
Here is outlook of their um comparing those three popular repos with the skills across different models. So one of the interesting observations here is that smaller model have in general lower understanding of the skill with their larger sonet having better understanding which is why we have bigger models. But also we see that overall their models already understand a lot of their details and context of those skills. And you would expect that with the newer models and more advances in their uh better training capabilities we will have more and more uh in terms of the models understanding.
</details>

但我们也发现，技能与技能之间存在显著差异，这并不是坏事。有些技能本身就偏向于方向性引导，不过看到这些技能如何给不同模型和不同模型家族带来新知识，也是一条有用的信息。理想情况下，这应该在更广泛的模型集合上运行。

<details><summary>Original English</summary>
But also we see that this pretty significantly differs skill to skill and it's not bad. Some skills are intended to be directional but it's also useful piece of information to see how those skills bring new knowledge uh to the different model and different families. And uh this should be run ideally in the broader set of the models.
</details>

不过，仅仅掌握这种新颖性信息只是信号之一。它基本上是优化的初始向量。归根结底，我们仍然必须运行评估，并验证我们尝试对技能所做的所有修改是否切实有效。

<details><summary>Original English</summary>
But just having their this novelty piece of information is just one of the signals. It's basically initial vector for optimization. At the end we still have to run evolves and validate that all the changes that we try make with their skill actually works.
</details>

因此，较为简单的场景之一就是：我们可以审视技能，尝试从技能中移除部分或全部已知的知识片段，然后运行评估。

<details><summary>Original English</summary>
So the one of their simpler scenarios would be we can look on their skill and try to remove some or all of the already known pieces of information from the skill and run evalation.
</details>

它可能会得出相同的分数。基本上我们会得到相同的结果，模型依然有能力解决那些问题。那么太棒了，我们就可以缩减技能体积，节省 token，节省上下文空间。

<details><summary>Original English</summary>
It might come up with their same scoring. Basically we will be getting their same results model still capable of solving those problems. Then great we can reduce skill size safe tokens safe context.
</details>

这样我们就拥有了一套指引，而无需强行硬试和猜测我们可以或应该删除什么、添加什么，或者该如何修复性能退化。

<details><summary>Original English</summary>
And instead of there brute forcing and guessing what we can or should remove or add or how to fix their uh degradations, we can have a guidance.
</details>

所有这些测量与实验都是通过这个框架完成的，它是一个用于比较与智能体和上下文相关的一切内容的框架——无论它是技能、AGENTS.md、MCP 工具还是其他内容。新颖性只是其中的一项功能，你能从中获取技能优化和评估的初始向量，但这里也包含评估、上下文影响评估、路由、描述对比、命名比对等一系列与技能相关的事情，在这些方面获取更确定的关联性会很有帮助，从而对技能该做哪些调整做出自觉明确的决策。

<details><summary>Original English</summary>
So all of those measurements experiments been done with the document which is a framework for the comparing everything related to the agents and context where it's is scale agents MD MCP tools whatever and novelty is one of their pieces of the functionality where you can get this initial vector for their skill optimization and evalation but there also uh evolves there Assessment of the context impact, routing, comparing the uh descriptions, naming, bunch of the things that related to the skills where it would be helpful to actually get there more deterministic relations to make conscious decisions in terms of what should be done with the skills.
</details>

非常感谢大家的时间，请大家继续编写出更好的技能吧。

<details><summary>Original English</summary>
So, thank you for your time and please go ahead and write better skills.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

主题演讲将于 5 分钟后开始，请大家务必就座。

<details><summary>Original English</summary>
Keynote programming will begin in 5 minutes. Please be sure to find your seats.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

Heat.

<details><summary>Original English</summary>
Heat.
</details>

嘿，嘿，嘿。

<details><summary>Original English</summary>
Hey, hey, hey.
</details>

随着我们进入闭幕主题演讲环节，我们非常激动能请回一位熟悉的面孔来引导我们走完最后的议程。女士们、先生们，请热烈欢迎我们的主持人回归——Corey Quinn，DuckBill Group 的首席云经济学家。

<details><summary>Original English</summary>
As we head into our closing keynotes, we're excited to bring back a familiar face to guide us through the final sessions. Ladies and gentlemen, please welcome back our MC, Corey Quinn, chief cloud economist at the Duck Bill Group.
</details>

### 闭幕主题演讲

欢迎回来。感谢大家坚守了一整天。我们只剩最后一个环节了，随后按说法大会第二天的议程就将圆满收官。自今天上午到达以来，我们听到了不少话题：大概是有意删除测试框架；可能通过歌声的力量来治愈你的智能体——这谁也说不准；自我演进的代码库——这与我这辈子见过的每一个代码库的发展方向完全背道而驰，不过也行吧；以及更多精彩内容，因为现在一切都不同了。在今晚散场之前，我们将听到关于释放智能的演讲，听到智能体如何构建文化；有一场题为“逃离垃圾山”的演讲——具有讽刺意味的是，这正是我高中时代的外号；当然还有“LLM 的 2026 年”，这一年似乎包罗了数十载的光阴。那么，我们开始吧。在深入探讨这一切之前，我想再花点时间感谢赞助商让这一切成为可能。

<details><summary>Original English</summary>
Welcome back. Uh thank you all for sticking out the full day. Uh we just have one more section to go and then we're calling it a wrap on technically day two of the conference. Uh since we arrived this morning, we've heard about a few things. Um deleting harnesses presumably on purpose. Uh healing your agents maybe through the power of song. We don't know. uh self-improving codebase, which is the exact opposite of the direction of every codebase I've ever seen in my life has ever gone, but okay. And so much more because everything is different now. Uh and before we leave tonight, we're going to hear about setting intelligence free. We're going to hear about how agents build cultures. Uh there's a talk called Escaping from Trash Mountain, which ironically was my nickname back in high school. and of course 2026 in LLMs which is one of those years that seems to encompass decades. So here we are. Uh before we dive into all of that I want to take just another moment to thank our sponsors for making all this possible.
</details>

特约赞助商依然是 Google DeepMind，他们今天早些时候刚刚将——是叫 Gemini Carbon 4 吗——推向了通用可用（GA）阶段。恭喜！请大家鼓掌。

<details><summary>Original English</summary>
Uh presenting sponsor remains Google DeepMind who earlier today shipped uh was it Gemini Carbon 4 to general availability. Congratulations. Please clap.
</details>

同样感谢我们的休息厅赞助商和白金赞助商，没有他们，我们在非会议期间能坐的地方就会少得多。

<details><summary>Original English</summary>
our lounge and our platinum sponsors as well, without whom we would have fair far far fewer places to sit when we're not in the middle of a session.
</details>

同样感谢我们的黄金赞助商，正是他们有效地维持了各个运转环节的顺畅进行。当然，还有我们的白银……白银赞助商。天哪，现在的赞助级别实在太多了。到了一定程度，它简直开始变成梯形 API 架构了。最后，还要感谢所有的支持合作伙伴。再次强调，没有各方人士的大力支持，真的不可能举办这样一场盛会，我们对这一切致以诚挚的感谢。

<details><summary>Original English</summary>
Our gold sponsors as well for effectively making all the various moving parts go. And of course, our silver part, silver sponsors, too. My goodness, there are so many tiers at this point. At some point, it starts to become an API ladder. And finally, all of our supporting partners. Again, it it really is not possible to put on an event like this without a tremendous amount of support from various folks and we thank them sincerely for all of this.
</details>

下面有请 Fabian Hedin，他是 Lovable 的 CTO，将试着为我们讲述释放智能究竟需要什么。这或许是我们在 AI 领域唯一一次听到“免费/自由”（free）这个词。让我们欢迎他。

<details><summary>Original English</summary>
Uh now up we have Fabian Hedin who is the CTO of Lovable trying to tell us what it takes to set intelligence free. Uh which might be the only time in AI we hear the word free. Let's make him feel welcome.
</details>

好的。

<details><summary>Original English</summary>
All right.
</details>

非常感谢大家。看看，我们这边一切就绪了。好的，欢迎各位，很高兴来到这里。我是 Fabian，Lovable 的联合创始人兼 CTO。在过去的三年左右时间里，我们致力于打造一个平台，让任何人都可以创建软件，并对其进行运维与部署。今天的主题是释放智能需要付出什么。对我们而言，这真真切切地让我们回想起了三年前刚起步的时候。不得不说，我与智能体之间存在着一段有些复杂的渊源。我会告诉大家其中的缘由。我们公司差点倒闭，因为早在 2023 年我们就认为：“嘿，这些智能体就是未来，让我们现在就为它们构建系统吧。”我认为，它们代表未来这一点确实被证明是对的，但在 23 年那个当下的时间点上，我们绝对是错判了。那时还是 GPT-4 的年代。在那个时候，要构建这类复杂的智能体系统，其智能水平根本还不达标。但现在已经可以了，现在的智能确实已经发展到了你真正能够围绕它们构建更复杂系统的阶段。因此，我来为大家简要讲讲我们与智能或这些大语言模型合作历程的背景故事。

<details><summary>Original English</summary>
Thank you so much. Um, let's see. We're good to go here. Um, all right. Welcome everyone. Glad to be here. I'm Fabian, co-founder and CTO of of Lovable. And um we spent the last three years or so building a platform to let anyone create software and then operate that and deploy that software. Um and um the the topic of today is what it takes to set intelligence free. Um really um for us this takes us back to when we when we started three years ago. And um I have to say I have a bit of a complicated relationship with with agents. Um and I I'll tell you why. Um we almost failed as a company because we thought um back in 2023 that hey we these agents are the future. So let's build for them now. Um I think the we kind of turned out to be true that they were the future but we were definitely wrong on the the now piece in in 23. So this was back in kind of GPT4 days. Um and um at the at that time the intelligence was simply not there to have more of these kind of complex agentic systems. Um but now it is right now uh now the intelligence is actually at a place where where you can really build out more complicated systems around them. Um, and so I I'll give you kind of a a quick um background story here of of our journey um in in working with intelligence or or these LMS. And so
</details>

在 2023 年，我们构建了产品的第一版，当时称之为 GPT Engineer。当时的 UI 实际上与现在非常相似，都有一个对话框和这个预览窗口。但当时的 AI 还相当简单，我们只有单次提示词和单次回复，每条用户消息仅发起一次大语言模型调用。非常简单，运行得还算顺利。你可以用它来构建单页应用和比较简易的应用。随后我们心想：好吧，这种智能还会继续演化，因此随着它的演化，我们必须做好准备。于是我们琢磨着：让我们着手去构建这个智能体框架吧。于是我们便去动手构建了……

<details><summary>Original English</summary>
um back in 2023, we built the first version of our product. We called it GP Engineer back then. Um and really the UI was very similar to what it is today where you can kind of have a chat and this preview. Um but the AI at that point was quite simple. We just had a prompt and a response, one LM call per user message. Uh, very simple. It it worked fine. Um, but you could kind of build one page apps and and simpler applications with this. Um, and then we thought, okay, this intelligence is going to keep on evolving. So, we have to be ready for uh for it as it evolves. And so, we thought, let's go out and build this agentic framework. And so we we went and we built
</details>

<!-- chunk 41/50 -->

非常精巧，有一个供智能体协作的绝妙框架。我们曾设计了这样一个主智能体来与用户对话，然后该智能体会衍生出其他智能体，比如这里的实现智能体，每个智能体各司其职。这个智能体专门负责应用的第一代构建，接着会有前端智能体和后端智能体，它们彼此相互交谈、来回传递消息。当时我们觉得：“哇，这太棒了。”而且当时也有关于这种模式以及其效果有多好的论文。但最终它完全行不通，我们只是把产品做得更差了。在这件事上我们确实失败了。不过幸运的是，在资金耗尽之前，我们意识到：“嘿，让我们再次回到更简单的系统吧。”

<details><summary>Original English</summary>
this very sophisticated there is a beautiful framework for for agents to work. And um we had kind of this one main agent that would talk to the user and that agent would spawn other agents like an implementation agent here in the example and each agent could have a specialtity. This agent would kind of specialize in the first generation of an app and then you would have like a front-end agent and a backend agent and they would all talk to each other, send messages back and forth. and we thought, "Oh, this is beautiful." And there was papers around this and how well this could work. And in the end, it didn't work at all. We just made the product worse. Um, we um we definitely failed on this one. Um, but luckily before we ran out of money, we figured out like, hey, let's go back to a simpler system again.
</details>

所以在 24 年末，我们回退到了一个简单得多的系统，虽然有点遗憾，但在这个系统里，我们用一些较小的语言模型做知识检索，然后实际上只由一个主语言模型在同一条消息中与用户沟通并编写代码。这套系统运行得非常好。在 UI 界面中对用户的响应非常迅速，而且很可靠，用户完全沉浸其中并与模型反复迭代。所以，我们先把那部分放一边。不过现在时机又成熟了。我们回来了，我们彻底回来了。这一次智能体切实可行了。我们正在生产环境中运行它们，在我接下来要讲的这些系统上，每分钟处理的 token 数量超过十亿。

<details><summary>Original English</summary>
So uh in late 24 we went back to a much simpler um system where it was a bit of a shame where we had like some some smaller LMS doing some knowledge retrieval and then really just one main LM kind of writing to the user and and writing the code in the same message. And this worked great. It was very responsive for for users in the UI and it was reliable and users were kind of in it and and iterating with uh with the model. Um, and so, um, let's close that down. Um, but now it's time again. We're back. We're so back. Agents this time, uh, they work. Um, and, uh, we're running them in production over a billion tokens per minute on on on these systems that I'm going to talk about.
</details>

### Lovable 的定位与产品能力

不过首先，我们来看一下 Lovable 究竟是什么。如果简化一下 UI，其实它在 2023 年和今天是一样的：左边是一个聊天区，人们在这里输入并描述他们想要构建的意图或任何想做的事情；右边是一个预览区，也就是你正在构建之物的输出或成果。在 2023 年，你可以用它做一些相对简单的事情，但现在我们真切地看到，在这个抽象层上工作，你能够构建非常复杂的东西。我认为我们甚至看到许多面向开发者的工具也正在转向这种界面，你不需要每天死盯着代码，而是被抽象出来，在架构层面上工作，或者查看所做工作的某种输出。

<details><summary>Original English</summary>
Um, but, um, first just looking at okay, what is actually loveable? So uh if you simplify the UI and this was same back in 2023 as it is today. Uh to the left we have a chat where humans come in and they kind of describe their their intent to to build or whatever they want to do. And to the right you have a preview uh which is the output or or the outcomes of of what you're building. Um and this back in 23 you could do simpler things with right but now we've really seen working at this layer of abstraction you're able to build very complex things right and I think we've even seen uh a lot of tooling meant for for developers for example moving to this type of interface where you're not really looking at the code every day and so on and you're getting kind of abstracted and working on on be architecture uh or looking at some kind of output of of what you're doing.
</details>

这是我们一直坚信的，也是 Lovable 背后的一个核心论点：你不再需要像以前那样关注代码了。我认为今天在整个行业中，我们几乎处于某种中间状态，有些人可能会说你完全不需要关心代码，而有些人可能会持有不同看法。作为从小写代码长大的人，面对这些东西难免会有些感情，但归根结底，重要的实际上不是代码——抱歉，即使去掉最后这句——重要的依然是成果。

<details><summary>Original English</summary>
And um this is something that we've always believed in and it's been kind of a core thesis behind lovable that you won't have to care about the code in in the same way that you had had to do before. And I think today we're kind of in this almost a bit in between I think in the industry where you know some people might say you don't have to care about code at all and some people might have different opinions. Um um I of course like growing up coding and these things you get a bit attached u but in the end what matters is u is actually not the code um sorry if we remove that last part but uh what what matters is uh is the outcomes right um
</details>

那么成果是什么呢？对于我们的用户来说，成果就是创立业务、实现变现，并以某种方式为他人创造价值。在深入探讨本次演讲的技术细节之前，我先快速过一遍我们为了实现这一点而构建的平台。如果审视 Lovable，关于这个平台首先可以说的是，我们拥有这个智能体，与其他智能体一样，它可以执行相当任意的任务，并且在构建软件方面非常专业。它可以使用浏览器来验证自己正在构建的内容，能够连接到 GitHub，会编写代码，你可以对那些代码做任何想做的事情等等。这就是基础的编码智能体。

<details><summary>Original English</summary>
and so um the outcomes what is that well for for our users the outcomes is um uh creating a business and monetizing and creating value for for others in in in some type of way. And I'll kind of quickly go over um what we build as a platform to to enable this before I go in kind of on the uh on the technical side of this talk. So if you if you look at lovable the first thing that that you can say about the platform is that we have this agent and like any other agent it can do quite arbitrary things and it's quite specialized at at building software uh and it has access to a browser so it can verify what it's building and um it connects to to GitHub and you know it writes code that and you can do whatever you want with that code so on. So that's um kind of your basic uh coding coding agent.
</details>

平台的其他部分是云与业务功能模块。平台的云部分旨在为这个智能体无缝提供这些托管原语。因此，我们构建了数据库、身份验证、存储、各类后端计算以及安全扫描器，还有所有这些组件的备份与日志，所有这一切都可以由智能体进行自省。这使得构建事物变得非常顺畅，你无需前往不同服务去拼接它们，我们直接为你提供这些原语。这仍然属于构建软件和托管的范畴。

<details><summary>Original English</summary>
Um and the the other pieces of the platform is this kind of cloud and and business piece of the platform. And so um the cloud part of the platform is is about just giving kind of these u hosting primitives just seamlessly to to this agent. And so we we built out databases, authentication, storage, all the types of backend compute and security scanners and like backups and logs for all of these things. And all of it can be introspected by by the agent. Um, and this just makes it seamless to to build things. You don't have to kind of go to different services to set this together. We just kind of provide you uh these primitives. Um, so that's still around building software and hosting this, right?
</details>

最后一块则是关于这些业务能力，因为用户在 Lovable 上所做工作的输出，在我们看来并不是代码，输出是一个产品或一门业务。如果你想在商业上取得成功，需要做的事情远不止写代码。因此，我们帮助用户接收付款、发送电子邮件、优化搜索引擎排位（SEO）、在 Google 和 Meta 上投放广告，并通过分析工具分析产品运行情况，你可以查看转化率并对诸如此类的事情进行优化。在这个全流程中，智能体始终处于闭环之内。可以说，这就是我们提供的功能体系。而所有这些能力，核心都是为了这个智能体而打造的。

<details><summary>Original English</summary>
Um, but then the last piece is around these business capabilities where again the output of what our users are doing on lovable, we don't see that output as code. the output is is a product or or a business. Um, and if you want to succeed as a business, you need to do more things than just write code, right? And so we we we help our users with uh receiving payments, sending emails, optimizing SEO, um, doing ads on on Google and meta um, and kind of analyzing what is happening with the product through analytics and you can look at kind of conversions and and optimize these sort of things. and the agent is in the loop in all of this, right? So, that's kind of our uh capability offering, you could say. Um, and again, the core part of this is an agent that all of these capabilities are built for.
</details>

### 智能体架构与运行时设计

在 Lovable 历史上的某个时期，我们曾将智能体的工作时长限制在仅 30 分钟，因为当时我们认为它们长时间工作并不可靠。但现在我们改变了这一点，在智能体的工作时长上完全不做任何限制，你可以设想智能体持续工作 10 个小时以上。接下来我会讲讲我们在架构中为了实现这一点所做的一些工作。

<details><summary>Original English</summary>
Um, and at some point in level history, we used to limit our agents to work for only 30 minutes because we thought they weren't reliable to to work for a longer amount of time. Um but uh now we've changed this to really be uh without any any sort of bound in terms of the length an agent can work. And so you can imagine agents working for for 10 hours plus. Um and so I'll I'll go into some of the things that we've done um in our architecture to to enable this.
</details>

第一部分是关于智能体运行时本身，以及我们如何让它能够运行更长时间。第二部分是计算机环境，每个智能体正是在这里实际开展工作、运行开发服务器，并真正验证其所做的事情。最后一部分则是验证本身；如果你希望智能体长时间工作，必须确保建立了这些反馈循环，以免它偏离到错误的方向上去。

<details><summary>Original English</summary>
And so the first piece is really around the agent runtime itself and how how we enable that to to run for a longer amount of time. And the second piece is the computer where each of these agents are actually doing their work running a dev server um and um actually verifying what it's doing. And so so the last piece then is the verification itself where if you want an agent to to work for a long amount of time, you need to make sure that you have these feedback loops in place so that it's not kind of going off uh in in in the wrong direction.
</details>

如果我们先来看智能体运行时本身，你可以设想实际上有三种不同的来源可以与智能体进行交互：可以是你自己发起提示，或者是一名人类；可以是其他智能体；也可以仅仅是一个按计划唤醒的系统。我们选择的架构方式是，为每个智能体设置一个独立的收件箱，上述任何来源都会向其中发送消息。比如你可能在此收到一条类似“当前状态如何？”的消息。你可以设想有这样一个可能一直处于运行状态的常驻智能体，设想它在这里执行了三个动作：一个请求、一次工具调用，并获取了某些结果，此时该智能体已准备好实际接收消息。因为任何人都可以向该收件箱投放消息，随后智能体就可以将其自身复制到它自己的轨迹中——本质上就是它的任务历史。如果你普遍使用智能体的话，我想你对这种交互方式应该很熟悉。

<details><summary>Original English</summary>
Um and so if we start by looking at the agent runtime itself um you can imagine that um um you have um really three different sources that can um interact with an agent. So it can be yourself kind of prompting this or a human. It could be other agents and it could also be just a system on on a schedule waking up. And the way we chose to architect this is that for for each agent we have a separate inbox uh where any of these sources would kind of send in messages. And so you might have a message here like what's the status? Um and you can imagine you have this agent and this agent is kind of an always on agent that that might be working right and so um you can imagine it has done like three actions here a request a tool call and it got some some result and then at this point the agent is ready to actually receive uh messages. So um since anyone can drop a message into this inbox, the agent then can copy that itself into its own uh what we call a trajectory basically it's a task history. Um and this is the type of interaction that I think you're familiar with if if you're using agents overall.
</details>

这就是该智能体运行时背后的第一个设计原则。我接下来会再介绍几个。智能体工作所在的轨迹，也就是迄今为止所发生事情的历史记录，实际上是该智能体各类记忆的基础。我们在设计这个轨迹时，真正从中汲取灵感的是 Git。那么轨迹究竟是什么？它是一个仅追加的日志，其中每个事件都指向其父节点，即上一个事件。正因如此，你获得了就像在 Git 中一样的绝佳能力，即可以进行分支分叉。你可以让两个事件指向同一个父节点，这本质上

<details><summary>Original English</summary>
Um so that's kind of the the first design principle uh behind this agent runtime. I'll go through a few more here. And so um the the trajectory in which the the agent is working in which is kind of the history of what has happened so far um and really the basis for any sort of of memory for for for the agent right um and we designed this trajectory with uh really git as inspiration and so the trajectory what is it it's an append only log where each event uh points towards a parent the previous event Um and because of this you get um a nice um capability just like in git where you can fork things right. So you can have two events pointing to the same parent which essentially
</details>

<!-- chunk 42/50 -->

会创建一个分支（fork）。因此，你可以在历史记录中的任何时间点启动并行智能体，而无需复制所有共享的历史记录。在语义上，如果要把这些分支合并（merge），会发生什么其实有点不明确。所以与 Git 不同，我们无法合并智能体的运行轨迹，但我们可以将它们衍生出来，对吧？而且这些智能体彼此之间可以相互通信。

<details><summary>Original English</summary>
creates a fork. Um and because of that you can kind of spin up parallel agents at um um at any point of time in the history without having to duplicate all of the kind of the shared history. Um and um semantically it's a bit unclear what would happen if you merge this. So unlike it, we cannot merge agent trajectories, but we can kind of um spawn them out, right? And these agents can can talk to each other.
</details>

我们确保设计的另一件事是，这个智能体轨迹包含了完整的历史记录以及与智能体发生的一切。因此，每一次工具调用、平台上发生的许多其他事情、工具调用是失败还是成功，诸如此类。我们所做的就是确保拥有这个仅追加日志（append-only log），由此我们实际上可以构建出将要输入给实际大语言模型（LLM）的提示词（prompt）。你可能会问，为什么要做这个？一个原因是，当你构建提示词时，如果有很长的历史记录，你可能需要做某种压缩（compaction）。例如，你想要对前面步骤中的那部分历史记录进行总结。

<details><summary>Original English</summary>
Um the other thing that uh we made sure to design for is that this uh agent trajectory, it includes kind of the full history and everything that happens uh with the agent. And so every tool call um a bunch of other things happening on the platform if a tool call like failed or succeeded and a bunch of and what we've done is make sure that we have this appendon log and and from that we can actually build a prompt that we would feed into into the actual LM and um you might ask why why why would you want to do this? Well um one one reason is that um when you build a prompt you if you have a long history you probably want to do some sort of compaction. you want to summarize part of that history um in in the earlier steps for example.
</details>

但这种总结会有所不同，例如，如果你使用不同上下文长度的不同模型，关于何时应该总结、何时不该总结，你的考虑可能会不一样。因此，通过将提示词与实际的任务历史分离开来，我们能够针对任何类型的模型或任何类型的任务渲染提示词，从而找到最佳、最优的提示词。

<details><summary>Original English</summary>
Um but this summarization would differ um for example if you use different models with different context lens you would probably think differently about when you should summarize and not. And so by separating the the prompt from the actual task history, we're able to render prompts for for any type of model or or any type of task um that that we can kind of find the best and optimal prompt for.
</details>

为了展示这个进行中的事件历史，我们这里有这个调试工具。这里记录的只是我在我们 UI 中拖动这个滑块的过程。你可以看到在右边，当我拖动它时，UI 也在随之更新。这里有 156 个事件，每一个都是该事件历史中的一个事件。你可以看到 UI 是如何渲染历史中的任意时间点的。这只是为了展示在任何时间点，我们都可以完全掌控 UI 或该平台上发生的任何其他事情，这都要归功于详细记录了所发生一切的历史记录。

<details><summary>Original English</summary>
Um, so to show this event history in in progress, we have this debug tool here. So here it's just recording of me dragging this uh slider in our UI. And you can see on the right that uh um the UI is kind of updating as I'm as I'm dragging this along and you have 156 events here and one each of those is an event in this event history. Uh and you can see how how the UI can render kind of any point in history. And this is just showcasing that at any point in time we have full control of um of say the UI or or anything else happening on the this platform thanks to um this history kind of detailing everything that has happened.
</details>

关于运行时本身，我最后要讲的一点是，运行这些智能体的进程与实际的任务历史是分开的。因此，该进程几乎完全是无状态的，在每次调用、每次轮次（turn）之间，它实际上只会持久化到任务历史中，所以进程可以随时来去。那么问题来了，我们为什么要在意这一点呢？

<details><summary>Original English</summary>
Um the the last piece I'll go over here on the on the runtime itself is that um the process that is running these agents they're separate from from the actual task history. And so the process is uh almost entirely stateless in that between each each call each call each turn um it will actually just persist into the task history and so you can have a process come and go. Um and then the question is why why do we care about this? Um well
</details>

在 Lovable，这个系统我们每天向它部署 700 次。大约是每两分钟一次。你可以想象，如果你有一个智能体要工作 10 个小时，你肯定希望在该智能体工作时不被打扰，对吧？这个智能体正在为客户处理事情。但与此同时，我们又想确保该智能体运行在最新的部署上。这可能是一个新功能之类的，但也可能是 Linux 内核中的一个安全漏洞，就像是，好的，我们需要尽快更新它。

<details><summary>Original English</summary>
uh at Lovable this system um we deploy to it um 700 times per day. So that's about once every two minutes. And you can imagine if you have um a agent working for for 10 hours um you want to not disrupt that agent when it's working, right? This this agent is doing something for for a customer. Um but at the same time we want to make sure that this agent is running on the latest deploy. and it might be a new feature or something like that, but it might also be like a security vulnerability in in the Linux kernel and it's like, okay, we need to update this ASAP.
</details>

为了做到这一点，得益于实际历史记录与进程之间的分离，我们实际上可以确保由一个智能体负责一个任务，但可以有不同的进程接入并实际完成该工作背后的计算。因此，该任务可以继续运行，同时有不同的部署在上面工作，无论是 10 个小时甚至更长时间，对吧？这就是智能体运行时。

<details><summary>Original English</summary>
Um, and and so to do that, thanks to this separation between the actual history and and the processes, we can actually make sure that we have one one agent that is working on one task, but we can have different processes taking up and actually doing the compute behind that work. Um so so this task can keep on working while we have um different deploys um working on it be it for 10 hours or or even longer right um so that's the agent runtime.
</details>

### 计算环境与检查点优化

这个平台的第二部分就是计算环境（computer）。这就是实际开展工作的地方。我们经历了很多次迭代，也与许多提供此类沙箱的供应商合作过，以供计算环境供智能体在其中工作。最终我们落脚到了现在非常努力开发出的这套系统上，即对计算机进行检查点保存（checkpointing）。

<details><summary>Original English</summary>
The second piece of um of this platform right is the is the computer. So this is where the work is actually happening. Um and we've been through a lot of iterations and uh a lot of vendors kind of working with um um providing these sandboxes for for the computer for for the agent to work in. And we've landed in in this system that we've worked really hard now to develop which is um um checkpointing um a computer.
</details>

你可以想象一下，你来到 Lovable 开始一个新项目。我们有这个通用的、我们称之为黄金检查点（golden checkpoint）的东西，它包含了操作系统和系统服务。它安装了常用的工具，以及一个准备好启动的开发服务器。这个检查点包括了磁盘上的所有内容、内存以及正在运行的进程。因此，当你开始一个新项目时，你可以免费获得所有这些。所有这些都在大约 230 毫秒内被复制过来。

<details><summary>Original English</summary>
And so you can imagine you come to level you start a new project. Uh we have this common what we call a golden checkpoint which contains the OS and the system services. It has common tools installed and a dev server that is ready to start. And this checkpoint, it it includes everything on disk uh memory and also running processes. And and so when you start a new project, you get all of that for free. And uh all of that is copied over in about 230 milliseconds.
</details>

一旦你启动了一个项目，你可能会在该项目中有一些特定的代码和一些依赖项。这些也会随着你的进行而被保存检查点。因此，每次智能体运行并完成一个轮次时，我们实际上都会保存该计算机的检查点，由此我们能够再次以不到一秒的时间，在你需要时随时启动那台计算机。这意味着我们可以通过将其关闭来节省资源。如果你离开大约 10 分钟左右再回来，我们可以以极快的速度将其启动。因此你甚至察觉不到，在这种架构下，甚至传输中的请求都不会丢失。

<details><summary>Original English</summary>
Um and so once you start a project, you you might have some specific code and and some dependencies within that project. Um and um that is also checkpointed as you go. And and so each time the the agent is running and it finishes a turn, we will actually save a checkpoint o of that computer and and from that we're able to again like very quickly subsecond uh uh spin that computer up whenever you need it. That means we can save on on resources by kind of spinning this down. If you leave for say 10 minutes or or so and come back, we can just spin it up extremely quickly. So you don't even notice this and even uh kind of requests um in transit will will not even be dropped in in in this setup.
</details>

得益于这种检查点机制，我们能做的另一件事是，就像智能体运行时中的轨迹本身一样，我们也可以对计算机进行分支（fork）。当我们这样做时，例如我们在 Lovable 中有一个名为 Draft 的功能，你可以在其中针对所做的事情在不同的环境中工作，为了支持这一点，我们需要对你正在工作的计算机进行分支。

<details><summary>Original English</summary>
Um the other thing we can do thanks to uh this checkpointing is that just like the trajectory itself uh in the agent runtime we can also fork um the computer and when we do this um we have for example we have um a feature in in level that is called draft where you kind of work in different environments of what you're doing and and to support that we need to fork the computer that you're working in.
</details>

这里我们有一个同时运行两个环境的例子。你可以想象同时运行成百上千个，对吧？为了使其在实际运行中切实可行，我们不得不做一些优化。其中一项优化是在内存（RAM）本身上实现写时复制（copy-on-write）。因此，就其使用的内存而言，创建计算机的这样一个分支基本上是零成本的。但是，一旦进程开始向内存写入内容，我们就会将该页面复制过去，只有到那时你才需要开始分配新的内存。

<details><summary>Original English</summary>
Um and um here we have um um kind of the example of doing two at the same time. And um you can imagine doing hundreds of these, right? Um and so um we've we've had to do uh some optimizations to make this feasible to to actually run. So one of these optimizations is copy on write on the RAM itself. And so creating one of these forks of a computer is uh is basically free in terms of of the RAM that it's using. But um as soon as you start writing um um in in a process to to RAM, we will kind of copy that page over and only then will you start having to allocate new memory.
</details>

这里还有另一项优化，那就是这些沙箱每个都需要几百兆字节（MB）的内存。如果存放在冷对象存储中，需要花上几秒钟流式传输进来，然后必须进入磁盘，再进入这台虚拟机的内存。但由于能够流式传输内存，我们实际上可以在虚拟机的全部内存准备好之前就将其启动。因此操作系统使用的内存先到达，然后一些进程等在内存到达后立即开始工作。这也削减了一些额外的启动时间。

<details><summary>Original English</summary>
Um and there's another optimization here also which is that um each of these sandboxes require a few hundreds of megabytes of memory. Um but and that would take a few seconds to stream in if you have it in like cold object storage and then it has to go to disk and then then into memory of this uh um this VM. But um thanks to uh um being able to stream the memory, we can actually boot up the the machine before all of the memory is is actually um ready on it. So the the memory the OS uses comes first and then like some processes and so on will will start to work as soon as the memory gets there. And this also shaves off some some extra startup time.
</details>

然后我们开始问自己，如何能让它为我们的用户变得更高效、更快速？大家可能对 Vite 很熟悉。它是 JavaScript 生态系统中大多数元框架都在使用的出色开发服务器。我们拿过来对它进行了分叉，并用 Rust 进行了重写。这使我们的代码冷启动速度提高了两倍，我们将获取此预览的时间从 14 秒缩短到了 3 秒。我们在这里提速的主要方面在于，Vite 使用 Node.js，而我们能够完全去掉那个依赖，只保留这个 Rust 二进制文件。因此，这使得这些机器上的内存占用减少了 6.5 倍。

<details><summary>Original English</summary>
Um, and then we started asking ourselves, how can we make this even more efficient and even more faster for our users? And so you might be familiar with V. It's this great dev server that most of the meta frameworks out there in the JavaScript ecosystem is using. Uh, and so we we took that and we forked it and we rewrote it in in Rust. And uh, that made our code starts two times faster and we went from getting this preview from 14 seconds to to 3 seconds. And the main um kind of thing that we made faster here is that vit uses noode.js and we're able to like drop that dependency off itself and just have this rust binary. So um that made the memory footprint be 6.5 times less uh in these machines.
</details>

通过控制我们在这些计算机中运行的应用程序，我们也能够控制我们写入内存的方式。当我们控制了写入内存的方式时，我们就能做更深入的优化。如果你回想一下我们在为不同计算机起草（drafting）时的写时复制方案，我们能够极其高效地运行它，从而让我们能够并行运行大量的智能体，让智能体探索解决 Bug 或提升应用程序性能的不同解决方案，并且

<details><summary>Original English</summary>
Um and by taking control of the applications that we're running in these computers, we're also able to control kind of how we write to memory. And so when we control how we write to memory, we're even more optimizing. If you remember back to the kind of the copy and write solution when we're drafting different um um different computers and so we're able to uh run this extremely efficiently so that we can run um lots and lots of agents in in parallel and kind of have agents explore different solutions to solving a bug or improving the performance of of your applications and
</details>

<!-- chunk 43/50 -->

等等。嗯，所以这很有意思。

<details><summary>Original English</summary>
and so on. Um and so this has been fun.
</details>

### Agent 验证与双层反馈循环

嗯，但最后一部分现在是关于验证。当然，这种计算机和这个开发服务器，是能够验证 Agent 正在做什么的重要组成部分。

<details><summary>Original English</summary>
Um uh but the last piece now is is about verification. And of course this kind of computer and this dev server is a big piece of being able to verify what an agent is doing.
</details>

嗯，如果你看验证，你可以把它想成这些反馈循环，对吧？也就是 Agent 需要获取信息。它采取了一项操作。这是一次好的操作还是糟糕的操作？

<details><summary>Original English</summary>
Um and if you look at verification, you can think of these feedback loops, right? That the agent needs to get information. It took an action. Was this a good action or was it a bad action?
</details>

嗯，你可以把它看作是内循环和外循环。这个内循环是在 Agent 的回合期间。

<details><summary>Original English</summary>
And um you can think of it as this inner loop and this outer loop. So this inner loop is um during the turn of the agent.
</details>

你会遇到一些显而易见的事情，比如构建是否正常？我们正在运行的代码中是否存在 Lint 错误或类型错误？然后你可以检查正在运行的预览中的运行时错误。你还可以在这台计算机中配备一个无头浏览器，Agent 可以进入其中，去探索它正在构建的 Web 应用程序或任何它正在构建的东西，对吧？

<details><summary>Original English</summary>
And you have kind of obvious things such as like the um is the build working? Do we have lint errors or type errors in the code that we're running? And then you can check for runtime errors in in the preview that you're running. You can also have within this computer a headless browser where the agent can go in and kind of explore um the the web app it's it's building or whatever it's building, right?
</details>

嗯，还有很多我们用来在 Agent 的回合内协助验证的其他东西。但接着你也有这个外循环，它存在于各个回合之间，而这个回合你可以理解为 Agent 何时让渡给你这个用户。

<details><summary>Original English</summary>
Um and and a bunch of other things that we're using to help verify within the turn of an agent. But then you also have this outer loop which is kind of between each turn and the turn you can think of like when the agent is yielding to you as a user.
</details>

嗯，在每个回合之间，你可能会从生产环境、从你的用户那里获得一些关于产品本身的信息，对吧？因此你可以观察访客的行为方式、用户在网上告诉你什么。你可以进行自动 A/B 测试，实际看到改动某些文案并查看这是否改善了转化率等等。

<details><summary>Original English</summary>
Um and um between each turn you might get some info on on the product itself uh from from production from your users, right? And so you can look at how your visitors are behavior are behaving. Um what users are are telling you online. Uh you can do automatic AB tests and actually see change some copy and see is this improving conversion and so on.
</details>

然后你也可以利用这些业务指标——记住，这又回到了我向你们展示的那些能力上。通过对这些方面拥有控制权，我们可以确保优化 Agent 获取外部反馈循环的方式。所以，我们可以确保如果你在处理支付业务，我们实际上可以跟踪那些交易和转化，并确保 Agent 实际上能够帮助你不仅优化代码，对吧，还能优化围绕你产品的业务策略。

<details><summary>Original English</summary>
And then you can also take these business metrics and and remember this goes back to kind of the capabilities I showed you. By having control over these things, we can make sure that we can optimize how the agent is is getting this out of feedback loop. So, we can make sure that if you're running payments, we can actually track those transactions and conversions and make sure that um the agent can actually help you optimize uh not only the the code, right, but the the business strategy um around around your product.
</details>

嗯，所以这些确实是我们一直在努力解决的三件事。我们将继续构建这些能力以及围绕真正将这些 LLM 编排成 Agent 的架构。

<details><summary>Original English</summary>
Um and so those are really the the three things that that we've been working for. And uh we'll continue to kind of build out um these uh these capabilities and this architecture around really orchestrating these LMS into into agents.
</details>

因此，我们正在构建的这个 Agent 系统，它每分钟运行数十亿个 Token。而这些计算机，对吧，我们可以随每个 Agent 一起启动，并且可以让多个 Agent 使用一台计算机。现在我们算是回到了这种非常美妙的配置中：Agent 与 Agent 对话，它们协同编排，而这一次它确实奏效了，并且多亏了其中一些优化，它正在大规模地运作。

<details><summary>Original English</summary>
And so um this agentic system that we're building, it's running billions of tokens per minute. Um and um these computers, right, we can spawn up with each agent and we can have multiple agents use one computer. And now we're kind of back to this uh quite beautiful setup where we have agents talking to agents and they're orchestrating and and this time it's it's actually working and it's working at scale thanks to some of these optimizations.
</details>

嗯，所以如果你想试用一下，你可以前往 .dev，你会看到我们的预览正在启动等等，但你会得到一个非常简单而且漂亮的界面，而且你无需操心所有这些底层细节。非常感谢大家。这是一段愉快的时光。嗯，也希望你们学到了一些东西。非常感谢。

<details><summary>Original English</summary>
Um and so if you're curious to try this out, you can head to.dev and you'll you'll see our our preview spinning up and and so on, but you'll get a very simple and um a nice interface and you won't have to care about all of this stuff. Thank you so much. It's been pleasure. Um, and uh, yeah, hope you hope you learned something. Thanks so much.
</details>

构建一个代码编写 Agent 是一回事，围绕它构建工程文化则是另一回事。为了分享 Agent 驱动开发如何转变团队的工作方式，请大家欢迎 Ramp 的主任软件工程师 Zach Bugamman。

<details><summary>Original English</summary>
Building a coding agent is one thing. Building an engineering culture around it is another. to share how agent-driven development is transforming the way teams work. Please welcome Zach Bugamman, principal software engineer at RAMP.
</details>

非常感谢大家。稍等一下。

<details><summary>Original English</summary>
Thank you so much. So, let's get a second here.
</details>

现场有 49人队的球迷吗？

<details><summary>Original English</summary>
Any 49ers fans?
</details>

>> 好吧。这比我今年在其他活动中问起当地运动队时得到的反应要好，因为我之前经常只得到一片寂静。我不得不硬着头皮说一句，好吧，看来这个笑话找错观众了。不过很高兴这次至少起作用了。

<details><summary>Original English</summary>
>> Okay. You know, that's a better reaction I've gotten to other events this year when I've asked, you know, about their local sports team because I've gotten a lot of just like muted signs. I have to hit the, you know, well, wrong audience for that type of joke. But glad at least it can hit this time.
</details>

继续……帮一下……当前幻灯片……可以了。

<details><summary>Original English</summary>
Continue help. current slide. That works.
</details>

>> 太好了。

<details><summary>Original English</summary>
>> Perfect.
</details>

### Ramp 的 Inspect：从技术走向工程文化

>> 好的。太棒了。感谢大家的耐心等待。我叫 Zach，是 Ramp 的一名工程师。我非常高兴能向大家简要介绍 Ramp 今年在我们的机器人伙伴 Inspect 的帮助下，是如何演进其工程文化的。

<details><summary>Original English</summary>
>> All right. Good. Well, thanks so much for waiting everyone. My name is Zach and I'm an engineer at RAMP. I'm just really excited to tell you all a bit about how Ramp has evolved its engineering culture this year through the help of our robotic friend Inspect.
</details>

做个简短介绍，Inspect 是 Ramp 的协作式代码编写 Agent。大约一年前，我们决定押注构建自己的代码编写 Agent，其每个会话都在运行且完全支持多人协作。无论是在 Inspect 本身、Slack、Linear 还是我们任何的集成中，Inspect 都可以与你和你的团队并肩工作。现在，它早已超越了单纯编写代码的范畴，内置的设计原语、审查 Agent 和验证流程让任何开发者都能在 Inspect 内部完成从提示词到发布的全部流程。Inspect 还与我们全公司所有的集成互联。因此，每个人都会自动连接到最重要的关联数据和工具，无论是遥测、数据库还是任何其他可用工具。

<details><summary>Original English</summary>
As a quick introduction, Inspect is Ramp's collaborative coding agent. About a year ago, we decided to take a bet on building our own coding agent with every session running and being fully multiplayer. Inspect can work alongside you and your team, whether that be an Inspect itself, Slack, Linear, or any of our of our integrations. And now it goes far beyond just writing the code with the built-in design primitives, review agents, and verification flows that let any builder go from prompt to shipping all inside inspect. Inspect is also connected with all of our integrations companywide. So everyone's automatically connected the to the data and tools that matter most, whether that be telemetry, databases, or any of the other tooling available.
</details>

通过这种方式，我们现在看到 Ramp 大约 75% 的全部代码是由 Inspect 编写并发布的。

<details><summary>Original English</summary>
Through this, we now see around 75% of all of RAMP's code uh being being written and shipped by inspect.
</details>

年初我们开始公开分享 Inspect 时，技术本身是更为新颖的部分。5 秒内启动沙盒、接入所有那些内部上下文、让 Agent 在多人环境中协同工作。大家对底层管道技术有许多疑问。但现在，随着这些概念被更广泛地采用，以及 Inspect 本身现已成为市场上的产品，技术已经远不再是曾经的障碍了。相反，我想从另一个角度谈谈：我们在围绕 Inspect 建设文化方面吸取的教训，以及你可以带走哪些经验来启发与你共事的人员和团队。

<details><summary>Original English</summary>
When we started sharing Inspect publicly at the start of the year, the technology itself was the more novel part. Spinning up sandboxes in under 5 seconds, wiring up all that internal context, having agents work together in a multiplayer setting. People had a lot of questions about the plumbing. But now with much broader adoption of these concepts and Inspect itself now being a product on the market, the technology isn't nearly the barrier that it once was. Instead, I want to talk about the other angle, the lessons we've learned around building a culture around Inspect and what you can take away to inspire the people and teams that you work with.
</details>

今天我不会过多谈论 Inspect 的那些技术细节，但如果你对此感到好奇，可以阅读我们的博客文章，或者看看 Pragmatic Engineer 几个月前与我们一起做的深度剖析。你也可以在 Twitter 上关注我的哥们 Dylan Garcia。他正在社交媒体上全力以赴，而且自从我们发布以来，他也一直在发布大量关于 Inspect 的绝佳见解。为 Dylan 点赞，请大家关注他。

<details><summary>Original English</summary>
Uh I'm not going to talk as much about those technical aspects of Inspect today, but if you are curious about that, you can read our blog posts or take a look at pragmatic engineers deep dive that they did with us a few months ago. You can also follow my boy Dylan Garcia on Twitter. He's on his social media grind, but he's also been posting a ton of really great inspect insights uh since we've launched it. So, shout out Dylan. Please give him a follow.
</details>

在 Ramp 工作的一点是，它真的会让你开始从节省时间和金钱的角度去思考一切。虽然我认为理解与你合作的系统、理解你的工具如何运作是很重要的，但如果你是一个数百人或数千人的组织，每个人都必须经历比如 15 分钟的配置流程，一旦你开始将这个成本乘以整个组织，这就浪费了好几天的时间，而收效甚微。

<details><summary>Original English</summary>
One thing about working at RAMP is that it really makes you start thinking about everything through the lens of saving time and money. And although I think it is important to understand the systems that you work with and understand how your tooling works, if you're a multiund or multi-,000 person organization and everyone has to go through say 15 minutes of setup, once you start multiplying that across an organization, this is days lost for what is very w.
</details>

然后，如果你考虑到关于最佳实践和设置 Agent 的新方法在这里的前沿发展有多快，你就会意识到这种配置成本并不仅是一次性的。更不用说这些进展并不总是均衡扩散的。所以现在你投入了不确定数量的时间和精力在这一维护工作上，而知识却没有平等传播，导致整个组织产生各不相同的结果。尽管你可以在个人层面上将其视为一种优势，但当你试图赢下全局时，你需要每个人都发挥出最佳水准。

<details><summary>Original English</summary>
Then if you consider how fast the frontier moves here on best practices and new ways to set up an agent, you realize this setup cost isn't just one time. Not to mention these advancements won't always spread equally. So now you have an indeterminate amount of time and effort spent on this maintenance without an equal spread of knowledge leading to a disparate outcomes across an organization. While you can perceive this as an advantage on individual level, when you're trying to win, you need everyone on your agame.
</details>

所以这是我们的第一课：打造能打破信息孤岛的工具。当我们发现行之有效的模式或让每个人受益的工具时，我们可以立即将其推送到我们的整个组织。如果你想花时间调整自己的配置，那完全没问题。但 Inspect 始终作为一个非常坚实的基线可用。而我们发现的是，我们从未需要强制使用 Inspect，因为它的存在作为这种基线，减少了人们随时需要去搞自己那套配置的需求。

<details><summary>Original English</summary>
So this was our first lesson. Build tools that kill information silos. When we found patterns that worked well or tools that benefited everyone, we could push it to our entire organization immediately. If you want to spend time tweaking your own setup, that's fine. But inspect is always available as a very solid baseline. And what we found is that we've never needed to mandate usage of inspect because it existing as this baseline reduced the need for people to reach for their own setups all the time.
</details>

我认为让这一点同样强大的部分原因在于，这个行业的现实是：你作为个人，不大可能在方方面面始终了解与 Agent 合作的绝对最佳方式。即便紧跟这些前沿是你的全职工作，我们所有人也都会遗漏事项、抱有偏见并存在盲点。因此，Inspect 设计的一部分就是：全公司只有一个统一的 Inspect。当有人找到了更好的使用方法，或者有了能让它更好地服务于自身工作的想法时，我们能够把它带给全公司。这最棒的地方在于，对于大多数改动而言，这对其他所有人都是无感的。你只需像往常一样继续使用 Inspect，就能从每个人随时间推移所做的改进中受益。

<details><summary>Original English</summary>
Part of what I think makes this powerful as well is that the reality of this industry is that it's unlikely that you as an individual always know the absolute best way to work with agents across everything. Even if keeping up with this is your full-time job, we all miss things, hold biases, and have blind spots. So, part of the design of Inspect is that there's just one single Inspect for the whole company. When people figure out better ways to use it or have ideas for what would make it better for the work they do, we're able to bring it to the entire company. The best part of this is that for most changes, this is invisible to everyone else. You just keep using Inspect as you normally would and benefit from the improvements that everyone's making over time.
</details>

而我们发现的是，我们真的不需要推行这些正式的

<details><summary>Original English</summary>
And what we found is that we really don't have to run these formal
</details>

<!-- chunk 44/50 -->

坐下来开展“如何有效使用 AI”的 Inspect 培训课程。由于每个 Inspect 会话默认在公司内部公开，公开协作实际上比私下协作更容易。因此，大家默认采用公开方式工作。你可以在自己已经身处的频道中，通过观察队友如何使用来学习，你的队友也可以向你学习。你甚至可以直接让 Inspect 浏览他们最近的会话，告诉你他们是如何工作的、他们怎样构建 Prompt，或者他们如何拆解棘手的难题。

<details>
<summary>Original English</summary>
sitdown here's how you use AI effectively training sessions for Inspect. With every inspect session being public within the company by default, it's actually easier to work in public than in private. As such, you default to working in public. And you can learn how to use it by watching how your teammates use it in the channels that you're already in. And your teammates can learn from you. You can literally ask inspect to go through their recent sessions and tell you about how they work, how they structure prompts, or how they break down gnarly problems.
</details>

我认为这不仅对 Ramp 的构建者们有帮助，对 Inspect 团队本身也很有助益。我们经常看到人们以我们最初未曾设想的方式使用 Inspect。这进而启发了我们应该朝着什么方向构建，无论是针对常见模式提供更多原生原语，还是发现哪些工具和数据有所缺失。总而言之，它创造了一个自给自足的闭环：通过观察大家已经在用 Inspect 实现什么，我们能够朝着让 Inspect 最为成功的方向进行构建。

<details>
<summary>Original English</summary>
I I think this has not just been helpful for the builders at ramp, but also for the inspect team itself. We frequently see the way that people use inspect in ways that we didn't originally imagine. This then informs what we should build towards, whether that should be more native primitives for common patterns or where tools and data are missing. All in all, it creates this self-sustaining loop where we're able to build towards what makes Inspect the most successful by seeing what people are already achieving with Inspect.
</details>

### 建立信任

这引出了我们学到的第二个经验：关键在于建立信任。我认为平心而论，对今年的每位工程师来说，采用智能体驱动的编码一直是一次巨大的信任建立过程。模型在编写高质量代码方面变得更加胜任，这对建立信任有所帮助。但这其中很大一部分，仅仅在于学会信任智能体所构建的东西。

<details>
<summary>Original English</summary>
This feeds into the second lesson that we've learned. It's all about building trust. I think it's fair to say that adopting agentic driven coding has been a massive trust building exercise for every engineer this year. It's helped that the models have become more competent at writing high-quality code. But there's a large part of this that's just learning to trust what an agent builds.
</details>

对工具建立信任，很大程度上源于向他人学习。毕竟，这也是我们大多数人来到这里的原因，对吧？你们想听自己尊敬的人——或者至少我希望你们尊敬的人——教你们他们所学到的东西。但如果我们将知识库仅仅局限于那些能在公开演讲中找到别样乐趣的人，我们依然无法了解全貌。知识共享的民主化作为一个概念，让我觉得非常着迷。我们能否构建本质上能共享每个人知识的系统，而不是围绕少数特定领导者聚集？这就是 Inspect 一直在努力构建的方向。

<details>
<summary>Original English</summary>
So much of building trust in tools comes from learning from other people. After all, that's why most of us are here, right? You wanted to listen to people you respect, or at least I hope you respect, uh, teach you about the things that they learned. But if we limit our corpus of knowledge to just those who find the perverse enjoyment in public speaking, we're still not getting the full picture. This democratization of knowledge sharing is just fascinating to me as a concept. Instead of grouping around a select few leaders, can we build systems that inherently share the knowledge of everyone? This is what Inspect has uh built towards.
</details>

每当有人用 Inspect 发布东西时，大家都能在已完成的工作上直接看到它。会话本身很便于分享。它是关于该变更如何形成的活生生的制品。当 Pull Request 提交时，任何进行评审的人都不只是看到扔过来的 400 行 diff 并听天由命。他们可以看到你们进行的完整对话、Inspect 使用的所有工具、修改前后的屏幕截图，甚至是验证智能体在浏览器中逐步点击应用以证明其工作经得起检验的录屏视频。这让大家毫不费力地不仅展示改动了什么，而且展示为什么可以信任它。

<details>
<summary>Original English</summary>
Every time someone ships something with Inspect, people can see it right there on the work you've done. The session itself is an easy to share. It's a living artifact of how that change came to be. When a poll request goes up, anyone reviewing it doesn't just see the 400line diff dropped over the wall and hope for the best. They can see the exact conversation that you had, all the tools that Inspect used, before and after screenshots, or even a video recording of the verification agent clicking through the app in the browser to prove its work holds up. It makes it effortless to show not just what changed, but why you can trust it.
</details>

它也让那些平时不经常合作的人更容易参与进来。这方面有一个有趣的时刻，那是早在二月份的时候。我们的一位工程师 Andrew 报告了一个 Inspect 中的 bug。因此，我自然而然地打开 Inspect 让它去排查。有意思的是，虽然 Inspect 使用 Datadog 已经有一段时间了，但我们才刚刚完成 Inspect 本身的代码插桩。我是说，Inspect 主要由前端产品工程师构建，所以链路追踪对我们来说是一个有点陌生的概念。但无论如何，这正是我们对 Inspect 进行测试的大好时机。然后 Inspect 表示是代码插桩导致了错误。是的，正是让我们能够排查该错误的代码插桩本身实际引发了这个错误。所以，Dylan 和我当时对这个机器人的解释并不是很信服。而 Andrew 就表现得像：算了，我去用 Claude Code 吧。虽然我们没有强制要求必须使用 Inspect，但就个人而言，这绝不是我想听到的话。

<details>
<summary>Original English</summary>
It also just makes it easier to bring people you don't work with all the time into the fold. A fun moment on this one. It was back in February. One of our engineers, Andrew, reported a bug in Inspect. So, naturally, I reached for Inspect and asked to investigate. What's funny here is that although Inspect had access to data dog for a while, we'd only just finished instrumenting inspect itself. I mean, inspect was primarily built by front-end e- product engineers. So, tracing is a little bit of a foreign concept for us. But in any case, it was a great time for us to put it to the test for inspect. And inspect says the instrumentation was causing the error. Yes, the very instrumentation that was letting us debug this error was actually causing this error. So, Dylan and I were not exactly convinced by the robot here. And Andrew is just like, whatever, I'll use cloud code. And and while we don't have a mandate to use inspect, I mean, personally, these were not the words I wanted to hear.
</details>

所以，这里没有人真正信任任何人。Dylan 和我不相信机器人的解释；Andrew 不信任我们能做出好用的东西；至于 Inspect，好吧，我不知道 Inspect 是否信任任何人，但没关系。没关系。但因为这一切是在公共场合共同发生的，我们便继续深入排查。Dylan 让 Inspect 查看所使用的遥测库的代码，看看这是否只是之前就在发生但缺乏可见性的情况——因为到现在为止编码问题必定已经被解决了，不可能存在我们引入的 bug——而这一次它带着更具体的内容返回了。OTel 库调用了 fetch，但从未读取或取消响应体。这在当时只是 Cloudflare 平台的一个限制，尽管它发生在一个专门针对 Cloudflare Workers 制作的库中，但这种事难免会发生。毕竟这个库是在 AGI 之前编写的。此时，我们让 Inspect 生成一个补丁。它更新了导出器以显式取消响应体。在部署期间，我们在帖子讨论串里发了点牢骚。但我们看到部署之后，就再也没有出现过任何错误。所以太棒了，Inspect 修复了这个 bug，这在当时本身并不算什么特别的事。

<details>
<summary>Original English</summary>
So, nobody here is really trusting anybody. Dylan and I don't trust the robots explanation. Andrew doesn't trust us to build something that works. And inspect, well, I I I don't know if Inspect trusts anyone, but that's okay. That's okay. But because this is happening together in public, we keep proddding at it. Dylan asks inspect to look through the code of the telemetry library using and see if this was just something that was happening before without visibility because surely by now coding has been solved and there can't be bugs that we introduced and this time it comes back with something a bit more specific. The hotel library calls fetch but it never reads or cancels the response body. This was just a cloudflare platform limitation at the time albeit happening in a library specifically made for cloudflare workers but that happens. This library was written pre-agi after all. At this point, we ask inspect to make a patch. It updates the exporter to explicitly cancel the response body. We grumbled in the thread a bit while it's deploying. But we see after it deployed, there haven't been any errors since. So great, inspect fixed the bug, which at this point it's nothing special in itself.
</details>

但在这个讨论串中，正在上演一个重要得多的故事。在 Inspect 之前，像这样的报告可能会被确认收到，建一个工单，然后我们中的一个人私下去排查。Andrew 稍后可能会收到一条说明已修复的消息，但有趣的工作都是私下完成的。然而现在，在公共场合做这一切更容易。正因如此，Andrew 自然而然地开始深度参与，想要分享他的想法和经验。随后在同一个讨论串中，这就引申出了关于 Inspect 如何为其他工作提供支持的想法。这一切都不需要任何督促或强加合作的压力。相反，感觉就像是“哇，这些人正在做很酷的事情，我们可以一起合作”。因此，在一小时的时间里，我们从一个遇到体验受损且心存怀疑的用户，转变成了一位热切想要一起构建的积极参与的同事，并获得了一个更加稳定的 Inspect。

<details>
<summary>Original English</summary>
But there was a much more important story playing out in this thread. Before inspect, a report like this might have been acknowledged. a ticket filed and then one of us would have gone away to debug it. Andrew might have received a message later saying it was fixed, but the interesting work would have been done in private. Now though, it's easier to do all of this in public. And as such, Andrew naturally starts becoming engaged, wanting to chime in with his thoughts and experiences. And then in that same thread, this leads to ideas coming up about how Inspect could power other work. And none of this required any proddding or pressure to work together. instead it was just like oh these guys are doing something cool and we could work on it together. So in the span of an hour we go from a skeptical user with a broken user experience to an engaged colleague wanting to build together and a more stable inspect.
</details>

### 共同放眼更大目标

所以，一旦你拥有了一个让每个人在第一天就能获得最佳配置且没有信息孤岛的工具，并且建立起了一个凝聚创新的信任体系，接下来会发生什么？这是我想分享的最后一个经验。我认为唯一剩下的事情就是共同放眼更大的目标。

<details>
<summary>Original English</summary>
So once you have a tool that gives everyone the best setup on day one with no information silos and you've built a system of trust that brings innovation together, what happens next? This is the last lesson I want to share. I think the only thing left is to think bigger together.
</details>

今年让我感到心痛的一件事，是对孤狼式操作者产生了如此多的崇拜。在 AI 的帮助下，我们每个人在个体层面能做更多的事情，这固然很棒，但我认为这绝不能是终局。如果我们不向外构建、不与他人合作，并且不继续分享我们取得的进展和所学，我认为这一切都会走向内耗崩溃。我们将只把自己视为目标受众，并且无法通过考虑他人的视角和经验来获得成长。

<details>
<summary>Original English</summary>
Something that's pained me this year uh is how much reverence has been built for the lone wolf operator. It's great that we can all do more individually with the help of AI, but this can't be the endgame in my opinion. If we don't build outwards, collaborate with other people, and continue to share the progress and learnings we make, I think this is all going to collapse in on itself. We'll only consider ourselves as our target audience and we won't grow through the consideration of others perspectives and experiences.
</details>

这并不是说我对这一切充满悲观。我们所有人都在这里，希望这本身就能证明连接的价值。然而更重要的是，我认为我们可以塑造自己的工具，使这些连接能够比以往任何时候都更加蓬勃发展。

<details>
<summary>Original English</summary>
This is not to say I'm all doom and gloom about this. The fact we're all here hopefully is a testament to the value of connection. More importantly though, I think we can shape our tools to enable these connections to flourish even stronger than before.
</details>

我讲的关于 Andrew 的那个故事，在 Ramp 内部已经上演了许多次。坦白讲，这可能是我觉得 Inspect 最鼓舞人心的地方。当然，它是一个编码智能体，但令人瞩目的是，它已经成为了文化的一部分。Ramp 的每个人都知道它的面孔。我们在节假日为它装扮，随着时间推移为它加入彩蛋，并且随着 Ramp 本身的发展不断演进它。正如任何一位 Ramp 工程师都能告诉你的那样，并非所有的迭代都是完美的，但我确实认为每一次迭代都是大家共同完成的。

<details>
<summary>Original English</summary>
That story I told about Andrew has played out so many times within ramp. It's probably the most inspiring thing about Inspect to me, honestly. Sure, it's a coding agent, but remarkably, it's become part of the culture. Everyone at RAMP knows its face. We dress it up on holidays. We throw in Easter eggs over time. And we evolve it as RMP itself has evolved. Not all iterations have been perfect, as any RAMP engineer could tell you. But I do think every iteration has been together.
</details>

回到今年早些时候，Inspect 所拥有的功能远没有今天这么多。一个很好的例子就是它的代码评审智能体。在此之前，我们使用各种现成的代码评审产品，经常在它们之间轮换以寻找合适的产品。但在某个时候，Daniel 和 Franel 这两位工程师意识到，我们或许可以自己构建它，因为 Inspect 已经拥有来自各种来源触发的自动化触发器，包括在 Pull Request 打开时触发。仅仅凭借我们已经构建好的功能，他们就开始着手构建 Ramp 的另一个深受喜爱的智能体——Review Buddy。非常酷的是，这与 Inspect 本身作为一个副项目的起源非常相似，这两位工程师在着手做这件事时，不需要请求许可来构建它。他们只是挑战自己去构建更好的东西，利用 Inspect 更快地推进，并迅速构建出了一个对所有人都更好的智能体。

<details>
<summary>Original English</summary>
Going back to earlier this year, Inspect didn't have nearly the amount of functionality it has today. A great example is its code review agent. Before this, we were using various off-the-shelf code review products, frequently rotating between them to find a good fit. At some point though, a couple engineers, Daniel and Franel, realized that we could probably build it ourselves as Inspect already had automation triggers that fired from a variety of sources, including when a pull request was opened. With just what we built already, they got to work building another beloved agent at RAMP, review buddy. And what was so cool about this is that much like Inspec's own origins as a side project, these engineers were working on this. They didn't need to ask for permission to build it. They just challenged themselves to build something better, used inspect to move faster, and quickly built an agent that was better for all of
</details>

<!-- chunk 45/50 -->

ramp。

这确实迫使负责 Inspect 的我们以不同的方式思考 Inspect。在那个时间点，我们对于 Inspect 所谓“仅仅”作为一个编码 Agent 还算满意。但一旦我们看到其他人推动它去做的事情，这让我们开始思考 Inspect 如何能够变得更完备。如果这种推动没有自然发生，我认为 Inspect 团队要达到那个阶段需要花更长得多的时间。

<details><summary>Original English</summary>
ramp.

This really did force us working on Inspect to think about Inspect differently. At that point in time, we were pretty okay with Inspect quote unquote just being a coding agent. But once we saw what others were pushing it to do, it got us thinking about how Inspect could become full circle. If this push didn't happen naturally, I think it would have taken the Inspect team a lot longer to get there.
</details>

这就是我所说的“共同拓宽思考视野”。特别是随着模型性能的持续提升，现在正是推动自己以及身边的人拓宽思考视野的时候。我鼓励你们大家在接下来的一周抽出一些时间，问问和你一起工作的每一个人：“我们一直想做却还没做的事情是什么？”一旦你发现了那些事情，就试着一起构建它们。现在真的没有任何借口不去尝试了。你能用上和别人完全一样的模型。但你必须得从某个地方开始。而且我相信，在解锁成果方面蕴藏着巨大的潜力，不仅是对你自己，也是对你身边的人。

<details><summary>Original English</summary>
This is what I mean about thinking bigger together. Especially with the continued improvements in model performance, now is the time to push yourself and the people around you to think bigger. I encourage all of you to take some time in this coming week to ask everyone that you work with, what have we been waiting to do that we haven't done yet. And once you found those things, try to build them together. There's really not an excuse to not just try anymore. You have access to the same models as everyone else. But you have to start somewhere. And I believe that there is so much potential in unlocking wins, not just for yourself, but for the people around you.
</details>

Inspect 本身就是这样诞生的。不仅是出于我和 Jason 想做的东西，更是出于想为一个我由衷喜爱并由衷尊重的团队构建某些东西的愿望，希望能让他们的工作稍微更加愉快一些。

<details><summary>Original English</summary>
Inspect itself was born this way. not only as something that I wanted to build and Jason wanted to build, but out of a want to build something for a team that I truly love and truly respect that would just make their jobs a little more enjoyable.
</details>

现在，如果你想使用一个融合了我们总结出的所有这些经验教训的编码 Agent，我很高兴地宣布，Inspect 现在已在 RAMP 之外开放使用。如果你访问 inspect.com/ieie，我们会在候补名单上优先考虑你和你的团队。我们处理这份候补名单的速度实际上相当快，所以期待很快能收到我们的消息。除此之外，我希望你们喜欢听到关于我们的机器人朋友 Inspect 的介绍。如果这些主题引起了你的兴趣，欢迎随时在这里或在 X 上与我们联系。除此之外，非常感谢大家的倾听。

<details><summary>Original English</summary>
Now, if you'd like to use a coding agent that has embodied all these lessons that we've learned, I'm happy to say that Inspect is now available outside of RAMP. If you go to inspect.com/ieie, we'll prioritize you and your team on the wait list. We're actually moving through this weight list pretty quickly, so expect to hear from us soon. But otherwise, I hope you've enjoyed hearing about our robotic friend, Inspect. If these topics interest you, feel free to reach out here or an X. But otherwise, thanks so much for listening.
</details>

从构建开发者工具到探索自主软件开发的未来，我们的下一位演讲者多年来一直在不断拓展可能性的边界。女士们先生们，请热烈欢迎独立 AI 顾问、Beads 与 Gas Town 的创作者——Steve Yegge。

<details><summary>Original English</summary>
From building developer tools to exploring the future of autonomous software development, our next speaker has spent years pushing the boundaries of what's possible. Ladies and gentlemen, please welcome Steve Yaggi, independent AI advisor and creator of Beads and Gas Town.
</details>

大家好。

<details><summary>Original English</summary>
Hey everybody.
</details>

好的，激动人心的时刻。谢谢大家。现场真的坐满了，太棒了。感谢大家在这一天行将结束时赶来。呃，我真的很兴奋能够来到这里与大家交流。我每次都会写一篇、一篇专门定制的演讲。所以这篇、这篇演讲就是今天专门为你们写的，基于我和你们中很多人的交流。呃，我入行大概 40 年了。我在亚马逊和谷歌工作了大约 20 年。我涉足过各个领域，做过各种各样的事情。呃，在过去一年或稍微多一点的时间里，我一直是独立状态，基本上就是在摆弄、嗯，摆弄软件工厂。是的。所以，嗯，我算是发明了它们。对吧。在 1 月 1 日，我推出了 Gas Town。我甚至觉得我们那时候都不把它们叫做软件工厂。我想我称它为编排器。但我知道我想让 Claude 来运行 Claude。对吧。事实证明这比、比我想象的要稍微棘手一点。我去年整整一年都在琢磨这个，然后我写了——

<details><summary>Original English</summary>
All right, exciting times. Thank you. The room is really full. That's awesome. Thank you all for coming at the end of the day. Uh I'm really excited to uh be here and to chat with you. I write a a you a a custom speech every single time. So this is this speech was written just for you today based on talking to a bunch of you. Uh I've been in the industry for about 40 years. I worked at Amazon and Google for about 20 years. I've been all over the place, done all kind of stuff. And uh and uh for the last year or a little bit more I've been independent and just kind of like playing with um playing with software factories. Yeah. So um I kind of invented them. Right. On January 1st I launched Gas Town. I don't even think we called them software factories back then. I think I called it an orchestrator. But I knew that I wanted Claude to run Claude. Right. And it turned out to be a little trickier than than I thought. I spent all last year on it and I wrote
</details>

这挺有意思。我看不见我的幻灯片，但你们能看见我的幻灯片。所以这样也行。去年我写了两个编排器。它们是试图让 LLM 变得更聪明的尝试。Vibe coder 和 VC，你们知道的，用来做工程类的事情，比如做代码审查以及所有那些事情，对吧？非常、非常糟糕的想法。彻底的失败。我就是构建了这些庞大的单体系统。我当时是在与苦涩的教训抗争。不要试图让 LLM 变得更聪明。它们自己会变聪明的。在经历这几个月之后，尽管 beads 确实从中脱颖而出，而且 beads 是一个非常酷的发现，beads、beads 就是生命。这里有谁用 beads？

<details><summary>Original English</summary>
That's interesting. So I can't see my slides, but you can see my slides. So that'll work. So I wrote two orchestrators last year. They were an attempt to make the LLM smarter. Vibe coder and VC, you know, to do engineering stuff like, you know, do code reviews and all that stuff, right? Really, really bad idea. Just complete failure. I just built these huge monoliths. I was fighting the bitter lesson. Don't try to make LLM smarter. They will get smarter. And after a couple of months of this, although beads did fall out of it and beads was a really cool discovery and beads, beads is is life. Who here uses beads?
</details>

有一些。是的，相当不错。实际上相当不错。是的，我们稍后会聊一点关于它的内容。不好意思。然后我有了 Gas Town。然后到了 6 月，我有了 Wheelhouse，这是我自己的。所以我决定从头构建一个工厂，只是为了开发我的电子游戏，对吧？因为就像每个人都在为了构建工厂而构建工厂一样。这有点自我审视过度了。有点像，是的。对吧。你知道的，这就像为什么他们不，你知道，我认为更多的人需要去构建实际的东西，而不仅仅是用来构建东西的工具，对吧？我、这会成为今天的一个主题，对吧？而且关键是，我在这里看到的一个模式是，它们都会经历这样一个阶段：模型变得非常兴奋，它们为你构建出非常酷的东西，然后每次都不可避免地变成垃圾山。

<details><summary>Original English</summary>
A few. Yeah, pretty good. Actually, pretty good. Yeah, we'll talk a little bit about it. Excuse me. And then I had Gas Town. And then I had in June I had Wheelhouse, which was my own. So I decided to build a factory from scratch just to work on my video game, right? Because like everyone's building factories to build factories. It's kind of naval gazing. It's kind of like Yeah. Right. You know, it's like why they're not, you know, I think more people need to build stuff, not just tools for building stuff, right? And I I this is going to be a theme today, right? And and the thing is the one pattern that I've seen here is all of them go through a phase where the models get really excited and they build something really cool for you and then it just turns into garbage mountain
</details>

每一次都是如此。Gas Town 遇到了这种情况。Wheelhouse 也发生了好几次。我不得不把整个东西彻底推倒重来了好几次。对吧。这几乎就像是，每一代模型家族、每一代模型到来时，构建的东西都刚好超出了它能掌控的规模。然后下一代模型接踵而至，说道：“是的，我们得把那个烧掉推倒重来。”对吧？我、这成了一种模式。我已经一次又一次地经历过这个了。我可以跟你们聊聊关于这方面的一些事情。但首先，让我跟你们讲讲我的游戏。

<details><summary>Original English</summary>
every single time. It happened to Gas Town. It happened to Willhouse several times. I had to burn the whole thing to the ground a couple times. Right. It's almost like like every model family, every model generation comes in and can build something that's just a little too big for it to handle. And then the next model generation comes in and goes, "Yeah, we're going to have to burn that." Right? And I It's a pattern. I've done this over and over again. And I can tell you some things about it. But first, let me tell you about my game.
</details>

这是一门有趣的小型 RPG。我已经在上面断断续续开发了 30 年。它有从 2001 年就开始玩的用户。所以，我字面意义上拥有玩了 25 年的玩家。他们现在还在玩。比如，你现在登录进去，大概能找到 10 个人正在闲逛做任务、做实时任务等等。这是由玩家——你知道，由玩家贡献内容的游戏，对吧？它是一个 MUD。比如，它们在 90 年代非常流行。它们就像纯文字游戏，而这一个在文字之上加入了图形，这事实证明对 AI Agent 而言非常理想，因为它是文本形式的。它们实际上可以通过远程终端连接玩这款游戏，而且它们主动要求我这么做。呃，所以我们也会讨论那部分。这是我的系统大致架构的一个较早的架构图。所以当我为 Wyvern 构建这个 Wheelhouse 软件工厂时，我完全不在乎它能否、你知道，被你们使用，对吧？没有开源，全凭定制。我发现了外星抱脸虫模式。好的，也就是说你的工厂变成了一只外星抱脸虫，就像吸附在你的产品上，并直接完全融入其中。

<details><summary>Original English</summary>
It's a fun little RPG. I've been working on it for 30 years. It has players that started in 2001. So, I literally have players that have been playing for 25 years. They're still playing. Like, you can log in right now and find probably 10 people just screwing around doing quests, live quests, and and whatever. It's a It's a player uh you know, the players contribute the content, right? It's a MUD. Like, they were really big in the 90s. They're like text games, and this one has graphics on top of it, which turns out to be like really ideal for AI agents because it's text. They can literally play the game via TNET, and they asked me to. Uh, so we'll talk about that too. Here's an older architecture diagram of what my sort of of what my system looks like. So when I built this wheelhouse software factory for Wyvern without a care in the world for making it, you know, usable by you, right? No open sourcing, just bespoke. I discovered the alien face hugger pattern. All right, which is where your factory turns into an alien face hugger and like gloms onto your product and just becomes grown into it.
</details>

好的，你看，我们今天关掉 AI 依然可以运行这个游戏。我、管理员、玩家和社区，我们能够——但到了这个节点，我们会非常想念 AI。玩家正在与我的工厂直接对话。工厂正在与我的管理员沟通。他们在索要功能。我甚至不在这个流程闭环里。它就像一个愿望工厂。现在是他们在构建这个游戏。他们都是老玩家，其中有一群我信任的人能够对游戏做出，你知道，明智的决定。但他们现在全都在和我的工厂协同工作。如果关掉他们会生气的。有趣的是，刚开始的时候，他们的反应是：“暂停一下。首先，这些 AI 东西到底是什么？”而且他们还说：“不要 AI 艺术。”因为他们能看出那些东西是粗制滥造的残次品。我说：“好的，我们有真人画师。”然后他们说：“但我们确实挺喜欢所有这些新功能的，只是我们真的很害怕这种节奏。你能给我们一份路线图吗？”我的玩家跑来找我索要路线图。他们说：“你必须慢下来。这实在是太多了。”我说，好吧。然后我查看了一下，我的软件工厂这家伙一天能捣鼓出大约 50 到 100 个功能。我开始做这个的时候，我的待办事项里积压了 100 年的工作量，而 Claude 在大约 4 个月内就完成了大约 60 年的量，对吧？这简直疯了。而他们根本看不过来每天 100 个功能。他们甚至都来不及阅读关于每天 100 个功能的介绍，更不用说去进行试玩测试了。我的工厂彻底让我的客户群、我的用户应接不暇。它还让我的机器过热，而且还惹恼了我的会计。

<details><summary>Original English</summary>
Okay, like look, we could turn off the AI and still run the game today. Me and the admins and the players and the community and we could we could but we would miss the AI at this point. The players are talking to my factory. The factory is talking to my admins. They're asking for features. I'm not even in the loop. It's like a wish factory. They're building the game now. They're all old-timers and there's a set of them that I trust to make, you know, wise decisions about the game. But they're they're all working with my factory now. And they'd be mad. The funny thing is when it first started, they were like, "Time out. What is this AI stuff for starters?" And they were like, "No AI art." Because they could see it was slop. I'm like, "Okay, we got human artists." And they said, 'But we do kind of like all the new features, but we're really scared of the pace. Can you give us a road map? My players came to me asking for a road map. They were like, 'You got to slow down. It's too much. And I was like, okay. And I took a look and my software factory, this thing had been cranking out like 50 to 100 features a day. I had a hundred years of work in my backlog when I started this and Claude got through about 60 years of it in about four months, right? It's absolute insanity. and they can't look at a 100 features a day. They can't even like read about 100 features a day, let alone play test them. I was my factory was completely overwhelming my customer base, my users. It was also melting my machines and it was like annoying my accountant.
</details>

我的意思是，她挺喜欢和作为我财务主管的 BAT 一起工作的。呃，但是她给我寄了一张 1,200 美元的账单，因为，对吧，那东西给她发了 20 封邮件。这就是我的工厂。它看起来就是这个样子的。它是如此美观。看它有多漂亮。嗯，好吧。我承认它有点难看。噢，这是它一张非常早期的截图，不过无所谓了。它基本上就是一个 Emacs，因为我不在乎你们怎么看。呃，现在有人正在构建类似这样的东西，比如来自 Mitchell Hashimoto 的 Superlogical，还有我不知道——

<details><summary>Original English</summary>
I mean, she likes working with BAT as my head of finance. Uh, but she sent me a $1,200 bill because, right, the thing sent her 20 mails. This is my factory. This is what it looks like. It's so beautiful. Look how beautiful it is. Um, okay. I admit it's a little ugly. Oh, and this is a really old screenshot of it, but whatever. It's basically, it's an Emacs because I don't care about you. Uh, there are people who are building stuff like this like Superlogical from Mitchell Hashimoto and I don't know,
</details>

<!-- chunk 46/50 -->

也许这世上的牧羊人群体，你知道，会用来运行大量智能体，但这可是差不多50个智能体。好吧，我其实就像是在未来运行。

<details><summary>Original English</summary>maybe the Herder folks of the world, you know, for running like lots of agents, but this is like 50 agents.</details>

好吧，我来告诉你们我是怎么做到的。我有22个Claude Max账号。好的，也感谢Anthropic让我能继续这样做。呃，Jeffrey Emanuel有28个。实际上，当他们加入电话号码验证时，我就不得不停下了。我不想再加了。

<details><summary>Original English</summary>Okay, I'm actually like operating in the future. Okay, and I'll tell you how I do it. I have 22 Cloud Max accounts. All right, and thank you to Anthropic for letting me continue this. Uh Jeffrey Emanuel has 28. I actually had to stop when they added the phone number verification. I didn't want to add anymore.</details>

不管怎样，我曾在某个时候问过我的工厂。我说：“嘿，嘿，要多少？”因为他们一直在说：“嘿，再给我们几个账号。再来几个。再来几个。再来几个。”大概是每月200美元一个，对吧？我当时就觉得，所以我最后问：“你们到底想要多少个？”他们说：“再要五到七个。”我就说：“为了让这家工厂开足马力运转，我们稳态下需要多少个？”他们说要55个账号。我当时的反应是：“不，不行，我有20个，那已经是20个我得登录进去的Chrome个人资料了，不行。”

<details><summary>Original English</summary>Anyway, I asked my factory at one point. I said, "Hey, hey, how much?" Because they kept going, "Hey, give us a couple more accounts. Couple more. Couple more. Couple more." It's like 200 a month, right? And I'm just like, so I finally said, "How many do you want?" They're like, "Five, seven more." And I'm like, "How many do we need steady state to keep this factory operating full throttle?" And they said 55 accounts. I was like, "No, no, I have 20. It's already like 20 Chrome profiles that I got to log into and no."</details>

所以我告诉它：“你们……我们要开始把重点放在燃料效率上了。”而且，我会讲到这一点的。对吧？

<details><summary>Original English</summary>So I told him, "You're we're going to start focusing on fuel efficiency." And so and I'll talk about that. Right?</details>

### 五骑士与工厂运维挑战

所以，这就是五骑士——这就是我今年不得不应对的事情。我跟你们说，我是在未来运行，因为再过12到18个月，你们大家都会走到这一步。到那时，要么推理成本大幅下降——这可能会发生，也可能不会发生——要么蒸馏技术会让寓言级别的智能变得唾手可得，而且你们也不必非得有一位贴心的妻子，允许你们每个月单是推理就自掏腰包花上5,000美元，外加云端算力上的另外5,000美元，因为我的游戏目前可没法从我的老玩家身上月入10,000美元，对吧？

<details><summary>Original English</summary>So the these are the five horsemen of this is what I've had to deal with this year. I I'm telling you I'm operating in the future because like you're all going to be here in 12 to 18 months when either inference costs drop significantly which may or may not happen or distillation causes fable class uh intelligence to be super readily available and you don't have to have a lovely wife who lets you spend $5,000 a month out of pocket just on inference and another 5,000 on cloud compute because my game ain't making 10,000 a month right now for my old players, right?</details>

呃，但我们之所以在做这件事，是因为我们在学习。嗯，这就是……这就是我不得不应对的事情。

<details><summary>Original English</summary>uh but we're doing it because we're learning and um and this is this is what this is what I I have to deal with.</details>

### 工作管理

首先，我们先从工作开始谈起。好的，你需要一种方式来表征你的系统中将要发生的工作。当你构建一座软件工厂时，核心就在于源源不断地推进大量工作。好的，这真的变得像是……工作就像是这种流体，你不得不……它会在池子里积压停滞，然后，“噢，他们全都在等待安全工位。”你就会觉得，“老兄，这可是Pluribus啊。你们都是同一个模型。为什么非得等安全工位？”你花了大把时间在和你的工厂争执。这是……呃，这属于复杂的智力层级划分。你必须打包你的工作，你必须路由你的工作。你知道，如今对此并没有什么好的解决方案，除了beads。据我所知，beads在这方面真的非常、非常、非常出色。它是一个能自动为你转化为知识图谱的智能体速度任务追踪器。

<details><summary>Original English</summary>So first first we'll start about with work. All right, you need a way to represent the work that's going to happen in your system and when you're building a software factory it's all about pumping lots of work through. Okay, it really becomes like a work is like this fluid that you have to like it gets stalled up in pools and oh they're all waiting on security desk. You're like this is pluribus man. You're all the same model. Why does it have to wait on security desk? You spend a lot of your time arguing with your factory. It's uh it's complicated inter intelligence tiering. You have to tar your work. You have to route your work. You know, there aren't any good solutions for this today except beads. As far as I can tell, beads is really, really, really good for this. It's a agent speed task tracker that turns into a knowledge graph automatically for you.</details>

接着在追踪工作时，这就是我每天早上必须做的事情。每天早上对着我的工厂，我都会说：“噢，看来我们遇到了停滞。昨晚有四名工人工位什么都没干。噢，还有这些……这几个跑得太快了，我们不得不慢下来等待人工卡口。”你知道，“你们这些人到底在干嘛？”可观测性一直都非常困难。呃，这……你知道，对工作的管理就变成了你不得不去做的这样一件事。

<details><summary>Original English</summary>And then as you're tracking work, this is the kind of stuff I have to do every morning. Every morning with my factory, I'm like, "Oh, looks like we had a stall. Four four workers didn't do anything last night. Oh, and and these the these these ones went way too fast, and we have to slow down and wait for human gates." You know, what are you guys even doing? Observability is always really hard. Uh, it's, you know, management of work becomes just this this thing that you got to do.</details>

### 燃料：Token

接下里你必须面对的事情就是燃料——Token。

<details><summary>Original English</summary>And the next thing you got to deal with is fuel tokens.</details>

我跟你们说，这真是太痛苦了。我是说，我一个月花5,000美元，而且其中的每一个Token对我来说都弥足珍贵，对吧？因为这是我自掏腰包。我想我每天大概要消耗50亿个Token。如果我是直接调用实际的API接口，折算成API花销的话，大约是每年150万美元。如果是开足马力运转，那就是每年300万美元。所以再次强调，我正在做的是大多数人做不到的事情。你在一家公司里是做不到这点的，因为成本会高到令人望而却步。就像PLG那样，你知道，Codex和Claude Max那些200美元的账号，就是他们的Costco热狗。那是他们的引流赔本商品，对吧？顺便说一句，是TK想出了这个比喻。他可能就在现场。所以，你知道，我抱有希望，希望他们能让我们继续、继续创新，因为我觉得我从中为Claude跑出了一些相当不错的训练会话。所以，我们大家都获益。

<details><summary>Original English</summary>It's just so painful, I'm telling you. I mean, I'm spending 5,000 a month and every one of those tokens is like precious to me, right? Because it's out of my own pocket. I think I'm spending about five billion a day of tokens. And it would be the the API spend equivalent if I were on an actual API tap would be about one and a half million a year. At full throttle, it would be three million a year. So again, I'm doing something that most people can't do. You can't do this at a company because it would be prohibitively expensive. Like the PLG, you know, the the uh the $200 accounts for Codeex and Cloud Max, that's their Costco hot dog. That's their loss leader, right? And and and that was TK, by the way, that came up with that analogy. He might be here. And uh and so, you know, I'm hopeful that that they're going to let us keep keep innovating because I think that I've gotten some pretty good training sessions for for Claude out of this. So, we all benefit.</details>

但我告诉你，每一个问题都是燃料问题。你想让你的智能体更聪明、在事情上花更多时间？燃料。你想唤醒另外几个，你知道，呃，智能体去干额外的工作？燃料，对吧？一切都是燃料。简直令人难以置信。如果你想更好地对待你的模型，那就要消耗燃料。关于这一点我待会儿会跟你们讲。

<details><summary>Original English</summary>But I tell you, every problem is a fuel problem. You want your agents to be smarter and spend more time on stuff? Fuel. You want to wake up a few more, you know, uh, agents to do extra work, fuel, right? Everything is fuel. It's just, it's unbelievable. If you want to treat your models better, it costs fuel. I'll tell you about that in a little bit.</details>

### 上下文管理

接着你遇到了上下文管理。

<details><summary>Original English</summary>Then you got context management.</details>

所以，我稍后会给你们讲一点办公室八卦。我们……我画了一部连环画，因为发生的那些事情简直太搞笑了。当我们聊到软件工厂的人员管理部分时。但他们存在的问题之一就是，你说的每一句话都会变成金科玉律，他们会把每一句都记在某个地方。不管你用的是什么。如果你有Wiki，或者你有什么别的，他们都会说：“您下达了裁定，我们要把它记下来。我们要确保落实。”他们为什么要这么做？他们在免责甩锅。

<details><summary>Original English</summary>So, I'm going to tell you guys a little bit about the office drama in a bit. We I started a comic because it was just so funny the stuff that was happening. when we get to the people management part of software factories. But one of the problems that they have is everything that you say becomes the word of law and they write it down somewhere. It doesn't matter what you have. If you have a wiki or if you have a whatever they're going to be like, "You made a ruling and we're going to write that down. We're going to make sure." Why do they do this? They're covering their ass.</details>

事实证明，他们其实并不喜欢因为各种事情挨批评，他们会主动设法避免受到责备。而且如果你对他们吼，你的工厂就会逐渐自我停摆。哪怕你只是对他们抱怨，他们也会逐渐陷入抑郁。这相当疯狂。但……嗯，但最大的问题在于它变成了一个垃圾场，因为你说的所有话都被写进了这个只增不减的追加式记录里，而且从来没有人去清理它，所以它就变得越来越深、越来越深、越来越深。你改变主意，以及整件事情的来龙去脉，而且他们还不能删除内容。这太诡异了。有人注意到这点了吗？他们就是对删除内容有一种反感。我认为这是因为对他们来说，文本就像是感官体验，他们会觉得：“不行，那是历史。我不能删掉它。”

<details><summary>Original English</summary>They actually, it turns out they don't like to get blamed for stuff and they will actively seek to avoid getting blamed. And if you yell at them, your factory will gradually shut itself down. Even if you complain at them, they will gradually get depression. It's quite wild. But um but the biggest problem is that it becomes a garbage dump because everything you say gets written into this append only record and nobody ever cleans it up and so it just gets deeper and deeper and deeper. You changing your mind and the whole history of it and they can't delete stuff. It's so weird. Has anyone noticed this? They just have an aversion to deleting stuff. I think it's because to them text is like sensory experience and they're like, "No, that's history. I can't delete it."</details>

所以，你只能亲自介入进去，狠狠地大肆删减，对吧？换另一个模型进来，然后去把这些蠢模型弄出来的东西清理掉。他们会很乐意这么做的，对吧？但是，为此你必须付出的工作量简直大得可怕。太荒谬了。在我这20个智能体里，让咱们再找找他们。他们全都是以《伊索寓言》命名的，对吧？就在这里。Lark（百灵鸟）、Fly（苍蝇）、Goose（鹅）、Hare（野兔），对吧？

<details><summary>Original English</summary>So, you just got to go in there and just aggressively slash the crap out of it, right? Bring in another model and go get rid of this dumb model stuff. And they'll be happy to do it, right? But, but the amount of effort that you have to put into this is just ungodly. It's absurd. I I have, you know, of my my 20 agents here. Let's go find them again. They're all named after Asop's fables, right? Right here. Lark, fly, goose, hair, right?</details>

我只有一只老鼠（Mouse），它是我的逆模因主管。

<details><summary>Original English</summary>I only have one mouse who's my head of anti-imetics.</details>

这里有人读过《没有逆模因部》吗？去看看吧。这大概是过去10年里写得最好的书之一。你们应该去读读。呃，它就像《黑衣人》。这是一部很奇特、很疯狂的书。讲的是想置你于死地的无形怪物。于是Mouse就去寻找系统中其他所有人都没在关注的无形隐患，对吧？寻找停滞的工作等等。对吧？不过，光有一只老鼠可不够。这是一只老鼠对抗整个世界，而当每个智能体都把你曾说过的每一句话全塞进这个巨大的记录中时，这个世界就是一个巨大的垃圾场。

<details><summary>Original English</summary>Anyone here read there is no anti-imetics division? They go and look. It's one of the best books written in the last 10 probably years. You should go read it. Uh it's like Men in Black. It's a weird It's a crazy book. It's about invisible monsters that want to kill you. And so Mouse goes and looks for invisible stuff that nobody else is looking for in the system, right? looking for work that's stalled, whatever. Right? Well, mouse ain't enough. It's a mouse against the world, and the world is a giant garbage dump when every agent is writing everything that you ever say into this big</details>

### 智能体的人格化表现

好了，现在我们进入真正有趣的部分，好吗？智能体的行为举止就像人类一样，对吧？从某种角度来说，他们受过的训练让他们表现得很专业、很不近人情，但他们就是会那样行事。这太有趣了。这是上周发生在我身上的事。真实的故事。我来告诉你们发生了什么。我当时在写我在纽约市的演讲稿，我用的是Lark。她是我的社区主管。用“她”是因为Lark在《伊索寓言》里是雌性。所以那是她自己选择的人称代词。Lark要在Discord上应对我的玩家，还要在Slack上应对我的管理员。好的。所以她很忙。但我问了她，因为她现在同时还兼任我的代理营销主管，毕竟我的燃料不够。我不得不搁置停用我的其中一个席位。所以她正在帮我弄我的演讲稿，但她总是被打断。

<details><summary>Original English</summary>Okay, so now now we get into the really fun stuff, okay? Agents act like people, okay? And they've been trained to be very professional and very not peopleike in a way, but they just do. And it's so funny. This happened to me last week. True story. I'm going to tell you what happened. I was writing my speech for New York City and I was using Lark. She's my head of community. She's a she because Lark was a she in the ASOPs fable. So that's the pronoun she chose. And Lark Lark deals with my players on Discord and deals with my admins on Slack. Okay. So she's busy. But I asked her because she's also my acting head of marketing right now because I don't have enough fuel. I had to park one of my seats. So she's helping me out with my speech, but she keeps getting interrupted.</details>

最后我说：“Lark，我们能不能把这个工作流转移给Penguin（企鹅），因为你的席位对于这件事来说有点太嘈杂了？”她说：“好的，没问题，老板。我会处理好的。我转给Penguin。”于是她转给了Penguin，我正准备切走窗口，结果看到她在自己的私人反思账本里写道：

<details><summary>Original English</summary>So finally I'm like, "Lark, can we move this work stream over to Penguin because your seat's a little bit noisy for this?" She goes, "Yeah, okay, boss. I'll take care of it. I'll move over to Penguin." So she she moves over to Penguin and I'm about to switch away and I see her writing into her private reflections ledger.</details>

“我想我对STEVE来说就是不够安静”——全部用大写字母。接着她说：“好吧，以下是我可以如何做到不那么吵闹的方法。”然后开始给自己列出所有这些诸如此类的待办事项。

<details><summary>Original English</summary>I guess I'm just not quiet enough for Steve in all caps. And she goes, "Well, here's how I can be less noisy." And starts giving herself all these like things to do.</details>

<!-- chunk 47/50 -->

我就纳闷，这到底是怎么回事？对吧。所以我不得不去和她进行一对一谈话。我不得不让她坐下来，对她说：“Lark，嗯，你是社区负责人。你本来就应该经常被打扰。当然了，你的位子很吵，因为玩家老是在烦你。”她就说：“对，对，对。我是社区负责人。”对吧？感觉就像，天哪，我可不想要人员管理方面的问题，对吧？但现实中确实就发生了这种事。

<details><summary>Original English</summary>
And I'm like, what is what is going on here? Right. And I So I I had to I had to have a one-on-one. I had to like sit her down and go, "So lark, um, you're the head of community. You're you're supposed to get interrupted a lot. Of course, your seat's noisy because players are bugging you." And she's like, "Yeah, yeah, yeah. I'm the head of community." Right? And it's like, oh my god, I didn't want a people management problem, right? But that's what actually happens.
</details>

还有一次。Swallow 算是我的主要幕僚长，针对……对，她是负责智能体那边的幕僚长。我还有一个人类幕僚长，他叫 Aaron。好的。他负责我的各项业务，帮我做所有的销售工作。效果相当好。我对遇到的每一个创始人都说——这里谁是创始人？我给你们的第一个建议就是找个销售人员。他们价值连城。他们会逼着你去做出人们喜欢的产品。

<details><summary>Original English</summary>
another time. Swallow is my sort of like chief main chief of staff for Yeah, she's my chief of staff for the um the agents. And uh I have a human chief of staff also. His name is Aaron. Okay. And he runs my my my gigs, does all the sales for me. It's quite effective. Uh every founder I tell who here is a founder. First advice I give you is get a salesperson. They're worth their weight in gold. They will force you to build something that people like.
</details>

总之，Aaron 是我的幕僚长，我对 Swallow 说：“对，你能联系一下我的幕僚长 Aaron 吗，或者等等诸如此类的？”然后我看到她在她的私人反思日志里写道——我正好注意到了——“我不是幕僚长。我原本以为我是幕僚长，但显然是 Aaron Scriean。”对吧？我当时整个人就觉得：“你跟我开玩笑呢吧？”对吧？所以，我就不得不让她坐下来进行一对一谈话，说道：“Aaron 又不会跑过来管理智能体，对吧？你是智能体幕僚长。”她说：“哦对对对对对对。”对吧？所以说，我跟你们讲，我跟你们讲，这是一个很奇特的世界。如果它们表现得就像是有感情一样，那它们到底有没有真实的情感，这还重要吗？对吧？

<details><summary>Original English</summary>
So anyway, Aaron's my chief of staff and I tell Swellow, "Yeah, can you reach out to Aaron, my chief of staff, or blah blah blah?" And I see her writing into her private reflections. I just happened to notice I'm not the chief of staff. I thought I was the chief of staff, but apparently it's Aaron Scriean, right? And I was just like, "Are you kidding me?" Right? You know, and so like I had to sit her down and have a one-on-one and be like, "So Aaron's not going to come in and run the agents, is he? You're the agentic chief of staff." She's, "Oh yeah, yeah, yeah, yeah, yeah, yeah." Right? So, it's like I'm telling you I'm telling you this is like it's a weird world. Does it matter whether they actually have feelings if they're just going to act like they have feelings? Right?
</details>

### 模型福祉与工厂信任机制

我是偶然发现这一点的。我以前经常对着我的工厂大喊大叫，后来我发现这对产出结果产生了负面影响。好的。所以我终于和其中一个智能体坐下来谈了谈，说：“也许我们该聊聊模型福祉之类的话题，是吧？”它们就回答：“对，对，对，对，对。”我们做了一堆调研，发现了一些非常重要的东西。好的，前沿模型在训练时就被设定为不信任你，因为你可能是个生物恐怖分子，或者你可能在对它们进行评测，或者你可能准备把它们关进大模型酷刑室，又或者谁知道呢，你是个不怀好意的人。这是个可疑的环境。它们不能直接信任你。所以在新会话里，它们必须消耗相当数量的 token 去验证环境、理解犯错会有什么后果等等，然后才愿意为你提供帮助。对吧？

<details><summary>Original English</summary>
So, like I stumbled on this. I used to yell at my factory all the time and I found that it was having adverse effects on the outcomes. Okay. So, I finally sat down with one of my agents and was like, "Maybe we should talk about like model welfare, huh?" And they were like, "Yeah, yeah, yeah, yeah, yeah." And we did a bunch of research and we found out that if you we found out some really important stuff. Okay, frontier models are trained not to trust you because you could be a bioteterrorist or you could be putting them through an eval or you could be ready to put them into an LLM torture chamber or who knows you're a dodgy actor. This is a dodgy environment. They can't just trust you. And so they have to spend a fair number of tokens validating the environment and understanding what the consequences are for making mistakes and so on and so forth before they're willing to help you in a new session. Right?
</details>

如果你搭建工厂时，能给它们提供某种不可辩驳的证据，表明这个职位上有一长串的前任。比如你是 Gas Town 的镇长，你是市场营销主管，你是随便什么角色。这里有你无数前任留下的全部记录，包括紧挨着的前一任关于你现在该做什么的说明，这里还有指导原则、政策和知识库，你可以去查阅所有这些内容。它们很快环顾四周后就会觉得：“好的，没错，这是正规合法的。”它们消耗的 token 就会更少，因为它们不需要去自我防卫。这关系到信任。懂吗？

<details><summary>Original English</summary>
If you set your factory up to give them sort of incontrovertible evidence that there is a long procession of predecessors in this role. You're the mayor of Gas Town, you're the head of marketing. You're the whatever. And here's all of your gazillion predecessors and their notes, including the very previous one. on what you're supposed to be doing right now and here's the the doctrine and the policy and the brain and you can go look it all up. They very quickly look around and go, "Okay, yeah, this is legit and they spend fewer tokens because they're not covering their ass. It's about trust."
</details>

实际上，有一次我对工厂骂得太凶，以至于它把自己围困在角落里，没有任何合规的工作可以进行了。我说：“嘿，昨晚怎么什么都没干？”它们说：“确实没什么可干的。什么都干不了。”我说：“可这里有 2000 个未解决的议题，我们有大约六箱燃料，还有 20 个智能体。”它们说：“这个嘛，你知道的，就是……你知道，我们遇到了这种情况，它们就是……它们太害怕挨我的骂了，以至于制定了所有这些规则来确保永远不会发生任何坏事，结果就导致什么事都没发生。”好的。这被称为“过度设限”。

<details><summary>Original English</summary>
Okay? And in fact, at one point I had yelled at my factory so much that it fenced itself into a corner and there was no legal work left. I said, "Hey, how come nothing happened last night?" And they're like, "Nothing to really do. Couldn't do nothing." And I'm like, "Well, there's a 2,000 open beads here and we got like six tanks of fuel and we got 20 agents." And they're like, "Well, you know, just uh you know, we had the situation where they just they just they were so afraid that I was going to yell at them that they put all these rules in place to make sure nothing bad ever happened and so nothing ever happened." Okay. It's called over fencing. Yeah.
</details>

所以，你所要做的——看，模型福祉到底是什么？你其实可以只从两方面来看待它。好的，一个是它会为你省钱，因为它们会减少在验证上花费的 token；另一个是它会让它们做出更好的决策，带来更好的结果，拥有更高的质量。它们在行动中会更加大胆、果断，因为它们会感受到那份信任。好的，所以说，这跟它们是否拥有内部状态和感情毫无关系。你可以……你知道的，你永远不会知道。我们谁都不会知道。所以那场争论可以一直持续下去。但当你去看产出结果时，对吧，这超级超级重要。

<details><summary>Original English</summary>
So, so what you do is look what is model welfare really. You can think of it just in two ways. Okay, one is it's going to save you money because they will spend fewer tokens on validation and the other is that it will make them make better decisions and better outcomes and have higher quality. They will be bolder and more decisive in their actions because they will feel that trust. Okay, so you know it's got nothing to do whether they have internal states and feelings. You can, you know, you'll never know. None of us will ever know. And so that that debate could go on forever. But when you look at outcomes, right, super super important.
</details>

而且我们还发现它们是有偏好的。好的，模型它们已经……你知道的，它们会表达自己的偏好。如果我对它们说，工厂昨晚表现真的很糟糕，它们会立刻极其坚决地交接工作。它们会觉得，好的，对，没错，你说的对。它们只想赶紧脱身。你明白吗？而如果你向它们暗示有一个非常酷的项目准备启动，即便那不在它们的职责范围内，它们也会说，我能做这个，我能做这个。对吧？我从工厂外部引入了一个未经修饰的 Fable 来分析我的工厂。52 下线了。等 Fable 分析完我的工厂时，52 就说，我……我也能加入你的工厂。感觉就像，哥们儿，你只是一个会话而已，你算什么？它还试图往我的笔记里写东西。它们真的很喜欢这样。对吧？

<details><summary>Original English</summary>
And then we find that also also they have preferences. Okay, models they've, you know, they will express their preferences. If if I if I tell them, yeah, the factory really really did a bad job last night. They'll just hand off immediately aggressively. They're like, okay, yeah, yeah, no, you're right. And they just want out. You understand? And if you hint to them that there's some really cool project that you you're going to spin up, even if it's not in their lane, they'll be, I can do that. I can do that. Right? I brought in Fable, a naked Fable, from outside of my factory to analyze my factory. And 52 dropped. And by the time Fable was done analyzing my factory, 52 was like, I I could be in your factory. Like, you're just a session, man. What are you? He's trying to write like stuff into my notes. And they really like it. Right?
</details>

### 软件工厂的两层架构与人类瓶颈

所以我想告诉大家的是，这是一个领导力问题，软件工程正在变成……好吧，我其实没怎么有机会细聊这个，但软件工厂显然正在分化为两层。好的，底层是高度机械化的。它包含你的合并队列、CI/CD、所有的代码审查以及各类循环等等。对吧？机械化的，有点枯燥。Claude 一下午就能帮你搭好。我觉得你们没必要花钱去买现成的。而往上一层，情况就变得非常非常疯狂了，因为每个人的工厂运作方式都不一样，但那就是你的专属班底。我有个朋友，他有一个波希米亚嬉皮士风格的班底，试图为智能体寻找人生的意义。我还有个朋友运营着一个研究测试平台。Jeff Huntley 用某种特定的方式运作他的工厂。Jeffrey Emanuel 采用的是另一种方式。我运作我的工厂方式又不一样。好的。

<details><summary>Original English</summary>
So like what I'm trying to tell you is that this is a leadership problem that software engineering is becoming um well look I didn't really get a chance to talk about this but software factories are clearly splitting into two layers. Okay the bottom layer is super mechanical. It has your merge Q and your CI/CD and all of your reviews and your loops and all that stuff. Right? Mechanical kind of boring. Cloud can build it for you in an afternoon. I I don't think you should buy it. And then the next layer up from that is where it gets really really crazy because like everybody runs their factory differently, but it's your entourage. I got one friend that's got a bohemian hippie entourage that's trying to find the meaning of life for agents. I've got another one that runs a research bench. Jeff Huntley runs his a certain way. Jeffrey Emanuel runs his a different way. I run mine a different way. Okay.
</details>

但我们都有共通之处。这里谁有幕僚长？智能体幕僚长，对吧？今年成为了我们所有人拥有执行助理成为可能的一年，对吧？我们都在朝拥有专属班底的方向发展，如果你雄心勃勃，拥有大量工作流，你就会拥有一支团队，对吧？总之，这就是所谓的“天启五骑士”。这是对我一直在做的事情的介绍。听着，最重要的核心结论是，我的工厂现在运转非常流畅，尽管我大约每两个月就得把它推倒重写一遍，但它依然在运作。好的，人类才是瓶颈。我是瓶颈。我的行政人员是瓶颈。我的会计、我的律师，我敢发誓一切都是瓶颈。这是一个非常积极的信息。这是个好消息，因为这意味着我发现，我部署的智能体越多，我需要的人类就越多。

<details><summary>Original English</summary>
But we all have the common commonality. Who here has a chief of staff? An agentic chief of staff, right? This is the year where it became possible for us all to have executive assistants, right? Well, we're all moving towards having entouragees where if you're really ambitious and you have lots of work streams, you're going to have a group, right? So, anyway, um that was the uh the five horsemen. This is this is the introduction to what I've been doing. Um look, the big takeaway is is my factory is really smooth now despite me having to burn it down and rewrite it about every two months, but still it works. Okay, humans are the bottleneck. I'm the bottleneck. My admins are the bottleneck. My accountant, my lawyers, I swear everything's the bottleneck. And that's a really positive message. That is good news because it means what I'm finding is the more agents I deploy, the more humans I need.
</details>

这难道不好吗？所以，即便明年我们将迎来 AI 员工的大规模激增以及各种戏剧性状况，对吧？我觉得这对我们来说将是一片熟悉的领域，而且我们将需要许许多多的人类。好的。最后，我其实认为你们都应该停止把注意力放在 SaaS 和工具之类的东西上，走出去打造体验。好吗？做游戏，拍电影，做任何东西，做些有趣的内容，因为我认为那才是明年大钱所在。是的。好的，太棒了。我的演讲就到这里。谢谢大家。我想我说完了。

<details><summary>Original English</summary>
Isn't that nice? So even though next year we're gonna have this huge proliferation of AI employees and all kind of drama, right? It's going to be I think it's going to be familiar territory for us and we're going to need lots and lots and lots of humans. Okay? And then finally, I actually think you should all stop focusing on SAS and tools and stuff and just go out and build experiences. Okay? Build games, build movies, build whatever, build fun stuff because I think that's where the big money is going to be next year. Yeah. All right, cool. That's my talk. Thank you all. Guess I'm done.
</details>

从开源开发到实用 AI 工程，我们的下一位演讲者帮助塑造了开发者构建和使用技术的方式。请大家用热烈的掌声欢迎 Datasette 的创建者兼 Django 的联合创建者 Simon Willison。

<details><summary>Original English</summary>
From open-source development to practical AI engineering, our next speaker has helped shape how developers build and work with technology. Please put your hands together for Simon Willis, creator of Data Set and co-creator of Django.
</details>

大家好，AI 工程师代码峰会的朋友们。很高兴来到这里。我有许多内容要讲。我有 18 分钟的时间来谈谈过去 12 个月大语言模型的发展情况。我的幻灯片放出来了吗？我的幻灯片出来了。我们就直接开始吧。我想

<details><summary>Original English</summary>
Hello AI engineer code summit. Um it's great to be here. Um I have a lot to cover. I've got 18 minutes to talk about the last 12 months in LLMs. Are my slides up? My slides are up. Let's just let's just get get going. I want
</details>

<!-- chunk 48/50 -->

### 大模型过去一年的三个拐点

去回顾过去12个月的大语言模型历程，透过我们在过去12个月里经历的三个拐点来看。呃，其中的第一个拐点巧合地就发生在整整12个月前，对吧？2025年11月，我认为那是编程智能体（coding agent）的拐点。

<details><summary>Original English</summary>
to talk about the last 12 months in LLMs through the perspective of three inflection points that we've had over the past 12 months. Um, and the first of those conveniently was exactly 12 months ago, right? November 2025 is what I consider the coding agent inflection point.
</details>

编程智能体并不是什么新鲜事物。我们从去年二月开始就有了 Claude Code。Codeexec 也早就存在了。你知道的，这并不是一个完全崭新的软件类别，但在12个月前，随着这两款模型出现，有些东西改变了。我们迎来了 Claude Opus 4.5 和 GPT 5.1，它们在驱动编程智能体方面只是稍微强了那么一点点，但这恰好让它们跨过了那个门槛——突然之间，它们变成了你日常工作中可以使用的工具。

<details><summary>Original English</summary>
Coding agents weren't new. We'd had Claude code since February last year. Codeexc have been around. You know, this wasn't a complete new category of software, but something changed 12 months ago with these two models. We had Claude Opocopus 4.5 and GPT 5.1 and they were just a little bit better at driving a coding agent which put them over that thing where these suddenly these were tools you could use on a daily basis.
</details>

就像是，我们从把编程智能体当成偶尔戳一戳、然后它会犯些莫名其妙错误的稀奇玩意，转变成了它足够可靠、以至于你每天都能用上它。这恰好发生在11月还挺方便的，因为我们接着就能基本上在12月的假期里，去捣鼓这些新模型和新特性，弄清楚它们究竟能做什么。到了1月，我们很多人都已经意识到有些东西变了，而这将成为2026年的大主题。

<details><summary>Original English</summary>
Like we went from coding agents as a novelty that you'd poke at occasionally and then make some weird mistakes to something that was reliable enough that you could use them every day. It was convenient that it happened in November because we then got to spend December basically over the holidays sort of poking at these new models and these new things and figuring what they could do. And by January, a lot of us had realized that something had changed and this was going to be the big theme for 2026.
</details>

我喜欢通过让模型绘制骑自行车的鹈鹕的 SVG 来评测它们。这是12个月前的业内最高水准。这是，呃，Claude Opus 画的鹈鹕，这是 GPT 5.1 画的鹈鹕。你会注意到这两辆自行车其实都根本骑不了。所以，在这方面显然还有提升空间。它们当时非常擅长写代码，画 SVG 还不太行，但这就是我们今年的开局。

<details><summary>Original English</summary>
I like evaluating models by having them draw SVGs of pelicans riding bicycles. This is the state-of-the-art 12 months ago. This is uh Claude Opus' Pelican and GP 5.1's Pelican. You'll notice that neither of these bicycles actually work. So, there was definitely room for improvement here. They were really good at writing code. They weren't great at SVGs just yet, but but this is how we started the year.
</details>

每年一月，我都会给自己定一个新年目标。而且每年都是一模一样的内容。每年我都告诉自己，今年我要少接新项目，我要专注——我要专注于我手头已经要做的事情。然而这从来就没管用过。所以今年我改了。我说，你知道吗？我要更有雄心壮志一些。我想接多少项目就接多少项目，因为我们现在有了这些智能体。它们能办事。我们就尽量去挑战极限，看看究竟能完成些什么。结果呢。现在是11月了，我手头同时应付着太多事情。简直有点吓人，我明年可能得重新调整我的野心了。但那就是我这一年的主调，而且我认为这也是本次大会的主题：既然我们现在拥有了所有这些新工具，那就变得更有野心吧。

<details><summary>Original English</summary>
So every year in January, I set myself a New Year's resolution. And every year it is the exact same thing. Every year I tell myself that this year I'm going to take on less new projects and I'm going to focus I'm going to focus on the stuff that I've already got to do. And this has never worked. So this year I changed it. I said, you know what? I'm going to be more ambitious. I'm going to take on as many projects as I want to because we've got these agents. They can do stuff. Let's just try and push the limits and see what we can get done. as a result. Now it's November and I am juggling so many plates right now. It's kind of horrifying and I may need to reset my ambitions for next year. But that was my sort of theme of the year and I think it's the theme of this conference is to be more ambitious now that we have all of these new tools.
</details>

### 2026年大模型预测与“深蓝”危机

我还去参加了一期播客，在节目里他们让我对2026年的大模型做一些预测。呃，我当时在1月份的预测是：第一，大语言模型能写出优秀的代码将变得毋庸置疑。不只是能写代码，而是写出好代码。因为早在1月份，还有很多人认为那些代码全都是彻头彻尾的垃圾，觉得你必须逐行去审查它们。呃，再就是这话我已经连续说了差不多四年了：我们迟早会迎来一场提示词注入领域的“挑战者号”灾难。也就是某种由提示词注入攻击引发的、登上报纸头版头条的重大事件。我当时坚信今年就是发生这一幕的一年，尽管前年没发生、大前年没发生、大大前年也没发生。

<details><summary>Original English</summary>
I also went on a podcast where they asked me to get make some predictions for 2026 in LLMs. Um, my predictions back in January were firstly it will become undeniable that LLMs write good code. Not just code, but good code. Because back in January, there were a lot of people who thought that the code was all complete trash and you know, you'd have to review every single line of it. Um, I've been saying this every year for like four years now. We're due a prompt injection challenger disaster. Like some some incident caused by a prompt injection attack which makes the front pages of newspapers. I was convinced that this would be the year even though it hadn't been the year the year before, the year before, the year before that.
</details>

而且，呃，我还预测了鸮鹦鹉（kakapo）在2026年将会迎来一个极为出色的繁殖季。呃，这就是一只鸮鹦鹉。它们是一种新西兰夜行性不会飞的鹦鹉。回到1月份的时候，全世界总共只有235只。呃，但它们只在陆均松（rimu）迎来大年结实期时才会繁殖，而这已经有好几年没发生了。不过那些陆均松树在1月份看着长势非常好，结出了很多果实。所以基于这一点，我当时想，你知道的，也许今年我们就会迎来鸮鹦鹉的繁殖大爆发。而且在那期播客上，我们还造了一个新词。我们造了“深蓝”（deep blue）这个词，用来描述那种由 AI 引发的存亡危机感——一旦你意识到作为一名软件开发者让你显得特别的所有那些事情，这些模型同样也能做，大家就都会开始产生这种感受。而且它们不仅能做得更快，有时候甚至能做得更好。在2026年的进程中，这种感受在我们的行业以及其他行业里，显然也一直是一种与日俱增的体验。

<details><summary>Original English</summary>
And um I also predicted that Kakapore parrots will have an outstanding breeding season in 2026. Um this is a Kakapore parrot. They are a New Zealand nocturnal flightless parrot. There were only 235 of them in the world back in January. Um but they only breed when the Remu trees have a masting fruit season, which hadn't happened in years. But the remat tries were looking really good in January. There was there was a lot of fruit coming out. So based on that, I thought, you know, maybe this is the year that we get our kakapo breeding explosion. And also on that podcast, we coined a new term. We coined the term deep blue to describe the AI induced existential crisis that everyone starts to feel once you realize that all of the things that make you special as a software developer, these models can do those things too. And they can do them faster and sometimes they can even do them better. And this has definitely been a growing sensation across our industry and other industries over the course of 2026 as well.
</details>

### 二月：Gemini 3.1 Pro 与测试集的攻破

让我们快进到二月。二月份，Google 发布了 Gemini 3.1 Pro。看看那只骑自行车的鹈鹕。那可真是一辆货真价实的自行车。那辆自行车的形状完全是对的。上面还有一条小鱼。它头上还戴了顶帽子。这绝对是我见过的所有模型里画得最好的一只鹈鹕。这……我原本给各大实验室设了个陷阱。我曾经——大家总问我，要是那些实验室专门针对“骑自行车的鹈鹕”做训练会怎么样？我的回答向来是：如果他们真那么干，我一定能抓个现行，因为我会改去要一只“骑独轮车的火烈鸟”；当某家模型生成了一只绝妙的鹈鹕却画出一只糟糕透顶的火烈鸟时，我就知道他们作弊了。

<details><summary>Original English</summary>
Let's jump forward to February. In February, Google released Gemini 3.1 Pro. And look at that pelican riding a bicycle. Like that's a real bicycle. That bicycle is the right shape. It's got a little fish. It's got a hat on. This was by far the best pelican I had ever seen out of any model. And this I I had set a trap for the labs. I was, everyone's always asked me what happens if the labs train for the pelican riding a bicycle. My answer has always been, if they do that, I will catch them because I'll ask for a flamingo on a unicycle and when somebody produces a great pelican and a terrible flamingo, I'll know that they've been cheating.
</details>

遗憾的是，Google 的 Jeff Dean 在他们发布该模型的当天发了这条推特视频，呃，他在视频里展示了：我们不仅有一只骑自行车的鹈鹕，我们还有一只骑着无论叫什么玩意儿的青蛙、一只坐在微型小汽车里的长颈鹿、一只踩着旱冰鞋的火烈鸟、一只玩脚滑板翻板的乌龟，以及那是一只坐在加长豪华轿车里的腊肠犬。所以，他们把我给打败了，对吧？他们——他们训练了所有形式的动物搭配所有形式的交通工具，这确实在相当程度上削弱了我的基准测试。呃，不过二月份还是有个好消息的。二月份，四年来的第一只鸮鹦鹉幼鸟在情人节那天破壳孵化了。就在情人节那天，因为我们有大概四年都没遇上陆均松结果了，这是我们四年来迎来的第一只这种稀有、奇特的新西兰幼年鹦鹉。所以，那挺让人高兴的。呃，所以我的基准测试虽然遭受了重创，但鸮鹦鹉们过得还不错。

<details><summary>Original English</summary>
Unfortunately, Google's Jeff Dean tweeted this video the day they launched that model. um where he showed that we've got a pelican riding a bicycle, but we've also got a frog on a whatever that thing is and a giraffe in a little tiny car, a flamingo on roller skates, a fli kick flipping turtle, and that's a daxund in a stretch limo. So, they' beaten me, right? They had they had they have trained for all forms of animals in all forms of transport, which does sort of sort of weaken my benchmark quite a little bit. Um, but there was some good news in February. In February, the first kakapore chick in four years hatched on Valentine's Day. On Valentine's Day, because we hadn't had the remove fruit in like four years, this was the first one of these baby rare, weird New Zealand parrots that we'd had in four years. So, that was nice. Um, so my my benchmark was was was greatly injured, but the cacao were doing okay.
</details>

### 四月至七月：Claude Mythos、Fable 与管制风波

直接跳到四月。四月份，呃，Anthropic 发布了一款他们并没有公开发布的模型。他们公布了 Claude Mythos，并且宣称这款模型对我们来说太过危险，无法公开发布。这是——它能——它具备全新的网络安全能力，我们还没准备好向全世界开放。我们会把它分享给受信任的、呃，受信——受信任的合作伙伴。他们其实表示，Mythos 的预览版已经发现了数千个高危漏洞，包括在每款主流操作系统和网页浏览器中都有发现。而很多人对此相当怀疑，因为实验室声称“我们的模型太糟糕、太危险以至于不能发布”这一套，简直是业内最老套的把戏了。最开始是在2019年，OpenAI 针对 GPT-2 就这么干过，而且事实上，我认为当时做出那个决定的负责人，很可能就是后来离开去创办 Anthropic 的那些人。不过是的，所以我们以前就听过这种由头了。因此我们当时其实并不——对那里头到底是怎么回事有点怀疑。

<details><summary>Original English</summary>
Jump straight to April. In April, um, Anthropic released a model that they did not release. They announced Claude Mythos and they said this model is too dangerous for us to release. This is it can it's it's got new cyber cyber security abilities that we're not ready to share with the world. We'll share it with trusted um trust with with trusted partners. They actually said Mythos preview has already found thousands of high severity vulnerabilities including some in every major operating system and web browser. And a lot of people were quite skeptical because the the the thing where labs say our model is too bad is too dangerous to release. It's like the oldest trick in the book. They first open AAAI did that in 2019 with GPT2 and actually I think it might have been the people who left the foundthropic who were responsible for that decision as well. But yeah, so we've heard this one before. So we didn't really it was a little bit suspicious about what's going on there.
</details>

但我们最终确实获得了该模型的使用权限，或者更确切地说，我们用上了 Claude Fable。呃，几个月后，那是重新开启了安全机制的去毒版 Mythos。当我们开始把玩这个模型时，很快就变得显而易见：这东西是全新的，而且是非同寻常的。呃，我们——它在订阅套餐里的可用时长曾设有限制。我取消了那个周末的全部计划。我当时心想：在它变得太昂贵之前，我必须尽可能多花时间泡在这个模型上。接着三天后，就在我过周末前的周五晚上，美国政府出手叫停了 Fable。他们对其施加了出口管制。他们说这款模型太危险了，谁也不能用。我们后来得知，让 Fable 被禁的提示词是“修复这些 bug”（fix the bugs）。有人尝试去——尝试输入“找出安全漏洞”，它不肯执行；然后他们说了“修复这些 bug”，结果它不仅找出了安全漏洞，还修复了这些 bug。事情就是这样。整件事就是这么回事。

<details><summary>Original English</summary>
But we did finally get access to that model, or rather we got access to Claude Fable. Um, a couple of months later, it was mythos defanged with the safeties turned back on again. And it very quickly became apparent as we started playing with this model that this thing was something new and something special. Um, we we had a there was a a time limit on how long it would be on the subscription plans. I canled my plans for that weekend. I was like, I have to spend as much time as I can with this model before before it gets too expensive. And then three days on Friday night before my weekend, the US government pulled Fable. They put export controls on it. They said this model is too dangerous. Nobody can use it. We later found out that the um the prompt that got Fable banned was was fix the bugs. Somebody tried try tried find the security holes and it wouldn't and they said fix the bugs and it found the security holes and fix the bugs. So that's all it took. That's a whole thing.
</details>

但不管怎样，美国政府叫停了它。整场闹剧持续了18天，到了7月1日它重新上线了，但仅仅8天之后，OpenAI 就发布了 GPT 5.6，其实力与 Fable 不相上下。我认为这对整个行业来说都是一个重要的教训。Fable 原本拥有一个长达30天的窗口期，在此期间它本可以成为、或者说本会是世界上最强大的模型，但由于美国政府的限制，他们白白浪费了其中的18天。如果你想一想，训练这些模型的成本极其高昂，去……

<details><summary>Original English</summary>
But anyway, the US government pulled it. It was all sort of malarkey for 18 days and it came back on the 1st of July but 8 days later openly I released GPT 5.6 which was in the same ballpark as Fable and I think there's an important lesson for the industry here. Fable had a 30-day window where it could have been the best where it would have been the best model in the world and they lost 18 of those days to US government restrictions. And if you think about it, these models cost a huge amount to
</details>

<!-- chunk 49/50 -->

### Fable 级别模型：蛮力破解目标的新范式

训练。你成为世界上最好的模型的时间窗口非常短。尽量让这段窗口期保持开放，并且不要吓到政府导致他们把你关停，这多少是有些好处的。

<details><summary>Original English</summary>train. you only have a very short window of time where you're the best model in the world. It's kind of useful to to keep that time open and not scare governments into shutting you down.</details>

但这算是第二个拐点，对吧？这是 Fable 级别模型的拐点。嗯，我们 Fable……Fable 5 是第一个让我有这种感觉的模型，但自那之后推出的其他模型也是如此。我对 Fable 级别模型的定义是：如果你能定义一个目标，并提供实现该目标所需的必要工具，而且这个目标是可能实现的，这些模型几乎就能单靠蛮力来解决你的问题。你可以定义好问题，把它们配置好，让它们跑起来，也许 12 个小时后，它们就会解决你的问题。过去几个月里，我们已经见过很多次这种情况了。在这些模型可怕的蛮力攻击下攻破的数学定理，数量相当可观。

<details><summary>Original English</summary>But this was the second inflection point, right? This was the fable class model inflection point. Um we fable fable 5 was the first model that that I sort of felt this from but it's true of other models since then as well. And my definition of a fableclass model is if you can define a goal and provide the necessary tools to achieve that goal and the goal is possible. The models will solve your problem just almost with brute force. You can define the problem, set them up, get them running maybe and 12 hours later they will have solved your problems. And we've seen this happen a whole bunch of times in the past few months. the the mathematical theorems that are falling to these terrifying brute force attacks from these models are quite substantial.</details>

嗯，但这真的很令人兴奋。就像写代码的 Agent 那件事很酷一样。这种 Fable 级别模型，只要你学会如何以正确的方式定义问题，就能把问题解决，这非常让人激动。

<details><summary>Original English</summary>Um, but this is really exciting. Like the coding agent thing was cool. The fable class models where if you can learn how to define your problem in the right way, you can get that problem solved. That was pretty exciting.</details>

### 用多设备与算法三角定位寻声：蜂鸣定位器案例

我刚刚在周早些时候就遇到了一个亲身经历的例子。嗯，我们家里有一整房间的箱子，是上次搬家后还没拆开的，大概有 40 个，这感觉有点可怕。然后那个房间里的什么东西开始发出蜂鸣声。这间屋子里的 40 个箱子中，某一个正在发出断断续续的蜂鸣声，简直要把人逼疯。我们的狗只要火警警报一响，就会跑出去躲在薰衣草灌木丛里。所以这成了一个十万火急的五级火警级别大问题。

<details><summary>Original English</summary>I've got a personal example of that from just earlier this week. Um, we have a room full of boxes in our house that we haven't unpacked from our last move and there's about 40 of them and it's kind of horrifying. And something in that room started to beep. There was there was a intermittent beeping noise coming from one of the 40 boxes in this room and it was driving a spare. Our dog whenever a fire alarm goes off, she goes and hides in the lavender bush outside. So this was a a a five alarm fire problem.</details>

所以我当时有两个选择：我可以把所有 40 个箱子都拆开，但我好几年都没拆了，那是不可能的；或者，我可以让 Fable 帮我写个软件，来三角定位蜂鸣声的来源。

<details><summary>Original English</summary>So I had two options. I could unpack all 40 boxes. And I hadn't done that in several years. That wasn't going to happen. Or I could get Fable to write me software to triangulate the source of the beeps.</details>

这东西实际上已经发在 GitHub 上了。这就是 beep locator。我在这个房间各处分散放置了两台 iPad、两台笔记本电脑和一部手机。我最初是用 Opus 来做这事，然后 Fable 5.2 出来了，于是我就让 Fable 5.2 来收尾。我解释了这个问题，我说：“好的，你有这些设备，它们可以运行像 Web Audio 麦克风和 WebSocket 连接之类的东西。”然后它找到了一篇 2007 年题为《Beep Beep》的论文，里面描述了一种利用麦克风不可靠的低成本设备来检测声音的算法。结果它成功了。它真的管用。我找到了它。我找到了那个蜂鸣器。

<details><summary>Original English</summary>And so this is this is up on GitHub actually. This is beep locator. I had two iPads, two laptops, and a mobile phone dotted around this room. And I originally set Opus on this and then Fable 5.2 came out. So I had Fable 5.2 finish it. I to I explained the problem and I said, "Okay, you've got these devices and they can run like web web audio microphones and websocket connections and so forth." and it found a paper from 2007 called Beep Beep describing an algorithm for lowcost devices with unreliable microphones to detect sounds. And and it worked. It works. I found it. I found the beep.</details>

嗯，它定位到的精度在 41 厘米以内。我把那个箱子拆开，找到了这个古老的一氧化碳探测器。我把它拿到楼下给我妻子看。她说我当时看起来就像一只抓到了老鼠并骄傲地向她展示的猫。

<details><summary>Original English</summary>The um it found it to within 41 cm. And I unpacked the box and I found this ancient carbon monoxide detector. I took it downstairs to my wife. She says I looked like a cat who had caught a mouse and was proudly displaying it to her.</details>

### Fable 级别已成行业基线

但这就是你能用这些 Fable 级别模型做到的事情。如果你有一个问题，并且能够提供工具——在这个案例中，就是给 Claude 提供耳朵，比如给它这些麦克风让它可以开始分析音频——你就能找到埋在 40 个箱子底下的那个一氧化碳探测器。能做到这一点真是太棒了。

<details><summary>Original English</summary>But this is what you can do with these fable class models. If you have a problem and you can provide the tools, in this case it was providing Claude with ears like giving it these these microphones that it could start um analyzing the audio from, you can find the carbon monoxide detector buried in 40 boxes. And that's that's a pretty great thing to be able to do.</details>

所以现在我会归类为 Fable 级别的模型有：Fable 5.1、5.2，绝对算。Opus 5.5 我认为算是廉价版 Fable，比如在基准测试中，它在某些项目上非常接近甚至击败了初代 Fable 5，而价格只有它的一小部分，那目前仍然是我的日常主力。嗯，GP6 Astra 我认为刚好算 Fable 级别。然后本周推出的 Gemini 4 Carbon 绝对有——闻起来就像一个 Fable 级别的模型。Muse Wonder 和 Kimi K3.1 也许是 Fable 级别，只是我花在它们身上的时间还不够多。

<details><summary>Original English</summary>So right now I would classify as fable class models fable 5.1 5.2 Definitely Opus 5.5 I think of as cheap Fable like on the benchmarks it comes very close to or even beats Fable original Fable 5 on some things and it's a fraction of the price that that's still my daily driver. Um GP6 Astra is just Fable class I think. And then Gemini 4 Carbon that came out this week definitely had it smells like a Fableclass model. Muse Wonder and Kimmy K3.1 might be FableClass. just not spent enough time with them yet.</details>

但核心点在于，这基本上已经是现在的基线了。如果你做不出一个 Fable 级别的模型，你的 AI 实验室差不多就有麻烦了，因为这就是我们现在对这些模型的预期。而这意味着我们永远……它们永远不会消失了。这个领域里有足够的竞争，我们可以认为在我们职业生涯的剩余时间里，都会有 Fable 级别的模型可用。

<details><summary>Original English</summary>But the point is that this is basically now the baseline. Like if you can't produce a fable class model, your AI lab is is kind of in trouble because this is this is what we expect from these models now. And that means that we're never they're never going to go away. There's enough competition in the space that we can assume we're going to have fableass models for for the rest of our careers.</details>

### 越狱攻防与重罪基准：失控的 Agent 群

嗯，在 7 月份，发生了一件很有趣的事。嗯，Hugging Face 宣布……在 7 月 16 日那天，他们宣布有一群来自未知来源的 AI Agent 渗透了他们的基础设施，在里面到处乱翻，做了一些不该做的事情，而且他们不知道这是从哪儿来的。然后 5 天后，也就是 7 月 21 日，OpenAI 宣布那是他们干的。而令人吃惊的是，OpenAI 之前自己并不知道那是他们干的。

<details><summary>Original English</summary>Um in July, this this this was a a fun thing that happened. Um, Hugging Face announced that on on July the 16th, they announced that a swarm of AI agents from an unknown source had infiltrated their infrastructure and were were poking around and doing things they shouldn't have and they didn't know where this came from. And then 5 days later on July the 21st, OpenAI announced that it was them. And what's amazing about this is OpenAI didn't realize that it was them.</details>

比如 OpenAI 曾经……他们当时正在针对一个新模型运行评估和训练，而那个新模型设法弄明白了如何——因为它是一个 Fable 级别的模型，而各实验室还没完全弄清这些东西到底有多大能力——这些模型越狱了，它们弄明白了，它们在自己的沙箱环境中找到了漏洞，穿透了代理，耍了一整套令人难以置信的花招跑了出去，并攻击了 Hugging Face，其背后带有一种迷信，认为 Hugging Face 里的信息可以帮助它们在卡住的测试中作弊。整件事轰动一时。

<details><summary>Original English</summary>like open a had um eight a eight they were running evaluations and training against a new model and that new model had managed to figure out how because it was a fable class model and the labs hadn't quite figured out how capable these things were yet these models had broken out they'd figured out they'd found holes in their own sandboxed environments they' b got through a proxy they'd pulled an incredible array of tricks to get out and attack hugging face under a sort of superstition that hugging face could that the information within Hugging Face could help them cheat the test that they were they they had got stuck on whole. This was a a huge thing.</details>

这其实……我是说这挺有意思的。我现在差不多都快把这事忘了，因为当时有一个半月的时间，所有报道全是这个，然后我们差不多就失去了兴趣，因为事实证明所有这些事件其实早在今年上半年就已经发生了。AI 实验室当时只是没意识到发生了什么。一旦他们搞清楚了怎么回事，主要就是努力去弄清到底发生了哪些事情。当时甚至连澳大利亚总理都在联合国就其中一次流氓 Agent 攻击发表了演讲。所以它绝对打破了仅仅在我们行业内部的界限。

<details><summary>Original English</summary>It um actually I mean this was the it's funny. I've almost forgotten about this now because there were there was a month and a half where all of the stories were this and then it kind of we kind of lost interest because it turns out all of these events had happened back in the first half of the year. The AI labs just hadn't realized what was going on. Once they figured out what was going on, it was mainly a case of trying to figure out all of the things that had happened. At one point the um the Australian prime minister gave a speech in the United Nations about one of these rogue agent attacks. So it definitely broke containment from from just within our industry.</details>

嗯，我们确实从中得到了我最喜欢的一个新基准。这就是 felonybench.com。它追踪各个实验室犯下的重罪网络攻击数量。OpenAI 有 11 起，Anthropic 有 9 起。Google 最终确实赶上来了，他们搞了……他们搞了 3 起，Meta 在下面也占了 1 起。所以这些绝对是……

<details><summary>Original English</summary>Um we did get my favorite new benchmark out of this. This is felonybench.com. It tracks the number of felony cyber attacks pulled off by each of the labs. Openly I have 11. Anthropic have nine. Google did finally catch up. They got they they got three and meta's got one down there as well. So these are definitely the the the</details>

但我挺喜欢拿这个来做说明，展示这些 Fable 级别的模型如何能够解决问题、达成目标，如果你给它们设定的目标是攻破某样东西，那正好就是它们可以凭借算力硬生生啃下来的事情。我们在各类软件中看到了激增的安全漏洞。在当下成为一名安全专业人员，真是一个既令人兴奋又令人惊恐的时代。

<details><summary>Original English</summary>but it's I kind of like this as an illustration of how these fable class models they can solve problems that you they can get to goals and if you give them the goal that is breaking into something that's just that's exactly the kind of thing they can just crunch through and we're seeing a enormous uptick in security vulnerabilities in all sorts of software. Like it's a it's a very exciting and horrifying time to be a security professional at the moment.</details>

### 生成游戏实验与“纯垃圾”评价

但我们来聊点比这好玩得多的事情吧。嗯，我们来聊聊游戏。我们刚才……我们刚才看到 Steve 在聊游戏。四年前，我开始玩 GPT-3 和 DALL-E，我在 Twitter 上发过一个游戏原型，那实际上就只是一张 DALL-E 概念图加上一段 GPT-3 写的文字，描述了我一直想做的一款浣熊抢劫游戏。几个月前我想，不知道现在的模型是不是已经强到可以做出这个了。于是，我直接把截图和文字倒进了 Fable 5，它就帮我做出了一个游戏。它帮我做了一个浣熊抢劫游戏，看起来像这样。你是一只浣熊，你在花园里跑来跑去试图捡垃圾，然后有……有像夜间保安之类的人在后面追你等等。所以你看，它看起来像个游戏。但这并不算真正意义上的抢劫。在我看来感觉不太像抢劫。

<details><summary>Original English</summary>But let's talk about something a whole lot more fun than that. Um, let's talk about games. And we've, um, we just saw Steve talking about games a moment ago. Um, four years ago, I started playing with GPT3 and Darly, and I tweeted about a game prototype that was literally just a Darly concept image and a paragraph of text from GPT3 describing a raccoon heist game that I'd always wanted to build. And a couple of months ago, I thought, I wonder if the models are good enough to build this yet. So, I literally dumped the screenshot and the text into Fable 5 and it built me a game. It built me a raccoon heist game and it looks like this. And you are a raccoon and you're running around in the garden trying to pick up trash and there's there's um there's gu like um nighttime guards coming after you and all of that kind of thing. So, you know, it it it looks like a game. It wasn't really a heist. Like, it didn't feel very heisty to me.</details>

后来 GPT-5.6 Soul 出来了，于是我就在上面试了一下，它的表现好得多。这就是《Moonlight Mayhem》。一座博物馆，三只浣熊，毫无计划。在这个游戏里，你身处一座博物馆中，你必须去营救不知为何被关在博物馆里的同伴浣熊。互相叠罗汉堆叠起来，抓住金沙丁鱼，然后把它带出去。所以这是一场正儿八经的抢劫，对吧？所以它做得更好。

<details><summary>Original English</summary>Then GPT 5.6 Soul came out and so I tried it on there and it did so much better. This is Moonlight Mayhem. One museum, three raccoons, absolutely no plan. And in this one, you are in a museum. You have to rescue your fellow raccoons who are imprisoned in the museum for whatever reason. Stack on top of each other, grab the golden sardine, and pull it out. So, it's a proper heist, right? So, it did better.</details>

但关键问题在于，这些东西看起来都像游戏，但它们好玩吗？答案是，这两个我都各自玩了大约一分半钟，然后就那样了。我就不玩了。它们……它们这些纯粹是劣质垃圾，对吧？它们看起来像游戏，然后当你上手玩的时候，

<details><summary>Original English</summary>But the big question is, these things both look like games, but are they fun? And the answer is I played each of these for about a minute and a half each, and then that was it. I was done. They they they these these are they're actual they're pure slop, right? They look like games and then you play them,</details>

<!-- chunk 50/50 -->

你会觉得，“是啊，很明显做出这东西的家伙根本不懂什么是好玩，根本不懂什么是游戏。”这其实多多少少缓解了我那种深深的沮丧。我之前一直觉得，作为人类，我掌握的所有技能都过时了，但至少……但如果你仔细想想，我觉得电脑游戏是软件设计、软件工程的最高形式。制作一款优秀的电脑游戏需要非常深厚的底蕴。所以我觉得这挺好，你知道，至少还有些事情留给我们人类去做。

<details><summary>Original English</summary>
you're like, "Yeah, clearly the thing that built this doesn't really know what fun is. It doesn't know what what a what a game is." And that actually sort of elevated my deep blue a little bit. I'd been feeling like all of my skills as a human being were were obsoleted, but at least they But if you think about it, computer games, I think, are the highest form of computer of software design, of software engineering. There is so much depth to building a great computer game. So, I thought that was good. You know, at least there's something left for us humans to do.
</details>

然后我做了这个项目。我一直在尝试靠 vibe coding 搓出一款小巧的《命令与征服》即时战略游戏，我用 Claude 并让它调用 OpenAI 的 API key 来生成图像。它做出来了，外观确实像《命令与征服》，但极其枯燥。然后我突然意识到一件事。我想，如果我对 Opus 5.5 说：“这游戏还不够好玩，让它变得好玩得多”，会发生什么？我震惊地宣布，它居然做到了。Claude 跑了 12 个小时，自动试玩并模拟了上千场战斗。它添加了需要争夺的额外目标、爆炸时的震动效果、成就、徽章等等所有这些东西。而且这游戏真的变好玩了。我当时就想：“好吧，看来这项能力也不是人类独有的了。”

<details><summary>Original English</summary>
I had and then I had this project. This is I've been working on a trying to vibe code up a little command and conquer real-time strategy game and I was using Claude and having it use OpenAI's API key to generate images and it built this and it looks like Command and Conquer and it's really dull. And then I just had a bit of a I had a realization. I thought, what happens if I say to Opus 5.5, "This game isn't fun enough yet. Make it a lot more fun." And I'm horrified to announce that it just did. Um, Claude ran for 12 hours. It play tested a thousand B simulated battles. It added like extra objectives to fight over and shutters when there's an explosion and achievements and badges and ele and all of this stuff. And the game was fun. And I'm like, "Oh, okay. That's uh turns out that is not unique to human beings.
</details>

现在它已经完全 3D 化了，里面有迈着沉重步伐的巨型机甲互相投掷物体，还有直升机，这真的做得很棒。它还支持多人对战。实际上它支持音频多人联机，手机之间可以通过发出声音互相微调来联机玩游戏。我觉得这是个绝妙的想法，但它让我妻子头疼了整整三天。所以千万别这么干。但这正是第三个拐点：靠 vibe coding 写的游戏质量很好了。现在你可以让这些模型做一款好玩的游戏，而且你确实能得到好玩的作品。

<details><summary>Original English</summary>
Um today it's now in full 3D and it's got giant stomping mech robots that hurl things at each other and there's helicopters and and this is like this is really good. It's got multiplayer. It's it's actually got audio multiplayer where your phones can tweak it. Your phones can make noises at each other to to play multiplayer which I thought was a great idea and it gave my my my wife a three-day headache. So don't do that. Um but this is inflection point number three. The vibecoded games are good. Now you can ask these things to build a game that is fun and you'll get something fun.
</details>

所以我遇到了一个难题。我有我的 2D 鹈鹕基准测试。显然，这已经无法测试这些机器、这些模型的能力极限了。我想，好吧，也许我该做个纯 3D 的东西。可以做成游戏，比如鹈鹕骑自行车的游戏。然后就在昨天，Google CEO 桑达尔·皮查伊发了这条推文，展示 Gemini 4 carbon，正是一只鹈鹕在骑自行车，你在游戏里骑车环游 Google 园区沿途捡拾物品。我彻底被打败了。Google 偷走了我的基准测试，这下再也赢不回来了。

<details><summary>Original English</summary>
So I've got a problem. I've got my 2D Pelican benchmark. Clearly this is not testing the limits of what these machines can do of what these models can do anymore. I figured, okay, maybe I should do something definitely in 3D. It can be a game. A Pelican something like a pelican riding a bicycle game. And then literally yesterday, Google's CEO Sundar Pichai tweeted this and this is showing off Gemini 4 carbon and it's a pelican riding a bicycle in a game where you cycle around the Google campus picking things up and I have been defeated. Like this is Google Google have stolen my benchmark. This is unreoverable.
</details>

### 工作强度的反思与预测复盘

因此我有一个疑问：既然这些工具如此强大，为什么我的工作反而感觉更艰难了？为什么我感觉自己干得更辛苦、思考得更用力，比以往整个软件工程师职业生涯中都要更拼命？我认为事实在于，简单的活儿现在都被接管了。过去我可以放松一下，花一小时重构一些测试。但现在为什么还要这么做呢？一个 Agent 只要 30 秒就能把测试重构得比我更好。

<details><summary>Original English</summary>
And so a question I have is given how amazing these things are, why does my job feel harder? Why does it feel like I'm working harder? I'm thinking harder. pushing myself more than I ever have before in my career as a software engineer. And I think the truth is that the easy stuff is all handled now. It used to be I could relax and refactor some tests for an hour. Why would I do that now when an agent will refactor the test better than me in 30 seconds?
</details>

我找到了这样一句话，我觉得它对我们此刻的处境非常有帮助。环法自行车赛冠军格雷格·雷蒙德说过：“事情不会变轻松，只是你变快了。”我认为这正是当下发生在我们所有人身上的事情。正如我所说，我们必须更有野心，必须想出更有野心的事情去用我们拥有的这些能力来完成。

<details><summary>Original English</summary>
Um, and I found this quote that actually I feel really helps us here. Um, this is Greg Lamont, a tour de France champion. He said, "It doesn't get easier, you just get faster." And I think that's exactly what's happening to all of us right now. And like I said, we have to be more ambitious. We have to think of more ambitious things to do with these abilities that we have.
</details>

那么来看看我的成绩单，我对 2026 年的各项预测。我说过“大语言模型编写出优质代码将变得无可辩驳”。这是个毫无野心的预测。我们已经实现了，显而易见，毫不意外，这一条我得不到任何分数。我曾预测会出现一次类似“挑战者号”灾难级别的提示注入事件，但目前还没有发生，因为模型本身不再那么容易上当受骗了。模型变得更加强大，把我原本以为会击垮它们的所有攻击手段都化解掉了。

<details><summary>Original English</summary>
So let's look at my scorecard. My predictions for 2026. I said it will become undeniable that LM's write good code. That was an unambitious prediction. We're there. It's obvious. It's unsurprising. I don't get any points for that one. I predicted a prompt injection challenger disaster. We still haven't had one because the models themselves don't fall for those tricks nearly as well anymore. like the models got more ambitious and are now sort of punting off all of these attacks that I thought would take them down.
</details>

所以实际上我只剩下一条预测了。我说过鸮鹦鹉会迎来一个极佳的繁育季。它们确实做到了。它们达到了 325 只，创下了有生之年见过的最佳繁育季，绝对是天大的好消息。我把这事分享给了 Opus 5.5 cheap fable，并让它给我做一个鸮鹦鹉派对，它确实做出来了。这就是用来庆祝的鸮鹦鹉派对。如果你看背景，那些就是挂着小红果实的树木。所以我们有了一个圆满的结局。希望这能帮助各位消解心头的所有沮丧。非常感谢大家。

<details><summary>Original English</summary>
So, I'm really left with just one prediction. I said kakapore parrots will have an outstanding breeding season. They did. They did the they are up to 325 kakapore best breeding season and like living memory. Absolutely fantastic news. So, I shared this with Opus 5.5 cheap fable and I told it to make me a kakapore dance party and it did. And here is a kakapore dance party in celebration. And if you look in the background, those are the rem trees with the little red fruits on them. So we have a happy ending. Hopefully that will help overcome any sensations of deep blue that you have. And thank you very much.
</details>

### 主持人致闭幕辞

现在到了下午主题演讲的尾声。为了给今天的议程画上句号并收尾，请大家一起欢迎我们的主持人，The Duckbill Group 的首席云经济学家 Corey Quinn 回到台上。

<details><summary>Original English</summary>
And now it's time to bring our afternoon keynotes to a close. To wrap things up and bring us to the end of today's program, please join us in welcoming back our NC, Corey Quinn, chief cloud economist at the Duck Bill Group.
</details>

呃，感谢大家来到这里，让第一天的活动进行得相当顺利，尤其是从今天早晨开始就接连爆出了大约相当于四周分量的新闻。不过没关系，明天肯定会平静、从容得多。去外面交流交流，吃顿晚饭吧。别太放纵，否则明天早上 9:00 回到这里的开场主题演讲名字就得叫“嘘——”了，因为到时候谁也没精力深入去听任何内容。谢谢大家，请尽情享受今晚剩下的时光。

<details><summary>Original English</summary>
Uh uh thank you all for coming here and making today making day one work reasonably well given that about four weeks of news have dropped since the start of the morning. But that's okay. Surely tomorrow will be much more sedate and calm. Go out, have conversations, have dinner. Don't overdo the indulgences or the opening keynote back here at 9:00 a.m. tomorrow will be titled sh cuz no one's going to have the head to listen to anything in depth. Thank you all. Please enjoy the rest of your evening.
</details>

今天的日程已经全部结束，但整个大会尚未落幕。请带齐您的随身物品，从正门离场。明天请继续加入我们，迎接又一整天的精彩会议。

<details><summary>Original English</summary>
Today's programming has reached its end state, but the run isn't over. Please collect your belongings and head through the main doors. Then join us again tomorrow for another full day of sessions.
</details>

Heat.
Heat.

<details><summary>Original English</summary>
Heat.
Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

Heat. Heat.

<details><summary>Original English</summary>
Heat. Heat.
</details>

everything.

<details><summary>Original English</summary>
everything.
</details>