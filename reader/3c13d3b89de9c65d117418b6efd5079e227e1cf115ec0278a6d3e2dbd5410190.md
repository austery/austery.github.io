---
author: Latent Space
date: '2026-11-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wX8nDtGIfYA
speaker: Latent Space
tags:
  - ipo
  - valuation
  - unit-economics
  - compute-spend
  - inference
title: Anthropic IPO 前瞻：S-1 财务细节、算力承兑与商业化拆解
summary: 本期对话聚焦 Anthropic 上市前的核心财务与商业化披露。嘉宾 Tanay Jaipuria 与主持人围绕其 S-1 文件展开分析，探讨了隐含估值、极低的现金消耗率、推断与训练算力分配、企业代码生态以及巨额算力承诺等关键议题。
insight: ''
draft: true
series: ''
category: investment-assets
area: finance-wealth
project: []
people:
  - Tanay Jaipuria
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Claude
  - S-1
media_books: []
status: evergreen
---
### IPO 前瞻与估值倍数

大家早上好。今天我们在 Anthropic IPO 之前做最后一期关于其 IPO 的播客。至于 IPO 之后是否还会继续跟进，目前尚待确定，因为那时候这就变成财经播客的范畴了。但我认为这显然对很多听众来说仍然高度相关，特别是那些在 Anthropic 工作的人，还有在 OpenAI 工作的听众，以及生态系统中关联的所有人。IPO 路演已经持续了几周，我们掌握的信息也比以前多了一些。我们在 Jam and Ball 播客中详细讨论过很多内容，反响非常好，感谢大家所有的积极反馈。你知道，我尽量邀请那些在技术与金融交叉领域让我尊敬和仰慕的人，因为我觉得如果说有什么的话，我的职业经历正好让我能够胜任做这件事。我们看到 Anthropic 提交的文件定价大概在 70 到 78 美元之间，这意味着隐含估值为 1.3 万亿到 1.4 万亿美元。目前看起来大约获得了 7 倍的超额认购，最终定价很可能会在 80 美元左右。另外在远期合约或加密货币合约市场上，大家也在押注最终首日涨幅会落在哪里。如果情况与 SpaceX IPO 类似，首日会有一个小幅跳涨，大约是 19% 到 20%，价格也许会涨到 100 美元左右。所以这就处在大概 1.54 万亿到 1.6 万亿美元的估值区间。这意味着大约是过去 12 个月收入的 38 倍，当前收入的 20 倍。当然，所谓的远期收入完全取决于你的预测。目前预计——10 月份的年化运行率（run rate）披露为 810 亿美元，这也是一项新披露的数据。

年底的年化收入预计仍将达到 1000 亿美元。人们真正在思考的是：从这里开始未来会走向何方？市场目前的定价逻辑是什么？在这样的规模下，这显然是所有人给出过的最高估值倍数。至于对未来年份的预期，比如 2028 年或 2030 年，年收入预测范围从 4000 亿美元到 1 万亿美元不等，这是一个非常宽泛的区间。但为了给 Anthropic 的长期投资进行承销，你必须做这类的算术推演。所以你可以理解为什么大家都在向前看。目前有 1.1 万到 1.2 万家客户每年每家至少花费 10 万美元；一旦进入一家公司，未来几年还会带来 9 倍的扩张。其净金额留存率（NDR）表现极佳，通常顶尖水平大概是 150%，而这里达到了 900%。所以路演中的讨论主要集中在三件事上：第一是 Claude Cowork，从市场叙事来看这基本上是下一个阶段，即你在 Claude Code 之外能拓展得多好。我认为未来的形态可能与 Claude Cowork 有所不同，因为正如我们之前在节目存档里与 Felix 录制的第一期 Claude Cowork 播客中所聊的，那是一种现存形态，但我认为它并不算非常云原生；而他们在 S-1 文件中描绘的那种自主协同队友——就像我们在第一期播客中讨论的——绝对必须是云原生的。无论是 Claude Duet、Instinct，还是 Grok bots、Cognition bots，所有人都在朝这个方向发展，我不认为 Claude 会落后，它很可能会演变成不同于 Claude Cowork 的新形态。第二是芯片：Anthropic 希望跨 Nvidia、AMD、TPU 和 Trainium 运行，他们还发布了如何能更轻松地从 Nvidia 迁移到 AMD 的信息。这显然也是人们担忧的整个 RSI 叙事的一部分，但从商业角度来看这极为合理：如果你受制于 Nvidia 的瓶颈，那就必须这么做；而且这是可验证的，也是大模型易于完成的核心任务之一。第三是利润率：关于利润率我们得到了更多披露，调整后利润率从 19% 下降到了 15%，从 GAAP 营业利润转为轻微的 GAAP 亏损，这属于主动为之，并不是大问题。Anthropic 预计长期内可以达到 35% 以上，如果实现将会意义重大，因为那将非常赚钱。正如我们在之前与 Jam 的播客中讨论的那样，对于如此庞大体量并筹备 IPO 的大型科技公司而言，这是前所未闻的。通常这类公司在深度亏损（比如连续三四年录得 -100% 的利润率）之后才开始好转。而这是伴随着利润的增长，极为罕见。本周发生的最后一件事是 OpenAI 的模型发布。正如我们之前所确立的，模型发布对于前沿实验室的生存能力至关重要。前沿模型的保鲜期大约只有 6 个月，如果你不能在前沿推出下一代模型，使用量显然就不会流向你，这对于基准测试和社区风评体验（vibe checks）非常敏感。OpenAI 推出了 GPT-6.2 和 Fable，Anthropic 推出了 Fable 5.2。显然 Fable 5.2 依然位居榜首，大部分实际体验也证明 Fable 处于领先地位。此外 OpenAI 声称在效率前沿占据优势，但人们在实际使用中的反馈褒贬不一。总体而言，这两家公司的模型发布并没有根本改变各自的阵营：如果你是 Claude 用户会继续留用，如果你习惯了 OpenAI 也会继续使用。那些可能剧烈改变 IPO 叙事（无论是利好还是利空）的关键风险并没有真正发生。大家预期的 Fable 5.5 没有发布，Gemini 推出了 Gemini 4 也没有对整体格局产生冲击，尽管 Gemini Carbon 表现相当不错。仅此而已。因此对于 Anthropic IPO 来说，这些关键风险已经过去了。Anthropic 依然是全球顶尖的模型实验室，明天就要 IPO，这将会是一场轰动性的上市。这对整个生态系统极为有利，因为如果 Anthropic IPO 失败，再叠加当前正在发生的 Nvidia 风波，市场预期将会变得非常糟糕。这就是过去一周的总体动态。大家已经做好了准备。我们在本期播客中录制了对 S-1 文件更深入的细节剖析，希望大家喜欢，也祝明天的上市一切顺利。好的，现在我们在远程演播室。这是我们跟进 Anthropic IPO 系列的又一期节目，今天邀请到了 Tanay Jaipuria。欢迎你！
<details><summary>Original English</summary>
Good morning. Today we're doing our last anthropic IPO podcast before the IPO and TBD on whether or not it will actually continue covering it after the IPO because uh that becomes the domain of finance podcast. But uh I think it's still obviously very relevant to a lot of listeners particularly those of you that work at Anthropic but also those of you that work at OpenAI and uh everyone else connected in the ecosystem. Um, the IPO road show has been going on for a couple weeks and we know a bit more than we used to before. Uh, and we covered it a lot of it in the Jam and Ball podcast. That went really well. Thank you for all the positive feedback and uh, you know, I think I try to pull in people that I respect and look up to in terms of the crossover of technology and finance. Uh, because I mean I think that is if if anything my career has set me up to do that. Um so we have a price for the anthropic filing I guess uh between $7 to $78 which is an implied valuation of 1.3 to 1.4 trillion. uh it looks like it is roughly seven times overs subscribed and probably will price in the range of 80ish and then there's also forward contracts or crypto contracts on speculating where the final pop is going to end up if it looks anything like the SpaceX IPO there will be a small pop um it will be about 19 to 20% on the first day uh maybe would go up to $100 um and so that that is in that range of let's call it 1.5 4 to 1 uh 6 trillion, you know, and um that represents roughly 38 times trailing 12-month revenue, 20 [clears throat] times current revenue. And obviously this uh and and obviously that what what Ford revenue is is just dependent on what your projections are. It's still anticipated to uh so October run rate was 81 billion. That was also a new disclosure. Still projected to end the year at 100 billion. And what really people are thinking about is like well where does it go from here right like what is the market pricing um this is obviously the highest multiple that anyone's ever uh priced at especially at this size and uh you know ranges for the future like uh future years in like 2030 u or 2028 um really range from like 400 billion to a trillion uh in revenue and so uh that is very wide range. [laughter] Um but you kind of have to do this kind of math in order to uh underwrite long-term investments in Anthropic. Um and so you can see why people looking ahead. You know, I think um uh 11 12,000 customers spend at least 100K per uh uh year and per customer, but once they land in a company, they also expand nine times um in the in the future years. So like uh there is uh NDR like a very good net dollar retention uh usually state-of-the-art is let's say 150% and this is 900%. Um so really the discussion about the road show has focused on three things. One which is cloud co-work um it is basically the sort of next phase as far as the market narrative is um how how well are you extending outside of cloud code. I think there is probably going to be a different form factor I would say than cloud co-work because cloud coowork is you know we did the first cloud co-work pod with Felix um if you scroll back in our archive and it's a it's a form factor that's there but I think it's not very cloud native and definitely the sort of autonomous like teammate that they are pitching for their S1 that we covered in the first podcast that is um definitely going to have to be cloud native that's cloud duet that is the instinct that is the gro bots that is the cognition bots all those things are like everyone is trending towards that direction and I don't see why cloud would not do that and probably that is going to be something different than cloud co-work uh the second one is chips uh entropic wants to run across Nvidia AMD TPUs tranium um and they also released information about how they were easily able to migrate much much more easily uh from Nvidia to AMD And I that is obviously part of the whole RSI narrative that people are concerned about. But I think that is obviously just makes a lot of business sense for them that like hey if you're I'm bottlenecked on Nvidia I'm sorry I I have to do this right and by the way it's verifiable and by the way it's uh one of the core tasks that we that is uh that that is easy for LMS to do. Third is margins. Um so we have a little bit more in terms of disclosures on margins. Um we know that margin went down from 19% to 15% and using an adjusted margin. Uh it went from a gap operating profit to a slight gap loss and that is just intentional not a big deal. Um Anthropic is projecting that it can get above 35 in the long run. Uh so that would be a very big deal because then it would be very profitable and that's something that uh again like we as we discussed in uh this podcast in the previous one with Jam that is just unheard of for a large tech company of this size IPOing. uh usually you're unprofitable like deeply unprofitable like like 100 negative 100% profits for I don't know 3 4 years [laughter] before you even start to turn it around. Um and that's good. I mean this is growth with profit which uh never happens. Uh I think the final thing that happened this week is opening eyes model launch. Um as we already established model launches are incredibly incredibly important to the viability of the Frontier Labs. Um the shelf life of Frontier model is roughly 6 months and if you don't release the next model at the frontier then obviously the usage is uh not going to come to you and it it is very sensitive to benchmarks and uh vibe checks and so open shipped GBT 6.2 and Fable and topic shift Fable 5.2 and obviously Fable 5.2 is still on top and I think the vibe checks are mostly holding out that Fable is on top. So there's that and then there's the efficiency frontier which open does claim. I think people are a little bit more mixed in practice in terms of there's benchmarks and then there's just like impractical use and um I would say that there's basically both model launches have not really changed camps either way. If you're a cloud person, you could continue to be clawed. If you're happy with an open AI, you're continue to be open AI. Uh those key risks for the IPO that may have dramatically changed the story either for the positive or negative haven't really changed. There was no Fable 5.5 that people were anticipating and um there, you know, and Gemini shipped Gemini 4 that did not affect the narrative even though Gemini carbon did very very well. And that's about it, you know. So like those key risks are behind us for the anthropic IPO. Um Enthropic is still the top model lab in the world and uh it is IPOing tomorrow and it is going to be a blockbuster IPO and that's really good for the ecosystem because a failed enthropic IPO would have been uh would have read through really badly together with the Nvidia drama that is also happening at the same time. Um so that is the overall update in the last week. You are mostly prepped. This is our podcast that we recorded to go through some finer details in the S1 and I hope you enjoy and good luck tomorrow. Okay, we're in the remote studio. Uh this is another in our series covering the enthropic IPO uh with Tane Japur. Welcome.
</details>

>> 谢谢你的邀请。我是节目的长期听众，很高兴能来做客。
<details><summary>Original English</summary>
>> Uh thank you for having me. Longtime listener of the podcast and excited to be on.
</details>

>> T，你怎么会想到去写 S-1 文件的拆解分析呢？
<details><summary>Original English</summary>
>> Uh T, how come you're uh writing S1 breakdowns?
</details>

>> 是的。总的来说，过去六七年里我一直在 Substack 上撰写各类长文，其中一个主题就是在有趣的公司上市时对其进行深入拆解。我认为 S-1 文件通常是局外人能够窥见公司业务各个维度的时刻。我之所以非常喜欢阅读它们，是因为你可以从中体会到这家公司迄今为止的发展历程；而且我觉得每家企业都能为人们提供一些有趣的商业启示，无论是关于泛商业层面的，还是针对特定业务类型的。所以我过去一直从这个视角进行跟踪。在过去一年左右的时间里，我们见证了 SpaceX 以及现在的 Anthropic 这样真正具有划时代意义的公司走向上市，去研究它们就变得更加有趣了。它们不仅能让你了解这些具体公司的现状，还能展现更广泛的市场全貌。通过 Anthropic 的 S-1 文件，你可以纵览一切：从模型研发、到如今被普遍视为下一个巨大市场的模型推断（inference），再到算力需求现状、新型云服务商（neoclouds），以及未来在科学等领域的布局。显而易见，这是一家定义行业的标杆公司，而且目前仍处于相对早期的阶段。令人不可思议的是，在短短五六年的时间里，它就如此迅速地创造了如此巨大的价值，这是我们在任何公司身上都前所未见的。
<details><summary>Original English</summary>
>> Yeah. No, I think in in general I guess uh maybe for the last uh six or seven years I've been uh you know writing about various things like more on long form on on Substack and one of the topics I've been writing about just like breakdowns of interesting companies as they go public and I think the S1 is usually the time when as as an outsider you get a look into like you know all aspects of the business and the the reason I enjoy reading them so much is that you can kind of get a sense of like the story of the business so far and I feel like in every business there are some interesting lessons that you know for people to take away about business in general about you know specific kinds of businesses and so I used to follow them from that perspective and then obviously over the last year or so some of the you know the ones we've had go like with SpaceX and now with the Anthropous one these are like you know truly generational defining companies and so uh I think it's been even more uh even more fun to to look into those and I think they do give you a sense of the current state of um those companies specifically but then also the market more much more broadly and so with the anthropic S1 kind of gives you like a purview into everything from you know this this the idea of like you know the model development inference everyone's talking about like inference as this you know the next big huge market uh it gives you a sense of you know the current state of all the compute uh needs and like neoclouds and then also what's to come in the future with things like science and uh some of those things. And so I think it's obviously like a category defining company and one that uh and one that's still relatively early in in kind of crazy that in you know in five or six years it's uh created this much value so quickly uh and it's something we've never really seen before uh uh across any company really.
</details>

>> 确实如此。我很乐意直接切入正题。你准备了很多图表，我们可以跟着你的思路来展开。看那些核心财务数字，他们的营收增长非常迅猛，相比去年同季度增长了大约 13 到 14 倍，非常引人注目。10 月份的年化运行率数字刚刚泄露出来，我们之前就知道他们有所储备，虽然在 S-1 文件中留白了，但现在报告的年化运行率达到了 800 亿美元，对吧？
<details><summary>Original English</summary>
>> Yeah, for sure. Uh and you know I I'm I'm happy to dive right in there. you have a lot of charts that are um have been prepared and I can go wherever you want to take this headline numbers um you know they're they're ramping revenue a lot it's really interesting basically up like 13 14x from uh same quarter last year I think the run rate numbers just leaked for October which we knew was was uh something that they had in store and they they kind of left blank in the S1 but now uh they're reporting 80 billion run rate right
</details>

>> 嗯。
<details><summary>Original English</summary>
>> um
</details>

>> 是的，800 亿除以 4 就是季度 200 亿，对。
<details><summary>Original English</summary>
>> yeah So I think it's 80 divide by 4 is 20. Yeah.
</details>

>> 是的。我猜测他们计算 800 亿的方式更偏向于按月折算。他们实际采用的精确定义可能是 28 天乘以 13，再加上当月的订阅收入。这很有意思，因为即使在 Twitter 上，人们的反应也褒贬不一：有人认为这是一个非常正面、积极的数字，标志着增长重新加速；而另一些人则认为，这意味着他们可能达不到之前谈论的 1000 亿退出年化运行率（exit run rate）。虽然很难断言，但我认为环比月增长率大概落在 8% 到 10% 左右。
<details><summary>Original English</summary>
>> Yeah. And I think the the my guess is the way they calculate that 80 is this kind of more like on a monthly basis. And so I think the exact definition they might use is actually 28 days times 13 plus like monthly subscription revenue. And so it's it it's interesting because I think it's being even on Twitter I think the reactions to that will mix where there are some people saying oh this is like a very good very positive number and uh signals reaceleration. uh whereas some are saying that it's actually they'll it'll mean that they likely will fall short of the 100 exit run rate that they've been talking about. I I think it it's hard to tell but I think it probably is in that kind of 8 to 10% month overmonth growth which I think is
</details>

>> 我不知道这算不算重新加速，但至少和他们过去几个月的表现大致持平，我猜甚至可能略有上升。不过目前很难完全确定，因为他们还没有按月对第三季度等数据进行详细拆解。
<details><summary>Original English</summary>
>> I don't know if it's re acceleration but it's at least roughly in line with what they did in the last few months and it might be slightly up is my is my guess but hard to hard to fully know at this point because they haven't broken down you know Q3 and stuff by month.
</details>

>> 确实是这样。80% 来自用量消耗，20% 来自订阅，这挺耐人寻味的。订阅模式能享有多大折扣早已是公开的秘密，所以大家其实有动力去压低这 80% 的按量消耗占比，但这需要先摸透其订阅体系。
<details><summary>Original English</summary>
>> Yeah. Yeah. Totally totally. uh 80% consumption, 20% subscriptions, which is kind of funny. Uh it's like it's a pretty public secret how much of a discount the subscriptions get. Um so actually people are incentivized to make this 80% consumption base lower, but uh you have to sort of figure out the subscription system.
</details>

>> 年花费超过 10 万美元的客户数量增长了 8 倍，达到 1.2 万家。抛开大家已经看过的总体数字和盈利表现，由你来主导的话，你认为大家最应该领会的核心要点有哪些？
<details><summary>Original English</summary>
>> Um and uh you know number of customers over over 100K is up eight times to 12K. Um yeah, you know, like I I'll let you drive like what what let's assume that people have looked at the headline stuff and they know about the profitability. What are the major topics that uh you think are the the main messages that people should take away?
</details>

### 现金消耗率与资本效率对比

>> 是的。过去几个月里一直有各种关于他们大致年化运行率的泄露信息，所以对于关注这件事的人来说，基于 S-1 之前公开发布的内容，这些都在意料之中。我认为最让人意外的其实是公司的现金消耗情况，我是从积极的层面来看这一点的：他们此前筹集了大约 1400 亿美元现金，而资产负债表上居然还躺着大约 1320 亿美元。也就是说，他们走到今天这一步消耗的资金不到 100 亿美元。除了身处内部知晓真实数字的人，外界没有人预料到他们账面上预留的现金弹药库有如此庞大，大家之前的预期更多是基于对其烧钱速度和利润率的推测。因此这其实是一家资金效率极高的企业。我做过一项简要分析：鉴于他们目前的体量——如果按季度乘以 4 计算，在 IPO 时大约达到了 700 亿美元的年化规模——考察其每单位年化收入所消耗的现金资本，在过去五到七年上市的任何具备相当规模的企业中，几乎没有任何一家能与之媲美。从收入年化运行率对应的现金消耗效率来看，大概只有 Airbnb 能勉强接近。从绝对金额来看，Anthropic 上市前烧掉的资金甚至比 Uber 当年上市时还要少；考虑到他们所创造的一切，这是相当惊人的成就。回过头来看，Meta 在 Reality Labs 项目上大概每两三个季度就要烧掉 100 亿美元，即使现在降到了每年 160 亿美元左右，每两季度也得烧 80 亿，每年持续消耗的资金体量非常庞大。
<details><summary>Original English</summary>
>> Yeah, I think like you know at various points across the last few months there have been all these leaks about you know roughly like their run rates and stuff. So I don't think like you know to me like it's kind of like those things were not as much of a surprise to anyone that's kind of been following this in terms of uh you know what to expect based on what has been publicly reported even before the S1. I think perhaps the biggest surprise to people was just around the cash burn of the business and and in I mean that in a positive way. So they they had raised like you know $140 billion of cash and literally like they still have on the balance sheet like 132 billion or so. And so they burnt like under $10 billion to get to where they have. And I I think it's like one no one I don't think other than you know obviously the people that actually knew the numbers from from being on the inside. I don't think anyone expected that they that the cash war chest that they had on their balance sheet was actually that large just based on uh you know based on expectations around the burn and the uh margins and things of of the business. And so it's actually been like a very very very efficient business. Um and um uh I I kind of had just did this quick analysis around you know given the scale they've gone to right which is you know roughly 70 billion at the time of you know if you do like the quarterly times four what's the capital consumed in terms of like the cash burn per dollar of kind of revenue run rate at the time of the IPO and there are very few businesses of any meaningful scale really that we've seen go public over the last five seven years that are anywhere close like I think Airbnb is probably the only one uh that that kind of comes close on a revenue run rate basis in terms of the cash efficiency in terms of the burn. And so I think this was something that was quite surprising. I think even from like an absolute dollar basis like I think Anthropic has literally burned like less dollars than Uber did to to get go like at the time when they went public which uh you know given what they've created with this is is you know pretty remarkable. Uh um and uh it's like you know the cash burn. I was thinking about this like like Meta is still burning like 10 $10 billion on their reality labs initiatives every like two quarters or so. Uh I think it's now down to like 16 billion a year. So maybe they burn like 8 billion but they're still burning every year. Way more absurd. [laughter]
</details>

>> 是啊，相比于这家从零起步、构建出长程智能体（long horizon agents）并在众多领域拔得头筹的公司，Meta 烧得太多了。等等，我原本以为他们会把那项开支压缩到零，搞什么鬼？
<details><summary>Original English</summary>
>> Yeah. Than like you know this company that got off the ground and like built like you know basically built like long horizon agents and like you know was the first of so many of these things. Oh, wait. I expected them to to take it to zero. Like, what the hell? [laughter]
</details>

>> 没有，他们仍然在巨额亏损。
<details><summary>Original English</summary>
>> No. Yeah, they still losing like to photo.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 什么？
<details><summary>Original English</summary>
>> What?
</details>

>> 就像是每造一副眼镜就要烧掉 100 万美元一样，太不可思议了。
<details><summary>Original English</summary>
>> It's [laughter] like they're burning like a million dollars per spectacle for glasses or something. Like, what the Like,
</details>

>> 这太疯狂了。所以我给 MSL 提的方案是：他们每年在 VR 上烧掉大约 200 亿美元，只要把这 200 亿砍掉转投给 MSL，就能拥有一个完整的云基础设施。他们现在确实有了，只不过因为财力太雄厚，他完全可以两者兼顾。
<details><summary>Original English</summary>
>> um that's that's crazy. So, so I expected so my my actually pitch for MSL was look the uh they were burning something like 20 billion uh per year uh on on on on on VR and you just cut that 20 and reallocate to MSL uh and you you have a Neol, right? Like like and which is they they now have it. It's just that his pockets are so deep that he can just do both.
</details>

>> 是的，他当时的态度就像是：“哦，我会投资那个，但我可能不会把这边的开支完全砍掉，而是慢慢来削减。”
<details><summary>Original English</summary>
>> Yeah. He was like, "Oh, I'll do that, but maybe I won't do the cut fully and like I'll slowly do the cut." Yeah.
</details>

>> 显然他乐在其中，享受生活。但这类智能眼镜与 Muse 相比根本不值一提。太搞笑了，真不敢相信他们每个季度还能烧掉 50 亿美元。
<details><summary>Original English</summary>
>> I mean, like clearly like he's enjoying it. He's loving life. Uh whatever. But like uh you know, these glasses are nothing compared to Muse, right? Um Yeah. So, uh it it's so funny. Oh man, I can't believe they're still burning five billion a year. Uh five billion per quarter.
</details>

>> 好的，这就是关于现金消耗的情况，我觉得这一点被低估了。这里没有呈现的一个数据是 OpenAI 究竟排在哪里，因为我们没有 OpenAI 的 S-1 文件。OpenAI 的效率要低得多，大概更接近 Snowflake、Cerebras 或 CoreWeave 所在的区间。之前流出过一些非官方图表，所以这并不是全新事实。如果密切留意泄露的 S-1 信息，会发现有人画过预测图表：Anthropic 处于相对稳健的曲线上，而 OpenAI 的亏损下探幅度要深得多。所以大家一直知道这种差距，只是不知道具体规模有多大。
<details><summary>Original English</summary>
>> Yeah. Uh come on. All right. So, that's the cash burn. You know, I think um that's something that um I feel like is underrated. Uh so the the one number that you're not seeing on here is where's OpenAI, right? Uh because we don't have the Open S1. Um it is way more inefficient. Uh it it is probably closer to like the Snowflake Cerebras Core Weave range. Uh and there have been unofficial charts. So this was this is like not a completely new fact. if people were paying close to the the leaked S1 where people were already drawing um charts like uh Enthropic was let's say doing uh was was was known to be doing like this uh as like a like a projection and then and then OpenAI was like kind of like way deeper and like yeah something like that. Um and so so this is a known chart that like we just didn't know how big it was. Um
</details>

>> 是的，我认为之前大家对具体差距的量级并不清楚。
<details><summary>Original English</summary>
>> yeah the I think the magnitude wasn't
</details>

>> 我把这归结于几点原因：首先，Anthropic 起步较晚，他们基本上跳过了 GPT-1、2、3，因为那是在 OpenAI 做的，那些研发成本是由 OpenAI 承担的。两家公司拥有相同的创始团队班底，他们已经在那里交过了学费，出来后可以在完全隔离的洁净室（clean room）环境中重构这些工作。但除此之外，Anthropic 为什么如此高效？这是一个非常缺乏深入探究的问题。部分原因在于他们现在的单客经济模型（unit economics）已经实现盈利，而且达到目前水平所消耗的资金并不多，这在科技界基本上是前所未闻的。
<details><summary>Original English</summary>
>> Yeah. Yeah. So, so, um, and I think I I attribute this to to a couple things, right? Um, Enthropic started later. So, they they they basically skipped GPT123 because that was done on Open Eyes. Um, and you know, that that R&D Yeah. It was done on their dime. It's the it's the same founding team. Um, so like they, you know, they they already paid the tuition there and then now they come out and and they can just kind of repeat that work from a a clean room perspective. Um but you know what else like what why is why is anthropic so efficient? I think that is like a really really um underexamined thing. Uh partially I think it's just straight up like there are now unit economics profitable uh which is cool. Uh but they also didn't burn that much to get there which is super unusual like like basically unheard of in tech.
</details>

### 毛利率与算力成本拆解

>> 是的。如果你看紧挨着下方的毛利率图表，这可能也与 OpenAI 形成了鲜明对比：Anthropic 始终聚焦于代码生成以及更广泛的企业级市场，策略是打造最顶尖的模型，主要通过渠道伙伴进行分发，并尽可能借助渠道伙伴获取算力。因为没有涉足大众消费级市场，他们不需要承担庞大的免费推断用户群，因此服务付费用户的经济模型表现非常出色。他们公布的最常见数据是 85% 的毛利率，其背后的逻辑是：针对付费用户的推断成本大约只占总收入的 15%。后面有一张图表对此进行了详细拆解，指出他们在付费推断上实现了大约 85% 的毛利率。但许多同行通常会把免费层级用户的推断成本归入销售与市场营销费用中，理由是这是吸引用户上平台的获客手段，后续转为付费再进行变现。有人或许会争论这部分是否该算入主营业务成本（COGS）。但关键在于，对于 Anthropic 而言，依靠企业客户和代码场景，且 Claude 并不像 ChatGPT 那样面向大众，从利润率和现金消耗角度看反而是优势，因为他们无需在免费方案上支撑庞大的用户池。他们大概只将 4 个百分点的利润率（相当于算力开支的 5% 到 6%）花在免费用户的推断上。我认为当 OpenAI 的数据公布时，考虑到其庞大的用户基数，这一比例会高得多。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. And and if you go to the the next the the chart right below around kind of gross margin I think and this also probably contrasts something with uh with open AAI which is that uh because anthropic focused and ended up focusing on coding and on enterprise maybe more generally and more just like let's have the best models and uh both on let's distribute primarily through channel partners but then also let's leverage them for compute wherever possible and they would didn't have this because they weren't trying to do consumer they didn't really have this like massive consumer base that they had to support uh with like you know mostly free inference. They the the economics are like very very uh positive for them on on kind of like you know on supporting like their paid users. And so I think the most common number like you know is like this kind of idea of 85% gross margins that they report and the way to think about that is that essentially like as a percent of revenue their like inference on paid users is about 15%. Uh and there's a chart further below that kind of breaks breaks that down. Um uh and so that you know they reported yeah they reported these like 85% gross margins on you know essentially paid inference. Uh but then you know one thing that a lot of these companies obviously have been doing is that there's these like free free free free tier users and it it's been common to put this into sales and marketing spend because you know you could argue that it's like oh it's our like it's how we attract users to a platform and then we monetize them with if they become paid and so they put that free tier inference in sales and marketing spend and so you could be like oh maybe that should go in cogs and but I think the point is that for Enthropic because you know they primarily relied on enterp price and on coding and claude is not as big as like you know chat GPT is from a margin perspective and maybe like a cost uh cash bone perspective that actually is a positive for you because you don't have this huge user base you have to support on on the free plan and so they only spend like you know only about like 4% of margin points or about like five six% of their compute spend ends up going on like this free user inference and so I think that's kind of like the other aspect of it I I imagine when the numbers come out for OpenAI that's going to be significantly higher just given the size of that size of that user base. Um
</details>

>> 对于任何免费层级来说，4% 都是非常小的比例。通常在分析 S-1 和投资时，人们往往直接将免费层级视为市场营销开支。
<details><summary>Original English</summary>
>> yeah for do we do we is four 4% is small right for any free tier. I I don't know how you you look at your other uh S1's and investing. Um usually free tier is like people just kind of treat this as marketing right like this marketing expense. Yeah,
</details>

>> 没错。这仅仅指算力消耗，虽然公开上市且提供包含算力免费计划的公司并不多，但核心在于他们没有把大量算力耗费在免费用户上。绝大部分算力要么投入到了训练与科研中，要么用于支持付费用户。回想一下 OpenAI 下架 Sora 的举动，我认为原因之一就是 Sora 没有明确的变现途径，同时消耗了极其庞大的算力；在没有真正将其打造成 AI 视频生成平台进行商业化的前提下，算力完全可以投入到更有产出的地方。在 Anthropic 身上你也能看到这种取舍。
<details><summary>Original English</summary>
>> exactly. And and so obviously this is specifically on the compute usage and so it's hard like there aren't that many companies that have like you know that are public that have like free user with compute plans, but I think essentially like they're not using up a ton of their compute on serving these free users. And so most of it is either being used for training and research or is being used to support these paid users which I I think like you know if you if you think about like you know remember OpenAI getting rid of Sora uh one kind of reason for that I think was just that it one it was obviously not really monetizing because it didn't intend to but it was such a use it was such a large use of compute that it was like you probably have more productive uses of that especially given that they weren't really trying to monetize it into some kind of like you know like AI video gen platform. form truly. Um, and so I think you see that with with with Enthropic.
</details>

>> 我觉得 Sam 一直想为 OpenAI 打造一个社交网络。如果你不是 Twitter，也不是 Facebook 或 Instagram，那你该做什么？做 AI 版 TikTok。这是一个合乎情理的尝试，只是没能成功。我觉得这值得一试。在这点上我更倾向于为 OpenAI 辩护：你确实可以在 B2B SaaS 或企业级代码领域深耕，但 AI 理应更广阔、更有创意，而不仅仅局限于帮人们写代码。因此我支持 DeepMind 和 OpenAI 去做那些不局限于日常工作的探索。
<details><summary>Original English</summary>
>> I I think there was a case for, you know, Sam has always wanted to build a social network for OpenAI. And what do you do if you're not Twitter, you're not Facebook or Instagram. You do AI Tik Tok, right? Um, and that was a reasonable bet and it didn't work out. So, I don't know. I I think it was worth a try. I actually like I'm kind of like an open AI defender here in terms of yeah you can do coding in B2B SAS or enterprise but like you know AI is supposed to be a bit more broad and creative and weird than just you know we help you code better. Um and so I I you know I defend like the deep minds and the the opening eyes for doing things that are not you know just work.
</details>

### 代码场景之后的新增长曲线与安全需求

>> 是的。Anthropic 的成功部分归功于它的专注，这为他们带来了巨大助益。但人们普遍存在一个疑问，从数据中也能初见端倪：第二季度是一个具有跨时代意义的爆发季度，折合年化运行率增加了大约 250 亿美元；然而到了第三季度增速明显放缓，季度环比增长从超过 100% 回落到了 40% 到 45% 左右。人们开始讨论：那是否只是极致消耗 Token（token maxing）的季度，由于当时其他家在代码以及长程推理模型上尚未跟进，Anthropic 借此吃下了所有潜在市场份额？如今大家都追赶上来了，开源权重模型也很强劲，单纯刷 Token 的阶段正在过去，大家都在讨论跨模型路由（routing across models），在缺乏下一条增长曲线的情况下业务增长可能会受到冲击。我认为这确实是一大潜在风险。不过考虑到核心技术在当下的渗透率依然很低，风险可能没有想象中那么致命。但大家都在探寻：在代码之后，是否会出现另一个体量相当的场景，让大批用户愿意为了这类用例每月花费 8000 到 10000 美元来购买 Token？梳理各细分领域的匹配度，代码显然排在首位，其次是客户支持和法律场景。另一个正在兴起的方向是安全领域，X 上对此有诸多讨论，探讨明年 Token 消耗中会有多少比例流向安全。各大实验室在某种程度上制造了安全问题，却也提供了解决方案：攻击者如今能获取各类模型发起攻击，最近一系列攻击事件已经显现出端倪；而经过剪裁（ablated）的模型也能被深度利用。因此我认为安全是一个极具潜力的消耗大户。此外，他们在长远规划中多次提及科学与生命科学领域，希望借助模型推进药物研发等探索，文件里也提到了他们的湿实验空间（wet lab space）。
<details><summary>Original English</summary>
>> Yeah. And I think it's one of those where I think that's the Anthropic has worked partially because of its focus, right? And and if you see where they've gone to that that that's helped them a lot. But as you think about uh one big question that people have and you kind of start to see it in some of the numbers is that hey like Q2 was this like generational quarter for y'all where yall added like you know like 25 billion of like you know like on an annualized basis of like run rate revenue and already you see like a a decline in Q3 both like a massive slowdown where you went from like you know over 100% quarter over quarter growth to like 40 45% or so quarter over quarter growth but then also you ended up um now that the people are like oh was at just the quarter of like max token maxing and peak kind of like entropic share because no one else had caught up on coding and on like a good like you know like reasoning model like a long horizon reasoning model and you just basically captured all of that that market available and now everyone's kind of caught up now open wave models are strong token maxing is ending everyone's talking about like you know routing across models and so you're going to suffer from that without maybe that next leg to go on and I do think that is parti actually one of the risks I don't think it's as big as that in the sense that it's we're so we're still so underpenetrated in terms of just diffusion of you know this core technology that's already available to us but I do think there is this big question of what is is there going to be like the next thing off to coding that is like actually the size of this of coding where um someone you can imagine like mo some large base of people are spending like $8,000 a month or $10,000 a month on kind of tokens off that kind of for that kind of use case. Um it to me I think what the the if you think about just like you know product market fit of various segments like obviously I think coding is number one. I think customer support legal have probably been some of the others. I think the the one that seems to be coming and there have been various debates on X about like you know what percent of token use next year is going to be on around security. I think that could be another one where in some ways these labs have kind of created the problem but then also offer the solution where now attackers have access to all these models and can kind of go ham on on these. And I was starting to see some of this play out, right, with some of the PHP stuff and then just like more and more of these hacks happening and you know some of these like um the models that are like uh um ablated and like that allow you to kind of really uh use these and so I can't I I I see that as like a promising area in terms of like you know what's that what's another like massive source where like a lot of tokens can be used. Um uh but then I think what they talk about a lot uh for long term is around like science and uh uh uh life sciences and uh you know let's uh maybe use these to start doing things drug discovery and and all of those things. Um and and they touch on like you know some of the uh the wet lab space they have and and and those things as well.
</details>

>> 好的。我们把湿实验室的内容留到最后，因为那是较新的探索，且我们掌握的细节相对有限。除了这些核心财务指标外，还有什么让你感到意外的吗？
<details><summary>Original English</summary>
>> Right. Right. Um we we'll leave the weblab stuff to the end because obviously that's like newer and and less um uh we honestly just have less details about it. Um what other what like Okay, so you know we've talked about a lot of the headline financial things. Um what you know what really surprised you? What else?
</details>

### 研发算力占比与数据采购开支

>> 就我个人而言，训练和研究占用的算力份额依然相当高，这让我很吃惊：他们大约将 70% 的算力用于训练和科研，只有约 30% 用于推断。这令人感到意外：一方面意味着他们的推断效率极高；另一方面，去年初推断算力占比曾经是 50%。
<details><summary>Original English</summary>
>> Yeah, I mean I personally was pretty surprised by in some ways the the share of the compute that was on training and research still like like you know it's basically they're using about 70% of their compute on training and research and only like 30% is going towards inference and that I think we're surprised both one that just means you know [laughter] the inference is very efficient so like you know it's going right it it was 50 at at uh at the start of last year
</details>

>> 没错。他们确实把推断效率压榨到了极致。对于 Anthropic 这种规模的企业，如果今年所谓的推断成本只有大约 100 亿到 120 亿美元，仔细想想是不可思议的。这甚至会让人对目前一些大规模算力集群建设的必要性产生一丝疑问。虽然整体上看行业仍处于极早期，但他们达到了这样的规模，每年却仅需消耗 100 亿到 150 亿美元的推断算力来支撑，这确实超出我的预料。另一件让我意外的事是关于数据的支出。文件里虽然没有单列，但给出的数据足以让你拆解出数据采购的费用。直到最近一个季度（大约一周前通过修正文件披露）之前，我测算其年化数据开支大约在 9 亿到 10 亿美元左右，考虑到硅谷有那么多公司在兜售针对细分领域的 RL 环境等各种数据，这个规模实际上相当小。不过在 6 月至 9 月的季度中出现了一次大幅跃升，当季数据支出约为 6 亿美元。这表明他们近期大幅增加了数据采购，目前年化数据开支已接近 20 亿到 25 亿美元。有意思的是，业界近期对向企业采购运营数据以及通过数据经纪商获取真实公司数据的兴趣重新升温。这表明目前依赖强化学习（RL）环境、后训练（post-training）以及在各个垂直领域进行强化的范式正在发挥作用，且取得了良好成效，促使他们持续扩大在各类数据上的投入。从比例来看，数据开支大致相当于算力支出的 5% 到 6%，上季度则从约 4% 跳升到了 6%，这也是未来值得保持关注的一点。
<details><summary>Original English</summary>
>> exactly and so I think they're really squeezing inference efficiency out which to me I mean if you think about it right a business of the scale of anthropic if if their quote unquote infer inference costs are only like call it like 10 billion this year maybe like10 to 12 billion a year that's kind of crazy if you think about it like and it it does make you question a little bit about like some of these sizes of these builds out build out more now again we're still very early in aggregate but the fact that they've gone to this scale and they're only spending like you know 105 billion a year on on inference to support that size. I think that that was surprising to me. Uh I think the other piece of it was that um they kind of they didn't technically do this, but they vaguely gave you these numbers that let you break out like the data the spending on data. And even that to me was surprising in that it was until this past quarter, which they only kind of published through the amended filing like a week or so ago. It my best estimate on it was it was like about like 900 million or a billion of run rate spend on data, which I thought was actually quite small. given that you consider this how many of these companies are in there in Silicon Valley selling like various forms of data like RL environments of all these different niches and the scales that like you know that so many of them are at uh and so that was surprising to me. I think the one thing you did see is that there was at least if you on a quarterly basis there was a big jump to I think they spent about 600 million or so in the June to September quarter on on data and so it seems like they have very recently ramped up this spending quite a lot and so today you could argue they're you know now spending close to like two two and a half billion a year uh run rate on data. Um, and it it's interesting because now it feels like, you know, there's been this renewed interest in all these like buying operational data from companies and like these data brokers that are helping get like real company data onto people. So to me it's a sign that like this the this kind of RL environment paradigm we've been in and like just like post training and using RL to keep scaling across every one of these domains uh is working and they're seeing good results from it and they're continuing to ramp up their spend on on on that across all these forms and so I I thought that was interesting well and it roughly the spend on data has more or less been you know like five to six% of their spend on compute over time although it it kind of did have this jump as I mentioned in the last quarter from like and so it went from like 4ish% compute to 6%. But I think that that's another thing to watch.
</details>

>> 我也在关注这一点。你认为将数据支出按占算力的百分比来衡量合适吗？
<details><summary>Original English</summary>
>> Yeah, that's something I've been I've been tracking a little bit. Um do you think that scaling it by percent compute is the right way to do it.
</details>

>> 我并不觉得这是最好的方式。一方面应该直接关注绝对数值；另一方面，由于数据是模型训练的核心输入，将其作为训练和研究算力的占比来衡量或许更具参考价值。此外，上述数字仅代表外部采购支出，Anthropic 内部很可能还有规模庞大的合成数据（synthetic data）生成工作，这部分成本通常直接被计入训练和科研算力当中。
<details><summary>Original English</summary>
>> Uh I I I don't think so. I mean I think like one is just like what's the absolute number and like let's talk about that. I think but if you think about if you think about it as like it's it's ultimately a core input into training maybe percent of training compute could be a good like percent of compute that's going on training and research the other thing that's not captured in this is that this is the spend on external vendors that I my guess is there's also a sizable just like or not my guess but there is a sizable synthetic data effort internally as well to synthetically generate data that is probably just getting captured in training and research compute uh uh uh uh um as well. Uh and so so that that is like you know the other aspect
</details>

>> 他们还会购买书籍并进行处理。
<details><summary>Original English</summary>
>> they're also buying books and uh destroying them.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> S-1 利润表中有一个季度的单独行项目记录了一笔和解金。
<details><summary>Original English</summary>
>> Yeah. And so I think this was the they had the separate line item in the for one of the quarters in the S1 for this the settlement that they paid for
</details>

>> 那笔 15 亿美元的支出具体是什么？
<details><summary>Original English</summary>
>> 1.5 billion. What was this?
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yeah. Exactly.
</details>

>> 我之前没有展开讲，但它似乎被称为 Books 和解案。利润表中为此单独列出了一项支出。我觉得这件事情耐人寻味的地方在于，引发诉讼并被罚款的原因，并不是他们合法购买并使用的那部分书籍，而是因为他们同时通过种子网络（torrent）下载了大量未付费的内容。核心问题不在于使用了买来的书，而在于混入了未经授权的内容。如果他们当初把所有书都买下来，或许就不需要支付这笔和解金了。
<details><summary>Original English</summary>
>> Yeah. I I didn't touch on it but it's I think it's called like the bots settlement or something. And so they in one of the quarters there's a separate line item on the in the income statement for for specifically that. Um, and the thing I found funny with the whole uh with that whole thing was that the issue was not that they uh or the things that they ended up getting uh fined for, I believe, was not the ones that they actually bought, but that they tormented a bunch as well. And so it was that not that you actually used it. You bought some and you used it, but was more that you there was some that you didn't pay for which you used. And so if they just like bought all of them, I think you may not have had to pay the settlement.
</details>

>> 关于这个背景我知道一些内情。这大概源自 Books3 数据集。GPT-1 和 GPT-2 最初是在名为 Books1 和 Books2 的数据集上训练的，那些是版权明确的书籍。后来开源社区的一位开发者（如果没记错的话好像叫 Shawn）觉得这个主意很好，于是制作了一个包含《哈利·波特》等真实图书的、版权严重违规的数据集，并将其命名为 Books3。Books1 和 2 拥有合法的版权许可，而 Books3 显然没有。然而 Books3 在模型训练圈内被广泛引用和采用。我不确定 Anthropic 是否是因为 Books3 惹上麻烦，但性质十分接近：某人将未经授权的内容打包到了语料库中，最初研究人员只是在学术项目中使用，大家并不以为意；但如今用于商业化模型时，这个决策最终付出了 15 亿美元的代价。
<details><summary>Original English</summary>
>> So uh I have a tiny bit of context about this. Uh this is actually probably from books three. Uh I don't know if you know the context cuz this is kind of deep lore and I can cover it briefly for people who are interested. Um so basically GPT ones and one and two was trained on this data set of books one and two and it it's literally called books one and two. You can go look it up. These are sort of uh copyright clear books. Now uh a random person uh I forget his name now. I think like his name is Sean as well and just from like nowhere just like open source AI person goes like hey books one and two are really good idea uh let's keep going and so he like creates a very very illegal data set of like actual books including like Harry Potter and whatever and calls it books three right uh you you can call things whatever you want but clearly you know books one and two were like official copyright clear books three was not books three but how however books three was like it's like pretty widely cited or used uh in in the model trading circuit. So um I don't know if enthropic was exactly caught by books three but it's going to be something like a books three where uh it was included by somebody in some corpus that was just like okay like you know researchers got used to training on this for like an academic project where it didn't really matter but now it matters for topic and so this decision cost 1.5 billion.
</details>

>> 是的，经此和解之后，他们必然会更加谨慎，并对其训练集的来源进行更严格的溯源审查。
<details><summary>Original English</summary>
>> Yeah. And I'm I'm sure after that settlement they they're going to be a lot more careful and they have much better prominence on everything else that goes into their training uh training sets.
</details>

>> 我原本认为这场争议应该上诉到最高法院，虽然最终并没有走到那一步。这本可以被探讨为“转换性使用”（transformative use），毕竟我们使用的模型架构本身就叫 Transformer。如果我去读了《哈利·波特》，凭借过目不忘的记忆力在别处默写出来，人类的大脑会因此违法吗？模型在本质上也是类似的运作逻辑。当然，因为涉及机器且大语言模型有时会被视作数据库，情况显得更具争议。但我确实认为，在对待人类与对待 AI 之间存在着某种双重标准。
<details><summary>Original English</summary>
>> I mean so so that was the whole uh discussion that I think should have gone to the Supreme Court. It did not. Um I think yeah I don't I don't think it went to Supreme Court. Um but uh it could be transformative use like we literally call it transformers, right? like like we we are I am allowed to go and read Harry Potter and like maybe I have a perfect memory and I can go somewhere else and write down word for word Harry Potter from memory. Is my brain illegal? Like [laughter] like that's that's like effectively what we're doing. Uh you know just because there's there's machines involved and you can kind of view LMS as databases like maybe that that's like a bit more questionable there. But um you know I I do think that there's some amount of dual standard or double standard when it comes to treating humans versus treating AI differently you know.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 无论如何，这些是眼下的趣味话题。
<details><summary>Original English</summary>
>> Um anyway fun questions for now.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 产品形态与收入渠道结构

>> 我经常向人们追问的一点是：Claude Code 贡献的收入占比到底有多大？我们是否应该在乎这个？以往他们披露过“Claude Code 创收 10 亿美元”、“Claude Code 创收 20 亿美元”，最后一次更新是在今年二三月份达到 20 亿美元，之后就停止披露了。通常当一家公司停止披露某个指标时，人们会假定数据表现不佳。但事实是，Claude Code 作为独立的 CLI 工具形式已经淡出，它被整合进了 Claude Tag 和 Claude Cowork 中。在 S-1 列出的 4 款产品中，有 3 款都是基于 Claude Code 构建的。因此可以说，Claude Code 支撑的收入可能达到了 500 亿美元。这也是大家一直在争论的问题之一。
<details><summary>Original English</summary>
>> Um so so yeah I think the other thing that I always press people on is like what percent is cloud code? Do we care? You know we used to have these disclosures of like oh cloud code is like 1 billion in revenue. CL code is two billion in revenue. The last update we got by the way was two billion in February or March of this year and then they stopped reporting right. So when people stop reporting usually you assume the number is bad. Um but the the truth is that cloud code as a CLI stopped being a thing like it basically just got adopted into cloud tag and cloud co-work and you know now like three out of the four products that they list on the S1 is like cloud codebased things. So like arguably cloud code is responsible for I don't know like 50 billion in revenue. [laughter] So I I I don't know if that matters. I you know it's this is one of those things that like people debate.
</details>

>> 是的，我也希望能看到他们第一方应用贡献的具体收入比例，尽管他们并未单独披露，这也可以理解。
<details><summary>Original English</summary>
>> Yeah. Yeah. I think like the other thing I I would have liked to see but they did not disclose which I don't fault them for not doing so is that what percent of actual revenue is coming from you know like these first party applications that you've built on top like the true like you know like like like the actual like you know the end of like versus like you know someone yeah or just
</details>

>> 或者说任何直接使用服务的人。单纯通过 API 调用模型，与使用 Claude Cowork 或 Claude Code 这类构建了额外抽象层的终端产品截然不同，后者能建立更高的客户留存壁垒。
<details><summary>Original English</summary>
>> or or just anyone using your if they could use it directly from you but like like a hobby using you and their AP like via an API is pretty different than a consumer using like cloud co-work or cloud code or something where you kind of have like one more level of uh um abstraction that you've kind of built which allows you to like you know arguably have a little bit more of uh retention over time and the reason I say that is like a few things so one is so
</details>

>> 没错。目前我们知道大约有一半的收入来自渠道合作伙伴，这个比例近期略有下降，目前约为 44%。审视其主要成本项：首先是已经谈到的算力；其次是人力，得益于效率的持续提升，人均年化收入已经从 100 万美元左右攀升至 600 万美元，人力成本占收入的比例不断走低；第三项是销售与市场开支，但这主要并非用于品牌推广，而是向渠道合作伙伴支付的分成费用，约占合作伙伴为其带来收入的 30% 到 35%。另外一项重要披露显示：他们约 80% 的模型使用量（或大部分收入）均来自于最近 6 个月内发布的模型。由于大部分收入来自按量计费而非订阅模式，这导致了一种独特的动态格局：公司绝对不能在模型前沿上掉队，否则就会置巨额收入于险境。设想如果他们因为某种原因掉队了 3 个月，而 Gemini 或 OpenAI 发布了非常出色的新模型，Anthropic 最强模型依然停留在 Opus 5.5，那么在 API 接入层，客户可以极其轻易地完成模型切换，从而导致市场份额和收入的骤降。从商业策略角度来看，这也是为什么他们需要尽可能吸引用户使用其第一方应用：如果你习惯了使用 Claude，并且设置了大量定时任务，即便它在技术上短暂落后几个月，你也不太可能全盘迁移至 ChatGPT；但如果只是纯粹的 API 调用，当模型落后时客户流失的速度就会快得多。这使得厂商陷入了一场永无休止的竞赛，不仅必须保持在前沿，还必须在整个性价比曲线上处处维持竞争力。
<details><summary>Original English</summary>
>> we do know for for example that about half their revenue is coming from channel partners I think that's actually now going down slightly it was on the way up I think it's now down to 44% it's coming from these channel partners and that they rough roughly are paying if you think about like the big cost right it's pretty much compute which we've touched on people which again is is as a percent of revenue just keeps going down because they are getting more and more efficient I think the revenue per employee is now up to like six million per per year from like from a million or something um and then the third is this kind of the sales and marketing but most of it's not like you know brand building sales and marketing it's like these the fees that paying these channel partners which is about 30% of the revenue 30 to 35% of the revenue that those channel partners are getting for them. Um, but I think the other reason this important is that they disclose that about 80% of their uh most of the model usage uh or most of their revenue comes from models that were released in the last 80% of the usage comes from models released in the last six months. And I think what that the dynamic that kind of ends up creating especially when you add to that fact that most of their revenue comes from usage based plans or from usage based pricing as opposed to like you know subscriptions is that you can't fall behind at all or you you you kind of are putting like a large percent of your revenue at risk. So like if like and I think it would be hard for this to happen but if imagine like for whatever reason like they just fall behind for 3 months and you know there's like you know Gemini's new model is very good, open's new model is very good and um and Anthropics is just like slightly behind for a reason and it's like you're still using Opus 55 is the best that they have and the others are further ahead. you could find yourself in a scenario where because people are just kind of using you at the API layer in some system where they can easily just swap you out that you have lost a lot of shareh suddenly and lost a lot of revenue and so I think that's like a tricky place to be in and so from a company strategy perspective I think you know the more they can get people to use your apps like if you're using you know claude you're not going to switch of like or switch all everything over to chat you might have a bunch of scheduled tasks and you won't do that switch if like you know it's behind for a few months or something but if it's the more it's just APIdriven usage the more risk there is of just people uh you know just like the revenue can go away more quickly as well and so I do think that that is one of the things where you're in this game where you just always have to stay uh and not necessarily at the frontier but also just at the like at every point of the price performance globe that kind of matters from a usage and workload perspective.
</details>

>> 这个总结非常到位。自 S-1 文件发布以来已经过去了几周，发生了很多变化，目前追踪到的 IPO 发生概率大约在 50% 多。眼下这个关口究竟有多关键？如果不推进 IPO，抑或上市之后股价破发，这会是世界末日吗？还是说即便脱离二级股市，只要坚守基本面也能平稳运转？
<details><summary>Original English</summary>
>> Yeah. Amazing. Um I I think that's that's a really good recap of of the state of things. Um okay, so it's been it's been a couple weeks since the S1. Um a lot has changed. Uh we are now tracking um what is it like 50 something% uh probability of IPO? How critical of a moment are we in whether this or not this happens or not? Right. Um if if they don't IPO, is it the end of the world? If they if they do and it still flops, is that the end of the world or is there no end of the world and actually just keep on the fundamentals, screw the forget the stock market?
</details>

### 上市时机窗口与生态流动性

>> 我认为早上市总比推迟要好，哪怕这意味着要承受 10%、20% 或 30% 的估值折让。无限期推迟可能会比以 1.25 万亿代替 1.5 万亿估值上市引发市场更多的恐慌与不确定性。另一个关键原因在于：整个科技生态系统中沉淀了极其庞大的流动性诉求，全维系在这批领军企业的 IPO 之上。SpaceX 已经迈出了这一步，而后续许多超大规模融资轮次、新型算力实验室（Neolabs）以及算力基建生态的持续运转，都依赖于这些标的上市为风投界及其背后的受限合伙人（LPs）提供退出流动性，从而让 LP 有资金再投给新一期 VC 基金，进而投资下一批创业企业。因此从全局来看，尽早上市非常重要。虽然推迟到 1 月而非 11 月不至于带来毁灭性后果，但我认为从大局出发，赶在 11 月底前上市或许优于等到新年之后，哪怕估值打些折扣。因为公司的基本面很强，而且它大概率会早于 OpenAI 敲钟。在同比增速依然保持惊人倍数的年份尽早挂牌非常必要，因为潜在的风险在于，未来如果出现个别月份环比负增长，很可能会引发市场过度的恐慌。在目前月环比仍能维持 5%、8% 到 10% 增长的阶段挂牌是最理想的。虽然大家不会仅仅将 100 亿到 1000 亿的跨越视作理所当然，但过去几个月增速逐渐放缓也是事实；鉴于其现有规模仍能保持如此亮眼的成长速度，他们应该抓住当前的窗口期完成上市。
<details><summary>Original English</summary>
>> I think that my my guess is that it would probably it definitely would be better for them to even go out sooner rather than later even if that means like you know 10 20 30% like a lower valuation. uh in that like like you know indefinitely delaying it might actually lead to more fear and uncertainty than just like you know going out at like 1.25 instead of 1.5 or whatever that ends up being. Um I I think the the other reason this ends the probably the area this also ends up mattering in is just that so much of liquidity in the in the ecosystem rests on you know these the IPOs of some of these these companies and SpaceX has is the one that has gone out and I think a lot of the continued funding of these very large rounds like you know it's like whether it's like these Neolabs and some of the other like you know like the comput buildout and ecosystem stuff also just relies on hey like these things actually going public and providing liquidity to uh the venture community and then to the the RLPs which then allows them to invest back in the next funds of the VCs that then allows them to invest in the next set of companies and so I do think from that perspective as well it is it is important now I don't think it's going to be the end of the world if it happens in January instead of November but I do think like you know like it probably from an aggregate perspective and I I I wonder what the what the anthropic things, but it might actually be better to go out now like you know like before the end of November as an example than maybe wait for the new year even if that does mean a a slight like kind of discount on the valuation. Um uh yeah cuz I I do think that the fundamentals of this business strongs I don't think I still think it will be the first of the uh between like it will be it'll be easier for them potentially to go out than it would uh and open AAI and I think if you're if you're anthropic you probably still want to go out in this this year you've had where you're still growing like you know at least like on a year-over-year basis like this uh enormous amount because I do think what what they what the risk for them is that you could have like some month where you have like some negative month overmonth growth and then that could actually freak people a lot. Um uh and so you want to go out while you're still growing this you know 5 10 8% a month and uh uh uh um and already like people aren't viewing this as oh you went 10 to 100. I think that is true and they likely will go 10 to 100 but there's also the well in the last three four five months you actually you know your your grow your the growth is declining and so but it still is growing at amazing pace for the the scale it's at so you still want to kind of get out in in that period um um I think
</details>

>> 是的，短期看无论是这个月还是下个月，只要在未来半年内完成，差异可能只是四舍五入的统计波动。我平时经常接触开发者、工程师和科研人员，他们也在问我：估值既然已经达到 1.5 万亿美元左右，那么接下来的 2 倍、5 倍在哪里？未来是走向 3 万亿、7.5 万亿还是 10 万亿美元？这是巨大的未知数。在经历过去一年的暴增后，未来的持续成长空间在哪里？这也是我一直想强调的：他们正在试图讲述长远增长的故事，也就是智能体——在 S-1 文件中被称为“虚拟协作者”（virtual collaborators）。这正是大家必须去评估的下注方向。显然 S-1 文件除了展示近期的财务表现和风险考量外，不会过多断言远期发展。
<details><summary>Original English</summary>
>> yeah you know like uh look there's the short term like you know is it this month is it next month like look if it's within the next like six months like where you know we're mostly it's like rounding error um when employees are I think they, you know, I I talk to developers and engineers and researchers all the time and they're asking me like, look, okay, it's 1.5ish. Um, and so now now they're looking for the next like 2x, the next 5x, right? Like is it three 3 trillion? Is it 7.5 trillion? Is it 10? And um that's really like the big unknown, right? They had this big jump in the past year plus. Um what is the ongoing prospects, right? And so, um, that's the other thing I I really want to emphasize, which is like they're trying to also tell that story about what's the long-term growth. It's basically agents, uh, they call it virtual collaborators in the the S1. Um, you know, it's and that's a that's a bet that you have to take, right? Like obviously the S1 is not going to tell you anything beyond like recent financial performance and maybe some risk discussion, but that's about it.
</details>

>> 是的，大家一直在探讨企业未来在 Token 上的合理支出规模到底是多少。人们对此会有自己的判断，进而评估 Anthropic 在其中的市场份额，以及如何依据自身在前沿技术的站位和盈利能力来进行变现。文件里有几个很有意思的统计数据：其一，目前财富 500 强企业中只有大约一半在 Anthropic 年支出超过 10 万美元；这意味着剩下的 250 家企业年支出竟然还不到 10 万美元，这让我觉得不可思议。其二，在那些年支出超过 10 万美元的客户群中，Anthropic 的账单金额还占不到这些企业总运营支出的 0.1%。随着时间推移，企业在 Token 上的开销占其运营费用的比例到底会达到多少？各家观点不一，但在我看来，未来三到五年内达到几个百分点是完全可能的，甚至这个估计都偏保守。单凭现有的业务基础推演，未来就存在 10 到 30 倍的潜在增长空间，甚至不需要底层智力水平出现巨大跃迁，更多是靠解决所谓的“扩散鸿沟”（diffusion gap）或“能力悬置”（capability overhang）。随着这些问题的解决，Token 的使用量必然会持续爆发。但紧接着面临的问题是：如果大部分场景根本不需要最顶尖的前沿模型，这些需求是否会分流至价格战激烈的开源权重模型？相比大家愿意支付高溢价的前沿模型，开源模型的利润率会低得多，而前沿模型的应用范围可能仅局限于企业级用例中的较小一部分。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah, I think this this idea I think this question that people have been debating around what is the right amount over time for a company to spend on kind of tokens and and and and because I think it's like you know you people will have a view on that of like how big is this kind of spend on tokens going to be and then they'll have a view on like what is entropic share of that going to be and then like how is that going to monetize based on where you are in the frontier or like you know the profitability of that. I think other than stat that was interesting from there one was that only today only about half the Fortune 500 spend over a 100k a year on entropic. So I was just wondering like what what are the other two like how are there like still 250 companies in the fortune 500 that aren't spending 100k a year on entropic like that's kind of crazy to me. Um and then the other one was that like off the ones that are spending this over 100k. off that first set. Uh, Enthropic is is under 0.1% of their like aggregate expenses. And so it's like there, you know, you would think that everyone has different views on this, but what is token spend as a percent of opex of expenses for these companies over time going to be? And it's obviously going to vary depending on the kind of company you're in, but my guess is that at least it's going to be like, you know, in the few percentage points and even that could be like, you know, under counting and I'm talking about like, you know, three, five years from now. And so there's probably like a 10 to 30x if you just think about it on just what you're doing now. Even without that much further, you don't need like you know the intelligence to get smart. It's more maybe just the things around it and the actual like you know this this idea of the diffusion gap or the uh uh capability overhang that people talk a lot about. I think as that gets addressed I think this the token usage should just continue to grow. But then I think then the other questions become like okay like what is the if most of the you said you don't need these like the frontier models for will more of that go to open weight will more of that will will the margins on those be low because they're much more price competitive versus like the frontier models where you know people are willing to pay higher prices and stuff and but those might only apply to a smaller set of the use cases than than like you know everything and that's being used in the enterprise.
</details>

>> 讲得很好。接下来我们对更广泛的行业生态做个盘点，最后再收尾在湿实验室和前沿科学。对于新型实验室（Neolabs）和新型云厂商（Neoclouds），你目前更看好多头还是空头？
<details><summary>Original English</summary>
>> Yeah. Yeah. That's great. Uh, cool. Uh, I'm going to play a little bit of like a read around the broader ecosystem and then we'll end with the wet lab stuff and the science stuff. Um, does are you bullish or more bullish or more bearish Neolabs and Neo clouds? You can you can sort of interpret that either way.
</details>

### 新型云厂商、开源推断与利润率侵蚀

>> 考虑到一些估值回调，如果以平均水平来衡量，我对新型云厂商更偏向乐观。如果把新型云厂商组合与新型实验室组合放在一起对比，未来可能会有一两家新型实验室脱颖而出成为超巨型企业，拉动整个实验室组合的收益超越新型云厂商；但如果只看普通样本，持有新型云厂商的表现很可能会更好。更何况许多新型实验室最终会蜕变成新型云厂商，因为它们已经锁定了长期算力承兑合约，一旦在应用端找不到高产出的业务支撑，就只能转做底层算力分销商。
<details><summary>Original English</summary>
>> I I think that a at the current pricing of the NeoClouds post some of this uh dips and stuff probably more bullish on th those ones from like a from if you were just to take like the average one like how that'll turn out. I think if you were to take like a basket of like the Neoclouds versus the Neolabs, I think what's going to happen is that you might you may end up having one of one or two of these Neolabs becoming extremely extremely significant companies. Uh and so I think that basket will may end up like outperforming the Neocloud basket. But if you just take like your average one like you definitely are better off with the Neoclouds, I think. And [laughter] I think the other thing is like many of these neolabs will end up being the neoclouds because they've already bought the compute and if they can't find a productive use for it, they end up
</details>

>> 没错。它们多数都以各种方式锁定了长期算力，如果找不到高效的使用场景，最终只能转型成为算力供应商。
<details><summary>Original English</summary>
>> Exactly. Yeah. Yeah. Because most of them I think ended up, you know, ended up basically like securing like long-term compute in one way or the other. And so now they could end up if they don't have a productive use for it, then they'll end up being the the supplier of it.
</details>

>> 是的，沦为新型云厂商确实是新型实验室的一种常见失败模式。
<details><summary>Original English</summary>
>> Yeah. I mean that that's the you know that's the failure mode of a neocloud um or neo lab is to become a neocloud that's for sure.
</details>

>> 确实。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但在推断的盈利能力方面，我们目前已经有了几个确凿的数据点：Anthropic 的推断十分盈利；DeepSeek 也发布了推断技术栈，公开表示利润率在 80% 左右。
<details><summary>Original English</summary>
>> Um but I do think like just in terms of the profitability of inference we have now have a couple data points of how profitable anthropic inference is how profitable deepseek inference is because they released the deepse inference stack [clears throat] and they they said it's something like 80 something%.
</details>

>> 这使得新型云厂商在整体上更具投资吸引力，不仅因为 Anthropic 证明了推断的暴利，而且 DeepSeek 最顶尖的技术栈是开源的，任何人都可以买下一机架的 GB300 自行部署。当然实际操作不会这么简单。
<details><summary>Original English</summary>
>> Yeah. So like I think like that should make all neo clouds just gener generally more uh interesting as an investment because not only do we know that anthropic is um profitable but also the state-of-the-art stack with Deepseek is is open source and so you can just buy a rack of GB300s and go nuts and obviously it's not that simple but
</details>

>> GPU 的回本周期并非 10 年，也不是 4 年，甚至可能连 3 年都不到，可能只需要 1 年。
<details><summary>Original English</summary>
>> um you know like the payback period for a GPU is not 10 years it's Not four years, it's not maybe not even 3 years, it might be a year.
</details>

>> 是的。SpaceX 在其财报电话会上就曾表示，其硬件基础设施的投资回报周期甚至不到一年，这相当惊人。
<details><summary>Original English</summary>
>> Yeah. Yeah. Uh yeah, [laughter] I think SpaceX SpaceX on their owning squall said that they're seeing the sub sub oneear paybacks on their on their buildouts, right? Which is which is kind of crazy.
</details>

>> 那么大家为什么还会持怀疑态度？如果这些完全属实，市场为什么会疑虑重重？这可能并不是全部真相。毕竟债券市场聚集着全世界最精明的投资者，他们做的尽职调查最为严苛，而他们正在全面上调针对这些公司的借贷利率。大家之所以只能去股权市场融资，正是因为在债务市场借不到钱。
<details><summary>Original English</summary>
>> So So then like why are people skeptical? Like why why are people like why why is if that is actually true? So that this it's probably not true. And the reason is the debt markets are the smartest people in the world, right? They do by far the most due diligence and they are hiking interest rates on all these guys, right? The whole reason we're raising equity is because you can't raise debt.
</details>

>> 在我看来，一个很重要的维度在于当前市场处于严重的供需失衡期，大家对于这种失衡何时能够出清持有不同预期。此外，如果你审视 Anthropic 的推断数据，在稳态甚至当前环境下，普通的开源模型推断市场（仅仅为开源模型提供托管服务的模式，比如规模化运营的 Fireworks 或 Baseten）很难在长期内维持类似 Anthropic 那样的超高推断利润率。因为模型对所有人都是公开的，永远会有厂商为了争夺市场份额而打价格战。观察 OpenRouter 的现状非常有启发性：无论是 Kimi K3 还是 GLM-53，原厂给出了官方定价，但平台上往往有五到十家第三方服务商以原厂 20% 甚至 10% 的极低价格提供服务，直接便宜了 10 倍。尽管它们目前体量较小，但只要你定价过高，且开源许可证允许，新入局者完全愿意以 10% 到 20% 的微薄毛利率来卷低价格以掠夺份额。我不认为基础开源 Token 推断服务商的长期利润率能维持在 40% 以上，这也是为什么众多厂商都在积极发力后训练（post-training）和模型定制服务——定制化能形成更高的业务壁垒并绑定更独特的模型，从而在进一步优化效率的同时获取更高的利润空间。
<details><summary>Original English</summary>
>> I don't know. I to me I think one aspect of this is that obviously we are in this moment in time where definitely there is this you know imbalance of supply and demand and so I think people just have a different view or or the different view in terms of when that does end up clearing. I also do think that if you look at like you know anthropics inference numbers I don't think that the at steady state or even right now for example like the open-source inference market where it's like you're just serving inference on these on on the models that are open source like you know you you see different numbers thrown around for the the atcale players there right like the fireworks the base stands of the world uh but I I don't think you know I I don't think at steady state these things end up close to like what the entropic numbers uh for inference just because like that model is available to everyone and someone will will price will will undercut you on price to kind of just get share and I kind of see this playing out. I think I think open router is just like fascinating to look at like you can go look at um you know like go look at like a Kimmy K3 or you know GLM53 like it doesn't really matter what model you look at and you'll see like the set of players on like the official you know the lab itself that made that model like a Kimmy and like the price that they charge at and there are like five and 10 plus like players now that are basically like at like 80% on like basically 20% of that price or even 10% of that price but they are like undercutting the, you know, the the the little what the price that like the Deep Seek themselves might give it at or that like Miniax or whatever might give it at that, they're like undercutting them by like 10x and these are like smaller players, but I do think you're going to continue to see this trend of like, oh, if you try to charge too much, especially in the open source model and depend on the licensing of that model requirements, like there'll just be like some new player like, oh, I have like I'll just capture share now and uh and I'll run it at like 20% gross margins or even 10% u and and as opposed to and and just like capture that share. And so I do think it'll be interesting to see how some of that plays out and settles out. My guess is that I I don't expect any open source inference providence provider to have at least like maybe o over at least like 40% margin longterm on like the vanilla open source tokens which I think is partly the reason why you know you see many of them uh pushing into things like post training and uh uh helping customize models because then that becomes a slightly different uh more lock in slightly different model you're serving and you can maybe uh you know you can benefit from like as you optimize it further and the maybe charge higher have higher margins on those.
</details>

### 科学计算承兑与生命科学湿实验室

>> 太棒了。最后我们收尾在湿实验室和科学计算上。Dario 一直公开表达他对 AI for Science 的个人浓厚兴趣，但外界目前看到的成果还相对有限。S-1 究竟披露了什么，外界又在讨论些什么？
<details><summary>Original English</summary>
>> Awesome. Um so I just want to wrap it up with the the wet lab and the sciences uh work. Um Daario has been pretty open about his personal relationship with uh AI for science. Um we haven't seen that much yet. Um what are people first of all what was disclosed and what uh are people talking about there?
</details>

>> 退一步来看，S-1 中最令人瞠目的数字之一是他们签署了高达 9000 亿美元的算力采购承诺协议，这引发了部分人的担忧。根据其披露的排期，明年的算力支出可能达到 700 亿至 800 亿美元，后年起将进一步攀升至 1000 亿至 1200 亿美元的区间。核心问题在于：除了 SpaceX 的协议外，这些合约大多具有法律强制约束力；如果技术扩散耗时过长，代码之外的新场景未能及时拉动足够的 Token 消耗，导致需求无法消化如此庞大的算力供给，该如何应对？生命科学布局的重要性便在此凸显：它为 Anthropic 提供了一个完全由自身掌控的算力消化渠道。他们可以成为自己模型的最大使用者，去开展药物研发、新材料等前沿探索，而不必受制于外部企业客户缓慢的技术采纳周期。若企业端的技术扩散鸿沟变大或周期拉长，这部分业务就能成为平滑算力冗余的安全垫。当然，算力的另一大用途是 RSI（自进化智能）以及持续迭代更强大的基础模型，但这依然无法解决外部客户需求不足的潜在瓶颈。下注生命科学，辅以文件里略微提及的机器人领域，使他们能够将业务触角延伸至物理世界，自主掌控探索流程，并有望携手药企合作伙伴将前沿发现推向管线落地。
<details><summary>Original English</summary>
>> Yeah, I mean so maybe for a step back I think the the other thing is like you know like the the obviously signed like these like 900 billion of comput of compute commitments which has been you know one of the kind of like eyepopping figures in the S1 that has some people worried and I think to me the question for seeing the applic they have like a rough schedule and so let's say that you know next year they might end up having compute expensive 70 to 80 billion the following year onwards it ramps to like more like the 100 120 billion range And so the question becomes like what happens given that you know these are like mostly contractual other than the SpaceX one. Uh what happens if you don't have enough demand to serve it which is you know like is obviously not a great scenario but it could happen and the reason it could happen is just that um uh it doesn't have to do with anything around even just competition and things. It could just be that diffusion takes longer and so you don't have it's it just you know beyond coding that next thing isn't using as much tokens yet you don't have that next thing and so I think the life sciences stuff is important because it provides like a some use of that compute that is more in anthropic's own control where you can focus your models and then hey like let's we will be the primary user of our own models and and help with you know you could partner with companies obviously, but like you'd be then looking for these novel discoveries and and it doesn't have to be just life sciences or it could be any kinds of things in science, new materials, uh new things like that. And so I think it's really important there because it it it it then means that at least you have an avenue where you can direct compute to which has another way of being productive that isn't dependent on timelines of of enterprises and uh and others to adopt your technology. And so if this diffusion gap ends up bit being long being wider or takes longer you have this kind of this other business segment where you can direct some of the uh compute to and so I think it's important from from that perspective um uh uh beyond just like you know just further the other obviously big use of computers RSI as well and and just making the models better and better but I think that's may not still solve the customer demand piece whereas like having like these life sciences bats and I think they also touched on robotics a a little bit but not as much as life sciences. Like having those then also puts you in a different um having some of these other things that are expanding to physical world but then also things that may be a bit more in your control where you are operating these to try to find like make novel discoveries and that you yourself are you know potentially with the farmer partners taking through the the the pipeline.
</details>

>> 太精彩了。最后还有什么结语或想对创始人及听众分享的吗？
<details><summary>Original English</summary>
>> Yeah. Awesome. Um, all right. Any parting thoughts, um, messages for people, founders, you know, talking to Wing, whatever.
</details>

>> 没有特别的了。事态的发展会非常耐人寻味，我很好奇未来几个月会呈现何种走势。在真正挂牌之前，所有人都会紧盯其单月的实际营收环比增长。
<details><summary>Original English</summary>
>> Uh, no parts. I mean, I think it's going to be very interesting to see how this plays out. And, uh, I'm curious to see what the next couple months look like. And I think until they go public, the the number that everyone's going to be watching very closely is just like the month over month the the actual revenue growth for them. So
</details>

>> 这也正是为什么宜早不宜迟。否则他们就必须设法通过各种手段刺激下一个阶段的 Token 峰值消耗。
<details><summary>Original English</summary>
>> yeah, it's going to be [laughter] which is why it's better for them to do it sooner rather than later. Otherwise, it's like they have to like somehow like encourage a token max for the next
</details>

>> 那样的话他们就必须尽快发布 Fable 5.5 以及后续版本了。这显然能重新吸引注意力并拉动使用量，也是他们必须动用的杠杆之一。
<details><summary>Original English</summary>
>> Yeah, I mean in that case they need to release Fable 5.5. Um yeah, and uh you know, whatever is beyond that, but yeah, I mean that that would obviously be a driver of more attention and and usage and that would that is a lever that they have to pull.
</details>

>> 无论如何，非常感谢你为我们做出的深度梳理，我致力于为即将面临这次事件的人们提供扎实的参考。许多工程师在纠结现在该入职还是套现，整个二级市场也都在关注，因为 Anthropic 是在这一年周期内引领行业的三大前沿实验室 IPO 之一。这对于 OpenAI 未来的 IPO 也至关重要：如果 Anthropic 出现任何形式的滑铁卢，OpenAI 恐怕很难顺利推进上市，而那对各方都将极为不利。这是一个关键的历史节点，让我们拭目以待。感谢你的分享！
<details><summary>Original English</summary>
>> Um but regardless, thank you for taking us through. Uh, you know, I I'm I'm really just trying to give people a good grounding on what they should know going into this. I think a lot of engineers are wondering if they should join, if they should cash out, you know, same thing for just like the general broad rest of the market because Anthropic is probably, you know, one of the uh the three IPOs that are, you know, happening that are the leading frontier labs in in this sort of one-year period. Uh and I I do think it really matters for the OpenI IPO which um if I you know anthropics fails in whatever shape shape or form and anthrop OpenI was just not going to do it. Um and that that's that's sucks for multiple reasons. Um
</details>

>> 是的，这确实是一个极其关键的时刻，让我们看看接下来的走向。谢谢你邀请我来探讨。
<details><summary>Original English</summary>
>> yeah so uh pretty pivotal moment. We'll we'll see. [laughter] Thank you for covering it.
</details>

>> 谢谢你的做客。能深入讨论这些内容很棒，我非常喜欢你输出的内容，我们后续会继续关注。
<details><summary>Original English</summary>
>> Yeah. Yeah. Thank you for having me. It was great to great to discuss and uh yeah love your love the stuff you put out and so uh we'll we'll continue to listen and excited to follow along.
</details>

>> 你的研究同样出色。大家可以关注他的 Substack 以及 Deploy Codes。我们正在与 Ode 合作推出前线部署工程师（Forward Deployed Engineering）专题播客，对此我们感到非常兴奋。无论如何，AI 已经到来，无论企业是否上市，我们都必须积极推进其工程落地。
<details><summary>Original English</summary>
>> Yeah and same same for your work uh you know everyone go read his uh substack as well as uh deploy codes. We're we're actually starting a for deployed engineering track uh podcast uh and we're launching it with ode um which uh which I'm we're pretty excited about. Uh, regardless, the AI is here and we have to deploy it, right? Whether or not things are public or not, we have to deploy it.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Exactly.
</details>

>> 好的，谢谢 Tanay。
<details><summary>Original English</summary>
>> All right. Thanks, Jenny.
</details>

>> 好的。
<details><summary>Original English</summary>
>> All right.
</details>

>> 谢谢大家，我们下周见。
<details><summary>Original English</summary>
>> Thanks. See you next week.
</details>