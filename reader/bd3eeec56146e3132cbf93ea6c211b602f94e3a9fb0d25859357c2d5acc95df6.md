---
author: Joseph Wang
date: '2026-08-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KYirz5POgZg
speaker: Joseph Wang
tags:
  - treasury-yield
  - operation-twist
  - liquidity-management
  - yield-curve-control
  - government-debt
title: 美债收益率飙升至5.3%：财政部扭曲操作与多维政策工具箱解析
summary: 面对美国30年期国债收益率攀升至5.3%的历史高位，财政部打破惯例启动扩大回购计划进行'财政部扭曲操作'（Treasury Twist）。本文深度剖析国债回购的底层机制、流动性管理与久期缩短效应，并探讨削减长债发行、施压商业银行增持、调动政府赞助企业（GSEs）以及美联储收益率曲线控制（YCC）等后续政策工具。
insight: ''
draft: true
series: ''
category: investment-assets
area: finance-wealth
project: []
people:
  - Scott Bessent
companies_orgs:
  - US Treasury
  - Federal Reserve
  - FHFA
  - Fannie Mae
  - Freddie Mac
products_models: []
media_books: []
status: evergreen
---
### 破位冲高：长端美债收益率失控与财政部非常规干预

在通常平静的8月下旬，全球金融市场掀起巨浪。**美国30年期国债收益率**（US 30-year Treasury yield）持续攀升至 5.3% 的历史高位，创下自 2008 年全球金融危机以来的最高水平。这一轮长端债券抛售潮的背后交织着多重宏观驱动力：首要因素是地缘冲突（伊朗战事）推高全球能源价格所引发的输入型通胀预期；其次是市场对美联储抗通胀决心的怀疑，尤其是美联储主席在近期 FOMC 会议上对通胀目标表达模糊，动摇了债市对货币政策锚定的信心；此外，科技巨头等超大规模企业（Hyperscalers）海量发债产生的挤出效应，以及股票市场强势表现导致的风险偏好分流，均加速了长债收益率的上行。

面对突破容忍极限的 5.3% 收益率，美国财政部长 **Scott Bessent** 最终选择主动出击。财政部在年中打破通常仅在季度再融资声明（Quarterly Refunding Announcements）中调整政策的惯例，突发宣布扩大针对长端国债的**国债回购计划**（Treasury Buyback Program）。这一未经预告的非周期性干预，明确释放出财政部不容忍长端收益率继续无序走高的政策信号。

<details>
<summary>Original English</summary>

Hello my friends. Today is August 22nd and this is Markets Weekly. All right guys, so last week was supposed to be a very quiet summer week, but it was actually super exciting. It seems like Secretary Bessent finally got tired of watching long bond yield rise every single day and he's calling time and actually doing something about it. So today, let's talk about the Treasury buyback program that Bessent is doing to try to conduct a Treasury twist to lower elongated yields. And let's talk about some next steps the Treasury could do to further lower yields because it looks like what he's doing so far may not be enough. And the Treasury actually really does have a large toolkit as Secretary Bessent suggests.

All right, starting with the buybacks or the Treasury twist as Bessent notes. Now, for context, look at this chart of the US 30-year bond yield. You can see that it's been rising relentlessly. And actually, we just did an episode on this last week that you can check out. In short, there's a number of stories why the long bond yield keeps rising. First and foremost, of course, is that this is a global movement driven by the war in Iran driving up energy prices. So everywhere in the world the long bond yields are rising mostly because energy prices are rising. You also have concerns about the Fed's commitment to its inflation target. Kevin's last performance at his FOMC meeting was very concerning because he suggested that you know maybe he's not going to target PCE. Maybe he's going to target something else that he doesn't want to tell you about. And that of course shakes the bond market's confidence in the Fed as someone who cares about inflation. You also have another a few more market-based stories where you can say that for example the hyperscalers are issuing a lot of debt crowding out treasuries or you can say that the equity market is doing so well that 5% long bond yields are just not enough. In any case the long bond yield keeps going up and up and up and at 5.3% it is historically high. It's heights it's been since before the 2008 financial crisis.

Now it's been higher in the past, say the 1970s and 80s, but also remember that back then inflation, you know, was like 10%. So the long bond yield is historically high and there's a lot of things the government can do to stop this, but you don't know whether or not they're going to do this until they actually show that they are concerned. And last week there was a very strong indication that the Treasury had had enough of the long bond yield rising. So last week in the middle of a week there was an announcement that the US Treasury would upsize its buyback program in the Longan sector. Now this first off is an extraordinary thing to do. Usually when the Treasury makes adjustments to its buyback program, it does it at its quarterly refunding announcements which was just a few weeks ago. So this out of the blue unanticipated is clearly a response to changing market conditions. The Treasury does not like what it sees. 5.3% on the long end is too much for them.

</details>

---

### 解构国债回购：流动性润滑还是财政版扭曲操作？

美国财政部的国债回购机制最初由上一届政府引入，在制度设计上包含两大官方支柱：**现金管理**（Cash Management）与**流动性管理**（Liquidity Management）。
* **现金管理**: 由于财政收入流入高度集中（如4月报税季和季度企业预缴税），而政府支出相对平滑，财政部在特定月份会积累大量闲置现金。通过回购并提前退役国债（如回购短期国库券），财政部可以高效利用过剩现金、减少纳税人利息负担。
* **流动性管理**: 国债市场并非如股票交易所那般所有标的具备同等流动性。国债按发行批次拥有独立的 **CUSIP 编码**。新发行的基准国债被称为**在跑国债**（On-the-Run Treasuries: 交易活跃度最高、流动性最好的最新批次），而历史发行的存量国债则迅速沦为**离跑国债**（Off-the-Run Treasuries: 随时间推移流动性显著折价的非基准老券）。当做市商（一级交易商）因资产负债表受限而不愿为老券报价时，通过数学拟合模型（如三次样条曲线 Spline）可观察到老券相对理论价格出现显著的流动性溢价。此时财政部扮演“终极做市商”（Dealer of Last Resort），从一级交易商手中回购离跑国债，并相应发行在跑国债以维持总体存续久期中性。

然而，在上一任政府反复强调回购“不改变久期、遵循规律且可预测发行”的基调下，本次 Bessent 治下的财政部撕下了流动性中性的伪装。在 CNBC 的采访中，Bessent 直接将此操作定性为**财政部扭曲操作**（Treasury Twist: 财政部通过发行超短端国库券 Bills 筹资以回购长端国债 Bonds，主动缩短未偿债务加权久期以压低长端利率）。这种将 2012 年美联储公开市场“扭曲操作”转移到财政部资产负债表端实施的做法，本质上是借助发行短端替代长端，重构长债供需平衡。尽管在宣布当日 30 年期美债收益率应声回落约 9 个基点，但随后两天在油价飙升的压制下悉数回吐，表明当前规模的回购尚不足以彻底扭转宏观冲击。

<details>
<summary>Original English</summary>

So what exactly is the buyback program? Well, first off, the buyback program is something that was introduced by the last administration and it really has two aims. The first aim is cash management and the second aim is liquidity management. So cash management is some of is it's a more benign and understandable thing. So cash management if you're think about things from the treasury perspective you'll notice that your cash inflows are very lumpy. So you get a ton of money coming in in April when everyone pays taxes and then you get some money coming in on quarterly corporate taxes estimated taxes and you know maybe tariffs and stuff like that. But because your cash inflow is lumpy and your cash spending is not as lumpy sometimes you will end up with much more cash than you want. And so if you can have buybacks back then, maybe you could just, you know, deploy some of that excess cash by retiring treasury debt, saving the taxpayer some money. So in April when you have huge inflows from tax receipts, maybe you have more money than you need, you can use that and buy back some bills. So that was, I think, a totally reasonable way to do buybacks.

Another goal of the buyback operation is to help with treasury market liquidity which I think is the much more important part of it. So the treasury market it's not like the stock market whereas say if you want to buy Apple stock there's this Apple ticker you find it on your brokerage screen and you buy it and Apple was traded on exchange and everything goes well. So the treasury market is I guess you can say a lot messier in the sense that there's just not one ticker. Every Treasury issuance has a unique QIP ID. So for example, if the Treasury auctioned off a 10-year Treasury security, that tenure would have a QIP and a few months later when an auctions a new vintage of 10 year then that new vintage is going to have a another QIP. So you can think of the treasury market as a collection of many QIPs and each QIP will have different coupons and different liquidity profiles. If you're interested, I talk about this in my book Central Banking 101. Also have a online course on the treasury market on centralbanking101.com.

So one of the properties of the treasury market is that the newly auctioned treasuries we call them on the runs are very liquid but the older issues formally issued treasuries in the past are less liquid and we call them off therun treasuries and as a treasury becomes progressively off therun so let's say something that was issued a few years ago it becomes pretty illiquid so that becomes a problem for market functioning. So, one of the ways that you could improve this is if the Treasury could act as a dealer of last resort and offer primary dealers a way to offload their less liquid securities. So, if that were the case, primary dealers would be more willing to make markets in off the run treasuries knowing that at the end of the day, they could always sell these securities to the US government so they wouldn't be stuck with them. So the way that the treasury would do this is that for example how do you measure liquidity in the treasury market? There's actually a lot of ways to do this. Some popular ways would be for example to look at how off the runs trade with respect to a mathematical model. We call this to spline for example if your mathematical model tells you that a 30-year Treasury should be trading at 5% but you have one off the run that's trading at you know 5.2%, that's probably an illiquidity premium and that suggests some liquidity problems in the Treasury market. And there's many ways to measure this. And so, according to this Treasury presentation, after the buyback program was announced, there was notable improvements in liquidity in the Treasury market.

So one of the things that the prior administration was very strong to emphasize was that this liquidity management program these buyback programs are not meant to change the duration of the treasury market. So the way that they would finance these buyback programs would simply just to be issued on the runs. For example, if they were to buy back a 30-year Treasury, the way they would finance this was just to issue more 30-year treasuries. So, in a sense, it's issuing on the runs to buy back off the runs. So, they wanted to emphasize this because they wanted to tell everyone that, you know, this is not some kind of gimmick. We are going to issue in a regular and predictable way. Changes in coupon sizes will be done through changes at the quarterly refunding where we will announce auction sizes. After all, we are respectable people. But of course all the I guess more conspiracy oriented people or maybe just the straight up more clever people at the time knew that this was something that had tremendous potential to control the yield curve and I have written about this in the past.

But anyway, now we have a different administration. So last week, Bessant announced this buyback program and so the question was is this just to improve liquidity in the 30-year whereas you're be issuing more on the runs to buy back off the runs as the program was originally intended or is this really changing the duration of the treasury's outstanding as a way to suppress yields and Besson was actually pretty candid about this in an interview he gave with CNBC where he called this a treasury twist. "That in terms of being willing to do, you know, what I would call a Treasury twist here in terms of the bond market, what do I know that the market doesn't know?" So that's very obviously means that he's going to be issuing bills to buy back bonds and that's going to shorten the duration of the treasury outstanding just by a little bit. And of course, he could totally upsize his buyback programs. And really, there's no limit to this. He could just really buy it all if he really wanted to. So, he's going to probably keep doing this until he gets the outcome that he wants.

Now, for those of you who actually are following this in the past, Operation Twist is something the Fed did in 2012 where they reduced their holdings of short dated treasuries to and to increase their holdings of longerdated treasuries. It was a way of course to put downward pressure on longer dated interest. That time the Fed is doing it. This time the Treasury is doing it. So on the day that this was announced, we have the long bond basically rally. So yields go down by about nine basis points. In the next two days, they basically gave it all back up. To be fair, we also had constant increase in oil prices those days and that kind of drove up yields globally. So at the end of the day, this so far has not been successful, but really I wouldn't sweat it because they really do have the firepower to make this work.

</details>

---

### 财政政策第二阶：直接削减长债拍卖规模

如果基础规模的回购无法有效压制收益率，财政部在自身权责范围内最具杀伤力的下一步棋，便是直接在供给侧动刀——**单边下调长端国债拍卖规模**（Cut Auction Issuance Sizes Outright）。

在超长端债券市场中，微观供求结构对定价的决定性往往超过市场对美联储远期政策利率路径的预期。通过直接减少 10 年、20 年、30 年期长债的供给份额，能够对收益率产生立竿见影的机械性下压效果。这一策略近期已在日本国债市场（JGB）得到了实证检验：面对 40 年期国债收益率的急剧走高，日本财务省通过连续公开削减 40 年期拍卖配额，引发了超长端收益率的断崖式回落。尽管日本的经验表明这种供需干预带来的收益率下行在数周后可能因外部宏观环境而逐步钝化，但它确实能为财政当局争取到极其宝贵的时间窗口。

<details>
<summary>Original English</summary>

So the second thing we want to talk about is what else the Treasury can do supposing that this has not had impact that they wanted. So first off, as we noted before, if four billion, at least four billion or whatever number they're doing is not enough to lower long bond yields, they can just upsize this enormously again. So this is relying on the belief, the theory that for the long bond, supply and demand matter more than the expected path of Fed policy, which of course I think that's pretty commonly accepted. So by simply reducing the supply of long bonds, you could actually have impacts on the yield. And we did see that on announcement day. But again, you're fighting against the relentless rise in oil prices. So that is a problem.

So assuming this is not enough, the next step the Treasury could do is of course a very common and straightforward thing to do and that is cut issuance sizes outright. Now they already hinted about this at the last Treasury refunding announcement show and we talked about this last week. Should check out that video. So if they were to cut long end issuance sizes that would also very clearly send a strong signal to the markets and mechanically have less supply and that would have a notable downward shift in the long bond yield. Now this is something most recently deployed in Japan. So in Japan they had some problems with their 40-year bond yield to be precise and they have consistently been cutting sizes in their 40-year auctions. So you can see that in their public announcements and it has had a very notable impact on 40-year bond yields over there. You can see that upon announcement there was this huge huge implosion in 40-year yields. However, though you'll have to also note that the improvement was it lasted for some weeks but ultimately temporary. So this definitely buys time definitely very impactful. But unless we have some resolution there on the Iran war, I think it's going to be quite difficult.

</details>

---

### 监管资本与准政府杠杆：调动商业银行与GSEs入场托底

超越财政部独立操作的边界，行政部门还拥有深度的金融监管与准官方机构调动能力：
1. **监管道德规劝与银行资产配置（Moral Suasion & Bank Regulations）**: 类似土耳其在选举期间强制国内银行系统承接政府债券以压制收益率的做法，美国监管当局对大型商业银行拥有巨大的自由裁量权。无论是银行间的并购重组审批，还是关于巴塞尔协议（Basel）资本充足率与补充杠杆率（SLR）的监管松绑，监管部门均可作为筹码，引导商业银行以“履行爱国义务”或优化合规资产为由，大规模吸纳国债资产。
2. **调动政府赞助企业（Leveraging GSEs）**: 回溯此前抵押贷款利率过高时期，美国联邦住房金融局（FHFA）局长曾直接指令**房利美**（Fannie Mae）与**房地美**（Freddie Mac）两大政府赞助企业入场收购 2000 亿美元抵押贷款支持证券（MBS）。相同的行政逻辑完全可以复刻于国债市场——通过指示 GSEs 发行短期机构债筹资，进而利用杠杆在二级市场大举扫货长端美债，发挥准财政后备军的吞吐托底作用。

<details>
<summary>Original English</summary>

Now, moving beyond these more treasury only things, there's also other things they can do. Now, there's this very interesting post by a professor of economics in Turkey showing that in Turkey when they wanted to suppress yields, what they did was they forced the banks to load up on bonds and that suppressed yields for a period of time. Actually apparently through the election and then once the election was over everything went back to normal. So a next thing they could do is to heavily encourage banks to buy more treasuries. Again the US government is a regulator of commercial banks and of course the banks kind of need government support to do all sorts of things. For example, let's say you're a bank and you wanted to have a merger with another bank. Usually that requires an okay by the regulators and you know maybe you can say that hey you want to do this merger great how many treasury bonds do you have or maybe if you can go talk to a mega bank and say hey you know we hear that you're concerned about you know regulation you know Basel and all that stuff hey we've been doing really a lot of work to make your businesses more profitable more successful could you help us out with this thing about the the bonds after a while we did reduce your capital requirements so you know why don't you do the patriotic thing. So that's something that could happen as well.

And something else that could happen is if you think back to, for example, when mortgage rates were too high, you had director of the FHFA just, you know, command Fannie Mae and Freddie Mac to go out and buy $200 billion in mortgage bonds to try to lower interest rates. And the director, although not best friends with Bessent, is someone who I think really wants to please the president. So, I see no reason why he couldn't ask Fannie Mae and Freddie Mac to lever up issue a whole bunch of short-term agency debentures and just go and buy a whole bunch of treasury bonds as well. So, remember the government has all sorts of government sponsored enterprises that they basically control and can go and force to go and buy bonds. So, there is so many many things that they can do.

</details>

---

### 终极核选项：美联储三重法定职责与收益率曲线控制

在政策工具阶梯的顶端，最终极的干预来自于直接动用**美联储**（Federal Reserve）的资产负债表。
* **历史实践与机制可行性**: 市场常有观点认为收益率曲线控制（YCC: Yield Curve Control，央行承诺无限量买入特定期限国债以将其收益率锚定在目标水平以下）在现代大型经济体不可行，但历史与现实证明该论调并不成立。美国在 1940 年代二战时期曾成功实施过 YCC，而日本央行在政府债务占 GDP 比重两倍于美国的情况下依然长期维持了 YCC 操作。拥有无限法币发行权的央行在技术上实现 YCC 轻而易举，其核心代价并非技术可行性，而是对汇率贬值与潜在通胀的负面反噬。
* **第三法定使命的政治博弈**: 尽管美联储独立运作，但《联邦储备法》赋予美联储的法定职责实际上包含三项——**物价稳定**（Price Stability）、**充分就业**（Maximum Employment）以及经常被忽视的**适度长期利率**（Moderate Long-term Interest Rates）。由于“适度”一词在法律上缺乏明确的数值定义，这一模糊地带为行政部门向美联储施加政治舆论压力提供了合法的制度切入点。

综合来看，5.3% 的长端国债收益率已触及决策层的红线。从加大回购规模、削减长债供给，到动员银行体系、调动 GSEs，直至最终寻求央行层面的干预，政府拥有极其充裕的干预弹药库。长端收益率进一步无序冲高的空间已被多重政策工具锁死，而一旦中东地缘冲突迎来实质性缓和，30 年期美债收益率重回 5% 下方将是大概率事件。

<details>
<summary>Original English</summary>

The ultimate thing that could be done of course is to get the Fed involved. I think we're, you know, really far from that. There are so many other things that we can do first. The nuclear option of course is yield curve control which the US did in the 1940s and Japan did recently even though the debt to GDP ratio of Japan is like twice as high as the US. There are some people who saying that oh no you can't do yield curve control but that's total nonsense right if you have a money printer you can do yield curve control super easy. It will have negative implications on the currency and other stuff but you can easily do it.

One other thing you can talk about is so as I've suggested on Twitter the Fed has actually three mandates right: price stability, full employment, and of course moderate long-term interest rates. Now what is moderate long-term interest rates? Nobody knows. And that's kind of the beauty of it. If nobody knows, you know, you can point to this and make an argument and try to get the Fed to do something. Again, that's more difficult, but having that third mandate really opens up the door to at least make some sort of political argument that could open the door to some sort of action.

So, in any case, the important thing that I take away from this episode is that 5.3% on the long bond is too much for the Treasury and they're going to do something about it. And what I believe is that they have more than enough tools in the toolkit to handle this. So, I'm really not worried about yields going higher anymore. Of course, the best thing, of course, would be some sort of resolution in the Iran war. When that happens, I could easily see the long bond below 5%. Hopefully that'll happen soon. All right, so next week is going to be another exciting week. We'll see if the bond market tests the Treasury Secretary's resolve. Anyway, find out on Monday. All right, talk to you guys next week.

</details>