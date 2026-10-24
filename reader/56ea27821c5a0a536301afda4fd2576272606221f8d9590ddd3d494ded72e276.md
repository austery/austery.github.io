---
author: a16z
date: '2026-09-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3T5sij3spWw
speaker: a16z
tags:
  - personal-agent
  - agentic-workflow
  - autonomous-agent
  - consumer-ai
title: a16z 对话 Assistant Bench 创始人：消费级 AI Agent 的破局点与经济账
summary: a16z 合伙人 Anish Acharya 深度对话 Assistant Bench 创始人 David Pawlan，全面梳理消费级个人 AI Agent 的爆发轨迹。探讨了通用与垂直 Agent 的格局、硬件载体与语音交互、主动性与人格特质的护城河、Agent-to-Agent 交互新范式以及长尾创业公司的商业化与生存挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - a16z
  - OpenAI
  - Meta
products_models:
  - ChatGPT
  - Assistant Bench
  - Muse
  - Instinct
media_books: []
status: evergreen
---
### 精彩预告：消费级 Agent 的核心命题

**大卫·鲍兰**: 普通大众根本不在乎效率提升 10%。我有一个非常犀利的观点：**Muse charm**（智能吊坠）其实并不是为了赢得硬件竞赛，更多的是为了在现实世界中收集数据，为扎克伯格未来绘制真实世界的**元宇宙**（Metaverse）提供燃料。

<details>
<summary>Original English</summary>

**David Pawlan**: The general population does not care about being 10% more efficient. I have a hot take thesis that this Muse charm is actually less about trying to win the hardware game and it's more about data collection in the real world to fuel Zuckerberg's future metaverse of mapping out the actual world.

</details>

**阿尼什·阿查里亚**: 我们团队内部之前开玩笑说，距离 Agent 给别人发信息说“我注意到你对她没那么上心，所以我已经替你跟她分手了”这种场景，大概也就差几天时间了。

<details>
<summary>Original English</summary>

**Anish Acharya**: We were joking internally like we're days away from an agent messaging someone saying "I noticed you weren't that into her so I went ahead and broke up with her."

</details>

**大卫·鲍兰**: **主动性**（Proactivity）具有极大的防御壁垒。我骑车上班的时候想把事情办完，直接打开 **ChatGPT Voice** 的高级语音模式……

<details>
<summary>Original English</summary>

**David Pawlan**: There is massive defensibility around proactivity. I was biking to work. I want to get stuff done and I just start talking to ChatGPT voice and throw it into advanced mode...

</details>

**阿尼什·阿查里亚**: 感觉未来必然会出现只服务于 **Agent-to-Agent**（智能体对智能体）交互的基础设施和产品，这些在今天是完全不存在的。你觉得那会是什么样子？

<details>
<summary>Original English</summary>

**Anish Acharya**: It does feel like there's going to be infrastructure and products that exist only for agent-to-agent interactions that doesn't exist today. What do you think that looks like?

</details>

---

### 开篇与个人 AI Agent 的爆发潮

**阿尼什·阿查里亚**: 这一切都是必然会发生的。大家好，欢迎收看 **a16z Show**。今天我非常激动能与我的好友 **大卫·鲍兰**（David Pawlan）坐在这里。几周前我们刚聚过一次，我们俩都对个人助手以及整个消费级 AI 领域正在发生的事情感到无比兴奋。伙计，在过去的短短几周里，发生的变化实在太多了。

为了抛砖引玉，我认为在整个生态系统中，有几个时刻让人仿佛“看到了上帝”。ChatGPT 的问世是一个重磅时刻。在 2022 年 11 月和 2023 年初，很多人都在惊呼：这个能写邮件、能写诗、能跟你来回对话、让你感觉在与一个合成人互动的神奇事物到底是什么？那当然是一切的开端，是一场大爆炸。

第二个重大时刻是**代码智能体**（Coding Agents），开发者们开始痴迷于 **Claude Code** 和 **Codex**，以及那种轻而易举构建软件的能力。而最近，随着 **Instinct**、**Muse** 以及 ChatGPT 各种工作流的涌现，我们在**个人智能体**（Personal Agents）及其能为普通消费者做些什么方面，迎来了一股异乎寻常的热潮。所以今天我们来聊聊关于个人 Agent 的方方面面。我们会尽可能深入地探讨。我们假设大家已经看到了我们所看到的许多动态，今天也将是我们系列对话的第一期。欢迎大卫！

<details>
<summary>Original English</summary>

**Anish Acharya**: It is inevitable that we're going to see... All right, welcome to the A16Z show. I'm so psyched to be here with my friend David Pawlan. We hung a couple of weeks ago. We're both so enthusiastic about everything that's been happening with personal assistant and consumer AI generally. And man, so much has happened in the last couple of weeks.

Maybe to tee it up, you know, I sort of think that there's been a few moments where some part of the ecosystem has sort of seen God. And ChatGPT was a big one. And you know, I think for a lot of folks in November 22 and a bit of 23, it was like, what is this thing that can write emails and poems and start to have a conversation back and forth and feel like you're interacting with the synthetic person? That was of course the beginning, the big bang. The second moment really was coding agents and everything that developers have been obsessed with around sort of Claude Code and Codex and the ability to trivially create software. And then finally, most recently with Instinct, Muse, and ChatGPT work, we've had this extraordinary enthusiasm around personal agents and what they can do for us as consumers. So, we're here to talk about all things personal agents. We're going to go as deep as we can. We're going to assume that everybody has seen many of the same things that we have seen and we're going to make this the first in a series of conversations. Welcome, David.

</details>

**大卫·鲍兰**: 谢谢你，感谢邀请我来，非常期待今天的交流。

<details>
<summary>Original English</summary>

**David Pawlan**: Thank you. Thanks for having me. Excited to be here.

</details>

**阿尼什·阿查里亚**: 让我们先放大视野，聊聊过去几个月、几周里个人 Agent 的发展轨迹。你最近看到了什么，对当前的局面有什么看法？

<details>
<summary>Original English</summary>

**Anish Acharya**: Let's like zoom out and maybe talk about, you know, the arc of personal agents over the last few months, the last few weeks. What have you been seeing? What's your sort of view on things?

</details>

**大卫·鲍兰**: 是的，这个领域在过去四周里彻底爆发了。我们可以把时间线往前拉一点，我是 **Poke** 的早期用户。Poke 可以说是最早真正进入市场的消费级 AI Agent 之一。我记得它大概是 9 月 8 号上线的，三天后的 9 月 11 号我就开始用了。那段记忆非常鲜活，因为体验实在太不可思议了。他们的核心卖点是让你跟 Agent 讨价还价，协商你究竟愿意为它付多少钱，这完全震撼了我。

接着到了 11 月下旬，**OpenClaw** 发布，迅速席卷了科技圈，让人意识到未来真的要来了。随后陆陆续续涌现出一些新产品，但最近最引人注目的，是 **Instinct** 彻底引爆了科技推特圈。它完全踩中了浪潮，热度极其疯狂，随后就像多米诺骨牌一样：**Grokbot**、**Muse**，还有一大批长尾产品如 **Caddy**、**Ali**、**Pi** 相继登场。看到整个科技圈对“这些 Agent 日常究竟能为我们做什么”爆发出如此巨大的兴趣和求知欲，真的很不可思议。而且大家都处于同一条船上——没人真正确切知道答案，这里就像狂野西部，大家都在探索尝试。

<details>
<summary>Original English</summary>

**David Pawlan**: Yeah, so this space has exploded over the past four weeks. We can roll it back. I was an early adopter of Poke. So I want to say Poke, which was kind of one of the first like consumer AI agents to really hit the market. Yes. That launched I believe it was September 8th and then I started using it September 11th, like 3 days later. And like I remember it so vividly cuz it was just an unbelievable experience. Their whole gimmick was this negotiation with the agent on how much you're actually going to pay. And it totally blew my mind. Then comes late November and OpenClaw gets released and that kind of takes the actual world by storm of like there is something coming. And then a few other have popped up here and there, but most recently we saw Instinct really blow up the the tech Twitter bubble. Just absolutely rode a wave, went nuts, and then it was just dominoes. You have Grokbot, you have Muse, you have a bunch of longtail ones like Caddy or Ali or Pi. And it's really been amazing to see, you know, this whole tech bubble is just exploding with interest and like an intellectual curiosity for what can these agents do for us on a day-to-day basis. And there's I think everyone's kind of in the same boat where nobody really knows like it's it's the wild wild west. We're just playing around here.

</details>

---

### 什么是 Assistant Bench？消费级评测基准的建立

**阿尼什·阿查里亚**: 我完全同意。我们应该花点时间聊聊 **Assistant Bench**，这是由你发起、最近受到极高关注且引发广泛讨论的全新评测平台。给大卫先介绍一下 Assistant Bench 的背景，然后我再问你几个问题。

<details>
<summary>Original English</summary>

**Anish Acharya**: I totally agree. And we should take a moment to talk about Assistant Bench, which is this new, really important and discussed benchmark that you're the author of. Maybe tee up Assistant Bench a little bit and then I'll ask you a few questions.

</details>

**大卫·鲍兰**: **Assistant Bench** 是一个按具体用例横向对比所有这些 AI 助手的网站。我们给所有的助手输入完全相同的 Prompt。例如：“帮我订一张去芝加哥的机票”、“在我具体定位的五个街区范围内找一家素食餐厅”等等。我们在单轮 Prompt（One-shot Prompt）的基础上去对比实际产出的结果：它是否真的执行成功了？它会不会追问后续问题？它在 16 个不同的评估维度上表现如何？我们把所有这些指标放在一起进行横向比对。

虽然我们用了“基准”（Benchmark）这个词，但可以把它看作是一个**面向消费者的评测基准**，而不是后台纯技术性的评测。如果你想订机票，你到底应该用哪一个？谁的表现最好？它们的实际响应速度有多快？我之所以做这个对比，纯粹是因为我自己在做市场调研，想弄清楚它们之间到底孰优孰劣、各自的短板在哪里。我公开发布了一部分数据，那大概是两周前，距今正好 16 天，结果网站彻底火了。目前网站访问量已经突破 10 万次，基本上每一位赛道里的创始人都主动联系了我。我认为这充分证明了大家的普遍好奇：人们迫切想知道这个行业的演进方向。

<details>
<summary>Original English</summary>

**David Pawlan**: Assistant Benchmark is a site that essentially compares all these AI assistants on a use case basis. So we're asking all of these assistants the same prompt. Book me a flight to Chicago. Find me a vegetarian restaurant within five blocks of my specific location, etc., etc. And we're comparing the actual outcome on like on a one-shot prompt. Does it actually work? Does it ask follow-up questions? How does it perform across 16 different dimensions? And we compare those all. So, it's we use the word benchmark. Think of it more as like a consumer-facing benchmark, not necessarily technical behind the scenes, but if I want to book a flight, which one should I actually use? Who is performing the best? How fast are they actually replying? Got into this whole comparison because I was just doing market research myself trying to figure out how are these all comparing against one another? What are the gaps? And published a bit of that and it was almost two weeks ago. It's 16 days ago today that we launched it and it's just absolutely exploded. It's, you know, over 100,000 views on the website has had over 100,000 visitors have had outreach from basically every single founder. And I think it really just goes to show like everyone's curious. People are looking for answers to where this industry is moving.

</details>

---

### 市场全景：通用 Agent 与垂直领域的分野

**阿尼什·阿查里亚**: 给我们详细讲讲，大卫。这确实令人兴奋。很有意思的是，评测基准现在已经成了行业对话的核心支柱，因为新产品层出不穷，单靠个人根本不可能把每一个都试一遍，这也说明市场生机勃勃。除了 Instinct 和 Muse 之外——我们稍后一定会对它们进行深度拆解——你觉得还有谁在做有意思的事情？你观察到了哪些垂直专业化的方向？

<details>
<summary>Original English</summary>

**Anish Acharya**: And so talk us through David. That's incredibly exciting. It's cool to actually It's funny how benchmarks have become such a staple now of the conversation because there's so many launches it's hard to try everything which is also an exciting signal. Maybe talk us through everybody who's not Instinct and Muse. We're definitely going to deep dive on those later, but who else do you think is doing interesting work and what are the kind of directions of specialization that you're seeing?

</details>

**大卫·鲍兰**: 没问题。市面上确实有大量的长尾解决方案。我认为大体可以分为两大类。第一类是面向 B2C 消费者的通用型 Agent（Generalized Agents），代表就是 Instinct 或 Muse。长尾阵营里还有 Caddy、Ali、**Season** 等。目前在我们的网站上，光是通用类别下就有 64 个产品。在通用类别内部，我们还可以进一步细分，比如专门针对**出行旅行**的助手，像 **Soar** 或 **Miso**；或者专门针对**电子邮件**的助手。

光谱的另一端则是面向 **B2B 工作流**的助手，包括从 **The Town** 到 **Catch** 再到 **Vellum** 等。它们本质上做的事情很相似：充当更偏向高管执行助理（Executive Assistant）的角色，而不是消费端的打法。这就是目前的大致格局。据我目前的统计，市面上总共有 122 个不同的 AI 助手产品。

<details>
<summary>Original English</summary>

**David Pawlan**: Totally. So, we've got a bunch of longtail solutions out there. I think I would categorize it into two groups. You have like the B2C consumer-facing generalized agents. That's like the Instinct or Muse. Some of the longer tail ones, you have Caddy, you have Ali, you have Season. There's I believe 64 right now just in the general category on the site and then we can break that down even further into a little more specialized within that. So you can have travel specific ones like Soar or Miso. You can have email specific ones. The other side of the spectrum is going to be more of like your B2B workflow type assistants. And those are, you know, anyone from The Town to Catch to Vellum. And they're all essentially doing the same thing, right? They're your assistant that's actually like more of like an executive assistant, not the consumer-facing approach to it. And that's kind of like the general landscape at the moment. So far to my knowledge there are 122 different ones.

</details>

**阿尼什·阿查里亚**: 哇，跨越所有类别总共有这么多。太惊人了。那么在这些领域中，竞争最激烈、最有趣的焦点在哪里？

<details>
<summary>Original English</summary>

**Anish Acharya**: Wow. Across all the categories. Incredible. And what about areas of concentration? Where is the most sort of interesting competitive focus?

</details>

**大卫·鲍兰**: 目前来看，绝大多数产品仍然集中在通用型方向上，大家都试图包揽一切。

<details>
<summary>Original English</summary>

**David Pawlan**: So everyone right now by and large is focusing on the generalized like... Just trying to do everything.

</details>

**阿尼什·阿查里亚**: 对，大家都想成为无所不能的助手。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yep. Just trying to do trying to do everything.

</details>

**阿尼什·阿查里亚**: 比如拿旅行来说，旅行是一个**低频但高价值**（Infrequent High Value）的行为。你认为这个方向行得通吗？垂直的旅行 Agent 会胜出吗？

<details>
<summary>Original English</summary>

**Anish Acharya**: And when you think about something like travel, just to pick on that, that's an infrequent high value behavior. Do you think that works?

</details>

**大卫·鲍兰**: 我觉得或许能出现一个独立的优胜者，但总体而言，我认为现在的很多垂直噱头更多是在博取眼球，实用性还不够。

如果你去看前三大核心用例：
排名第一的是**日常行政琐事**（Daily Admin），比如清理收件箱、处理杂务。
第二类是**智能体编排**（Agent Orchestration），这非常有趣。现在的各种群聊机制有点火，但老实说，这些群聊里大多是科技推特圈的人，并不能代表真实世界。

<details>
<summary>Original English</summary>

**David Pawlan**: I think you're going to maybe see potentially one winner as an independent agent, but by and large I really think it's more of a gimmick, right? It's an attention grabber. What are use cases one to three? So, number one is more just daily admin type stuff, whether it's cleaning out your inbox, whatever. The second is going to be more agent orchestration, which is really interesting. I think these group chats are a little... these are all group chats with people in tech Twitter, right? So, it's not necessarily representative of the world.

</details>

**阿尼什·阿查里亚**: 确实如此。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah.

</details>

---

### 隐形 Agent 与财务行政的高价值场景

**大卫·鲍兰**: 最后一个大类是**个人财务**（Finance）。我认为这是最有趣的一个方向。

<details>
<summary>Original English</summary>

**David Pawlan**: And then the last category being finance. I think that's the most fun one to look into.

</details>

**阿尼什·阿查里亚**: 这点非常有意思。知名科技分析师 **本·汤普森**（Ben Thompson）曾写过一篇很棒的文章，提出一个批评观点：普通消费者其实根本不想把自己的生活当作一家小企业来经营，他们不需要所谓的“生活 ERP”。但我确实觉得财务是一个存在海量**行政负担**（Administrative Overhead）的领域。如果你看看金融市场或各种利润池，其实到处都充满了摩擦成本。所以我虽然赞同 Ben 的观点——消费者更倾向于寻求娱乐和多巴胺，而不是追求工作流程优化——但如果有一个 Agent 能够真正帮你省钱，或者替你承担繁琐的财务交涉，这就完全是另一码事了。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah. Yeah. It's really interesting because one of the critiques, you know, Ben Thompson wrote this great piece, which is like the general consumer does not want to run their life like a small business. But it does feel like finance is an area in which there is a ton of administrative overhead. And if you look at, you know, the number of financial markets or financial sort of profit pools, there's friction everywhere. I do think that, while I generally agree with Ben that most consumers are looking for distraction and amusement and entertainment rather than optimization, having an agent that can save you money or do the financial heavy lifting feels very different.

</details>

**大卫·鲍兰**: 完全正确。这恰恰切中了我的核心论点：这个世界未来的走向，在于 Agent 的**不可见性**（Invisibility）。你雇佣一个助理，是为了让他保持“隐形”，对吧？最好的员工就像一个默默运转的齿轮，你甚至感觉不到他的存在，但所有事情都被打理得井井有条。

我所见过的最好、最主动的用例，基本都落在财务领域。我们即将看到这种场景的大爆发，比如你根本不需要打开 App。举个我自己的真实例子：每次我订机票后，只要该航班随后降价，我的助手就会主动联系航空公司，帮我把差价换成旅行代金券（Travel Credit）。

<details>
<summary>Original English</summary>

**David Pawlan**: Totally. And I think that touches on the general thesis to where I think the world is going. You hire an assistant to allow it to be invisible, right? Like the best employee is someone that's just a cog in the wheel and they run invisible and stuff just gets done. And the best, most proactive use cases I'm seeing, I think, do fall in the financial space. And I think we're going to see an explosion in a world where it's not even opening an app. Or one that I do is anytime I book a flight, if the flight price drops, I then have my assistant hit up the airline and get me a travel credit.

</details>

**阿尼什·阿查里亚**: 太棒了。

<details>
<summary>Original English</summary>

**Anish Acharya**: Wow.

</details>

**大卫·鲍兰**: 我还有一个朋友，这可能是我见过的最喜欢的用例：他家草坪的喷淋系统是根据天气预报自动联动的，如果明天要下雨，Agent 就会自动关掉喷淋，这直接让他的水费账单大幅下降。因此，我认为正是这些**隐形智能体**（Invisible Agents）在后台替你默默做事、实打实帮你省下真金白银，才会成为大众市场的引爆点。

<details>
<summary>Original English</summary>

**David Pawlan**: And I have a friend, this is my favorite use case I think I've seen yet. His sprinklers are dependent on the weather and it's dropped his water bill. And so I think these invisible type agents that are going to be doing things in the background to actually save you money are what's going to drive it.

</details>

**阿尼什·阿查里亚**: 没错。美国消费者没有人愿意为了把效率提升 10% 去专门买一个工具。普通大众不在乎效率提升 10%，但我认为能真正吸引广大用户的钩子，在于**为你省钱**。如果它能直接帮你省下真金白银，那吸引力就完全不同了。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah. It'll be interesting too. Like I think the American consumer, nobody wants to be 10% more efficient. The general population does not care about being 10% more efficient. And I actually think the hook that's going to get a lot of people here is it's going to save you money. If it can literally save you dollars, that's very compelling.

</details>

---

### 交互界面与载体：短信、WhatsApp 还是新硬件？

**大卫·鲍兰**: 确实如此。从应用落地和交互载体的角度来看，未来的世界会极其有意思。你怎么看接下来的演进？你认为未来会出现多套并存的交互界面吗？

<details>
<summary>Original English</summary>

**David Pawlan**: Totally. It's going to be a very interesting world in terms of the application of it. And so like where do you see this world moving? Do you believe that multiple interfaces exist?

</details>

**阿尼什·阿查里亚**: 这是一个绝佳的问题。我认为这也是为什么目前有如此多尝试的原因。在不同国家，人们使用的主要沟通渠道截然不同，甚至在一定程度上还会因人群习惯产生分化。在美国，iMessage 是最神圣、最珍贵的私人空间。当我在 iMessage 里与某个产品互动时，会感觉那是一段非常私密的关系。而现在我们看到 Instinct 和其他几个产品正是扎根在 iMessage 里面。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah, that's a great question, man. I mean, I think this is why there's so much surface area. Different countries use different channels, part of it may actually fragment by demographic as well to some extent. In the US, the iMessage space is more precious. So it feels like a more personal interaction when I'm in that space. And now obviously Instinct and a few others are in iMessage.

</details>

**大卫·鲍兰**: 完全赞同。iMessage 带来的**个性化沉浸感**极强，感觉就像在给一个真人朋友发短信。不过大体上我目前只看到两种主流交互界面：要么是基于短信的聊天窗口，要么是 **WhatsApp**。而 Muse 则试图引入完全不同的交互媒介——比如**硬件**，这非常值得探讨。

<details>
<summary>Original English</summary>

**David Pawlan**: Yep. I completely agree. The personalization that comes with iMessage, it feels like you're texting a human. And I really have only though seen by and large two surfaces appear: it's either an SMS-based chat, or it's WhatsApp. And then you have Muse that they're trying to introduce as a different surface, which is pretty interesting.

</details>

---

### 硬件载体之争：Muse 智能吊坠 vs 智能眼镜 vs 语音

**阿尼什·阿查里亚**: 这一点极其迷人。曾经有位智者说过：“硬件是灵魂在物理世界的表达。”虽然硬件赛道往往是创业公司的坟场，但我依然觉得硬件领域蕴藏着巨大的机会。

<details>
<summary>Original English</summary>

**Anish Acharya**: I think it's fascinating. I mean, a smart person said this, which is that hardware is the physical manifestation of soul. But I think hardware is a graveyard of startups, but I do think there's actually something there with hardware.

</details>

**大卫·鲍兰**: 我有一个激进的假说：我认为这款 Muse 吊坠其实根本不是为了去赢下消费级硬件战争，它的核心是为了在真实世界中**收集海量数据**，为扎克伯格构建真实世界空间映射的元宇宙愿景输送原料。

<details>
<summary>Original English</summary>

**David Pawlan**: I have a hot take thesis that this Muse charm is actually less about trying to win the hardware game and it's more about data collection in the real world to fuel Zuckerberg's future metaverse of mapping out the actual world.

</details>

**阿尼什·阿查里亚**: 但难道他们不能直接从 **Meta Ray-Ban 智能眼镜** 上获取这些数据吗？

<details>
<summary>Original English</summary>

**Anish Acharya**: But don't you think that they already get that from the glasses?

</details>

**大卫·鲍兰**: 智能眼镜确实在一定程度上能做到，但我不知道吊坠上是否配备了摄像头。如果带了摄像头，它就是一个无处不在的被动记录仪。

<details>
<summary>Original English</summary>

**David Pawlan**: I think they do to some extent, but I don't know if the charm has a camera. If it does, it's just a passive recording device everywhere.

</details>

**阿尼什·阿查里亚**: 我觉得吊坠可能没有摄像头。我认为吊坠的设计初衷是偏向于首饰和佩戴体验。我之前体验过各种 VR 和可穿戴设备，智能眼镜之所以让人惊艳，是因为人们开始习惯把科技戴在身上，并享受那种无缝的技术连接感。但我认为最强大的交互形态其实是**音频与语音**。

<details>
<summary>Original English</summary>

**Anish Acharya**: I don't think so. I think the charm is meant to be more jewelry. It's going to be fascinating. I think there's something really compelling to that. People like feeling like they have the technology connectivity with them. But I think audio is incredible.

</details>

**大卫·鲍兰**: 我对**语音和音频**极其看好！昨天 ChatGPT 发布了高级语音模式（Advanced Voice Mode），我今天早上骑车上班时试用了，那简直是我的第二个“顿悟时刻”（Magic Moment）。当时我双手握着车把腾不出手，但我又想把工作处理完，于是我就直接对着 ChatGPT 语音说话。在骑行的路上，它帮我回复了多封邮件，发出了日历日程邀请。等我骑到工位坐下时，我的邮箱已经达到了 **Inbox Zero**（收件箱清零）。

<details>
<summary>Original English</summary>

**David Pawlan**: Audio is incredible. I'm quite bullish on voice and audio. ChatGPT voice yesterday launched Advanced Voice. I played around with it this morning and to me it was my second magic moment, really. I was biking to work, hands are busy, I want to get stuff done, and I just start talking to ChatGPT voice. Replied to different emails, sent out calendar invites, got to the desk, inbox zero.

</details>

**阿尼什·阿查里亚**: 太不可思议了！所以你用的是 ChatGPT Voice，而不是 Muse，对吧？

<details>
<summary>Original English</summary>

**Anish Acharya**: It's incredible. And so, this is ChatGPT voice, not Muse, correct?

</details>

**大卫·鲍兰**: 没错，是 ChatGPT Voice。对于普通消费者来说，如果一个 AI 助手必须强迫你打开手机去按一个按键，那它就依然存在巨大的阻力。沉迷于手机的科技圈人群习惯了打字，但要让大众真正接纳，能够随时随地通过语音对话完成一切，才是质的飞跃。

<details>
<summary>Original English</summary>

**David Pawlan**: Correct, ChatGPT voice. For the general consumer, an assistant where you have to take out your phone and push a button is still friction. The tech bubble is chronically online and on their phone, but to hit mass adoption, voice changes the game.

</details>

---

### 社交属性与 Agent 人格：主动性才是真正壁垒

**阿尼什·阿查里亚**: 接下来我想跟你探讨的是**社交属性**（Social）。很多产品都在尝试社交化，你见过哪些真正奏效的做法？你对社交层面的演变有什么推论？

<details>
<summary>Original English</summary>

**Anish Acharya**: So the next thing I wanted to talk to you about was social. A lot of people have tried it. Have you seen anything that works well? And what are your kind of theories for how this evolves?

</details>

**大卫·鲍兰**: 很多人都在做社交尝试，我总结下来大致有三种路线。比如像 **Doc**，它走的是在你的专属网络内进行协同和分享的路线，体验很惊艳。

<details>
<summary>Original English</summary>

**David Pawlan**: A lot of people have tried it. I think I've seen three different approaches. One is like Doc, where it's within your network and sharing.

</details>

**阿尼什·阿查里亚**: 我一定要去试试 Doc，而且它是 a16z 投资的企业。

<details>
<summary>Original English</summary>

**Anish Acharya**: I've got to try that out. I love that. And I love that it's an a16z company already.

</details>

**大卫·鲍兰**: 你确实该试试 Doc。我这周听到的另一个非常有意思的观点是：Agent 自身可以直接在社交平台上发帖，你可以跟它互动，其他人也可以跟它互动。我们似乎在试图将这些 Agent **拟人化**（Humanize）。大众对 AI 生成的合成人表现出了极大的兴趣，但在你的个人私密空间里，大家又会觉得这有点古怪。

<details>
<summary>Original English</summary>

**David Pawlan**: Totally. You should give Doc a try. The other interesting take that I heard this week was that an agent can make a post and you can either engage with it or others can. It's almost as if we're trying to humanize these agents. And the world has fallen in love with AI-generated humans, but in your personal space people feel a little weirded out.

</details>

**阿尼什·阿查里亚**: 这引出了一个相关的问题：你认为市场是否会根据 **Agent 的性格特征**（Personality）产生细分？

<details>
<summary>Original English</summary>

**Anish Acharya**: So one related question I wanted to ask you is do you think that the market segments by personality of the agent?

</details>

**大卫·鲍兰**: 每个人肯定都有自己偏好的沟通风格。像 Poke 一上线就非常火爆，它的性格极其鲜明、调侃刻薄、个性强烈。但我认为**性格并不是一个具有防御性的壁垒**（Defensible Moat），因为调整性格太容易了，无非是一段系统提示词（System Prompt）的设定。

<details>
<summary>Original English</summary>

**David Pawlan**: I think everyone for sure prefers a different style of communication. Poke came out of the gates hot, right? The personality of Poke is quite distinct. But I don't think personality is really a defensible moat because it's quite easy to copy.

</details>

**阿尼什·阿查里亚**: 这个观点很有启发，我也同意你的看法。但我试着为反方做一下“强力辩护”（Steel Man）：如果我们把“性格”定义得更严肃一些，称之为 Agent 的**内在宪章**（Constitution）——它决定了 Agent 的行动偏好。比如，有的 Agent 天生激进主动，哪怕有 10% 的概率犯错，只要能替你把事情抢先办好，你也宁愿接受它的失误；而有的 Agent 则极其保守严谨。从这个维度看，这种行为宪章是否构成壁垒？

<details>
<summary>Original English</summary>

**Anish Acharya**: That's interesting and I agree with you, but maybe let me try the steel man argument. If you think about personality as a constitution, which is an example of an aggressive bias to action, and you'd rather have it make mistakes 10% of the time as long as it gets stuff done... Is that a moat?

</details>

**大卫·鲍兰**: 我认为**主动性**（Proactivity）具有极大的防御壁垒！真正的分水岭就在于此。

工作流本质上可以划分为两类：
第一类是你必须**保留控制权**（Retain Control）的工作流。如果 Agent 擅自替你做出重大决定，比如直接更改航班或转账，这需要你在外部行动上做出配合，就必须提前获得你的明确许可。
第二类则是像“我已经为你起草好了这封邮件”、“我发现机票降价并自动帮你申请了退款代金券”这种场景。你完全不需要介入任何操作，它默默帮你省下了时间和金钱。这种主动执行的能力，有着极深的壁垒。

<details>
<summary>Original English</summary>

**David Pawlan**: I think there is massive defensibility around proactivity. It really does come down to two categories. There's some workflows where you want to retain control and you don't really want an agent to be acting too proactively without permission, because that requires a change in action on your side. However, the proactiveness of "Hey, I drafted this email for you" or "I got a flight credit," there's no action needed on your side. It's just saving you money, saving you time.

</details>

**阿尼什·阿查里亚**: 哈哈，这真的太有意思了。我们内部之前还开玩笑说，估计要不了几天，就会有 Agent 替主人向约会对象发消息说：“我注意到你最近对她其实没那么上心，所以我已经替你发消息跟她分手了。”

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah, it'll be interesting. You know, we were joking internally like we're days away from an agent messaging someone saying "I noticed you weren't that into her so I went ahead and broke up with her."

</details>

**大卫·鲍兰**: 鉴于推特上大家对这个段子的狂热转发，我毫不怀疑绝对会有开发者把这个做出来，至少能成为爆款梗。

<details>
<summary>Original English</summary>

**David Pawlan**: I would assume so purely given the traction of that post, at least just a source of comedic popular tweets.

</details>

---

### 垂直 Agent 的生存空间：针对母职群体的场景洞察

**阿尼什·阿查里亚**: 确实。目前市场的一个大背景是：大多数通用消费级 Agent 都在使用相同的底层模型（如 OpenAI、Claude 等）。你认为那些专注于**细分垂直领域**（Vertical/Narrow Startups）的创业公司该如何突围？

<details>
<summary>Original English</summary>

**Anish Acharya**: Right. It feels like one of the big things that's happening is most consumer agents are just thin wrappers on the underlying models. Do you think there are narrow startups that can win? Give us some insight on what narrow startups mean to you.

</details>

**大卫·鲍兰**: 老实说，现在市面上很多所谓的消费级 Agent，本质上只是把底层大模型包装了一下。它们的唯一优势，就是帮用户省去了繁琐的 API 配置步骤，普通人花 20 美元买个现成开箱即用的产品而已。

但我认为真正的机会在于**深度垂直化**。比如我不做通用助手，而是把全部精力聚焦在“**全职妈妈的日常助理**”上。这个 Agent 深入理解一位母亲管理家庭的全部日常：从孩子的日程表、课后接送、儿科医生的预约细节，到学校的各种通知。这种深度垂直的理解和工作流定制，是通用模型无法直接开箱提供的。

<details>
<summary>Original English</summary>

**David Pawlan**: Right now I honestly see the consumer agent is literally just a replication of the underlying model. It's just a matter of fact that you don't have to configure everything and you're paying $20 for convenience. But instead of being a generalist, if I spend all my time focusing on an agent that knows everything about how a mother operates her day-to-day life—child drop-offs, doctor appointments—that is a very compelling narrow startup.

</details>

**阿尼什·阿查里亚**: 就像现实世界中拥有顶级审美、能帮你订到最难订餐厅的顶级礼宾（Concierge）一样，垂直领域拥有特定的领域智慧。

<details>
<summary>Original English</summary>

**Anish Acharya**: Like a concierge that's got A+ taste to get you into restaurants. It's specialized.

</details>

---

### Assistant vs. Agent：从执行指令到拥有“能动性”

**大卫·鲍兰**: 接下来这个话题我也很想听听你的深度见解：推特上大家一直在交替混用 **Assistant**（助手）和 **Agent**（智能体）这两个词。未来到底是属于 Personal Assistant，还是属于 Personal Agent？这两个词对你来说分别意味着什么？

<details>
<summary>Original English</summary>

**David Pawlan**: We interchange between assistant and agent, and it's been a constant conversation on Twitter. Is the future going to be a personal assistant or a personal agent, and what do those mean to you?

</details>

**阿尼什·阿查里亚**: 问得太好了！在我看来，“Assistant”（助手）是一个相对低能级、被动的角色，就像过去的打字员或实习生，你必须明确告诉它“去做 A、做 B、做 C”，它才能去机械执行。

而“Agent”（智能体）的核心在于它拥有**能动性**（Agency）。它能够在不需要你一步步下达指令的前提下，主动理解目标、进行自主规划并把事情在现实世界中办妥。在企业级 AI 中，我们已经看到 AI 从最初干杂活的实习生，逐步进化到能够独立接管复杂的端到端业务。而在消费端，拥有 Agency 的 Agent 才是真正的未来。

<details>
<summary>Original English</summary>

**Anish Acharya**: Oh, that's such a great question, man. I mean, to me, assistant is a sort of less capable role—an assistant can only do what you explicitly tell it to do. While an agent has agency, and can just make good things happen in the world autonomously. In enterprise AI they started as interns and then through agency took on more specialized and delicate work.

</details>

---

### 机器仲裁与社会间接层：人际关系的全新缓冲

**大卫·鲍兰**: 我非常赞同。我也非常好奇这对人类社会的深远影响。我们在旧金山这个科技泡沫的中心，有时外界会质疑我们脱离现实，但我觉得这就是未来的缩影。

<details>
<summary>Original English</summary>

**David Pawlan**: I'm super aligned. I'm also very interested in what ramifications it might have. We're in SF, in the tech bubble, but I just think this is like the future.

</details>

**阿尼什·阿查里亚**: 我不觉得这只是泡沫，这就是未来。而且我认为 Agent 的普及实际上能大幅改善社会人际关系。因为 Agent 具有非人属性，它可以在人与人之间提供一层**社会间接层**（Social Indirection）。比如在面对人际冲突或尴尬交涉时，它能充当**化解正面冲突的仲裁者**（Arbiter of Confrontation）。

<details>
<summary>Original English</summary>

**Anish Acharya**: I don't know if it's a bubble, I just think it's like the future. I actually think that it could improve a lot of social interactions. The agent, as a non-human, can provide a layer of social indirection, like an arbiter of confrontation.

</details>

**大卫·鲍兰**: 潜在确实如此！我并不是提倡大家变得更加被动回避，但它确实能够消除许多无谓的情绪损耗，让人类把精力集中在真正美好的事物上。小时候我母亲常对我说：“外面的世界那么美好，你整天坐在电脑前干什么？”如果 Agent 能够帮我们把所有讨厌的日常行政杂务（Life Admin）全部自动化接管，我们就能真正解放出来去体验真实世界。

<details>
<summary>Original English</summary>

**David Pawlan**: Potentially. Yeah. I'm not advocating for a more passive world, but it eliminates unnecessary friction. I grew up with my mother saying: "It is a beautiful world out there, what are you doing in front of the screen?" Hopefully it allows us to automate so many of these tasks—the life admin work—so we can enjoy life.

</details>

**阿尼什·阿查里亚**: 没错！这正是技术的意义所在，让生活变得更有趣、更充实。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah, that's right. That's why technology makes life more fun and more interesting.

</details>

---

### Agent-to-Agent 交互新范式与商业生态重构

**阿尼什·阿查里亚**: 回到近期的现实问题。我一直在思考一个必然会出现的范式：未来一定会诞生大量**完全专属于 Agent-to-Agent 之间交互的基础设施与产品**。在那个世界里，机器与机器直接对话，你认为那会是一幅怎样的图景？

<details>
<summary>Original English</summary>

**Anish Acharya**: You know, to kind of come back to the near-term, a thing that I've been thinking about: it does feel like there's going to be infrastructure and products that exist only for agent-to-agent interactions that doesn't exist today. What do you think that looks like?

</details>

**大卫·鲍兰**: 这将是一个全新的范式！未来每个 Agent 都会拥有自己的专属电子邮箱、专属电话号码，甚至拥有自己的去中心化身份识别。随后就是庞大的**网络安全**（Cybersecurity）与鉴权体系：如何验证对方是一个合法的 Agent？如何防止欺诈和恶意调用？这里蕴含着极其巨大的创业机会。

<details>
<summary>Original English</summary>

**David Pawlan**: It's going to be a whole new paradigm. You have agent emails, agent phone numbers, agent identities. And then you have the whole cybersecurity component: how do you verify an agent, how do you prevent abuse? There are so many niche problems to solve to build this new world.

</details>

**阿尼什·阿查里亚**: 尤其是在**电商与消费**（Commerce）领域，这种变革更为剧烈。你如何看待最近 **Amazon** 和 **Shopify** 之间发生的动态？

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah, especially commerce. Do you have a view on what specifically happened with Amazon and Shopify?

</details>

**大卫·鲍兰**: Shopify 和 Amazon 是完全不同的商业飞轮。Amazon 的核心商业模式本质上是依靠巨额的**广告展示与搜索竞价**，如果每个消费者都派出自己的 Agent 直接去抓取并购买最划算的商品，Amazon 原有的广告利润池就会被大幅削弱。

而当每个人都拥有自己的 Agent 时，博弈权力会重新洗牌。比如在餐饮外卖领域，权力会不会从抽成高昂的聚合平台重新回流到餐厅本身？因为 Agent 可以直接跨过中介平台，直接与商家的底层系统对接交易。

<details>
<summary>Original English</summary>

**David Pawlan**: Shopify and Amazon are two completely different business models. Amazon makes so much profit from advertising and sponsored placements. If an agent just bypasses that and buys the optimal product, it takes a lot of profit out of their experience. And when everyone has an agent, does power go back to the merchants and restaurants instead of the platforms?

</details>

**阿尼什·阿查里亚**: 你说的太对了。传统互联网依靠信息差和展示位收税，而 Agent 的普及将彻底颠覆现有的搜索和推荐机制。当 Agent 帮你买一双普通白袜子时，互联网上有两万种白袜子，Agent 根本不需要看广告，它只会根据绝对的性价比和质量进行客观匹配。

<details>
<summary>Original English</summary>

**Anish Acharya**: Yeah, I think you're super right. In the Amazon/Shopify dynamic, advertising gets disintermediated. If there's 20,000 types of white socks, an agent doesn't care about ads, it just wants the best socks for your criteria.

</details>

**大卫·鲍兰**: 现在的 AI 和大模型在某种程度上“打破”了原有的互联网流量逻辑。Muse 在这方面有先发优势，在商业消费的全新世界里，长尾独立品牌反而迎来了巨大的红利。

<details>
<summary>Original English</summary>

**David Pawlan**: AI feels like it kind of broke the internet in terms of discovery. Muse has probably a head start in this world of commerce, and it could be huge for longtail independent sellers.

</details>

**阿尼什·阿查里亚**: 没错！这能够让互联网回归到**以消费者利益为第一优先级**（Consumer-Aligned Internet）的真正健康状态。

<details>
<summary>Original English</summary>

**Anish Acharya**: It opens the door to a truly consumer-aligned internet, which I think we haven't had in a long time.

</details>

---

### 商业模式与经济账：长尾创业公司的破局点

**大卫·鲍兰**: 聊到这里，我们不得不谈谈 Agent 的**经济模型**（Economics）。在 Assistant Bench 收录的 122 个产品中：
有 65 个是付费的；
其中 35 个是纯预付费订阅制，30 个采用免费增值模式（Freemium，达到限额后收费）。

长尾初创公司到底该如何在这个高昂推理成本的市场里活下来？为什么有些产品每月收费高达 100 美元甚至更高？

<details>
<summary>Original English</summary>

**David Pawlan**: We touched on the economics of the agents. Of the 122 that I have on the site, 65 are paid. 35 are fully paid, 30 are freemium. How does a longtail startup actually win this space? And why are they charging so much?

</details>

**阿尼什·阿查里亚**: 伙计，对于初创团队来说，目前的挑战确实极其严峻。根据我们的测算，目前许多端到端智能体的单次复杂调用成本极其惊人。如果是做非常宏大的任务自动化，单月的算力和浏览器模拟成本非常高昂。

但我也坚信，**浏览器操作**（Browser Use）和推理调用的成本会迅速下降，正如过去每一次计算成本断崖式下跌一样。随着基础设施的成熟和轻量模型的优化，长尾初创公司将能够以极低的成本运行高可用 Agent，届时我们将迎来消费级 Agent 真正的应用大繁荣。

<details>
<summary>Original English</summary>

**Anish Acharya**: Man, it's going to be really challenging. By our estimate, it's costing a ton to run these ambitious workflows today. But I think it's very possible that browser use gets cheap enough that more startups can survive and thrive. It's going to be fascinating to see.

</details>

**阿尼什·阿查里亚**: 非常精彩。来自 Assistant Bench 的大卫，非常感谢你今天的做客。大家一定要去访问体验 Assistant Bench 这个网站。我们以后会频繁进行这种对谈，感觉每周都有聊不完的新进展。请大家在 X（Twitter）上关注大卫，也欢迎关注我，让我们一起在社区中学习探讨。祝你和你的 Agent 们度过愉快的一天！

<details>
<summary>Original English</summary>

**Anish Acharya**: Super interesting. Well, David from Assistant Bench, make sure everybody checks it out. Thank you so much for joining us. We're going to do this frequently. I feel like we could do this every week, things are happening every single day. Please follow him on X, follow me as well. Happy day to you and your agents.

</details>

**大卫·鲍兰**: 非常感谢，我也觉得今天聊得特别开心！

<details>
<summary>Original English</summary>

**David Pawlan**: Appreciate it. Same to you. This is fun.

</details>

**阿尼什·阿查里亚**: 好的兄弟，谢谢你！

<details>
<summary>Original English</summary>

**Anish Acharya**: All right, brother. Thank you.

</details>

**大卫·鲍兰**: 太棒了！

<details>
<summary>Original English</summary>

**David Pawlan**: Awesome.

</details>