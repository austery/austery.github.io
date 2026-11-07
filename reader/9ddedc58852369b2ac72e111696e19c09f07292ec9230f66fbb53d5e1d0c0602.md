---
author: a16z
date: '2026-09-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GzEtpAKYRvE
speaker: a16z
tags:
  - frontier-pacing
  - existential-risk
  - agentic-workflow
  - database-architecture
  - tech-trends
title: 商业领袖的竞争、前沿发展节奏控制与AI Agent的数据库新范式
summary: 文章探讨了商业领袖在竞争中的心态、对技术发展速度的看法，以及对AI前沿研究的自动化需求。核心讨论集中在如何平衡对生存风险的恐慌与建设性讨论，并深入分析了AI Agent对极速、高弹性数据库的需求，以及如何通过技术突破实现对传统数据库范式的颠覆。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/10 -->

### 精彩片段与核心争论前瞻

**Ali Ghodsi**: 作为一名商业领袖，这里存在着公地悲剧。如果你想停下来，如果你想放慢速度，那你自己为什么不放慢呢？因为我在参与竞争，我想要赢。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: As a business leader, there's a tragedy of the commons. If you want to stop, if you want to go slower, why don't you go slower? Like, I'm competing. I want to win.

</details>

**Martin**: 这里几乎分成了两大阵营。一个阵营认为这实际上是一个工程问题，而另一个阵营则认为你必须把它放慢下来。

<details>
<summary>Original English</summary>

**Martin**: There's almost two camps. There's one camp which believes that this actually is an engineering problem, and there's others which actually believe you have to slow it down.

</details>

**Ali Ghodsi**: 人类对正在发生的攻击响应速度不够快。你必须将所有这些都自动化，而大多数组织实际上还远未做到这一点。前沿实验室正在推进的 RSI（递归自我改进）是否会把我们带向那里？这是个核心大问题。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Humans don't respond fast enough to the attacks that are happening. You need to automate all of those. And most organizations are actually not close to doing that. Is RSI and recursive self-improvement that the labs are doing leading us there? That's the big question.

</details>

**Martin**: 正如埃隆所说的，这是一场精心策划的“4D 国际象棋”：因为一方面你在对外声称全人类都会走向毁灭；另一方面你却在私下询问：“嘿，你想要多少 IPO 配额？”

<details>
<summary>Original English</summary>

**Martin**: something Elon said, this is some elaborate 4D chess because on the one hand you're saying all of humanity will die. On the other hand, you're saying, "Hey, what do you want for your IPO allocation?"

</details>

**Ali Ghodsi**: 上周破天荒头一次，有一家规模级大公司宣布他们正从前沿模型转向 GLM。你认为这代表着一种行业趋势，还是仅仅只是一个个例或轶事？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: For the first time ever, a company at scale last week said that they're moving from the frontier models to GLM. Do you think that that's a trend or do you think that's just like a one-off anecdote?

</details>

### 开场与前沿发展节奏（Pacing the Frontier）讨论

**Martin**: 额，非常感谢你能来这里，Ali。

<details>
<summary>Original English</summary>

**Martin**: Um, thank you for being here, Ali.

</details>

**Ali Ghodsi**: 我也非常兴奋。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Super excited.

</details>

**Martin**: 我们显然很想深入聊聊 Databricks，但眼下关于 AI 正在发生一场更广泛的讨论。Dario 已经发表了观点，Jakob 也表达了看法，还有 Elon 也参与其中，但我们很想听听 Ali Ghodsi 的真实想法——尤其是就宽泛意义上的“前沿发展节奏控制（Pacing the Frontier）”等话题而言。对于外界流传的这些观点，你最赞同的地方是什么？你在哪些方面持不同意见？又有哪些未被捕捉到的细微差别？

<details>
<summary>Original English</summary>

**Martin**: So, we obviously want to get to Databricks, but there is a broader conversation going on right now about AI and Dario's weighed in, Jakob's weighed in, Elon's weighed in, but we want to hear what Ali Ghodsi thinks in terms of, you know, if you called the topic broadly speaking pacing the frontier, etc. Um, what is your strongest agreement with what's being out there? Where do you disagree? And maybe where is there nuance that's not being captured?

</details>

**Ali Ghodsi**: 好的，我很乐意聊聊这个话题。我和 Martin 经常争论，所以我相信我们很快就会展开激辩。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, happy to cover it. And me and Martin argue a lot. So, um, I'm sure that's not gonna take long.

</details>

**Martin**: 这次我们会尽量克制、收敛一点。

<details>
<summary>Original English</summary>

**Martin**: We'll try and we'll try and rein it in this time.

</details>

**Ali Ghodsi**: 尽量保持冷静。不过，首先而且最重要的是，我认为——也许我们在这一点上是有共识的——领导者有责任不要无谓地制造恐慌吓唬大众，除非真的有非常非常充分的理由。大家知道，社会上不同的人处于不同的心理状态。因此，动辄谈论这些生存风险，谈论全人类都将被彻底消灭的末日图景，我认为是非常不负责任的。这可能会让很多人情绪崩溃，并引发大量的心理健康问题。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Try to stay calm. But, uh, well, I do think first and foremost that there—maybe we agree on this—that leaders have responsibility to not freak people out unnecessarily unless there's really, really good reason. And I think, you know, there's always different people in society that are at different places, you know, in their mind space. So, you know, talking about these kind of existential risks and, you know, scenarios where all of humanity is going to be wiped out, I think is irresponsible. Like, it can tip a lot of people over and it can cause a lot of like mental health issues.

</details>

**Martin**: 除非你真的手里掌握着某种足以把人类彻底毁灭的东西。

<details>
<summary>Original English</summary>

**Martin**: unless you have something that's going to wipe people out.

</details>

**Ali Ghodsi**: 是的，正如我刚才所说，如果真有切实确凿的根据，那自然是另一回事。但我认为当下生存危机的发生概率接近于零。既然如此，为什么要让所有人陷入恐慌呢？这根本毫无必要。当然，风险是存在的，我们稍后会深入探讨，那可能才是我们存在分歧的地方。但首当其冲的是，我认为领导者不应该到处吓唬大众。如果我们在 AI 研究层面存在技术上的分歧与细节争议，研究人员大可以在圈内讨论，用不着每次都跑到电视上，或者在 Twitter 上对着数千万人大声宣扬：“嘿，我认为有 10% 的概率全人类都会被毁灭。”我认为这对很多人不仅毫无帮助，实际上反而对很多人造成了相当大的伤害，让他们陷入焦虑不安，而他们根本就不理解这一切背后的技术细节与真正含义。所以这种做法是我们不应该采取的，它毫无建设性，对任何人都没有实际帮助。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, as I said, yeah, if there is a actual reason for it, then, you know, that's a different story. But I think that right now the existential risk is close to zero. Um, so why freak everybody out? It's not actually needed. There are risks. We'll get into it. That's probably where we disagree. Um, but first and foremost, I think that leaders should not freak everyone out. And I mean, you know, if there's like technical nuances in how we're doing AI research and so on, well, researchers can discuss that. You don't need to every time go on TV and or blast on Twitter to millions of people that, hey, you know, I think there's like this percentage, 10% risk that all humanity is going to be wiped out. I don't think that's like helpful for a lot of people. Actually, I think causes a lot of harm for a lot of folks who get stressed out and actually are not in the nuances of all of this stuff and what it means. So that I don't think we should do. I don't think it's fruitful. It doesn't really help anyone.

</details>

### 公众恐慌、政治介入与多方博弈

**Martin**: 我觉得这对普通公众来说非常非常真实。

<details>
<summary>Original English</summary>

**Martin**: I think this is very, very true for the general public.

</details>

**Ali Ghodsi**: 是的。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah.

</details>

**Martin**: 比如我的姐姐，她人非常好，在亚利桑那州乡村地区当学校老师。周日她给我发短信问：“我需要为你准备好避难小木屋吗？”她本身就有点末日生存准备者的倾向，但她问：“我应该为了 AI 末日准备小木屋吗？我已经储备好了水，你什么时候过来避难？”我当时只能回她：“先等一下，我们还没到那个地步。”所以很明显，这种恐慌已经蔓延到了普通民众之中，我同意——

<details>
<summary>Original English</summary>

**Martin**: Like my sister, who's great, who's a school teacher in rural Arizona, on Sunday texted me and said, "Should I prepare the cabin for you?" She's kind of a prepper anyways, but "Should I prepare the cabin for the AI apocalypse? You know, I've got water set up. Like, when are you showing up?" I'm like, "Hold on. Like, we're not there yet." So, clearly this has kind of spilled over the populace, which I agree—

</details>

**Ali Ghodsi**: 这是毫无必要的，并且会带来反噬。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: is unnecessary and has blowback.

</details>

**Martin**: 我认为还有第二点。我不知道你进演播室前有没有注意到，我刚才刷 X（Twitter）时看到 Elizabeth Warren 刚提到了关于暂停所有 AI 开发的提议。当然，这是紧随 Bernie 的步伐，而 Bernie 还在与 Steve Bannon 这样的人合作。所以现在不仅是吓唬公众的问题，联邦监管体系和政界力量也开始全面介入运转了。我认为这可能会完全背离这项提议最初的实际目标，因此这里面涉及的绝不仅仅是公众恐慌那么简单。

<details>
<summary>Original English</summary>

**Martin**: I think there's a second one, which is, um, I don't know if you saw like walking in here, I was checking X and Elizabeth Warren just talked about um pausing all of AI development. That of course is on the coattails of Bernie, who is also working with Bannon like Steve Bannon. So now, so in addition to like, you know, just scaring people, the federal complex is now spinning up and I think that could be actually quite contrary to the actual goals of the message, and so there's more than just, you know, I think public hysteria at stake here.

</details>

**Ali Ghodsi**: 是的，这里面充斥着大量的政治博弈。我身处所有这些圈子之中，能够看清两边的全貌。必须说明的是，两边都存在着极其严重的政治算计。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, there's a lot of politics going on, but I'm like in all of these groups and, you know, I see both sides. There's heavy politics happening on both sides, we should say, right.

</details>

**Martin**: 噢没错，两边都在搞政治算计。

<details>
<summary>Original English</summary>

**Martin**: Oh yeah, this is happening both sides.

</details>

**Martin**: 两党中除了特朗普本人之外的势力，似乎都一致赞同 AI 在某种程度上应当受到限制。

<details>
<summary>Original English</summary>

**Martin**: No, this is a—I think both parties that do not include Trump himself agree that AI should be constrained at some level.

</details>

**Ali Ghodsi**: 我指的也包括这场争论的另外一边。让我举个例子。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: I'm talking about the other side of this argument as well. Let me give you an example.

</details>

**Martin**: 甚至连 Greg Abbott 也是这样，对吧？连 Greg Abbott 都表态过，比如不能在德州随意建数据中心。

<details>
<summary>Original English</summary>

**Martin**: Even Greg Abbott, right? Even Greg Abbott was like, you know, you can't have data centers in Texas.

</details>

**Ali Ghodsi**: 呃，我指的并不是政客。我说的是两边都存在政治博弈：商业这一边同样存在政治算计。那些希望看到巨额 IPO 成功上市、希望从投资中获取丰厚回报的人——

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Well, I'm not talking about politicians. I'm talking about there's politics going on on both sides, right? There's politics on the business side. People who want to see great IPOs and they want to get returns on their investments—

</details>

**Martin**: 他们就会叫嚷：“别把我的 IPO 搞砸了！”

<details>
<summary>Original English</summary>

**Martin**: and they're like, "Don't mess up my IPO!"

</details>

**Ali Ghodsi**: 他们迫切希望：“嘿，大家能不能都闭嘴，好让我们把本金和利润赚回来。”所以存在着这样的一方，他们手握充沛的资源并且全力动用这些资源。因此商业资本这一侧同样在搞政治公关，他们绝非坐以待毙、什么都不做，他们能够暗中操控局面，并且拥有深厚的政商关系。而另一边，则聚集着所有想着“我们该如何把这个议题武器化？这太棒了，某某人发了这条推文，让我们把这个点当成武器打出去，把这种舆论扩散开来，大力推高这些讨论串”的人。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: and they want to get like, "Hey, can everybody just shut up so that we can get our money back?" Uh, so there's that. And they're, you know, they have resources and they're using them and, you know, so there's politics on that side and those are like not—they're not sitting quietly and not doing anything, and they can pull strings and they have connections. On the other side, there's all the people that like, "Okay, how do we weaponize this? This is awesome. This guy tweeted this, you know, let's like let's weaponize this one. Let's plant this. Let's pump these threads."

</details>

### 控制节奏（Pacing）的公关困境与公地悲剧

**Martin**: 让我们来谈谈大家都在利用的具体杠杆点。因为我其实认为这是一个极其典型的公关失策案例，而不仅仅是宣扬末日悲观论调那么简单。我认为公关上的混乱在于：行业试图进行自我监管并不罕见，这本身很正常；而且强调安全与防护极为重要，在每一轮重大技术变革浪潮中也都是如此，大家希望拥有某种监管与治理，这原本是非常合情合理的。问题在于，这一切偏偏被套上了“控制节奏（Pacing）”的包装，而“控制节奏”这个概念存在很多致命问题。首先，控制节奏与安全/防护其实是相互正交、互不相干的。就好比你放慢速度去造一件武器，这与快速制造武器在本质上并没有区别。人们觉得这不够真诚，因为这些公司此前一直在全速狂奔——

<details>
<summary>Original English</summary>

**Martin**: Let's talk to the specific leverage point that everybody is using because I actually think that this is like a classic case of a PR misstep and it's not just the doomy gloomy type stuff. So, here's the PR mess. I think which is like it is not unusual for industries to try and regulate themselves. It's just not right. And I think saying like security and safety is important, it is with every tech epoch and we want to have some oversight, that was very, very sensible. The problem is just couched in this notion of pacing and there's a number of issues with pacing. First off, it's orthogonal to safety and security. Like you can slowly build a weapon. That's not different than building a weapon. People don't feel it's genuine because like these companies have been at a dead run—

</details>

**Ali Ghodsi**: 而且他们现在仍在购买更多的算力，试图变得更快。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: they're still buying more compute to be even faster.

</details>

**Martin**: 不，我的意思是，他们历史上从来没有真正放慢过脚步，而且这种做法感觉就像是在对“暂停派”做出一种毫无原则的软弱妥协。别人喊“暂停”，你就改口说“控制节奏”，这听起来几乎就像暂停一样，但又试图显得不像真的暂停。所以他们选择打出“控制节奏”这面旗帜。但如果你实际去读一下——你读过 Dario 写的那篇文档吗？那其实是一篇完全合情合理的文档。

<details>
<summary>Original English</summary>

**Martin**: No, no. I mean, no. I mean, like they just haven't done it. They haven't done it historically, but also it kind of it kind of feels like this kind of almost milk toast capitulation to the pause people. So, you're like, "Well, you say pause, well, I say pacing, which is almost like pause, but it's not like pause." So, they chose this kind of like flag to follow around pacing. But if you actually read, did you read the document that Dario wrote? It's a totally sensible doc.

</details>

**Ali Ghodsi**: 是的，我读过了。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I read it. Yeah.

</details>

**Martin**: 它里面讲的内容根本就与放慢节奏毫无关系，对吧？所以我坦率地说——

<details>
<summary>Original English</summary>

**Martin**: It just has nothing to do with pacing, right? And so I honestly—

</details>

**Ali Ghodsi**: 不，他在文章里确实提到了这一点。听着，我在这个层面上稍微有一点不同意见。看，这里存在着公地悲剧。外界会有一种质疑声音：“嘿，如果你想停下来，如果你想放慢速度，那你自己为什么不放慢呢？为什么要写文章呼吁大家放慢？”很多人都在提出这个论点。但作为一名商业领袖，我非常理解这里面存在的公地悲剧。因为我在参与市场竞争，我想要赢；而且从市场均衡理论来看，这也表明单方面控制节奏在实践中本来就是行不通的。所以我的意思是，大家说“如果你们不一起停下，这种公地悲剧就会继续上演”，这在逻辑上是有一定道理的。我不可能自己单方面停下竞赛，因为你知道——

<details>
<summary>Original English</summary>

**Ali Ghodsi**: No, he does mention it. Look, I kind of a little bit disagree. Look, there's a tragedy of the commons. There's this like, "Hey, if you want to stop, if you want to go slower, why don't you go slower? Why do you write articles?" There's a lot of people making that argument. But no, I mean, as a business leader, I understand that there's a tragedy of the commons. Like, I'm competing. I want to win, you know, and you're also the market equilibrium, which suggests that pacing is probably impractical anyways. Yeah. So I'm just saying that so it makes kind of sense for people to say, "Hey, if you guys don't stop, this strategy of the commons is going to continue." I'm not going to stop racing because, you know—

</details>

**Martin**: 因为这里关乎巨额的 IPO 利益，关乎生死存亡的商业竞争，而且人与人之间还夹杂着真实的敌意和恩怨。所以我不会——

<details>
<summary>Original English</summary>

**Martin**: there's IPOs at stake. There is a competition at stake. There's also some animosity between the people. So like I'm not—

</details>

<!-- chunk 2/10 -->

### 单边暂停的博弈与开源安全事件

**Speaker A**: ……单方面停下来。那样我不就成冤大头了吗？你懂的，凭什么不是你们先停？所以他们其实是在呼吁：能不能有监管或外界力量介入进来，叫停大家？不过我认为，你也可以换个角度来看：看看之前 Hugging Face 与 OpenAI 的那起安全事件。顺便说一句，我认为这些公司都非常优秀，他们可能也投入了大量资源，但从公开披露的事件经过来看，事实非常清楚——

<details>
<summary>Original English</summary>

**Speaker A**: ...going to stop unilaterally. I'll be a sucker. You know why don't you stop first? You know so then they're saying hey can can you come in and stop us? Um but you know I think that uh you could also make the argument that if you look at the Hugging Face OpenAI incident that uh by the way I think these companies are great and I think they are probably investing a lot of resources but it's very clear from if you read what happened

</details>

**Speaker B**: ——事实是，他们当时并没有去监控生成的每一个 token 并对其进行把控。他们当时就是在放手跑这些强化学习（RL）实验，事后才回过头去检查到底发生了什么。所以在那起具体的事件中，他们本应该放慢节奏，本应该推进得更慢一些，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: is that uh they weren't monitoring every token coming out and having it you know they were just like running these RL experiments and then after the fact coming in and checking what happened so they should have paced they should have been much slower in that particular incident right

</details>

**Speaker A**: 我并不是想在措辞或句法上吹毛求疵，但在公关（PR）传播中，用词真的很重要。就拿 Hugging Face 的那起事件来说，当我读到那篇报告时，我的第一反应并不是“噢，OpenAI 应该放慢节奏（pace）”，而是“老兄，把你自己的东西彻底锁好、做好安全防护啊！”就像我们过去一直在做的那样，把安全控制措施落到实处。

<details>
<summary>Original English</summary>

**Speaker A**: I I just don't want I don't want just quibble on syntax but like words matter with PR right so let's take the Hugging Face incident when I read that you know you know what my reaction was is was not oh OpenAI should pace it's like dude [ __ ] secure your thing right like do security controls like we always have done like

</details>

**Speaker B**: 但这本身就是一种“控制节奏（pacing）”，这就是 pacing。

<details>
<summary>Original English</summary>

**Speaker B**: it is pacing though it is pacing

</details>

**Speaker A**: 这根本不是 pacing。在整个互联网的发展历程中，如果按照这种逻辑，我们是不是得说“让我们控制互联网的增长节奏”？做好安全防护、做好访问控制，这些都是标准操作……

<details>
<summary>Original English</summary>

**Speaker A**: it's not pacing like in the history of the internet we had all of these things like let's pace the growth of the internet let's do security let's do control let's do like what I mean you could

</details>

**Speaker B**: 这些确实该做，但它在本质上确实属于一种节奏控制。因为你看，我平时经常遇到这种事情：我在 Databricks 有法务部门，也有安全部门，他们总是要求把所有事情都慢下来——不仅仅是针对 AI，而是字面意义上的每一件小事。比如“你要去上播客？那讲稿是什么？你打算说什么？我们得先审核一下。合规和法律边界在哪里？这个不能说，那个能说；你说的每句话都必须是实质真实的，不能随意表态……”

<details>
<summary>Original English</summary>

**Speaker B**: you should do that but it is pacing in the sense that look I face this all the time. I have a legal department at Databricks. I have a security department at Databricks and you know they're always like hey slow everything down for everything not AI like literally every little thing like oh you're going to go on a podcast well what's the script for it what are you gonna say and you know let's review that and you know what's the legal you cannot say this you can say that you know everything you say have to materially true you cannot

</details>

**Speaker A**: 这屋子里就坐着专门负责卡我们节奏的人呢。

<details>
<summary>Original English</summary>

**Speaker A**: he's pacing people in this room with us right now

</details>

### 安全把控与“放慢前沿”的公关困境

**Speaker B**: 所以你看，当你在跑一个强化学习实验、训练下一个模型时，安全团队是不是应该守在那里，运行所有的监控探针并检查一切？在这些实验中，消耗了数百万 GPU 算力时长的 token 被源源不断地生成出来，那些智能体（agents）在沙盒环境里横冲直撞、四处乱跑。如果真让安全团队坐在那里逐一审查所有东西，那研发速度势必会被大幅拖慢。

<details>
<summary>Original English</summary>

**Speaker B**: so you know so you're running a RL experiment you're training the next model should the security team be there and look at like run all their monitors and look at everything I mean like millions of hours of GPU hours of tokens were produced and these agents were running you know a mock in the sandboxes it would have slowed them down significantly if we had security team sit there and look at all the stuff

</details>

**Speaker A**: 这点我完全同意。

<details>
<summary>Original English</summary>

**Speaker A**: I agree

</details>

**Speaker B**: 现在各大实验室的真实想法其实是：“如果我们主动这么做，就会被严重拖慢；而且我们无法确定竞争对手是否也在这么做。所以，监管部门能不能介入进来，统一要求大家慢下来？直接给我们画定明确的护栏，我们非常乐意遵守规则、做好安全措施。否则这根本行不通，因为我们在竞争中会被彻底击败。”

<details>
<summary>Original English</summary>

**Speaker B**: now and they're saying that hey like you know if we do that it'll slow us down and I'm not sure the other side is doing that so can you guys come in and slow us down like just tell us like put some guardrails around us we'll happily then follow the rules and do the secure thing um otherwise it doesn't make sense because we'll get our

</details>

**Speaker A**: 我只是觉得，当公众已经产生恐慌情绪时，使用这些带有微妙二阶含义的词汇是行不通的。你说“我要控制节奏（pace）以防此类事件发生”，公众根本不买账。我认为当时最明智的做法就是直接讲清楚：“安全与防护至关重要，我们正在部署这些控制措施。”这才是核心所在。但如果看实际效果，这种微妙的表达完全被误读了。

<details>
<summary>Original English</summary>

**Speaker A**: I just I just think like nuance second order words don't work when like people are really afraid you're like I'm going to pace and therefore or things like these don't happen. I literally think we should have just been like safety and security is paramount. We're going to put in these controls. Like that's the important thing. And I do think that nuance actually got lost if you look at

</details>

**Speaker B**: 你赞同扎克（Mark Zuckerberg）当时的表态吗？

<details>
<summary>Original English</summary>

**Speaker B**: what Zuck said. Do you agree with

</details>

**Speaker A**: 我觉得扎克的做法就像是在说：“我们会把握好自己的节奏，我们会加入安全机制；我们之所以推迟发布，完全是出于安全考量。”

<details>
<summary>Original English</summary>

**Speaker A**: I thought Zuck did like hey we're going to pace ourselves. We're going to put in SEC like the reason we released this later is because of security.

</details>

**Speaker B**: 听我说，我认为扎克做得非常出色的一点在于，他把焦点牢牢锁定在安全、防护以及自我监管上。而 Dario（Dario Amodei）一开口的前几个词却是“我们需要放慢前沿的步伐（pace the frontier）”。这瞬间就会把人带入一种完全不同的心理认知；而他本可以说“我们需要保障前沿的安全（secure the frontier）”。

<details>
<summary>Original English</summary>

**Speaker B**: Well listen what I thought was so great about Zuck is like he was very focused on like like security um safety and self-regulation. Dario Dario's first five words or whatever are like we need to pace the frontier right it just puts you in a very different mindset than what he could have said is we need to secure the frontier

</details>

**Speaker A**: 没错，“我们需要前沿安全”。在某种程度上，我认为他们当时既想迎合那些呼吁暂停研发的“末日论者（doomers）”，又想迎合政策制定者，结果两头都没讨好。

<details>
<summary>Original English</summary>

**Speaker A**: fine we need safety the front I mean there like at some level I think they were trying to optimize both for the doomers which cause for pause and for politicians and they kind of didn't satisfy either

</details>

**Speaker B**: 但现实是，大模型实验室内部的人确实正在陷入恐慌。顺便说一下，很多安全研究人员是真的在恐慌，而且他们并不全都是有效利他主义（EA）那一套信徒。大家就是纯粹被模型的表现给震惊到了。

<details>
<summary>Original English</summary>

**Speaker B**: but those people are actually freaking out inside the labs and there are a lot of safety people that are freaking out genuinely by the way and not all of them are EA people and so on People are like, "Hey, they're surprised." Right.

</details>

**Speaker A**: 确实如此。但关键问题在于，使用“放慢节奏（pace）”这种词对于两边都没有任何帮助。

<details>
<summary>Original English</summary>

**Speaker A**: Right. But here's the thing is like using the word pace doesn't help

</details>

**Speaker B**: 根本帮不上任何一边。这完全像是陷入了某种公关的“恐怖谷”——它同时激怒了末日论群体和政策制定者。末日论者会说：“这根本不是暂停研发，这只是调整节奏而已！”

<details>
<summary>Original English</summary>

**Speaker B**: either of them. I think I think it's like literally you're like you're trying to find this like pace is like the uncanny valley of making the doomer people unhappy and the policy people unhappy because the doomer people are like that's not a pause. This is pacing. Yeah.

</details>

**Speaker A**: 而其他人则会认为：“这根本不现实，你们反正也不会真的停下来，而且你们也没有真正聚焦在安全控制上。”所以抛开我们实际应该怎么做不谈（这个问题我们稍后应该深入讨论），我只是觉得当初的那种对外宣发方式非常糟糕，根本没有起到预期效果，这也是为什么现在会遭遇如此强烈的舆论反弹。

<details>
<summary>Original English</summary>

**Speaker A**: And you know everybody else is like well like this is you know this isn't real. You're not going to do it anyways and and you're not focused on security. So so again independent of what we should do which we should talk about. I just think that the way it was presented was just bad and it just didn't work and that's why we're having the blowback.

</details>

**Speaker B**: 这些技术人员毕竟没有受过专业的公关训练。诚然，对于其中一部分观点我是认同的……

<details>
<summary>Original English</summary>

**Speaker B**: These guys are, you know, uh they're not trained uh, you know, PR people, you know, and yes, some of the stuff I agree I agree with. I mean, I agree with

</details>

**Speaker A**: 确实没有受过专业公关训练。

<details>
<summary>Original English</summary>

**Speaker A**: trained PR people.

</details>

### 强化学习的现实风险与超级智能的条件假设

**Speaker B**: 我认同其核心前提，即我们不应该让公众陷入恐慌。我认为目前所谓的“人类生存危机（existential risk）”概率基本接近于零。但是，让我们来讨论核心的问题：任何在进行大规模强化学习训练并为其设定奖励函数的人，如果放出上万个智能体，投入上亿美元，让它们在一个庞大的计算集群上并行运行一两个月去尝试解决任何问题——甚至不需要是专门的安全任务，哪怕只是让它们去解一道数学难题——都可能会发生非常糟糕的后果。这里所说的“糟糕后果”是指系统被入侵或破坏，其中网络安全（cybersecurity）就是最首要的风险。

<details>
<summary>Original English</summary>

**Speaker B**: I agree with the core premise that we shouldn't freak the public out. I think that existential risk right now is close to zero. um you know uh but let's talk about the core thing which is um the the fact that you know anyone who's doing big reinforcement learning runs and they're giving it a reward function. So unleashing you know saying hey here's like a you know 10,000 agents and here's $100 million let's put them in parallel and let them run on a gigantic cluster for a month or two try to solve anything and it doesn't need to be a security thing. It could be like do anything you know solve this math puzzle really bad things can happen really bad things meaning things get hacked and it has you know cyber is the primary one

</details>

**Speaker A**: 没错，这才是实实在在的风险。而把这些包装成“生存危机”之类的论调，我认为是一个严重的错误，这样去吓唬公众非常不好。

<details>
<summary>Original English</summary>

**Speaker A**: right that is real right I think of this making it hey this is an existential risk and so on which I think was a mistake I think it's not good

</details>

**Speaker B**: 这样去吓唬公众，导致现在全世界所有人都在讨论这件事，连平时完全不在意这些话题的人都被卷了进来。很多以前从来不关心技术、觉得这些东西极其枯燥的人，都发消息问我：“你到底怎么看？这对我真的很重要吗？我现在开始感到担忧了。”于是这演变成了一个政治议题。我们马上迎来大选，全球各地也都在举行选举，世界其他地区同样不会坐视不管。但我认为，以客观平衡的方式去阐述这个问题并如实揭示真实风险，是我们的责任。至于书中描绘的那种“超级智能（superintelligence）”，我认为还极其遥远，我没有看到任何证据表明我们正在快速走向那一阶段，或者它即将发生。

不过，大模型实验室里的某些人似乎确实被吓到了，他们担心我们可能正在取得通往那一步的进展，这种担忧主要源自递归自我改进（Recursive Self-Improvement, RSI）——即模型在不断改进自身。我非常想弄清楚他们究竟看到了什么我们不知道的信息。

要真正实现所谓的自我迭代飞跃，需要满足四个判据条件。如果这四件事同时发生，我非常乐意去深入理解它们：
第一，训练下一代模型所需的计算资源和 GPU 数量呈现超线性（superlinearly）减少，而不是仅仅微量减少；
第二，下一代模型所需的训练时间也同步大幅缩短；
第三，模型的准确率与智能水平显著提升；

<details>
<summary>Original English</summary>

**Speaker B**: to scare the public that way um I think it's become something that everyone not just your sister everybody around the planet is like now talking about I've had all kinds of people that never care about this stuff and they find this extremely boring uh ping me and say what do you really actually think about this is really important in my account. Now I'm starting to worry about it. Uh so then it becomes a political issue and we have elections here coming up but there's elections all around the world. Uh so you're going to see they're not going to sit still in other parts of the world either. Uh but I think that's our responsibility to talk about this uh in a balanced way and actually expose the risks. I think that super intelligence that idea from that book is very very far away. I don't see any evidence that we're actually marching towards that or that's going to happen. Apparently some people Yeah. Apparently some people at the labs are freaked out that maybe there's progress towards that and I think it comes from RSI recursive self-improvement the model is improving themselves. Uh I would love to understand how much what have they seen something we don't know. Uh there's you know kind of four criterias if there if those four things are happening I would love to understand them. One is our models uh the ne if if we end up in a situation where following four conditions are happening which is the next model require less resources less GPUs to train and you know super linearly not just like tiny little bit the next model uh you know takes less time to train as well. So the second condition uh third accuracy of the model the intelligence is increasing

</details>

**Speaker A**: 第四，我们能够将前三个过程一遍又一遍、循环往复地持续进行下去。

<details>
<summary>Original English</summary>

**Speaker A**: and fourth we can do the former three again and again and again in a you know it's not just

</details>

**Speaker B**: 这四个条件必须在同一时间全部成立，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: all all of those at the same time right

</details>

**Speaker A**: 必须全部同时发生，缺一不可。

<details>
<summary>Original English</summary>

**Speaker A**: all at the same time not just any of them yeah

</details>

**Speaker B**: 是的，只有当这四项条件全部同时满足时，你才能想象那种真正失控的自我迭代飞跃。因为只要其中任何一项不满足——比如所需计算资源保持恒定，那情况就还在可控范围内，因为我们终究会耗尽硬件资源，缺乏足够的 GPU 算力，系统就会自然放慢节奏；训练时间也是同理。所以必须同时满足这些极其苛刻的条件。如果大家仅仅是指“软件正在编写自身”，那我们今天早就已经实现了，Databricks 内部超过 90% 的软件代码……

<details>
<summary>Original English</summary>

**Speaker B**: all four if all four are happening uh then you can imagine in a way where you can you know cuz any of them does not happen like for instance if resources is constant then that's okay because we're going to run out of hardware so then it'll pace itself like we will not have enough hardware to do that not enough GPUs right uh time the same. So it needs to be that you end up in this situation. So if it's if you just mean that the software is writing itself, uh we're already there today like 90 some percent of the software in Databricks is

</details>

<!-- chunk 3/10 -->

### 递归自我改进与超级智能的判定条件

**Speaker A**：……由 AI 编写。那么最后这几个百分点是否也是由 AI 编写的，这真的有那么重要吗？其实并没有那么重要。但如果你满足了这四个条件，就可能会迎来一种加速发展：下一个模型的开发耗时减半、消耗的资源减半，而且智能水平更高；如果你沿着这条路径持续推进，最终可能会进入这样一种情境——顺便说一句，我甚至都不知道这是否必然会带来狭义上的超级智能……

<details>
<summary>Original English</summary>

**Speaker A**: ...written by AI. Does it matter if the last few% is also written by AI? No, it doesn't matter really that much. Uh but if you're getting these four conditions then you might get a speed up where the next model let's say takes half amount of time and half the resources and it is more intelligent and you keep doing that you know uh then you might end up in a situation where I don't know by the way I don't even know if that necessarily leads you to super intelligence per...

</details>

**Speaker B**：它可能仍然会收敛，是的。

<details>
<summary>Original English</summary>

**Speaker B**: ...still converge yeah.

</details>

**Speaker A**：但它确实有可能导向超级智能，所以那样一来风险就会更高。因此，如果他们能够共享所有这些数据，让我们能够对此保持透明并加以审视，那就太好了。

<details>
<summary>Original English</summary>

**Speaker A**: ...but it could so then that would be more risky so that it would be nice if uh they can share all that data and we can shine some light and transparency on that.

</details>

**Speaker B**：我认为你做的这个拆解分析非常棒。

<details>
<summary>Original English</summary>

**Speaker B**: I actually think it's a great breakdown that you have.

</details>

**Speaker A**：我觉得实际上根本没有人在用这个作为定义，对吧？大家有些人在恐慌，觉得“天哪，涌现行为出现了，现在它正在自我创造了”等等。但我认为，就像我说的，很多人的定义仅仅是：“嘿……”

<details>
<summary>Original English</summary>

**Speaker A**: I don't think anyone is using that as a definition actually right I think people I think there There's a little bit of people freaking out about like oh my god emergent behavior now it's creating itself and so on but I think like as I said a lot of people their definition is just hey...

</details>

**Speaker B**：“如果连我都不再写代码了，全靠它自己写代码……”

<details>
<summary>Original English</summary>

**Speaker B**: ...if I'm not even coding anymore and it's coding itself...

</details>

**Speaker A**：对。

<details>
<summary>Original English</summary>

**Speaker A**: ...right.

</details>

**Speaker A**：但我认为他们混淆了两件事：一边是“我的个人价值何在、这对我来说是否可怕”，另一边则是“这是否意味着我们将迎来博斯特罗姆（Bostrom）在 2014 年从理论上假设的那种超级智能”。

<details>
<summary>Original English</summary>

**Speaker A**: ...uh but I think they're conflating hey what's my value and is it scary for me versus hey that then means we'll get that super intelligence that 2014 theoretically was uh hypothesized bystrom um...

</details>

### 算力门槛与前沿模型训练的现实反论

**Speaker B**：不过你在算力方面的观点非常精辟，我认为这在很多关于递归自我改进（RSI）的争论中都被忽略了，对吧？因为就我们目前所知，训练一个优秀模型所需的最低算力门槛一直在不断攀升。以前可能是 1 亿、10 亿，现在大概需要 50 亿美元了。所以……

<details>
<summary>Original English</summary>

**Speaker B**: ...well your point in compute though is a really good one that's missed in a I think in a lot of arguments on RSI right Because as far as we can tell, the minimum threshold for compute needed to train a good model just keeps going up. Like it was 100 million billion now it's probably like 5 billion. Um and so that...

</details>

**Speaker A**：现在训练一个模型……

<details>
<summary>Original English</summary>

**Speaker A**: ...you train a model now...

</details>

**Speaker B**：训练一个前沿模型，对吧。

<details>
<summary>Original English</summary>

**Speaker B**: ...to train like a frontier model. Right.

</details>

**Speaker A**：要 50 亿到 100 亿美元。

<details>
<summary>Original English</summary>

**Speaker A**: ...5 to 10 billion.

</details>

**Speaker B**：对，没错，正是如此。相比之下……

<details>
<summary>Original English</summary>

**Speaker B**: Right. Right. Exactly. Versus...

</details>

**Speaker A**：几十亿、几十亿、几十亿、几十亿美元，是的。

<details>
<summary>Original English</summary>

**Speaker A**: ...billion billion billion billion. Yeah.

</details>

**Speaker B**：相比之下非常昂贵。

<details>
<summary>Original English</summary>

**Speaker B**: Versus very expensive.

</details>

**Speaker A**：是的，前沿模型极其昂贵。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Frontier is very expensive...

</details>

**Speaker B**：而要在 6 个月后复现这个前沿模型，成本大概只有二十分之一。不，我觉得莎拉（Sarah）提到了一个极好的观点，这也是反驳整套递归自我改进论调的一个有力论据：首先，各家前沿实验室每年只能进行一到两次这样的完整训练运行……

<details>
<summary>Original English</summary>

**Speaker B**: ...to to replicate the frontier 6 months later is about 120th the cost. No, I think Sarah has a great point which is it's this is a good argument against this whole thing which is that the next model first of all there's only one or two such runs a year that each of these labs do...

</details>

**Speaker A**：而且它们所呈现的情况，正好与我刚才提到的四个条件完全相反，对吧？也就是说，下一个模型需要投入更多的资源、需要更多的人类参与，而且过程更加脆弱。他们必须建设数据中心——我的意思是，实验室本身不一定亲自去建，但其他人必须去建，而且数据中心的规模必须极其庞大；他们必须搞到 GPU，必须调通网络连接，必须做好工程架构以确保系统具备容错能力。因为要知道，你每塞进去一个数量级更多的 GPU，就必须去操心以前根本无需担心的硬件与网络故障。所以你必须提高系统的鲁棒性。这是一个非常脆弱的过程，一旦失败，你就会挥霍掉天文数字般的资金。因此他们对每一次训练运行都极其慎重，而且已经发生过多起训练失败或搞砸的情况了。

<details>
<summary>Original English</summary>

**Speaker A**: ...and they take it's the opposite of the four criterias that I mentioned right which is it's going to take more resources more humans involved and it's even more brittle and they have to build out the data centers I mean like the labs are not necessarily doing that but others have to build the data centers and they have to be gigantic and they have to get the GPUs and they have to get the networking right they have to do the engineering to make sure that they can tolerate because you know every order of magnitude more GPUs you cram in there, you have to now worry about errors that before you didn't have to worry about. So you have to increase robustness of the So it's like a very brittle process and if it fails, you've squandered so much money. So they're like very very careful with that run and there's been multiple runs that have been botched.

</details>

**Speaker B**：所以实际情况恰恰相反：大家以为“下一个模型更快、更便宜、更聪明并且能递归改进”，但现实却是耗时更长、系统更脆弱、需要更多的人……

<details>
<summary>Original English</summary>

**Speaker B**: So it's it's the opposite of that that hey the next model is faster, cheaper, smarter and recursive improve. It's the opposite. It's like it's taking longer and it's more brittle and it's more people...

</details>

**Speaker A**：而且实现难度更高。所以，我确实认为这是事实。

<details>
<summary>Original English</summary>

**Speaker A**: ...and it's harder to pull off. So, um I do think that that is true...

</details>

**Speaker B**：就 RSI 而言确实如此；而就实际的网络安全风险和系统被黑客攻击的风险而言，我们需要对此给予高度重视，是的。

<details>
<summary>Original English</summary>

**Speaker B**: ...with respect to RSI, with respect to actually cyber risks and things getting hacked. We need to take it super seriously. Yeah.

</details>

### 黑盒检验标准：人员编制与算力资源演变

**Speaker B**：所以我在这里可能会有另一个角度的看法：我其实很喜欢你提出的这四项标准，我刚才简直就是坐在这儿等着反驳它，但我发现这确实非常精辟。所以，让我给你提供一个类似于“黑盒检验”的视角。当你面对这些动态自适应系统时，你该相信什么？你是相信客观数据，还是相信你容易被蒙蔽的眼睛？对吧？所以，我认为在这些问题上你必须回归数据。那么，应该看哪些数据呢？我真的认为，也许看它们上市公开的数据是一种合适的方式。比如，如果这些公司在业务持续扩张的同时，人员规模在缩减，投入的资金规模也在减少，那我就会说：这里绝对发生了一些质变。我认为你确实可以把这当作一个黑盒来观察。但目前的迹象完全不是这样，他们正在疯狂招人，疯狂扩张。

<details>
<summary>Original English</summary>

**Speaker B**: So, I'm I'm going to have like another like miss here like I actually love your four criteria. I was like literally just waiting to argue with it, but I actually think it's this is very good. Uh so, I'm let me give you like um like a blackbox what when like when you're dealing with these like dynamic adaptive systems like what are you going to believe? Are you going to believe like the numbers or your lying eyes? Right? Right. So, I think you kind of have to go to the numbers on these ones. So, like what are the numbers to look at? I really think you should just basically and maybe going public is the right way to do it. Like like if if these companies continue to grow, reduce the number of people and the number of amount of money that goes into them, um then I would say something is is definitely happening here. Like I do think that like you can actually blackbox this and take a look. But none of those indicate like they're hiring like crazy. They're like crazy.

</details>

**Speaker A**：这不太公平，因为你知道公司并不一定是高效运作的，对吧？举个例子，OpenAI 自身当时在同时做上百万种不同的业务，而做大语言模型（LLM）的其实只是一个大约 10 人的极小团队，但正是这部分 LLM 成果发挥了巨大作用。就像 Twitter 以前有很多人，现在人少得多了。

<details>
<summary>Original English</summary>

**Speaker A**: That's not fair because you know companies are not necessarily efficient, right? So like what if you have I mean OpenAI itself was doing like a million different activities. A very small team of like 10 people were doing LLMs and the LLM stuff was useful. Twitter there was a lot of people now it's much less people.

</details>

**Speaker B**：我同意，这只是另一种试金石。我们可以同时设立两套试金石：一套是你提出的试金石，我觉得非常棒，但你需要一种能够具体测量和监测它的手段；另一套则是黑盒试金石。比如，听着，如果 Anthropic 在两周后缩减到只有 12 个人，并且公司持续增长，同时以越来越快的速率发布模型，那么我认为我们大概就该警惕并重视起来了。

<details>
<summary>Original English</summary>

**Speaker B**: I agree it's just another litmus test. We have can have two litmus test. We have your litmus test which I think is great but then you would actually have to have a way to instrument it. Yeah. And then we should have the blackbox listen test. Like I mean listen if if anthropic in two weeks is you know 12 people and they continue to grow and they're putting out models at an increasing rate I think we should probably take notice of that.

</details>

**Speaker A**：那是充分条件，但不是必要条件，对吧？但我只是想说，事情有可能是这样的：真正合理的观察方式是去看当前进行的预训练（pre-training）和后训练（post-training）中那些真正必不可少的核心部分。因为他们坐拥如此庞大的资源，可能会去做很多根本不需要做的多余杂项，之所以做只是因为他们有花不完的钱和资源，可以随便招人。所以，真正训练下一个模型的团队其实极小极小，而且这个团队的规模实际上还在缩减，他们干的活越来越少，全都由 AI 自主接管，包括后训练也是如此，并且他们使用的 GPU 越来越少……

<details>
<summary>Original English</summary>

**Speaker A**: ...that's sufficient criteria but it's not necessary condition right but I'm just saying that you know it could be that you know and really the right way to do this then to look at okay the pre-training and the post- training that's being doing that's really necessary because they have so much resources that they might be doing a lot of other stuff they don't need to do but they're doing it just and they can just hire the people because they have infinite money and infinite so really the people that are training the next model is that team tiny tiny and it's actually getting reduced and they're doing less and less work and just the AI is doing it and the post training and then they're all just using less GPUs...

</details>

**Speaker B**：但现在根本不是这种情况。

<details>
<summary>Original English</summary>

**Speaker B**: ...that's not the case.

</details>

### 历史上的算力恐慌与当前安全风险

**Speaker B**：作为一个行业，我们以前经历过很多次类似的争论。我还记得当年我们学会如何真正构建计算机集群的时候，因为大型机（mainframe）实际上受限于内存一致性（memory coherence）等物理瓶颈。还记得吗？你只能把大型机做到那么大，然后……

<details>
<summary>Original English</summary>

**Speaker B**: ...we've had this argument many times as an industry before. I remember when like like we learned how to really cluster computers because like the main frame was actually kind of limited by things like memory coherence. Remember that like you can only make it so big and you have...

</details>

**Speaker B**：然后我们就转向了客户端-服务器架构（client-server），那样就没有那个问题了；随后我们开始制造超级计算机，本质上也就是计算机集群。

<details>
<summary>Original English</summary>

**Speaker B**: ...you know and then we kind of went to the client server and then we didn't have that problem and then we started creating supercomputers which were like basically just like you know clustered computers.

</details>

**Speaker A**：是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yep.

</details>

**Speaker B**：然后……

<details>
<summary>Original English</summary>

**Speaker B**: Um and...

</details>

**Speaker B**：在某个时刻互联网出现了……

<details>
<summary>Original English</summary>

**Speaker B**: ...at some point internet happened...

</details>

**Speaker B**：大致也是在那个时候，GPU 开始崭露头角。你还记得当时我们甚至对 PlayStation 游戏机实施出口管制吗？

<details>
<summary>Original English</summary>

**Speaker B**: ...and and and and that was kind of also roughly like when GPU started getting good. And do you remember that we would actually like export control PlayStations...

</details>

**Speaker B**：因为我们担心萨达姆·侯赛因会用它们来进行军事模拟。当时的论调非常相似，都是在说……

<details>
<summary>Original English</summary>

**Speaker B**: ...cuz we were worried that Saddam Hussein would use them to do simulation. And the arguments were very similar which is like...

</details>

**Speaker B**：“这些东西正变得无限强大，我们正在用它们来模拟核武器”——当时确实在用，我自己就在这么做。

<details>
<summary>Original English</summary>

**Speaker B**: ...these things are getting infinitely powerful. We're using them to simulate nuclear weapons which we were like I was.

</details>

**Speaker A**：是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**：当时人们说：“我们不能这样，这东西存在生存性风险（existential risk）。”其实他们当时没用这个词，但意思就是“这有可能被用来制造核武器之类的东西，我们必须阻止它”。然而，这些预言没有一个真正发生。因此，我认为一个非常合理且值得探讨的问题是：这一次真的会有所不同吗？是，还是不是？对此我也没有确切答案。

<details>
<summary>Original English</summary>

**Speaker B**: Um like we can't you know this stuff has existential risk. Actually they didn't use those words but like this has the potential for like nuclear weapons or whatever and we should stop it. And like none of that came to path. So, I think a very reasonable discussion is is is is this time different? Yes or no? I don't have an answer to that.

</details>

**Speaker B**：但我是一台 PC，而你知道，你是一台……

<details>
<summary>Original English</summary>

**Speaker B**: But I'm a PC, but you know, you're a...

</details>

**Speaker A**：是啊。我的意思是，听着，我想我还不够老，记不得那些事。所以无知便是福，我就当这是夸奖收下了。得了吧。所以……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean, look, I I think I was I'm I'm not old enough to remember. Uh so, ignorance is bliss. So, I can take this. Come on. So,

</details>

**Speaker A**：我真不记得当年 PlayStation 是非法的、萨达姆·侯赛因如何如何，我确实不知道。可能只是我孤陋寡闻吧。

<details>
<summary>Original English</summary>

**Speaker A**: I I don't recall PlayStations being illegal and Saddam Hussein being I I just don't know. Maybe I'm just Maybe I'm just ignorant.

</details>

**Speaker B**：那大概是 1999 年左右的事。

<details>
<summary>Original English</summary>

**Speaker B**: This is like 199.

</details>

**Speaker A**：可能是我年纪大了而且孤陋寡闻吧，我是说，你懂的……

<details>
<summary>Original English</summary>

**Speaker A**: Maybe I'm old and ignorant. I mean, you know,

</details>

**Speaker B**：也许瑞典人根本不在乎这个？是不是……

<details>
<summary>Original English</summary>

**Speaker B**: maybe they didn't care in Sweden. Is that...

</details>

**Speaker A**：也许只是上年纪引起的健忘症吧。但无论如何……

<details>
<summary>Original English</summary>

**Speaker A**: Maybe it's just amnesia from age. Uh but whatever it is,

</details>

**Speaker B**：瑞典根本不在乎美国的出口管制。

<details>
<summary>Original English</summary>

**Speaker B**: Sweden doesn't care about the export controls in the US.

</details>

**Speaker A**：是啊。不管怎样，我认为现在的 AI 处在一个完全不同的量级上，对吧？伴随着 AI 的发展以及我们目前正在做的事情、推进的速度等等，前沿领域的进展确实令人震惊。我确实认为网络安全（cyber）实际上将是我们所见证的最大威胁之一，对吧？因为……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. You know, whatever it is, uh I think it's it's at the different scale now, right, with the AI and you know, with the you know, what we're doing, uh the pace of development and so on, uh they are freaking out the frontier. I do think cyber is actually one of the biggest one that we're going to see, right? Because um...

</details>

**Speaker B**：顺便提一句，因为如今地球上的基础设施实在太多了，远远超过了当年不管是萨达姆、Xbox 还是你提到的任何时期的规模。我是说，我们现在把太多的事物互联在一起了，而且它们彼此高度依赖……

<details>
<summary>Original English</summary>

**Speaker B**: ...it's there's just so much infrastructure on the planet, by the way, way more than it was whenever whatever Saddam or Xbox or whatever it was you're talking to. I mean like we've just interconnected way more things and they're dependent...

</details>

<!-- chunk 4/10 -->

### 网络基础设施脆弱性与智能体安全风险

**Martin**：而且，从对互联网技术的依赖程度和全球互联互通的格局来看，今天的世界与三十年前相比已经完全不同了。所以我想强调的核心观点是，当前存在着海量处于不安全状态的基础设施。

<details>
<summary>Original English</summary>

**Martin**: And like the planet just looks different today from internet tech dependency, interconnection, than, you know, 30 years ago. So I just want to make this point: there's so much infrastructure that's insecure.

</details>

**Databricks 负责人**：没错。如果你把这些 AI 智能体（Agents）释放出去，它们就会去寻找各种漏洞，寻找可以利用的攻击面，在这里或那里尝试攻破系统。所以这是一个切切实实存在的风险，你不能对此视而不见——顺便说一句，这一次模型还没有做出这种破坏行为。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Right, and if you're going to unleash these agents, they're going to find loopholes, they're going to find exploits, they're going to break in here and there. So this is a real risk, you can't just... and by the way, this time it didn't do that.

</details>

**Martin**：但你完全可以设想这样一种场景：智能体开始跨节点跳跃，它获取了计算资源并在其他机器上自我复制执行，就像病毒一样四处扩散传播，这确实是一个实质性的风险。

不过，出于纯粹的好奇——我保证我并不是在这里故意唱反调或刁难你——但你觉得为什么我们到现在为止还没看到太多这种严重的破坏事件呢？我的意思是，我比你年长得多，我对当年的情况记忆犹新。在互联网刚刚兴起的那个年代，走到当前这个发展阶段时，网络蠕虫病毒已经实打实地瘫痪了 10% 的网络，导致医院系统停摆，摧毁了关键基础设施，并造成了数百亿美元的直接经济损失。所有这些破坏在当时早就已经真真切切地发生了。而且正如你所说，当年的数字化建设规模要小得多，承载的经济体量也少得多。而现在的 AI 领域有如此多的人在全力寻找风险与安全威胁，行业发展速度如此之快，涌入了如此庞大的资金，但我们至今还没有看到任何能在严重程度上与早期互联网蠕虫病毒相提并论的灾害。这种预期的脱节究竟是因为什么？

<details>
<summary>Original English</summary>

**Martin**: But you could imagine a scenario also where it starts hopping, like it takes resources and it starts executing itself elsewhere, so it kind of spreads like a virus a little bit. That's a real risk. So—and this is pure curiosity, I promise I'm not, you know, trying to be a foil here—but why do you think we just haven't seen very much then? Like again, I'm much older than you, I remember very well. When the internet came out, by this point we had literally taken out 10%, we'd disabled hospitals, we'd taken out critical infrastructure, we'd caused tens of billions of dollars in economic damages from worms—like all of that had already happened. And to your point, we had much less buildout, you know, less of the economy was on it. And so AI has so many people that want to find risks and threats, we're running so fast, so much money has been poured into it, and we haven't seen anything commensurate with the early days of worms. What is that disconnect?

</details>

### 安全防御的自动化竞赛：从传统 SOC 到智能体威胁猎捕

**Databricks 负责人**：是的。听着，我也很清楚当年的那些历史。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Yep. Look, so I do remember those days.

</details>

**Martin**：我们经历过那个时代。

<details>
<summary>Original English</summary>

**Martin**: The same time.

</details>

**Databricks 负责人**：是的。所以，我个人的看法是，我目前晚上依然睡得很踏实，我并不认为眼前存在什么所谓的“人类存亡级危机”（Existential Risk）。但我确实认为，当前有大量的底层基础设施急需进行安全防护加固。

我们在安全检测市场上推出了一款名为 Lakehouse Watch（LakeWatch）的产品，旨在帮助企业进行安全威胁检测。这个领域的发展速度简直是日新月异。因为在过去，企业通常依赖传统的 SOC（安全运营中心）团队，由安全分析师人工去查看发生了哪些入侵事件、系统正在遭受怎样的攻击等等；而现在，仅靠人工已经完全无法跟上这种攻击节奏与数据规模了。

因此，整个网络安全领域正在经历一场深刻的转型——全面转向利用 AI 智能体来实现自动化的端到端安全检测。如果我们不加快推进这一点——事实上，整个行业目前都在争分夺秒、极其迅速地推进这项变革——如果我们不这样做，我认为大家很快就会开始看到类似的问题发生：比如网站频繁宕机、整个系统长时间停摆瘫痪，并且必然会带来一系列后果。这虽不至于造成人类灭绝的存亡危机，但巨大的经济损失、关键业务中断甚至间接导致人员受到伤害等情况是完全可能发生的。

因此，我们必须全速赛跑，把这一整套防御体系彻底建立起来。面对正在发生的安全攻击，人类的反应速度已经远远不够快了。你必须将所有的检测与响应流程全面自动化，而目前绝大多数组织实际上离实现这一目标还差得很远。大型银行正在付诸实践，一些安全意识极强的头部机构也在做，但当今大部分行业依然在靠老旧传统的安全运营中心模式运转——安全运维人员每天早上一睁眼，邮箱里就塞满了数百封由告警规则触发的安全事件邮件。其中很大一部分仅仅是误报，可以忽略不计；但其中确实混杂着真实的安全威胁，而他们根本没有足够的人力和时间逐一排查并揪出真正的威胁。

企业必须拥有全自动化的威胁猎捕（Threat Hunting）能力，利用智能体主动、自动地对自己的系统进行持续的攻防模拟与压力测试。但目前行业整体还没普遍做到这一点。所以如果单纯认为这只是早期互联网的重演、坏事迟早会发生，那么这背后其实正在展开一场攻防双方的技术军备竞赛。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Yeah. Look, I would just say that I am sleeping well at night and I don't think there's existential risk right now. I do think there's a lot of infrastructure that needs to be secured. Yeah. We have a product in the market, in the detection market, LakeWatch, that helps you do detections, and the space is just moving so fast. Because you used to have these SOC teams, security operations center people, that would look at what intrusions are happening, how are we being attacked, and so on, and now the humans just can't keep up. So the whole cybersecurity space is being transitioned into fully automated using agents for detection on the other side.

If we don't do that—I mean now we're rushing, the industry is rushing to do that super super fast. If we don't do that, I do think you will start seeing those kind of things, like sites going down, you know, whole systems that stop working for a while, and there will be consequences—not existential, but economic damage and, you know, people getting hurt and so on could happen. So we just have to race very, very fast to do all of those things. Humans don't respond fast enough to the attacks that are happening. So it just, you need to automate all of those, and most organizations are actually not close to doing that.

The banks are doing it. Some of the people that are super security conscious are doing it, but most of the industry today is running with old school security operation centers and people that are waking up every day and there's like hundreds of emails of detections that have fired. Many of them are just false positives, so you don't need to—you can ignore them, but some of them are not. They just don't have time to go through those and you need to identify that. You need to have threat hunting that's automated, where you're actually attacking your own systems automatically with agents, and so on. It hasn't happened. So I do think like if we just say, hey, this is just like the internet in the early days, you know, bad things are going to happen. So there is a race going on.

</details>

### 数据、AI 与网络安全的市场大融合

**Martin**：说实话，我其实非常惊讶。今天早上我还刚参加了一个电话会议——我觉得咱俩关系一直挺近的，经常定期交流，我也自认为对 Databricks 的产品布局相当了解。但今天早上电话里有一位初创公司创始人直截了当地对我说：“我们正在构建的所有可观测性（Observability）和智能体威胁检测，底层全部是跑在 Databricks 之上的。”坦白讲，在此之前我甚至都不知道你们居然有这方面的产品与解决方案。所以，单纯从科普和了解的角度来看，你们在智能体、AI 可观测性、安全防护与可靠性保障（Safety）这套技术体系里，到底已经深入拓展到了什么程度？

<details>
<summary>Original English</summary>

**Martin**: You know, I was actually very surprised. Earlier this morning I was on a—like I feel like you and I are pretty close, we talk periodically, I feel like I know a fair bit about Databricks. I was on a call this morning where a founder was basically like, "Yeah, listen, you know, we're doing all of this observability, agent threat detection, and we're using Databricks." I didn't even know that you had this offering, quite frankly. So, like, I mean, this is just from an education standpoint, how extensive have you gotten in the agent AI observability, security, safety thing?

</details>

**Databricks 负责人**：是的，其实我们今年还在 RSA 信息安全大会上与 Ben Horowitz 一起就这个主题发表过专题演讲。这背后的核心根源在于：数据、人工智能与网络安全正在深度融合。这两个原本独立的市场正在发生坍塌与重构，因为至少在我看来……

<details>
<summary>Original English</summary>

**Databricks Speaker**: Yeah, I mean we gave a talk this year at RSA actually with Ben Horowitz, but the issue is that data and AI is blending with cyber. These two markets are collapsing because I think at least...

</details>

**Martin**：这两个市场之所以会融合坍塌，是因为在以往的认知里，数据和 AI 是一个独立的领域——也就是过去 Databricks 这类公司所深耕的业务：企业拥有一大批数据，在上面运行 AI 和机器学习算法，这些数据科学工作完全独立存在；而另一边则是网络安全世界。网络安全的目标是监测是否有黑客企图入侵系统，或者是否有恶意分子在搞破坏，我们需要检测出这些异常。

但现在的变化是，在数据与 AI 这一侧，企业内部开始运行大量的智能体（Agents）。员工在部署智能体，这些智能体还会与其他外部智能体互相调用协作，从而产生了海量的数据、系统日志、调用轨迹以及留下的各类数字指纹。既然企业内部是由这些智能体在驱动业务，这两个世界便不可避免地愈发紧密地粘合在一起：智能体产生的所有海量数据都需要被实时分析，而处理这些数据所需的吞吐规模与计算量，相比仅仅一两年前已经暴增了数个数量级。

整个安全威胁演进的周期也发生了剧烈变化。在 2018 到 2019 年前后，从一个 CVE 漏洞被公开披露，到黑客社区真正将其武器化并用于实际攻击，通常需要两到三年的时间；到了 2022 年，这个窗口期被大幅压缩，但通常也还需要大约 8 到 9 个月的时间。

<details>
<summary>Original English</summary>

**Martin**: And the reason they're collapsing is that it used to be like, okay, we have data and AI, the kind of stuff Databricks and these kind of companies used to do, which is like, okay, you have a bunch of data and you run AI and machine learning and that lets live separately. And then you have the cyber world. Cyber world is, you know, we want to detect if bad people are trying to hack us, if bad people are doing things, we need to detect that, okay. But now on the data and AI side we have agents running internally in the company. People are having agents running, and the agents are also doing things with other people's agents, and they're producing a lot of data—logs, trails, you know, fingerprints that are being left. And so then now you have internally these agents that are doing that. So these worlds start merging more and more, which is like, okay, well, all the data that's being produced needs to be analyzed, and the scale at which you need to do that is just many, many orders of magnitude more than just one or two years ago.

So things have changed dramatically. Like 2018–19, the time it would take from a CVE vulnerability being sort of published until you see it actually be weaponized in the industry would be like two, three years. That went down to 2022 significantly, but it was still like eight, nine months.

</details>

**Databricks 负责人**：是的。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Yeah.

</details>

**Martin**：当时还有 8 到 9 个月的缓冲期，企业还有相对充裕的时间应对，那是在 2022 年。但如果你观察从 2022 年至今的加速曲线，现在漏洞从披露到被武器化基本上已经缩短到了几个小时之内。

<details>
<summary>Original English</summary>

**Martin**: So that's kind of fine, you have 8, 9 months from a vulnerability to—that was 2022. Now if you look at the curve from 2022 until now, now it's down to like basically hours.

</details>

**Databricks 负责人**：没错，窗口期基本已经被压缩到归零，漏洞一出现就会立刻被武器化。因此，你必须依赖统一的数据与 AI 平台架构，以全自动化的方式来构建防护。正因如此，我认为传统的安全市场与数据 AI 平台市场最终必将彻底合二为一。

<details>
<summary>Original English</summary>

**Databricks Speaker**: So it's down to like basically no time, like things get immediately weaponized. So you need to just do it in an automated [way] with the data and AI sort of platform approach. So these markets, I'm going to argue, are just going to collapse actually.

</details>

### 工程方案与监管分歧：AI 风险到底是工程问题还是政治问题？

**Martin**：我完全同意。这就引出了一个非常核心的问题。回到关于人类存亡级生存风险（Existential X-Risk）的争论上，感觉行业目前基本分化成了两大阵营：

一个阵营认为，这归根结底是一个工程问题，像 Databricks 这样的科技公司完全可以通过工程手段来解决……

<details>
<summary>Original English</summary>

**Martin**: I agree. So it's a very specific question. I actually think a lot of—like to pull back on the existential x-risk discussion, it feels like there's almost two camps. Yes. There's one camp which believes that this actually is an engineering problem and companies like...

</details>

**Databricks 负责人**：像 Databricks 这样的公司能够解决它，通过产品、工程方案和专业服务来攻克这些难题，作为整个产业，我们只需要踏踏实实通过技术工程去解决这个问题。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Like Databricks can solve it, and they can solve it through product and through engineering solutions and through services, and so we just as an industry need to solve that problem.

</details>

**Martin**：对。但在我看来，还存在着另一个阵营，他们坚信这在根本上不存在任何工程解决方案。他们认为必须强制放慢研发步伐，必须通过强监管来遏制，把 AI 视作类似于核武器一样的危险存在等等。

所以，这是否意味着你坚定地认为这是一个可以通过技术解决的工程问题？还是说你目前还不愿意下这样一个断言？因为退一步讲，如果这真的无解且必须全面叫停，那企业为什么还要买 Databricks 呢？干脆把所有的技术模型全关进国家实验室封存起来算了。

<details>
<summary>Original English</summary>

**Martin**: Yeah. And there's others which actually believe, it seems to me, that there is no engineering solution. You have to slow it down, you have to use regulation, it's more like a nuclear weapon, etc. So does this mean you believe it is an engineering problem or are you not quite comfortable saying that yet? Because wait, if it's a—why would even buy Databricks, man, let's just put the stuff in a national lab.

</details>

**Databricks 负责人**：只要“控制步调”（Pacing）就是唯一的解药——开个玩笑而已。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Just pace it is the only solution. Just kidding.

</details>

**Martin**：大家只要各自稍微放慢一点研发节奏，世界就太平了？对于那些不法分子和恶意黑客来说，他们的逻辑字典里从来就没有“放慢步调”这回事。我认为现实就是非黑即白：要么彻底叫停，要么用工程技术彻底解决它。

<details>
<summary>Original English</summary>

**Martin**: Everybody just pace themselves a little bit then it'll be fine. The bad guys, there is no line of inquiry ever that gets to pacing. I think it's like you pause it or you solve it.

</details>

**Databricks 负责人**：我们今天算是看明白了，Martin 极其讨厌“控制步调”（Pacing）这个词。我向你保证，以后再也不会在你面前提这个词了，好吧。

<details>
<summary>Original English</summary>

**Databricks Speaker**: What we've learned here is that Martin really hates the word pacing. I will never use that word with you ever again. Okay.

</details>

**Martin**：态度非常明确，我全记下了。看来我表现得有点抓狂了。

<details>
<summary>Original English</summary>

**Martin**: Clearly duly noted. More frustrated Mark.

</details>

**Databricks 负责人**：哈哈。回到正题：这到底是一个工程师能够搞定的工程技术问题，还是涉及更深层次的复杂问题？我认为，首先得厘清我们讨论的究竟是哪一个层面的问题。我认为外界常常把两个完全独立的议题混为一谈了。

<details>
<summary>Original English</summary>

**Databricks Speaker**: Yeah. Is it an engineering problem that can be solved by engineers or is there more to it? I actually think—which problem are we talking about? There's two separate problems that I think are being conflated.

</details>

**Martin**：是的。

<details>
<summary>Original English</summary>

**Martin**: Yeah.

</details>

**Databricks 负责人**：第一个层面，是所谓的“超级智能”（Superintelligence）问题。

<details>
<summary>Original English</summary>

**Databricks Speaker**: There is the super intelligence problem.

</details>

**Martin**：对。

<details>
<summary>Original English</summary>

**Martin**: Yeah.

</details>

**Databricks 负责人**：如你所知，我认为很大一部分关于生存风险的恐慌与讨论，都源于 Nick Bostrom 在 2014 年出版的那本《超级智能》（Superintelligence）。但如果你去仔细推敲其中的各种学术定义，就会发现许多人在讨论时根本没有建立起清晰准确的概念界定……

<details>
<summary>Original English</summary>

**Databricks Speaker**: You know, and I think a lot of this comes from Bostrom 2014 Superintelligence book. And if you look at the definitions, like I think people don't have these clear definitions...

</details>

<!-- chunk 5/10 -->

### 超级智能的定义与工程化 AI Agent 的现实分歧

**Ali Ghodsi**: 如果你读过他的书，就会发现里面关于超级智能的那些定义其实有点不可思议。所以我认为，当他提到超级智能时，他脑海中所设想的是某种人工智能——我不太清楚具体的例子是什么——比如它们能在几秒钟之内撰写出一篇包含原创、同行评审级别研究成果的完整博士学位论文，或者瞬间完成相当于人类思考上千年的心智工作量。这就是他所设想的那种无论在运行速度还是智能水平上都极其夸张的程度，比如它们能够以极快的速度学习。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...of what super... If you read his book, those definitions are kind of crazy. So I think what he had in mind when he said super intelligence is, you know, AIs that—I don't know what the examples were, something like...

</details>

**主持人**: 比如它们在几秒钟内就能写出一篇包含全新同行评审内容的完整博士论文。

<details>
<summary>Original English</summary>

**Host**: ...something like they write a whole PhD thesis with novel, peer-reviewed stuff in a couple seconds...

</details>

**Ali Ghodsi**: 并且能够瞬间完成跨越千年的思考。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...and they can do like millennia worth of thought...

</details>

**主持人**: 完全是瞬时发生的。

<details>
<summary>Original English</summary>

**Host**: ...you know, instantaneously...

</details>

**Ali Ghodsi**: 没错，这指的是极高水平的处理速度以及极高的智能层次。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...and you know, so this is like the level of, you know, how fast they are, how intelligent they are...

</details>

**主持人**: 比如它们学习的方式和速度。

<details>
<summary>Original English</summary>

**Host**: ...like they can learn.

</details>

**Ali Ghodsi**: 是的，没错。但这在量级上存在着成千上万倍的差距。问题的核心在于，这两者面临的挑战规模是完全不可同日而语的。如果真的存在那样一种终极的超级智能，我认为这仅仅是一个通过工程手段就能解决的问题吗？不，我认为如果那种情况真的发生，那确实会演变成一种非常现实的生存层面的危机（existential risk）。

当然，这也是大家目前所公认的。但现在的问题在于，很多人把那种极端设想与我们当前所拥有的 Agent 混为一谈了。我们现在的 Agent 距离那个水平还差得非常远，根本不可同日而语，目前在技术路线上也完全没有任何通向那种超级智能的迹象。

然而，我们现有的这些 Agent 已经具备了相当强大的能力，你能够利用它们做一些在整个人类历史上都从未实现过的事情。因此，我确实认为行业已经迎来了一个关键的拐点（inflection point）。有某些根本性的东西被改变了——例如在 Databricks，我们拥有非常优秀的网络安全研究人员，但我以前绝不可能说：“让我们把一万名顶尖安全研究员放进沙箱里运行一个月，让他们去完成价值一亿美元的专业薪资工作。”但现在我们完全可以做到这一点。我们只需要按下一个按钮，就能瞬间调用十万个这样的 Agent 协作工作。

再比如在数学领域，我们可以说：“我们想要去证明或者解决某个数学猜想。”那么好吧，我们可以召集一批相当优秀的数学家，但这次我们能让一万个 AI 数学家同时进行协同推演，这样一来你就能取得非常迅速的突破性进展。

因此，我认为这种能力的飞跃直接引发了当下各种严峻的网络安全风险。网络安全问题正是这里最主要的威胁所在。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah. Yeah. It's just, yeah, I mean, yeah, but it's just many, many, many orders of magnitude, right? The scale of the problem is just completely different. So if such a thing exists, do I think that's just an engineering problem to solve? No, I think that's actually... If such a thing would happen, that would be very existential.

Of course. And that's what everybody agrees on. So I think that's being mixed with now we have agents that are nowhere near that. There's nothing like that, and we don't have anything towards that path right now.

But these agents are capable, and you can do something with them that you could never do before in the history of mankind. So I do think an inflection point has happened. Something has changed, which is: we have good security researchers at Databricks, but I could never say, "Let's get 10,000 of them in a sandbox for a month and have them do hundred million dollars' worth of salary wage work." We can do that now. We just turn on a button and we can get 100,000 of them.

Or mathematics: we can say, "Hey, we want to solve a conjecture." Okay, let's get pretty good mathematicians, but let's have 10,000 of them collaborate, and then you can make very fast progress. So this leads to all these cyber risks. I think cyber is the major problem here.

</details>

**主持人**: 这类网络安全风险我认为是完全可以通过工程手段来解决和防范的。

<details>
<summary>Original English</summary>

**Host**: This is I think you can solve with engineering.

</details>

**Ali Ghodsi**: 确实如此。我们正在致力于解决这一问题，业内也有许多其他团队正在攻克这一难关。尽管风险依然客观存在，但它们并不属于毁灭人类的生存性危机，我认为我们应该积极推进这项技术。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And I think we are working on it. Many others are working on it. There's still risks; they're not existential. I think we should do it.

</details>

### 自我迭代、独立审查与监管治理机制

**主持人**: 至于超级智能那件事——也就是能够瞬间写出突破性博士论文，或者无需在纸上推导就能在直觉上直接进行11维空间物理推理的存在，这种人类完全无法企及的超级智能——核心问题在于：各大前沿实验室目前正在探索的 RSI（递归自我改进，Recursive Self-Improvement）是否真的在把我们引向那个方向？我们最终会走到那一步吗？

<details>
<summary>Original English</summary>

**Host**: There is the super intelligence thing. That's the thing that could write a novel PhD thesis or reason intuitively in 11-dimensional space physics instantaneously without writing anything down, something humans can't do. That kind of super intelligence—the question is, is RSI and recursive self-improvement that the labs are doing leading us there? Are we going to get there?

</details>

**Ali Ghodsi**: 它们正在努力尝试实现这一点。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Trying to do...

</details>

**主持人**: 它们正在努力尝试，但那真的会发生吗？如果会，发生的速度又会有多快？这才是核心的大疑问。而且这些实验室之前曾提议过：“嘿，我们应该设立外部核查员，让他们进入实验室来监督和审查我们正在进行的工作。”我认为这本身是一个很好的提议，让核查员进去获取真实的内部数据。但关键问题在于，这些核查员到底应该由谁来担任？因为核查团队的人选构成是完全可以被操纵（stack）的，对吧？

<details>
<summary>Original English</summary>

**Host**: Trying to do. Is that what's going to happen? And how fast is that going to happen? That's the big question. And they've suggested that, "Hey, we should have inspectors that come in and look at what we're doing." I think it's a good idea: have them go in there and get the data. The question is who are the inspectors, because you can stack that, right? You can stack that.

</details>

**Ali Ghodsi**: 你觉得应该由谁来担任？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Who do you think?

</details>

**主持人**: 是啊，目前在两大阵营中都有一大批候选人。其实如果真由某些特定人员担任核查员，我可能并不会太在意他们的评估结论，因为他们在进入实验室展开调查之前，脑子里往往就已经有了预设的既定立场。

<details>
<summary>Original English</summary>

**Host**: Yeah. There's a bunch of people on either camp. Actually, I wouldn't care if they're the inspectors. I would not be very impressed by what they say because they've already made up their minds even before they would go in there.

</details>

**Ali Ghodsi**: 没错，正是这样。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Right. Exactly.

</details>

**主持人**: 但我们举个例子，比如 Yann LeCun——作为深度神经网络技术的先驱和奠基人之一——如果他说：“嘿，这里根本没什么值得大惊小怪的，没有任何生存风险。”我这里是在概括他的意思，“这根本不算什么，所谓的超级智能威胁纯属无稽之谈，只管继续往前推进，全速发展就好。”

<details>
<summary>Original English</summary>

**Host**: But let's say like as an example, if Yann LeCun, who was one of the inventors of this deep neural network technology, right, one of the pioneers—if he said, "Hey, there's nothing to see here. There's no risk." You know, I'm paraphrasing him: "This is nothing. This superintelligence, this is just nonsense. Keep on going. Go fast, fast, fast."

</details>

**Ali Ghodsi**: 我们谁都不会轻易相信这种话。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: None of us would believe it.

</details>

**主持人**: 我并不是想强加观点给他。但如果他作为核查员之一进入内部进行了实地调查，出来之后对大家说：“听着，我已经彻底看过了，情况正如我之前所说，这里没有任何异常风险，大家继续推进即可。”如果他这么说，我反而会感到非常安心。

<details>
<summary>Original English</summary>

**Host**: I'm putting words in his mouth. I mean, I'm not exactly... No. If he was one of the inspectors and he went in there and he had a look, and he came out and he said, "Hey, I've looked and it's just what I said. There's nothing to see here. Just keep going," I would feel very good about that.

</details>

**Ali Ghodsi**: 对，那样确实能让人感到安心；或者反过来，如果他调查完走出来惊呼：“天哪……”如果他的坚定立场发生了动摇，并且稍微改变了自己的想法，那同样会释放出非常有价值的信号。所以归根结底，关键在于我们究竟挑选谁来担任核查员。我认为设立核查机制本身是个好主意，我们应该引入一部分核查人员，并且挑选一组背景多元化的人选，这样我们才能获得不同维度、细致入微的视角。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...that would say okay... I would feel very... Or if he comes out and says, "Oh my god," you know, he's wobbling and he would change his mind a little bit, that would also have a lot of interesting signals. So I think it comes down to who we pick as inspectors. And I think it's a good idea, let's have some of them and pick a diverse set of people so that we can get different nuanced points of view.

</details>

### 利益冲突与三方监管模式的博弈

**主持人**: 那你如何看待埃隆·马斯克（Elon Musk）所持的观点呢？目前看来业内大致存在三种方案：像 OpenAI 和 Anthropic 提倡的是引入第三方独立核查；而埃隆·马斯克的设想，据我所知，更倾向于让各大 AI 实验室之间互相交叉审查（cross-check），类似于科学界的同行评审机制；然后马克·扎克伯格（Mark Zuckerberg）的方案则是自我监督和自我规范。你怎么看待这中间的第二种方案（同行互审）？

<details>
<summary>Original English</summary>

**Host**: What do you think about this kind of Elon Musk view, which is it's less third party, it feels like there's kind of three proposals: the OpenAI/Anthropic one is a third party...

**Ali Ghodsi**: Yeah.

**Host**: The Elon Musk one, as far as I can tell, is the labs cross-check each other like peer review like you do in science.

**Ali Ghodsi**: Yeah.

**Host**: And then the Mark Zuckerberg one is police yourself, right? What do you think about this middle one?

</details>

**Ali Ghodsi**: 让他们互相制衡、互相评估吗？我觉得这就像是在拳击擂台赛上，让台上的拳手们自己来充当彼此的裁判一样。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: That they should pace each other, like evaluate each other? I think like if we have boxing matches in the ring, the boxers should just be the judges of each other.

</details>

**主持人**: 这能行得通吗？

<details>
<summary>Original English</summary>

**Host**: Would that work?

</details>

**Ali Ghodsi**: 根本行不通。他们整场比赛都会不停地大喊对方犯规：“犯规！犯规！犯规！”只要对方阵营一旦发布了一款强大的旗舰模型，另一方立刻就会大叫：“啊，这存在巨大的超级智能风险！”

他们绝对会指责对方不够负责任。当背后涉及到巨大的既得利益，甚至牵涉到各自的 IPO 上市计划时，这两家公司本身就处于极度激烈的竞争之中，彼此之间还有着复杂的恩怨历史。指望他们能公正客观地对待彼此？他们怎么可能做得到。这就是为什么你必须引入第三方独立机构的原因。试想，如果人们自己私下就能把所有利益纠纷和是非曲直解决清楚，世界上为什么还需要法官？我们为什么还需要第三方仲裁机构？当然，他们如果想尝试同行互审也可以去试，但我深表怀疑，他们必然会受到多重利益立场的偏见影响，从而无法客观地评价对方。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: No. They would scream foul all the time: "Foul, foul, foul!" The moment the other guy puts out a great model, it's like, "Ah, big super intelligence risk!"

Absolutely. Like, you know, "They have not been responsible." When vested interests are at play, and there's like IPO plans, and these two companies are so competitive and they have like this history between them—yeah, they'll be very fair to each other, I'm sure! That's why you need a third party, right? I mean, why do we have judges in the world at all? Why do we have third parties at all? Why can't people just figure things out between themselves? But I mean, they should try. If they want to do it, they should try. But I'm skeptical that they wouldn't just be biased in multiple ways to judge each other.

</details>

**主持人**: 那我必须问一下，Ali，你是否赞同马斯克在 All-In 峰会上表达过的另一种看法？他当时大概是说：“这背后其实是一场精心设计的四维空间博弈（4D chess）。因为一方面，你在不断渲染 AI 会毁灭全人类；而另一方面，你又在私下询问投资人‘你们想要认购多少我们公司的 IPO 原始股？’”这种观点可能有些愤世嫉俗，但你觉得该如何调和这种看似矛盾的说辞？这种巨大的认知失调确实让很多人感到困惑，你认为这背后的逻辑究竟该怎么理解？

<details>
<summary>Original English</summary>

**Host**: So I have to ask, Ali, do you think something Elon also said—I think it was on the All-In Summit—he was like, "This is some elaborate 4D chess, because on the one hand you're saying all of humanity will die, on the other hand you're saying, 'Hey, what do you want for your IPO allocation?'" Right? And so that is probably a more cynical view, but how do you reconcile that? The dissonance I think gets a lot of people. How do you think that gets reconciled?

</details>

**Ali Ghodsi**: 我认为所有这些因素其实都交织混杂在一起。一方面，确实有一部分人发自内心地感到恐慌；另一方面，也确实有人会觉得，如果有出台相关的行业监管政策来规范和放缓大家的发展节奏，这从商业竞争的角度来看对自己是有利的。同时，我也认为商业利益的驱动是真实存在的。

通常情况下，人们总能在大脑中找到某种方式，将所有这些看似冲突的诉求和谐地自洽起来。所以，要说过去行业内是否存在一种营销噱头的倾向——通过不断宣称“天哪，我刚训练出来的最新模型实在太强大、太不可思议了，它甚至让我感到害怕”，以此来吸引全世界的目光——是的，这种恐吓式营销策略确实一直存在。

但与此同时，正如我之前提到的，安全漏洞从被披露（CVE）到被实际武器化利用的时间窗口，在短短三四年间已经从数年缩短到了几分钟。因此网络攻击的威胁是实实在在的。所以这既是一种非常出色的市场营销手段——每当训练出新模型时就大肆宣扬它对世界构成了多么可怕的潜在风险，这确实能带来巨大的关注和收益——但同时网络层面的风险也确实确凿无疑。这两者之间或许并不真正矛盾。

你我都是搞网络技术出身的，在技术历史上，通过成立独立第三方机构来进行技术仲裁与标准制定的成功先例屡见不鲜，比如 IETF、IEEE，甚至是 ICANN……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Look, I think all of these things get mixed. I think there are people that are freaked out, and I do think that there are people saying like, "Hey, if there was regulation that would pace us—sorry to use the word—that would be good for us." Right? That would be good for us. But I also think that people have vested interests.

Right, these things... Usually people figure out a way to always get all of these things to align harmonically in their head. So yeah, do I think that there has been a tendency in the past of in general using also marketing stunts by saying, "Oh my god, this latest model is so good that I trained, it's like unbelievable, it's like almost scaring me," and then the whole world kind of starts focusing on it? Yeah, there's been that kind of marketing going on.

Yeah. But at the same time, also, as I said, the time from CVE to actually weaponized exploit has been going down from years down to like minutes now, just in like three, four years. So it's real. The cyber attacks are real. But there's also a great marketing ploy to, you know, whenever you train a new model, make lots of noise around how much of a crazy risk it is to the world. It helps you, right? So maybe they're not in contradiction, these things.

So, I mean, you and I are networking folks, and there's a long history of forming third parties to help arbitrate things, right? Like IETF, or IEEE, or even like ICANN...

</details>

**主持人**: 我明白你想表达的方向了。

<details>
<summary>Original English</summary>

**Host**: I see where this is going.

</details>

**Ali Ghodsi**: 不，不，所以我的问题在于，我认为提出这样一个第三方监督方案实际上是非常合情合理的……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: No, no, so my question to you is... I think it's actually this is a very sensible proposal that they...

</details>

<!-- chunk 6/10 -->

### 行业自律与联邦监管的博弈

**Speaker A**：我其实很赞同你的看法。你大概会希望确保评估机制是独立的，而目前的情况显然算不上完全公正。

<details>
<summary>Original English</summary>

**Speaker A**: I actually agree with you. You probably want to make sure it's independent, which is not fair right now, whatever.

</details>

**Speaker B**：而且关于到底由谁来担任评估者，必然会引发大量争议，每个人都会有不同意见。没错，但你之前也提到过，我们为什么需要法官呢？所以引入国家公权力介入，实际上跟纯粹依靠行业自律完全是两码事。那么你认为在什么样的时间节点上，真正去考虑联邦层面的介入才是合理的？还是说你觉得现在就应该考虑实质性的联邦介入，而不是仅仅依靠更多的行业自我监管？

<details>
<summary>Original English</summary>

**Speaker B**: And there's going to be a lot of arguments about who you put in charge, and everybody's going to disagree. Right, right. But you said, you know, why do we have judges? So the state stepping in is actually quite a different thing than basically industry self-policing. So at what point in time do you think it makes sense to actually consider federal involvement? Or do you think now is the time to actually consider actual federal involvement as opposed to more industry self-policing?

</details>

**Speaker A**：嗯，这两者确实有很大差异。

<details>
<summary>Original English</summary>

**Speaker A**: Well, these are very different.

</details>

**Speaker B**：它们虽然不同，但在实际运作中往往会相互渗透和交织。比如美国金融业监管局（FINRA），它并不是一个完全独立的自治机构；它名义上是自律组织，但实际上与政府监管架构紧密相连。所以我认为这两者之间是会逐渐融合渗透的。

<details>
<summary>Original English</summary>

**Speaker B**: They are different, but they kind of bleed into each other. For instance, FINRA is not like a completely independent self-regulatory body. It is, but it's linked to the government. So I think these things will kind of bleed over.

</details>

**Speaker A**：所以你认为它们的发展路径是：在历史上通常先由行业自身进行自我约束与监管，随后逐步演变成正式的官方规制？

<details>
<summary>Original English</summary>

**Speaker A**: You think that historically industry self-polices and then it evolves into regulation?

</details>

**Speaker B**：如果各家机构都在声称存在生存级风险（Existential Risk）——他们现在确实在这么说——并且还在公开呼吁“请来监管我们、规制我们”，我认为监管机构是很难直接回绝说“不，我们不管”的。尽管到目前为止监管机构还没有全面插手，但我认为这种局面维持不了太久。之前戴维·萨克斯（David Sacks）不是还说过：“我还从来没见过有哪个 CEO 会主动要求政府来监管他们。”但我最喜欢的一句话是——

<details>
<summary>Original English</summary>

**Speaker B**: If they are saying there is existential risk, which they're saying, and then saying "come police us and regulate us," I think it's very hard for regulators to say, "No, we're not going to do that." So far they've said that, but I think that's not going to last very long. But wasn't David Sacks like, "I've never had a CEO ask us to regulate them." And my favorite thing—

</details>

**Speaker A**：——而对 CEO 来说，“我也从来没见过有哪个监管机构会对监管权力的扩张说不”。

<details>
<summary>Original English</summary>

**Speaker A**: And the CEO, "I've never had a regulator that says no to that."

</details>

**Speaker B**：对，绝不会拒绝。我的意思是，现实情况是背后的元政治机器（Metapolitical Machinery）实际上早已经运转起来了，对吧？每个人都有自己的一套公开说辞与政治诉求，连奥巴马都公开发表了看法，这已经演变成一个重大的公共议题。

<details>
<summary>Original English</summary>

**Speaker B**: Say no. I mean, the reality is the actual metapolitical machinery is actually in motion already, right? I mean, everyone has a talking point. Obama has come out. It is a major issue.

</details>

### 监管窗口期与资本驱动的技术竞赛

**Speaker A**：那你是否认为存在这样一种现实可能性——现在动手已经太晚了？这可能会成为中期选举中的核心议题，随后我们将会迎来严厉粗暴的联邦行政规制，整个行业的所有研发都会被叫停；相关的监管审查会全面进驻 Anthropic，进驻美国能源部（DOE），我们其实已经错过了从容应对的时间窗口？还是说你认为我们依然有可能达成某种合理理性的行业自律与协同监管框架？毕竟面对公众舆论和媒体头条的轰炸，有些事情是很难阻挡的。

<details>
<summary>Original English</summary>

**Speaker A**: Do you think that there's a reality that it's too late? This will be a major issue in the midterms and we're actually going to get heavy-handed federal regulation and this is all going to be paused, goes into Anthropic, goes into the DOE, and we're past that point? Or do you think we can actually end up with a sensible self-policing regulation? Because with the headlines, you cannot—

</details>

**Speaker B**：我们仍然应该尽最大努力去践行正确的做法。我认为事物未来的演化路径依然存在一定的自由度与变数，我们现在依然还有时间。

<details>
<summary>Original English</summary>

**Speaker B**: We should strive towards doing the right thing. I think there's still some degrees of freedom of how things evolve and there's still time.

</details>

**Speaker A**：是的，你说得很对，目前大体上的格局就是这些公司正在不断吸纳投入成百上千亿美元的庞大资本。

<details>
<summary>Original English</summary>

**Speaker A**: And yeah, you're right that largely you have these companies where we're pumping in so many billions of dollars.

</details>

**Speaker A**：而且从强化学习（Reinforcement Learning）的运作机制来看，你给它设定一个可严格验证的奖励函数（Reward Function），比如“我们要解决这道复杂的数学题”，或者攻克编程领域中某个非常狭窄具体的专项任务，然后把海量的资金和算力灌注进去。你确实能在那个狭窄的特定领域内取得极其出色的成果，但这根本不意味着你正在获得真正的超级智能（Superintelligence）。

<details>
<summary>Original English</summary>

**Speaker A**: And the way reinforcement learning works is that you give it the reward function that's verifiable, like "we're going to solve this math problem" or this narrow area of programming and so on, and we pour in so much money into that. You can get quite good results in that narrow kind of domain; that doesn't mean that you're getting that super intelligence.

</details>

**Speaker B**：没错。甚至人们很容易陷入一种自我欺骗的错觉，误以为由于自己投入了如此多的前置思考并运行了海量的试验历程，从而在较少的新增输入下就获得了更好的输出效果。然而，在消耗了如此庞大外部资源的背景下，想要真正做一个严谨封闭的对照实验是非常极其困难的。

<details>
<summary>Original English</summary>

**Speaker B**: No, but you can even trick yourself into thinking that less inputs are giving you a better outcome just because you're running so many experiences and thought about it so much, right? But it's actually very hard to do a closed experiment this way given how many resources are going in.

</details>

**Speaker A**：确实，正印证了你的观点，目前的融资规模正在以极其惊人的天文数字不断攀升。

<details>
<summary>Original English</summary>

**Speaker A**: Well, the fundraisers are going up astronomically to your point.

</details>

**Speaker B**：是的，千真万确。这也是为什么这些头部公司纷纷选择走向公开上市（IPO）。换作平时，我认为他们更愿意继续保持私有化状态。作为一名管理着规模化私有企业的人，我认为在其他正常情况下大家都更青睐保持私有。那他们为什么非要急于公开上市呢？因为他们极度渴望巨量资本，并且他们将技术扩展定律（Scaling Laws）以及背后的资本充裕度视作核心的战略竞争壁垒。这就是他们上市的真实动因。

不过，我想让我们重新回到我之前列出的那四项关键指标。如果那四项条件真的成立了——假如那四条确实成真了，你会不会希望能提前知情？这种可能失控的前景会不会让你感到深切担忧？虽然目前还没有任何实质证据表明这四种情况正在发生，但如果事实证明技术演进确实正在朝那个方向迈进呢？

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes. And that's why these companies are going public, right? I think otherwise they would stay. I mean, as someone who runs a private company at scale, I think they would prefer to stay private otherwise. Why are they going public? Because they need the capital and they consider the scaling laws and the capital to be a strategic advantage. So that's why they're going public.

But I would say let's go back to the four things that I listed. If those four are true, would you want to know about it and would that be worrisome that that could get out of hand? Now there's no evidence that those four are happening, but if there was, that is actually where it's headed.

</details>

### 递归自我改进（RSI）与自动催化效应的本质辨析

**Speaker A**：是的，我确实认为去深入理解任何系统的自我推进或自我驱动属性都是至关重要的。我们在过去研究各类复杂动态系统时就一直在做这种探索，比如研究编译器（Compilers）自举，或者针对纳米技术（Nanotechnology）开展的全部科研探索，这类机制一直是我们共同关注的焦点。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I actually think understanding for any system any sort of self-propelling property is important, and we've done this in the past with dynamic systems, right? Like we've done this with whatever compilers, we did this with all the research on nanotechnology. It's been common interest of ours.

</details>

**Speaker B**：我也觉得对这个方向产生兴趣并不是什么新鲜事。我只是觉得——

<details>
<summary>Original English</summary>

**Speaker B**: And I don't think that that's new that it's an interest. I just think—

</details>

**Speaker A**：大家普遍的担忧在于，这些特定的人工智能系统本质上是极其复杂的元经济系统（Meta-economic Systems）。

<details>
<summary>Original English</summary>

**Speaker A**: The fear is that these particular systems are meta-economic systems that are so complex.

</details>

**Speaker B**：这种情况下真正的风险在于“狼来了”式的虚假警报——在明明没有出现真正自我进化迹象的时候大呼小叫说看到了，我认为目前行业中充斥着大量这种浮夸现象。

<details>
<summary>Original English</summary>

**Speaker B**: That the risk is crying that you're seeing it when you're not seeing it, and I think a lot of that's happening right now.

</details>

**Speaker A**：是的，但是——

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. But—

</details>

**Speaker B**：但当然，如果你真的确凿观察到了那种现象，你肯定希望第一时间搞清楚真相。

<details>
<summary>Original English</summary>

**Speaker B**: But of course if you see it, you want to know.

</details>

**Speaker A**：但客观来说，各大前沿实验室现在的确把大量精力聚焦在递归自我改进（Recursive Self-Improvement, RSI）上，这也是他们下一步的核心方向。或许他们只是陷入了某种毫无根据的自我恐慌之中，就像他们当年对 GPT-2 表现出的过度焦虑一样。

<details>
<summary>Original English</summary>

**Speaker A**: But it is fair to say that the labs are now focusing a lot on RSI and that's where they're headed next. And maybe they're just unjustifiably worried themselves just like they were worried about GPT-2.

</details>

**Speaker B**：对吧？当年他们到处宣扬 GPT-2 会毁灭世界，结果事实证明并没有，随后 GPT-3 和 GPT-4 也顺利发布了。

<details>
<summary>Original English</summary>

**Speaker B**: Right? Like they were like GPT-2 is world ending and then it wasn't, and GPT-3 and 4 came out.

</details>

**Speaker A**：所以，我不想在字眼上做无谓的争辩。很多时候当他们口口声声谈论 RSI 时，他们实际所指的只不过是“自动催化效应”（Autocatalytic Effects）。而自动催化效应在我们整个计算工业界已经存在了极其漫长的时间。举个最典型的例子：你根本不可能在没有计算机芯片的前提下去凭空制造出一枚新的计算机芯片，现实中你绝对做不到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: So I don't want to quibble. A lot of the times when they say RSI, they're actually talking about autocatalytic effects, and autocatalytic effects have been in our industry for a very, very long time. So, for example, there's no way you can create a computer chip without a computer chip. You just cannot do it.

</details>

**Speaker B**：任何计算机专业的学生都知道，编译器最经典的能力就是编译它自己的源码。

<details>
<summary>Original English</summary>

**Speaker B**: Anyone with a computer science degree knows a compiler writes its own compiler.

</details>

**Speaker A**：对，编译器自编译确实更接近狭义上的 RSI；但其实像蒸汽机的发展也是自动催化的过程，对吧？听我说，我的全职工作就是天天接触从顶级实验室出来创业的人，他们每个人都张口闭口谈论 RSI，仅仅因为全行业都在炒作 RSI 这个热词。但其中可能只有区区 1% 的团队在做真正意义上的 RSI。绝大多数人所谓的 RSI，本质上只是“我们利用 AI 工具来做数据清洗”、“我们用 AI 辅助生成代码”这一类流程。

<details>
<summary>Original English</summary>

**Speaker A**: Well, that becomes closer to RSI. But like the steam engine was autocatalytic, right? So listen, my full-time job is people coming out of labs and starting companies, and they all say RSI because everybody says RSI. And maybe 1% of those are actually RSI. They're more like, "we use AI for data cleaning, we use AI for code generation."

</details>

**Speaker B**：让我们把界限划分清楚。所以你的意思是，他们所做的在本质上只是催化剂层面的工作，即通过 AI 工具来加速工程与研发流程？

<details>
<summary>Original English</summary>

**Speaker B**: Let's make the distinction. So you're saying it's basically catalyst in a sense that they're using AI to speed things up.

</details>

**Speaker A**：对，这就是自动催化。所以我想说明的是——

<details>
<summary>Original English</summary>

**Speaker A**: It's autocatalytic. Yes. So I would say—

</details>

**Speaker B**：这就是我们听到的用一个模型辅助构建另一个模型的过程，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Of what we hear, using another model, right?

</details>

**Speaker A**：你用一个 AI 模型来编写和优化底层 GPU 内核算子，或者用模型来执行自动化数据清洗，这完全就像我用现有的电脑来辅助设计下一代电脑一样。这就是自动催化属性，事实上每一项突破性技术都具备这种特性——互联网本身就是自动催化的，因为它让全球的人们能够跨越空间远程协同工作。

<details>
<summary>Original English</summary>

**Speaker A**: You're using a model to build a GPU kernel. You're using a model to do data cleaning, just like I use a computer to design a computer. It's autocatalytic, which is true of every technology. The internet was autocatalytic because it allowed people to collaborate remotely.

</details>

**Speaker B**：从经验来看，目前行业里 90% 以上的精力和算力开销都花在这些自动催化式的工程提效上，这完全符合正常的技术演进预期。

<details>
<summary>Original English</summary>

**Speaker B**: This is anecdotal: 90% of the calories are autocatalytic, which is 100% what you would expect.

</details>

**Speaker A**：而且这种模式已经持续存在很长时间了，根本算不上新鲜事物。但我必须指出，现在的确开始出现一股新趋势，大家正把研究重心转向真正的自我迭代——我们是否能够让模型完全自主地训练自身？这有点类似于安德烈·卡帕西（Andrej Karpathy）之前尝试的自动化研究探索，但现在的团队希望能把这个方向推向极致。

<details>
<summary>Original English</summary>

**Speaker A**: And that's been going on for a while, though; that's not even new. But I would say now there is a focus on: let's move towards actually can we get the model to train itself? This kind of like the auto-research that Karpathy did, but now they want to do that.

</details>

### 通用人工智能（AGI）的炒作与企业真实落地现状

**Speaker B**：确实有团队正在从事这方面的探索，但这部分研究所消耗的实际资源和算力，远没有大家想象的那么庞大。我觉得自己对整个行业的实际现状有着非常充分且真实的样本感知，因为几乎所有创业者和技术团队都会来跟我们交流。

<details>
<summary>Original English</summary>

**Speaker B**: There are teams that do that. It is not nearly as many calories as you would expect, and I just feel like I actually have a good sampling of this because they all come and talk to us.

</details>

**Speaker A**：既然如此，或许你可以作为独立审查员之一去调取并核查这些实际数据，让我们大家都能看清楚底层数据的真相。也许最终会发现这里根本没有什么值得大惊小怪的重大隐患。我个人其实也不认为前面提到的那四项极端危险判定标准有很高的发生概率。

<details>
<summary>Original English</summary>

**Speaker A**: Right, so maybe you can be one of the inspectors. Can we get all that data and all of us look at that data? Maybe there's nothing to see here. I personally don't think it's very high probability that those four criteria are happening.

</details>

**Speaker B**：格雷格·布罗克曼（Greg Brockman）本周刚上了播客节目，并且公开宣称我们已经正式迈入了通用人工智能（AGI）时代。

<details>
<summary>Original English</summary>

**Speaker B**: Brockman went on the podcast this week and said we're at the AGI era.

</details>

**Speaker A**：对啊，在他发表了那番言论之后，我也向同行们问了同样的问题，现在几乎每个人都在人云亦云地说我们已经实现了 AGI。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so now I asked the same question after he said that, and now everybody's saying we have AGI.

</details>

**Speaker B**：所以你看，大众总是盲目跟风这些宏大叙事。但是长期以来，每当我向业内人士提出这个问题时，他们都会信誓旦旦地宣称“AI 在绝大多数时间里都比我身边的绝大多数人要聪明”。这种说法差不多从去年第三、第四季度开始就屡见不鲜了。

可是紧接着我进一步质问他们：“在座的各位当中，有谁真正部署并管理着数百甚至数千个自主智能体（Agents）？这些智能体是否真正形成了能够彼此协同配合的蜂群集群网络（Agent Swarms），能够自主磋商谈判，并全方位自动化接管你的日常生活以及周遭的所有业务？”当我让他们“如果是的话请举手”时，现场几乎没有一个人举手。当然，马丁（Martine）在家里确实自己搭建了一套类似系统。

<details>
<summary>Original English</summary>

**Speaker B**: People follow this narrative. But for a very long time, when I asked this question, people said that AI is smarter than most other people around me most of the time. That's been happening almost since Q3/Q4 last year.

Then I asked them: "How many of you are managing hundreds or thousands of agents that are coordinating with each other in swarms and negotiating, and automating your life and everything around you? If so, raise your hand." Almost nobody raises their hand. Of course, Martine has done that at home, you know.

</details>

**Speaker A**：完全没有，现实中绝大多数企业目前仅仅是用上了微软的 Microsoft Copilot 而已。

<details>
<summary>Original English</summary>

**Speaker A**: No, most enterprises are on Microsoft Copilot, yeah.

</details>

**Speaker B**：对，这基本就是绝大多数企业应用 AI 的最高上限了。

<details>
<summary>Original English</summary>

**Speaker B**: Like that's the extent of their AI.

</details>

**Speaker A**：从我所调研和交流过的大多数企业实际情况来看，每当我问起自动化智能体网络时，他们都会回答：“不，我们根本没有部署任何那种前沿技术。”当我们追问“那你们到底在用 AI 做什么”时，他们其实仅仅是在使用基础的问答聊天机器人（Chatbot）——向聊天机器人提出各种问题。而这种聊天机器人的本质，不过是对传统谷歌搜索结果进行了一层极其华丽而高效的包装聚合，其核心价值无非是让获取信息的速度变得更快了一点而已。

<details>
<summary>Original English</summary>

**Speaker A**: From what I've seen, most enterprises I talked to, when I asked this question, they're like, "No, we don't have any of that." So we're like, "What are you doing then?" They're using a chatbot. They're asking questions from a chatbot that's basically a very, very glorified efficient Google search of the old day results, so it's just faster.

</details>

<!-- chunk 7/10 -->

### 企业 AI 落地的瓶颈：上下文缺失而非模型智商

**Ali Ghodsi**：……Google 搜索。接着是编程领域，人们确实在用 AI 写代码。虽然我们可以探讨编程上的投资回报率（ROI），但目前并没有出现那种能将整个企业完全自动化的智能体式（agentic）工作流，这种情况根本还没有发生。

那么原因究竟是什么？我认为，如果你客观审视就会发现，模型本身的智能已经足够了。但它们唯独缺乏任何组织内部都天然具备的“上下文”（Context）。比如，模型没有参加过每一次会议，不知道每个人脑子里在想什么，不清楚所有的业务流程。在每个组织中，总有那么几个无所不知的员工，大家经常走过去拍拍他们的肩膀请教问题，私下里大家甚至会感叹：“天哪，要是他（她）离职了该怎么办？”AI 模型缺乏的就是这种上下文。

如果能将这些组织上下文融合并赋予 AI 模型——哪怕仅使用当前的前沿模型——我认为就能为全球任何企业带来巨大的生产力提升。要做到这一点，我们实际上不需要更聪明的模型。我们不需要一个能解决纳维-斯托克斯方程（Navier-Stokes）、攻克数学猜想，或者在“人类终极考试”上从 60% 提升到 70% 的更强模型，这些完全不需要。

所以我觉得，现在很多人在为“我们要不要放慢前沿模型研发步伐”而焦虑，但事实上，即使前沿模型不再继续推进……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ... Google search. And then coding is happening, so people are using it for coding, though we can discuss the ROI there. But there is no agentic work that has automated the whole enterprise; that has just not happened.

So then why is that? I think that the real reason, if you actually look at it, is the models are smart enough, but they just don't have the context that exists inside of any organization. Like, they have not been in every meeting. They don't know what's in everybody's heads. They don't know all the processes. There's always a couple of employees who know everything in every organization. You go tap on their shoulder, and everybody's like, "Oh my god, what would happen if he or she quits?" They don't have that context.

And if you just fused that and gave that context into AI models—just a frontier model today—I think there's so much productivity gains you could get for any organization on the planet. For that, we actually don't need smarter models. So we don't need a smarter model that can actually solve Navier-Stokes or conjectures, or do better on humanity's last exam, like needing to go from 60% to 70%. None of that is needed.

So I think actually people are very upset on like, "Oh, if we pace the frontier..." But actually, if the frontier doesn't advance...

</details>

**主持人**：……其实并不会产生太大影响。对于全球绝大多数企业来说，它们在实际应用自动化并从中获取价值的采纳曲线上，还远远落后。不过，这对前沿 AI 实验室来说将是灾难性的，因为算力与智能的价格正在渐进式暴跌，几乎每六个月就会下降到原来的十分之一左右。因此，如果不继续推进前沿……

<details>
<summary>Original English</summary>

**Host**: ...it doesn't actually matter. I think for the vast majority of organizations on the planet, they're just so far behind in the adoption curve of actually automating things and getting value out of this stuff. But it would be disastrous to the labs, because the price of intelligence is dropping asymptotically—I think it's going down by one-tenth every six months or something like that. So that would dramatically change their businesses if...

</details>

**Ali Ghodsi**：……如果不继续推向前沿的话，商业模式就会彻底颠覆。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...you weren't pushing the frontier.

</details>

**主持人**：是的。但这才是我们应该聚焦的核心，对吧？我们应该关注价值产出。我们经常讨论成本和风险，任何事情都应该做成本效益分析。我们之前在这里聊了很多代价，比如是否存在人类存亡级别的威胁、网络安全风险，以及各种让人担忧的隐患，这些都属于“成本端”。但“收益端”呢？现在 AI 已经进入大众视野，全社会都在关注，大家都在问：“这对我有什么好处？我能从中得到什么？”而大众目前感觉似乎什么都没得到。

<details>
<summary>Original English</summary>

**Host**: Yeah. But this is what we should focus on, right? We should focus on—there's two sides, and we discuss the costs a lot here, right? There's cost-benefit analysis that we should do on everything. We've discussed the costs a lot here: Is there an existential threat? Is there cyber risk? Are there things we should be worried about, and so on? That's the cost side. What's the benefit? And I think now that this has become a public thing and the whole public cares about AI, they're asking, "Hey, what's in it for me? What am I getting out of it?" Seems nothing.

</details>

### AI 的实际价值：从挽救生命到加速新药研发

**主持人**：那么企业该如何实现这些价值？在您迄今见过的实际应用案例中，有哪些带来了超乎预期的惊喜？

<details>
<summary>Original English</summary>

**Host**: So, how do they get there? What are some of the use cases you've seen to date that have maybe surprised you to the upside?

</details>

**Ali Ghodsi**：是的。首先，外界对生存危机等风险有太多的担忧，以至于很多人根本不了解那些正在切实创造价值的精彩应用。我们手头有非常多令人惊叹的真实案例。

其中我很喜欢的一个是 Crisis Text Line（危机短信热线）。他们与我们合作，利用大语言模型来识别青少年是否有自残或自杀倾向。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I mean, first of all, there's so much worry about existential risk and so on, so I think a lot of people just don't know cool use cases where people are actually doing interesting things. We have a lot of use cases that are just fascinating.

One that I like is Crisis Text Line. They actually use large language models with us to detect if teenagers want to do self-harm or suicide.

</details>

**主持人**：哇，这太震撼了。

<details>
<summary>Original English</summary>

**Host**: Oh, wow. Yeah.

</details>

**Ali Ghodsi**：这是一个极佳的应用场景，它在真真切切地挽救生命。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: You know, that's an awesome use case, and it actually saves lives.

</details>

**Ali Ghodsi**：那是一家非常了不起的机构，正在做着伟大的工作。

另一个非常有趣的案例是面向糖尿病患者的 Omnipod（无管路胰岛素泵）。患者可以佩戴 Omnipod，它通过 AI 实时学习患者的胰岛素释放规律和血糖水平，从而精准控制注射。不知道你是否还记得，过去患者必须频繁……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So that's a great company, and that organization is doing amazing work.

Another one that's kind of interesting is the Omnipod, which is for diabetes patients. They can put the Omnipod, and it uses AI to really learn your insulin release and your glucose levels and actually exactly release. I don't know if you remember, people used to like...

</details>

**主持人**：……自己扎针采血测糖，对吧？

<details>
<summary>Original English</summary>

**Host**: ...stick themselves, right?

</details>

**Ali Ghodsi**：对，而现在这一切都是全自动完成的，就像是一个针对你身体进行自我学习的 AI 系统，非常酷。

再比如 Zipline，他们的业务同样令人赞叹。他们最初起步时使用完全自动化的无人机，全部由 AI 驱动——从电池优化到航线规划等方方面面——在急需物资的地区运送食物。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Um, but this now happens automatically, and it's like self-learned AI for your body. It's a cool use case.

Zipline is another one. They're doing awesome. When they started, it was like these drones that were completely automated, all AI-driven—everything from the battery optimization to the routes and everything—and they were delivering food in areas of need.

</details>

**主持人**：是的，还为难民运送血液制品。

<details>
<summary>Original English</summary>

**Host**: Yeah. Blood to refugees.

</details>

**Ali Ghodsi**：向难民运送血液制品。从非洲起步，随后扩展到全球其他地区。这都是构建在 Databricks 之上的 AI 实际应用，非常振奋人心。

除此之外，还有一些更前沿的案例。比如一个我很喜欢但解释起来稍显硬核的项目：我们与默克（Merck）联合构建的一个基于 Transformer 的模型，名为 TEDD（Transformer-Enhanced Drug Discovery，Transformer 增强型药物研发）。他们已经公开发表了这项研究成果，大家可以去查阅。

简而言之，这个模型不再是预测英语文本中的下一个 Token，而是预测基因调控网络（DRN）将如何产生响应。它能够精准识别出哪些细胞是引发病变的原因（因果性），哪些细胞只是伴随反应（反应性）。这样一来，他们就可以将其应用于新药研发，大幅降低针对特定疾病开发靶向药的研发成本。这是一个超级前沿的落地案例。

类似的案例还有很多，比如我之前提到的 Genie。通过构建企业本体（Ontology），你可以随时向它提出任何业务问题。诺和诺德（Novo Nordisk）就在使用这项技术。大家都知道他们研发了知名的 GLP-1 药物，而现在诺和诺德正将这套系统应用在他们开展的所有临床试验中。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Blood to refugees, yeah. Started in Africa and then elsewhere in the world. So that's an AI use case built on Databricks. That's a cool one.

But there's more advanced ones also. One that I kind of like, but it's harder to explain, is this transformer-based model that we built with Merck. It's called TEDD—Transformer Enhanced Drug Discovery is the name. And they published the research, so you can check it out.

Basically, instead of predicting the next token in English, it predicts what the gene regulatory network (the DRN) is going to respond with, and it can really detect which cells are causal and which ones are just reactive. Therefore, they can start using this in drug discovery and get costs down significantly for developing drugs that are targeting specific diseases. So that's a super cool use case.

There are lots of these. Genie, which I mentioned—you have this ontology, and you can ask any questions. Novo Nordisk is using this. They built this GLP-1 drug, but what Novo is doing is now they're using it for all of their trials that they're running.

</details>

**主持人**：哇，太厉害了。

<details>
<summary>Original English</summary>

**Host**: Oh, wow.

</details>

**Ali Ghodsi**：例如在进行肥胖症研究时，获取业务洞察所需的时间能够从过去的数周直接压缩到几分钟。

所以，AI 拥有大量令人惊叹的实际应用场景。我们绝不能忽视这些巨大的积极效益，我们渴望这些价值落地，而不是去人为阻碍它们的发展。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And it can compress the time it takes to get insights versus if you're doing an obesity study or something, from weeks down to minutes.

So there are a lot of amazing use cases of AI. We should not forget these upsides also. We want all of these, and we do not want to pace these.

</details>

### 构建企业本体（Ontology）：沉淀组织隐性知识

**主持人**：确实如此，完全同意。如果展望未来 12 个月，企业到底该如何真正获取这些价值？你刚才提到了“上下文”，但企业在实操中究竟该如何落地？

<details>
<summary>Original English</summary>

**Host**: Yeah, exactly. You're totally right. And so how do they—let's say if you map out the next 12 months—how do the enterprises actually get value? You dropped the word context, but how do they operationalize that?

</details>

**Ali Ghodsi**：这其实比大多数人想象的要困难得多。首要任务是必须确保将组织内部发生的一切全面数字化。你不可能挥动魔法棒就凭空实现这一点。所有的会议都必须转录……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: It's actually harder than most people believe. But first and foremost, we have to make sure that we have digitized everything that's happening in an organization. You cannot actually just have a magic wand and make that happen. So every meeting has to be transcribed...

</details>

**Ali Ghodsi**：……你必须能够捕获所有会议的全部上下文以及正在发生的所有事情，所有数字化内容都必须输入给 AI。因此你需要构建我们所谓的“本体”（Ontology）。我们 Databricks 会帮助构建这个本体，但第一步也是最关键的一步是采集这些数据。这在许多企业本身就是一个难题，因为法务团队会提出合规要求：“不要录制每一次通话，不要把所有事情都记录下来。”因此你必须找到一种合规且可行的方式去推进……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...you have to be able to get all the context of all the meetings and everything that's happening. All the digital content has to be fed to the AI. So you have to build—we call it an ontology. We build that, but first and foremost, you have to collect that. That itself is a problem in many organizations because legal teams will say, "Don't record every call, don't record everything." So you have to do that in a way where...

</details>

**主持人**：你能为听众通俗地定义一下什么是“本体”（Ontology）吗？我知道 Palantir 经常把这个词挂在嘴边，但这并不是他们的专属词汇。“本体”到底意味着什么？大家该如何去理解它？

<details>
<summary>Original English</summary>

**Host**: Can you define ontology for everyone? Because I know Palantir says the word a lot, but it's not like they own the word. What does that mean, and for the people listening, how should they understand it?

</details>

**Ali Ghodsi**：在企业语境下，“本体”指的就是组织内部所有抽象概念之间的关联网络——包括所有战略目标、各个业务部门、所有员工以及正在推进的全部项目之间的确切定义与相互关系，涵盖人员、资源与公司实际业务之间的全貌。

这就好比一个今天刚入职的新员工，和一个在公司工作了五年的老员工之间的区别。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I mean, ontology just means that in an organization, the relationship between all the abstract concepts of all the goals, all the departments, all the people, and all the projects that are going on—what do they exactly mean, and what's the relationship between them: the people, the resources, and what that company does.

So it's the difference between a person who is a new employee in the company and just started today, and a person that has worked there five years.

</details>

**主持人**：假设他们两人的专业技能完全相当，拥有相同的教育背景，同样聪明、勤奋，各方面条件都一样。但一位是今天第一天上班，另一位已经在这里工作了五年。

<details>
<summary>Original English</summary>

**Host**: Let's say they're equally skilled. They have the same educational background. They're equally smart and hardworking and all of that. But one, her first day is today at work; the other one, she's been there 5 years.

</details>

**Ali Ghodsi**：这两名员工之间的本质区别究竟是什么？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: What's the difference between these two people?

</details>

**Ali Ghodsi**：那位老员工脑海中拥有整套关于这家组织如何运转的“本体”：她知道关键人物是谁、事情怎样才能办成。她明白千万别只看正式的组织架构图，别去找那个人签字，因为找他根本办不成事；你应该去找这个人……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: The one has an ontology of how that organization works, who the people are, how you get stuff done. Don't look at the org chart. Don't go ask that person—he will not get anything done. You go ask this person...

</details>

**Ali Ghodsi**：……因为找这个人才能把事情真正搞定。她知道流程上的潜规则：“那份表格其实没必要填”、“这个项目目前的核心状况是这样，这才是最关键的”。所以，组织内部存在大量沉淀在每个人大脑中的隐性知识，他们深谙组织究竟是如何协同运作的。这也是为什么在创业圈大家常说：“如果核心团队流失了大半……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...he'll get it done for you. And "That's not how it works; you don't need to file that paperwork here," and "This is this project, this is what's going on, this is essential." So there's just a lot of ingrained knowledge that's sitting in everybody's heads who knows how an organization works. That's why people say in startup land, "Hey, if you lose most of your people..."

</details>

<!-- chunk 8/10 -->

### 企业本体与离线索引：构建 AI 驱动的企业知识图谱

**Ali Ghodsi**：那家公司根本无法从中恢复过来。你不可能随便招募新人就能填补这个空缺，因为那些员工和他们掌握的知识是如此不可或缺。那么，我们该如何提取出这种上下文——也就是企业的“本体”（Ontology）——并将其提供给 AI 呢？其中一部分工作在于，我们必须对所有沟通和记录进行归档等等；但第二部分关键在于，你究竟如何将这些纷繁复杂的上下文真正提炼成一个图谱。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: That company can't recover from it. You can't just replenish and hire new people, like the people are so essential. How do we get that context, that's the ontology, and give it to the AI? Part of that is we just have to have, you know, the recording and all of that, but the second part is how do you actually distill it down into a graph...

</details>

**Host**：也就是提炼成一个数字图谱，然后你可以把它喂给 AI。

<details>
<summary>Original English</summary>

**Host**: ...actually a digital graph, that you can then feed to the AI.

</details>

**Ali Ghodsi**：是的。你看如今许多智能体（Agents）的工作机制，比如 Claude Code 或者任何现有的智能体系统，像是 Codex、Pi，或者是 OpenCode，乃至市面上一整套类似的产品。它们都有一个所谓的“智能体循环”（Agentic Loop）。它具备推理能力，但随后它必须逐一去查询每一个外部资源。比如为了回答你的问题，它会访问某个 MCP（Model Context Protocol）服务器，试图查看答案是否在那里；如果不在，再去查询另一个资源。最后它将这些信息合成并给出答案，但这种方式是非常缓慢低效的。

我把这种情况比作：如果 25 年前 Google 也是以这种方式来构建 Google 搜索的话，那会发生什么？当时我们可能会说：“好的，我们要检索出 10 个蓝色链接。我们在搜索框输入关键词。”但系统并没有立即返回 10 个蓝色链接，而是先跳转到一个网站，用大语言模型总结那个网站是做什么的，在页面中找到几个超链接，再并行跳转到其中几个网页，阅读那几个网站的内容，这样持续运行 10 分钟，最后才为你提供它能找到的最佳 10 个蓝色链接。

首先，这种做法极其昂贵，每次你在网上搜索都要耗费巨额的算力与资金；其次，它耗时过长，用户每次搜索都得苦等 10 分钟；第三，检索质量依然会很糟糕，因为你实际上只检索了全网浩瀚数据中极小的一个子集，对吧？

那么 Google 是如何解决这个问题的呢？他们建立了索引。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So the way a lot of the agents work today, like Claude Code or any of them, Codex or Pi or, you know, OpenCode, or you can go through the whole slew of them, you know, they have this loop, agentic loop. It can reason, but then it goes and checks every resource one at a time. So it'll go to this MCP server for your question and try to see is the answer here, is there another one? It synthesizes it and gives you an answer, but it's kind of slow.

I liken this to if Google would have built Google Search this way 25 years ago. We would have said, "Okay, we're going to get 10 blue links. We search for key terms here," but instead of giving you 10 blue links, it would have gone to one website, summarized with an LLM what it does, found a few hyperlinks, jumped in parallel to a few of them, read a few websites, done that for 10 minutes, and then given you like its best 10 blue links it would find.

Well, that would be very expensive, cost a lot of money to do that every time you go on the web. Two, it would have taken a long time—you've got to wait 10 minutes. And three, the quality would be bad because you're actually only looking at a very small subset of everything that exists out there, right? So how do they do it? They have an index.

</details>

**Host**：没错，用户的请求根本不需要离开 Google 的服务器。你在搜索框发起查询，它直接命中索引，倒排索引（Inverted Index）能在不到 100 毫秒的时间内迅速为你返回那 10 个蓝色链接。

<details>
<summary>Original English</summary>

**Host**: Right? You never leave Google servers. You search for it, it hits the index, the reverse index immediately gets you the 10 blue links within, you know, less than 100 milliseconds.

</details>

**Ali Ghodsi**：我们必须为 AI 建立完全相同的机制。因此，企业本体的核心就在于我们必须全天候、在离线状态下预先计算好这个索引。这非常类似于 Google 当年发明的 PageRank 算法，但企业场景下的计算要复杂得多。因为 Google 面对的只是一个所有人都能公开访问的万维网，而企业内部则涉及严格的权限控制。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: We need to do the same thing for the AI. So the ontology is that we need to compute that index offline all the time. So it's almost like the PageRank algorithm that Google had invented back in the day, but it's more complicated because Google was just looking at a web where everybody can go on the web. Here there are permissions...

</details>

**Host**：而且当时的网页之间本来就存在现成的超链接……

<details>
<summary>Original English</summary>

**Host**: ...and the links existed, and...

</details>

**Ali Ghodsi**：是的，在企业内部存在复杂的权限机制。我被允许访问的数据，可能并不是你被允许访问的数据。因此这里涉及隐私安全和访问控制（Access Control）。此外，我们在这里处理的对象类型繁多，绝不仅仅是普通的网页。

所以，这个问题的工程难度要大得多。但它是完全可解、可掌控的，你完全有能力把它做出来。我坚信企业可以实现这一点，并从中获得巨大的生产力飞跃，因为我们 Databricks 已经在自身内部完全落地了这一体系。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, here there's permissions involved. The data I'm allowed to access might not be the data that you're allowed to access. So there's privacy, there's access control. Also there's many different types of objects here that we're dealing with, not just websites.

So the problem is a little bit harder, but it's manageable. You can actually do it. So, you know, I'm convinced you can do this and you can get massive productivity gains out of it because we did it for Databricks.

</details>

**Host**：确实如此。

<details>
<summary>Original English</summary>

**Host**: Yeah, exactly.

</details>

**Ali Ghodsi**：我们把这套体系应用到了我们自己身上。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: We did it for ourselves.

</details>

**Host**：是的。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah.

</details>

### Databricks 内部实践：本体图谱重塑组织运作与决策流程

**Ali Ghodsi**：没错。我们整个公司因为这套体系发生了彻底的蜕变。比起大约一年前的状态，现在的运作方式已经完全不同了。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah. And the company's just completely changed. It's like not the way it was I would say a year ago because of this.

</details>

**Host**：我的意思是，Databricks 一直都在对自己的产品进行深度的“吃自家狗粮”（Dogfooding），但你能否详细讲讲，作为一家组织，你们具体看到了怎样的实际影响？

<details>
<summary>Original English</summary>

**Host**: I mean you've been dogfooding Databricks for Databricks forever, but maybe say more about the impact you've seen as an organization.

</details>

**Ali Ghodsi**：好的。当我们构建出这套本体并开始基于它运转之后，我们自身拥有的本体规模可能比我们所有的客户都要庞大。在我们所有的客户利用我们的平台构建本体时，Databricks 自身本体图谱的体量比他们任何一家都要大，因为 Databricks 使用 Databricks 产品的深度和频次超过了世界上任何其他公司。在我们构建的本体图谱中，包含了数以千万计的节点。

让我们看看传统组织内部通常是如何运转的：组织通常呈树状层级结构，信息沿着树状层级自上而下或自下而上流动。比如当基层无法做出决策时，就会将问题逐级向上汇报，希望上级领导能出面定夺或打破僵局；信息一层层往上汇报时，管理层必须重新去了解前因后果、熟悉现状、获取全部上下文背景，随后才能做出决策；而一旦决策制定完成，管理层又必须将决策信息一层层向下传达渗透到整个组织中。

如果你拥有了企业本体，这整个流程中的绝大部分工作现在都可以直接由 AI 来承担。为什么这么说？

你想想在日常会议中通常会发生什么：在会议上，大家会讨论某项业务分析。通常是某个聪明人利用 Excel 建立了财务或业务模型，分析了大量数据指标，制作了一份包含精美图表的 PowerPoint 演示文稿并在会上展示。现在，这类分析工作大部分都可以直接交由 AI 来完成。

AI 可以直接为你完成全套数据分析，因为它已经掌握了企业全部的上下文背景。它能以你期望的方式呈现数据结果。你可以直接就数据向 AI 追问细节，而不再需要组织一轮又一轮的后续跟进会议。你可以直接向 AI 提出疑问并即时获得解答。

这与 Jack Dorsey 此前谈到的对组织结构的改造理念非常相似。我们所做的，就是提供了一种切实可行的具体实现途径。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I mean once we got this ontology and we started working on it, and we actually have probably the largest of all of our customers—we have the largest ontology. Our ontology is bigger on us than any of our customers when they use, you know, us to build their ontology, because Databricks uses Databricks more than anyone else uses Databricks. And so it's like millions of millions of nodes in the graph, in the ontology graph that we have.

So it's just, you know, what happens in an organization? In an organization you have a tree structure organization, and information flows up and down the tree structure. You know, if you can't make a decision, you escalate to your boss, maybe they can tie break it. It escalates up, they need to get up to speed on what's happening, and they need to get all the context, and then they make decisions. Once decisions get made, you have to percolate them down in the organization.

A lot of this can now be done by AI if you have an ontology. Why? Because, you know, what happens in a meeting? In a meeting you go through some—you know, someone has done the analysis. They probably have a PowerPoint deck with some pretty graphs in it. That person that did the analysis is some smart person that used Excel, made some models, there's some numericals.

So a lot of that you can now just do with AI. So the AI can do the analysis for you. It has all the context. It can present it in a way that you want. You can ask questions about it instead of having follow-up meetings. You can directly ask questions directly from the AI.

So it's very similar. It's along the lines of what Jack Dorsey has said that you can do to the organization. It's just a concrete way of implementing it.

</details>

**Host**：明白。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Ali Ghodsi**：所以这对我们来说是一个彻底的颠覆性变革（Game Changer）。现在开会时，所有人都在手机上打开 Genie，向 Genie 提问。你会发现，只要会议中有人提到某个复杂的数据或议题，大家的第一反应全都是立刻低头看手机查 Genie。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So it's a game changer for us. Like, you know, everybody's on their phones now in the meetings on Genie, and they're like asking Genie questions. You can see as soon as someone says something complicated or something like, you know, you see everybody go to the phone.

</details>

### “让 Genie 查一下”：从销售运营到董事会的日常变革

**Host**：你能分享一下你曾经在董事会上提到的那个关于财务的趣事吗？

<details>
<summary>Original English</summary>

**Host**: Can you share that finance the—like the finance anecdote you mentioned once in a board meeting?

</details>

**Ali Ghodsi**：哈哈，当然可以，那是我们内部董事会上的事。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, it's uh, yeah sure, internal board meeting.

</details>

**Host**：只分享合规允许公开的部分就行。

<details>
<summary>Original English</summary>

**Host**: Only what's kosher.

</details>

**Ali Ghodsi**：哈哈，没问题。当时我们准备一份汇报演示材料，我需要了解我们在《财富》500 强企业中的客户数量到底有多少。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, exactly. No, it's uh actually needed for, uh, for one of our presentations. I need to know how many customers do we have in Fortune 500...

</details>

**Host**：也就是我们在《财富》500 强企业中的市场渗透率是多少。

<details>
<summary>Original English</summary>

**Host**: ...that use—what's our penetration of Fortune 500?

</details>

**Ali Ghodsi**：对。于是我发信息问了销售运营（Sales Ops）团队的一位员工，因为我以为她手头会有现成的统计数据。结果她回复我发短信说：“抱歉，我现在在飞机上，没法登录 Genie 查数据。”

我当时就跟她说：“如果你也只是打算登录 Genie 去查，那我完全可以自己查啊！我之所以问你，是因为我以为你掌握了某种我没有权限访问的其他特殊数据源。”

当时我心里有点哭笑不得，还有点小郁闷，于是我转而给我们的首席财务官（CFO）Dave 发了短信。我发信息问 Dave：“嗨，你知道我们在《财富》500 强里的渗透率是多少吗？”结果 Dave 直接给我回了一张 Genie 查询结果的截图。

原来连 CFO 也是直接去问 Genie 的！于是我当时就感慨：“现在公司里还有人在做哪怕一点点传统的原创性查询工作吗？怎么所有人全都是跑到 Genie 那里，向企业本体提问获取答案。”

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And I asked one of the people in sales ops cuz I thought she would have it, and she texted me back and said, "Oh sorry, I can't log in to Genie right now, I'm on a flight."

And I said, "If you're just going to log into Genie, I can do that myself. Like I asked you because I thought you had like something alternative that I don't have access to."

So then I was kind of a little bit angry, so I texted the CFO instead, Dave. And so I texted Dave and I said, "Hey, do you know what our Fortune 500 penetration is?" And he just copy-pasted a screenshot of Genie back. So he also asked that.

So I said, "Does anyone do anything novel here or there? Just everybody just going to Genie and asking the ontology, you know, for questions."

</details>

**Host**：这就像是现在的大家不再说“让我帮你 Google 一下”，而是变成“让我用 Genie 帮你查一下”。

<details>
<summary>Original English</summary>

**Host**: It's like "let me Genie that for you" instead of "let me Google that."

</details>

**Ali Ghodsi**：现在大家全都在这么做。我们平时在公司里就是这么说的，大家会说：“嗨，谁能直接用 Genie 查一下这个？能不能直接从本体图谱里调取出来？”

所以我坚信这是一个革命性的转变。但这绝不是说你在组织里随便按下一个按钮，企业本体就会凭空诞生。在这方面，我认为 Palantir 确实做得非常出色，他们深入各个企业组织，将大量隐性知识（Tacit Knowledge）梳理成文档并沉淀到组织系统中。

而我们的做法是：自动化地提取这些沉淀下来的知识并构建知识图谱，随后将该图谱输入给智能体，从而精准回答业务问题。并且，它能够以企业管理者最习惯和偏好的形式呈现——以清晰的图表、严谨的分析维度来展现；管理者还可以对这个结果进行多轮深入交互式追问，不断提出问题并即时获得答案，以便快速拍板决策，进而将这些信息与结论迅速下发同步到整个组织当中。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: That's what everybody's doing now. We just say it. We say, "Hey, can someone just Genie this? Like, you know, can you just get it from the ontology?"

So I do think it's a game changer. But it's not just you press a button and you have an ontology in an organization. And I think Palantir actually has done a great job of going to organizations and getting a lot of that tacit knowledge written down and getting it into the organizations.

We automatically take that and build the graph, and then we feed that graph into the agents so that we can answer the question, and answer it in a way that business leaders would like to see it, which is in graphs, analytical way, and a way where you can interrogate that question and continue asking questions and getting answers to those so you can make decisions, and then disseminating that information in the organization.

</details>

### 从“Token 最大化”转向“价值最大化”与成本治理

**Host**：是的，这确实非常惊艳。你之前提到了一个有意思的观点——“开发者显然都在广泛使用 AI，但其实际创造的价值却存疑”。我想就这一点跟你做个深入探讨。因为我觉得你们团队在这方面的探索是最早的一批。

我尽量避免使用“Token 最大化”（Token Maxing）这个词，因为这个词带有相当负面的贬义色彩；但如果从鼓励和赞赏那些善于运用 AI 来显著提升个人生产力的人这个角度来看，你们无疑走在了整个行业的最前沿，对吧？

但随之而来的必然是一个周期循环：大家开始意识到“糟糕，大家使用 AI 时浪费太严重了，现在我们需要转向价值最大化（Value Maxing）”。你们自身在这一转变过程中经历了怎样的探索路径？你们团队是如何看待追求“价值最大化”而非盲目追求“Token 最大化”的？

另外，我也想把 Unity Catalog / Gateway 引入到这个讨论中来，因为我认为 AI 成本治理与管控正变得愈发至关重要，而你们正在帮助广大客户实现这一目标。或许你可以把这几部分结合起来详细展开谈谈。

<details>
<summary>Original English</summary>

**Host**: Yeah, it's pretty amazing. You sort of bookmarked the "developers are obviously using AI, questionable value" [point]. I want to follow up with you on that because I feel like you guys were one of the earliest.

And I don't want to use the word "token maxing" because it has such a negative connotation, but I think in terms of applauding people who can use AI to become more productive, you guys were, you know, at the forefront of that, right? And then of course there's this cycle of, "Oh shoot, people are being wasteful, now we need a value max."

What was your own journey on that, and how do you guys think about value maxing, not token maxing? And then I'm going to throw in Unity Gateway in this, right, because I think the managing of cost piece is actually getting more important and you guys are helping people do that, but maybe tie that in to extend it.

</details>

**Ali Ghodsi**：好的。大约在去年第四季度（Q4），底层基础模型的能力迎来了质的飞跃，变得极其强大。我们当时开始敏锐地观察到：模型确实开始能够带来显著的生产力提升了。于是我自己也开始亲自尝试并深入使用……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, so around Q4 last year was when, you know, the models got really, really good, and we started noticing that, okay, it's actually starting to give much better productivity. So I actually started using...

</details>

<!-- chunk 9/10 -->

### 推动全员落地 AI 编程与成本管控体系的建立

**Ali Ghodsi**：我自己也开始使用这些模型，将代码直接提交到 Databricks 的生产环境中。我的想法是，必须一路贯通到生产环节。我做到了这一点，随后便开始在全公司内部强力推行，告诉大家：“每个人都必须这么做。我已经做到了，你们为什么不行？”如果作为 CEO，都能在这样一个具有极高敏感度、背负着严苛安全合规要求的数据平台上将代码提交至生产环境，那么组织内的任何一个人、任何一位管理者也理应能够做到。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: ...the models myself to sort of start, you know, commit code into production for Databricks, like the actual—as I want to take it all the way to production. So I did that, and started pushing the organization that, "Hey, everyone needs to do that. I have done it. Why are you not?" Like, if the CEO can commit code to production on a very sensitive data platform that has all these security requirements, you should be able to do that too. "You" being any manager, anyone in the organization.

</details>

**Ali Ghodsi**：于是我们开始对所有人进行非常严格的推动，并在第四季度设立了排行榜。到了大约一、二月份新的一年开启时，我们已经全速运转起来了。每个人都在使用这些工具，我们持续推进并进行管理。但与此同时，那种“Token 消耗最大化”（token maxing）的现象在二、三月份也已经开始显现了。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So started pushing everyone very hard, and we started making leaderboards in Q4. And at the beginning of, I'd say January, February, when kicked off the year, we were already full swing. Everybody was using the stuff, and we're pushing, and we're managing this. But you know, the whole token maxing thing was happening around, you know, February, March period already; it was happening.

</details>

**Ali Ghodsi**：我们只是碰巧比其他人领先了几个季度，从而较早地看到了这里正在发生的事情——也就是成本正在逐渐失控。所幸我们当时已经拥有了一个名为 Uni Gateway 的网关，该网关原本就是用来提供 Token 算力容量的。无论是 OpenAI、Anthropic、Gemini 还是 Grok 的算力容量，任何客户找上门来，我们都可以直接向他们提供，因为我们与这些模型厂商以及各类开源模型都建立了合作关系。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So yeah, we just had the luck of being like maybe a few quarters ahead of folks to see what was happening here, and it was getting out of hand. So we already had a gateway—so it's called Uni Gateway—where this gateway was being used to provide token capacity. So you can get OpenAI, Anthropic, Gemini, Grok capacity; like any customer can come to us and we'll just provide them that capacity, because we have relationships with those and any open-source model.

</details>

**Ali Ghodsi**：于是我们开始在网关中引入预算约束机制，并向用户发出预警，例如：“你还剩多少预算”、“你已经接近预算上限了”。我们针对个人以及团队分别实施了这一机制。接着，我们开始构建强大的分析系统，以便能够精准预测各项成本的走向。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So we started putting in budget constraints in place and giving people warnings like, "Okay, you have this much of your budget left, you're getting close to your kind of ceiling." So we started doing that per person and for group, and then we started doing great analytics so we could predict exactly where the costs were going.

</details>

### 智能路由与 Harness 架构带来的成本杠杆

**Ali Ghodsi**：随后，我们又加入了智能路由器（smart routers）。如果你快要耗尽预算，或者只是提出了非常简单的日常问题，路由器实际上可以直接为你选择更便宜的模型。我们开始推行这一做法。不仅如此，我们还构建了一个名为 Omnient 的 Harness 工具框架，它能够在不同的 Harness 之间进行多路复用调度。事实证明，Harness 本身的设计至关重要。如果你使用完全相同的模型，但搭配不同的 Harness 框架，两者之间的实际成本差异可能接近两倍。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And then yeah, and then we added smart routers that could actually pick cheaper models if you're getting close to your budget or if, you know, you have simple questions. We started doing that. We also built a harness called Omnient, which can multiplex between the different harnesses. Turns out actually the harness itself matters. Like if you use the same model but different harnesses, there's almost 2x cost difference.

</details>

**Interviewer**：即使是完全一模一样的同一个模型？

<details>
<summary>Original English</summary>

**Interviewer**: Even exactly same model?

</details>

**Ali Ghodsi**：是的，完全相同的模型版本，仅仅因为 Harness 框架不同，你在实际支出上就会产生两倍的差距。因此，如果你能够灵活切换 Harness，就能在成本控制上获得极大的杠杆优势。借助所有这些手段，我们真正做到了拉平并压低成本曲线：尽管我们的 AI Token 使用量持续攀升……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah. You know, same version, but different harness, you get 2x difference in actual cost. So if you can change harness, you can get a lot of leverage in the cost. So we started using all of this that we were able to actually bend the curve, and actually our cost for AI has been basically—the tokens continue to go up...

</details>

**Interviewer**：但总成本却基本保持持平。

<details>
<summary>Original English</summary>

**Interviewer**: ...but the costs have been sort of stagnant.

</details>

**Ali Ghodsi**：对，基本维持稳定。这对我们而言极其重要，而且市场上对此类能力有着巨大的需求。我认为现在每家企业和组织都在经历这个阶段。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So that's been actually super, super important for us, and there's a huge demand for this. I think every organization is going through this now.

</details>

### 前沿模型与开源模型的市场分化与实际落地

**Interviewer**：确实如此。我参加过很多董事会，目前在 20 多家公司的董事会任职。就在上周，我第一次听到一家具备相当规模的大型企业表示，他们正准备将业务从前沿闭源前沿模型迁移到 GLM 上，而且这是一家非常庞大的工程研发团队。你是否也看到了这种趋势？你认为这代表着一种普遍趋势，还是说仅仅是个例？因为在此之前我也经常听到类似的说法，比如最初 DeepSeek 引发关注并波及英伟达股价时，后来证明影响并没有那么大；接着是 Kimi 时刻，再接着是下一次 DeepSeek 时刻。过去这些似乎都没有对市场产生立竿见影的实质性冲击。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, I, for the first time—I do a lot of board meetings, I'm on 20-some boards. For the first time ever, a company at scale last week said that they're moving from the frontier models to GLM. This is a large engineering organization. Do you see this? Do you think that that's a trend, or do you think that's just like a one-off anecdote? Because I've been hearing about—I remember the first DeepSeek moment and like Nvidia stock, and then that turned out to not be real. Then the Kimi moment, then the next DeepSeek moment. None of it seems to have actually had an appreciable impact on the market.

</details>

**Ali Ghodsi**：是的。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah.

</details>

**Interviewer**：但现在我手头积累的真实案例越来越多了，这种转变似乎真的在发生。我很想听听你的看法。

<details>
<summary>Original English</summary>

**Interviewer**: But now, then the amount of anecdotes that I have are pretty real, and it seems to be happening. Yeah. Love your view.

</details>

**Ali Ghodsi**：我认为大家其实两者都需要。对于那些能够带来高投资回报率（ROI）的高难度复杂任务，他们自然希望使用具备最高智力水平的最新前沿模型。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: I mean, I think people want both. They want, you know, they want the latest model that's super intelligent for the difficult task where they get ROI.

</details>

**Interviewer**：是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Ali Ghodsi**：但与此同时，工作中存在着大量平淡琐碎、并不需要高深智能的任务。比如有些人竟然直接调用大模型框架去给文件重命名之类的。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: But then there's a lot of mundane, dumb things, like, you know, people literally use their harness to rename files and whatnot.

</details>

**Interviewer**：确实是这样。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Ali Ghodsi**：你为了这种琐事支付了高出好几个数量级的昂贵费用。这种事情至少自己动手敲键盘改一下，别让大模型去做。模型在那转上 5 分钟，最后帮你重命名了一个文件，却花掉了你好几美分。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: You know, like, you're paying, you know, orders of magnitude more for that. At least type that in yourself. Don't have the model do that. It's going to spin for 5 minutes and then it's going to rename the file for you and cost you, you know, cents.

</details>

**Interviewer**：我只是想知道，你是否真的在市场上看到了实质性的迁移趋势？

<details>
<summary>Original English</summary>

**Interviewer**: I guess people—I'm just wondering, do you actually see market movement?

</details>

**Ali Ghodsi**：不，大家确实正在付诸行动。他们目前的典型落地模式是：要么采用“专家架构模式”（expert pattern），即使用轻量廉价的开源模型去调用大型专家模型，或者反过来进行协作；要么在它们之间建立一种能够来回流转匹配机制。此外，多路复用不同 Harness 并随时替换 Harness 以此实现成本控制，也是大家普遍采用的做法。例如，很多人发现 Pi 在作为 Harness 框架时效率非常高。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: No, people are moving on it. But what they're doing is that, you know, the pattern is either use, you know, you can use this expert pattern where you have, you know, small cheaper open-source model that uses expert model—the big ones—or vice versa, or a way in which they can sort of ping-pong them to each other, but also multiplexing harnesses and just changing harnesses so that you can control the costs is also what people are doing. You know, people have found, for instance, you know, Pi is very efficient when it comes to as a harness.

</details>

**Ali Ghodsi**：所以我认为未来会出现多种多样的组合方案。正如你所说，模型本身是具备随机性的（stochastic），每次给出的答案都不一样，而且模型迭代变化非常快，因此行业内正在进行大量的探索与实验。我认为我们最终会进入这样一个时代：不再是什么事情都一股脑调用最聪明的模型。过去几年大家的基本范式都是：一旦有更聪明的新模型发布，无论多琐碎简单的任务，大家都全盘套用。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Um, so yeah, I think there's going to be a multitude of these. It's easy to—the models themselves are stochastic, as you said, every time they give a different answer, and they're changing so much. So there's just a lot of experimentation happening. So I think we're going to get to a world where you're not always using the smartest model for everything, which is kind of been the paradigm for the last couple years. Like, new model comes out, it's super smart, they use it for everything, even really, really simple mundane tasks.

</details>

### 初创公司与大企业的分工：架构、代码生成与后训练

**Interviewer**：是的。我来告诉你我观察到的现象：我看到很多人使用 Fable 和 Astra 来做整体架构设计……

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. I'll tell you what I see. I see people using Fable and Astra for like architecture...

</details>

**Ali Ghodsi**：嗯哼。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Uh-huh.

</details>

**Interviewer**：……然后用便宜的模型去做具体代码实现，接着再用 Fable 或 Astra 来做代码审查与审计。这种工作流似乎正在成为一种新兴的标准模式。

<details>
<summary>Original English</summary>

**Interviewer**: ...a cheap model for implementation, and then Fable or Astra for audit. Yeah, like that seems to be like this emerging.

</details>

**Ali Ghodsi**：你们在初创公司群体里看到了什么现象？难道他们不是……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: What are you guys seeing in the startups? I mean, aren't they...

</details>

**Interviewer**：但事实就是如此，这确实就是目前正在形成的典型模式。

<details>
<summary>Original English</summary>

**Interviewer**: But that's it. That's honestly the pattern.

</details>

**Ali Ghodsi**：开源模型的占比大概有多少？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: How much open source?

</details>

**Interviewer**：按 Token 消耗量算，还是按美元消费金额算？

<details>
<summary>Original English</summary>

**Interviewer**: By token or by dollar?

</details>

**Ali Ghodsi**：两种都可以说说。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Either.

</details>

**Interviewer**：按美元金额来算，开源模型大概只占 5%，占比非常小；但如果按 Token 调用量来算，开源模型的占比已经超过了 60%。

<details>
<summary>Original English</summary>

**Interviewer**: So by dollar, open source is like 5%. It's very little. But by token count, it's over 60%.

</details>

**Ali Ghodsi**：是的，我正准备这么说。比如我们去跟像 Decagon 这样的公司交流，我认为在企业内部使用与面向外部的产品端使用之间存在显著差异。在面向外部的产品端，开源模型的占比可能已经接近 90% 了。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I was going to say, I mean, we talked to let's say a Decagon or something like that. I think it's different internal use versus external for product. On the external for product, I think they're almost up to 90% open source.

</details>

**Interviewer**：至于内部使用方面——我不是特指某一家具体公司——很多团队的心态依然是：“我们无所谓，直接用最顶级的闭源前沿模型就行，暂时不用考虑成本控制。”但随着规模进一步扩大……

<details>
<summary>Original English</summary>

**Interviewer**: On the internal—and I don't want to say for them in particular, but a lot of them are like, "We don't care, we'll just use frontier, we're not thinking about cost control." But as it gets bigger, yeah.

</details>

**Ali Ghodsi**：没错，你和我之前一起参加过另一家公司的董事会会议，他们出于减少资源浪费的考虑，确实把内部前沿模型的使用量大幅削减了下来。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Right, you and I were another board meeting where they actually did bring that down just from a waste perspective.

</details>

**Interviewer**：所以我非常明确地看到，在产品侧正在加速向开源模型转移。这正好引出了另一个相关的问题，关于开源模型，尤其是关于“后训练”（Post-training）的具体实践。我认为你们在这方面起步非常早。我记得在 2023 年和你交流过，你们是哪一年收购 Mosaic 的？

<details>
<summary>Original English</summary>

**Interviewer**: So I definitely see that moving more toward open source on the product side. And actually, that's related to another question around open source, but post-training specifically. I feel like you were kind of early. I remember talking to you in 2023. When did you buy Mosaic?

</details>

**Ali Ghodsi**：2023 年。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: 2023.

</details>

**Interviewer**：2023 年。也就是说，你在 2023 年所抱持的愿景，到了 2026 年终于变成了现实。不知道你们是否赞同这一点？这正是我们在行业各处普遍听到的声音……

<details>
<summary>Original English</summary>

**Interviewer**: 2023. Okay. So this vision that you had in '23 kind of came true in 2026. I don't know if you guys would agree, right? Like, that's sort of what we're hearing across...

</details>

**Ali Ghodsi**：那当然。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: You know, of course.

</details>

**Interviewer**：就是大家常说的：“企业必须掌握并拥有属于自己的智能资产（own your own intelligence），对开源模型进行后训练等等。”

<details>
<summary>Original English</summary>

**Interviewer**: Oh, just sort of like, "Hey, you're going to actually own your own intelligence, you're going to be, you know, post-training your open-source models, etc."

</details>

**Ali Ghodsi**：这绝对是初创公司正在践行的路线。我不确定大企业是否已经全面跟进，但是……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And that's definitely what the startups are doing. I don't know if that's what the enterprises are doing yet, but like...

</details>

**Interviewer**：你是否觉得自己当年在这方面布局得太早了？

<details>
<summary>Original English</summary>

**Interviewer**: I mean, do you feel like you were early to that, or...

</details>

**Ali Ghodsi**：首先，在我们刚起步的时候，最初的想法还包含“我们可以帮客户从头进行预训练（pre-train）”。但后来发现这根本行不通，没有任何意义。现在市面上已经有非常优秀的开源预训练模型可以直接拿来使用。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, I mean, first of all, you know, there was—when we started, it was also, "Hey, we'll also pre-train it for you," which that doesn't make any sense. There's so very good pre-trained model now that you can use, right?

</details>

**Interviewer**：但客户可以在这些模型之上进行后训练和强化学习。

<details>
<summary>Original English</summary>

**Interviewer**: But that you can do actually post-training on the model and you can do reinforcement learning.

</details>

**Ali Ghodsi**：是的，我们目前正在大规模开展这项业务，很多初创公司本身就是我们的客户。我们通过强化学习环境（RL environments）帮助他们进行训练，使模型在他们特定的垂直任务场景中表现得极其出色。对于他们来说，这么做非常合情合理：如果你的产品要处理大量高频重复的任务——比如一家初创公司推出了一款面向特定垂直领域的产品，它要解决的是精准的具体问题，而非泛化通用智能——那么选择一个优秀的开源基础模型，利用强化学习进行微调，让它在该特定任务上达到极致性能，是极其明智的选择。这样既能大幅降低运营成本，又能获得极快的推理响应速度，同时还能将核心知识产权（IP）完全掌握在自己手中。从这个角度来看，这条路径完全行得通；不过对于大型传统企业而言，他们目前往往只需要基础的通用能力……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah, we're actually doing it at scale, and many of those startups are actually customers. So we actually help them, you know, using reinforcement learning environments where we can make the models very, very good at the specific task that they are doing. It makes a lot of sense for them to do that. If you have a repetitive task—so if you have a startup and it's offering a product, and the product does something specific, it's not just a general intelligence, it does something specific for you—it makes just a lot of sense to take a really good open-source model, and you know, use reinforcement learning and make it really good at that specific task. You can cut the cost down, they can make it really fast, you know, they control their own IP. So in that sense that is possible, but large enterprises, they just need basic...

</details>

<!-- chunk 10/10 -->

### 大模型评估的困境与前沿模型捷径

**主持人**：自动化……对他们现阶段来说实在太繁重了。确实如此。

<details>
<summary>Original English</summary>

**Host**: ...automation, and it's just too much for them to do this right now. Yeah.

</details>

**Ali Ghodsi**：我认为核心挑战之一在于，你必须拥有高质量的评估体系（evals）。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: I think one of the challenges is, you know, you need good evals.

</details>

**主持人**：完全同意。

<details>
<summary>Original English</summary>

**Host**: Totally.

</details>

**Ali Ghodsi**：但构建出优秀的评估体系是非常困难的。因此，初创公司有动力并且能够集中精力去做这件事，而对于其他大型机构而言，最省事的“快捷键”往往是直接使用顶尖的前沿模型（frontier model），而不是费尽周折去搭建属于自己的评估体系。我们实际上甚至在产品内部为客户自动生成评估集，并将其摆在最核心的位置；但后来发现用户根本不想用它。于是我们妥协说：好吧，那我们把它移到后端作为一个可选功能，结果他们就再也没有去点开过。所以总的来说，我认为……

<details>
<summary>Original English</summary>

**Ali Ghodsi**: And making good evals is hard. So while the startups can do that and they're motivated to do that, other organizations, the easy button might be just to use a frontier model than having to create their own evals. We actually generated even, you know, evals for the customer automatically in the product and we had it front and center, but then people didn't want to use it. So we said okay, let's move it to the back end so that it's optional, and then they would never go to it. So I would say in general...

</details>

**主持人**：为什么会这样？他们只是不想卷入其中，觉得太复杂了吗？

<details>
<summary>Original English</summary>

**Host**: Why? They just don't want to get into it? It's too complicated or...

</details>

**Ali Ghodsi**：我觉得大家想要的是立竿见影的正向反馈。比如会觉得：“嘿，又有新模型发布了，我想赶紧试试看，把眼前的业务问题解决掉。”你根本没有充足的时间按照严谨的科学方法行事——先设计评测基准，再建立完备的 Baseline。这在某种程度上非常像软件工程中的测试驱动开发（TDD, Test-Driven Development）。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: I think you want quick, you know, quick reinforcement of like, you know, hey, there's a new model. I want to try this out. I want to get this problem solved. You don't have time to go do this the scientific method of let's make an eval, let's have a great baseline. And it's sort of like TDD, test driven development.

</details>

**主持人**：在真实的软件工程实践中，大家真的会贯彻测试驱动开发吗？极少数人会这么做，对吧？所有人嘴上都说这是最正确的开发方式，但现实中几乎没有人真正执行。

<details>
<summary>Original English</summary>

**Host**: You know, in software engineering, did people actually do test-driven development? Very few did, right? Everyone said it's the right way to do it, but nobody actually in practice did it.

</details>

**Ali Ghodsi**：是的，这也正是自行训练模型的痛点与“魔咒”所在——评估环节才是最硬的骨头。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So that's the same, that's kind of a little bit of the curse of doing training your own model is the eval is the hard part.

</details>

### Forward Deployed 工程师模式与企业落地支持

**主持人**：据我所知，Databricks 拥有所谓的前线部署（Forward Deployed, FD）团队模式，这在当下是一个非常流行的词汇或缩写。不过在如此庞大体量的企业中推行这种模式具体是怎样的体验？这需要配置全职的 FTE 团队吗？你们是如何运作的，这一模式又是如何演进的？

<details>
<summary>Original English</summary>

**Host**: I know you have an FD model at Databricks. That's a very popular word right now, or acronym. But what does it take to get these at enterprises that large? Is it a full FTE model that's required, or how do you do that, and how's that evolved maybe?

</details>

**Ali Ghodsi**：是的。我们一直设有这些前线部署（FD）工程师，并且市场对他们的需求呈现出爆发式增长。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah. I mean, we've had these FDs and the demand for it's gone up significantly.

</details>

**主持人**：嗯。

<details>
<summary>Original English</summary>

**Host**: Mm.

</details>

**Ali Ghodsi**：其中很大一部分工作在于如何构建企业本体（Ontology）。虽然本体构建过程本身是自动化的，但如果你前期没有采集任何有效信息、没有记录下任何数据，那就无从谈起。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: A lot of it is, you know, how do we build that ontology? The ontology is automatic, but if you're not collecting any information, like you're not recording anything, right...

</details>

**主持人**：确实。

<details>
<summary>Original English</summary>

**Host**: Um.

</details>

**Ali Ghodsi**：所以这是我们承担的核心工作之一。此外还涉及许多具体落地场景，例如客户会提出：“我想构建一个面向最终用户的智能体（Agent），它必须具备极低的延迟响应能力，同时必须配置完备的安全防护栏（Guardrails），防止有人恶意滥用或诱导它回答违规问题等等。”我们便能协助构建出这样的系统。比如 Fox 推出的体育 AI 助手，用户可以与它实时探讨各项体育赛事；如果你试图诱导它聊政治话题，它能极其敏锐地拒绝回答并巧妙地将话题重新引回体育赛事上。这就是 FD 团队所打造的能力。我们深入现场，帮助这些机构真正迈出应用 AI 的第一步。这一点至关重要，因为许多企业内部根本没有足够的技术积淀与专业人才来独立构建这些系统，他们非常需要专业团队在旁提供关键的起步支持，随后才能自主运转起来。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So that's one of the key things that we do, but also things like, you know, I want to build an agent, I want it to be customer-facing, and have really low latency, and I want it to have guardrails to prevent people coming to abuse it or ask it things that we don't want it to answer, and so on. So we can build that, like sports AI that Fox has—you can go chat with it about sport events. You can try to ask it actually about politics, and it's very good at rejecting you and moving and talking about sports instead. So the FDs built that so we'll help the organizations actually get started with AI. It is important because just many organizations do not have the in-house expertise to build this stuff. So they need just a little bit of help on the side and then they get started.

</details>

### Neon 与 Lakebase：专为 AI Agent 打造的极速数据库

**主持人**：完全合理。这更多是智能体（Agent）应用层面的实践。但我最近看到一份来自中立第三方的测试报告，显示 Lakebase 或者说 Neon 已经成为了 Agent 生态中最首选的 Postgres 数据库。我觉得这非常有意思：一方面为 Databricks 感到兴奋；另一方面如果放在一年前，我大概完全预料不到这一结果。

<details>
<summary>Original English</summary>

**Host**: Yeah, makes sense. So this is more related on the agent side, but I saw recently that I think a third party, neutral third party, did some tests that Lakebase or Neon was actually the Postgres database of choice for agents. And I thought that was interesting. One, because you know, exciting for Databricks, but two, I probably wouldn't have guessed that maybe a year ago.

</details>

**Ali Ghodsi**：确实出乎很多人的意料。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Surprise for sure.

</details>

**主持人**：是的，确实令人惊喜。毕竟市面上还有其他拥有极佳开发者生态和发展势头的数据库产品，但 Neon 却毫无悬念地稳居第一。我很好奇，你们究竟是如何攻克这一领域的？又是什么特质让你们在 Agent 领域脱颖而出并赢得市场的？因为在当下的技术周期中，谁赢得了 Agent，谁就赢得了未来的数据库市场。

<details>
<summary>Original English</summary>

**Host**: Yeah, it was a surprise, just cuz there's others out there that have, you know, great developer momentum as well, but it was pretty clearly number one. And so I'm curious, how did you guys crack this? And what makes you win across the agents? Because if you win the agents now, you win the market.

</details>

**Ali Ghodsi**：是的。我认为巨大的功劳应该归于 Neon 团队以及 Nikita 及其核心成员。他们所做的核心突破，就是始终保持着一种极度的执念：如何让大模型与智能体主动倾向并选择 Lakebase 或 Neon 作为底层数据库？

智能体在运作时需要做什么？智能体需要不断进行试验。它们在后台自主运行，尝试编写并构建小型软件模块，而这个过程离不开数据库的支撑。这就要求数据库必须能够以近乎瞬间的速度启动。Neon 团队对性能有着近乎偏执的追求——所有操作都必须在远低于一秒的时间内完成。因此，数据库可以在极短的毫秒级内拉起；哪怕是数 PB 级别的超大型数据库，你也能够在不到一秒钟的时间内完成克隆。这带来了极致的弹性与极速的响应能力。

随后，他们构建了一项杀手级特性——分支（Branching）。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah. I mean, I think a lot of credit should go to Neon and Nikita and team. And I think what they've done is they've just been obsessive about how do you make the models and agents favor Lakebase or Neon as a database. So what do they do? The agents want to experiment. You know, they're going off, they're trying to build a little bit of software. They need the database. So you need the database to come up quickly. So they had this obsession that everything should take far less than a second. So database comes up in far less than a second. You can clone gigantic database—kind of petabyte database—you can clone it in less than a second, you know. So it's like highly elastic, highly responsive. And then they built this killer feature called branching.

</details>

**主持人**：嗯。

<details>
<summary>Original English</summary>

**Host**: Mm.

</details>

**Ali Ghodsi**：分支特性允许你直接对数据库进行分支操作，针对同一个底层数据集派生出成百上千个独立分支。他们把这一机制做得极其轻量化。我们在 Agent 领域的其他工具演进中也看到了类似的趋势，比如 UV、ripgrep 等等——它们本质上都是对传统 Unix 工具链进行深度重构，使其变得极其轻量、速度达到极致飞快。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So branching just lets you branch the database and you can have many many branches over the same database. And they just made this very, very lightweight. We saw this with other things with agents, right? Like UV, you know, ripgrep, like basically reimplementation of a lot of the tools on Unix making them really really blazing fast and lightweight...

</details>

**主持人**：同时还为 Agent 提供了天然的容错与故障安全（fail-safe）机制。而他们把这种理念应用到了难度更高的领域——数据库。

<details>
<summary>Original English</summary>

**Host**: ...and also sort of failsafe for agents. They've just did this to a harder problem which is database.

</details>

### 数据库新范式：面向 Agent 的极速与分支能力

**Ali Ghodsi**：没错。所以现在你拥有了一个全功能的 Postgres 数据库，而且这个数据库兼具所有这些独特优势：极致的速度、极其轻盈敏捷、具备故障安全性，你可以随时回滚到历史快照，轻松执行各类操作。我认为正是这些特性让 Agent 调用它时变得无比得心应手。此外，他们还设计了非常契合的定价模型——因为 Agent 会频繁构建临时软件并运行探索性实验，你绝不希望仅仅因为 Agent 的自动化尝试而导致账单成本瞬间失控飙升。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: So like now you have a Postgres database and the Postgres database has all these advantages that it's really fast, it's nimble, it's fail safe, you can go back to snapshots, you can do those things. So, I think that's why it's just easier for the agents to use this. They also made sure that they had a pricing model that was like: you don't want just because the agents are building some software and experiment, you don't want the cost to run up.

</details>

**主持人**：确实，完全同意。

<details>
<summary>Original English</summary>

**Host**: Yeah, totally.

</details>

**Ali Ghodsi**：如果这是承载大量真实用户访问的生产环境负载，企业当然乐意支付相应的数据库费用；但如果只是为了探索性实验，成本就必须得到控制。Neon 团队对此有着纯粹的专注——他们并不是试图去打赢传统的数据库市场争夺战，也不是单纯为了比某个既有的数据库厂商参数更好看，而是全神贯注于一件事：如何做到对 AI Agent 而言最极致、最优秀的数据库？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: You're okay paying for your database if it's like production use and lots of people are using it, but just to experiment. So I think they were just obsessed. They were not trying to win the database war or trying to be better than some other vendor. They were obsessed with: how are we the best for the agents?

</details>

**主持人**：这是一个全新的用户画像（Persona）。因为在传统的数据库领域，长久以来的核心聚焦点都是“我们如何赋能 DBA 数据库管理员？如何帮助应用开发工程师？如何服务使用数据库的具体人类工程师？”而他们彻底颠覆了游戏规则，提出“我们如何全方位聚焦于 Agent，让 Agent 获得它们心目中最理想的数据库支持？”

<details>
<summary>Original English</summary>

**Host**: And that's a new persona because in databases the obsession has been how do we help DBAs? How do we help app devs? How do we help the people that are using the database? Exactly. They changed the game and said hey, how do we focus on agents and help agents get the best database they want?

</details>

**Ali Ghodsi**：没错。如今在 Neon 和 Lakebase 上创建的数据库实例中，有超过 90% 实际上是由 Agent 自动化创建的，甚至已经不再是人类手动创建的了。数据本身就足以说明一切。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Exactly. And you know now over 90% of the databases that are created on Neon and Lakebase are actually created by agents. So it's not even humans. So you know numbers speak for themselves.

</details>

### 团队协同与 P(doom) 终极拷问

**主持人**：顺便提一句，这确实非常了不起。我自己也已经开始将 Neon 作为我的标准主力数据库来使用了。对我来说这体验很奇妙，因为通常在大型企业并购之后，产品研发节奏往往会放缓；但事实是，Neon 的产品体验反而变得更加实质性地出色了。

<details>
<summary>Original English</summary>

**Host**: By the way, it's remarkable. So, I've started to use Neon as like my standard database and it was bizarre to me because like normally when you enter a large company things slow down. It's actually like the products got materially better.

</details>

**Ali Ghodsi**：是的。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Yeah.

</details>

**主持人**：他们目前是保持完全独立运作，还是与 Databricks 其余团队紧密协同？具体的协作方式是怎样的？

<details>
<summary>Original English</summary>

**Host**: Are they totally independent? Do they work with the rest of the... like how...

</details>

**Ali Ghodsi**：不，他们是一支非常出色的团队，我们之间的协同非常紧密。大家都对数据库和数据技术抱有极大的热情，这是我们共同的基因与日常。整个团队做得极其出彩，把产品打磨得超级敏捷、迅速，并且对智能体生态极其友好。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: No, it's a great team. I mean, and work very closely together. You know, we love databases and data. So we live that. But no, the team does a great job of just making super fast, snappy, and great for agents.

</details>

**主持人**：太棒了。顺便问一句，Ali，你对人类毁灭概率 P(doom) 的评估是多少？

<details>
<summary>Original English</summary>

**Host**: All right. Hey Ali, what is your P doom?

</details>

**Ali Ghodsi**：低于 10%……不，其实接近于 0。你自己的预测是多少？

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Less than 10%. Uh, no. Close to zero. What about yours?

</details>

**主持人**：我不好说。我唯一的回答是：我认为没有 AI 的情况下人类走向毁灭的概率（P(doom) without AI），要远远高于拥有 AI 的情况下人类走向毁灭的概率（P(doom) with AI）。你觉得这个回答怎么样？

<details>
<summary>Original English</summary>

**Host**: I don't know. I say my only answer is my P Doom without AI is much higher than my P Doom with AI. How's that?

</details>

**Ali Ghodsi**：哇，我也正是这么想的！从技术演进的角度来看，在这个观点上我完全赞同 Ali。非常精辟。

<details>
<summary>Original English</summary>

**Ali Ghodsi**: Wow. That's what I say. I went on a technical... I would agree with Ali on this one. Yeah.

</details>