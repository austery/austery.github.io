---
author: All-In Podcast
date: '2026-04-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mjNP5IOzCbA
speaker: All-In Podcast
tags:
  - defense-tech
  - industrial-base
  - deterrence
  - autonomous-systems
  - geopolitics
title: 现代战争的现状：Palantir 与 Anduril 高管深度解析无人机、AI 与传统国防的重塑
summary: 本访谈由 All-In 播客主持，对话 Anduril 联合创始人 Trey Stephens 与 Palantir 首席技术官 Shyam Sankar。内容涵盖了美国国防工业基地的萎缩与重塑、硅谷对国防态度的转变、现代战争中的软件定义硬件、威慑力量的本质，以及 AI 自动系统在伦理与效能方面的平衡。专家们警示了关键供应链的风险，并展望了美国重新工业化的未来愿景。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Palantir
  - Anduril
  - SpaceX
  - Founders Fund
  - Lockheed Martin
  - Department of Defense
products_models:
  - Foundry
  - Lattice
  - Arsenal
  - Starship
  - F-35
media_books: []
status: evergreen
---
### 序言：Palantir 与 Anduril 的渊源

**主持人**: **Trey Stephens**，**Shyam Sankar**，欢迎来到在希尔与谷地论坛（Hill and Valley Forum）录制的 All-In 播客。感谢二位到来。最近怎么样？

<details>
<summary>Original English</summary>

**Trey/Shyam**: Thanks for having us. Doing great. Good to be here, too.

</details>

**主持人**: 你们两个是老朋友了对吧？认识很久了。

<details>
<summary>Original English</summary>

**Trey/Shyam**: A really long time.

</details>

**主持人**: 给我们讲讲你们是怎么认识的。**Palantir** 和 **Anduril** 之间有什么联系和历史？

<details>
<summary>Original English</summary>

**Trey Stephens**: Well, I'll start. You can fill in all the gaps.

**Shyam Sankar**: I feel like I know the story you're going to tell and it's going to be very uncomfortable.

</details>

**Shyam Sankar**: 在 **Palantir** 早期，我到处奔走，给任何可能想看的人做演示。**Trey** 当时在一家情报机构工作，碰巧看到了其中一个演示。他应该告诉你他的版本，关于他对官僚主义的挫败感。但我认为他当时意识到，嘿，这可能真的很酷。也许我应该离开那个该死的地窖办公室，不再整天和同事聊体育却一事无成，而是加入这场“远征”。于是 **Trey** 主动联系并申请了。但他犯了个大错：他大老远跑去帕罗奥图（Palo Alto），结果穿了一套完整的**西装领带**，还戴着 **CIA 的袖扣**，请注意。

<details>
<summary>Original English</summary>

**Shyam Sankar**: So Trey, I think you know in the early days of Palantir, I was roaming around giving demos to anyone who could possibly want to see them. Trey was working in an intel agency and happened to see one of these demos and he should tell you his version of it, his side of it, his frustration with bureaucracy, but I think he realized like, hey, this might be really cool. Maybe I should leave the hell hole I'm in in the basement of this building getting nothing done, talking about sports with other people to go join this crusade. So Trey reached out and applied. He made a big faux pas. He came all the way to Palo Alto and he wore a full-on suit, tie, cufflinks—CIA cufflinks, mind you.

</details>

**Shyam Sankar**: 来面试时，我们可能只有 20 个人，大家都穿着 T 恤和旧衣服。他在大厅被接待员拦住了，接待员人很好，告诉他赶紧把领带扔了，试着穿得休闲点，别把事情搞砸。但我们立刻就喜欢上了他，他帮助我们建立了**政府业务**。

<details>
<summary>Original English</summary>

**Shyam Sankar**: Coming to interview with, I don't know, we were probably 20 people, you know, who wore t-shirts and, you know, second hand-me-down clothes. And he was intercepted in the lobby by a receptionist who really cared about him and told him to ditch the tie and try to dress down and don't screw it up too bad. But we loved him immediately and he helped us build the government business.

</details>

**主持人**: 所以那是在 **Palantir**。你是第 13 号员工，那是 2006 年左右对吧？非常早期。

<details>
<summary>Original English</summary>

**Trey Stephens**: Yeah. I came in in early 2008, but there were still, you know, 25-30 people at that point.

</details>

### 国防哲学的重塑：隐私、安全与威慑

**主持人**: **Peter Thiel** 在最开始的时候参与了孵化对吧？也许你可以回顾一下，因为很多人知道 **Palantir** 的历史，但在那个只有一小群人的时代，你们是如何摸索出商业模式的？

<details>
<summary>Original English</summary>

**Shyam Sankar**: Yeah, it was one of those things that was kind of a slow start. There was a real idea amongst the five co-founders, including Peter, that it's kind of insane to live in a world post-9/11 where people are arguing about what's more important, privacy or security. Aren't they both really important? And who is actually spending time pushing out the **efficient frontier**? For any amount of given security, you should have more privacy than you had before, or any amount of given privacy, you should have more security. This sort of changing the dialectic there was really the entire impetus of what we started with. Now there's a technical approach that follows from that, an approach to privacy and civil liberties. But really we started as a business that was pretty myopically focused on solving a handful of problems in **counterterrorism** for a few institutions in the world.

</details>

**主持人**: 让我问一个对广大观众都很重要的问题，也是为了让你们两位阐述个人哲学观点：**战争是好事吗？** 现在有很多关于“**军工复合体**（Military-Industrial Complex）”有战争动机的讨论。你们做这些工作的哲学动力是什么？你们如何看待战争、国防以及你们公司追求的事业？

<details>
<summary>Original English</summary>

**Shyam Sankar**: Well, anyone who's been to war would tell you that war is awful. War is bad. Categorically bad. That doesn't mean it's always avoidable. There are people who will want to use might to make right to define a set of rules. And you have to be in a position to protect your people and your interests accordingly.

</details>

**Trey Stephens**: 归根结底，一切都关乎**威慑**（Deterrence）。你不想打仗，但你必须做好准备，以便如果万一开战，你能果断且迅速地取胜。我从未见过哪个将军会说：“你知道我今天最想做的事吗？我想打电话告诉家长们，他们的孩子在战斗中牺牲了。”没人想这么做。我认为我们在 **Palantir** 以及现在在 **Anduril** 所做的一切，目标都是为了让你的对手感到挑战你是**不可想象的**（unthinkable）。

<details>
<summary>Original English</summary>

**Trey Stephens**: At the end of the day, it's all about deterrence. You don't want to go to war, but you want to be prepared so that if you do have to go to war, that you will win decisively and quickly. I've never met a general that has said, "You know what I really want to do today? I want to make phone calls letting parents know that their children have died in combat." Nobody wants to do that. And I think that that's really the goal of everything we were working on at Palantir and what we're working on at Anduril, which is make it unthinkable to your adversaries that they should ever challenge you.

</details>

### 硅谷与国防的“破冰”

**主持人**: 为什么在很长一段时间里，特别是在硅谷，建立一家国防公司或服务于国防部门的技术公司被视为禁忌和不受欢迎的领域？

<details>
<summary>Original English</summary>

**Shyam Sankar**: I think it's a beautiful consequence—and I mean it unironically—of the peaceful world that we lived in. The origin story of Silicon Valley is actually defense. **Lockheed** was the largest employer in Silicon Valley in the 1950s. The **Corona spy satellites** were built there. In a world gripped by the threat of the Soviet Union, Silicon Valley有完全不同的姿态。但在“冷战结束”、“历史终结”后的世界，在全球化万岁的观点下，这些事情被看得更加愤世嫉俗，威胁似乎并不真实。

</details>

**Shyam Sankar**: 我认为你可以追溯到硅谷真正醒悟的时刻，就是当**俄罗斯坦克越过乌克兰边境**的时候。硅谷有很多乌克兰人和东欧人受此影响。他们意识到，这比单纯引用艾森豪威尔关于军工复合体的名言要复杂得多。有趣的是，许多抗议硅谷参与国家安全项目的人，正是那些在社交媒体个人简介里挂着**乌克兰国旗**的人。这显然存在政策或理解上的错配。另外，现在的科技巨头是全球化的，它们不一定视自己为美国公司，抗议者中也有很多非美国公民。

<details>
<summary>Original English</summary>

**Shyam Sankar**: I think many of the people who were protesting Silicon Valley's involvement in working on national security priorities were the exact same people that had a Ukraine flag in their bio. So there's clearly just a policy mismatch or an understanding mismatch. The other thing I would mention is that these large tech companies, unlike many epics prior, were global technology companies. They didn't necessarily view themselves as American. A lot of the signatures on these protests were not coming from US citizens.

</details>

**主持人**: 你觉得最近这种情况改变了吗？

<details>
<summary>Original English</summary>

**Trey Stephens**: I think that there's just an increased awareness of the complexity of the geopolitical situation. It's certainly a lot less controversial to work on these topics than it was in 2017 or 2018.

</details>

### 美国工业基地的萎缩与挑战

**主持人**: 有人说硅谷正在接管国防，硅谷是美国战争机器的新篇章。能否回应一下，从二战结束到今天，国防工业发生了怎样的演变？

<details>
<summary>Original English</summary>

**Shyam Sankar**: The industrial base that won World War II and the early Cold War was not a "defense" industrial base. It was an **American industrial base**. **Chrysler** made the Minuteman ICBM—they were the prime contractor—同时他们也造面包车。**General Mills** 这家麦片公司曾有一个机械部门，利用研发谷物处理的技术来制造鱼雷和惯性导航系统。**Ford** 直到 1990 年还在造卫星。整个经济不仅在投资繁荣，还在为保障繁荣的自由提供担保。

</details>

**Shyam Sankar**: 现在的结构发生了剧变。1989 年柏林墙倒塌时，只有 6% 的主要武器系统支出流向了纯国防公司，94% 流向了**军民两用公司**。而今天，**86% 的支出流向了国防专业公司**。这种结构的改变导致了极其病态的叙事，认为如果情况变糟，我们可以像二战那样一夜之间把汽车工厂变成军工厂。但历史现实是，二战时的动员花了 **18 个月**。今天，当乌克兰在 10 周内耗尽了 10 年的产量时，这本应是一个“五级火警”信号：我们对**威慑**的基本计算错了。我们以为库存能威慑对手，但真正的威慑力始终是**工厂**——即产生和再生库存的能力。

<details>
<summary>Original English</summary>

**Shyam Sankar**: That figure today is 86% goes to defense specialists. We have a very different structure of the US economy as a result. And it leads to very perverse narratives of what it would be like to mobilize if things got really bad. It took 18 months to do that [in WWII]. When Ukraine went through 10 years of production in 10 weeks of fighting, that probably should have been a five-alarm fire that we got the fundamental calculus on deterrence wrong. We thought the stockpile was going to deter our adversaries. It was always the factory.

</details>

**主持人**: 看看现状。在无人机产量上与中国有 **10,000 比 1** 的差距，造船能力差距达到 223 倍。我们是世界上国防开支最高的国家，但我们到底准备好了吗？

<details>
<summary>Original English</summary>

**Shyam Sankar**: Well, our joint force is the best in the world. But our adversaries are moving very quickly. Deterrence is eroding. You had Crimea in 2014, the militarization of the Spratly Islands, Iran, the Houthis. We have amazing high-end capabilities, but you can't keep shooting **$2 million interceptors at $20,000 drones** and have that math work very long. When you lose the general American industrial base, you lose **volume** and you lose the R&D stimulus to be creative—比如用造浴缸的方法去造廉价巡航导弹。我们现在被困在那些极度先进但单价 200 万美元、无法大规模生产的平台上。

</details>

### Anduril 的“兵工厂”策略

**主持人**: **Trey**，你写过一篇文章《无偿付能力，无安全》（No Solvency, No Security）。请分享一下你对工业基地重要性的看法，以及建立强大的制造能力需要什么？

<details>
<summary>Original English</summary>

**Trey Stephens**: We sent most of these capabilities away during the last 30 years of globalization, and that gutted entire communities. In my family, relatives worked at GM, Ford, Frigidaire—every single one of those factories in Ohio closed. What we're doing with Anduril right now is building a **5 million square foot factory campus** in Columbus, Ohio. We are tapping into that underemployed knowledge base. Since 2000, only one new company has built major manufacturing muscle: **Tesla**. That's it. We've atrophied massively.

</details>

**主持人**: 讲讲 **Arsenal-1** 及其背后的制造理念。是产品驱动还是产能驱动？

<details>
<summary>Original English</summary>

**Trey Stephens**: **Arsenal-1** 是我们在哥伦布建立的工厂园区。其背后的软件平台旨在降低自动化和流程管理的成本。我们正与 **Palantir 的 Foundry 平台**合作。核心理念是**模块化**。如果我们只固定生产某种无人机，在冲突中就会受限。我们的思路更像**合同制造商**（如富士康），我们建立的是一整套构建光学系统、动力系统的能力，并利用规模网络降低零部件成本。这样我们可以根据需求，瞬间从生产 A 产品转向生产 B 产品。相比之下，乌克兰战争初期，我们需要更多“毒刺”和“标枪”导弹，但库存耗尽后，生产线已不存在，甚至要从退休人员中找人回来教大家怎么造。

</details>

### 国防市场的游戏规则：从“定制”到“产品”

**主持人**: 谁来出资？政府会支持这些设施的建设吗？

<details>
<summary>Original English</summary>

**Trey Stephens**: Our business model is very different from the "Primes" (传统五大防务商). They respond to requirements directly from the customer. We are doing all of this as **private R&D investment** and then selling the output as a **product**. This is a fundamental change. It requires a tremendous amount of capital. I don't think the market will support 100 new Primes, but I hope there is more competition. This isn't like building a normal tech company.

</details>

**Shyam Sankar**: 这一点对技术圈可能很显而易见，但在国防领域不是这样。在国防部，人们不“制造产品”，而是根据政府给出的“**规格说明书**（Spec）”来建造。国防市场是一个“**买方垄断**（Monopsony）”，唯一的买家拥有巨大的权力，无论他们是对是错。历史上，创新的买方往往是错的。比如丘吉尔在担任海军大臣时开发了坦克，因为英国陆军当时还没意识到在下一场战斗中骑马是行不通的。每一项创新都是一种“异端行为”，需要一个偏执的创始人坚持到底，直到战斗时刻才被验证。

<details>
<summary>Original English</summary>

**Shyam Sankar**: Defense works as a monopsony where there's a single buyer. If you look at the history of defense innovation, typically the monopsony is wrong. Churchill as head of the Royal Navy built the tank because the British army was not smart enough to realize that having horses was not going to work. Every one of these innovations is an act of heresy. You need this competition.

</details>

### 风投进入国防科技：机会与风险

**主持人**: 过去主要有 51 家国防承包商，后来整合到了大约 5 或 6 家。现在有大量资金集中在新的挑战者身上：你们、**SpaceX**、**OpenAI**。未来是会回到少数几家巨头垄断的老路，还是能创造持续竞争的环境？

<details>
<summary>Original English</summary>

**Shyam Sankar**: Just like venture capital, there's going to be a **power law** here. A grave mistake we've made is "innovation theater"—把资金像涂花生酱一样平摊给每一家公司。这无法达到规模化。你可能投了 10 个赌注，但在某些时刻，你必须把资金集中在那些真正奏效的事物上。

</details>

**Trey Stephens**: 没错。如果你是航天科技投资者却没投 **SpaceX**，你可能亏钱了；如果你投社交媒体没投 **Facebook**，你也亏钱了。但资本配置者的记忆力通常很短，他们忘了必须将资金集中到赢家身上。

<details>
<summary>Original English</summary>

**Trey Stephens**: If you're a space tech investor and you didn't invest in SpaceX, you probably lost money. Capital allocators have a very short memory.

</details>

**主持人**: 对于现在涌入国防科技领域的风投，你有什么建议？

<details>
<summary>Original English</summary>

**Trey Stephens**: I think there's a real tension around the amount of capital raised and the valuations. My advice is: **You can raise less at a lower price.** This avoids "playing chicken" with numbers that don't make sense. In Anduril, we've focused on "climbing down the multiples tree"—我们不希望下一轮的营收倍数高于前一轮。这种纪律非常重要，尤其是考虑到中期 IPO 的目标。

</details>

### 关键供应链与“全球化”的盲点

**主持人**: **Shyam**，你提到过战略资本办公室（Office of Strategic Capital）的作用，以及供应链中的瓶颈，比如无刷电机。还有其他让你担心的领域吗？

<details>
<summary>Original English</summary>

**Shyam Sankar**: 太多了。除了战争武器，我更担心那些影响我们**战斗意志**的事物。**制药**就是其中之一。我父亲是药剂师。**80% 的通用药物活性药物成分（API）由中国生产。** 如果美国人在保卫自由世界与自家 5 岁孩子死于耳炎（本可轻易治愈）之间做选择，你觉得他们会选什么？我们沉溺于全球化愿景：我们负责创新，他们负责生产。但**创新其实是生产力的结果**。

</details>

**Trey Stephens**: **半导体**是另一个有趣的例子。我们曾是半导体行业的故乡，但随着 **TSMC** 在台湾崛起，我们基本上任由其发生。现在，面对 2027 年的台湾风险，似乎再多钱也很难在相关时间表内修复这个问题。

<details>
<summary>Original English</summary>

**Trey Stephens**: Semiconductors is another big one. We basically just allowed it to happen somewhere else and now almost no amount of money is going to fix this problem on a timeline of relevance to the risk Taiwan has in 2027.

</details>

### 伦理、AI 与自动系统的杀戮开关

**主持人**: 谈谈技术的伦理。最近 **Anthropic** 拒绝让 **Claude** 模型在没有人类监督的情况下用于 Maven 项目，五角大楼将其标记为供应链风险。在自动系统中，人类应该扮演什么角色？谁有权按下“杀戮开关”？

<details>
<summary>Original English</summary>

**Trey Stephens**: My belief in democracy is central here. The people of America elect representatives to make hard decisions. **Fully autonomous weapons are not new.** 我们有部署在舰艇上的 **Phalanx CIWS**（密集阵近程防御系统），它能完全自主击落空中威胁，因为人类根本没时间反应。但系统中存在**问责制**。船上有一个人对该武器系统的行为负责。未来的 AI 自动系统也将如此。

</details>

**Trey Stephens**: 从伦理上讲，我们从冷战时期的核武器“平台期”转向了**精确制导武器**。我们现在可以发射不含爆炸物的导弹穿过公寓窗户，消除目标同时避免平民伤亡。AI 作为指挥中心，能带来更高的精确度和辨别力，这比在城市投下哑弹要伦理得多。**拒绝参与国防科技建设并不是一种道德中立。** 当你决定退出时，你就在做道德决定。

<details>
<summary>Original English</summary>

**Trey Stephens**: We are shooting non-explosive missiles into windows of apartment buildings, avoiding unintended casualties. AI leads to better precision and less civilian casualties. Abstention from participating in building technology for national security is not a morally neutral decision.

</details>

### 监控国家的叙事与问责

**主持人**: 有人抗议 **Palantir** 助力建设“监控国家”。你们如何回应？

<details>
<summary>Original English</summary>

**Shyam Sankar**: 这种指责很荒谬。我们不收集数据，也没有数据。指责我们就像指责 **Excel** 是监控工具一样。**Palantir** 只是让客户把他们拥有合法授权收集的数据整合起来做决策。实际上，就像 Alex Karp 所说，由于我们的系统有极其严格的审计追踪，这是世界上最难进行非法操作的平台。

</details>

**Shyam Sankar**: 这里的核心是**认识论上的谦逊**（Epistemic Humility）。政策决定是由民选官员负责的。如果你作为技术人员在限制民主国家的决策空间，那其实是一种“**技术精英的暴政**”。

<details>
<summary>Original English</summary>

**Shyam Sankar**: It's like accusing Excel of being a surveillance tool. If you are "salami slicing" the policy as a tech person, that's actually tyranny by tech-bro. A small number of people are constraining the maneuver space of a democracy with no accountability.

</details>

**主持人**: 如果政府机构非法使用你们的技术，你们会举报吗？

<details>
<summary>Original English</summary>

**Trey/Shyam**: 100%. 每一个机构都有**监察长**（Inspector General）办公室。这套机制确实在发挥作用，有时甚至会被用来对付像 Maven 项目创始人 Drew Cukor 上校这样的英雄。

</details>

### 展望 2040：美国的故事

**主持人**: 如果我们做对了或做错了，2040 年会是什么样子？

<details>
<summary>Original English</summary>

**Shyam Sankar**: 如果搞砸了，我们将迎来一个无法恢复的“**中国世纪**”，全世界都将成为中国的附庸国。CCP 的策略很明确：不仅要中国繁荣，美国必须倒下。如果做对了，我们将看到美国的**大规模重新工业化**，以及随之而来的西方复兴。我们将拥有一个繁荣的中产阶级——其定义是相信子女的未来会比自己更好。

</details>

**Trey Stephens**: 我完全同意。这也涉及**教育**。我们需要让年轻人进入一个需要他们并能受益于他们服务的市场。重新工业化将是挫败中国长期战略的核心。

<details>
<summary>Original English</summary>

**Trey Stephens**: The re-industrialization point is going to be the central point of making sure that China's belt and road strategy is not going to put us in a position where we literally just can't do anything.

</details>

**主持人**: 我们需要维持军事和工业的**绝对领先**（Primacy）吗？还是可以接受一个多极世界？

<details>
<summary>Original English</summary>

**Trey Stephens**: 挑战在于，如果你不是领导者，你就无法设定**参与规则**。二战结束以来，我们一直坐在桌子的主位上，决定了半导体、供应链和贸易路线的规则。一旦你退后，别人就会制定游戏规则，而多极状态通常维持不了太久。

</details>

**主持人**: 非常感谢两位，Trey，Shyam。

<details>
<summary>Original English</summary>

**Trey/Shyam**: Thank you.

</details>