---
author: Bloomberg Podcasts
date: '2026-03-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=NRLNO_KOh9I
speaker: Bloomberg Podcasts
tags:
  - high-frequency-trading
  - market-structure
  - speed-race
  - diminishing-returns
  - artificial-intelligence
title: 交易速度如何接近光速？高频交易的社会学视角与AI时代的军备竞赛
summary: 本期Odd Lots播客邀请社会学教授Donald McKenzie，深入探讨高频交易（HFT）如何将交易速度推向光速极限。McKenzie教授从社会学视角分析了HFT的演变、市场结构、银行在其中的角色，以及速度军备竞赛的经济和社会影响。他指出，HFT的成功在于利用市场结构而非算法本身，并揭示了“做市商”与“流动性攫取者”之间的动态。最后，他将HFT的速度竞赛与当前AI模型训练的规模化挑战进行类比，探讨了技术进步与边际效益递减的哲学问题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - NASDAQ
  - New York Stock Exchange
  - Spread Networks
  - OpenAI
products_models:
  - Island
  - Archipelago
media_books:
  - An Engine Not a Camera
  - Trading at the Speed of Light
  - 'A Tenth of a Second: A History'
status: evergreen
---
### 播客开场与高频交易

**Joe Weisenthal**: 大家好，欢迎收听新一期的OddLots播客。我是Joe Weisenthal。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Hello and welcome to another episode of the OddLots podcast. I'm Joe Weisenthal.

</details>

**Tracy Alloway**: 我是Tracy Alloway。Joe，我认为我们这个播客喜欢做的一件事，就是解构那些我们习以为常的事物。世界上有很多过程，我们总是说，当出现某种“爆炸”或问题时，我们才会注意到X或Y，这说明一定有什么事情正在发生。但我们不必总是等到出问题。我们生活在一个你点击按钮，事情就会发生的世界，你对点击按钮后会发生什么有一些直觉，但对从点击按钮到事情发生之间究竟发生了什么，你并没有很好的直觉。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And I'm Tracy Aloway. Tracy, one of the things that I think we like to do on this podcast is sort of deabstract the things that we take for granted in the world. And there are various processes. We always say this when there's like a blowup or something like that where it's like, oh, if we're having to pay attention to X or Y, there must be something going on. But we don't always have to wait for blow-ups. But like we live in this world where like you click buttons and things happen and you have some intuition of what happens after the button is clicked, but you don't really have a great intuition of like what happens between the button clicking and the thing happening.

</details>

**Joe Weisenthal**: 没错。我其实不知道输入一个股票交易的流程具体是如何运作的，它最终会出现在哪里。这是一个大问题。我怀疑很多人，即使是市场里的人，可能也不知道整个事件序列。部分原因是这些年随着像 **Reg NMS** 这样的法规，它变得更加复杂了。你还记得吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Absolutely. I actually don't know how the process of like inputting an equities trade actually works like where it kind of shows up. So that's a big question. And I suspect a lot of people, even people who are in markets, probably don't know like the entire sequence of events. Partly because it's gotten more complicated over the years with like regg NMS. Do you remember that and stuff like that?

</details>

**Tracy Alloway**: 我对交易的另一个认识是，显然，这里的大趋势是**高频交易**（HFT），对吧？它变得越来越快。当我们大约在2000年代中期金融危机后开始撰写关于HFT的文章时，我记得当时认为这完全是关于算法本身，以及在金融市场中找到一个真正聪明的模式来利用。但我了解得越多，读得越多，就越意识到它并非如此。它关乎利用市场结构。

<details>
<summary>Original English</summary>

**Tracy Alloway**: The other thing I've been realizing about trading, obviously the big trend here is high frequency trading, right? And it's just getting faster and faster and faster. When we first started writing about HFT, I guess in the sort of like mid 2000s after the financial crisis, I remember thinking that it was all about the actual algorithm and finding like a really smart pattern in financial markets to exploit. But the more I learn about it and the more I read about it, I kind of realize it's not really that. It's about exploiting the market structure.

</details>

**Joe Weisenthal**: 是的，没错，完全正确。而且有很多，你知道，我们最近和谁聊来着？哦，是 **Hudson River Trading** 的那个人。你知道，有著名的“电线战争”，就是“不，我想离主服务器近一英寸”，等等。这就像是，“天哪，这是对脑力的良好利用吗？”所以，我们即将解决市场问题，因为速度又快了一纳秒，等等。但你知道，另一件事，与此相关，我长期以来的一个问题是，一份就业报告会在周五早上8:30发布，市场会立即做出反应。我就想，这怎么发生的？因为它不是因为有人盯着屏幕，手指放在买入或卖出按钮上而发生的，而是必须通过编程，让数据能够即时被吸收，然后基于此做出某种方向性交易。但我不知道那怎么发生，我不知道那怎么运作。当然，还有一个总体问题是，所有这些电子交易对市场本身到底意味着什么。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. Yeah. Totally. And there are so many, you know, we we had that I forget who we were talking to recently. Oh, it was the guy from Hudson River trading and you know, there were the famous like wire wars where it's like, no, I want to be one inch closer to the main server, etc. It's like, god, this is like a good use of brain power. So, like we're going to solve the market because one more nancond faster, etc. But, you know, the other thing, you know, sort of related to this, one of my long-standing questions is, you know, a jobs report will drop at 8:30 on a Friday and the market immediately moves. And I'm like, how did that happen? Because it didn't happen because someone was staring, they had their like fingers above the buy or the sell button, but also had something had to be programmed such that that data could instantly be ingested and then some sort of like directional trade was made based on that. But I don't know how that happens. I don't know how that works. There's also of course the overall question of what all this electronic trading actually means for the market itself.

</details>

**Tracy Alloway**: 是的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yes.

</details>

**Joe Weisenthal**: 人们谈论多策略基金的反馈循环，以及可能增加市场波动性等问题。所以我们应该讨论一下。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And people talk about things you know with the multistrat funds getting these feedback loops and maybe increasing volatility in the market and things like that. So we should discuss

</details>

**Tracy Alloway**: 我想再补充一点。你问这对市场本身意味着什么？那么，对于社会本身又意味着什么呢？为什么如此多的精力被投入到比如“离服务器机房近一米”这样的事情上？为什么这是时间的良好利用？这是否改善了资本配置？我很高兴地说，我们确实请到了一位我认为是完美的嘉宾来谈论这个话题，他以其在多个领域非凡的毕生工作而闻名，这与我能想到的几乎任何其他学者或研究员都截然不同。我们将与 **Donald McKenzie** 教授对话。他是苏格兰**爱丁堡大学**的社会学教授。我第一次接触他的作品时，他写了一本很棒的书，叫做《**An Engine Not a Camera**》，这本书是关于金融和量化金融的最初诞生，以及高级模型的使用，以及这些模型如何不仅仅反映现实世界中发生的事情，而是这些模型的采用如何创造了一个反馈循环，即“引擎效应”，从而实际开始驱动市场本身。最近，他写了一本名为《**Trading at the Speed of Light**》的书，全部是关于高频交易的。他最近还写了一本关于数字广告的书。所以，他真的是一个博学多才的人，思考着行业与驱动这些行业的科技基础之间的关系。McKenzie教授，非常感谢您来到OddLots。

<details>
<summary>Original English</summary>

**Tracy Alloway**: and I would just add one more thing. You say what does it mean for the market itself? What does it mean for society itself that so much effort is being placed on like getting a meter closer to the server room or whatever and why is this a good use of time and is this improved capital allocation? I'm really excited to say we do in fact have I think truly the perfect guest to talk about this someone who has a sort of an extraordinary body of life's work in a range of areas that is very distinct from almost any other academic or researcher that I can think of. We're going to be speaking with Donald McKenzie. He's a professor of sociology at the University of Edinburgh in Scotland. I first came across his work. He wrote a fantastic book called An Engine Not a Camera, which is sort of about finance and the original birth of quantitative finance and the use of advanced models and how these models didn't just reflect what was going on in the real world, but how the adoption of these models then created this feedback loop, the engine effect such that it actually started to drive markets themselves. More recently, he wrote a book called Trading at the Speed of Light, all about highfrequency trading. He's also written recently a book about digital advertising. And so truly a a polymath in the world of thinking about this relationship between industry and the sort of technological substrates that drive them. Professor McKenzie, thank you so much for coming on OddLotss.

</details>

**Donald McKenzie**: 嗯，非常感谢你们邀请我。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Well, thank you very much for inviting me to do that.

</details>

### 嘉宾核心研究领域

**Joe Weisenthal**: 没问题。您能先向我们介绍一下您毕生工作的核心理念吗？您的核心兴趣是什么，以至于在这些不同领域都产出了书籍？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Absolutely. Why don't you start off by telling us the gestalt of your life work? What is your core underlying interest such that it's produced books in these various realms?

</details>

**Donald McKenzie**: 是的，我的意思是，从根本上说，我是一名技术社会学家。所以我对影响或可能影响我们所有人的技术系统感兴趣。随着时间的推移，我在这个领域的第一个主要项目是关于**核导弹制导技术**。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, I mean fundamentally I'm a sociologist of technology. So I'm interested in the technical systems that affect or could affect all of us you know so over time uh first major project in that area was on nuclear missile guidance technology.

</details>

**Joe Weisenthal**: 太棒了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Amazing.

</details>

**Donald McKenzie**: 然后我转向了**安全关键计算技术**。接着是您刚才提到的**金融模型**方面的工作。然后是**高频交易**。再然后是**数字广告**，你知道，因为它不仅通过我们不想看到的广告让我们抓狂，当然也是日常数字世界大部分资金的来源。而最近，我开始研究**人工智能**和**大型语言模型**。所以你可以看到，它们都是高度技术化的领域。它们都以这样或那样的方式影响着我们所有人。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Then I moved on to safety critical computing technology. Then the work on financial models that you've just mentioned. Then high frequency trading. Then digital advertising, you know, because as well as driving us all insane by or ads that we don't want to see appearing on our screens, that's also of course the big funding source for much of the everyday digital world. And then most recently of all I've started working on AI and large language models. So you can see that you can see the picture. They're all highly technical areas. One way or the other they all affect all of us.

</details>

### 社会学研究方法

**Tracy Alloway**: 我们想和您交谈的另一个原因是，您总是从社会学的角度看待一切，我非常喜欢人类学家和社会学家去华尔街并撰写相关文章。您为什么选择这种方法，尤其是在您的高频交易书中？

<details>
<summary>Original English</summary>

**Tracy Alloway**: The other reason we wanted to talk to you is because you come at everything from this sociological perspective and I absolutely love it when like anthropologists and sociologists go to Wall Street and write about it. Why did you take that approach especially with your highfrequency trading book?

</details>

**Donald McKenzie**: 是的。我不会做那种量化的社会科学，你知道，例如在市场方面，我把这留给经济学家。我喜欢和人交谈。我喜欢去观察事物，尽可能地去观察。我喜欢追溯事物是如何随时间发展的。你知道，我的工作通常带有一种历史维度。但最有趣的部分不是写书，最有趣的部分是和人交谈。那是我一直以来最享受的部分。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Well, I don't do kind of like quantitative social science, you know, I can leave that for example as far as markets are concerned. I leave that to economists. What I do I like talking to people. I like going looking at stuff to the extent that you can look at it. I like tracing how things have developed through time. you know, my work's often got a kind of, you know, something of a historical dimension to it. But the most fun bit isn't writing the books. The most fun bit is talking to people. And that's the bit I've always enjoyed most.

</details>

**Joe Weisenthal**: Joe，这本书里有一件有趣的事情，我不知道你有没有注意到，但Donald会写下他所有的消息来源数量和他们是谁。比如，交易所的人，高频交易公司的人，他们的资历是什么，这是我以前从未真正见过的。这真是一件很酷的事情。顺便说一句，正如Donald所说，有趣的部分是和人交谈，而不是写书。作为每天都和人交谈但从未写过书的两个人，我觉得，现在当然，我们从未真正经历过写书的过程，因为交谈的部分更有趣。我不想停止交谈。所以，我已经觉得在某种程度上，Donald是我的同类。和人交谈很有趣，不是吗？告诉我们您是如何找到他们的。你知道，就像，HFT对你来说很有趣，你只是想进行一些对话。社会学家的工具箱在这里是用来知道和谁交谈的？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: One interesting thing in this book, Joe, I don't know if you noticed, but Donald writes down like all his numbers of sources and who they are. So like, you know, people from the exchange, people from high frequency trading firms, what their seniority is, which is something I hadn't really seen before. That is a really cool thing. By the way, as Donald says, the fun part is talking to people, not so much the writing of the book. As two people who talk to people every day and have never written the book, I feel already, now granted, we never actually went through the process of writing the book because the talking part is so much more fun. I don't want to ever take a pause from the talking. So, I already feel like to some extent, Donald is a kindred spirit. It's like it's fun to talk to people, isn't it? Talk to us about how you find them. you know, it's like, okay, HFT is interesting to you and like you just want to have some conversations. What is the sociologist's toolkit here for knowing who to talk to?

</details>

**Donald McKenzie**: 是的。这总是很困难，而且总是非常临时的。其中总有很多运气成分。对于金融市场的话题，我通常会开始阅读《**金融时报**》，在《金融时报》中找到名字，然后联系这些人，也许他们会把我介绍给其他人。但是，你知道，正如我所说，也有一些傻运气。我在高频交易方面的工作中有一个关键时刻，就是一开始去采访一个人，他的墙上挂着《**福布斯**》杂志封面的裱框，文章标题是“自由企业来到华尔街”，我想“哦，这听起来很有趣”，我就去查了一下，发现它与一个名为 **Island** 的新电子股票交易所有关。结果发现，Island 的故事与高频交易的故事完全交织在一起。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Well, it's always difficult and it's always very ad hoc. There's always a lot of luck involved in it. And with a financial market topic, I will typically start reading the Financial Times, finding names in the Financial Times, approaching those people, and then maybe they pass me on to other people. But, you know, there's also, as I said, dumb luck involved. like crucial moment in the work I did in high frequency trading was going to interview someone at the start of it and framed on his wall was the front cover of an issue of Forbes with the headline of the article free enterprise comes to Wall Street and I thought oh that sounds kind of interesting and I checked that out and it was to do with a new electronic stock exchange called Ireland And it turned out that Ireland the story of Ireland was completely interwoven with the story of of high frequency trading.

</details>

### HFT公司的文化转变

**Tracy Alloway**: 在我们深入探讨高频交易究竟是什么，以及它如何融入股票、期货或债券的下单过程之前，我有一个文化问题，那就是每当你走进一家HFT公司的办公室，它总是看起来像一家科技公司。对吧，有棋盘和Mac电脑，非常现代。你认为他们为什么采取这种方式？这种美学是如何成为常态的？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Before we get into exactly what high frequency trading is and how it fits into, you know, placing orders for equities or futures or bonds, I have a cultural question which is whenever you go into an HFT firm's office, it always looks like a tech company. Yeah. Right. with the chess board and the mach and very modern like why do you think they've taken that approach? How did that aesthetic become the norm?

</details>

**Donald McKenzie**: 是的，这是一个很好的文化变迁指标，因为在此之前，我们对金融市场的主导印象可能是**纽约证券交易所**的交易大厅。你知道，穿着彩色夹克的人们。他们通常在电视上出现，即使是现在，当市场出现大幅下跌或其他情况时，摄像机也会试图捕捉那些看起来沮丧和担忧的人。所以我们认为那就是金融。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, that's a really good indicator of cultural change because of course previous to that the sort of dominant image we might have of a financial market would be the trading floor of the New York Stock Exchange. You know, folks in colored jackets. They're typically televised when even nowadays when you know so there's been a a big drop in the market or something so the the camera has tried to catch somebody who's looking kind of glum and and worried. So we think of that as what finance is.

</details>

**Joe Weisenthal**: 或者我们想到《**华尔街**》电影中的**Bud Fox**，一群梳着油头的人，你知道，打电话，在锅炉房里。是的，互相大喊大叫，看着绿屏，对吧？抱歉，我不是想打断，但我怀疑人们想象的就是这两种场景。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Or we think about like the Bud Fox in Wall Street of a bunch of guys and slick back hair sort of, you know, on the phone and boiler. Yeah. Yelling at each other looking at a green screen, right? Sorry, I didn't mean to interrupt that, but those are I suspect the two things people imagine.

</details>

**Donald McKenzie**: 是的。是的。你知道，其中涉及一个转变，但总的来说，高频交易公司雇佣的是懂编程的人，通常拥有数学类学科的高级学位，甚至那些自称交易员的人也常常有这样的背景。而且，你知道，我敢肯定，当没有访客在场时，当出现问题时，屏幕前会有很多咒骂。但你说得对，那些交易室的正常体验是安静、有序的，你确实会把它们误认为是硅谷的初创公司。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Yeah. And you know there's was a transition involved but by and large the high frequency trading firms hire people who know how to code often you know with higher degrees in mathematical kinds of subjects and even the people who refer to themselves as traders often have that kind of background. And you know, I'm I'm sure when the visitor isn't there, there'll be a fair bit of swearing at the screen when something goes wrong and and that kind of stuff. But you you're right that the normal experience of those trading rooms, they're quiet, they're orderly, and you could indeed make mistake them for a Silicon Valley startup.

</details>

**Tracy Alloway**: 是的。如果你看到人们穿着牛仔裤，我参观过一家，我好像看到首席执行官，他只是穿着大学T恤或类似的东西。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah. And if you see people in jeans and I I visited one and like I think I saw the CEO and he was just like wearing his like college t-shirt or uh something like that.

</details>

**Donald McKenzie**: 是的。我记忆犹新，因为在之前的工作中，我为《**An Engine Not a Camera**》以及一些后续项目工作时，我经常去投资银行，在投资银行里，你知道，我得穿西装、漂亮的衬衫、打领带等等。所以当我开始采访高频交易公司时，我穿着那身衣服出现在一家公司，公司的老板有点凶地对我说：“你穿得太正式了。”

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. With strong memory I've got because you know in the previous work they work for an engine not a camera and some follow on stuff. I would often go to investment banks and in investment banks you know I kind of had to wear a suit and a nice shirt and a a tie and so on. So when I started interviewing in high frequency trading, I turned up at one firm dressed like that and the owner of the firm sort of snarled at me. You're overdressed.

</details>

**Joe Weisenthal**: 哇。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Wow.

</details>

### Island交易所与速度竞赛的起源

**Tracy Alloway**: 您提到了 **Island**。您能给我们讲讲那个故事吗？我想更多地了解技术等等，但您说，好吧，这最终成为一个交易所。它有什么独特之处？Island是什么？我听说过它，但它又是那种我听说过就没再关注的东西。它有什么独特之处，为什么它与HFT的历史如此交织？它与存在了数百年的其他交易所有什么不同？

<details>
<summary>Original English</summary>

**Tracy Alloway**: You mentioned Island. Why don't you tell us that story? You know, I want to get more into the tech, etc., but you're like, okay, this turned out to be an exchange. What was distinct? What is Island? I've heard of it, but it's again one of these things that I've heard of it and then I moved on. What was distinct about this and why is it so interwoven into the history of HFT? How is it different from other exchanges that have existed for hundreds of years?

</details>

**Donald McKenzie**: 是的。是的。你知道，我当然会过度简化，因为Island之前也有一些与它有点相似的先行者，但我们没有时间深入探讨。我的意思是，从根本上说，在 **Island** 上的交易是围绕一个**电子订单簿**组织的，它列出了所有买入或卖出相关股票的报价。这个电子订单簿由一个叫做**撮合引擎**的东西管理。顾名思义，它会寻找匹配。换句话说，就是以相同价格的买入报价和卖出报价。当它找到这对时，它就会完成交易，交易就完成了。所以这一切都是电子化的。不涉及直接的人工协商。你只需将订单输入订单簿，撮合引擎要么执行它们，要么找不到匹配。在Island之前也有以这种方式运作的交易所。但Island的独特之处在于它的撮合引擎速度极快，以当时的标准来看，也就是1990年代末。最接近的类比是一个叫做**Instanet**的系统，它的撮合引擎可能需要几秒钟才能找到匹配并执行交易。当然，对于一个坐在那里的人来说，即使他们不耐烦，两秒钟也不是很长的时间。Island将这个速度提高了**一千倍**。所以它可以在**2毫秒**内执行交易，也就是千分之二秒。所以，这就是高频交易的开端，有了这样的交易所——我的意思是，严格来说，Island不是交易所，它被称为**电子通信网络**（ECN），但为了简化，我称之为交易所。如果你有这样的交易所，并且你有一个**自动化交易系统**，那简直是天作之合。交易所和交易公司非常非常契合。其中一个结果就是Island的流动性。它交易 **NASDAQ** 股票。当然，这是**互联网泡沫**时期，NASDAQ科技股交易量很大。Island为那个市场带来了大量的流动性。所以，你会得到一种反馈循环，自动化交易为那些具有吸引高频交易的技术特征的交易所带来流动性，使其可行。因此，老牌交易所开始不得不改变他们的运作方式，否则他们就会输给新交易所。这基本上就是今天电子市场形成的反馈循环。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Yeah. You know, I'm going to oversimplify of course because there were predecessors to Ireland that you know were a little bit like it and so on, but that would take us too long to go into. I mean, fundamentally, trading on Ireland was organized around an electronic order book, which was is a list of all the bids to buy or offers to sell the shares in question. And that electronic order book is managed by something called a matching engine. And as the name implies, that looks for a match. In other words, a bid to buy and an offer to sell at the same price. And when it finds that couple, it consummates the trade and the trade is done. So it's all done electronically. There's no direct human negotiation involved. You just enter your orders into the order book and the matching engine either executes them or fails to find a match. There were exchanges prior to Ireland that worked in that kind of way. But what was distinctive about Ireland is that its matching engine was blisteringly fast by the standards of the day which were the you know was essentially the late 1990s. So the closest analog was a system called instant and it might take a couple of seconds the matching engine to find the match and execute the trade. And of course for a human being sitting there even if they're impatient 2 seconds is not a very long time. Island improved on that a thousandfold. So it could execute trades in 2 milliseconds 2000th of a second. So that was the opening for highfrequency trading that with exchange I mean strictly Ireland was not exchange it was what was called an electronic communications network or ECN but I'll call it an exchange for simplicity. If you've got an exchange like that and you've got an automated trading system it's a marriage made in heaven. The two things the exchange and the trading firm fit each other very very well and amongst the consequences of that is that liquidity in Ireland. It traded NASDAQ stocks. This is the time of the dotcom bubble of course where there's a lot of trading of NASDAQ tech stocks. Ireland brought a lot of liquidity to that market. So that's you get a kind of feedback loop where you get automated trading bringing liquidity to exchanges that have the kind of technical features that make high frequency trading attractive and feasible. So the established exchanges started to have to change how they did things because otherwise they were going to lose out to the new exchanges. And that's basically the feedback loop that's created today's electronic markets.

</details>

### 纳秒级交易与订单执行流程

**Joe Weisenthal**: Joe，每当我听到毫秒和纳秒这样的词，我都很难理解它到底是什么。它比那更快。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Joe, whenever I hear terms like millisecond and nancond, I just it's so hard to wrap my head around what that actually it's. It's faster than that.

</details>

**Tracy Alloway**: 哦，是的。当然。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Oh, yeah. For sure.

</details>

**Donald McKenzie**: 我可以帮忙解释一下。我会伸出我的手指，我将它们分开30厘米，或者因为你在美国，我会说一英尺。在真空中的光速下，光从一个手指到达另一个手指需要**一纳秒**。这表明了自动化交易，特别是高频交易的速度有多快。当我大约在2011年开始研究这个话题时，人们还在谈论毫秒，也就是千分之一秒。两三年后，它变成了微秒，也就是百万分之一秒。而到研究结束时，纳秒已经开始变得重要。所以，光传播30厘米，也就是一英尺的距离，对高频交易来说变得至关重要，大约在2018、2019、2020年左右。

<details>
<summary>Original English</summary>

**Donald McKenzie**: I I can actually help there. And I'm going to hold my fingers. I'm holding them 30 cm apart or since you're in the US, I'll say one foot apart at the speed of light in a vacuum. It takes a nancond to get from one finger to the other finger. And that's an indication of how fast automated trading specifically high frequency trading has become. That when I started working on the topic in roughly 2011, people were still talking about milliseconds or thousands of a second. Two or three years later, it had become microsconds or millionth of a second. And by the time Ed was finishing the research, nanconds were starting to account. So light traveling that 30 cm traveling that foot that mattered to high frequency trading by you know roughly 2018 2019 2020 round about then

</details>

**Joe Weisenthal**: 这非常有帮助。我确实想问一些关于我们实际能以多快的速度进行所有这些操作的物理现实问题。但在我们深入之前，您能谈谈交易流程吗？我们暂时只关注股票市场。有人下达买入或卖出股票的订单。在交易员、做市商和交易所之间的生态系统中，实际发生了什么，使得这笔交易得以实现？实现并执行交易到底意味着什么？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: that's very helpful. I do have questions about the physical realities of how fast we can actually go with all this stuff. But before we go any further, can you talk about the process of let's just focus on the equity market for now. Someone places an order to buy or sell a stock. What actually happens in the ecosystem between traders and market makers and the exchange that makes that happen and what does it mean to actually make that happen and execute the trade?

</details>

**Donald McKenzie**: 那么，发生的情况是，你的订单通过经纪商，你的用户——我的意思是，在经纪系统里不再是人类——通过经纪系统被放入交易所的**订单簿**中，然后会发生两件事之一。第一种情况是，如果撮合引擎能在订单簿中找到一个与你的订单价格匹配的现有订单，它就会执行交易，然后交易就发生了，不是完全即时，但非常非常快，你就完成了。就是这样，结束了。另一方面，如果订单簿中没有匹配订单，你的订单就会停留在订单簿中，它会一直待在那里，直到你取消它，或者出现一个匹配订单，然后在那一刻被执行。所以这就是基本流程。

<details>
<summary>Original English</summary>

**Donald McKenzie**: So what happens is your order via the broker your user I mean in the brokerage system is no longer a human being via the brokerage system gets placed in the exchanges order book and then one of two things happens. The first is if the matching engine can find an existing order in the order book that matches the the price of your order, it executes the trade and the the trade then happens, not quite instantly, but you know, very very very fast and you're done. You're that's it. It's over. If on the other hand there is no match as the order book stands your order rests in the order book and it stays there until either you cancel it or a matching order comes along and then it's executed at that point. So that's the basic process

</details>

### 速度的质变与人机分工

**Joe Weisenthal**: 你知道，所以我觉得交易速度的提升一直都在发生，远在我们谈论任何电子化之前，我敢肯定，其他技术也存在，技术演进是一个长期的事情，这是一种相当平庸的说法，我想。但我好奇的是，在什么意义上，量的变化变成了质的变化？也就是说，当你从1秒到千分之一秒再到纳秒时，这如何改变了可以采用的策略类型，或者在纳秒时代与1秒时代成功交易所需的技能类型？请跟我们谈谈这种关系。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: you know so it occurs to me like gains of speed in trading have been happening forever long before we were talking about you know anything electronic I'm sure yeah other technologies exist technological evolution is a long time thing is pretty benol statement I suppose but what I'm curious about is the sense in which a change in degree becomes a change in kind essentially so that like when you go from 1 second to a thousandth of a second to a nancond. How does that change say like the types of strategies that can then be employed or the types of skills that might be required to be a successful trader in the nancond era versus the 1 second era like talk to us about like that relationship.

</details>

**Donald McKenzie**: 是的。是的。有一本很棒的书，是技术史学家 **Jima Canales** 写的，叫做《**A Tenth of a Second: A History**》，而十分之一秒的重要性在于，那是普遍接受的人类感知时间的下限阈值。你知道，基本上我们无法在心理上处理比这更短的时间间隔。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Yeah. Well, there's a wonderful book by the historian of technology Jima Canales which is called a tenth of a second a history and the significance of the tenth of a second is that's the generally accepted lower threshold of the human perceptibility of time. You know, basically we just can't mentally process time intervals that are less.

</details>

**Joe Weisenthal**: 所以 Tracy，不要因为无法对纳秒建立直觉而感到难过。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So Tracy, don't feel bad about not being able to build an intuition for a nancond.

</details>

**Donald McKenzie**: 少于十分之一秒，你知道。所以本质上发生的是，我们已经从那种十分之一秒或更长的时间尺度，进入了一个人类——我的意思是，他们仍然可以对系统进行总体控制，但他们无法足够快地执行实际的交易决策，以免被算法超越——的时代。所以我们从一种以人为中心的交易形式，转向了以机器为中心的交易形式，而这种变化的实际阈值可能就在十分之一秒左右。

<details>
<summary>Original English</summary>

**Donald McKenzie**: less than a tenth of a second, you know. So what essentially happened is that we've moved from that kind of you know the tenth of a second or longer from from that kind of epoch into an epoch where human beings I mean they can still be in overall control of the system but they can't actually execute the actual trading decisions fast enough not to be outrun done by an algorithm. So we moved from a a kind of human- centered form of trading to a machine centered form of trading and the you know the actual threshold of the change is probably around that tenth of a second amount.

</details>

### 银行与独立HFT公司的竞争

**Tracy Alloway**: 我还有另一个文化和市场结构问题。但有一件事我一直觉得高频交易很有趣，那就是银行并没有真正参与其中。

<details>
<summary>Original English</summary>

**Tracy Alloway**: I have another cultural and I guess market structure question. But one thing that I always thought was interesting about high frequency trading was that the banks didn't really get into it which you know

</details>

**Joe Weisenthal**: 有一个主要原因，那就是2008年之后禁止自营交易，但即使在那之前，他们似乎也无法与独立公司竞争。为什么会这样？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: there's one big reason why which is the ban on prop trading after 2008 but even before then they just never seemed to be able to compete with independent firms. Why did that happen?

</details>

**Donald McKenzie**: 是的，我问过很多人，我认为原因很复杂。而且我要说，有些银行比其他银行更成功。银行并非总是表现不佳，尽管大多数银行在这方面表现不佳。一种思考方式是，银行通常会有一个IT部门，它与银行的其他职能，如交易、做市等是分开的。所以，如果你是一个交易员，你必须说服IT人员给你一个足够快的系统，这可能涉及他们编写一些新软件，购买一些新设备。所以你需要获得更高级别的管理层批准，而这一切都需要时间。然而，高频交易公司通常规模很小。你知道，50人就是一家不错的公司了。150人就是一家相当大的高频交易公司。这些公司通常由创始人拥有和运营。所以有一个或多个老板，但除此之外，它的组织结构相对扁平。例如，至少在高频交易的早期是这样，现在不那么简单了，但在高频交易的早期，如果某个IT公司推出了一款新的、更好、更快的服务器，而你是一家这样的公司的交易员，你会说：“好吧，我们买这个新服务器吧。”你就可以直接用自己的个人信用卡购买服务器，把它送到你的办公室，然后让你的工程师把它带到他们进行交易的数据中心，并立即安装。你知道，这可能需要一周或10天左右。而在银行，如果你能在6个月内完成，那就算做得相当不错了。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, it's I've asked people that and there's I think complex sorts of reasons and I let it be said some banks have been more successful than others. Banks are not always bad at this though most banks are bad at it. One way of thinking about it is is that typically a bank will have an IT department that's separate from the other functions of the bank like trading like market making and so on. So if you you know if you're a trader you got to persuade the IT people to give you a fast enough system which involves them you know maybe writing some new software buying some new kit. So you need to get higher level management sign off on it and it all takes time whereas the high frequency trading firms are typically pretty small. you know 50 people is a decent size firm. 150 people is you know is a reasonably big high frequency trading firm. Very often those firms are owned and run by the you know the people who founded them. So that there is a boss or bosses but you know other than that it's a relatively flat organizational structure. If for example, at least this was the case in the early days of high frequency trading, it's not quite as simple as this now, but in the early days of high frequency trading, you know, if some IT firm came out with a new, better, faster server and you were a trader in a firm like that and you okay, well, let's get this new server. You could just use your own personal credit card to buy the server, get it delivered to your office, and then get your engineers to take it out to whatever data center that they were trading in and and get it installed straight away. And you know, that could maybe that would be a week or 10 days or something. Whereas in the bank, you'd be doing pretty well if you could achieve that within 6 months.

</details>

**Joe Weisenthal**: 是的，那太棒了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah, that's amazing. Purchases,

</details>

**Tracy Alloway**: 我们不知道。我们对长时间等待电脑到货一无所知。

<details>
<summary>Original English</summary>

**Tracy Alloway**: we don't know. We don't know anything about long waits for computers to arrive.

</details>

**Joe Weisenthal**: 不，我们当然不知道。嗯，那是讽刺。顺便说一句，这让我想起了一个我想问的问题，那就是我们知道公司之间存在竞争，高频交易员为了最快的连接到交易所等等而竞争。我想公司内部也存在竞争，因为撇开信用卡轶事不谈，这些可能很昂贵，而且供应也有限，你知道，只有这么多服务器可以托管在他们想要的位置。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: No, we surely don't. Um, that's sarcasm. By the way, actually, this reminds me of something that I wanted to ask, which is we know there's competition between firms, highfrequency traders for the fastest connections to um, exchanges and things like that. There's also competition I imagine within the firm itself because setting aside the credit card anecdote these can be expensive and there's also limited supply you know only so many servers can be colllocated where they want to be

</details>

### HFT公司内部资源分配

**Tracy Alloway**: 在您的研究中，您是如何找到HFT公司的高管的？他们是如何将最快的连接分配给哪个团队的？

<details>
<summary>Original English</summary>

**Tracy Alloway**: in your research how did you actually find executives at HFT places how did they actually allocate the fastest connections to which team

</details>

**Donald McKenzie**: 是的，我发现高频交易公司可以分为两个不同的阵营。在其中一些公司中，存在独立的交易团队，它们之间不怎么沟通，而且确实是刻意不沟通的。在某些情况下，办公室的布局方式使得一个团队的人不太可能偶然听到另一个团队的人说的话。我的意思是，在那些公司里，是的，它们本质上是在竞争。我认为在这种公司中，每个交易台的业绩，也就是盈亏（P&L），表现最好的小交易团队会获得微波链路上的可用带宽，这对高频交易至关重要，等等。也许他们会首先获得最快的机器，等等。另一种交易公司过去和现在都作为一个统一实体运作，在某些情况下，甚至没有交易员的个人盈亏账户。在这种公司中，有很多共享的基础设施。而且，即使在那种隔离的交易公司中，也存在共享的基础设施，因为如果你是这种公司的老板，显然不为每个交易团队设置完全独立的IT系统，会带来简单的经济效益。但存在这种划分：公司是作为一个统一实体运作，还是作为竞争性交易团队的集合体运作？

<details>
<summary>Original English</summary>

**Donald McKenzie**: yeah what I found was the high frequency trading firms fell into two different camps, so to speak. In some of them, there were separate trading teams that didn't really communicate with each other and indeed by design didn't communicate with each other. In some cases, the the office was actually laid out in such a way that somebody in one team was not very likely accidentally to overhear something said by someone in the in another term. I mean in those in those firms yes I mean they are essentially in competition and I think that in that kind of firm then the results of each trading desk the P&L the profit and loss the little trading teams that are doing best would get the available bandwidth on the microwave links that are crucial to high frequency trading and and so on and maybe they would get the fastest machines first and and so on so forth. Earth. The other kind of trading firm was and is operated as a unified entity in some cases even without individual profit and loss in individual P&L accounts for traders and there's a lot of shared infrastructure um in that kind of firm and indeed there's also shared infrastructure in this you know the segregated kind of trading firm because if you're the boss of such a firm there's obviously simply economies in not having completely separate IT systems for each each trading for each each trading team. But there's that kind of divide. Does the firm operate as a unified entity or does the firm operate as a sort of aggregate of competing trading teams?

</details>

### 速度竞赛基础设施的演变

**Joe Weisenthal**: 那么，我们来谈谈谁最接近，或者谁的服务器可以放在哪里。请告诉我们更多关于时间线的信息。**Island** 在90年代末出现。交易行业的人们什么时候开始意识到，鉴于这种新的物理现实，鉴于速度，我们需要开始考虑谁将拥有**主机托管**？我们需要开始考虑微波无线电的视线传输？这场速度战的起源在哪里？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So actually let's just you know on the subject of who is the closest or where who gets to have their server located where tell us a little bit more about the timeline. So island emerges in the late '9s. When did it start to dawn on people in the trading industry that given this new physical reality given the speed we need to start thinking about who is going to have collocation. we need to start thinking about sort of like microwave radio line of sight. Where did that speed war was the genesis of it?

</details>

**Donald McKenzie**: 是的。是的。一个关键日期是**2005年**，当时 **Island** 已经被 **Instanet** 收购，又被 **NASDAQ** 收购，而**纽约证券交易所**则收购了另一个开创性的电子交易交易所，这个叫做 **Archipelago**。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Yeah. I mean a kind of crucial date was 2005 where Ireland which had already been bought by Instanet was acquired by NASDAQ and the New York Stock Exchange uh acquired another of the pioneering electronic trading exchanges. This one was called Archipelago. And

</details>

**Tracy Alloway**: **Island** 和 **Archipelago** 只是巧合吗？这有点像...

<details>
<summary>Original English</summary>

**Tracy Alloway**: is that just a coincidence that island and archipelago? That's kind of like

</details>

**Donald McKenzie**: 是的。不，我肯定这不是巧合。是的。然后它们在技术上进行了重组。纽约证券交易所和NASDAQ在技术上围绕这种新的、可以说是“叛逆”的交易技术方法进行了重组。而2005年，由于那一年发生的收购，是一个值得注意的年份。但即使在2005年之前，交易公司的人们也开始意识到，你不能仅仅在办公室里放一台机器就进行自动化交易。例如，堪萨斯城有一家名为 **Tradebot** 的交易公司，其老板 **Dave Cummings** 写了一本相当不错的自传。Cummings 意识到的一件事是，当他的机器在堪萨斯城时，在Island上交易会让他处于劣势。所以像这样的公司开始将他们的机器直接搬到Island的机房，或者如果不能，就搬到同一栋楼里另一家公司的办公室，以缩短距离。这种事情在2005年就已经到位了。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. No, I'm sure it's not a coincidence. Yeah. And they technologically reorganized themselves. The New York Stock Exchange and NASDAQ technologically reorganized themselves around this new insurgent technological approach to trading, so to speak. And 2005 because of the acquisitions in that year is is a kind of noteworthy year. But even before 2005, people in trading firms started to become aware that you couldn't just do automated trading with the machine sitting in your office. For example, there's a Kansas City trading firm called Tradebot whose owner Dave Cummings has written a really rather nice autobiography. And one of the things that Cummings came to realize is that trading an island while having your machines in Kansas City was placing him at a disadvantage. So firms like that started to move their machines either directly into the island computer room or they couldn't do that into the offices of another firm in the building to shorten the distance and that kind of thing was already in place by 2005.

</details>

**Donald McKenzie**: 接着，在一段时间内发生了两件事。出现了一种“狂野西部”时期，可以说，有很多高频交易员在墙上钻孔的故事，以缩短他们的服务器与交易所撮合引擎之间的距离。这种情况现在基本上已经结束了。现在，所有主要交易所的数据中心都有关于**等长电缆**的规定。所以，如果一家交易公司的服务器碰巧物理位置靠近交易所撮合引擎，连接它们的光纤电缆会被盘绕起来，以便该数据中心内每家交易公司的电缆长度完全相同。另一件开始发生的事情是，将信号从一个交易所的数据中心传输到另一个交易所的数据中心，开始成为一场技术速度竞赛。回到2005年，大体上它只会通过光纤电缆发送，但确切的路径不受交易所或交易公司的控制。所以有很多随机性。这里的关键连接实际上是**芝加哥商业交易所**（CME）当时位于芝加哥市中心的数据中心（现在在芝加哥郊区）与新泽西州北部交易股票的数据中心之间的连接。那里发生了一种三重演变。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Two things then happened for a period. There was a kind of wild west so to speak where there are lots of stories of high frequency traders like drilling holes in walls so as to shorten the distance between their servers and the exchanges matching engines. That has by and large generally come to an end. What happens now in the in the data centers of all the major exchanges is there is a rule about equal cable length. So if you happen to have if a trading firm happens to have its servers physically close to the exchange matching engines, the fiber optic cable that connects them is coiled so that there's exactly the same cable length for each of the trading firms within that data center. The other thing that started to happen is that getting the signal from one exchange's data center to another exchanges data center started to become a technological speed race. Back to 2005, by and large it would just be sent by fiber optic cable, but the exact route was not under the control of the exchanges or of the trading firms. So there's a lot of sort of randomness. The crucial link here is actually between the Chicago Merkantile Exchanges data center then um in downtown Chicago. It's it's now in in in the suburbs of Chicago. The link between that and the data centers that trade shares in northern New Jersey. And there was a kind of triple evolution there.

</details>

**Donald McKenzie**: 第一阶段的演变是，一家特定的交易公司，由于它不再直接经营，我可以点名，叫做 **Gecko**，它设法将现有的光纤电缆“缝合”起来，以在芝加哥-新泽西连接上获得最快的路线。这在业内被称为“**黄金线**”（gold line），“黄金”是因为拥有最快路线可以赚到的钱。然后，如果我没记错的话，在2010年，一家新公司 **Spread Networks** 实际上从芝加哥到新泽西州北部挖了一条全新的电缆。你知道，他们钻穿停车场下面等等，真的努力做到尽可能接近地理学家所说的“大地测量线”，换句话说，就是地球表面上从A点到B点最快的路线。然后第三阶段，这被**微波**的到来超越了，因为光在光纤电缆中——我的意思是，光纤电缆的核心本质上是一种特殊形式的玻璃——这种玻璃会将光速减慢到真空速度的三分之二。然而，如果你能通过大气层发射电磁信号，它不完全是真空中的光速，但非常非常接近真空中的光速。所以那是第三阶段，人们从完全使用光纤电缆转向通过芝加哥和新泽西州北部之间的微波链路来补充光纤电缆。

<details>
<summary>Original English</summary>

**Donald McKenzie**: The first evolution was that the particular trading firm, and since it's no longer directly in business, I can actually name it Gecko, um, managed to, as it were, stitch together existing fiber optic cables to get the fastest route on the Chicago, New Jersey link. And that actually in the business was known as the gold line. gold because of the money that you could make by having the fastest route. Then in 2010, if memory serves me right, a new firm, Spread Networks, actually dug an entire new cable from Chicago to Northern New Jersey. Uh, you know, drilling, you know, sort of underneath car parks and, you know, just really trying to be as close to what a geographer would call the geodisic. In other words, the the fastest route on the surface of the earth from point A to point B. Then third phase that was trumped by the arrival of microwave because light in a fiber optic cable I mean the core of fiber optic cable is essentially a specialized form of glass and that glass slows the light down to only 2/3 of its speed in a vacuum. Whereas if you can shoot your electromagnetic signal through the atmosphere, it's not exactly at the speed of light in the in a vacuum, but it's very very close to the speed of light in a vacuum. So that was the third phase when people moved from exclusive use of fiber optic cable to supplementing the fiber optic cable by microwave links between Chicago and northern New Jersey.

</details>

**Tracy Alloway**: 那真是太不可思议了。

<details>
<summary>Original English</summary>

**Tracy Alloway**: That was incredible.

</details>

### 做市商与流动性攫取者

**Joe Weisenthal**: 我还有另一个文化和市场结构问题，那就是除了这种激烈的速度竞争之外，当时还有一种说法认为这是一件坏事。嗯，一个有趣的文化现象是，你看到高频交易公司将自己分为“好人”和“坏人”。所以有些人会说，“嗯，我们创造流动性，对吧？我们对市场有好处。”然后还有一些人，我的意思是，他们不会这样形容自己，但他们被指责为**流动性攫取者**。我们应该如何看待这种特殊的紧张关系？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I have another cultural market structure question which is along with this intense competition to be faster than anyone else there was a narrative around that time that this was a bad thing Right. Um, and one of the interesting cultural things is you saw the highfrequency trading firms kind of divide themselves into good guys and bad guys. So there were some that were saying, "Well, we make liquidity, right? We're good for the market." And then there were others, I mean, they wouldn't describe themselves this way, but they were accused of being liquidity takers in the market. How should we think about that particular tension?

</details>

**Donald McKenzie**: 是的。不，那是一个非常根本的问题，因为你说得非常对，交易公司之间存在一定程度的差异化，甚至在那些更隔离的公司内部，不同的交易台也分属于不同的阵营。我的意思是，思考这个问题的方式是记住，在所有这些交易所中，交易都是围绕**电子订单簿**组织的。正如我所说，它列出了买入和卖出相关工具的所有报价。**做市商**公司所做的是，它将大量订单放入订单簿中，这些订单的价格不能立即执行，但这些订单随后会填充订单簿。所以，如果其他人，无论是个人投资者还是资产管理公司，需要进行交易，他们会发现一个充满大量现有买卖报价的订单簿，他们可以根据这些报价进行交易。所以做市商公司提供**流动性**，大多数人认为这是一件好事。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. No, that's a very fundamental thing because you're quite right that there's a degree of differentiation between trading firms and indeed in the more segregated firms also within those firms you different desks fall on others on different sides of that. I mean the the way to think about it is to remember that in all these exchanges trading is organized around an electronic order book. As I said, a list of the bids to buy and offers to sell the instrument in question. What a market making firm does is it places lots of orders into the order book at prices that can't immediately be executed, but those orders then populate the order book. So if somebody else comes along, an individual investor or maybe an asset management firm, somebody else comes along and needs to trade, they find an order book that's populated with lots of existing bids and offers that they can execute against. So the market making firm is providing liquidity and most people reckon that that's a good thing.

</details>

**Donald McKenzie**: 另一种公司，正如你所说，往往争议更多，它们不这样做。它们不持续填充订单簿。它们的系统持续监控订单簿。然后，当它们检测到它们认为是盈利机会时，它们会根据订单簿中已有的订单进行执行。这被称为**流动性攫取**，因为执行当然会从订单簿中移除订单。在实践中，很多这种情况实际上发生在高频交易公司之间，因为订单簿中的大多数订单是由做市高频交易公司放置的。而针对这些订单的许多执行则是由专门从事流动性攫取的高频交易公司进行的。这就是赋予这个行业“速度军备竞赛”特征的核心。

<details>
<summary>Original English</summary>

**Donald McKenzie**: The other kind of firm, the one where, as you say, there tends to be more controversy, they don't do that. They don't constantly populate the order book. Their systems constantly monitor the order book. And then when they detect what they think is a profitable opportunity, they execute against the orders that are already in the order book. And that is called liquidity taking because of course the execution removes the order from the order book. And in in practice, a lot of this is actually going on between high frequency trading firms because most of the orders in the order book are placed by market making high frequency trading firms. And a lot of the executions against those are by the high frequency trading firms that specialize in taking liquidity. And this is the core of what gives the business its characteristic as an arms race in speed.

</details>

**Donald McKenzie**: 所以，想象一下，你的算法正在新泽西州北部的一个数据中心交易股票，而**芝加哥**交易的相关**股指期货**价格发生变化，甚至股指期货的订单簿发生重大变化，然后假设股指期货的价格下跌，这很可能在极短的时间内导致新泽西州交易的标的股票价格下跌。而在那极短的时间内，在那段中间时期，许多做市商公司的订单在那些订单簿中变得“陈旧”（stale），正如市场人士所说。所以做市商公司会争相取消他们的陈旧订单，而流动性攫取者公司则会争相执行那些陈旧订单。而这场竞赛现在实际上可以在纳秒级的时间内展开。

<details>
<summary>Original English</summary>

**Donald McKenzie**: So for imagine for a moment that your algorithms are trading equities in one of the data centers in northern New Jersey and the relevant stock index future traded in Chicago changes in price or even you know there's a big shift in the order book for that stock index future and then let's say the price of the stock index future falls that's very likely to lead within a tiny fraction of a second to falls in the price of the underlying shares being traded in New Jersey. And in that tiny little fraction of a second in that intervening period, a lot of the market making firms orders in those order books become stale as people in the markets would put them. So the making firms rush to try to cancel their stale orders and the taking firms race to execute against those stale orders. And that's a race that nowadays can literally be played out in nanoseconds.

</details>

### HFT公司的资本结构与风险控制

**Joe Weisenthal**: 这很有趣。说实话，我以前从未真正理解这种动态。您提到这些高频交易公司，它们基本上都是由员工或所有者运营的。是什么让高频交易公司与对冲基金（它们有有限合伙人并进行分配等）有所不同？你知道，你从没听说过“哦，我在 **Jane Street** 有投资”之类的话。他们，我想那不是我所想的。这种业务的性质是什么，使得它们本质上交易的是自己的资本？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That's interesting. I hadn't appreciated that dynamic at all to be honest. You mentioned that these highfrequency trading firms, they're all sort of like they're run and operated basically by the employees or the owner or something like that. What is it that sort of distinguishes a highfrequency trading firm from say a hedge fund that would have limited partners and make distributions etc. You know, you never hear about like oh I have an investment with Jane Street or something like that. They I don't think that's what I think. What is it about the nature of the business such that essentially they trade their own capital?

</details>

**Donald McKenzie**: 是的，我想这在某种意义上就是历史演变的结果。我的意思是，在许多情况下，这些高频交易公司最初是由成功的**场内交易员**（floor traders）建立的，特别是芝加哥市场（期货市场）的场内交易员。如果你在那方面很成功，你可能不会成为亿万富翁，但你可以赚到相当可观的钱，几千万美元，这足以让你创办一家最初规模不大的自动化交易公司，而且你通常不需要任何外部资本。你只需要购买必要的技术设备，并雇佣技术娴熟的人员等等。但你可以从很小的规模开始。你可以创办一个10人左右的公司。现在，由于我们刚才谈到的速度竞赛，这项业务变得昂贵得多，但总的来说，这些公司盈利了，所有者将利润再投资于公司，这样公司的能力就增长了，以满足不断增长的需求。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, I guess that's just you know in a sense it's one of those things that's historical evolution. I mean in many cases those high frequency trading firms were initially set up by successful floor traders particularly floor traders in the Chicago markets the futures markets and if you were successful in that you could you might not become a billionaire but you know you could make decent amount of money tens of millions of dollars and that was enough to enable you to start an initially small automated trading firm and you often didn't need any external capital to do it. You just had to buy the necessary technical kit and hire technically savvy people and so on. But you could start really quite small. You could start, you know, 10erson firm or something like that. Now the business has got a lot more expensive since then because in good part of the speed race that we've just been talking about but by and large those firms made profits the owners reinvested the profits in the firms so that you know the the capabilities of the firms grew to meet the growing demands on them.

</details>

**Donald McKenzie**: 另外，也许应该提到的是，这些创始人会将他们大部分的净资产投资在公司里。所以他们的风险控制通常都相当好。你知道，这些公司的风险管理不是那种交易员必须设法智取的分离的官僚部门。创始人会很快发现你是否试图做那样的事情。尽管如此，一些自动化交易公司还是破产了，但实际上，它们破产的数量之少是相当有趣的。我认为这是因为相对较小的结构、创始人的亲身参与等等，创造了一种技术文化，这种文化实际上运作得相当好，比我在这项研究开始时预期的要好。

<details>
<summary>Original English</summary>

**Donald McKenzie**: And then another thing that should perhaps be said is that those founders would have the majority of their net worth invested in the firm. And so their risk control was often, you know, pretty good. You know, risk management for those firms was not a sort of, you know, a separate bureaucratic department that the traders had to try to outwit, so to speak. the founder would quickly detect if you were trying to do something like that. Now, some automated trading firms have blown up ne nevertheless, but it's actually quite interesting how few of them have blown up. Yeah. because of you know for example because of classical software bugs and that's I think because the relatively small structure the handson involvement of the founders etc etc has created a kind of technical culture that actually works pretty reasonably well better than I would have expected it to work at the start of this research

</details>

### 速度的物理极限与经济制约

**Tracy Alloway**: 所以我想问的一件事是关于我们实际能走多快的物理限制。我很确定人们总是说你不能比光速更快。那里可能有一些关于量子纠缠之类的注意事项，但我们肯定已经非常接近事物实际能走多快了。您认为这场速度竞赛还能持续多久？

<details>
<summary>Original English</summary>

**Tracy Alloway**: so one thing I wanted to ask is this idea of physical limitations to how fast we can actually go. I'm pretty sure people always say that you can't go faster than the speed of light. There's probably some caveats there about like quantum entanglement and stuff like that, but surely we must be getting close to how fast things can actually go. What's your sense of how long the speed race can continue?

</details>

**Donald McKenzie**: 是的。我们永远无法达到零。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. Well, we can never get to zero.

</details>

**Joe Weisenthal**: 嗯。当然，我认为**爱因斯坦**基本上是正确的。你不能比真空中的光速更快。同样，一个计算机系统，总是会有非零的处理时间，但你可以越来越接近那个极限。所以在数学上，零是一个**渐近极限**。也就是说，你总是可以更接近它，但你永远无法真正达到它。我认为这就是这个行业的本质。你知道，我们仍然处于纳秒级别。如果我没记错的话，下一个更小的时间间隔是皮秒。你知道，我能想象这会在皮秒领域继续下去。所以，我看到的是，有一个硬性限制，但我们永远不会真正达到这个硬性限制。我们仍然会努力尽可能地接近它。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Mhm. Of course, I think Einstein is basically correct. You can't get faster than the um the speed of light in a in a vacuum. And similarly, a computer system, there's always going to be a nonzero processing time of the system, but you can get ever ever closer to that. So in mathematics speak, zero is an asmtopical limit. Um that's to say you can always get closer to it, but you're never actually going to get right there. And I think that's the nature of the business. You know, we're still in the nancond regime. If I remember correctly, the next lowest time interval is the picoscond. um you know we I could imagine this continuing in a in a domain of picos seconds. So that's the way I would see it that there's a hard limit but we're never actually going to get to the hard limit. We're still going to race to get as close as possible.

</details>

**Tracy Alloway**: 但根据您目前的研究，您的理解是这场竞赛还没有结束。对于这些公司来说，我敢肯定他们有很多不同的项目正在进行，包括与人工智能相关的各种事情，我们还没有谈到，我想我们也不会谈到，但速度竞赛没有也不会结束。

<details>
<summary>Original English</summary>

**Tracy Alloway**: But your understanding as of the time of your work is that the race is not over. that for these firms and I'm sure they have many different projects on their plate including various things with AI which we haven't gotten to and I guess we won't but the speed race is not and will never be done.

</details>

**Donald McKenzie**: 是的，我认为这是正确的。当然，这里有一个经济过程在起作用，也就是说，你在速度上的投资必须能够从你的交易利润中收回。我认为 Tracy 在一开始就说了，这里本质上发生的是，金融市场的结构性特征正在被利用，比如股指期货与标的股票之间的关系。通过利用这些结构性特征所能赚到的钱并非微不足道。**芝加哥**经济学家 **Eric Suffort** 及其同事对此进行了很好的衡量。它并非微不足道，但可能只有个位数级别的数十亿美元。所以，你知道，突然决定在速度技术上投资500亿美元将是一个愚蠢的决定，因为你无法收回成本。所以存在这样一个经济因素，我相当确定它正在减缓速度竞赛，速度竞赛仍在进行，但它的速度增长率肯定没有加速，我认为这个经济因素可能解释了这一点。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, I think that's correct. Now, of course, there is an economic process, yeah, at work here, which is to say that the investments that you make in speed have to be recoupable from the trading profits that you make from your trading. And I think Tracy I think said at the very beginning what essentially is going on here is that structural features of financial markets are being exploited like the relationship between the stock index future and the underlying equities. The amount of money to be made by exploiting those kind of structural features is not trivial. It's been nicely measured by the um Chicago economist Eric Suffort and colleagues. It's not trivial, but it's perhaps singledigit billions of dollars. So, you know, suddenly deciding you're going to invest $50 billion in the technology of speed would be a dumb thing to do because you wouldn't be able to recoup it. So there is that economic factor that is I'm pretty certain slowing you know the speed race is still there but it's it's you know and you know things are getting faster but the rate at which they're getting faster is certainly not accelerating and I think that economic factor probably explains it.

</details>

### HFT对市场效率与金融薪酬的影响

**Joe Weisenthal**: 这说得通。那么，我们应该更多地谈谈HFT对整体市场的影响。您的书中有件事引起了我的注意，您引用了一项先前的研究，我不记得是谁做的，但基本上说的是，从1880年到2012年，金融市场的效率并没有提高。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That makes sense. So, we should talk about the impact of HFT on the overall market a little bit more. And one of the things that caught my eye in your book was you cite a previous study, I can't remember by who, but basically saying that the efficiency of financial markets has not improved between the 1880s and 2012,

</details>

**Tracy Alloway**: 这非常反直觉。但这到底意味着什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: which is very counterint. But what does that mean? Yeah.

</details>

**Donald McKenzie**: 是的。这是 **Thomas Philippon** 的研究。或者用法式发音，在美国人听来是 Thomas Philippon。他所说的效率与我一直在谈论的效率非常不同。他所说的效率是他所谓的**金融中介的单位成本**，这本质上就是，粗略地说，投资者、资产管理公司等想要做的事情需要花费多少钱。而且，你知道，从1880年到我认为他最新数据到2015年，这个成本并没有真正明确的下降趋势，尽管信息和通信技术在这几十年里取得了所有进步，这非常引人注目。简单粗暴地解释是，这些效率收益以金融部门高薪的形式被攫取了。你知道，通常是通过费用的形式。所以你支付给指数基金的费用，比如说，确实下降了。但人们也将钱投入到私募股权和对冲基金等，这些基金的费用要高得多。所以这些效应似乎在1940年代相互抵消了。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah. So that is work by Thomas Filipon or his French pronounce it in the American way. It's Thomas Filipon. What he means by efficiency there is really rather different from what I've been talking about. What he means by efficiency is what he calls the unit cost of financial intermediation which essentially is you know basically putting it crudely how much it costs to do the kind of thing that investors want to do that asset managers want to do and so on and it you know it's very striking finding that from the 1880s to I think his most recent data got up to 2015 that there was no really clear-cut tendency for that cost to decline despite all the advances in information and communication technologies over those many decades. And the explanation to put it simplistically and crudely is the capture of those efficiency gains in the form of high pay in the financial sector. You know, typically through the form of fees. So the fees that you pay for an index fund, say for example, those have really gone down. But people have also been moving their money into private equity and the like hedge funds which have much higher fees and so on. So those kind of effects seem to have sort of canceled themselves out in the 1940s.

</details>

**Donald McKenzie**: 1940年代，金融行业的专业人士基本上与在不同行业拥有同等教育资格的人薪酬大致相同。然后从1970年代开始，差距越来越大。现在当然，你可以通过成为人工智能领域的技术专家赚很多钱，但总的来说，抛开这些例外，金融是一个薪酬非常高的职业，至少对于其中的核心角色来说是这样。这本质上就是 Philippon 那个发现的解释。

<details>
<summary>Original English</summary>

**Donald McKenzie**: A professional in finance was basically paid roughly the same as somebody with equivalent educational qualifications in a different line of business. And then from the 1970s onwards the gap has got bigger and bigger and bigger. Now these days of course you can make a lot of money by being a technologist in AI for example but by and large those sort of exceptions aside finance is an extraordinarily well-paying professional at least for those in the central roles in it. And that's essentially the explanation of of that finding by Philippon.

</details>

### AI的规模化与边际效益递减

**Tracy Alloway**: 这是一个很好的机会来谈谈人工智能，因为我想作为一名研究科技行业或关注科技如何影响事物的社会学家，您的下一个项目必然是人工智能，对吧？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Well, this is a good opportunity to ask about AI because I suppose it's inevitable as a sociologist who examines the tech industry or looks at how tech is impacting things. Your next project must be AI, right?

</details>

**Donald McKenzie**: 是的，没错。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yes, it is.

</details>

**Tracy Alloway**: 那么，具体的角度是什么？或者到目前为止您发现了什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: And what's what's the particular angle or what have you been discovering so far?

</details>

**Donald McKenzie**: 是的，现在还处于非常早期阶段。但我目前最感兴趣的是**人工智能的规模化**问题。当然，对于任何读报纸、订阅彭博社或其他媒体的人来说，这都不是秘密。我的意思是，数万亿美元正被投入到人工智能基础设施中。而且绝对存在一种逻辑，这种逻辑被反复强调，那就是这些系统都是围绕**神经网络**构建的，而神经网络的有效性随着网络规模、训练数据规模、模型参数数量等而增长，并且存在众所周知的**规模化定律**。但是——这就是我感兴趣的地方——**Sam Altman** 在去年二月有一个非常精妙的说法，即一个系统的智能大致是投入训练、运行和推理计算等资源的**对数**。当然，Altman 的意思基本上是，给这个行业更多的钱，你就会获得更多的智能。而这当然确实是正在发生的事情，即给这个行业更多的钱。但是，一个对数函数，这里涉及一点数学，一个对数函数，至少是 Altman 所指的那种，是一个**边际效益递减**的函数。你可以画出它的图表，它非常清楚地表明了边际效益递减。它会让你越来越好，但每一次增量都需要你投入更多的资源。而我们在这里处理的是，图表中的横轴，可以说，是以万亿美元的金融投入或数百兆吨的二氧化碳排放（由为数据中心供电所需的电力产生）来计量的。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Yeah, it's very early days. But the thing I'm most interested in so far is the question of scaling a I because of course it's no secret to anybody who reads reads a newspaper subscribes to Bloomberg or or whatever. I mean the huge trillions of dollars are being thrown at AI infrastructure and absolutely there is a sort of logic there that's you know repeatedly stated that you know these systems are all built around neural networks and the effectiveness of a neural network grows with the size of the network the size of the training data the number of parameters in the model and so on and there are well-known scaling laws but and this is the thing that interests me is the the but there's a very nice little statement from Sam Alman in February of last year that the intelligence of a system is roughly the log the logarithm in other words of the resources devoted to training it running it to computation at inference time and so on. Now, of course, what Alman meant was basically give the industry more money and you'll get more intelligence. And that's of course indeed the giving the more money to the industry is exactly what what's going on. But a logarithmic function, there's a bit of maths here, a logarithmic function, at least of the kind that Altman is referring to, is a diminishing returns function. You can draw its graph and it very clearly demonstrates diminishing returns. It'll you can always get better and better, but each increment costs you more in terms of the resources deployed. And we're dealing here where the horizontal axis in the graph so to speak is denominated in trillions of dollars of financial input or hundreds of megat tons of carbon dioxide emitted by the electricity generation needed to power the data center.

</details>

**Donald McKenzie**: 所以问题就变成了，在一条边际效益递减的曲线上，你要走多远？你什么时候决定我们真的必须停止？你能决定我们真的必须停止吗？你是否有一种准魔法般的信念，认为在某个点上，边际效益递减会发生某种质的变化，即**通用人工智能**或**超级智能**会突然出现？所以，这就是我目前最感兴趣的核心问题。在一条边际效益递减的曲线上，你要走多远？

<details>
<summary>Original English</summary>

**Donald McKenzie**: So the question becomes on a diminishing returns curve how far do you go? When do you decide we really got to stop? Can you decide we really got to stop? Do you have kind of quasi magical beliefs so to speak that at some point the diminishing returns something qualitative will happen that artificial general intelligence or super intelligence will suddenly appear? So that's the core of what I'm interested in um right now. How far do you go along a diminishing returns curve?

</details>

**Joe Weisenthal**: Joe，我只想郑重声明，如果你给我更多的钱，我就会变得更聪明。没有边际效益递减，只是为了记录在案。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Joe, I just want to state for the record if you give me more money I get more intelligent. There's no diminishing returns just for the record,

</details>

**Tracy Alloway**: 嗯，我注意到了。首先，这很有趣，你知道，在这样的背景下听到这些，突然间就明白了这如何融入您的工作，以及这种**军备竞赛**的理念，对吧？因为是的，确实如此，也许公司可获得的额外利润是有限的，也许那个利润池正在缩小，也许利用剩余利润的成本越来越高。但另一方面，你不能落后。你不能让，所以这在高频交易中是真实的，在人工智能中也显然是真实的，那就是，好吧，它花费越来越多的钱来改进模型，但你不能落后，即使每次迭代的经济效益看起来更差。

<details>
<summary>Original English</summary>

**Tracy Alloway**: you know. Um, noted first of all, and it's interesting, you know, hearing this in the context and it suddenly makes so much sense how this fits into your work and this idea of like the arms race, right? Because yes, it's true like maybe there's only so much extra profit available for the firm and maybe that pool of profit is shrinking and maybe it gets more and more costly to sort of exploit the remaining profit that's available. But on the other hand, you can't fall behind. You can't let and this is so there it's true in HFT and it's clearly true in AI where okay like it spends more and more money to improve the model but you can't fall behind even if the economics look worse with each iteration.

</details>

**Tracy Alloway**: 无论如何，McKenzie教授，这次对话很愉快。我真的很享受。我们学到了很多。非常感谢您来到OddLots，嗯，是的，谢谢您。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Anyway, Professor McKenzie, lovely conversation. I really enjoyed that. We really learned a lot. Really appreciate you coming on to OddLots and uh yeah, thank you for

</details>

**Donald McKenzie**: 谢谢你们两位。谢谢你们两位邀请我，就像我说的，谢谢你们进行了一次非常棒的对话。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Thank you both. Thank you both for inviting me like I said and you know thanks for a a really great conversation.

</details>

**Joe Weisenthal**: 太棒了。谢谢您。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: It was fantastic. Thank you.

</details>

**Tracy Alloway**: 等您的人工智能书出版后，我们得再请您回来。

<details>
<summary>Original English</summary>

**Tracy Alloway**: We'll have to have you back on when you publish your AI book.

</details>

**Donald McKenzie**: 绝对。

<details>
<summary>Original English</summary>

**Donald McKenzie**: Absolutely.

</details>

### 播客总结与HFT/AI的共同点

**Joe Weisenthal**: Tracy，我喜欢这次对话。真的很有趣。我喜欢遇到那些真正理解技术，真正能阐明技术作用的人，特别是对于一个社会学背景的人来说，能如此自如地谈论这些，总是令人印象深刻。我认为这就是他工作的核心，他理解这一切。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Tracy, I love that conversation. Really interesting. I love like encountering people who are like actually understand the tech, actually can articulate what the tech is doing for especially it's always impressive someone with a sociology background to just sort of be like that comfortable and I think that's like the throughine of his work is like he gets it

</details>

**Tracy Alloway**: 是的。所以书里有很多去数据中心实地考察，查看电缆之类的描述，但正如你所说，也有很多与人交谈和获取轶事。还有一些有趣的故事，比如“星号之战”之类的，那是在书的最后，但人们应该去读一读。这次对话中让我印象深刻的另一件事是，在接近尾声时，当我们讨论人工智能时，你提出了一个观点，那就是现在HFT和AI之间存在类似的动态，因为一切都被框定为**生存问题**。

<details>
<summary>Original English</summary>

**Tracy Alloway**: right. So in the book there's lots of like field trips to data centers and looking at cables and things like that but then also as you stated just talking to people and getting anecdotes and there's funny stories about like the battle of the asterisks and things like that that's at the very end but people should go and read it. The other thing that stood out to me from that conversation was towards the end when we discussed AI, you made the point that you get this similar dynamic between HFT and AI now where because everything is framed as existential.

</details>

**Joe Weisenthal**: 你就是不能停下来，对吧？你总是必须继续前进。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Uh you just can't stop, right? You always have to keep going.

</details>

**Tracy Alloway**: 完全正确。你看，我的意思是，我想高频交易在广义上并不是那种“生存问题”，但它在公司层面是生存问题。是的，在公司层面。所以就像，我以前真的没想过，好吧，你有一个理论利润池，那是芝加哥期货交易价格和纽约股票交易价格之间的差距，那是固定的，不会变得那么大。但再说一次，如果有人更快地利用它，我以前从未真正听过，直到你的问题和他的回答，这种“做市商-攫取者”的动态，那就是，好吧，我有这些订单，现在我正迅速取消它们，而你正迅速执行它们，如果你和我都身处市场，我们不能放慢速度，如果你变得更快，我必须变得更快，因为你每次都会“狙击”我，反之亦然。但是，你知道，他们仍然赚了很多钱。看起来不像人工智能公司，他们赚了很多钱。是的，没错。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Totally. And look, I mean, I suppose the high frequency trading is not sort of like existential in the broad sense, but it's existential at the firm level. At the firm. Yeah. Yeah. at the firm level. So it's like and I hadn't really thought about okay you like have this like pool of theoretical profit which is the gap between where the futures are trading in Chicago and where the stocks are trading in New York that's fixed right there that's not going to get that big but again like someone gets faster at exploiting that and I had never really heard quite until your question and his answer this sort of make taker dynamic of okay I have these orders and now I'm quickly rushing to cancel them and you're quickly rushing to fulfill them and if you and I are both in the market we can't slow if you get faster I must get faster cuz you're going to then snipe me every time or vice versa etc. But, you know, they still make a lot of money. It seems like unlike the AI firms, they make a lot of money. Yeah, exactly.

</details>

**Joe Weisenthal**: 那是HFT世界里一个有趣的动态，那种“攫取者”与“做市商”的指责。我总是想到**蜘蛛侠**的梗图，他们都互相指着对方。感觉非常像那样。但很高兴能再次回顾HFT。这有点像旧事重提，因为以前你听到的更多，而现在它已经变得如此常态化，以至于人们不再谈论它了。嗯，你知道，我们听到了很多，尤其是在2008年之后。是的。那是终极的互相指责时代，对吧？**Michael Lewis** 的书，因为你就像每个人都有一些，哦，是裸卖空者，是信用评级机构，是那个，你知道，那个迫使银行在抵押贷款分配上公平的法律，等等。就像，有上百万个互相指责。哦，也许是HFT公司，也许是卖空者，随便什么。所以我的意思是，我们不怎么听到它的部分原因是没有发生危机等等。但正如你所说，竞赛仍在继续，而且形式多样。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That was a funny dynamic in HFT world, the like accusations of Taker versus Maker. And I always think of the, you know, the Spider-Man meme where they're all kind of pointing at each other. It felt very much like that. But it was really great to catch up on HFT again. This was sort of a blast from the past because you used to hear about it more and now it's become so normalized that people just don't talk about it that much. Well, you know, we heard about it a lot and especially post 2008. Yeah. That was the ultimate fingerpointing era, right? The Michael Lewis because you just have like everyone had some, oh, it's the naked short sellers, it's the credit rating agency, it's the uh, you know, the law that forces banks to be equitable in who they distribute mortgages to, etc. Like, there was a million fingerpointing. Oh, maybe it's the HFT firms, maybe it's the short sellers, whatever. So I mean part of the reason we don't hear about it as much is because there hasn't been a crisis etc. But as you said the race continues and of various flavors.

</details>

**Tracy Alloway**: 你永远无法达到零，但你可以永远更接近。

<details>
<summary>Original English</summary>

**Tracy Alloway**: You can never get to zero but you can always get closer.

</details>

**Joe Weisenthal**: 你知道，我总是想到有些线是直线上升的，你知道，它们是否会像曲线一样回转呢？你会得到像负空间一样的东西，我们能做得比“线向上”更好吗？比如“线向上再向后”？我想爱因斯坦会说不。嗯，要是我们能请爱因斯坦来做嘉宾谈论交易就好了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know it's like you know I always think about some lines they go like straight up you know it's like the they ever like curve back around instead. You get like negative space like can we do even better than line go up like line go up and backwards? I guess Einstein would say no. Um, if only we could have Einstein on as a guest to talk about trading

</details>

**Tracy Alloway**: 谈论高频交易。

<details>
<summary>Original English</summary>

**Tracy Alloway**: to talk about high frequency trading.

</details>

**Joe Weisenthal**: 我们就到这里吧？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Shall we leave it there?

</details>

**Tracy Alloway**: 那会是完美的嘉宾。我们就到这里吧。

<details>
<summary>Original English</summary>

**Tracy Alloway**: That would be a perfect guest. Let's leave it there.

</details>

**Joe Weisenthal**: 好的。这是OddLots播客的又一期节目。我是Tracy Alloway。你可以在@TraceeAlaway关注我。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: All right. This has been another episode of the OddLots podcast. I'm Tracy Aloway. You can follow me at Tracee Alaway.

</details>

**Tracy Alloway**: 我是Joe Weisenthal。你可以在@thestalwart关注我。请查看Donald McKenzie的书《**Trading at the Speed of Light**》。当然，也请关注我们的制作人，**Carmen Rodriguez** (@Kerman)、**Dashel Bennett** (@Dashbot) 和 **Kell Brooks** (@Kellbrooks)。如需更多OddLots内容，请访问bloomberg.com/odlots。我们有每日新闻通讯和所有节目。你可以在我们的Discord群组discord.gg/odlots中24小时7天讨论所有这些话题。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And I'm Joe Weisenthal. You can follow me at the stalwart. Check out Donald McKenzie's book, Trading at the Speed of Light. And of course, follow our producers, Carmen Rodriguez at Kerman, Dashel Bennett at Dashbot, and Kell Brooks at Kellbrooks. And for more OddLots content, go to bloomberg.com/odlots. We have a daily newsletter and all of our episodes. And you can chat about all these topics 247 in our Discord. discord.gg/odlots.

</details>

**Joe Weisenthal**: 如果你喜欢OddLots，如果你喜欢我们回顾HFT的繁荣以及它如何持续，我想，那么请在您最喜欢的播客平台上给我们一个好评。请记住，如果您是彭博社的订阅者，您可以免费收听我们所有的节目。您只需在Apple Podcast上找到Bloomberg频道并按照说明操作即可。感谢收听。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And if you enjoy OddLots, if you like it when we look back at the HFT boom and how it continues, I guess, then please leave us a positive review on your favorite podcast platform. And remember, if you are a Bloomberg subscriber, you can listen to all of our episodes absolutely adree. All you need to do is find the Bloomberg channel on Apple Podcast and follow the instructions there. Thanks for listening.

</details>