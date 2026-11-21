---
author: The MAD Podcast with Matt Turck
date: '2026-03-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jH2ZIUKvazU
speaker: The MAD Podcast with Matt Turck
tags:
  - foundation-model
  - software-economics
  - unbundling
  - commodity-technology
  - ai-agents
title: Benedict Evans 对谈：OpenAI 的护城河危机与软件的未来
summary: 知名科技分析师 Benedict Evans 探讨了 OpenAI 面临的核心挑战：基础模型缺乏网络效应且趋于商品化。他深入分析了 AI 如何通过“去捆绑”重塑软件产业，提出了“即兴软件”概念，并结合 1997 年互联网泡沫等历史类比，预测了 AI 对企业架构、劳动力市场以及软件开发门槛的深远影响。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Sam Altman
  - Fidji Simo
companies_orgs:
  - OpenAI
  - Microsoft
  - Meta
  - Google
  - Nvidia
  - TSMC
  - Oracle
products_models:
  - ChatGPT
  - Claude
  - GPT-4
  - AWS
  - Azure
media_books: []
status: evergreen
---
### OpenAI 的战略挑战与模型同质化

**Benedict Evans**: 如果你是 **Sam Altman**，你现在拥有的其实是一种**商品化技术 (Commodity Technology)**。你的竞争对手是那些拥有巨大传统现金流的巨头。你没有自己的基础设施，也没有真正的差异化，但你拥有极高的**思想占有率 (Mind Share)**。所以你会怎么做？你会尝试将这种影响力换成硬件资产，并试图通过游说来实现一个**自我实现的预言 (Self-fulfilling Prophecy)**。

<details>
<summary>Original English</summary>

**Benedict Evans**: If you're Sam Alman, you've got a commodity technology. You've got you're competing with people who have giant legacy cash flows. You don't have your own infrastructure, don't really have any differentiation, but you've got massive mind share. So, what do you do? You try and swap that for hard assets and you try and talk your way into a self-fulfilling prophecy.

</details>

**Benedict Evans**: 接着你会遇到一种中间情况，几乎可以称之为**即兴软件 (Improvised Software)**。现在的 **AI 编程**意味着编码变得更加便宜和容易，也意味着以前无法用软件实现的一大堆事情，现在都可以实现了。因此，软件的数量将会迎来大爆发。

<details>
<summary>Original English</summary>

**Benedict Evans**: And then you've got this middle case where you could almost kind of call it like improvised software. And now AI coding means coding is way cheaper and easier and also means that there's a whole bunch of stuff that you couldn't do in software that now you can. And so there will be way more software.

</details>

**Matt Turk**: 大家好，我是来自 **FirstMark** 的 Matt，欢迎收到本期播客。今天我的嘉宾是 **Benedict Evans**。Ben 是全球最深刻、最有影响力的科技分析师之一。他也是我最喜欢的嘉宾之一，今天是他第三次参加我们的节目。在这次对话中，我们涵盖了 **AI 大去捆绑 (The Great AI Unbundling)**、软件是否真的已死、为什么 **OpenAI** 可能会成为下一个 **Netscape**，以及这一切对 AI 开发者、投资者和高管意味着什么。请欣赏这段精彩的对话。Ben，欢迎回来。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt from First Mark. Welcome to the Matt podcast. Today my guest is Benedict Evans. Ben is one of the most thoughtful and influential tech analysts in the world. He's also one of my favorite guests making his third appearance on the show today. In this conversation, we cover the great AI unbundling, whether software is really dead, why OpenAI might be the next Netscape, and what it all means for AI builders, investors, and executives. Please enjoy this fantastic conversation with Ben Evans. Benig, welcome or I should say welcome back. Thanks for being back on the Matt podcast.

</details>

**Benedict Evans**: 谢谢。

<details>
<summary>Original English</summary>

**Benedict Evans**: Thank you.

</details>

**Matt Turk**: 我觉得从 **OpenAI** 最近的动向开始会很有趣。就在我们录音的前一天晚上，《华尔街日报》报道称该公司正计划重大转型，聚焦于编程和商业用户。其应用负责人 **Fidji Simo** 据传表示公司应该停止“支线任务”。你最近也写过关于 OpenAI 的文章。我们是如何走到这一步的？OpenAI 面临的根本挑战是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: So I thought a fun place to start would be what's going on with OpenAI. So, as we recording this just last night, there was a Wall Street Journal article that said that the company is planning a major refocus on coding and business users with their CEO of application Fiji Simo reportedly saying that the company should stop side quests. You wrote recently about OpenAI. How did we get here and what are the fundamental challenges that OpenAI faces?

</details>

**Benedict Evans**: 我想我们可以从两个方面来谈。一个是 OpenAI 一直在尝试做的各种事情，另一个是核心问题。这个核心问题在于，据我们所知，**基础模型 (Foundation Model)** 并不存在**赢家通吃效应 (Winner-takes-all Effect)** 或**网络效应 (Network Effect)**。也就是说，你所做的事情，无法阻止其他人做出一个和你一样好的模型。这和我们熟悉的软件行业完全不同。

<details>
<summary>Original English</summary>

**Benedict Evans**: I suppose there's two way you ways we could talk about this. One of them is to talk about all the stuff that OpenAI has been trying to do. I think the other is to talk about the problem. And the problem is that as as far as we can see, there is no winner takes all effect or network effect in a foundation model. So there's nothing that you can do that means other people can't make a model as good as yours, which is what we're used to from the software industry.

</details>

**Benedict Evans**: **Windows**、**Google**、**Facebook**、**Instagram**、**TikTok** 以及 **iOS**，它们之所以能产生垄断或近乎垄断的地位，是因为软件虽然资本投入极少，但具有极强的网络效应，从而产生高毛利。但在 **LLM（大语言模型）** 领域，模型研发极其昂贵且困难，你可能会像 **Microsoft** 或 **Meta** 那样掉队，或者好不容易才爬上梯子。但并没有一个杠杆能让你一旦拉动就甩开所有人，让他们永远追不上。这不像 Google 对阵 **Bing**——无论微软投入多少钱、多么努力，Bing 永远追不上 Google。这意味着，如果我们有 3 到 6 家甚至更多的组织能做出顶尖模型，他们就会每隔几周或几个月就互相超越。

<details>
<summary>Original English</summary>

**Benedict Evans**: That's how Windows and Google and Facebook and Instagram and Tik Tok and iOS. What we're kind of used to in tech is that software by definition has no capital or very little capital but it has network effects and so it tends to produce monopolies or near monopolies and that produces high margins and so that what happened with Windows and Mac OS and Google and so iOS not Mac OS and Google and so on. Well, the question with LLMs is like they're very expensive and very hard and so you can kind of fail to get onto the ladder or fall off the ladder for like Microsoft on the one hand and Meta for for the meantime on the other hand. But there's nothing that there's no lever that you can decide you're going to pull whereby you'll just pull ahead of everybody else and they won't be able to catch up which is like Google versus Bing. Doesn't matter how much money and how hard Microsoft works, Bing will never catch up with Google. So that means if we've got like pick a number between three and six or maybe more organizations that can make a frontier model and they keep leaprogging each other every couple of weeks or every couple of months. So that's one problem.

</details>

### 大模型的经济学：商品化还是生态系统？

**Matt Turk**: 延续这个问题，你提到了软件。如果基础模型更像是 **AWS**、**Azure** 和 **GCP** 这样的三巨头垄断呢？虽然它们的服务高度同质化，但由于市场巨大，似乎大家都过得不错。这算是一件坏事吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Just to build on that problem, you mentioned software. Is it such a bad thing? If you think of not Windows, but if you think of the oligopoly of AWS, Azure and GCP, those are largely undifferiated businesses that in because of the market size seem to be doing quite well.

</details>

**Benedict Evans**: 首先，我稍微反驳一下这个类比。如果你观察市场份额，Google Cloud、Azure 和 AWS 实际上处于非常不同的业务中。AWS 主要是**基础设施**，微软主要是**服务**，而 Google 虽然发明了云技术，却在很远的地方拼命追赶。所以它们并不完全一样。但挑战在于，基础模型本身的平衡点在哪里？它们能建立起基于自身的**生态系统**吗？

<details>
<summary>Original English</summary>

**Benedict Evans**: First of all, I push back slightly on that comparison and then then answer the question. And the first is if you actually look at the market shares, Google cloud, Azure and and AWS are actually in quite different businesses. AWS is mostly infrastructure. Microsoft is mostly services. Google is mostly scrambling to catch up in in a very distant certain place despite having basically invented cloud. So they're kind of not all the same, I think. But the the challenge I suppose is is where do we get to equilibrium on the foundation model itself?

</details>

**Benedict Evans**: 就像 iOS 和 Android 那样，它们能通过在原始模型之上构建工具和各种功能来捕捉价值吗？企业会决定“我们要全公司标准化使用 **ChatGPT**”吗？但这在云服务领域并没有发生。作为一个企业，你买一个 **SaaS** 应用时，并不会想“我们要用 AWS 账号登录”。作为消费者，我也不关心 **Uber** 用的是哪朵云。所以，模型要么能构建出类似 Windows 这种 Sam Altman 去年底经常谈论的东西，要么它们就是基础的**商品化基础设施**。

<details>
<summary>Original English</summary>

**Benedict Evans**: Is it that these things will be able to create ecosystems above themselves? So it will be like iOS and Android and so they will create value they will create value capture they'll build tools and all sorts of stuff on top of the raw foundation model and so you'll have to choose right all our company is going to standardize on chat GPT which isn't what happened in cloud you as a business if you go and buy a SAS app you don't like think well we're going to log into it with our AWS account certainly as a consumer like I don't can't remember which cloud snap uses and I don't care and if I you I install Uber like which cloud does Uber use? Who cares? So it may be that the models are able to kind of build something that looks more kind of like Windows which is what Sam Waltman talked about a lot at the end of last year or it may be that they're basically commodity infrastructure.

</details>

**Benedict Evans**: 如果是基础设施，它们就会按**边际成本**出售，你甚至可能无法从投资中获得回报。这种情况下，你的回报来自于你在其上构建的应用。这就是 Meta 或 Google 的不同之处——它们拥有利润丰厚的现有业务，现在需要内置 **LLM** 来驱动各种功能，而且它们肯定希望用自己的 LLM 而不是别人的。但它们不一定要靠 LLM 本身赚钱。

<details>
<summary>Original English</summary>

**Benedict Evans**: and they're sold at marginal cost and maybe you barely make a return on the investment or maybe you don't make a return on the investment itself and what you're doing is making a return on everything you built that you do with this on top of it. And that's where the the the these companies do get different because if you are Meta or Google, you've got this whole other highly profitable business which now needs to have LLMs inside it powering all sorts of capabilities and features. And you probably want them to be your LLMs rather than somebody else's. But you not may not necessarily need to make money from the LLM by itself anymore than Meta. I mean, obviously Meta has a cloud, but Meta doesn't even try and doesn't sell the cloud. they just use it power their own stuff.

</details>

**Benedict Evans**: 现在的核心问题是：单纯的**聊天机器人 (Chatbot)** 本身并不是一个伟大的产品。大多数人都在纠结拿它来干什么。有一小部分科技圈内外的人非常擅长自我优化，他们的工作恰好非常契合 LLM 的能力。但如果你看使用数据，只有约 10% 的人口每天使用，另外 50% 是每周或每月使用一次。大多数拥有 ChatGPT 账号的人，今天都想不出能拿它做什么。

<details>
<summary>Original English</summary>

**Benedict Evans**: well the problem at the moment is that the raw chatbot by itself isn't a great product and most people struggle to work out what to do with it you've got um a small number of people mostly in tech and also outside tech who are very self-optimizing and have certain kinds of jobs that map very well to the kinds of stuff that LLMs are very good at doing. If you look at the usage data, something like 10% of the population is using these things every day, but another 50% are using it every week or every month. So most people who have a chat GPT account can't think of anything to do with it today.

</details>

**Benedict Evans**: 那么，这是因为模型还不够好？还是习惯还没改变？或者极端的说，你会因为人们每月才用一次 Google 就觉得 Google 不行吗？这似乎不是好答案。所以你必须在其上构建大量的东西，这又回到了“商品化基础设施”的观点。现在的疑问是：我们是会直接使用 ChatGPT 或 **Claude**，还是它们会变成埋在底下的**隐形 API 调用**，由其他应用来赚所有的钱？

<details>
<summary>Original English</summary>

**Benedict Evans**: And so you can ask, well, is that because the models have to get better? Or is it because habits have to change? Or at the extreme, could you say, well, people only use Google once a month, once a week, too, which doesn't seem like a good answer. Or do you have to build a whole bunch of stuff on top, which is back to this commodity infrastructure point? And so it seems like what a lot of what the question now is like, oh, are we all just going to use chat GBT or anthropic or or Claude as chat JBT or is that going to be like an invisible API call buried underneath? that's used by some other thing and it's the other thing that makes all the money.

</details>

**Benedict Evans**: 这里有一个非常有趣的类比：**台积电 (TSMC)**。芯片行业没有网络效应，但每一代技术都变得更难、更贵，竞争者随之减少。现在最前沿的基本上只有一家公司，落后一代的有两三家。台积电赚了很多钱，但它们并没有捕捉到科技行业的全部价值。消费者不知道 iPhone 里的芯片是台积电做的，台积电也不会从 App Store 的每笔销售中抽成。这就是 OpenAI 面临的巨大战略难题：你拥有商品化技术，没有网络效应，虽然有 9 亿周活用户，但大多数人不知道拿它干嘛，只有 5% 的人在付费。你的用户群广如大海，却深如茶碟。你必须把现有的关注度和势头转化为某种更持久的东西。

<details>
<summary>Original English</summary>

**Benedict Evans**: The really kind of interesting comparison here would be TSMC because what happened in chips was that there's no network effect but with each generation it got more difficult and more expensive and now there's basically one company at the frontier and two or three that are a generation behind and then five or 10 that are a generation behind that and TSMC makes lots of money but like they don't capture all the value of the tech industry like you know as a consumer you don't know that TSMC makes a chip in your iPhone and they don't get like a cut of every app store sale. So that's sort of the puzzle. This great strategic problem for Open AI is you basically got commodity technology. You don't have a network effect or when it takes all effect. You've got 900 million weekly active users, but most of them are not using it every day and can't think of anything to do with it. And only 5% of them are paying for it. So the usage is like a mile wide but an inch deep. And so you've kind of got to swap the mind share and the momentum that you have for something more durable.

</details>

### 更好的模型能解决产品问题吗？

**Matt Turk**: 去年我们聊天时，也谈到了人们不知道该用它干什么，甚至讨论过 ChatGPT 是否需要一个新的 **GUI（图形用户界面）**。引人注目的是，过去一年模型开发取得了非凡进步，引入了**推理 (Reasoning)** 和 **强化学习 (RL)** 等技术。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, you just said u last year when you and I chatted I think we were having this conversation in those terms that like people were not sure what to do. We went into whether JPD needed a new guey. What's fascinating is that it's been an extraordinary year in model development with you know reasoning and RL and and all the things

</details>

**Benedict Evans**: 但结论是，更好的模型并不能解决问题。我一年前写过一篇类似“更好的模型意味着什么”的文章，这听起来可能很荒谬，但我总记得多年前 iPhone 还是新鲜事物时，纽约的一个深夜电视节目在大街上向人们展示去年的手机，并谎称是新款，人们纷纷惊叹“哇，太神奇了”，因为你根本分不出来。

<details>
<summary>Original English</summary>

**Benedict Evans**: and the net is that a better model doesn't solve the problem. This is something I wrote like a year ago I think where I said what do you mean when you when you it was something like what is a better model and which sounds like a crazy thing to say but I always remember um like years ago when iPhones was a hot new thing um one of the New York late night TV shows they would go onto the street and they show people last year's phone and say it's a new phone what do you think and they go wow it's amazing cuz like you couldn't really tell actually

</details>

**Benedict Evans**: 如果你在做非常硬核的研究，把模型推向极限，你会发现“以前它做不到这一点，现在可以了”。但对于大多数任务，模型在很多方面的表现是参差不齐的。你并不确切知道它是否能完成某件事，或者能完成得有多好。当你需要的是“正确答案”而不是“大概正确的答案”时，模型变得更好几乎毫无意义。比如，我让模型编译 50 个东西，上个月它错了 10 个，我得全部检查一遍；这个月它错了 8 个，但我还是得全部检查一遍。所以，实际上什么都没变。真正的改变不在于准确率从 90% 提升到 95%，而在于它是否能从“大概对”变成“绝对对”。如果没有这一跃迁，你就必须更加努力地思考如何围绕它构建工具和软件。

<details>
<summary>Original English</summary>

**Benedict Evans**: and you know if you're doing like very specific very hardcore stuff and you're pushing these models to the limit then you'll be able to Oh, it didn't do that and now it can do that. With most stuff, the models are jagged in lots of different ways. You don't really know whether it will be able to do that or not or how well it will be able to do that. And most of the stuff that you try, it can sort of do to varying degrees. And now it can sort of do it slightly better or maybe slightly less sort of. But if you've got a bunch of use cases where you need the right answer as opposed to sort of the right answer, then saying that the model is better doesn't mean anything. I mean literally is literally meaningless because what you're telling me is I asked the model to compile 50 things and last month it would get 10 of them wrong. So I'd have to check all 50 and now it will get eight of them wrong or 12 but probably eight. So again I'll have to check all 50. So actually nothing's changed. And the point that things change is not when it goes from 90% right to 91% right to 95% right. The point it's either right or not right.

</details>

### AI 助手、Agent 与用户界面的未来

**Matt Turk**: 曾经有一种希望，认为**记忆功能 (Memory)** 会为聊天界面（包括 ChatGPT）增加防御壁垒和护城河。但这似乎并没有发生，为什么？

<details>
<summary>Original English</summary>

**Matt Turk**: At some point there was a hope that memory would be adding some level of defensibility and mode to all those uh chatbot interfaces including very much chat GPT. That doesn't seem to have happened. Why is that?

</details>

**Benedict Evans**: 这有几点原因。首先，只有当你已经在大量使用它时，记忆功能才有意义。如果大多数人（约 80% 的用户）一年点击回车键不到 1000 次——这意味着平均每天不到 3 次——那么根本谈不上什么“记忆”。其次，这与其说是网络效应，不如说是**粘性 (Stickiness)**。而这种粘性也很脆弱，如果你让 ChatGPT 告诉你它知道关于你的一切，然后把这些粘贴到 Claude 里呢？

<details>
<summary>Original English</summary>

**Benedict Evans**: Well, so two or three things. Firstly, I think very obviously it only works if you're using it a lot already. And so if you haven't worked out a bunch of stuff to do with this, and most people have not, then you don't see the memory. OpenAI did this this data at the end marketing at the end of last year where they gave everyone a cute little graphic of how many messages they done... And it turns out that if you did a thousand prompts last year, you're in the top 20%. So basically 80% of people hit return less than a thousand times last year... And so there's no memory there. Me then the sort of a subsidiary point would be okay is that a network effect or is that stickiness? It's probably more stickiness.

</details>

**Benedict Evans**: 这种感觉非常像 1997 年。虽然很清楚这（AI）是一件大事并且已经开始发挥作用，但这并不意味着你知道结局会如何。聊天机器人作为一个产品，很难实现差异化，就像你很难让**网页浏览器**变得不同一样。它就是一个输入框、一个输出框。你可以改进底层的渲染引擎，就像 Chrome 做的那样，也可以改进底层的 LLM。但展现给用户的产品界面几乎无法改变。难道聊天机器人的本质不就是完全通用、甚至**没有 UI** 吗？

<details>
<summary>Original English</summary>

**Benedict Evans**: One thing that occurred to me looking at chat GBT as a product is it's kind of like trying to trying to differentiate the web the chatbot itself is kind of like trying to differentiate a web browser in that you've got an input box and output box. And how can you make them different if the whole point is that you can type in anything and get anything out? ... Is it even possible in principle to make the UI of a of a chatbot different? Because isn't the whole point that it's completely universal and there's no UI?

</details>

**Matt Turk**: 你曾提到，在基础模型公司做产品与在其他任何公司都完全不同。

<details>
<summary>Original English</summary>

**Matt Turk**: yeah you had a really interesting point somewhere about how building product in a foundation model company was fundamentally different from any other company.

</details>

**Benedict Evans**: 是的。Fidji Simo 曾说过，在这些公司，你的工作方式是：早上打开电脑，收到研究小组的邮件说“嘿，我们搞出了个酷东西”，然后你的任务是去拿它做点什么。比如搞出了新的语音模型，那我们就得加个麦克风按钮。你不是在设定产品策略，你是从**技术出发**。这正是科学研究的运作方式，但你无法控制产品走向。这与 **Steve Jobs** 的名言截然相反——你不能从技术出发去寻找产品，你必须从**用户体验**出发，倒推回技术。但在 AI 领域，技术不断剧烈变动，你甚至不知道下周它能干什么，所以你很难知道自己到底在构建什么。你是**策略的接受者**，而不是制定者。

<details>
<summary>Original English</summary>

**Benedict Evans**: Oh yeah. Well, this is so so Kevin Wheel and and Mike Quigger gave this made both made this point... And then Fiji Simo made it... she said... the way it works is you you turn on your computer and you you look at your phone in the morning, you've got an email from the research group that says, hey, guess what? We've got this cool thing. And then your job is to go and do something with it. ... You don't control the product strategy, which is of course how science works... Simi... comparing it with Steve Jobs famously saying you can't start with the technology and work forward to the product. You've got to start with the user experience and work backwards to the technology. ... You're a strategy taker not a strategy setter.

</details>

### 软件的终结还是大爆发？

**Matt Turk**: 谈到软件的演变，你是否认为未来人们会通过 **Claude Code** 这种工具来自己构建软件？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. And to the point that you're just making and and also anthropic presumably you're not in the camp of believing that people are going to be building their own software with claude code.

</details>

**Benedict Evans**: 虽然有人这么说，但我认为探讨人们是否会自己写一个 Stripe 并不有趣。更有趣的是去思考软件的广阔**分类法 (Taxonomy)**。首先是大型企业 **ERP** 这种“**记录系统 (Systems of Record)**”，你需要为 5 万人和 10 亿次交易以相同方式存储数据，这种软件不会消失。然后是具体的任务和工作流，当单一系统（如 SAP）太僵化时，你就会将其“**去捆绑 (Unbundle)**”为垂直领域的专用工具，比如 **Frame.io**。

<details>
<summary>Original English</summary>

**Benedict Evans**: It's funny this is like um it's almost like a straw man except there are like presumably real rational sentient people who actually say this stuff. I don't think it's particularly interesting to explain why people aren't going to code their own stripes. I think what's more interesting is to kind of do think about a broader taxonomy of software which is that you have like the big eye and enterprise ERPs and and what they call systems of record. So like you need to store the same data in the same way for 50,000 people and a billion transactions a year. ... Then you have but then you have tasks and workflows where that single system like call it SAP is too inflexible and so you break it out unbundle it into something dedicated and vertical.

</details>

**Benedict Evans**: 还有第三种中间情况：人们在用 **Excel**、Google Sheets 或邮件处理业务，这可以被称为“**即兴软件**”。这些流程并不总是重复的，不需要严格的合规跟踪，但规模又不足以支撑一个专用工具。现在，AI 编程意味着编写软件变得便宜且容易得多，也意味着以前无法自动化的事情，现在可以自动化了。因此，会有**多得多的软件**出现。

<details>
<summary>Original English</summary>

**Benedict Evans**: and then you've got this middle case of using Google Sheets and email or using Excel... where you could almost kind of call it like improvised software where it's not a process that's being done over and over again in the same way... And now on the one side, AI coding means coding is way cheaper and easier and also means that there's a whole bunch of stuff that you couldn't do in software that now you can. And so there will be way more software.

</details>

**Matt Turk**: 所以软件行业会发生什么？它还是股市中的独立类别吗？

<details>
<summary>Original English</summary>

**Matt Turk**: so what do you think happens to software than than SAS?

</details>

**Benedict Evans**: 软件会多得多。但这需要结合“谁懂软件如何运作”以及“谁深入思考并理解了问题”。像 Frame.io 这样的工具并不是由某个在后期工作室工作的、不懂产品的人做出来的。理解代码应该做什么、理解问题的本质，这是一种不同的技能。AI 会导致一些现有的专家系统消失，因为 LLM 做得更好；但也像 SaaS 时代一样，SaaS 让软件数量增加了几个数量级，自动化了无数以前太小或太难解决的任务。在大型机时代，一个大公司可能只有 5 个软件；在云时代有数百个；在 AI 时代，由于自动化成本骤降，你会拥有无法计数的软件。

<details>
<summary>Original English</summary>

**Benedict Evans**: way more software. ... Who understands how software works and who has really thought carefully and understood the problem... Frame.io was not made by some guy or some woman working at a video production suite... because that's not how they think. They're not software people. They're also not product people. ... There will be way more software both stuff that doesn't need AI except to create it and stuff that needs to use AI to do the new thing. Some incumbent software will go away... It is just like a one-off improvised thing where you'll get the model to do it.

</details>

### AI 对各行业的深度冲击与历史类比

**Benedict Evans**: 人们去年重新发现了**杰文斯悖论 (Jevons Paradox)**。这其实就是**价格弹性**。如果你让某件事变得便宜且容易，你可能会花更少的钱做同样的事，但也可能花同样的钱做更多的事，甚至因为投资回报率 (ROI) 的改变而投入更多的钱去做。就像电子表格并没有导致金融从业人员减少，反而增加了，因为现在可以做以前根本无法完成的大量新分析。

<details>
<summary>Original English</summary>

**Benedict Evans**: people last year suddenly everyone discovered looked up the Jeffness paradox in Wikipedia... this is just pricey elasticity... if you make it cheaper and easier to do something you might do the same thing for less money or you might do more for the same amount of money or you might do do more with more money if you have a completely different ROI which is exactly what you see in like financial services is spreadsheets did not result in a collapse in the number of people working in finance say quite the opposite.

</details>

**Benedict Evans**: 有一个陈词滥调是“软件正在吞噬世界”，比如 **Uber** 和 **Airbnb**。Uber 并没有向出租车公司卖软件，它改变了“出租车”的含义。在纽约，Uber 的日订单量是以前黄色出租车的几倍。而 Airbnb 大多是增量的。如果你问 AI 是否会改变酒店业和出租车业？答案是：**这取决于具体情况 (It depends)**。我对此非常认真。如果你未婚妻要在晚上 9 点飞往某个美国中西部城市参加明早 8 点的会议，她需要健身房、客房服务和冰箱，她绝不可能住 Airbnb。

<details>
<summary>Original English</summary>

**Benedict Evans**: the market end reason software is eating the world thing of Uber and Airbnb... Uber rides per day is like triple double or triple what yellow cabs were... Airbnb was mostly additive. And you dig into that and the answer is why... Benedict... always says the answer is it depends. ... travel is business... she's not going to go and stay in an Airbnb. Like, absolutely zero negative possibility that she's going to go and stay in an Airbnb.

</details>

**Benedict Evans**: 同样，我很难认同那些通过所谓的“AI 暴露度”来给职业打分的分析。它们方向上可能是对的，但在 1997 年你分析互联网时，你可能也会说出租车司机绝不会受影响，因为你怎么能想象出 Uber 呢？你会觉得报纸可能会受影响，而在当时报纸行业还觉得互联网是个大机会。结果呢？互联网“去捆绑”了物理资产，如果你的防御能力基于拥有印刷机这种物理资产，你的商业模式就爆炸了。

<details>
<summary>Original English</summary>

**Benedict Evans**: So, this is the problem I have with people kind of trying to score professions, AI exposure... directionally right in the same way that an analysis you did in 1997 about the internet would have been... But you would not have got Uber from that analysis. You would have said, well, taxi drivers. Well, how would the internet change that? Obviously won't touch that one at all. You would have said newspapers maybe. ... what really happened was you unbundled physical assets from the underlying product. And if your defensibility was based on owning a physical asset... then your whole business model has just exploded.

</details>

### 企业 AI 部署的现状与初创企业的机遇

**Matt Turk**: 你在咨询和演讲中接触了很多大公司。你现在的感觉是怎样的？人们是比以前更困惑了吗？

<details>
<summary>Original English</summary>

**Matt Turk**: and you talk to a lot of big corporations... What's your sense of the overall sentiment? Are people more bewildered than they used to be?

</details>

**Benedict Evans**: 我不觉得是困惑。或者说，不比科技圈的人更困惑。每个人都部署了 **Copilot**，然后发现“哦，效果不咋地”。这就像在 1997 年给每个人发了互联网，然后说“去提高生产力吧”，这行不通。现在每个人都有了一堆试点项目，有些进入了生产环境，有些失败了。

<details>
<summary>Original English</summary>

**Benedict Evans**: So, I certainly wouldn't say bewildered. I mean, at least not any more bewildered than anyone in tech. ... Everyone deployed CPilot and went, "Oh, okay. That wasn't very successful." Every It's kind of like giving everybody the internet in 1997 and saying, "There you are. Be more productive. Doesn't didn't really work." Everyone now has a bunch of pilots.

</details>

**Benedict Evans**: 对于创业者来说，答案其实超级简单。回到 Frame.io，这个想法在之前的十年里任何时候都可能产生。虽然浏览器的技术实现可能还没到位，但它本质上就是“视频版的 Google Docs”。大多数 SaaS 公司其实就是**数据库的包装器 (Database Rappers)**。写几条 SQL 语句或在 AWS 上建个表并不难，难的是：代码应该做什么？如何告诉人们他们需要它？我们要收多少钱？去市场策略是什么？这些核心问题一点都没变。

<details>
<summary>Original English</summary>

**Benedict Evans**: Paradoxically, the answer for a builder is actually super easy... Frame.io... In principle, you could have had that idea at any time in the previous decade. ... Most SAS companies are database rappers where somebody realized that here is this problem... And the hard part of that was not writing a bunch of SQL queries... It's all the other stuff around like what what should the code be doing and how would we tell people... and I don't think that has changed at all.

</details>

**Benedict Evans**: 我认为创业者分为三类：一类是寻找机会的，二类是相信某个技术趋势（如 Mobile 或 AI）的，三类是在过去十年里拼命想解决某个行业痛点的。我怀疑**第三类**产生的效果最好。你可以拿着 AI 这把锤子到处敲钉子，也可以从问题的另一端开始，感叹“现在我终于可以解决那个问题了”。

<details>
<summary>Original English</summary>

**Benedict Evans**: I suspect that it's the third category that produce the best outcomes. ... Yes, you can pick up AI and go around looking hitting everything with it. You know, it's a hammer and everything's a nail. Or you can start from the other end and think, you know, now finally I can solve that problem.

</details>

**Matt Turk**: 好的，Ben，我们真的可以聊上几个小时。非常感谢你再次参加播客，期待下次交流。

<details>
<summary>Original English</summary>

**Matt Turk**: All right, Ben, but we could quite literally go on for hours. This is so fascinating. ... Thank you so much for being back on the Mad Pod and um look forward to the next one.

</details>