---
author: EO
date: '2026-06-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bVSzAkuuymw
speaker: EO
tags:
  - category-design
  - revenue-ai
  - market-selection
  - software-engineering
  - startup-strategy
title: 破局局部最优：Gong 创始人谈 AI 时代的品类创造、逆境攻势与商业壁垒
summary: Gong 联合创始人兼 CEO Amit Bendov 结合自身从程序员、销售到掌舵 70 亿美元估值公司的创业历程，深入探讨了初创企业如何突破市场容量的“局部最优”陷阱。他分享了 Gong 如何从 CRM 的数据盲区中发现痛点，利用“音轨化”界面与“听播比”等设计定义收入 AI 品类；阐述了在 2023 年行业低谷期，通过控租金、重研发以及“爬坡突袭”战术击溃对手的实操策略；并深刻剖析了 AI 时代“氛围编程”的幻象，指出企业真正的护城河在于复杂的生产运维与 B2B 销售中的非对称博弈。
insight: ''
draft: true
series: ''
category: business-entrepreneurship
area: finance-wealth
project: []
people: []
companies_orgs:
  - Gong
  - Salesforce
  - Sisense
products_models: []
media_books: []
status: evergreen
---
### 市场选择与“局部最优”陷阱

初创企业的停滞往往并非由于外部大环境的恶化，而是因为其所切入的**细分市场**（Market Segment: 拥有相似需求和购买行为的客户群体）容量不足。如果目标市场规模太小，其他所有的努力都将无济于事。这就像数学中的**局部最优**（Local Optimum: 在特定邻域内最好的解，而非全局最优解）概念：你正在努力攀登一座小山丘并成功登顶，但你其实永远无法到达真正的高山。在狭小的市场里，你或许能做到 5000 万或 1 亿美元的年营收，但绝对无法成长为一家十亿美元级别的巨头。因此，企业决定在哪个市场中竞争，比其他任何事情都更为重要。

许多创业者在遭遇瓶颈时，需要分清这究竟是企业内部的问题，还是市场天花板所致。例如，有些公司专门为**销售开发代表**（Sales Development Representative: 负责挖掘潜在客户并预约会议的初级销售人员）开发解决方案。如果你身处硅谷，你会觉得每个公司都设有 SDR 岗位；但实际上，像在威斯康星州的企业可能根本没有这个角色。这就是一个典型的小市场案例。更糟糕的是，在一个容量狭小且竞争激烈的市场中生存，就像“五条饥饿的狗在抢一小块肉”一样惨烈。而对于 Gong 而言，我们在一开始就明确自己面对的是一个万亿美元级的庞大机会。如果项目最终失败，那绝非市场问题，而只能归咎于我们自己。

<details>
<summary>Original English Source</summary>
A lot of companies stall, not because of external conditions. It's because maybe the market like isn't large enough. If your market is too small, very little else matters. There's like in math this thing of local optimum, right? You're climbing a hill and you reach the top, but you're not getting to the mountain. You can get to like 50 million, 100 million, right? You're not going to reach like a billion. Which market do you play in? That's like more than anything [music] else. ... So, first understand if you're stuck, understand if it's just like intrinsic to your business or something that's happening right now. There are a lot of companies that are, for example, oh, we're developing solutions for SDRs, right? That's something don't do that. If you live in the Bay Area, you think like everybody has SDR. Companies in Wisconsin don't have. So, this is example of a small market. I mean, you can get to like 50 million, 100 million, right? You're not going to reach like a billion. So, understand if you're stuck because you've reached a local optimum of your market. Also, if it's a small market and it's very competitive, that that's that's the worst thing. It's like five hungry dogs like fighting for a very small piece of meat, [music] right? For us, we understood, "Listen, we have like a trillion dollar opportunity. Like if we don't succeed, like it's not the market, it's us."
</details>

### 重塑 CRM 盲区：Gong 的产品起源与融资困局

Amit Bendov 拥有多元化的职业背景。他出身平凡，家人大多未上过大学，早年梦想是成为摇滚乐团的吉他手。虽然琴技不错，但深知自己并非最顶尖的 1%，且身处以色列这样的小国，难以以此维持生计。为了糊口并接近演艺界，他最初在一家乐器行（类似于 Guitar Center）销售专业音频设备，随后因对计算机科学产生兴趣而转型为程序员。他曾带领研发团队，并从特拉维夫搬到美国创立了 ClickSoftware（后被 Salesforce 收购），之后又担任商业智能公司 Sisense 的 CEO。

在 Sisense 任职期间，公司遭遇了一个极其糟糕的季度，而管理层对此一无所知。当时所有人都在宣扬**客户关系管理系统**（Customer Relationship Management: 用于管理企业与客户互动关系的系统）是唯一的“单一真理源”。但当他们去分析 CRM 数据时，却发现里面空无一物——因为其完全依赖于人工汇报，仅有大约 1% 的真实业务信息能被录入系统，其余 99% 都留存在销售人员的脑海中。结果就是，只有半数销售人员能达成业绩指标，而高达 90% 的销售机会流失了，企业却完全不知道原因何在。当时，AlphaGo 已经击败了人类围棋世界冠军。Amit 想到：能否构建一个免去人工手动更新 CRM 负担的自主化系统？这个系统能自动捕捉沟通对话的完整上下文，并利用 AI 将其转化为逻辑洞察与业务行动。

在产品设计上，Gong 融入了 Amit 早期音乐行业的背景。由于不希望管理者被迫去听 45 分钟的完整会议录音，他们借鉴了 SoundCloud 的播放按钮设计，并模仿 GarageBand 等音乐软件的音轨结构，在界面中为不同的参会人员分配不同的音轨。此外，他们还首创了**听播比**（Listen-to-Talk Ratio: 销售人员在对话中倾听与发言的时长比例）指标，并开发了自动追踪竞争对手提及情况的功能。

然而，Gong 的早期融资过程非常艰难。投资人普遍担心销售人员会因防备心理而将该系统视作监视员工的“老大哥”（Big Brother）；同时认为 Google 和 Amazon 等科技巨头会轻易占领这一空间，且当时的 AI 技术水平尚未成熟。但最终，几家投资机构的注资让 Gong 得以启航，并从此走上快速发展的轨道。目前其季度营收同比增长率连续 12 个季度保持在 50% 以上。

<details>
<summary>Original English Source</summary>
I grew like in a very humble background. I mean, great family, loving family, but most of my family like did not even like go to college or university. So, from my family's perspective, if I was like seller at a retail store, it'll be just fine. They'll love me still the same because it's a job and that's what you do. So, my original dream as a teenager, I wanted to be a guitar player at a rock band. I was pretty good, to be honest, but not like not top 1% and I was like in a small country, Israel. It's not you can't even if you're big, like it's not all that big. That's a miss, but I started my career actually selling professional audio equipment at a retail store like like a guitar center. I was hoping to get close to the the showbiz, but I realized, "Okay, maybe like you know, I don't want to play in weddings when I'm 40" to pay the bills. And I was really intrigued by [music] computer science. So, I signed up. There was a fork in the road for me. My first job was an engineer. I wrote code. Many people don't know that. Then I led an R&D team. Then I moved from Tel Aviv to the US to start my first company, ClickSoftware. It's now part of Salesforce. And I became the CEO of a company called Sisense in business intelligence. We're growing pretty fast and then all of a sudden we had a quarter that wasn't great at all. I've no idea what was going on. We're analyzing a lot of data from the CRM that everybody says, "Oh, this is the way to manage customers. It's a single source of truth." There was nothing there. It actually relies on people telling it [music] what happened and that didn't make sense. So, only 1% of the information ever [music] actually makes its way to the CRM. It's all in people's heads. Now, what happens at the companies, only half the sales people are making their numbers. Nine out of 10 opportunities are not won without the company ever knowing why. And I thought, "Wow, this just totally doesn't make sense." Like there was the year that AI was already beating the world champion in Go. You remember like AlphaGo and DeepMind. And [music] the thought was, "Can we create like a system that will relieve people from the needs to update CRM?" That was the idea that when I left Sisense, I thought, "Hey, maybe we could build a company around that." The idea was like an autonomous system that automatically captures context from conversations and uses AI to turn it both to insight and in action. Are you using like a meeting assistant today? We invented this. This was from my background in the music industry is first. If we capture a meeting, meetings that we have usually have like multiple people, but we didn't want people to listen to like 45-minute meetings, right? We wanted them like hear like the interesting points out there. So, things like markers, topics. Today is pretty standard, but that did not exist. So, we have first drew and I plagiarized a little bit from SoundCloud. There was that the play buttons and where we put in and you have those like tracks. If you use like GarageBand or something, you'll see like there's a drum, guitar, bass, right? So, if you look at Gong, you'll see those tracks. All the concept like listen-to-talk ratio. It is the first application that was like measuring how much you're listening versus talking. How it tracks competitors. We invented this thing. That was pretty pretty innovative. And we went to raise [music] money. I said, "Let's start a company." I was pretty sure it's going to be a walk in the park, but it was [music] a far cry from that. It was like very frustrating and almost nobody wanted to invest in us. They obviously took a meeting and like another meeting and what about this and what about that? And people thought that sellers are going to hate Gong because they're going to see it as a big brother. Google and Amazon are going to own this space. That the technology is not there. They could When we started like AI was nowhere near where it is right now. So, it was it was a hard job. So, we struggled to raise money, but finally we found like a couple investors that gave us the money and that allowed us to start the company and it was pretty smooth from that point on.
</details>

### 逆境中的资本配置与“爬坡突袭”战术

在 2023 年，经历过疫情期间的爆发式增长后，行业迎来了“增长宿醉期”（Hangover: 指泡沫破裂或高速增长后的调整期）。由于客户过度招聘及面临财务压力，Gong 的客户流失率大幅攀升。同时，一些竞争对手通过收购整合了数个同类产品，并向客户推销“多合一”廉价套餐。尽管这些整合产品的质量并不尽如人意，但在当时预算吃紧的情况下，客户往往只盯着财务表格做采购决策。这导致 Gong 在 2023 年的增速显著放缓。

面对这一危机，Gong 并没有陷入绝境。他们此前储备的充足资金（虽然融了很多钱，但几乎未动用）提供了巨大的心理底气和执行力。当所有竞争对手都在因财务压力而挣扎时，Gong 决定反其道而行之，**踩下研发的油门**。

在资金流向的优先级上，Amit 坚持将资金花在人才与工程研发上，而非昂贵的实体办公室上。他回忆起 1999 年时，公司曾花费数百万美元租用了一间充斥着钢筋和空塑料袋、堆满闲置桌椅的奢华办公室，这让他至今感到心有余悸。因此，Gong 长期只签署 2 到 3 年的短期办公室租约，并从成立第一天起就广泛使用 WeWork 灵活办公空间，从而避免了因企业快速扩张而空间不足、或因业务停滞而被长期租约深度套牢的风险。

在省下非必要开支后，Gong 集中火力研发了两个新产品（使产品线扩展到四个），实现了反向的业务整合。Amit 借用了业余自行车运动的逻辑：在艰难的爬坡路段，当每个人都筋疲力尽、大口喘气时，如果你还有能力加速并发动突袭（Attack），那么你的对手在心理上就会彻底崩溃并放弃抵抗。通过在行业寒冬中加大研发投入，当市场回慢并开始复苏时，那些曾经廉价打包的竞争对手已经被远远甩在身后。

<details>
<summary>Original English Source</summary>
We did have like a rough patch in 2023 because that was the post-COVID growth, right? The hangover. A lot of our customers have over-hired people and got into financial stress. So, we saw like higher churn. We also had competition that went in and and bought like a a bunch of competing products and they're going to our customers and consolidating. They said, "Oh, we're going to do like all three or four products in one." The products were not very good, but at that time customers were just looking at a spreadsheet and said, "Okay, like yeah, one, two, three." And so, our growth slowed down substantially in '23. I wouldn't say existential, but it was definitely like not not fun days. So, we raised a lot of money, but we barely touched it. We just saved it for if and when we're going to need that. So, that gave us a lot of confidence and and the ability to execute. And we knew that if we struggle right now, all of our competition's struggling. ... So, what do you do? We step on the gas pedal, right? So, we know that everybody's going to struggle. We have the cash and we're going to invest in engineering. I'd much rather invest in people and engineering than than in office space. Cuz like I remember like in '99, I was stuck with like an office that was like all like steel and plastic bags all the area and chairs and like, you know, millions of dollars. It was like giving goosebumps even to watch it and say like, "Why did we do that?" I mean, we we we spent money on real estate and not on people, all right? Is there anything that I could have done, right, that would have like changed the outcome? So, we only do like two to three-year leases, right? I think for now, for the first time we did like a four-year lease in an office, but generally we've been in WeWork at WeWorks like since day one and we still are. Offices like either they're too small, you grow so fast that they need to move out, or if you don't grow, then you're stuck now with a lot of space. So, we built like two more products. Now we are in about four. Then we started like consolidating and now they're they're behind. I'm an amateur cyclist. When you're climbing, right, you know, everybody's exhausted, then you attack, right? You just give it like all your energy. Just psychologically it breaks your If you're good, right, if you're able to accelerate, then everybody just gives up because they know that they're barely breathing and now you're charging ahead. And that's exactly what we did.
</details>

### 品类设计与“复活节寻宝式”的早期市场竞争

对于创业公司而言，在市场切入路径上面临着两种选择：一是**加入既有品类**，其优势在于市场已被验证、客户预算已经存在，你只需要证明自己为什么比对手更好；二是**定义新品类**，这虽然听起来极具诱惑力，但需要进行大量的客户教育，并且由于客户没有现成预算，难度极大。值得注意的是，单一的产品并不等于一个品类。只有当有多家公司在做类似的事情时，品类才真正诞生。因此，创业者应该从创造一个独特的产品开始，一旦取得成功，必然会吸引模仿者，这时品类才开始逐步成型。

在今天，以 Gong 为代表的“收入 AI”已成为企业采购的必备项，但在成立之初，市场上根本没有此类预算。面对当前由 AI 引发的行业狂热和噪音，Amit 建议创业者不要盲从竞争对手的动作。他引用了杰夫·贝佐斯（Jeff Bezos）的观点：绝大多数人口头上说自己“以客户为中心”，但实际上他们是由“竞争对手驱动”的。他们总是盯着对手做了什么，然后试图跟风并做得更好。

在 AI 行业的早期阶段，市场并非零和博弈。竞争更应该像是一场**复活节寻宝**（Easter Egg Hunt: 指在广阔空间里各自寻找隐藏机会的非直接冲突竞争模式），而不是相互盯防的橄榄球比赛。在充满无限可能的新兴市场中，没必要盯着竞争对手的动作一味模仿或针对性升级，而应该走不同的方向，去寻找其他未被发现的“彩蛋”。

<details>
<summary>Original English Source</summary>
There are two choices. Is there a join an existing category? Let's say the advantage it's already established, people are buying and you just need to explain why you're better. There's already budget for this. Starting categories like uh is very compelling people. Oh, I'm going to start like a whole new category of of music or whatever, right? It's also hard because people don't have budget, they don't know how to think about it. So, there's a lot of education and if you want to be precise, you can start a category. Categories by definition like a number of companies doing the same thing. If it's just you, you're not a category, you're a unique product. So, you start by creating a unique product. If you're If you're not successful, then nothing happens. If you're successful, it's guaranteed that other will try to like either copy or do something better than you or like something different. That's when you start to have a category. It does take time. Today Gong is considered or something like Gong, revenue AI, most companies say we need that, but it wasn't like a must have when we started. Like people had to find budget for it, it didn't exist, right? It wasn't like a CRM or a contact database. [music] So, creating a category sounds very exciting and I'm I've no regrets, but if you're an entrepreneur, don't just think that oh, I need to start like a new category. ... If you're in an early market, which we are right now in AI, there are so many possibilities, why would you like try to like one up a competitor, [music] right? Just try to go like in a different direction and there are so many options. It could be like way better. I'm stealing from Jeff Bezos, right? Who said it like and most people say they're obsessed with customer, they're not. They're really competitor-driven. They look, "Oh, they did this. I'm going to do that, too. And I'm going to do better, right?" That's the wrong thing. ... Competition should be more like like an Easter egg hunt than like a football match that you're you got to match like every play that the other opponent is doing. It's not a zero-sum game like in in the early stages. Just They're They're more Just just go and keep looking. Why don't go where all the other kids are going.
</details>

### “氛围编程”的幻象与 B2B 销售的非对称博弈

当前，许多投资者担心在 AI 强大的生产力加持下，任何人都可以凭借“氛围编程”（Vibe Coding: 指完全依靠 AI 辅助，仅用简单指令便能生成代码的非传统软件开发方式）快速拼凑出软件，进而质疑软件公司是否还拥有壁垒。Amit 认为这种担忧被严重夸大了。

编写代码只是软件公司运营中极小的一部分。一个真正的软件企业还需要解决**部署上线**、**安全漏洞修补**、**依赖库管理**以及**全天候生产环境保障**（24/7 Production Support: 保证线上系统不间断运行的技术服务）等极其复杂的工程细节。即使将 Salesforce 的全部源代码开源到网上，普通人也根本无法与其直接竞争，因为企业级 CRM 和 HR 系统的底层复杂性超乎想象，根本无法单靠百人工程师团队在短时间内通过“氛围编程”重构出来。

此外，在 B2B 销售场景中，博弈过程充斥着极强的信息不对称性。买家在面对销售人员时，往往不会全盘托出真实情况，甚至会刻意隐瞒。例如，买家可能会声称“我们没有这笔预算”，或者在自己并非最终决定者的情况下宣称“我可以全权做主”；或者在暗中考察竞争对手时保持沉默。这种非对称沟通意味着 AI 必须具备极高水准的上下文推理和数据理解能力才能有效工作。

更深层挑战在于，大型 B2B 交易是多对多的复杂关系网络。评估其中的政治权力结构和人际博弈，并非是擅长“追求合理性”的 AI 所能解决的。AI 习惯于根据训练数据输出最平庸、符合逻辑的结果；但在实际的复杂商业谈判中，一些看似违背常理、极具创意的出牌方式，往往才是赢得订单的奇招。这种对于模糊性的判断力与创造力，构成了人类销售人员的核心竞争力。

<details>
<summary>Original English Source</summary>
The noise that's happening right now with AI, I know it's very confusing. Just just make a bet and just keep going. Ignore the noise. Right now, people are very emotional. It's almost like when, you know, people fall in love with someone that, you know, it's more like the hormones thinking versus like the brain. The dust will settle. At some point, it'll be clearer. So, if you have a direction, hopefully it's good, just keep going, keep plowing, do your own thing. Look a little bit like to what's going on, but don't be enamored with like things around you. If I have to distill it to one, this is it. Like, who do you cater to and what do you offer? Let's say it's apocalypse. There's some truth in that, but it's like a way like overreaction of the market. Right now, it's like investors are worried like if AI's has this like power of God, anybody can do software. So, what what is the moat? It's a natural question, but it's way way exaggerated cuz most companies will probably like open source their code and it will still be difficult for someone to compete with them. The code is just a part. What about like running it? Like there's like security vulnerability that you need to patch, a package, a library. Like who do you call it like 00 a.m.? Just writing the code is one part of a software company, but actually like running it, right, and supporting production, driving adoption is extremely hard. So, even if like where their salesforce's like code was out there on the internet, it would still be difficult for anybody to compete with them. CRM and HR are incredibly complex, right? People just underestimate it. They think, you know, you can't vibe code it like uh even like with 100 engineers or otherwise, why are we not seeing one right now? Why are we not seeing like a competitor? We have to understand that sales is asymmetrical engagement. So, buyers don't necessarily tell you everything. They might even lie to you. I don't have a budget, all right? Or I am the decision maker, even though you're not. We're looking at a few of our competitors. They might not tell you what they are, and they might not be looking at anything. So, this is like already like AI needs to have like excellent context or data, right? When you negotiate, like you want to lower the price, you want to increase the price. So, that's like uh one thing. Second, at least for us, like we help mostly with B2B sales, which is complex. It's like multiple people selling to multiple people. Understanding the power dynamics, the political power structure, all of that is something that AI will struggle. Ambiguity is not where it's good. Reading the room and judgment, creativity, right? AI is very straightforward. It's trained on um being plausible. Sometimes the creative moves aren't the ones that are plausible. It's just doing something like that seems unreasonable, but still like um a winning place.
</details>

### 自动驾驶演进框架与多曲线增长模型

Gong 将自身的产品演进路径比作特斯拉的**自动驾驶系统**（Self-Driving System: 能够实现部分或全部自主驾驶能力的软硬件架构）。自动驾驶分为五个层级（L1 为简单的车道保持辅助，L5 为全自动驾驶），而 Gong 同样定义了销售管理的自主演进框架。

要实现这个自主系统，企业需要构建三大核心模块：
1. **数据传感器（Sensors）**: 类似于车辆上的雷达、激光雷达和摄像头，用于无死角捕捉客户沟通的原始数据（在 Gong 中即为“收入图谱”）。
2. **AI 理解层**: 对捕获的信号进行语义解析。当红灯闪烁时，需要判断它是红绿灯、汽车尾灯还是摩托车，并识别其是在加速还是减速。
3. **应用交互层（Application Layer）**: 在解析数据的基础上，为销售团队提供可落地的执行工具和策略指导。

在 2017 年，Gong 大致处于 L1 阶段，尽管当时激光雷达等设备尚不普及、AI 算力也不足，但 Gong 预先搭建了底层框架，使得后续的技术成熟后可以直接无缝接入。

对于寻求持续增长的企业来说，外部看到的平滑上涨曲线在内部其实是由多条 **S型增长曲线**（S-Curve: 描述技术或产品生命周期中，起步慢、爆发快、后期饱和的S型轨迹）叠加而成的。任何单一产品在发展到一定阶段后都会触碰玻璃天花板，导致增速放缓。因此，优秀的管理者必须提前 2 到 3 年开始布局和叠加新的产品线（从最初的一个主产品演进到如今的四个核心产品），因为当你真正意图去寻找新增长点时，往往已经为时已晚。

Gong 的第一运营原则是培育**狂热粉丝**（Raving Fans: 极其忠诚并会主动为品牌宣传的用户），这需要产品在基础的价值与体验上持续给客户带来超出预期的惊喜（就像一把椅子在人坐上去时能主动开始提供合适温度的按摩服务一样）。为此，Gong 聚焦于两大北极星指标：一是通过消除 CRM 手动更新、预测以及零散数据筛选等无意义的行政消耗，帮助销售人员砍掉 75% 的非生产性时间；二是在他们与客户深度沟通时，提供实时的战术辅导。产品必须以超预期的价值让原本心怀疑虑的用户发出“Wow”的惊叹，从而支撑起多业务增长曲线的层叠攀升。

<details>
<summary>Original English Source</summary>
When you're alone, like nobody cares. Once you're your head, there's a crosshair on your back. So, everybody wants to kill you, right? And that's like we take it as a compliment. We've built the system over 10 years, and and again, it's there there's a lot of complexity. Our vision was we thought of it as a self-driving car, right? So, when we started Gong, we wanted to build an autonomous system. Our inspiration was a was a Tesla. Self-driving car like five levels. Five is like full self-driving, and one is getting like lane keeping alerts. And we thought, if you want to build a self-driving car, and this is a self-managing customer management system, you need three things. First, you need the sensors to capture all the data. In a car, it'll be the radars, the lidar, cameras. So, this is our revenue graph. Second, you need to make sense of all of it, right? So, you see like a red light blinking. Is it a traffic light or is it a car or motorcycle? Is it accelerating or decelerating, right? So, this is like the AI level. And then there is the application layer. So, we always thought about like the five levels. And we said, "Okay, today we're like 2017, we're like at level one, right? And when can we get to level five?" So, we built even though something like a lidar didn't exist or the AI wasn't strong enough to be full self-driving. So, we built the framework so we can plug in like the technologies as they mature. ... At Gong, we have our number one operating principle of raving fans. We're not happy with just happy customers. Happy is like, yeah, I could be happy with a with a chair, right? That's not. We want something people talk about that is a level above, right? What if I sit on the chair, like here in the kitchen, and all of a sudden it starts to give me like a back rub, and it just at the temperature of What just happened here? Right? I mean, that's you get people to talk about it, and it surprises you for the better. It does something that you don't don't expect. You got to understand your mission is not feature or AI or all of that. That's like what people buy. That's what they ultimately want to accomplish. First, we focus on value, not just features. So, we say, "What does it do?" So, we have like two things that that Gong will try to do. First, like 75% of a seller's time is non-productive, all right? It's like updating CRM, it's like doing forecast, doing training, doing like sifting through a list. So, what can we remove out of that? Second, [music] when they're with talking with customers, how do we help them be better on their job? So, these are the two North Star metric. People move from like somewhat reluctant to use it like, "Ah, is it like invasive?" They go, "Oh, wow, like she just did that, right?" So, you get that that wow all the time and the product surprises you in what it does and it needs to work well and it needs to be above what you expect. ... From the outside, when you see a company growing, right? It looks like this. But from the inside, there are multiple revenue sources, right? And you need to layer them in a way that it looks smooth from the outside, but each one is kind of like S-shaped, right? At some point it'll hit the glass ceiling. You know, you asked me about the people getting stuck because you're you're doing one thing and and that's it. Like it's not it's not growing as fast anymore. So, you always need to layer those things. You need to think about like two or three years in advance cuz when you realize that you need it, like it's already too late. >> Mhm.
</details>