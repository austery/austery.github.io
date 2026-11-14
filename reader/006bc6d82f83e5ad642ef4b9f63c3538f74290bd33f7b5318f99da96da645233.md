---
author: AI Engineer
date: '2026-09-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ztlXKfPCT3Q
speaker: AI Engineer
tags:
  - rotational-grazing
  - autonomous-agent
  - context-engineering
  - multivariate-analysis
  - regenerative-agriculture
title: 重构实体农业：利用多变量 AI 智能体破局草饲放牧系统
summary: Firecrawl 的 Cody Menefee 探讨了如何将 AI 智能体与上下文工程应用于真实物理世界。面对 97% 肉牛依赖集中育肥的现状，他提出利用卫星与地表感知、开源硬件项圈及 LLM 多变量推理，实现草场轮牧的完全自动化，以技术重塑生态农业与食品系统。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Firecrawl
products_models: []
media_books: []
status: evergreen
---
### 破局思维与跨界实验：从特斯拉运火鸡到重构农业认知

在当下的技术峰会与工程讨论中，软件工程师们往往深陷于一种内部循环——不断为“制造软件的人”开发新工具，陷入在 SaaS 框架与 MCP（模型上下文协议）中打转的同质化竞争。**Cody Menefee**（Firecrawl 增长团队成员）从自身的非典型背景切入，向开发者提出了打破思维局限的挑战。Cody 并非计算机科班出身，他在肯塔基州长大，从事过酒保、机械修理工和服务员等蓝领工作。进入软件行业后，他更倾向于将自己定义为使用 AI 智能体协同编码的“氛围程序员”（vibe coder），而非传统的软件工程师。然而，正是这种不设限的思维，驱使他将目光投向了极度缺乏数字化重塑的传统领域：**畜牧农业**（Livestock Farming），特别是针对草饲牲畜系统的**轮牧自动化**（Automating Pasture Rotation）。

为了亲身体验牲畜养殖的全流程，Cody 曾进行过一次激进的个人实验。在严禁养殖家禽的纳什维尔居民区后院，他违规养殖了十只火鸡，旨在完整经历从饲养到屠宰的心理与实操过程。在屠宰当天，他甚至用自己的特斯拉车顶运载这批火鸡，不仅压裂了车顶玻璃全景天窗，还因巨大的风阻显著削减了电池续航，在超充站引来大量路人围观。尽管他曾设计过极具视觉冲击力的白底黑字“TURKEY”包装并试图全职转行养鸡，但现实的经济账让他意识到小规模传统农场极难盈利。在承担家庭责任的前提下，他放弃了“扮演农夫”的念头，转而思考如何利用底层软件架构、自动化系统与智能体技术，在宏观层面上解决农业系统的规模化瓶颈。

<details>
<summary>Original English</summary>

[Speaker 1]: Right? Hello everybody. My name is Cody. I put this picture up here because this jacket so far has not actually landed as well as I thought it would—no one gets the joke. So this was to really put it in front of your face. I don't just enjoy wearing heavily branded letterman jackets; we intentionally tried to lean into it a little bit.

So my name is Cody, I'm on the growth team at Firecrawl. And today, I'm here to tell you: you're not thinking big enough. But before I can actually get into that, I have to address a bit of an elephant in the room, which is Theo stole my talk. Theo put out a video about a month ago called "You Need to Think Bigger." But I would like to say I submitted the CFP for this talk long before Theo put his video out. I didn't steal his talk; he stole my talk.

Today, we're actually going to talk about farming. And yes, I actually mean farming. More specifically, I mean livestock farming, and even more specifically, I mean automating pasture rotation for grass-fed livestock systems. I'm feeling most of you did not expect to learn about cows and grass and farming today, but I'm here, so you're going to.

A little bit of background on who I am and why maybe you should listen to me: the short version is, I actually have no credentials that qualify me for this talk, but nonetheless, I want to do my best to give it. I grew up in Kentucky, have a background in blue-collar work—I was a bartender, a mechanic, a server, a whole bunch of things. Never actually a farmer, though. And then I sort of found my way into engineering and software development. I actually don't really like taking the title of software engineer; I'm pretty averse to that, it feels like stolen valor, because I am the vibe coder most of you all are scared of. I use AI agents all day long, I don't have syntax memorized, I'm not proficient in any particular coding language, but I will crank out some stuff on a weekend. Today, I work at Firecrawl. We're building context for AI agents. We have a series of web data APIs to give your agents access to the web. Again, I sit on the growth team.

But today, we're actually going to get into some more farming stuff. First, a bit of credential I do have: this is a real picture of me hauling turkeys on top of my Tesla. And I do still have a crack in that glass ceiling because of it. This was in Nashville, where I live in the middle of a residential neighborhood where you are not allowed to raise turkeys. But I raised ten turkeys in my backyard because I wanted to know what it was like to actually raise livestock myself that I would eat. It's a very mentally difficult process, to be honest. But this was me loading them up on the roof of my Tesla, and then I drove for three hours with them to the processor, had to stop at a Supercharger on the way, and lots of people were taking pictures. What I can tell you is your range is sufficiently decreased when you have a giant windbreak full of turkeys on top of the roof. So that was quite the anxious drive.

I can tell you, I also almost left engineering to be a farmer. I really wanted to raise chickens. This is a real product image that I came up with: I wanted to wrap turkeys in white wrapping and literally just slap "TURKEY" on top of it. I thought it was provocative; I thought it would get you to buy chickens. But I realized it's actually really hard to make any money farming—surprise, surprise. And I have a wife, I have two kids. It didn't feel right to ask them to give up the lives they had so that I could go cosplay as a farmer and raise chickens. So I decided to pivot and see if there were ways that we could scale farming itself, and that's the type of systems that I'm interested in when it comes to livestock agriculture.

So three things I want to accomplish in this talk:
1. Convince you all to pursue bigger ideas. I think at a lot of these conferences, a lot of us individually spend a lot of time talking about building software for people who build software for people who build software, and so on and so forth. I'm really just here to challenge you that there are other problems to solve than just another MCP for another SaaS solution at another company.
2. I'm just trying to take advantage of a captive audience. If you corner me anywhere at any time, there's a good chance I will talk to you about farming. So here I am.
3. Hopefully, I can convince you to come work with Firecrawl.

</details>

### 轮牧瓶颈与生态困境：为什么 97% 的肉牛无法在草场终育

在底层生态与动物福利层面，食草牲畜理应生活在天然草场上。放牧模式不仅对动物身心健康、肉类营养成分与消费者福祉更优，更是修复土壤微生物群落与生态多样性的关键一环。然而，当下的工业化农业呈现出巨大的结构性矛盾：全球高达 **97% 的肉牛最终都在集中育肥场**（Feedlot: 依赖谷物和浓缩饲料高密度圈养育肥的工业化设施）完成催肥，仅有 **3% 的肉牛实现了全程草饲放牧**。制约草饲牲畜比例扩大的核心瓶颈并非土地总量，而是极其高昂的**劳动力壁垒**（Labor Bottleneck）。

大众对草饲放牧常存在一种田园诗式的误解，认为只需将上百头牛散放至百英亩草场任其采食即可。但放任自由采食会迅速摧毁草场质量——牛会优先啃食口感最嫩、糖分最高的优势草种，彻底踩踏并忽略适口性较差的杂草，导致优质草种根系枯竭，杂草肆虐，土壤退化。解决这一生态退化的标准实践是**轮牧**（Rotational Grazing: 将草场划分为若干独立放牧小区，定期轮换牲畜以兼顾牧草采食与充分休眠的科学管理机制）。在理想的轮次中，农户需将草场切分为仅供牛群采食单日口粮的**放牧小区**（Paddock），每日执行一次转场移动。这种机制能让被啃食过的草场获得充分休养期，从而成倍提升草场的年均产草效率与承载上限。

然而，精细化轮牧在物理执行层面是一项极其繁重的重体力劳动。农场主不仅要每天在不同地块之间重新拉设电网围栏、迁移重型供水设施，还要顶风冒雨驱赶牛群。近期市场上出现了诸如估值达到 20 亿美元的 **Halter** 以及 **NoFence** 等农业科技公司，它们尝试通过 GPS 智能项圈配合卫星通信，在草场上建立**虚拟地理围栏**（Virtual Fencing），允许农场主通过手机远程设定电子边界引导牛群移动。这虽然在物理层面解放了手动搬运围栏的劳力，但并未解决更高维度的决策难题：**如何决定牛群的下一个最佳移动点**。牧草的生长绝非匀速线性的数学过程，干旱程度、局部降水、历史啃食深度以及土壤肥力均会导致地块恢复速度参差不齐。农场主每日仍需亲自深入草场，依靠经验与视觉直觉评估草高与长势。牧草具有严苛的生长生物学周期——啃食过浅会导致草质老化、纤维化变硬且适口性变差；啃食过度过短则会损毁分生组织，导致数周无法返青。精准把握这一最佳采食窗口，构成了轮牧系统中高度依赖人类专家的核心决策堵点。

<details>
<summary>Original English</summary>

[Speaker 1]: First things first: I believe livestock belong on pasture. I think animals should live on grass. I think it's better for the animal, the consumer, the farmer, the ecosystem. I could give you a whole TED Talk on each of those if I need to; you can find me later if you need me to tell you why it's better for animals to be on grass, but I don't have enough time to get into all of that. Take my word for it. Let's start there: the assumption is animals should be on grass.

This is the ball I want to hit. I am not actually anti-containment farming; I think there's a reason we needed to do that. But 97% of cows are still currently finished on feedlots; 3% are raised on pasture. My contention here is more animals could be on grass. I want to try to figure out how to get animals on grass.

The question is, why aren't they on grass? And that is: labor is the bottleneck. It is a pain in the ass actually raising animals on grass. Pasture done right actually means moving animals constantly, and that takes a lot of work.

If you think about grass-fed beef, you might think of: I have 100 cows, 100 acres; I put 100 cows on 100 acres, they ate the grass, got beef at the end of the year. That's not quite how it works. You will very rapidly decrease the quality of your pasture if you just let cows graze where they want, because they'll graze their favorite things, ignore things that they shouldn't, trample areas consistently, and so on and so forth.

So the solution to that is rotational grazing. What this means is you break up your pasture into individual paddocks where the animals have enough food for one day, and then you move them every single day. This allows certain areas to rest and other areas to be grazed, and over time will increase the efficacy of your pasture. But this takes a whole, whole lot of work. This means you have to move fences, animals, water, and keep track of it every single day in order to appropriately move the animals as often as they need to.

There are some solutions actually trying to work on this problem. You may have seen a company called Halter in the news recently; Peter Thiel invested at a $2 billion valuation. NoFence is the other company. What these companies do is provide collars for the animals connected to GPS satellites, allowing you to draw virtual boundaries where you can move the animals remotely. I think this is a great step in the direction of trying to expand labor.

But this has a problem, which is you have to know where to move the animals. This is not a science, to actually be honest with you. You can't move them in a straight line across the pasture routinely every single day to the same part of land. The reason is that grass doesn't grow the same every single day. There are drought conditions, rainfall, how much impact a particular section of the paddock has had. And the way this is solved today is actually farmers going out on pasture, putting eyes on the grass, and making intuitive decisions about where the next best move should be.

So the question is: how do we replace the farmer's eyes on pasture so that they can remotely make educated decisions on where to move their virtual fences? There's a bit more that actually goes into this as well, and that is you have to also know how tall the grass is. Grass has a growing cycle: if you graze it way too short, it takes a long time to come back; if you let it go too long, it becomes old and bitter, and the animals don't like it. There's this juvenile sweet spot that you want to keep the grass in. You want to cut it before it gets too tall, but you also don't want to cut it too short. You need to keep the animals moving and then constantly coming back to the same pasture so that your grass stays at the most optimal growing phase and constantly has the most productivity possible.

</details>

### 自主放牧的技术闭环：遥感成像、实地基准与多变量决策模型

要彻底取代农场主在草场上的双眼，构建一套端到端的自动化放牧闭环，核心在于建立可靠的草场感知体系与决策中枢。在感知层的工程探索中，Cody 评估了三种差异化的数据捕获路径：
* **无人机正射影像建图**（Drone Orthomosaic Mapping: 拼接高空多角度照片生成毫米级草场几何图谱）：虽然能提供超高分辨率的草高与密度数据，但其实施门槛极高。农户需要接受复杂的飞行培训，且目前全球各司法管辖区均未批准超视距的完全自主农用无人机常态化飞行。
* **高频卫星遥感监测**：类似 Planet 这样的卫星服务商已能实现每日一次的全球 1 米级分辨率重访。然而从轨道高度俯瞰地表，高空光学成像仍难以精确分辨草丛垂直高度与底层含水细节。
* **地表参考标杆与红外相机**：林肯大学密苏里分校的一位研究人员提出了更接地气的方案——在草场关键树木旁设立带刻度的标杆，配合自动感应林道相机（trail cam），以标杆作为物理基准物，持续监测草丛相对于标杆的高度反弹曲线。

一旦低成本感知硬件与 GPS 虚拟项圈完成物理链路整合，系统便能引入大语言模型作为**自主放牧智能中枢**。这个智能体承担的核心角色，是执行跨维度的**多变量综合分析**（Multivariate Analysis）。为了推演当天的最佳放牧坐标，LLM 必须聚合解析一系列非结构化与结构化异构数据流：牲畜实时群落坐标、历史移动轨迹、未来气象与干旱预警指数、全场各小区的生物质累计恢复量。更为关键的是，这种决策并非孤立考虑某一个地理斑块，而是在多重嵌套关系中寻找全局最优解：
* **微观个体层**：单头牲畜在该地块的行为偏好与健康状态。
* **群体群落层**：整个牛群的采食同步性与草皮踩踏承载力。
* **地块循环层**：放牧小区与全农场轮休周期的动态平衡。
* **宏观生态层**：区域水土保持与碳固存效能。

通过算法精确调度放牧节奏，农场得以在更少英亩的土地上支撑更大规模的牛群密度。这种空间利用率与生态承载力的跃升，是从根本上抹平草饲放牧与集中育肥场之间成本鸿沟的技术路径。

<details>
<summary>Original English</summary>

[Speaker 1]: So a couple of ways that we can do this—these are things, these are my solutions, something I've actually been working on and thinking about how we can do this.

A couple of options that I have are:
1. Drone orthomosaic maps. If we could find a way to automate drone flights where we go fly around our pasture, take a whole bunch of pictures, get some very high-fidelity, high-resolution images of the grass that farmers could analyze. The problem with this is there's a lot of skill upgrading we need to do with the farmers to teach them how to fly drones, a lot of regulatory issues for keeping the drones in sight, and ideally this would be autonomous. Currently, there isn't a jurisdiction in the world that has approved autonomous drones for these types of applications. So this is a really big bottleneck. I think it has pretty high fidelity and quality of imagery, but it is going to be a hard problem to solve in terms of actually getting all those hurdles accomplished.
2. Satellites is my most favorite option today. There's a local company called Planet out there taking pictures of the entire globe every single day with 1x1 meter resolution. But they're still satellites really high up in the sky, and it is hard to tell some of the things you need to tell to actually make those educated decisions.
3. The middle photo here is actually from a friend of mine out in Missouri working as a research graduate assistant at Lincoln University. This idea is just putting a trail cam next to a tree and some measuring apparatus that that camera can look at, and just figuring out: how tall is the grass in relation to that particular object? Just so that we have some sort of reference point that we can use to see how well the grass is growing back.

If we can solve this problem along with the collar situation, I think there's a world here where we can drop an LLM in the middle of this loop and start to work on autonomous grazing operations. What this would mean is an LLM essentially making the next best decision on where the animals should be on any given day. This is multivariate data analysis; this requires the LLM to have several data streams: where animals are, GPS locations, where they were yesterday, where they might go tomorrow, what the drought conditions are in the area, how tall the grass is across the entire farm.

And actually, it has to make this decision not just on a day-to-day basis, but in varying degrees of relation:
- Where is the best next place for a particular cow to be?
- Where is the best next place for the herd to be in relationship to the pasture itself, in relationship to the farm as a whole?
- And then more broadly, the ecosystem at large.

All of these components feedback into each other. If you can optimize this entire picture, you have a more productive farm. We can actually have more animals on fewer acres, which is how we end up actually scaling to compete with the feedlot style: we can actually have more cows on fewer grass.

</details>

### 破除生态壁垒：开源知识库、硬件解耦与多物种协同轮牧

为了将上述架构落地为工程现实，必须正面攻克横亘在农业系统前的三大核心阻碍：
1. **农业隐性知识的提炼与数字化**：轮牧领域大量极具价值的实操精髓并未固化在标准数据库中，而是散落在密苏里州、田纳西州和肯塔基州等地农场主的实地讲解视频与学术论文中。针对这一现状，Cody 利用 Firecrawl 的抓取管道采集 YouTube 农业长视频转录文本与 arXiv 研究文献，清洗结构化后构建了开源项目 **OpenPasture**，使分散的农牧知识转化为任何农户与 AI 智能体均可调用的公开基准库。
2. **多光谱草场表征层的构建**：感知系统必须深度量化草场的两大关键生理指标——**生物质总量**（Biomass: 单位面积内可供采食的植被干重）与**物种多样性**（Biodiversity）。单一草种的过度啃食会导致特定优势草退化；而一个高韧性的草场必须保持暖季草、冷季草与固氮豆科植物的复合分布。只有当牲畜摄入全谱系的微量矿物质时，农户才能彻底摆脱人工硫酸铜或矿物舔块的药物依赖。
3. **封闭硬件生态的解耦与开源诉求**：当前以 Halter 和 NoFence 为代表的商业公司奉行典型的“软硬件绑定”锁死策略，用户必须高价采购专用项圈且无法接入第三方软件接口。这不仅剥夺了农户像对抗约翰迪尔（John Deere）农机垄断那样主张的**维修权**（Right to Repair），也直接扼杀了外部算法通过 API 推动围栏调度的可能性。为此，Cody 向开源社区发出号召，呼吁硬件工程师设计基于现成开源元器件、具备开放 API 的平价牲畜智能项圈，将硬件基础设施与上层算法彻底解耦。

在牛羊等**反刍动物**（Ruminant: 拥有瘤胃并依赖共生微生物消化纤维素的偶蹄目哺乳动物）之外，自动化放牧的生态效益还能通过**多物种复合放牧**（Multi-Species Stacking）产生倍增效应。以商业化放养农场 **Pasturebird** 为例，他们将可容纳数千只肉鸡的禽舍改装在巨型滚动轮轴上，设定机械系统每 24 小时沿草场向前平移一段距离。肉鸡作为杂食性动物，其排泄物富含高浓度的氮磷钾元素，是草场绝佳的天然有机肥料。当牛群与鸡群形成阶梯式轮替时，系统将触发强大的生态共生循环：
* **前置采食**：牛群首先平整并啃食过高过硬的草冠顶端。
* **后置净化**：紧随其后的鸡群啄食牛粪中的寄生虫幼虫与蝇蛆，既摄取了昆虫蛋白，又在源头上切断了反刍动物寄生虫的感染生命周期。
* **生物降本**：整座农场的寄生虫负荷大幅降低，直接免去了昂贵的化学驱虫药剂开销，在无需频繁人工干预的前提下培育出了抗病性极强的动物基因库。

<details>
<summary>Original English</summary>

[Speaker 1]: How do we solve this problem? There's a couple of components. There's three main blockers that I think exist in order for us to actually create this system:

The first one is building a knowledge base, and this is primarily what I'm working on at Firecrawl, and then an open-source project I have called OpenPasture. The idea here is a lot of the knowledge on when to move, why to move, how to move, the benefits of moving, etc., is all locked up primarily in videos. There's a bunch of really cool farmers out there—I could give you a whole bunch of channels you could go down rabbit holes on—just good old guys out in Missouri, Tennessee, Kentucky, trying to move their animals every single day, telling you what they're learning, telling you what species are best for this, what legumes you want to aim for in the wild diversity of your pasture, and a whole bunch of things that go into this. We need to build that knowledge base. Firecrawl is a toolkit that I use to actually collect this data, going out scraping those YouTube videos, scraping research papers such as arXiv, building this knowledge base up. OpenPasture is the actual repository I put this information in to make it available to any farmer that I think might be able to use it.

The next thing to solve is the visualization layer. There's a lot of components we need to know about the grass that farmers primarily get out of intuition from looking at the pasture. The two main things worth figuring out about the pasture—both where the animals are, where they should go, where you want them to be—is:
1. What is the biomass? How much foliage actually is available for them to consume?
2. In the long term, what is the biodiversity of that particular pasture?
If they overgraze sections too heavily, they'll start to over-index on different types of species, and warm-season grasses and legumes degrade, etc. Ideally, you want a really rounded, really diverse pasture over time to make sure that the cattle are getting the nutrients they need to, so you don't have to supplement with things like copper, minerals, etc. Ideally, they get all of the micronutrients and macronutrients from the grass itself, which becomes an entirely, ideally, hands-off system.

And then the third one is those geofence companies—NoFence, Halter. While I appreciate the technology they're trying to push forward, I have a pretty strong disagreement with them, which is: in order to use their software, they require you to buy their collars, and you can't plug your own software into their collars. From a business standpoint, I get why this is; from an industry standpoint, I think it's a real pain in the ass. I would like to innovate on the software layer. I would like to push GPS locations to these collars that my LLM can predict. I don't want to have to rely on their software to do this because I don't think it's as good, or I think I can make it better, to be totally honest with you.

So a bit of the purpose of this talk is actually a call to action for you all in the audience: I need someone to make me a collar. I need it to be open, the APIs need to be open. Ideally, it's an off-the-shelf solution, some component parts that we can slap together. Farmers are pretty scrappy and like to build their own things. There's a lot of analogy to John Deere and the Right to Repair. So I ask anyone looking to design an open collar where the patent can be open and the APIs are open so that we can compete on software and optimize this solution.

The next thing I'd like to tease you about is: this actually goes beyond just ruminants. Ruminants are a type of animal—cows, sheep, goats—all ruminant animals that chew grass and digest it in an organ called the rumen. But there's actually an additional benefit we get when we stack species on these pasture rotations. A company called Pasturebird was a big catalyst for me to really get obsessed with this idea. What they did is took your normal chicken house, put it up on big wheels, and automated the movement so it creeps every 24 hours across pasture. The reason you can do it this scientifically with chickens is because they don't actually get most of their nutrients from the grass—you have to supplement them with grain feed because chickens are omnivores, not quite herbivores. So you can just inch this coop across the grass, giving them fertile land to grow on. The nitrogen from their droppings actually helps as a fertilizer for the grass itself.

And there's an added benefit here when you stack the ruminants with the chickens: if you run ruminants first, they sort of cut off the top of the grass, and then chickens come behind them and peck out the parasites from their droppings. It reduces the parasite load overall across your farm, which reduces the medication expense you have to pay to keep your animals healthy. Over time, you have a more robust breeding stock, so you have stronger animals over time that require fewer interventions and can be left alone to just eat grass and turn into meat eventually.

</details>

### 物理世界的真正命题：上下文工程与非确定性决策的未来

纵观农业自动化面临的重重技术关卡，软件工程的进化方向应当迎来一场深刻的范式转移。当前软件行业存在过度追求将大型语言模型塞入**确定性算法**（Deterministic Algorithm）的执念，然而现实世界中最具颠覆性价值的物理场景，几乎全属于**非确定性问题**（Non-deterministic Problems）。在农场微气象、土壤墒情与牲畜摄食相互交织的复杂混沌体系中，并不存在唯一的绝对数学最优解，有的只是在海量多源数据博弈下权衡生成的概率性最优建议。大语言模型真正的破局点，正是作为“多输入感知与非确定性推理”的中枢，在不确定性中给出高置信度的决策路径，由人类农户进行最终的确认或修正，从而将农场主从繁重而受限的体力搬运中彻底解放。

这类真实世界复杂问题的核心咽喉，归根结底在于**上下文工程**（Context Engineering: 面向 AI 智能体的高质量异构外部世界数据感知、清洗、封装与结构化供给全流程）。智能体若要对物理世界做出准确推演，必须获得真实、高信度且低延迟的环境上下文。这也正是 **Firecrawl** 的核心技术使命所在：通过构建强大的网络与数据获取基础设施，将非结构化的长视频转录、学术论文与动态传感器数据转化为智能体可无缝消化的富上下文层。跳出为软件工程师重复造轮子的狭隘舒适区，投身于粮食体系、实体工业与生态基建等庞大现实物理命题的构建，才是当代 AI 开发者应当追求的宏大愿景。

<details>
<summary>Original English</summary>

[Speaker 1]: So the three things I really hope you will take away from this talk:
1. I think we need to find big, real-world, physical problems that we can solve that require multivariate analysis and not quite yes/no decisions. There are lots of problems out there that don't actually have deterministic solutions. I hear a lot of engineers talk about how we turn LLMs into deterministic processes, and my contention is actually there's a lot of problems that you can't solve with deterministic algorithms. This is one of them. It's a multivariate analysis. There isn't a single "next best paddock" to move to; there's just a best guess on where you think they should go. I think we can take systems like that, that are multi-data input systems, and drop an LLM in the center that actually reasons over the data and at least makes a suggestion that the human can confirm or deny. We can really start to scale systems like this that are very much restricted by the farmer's ability to allocate their own labor or their decision-making power, and really give them the tools that they need to grow their operations. Hopefully, I think all animals can be raised on grass if we solve these problems.
2. The last one is: maybe you can help me solve some of these problems. The number one problem is actually just giving the agents the context they need—gathering the data, packaging that data, and then presenting it in a way that the LLM can reason over. That's what we do over at Firecrawl.

So you're not thinking big enough. Firecrawl is building a context layer for AI, and I hope you can come build with us. We're hiring, so here's all the job postings we currently have. Go on our website and if you find something that works out for you, reach out to me. We'd love to have more people trying to figure out how we get data off the web to solve some of these more complex problems and present that data as context to the AI agents. Perhaps we can make the world a better place.

My name is Cody. OpenPasture is my open-source project; Firecrawl is where I do my day-to-day life. And these are my socials. I'll hang around for a little bit. I'd love to chat more about animals, cows, birds, all you like. Thank you very much for coming.

</details>