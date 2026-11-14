---
author: Dwarkesh Patel
date: '2026-08-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oZBGAuANX6I
speaker: Dwarkesh Patel
tags:
  - compute-economics
  - ai-scaling
  - semiconductor-supply
  - alchian-allen-effect
title: 智能红利与算力刚性：为何更智能的 AI 模型将推高算力价格？
summary: 本文探讨了 AI 实验室营收十倍增长与算力供给仅三倍增长之间的矛盾，分析了智能变现效率提升将如何推高算力租金，并结合阿尔钦-艾伦效应及半导体物理产能瓶颈预测了未来算力市场的极端刚性与集中化趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Google
  - SpaceX
  - TSMC
products_models:
  - GB200
  - GB300
  - H100
media_books: []
status: evergreen
---
### 智能红利与算力刚性：为何更智能的 AI 模型将推高算力价格？

### 算力与营收的非对称增长及调节路径
在过去连续三年中，**Anthropic** 的营收实现了同比 10 倍的增长，去年年底达到 90 亿美元，今年预计将达到 1000 亿至 1500 亿美元。如果这一趋势持续，到明年年底其营收需达到 1 万亿美元。尽管这种指数级外推在商业上极为疯狂，且完全取决于 AI 能力是否能达到相应的实用高度，但即使这一趋势得以维持，它也与另一个核心趋势相冲突：前沿实验室的**算力供给**（Compute Supply: 用于模型训练和推理的计算资源供给）年增长率仅为约 3 倍。

要弥合 10 倍营收增长与 3 倍算力增长之间的鸿沟，行业必须发生以下三种调节，或其某种组合：
1. **实验室利润率**（Lab Margins: AI 研发实验室从推理等服务中获取的毛利率）提升；
2. **算力价格**（Compute Prices: 租用或购买计算资源的市场价格）上涨；
3. **推理算力占比**（Inference Share: 用于模型日常运行/应答而非训练研发的算力比例）相对于训练算力增加。

目前，这三种趋势均已在现实中显现。在利润率方面，Anthropic 的推理利润率已从去年中期的 40% 飙升至如今 Fable 模型的 80% 以上。在算力价格方面，GPU 现货价格较今年 2 月的低谷上涨了 40% 以上。在算力分配上，**OpenAI** 在 2024 年仅将四分之一的算力用于推理，而当前这一比例已接近或超过 50%。

然而，前沿实验室并不希望将过多算力消耗在推理端。在实验室的商业逻辑中，推理收入的本质是向投资者证明 AI 的商业可行性，从而募集更多资金以训练下一代更大、更强的模型。若将大部分算力用于推理，无异于宣告 AI 技术进步停滞，使自己降格为普通的云服务商。实验室的目标是开发**通用人工智能**（Artificial General Intelligence: 具备与人类同等或更高级智能的通用 AI 系统），他们坚信能在一年内开发出让当前模型相形见绌的新一代系统，因此必须将大部分算力投入到训练与实验中。

<details>
<summary>Original English Source</summary>

Today I want to talk about what the compute situation for the labs will look like over the next few years. For the last three consecutive years, Anthropic's revenue has 10x'd year over year, and it's likely to do so again this year. They ended last year with nine billion in revenue. I think they'll probably end this year with somewhere between one hundred billion to one hundred and fifty billion dollars in revenue. Now, for this trend to continue, Anthropic would need to make one trillion dollars in revenue by the end of next year. Of course, there's no deep reason why this has to be true. It's a very wild conclusion, and it's ultimately a question of AI capabilities. Does AI get that useful by the end of next year? But suppose the trend does continue. I want to think through what happens in that world.

The other big trend in AI is that lab compute only 3x's year over year. For a lab to keep 10x'ing revenue year over year while compute only 3x's, one of the following three things needs to happen, or some combination of the three: One, lab margins have to increase. Two, the price of compute has to increase. Or three, the percentage of compute that labs spend on inference rather than training has to increase. My understanding is that basically all three of these things are already happening. With regards to the margins, Anthropic's inference margins reportedly went from forty percent in the middle of last year to upwards of eighty percent now for Fable. With regards to compute, the spot prices for compute are more than forty percent higher than they were in the February trough that we had earlier this year. And with regards to the share of compute that goes to training versus inference, in 2024, according to Epoch, OpenAI was spending just a quarter of its compute on inference, and that number is likely closer to fifty percent, if not higher, now.

Now, labs would prefer not to do this final thing of increasing the share of compute they spend on inference. The way the labs see the world, the whole point of inference revenue is to help convince investors to give you more money in order to train the next bigger, better model. And if you're spending most of your compute on inference, then you're basically declaring that AI progress has stalled and you're just now in the business of being a cloud provider. This is a less compelling business than building AGI, so the labs do not want to be in this business, nor do they think they are in this world. They think that within a year, they'll have built models that make the current ones look extremely shitty. But they need to invest a lot of their compute — the majority of their compute — into doing the training and experiments that are necessary to build the next model.

</details>

### 算力定价重估与智能变现的宏观博弈
在算力与营收的博弈中，溢价的分配将流向利润率占优的前沿实验室，或是整条产业链下方的算力提供商。若实验室利润率占据主导，头部模型必须具备压倒性的竞争优势，使其利润率从现有的 80% 提升至 90% 以上。然而，在市场经济中，如此高昂的智能利润率极易被竞争对手侵蚀。

因此，另一个主要的调节通道在于算力价格的上涨。目前，前沿实验室所需的算力不仅是零散的现货实例，更需要具备高效率、灵活性以及能够保障模型权重和客户信息安全的规模化算力集群。一个典型的案例是 **Google** 与 Anthropic 向 **SpaceX** 租赁算力的交易。例如，Google 每月支付 9 亿美元租用 11 万张 GPU（包含 **GB200** 和 **GB300** 的混合架构），其每小时租用单价高达市场现货价格的 2 倍。

随着模型智能度的提升，其变现相同算力的能力将显著增强。如果一个相当于人类水平的软件工程师能够运行在 **H100** 等效芯片上，按照目前人类软件工程师的薪资水平，该芯片的年租金应当超过 25 万美元，这比目前 H100 约 1.5 万美元的现货租金高出 15 倍以上（且尚未计入 AI 可以无休工作的时间）。

虽然有人会担忧，成千上万虚拟工程师的涌现会引发**劳动力总额谬误**（Lump of Labor Fallacy: 认为社会工作总量是固定不变的，新劳动力的加入必然导致工资下降的假说），从而降低单个 H100 产生的边际收益。但经典经济学关于高技术移民的研究表明，由于创新和分工会提升整体劳动力的价值，劳动供给冲击在长期内并不会压低工资。因此，算力的边际价值与租金水平在未来极有可能保持在令人震惊的高位。

<details>
<summary>Original English Source</summary>

So that leaves only two options for how you can get out of this gap between the fact that lab compute only increases 3x year over year, but revenue increases 10x. Either the lab's margins have to increase so that they get the surplus, or the price of compute has to increase so that everybody in the stack below the lab gets the surplus. It's not clear to me which world we end up in. Do we end up in a world where we go from 80% for some of the top models to greater than 90% margins if the lab margin effect dominates? That would require the leading model to be so far ahead of the competition, because the nature of margins — why they exist in a market economy — is that the thing you are serving is so much better than what somebody else could go get and replace you on the market. But it's just really wild for me to consider that the margins for something like intelligence will be greater than 90% and they don't get competed away at that level.

So that leaves only one other possibility of this escape valve between these two trends, which is that the price of compute has to increase. As I mentioned, this is already starting to happen. And the effect is even stronger when you look at the tranche of compute that the frontier labs actually need to accumulate, because they can't just go out and buy a spot instance. They need to make sure that they get enough scale to get really good efficiency and flexibility, and also that they have the kind of compute that lends itself to the security they need for their own weights and for their customers' information.

I think a relevant case study here is to look at the compute that Google and Anthropic are renting from SpaceX. Google, for example, is paying nine hundred million dollars a month for a hundred and ten thousand GPUs that are a blend of GB200s and GB300s. The price that Google is paying here is 2x the spot price per hour for those GPUs. And that spot price itself is more than forty percent higher than it would have been in February. I want to emphasize a key conclusion here: as AI models get smarter, they will be better able to monetize the same amount of compute. If a true human-level software engineer could run on an H100 equivalent, then at today's prices for software engineers, that H100 should rent for over 250K a year. That's over 15x the current spot price for an H100. And this is not even accounting for the fact that your AI can work nights and weekends.

Of course, you might expect that if we had ten million extra software engineers suddenly appear in the economy, the marginal value of a software engineer would decrease, and thus the revenue that that H100 would be able to generate would not be 15x higher than it is right now. But I actually don't know if this is true. If we apply this argument to people instead of AIs, then this would be the classic lump of labor fallacy. For example, economists generally believe that high-skill immigration does not decrease wages in the long run because of how innovation and specialization increase the value of labor. Maybe this labor supply shock will be so big and so fast that we can't count on this general heuristic anymore. But if you believe what standard economics says, then the marginal value of labor, and thus the marginal value of compute, should stay astonishingly high.

</details>

### 阿尔钦-艾伦效应与算力生态的价值筛选
在这种算力高溢价的经济格局下，AI 行业的竞争维度将发生剧变：

首先，前沿实验室由于拥有更强的算力变现能力，将彻底垄断核心资源，使其他竞争者难以承受算力竞价。

其次，**阿尔钦-艾伦效应**（Alchian-Allen Effect: 假定当两种替代品因固定附加成本增加而价格同等上升时，消费者会倾向于选择高品质产品的经济学效应）将发挥关键作用。如果租用 H100 的成本高达每小时 20 美元，那么使用性能较弱、效率较低的模型将变得极其愚蠢，因为在昂贵硬件上消耗更多 Token 来获取相同结果的成本是不可接受的。因此，能够训练出更省算力、更高性能模型的实验室将能够获得极高的品牌溢价。

最后，大批现有的普适性 AI 应用可能会因为算力成本的飙升而被无情排挤出局。当前 AI 服务的廉价，在很大程度上是因为它们还无法取代顶尖人类的工作。然而，一旦 AI 能够在前沿领域（例如自动化 AI 研发）展现出超越人类的生产力，Google、Anthropic 或 OpenAI 等巨头为了将其用于科研自动化而愿意支付的 Token 价格，将远远超出普通用户为了生成娱乐性“AI 废话（slop talk）”所愿意支付的成本。

<details>
<summary>Original English Source</summary>

So let's think about what changes in such a world. One of the things that would happen is that as the top labs get better and better at monetizing compute, and the cost of compute increases, it becomes harder for anybody else to compete against them, because they have to bid for this resource against somebody who is basically able to make better use of it.

Another thing that will happen — and I think this is actually the most interesting implication of this whole thought exercise — is that if you can train the best, most efficient model, then you'll be able to charge much higher margins than you can today. This is the Alchian-Allen effect in economics, and what it's basically saying is that if it costs twenty dollars an hour to rent an H100, then it would be extremely stupid to use a weaker, less efficient model, because it's gonna burn more tokens on your expensive compute to get the exact same result. So labs will be able to charge a much larger premium if they can train a model that better economizes this scarce input. Basically, if you have a model that can get the same result by using less compute, then you've, in some sense, created more compute, and the value of compute is gonna increase.

Another thing that will happen is that a lot of current popular applications of AI will probably get priced out. The reason AI is relatively cheap right now is that AI just can't do a lot of things that top humans can do. But this, at some point, will no longer be the case. And at that point, Google or Anthropic or OpenAI will be willing to pay more for the tokens to automate AI research than you or I will be willing to pay to make more AI slop talk.

</details>

### 商业插播：Mercury 财务自动化
在探讨宏观算力之余，作者分享了个人在月末处理公司账目时的实际效率工具。为了避免手动分类大量新签约承包商（如导师、研究员和摄像师）以及新软件的复杂交易账目，作者借助了 **Mercury** 银行平台内置的 AI 助手 **Command**。

Command 可以一次性对所有交易进行分类并给出合理的判断依据，不仅关注商户名称，还会深入分析团队采购人员、备注和备忘录以构建完整的上下文。在人工审核确认后，所有分类数据将自动同步至 **QuickBooks**。

> [!NOTE]
> Mercury 是一家金融科技公司，并非受 FDIC 保障的银行。其银行服务由 Choice Financial Group 和 Column N.A.（均为 FDIC 成员）提供。AI 建议的准确性及操作效果不受保证。

<details>
<summary>Original English Source</summary>

At the end of the month, I go through the time-honored tradition of closing my books. I start by opening Mercury, which is my banking platform, to make sure that all my transactions are properly categorized. Auto-categorization rules handle the predictable stuff pretty well. But I'm constantly working with new contractors—tutors, researchers, and videographers—and I'm also trying new tools. Manually categorizing all of these transactions would add a couple of hours of overhead every single month.

So instead of going through them one by one, I have Command, Mercury's built-in AI, take a stab at all of them at once. Command proposes a category for each transaction and provides its rationale. I just review, fix anything that's off, and approve.

Once all this work is done in Mercury, it syncs everything with QuickBooks. And Command's judgment calls are genuinely good. It does the obvious things, like looking at the vendor, but it also investigates who on my team made the purchase and looks at notes and memos to build up as much context as possible. This is just one of the ways you can use Command to automate the back end of your business. To learn more, go to mercury.com/command. Mercury is a fintech company, not an FDIC-insured bank. Banking services are provided through Choice Financial Group and Column N.A., Members FDIC. AI-generated responses and suggested actions may vary and are not guaranteed.

</details>

### 算力供给的物理刚性与垄断隐忧
在传统经济学中，著名的**西蒙-埃利希赌局**（Simon-Ehrlich Bet: 1980年经济学家西蒙与生态学家埃利希关于资源稀缺性与价格关系的著名打赌，最终以资源价格下跌、西蒙获胜告终，用以证明市场机制与技术创新能解决资源稀缺问题）被用来佐证市场信号和人类智慧终将化解物质的稀缺性。然而，这一逻辑在算力供给上面临严峻挑战，因为算力在应对强烈的需求冲击时，其供给弹性显著弱于传统金属矿产。

维持算力每年 3 倍增长的三个物理支柱目前均已达到极限，极难加速：
1. **摩尔定律**（Moore's Law: 约每两年集成电路芯片上可容纳的晶体管数目翻倍的经验法则）：贡献了约 1.4 倍的增长。当前保持该定律的延续已属不易，很难指望其加速。
2. **新建晶圆厂**（Fabs）：贡献了约 1.2 倍的增长。直至 2030 年甚至更晚，该进程都将受到 **ASML** 的 **EUV 光刻机**产能的严重制约。
3. **晶圆份额倾斜**：贡献了约 1.8 倍的增长。这是通过将原本分配给智能手机和 PC 的晶圆产能转移给 AI 芯片实现的。然而，在 **TSMC**（台积电）的最先进 N3 节点上，AI 的占比已经从 60% 飙升至 86%，这一调整空间将在明年年底前触顶。

虽然在未来的后奇点时代，随着机器人技术的发展，算力制造成本可能会降低为硅砂和铜矿等原材料成本与加工费用的总和，但在当前的“奇点前”阶段，每年仅 3 倍的算力增幅根本无法抵消 AI 智能变现价值的飙升。

这种营收 10 倍增长与算力 3 倍增长之间的巨大不对称，进一步揭示了人工智能模型行业中强大的规模效应。一旦模型完成训练，其所学到的技能可以瞬间无边际成本地共享给所有用户，这与每次都需要从头培训的人类劳动力截然不同。这种极强的规模经济效应虽然令人担忧权力过度集中，但它无疑是当前我们所面对的技术现实。

<details>
<summary>Original English Source</summary>

Now, I wanna clarify that at some point in the future, compute will get cheap again. At some point, we'll just have robots that can convert shores of silica sand and mines of copper into new computer chips, and then the price of compute is basically the raw inputs and the tools required to do this processing. I'm just talking about this current pre-singularity regime where AI compute merely 3x's year over year, which is not enough to offset how much more valuable AI is becoming over time.

By the way, the fact that Anthropic's revenue has been 10x'ing year over year, whereas their compute has only been 3x'ing year over year, I think illustrates how strong the economies of scale are in the model business. And logically, this makes sense. When you train a model, you just have to spend this one-time cost to learn all these different skills that then get to be shared across all your users. This is very unlike human labor, where each instance has to be retrained from scratch. I wish we didn't live in a world with such strong economies of scale for intelligence, because I'm worried about power concentration, but it seems we do.

I'm a bit worried that this kind of analysis honestly pattern matches a lot onto the ways that people in the past have been wrong about scarcity. I'm thinking, for example, of the famous Simon-Ehrlich bet. Paul Ehrlich was this famous doomer about population growth, and he made this bet that a basket of commodities would increase in price rather than decrease in the decade preceding 1990. This is a very famous bet because it's supposed to illustrate how Ehrlich's Malthusian worldview was wrong, and how he did not anticipate the way in which market signals and human ingenuity can find better ways to economize scarce inputs. I'm guessing that the analogy to this bet is probably wrong. Other analysis has shown that if that bet had been made in a different decade, Ehrlich might well have won. But more generally, I think the supply of compute is much less elastic, much less capable of absorbing large demand shocks, and much less capable of being accommodated by using different substitutes than the extraction of different metals is.

To illustrate why I think this 3x in compute capacity year over year is hard to budge or potentially even sustain: I don't see how any of the three elements that constitute that 3x can be much accelerated. 1.4x of that is coming from Moore's Law. Far from increasing it, I think it'll be a miracle if we can just keep it going for a few more years. 1.2x is coming from building new fabs. This process is ultimately gonna be bottlenecked up to 2030 and potentially even beyond by just building new ASML EUV machines. Dylan, when he was on the podcast a few months ago, talked about this in great detail. And 1.8x comes from the fact that AI is absorbing a lot of wafer allocation that was previously going to smartphones and PCs. This is probably gonna hit a wall by the end of next year, when at the leading edge N3 nodes at TSMC, AI will have gone from 60% to 86%. At some point, you have just absorbed all leading-edge wafer capacity for AI, and you can't keep increasing this number. So I don't know how we even continue to do 3x compute scaling year over year for the next few years, much less go beyond that.

Okay, this was a narration of a blog post that I also released on my website at dwarkesh.com. Check it out for other posts or to be notified when I release a post in the future. Otherwise, I'll see you for the next full episode.

</details>