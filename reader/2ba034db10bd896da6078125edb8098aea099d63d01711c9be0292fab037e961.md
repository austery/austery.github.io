---
layout: post.njk
source: https://yage.ai/share/midjourney-scanner-anti-vc-path-20260619.html
speaker: yage.ai
title: Midjourney 用生图的现金流造了一台扫描仪
date: '2026-06-19'
summary: 文章探讨了生成式 AI 公司 Midjourney 如何通过其生图业务的社区订阅收入，反向孵化出一台全身超声 CT 扫描仪。该项目展示了一种不依赖传统风险投资路径的前沿研发模式，即利用软件现金流驱动硬件研发和商业化进程，挑战了当前前沿 AI 领域资本集中于大型 VC 的主流趋势。
area: tech-engineering
category: ai-application
tags:
  - generative-ai
  - hardware-innovation
  - business-model
  - medical-device
people:
  - David Holz
companies_orgs:
  - Midjourney
products_models:
  - Midjourney Scanner
media_books: []
draft: true
status: evergreen
---

一个装满水的环形水槽，人站在正中央。三十五万八千个微型换能器嵌在环上，声波以水为介质，从四面八方同时穿过身体。二十一台上架服务器接到回波，靠
2 PFLOPS 算力重建出一帧三维截面图。

造这台机器的公司，叫 Midjourney。大部分人知道这个名字，是因为 Discord
上那个打几个字就能出图的 AI 工具。

2026 年 6 月，创始人 David Holz
在旧金山发布会上介绍扫描仪，讲了一句话：

> 「这台机器目前还没用上 AI，就是很酷的硬件加软件。」

来源：Athletech
News 现场报道。

一家靠生成式 AI 吃饭的公司，转身去做硬件，发布会上说目前没用 AI。

NEA 2026 年 6 月的大盘数据显示：全球前沿 AI lab 累计 1.68
万亿美元私募估值，93.6% 进了 OpenAI、Anthropic、xAI、SSI 四家 VC-backed
generalist 的口袋。所有主要 lab 都在加速跑同一条 VC
重注的资本路径时，Midjourney
站在了反方向。它靠生图软件的社区订阅收入，反向孵化出一台全身超声扫描仪。这件事的意义不在规模，在存在：前沿
AI 的资本路径不必然只有拿 VC 这一种走法。

## Scanner 到底是什么

Midjourney Scanner
俯视截面：人站在水环中央，40 颗 Butterfly 超声芯片环绕

扫描仪的全称是全身超声 CT（USCT, Ultrasound Computed
Tomography）。没有辐射，不用超导磁体，原理是在水里用声波重建三维截面。环形水槽直径七十厘米，装满水作为声波耦合介质，四十颗
Butterfly Network 的 Ultrasound-on-Chip 芯片环绕一圈，每颗控制 8,960
个换能器，三百六十度同时发射和接收。声波在水中以每秒 1,481
米的速度传播。二十一台上架服务器每秒钟吞掉 17 GB 原始信号，靠 2 PFLOPS
算力拼出整个人体截面的三维模型。当前一次全身扫描大约二十分钟，六十秒是下一代目标（Latent.Space
现场转述），不是当前实测值。

但物理规律摆在那里。超声进入人体以后，碰到骨头就反射掉绝大部分能量。头骨、肋骨、脊柱、骨盆这些位置，声波穿透率接近于零。同理，肺部充满空气，肠道含有气体，声波在这些界面一样会被阻断。这台扫描仪做不了脑成像，做不了肺成像，做不了肠道成像。Morningstar
引用的 Eric Topol 直接指出：“Midjourney’s
scanner can’t provide imaging of brain tissue like MRIs can.” USCT
和 MRI
测的是不同物理量，两类成像能覆盖的器官有重叠，但远谈不上可替代。

反过来，USCT 能做的事相对集中：体成分分析（body
composition）、肌肉骨骼成像、腹部实质脏器（肝、肾、胰腺）成像。Midjourney
从体成分切入 FDA 监管路径，也吻合这一定位。体成分在 FDA 分类里属于 Class
II 医疗器械（21
CFR
870.2770），审批门槛远低于诊断用途，用不着像肿瘤筛查那样走大规模临床试验。设备团队目前大约九人，扫过十二个人，还没有发布临床数据。公司正在走
ISO 13485 和 21 CFR 820
医疗器械质量管理体系路径，和 FDA 的接触刚刚启动。

硬件里面，Butterfly Network 是关键一环。2025 年 11 月 17
日，Butterfly Network 子公司和 Midjourney
签了一份五年期共同开发与授权协议，Butterfly 向 SEC 提交的 8-K
文件有完整披露（Yahoo
Finance 转载）。

协议条款：一千五百万美元首付，每年一千万授权费按季支付，最多九百万的里程碑付款，硬件商业化后收入再分成，外加芯片采购款。一台
Scanner 配四十块 Butterfly Ultrasound-on-Chip 成像模块。Midjourney
自己的公告页上从头到尾没提
Butterfly 这个名字。合作关系全靠 Butterfly 向 SEC 提交的文件，以及 The
Verge、MarketWatch 这些第三方媒体交叉确认，而不是 Midjourney
主动放的料。

Scanner 的落地方式不卖给医院。旧金山 Union Square
大约两千三百平米的四层空间，放九到十台扫描仪，请了设计冰岛 Blue Lagoon
的建筑师来操刀，租约已经签了，计划 2027 年底开张。交付形态是
spa，跟医院采购清单上的条目属于两个物种。

## 为什么稀缺

回到 NEA 那组数字。NEA 自己的判断是：

所谓 Neolab 市场不是真正的市场，就是一个篮子，装了四个名字。

NEA 2026 年 6 月数据：前沿 AI lab
私募估值 93.6% 集中在四家 VC-backed generalist

在这么极端的收敛结构里，Midjourney 的稀缺性来自四件事同时成立。

第一，它有一款在全球范围有付费用户的生成式 AI 产品。生图业务通过
Discord
触达几百万用户，靠月订阅付费。第二，它没有外部投资人。公告页白纸黑字写着
“Midjourney has no
investors”，自称「a community-backed research lab」。独立研究机构 Sacra 交叉确认：Midjourney 从
2021 年成立至今没拿过外部融资，完全自筹。Crunchbase
上融资记录为零。第三，现金流来自社区付费，不是企业合同。几百万日常用户的月订阅构成可预测的经常性收入。第四，这笔软件订阅产生的现金流正在反向流进医疗硬件研发。一千五百万美元的
Butterfly 首付、每年一千万授权费、九人硬件团队工资、Union Square
租约，全部由生图业务的订阅收入兜底。

单独拎出哪一项都不够稀缺。Hugging Face 同样是社区驱动的开源 lab，但
2017 年就拿了 SV Angel 种子轮，累计融资三亿九千五百万美元。Stability
AI 打着开源旗号，累计融资两亿三千一百万美元，每月亏损超过全年营收。四件事同时压在一家公司身上，才是
Midjourney 跟其他 AI lab 拉开距离的地方。

不过，落到数字上就没那么简单了。

Midjourney 的营收没有官方发布，只有第三方估算。Sacra 估大约两亿美元 ARR（2023
年），GetLatka
估五亿美元（2025 年）。两个数字差了一倍多。Midjourney
的真实营收外界并不知道。

目前的状态，更准确地说，是阶段性
bootstrapped，不是永久性的。软件阶段和早期硬件研发不拿 VC，这是事实。但
Holz
自己说过，规模化到五万台需要两百亿美元的资本开支。按第三方估算里最乐观的方案（五亿美元
ARR，五成利润率，每年两亿五千万美元自由现金流），两百亿除以两亿五，是八十年。规模化阶段大概率需要外部资本进来。

这套模式也很难被广泛复制。Holz 上一个创业项目 Leap Motion
融资超过一亿美元，最终以大约三千万美元被收购，收购价低于投资人累计投入的钱。Midjourney
公告页上的无投资人措辞，以及它对 VC
路线的刻意回避，背后有这么一段具体的个人经历。

## 有没有先例

一家软件公司靠订阅收入反向做硬件，听起来有点反直觉，但不是没有先例。

1976 年，Wozniak 和 Jobs 在车库里手工组装 Apple I。关键的杠杆是 Byte Shop
那张五十台的采购订单：Jobs 拿这张订单当抵押，向零件商 Cramer
Electronics 拿到了 net-30
账期。先有人承诺付钱，再买零件开工。现金流的顺序翻过来，让两个没钱的创始人启动了硬件生产。

1978 年到 1993 年，James Dyson 自己掏了十五年腰包，造了
5,127 个原型机。转折点在 1980 年代的日本市场：G-Force
吸尘器在日本卖到两千美元，在当时算奢侈品级别，用高溢价市场的现金流养英国本土主流市场的研发。1993
年才正式成立公司。

2012 年，Palmer Luckey 在父母车库里改装 VR 头显，靠
Kickstarter 众筹了两百四十三万美元启动开发。John Carmack 的背书和
Valve 的技术合作是关键放大器。Oculus 起步阶段确实绕过了早期 VC，但 2013
年开始拿融资，2014 年被 Facebook 用二十亿美元收购。

这三件事要跑通，前提是一样的：得有一批愿意为未完成产品先掏钱的用户，产品能拆出一个最小可交付形态启动现金流，创始人能接受漫长的研发周期。

对照一下当前做物理硬件的其他前沿 lab。Tesla 的工厂、Figure
的人形机器人、1X 的 NEO、Anduril 的自主系统，全部走在 VC-backed
路线上。Anduril Series G 估值三百零五亿美元，Founders
Fund 单笔就写了十个亿。这些公司同样证明前沿 lab
可以做物理世界产品，但它们的资金路径和 Midjourney
不在同一个方向上。用软件订阅现金流启动硬件研发，这个维度上 Midjourney
目前是孤立的。

## Holz 的轨迹

把 David Holz 的三次创业排在一起看，中间有一条松散的线。2008 到 2014
年，Leap Motion 从红外传感器信号重建手部姿态。2021 到 2025
年，Midjourney 从高斯噪声采样重建图像。2025 年到现在，Scanner
从超声回波重建三维人体。三件事不算同一个技术母题。重建这个标签太宽，往雷达和自动驾驶上套也一样能讲通。但可以看出来，Holz
长期被传感器、空间界面、生成式视觉、人体成像这几类问题吸引。有这条脉络在，Scanner
作为一个方向就不显得突然。

## 风险面

Butterfly Network 自己的财务状况不乐观。到 2025 财年末，累计亏损八亿七千九百万美元，靠
2025 年一笔八千一百万美元的股权融资吊着。如果 Butterfly
破产、被收购或者断供芯片，Scanner
的核心元件供应链会出现单点故障。四十颗芯片全部来自同一个供应商，目前看不到替代路径。

spa 模式还没被验证过。Union Square 首店 2027
年底才开业，单台经济模型（客单价多少、翻台率多高、运营成本怎么拆）全是未知数。消费者愿不愿意定期走进一个装满水的环形水槽做全身扫描，取决于定价、体验和拿到手里的价值感，数据层面找不到任何可参照的先例。

五万台和两百亿美元资本开支，是 Holz 在发布会上加了 speculative
前缀的数字，属于愿景，不是执行计划。软件利润和硬件规模化所需资本之间差了好几个数量级。规模化阶段大概率要接外部资本，而一旦拿了外面的钱，Midjourney
现在的无投资人叙事就会发生质变。

团队大概九个人，差不多是一家硬件初创公司种子轮的配置。扫过十二个人，没有发布的临床数据。监管路径才走了第一步：体成分归在
FDA Class
II，门槛相对低；诊断用途从临床试验走到上市审批，挑战量级完全是另一回事。

## 回到 93.6%

NEA 那个 93.6%
不是自然规律，是过去五年所有人同时朝一个方向跑出来的结果。只要有人在往旁边走，这个数就不一定是终点。

Midjourney 不一定就是趋势开头的那个信号。Holz 对 VC
的回避有个人色彩，Scanner 有可能开不出来，spa
模式有可能跑不通，体成分这个市场有可能撑不起五万台。

但它毕竟做到了几件可以验证的事。原型机已经建出来了。一个没有外部投资人、靠社区订阅付费运转的
AI
lab，正在用自有现金流支付芯片授权费、硬件团队工资和旧金山核心商圈的店面租金。NEA
大盘里 93.6% 的资金涌向了四家公司，但让资金不走 VC
那条路也能到达前沿研发。这件事的真实性，不取决于 Scanner
最后跑不跑得出商业化闭环。

旧金山 Union Square
拐角，四层楼面正在施工。接下来两年，那个地方会一直亮着灯。