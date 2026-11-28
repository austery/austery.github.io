---
author: a16z
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=lXkjXSul6yg
speaker: a16z
tags:
  - robotics
  - embodied-ai
  - automation
  - supply-chain
  - reinforcement-learning
title: Tutor Intelligence 创始人专访：全栈机器人平台与物理经济自动化
summary: Tutor Intelligence 联合创始人兼 CEO Josh Gruinstein 探讨了机器人在工业物流领域的落地路径。他指出美国绝大多数工厂处于自动化空白期，机器人需通过全栈平台、人机遥操作协同（Tutors）以及真实世界数据飞轮来实现商业化与规模化部署。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Josh Gruinstein
companies_orgs:
  - Tutor Intelligence
products_models:
  - Cassie
  - Sunny
media_books: []
status: evergreen
---
### 序言与背景介绍

>> 不管别人怎么说，在 2026 年的今天，我们拥有一个高度互联、相互依存的全球供应链。无论是美国公司还是中国公司，都在深入思考其长期战略究竟会是什么样？归根结底，每个人都在努力建设自己的工业产能。
<details><summary>Original English</summary>
>> No matter what anybody says, today in 2026, we have a highly interconnected, interdependent global supply chain. Both US companies and Chinese companies are thinking very hard about what does the long-term strategy of this look like? And ultimately, everybody trying to build their industrial capacity.
</details>

>> 我们看到很多机器人的商业计划书。很少有人去思考所有这一切最后机器人到底应该做什么。
<details><summary>Original English</summary>
>> We see a lot of robot pitches. Very few people thinking about what the robot is supposed to do at the end of all of this.
</details>

>> 我们把机器人卖给的对象，几乎都从未购买过机器人。几乎整个市场都是全新待开发的绿地（Greenfield）。现实是你必须构建一个全栈平台。Tutor 机器人已经协助制造并向美国消费者运送了超过 2.5 亿件产品。我们正在训练前沿的机器人 AI 模型，进行规模化机器人制造，并直接部署到供应链中规模最大的企业中。
<details><summary>Original English</summary>
>> Almost everybody we're selling a robot to has never purchased a robot before. Almost all of the market is Greenfield. The reality is you need to build a full stack platform. Tutor Robots have helped manufacture and ship over a quarter of a billion products to American consumers. We're training frontier robot AI models, manufacturing robots at scale and directly deploying into the largest businesses in the supply chain.
</details>

>> 机器人领域的产品创新是如何运作的？大多数公司还停留在 V1 阶段，而你们已经有了两款机器人，并且持续快速迭代。
<details><summary>Original English</summary>
>> How does product innovation work in robotics? Most companies are just on V1 whereas you're got two versions of the robot and you continue to iterate really fast.
</details>

>> 那么，Josh，感谢你的加入。我们今天请到了 Josh Gruinstein，他是 Tutor Intelligence 的 CEO 兼联合创始人，我们今天要聊聊机器人。在深入展开之前，能不能先简要介绍一下你自己的背景以及这家公司？
<details><summary>Original English</summary>
>> So Josh, thanks for uh for joining us. So, uh, we're with Josh Gruinstein, who is the CEO and founder, co-founder of of, um, Tutor Intelligence, and we're going to be talking about robots today. And so, maybe before we jump in, just give a quick background maybe of yourself and then the company.
</details>

>> 好的。我是 Josh。我在大约五年半前创办了 Tutor，核心假设是：如果你能直接把机器人部署到现实世界中、部署到物理经济中最需要机器人的各个地方，你就能开始建立起在整个物理经济中普及机器人所需的数据集、模型和供应链。我们目前大约有 160 人，主要位于波士顿。我们正在训练前沿的机器人 AI 模型，进行规模化机器人制造，并直接部署到供应链中最大的企业中。
<details><summary>Original English</summary>
>> Yeah. So, I'm Josh. I started tutor about five and a half years ago uh with the core thesis that if you could just start deploying robots out into the world into all the places in the physical economy where robots are needed the most, you could start to build the data sets, the models, and the supply chain that's needed to proliferate robots uh throughout the physical economy. So we're about 160 people based primarily in Boston and we're training frontier robot AI models manufacturing robots at scale and directly deploying into the largest businesses in the supply chain.
</details>

>> 也许可以聊聊……你看，我们见过很多融资宣讲，有很多公司空谈机器人，但实际上并没有部署机器人，或者至今还没有部署。
<details><summary>Original English</summary>
>> Maybe talk a little bit about like you know we see a lot of pitches there's a lot of companies that talk about doing robotics but don't actually deploy robots or have not yet.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而你们是少数几家真正实现规模化部署机器人的公司之一。能否谈谈目前的业务现状？
<details><summary>Original English</summary>
>> And you're one of the few companies has actually deployed robotics at scale. So maybe just talk about like the state of the business.
</details>

>> 好的。我们在全美各地都部署了机器人，从小型夫妻店到财富 50 强、财富 100 强企业都有。Claude 昨晚告诉我，据它估计，Tutor 机器人已经协助制造并运送了超过 2.5 亿件产品。
<details><summary>Original English</summary>
>> Yeah. Uh, we have robots deployed across the United States everywhere from small mom and pop businesses to Fortune50, Fortune 100 businesses. Claude told me last night that it estimates Tutor Robots have helped manufacture and ship over a quarter of a billion products.
</details>

>> 哇。
<details><summary>Original English</summary>
>> Wow.
</details>

>> 交付给美国消费者。所以可以说，大多数美国消费者在下游几层关系上都是 Tutor 的客户。我认为这源于公司的创立故事，也就是我们对机器人学习现状的审视。在我们看来，机器人智能和机器人软件显然是个瓶颈，对吧？60 年来，机器人一直是一种定制工程机械，
<details><summary>Original English</summary>
>> To American consumers. So like presumably most American consumers have are a tutor customer a couple layers down. Um I think this comes from kind of the origin story of the business which is us looking at the state of robot learning. It was obvious to us that robot intelligence and robot software was this bottleneck right? Robots for 60 years has been this custom engineered machines
</details>

>> 根本无法规模化扩张。所以我们创办公司时的假设是：如果我们能直接开始部署机器人，就能构建起标注数据集，帮助我们训练这些模型，并将这一价值传递给美国消费者。
<details><summary>Original English</summary>
>> that can't scale. Um yeah, so we we started the company with this thesis that if we could just start deploying robots, we could build uh the label data sets that help us train these models and deliver this value to the American consumer.
</details>

### 全栈系统与核心理念

>> 我们见过很多机器人 Pitch。其中 99% 都是从关于模型的某种洞察开始的，比如如何构建模型，或者关于数据形态的洞察，但极少有人去思考，
<details><summary>Original English</summary>
>> We see a lot of robot pitches. 99% of them start with some insights about the model and how you got to build the model or some insight about the data uh shape of the data that is and [snorts] very few people thinking about
</details>

>> 机器人在所有这些环节的末端到底该做什么。你们是从反向出发的，而且你们有一个洞察，那就是实际上你可以去“辅导”（tutor）机器人。这也是你们公司的名字。这种洞察从何而来？
<details><summary>Original English</summary>
>> the what the robot is supposed to do at the end of all of this. You started from the reverse and you had the insight that uh you could actually tutor the robot so to speak. Yeah, that's the name of your company. Where did that uh insight come from?
</details>

>> 这源于一个思想实验：地球上有 80 亿人，每个人都具备我们希望机器人拥有的基础物理智能。设想你拥有一款无限强大的软件，能够把地球上的任何一个人与任何一台机器人连接起来，并赋予该机器人智能。这有点像一种“天降神机”（deus ex machina），仿佛突然之间你拥有了无限的机器人智能。假设你把这一点视为理所当然。那接下来呢？问题并没有真正解决，对吧？你仍然需要真正地规模化制造机器人。如今在美国，机器人仍然是个作坊式的小众产业（cottage industry），即使在自动化程度最高的制造和物流行业，机器人也只是四舍五入的微小零头。所以那种规模制造并不存在，相关软件当然也不存在，客户也不存在，因为机器人根本做不了客户想让他们做的工作。因此我认为机器人技术不属于技术栈中的任何单一层级，它不仅关乎智能，不仅关乎硬件，也不仅关乎客户。而是要想明白如何将这三部分结合起来，在我看来，正是这三者的结合，才让你能够在其中任何一个层级上建立起成功的平台。
<details><summary>Original English</summary>
>> Uh it came from kind of this thought experiment where yeah, we had this insight that hey, there are 8 billion people on earth who all have this baseline physical intelligence that we want our robots to have. And so imagine you had infinitely powerful software that could connect any human being on earth to any robot and kind of embody that robot with intelligence. That's kind of like this ASX mocking of like suddenly you have unlimited infinite robot intelligence. Let's say you take that for granted. Now what? Right? you know the problem isn't actually solved right you still need to actually manufacture robots at scale right robots are this cottage industry today in the United States robots are rounding error even in the most automated industries like manufacturing logistics so that doesn't exist certainly none of the software exists and none of the customers exist because you know again the robots can't do any of the jobs that customers want robots to do so robotics is not I think any one layer of the stack it's not just about intelligence it's not just about hardware it's not just about the customer. It's about kind of figuring out how to put all these three pieces together and it's the combination of all three that actually lets you build in my view a successful platform at any one of those layers.
</details>

>> 是的。在内部我们常说，机器人公司是终极的系统公司。
<details><summary>Original English</summary>
>> Yeah. Internally, we talk about robotics being the ultimate systems company.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而不是偏废其一。
<details><summary>Original English</summary>
>> As opposed to being one one or the other.
</details>

>> 不过有意思的是，这也正是我一直想问你的一个问题：你拥有相当深厚的技术背景，麻省理工学院（MIT）机器人方向，没错吧？但是每次我和你交谈，感觉就像是在跟一个运营专家说话，聊的是单位经济效益、运营和供应链。
<details><summary>Original English</summary>
>> Well, you know what's funny about this though, which is um and it was a question I wanted to ask you is uh you've got a pretty deep technical background, right? you know, and like uh I mean MIT Robotics, is that fair? Um but whenever I talk to you, I feel like I'm talking to an operations guy that talks about like [laughter] that talk about unit economics and operations and supply chain. So I mean
</details>

>> 甚至是市场拓展（GTM）专家。
<details><summary>Original English</summary>
>> and even the go to market guy [laughter]
</details>

>> 市场拓展专家。所以你的这种转变非常彻底。这可能是一个开放式的问题，但我一直在想：难道更难的问题实际上是这些业务和运营层面的事吗？
<details><summary>Original English</summary>
>> go to market guy. So it's kind of you've done this like the transformation is complete and so like may maybe this is kind of an open-ended question but like I've always wondered like is the harder problem here actually that stuff?
</details>

>> 不。但我认为关键在于你必须把所有事情都做了。当我单纯作为一名机器人工程师、只攻克这个问题的技术面时，我认为我作为机器人专家的优势就在于非常注重全栈。我愿意去思考制造和硬件，愿意去思考 FPGA 和 ASIC。如果你像我一样把机器人视作这种终极的系统问题，那么向前推进的唯一途径就是尽可能跨越技术栈的多个层级，去寻找所有巧妙的权衡取舍。
<details><summary>Original English</summary>
>> No. But but I think you have to do all of it is kind of the thing. And like I when I was just a roboticist, right, and only working on the technology side of this problem, I think my strength as a roboticist was that it was very full stack. And I was willing to think about the manufacturing, the hardware. I was willing to think about FPGAAS and AS6. Like if you view robotics in the same way that I do that it's this like ultimate systems problem, the only way you can make forward progress is by figuring out all of the clever trade-offs across as many layers of the stack as you can.
</details>

>> 如果你丢弃技术栈中的某一层，心想“好吧，我们不去碰那一层”，
<details><summary>Original English</summary>
>> And if you throw out one of the layers of the stack and you're like, well, we're not going to touch that,
</details>

>> 你就直接抹去了 90% 用于取得进展的权衡空间。
<details><summary>Original English</summary>
>> you've eliminated 90% of your trade-off space to make progress.
</details>

>> 很有意思。
<details><summary>Original English</summary>
>> Interesting.
</details>

>> 后来创业时，我变得非常清楚：机器人技术实际上并不是狭义上的“模型、硬件、软件”全栈，而是“模型、硬件、软件、供应链、客户、产品”这样一个大全栈。
<details><summary>Original English</summary>
>> And then starting a business, it became really clear to me that like, oh, okay, robotics is not actually full stack like model, hardware, software. It's full stack like model, hardware, software, supply chain, customers, product, right? It's like
</details>

>> 确实。同样，你可能会问这样一个问题：为什么机器人领域过去一直行不通？曾有许多机器人初创公司，我认为没有哪家初创公司取得了真正巨大的商业成功。为什么会这样？我认为原因之一是没有掌握“智能”这一核心基元，而智能本可以让系统的单位经济效益达到某种水平；第二点在于，这是一个高度解构（disaggregated）的市场，参与者无数，彼此都在试图互相配合，但在机器人领域，我们现实中真正需要的是能够在整个全栈上进行权衡取舍的能力。
<details><summary>Original English</summary>
>> exactly and similarly you ask the question like why hasn't robotics worked, right? There's been a lot of robot startups. I would argue no robot startup has been like really massively economically successful. Um why is that? And I I think it's because one, you don't have this core primive which is intelligence and that lets you kind of bring the the um unit economics of the system to a certain level. Um but two, it's that it's the super sort of disagregated market and you have infinite players and they're all trying to work with each other and the reality of what we need in robots is to be able to make trade-offs across the full stack.
</details>

### 横向与垂直一体化

>> 这很有意思。这也是我们的一个观察，用这种方式表达非常恰当：大多数机器人公司都是从横向切入，最终全都走向了垂直。
<details><summary>Original English</summary>
>> You know it's interesting. So this is an observation that we have had and it's it's interesting to articulate it this way which is most robot companies start horizontal and they all go vertical.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 每一家都是如此。他们一开始可能只是“我们做了一个模型”之类的，然后就开始买 3D 打印机自研硬件。你认为这是否是因为市场太不成熟，就像早期汽车工业那样？还是说你认为这是这个领域固有的特性，即便过 20 年，也必须垂直化，只因运动的经济性或其他因素的要求？
<details><summary>Original English</summary>
>> Every one of them like they literally start like we have a model or whatever and then you know they start like buying 3D printers and do you think that that is kind of because the market is so immature like you had to do in the early days of cars or like you think it's actually inherent in this domain like like even in 20 years you will have to verticalize just because the economy of movement or something requires that
</details>

>> 不，我认为这是市场成熟度的问题，在早期的计算机市场中也能看到类似现象。因此对我们来说，问题就变成了：如何构建通用的平台，让人们能够去建立非机器人专属的商业业务？如今我们拥有所有这些出色的软件企业，运营它们的人不需要去操心芯片架构。如何在机器人所在的物理世界中实现这一点？如何着手构建那样的平台？我同意你的观点，以往人们试图通过聚焦在技术栈极其狭窄的单层来解决这个问题。而在我们看来，现实是你必须构建一个全栈平台。要检验这个全栈平台是否真正行之有效，唯一的办法就是在这个平台之上拥有成功运转的业务单元。
<details><summary>Original English</summary>
>> no I think it's a maturity in the market and you can see similar things in like the early computing market. And so to us, the question then becomes, okay, how do you build kind of the general platforms that let people build businesses that aren't robotics businesses, right? We have all these incredible software businesses today and the people who run them don't have to think about chip architectures, right? Um, how do we make that possible in the physical world with robotics and how you go about building that platform? And I agree with you, people have tried to solve that problem by thinking about very narrow layers of the stack. And in our view, the reality is you need to build a full stack platform. And the only way to know that that full stack platform really works is to actually have successful business units operating on top of it.
</details>

>> 你是否认可物理世界与数字世界存在差异，算力之所以能够横向化，是因为拥有清晰且普遍适用的抽象层，而在物理空间导航等领域则并非如此？
<details><summary>Original English</summary>
>> I mean I mean are you open to like it being the case that actually the physical world is different than the digital world and the reason we horizontalized compute is because you have clean abstractions that are generally applied and that's just not the case for like navigating you know physical space or
</details>

>> 我认为人形机器人（humanoid）的精妙之处恰恰就在于它也是同一种清晰的抽象。想想看什么是 CPU？它是一种通用计算机器，并没有针对每一种用例进行完美优化，但它足够通用，可以运行大多数计算任务。
<details><summary>Original English</summary>
>> I think the beauty of something like a humanoid is it's the same it's that clean abstraction right you think about like what is a CPU and it's this general computing machine and it's not perfectly optimized for every use cases right but It's general enough that you can run most computing worlds.
</details>

>> 哦，那是你在人体形态内的横向组件。但举个例子，你会用同样的“大脑”或子组件去造人形机器人，又去造无人机或其他构型的机器人吗？
<details><summary>Original English</summary>
>> Oh, but that's so that's your horizontal component within the human. But but for example, would you use the same you know brain or you know like sub components to make a human as you would to like make a drone or to make some other form
</details>

>> 构型不同则不会。但你可以在计算领域做同样的类比：我们有 CPU、GPU，也有 ASIC，对吧？所以我认为这取决于市场的成熟度：起初你处在一个针对定制机器进行专业化分工的世界，因为那是市场唯一能支撑的形式；接着你迈向通用化，在机器人领域这表现为人型及类似的形态；最终突破达到那种成熟分工。
<details><summary>Original English</summary>
>> factor? No, but you can make that same analogy in compute right we have CPUs, we have GPUs, we have AS6, right? So I think you track the maturity of the market and you start in this world of specialization custom machines because that's the only thing the market can support. you move towards general purpose and in robotics this is going to look like humanoids and similar form factors and then eventually you kind of break past to uh you know that resp.
</details>

### “Tutor” 的内涵与数据生成模式

>> 为什么这家公司叫 Tutor Intelligence（导师智能）？
<details><summary>Original English</summary>
>> Why is this thing called tutor intelligence?
</details>

>> Tutor 创立时抱有这样一个论点：存在一个由人类智能构成的完整互联网在运转，人们在社交媒体上发帖、写电子邮件，这个人类智能网络通过自然行为的附带产出，为大语言模型和其他数字世界模型创造了极好的数据集，可用于训练通用模型。问题在于，我们在物理世界中的工作并非如此。比如我端起咖啡杯，没有人知道，也没有人记录下我指尖施加的所有压力以及空间位姿。因此我们不具备这种数据资产。Tutor 背后的核心思路是：与其试图去寻找一种在零数据下凭空构建机器人智能的算法——在我们看来，这完全是一道胜算渺茫的难题，因为计算机视觉和自然语言处理的发展都不是这种路径——那何不在真实世界中建立起一个机器人网络？我们让机器人与人类遥操作人员相连接，我们称他们为“导师”（tutors），由他们来教导机器人如何执行新任务。就像互联网通过日常行为顺带创造了训练前沿模型的数据集一样，我们也可以对机器人做同样的事情，构建起机器人训练数据的互联网。而且这会带来所有这些绝佳的涌现特性：突然之间，建立这个网络不再是一项纯粹消耗巨资的项目，因为在你建设网络的同时，你也在创造巨大的经济价值；通过部署这些机器人并收集数据，你让所有人的商品变得更便宜。因此在一种非常独特的方式上，这形成了一个正和博弈。所以当我们考虑给公司起什么名字时，它并不完全是纯粹的人工智能，虽然有人工智能的成分，但归根结底是我们正在构建的用于连接和控制这些机器人的“导师智能”。
<details><summary>Original English</summary>
>> So, Tutor was founded uh kind of with this thesis that there is a whole internet of human intelligence that isworked right that is posting on social media that's writing emails and that network of human intelligence for LLMs and other kind of digital world models by natural emission has created this beautiful data set that we can use to train general purpose models. And the issue is our work in the physical world is not similarly, right? Like I pick up my coffee cup and nobody knows, right? Like nobody recorded all of the pressures of of my fingertips and where they were in the poses. And so we don't have this asset. Um and the core idea behind tutor is what if instead of trying to fill find kind of this algorithm where from no data we could build robot intelligence. And for us we were like yeah that that seems like a problem that's rigged against us, right? That's not how this worked in computer vision. It's not how this worked in NLP. What if we could build this network of robots out in the real world? We could connect them with human teley operators, which we call tutors uh that teach the robots how to do new tasks. And in the same way, the internet kind of by a mission created this data set to train these frontier models. We can do the same with robots and we can build this internet of robot training data. And there all these beautiful kind of emerging properties where like okay, suddenly it's not this massive capital project. it is to go build this network, but also you're creating incredible economic value as you're doing it, right? You're making everybody's goods cheaper as you deploy these robots and collect this data. And so it's very positive sum, I think, in this very unique way. Um, and so when we thought about, okay, what are we going to name this business? Um, you know, it's not strictly artificial intelligence. There's some artificial intelligence, but it was ultimately like this tutor intelligence that we're building that was connecting and controlling these robots.
</details>

>> 这确实是个绝妙的洞见。有趣的是，我们在投资前与客户交谈时，大多数人似乎并不知道、甚至根本不在乎，
<details><summary>Original English</summary>
>> Yeah, that's an amazing insight. And the funny thing is when we talked to our customers before we invested, most of them didn't seem to know or didn't even seem to care
</details>

>> 背后是否存在导师，或者什么时候是导师在操作、什么时候是你们的自主学习模型在运行。这得归功于你们，把体验做得非常无缝。
<details><summary>Original English</summary>
>> that there was a tutor or when the tutor was operating and when the your learning model was operating and that credit to you guys that you made this very very seamless too.
</details>

>> 对我来说，这是机器人表现良好的信号。你希望得到的反馈是：“我大批量生产的洗发水现在每件成本便宜了 5 美分。”如果反馈是“这台机器人长得很漂亮”，那它大概率是一台非常糟糕的机器人。
<details><summary>Original English</summary>
>> Yeah, this is to me a signal that you know the robots are good, right? You want the feedback to be like my shampoo is that I'm manufacturing at volume. It's now 5 cents cheaper than it was. If the feedback is like the robot is pretty, it's like a probably really bad robot. [laughter]
</details>

>> 那么未来的目标是完全不再需要导师，还是说这并不重要？
<details><summary>Original English</summary>
>> Is the goal to not have tutors in the future or does it matter?
</details>

>> 我们在一个非常务实的层面上思考这个问题：导师在运营上的复杂度是多少？导师的经济影响是什么？想想用 H200 芯片提供模型推理服务的成本是多少？你可以据此计算出成本、以及该 H200 的占空比和利用率。对人类智能也可以进行极其类似的思考：你真正需要从人类那里获得、而目前模型还无法提供的异构智能特征是什么？随后这就演变成一个单位经济效益问题：为了让模型达到最后的几个 9，你需要投入多少工程研发，相比之下使用导师又需要多少成本？回到我们之前讨论的，为了让这种业务跑通，你希望尽可能在所有这些地方拥有充分的权衡空间。
<details><summary>Original English</summary>
>> We think of it like at a very pragmatic level of like what is the operational complexity of tutors? What is the economic impact of tutors? Right? Like think about what is the cost to serve models with an H200, right? Right? And you can math that out and what's the duty cycle and utilization of that H200. And you can think very similarly about human intelligence, right? What is sort of the heterogeneous profile of intelligence that you really want from humans that you can't get yet from your models? Um, and then it becomes a unit economics question, right? Like how much engineering do you have to do to get that last nine uh out of your models versus using tutors? And really, you know, going back to what we were talking about, you want to be able to make as many trade-offs here as you possibly can to make a business like this work.
</details>

### 数据分布、仿真与前沿模型

>> 人们很容易认为生成式 AI 的经济奇迹也会在这里上演。生成式 AI 的奇迹在于：你用某种分布的数据去训练这些模型，结果证明大致相同分布的数据在经济上就具有可行性。比如你用图像训练它，人们需要图像；用文本训练它，人们也需要文本。基本上可以说是输入什么分布，输出就满足什么分布。
<details><summary>Original English</summary>
>> I mean, the, you know, um, it's tempting to say that like the economic marvel that happened with generative AI could also happen here. And the kind of the the marvel that happened with generative AI is like you you train these, you know, these models with, you know, some distribution of data and it turns out basically the same distribution is economically viable, right? It's like you train it on images and people want images. you trade it on text and people like you know it's like kind of distribution in distribution out.
</details>

>> 但在这些机器人身上，情况显然不一定如此。
<details><summary>Original English</summary>
>> It's not clear that this is actually the case
</details>

>> 你可以用某种分布的数据去训练它，但实际需要的任务可能刚好稍微超出了这个分布范围。
<details><summary>Original English</summary>
>> with with these robots right you could train it on like you know a distribution of data but then like actually what you need is just slightly out of that distribution so like
</details>

>> 你对这套系统的扩展方式、收敛情况以及最终能否撤掉导师有着最直接的观察，你在这方面的直觉是什么？
<details><summary>Original English</summary>
>> how I don't know you probably have the best visibility into how this scales and what the convergence is and whether you can actually remove tutors like what is your intuition on on that?
</details>

>> 我认为这是一个核心大问题，最终归根结底在于数据到底是什么以及从何而来。互联网的魔力在于：如果你作为一家公司在应用层为软件工程师提供加速软件开发的工具，你自然就会汇聚所有这些极具经济价值的工作流数据。只要你作为一个企业能赚钱，你大概率也在作为企业产出数据，经济激励是完全一致的。对于机器人来说也是同样道理：如果你的做法是“我们在所有人头上绑上摄像头，派他们走遍印度尼西亚去收集执行 X、Y、Z 任务的数据”，你根本没有任何保证，全靠猜测；并没有市场的“无形之手”引导你确保这些数据真正具有经济价值。但如果数据是业务运作的自然副产物，即机器人在真实的客户现场工作，客户为机器人完成的任务付费，你就能百分之百确信这些数据是具备经济价值的。
<details><summary>Original English</summary>
>> I think this is one of the big questions and I think really it ultimately comes down to like what is the data and where are you getting it from? Yeah. And the magic of the internet right is like if you are um a company and you provide at the application layer tools for software engineers to accelerate their software development you are naturally inflow of all of this really really really economically valuable work. Right? If you can make money as a business um then you're probably also making data as a business. Right? those like economic incentives are aligned. And similarly for robots, if you're like, "Okay, we're just going to strap cameras on everybody's heads and send them throughout Indonesia to collect data doing X Y and Z." You you have no guarantee, right? You you can guess. Um but there's no, you know, invisible hand of the market that's guiding you to ensure that that data is actually economically valuable. But if it's actually this like kind of emission byproduct, if you have robots in real customer sites that customers are paying for, for those robots to do that task, you know for sure that that data is economically valuable.
</details>

>> 这难道不也取决于解空间的维度吗？有没有可能具有经济价值的工作维度过高，你可以解决其中的 90%，但剩下的 10% 在相当长一段时间内仍需要人类来做，只因为获取对应的数据集需要在太长时间内使用过多导师？
<details><summary>Original English</summary>
>> Doesn't it kind of depend on also the dimensionality of the solution set though? Like it could it could be the case that like the economically valuable stuff is so high dimensional that you could like you could solve 90% of it but the last 10% you know you'll you'll need a human being to do for a while just because like getting that data set is just going to require too many tutors over two period of time
</details>

>> 这种结果也许完全没问题，从经济效益角度来说你也许完全能接受；这也可能是其他形式数据发挥作用的地方。我们不是原教旨主义者，我们愿意做任何权衡。我们非常乐于使用仿真来拓宽这些数据分布，也非常乐于使用互联网规模的数据来拓宽分布。除了真实世界的机器人数据之外，我们的工具箱里还有很多其他工具。
<details><summary>Original English</summary>
>> and that might be fine right you might be willing to accept that on the economics that also might be a place where other forms of data matter I think we're not purists uh again we're willing to take any trade-off right we love using simulation to kind of widen these data distributions. We love using like internet scale data to widen these distributions. So we have a lot of tools in our toolbox other than that real world robot data
</details>

>> 能否多谈谈仿真以及这些工具，以及像 Astra 这样的模型在这方面带来的影响？
<details><summary>Original English</summary>
>> and talk a little bit more about the simulations and these other tools and the impact models like Astra are having on that
</details>

>> 这在机器人领域似乎引发了另一波令人兴奋的小高潮。
<details><summary>Original English</summary>
>> seems to be another cottage industry of excitement for the robotics
</details>

>> 对，你们是如何利用这些的？
<details><summary>Original English</summary>
>> world right how are you using that
</details>

>> 这是一场翻天覆地的巨变。过去有一段时间，大家都知道所有关于世界的常识都蕴含在这些模型中，但它们无法表达出来，缺乏空间推理的最后一公里，无法把类似 GPT 模型所掌握的知识与动作扩散 Transformer 头（Action Diffusion Transformer head）所能理解的内容联系起来。如今情况改变了：前沿实验室目前正在使用 3D 空间数据（如 CAD 和 3D 建模）对其模型进行后训练，
<details><summary>Original English</summary>
>> it's it's a sea change right I think we lived in this world for a while where everybody knew that all of this general knowledge about the world was baked into these models but they couldn't really express it, right? They didn't have that last mile of spatial reasoning to connect the dots from the stuff that like uh you know a GBT model knows to something that an action diffusion transformer head can know. Um and that's changed, right? The labs are now post-training their models on 3D spatial data like CAD and um
</details>

>> 顺便提一句，他们之所以这么做，是因为有直接的经济激励，存在真实的商业市场，
<details><summary>Original English</summary>
>> like 3D modeling, which by the way they're doing because there's this direct economic incentive because there's a real market for it.
</details>

>> 所以他们能立刻变现。事实证明，这正是我们模型所需要的空间推理能力。因此我认为我们被直接推向了未来好几年，因为我们开始能够把这些大型前沿模型中所具备的通用智能应用到机器人上。
<details><summary>Original English</summary>
>> um so they can immediately monetize it. And it turns out that's the exact spatial reasoning that our models need. So I think we've been catapulted many years ahead in the future because we're starting to be able to use all of that general intelligence that lives in these big frontier models for robotics.
</details>

>> 由于这是一个系统问题，这对你们而言净效应是加速推动。
<details><summary>Original English</summary>
>> And because it's a systems problem, the net effect for you is acceleratory.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而不是放慢脚步，或者担心有人会来抢走你们的饭碗。
<details><summary>Original English</summary>
>> As opposed to slowing you down or saying somebody's going to come and eat your lunch.
</details>

>> 没错。我们经历过几次这样的技术浪潮。我们在 2021 年创立这家公司，最初用的是卷积神经网络（CNN）。我们经历过每一次巨变，而始终不变、永远具备核心价值的，就是数据流。独一无二能够持续运转的始终是数据流。至于架构上的上百万种技巧，只要有助于加速飞轮，那就去采用；只要有助于部署更多机器人、收集更多数据、扩大制造规模、完成更多任务，那就值得去做。但归根结底，我们认为在企业中具有长期代际价值的，是飞轮和闭环本身。
<details><summary>Original English</summary>
>> Yeah. No, we uh and we've seen a couple of these uh happen, right? We started this business in 2021. We were doing this initially with convolutional neural networks, right? So like we've we've gone through every C change and and the thing that is always valuable is the flow of data, right? And the flow of data is is always the thing that uniquely you can do. And it's like yeah, those like the a million architectural tricks like do them if it helps you accelerate the flywheel, right? if it helps you deploy more robots, collect more data, manufacture at a bigger scale, do more tasks, like they're worth doing. Um, but but ultimately we think the thing that has kind of the long-standing generational value in a business is the flywheel and loops themselves.
</details>

### 自研硬件与机器人构型：Cassie 与 Sunny

>> 能否具体讲讲你说“制造机器人”是指什么？在这个光谱的一端，就像是买一台宇树（Unitree）机器人，
<details><summary>Original English</summary>
>> Can can you talk a little bit about what you mean when you say you build robots? Like I think on one end of the continuum it's like you buy a unit tree.
</details>

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后你对它进行提示（prompt）；另一端则是自己去机加工零件。你们处在什么位置？
<details><summary>Original English</summary>
>> You know, and you like prompt it and the other end, you know, like whatever you're like machining parts like where are you in this?
</details>

>> 好的。给大家提供一个背景信息：在 2025 年，美国总共部署了 38,000 台工业机器人工作站，这个数字相较于整体体量微乎其微。
<details><summary>Original English</summary>
>> Yeah. So um for context for everybody in 2025 the United States deployed uh 38,000 industrial robot workups which is tiny compared to roughly
</details>

>> 这还是算上了发那科（Fanuc）以及老牌厂商。
<details><summary>Original English</summary>
>> counting the fuks and the old
</details>

>> 算上了发那科。但也就仅此而已了。美国根本没有部署任何宇树机器人，如果真有任何规模都会体现在统计数据中，但实际上可能基本为零。因此，现有的机器人供应链既太小，而且正如你指出的那样，方向也不对。发那科和 ABB 制造的机器人大部分并不在美国制造；即便在美国制造，它们制造的也是专为系统集成商设计的设备，旨在进行快速重复运动，并不是基于与前沿模型协同设计所需的权衡取舍而打造的。因此，在硬件方面我们基本上是从零开始。为了规模化部署机器人，Tutor 实际上被迫自主设计和制造硬件。当然对于今天的我们来说，我们并不自研执行器（actuator），也不自研相机。有一整层零部件我们是从原始设备制造商（OEM）那里采购的，他们是在以大得多的规模进行生产。但是真正的机器人本体——也就是能到处行驶、装有机械臂并能完成所有任务的设备——实际上是我们自己在马萨诸塞州沃特敦（Watertown）规模化制造的。
<details><summary>Original English</summary>
>> the fukes right but but that's it right nobody nobody deployed any unitries in the United States and to any they would have shown up in those numbers but they were probably zero um and so the supply chain that exists for robots is both too small and as you called out wrong right like the robot spots that Fenuk and AB are building. They're mostly not building the United States, but but even when they are building them in the United States, they're building these objects that are designed for systems integrators, that are designed for fast repetitive motions. They are not cut from the set of trade-offs that you would want to co-design with frontier models. Um, and so we're kind of starting from scratch on the hardware side. Um, so tutor in order to deploy robots at scale has actually been forced to design and manufacture our own hardware. for us today, like we're not building actuators, right? So, we're not building cameras. There's a whole layer of stuff that we're sourcing from OEMs where they're manufacturing at a much larger scale. But the actual robot itself of, you know, the thing that drives around and has the arm on it and can do all the tasks we actually are building uh at scale uh in Watertown, Massachusetts.
</details>

>> 能否谈谈机器人的形态学（morphology）？是叫形态学还是解剖结构？
<details><summary>Original English</summary>
>> Can you talk about the morphology of the robot? Is that what is that called? Morphology, anatomy.
</details>

>> 都可以。
<details><summary>Original English</summary>
>> You can use whatever.
</details>

>> 它们长什么样？
<details><summary>Original English</summary>
>> What do they look like?
</details>

>> 它们长什么样？我们造了两款。
<details><summary>Original English</summary>
>> What do they look like? We make two.
</details>

>> 其中一款……
<details><summary>Original English</summary>
>> Um, so one robot we make.
</details>

>> 看看他网站上的照片。请继续。
<details><summary>Original English</summary>
>> Look at his website mine. Yeah, go ahead.
</details>

>> Cassie 属于干粗重活的机型。Cassie 专为繁重工作设计，配有单机械臂和大量吸盘，由 2 亿到 4 亿参数规模的基础模型驱动。这源自 Tutor 在 2021 年起步时的思考：基础模型能为机器人做什么？它们可以预测抓握的可行性（affordance grasps），然后由机器人去执行。这是可规模化制造的硬件、模型实际能力以及庞大市场需求三者协同设计的产物：在美国物理经济中，任何东西都必须用托盘或纸箱运输，因此存在大量需要人工搬运托盘和箱子的繁重体力劳动。Cassie 就是这种协同设计的成果。我们对它进行大规模制造，并部署到制造业与物流业中各种各样的企业中。我们的第二款机器人叫 Sunny。Sunny 算是一种工业级半人形机器人。这就好比你看着一台机器，并提出要求：我需要这台机器人在工厂里以人类的工作速率和可靠性连续运行 3 到 10 年。于是你会得出一组略有不同的设计决策：Sunny 是轮式而非足式，因为大多数室内工业环境都是抛光平整的地面；它拥有高得多的有效载荷能力，移动速度快得多，并且符合工业协作安全标准，能够与人类协同作业。我们在波士顿的数据工厂里有 100 台 Sunny 正在运行，收集数据供内部使用并推进我们的研究计划。同时，我们目前也有越来越多的 Sunny 部署在现实世界中，执行更灵巧的双手操作任务。
<details><summary>Original English</summary>
>> Uh, so Cassie, Cassie is kind of uh a brute, right? Cassie is designed to do heavy duty work. It has a single arm and a lot of suction cups and it's powered by foundation models and like the 200 to 400 million perimeter range and kind of came out of this world that tutor was started out of in 2021 of like what can foundation models do for robots? They can predict kind of affordances grasps that you can go then execute. Um, so it's this co-design of the hardware that you can manufacture at scale, what your models can actually do, and actually a big market need where in the United States, anything in the physical economy has to be transported on a pallet or in a cardboard box. So there ends up being an enormous amount of physical human handwork of transporting pallets, cases um, by hand. And so Cassie is kind of the result of that code design. and we manufacture it at a very large scale and we deploy it to a big diversity of businesses across manufacturing logistics. Our second robot is called Sunny and Sunny is kind of an industrial semi-humanoid, right? It's as if you said you were looking at a unit and you were like, I need this robot to run for 3 to 10 years in a factory at human rates and reliability. And so you end up with a slightly different set of design decisions. Sunny is wheeled, not legged, because most indoor industrial settings have polished ground floors. um it has a much higher payload capacity and can move much faster and has uh industrial collaborative safety standards that enable it to operate around humans. And so we have 100 sunnies operating in Boston in our data factory collecting data for internal use and advancing our research agenda. And then we also now have a growing fleet of sunnies out in the real world uh doing more dextrous by manual manipulation.
</details>

>> 你如何看待针对不同形态的产品线宽度？是用 3 款机器人就能覆盖大部分实用市场，还是需要 30 款？
<details><summary>Original English</summary>
>> And do you see how broad do you see this product line of different robot form factors? Is it can you capture a big chunk of the useful market with three of them or do you need 30 of them?
</details>

>> 这取决于你如何定义实用市场，以及你的目标领域。如果只局限在制造和物流领域，Sunny 和 Cassie 目前大概能覆盖 80% 到 90% 的工作，它们正是针对这些应用场景而设计的。
<details><summary>Original English</summary>
>> Depends how you define the useful market. Like where do you want to go? If you want to just live inside of manufacturing logistics, Sunny and Cassie today can probably do 80% to 90% of the work, right? These are designed for those cuts. Uh
</details>

>> 能否描述一下具体是哪些工作？
<details><summary>Original English</summary>
>> what maybe just describe what that work is because
</details>

>> 大众可能并不普遍了解。
<details><summary>Original English</summary>
>> yeah I'm not sure it's broadly understood.
</details>

>> 好的。大多数人对美国工业基础或制造物流的印象往往来自电视节目《造物小百科》（How It's Made）。不知道你们看没看过。
<details><summary>Original English</summary>
>> Yeah. So most people have this mental picture of what sort of the industrial base or manufacturing logistics look in the United States which comes from um the TV show how it's made. I don't know if either of you have seen this.
</details>

>> 当然看过，经常看。
<details><summary>Original English</summary>
>> Yes. Of course. Of course. Yeah.
</details>

>> 你会看到各种鲁布·戈德堡式（Rube Goldberg）复杂的机械杠杆，画面里看不到任何人类，对吧？仿佛有人建造了一台机器，而这台机器本身就是一座工厂。
<details><summary>Original English</summary>
>> And you see these like Rube Goldberg and machines of levers and it's like yeah you don't see any humans in those pictures, right? Somebody built a machine that is the factory
</details>

>> 那种情况确实存在。如果有，他们很可能拍下来放进了《造物小百科》里，因为那是美国制造业和物流业最顶尖的 0.01%。但在那之下是什么光景？你走进那些上百万平方英尺的设施，看到的是一群人围在传送带或折叠桌旁用双手干活。对任何不来自这个行业和圈子的人来说，这都是令人震惊的。所以再看像 Cassie 这样的机器人，它承接的是大量极其繁重的体力活，这类岗位招工极难，员工每三个月就会流动一轮，从事这项工作的工人平均年龄在 55 岁左右，且即将退休。这时就可以用 Cassie 来做这些繁重工作。同样，对于 Sunny，你买过的几乎所有装在箱子里的东西，都是人工装进去的，这对大多数人来说都是个不可思议的事实；任何需要一定组装程度的工作——比如甚至像 iPhone，你可能以为是机器人把包装合在一起的，不是的，即使在最高级别的生产规模上，也是由人工完成的。
<details><summary>Original English</summary>
>> and that does exist. Uh, and if it exists, they probably filmed it and put it on how it's made, right? Because that's the top 0.01% of American manufacturing and logistics. Um, and so what's below that? And you walk into these million square foot facilities and you see a bunch of people uh standing around on conveyor belts or folding tables doing things by hand. And it's kind of shocking for anybody who doesn't come from this industry and community. Um, and so you look at a robot like Cassie and it's like, you know, a huge amount of work, which is backbreaking work that's really hard to hire for. There's a three-month turnover where your average age of the worker doing that work is 55 years old and about to retire. And it's like, okay, we we could use a Cassie to do that backbreaking work. And similarly, Sunny is like basically anything you ever bought that came in a box, a human had to put that in a box, which is a crazy revelation for most people. uh anything that requires any degree of assembly, right? Like even, you know, iPhones, you know, it you would assume it's a robot, you know, putting that packaging together. No, it's a person even at the highest level of scale.
</details>

>> 接着回到刚才的问题：你有一台带吸盘的单臂机器人，有一台双臂半人形机器人。
<details><summary>Original English</summary>
>> And then to his question, which is so like you have like the single arm with the sucker, you've got the two armed humanoid.
</details>

>> 对。它们有什么是做不了的？
<details><summary>Original English</summary>
>> Yeah. What can't they do?
</details>

>> 它们做不了什么？下一步又该走向哪里？
<details><summary>Original English</summary>
>> Yeah. What can't they do? And where do you go from there? Yeah.
</details>

>> 它们无法到室外去，而室外应用非常吸引人。
<details><summary>Original English</summary>
>> So they can't go outside and outside is really really interesting.
</details>

>> 这是纯粹的移动能力（locomotion）问题吗？
<details><summary>Original English</summary>
>> Oh, is that just like a locomotion issue?
</details>

>> 不是移动算法的问题，而是硬件本体的问题。这些机器人是轮式的，虽然有一点抓地力，并配有铰接式的后肢结构，但它们无法在碎石路面上行驶。在建筑施工、在垃圾填埋场回收材料等场景中，机器人存在着巨大的机会。这类场景需要配有双腿的足式机器人。因此我认为这最终会成为我们具身形态谱系的一部分。同样，家庭场景中的机器人也是如此。你现在大概不会想在家里放一台 Cassie 或 Sunny，对家庭环境来说，它们在设备形态上太具工业感了。
<details><summary>Original English</summary>
>> It's not locomotion. It's the hardware, right? These these robots have wheels and they have like a little bit of traction, you know, uh they have like these articulating hind legs, but uh they can't drive over gravel, right? There's huge opportunities of robots in construction, robots reclaiming materials from landfills. Um we, you know, we need robots with legs uh for that. So, I think that'll eventually be part of our pantheon of embodiment. And then similarly, robots in the home. You probably don't want a Cassie or Sunny in your home just now. It's a little bit too industrial of a device.
</details>

>> 确实，看起来挺吓人的。
<details><summary>Original English</summary>
>> Yeah, they look scary. Yeah.
</details>

### 商业模式与客户接纳

>> 我们聊聊客户接纳的情况。进展如何？显然不仅限于“我招不到人所以有什么用什么”这种层面，
<details><summary>Original English</summary>
>> Yeah. Let's talk about the customer adoption side. How's how has that been? Obviously, not strictly from a I don't have people so I'll take whatever I can get.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 一旦把机器人放入装配线或其他流程中，他们在心态上的接纳过程是怎样的？
<details><summary>Original English</summary>
>> To once they have it in their assembly line or whatever it is. How does adoption go uh in terms of their mindset?
</details>

>> 这是一个很有意思的挑战，因为我们售卖机器人的对象几乎此前都从未购买过机器人。这也符合前面的统计数据：如果美国每年只部署 38,000 台机器人，如果十分之九的美国工厂和仓库根本没有任何机器人，那么几乎整个市场都是全新的空白领域。这些人知道老一代自动化是什么样子，因而先入为主地认为机器人不适合自己。我们打破这一僵局的方式并不是空谈 AI、模型或导师之类的概念。我们给他们打电话时会说：“您好，您是否考虑过以每小时 16 美元的价格租用一台机器人？”他们以前从未考虑过，这对他们来说是一个全新的商业主张。这样你就能约上会议，向他们解释我们正在做的事情，让他们产生兴趣并参与进来。通过创建这种在我们（机器人供应商）与客户之间实现真正激励一致的商业模式，我们分发机器人的速度比传统工业自动化行业快了好几个数量级。从第一次通话到签署合同，我们的平均时间是 40 到 60 天。从签署合同到机器人实际进入客户现场作业，平均时间约为 40 天。我们在一天之内就能在生产环境中把机器人部署就绪，通常在机器人进场后的最初几小时内就能完成。我们能够如此迅速地推进，不仅因为机器人是通用的智能机器，不需要进行定制化改动，直接从工厂发货给客户；而且因为我们没有让客户承担任何经济风险，因此能够顺利吸引他们入局。
<details><summary>Original English</summary>
>> Yeah. It's an interesting challenge because almost everybody we're selling a robot to has never purchased a robot before. Um, and that kind of comes out of these stats, right? If the United States is only deploying 38,000 robots a year, if nine out of 10 US factories and warehouses don't have any robots, then almost all of the market is green field. And these people, you know, understand what this old guard of automation looks like and they assume a robot doesn't work for them. And so the way we break through that actually isn't by talking about AI or models or tutors or anything like that. We called them up and we're saying, "Hey, have you ever considered a robot for 16 bucks an hour?" And they haven't, right? That that's a new proposition for them, right? So, you can book a meeting and then you can kind of explain to them this thing that we're doing and get people interested and involved. Um, and kind of by creating that business model where there is that true incentive alignment between us as the robot vendor and the customer, we're able to run distribution of robots at velocities that, you know, are many orders of magnitude faster than traditional industrial automation industry. We have an average time um from uh that first call to a robot signing contract of 40 to 60 days. We have an average time from that signed contract to robots actually in the customer site of about 40 days doing work. Uh we stand up robots in production within a day. Uh often within the first couple hours that a robot is on site. So we're able to move very very very quickly because not only is the robot this generally intelligent, generally capable machine that we're not customizing, we're just, you know, shipping directly from the factory to the customer. Um, but we're not putting any sort of economic risk on the customer. So, we're able to get them on board.
</details>

>> 一旦部署之后，他们对人工与机器的态度会发生怎样的转变？
<details><summary>Original English</summary>
>> And once they deploy it, how do their attitudes about labor versus machines change?
</details>

>> 运营圈子非常务实，他们看到东西起作用，就会觉得这行得通，对吧？仅此而已。事实摆在眼前，它确实能完成工作。他们清楚知道还有哪些岗位需要做这类工作，于是说“那我们把它部署到所有那些岗位上去”。因此我们能够极其迅速地进行规模扩张，无论是小型企业，还是供应链中规模最大的企业，从单一场所部署一台机器人，扩展到跨多个场所部署十几台甚至更多机器人。
<details><summary>Original English</summary>
>> The operations community is really really fantastic because they see a thing work and it's like it works, right? [laughter] Like that's it, right? It's it's like, yeah, I I can see obviously it does the job. I know all the places where this job needs to be done. Let's go put it in all those places. So we've been able to scale up very very quickly both with small businesses um and to some of the largest companies in the supply chain from you know one robot in one site to you know a dozen plus robots across many sites.
</details>

>> 不过这很有意思，在生成式 AI 中存在一种社交心理因素，人们对自己使用的模型会产生依恋，且很难去替换模型。你在机器人部署方面的经验可以说比目前绝大多数人都丰富，你观察到的情况也是这样吗？他们是把机器人当成设备看待，还是开始把它视作某种实体和同事？
<details><summary>Original English</summary>
>> It it is interesting though because like like a lot of geni was like there's a social element where like people get very attached to their models and like it's hard to swap models and so I mean listen you probably have more experience deploying robots than most people alive at this point like are you saying the same thing like is it are they viewed like equipment or like they starting to be viewed like beings and co-workers?
</details>

>> 我看到过一条非常搞笑的推文，大意是说：“机器人在跑通之前叫机器人，一旦真正能用了，它就只是一台机器。”
<details><summary>Original English</summary>
>> Yeah. So I saw a very funny tweet which was um a robot is a robot unless it works in which case it's a machine. [laughter]
</details>

>> 我得去找找这话是谁说的。
<details><summary>Original English</summary>
>> I got to figure out the attribution.
</details>

>> 但现实中真的如此吗？
<details><summary>Original English</summary>
>> But is it real? Like is it
</details>

>> 现实中确实相当真实。
<details><summary>Original English</summary>
>> it's it's pretty real.
</details>

>> 确实是这样？一旦能工作，他们就只把它当成一件设备。
<details><summary>Original English</summary>
>> Is that what it is? Like they just view it as like a piece of equipment once it works.
</details>

>> 至少在工厂车间主管这一层级确实如此。不过有趣的是，在机器人领域，购买者并不是最终使用者。购买者通常是首席运营官（COO）或总经理，而使用者则是整天与机器人协同作业的工厂一线工人。在这一层面，你确实需要去培育工人和机器人之间的关系，因为我们并没有让整座工厂 100% 自动化，我们自动化的是工厂或仓库中的部分具体岗位。
<details><summary>Original English</summary>
>> Certainly at like the factory manager level. Yes. I think there's still the layer of like interestingly in robotics your buyer is not your user, right? Your buyer is like the COO or the general manager and the user is like a factory worker, right? Who's working with the robot all day long. And there you actually do need to cultivate the relationship between those workers and the robots because you know we don't fully automate 100% a factory. We we automate some jobs in a factory or warehouse.
</details>

### 人机交互与命名机制

>> 你在处理这种关系上是否有特定的理念？比如是否尝试让它们看起来更友善？是否更像同事还是更不像同事？会给它们增加语音交互吗？从哲学层面上你是怎么看的？
<details><summary>Original English</summary>
>> Do you have a philosophy on like how you even approach this? Like do you like try to make them look friend? Do you like to make them look more like co-workers or less like co-orkers? You make them talk like like how do you kind of view this philosophically?
</details>

>> 幸运的是，学术界有一个专门的研究领域叫 HRI（人机交互，Human-Robot Interaction）。
<details><summary>Original English</summary>
>> Yeah. Uh so very very luckily there is a whole school of academic research called hri human robot interaction.
</details>

>> 原来如此。
<details><summary>Original English</summary>
>> No idea. There you go.
</details>

>> 很多人在这方面做了大量思考，包括我学术背景中的一些同行。这里面有很多技巧。其中一个技巧是：每台机器人都有名字。
<details><summary>Original English</summary>
>> Yeah. A lot of people have spent a lot of time thinking about this um including a bunch of people from from my academic background. Um and there are a whole bunch of tricks. So one trick is uh every robot has a name
</details>

>> 这有助于与机器人建立情感联系。
<details><summary>Original English</summary>
>> and so that lets us actually build relationship with the robots. It also
</details>

>> 谁来给它起名字？
<details><summary>Original English</summary>
>> names it.
</details>

>> 主要是我们的制造技术人员。
<details><summary>Original English</summary>
>> Uh mostly our manufacturing technicians.
</details>

>> 也就是说是由你们命名，而不是客户？这不像养小狗，养了一只新狗你可以重新给它起名。
<details><summary>Original English</summary>
>> So okay so so you name it not the it's not like a dogs when you get a new dog you can rename it.
</details>

>> 当客户在 Tutor 扩大规模、追加复购订单时，他们就获得了给机器人命名的权限。
<details><summary>Original English</summary>
>> So when a customer expands with tutor when they when they do a repeat order then they're allowed to name the robots.
</details>

>> 就像船只不应该改名以防带来厄运一样，船名得保留，但小狗可以改名。
<details><summary>Original English</summary>
>> Oh, like you're not supposed to like rename a boat because bad luck. You got to keep the boat name, but you can rename a dog. So, like
</details>

>> 是的，新加入的机器人可以获得命名。这解决了问题，也赢得了客户。
<details><summary>Original English</summary>
>> Yeah. So, the new robots get to be get to be named. That solves it. And we get customers.
</details>

>> 这样他们亲自命名后会有更强的主人翁意识。
<details><summary>Original English</summary>
>> So, they get a higher sense of ownership now they've named it.
</details>

>> 完全正确。我们得到了非常强烈的反馈，比如有人用自己孩子的名字给机器人命名，有人用他们最喜欢的橄榄球运动员、最喜欢的流行歌星命名。人们会产生深厚的情感，因为机器人归根结底是在提供帮助，减轻他们的工作负担。如果你是工厂流水线工人，就不必再做那么多繁重的重体力活，有机会晋升到更高的职位，而且这些地方原本就招不到人；如果你是车间主管，你的管理工作也会轻松千百倍。
<details><summary>Original English</summary>
>> Exactly. Right. Um and we get like really strong signals like we had um people name the robots after their kids, right? Uh people named the robots after their favorite football player, their favorite pop star. Um, people get very attached because the robot ultimately helps, right? It makes their jobs easier. If you're a line worker in the facility, you're not doing backbreaking work as much. You're able to be elevated into a higher position and none of these places can hire. And then if you're a factory manager, your job is just a thousand times easier.
</details>

>> 你们最初使用的是什么命名规则？
<details><summary>Original English</summary>
>> What naming scheme do you use? Yeah. From when you
</details>

>> 我们一开始采用飓风命名法，后来……
<details><summary>Original English</summary>
>> We started off doing hurricane naming and then we kind of
</details>

>> 看来这并不……
<details><summary>Original English</summary>
>> So that's not
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 显然你没仔细读过那本人机交互的书。
<details><summary>Original English</summary>
>> You didn't read the HR eye book clearly.
</details>

>> 这个嘛，我也不清楚。
<details><summary>Original English</summary>
>> Well, it's I don't know.
</details>

>> 你可是学术界出来的。
<details><summary>Original English</summary>
>> You're an academic.
</details>

>> 客户并不知道“Britney”对应的编号代表什么。不过我们后来确实停止了这种方式，因为我们把字母表从头到尾轮换了太多遍，已经很难追踪记录了。
<details><summary>Original English</summary>
>> The customer doesn't know that Britney is, you know, nod 26 or whatever equals 2. It's um it's uh but we actually stopped because we kind of went through the hurricane. We went through the alphabet too many times to be able to keep track of it.
</details>

>> 那你们现在用什么方式命名？
<details><summary>Original English</summary>
>> Okay. So, what are you using now?
</details>

>> 我想技术人员就选任何能给他们带来快乐的名字。我们非常幸运且荣幸能在美国雇佣庞大的员工团队来协助制造这些机器人，他们也负责给机器人起名。
<details><summary>Original English</summary>
>> Uh I think the technicians just just pick whatever brings them joy. We we have a really wonderful and privilege to employ a big staff of people in the United States who are helping to build these robots [snorts] and they are also naming them.
</details>

>> 太棒了。
<details><summary>Original English</summary>
>> Awesome.
</details>

### 市场定位：中小企业 vs. 巨头定制

>> 在投资前调研时另一件让我吃惊的事情是：以往我们接触大多数机器人公司时，他们瞄准的都是那些体量庞大的巨头，比如财富 50 强这类大公司，因为这类企业看起来有足够的预算进行大量实验等等。而你们的客户绝大多数几乎都是本地中小企业。这背后蕴含着什么信号？还是一种深思熟虑的战略？
<details><summary>Original English</summary>
>> The other thing that surprised me when we first did the work before investing, most of the time when we talked to robotics companies, they're going after these humongous companies, right? Yeah. The big Fortune50 type companies that seem to have the budget for lots of experiments, etc. Yeah. Whereas I think a significant majority of your customers are all these local businesses almost. Yeah. And what does that I mean is there a message in there or or was it a conscious strategy or
</details>

>> 这包含很多维度的考量。首先，那才是市场的大头。美国制造和物流企业中，绝大部分都是小型或中型企业。如果你想服务这个市场，这就是必须覆盖的群体。其次，我们创立这家公司时，目睹了所有这些极具学院派风格、聚焦供应链的机器人初创公司纷纷涌现，但随后都未能真正成功。我们有机会去反思：这里究竟出了什么问题？我认为机器人公司犯下的一个重大错误就是：他们并不是真正的产品驱动型公司。他们的做法通常是：某家大公司遇到了一个非常特定的问题，愿意签一份光鲜的合作意向书说未来会扩大采购；于是初创公司花两年时间去构建一套极其定制化的系统来解决他们的问题；等部署上去后，大概率根本行不通，因为任何做过产品的人都知道产品绝不可能一蹴而就，打造产品需要反复迭代；退一步说，就算成功了，谁能保证该客户之后还会有这个需求？于是砰的一声，这家初创公司就倒闭了。
<details><summary>Original English</summary>
>> Yeah, it's a lot of things. One is that's most of the market, right? The vast majority of US businesses and manufacturing logistics are small businesses or mid-market businesses. Um so if you want to serve the market, that's what it takes to serve them. I think we also started this company um at a time we're seeing kind of all of these very academic supply chainoriented robotics startups kind of get started and then not really succeed. Um and we we had the opportunity of being like okay what went wrong here? And one of the big things I think that robotics companies get wrong is they're not actually really product companies. They're like okay some really big company has a very specific problem. They're willing to write us a shiny piece of paper that says they're going to expand with it. we're going to spend two years building a very custom system to solve their problem. We'll deploy it. Chances are it won't work because like anybody who's built products knows that you can't just one and done a product, right? Doing product requires iteration. And then even if it does work, who's to say that customer still has that problem and so boom, the company's done.
</details>

>> 我感觉自己接连看到这种情况发生了 5 到 10 次，以至于我们觉得要是这种事发生在我们身上，简直太丢人了。因此，与多样化的客户群体合作，构成了一个促使我们构建正确产品形态的绝佳倒逼机制——对我们来说，这种形态就是通用机器人。我们不想去建造一套只适用于大型工业客户 A 或客户 B 的复杂机器，我们想构建一个平台，拥有通用的机器人硬件本体，运行通用的机器人模型，能够立即投入作业。如果你能在两周内与一家中端市场客户签约并让机器人随即上线运转，这种产品和业务形态就与服务大客户完全不同，而这正是取得成功的标志。
<details><summary>Original English</summary>
>> And I feel like I saw this happen like five to 10 times in a row to the point of like, oh my, if this happened to us, like that would just be embarrassing. Um, and so I think working with a diverse range of customers is this beautiful forcing function for building the right shape of product which to us is a general robot, right? We don't want to build a Rube Goldberg machine that works really well for big industrial customer A or B. We want to build a platform that is generally capable robot bodies running generally capable robot models that can immediately get to work. Um, and if you can, you know, sign a contract in two weeks with a mid-market customer and have a robot running immediately after that, and that's a totally different type of product and business than your other customers, you know, you're being successful.
</details>

### 行业终局与产品迭代模式

>> 假设你们持续取得成功，从终局来看，你认为这个行业会是什么格局？是仅仅意味着相关作业成本更低、速度更快，还是品质提升、能做更多任务？在经济层面或生产力层面的最终收敛形态是怎样的？
<details><summary>Original English</summary>
>> How do you think in the limit um what the industry looks like assuming you continue to be successful? Is it just that um you know this work gets cheaper faster or does like somehow quality go up or can they do more things or like kind of like what is like the economic convergence or the productive convergence?
</details>

>> 我认为一切都会变得更好。存在整整一类商品，只要它们更便宜，人们就会购买更多；如果你认为这些商品是有价值的，那这对每个人都是好事。世界上也存在许多拐点。比如前几天我和一个人聊天，他在威斯康星州的一家房屋制造工厂流水线上工作。据他描述，在工厂里建造房屋目前比传统的现场建造大约贵 5%；但如果这些在工厂制造的房屋能比传统现场施工同等质量的房屋便宜哪怕仅仅 1%，开发商的所有需求都会立刻转向在工厂建造房屋的模式。类似的情况也适用于垃圾填埋场的材料回收以及许多其他市场。因此我们的期望是：如果 Tutor 真正取得成功，我们能够提供这种机器人的底层支撑，提供这种其他企业可以用来重塑物理经济的劳动力基质，让世界最终成为一个生活成本更低、更美好的地方。
<details><summary>Original English</summary>
>> Yeah, I think everything gets better. So there's a whole set of goods that um if they are cheaper we will buy more of them and if you believe those goods are valuable that's good for everybody. There are also a bunch of discontinuities in the world. Like I was talking with somebody um the other day who worked on the line in a housing factory in I think Wisconsin and they were describing how the houses that they're building are about 5% more expensive uh to build them in a factory than to do traditional construction on site. But if these houses were even just 1% cheaper than kind of the equivalent quality of house manufactured or constructed on site in the traditional way, all of the demand from developers would immediately go to that other shape of building these homes in a factory. And the same thing could be said about like reclaiming materials and landfills and a whole bunch of other markets. So I think our hope is like if Tutor is really successful, we can provide this robot substrate, this this labor force that other businesses can use to transform the physical economy and make the world ultimately uh a cheaper and better place to live in.
</details>

>> 你们未来会进入家庭场景吗？
<details><summary>Original English</summary>
>> Will you ever go in the home?
</details>

>> 我们并不固步自封，任何场景我们都可以去。
<details><summary>Original English</summary>
>> Um yeah, we we're not opinionated. We'll go anywhere.
</details>

>> 但我想仅从任务复杂度和安全性来看，这会是一个难度大得多的技术问题吧？
<details><summary>Original English</summary>
>> But I would imagine that that would be kind of a much tougher technical problem just from like I don't know complexity of task and safety and
</details>

>> 以及其背后的经济账，对吧？一台 Tutor 机器人在工厂里能创造多大经济价值，又有多少消费者愿意在家里为此买单？这笔账目前还不太算得过来。但这再次回到了我们的总体哲学：在技术栈尽可能多的层级上进行权衡取舍以建立立足点，开始构建平台；随着平台的建立，你在发展过程中需要做出的妥协权衡就会越来越少。
<details><summary>Original English</summary>
>> and the economics of it right like how many what is the economic value a tutor robot delivers uh in a factory and how many consumers are willing to pay for that in their home and it doesn't quite work out. Um but again that that comes back to our our overall philosophy is take trade-offs across as many layers of the stack as possible to get a foothold. start building the platform and as you build the platform you have to take fewer and fewer trade-offs over your time.
</details>

>> 机器人领域的产品创新是如何运作的？大多数公司还停留在 V1 阶段，而你们已经有了两款机器人，并且持续快速迭代。这与数字产品创新或其他领域有何不同？
<details><summary>Original English</summary>
>> How does product innovation work in robotics? I mean most companies are just on V1 whereas you're got two versions of the robot and you continue to iterate really fast. What is it different? How is it different than like digital product innovation or other categories?
</details>

>> 我们正试图让它与数字产品尽可能相似。我们自己制造机器人，这使我们有能力掌控制造流程，并探索如何每两周对制造流程推送一次改动。我们每天向机器人推送代码，或者每两周发布一次大版本更新，并构建了海量基础设施来支撑这种级别的迭代速度。我们在组织内部打造了一种非常独特的产品职能架构，产品团队实际上与客户成功和现场实施团队紧密坐在一起，作为一个大团队共同协作。因此他们距离客户极近，我认为这对我们非常成功。此外我们还有一个研究团队，一方面能够深度融入客户的问题空间，通过各种抓手从客户那里获取特定类型的数据；另一方面也能够进行前沿探索。如果我们在模型侧取得突破，让机器人能够执行全新形态的任务，我们就能够围绕该技术协同设计出一款产品，迅速将其推向现场，其速度我认为是大多数公司做不到的。
<details><summary>Original English</summary>
>> We're trying to make it as similar as possible. So we're manufacturing our own robots. This gives us the ability to own that manufacturing process and figure out how do we push changes to the manufacturing process every 2 weeks. We are shipping code to robots either every day or major releases every two weeks and have built a huge amount of infrastructure to support that level of iteration. We've built a think a really unique shape of product function where our product function in our organization actually sits right next to our customer success and implementation functions and operate actually as one big team. So they're as close to the customer as humanly possible, which I think has been really successful for us. And then we also have a research team which is able to be both on the one hand deeply embedded in kind of the customer problem space and we're able to pull all sorts of levers to get specific types of data from customers um but also able to take these moonshots. And you know, if we have a breakthrough on our modeling side that lets robots do a whole new shape of thing, we can kind of co-design a product around that in a way that I think most companies couldn't and get that out into the field much quicker.
</details>

### 客户需求与成本结构

>> 如果我正在收听这期节目，我经营着一家仓库，
<details><summary>Original English</summary>
>> If I if I'm uh listening to this and I have a warehouse
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 我想要一台机器人，是直接上你们网站输入邮箱就可以了吗？具体流程是怎样的？
<details><summary>Original English</summary>
>> and I want to get a robot, do I just go to the website and like put in my email? That's how does this work?
</details>

>> 你可以访问我们的网站留下邮箱。我们网站上其实有非常酷的定价计算器，你可以输入有关当前仓库或工厂运营的一些数据，就能估算出：初步部署 Tutor 机器人后，每年可能节省 10 万美元、100 万美元甚至 1 亿美元。而且这不需要花 5 年时间进行定制工程路线图规划，从今天算起两个月后，你就可以在无需大额资本支出的情况下每年省下那 100 万美元。
<details><summary>Original English</summary>
>> You can go to our website, you can put an email. We actually have cool pricing calculators where you can actually put in some operational data about how your warehouse or factory runs today and you can get an estimate of, hey, with an initial deployment of TUDA robots, we could be saving $100,000 a year, a million dollars a year, $100 million a year. Um, and that's not like, okay, this is a road map over 5 years of custom engineering. It's like, no, you could save that a million dollars a year two months from today, uh, without putting capbacks down.
</details>

>> 你是否发现外界对此有需求？我的意思是，这听起来太像科幻了，市场上真的有需求吗？
<details><summary>Original English</summary>
>> And have you found that there is like demand for I mean it's just such a sci-fi thing like is there demand out there?
</details>

>> 需求非常大，而且这甚至不能称为对“机器人”的需求，因为人们根本不知道这种形态的机器人存在、有效并且能胜任这份工作。我们的分析框架是：机器人的价值等于机器人能完成的工作量，
<details><summary>Original English</summary>
>> There is so much demand and it's not even demand for robots because again like people don't know that the shape of robot exists or that it works or that it can do this job. So it's it's ultimately like you know we have this framework of the value of a robot is you take how much work a robot can do
</details>

>> 除以它的成本。
<details><summary>Original English</summary>
>> and you divide it by its cost
</details>

>> 仅此而已，其他一切都只是注脚。如果我们在美国物理经济中这些流动性极高的劳动力市场中具备竞争力，能够以更低的成本提供同等甚至更高的作业能力，那么其对应的市场就是整个市场，涵盖所有在物理世界中完成的工作。
<details><summary>Original English</summary>
>> and that's it, right? Everything else is is commentary. And so if we're able to compete in these highly liquid labor markets that exist across American physical economy, uh, and we can offer something that delivers greater equivalent capability to lower cost, the market for that is the whole market, right? It's all physical work done.
</details>

>> 有一个专业技术层面的问题：当你谈到成本时，是指前期采购成本的分摊，还是指日常运营维护的持续成本？
<details><summary>Original English</summary>
>> And what just one quick wonky question on this, which is how much when you say cost do you mean amortizing the upfront cost versus like the ongoing cost to operate it?
</details>

>> 两者兼有，这非常有趣且与以往不同。传统上我们思考机器人是基于投资回报率（ROI）：大额的资本支出（Capex），然后需要 10 年时间来收回成本；而现在实际上越来越多的成本转化为了持续的推理和遥操作费用。
<details><summary>Original English</summary>
>> It's both, which is very interesting and different, right? Traditionally we've thought about robotics as ROI right big capex expense and then 10 years to make it back and now it's actually like no more and more of the cost is going into ongoing uh inference teley operation
</details>

>> 但这是否也包括日常维护和故障报修等？主要的成本项是什么，还是说两者大致相当？
<details><summary>Original English</summary>
>> but does that also include like maintenance and break fix and all of that and then what and like what is the dominant cost or or are they roughly equal?
</details>

>> 随着时间推移，我们在持续压低所有环节的成本。
<details><summary>Original English</summary>
>> Uh we drive down all of them over time.
</details>

>> 不，我指的是从你们核算销货成本（COGS）的角度来看，前期成本和持续成本各占多大比例？
<details><summary>Original English</summary>
>> No, no. I'm just saying like from from your standpoint when you like pencil out your cogs, how much of is it the upfront cost versus the ongoing?
</details>

>> 目前来说更多是持续成本，这让许多人感到意外。
<details><summary>Original English</summary>
>> Yeah, it is more ongoing at this point and that's surprising to people.
</details>

>> 很有意思。
<details><summary>Original English</summary>
>> Interesting.
</details>

>> 哇，原来是这样。
<details><summary>Original English</summary>
>> Oh wow. Yeah.
</details>

>> 对我来说并不意外。你实际上是在和一个喂点米饭就能维持运转、效率极高的系统竞争，那就是人体本身。
<details><summary>Original English</summary>
>> Not surprising to me. I mean, you're really competing with like something that you feed rice to and it's very very efficient, right? Like the the human body.
</details>

>> 当客户找上你们时，是因为像“黑色星期五”这种购物季临近、需要在极短时间内完成大批量生产，还是说这已经成为了他们实际劳动力规划周期的一部分？
<details><summary>Original English</summary>
>> Yeah. So the when you get called into these customers, is it because Black Friday or something is coming up and they need a bunch of units done in a really short time or is this actually now part of their actual labor planning cycle?
</details>

>> 不，这是具有战略意义的考量。这些企业面临着非常艰难的抉择：他们清楚自己劳动力的年龄结构，知道受各种长期趋势推动需求正在攀升，而完成这些履约工作的成本基数也在不断上涨。他们会思考业务该如何持续盈利，因为他们不是拥有巨额毛利率可以任由压缩的软件企业；制造业如果算不过账，业务要么能运转，要么就彻底停摆。因此我认为我们的客户归根结底是在寻找一个能解决机器人问题的长期合作伙伴。比如某个客户生产除臭剂，他们的核心业务就是制造除臭剂，是除臭剂或蜡笔等产品的生产运营专家；而他们需要一个在机器人技术上足够专业的合作伙伴。
<details><summary>Original English</summary>
>> No, it's strategic, right? It's um these businesses, I think, are faced with a really hard choice, which is they know the age of their workforce. They know that demand is ramping up due to all these secular trends and the cost basis of fulfilling that work is going up and they're like how does our business pencil out because you know these are not software businesses that have these you know huge gross margins that you can you can play with and can compress a little bit and it's like it's fine. It's like no the business either works or it doesn't. Um, and so I think our customers are ultimately looking for a long-term partner that can do the robots, right? If one of our customers is manufacturing deodorant, they're doing the deodorant, right? And they're going to be operational experts in deodorant or operational experts in crayons or whatever the thing they manufacture is, and they need a partner who's the expert on robots.
</details>

### 地缘政治与供应链考量

>> 我想问一个关于工厂性质的问题：虽然今天可能受限于产能短缺，但在未来某个时刻，你可以随时向任何人发货机器人。如果随着时间推移，你们的机器人变得越来越通用化，这对工厂的选址意味着什么？人们围绕工厂的组织方式、甚至单产业工厂城镇的形态，是否都会发生根本性的改变？
<details><summary>Original English</summary>
>> I had a question on the the nature of factories and I mean you can ship a robot to anybody any time not today because of your shortages but at some point in the future right [sighs and gasps] and if your robots become more and more general purpose over time what does it mean for where factories are located and how people organize around these factories and and you know these one town factories and what one factory town whatever the expression is a lot of fundamentally changes now, right?
</details>

>> 会发生巨大的改变，这里面涉及很多地缘政治因素。我认为一大关键在于：这将成为美国与其他国家之间的“大均衡器”。像中国这样的国家对上一代工业自动化体系进行了大量投资，这在某些方面让他们非常成功，但事后看来，这可能最终会被证明是一个巨大的包袱。因为正如我们刚才所讨论的，美国正在利用通用机器人对我们的工业制造产能进行全新维度的绿地建设；而在中国，他们可能不得不推倒重来，我们在美国则不需要以同样的方式去拆除旧设施。另一个将要发生的巨大变化是：我们将拥有多得多的工厂。正如云基础设施和软件工具让更多人能够创建新企业一样，如果拥有这种无限灵活的劳动力底层基质，任何人都将能够在物理世界中开创并扩展自己的实体业务。
<details><summary>Original English</summary>
>> Yeah. Uh I think a lot changes, right? There's a lot of geopolitics in this. I think one big thing is this is going to be a great equalizer between the United States and other company or excuse me, other countries like China invested in the previous regime of industrial automation. And in some ways that made them very successful and in other ways I think in hindsight that might end up being an enormous mistake because in the United States we just discussed we're doing this green field build of automating our industrial capacity using generally capable robots in China they're going to have to tear down right we're not going to have to do that in the United States in the same way. I think another thing that's going to shift which is going to be really interesting is we're just going to have way more factories. In the same way that we have way more businesses because kind of the cloud and all of the software tooling let people build new businesses. Anybody will be able to start a business in the physical world. Anybody will be able to scale a business in the physical world. if we kind of have this infinite flexible labor substrate.
</details>

>> 你提到了中国。我们之前其实发布过一份关于机器人供应链的报告，显示中国在其中处于极其核心的地位。你能否谈谈你们对中国供应链的依赖程度、这种关系如何演变，以及供应链中针对中国的风险有多大？
<details><summary>Original English</summary>
>> You you brought up China our you know uh you know we actually we actually published a report on the supply chain in robotics and it seemed to be that that China was so central to it. So can you talk a little bit about your dependency on it and then how that evolves over time and how much of there is there risk in China to the supply chain.
</details>

>> 不管外界怎么说，在 2026 年的今天，我们拥有一个高度互联、相互依存的全球供应链，机器人领域只是其中的众多案例之一。美国公司和中国公司都在深入思考其长期战略格局：中国公司在对美国投资，美国公司在对中国投资，归根结底每个人都在努力构建自己的工业产能。
<details><summary>Original English</summary>
>> Yeah. Uh I think ultimately no matter what anybody says today in 2026 we have a highly interconnected interdependent global supply chain and this is one of many examples of this and I think both US companies and Chinese companies are thinking very hard about kind of what does the long-term strategy of this look like and it's Chinese companies investing in United States it's United States companies investing China and ultimately everybody trying to build their industrial capacity.
</details>

>> 我注意到据我所知你们进行了更深入的垂直一体化。是这样吗？你们把更多环节收归自研自制，未来是否计划继续这么做？
<details><summary>Original English</summary>
>> Yeah, I've I've noticed that you know you've gotten as far as I can um tell you've um verticalized more. Is that right? Like you're taking more in house and do you continue do you plan to continue to do so?
</details>

>> 是的。在供应链领域存在一个棘手的问题，由于机器人行业规模相对较小，你一开始可能是从 OEM 那里采购子组件；随着订单量增加，当采购量占到其业务相当大的比例时，他们不再仅仅是普通的 OEM，更像是专门的外协代工厂（contract manufacturer）。到那个阶段，双方的关系和动态就发生了变化：它还是适合做该部件的代工厂吗？我是继续找代工，还是将其收归内部自产？
<details><summary>Original English</summary>
>> Yeah. Well, there's this tough thing in supply chain where and again because robotics is such a cottage industry is you might start um in a world where subcomponents are coming from OEMs and then you grow your volume to the point of they're not OEMs anymore. They're they're glorified contract manufacturers, right? ones are doing a material percentage of their volume and at that point just the relationship and the dynamics change right it's like is that the right co-man for that thing do I want to be using a co-and or do I want to be manufacturing it in house
</details>

>> Tutor 肯定是全美最大的机器人部署方之一，因此也是这些 OEM 厂商最大的客户之一。我想随着时间推移，你们会持续推动自主掌控这些核心组件。
<details><summary>Original English</summary>
>> yeah I mean tutor must be one of the largest deployers of robots in the United States you know as a result you must be like one of the largest customers for some of these OVMs you know as a result I would imagine over time like you just continue to like drive you know these components yourself
</details>

>> 我认为确实如此。
<details><summary>Original English</summary>
>> I think that's right
</details>

>> 这意味着全部自研自产，还是指示他们按需制造？他们仍然属于供应商吗？
<details><summary>Original English</summary>
>> does that mean taking it in house or just telling them what to do I mean is it like are they still suppliers?
</details>

>> 我想是两者结合。
<details><summary>Original English</summary>
>> Some combination I guess
</details>

>> 是吗？
<details><summary>Original English</summary>
>> is it
</details>

>> 两者结合。归根结底，Tutor 要想取得成功，美国本土必须具备成熟的机器人供应链。鉴于我们占据了该供应链如此大比例的市场需求，我认为大力投资以在美国本土构建这种产能，既是我们的责任，也是我们的机遇。这就是为什么我们在马萨诸塞州沃特敦制造机器人，也是为什么我们预计将继续深化垂直整合、在美国本土制造越来越多的机器人核心零部件。
<details><summary>Original English</summary>
>> some combination. I think ultimately for tutor to be successful we will need a mature robotic supply chain in the United States and we're in this position where because we are so much of the demand for that supply chain. I think it's both our obligation and our opportunity to invest very very very heavily to building this capacity in United States. And that's why we build robots in Watertown Massachusetts. It's why we expect to continue to verticalize and build more and more of our robot componentry in the United States.
</details>

### 研究架构与人才招募

>> 回到我们最早交谈的时候，我记得大概是第二次会面时我们真正深入聊了研发技术。虽然商业化是你们的巨大强项，但研发本身也是核心支撑。能否谈谈你们的研究路径？关于哪类机器人学习模型能够最终胜出有各种理论，你们在学习模型上是如何下注的？
<details><summary>Original English</summary>
>> Again, going back to when we first started talking, I remember it was probably the second meeting when we actually started about the research, right? Most of the meeting because you got such a great business, but that's a big strength of yours, right? And talk about how you approached it and there's all sorts of theories about which robotic learning models will win and so on so forth. How how are you approaching the robot the learning bed?
</details>

>> 好的。在研究方面，
<details><summary>Original English</summary>
>> Yeah, in research
</details>

>> 我们借鉴了大语言模型（LLM）的发展历程，分析其中的异同。在大模型领域非常明确的一点是：尽管存在大量异构的数据来源，但处于数据金字塔顶端的，始终是在真实世界中执行目标任务的强化学习轨迹数据。因此我们构建的研究体系核心在于：如何最大限度地利用机器人在现实世界中的实际经验？为此我们在波士顿组建了一支拥有 100 台机器人的机队，称为“数据工厂一号”（Data Factory 1）。据我们所知，这是全美规模最大的半人形机器人数据采集基地。我们把它作为科研试验平台，探索如何利用机器人规模化开展真实世界的强化学习。强化学习这类技术在小批量样本下很难奏效；如果你在真实世界中拥有一支庞大的机队，就能开始尝试这些学术界和工业界以往都无法施展的方法。
<details><summary>Original English</summary>
>> I think we're thinking about how this played out in LLMs and what's similar and what's different. And I think one thing that clearly has been very very important in LLM is there are lots of heterogeneous sources of data but ultimately there's a top of the data period which is real world reinforcement learning traces doing the thing you want to be able to do. And so we've built our research program in such a way where we are thinking about how do we get the most out of robot experience out in the real world. Um and so we built this 100 robot fleet called data factory 1 in Boston. This is to our knowledge the largest sort of semi-humanoid data collection farm in the United States. And we're able to use this as kind of this research test bed of how do we do real world reinforcement learning at scale with robots. Um, you know, reinforcement learning is a technique family where uh it doesn't really work at small batch sizes. Um, and so if you have a very large fleet out in the real world, you can start to play with these methods which I think people haven't been able to play with either in academia or industry.
</details>

>> 搭建这样一个团队肯定与常规科研实验室非常不同。能否谈谈团队的构建？是否有正在物色招聘的人才？
<details><summary>Original English</summary>
>> So I I I presume like building a a team for this is quite different, right, than like you know lab. So maybe talk about kind of like the construction of the team and maybe if there's anybody you're looking to to hire.
</details>

>> 我们在全方位招募人才。我们在招聘研究员和工程师，覆盖技术栈的每一个单层。同时我们也在招聘制造机器人的装配技术人员。
<details><summary>Original English</summary>
>> We're looking to hire everybody. So we're looking to hire researchers and engineers and that's across every single layer of the stack. Uh we are also looking to hire uh technicians to build robots.
</details>

>> 你所说的技术栈每一层，是指软件、硬件、材料、电子这些？
<details><summary>Original English</summary>
>> By the way, every layer of the stack you mean like software, hardware, materials, electronics like there.
</details>

>> 没错。没有任何一层你可以推卸责任。无论你是否愿意，都必须直面它，关键在于你是否真正理解它。我们正在打造这样一支团队。我认为这是一支形态非常独特的团队，不仅在于跨越技术栈所有技术层级的高度跨学科协作，而且我认为这是整个宇宙中极少数能让你早上在白板前推导模型架构、下午就到工厂生产线实地观察机器人运行状态的地方之一。
<details><summary>Original English</summary>
>> Yeah. There's nowhere that you can abdicate responsibility, right? You're going to engage with it whether you want to or not. The question is whether you understand it. Um so so we're we're building that team and I think that's a really unique shape of team not only because it's so interdisciplinary and collaborative across all those layers of the technical stack but because I think it's one of the only places in the universe where you can be on a whiteboard talking about model architecture in the morning in the afternoon like you know looking at a factory line and seeing how a robot is doing and
</details>

>> 团队主要集中在马萨诸塞州吗？
<details><summary>Original English</summary>
>> is this primarily in Massachusetts or
</details>

>> 我们的团队遍布全美。尤其是市场拓展（GTM）人员和现场技术人员，因为我们的客户遍布全美各地。
<details><summary>Original English</summary>
>> so we have a team across the United States um we have especially folks on the go to market and technicians who are kind of engaging you know our customers are everywhere across the United States.
</details>

>> 太好了。非常感谢！
<details><summary>Original English</summary>
>> That's good. All right. Awesome. Thank you.
</details>