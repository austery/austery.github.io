---
author: Latent Space
date: '2026-11-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wX8nDtGIfYA
speaker: Latent Space
tags:
  - ipo
  - ai-economics
  - compute
  - inference
  - financial-analysis
title: Anthropic IPO 前瞻与 S-1 财务细节剖析
summary: 本期对话剖析了 Anthropic 即将进行的 IPO 及其 S-1 披露的核心财务细节。讨论涵盖 1.3 至 1.4 万亿美元估值、810 亿美元年化营收、较低的现金消耗与高毛利率，并深入探讨了推理与训练算力分配、数据支出、渠道依赖以及向科学与生命科学等场景拓展的长远增长路径。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models: []
media_books: []
status: evergreen
---
### IPO 前瞻与估值核心数据

早上好。今天我们在 Anthropic IPO 之前做最后一期关于其 IPO 的播客，至于 IPO 之后是否还会继续跟进报道则待定，因为届时这就属于财经播客的范畴了。但我认为这显然对很多听众都非常重要，特别是那些在 Anthropic 工作的人，也包括在 OpenAI 工作的人以及生态圈内相关的每一个人。IPO 路演已经持续了几周，我们比以前了解得更多了一些。我们在 Jam and Ball 播客中详细讨论过很多内容，反响非常棒。感谢大家的积极反馈。我在科技与金融的交叉领域尽量邀请我所尊重和敬仰的人，因为我认为我的职业生涯正是为此做准备的。

关于 Anthropic 的申报价格，大概在 70 到 78 美元之间，隐含估值为 1.3 万亿到 1.4 万亿美元。目前看来大约获得了 7 倍超额认购，最终定价很可能会在 80 美元左右。另外还有远期合约或加密合约在押注最终的首日涨幅会在哪里。如果表现与 SpaceX 的 IPO 类似，首日会有小幅上涨，大约在 19% 到 20% 左右，股价可能会达到 100 美元，对应的估值范围可以说是 1.54 万亿到 1.6 万亿美元。这大致相当于过去 12 个月收入的 38 倍，当前收入的 20 倍。显然，远期收入完全取决于你的预测。官方仍预期——10 月份的年化运行率（run rate）披露为 810 亿美元，这是一项新的披露。

<details><summary>Original English</summary>
Good morning. Today we're doing our last anthropic IPO podcast before the IPO and TBD on whether or not it will actually continue covering it after the IPO because uh that becomes the domain of finance podcast. But uh I think it's still obviously very relevant to a lot of listeners particularly those of you that work at Anthropic but also those of you that work at OpenAI and uh everyone else connected in the ecosystem. Um, the IPO road show has been going on for a couple weeks and we know a bit more than we used to before. Uh, and we covered it a lot of it in the Jam and Ball podcast. That went really well. Thank you for all the positive feedback and uh, you know, I think I try to pull in people that I respect and look up to in terms of the crossover of technology and finance. Uh, because I mean I think that is if if anything my career has set me up to do that. Um so we have a price for the anthropic filing I guess uh between $7 to $78 which is an implied valuation of 1.3 to 1.4 trillion. uh it looks like it is roughly seven times overs subscribed and probably will price in the range of 80ish and then there's also forward contracts or crypto contracts on speculating where the final pop is going to end up if it looks anything like the SpaceX IPO there will be a small pop um it will be about 19 to 20% on the first day uh maybe would go up to $100 um and so that that is in that range of let's call it 1.5 4 to 1 uh 6 trillion, you know, and um that represents roughly 38 times trailing 12-month revenue, 20 [clears throat] times current revenue. And obviously this uh and and obviously that what what Ford revenue is is just dependent on what your projections are. It's still anticipated to uh so October run rate was 81 billion. That was also a new disclosure.
</details>

目前仍预计年底将达到 1000 亿美元。大家真正在思考的是，未来会走向何方？市场的定价逻辑是什么？这显然是任何人给出的最高估值倍数，尤其是在这种体量下。关于未来年份（如 2030 年或 2028 年）的预测范围，收入从 4000 亿美元到 1 万亿美元不等，区间非常宽泛。[笑声] 但为了对 Anthropic 进行长期投资承销，你必须做这类测算。所以你能理解大家为何向前看。目前有 1.1 万到 1.2 万名客户每年每家支出至少 10 万美元，而且一旦进入一家公司，未来年份还会扩张 9 倍。其净金额留存率（NDR）非常高，通常业界顶尖水平大概是 150%，而这里达到了 900%。

关于路演的讨论主要集中在三件事上：第一是 Claude Co-work。从市场叙事来看，这基本上属于下一阶段——你在 Claude Code 之外拓展得如何。我认为未来的产品形态可能会与 Claude Co-work 不同，因为对于 Claude Co-work，我们在播客档案里第一期与 Felix 录制过相关内容，它目前是一种产品形态，但感觉并不是特别云原生。他们在 S-1 中宣传的那种自主团队协作伙伴，肯定必须是云原生的。那正是 Claude Duet、Instinct、Grok 机器人、Cognition 机器人，所有人都在朝这个方向走，我不认为 Claude 会不这样做，而且它很可能会与 Claude Co-work 有所不同。

第二是芯片。Anthropic 希望在英伟达（Nvidia）、AMD、TPU 和 Trainium 上运行，并且他们还披露了关于如何能非常容易地从英伟达迁移到 AMD 的信息。这显然是大家所关心的整个 RSI（递归自我改进）叙事的一部分。但我认为从商业角度来看这完全合情合理，因为如果受制于英伟达的瓶颈，就不得不这么做，而且这是可验证的，也是大语言模型容易完成的核心任务之一。

第三是利润率。我们在利润率方面有了更多披露。按调整后利润率计算，利润率从 19% 下降到了 15%。从 GAAP 营业利润变成了小幅 GAAP 亏损，这完全是预料之中的，不算什么大问题。Anthropic 预计长期内可以达到 35% 以上。如果实现将是一件大事，因为届时它将非常赚钱。正如我们在之前的播客以及与 Jam 的讨论中所谈到的，对于一家达到这种规模并进行 IPO 的大型科技公司来说，这简直是闻所未闻的。通常情况下是严重亏损的，在开始扭亏为盈之前，甚至可能有三四年亏损幅度达到 -100%[笑声]。而这是兼具增长与盈利，以往从未发生过。

<details><summary>Original English</summary>
Still projected to end the year at 100 billion. And what really people are thinking about is like well where does it go from here right like what is the market pricing um this is obviously the highest multiple that anyone's ever uh priced at especially at this size and uh you know ranges for the future like uh future years in like 2030 u or 2028 um really range from like 400 billion to a trillion uh in revenue and so uh that is very wide range. [laughter] Um but you kind of have to do this kind of math in order to uh underwrite long-term investments in Anthropic. Um and so you can see why people looking ahead. You know, I think um uh 11 12,000 customers spend at least 100K per uh uh year and per customer, but once they land in a company, they also expand nine times um in the in the future years. So like uh there is uh NDR like a very good net dollar retention uh usually state-of-the-art is let's say 150% and this is 900%. Um so really the discussion about the road show has focused on three things. One which is cloud co-work um it is basically the sort of next phase as far as the market narrative is um how how well are you extending outside of cloud code. I think there is probably going to be a different form factor I would say than cloud co-work because cloud coowork is you know we did the first cloud co-work pod with Felix um if you scroll back in our archive and it's a it's a form factor that's there but I think it's not very cloud native and definitely the sort of autonomous like teammate that they are pitching for their S1 that we covered in the first podcast that is um definitely going to have to be cloud native that's cloud duet that is the instinct that is the gro bots that is the cognition bots all those things are like everyone is trending towards that direction and I don't see why cloud would not do that and probably that is going to be something different than cloud co-work uh the second one is chips uh entropic wants to run across Nvidia AMD TPUs tranium um and they also released information about how they were easily able to migrate much much more easily uh from Nvidia to AMD And I that is obviously part of the whole RSI narrative that people are concerned about. But I think that is obviously just makes a lot of business sense for them that like hey if you're I'm bottlenecked on Nvidia I'm sorry I I have to do this right and by the way it's verifiable and by the way it's uh one of the core tasks that we that is uh that that is easy for LMS to do. Third is margins. Um so we have a little bit more in terms of disclosures on margins. Um we know that margin went down from 19% to 15% and using an adjusted margin. Uh it went from a gap operating profit to a slight gap loss and that is just intentional not a big deal. Um Anthropic is projecting that it can get above 35 in the long run. Uh so that would be a very big deal because then it would be very profitable and that's something that uh again like we as we discussed in uh this podcast in the previous one with Jam that is just unheard of for a large tech company of this size IPOing. uh usually you're unprofitable like deeply unprofitable like like 100 negative 100% profits for I don't know 3 4 years [laughter] before you even start to turn it around. Um and that's good. I mean this is growth with profit which uh never happens.
</details>

我认为本周发生的最后一件事是 OpenAI 的模型发布。正如我们之前确立的观点，模型发布对于前沿实验室（Frontier Labs）的生存能力来说极其极其重要。前沿模型的生命周期大约只有 6 个月，如果不发布下一个处于前沿水平的模型，使用量显然就不会流向你，而且这对基准测试和实际使用口碑感受（vibe checks）非常敏感。OpenAI 推出了 GPT-6.2，而 Anthropic 推出了 Claude 5.2。显然 Claude 5.2 依然位居榜首，口碑评价大多也证实了 Claude 处于领先地位。此外还有效率前沿，OpenAI 声称占据该优势。我认为在实际应用中人们的看法更复杂一些，因为存在基准测试与实际使用之间的差异。我想说的是，这两个模型的发布基本上没有改变双方阵营。如果你是 Claude 的拥趸，会继续用 Claude；如果你满意 OpenAI，会继续留在 OpenAI。那些可能大幅改变局面的 IPO 关键风险（无论是利好还是利空）并未真正发生。人们所期待的 Claude 5.5 并没有出现，Google 推出了 Gemini 4，尽管 Gemini Carbon 表现非常出色，但并未影响市场叙事。大致就是这样。所以这些关键风险对于 Anthropic 的 IPO 来说已经过去了。Anthropic 依然是全球顶级模型实验室，明天就将进行 IPO，这将会是一场重磅的上市。这对于整个生态圈非常有利，因为一次失败的 Anthropic IPO，再加上同时发生的英伟达戏剧性事件，将会带来极其负面的连锁反应。这就是过去一周的总体情况更新，大家基本都准备好了。这是我们录制的深入探讨 S-1 若干细节的播客，希望大家喜欢，祝明天好运。

好的，我们来到了远程演播室。这是我们与 Tanay Jaipuria 一起报道 Anthropic IPO 系列的另一期。欢迎你。

<details><summary>Original English</summary>
Uh I think the final thing that happened this week is opening eyes model launch. Um as we already established model launches are incredibly incredibly important to the viability of the Frontier Labs. Um the shelf life of Frontier model is roughly 6 months and if you don't release the next model at the frontier then obviously the usage is uh not going to come to you and it it is very sensitive to benchmarks and uh vibe checks and so open shipped GBT 6.2 and Fable and topic shift Fable 5.2 and obviously Fable 5.2 is still on top and I think the vibe checks are mostly holding out that Fable is on top. So there's that and then there's the efficiency frontier which open does claim. I think people are a little bit more mixed in practice in terms of there's benchmarks and then there's just like impractical use and um I would say that there's basically both model launches have not really changed camps either way. If you're a cloud person, you could continue to be clawed. If you're happy with an open AI, you're continue to be open AI. Uh those key risks for the IPO that may have dramatically changed the story either for the positive or negative haven't really changed. There was no Fable 5.5 that people were anticipating and um there, you know, and Gemini shipped Gemini 4 that did not affect the narrative even though Gemini carbon did very very well. And that's about it, you know. So like those key risks are behind us for the anthropic IPO. Um Enthropic is still the top model lab in the world and uh it is IPOing tomorrow and it is going to be a blockbuster IPO and that's really good for the ecosystem because a failed enthropic IPO would have been uh would have read through really badly together with the Nvidia drama that is also happening at the same time. Um so that is the overall update in the last week. You are mostly prepped. This is our podcast that we recorded to go through some finer details in the S1 and I hope you enjoy and good luck tomorrow.

Okay, we're in the remote studio. Uh this is another in our series covering the enthropic IPO uh with Tane Japur. Welcome.
</details>

>> 谢谢邀请我。我是本播客的长期听众，非常高兴能来参加。

<details><summary>Original English</summary>
>> Uh thank you for having me. Longtime listener of the podcast and excited to be on.
</details>

>> Tanay，你怎么会写 S-1 的拆解分析呢？

<details><summary>Original English</summary>
>> Uh T, how come you're uh writing S1 breakdowns?
</details>

### 解读 S-1：世代级企业与核心指标

>> 是的，我想总的来说，大概在过去的六七年里，我一直在 Substack 上撰写各类长篇内容，其中一个主题就是在有趣的公司上市时对其进行剖析。我认为 S-1 通常是局外人能够窥见一家企业各个层面的时刻。我之所以如此喜欢阅读它们，是因为你能借此了解这家企业迄今为止的故事脉络，而且我觉得每家企业都有一些有趣的经验，供人们吸取关于商业运作或特定商业类型的知识。我最初就是从这个角度去关注的。而在过去一年左右的时间里，我们见证了 SpaceX 以及现在的 Anthropic 上市，这些都是真正具有世代定义级别的公司。因此，去深入研究它们就更加有趣了。我认为它们确实能让你了解这些具体公司的现状，同时也能更广泛地了解整个市场。通过 Anthropic 的 S-1，你能全面了解从模型开发、推理——现在每个人都在谈论推理是下一个巨大的市场——到当前所有算力需求与 Neoclouds 的现状，再到未来在科学及其他领域的前景。所以，这显然是一家定义品类的公司，而且它依然处于相对早期阶段。在短短五六年时间里能如此迅速地创造如此巨大的价值，确实不可思议，这在以往任何公司中都是我们未曾真正见过的。

<details><summary>Original English</summary>
>> Yeah. No, I think in in general I guess uh maybe for the last uh six or seven years I've been uh you know writing about various things like more on long form on on Substack and one of the topics I've been writing about just like breakdowns of interesting companies as they go public and I think the S1 is usually the time when as as an outsider you get a look into like you know all aspects of the business and the the reason I enjoy reading them so much is that you can kind of get a sense of like the story of the business so far and I feel like in every business there are some interesting lessons that you know for people to take away about business in general about you know specific kinds of businesses and so I used to follow them from that perspective and then obviously over the last year or so some of the you know the ones we've had go like with SpaceX and now with the Anthropous one these are like you know truly generational defining companies and so uh I think it's been even more uh even more fun to to look into those and I think they do give you a sense of the current state of um those companies specifically but then also the market more much more broadly and so with the anthropic S1 kind of gives you like a purview into everything from you know this this the idea of like you know the model development inference everyone's talking about like inference as this you know the next big huge market uh it gives you a sense of you know the current state of all the compute uh needs and like neoclouds and then also what's to come in the future with things like science and uh some of those things. And so I think it's obviously like a category defining company and one that uh and one that's still relatively early in in kind of crazy that in you know in five or six years it's uh created this much value so quickly uh and it's something we've never really seen before uh uh across any company really.
</details>

>> 确实如此。我很乐意直接切入主题。你准备了很多图表，我可以顺着你想探讨的方向聊。 headline 数据方面，他们的收入增长非常迅猛，与去年同期相比增长了大约 13 到 14 倍。10 月份的年化运行率数据刚刚泄露出来，我们此前就知道这是他们预备披露的数据，在 S-1 中曾留白，但现在他们报告的年化运行率是 800 亿美元，对吧？

<details><summary>Original English</summary>
>> Yeah, for sure. Uh and you know I I'm I'm happy to dive right in there. you have a lot of charts that are um have been prepared and I can go wherever you want to take this headline numbers um you know they're they're ramping revenue a lot it's really interesting basically up like 13 14x from uh same quarter last year I think the run rate numbers just leaked for October which we knew was was uh something that they had in store and they they kind of left blank in the S1 but now uh they're reporting 80 billion run rate right
</details>

>> 嗯。

<details><summary>Original English</summary>
>> um
</details>

>> 是的，所以 80 除以 4 就是季度 200 亿。是的。

<details><summary>Original English</summary>
>> yeah So I think it's 80 divide by 4 is 20. Yeah.
</details>

>> 是的。我猜测他们计算那 800 亿的方式更偏向于按月折算。他们实际采用的具体定义可能是 28 天乘以 13，再加上当月的订阅收入。这很有意思，因为即使在 Twitter 上，人们对此的反应也很复杂：有人认为这是一个非常积极的数字，预示着重新加速增长；而有人则表示，这实际上意味着他们可能无法达到一直谈论的 1000 亿美元退出运行率。我认为这很难断定，但大概处于环比月增长 8% 到 10% 的水平，我认为……

<details><summary>Original English</summary>
>> Yeah. And I think the the my guess is the way they calculate that 80 is this kind of more like on a monthly basis. And so I think the exact definition they might use is actually 28 days times 13 plus like monthly subscription revenue. And so it's it it's interesting because I think it's being even on Twitter I think the reactions to that will mix where there are some people saying oh this is like a very good very positive number and uh signals reaceleration. uh whereas some are saying that it's actually they'll it'll mean that they likely will fall short of the 100 exit run rate that they've been talking about. I I think it it's hard to tell but I think it probably is in that kind of 8 to 10% month overmonth growth which I think is
</details>

>> 我不知道这算不算是重新加速，但至少与他们过去几个月的表现大致持平，我的猜测是可能略有上升，但目前很难完全了解，因为他们还没有按月拆解第三季度等数据。

<details><summary>Original English</summary>
>> I don't know if it's re acceleration but it's at least roughly in line with what they did in the last few months and it might be slightly up is my is my guess but hard to hard to fully know at this point because they haven't broken down you know Q3 and stuff by month.
</details>

>> 是的，完全同意。80% 来自用量计费，20% 来自订阅，这挺有意思的。订阅能享受多大的折扣在业内算是一个公开的秘密，所以人们其实有动力降低这 80% 的用量计费比例，但你得摸透其订阅体系。

<details><summary>Original English</summary>
>> Yeah. Yeah. Totally totally. uh 80% consumption, 20% subscriptions, which is kind of funny. Uh it's like it's a pretty public secret how much of a discount the subscriptions get. Um so actually people are incentivized to make this 80% consumption base lower, but uh you have to sort of figure out the subscription system.
</details>

>> 而且年支出超过 10 万美元的客户数量增长了 8 倍，达到 1.2 万家。由你来引导，假设大家已经看过了主要数据并且了解其盈利情况，你认为人们应该领会的核心信息和主要话题是什么？

<details><summary>Original English</summary>
>> Um and uh you know number of customers over over 100K is up eight times to 12K. Um yeah, you know, like I I'll let you drive like what what let's assume that people have looked at the headline stuff and they know about the profitability. What are the major topics that uh you think are the the main messages that people should take away?
</details>

### 资金效率与毛利结构拆解

>> 是的，过去几个月里的不同时间点，关于他们大致的运行率等数据一直有各种泄露。所以对于一直关注此事的人来说，基于 S-1 发布前公开报道的内容，这些数据并不算太大的意外。我认为可能让人们最感惊讶的是这家公司的现金消耗速度——我是从正面积极的角度来说的。他们筹集了大约 1400 亿美元现金，资产负债表上居然还躺着大约 1320 亿美元左右。也就是说，为了达到现在的规模，他们总共消耗了不到 100 亿美元。我认为除了真正了解内部数据的局内人之外，根据大家对该业务现金消耗和利润率等预期，没人能想到他们资产负债表上的现金储备居然有这么大。所以它实际上是一家非常、非常、非常高效的企业。

我做了一个简短的分析：考虑到他们所达到的规模——按季度乘以 4 计算，在 IPO 时年化运行率大约在 700 亿美元左右——衡量在上市时每产生一美元年化营收运行率所消耗的资本（即现金消耗）。在过去五到七年里上市的任何具备相当规模的企业中，很少有能与之匹敌的。我认为在营收运行率基准下的现金消耗效率方面，大概只有 Airbnb 能与之相近。因此我认为这是非常出人意料的一点。即便从绝对美元金额来看，Anthropic 在上市时所消耗的美元资金其实比 Uber 上市时还要少。考虑到他们所创造的成果，这确实非常了不起。

关于现金消耗，我此前在想：Meta 每两个季度左右在其 Reality Labs 业务上仍然要烧掉 100 亿美元。现在大概降到了每年 160 亿美元，所以每季度可能消耗 80 亿美元，但他们每年烧掉的资金依旧极其荒谬[笑声]。

<details><summary>Original English</summary>
>> Yeah, I think like you know at various points across the last few months there have been all these leaks about you know roughly like their run rates and stuff. So I don't think like you know to me like it's kind of like those things were not as much of a surprise to anyone that's kind of been following this in terms of uh you know what to expect based on what has been publicly reported even before the S1. I think perhaps the biggest surprise to people was just around the cash burn of the business and and in I mean that in a positive way. So they they had raised like you know $140 billion of cash and literally like they still have on the balance sheet like 132 billion or so. And so they burnt like under $10 billion to get to where they have. And I I think it's like one no one I don't think other than you know obviously the people that actually knew the numbers from from being on the inside. I don't think anyone expected that they that the cash war chest that they had on their balance sheet was actually that large just based on uh you know based on expectations around the burn and the uh margins and things of of the business. And so it's actually been like a very very very efficient business. Um and um uh I I kind of had just did this quick analysis around you know given the scale they've gone to right which is you know roughly 70 billion at the time of you know if you do like the quarterly times four what's the capital consumed in terms of like the cash burn per dollar of kind of revenue run rate at the time of the IPO and there are very few businesses of any meaningful scale really that we've seen go public over the last five seven years that are anywhere close like I think Airbnb is probably the only one uh that that kind of comes close on a revenue run rate basis in terms of the cash efficiency in terms of the burn. And so I think this was something that was quite surprising. I think even from like an absolute dollar basis like I think Anthropic has literally burned like less dollars than Uber did to to get go like at the time when they went public which uh you know given what they've created with this is is you know pretty remarkable. Uh um and uh it's like you know the cash burn. I was thinking about this like like Meta is still burning like 10 $10 billion on their reality labs initiatives every like two quarters or so. Uh I think it's now down to like 16 billion a year. So maybe they burn like 8 billion but they're still burning every year. Way more absurd. [laughter]
</details>

>> 是啊，相比之下这家公司从零起步，构建了长上下文智能体（long horizon agents），在很多领域都是开创者。等等，我本来以为他们会把那部分开支削减归零呢，搞什么鬼？[笑声]

<details><summary>Original English</summary>
>> Yeah. Than like you know this company that got off the ground and like built like you know basically built like long horizon agents and like you know was the first of so many of these things. Oh, wait. I expected them to to take it to zero. Like, what the hell? [laughter]
</details>

>> 没有，他们依然在巨额亏损。

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

>> [笑声]这就好像他们每副眼镜要烧掉一百万美元一样，太疯狂了。我之前针对 MSL 的想法是：他们每年在 VR 上烧掉大约 200 亿美元，只要削减那 200 亿重新分配给 MSL，就能拥有一个 Neocloud。他们现在确实做到了，只是他的财力太雄厚了，两边都能兼顾。

<details><summary>Original English</summary>
>> It's [laughter] like they're burning like a million dollars per spectacle for glasses or something. Like, what the Like,
>> um that's that's crazy. So, so I expected so my my actually pitch for MSL was look
>> the uh they were burning something like 20 billion uh per year uh on on on
>> on on VR
>> and you just cut that 20 and reallocate to MSL uh and you you have a Neol, right? Like like and which is they they now have it. It's just that his pockets are so deep that he can just do both.
</details>

>> 是啊，他心想：“哦，我可以做那个，但我也许不会彻底砍掉这块，而是慢慢缩减。”

<details><summary>Original English</summary>
>> Yeah. He was like, "Oh, I'll do that, but maybe I won't do the cut fully and like I'll slowly do the cut." Yeah.
</details>

>> 显然他很享受这一切，生活很滋润。但这些眼镜和 Muse 相比根本不算什么。太搞笑了，真不敢相信他们每个季度还要烧掉 50 亿美元。

<details><summary>Original English</summary>
>> I mean, like clearly like he's enjoying it. He's loving life. Uh whatever. But like uh you know, these glasses are nothing compared to Muse, right? Um
>> Yeah.
>> So, uh it it's so funny. Oh man, I can't believe they're still burning five billion a year. Uh five billion per quarter.
</details>

>> 行吧，这就是现金消耗情况。我觉得这一点被低估了。这里唯一没看到的数据是：OpenAI 在哪里？因为我们没有 OpenAI 的 S-1。它的效率要低得多，大概更接近 Snowflake、Cerebras、CoreWeave 的区间。以前也有非官方图表，如果有人密切关注泄露的 S-1，这不算全新的事实。此前人们画的图表中，Anthropic 的预测曲线表现良好，而 OpenAI 则深陷亏损之中。所以这是已知的图表趋势，只是我们此前不知道差距具体有多大。

<details><summary>Original English</summary>
>> Yeah. Uh come on. All right. So, that's the cash burn. You know, I think um that's something that
>> um I feel like is underrated. Uh so the the one number that you're not seeing on here is where's OpenAI, right? Uh because we don't have the Open S1. Um it is way more inefficient. Uh it it is probably closer to like the Snowflake Cerebras Core Weave
>> range. Uh and there have been unofficial charts. So this was this is like not a completely new fact. if people were paying close to the the leaked S1 where people were already drawing um charts like uh Enthropic was let's say doing uh was was was known to be doing like this uh as like a like a projection and then and then OpenAI was like kind of like way deeper and like yeah something like that. Um and so so this is a known chart that like we just didn't know how big it was. Um
</details>

>> 是的，我认为具体的数量级此前并不明确。

<details><summary>Original English</summary>
>> yeah the I think the magnitude wasn't
</details>

>> 是的。我认为这可以归因于几个因素：首先，Anthropic 起步较晚，他们基本上跳过了 GPT-1、2、3，因为那是在 OpenAI 完成的。那些研发成本是由 OpenAI 承担的，团队还是原来的创始团队。所以他们已经在那边交过了学费，离开之后可以从纯净室（clean room）的视角直接复现那些工作。但为什么 Anthropic 会如此高效？我觉得这是一个非常未被深入探讨的问题。一部分原因在于他们现在实现了单体经济（unit economics）盈利，这很酷；同时他们走到今天并没有消耗太多资金，这在科技界极其罕见，基本闻所未闻。

<details><summary>Original English</summary>
>> Yeah. Yeah. So, so, um, and I think I I attribute this to to a couple things, right? Um, Enthropic started later.
>> So, they they they basically skipped GPT123 because that was done on Open Eyes. Um, and you know, that that R&D Yeah. It was done on their dime. It's the it's the same founding team.
>> Um, so like they, you know, they they already paid the tuition there and then now they come out and and they can just kind of repeat that work from a a clean room perspective. Um but you know what else like what why is why is anthropic so efficient? I think that is like a really really um underexamined thing. Uh partially I think it's just straight up like there are now unit economics profitable
>> uh which is cool. Uh but they also didn't burn that much to get there which is super unusual like like basically unheard of in tech.
</details>

>> 没错。如果看正下方的毛利率图表，我认为这也与 OpenAI 形成了鲜明对比：因为 Anthropic 始终专注于编程和更广泛的企业级市场，其策略是打造最好的模型，优先通过渠道合作伙伴进行分发，并尽可能借助渠道获取算力。他们并不试图面向大众消费者，因此不需要用大量免费推理去支撑庞大的 C 端用户群。在支持付费用户方面，他们的经济模型非常健康。大家最常提到的数字是他们报告的大约 85% 的毛利率，理解这一点的方式是：付费用户的推理成本占营收的比例只有大约 15% 左右。下文有一张图表对此进行了细分。

他们报告在付费推理上实现了 85% 的毛利率。但很多此类公司常做的一件事是：对于免费层用户，通常将其计入销售与营销费用（S&M）。因为你可以辩称这是吸引用户进入平台的手段，并在其转为付费后实现变现，所以将免费层的推理成本归入营销支出。有人可能会觉得这应该计入主营业务成本（COGS）。但关键在于，由于 Anthropic 主要依赖企业级客户和编程场景，Claude 在用户规模上不像 ChatGPT 那么庞大，从利润率和现金消耗的角度来看，这反而是个优势，因为他们没有庞大的免费计划用户群需要负担。他们只花费大约 4% 的毛利率点数，或者说大约 5% 到 6% 的算力支出用于免费用户的推理。我认为当 OpenAI 的数据公布时，考虑到其庞大的用户基数，该比例会明显更高。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. And and if you go to the the next the the chart right below around kind of gross margin I think and this also probably contrasts something with uh with open AAI which is that uh because anthropic focused and ended up focusing on coding and on enterprise maybe more generally and more just like let's have the best models and uh both on let's distribute primarily through channel partners but then also let's leverage them for compute wherever possible and they would didn't have this because they weren't trying to do consumer they didn't really have this like massive consumer base that they had to support uh with like you know mostly free inference. They the the economics are like very very uh positive for them on on kind of like you know on supporting like their paid users. And so I think the most common number like you know is like this kind of idea of 85% gross margins that they report and the way to think about that is that essentially like as a percent of revenue their like inference on paid users is about 15%. Uh and there's a chart further below that kind of breaks breaks that down. Um uh and so that you know they reported yeah they reported these like 85% gross margins on you know essentially paid inference. Uh but then you know one thing that a lot of these companies obviously have been doing is that there's these like free free free free tier users and it it's been common to put this into sales and marketing spend because you know you could argue that it's like oh it's our like it's how we attract users to a platform and then we monetize them with if they become paid and so they put that free tier inference in sales and marketing spend and so you could be like oh maybe that should go in cogs and but I think the point is that for Enthropic because you know they primarily relied on enterp price and on coding and claude is not as big as like you know chat GPT is from a margin perspective and maybe like a cost uh cash bone perspective that actually is a positive for you because you don't have this huge user base you have to support on on the free plan and so they only spend like you know only about like 4% of margin points or about like five six% of their compute spend ends up going on like this free user inference and so I think that's kind of like the other aspect of it I I imagine when the numbers come out for OpenAI that's going to be significantly higher just given the size of that size of that user base. Um
</details>

>> 对任何免费层来说，4% 的比例都很小对吧？我不知道你从其他 S-1 和投资角度是怎么看的。通常免费层大家就直接当作营销费用来对待。

<details><summary>Original English</summary>
>> yeah for do we do we is four 4% is small right for any free tier. I I don't know how you you look at your other uh S1's and investing. Um
>> usually free tier is like people just kind of treat this as marketing right like this marketing expense. Yeah, exactly.
</details>

>> 确实如此。这具体是指算力消耗方面。市场上公开上市且提供包含算力计划的免费用户的公司并不多，但核心在于他们并没有将大量算力浪费在服务免费用户上。大部分算力要么用于训练和研究，要么用于支持付费用户。回想一下 OpenAI 关停 Sora，我认为部分原因在于：一方面它没有真正实现商业变现，因为原本就没打算变现；另一方面它消耗了极其巨大的算力，而他们显然有更多富有成效的用途，尤其是考虑到他们并没有真正想把 Sora 做成某种 AI 视频生成平台。Anthropic 也是同样的逻辑。

<details><summary>Original English</summary>
And and so obviously this is specifically on the compute usage and so it's hard like there aren't that many companies that have like you know that are public that have like free user with compute plans, but I think essentially like they're not using up a ton of their compute on serving these free users. And so most of it is either being used for training and research or is being used to support these paid users which I I think like you know if you if you think about like you know remember OpenAI getting rid of Sora uh one kind of reason for that I think was just that it one it was obviously not really monetizing because it didn't intend to but it was such a use it was such a large use of compute that it was like you probably have more productive uses of that especially given that they weren't really trying to monetize it into some kind of like you know like AI video gen platform. form truly. Um, and so I think you see that with with with Enthropic.
</details>

>> 我觉得是有理由的，Sam 一直想为 OpenAI 打造一个社交网络。如果你不是 Twitter，也不是 Facebook 或 Instagram，你要做什么？做 AI 版 TikTok。那是一个合理的押注，只是没有成功。我觉得值得一试。在这一点上我算是 OpenAI 的辩护者：你固然可以做编程、做 B2B SaaS 或企业级软件，但 AI 本应该比“帮人更好地写代码”更宽广、更具创造力且更有趣。所以我理解 DeepMind 和 OpenAI 去做那些不局限于日常工作的事情。

<details><summary>Original English</summary>
>> I I think there was a case for, you know, Sam has always wanted to build a social network for OpenAI.
>> And what do you do if you're not Twitter, you're not Facebook or Instagram. You do AI Tik Tok, right? Um, and that was a reasonable bet and it didn't work out. So, I don't know.
>> I I think it was worth a try. I actually like I'm kind of like an open AI defender here in terms of
>> yeah you can do coding in B2B SAS or enterprise but like you know AI is supposed to be a bit more broad and creative and weird than just you know we help you code better. Um and so I I you know I defend like the deep minds and the the opening eyes for doing things that are not you know just work.
</details>

### 业务增长瓶颈与新用例探索

>> 是的，Anthropic 之所以成功，部分原因正是由于其专注。从他们的发展历程来看，专注带来了巨大的帮助。但人们的一个大疑问——从数据中也能初见端倪——是：第二季度对他们来说是一个里程碑式的季度，年化运行率增加了约 250 亿美元；但第三季度增速出现了大幅放缓，环比增长从超过 100% 降到了 40% 到 45% 左右。人们开始怀疑：那个季度是不是只是“Token 狂欢（token maxing）”和 Anthropic 市场份额的顶峰？因为当时没有其他家在代码领域和优质的长上下文推理模型上跟上来，他们吸收了所有可用市场；而现在大家都追赶上来了，开源权重模型很强大，Token 狂欢正在降温，大家都在讨论模型间的路由分发（routing），在没有下一个增长支柱的情况下，是否会因此受到冲击？

我认为这确实是一个风险，但我认为没那么严重，因为就当前核心技术的普及度而言，整体渗透率依然非常低。但确实存在一个大问题：在编程之后，是否会出现另一个规模相当的新领域？让大批用户愿意为了那种场景每月在 Token 上花费 8000 或 10000 美元。从各细分领域的产品市场契合度（PMF）来看，编程显然是第一位，其次是客户支持和法律等。另一个正在显现的领域——X 上有很多关于明年安全领域 Token 使用占比的争论——就是安全。实验室在某种程度上制造了问题，但也提供了解决方案：攻击者可以使用所有这些模型大肆发起攻击，我们已经看到一些涉及 PHP 的攻击和黑客事件，以及被移除安全护栏的模型。我认为安全是一个很有前景的大规模消耗 Token 的场景。

至于长期前景，他们谈得很多的是科学和生命科学，利用这些模型开始进行药物研发等工作。他们也在 S-1 中提到了自己的湿实验室（wet lab）空间等内容。

<details><summary>Original English</summary>
>> Yeah. And I think it's one of those where I think that's the Anthropic has worked partially because of its focus, right? And and if you see where they've gone to that that that's helped them a lot. But as you think about uh one big question that people have and you kind of start to see it in some of the numbers is that hey like Q2 was this like generational quarter for y'all where yall added like you know like 25 billion of like you know like on an annualized basis of like run rate revenue and already you see like a a decline in Q3 both like a massive slowdown where you went from like you know over 100% quarter over quarter growth to like 40 45% or so quarter over quarter growth but then also you ended up um now that the people are like oh was at just the quarter of like max token maxing and peak kind of like entropic share because no one else had caught up on coding and on like a good like you know like reasoning model like a long horizon reasoning model and you just basically captured all of that that market available and now everyone's kind of caught up now open wave models are strong token maxing is ending everyone's talking about like you know routing across models and so you're going to suffer from that without maybe that next leg to go on and I do think that is parti actually one of the risks I don't think it's as big as that in the sense that it's we're so we're still so underpenetrated in terms of just diffusion of you know this core technology that's already available to us but I do think there is this big question of what is is there going to be like the next thing off to coding that is like actually the size of this of coding where um someone you can imagine like mo some large base of people are spending like $8,000 a month or $10,000 a month on kind of tokens off that kind of for that kind of use case. Um it to me I think what the the if you think about just like you know product market fit of various segments like obviously I think coding is number one. I think customer support legal have probably been some of the others. I think the the one that seems to be coming and there have been various debates on X about like you know what percent of token use next year is going to be on around security. I think that could be another one where in some ways these labs have kind of created the problem but then also offer the solution where now attackers have access to all these models and can kind of go ham on on these. And I was starting to see some of this play out, right, with some of the PHP stuff and then just like more and more of these hacks happening and you know some of these like um the models that are like uh um ablated and like that allow you to kind of really uh use these and so I can't I I I see that as like a promising area in terms of like you know what's that what's another like massive source where like a lot of tokens can be used. Um uh but then I think what they talk about a lot uh for long term is around like science and uh uh uh life sciences and uh you know let's uh maybe use these to start doing things drug discovery and and all of those things. Um and and they touch on like you know some of the uh the wet lab space they have and and and those things as well.
</details>

>> 对，我们把湿实验室的内容留到最后，因为那相对较新，细节披露也较少。聊了这么多核心财务数据，还有什么让你感到意外的？

<details><summary>Original English</summary>
>> Right. Right. Um we we'll leave the weblab stuff to the end because obviously that's like newer and and less um
>> uh we honestly just have less details about it. Um what other what like Okay, so you know we've talked about a lot of the headline financial things. Um what you know what really surprised you?
</details>

### 算力分配、数据支出与版权诉讼

>> 就我个人而言，依然分配在训练和研究上的算力比例让我相当惊讶：他们大约 70% 的算力用于训练和研发，只有约 30% 用于推理。这令人惊讶的一点在于[笑声]其推理效率极高——去年初这一比例是 50%。

<details><summary>Original English</summary>
>> What else? Yeah, I mean I personally was pretty surprised by in some ways the the share of the compute that was on training and research still like like you know it's basically they're using about 70% of their compute on training and research and only like 30% is going towards inference and that I think we're surprised both one that just means you know [laughter] the inference is very efficient so like you know it's going right it it was 50 at at uh at the start of last year
</details>

>> 没错，他们确实在极致压榨推理效率。仔细想想，像 Anthropic 这种规模的企业，如果今年其推理成本只有大概 100 亿到 120 亿美元左右，这是很惊人的，甚至会让人反思当前一些基建扩张的规模。虽然整体上我们仍处于早期，但达到这种营收体量，每年却只需约 100 亿到 150 亿美元的推理支出来支撑，这让我很吃惊。

另一部分在于数据支出：他们并没有直接单独列出，但给出的数据足以让你拆解出数据支出。这也令我惊讶，因为直到大约一周前修改申报文件披露上个季度的数据之前，我对其数据年化支出的最佳估计大约在 9 亿到 10 亿美元左右。考虑到硅谷有那么多公司在向各类垂直领域销售 RL 环境等数据及其规模，这个数字其实相当小。但能看到的是，按季度计算出现了一个大幅跳跃：在 6 月至 9 月的季度中，他们在数据上花费了约 6 亿美元。可见他们最近显著加大了这方面的开销，如今可以说他们的数据年化支出运行率接近 20 亿到 25 亿美元。

现在市场上对购买企业运营数据以及通过数据经纪商获取真实公司数据重新产生了浓厚兴趣。这表明基于强化学习环境、后训练（post-training）以及跨领域扩展的范式正在发挥作用且成效良好，因此他们继续在各类数据形式上加大支出。数据支出在历史上大约占算力支出的 5% 到 6% 左右，尽管上季度如我所说出现了跳升，从约 4% 上升到了 6%，这也是一个值得观察的动态。

<details><summary>Original English</summary>
>> exactly and so I think they're really squeezing inference efficiency out which to me I mean if you think about it right a business of the scale of anthropic if if their quote unquote infer inference costs are only like call it like 10 billion this year maybe like10 to 12 billion a year that's kind of crazy if you think about it like and it it does make you question a little bit about like some of these sizes of these builds out build out more now again we're still very early in aggregate but the fact that they've gone to this scale and they're only spending like you know 105 billion a year on on inference to support that size. I think that that was surprising to me. Uh I think the other piece of it was that um they kind of they didn't technically do this, but they vaguely gave you these numbers that let you break out like the data the spending on data. And even that to me was surprising in that it was until this past quarter, which they only kind of published through the amended filing like a week or so ago. It my best estimate on it was it was like about like 900 million or a billion of run rate spend on data, which I thought was actually quite small. given that you consider this how many of these companies are in there in Silicon Valley selling like various forms of data like RL environments of all these different niches and the scales that like you know that so many of them are at uh and so that was surprising to me. I think the one thing you did see is that there was at least if you on a quarterly basis there was a big jump to I think they spent about 600 million or so in the June to September quarter on on data and so it seems like they have very recently ramped up this spending quite a lot and so today you could argue they're you know now spending close to like two two and a half billion a year uh run rate on data. Um, and it it's interesting because now it feels like, you know, there's been this renewed interest in all these like buying operational data from companies and like these data brokers that are helping get like real company data onto people. So to me it's a sign that like this the this kind of RL environment paradigm we've been in and like just like post training and using RL to keep scaling across every one of these domains uh is working and they're seeing good results from it and they're continuing to ramp up their spend on on on that across all these forms and so I I thought that was interesting well and it roughly the spend on data has more or less been you know like five to six% of their spend on compute over time although it it kind of did have this jump as I mentioned in the last quarter from like and so it went from like 4ish% compute to 6%. But I think that that's another thing to watch.
</details>

>> 我也一直在关注这一点。你认为按算力支出的百分比来衡量数据规模是合适的方式吗？

<details><summary>Original English</summary>
>> Yeah, that's something I've been I've been tracking a little bit. Um do you think that scaling it by percent compute is the right way to do it.
</details>

>> 我觉得不尽然。看绝对数值并进行讨论是一种方式；但如果将其视作模型训练的核心投入，计算占训练与研发算力的百分比可能更为合理。另外未包含在内的是外部供应商支出：内部很可能还有一个规模可观的合成数据生成项目，这部分成本大概直接被计入了训练与研发算力之中。

<details><summary>Original English</summary>
>> Uh I I I don't think so. I mean I think like one is just like what's the absolute number and like let's talk about that. I think but if you think about if you think about it as like it's it's ultimately a core input into training maybe percent of training compute could be a good like percent of compute that's going on training and research the other thing that's not captured in this is that this is the spend on external vendors that I my guess is there's also a sizable just like or not my guess but there is a sizable synthetic data effort internally as well to synthetically generate data that is probably just getting captured in training and research compute uh uh uh uh um as well. Uh and so so that that is like you know the other aspect
</details>

>> 他们还在买书并销毁书籍。

<details><summary>Original English</summary>
>> they're also buying books and uh destroying them.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在 S-1 某一季度的利润表中，有一项单独列出的和解赔偿金。

<details><summary>Original English</summary>
>> Yeah. And so I think this was the they had the separate line item in the for one of the quarters in the S1 for this the settlement that they paid for
</details>

>> 15 亿美元，那是怎么回事？

<details><summary>Original English</summary>
>> 1.5 billion. What was this?
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah. Exactly.
</details>

>> 我之前没细说，好像被称为 Books 和解案之类的。在某一季度的利润表中有一行单独的专项支出。我觉得好笑的地方在于：被罚的原因并不是他们实际购买的书，而是因为他们抓取了大量盗版资源。问题不在于使用了购买的书籍，而在于使用了未付费的内容。如果他们全买下来，可能就不需要支付这笔和解费了。

<details><summary>Original English</summary>
>> Yeah. I I didn't touch on it but it's I think it's called like the bots settlement or something. And so they in one of the quarters there's a separate line item on the in the income statement for for specifically that. Um, and the thing I found funny with the whole uh with that whole thing was that the issue was not that they uh or the things that they ended up getting uh fined for, I believe, was not the ones that they actually bought, but that they tormented a bunch as well. And so it was that not that you actually used it. You bought some and you used it, but was more that you there was some that you didn't pay for which you used. And so if they just like bought all of them, I think you may not have had to pay the settlement.
</details>

>> 我对此有一些背景信息。这大概来自 Books3 数据集。这属于陈年旧事了，如果大家感兴趣我可以简单讲讲：GPT-1 和 GPT-2 是在 Books1 和 Books2 数据集上训练的，名称就叫 Books1 和 Books2，是版权清晰的书籍。后来一位开源 AI 人士心想既然 Books1 和 Books2 很好，不如继续扩大，于是创建了一个包含《哈利·波特》等实际版权书籍的非法数据集，命名为 Books3。Books1 和 2 是正式合规的，而 Books3 显然不是。但 Books3 在模型训练圈子里被极其广泛地引用和使用。我不知道 Anthropic 是否恰好是因为 Books3 栽了跟头，但肯定类似——研究人员在学术项目中习惯用它来训练，当时无所谓，但到了商业化阶段问题就暴露了，这一决策代价高达 15 亿美元。

<details><summary>Original English</summary>
>> So uh I have a tiny bit of context about this. Uh this is actually probably from books three. Uh I don't know if you know the context cuz this is kind of deep lore and
>> I can cover it briefly for people who are interested. Um so basically GPT ones and one and two was trained on this data set of books one and two and it it's literally called books one and two. You can go look it up. These are sort of uh copyright clear books. Now uh a random person uh I forget his name now. I think like his name is Sean as well and just from like nowhere just like open source AI person goes like hey books one and two are really good idea uh let's keep going and so he like creates a very very illegal data set of like actual books including like Harry Potter and whatever and calls it books three right uh you you can call things whatever you want but clearly you know books one and two were like official copyright clear books three was not books three but how however books three was like it's like pretty widely cited or used uh in in the model trading circuit. So um I don't know if enthropic was exactly caught by books three but it's going to be something like a books three where uh it was included by somebody in some corpus that was just like okay like you know researchers got used to training on this for like an academic project where it didn't really matter but now it matters for topic and so this decision cost 1.5 billion.
</details>

>> 经过那次和解之后，他们肯定会谨慎得多，对进入训练集的所有内容建立严格得多的溯源机制。

<details><summary>Original English</summary>
>> Yeah. And I'm I'm sure after that settlement they they're going to be a lot more careful and they have much better prominence on everything else that goes into their training uh training sets.
</details>

>> 这场争论本该上诉至最高法院，但并没有。我认为这本可以属于转换性使用（transformative use），毕竟我们把它称为 Transformer，对吧？我被允许去阅读《哈利·波特》，假如我记忆力超群，能凭记忆一字不差地写下来，我的大脑违法了吗？[笑声] 这基本上就是我们在做的事情。虽然涉及机器介入，大模型某种程度上像数据库，情况更复杂一些，但在对待人类与 AI 方面确实存在双重标准。

<details><summary>Original English</summary>
>> I mean so so that was the whole uh discussion that I think should have gone to the Supreme Court. It did not. Um I think
>> yeah I don't I don't think it went to Supreme Court. Um but uh it could be transformative use like we literally call it transformers,
>> right? like like we we are I am allowed to go and read Harry Potter and like maybe I have a perfect memory and I can go somewhere else and write down word for word Harry Potter from memory. Is my brain illegal?
>> Like [laughter] like that's that's like effectively what we're doing. Uh you know just because there's there's machines involved and you can kind of view LMS as databases like maybe that that's like a bit more questionable there. But um you know I I do think that there's some amount of dual standard or double standard when it comes to treating humans versus treating AI differently you know.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 不管怎样，这是目前很有意思的议题。

<details><summary>Original English</summary>
>> Um
>> anyway fun questions for now.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 产品形态、渠道依赖与模型迭代风险

>> 我经常追问大家的一个问题是：Claude Code 到底占了百分之多少？我们是否在意？过去曾经有过披露，比如 Claude Code 带来了 10 亿美元收入、20 亿美元收入。今年二三月份更新达到 20 亿美元后他们就停止披露了。通常停止披露时人们会猜测数据表现不佳。但事实是，Claude Code 作为纯 CLI 工具已不再单独存在，而是被整合进了 Claude 体系和 Claude Co-work。S-1 列出的四款产品中有三款基于 Claude Code，所以可以说 Claude Code 支撑了也许 500 亿美元的收入[笑声]。大家对此争论不休。

<details><summary>Original English</summary>
>> Um so so yeah
>> I think the other thing that I always press people on is like what percent is cloud code? Do we care? You know we used to have these disclosures of like oh cloud code is like 1 billion in revenue. CL code is two billion in revenue. The last update we got by the way was two billion in February or March of this year and then they stopped reporting right. So when people stop reporting usually you assume the number is bad. Um but the the truth is that cloud code as a CLI stopped being a thing like it basically just got adopted into cloud tag and cloud co-work and you know now like three out of the four products that they list on the S1 is like cloud codebased things. So like arguably
>> cloud code is responsible for I don't know like 50 billion in revenue. [laughter]
>> So I I I don't know if that matters. I you know it's this is one of those things that like people debate.
</details>

>> 我原本希望看到但他们未予披露的一点是：实际收入中有多少来自基于底层构建的第一方原生应用，与仅仅通过 API 调用相比有何差异。

<details><summary>Original English</summary>
>> Yeah. Yeah. I think like the other thing I I would have liked to see but they did not disclose which I don't fault them for not doing so is that what percent of actual revenue is coming from you know like these first party applications that you've built on top like the true like you know like like like the actual like you know the end of like versus like you know someone yeah or just
</details>

>> 或者仅仅通过 API 调用底层模型。某人在外部应用中通过 API 调用你，与终端用户直接使用 Claude Co-work 或 Claude Code 是截然不同的。多构建一层抽象，理论上随着时间推移能获得更高的用户留存。

我们知道大约有一半的收入来自渠道合作伙伴，这个比例目前正略微下降，从上升态势降到了 44% 来自渠道伙伴。如果分析主要成本构成：一是算力；二是人力，随着人效提高（每名员工产生的年收入从约 100 万美元提高到了 600 万美元），人力占营收的比重持续走低；三是销售和营销费用，其中大部分并非品牌建设，而是支付给渠道伙伴的费用，大约占渠道伙伴带来收入的 30% 到 35%。

另一个关键披露在于：其 80% 的使用量或大部分收入来自过去 6 个月内发布的模型。结合其大部分收入来自按量计费而非订阅模式的事实，这就形成了一种竞争动态：你绝对不能掉队，否则就会将很大一部分收入置于风险之中。假设他们因为某种原因落后了 3 个月，Gemini 或 OpenAI 推出了非常出色的新模型，而 Anthropic 依然停留在 Opus 5.5。如果企业主要是在 API 层接入并能随时替换，你可能会在瞬间丢失大量市场份额和收入。从公司战略来看，越能引导用户使用自身的第一方应用（例如日常使用 Claude 且有大量定时任务），用户就越不会轻易迁移；但如果纯粹是 API 驱动的使用，收入流失的速度就会快得多。这使得公司陷入一场必须始终保持在价格与性能曲线上各关键节点领跑的竞赛。

<details><summary>Original English</summary>
>> or or just anyone using your if they could use it directly from you but like like a hobby using you and their AP like via an API is pretty different than a consumer using like cloud co-work or cloud code or something where you kind of have like one more level of uh um abstraction that you've kind of built which allows you to like you know arguably have a little bit more of uh retention over time and the reason I say that is like a few things so one is so we do know for for example that about half their revenue is coming from channel partners I think that's actually now going down slightly it was on the way up I think it's now down to 44% it's coming from these channel partners and that they rough roughly are paying if you think about like the big cost right it's pretty much compute which we've touched on people which again is is as a percent of revenue just keeps going down because they are getting more and more efficient I think the revenue per employee is now up to like six million per per year from like from a million or something um and then the third is this kind of the sales and marketing but most of it's not like you know brand building sales and marketing it's like these the fees that paying these channel partners which is about 30% of the revenue 30 to 35% of the revenue that those channel partners are getting for them. Um, but I think the other reason this important is that they disclose that about 80% of their uh most of the model usage uh or most of their revenue comes from models that were released in the last 80% of the usage comes from models released in the last six months. And I think what that the dynamic that kind of ends up creating especially when you add to that fact that most of their revenue comes from usage based plans or from usage based pricing as opposed to like you know subscriptions is that you can't fall behind at all or you you you kind of are putting like a large percent of your revenue at risk. So like if like and I think it would be hard for this to happen but if imagine like for whatever reason like they just fall behind for 3 months and you know there's like you know Gemini's new model is very good, open's new model is very good and um and Anthropics is just like slightly behind for a reason and it's like you're still using Opus 55 is the best that they have and the others are further ahead. you could find yourself in a scenario where because people are just kind of using you at the API layer in some system where they can easily just swap you out that you have lost a lot of shareh suddenly and lost a lot of revenue and so I think that's like a tricky place to be in and so from a company strategy perspective I think you know the more they can get people to use your apps like if you're using you know claude you're not going to switch of like or switch all everything over to chat you might have a bunch of scheduled tasks and you won't do that switch if like you know it's behind for a few months or something but if it's the more it's just APIdriven usage the more risk there is of just people uh you know just like the revenue can go away more quickly as well and so I do think that that is one of the things where you're in this game where you just always have to stay uh and not necessarily at the frontier but also just at the like at every point of the price performance globe that kind of matters from a usage and workload perspective.
</details>

### 上市时机与生态系统的资本流动

>> 总结得太好了。距离 S-1 发布已经过去了几周，情况发生了很大变化。现在追踪的上市概率大概是百分之五十多。对于这次 IPO 是否如期进行，目前处于多么关键的节点？如果他们不上市，会是世界末日吗？如果上市后表现低迷，会是世界末日吗？还是说根本无所谓，只要关注基本面、不用理会股市？

<details><summary>Original English</summary>
Yeah. Amazing. Um I I think that's that's a really good recap of of the state of things. Um okay, so it's been it's been a couple weeks since the S1. Um a lot has changed. Uh we are now tracking um what is it like 50 something% uh probability of IPO? How critical of a moment are we in whether this or not this happens or not? Right. Um if if they don't IPO, is it the end of the world? If they if they do and it still flops, is that the end of the world or is there no end of the world and actually just keep on the fundamentals, screw the forget the stock market?
</details>

>> 我个人的推测是：尽早上市对他们肯定更好，哪怕估值折让 10%、20% 或 30%。因为无限期推迟可能会比以 1.25 万亿而非 1.5 万亿估值上市引发更多的恐慌与不确定性。另一个重要原因在于，整个生态圈的流动性很大程度上依赖于这些领头公司的 IPO。SpaceX 已经上市，而支持后续大规模融资（无论是 Neolabs 还是算力基建）也依赖于这些公司走向公开市场，为风投机构提供流动性，进而让资金回流给 LP，促成新一期基金的募集和对后续企业的投资。

如果推迟到 1 月而非 11 月，并非世界末日；但从总体角度看，在 11 月底前上市可能比等待新年更好，哪怕估值上有一点折让。因为业务基本面很扎实，且他们比 OpenAI 更容易上市。他们肯定希望在同比维持巨大增长的这一年完成挂牌，面临的潜在风险是未来某个月出现环比负增长，那会引发巨大的恐慌。在仍能保持每月 5%、8%、10% 增长时上市是明智的。虽然过去三四个月增速有所放缓，但考虑到其现有体量，整体依然处于惊人的扩张速度中。

<details><summary>Original English</summary>
>> I think that my my guess is that it would probably it definitely would be better for them to even go out sooner rather than later even if that means like you know 10 20 30% like a lower valuation. uh in that like like you know indefinitely delaying it might actually lead to more fear and uncertainty than just like you know going out at like 1.25 instead of 1.5 or whatever that ends up being. Um I I think the the other reason this ends the probably the area this also ends up mattering in is just that so much of liquidity in the in the ecosystem rests on you know these the IPOs of some of these these companies and SpaceX has is the one that has gone out and I think a lot of the continued funding of these very large rounds like you know it's like whether it's like these Neolabs and some of the other like you know like the comput buildout and ecosystem stuff also just relies on hey like these things actually going public and providing liquidity to uh the venture community and then to the the RLPs which then allows them to invest back in the next funds of the VCs that then allows them to invest in the next set of companies and so I do think from that perspective as well it is it is important now I don't think it's going to be the end of the world if it happens in January instead of November but I do think like you know like it probably from an aggregate perspective and I I I wonder what the what the anthropic things, but it might actually be better to go out now like you know like before the end of November as an example than maybe wait for the new year even if that does mean a a slight like kind of discount on the valuation. Um uh yeah cuz I I do think that the fundamentals of this business strongs I don't think I still think it will be the first of the uh between like it will be it'll be easier for them potentially to go out than it would uh and open AAI and I think if you're if you're anthropic you probably still want to go out in this this year you've had where you're still growing like you know at least like on a year-over-year basis like this uh enormous amount because I do think what what they what the risk for them is that you could have like some month where you have like some negative month overmonth growth and then that could actually freak people a lot. Um uh and so you want to go out while you're still growing this you know 5 10 8% a month and uh uh uh um and already like people aren't viewing this as oh you went 10 to 100. I think that is true and they likely will go 10 to 100 but there's also the well in the last three four five months you actually you know your your grow your the growth is declining and so but it still is growing at amazing pace for the the scale it's at so you still want to kind of get out in in that period um um I think
</details>

>> 短期之内是在本月还是下月上市，如果是半年以内其实只是微小的误差。我经常与开发者、工程师和研究人员交流，他们常问：如果是 1.5 万亿左右的估值，未来的 2 倍、5 倍在哪里？会达到 3 万亿、7.5 万亿还是 10 万亿美元？这是巨大的未知数。过去一年多实现了大幅飞跃，未来的持续前景如何？他们试图讲好长期增长的故事，核心就是智能体——在 S-1 中被称为“虚拟协作伙伴（virtual collaborators）”。这是一场必须承担的押注，因为 S-1 展现的只是近期的财务业绩和风险讨论。

<details><summary>Original English</summary>
>> yeah you know like uh look there's the short term like you know is it this month is it next month like look if it's within the next like six months like where you know we're mostly it's like rounding error um when employees are I think they, you know, I I talk to developers and engineers and researchers all the time and they're asking me like, look, okay, it's 1.5ish. Um, and so now now they're looking for the next like 2x, the next 5x, right? Like is it three 3 trillion? Is it 7.5 trillion? Is it 10? And um that's really like the big unknown, right? They had this big jump in the past year plus. Um what is the ongoing prospects, right? And so, um, that's the other thing I I really want to emphasize, which is like they're trying to also tell that story about what's the long-term growth. It's basically agents, uh, they call it virtual collaborators in the the S1. Um, you know, it's and that's a that's a bet that you have to take, right? Like obviously the S1 is not going to tell you anything beyond like recent financial performance and maybe some risk discussion, but that's about it.
</details>

>> 核心议题在于未来一家公司在 Token 上的合理支出是多少，这将决定 Token 总体市场规模，以及 Anthropic 能占据多大份额并在此基础上实现盈利。

有趣的统计数据包括：目前财富 500 强企业中只有约一半在 Anthropic 上每年支出超过 10 万美元，还有 250 家大企业未达到这一门槛；而且在支出超过 10 万美元的企业中，Anthropic 的费用占其总运营开支的比例不到 0.1%。未来几年 Token 支出占企业运营开支的比例即便提升到几个百分点，也将带来 10 到 30 倍的潜在增长空间，甚至不需要底层智能出现巨大飞跃，只需填补技术扩散差距或能力过剩（capability overhang）。但随之而来的问题是：如果不需要前沿模型，需求是否会流向开源权重模型？开源模型竞争激烈会导致利润率走低，而高利润的前沿模型可能只适用于企业中更有限的高端场景。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah, I think this this idea I think this question that people have been debating around what is the right amount over time for a company to spend on kind of tokens and and and and because I think it's like you know you people will have a view on that of like how big is this kind of spend on tokens going to be and then they'll have a view on like what is entropic share of that going to be and then like how is that going to monetize based on where you are in the frontier or like you know the profitability of that. I think other than stat that was interesting from there one was that only today only about half the Fortune 500 spend over a 100k a year on entropic. So I was just wondering like what what are the other two like how are there like still 250 companies in the fortune 500 that aren't spending 100k a year on entropic like that's kind of crazy to me. Um and then the other one was that like off the ones that are spending this over 100k. off that first set. Uh, Enthropic is is under 0.1% of their like aggregate expenses. And so it's like there, you know, you would think that everyone has different views on this, but what is token spend as a percent of opex of expenses for these companies over time going to be? And it's obviously going to vary depending on the kind of company you're in, but my guess is that at least it's going to be like, you know, in the few percentage points and even that could be like, you know, under counting and I'm talking about like, you know, three, five years from now. And so there's probably like a 10 to 30x if you just think about it on just what you're doing now. Even without that much further, you don't need like you know the intelligence to get smart. It's more maybe just the things around it and the actual like you know this this idea of the diffusion gap or the uh uh capability overhang that people talk a lot about. I think as that gets addressed I think this the token usage should just continue to grow. But then I think then the other questions become like okay like what is the if most of the you said you don't need these like the frontier models for will more of that go to open weight will more of that will will the margins on those be low because they're much more price competitive versus like the frontier models where you know people are willing to pay higher prices and stuff and but those might only apply to a smaller set of the use cases than than like you know everything and that's being used in the enterprise.
</details>

### 云与实验室生态、资本回报与生命科学探索

>> 很好。我们接下来讨论更广泛的生态系统，最后再以湿实验室和科学领域作结。对于 Neolabs 和 Neoclouds，你目前看多还是看空？

<details><summary>Original English</summary>
>> Yeah. Yeah. That's great. Uh, cool. Uh, I'm going to play a little bit of like a read around the broader ecosystem and then we'll end with the wet lab stuff and the science stuff. Um, does are you bullish or more bullish or more bearish Neolabs and Neo clouds? You can you can sort of interpret that either way.
</details>

>> 在经历近期估值回调后，以当前定价看，针对普通平均标的而言，我对 Neoclouds 相对更看好一些。如果是一篮子 Neoclouds 与一篮子 Neolabs 对比，Neolabs 阵营可能会诞生一两家极其庞大的伟大公司，从而让整个组合表现超越 Neoclouds；但如果只挑平均水平的标的，Neoclouds 相对更稳妥。而且很多 Neolabs 最终会转变成 Neoclouds，因为它们锁定了大量长期算力，如果找不到生产性用例，最终就会转为算力供应商[笑声]。

<details><summary>Original English</summary>
I I think that a at the current pricing of the NeoClouds post some of this uh dips and stuff probably more bullish on th those ones from like a from if you were just to take like the average one like how that'll turn out. I think if you were to take like a basket of like the Neoclouds versus the Neolabs, I think what's going to happen is that you might you may end up having one of one or two of these Neolabs becoming extremely extremely significant companies. Uh and so I think that basket will may end up like outperforming the Neocloud basket. But if you just take like your average one like you definitely are better off with the Neoclouds, I think. And [laughter] I think the other thing is like many of these neolabs will end up being the neoclouds because they've already bought the compute and if they can't find a productive use for it, they end up
</details>

>> 确实如此，大多数机构都锁定了长期算力，若缺乏生产性用途，就会成为算力供应商。

<details><summary>Original English</summary>
>> Exactly. Yeah. Yeah. Because most of them I think ended up, you know, ended up basically like securing like long-term compute in one way or the other. And so now they could end up if they don't have a productive use for it, then they'll end up being the the supplier of it.
</details>

>> 成为 Neocloud 是 Neolab 的一种失败退出模式。

<details><summary>Original English</summary>
>> Yeah. I mean that that's the you know that's the failure mode of a neocloud um or neo lab is to become a neocloud that's for sure.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 针对推理的盈利能力，我们现在有了更多数据点：Anthropic 的推理和 DeepSeek 的推理都展示出了极高的利润率。DeepSeek 发布了推理架构并表示利润率在 80% 左右。

<details><summary>Original English</summary>
>> Um but I do think like just in terms of the profitability of inference we have now have a couple data points of how profitable anthropic inference is how profitable deepseek inference is because they released the deepse inference stack [clears throat] and they they said it's something like 80 something%.
</details>

>> 这使 Neoclouds 作为投资标的整体更有吸引力，因为不仅证明了 Anthropic 的推理能赚钱，而且 DeepSeek 的尖端架构是开源的。你只需买一机架 GB300 就能开工——虽然实际没那么简单，但 GPU 的投资回报周期不再是 10 年、4 年或 3 年，可能只需 1 年。

<details><summary>Original English</summary>
>> Yeah. So like I think like that should make all neo clouds just gener generally more uh interesting as an investment because not only do we know that anthropic is um profitable but also the state-of-the-art stack with Deepseek is is open source and so you can just buy a rack of GB300s and go nuts and obviously it's not that simple but
>> um you know like the payback period for a GPU is not 10 years it's Not four years, it's not maybe not even 3 years, it might be a year.
</details>

>> SpaceX 在财报电话会议上也表示其基建投资的回报周期不到一年。

<details><summary>Original English</summary>
>> Yeah. Yeah.
>> Uh
>> yeah, [laughter] I think SpaceX SpaceX on their owning squall said that they're seeing the sub sub oneear paybacks on their on their buildouts, right? Which is which is kind of crazy.
</details>

>> 那大家为什么还持怀疑态度？如果这属实，为什么债务市场还会警惕？因为债券市场是最精明的，尽职调查做得最严，而他们正在提高对这些公司的利率。大家之所以要股权融资，正是因为借不到债。

<details><summary>Original English</summary>
>> So So then like why are people skeptical? Like why why are people like why why is if that is actually true? So that this it's probably not true. And the reason is the debt markets are the smartest people in the world, right? They do by far the most due diligence and they are hiking interest rates on all these guys, right? The whole reason we're raising equity is because you can't raise debt.
</details>

>> 我们正处于供需不平衡的特殊时间节点，人们对于何时达到供需平衡看法不一。如果观察开源推理市场，面对像 Fireworks 或 Baseten 等规模化厂商，我不认为长期稳态下开源模型的推理利润率能维持在 Anthropic 的高水平。开源模型对所有人开放，新进入者为了争夺份额会打价格战。在 OpenRouter 上，无论是 Kimi k1.5 还是 GLM，官方实验室定了一个价格，而五到十个第三方服务商能以低至官方一到二折的价格去大幅削价抢份额。因此我认为在纯开源模型代维场景下，提供商长期的毛利率很难超过 40%。这也是为何许多厂商正在转向模型后训练（post-training）和定制化服务，以此构建粘性并获取更高的利润率。

<details><summary>Original English</summary>
>> I don't know. I to me I think one aspect of this is that obviously we are in this moment in time where definitely there is this you know imbalance of supply and demand and so I think people just have a different view or or the different view in terms of when that does end up clearing. I also do think that if you look at like you know anthropics inference numbers I don't think that the at steady state or even right now for example like the open-source inference market where it's like you're just serving inference on these on on the models that are open source like you know you you see different numbers thrown around for the the atcale players there right like the fireworks the base stands of the world uh but I I don't think you know I I don't think at steady state these things end up close to like what the entropic numbers uh for inference just because like that model is available to everyone and someone will will price will will undercut you on price to kind of just get share and I kind of see this playing out. I think I think open router is just like fascinating to look at like you can go look at um you know like go look at like a Kimmy K3 or you know GLM53 like it doesn't really matter what model you look at and you'll see like the set of players on like the official you know the lab itself that made that model like a Kimmy and like the price that they charge at and there are like five and 10 plus like players now that are basically like at like 80% on like basically 20% of that price or even 10% of that price but they are like undercutting the, you know, the the the little what the price that like the Deep Seek themselves might give it at or that like Miniax or whatever might give it at that, they're like undercutting them by like 10x and these are like smaller players, but I do think you're going to continue to see this trend of like, oh, if you try to charge too much, especially in the open source model and depend on the licensing of that model requirements, like there'll just be like some new player like, oh, I have like I'll just capture share now and uh and I'll run it at like 20% gross margins or even 10% u and and as opposed to and and just like capture that share. And so I do think it'll be interesting to see how some of that plays out and settles out. My guess is that I I don't expect any open source inference providence provider to have at least like maybe o over at least like 40% margin longterm on like the vanilla open source tokens which I think is partly the reason why you know you see many of them uh pushing into things like post training and uh uh helping customize models because then that becomes a slightly different uh more lock in slightly different model you're serving and you can maybe uh you know you can benefit from like as you optimize it further and the maybe charge higher have higher margins on those.
</details>

>> 最后我们以湿实验室和科学领域收尾。Dario 对其在“AI for Science”方面的个人抱负非常直率，虽然目前尚未全面铺开，S-1 中具体披露了什么，业内在探讨什么？

<details><summary>Original English</summary>
>> Awesome. Um so I just want to wrap it up with the the wet lab and the sciences uh work. Um Daario has been pretty open about his personal relationship with uh AI for science. Um we haven't seen that much yet. Um what are people first of all what was disclosed and what uh are people talking about there?
</details>

>> 退一步看，Anthropic 签署了高达 9000 亿美元的算力承诺，这是 S-1 中让人瞠目结舌且引发担忧的数据之一。按排期来看，明年他们的算力支出可能达到 700 亿到 800 亿美元，随后年份将增加到 1000 亿至 1200 亿美元的区间。核心问题在于：除 SpaceX 的合作外，这些承诺多具有合同约束力；如果没有足够的外部需求来消化算力该怎么办？这并非一定是因为竞争，也可能是因为技术扩散需要更长时间，编程之后的下一个杀手级应用尚未消耗足够多的 Token。

因此生命科学领域的布局至关重要，它提供了一个完全由 Anthropic 自身掌控的内部算力消耗途径：他们可以成为自身模型的主要使用者，聚焦于科学发现、新材料等前沿突破，而不必受制于外部企业的技术采纳周期。如果技术普及周期的差距拉长，他们至少能将庞大的算力导向这一具备生产力的业务板块。此外，算力还能用于递归自我改进（RSI）来持续强化模型，尽管这不能直接解决客户需求问题。S-1 中也简要提及了机器人，但重点依然在生命科学，通过与药企合作推进管线研发，把模型能力拓展到实体物理世界中。

<details><summary>Original English</summary>
Yeah, I mean so maybe for a step back I think the the other thing is like you know like the the obviously signed like these like 900 billion of comput of compute commitments which has been you know one of the kind of like eyepopping figures in the S1 that has some people worried and I think to me the question for seeing the applic they have like a rough schedule and so let's say that you know next year they might end up having compute expensive 70 to 80 billion the following year onwards it ramps to like more like the 100 120 billion range And so the question becomes like what happens given that you know these are like mostly contractual other than the SpaceX one. Uh what happens if you don't have enough demand to serve it which is you know like is obviously not a great scenario but it could happen and the reason it could happen is just that um uh it doesn't have to do with anything around even just competition and things. It could just be that diffusion takes longer and so you don't have it's it just you know beyond coding that next thing isn't using as much tokens yet you don't have that next thing and so I think the life sciences stuff is important because it provides like a some use of that compute that is more in anthropic's own control where you can focus your models and then hey like let's we will be the primary user of our own models and and help with you know you could partner with companies obviously, but like you'd be then looking for these novel discoveries and and it doesn't have to be just life sciences or it could be any kinds of things in science, new materials, uh new things like that. And so I think it's really important there because it it it it then means that at least you have an avenue where you can direct compute to which has another way of being productive that isn't dependent on timelines of of enterprises and uh and others to adopt your technology. And so if this diffusion gap ends up bit being long being wider or takes longer you have this kind of this other business segment where you can direct some of the uh compute to and so I think it's important from from that perspective um uh uh beyond just like you know just further the other obviously big use of computers RSI as well and and just making the models better and better but I think that's may not still solve the customer demand piece whereas like having like these life sciences bats and I think they also touched on robotics a a little bit but not as much as life sciences. Like having those then also puts you in a different um having some of these other things that are expanding to physical world but then also things that may be a bit more in your control where you are operating these to try to find like make novel discoveries and that you yourself are you know potentially with the farmer partners taking through the the the pipeline.
</details>

>> 太棒了。最后有什么寄语给创业者和听众吗？

<details><summary>Original English</summary>
>> Yeah. Awesome. Um, all right. Any parting thoughts, um, messages for people, founders, you know, talking to Wing, whatever.
</details>

>> 没有特别的了。我认为未来的走势会非常精彩，很好奇接下来的几个月会发生什么。在他们正式挂牌之前，大家都会极其密切关注其具体的月度营收环比增长。

<details><summary>Original English</summary>
>> Uh, no parts. I mean, I think it's going to be very interesting to see how this plays out. And, uh, I'm curious to see what the next couple months look like. And I think until they go public, the the number that everyone's going to be watching very closely is just like the month over month the the actual revenue growth for them. So
</details>

>> 是的，这就是为什么早上市比晚上市更好，否则他们就必须设法刺激下一轮 Token 消费狂潮。

<details><summary>Original English</summary>
>> yeah, it's going to be [laughter] which is why it's better for them to do it sooner rather than later. Otherwise, it's like they have to like somehow like encourage a token max for the next
</details>

>> 那样的话他们就必须推出 Claude 5.5，或者更强大的模型来带动关注度和使用量。

<details><summary>Original English</summary>
>> Yeah, I mean in that case they need to release Fable 5.5. Um
>> yeah,
>> and uh you know, whatever is beyond that, but yeah, I mean that that would obviously be a driver of more attention and and usage and that would that is a lever that they have to pull.
</details>

>> 无论如何，感谢你带我们梳理这些内容。我只是想让大家在面对这一事件时有扎实的认知基础。许多工程师在考虑是否加入或兑现期权，整个市场也都在关注，因为 Anthropic 是这一年期内三家引领前沿的实验室 IPO 之一。这对于 OpenAI 的 IPO 也至关重要，如果 Anthropic 遭遇挫折，OpenAI 可能就不会上市了，那将带来多方面的负面打击。目前是一个非常关键的节点，拭目以待。感谢你的解读。

<details><summary>Original English</summary>
>> Um but regardless, thank you for taking us through. Uh, you know, I I'm I'm really just trying to give people a good grounding on what they should know going into this. I think a lot of engineers are wondering if they should join, if they should cash out, you know, same thing for just like the general broad rest of the market because Anthropic is probably, you know, one of the uh the three IPOs that are, you know, happening that are the leading frontier labs in in this sort of one-year period. Uh and I I do think it really matters for the OpenI IPO which um if I you know anthropics fails in whatever shape shape or form and anthrop OpenI was just not going to do it. Um and that that's that's sucks for multiple reasons. Um
>> yeah so uh pretty pivotal moment. We'll we'll see. [laughter] Thank you for covering it.
</details>

>> 感谢邀请，探讨这些非常愉快。我很喜欢你们输出的内容，会继续收听并保持关注。

<details><summary>Original English</summary>
>> Yeah. Yeah. Thank you for having me. It was great to great to discuss and uh yeah love your love the stuff you put out and so uh we'll we'll continue to listen and excited to follow along.
</details>

>> 大家也可以去阅读他的 Substack 以及关注 Deploy Codes。我们正在开启一档针对前沿工程方向的播客，非常令人期待。无论公司上市与否，AI 时代已经到来，我们都必须将其落地部署。

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

>> 谢谢，下周见。

<details><summary>Original English</summary>
>> Thanks. See you next week.
</details>