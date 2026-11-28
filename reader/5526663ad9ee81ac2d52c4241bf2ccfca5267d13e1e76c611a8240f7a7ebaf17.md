---
author: The MAD Podcast with Matt Turck
date: '2026-07-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=6opo7LnZajM
speaker: The MAD Podcast with Matt Turck
tags:
  - agentic-commerce
  - token-theft
  - vibe-deployment
  - agent-economy
title: 智能体商业的演进：从Token盗用到端到端运营的未来图谱
summary: 文章深入探讨了人工智能领域中“智能体商务”的崛起，分析了其经济技术栈、基础设施建设以及潜在的商业模式。核心观点包括用户对AI代购的担忧是合理的，未来的发展将从简单的买方角色演变为多面经济参与者，最终实现智能体作为微型企业的端到端运营。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/10 -->

### 智能体盗用 Token 与商业前景

**Emily Sense**：欺诈者们已经发现，在 AI 领域，你实际上并不需要窃取金钱或凭证。你只需要窃取 token 就行了。当我查看数据时，这种行为的规模着实让我震惊。在 AI 公司的注册用户中，有超过六分之一属于这种滥用行为。就像是吃霸王餐一样，只不过他们是为了 token。当我去问我的朋友和家人，是否愿意让 AI 智能体代他们购物时，他们通常会立刻想到：它会不会超支？会不会买错东西？我能阻止它吗？实际上，这些担忧都是合理的。这不仅仅是 Emily 授权一个智能体代她购物。而是 Emily 拥有一个负责运营业务的智能体，这包括买卖商品并创造利润。这才是我想在 12 个月后讨论的世界。

<details>
<summary>Original English</summary>

**Emily Sense**: fraudsters have figured out that in AI you actually don't really need to steal money or credentials. You can just steal tokens. And the scale of this actually shocked me when I looked at the data. So more than one in six signups at AI companies are this kind of abuse. Whatever the dine and dash, but it's for token. When I go and ask my friends and family whether they'd be comfortable letting an agent buy things on their behalf, they usually jump straight to like, well, is it going to overspend and is it going to buy the wrong thing and can I stop it? And those are actually all legitimate concerns. And it's not Emily permissioning an agent to buy on her behalf. It's Emily has an agent who's tasked with running a business and that includes buying some things and selling some things and making some profits. And that would be the world that I would like to be talking about 12 months from now.

</details>

### AI 智能体的经济技术栈

**Matt Turk**：大家好，我是 Matt Turk。欢迎回到 Matt 播客。今天我很高兴能再次邀请到 Stripe 数据与 AI 负责人 Emily Sense。自从 Emily 和我去年讨论过智能体商务（agent commerce）的崛起之后，它的发展只增不减。在这次对话中，我们将深入探讨 AI 智能体的经济技术栈：智能体将如何代表你进行买卖；为什么现有的定价机制正在失效；token 的货币化；被 Emily 称为整个 AI 领域最被忽视的话题——token 盗窃；最后，我们还将探讨智能体最终是否能独立运营完整的业务。请欣赏我与一如既往优秀的 Emily Sense 的对话。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome back to the Matt podcast. Today I'm excited to be joined again by Emily Sense, head of data and AI at Stripe. The rise of agent commerce has only accelerated since Emily and I talked about it last year. And in this conversation, we go deep on the economic stack for AI agents. How agents buy and sell on your behalf, why perceive pricing is breaking, token monetization, token theft, which Emily calls the most under discussed topic in all of AI, and finally, whether agents may eventually run entire businesses on their own. Please enjoy my conversation with the always excellent Emily Sense.

</details>

**Matt Turk**：好的，欢迎回来。我们大约在一年前聊过，当时讨论的主题全都是关于智能体商务的崛起。显然，这是一个需要时间去演进的长期趋势。我很好奇你在过去 12 个月里观察到了什么？哪些已经成为现实，又有哪些还有待建设？

<details>
<summary>Original English</summary>

**Matt Turk**: All right, so welcome back. You and I chatted about a year ago and the theme of the discussion we had was all about the rise of agentic commerce. Keeping in mind that obviously this is a long-term trend that's going to take a while to play out. I'm curious about what you've observed over the last 12 months. What has become reality and what is yet to be built?

</details>

**Emily Sense**：是的，一年前我们在谈论智能体作为买家时，很大程度上还处于假设阶段。我认为当时一些典型的体验，比如消费者体验，还没有被定义。我们很大程度上是从第一性原理出发，来推演这会是什么样子。时间快进一年，如你所知，我们仍处于早期阶段，还有很多工作要做，但我们已经部署了实际的基础设施。有真正的公司在上面进行构建。我们有了真实的模式可以学习。而且可以明确的是，它的发展形态已经变得更加清晰，并且还会继续演进。

<details>
<summary>Original English</summary>

**Emily Sense**: Yeah, I mean a year ago we were talking about agents as buyers in a pretty hypothetical way. I think that the canonical experiences, the consumer experiences, for example, weren't defined. We were largely reasoning kind of from first principles about what this might look like. Fast forward a year, as you know, like still early innings, still a lot to do, but we have actual infrastructure deployed. We have real companies building on it. We have real patterns to learn from. And to be clear like the shape of how this unfolds has become more clear and it's going to continue to evolve.

</details>

### 智能体商务的图谱与基础设施

**Emily Sense**：具体来说，我们现在的观点是，智能体商务的运作方式存在一个完整的图谱，这对于企业如何思考这个问题其实非常重要。在图谱的一端，这也是我们的机器支付协议（Machine Payments Protocol）所在的位置，基本上就是智能体自主发现一项服务，决定购买并完全独立地处理交易，对吧？也就是没有任何人类参与。这也许就是人们在谈论智能体商务时所想到的场景，但这仅仅是图谱的一端。图谱的另一端是，人们在 AI 界面中寻找适合扁平足跑者的跑鞋，AI 界面会给你一个答案。这种情况在传统搜索中也是如此，但现在越来越多的是，这个答案会附带一个购买按钮。

<details>
<summary>Original English</summary>

**Emily Sense**: So specifically what we've come to believe is there's a full spectrum of how agentic commerce plays out and that's actually really important for businesses in how they think about it. So at one end, and this is where our machine payments protocol lives, but basically you have agents that are out autonomously discovering a service and deciding to buy it and handling the transactions like entirely on their own, right? Like no human in the loop. And that's maybe what people think of when they say agent commerce, but that's just one end of the spectrum. There's also the whole other end of the spectrum where like people are looking for shoes for flatfooted runners inside an AI surface and the AI surface gives you an answer and increasingly you know that was true also in sort of traditional search but now increasingly that answer comes with a buy button.

</details>

**Emily Sense**：因此，这已经成为大量人群发现产品的方式。如果你是一家企业，你就需要出现在那里。我们一直在构建基础设施，以实现两个目标：第一，让企业能够轻松地在那里展示；第二，让智能体能够轻松地执行这些交易。所以，你问到了哪些方面变得更加具体了。我们最近与 Google 达成了合作，这样商家就可以直接在 AI 模式和 Gemini 应用内进行销售。比如，你可能会在 JD Sports 购物——因为我刚才提到了跑鞋——或者是 Fanatics 或 Quint。这些都是早期的采用者。至于微软和 OpenAI，我们也在和他们做类似的事情，比如帮助企业让他们的产品在 Copilot 和 ChatGPT 中可被发现。Meta 是另一个例子，形式略有不同，但我们正在为广告内的直接结账功能提供支持。

<details>
<summary>Original English</summary>

**Emily Sense**: And so you know this is already how a huge number of people are discovering products. If you're a business, you need to show up there. And we've been building the infrastructure to make it a easy for businesses to show up and b easy for agents to execute those transactions. So, you asked about sort of what's become more concrete. We recently partnered with Google so merchants can sell right inside AI mode and the Gemini app. So, you know, maybe you shop at JD Sports because I was on the topic of running shoes or Fanatics or Quint. Those were all early adopters. Microsoft and OpenAI, we're doing something similar with them, like helping businesses make their products discoverable inside Copilot and ChatgPT. Meta is another example, a little bit of a different flavor, but we're powering checkout right inside ads.

</details>

**Emily Sense**：所以，这其中包含了发现过程，然后是一键操作，最后由智能体实际代表你去执行交易。但我想说的是，我们在过去一年里学到的贯穿始终的经验是，无论我们讨论的是通过 MPP 实现完全由智能体主导的交易，还是在 AI 服务中很大程度上由人类主导的购买，都需要一套新的基础设施来支撑。无论你处于图谱的哪个位置，这套基础设施都必须发挥作用。这也是我们智能体商务套件背后的前提，简单来说就是：企业需要能够展示他们的产品、目录和价格；消费者需要能够授权智能体代为支付；然后智能体需要能够安全地执行该交易。

<details>
<summary>Original English</summary>

**Emily Sense**: So, there's the discovery and then the one click and the agent actually goes and executes the transaction on your behalf. But really I'd say like what we've learned over the last year, the through line is like whether we're talking about like fully agent-led transactions with MPP or these very sort of human-led purchases inside AI services, there's just a new set of infrastructure that needs to work no matter where you are in the spectrum and that includes I mean it's the premise behind our agentic commerce suite but briefly like businesses need to be able to expose their products and their cataloges and their prices and then consumers need to be able to authorize agents to pay on their behalf and then agents need to be able to safely execute that transaction.

</details>

**Emily Sense**：所以这就是我们所构建的基础设施。那些是我们正在合作的一些伙伴。而且我想说，看看那些在此基础上进行构建的公司，你大概就能很好地把握商务未来的发展方向，对吧？在平台端，有像 Wix、Shopify、Big Commerce 和 Commercetools 这样的公司；而在品牌端，则有 Best Buy、Coach、URBN 和 Kate Spade 等。不过话又说回来，现在仍然处于早期阶段，交互模式将会是什么样子，又将如何演进，还有待观察。

<details>
<summary>Original English</summary>

**Emily Sense**: So that is the infrastructure we have built. Those are some of the partners that we've been working with. And I would say like, you know, the companies building on it probably give you a good read of where commerce is headed, right? So, companies like Wix and Shopify and Big Commerce and Commerce tools sort of on the platform side and then on the brand side like Best Buy and Coach and URBN and Kate Spade. But again, it's still early and what the interaction patterns will be and how they'll evolve. 

</details>

**Emily Sense**：我特别感兴趣的是，消费者会以多快的速度让渡更多的决策过程。也就是说，我们何时能从目前的情况——消费者在这里，AI 帮你找到产品，智能体负责帮你免去繁琐的结账流程——真正过渡到另一种时代：我们只需说，“我不知道，我只有 500 美元的返校购物预算，而你已经了解关于我的孩子、他们的学校以及我住址的一切信息，所以你去搞定吧”；甚至我都不用告诉你，你就直接去帮我办好。但我认为，我们需要在未来的一两年里去了解这一点。

<details>
<summary>Original English</summary>

**Emily Sense**: And I'm particularly interested in like how quickly consumers will give up more of the decisioning process and really move from consumer happening over here where AI helps you find the product and the agent is the one sort of helping you avoid going through cumbersome checkout flows to a time when we say like I don't know I have a $500 budget for back to school shopping and you already know everything about my kids and their school and where I live so like get it done or I don't even tell you and just go do it for me. But I think we will need to learn that over the coming year or two.

</details>

### 智能体自动化的三个层级

**Matt Turk**：对于智能体商务（agentic commerce），你们有没有提出一个像行业内某人提出的那种框架？它几乎就像是自动驾驶汽车的自动驾驶级别一样，比如 L1 是你去发现。

<details>
<summary>Original English</summary>

**Matt Turk**: Is there a framework for agentic commerce that you guys came up with like somebody in the industry came up with that? So that would almost be like the levels of autonomy for self-driving cars like you know L1 you discover.

</details>

**Emily Sense**：我们还真的有。是的。天哪。这就像是我们有级别一、级别二、级别三。基本上，如果你去想的话，它就像是——最高级别就是我提到的 MPP（机器支付协议）版本，在那里智能体是真正自主的；而级别一则基本上是由人类自己做出所有的决策，智能体只是简单地执行交易。我想说，在消费者端，我们目前主要徘徊在级别二。人们正在下放一小部分的选择权，或者在很大程度上依赖 AI 来帮助寻找产品。也许有一点级别三的影子，但你知道，我们还没达到那种你可以通过大语言模型一次性搞定暑假预订的世界。

<details>
<summary>Original English</summary>

**Emily Sense**: We do literally. Yes. Oh my gosh. It's like we had like level one, level two, level three. Basically, if you think about it, it's just like the highest level is sort of the the MPP version that I talked about where the agent is like truly autonomous and sort of the level one is the human does basically all of the decisioning themselves and it's the simple execution of the transaction. And I would say sort of on the consumer side, we're mostly hovering level two. You know, people are delegating a little bit of the selection or leaning hard on the AI to help find the product. maybe a hint of level three, but like you know, we're not in the world where you're booking your summer vacation oneshotting it with an LLM.

</details>

**Matt Turk**：那么从供应商的角度来看，你会如何描述？那可能有点像是级别三。所以那已经是今天的现实了，对吧？你已经可以获得一个推荐，然后你按下按钮。我们目前大概就处于这个阶段。一个例子就是 ChatGPT 的即时结账功能，你在那里获得推荐。

<details>
<summary>Original English</summary>

**Matt Turk**: And what would you describe from a vendor standpoint? That would be sort of like level three. So that's a reality as of today, right? So you can already get a recommendation and then you press the button. That's sort of where we are. And an example of this would be ChatGPT instant checkout, for example, where you get the recommendation.

</details>

**Emily Sense**：完全正确。或者你是在 Gemini 里，或者你知道的……

<details>
<summary>Original English</summary>

**Emily Sense**: Totally. or you're in Gemini or you know

</details>

**Matt Turk**：是的，正是如此。

<details>
<summary>Original English</summary>

**Matt Turk**: yeah exactly

</details>

**Matt Turk**：你刚才提到了一些重要的进展，这些都是自我们上次交谈以来，在整个行业的成熟度方面所发生的事情。你提到了智能体商务协议，我认为那是去年秋天推出的。那是什么？我想那是你们和 OpenAI 合作构建的东西。

<details>
<summary>Original English</summary>

**Matt Turk**: you touch upon some important developments that happened since we last chatted in terms of like overall maturation of the industry you mentioned the agentic commerce protocol which I think came out last fall what is that I think that's something that you guys built in partnership with openai

</details>

**Emily Sense**：是的，那是我们与 OpenAI 合作构建的。智能体商务协议只是一种让企业与智能体进行交互的标准化方式，它包含几个不同的组件。而且，这可以说是包含在我们更广泛的智能体商务套件中的。其中一点是，企业如何向智能体展示他们的产品目录、库存和价格？你可能会说，哦，智能体可以自己出去搜索或推断。

<details>
<summary>Original English</summary>

**Emily Sense**: yes we built it in partnership with openai the agentic commerce protocol is just a standardized way for businesses to work with agents and there's a couple different components of it. And this is sort of wrapped in our broader agentic commerce suite. One is how do businesses expose their product catalog, their inventory, their prices to agents? And you know, you could argue, oh, the agents could go out and you know, search or infer,

</details>

<!-- chunk 2/10 -->

### Agentic Commerce Protocol (ACP) 与电商基础设施

**Speaker A**：……但库存这种东西，你是希望能够具有确定性的。我们不希望企业需要向每一个新上线的智能体（Agent）去重新注册他们的产品目录或库存。因为，就像你我喜欢与许多不同的模型提供商合作，或者在这些提供商中使用各种不同的模型一样，在很多情况下，我们也同样看到企业不想只把赌注押在一个智能体平台上。他们可能既做 B2C 也做 B2B；他们可能希望跨越许多不同的平台去触达广泛的消费者群体。因此，智能体电商协议（Agentic Commerce Protocol，ACP）允许他们只需一次性暴露其产品目录，然后就可以选择接入所有支持该协议的智能体。这其中还包含共享的支付令牌（Payment Token）。此举的目的是为了确保在交易发生的那个瞬间，智能体能够安全地将买方的凭证传递给卖方以执行交易。而这些都只是经过代币化的凭证。所以你知道，智能体并不会像你我可能不愿意让智能体直接拿到我们信用卡那样去获取这些凭证。关于这一点，我非常喜欢的一点是，无论是产品目录组件，还是共享的支付令牌，它们都是平台无关、且与支付处理器无关的。所以所有这些都能顺畅运作——正如你提到的，这是我们与 OpenAI 共同开发的。它不仅适用于 OpenAI，也适用于其他提供商。如果由 Stripe 处理你的支付，它是有效的；但你也可以把这个共享支付令牌传递给任何其他支付服务提供商（PSP）。对我们而言，这真的是为了让企业能够更轻松地在客户所在的地方触达他们（越来越多是通过 AI 工具），而不需要为了做到这一点去重新发明他们的电商基础设施，对吧？我们希望只去重塑一次电商基础设施，然后企业就能开箱即用地获得这些全新的需求增长点。

<details>
<summary>Original English</summary>

**Speaker A**: ...but sort of inventory is a thing that you want like deterministically known. Um, and we don't want businesses to need to kind of register their product catalog or register their inventory with every single new agent that comes online because in the same way you and I like to work with a lot of different model providers uh or a lot of different models within those model providers, in many cases both uh we we similarly are seeing businesses not want to place bets on just one agentic surface. Um they may be selling BTOC and B2B. They may be wanting to reach a wide swath of consumers across many different um surfaces. doesn't. So, agentic commerce protocol lets them um expose their product catalog once um and then opt in to um all of the agents uh who who uh work with with that protocol. Um it also includes the the shared payment token. And so this is about making sure that um in the moment of transaction, the agent can securely pass the buyer's credentials over to the seller to execute the the transactions. And these are just tokenized credentials. So, you know, the agent doesn't have um access to the credentials in the way that you and I probably wouldn't want an agent uh to have our credit card. Um, and one thing I love about, you know, both the um, catalog component of this as well as the shared uh, payment token is it's uh, platform agnostic, payment processor agnostic. So all this works uh, you know, you mentioned that we co-created with OpenAI. It works with OpenAI but also other providers. It works if Stripe processes your payments, but you can also pass on that that shared payment token uh, to any other uh, PSP. Um, and for us, this is really about making it easy for businesses to reach their customers where they are, which is increasingly through AI tools and to not have to reinvent their commerce infrastructure to do that. Right? We want to reinvent commerce infrastructure once and then they out of the box um can get these sort of uh new lines uh of demand.

</details>

**Speaker B**：所以 ACP（智能体电商协议）有点像 MCP（模型上下文协议），只不过是专门针对电商的，对吧？这就是它名字的由来。那么它是在去年 9 月底推出的。就整体的采用情况而言，这是不是还需要一个循序渐进的工作过程，才能让电商公司真正去拥抱它？还是说我们现在已经进展到什么阶段了？

<details>
<summary>Original English</summary>

**Speaker B**: So ACP is a little bit like MCP but for commerce, right? That's hence the name with the status. So that was launched in uh at the end of uh September of last year. In terms of like overall adoption, is that kind of like a work in progress to get commerce companies to to embrace it or where are we?

</details>

**Speaker A**：实际上，我们已经看到了来自品牌方的大量需求。像百思买（Best Buy）已经接入了，Coach 接入了，URBN 接入了，Kate Spade 也接入了。此外，我们还看到了 Quint、Fanatics、JD Sports 等等一大批品牌的加入。同时，我们也看到了来自平台方的大量需求，你以前可能一直认为像 Wix、Shopify 或 Big Commerce 这样的平台，只是在为小企业开展电商业务构建技术。而现在，支持小企业做电商的一项重要技术环节，就是确保这些小企业能够出现在 AI 工具中，并能够参与到这波智能体电商的浪潮里。因此，Wix、Shopify、Big Commerce 以及各种电商工具在平台端都已经采用了这个协议。然后，在 AI 端，也就是智能体端，我们正在与所有大型公司合作。比如 Google 的 Gemini、微软、OpenAI，并且在这三个维度上，还会有更多企业陆续上线。但我们真正的想法是，供应端是由那些大型品牌和拥有小企业的平台组合而成的。而在智能体端，除了你所想到的那些传统的智能体玩家之外，还出现了一些有趣的细微变化——比如 Meta，他们可能会觉得，或许连广告本身都在变成一种智能体购买行为。所以这是一个非常有趣的延伸。

<details>
<summary>Original English</summary>

**Speaker A**: We've actually seen a ton of demand from brands. So Best Buy's on it, Coaches on it, URBN's on it, Kate Spade's on it. Um we've seen uh Quint and Fanatics and JD Sports and a whole bunch more. Um, we've seen a ton of demand from platforms which sort of uh you've probably long thought of platforms like Wix or Shopify or Big Commerce or whatever. You've probably long thought of them as um you know building technology for small businesses to do commerce. And now an important part of uh technology for small businesses to do commerce is making sure those small businesses um are appearing in AI tools and can engage in this wave of agentic commerce. And so Wix and Shopify and Big Commerce and Commerce tools on the platform side have all um adopted the protocol. And then on the AI side, on the agent side, we're working with all the all the big ones. So uh with with Geminis and with Google, uh Microsoft, uh Open AI, uh and um lots more coming online in in all three dimensions. But we really think of like the this the supply side is a combination of the large brands and the platforms who have the small businesses. Um and then on the um sort of agent side, it's what you would think of as the traditional agent pay players and then there's been some um interesting nuance as well for example with meta where like well maybe ads are just becoming agentic buying too. Um and so that's been an interesting extension

</details>

### 智能体对智能体交易的未来愿景

**Speaker B**：我觉得到目前为止，我们主要谈论的还是智能体买方——至少在我们刚才给出的例子中，智能体代表的是消费者。想必也会有“智能体卖方”的概念吧？未来这会是什么样子？如果所有技术问题都解决了，且普及率也达到了，这基本就是两个智能体在互相谈判某笔交易吗？这最终的愿景是什么？

<details>
<summary>Original English</summary>

**Speaker B**: and I think we talked mostly so far about agents buying at least like in the example we gave where the agent represents the the consumer. Presumably there's a concept of agent selling as well like what's the what does this look like in the future like if all technical problems has solved and adoptions happen is that basically two agents negotiating something what is the ultimate vision

</details>

**Speaker A**：当我退一步，用我作为经济学家的思维来思考时，我会觉得这真的会非常高效，对吧？智能体非常擅长发现和探索，我们已经看到了这一点；智能体也非常擅长集成；智能体在寻找最优定价匹配以及谈判方面都相当出色。它们有着难以置信的持久力。它们的时间价值远低于人类的时间价值，因此它们能够以快得多的速度完成那些来回的交涉。此外，它们在实际集成和采用某样东西时也表现得非常优秀。所以，特别是当你考虑到 B2B 采购时——也许我们稍后也可以稍微谈谈 Stripe Projects——不仅是找到服务、就价格进行谈判、签订合同并进行采购，而是实际上要一路推进到集成和使用该产品，我认为智能体将在这些方面提供极大的帮助。因此，我绝对是在想象一个高效得多的经济体：你在买方有智能体，正如你指出的，在卖方也有智能体，而且它们在所有这些维度上都具备极高的效率。这当然会像诺贝尔奖得主罗纳德·科斯（Ronald Coase）所描述的那个世界一样，基本上就是消除了企业之间合作的摩擦，使市场更高效，加剧竞争，服务于消费者，并刺激经济增长。不过我要说的是，今天还没有发生太多智能体与智能体之间的交易。所以正如你一开始问的，哪些已经成为现实，哪些还在未来？我认为那仍然属于未来。但我觉得，你总是先从一端开始，然后再加入另一端，随着时间的推移，我们可能最终会同时拥有两端。

<details>
<summary>Original English</summary>

**Speaker A**: so when I when when I when I like step back with my economist brain I'm like that would be really efficient right agents are really good at discovery right we've already seen that um agents are really good at integration agents are pretty good at like finding optimal pricing matching, negotiating. They're incredibly persistent. Uh their time is worth a lot less than human time and they can get those get those back and forths done um much more much more quickly. Um and then they're also actually really good with like integrating and actually adopting the thing. So, especially if you think of like B2B buying and maybe we can talk about um Stripe Projects a little bit later too, but just like actually like not just finding the service and negotiating it for the price and contracting on it and buying it, but actually like getting all the way to integrating and using the product. Um I think agents are going to help with a lot. And so I'm I'm definitely um imagining an economy that is much more efficient because you have agents on the buy side and as you note also on the sell side and they're kind of hyperefficient on all of those dimensions uh which of course um you know in the in the in the uh Ronald Coast Nobel Prize winner Ronald Coast version of the world would basically um just like remove frictions for firms to work with each other would make markets more efficient would make competition higher would serve consumers would spur growth. Um I will say today not a lot of agent agent transactions happening. So like you know you you asked at the top like what's become real and what's still in the future. I think that's still in the future. Um but I think you start with one side you add the other and and over time um we probably land with both.

</details>

### AI 对宏观经济与生产力的深层影响

**Speaker B**：为什么这如此重要？一方面，这确实很酷。我可以自己忙点别的事，然后我的智能体去帮我寻找一个好产品，因为它了解我。这很个性化，也很方便。但我认为你想表达的是，它的意义远比这要深刻得多。这是一种全球经济范畴的加速，是生产力的加速。我不是想把话硬塞到你嘴里，但最终利害攸关的就是这些，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Why does this matter so much? On the one hand it's it's it's kind of cool. I can be uh you know doing something and my agent does uh like look looks for a good product because it knows me. So it's personalized. So it's convenient. Uh but I think what you're saying is that it's it's much deeper than that. It's a it's a global kind of economy acceleration, productivity acceleration. Not to put words in your mouth, but like that's what's at stake ultimately.

</details>

**Speaker A**：是的。事实上，在消费端确实如此，对吧？如果我们让人们更容易去发现、交易和集成，那就会刺激增长。顺便提一下，我认为我们现在已经从全球宏观数据中看到了一些由 AI 带来的生产力提升，但我认为目前的驱动力还主要不是来自于消费端，因为那些数字依然很小。目前的驱动力主要来自于我们正在向经济体注入大量的 AI 资本支出（CapEx），那才是真正被泵入经济的“消费”。但我认为，随着时间的推移，智能体消费绝对会成为一个重要的驱动力。同样真实的是，还有一个更深层次的变化，那就是智能体不仅让购买东西变得更容易，也让创办和运营公司变得更容易了。这完全是另一个视角，但我们在宏观数据中非常确凿地看到了这一点。我不知道你有没有观察过美国历年来的新企业成立数量，在疫情期间，这个数字激增了，这并不让人感到非常意外。但如果你继续观察，你会发现它们在之后的一段时间里趋于平稳，而在过去的几个季度里，这个数字现在又开始加速增长了。而让我感兴趣的不仅仅是这种加速，而是这其中的构成。比如，所有这些增量的新建企业究竟是什么？这部分增量增长完全来自于“无雇员企业”——这是美国人口普查局使用的字面语言，但你我通常会直接称他们为“单人创业者”（Solopreneurs）。所以，你知道，那些年收入超过 10 万美元的单人创业者的数量，自 2022 年以来就呈直线上升趋势。现在，仅在美国，就有 500 万人靠经营一人公司来维持生计。他们不是那种随便说说“哦，我是一名单人创业者”的人，而是字面意义上地，这真的是他们在养家糊口的收入。此外，还有数十万单人创业者的年收入超过了一百万美元。所以，你知道，我认为这就有点……

<details>
<summary>Original English</summary>

**Speaker A**: Yes. And actually that you know that is true on kind of the consumption side, right? If we make it easier for folks to discover and transact and integrate um uh then that will spur growth. And by the way, we're we're seeing I think uh some productivity uh in the global numbers from AI, but I think right now it's not primarily about consumption because like the numbers are still very small. It's primarily about like oh we're flooding the economy with a bunch of AI capex like that's that's actually the consumption that's getting pumped into the economy. But I think that's that's definitely going to be um a driver over time. It is also true that um there there's a deeper change which is agents are making it easier not just to buy things but also to like start and run companies. Um that's a whole other other angle but we we see that very solidly in the macro data. Um you know I don't know if you've seen like US business formations over time but during the pandemic they surged. that wasn't super surprising. But then if you look, they like plateaued over time and then they're like accelerating again now over the last um couple quarters. And what's interesting to me isn't just that acceleration, but actually the composition. Like what are all of those incremental new businesses being created um and the incremental growth is coming entirely from uh non-employer firms is the literal language that the Census Bureau uses, but you and I would just call them solopreneurs. And so, you know, the number of people, solarpreneurs, who are earning more than $100,000 a year, um, has just gone like this since 2022. And now there's in America alone 5 million people making their living running solo companies. Not like, oh, I just said I was a solarreneur. Like literally, that is my income supporting my family. Um, and there are hundreds of thousands that are clearing a million a year. And so, you know, I I think that's kind of...

</details>

<!-- chunk 3/10 -->

### AI 带来的商业活力与建立信任的挑战

**Speaker A**: 很有意思，因为有了 AI，你能否构建出某个产品？然后有了 AI，你能否围绕它运营一家企业？顺便说一下，我认为“感知编程 (vibe coding)”和“感知部署 (vibe deploying)”对于能否构建产品来说非常重要。此外，AI 领域正在涌现大量特定领域的智能体，它们真正在解决如何运营这家企业的问题，比如在会计和客户支持方面，这使得这些小型公司在结构上具有很强的生存能力。所以不管怎样，我认为我对 AI 抱有的经济热情，部分来自于市场效率的提升、消费的增长以及更好的匹配等，但同样甚至更多地，是来自于 AI 对商业活力的影响，以及让有想法的个人能够将一个想法变成推向市场、满足用户真实需求的产品。总之，我认为在未来几年里，这两者都会越来越多地体现在宏观经济数据中。

<details>
<summary>Original English</summary>

**Speaker A**: interesting because it's like, uh, with AI, can you build something? And then with AI, can you run the business around it? I think vibe coding and and vibe deploying, by the way, are are really important for can you build something? And then there's a bunch happening in AI um domain domain specific agents that are really solving for like can you run that business um on the accounting side and the customer support side and and um and that's making these these smaller companies um very structurally viable. So anyway, I think like the the economic enthusiasm I have around AI comes somewhat from the efficiency of sort of markets and growing consumption and better matching and so on, but just as much if not more from the effect AI is having on business dynamism and the ability for um individuals with an idea to get from an idea to a product that is in market um and and meeting real uh user needs. So um anyway, I think I think they'll both I think they'll both play into the macro numbers increasingly over the coming years.

</details>

**Speaker B**: 那么，在我们结束关于代理商务 (agentic commerce) 的现实及其影响（包括未来的影响）这部分概述和介绍时，我想问一下目前最大的阻碍是什么？具体来说，你认为问题最终仅仅是技术能力上的吗（我们稍后会讨论你们构建的一些东西），还是说这是一个关于信任的人性问题，也就是让机器为你打理事情的接受度，尤其是在涉及到你的个人资金时？

<details>
<summary>Original English</summary>

**Speaker B**: So as we close this kind of like overview introduction section just um on the the reality of agendommerce and the impact in including the future impact of agendom. What are the biggest roadblocks right now? uh in in particular, do you think that the uh issue ultimately is more just like technical capabilities and we'll talk in a second about some of the stuff that you guys have built or is that a human question of like trust and just accepting to have the machine do things for you especially when your money is your personal money is at stake?

</details>

**Speaker A**: 是的，我认为要真正扩大规模，我们需要克服的两个主要阻碍，第一就是信任，实际上我们在信任方面已经做了很多工作。我们讨论过共享支付代币 (shared payment token)，智能体没有任何权限访问支付凭证。每一个共享支付代币都包含 Radar 风险评分，对吧？既评估这是否是一个合法的买家，也评估这个代表买家行事的智能体是否行为合法。也许我们会谈谈作为智能体钱包的 Link，但我们已经做了很多工作，让消费者可以为智能体的支出设置护栏。所以它有点不同于那种一次性的虚拟信用卡（后者的凭证范围被限制得近乎死板），但在 Link 钱包中，你可以明确地设置护栏。

但即使从技术或基础设施的角度来看有了这种信任层，我仍然认为任何市场建立信任都需要时间，尤其是当你谈论的是让它替你做决定，比如买什么和花钱的决定时。我认为人类很自然地需要循序渐进地建立这种信任。因此，我认为这也是为什么在消费者一侧，我们目前主要看到人们在 AI 应用中发现商品，但他们仍然自己做出最终选择，而且绝大多数还是购买中低价位的商品。如果要发展到可以把重大决定交给 AI 的地步，他们将需要更多的信任，坦率地说，在某种程度上也需要这些应用在用户体验上有所进化。

顺便提一下，我当年并没有密切关注人们是如何把消费从实体店转移到线上的，但我敢打赌，在网上购物的最初几年，没有人会说：“我要去网上买个沙发、床垫或者皮夹克”，因为这些都是我想亲手摸一摸，或者要花很多钱的东西，而且在网上也很难判断质量。随着时间的推移，各种机制建立了起来，让人们相信买到的是对的产品，当他们花了很大一笔钱时，商品能完好无损地送到家门口。很明显，今天在网上购买床垫的人可能比在线下实体店买的还要多。所以我认为我们会达到那个阶段，但信任是一个重要的促成因素，我还是那句话，很多技术基础都已经就绪，但就是需要反复的体验。人类就是需要一次次的体验才能建立起信任。当涉及到金融财务相关的事情时，基本上没有人一开始就会预设信任。你必须去赢得它。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think the the two primary um blockers that you know we'll need to move through to really scale this up are um one trust and actually we've we've done a lot on the trust side. We talked about the shared payment token agent doesn't have any access to the credentials. Every shared payment token includes radar scores, right? Both is this a legitimate buyer and is this an agent acting in a legitimate way on behalf of the buyer. Um maybe we'll talk a little bit about link as the wallet for agents, but we've done a lot so that consumers can set guard rails around what the agent can spend, right? So it's it's a little different than like a one-time use virtual card, which are like uh pretty maniacally scoped credentials, but in the case of a link wallet, you you very much have have the guard rails to set. 

But even with the sort of trust layer from a from a technology or infrastructure perspective, like I just think it takes time for any market to build trust, especially when you're talking about um making decisions for, you know, what I buy and spending my money. Um I think it's very natural for humans to kind kind of want to build their way up to that. And so, um, I think that's a that's a big reason why on the consumer side, what we're mostly seeing is people are discovering things inside AI apps, but they're still choosing the exact thing and they're still disproportionately buying low to mid-pric stuff. Um, and they'll need more trust and honestly also to some extent an evolution of um, the user experience uh, in some of those apps um, if they're going to get to a place where they're where they're handing off major decisions. 

By the way, you know, I I I wasn't uh super close to how people moved their uh spending from stores to online, but I bet in the first few years of sending on spending online, nobody was saying like, you know, I'm going to go online and buy a couch or a mattress or a leather jacket, like a thing that I want to feel or I'm going to spend a lot of money on or where like uh quality is sort of hard to infer from things I can tell on the internet. Um, and over time mechanisms built up for people to trust that that was the right product, that when they spent substantial money, it was going to arrive at their door in good shape. Um, and obviously today there's probably more mattresses bought online than than in person. So I I think we will get there, but I think trust is uh an important enabler and I would say again a lot of the technology foundations are in place, but it just takes reps. Like humans just need reps um for trust to be built. When it comes to financial stuff, basically nobody enters with an assumption of trust. Uh you have to you have to earn it.

</details>

**Speaker B**: 我不会直接那么说，但曾经有一段时间，在网上输入信用卡信息的想法是完全疯狂的。当然，这也造就了 Stripe 令人难以置信的崛起和它所有的成功。好的，太棒了。

<details>
<summary>Original English</summary>

**Speaker B**: I'm not going to tell you that, but uh there was a a time when the idea of like entering a credit card on the uh internet was uh completely insane. Uh which of course led to the unbelievable rise of Stripe and and um and all the success. Um so okay, fantastic.

</details>

**Speaker A**: 但这很有意思，对吧？时至今日，我仍然非常不愿意在网上输入我的银行账户详情。我很乐意把银行账户绑定到 Stripe 上的 Link 钱包，让它可以代我付款，但我直到今天都不愿意在网上输入我的银行账号。我觉得非常有趣的一点是，随着这些我们被代理商务拉扯出来的基础设施逐渐成为常态（比如储值余额、钱包、绑定的银行账户等），互联网是否会在某种程度上变得更安全？我不知道，我也许需要我的智能体能够在有一定护栏的情况下消耗我的稳定币余额，这是否至少能减少我们在传统电商中看到的那类欺诈？也许可以。

<details>
<summary>Original English</summary>

**Speaker A**: But that's interesting, right? it there is still a I mean it I still feel extremely uncomfortable entering my bank account details on the internet so I'm happy to enter my bank account details to my link wallet on stripe so that it can make payments on my behalf but I am not happy to enter uh still today on the internet uh my bank account number and you know and I think this is this is actually really interesting to reason about uh will the internet actually get safer to some extent as these foundations that we are um sort of they're being pulled out of us because of agentic commerce but as you know stored balances and wallets and linked bank accounts and whatever become more of the norm I don't know I need my agent to like be able to burn down my stable coin balance with some guard rails like does that actually reduce at least the types of fraud that we've seen in um traditional uh traditional online commerce. Maybe maybe

</details>

### 用户体验的进化与面向智能体的 Link 钱包

**Speaker B**: 你刚才提到应用内部的用户体验不太好。你有什么具体想法吗，它在哪些方面做得不足？

<details>
<summary>Original English</summary>

**Speaker B**: you talked about the uh user experience inside of the app not being great. Do you have is there anything specific that you have in mind in terms of like how it falls short?

</details>

**Speaker A**: 我认为有几个方面。首先，这也是我们通过代理商务套件 (agentic commerce suite) 正在努力解决的一部分问题，我们应该让这些 AI 工具和 LLM（大语言模型）非常容易地、准确且全面地反映库存情况。在缺乏标准协议的情况下，要想确切知道谁在卖什么、商品是否真实、价格如何、还有多少库存以及各种参数是什么，其实是有点棘手的。因此，我认为部分体验需要进化，要有合适的库存集合供它们读取，并且在这个库存集合上有确定性的元数据，这样 LLM 才能在上面做非确定性的事情。

此外，我认为部分体验也受限于我们的习惯。大家都很熟悉进入一个网站，输入搜索，获得一些购物结果，然后选择一件商品这样的流程。但是，我想我们到底希望把消费的哪一部分委托出去，以及我们需要什么样的体验？这里面包含了一点发现的环节，一点设置护栏的环节，以及一点信任的环节，同时也需要 AI 对我们有足够深度的了解，才能打造出出色的客户体验。市面上有很多优秀的 AI 工具，它们也在通过很多方式加速我们的消费效率，但我还没看到哪种体验能让我觉得“这太神奇了，我非常清楚我已经准备好把哪些最终决定交给它”。

<details>
<summary>Original English</summary>

**Speaker A**: I think there's a few things. um one and you know part of what we're um working on with the agentic commerce suite is it should be really easy for um these you know AI tools LLMs to accurately reflect and comprehensively reflect inventory um you know absent uh a standard protocol it's actually like a little bit tricky to know exactly who's selling what and is it real and how's it priced and how much is left and what are the various parameters? And so um partly the experience I think just needs to evolve to actually have the right inventory set to read over and the right um deterministic metadata on that inventory set um that that the LLM can then do non-deterministic things on top of. 

Um, but I think some of the experience is just uh, you know, we're all very familiar with uh, the the flow of going in and typing in search and getting some shopping results and choosing a thing. But I think that whole like what part of consumption do we want to delegate and what experience do we need, which is a little bit of the discovery and a little bit of the guardrails and a little bit of the trust. um but also just like the depth of understanding of us um in order for that to be a great a great customer experience and I you know there there's lots of great AI tools out there and there's lots of ways that they're accelerating you know the efficiency of consumption but I haven't yet seen I guess I what I was saying on experience is I haven't yet seen an experience where I'm like that is magical and I know exactly the end things that I'm ready to offload.

</details>

**Speaker B**: 我想讨论一下你刚刚顺带提到的你们在 2026 年构建和发布的一些东西，特别是关于如何安全地把钱交给智能体的概念。你提到了 Link 钱包。用通俗的话来说，面向智能体的 Link 钱包是什么？

<details>
<summary>Original English</summary>

**Speaker B**: I want to cover some of the stuff that um you mentioned in passing around what you all have built and released in 2026 um and especially around the concept of of giving agents money uh safely. You mentioned uh the link wallet. What is the link wallet for agents in simple terms?

</details>

**Speaker A**: 是的。甚至在我们谈论智能体之前，Link 就已经是 Stripe 的消费者钱包，今天有 3 亿用户在使用它。我们正在把它变成智能体的钱包。所以它的理念是，你可以授权一个智能体代表你进行支付，但你可以获得内置的控制权，让你始终保持知情和掌控。所以你不是给了智能体一张空白支票，或者让它无限制地访问你的支票账户。你非常明确地定义了它可以做什么。而且你随时可以收回权限。我们之前讨论过信任，我实际上认为，在这个领域里，信任维度被低估或讨论得不够，其实它和产品挑战一样重要。就像我去问我的朋友们……

<details>
<summary>Original English</summary>

**Speaker A**: Yes. So maybe even before we get to agents, link is just Stripe's consumer wallet and 300 million um users uh use it today. Uh we're making that the wallet for agents. So the idea is you can authorize an agent to make payments on your behalf, but you get these built-in controls so you stay in the loop, right? So you're not giving the agent like a blank check or unlimited access to your checking account. You're very distinctly like defining what it can do. Um, and you can always uh pull it back. And you know, we talked about trust a bit earlier. I actually think the trust dimension here is like as underrated or under discussed as the product challenge. Like when I go and ask my friends

</details>

<!-- chunk 4/10 -->

### 代理商务中的消费者控制与 Link 钱包 (Consumer Control and Link Wallet in Agentic Commerce)

**Speaker A**: ……当家人考虑是否放心让代理代替他们去买东西时，他们通常会直接想到：“嗯，它会不会超支？它会不会买错东西？我能阻止它吗？如果它买错了怎么办？”这些实际上都是非常合理的担忧。因此，Link 钱包内置的控制功能，真正让整个方案对消费者来说变得可行。我还要说，你、我以及其他人都有很多不同的支付凭据，对吧？比如我们有银行账户，有信用卡，可能还有借记卡，此外还有“先买后付”服务、稳定币等等其他各种方式。一个能够由各种余额和众多不同支付凭据（法定货币、加密货币或其他任何形式）支持的统一钱包，它的好处之一就在于……你知道，这只是一个单一的入口。我不喜欢有太多东西需要去操心，尤其是在我把任务交给代理、并且需要监控它以确保事情确实按我预想的那样进行时，我特别不喜欢去费神管理一大堆东西。所以我认为，Link 钱包的部分魅力也恰恰在于它的整合性。你可以用任何支付凭据来支持它，但归根结底，你的代理钱包只是一个单一的钱包，这让你在管理和理解它时变得顺畅得多。

<details>
<summary>Original English</summary>

**Speaker A**: ...and family whether they'd be comfortable letting an agent buy things on their behalf, they usually jump straight to like, well, is it going to overspend and is it going to buy the wrong thing and can I stop it and what happens if it buys the wrong thing? And those are actually all legitimate concerns. And so um the controls within link wallet um are really what make the whole thing uh viable for for consumers. Um I would also say that like uh you and I and others have many different payment credentials, right? Like we have uh bank accounts and we have uh credit cards and we may have debit cards and there are buy now pay laterers. Um and one of and stable coins and whatever else. One of the nice things about um a single wallet that can be backed by balances and many different payment credentials, fiat and crypto and whatever else um is, you know, there's just there's just one like, you know, I don't like having a lot of uh things to reason over and I especially don't like having a lot of things to reason over when I am passing it off to an agent and need to monitor it and make sure that what I think is happening is actually happening. Um, and so I think part of the beauty of the link wallet is also just the the consolidation. You can back it by whatever the payment credentials are, but at the end of the day, your agent wallet is just a single wallet. Um, which makes it much more uh streamlined to reason around.

</details>

**Speaker B**: 从技术上讲，那是一次性使用的信用卡，还是完全不同的东西？

<details>
<summary>Original English</summary>

**Speaker B**: And technically, is that a one-time usage credit card or is that completely different?

</details>

**Speaker A**: 好问题。好的。大概 12 个月前我们讨论时，Stripe 上——我想也是世界上——最最早期版本的“代理商务”（Agentic Commerce），使用的就是这些一次性虚拟卡。实际上，它的起源是我们为平台和市场（Marketplaces）使用的一次性卡。比如我在 DoorDash 上点了一份沙拉，司机会得到一张一次性使用的虚拟卡来为我的沙拉付款。这让我感觉很好，因为无论是司机还是我不认识的餐厅，都不需要看到我的支付凭据。所以在代理商务的第一个版本中——对我们来说，我相信第一个具有实质性实际交易量的是在 Perplexity Shopping 上——我们使用的就是这种一次性虚拟卡。基本上，人类消费者会说他们想要什么东西，然后用他们的支付凭据来购买这种“一次性资金”，也就是这张一次性虚拟卡。代理被授予这张一次性虚拟卡，然后它们在互联网上用它来完成购买。因为是一次性的，它的使用范围被严格限定，通常仅限于单一供应商，并且金额也是固定不变的。

相比之下，我认为 Link 钱包要灵活得多，对吧？我可以设定一个预算，在多个商家或某个领域内的一组商家中使用。我可以在单笔交易层面进行单独授权，或者针对累计金额超过一定数额时进行授权。因此，一次性虚拟卡在让我们起步阶段非常有价值，尤其是对于这种一次性的消费者交易。但 Link 钱包要灵活得多。我现在依然认为，在大家真正同意让代理在特定范围的交易之外自由使用钱包之前，还需要几个月的时间；但确保基础设施能够扩展以适应这种需求，正是我们开发 Link 钱包所处的阶段。然后，当消费者准备好接受它时，这项技术已经在线就绪，没有任何阻碍。

<details>
<summary>Original English</summary>

**Speaker A**: Good question. Okay. So, the very like when we were talking 12 months ago, the very very first version of Agentic Commerce on Stripe and I think in the world was these one-time use cards. And uh actually the genesis of that was one-time use cards that we used um for like platforms and marketplaces, right? Like when I order um a salad from Door Dash, the driver has a one-time use virtual card uh that can be used to pay for my salad. And that feels good to me because uh neither the driver nor the restaurant which I don't have any affiliation with needs to see my payment credentials. And so uh in the first version of agent commerce which for us uh I believe the very first uh meaningfully live volume was on perplexity shopping we used uh these these one-time use virtual cards. And basically the the human consumer would say they wanted the thing. their payment credentials were used to basically buy this like onetime fund, this onetime use virtual card. The agent was handed this onetime use virtual card and then they went off on the internet and and and purchased with it. And that was uh very scoped uh by definition of being one time and it was generally um you know scoped to a single provider and scoped to a very fixed amount.

Uh I would think of uh link wallet as much more flexible, right? So I can set a budget uh to be used across a set of providers or set of providers in a domain. Um I can permission at the individual transaction level or I can permission sort of above some amount in aggregate or individually. And so um one time use virtual cards were super valuable for sort of getting us off the ground especially for these sort of singleuse consumer transactions. Um but the link wallet is much more flexible. Now I still think that we will be a few months hence before folks are actually um agreeing to um you know agents using the wallet uh beyond a particular scoped transaction but making sure the infrastructure scales to that is really where we are with link wallet. Um and then as the consumers become ready for it the technology is already online uh and there's no hold up.

</details>

### 共享支付代币与微交易 (Shared Payment Tokens and Microtransactions)

**Speaker B**: 你刚才提到了共享支付代币（Shared Payment Token）。那到底是什么？

<details>
<summary>Original English</summary>

**Speaker B**: You mentioned shared payment token. What what is that?

</details>

**Speaker A**: 它是一种全新的支付基础组件。我们在大概六个月前专门为代理商务开发了它。这是消费者授权 AI 代理代其付款的一种方式，而无需交出真实的银行卡信息。因此，该代币准确地编码了代理被允许执行的操作，对吧？向哪些商家支付、最高支付多少金额、使用什么货币、有效期是多久。代理在结账时向商家出示这个代币。代理永远也看不到底层的真实支付凭据。并且，共享支付代币覆盖了更多支付方式，包括像 Affirm 和 Klarna 这样的“先买后付”选项。所以它不仅仅是信用卡。它真的可以代表不同的支付方式，这取决于用户存档了哪些支付方式。这实际上是让面向代理的 Link 钱包发挥作用的支付原语。它同时也为我们的机器支付业务提供支持。它的核心在于：探讨代理如何在不承担风险的情况下进行交易，以及企业作为记录商家（Merchant of Record）如何保持控制权。

所以我认为，在我们构建共享支付代币时，一次性虚拟卡就像是一个非常有用的后盾。共享支付代币是一种与具体钱包无关、并且顺便说一句，也与支付处理器无关的新型支付基础组件。你可以把它传给 Adyen 或者你用的任何其他处理器，它不需要非得在 Stripe 上处理。然后，你可以把 Link 钱包看作是消费者体验端，是面向消费者的代理钱包，它利用了同一个共享支付代币基础组件，但为消费者提供了更加全面丰富的功能。

<details>
<summary>Original English</summary>

**Speaker A**: It's a new payment primitive. We built it u maybe six months ago specifically for agent commerce. Um it is a way for a consumer to authorize an AI agent to pay on their behalf um without handing over their actual card details. So the token encodes um exactly what the agent is allowed to do, right? Which merchants can be charged up to what amount, in what currency, for how long. Um the agent presents the token to the merchant at checkout. Um the agent never sees the underlying credentials. Um and uh shared payment tokens, you know, cover more payment methods, including buy now pay later options like a firm and CLA. So it's not just cards. Um it can really represent like different payment methods uh depending on what uh the user has on file. And this is actually the payment primitive that makes links wallet for agents work. Um it also powers our machine uh payments work. Uh it's really about okay how can agents transact uh without taking on risk and how can businesses remain in control uh as the merchant of record.

And so I would think of like one-time use virtual cards were like a useful backs stop as we went and built the shared uh payment token. Shared payment token is a new payments primitive that is wallet agnostic and by the way also payment processor agnostic. You can pass it over to Adion or whoever else you have. uh it doesn't have to be processed on Stripe. And then think of like link wallet as the consumer experience, the consumer wallet for agents um that leverages that same uh shared payments token primitive um but is more um fully featured for the consumer

</details>

**Speaker B**: 而且因为它是软件，所以它是完全可编程的。为了深入探讨你刚才说的一些内容：你可以限制某些类别的商家，或者限定只能在亚马逊上购买，又或者只能在美国或法国购买，对吗？

<details>
<summary>Original English</summary>

**Speaker B**: and it's software so it's fully programmable. So just to double click on some of what you just said, you can restrict certain categories of merchant or you can only buy from Amazon uh or you can only buy in the US or in France or

</details>

**Speaker A**: 是的，完全正确。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Exactly.

</details>

**Speaker B**: 太棒了。

<details>
<summary>Original English</summary>

**Speaker B**: Fantastic.

</details>

**Speaker A**: 或者你可以，你完全可以设定说：“我需要手动审批每一笔单独的交易”，对吧？当人们在进行合理大金额的交易时，这没什么问题。但我认为，我们将非常迅速地进入一个交汇点：一边是代理商务，另一边是稳定币所促成的微交易能力，进而让人们将代理视为常规买家。在过去，即便在内容消费领域，微交易也从来没有真正行得通，因为没人愿意为了买一篇 5 美分的文章去繁琐地输入信用卡信息，那样的摩擦成本实在太高了。另一方面，也没人愿意处理一笔 5 美分的信用卡交易，因为手续费会导致利润变成负数。

但我认为，我们正在进入这样一个世界：人类完全无需做任何动作来执行交易。你不需要输入任何密码或凭据，也不需要浏览导航到任何付款网页。代理在后台替你做这一切。于是，微交易立刻变得切实可行。你再把它与“消耗某些稳定币余额”结合起来——我们也可以聊聊我们在这方面与 Tempo 合作所做的工作——突然之间，微交易变得非常有商业可行性。我认为我们将很快进入一个世界，尤其是在购买推理计算、API 代币或者各类 AI SaaS 增值产品时，你会使用你的 Link 钱包在后台进行成百上千次的微交易，并且绝对不会去逐一审批每一笔。当然，如果你今天就想审批每一笔交易，你的确可以这么设置。但这模式不可扩展，因为没人会想要为了获得一点点数据、一小段研究结果或者完成当前任务所需的几个代币，而去点击审批一笔 1 美分的微小交易。

<details>
<summary>Original English</summary>

**Speaker A**: Or or you can or you can literally set it to say I need to approve every single transaction, right? Um and you know when people are making reasonable size transactions that's fine. I think we're going to move to a world very quickly sort of at the intersection of agent to commerce and what stable coins enable in terms of sort of microtransactions and then reasoning about agents as the buyers. Agents are very you know microtransactions never actually really made that much sense even in the context of content because nobody wanted to put in even if it was only 5 cents no one wanted to put in their credit card to buy a 5 cents article like that was just too much friction. A and B, nobody wanted to process a credit card for 5 cents because you would have negative margins.

But I think we enter a world where like the human is not doing any work to execute the transaction. You're not typing in any credentials. You're not navigating to any web pages. The agent's doing it for you. Um then microtransactions become viable. And you pair that with okay and now it's you know uh burning down some stable coin balance. And we can talk about the work we're doing with Tempo there. um suddenly microtransactions become very viable and I think we're going to quickly move to a world where especially in buying inference or tokens or um sort of AI sassy products um there's going to be you know you are going to be using your link wallet to um make a ton of microtransactions and not approve everyone. But yes, if today you want to approve everyone you can. that's not going to scale because no one's going to want to approve the the one cent transaction for the little bit of data, the little bit of research or the token um that I needed for for this job.

</details>

### 风险防范与记录商家 (Risk Management and Merchant of Record)

**Speaker B**: 那么，对于一切可能出错的情况，目前的想法是什么？你知道，正如你刚才所说，当你向朋友谈起这件事时，他们会说：如果代理买错了东西该怎么办等等。我想这大概是个处于探索前沿的问题，所有人都在努力寻找答案和边界，但你们目前的思路是怎样的？

<details>
<summary>Original English</summary>

**Speaker B**: So, what's a current thinking in terms of like everything that can go wrong? You know, you were saying like when you talk about this to your friends, they they say, well, what if the agent buys the wrong thing and so on and so forth. Uh I mean, presumably that's a the frontier. Everybody's trying to figure it out, but what's the current thinking?

</details>

**Speaker A**: 是的。我们正从几个维度来深度考虑这个问题。首先，关于你的问题：要是送错了东西，或者东西质量不好等等该怎么办。企业端必须保持作为“记录商家”（Merchant of Record）的身份。对我们来说，这是一个极其核心的设计原则。这意味着，我们将我们的工作使命视为：确保让代理发起的交易，其行为方式和保障表现得与普通人类发起的交易完全一样。当然，这并不意味着代理在后台操作时需要表现得像人类一样慢，或者受到像人类那样相同的物理和界面约束。但从责任和商业企业的角度来看，他们仍然是记录商家。他们只是在销售，他们碰巧遇到了那种情况……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. We're thinking about this in a few dimensions. One is um to your question on you know what if what if the wrong thing gets sent or the thing's not good or whatever. Um businesses have to remain the merchant of record. Like that's a core design principle for us. Um which means like we see our job as having agentic transactions behave the way human transactions do. Now that doesn't mean that agents need to behave like humans or be constrained in the same way humans do. from the perspective of the business um they remain the merchant of records. They are selling you know they happen to have that

</details>

<!-- chunk 5/10 -->

### Agentic Commerce and Trust

**Speaker A**: 通过代理促成的销售，但商业本质依然是商业。我们以不同方式提到过的另一个设计原则是，始终提供适当的、细粒度的、可编程的控制和护栏，以确保商业活动能够规模化进行。这基本上是在说，无论你希望控制得多精细、掌握多大主导权，或者希望它有多自由，你都不应该被迫采用新工具、换用新钱包，或是改变底层的支付网络，也不应该需要改变你的产品目录或展示产品的位置。基本上，这些控制和护栏应该是开箱即用的，并且能够灵活调整。我认为在消费者端，这体现为消费者依然可以掌控 Link 如何授权代理进行购买。而在企业端，正如我在谈论共享支付代币（shared payment token）时简要提到的那样，这体现为要确保我们所掌握的、关于底层买家及其代理（代表该买家操作）的良好信用信息，能够完整地传递给企业，以便企业能够智能地采取行动。因此，你知道，Radar 是我们的防欺诈保护产品。我们推出它已经十多年了。它过去主要针对交易欺诈。而现在，它会审查各种欺诈和滥用行为，以及机器人攻击，并评估多个层面的信用度——这不仅仅针对最终客户，也包括代表客户操作的代理。因此，这些 Radar 评分实际上在开箱即用时就已经包含在共享支付代币中，供企业与企业之间进行评估。但从根本上讲，我认为企业仍然是记录在案的商家（merchant of record）。消费者可以获得他们所需要的细粒度护栏和控制；然后在整个生态系统中，我们会尽可能地创造对称的信息。我的意思是，我们现在处理的交易量约占全球 GDP 的 2%。而在人工智能背景下，我们在这一 GDP 份额中占据了非常非常大的比例，因为基本上所有 AI 买家和卖家都在使用 Link，并接入了 Stripe。所以，你知道，这使我们能够切实了解到什么时候事情进展不顺，而且我们深知，通过预先提供这些信息来保护整个生态系统，很大程度上就是我们的职责。当人们深入剖析关于代理化商业的整个思路时，会发现这真的很吸引人，因为这就是技术能做到的，也是作为一个负责任的生态参与者所能做到的。但最终，这些问题中的很大一部分必将以某种方式诉诸法庭。我的意思是，法律系统将需要适应和演进，因为如果出了严重的差错，比如涉及巨额的商业交易，你要弄清楚谁该承担责任。最终，会不会是因为底层模型提供商的问题？因为代理可能失控了。我想这一切都需要时间，在生态系统中慢慢消化和解决。

<details>
<summary>Original English</summary>

**Speaker A**: sale facilitated through an agent but like the business is still um the business. Uh another design principle which we've touched on a bit in different ways is always provide appropriate granular programmable controls and guardrails to enable commerce to happen at scale. And that's basically saying like no matter how scoped in and in control you want to be or how much you want it to be a free-for-all, like you shouldn't have to adopt a new tool, move to a new wallet, change, you know, the underlying payment uh rails, you shouldn't have to change your product catalog or where you expose it. Like basically out of the box, um uh those those controls and guardrails should uh should eb and flow. And I think in the consumer case um that looks like consumers remaining in charge of how link authorizes agents to buy. Um and in the business case um you know I touched on this briefly in the context of shared payment token but it looks like making sure that the information we have about the goodness of the underlying buyer and the agent operating on that buyer's behalf are passed fully to the business. um to action intelligently. And so, you know, Radar is our fraud uh protection product. We've had it for uh over a decade. It used to be really about transaction fraud. Now, it looks at all kinds of um fraud and abuse and bought and multiple layers of goodness where there's not just the the the end customer, but also the agent operating on behalf of the customer. And so, those radar scores are actually included out of the box in the shared payment token uh for businesses to businesses to reason about But but basically I think business remains merchant of record. Consumer has as fine grain guard rails and controls as they need and then in the ecosystem there is as much uh symmetric information as as we can create. I mean we now look across just about 2% of of global GDP. Um, in the context of AI, we look at a very very large share uh of that of that GDB because basically all AI buyers and all AI sellers are on link um and on Stripe. Um, and so you know that that allows us to actually understand um when something is going sideways uh and we see uh very much our job to uh protect the ecosystem by by providing that information up front. It's really fascinating as one unpacks this entire line of thinking around agentic commerce because this what the technology can do that's what you can do as a responsible player in the ecosystem but like ultimately a lot of this will have to go to court one way or another. I mean the legal system will need to uh adapt and evolve because if something goes terribly wrong you know large commerce transaction you know who's at fault. ultimately could could it be the the model provider underneath because like the agent went haywire. I guess all of this is going to take time to work its way through the ecosystem.

</details>

**Speaker B**: 是的。而且不仅仅是在购买环节，对吧？比如，当有代理介入时，不仅仅是糟糕的购买行为，还有各种类型的不良行为，谁该对此负责？所以我确实认为这里的格局正在发生改变。特别是在谈到支付时，你刚才提到，过去人们并不太敢随意把自己的信用卡信息输入到互联网上。我觉得想想以下几点挺有意思的：像共享支付代币这样的东西，代理从来看不到底层的支付凭证。每笔交易都由 Stripe Radar 实时评分。然后商家去处理这些交易。支付凭证就像从来不会在不受信任的服务中传输一样。而以前，当人类把信用卡号码输入到一个随机网站（不是 Stripe，而是其他随机网站）时，凭证是会暴露的。所以不管怎么说，我认为提出这样一个问题也很有意思：这是否会为支付的信任和安全性带来实质性的提升？而我可以想象，答案是肯定的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Not just in purchasing, right? Like uh you know who is at fault for not just bad purchasing behavior but bad behavior of all types when when there's an agent involved. So so I do think uh the the landscape is changing there. when it comes to sort of payments in particular, you you mentioned a bit ago that um uh back in the day people didn't really trust just like putting their credit card on on the internet. I think it's interesting to think like with things like shared payment tokens, agent never sees the underlying credentials. Um each transaction is scored in real time by Stripe Radar. Um merchants go and handle the transactions. Credentials like never travel through untrusted services. the way they can when a human types a credit card number into a random website, not Stripe, but other random websites. Um, and so anyway, I think it's also interesting to ask like is there is there sort of meaningful payments trust and safety upside here? Um, and and I could imagine yes.

</details>

**Speaker C**: 所以回顾一下，从防欺诈的角度，以及可能也包括防失误的角度来看，比如你输错了数字之类的情况，由代理进行支付最终会比人类直接输入银行卡信息更安全，对吗？

<details>
<summary>Original English</summary>

**Speaker C**: So to play it back, agent payments would eventually be safer than than human just typing cards in terms of fraud, in terms of mistake presumably as well, right? Like if you type in the wrong number or something like that.

</details>

### Vibe Deployment

**Speaker A**: 是的。如果做到极致，做对了的话。我相信它应该会安全得多。今天，我认为首要的效应在于它更加方便。就比如，大多数时候我的信用卡并没有遭到欺诈者盗刷。反而是我自己手滑输错了我的 CVC 码。这很烦人，也让我很沮丧。不过，你知道，目前我认为我们获得的最大好处还是便利性。但发展到极致的话，是的，你完全可以想象，好吧，现在再也没有人会在互联网上传递这些随机的支付凭证了。顺便说一下，人们其实也不太需要在意交易是通过他们手头的10种不同的支付凭证中的哪一种进来的，对吧？他们真正在意的是有一个钱包。他们看到钱包里发生了什么。并且这个钱包可以在各个卖家之间以一种非常代币化、非常安全的方式使用。所以我想涵盖的另一个非常有趣的话题，你刚才也简要提到了，那就是“氛围部署（vibe deployment）”。那是什么意思？

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Done like done right in the limit. I believe it should be much safer. Today I think the first order effect is it's just more convenient. Like right like usually it's not a fraudster on my credit card. It's like me fat fingering my own CBC. It's annoying and I'm frustrated. Um but you know right now I think most of what we're getting is is convenience. But in the limit, yeah, you could you could totally imagine, okay, now nobody's passing these random payment credentials uh over the internet. And by the way, people also aren't really necessarily reasoning about transactions coming in through 10 different payment credentials they have, right? They really have a wallet. They see what happens in the wallet. Um and that wallet is used in a very tokenized uh secure way uh across sellers. So another really interesting topic I wanted to cover and that you mentioned briefly is vibe deployment. What does that mean?

</details>

**Speaker B**: 它是指在你构建完东西之后发生的事情，其实大家对它的讨论还不够多。关于编程这部分，一年前我们聊天时很多人都在讨论用 AI 来编程，这很合理，因为那时这个问题还没被解决，而现在基本上已经解决了——我们实际上也能在我们的数据中看到它已经被解决了。这些是一些有点随意的数据，但我发现它们很有趣。比如，自一年前我们交流以来，访问 Stripe 文档的代理（agent）流量增长了10倍以上。现在，代理流量约占我们所有文档流量的 40%。

<details>
<summary>Original English</summary>

**Speaker B**: It's what happens after you build the thing and it's actually not talked about enough but like the coding part uh a lot of people talked about AI for coding you know when we were talking a year ago that makes sense because it wasn't solved now that's basically solved um and we actually see that it's solved in our data. Um these are semi-random facts but I I find them interesting. So like agent traffic to Stripe's documentation grew more than 10x since we talked a year ago. uh agent traffic is now about 40% of all our docs traffic

</details>

**Speaker C**: 这意味着代理们正在试图弄清楚问题，它们会访问 Stripe 的技术文档来理解……

<details>
<summary>Original English</summary>

**Speaker C**: and meaning meaning that the agents are trying to figure it out and they go to the stripe technical documentation to understand uh

</details>

**Speaker B**: 这意味着现在的程序员，很大程度上既是代理，也是开发者，而且在某些细分领域，他们基本上全都是代理，完全没有人类开发者了。另一个真实的例子是我们的 CLI，即我们的命令行界面，历史上它曾像是一个相当小众的工具，只被一小群开发者使用。然而现在，它的使用量简直爆炸式增长，我们当时就在想，这是怎么回事？现在它 70% 的 API 资源请求都来自代理。所以你可以认为，如今使用我们 CLI 的绝大多数实体都不是人类。总而言之，我觉得尽管这些只是 Stripe 的两个有趣的轶事，但在整个生态系统中，你可以看到大量类似现象，告诉你“氛围编程（vibe coding）”是真实存在的，对吧？就跟你自己的亲身体验是一样的，对吧？那部分已经行得通了。但是，然后呢？比如，一个代理在 20 分钟内为你写出了一个完整、可运行的应用程序。太棒了。我们喜欢这样。好的。但在那个应用程序真正上线之前，你仍然面临着相当大的摩擦，对吗？所以你必须去——我指的是，这取决于你在做什么——但你很可能必须去数据库提供商那里创建一个账户，然后是你的认证提供商，接着是你的托管服务，你就像在不同的平台间跳来跳去。你需要面对所有这些仪表盘。你就像在想，这怎么搞，只能靠手动复制粘贴各种东西，管理凭据、API 密钥以及其他各种事务。而且，这其中的每一个服务都有它自己的注册上手流程。所以，这跟我们刚才讨论的支付流程的风格有些不同，但它确实是一个非常低效的、需要填一堆步骤的过程。而且，每一个流程就像以前的支付流程一样，是为像你我这样的人类设计的，让人类坐下来点击那些古怪的设置向导。我猜这以前并没有太困扰我们，因为我们做这种事的频率不高，那时候最困难的部分是编程部分。但现在既然应用程序可以在 20 分钟内被编码构建出来，那么好吧，现在最耗时的一环（the long pole）变成了部署这个东西。所以总之，氛围编程变得简单了。而氛围部署（vibe deployment）则变成了更大的瓶颈限制。因此，实际上就在过去几个月里，我们为此推出了 Stripe Projects。基本上就是说，代理应该能够——去注册、配置和集成它们部署应用程序所需的所有服务，而且它们应该能够直接在命令行中完成这些工作。不仅是 Stripe 的服务，对吧？这就像是一个完整的生态系统，比如你可以使用 Vercel 和 Supabase 等等。

<details>
<summary>Original English</summary>

**Speaker B**: meaning the coders now are are almost as much agents as they are developers and in some segments they are basically all agents and and uh not at all developers and another example actually is is our CLI our command line interface which historically was like a pretty niche tool used by like a pretty small group of developers. Um it now it just like exploded and we were like what is happening? And it's now um 70% of its API resource requests are from agents. So like you could think of like the majorities the majority of entities that are using our CLI today like aren't people. So anyway, I think though you know those are just two like fun stripe anecdotes, but there's lots of them across the ecosystem you can look at that tells you like vibe coding is real, right? Just your own lived experience is the same, right? That part worked. But then what? So like an agent writes you like a complete working application in 20 minutes. Fabulous. Like we love it. Okay. But you've still got this pretty big friction before that app is actually live, right? So you got to go like I don't I mean it depends what you're doing, but you got to probably create an account with your database provider, then your off provider, then your hosting service, and you're like bouncing around. You got all these dashboards. you're like I don't know how you do it like copy pasting stuff by hand and managing credentials and API keys and whatever else and and every one of those services has its own onboarding flow. So like a little different flavor than the payments flow we talked about but like it's a pretty inefficient fill out a bunch of steps. Um and every one of them just like the payments flows was designed for like you and me as humans sitting down and clicking through this like weird setup wizard thing. Um, and I don't think it really bothered any of us that much because we weren't doing it that much because the hard part was the coding part. But now that like the app could be built in coded in 20 minutes like okay the long pole is deploying the thing. Um, and so anyway, vibe coding was easy. Vibe deployment um has become like more of the binding constraint. Um, and so we actually we we recently like in the last couple months uh launched Stripe projects for this. Um, but basically it's like agents should be able to um well sign up for and configure and integrate all of the services they need to deploy an app and they should be able to do that like right from the command line. And it's not just Stripe services, right? was like a whole ecosystem of like you get like Verscell and Superbase and

</details>

<!-- chunk 6/10 -->

### 编排部署与 Stripe 的角色

**Stripe Representative**: Cloudflare 还有 Twilio，或者是任何你需要的，比如 Clerk。呃，我想我们大概在一两周前刚刚宣布了另外 16 个合作伙伴。呃，总之，生态系统对此充满了热情，因为结果发现大家似乎都有着同样的问题。呃，呃，开发者们都有同样的问题，那就是现在的最大瓶颈就像是部署；而企业们也有同样的问题，那就是他们之前的入驻流程是为人类设计的，但现在他们需要让它，呃，也能为智能体工作。

<details>
<summary>Original English</summary>

**Stripe Representative**: Cloudflare and Twilio like whatever you need Clerk. Um I think we announced like 16 more partners a week or two ago now. Um and anyway there's a lot of enthusiasm from the ecosystem because it turns out that everyone kind of has the same problem. Um uh developers all have the same problem which is now like the long pole is like the deployment and businesses have the same problem which is like their onboarding was designed for humans and now they need it uh to work for agents.

</details>

**Interviewer**: 为了切中要害，进一步来说，为什么 Stripe 会关心这个？

<details>
<summary>Original English</summary>

**Interviewer**: And to bring it home why does Stripe care?

</details>

**Stripe Representative**: 好的，所以我认为有很多事情是 Stripe 所关心的，但在纸面分析上你可能会觉得，为什么 Stripe 要去关心这个？我的——最诚实的答案是，我们关心是因为它正日益成为瓶颈。就像那种构建应用的门槛已经消失了，但是部署的门槛却像是一种真正的摩擦阻力。而且如果你仅仅把视角往回拉，就像好的，抛开作为一家支付公司不谈，我们的使命是增加互联网的 GDP，其中很大一部分在于我们如何让更多的公司起步，以及我们如何帮助他们更快地赚到类似于他们的第一笔钱并从中扩大规模。因此，如果一个有想法的人可以创建一款应用，但却无法将其部署，那他们就无法进行销售。所以，直接消除部署的摩擦显然，就像，扩大了，呃，互联网经济，并且你知道，你主要可以把它看作是，呃，就像，仅仅——仅仅——仅仅像编排（orchestration），就像我们所做的所有事情就是编排。所以，呃，如果有其他人想要、能够并且确实去做了这种编排，我们也是完全可以接受的。但是我们当时就像是在看着开发者们试图让他们的东西上线，我们也在看着企业们试图让那个东西就像能被开发者使用，我们就觉得，好吧，我认为我们可以，我们可以让这个市场，呃，稍微变得更加顺畅一点。

<details>
<summary>Original English</summary>

**Stripe Representative**: Okay so I think there's a lot of things that Stripe cares about that on paper you'd be like why does Stripe care? I'm the the honest answer is we care because it was becoming the bottleneck. like the barrier to building is gone, but the barrier to deploying is like a real friction. And if you just zoom back like okay, separate from being a payments company, our mission is to increase the GDP of the internet, a big part of that is how do we get more companies off the ground and how do we help them get kind of their first dollar faster and scale from there. And so if a person with an idea can create an app but can't deploy it, they can't sell. And so removing deployment friction directly obviously like expands um the the internet economy and you know you can think of it primarily as um like ju just just like orchestration like all we're doing is orchestration. So, um, if someone else wanted to and could and did orchestration, we'd be cool with that. But we were like looking at the developers trying to get the thing live and we were looking at the businesses trying to get the thing like used by developers and we're like, okay, I think we can we can make this market uh a little bit smoother.

</details>

**Interviewer**: 是的。而且回放一下编排的概念，因为你们有所有这些合作伙伴。所以最终你们做托管、可观测性、呃，电子邮件、队列（Q）、密钥等所有这些事情，但那是由不同的，呃，供应商提供的，而你们提供的是黏合剂，以确保人们能够安全且高效地部署他们的智能体。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. And to play back orchestration because you have all these partners. So ultimately you do hosting observability uh email Q secrets all the things but that's provided by different uh vendors and you provide the glue to make sure that people can deploy their agents safely and efficiently.

</details>

**Stripe Representative**: 是的。完全正确。完全正确。

<details>
<summary>Original English</summary>

**Stripe Representative**: Yes. Exactly. Exactly.

</details>

### AI 经济中的代币变现与计费模式

**Interviewer**: 非常酷。好的。那么以上就是关于 Vibe 部署的内容。将代币（Tokens）作为金钱来变现，呃，也是一个引人入胜的话题。让我们就像从最——最——最开头讲起。从 Stripe 的角度来看，代币变现意味着什么？这是一个很大的问题，因为从全球的视角来看，代币变现意味着什么，就有点像，好的，实际上整个下一代 B2B 和部分 B2C 会如何变现呢，看看那——那——那过去十多年的 SaaS，呃，有着那种非常漂亮且易于变现的经济学模型，对吧？特别是在 SaaS 领域，就像你构建了一次产品，然后你每增加一个客户，为他们提供服务的成本基本上为零，就像边际成本接近于零，这就是为什么 SaaS 的利润率非常高的原因。而且这也正是为什么，你知道，固定费用的订阅或基于席位的许可证在 SaaS 中，呃，运作得非常好的原因。呃，AI——我笼统地说 AI，因为你可能真的就是在售卖 LLM，但也可能是在售卖，你知道，某种作为 LMS 包装器或在其之上运行的产品，或者是重度由 LM 驱动并且——并且需要大量代币的产品。呃，它打破了那种模式，因为显然每一次提示（prompt）和每一次 API 调用以及每一项任务，呃，突然之间都有了一个——一个真正的边际成本，而在 SaaS 中这是没有的。推理不是免费的。因此，现在你有了所有这些企业，在这些企业中你的客户如何使用你的产品直接决定了，呃，你是赚钱还是亏钱。而且这是一个非常不同的游戏。呃，并且，呃，你知道，从——从我们的有利视角来看，就像归根结底那意味着一部分需求，即基于使用量的计费对于 AI 公司来说真的至关重要。就像你需要能够实时计量客户实际消耗了什么，然后向他们收费，呃，以一种显然那——那——那样能够与你的——与你的底层成本相一致的方式。

<details>
<summary>Original English</summary>

**Interviewer**: Very cool. All right. So that's vibe deployment. Tokens as money is uh also a fascinating topic. It's like taking it from the the the top. What does it mean to monetize tokens from a Stripe perspective? That's a big question because what does it mean to monetize tokens from a world perspective is kind of like okay actually how's the whole next generation of B2B and some B TOC going to monetize look like the the the last kind of decade plus of SAS uh had like pretty beautiful and simple to monetize economics right and in particular with SAS like you build a product once and then you get one more customer and it costs you basically nothing to serve them like marginal costs are near zero and that's why SAS margins are really And that's why, you know, the fixed fee subscriptions or seatbased licenses work really well um in SAS. Um AI, and I say AI generally because like you could literally be selling LLM, but you could also be selling, you know, some product that's a wrapper or on top of LMS or a product that's heavily powered by LM and and requires a lot of tokens. Um it breaks that model because obviously every prompt and every API call and every task um has a a real marginal cost all of a sudden, which it didn't have in SAS. the inference isn't free. And so you now have all these businesses where how your customers use your product directly determines uh whether you make or lose money. And that's a very different game. Um and uh you know from from our vantage point like part of what that boils down to is the need for usage based billing as really critical for AI companies. like you need to be able to meter what customers are actually consuming in real time and then charge them um in a way obviously that that that aligns with your with your underlying costs.

</details>

**Interviewer**: 而且你从你的视角来看，在目前的阶段，从供应商创业公司的立场出发，在 AI 经济中几乎所有的参与者都在，呃，使用基于使用量的计费吗，还是说这仍然是按席位和按使用量计费之间的一种混合模式？

<details>
<summary>Original English</summary>

**Interviewer**: And do you see from your perspective pretty much all the players in the AI economy from a vendor startup standpoint uh use usage based billing at this stage or is that still a mix between per seat and per usage?

</details>

**Stripe Representative**: 我看到很少有正在扩张或已经扩张的 AI 公司仍然完全专属地采用订阅制或基于席位的模式。而且根据我与他们的交流，我相信那是因为一个简单的原因，那就是那里的经济账算不平，因为你知道，有些人在，呃，使用量巨大，而有些人的使用量并不多，这些使用量大的人会让你花费巨大的成本，而那些人则花费你不了多少成本，如果没有一个基于使用量的计费表，你很难将绵羊和山羊区分开来并对他们进行恰当的定价。话虽如此，呃，这些企业中的许多确实有一个基于使用量的计费方案，但它是作为你们可以认为是类似于固定费用订阅的一种补充存在的。所以就像一个很好的例子是 Lovable。当他们推出产品时，他们通过 Stripe 计费提供了一个类似于简单的订阅服务，这完全合情合理。他们处于早期，他们移动速度很快，他们想要迅速变现。订阅制对于消费者来说也非常熟悉和简单。呃，你知道，如果你考虑一下 Lovable，就像他们的一些，呃，目标用户是那种不是很懂技术的，他们会怎么想类似于，哦，我该如何理解一个代币或者一个积分的概念，对吧？好的。所以，所以他们——他们从订阅制起步，但随后随着——随着公司的发展以及——以及他们部分成本的增长，他们的计费需求演变了，并且，呃，他们需要至少有部分是基于实际的，呃，代币消耗来进行收费的。所以他们所做的是一种混合计费模式，这——这实际上也就是我们看到大量企业，尤其是那些包含一个 B2C 成分的企业正在采用的模式，即他们在他们的订阅制基础之上叠加了基于使用量的计费。所以当客户达到某个阈值时，你知道，而且顺便说一句，很多人都有那种免费增值额度（premium thresholds），但是随后在那个额度之上，他们通常会有类似于固定费用的设置，你知道，每个月 25 美元或者每个月 100 美元，呃，可以享受一定数量的积分额度，然后在那之上，呃，你——你就会有基于使用量的计费。所以一旦客户达到了阈值，在这个例子中的 Lovable 就会，就像，精确地根据超出的代币消耗数量来收费，而且，你知道，我认为那种——那种——那种一致性将会吸引一大批能够舒适地接受订阅制的人入门，但是随后某种程度上你的在——在任何具有实质意义的业务量上，你的收入就会非常直接地随着，就像客户如何使用产品而规模化增长，并且相应地随着，就像你提供该产品所耗费的多少成本而规模化增长。呃，所以客户只为他们所获得的东西买单，而你也能确保你的变现，呃，能够覆盖，呃，那些——那些你必须要承担的底层成本。而且 11 Labs 是另一个例子，就像他们经历了完全相同的事情，确切地说就像从订阅制起步，他们最近转向了这种类似于即用即付的计划，呃，而且——而且这只是我们目前在 AI 领域几乎所有地方都能看到正在上演的一种模式。

<details>
<summary>Original English</summary>

**Stripe Representative**: I see very few scaling or scaled AI companies that are still exclusively subscriptions or seatbased. And I believe from my conversations with them that that is for the simple reason that the economics there don't make sense because you know you have some people that are uh using a ton and some people that are not using very much and these people cost you a ton and these people cost you not very much and it is very hard to separate the sheep from the goats and price them appropriately without a usagebased meter. That said, um many of those businesses have a usagebased offering, but it is complementaryary to what you can think of as like a fixed fee subscription. So like a great example is lovable. When they launched, they had like a simple subscription through Stripe billing makes total sense. They were early, they're moving fast, they wanted to monetize quickly. Subscriptions are also very familiar and easy for consumers. Um, you know, if you think about a lovable, like some of their uh target users are like not very technical, like how are they going to feel about like, oh, how should I reason about a token or a credit, right? Okay. So, so they they started with subscriptions, but then as the as the company grew and and some of their costs grew, their billing needs evolved and uh they needed to charge at least somewhat based on actual uh token consumption. And so what they did is a hybrid billing model which which actually we're seeing a large number of businesses especially businesses that have a BTOC component do where they have usagebased billing on top of their subscriptions. So customers hit some threshold you know and by the way many people have premium thresholds but then above that they often have like a fixed fee you know $25 a month or $100 a month uh up to some number of credits and then above that uh you you have usage based billing. So once customers hit the threshold, lovable in this case charges like precisely based on the number of tokens consumed above that and you know I think that that that alignment is going to get a bunch of people in the door comfortable with subscriptions but then sort of your at at any volumes that matter your revenue is scaling very directly with like how customers are using the product and correspondingly with like how much it is costing you to provide that product. Um so customers pay only for what they get and you make sure you monetize uh for um for the underlying cost that you're going to have to bear. And 11 Labs is another example like they went through the exact same thing literally like started with subscriptions they recently moved to this sort of pay go plan um and and this is just a pattern that we see playing out pretty much everywhere in the AI space right now.

</details>

### 为智能体计费的演变

**Interviewer**: 一旦你开始向智能体（agents）收费，计费方式会有很大的改变吗，呃？

<details>
<summary>Original English</summary>

**Interviewer**: Does billing change much uh once you start charging agents?

</details>

**Stripe Representative**: 所以，呃，我认为是的，呃，有几个原因。一个是智能体可以以机器速度进行消耗。因此，即便你是，就像，呃，即便你是在做一件基于使用量计费的事情，但你是，就像在月末进行结算，那么等到了月末的时候，一个智能体可能已经花掉了——我敢说人类在有智能体为他们工作的情况下一定程度上也能花很多——但就像特别是智能体，它可能已经花费掉了类似于极其惊人的金额。所以实际上，呃，我认为在智能体的世界中，我们将会越来越多看到的是实时计量，就像你消耗了什么，以及实时计费，这，呃，实际上就是我们和 Metronome 共同构建的内容，即针对非常复杂模型的实时计量与基于使用量的计费，以及和 Tempo，呃，区块链的合作，在那里，呃，你知道，智能体正在，呃，实时地消耗代币，并且，呃，为那些代币的成本付款结清。而那很重要，因为智能体能够购买机器速度。这是可行的，因为，呃，有了，呃，在 Tempo 和 Metronome 之间的大量——那些基础设施。呃，并且，呃，智能体也很乐意就像以一种非常字面意义上的即用即付的方式买单。此外，企业也需要它们即用即付，这样它们就不会，呃，累积起一大笔开销然后——然后突然消失跑路。是的，这——这在下游后果方面也非常引人入胜，对于它对，比如，财务和会计，以及像这样同样需要以那种速度运转的系统意味着什么。

<details>
<summary>Original English</summary>

**Stripe Representative**: So uh I think so uh for a couple reasons. One is agents can consume at machine speed. And so even if you're like um even if you're doing a usage based thing, but you're like charging at the end of the month, by the time you've gotten to the end of the month, an agent can have spent I bet a human can too to some extent with agents working for them, but like especially an agent can have spent like an egregious amount. And so actually um I think in the world of agents what we're going to see more and more of is real time metering like what have you consumed and real time billing which is uh actually what we have co-built between metronome so real time metering usage based billing for very complex models and tempo uh blockchain where um you know agents are uh consuming tokens in real time and uh paying down uh for the cost of those tokens. And that's important because agents can buy machine speed. It's viable because uh of uh a bunch of the the infrastructure between Tempo and Metronome. Um and uh agents are happy to just like pay as they go in a very literal way. Plus, businesses need them to be paying as they go so that they don't uh rack up a bunch of spend and then and then go dark. Yeah, it's it's fascinating also in terms of downstream consequences for what it means for like finance and accounting and like systems that need also to move at that speed.

</details>

<!-- chunk 7/10 -->

### 会计在 AI 时代的新定义

**Speaker A**: 完全同意。我们有一款收入确认的会计产品，主要是提供给很多采用传统订阅模式的企业，但最让痛点集中的地方其实是，当你面对海量的行数据激增时，传统的电子表格会计方式根本行不通，因为微交易（microtransactions）正实实在在地发生。我还认为，这正在改变“会计”一词的含义。我不提那家公司的名字，但我曾与一家相当成功的 AI 公司的二号财务人物交谈，有些结合非常有趣。首先，他们就像是“会计兼工程师”的复合体，由于他们处理的数据规模庞大，他们必须具备这种能力。其次，他们所做的并非你我传统认知中那种仅仅是“结账”的会计工作。当然，他们肯定需要结账，但他们的职责还包括发现那些异常的状况。我之所以和他们交流，是因为他们识别出了一些欺诈模式，并希望在这方面获得帮助。总之，这非常有意思：在这样一家 AI 公司里做会计到底意味着什么？它绝对需要新工具，绝对需要新系统，甚至可能需要完全不同的技能组合。并且，你所要负责的不仅限于结账，还要审视整个收入识别技术栈（Revre stack）并思考：“这反映了我们业务怎样的健康状况？这反映了我们业务中存在怎样的欺诈和滥用行为？这又反映了我们产品里存在哪些漏洞？”

<details>
<summary>Original English</summary>

**Speaker A**: Totally. I mean we have a revenue recognition accounting product and it's mostly needed by I mean we provide it to a bunch of businesses who have traditional subscriptions but where there's the most acute pain is actually like traditional accounting in spreadsheets like does not work when you have this just like proliferation of rows because these are like microtransactions are truly happening. Um, I also think it's changing uh what it means to be an accountant. I will uh avoid naming the company, but I was talking to the sort of number two in accounting at a pretty successful AI company, and couplings were interesting. One is they were like a hybrid accountant engineer, which they needed to be because of the scale of the data they were dealing with. And two, they weren't doing like accounting in the traditional you and me sense of like just close the books. like they have to close the books for sure, but their job was also to find like weird anomalous stuff happening and I was talking to them because they were like identifying some fraud patterns and wanted help with them. Um, but anyway, just very interesting like okay, what does it actually mean to do accounting at like one of these AI companies? Definitely needs new tools, definitely needs new systems, probably a different skill set. And then like what you're accountable for really isn't just closing the books. like looking across the whole Revre stack and saying, "What does this tell me about the health of our business? What does this tell me about fraud abuse in our business? And what does this tell me about breakages in our product?"

</details>

**Speaker B**: 是的。所有这些最终都演变成了一个需要实时处理的庞大数据问题，对吧？这也正是 ClickHouse 这类公司崛起的原因：谁能实时处理海量数据，谁就成为了必需基础设施的核心部分。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. All of which becomes a massive data problem that needs to be treated in real time, right? Hence the rise of the clickous of the world like whoever can process massive amounts of data in real time becomes the core part of the required infrastructure.

</details>

### AI 时代的新型欺诈：代币盗窃

**Speaker B**: 好的。你曾在某个地方写到过关于“代币盗窃（token theft）”的内容，我想确保我们今天能聊聊这个话题。那到底是什么？作为一种新型的欺诈手段，代币盗窃究竟是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Okay. You wrote somewhere about token theft and I wanted to make sure that we cover that. So what is that? What is token theft as a new form of fraud, I guess?

</details>

**Speaker A**: 是的，这是一种新型的欺诈形式。我认为这是目前 AI 领域里最被严重忽视的话题之一，被忽视的程度可能相当高。欺诈者们已经意识到，在 AI 领域，你其实并不需要去窃取金钱或用户凭证。你只需要窃取“代币（tokens）”就可以了。代币具有非常真实的价值，对吧？你可以用它们来构建各种产品。你可以在市场上转售它们。或者你可以在其上包装出一个新产品而无需支付一分钱，然后直接去销售那个全新的产品。这有点像倒卖，但表面上看起来并不像是在销售某个服务的订阅。它看起来就像是你在销售你自己独立研发的产品，但实际上在后端，它完全是由别人的服务所驱动的。而对于 AI 公司来说，这可能在我们之前关于 SaaS 的对话中有所暗示，但这种风险真的是生死攸关的，对吧？如果有人偷了一点你的 SaaS 服务，这毫无影响，因为这在边际上并没有真正增加你的任何成本。但是当有人窃取你的代币时，如果你的欺诈率足够高，你产品的经济模型实际上会崩溃得非常快。不管怎样，由于我们基本上与所有的 AI 公司都有合作，我们得以坐在前排，非常有趣地观察着正在实际发生的事情以及不断演变的欺诈模式。目前主要有三种模式，不过我不认为这三种模式会永远存在，因为我们在过去三个月里已经在很大程度上消灭了它们。但是新的欺诈模式总会层出不穷。但我认为这三种模式对于理解这个领域的广度很有启发意义。第一种是“多账号滥用（multi-account abuse）”。也就是恶意行为者一次又一次地疯狂注册账号，只为了获取那些新用户积分。当我仔细查看数据时，这种行为的庞大规模着实让我震惊：在所有的 AI 公司里，超过六分之一的注册竟然都属于这类滥用。顺便说一句，这也会让公司感到非常困惑。比如：这些是优质客户吗？这些人到底是谁？而且这对公司来说代价极其高昂，因为我不得不在这些免费产品上为相对极少数的人消耗大量的代币，而这些极少数人却在疯狂注册海量的账号，并实际上消耗了相当大数量的代币。好的，这是非常非常处于漏斗最顶端的情况。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it's a new form of fraud. It's I think one of the most underdised topics in AI right now, maybe by a lot. Um fraudsters have figured out that in AI um you actually don't really need to steal money or credentials. Uh you can just steal tokens. And tokens have real value, right? You can use them to build things. Um you can resell them on marketplaces. um you can wrap a new product on top uh without paying a scent and go and sell that real that new product. So kind of like resell, but it doesn't look like you're selling the subscription to the thing. It looks like you're selling this other product that you've come up with on your own, but really in the back end it's completely powered by someone else's thing. Um and for AI companies, maybe this is implied by our earlier conversation on SAS, but like the risk is existential, right? If someone stole a little bit of your SAS, like didn't matter because it didn't really cost you anything on the margin. um when someone steals your tokens, if your fraud rate is high enough, the economics of your product actually um break really fast. So anyway, because we um work with basically all the AI companies, we have this interesting front row seat into um what's actually happening and the fraud patterns um playing out. And right now um there's three and I don't think these will be the three forever because we've already largely burned down these three over the last three months. Uh but new ones will pop up. But I think these three are just um instructive for reasoning about sort of the breadth of the space. Um one is multi-account abuse. So this is like bad actors just like hammering your sign up again and again and again and again so that they can get those like new user credits. Um and the scale of this actually shocked me when I looked at the data. So like more than one in six signups at AI companies are this kind of abuse. And by the way that's also very confusing for the company. Like are these good customers? Who are these people? But it's very expensive for the company cuz like I've spent a bunch of tokens on these free products for you know a relatively small number of people who are spinning up a massive number of accounts and actually uh consuming quite a bit of tokens. Okay, so that's like very very top of funnel.

</details>

**Speaker A**: 我认为第二个非常有趣的例子是“免费试用滥用（free trial abuse）”。这类欺诈者会进来创建一个免费试用，绑定一种支付方式，然后他们会耗尽所有的积分额度，但他们绝无转换为付费用户的意愿。你要知道，免费试用滥用在整个互联网的各种形式中一直存在，无论是不是 AI，但在过去 6 个月里，Stripe 上的此类滥用事件增加了一倍多，而其中大部分的增长都来源于 AI 以及 AI 相关企业。为了让你们直观感受一下这到底有多赚钱，甚至有整个周边的黑灰色产业围绕它建立了起来。我不知道你是否曾被推销过“免费试用卡”。最近就有人向我推销过。它基本上就是说，“哦，你可以批量生成这种免费试用卡。它们在 24 小时后就会自动过期，所以你永远不用付费。”如果你或我拥有这样一张卡，我们大概率会用它来进行一些合法的目的，比如试用某项服务，只是为了省去之后取消订阅的麻烦。但是对于欺诈者们来说，他们完全可以引爆这些东西，疯狂注册一大堆免费试用账号，疯狂消耗大量的代币，而根本不打算付费。然后第三种模式比这更处于产业链的下游位置，基本上就是我们刚才讨论的基于使用量（usage-based）的计费模式。有些人会累积高达数千美元的巨额费用，然后在月底出账单时却从不付款。这就好比经常发生在餐厅里的“吃霸王餐（dine and dash）”行为，只不过他们吃的是“代币霸王餐”。而且不幸的是，到那个时候——再次强调，这是 AI 而不是 SaaS——公司实际上已经默默承担了那些代币所产生的所有成本。

<details>
<summary>Original English</summary>

**Speaker A**: Another example I think is interesting is free trial abuse. So these are like fraudsters come in, they create a free trial, they put down a payment method, um they drain through like all of the credits, but they never have any intent to convert. Um, and you know, free trial abuse has always existed in various forms across the internet, AI or not, but it's more than doubled on Stripe in the last 6 months, and most of that doubling is coming from AI and uh AI businesses. And just to give you a sense like uh how lucrative this is, like there's whole cottage industries built around it. So, I don't know if you've ever been marketed a free trial card. I was recently marketed one. It's basically like literally it's like, "Oh, you can like spin up free trial cards. They expire in 24 hours, so you'll never have to pay." And like if you or I had one, we'd probably use it for like some legitimate purpose to try out a service and just not have to go through the pain of cancelling, but like literally fraudsters can just like explode these things and spin up a bunch of free trials and spend a bunch of tokens um with no intent to convert. Um and then the third is is a little further downstream of this which is basically like we talked about the usage based uh billing. Folks are racking up like thousands of dollars of uh costs and then being build at the end of the month uh and never paying. And so like whatever the dine and dash that happens in restaurants is like a d and dash um but it's but it's for for tokens and unfortunately at that point again this is AI not SAS so like the company has borne the cost uh of of those tokens.

</details>

### 黑市交易与“套壳”欺诈产业

**Speaker B**: 抱歉，如果这是个显而易见的问题的话。我猜我大概会是个很糟糕的欺诈者，因为这对我来说甚至都不是那么明显。所以……如果我免费获得了这些代币，我到底能用它们做些什么呢？我想，如果我是从像 Claude 或 ChatGPT 这样的通用大语言模型（LLM）那里获得了代币，我还能明白我可以拿它做什么。但如果我去找 Cursor、Lovable 或者 ElevenLabs 薅到了代币，我实际上又能拿它做些什么呢？

<details>
<summary>Original English</summary>

**Speaker B**: and sorry if that's obvious and I guess I would be a terrible fraudster because it's not even super obvious to me. So uh if I get tokens for free what do I actually do with them? So I guess if I get tokens from a general purpose LLM like claude or chat GPT I could see what I do with it. If I go to a cursor or lovable or 11 labs what what is it that I actually do?

</details>

**Speaker A**: 是的。问得非常精确。好的。其实，你拿它做什么在很大程度上取决于……这项服务到底是什么样子的？这些代币原本是用来干什么的？你刚刚一针见血地指出，哦是的，你只需要从底层的大语言模型中获取代币。这很容易理解。而对于那些在模型基础之上的上层业务来说，就存在着大量的“倒卖滥用（resale abuse）”。所以，你真的会在其他各大市场上以略低于原价的折扣价格出售它——也就是你应该支付但实际上你并没有支付的那个基础价格。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Exactly. Okay. So what you do with it very much uh changes based on like what's the service like what exactly were these tokens uh meant for? Um you nail on the head for like oh yeah you just like get the tokens from the underlying LLM. Fine. um for those sort of um businesses that are a layer above that a bunch of resale abuse. So, uh you literally sell it sometimes in other markets uh for a slightly discounted price uh a discounted price on the base price that you should have paid but you didn't pay.

</details>

**Speaker B**: 所以，存在一个像暗网一样的庞大市场网络，在上面你会说，比如“花 2 美元就能使用 Cursor 或 Lovable”，但我的成本其实为零，所以我能从中赚钱。

<details>
<summary>Original English</summary>

**Speaker B**: So, there's a dark like a dark web of marketplaces where you say like use a cursor or lovable for $2 but my cost is zero therefore I make money.

</details>

**Speaker A**: 是的。完全正确。比如，我就把我的登录凭证之类的账户信息卖给你。不过除此之外……所谓的“长尾效应（longtail）”听起来规模很小，但其实存在着非常多针对特定领域的专业欺诈模式。例如，有人窃取代币去大量生成内容，然后利用这些内容以各种诈骗手段骗取巨额钱财。举个很简单的例子，我们看到有人大批量地使用 AI 生成音乐曲目，然后把它们上传到 Spotify 和 Apple Music 这样的平台，接着雇佣虚假的播放量水军刷榜，以此来赚取高额版税。另外，对于几乎所有那种“套壳业务（wrapper businesses）”来说，还有另一种在套壳之上的多层嵌套欺诈形式。他们不会只是在淘宝（Taobao）等电商平台上转售你的订阅服务，他们甚至会直接原原本本地克隆这家 AI 公司，对吧？你完全可以用 AI 快速写出一个前端网站代码。它的后端只是原封不动地吐出从你所窃取的服务那里获得的结果，然后你就可以把这个产品当作你自己的全新产品来卖。而且价格卖得更便宜。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Exactly. So, so just say I give you my login credentials whatever. Um there's also but but then there's just like there's just this like uh longtail makes it sound small but uh very domainspecific fraud patterns. So for example um people steal tokens to create content that they then use to extract money in all sorts of scammy ways. So, a simple example, uh, we see people going in and like mass generating music tracks and then uploading them to Spotify and Apple Music and then getting fake streamers and then collecting royalties. Um, or then for like basically all of the rapper businesses, there's this whole other layer of rapper on a rapper where like rather than just resell the subscription on places like Telbal, they'll like literally clone the AI company, right? You can just like vibe code a website. The back end is just like spitting out exactly what you got from the service that you're stealing from and then you like sell the product as yours. Uh but cheaper.

</details>

**Speaker B**: 你们打算把这些交给那些有创造力的人吗？我……

<details>
<summary>Original English</summary>

**Speaker B**: Are you gonna give it to people that they're creative? I

</details>

<!-- chunk 8/10 -->

**Speaker A**: 这听起来简直比创办一家真正的公司还要难。

<details>
<summary>Original English</summary>

**Speaker A**: I mean that sounds almost harder than starting an actual company.

</details>

**Speaker B**: 是的。我不知道，我是说他们确实在上面投入了大量时间。Token 也是非常有价值的。你知道，有趣的是，当我们大约在六到九个月前开始看到这些不同形式的趋势时，它们随后就大幅升级了。你知道，在和 AI 公司交谈时，那些大型 AI 公司都在全力应对这个问题，因为这几乎是关系到他们利润率的最生死攸关的事情之一。他们一直和我们在战壕里并肩作战，识别问题。他们就好像，你知道，我们只要看到一个问题，我们就建立一个模型。就像多账号滥用，好吧，在登录的时候，有一个 API。你把你所知道的信息发给我们，我们给你返回一个评分，如果他们是坏人你就封禁。在免费试用开始时，也是一样。当人们积累使用量时，你把所有的元数据发给我们，我们给你返回他们是否有欺诈嫌疑，你可以要求他们充值，或者切断服务之类的。就像我们看到的每一个这样的情况一样，我们在几周的时间内就得到了……你知道，通常这甚至不像是一个成熟的产品。它就像一个 API，你发给我们一些东西，我们发给你一些东西。然后采用率就一直很好。所以 AI 公司都在全力应对。我认为有趣的是，每家公司都将成为一家 AI 公司，而我不认为整个行业都已经开始思考这个问题，或者真正推理出，实际上正在发生的大部分欺诈不是传统的凭证或支付欺诈。它就像我们过去所说的第一方滥用，对吧？比如转售滥用、账号共享、多开账号或者免费试用滥用。这就像是第一方滥用。而且我认为并不是以前没有发生过第一方滥用。只是至少在 SaaS 产品中，第一方滥用不会让你付出任何代价。所以，首先，通过我们提到的那些例子来免费获得一点 Salesforce 服务并不是那么有用，这在大多数 SaaS 中都不适用。其次，即使找到一种方法来揩油是有用的，并且作为欺诈者你可以从中获得一点利润，这实际上也没有让企业损失多少，因为他们的边际成本为零。因此，随着每家企业都变成 AI 企业，我认为我们在关于 Radar 的工作中，真正地把我们的防欺诈产品从关注交易转移到关注整个客户生命周期，并且从防范传统欺诈转移到防范端到端的滥用。但我认为整个行业还没有达到这个阶段。你知道，你和我都谈论过 AI 带来的很多经济上的好处，但我认为只有在安全的前提下，这些好处才能真正实现。所以，举个例子，六到九个月前，当我和其中一些 AI 公司交谈时，他们会说，“哦，我知道了。我打算通过取消免费试用来解决我的免费试用滥用问题。”或者，“我打算通过只做销售主导的模式，只针对企业客户，而不做产品主导增长 (PLG) 来解决我的免费试用滥用问题。”但是，你知道，我今天很少听到这种说法了。为什么？不是因为欺诈问题已经完全解决了，而是因为每个人都知道他们需要智能体（agents）也成为他们的买家。如果智能体要成为他们的买家，他们最好有一个自助服务模式。他们最好有一个 PLG 模式。他们绝对不想切断那个增长来源，然后只把赌注押在高度安全的销售主导模式上。但看到 Token 盗窃的发展确实很有趣。我完全同意，欺诈者很有创造力，但我认为那正是 Token 有多宝贵的一种体现。因此，我实际上认为这种“创造力”不会消失。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I don't know. I mean, they definitely put a lot of time into it. Tokens are also very valuable. And you know, what's been interesting as we sort of started seeing these trends maybe at this point six, nine months ago in various flavors, but then they escalated a bunch. You know, talking to AI companies, the large AI companies are all over this, like it's one of the most existential things for their margins. They have been in the trenches with us identifying the issues. They have been like, you know, we literally see a problem, we build a model. Like, multi-account abuse. Okay, at the time of login, there's an API. You send us what you know, we send you back a score, you block if they're bad. At the time of free trial start, same thing. As people are accumulating usage, you send us all the metadata, we send you back whether they're fraudy, and you can require a top-up or cut off service or whatever. Like literally each of those as we've seen them, we've like order of weeks gotten, you know, generally this isn't even like a full-fledged product. It's like an API, like you send us some stuff, we send you some stuff. And the adoption has just been like, okay, so the AI companies are all over this. I think what's interesting is every company is going to become an AI company and I don't think the industry at large is thinking about this yet or has really even reasoned that actually most of the fraud that's happening is not traditional credential or payment fraud. It's what we would historically have called first-party abuse, right? Like resale abuse or account sharing or multi-accounting or free trial. It's like first-party abuse. And I think it wasn't that first-party abuse didn't happen before. It's just at least in sort of SaaS stuff, first-party abuse didn't cost you anything. And so, a, it wasn't that useful to get a little bit of Salesforce for free for, you know, the examples we talked about wouldn't be relevant in most SaaS. And B, even if it was useful to figure out a way to skim off the top, and you could get a little bit of profit for it as a fraudster, it didn't actually cost the business that much because their marginal cost was zero. And so, as every business becomes an AI business, I think we've been in the context of our work on Radar really reasoning about our fraud prevention product as moving from transaction to full customer life cycle and moving from traditional fraud to end-to-end abuse. But I don't think the whole industry is there yet. And you know, you and I talked about much of the economic upside of AI, but I think that'll really only be realized if it can happen safely. So, for example, six, nine months ago, when I talked to some of these AI companies, they'd be like, "Oh, I know. I'm going to solve my free trial abuse problem by cutting off free trials." Like, I'm going to solve my free trial abuse problem by only having a sales-sold motion and only going after enterprises and not having PLG. And like, you know, I hear less of that today. Why? Not because the fraud's totally solved, but because everyone knows they need agents to also be their buyers. And if agents are going to be their buyers, they better have a self-serve motion. They better have a PLG motion. Like there's no way they want to siphon off that source of growth and sort of only double down on a highly secure sales-sold motion. But it's been interesting to see what's happened with token theft. I totally agree. The fraudsters are creative, but I think that's like a manifestation of how valuable the tokens are. And so I actually don't think that creativity is going anywhere.

</details>

### Radar 与人工智能欺诈防御

**Speaker A**: 那么 Radar 第一是实时的，第二大概也完全是由 AI 驱动的吧。这就像是用 AI 来对抗 AI 一样。

<details>
<summary>Original English</summary>

**Speaker A**: And Radar is one, real-time and two, presumably entirely AI-driven as well. It's like AI fighting AI kind of a thing.

</details>

**Speaker B**: 是的，它是实时的，而且是由 AI 驱动的。而且我认为在这里最重要的一点，或者说它区别于其他产品的地方，就是它横跨了整个 Stripe 的网络。所以说，基本上没有我们没见过的好的 AI 买家，也很少有我们没见过的坏的 AI 买家。所以这种结合……你知道，是的，有网络的规模，以及全球 GDP 的 2% 流经 Stripe，但真正说到 AI，关键在于网络的密度。我们简短地谈到了 Link，但为了让你有个概念，比如 Lovable 作为一个 AI 公司就是一个很好的例子，Lovable 58% 的交易量是通过 Link 流转的。在涉及 AI 时，Link 是一个极其密集的网络。所以你可以从那里推演开来，如果我们知道所有的好买家是谁，并且我们见过坏人在其他地方作恶，然后再把这一点和 AI 以及这些实时 API 结合起来，你就能得到相当好的防欺诈手段。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's real-time, it's AI-driven. And then I actually think most importantly here for its differentiation, it just looks across the Stripe network. So like there's basically no good AI buyer we haven't seen before and there are very few bad AI buyers we haven't seen before and so that combination... yes, the size of the network and this 2% of global GDP flowing through Stripe, but really when it comes to AI it's the density of the network. And we talked about Link briefly, but to give you a sense, like Lovable is a good example as an AI company, 58% of Lovable's volume flows through Link. Like Link is an extremely dense network when it comes to AI. And so you know you can sort of extrapolate away from there, but if we know who all the good buyers are and we've seen the bad guys be bad somewhere else, then combine that with yes, AI and these sort of real-time APIs, and you get pretty good fraud defenses.

</details>

### Tempo 与智能体商务 (Agentic Commerce)

**Speaker A**: 你之前提到了 Tempo。我们需要讨论一下 Tempo 吗？就是说 Tempo 与智能体商务（agentic commerce）的对话有多大相关性？

<details>
<summary>Original English</summary>

**Speaker A**: You mentioned Tempo at some point. Should we cover Tempo? Like how relevant is Tempo to the agentic commerce conversation?

</details>

**Speaker B**: 所以我认为我们与 Tempo 合作中有几个方面是非常有趣的。当你从商业角度思考智能体商务时，我们推出了机器支付协议 (Machine Payments Protocol, MPP)，我们是和 Tempo 一起构建的，它是一个开放标准。它的运作方式非常优雅，对吧？就像一个智能体请求访问一项服务，它可以是任何东西，一个 API 或者一个 MCP 服务器之类的，然后服务方返回一个支付请求，接着智能体进行支付。这其中不需要创建账户、不需要结账用户界面、不需要人工干预，也不像你和我传统上在互联网上互动的方式。这只是为智能体向企业购买服务提供的一种非常机器可读的、标准化的方式。而且我们确实看到 MPP 是企业让智能体作为买家时主要使用的机制。我们与 Tempo 的另一项合作，也是我超级看好的，更多是与欺诈有关。因为你知道，智能体正越来越多地成为 AI 产品的使用者，而智能体消耗 Token 的速度可能非常非常快。所以我们刚才稍微谈到了企业面临的这种两难境地：要么你可以切断自助服务，虽然非常安全但增长缓慢；要么你把它开放，包括对智能体开放，但那样你可能会让自己面临相当大的滥用风险和金钱损失。这两种选择都不太好。你真正想做的是，特别是当智能体是买家时，你想要跟踪这些正在被消耗的 Token。你刚才提到了基础设施。你想要在相当大的规模上实时地跟踪它们。同样重要的是，你不只是想在它们被消耗时跟踪它们，你还想在它们被消耗时收取费用。所以，我们称之为流式支付 (streaming payments)。这就是 Metronome 和 Tempo（Stripe 协助共同构建的针对支付优化的区块链）正在一起实现的功能。所以 Metronome 的工作就是实时跟踪使用情况，而 Tempo 的工作就是实现这种快速、低成本、高并发、即时结算的微支付。显然，它们是以稳定币进行结算的。因此，结合起来，AI 公司就可以在 Token 被消耗时向智能体买家收费，而不是被迫在关闭业务或被拖欠发票之间做出选择。所以，是的，我们非常看好 Tempo 以及稳定币在整个智能体经济和智能体商务中的应用。

<details>
<summary>Original English</summary>

**Speaker B**: So I think there's a couple components of our work with Tempo that I think are really interesting. So when you think about agentic commerce on the business side, we launched the Machine Payments Protocol or MPP, and we built it with Tempo, and it's an open standard. And the way it works is quite elegant, right? Like an agent requests access to a service, and it can be whatever, an API or an MCP server or whatever, and then the service responds with a payment request and then the agent pays, and there's no kind of account creation or checkout UI or human in the loop or sort of the way you and I would traditionally engage on the internet. It's just this very machine-readable standardized way for agents to buy from businesses. And MPP is really the primary mechanism that we're seeing businesses use for agents as buyer. The other collaboration with Tempo that I am super bullish on is more related to fraud. Because you know agents are increasingly becoming the users of AI products and agents can burn through tokens very very quickly. And so we were talking a little bit about this dichotomy that a business faces where either you can siphon off self-serve and be really safe but grow slowly, or open it up including to agents but then be putting yourself at risk for quite a bit of abuse and monetary losses. Neither of those is great. What you actually want to do, especially when the agents are the buyers, is you want to track the tokens as they're consumed. And you mentioned the infrastructure. You want to track them in real time at substantial scale. And then as importantly, you don't just want to track them as they're consumed. You actually want to collect payments as they're consumed. And so we call this streaming payments. And it's what Metronome and Tempo, which is this blockchain optimized for payments that Stripe helped co-build, are making possible together. And so just Metronome's job is like track the usage in real time, and Tempo's job is just enable this fast, low-cost, high-volume micropayments that settle instantly. Obviously they settle in stables. And so put together it's like AI companies can charge agent buyers as tokens are consumed instead of having to choose between closing off business or getting stiffed on the invoice. So we're very bullish about Tempo and stables in general in the agent economy at large and for the purposes of agent commerce.

</details>

### AI 初创公司的趋势

**Speaker A**: 超级有趣。好吧。那么，也许作为最后一个话题，你们有各种关于整体 AI 经济的有趣数据，但特别想问关于 AI 初创公司的。我想我们上次讨论过一些那方面的内容。在过去的一年里，你在 AI 初创公司方面看到了什么？趋势、事实以及……

<details>
<summary>Original English</summary>

**Speaker A**: Super interesting. All right. So, perhaps as the last topic, you guys have all sorts of interesting stats about the AI economy in general, but like in particular AI startups. I think we covered some of that last time. What have you seen in the last year in terms of AI startups? Trends and facts and...

</details>

<!-- chunk 9/10 -->

### AI 带来的初创企业大爆发

**Speaker A**: 增长率。你观察到了什么趋势？

<details>
<summary>Original English</summary>

**Speaker A**: growth rates. What have you seen?

</details>

**Speaker B**: 很有意思，去年我们交谈时，谈到了 AI 初创企业的增长，以及它们与传统初创企业看起来有多么不同。而我今天想说的是，AI 初创企业和非 AI 初创企业之间确实存在差异，但更让我震惊的是，AI 正在整体上重塑整个初创生态系统。所以，在“感觉编程”（vibe coding）和“感觉部署”（vibe deployment）等类似趋势的推动下，新企业的注册量——其实我认为新企业创立的整体故事被低估了。目前，基本上全球发达经济体的新企业注册量都在激增。比如荷兰增长了 40%，芬兰增长了 70%，法国增长了 80%。这种活力的激增，我们在美国确实能看到并真切感受到，但它其实正在各个发达经济体中发生。当我们通过 Stripe 的视角来观察时，新企业成立的步伐自我们去年交谈以来已经翻了一倍。虽然这些并不全是 AI 企业，但其中非常多的是因为 AI 才得以实现。而且，它们不仅是在起步，还在快速扩张。比如我们为创始人提供公司注册服务的产品 Atlas，从 2024 年这批 Atlas 初创企业来看——你知道现在才 6 月，所以它们还处于生命周期的早期阶段——但它们目前的营收增速已经是去年同期那一批企业的五倍了。五倍。

<details>
<summary>Original English</summary>

**Speaker B**: So, it's interesting when we when we talked last year, we talked about uh the growth of AI startups and uh how they looked different than traditional startups. And what I would say today is like, you know, there's definitely a delta between AI startups and non-AI startups. But what's more striking to me is how AI is just changing the startup ecosystem generally. Um and so you know in the vein of vibe coding and vibe deployment and all of that like uh new business registrations are um well so I think in general the the business formation story is underappreciated. So um new business registrations are up basically around the world at least for advanced economies they're up um like 40% in the Netherlands and 70% in Finland and 80% in France. Um and so there's this sort of like surge in dynamism that like yes we see and feel in here in the US but it's happening um across advanced economies. When we look at this with the stripe lens um the pace of new businesses launching has doubled since we talked last year. Um and not all those businesses are AI businesses but um many many of them were uh made possible because of because of AI. Um and they're not just getting started they're also scaling. So like Atlas is our um product for founders to incorporate and Atlas startups from the 2024 cohort and you know it's only June so it's early in their life cycle but they're tracking to like five times the revenue of last year's class at at these same um number of months. five times.

</details>

**Speaker B**: 五倍。其中一部分原因是企业数量增加了，但很大程度上是因为它们赚到第一桶金的速度变快了，进而扩张得更迅速。赚到第一桶金的时间缩短，很大程度上无疑归功于 AI。此外，扩张速度更快，一个很大的因素是它们走向全球化的方式。我不知道这其中有多少是 AI 的功劳，但在人们过去的旧有模式中，你得先做大，一旦做大了，你才有资格走向全球。而我们在过去一年中越来越多地看到，企业从一开始就直接走向全球——这倒不一定字面上意味着进入每个国家，而是你在发布的第一天，就已经在几十个国家开展业务了。这就是你做大的方式。你通过全球化来做大。既然我们谈论的是 AI，我可以拿 Emergent Labs 作为一个例子。这是一个供你构建和部署各类全栈应用的 AI 平台。他们 2024 年在美国成立，70% 的收入来自国际销售。他们已经在 16 个国家开展了实质性业务。也就是说，他们相当大一部分收入来自于众多其他国家。总之，我认为目前的情况是——没错，确实有很多 AI 公司，并且它已经从仅仅作为底层技术提供商，发展到各个垂直领域涌现出大量的套壳（wrapper）企业。但我认为，从自上而下的宏观视角来看，更有趣的是，过去你必须是一个开发者才能成为一个构建者，进而创办一家企业。现在，你只需要有一个想法，加上“感觉编程”、“感觉部署”，以及合理的经济基础设施就可以了。然后我们就看到了新企业的激增，而且它们的发展很难被阻挡，因为即使只有一名员工，它们也能及早开始商业变现，快速增长，并在多个市场中扩张。我认为，这几乎肯定得益于所有那些同样可以用 AI 完成的运营工作——这不太属于 Stripe 日常核心的业务范畴。我们在会计结算或者收入确认之类的事情上能帮上一些忙，但显而易见，很多客户支持和其他运营工作是由其他企业来完成的。但我觉得这是一个有趣的时代，现在有很多讨论在关注：AI 会不会导致少数公司占据极高的市场份额，从而缺乏竞争？我对 AI 经济持乐观态度的原因之一是，至少到目前为止，确实有一些大公司拥有与 AI 高度互补的资源，我们不需要挨个点名，大家都知道它们是谁，它们正在爆发式增长。但同时，市场上也涌现出大量的小公司，它们不仅被创立出来，而且正在触达客户并快速增长。所以我认为这对市场竞争和经济增长都是个好兆头。

<details>
<summary>Original English</summary>

**Speaker B**: Five times. And some of that is there's more of them, but a bunch of it is they are getting to their first dollar faster and then they are scaling up more quickly and getting to their first dollar faster. A lot of that is for sure AI and then scaling up more quickly um uh that you know there a big part of this is actually how they're going global. And I don't know how much of that is AI or not, but like sort of the old model people had was you get big and then once you're big, you deserve to go global. And what we're seeing with like increasingly over the last year is you literally go global from it doesn't lit necessarily literally mean every country, but it's like you're in dozens of countries on day one like your launch day. And that is how you get big. You get big by being global. And so uh I guess we're talking about AI. So I could use like emergent labs as an example. Um right AI platform for um you know you build and deploy these kind of full stack apps. So they were founded in 2024 in the US. Um 70% of their revenue um comes from international sales. Uh and they do material business in um 16 countries. Like a substantial share of their revenue comes from many many countries. Anyway, I I think there's this sort of like yes, there's AI companies and, you know, it's moved from, you know, just being sort of the underlying providers to like a lot of rapper businesses, proliferation of rapper businesses across every single vertical. But I think what's kind of more interesting from the tops down macro perspective is just you used to have to be a developer to be a builder and therefore build a business. Now you kind of have to have an idea plus vibe coding plus vibe deployment plus reasonable economic infrastructure. And then you know we see this proliferation of um new businesses and they um aren't uh uh their their development is not easily arrested right like they even with one employee they uh you know start monetizing early they um grow quickly they uh expand across a bunch of markets and um I think that's almost certainly helped by all of the operational work that can also be done with AI which is less in sort of the day-to-day core wheelhouse of Stripe. We help with some of that on the accounting or revick or whatever, but um you know much of the customer support and other operations are are obviously done by other businesses. Um but I think it's an interesting time and there's a lot of discussion of like is AI going to lead to a small number of firms um with heavy market share and not a lot of competition. And I think one of the reasons I'm bullish on the AI economy is at least so far for sure there are big guys who have things that are highly complimentary to AI. We don't need to go through that list. Everyone knows them. Um that are exploding but there's also an explosion of little guys coming in the market and uh not just being created but like reaching customers and growing quickly. And so I think that bodess well for for competition and for and for economic growth.

</details>

### AI 支出与投资回报率的校准

**Speaker A**: 这一切显然非常令人激动。但既然我们之前提到了 Token 成本和按使用量计费等问题，你是否会担心其中有一部分原因是：买方和使用方都有点得意忘形了，并没有完全意识到使用 AI 所代表的实际美元开销，从而可能会对这种高速增长产生某种反弹？我的意思是，我们都看过那些报道，说有些公司因为对员工的行为缺乏把控，而在 Token 支出上彻底失控（gone bananas）。

<details>
<summary>Original English</summary>

**Speaker A**: All of this is obviously extremely exciting, but since we talked about um token costs and uh you know usage base and all the things, do you worry that like a part of this is a little bit people uh on the on the on the buying side and on the usage side got a little carried away quite didn't quite realize the dollar amount that uh using AI represented and that there might be some kind of backlash against that hyperrowth. So, I mean, we've all read the stories of companies who have accidentally gone bananas on token spend because they had like no control over what their employees were doing.

</details>

**Speaker B**: 我认为那些真正“彻底失控”的公司，总体上都是些财大气粗的企业。但这并不是说，如果这种开销继续下去，它不会成为经济中的一个问题。不过，也有那些管理良好、运作高效的聪明企业，它们是能够承受一两个月的决策失误和成本失控的。而且，大体而言，虽然我并不完全清楚这些公司的具体情况，但如果我们谈论的是，假设它们有 2%、3%、4% 的人力成本变成了 Token 支出，并且其中 30% 或 40% 是低效的，我认为它们能够相当快地重新回到效率前沿，这并不是什么关乎生死存亡的事情。至于那些小公司，我其实不认为会发生这种情况。你知道，它们中的很多都在进行固定费用的采购，而且它们还在使用小型订阅计划之类的。所以，传闻是存在的。顺便澄清一下，我认为关于使用 AI 的效率前沿，我们还有很多需要学习的地方。这其中包含模型路由，以及你为特定任务选择什么模型；也包括可观测性，我认为很多公司都发现自己在这方面落后了；还有就是规范、控制和安全护栏。你知道，我们当然都希望 LLM（大型语言模型）的使用能带来高投资回报率（ROI）。但我们也希望员工能在他们产生真正巨额的成本时心里有数，并且希望他们能告诉我们，他们是否预期这些成本的 ROI 能够实现。所以，是的，我认为这里会有一点点重新校准的过程，但我认为并没有发生任何关乎存亡的事情，足以抵消这其中长期的上升空间。

<details>
<summary>Original English</summary>

**Speaker B**: I think the companies who have truly gone bananas are by and large the companies with pretty deep pockets, which isn't to say that it's not like going to be a problem in the economy if that spending continues. But there's smart companies that are well-run, well-managed. They can handle a month or two of poor decisions and runaway costs. And um you know by and large I I don't exactly know what we're talking about at these companies but if we're talking about like I don't know 2% 3% 4% of their headcount costs are going into tokens and uh 30% of that or 40% of that is inefficient I think they can like pretty quickly get back to an an efficient frontier and and it's not really anything existential. Um for the little guys actually don't don't think that's happening. um you know many of them are sort of making fixed fee fixed fee purchases and they're still on small plans and and whatever. So I mean the stories are out there and by the way just to be clear like I think we have a lot to learn about the efficient frontier of AI use and there's a component there around like model routing and what models you select for the job and there's a component around just like observability which I think many companies have find found themselves to be behind on and then there's just like um like norms and controls and guard rails and you know I think we all want high ROI uh usage of LLMs Um, but we also want employees to know when they're, you know, racketing up really substantive costs and we want them to be able to tell us uh whether they anticipate the ROI of those costs is going to be there. So, yeah, I think there'll be like a little bit of uh uh recalibration, but I don't think anything existential has happened that's going to enol um the the sort of long run upside here.

</details>

### 迈向智能体经济（Agentic Commerce）

**Speaker A**: 好的。那么最后一个问题，当我们一年后再次交谈时，你认为我们在智能体商业方面会发展到什么地步，也许会达到 L1 到 L5 的某个阶段？我不是非要你给出一个精确的预测，但现实地来看，你觉得未来 12 个月在这个方向上会发生什么？

<details>
<summary>Original English</summary>

**Speaker A**: All right. So as a last question when we talk again in in a year from now where do you think we are uh in terms of agentic commerce maybe using uh you know L1 to L5 and I I won't hold you to the prediction but like directionally what do you think realistically is going to happen in the next 12 months?

</details>

**Speaker B**: 我认为未来 12 个月最有趣的事情是——我的意思是，我认为我们会向上迈进，我不知道会不会达到 L4 或 L5，但我认为更有趣的事情其实是，我们之前谈论作为经济参与者的智能体时，大多是在买方（buying）的语境下。但我认为我们将开始看到——我不是说这会普及到每个角落——但我认为我们会开始看到，智能体成为多面的经济参与者。它们既在买入，也在卖出；它们在配置基础设施，也在运营企业。而且它们在端到端地做这些事情。重申一下，我不知道会有多少这样的智能体会存在，也不知道它们将如何运作，是会相互协作，还是会处于这些奇怪的利基孤岛中。但我认为，这一切将继续催生对更多专用基础设施的需求，包括金融基础设施，而不仅仅是旧有那种以人类为中心的商业堆栈。所以，这就是目前的状况。

<details>
<summary>Original English</summary>

**Speaker B**: I think the most interesting thing in the next 12 months is I mean I think we I think we'll move up and I don't know if it's going to be to four or to five but I I think the more interesting thing is actually that like we talked about agents as economic actors mostly in the context of buying but I think we'll start to see and I'm not saying this will be proliferated everywhere but I think we'll start to see agents that are like multiaceted economic actors. They're buying and they're selling and they're provisioning infrastructure and they're running businesses. um and they're like doing the thing end to end. And again, I don't know how many of these there will be or how they'll operate or whether it'll be like with each other or like in these like weird niche silos. Um but I think all of that's just going to continue to demand more purpose-built infrastructure including financial infrastructure versus just the sort of old um human centric commerce stack. Um, and so that that's that's

</details>

<!-- chunk 10/10 -->

### 代理作为微型企业的未来

**Emily**: 所以情况大概是，当我们依靠直觉部署，依靠直觉写代码，然后依靠直觉部署时，会是什么样子？然后我的内容、我提供的服务默认就是公开的。实际上我们刚刚悄然在 Stripe Directory 上推出了公开预览版，这只是一种让代理发现提供商的非常简单的方式，然后通过 Stripe Projects，它们可以直接整合这些提供商。但是，好吧，然后一个代理也发现了所有东西，整合它、购买它，然后，你知道的，用它配置、整合和购买的东西组合创造出一项服务，并开始销售某样东西。无论如何，这种将代理视为一家微型企业的想法，我认为可能是 12 个月后我们会看到的最有趣的事情。话说回来，我不认为一般的企业会是……或者别提什么“独立创业者”（solopreneur）了，那会叫什么？一个“独立代理”？我不认为那会是我们生活的世界。但我认为 12 个月后，我们完全可以看到一些这样的例子，它们为整个端到端的事情铺平了道路。而且，你知道的，新技术的出现总是伴随着这样的过程，对吧？你拿你现有的流程、市场或任何你拥有的东西，然后弄清楚新技术如何让它效率提高 5% 或 10%。它能让我免去输入信用卡号的麻烦，对吧？但真正有趣的地方在于，我们开始重新构想整个系统的运作方式。这不是 Emily 授权一个代理代表她购买东西。而是 Emily 有一个代理，它的任务是运营一家企业，这包括买一些东西、卖一些东西，赚取一些利润，那将是我希望在 12 个月后谈论的世界。

<details>
<summary>Original English</summary>

**Emily**: Kind of where like what is what does it look like when okay I'm vibe deploying I'm I'm vibe coding and I'm vibe deploying and then uh my content is my offerings are default exposed and actually we just we just quietly uh went to to public preview on uh on Stripe directory which is just a really easy way for agents to um discover providers and then through stripe projects they can integrate them directly but like okay and then an agent's like also discovering everything and integrating it and buying it and then you know creating a service out of the combination of things it has provisioned and integrated and bought and is starting to sell a thing anyway like this this idea of like an agent as a micro firm um I think would probably be the most interesting uh thing to see 12 months from now And again, I don't think the median uh firm is going to be uh or forget a soloreneur, a what would it be? A solo agent uh uh I don't think that's I don't think that's a world we'll live in. But I I think 12 months from now we could totally see some examples of that that sort of pave the path for hm like the the whole thing end to end. And you know this always happens with a new technology, right? You take like your current processes or market or whatever you have and you figure out how does the new technology make that 5% more efficient or 10% more efficient. It keeps me from having to type in my credit card number, right? But like where it actually gets interesting is where um we start to reimag like how the system works. Um and it's not Emily permissioning an agent to buy on her behalf. It's Emily has an agent who's tasked with running a business and that includes buying some things and selling some things and making some profits and um that'll that'll be the world that I that I would like to be talking about 12 months from now.

</details>

**Matt Turk**: 好吧，Emily，这又是一次精彩的对话。非常感谢你。我真的很享受这次交流。

<details>
<summary>Original English</summary>

**Matt Turk**: Well, Emily, it's been another amazing conversation. Thank you so much. Really enjoyed it.

</details>

**Emily**: 谢谢。

<details>
<summary>Original English</summary>

**Emily**: Thank you.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。感谢收听这一期的 Mad 播客。如果你喜欢这期节目，如果你还没有订阅，我们非常感激你能考虑订阅，或者在你观看或收听这期节目的任何平台上留下好评或评论。这对我们做播客和邀请优秀的嘉宾真的很有帮助。谢谢，我们下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks, and see you at the next episode.

</details>