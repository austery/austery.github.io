---
author: Money or Life 美股频道
date: '2026-07-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iu2qnkSOnic
speaker: Money or Life 美股频道
tags:
  - aerospace-engineering
  - rocket-static-fire
  - hardware-iteration
  - propulsion-system
  - fail-fast
title: SpaceX星舰纪录片：冲破物理极限的V3代星舰与猛禽3发动机开发纪实
summary: 本片深度记录了SpaceX研发第三代（V3）星舰及其超重型助推器的曲折历程。从Booster 18的氮气增压爆炸，到Booster 19的10台及33台猛禽发动机静态点火中止（Pad Abort），再到Massey测试场的重建，展现了SpaceX通过快速迭代、极限简化设计（猛禽3代）以及在失败中搜集数据的独特工程哲学。
insight: ''
draft: true
series: ''
category: testing
area: tech-engineering
project: []
people: []
companies_orgs:
  - SpaceX
products_models:
  - Starship
  - Raptor-3
  - Falcon-9
  - Falcon-Heavy
media_books: []
status: evergreen
---
### V3级超重助推器的首次静态点火挑战

**[测试指挥官]**: 直到发射倒计时大约4分钟时，许多关键的操作开始密集展开。倒计时3分钟时，我们将结束推进剂的加注工作。也就是说，在这个时候，液氧和液体燃料（液态甲烷）的加注都已经收尾了。到了倒计时40秒，我们就会停止与发射台的所有外部交互。此时，整枚火箭将完全处于自主控制状态。

好的，请所有Booster 19（B19）的测试操作员注意。这是我们针对今天测试任务的最终“Go/No-Go”决策轮询。我们今天的主要目标是进行一次**10台发动机的静态点火测试**。

<details>
<summary>Original English</summary>

**[Test Director]**: ...until about T-minus 4 minutes. A lot of stuff starts going down. T-minus 3 minutes closing out the propellant load. So, you're finishing out the liquid oxygen load and the liquid fuel load. T-minus 40 seconds. We stop interacting with the pad. The vehicle is just on its own.

All right, test all B19 operators. This is the final go/no-go poll for today's operations. Our main objective today is a 10 engine static fire.

</details>

**[SpaceX工程师A]**: 为什么是进行10台发动机的点火，而不是把全部33台发动机一起点燃呢？因为这是目前在发射台上进行测试的第一款**V3级助推器（Version 3 Booster）**。在这样一个全新的系统上，有很多地方都可能出差错。如果我们今天运气不好遭遇了“糟糕的一天”（指发生爆炸或严重损坏），限制点火发动机的数量可以控制并缩小可能出现问题的波及范围。

<details>
<summary>Original English</summary>

**[SpaceX Engineer A]**: Why 10 engines instead of all 33? This is the first V3 booster down at the pad right now. So there's a lot of stuff that can go wrong and if we do have a bad day, it limits the scope of the issues that we can have.

</details>

**[SpaceX工程师B]**: 这将是我们在SpaceX所有火箭型号上所见过的**最高燃烧室压力（Chamber Pressure）**。因此，今天的测试绝对会是一场非常火爆且刺激的硬仗。

<details>
<summary>Original English</summary>

**[SpaceX Engineer B]**: This will be the highest chamber pressure we've ever seen on a vehicle at SpaceX. So definitely going to be a pretty spicy test today.

</details>

**[SpaceX工程师C]**: 然后，当发射倒计时进入最后40秒，尤其是到了倒计时最后4秒时，我的心率真的开始疯狂飙升。接着，我们点燃了发动机。热流，热流！滚烫的烈焰与高温扑面而来。

我们现在所处的地方是**星厂（Starfactory）**，这是一座占地将近100万平方英尺的超大型制造工厂。我们建造它的目的，就是为了能够实现星舰飞船（Ship）和超重型助推器（Booster）的大规模量产。

**星舰（Starship）**是一枚完全可重复使用的火箭。它由两个部分组成：上级是星舰飞船，下级是超重型助推器。助推器的作用是为飞船加速，将其送往轨道方向。而飞船则是最终真正进入轨道、将人员或有效载荷运送到目的地的载具。

这里充斥着进步的声音，气动铆枪的轰鸣声，还有铁锤的敲击声——当然，现在的铁锤敲击声已经比以前少多了。

<details>
<summary>Original English</summary>

**[SpaceX Engineer C]**: And then you're counting down from T-minus 40. T-minus 4 on is when my heart rate really starts to tick up. And then we light the engines. Heat. Heat. Heat. Heat. We are in Starfactory and this is an almost 1 million square ft facility that we've built to enable that production of both ship and booster.

Starship is a fully reusable rocket. It's two stages. So, it has a ship, which is the upper stage, and a booster below it. The booster accelerates the ship to get it going towards orbit. The ship is what actually goes into orbit to take the people or the payload to wherever they're going.

The sound of progress, the rivet guns, and the sledgehammers. Less sledgehammers than there used to be.

</details>

---

### 研制星舰的起源与迭代路线

**[SpaceX工程师D]**: 星舰的故事要从SpaceX的创立开始说起。

如果直接去研发埃隆·马斯克所设想的、将人类送上月球和火星所需的终极航天载具，这在当时基本上会让公司直接破产，这在财务和技术上都是不可能实现的。因此，你必须把这个宏大的目标拆解成一个个较小的部分，逐步去攻克。

在当时看来，那些所谓的“小部分”其实一点也不小，它们分别是：**猎鹰1号（Falcon 1）**、**猎鹰9号（Falcon 9）**、**龙飞船（Dragon）**（包括货运版和载人版），以及**猎鹰重型火箭（Falcon Heavy）**。

<details>
<summary>Original English</summary>

**[SpaceX Engineer D]**: The story of Starship starts with the founding of SpaceX. Rather than starting with the vehicle that Elon envisioned needing to get people to the moon and Mars, he thought it would basically bankrupt the company. It wouldn't be possible. So, you have to fight it off in small pieces. And so those pieces, which at the time did not seem small at all, were Falcon 1, Falcon 9, Dragon, both cargo and crew, Falcon Heavy.

</details>

**[旁白]**: 3，2，1。猎鹰重型火箭已经超越音速！

<details>
<summary>Original English</summary>

**[Narrator]**: 3 2 1. Falcon Heavy is supersonic.

</details>

**[SpaceX工程师D]**: 这些火箭都是我们的基石，让我们在摸索中学会了如何制造和运营火箭。我们没有照搬传统航空航天业的老路，而是用我们自己的方式去践行，这也是我们今天能够站在这里研发星舰的基础。

<details>
<summary>Original English</summary>

**[SpaceX Engineer D]**: These were the building blocks that let us cut our teeth on learning how to do rockets. Not the way the aerospace industry had been doing it, but the way we needed to do it to end up here where we are today working on Starship.

</details>

---

### 星舰V3的革命性架构升级

**[SpaceX工程师E]**: 正在发射台上的**第三版（V3）**星舰，是我所认为的星舰助推器奠基性设计。它将赋予我们全新的能力，去执行摆在我们面前的各种宏大任务。它将是把人类重新送回月球的工具，也将是率先在火星上留下人类足迹、乃至建立火星城市的载具。

星舰的体型极其巨大，这种超大尺度绝非偶然，也不是为了赢得什么吉尼斯世界纪录——尽管我们确实凭借飞船和发射塔拿到了吉尼斯纪录。我们之所以需要如此庞大的体积，是因为只有这样才能实现我们梦想用它来做的事情。

**Ship 39**是第一艘V3版飞船。这枚火箭与以往任何人制造过的火箭都截然不同。第三代星舰在飞船设计上基本上是一次“白纸一张”的全新设计。我们总结了V1版和V2版飞船的大量经验教训，退后一步审视：从性能或可靠性的角度来看，之前的火箭有哪些地方是真正存在痛点的？然后，我们通过一系列全新的设计，直接针对性地解决了这些问题。

它可以进入轨道，在轨道上停留长达48小时。它可以与其他星舰交会对接，并进行**推进剂在轨转移（Propellant Transfer）**。这正是解锁星舰全部潜能的核心技术。一旦你攻克了这项技术，整个太阳系都将近在咫尺。

而现在，我们正在对这艘飞船进行出厂检查和测试。我们正在赋予这枚火箭生命。我们以前从未制造过V3版本的飞船，更没有将其推入到这种生产制造阶段。因此，对于这艘特定的飞船，我们必然会遇到一些奇特甚至古怪的问题。而且，对于这套系统架构的整体表现，我们很多时候也只能依靠模拟和流体模型来推测其运行机理。现在，真正的实物就矗立在我们的身边。

<details>
<summary>Original English</summary>

**[SpaceX Engineer E]**: Version three is what I like to call the foundational design of Starship booster in the pad. That's going to give us the new capabilities we need to do the missions in front of us. It'll be the one that puts humans back on the moon. It'll be the ones that put the first bootprints and then city on Mars.

Starship is giant and that scale is not an accident. It's not to win some Guinness World Record prize, which we did for both the ship and the tower. It's because we need that size to do the things we dream of doing with it.

Ship 39 is the first V3 rocket. This rocket is unlike anything anybody's ever done before. Version three is basically a clean sheet design of the ship. We essentially took a bunch of lessons from version one and version two and we took a step back and said what were the things that were really problematic either from a performance perspective or from a reliability perspective on the previous rockets and then we directly address those with a variety of new designs.

It can go up to orbit, it can stay on orbit for 48 hours. It can meet up with other ships and it can do propellant transfers, which is really the core technology that you need to unlock Starship. Once you unlock that capability, the whole solar system is on your doorstep.

And right now, what we're doing is we're actually going through checkout. So, we're actually kind of bringing the rocket to life. We've never built a ship V3 before and gotten it to this state of production. So, we are going to have special things to this specific vehicle that are going to be odd. But there's also things about the architecture as a whole that we don't really know how to deal with because we've only done simulations. We've only built fluid models how we think a ship V3 operates. Now, we have the real deal next to us.

</details>

**[测试总监]**: 我们的第一优先级是你们的安全。第二优先级是确保这台航天载具的安全。在这两点之后，我们才会去考虑执行我们的既定日程表。

<details>
<summary>Original English</summary>

**[Test Director]**: First priority is your safety. The second priority is make sure the vehicle's okay. and then we worry about executing to our schedule.

</details>

**[SpaceX工程师F]**: 我们非常兴奋，同时也非常焦虑，但综合考虑各方面因素，我们的准备工作做得相当充分。我们相信会取得一个好的结果。

我们有意先从星舰的飞船部分开始研发，因为它是如此新颖独特。至于可重复使用的助推器，我们之前已经在猎鹰9号上成功实现过，因此那至少是我们在一定程度上探索过的领域。但我必须承认，超重型助推器的研发难度，比我们最初预想的要大得多。

这是一枚全新的火箭。这是我个人参与过的最雄心勃勃的载具设计，能看到它在这里变成现实，真是一件疯狂的事情。

V1版本飞船的飞行测试任务充分体现了SpaceX工程团队所倡导的**快速集成测试风格（Rapid Integrated Test Style）**。从我们的第一次尝试（Flight 1）到第五次飞行（Flight 5），我们仅仅用了五次飞行就成功捕获了助推器，这说实话简直令人难以置信。

第一次飞行成功离开了发射台。它证明了我们可以将整个庞大的系统组合在一起。虽然火箭最终解体了，但我们从那次失败中汲取了极多的教训。这让我们能够对发射台以及整车硬件设计进行大量改进，从而在第二次飞行中取得了大得多的成功。

在第二次飞行中，我们的助推器成功飞到了Max-Q（最大动压点），实现了飞船与助推器的分离，并开始向发射场方向进行返航点火（Boostback Burn）。我们达成了飞行测试中的又一个重大里程碑。在第三次飞行中，我们成功完成了完整的返航点火。在第四次飞行中，我们成功实现了海上软着陆的演示。而在第五次飞行中，我们得以返回发射场，并用我们的**筷子回收系统（Chopsticks）**成功捕获了超重型助推器。

<details>
<summary>Original English</summary>

**[SpaceX Engineer F]**: We're quite excited. We're quite anxious, but all things considered, we're pretty well prepared. We think that we'll have a good result.

We intentionally started Starship with the ship portion because it was so novel. We have done a reusable booster before with Falcon 9 and so it's at least a little bit better tread ground. I will say I think the booster turned out to be a lot harder than we gave it credit for.

This is an entirely new rocket. This is the most ambitious vehicle design I have ever personally worked on and it is a wild thing to see come to reality here.

The version one flight test campaign really exemplifies the rapid integrated test style that we do in SpaceX engineering. It took us five flights from our first attempt from flight 1 to flight 5 to successfully catch a booster which was honestly mind-blowing.

Flight one was able to get off the pad successfully. It proved that we could get this full system together and we learned a lot from the eventual failure of the vehicle in that flight. We were able to put together a lot of improvements on the launchpad and on the vehicle hardware design that led to much better success in flight 2.

</details>

**[SpaceX工程师G]**: 能够飞上天并取得那样的任务成功——把载荷送入轨道，并且把火箭稳稳回收，这简直太不可思议了。我现在聊起这件事还是会起鸡皮疙瘩。

我们即将在测试工作中迎来一段非常令人兴奋的时期。我们要让这台设备经受各种严苛的考验，确保我们设计的每一样东西都能正常工作。

你想在这里停下来吗？

<details>
<summary>Original English</summary>

**[SpaceX Engineer G]**: We were able to make it with the booster to Mo. We were able to separate the ship and we were able to begin boosting back towards the launch site. So, we hit the next big milestone in the flight test campaign. On flight three, we were able to get all the way through our boost back burn. On flight four, we were able to do a successful water landing demonstration. And on flight five, We were able to come back to our launch site and successfully catch the vehicle with our chopsticks.

To be able to go fly that and have complete mission success at that point of we got the payload to orbit and we landed that rocket was incred. I'm getting goosebumps talking about it now. We're about to get into a really exciting period of the vehicle test campaign here. Putting the thing through its paces and making sure that everything we design works okay. You want to stop right here?

</details>

**[SpaceX工程师H]**: 是的。这是我们有史以来第一次让这个系统的所有部分协同工作。如果我们能从中发现或学到什么，我们一定要以最快的速度去掌握它。

<details>
<summary>Original English</summary>

**[SpaceX Engineer H]**: Yeah. Get all of the pieces of the system working together for the first time. And if we're going to learn anything from that, we'll learn it as quickly as we possibly can.

</details>

---

### Booster 18的爆炸教训与低温测试

**[SpaceX工程师H]**: **Booster 19（B19）**实际上是我们建造的第二枚V3级助推器。在它之前是**Booster 18（B18）**。不幸的是，在对Booster 18进行首次测试时，我们遭遇了异常事故。

作为我们建造的第一枚V3级助推器，整个团队对B18的测试都感到无比兴奋。大家都非常希望它能顺利工作。然而，当我们在对**氮气系统（Nitrogen System）**进行加压时，发生了一次猛烈的爆炸，彻底摧毁了火箭。幸运的是，我们在设计这项测试时，就已经把安全性考虑在内——如果真的发生意外，安全必须得到保障。测试时车上并没有加加注易燃推进剂或其他活性化学物质，因此发射台只受到了极其轻微的损坏，当然，也没有任何人员在这次事故中受伤。

<details>
<summary>Original English</summary>

**[SpaceX Engineer H]**: Booster 19 is actually the second of the version three boosters that we've built. Booster 18 came before it. We had an unfortunate anomaly during our first test campaign of the booster 18 vehicle. This is the first version 3 booster that we've built. So this is booster 18. This is really awesome because it's going to be our first full vehicle level operation and test with a version 3 vehicle. So the whole team's very excited about this. Sure hope it works.

When we were pressing the nitrogen system, we had an explosion that took out the rocket and thankfully we had designed that test to be safe if something like that happened. We did not have propellants or reactive things on the vehicle. And so the test site incurred very little damage and of course nobody was hurt in the incident.

</details>

**[SpaceX工程师I]**: 确实，作为测试工作的一部分，现场会非常吵闹，所以你必须学会适应，在发射台周围走动时不要一惊一乍的。

现在助推器已经运抵测试现场。我们将要对其进行一次**低温结构验证测试（Cryo Proof）**。这实际上是极其漫长的一天。通常这会被规划为一个长达12小时的推进剂加注与卸载过程。因为我们要往这枚火箭里灌入海量的超低温推进剂。在这一整天里，我们会执行大量的测试用例，所以这绝对是一场持久战。

<details>
<summary>Original English</summary>

**[SpaceX Engineer I]**: Yeah, as part of testing, this is loud, so you learn to not be super skittish as you're walking around. So, we have our booster here on site. We're going to be performing a cryo proof. It's actually a really long day. So, it's normally planned to be a 12-hour overall propload load and offload. It's just a ton of propellant that we're putting on the vehicle. And we do a bunch of test cases throughout the whole day. So, it's a long one.

</details>

**[测试操作员A]**: 正在将助推器存储管理器切换至低温高流量加注验证状态。

<details>
<summary>Original English</summary>

**[Test Operator A]**: Taking booster SM to cryo highfill proof.

</details>

**[SpaceX工程师I]**: 低温测试是你第一次真正将低温推进剂灌入箭体。我们加注的液体推进剂温度非常低，通常在**80开尔文（约零下193摄氏度）**的范围。我们的测试哲学是“怎么飞就怎么测，怎么测就怎么飞”（Test like you fly, fly like you test）。

<details>
<summary>Original English</summary>

**[SpaceX Engineer I]**: Cryoproof is the first time you actually put propellant onto the vehicle. The liquid propellant that we're putting on does get pretty cold. Generally in the 80 Kelvin range. We want to test like you fly and fly like you test.

</details>

**[测试操作员B]**: 低温加注液位已达到70%，验证百分比已确认。

<details>
<summary>Original English</summary>

**[Test Operator B]**: On 70% proof percentage confirmed.

</details>

**[测试操作员C]**: 燃料接口现在已实现完全的低温冷透。

<details>
<summary>Original English</summary>

**[Test Operator C]**: and fuel interface is fully crowded now.

</details>

**[SpaceX工程师J]**: 这种与团队一起在控制室里熬夜奋战的经历真的是独一无二。当你经历这些里程碑并心想：“天啊，我竟然真的能给一枚火箭加注推进剂，这太神奇了。”

<details>
<summary>Original English</summary>

**[SpaceX Engineer J]**: There is definitely nothing like a late night with your team in the control room. It's one of those milestones where you're like, "Wow, if I can load a rocket, this is amazing."

</details>

**[测试总监]**: 飞行硬件测试（FHT）看起来非常稳定。让我们开始执行助推器的推进剂卸载配置。收到。

<details>
<summary>Original English</summary>

**[Test Director]**: The FHT looks pretty stable. Let's go ahead and get booster configured for offload. Copy.

</details>

---

### 猛禽3代发动机的极限简化

**[SpaceX工程师K]**: 那么，什么是热源？这就是我们的**猛禽3代（Raptor 3）**发动机。V3是一款超高性能的助推发动机，设计目标是极高的可重复使用性和可靠性。

在生产了大约600台猛禽2代（Raptor 2）发动机之后，我们积累了海量的经验。你可以直观地看到，从V2到V3，发动机的外观经历了多么恐怖的简化。这种超高水平的系统集成在整个火箭发动机制造史上都是极其罕见的，这凝聚了大量工程师为了合并硬件、消减冗余管道和阀门所付出的心血。

简化带来的直接效果是，这实际上是一项拥有更高可靠性的设计。**零件数量的减少意味着成本更低、制造速度更快**。这使得我们能够制造出更轻的火箭本体，制造出维护和检修更加容易的载具。简而言之，就是制造出一枚更优秀的火箭。

让这样一台复杂的火箭发动机实现真正意义上的完全重复使用，是人类以前从未做到过的事情。我们的终极目标，是让火箭发动机能够像商用民航飞机上的喷气式发动机一样，无需繁琐的拆卸检修，就能频繁、稳定地一次又一次起飞。

在与SpaceX外部的人交流时，人们常常有一种根深蒂固的观念，认为那些远远超出人类已有经验尝试的事情是绝对“不可能”的。但事情是否真的不可能，唯一的评判标准是它有没有违背**物理学定律（Laws of Physics）**。我们没有违反任何物理学定律，我们只是在尽最大可能，最有效地去利用物理学规律而已。

<details>
<summary>Original English</summary>

**[SpaceX Engineer K]**: What heat? This is a Raptor 3. V3 is a high performance boost engine. It's also designed to be reusable and highly reliable. We've learned a lot over the course of producing around 600 V2 engines. You can see the amount of simplification that's occurred between V2 and V3. The level of integration is really unique for rocket engine that comes from a lot of work among many engineers to consolidate the hardware.

The effect of that is that it's actually a higher reliability design. So fewer parts is cheaper, faster to build. So that allows us to make a lighter vehicle, to make a more reliable vehicle to overhaul, just build a better rocket.

Achieving full reusability of an engine like this is really something that people haven't done before. The goal is to get the engine to behave in a similar way to the engines on commercial airplanes.

frequently in interactions with people outside of SpaceX. The perception is that things far beyond what have ever been done before are impossible. Things being impossible is really to be determined by breaking laws of physics. We are not breaking laws of physics. We're just trying to leverage them as effectively as we can.

</details>

---

### 33台发动机全开的Pad Abort

**[测试指挥官]**: 请所有B19操作员注意。这是针对今天测试任务的最终决策轮询。我们今天的主要目标是进行**10台发动机的静态点火**。

<details>
<summary>Original English</summary>

**[Test Director]**: All right, attention all B19 operators. This is the final go now go poll for today's operations. Our main objective today is a 10 engine static fire.

</details>

**[SpaceX工程师L]**: 静态点火是整个工程研发流程的最高潮。我们把所有的拼图碎片拼凑在一起，然后点燃发动机。如果你能顺利通过这一关，你就会对火箭具备极大的信心，知道它已经做好了飞天的准备。

<details>
<summary>Original English</summary>

**[SpaceX Engineer L]**: Static fire is the culmination of the engineering process. We are bringing all of the pieces of the puzzle together and we are lighting the engines. And if you make it through that, you have pretty good confidence that you're in a good position to go fly.

</details>

**[测试操作员D]**: 确认触发中止命令。LB1异常。看起来我们在点火过程中，由于气流扰动，从Apex燃烧室组中意外踢出了两个燃烧室。数据表明，我们在点火后2.135秒时触发了关机。

<details>
<summary>Original English</summary>

**[Test Operator D]**: ...aboard. One LB1. Looks like we kicked out two combusters from the Apex Bank being felted. Looks like we up to time of 2.135 seconds.

</details>

**[SpaceX工程师M]**: 我们其实成功点燃了全部10台发动机，它们当时正在向全功率爬升，一切看起来都很正常。然而，发射台侧突然触发了**主动测试中止（Pad-side Abort）**。这意味着某个传感器检测到了异常数据并触发了保护机制，从而命令系统进行紧急快速关机。

这是一次非常剧烈、粗暴的紧急停机，尤其是我们之后不得不将全部10台发动机全部拆卸下来。值得庆幸的是，这10台发动机全部可以回收修复。

在静态点火发生后，我们看到的数据显示，由于极速关机产生的剧烈震动和瞬态压力，大约有一半的发动机出现了机械损伤。因此，我们把助推器运回了巨型厂房（Mega Bay）。接着，我们决定将全部10台发动机从助推器上拆下进行故障排查，以便彻底查明原因；同时，为了不耽误B19的测试进度，我们从**Booster 20（B20）**上拆下了发动机，回填安装到了B19上。

<details>
<summary>Original English</summary>

**[SpaceX Engineer M]**: We successfully lit all 10 engines. They were ramping up to power. Everything was looking good. Uh stage and engines combined. However, there was a pad side abort called. So, what that means is some sort of sensor tripped and from there we command a fast shutdown. It was a hard one and especially since we had to drop all the engines afterwards and thankfully uh 10 of them were salvageable which is good. We saw some data right after static fire that showed about half the engines had what looked like mechanical damage basically as a result of the really fast shutdown. So we brought the booster back to Mega Bay. We then decided to remove all 10 engines from the booster so that we could troubleshoot and understand what's going on those 10 while still making progress on B19 by backfilling engines from B20.

</details>

**[测试指挥官]**: 请发射台上的所有操作员注意。今天的主要目标是在B19助推器上进行一次**33台发动机的全规模静态点火测试**。好的，最终的Go/No-Go轮询将在1分钟内开始。

这我们将是今天使用全部33台发动机进行的静态点火。这也是今天操作的最后一轮轮询。

飞行软件？**Go！**
加注控制？**Go！**
猛禽发动机？**Go！**
火箭级段？**Go！**
控制中心？**Go！**
地面保障2？**Go！**
地面保障1？**Go！**
测试指挥？**Go！**

各位准备。10，9，8，7，6，5，4，3，2，启动！

<details>
<summary>Original English</summary>

**[Test Director]**: All right, attention operators on LVN1. Today's main objective is a 33 engine static flyer on B19. Okay, do no go poll coming up in one minute. So, we're doing our static fire today with all 33 engines. This is the final go no-go poll for today's operations. Flight software: go. Ay: go. Raptor: go. Stage: go. C: go. GC2: go. GC1: go. FC1: go. Two guys. 10 9 8 7 6 5 4 3 2 Mission.

</details>

**[测试指挥官]**: 噢，天呐。我们提前中止了。所有团队立刻对警报进行分类筛查。准备卸载推进剂。

<details>
<summary>Original English</summary>

**[Test Director]**: Wow. We kicked out early. All teams triage alerts. Prepare for offload.

</details>

**[SpaceX工程师N]**: 今天，我们在B19助推器的第二次全发动机静态点火尝试中再次遭遇了中止。这次是在**分流阀（Diverter）**上发生了一次发射台侧的中止。我们成功度过了发动机的启动阶段，但最终在其中一个分流管路上丢失了部分传感器的数据。传感器读数显示，该分流管的压力低于我们的理论设定值，导致系统在点火后1.88秒触发了关机。

这真的很艰难，因为有些极端的运行环境在实际点火之前是根本无法模拟和测试的。例如这个分流器，你可以在地面上对它进行无数次压力和流量测试，但你显然无法在点火前模拟出33台发动机共同轰鸣时所产生的巨大**物理振动（Vibration）**以及极其恶劣的声学和力学环境。

<details>
<summary>Original English</summary>

**[SpaceX Engineer N]**: Today we aborted our second attempt of the B19 full count static fire. We actually had another pad abort on the diverter. We made it through engine startup and then ultimately lost some of our sensors on one of the ramp manifolds. It basically said that the manifold pressure was lower than we believe that it probably was and it kicked us out at t plus 1.88 seconds.

It's just tough cuz there are some things that are hard to test ahead of time. So the diverter you can test as much as you want, but you can't obviously test for what theoretical vibe and environment you're going to see when the engines are turned on.

</details>

**[SpaceX工程师O]**: 任何时候，当你走进一次测试，试图同时点燃33台如此庞大且威力惊人的发动机，让它们协同工作，并在测试结束后整枚火箭还能完好无损地矗立在发射台上，这本身就是一次巨大的胜利。我认为每一次测试都代表着成功。我们在地面系统、火箭本体以及发动机上都收集到了大量的宝贵数据，在现阶段发现并标记出这些潜在隐患是非常有价值的。但这确实也是令人悲喜交加的一天。

我们SpaceX内部有一句名言，叫作**“只有偏执狂才能生存”（Only the paranoid survive）**。这句话背后的核心逻辑是，在测试过程中会有海量的信息和数据涌向你。如果你能聪明、细致地利用这些数据，你通常就能预判未来哪些地方可能会掉链子。几乎每次我们的系统发生故障或出现偏差时，其实在之前的测试数据和操作记录中就已经留下了蛛丝马迹。如果你足够敏锐、足够偏执，在当时就去掘地三尺地追查，你完全可以在灾难发生前就地解决它。

<details>
<summary>Original English</summary>

**[SpaceX Engineer O]**: Anytime that you walk into an operation where you want to turn on 33 of these enormously powerful engines and get them all to work together and walk away from it in one piece, that is a win. I think every test is always a success and we had a bunch of findings on the ground systems, the vehicle and the engines that I think were really good to flag at this point. But definitely a bittersweet day.

We have this saying called only the paranoid survive. The idea behind it is that there's an enormous amount of information and data that's coming to you. And if you can use that wisely, you can usually use that to figure out where things are going to go wrong in the future. And almost every time that we fail something or have something go arai, there were clues in previous data in previous operations that if you had known what to look for and have been good enough and paranoid enough to do so, could have found it there.

</details>

---

### Massey测试场的涅槃重生

**[SpaceX工程师O]**: 距离**Massey测试场（Massey's Test Site）**遭遇S36号飞船爆炸事故，已经过去了10个月。

<details>
<summary>Original English</summary>

**[SpaceX Engineer O]**: It's been 10 months since Massie's had the S36 anomaly.

</details>

**[SpaceX工程师P]**: **Ship 36（S36）**的爆炸对我们来说是一个非常沉重的打击。当时一个**碳纤维复合材料压力容器（CPV - Composite Pressure Vessel）**发生了爆炸，它不仅彻底炸毁了那艘飞船，还几乎将Massey测试场的大部分地面测试基础设施夷为平地。

这引发了我们的深度思考：我们该如何确保，如果未来再次发生类似的测试异常，我们的发射台和测试场能够承受住爆炸的冲击力并幸存下来？

<details>
<summary>Original English</summary>

**[SpaceX Engineer P]**: Ship 36 was a tough one. We had a CPV explode and it not only took out the rocket, but it took out a lot of the test site infrastructure over at Massy's. How do we go make sure if we have an anomaly again, the pad can take a beating and still survive?

</details>

**[SpaceX工程师Q]**: 损失一枚火箭是一回事。我们拥有整条火箭生产线，我们可以源源不断地制造出更多的火箭。但如果损失了发射台或测试场的物理基础设施，情况就会变得极其棘手。因为你必须花费数月的时间去重建和修复这些地面硬件，然后才能重新开展任何测试工作。

现在，我们终于让Massey测试场重新回到了工作状态。我们不仅是从零开始制造这枚火箭，更是从零开始建设这整个测试场。因此，这里有各种各样全新的系统。今天将是我们第一次把发射台和火箭本身这两个复杂系统结合在一起，来验证它们之间的接口和协同工作是否完全正常。

这艘用于静态点火的飞船目前正处于发射前准备状态，即将开始静态点火前的系统整备。我们在飞船上进行长达60秒的静态点火测试，因为只有这样，你才能观察到火箭在长时间点火状态下的**热效应分布（Thermals）**是如何变化的，以及整车的综合性能表现。如果你能顺利挺过这60秒，就说明这艘飞船已经处于可以执行实际飞行任务的良好状态了。

<details>
<summary>Original English</summary>

**[SpaceX Engineer Q]**: Losing a rocket is one thing. We've got a production line for rockets and we can go make more. Uh losing the physical infrastructure of the launch pad or the test site is very difficult cuz you need to go repair that over a period of many months before you can get back into testing.

Now we have Massie's back online here. We've really, you know, built this rocket from scratch, but we've also built the pad from scratch. So, it's all kinds of new systems. This will be the first time that we bring together the pad and vehicle pieces to make sure that they all work.

Static fire vehicle is in prepad clear about to do our static fire pack up state. We run 60 seconds on ship because you get to see how the vehicle thermals all shake out and just general vehicle performance. That if you can make it through that that you are in a reasonable position to go fly.

</details>

**[测试操作员E]**: 发动机已启动。推进剂正在建立推力！

<details>
<summary>Original English</summary>

**[Test Operator E]**: Start up. Throttle up.

</details>

**[SpaceX工程师R]**: SpaceX的征程，本质上是一场让人类能够自由出入太阳系乃至飞向更深邃宇宙的征程。这正是我们研制星舰的终极目标。

<details>
<summary>Original English</summary>

**[SpaceX Engineer R]**: The journey of SpaceX is a journey to give humans access to the solar system and beyond, which is really the goal for Starship.

</details>

**[测试操作员F]**: 点火时间已达20秒。

<details>
<summary>Original English</summary>

**[Test Operator F]**: Plus 20.

</details>

**[SpaceX工程师S]**: 这枚火箭未来对整个世界所产生的深远影响，我认为目前绝大多数人都还无法真正想象和理解即将到来的巨变。

<details>
<summary>Original English</summary>

**[SpaceX Engineer S]**: The impact that this rocket is going to have on the world. I don't think most people can really comprehend the change it's going to happen.

</details>

**[SpaceX工程师T]**: 这真是一场极其疯狂的旅程。正如我们为了最终实现让人类飞天而竭尽全力工作一样，工程研发中的巅峰与谷底是并存的，那些高光时刻让人无比兴奋，而低谷期也极其令人沮丧。但这终将是不可思议的成就。

点火时间已达40秒。

<details>
<summary>Original English</summary>

**[SpaceX Engineer T]**: This is such a wild ride. The highs are high, the lows are low as we like really work to get to ultimately launching people, which is going to be amazing. Plus 40.

</details>

**[SpaceX工程师U]**: 仅仅因为它远远超出了人类之前的尝试，并不意味着它就是“不可能”的。我们已经一次又一次地用实际行动证明了这一点。

点火时间已达50秒，测试圆满完成！太棒了。

<details>
<summary>Original English</summary>

**[SpaceX Engineer U]**: It is not impossible just because it's far beyond what has been done before. We've proved that time and time again. Plus 50ation. Yeah.

</details>