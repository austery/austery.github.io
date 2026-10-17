---
author: Bloomberg Podcasts
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8wGO8SyEDTc
speaker: Bloomberg Podcasts
tags:
  - fuel-hedging
  - options-trading
  - crack-spread
  - risk-management
  - airline-industry
title: 航空公司的燃油对冲真相：如何通过期权与收益管理将成本转嫁并套利
summary: 彭博 Odd Lots 播客深度对话前卡塔尔航空集团财务官 David King，解构航空业燃油套期保值的内在逻辑。航司并非单纯的燃油消费者，而是拥有天然多头定价权的“燃油生产商”。在高油价环境下，航司通过燃油附加费将成本转嫁给旅客，甚至反向运用跨式期权策略实现套期保值与盈利。
insight: ''
draft: true
series: ''
category: investment-assets
area: finance-wealth
project: []
people: []
companies_orgs:
  - Qatar Airways
products_models: []
media_books: []
status: evergreen
---
### 航司对冲的神秘面纱

**崔西·阿洛威**: 大家好，**Odd Lots** 的听众朋友们！我们的巡回活动正在进行中，下一站是芝加哥。我和乔计划于 10 月 15 日在**芝加哥城市酒庄**（Chicago City Winery）进行一场 Odd Lots 现场节目录制。门票现已在 bloomberg.com/oddlots 开售。特别鸣谢**巴克莱银行**（Barclays）对本次现场录制的赞助。10 月 15 日，芝加哥城市酒庄见！请抓紧购票。这里是彭博音频工作室的 Podcast Radio News。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Hello, Odd Lots listeners! The Odd Lots tour is continuing, and the next destination is Chicago. you're right. Joe and I are planning to do a live recording of Odd Lots at Chicago City Winery on October 15th. Tickets are available for purchase now at bloomberg.com/odd lots. We would like to extend special thanks to Barclays for sponsoring the Odd Lots live recording. See you at Chicago City Winery on October 15th! Purchase your tickets right now. Bloomberg Audio Studios Podcast Radio News Hello, welcome to another episode of the Odd Lots podcast.

</details>

**乔·威森塔尔**: 我是**崔西·阿洛威**（Tracy Alloway），我是**乔·威森塔尔**（Joe Weisenthal）。乔，有一个话题我们一直想聊很久了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I am Tracy Alloway, and I am Joe Weisenthal. Joe, there is a topic we have wanted to cover for a long time.

</details>

**崔西·阿洛威**: 没错。虽然表面上看似乎挺简单，但实际上我很难找到完全契合这个主题的嘉宾。因为这是一个关于航空公司特定策略的故事。在我担任交通运输记者的几年里，我发现航空公司有很多非常奇特的特点：极其保密，很不情愿分享细节。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yes, that is correct. It might look simple, but actually, I had a really hard time finding a guest who was the perfect fit for the topic. This is because it is a story about a specific airline strategy related to airlines. When I worked as a transportation reporter for a few years, I realized that airlines have many peculiar aspects. He has a lot of secretive sides and is reluctant to share details.

</details>

**乔·威森塔尔**: 实际上我以前并不了解这个行业的惯例，不知道航司倾向于这样保密。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Actually, I was unaware of this industry practice. I didn't know that airlines tend to keep secrets in this way.

</details>

**崔西·阿洛威**: 关于航空业，一直有两件事让我充满好奇，今天我想聊其中之一：就是航司关于**燃油对冲**（fuel hedging）的内部细节及其运作方式。第二件事是，我一直想看看包含航司实际获得折扣的飞机订购合同。每当**维珍大西洋航空**（Virgin Atlantic）宣布向**波音**（Boeing）或**空客**（Airbus）订购一定数量的飞机时，公布的价格总是官方目录标价，外人根本无从知晓航司实际支付了多少。虽然在做交通记者的日子里我一次也没能看到那种底价合同，但至少今天，我们终于能解开燃油对冲的谜团了。

<details>
<summary>Original English</summary>

**Tracy Alloway**: There are two things I have always been curious about regarding the aviation industry, and today I would like to talk about one of them. It is the internal details regarding fuel hedging and its operation methods. Second, I wanted to see the aircraft order contract that included the discounts the airlines actually receive. Whenever Virgin Atlantic announces that it is ordering a specific quantity of aircraft from Boeing or Airbus, the prices are always listed at the regular price. So, you can't really know how much airlines are actually paying. So I've always wanted to see that, but I never saw it even once while working in the transportation industry. However, at least for now, I have been able to resolve my curiosity about fuel hedging.

</details>

### 燃油对冲与成本转嫁机制

**乔·威森塔尔**: 我非常期待这一期，也正因为航空公司的燃油对冲话题。每当油价暴涨或大幅震荡时，大家总会扯到航司身上，我们都有过类似的经历吧？大家总会说：“啊，这家航空公司做燃油对冲了吗？”对话通常到这里就戛然而止了——要么认为“做了对冲就万事大吉”，要么觉得“没做对冲股价肯定要跌”。每个人都在谈燃油对冲，但往往没人真正清楚它到底意味着什么。

而且我发现很有趣的一点是，航空公司竟然有自己的**交易员**（traders）。一提到交易员，人们脑海中浮现的往往是交易所或华尔街，而大企业内部活跃开展的资本交易活动却鲜受关注。在航司的成本结构中，燃油是仅次于**人力成本**（labor costs）的第二大支出项，同时也是波动性最剧烈的一项。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: The reason I am really looking forward to this episode is because of the story about airline fuel hedging. As you know, whenever oil prices rise significantly or skyrocket, stories about airlines come up. We've all had that experience, haven't we? Right? This is exactly what interests me. You know, things like the ones we always talk about. "Ah, did the airline hedge its fuel?" And then the conversation ends right there. Ah, it should be fine since I hedged. Or, "Since I didn't hedge, the stock price will probably fall." Something like this. We all talk about fuel hedging, but often we don't really know what it actually means. And I also find it interesting that there are traders at airlines. When you hear the word "trader," you usually think of places like exchanges, right? However, capital transaction activities actively carried out by companies are receiving almost no attention. To add one more point regarding fuel and airline costs, fuel is the second largest cost item for airlines, after labor costs. That's obvious. However, fuel is also the most volatile cost item.

</details>

**崔西·阿洛威**: 听到“对冲”这个词，人们通常认为航司是担心油价（尤其是航空煤油价格）暴涨，因此试图将成本锁定在某个固定水平，以避免承受类似近期航油暴涨的冲击。但在现实中，航司在油价上涨时还拥有另一种手段：直接**提高机票票价**或**增加燃油附加费**（fuel surcharges）。

换句话说，可能会出现这样一种情况：油价暴涨，而航司既能享受此前锁定的低油价，又能向乘客征收额外的燃油附加费。在通胀蔓延、航油短缺新闻满天飞的背景下，即便票价里被加上了高额附加费，消费者往往也不会有太多抱怨——大家虽然觉得机票贵，但还是照买不误。

<details>
<summary>Original English</summary>

**Tracy Alloway**: When people hear the term hedging, they usually think that airlines are worried about rising oil prices, especially jet fuel prices. you're right. So, airlines try to fix prices at a specific level to avoid getting caught up in sudden price fluctuations, such as the recent surge in jet fuel prices. However, at the same time, airlines use another means of raising airfares or increasing fuel surcharges when oil prices rise. In other words, a situation may arise where a fixed price falls below the fixed price due to a surge in oil prices, and an additional fuel surcharge may be imposed. This is because, just as we have experienced inflation, we could suffer a major blow if an oil shortage occurs. With all sorts of news pouring in these days, including the aviation fuel shortage, customers probably won't complain much even if a large fuel surcharge is added to their airfare. Airfare is really expensive these days.

</details>

**乔·威森塔尔**: 确实如此。机票现在非常贵，即便加了巨额燃油附加费，大家也见怪不怪。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yes, that is correct.

</details>

**崔西·阿洛威**: 实际上，如果航空公司在锁定了低采购价的同时又全额加收燃油附加费，这在某种程度上相当于在燃油市场建立了一个**双重多头头寸**（double-long position）。

<details>
<summary>Original English</summary>

**Tracy Alloway**: If the fuel surcharge was also fully added, wouldn't it be effectively a double-long position?

</details>

**乔·威森塔尔**: 哈哈，你刚才给我的提示就像一记当头棒喝。这正是我一直想搞懂的问题：既然航空公司拥有如此强大的成本转嫁能力，为什么还要进行金融对冲？当你在两头同时获利时，对冲的真实风险暴露到底是什么？这正引出了我们今天的嘉宾。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: What you just said felt like a hit to the back of the head. I'm laughing because that 's something I've always wanted to know. I've always wondered about this, and how it was actually dealt with, but I just couldn't figure it out. That's why I'm really looking forward to this episode. Today, we brought in the best person to explain all this in a very interesting way.

</details>

### 嘉宾登场：从债券交易到航司财务舵手

**崔西·阿洛威**: 今天的嘉宾曾在一流国际航空公司主导实施了极具独创性的燃油对冲策略，他对石油与航油市场的理解非常深刻。让我们欢迎**戴维·金**（David King），前**卡塔尔航空**（Qatar Airways）集团财务官、石油市场资深专家。戴维，非常感谢你做客 Odd Lots！

<details>
<summary>Original English</summary>

**Tracy Alloway**: I will speak with Mr. David King. He is a former Group Finance Officer at Qatar Airways and an expert across the oil market. David, thank you so much for appearing on All Sots.

</details>

**戴维·金**: 很高兴与你们交流！感谢邀请。

<details>
<summary>Original English</summary>

**David King**: I am glad to meet you. I am so glad to finally meet you.

</details>

**崔西·阿洛威**: 感谢你在新加坡的深夜坚持连线。能否先简要介绍一下你的职业背景？为什么你既是卡塔尔航空的前财务高管，又是公认的石油市场专家？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Thank you for staying with us until late in Singapore. Could you briefly introduce yourself and explain why I just referred to you as both the former Group Finance Officer at Qatar Airways and an oil market expert?

</details>

**戴维·金**: 这说来话长了。我早年在多伦多和纽约做利率交易，曾在列克星敦大道 425 号的一家加拿大银行工作，离你们现在的位置不远。后来我回到新加坡加入**国民西敏寺银行**（NatWest），被派驻伦敦销售政府债券。之后我在一家日本商社担任债券交易员，但在 1998 年亚洲金融危机中失业了。

于是我转型进入能源行业，在**安然**（Enron）做天气衍生品交易，负责亚洲业务。在安然破产前两个月，我跳槽到了**胜科工业**（SembCorp），这是一家综合性工业巨头，拥有电厂、燃气管网和离岸海事工程。我先后在那里管理天然气交易和新加坡的大型公用事业电厂。随后我转战**新加坡大士能源**（Tuas Power），最后通过猎头推荐，我前往多哈，加入了正处于迅猛扩张期的卡塔尔航空。

<details>
<summary>Original English</summary>

**David King**: It's a long story. I will briefly tell you about my experience trading in Toronto. I did interest rate trading in New York. I worked at a Canadian bank at 425 Lexington Avenue, which is not far from your house. yes. I returned to Singapore and joined National Westminster Bank (NatWest), and was dispatched to London to sell government bonds. After that, I worked as a bond trader at a Japanese trading company, but I lost my job during the Asian financial crisis in 1998. So I switched to being an energy trader. The place I went to then was Enron. I started doing weather derivative trading, looking after Asian products. I was lucky enough to leave Enron two months before it went bankrupt. And I worked at SembCorp. Sembcorp is an industrial conglomerate that does a variety of businesses. I was in charge of gas trading there, and then I went to an offshore marine construction company and then an energy company, managing large utility power plants in Singapore. After working at Tuas Power in Singapore, I worked for Qatar Airways through a recruitment agency. The person who hired me was CFO Daniel Ho. He is someone who knows a lot about human resources. After that, I was in charge of fuel hedging at Qatar Airways for about four years.

</details>

### 裂解价差与现货市场的流动性现实

**乔·威森塔尔**: 戴维，你此前提到过一个关键细节：因为航空煤油本身的金融衍生品市场规模相对较小、流动性较差，许多航空公司在做对冲时，实际上是通过交易**布伦特原油**（Brent Crude）或**西德克萨斯轻质原油**（WTI）来进行间接对冲。这是否意味着航司暴露在巨大的**裂解价差**（crack spread，即航油与原油的价差）风险之下？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That because the jet fuel trading market itself is so small, fuel hedging is mostly done through Brent crude trading. In that case, does this mean that airlines could be significantly affected due to the large fluctuations in jet fuel and Brent crude oil prices? As you know, that difference can change by several dollars in just a few days. So, wouldn't airlines be deeply concerned about that gap?

</details>

**戴维·金**: 没错。很多人不了解，航煤与原油的价差波动可以极其剧烈。比如 2022 年初俄乌冲突爆发前，布伦特原油上涨了大约 50%，但新加坡航煤价格却暴涨超过 100%，直接翻倍！这意味着，即便一家航司对布伦特原油做了 100% 的完美对冲，其承担的实际航煤采购成本仍然可能因为裂解价差失控而承受巨额亏损。

航煤衍生品缺乏流动性，做市商报出的买卖价差非常宽。如果你直接在航煤市场上做大规模互换（Swap），交易成本会高得惊人。因此，业内普遍用布伦特或**伦敦柴油**（Gasoil / Low Sulfur Gasoil）作为代理标的。但这种基差风险（Basis Risk）在极端行情下足以致命。

<details>
<summary>Original English</summary>

**David King**: If we go back to early February, that is, before the war started in March, Brent crude had risen by 50%, and Singapore jet fuel had risen by more than 100%, that is, more than doubled. In my opinion, even airlines that had well hedged against Brent crude prices would have had a very large crack spread gap. Jet fuel doesn't have a large derivatives market of its own. Banks and brokers charge huge spreads. So airlines use Brent or Gasoil as a proxy, but the crack spread risk remains open.

</details>

### 卡塔尔航空的 3.6 亿美元浮亏风暴

**崔西·阿洛威**: 戴维，你能讲讲你刚加入卡塔尔航空时面临的具体挑战吗？当时管理层面临着怎样的燃油对冲困境？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Could you briefly explain what problem you were trying to solve for your employer at the time?

</details>

**戴维·金**: 让我分享一段真实的经历。我刚加入卡塔尔航空担任集团财务经理时，赶上了 2008 年金融危机之后的油价大崩盘。当时航司传统的对冲组合遭受了毁灭性打击——浮亏高达 **2.8 亿美元**，后来甚至扩大到了 **3.6 亿美元**！

首席执行官阿克巴尔·阿尔·贝克尔（Akbar Al Baker）把首席财务官丹尼尔·霍（Daniel Ho）和我叫进办公室，非常严厉地质问：“丹，为什么我们在燃油上亏了整整 3.6 亿美元？！”这就是典型的“烫手山芋”（hospital pass）。

在传统的航司财务认知里，财务人员会向管理层解释：“总裁先生，当油价上涨时，我们的互换合约会赚钱，从而抵消现货燃油采购的高成本；但当油价大跌时，虽然对冲合约亏损，但我们在现货市场买到了便宜的燃油，整体成本是平的。”

但 CEO 直接打断了这种理论说辞：“戴维，你是集团财务官，我不管你们有什么金融理论，我的财报上不能看到赤字！你必须保证今后绝对不能再出现这种对冲巨亏！”

<details>
<summary>Original English</summary>

**David King**: Let me tell you a short anecdote. Very simply. The losses on our hedge portfolio amounted to $280 million, and eventually ballooned to $360 million. The CEO called CFO Daniel Ho and me into the office. The CEO asked CFO Daniel Ho, "Dan, why are we losing as much as $360 million?" I was a group finance manager who had just joined the company at the time, and I remember what I was in charge of back then. Do you know what a "hospital pass" is? When you pass the ball, everyone runs towards it, but it gets kicked away in a situation where no one can receive it. People usually say, "You know, Mr. President, when oil prices rise, you make money through swap transactions, right? You lose money in physical trading because you have to buy at a higher price. But since it's a variable price, the physical trading makes money when prices drop, so it's a wash." But it was a very difficult situation for the CEO. He said, 'David, you are the Group's Chief Financial Officer. I do not want to see deficits on the financial statements anymore. Do you understand?' He said. So, what I realized after that meeting was that I had to do something that would eliminate downside risk and prevent hedge losses.

</details>

**乔·威森塔尔**: 很多企业高管在做对冲时都会产生这种心理矛盾：当油价上涨时，他们觉得财务部门做了对冲是理所应当的；但当油价从 140 美元腰斩到 40 美元时，看到账面上几亿美元的衍生品实际现金流亏损，任何 CEO 都会抓狂。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That is the classic dilemma of corporate hedging. When prices go up, everyone takes it for granted. But when oil plunges from $140 down to $40, writing multi-hundred-million dollar checks to Wall Street banks drives CEOs insane.

</details>

**戴维·金**: 完全正确！更糟糕的是，对于当时的卡塔尔航空来说，燃油成本占整个运营总支出的 **44%**！欧美航司的人力成本通常是第一大项，但卡塔尔航空地处多哈，大量机组和地勤人员来自东欧和亚洲，人力成本相对较低，这使得燃油价格波动对公司利润表的影响被极度放大。

在面临“绝不允许发生对冲亏损”的严苛行政指令下，我回到办公室与副手坐下来深入复盘：如果传统基于消费者的对冲思路（单纯买入互换或看涨期权）在油价暴跌时会产生巨大亏损，我们该如何彻底重构战略？

<details>
<summary>Original English</summary>

**David King**: Fuel accounted for 44% of our total operating costs at Qatar Airways. It was enormous. In Europe or the US, labor is 35-40% and fuel is 25%. For us, labor was lower because living costs and crew payroll from Eastern Europe and Asia were lower, making fuel 44%. So when oil moves, the company's survival is on the line. I sat down with my deputy finance manager to re-examine the whole structure from scratch.

</details>

### 航司本质是“燃油生产商”：重构头寸暴露

**戴维·金**: 我过去有大宗商品交易和炼油厂管理的背景。炼油厂既是原油的消费者，也是成品油的生产商。我问自己：航空公司到底在生产什么？

航空公司不是在卖机器，我们是在生产并销售“座位里程”（Seat-kilometer），即把乘客从 A 点运送到 B 点的位移服务。当你拆解一张机票的定价时，你会发现什么？机票价格通常由基础票价、机场税费以及巨额的**燃油附加费**构成。

在航空业，尤其是长途国际航线中，燃油附加费会随着油价上涨而迅速上调。当油价高企时，全行业的机票价格都在上涨，消费者不仅接受了高票价，还支付了高额附加费。这意味着：在收益管理端（Revenue Management），航空公司实际上天然持有一个**石油多头头寸**（Long Oil Position）！

<details>
<summary>Original English</summary>

**David King**: Having experience in oil trading and refineries, I looked at a refinery: it consumes crude and produces refined product. So I said, "As an airline, what do we produce?" We produce a chair moving from point A to point B. And what is inside that chair? A ticket. And what is inside the ticket? A base fare and a fuel surcharge. When oil prices surge, airlines raise fares and increase fuel surcharges. Passengers accept it because everyone sees high oil prices in the news. Therefore, on the ticket and revenue side, the airline is naturally LONG oil!

</details>

**崔西·阿洛威**: 这真是一个颠覆性的视角！传统金融教材总是把航司归类为“燃油消费者”，因此认为航司天然是“空头燃油”，需要买入看涨期权或互换来锁定价格。但你的洞察是：航司通过票价和附加费的转嫁机制，在业务前端其实已经变成了一个**原油多头**！

<details>
<summary>Original English</summary>

**Tracy Alloway**: That is a fascinating perspective! Finance textbooks always describe airlines as fuel consumers who are naturally short oil and need to hedge against rising prices. But you realized that through surcharges and pricing power, the airline is structurally long oil on the revenue side!

</details>

**戴维·金**: 没错！一张机票包含了两面：
1. **支出端（物理消耗）**：飞机飞行需要消耗航煤，因此航司在物理层面拥有**燃油空头**（Short Fuel）。
2. **收入端（商业定价）**：航司通过动态燃油附加费和票价涨幅向乘客全额甚至超额回收油价成本，因此在收入层面拥有**燃油多头**（Long Fuel）。

当油价上涨时，收入端的超额利润自动弥补了支出端的燃油成本上升；而最危险的反而是油价暴跌的时候——全球经济衰退导致旅客出行需求萎缩，航司被迫打折降价，燃油附加费清零，此时如果你手里还拿着高价买入的传统金融对冲合约（互换或看涨期权组合），你就会遭遇现货收入崩塌与衍生品巨额浮亏的双重绞杀！

所以，航司真正需要防范的不是油价上涨，而是**油价崩盘及经济衰退周期**。从风险管理的本质来看，航司的对冲策略不应该像消费者那样操作，而必须像**石油生产商**（Oil Producer）那样去对冲！

<details>
<summary>Original English</summary>

**David King**: Exactly. Now, a fuel long position is created on one side of the ticket, and a fuel short position is created on the other side because you need jet fuel to fly the airplane. So we had a short position on one side and a long position on the other. What should we think about? We need to consider a producer hedging strategy! When oil crashes, air travel demand drops, fuel surcharges disappear, and ticket prices collapse. If you are sitting on expensive long swaps, you bleed hundreds of millions of dollars. The airline needed protection against falling prices, not rising prices.

</details>

### 实战跨式期权：构建零成本安全护城河

**乔·威森塔尔**: 那么，你们具体是如何构建这个“生产者对冲策略”的？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So how did you actually execute this producer hedging strategy in practice?

</details>

**戴维·金**: 我们采用了基于**跨式期权组合**（Strangle / Collar 结构变体）的创新架构：

由于航空公司已经在机票收入中天然获得了油价上涨的保护，我们不再单纯支付高昂权利金去买普通的看涨期权。相反，我们将对冲组合设计为在油价平稳或温和上涨时产生正现金流，并在油价剧烈下跌时提供坚实的底线支撑。

我们通过卖出虚值看涨期权（Sell Out-of-the-Money Calls）收取权利金，同时买入虚值看跌期权（Buy Out-of-the-Money Puts）来锁定油价下行时的保底价值。由于我们不需要为传统对冲支付大笔保险费，这套策略在绝大多数年份都能稳定运行，且在账面上消除了发生灾难性对冲赤字的可能。

当油价暴跌时，我们的看跌期权头寸开始盈利，直接抵消了客运收益率（Yield）下滑的冲击；而当油价暴涨时，虽然卖出的看涨期权端会出现衍生品亏损，但我们在现货市场征收的高额燃油附加费和客票提价所带来的运营现金流，远远覆盖了期权端的支出！

更重要的是，我们在内部向管理层明确了这一逻辑：每一笔衍生品交易都与收益管理团队（Revenue Management）的定价算法严格联动，让整个航司的资产负债表呈现出平滑的抗周期韧性。

<details>
<summary>Original English</summary>

**David King**: This is one of the reasons why we used the strangle strategy. We sold calls and bought puts. Why? Because revenue management handles the upside via surcharges. If oil stays within a certain range or rises gradually, our options structure generates premium or stays flat. If oil crashes, our puts protect us against the collapse in passenger revenue and disappearing surcharges. If oil spikes aggressively, the liability on our short calls is easily offset by the massive influx of cash from high fuel surcharges and elevated ticket pricing. We aligned derivatives trading directly with revenue management.

</details>

### 中东航司的燃油供应链与地缘补给博弈

**崔西·阿洛威**: 很多人有一个刻板印象：中东国家拥有世界上最丰富的石油储备，中东航司比如卡塔尔航空、阿联酋航空（Emirates）和阿提哈德航空（Etihad Airways），是不是能直接从本国政府或国有石油公司获得极低成本的廉价航空煤油补贴？

<details>
<summary>Original English</summary>

**Tracy Alloway**: People often assume that Gulf carriers like Qatar Airways, Emirates, and Etihad have an unfair advantage because they sit on vast oil reserves. Do Middle Eastern governments simply subsidize jet fuel for their flag carriers?

</details>

**戴维·金**: 这绝对是一个巨大的误解！中东国家虽然富含原油，但历史上它们的**炼油产能**（refining capacity）并不充裕。原油从地下开采出来并不能直接倒进飞机油箱，必须经过现代炼油厂的加氢裂化等复杂工序精炼成符合严格航空标准的航煤。

在很长一段时间里，卡塔尔等海湾国家甚至需要从国外进口航空煤油！当地的国有石油巨头如**卡塔尔石油公司**（Qatar Petroleum，现卡塔尔能源）是完全按照国际市场商业原则运作的，它们对本国航司不仅不打折，结算价格往往比新加坡现货基准还要贵。定价权完全掌握在石油公司手中，航司没有任何议价优势。

正因如此，航司在运营端必须想尽一切办法在物理层面进行燃油套利。

<details>
<summary>Original English</summary>

**David King**: That is completely false. Having crude oil in the ground is different from having jet fuel. Jet fuel requires sophisticated refining infrastructure. For a long time, Gulf states actually had to import jet fuel from abroad. Moreover, state entities like Qatar Petroleum operated on strictly commercial terms. They didn't give discounts to the national airline; in fact, trading with them was tough, and their domestic prices were often higher than the Singapore index. There were no fuel subsidies.

</details>

**乔·威森塔尔**: 我听说过一个关于你们在物理燃油调配上的传奇故事，你能证实一下吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: There is a famous story about physical fuel tankering that you did. Could you share that?

</details>

**戴维·金**: 哈哈，是的。当时我们接收了一架崭新的**波音 787 梦想客机**（Boeing 787 Dreamliner），对外官方声明是飞往迪拜进行飞行员机组训练。但实际上，我们在起飞时故意只加了极少的燃油——大概只有 4 吨到 5 吨油，这个油量甚至不够在迪拜机场上空盘旋等待，必须直接进近降落。

为什么我们要这么做？因为当时迪拜的航油价格明显低于多哈！飞机几乎空腹落地迪拜后，我们在迪拜把油箱加得满满当当（多达 100 吨燃油），然后飞回多哈。回到多哈国际机场后，我们把多余的燃油直接抽进航司自有的储油罐里！

这种**燃油携带与倒运**（Fuel Tankering）不仅摊薄了高昂的本地航油采购成本，而且航司自建的燃油储备设施还能确保即使外部供应链遭遇地缘阻断，整个机队也能维持独立运转。

<details>
<summary>Original English</summary>

**David King**: Yes! When we took delivery of the 787 Dreamliner, the official announcement was that we were flying to Dubai for crew training. But in reality, we took off with the fuel almost completely depleted—barely 4 or 5 tons. It wasn't even enough to circle Dubai Airport; we had to land straight away. A 787 can take up to 100 tons of fuel. So we tankered cheap fuel in Dubai, flew back to Doha, and discharged the fuel directly into our own storage tanks at Doha International Airport! That allowed us to lower procurement costs and secure physical inventory.

</details>

### 全球炼油瓶颈与航油柴油争夺战

**崔西·阿洛威**: 让我们把目光转向当前的宏观环境。近期欧洲和全球柴油市场极度紧张，市场甚至在讨论美国可能出台精炼油出口禁令。作为交易员，你怎么看当下的精炼油供需格局？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Looking at the current macro landscape, diesel and distillate supplies are under immense pressure globally, and there has even been talk about potential US refined product export bans. How do you view the global distillates market today?

</details>

**戴维·金**: 提到出口禁令，这让我联想到政治民粹主义对商品流动的影响。俄罗斯是全球第二大柴油出口国，俄乌冲突及随后的制裁导致欧洲柴油出现巨大的供应缺口。

而在炼油化工体系中，**航空煤油**（Jet Fuel）、**车用柴油**（Diesel）和**民用取暖油**（Heating Oil）都属于中间馏分油（Middle Distillates）。它们的生产在炼油塔里存在着天然的替代关系——炼厂可以通过调整催化裂化参数，多产柴油而少产航煤，反之亦然。

美国东海岸由于缺乏足够的管道输送能力，在历史上极度依赖从美湾（US Gulf Coast）经海运驳船运送燃料，或者直接从欧洲进口柴油。由于欧洲柴油短缺，**伦敦柴油**（London Gasoil）价格暴涨，全球贸易流被彻底打乱。甚至出现了从美湾经巴拿马运河向亚洲运送燃料，以及从亚洲长途奔袭调运精炼油的奇特套利航线。这种全球炼油产能与贸易流的错配，使得航空煤油的裂解价差在未来很长一段时间内都将保持极高波动。

<details>
<summary>Original English</summary>

**David King**: When a major exporter restricts supply, the ripple effects are massive. Russia is the world's second-largest diesel exporter, so European diesel supplies plummeted. In refining, jet fuel, diesel, and heating oil are all middle distillates. Refineries optimize yields based on margins. The US East Coast is geographically constrained with limited pipeline capacity, relying heavily on maritime shipments from the Gulf Coast or imports from Europe. With London Gasoil surging, global flows reversed. Ships like Aframax or Panamax tankers are moving products from the Gulf through Panama to Asia, and cross-hauling across continents. This distortion keeps jet fuel crack spreads exceptionally volatile.

</details>

### 总结：航司博弈的商业启示

**乔·威森塔尔**: 戴维，非常感谢你今天精彩绝伦的分享！听众可以在 SSRN 上阅读你的学术论文《21世纪燃油对冲：航空公司如何先发制人调整收入》（21st Century Fuel Hedging: How All Airlines Preemptively Adjust Revenue）。

这场对话完全颠覆了我们对企业对冲的传统认知。通常人们把交易员看作单纯在市场上投机牟利的群体，但真正的企业交易员必须彻底看透商业模式的本质。航空公司看似是燃油短缺的受害者，但借助动态定价与燃油附加费，航司实际上已经蜕变为原油市场的隐性多头。识别出企业的内在风险敞口，才能制定出超越教科书的真正对冲策略。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: David King, thank you very much for appearing on Odd Lots. For those who would like more details, you can find the paper at SSRN entitled "21st Century Fuel Hedging: How All Airlines Preemptively Adjust Revenue." What I found most interesting in this episode is that while corporations dislike the term 'trader', that is exactly what they do. Typical traders focus solely on maximizing profits, but if you properly understand the company's core business, you realize airlines are structurally long oil via ticket pricing and surcharges. Identifying that natural exposure changes everything.

</details>

**崔西·阿洛威**: 确实如此。这就像芝加哥的面包店：当鸡蛋价格暴涨的新闻传遍大街小巷时，面包店老板可以顺理成章地涨价，顾客也不会抗议；航空公司的票价弹性在油价飙升期展现得淋漓尽致。尽管大家抱怨票价昂贵，但出行需求依然井喷，全球航空市场依然火热。

感谢戴维的倾囊相授。本期 Odd Lots 就到这里。我是崔西·阿洛威，大家可以在推特上关注我（@tracyalloway）。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yes, I completely agree. Just like a bakery in Chicago that raises pastry prices when egg prices soar in the news, consumers accept high airline ticket prices because they know oil is high. Travel demand continues to surge regardless. Thank you for listening. I am Tracy Alloway. You can follow me on Twitter at @tracyalloway.

</details>

**乔·威森塔尔**: 我是乔·威森塔尔，可以在推特上关注我（@TheStalwart）。感谢制作人 Carmen Rodriguez、Dashbot Bennett、Caleb Brooks 以及 Kevin Lloyd Lozano。更多内容请订阅彭博每日通讯，或登录 bloomberg.com/oddlots 收听全集。也欢迎加入我们的 24 小时 Discord 社群（discord.gg/oddlots）。如果您喜欢我们的节目，请在播客平台上留下好评！我们下期再见。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I am Joe Weisenthal. Follow me at @TheStalwart. Please also follow producers Carmen Rodriguez, Dashbot Bennett, Caleb Brooks, and Kevin Lloyd Lozano. For more Odd Lots content, check out the daily newsletter and all episodes at bloomberg.com/oddlots. You can also talk about all these topics anytime, 24 hours a day, on Discord at discord.gg/oddlots. If you enjoyed this conversation, please leave a positive review on your favorite podcast platform. Thank you for listening.

</details>