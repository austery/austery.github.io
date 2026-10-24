---
author: Latent Space
date: '2026-02-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=x9rWFiIubmc
speaker: Latent Space
tags:
  - ai-agent
  - semiconductor-cycle
  - hbm-memory
  - financial-analysis
  - gpu-supply-chain
title: 对话 Doug O'Laughlin：Claude Code 带来的金融分析革命与全球存储芯片大缺货
summary: 半导体研究机构 SemiAnalysis 的 Doug O'Laughlin 深度探讨了 AI 代理（如 Claude Code）如何通过“一键生成”能力重塑金融研究工作流。同时，他深入分析了摩尔定律终结背景下，由 HBM 需求激增引发的全球 DRAM 产能挤压，并对微软的 AI 战略布局及 Oracle 的财务决策提出了犀利见解。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Doug O'Laughlin
  - Dylan Patel
  - Jensen Huang
  - Satya Nadella
companies_orgs:
  - SemiAnalysis
  - Anthropic
  - OpenAI
  - Nvidia
  - Microsoft
  - Oracle
  - TSMC
  - Samsung
  - SK Hynix
products_models:
  - Claude Code
  - Claude 3.5 Sonnet
  - Claude 4.5
  - GPT-4
  - TPU v7
  - Blackwell
media_books:
  - On Writing Well
status: evergreen
---
### AI 代理的“觉醒时刻”

**[主持人]**: 这种东西经常犯错，一直都在犯错。它目前还像是个**初级分析师**，对吧？分析师去处理那些极其麻烦的信息，汇总起来让你在顶层做出明智的决策。

<details>
<summary>Original English</summary>

**[Host]**: This crap makes mistakes all the time. All the time. It is still just like a... like I think of it once again as like a junior analyst, right? The analyst goes and does all this like really pain in the ass information. You bring it all together to make a good decision at the top.

</details>

**Doug O'Laughlin**: 历史上，情况确实是这样的：我曾经也是那个初级分析师，去搜集所有信息，在做了足够多次之后，会产生一种**元认知**（meta level thinking）。你会觉得，好吧，我真正理解了这类分析，我是这方面的专家，我的准确率很高。现在我是专家了。我认为 AI 目前还没有这种元层面的学习能力。

我们看看 L1 模型是否能做到。全世界那些投入万亿级美元的人都认为它能做到。它最好能做到，否则投入这么多钱却没有元学习能力就太糟了。但对我个人和我们的公司来说，AI 极大地**放大**了专家的能力。你仍然得做点什么，不能只是把生成的垃圾直接端上去。对我来说，它什么时候在“注水”是非常明显的。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: Historically, what happens is that junior analyst who I once was went and gathered all that information and after doing this enough times, there's a meta level thinking that's happening where it's like, okay, here is what I really understand and how this type of analysis I'm an expert in. Actually, I'm very good at. I consistently have a hit rate. Now I'm the expert, right? I don't think that metal level learning is there yet. Um, we'll see if L1's do it, right? Everyone who's spending one quadrillion dollars in the world thinks it will. It better it better happen, right? If you're spending, you know, a trillion dollars and there's not metal level learning. But for me in our firm, that massively amplifies everyone who is an expert because like you have to still do something. You can't just like slop it up. It's very obvious to me what it's sloping.

</details>

**[主持人]**: **Doug Loft**，欢迎来到 Inspace。

<details>
<summary>Original English</summary>

**[Host]**: Doug Loft, welcome to the inspace.

</details>

**Doug O'Laughlin**: 谢谢邀请。认识这么久了，我可以叫你 Swiss 吗？我的大脑一直这么记的。如果你愿意，也可以叫我 Mule（骡子），你知道的。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: Yeah, thank you for having me. Yeah. Um, I after all this time, I just Is it okay if I just call you Swiss? I feel the... that's that's where my brain is. So, I've known you for so long. You can call me Mule if you want. I'm um you know.

</details>

### 从价值投资者到半导体专家

**[主持人]**: 让我们讲讲 Doug 的故事。很多人听说过 **Dylan**，但我今天想专门讲讲 Doug 的故事，讲讲 **Fabricated Knowledge** 的故事。你以前是个**价值投资者**，账号叫 **Value Mule**，后来是有导师还是什么原因让你被“宅男狙击”（nerd sniped）进了半导体领域？

<details>
<summary>Original English</summary>

**[Host]**: Um, let's let's do a little bit of the Doug story because a lot of people hear about Dylan. Uh, and I wanted to just make this the Doug story. Made the fat knowledge story. You used to be a value investor. That's kind of how you you were value mule and you had a mentor or something that nerd sniped you into semiis. Is that the the story?

</details>

**Doug O'Laughlin**: 不，实际上是我自己“狙击”了自己。我不会说那是单纯的价值投资——虽然对听众来说，叫它价值投资也行——但在当时，我们更关注**优质复利公司**（quality compounder companies）。我发现的那家彻底让我沦陷的公司是 **ASML**。我爱上了它，然后开始阅读关于它的一切：制造这些机器有多复杂，谁能制造它们。从此我进入了半导体整个下游领域。这一切始于 2018 年的 ASML。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: Um, no. Actually, I solo nerd snipe myself. So, I I wouldn't say value because uh well well for for everyone who's listening to this podcast, might as well be value, right? Maybe quality focus back in the day, but we had this whole thing where we wanted to buy quality compounder companies. And um the one I found that nerd site me all the... like single shot me is I found ASML and I like fell in love with it. And then I like after ASML I just like read about all this stuff how complicated it's to make these who are the people who are able to make them and then I you know semicopters the whole downstreams all from there but it started with ASML in 2018.

</details>

**[主持人]**: 我本来想把 **Asianometry**（YouTube 频道名）搬出来的。

<details>
<summary>Original English</summary>

**[Host]**: I was going to pull out the Asianometry.

</details>

**Doug O'Laughlin**: 那太完美了。John 简直是个“怪物”，他有一整个关于 ASML 各个方面的播放列表。最疯狂的是，ASML 的一切听起来都像**科幻小说**。除了会说话的智能机器人，科幻小说真的存在，就在 ASML。我一直觉得半导体是人类制造的最重要的东西。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: Yeah. That's perfect. That's a perfect one. be amazing. John's a monster, honestly. This one, right? Uh yeah. Yeah. Um I mean, the thing that's crazy is he has um I don't know, he has a whole playlist about it. Every single aspect of what goes into it. And what what's truly great about it, it's all science fiction. Like that's my favorite thing is like science fiction exists other than you know the talking perfectly intelligent robot whatever information LLM. Yeah, ASML is all science fiction. So the semicuncture stuff's always been science fiction. Always loved it. Always thought it was cool. Thought it was the most important thing that we ever made.

</details>

### 摩尔定律的终结与英伟达的崛起

**Doug O'Laughlin**: 对我来说，一个具有“激进化”意义的观点是：我深信**摩尔定律已经死了**。我意识到，这不仅是一项超难制造、极具技术趣味的新技术，而且所有的旧游戏规则都要被扔掉了。

以前大家觉得半导体是一个极其成熟的行业。在 ChatGPT 出现之前，你得读那些行业入门手册（primers），它们会告诉你这是个成熟行业，增长乏力，大家都在玩 2000 年代初的那套旧剧本。很多人讨厌硬件，觉得软件才是最有价值的。大家认为半导体没什么新鲜事了。然而，每天制造一颗新芯片都像是在写科幻小说，人们却把它视作理所当然。

当科幻小说终结，当你无法再把芯片做得更小时，你以前免费获得的性能提升全消失了，你必须重新思考。对于半导体行业，这为那些懂得如何制造好芯片的人创造了极大的**定价权**或价值。**英伟达（Nvidia）**就是最好的例子。他们不仅懂芯片，还懂网络、设计、扩展，懂每一个环节。而在过去，只要 CPU 变强，一切就万事大吉了。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: For me, the thing that was like I guess radicalizing was um I really believe Morris law was dead. Um and I was like, "Oh my god, not only is it this cool new technology is super hard to make and very interesting and technologically very fun to understand and and like I get it intuitively, but um also everything all the old playbook is about about to be thrown out because it's been like this is a super mature industry. you read the these primers about it like that's how you learned about things back before chat GPT knew everything or um you had to go and read these primers of all this information they're like oh it's a very mature industry... everyone kind of had this old playbook from the early 2000s... people just thought it was this old mature business that had nothing new under the sun. Meanwhile, every single day just making a new chip was like science fiction... And when the science fiction ends because you can't make the chips as small as you could, all of a sudden all those free gains you got go away and you have to think about it. And what happened for semiconductor specifically is it created a lot of pricing power or value for everyone who knew how to make a good chip. So Nvidia is probably the best case.

</details>

### Claude Code 与“一键生成”的生产力

**[主持人]**: 让我们把焦点转到 **Claude Code** 的发布。你一直是 Claude Code 的强力推客。

<details>
<summary>Original English</summary>

**[Host]**: Uh, but we wanted to sort of focus this for the cloud code launch, cloud code anniversary, and you've been a big cloud code show.

</details>

**Doug O'Laughlin**: 我确实是。你看到那个“4% 的代码由 AI 生成”的图表了吗？现在可能已经到 5% 了。生成代码现在变得非常容易，这个数字会持续攀升，这种速度令人震惊。

如果你想玩好任何游戏，归根结底我们都是工具使用者。作为基金经理或分析师，你的工作是寻找信息优势，以别人没做过的方式整合信息。我一直认为，掌握最重要的**军用级工具**至关重要，本质上就是 ChatGPT、Anthropic 这些。我是这类工具的早期采用者。比如，从一年前 Claude Code 刚出来时，我就开始用它跑我们的案例研究（case study）。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: Yeah, I I am. Where's the chart with the four uh 4% of code? ... Oh, you know what's really crazy is we've updated that chart. I think it's like five now... if you want to be good at any game, we're we're tool users at the end of the day, right? ... let's say you're a fund manager or an analyst, right? Your job is to find information edges and like new ways to put information together that no one else has done. Um, and so like I've always thought it's really important to know the most important weaponsgrade uh tool that you can do all the time which is essentially chache anthropic all this kind of stuff and I've been pretty like I'm a I'm an early adopter in tools as much as I can be.

</details>

**Doug O'Laughlin**: 我们的案例研究是用来招聘财务分析师的。我会把任务丢给 AI Agent：当代理真正成熟时，它们应该能“一键完成”（oneshot）那些人类需要 24 小时才能完成的多步骤困难任务。

我以前用 Opus 4 做过一些“氛围编程”（vibe coding），但很辛苦，需要反复反馈。但当 **Claude Code 4.5** 出来后，我试了一下，它开始能**一键生成一切**了。那些你原本觉得“UI 凑合就行”的 MVP 项目，它直接一键搞定，还能解释它在做什么。这种通用的、一键生成 MVP 的能力，让你能基于它构建更复杂的东西，因为你在某种程度上可以信任它的产出。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: ... can you take this company and do some analysis, blah, blah, blah, give us this format back. Um, and I've been running it through like the agentic things like, hey, what what when agents really come around, they should be able to oneshot multi-step hard things to do, things that would take a human 24 hours to do, right? ... and then um you know everyone was freaking out about cloud code 4.5 and I like took it for a spin... and it just like one it started like oneshotting everything, right? Like all these MVPs... generalized easily oneshot MVP of these like projects and able to like really build things on top of it because you can trust what it's doing to a certain extent.

</details>

### “现在全是能力问题了”

**Doug O'Laughlin**: 我会把我的头寸信息、想法给它，让它帮我整理笔记并汇总。它做得很好。然后我让它构建投资组合，跑基础风险分析。我甚至让它根据我的投资风格建立一个**投资框架**，给标的打分。这种迭代式的工作让我意识到：这是一个疯狂有用的工具，它迅速将我的思考系统化了。

我现在的口头禅是：“**现在全是能力问题了**”（It's all a skill issue now）。如果你做不到，那是你不会用工具。我甚至让 AI 抓取了 GitHub 上所有带有“Signed-off-by: Claude Code”字样的提交记录（commits），写了个定时任务（cron job）每天更新。看到那个指数级增长的曲线了吗？两周内增长了 4%，我从没见过增长这么快的趋势。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: ... can you just like kind of like start copy pasting some notes over and putting all together? It's like yeah it does... can we like make an investment framework for my investment style and start to grade all this stuff... and my joke on the the podcast is it's all a skill issue now... I heard about the fact that the cloud code has the commits, right, onto the public... scrape me all the commits, right? ... I have like a crown job updating it every single day... 4% in like two weeks or something.

</details>

### 全球存储芯片大缺货：AI 的“超级石油”

**Doug O'Laughlin**: 让我们谈谈**存储芯片疯狂**（Memory Mania）。这里有一个 3:1 或 4:1 的折损率。当你把产能转向 **HBM**（高带宽内存）时，因为 HBM 极其巨大且复杂，良率并非百分之百，制造一个单位的 HBM 实际上要消耗掉三个单位的普通 DRAM 产能。

这就像是：人类发明了一种更高级的**航空燃油**（超级石油），但制造它的唯一方法是消耗掉你所有的普通燃料，进行大规模的浓缩和精炼。结果就是，一旦这边有任何需求，普通燃料立刻就会短缺。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: it's a 3:1 to 4:1 ratio... when you convert to HBM because there's a huge amount of HBM, it takes three times uh one HBM sort of unit is like three times uh of the other sort of DDR or whatever, right? ... effectively, you're trading some like... I called it like super oil... in order for this higher grade of jet fuel has been invented and the only way to make it is to like actually uh get rid of all all your other fuel and you have to like massively condense it and refine it. Okay. So um now what happens is if there's any demand here it's an instant shortage.

</details>

**Doug O'Laughlin**: 我们刚刚经历过历史上最惨烈的 NAND 和 DRAM 崩盘，那是灾难性的。由于那次惨痛的周期，没人投资新的无尘室或资本设备，大家都在失血，甚至有人面临破产。

现在，需求突然爆发，尤其是最高端的 HBM。HBM 消耗了所有的 DRAM 产能。而那些需要两年才能建成的无尘室还没盖好。我们的结论是：**DRAM 价格可能会再涨 100%**。这会发生**需求破坏**（demand destruction），普通消费者可能买不起低端手机了，或者今年你买不到打游戏用的显卡了，因为你被市场价格排挤出去了。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: And so we we hilariously enough came out of like the biggest shortage ever in Nan and DM. Like terrible like catastrophic the worst one ever... meanwhile, we have all this new demand, HBM specifically... we completely constrained, took all the DM capacity... these clean rooms take two years to make, man... our conclusion is like we we could see DM prices like go up 100% again... you're not going to get your low-end phone. You're not going to get a GPU this year for gaming. None of that stuff.

</details>

### 微软的“野蛮人”难题

**Doug O'Laughlin**: 关于微软，我有一个最辛辣的观点：**微软在 AI 竞赛中其实处境最尴尬**。他们是全世界所有人都想狙击的目标，因为几乎所有人类都在用微软的软件做信息工作（Excel, PowerPoint, Word）。

他们在 Azure 业务中引入 OpenAI，本质上是在**雇佣野蛮人来守卫罗马城门**。你对这些野蛮人说：“嘿，我们需要些帮手，我们付钱让你们去冲锋陷阵。”但问题是，这些野蛮人每年都在变得更强大，总有一天他们会意识到：我可以轻松翻过这堵破墙。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: ...Microsoft has the most to lose... they're the horizontal software company that humans use their software to do information work... The problem is the Azure business with OpenAI, right? You're essentially renting barbarians at the gate. You're you're like, you know, this is ancient rome and you're like, hey, we need some extra guys, so we're going to we're going to pay money for these barbarians to burn... The problem is like each year they become more powerful...

</details>

**Doug O'Laughlin**: 微软陷入了“**创新者困境**”：是维持现有的现金流和股东价值，还是全身心投入 AI 去杀掉自己的核心业务？Satya（微软 CEO）看起来不像是那个愿意“梭哈” AGI 的人。他可能觉得 AI 只是另一个 Excel 级别的工具。

与此同时，Claude for Excel、Claude for PowerPoint 正在实现微软本来应该自己做出的产品体验。微软现在被卡在中间， execution（执行力）相当惨淡。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: ...responsible this like an innovator's dilemma, right? Like do I maintain maximize shareholder value and cash flow today or do I have a a deep belief that AI will kill the hell out of my core business... it seems like Satia is not a believer... reality is Claude for Excel, Claude for PowerPoint is literally exactly what it's supposed to be. Microsoft should have built it.

</details>

### 徒步 Continental Divide Trail 的感悟

**[主持人]**: 最后聊聊徒步。你休了个长假去走了**大陆分水岭步道（CDT）**。在 AI 时代，大家总担心休息一年就会被彻底甩开。

<details>
<summary>Original English</summary>

**[Host]**: Last thing hike... I've never taken a break. Never... if you take a break in this time, you're like just going to be so behind.

</details>

**Doug O'Laughlin**: 我走的是 CDT，它是美国三大步道中最长、最偏远的。那是在 2021 年，AI 爆发之前。我花了 6 个月走了 2800 多英里。那是真正的冒险。在现代生活中，你什么时候才有机会说“我要去冒险”？

在那 6 个月里，你会经历**极度的低谷和极度的高潮**。极度低谷时你会怀疑人生：“我在这干嘛？”极度高潮时你会觉得“天呐，活着真好”。这种原始的生命体验非常有意义。它让我更清晰地定义了自己，我知道了自己的底线在哪里，哪些事太吓人、太难，我不会去做。**自我掌控（Self-mastery）是你最重要的工具**。

<details>
<summary>Original English</summary>

**Doug O'Laughlin**: I did the Continental Divide Trail, which is the longest and most remote of the three... I did that in 2021 pre-AI... 6 months, 2800 miles... when in modern life do you get to say hey I'm going on an adventure... these crazy lows where you're like, what am I doing? What does all mean? Highest highs and mean like holy crap, it's so good just to be alive... selfmastery is your most important tool use of all.

</details>

**[主持人]**: 感谢你参与对话，带我们从 Claude Code 的痴迷聊到半导体，再聊到徒步。

**Doug O'Laughlin**: 谢谢邀请，很高兴能叙叙旧。