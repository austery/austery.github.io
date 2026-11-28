---
author: Latent Space
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YHiqVRxGViM
speaker: Latent Space
tags:
  - materials-science
  - experimental-ai
  - superconductivity
  - robotics-automation
  - computational-chemistry
title: Periodic Labs访谈：AI驱动的材料科学探索与室温超导愿景
summary: 本期节目探讨了Periodic Labs如何利用AI与自动化实验结合，突破纯数字智能的局限，在物理材料领域进行探索。嘉宾们分析了从比特到原子的挑战，强调了实验数据校准计算模型的重要性，并展望了通过超级智能加速超导材料等前沿科学发现的潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Anjney Midha
  - Liam Fedus
  - Ekin Doğuş Çubuk
companies_orgs:
  - Periodic Labs
  - OpenAI
  - Google
  - Bell Labs
  - Stanford University
products_models:
  - Materials Project
  - Custodian
  - Jackson MD
  - Superdome
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 引言与开场致谢

**主持人（Anjney Midha）**: 但我们也必须思考，即便是第7期节目，其水准也可能非常完美、平稳，并且比今天做得更好。这毫无疑问需要巨大的投入，需要付出极高的实验与验证代价，而这一切都是为了换取扎实的结果。同样，这正是机器学习为何能取得如此丰硕成果的原因——明确目标并全力达成。但显而易见的是，这一切都是为了探索未知的可能。正因如此，无论开源还是闭源模型，都能在现实世界中得到广泛应用。因为我们坚信，这能让更多此前无法企及的实验与探索成为现实，包括在“终极极限”下探索宏伟的室温超导体研发。

<details>
<summary>Original English</summary>

**Host (Anjney Midha)**: Аха ҳаргьы ҳхәыцуеит Ажәабжь 7 акәзаргьы иҟалоит даара Инаӡоу, еиҟароу Иахьа аасҭа еиӷьуп, Уи хьаас имаӡам Ахарџь аҭаххоит Аԥышәарақәа рзы Адкылара алҵшәа. ИАРА УБАС Уи зыхҟьо убри ауп изакәызеи амашьынатә ҵара даара алҵшәа амоуп уи аҟны , изакәу иазыҟаҵоу. Аха ари, еилкаарала, иазыҟаҵоу. Убри азоуп ҳара Ма иаарту ма иарку амоделқәа ирылшон Урҭ рхархәара адунеи, избан акәзар ҳара ҳакәӡам Ҳара агәра ҳгоит уи ҟалар шалшо аԥышәара. Убасҵәҟьа, "нҵәарала", аԥҵара Амҩангага ду ауада атемпература.

</details>

**主持人（Anjney Midha）**: 在正式进入本期节目之前，我想对各位听众朋友说几句话。感谢大家一路以来的支持！我们此前未能尽早制作并推出视频版本，但现在只要大家喜欢，就可以随时观看我们的完整视频录像。我们的赞助商也几乎定期向我们提出申请，希望我向所有观众转达：收听和观看节目完全是免费的，唯一的请求就是希望大家点击订阅。我想对大家说的唯有一点：我们每周都会如约为大家带来新内容。只要大家持续关注，我向你们保证，我们的节目一定会越来越精彩！好的，今天我们非常荣幸能与 Liam 和 Doğuş 一同坐在这里交流，非常感谢二位的到来！

<details>
<summary>Original English</summary>

**Host (Anjney Midha)**: Ԥхьаҟа ҳцаанӡа Аепизод, исымоуп ахәыҷы Ацҳара азы listeners. Иҭабуп. Ҳара иҟаҳҵон аиқәыршәара рылымшеит агәырҿыхага, уара убас Иубарц уҭахуп авидеонҵамҭақәа рыхәаԥшра. Есымша шамахамзар ҳара ҳахь унеиуеит Аспонсорцәа арзаҳалқәа ҟарҵоит Зегьы шәахь аҳәара. Зынӡаск ихы иақәиҭуп аҟаҵара, ауп агәыҵха ақәыӷәӷәа " аҽҭаҩра". Уи Акы заҵәык иуасҳәарц исҭаху you every week. Уара Уара иҟауҵоит, ажәа усҭоит. ари ашоу еиҳагьы еиӷьуп. аусқәа. ИБЗИОУП. Ҳара ара ҳаҟоуп абра Лиами Догеи рыцны Иҭабуп шәахьшәыдышәкылаз азы.

</details>

**Liam Fedus**: 很高兴能来到这里，非常感谢你的邀请！

<details>
<summary>Original English</summary>

**Liam Fedus**: Ааи, ҳаигәырӷьоит ара ҳахьыҟоу, насгьы Иҭабуп шәахьааиз.

</details>

**Ekin Doğuş Çubuk**: 没错，非常荣幸，我也很期待今天的讨论。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Даара исгәаԥхоит. Исгәаԥхоит.

</details>

---

### Periodic Labs 的创立初衷：突破纯数字智能的界限

**主持人（Anjney Midha）**: 人们常说：“单纯的数字智慧固然必要，但它远远不够。”创办 Periodic Labs 的核心理念究竟是什么？当初究竟是什么促使你们下定决心，去走一条前人未曾走过、充满未知的探索之路？若要在现实世界中真正拓展人类知识的边界、推动实质性的科学进展，绝不能依赖凭空想象。在实验室里，你无法坐在空荡的房间里凭空获得成果，必须全方位考虑现实中可能发生的一切意外与实验反馈。面对未曾预料的变数，科学探索本质上就是一个不断试错、循环往复的迭代过程。这也正是我们最为核心的信念所在。

<details>
<summary>Original English</summary>

**Host (Anjney Midha)**: Уа Иаҳәоит: «Аҟәышра Иаҭахуп, аха изымхо. Аҿыц ? Апериодик, зыӡбахә ҳамоу Уи иазхәыцит иан иаԥиҵеит: уара иузыҟаҵомызт азхәыцра" амҩа аӡбара. Адунеи Адырра аҳәаақәа рышьақәыргылареи рынагӡареи Апрогресс, иаҭахуп дара. Hmm, none. аномер ауада, урҭ ирышьҭуам Зегьы уазхәыцроуп иҟалар алшоит, ум, алҵшәа аԥышәарақәа, иззыԥшуи Узқәымгәыӷӡоз, уара аитеративтә процесс. ИАРА УБАС Ари ҳара ҳзы ихадароу Агәрахаҵарақәа, избан ҳара ари иаԥиҵеит, нас уи ауп

</details>

**Liam Fedus**: 没错。从一开始我们就清楚地认识到，我们所追求的目标并非单纯构建一套数字维度的通用智能系统，更不是仅仅在计算机里模拟物理世界，而是要直接深入物理现实本身进行探索与研发。我们深信，唯有直面物理世界，才能孕育出全新维度的科学智能。

<details>
<summary>Original English</summary>

**Liam Fedus**: Убри аҟнытә ахаҭа инаркны Ҳара алагамҭазы иҳаӡбеит, Иаҳҭахузеи амаҭәашьартә ҟәыӷара асистемақәа Аинтеллект, асимуляциа афизикатә дунеи, аха Аҿиарагьы афизикатә аԥышәа. Ҳаргьы Ҳара агәра ҳгоит абри аҟынтә Даҽа хкык цәырҵуеит аҟәышра.

</details>

**主持人（Anjney Midha）**: 在像 OpenAI 或 Google 这样的科技巨头面前，作为初创团队，你们并没有那些巨型工业实验室无尽的硬件与算力资源。换句话说，你们必须另辟蹊径，跳出既有的游戏规则，走出一条全新的道路。

<details>
<summary>Original English</summary>

**Host (Anjney Midha)**: Сгәанала, аригьы џьашьахәыла, аҟны еиԥш OpenAIи Googleи рҭагылазаашьа, Уара акгьы умаӡам урҭ рҟны аресурсқәа Алабораториа дуқәа . Даҽакала иуҳәозар, иуҭахын Уцаны ухатәы ҟаҵа акы, ум, избанзар уара Ухы иҭуҵаауашәа Ахәмарра ахатә ԥҟарақәа аныҟәара.

</details>

**Ekin Doğuş Çubuk**: 是的，这正是我一直想表达的。此前这样的架构与跨学科范式在行业内根本不存在。我们竭尽全力将各个领域的顶级人才汇聚一堂：固态化学家、凝聚态物理学家、硬件工程师、机械臂与自动化专家、大语言模型专家以及计算机科学家。其中许多技术与实验手段都是极其前沿的，例如利用机器人自动化操作平台进行精确实验。能够把这一整套多元的顶尖团队与物理设施结合在一起，对于解决这个领域的难题具有决定性意义。在我看来，当今真正具备这种跨学科综合攻坚能力的地方，恐怕只有类似贝尔实验室（Bell Labs）这样的科研圣地了。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Ааи, уи ауп исҳәарц исҭаху адҵа еиԥшу Сгәанала, ари ахаангьы иҟалом. did not exist. Ҳара Ҳара ҳҽазаҳшәоит Ахимикцәа реидкылара- ацәеижь ӷәӷәақәа, Аҭагылазаашьа ӷәӷәа афизикцәа ацәеижьқәа, анџьнырцәа Ахардвер апрограмматә еибыҭа, LLM аекспертцәа, акомпиутер аҭҵааҩцәа. Um, and some Абарҭ атехнологиақәа рҟынтә даара ҿыцқәа, иаҳҳәап, аԥышәарақәа, Аманипуляторцәа иалагеит уи иазкны. Аԥышәа Ари амазаара даара акраҵанакуеит Абарҭ ауаа зегьы рзы акыр зҵазкуа. Ум, насгьы сгәы иаанагоит иҟоуп Белл Лабс еиԥш иҟоу аҭыԥқәа,

</details>

---

### 现实世界的物理闭环与纯代码推理的根本差异

**Liam Fedus**: 没错，我想和世界上最顶尖的研究者们一起探讨这个课题：这里的核心差异究竟在哪里？到底发生了什么本质变化？我认为大家现在已经看得越来越清楚了：我们的核心数据并非来自互联网文本，而是直接来源于我们的物理实验室，这正是我们赖以立足的基石与真理。单纯依靠现有文献或教科书中的结论来完成前沿材料的优化设计是根本行不通的，因为我们正在探索的领域早已跨越了人类已知文献的边界。

<details>
<summary>Original English</summary>

**Liam Fedus**: Ааи. Сара исҭахуп акы Алацәажәара Иреиҳау руак аҭҵааҩцәа. Убри азын, Излеиԥшымзеи Иҟалазеи араҟа? Сгәанала, уара уажәнатә иҟалап еиҳа еилыкка: ишԥа Уара иухәҭоуп Ааи, ус ауп исҳәарц исҭаху . Uh, our data Ҳара ҳҟынтә иаауа Афизикатә лабораториақәа , насгьы ари ҳара ихадоу аҵабырг. Имариам адгалара Аоптимизациа аҭакқәа ирыбзоураны Астатиақәа рҟынтә еилкаау мамзаргьы арҵага шәҟәқәа, избан акәзар ҳара ҳара урҭ аҳәаақәа ҳарҭысуеит.

</details>

**主持人（Anjney Midha）**: 我完全赞同，这是整个范式中最关键的区别。但随之而来的问题是：现实反馈往往伴随着极大的不确定性。在纯数学优化或纯软件算法中，计算结果具有确定性和极高精度（high accuracy）。然而在我们的物理研发闭环中，一旦引入物理实验与开放材料环境，一切就变得截然不同——闭环操作并非每次都能产生确定性的预期输出，对吧？

<details>
<summary>Original English</summary>

**Host (Anjney Midha)**: ИАРА УБАС Сгәанала, ари иреиуоуп Зегьы иреиҳау аиԥшымрақәа. Аха азҵаарақәа цәырҵуеит, Иаҳҳәап адкылара ақәымгәыӷра. Убри азын, Аоптимизациа аҟны аматематика, уи иамоуп high accuracy. Уара Азнеира амц Ҳара ҳпроцесс аганахьала ари ахадоуп. Иаҳҳәап, ҳара Ацикл аус адулара Аартратә маҭәахәқәа , акы ҭыҵӡом ус акәӡами?

</details>

**Ekin Doğuş Çubuk**: 没错。在物理材料合成与表征过程中，整个流程本质上具有随机性且充满了噪声与误差。有时候，即便在不同设备之间，也会产生难以忽略的读数漂移与测量偏差。我们必须允许并处理一定程度的不确定性（a certain amount of uncertainty）。因此，核心决策在于你们如何设计底层推理与实验探索策略。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Уи адагьы Ахҵара апроцесс иҟалар ҟалоит стохастикатәи ииашам. Зны-зынлагьы ажәҩан Абжьара ацәхьаҵра еиуеиԥшым амашьынақәа. Иҟаҳҵоз џьшьа a certain amount. ИАРА УБАС Аӡбара, ишԥаҟашәҵеи Ахәыцратә стратегиақәа .

</details>

**Liam Fedus**: 是的，我认为这正是在通用探索空间、常规机器学习工具以及现实物理验证之间架起桥梁的关键。但我们必须直面这种高度的不确定性。如何才能最有效地利用每一次宝贵的实验机会？我们必须依靠更具针对性、更高效的物理迭代（iterations）。我们深知这是一个当下最受关注的核心议题。正如你所探讨的：在面对未知的材料空间时，人类科学家究竟是如何思考与决策的？真实的科学探索逻辑到底是什么？

<details>
<summary>Original English</summary>

**Liam Fedus**: So I think that between еицырзеиԥшу амҽхак. Истандарту аҵара ахрахәара аинструментқәа, Уи агәаҭара . But we have to go. Аҩаӡара ҳарак uncertainty? Ас еиԥш иҷыданы Еффективла ахрахәара амш? We are much , уахьуҭаху iterations. Ҳара иҳамаӡам Сгәы иаанагоит ари уажәнатә иҟоу темоуп Уара узлацәажәо еилыркаа: изеиԥшраз Ауаҩы дышԥаизнеиуаз Уара уаԥхьа аԥҵара, насгьы иарбан ииашаҵәҟьаны ?

</details>

**Ekin Doğuş Çubuk**: 我认为这里存在诸多根本性的挑战与误区。其中之一就是人们误以为科学实验可以像纯数学或纯计算机编程那样被完美形式化。但现实绝非如此，两者存在巨大鸿沟。当你编写代码时，所有的上下文都可以被完整封装在人类语言或大模型已有的上下文窗口内。代码环境拥有明确的公理系统，所有的逻辑、函数调用以及 API 接口都是确定的。在这种封闭体系下，一切都在控制之中，你的双手不需要触碰任何物理实体，逻辑清晰易辨。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Сгәанала, араҟа ирацәаҩуп. ашәарақәа. Урҭ руаӡәк уи аума, Сара сгәанала, зегьы Аҭҵаарадырратә ԥышәара инаигӡароуп иалкаау Армаҷра ашәагаақәа. Аригьы Даара еиԥшым Апрограммаркра аҟынтә мамзаргьы аматематика. Убри азын, Уанбаҟауҵо Апрограммаркра, Аконтекст зегьы иалшоит Иҟазарц Ауаҩы ма абызшәа модельқәа. Ари еизакуп аксиома, џьоукы ауаа ирызцәырҵуа алҵшәақәа афункциақәеи ааԥхьарақәеи APIs. Ус анакәха, иуҭаху зегьы азы иаҭахуп азхәыцрақәа, ҵаҟа иҟоума анапы, уара Даараӡа иҟазароуп ҟәышны ари еилкаа.

</details>

---

### 从比特到原子：热力学规模与真实实验室的物理噪声

**Liam Fedus**: 但在物理世界中，正如大家所熟知的，我们面对的是原子数量级的宏观体系，其复杂度远远超越了单台计算机能够穷举或精确模拟的范畴。正因如此，我们必须将真实系统的测量规模与信息比特紧密结合。你知道吗？这正是热力学第一定律以及统计物理的核心命题所在。最开始我们可能只能通过极少数宏观状态变量来描述体系，但这些宏观变量远远无法完整刻画系统微观状态的无限复杂度。

<details>
<summary>Original English</summary>

**Liam Fedus**: Афизикаҿы, ишыжәдыруа еиԥш , ҳара ҳалагоит Еиҳаны ахыԥхьаӡара ԥаса аасҭа атомқәа ҳара иҳалшоит аиқәырхара акомпиутер. Убри азы, Ицар акәхоит ашәарақәа рхыԥхьаӡара абитқәа рыхцәажәара асистема, ахыԥхьаӡарахь абитқәа ҳара иҳалшо Иудыруама, ари ҟалап раԥхьатәи акәын Аԥхьатәи аҭахра атермодинамика. Раԥхьа урҭ ракәын фба аҽеиҭакқәа зынӡа ибзианы иҳаилнаркаауеит зеиԥш ыҟам. Абри ауп.

</details>

**Ekin Doğuş Çubuk**: 确实如此。比如体系中包含多达 $10^{23}$ 甚至 $10^{27}$ 量级的微观粒子，而在实验中你往往只能控制环境温度、宏观状态以及少数简化的外界变量。换言之，在绝大多数物理条件下，微观状态的组合空间是天文数字。如果仅仅依靠直觉或纯理论假设，预测往往会出现严重偏差。现实中晶体结构的生成往往依赖极为微妙的动力学路径（kinetics），我们必须搞清楚如何去扩展这些微观结构。我们深刻意识到，状态路径的动态演化对于最终相态具有决定性影响，动力学控制至关重要。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Иаҳҳәап, шәара ишәымоуп , урҭ 10 ыҟоуп 23-тәи мамзаргьы 10 27-тәи амчрахь, аха шәара аҳауа аԥхарреи аҭагылазаашьеи, насгьы имариоу аԥсахгақәа, зегьы. That is, he says еиҳарак аҭагылазаашьақәа рҿы, ус акәӡами? Иаҳҳәап уара агәаԥхара ииашам? Ари ииашаҵәҟьаны structures. Нас ишԥа насгьы уи шҳарҭбаатәу Ааи? We decided that уи аҽеиҭакрақәа даара акрызҵазкуа. Абри аҟынтә Иеиликааит уи акрызҵазкуа. Kinetics даара акраҵанакуеит. Убри азы аҽазкра Ари аилкаара .

</details>

**Liam Fedus**: 人们在研究四面体（tetrahedra）配位以及各类复杂的晶体化学时，往往容易陷入纯理论推导。但科学不仅需要理论构想，更需要尽可能在真实世界中采集高保真的实验数据。你在实验室里拥有实验记录本，详细记录所观察到的一切现象。但显然，这其中依然有大量隐性变量被遗漏了。

<details>
<summary>Original English</summary>

**Liam Fedus**: People are also very агәаԥхара атетраедрақәа, насгьы ахимиа абри. So, this is from атеориатә ган, насгьы Иахьынӡазалшо аизгара еиҳаны адыррақәа. Убри аҟнытә Уара алабораториа умоуп ажурнал, уара иуҩуеит иубо зегьы, уҳәа убас иҵегьы. Аха еилкааны , уи, ҳәарада, ирацәоуп Иуцәыӡуазеи?

</details>

**Ekin Doğuş Çubuk**: 正如 Liam 所提到的，现实物理实验中存在各种意想不到的工程挑战与扰动。举个具体的例子：随着实验时间的推移，你的高温炉加热管和内壁材料会逐渐老化、性能衰退，反应腔体的温区均匀性会越来越差（worse and worse）。另一个普遍难题就是炉膛内部温度场的不均匀分布，不同放置位置的反应物所承受的热历史存在显著差异。此外，还有光学读数和精密仪器的环境震动与漂移问题。我记得有一次，经过反复排查，我们最终发现竟然是因为有人在夜间走动，其脚步引发的地面微震直接干扰了超高精度仪器的读数。这些在纯软件或理论计算机科学中从未遇到过的现实物理噪声，在真实物理世界中无处不在。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Убри аҟнытә, Лиам ишазгәеиҭаз еиԥш, Абарҭ зегьы цәырҵуеит ауадаҩрақәа. Ҿырԥштәыс иаагоуп, Аамҭа цацыԥхьаӡа уҟәаҟәа иаԥсахоит, избанзар аамҭазы Ахәҭа ахархәара аматериалқәа уара апроцесс, иԥсыҽхоит насгьы Иаҵанакуеит . So every time, Адуховка, уи зегьы ҟалоит worse and worse. Егьы Апроблема избан акәзар аҳауа аԥхарра ауниформа. Шьҭахьҟа Уара уахьыҟоу аҭыԥ алҵшәа. Уажәраанӡа иҳамоуп Иҟалап знымзар-зны ааԥшуеит. Аоптикатә адрыдрыларақәа. I remember, Аус анызуаз Аҵыхәтәаны еилыркааит Аӡәы уахынла дныҟәон. Адырдырра анырра аиуеит Аиӷьтәрақәа азҿлымҳара Апрограммаркреи Атеориатә акомпьютертә ҭҵаарадырра, избан акәзар уи анаука. There is a solid анаҩс иҟаҵатәу. Атеориатә Ааи.

</details>

---

### 材料合成的深层循环与自主实验室迭代机制

**Liam Fedus**: 没错，这是一个具有极其重大意义的闭环。让我们深入剖析材料探索的具体环节：首先是根据目标性能构思候选材料；紧接着的核心难题在于——如何在现实中把这种目标材料合成出来（synthesize it）？这要求你必须极其深刻地掌握具体工艺参数和严苛的反应条件，其合成难度堪称地狱级别。退一步说，即便完成了合成前两个步骤，制备出了样品，样品表面往往缺乏明确的表征标签，你必须进行极其严谨复杂的结构与物理特性表征，才能确定自己合成出来的究竟是什么物质。

<details>
<summary>Original English</summary>

**Liam Fedus**: зыбжьы дуу Ҿырԥштәыс иаагоуп. ацикл ахәҭак насгьы Маҷк иҵауланы иҭысҵаап лара лтәы. So, as part of аԥҵара. Иара Агәҭынчымрақәа аҟазшьақәа. Ҳара ҳахь иаҭаху аҟазшьақәа. Next—how synthesize it? Ас еиԥш this object? Аригьы Уара иудыруеит аиҿартәышьа закәу аус адулара аҭагылазаашьақәа Даараӡа иуадаҩуп . But then again, Абарҭ анухыркәшалак Ҩ-шьаҿакгьы акы иаԥҵоуп, уи иамаӡам адыргақәа, ус анакәха уара Иаҭахуп ахарактеристика аҭара Узакәыҵәҟьоу еилкаа иҟаҵоуп.

</details>

**Liam Fedus**: 在这种复杂现实情境下，绝不能把强化学习与材料探索当成虚构的黑盒——我们投入一批材料进行物理合成与烧结，等待几天时间，然后通过仪器仔细检测样品是否具备我们所渴望的室温超导特性（room-temperature superconductor）。这绝非一蹴而就的魔法，许多人会好奇地问：难道不能直接在工作站的 GPU 集群上挂机跑上一周算力模拟来解决吗？绝不可能！因为如果没有物理实验提供真实的数据流，单靠数字模拟根本无法收敛出真实的物理规律，分散性（dispersion）与累积误差会彻底吞噬计算结果。每一次现实实验的任务分发与物理合成，都需要借助各类精密自动化工具与机械设备来协同完成。

<details>
<summary>Original English</summary>

**Liam Fedus**: Ус анакәха, уи аҭагылазаашьаҿы, аҭыԥан Азхәыцра аҵаратә ҭагылазаашьа Арӷәӷәара ацны Ҳара акы иазкны Иалаҳгоит Аԥышәара, ҳара ҳазыԥшуп мышқәак рышьҭахь Ҳара ҳҽазаҳшәоит Ирыԥшаазар аилкааразы Ҳара ҳсупермҩангаҩуп ауада temperature or not? Иара зынӡа иҟамло. Сара сҵаар сҭахын. абри атәы. Ааи, ус акәӡам. Уара утәы аанужьыр улшоит Аусуратә GPU мчыбжьык ма убас еиԥш иҟоу акы. Ари хымԥада ҟалашьа амам, избан акәзар Уара узхом Агентцәа Армаҷразы иазхоит dispersion. Аамҭа Адҵара анырхуеит Аиҭныԥсахлара акы еиԥшым аинструментқәа.

</details>

**Ekin Doğuş Çubuk**: 仔细观察真实的物理与化学实验，比如实时监测晶体相变以及各类极端反应条件，过程极其漫长且充满了不可控的物理噪声与宏观变数。因此，我们对待 AI 系统的方式，是将其视为与物理实验环境无缝联结的自主智能代理（AI Agents）——它们深入我们所构建的高质量实验数据流，并置身于由真实物理反馈驱动的强化学习闭环之中。唯有通过与真实物理环境反复对抗与相互印证，AI 模型才能真正学会材料科学的深层直觉，从而推动人类在这一领域取得真正的颠覆性突破。

<details>
<summary>Original English</summary>

**Ekin Doğuş Çubuk**: Уара Уааԥшы. Иҟоуп афизикатә Аԥкра аԥышәарақәа, ҿырԥштәыс иаагозар, аамҭа ишиашо аҟәардәқәа. Убри аҟнытә ари ирацәоуп Ашьшьыҳәа, насгьы мыцхәы абжьы ӷәӷәала. Убри аҟнытә ҳара Апрограмма ҳахәаԥшуеит АИ аԥҵара аҳасабала Агентцәа уи акәша-мыкәша Ҳара иҳамоу адатасет иоуит. And in case Уара уҟазшьа змоу Акәша-мыкәша аԥшаара Аҟынтәи аҵара арӷәӷәарақәа, урҭ Иҟаҵәҟьоу Амла

</details>

<!-- chunk 2/7 -->

### X射线晶体学与多相合成的现实挑战

**Ekin Dogus Cubuk**: 拥有这些数据并且能够有效地将其推导出来吗？我们所做的其实是这样的：我们把X射线照射到材料样品上。X射线在材料内部的原子之间发生散射。这样一来，你就能解析出其晶体结构。同样，理解这背后到底意味着什么至关重要：这就是为什么从我们最初发表的研究工作开始，就专门为此开发了自动化解析系统。过去需要经历大量的尝试和反复摸索。虽然眼前呈现出的数据看似被解析了出来，但再次强调，材料合成中往往同时存在多种共存相（phases present）。如果你稍不注意，就可能把特征错误地归因于不正确的相，或者得出缺乏材料有效性（material validity）的错误结论。利用算法优化和稳定这个解析过程本身就非常具有挑战性。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: To have this data and effectively work it out? What we do is essentially this: we direct X-ray beams onto the material. The X-rays scatter between the atoms. That way, you can deduce and understand the crystal structures. That is also why, from some of our earliest papers, we developed specialized systems for this. A lot of effort and trial went into it. What sits before you is obtained, but again, there are multiple phases present. You might assign peaks to incorrect phases or make claims lacking material validity. Utilizing and optimizing this process is fundamentally demanding.

</details>

**Liam Fedus**: 没错。当元素组合在一起时，你可以将其视为一个根据物理世界状态随时间演进的映射函数。因此，在某个特定日期，你拥有了这些可见的实验观测数据。接着，你可以结合强化学习来构建一个学习环境，在这里你会说：‘好，既然我们有了这个实验数据集，那么，你知道的，下一步科学家应该选择进行哪一项实验，或者我们能从那次实验中获得什么结果？’这同样非常引人入胜，因为它使得我们不必仅仅依赖外部预先编写好的传统计算程序。因为以前的做法往往是模型只记住了特定知识片段，然后你试图让它去匹配模式并给出答案；而现在，你是在为它构建一个能够通过与实验对照来学习任务的环境。

<details>
<summary>Original English</summary>

**Liam Fedus**: Right. As elements come together, you can treat this as an evaluation function over the state of the physical world over time. Thus, you can say: on this date, we had these experimental observables. And you can create learning environments with reinforcement learning, where you say, 'Okay, given this array of experimental data, what is the next step a scientist should choose, or what was the outcome from that experiment?' This is also extremely interesting because it allows us to avoid relying solely on hardcoded external programs. Previously, a model might just recall a memorized chunk of knowledge, and you would try to make it produce an answer. Here, you are structuring tasks through comparison with reality.

</details>

**Liam Fedus**: 这就涉及到了模型的工作与现实实验结果的对比。传统模型只是在生成一个静态答案，由此得出某种推理，但这并不符合真正的科学发现流程。科学并不只是给出一个看似合理的论断就算完成，而是必须形成正确的假说策略，并在真实实验中验证这些策略。如果你的论点无法在全新构建的系统中立足，那么对于实际科研来说就是毫无用处的。但当我们面对真实物理实验时，那些看似简单的假设边界往往会彻底崩溃。

<details>
<summary>Original English</summary>

**Liam Fedus**: This directly relates to evaluating model performance against actual work. A model produces an answer, and people might say, 'Oh, it generated a reasonable conclusion.' But it does not work that way in nature. What is truly required is proposing accurate hypotheses, obtaining the results, and then establishing sound strategies based on whether those hypotheses hold up under empirical weight. Purely theoretical arguments do not survive when tested in entirely new physical systems. Hence, they are useless for what we care about. But when we run real experiments, simplistic boundary assumptions completely break down.

</details>

### 还原论的局限：从狄拉克方程到复杂化学

**Nathan Labenz**: 这引出了一个我一直想请教的问题，尽管我有点担心自己会偏离主题。作为一个非物理学出身的工程师，我常常思考：从根本上说，我们在物理学上不是早就已经把基本规律搞清楚了吗？那么为什么还需要这么费劲？难道我们现在还没有一套完善且终极的物理理论吗？这是一个很好的问题，也是一个非常核心的疑问。很多人会打趣说：‘哈哈，是啊，既然基本定律都有了，你们现在还没解决的问题到底是什么？’也就是说，我们明明在微观层面掌握了基本方程，为什么在复杂材料层面仍然无法直接计算出一切？

<details>
<summary>Original English</summary>

**Nathan Labenz**: This brings up a question, though I am wary of digressing too far from the main topic. As an engineer rather than a physicist, I still wonder: fundamentally, haven't we already figured out the underlying physics? If so, why is this so hard? Could it be that we still lack a complete theoretical framework? It is a great question, and quite fundamental: 'Haha, yes, that is sweet—what is it that we haven't resolved yet?' In other words, if we have the equations, why haven't we definitively conquered materials at scale? Why did we leave so much behind? It is a genuinely great question: we haven't finished it yet, have we?

</details>

**Ekin Dogus Cubuk**: 嗯，关于这一点，科学史上流传着一个非常著名的典故。当保罗·狄拉克（Paul Dirac）奠定非相对论量子力学的基础时，他曾给出过一段著名的论述，仿佛一切基本的物理规律都已经尘埃落定。人们非常喜欢引用狄拉克的那句名言。虽然我不敢百分之百确证原话的每一个字，但大意是狄拉克宣称：‘大部分物理学以及全部化学所必需的底层数学定律已完全明了，剩下的困难只在于这些方程过于复杂而难以求解。’很多人由此开玩笑说：‘剩下的工作全归化学家了。’当时的乐观想法是，既然他能精确求解氢原子的一切性质，那所有问题就应该都能迎刃而解。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: Um, well, there is a famous historical perspective on that. When Dirac formulated quantum mechanics, he made an assertion that seemed to imply that everything essential was essentially done. People love quoting this famous line. I'm honestly not sure how historically precise every nuance is, but Dirac essentially remarked that the underlying physical laws necessary for the mathematical theory of a large part of physics and the whole of chemistry are thus completely known, and the rest is just chemistry. The intuition was that because he could solve the hydrogen atom analytically, everything else would follow.

</details>

**Ekin Dogus Cubuk**: 是的，也许在纸面上确实可以这么说。但实际上，你或许可以求解一个极其简单、孤立的系统，比如一维链状排列的几个氢原子，但我们根本无法从第一性原理精确求解稍微复杂一点的真实体系——比如让氢原子与含氮化合物或者其它多种元素相互作用。物理学家喜欢研究高度对称、没有外在干扰的单原子或极简模型，在真空中计算完美球形对称体系，就像物理学笑话里说的‘真空中的球形奶牛’。可过去一百年的科学进展让我们清醒地认识到，真实世界完全不是那么简单的。仅仅把对氢原子的理解向外推演一步，就极其艰难。而且这绝不仅仅是化学层面的复杂性，它直接触及了物理学本身的深层未解之谜。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: Yes, perhaps in principle. You can solve a very simple toy system, like a 1D chain of hydrogen atoms, but we could not solve realistic, complex interactions—say, binding hydrogen with a nitrogen compound or complex reagents. That is where pure simplicity gives way to messy chemistry. Physicists genuinely love pristine, unadorned, isolated atoms—systems so simple that they can be solved analytically, like the proverbial spherical cow. But what we have learned over the last 100 years is that it is simply not that easy. Expanding beyond our basic understanding of hydrogen proved exceedingly difficult. And this is not merely a matter of chemistry; it represents deep, unsolved physics.

</details>

### 超导之谜与“多者异也”的涌现法则

**Liam Fedus**: 事实上，这里面蕴含着大量的现代物理问题。我想指出的其中一个至今我们仍未能从根本上理解的现象，就是高温超导性（superconductivity）。很多人会问：你们所谓的‘高温’到底有多高？是175开尔文，还是200开尔文？当人们谈论‘高温超导’时，指的往往是非常规超导（unconventional superconductivity）。在常规超导中，电子配对主要是通过晶格振动的声子介导机制来完成的，这可以通过同位素效应（isotope effect）在实验中得到验证——当你改变原子的同位素质量时，超导转变温度会发生可预测的规律性偏移。但在高温非常规超导体中，物理学家至今未能建立起一个普适公认的微观理论。

<details>
<summary>Original English</summary>

**Liam Fedus**: Indeed, there is an enormous amount of genuine physics here. To give you one clear example that we still do not fundamentally understand today: superconductivity. And when you ask what 'high temperature' means to people—is it 175 Kelvin, 200 Kelvin? When we say 'high-temperature superconductivity', we are often discussing unconventional superconductivity. In conventional superconductors, pairing is predominantly phonon-mediated. In those cases, you observe the isotope effect: as you substitute different atomic masses, you observe a direct shift in critical temperature. But in unconventional superconductors, they do not obey these standard rules, and physicists still lack a unified, predictive theory.

</details>

**Liam Fedus**: 不仅如此，我们根本无法确信我们掌握了预测非常规超导体的理论工具。现有理论在解释某些特定效应时或许有用，但面对复杂强关联体系时却常常束手无策。我们需要在真实物理世界中去探寻答案。这就是为什么把人工智能与实验理论相结合来进行材料发现显得如此关键。人们常常忽略了自然界的一个核心规律，正如诺贝尔物理学奖得主菲利普·安德森（Philip Anderson）在那篇著名的论文中所写道的那样：‘多者异也’（More is Different）。

<details>
<summary>Original English</summary>

**Liam Fedus**: Furthermore, we cannot reliably predict new superconductors. And superconductivity is just one prominent example among many phenomena we don't understand. We have partial theories, but there are countless systems where theoretical tools fail to capture many-body interactions. What I mean is that there are so many collective effects we urgently need to find out. This is why applying AI in conjunction with theory to explore discovery is vital. People often wonder what creation truly entails. There is that famous quote from Phil Anderson: 'More is different.' It means that even if you understand the fundamental microscopic laws governing individual elements, when you assemble many of them together, they behave in fundamentally novel ways that could not have been deduced by simple reductionism.

</details>

**Liam Fedus**: 安德森的核心洞见在于：哪怕你把支配单个组分的微观基本定律研究得一清二楚，一旦你将大量相互作用的元素组合在一起，系统的集体行为就会展现出全新的、质的飞跃。基本定律本身可能是简洁明了的，但多体系统的集体行为却异常复杂，以至于仅凭理论推演几乎无法进行全局仿真。这就是‘涌现’（emergence）与‘普适性’（universality）的力量，它奇妙而深邃。这也正是深度学习模型在模拟复杂多体物理系统时表现出惊人潜力的原因：我们在所有深度模型中看到的大尺度通用能力，恰恰呼应了复杂物理系统中的涌现现象。

<details>
<summary>Original English</summary>

**Liam Fedus**: Anderson's point was that understanding the elementary microscopic laws is one thing, but when you add diverse elements together, their collective behavior behaves in fundamentally distinct ways that simple reductionist physics cannot trivially extrapolate. How do you understand the behavior of vast numbers of interacting entities? Individual laws look straightforward, but collective behavior is extraordinarily difficult to compute or compare directly. That is emergence and universality; it is truly remarkable. That is also why deep learning models are so fascinating here. We observe power laws and universal behavior across deep architectures, mirroring the emergence and versatility we find in physical systems. A lot of theoretical physics focuses precisely on where emergence originates.

</details>

### 材料逆向工程与‘材料界的台积电’构想

**Nathan Labenz**: 确实如此。在理论物理领域，关于涌现和复杂系统的探讨浩如烟海。但如果我们从实际的材料工程目标出发——假设你希望获得具有某种特定宏观性能的新材料，你不仅需要设计它，还需要知道如何在物理上合成它。从理想状态下完全逆向工程（reverse-engineer）任意给定性质的材料，到现实中往往只能通过大量繁琐的经验试错，这两者之间究竟有多大差距？将已知数据转化为可以直接生产的合成配方，真的有可行路径吗？

<details>
<summary>Original English</summary>

**Nathan Labenz**: Certainly. There is a vast body of theoretical literature examining emergence. But turning to the engineering outcome: suppose you want to ensure specific physical properties in a target material. You try to synthesize it, and then you need to figure out how to actually arrive at that desired state. Is that feasible? Can you reverse-engineer arbitrary target states? Does that have practical validity? What often happens is that after endless trials, researchers still don't know precisely what transpired. I think there is a huge gap between attempting to reverse-engineer everything and iteratively improving real material properties.

</details>

**Liam Fedus**: 我认为通往这个目标的路径是存在的。我们之所以难以做到对所有材料进行理想化的逆向工程，是因为材料合成既涉及热力学平衡，又涉及复杂的动力学竞争。在这两者的复杂博弈中，我们常常需要剥离大量干扰因素。好的，试想一下：你从过往的学术论文或者数据库中提取了大量已知数据，但当你尝试进入实验室去重复并制造它们时，你是否能百分之百成功？这就像在探寻一种全新的工业制造范式。我之所以经常思考这个问题，是因为这关乎一家科技公司的长远定位。

<details>
<summary>Original English</summary>

**Liam Fedus**: I believe there is. The reason we struggle to cleanly reverse-engineer everything is that material synthesis is an intricate competition between thermodynamics and kinetic pathways. In sorting through those coupled processes, we also have to eliminate endless confounders. Okay, consider this: given all the prior publications and literature data, can you actually replicate those findings when entering a real synthesis workflow? Is it a predictable process or sheer trial-and-error? The reason I frame it this way is that it shapes how we conceptualize the entire enterprise.

</details>

**Liam Fedus**: 大家都很清楚台积电（TSMC）在半导体领域的定位：它是一家代工厂（foundry），专门负责制造极其精密的半导体芯片，而设计这些芯片的往往是外部设计公司。但台积电之所以拥有不可替代的护城河，是因为它掌握了世界上最顶尖、最可靠的物理制造与工艺流程。我们完全可以把同样的理念引入到先进材料领域：建立一个‘材料界的台积电’。人们来到这里，提出他们想要的材料功能与性质需求，而我们的系统则深入理解底层合成动力学，将其转化为高通量物理制造流程，就像一个物理世界的编译器一样。这听起来有点像《星际迷航》中的复制机，但它正通过自动化实验室与AI的结合逐步变为现实。

<details>
<summary>Original English</summary>

**Liam Fedus**: Think about TSMC: TSMC is the premier fabrication foundry for semiconductors, though they don't necessarily design the end-user products themselves. Yet everyone relies on TSMC because they master the intricate, high-yield manufacturing processes. You could imagine becoming the TSMC for materials. Customers and scientists come in with specifications for the properties they desire, and our platform understands the synthesis process and compiles the exact chemical and thermal recipes. It functions like a compiler for the physical world—much like a replicator in Star Trek. That is the long-term vision we are building toward.

</details>

**Nathan Labenz**: 如果我们要满足这种宏观层面的苛刻要求，让AI在浩瀚的原子排布与合成路径中进行搜索，这是否是一个寻找正确构型与相图配置的优化问题？这里面存在明确的目标函数（objective function）吗？还是说物理现实比这要复杂得多？

<details>
<summary>Original English</summary>

**Nathan Labenz**: If we consider those requirements, is this essentially an optimization problem over crystal configurations and phase space? Is there a well-defined objective function that you can simply plug into an optimizer, or is the reality far more open-ended?

</details>

**Liam Fedus**: 不，据我所知，这远非一个单一的目标函数所能涵盖。真实物理世界的复杂性要大得多。当人们在谈论通用超级智能（superintelligence）时，往往只关注数字世界；但我们所追求的超级智能，必须能够在物理世界的尺度上拥有敏锐的感知、推理和执行力，必须直面大自然的所有非线性和意外情况。

<details>
<summary>Original English</summary>

**Liam Fedus**: No, from what I've seen, it cannot be reduced to a single objective function. It is vastly larger and more nuanced than that. When people discuss superintelligence, they often restrict their imagination to purely digital domains. But true synthesis superintelligence must meet the physical world eye-to-eye, confronting nature's nonlinearities and unexpected phenomena directly.

</details>

### 相变物理学与X射线衍射图谱的现实解析

**Nathan Labenz**: 回到刚才提到的多相共存（phases）。你能展开讲讲相变在材料科学中的意义吗？我理解这与涌现现象有着密切的联系，而且它似乎也是实验室中识别新材料的关键信号。

<details>
<summary>Original English</summary>

**Nathan Labenz**: Circling back to what you mentioned about phases: could you elaborate a bit more on phases and phase transitions? In my mind, that links directly to emergence, and it serves as a crucial physical signal for identifying novel phenomena.

</details>

**Ekin Dogus Cubuk**: 是的，相变是非常迷人的物理现象。对大多数普通人来说，最直观的例子就是烧开水：当你不断给冰加热，冰会融化成水；继续加热到临界点，水会剧烈沸腾变成水蒸气。这代表着系统从一种凝聚态物理相剧烈跃迁到另一种相。在理论物理和计算机科学中，著名的伊辛模型（Ising model）也是研究相变的经典范例：在自旋系统中，相邻自旋倾向于同向排列（朝上或朝下），在不同温度下，系统会从无序状态自发组织成有序铁磁态。相变使物理学家能够清晰地观测宏观性质如何在微观连续变化下发生突变。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: Yes, phase transitions are profoundly captivating. For most people, the classic mental model is boiling water: you apply heat to ice, it melts into water, and at the boiling threshold, it transforms into steam—a stark transition between distinct physical phases. Another quintessential example widely known across physics and computer science is the Ising model. Spins can be oriented up or down, and as temperature changes, they abruptly self-organize from randomness into correlated order. Phase transitions provide a rigorous framework for physicists to investigate emergent phenomena.

</details>

**Ekin Dogus Cubuk**: 在实验材料学中，我们同样通过改变温度、施加压力或引入不同反应前驱体来诱发反应，促使原子重新排列并形成全新的晶体结构。在这个过程中，X射线衍射（XRD）就成了我们的‘眼睛’。因为当材料内部的原子几何排列发生改变时，X射线衍射的衍射峰位和强度也会随之剧烈改变。但在真实的固相合成实验中，实际情况远比理论复杂：当你第一次尝试合成某种目标材料时，结果从来不是简单的‘成功’或‘失败’（是或否），在反应炉里取出来的产物往往是极其复杂的混合相。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: In materials synthesis, we similarly vary temperature or introduce reactive conditions to trigger reactions. The atoms begin reacting and organizing into novel crystal structures. This is directly reflected in the X-ray diffraction patterns: because the atomic geometry has changed, the diffraction peaks shift dramatically. But in practical, real-world materials discovery, when you run an experiment for the first time, the outcome is never a clean binary 'yes' or 'no'. What you obtain is an extremely messy mixture of coexisting phases.

</details>

**Ekin Dogus Cubuk**: 在这个混合相样品中，可能只有极少量的目标产物，或者生成了某种意想不到的二维晶体（2D crystal），而绝大部分则是完全不需要的副产物。传统的物理仿真软件在这里很难精确还原这种复杂的非平衡态动力学。这就需要我们的材料智能系统能够看懂复杂的XRD图谱，并敏锐地判断：‘虽然大部分是杂质，但这里出现了一个微弱的新相特征，让我们调整温度和烧结时间再试一次。’这就是为什么将自动化物理实验与AI闭环连接起来能够产生真正的突破——它不仅替代了人工查阅XRD图谱的耗时过程，更赋予了机器在真实物理世界中自我迭代的科学直觉。

<details>
<summary>Original English</summary>

**Ekin Dogus Cubuk**: Within that intermediate mixture, you might have tiny traces of the desired phase, or unexpected 2D crystals, along with various precursor phases that you never intended to make. This complexity makes standard simulations inadequate, which is why having an automated physical lab connected to AI is indispensable. A materials scientist or an AI system looking at the XRD can say: 'Wait, there is an interesting trace here; that might not be the primary phase, but let's alter the synthesis parameters and run another cycle.' For our listeners: XRD stands for X-ray diffraction, which illuminates atomic structure. And that is where the real breakthroughs in discovering novel physical phases happen.

</details>

<!-- chunk 3/7 -->

### 相变观察与实验可重复性困境

**Speaker A**: 在任何地方都无法直接观察到相变的确定性边界。它并不会显现出来。这里存在着物理材料层面的某种固有复杂性。利用现有的这些手段，我们正在经历一个不可思议且至关重要的科学探索过程。因为如果去审视这些“存在”与“不存在”的临界状态，就会发现它完全属于疑难复杂问题的范畴。回头来看，你是否能够做出一个完全明确且毫无歧义（unambiguous）的判断？在此处，往往存在着多种截然不同的解释（interpretations）。事实就是如此。难道这不是理所当然的逻辑吗？面对这样一个全新的相态，究竟是什么在困扰着你？

<details>
<summary>Original English</summary>

**Speaker A**: џьаргьы иҟам афаза азгәаҭара. Лара дыҟаӡам. амаҭәашьартә ҟәыӷара иамоуп Абарҭ шәхы иашәырхәа Уамашәа иубаша акрызҵазкуа аҭҵаарадырратә процесс, избан акәзар арҭ Иҟоуи иҟамзи . ацәгьарақәа рахь иаҵанакуеит ахәаԥшра. Ахынҳәра Уара уоума аҟаҵара Иазгәаҭаз unambiguous. Абра interpretations. Ус ауп. ? Абри ауп логикас иҟоу афаза ҿыц, убри аҟнытә ари Угәы иҵхозеи?
</details>

**Speaker B**: 依我来看，不确定性始终存在。归根结底，核心问题在于实验的可重复性（replication）。有人可能会问，我们为什么要大费周章去进行实验复现？但我的观点是，这极其困难。整个过程绝非完全确定的（deterministic），不仅如此，还伴随着大量未明确的杂相以及其他物质因素。两种不同的相态甚至可能给出相似的表征图谱，无法得出唯一的定论。因此我认为，单纯依靠现有的系统和化学直觉是远远不够的。在诸多现实条件的限制下，消除这些歧义与无意义的假象极其棘手。既然如此，如果进入到这个领域，你究竟在期待什么？

<details>
<summary>Original English</summary>

**Speaker B**: Изхысҳәаауа, Иаанхоит ақәымгәыӷра. Нас, Аус злоу арепликациа ауп. Ҳәарас иаҭахузеи, ҳара имҩаԥаҳгоит арепликациа. Аха мап, сара Сгәанала, уи уадаҩуп. Уи нагӡаӡам адетерминисттә, иара убас иҟоуп, ибзиоуп, ԥыҭҩык Еилкаамкәа аҟазаара уҳәа убас иҵегьы амаҭәақәа. Еиуеиԥшым ҩ-фазак Аиашаз илшом акы аҭак аҟаҵара насгьы еиԥшу ахсаала. Убри аҟнытә сара сгәанала асистема даара акраҵанакуеит ахрахәара ахимиатә интуициа Даараӡа иҟалон Аҭагылазаашьақәа ҳасаб рзуны Ацхыраара аныхра аҵакыдара. Ус анакәха, шәара џьара Уҭал арахь Убри инамаданы, Уззыԥшузеи?
</details>

### 多模态表征与数据先验因子的引入

**Speaker A**: 是的，在我看来，热力学规律难道不是最核心的根本吗？与此同时，先验因子（a priori factor）也起到了决定性的作用。目前它在材料表征方面提供了极大的帮助。我们可以借助 X 射线衍射（XRD）技术，结合电学性能测试，以及电子显微镜（electron microscopy）进行观测和尺寸测量。这些手段确实带来了实质性的帮助（really helps）。计算能力的引入同样关键。但如果让十个人来面对同一个普遍性问题，要给出一个统一的判断依然有点困难（a little difficult）。处理这些计算需要更高的智能水平，甚至如同超级智能一般。它能够指出混淆与冲突的根源所在。长期以来，处理器都在机械地消化数据，但这仅仅是整个数据集的一部分（part of the data）。

<details>
<summary>Original English</summary>

**Speaker A**: Ааи, сгәанала... Атермодинамика Зегь реиҳа ихадоу ииашам? Убасгьы акраҵанакуеит a priori factor. Макьаназы Уи акыр иацхраауеит, ус ауп аҟазшьарба аматериалқәа. Ҳара иҳалшоит анапхгара Арентгентә адифракциа (XRD), уҳәа убас, Ҳаргьы иҳалшоит Афымцатә шәага аҟазшьақәа. Ҳара Аелектронтә microscopy. Нас ашәарақәа. Убас really helps. ИАРА УБАС Аҳасабратә амч. Убри аҟнытә Ауаҩы 10 еиуеиԥшым ииҭа Еицырзеиԥшу азҵаара ақәыргылара a little difficult. Аха азы еиҳау аҟәыӷара аҭахуп. Суперинтеллект еиԥшуп, аҳасабрақәа. Иара илшоит Ҳахьнанагоит аилаӡара Акыр аамҭа уи аҭыԥан Ирҳәоижьҭеи акрааҵуеит избан акәзар адатақәа ус баша апроцессор. Убри аҟнытә part of the data.
</details>

**Speaker B**: 不仅如此，由于存在多种不同的测量路径，如果其中某一项数据是错误的该怎么办（Because what if one of is wrong?）？当面对这种矛盾时，你该如何决定采取什么行动（How do you decide what to do?）？作为一名专业研究人员（As a specialist），你如何确立真相？如果仅仅盲目相信模型，认为自己的模型能够研究并解释一切，那是不切实际的。我甚至不知道自己正在面对什么，人们往往只是盲目地敬畏机器。正因如此，我们才不得不对数据持怀疑与回避态度。

<details>
<summary>Original English</summary>

**Speaker B**: Уи адагьы Еиуеиԥшым амҩақәа Акы еиԥшны ашәара иҵабыргыҵәҟьаны. Because what if one of is wrong? Ус анакәха, ианба Уара иуцәугоит ари адата ? How do you decide what аҟаҵара? As a specialist аиаша? Нас сара ус баша, иудыруама, Сара смодельуп, зегьы ҭысҵаауеит. Сара Сзакәу сыздыруам. Издыруам, насгьы сара Машьынак сыршәуеит. Ааи, ааи. Убри аҟнытә ҳара ҳара адатақәа ҳрыцәцоит.
</details>

### 上帝视角、AI 代理与麦克斯韦妖假想

**Speaker A**: 在我看来，我们理想中希望拥有一种具备全知视角的上帝能力，使计算机能够洞悉超越人类认知极限的信息，观察到所有的原子（all atoms）。为了实现这一点，必须保存并处理所有数据，而不是像现在这样受到权限与通道的制约。遗憾的是，我们至今收集的数据依然残缺不全，未曾真正触及全部核心信息。在人工智能和模型的探索方向上（model, right?），人们总设想这个模型掌握了所有这些数据（has all this data），宛如上帝掌握一切信息比特那样。但当前的传统智能代理所能重构和接触到的，实际上仅仅只是极小的一个数据子集（subset of data），或者说有限的片段。

<details>
<summary>Original English</summary>

**Speaker A**: Ум, сара Сгәанала, иҟалап исымазар акәхарын ҵакыс иамоу Анцәа дихәаԥшуан. Еиҳахон ауаа раасҭа адыррақәа ҭанагалар алшоит акомпиутер. Рыцҳарас иҟалаз, ҳара, Ахәаԥшра all atoms. Убри азы Еиқәырхатәуп, ҳара Усҵәҟьа иҳахәҭам анеирҭа. Рыцҳарас иҟалаз, ҳара уажәгьы ҳаҟоуп Иарбан дыррақәоу еизгоу акгьы ҳԥыхӡом. АИ аганахь ала аҽаԥшьгара, —уи, ум, уазхәыцроуп аҭҵаара, ианба еиԥш model, right? Ари амодель has all this data. Убри азын, Анцәа зегьы имоуп. абитқәа ма убас еиԥш иҟоу акы адәылҵырҭа. Убри азоуп уара аинформациа. Уажәы Ари традициатәуп агент- урҭ рҟынтәи аиҭашьақәыргылара ииашаҵәҟьаны Иҟалоит уи иалагӡаны. subset of data. Мамзаргьы абарҭ зегьы.
</details>

**Speaker B**: 是的，早在 19 世纪，人们就在思考系统的熵增规律。当时曾提出过一个著名的思想实验：如果存在一个能够观察每个微观粒子的智能体——正如麦克斯韦妖（Maxwell's demon）那样——去逆转熵增过程，情况会怎样？在我看来，你提出的关于未来的长远展望，就类似于我们要保护和利用如此庞大的微观信息，必须去打破某种常规的限制。毫无疑问，我想表达的正是一种宏观与微观兼顾的全局视野。这让我联想到空调与制冷系统的工作机制，因为它正是这样运行的。但我认为，“这究竟意味着什么”的追问绝非空穴来风：面对世界上所有的这些分子与原子，如果不加节制地倾倒所有参数，而是逐一进行精确测量与控制，我们究竟该如何做到？

<details>
<summary>Original English</summary>

**Speaker B**: Ааи. зааӡа. Сара ииашаҵәҟьаны Ааи, иудыруама, 1800-тәи ашықәсқәа рзы асистема аентропиа иамоуп Иҟан ус ахаҿы иаагаз Аԥышәара: иҟалазеи Ахәаԥшра еснагь ус ҟасҵон, асистема аентропиа, уи Аамҭа ыҟамызт ҳәа сгәы иаанагоит. ҟалоит. Аха аргумент ақәыргылатәуп Аныхра ентропиа аизҳара. Ус анакәха, макьана ҳахьымӡацгьы Убас иаҟароуп Максвелл иџьныш ала, сара Сгәанала, уара утәы Азҵаара даара хара иԥшуа иазкны ԥхьаҟатәи аамҭа, ҳара ҳахь Ҳара иҳахьчап убриаҟара адыррақәа рацәоуп, ҳара Ҳаиԥырҵыр акәхоит аԥыргара. Ааи, мап, ҳәарада, мап. Сара исҳәарц исҭахыз абри аҩыза акәын амҽхакрбага. Ари исгәаланаршәоит Аус сымоуп. аҳауархьшәашәага, избан акәзар Убасҵәҟьа ауп ишус ауеи. Аха саргьы сгәы иаанагоит "Изакәызеи" азҵаарақәа Амала иааумхәан адунеи аҿы иҟоу адаԥаҩқәа зегьы Зегьы мыцхәы иумырҭәын ахархәагақәа, акәымкәа Еишьҭагыланы зегьы рықәҭыхра ". Ишԥаҟаҳҵо уи?
</details>

### 分布式协作与虚拟会议的局限

**Speaker A**: 确实如此，完全同意。这正是我所考虑的核心问题。要在单个原子的层面上增强可视度与观测精度，目前几乎是不可能的；但如果需要，我们正试图引入更强大的隐藏变量与分析手段。此外，关于协作方式和地理分布的问题：你对加利福尼亚有兴趣吗？还是尼泊尔或者澳大利亚？我们原本有着宏大的国际合作计划，希望能更加开放。然而你当前所处的物理位置和环境成本构成了巨大的限制。就像我们现在这样，通过远程资源进行交流——当前我们正在使用 Zoom 会议系统（This is Zoom），你的物理位置依然会产生直接的影响。

<details>
<summary>Original English</summary>

**Speaker A**: Ииашоуп. Ибзиоуп, ааи. Ибзиоуп, ааи. Ааи, ааи. Ииашоуп. ИБЗИОУП. Ааи, ус сгәы иаанагоит. Ишԥа ҳәа азҵаара Ааи, ус ауп. Уара Алаԥшра аизырҳара хаз-хазы атомқәа Иҟамло, аха ҳара ҳара иацаҳҵоит идуӡӡоу иҵәаху аԥсахгақәа, уҭахызар. Ааи. Ааи, насгьы аинтересқәа: Угәы иҵхо уара Калифорниа? Ибҭахӡами? Непал ма Австралиа ? Ааи, иҳалшон. Уи ыҟоуп Апланқәа ҳамоуп Еиҳаны иаарттәуп Уара умҩақәҵоуп, уахьыҟоугьы ахә. Ааи? Like here, we have Ҳара даара иаҳгәаԥхо уантәи, ҳресурсқәа . Уара ишуҳәаз еиԥш, аиԥшымрақәа ыҟазар ауеит This is Zoom. Сара исымоуп Уахьыҟоу анырра анаҭоит уара. Ааи.
</details>

**Speaker B**: 是的，我对此深有体会。实验室是不可替代的实体环境，其实体资源、实验条件和材料样本都受制于物理边界。计算工具与理论方法（Or how）固然能从高层抽象（high level）的角度提供全局洞察，但这两者究竟该如何真正结合？坦率地说，运行计算模拟固然相对简单直接，但若论及真实准确性，实验测量才是真正的基准。真实实验反映的是无可辩驳的客观事实。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи, исымоуп. алабораториа. даҽакы. Убас иҟоу амазаара хымԥадатәиуп алабораториақәа рҳәаа, иара убас аԥышәа мамзаргьы, иаҳҳәап, аматериалқәа. Иҟоуп Еиуеиԥшым аԥкрақәа. Иаҳҳәап, сара сзызҿлымҳауп, Аҳасабратә аинструментқәа? Or how Аҳасабратә Аԥышәарагьы ус акәӡам Хымԥада еиқәшәоит. Hmm, ah насгьы атеориа аҟынтә Аилкааратә хәаԥшышьа high level. Убас, Ишԥаҟало уи зегьы? ҳаицны? Иҟоуп еиҳа имариоугьы еиҳа ииашаны иуҳәозар, анагӡара асимуляциақәа, аха иҟоуп акы, Еиҳа имариоу, еиҳа ииашаоу аԥышәа. Аԥышәарақәа еиҳа ииашоуп иҟамлаз версиа, насгьы амш.
</details>

### 科恩-沈方程、密度泛函理论与能量凸包

**Speaker A**: 让我举例说明（Um, let me）。回到材料性质的量子力学本质，沃尔特·科恩（Walter Kohn）与沈吕九（Lu Jeu Sham）创立的科恩-沈方程，为这一领域赢得了诺贝尔奖。他们揭示了如何将极其复杂的量子多体相互作用系统简化为电子密度问题。面对庞大的原子体系与构型空间，必须考虑电子密度分布。后退一步来看，因为不同材料的所有性质并非完全孤立。量子力学计算能够让我们逼近并掌握材料的本质特性，而这正是我们筛选材料时所积极利用的工具。具体到这种材料（That is, according to this material?）：如果其形成能高于其他原子组合，它在热力学上就是不稳定的，无法稳定合成。因此所谓的稳定性，在能量凸包（convex hull）图像上表现为低于其他竞争相的能量面。

<details>
<summary>Original English</summary>

**Speaker A**: Um, let me. аҿырԥштәқәа. Ус анакәха, акы ааҭгылара. Иулшома Ииашоуп. Ааи. — ари зегь реиҳа иҟалап ахархәара аматериалқәа. Лара Кәына-Шема, уи азы Кон априз. Уи еиликааит, Изакәызеи акванттә механика Зегьы рзы аҭыԥ Убри аҟнытә, иаҭахуп системақәа. Аҽи акосмос. Уи зегьы Уазхәыцроуп аҵарҭыша аҭаҭынра иазкны, системақәа. Ус анакәха, абри даара имариоуп. Шьҭахьҟа, Еилылкаап ҳәа сгәы иаанагоит. избанзар зегьы аҟазшьақәа зеиԥш ыҟам. Избанзар Астатиа иатәушәа збоит аҳасабра Аквант азааигәатәра Амеханикатә аҟазшьақәа аматериалқәа. ИАРА УБАС Активла Ҳара ари ҳхы иаҳархәоит аматериал. That is, according to this material? Азы ари аенергиа еиҳазар, Егьырҭ раасҭа урҭ атомқәа, уи ҟалашьа амам аԥҵара рылшоит. Убри аҟнытә аҭышәынтәалара уи иаанаго Аконвекс иқәуп Егьырҭ рцәаҩа аматериалқәеи урҭ аенергиақәа. Ҳм, уи аума?
</details>

**Speaker B**: 这一点显而易见。在实际评估中，我们需要在指数级增长的体系规模与可承受的计算代价之间取得平衡，这就需要建立逼近算法并容忍一定的误差范围。为了以一定的计算成本（for a certain price）换取效率，我们必须付出妥协。希瑟·库里克（Heather Kulik）教授的研究也多次指出，虽然完全精确的解析解目前并不存在，我们并没有完全掌握真实的基准（We don't really know）。因此在实际计算中，密度泛函理论（DFT）普遍依赖各种近似泛函（approximation）。科恩-沈定理表明电子密度决定基态性质，但我们无法精确获知动能泛函（kinetic energy functional）的具体形式，也没有完美无瑕的理想 DFT 计算机。最终在数值计算中，我们只能依赖各种近似展开。

<details>
<summary>Original English</summary>

**Speaker B**: Еилкаауп, иаԥсоума ҳара ҳахь... Изхысҳәаауа, иҟалап Еиҳа имариоу, азеиԥш алкаа. Убри азын, ашәпара — абри ауп амҩа Иҟоу акы агара Аекспоненциалтә мамзаргьы асистема ашәагаа, насгьы ирмаҷтәуп иааигәаны , гхак аманы, аҩаӡара. Um, so, аҵакқәа рыԥхьаӡара, for a certain price. Ҳәарада, Уи зегь рыла иманшәалоуп, ҳара иҟаҳҵомызт Ари бзиахар алшоит. ахҭыс. Heather Kulik ҳәаақәҵарала, аха иара убасгьы Адыррақәа ыҟаӡам . We don't really Ҳара иаадыруеит урҭ зеиԥшроу , насгьы DFT зегь рыла ҳара Yes, I think so. Сара Иҟазароуп approximation. Атеорема Кәына-Шема иаанарԥшуеит Анеирҭа . And for models, шьаҭас иҟаҵаны аҵарҭыша аҵарра, ҳара иҟаҳҵаӡом Афункционалра kinetic energy. ИАРА УБАС Ҳара иҳамам идеалтәу ДФТ акомпиутер. абри аамҭазы. Аҳасабратә аҵыхәтәан, уара иулшоит зегь раԥхьаӡа иргыланы аԥхьаӡара. Имарианы
</details>

### 生成模型、变分自编码器与 AI 驱动的材料发现

**Speaker A**: 是的，直到处理更大尺度前，这种计算开销是必须承受的。我想补充说明一点，我早年从事金融领域的量化计算，当时我们受制于单核算力（single core）。从统计与分布的角度来看，当前的变分自编码器（VAE）在数学理念上与之非常契合，都是将复杂高维数据投影到潜空间参数上。但 VAE 涉及到标准差分布，例如一倍标准差（sigma, one sigma）的不确定度度量。计算开销虽然高昂，但这提供了一种极为出色的泛化能力。诚然，单凭我个人无法断言哪种方法绝对最好，但对于预测新型稳定材料而言，这无疑比传统手段优秀得多。

<details>
<summary>Original English</summary>

**Speaker A**: Ааи. Ааи, ааи. But until n- Уара иулшоит иулшоит Сара згәаҭарак ҟасҵоит. , издыруам уара иуҭаху Ари аиҿцәажәара акәу, мамзаргьы? . I came from афинансқәа. Ҳара иҳаман single core. Ари даара доуҳала ВАЕ у еиԥшуп Абарҭқәа аӡәы заҵәык иахь параметр. Издыруама сара стәы. But VAE is sigma, one sigma. Аха Абжьы еиԥшума? Ааи, ааи, ашәпара афаил Макьана иазхоит ахарџь идуӡӡоуп. Ааи. Ииашоу. Уара ухәыҷуп Азеиԥштәра, аха ари даара ибзиоуп. Иара, ииашаҵәҟьаны, Зегь реиҳа ихадоу аамҭа . Акы. Хаҭала сара исыздыруам. зегьы иреиӷьу аметод Апрогнозҟаҵара Аҿыц аҭышәынтәалара аматериал. Иара хымԥада Иидеалтәым, аха Ҳәарада, еиӷьуп даҽа методқәак Исгәалашәоит.
</details>

**Speaker B**: 回顾这些已有手段，在某些特定场景下进行对比确实十分方便，但单纯依靠纯模拟往往难以独立支撑突破。如今，在模拟流水线中融入人工智能（AI）并与实验紧密结合，使得发现周期比以往任何时候都要快得多。相比于在传统实体实验室（laboratories）中进行漫长低效的试错，通过数据驱动与生成模型来发掘新材料要高效得多。以事实和实验数据为基石，结合强大的预测模型，你当前最关注的核心方向正是这个，对吗？好的，让我们继续深入探讨。

<details>
<summary>Original English</summary>

**Speaker B**: Убас, Ахынҳәра урҭ зҳамоу ҳхы иаҳархәоит, Усқәак еиҳа имариоуп аиҿырԥшра аасҭа Урҭ бзиоуп акы. Нас ҳара Ҳара иҳалшоит ари дара рхаҭақәа мацара Асимуляциақәа ахаангьы аха асимуляциатә цәаҳәаҿы , АИ и аекспериментқәа, ԥаса аасҭа еиҳа ирласны. Акы убри акырӡа еиҳа ирласны. Сара исымоуп Еиҳа имариоуп ҿыцқәа раартра аасҭа laboratories. Шәшԥаҟоу? Убас ала шәмодельқәа ииашоу афакт ала Иарбан уара узҿлымҳау? Ибзиоуп,
</details>

<!-- chunk 4/7 -->

### 材料计算与实验室实验的校准循环

**Speaker A**: 我们拥有计算实验室，在现代材料科学中，你可以通过计算每天运行成百上千乃至上万次模拟。但你真的能完全脱离实体实验吗？我不这么认为。那么，在今天我们究竟还能做到什么？这是真的可以全靠纯模拟吗？

<details>
<summary>Original English</summary>

**Speaker A**: We have computation and we also have the laboratory. In modern computational materials science, you can do hundreds or thousands of calculations a day. But can you really do without physical experiments? I don't know about that. And can you really rely purely on simulation today, honestly?

</details>

**Speaker B**: 对，这就是我想说明的关键。单纯依靠计算在过去从来都无法完全解决问题。真正的情况是，仅靠密度泛函理论（DFT）等计算方法，往往无法直接准确预测所有材料性质。哪怕运行几百万次计算，仅凭这些算力数据也是远远不够的。因此，我们必须正视现实：单纯依赖模拟是不行的。所以，这里真正的做法是，必须让计算与实验室里实际完成的物理实验紧密结合。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, that is exactly what I want to say. Pure computation has never been able to do it all alone. In reality, relying solely on DFT calculations fails to capture the true material properties. Even running millions of calculations is not enough. Therefore, we cannot rely solely on simulation. So what really happens is that calculations must be grounded in what is actually carried out in physical laboratories.

</details>

**Speaker A**: 人们现在也在讨论大语言模型（LLM）与材料模拟的结合。这是一种混合架构吗？

<details>
<summary>Original English</summary>

**Speaker A**: People are also doing this with LLMs now. Is this a hybrid approach?

</details>

**Speaker B**: 这确实往往是一种混合系统。以长期推进的材料基因组计划（Materials Project）为例，它拥有最顶尖且开源的 DFT 数据库。但实际的科研工作流程是将实验数据与 DFT 相互配合，利用实验基准数据来校准 DFT 模拟。在我们公司内部也是如此：每当我们对某类特定化学性质或材料系统感兴趣时，我们都会在实验室中进行实际的物理实验，并使用实验结果来校准我们的计算模型。

<details>
<summary>Original English</summary>

**Speaker B**: It turns out to be a hybrid. Take, for example, the long-standing Materials Project, which provides the best open-source DFT databases. In practice, experimental data is used alongside DFT to calibrate the simulations. That is exactly what we do inside our company. When we are interested in a specific chemical property or system, we run experimental tests and use that empirical data to calibrate the models.

</details>

### 生物系统与无机晶体材料的复杂度差异

**Speaker B**: 这就引出了另一个非常关键的对比点。我曾和许多生物学家朋友深入交流过，当他们听说我们在材料科学中所做的事情时，总是感到非常惊讶。他们会问：“在材料科学中，难道你们不能直接看清楚到底发生了什么吗？”因为在结构生物学领域，研究人员可以观察蛋白质折叠结构，并通过 X 射线晶体学衍射（XRD）在埃（angstrom）级的精度上精确重构出分子的三维原子排布。

<details>
<summary>Original English</summary>

**Speaker B**: This is another point. I have talked to many biologist friends, and they are always deeply surprised when we discuss how materials science works. They say: "In materials science, can't you just determine what is happening directly?" Because in biology, you can look at protein structures and reconstruct them down to the exact angstrom level using X-ray diffraction (XRD).

</details>

**Speaker A**: 那么无机材料与生物系统在 X 射线衍射表征上的区别究竟在哪里？在处理生物大分子时，我们会因为投影视角的丢失而损失信息吗？

<details>
<summary>Original English</summary>

**Speaker A**: So where is the difference in X-ray diffraction between materials and biology? What information do we lose, and is that due to projection losses? It is hard not to wonder about that question.

</details>

**Speaker B**: 难道不是这样吗？如果换一种方式来理解，生物大分子的柯尔莫哥洛夫复杂度（Kolmogorov complexity）在某种意义上其实是相对较低的。你可以说生物大分子的序列就像是能够被直接“编译”的代码，具有高度的一致性与规则性。当然，我不是生物学家，不敢断言生物学的一切细节。但在三维超导体或无机材料中，情况完全不同。人们从来无法简单地用一个单一模型来表征这些复杂相态，比如多元非均质晶体，其生长机制和内部形态错综复杂，就像交织的金属键网络。

<details>
<summary>Original English</summary>

**Speaker B**: But isn't it? If you look at it from another angle, does biology have a lower Kolmogorov complexity in that sense? As we often say, you can think of it as something that can compile along a deterministic sequence. Most people would agree—though I am not a biologist, so I am cautious here. But with 3D superconductors, diamonds, and inorganic crystals, it is completely different. People have never been able to represent them easily. For instance, multi-component crystal lattices and their pathways can be astonishingly complex, like interconnected metal ties.

</details>

**Speaker A**: 确实如此，这非常引人入胜。比如在电池电解质的研究中，为什么高性能电池技术如此艰难？问题的症结全都在电解质界面的微观结构与反应机制上。为了追求极高能量密度，电解质在极端工况下极易分解并引发副反应。

<details>
<summary>Original English</summary>

**Speaker A**: But yes, that is extremely interesting. Have you ever looked closely at electrolytes? Why are high-performance batteries so difficult to crack? Everything hinges right there. Pushing electrolytes to high-energy limits causes degradation and severe parasitic reactions.

</details>

**Speaker B**: 面对这种纳米尺度的复杂演化，对比生物学的发展速度，你觉得材料科学的纳米技术突破为何经历如此漫长的探索？两者的核心区别在于：生物系统是由数百万年的自然进化所塑造出来的精巧自组织系统；而在非生物无机材料中，我们往往要在高温、高压等极端非平衡态条件下，强行将不同的原子与相界面结合在一起。

<details>
<summary>Original English</summary>

**Speaker B**: When you look at this, how do you think it compares with biology? Progress in nanotechnology and materials has been notoriously difficult over the years. While in biology, evolution over millions of years has produced exquisite self-assembling systems, in inorganic materials under high temperatures, we are forcefully combining distinct atomic phases, where disruptions and boundary defects are everywhere.

</details>

**Speaker A**: 在半导体硅基计算领域，我们遵循摩尔定律（Moore's law）实现了算力的爆发。但在材料研发的实验与表征中，是否也能通过工具革新跨越这个鸿沟？

<details>
<summary>Original English</summary>

**Speaker A**: In silicon-based computation, we have benefited enormously from Moore's law. But in materials experimentation, can we bridge millions of years of evolution through tool innovations?

</details>

**Speaker B**: 在我看来，核心在于涌现行为（emergent behavior）的测量。当我们进行 X 射线表征时，我们测得的是能谱信号（spectrum）。但对于复杂的真实无机材料晶体，能谱并不能直接等同于直观的三维微观结构全貌。很多研究者误以为测出一个图谱就能直接反解出完美的空间原子排列，事实并非如此。材料中的缺陷、相变与非晶区构成了极其繁复的行为。生物学中蛋白质遵循相对明确的折叠模板与局部物理化学约束；而在多尺度材料体系中，从微米级的晶界与微观组织结构，到宏观机械与电化学性能，各个尺寸尺度相互耦合，带来了巨大的理论与建模挑战。

<details>
<summary>Original English</summary>

**Speaker B**: In my view, one of the central problems is understanding emergent behavior. When you take X-ray measurements, you get a spectrum. But for a complex crystal material, that information does not simply equal an obvious structure. People often think: "Isn't it straightforward to deduce the crystal structure?" No, it is far more difficult. In proteins, folding follows certain constrained rules where physics aids structural determination. But in complex materials, emergent phenomena span microstructures across multiple length scales, creating immense modeling difficulties.

</details>

### 从算力极限到高价值应用赛道

**Speaker A**: 既然多尺度微观结构给材料计算带来了如此巨大的维度灾难，那么在研究方向的选择上，我们是否应该聚焦在那些经济价值极高、真正能产生重大突破的特殊材料上？比如超导材料、新一代电池，甚至是科幻般的太空电梯高强度纤维？

<details>
<summary>Original English</summary>

**Speaker A**: Given that microstructures spanning varying length scales make simulation so hard, should we pivot the focus toward high-value materials? When people think of breakthrough materials, things like batteries, superconductors, or space elevators immediately come to mind. What specific categories stand out in your view?

</details>

**Speaker B**: 如果用实际的工业痛点来说话，首先必须提到的是高性能永磁体，特别是如何减少对稀土元素或昂贵过渡金属（例如电池与磁体中的钴）的依赖。从更底层的物理视角来看，我们需要思考计算能力的物理边界。在理论物理中，兰道尔极限（Landauer's principle）定义了每一次计算操作的最小能量耗散。随着计算 FLOPs 数量级随摩尔定律持续攀升，高通量量子模拟的能耗成本也在剧烈上升。

<details>
<summary>Original English</summary>

**Speaker B**: To speak in direct terms: permanent magnets, and especially minimizing dependence on scarce transition metals such as cobalt in batteries, are paramount. Furthermore, we must consider the fundamental physics of computation. What is Landauer's limit here? Every flop of calculation expends energy, and as calculations scale up, the thermodynamic cost of brute-force computational screening becomes a serious constraint.

</details>

**Speaker A**: 没错，10 到 15 年前人们开始大规模尝试高通量材料计算时，往往低估了微观相变所需计算规模与散热问题。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly, that is a profound point. I recall that about 10 or 15 years ago, when large-scale calculations took off, people began encountering these bottlenecks: running massive simulations generates significant heat dissipation and energy consumption.

</details>

**Speaker B**: 是的，当我们在计算机中模拟接近真实尺度的材料相变时，根据热力学与兰道尔极限，其计算功耗和复杂度会迅速膨胀。如果不结合真实世界的物理约束，单纯依赖盲目的高通量暴力计算，就相当于在没有现实反馈的真空中空转。你不能只建立一个理想化的“完美晶体（perfect crystal）”模型就宣称自己解决了真实世界的问题。在真实的工程场景中，材料往往充满缺陷、杂质和多晶相，现实并不符合理想模型的简单假设。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. When you perform these intense calculations, heat is generated, and Landauer limits ultimately apply to the efficiency of continuous computation. Computation is massive in theory, but without physical validation, relying only on predictive simulations without empirical checks can lead nowhere. Some people assume you can just model a "perfect crystal" and claim success, but real-world materials possess real defects and disordered boundaries that behave entirely differently.

</details>

### 自主化实验室与材料闭环合成

**Speaker A**: 正因如此，很多顶尖的投资者和学者，比如埃拉德·吉尔（Elad Gil）在相关讨论中也指出，单纯的软件与 AI 算法必须与物理世界的实验基础设施相闭环。不能仅仅坐在电脑前做理论预测，而是要加速“合成-表征-反馈”的完整实验周期。

<details>
<summary>Original English</summary>

**Speaker A**: Indeed. One of the most memorable discussions, like conversations with Elad Gil, emphasizes that real impact requires linking algorithms to physical experiments. You cannot just predict in isolation; you have to close the loop through actual experimentation cycles.

</details>

**Speaker B**: 我完全同意这一点。光靠漂亮的算法模型不能代替真实的材料制备。很多人引用一句话：“未来的实验室自动化设备就像拥有 140 的智商（IQ 140）。”这句话的真正内核在于：实验室中的自动化设备不再是死板的机械手臂，而是具备感知与实时决策能力的智能代理。

<details>
<summary>Original English</summary>

**Speaker B**: I completely agree with that. Predictions alone are not enough; you have to shorten the experiment cycle. People like the quote that "instruments and lab automation should operate with an IQ of 140." What does that really mean? It means the laboratory equipment is not just dumb mechanical arms moving around, but systems capable of intelligent real-time adaptation.

</details>

**Speaker A**: 在实现全流程自动化实验的过程中，最初你们遇到了哪些具体的工程瓶颈？

<details>
<summary>Original English</summary>

**Speaker A**: In your early steps toward automating these lab processes, what were the major bottlenecks you encountered?

</details>

**Speaker B**: 在最初的阶段，最大的瓶颈在于样品形态的多样性与复杂表征。传统的流程依赖技术员和科学家手动操作电子显微镜：将样品放置到位、调整对焦视野、拍照分析。这种人工操作方式吞噬了海量时间，根本无法实现规模化高通量。因此，我们早期开发了基于机器视觉和自动化控制的自适应程序，让设备能够自主选取扫描区域、对焦并捕获高质量表征图像。如今，这一系统已经演变为完整的自主化实验流：机器能够根据当前数据分析结果，自主决定接下来的合成参数与测量手段，让高通量材料实验室实现全天候不间断的数据采集与迭代闭环。

<details>
<summary>Original English</summary>

**Speaker B**: In our initial steps, our biggest bottleneck was handling diverse material morphologies. We had technicians and scientists manually operating electron microscopes—searching for regions of interest, adjusting focus, and capturing images. It was extremely slow and unscalable. So we transitioned to automated software that intelligently locates regions, focuses, and acquires micrographs. Now, the machines autonomously synthesize and collect data around the clock, turning the laboratory into a truly scalable, self-driving discovery engine.

</details>

<!-- chunk 5/7 -->

### 实验通量与高带宽控制

**Speaker A**: 听到这个真的很让人惊讶。通常大家会觉得缩小规模、关注细节似乎微不足道，但相比之下，那些需要花费数小时运行的实验，是不是更需要更高的通量或更大的带宽支持？当我得知实验周期长达数小时时，确实感到不可思议。

<details>
<summary>Original English</summary>

**Speaker A**: Иџьашьаны Ари уаҳауеит избанзар Аиҵахара хшыҩзышьҭра азҭаразы, Ихәыҷушәа убоит иаҿырԥшны сааҭла инарыгӡоит, ииашоуп? Мамзаргьы Еиҳа ирласны ма Иҳараку Абандҭбаара or something else. Сара иџьеишьеит уи аниаҳа.

</details>

**Speaker B**: 关键在于，当实验本身确实需要耗费大量时间进行时，在容易出错的关键阶段进行细粒度控制就变得极为重要。换句话说，我们需要更精准、更严格的控制。

<details>
<summary>Original English</summary>

**Speaker B**: Акраҵанакуа, Аԥышәарақәа ииашаҵәҟьаны Акыр агара Агхара ахьыҟоу астадиақәа аҵакы амазаауеит. Еиҳа ииашоу АКОНТРОЛЬ.

</details>

**Speaker A**: 还有另外一点——因为这本质上类似于根本原因数据分析，其边际价值极高。最后，特别是进行专门的 X 射线衍射（XRD）分析测试时，往往需要提前数小时进行准备。而在我看来，真正的处理结果和判定其实只需要几分钟。

<details>
<summary>Original English</summary>

**Speaker A**: Another thing— избанзар уи еиԥшуп Изыхҟьо данноқәа ранализ, зыхә ҳараку. And, finally, анализ ҷыдала XID- аԥшра аҭахуп 2 Сааҭқәак раԥхьа Алҵшәа, ари, сара сгәанала аминуҭқәа.

</details>

**Speaker B**: 噢，当然是这样。没错。而且随着执行的实验数量不断增加，对吧？你们所做的不仅是单一任务。确实如此。这不仅仅是一个孤立的瓶颈工具，而是整个推导与分析链条中的核心环节之一。

<details>
<summary>Original English</summary>

**Speaker B**: О, ҳәарада. Ааи. Нас ԥышәарак еиҳаны анагӡара Ааи? You are performing. Ус ауп. аҩныҵҟа Ари уадаҩрак мацара акәӡам. аинструмент. Ари ус акәӡам алкаақәа рышьҭақәа руак.

</details>

### 人机协同与自动化闭环中的操作权责

**Speaker A**: 我明白你的意思。你看，这是为什么呢？我认为正因如此，如果这其中涉及到关键环节，到底由谁来主导这些步骤，谁在实际工作中承担最终职责？

<details>
<summary>Original English</summary>

**Speaker A**: Сара еилыскаауеит уара уара иуҳәарц иуҭаху. Уааԥшы, изакәызеи? Сара ус сгәы иаанагоит, and therefore so. Ус анакәха, изакәызеи Уара ухәҭаа урҭ, насгьы дарбан ииашаҵәҟьаны.

</details>

**Speaker B**: 好的，是的。我想到的另一点是，这或许也是一种演进。我认为目前仍然是人类科学家在宏观主导方向，而具体的执行路径往往会发生交替。有时我甚至会觉得，什么时候才应该真正放手交给自动化呢？我们必须遵循审慎的评估基准。

<details>
<summary>Original English</summary>

**Speaker B**: Ибзиоуп, ааи. Даҽакгьы Сара сзызхәыцуа, ари рҿиамҭазар ҟалап Сара ус сгәы иаанагоит ауаа роуп анапхгара зуа, насгьы Амҩақәа Сгәы иалсуеит зны-зынла Ус ауп. Ианба ашьҭыхра Ҳара агәаанагара ҳақәныҟәоит.

</details>

**Speaker A**: 澄清一下，你们每天都在执行这样的流程吗？

<details>
<summary>Original English</summary>

**Speaker A**: Just clarifying. Даҽазнык do it every day.

</details>

**Speaker B**: 我们非常清楚实际的工作情境。许多实验室确实已经引入了这类自动化机器人。

<details>
<summary>Original English</summary>

**Speaker B**: Ҳара Сара издыруеит аҭагылазаашьаҵәҟьа. аусқәа. Аӡәырҩы ауаа ирымоуп абас еиԥш иҟоу ароботқәа.

</details>

**Speaker A**: 是的。我认为通过人机协同流程，人们可以极快地解析光谱并启动后续实验，逐一排查变量。因此，例如当遇到非常复杂、令人困惑的实验现象且已经耗费了数月时间时，这种流程能够避免浪费大量宝贵时间。

<details>
<summary>Original English</summary>

**Speaker A**: Ааи. I think that one апроцессқәа рҟынтәи, ауаа реимадареи Даара ирласны иулшоит Аҭшәа аилкаара Аԥышәаратә апроцесси алагара Аӡәаӡәала иқәгатәуп акы. Убри аҟнытә, ҿырԥштәыс, иҟазар Даара иуадаҩу акы Ауснагӡатә аҟазара, уаҟа ауаа џьашьахәуп, насгьы мызқәак ҵуан, Иаԥсамзар ҟалап аамҭа рацәа.

</details>

**Speaker B**: 同样，也有可能出现这样的情况：有时候人们只是在追求特定的极端性能或高带宽通量。但在我们看来，这并不是唯一的方向。系统的实际能力和深度思考同样庞大而关键。一旦超出了这些边界，如果缺乏必要的数据，就寸步难行。很多时候，探寻路径依赖于对实验结果和假设的反复推演与计算。正因如此，我们需要大量的模型支持。

<details>
<summary>Original English</summary>

**Speaker B**: ИАРА УБАС, иҟалар ҟалоит, Д а Ҳара иаҳҭахӡам ахырхарҭа. Аха иҟоуп даара идууп. Аха урҭ асистемақәа ирылшо Иагьа азхәыцра. Убри азы урҭ аҳәаақәа ранҭыҵ, ианумоу Мамоу. Аӡәы Амҩақәа — ахәаԥшышьала алҵшәара аҳасабрақәа. Убри азын, ирацәаны модельқәа.

</details>

### 计算资源分配与负对照的重要性

**Speaker A**: 程序就是这么演化出来的。是的，我也一直在思考这些计算与资源开销。我的意思是，当然，你肯定也认同这一点。最典型的例子就是算力消耗与运算周期的权衡：我们是否真的需要海量的计算资源来支撑高密度的运算？如果一味堆砌算力，这种方式其实并不可持续。对于资源受限的团队来说这更加艰难，因此必须保持高效精简（thrifty）。

<details>
<summary>Original English</summary>

**Speaker A**: Убас иҟалеит апрограмма. Ааи, уи сазхәыцуеит. аҳасабрақәа. Сара сгәы иаанагоит, . I mean, of course, Уара абри уақәшаҳаҭхоит. Уи еиҳарак ииашоуп ҿырԥштәыс, аҩаӡара иазкны ашьҭыбжь амш. Ҳара иаҳҭахуп Ахыԥхьаӡара ду Аҳасабратә Ашьҭыбжь рацәа азы аресурсқәа Ари аус ауӡом. Уара узы еиҳа иуадаҩуп избанзар thrifty.

</details>

**Speaker B**: 努力获取高质量基准确实至关重要，这是对的。你在其他几个自动化平台上应该也注意到了：往往会出现大量“零结果”（zero results），即材料合成或表征未达到预期；而在像你们这样的系统中，往往依赖全局信号和中位成功率来判定。

<details>
<summary>Original English</summary>

**Speaker B**: Уаргьы ииашаҵәҟьаны Аиура аҽазышәара Ари иашоуп. Ааи. Уара иазгәоуҭеит даҽа ԥыҭҩык рҿы аплатформақәа. Ас еиԥш Азеро еиԥшуп алҵшәа аматериалқәеи уара ахрахәара, еиҳаракгьы, еиԥш Уара утәы сгәанала Азеиԥш сигнал Ақәҿиара абжьааԥны.

</details>

**Speaker A**: 嗯，确实经常是零结果。产生无产物或失败的结果，恰恰证明了我们最初设定的合成目标与假设在当前条件下并不成立。难道你从一开始就没有考虑过先构建对应的控制结构吗？

<details>
<summary>Original English</summary>

**Speaker A**: Ммм. Ааи, зеро. Алҵшәа ҟалар алшоит Иҳаман ҳәа ауп иаанаго акы аԥҵара агәҭакы ашьақәырӷәӷәарақәа иаҳдырбоит ҳара иаҳшам. Уара зныкыр Аԥҵара угәы иҭаӡам аструкткра?

</details>

**Speaker B**: 当然考虑过。是的，很好，你指出了负对照（negative control）的关键性。

<details>
<summary>Original English</summary>

**Speaker B**: Ҳәарада. Ааи. ИБЗИОУП. Уара иухыухуеит негативтә контроль.

</details>

**Speaker A**: 当然，负对照至关重要。体系中存在各种杂质相、过渡相以及独特的物理化学特征。

<details>
<summary>Original English</summary>

**Speaker A**: Ҳәарада. ИБЗИОУП. Ҳәарада. Иҟоуп аҟьашьратә фазақәа, аҟазшьақәа.

</details>

**Speaker B**: 对，完全没错。确实可能如此，100% 正确。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи, ааи. ИБЗИОУП. Ҳәарада. Ари ҟалар алшоит Иҵабыргыҵәҟьаны. 100%.

</details>

**Speaker A**: 许多过往文献中的产物，其先验结构与物相组成在实验前根本是未知的（was not known）。因此，负样本和阴性数据对于训练至关重要。大家过去往往只关注阳性结果。

<details>
<summary>Original English</summary>

**Speaker A**: ИБЗИОУП. Ҳәарада. џьоукы рылҵшәа Ирылшеит Уаанӡа иҟаз аилазаашьа was not known. Убри аҟнытә анегативтә. Ҳара Аҟаҵара дашьҭан.

</details>

### 数据合成、文献偏见与工程迭代

**Speaker B**: 是的。一般来说，分类算法在学术界往往只使用阳性数据（only positive）进行发表，用于材料合成报告。这在文献中非常普遍，然而这就导致了偏差。此外，我们对晶体结构的认识，是的，问题的关键就在于表征手段的覆盖范围。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи. And also in general, Алгоритм аклассификациа. Аҟны акәзар Убзиахоит only positive. Аригьы Акьыԥхьра synthesis. Зны-зынла урҭ азыманшәалара. Um, and also, we Ҳара иаҳдыруеит акристалл Ус ауп. Yes, the question амҽхакрбага.

</details>

**Speaker A**: 举例来说，是的。我认为在我们讨论的算法语境下，还有另一个维度。你们是否经历过这样一套流程：通过负向迭代过程不断逼近最终理想的阳性产物？这种材料探索本身极具吸引力，我会将其称之为一种工程化过程。

<details>
<summary>Original English</summary>

**Speaker A**: Ҿырԥштәыс иаагоуп, Ааи. So, um, I think, Ҳара иаҳҳәо аконтекст аҿы алгоритм. Сгәанала, иҟоуп даҽакгьы. Ус еиԥш иҟоу асериа шәымоума? анегативтә апроцесс аитерациақәа уара азнеира ипозитивтәу алҵшәа. Иара даара аинтерес аҵоуп аматериал, сара уи ахьӡысҵон апроцесс инженертә.

</details>

**Speaker B**: 确实，当真正的有效结构被创造出来时（was created），其后续优化与演进往往超越了传统教科书中的定式。我们确实具备应对更复杂探索目标的能力，并且正在不断积累这种实证经验。

<details>
<summary>Original English</summary>

**Speaker B**: Um, so, Ииашоу Убасҟак was created. Ум, насгьы уи аиҭаҿиара Иазхар ҟалап Иҟоуп усқәак, иудыруеит, Ашкол аҿы арҵага шәҟәы, аха егьырҭ Аусқәа ииашаҵәҟьаны Ахықә иқәгылоуп алшарақәа ҳамоуп, ҳаргьы убас Ҳара ари еизаҳгоит аԥышәа.

</details>

**Speaker A**: 那么你是否了解，积累了大量未成功的负向数据后，整个事件的走向发生了怎样的变化？

<details>
<summary>Original English</summary>

**Speaker A**: Нас Иудыруама, иамоу анегативтә хыԥхьаӡара ишԥанеитәу ахҭыс?

</details>

**Speaker B**: 是的，回顾最终结果，如果所有探索都由研究人员独立手动完成，往往只能得到孤立的产物。于是大家开始认识到，光有一次性的阳性结果是远远不够的，真实空间中绝大多数都是未反应或失败的负样本。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи, ҳхынҳәны алҵшәа Зегьы ҟауҵар рхала, Шәара шәеиҳараҩык алҵшәа Амала иуиҭоит. Ус анакәха, шәара иалагеит "зынтәи", анегативтә Иазхом ипозитивтәу. Еиҳараӡак анегативтә.

</details>

**Speaker A**: 我明白了。那么如果将这些数据全面输入到模型中（Such data process into the model），涵盖所有实验条件和对话反馈的高价值全局数据，就能训练出真正顶尖的模型（the best models）。

<details>
<summary>Original English</summary>

**Speaker A**: Аха иҟазар Сара еилыскаауеит. Ус анакәха уара утәы ИБЗИОУП. абӷьааҳәа. Such data process into the model. Убри азы данноқәа, аицәажәарақәа реиԥш, Имҩаԥысит Зегьы реилаҵара зыхә дуу. Ум, насгьы сгәы иаанагоит аҭҵаарадырра алҵшәақәа, а аусушьа. the best models.

</details>

### 物理世界与基础模型的交汇

**Speaker B**: 但是，关键区别在于，这些物理世界的材料创造无法单纯靠纯软件式的灵感凭空倒推。虽然相对强度（RSI）等指标可能会更高，但这是否意味着某些推论在现实物理中完全不合逻辑？因为这就是客观规律。

<details>
<summary>Original English</summary>

**Speaker B**: Аха Аха, еиԥшымзаарас иҟоу Уи уаҳа ишымхынҳәуа арҿиара, амаҭәашьартә ҟәышра. Ус анакәха, ари... . Yes, the RSI is higher. Ари ҷыдала иҟоуп Аха уи иаанагома иҟалап, иаҳҳәап, ари логика амаӡам, избанзар уи акоуп.

</details>

**Speaker A**: 是的，这正是我想说的。在充满不确定性的现实决策环境中，当启动 AI 自动化闭环时，人们往往会真正撞上物理世界的硬约束。此外，我认为还有另一个维度：即便目前仍有机遇，前沿实验室此前在某个水平线上可能会停滞不前，而引入像 GPT-4 这样的模型后，大家便会说：“好的，从现在开始我们将实现飞跃式改进。”因此，我们坚信物理科学与工程系统之间正孕育着全新的系统能力。

<details>
<summary>Original English</summary>

**Speaker A**: Ааи, уи ауп исҳәарц исҭаху Адкылара ыҟоуп аҭагылазаашьақәа рҿы аӡбарақәа ақәымгәыӷрақәа, Еилкаауп, абжьы анго АИ ациклқәа ралагара. Иҟоуп даҽа џьоукы ауадаҩрақәа уанрықәшәо Аиҿцаараҵәҟьа афизикатә дунеи ацны. Уи адагьы, иҟоуп ҳәа сгәы иаанагоит даҽа ганк, иаҳҳәап Иарбан еиҵацалоу Ашансқәа макьана иҟоуп даара акраҵанакуеит. Ҟалозар Алкаа абас иҟан Иазхоуп, зегьы Иԥхьагылоу алабораториақәа Аҩаӡараҿы иаангылон GPT-4 иаҳәоит: "Ибзиоуп, иахьарнахыс ҳара Иҟаҳҵоит Аиӷьтәра Убри аҟнытә, ҳара агәра ҳгоит афизикатә рыбжьара аҭҵаарақәеи аинженериеи ари ҳара ҳҿы Еиуеиԥшым ахкқәа рцәырҵра асистемақәеи алшарақәеи.

</details>

**Speaker B**: 无论具体模型如何迭代，它所带来的机器学习成果都是极具价值的。从科学认知的角度来说（And scientific），为什么以前人们做不到？正因为我们建立的自动化实验室将数字世界与现实世界深度耦合。我们不仅坚信科学发现与材料验证是可行的，而且单靠软件 AI 是不可能凭空在空房间里造出室温超导体的。

<details>
<summary>Original English</summary>

**Speaker B**: Амодел акәзаргьы Абжьбатәи абиԥара Адкылара алҵшәа. ИАРА УБАС Амашьынатә ҵара ибзиаӡоу иазыҟаҵоу. And scientific еилкаарала, даҽакала иуҳәозар, Избан шәазыҟаҵамыз? . Убри азоуп абарҭ зҳаргыло алабораториақәа, убас ала аҩбагьы Урҭ рхархәара адунеи, избан акәзар ҳара ҳакәӡам Ҳара агәра ҳгоит уи ҟалар шалшо Ибзианы аҟаҵара Аартра, акгьы аԥышәара. Ааи, аӡәгьы илшом супермҩангагак аԥҵара ауада АИ ацхыраарала.

</details>

**Speaker A**: 对，没人能仅靠一个纯软件 AI 就在房间里凭空制造出超导体。不过大体上就是这样（But that's about it）。在我看来，这对于理解现实世界至关重要。编程与数学虽然强大，但它们与客观物理材料完全是两码事。

<details>
<summary>Original English</summary>

**Speaker A**: Ааи, ааи. Сара исымоуп Адкылара егьы. But that's about it. Ааи, сара сгәанала, уи даара Ихадоуп аилкаара адунеи. Ааи, урҭ ҩ-хҭыск еиԥшым. . Арҭ ҩба даара еиԥшым амаҭәақәа. Исҳәарц исҭаху Апрограммаркреи аматематика.

</details>

### 从原子结构到系统抽象层级

**Speaker B**: 真正的物理突破终将到来。是的，能请你详细展开讲讲吗？

<details>
<summary>Original English</summary>

**Speaker B**: She will come, yes. Ааи, Ааи. О, ааи. Исзаагар сылшома? Унеир улшома?

</details>

**Speaker A**: 因此我想回到刚才讨论的层面。从个体的视角来看，是否还有其他层级？比如在你们所观察到的各个层级中，从这个维度出发，你会发现“没错，现在这个环节仍然需要重复验证”。

<details>
<summary>Original English</summary>

**Speaker A**: Убри азы, Сара схынҳәуеит Излацәажәоз акампаниа, хаҭалатәи ауаҩы изкны абри аҟынтә. Are there others? Иаҳҳәап, аҩаӡараҿы шәара игәашәҭо, насгьы Иудыруама, сара Сара ахәыцра сҭахуп. Уи иазкны абри аган ала убара, нас уазхәыц, уи "иашоуп, уажәы абри Уаҳа Алакьысра аҭаххоит ари еиҭа.

</details>

**Speaker B**: 至于这一点——不，目前多达 90% 的繁重工作依然需要人工深度参与。我们本希望能有一张现成的、无可争议的完整疆界地图，但现实中并不存在这种捷径。你能列举出具体的几个层级吗？

<details>
<summary>Original English</summary>

**Speaker B**: And this one— Ааи, мап, мап, макьана 90% ауаҩы иусура. Иудыруеи, иҟалап Иҳалшон џьара Ахсаала ҭыхтәуп атерриториақәа ҳәа акгьы ыҟам. Иҟоума, мамзаргьы Ухьӡ уасҳәар сылшоит ҩаӡарақәак.

</details>

**Speaker A**: 我看到你提出了一个非常切中要害的问题。我有很多系统性的思考与回答，让我们逐一拆解这些层级：第一个层级——最底层的原子与晶体微观结构。这本身是一种抽象，对吧？世界上不存在绝对完全无缺陷的理想结构。

<details>
<summary>Original English</summary>

**Speaker A**: Сара Сара избоит уара Бзиак ҭарҵеит азҵаара. Сара исымоуп Рацәак Асистематә аҭакқәа, аха Ҳаицәажәап ҩаӡарақәак рзы. Акы аҩаӡара — ари атомтәуп аструкткра. Иара абстракциа, ииашоума? Аидеал ыҟаӡам

</details>

<!-- chunk 6/7 -->

### 原子结构近似与连续介质模型

**Speaker A**: 在我们处理原子结构时，这仅仅是一种近似方法——本质上是一个连续介质模型（continuum model）。换句话说，在这种尺度下不再考虑分立的原子排布，而是将其视作连续的网格。当然，在度量层面，我们必须依赖热力学。比方说，如果你进行无休止的测试，最终的状态会变成什么样？这里还有另一个核心问题：测试过程不可能永远进行下去，因为时间是有成本的。那么，反应究竟能否迅速发生？体系是否具有足够的能量驱动反应？

<details>
<summary>Original English</summary>

**Speaker A**: In what we do with the atomic structure, this is just an approximation—a continuum model. So, there is no longer a discrete atomic structure, but rather a continuous mesh. Of course, in terms of measurement, there is thermodynamics. Suppose you spend forever testing: what will happen to the final state? And there is another aspect: forever is not an option, so time has a price. So, how quickly will a reaction occur or not, and is there enough energy or not?

</details>

**Speaker B**: 对，这正是我想表达的。关于你对未来理论发展和感知的看法，这完全有可能发生。我的意思是：我们既掌握了这些核心要素，又涵盖了其余各种特性。从一开始，这就是我们的研究本质，因此做决策并不复杂。你不能仅凭某种随机的有用属性来盲目决定该做什么，因为现实研发每天都在发生变化。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, that’s exactly what I mean. Regarding your view on future theoretical developments and intuition, that may very well happen. What I want to say is: here we have this, and we also cover all the rest. I mean, from the very beginning, that has been our character, so it is not that difficult. You cannot simply make decisions based on some random useful property, because that is simply how daily reality works.

</details>

### 人工智能与实验维度的扩展

**Speaker A**: 这里可能还会延伸出一个问题：研究团队是如何协作的？换句话说，在哪些特定节点人类专家的介入最具价值？这难道只是碰巧发生的吗？显然不是。既然要投入研发资金与时间，就必须让所有人高效同频协同。在实验室里，团队成员各司其职，有人推进流程，有人做决策，而重复性的繁琐事务不应耗费核心精力。

<details>
<summary>Original English</summary>

**Speaker A**: There may be an additional question: how do people coordinate? That is, at what specific moments is human involvement most critical? Could this just happen by chance? No, of course not. When you consider the time and money you are spending, it seems essential that everyone works together cohesively. You have people in the laboratory, tasks are moving forward, but you still need human judgment to resolve recurring challenges.

</details>

**Speaker B**: 确实如此，而且环境一直在动态变化。我的意思是，整个系统虽然由人主导，但引入人工智能可以将研发能力提升到一个完全不同的层级。时间是关键函数。目前的大语言模型（LLMs）和其他优秀工具为我们提供了强有力的基底。结合这些基础模型与计算工具，我们可以大幅加速结构发现的过程。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, and it is also constantly changing. I mean, while it is managed by people, bringing artificial intelligence into the picture takes things to another level. Everything is a function of time. From this perspective, there are excellent foundations, such as frontier large language models. By leveraging these tools, we can achieve sufficient capability for finding novel structures.

</details>

**Speaker A**: 这一点在半导体行业尤为关键。半导体领域的产业规划与研发逻辑与我们高度契合：发现新结构、扩大规模。在实验室规模化扩展方面，业界有很多巧妙的技术路径。利用丰富且高质量的实验数据，配合复杂的级联分析序列，你可以将通量扩展到数亿量级。

<details>
<summary>Original English</summary>

**Speaker A**: That is enough to make a significant impact. Take the semiconductor industry: the benefits, planning, and underlying thinking are very much aligned with this. For that vision of scaling laboratories, there are all sorts of cool tricks. By using interesting empirical data and complex analysis pipelines, you can scale up to hundreds of millions of evaluations.

</details>

### 强化学习、自动化管道与超导测量瓶颈

**Speaker B**: 我们能否复用类似的技巧？归根结底，关键在于每次分析的吞吐与耗时。我之前在一篇博文中引用过相关讨论：对于这些高通量实验室，整体耗时究竟如何？在基础线性流程中，如果想要进一步提升速度，能否实现充分的并行化？在这方面是否有秘诀？比如通过引入端到端的强化学习（RL）智能体来全自动调度实验。

<details>
<summary>Original English</summary>

**Speaker B**: Can you use the same tricks across different domains? Ultimately, it comes down to the performance and execution time of each analysis. As I noted in a blog quote: what about the turnaround time in these automated laboratories? In fundamentally linear workflows, if you want more throughput, can you parallelize? Are there specific tricks here—such as deploying an end-to-end RL agent to manage the loop?

</details>

**Speaker A**: 在进行大规模计算之前，我们实际上是在运行自动化的计算与合成活动。这为我们创造了独特的计算学习环境与理论推演空间。不管是生物大分子提取还是无机材料合成，比如数千种晶体样品的结晶与筛选，其核心逻辑都是相通的。

<details>
<summary>Original English</summary>

**Speaker A**: Before running the heavy calculations, we essentially execute automated campaigns. This setup creates valuable learning environments and opportunities for computational discovery. Whether dealing with biological extraction or inorganic materials—such as synthesizing and screening thousands of crystals—the fundamental principle remains identical.

</details>

**Speaker B**: 很多人提到，在测量诸如超导电性这类前沿物性时，测量本身往往是最大的瓶颈。与其他高产率测量手段不同，一次精准的超导特性表征可能需要持续数小时。因此，研究人员常常需要从海量候选化合物中进行筛选，在单个代表性样本上进行极其繁重的测试。

<details>
<summary>Original English</summary>

**Speaker B**: Many people point out that measuring superconductivity is a notorious bottleneck. Unlike high-throughput screening methods, precise superconductivity characterization can take hours for a single measurement. Therefore, researchers often have to evaluate diverse candidate mixtures and run extensive tests on selected specimens.

</details>

### 实验设计迭代、污染防护与跨领域工程

**Speaker A**: 确实如此。有的成分能够成功合成并表现出预期特性，而有的则不行。鉴于需要投入巨额研发资金，我们必须在进入昂贵流程前做好前期验证。我们早早就系统评估了这套研发循环：在扩大实验规模之前，先通过计算优化流程，否则试错成本会极其高昂。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly, some candidates work out, while others do not. Given the substantial financial investments required, you must validate candidate components early before committing to expensive production runs. We have thoroughly examined this experimental cycle from our first iterations: we refine the process computationally rather than blindly scaling up, because physical trial-and-error is prohibitively costly.

</details>

**Speaker B**: 比如在实际实验设备中，操作节拍非常紧凑。稍有不慎，测试通道就可能受到污染或出现物理堵塞，从而带来样品交叉污染的严重风险。因此在设备与实验设计中，我们必须重构方案，优化超薄部件的耐用性，并通过降噪技术保障测试数据的纯净度。

<details>
<summary>Original English</summary>

**Speaker B**: Take physical laboratory appliances, for example: operations run at very high speed. Trays or channels can get clogged or contaminated, posing a severe risk of sample degradation. Therefore, in our hardware and experimental design, we re-engineer components, reinforce thin interfaces, and implement noise reduction across our testing campaigns.

</details>

**Speaker A**: 我们将这些从底层工程中积累的认知沉淀为平台能力，并进行横向扩展。面对多维度的实验需求，我们起初也很惊讶，但很快意识到必须将扎实的工程架构与实验规程深度融合。这不仅需要粉末化学与材料工程的精深积累，还需要底层系统工程师提供坚如磐石的软硬件支撑。

<details>
<summary>Original English</summary>

**Speaker A**: We leverage this deep technical knowledge and scale it systematically. In response to complex operational requirements, we realized early on that success depends on integrating rigorous organizational principles with robust engineering infrastructure. This requires not only hands-on expertise in material powders and synthesis, but also dedicated systems engineers to build reliable pipelines.

</details>

### 交叉学科团队与从自主研发到半导体赋能

**Speaker B**: 建立这样一个连接计算工具与物理世界的闭环系统，是材料科学界长久以来的追求。过去这两类人才往往各自为战，导致工业界缺乏真正打通计算与实验的综合体系。然而，真正推动技术质变的正是一群兼具深厚理论底蕴与硬核工程实践能力的顶尖复合型专家。

<details>
<summary>Original English</summary>

**Speaker B**: Building an efficient bridge between computational tools and physical lab cycles has long been missing in the industry. Previously, theoreticians and experimentalists rarely collaborated this closely. But real progress happens when you bring together world-class domain leaders who can directly translate theory into practical execution.

</details>

**Speaker A**: 确实如此。比如在计算材料学领域，我当年写博士论文时非常敬佩的学者穆拉特·艾科尔（Murat Aykol），也是我们共同的导师克里斯·沃尔弗顿（Chris Wolverton）门下的优秀学者。穆拉特对复杂建模与系统工程有着敏锐的洞察力；我们在麻省理工学院（MIT）的实验室负责人乔（Joe）在合成与实验物理方面造诣极深；团队里还有丹尼尔（Daniel）等出色的研究骨干。

<details>
<summary>Original English</summary>

**Speaker A**: That is very true. When I was writing my dissertation, one computational materials scientist I deeply admired was Murat Aykol, who defended under our advisor Chris Wolverton. Murat has an extraordinary grasp of modeling and systems. Our lab lead Joe from MIT brings exceptional depth in chemical synthesis and experimental physics, and we also have Daniel and talented doctoral researchers on the team.

</details>

**Speaker B**: 像这样的跨界复合型人才在团队中还有很多。从神经网络建模、深度化学机理，到曾在 OpenAI 等前沿机构积累前沿 AI 经验的工程师，这种紧密的跨学科基因深植于我们的团队组织中。

<details>
<summary>Original English</summary>

**Speaker B**: There are many such examples across our ranks. We have people with deep expertise spanning neural network models, chemical physics, and machine learning backgrounds from places like OpenAI. Having wet-lab experimentalists and AI researchers working side by side defines our core DNA.

</details>

**Speaker A**: 最初，我们开发这一整套自动化计算与实验工具是为了满足自身的研发需求——我们自己就是首位重度客户。而现在，我们正将这些平台工具开放给半导体等高壁垒工业领域的合作伙伴。半导体产业传统上非常封闭且严谨，通过将我们的高精度模型与计算系统直接交付给行业科研人员，他们能够以前所未有的速度达成材料突破与工艺目标。

<details>
<summary>Original English</summary>

**Speaker A**: Originally, we built all these proprietary tools and computing power to serve our own internal research—we were our own primary customer. Today, we are deploying these mature capabilities to external sectors, with a major focus on the semiconductor industry. Semis have historically been driven by relatively closed environments; by empowering their scientists with our computational platforms and predictive models, our partners can achieve their technical milestones far faster.

</details>

**Speaker B**: 这正是这项工作的深远意义所在：我们将深厚的材料科学 know-how、严苛的物理化学第一性原理，与现代高效计算系统紧密融合在一起，让产业界能够真正透彻理解并驾驭复杂的材料化学与物理演变过程。

<details>
<summary>Original English</summary>

**Speaker B**: And that is truly significant. Instead of leaving teams to figure out complex physics and chemistry on their own, we provide the foundational models, engineering standards, and computational infrastructure needed to decipher complex materials behavior for industry partners.

</details>

<!-- chunk 7/7 -->

### 软件研发演进与材料科学的类比

**主持人**: 从这些角色出发……已经有很长一段时间了。好的，好的，我明白了。

<details>
<summary>Original English</summary>

**Speaker A**: аҟнытә абарҭ арольқәа роуп. Акыр аамҭа. Ибзиоуп, ибзиоуп, исыздыруам. (So from these roles... It has been a long time. Okay, okay, I don't know.)

</details>

**主持人**: 这是一种模式。在我看来，很多人在谈到你们 Periodic Labs 时，会问这到底是什么。我认为软件开发的发展历程是一个非常恰当的类比：软件工程领域正是经历了类似的演进。

<details>
<summary>Original English</summary>

**Speaker A**: ари модельуп, Сара сгәанала, ауаа Иаҳҳәап, уара Лабс, абри ауп ауаа зыӡбахә рҳәо Иаҳҳәап, изакәызеи Сгәанала, уи даара Аналог бзиа Аҿиара ҟалон апрограмматә еибыҭа апрограмматә еибыҭа. (This is a model, I think people say, like you at Periodic Labs, that's what people talk about, asking what is it. In my opinion, that is a very good analogy: how development happened in software engineering and software development.)

</details>

**嘉宾**: 是的。回看软件工程的早期发展阶段，先是出现了 GitHub Copilot，随后是早期版本的 ChatGPT。人们开始使用这些类 Copilot 工具来协助自己寻找解决方案。不仅如此，随着代码自动化工具（比如 Codex）的普及，现在由工程师纯手工从零编写每一行代码的情况已经大大减少了。我们坚信，同样的变革也会发生在 Periodic Labs 所专注的领域——通过智能化系统加速研究人员、材料科学家的工作。而随着模型智能水平的不断提升，系统不仅能协助探索，更能开始自主评估实验结果，从而助力实现最终的目标状态。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи. Ус анакәха, алагамҭазы Аҿиаратә етапқәа апрограмматә еибыҭа иҟан, иудыруеит, ГитХаб Копилот, нас раԥхьатәи аверсиақәа АицәажәараГПТ. Ауаа рхы иадырхәеит абарҭ акопилотцәа реиԥш иҟоу амаҭәахәқәа, Урҭ дрыцхраарц find a solution. ИАРА УБАС избанзар Автоматизациа Ҳара иҳамоуп Кодекс еиԥш иҟоу , ҳара ҳтәқәагьы маҷҩуп анџьнырцәа акод рҩуеит Ԥаса ишыҟаз еиԥшҵәҟьа . And we believe that Еиԥшу аҭагылазаашьа Периодикгьы ҟалар алшоит, асистемақәа рзы Аусура арццакра аҭҵааҩцәа, аҵарауаа- аматериалҭҵааҩцәа, . But as it grows Аҟәыӷареи Уалагар улшоит Алҵшәақәа рыхәшьара . So, help achieve target state. (Yes. So, in the beginning, in the early development stages of software, there was, you know, GitHub Copilot, and then the early versions of ChatGPT. People used these copilot-like tools to help them find a solution. Also because of automation, we have tools like Codex; fewer engineers write code manually from scratch just like before. And we believe that a similar situation can happen for Periodic Labs, for systems accelerating the work of researchers, material scientists. But as it grows in intelligence, you can start evaluating the results, helping reach the target state.)

</details>

### 贝尔实验室的启示与资本范式转移

**主持人**: 是的。我想表达的是，做这些事情是非常有价值的。试想在大学和学术机构的发展前后，有多少工作能产生真正的商业影响力？如果能吸引更多年轻人、汇聚更多关注，那将是梦寐以求的图景。

<details>
<summary>Original English</summary>

**Speaker A**: Сара Ааи. Исҳәарц исҭаху Абарҭқәа рыҟаҵара ахәарҭа злоу. Ишԥаҟоу еиԥшҵәҟьа ирацәаны аколлеџьқәа раԥхьаи рышьҭахьи. commercial influence. ИАРА УБАС еиҳа азҿлымҳара, аҿар It would be a dream. (Yes. What I want to say is that doing these things is valuable. How many colleges before and after have commercial influence? And also more interest, young people... It would be a dream.)

</details>

**嘉宾**: 这就引出了一个问题：你看历史上的贝尔实验室，它究竟是真实可复制的奇迹，还是不可再现的个例？他们的突破绝不仅仅是一小部分天才孤立的个人成就，也不是偶然碰运气发生的。当时不仅有太空竞赛等宏观时代背景作为底座支撑，更重要的是，西方电气公司与贝尔电话系统遍布全美的电话线路与通信网络，同最前沿的科研思考紧密交织在一起。

回顾人工智能的发展历程：在 2015 年之前的五年周期里，人们所讨论的进展是什么样的？而从 2021 年到 2026 年这五年间，整个局面完全是天翻地覆的差异。真正发生的质变在于：ChatGPT 及类似技术范式的成功彻底重塑了资本版图与资源分配机制。

<details>
<summary>Original English</summary>

**Speaker B**: ИАРА УБАС, иудыруама, Белл Лабс ииашаҵәҟьаны ииашам? So, they are not Ирылшеит џьоукы рхатәы зеиԥш ыҟам achievements. Дара, Ус баша иҟамло иҟан Абар акосмостә ҵаҵӷәы. Аха Мрагыларахьтәи еидызкылоз Мраҭашәаратәи аҭелқәа рномерқәа ацәаҳәақәа. Азхәыцра закәу intertwined. Убри азын, Иарбан прогрессу аицәажәара- 2015 шықәсанӡа. five-year period. ИАРА УБАС 2021 инаркны 2026 рҟынӡа аамҭа, Ус анакәха, абри, иудыруама, ажәҩан ауп Адгьыл. (And also, you know, Bell Labs, was it real or not? So, they are not just unique individual achievements. They didn't just happen by accident. Here was the space race as a foundation. But AT&T and Western Electric telephone lines and network infrastructure were intertwined with scientific thinking. For that reason, what progress was being discussed up to 2015, a five-year period? And in the period from 2021 to 2026, it is like heaven and earth.)

</details>

**嘉宾**: 这一波技术突破改变了一切底层条件：海量算力、高质量数据以及顶尖人才源源不断汇聚，形成了强大的正向飞轮效应。成功反哺了更大的成功，事实确实如此。因此，前沿技术以前所未有的规模撬动了资本与资源；而现在，我们也同样渴望将这种强大的飞轮机制引入到物理现实世界与硬科技当中。

<details>
<summary>Original English</summary>

**Speaker B**: What happened is that ChatGPT егьырҭгьы уи иеиԥшу азнеира аиқәшаҳаҭра landscape of capital. Иара аҭагылазаашьа аԥсахуеит Аҳасабратә амчхарақәа, адыррақәа уб егь. Аҟазшьа бзиақәа ргьежь. Ус ауп. Убри аҟнытә ақәҿиара ақәҿиара аанарԥшуеит. Иҵабыргыҵәҟьаны . So, technology Уамашәа иубаша иҭацәны Акапитал иадҳәалоу насгьы аресурсқәа, ҳара Ҳаргьы убасҵәҟьа ҳахьӡарц ҳҭахуп афизикатә дунеи аҿы. (What happened is that ChatGPT and other similar approaches shaped the landscape of capital. It fundamentally changed the conditions: compute power, data, and so on. A virtuous cycle. That is right. Therefore success breeds success, truly. So technology amazingly channeled capital and resources, and we also want to bring that same momentum into the physical world.)

</details>

### 开源软件生态与计算基础设施投入

**主持人**: 是的。我观察到的一个显著现象是：资金支持正经历从传统学术科研基金向风险投资的重大转移。比如在模型交付方面，你们是直接发布真实运行的模型，还是按照现代软件工程节奏进行定期迭代发布？

<details>
<summary>Original English</summary>

**Speaker A**: Ааи. Аӡәы Сара сгәаҭоит, иҟоуп Аҟынтәи аиасра Аҭҵаарадырра афинанстә цхыраара уҳәа убас иҵегьы авенчуртә капитал ахь Иаҳҳәап, аушьҭразы the actual model? Мамзаргьы Иахьатәи аамҭа иақәшәо рҭыжьрақәа. (Yes. One thing I observe is that there is a transition from academic research funding into venture capital. Say, for releasing the actual model? Or regular modern releases?)

</details>

**嘉宾**: 当然。换句话说，这是一整套明确的技术指引与路径。我们积极开发和维护软件工具链，包括 Materials Project、Custodian、密度泛函理论（DFT）自动化运行工具，以及对 Jackson MD 等关键计算框架的深度支持。因此，我们在开源社区做出了大量实质性的贡献，这些开源项目构成了我们核心能力的重要基石。是的，我们在软件研发上非常活跃。同时，我们还资助了多所大学的研究团队，协助他们向 Superdome 超级计算集群方向拓展。这也是我们全局视野中不可或缺的一环。

<details>
<summary>Original English</summary>

**Speaker B**: Ҳәарада. Даҽакала иуҳәозар, амҩақәҵарақәа. Ҳара иҟаҳҵоит апрограмматә еибыҭа Аматериалқәа рпроект, Ахьчаҩ, р DFT рыҩҩы, насгьы Ацәашьы Ҳара ҳтәқәа руак адгыларақәа. Jackson MD, адгыларақәа. Ус анакәха, ҳара Иҟаҳҵо рацәоуп иаарту ахыҵхырҭахь алагалақәа, иаҵанакуа Ааи, ааи. Ҳара даара активтә апрограмматә еибыҭа. Ҳаргьы иҳамоуп Афинансиркра ауниверситет ҳгәанала, агәыԥқәа ахырхарҭа superdome. Аригьы ахәаԥшра. (Certainly. In other words, directions. We build software: Materials Project, Custodian, DFT runners, and we support things like Jackson MD. So we make a lot of open-source contributions, which are integral. Yes, yes. We have very active software development. We also fund university research groups towards superdome compute resources. That is also part of our vision.)

</details>

### 超导合成的科学路径与镍氧化物突破

**主持人**: 能看到这样的全景布局非常有意思。好吧，让我们设想一下：假设你们在实验室合成这一侧的各个环节都已经完全走通、万事俱备。但我到现在依然不太理解超导电性的探索路径：其中的核心难点与决策点究竟在哪里？总体而言，到底是缺乏指导性的物理理论，还是主要卡在材料合成能力上？

<details>
<summary>Original English</summary>

**Speaker A**: Аинтерес аҵоуп абара Еиҳа абри еиԥшуп Ибзиоуп. Let's imagine Уара уманшәаланы Алабораториатә ииашоуп аспект. Уара зегь умоуп. Уажәгьы ибзианы исзеилкаауам. superconductivity. УА ИҞОУП аӡбара. Иарбан мҩоу? Иааизакны иуҳәозар, иҟам атеориа ма мамзаргьы synthesize. (It is interesting to see... more like this. Okay. Let's imagine you have the lab aspect dialed in, you have everything in place. I still don't fully understand superconductivity. That is the critical decision point: what is the path? Broadly speaking, is there no guiding theory, or is the bottleneck in the ability to synthesize?)

</details>

**嘉宾**: 这正是为什么实际材料合成（synthesis）具有决定性意义的原因所在。超导突破往往来自意想不到的合成实验。以镍氧化物（nickelates）为例：研究者们围绕镍、氧等元素展开探索；在此之前，人们深入研究了铜氧化物高温超导（以铜、氧为基础的高温超导材料，这项发现曾荣获诺贝尔物理学奖）。后来大家逐渐意识到，镍氧化物同样具备极佳的超导潜力。在元素周期表上，镍与铜相邻，它们具有非常相似的电子结构排布。

是的，斯坦福大学的教授们与同行在这方面取得了重大进展，我也正是那时深入了解到：通过制备外延薄膜等精细合成手段，确实有可能在镍氧化物中诱导出超导相。因此，如果我们能建立起由超级智能驱动的实验室自动化合成系统，就能够系统性地探索各个潜在方向。

<details>
<summary>Original English</summary>

**Speaker B**: Убри азоуп synthesis. Иҟалар ҟалоит, супермҩангара. Аиашаз, иара никкелатқәа рыла. Nickel, аксигени егьырҭгьы аус ауит, нас Иҽазишәеит акупратқәа, ус баша аџьаз, аксигени егьырҭгьы Нобель иаԥхьахә. еилыскааит аникелатқәагьы ыҟан хшыҩҵак бзиоуп. Сара исымоуп ҵакыс иамоу аниккелатқәеи Акупратқәа наҟ-ааҟ игылоуп Апериодикаҿы аҭаӡҩырақәа. Ааи. Ааи. Ҳапрофессорцәа Стенфорд, Сара еилыскааит ишсылшоз Аниккелатқәа раԥҵаразы ақәҭых ҵаӷақәа рсахьа змоу супермҩангара. Убри азын, Иҳамазар Алабораториақәа ҟалоит амч ду змоу суперинтеллект азы асинтез нас ҳара иҳалшоит Ахырхарҭақәа рыхә аҽазкра. (That is why synthesis is paramount. It could lead to superconductivity. In fact, look at nickelates: nickel, oxygen and others were studied, and then cuprates—copper, oxygen, which won the Nobel Prize. It turned out nickelates were also a great direction. In my view, nickelates and cuprates sit side by side in the periodic table rows. Yes, yes. Stanford professors and researchers, I realized it was possible to create nickelates in thin film form exhibiting superconductivity. Therefore, if we have laboratories empowered by superintelligence for synthesis, we can systematically explore and evaluate these promising directions.)

</details>

**嘉宾**: 这就像三维药物分子研发一样——在这个领域里，有大量激动人心的前沿课题等待攻克。另一个非常值得深入研究的例子是镁化物（magnesium）。众所周知，二硼化镁（MgB2）是在常压/常规环境条件下具有极高转变温度的经典超导体之一。然而在学术界和行业中，很多人往往坚持要先有完美的完备理论指导；但在超导研究的早期历史上，情况从来不是先有完备理论再有发现的，所有重大突破无一例外都是通过大胆实验与合成探索出来的。

<details>
<summary>Original English</summary>

**Speaker B**: Like 3D ахәышәтәыга — араҟа уи рацәоуп Аус ацура иҷыданы иблахкыгоу. Иҟалар ҟалоит, Даҽакы аҵара иаԥсоуп magnesium. Ишыжәдыруа еиԥш, Зегьы иреиҳау атмосфератә қәыӷәӷәара. ИАРА УБАС Урҭ аинтерес змоу супермҩангара, насгьы MgB2 was one of them. Аха Адәқьанқәа рҿы ауаа ирҭахуп атеориақәа. Ус акәӡамызт зааӡа. Иара иҟан зегьы. (Like 3D drug discovery—there is so much here that is especially fascinating to work on. Another area worthy of study might be magnesium. As you know, with the highest ambient atmospheric pressure transition temperature, and MgB2 was one of them. But people in the field often insist on having theories first. That was never how it worked early on; it was all about experimental discovery.)

</details>

### 登月级愿景与合作收尾

**主持人**: 所以可以想象，这是一个无比生动的梦想——一项真正的“登月计划”（moonshot）。我们必定能一步步实现这一伟大成就。衷心祝贺你们已经取得的卓越突破！在我看来，你们正处于实现这一历史性目标的绝佳位置。

<details>
<summary>Original English</summary>

**Speaker A**: So imagine, ибзаӡоуп ԥхыӡҵас иҟоуп, —и ахыҵра амза. We would just аихьӡара. . Ишәыдысныҳәалоит шәара шәзы successes. Сара Уара уҟоушәа убоит абри анагӡаразы, убри аҟнытә Ааи. (So imagine, it is a living dream—a moonshot. We would just achieve it. Congratulations on your successes. I see that you are truly in a position to accomplish this, so yes.)

</details>

**嘉宾**: 是的，非常感谢！真的太感谢了，今天聊得非常愉快。

<details>
<summary>Original English</summary>

**Speaker B**: Ааи. Ибзиоуп, даара иҭабуп. Иҭабуп. Ибзиан. (Yes. Great, thank you very much. Thank you. It was wonderful.)

</details>

**主持人**: 确实非常引人入胜。再次感谢！

<details>
<summary>Original English</summary>

**Speaker A**: Yes, very interesting. Ааи. (Yes, very interesting. Yes.)

</details>