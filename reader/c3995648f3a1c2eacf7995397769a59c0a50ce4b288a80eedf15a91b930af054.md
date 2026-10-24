---
author: All-In Podcast
date: '2026-04-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1bCXCxrDsCs
speaker: All-In Podcast
tags:
  - ai-coding
  - saas-economics
  - ceo-succession
  - nonprofit-governance
  - environmental-health
title: All-In播客：SpaceX与Cursor的重磅交易、SaaS债务危机、苹果新CEO、SPLC遭起诉及结肠癌成因分析
summary: 本期All-In播客深入探讨了科技与社会领域的几大热点话题。首先，节目分析了Elon Musk的xAI与AI编程工具Cursor的战略合作，及其对未来AI编码格局的影响。接着，讨论了私募巨头Toma Bravo放弃SaaS公司Medallia所揭示的SaaS行业债务危机和商业模式挑战。随后，话题转向苹果公司，分析了Tim Cook卸任后新CEO John Turnis面临的创新压力与未来方向。节目还深入报道了南方贫困法律中心（SPLC）因涉嫌欺诈和洗钱被起诉的争议事件。最后，David Friedberg的科学角带来了一项关于与农药相关的年轻人群体结肠癌发病率上升的研究。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - SpaceX
  - Cursor
  - xAI
  - Apple
  - Toma Bravo
  - Medallia
  - Southern Poverty Law Center
  - Anthropic
products_models:
  - Grok
  - Composer 2
  - Siri
media_books: []
status: evergreen
---
### 开场与Sacks会见特朗普

**Jason Calacanis**: 好的，各位，欢迎回到全宇宙最棒的播客，All-In播客第270期，你们播客主持人最爱的播客。和我一起的还是你们的科学苏丹 David Freeberg，独裁者 Chamath Palihapitiya，以及，是的，雨人回来了。没错，他就是 David Sachs。他肯定在华盛顿和总统在一起。是的，总统让他把车开进了车道。呃，Sacks，怎么回事？你推迟了录制。你这个大人物让整个团队把节目推后了一个小时。

<details>
<summary>Original English</summary>

**Jason Calacanis**: All right, everybody. Welcome back to the greatest podcast in the universe, episode 270 of the All-In Podcast, your podcasters's favorite podcast. With me again, your Sultan of Science, David Freeberg, the Dick Tater, Shamont Poly Hopetia, and yeah, the Rainman is back. Yeah, it's definitely David David Sachs. He's definitely in DC with a with Pus. Yeah, POTUS lets him drive in the driveway. Uh, Sax, what's going on? You you pushed back. You uh bigshotted the entire crew and pushed the show back an hour.

</details>

**Chamath Palihapitiya**: 就一条简单的短信。他大概是说和总统在一起，晚点开始。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Simple text. He's like with POTUS started.

</details>

**David Sacks**: 好的，好的，爸爸。看看他。好吧。好吧。大人物。怎么了？不，你看，我今天在华盛顿，在白宫，我只是问总统是否有时间，他挤出了时间，我们确实开了一个小会，所以我们为此推迟了播客。我只想说一件事，和他打交道真是太愉快了。你知道，当我在媒体上读到他们总是用某种方式描述他，说他对人大喊大叫，或者他情绪多变之类的。但那从来都不是我的经历。和他在一起总是很愉快。他总是那么和蔼可亲。

<details>
<summary>Original English</summary>

**David Sacks**: Okay. Okay, Daddy. Look at him. All right. All right. Big shot. What's going on? No, look, I was in DC today and I was at the White House and I just asked if the president had time and he made time and we we did have a little meeting and so we did push back the pod for that. One thing I just want to say is just what a pleasure he is to deal with. You know, when I read in the media, they're always describing him in a certain way that, you know, he's yelling at people or he's moody or or something like that. And that's never ever been my experience with him. He's always pleasant to be with. He's always genial.

</details>

**Jason Calacanis**: 他会问问题。他对主题很感兴趣。

<details>
<summary>Original English</summary>

**Jason Calacanis**: He ask questions. He's interested in the subject matter.

</details>

**David Sacks**: 这完全是另一种描述。我完全不明白媒体到底是怎么回事。

<details>
<summary>Original English</summary>

**David Sacks**: It's just a completely different portrayal. I don't get where the media is coming from at all on this.

</details>

**Jason Calacanis**: 他魅力十足。我们就实话实说吧。他很有魅力。

<details>
<summary>Original English</summary>

**Jason Calacanis**: He's charming AF. Let's just call it what it is. He's charming.

</details>

**David Sacks**: 我的意思是，也许如果你背叛他，可能会。我不知道。但我从未见过任何他们所描述的那种证据。我认为在人工智能问题上，我们真的很幸运，当这场人工智能革命发生时，他是白宫的总统。

<details>
<summary>Original English</summary>

**David Sacks**: I mean, maybe if you double crossed him, maybe. I don't know. But I've just never seen any evidence of of how they describe him at all. And I think on our issues of AI, I think we're really lucky that he's the president who's in the White House when this AI revolution is happening.

</details>

**Jason Calacanis**: 我的意思是，回顾一下历史，Sacks，如果现在是Kamla Ding-Dong在位会怎么样？我们可能就没有数据中心了？

<details>
<summary>Original English</summary>

**Jason Calacanis**: I mean, do an old history, Sax, what would happen if Kamla Ding-Dong was in right now and we'd have like no data centers?

</details>

**David Sacks**: 我们将没有数据中心，他们会用人工智能来审查我们，他们会通过人工智能推广DEI价值观。那在拜登的行政命令里。**特朗普总统**只是希望国家赢，希望成功，他对这些没有末日论者的神经质。这并不是说我们不支持任何监管，但我们应该有针对具体问题的具体解决方案，而不是对此畏缩不前，试图停止所有进展。我认为一个很好的例子是他关于数据中心的想法，他在一年多前，在数据中心成为热门政治话题之前就说过，我们应该让我们的人工智能公司建立自己的表后发电。这比伯尼·桑德斯那种关停一切的做法要好得多。所以我不知道，我认为我们非常幸运，他在这项技术发展的关键时期担任总统。而且就像我说的，他一直对此很感兴趣。他与很多商界领袖交谈。我总是对他已经知道的东西印象深刻。他听取行业顶尖人物的意见，并综合他所听到的。我认为他在这方面非常出色。

<details>
<summary>Original English</summary>

**David Sacks**: We'd have no data centers and they'd be using AI to censor us and they'd be promoting DEI values through AI. That was in the Biden executive order. President Trump just wants the country to win and be successful and he doesn't have these like doomer neurosis about it. That's not to say we don't support any regulation at all, but we should have specific solutions for specific problems as opposed to being cowering in fear over this and just trying to halt all progress. And I think a really good example of that was his idea around data centers where he said over a year ago before data centers even became a hot political topic that we should let our AI companies stand up their own power generation behind the meter. And that's a much better approach than the Bernie Sanders approach of just shutting everything down. So I don't know I think we're like very fortunate that he's the president during this critical time and development of this technology. And like I said he's always been interested in it. He talks to a lot of business leaders. I'm always actually very impressed with what he already knows. He listens to like all the top guys in the industry and he synthesizes what he hears. I think he's very good at that.

</details>

**Jason Calacanis**: 他谈到**Anthropic**的那些人，说他们是才华横溢的家伙，并且对他们赞不绝口，说他们是多么天才，并且他们正在进行一项交易。关于白宫和Anthropic之间的关系，有什么内幕消息吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: He was talking about the anthropic guys and he was like these are brilliant guys and he was like giving the flowers to them and how genius they were and that they were working on a deal. Any insights there about the relationship between the White House and Anthropic.

</details>

**David Sacks**: 我认为他说的非常平衡和准确。就像你说的，他说他们是非常聪明的人。他们确实有很棒的产品。我当然承认这一点。他还说他们非常左翼，但那是我们可以解决的问题。这不必成为交易的障碍。他说他们试图告诉五角大楼该做什么，五角大楼不喜欢这样。但无论如何，你看，他希望美国公司成功。而且他，我认为他真的非常喜欢高智商的人。我的意思是，他一直这么说，人们以为他在开玩笑，但我实际上认为这就像他的核心信念之一，他就是真的喜欢聪明人。他喜欢和聪明人在一起。忠诚的人，聪明的人，上镜的人，这似乎是三个圈子。嘿，Sachs，你占了其中两个。好吧。让观众自己去想吧。

<details>
<summary>Original English</summary>

**David Sacks**: I thought what he said was very balanced and accurate. Like you said he said that they were very smart guys. They do have a great product. I've certainly acknowledged that. He also said that they were very leftwing, but that was something we could work through. Didn't have to be a deal killer. He said they tried to tell the Pentagon what to do, which the Pentagon didn't like. But in any event, I mean, look, he wants American companies to be successful. And he he I think genuinely really does like high IQ people. I mean, he says it all the time and people think he's joking, but I actually think it's like one of his core convictions is he just really likes smart people. He likes being around smart people. Loyal people, smart people, people who are good on camera seem to be the three circles. And hey, Sachs, you fall into two of the three. Uh, all right. Let the audience figure that out.

</details>

### SpaceX与Cursor的重磅交易

**Jason Calacanis**: 话题一，**SpaceX**与**Cursor**签订了一项巨额协议。你知道Cursor，那家AI编程初创公司。真的，他们定义了这个类别。**XAI**和Cursor正在合作构建一个新的AI编程模型，号称将成为“世界上最好的编程和知识工作AI”。交易是这样的：据解释，SpaceX要么在2026年底前以600亿美元收购Cursor，这比他们传闻中的融资估值高出100亿美元，要么他们将为双方的合作向Cursor支付100亿美元。彭博社说，你可以把那100亿美元基本上看作是分手费。所以我认为这笔交易是板上钉钉了。Cursor在2月底的年化收入达到了20亿美元。这是一台印钞机。他们预计到2026年底，年化收入将达到60亿美元。他们要翻三倍。SpaceX预计2026年的收入在220到240亿美元之间。所以这对SpaceX的收入故事来说是相当增值的，在SpaceX的IPO时，其估值目标现在是2万亿美元，这将是其营收的约80倍。人们会说这是一个很高的估值，但也要用机会来衡量，Cursor的估值将是30倍，所以我认为这对大家来说最终都是一笔好交易。Cursor最初我认为是建立在Anthropic的LLM之上的，你以前可以在上面使用任何LLM，但在3月份，Cursor发布了他们专有模型**Composer 2**的第二版。就是这个。它现在的排名很高，在GPT4 5.4和Opus 4.6之间。这个故事的关键部分是，Elon在**Colossus**拥有55万个GPU。他正在扩展到100万个，然后当然他会把它带到太空。所以如果你相信基础设施很重要，而且很明显确实如此，这对一直受计算能力限制的Cursor来说是不可思议的。所以这是花生酱和巧克力。如果你把这两者放在一起，我预测这将在12个月内将SpaceX、XAI和Cursor推向编程排行榜的前列。这是我的预测。Chamath，作为SpaceX的股东，通过你支持的Starlink公司的收购。你有什么想法？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Uh, topic one, SpaceX has signed a huge deal with Cursor. You know, Cursor, that's the AI coding startup. Really, the the they defined the category. XAI and Cursor are building and collaborating on a new AI coding model that would quote be the world's best coding and knowledge work AI. Here's the deal. As it's been explained, SpaceX will either buy Cursor by the end of 2026 for 60 billion, that's 10 billion more than they were rumored to be raising at, or they will pay Cursor 10 billion for their collaboration together. Bloomberg says you can think of that $10 billion essentially as a breakup fee. So I think it's fate a calm plea that this deal is going to get done. Curser's run rate 2 billion at the end of February. This is a money printing machine. They expect to end 2026 with a $6 billion run rate. They're going to triple it. SpaceX projected revenue between 22 and 24 billion in 2026. So this is quite accretive to the revenue story at SpaceX at the IPO of SpaceX which is now targeting a valuation of 2 trillion which would be trading at roughly 80 times topline revenue which is a you know people would say it's a high valuation but also measure it with the opportunity cursor's valuation would be 30x so this is a good deal I think for everybody at the end of the day cursor started I think built off of of uh anthropics LLM you could use any LLM previously on it, but in March, Curser released the second version of their proprietary model, Composer 2. And uh here it is. It's it's ranked pretty high right now. It's between uh GPT4 5.4 and Opus 4.6 as you can see on the screen. The key part of the story here is that Elon has 550,000 GPUs in Colossus. He's scaling up to 1 million and then of course he's going to bring it to space. So if you believe that infrastructure matters and it's pretty clear it does this is incredible for cursor who has been compute constrained. So this is peanut butter and chocolate. If you put these two together I predict that this is going to move space xxx AI and cursor to the front of the coding leaderboard within 12 months. That's my prediction. Chimoth shareholder in SpaceX via the acquisition of the Starlink company that you were a backer of. What are your thoughts?

</details>

**Chamath Palihapitiya**: 这项收购基本上已经谈妥，其结构方式是为了让S1文件不过期。所以我认为它的宣布方式更多地与他们不想放慢速度，不想重写S1的部分内容，不想重做披露，不想重做风险有关。所以我认为你会看到这笔交易将会完成。事实上，这笔交易实际上已经完成了。但聪明之处在于，SpaceX今天在哪里？就算它值一万亿吧。它可能值多少？为了这次讨论，我们假设是两万亿。所以当交易以股票换股票的方式完成时，如果又是未来的600亿美元，实际上Elon已经得到了50%的折扣。他买了什么？他可以用2万亿美元的估值发行600亿美元的股票，然后得到一个模型和一个服务，我认为在编程领域非常有吸引力，而我们知道所有近期和短期的收入增长都在那里。这也是经过艰苦努力获得的模式，在强化学习中非常有价值。他得到了所有这些，然后他得到了一个非常顶尖的团队，我们早就知道Cursor团队非常出色。如果你看看Grok的使用情况，它解释了为什么他有这种过剩的算力。曾有一段时间，Grok对其输出token有非常陡峭和激进的折扣，在那一刻，有大量的实验和使用，但随着时间的推移，这种情况就消失了。所以Colossus内部有大量的算力和相对较低的利用率，他能够扭转局面，用柔术般的动作，基本上收购了目前AI领域最有趣、最有价值的第三方包装服务。所以，事实是他们以这个价格，实际上是300亿美元就拿下了。所以我认为这是一个非常好的交易，非常聪明的交易。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: The acquisition was essentially negotiated and the way that it's structured is so that the S1 doesn't go stale. So I think the way that it was announced has more to do with the fact that they don't want to slow down and have to rewrite parts of the S1, have to redo the disclosures, um have to redo the risks. And so I think what you're going to see is that this will get done. In fact, the deal is effectively done. But what's so smart is that where is SpaceX today? Let's call it a trillion. Where could it be, just for the purpose of this argument, let's say two trillion? So when the deal gets done on a stock- forstock basis, it's going to be if again if it's 60 billion in tomorrow dollars, effectively Elon's gotten a 50% discount. And what has he bought? He can issue $60 billion of stock at a $2 trillion valuation and get a model and a service that I think is extremely compelling in coding, which is where we know all of the immediate and short-term revenue gains are. It's also patterns that are hard fought and are really valuable in reinforcement learning. He gets all of that and then he gets a very cracked team, which you know, we've known for a while that the cursor team is absolutely excellent. If you look at the Grock usage, it shows why he had this excess capacity. There was a moment where Grock had a very steep and very aggressive discount on their output tokens and in that moment there was just a lot of experimentation and usage and over time that sort of went away. So there was a lot of capacity and a relatively low utilization I think inside of Colossus that he was able to turn around Jujitsu moved the whole thing and basically acquire the most interesting and valuable third party rapper service in AI right now. So uh and the fact is that they got it effectively I think at this price for 30 billion. So I think it was a really good deal really smart deal.

</details>

**David Sacks**: 你说得对。我确实记得一次新闻发布会，拜登说：“我们得关注这家伙。”紧接着，司法部就提起了一项诉讼，攻击该公司招聘不足。记得吗？无论如何，那都是陈年旧事了。所以让我们把那抛在脑后。看，我同意你们对此的分析。我认为这两家公司非常互补。Cursor显然在编码方面非常强大。这就是它带给XAI的。XAI带来了算力和一个基础模型。而Cursor的问题在于，尽管编码现在是AI领域的热点，但当它起步时，它实际上是在与OpenAI和Anthropic这样的通才竞争。但现在这些通才已经决定在这个编码领域进行垂直整合，对吧？所以Cursor现在正在与Cloud Code和OpenAI的Codex竞争。所以他们依赖于那些正在进入与他们竞争的业务的基础模型公司，这实在不是一个好位置。对吧？所以现在他们与一个不同的基础模型公司建立了新的联盟，这个公司也带来了算力，这非常有道理。然后他们带来了，Cursor给XAI带来了训练数据、大量的企业客户以及在编码方面的经验，我认为这将加速XAI在这一领域的发展。

<details>
<summary>Original English</summary>

**David Sacks**: Well, you're right. I do remember a press conference where Biden said, "We got to look at this guy." And so on the heels of that, the DOJ brought a a lawsuit attacking the company for not hiring enough. Remember that? Anyway, that's all ancient history. So let's let's put that behind us. Look, I I agree with your guys' analysis on this. I think these two companies are are very complimentary. Cursor obviously is very strong in coding. That's what it brings to XAI. XAI brings compute and they bring a foundation model. And the problem that cursor had is that even though coding is kind of like the white hot area of AI right now, when it got started, it was really competing against generalists in the form of open AI and anthropic. But now those generalists have decided to vertically integrate in this area of coding, right? And so cursor is now competing against cloud code and open AAI's codeex. And so they were dependent on foundation model companies that were getting in the business of competing with them which was just not a good place to be. Right? So now they have this new alliance with a different foundation model company which also brings the compute just makes a lot of sense. And then they bring cursor brings to XAI the training data a lot of enterprise clients and the experience in coding and I think this will accelerate XAI in this area.

</details>

**Jason Calacanis**: Sacks，你认为他们会放弃Kimmy K2.6吗？因为我认为Cursor的Composer 2用的是登月模型。Elon不可能花600亿美元却不用Grok来运行。我得这么想。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Sax you think they're going to dump Kimmy K2.6 six cuz I think Herser composer 2 uses the moonshot model. There's no reasonable way that Elon's going to pay $60 billion and not run on top of Grock. I got to think

</details>

**David Friedberg**: 我认为这可能很难，取决于用户。让Cursor如此出色的原因之一是...

<details>
<summary>Original English</summary>

**David Friedberg**: I think it might be tough depending on the the users. One of the things that makes Cursor so good.

</details>

**Jason Calacanis**: 等等，等等，多说点。你什么意思？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Wait, wait, say more on that. What do you mean?

</details>

**David Friedberg**: 所以，我认为不同的开发者希望在这方面有选择。有一个切换开关。所以，Cursor真正好的地方之一是他们有一个构建得非常好的IDE，这个应用层让它可能在用户体验方面超越了Codex、Claude或任何其他东西，意味着开发者在使用这个工具。你可以使用第三方IDE并集成模型或任何其他你正在使用的第三方服务，但我会想象开发者会希望继续至少在实际为他们编写代码的东西上有一些选择。过去120天里，人们开始意识到，AI的价值有多少是通过编写软件来实现的。我们有一个包装词，我们称之为“代理”（agents）。但代理从根本上说只是快速启动的应用程序。但对于所有这些，正如我们很快意识到的，你最终会制造太多的代理。它们最终会变得超级低效。它们需要被工程化。你仍然需要有强大的软件工程能力和才能来修复所有代理，构建所有工具链，让所有东西协同工作得很好，这就是为什么拥有一个强大的开发者环境，一个强大的IDE，实际上能解决那个最大的问题。所以最终所有那些对代理充满热情的企业都会说，“哇，等等。我们实际上得解决这一切是怎么做的。”就像我们本周在亚马逊的那个故事中看到的那样，内部有上百万个代理被启动，所有东西都在浪费资源，冗余的数据创建，冗余的数据存储，冗余的API调用等等。大量的金钱被浪费。所以你仍然需要中心化。你需要有优秀的软件工程人才，他们能构建好的基础设施并善用这些代理。而这最终将需要AI工具与标准软件工程前端的集成，也就是Cursor拥有的IDE。所以我认为这可能就是为什么每个人都开始意识到拥有软件工程师可能会让你在这场军备竞赛中获胜，而Elon购买Cursor似乎非常明智。

<details>
<summary>Original English</summary>

**David Friedberg**: So, I think that the different developers want to have choice in that sense. There's a toggle. So one of the things that's really good about cursor is they've got this very well-built out IDE this application layer that puts them probably from a UX perspective meaning developers are using the tool above codecs above clawed above anything else you can use a third party IDE and integrate the models or integrate whatever other third party service you're using but I would imagine that the developers are going to want to continue to have at least some choice on what's actually writing the code for them. The thing that people are waking up to in the last 120 days is just how much of the value of AI is being realized by writing software. And we've kind of got this rapper term, we call it agents. But agents are fundamentally just quickly spun up applications. But for all of them, as we're realizing very quickly, you end up making too many agents. They end up being super inefficient. They need to be engineered. And you still need to have a strong software engineering. capability and competency to fix all the agents to build all the harnesses to make everything work well together and that's why having a strong developer environment a strong IDE actually solves that biggest problem. So eventually all the enterprises that are getting hot and heavy on agents are going to be like, "Whoa, wait a second. We've actually got to fix how this is all being done." As we saw this week in that story with Amazon where there's like a million agents being spun up inside and everything's wasting resources, redundant data creation, redundant data stores, redundant API calls, etc. Tons of money being wasted. So you have to centralize still. You have to have good software engineering talent that's making good infrastructure and good use of these agents. And that ultimately will require an integration of the AI tooling with a standard software engineering front end which is the IDE that cursor has. So I think that that's probably where everyone's waking up to the fact that having the uh the software engineers may end up winning you the arms race here and seems pretty smart for Elon to buy cursor.

</details>

### SaaS行业的债务炸弹

**Jason Calacanis**: 话题二，私募股权领域是否存在SaaS债务炸弹？**Toma Bravo**，我们去年在第四届All-In峰会上请到了**Orlando Bravo**，正接近达成一项协议，将其投资组合公司**Medallia**移交给其债权人。这是一家做客户体验的SaaS公司。Toma Bravo在2021年以64亿美元全现金在市场顶部收购了他们。作为交易的一部分，他们承担了30亿美元的债务。背景是，2021年，这家公司有4.7亿美元的收入，年增长20%。本月早些时候，彭博社报道称，Toma Bravo对Medallia的债务偿还成本将从每年1亿美元增加到3亿美元，翻了三倍。**黑石集团**和其他公司拒绝向这家公司，向这家SaaS公司提供生命线。所以，看起来Toma Bravo只是交还了钥匙，抹去了51亿美元的股权。Chamath，你的看法。我们已经讨论了一段时间SaaS的逆风了。你对此一直非常直言不讳。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Okay. Topic two. Is there a SAS debt bomb in private equity? Toma Bravo, we had Orlando Bravo at the fourth all-in summit uh last year, is nearing a deal to hand its portfolio company Medallia over to its creditors. This is a SAS for customer experience company. TB acquired them in 2021 for 6.4 billion all cash at the top of the market. As part of the deal, they incurred 3 billion in debt. And for background, in 2021, this company had 470 million in revenue, growing 20% a year. Earlier this month, Bloomberg reported that TB's debt servicing costs for Medallia were about to triple from 100 million a year to 300 million a a year. Blackstone and other firms refused to extend a lifeline to the company, to the SAS company. So, it looks like Toma Bravo just handed the keys back and wiped out 5.1 billion in equity. Shimath, your thoughts. We've been talking about the SAS headwinds for a bit. You've been quite vocal about it.

</details>

**Chamath Palihapitiya**: 嗯，首先，我认为Toma Bravo是一个运营得令人难以置信的组织。他们的回报率高得惊人，Orlando是一个非常非常非常优秀的投资者。那么，我认为发生了什么呢？我怀疑他们可能已经收回了大部分（如果不是全部）的股权。很有可能他们在过去五年里至少进行了一两次股息资本重组。如果我没猜错，我怀疑他们是正回报。可能不是他们想要的回报。所以交出钥匙变得更容易，因为你必须记住，在私募股权中，整个策略都是为了改造那些在某个时候不起作用的资产，对吧？他们很少会买我们四个人会买的那种公司，那种干净白纸、从头开始、不惜一切代价增长的公司。所以他们有运营合伙人和所有其他人在背后随时准备收拾烂摊子。这就是整个策略。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Well, first of all, I think Toma Bravo is an unbelievably well-run organization. Their returns are bonkers and Orlando is uh really, really, really good investor. So, what do I think happened? I suspect that they probably got enough of their equity, if not all of their equity. There's probably a decent chance that they did at least one or two dividend recaps in the last five years. And if I had to guess, I suspect that they are positive return. It may not be the return that they would want. And so turning the keys over becomes easier because you have to remember in private equity, the entire playbook is for transformations of assets that are at some point not working, right? It's very rarely that they're buying the same kinds of businesses that the four of us would buy, which is just sort of of this, you know, clean white sheet denovo grow at all costs kind of business. So they have operating partners and all of these other people waiting in the wings to unfuck [ __ ] situations. That's the whole playbook. M

</details>

**David Friedberg**: 所以，要交出来，我怀疑这意味着有一个核心的腐烂，人们无法修复，再加上他们可能已经获得了足够的下行保护，这对他们来说不是什么大事。现在这对债券持有人来说是个问题，然后这可能会影响到Toma Bravo未来可能需要为后续交易支付的借贷成本。我不知道，但我怀疑他们不会就这么放弃一个业务。所以我怀疑他们可能已经收回了大部分资金。我不知道这是不是真的。有人发布了一些内部数据显示，Medallia的销售团队只完成了18%的目标。你们知道这家公司是做什么的吗？Medallia？

<details>
<summary>Original English</summary>

**David Friedberg**: so to turn it over I suspect means that there is a core rot that people couldn't fix combined with the fact that they have probably gotten enough downside protection that it's not a huge thing for them. Now this is an issue for the bond holders and then that'll maybe flow through to the borrowing cost that Tom Bravo has to pay maybe for a subsequent deal. I don't know but I doubt that they would just walk away from a business. So I suspect they probably got most of their money out. I don't know if that's true. There was someone that published some internal data showing that the sales team was like 18% a target at Medallia. Do you guys know what this company does? Medalia

</details>

**Jason Calacanis**: 客户支持是它的主要领域，还有客户体验管理。我不太清楚。

<details>
<summary>Original English</summary>

**Jason Calacanis**: customer support uh is the general arena and customer experience management. I don't know.

</details>

**David Friedberg**: 我不知道那是什么意思。

<details>
<summary>Original English</summary>

**David Friedberg**: I don't know what that means.

</details>

**Chamath Palihapitiya**: 是的。他们基本上会发送，比如你乘坐加勒比游轮后会收到一份调查问卷，然后他们利用这些调查数据为管理层和运营团队提供管理洞察和运营洞察，以改进他们的产品或服务质量。所以这有点像一个反馈调查循环。所以如果我告诉你们，嘿，你们想建立一个反馈调查循环来更好地经营你们的业务，你们今天是会购买SaaS，还是会要求你们的AI为你们启动一个代理来做这件事？我认为这正是发生的事情的一大部分，所有这些类型的公司，购买SaaS产品的替代方案是内部开发一些东西，而内部开发它要便宜得多，也容易得多。你会得到一个定制的工作流程。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah. They'll basically send like you go on Caribbean cruise ships and you get a survey afterwards and then they use that survey data to provide management insights and operational insights to the leadership team and the operating team on how to improve the quality of their product or their service. So it's sort of like this feedback surveying loop. So if I were to tell you guys, hey, you want to build a feedback surveying loop to run your business better, are you gonna buy SAS today or are you gonna ask your AI to spin up an agent for you to do that? And I think that's a big part of what's happened is all these sorts of companies where the alternative to to buying a SAS product is to spin something up internally and it's much cheaper and easier to spin it up internally. You get a custom workflow.

</details>

**David Sacks**: underlying problem is that these businesses in the SAS space where you're driven by net new sales every year. How many new customers are you signing up and then you're trying to manage retention and you're trying to increase sell through and retain customers? They're just having a really hard time sourcing new customers and there's probably higher than modeled attrition. That's right. And when you have a very kind of typically historically predictable business where you can say, "Hey, I've got a net revenue retention of 118% or what have you, meaning I'm I'm selling into my install base by 18% over what I'm making last year and then I'm signing up new customers, you can lever that business, right? You can borrow money against those cash flows because it becomes predictable." And what's happened in the last year in particular is agents have become so good and so fast and so cheap that many enterprises can simply spin up an alternative to a vertical SAS solution and that's crushing the sales team's ability to sell in. That's who you're competing against. Now I want to make one point and just link this with something else that happened this week and that's **Kevin Warsh**'s hearing for Fed Reserve chair. Kevin Warsh went and talked a lot about the deflationary effect of AI and I actually think we all talk about the SAS apocalypse as if it's this sort of like isolated business phenomenon where these SAS companies are getting blown up. I think another lens to look at what's going on is the incredible deflation of how much it costs to successfully run a business and you don't have to pay a premium price for SAS products anymore. Meaning that that piece of the business can suddenly get much cheaper. that AI is delivering on its deflationary promise. I'll just say one thing about what Warsh said. Warsh spoke a lot about the deflationary evolution promised by AI and that he expects that it will drive productivity growth like we've never seen before. But he said I don't know what that's going to do to the job market that there may be a dislocation between that productivity growth being realized and how the labor markets are going to be able to respond to those things. But fundamentally, he's saying that we're going to see economic deflation. The problem with economic deflation is that when it occurs, it means some business is seeing their revenue go down. And if that segment of the economy is levered, if they have debt sitting on top of that piece of the economy where it's supposed to always, always grow like a SAS company's top line is always supposed to grow. Suddenly that debt gets impaired and that can have an economic ripple effect that is adverse. But what he's pointing out is that as a result of deflation because it's not coming from some cost cutting or economic contraction. What he's saying is that the deflationary forces ultimately lead to economic expansion because other parts of the economy will now grow. So if I can suddenly cut, you know, call it 50% of my SAS budget and I can reinvest that capital in other ways of growing my business instead of managing my expenses all of a sudden my enterprise will grow and the economy will grow. He also said, just as an aside, and I want to make sure I cover this so so that we're really clear. He said, "The way that we've been measuring inflation is wrong, and that he doesn't agree with the way the Fed has been measuring inflation because you can do a survey of any household and they'll tell you, my god, everything's so expensive. So all of the indices and [ __ ] that are being used to calculate an inflation index is completely misrepresenting what the average American is actually feeling." And so he wants to rethink how the Fed is addressing inflation from an interest rate perspective. But he does think that the overall kind of economic picture is one of deflationary pressure and productivity gains coming out of AI.

<details>
<summary>Original English</summary>

**David Sacks**: Yeah. So the underlying problem is that these businesses in the SAS space where you're driven by net new sales every year. How many new customers are you signing up and then you're trying to manage retention and you're trying to increase sell through and retain customers? They're just having a really hard time sourcing new customers and there's probably higher than modeled attrition. That's right. And when you have a very kind of typically historically predictable business where you can say, "Hey, I've got a net revenue retention of 118% or what have you, meaning I'm I'm selling into my install base by 18% over what I'm making last year and then I'm signing up new customers, you can lever that business, right? You can borrow money against those cash flows because it becomes predictable." And what's happened in the last year in particular is agents have become so good and so fast and so cheap that many enterprises can simply spin up an alternative to a vertical SAS solution and that's crushing the sales team's ability to sell in. That's who you're competing against. Now I want to make one point and just link this with something else that happened this week and that's Kevin Worsh's hearing for Fed Reserve chair. Kevin Warch went and talked a lot about the deflationary effect of AI and I actually think we all talk about the SAS apocalypse as if it's this sort of of like isolated business phenomenon where these SAS companies are getting blown up. I think another lens to look at what's going on is the incredible deflation of how much it costs to successfully run a business and you don't have to pay a premium price for SAS products anymore. Meaning that that piece of the business can suddenly get much cheaper. that AI is delivering on its deflationary promise. I'll just say one thing about what WarCH said. Warch spoke a lot about the deflationary evolution promised by AI and that he expects that it will drive productivity growth like we've never seen before. But he said I don't know what that's going to do to the job market that there may be a dislocation between that productivity growth being realized and how the labor markets are going to be able to respond to those things. But fundamentally, he's saying that we're going to see economic deflation. The problem with economic deflation is that when it occurs, it means some business is seeing their revenue go down. And if that segment of the economy is levered, if they have debt sitting on top of that piece of the economy where it's supposed to always, always grow like a SAS company's top line is always supposed to grow. Suddenly that debt gets impaired and that can have an economic ripple effect that is adverse. But what he's pointing out is that as a result of deflation because it's not coming from some cost cutting or economic contraction. What he's saying is that the deflationary forces ultimately lead to economic expansion because other parts of the economy will now grow. So if I can suddenly cut, you know, call it 50% of my SAS budget and I can reinvest that capital in other ways of growing my business instead of managing my expenses all of a sudden my enterprise will grow and the economy will grow. He also said, just as an aside, and I want to make sure I cover this so so that we're really clear. He said, "The way that we've been measuring inflation is wrong, and that he doesn't agree with the way the Fed has been measuring inflation because you can do a survey of any household and they'll tell you, my god, everything's so expensive. So all of the indices and [ __ ] that are being used to calculate an inflation index is completely misrepresenting what the average American is actually feeling." And so he wants to rethink how the Fed is addressing inflation from an interest rate perspective. But he does think that the overall kind of economic picture is one of deflationary pressure and productivity gains coming out of AI.

</details>

**David Sacks**: 我对这件事有两种看法。我先谈谈私募股权的机会。让我先说一句，从历史上看，软件业务只有两个好的退出途径。一个是IPO，另一个是并购。然后这些大型私募股权公司出现了，给了我们第三个可能的退出途径，那就是你卖给他们，然后他们会根据，我不知道，三分之一的股权和三分之二的债务来筹集资金。所以这是债务融资的收购，这种做法在非科技经济领域已经存在很长时间了，但在科技世界里是相对较新的。原因是，如果你要用债务来融资购买，你需要有非常稳定的现金流，因为如果你错过了，如果你的现金流错过了，你无法支付债务利息，那么你将失去所有的股权，因为债权人会进行止赎。所以，为了进行任何形式的债务融资，你必须有非常可预测的现金流。很长一段时间以来，人们认为软件确实有那些可预测的现金流，至少对于成熟的企业来说，那些处于可以IPO作为替代选择阶段的企业。所以这是一个非常吸引人的事情。就像我说的，我认为有第三个选择是很好的。我对今天私募股权业务的现状有两种看法。一方面，现在的定价对他们来说一定非常有吸引力。我的意思是，我们看到公共SaaS公司的ARR达到十亿美元，增长率为20%，毛利率为80%，而它们的交易价格仅为ARR的三倍。

<details>
<summary>Original English</summary>

**David Sacks**: Well, I'm of two minds about this. I'm going to talk about the opportunity for private equity. Let me just say backing up that historically we only had two good exits for software businesses. One was to IPO, the other was M&A. And then these big private equity shops came along and gave us a third potential exit, which is you would sell to them and then they would raise the capital based on I don't know 1/3 equity and 2/3s debt. So it was debt finance buyouts which is something that's been around in let's call it the non- tech part of the economy for a long time but was a relatively new entrant into the world of technology. And the reason for that is that if you're going to to debt finance a purchase you need to have very stable cash flows because if you miss if your cash flows miss and you can't pay your interest on the debt then you're going to lose all your equity because the debt holders will foreclose. So in order to do a debt financing of any kind, you have to have very predictable cash flows. And it was believed for a long time that software did have those predictable cash flows, at least for the mature businesses, the ones that were at the stage where they could IPO as a a potential alternative. So it was a very attractive thing. I like I said, I think it was great to have that third option. I I'm of two minds about where the private equity business is today. On the one hand, the pricing now has got to be super attractive for them. I mean, we're seeing public SAS companies that are doing a billion ARR

</details>

**Chamath Palihapitiya**: 你刚刚说到了这一切中最关键的一点，那就是你必须有可预测的现金流。我认为发生的情况是，当你是一家初创公司时，你通常必须想出如何以颠覆性的价格进入市场。所以你会想，好吧，如果我提供10美元的价值，我就收1美元。这就是常规的策略，比如10%的价格与价值比率，对吧？问题是，当你开始往里面堆积风险资本，然后你又堆积成长型股权，你实际上在公司的优先股结构中创造了一个更高的回报门槛，对吧？你得清除3亿、5亿、10亿的pre-money估值，然后你还得在此基础上回报15%或20%。所以当人们筹集更多资金时，他们会做什么？他们会提高价格。但问题是，在某个时候，当你提高价格时，你会引来大量的竞争，并把一个巨大的靶子放在自己背上。私募股权是最后一站，因为当他们进来并投入数十亿甚至数百亿美元的不仅是股权还有债务时，而这些都必须是完全可预测并得到偿还的。他们唯一的杠杆就是提高价格。他们永远不能为了抢占市场份额而降价。他们不能承担那样的风险来偿还他们的债务持有人。所以Sacks，这里的大问题之一，也是为什么没人想碰这些公司的原因，就是它们定价过高。是的，它们创造了十亿美元的ARR，但单位成本已经失控了。过去可能是价值的10%。现在可能已经是价值的30%了。而且每个人都在看他们的合同，想着，嗯，当续约的时候，我要把这个砍掉一半，或者砍掉三分之二，或者砍掉75%。因为价值已经不在了。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: You just said the absolute critical thing in all of this, which is you have to have predictable cash flows. I think what happens is when you're a startup, you typically have to figure out how to disruptively price to enter the market. So you're like, okay, if I deliver $10 of value, I'm going to charge a dollar. And that's that's the normal playbook, like a 10% ratio, right, of price to value. The problem is when you start to stack venture capital into it and you then you stack growth equity into it, what you're effectively creating in in the preference stack of of your company is that you are creating a a higher return hurdle, right? You got to clear 300 million, 500 million, a billion of pre and then you have to return 15 or 20% on top of that. So what do people do as they raise more money? They increase price. But the problem is at some point when you increase price you engender a ton of competition and you put a huge target on your back. Private equity is the last stop because when they come in and they layer in billions and billions of dollars of not just equity but also debt and that has to then be completely predictable and paid back. Their only lever is to raise price. They can never cut price to take share. They don't they can't underwrite that to pay back their debt holders. And so Saxs, part of the big problem here and why nobody wants to touch these companies is that they are overpriced. Yes, they're making a billion dollars of ARR, but the unit cost has gotten out of control. It used to be 10% of value. It's probably now 30% of value. And everybody's looking at their contracts thinking, well, when it comes time to a renewal, I'm going to to just cut this in half, or I'm going to cut this by 2/3, or I'm going to cut this by 75%. because the value isn't there anymore

</details>

**David Sacks**: 或者他们可以威胁要这么做，并谈判一个更好的交易。

<details>
<summary>Original English</summary>

**David Sacks**: or they can threaten to and negotiate a better deal.

</details>

**Chamath Palihapitiya**: 当你让这些产品无头化，说“我只通过MCP和代理与这些产品通信”，情况就变得更糟了，你不能按席位收费了。那你该怎么办？Freeberg不需要50个Workday的席位。他需要两个席位，因为代理充当了读写Workday的方式。所以，他想为两个席位付费，而不是50个。然后如果你把这个乘以一百万家公司，那就把我们带到了这个感觉像自由落体的地方。我认为这归根结底是单位成本的问题。这些产品的单位成本和价格与价值比已经与市场的需求和愿望脱节了。在他们重置这个，或者你找到能更便宜地做到这一点的新产品之前，我们不会在这里得到清理和清算。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: And it becomes even worse because the minute you make these products headless, right, and you say, "I'm just going to communicate with these products via MCP and with agents, you can't charge on a per seat basis." What do you do then? Freeberg doesn't need 50 seats of, you know, workday. He needs two seats because the agents act as the way to write in and out of workday. So, he wants to pay for two seats, not 50. And then if you multiply that by a million companies, that's what gets us to this place where it just feels like a falling knife. And I think it comes down to these unit costs. The unit costs and the price to value of these products are out of whack with what the market needs and wants. And until they reset that or you find new products that can do it cheaper, we're not going to get a cleansing and a clearing here.

</details>

### 苹果新CEO与未来展望

**Jason Calacanis**: 好的。话题二。私募股权领域有SaaS债务炸弹吗？好吧，让我们快速谈谈Tim Cook辞职和继任的事情。这个人，John Turnis，是一位有25年经验的老将。他做过很多硬件，参与过iPad、AirPods的开发，而且从第一天起他就是Poly Market上的热门人选。据报道，他是一个果断的决策者。与Tim Cook不同，Tim Cook在榨干Steve Jobs产品线最后一分钱方面做得很好，这个产品线持续了十年。iPhone、Apple TV、手表，我不用重复了，但现在我们有了一个产品负责人坐上了这个位置，这是我们都知道他们所需要的，因为嘿，这些工具已经有点过时了。Siri过时了，AirPods过时了，整个系统不再建立在创新之上。它建立在，Freeberg，我想你会同意，只是榨取更多利润，更多利润。你对此有何希望？因为天哪，他们错过了太多好的机会。他们没有做出Meta那样的Oculus，你知道，雷朋眼镜。他们取消了他们的自动驾驶汽车。Freeberg，你希望这位苹果新CEO在创新方面关注什么？他们卖手机仍然没有问题。他们卖笔记本电脑和赚大钱也没有问题。但如果你处在那个位置，如果你在苹果董事会，老实说这对他们来说不是个坏主，你会告诉新CEO关注什么？David Freeberg。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Okay. Topic two. Is there a SAS debt bomb in private equity? All right, listen. Just rapid fire here on the Tim Cook uh resignation and moving on. This guy, John Turnis, is a 25-y year vet. He did lots of hardware, worked on iPad, AirPods, and he was the favorite on Poly Market since day one. He's a bold decision maker according to reports. And unlike Tim Cook, Cook, Tim Cook did a great job of squeezing every last nickel out of Steve Jobs's product line, which lasted for a decade. iPhone, Apple TV, watch, I don't need to repeat them, but here we are. We got a product person in the seat which is what we all know they needed because hey these tools are getting a little bit stale. Siri descriad Airpods discretad the whole uh system is not built on innovation anymore. It's built Freeberg I think you would agree on just ringing more profits more profits. What's your hope here? Because man they missed so many great swings at bat. They didn't get the Oculus, you know, Ray-B bands that Meta did. They cancelled their self-driving car. What would you hope that this new CEO of Apple focuses on Freeberg in terms of innovation? They don't have a problem selling phones still. They don't have a problem selling laptops and making a ton of money. But if you were in the seat, if you were on the board of of Apple, which wouldn't be a bad idea for them if I'm being honest, what would you tell the new CEO to focus on? David Freeber.

</details>

**David Friedberg**: 我的意思是，我不知道。未来的软件层不是过去的软件层。所以，这很明显。我不知道有多少可谈的，但你只需要一个无处不在的Siri替代品，存在于你所有的设备中。知道你是谁，为你个性化，能看到你的邮件，看到你的日历条目，知道你喜欢什么样的音乐，能连接到你的家，基本上为你的生活构建那个AI层，并让它在你所有的苹果设备中无处不在，无论你使用什么设备，它都知道你是谁。你可以用一种自然语言的方式与它互动。而且，你知道，这很明显。

<details>
<summary>Original English</summary>

**David Friedberg**: I mean, I don't know. The software layer of the future is not the software layer of the past. So, okay, it's pretty obvious. I don't know if how much there is to talk about, but you just need the Siri equivalent that's ubiquitous in all of your devices. Knows who you are, personalized to you, sees your email, sees your calendar entries, knows what kind of music you like, has connection to your home, basically build that AI layer for your life and make it ubiquitous in all of your Apple devices that no matter what device you're using, it knows who you are. You can can engage with it using kind of a natural language method. And it's, you know, it's it's pretty obvious.

</details>

**Jason Calacanis**: 是的，他们应该收购Whisper Flow。是的。我的意思是，那将会是……

<details>
<summary>Original English</summary>

**Jason Calacanis**: Yeah, they should buy Whisper Flow. Yeah. I mean, that would be

</details>

**David Sacks**: 嗯，我的意思是，每个人都会问同样的问题，那就是你打算在AI方面做什么？我不知道他们是否需要走在最前沿，但他们总归需要一个答案。**Siri**将需要被AI赋能。可能的方式应该是你可以选择你的模型。我的意思是，我不知道他们是否需要只选择一个模型提供商。这可以是一个设置，你进去用任何聊天GPT、**Grok**或Claude之类的东西设置你的账户，你可以选择自己的模型提供商，然后你将有更多的定制化和更多的能力来控制你的存储。让我只说一句，关于**Tim Cook**的退休，他作为苹果的CEO有着不可思议的职业生涯，我的意思是，他非常有效地运营了15年。公司的市值增长了超过10倍。收入从大约每年1000亿美元增长到超过4000亿美元。他还通过将业务组合转向服务来提高了收入质量，这也是它获得更高估值的部分原因。你知道人们说，他们在Tim Cook的领导下没有做任何创新，但你知道，我见过人们在推特上列出在他领导下发布的产品清单，其中有很多。现在，确实没有像iPhone那么大的东西，但他们在Tim Cook的领导下确实发布了很多产品。最后，我的意思是，你回顾过去15年，苹果真的没有任何公开的失误或丑闻。它是少数几个仍然受到大众喜爱的科技品牌之一。我认为其中一个主要部分是Tim Cook对隐私的执着，并让公司在这方面站在了正确的一边，我认为用户确实很感激。而且你知道，他甚至Tim Cook甚至得到了总统的赞扬。而且我认为那只是未经请求的，总统谈到Tim Cook不常给他打电话，但当他打电话时，都是些重要的事情，因此总统试图帮助他们。看起来他在过去十年左右与总统培养了良好的关系。所以你不得不说，他以极大的优雅和风度驾驭了一个可能动荡的时期。

<details>
<summary>Original English</summary>

**David Sacks**: Well, I mean, everybody is going to be asking the same question, which is what are you going to do about AI? I don't know that they needed to be on the bleeding edge of it, but they are going to need an answer at some point. And Siri is going to need to be AI empowered. Probably the way it should work is that you get to choose your your model. I mean, I don't know that they need to pick just one model provider. It could be a setting where you go in and you set up your account with whatever chat GPT or Grock or Claude or what have you and you can choose your own model provider and then you'll have more customization and more ability to control your your storage. Let me just say just on Tim Cook's retirement, he had an incredible run as CEO of of Apple, I mean he ran it very effectively for 15 years. The market cap of the company went up by over 10x. the revenue grew from roughly 100 billion a year to over 400 billion a year. He also improved the quality of revenue by by moving the mix into services which is partly why it got why it got a higher valuation and you know people say that well they never did any innovation under Tim Cook but you know I've seen people tweet lists of products that were released under him and there were a lot of them now it's true nothing as big as the iPhone but they did release a lot of products under Tim Cook and then just finally I mean you you look back over the last 15 years and there really weren't any public snafuss or scandals or brogleos with with Apple. It's one of the few tech brands that is still I think beloved by the population. I think a major part of that was Tim Cook's dedication to privacy and keeping the company on the right side of that which I think users do appreciate. And you know he even Tim Cook even got praise from the president. And I think it was just unsolicited where the president talked about how Tim Cook didn't call him up that often, but when he did it it was something important and therefore the president tried to help them out. Seems like he nurtured a good relationship with the president over over the last decade or so. So you just have to say that he navigated what could have been a turbulent period with a a great deal of grace and appl.

</details>

### 南方贫困法律中心(SPLC)遭起诉

**Jason Calacanis**: Racism Corner。我们去“假装有种族主义”角吧。我想知道**SPLC**是如何在离岸银行账户里积累了8.22亿美元的。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Racism Corner. Let's go to race fake fake racism corner. I want to know how the SPLC managed to accumulate $822 million in offshore bank accounts.

</details>

**Chamath Palihapitiya**: 是的，这太不可思议了。这些数字很大。好的，SPLC。这怎么可能？到底发生了什么？

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah, this is incredible. These are big numbers. Okay, SPLC. How is that possible? What is going on?

</details>

**Jason Calacanis**: 这真是个大新闻。SPLC已经被起诉了。注意，是起诉，还没被判有罪，罪名是11项电信欺诈和洗钱。记住这一点。电信欺诈和洗钱。核心指控是：在2014年到2023年间，南方贫困法律中心利用隐藏的银行账户，将300万美元的捐款 funnel 给了付费线人。就像警察或FBI可能使用的机密线人一样。他们作为非营利组织使用这些线人来渗透仇恨团体。SPLC的官方使命是“成为南方及其他地区种族正义的催化剂，与社区合作，瓦解白人至上主义，加强跨领域运动，并促进所有人的**人权**。”好的，纸面上听起来很棒。他们试图渗透的组织例子有：**三K党(KKK)**、**雅利安国(Aryan Nation)**、新纳粹团体，以及“团结右翼”活动的组织者，**骄傲男孩(Proud Boys)**，被SPLC标记为仇恨团体。**守誓者(Oathkeepers)**，没有被列为仇恨团体，但属于民兵运动的一部分。我的朋友**Sam Harris**，他没有被列为仇恨团体，但也被SPLC在他的“仇恨观察”头条中钉为“仇恨邻近”。这是我对这个组织有重大问题的地方，他们会非常松散地给人们贴上仇恨言论的标签，并试图让他们被封杀。所有这一切都在夏洛茨维尔事件之前达到了高潮。你还记得那个被错误剪辑的夏洛茨维尔骗局，他们说特朗普说双方都有好人，但他们没有给出他的完整引述。对特朗普总统非常不公平。我们后来才发现，而那当然是拜登参选的原因。他说夏洛茨维尔“双方”事件是他的灵感来源。2026年收入5800万美元，到你说的，Chamath，翻倍并飙升到1.36亿美元，是原来的两倍多，并且此后一直保持高位。这里有一些起诉书的图片。我最后总结一下，然后听取大家的反馈。他们有一个代号为F37的机密线人。根据起诉书，他是“策划2017年弗吉尼亚州夏洛茨维尔‘团结右翼’活动的在线领导聊天组的成员，并在SPLC的指示下参加了该活动。” F-37在SPLC的监督下发布了种族主义言论，并帮助协调了几位与会者前往该活动的交通。在2015年到2023年间，SPLC秘密向F-37支付了超过27万美元。这就是这里的法律案件。我先说到这里。

<details>
<summary>Original English</summary>

**Jason Calacanis**: This is a big one. SPLC has been indicted. Indicted, not found guilty yet, on 11 counts of wire fraud and money laundering. Keep that in the back of your head. Wire fraud and money laundering. Here's the core allegation. Between 2014 and 2023, the Southern Poverty Law Center used hidden bank accounts to funnel 3 million in donor money to paid informants. Like these are confidential informants like the police or FBI might use. They use these as a nonprofit NGO to infiltrate hate groups. And so the official mission of the SPLC is quote to be a catalyst for racial justice in the South and beyond, working in partnership with communities to dismantle white supremacy, strengthen intersectional movements, and advance the human rights of all people. Okay, sounds great on paper. Examples of organizations they were trying to infiltrate, KKK, Aryan Nation, neo-Nazi groups, and the Unite the Right organizers, Proud Boys, labeled as a hate group by the SPLC. Oathkeepers, not listed as a hate group, but part of the the militia movement. My friend Sam Harris, he was not listed as a hate group, but he was also pinned by the SPLC as like hate adjacent in their hate watch headlines. And this is something that I had a major problem with this organization on, which is they would just very loosely label people as hate speech and try to get them cancelled. All of this kind of uh came to a head. revenue before Charlottesville. You remember the incorrectly clipped uh Charlottesville hoax where they said Trump said both good people on both sides, but they didn't give his full quote. Very unfair to President Trump. Uh we found out later and that was the reason Biden of course ran. He said the Charlottesville both sides thing was his inspiration. 58 million in 2026 to your point Shimoth doubled and spiked to 136 million more than double and it's remained elevated ever since. Here are some, you know, images for the indictment. And I'll wrap on this and then get everybody's uh feedback. They had F37 as one of their confidential informants. He was a member, and this is according to the indictment, quote, member of the online leadership chat group that planned the 2017 Unite the Right event in Charlottesville, Virginia, and attended the event at the direction of the SPLC. F-37 made racist postings under the supervision of the SPLC and helped coordinate transportation to the event for several attendees between 2015 and 2023. The SPLC secretly paid F-37 more than $270,000. That's the legal case here. Let me pause there.

</details>

**David Sacks**: 是的。所以，你说得对，SPLC据称资助了27万美元来帮助策划夏洛茨维尔事件。除此之外，他们还秘密地向一系列暴力的种族主义极端组织输送了超过300万美元的资金，包括三K党、美国纳粹党、雅利安国、美国联合部落等，名单还在继续。所以，我认为别忘了那300万美元。所以这个本应打击种族主义的组织，实际上通过付钱给这些团体来煽动种族主义，基本上是组织抗议活动，然后SPLC可以指着这些活动说美国有巨大的种族主义问题，请给我们捐款。这基本上就是夏洛茨维尔事件后发生的事情。他们能够筹集的资金增加了8100万美元。所以那27万美元的投资带来了8100万美元的回报。相当不错。但这正是整个故事的关键，这些家伙基本上是在搞诈骗。你知道这是诈骗的一种方式是，根据起诉书，他们以虚构实体的名义开设银行账户，以向他们自己的捐赠者隐瞒他们所做的付款，因为如果他们的捐赠者知道他们在资助三K党，他们就不会得到好莱坞名人和所有其他人的这些捐款了。所以，这真是一个令人难以置信的故事。

<details>
<summary>Original English</summary>

**David Sacks**: Yeah. So, you're right that the SPLC allegedly did fund $270,000 to help plan Charlottesville. In addition to that, they secretly funneled more than $3 million to a bunch of violent racist extremist groups, including the Ku Klux Clan, the American Nazi Party, Aryan Nation, United Clans of America, and it goes on from there. So, I think don't forget about the 3 million bucks. So this group that was supposed to be fighting racism in fact was fermenting racism by paying these groups to basically organize protests that SPLC could then point to and say that America has a huge racism problem donate to us. And that's basically what happened after Charlottesville. They increased the amount of money that they were able to fund raise by $81 million. So that $270,000 investment led to an $81 million return. pretty good. But this is kind of the whole point of the story is that these guys are basically running a grift. And one of the ways that you know this is a grift is because according to the indictment that they opened bank accounts under fictitious entities to conceal the payments that they were making from their own donors because if if their donors knew that they were funding the KKK, they wouldn't be getting all these contributions from Hollywood celebrities and all the rest of it. So, it's really just this unbelievable story.

</details>

**Chamath Palihapitiya**: 这些非政府组织已经完全失控了，他们扮演着我们生活中的霸主和权力掮客，这必须被制止。他们都应该被解散。那些向SPLC捐款的人应该起诉他们，撕开所有的文件，拿回他们的钱，因为你们要知道，如果你在听或在看，并且你捐过款，有8.22亿美元的你的钱正躺在一个离岸银行账户里等着你拿回去。好的？然后，另外，如果你将来考虑向这些组织中的任何一个捐款，除非有完全透明的审计，否则你实际上可能在做与你想象中相反的事情。如果你反对种族主义，你可能在支持种族主义。如果你反对对同性恋的歧视，这可能实际上在促进对同性恋的歧视。如果你支持跨性别者的权利，这可能在阻碍跨性别者的权利，因为这个剧本似乎是做相反的事情来创造叙事，把它交给媒体里的朋友，他们会视而不见并放大它，撒谎，制造混乱，然后筹集一大笔钱，制造一大堆麻烦，并试图策划权力。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: these NOS's have completely run a muck they're are cosplaying as these overlords and power brokers in our lives and it needs to get stopped they should all be dismantled the people that donated to the SPLC should sue them rip open all of the documentation get their money back because just so you guys know if you are listening or watching and you have donated there is 822 million dollar of your money sitting in an offshore bank account waiting for you to get it back. Okay? And then separately, if you are thinking of donating to any of these organizations in the future, unless there is a full transparent auditing of of it, you actually may be doing the opposite of what you thought. If you are against racism, you may be supporting racism. If you are against discrimination for gays, this could be actually promoting discrimination for for gays. If you are supportive of trans rights, this may be pushing back against trans rights because the playbook seems to be do the opposite to create the narrative, give it to your friends in the media who will look the other way and just amplify it, tell the lie, create the craziness, and then raise a a bunch of money, make a bunch of stink, and try to curate power.

</details>

**David Friedberg**: 美国国税局对501(c)(3)非营利组织的定义是从事豁免活动。豁免活动的定义是慈善、宗教、教育、科学、扫盲、公共安全、促进业余体育竞赛或防止虐待儿童或动物。你告诉我，我们今天称之为非营利组织的90%是如何符合这个定义的。我们完全对这样一个事实视而不见：这些组织，无论其政治派别、社会利益如何，都具有根本性的商业利益，并且可能与501(c)(3)的定义不符。我们让它们逍遥法外太久了。我不认为这是蓝色或红色的问题。我认为这是一个问题，我们让这些组织轻易获得资金，隐藏资金，并随心所欲地使用资金。我们需要制止这种情况。我认为现在是一个绝佳的机会，让每个人都通过清理所有这些烂摊子来重新洗牌，让所有这些组织被冲刷干净，并确保任何想做任何邪恶事情的组织，尽管去做。但它不是一个非营利组织，你不应该获得慈善捐赠扣除，政府也不应该向这类事情投入资金。这在社会秩序中是完全不同的一种活动。作为一个自由意志主义者，我完全支持。但我不认为他们应该免税。我也不认为他们应该得到政府的钱。我也不认为个人应该从给他们钱中受益。如果我们能把所有这些烂摊子都解决了，我认为很多这些问题都会消失。我认为这是一个主要问题。我认为这一集的主题是审计一切。无论是政府的浪费和滥用，还是这些非政府组织，或者是像陶氏化学这样制造这些化学品，30年后可能与癌症相关的人。我们需要审计一切。我们需要以全新的眼光看待这件事，因为这不是红对绿。红，这不是红对蓝，这是绿。这显然是一个金钱激励，而对于社会来说，不知道这个国家种族问题的真相是极具破坏性的。

<details>
<summary>Original English</summary>

**David Friedberg**: the IRS definition of what a 501c3 nonprofit organization is meant to be doing is to engage engage in exempt activities. The definition of exempt activities is charitable, religious, educational, scientific, literacy, public safety, or fostering amateur sports competition or preventing cruelty to children or animals. You tell me how the 90% of what we call nonprofits today fall under that definition. We have completely closed our eyes to the fact that organizations regardless of of political affiliation, social interest, have fundamental commercial and probably not aligned interests with the definition of a 501c3. And we've allowed them all to get away with it for far too long. I don't think that this is a blue or red thing. I think that this is a thing where we let these organizations make it easy to get money, to hide the money, and to do whatever the hell they want with the money. and we need to stop it. And I think that it's an amazing opportunity right now for everyone to kind of reset the decks by cleaning all this [ __ ] up and getting all of these organizations flushed and make sure that any organization that wants to do whatever [ __ ] nefarious things they want to do, by all means do it. But it's not a nonprofit and you shouldn't get a a charitable donation deduction and the government should not be putting money into these sorts of things. This is an entirely different sort of activity in the social order. And as a libertarian, I'm all for it. But I don't think that they should be taxexempt. And I don't think they should be getting government money. And I don't think that individuals should be benefiting from from giving them money. And if we could fix all that [ __ ] up, I think a lot of of these problems are going to go away. And I think this is a major problem. I think the theme of this episode is audit everything. Whether it's government waste and abuse or it's these NOS's or it's people like Dao making these chemicals that 30 years later, you know, perhaps are correlated with cancer. We need to audit everything. We need to take a fresh look at this because it's not red versus green. Red, this is not red versus blue, it's green. This is is clearly a monetary incentive and it is incredibly disruptive for society to not know the truth about what's going on with race in this country.

</details>

**David Sacks**: 这是一个系统性问题，关于非营利组织和非政府组织。让我与商业作个对比。在商业中，你成立一家公司。公司必须创造收入，必须盈利。如果做不到，它就会倒闭，对吧？因为它会亏损。所以，市场有一个反馈机制。公司必须创造人们愿意购买的产品，而这些产品必须能赚钱。而对于一个非政府组织、非营利组织，随便你怎么称呼，他们筹集资金。他们不卖东西。他们从捐赠者那里筹集资金，以从事某项活动。但随着时间的推移，实际的活动可能变得不再重要。而真正重要的只是他们能够继续筹款，对吧？因为他们只是想找个理由继续向捐赠者要钱，从他们那里得到越来越多的钱。这就是维持这个组织的方式。

<details>
<summary>Original English</summary>

**David Sacks**: Listen, here's here's the systemic problem with nonprofits and NOS's is, and let me just contrast it with business. In business, you set up a company. The company has to make revenue. It has to make profits. And if it doesn't, it's going to to go out of business, right? Because it'll lose money. So, there's a feedback mechanism from the market. The company has to create products that people are willing to buy, and those products have to make money. With an NGO, nonprofit, what have you, they raise money. They don't sell things. They fund raise from donors in in order to engage in an activity. But what what happens over time is the actual activities may stop mattering. And all that really matters is they're able to keep fundraising, right? Because they're just trying to figure out a justification to keep going back to donors to get more and more money out of them. That's what perpetuates the organization

</details>

### 科学角：结直肠癌飙升的可能原因

**David Friedberg**: 是的，这不一定是个大惊喜，但本周发表了一篇非常有趣的论文，试图阐明结直肠癌的根本原因或预测因素。所以，我不知道你们是否认识年轻的朋友，但结直肠癌，尼克，如果你能拉出第一张图片，或者说结肠癌，现在已经成为第三大癌症。在过去20年左右，年轻人，通常是50岁以下的人患结肠癌的数量出现了可怕的增长。这个数字在过去二十年里增长了超过80%。历史上，这是一种与年龄相关的疾病。所以，当你变老，超过70岁，你得结肠癌的概率会急剧上升。但年轻人得结肠癌的这种增长相当惊人。一个真正的问题是，是什么原因造成的？根本的诱因是什么？所以，这个来自西班牙巴塞罗那的研究团队做了一项了不起的研究，他们研究了50岁以下患者和70岁以上患者肿瘤细胞中表观基因组或基因表达的差异。这类数据会告诉你哪些不同的环境诱因与那些基因表达的变化相关联。所以，每当我们接触到环境中的某种东西，无论是某种食物、饮料或其他任何东西，环境中的某种化学物质，我们体内接触到那种化学物质或环境诱因的细胞，其基因会被开启和关闭。你可以通过观察这些基因的RNA来看哪些基因是开启的，哪些是关闭的，这告诉你那些基因是否在表达RNA来制造蛋白质。你可以观察基因表达来确定当一个细胞暴露于特定环境诱因时发生了什么变化。所以他们能够从由联邦政府资助的癌症基因组图谱中获得这些结肠腺癌的样本。然后他们能够研究这些来自50岁以下和70岁以上患者的结肠癌细胞，观察基因表达谱的差异以及哪些环境诱因与该基因表达谱相关联。所以这会告诉你，嘿，这些环境诱因更有可能是导致这种结肠癌风险的根本原因或驱动因素。有一件事脱颖而出。他们研究了很多东西。他们研究了生活方式因素。他们研究了饮食指数、你吃了多少、你有多超重、酒精、出生体重。他们对性别进行了调整。他们对所有这些不同的东西进行了调整。当你向下看这个列表时，你会看到这是70岁以上患结肠癌的人（通常你得病几率很高）和50岁以下的人（通常你不会得病）之间的差异。50岁以下的人到底怎么了？你可以看到这里有一行全是橙色的。那一行是一种叫做**piclorum**的农药。Piclorum是**陶氏化学公司**在1963年开发的一种农药。这是该农药的化学式。它与植物制造的激素——生长素有关。在1960年代，有一股热潮，试图制造合成植物激素，然后你将它施用于植物。它会导致植物过度生长，然后植物很快死亡。Piclorum成为我们环境中一种非常广泛使用的除草剂。它用于管理牛群放牧的牧场和草地的杂草。它用于控制道路和铁路附近的杂草，在工业区清除高速公路和公用事业走廊的杂草。而piclorum的一个问题，其中一个已知的问题是它非常持久。它不能很好地生物降解。Piclorum会存留一年多。它留在水中。它会进入地下水，并且在使用一段时间后会持续存在于环境中。我回去查了环保局关于这种化学品的数据。上一次环保局进行安全研究是在1995年。那是在我们有能力进行像刚才那样的表观基因组研究之前，以阐明即使一种化学物质可能不会立即导致癌症，你也不能将它应用于细胞并看到它引发癌症，但长期使用或暴露于我们环境中的某些化学物质会导致表观基因组的变化，这意味着这些基因被开启和关闭。当某些基因以错误的方式被开启或关闭时，它会引发组织中的细胞开始功能失调并失控，最终导致癌症。我认为这篇论文显示了piclorum在驱动年轻人结肠癌方面的相当强烈的影响。它很可能会导致，也应该导致环保局对这是否应该被合法允许进行审查。但它也应该导致一种新的机制，我们用它来评估我们用于食品供应、环境、工业应用中的化学物质，因为我们现在可以查看所有这类表观基因组数据，以试图在我们看到它们引起问题之前弄清楚这些化学物质对我们做了什么。所以我认为这是这个团队完成的一篇了不起的论文。他们做了大量工作来确保他们所做研究的统计数据是可靠的。它真的，我认为，阐明了一些非常可怕的事情。

<details>
<summary>Original English</summary>

**David Friedberg**: Yeah, this is not necessarily a big surprise, but there was a really interesting paper published this week on trying to elucidate the underlying cause or predictor of colorctal cancer. So, I don't know if you guys know any young friends, but colurectal cancer, Nick, if you could just pull up this first image or colon cancer has become now the third leading cancer. Over the last 20 years or so, there's been a scary rise in the number of young people, people generally under 50 years old that are getting colon cancer. That number has climbed by by over 80% in just the last two decades. Historically, it's been an age related disease. So, as you get older, over 70 years old, your probability of getting colon cancer shoots through the roof. But this rise in young people getting colon cancer has been pretty alarming. And there's been a real question mark on what is causing it. what's the underlying trigger? So, this research team out of Barcelona in Spain did an amazing study where they looked at the the difference in the epiggenome or the gene expression in tumor cells of patients that are under 50 years old and those that are are over 70 years old. the sort of data will show you what different environmental triggers are associated with those changes in gene expression. So whenever we're exposed to something in the environment, whether it's some food or some drink or whatever else it is, some chemical in the environment, the cells in our body that are exposed to that chemistry or exposed to that environmental trigger, have genes that get switched on and off. And you can see which genes are on and off by looking at the RNA of those genes, which tells you that those genes are expressing RNA to make protein or not make protein. And you can look at that gene expression to determine what is changing when a cell is exposed to a particular environmental trigger. And so they were able to get these samples of colon edinocinomas from the cancer genome atlas, which is funded by the federal government. And they were then able to take a look at these cancer cells from colon cancer in patients that are under 50 and patients that are over 70 and look at the difference in the gene expression profile and what um environmental triggers are associated with that gene expression profile. So that will tell you, hey, these environmental triggers are more likely the cause or an underlying driver of the risk of getting this colon cancer. And one thing rose to the top. So they looked at a whole bunch of things. They looked at lifestyle factors. They look at eating index, how much you ate, how overweight you were, alcohol, birth weight. They adjusted for gender. They adjusted for all these different things. And as you look down this list, you'll see this is the difference between people that got colon cancer that were over 70 when you typically have a very high chance of of getting it and people that are under 50 when you don't. And what is going on with people under 50. And you can see there's this one row here that's all orange. That row is a pesticide called piclorum. Plorum is a pesticide that was developed by the DAO Chemical Company in 1963. This is the chemical formula for that pesticide. It's related to oxin, which are these hormones that plants make. And in the 1960s, there was this big rush to try and make synthetic plant hormones that you would then apply to a plant. It would cause the plant to overgrow and the plant would quickly die. And piclorum became a very widely used herbicide in our environment. It's used to manage weeds in rangeand and pasture land where cattle graze. It's used to control weeds near roads and near railroads on industrial sites to clear weeds away from highways and utility corridors. And the problem with piclorum, one of the the things that's been known about it is it's very persistent. It doesn't biodegrade very well. Plorum sticks around for well over a year. It stays in the water. It moves into groundwater and it's persistently in the environment after it's been used for some period of of time. I went back and looked at the EPA data on this chemical. The last time there was an EPA safety study done was was in 1995. And so this was before we had this capacity to do epigenomic studies like what was just done to elucidate that even though a chemical might not be causing cancer immediately and you can't apply it to a cell and see it trigger a cancer, the long-term use or exposure to certain chemicals in our environment causes a change in the epiggenome, which means that these genes are being turned on and off. And when certain genes are turned on or off in the wrong way, it can trigger cells in the tissue to start to malfunction and go haywire and and ultimately lead to cancer. And I think that this paper shows a pretty strong effect of piclorum in driving colon cancer in young people. It will very likely lead and it should lead to an EPA review on whether this should be legally allowed. But it should also lead to a a new mechanism by which we assess chemistry that we're using in our food supply, in our environment, in our industrial applications because we can can now look at all of this sort of epigenomic data to try and figure out what are these chemicals doing to us before we see them cause the problem. So I thought this was like an amazing paper done by this team. They did a lot of work to try and make sure that the statistics were sound in the studies that they did. It really uh I think elucidated something pretty scary.

</details>

**Chamath Palihapitiya**: 这是一个很好的问题，Shimat。所以，我正要谈这个。谢谢你问。他们然后把那种piclorum暴露，然后他们查看了美国所有的县。他们能够收集到加利福尼亚、康涅狄格、佐治亚、爱荷华、新墨西哥、犹他、华盛顿有足够数据的地方的数据，他们能够从农药国家综合项目中查看pllorum的使用估计，并试图推断出在piclorum使用频繁和不频繁的地方。再次，它阐明了信号，即当pllorum在环境中更频繁地使用时，那些县的结肠癌频率要高得多。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah. Sorry, that's a that's a great question, Shimat. So, I was going to talk about this. Thank you for asking that. They then took that piclorum exposure and then they looked at all the counties across the United States. They were able to gather data where there's enough data in California, Connecticut, Georgia, Iowa, New Mexico, Utah, Washington and they were able to look at pllorum use estimates from the pesticide national synthesis project and try and deduce in places where piclorum was highly used and not highly used. And once again it elucidated signal which is that when pllorum was used in the environment in the counties more frequently there was a much higher frequency of colon cancer in those counties

</details>

**David Sacks**: 合理地强，风险比大概是3倍，非常强。

<details>
<summary>Original English</summary>

**David Sacks**: reasonably strong the odds ratio is like 3x it's very strong

</details>

**David Friedberg**: 是的。所以，我戴上我的PCAST帽子。谢谢你，David Sachs，给我这个角色。我认为这说明了政府在做基础科学和基础研究方面的一个重要角色。所以国家癌症研究所和联邦政府几年前用1亿美元建立了这个基因组图谱。他们现在每年只花几百万美元来维护它，获取癌症组织样本，然后为科学家提供使用这些癌症组织样本进行表观基因组分析和研究的可能性，这些研究由政府拨款支持，或者在这种情况下，由一个外国大学获得资金来做。所以，基础科学在阐明这一点上仍然扮演着重要角色，如果我们没有联邦政府和联邦资助的科学项目提供给我们的这个资源，我们本来是无法看到的。这导致了这个发现。你不需要花哨的AI来做这个。坦白说，JCL，有大量的数据和资源是可用的。过去几年发生的事情叫做RNA测序，你可以实际看到哪些基因是开启的或关闭的。不仅仅是DNA是什么，而是在DNA中。记住我们已经谈了很多关于表观基因组，哪些基因是开启的或关闭的，以及当你患有不同癌症或接触不同化学物质时，这会如何改变。当你接触像pllorum这样的特定化学物质时，你的结直肠癌风险会急剧上升，你可以在那些组织中看到这种关系，然后你可以把所有数据放在一起说，哦，天哪，这里有很多证据指向这种联系，非常有力。我认为重要的是，它打开了一扇窗，这不应该只是一个由西班牙团队进行的一次性研究项目，而可能应该是一些政府机构扮演的基础角色，那就是阻止美国人和全世界得癌症。让我们找出我们在工业中做错的事情，然后回去把它们从我们的食物供应和工业供应中删除。嗯，我认为这是一个非常好的例子。

<details>
<summary>Original English</summary>

**David Friedberg**: Yeah. So, I'll I'll put my PCAST hat on. Thank you, David Saxs, for the role. And I think this speaks to one of the important roles that government has in in doing fundamental science and fundamental research. So the the National Cancer Institute and the federal government stood up this genome atlas with $100 million a couple years ago. They spend only a few million dollars a year now to maintain it to get cancer tissue samples and then create the availability to scientists to use those cancer tissue samples to do the sort of epigenomic analysis and study supported by you know government grants or in this case supported by a foreign university getting funding to do it. And so there's there's an important role that fundamental science still has in elucidating this that we would have otherwise not been able to see if we didn't have this resource available to to us from the federal government and federal funding of scientific programs like this. And that leads to this discovery. You don't need fancy AI for for this. To be frank, JCL, there's an incredible amount of data that's available or or resources that are available. What's happened in the last couple years is what's called RNA sequencing where you can actually look at which genes are on or off. not just what's the DNA but in the DNA. Remember we've talked a lot about the epiggenome what genes are on or off and how that that changes when you have different cancers or when you have different chemicals and when you have a certain chemical like pllorum your colorctal cancer goes through the roof and you can see that relationship in those tissues and then you can put all the data together and say oh my gosh there's a lot of evidence here that points to this connection very powerful I think it's important that it opens up the window that this shouldn't just be a one-off research project conducted by a team in Spain but maybe should be a fundamental role that some of the government agencies play, which which is to stop Americans and the world from getting faking cancer. Let's figure out the things that we got wrong in industry and go back and delete them out of our food supply and out of our industrial supply. Um, and I think this is a really good example of that.

</details>

**Jason Calacanis**: 好的，各位。这就是全世界最伟大的播客第270期的全部内容。我是你们全世界最伟大的主持人。感谢Chimoff Hatia，David Saxs和David Freeberg带来的这期节目。告诉你的朋友，你的邻居，我们下次再见。再见。

<details>
<summary>Original English</summary>

**Jason Calacanis**: All right, everybody. That's it for episode 270 of the world's greatest podcast. I am your world's greatest moderator. Thank you, Chimoff Hatia, David Saxs, and David Freeberg for the episode. To your friends, your neighbors, and we'll see you all next time. Bye-bye.

</details>