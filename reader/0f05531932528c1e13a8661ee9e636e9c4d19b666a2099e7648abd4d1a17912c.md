---
author: a16z
date: '2026-10-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bmDrbHOh7Bo
speaker: a16z
tags:
  - mesh-network
  - network-protocol
  - peer-to-peer
  - cybersecurity
  - data-privacy
title: 重构互联网底层协议：对话互联网地图之父 Barrett Lyon
summary: 网络安全先驱、Opte 项目创始人 Barrett Lyon 深入探讨了现代互联网协议的停滞、监控资本主义与数据审查的威胁。结合自身遭遇空难、创立 Prolexic 以及搭建去中心化隐私网络 Doxnet 的传奇经历，他阐述了如何通过点对点网状架构与无服务器设计，重新找回早期互联网自由开放的精神。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Prolexic
  - Doxnet
  - MoMA
products_models: []
media_books:
  - The Opte Project
status: evergreen
---
### 互联网协议的停滞与反思

**主持人**: 我们现在确实处在一个转折点上，因为从本质上讲，我们见证了投币式大规模智能的诞生。

<details>
<summary>Original English</summary>

**Speaker 0**: for really at an inflection point because you have the birth of essentially coin operated intelligence at scale.

</details>

**巴雷特·里昂**: 互联网实际上已经停滞了，特别是从**协议设计**的角度来看，几乎没有什么真正的新东西。

<details>
<summary>Original English</summary>

**Speaker 1**: the internet is really kind of stagnited, but from protocol design. there's like not a lot of new stuff.

</details>

**主持人**: 所有的东西都是建立在现有堆栈之上的。消除这些历史包袱正是我努力的方向。按照你的说法，你实际上构建了一种瞬态连接机制，让人们能够直接连接并交流，而不留下任何记录。

<details>
<summary>Original English</summary>

**Speaker 0**: all of it's built on top ereracing that is kind of what i'm trying to go for what you're saying is you've actually built this transient way for folks to connect and chat without there being any record.

</details>

**巴雷特·里昂**: 像 **WhatsApp**、**Signal**、**iMessage**、**Telegram** 这类应用，真正的大问题在于它们伪装成了端到端的直连。表面上是你把内容发给另一个人，实际上你只是把数据发到了一台服务器上。那么问题来了：那些服务器到底是谁的？

<details>
<summary>Original English</summary>

**Speaker 1**: the really big problem is on what's app signal ie message telegram is you've applications disguise themselves. with you sending something to somebody else. you're really sending something to a server. that question is like, okay. well, whose servers are those.

</details>

**主持人**: 这正处于影响我们国家、科技乃至整个未来走势的关键节点，而公众看到的很多讨论似乎在某种程度上被操纵了。

<details>
<summary>Original English</summary>

**Speaker 0**: it's coming at such an important influction point for like the future of our country attack, and they just have this conversation that seems be manipulated to summit.

</details>

**巴雷特·里昂**: 这种操纵感非常明显。在我看来，科技的未来必须建立在真正独立的基础设施之上。如果我们现在亲手削弱它……

<details>
<summary>Original English</summary>

**Speaker 1**: it feels very manipulated. and to me, the future of attack is needing to build this infrastructure. now if we're crippling it,

</details>

### 空中险情与绝处逢生

**主持人**: 今天做客我们节目的是 **Barrett Lyon**。他可以说是科技界最传奇的人物之一，有很多不可思议的故事。每次和你碰头我都大为震撼，因为你随口讲的一个故事，就能把我这辈子做过的事全部比下去。最近我听到了一个我之前从未听过的故事——大概是在我们投资你上一家公司的那段时期。你是一名拥有飞行执照的飞行员，为了优化通勤效率，你选择开飞机往返各地。我记得有一次在我们开完会飞回去的路上，你遭遇了一场非常凶险的事故。

<details>
<summary>Original English</summary>

**Speaker 0**: well today were joined by bret lion. perhaps the most one of the most interesting people in tech II have a lot of stories to share. and IMO is kind of blown away every time you catch up because you tell me a new story that just puts everything i ever done one, an p, elen compason. um and i think the most interesting one i heard recently and i'd never heard it before. and this was during a period, i believe where we were investors in your previous company. um was you? you are pilot, you have a pilot license, and you decided to optimize your life by flying places. um and you had a uan unfortunate experience. i believe flying back from one of our meetings.

</details>

**巴雷特·里昂**: 确实如此。当时在湾区开车上班，单程原本只要 15 分钟，后来堵到了将近 45 分钟。我家人住在塔霍湖地区，我心想，开飞机过去差不多也是这个时间，那我不如直接飞着通勤。那时候还没有像疫情后那样普及远程办公，公司还要求必须肉身到岗，所以我开始频繁开飞机。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, well, i mean, as one is driving to work in the area, and i realize it was almost forty five minutes, which used to be fifteen, and my family lives up in the taahoo regions omicgoel. i think the plane can fly there and about the same time, maybe i could just can me te that way now is before um before worked from home was like qudified by um by coved. so i had a phylike can need to physically be present. um so yeah, i start flying.

</details>

**主持人**: 所以你的日常代步车其实是一架飞机。

<details>
<summary>Original English</summary>

**Speaker 0**: and so your daily driver was a daily flyer. great.

</details>

**巴雷特·里昂**: 没错。我在那架 **Cirrus**（西锐）飞机上累积了大约 1300 个飞行小时。那天在这边开完会后，我从圣卡洛斯机场起飞。大概飞到奥克兰机场上空的时候，发动机开始出现异样。我一开始以为只是燃油里进了水之类的杂质。我继续爬升，穿过了 B 类空域，感觉状态还行。然而紧接着，飞机几乎失去了全部动力。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. yeah. so i put like thirteen hundred hours on. i'm a serious. and yeah, one day after meeting here, i left and got in the plane took off from sancarlos and some where around over the over oakland airport bengine started acting up. and you know, i thought, maybe it's like some sort of water in the fuel or something. but i climbed up cleared braveo and felt like i was okay. and right after that, that lost pretty much all power.

</details>

**主持人**: 动力骤降的瞬间，你脑子里第一反应是什么？

<details>
<summary>Original English</summary>

**Speaker 0**: and um and what went through your head a media. we ah after that uah,

</details>

**巴雷特·里昂**: 我当时给朋友们发了条消息：“兄弟们，我遇到紧急情况了，我爱你们。”然后我向塔台宣布紧急状态，脑子里飞快盘算：我该迫降在哪里才不会伤及地面的人？我找到了一片空地。因为当时飞行高度还比较高，我发现那旁边有一座很大的机场，不是奥克兰机场，而是另一个军民两用机场。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, actually message my friends and say, i guys i'm emergency. i love you. um uh, i don't no, i just declared emergency and just try to think okay, where do i crash and not hurt people? i found a field, and it turns out, you know, i was up pretty high. and there is a yeah giant airport right next to it's not oakland, but it was uh you can, and field, uh uh, forget the name, me, the town, and uh giant ant milmilary.

</details>

**主持人**: 是阿拉米达（Alameda）吗？

<details>
<summary>Original English</summary>

**Speaker 0**: oh yeah, allimeter.

</details>

**巴雷特·里昂**: 不，是山脉背后的另一个，好像叫布坎南机场（Buchanan Field）。最终我落在了那里。但在这之前，看着那片野地，我内心经历了激烈的挣扎。飞机配有 **机载降落伞系统**（CAPS），我到底要不要拉伞？我读过那么多空难调查报告，很多飞行员丧命的原因就是没有及时拉伞。但我当时心想，机场就在眼前，飞机还在滑翔包线内。

<details>
<summary>Original English</summary>

**Speaker 1**: no, it was the other one, the other one, uh, on the other side of them not arrange there. uh you can't feel is a name of it believe, but um then you landed there. but so but before that kind kind of just field, then i was psyriright. well, i've get a parachute, but i seeks parachute. do do i ll ll it? i was thinking, alright. well, when i read all these crash reports, the reason the pilot dies is because dididn't paracachuolike II kind of like, well, the airport right there. and i'm still in the airflag.

</details>

**主持人**: 这款飞机有个很耐人寻味的悖论：它号称是有史以来最安全的飞机之一，但事故致死率有时反而不低，因为很多飞行员在危机时刻根本不敢使用自带的安全降落伞。

<details>
<summary>Original English</summary>

**Speaker 0**: and isn't that a funny corker that plane that it's like technically the safest plane ever made? but yet it's involved in the most crashes because people never use a safety fuure ure well.

</details>

**巴雷特·里昂**: 伞确实管用，但一旦拉开，整架飞机就报废了。火箭从机尾射出，会扯坏机体结构，摧毁飞机。而且拉伞并不意味着能稳稳着陆，座椅设计有缓冲吸能吸震的溃缩区，落地撞击力依然非常剧烈。

<details>
<summary>Original English</summary>

**Speaker 1**: and i mean it, it does work, but it destroys es plane too. so yeah, it's shoot a rocket back the tail and ririps out all the stuff out and yeah, regions, the plane. so and then it's not a guarantee that you're going to lan nicely on ground. and in fact, the seat, i think you're made with a crumble impact things. so when you do hit the ground, it absorbs some of the so compression,

</details>

**主持人**: 这整个惊魂过程持续了多久？

<details>
<summary>Original English</summary>

**Speaker 0**: and this is all playing out over how long is a period of time.

</details>

**巴雷特·里昂**: 大概就几分钟，甚至更短。我最终滑翔进场，呼叫塔台后顺利接地，直接滑进了过路机停机位。当时我整个人又惊又懵。下了飞机，眼前停着一辆巨大的专业机场消防车。车上下来一个人跟我握手。那一刻，后怕才真正涌上心头。我心想，如果稍微偏差一点，这个人就不是来跟我握手，而是来从残骸里清理我的尸块或者给我灭火了。那次真的是死里逃生。之后我租了辆车开回家，也下定决心彻底结束这种飞行通勤，风险实在太高了。飞机放了一阵子，后来飞到拉斯维加斯卖掉了。

<details>
<summary>Original English</summary>

**Speaker 1**: oh, i don't know a probably like minutes, less, maybe less. and then anyanyi just made it called the land and landed roll right on to the transit parking spot. there was as columate, it was frustrated, and it ll confused like when i got out of the plane. and then uh you know there's big fire truck thing. yeah, the huge ones yeah, that look like some kid made them. they're big um the guy get out of that shakes my hand. and then that's when it the fear hit me, because i'm like, that's the guy scraping my my brains, often, no, no, is the guy. this puts the fire out like the yeah that was close. and uh then don't like no right idea, have to get home somehow to run a run a car. drifl does kind of end of it from me, like, you know that the risk is too high. i kept the plane for while and ended up, uh, fearing it out to loss bagas and selling it. but oh,

</details>

**主持人**: 后来查明机械故障的具体原因了吗？

<details>
<summary>Original English</summary>

**Speaker 0**: does you ever find out what the issue were the cause?

</details>

**巴雷特·里昂**: 查清楚了，是极其诡异的三重故障同时爆发。首先，进气控制阀上的一块金属片断裂，被直接吸进了进气歧管，掉进油底壳，压坏了 3 号和 6 号气缸。紧接着，这引发了点火系统的电气故障，当时飞机换装了一套崭新的电子点火系统，在冲击下彻底罢工，直接损失了一半点火能力。雪上加霜的是，另一侧作为机械备份的磁电机（magneto）也同时失灵。这是一连串不可思议的连锁故障。更隐蔽的是，在地面怠速测试时磁电机看起来还能工作，发动机能启动，可一旦推到高转速，点火系统就彻底失效。排查了很久才搞明白。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, i was like three, really weird things at the same time. um one was a piece of metal on the eron take control vvve. but the canada ever broke off and sucked into the air and take manifold and then went ent in the oil pen. and it was crutioned at syyinder, three and six. i think, oh, wow, then that caused a an electrical problem with something with these spark, which was controlled by a brand uum um electronic fuel, electronic ignition system that stopped working. and so then i lost have ignition. and then at the same time, my magnedo on the other side, which is the backup also stopped word. oh yeah. so it's like three is like casascating strange failure. and then it was also, we're tuook is on the ground. the magnet a was kind of working a little bit. so it would start. but then when you went to highe RP ms and just went e bye bye. so yeah anyway, yeah, so that's what it was it took while to figure out. uh but yeah, there was thousand interesting to track le happens.

</details>

**主持人**: 这下你完全能理解为什么教皇每次下飞机都要亲吻地面了。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, now you now you understand why the year the pope kisses the ground when it gets off the plain eggs.

</details>

**巴雷特·里昂**: 是的，如果我这辈子还会买飞机，它上面的活动机械部件一定要尽可能少。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, if there's ever plple of my life, it will have less moving parts.

</details>

**主持人**: 最好还得有副驾驶和足够的冗余备份。

<details>
<summary>Original English</summary>

**Speaker 0**: probably have you're back up back in pilots and every dundancy.

</details>

**巴雷特·里昂**: 没弄错，一旦你单飞，你的风险敞口就会急剧放大。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, yeah. and if you fly a you can you you increasing your, i guess you're risk level little bit.

</details>

### Doxnet 的诞生：重构底层网络协议

**主持人**: 经历过生死往往会触发许多深层思考。我们今天想重点聊聊你的全新创业项目 **Doxnet**。这跟你以往做的东西大相径庭，看起来更贴近普通人的现实痛点，也更加紧迫和重要。能详细聊聊 Doxnet 是什么、创立它的初衷是什么，以及为什么你认为它在当下如此关键吗？

<details>
<summary>Original English</summary>

**Speaker 0**: yeah. well, that, and that sort of probably triggered a lot of things. i know we're here to talk about your new venture, which which short of is something very, it's say very different for you. it seems more like a more close to home, um more important. and so maybe we can talk a bit about dogs, sure. and sort of like why you decided to build? well, first of all, what is it what caused you to do it? um and and kind of maybe you're thinking around why this is important right now? well,

</details>

**巴雷特·里昂**: 首先讲讲名字的渊源。我小时候当黑客那会儿的代号叫 Dox。高中时我和朋友搞了个业务叫 **Doxnet**。在云计算普及之前，我们租用实体服务器，给用户开 Shell 账号（命令行终端账号）收费。这是一门完全合法的生意，我们在高中时靠卖每个月 5 美元的 Shell 账号赚了不少钱，拥有上千名付费用户。我们开发了丰富的功能，甚至形成了一个小社区。高中毕业后，我关停了那门生意开启职业生涯，但这个域名我一直保留着。

我一直对协议设计非常痴迷。今天的互联网在协议创新层面已经严重停滞了，极少出现颠覆性的底层协议，所有人都在修修补补往上堆砌应用。加之我敏锐地意识到网络审查的升级、个人隐私的蚕食，以及市面上各种 VPN 的野蛮生长，这让我下定决心：我们要从零搭建一套全新的平行网络，从根本上保护人们免受广告商追踪、恶意软件监控以及外部敌对势力的窃探。

<details>
<summary>Original English</summary>

**Speaker 1**: okay, the dogs net. first of all, uh, maybe she explaplathe name. ah ah ah you HI was uh is a kid at my hacer name was dox. and then i started a business in high school. my high school friend uh called doc's net, and we were renting this before cloud, and we renting ting ver server, basically giving user accounts for for money. yeah, um totally legid business. and in high school are making pretty good money with these shalaccounts. yeah shelacaccounts. we are something shall accounts for five milllies a month, but we had a thousand users. yeah, and we had all these features and people like it there. re's actually little community around it for a while. um but i should yeah got at high school and shut it all down, started my career and but it's kept the min. and also, i'm very fascciny about particle design and the fact that the internet is really kind of stagnated bit from a particle design. there's like not a lot of new stuff, all of its built on top. so there's that and then just noticing the shift of censoror censorship peoppeopleprivacy being eroted in all of this kind of thing kind of in the uprize of VPN. uh made it really interesting to make it a kind of an alternative network that kind of is designed from the ground up to protect people, uh from advertisers, trackers, mell, where uh and you know, foreign adversaries, trying to learn about what you're doing. and i mean,

</details>

**主持人**: 早期互联网的承诺本应是一个自由的思想大集市，不受限制，没有审查。最初构建互联网的那批先驱，大多都是坚定的言论自由至上主义者。然而在过去几年中，情况发生了翻天覆地的倒退。

<details>
<summary>Original English</summary>

**Speaker 0**: the original promise of the internet was this incredible marketplace of ideas, unrestricted, no censorship, right? i think a lot of original there, a lot of the original people around the founding of what became the internet, where were you know, free speech maxilists. it was sort of a very, very specific crowd. and i think over the last couple years, that tear point is has shifted pretty incredibly right?

</details>

**巴雷特·里昂**: 权力集中在了极少数寡头手中。比如一些国家的主导电信巨头，利用单一网络出口卡住全体国民的喉咙，强行控制人们的信息获取与决策过程。

互联网最初的设计初衷是彻底开放的。重塑这种开放性正是我的动力所在。在互联网早期，人们通过无线分组调制解调器实现无线网络通信，例如 ALOHAnet。而今天，网络边缘拥有功率强大的 Wi-Fi 芯片和设备算力，我们完全有条件构建更高效的 **Mesh 网状协议** 与真正的点对点（P2P）通信。整个互联网最大的污点之一就是 **载波级 NAT**（Carrier-Grade NAT），NAT 彻底阉割了终端双向直连的能力，扼杀无数优秀的分布式应用。Doxnet 的核心目标就是抹掉 NAT 的枷锁。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. and it's in the hands of a few. um so you know, for example, trying is good example is, is china that com trina to talcom m this, there has a china neck. yeah, anyway, either way, the um as a pregate chocold of the entire population using net network as an opportunity to force people in a different decision making processes. and the internet originally, like he said, is kind of designed with this like we're open kind of concept. so bring that back is some one of the things that was kind of interested in doing um trying to figure out new ways of doing things that might kind of leverage before the internet you way back back today. wireless networking was what uh hello honet or something like that is a wireless through um um packet modems and things. but now we have a really high powerful wifi on the edge, um incredible opportunities to create better mesh protocols uh and better p to p. and kind of really one of the biggest stains of the entire internet is curia. great net has just destroying applications of ability to do really cool stuff and um erasing that is kind of what i'm trying to go for jotcha.

</details>

### 网络层与身份绑定的错误结合

**主持人**: 人们总觉得网络审查只发生在海外威权地区。但我最近在美国本土某些州发现，因为推行 KYC（了解你的客户）或年龄认证法案，网络运营商开始在底层强制封锁某些健康或敏感网站。审查机制已经悄然渗透进美国本土。

<details>
<summary>Original English</summary>

**Speaker 0**: um and also, i think we know one of the interesting things as we always talk about sort of foreign governments, restricting internet access, right? we we harart on china in russia, um but i was in a in a state recently that has a know your customer rule, and they rereiring your blocking access to certain websites. um you know, whatever they define is being inappropriate. it could be a health website. it could be whatever um and so we're actually seeing the the creeof of kind of the censorship even within the united states.

</details>

**巴雷特·里昂**: 是的，这种审查正在美国蔓延，而且手段非常粗暴盲目。管理者试图强行让网络协议层去解决 **身份验证** 问题，但网络层根本不是干这个的，这是用错了锤子。**IP 地址绝不是身份证**。试图在底层网络基于年龄做访问限制，即便初衷合理，实现的层级也完全搞错了，根本不该转嫁给网络路由层。

更荒唐的事情屡见不鲜。前阵子思科的 Cisco Umbrella 系统把某家大型运营商直接整网封锁，原因是系统误将其判定为法国运营商。法国此前要求封杀上百个盗版网站，该安全服务商采取焦土策略直接封禁法国区域流量。一旦地理位置服务（GeoIP）出错，无数无辜的用户就会瞬间躺枪被阻断。这种基于中心化标签的封锁极其糟糕。

<details>
<summary>Original English</summary>

**Speaker 1**: yes, it's creeping into the US, and it's being done in in a way kind kind of ve because you're asking a lot of times are asking the network to solve an identity problem. and the network doesn't do identity. yeah, you know it's not that hammer yeah. and i kear the the nail IP adaddress is not your drivers licenence and asking people to do network restrictions based off of age. and things like that, it makes a lot of sense, but in different place in the stack. yeah, you know, if they want want to present, you know, restrict things for certain reasons that should be done in a much different way and not asking the network to do it. so yeah, II think that we're starting to see that united states for seeing it definitely elsewhere. um and it's also not just with like age restrictions. but uh interesting problem popped up the other day where google or a cisco umbrella broke for like a major carrier because they classify that carrier as france. they're not even in france, really as far as their corporate structure goes. but france had AA rule requiring them to block like one hundred plus pieracy sites. and they said, no, we're going to go scorch stors. we're just going to block france. well, then there's the blast radius of that, which is okay. well, then if your GO provider accidentally identifies somebody's the wrong location, then you're also know part of that policy. yeah, and it's terrible.

</details>

**主持人**: 自动化分类算法往往带来灾难。我们之前考察过一家做情感陪伴 AI 机器人的初创公司，结果一半的内容分类引擎直接把它判定为成人涉黄网站，而人家做的是完全合规的心理陪伴产品。

<details>
<summary>Original English</summary>

**Speaker 0**: those those classifications are always the worst. i mean, we were looking at we were looking at an investment opportunity in a company that makes chat pots that are focused on more like partnership type stuff for companionship type stuff. and half of the classifications engines classified is a doll contempt. and and just just sort of okay. well, this is like a legitimate like you know, EE partner e spouse side, like it's not doing the untoward stuff.

</details>

**巴雷特·里昂**: Doxnet 也遇到过类似情况，因为名字里带有“dox”（人肉搜索的意思），而且包含两个“x”，一开始直接被 Cloudflare 拦截标记。不过这也让我们顺理成章走正规申诉渠道完成了合规备案，反而帮我们扫清了所有通道。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, we've run into that a little bit to darks because it's got too axes in it. and then also, there's starcing yeah, but it actually worked out in our favor because we got flag. i think with uh claud and then we applied with no the proper means to go through there, uh, the registration process, and it opened up everything for us. just nice, nice ah,

</details>

### 去中心化架构与真正的点对点通信

**主持人**: 伴随着审查的加剧，各种隐私工具应运而生，其中最普遍的就是 VPN。能否深入谈谈，现有工具究竟存在什么硬伤？Doxnet 到底有何不同？

<details>
<summary>Original English</summary>

**Speaker 0**: yeah. and so maybe i mean, i think so. so you know, the this creeping, sort of the creeping information to terleterarianism um has given birth to a whole bunch products of which we know we're all super familiar right in vpn is probably the most most common. um and so maybe 'd be great to hear a little bit about sort of why the existing tools i know know. why are you building dogs? how was it different? maybe we could double click a bit on on sorter your thoughts around it.

</details>

**巴雷特·里昂**: 市面上绝大多数传统 VPN 本质上就是租赁式进出网关。运营商租用一台 VPS 服务器，装上通用代理软件。用户加密连接上去，再从那个节点把流量发往公网。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. sure. it's quite so a lot of the vpenons um i would say or just entry and exit points. so they're operate the leasa server from a landlorand uh set up a polite thethere's software on it. and then you connect to it, encrypted it, then then 're requests and things that you do on the internet comfort out that note.

</details>

**主持人**: 这只是用别人的 IP 替代了自己的 IP，试图绕过身份绑定。

<details>
<summary>Original English</summary>

**Speaker 0**: and that's to solve the your ip addresses your identity problem.

</details>

**巴雷特·里昂**: 仅此而已，很多人误以为这就带来了绝对安全，其实差得远。现代网络是完全可以通过 API 实时重构的。在 Doxnet，你的 AI Agent 可以直接调用 API 随时编排整个私有网络，传统的 WireGuard/VPN 协议仅仅被我们当作接入入口。

进入 Doxnet 内部后，是一个完全平行的网络空间：我们构建了 196 个在公网根本不存在的全新顶级域。你可以自由注册域名、分配私网 IP、租用公网 IP，在端系统之间通过 Gossip 协议下发网络策略。这是一个完全自给自足的新生态。

更重要的是，因为拥有全栈控制权，我们在上面实现了**真正可靠的 P2P 终端直连**。诸如语音通话、视频聊天等通信应用，完全运行在端到端网状网络之上。全部流量多重加密，**无需电话号码、无需邮箱、无需实名身份**。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah kind ah kind of is a way around that, i guess. and but it's also kind of people feel like there's more security to that. and i could argue against that. but um if it's very basic, it's not if you think about it that those networks are real time adjustiable, you could apply a api to everything. and uh also, you can are a well, here's an api that your agent can use. they can build an entire network. and you're just using the VPN protocols as a way to get into that area. and then inside, we can create either. you can call it while garden or a parallel internet or where everyone to call it, but we build an entire man network hundred and ninety six different domains that don't exist on the internet. you can register domains, you can lease IP addresses, you lethese meash addresses or public addresses. um h ate policy all within can contcontsystem goss. so it's a whole different ecosystem and there. and then on top of that, we've been able to use that um system since we we can kind of control it um to create p to p applications actually work. so like phone sall that vehicle chat, uh, all those those things sit best of class on top of the app run across the mish network. and it's all ecypted docha, no phone numbers, no, no email dresses, no names, no, uh, no, nothing.

</details>

**主持人**: 我们都有很深的信息安全背景。安全界有一句铁律：如果你想进行真正的机密对话，绝对不要在任何通电、带电池或有电磁信号的设备旁边谈。而你现在做的是打造一个无痕连接与通信通道，彻底不留任何日志与服务器痕迹。

<details>
<summary>Original English</summary>

**Speaker 0**: so it's it's funny. it's funny. and that's that's that's phenomenal because i think you know, we're we're both pretty well steeped in the security space. and you know, i think i come from sort of i've had a drilled into my head that if you want to have a private conversation, don't do it anywhere, anywhere, anything with with battery or 're electrical signal, right, right? um and so and so what you're saying is you've actually built this sort of trtranent ent um for focuks to connect and chat without there being any record.

</details>

**巴雷特·里昂**: 没错。注册 Doxnet 账号时，你只需要解开一个小拼图证明你是人类，就会获得一个专属安全 Token。你可以随时更换它，或者彻底销毁账号重建。在系统内部，你可以生成一个加密凭证分享给好友。表面上只是发了个好友邀请，底层实际上完成了一次非对称加密握手，赋予双方相互信任的专属特权。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. so you create your account, you just have to prove your human by doing a little puzzle. um once you do that, you get a talken at yours. um you can change it. um you can delete your account, make a new um, but once you're in there, you can create a certificate and share with a friend. you don't really know you're doing it just as yum biite friend and looks kind of like normal, but it's actually doing a crptographic exchange with each other. and then you have extra privileges.

</details>

**主持人**: 公钥基础设施（PKI）在历史上最大的教训就是：只要你把“PKI”这套底层数学概念摆到用户面前，产品就注定失败，必须将复杂的密钥交换彻底封装抽象。

<details>
<summary>Original English</summary>

**Speaker 0**: i think i think the key lesson of PKI was actually, if you tell people, it's PKI, it's not going to work. yeah, you have to get of abstract that later way yeyeah.

</details>

**巴雷特·里昂**: 严格来说我们采用的是私有密钥隔离体系，不依赖公网 PKI。当两个节点建立信任后，两台手机就能通过 Mesh 网状网络实现端到端直接打通。

这也解锁了没有任何文件体积限制的点对点文件极速传输。WhatsApp、Signal、iMessage 尤其是极其诡异的 Telegram，本质上都在搞欺骗：它们伪装成你在直接发文件给对方，实际上是你先把整个文件上传到中心化存储服务器，接收方再去下载。服务器带宽和存储通常集中在单点，上传下载速度严重受限。

但在 Doxnet 中，中间人、中转服务器被彻底剔除。**你的手机本身就是直连对方的服务器**。你给朋友发送数个 G 的大文件，走的是完全点对点的私网隧道，外加三到四层**后量子加密**（Post-Quantum Cryptography）。这才是捍卫真正言论自由的工具。

<details>
<summary>Original English</summary>

**Speaker 1**: it's it's well, it's not even PKI is private key influenly. it's not public. so anyway, you and your friend just decided, okay, we trust each other now that unloxxy ability for the phones over the mesion network to talk to each other indirectly. then also, you have all these really called fire file transfer stuff, which is no file size limit. theyou're big proms is on what's up signal imemessage telegram. and by the way, telegrams creepy, um all of those applications disguise themselves as you sending something to somebody else, but you're really sending something to a server. and then the servers, then having the other person pull that. so if you upload to file you're uploloadit and and also also the upload infrastructures and always is diriributed, or it doesn't might even be a little bit slow ah h might be be one. one part of UUS. you're uploading it to another to the uploaded a little slow. so when we use our applications, it extracts, all of that, it's gone. so it's really no middle man, no server in the middle, and your phone becomes a server to uh your frifast. and it's fast it. it works great. you can send our gget of five two one other and one week about its private network point point point point, yeah and and and ww. it's like three layers, four layers of encrypptuatlture. so yeah, it's post quantum. and i mean, these are really nice tools to have. yeah. so i know when you start stacking up all of these things. yeah, what's net is kind of like this yeah ooooit for freedom of speech. i guess,

</details>

**主持人**: 这不仅是言论自由，更是免遭全面监控的自由。

<details>
<summary>Original English</summary>

**Speaker 0**: freedom from surveillance. yeah.

</details>

### 商业 VPN 的暗面与基础设施控制权

**主持人**: 你刚才提到了 Telegram 令人不安的机制。市面上大量的免费甚至付费 VPN 同样水极其深。最生动的案例莫过于几年前全球多国警方破获的大型跨国有组织犯罪集团案件。当时 FBI 秘密自主研发了一款名为 **ANOM** 的端到端加密即时通讯 App，并伪装成地下黑市工具定向推广给黑帮。犯罪分子还互相告诫不要信任 Signal 因为背后有美国国家安全局，纷纷使用这款“绝对安全且小众”的专有软件。结果成百上千名毒枭的聊天记录被全量镜像留存，最终全网一网打尽。在各类应用商店里搜出来的几十款免费 VPN，背后又有多少干净的？

<details>
<summary>Original English</summary>

**Speaker 0**: you mention ed you you tetegragram is PPIII. ah uh, i would, i think i find all it just seems like a lot of the VPNI don't want to to say all because that's the absolutest term. but it seems like a lot of the PPS very, very eey, right? and and without basashing anyone specific, i think, for me, the most illustrative story was in the in the news. there was there was actually an issue where a bunch of organized criminals were arrested across the world. is australia. i believe it arrested some, the us said, arrested some, and it turned out that the fbi had built a secure messaging up um and then marketed it exclusively to organize criminal groups. and so these guys are like, don't trust signal cause that's the nsa. let's use. let's use this up because this is safe and only five people use it. i and it turned out that they all got inded ted because and they are letting muss them in prison. now um and so like in the US, right, we've seen this activity. and then if you look on any app store and you look for vpn, you probably find fifty vps, yeah that are all theare free abroad.

</details>

**巴雷特·里昂**: 免费的往往是最昂贵的。如果产品是免费的，那你本身就是被打包售卖的商品。

很多人忽视了企业治理与司法管辖权的重要性。Doxnet 主体虽然位于美国，但我们设立了一家独立的瑞士实体全权托管欧洲的业务，实现运营与司法层面的硬隔离。我个人绝不能容忍把自己的数据托付给一家产权模糊、幕后金主不明的所谓隐私公司。我们在股权架构、技术实现上保持极高的透明度。

很多人只看 VPN 承诺的“零日志政策”，但核心问题是：**那些底层服务器究竟是谁的物理设备？** 绝大部分 VPN 品牌根本没有自己的硬件，全是从不知名的机房承租的廉价 VPS。那些底层数据中心机房究竟在拿裸流量干什么？其上游骨干网络电信运营商又有怎样的镜像拦截策略？如果不亲自掌控从物理机架到光纤的上游链路，宣称的隐私不过是空中楼阁。

<details>
<summary>Original English</summary>

**Speaker 1**: well, if it's free, there's nothing free, yeah. and if you're not paying for it, you're the product you're being eaten alive. yeknow nice is, is as pretty oooolass. we can use them to protect people. and so the ark nets ts u space, but we also have a swiss company that handles all of european operations. so there's separation between the operations between the two regions were doing other regions like that too. so it's it's yeah. corporate governance actually matters in these these tegisst situations. but like you know, i just don't feel comfortable with my data going to a company that doesn't talk about who owns it, why they exist other than privacy. um you know, we made a very, very, very conscious decision that were very open, though what we're doing whoinvolved. why why the decisions of them made those ways? and and it's it's also a kind of to drive community too. but um yeah, i there, there are creey vapons ons there. oh,

</details>

**主持人**: 大众总把目光聚焦在 CIA、NSA、摩萨德等国家级情报机关上，但在现实生活中，很多安全威胁往往更加低级且现实。比如在早期加密货币浪潮中，不少人的钱包被盗空，就是因为他们使用了某些第三方网络代理服务。在一些地区，黑客团伙、有组织犯罪与当地情报力量彼此勾连，底层数据随意倒卖。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, i mean, an, you know know, it's not just. i mean, it's funny because we like to talk about nation states. we like to talk about intelligence agency, israel like CIA and SA. these are all super cool um but in reality, like the risks are a lot more low level than that right? like. and you know, for some of these, there are instances at the beginning of sort of the crypt of the initial crptotal currency waves, where people's accounts were getting drained. and they were using some of these services. uh there were another countries. and it turns out that, like you know, in of these countries, you have the meshing together of the intelligent state apperaats. and organized crime, right? and so and so you you see where these things start to blead into each other.

</details>

**巴雷特·里昂**: 这就是所谓的无管理服务器与共享托管的阴暗下腹部。如果不掌握裸金属服务器物理所有权，你就无法定义任何真正的安全规则。机房跳线之外是各级运营商的互联互通，为了避开这些暗桩，我们投入了极大的精力去构建真正的自建节点。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, i mean, uh then people look at the policies to the vps it on your logs know this. and the but question is like, okay, well, whose servers are those? yeah, are they owned by big brand VPN? or are they least and if there least who are they leased from? and what are those people doing with the data and what are their policies? but there's there's that whole underbelly because and learning about that is been difficult. but there personally was not not up to be building infrastructure all over the world as rapidly as i could. but i ended up realizing that, that was yeah. it's not your equipment. uh you can't set policy, it's just you can't. and then then the the next later policy is the the carriers and interconnect beyond beyond your cage, whatever it is. so it's been incredible amounof work to work around um yeknow the beare metals of service, kind of creepy underbelly.

</details>

### AI 智能体驱动的极简基础设施

**主持人**: 这正是 Doxnet 与众不同的核心分水岭：你们真正掌控了从物理裸金属光纤线路到上层软件代码的**全栈控制权**。

<details>
<summary>Original English</summary>

**Speaker 0**: and this is like one big difference with. i think a lot of folks right is that you own the full stack from like software, a wire,

</details>

**巴雷特·里昂**: 软件、光缆、硬件全覆盖。连我们自己用于动态路由与流量分析的 AI 组件，全部私有化部署在自己的裸金属物理服务器上。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah software wire, and uh even all the AI components run rounding and things like that or all on our bit on on r metal.

</details>

**主持人**: 早期交流时我就发现，你对主流云端大模型厂商极其警惕，坚持自己搭建 AI 架构。在全球 GPU 极度紧缺、电力瓶颈严重的当下，你们是如何在短短六个月内以极高效率铺开全球站点的？

<details>
<summary>Original English</summary>

**Speaker 0**: well, II think that was that was one of the funny things. i think when we originally start talking about this was um you were you were incredibly ditrusting of large influence in eye providers. yeah ah, and and you build your own AI stack. yeah, that's and so so i mean, GP user short in shortage. it's that it the power is hard to get everybody dy's 's titidata that are now like, how did you pull that off? yeah, and six months very efficiently.

</details>

**巴雷特·里昂**: 到目前为止，我们已经在全球部署了 26 个物理核心机房站点。

<details>
<summary>Original English</summary>

**Speaker 1**: well, i mean, we built uh so far, it's like twenty six sites around the world with you.

</details>

**主持人**: 这么庞大的网络，团队目前有多少全职员工？

<details>
<summary>Original English</summary>

**Speaker 0**: does it rounding and uh and how many employees in the company.

</details>

**巴雷特·里昂**: 参与的核心团队总共只有 12 个人。

<details>
<summary>Original English</summary>

**Speaker 1**: so i total, i think the people volved twelve, yeah, wow, yeah. okay.

</details>

**巴雷特·里昂**: 我们公司没有专职的网络管理员，也没有专职的系统运维（SysAdmin）。**所有的自动化运维全部由定制的 AI 智能体完成**。而且运行得极其稳定高效。这意味着我们内部接触机密基础设施的人为敞口极小，不存在成百上千名员工可能造成的越权与数据泄露隐患，内部人员威胁的爆炸半径被压缩到了极限。

<details>
<summary>Original English</summary>

**Speaker 1**: and we have no network administrator, no sa sedman. that's all done by AI. so um and it's actually works. and quite well, uh, i kind of i'm kind on top itory the nice thing, though, if you think about our footprint of, like, like who's involved, you know, we don't have a thousand employees with access to this network. yeah me, you know the the the the blast radiof, uh just the corporate structures, very minimal. yeah,

</details>

**主持人**: 这太震撼了。很多人不愿意公开讨论**内部人员威胁**（Insider Threat），因为这令人尴尬。但内部员工窃密和误操作向来是网络体系中最致命的隐患。依靠自主可控的 AI 智能体，你们直接规避了绝大部分人为风险。

<details>
<summary>Original English</summary>

**Speaker 0**: now, that's that's impressive. and i think you know, the yeah, the the you know, the thing, we very rarely talfortable, because it's kind of uncomfortable yejust, how great and extent inside der threat is yeah and how it's like the most crippling catastropphic side real taacks. are we sort of the insider threat angle? and now you're saying with agents like you're kind of leyour eliminminat least ast, a good portion of that race.

</details>

**巴雷特·里昂**: 没错。我们的 AI 运行在高度隔离的安全飞地中，绝不将上下文推理数据外传给公共 API。所有机架由物理摄像头 24 小时严密监控，没有任何无关人员能触碰机器。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, and it's running in its own a secure environment that is not exporting data like a one of the big AI compananso. so all the contets and inference and stuff stays inside, and we have it secured, and we monitor all equating with cameras. and uh, no one goes in touches.

</details>

**主持人**: 你们甚至有专门巡检机房摄像头的视觉 AI 智能体吧？

<details>
<summary>Original English</summary>

**Speaker 0**: any d have agents that watched ccameras for the actually well.

</details>

**巴雷特·里昂**: 严格来说，监控摄像头硬件厂商本身就集成了运动识别算法。一旦有任何物理异常移动，系统就会直接触发警报。我们甚至动过在机房几个通道安装激光防盗网的念头。

<details>
<summary>Original English</summary>

**Speaker 1**: i mean, technically, we don't, but the camera companies that made the agents don't try. yeah yeah, we get alarms. if something moves and something like yeknow, something goes around, but yeah, we've even thought about putting lasers in a couple of spots.

</details>

**主持人**: 像电影《碟中谍》里演的那样。

<details>
<summary>Original English</summary>

**Speaker 0**: but ah kind of make admission of possible stuff.

</details>

**巴雷特·里昂**: 确实很酷。我们甚至采购了电子触发开关，当激光光束被遮断时就会直接触发报警。但现实中遇到一个尴尬问题：现代数据中心为了安全与巡检，机房里的灯从不关闭，而且机房内部极其洁净无尘，既没有粉尘也没有烟雾，你根本看不到电影里那种酷炫的绿色激光束。

<details>
<summary>Original English</summary>

**Speaker 1**: i'm like quite now that be kind of fun. yeah, ah you got ta have the one data center. you take people too yeah, to impress them, right? that's the like the switch data centers and loasof agas. you know, they got the i gueep with the fifty commmachine. and ah ah II memean laser ers. i did this stick anyway, long story short. uh we did look into it and even got the the uh, the uh actuated switches. so so the bebeamdidid break. so we did actually set off the arms and things. but uh just the problem was the data center doesn't turn off the lights. so you don't get to see this really cool displays. oh, and there's no dust in there. and there's no cool play. yeah. so yeah,

</details>

**主持人**: 总不能在机房里撒滑石粉或者放烟雾弹来做激光秀吧。

<details>
<summary>Original English</summary>

**Speaker 0**: you can bring some talking powders, because that don't know know.

</details>

**巴雷特·里昂**: 哈哈，为了激光秀在机房里放烟雾弹就太离谱了。但这也反映出一个魔幻的社会现象：大众对现代数据中心的技术全貌几乎一无所知。

<details>
<summary>Original English</summary>

**Speaker 1**: so i go, let's smoke up the data center for laser show. that's the other thing. this starly crazy is people like don't understand data centers at all.

</details>

### 数据中心恐慌与公众认知偏差

**主持人**: 大众舆论中的数据中心简直被妖魔化了。

<details>
<summary>Original English</summary>

**Speaker 0**: oh, yeah, it's crazy. i mean, i think you're seeing that in the popular press, right?

</details>

**巴雷特·里昂**: 媒体成天炒作数据中心“吞噬大量水资源”。数据中心明明早就存在了几十年。冷却系统是一个闭式循环，只有在故障检修排空或少量自然蒸发时才需要微量补水，数据中心绝不是像怪兽一样每天靠喝水维持运转。这种荒谬叙事竟然能大行其道。

<details>
<summary>Original English</summary>

**Speaker 1**: oh, yeah. no, they drink water. yeah, so they come on. no, it's data. a digsters been round for a very, very long time yeyeah. they need water when they break, and you have to replunh some of the water and there some evaporation, but it's not like they're running off of water. it's a crazy part yeah.

</details>

**主持人**: 如果给人类创造的最精密机器排个名，第一大概是商业喷气式客机，第二绝对是现代化数据中心，其内部精密与封闭程度极高。

<details>
<summary>Original English</summary>

**Speaker 0**: and it's just sort of like i think i think in in order of like most impressive machines, humans of bill, like one is probably commercial airliners, right? and two is tta be data ascenters like there's so incredibly sophisticated their close systems.

</details>

**巴雷特·里昂**: 事实上从外部看，数据中心就是最普通、最枯燥的工业大楼。网上还有一些博主拍视频，配上所谓站在数据中心外听到的刺耳噪音。我进出过那么多机房，建筑物外部除了备用发电机平时根本听不到动静。很多视频是把机房内部的高转速风扇音频剪辑配到建筑物外观视频上，以此挑动公众恐慌。

<details>
<summary>Original English</summary>

**Speaker 1**: like yeah, i mean, the data ceners themselves are kind of just boring buildings, yeh. and the the other thing is like this sounds, i've never heard sound outside of a data cenner before before ah maybe a dator something before i see videos or people are watching data. and and i look at how it's audio from inside and dob people aren't smart of to know that yeah, that it's uh, it's fake.

</details>

**主持人**: 声音全被隔音墙包裹在建筑内部。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, i mean, yeah, that's all contained with inxisitithese thing.

</details>

**巴雷特·里昂**: 公众就是这样轻易被虚假信息裹挟的。

<details>
<summary>Original English</summary>

**Speaker 1**: people are being manipulated with this day. ate anything isn't it?

</details>

**主持人**: 这背后显然有特定利益集团在系统性地操纵舆论走向。

<details>
<summary>Original English</summary>

**Speaker 0**: amazing, right? and i think like it's going to be, i think, over as the years progress, it's it's going to come out that this was all just some sort of like very interested group of a organizations are interest. i completely manipulating public opinion to some end.

</details>

**巴雷特·里昂**: 作为深谙技术底层运转的业内人，看着大众舆论被彻底带偏，既无奈又啼笑皆非。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, but it's very interesting to be in the know and then watch this. and i go, oh, my gna, see people people missing the mark.

</details>

**主持人**: 你这几个月跑了二十多个数据中心，在外面看到过抗议示威的人群吗？

<details>
<summary>Original English</summary>

**Speaker 0**: have you seen? i mean, because you give been to twenty something data centors in the last couple months, if you seen actual protesters outside,

</details>

**巴雷特·里昂**: 从未见过。绝大部分大型数据中心园区——比如在弗吉尼亚州的数据中心走廊——周围只有大片草坪、野兔和空旷的停车场，根本没人抗议。

<details>
<summary>Original English</summary>

**Speaker 1**: no, never, yeah, i know i haven't like, no, you see nothing. it's just most of them, especially like the big data center parin. uh, virginia, yeah, you to see funny rabbits in the field. yeah, yeah, just a big building in a bunch of parking light nono, nothing. yeah.

</details>

**主持人**: 而那些数据中心集中的县区，正是靠着数据中心的巨额税收成为了全美最富裕的地区之一。

<details>
<summary>Original English</summary>

**Speaker 0**: meanwhile, let's like one of the ricast counties in the in the country, cucause of all the datacentters, right,

</details>

**巴雷特·里昂**: 没错，它带来了高薪技术人才、繁荣的基础设施投资。当地靠近骨干节点，连家庭宽带网速都快得多。至于所谓的数据中心喝干湖水，不过是因为有些数据中心（比如 Switch 在外围修建了景观应急蓄水湖），被好事者以讹传讹脑补成了怪兽吸水。这种阴谋论就像当年炒作“阿波罗登月是假造的”一样离谱。

但在当下科技与国家竞争的关键节点上，如果全社会被社交媒体上的虚假短视频带偏节奏，进而阻碍核心算力与通信基础设施的建设，造成的自废武功将是灾难性的。

<details>
<summary>Original English</summary>

**Speaker 1**: right, because it brings jobs. the people are work in them in the field pennies, and uh and it also brings high tech talent, yeah, and then also infrastructure and infrastructure powers everything you do. yeah, so if you have a data center your biby interinternet faster. yeah things like that work. but well, then they on which one it is, but and then they argument about data centors drinking water goes back to some quite that was like fabricated entirely like it's it's yeah. well, i think there was the switched data builbuilbuilnenear o. ah and they built this big like lake out there. and then people think that it lives off the lake. yeah and realiis, you know, if say, you have a chililer failure and you, you have to drain all that closest. now you need to refill. yeah ah it's thing to the like. yeah, so anyah. yeah, it's so it's interesting to see people. yeah ah know i work in these buildings and then you see the conspiracy theories, and it's like it we're way off here. i'm sorry. this feels just like them like the people that think the moon landing was fake. like it just feels like classic sort, but it. but i do think like this is it's coming at such an important inflection point for like the future of our country. attech yeah society and general. um and they just have this conversation that seems be manipulated to summit. it feelels very manipulated. and to me, the future of attech is needing to build this infrastructure. now yeah. and if if 're crippling it, then we're making bad decisions. yeah, and we're making bad decisions on instagram posts. yeah. and if for tippk, right, which you knows where that content is more like some crazy entty data in music video. yeah ah that's that's public opinion is being forced with being framed by that.

</details>

### 监控资本主义与数据聚合的危害

**主持人**: 这正好引出了 Doxnet 想要解决的另一半核心使命：防范商业广告与数据经纪商的无死角监控。人们总害怕国家安全局的监控，但现实中商业广告巨头的监控跟踪技术，无论在精度还是覆盖面上，都远远甩开了情报机关。甚至情报机关现在都在直接向商业数据贩子采买数据。

<details>
<summary>Original English</summary>

**Speaker 0**: well, this is the second half. i mean, i guess i know we had talked about sort of intelligence agencies in the big bad, scary government, right? but like and now we're talking more about clearly an operation that's probably being done by some sort of commercial interest to manipulate public inion on yeright, which goes to kind of the second half of why you built talks, which is like, you know, advertising, oh yeah, which is sort of like the like people like to think the nsa is incredibly sophisticated. but you know, advertisers are probably far ahead what they're doing. i think you're seeing now where intelligence agencies are actually using data brokers and using the techniques of that agencies.

</details>

**巴雷特·里昂**: 手机里的主流 App 全都植入了隐蔽的追踪 SDK。WhatsApp、各种通讯工具乃至苹果自家的遥测埋点（Telemetry），不管他们包装成“诊断数据”还是“元数据”，本质上都是追踪器。在 Doxnet 网络中，我们直接在网络层拦截并屏蔽所有此类遥测请求。由于网站核心业务逻辑不依赖这些埋点，拦截并不会导致页面崩溃。

曾有一位身价不菲但认知偏狭的富豪问我：“就算别人知道我在电商网站上买了条内裤，又能怎么样呢？”

我的回答是：危险的从来不是孤立的一单消费，而是**数据的全域聚合**。当你在不同 App、不同网页上留下的痕迹被数年如一日地积累、转卖、拼凑，分析师甚至能精准推断出你的作息规律、早晨几点喝咖啡、家庭收入、购物频次，甚至在你的伴侣知晓之前，就已经推算出你是在备孕迎接婴儿，还是在准备离婚转移资产。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. so the gllar apps have these tracackers. uh, what's up has DAT that what's up that uh, apple even has apple kilometry. they call a toometry or mada data, whatever they want to call it. it's it's some level of it is a tracker, and you can block them. it doesn't break the up, doesn't break most websites. don't have any problem with that telieary data breaking because of the rest of the site was still low. but you know, so he asked me very controversial, wealthy individual said, well, so what someone will won't know that i purchase uh underwear off of target tot com. and then my h well, it's not really that one. it's all of them when you combine all of the tracking that's being done on every different app you're using or every different website and it accumulates. and then it's being stored by who knows who where and being sold. and then when you aggregate all data points together, you could know if you're a coffee drinker, what time can you wake up in the morning? um what your income is where you shop um how after you purchase things. and if you're preparing for the birth of a child,

</details>

**主持人**: 或者提前侦测到人生的重大变故。

<details>
<summary>Original English</summary>

**Speaker 0**: they're perhaps for divorce, right? some other big wife eventate.

</details>

**巴雷特·里昂**: 他们往往比当事人的配偶更早嗅到端倪。切断这一切追踪不仅不会影响生活，反而能带来巨大的宁静。Doxnet 的整个网络架构正是为了从根源上粉碎并过滤这些垃圾追踪，回归到早期互联网纯粹的互联与创造，彻底摆脱被广告商和情报机构无休止审视的噩梦。

<details>
<summary>Original English</summary>

**Speaker 1**: they probably know these events move sooner. yeah, your spououse it. yeah ah um so turning it off, doesn't bother me at all. yeah, i love all that stuff being turned off. i hate that kind of stuff. so that's a big piece of the app is well, the the network. it's not just part. the apps part. the network is to kind of deconstruct all of that and get rid of it. and just kind of like the get back to the old internet that has h the ability to connect cted things and has the ability to your create. and and then also, you not not be sped on by you know,

</details>

**主持人**: 我们现在正迈入一个全新的拐点：我们迎来了大规模、低成本的“投币式智能”（大语言模型）。这就像把无限打字机交给了无数只猴子。当铺天盖地的遥测数据与强大的 AI 推理能力相结合时，得出的结论和个人数字画像将极其可怕。

<details>
<summary>Original English</summary>

**Speaker 0**: advertisers and governments and everybody else when it seems like we're really at an infleletion point because you have the birth of essentially coin operated intelligence at scale, right? you can deploy millions. you've got the prevent. you got the proverbial millions of of monkeys with millions are infinite monkeys with infinite typewiters. um and and so we're sort of looking at this world in which there's more telemetry. there's more data everything you do is being tracked, and you can combine that with intelligence right to to actually arrive at some pretty scary conclusion.

</details>

**巴雷特·里昂**: 是的，任何人只要把这堆无孔不入的聚合数据一股脑丢给 LLM，说一句“帮我分析这个人的一切”，就能得到令人毛骨悚然的深度洞察。这种针对个人的无缝画像不仅能用于精准商业收割，甚至能用来精心策划跨平台的公众猎巫行动。消灭这些无底线的广告追踪，人们的真实生活质量才会真正提高。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, you can take all that and just dump it into an ele m and say, tell me about this person. yeah, if you get an answer,

</details>

### 从抗击 DDoS 到创立 Prolexic

**主持人**: 早期互联网的成功在于开放自由。感谢你正在通过 Doxnet 重新赋予人们这种自由。其实多年前我们的轨迹就曾有过交集。我在 2000 年代初曾深入研究过分布式拒绝服务攻击（DDoS），包括当年臭名昭著的 **Stacheldraht**、**TFN**、**TFN2K** 等攻击工具。而你正是当年在全球站在最前线开创抗 DDoS 商业解决方案的先驱，比如你创办的 **Prolexic**。能讲讲当年是怎么切入这个领域的吗？

<details>
<summary>Original English</summary>

**Speaker 0**: probably really effective targeting against things like datasoners as well. right? yeah, like you start to see these mass movements orchestrated across multiple platforms. and you start to think like, uh, that's that's pretty clever. yeah, left people should be targeting those maybe not the data centers, but the tracking is pretty bad ad tracking. it's you know that that kind of stuff really can go away in your life would be better. yeah. um so yeah, that's like the court. it's like trying to recreate that vibe. the internet used to have and then try then see where we could take it yeah, with with bigger resources. and and things like that, you could start creating more partiticles and things like they don't exist yet. yeah, absolutely. i mean, the internet succeeded because it was free. and so thank you for trying to make it free. yeah try, but but have you have me me just is awesome. so don't don't, if you know know, but our paths cross a long time ago. um i was looking back through some of my archives and and II did a lot of work um started in the early acanands deed of spots. so stockled drought TFNTFNUK. um and then, obviously, a large large denal of dessert service distrited, ted count attacks. and you were at the forefront of building a lot of the solutions to prevent that, like it plexic.

</details>

**巴雷特·里昂**: 这其实又得追溯到高中时代的 Doxnet。当时就不断有人用洪水攻击打瘫我的服务器，我不得不通宵达旦摸索防御技巧与生存策略。后来我把自己总结的一整套《DDoS 幸存法则》写成了实战指南，并在 SANS 安全大会上作了演讲。那篇文档被 Google 收录后声名大噪，全球各地的求助电话开始打爆我的手机。

当时正值网络勒索犯罪的猖獗期：比如一家卖手表的电商为了抢夺圣诞促销旺季，花钱雇黑客打瘫竞争对手的线上商城；或者在“超级碗”决赛即将开打的几分钟前，全美所有的线上博彩网站瞬间被黑客集体打入瘫痪，黑客以此勒索巨额赎金。

面对这种严峻局面，我创办了 **Prolexic**。我的理念是：单打独斗的小公司不可能买得起对抗超大规模流量清洗的昂贵硬件，必须通过超大带宽与清洗云服务实现规模化防御。这实际上成为了**最早诞生的云计算服务模式之一**。后来这家公司被 Akamai 收购，但甚至直到今天，Akamai 依然保留着 Prolexic 这个产品名，这在科技并购史上是相当罕见的。后来我又创立了 **Defense.Net**，随后演变为 F5 Silverline。

在此期间，我还创立了专注于大视频分发的高性能 CDN 公司 **BitGravity**。在流媒体分发技术成熟前，用户在线拖动进度条往往要浪费数倍的下行带宽下载多余碎片，我们研发了大量底层黑科技帮助客户节省巨额带宽成本。

我毕生痴迷于构建大规模的底层物理基础设施。过去这些黑科技是为大财阀服务的，而今天，在 Doxnet 中，我希望把这些顶层架构能力回馈给普通人。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, well, actually, can it goes back to dogs, that and high school people were attacking my servers. and so we had to figure out better ways to protect them and techniques and tricks and and all the different things you need to do to survive a detados attack. and i started writing um kind of my list of what you would do to survive, and then somehow II presented that it sands. and then it got an in google, and then people start calling me. and then we started dealing with real cybrigragram extortion people traying to take. you know, one company cells watches, the other cells watches. the other one is attacking the other watch company during christmas cells season um or you know, supervols about to start and all the gambling sites ts, good dark. yeah, um things like that, and it got pretty serious. and so a builtihole company to protect businesses from these attacks. in the way i looked at is like you need big scale. you need to have the biggest most expensive stuff, and not everyone could afford that we''ll turn that into kind of at least services. is it it? no, it's when the first cloud services to exist and as pretty very successful still exist today. it's kami proxic ic theyy'even ket, the name that's just rare. and and then we did defence that later on which became a five silver line. and and then so in between all that i really like big scales, stuff and and band with. and uh so the other one we did was called big gravity. and that was one of the first or these first videocentricc c dians. so big file a big object delivery, and we have some really great customers. theare really on people got it. and then we had a lot attack around it to save people money. you know, people don't realize it hit play. and he's downloading a progressive file. and it before all this kind of media management stuff existed, you're just wasting band with just to scroll into the middle of a video. yeah, cocost people money. so anyway, we created all kinds of cool stuff er around video. and so as far as like building it, a new network for consumers, it well actually tually. it's a little bit for bots too. um i it's actually a lot of agentic networking components to it. it's a great at my alc because i love building big infrastructure. i love building building a scaled stuff, but now it's kind of twisting instead doing this for corporations or doing for people, never really seeing a lot of that being done at least well. so it's going to be fun to see. can i help people adapt to it? but um i think one of the more interesting things about that is, uh, we might even see some dedos on our netward. i'm sure you're ready for that well in bound from the internet. but what happens is somebody gets on to my network and start to using it inside and now have to deal with those those silly people. yeah, but um yeah, the truth is, even if you have privacy, there's still laws and you need to at least follow them as much as you can. so

</details>

### Opte 项目与 MoMA 的艺术跨界

**主持人**: 你身上还有另一个极具传奇色彩的跨界标签：你创作的视觉艺术作品，被纽约现代艺术博物馆（**MoMA**）永久收藏。

<details>
<summary>Original English</summary>

**Speaker 0**: but i think one other interesting thing. so you know it's it's sort of, and this is that kind of spending spending years talking with you? one other interesting thing is that you created an art work that actually hung the at the ethomoma. yeah, and it's part of the permanent collection.

</details>

**巴雷特·里昂**: 准确地说，有两件作品被永久收藏。大学时代我主修的是哲学，研究美学与早期理论人工智能。毕业后我从事白帽黑客与渗透测试，接单帮大公司做网络安全审计。在踩点渗透时，第一步往往是绘制目标公司的网络拓扑全景图。后来我把这个绘制过程自动化了。

某天午餐时我和朋友吹牛，打赌说我能用同一套网络探测与路由追踪技术把**整个互联网的完整拓扑结构**全部绘制成可视化地图。我们立下了一个 50 美元的赌注，当时我都觉得自己肯定要输。

巧合的是，不久后我骑自行车遭遇车祸被汽车撞倒，导致腿部骨折无法走动。在漫长无聊的康复休养期间，我整天坐在电脑前写代码，最终诞生了著名的 **Opte 项目**（The Opte Project）。

那幅如宇宙星系般绚烂的互联网拓扑图轰动了世界，不仅被 MoMA 永久收藏，还走进了波士顿科学博物馆等全球各大展馆。我后来还为它制作了动态演进视频，记录了互联网在千禧年泡沫前后的巨变，直观展现了各家科技巨头在网络版图上的兴盛与崩塌。当时我甚至还有幸与“互联网之父”文顿·瑟夫（Vint Cerf）面对面深入探讨这个项目。

<details>
<summary>Original English</summary>

**Speaker 1**: that's that's two pieces. um yeah. uh, college project i studied philosophy only, if studied. yes, i studied that. uh then the artist, aesthetics and anyway, smelter stuff it a lot of it was like theoreticical AI. yeah, oh, my wow. actually philosopy degree makes a lot of sense ce. this is helpful. uh, but yeah, i started mapping. uh, network saas. i was doing. i was a penetration test ter was hacking ethical hahacking into other companies, and i found that casing the joint was the easiest way to start. so you make it network diagram and where all the stuff is and how it all works. and what you think is where and then i start automating that. and then i got it mouthat lunch ch day and and bet some guys that um i could probably use the same technique to map the entire internet. and the that started a fifty dollar bet that i was pretty sure was gonna lose. and then i got hit by a car in a bicycle. oh, okay, yeah, and couldn't walk. and i said in my life are really slow, and i sat down and started doing the code for that. and that became the opi project. and they that ended up in not just maoma, but like boston museum of science, uh all over the world and different traveling exhibits. and um then imated animations of that, too. and it's pretty neat because it's that project. it's got a lot of intention, not just because it's blitks cool, but there's kind of really interesting history in in in the videos. things are happening, you could see companies crashing burn. and all kinds of stuff. and i was like enough to be able to talk to event surve about it. and yeah have opportunities to ask my questions to him, and sciricuthat is awesome and youyouve you've done one youve.

</details>

**主持人**: 你同时完成了两件极难的事情：一是创办顶尖的硬核科技公司，二是成为被殿堂级博物馆永久收藏的成功艺术家。后者往往比前者更难。

<details>
<summary>Original English</summary>

**Speaker 0**: probably accomplish two of the harder things do in this world, which is one starting a successful tech company. and two being a sucessssartist being an art as a successful artist, is probably much more difficult than starting attech company. yeah,

</details>

**巴雷特·里昂**: 那次经历非常超现实。MoMA 开幕当晚举办了盛大的派对，作为参展艺术家，策展人带着我在馆内四处游览。但第二天狂欢散去后，我却陷入了严重的**冒名顶替综合征**（Imposter Syndrome）和抑郁。我觉得这一切纯属偶然，我怀疑自己这辈子再也无法创作出达到同样高度的艺术作品了。那种感觉非常奇特。

<details>
<summary>Original English</summary>

**Speaker 1**: it was actually kind of strange, you know, after i went to the opening it imama. and it was, you know, this giant party, yeah, and you know, was one of the artist, and you know that we hadn't do you exhibit? and like the piece er er it was just kind of government, this is kind of cool. this is ADJ. there's 're drinking. and then uh and then the curators they took me to a siarly interesting parts of mmas. other properties are down, and it was really cool experience. but the next day, i kind of have this this and posture syndrome, yeah, where i just felt super depressed on like wow II ever going to experience. but arartists feels like ever again, because this kind kind of acacdental, you know, yeah um but yeah, i got to do it again, but but it was yet very strange surreal. uh moment in life strgly,

</details>

**主持人**: 你大概是科技圈里唯一获此殊荣的人。

<details>
<summary>Original English</summary>

**Speaker 0**: the only person in tech. they can say that,

</details>

**巴雷特·里昂**: 我许多全职搞艺术的朋友比我优秀得多，他们都惊呼：“你怎么就直接杀进 MoMA 了？”有时连我自己都快忘了这段往事，就像我也经常忘记那本记录我真实经历的纪实出版物一样。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, it's interesting in a lot of artist friends that are probably much better artist than me. and uh, yeah, they're like, what how did you get in the moment? yeah, that happened. yeah, and part the permanent collection, too. yeah, just me. yeah, you're one of a few hundred hundred thousand. yeah, yeah, i forget about that sometimes. yeah, i also figured about the book too.

</details>

### 莫斯科追凶与惊险撤离

**主持人**: 对，我们还没聊过那本书！

<details>
<summary>Original English</summary>

**Speaker 0**: that is true. yeah, we have not talked about the book. i don't know you want to cover that or sure we'll grow this on the list of great, great. why? for for story?

</details>

**巴雷特·里昂**: 我平时经营着一个 24 小时开着的 AI 驱动喂鸟器直播间，吸引了一个小圈子。前几天直播间里有位网友认出了我的真实身份，在评论区留言说刚刚读完了那本写我的纪实书，我才猛然惊醒：对啊，那段经历竟然还被白纸黑字写成了书。

<details>
<summary>Original English</summary>

**Speaker 1**: i keep for getting about that. it exists. yeah. and yeh recently. so II have an ai parade web camp that watches spatat s mmy yei. yeah, then it has, and it's twenty four hours. it's spbeen up for almost a year. now. it has got a little check community of people on there, and one of them figured out who i was. and then the other day, look, i just finisshreading the book about you. and like, what oh h what would you mean about? oh, sure. that's right. they figured it out.

</details>

**主持人**: 那本书讲的到底是什么传奇故事？

<details>
<summary>Original English</summary>

**Speaker 0**: so what is the book about you? when what is it about how it's been so like?

</details>

**巴雷特·里昂**: 那本书主要记录了当年创立 Prolexic 期间，我们千里追踪俄罗斯跨国有组织黑客犯罪集团的真实大案。当年有几个极其凶残猖獗的黑客团伙，对我们的客户实施高强度勒索攻击，甚至把我们整个团队的圣诞假期彻底摧毁，所有人被迫不分昼夜地轮班抢修网络。

<details>
<summary>Original English</summary>

**Speaker 1**: so it's about, i think it's the beginnings of proxic and tracking down these uh cyber criminals in russia. and specifically, these guys, there's a coucouple of extremely aggressive, extorting and damaging a lot of our clients. yeah ah ah so we just kind kind had enough of it. so this this got to end. i mean, we had christmas is destroyed because we're just dealing customers and network ortages.

</details>

**主持人**: 这伙人不仅是网络黑客，还是真正染指毒品走私、人口贩卖的跨国有组织重刑犯。

<details>
<summary>Original English</summary>

**Speaker 0**: when these are like real criminals. these are these are are just attkers. these are people that are doing human trafficking, the trafficking and arcotics, and they have a site hosoit.

</details>

**巴雷特·里昂**: 是的，穷凶极恶。后来那帮罪犯被抓捕，被判处了八年劳役重刑。在案件侦破过程中，我和同伴亲自飞往莫斯科深入腹地搜集追踪线索。在莫斯科停留期间，我们突然收到了当地线人传来的强烈危险信号：“你们已经被盯上了，立刻撤离！”我们不敢有丝毫耽搁，立刻动身逃离了俄罗斯。整本书完整还原了那段命悬一线的跨国追凶风暴。身处其中时觉得只是工作日常，如今回头看确实惊心动魄。

<details>
<summary>Original English</summary>

**Speaker 1**: there's some stuff going on. yeah, yeah, yeah, and they went to prient for a think, eight years and hard labor, something like that. yeah, i don't know what happened to them afterwards. but yeah, that, that was really we went out to russia. and uh, got turned around it. we were there in moscow for a while. then there was a reasof really interesting signals of like you need to leave now. so we laughgh. but uh, yeah, that hope le book is about that whole saga. what happened uh through that period of time? it's it's really weird because it's yeknow when you live it, it seems kind normal. but and you look back in OGG. so i was kind of crazy. yeah,

</details>

### 火人节狂欢与数字游牧反思

**主持人**: 每次和你聊天，总能挖掘出不可思议的新故事。火人节马上就要开始了，你参加火人节的历史有多久了？

<details>
<summary>Original English</summary>

**Speaker 0**: i tell you every time talk. i hear no news stories. how's i talk about burning man that could be a all episode itself. yeah, actually when was your first book burning man is next week.

</details>

**巴雷特·里昂**: 这周末就要开拔了，大概是我第 14 次参加火人节。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah ah this coming weekend. yeah, coming weekend. yeah, awesome. i think it's your fourteen you're fourteen. some mrunner II can't remember, we lost a couple there to ve it side. yeah, don't remember which ones i skipped,

</details>

**主持人**: 你在火人节有一辆名震全场的标志性艺术改装车。

<details>
<summary>Original English</summary>

**Speaker 0**: but um and you have a famous car.

</details>

**巴雷特·里昂**: 准确地说，那辆大名鼎鼎的艺术车是我合伙人打造的。当时他发起了 **Mayan Warrior**（玛雅勇士）项目，我则协助建立了 Mayan Warrior 营地。我们作为合伙人把这个疯狂的构想推向了巅峰。那台车从最初沙漠里自娱自乐的原型车，演变成了风靡全球的文化现象，吸引无数人花钱买票看演出。

这让我深刻领悟到：当你对一件事倾注无与伦比的热忱时，你周遭会形成强大的引力场，感召无数志同道合的人加入。今年是 Mayan Warrior 艺术车第一次不再开赴火人节黑石沙漠，那个移动超级音响舞台的狂欢时代正式画上了句号。不过我合伙人今年依然带了两件极其出色的静态艺术装置去沙漠参展。

<details>
<summary>Original English</summary>

**Speaker 1**: well, my partner has the famous car. yeah. so problem created mine warrior and i created mine warrior camp now. and so we were partners in that whole crazy thing for a while. and why that that car went from, like, you know, is fun project to like a whole global. uh um phenomenon like get, you know, people pay money to cosee it. it's crazy. uh, it was a lot of it was, you know what? let's think about this morning is like when your passion about something, it kind of cook kind of creates that or around you. and then other people pick up on it. and we were very passionate about that project. and i think it kind kind of inspired a lot of folks to do really interesting. other projects are similar to it. and this is the first year. we're not taking it to the to the player. it's no wow, not going. that's we're done. will you bedoin your laser feel there? no, wow. no right. no, well, they''ll be something. uh it's not not mit's probably got beaubeautiful art piece. there's two art pieces that he's bring that year that 'll be pretty cool, awesome, but uh, no more travelling superpower soundstage. it's that's gone.

</details>

**主持人**: 如今火人节沙漠里通了 **Starlink**（星链），这对火人节独有的无网离群氛围有什么影响？

<details>
<summary>Original English</summary>

**Speaker 0**: how's the ve bother now that you can get starling?

</details>

**巴雷特·里昂**: 这是一把双刃剑。从营地组织运作的角度来看，星链无可替代：比如水罐车缺水了需要紧急调配物资，或者查找人员、疏导营地门口的拥堵，即时通讯带来了极大便利。过去我们只能依靠大功率摩托罗拉无线电手台甚至短波电台呼叫。

但如果你带星链去沙漠只是为了整天躲在帐篷里刷短视频、看电影，那绝对是把火人节的精神彻底毁掉了。星链应该用于保障关键后勤，而不是让人沉溺在虚拟世界的奶头乐里。

<details>
<summary>Original English</summary>

**Speaker 1**: it's actually, i mean, you couldn't argue against it. you could arargue for it. i find that if you're running t for me like when you're organizing a camp or dealing with, you know, oh, we ran out of water on our car. it helps because you can communicate yeah, totally because we always bring high power red motorrole radio. yeah, and yeah, but but it's also like you know it's those communications device. so out there. i don't know it takes the a job when when it comes es, like finding things or organizing things, people don't get stuck at the gate very ononger. yeah, but if you're sitting there watching movies, that's probably the wrong use. yeah, wrong use for it. you know, no, if you if you're using it for uh anything other than like local communications, and maybe it's like the wrong wrong use, but but it, but it has changed a it. yeah,

</details>

**主持人**: 正如你所言，顺应内心的激情，能带你探索无数奇妙而深邃的兔子洞。而你就是那个永远在追逐热忱的硬核极客。非常感谢你能做客我们的节目。作为 Doxnet 的重度受益者，我由衷感谢你为这个时代打造了这样一款重塑早期互联网精神的神器。

<details>
<summary>Original English</summary>

**Speaker 0**: awesome. oh, as you said, right, like you ursue your passion and that takes it down all sworts of amazing rabbholes. and you are clearly someone that it is always pursuing his passience. so thank you. so much for stopping by i am, i am a incredibly happy dogs, net user and and and thank you for building it. it's good to get that old internet, vite back.

</details>

**巴雷特·里昂**: 这才刚刚拉开序幕，非常感谢你的信任与一路以来的支持！

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, well, it's just getting started and thanks for 're, trusting me that helped it.

</details>