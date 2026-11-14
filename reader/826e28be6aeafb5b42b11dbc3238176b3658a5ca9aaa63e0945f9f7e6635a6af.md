---
author: AI Engineer
date: '2026-10-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GCse4OMzY8U
speaker: AI Engineer
tags:
  - compute-trading
  - market-structure
  - jevons-paradox
  - over-the-counter
  - data-center-finance
title: 算力暗池：为何算力交易至今仍发生在线上聊天群中？
summary: Jump Trading 的算力交易负责人深度解析当前算力市场的宏观与微观结构。面对代币价格暴跌与算力成本坚挺的杰文斯悖论，中端算力买家面临严峻的融资错配与长期合约风险。演讲揭示了当前缺乏统一交易所、严重依赖场外私密群聊撮合的“算力暗池”现状，并探讨了算力期货、灵活合约及资产负债表桥接等金融化破局路径。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Jump Trading
  - CoreWeave
  - a16z
products_models:
  - H100
  - H200
media_books: []
status: evergreen
---
### 算力暗池与场外交易现状

>> 大家好。我叫 Afaan，在自营交易公司 Jump Trading 负责算力交易（compute trading），旁边是我的联合负责人 Alejandro。

今天我们将探讨适用于算力交易的一些市场结构、算力交易究竟是什么、以及我们预见它将发展成什么样。我认为我们会先从宏观视角切入，接着审视微观结构，然后简单谈谈我们对政策层面的看法。

本场演讲的标题是“算力的暗池”（The Dark Pools of Compute），不过现场有些朋友来自金融界，可能会困惑我为何使用这个术语。我在这里所说的“暗池”到底是什么意思？

本质上，我指的是一个不透明的市场（unlit market）。目前大部分算力——这里指物理算力——都是以大宗（blocks）方式交易的，而且都是私下报价。我们有大量的经纪人，这些都是长期的双边合约。归根结底，这些实际上是商业协议。我们在这里使用“交易”这个词，是为了观察各方之间是如何进行交易交割的。这些商业协议往往是由主服务协议（MSA）、服务等级协议（SLA）和订购单组合而成的，针对特定集群，在每份订单中都包含特定的硬件条款。但当我们观察定价和其中一些其他指标时，很多时候大家讨论的核心都围绕着硬件规格（skew）——也就是芯片本身是什么、底板是什么，比如 H100、H200、B300 等等。

<details>
<summary>Original English</summary>

>> Um hey everyone. My name is Afaan and I'm I'm a lead for compute trading at Jump Trading, which is a proprietary trading firm, alongside my co-lead over here, Alejandro.

So, today we're going to be looking over some of the market structure as it applies to compute trading, what compute trading even is, um what we can see it becoming. And I think we'll start with some macro, look at micro structure, and then talk a little bit about where we see things in policy.

So, the title of the talk is the dark pools of compute, but some of you guys are in finance, so you might be confused as to why I'm using this terminology. Uh what do I mean by dark pool here?

Essentially, what I'm referring to is an unlit market. Um right now, most compute trades in blocks, physical compute here, and these are private quotes. We have a lot of brokers and these are long bilateral contracts. Now, at the end of the day, these are really commercial agreements. So, we're using the term trading here to kind of like look at how it's transacted between parties. These commercial agreements tend to be some mixture of an MSA, an SLA, and an order form, cluster specific uh with hardware specific language in each kind of um in each order. And but when we're looking at pricing and looking at some of these other kind of uh metrics, a lot of the time, most of the talk is around the skew. So, what the chip itself is, the base board. So, H100, H200, B300, uh etc.
</details>

因此，这里的许多谈判都是在公众视野之外进行的。目前并没有一个被广泛采用、人人都去查看并交易算力的实体交易算力交易所。这些交易都是在聊天工具里完成的，对吧？它们不在公众视野之内。虽然有一些公开市场、价格参考和许多按需市场，然而对于这些真正有固定期限（tenured）——即在给定租期内、具有固定容量且伴随特定合同总价值（TCV）的算力——它们是通过 Slack 消息、X 私信和 Telegram 群聊来交易的。这是一堆散布在各类新型聊天工具中的场外（OTC）渠道。你们中有些人可能熟悉大宗商品交易，熟悉大家在 Ice Chat、Bloomberg Chat 等平台上聊天沟通的方式，这里的市场目前差不多就是这样的状态。

<details>
<summary>Original English</summary>

And so, um a lot of the negotiation here happens kind of outside the public view. There's no, you know, like exchange for physically traded compute that's widely, you know, adopted and you know, used for everyone goes there to like take a look and trade uh compute. These are done in chats, right? They're out of the public view. Um there's public marketplaces, there's price references, there's a lot of um you know, on-demand marketplaces. However, for these actual tenured, so you know, on a given term for a fixed amount of capacity uh with a certain total contract value, these trade over Slack messages, X messages, Telegram group chats. It's a bunch of OTC kind of channels that are all over in these kind of I want to call them like neo neo chat. Um and some of you might be familiar with commodities and how a lot of you know, there's chatting happening on Ice Chat, Bloomberg Chat, etc. This is kind of where where the where the kind of markets here lie.
</details>

### 宏观市场结构与杰文斯悖论

我想谈谈这里的宏观市场结构以及其中的参与者。这是 a16z 最近发布的一张图，你们中有些人可能已经看过了。我把它拿出来展示，是因为大家可以去 a16z 的 X 账号亲自查看这张图表。我们看到的是，特定能力的成本已经大幅下降。

当然，最终的账单仍然取决于模型的使用量、容量以及速度等其他因素——随着新型代码生成与 ChatGPT 模型的推出，速度现在是一个非常关键的考量。代币（token）越便宜，就能释放越多的使用量，团队可以用相同的预算完成更多的工作。因此我们看到的是，很多团队干脆直接消耗了多得多的代币。我们面临着这种尚未完全释放的潜在需求，人们在维持原有预算不变的情况下，只会去使用更多算力。某些模型成本更高，他们消耗的代币数量也更多。

这样一来，原本成本过高的应用变得可行了。然而，正如我们讨论算力时所说，底层的硬件容量依然需要被构建和付费，即便特定任务的单次成本已经降低。因此，关键的区别在于：智能的价格、人们想要运行的任务数量、以及服务这些任务所需的硬件规模之间的差异。

<details>
<summary>Original English</summary>

And so I want to look at a little bit here on the macro market structure and a little bit on the players here as well. And so this was a recent kind of a16z, some of you guys might have seen this. So I'm I'm putting this out there because you know, you can go on a16z's actual X and take a look at this graph yourself. What we're looking at is that the cost of a given capability has fallen sharply.

The bill of course still depends on the model usage, capacity, and other factors such as speed is a big thing right now with the new code ChatGPT models. Um cheaper tokens unlock more usage and a team can do more work for the same budget. So what we're seeing is that a lot of teams are simply just using way more tokens. So we have this latent demand that hasn't really been hit yet and people were just going to use more with the same budget that they were using before. One model's cost more and they're just expending more tokens.

Um so applications that were too expensive become possible. Um however, as we're kind of talking about compute here, the capacity underneath still has to be built and paid for um even as the cost of a particular task comes down. And so the important distinction is between the price of the intelligence, the number of tasks people want to run, and the amount of hardware needed to serve them.
</details>

这就引出了杰文斯悖论（Jevons paradox），也是我们最近一直在观察的现象。直觉上，大家会认为算力与推理成本往往是同向变动的，相关性非常紧密。但正如你们所见，这里发生了一定程度的脱钩：代币价格进一步下跌，但算力价格依然保持坚挺。对这种现象能有什么解释呢？这里有很多潜在的解释，其中之一就是杰文斯悖论：即便在新型底板和 GPU 上提供代币生成和推理服务的效率变得极其高效，人们的消耗量却急剧上升。因此对算力的需求不降反升，即便每百万代币的输入、缓存和输出成本大幅优化，人们消耗的代币总量却大大增加了。

通过让单个任务更便宜，刺激了更广泛的使用，抵消了单任务层面的资源节省。对推理云（inference clouds）而言，这意味着服务更多的应用程序、处理更多的代币、获取更大的市场份额。而对于应用层的从业者来说，这意味着你们能够服务更多类型的客户——任何基于代币基础设施进行构建的人都是如此。

<details>
<summary>Original English</summary>

And so this is where we get to kind of the Jevons paradox and a little of some of the stuff that we've been looking at lately where we had a very interesting thing where, you know, intuitively you'd assume that compute and inference kind of like rises together, correlates very, you know, very closely as you can see. You can see there's a little bit of a decoupling that happened and token prices declined further but compute prices have remained robust. And so like what what can be an explanation for this? Now, there's a lot of like potential explanations. One here is the whole Jevons paradox is that even though token prices and inference is getting extremely efficient to serve on these new baseboards and and and and GPUs, people are just consuming a lot more. And so the demand for compute rises and people just consume a lot more tokens even if the cost per cost per million for input and for caching and, you know, for output becomes a lot more efficient.

And so making the task cheaper, encouraging the use that way resource saving per task. For inference clouds, that's going to be more applications, serving more tokens, bigger market share.

And for app layer individuals, that means you guys can serve to a lot more kind of customers. So anyone who's building utilizing the token infrastructure.
</details>

### 上游基础设施要素与参与者版图

那么，宏观结构中究竟包含哪些要素？虽然这里列出的非常基础，但你得有我们一直在讨论的芯片。你还需要电力、建筑物、电网连接，当然还需要庞大的资本来推进这些建设，这正是眼下大家热议的焦点。芯片、电力、场地、资金，所有这些都必须齐备，你才能获得一小时真正可用的“GPU 每小时”算力。

国际能源署（IEA）4月的更新报告预测，全球数据中心的用电量将从 2025 年的 485 太瓦时（TWh）激增至 2030 年的 915 太瓦时。因此，目前的大量讨论都集中在扩建、建立电网连接上。我们的电网容量足够吗？是否有其他能源可以接入？我们在哪里能获得土地来实际完成这项工程？因此，托管设施（colocation sites）、数据中心运营商、为扩建提供融资的人士或贷款人本身都在关注这一领域。算力上游的一切因素，最终都会向下传导至算力本身的成本和使用之中。

<details>
<summary>Original English</summary>

And so what really goes into, you know, the macro structure. Now like this is very, you know, bare bones here but you've got your chips which we've been talking about. You have power, you have buildings, grid connections and then of course you need a lot of capital to get these build outs going and then that's kind of been the whole talk here. And so um chips, powers, buildings, money, they all have to come together before, you know, you can even get to an hour of like actual usable GPU per hour compute.

And so the IEA April update projects that the global global data center electricity is going to rise from 485 terawatt hours in 2025 to 915 2030. And so a lot of the talk right now is around build-outs, about getting the power grid set up. Will we have enough power grid here? Is there other energy sources that we can tap into? Where are we, you know, able to get the land to actually be able to do this? And so, colocation sites and data center operators, and people who are doing the financing the build-outs or the lenders themselves, are all kind of looking into this. And that type of everything that's upstream, essentially, of the compute is going to then flow down into the compute uh costs and also usage.
</details>

那么，在所谓的宏观版图底层，具体格局是怎样的呢？芯片和系统厂商供应 GPU 服务器和网络设备；场地与运营商提供电力、空间、组装和管理；这里有 GPU、显存、服务器和网络连接；算力容量提供商——包括超大规模云厂商（hyperscalers）、新型云服务商（neo clouds）以及任何类似新型云模式运营、转售裸机容量的运营商；最后是最终用户。那么谁是真正的最终用户呢？初创公司、推理云、实验室、新型实验室，以及应用层上的任何团队，还有运行开放权重模型的企业。

我把它们划分成了这些方框，但实际上参与者完全可以是“以上皆是”。比如一家芯片和系统厂商，完全有可能进行全流程的端到端建设，同时自身也是这一切的最终用户。因此，这里存在一定程度的重叠与变化。

正如我之前提到的推理云，他们可能会租用一个集群，在上面提供代币生成服务，并用这笔收入来偿还集群的租赁费用。对于推理云自身来说，这可能是一种使用场景。

<details>
<summary>Original English</summary>

And so, what does this like actual macro map look like underneath a quote chip and system vendors supply the GPU servers and networking, sites and operators supply the power, space assembly and management right here, GPUs memory servers and networking, um capacity providers, these are hyperscalers and neo clouds and any other operator that's like operating similar to how a neo cloud would operate, reselling bare metal capacity, and then the users. So, who's the actual end user? The startups, the inference clouds, uh labs, neo labs, and also anyone on the app layer and enterprises for anyone doing open weight stuff as well.

And um these boxes, like I've kind of boxed them out here, but, you know, there's people can be all of the above. A chip and system vendor, like someone could do a full end-to-end build-out and also be the end user of everything. And so, there's a little bit of um variation that that that occurs here.

And so, as I was kind of mentioning about the inference clouds before, they might rent a cluster and they'll serve tokens off of it and they'll use that revenue to the pay off the cluster. Um and so, that might be a use case for the actual inference cloud themselves.
</details>

### 中端市场的融资错配与运营模式

然而，对于超大规模云厂商、前沿模型实验室和规模较大的新型云服务商而言，它们能够做出巨大的采购承诺，因为它们有能力募集大额股权资金，也有能力承担更多债务。它们具备签署长期限协议的能力，比如 OpenAI 签署的 10 年期大单等等。然而，处于中端市场（middle market）的参与者根本无法做到这一点。

谁会为一个 B 轮融资的初创公司承销足够容量、为其背书一份 3 年期超过 2 亿美元的算力合同？他们必须融多少轮股权才够？他们是否得把整轮股权融资的资金全砸在集群租用上，导致没有剩余资金去覆盖实际的运营成本？

我们来看一下这里的融资链条及其影响。贷款人是根据合同约定的预期收入来为扩建工程提供资金的，许多推理云的情况正是如此。他们希望为扩建提供贷款，但他们需要确信这笔贷款能得到偿还。你怎么去为一个未上市的私营初创公司做承销呢？它们并没有太多其他资本背书。它们不是上市公司，没有丰厚的现金流、资产负债表和利润表，甚至可能处于尚未盈利、尚未产生收入的阶段。因此贷款人看重的是：该客户能否在特定规模上获得有保障的合同收入。CoreWeave 的公开申报文件提供了大规模基础设施融资的典型案例，这种融资由“照付不议”（take-or-pay）的客户合同作为支撑。这张图表展示了一个小型的示意案例。

这里的错配在于：硬件融资方要求非常长的期限，但客户只承担得起短约，或者根本不愿意签署超过 36 个月的长期融资协议。客户必须支付高达 15% 到 25% 的预付款——这是 CoreWeave 公布的其中位数预付款比例——在总价值 1 亿美元的集群合同中，预付款比例为 15% 到 25%。这就意味着一家初创公司必须预先拿出 1500 万到 2500 万美元，这可能直接花光他们整轮的融资金额。

<details>
<summary>Original English</summary>

However, for hyperscalers, frontier labs, and larger neo clouds, they can make substantial commitments because they have the ability to get into the large equity, they have the ability to take on more debt. And uh they have the ability to do long horizon kind of deals. So, 10-year deal opening I contracted it out, etc. So, of that nature. However, anyone in the middle market isn't actually able to do this.

Who's underwriting a Series B startup with enough capacity to get in a 200 million plus contract over 3 years for compute? How many equity rounds will they have to raise, right? Will they have to use their entire equity round to fund just the actual cluster and then they don't have any remaining capital left to use for actual costs?

And so, we're looking at a little bit of the financing chain here and how that plays in. So, lenders are financing the buildout against contracted revenue even in many cases for inference clouds. And so, they want to finance the buildout. They want confidence that their loan will get repaid. I mean, like how are you going to underwrite a startup like a private company that doesn't have like much else going for them right now. Like what are the, you know, they're not publicly traded. There's not that much cash flows, balance sheet, income statement. They might even be pre-profit, pre-revenue, etc. And so, what they're looking at is that can the person get contracted revenue over a certain scale. And so, Coreweave's public filings give large-scale example infrastructure financing supported by take or pay customer contracts. And so, this diagram kind of shows the smaller illustrative example here.

And the mismatch is that hardware financing they want very long terms, but customers are only able to afford or don't really want to like get into a long-term financing over 36 months. They have to put up on up to 15 to 25% is what Coreweave has quoted that they've seen their median prepayment to be, 15 to 25% up front on a 100 million TCV cluster. That's 15 to 25 million dollars that a startup has to put up front. That might be their entire round.
</details>

这就是我所指的情况的一个直观展示。比如你融资了 4000 万美元，需要签一份 3 年期 1 亿美元的合同。你交了 30% 的预付款——这是一个示意案例——你就只剩下 1000 万美元来维持公司运转。正如你在这里看到的，你的算力供给呈现阶梯函数式的增长。那是你的合同容量，而实际需求可能远低于这一水平。每当你需要引入一个新集群时，都必须与股权融资或类似事件绑定，但你可能会面临产能上限，不得不拒收客户。

此时你有什么选择？你要么拒收客户，直到完成下一轮股权融资、能再次拿出 30% 的预付款去启动下一批算力容量；要么使用按需算力来填补缺口、弥补容量不足。这现在成了一个选项。此时你必须计算经济账：如果去找贷款人为预付款部分提供融资，但融来的预付款成本还不如当时直接在现货市场按需采购划算（假设届时能买到相应容量），那么走贷款在经济上是否还合理？

<details>
<summary>Original English</summary>

And so, this is kind of a look at what I'm you know, referencing here. It's like you're raising 40 million, you need a 100 million contract over 3 years. You put down 30% prepayment. This is an illustrative example. You've got 10 10 million left to run the business, um and so you might have this kind of step function as you can see here. So, that's your contracted capacity and what you can actually in the demand is like, you know, uh below that. And so, now every time that you have to get into a new cluster, it's like tied to your equity round or whatever else it may be, but you might have to cap out and turn away customers. So, what are your options? You either turn away customers until you can get into your next, um you know, equity round so you can put down another 30% prepayment so you can get next little bit of capacity going, or do you use on demand to close the area under the gap and bridge the shortfall?

That's like an That's like an option now. Now you have to look into the economics. What does that look like? What's the difference between, you know, maybe instead what they do is they go to a lender to finance the prepayment component, but if the yield on the prepayment component that they're getting financed is less than, um them just buying it out on demand at that time if they're able to get into that amount of capacity, then does the economics make sense there?
</details>

以下是我们观察到的一些运营模式：

你可以自建并运营全栈体系：硬件、场地，你的团队负责调配电力、许可、组装和运维。

你也可以在托管数据中心拥有服务器，组装和运营或多或少交由合作伙伴处理。

在天平的另一端是包销合约（off-take contract），购买特定规模的容量，由提供商拥有并运营资产。他们可能不会给你裸机的完整 root 权限，或者根据单租户还是多租户等配置划分访问权限层级，这些配置也会影响最终定价。

一些企业看重物理层面的控制权，一些企业重视机密计算，另一些企业可能看重特定的拓扑结构调整或重新配置系统的能力。如果这些对你的业务至关重要，他们可能会希望获得越来越多的控制权，从而自行搭建和运营技术栈。考虑到仅仅签署租赁包销合约所必须放弃的机会成本，自建模式在经济上对他们来说可能是合理的，因此他们愿意为此支付更多。

<details>
<summary>Original English</summary>

And so, here are some of the operating models that we've seen. It's like you can build and operate the full stack. Hardware, site, your team is going to arrange power, permit, the assembly, the management.

You can also own servers in a colocation facility with more or less the assembly and operation handled by a partner. Um on the other end, an off-take contract buys defined capacity and the provider is going to own and operate the asset, and they might not give you complete root access to the bare metal or there might be kind of like levels to how much access you get depending on if it's tenant, multi-tenant, and etc. type of like configurations that can also affect them the pricing.

Um And so, some businesses are going to value the physical access, some businesses are going to value, um you know, confidential compute, uh you know, they might value certain topology changes or the ability to reconfigure the system. And so, if that is something for your business and they might actually want to have more and more control and build and operate the stack and the economics for them might make sense given the opportunity cost they would have to give up um if they were to just take rental off take contracts. So they might be willing to pay more there.
</details>

这是一张关于“自持与租赁在利用率上升时的对比”的简易图表。我们看到的是，通常情况下，这些包销合约的成本正在逼近自己构建和融资一个集群的成本。如果你在 3 年内要花掉 1 亿美元，除去时间成本和潜在的运营开销，如果经济账算得过来，直接买下一个算力运营方或许更合理。

这里存在一个必须遵循的平衡点：自持成本高过租赁成本时，租赁成本理应处于自持成本线下方；但如果你的利用率极高，且增量变化难以预测，直接买下并自持整套系统可能是最优解。

我们发现了一个新动态：算力采购直接影响着一家成长型公司的实际现金跑道（runway）。这也促使投资者对算力采购产生了浓厚兴趣。从风险投资（VC）的角度来看，算力获取途径和付款条款直接决定了他们被投企业的现金跑道有多长。因此，帮助被投企业采购合适的算力容量，能够直接改善底层投资的回报，两者紧密相连。他们能够为被投公司采购并落实算力容量，并提供资金支持。这也为宏观结构引入了另一个有趣的微观维度：究竟由谁来协助安排算力容量？报价如何进行对比？这些合约又能够转移哪些风险？

<details>
<summary>Original English</summary>

And so here's how I ownership and rental is a very like crude graph. How ownership and rental can compare as utilization arises.

And so what we're looking at is that usually you know an off take contract or these off take contracts are getting to the cost of actually almost building out and financing your own cluster. And it's not because I mean if you're spending a hundred million over a three year period then maybe if the economics make sense it would have made more sense to simply buy out the compute operator yourself outside of the time cost and then off the operational cost that might exist.

So there's a there's a equilibrium that exists that that has to be followed where you know the ownership cost outweigh the you know rental cost and the rental cost should sit below the ownership cost. But if you're utilizing at a such a rate and you know in such variable kind of increments it might be best to just own the stack out right.

And so we're seeing this new dynamic that compute the compute procurement affects how much runway a growing company actually has. And so this also gives investors an interest in computer procurement. So we're kind of seeing this. Access and payment terms affect how much runway their port codes are going to have from a VC perspective. So helping a company buy a suitable capacity can improve the underlying investment and they're very connected. Right? So they're able to procure and they're able to actually find compute capacity for their port codes and and and fund that. And so that also brings another interesting aspect to the macro structure into the micro structure is that who helps place the capacity and how does this offer get compared and what risks these contracts can can transfer.
</details>

### 微观结构：价格发现、非同质化与金融化工具

围绕“GPU 每小时”这个核心单位，有许多不同的市场参与者在共同塑造这个市场。

首先是价格发现参与者：拥有指数、数据和基准测试的人士。我们所有人目前都在参考这些基准数据，未来在获得批准后，这些基准利率也将被用于推出相关期货合约。

其次是物理撮合场所、拍卖平台和聚合器——也就是任何能够撮合容量的渠道。我们看到了去中心化的按需算力市场；看到了提供流动池服务、自主拆分并拥有标准化合约的流动算力池；看到了裸机转售商；看到了开展大规模算力销售的新型云厂商；以及在裸机转售领域的独立经纪人与独立运营商。

还有交易台和经纪人。他们负责双边报价和执行。他们人脉广泛，行动敏捷。他们可能在一个地方看到符合高度相似规格的报价，同时知道另一端有一位对价格极度不敏感的买家正急需算力；他们能够及时拿到现货（RFS, Ready for Service），从而赚取可观的价差。接着，他们需要负责货源谈判，并承担和配置相应风险。他们必须为客户运营该集群，因此这笔服务必须对得起这份利差。

在金融市场方面，基于 GPU 运行小时的交易所即将到来，伴随而来的还有期货和衍生品。人们将利用它们来对冲风险并探索更复杂的金融架构——例如对冲资产负债表风险。

<details>
<summary>Original English</summary>

So we have a lot of different players around this GPU hour that are helping kind of shape this this market here.

You've got your price discovery individuals. So, people with indexes, data, the benchmarks that we're all looking at right now and referencing, which would be used to, you know, in the future launch the futures based on the benchmark rates, you know, talked about in in the associated contracts per spec per pending approval.

And then there's the physical matching venue auctions aggregators. So, anyone who can match capacity. We're looking at essentially decentralized marketplaces for on-demand compute. You're looking at liquid pools of compute that offer like liquid pool services and parted out themselves and have their own standardized contract. You're looking at bare metal resellers. You're looking at neo clouds themselves doing larger capacity sales. And then you're looking at individual brokers and individual operators here as well on the bare metal reselling. You have desk and brokers. They're looking at the bilateral quotes and execution. They might know a lot of people. They might be able to move fast. They might be able to see quotes at very similar specs in one place and know that there's a buyer that is extremely inelastic to price right now. It needs the compute immediately and they can get the RFS in time so they can charge a decent spread on it. And then what they do is they're going to have the source negotiating and then they're going to be carrying and placing the risk. They're going to have to operate that cluster for the person and it has to be worth that spread.

And you know, you have looked in financial markets, the exchanges that are coming that are based on the GPU hour, the futures and derivatives. People are going to be using it to take a look at how to maybe hedge out and look into more financial structures. So, hedge out risk. So, hedge out, you know, my balance sheet risk.
</details>

各方正在达成更有意思的协议。我们看到类似预付款融资工具（prepayment payment facilities）正在上线；人们正在利用期货，并且有兴趣借助期货和其他期权工具来对冲目前资产负债表上的既有风险。买方也在寻求灵活合约（flex contracts），比如：“如果我签署了一份 3 到 5 年的合同，当新芯片上市时，我是否有权升级？或者能否允许我展期？或者允许我把算力卖回给你？”

此外还有信贷融资机构：设备贷款人、租赁商和专业信贷提供商。

目前在我们看来，几乎每一笔交易都是高度定制化的（bespoke）。规格表不同，交付格式不同，物料清单（BOM）可能与实际交付内容不符；如果某个零部件缺失或缺货，还可能随时发生变更；原始设备制造商（OEM）和原始设计制造商（ODM）类供应商的交付周期往往非常漫长。

当谈判节奏非常快时，同一个词汇可能代表完全不同的含义。如果有人谈到“内存”，我们究竟是在讨论显存（VRAM）、CPU 内存，还是额外的存储空间？你到底确切指的是什么？这极大影响了终端用户的实际工作负载运行能力，也直接影响到定价和交付日期。

<details>
<summary>Original English</summary>

Maybe get into more interesting agreements. We're looking we're seeing kind of agreements such as prepayment payment facilities are coming online. We're seeing people utilize futures and are interested in utilizing futures and other kind of um um options to be able to There's demand for this to be able to hedge out the risk that they currently have on the books. We have buy side individuals looking for flex contracts, flexible contracts like hey, is there ability that if I lock myself into a 3 to 5 year contract that I'll be able to you know, at least upgrade when a new chip that comes out or maybe I'll be able to roll it over or maybe let me sell it back to you.

And then there's a credit financing. So equipment lenders, leasers, specialist credit providers.

And so the way we're seeing it right now is that every deal is bespoke. There's different spec sheets, there's formats. The bill of materials may not match the actual like delivery or there might be subject to change if a part is missing or part is out of stock and you know, there's like very long lead times that some of these OEM and ODM kind of providers have.

And the same term can mean different things when you're negotiating very quickly. If someone's talking about memory, are we talking about you know, VRAM or we talking about the CPU memory, talking about additional storage here? Like what did you exactly mean there? It affects quite a bit what type of loads can be run on you know, the actual end users needs and also with pricing. And delivery dates.
</details>

在任何人能够进行真正客观的对比之前，必须经过大量的来回沟通。这正是非同质化（non-fungibility）概念发挥作用的地方：如何拆解这一特性？哪些部分可以同质化？哪些部分占据最大权重（例如芯片规格等）？而哪些部分依然像普通商品或电商产品那样交易——即该报价仅适用于那一个特定集群？

因此，价格可能每天甚至更快地发生变化。公开报价仍然是一个不错的起点，但往往会被砍价或频繁调整供应内容。这里存在着种种潜在的隐藏因素，这也是我们称之为“暗色市场”（dark market）的原因。

这些是今天截取的部分公开 H100 参考价格，我刚刚更新过。大家可以看看公开数据，如果你去他们的官网上也能看到这些参考价格。这只是一个示例，展示了如今一块 H100 的公开按需或现货价格大概是什么水平。

大家可以看到各种各样的价格。人们可能会参考这些数据，也可能会根据自己内部掌握的行情来做预估，或者在综合考虑所有其他影响因素后，为自己的具体集群配置制定收费标准。

为什么需要这些新机制？为什么这些微观结构如此值得关注？核心在于解决错配问题：填补容量缺口、提供更灵活的承诺、转售权益以及防范价格波动风险。

从推理云的角度来看，如果你在以固定价格销售推理服务，而 GPU 的账单成本却处于浮动状态，就会产生巨大的价格风险敞口。锁定数年的算力容量可以解决一部分问题，但除非一直满载运行，否则会在其他地方造成算力闲置的风险敞口。转售闲置容量的前提是必须有人愿意买下这些小时。金融对冲可以锚定参考价格，但在现金结算或保证利用率方面，它无法立刻交付一个物理集群。因此，真正有用的机制设计，必须从企业自身面临且亟需管理的具体风险出发。

<details>
<summary>Original English</summary>

So there's a lot of back and forth before anyone can really compare and this is where the concept of like non-fungibility kind of comes into place and how to partition that out, what parts can be fungible, what parts hold the most of the weight such as the skew etc. And what parts are still like traded as if it was a product, e-commerce etc. where you know, it's only for that particular cluster that this price applies.

And so prices can update daily or faster. Quotes still a good starting point but it can get chopped rather than it is changes what's on offer. There's all these kind of latent factors, hidden factors as well why we're calling it a dark market.

These are some public H100 references snapshotted today. I updated them. So take a look at the what the public so those are the references for if you wanted to go on their websites to see. This is just an example here of like what a public on demand or spot pricing looks like for an H100 today.

You can see kind of various various prices here. And so, people might use this or they might use their own kind of internal what they've seen to actually like assume or use it to charge what they want to charge on their actual cluster specification, taking to account every other kind of factor that goes into it.

And so, why are these new structures kind of needed and what are these microstructures interesting? It's mainly to solve for these mismatches, right? Bridging capacity, more flexible commitments, resale rights, and protection against price moves. Um you know, you're selling a fixed price service from an inference cloud point of view, you'd be selling a fixed price service while the GPU bill floats and that creates price exposure. And so, locking capacity for years can solve a part of that, but it'll create idle hour idle hour exposure elsewhere as well, unless they're always using it.

Reselling spare capacity only helps if someone actually can buy the hours. A financial hedge can address a reference price, but can't deliver the cluster right now in terms of cash settlement or guarantee a utilization. So, the useful structure has to start with a particular risk that the business has and needs to manage.
</details>

### 监管政策与未来机遇

>> 政策这部分我会讲得非常快，因为我们的时间快用完了。

Afaan 刚刚提到的一切，都处在一个受到监管并受政策影响的框架之内，体现在方方面面。出口管制就是其中一个典型案例。今年 1 月，美国商务部将针对中国和澳门的合格 H200 级别许可证审查，调整为附带条件的逐案审查（case-by-case review）。

此外，开放权重模型将政策与我们一开始讨论的美国经济基本面重新联系在一起。美国的人工智能行动计划（AI action plan）明确鼓励开源和开放权重 AI，并建议完善算力金融市场，以便初创公司和学术界能够获得大规模的算力支持。

<details>
<summary>Original English</summary>

>> And I'll I'll go pretty fast on this policy section because we're running out of time.

Everything that a fan has said sits inside of a structure that is regulated and is affected by policy. In various ways. One way is export controls, one of the examples. In January, the US Commerce Department moved qualifying H200 class license reviews for China and Macau to case-by-case review with conditions.

Furthermore, open weight models connect policy back to the US economics we started with. The US AI action plan explicitly encourages open source and open weight AI and recommends improving the financial market for compute so that startups and academics can access large-scale computing power.
</details>

>> 我在这里做个总结：机遇究竟在哪里？

我们面对着这个不断扩大的中端市场。我们需要能够弥合买方与供方需求的强大资产负债表。市场需要一定程度的标准化：标准的容量合约、通用的规格、通用的条款和定义。成长型企业的实际需求和承诺能力，无法套用超大规模云厂商和前沿实验室所签署的现成合同。这些中端企业有着真实的业务负载，我们希望它们成长，但它们依然受制于融资难题、交付周期难题和规格不一致的难题。供应商希望通过长期承诺来进行扩建投资，而处于技术前沿的买方由于需求波动极大，希望在需求更加明确时以更小规模的批次进行扩容。买方需要一种途径，避免为尚未使用到的富余容量提前买单。

因此，拥有与市场非相关性（uncorrelated）的强健资产负债表、具备强劲信用评级并有能力评估这些风险的市场参与者，能够协助弥合买方需求与供方报价之间的断层。这需要的不仅仅是对单个 GPU 小时进行报价，更意味着要深刻理解交付流程、实际业务负载等所有环节。

目前市场上这样的参与者少之又少。而一个非常契合这一角色的参与者，应当是一家业务与市场周期非相关、资产负债表雄厚、信用评级优异，并且内部储备了深厚高性能计算硬件人才的企业。

在此向大家发出行动号召：让我们携手共建这个市场。非常感谢大家前来参加我们的演讲。

>> [掌声]

<details>
<summary>Original English</summary>

>> So, I'm going to tie this out right here, but where's this opportunity lie? We have this growing middle market. We need balance sheets that can bridge buyer and supplier needs. There needs to be some level of standardization, a standard capacity contract, common specs, common terms, and definitions. And so, growing companies with needs and commitment do not fit the contracts the hyperscalers and frontier labs can sign. Those companies have real workloads. We want them to grow. They still face this financing problem, a timing problem, a specification problem. A supplier might want the long-term commitment for the build-out while the buyer wants to expand in smaller blocks as demand becomes clearer as it's so volatile, front of curve. The buyer needs a way to avoid paying for capacity can't use yet.

And so, participants with strong balance sheets that are uncorrelated with the market and the ability to assess those risks with a strong credit profile can help bridge the gap between what buyers need and what suppliers offers. That requires more than quoting the actual GPU hour. It means understanding the delivery, workload, all of that. And so, there's very few kind of players in the market, and you know, a very well-suited player can be a firm that's uncorrelated with market, with strong balance sheet, strong credit rating, an incredible amounts of hardware talent that sits inside for high-performance computing.

And so, just making a CTA here, let's build this together. Thank you guys so much for attending our talk.

>> [applause]
</details>