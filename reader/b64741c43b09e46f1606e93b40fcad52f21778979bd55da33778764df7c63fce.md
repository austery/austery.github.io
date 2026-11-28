---
author: All-In Podcast
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DVBJQQCjgXU
speaker: All-In Podcast
tags:
  - anthropic-revenue
  - ai-safety
  - coding-agents
  - geopolitics
  - cyber-security
title: Anthropic 营收神话：300亿美金背后的 AI 军备竞赛、Mythos 安全博弈与中东地缘政局
summary: 本期访谈深度剖析了 Anthropic 令人惊叹的财务增长——营收从 10 亿暴涨至 300 亿美金，标志着 AI 商业化的爆发。Besties 讨论了 Anthropic 扣留 Mythos 模型的“安全营销”策略，以及其与 OpenClaw 的竞争黑幕。此外，节目还探讨了特朗普推动下的伊朗停火协议，以及 X 平台自动翻译功能对打破地缘政治信息壁垒的深远影响。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Dario Amodei
  - Sam Altman
  - Donald Trump
  - Benjamin Netanyahu
companies_orgs:
  - Anthropic
  - OpenAI
  - Microsoft
  - Google
  - Meta
  - X
products_models:
  - Claude
  - Mythos
  - Spud
  - OpenClaw
  - Blackwell
media_books:
  - New Yorker
status: evergreen
---
### 告别反思，拥抱行动

**查马斯**: 你认为在 100 天内，会有多少个 PR（拉取请求）被推送到**核心结构化互联网**？那个盘口数字是多少？我给你个数字。

<details>
<summary>Original English</summary>

**Chamath**: How many PRs you think are going to get pushed to the core structural internet in 100 days? What's the overunder number? Cuz I'll give you a number.

</details>

**萨克斯**: 你肯定会说零。我的回答是……

<details>
<summary>Original English</summary>

**Sachs**: You're going to say zero. My my answer to that is

</details>

**查马斯**: 我会说大概 10,000 个。但它会立即生效……

<details>
<summary>Original English</summary>

**Chamath**: I'll say like 10,000. But it's going to be immediately

</details>

**布拉德**: **查马斯**，如果这能防止你的浏览器历史记录被泄露给全世界，你可能愿意等这 100 天。

<details>
<summary>Original English</summary>

**Brad**: if it prevents your browser history from being released to everybody in the world, Chamath, that may be something that you're willing to, you know, let 100 days pass on.

</details>

**杰森**: 我看你提到浏览器历史记录时，查马斯立刻来精神了。

<details>
<summary>Original English</summary>

**Jason**: I think you got Chimat's attention when you said browser history.

</details>

**查马斯**: 那那些私密照片怎么办？

<details>
<summary>Original English</summary>

**Chamath**: What about the dickpicks?

</details>

**杰森**: 查马斯会自己发布它们的。好了，让你们的盈利奔跑吧。我们把代码开源给粉丝，他们已经为此疯狂了。爱死你们了。

大家好，欢迎回到世界排名第一的播客。**大卫·弗里伯格**这周不在，但代替他的是我们唯一的“第五位好哥们”——**布拉德·格斯纳**。我是说，布拉德，你怎么不再在发薪日给我来点“合十礼”了？你以前经常……

<details>
<summary>Original English</summary>

**Jason**: Chamat is he's going to release them himself. We'll let your winners ride. We open source it to the fans and they've just gone crazy with it. Love you. All right, everybody. Welcome back to the number one podcast in the world. David Freeberg is out this week. But in his place, the one, the only, our fifth bestie, Brad Gersonner. I mean, why don't you ever give me puts a little namaste in your payday anymore? You used to be

</details>

**查马斯**: 我打算找回那位最伟大的主持人，但现在感觉有点……你知道吗？这些家伙揍了我，他们把我做这个节目的乐趣都打跑了。

<details>
<summary>Original English</summary>

**Chamath**: I'm going to bring back the greatest moderator, but now it's just kind of You know what? These guys beat me up. They beat me up and they just beat the the joy out of me doing this program.

</details>

**杰森**: 那是因为你现在成了**罗安娜**（Roana）的辩护士。

<details>
<summary>Original English</summary>

**Jason**: It's because you're a Roana apologist now.

</details>

**查马斯**: 不，我会解释的。等会儿再说，什么罗安娜辩护士。我只是说，“嘿，他们已经停止了无脑刷存在感，开始做一些逻辑通顺的事情了。” 没错。好吧，我们开始。

<details>
<summary>Original English</summary>

**Chamath**: No, I We'll get into it. Okay. Save it for the [ __ ] Roana apologist. just because I said like, "Hey, they've stopped [ __ ] maxing and they've started doing like some logical things." Uh, yeah. Okay, here we go.

</details>

**布拉德**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Brad**: It's great to be here. Great to be here.

</details>

**杰森**: 欢迎你。当然，我们还有**大卫·萨克斯**也回来了。大家都想听听大卫的看法。上周我们很想念你。

<details>
<summary>Original English</summary>

**Jason**: Good to have you. Good to have you here. And of course, uh, we have David Saxs is back. Everybody wants to hear from David Sax. We missed you last week, bestie.

</details>

**萨克斯**: 我们没有打跑你的乐趣，我们只是试图挤掉你的一些“热空气”。

<details>
<summary>Original English</summary>

**Sachs**: We didn't beat the joy out of you. We just try to beat some of the hot air.

</details>

**杰森**: 那些让你在节目里啰嗦半天却言之无物的废话……

<details>
<summary>Original English</summary>

**Jason**: any any fluff that you can put on the show that just involves you talking and saying nothing is

</details>

**萨克斯**: 没错，我们就是要把那些东西删掉。

<details>
<summary>Original English</summary>

**Sachs**: that's the stuff we got.

</details>

**杰森**: 调大音量。好吧，我们会把它剪掉。我们会剪掉它，然后换成 thesyndicate.com 的广告。谢谢。另外，**查马斯**也在。

查马斯，从上周起你的“无脑刷”进度如何了？你度过了一个完整的“无脑刷”周末吗？是不是一整个周末都在后院甲板上抽雪茄，完全不去反思你过去 20 年造成的那些混乱？

<details>
<summary>Original English</summary>

**Jason**: Turn up. Yeah. Turn up. Okay. Yeah, we'll cut it right out. Um we'll cut it out and we'll just put a promo in for the syndicate.com. Thank you. Also with us, Jamalet is here. How's your [ __ ] maxing going since last week? Did you have a a a [ __ ] maxing full weekend? Did you have a good full weekend of just smoking cigars in the back deck and not ruminating about all the chaos you've caused in the last 20 years?

</details>

**查马斯**: 我认为我做的善事总的来说还是多过坏事的。

<details>
<summary>Original English</summary>

**Chamath**: I think I've done generally more good than than not.

</details>

**杰森**: 哦，确实如此。但总有一些混乱时刻。别想了。

<details>
<summary>Original English</summary>

**Jason**: Oh, you have. But there's been some chaotic moments. Don't think about it.

</details>

**查马斯**: 哥们，你不能只要高潮不要低谷。不然你在那儿干嘛？就为了讨好所有人然后当个失败者？你是为了赢才在那里的。没错，你在竞技场中。但在意识到反思无用后，你停止接受心理治疗了吗？

<details>
<summary>Original English</summary>

**Chamath**: You can't, bro. You can't have ups without downs, man. It's like, what are you there to do? Just like plate everybody and be a loser? Are you there to be a winner? Yes, you're in the arena, but have you stopped going to therapy after realizing ruminating?

</details>

**萨克斯**: 怎么突然对这个“无脑刷”这么感兴趣？你是它的代言人吗？

<details>
<summary>Original English</summary>

**Sachs**: What's up with this uh sudden interest in [ __ ] maxing? Are you like the clavvicular for [ __ ] maxing?

</details>

**查马斯**: 不，是世界终于追上我的脚步了。仅此而已。我一直都在这样做，只是他们以前没起名字。

<details>
<summary>Original English</summary>

**Chamath**: No, the world finally caught up with me. That's it. What do you I mean, I've been [ __ ] maxing this whole time. THEY JUST DIDN'T HAVE A name for it, guys.

</details>

**杰森**: 哇。好吧。**以利亚·隆**（Elisha Long）的视频真的很棒。我这周又看了两个。给我们讲讲，不反思、抽支雪茄、过自己的生活，到底有什么吸引力？

<details>
<summary>Original English</summary>

**Jason**: Wow. Okay. Eli's videos are really good. I watched two more this week. What take us through what's so appealing about not ruminating, smoking a cigar, and just living your life?

</details>

**查马斯**: 因为他说的在社会的各个层面，以及你想要实现的各种事情上都非常管用。即便你试图往上爬，你很快就会学到，你越想要某样东西，你就越得不到。我认为这才是他真正的核心信息：**放下，去生活，去尝试或者不尝试**。我认为这种**抽离感**对人们非常有益。我很喜欢，非常喜欢。

<details>
<summary>Original English</summary>

**Chamath**: Because what he says actually works at every level of society and every sort of thing that you may want to achieve. Even if you're trying to like climb the rungs, you very quickly learn that the more you want something, the less you're going to get it. And I think that's like his real message is let go, live life, and just try stuff or don't try stuff. And I think that that detachment is really healthy for people. I like it. I like it a lot.

</details>

**萨克斯**: 谁说这话的？我其实不知道。

<details>
<summary>Original English</summary>

**Sachs**: Who's the guy who says this? I actually didn't know.

</details>

**查马斯**: **以利亚·隆**。他通常自称 Eli。

<details>
<summary>Original English</summary>

**Chamath**: Elisha Long. Well, Eli, I think, is how he goes by.

</details>

**杰森**: 但他非常出色。在 YouTube 上。

<details>
<summary>Original English</summary>

**Jason**: But he's fantastic. He Mark YouTube channel.

</details>

**萨克斯**: **马克·安德森**发现了他。

<details>
<summary>Original English</summary>

**Sachs**: Mark Andre found him

</details>

**查马斯**: 没错，他说“这家伙就是未来的新星”。

<details>
<summary>Original English</summary>

**Chamath**: and he's like, "This is this guy is the new guy.

</details>

**杰森**: 现代哲学家。他为你如何生活提供了一份路线图，对吧？一位新时代的圣贤。

<details>
<summary>Original English</summary>

**Jason**: Modernday philosopher. He gives you a road map for how to live your life, right? A new age sage.

</details>

**查马斯**: 《沙丘》里那个角色的名字叫什么来着？

<details>
<summary>Original English</summary>

**Chamath**: What's the name of the guy? The character's name from Dune.

</details>

**萨克斯**: 我那时在研究女孩们的书，我在和女孩约会。

<details>
<summary>Original English</summary>

**Sachs**: I was into girls books. I was dating girls.

</details>

**查马斯**: 他就是现代互联网的**李桑·阿尔-盖布**（Lisan al-Gaib）。

<details>
<summary>Original English</summary>

**Chamath**: He's the Lison Algib of the modern internet.

</details>

**杰森**: 这就是为什么我们需要弗里伯格在这里，来解释这些梗。好了，听着。我们有很多议题要谈。基本观点就是：去创造点什么，不要反思。反思不值得。每个人都冲吧。

<details>
<summary>Original English</summary>

**Jason**: This is why we need Freeberg here is to explain these deep holes. All right, listen. We got a lot to get to. Don't The basic point is build something and don't ruminate. Okay, ruminating is just not worth it. Just everybody go for it.

</details>

**查马斯**: 没错，去做事。别在你脑子里瞎逼逼。去做就行了。

<details>
<summary>Original English</summary>

**Chamath**: No, just do stuff. Stop blathering in your own head. Just do stuff.

</details>

### Anthropic 扣留 Mythos：安全还是营销？

**杰森**: 绝对的。好了，说到做事。**Anthropic** 正在扣留其最新模型 **Mythos**（我用的是希腊语发音）。他们说这个模型对我们所有人来说都太危险了。据公司称，该模型自主发现了数千个漏洞，包括每个主要操作系统和 Web 浏览器中的错误。

他们做的这项小研究涵盖了过去几十年来在安全审计中被遗漏的、有 20 年历史的漏洞。举几个例子：他们在 OpenBSD 中发现了一个 27 年前的漏洞，该系统被广泛用于防火墙和关键基础设施。他们在 FFmpeg 中发现了一个 16 年前的错误，该错误在 500 万次扫描后仍被自动化工具遗漏。Linux 内核里也发现了各种错误。他们发布了一个宣传短片，大肆宣扬为什么不向公众分享这个模型。这是 **Dario**（Anthropic CEO）。欢迎随时来节目，兄弟。

<details>
<summary>Original English</summary>

**Jason**: Absolutely. All right. Listen, speaking of doing so, Anthropic is withholding its newest model, Mythos. I'm using the Greek uh pronunciation, its newest model, Mythos, uh saying it is far too dangerous for any of us to have access to it. According to the company, the model autonomously found thousands of vulnerabilities, including bugs in every major operating system and web browser. This uh little study they did included 20 year old exploits that had been missed by security audits for decades. Uh some examples, they found a 27y old vulnerability in OpenBSD used in firewalls and critical infrastructure. They found a 16-year-old bug in FFmpeg that was missed by automated tools after 5 million scans. The Linux kernel, all kinds of uh bugs they found. They released a hype video hyping up why they were not going to share this model. Here's Dario. Come on the program anytime, brother.

</details>

**Dario Amodei（视频内容）**: 由于模型擅长代码，它也顺带擅长**网络安全**。我们实验的模型在识别错误方面基本上和人类专业人士一样出色。这对我们很有利，因为我们可以更早发现更多漏洞并修复它们。它具有将漏洞串联起来的能力。这意味着你发现了两个独立的漏洞，每个单独来看都没什么大用，但这个模型能够利用三、四甚至五个序列化的漏洞制造出攻击手段，从而产生某种非常复杂的最终结果。

<details>
<summary>Original English</summary>

**Dario Amodei (Video)**: But as a side effect of being good at code, it's also good at cyber. The model that we're experimenting with is by and large as good as a professional human at identifying bugs. It's good for us because we can find more vulnerabilities sooner and we can fix them. It has the ability to chain together vulnerabilities. So what this means is you find two vulnerabilities, either of which doesn't really get you very much independently, but this model is able to create exploits out of three, four, sometimes five vulnerabilities that in sequence give you some kind of very sophisticated end outcome.

</details>

**杰森**: 好了。布拉德，顺便说一下，他们用的那个背景房间，就是那些家伙每周日玩《龙与地下城》的地方。布拉德，你是这家公司的投资人。这是在**美德标榜**（Virtue Signaling）还是事实？他们不发布模型、保持谨慎、只把它给少数人去寻找所有错误，这是明智之举吗？我们还有很多问题要讨论。

<details>
<summary>Original English</summary>

**Jason**: All right, Brad, uh, by the way, that set they're using there, that's the same room those guys play Dungeons and Dragons in every Sunday. Brad, you're Brad, you're an investor in this company. Is this virtue signaling or is it reality? Is this a good move by them to not release this model and be thoughtful, give it to a handful of people and just find all the bugs it can before releasing it to the public? And we've got a lot more issues to discuss.

</details>

**布拉德**: 我其实认为他们值得巨大的赞誉，让我来告诉你原因。这家公司本可以直接发布 Mythos，但这可能会破坏互联网的很多核心基础。在硅谷，我们常说“小步快跑，打破常规”。但在这种情况下，如果只是为了超越竞争对手而发布模型，可能会造成巨大的混乱。

他们进行了自己的漏洞测试，发现它会允许主动黑客攻击，泄露浏览器记录和信用卡信息。我喜欢的一点是，他们不需要政府来牵头。他们知道这符合公司和行业的长远利益。所以，他们发起了 **Glasswing 项目**（Project Glasswing），这是一个由 AI 驱动的网络安全联盟，成员包括苹果、微软、谷歌、亚马逊、摩根大通等 40 家最重要的公司。

他们的目标很简单：花 100 天时间，利用先进的 AI 去发现、修复并强化这些软件漏洞，赶在黑客利用它们之前。杰森，我认为这代表了我们正在跨越的一个门槛。Mythos 和 OpenAI 即将发布的 **Spud**（这是 OpenAI 首个基于 Blackwell 训练的模型），代表了 **AGI（通用人工智能）**模型的开端。这些模型的智能实现了巨大的跨越式提升，它们太聪明了，不能立即发布。

顺便说一下，并没有规定说每当你完成一个模型，就必须立即面向公众。他们建立了沙盒机制和防御联盟。这说明你可以信任行业和市场力量与政府的协调。他们正在就此与政府沟通，但并不仅仅依赖于自上而下的监管。这展示了一个非常务实的蓝图。我认为 OpenAI 最终也会这么做，谷歌也会。这是一种保持竞争压力并赢得 AI 竞赛，同时在安全方面做出权衡的积极方式。我认为你总是得做这些权衡。在这种情况下，Dario 团队做得非常好，值得称赞。

<details>
<summary>Original English</summary>

**Brad**: I I actually think they deserve a ton of credit here and let me walk you through why, right? They the company could have just released Mythos, broken a lot of core things on the internet. Often times in Silicon Valley, we say move fast and break things. In this case, it means just releasing the model to move further ahead of your competition. But here the company realized it would wreak havoc. They ran their own vulnerability testing. They saw that it would allow offensive hacking and people to expose browsers and browser history, expose credit cards, you know, on the internet. So, you know what I like about this is they didn't need government to hold their hand on this. We have plenty of government regulations. They know it's in the best long-term interest of the company and the industry, you know. So, they set up Project Glass Wing. It's an AIdriven, you know, kind of cyber coalition. Apple, Microsoft, Google, Amazon, JP Morgan, 40 of the most important companies. And their goal is very simple. Let's spend a 100 days use advanced AI to find and to fix and to harden these software vulnerabilities before hackers exploit them. Now, what I think this represents, Jason, is a threshold that we're crossing. Mythos and Spud, which is going to be out from OpenAI any day now, which is the first Blackwell trained model at OpenAI. They represent the beginning of what I would call AGI models. These are models with massive step function improvements and intelligence. Um, and they're just too smart to be released immediately, you know. And by the way, there was nothing that said that every time you you finish a model, you got to immediately release it GA. So they set up this idea of sandboxing, building defensive alliances, you know, in order to move away from that regime. I I think it shows, and Saxon and I have talked about this a lot, so I'm interested to hear what he thinks. It shows you can trust the industry and market forces in coordination with the government. They were talking to the government about this. But they're not relying on some top- down regulation in order to do this. They laid out a blueprint that seems to me very pragmatic that now that we're at this threshold, we're going to sandbox these things. I think that open AAI will end up doing the same thing. I think Google will end up doing the same thing. It's an aggressive way to keep the RA, you know, the pressure on and and win the race at AI while making the tradeoffs to protect safety. So, you know, I think you're always going to have to make these trade-offs. I think in this case, it was a great move by Dario and team and I think they deserve a lot of credit.

</details>

**杰森**: 萨克斯，看看这个。几周前我们请到了 Emil Michael，我们进行了非常深入的讨论。如果政府拥有这些工具，而 Anthropic 想要扣留它们，这种关系应该是怎样的？如果你推演一下博弈论，Anthropic 一定去跟政府说：“听着，这东西太强大了，它能组合两三个漏洞，创造出全新的攻击向量，这极其危险。如果中国拥有它怎么办？” 如果这东西真的像 Dario 说的那么强大，那它也是一种进攻性武器，比如可以摧毁……我们就选个迫切的问题吧，朝鲜的弹道导弹计划。这被描述为相当于“曼哈顿计划”。所以萨克斯，我有两个问题：你认为中国已经拥有并正在使用这种能力的概率是多少？你认为 Dario 进行这种自我监管是对的吗？

<details>
<summary>Original English</summary>

**Jason**: Sachs, when you look at this, we had Emil Michael on the program a couple weeks ago. It might have been four or five weeks ago, and we had a very thoughtful discussion about, hey, if the government is going to have these tools, you know, an anthropic wants to withhold them and, you know, what is the proper relationship there, you have to think that the government, and I know you don't speak for all parts of the government. If you were just going to run through the game theory, they must have gone to the government and said, "Listen, this thing is so powerful, it can put together two or three hacks, create a novel attack vector, and this is incredibly dangerous. What if China has it? And if this thing is as powerful as Daario says it is, then this is an offensive weapon as well for us to take out, let's just pick, you know, uh, a pressing issue, the North Korea's ballistic missile program. This is equivalent the way it's being described as the Manhattan project perhaps. So what are the chances two-part question for you Sax that China already has this and is using it and do you think Daario is doing the right thing by regulating themselves?

</details>

### 萨克斯的质疑：狼来了还是真危险？

**萨克斯**: 我认为 Anthropic 已经证明了它非常擅长两件事：一是产品发布，二是**恐吓大众**。我们在他们之前的发布中已经看到了这种模式——在推出新模型或模型卡的同时，他们也会推出一份研究报告，展示这项技术可能导致的最坏后果。去年大约一年前，他们发布了一项“敲诈研究”，声称新模型可以敲诈用户。这类事情发生了很多次。实际上，我问过 Grok，“给我几个 Anthropic 使用恐吓手段的例子”，这已经成了一种模式。

<details>
<summary>Original English</summary>

**Sachs**: I think Anthropic has proven that it's very good at two things. One is product releases. The second is scaring people. And we've seen a pattern in their previous releases of at the same time they roll out a new model or new model card, something like that. They also roll out some study showing really the worst possible implication of where the technology could lead. We saw this last year about a year ago. They rolled out this blackmail study where supposedly the new model could blackmail users. There's been a whole bunch of these things. Actually, I went back to Grock and I just asked, "Hey, give me examples where Antropic has basically used scare tactics and it's it's a pattern." Okay, it's a pattern.

</details>

**杰森**: 好的。

<details>
<summary>Original English</summary>

**Jason**: Okay,

</details>

**萨克斯**: 这些家伙，我不是说他们不真诚，但他们确实有利用恐惧来营销新产品的现成模式。回想一下我最喜欢的例子，那个“敲诈研究”，他们对模型提示了 200 多次才得到他们想要的结果。那个结果明显是逆向工程出来的，为他们赢得了想要的头条新闻。证据就是一年后的今天，市面上有很多开源模型达到了当时那个 Anthropic 模型的水平，你见过任何现实中的敲诈案例吗？我觉得没有。换句话说，如果那项研究反映的是模型的真实倾向，你早就应该看到实证了。

现在说回这次的网络攻击案例。我其实认为这一次更偏向真实的一面。我之所以提起之前的模式，是因为每当 Anthropic 吓唬人时，你必须问：这是战术吗？是“天要塌了”的固定戏码吗？他们在喊“狼来了”吗？在这次案例中，我会给他们信任。这符合逻辑，对吧？随着编程模型越来越强，它们寻找漏洞和制造攻击手段的能力也随之增强。

因此，我认为在未来 6 个月内，我们会经历一个“追赶期”，AI 驱动的网络安全将能检测到过去 20 年中埋藏在各种系统里的漏洞。风险是真实存在的。所以，设置预发布期是有道理的，让软件公司利用这个工具检测自家代码库并打上补丁。顺便说一下，这种能力不会只属于 Anthropic。我们知道中国的开源模型，比如 **Kimi K2**，大约落后 6 个月。所以我们有大约 6 个月的窗口期。我认为每家公司、IT 部门或 CISO（首席信息安全官）都应该认真对待这件事。如果每个人都各司其职并做出反应，那么就不会出现 Anthropic 描绘的末日景象。但有时候，恐惧能驱动正确的行为。最终我认为一切都会好转，但这确实需要大家保持关注，利用这些能力修复漏洞。然后我们就会进入 AI 网络进攻与防御之间的正常军备竞赛阶段。

<details>
<summary>Original English</summary>

**Sachs**: these guys, I'm not saying it's not sincere, but they have a proven pattern of using fear as a way to market their new products. And if you think back to, again, my favorite example is this blackmail study where they prompted the model over 200 times to get the result they wanted. And that result was was clearly reverse engineered and it it got them the headlines they wanted. And I would say the proof that it's reverse engineered is we're now a year later. There's a bunch of open- source models out there that have the same level of capability that that anthropic model had. And have you seen any examples of blackmail in the wild? I don't think so. So in other words, if that study were true in the sense of being a likely outcome of that model, I think you would see examples in the wild of that behavior. And we haven't seen any of that in the past year. Now, let's talk about this specific example with cyber hacking. I actually think that this one is more on the legitimate side. I mean, look, the reason why I bring this up is anytime Anthropic is scaring people, you have to ask, is this a tactic? Is this part of their Chicken Little routine? or is it real? You know, are they crying wolf or not? I actually would give them credit in this case and say this is more on the the real side. It just makes sense, right? So that as the coding models become more and more capable, they're more capable of finding bugs. That means they're more capable of finding vulnerabilities. And like one of their engineers said, that means they're more capable of stringing together multiple vulnerabilities and creating an exploit. And so I do think that over say the next 6 months we're going to have this call it one-time period of catching up where AIdriven cyber is going to be able to detect a whole range of of bugs that maybe have been dormant over the past 20 years across a wide range of systems. And so I do think that there is real risk here. And I do think therefore that having this pre-release period makes a lot of sense where they're giving the capability to all these software companies that have existing code bases to use the tool to detect the vulnerabilities for themselves so they can patch them before these capabilities are widely available. And by the way, it won't just be anthropic that makes these capabilities available. We know that like let's say the Chinese open source models like Kimmy K2, it's about 6 months behind. So we have a window here of maybe 6 months where we're still in this pre-release period where I think companies that have large code bases can get advanced access to this model and uh I guess open AI is going to release a similar thing in the next few weeks. I do think that every company or IT department or CISO that is managing code bases should take this seriously and use the next few months to detect any again like dormant bugs or vulnerabilities and and roll out patches. If everybody does their job and reacts the right way, then I do not think it will be the doomsday scenario that Anthropic is sort of portraying. But it's one of these things where the fear might end up being a good thing in order to drive people to in order to drive the correct behavior. So sure, I ultimately think this is going to work out fine, but you do need everyone to kind of pay attention, use the capabilities, fix the bugs, then we're going to get into a big arms race between AI being used for cyber offense and AI being used for cyber defense, but it'll be a more normal sort of of period.

</details>

**杰森**: 查马斯，Dario 和许多参与者都在非常严肃地对待这件事，他们发表了重大声明。萨克斯的观点非常微妙。你对此怎么看？这些公司如何两全其美？一方面说不该被监管，一方面又说如果这东西落入他人手中会导致灾难。如果中国现在就拥有这种能力，那就意味着需要更多的政府协调或监管。中国拥有同等能力的概率是非零的。我们假设他们落后，但谁知道他们在关起门来做什么。所以，你怎么看？是“狼来了”，还是动真格的？

<details>
<summary>Original English</summary>

**Jason**: Chimath, we have uh Daario and uh you know a number of the participants here are taking this super seriously. They're making a big statement. Zach's very nuanced uh I think take there. What's your take on how do these companies have it both ways? Hey, this is shouldn't be regulated. This should be regulated. If this is in fact a cataclysmic, oh my god, they're going to hack everything. What if the Chinese have this right now? That would speak to more government either coordination, regulation, or some kind of relationship between the CIA, the FBI for domestic stuff, and these companies because there it is a non-zero chance that the Chinese have an equal capability here. We're assuming they're behind, but who knows what they're doing behind closed doors. So, what's your take on this? Is it uh The Boy Who Cried Wolf, or is this the real deal? Now,

</details>

**查马斯**: 我认为这大多是**一场戏**（Theater）。

<details>
<summary>Original English</summary>

**Chamath**: I think it's mostly theater.

</details>

**杰森**: 好的。

<details>
<summary>Original English</summary>

**Jason**: Okay.

</details>

**查马斯**: 2019 年 2 月，当 Dario 还在 OpenAI 时，他们对 GPT-2 做了同样的事情。那是一个 15 亿参数的模型，在 2026 年听起来就像是个屁，但在当时，那个模型被认为是世界末日，会释放海量的垃圾邮件和误导信息。结果呢？他们进行了为期六到九个月的有计划发布，先发小的，再发大的。最后，什么事都没发生。

如果你真的认为 Mythos 具备它所声称的能力，那么两件事是肯定的：第一，资深黑客现在用 Opus 也能做这些事。第二，如果这些漏洞这么容易被发现，无论你用 Opus 还是 Mythos，现实是你得把互联网关掉五年才能把它们补完。所以当你看到这种万亿美金级别的阵仗时，这就是一场戏。为什么？你觉得他们在两个月内能完成什么？如果漏洞真的存在，几个月内能修好吗？现实是资本主义在前行，融资需求在前行，建立用户习惯的需求也在前行。这些需求会压倒一切。

所以我认为萨克斯是对的，他们摸索出了一套非常聪明的**市场进入策略**（Go-to-market），能够激活极高的关注度和使用率。为此我给他们点赞。我坚持我之前的观点：Anthropic 现在的表现非常惊艳，就像斯蒂芬·库里在场上到处投进疯狂的三分球。

<details>
<summary>Original English</summary>

**Chamath**: In February of 2019, when Daario was still at OpenAI, they did the same thing with GPT2. That was a 1.5 billion parameter model, which sounds like a total fart in the wind in 2026. But at that time, this 1.5 billion parameter model was supposed to be the end of days. And it was supposed to unleash this torrent of spam and misinformation. And that was the big bugaboo at the time. And so what happened? They went through this methodical roll out over six or nine months. They started releasing the smaller parameter models and then they scaled up to the big 1.5 billion parameter model. And at the end of it, it was a huge nothing burger. If you actually think that Mythos is capable of doing what it says it can do, two things are true. One is a very sophisticated hacker can probably do those things right now with Opus. And two, if these exploits are this easy to find, whether you use Opus or whether you use Mythos, the reality is you'd have to shut down the internet for about 5 years to patch them all. So when you see like a large multi- trillion dollar gang, it's a bit of theater. Why? What do you think they can actually accomplish in 2 months? Do you actually think that if there's these vulnerabilities, it's all going to get fixed? Let's give them six months. Let's give them nine months. But the reality is that capitalism moves forward, the funding needs moves forward, and the need for these guys to build adoption moves forward. And that's going to supersede what this is. So I do think that Sax is right that they have figured out a very clever go-to market muscle here and a go to market motion that activates hyper attention and hyper usage and so I give them tremendous credit and I'll maintain what I've maintained before. Anthropic is shooting the lights out right now. This is like Steph Curry going bananas from every everywhere on the court. These guys are hunking threes.

</details>

**杰森**: 没错。向 Anthropic 致敬。但我们以前见过这一招。当这些人还是 OpenAI 的首席架构师时，我们就见过同样的剧本。我认为回过头来看，我们会发现两点：一，如果要修复所有安全漏洞，真的需要关掉互联网好几年。二，高级黑客现在用 Opus 可能就能做到这些。

嘿，布拉德，让你说最后一句总结。我倾向于认为，也许他们以前确实虚张声势，但基于这些模型的进步速度，这像是一个“红色警报”时刻。这是 Defcon 级别（防御准备状态）。我们应该极其严肃地对待这件事，我认为这些公司需要与 CIA 协调，这既是防御也是进攻的机会。你认为这……

<details>
<summary>Original English</summary>

**Jason**: It's all in that. Okay. So huge kudos to Anthropic, but we've seen it before. We saw it when these folks were the principal architects at OpenAI who are now seeing the same playbook here. I think we'll look back and I think what we'll say are these two things. One is if we're really going to patch all these security holes, we need to shut down the internet for some number of years, honestly, literally years. And the second is an advanced hacker can probably do this today with Opus if they really wanted to. Okay. Hey Brad, I gota I'll get you in here for the for the last word. I I'm going to go with Yeah, maybe they did uh Crywolf before, but based on what I see with these models advancing and using them and I'm using a lot of the open source ones right now from China. I think that this is like code red kind of moment. This is Defcon. like we should be taking this deadly seriously and I think these companies got to coordinate with the CIA and this is uh equally a defensive as offensive opportunity. Do you think this

</details>

**查马斯**: 你现在是在要求 **AI 国家化**吗？

<details>
<summary>Original English</summary>

**Chamath**: you're asking for the nationalization of AI now?

</details>

**杰森**: 不，我其实不认为应该国家化。尽管我看到有人在影射这一点。我认为这些公司需要建立一个组织来与 CIA 协调。我假设他们已经在这么做了。我假设你、Emil Michael 和特朗普他们已经在房间里开过会了，讨论政府如何利用这来阻止坏人。我百分之百肯定 Dario 已经去找过他们了，说：“看看我们发现了什么，这是动真格的。” 布拉德，作为两家公司的投资人，你对他们很了解，由你来总结。

<details>
<summary>Original English</summary>

**Jason**: No, I actually I I I don't think it should be nationalized. Um although I did see people sort of insinuating that. I think these companies need to build a group Brad that work and coordinate with the CIA. I assume that they're already doing this. I'm assuming you Emil Michael and uh you know Trump and everybody have these people in a room and that they've given the defcon and said hey how can our government use this to stop bad actors and this is already being coordinated with the CIA and the FBI. I am 100% certain of that that Dario went to them and said look what we found. This is the real deal. I'll give you the last word on this Brad since you're an investor in both companies and you know them quite well.

</details>

### AI 行业的防御联盟：市场还是保姆国家？

**布拉德**: 23 年成立的“前沿模型论坛”（Frontier Model Forum）目前正在就**对抗性蒸馏**等问题进行合作。谷歌、OpenAI、Anthropic，他们都在协调。以前我也曾质疑过 Anthropic，觉得他们是在搞“监管捕获”之类的东西，但这次我觉得非常不同。Dario 本可以轻松跳出来说：“天哪，我们跨越了门槛，我们需要政府暂停研发。” 记住，甚至我们的朋友埃隆在 2023 年也曾呼吁暂停六个月。但这家伙没这么做。相反，他说：“我们该怎么办？我要召集 40 家领先公司，花 100 天进行沙盒化、系统强化，然后我们会继续推进。”

<details>
<summary>Original English</summary>

**Brad**: the frontier model forum which was which was put together in 23 um is cooperating on anti- and adversarial distillation stuff as we speak right they don't want to make it easy on you know so Google and and open AAI and and anthropic they're coordinating on this stuff you know there are times where I've pushed back on anthropic because I thought it was you know perhaps regulatory capture or something else this is very different in my mind right he could have easily Dario could have easily come out and said oh my god we passed a threshold we need to have a government moratorum. Remember, even our friend Elon called for a six-month moratorium in 2023 because of civilization risk. This guy didn't do that. Instead, he said, "Okay, what what should we do? I'm going to get 40 of the leading companies together. We're going to spend a 100 days sandboxing, hardening the systems, and then we're we're we're going to keep pushing forward."

</details>

**查马斯**: 你真心觉得 100 天内能完成什么？你认为在 100 天内会有多少 PR 被推送到核心互联网结构中？那个数字是多少？我给你个数字，你肯定会说零。我的回答是……

<details>
<summary>Original English</summary>

**Chamath**: What do you honestly think is going to get accomplished in a 100 days? How many PRs you think are going to get pushed to the core structural internet in 100 days? What's the overunder number? Cuz I'll give you a number. You're gonna say zero. My my answer to that is

</details>

**布拉德**: 我会说大概 10,000 个，而且是立即生效。

<details>
<summary>Original English</summary>

**Brad**: I'll say like 10,000, but it's going to be immediate.

</details>

**查马斯**: 但如果这能防止你的浏览器历史记录被泄露，查马斯，那可能是你愿意再等 100 天的事情。

<details>
<summary>Original English</summary>

**Chamath**: But if it prevents your browser history from being released to everybody in the world, Chimat, that may be something that you're willing to, you know, let a 100 days pass on.

</details>

**杰森**: 查马斯一听到浏览器历史记录就来劲了。

<details>
<summary>Original English</summary>

**Jason**: I think you got Chimat's attention when you said browser history.

</details>

**萨克斯**: 那私密照片呢？

<details>
<summary>Original English</summary>

**Sachs**: What about the dickpicks?

</details>

**杰森**: 查马斯会自己发布的。他现在就像是在说：“嘿，中国黑客，这是我的私密照，请发布出去。”

天哪。当他们做正确的事，或者依靠市场而不是奔向“保姆国家”要求更多监管时，我们要给予称赞。所以这对我来说是一个平衡的例子。未来肯定会有很多争论，但我希望能看到更多这样的做法。

<details>
<summary>Original English</summary>

**Jason**: As Chimat is, he's going to release them himself right now. CHIMAT'S LIKE, "HEY, CHINESE HACKERS, HERE ARE MY DICKPICKS. Please put them out." Oh my god. we have to be out there complimenting when they're doing the right things or relying on the market rather than running to the nanny state and saying do more of this. So this to me was just an example of of a of a good balance. I'm sure we're going to have plenty of debates about this in the future. But you know this is one I would like to see more of.

</details>

**萨克斯**: 这就是为什么，杰森，我试图采取更微妙的立场，因为我们别无选择，只能严肃对待这件事。无论这是否完全是一场戏，是否是危言耸听（他们确实有这个前科），我们都不能冒险，对吧？随着这些模型在编程方面变得越来越强，它们在网络安全方面也必然会变强。从“AI 前时代”过渡到“AI 后时代”，确实需要一个补丁期。我猜未来几个月我们会看到大量的补丁，这会解决问题。

在这种情况下，我愿意给他们信任。我过去批评过他，我认为那个“敲诈研究”简直是丢脸到像是个骗局，但在这种情况下，我认为它是合法的。

<details>
<summary>Original English</summary>

**Sachs**: This is why to use your word Jake I tried to have a more nuanced take is because we have no choice but to take this seriously. Whether it's total theater, whether it's fear-mongering, and they do have a pattern around this, we can't take the risk, right? And it does logically make sense that as these models become more and more capable at coding, they're going to get better at cyber. And there's going to be that one time period where you're moving from preAI to post AAI, and you need a patch for that. So, my guess is we're going to see a lot of patches over the next few months. I think that that will resolve the problem. I think this is a case where I'm going to give them the benefit of the doubt. I I think that, you know, I've criticized him in the past. I think that blackmail study was embarrassing to the level of being a hoax, but I think in this case, I'm going to give him credit and say that I think that it's legit.

</details>

**杰森**: 所以这不是“Anthropic 骗局”，这可能是真的。

<details>
<summary>Original English</summary>

**Jason**: So, it's not the anthropic hoax. This could be legit. I, you know, looking at

</details>

**萨克斯**: 我们别无选择。

<details>
<summary>Original English</summary>

**Sachs**: we have no choice but to treat it that way.

</details>

**杰森**: 当然。萨克斯，两件事可能同时成立。他们可能以前用过这种策略，这次可能也带有表演性质，比如那个配有戏剧性音乐的视频，确实有点戏剧化。但在逻辑上讲得通，那家在编程上下了最大赌注的公司，最有可能是最早发现这个问题的。100 天的时间对比黑客来说是一个巨大的优势。查马斯，你再补充一点。

<details>
<summary>Original English</summary>

**Jason**: Of course. Yeah. I mean, even if two things could be true at the same time, Saxs, they could have used this tactic before. It could be performative, like the video with the dramatic music in the background. It does have a little bit of drama to it, and the way they presented it is very dramatic, but it does make logical sense that the one company that made the bet on code bigger than anybody else would be the one who would discover this quickest. And you know in a 100 days that's a pretty good um that's a pretty big advantage versus the hackers. But let me think one more point there Jimat

</details>

**查马斯**: 人们没有谈论的最重要的一点是，因为这些工具，目前被推送的代码量在大多数组织中增长了 10 倍、100 倍。所以我们需要将这种安全性嵌入到这些新的编程工具中，实时进行。这才是机会。应该有实时的纠正机制。如果这真的是迫在眉睫的危机，他们选错公司了。我是说，能源公司、控制核反应堆的人、航空公司，这些才是关键。但这些公司没有被包括在内。所以如果你真的认为这是世界末日，起码我们应该同意扩大圈子。

<details>
<summary>Original English</summary>

**Chamath**: the most important thing that people haven't talked about here is the amount of code being pushed right now because of these tools is 10x 100x in most organizations. So we need to have this type of security embedded in these new coding tools to do it in real time. That's the opportunity. There should be real time correcting of this. If this was real, they picked the wrong companies. Meaning, there are energy companies, folks that control nuclear reactors. There are airplane companies that are flying hundreds of thousands of people in essentially manufactured missiles of like streaming gas going at 500 miles an hour. None of those companies were the ones that were included in this. And so I think if you really thought that this was end of days, at a minimum we can agree maybe we should have expanded the circle a touch.

</details>

**杰森**: 也许那些公司是这 40 家公司的客户。无论如何，这是一个非常重要的故事，我们将跟踪它的进展。Dario，来参加节目吧。布拉德，你能让 Dario 来吗？我邀请了他三次，我有他电话，但他一直没回我。

<details>
<summary>Original English</summary>

**Jason**: Well, maybe those are customers of the ones they're including here. Anyway, uh this is a really important story. We'll obviously track it in the coming weeks to see what turns out to be reality. And uh Daario, do come on the program at some point. Hey uh Brad, will you get Dario to come on the program? I've invited him like three times. I got his phone number. He's ghosted me. I don't know why.

</details>

**布拉德**: 他不理你？

<details>
<summary>Original English</summary>

**Brad**: Wait, he he's ignored you? I get

</details>

**杰森**: 我是通过世界顶级风投介绍认识的，他就在公司的早期股东名单里。他就是不回应。

<details>
<summary>Original English</summary>

**Jason**: I literally got an introduction from the number like one of the number one venture capitalists in the world. He's on the cap table very early. He just won't respond. I don't know why.

</details>

**布拉德**: 我会推荐 Dario 和 Dwarkish 的那期播客，那是非常精彩的作品。我听了三四遍，每次都做笔记。

<details>
<summary>Original English</summary>

**Brad**: I would tell you Daario's podcast with Dwarkish who I think is an excellent podcaster. I've listened to that three or four times taken notes every time. It is a really exceptional piece really exceptional piece of work by by by them.

</details>

### OpenClaw 之争：Anthropic 的垄断疑云

**杰森**: 好了，我们继续。布拉德，关于 Anthropic 还有一个话题。OpenClaw 的创始人 **Peter Steinberger**（著名的程序员）发推文说，Anthropic 正在切断他对 Claude 的访问权限。

基本情况是：每个使用 OpenClaw 的人以前只需支付每月 200 美元的订阅费，但这群人是重度用户，其 Token 消耗量是平均订阅者的 100 倍。Anthropic 说，你不能再用这 200 美元的计划了，你必须使用 API。这意味着费用从 200 美元变成按量计费，可能会增加十倍甚至更多。然后在不到 10 天后，Anthropic 发布了自己的 Agent 技术。所以，在商言商，他们基本上是对 OpenClaw 开了一炮。

<details>
<summary>Original English</summary>

**Jason**: All right, let's keep moving. We got a lot on the job. You may once again be tarred with your affiliation with us. Poor you. I mean, I don't care. Literally, I I've got friends on both sides of the aisle. I have friends of course you do. Even JCAL. Even JCAL has friends everywhere. Let me ask Brad a question here just while we're on the topic of anthropic. There was a really interesting story or tweet I guess you could say by the founder of OpenClaw that Peter. Peter. Yeah. What's his name? Peter Steinber. Steinberger. Steinberger. Steinberger. Yeah. renowned coder created openclaw which is kind of the thing that launched this whole agent era now you I guess you could say any event he said that anthropic was cutting off his access to was it was to claw is that the next topic this is on the docket it's a little bit nuanced everybody using openclaw would take their $200 a month subscription to anthropic which was essentially like a people were using more tokens and it's an average the people from openclaw it is very verbose and those people are 100x the usage of the average subscriber. So he said you can't use your 200, you have to use the API. You move from the $200 plan to the API, add a zero to your token use. So or more. And so they essentially anchored Open Claw and then 10 days later or less they released or announced their new agent technology which is according to them a safer better version of OpenClaw. So, hey, all fair in love and war and they have basically shot a huge cannon across the bow of openclaw.

</details>

**萨克斯**: 等等，你能解释清楚吗？你是说他们系统性地模仿了 OpenClaw 的每一个功能，将其整合进 Claude，然后切断了 OpenClaw 的“氧气”？

<details>
<summary>Original English</summary>

**Sachs**: Wait, can you just explain that exactly? So, so I think you're right that they systematically copied feature by feature of open claw, incorporated that into clawed and then the coupross was basically cutting off open oxygen. Can you just explain exactly what they did?

</details>

**杰森**: 简单来说，当你购买这些服务的订阅时，他们是把所有用户的用量平均化的。OpenClaw 成了 GitHub 历史上最火的开源项目。那些原本付 200 美元订阅费的人，实际上消耗了价值 20,000 美元的 Token。所以公司说你不能再在 OpenClaw 里用 200 美元的订阅了，必须去 API 按量付费。

<details>
<summary>Original English</summary>

**Jason**: Okay, very simply, when you buy a subscription to these services, they have blended your usage across many users. So there's, you know, nine out of 10 users use less than the tokens they're paying for and the top 10% use much more. When OpenClaw became a phenomenon, the number one open source project in history on GitHub with all of this usage, people went crazy. And you heard me talking about how crazy I went for it. those people with the $200 subscriptions were using $2,000 $20,000 worth of tokens. So they said you can no longer use your subscription to, you know, either your professional or enterprise subscription at $200 and plug that into your open claw. You now have to go to the API and pay per usage. So no more like unlimited.

</details>

**萨克斯**: 如果使用 Anthropic 自己的 Agent 框架，是包含在包月套餐里的吗？如果是的话，从反垄断的角度看，这可能涉及 **Token 倾销**或捆绑销售。

<details>
<summary>Original English</summary>

**Sachs**: If you use Anthropic's own agent harness, are you part of the bundled flat rate? You can assume that that's what they'll do, which if you were thinking on an antirust level might be token dumping or price dumping. I'm not saying like I'm ratting them. No, it's like bundling, isn't it? Well, price dumping or bundling. When you price something under the market price in antitrust, that would be price dumping, right? And if you were to bundle, it would be like the bundling issue.

</details>

**布拉德**: 这非常关键。你仍然可以通过 API 使用 OpenClaw，每家公司都有权为自己的产品定价。他们只是说，在现有的制度下，通过 OpenClaw 实际上是以 10 美分的价格卖 1 美元的东西，现在他们只是想回归合理的定价，但欢迎大家继续使用 API。

<details>
<summary>Original English</summary>

**Brad**: Critically important. You can use openclaw via claw API and every company has a right to set the price for its products. It's just saying that you were for under their current regime, they were selling dollars for 10 cents via OpenClaw because these were such power users and now they're just saying we have to price this rationally, but we're happy to have you guys use the API. So, okay.

</details>

**萨克斯**: 但是布拉德，当使用 Anthropic 提供的竞争产品时，他们是否在提供补贴？

<details>
<summary>Original English</summary>

**Sachs**: Okay. But Brad, when you use the OpenClaw competitor that Anthropic now offers, correct? Are they subsidizing that? Are you paying?

</details>

**布拉德**: 我们还不确定，因为还在封闭测试阶段。

<details>
<summary>Original English</summary>

**Brad**: We don't know yet because it's in closed beta.

</details>

**萨克斯**: 我的意思是，如果他们自己的 Agent 系统按月固定收费，而对第三方产品按量收费，你就可以提出“捆绑销售”的论点。考虑到 Anthropic 在编程领域目前拥有主导地位，这可能被视为反竞争。

<details>
<summary>Original English</summary>

**Sachs**: So in other words, what I'm saying is if they charge for API usage, right, their own first party agent harness or system, then that would be apples to apples. But if if they end up charging the bundled flat rate, let's say, for their stuff, but then charge the metered rate for third party stuff, you could make a bundling argument. Sure. Sure. And you could say it's anti-competitive assuming that Anthropic has dominant market share in coding, which I think most people would say they do at this point.

</details>

**布拉德**: 大多数企业之所以会选择 Anthropic 版本的 Agent 产品，是因为它符合安全参数。Altimeter 就在 Anthropic 上运行很多东西，直接让 OpenClaw 跑在我们的数据库上并不明智。这是基本产品层面的不同。

<details>
<summary>Original English</summary>

**Brad**: And assuming that it's the same product, I mean, the reason most enterprises will probably use the Anthropic uh version of this agentic product is because it meets all of your security parameters, right? So, Altimter runs, you know, a lot of stuff on Enthropic. They're already integrated within our our data warehouse, our data lake, things of that nature. So just letting openclaw loose on the uh altimeter you know data set would not be wise and so it's a different fundamental product.

</details>

**杰森**: 我明白。我也认为 Anthropic 把 OpenClaw 的功能整合进 Claude 有巨大的优势。我的问题是他们是否在给自己创造价格优势。我百分之百站在萨克斯这种更具“阴谋论”的一边。OpenClaw 太强大了，势头太猛，Anthropic 想要削弱它。我甚至相信当萨姆·奥特曼聘请 Peter 时，也是为了瓦解这个开源项目，把他的天才想法留在 OpenAI 内部。

现在想杀掉或竞争 OpenClaw 的名单很长：Anthropic、Perplexity Computer、Hermes Agent。阿里巴巴也将基于 Qwen 模型推出类似产品。埃隆也说要推出 **Grok Computer**。亚马逊和苹果也准备升级 Alexa 和 Siri。我认为目前模型领域的一大目标就是杀掉这个开源产品。

<details>
<summary>Original English</summary>

**Jason**: No I get that and I think that anthropic has a huge advantage let's say cloning open claw and just building it into claude. I'm not denying that to me that would be the reason why they don't need to do price discrimination is because there's already a very good reason to use the let's call it the bundled offering on a featured basis. But the question I'm specifically asking is whether they're giving themselves a price advantage because I think Brad is giving the the most generous interpretation. You're taking a more cynical one. I'm with you, Saxs. I'm 100% on the cynical side. Open Claw is so powerful. It's got so much momentum that not only is anthropic trying to ankle it. I believe when Sam Waltman bought it, it was uh and he didn't buy OpenClaw itself, he hired Aqua hired Peter. I believe it was to subvert the open- source project to get Peter's next set of genius ideas inside of OpenAI as opposed to letting them go there. People are going to say I'm a conspiracy theorist, but this is the number one focus and let me just give you a list of who is trying to kill OpenClaw/compete with them. Obviously, you have Anthropic, but also Perplexity Computer launched. It's awesome. I've been using it. Anthropic has this clawed managed agents. They dropped that on Wednesday, April 8th. uh yesterday uh today's Thursday when we tape you you guys listen on Fridays and then you have Hermes agent that was released on February 25th that's also open source and very good so that's in the open source camp Alibab is coming out with one that's going to be based on their Quinn model then you have Elon who said he's got something called rock computer coming out of macro hard which is a play on words for Microsoft in addition to that Amazon and Apple are preparing uh new releases of their uh [ __ ] maxing assistants Alexa and Siri that will be less [ __ ] in this new version and then nothing out of uh SAT and Microsoft yet. So the number one goal I believe in the large language model frontier model space is to kill this open source product.

</details>

**查马斯**: 拜托，他们是在构建多功能 Agent。这是消费者和企业想要的。这不代表是为了杀掉 OpenClaw，这只是显而易见该做的事。

<details>
<summary>Original English</summary>

**Chamath**: No, I mean come on like why they're building multi-functioning agents that can move from answering questions to actually doing something for you. like you got to do that because that's what consumers and enterprises wants. It doesn't mean that it's about killing OpenClaw. just this is an obvious thing right to do it

</details>

**杰森**: 但这是一场阻止开源运动的巨大行动，因为这相当于市场上的“开源 Android”。我认为开源最终会赢得大模型之争，占据 90% 的 Token 用量。我觉得整个前沿模型空间都可能被开源和 SLM（小语言模型）颠覆。我希望这会发生。布拉德，恕我直言，把你的整个业务和一生积累的知识都交给 Anthropic 是愚蠢的。

<details>
<summary>Original English</summary>

**Jason**: but this is a giant movement to stop it because this is the equivalent of having an open-source Android like player in the market and that could be incredibly disruptive these I believe open source is going to win the day on the large language models and take 90% of the token usage and I think the entire frontier model space could be undercut by open source and I think they realize that SLMs the the smaller language models that are verticalized now that will run on you know, desktops and laptops and is even starting to run on the top ones. That is their biggest competitive threat and I hope it happens. All due respect to your investments, Brad, I think this technology and the interface is uh you know, he placed bets, but I I think it's imperative that the agent level, which is essentially your entire life, you don't give that to Anthropic. You don't give that to OpenAI. That's your entire business, your entire life. It is foolish for you, Brad, to give your entire business and all the knowledge you have to anthropic through that. unless you're just going it to boost your um your your investment in those companies. But I would be very concerned if I was you with putting all of your knowledge that you've earned over a lifetime into any of these large language models.

</details>

**查马斯**: 杰森，谢谢你那充满激情的演讲。其实我想问个问题。

<details>
<summary>Original English</summary>

**Chamath**: All right, Jake, let me ask you. Can I ask a question? Thank you for that impassioned monologue. Um actually, I want to ask my TED talk.

</details>

**萨克斯**: 是的，谢谢你的 TED 演讲。我有一个“是/否”的问题问大家：你们是否相信 Anthropic 目前在编程领域拥有**主导性的市场份额**？

<details>
<summary>Original English</summary>

**Sachs**: I Yes, thank you for that TED talk. Um I have a yes no question for each of you. Do you believe that anthropic has dominant market share in coding? right now? Yes. No,

</details>

**布拉德**: 不。

<details>
<summary>Original English</summary>

**Brad**: no.

</details>

**查马斯**: 在编程领域，是的，他们领先，但还没到统治地位。

<details>
<summary>Original English</summary>

**Chamath**: In in coding, yes, they had the lead, but not that they had the lead, but not dominating.

</details>

**布拉德**: 我认为这是一个万亿美金的市场，这些家伙目前的份额还不到 10%。

<details>
<summary>Original English</summary>

**Brad**: I think it's a trillion dollar market, and these guys have less than 10% of it today. So, it's hard to make a case that

</details>

**萨克斯**: 你认为 Anthropic 目前向市场提供了百分之多少的编程 Token？

<details>
<summary>Original English</summary>

**Sachs**: What percent of coding tokens do you think that anthropic is providing the market right now?

</details>

**布拉德**: 超过 50%。

<details>
<summary>Original English</summary>

**Brad**: Greater than 50%.

</details>

**萨克斯**: 那就是所谓的“主导性市场份额”。

<details>
<summary>Original English</summary>

**Sachs**: Yeah, that's true. Okay, that's called dominant market share.

</details>

**查马斯**: 也许今天 Anthropic 提供了超过一半的编程 Token，但这只是一个非常早期的市场。如果我们走上法庭，很难证明他们已经形成了针对亚马逊、谷歌、微软、OpenAI 等公司的垄断。

<details>
<summary>Original English</summary>

**Chamath**: Uh, I don't know about that. More than 50% of the market. You got to look at what you got to look at what the TAM is. with the Tan, right? There are lot of people who provide, you know, that that are in this tiebreaker before we move on to the next. I'm not saying it's a permanent condition, but if you're telling me that today Anthropic is delivering over half of the coding tokens, that's clearly a dominant position in the market for coding. It's an early market. It could change, but if I were representing them, David, I would say nine months ago, everybody t called us uh, you know, out of the game. We were being destroyed by open AI in three months. Now people are saying we have dominant market position. This is the fastest changing most competitive market in the world. I think it would be very hardressed to walk into, you know, some district court make the case that these guys have somehow already formed a monopoly against Amazon, Google, Microsoft, Open AI, etc.

</details>

**萨克斯**: 他们可能有 50% 到 60% 的份额。但查马斯的观点也很重要：AI 辅助编程目前仅占整个市场的 5%。这是一个尚未变大的小市场。而且丑陋的真相是，无论你用什么模型，目前构建企业级软件的能力仍然很糟糕。当我去拜访万亿级的银行或保险公司时，没人说“这东西开箱即用”。大多数代码仍然需要人工调优。

我们处于一个积累了 50 年“技术债”的世界。全球有数百万亿行平庸甚至糟糕的代码。我们的一位客户甚至不得不请 60 岁的退休人员回公司来解读 **COBOL** 代码。我不是在开玩笑。那是一家年收入千亿美金的公司，这就是他们解决问题的方式。Opus 解决不了这个。解决全球 99% 的技术债将耗费数十年时间。

<details>
<summary>Original English</summary>

**Sachs**: Well, I'm not saying it's a it's already a permanent monopoly, but I am just asking about market share. And I do think you guys all agree that Shimov, go ahead. They probably have 50 to 60% market share because I think codeex is actually quite broadly used as well. But that belies the more important point which is AI enabled coding I think is still 5% of the broad market. So it's kind of a nothing burger. Yes, they're leading but they're leading in something that isn't that big yet. Now you would say how could it not be big? And what I would say is because most of the stuff that's being written is still white sheet denovo code. And I think the ugly truth is I don't care what model you have, but the long horizon ability for any of these models to actually build enterprisegrade software is still shiit [ __ ] And that's the actual lived experience. Not for me, but when I call on our customers, half a trillion dollar banks, hundred billion dollar insurance companies, none of these guys are like, "Wow, it just works out of the box." It doesn't work. So, most of it is still handtuned. So, until I can honestly tell you that we can point a model at this with the right guard rails, which I can't today, what I would say is it's a small market that will become large as these models become better. But we are in the world where we have 50 years of accumulated tech debt as a world. And I suspect when you enumerate the number of lines that that represents, it's hundreds of trillions of lines of just pretty marginal mediocre code to bad code. On top of that, we have all these legacy languages. I'll tell you one of our customers, they have to go and get 60year-old pensioners to come into the office to interpret cope. No, I'm not joking. This is a snowball for trend. This is a hundred billion dollar a year revenue company and that's how they solve these problems. It's not opus just solves it. So I I would just keep in mind that most of the tech debt in the world that exists 99% of it is still poorly addressed by these models. We are untying this Gordian knot. It's going to take decades to do it right. So all the breathlessness about all this other stuff, I really think it's not where the money is. It's not the big time stuff. And you can tell me, "Oh yeah, it's going to be the future." And I would say, "Tell this business that's a hundred billion dollars a year of revenue and 50 million billing relationships that all of a sudden you're going to open claw your way to a solution." It's [ __ ] Not to say that you can't have a great chief of staff, and not to say you can't do some useful stuff and trickery and, you know, have a good knowledge base. I'd like that, too. But the core things that your lived experience sits on today is a mess of tech debt that will get very slowly replaced. And that's just the reality of life.

</details>

**杰森**: 而且还有极其具颠覆性的竞争对手。我们几周前谈到了 **BitTensor (TAO)**。有一个项目叫 Subnet 62，名为 **Ridges AI**。他们是一个开源竞争对手，任何人都可以贡献。他们在不到 45 天的时间里，就达到了 Claude 4 的 80% 水平，而投入仅为 100 万美元。他们给代码贡献者提供奖励。这种“飞轮”效应正在疯狂转动。

<details>
<summary>Original English</summary>

**Jason**: And there are competitors that are extremely disruptive. I'll tell you about one. We talked about Bit Tensor Tao on this program a couple weeks ago when we had the um Jensen interview. You brought it up actually Chimath. There's a there's a project that's subnet 62. It's called Ridges AI. And what they're doing is a competitor that is not only open- source but anybody can contribute to it. They spent about a million dollars in tow like rewards and in 45 days they hit 80% of what Claude 4 is and they did that in under 45 days. The way that works is they give rewards for people who and they can do this anonymously make that coding product which is like codeex or claude code better. that flywheel is racing right now with participation in the same way Bitcoin is. So you're going to see a lot of open- source and these crypto open-source combinations and uh anybody who's not investigated this, I highly recommend you investigate this.

</details>

### 营收暴涨：从 10 亿到 300 亿的跨越

**查马斯**: 萨克斯说得对，我们下一步会进入 **Agent（智能体）**时代。编程能力是智能体的基础。我希望大家都能公平竞争，不要对他人的产品搞歧视。

让我们谈谈 Anthropic 的营收增长。这简直是前所未有的。Anthropic 的**年化营收（Run Rate）**已经冲到了 **300 亿美金**。2023 年初刚开始有收入，2024 年底到了 10 亿，2025 年中是 40 亿，2025 年底是 90 亿，到了 2026 年 4 月，竟然翻了三倍多到了 300 亿。他们现在拥有超过一千家年付费超过 100 万美元的企业客户。这是 Slack 和 Salesforce 梦寐以求的数字。布拉德，你是两家公司的投资人。看到 Anthropic 从落后这么远追上来，你有多震惊？

<details>
<summary>Original English</summary>

**Chamath**: I do think you're right about one specific thing. I would put zero, literally the probability zero of any important company worth anything more than a dollar having and outsourcing their production code to an open source project. That'll never happen. However, what will happen though is when you look at the cost of training this 10 trillion parameter model on Blackwell and when you look in the future let's just say in six or nine months that a 15 or 20 trillion perm model is going to get trained on Vera Rubin I think Jason where you are right I have zero and just to be clear I have no investments in this at all I'm to be so super clear I'm just observing because another project other than Bit Tensor that someone brought up to me is Venice. The concept of opensource training and orchestration is a hugely disruptive idea which is the complete orthogonal attack vector to this idea that you have to raise tens and tens of billions of dollars to train your models because if the capital markets run out of 10 and 20 billion dollar checks to give people the only solution is to be totally distributed. I tend to agree with you Jason that there is going to be at some point a very successful open source project for pre-training. Absolutely. Will there never ever be an open- source way where a real company that has any skin in the game says here guys re-engineer my codebase as an open source project. Never going to happen. Yeah, I I think the coding tools will. And if you look at the history of open source, Brad, you actually I think had a lot of bets in this space. Linux, Kubernetes, Apache, Postgress, like Terraform, like these open source projects are deep inside of enterprises. Deep. And we're sitting here 15, 20 years ago, the same argument was made. Nobody will ever adopt these inside the enterprise. You got to go with Oracle, whatever. And fair enough, many people do. But I think this is this $29 ridges um subscription to do this versus 200. It's starting to take hold inside of startups. And that's where I always look at the tip of the spear. Startups love to, you know, use open source products. I think this could be the next big thing. But listen, I I I invest in things that have a 90% chance of going to zero. So do your own research. No crying in the casino. Can I just make a a final few points? So just just quickly so number one is with respect to this market for code or code tokens whatever you want to call it it might be 5% today meaning 5% of the codes AI generated versus human generated I think it's going to 95% I mean I bet any amount of money on that the only question is when probably over the next few years so that's point number one point number two is it's possible that if you're the early leader in coding as a AI model company let's say you have 50 to 60% of market share. You have the most developers using it. Therefore, you have the most access to code bases. You might get the most training tokens. There is a potential flywheel there where you can see the early market leader consolidating its lead because it's generating the most code tokens and it's getting access to the most existing code. Now, I'm not saying for sure that's going to happen. is possible that the other guys catch up, but I think there is a possibility of a flywheel there and strong, I guess you'd call it data scale effects, things like that. So, I do believe that the market for coding tokens could be monopolized. Third, Anthropic's revenue run rate, as based on what I can tell and what's been publicly released, is the fastest growing revenue run rate at scale that I think we've ever seen. Uh, we perfect segue. It's the next story. Okay, maybe pull up the the tweets. But this thing is ramping at a rate we've never seen before. We can get into that in a second. But just one last final point is I think it's pretty clear that where we go from here is agents and coding gives you a huge step up on agents because you know one of the main things that agents need to do is is write code to be able to enable them to complete tasks. Correct. And so if it is the case that coding is this huge market that's going to be dominated by one or two companies and then that leads to another huge market which is agents. My point is just I think all these companies need to behave in a very clean way and not engage in tactics that later the government might say you know what that was anti-competitive. Everyone should just I think play fair. Do not engage in discrimination against other people's products. engage in fair pricing. I'm not accusing anyone of breaking any of the rules, but what I'm saying is that eventually the government's going to look at this market with the benefit of 2020 hindsight and I think everyone should just basically, you know, keep it keep your nose clean. Keep it tight. Keep it tight. Keep it tight. Tight is right. I think is an excellent point. Let's talk about the revenue ramp of Anthropic. This is just unprecedented. Anthropic's revenue run rate has topped 30 billion with a B. Early 2023, they turned on revenue. They started charging for API access. End of 2024, they're at a billion dollar run rate. February 25, they launched Claw Code. That was the starter pistol. Mid 2025, $4 billion run rate. End of 2025, $9 billion run rate. Just a couple of months later in April, $30 billion run rate. Yes, that's right. Triple. Uh and the way they did this is enterprise uh customers are a major part of the spend. Dario announced a couple of months ago that there's over a thousand enterprises paying over 1 million annually. This is truly mindboggling when you think about it because those are the most coveted customers in the world. These are the big fish that you just uh when people are running enterprise software, they they dream Slack dreamed of getting these million-dollar customers. Uh Salesforce dreams of getting these million-dollar customers. Brad, you're an investor. I guess uh Sam famously on BG2 asked you to sell your uh OpenAI stock back to him. You didn't. You demired, but you're an investor in both. How shocking is it to you to place both of those bets and then see one of them come from so far behind? You know, Chat GPT has 900 million users. I don't know if they've they've passed a billion officially yet, but they are the Verb, right? They're the Uber. They're the Xerox. They're the Polaroid of AI, but they didn't go after the enterprise. Daario made that and Daario worked. He was the co-founder of OpenAI. He left and according to the New Yorker story that came out from Ronan Farrell this week, he was basically left because of his disgust in working with Sam Alman. Your thoughts?

</details>

**布拉德**: 在我们深挖 OpenAI 之前，先看看大背景。他们在 1 月份增加了 40 亿营收，2 月份增加了 70 亿，3 月份年化营收增加了 100 多亿。这意味着他们在一个月内增加的营收规模相当于 DataBricks 加上 Palantir 的总和。这证明了 AI 营收真的出现了。

这种增长的原因在于，产品能力达到了我们之前说的 AGI 门槛。大家意识到，这不再仅仅是 IT 预算的问题，而是关于**劳动力增强**和**劳动力替代**的问题。我们看到了一个近乎无限的市场（TAM）。事实证明，智能市场的规模与我们之前见过的任何东西都完全不同。这不仅仅是 Anthropic 营销做得好，而是企业在渴求这个产品。

目前他们还受限于**算力（Compute）**瓶颈，他们今年每家都要增加 3GW 的算力。我认为到今年年底，Anthropic 的退出年化营收可能会达到 800 亿到 1000 亿美金。而 OpenAI 也会迎来同样的爆发。

<details>
<summary>Original English</summary>

**Brad**: Well, you know, before we go down the OpenAI rabbit hole, let's just really contextualize like what's going on here. You know, check I I I have this additional chart. you showed one, you know, they added 4 billion of revenue in January, 7 billion in February, 11 billion of annualized run rates, um, or 10 or 11 billion in March, just to put in perspective, that's data bricks plus Palanteer combined that they added in a single month, right? So we started with everybody at the start of the year ringing their hands including you know Gurley and others saying we're in a big bubble asking whether the AI revenues would show up to justify all of this investment and bam you have the largest revenue explosion in the history of technology. So the company's plans were to end the year at about a $30 billion ex exit run rate. They got there by the end of March right and I suspect that it's continuing in April. So you have to ask what's going on and what's the big so what the first thing for me is that model and product capability just hit this threshold we talked about earlier near AGI whatever the hell you want to call it and everybody like alimter said damn this is so good I have to have it this is no longer about my IT budget this is about labor augmentation and labor replacement and by the way co-work is growing even faster than Claude go at the same stage of development So what it showed is we have a near infinite TAM. It turns out that the TAM for intelligence is radically different than anything that we've seen before. And I think the best example of this, right? This is millions of self-interested parties, consumers, enterprises, a thousand now over a million dollars. Right? It's not that there was some great go to market and anthropic that all of a sudden, you know, they snuck up and blew everybody away. No, it was companies demanding the product. They're getting throttled on the product. Why? Because it's so good. It makes them better at their business. We are all self-interested actors. And when millions of those people are all making the same decision, there's a huge tell. And the tell here is that the TAM is as big as Daario and Sam and others have been saying. We knew intelligence was going to scale on the exponential. The question was whether revenue will scale on the exponential, and that's what we're seeing. And remember, they're doing this with only 1 1/2 to 2 gawatt of compute, right? These guys are massively compute constrained. They're each going to be adding 3 GW of compute this year. And so that will unlock they would be growing even faster. But for that, and then Jason, to your point about the open source models that we all want to be a part of this solution, I've talked to a lot of big companies, 65 to 70% of their token consumption is open-source model, right? are these cheap Chinese and other tokens. So these revenue ramps are happening while the world is already using open source. This is not frontier only. This is Frontier plus open source. We're going to see massive token optimization over the course of the year. But what happens on this Jebans paradox is the co the unit costs right of intelligence is plummeting. Not the cost of tokens. The unit cost of intelligence is plummeting because the capabilities of these models is so much better. I look at what it does for Altimeter day in and day out. I talked to a major uh company yesterday. They're on a run rate to do a hundred million of token consumption this year on about $5 billion in opex. They think that we're now nearing peak employment in their company, but that their token their intelligence consumption, okay, let's not call it token consumption, right? because tokens may go up a lot, but their intelligence consumption is going to go up, you know, a lot. So, I would leave you with this. We're early to Chimas's point. We have low penetration of the global 2000. We have low penetration of the use cases. We have low penetration of of within the use cases that they're already using. And the models are only getting better. So I think when you look out toward the end of the year, I would not be shocked if you see Anthropic exiting this year at 80 to 100 billion in revenue. And by the way, doing it at the same time that OpenAI, who is also on the wave, they'll be releasing an incredible model in the next imminently. They're going on that wave and you're going to see an inflection in their revenues as well.

</details>

**杰森**: 查马斯，第一个问题已经有了答案：这东西到底有用吗？现在的回答是一个惊叹号。第二个问题是营收增长，现在也是个惊叹号。最后一个拼图是：这能盈利吗？这些公司都在大量烧钱。他们什么时候能爬出“J 曲线”？

<details>
<summary>Original English</summary>

**Jason**: Okay, Chimath, question one has been answered. The question of hey, does this stuff actually have utility? that went from a question mark to an exclamation point. Of course, it's got utility. People are getting value from it. And it might be variable. Some people get more value than others. Number two, the revenue ramp was a big question. Now, that's turned into an exclamation point. The final piece of the puzzle that you've brought up many times is can this be profitable? And these companies are burning through a large amount of cash. So, what is your take on when these companies can get out of the J curve? We talked about this, I think, three episodes ago. I estimated like we're going to be looking at $4500 billion in investment into these data centers at a minimum and then they have to climb out of that to get to profitability. So what are your thoughts on these becoming profitable companies? Do you remember the investor that published this list Jason where he put all of the terms you talk about when one of the terms you can't talk about is profit. It's a list where it's like if you can't talk about free cash flow, you talk about IBIDA. When you can't talk about IBIDA, you talk about margina. When you can't talk about that, you talk about revenue. And then when you can't talk about revenue, you talk about gross revenue bookings. So you can kind of figure out, I think, where we are in any part of any cycle by just indexing into what does everybody talk about. I think where we are is we are between gross revenue and net revenue. That's where the discussion is. Okay. There was another article I think today in I think maybe it was the information that tried to categorize and distinguish that anthropic presents gross, open AI presents net. They're different. We don't know what the various take rates are. So they're saying that there's a difference. If it's not true, there's been no clarity provided by these companies. So, at a minimum, you have this confusion where there's the breathless talk. Then there's people that don't even know the difference between actual recognized revenue and run rate revenue and how to multi. I mean, so we're definitely there, okay? We can quibble about the details, but we are not at the place where people are like, "Oh, here's your steadystate, you know, free cash flow margin, and here's what your EBA does." We're never we're we're years from that. They're gonna have token maxing IBA like IB at the Wii.

</details>

**查马斯**: 我们需要弄清楚这种营收增长是否是负毛利的。

<details>
<summary>Original English</summary>

**Chamath**: The thing that we need to understand is how gross margin negative is this revenue growth.

</details>

**萨克斯**: 作为局外人，我们不知道。但布拉德可能知道。

<details>
<summary>Original English</summary>

**Sachs**: We don't know that and at least we don't as outsiders. Brad might know.

</details>

**布拉德**: 想想看，他们最大的成本投入是算力。他们只有 1.5GW 的算力。无论营收是 10 亿还是 800 亿，算力成本是固定的。所以你可能会看到这些公司的毛利率正在疯狂飙升，这是我见过技术公司毛利增长最快的一次。所以绝对不是负毛利。

<details>
<summary>Original English</summary>

**Brad**: Brad may know. I I I I will tell you think about this. What are their big cost inputs? The number one cost input is the cost of compute. Cost of compute. Right? I just told you they only have a gigawatt and a half of compute. and they have that gigawatt and a half of compute whether they have a billion in revenue or whether they have 80 billion in revenue. So you might actually expect to see these companies their gross margins are exploding higher like the fastest increase in gross margins I've probably seen out of any technology company. So this is not gross margin negative you're saying?

</details>

**萨克斯**: 那他们一定利润丰厚。

<details>
<summary>Original English</summary>

**Sachs**: No definitely not gross margin negative. And what I would tell you so that they must be hugely profitable then

</details>

**布拉德**: 你可能会看到我所说的“偶然性盈利”。他们可能花钱的速度还没挣钱快。记住，公司只有 2500 人，而谷歌达到这个营收规模时有 12 万人。

<details>
<summary>Original English</summary>

**Brad**: well you may see accidental why I call it accidental profitability. They may not be able to spend this revenue fast enough chamath on compute. And remember it's only 2500 people. Google crossed this revenue threshold when they had 120,000 people. These guys have 2500 people. So the only thing you can really spend money on, right, is compute. And they can't stand up the compute fast enough.

</details>

**查马斯**: 如果你是老牌巨头，如 Meta 或谷歌，你会希望把这变成一个**算力问题**，因为你拥有堡垒般的资产负债表。你可以用资本来碾压对手。如果你是 Anthropic 或 OpenAI，你希望智能越高效越好。我们现在还在早期阶段，还在讨论毛利和营收，还没到讨论真正的稳态利润。

<details>
<summary>Original English</summary>

**Chamath**: But none of this foots to me then to be honest because if you were on a threshold of 90% plus gross margin, I'm not saying it's there. I'm not saying it's 90% plus. I'm just saying it's gone from meaningfully negative 18 months ago to, you know, very very positive. I've seen rumored out out there 50% is what you're saying. The trend is there. Let me just say this. I think if you're an incumbent, you want the cost of compute to go down. I think if you're not an incumbent, so specifically, who do I mean? Meta, Google, and SpaceX. I think those three people who have all three of them, well, sorry, Meta and Google have a fortress balance sheet. I think by the end of June, SpaceX will also have a fortress balance sheet. What they will want to do is they will want to make this a compute problem because they will control the the conditions on the field. You already see this today. Yeah. Meta's models today, what people's general reviews are it's okay, but the one thing that people say is it's incredibly performant. The model quality is okay, but the performance is great, which speaks to Meta's huge advantage. They have a massive compute infrastructure. So if you're if you're not open AI and anthropic, they'll want to make this a capital problem because then they can win it. If you're anthropic and open AI, you want this thing to be as efficient as possible. I think where we are is very much in the early innings. And we're bumbling around talking about gross margins and you know revenues. We are not at profitability. And what is true for Facebook and what was true for Google was irrespective of where they got to a billion. Who g cares? They were profitable by year three and they never looked back. I was there. I remember it was glorious.

</details>

### 中东变局：伊朗停火与特朗普推特

**杰森**: 好了，我们要碰那个“第三轨”话题了：伊朗战争。最新进展是，在停火两周后，JD Vance 副总统、特别顾问 Jared Kushner 正前往伊斯兰堡进行和平谈判。复活节周日，特朗普发了一条 Truth 动态：“**打开霍尔木兹海峡，你们这些疯子，否则你们将生活在地狱里。等着瞧吧。**” 周二早上，他又发了一条威胁：“**一个文明今晚将会消亡，再也回不来了。我不希望发生这种情况，但很可能会发生。**”

晚上 8 点截止日期前的 6:30，特朗普宣布伊朗同意了为期两周的停火，前提是伊朗开放海峡。特朗普还开玩笑说，也许会设个收费站，我们拿大头，分给伊朗一点。萨克斯，大家想知道你对这场战争的立场。

<details>
<summary>Original English</summary>

**Jason**: Okay, here we go, guys. We're going to go to the third rail here. We got to catch up on the Iran war. Here's the latest. Two weeks into a ceasefire have started just two days ago at the taping of this VP JD Vance, friend of the pod is a and some special consultants Wikoff and friend of the pod Jared Kushner are headed to Islamabad, the capital of Pakistan for talks this very weekend. So while you're listening to this event, they are going to be working on the peace deal. Easter Sunday, Trump posted a truth stating, "Open the [ __ ] straight, you crazy bastards, or you're going to be living in hell. Just watch." Praise be to Allah. On Tuesday morning, Trump posted uh a another threat on social media. A whole civilization will die tonight. Never to be brought back again. I don't want that to happen, but it probably will. Tweets were obviously discussed uh a lot over the last week. He gave him an 8:00 p.m. deadline. At 6:30 p.m. POTUS announced on Truth Social that he had agreed. President Trump had agreed to a two-week ceasefire if Iran opens the straight. He also said, "Hey, listen. We got the straight. Maybe there'll be a toll booth, but we'll take the majority of the toll and we'll split it with Iran." Here's the quote. We received a 10-point proposal from Iran, and we believe it's a workable it is a workable basis on which to negotiate. And apparently Netanyahu took the ceasefire to mean level Lebanon dropping 160 bombs in 10 minutes yesterday. Saxs, uh, you were out last week. Everybody wants to know your position on the war. I'll hand it off to you. What are your thoughts on how on the two ceasefire and everything that's occurred up until this point?

</details>

**萨克斯**: 我要先声明，我不是白宫外交政策团队的一员。我个人的意见可能会被媒体解读为“特朗普顾问说某某”。但我认为实现停火是件了不起的事。我非常赞赏总统能够通过谈判达成停火，并派遣团队去解决问题。战争往往会有自己的生命力，很容易陷入“升级陷阱”。

<details>
<summary>Original English</summary>

**Sachs**: Well, look, I have to preface what I'm about to say, which is I'm not part of the foreign policy team at the White House. And the last time I commented on the war on this show, it somehow made international headlines that Trump advisor says XYZ. And I'm not a Trump adviser on this issue. I think that'd be a fair headline to write if it was a technology issue, but this is not. So whatever I say is just my personal opinion, but then the media is going to somehow portray it or attribute it to the White House or try and create an issue out of it. So, I feel like I'm limited in what I can say except that to say that I think it's terrific that we have the ceasefire. I think it's great that there's going to be this meeting in Islamabad to hammer it out. And I think what the president's accomplished so far with the ceasefire is it's a great thing because what happens with these wars is they take on a life of their own, meaning they tend to go up the escalation ladder, right? And there's a lot of podcasts that are discussing the so-called escalation trap and supposedly there are stages to this based on historical patterns. And so I think it's actually very hard to pull out of these things and I give the president tremendous credit for negotiating the ceasefire that we've achieved so far and then sending the team to hopefully work this out.

</details>

**布拉德**: 特朗普在伊朗问题上的原则是：摧毁其军事能力，消灭制造致命武器的人，然后撤离。市场已经给出了反应，即便特朗普发的推特吓坏了很多人，但大家相信他说到做到，会撤出来的。如果我们能让战机着陆，解决乌克兰、俄罗斯、委内瑞拉的问题，市场的上升空间是巨大的。

<details>
<summary>Original English</summary>

**Brad**: First, on March 4th, I tweeted the Trump doctrine in Iran. Massively destroy all military capa capabilities. Kill the people building lethal weapons to use against us and get out. Reserve the right to do it again if needed. Zero efforts to build Misonian democracy. Iran's going to have to build what comes next. And I think what the market has said right if you look back at last year on tariffs Jason the top tobottom draw down was about 15% on the NASDAQ intraday is down 22%. Okay, the draw down in this period over Iran was only down about 5 to 7% on S&P and NASDAQ, right? So, the market has said, listen, re trust Trump at his words. He said he's not going to get into an entangled war here. I think he terrifies the hell out of people with his tweets about, you know, destroying civilization and all this other stuff. But I think people, even though they don't like to hear it, they've resolved for themselves that when he says he's going to get out, he will in fact get out. Of course, there was a lot of hand ringing, but if you look at the markets today, we basically bounced all the way back from where we were pre-Iran on both the S&P and the NASDAQ. If in fact we land the plane, if JD lands the plane, and by the way, on Lebanon, yes, they were bombing yesterday, but Netanyahu has now said that you're going to have direct government talks between Israel and Lebanon. So, if the if we land the plane on these two things, I think it's off to the races in the market. By the way, while everybody's focused on Iran, stay tuned. I think we're getting close to a deal on Ukraine, Russia, right? Venezuela is, you know, kind of going seemingly very well. I think there's also going to be news on Cuba. You could envision a world there's risk to the downside. Certainly, I will stipulate, but you also have to pay attention to the risk to the upside. If you land the plane on those things heading into America 250 July 4th, the market could really take off.

</details>

**查马斯**: 最终做决定的是美国总统，而不是外国领导人。我认为以色列应该担心的是，除非他们能迅速找到下台阶，否则可能会失去美国这个长期稳固的盟友。

<details>
<summary>Original English</summary>

**Chamath**: I mean, the person that decides is the president of the United States. some foreign leader isn't getting to call the shots in the United States. I think very practically speaking, the markets are effectively pricing in that this was a small blip for whatever people think. That's just what the best prediction market that we have is telling us. I think that's important to acknowledge that we're probably in the endgame here. And the second thing to acknowledge is if I was Israel, I would really be concerned that unless I help find an offramp quickly, the risk that Israel loses America as a predictably steadfast ally could go down. And I think that that's problematic for Israel far more than is problematic for the United States. So all of that kind of tells me that we will find an offramp. A because I think economically it makes sense and then B geopolitically I think Israel will want to make sure that this doesn't burn a long-standing relationship.

</details>

### X 的秘密武器：自动翻译打破隔阂

**萨克斯**: 我注意到我的 Feeds 流里，以色列前总理 **Naftali Bennett** 发推说，民调显示以色列在美国变得越来越不受欢迎，他表示需要解决这个问题。我想说的是，X 的**自动翻译**功能对跨国界的理解做出了巨大贡献。Grok 在自动翻译方面做得非常好，它能把日本、以色列、法国发生的最好内容推送到你面前，当你回复时，对方看到的也是自动翻译后的。这就像是一个“真相机制”，绝对是非凡的。埃隆和 X 团队应该为此获得诺贝尔和平奖。

<details>
<summary>Original English</summary>

**Sachs**: Well, I noticed in my feed today that Naftali Bennett, who's a major Israeli politician who was a former prime minister, tweeted polling that showed that Israel was becoming very unpopular in the US and he was expressing concern about that and expressing the need to to basically address that or fix that. So, I think you're starting to see Israeli politicians raising that as an issue. And I think that's probably a good thing. Yeah, there it is. And it's really cool actually how X now just automatically translates things from foreign languages, in this case, Hebrew, and it puts it in your feed. So, yeah. So, here's Naftali Bennett, former prime minister, saying, "This is a serious situation. There's a lot of work ahead of us to fix everything." Now, obviously, this is not Netanyahu. this is one of his um political opponents. But yeah, I mean this is something for Israel to consider and think about and I think that they would improve their popularity uh if they got behind the ceasefire and I have no indication that they won't but that would certainly be a good place to start. I have to say just as an aside, this auto translate feature has done more for understanding across borders than anything I've ever seen. And it is the most impressive tech feature I I've seen released in years. Putting AI and large language models aside for people who don't know what's happening because of Grock being really good at doing auto translate. They've taken the pockets of the best of what's happening in Japan, what's happening in Israel, what's happening in France, and they're surfacing it auto translated. Then when you reply as an American to somebody in Japan, they see it autorated as well, which has led to people who don't speak the same language engaging on X in a very nuanced, fun, interesting way. And that for as a truth mechanism is just absolutely extraordinary. I think this is going to have such a profound effect. Maybe Elon and the X team should get like a Nobel Peace Prize award for this. I think it's going to change. I mean, I hate to be hyperbolic, but have you been using this feature, Chamat? Has it been coming up in your feed? And which language is up in your feed right now?

</details>

**布拉德**: 我在处理中东事务、中文、俄语、日语推文时确实看到了这个功能。

<details>
<summary>Original English</summary>

**Brad**: English. Okay. So, you're not part of the translation thing. Brad, has this hit your feed yet? And and which regions are you? Definitely. Definitely see it in on the Middle East stuff. Um, and uh, you know, I've seen on Chinese, I've seen it on on the Russian Japanese super helpful.

</details>

**萨克斯**: 让我告诉你，**日语推特**（Base Japanese）是另一个级别的怪兽。它让某些极端言论看起来都温和了。他们对移民的看法非常直接：“这就是不可接受的行为，这不是日本文化，滚出日本。” 伙计们，如果你没有 X 账号，你就错过太多了。

而且 X 在员工减少了 70% 的情况下，体验反而比埃隆进驻第一天时更好了。硅谷的每家公司都在看着这一点：我们可以用更少的人做更多的事。

<details>
<summary>Original English</summary>

**Sachs**: Let me tell you, bass Japanese is a whole another level of beast. Whoa. Man, base Japanese makes like Fentes and Alex Jones seem tame. They're like, look at this group of people. Insert whatever group of immigrants you like. And they're like, this is unacceptable behavior. This is not Japanese culture. These people need to be get the hell out of Japan. It is wild, folks. And if you don't have an X account, you are missing out. Go to X.com and sign up for this reason only because you think about the velocity. Like journalists are not even taking the time to translate and cover what's going on in those areas. And this is happening automatically in real time. So you start thinking about what happened in Ukraine. If you had people Russia and Ukraine doing this and having conversations with each other, it would be wild. You're like a such a good hype man. The problem is you hype buttered bread the same way you hype a nuclear reactor. And so it's hard to really tell, you know, what you're really hyping because your level of excitement, the intonation is exactly the same. Yo, man, there's nothing better than a slice of great toast. I mean, if this is very this in in a way, it is like sliced bread. It's very simple, but it is so powerful in the experience. This has been It is true. X is better today than it's ever been. And remember, they have 70% fewer employees than they had the day Elon walked into the building. And so if there were ever a debate about this, like, and I remember everybody saying, "Oh, it's going to tip over. Oh, it's going to be a crappy experience." The fact of the matter, here's we are a few years later, 70% fewer employees, and every other company in Silicon Valley is looking at that. I think for a lot of these tech companies, we've hit peak employment. We're going to create a tremendous number of new jobs, but for the existing jobs, these companies are all realizing they can do more with less.

</details>

**杰森**: 好了，各位。下周见。弗里伯格，我们想念你，但这确实是两年来最精彩的一集。爱你们。

<details>
<summary>Original English</summary>

**Jason**: All right, listen. We missed you, Freeberg, but this is the best episode in two years. Uh Freeird at the end of the show. And we will see you all at the liquidity summit except for the 400 people on the wait list who aren't going to get in. We got an email from the guys at Athena because we were just Oh my god. the they they're they're going to hire like 500 new Athena assistants. Yes, they had a thousand people after last week when we mentioned how much we love Athena. Go to Athena.com. But that's amazing. Those are like 500 hardworking men and women who are like working in the Philippines. Sax have great jobs. Sax, I'm going to get you a couple Athena assistants as a birthday present. That's what I'm going to get. You're going to love this, Sax. H Athena assistants are the best. Congratulations to my friends over there. All right, everybody. We'll see you next time. Love you boys on tonight favorite podcast. Let your winners ride. Rain and we open source it to the fans and they've just gone crazy with it. Love you queen of winners. Besties are gone. That is my dog taking out your driveways. Oh man, my appetiter will meet. We should all just get a room and just have one big huge orgy cuz they're all just useless. It's like this like sexual tension that we just need to release somehow. That's going to be good. We need to get merch. I'm going all in.

</details>