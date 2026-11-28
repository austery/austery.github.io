---
author: House of El - AI
date: '2026-05-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ms6P8b1cM9M
speaker: House of El - AI
tags:
  - physical-ai
  - sensor-data
  - iot-deployment
  - simulation-gap
  - incentive-alignment
title: AI数据瓶颈的真相：基础设施而非质量问题
summary: 一篇《财富》文章指出AI模型正因劣质数据而“窒息”，但本文认为这忽视了核心问题。物理AI面临的数据挑战源于缺乏大规模的真实世界传感器基础设施，而非数据标注质量。物联网传感器市场正经历爆发式增长，但在激励错位下，其部署速度仍受限。文章通过智能建筑、医疗保健及特斯拉的案例，强调传感器部署需以解决实际、即时问题为驱动，将AI训练潜力作为副产品，从而构建可持续的数据飞轮。最终，物理AI的未来属于那些掌握领域特定传感器基础设施的公司，而非依赖模拟或单纯追求数据标注质量的通用AI实验室。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Google
  - Tesla
  - Fitbit
  - Anthropic
  - Waymo
  - Cruise
  - Scale AI
products_models:
  - Sora
  - ChatGPT
  - Claude
media_books:
  - Fortune
  - Wall Street Journal
  - TechCrunch
  - MIT Technology Review
status: evergreen
---
### AI数据瓶颈的真实剖析：基础设施的缺失

《财富》杂志近日发表文章，声称人工智能模型正因“劣质数据”而“窒息”。该文观点认为，数据标注公司正向市场大量注入低质量的训练材料，这导致机器人、自动驾驶汽车等理解真实世界的物理AI系统陷入停滞。他们援引OpenAI关闭Sora项目为例证，指出其世界模型未能正确理解物理世界，最终因自身问题而崩溃。然而，本文认为这种解读完全错误地理解了实际情况。我们面临的并非数据质量危机，而是**基础设施的差距**（Infrastructure Gap），这一区别对于未来的发展至关重要。

“人工智能”是一个极度宽泛的领域，如同“医学”一词，涵盖了无数用例和分支，将其笼统概括反而模糊了其本质。文本AI，如ChatGPT、Claude等**大型语言模型**（Large Language Models），能够利用现有的**人类行为数据**（Human Behavior Data）进行自由创作。互联网上充斥着数十亿计的文字，这些Reddit帖子、维基百科文章、新闻网站、书籍和研究论文等，构成了巨大的**预训练语料库**（Pre-existing Training Corpus），其生成成本几乎为零，因为是人类在日常生活中表达自我的产物。

<details>
<summary>Original English</summary>

Fortune just published a piece arguing AI models are choking on drunk data. The thesis is simple. Data labeling companies are flooding the market with low-quality training material in physical AI that would be robots, self-driving cars, systems that understand the real world is grinding to a halt because of it. They point to OpenAI shutting down Sora as evidence. Their world model couldn't grasp physics properly, so the whole thing collapsed under its own weight. I think this completely misframes what's actually happening. I'm L, I have a PhD in computer science, and I analyze AI developments to understand what's actually happening beneath all of the hype because here's what the drunk data narrative gets wrong. We didn't hit a data quality wall. We hit an infrastructure gap, and the difference matters enormously for what happens next. Let me explain what I mean. When people say AI, they're collapsing an insanely broad field into a single word. It's like saying medicine. There are a bazillion use cases and branches, and lumping them all together obscures more than it clarifies. Text-based AI, your ChatGPTs, Claude's, your large language models, could free write on existing human behavior. People were already writing online, billions of words sitting there in various languages ready to be scraped. Reddit posts, Wikipedia articles, news sites, books, research papers, you name it. The internet was a massive pre-existing training corpus that cost exactly zero dollars to generate because humans made it by just existing and expressing themselves.
</details>

### 物理AI的独特数据挑战与传感器需求

然而，**物理AI**（Physical AI）面临的问题截然不同。试想，一个机器人需要了解什么才能叠一件衬衫？它必须理解：
*   施加多少力能让布料移动而不撕裂。
*   重力如何影响不同材料（例如丝绸与牛仔布的垂坠方式不同）。
*   捏住布料边缘时，布料的褶皱行为。
*   从多个角度识别“叠”的视觉形态。
这些信息并非能从维基百科文章中抓取，而是亟需**传感器数据**（Sensor Data）的支撑。

机器人需要理解物体在空间中的运动规律。自动驾驶汽车则需掌握在湿沥青、干燥混凝土或碎石路面上以特定速度刹车时的不同反应。**世界模型**（World Models）需要领会弹性、摩擦力、动量、光线在夜间透过雨水打湿的挡风玻璃如何折射——即整个现实世界的物理引擎。然而，这种数据目前尚未大规模存在，因为它要求**主动仪器化**（Active Instrumentation）。我们需要各类传感器：
*   温度传感器，测量材料热膨胀。
*   运动传感器，跟踪三维移动。
*   压力传感器，检测机器人抓手接触物体时的力分布。
*   带深度感知的摄像头，计算距离。
*   加速度计，测量速度变化。
*   陀螺仪，跟踪空间中的方向。
我们需要在数百万种不同场景和极端情况下，持续、实时地测量物理世界，而目前我们尚未达到这一水平。

<details>
<summary>Original English</summary>

Physical AI is a completely different problem. Think about what a robot actually needs to know to fold a shirt. It needs to understand how much force to apply so the fabric moves but doesn't tear, how gravity affects different materials. Silk drapes differently than denim, it's example. How the fabric's edges behave when you pinch them, what fold it even looks like from multiple angles. This is not information you can scrape from a Wikipedia article. You need sensor data. Robots need to understand how objects move through space. Autonomous vehicles need to know what happens when you brake on wet asphalt at 40 mph versus dry concrete versus gravel. World models need to grasp elasticity, friction, momentum, how light refracts through rain on a windshield at night, the entire physics engine of reality. And here's the thing, that data doesn't exist at scale yet because it requires active instrumentation. We need sensors. Temperature sensors measuring thermal expansion of materials, motion sensors tracking three-dimensional movement, pressure sensors detecting force distribution when a robotic gripper touches something, cameras with depth perception calculating distances, accelerometers measuring changes in velocity, gyroscopes tracking orientation in space. You need to actually measure the physical world in real-time, continuously, across millions of different scenarios and edge cases, and we are just not there yet.
</details>

### 物联网传感器市场：基础设施部署的潜力

即便如此，物联网（IoT）传感器市场仍展现出惊人的增长态势。**物联网**（Internet of Things: 连接到网络并发送数据的物理传感器）传感器市场在2024年估值为183.4亿美元，预计到2034年将飙升至4221.3亿美元，年复合增长率高达37%。这预示着巨大的市场潜力。截至2025年末，全球已部署约211亿台物联网设备，这意味着全球平均每人拥有大约三个传感器。这些设备涵盖：
*   建筑内的温度监测器
*   追踪心率的可穿戴设备
*   优化工厂车间的运动传感器
*   工业设备中的压力传感器
*   药品储存中的湿度传感器
*   调节建筑照明的光传感器
仅北美地区，物联网传感器市场预计将从2025年的85.2亿美元增长到2034年的1360.6亿美元。其中，运动传感器是增长最快的细分市场，年增长率达到15.8%，主要得益于**智能建筑**（Smart Buildings）为优化能源利用和减少浪费而对空间使用情况的洞察需求。这清晰表明，真正的基础设施正在大规模部署。

<details>
<summary>Original English</summary>

Now, before you think that I'm being pessimistic, let me show you what's actually going on beneath the surface. The IoT sensor market, that's Internet of Things, basically any physical sensor that connects to a network and sends data somewhere, was valued at 18.34 billion dollars in 2024, projected to hit 422.13 billion dollars by 2034, growing at a compound annual rate of about 37%. That is enormous growth. As of the end of 2025, there are about 21.1 billion IoT devices deployed worldwide. For context, that's roughly three sensors for every person on the planet, we're talking about temperature monitors in buildings, wearables tracking your heart rate, motion sensors optimizing factory floors, pressure sensors in industrial equipment, humidity sensors in pharmaceutical storage, light sensors adjusting building illumination, stuff like that. In North America alone, the IoT sensor market is expected to grow from 8.52 billion dollars in 2025 to 136.06 billion dollars by 2034. The fastest growing segment is motion sensors, expanding at 15.8% annually, driven by smart buildings trying to understand how spaces are actually being used so they can optimize energy and reduce waste. This is real infrastructure being deployed at scale.
</details>

### 激励错位：物理AI部署的经济与社会瓶颈

然而，一个关键问题是：为什么物联网的增长速度还不够快？如果传感器数据是下一波AI发展的瓶颈，为何我们未见到如“曼哈顿计划”般大规模的传感器部署投资？我认为，瓶颈并非技术，而是**激励错位**（Incentive Alignment）。一项技术若要大规模部署，必有人愿意为其买单。
*   文本AI的部署成本几乎为零，因为互联网已然存在。OpenAI和Google等公司只需构建数据抓取和训练系统。
*   然而，**物联网传感器部署**（IoT Sensor Deployment）则需前期资本投入，回报周期较长。这涉及传感器的制造、安装、维护，以及构建数据收集和处理的基础设施。

问题在于，物联网传感器的部署不像大型语言模型那样“性感”。从融资角度看，2024年的风险投资家更倾向于投资一家能编写代码、进行哲学讨论、具有病毒式传播潜力、且消费者吸引力明确的对话式AI公司，而非一家在商业建筑中安装温湿度传感器以优化暖通空调（HVAC）系统的公司。前者能轻松占据头条，引发科技媒体和社交媒体热议；后者虽是至关重要的基础设施，却显得“无趣”。你无法与建筑的HVAC系统对话，也无压力传感器为你写诗的病毒式演示。因此，物联网获得的资金、宣传和关注相对较少，尽管它对于下一波AI发展可能比另一个聊天机器人更为基础。

<details>
<summary>Original English</summary>

But here's the critical question. Why isn't it growing even faster? If sensor data is the bottleneck for the next wave of AI, why aren't we seeing Manhattan project levels of investment in sensor deployment? I think the bottleneck isn't technical, it's incentive alignment. Let me break down what I mean by that. When a technology gets deployed at massive scale, it's because someone sees a reason to pay for it. With text-based AI, the deployment was basically free. The internet already existed. Companies like OpenAI and Google just needed to build a scraping infrastructure and training systems, but IoT sensor deployment requires upfront capital investment with delayed returns. You need to manufacture sensors, install them, maintain them, build the data infrastructure to collect and process what they're measuring. And here's the problem, IoT sensor deployment isn't sexy like large language models. Just think about it from a funding perspective. If you're a venture capitalist in 2024, would you rather invest in A, a company building conversational AI that can write code and have philosophical discussions with viral demo potential and clear consumer appeal or B, a company installing temperature and humidity sensors in commercial buildings to optimize HVAC systems. One of these makes headlines, one of these gets TechCrunch articles and Twitter buzz, the other is infrastructure, critically important but kind of boring. You can't have a conversation with your building's HVAC system. There is no viral demo where a pressure sensor writes you a poem. So, IoT gets less funding, less hype, less attention, even though it is arguably more foundational for the next wave of AI development than yet another chatbot.
</details>

### 用户采纳：直接价值驱动下的传感器部署

另一个关键问题是，如果没有看到清晰、直接的利益，人们不会主动选择接受**普遍监控**（Ubiquitous Monitoring）。试想，如果有人告诉你：“我们想在你家里安装传感器，监测温度、入住情况、能源使用和活动模式。”你的第一反应会是：“为什么？我能从中得到什么好处？”若我的回答是：“嗯，这些数据最终可能有助于训练更好的AI模型。”你很可能会让我离开，而且这是理所当然的。价值主张必须是**直接且即时**（Direct and Immediate）的，而非抽象和面向未来的。

但如果我改口说：“这些传感器将通过自动优化供暖和制冷运行时间，使你的电费减少28%。”这样是不是更有吸引力？这不是假设。一所大学在校园内全面部署了**智能建筑传感器**（Smart Building Sensors），并记录到校园能源使用强度降低了28%，相当于每年节省了31万美元的公用事业费用。该系统还成功识别了六个空气处理装置的轴承退化，避免了估计高达28万美元的紧急维修费用。

<details>
<summary>Original English</summary>

And here's the other problem. People won't opt into ubiquitous monitoring without seeing clear, immediate benefits. Think about it from a user perspective. If I told you, "Hey, we want to put sensors all over your house to monitor temperature, occupancy, energy usage, movement patterns." Your first question would be, "Why? What's in it for me?" And my answer is, "Well, eventually this data might help train better AI models." You tell me to get lost, rightfully so. The value proposition has to be direct and immediate, not abstract and future-oriented. But what if instead I said, "These sensors will cut your electricity bill by 28% by automatically optimizing when your heating and cooling run?" Now we're talking, right? It's not hypothetical. A university deployed smart building sensors across their campus and documented a 28% reduction campus energy use intensity, equivalent to 310,000 US dollars in annual utility savings. The system also identified bearing degradation on six air handling units, preventing failures estimated to have cost 280,000 in emergency repairs.
</details>

### 智能建筑与医疗健康：传感器价值的体现

**智能建筑**（Smart Buildings）的运作机制具有深远意义。传统的建筑暖通空调（HVAC）系统按固定时间表运行，无论是否有人，都会在早上6点开启，晚上6点关闭。而物联网传感器通过运动和二氧化碳传感器实时监测占用情况。系统能够“学习”到会议室3B只在周二和周四下午使用，因此在一周的其余时间不会加热该房间。温度传感器会检测空间是否已达到目标温度，从而避免过度供暖或制冷造成的能源浪费。建筑变得智能响应，而非依赖僵化的定时器。能源节约是真实且立竿见影的，本月的公用事业账单就会有所体现。这种清晰的价值主张，才能真正吸引人们选择加入。

再看医疗健康领域。Google和Fitbit推出了**Device Connect**，该平台允许医院将可穿戴设备数据直接整合到电子健康记录中。其核心宣传点并非“请帮助我们训练更好的AI”，而是“实现实时心脏监测，使医生能够在紧急情况发生前发现心律失常”。研究表明，医生在常规初级保健访视中监测Fitbit数据在后勤上是可行的，并且患者在获得个性化建议和早期干预时，积极愿意与医疗服务提供者分享运动和健康数据。这就是构建基础设施的方式，不是通过对AI理解物理世界的大声宣告，而是通过部署**狭窄且高价值的应用**（Narrow, High-Value Applications）来证明仪器设备的成本是合理的。

<details>
<summary>Original English</summary>

Here's how that actually works because the mechanism is super important. Traditional buildings run HVAC systems on fixed schedules. Heat turns on at 6:00 a.m., off at 6:00 p.m. regardless of whether anyone is actually in the building. With IoT sensors, you're measuring occupancy in real time using motion and CO2 sensors. The system essentially learns conference room 3B is only used Tuesday and Thursday afternoons, so it doesn't heat that room for the rest of the week. Fair enough. Temperature sensors detect when a space is already at the target temperature, so the system doesn't waste extra energy over shooting. The building becomes responsive instead of running on dumb timers. The energy savings are real and immediate. Your utility bill goes down this month. That is the value proposition that gets people to opt in. Or take health care. Google and Fitbit launched Device Connect, which allows hospitals to integrate wearable data directly into electronic health records. The pitch is not, "Please help us train better AI." The pitch is, "Enable real-time cardiac monitoring so your doctor can catch arrhythmias before they become emergencies." Studies show that physician monitoring of Fitbit data embedded in routine primary care visits is logistically feasible, and patients are actively interested in sharing exercise and health data with their providers when it leads to personalized recommendations and early intervention. This is how you build the infrastructure, not by making grand proclamations about AI that understands the physical world, but by deploying narrow, high-value applications that justify the cost of instrumentation.
</details>

### 数据飞轮效应：以解决问题为导向的传感器价值链

每一次成功的部署都将启动一个**数据飞轮**（Data Flywheel）。传感器因解决特定问题而被部署，而其运行过程中产生的**数据**（Data）则成为副产品。这些数据进一步促成优化和新洞察的产生，从而证明在相邻领域部署更多传感器的合理性，进而生成更多数据，如此循环往复，形成复合效应。

以OpenAI的Sora项目为例，我认为《财富》杂志的诊断完全错误。Sora是OpenAI的文本到视频模型，其核心理念是用户输入如“一只金毛寻回犬在雪中玩耍”这样的提示，SSora便能生成逼真的视频。它不仅是一个视频生成器，更被定位为**世界模型**（World Model），旨在通过足够理解物理学来模拟物体运动、光线行为和材料相互作用。2025年末，Sora以高调姿态发布，迪士尼甚至承诺与其达成数十亿美元的合作，用户可以生成包含米奇老鼠或漫威角色的视频，Sora被誉为内容创作的未来。然而，六个月后，该项目便宣告关闭。

<details>
<summary>Original English</summary>

Each successful deployment creates a data flywheel. Sensors get deployed because they solve a specific problem. They generate data as a byproduct. That data enables better optimization and new insights, which justifies deploying more sensors in adjacent areas, which generates more data, and the cycle compounds. Let's talk about what happened to OpenAI's Sora for a second, because I think the Fortune piece gets the diagnostics exactly backwards. Sora was OpenAI's text-to-video model. The idea was basically you type a prompt like a golden retriever playing in the snow, what a cutie, and Sora generates a realistic video of that scenario. But it was not just a video generator, it was supposed to be a world model, a system that understands physics well enough to simulate how objects move, how light behaves, how materials interact. They launched it in late 2025 with a big splash, got Disney to commit to a billion-dollar partnership where users could generate videos featuring Mickey Mouse or Marvel characters, positioned it as the future of content creation. Six months later, they shut it down.
</details>

### Sora的失败：模拟的局限性而非数据质量

根据《华尔街日报》和TechCrunch的报道，Sora每天的计算成本高达约100万美元，甚至有估算认为，如果将所有基础设施成本计算在内，每天的开销可达1500万美元。用户增长在达到约100万人后迅速下滑至不足50万人。应用内购买的总收入在Sora的整个生命周期内估计仅为210万美元。简单来说，如果Sora每天烧掉100万美元，而总收入仅为210万美元，那么仅仅两天的运营成本就足以消耗掉其全部生命周期收入。其**单位经济效益**（Unit Economics: 指单一产品或服务的经济效益）灾难性地差，因此OpenAI选择终止项目。

然而，《财富》杂志的文章将此归咎于**劣质数据**（Junk Data）问题，认为Sora的世界模型因训练数据质量低劣而缺乏对物理学的充分理解，并暗示只要有更好的数据标注和模拟场景，Sora就能成功。我认为这种说法是“只见树木不见森林”。OpenAI试图通过模拟来理解物理世界。他们向模型输入**合成数据**（Synthetic Data），即计算机生成的物体坠落、弹跳、相互作用等场景。他们试图通过展示无数模拟交互的变体来教授物理学，但从根本上说，这并未奏效。这并非因为数据是劣质的，而是因为**模拟无法复制现实的复杂性**。

<details>
<summary>Original English</summary>

According to reporting from the Wall Street Journal and TechCrunch, Sora was burning through roughly $1 million per day in compute costs. Some estimates put it even higher. One analysis suggests around $15 million per day when you factor in all the infrastructure costs. User growth peaked at around a million people, then collapsed to fewer than 500,000. Revenue from in-app purchases totaled an estimated $2.1 million over the app's entire lifetime. Let me just put that into perspective. If Sora was burning a million dollars per day and only generated $2.1 million in total revenue, it would take 2 days of operating cost to consume the entire lifetime revenue. The unit economics were catastrophically bad and OpenAI pulled the plug. Now, here's where it gets interesting. The Fortune article frames this as a junk data problem. Their world model lacked sufficient understanding of physics because the training data was apparently low quality, and the implication is basically if only they had better data labeling, better simulated scenarios, Sora would have worked. I think that scenario is missing the forest for the trees. OpenAI tried to simulate their way to understanding the physical world. They fed the model synthetic data, computer-generated scenarios of object falling, bouncing, interacting, stuff like that. They tried to teach it physics by showing it endless variations of simulated interactions, and fundamentally it didn't work, not because the data was junk, but because simulations cannot replicate the complexity of reality.
</details>

### 模拟与现实的鸿沟（Sim-to-Real Gap）

模拟在这些情况下为何会失败？在计算机中模拟物理学，我们总是使用**近似值**（Approximations）。我们可以定义摩擦系数、弹性、空气阻力，但现实世界要混乱得多。一块布料的摩擦系数并非单一值，它取决于湿度、材料的磨损程度、接触表面的微观纹理，以及是否存在灰尘或油污等。一份机器人训练指南指出：“微观表面变化造成的摩擦力，使得在模拟中训练良好的机器人难以应对真实世界。”

再以水为例。模拟流体动力学计算成本高昂，且仍然无法捕捉到各种**边缘案例**（Edge Cases），例如表面张力在不同温度边界下的行为差异，或者肥皂分子如何改变流动模式。你可以无限接近真实，但仅仅“接近”不足以训练一个机器人洗碗，或者一个世界模型生成逼真的雨水视频。这就是所谓的**模拟与现实鸿沟**（Sim-to-Real Gap）。你可以在模拟中训练一个机器人在平坦地面上完美行走，但一旦它遇到真实世界的不规则情况——轻微不平的地面、意想不到的摩擦力变化、附近机器的振动——它就会摔倒。模拟无法让机器人为**现实世界的长尾效应**（Long Tail of Reality）做好准备。

<details>
<summary>Original English</summary>

Let me explain why simulation breaks down in these cases. When you simulate physics in a computer, you're always using approximations. You define coefficients for friction, elasticity, air resistance, but reality is a lot messier. A piece of fabric doesn't have one coefficient of friction. It depends on humidity, how worn the material is, the microscopic texture of the surface it's sliding across, whether there's dust or oil present, stuff like that. A robotics training guide notes, I'm quoting, "A microscopic surface variation creating friction can make the real world difficult for robots well trained in simulation." Or think about water, another example. Simulating fluid dynamics is computationally expensive and still doesn't capture edge cases, like surface [snorts] tension behaving differently at temperature boundaries, or how soap molecules change flow patterns. You can get close, but close isn't good enough when you're trying to train a robot to wash dishes or a world model to generate realistic videos of rain. This is called the sim-to-real gap. You can train a robot in simulation to walk perfectly on flat ground, but the moment it encounters real-world irregularities, slightly uneven floors, unexpected friction changes, vibrations from nearby machinery, it stumbles. The simulation doesn't prepare it for the long tail of reality.
</details>

### 特斯拉的真实世界数据飞轮：AI训练的典范

真正有效的是大规模的**真实世界数据收集**（Real-World Data Collection）。截至2026年2月，特斯拉的完全自动驾驶系统已累计记录了超过80亿英里（受监督驾驶里程），其车队每天从超过200万辆汽车生成1600亿帧视频。80亿英里是什么概念？如果你每天24小时以60英里/小时的速度驾驶，需要超过15000年才能积累如此多的驾驶经验。特斯拉的车队在短短几年内就完成了这一壮举。每一辆特斯拉汽车都是一个移动的传感器平台，持续不断地反馈真实世界的行为数据。

例如：
*   雾中的行人看起来是什么样子？
*   日落时分，阴影如何影响物体检测？
*   有人在单行道上逆行时会发生什么？
*   褪色、被雪覆盖或在新旧沥青上绘制的车道标记分别是什么样子？
特斯拉都知道，因为这些情况都真实发生过，并且它们的车辆都记录了下来。这就是特斯拉**数据飞轮**（Data Flywheel）的运作方式：

1.  **车队收集**（Fleet Collection）：每辆启用了摄像头的特斯拉汽车都在收集视频和遥测数据。其中大部分数据在本地被丢弃，因为特斯拉已经拥有数百万个晴朗天气下日常高速公路驾驶的例子。
2.  **影子模式**（Shadow Mode）：特斯拉同时运行两个系统：实际驾驶的自动驾驶系统和在影子模式下运行、只做预测但不控制汽车的实验模型。当影子模型与生产模型不一致或不确定时，该场景会被标记。
3.  **定向检索**（Targeted Retrieval）：特斯拉向特定车辆发送请求：“下次你遇到符合这些特定参数的场景时，上传视频。”这就是他们如何大规模收集极端案例的方式。他们不是随机采样，而是在积极寻找模型不确定或出错的场景。
4.  **人工标注**（Human Annotation）：棘手的场景会被发送给人工标注员，他们标注实际发生的情况。例如，“那是一个被邮箱部分遮挡的行人”、“那是一辆摩托车在车道之间穿行”、“那是路上的碎片，而不是静止的车辆。”
5.  **模型训练**（Model Training）：新的标注数据用于训练下一版本模型，然后通过**空中下载**（Over-The-Air）部署到整个车队。
6.  **持续验证**（Continuous Validation）：新模型运行后，特斯拉会在数百万英里的行驶中监控其实际性能和安全指标。如果性能下降，则回滚；如果性能更好，则成为新的生产基线。

<details>
<summary>Original English</summary>

You know what does work? Real-world data collection at scale. Tesla has logged over 8 billion miles driven on full self-driving supervised as of February 2026, their fleet generates 160 billion daily video frames from over 2 million vehicles. Let me put that into perspective for a second. 8 billion miles. If you drove 24 hours a day at 60 mph, it would take you over 15,000 years to accumulate that much driving experience. Tesla's fleet did it in a few years, so that is a remarkable achievement. Every single one of their vehicles is a rolling sensor platform continuously feeding data back about how the real world behaves. What does a pedestrian look like in fog? How do shadows affect object detection at sunset? What happens when someone drives the wrong way down a one-way street? What do lane markings look like when they're faded or covered in snow or painted on old asphalt versus new asphalt? Tesla knows because it happened and their fleet recorded it. Here's how their data flywheel actually works. Step one, fleet collection. Every Tesla on the road with cameras enabled is collecting video and telemetry. Most of this data is discarded locally. You don't need to upload footage of routine highway driving in clear weather because Tesla already has millions of examples of that. Step two, shadow mode. Tesla runs two systems simultaneously. The production autopilot system that's actually driving and experimental models running in shadow mode making predictions but not controlling the car. When the shadow model disagrees with the production model or when it's uncertain about something, that scenario gets flagged. Step three, targeted retrieval. Tesla sends a request to specific vehicles. Next time you encounter a scenario matching these specific parameters, upload the footage. This is how they collect edge cases at scale. They're not randomly sampling stuff. They're actively hunting for the scenarios where their models are uncertain or wrong. Step four, a super important one, human annotation. The tricky scenarios get sent to human labelers who annotate what's actually happening. That's a pedestrian partially occluded by a mailbox. That's a motorcycle lane splitting. That's a debris on the road, not a stationary vehicle. Step five, model training, the coolest part. The new label data goes into training the next version of the model, which then gets deployed over the air to the entire fleet. Step six, continuous validation. As the new model runs, Tesla monitors its real-world performance and safety metrics across millions of miles. If it performs worse, they roll back. If it performs better, it becomes the new production baseline.
</details>

### 数据护城河：传感器基础设施的战略地位

这才是真正的**数据护城河**（Data Moat），其优势并非源于更优的算法或更大的计算集群，而是源于：
*   **拥有传感器**。
*   **拥有数百万辆汽车组成的内置分发网络**。
*   **持续生成训练数据**。
令人深思的是，若无自身传感器基础设施，任何通用AI实验室都无法与之匹敌。Waymo拥有传感器，但其部署可能仅限于数千辆车，且运营区域有限。Cruise在停止运营前也曾拥有传感器。传统汽车制造商正努力构建传感器车队，但在数据积累和软件集成方面，它们已落后特斯拉多年。OpenAI、Google的AI部门、Anthropic——这些公司既不拥有汽车，也未能在物理世界大规模部署传感器基础设施。

那么，若无传感器基础设施，通用实验室该如何构建**物理AI**（Physical AI）？他们别无选择，只能进行模拟，而这正是其持续失败的根源。OpenAI曾试图模拟物理世界，为此每天烧掉100万美元，以极其昂贵的方式发现**摩擦力**（Friction）的存在。然而，他们之所以尝试模拟，是因为目前模拟的可扩展性远超真实世界数据收集。如果你需要1万个机器人拿起咖啡杯的例子，模拟可在几小时内生成。而在真实世界中，你需实际设置场景，让机器人运行1万次，同时祈祷没有故障。这既缓慢又昂贵。

<details>
<summary>Original English</summary>

This is the data moat, not necessarily better algorithms, not bigger compute clusters, owning the sensors and having a built-in distribution network of millions of cars continuously generating training data. And here's the thing that should make you pause. No generalist AI lab can compete with that without building their own sensor infrastructure. Waymo has sensors, but they're on maybe a few thousand vehicles operating in limited geographies. Cruise had sensors before they shut down operations. Traditional automakers are trying to build sensor fleets, but they're years behind Tesla in terms of data accumulation and software integration. OpenAI, Google's AI division, Anthropic, they don't own cars. They don't have sensor infrastructure deployed in the physical world at scale anywhere. So, what do you do if you're a generalist lab trying to build physical AI without sensor infrastructure? Well, you kind of have to simulate. Let me show you why that keeps failing. OpenAI tried to simulate the physical world and burned a million dollars a day doing it, which is an extraordinarily expensive way to discover that friction exists. But here's why they tried in the first place. Simulation is scalable in a way real-world data collection isn't right now. If you need 10,000 examples of a robot picking up a coffee mug, you can generate those in simulation in a few hours. In the real world, you need to physically set up the scenario, run the robot 10,000 times, and hope nothing breaks. It's slow and very expensive.
</details>

### 模拟的局限：无法精确捕捉现实细节

然而，模拟存在一个根本性问题：它只能教导模型你已编程到物理引擎中的内容。如果你没有考虑到：
*   咖啡杯把手可能因制造残留物而略带油腻。
*   陶瓷在不同温度下的行为差异。
那么，你的模拟就无法捕捉到这些细节。麻省理工科技评论报道，虚拟模拟可以训练机器人表演杂技，但无法训练它们抓取和移动物体，因为模拟难以精确建模物理学。

那么，机器人领域实际发生了什么？公司正转向大规模的**真实世界数据收集**（Real-World Data Collection），即使这既昂贵又缓慢，但他们别无选择。中国出现了培训中心，人们穿着外骨骼和虚拟现实设备，每天重复数百次相同的任务。尼日利亚、阿根廷和印度的零工正在拍摄自己在家做家务的视频。**Scale AI**及其他数据公司正招募大批人员，拍摄自己叠衣服、洗碗、整理货架的视频，以捕捉人类如何实际操作物体的混乱、多样的现实。2025年，投资者向**人形机器人**（Humanoid Robots）领域投入了超过60亿美元，其中很大一部分资金流向了**数据收集基础设施**（Data Collection Infrastructure），而非算法或计算能力。

<details>
<summary>Original English</summary>

But, simulation has a fundamental problem. It can only teach the model what you programmed into the physics engine. If you did not account for how coffee mug handles can be slightly oily from manufacturing residue, or how ceramic behaves differently at different temperatures, your simulation will just not capture that. MIT Technology Review reports that virtual simulations can train robots to perform acrobatics, but not how to grasp and move objects because simulations struggle to model physics with perfect accuracy. So, what's actually happening in robotics, right? Companies are pivoting to real-world data collection at scale, even though it's expensive and slow. They have to. There are now training centers in China where people wear exoskeletons and VR hardware while doing the same repetitive tasks hundreds of times per day. Gig workers in Nigeria, Argentina, and India are filming themselves doing chores at home. Scale AI and other data companies are recruiting armies of people to record themselves folding laundry, washing dishes, organizing shelves, capturing the messy, varied reality of how humans actually manipulate objects. Investors poured over $6 billion into humanoid robots in 2025, and a huge chunk of that money is going towards data collection infrastructure, not algorithms, not compute, data, the holy grail of computer science.
</details>

### 真实世界数据致胜：成功案例与模式

模式非常清晰：**真实世界数据**（Real-World Data）在任何时候都优于模拟，而真实世界数据需要**真实世界传感器**（Real-World Sensors）。那么，如果模拟行不通，我们如何才能真正大规模部署真实世界传感器呢？我们可以从当前的成功案例中寻找答案。

在制造业中，**工业物联网**（Industrial IoT）领域正以每年37.5%的速度增长。这得益于工厂部署传感器以实现**预测性维护**（Predictive Maintenance）。传感器不再按固定时间表更换零件，而是监测振动、温度和声学特征，预测机器何时可能发生故障。实践证明，这种部署能将维护成本降低25%，避免70%的停机时间。这带来了立竿见影的经济效益，从而立即证明传感器投资的合理性。此外，作为副产品，这些部署还生成了关于工业设备在压力下实际行为的**大规模数据集**（Massive Data Sets）。

<details>
<summary>Original English</summary>

The pattern is clear, isn't it? Real-world data beats simulation every single time. And real-world data requires real-world sensors. So, if simulation doesn't work, and you need real-world sensors, how do you actually get them deployed at scale? Look at what's working right now. In manufacturing, the industrial IoT segment is growing at 37.5% annually. Why? Because factories are deploying sensors for predictive maintenance. Instead of replacing parts on a fixed schedule, sensors monitor vibration, temperature, and acoustic signatures to predict when a machine is about to fail. Deployments demonstrate 25% maintenance cost savings and 70% downtime avoidance. That's real money saved immediately, which justifies the sensor investment immediately. As a byproduct, they're also generating massive data sets about how industrial equipment actually behaves under stress.
</details>

### 医疗与智慧城市：数据积累的价值

下一个用例是医疗健康。到2026年，全球将有超过3亿台可穿戴设备投入使用。其中大部分是带有心率监测器、加速度计以及日益普及的血氧传感器的健身追踪器和智能手表。**Google**和**Fitbit**的Device Connect集成允许这些数据流入**电子健康记录**（Electronic Health Records）。患者选择加入，是因为他们获得了持续的健康监测和早期干预。同时，作为副产品，医疗健康系统正在以前所未有的规模积累关于**人体生理学**（Human Physiology）的**数据集**（Data Sets）。

接下来是**智慧城市**（Smart Cities）。智慧城市占据全球物联网市场26%的份额。全球有600多个城市实施了物联网解决方案，用于交通管理、供水和垃圾收集。物联网驱动的交通灯和传感器已在美国145个城市投入运营，平均将交通拥堵减少了12%。城市部署这些传感器，是因为它们能够降低基础设施成本并提高生活质量。作为副产品，它们正在生成关于**城市动态**（Urban Dynamics）的实时数据，这些数据最终可用于训练管理城市基础设施的AI系统。

<details>
<summary>Original English</summary>

As a next use case, let's look at health care. Over 300 million wearable devices will be in use worldwide by 2026. Most of them fitness trackers and smartwatches with heart rate monitors, accelerometers, and increasingly blood oxygen sensors. Google and Fitbit's device connect integration allows this data to flow into electronic health records. Patients opt in because they get continuous health monitoring and early intervention. And as a byproduct, health care systems are accumulating data sets about human physiology at unprecedented scale. Next one, let's look at smart cities. Smart cities represent 26% of the global IoT market. That is a huge chunk. Over 600 cities worldwide have implemented IoT solutions for traffic management, water distribution, and waste collection. IoT powered traffic lights and sensors are operational in 145 US cities, reducing congestion by an average of 12%. Cities deploy these sensors because they reduce infrastructure costs and improve quality of life. As a byproduct, they're generating real-time data about urban dynamics that could eventually train AI systems managing city infrastructure.
</details>

### 激励对齐：解决实际问题以驱动数据积累

你是否注意到了这种模式？每一次部署都伴随着一个即时的**领域特定价值主张**（Domain-Specific Value Proposition），这正是基础设施投资的合理性所在。AI训练的潜力是次要的益处，而非主要的驱动因素。这就是我所说的**激励对齐**（Incentive Alignment）。你无法通过宣称“请部署这些传感器，它们总有一天会帮助训练更好的AI模型”来劝服城市。你必须通过告诉他们“这将减少交通拥堵，为您的居民每天通勤节省15分钟”来促使他们行动。数据的积累是解决实际问题所产生的必然结果。

我知道你们中有些人会认为：“这听起来像是一个**监控反乌托邦**（Surveillance Dystopia），到处都是传感器监控一切，并将数据输入AI系统。”我完全理解，而且我认为这种担忧绝对值得认真对待。确实存在一种普遍传感器部署是**剥削性**（Extractive）和**强制性**（Coercive）的版本。例如：
*   传感器跟踪你的行动以向广告商出售行为数据。
*   工作场所传感器监控上厕所时间以压榨员工更多生产力。
*   保险公司要求访问你的健康数据以调整保费。
这属于**对人的监控**（Monitoring of People），将人类视为提取价值的数据源。

<details>
<summary>Original English</summary>

Do you notice the pattern? Every deployment has an immediate domain-specific value proposition that justifies the infrastructure investment, the AI training potential is a secondary benefit, not the primary driver. This is what I mean by incentive alignment. You can't convince cities to deploy sensors by saying, "Please, this will help train better AI models someday." You convince them by saying, "This will reduce traffic congestion and save your residents 15 minutes per commute." The data accumulation happens as a consequence of solving real problems. Now, I know that some of you are thinking, "Al, this sounds like a surveillance dystopia, sensors everywhere monitoring everything feeding data into AI systems." I totally get it, and I think this tension is definitely worth taking seriously. There is a version of ubiquitous sensor deployment that's extractive and coercive. Sensors tracking your movements to sell behavioral data to advertisers, workplace sensors monitoring bathroom breaks to squeeze more productivity out of workers, insurance companies demanding access to your health data to adjust premiums. That's monitoring of people, treating humans as data sources to extract value from.
</details>

### 人本主义部署：为人类福祉服务

然而，还存在另一种版本。传感器可以减少你的电费，你每个月都能在水电账单上看到节省的费用。健康监测器可以在心脏病发作前捕捉到心律失常。建筑传感器可以优化空气质量，减少呼吸道疾病。这是**为人类服务**（Monitoring for People）的监控，技术被部署以促进人类的繁荣，这才是最好的技术。其区别不在于传感器本身，而在于：
*   **谁控制它们**。
*   **谁从数据中受益**。
*   **参与是否真正自愿且有明确的价值交换**。

我个人认为，未来的道路需要**透明度**（Transparency）。你应该始终知道你环境中存在哪些传感器，它们在测量什么，以及数据流向何处。**价值交换选择加入**（Opt-in with Value Exchange）：参与应该是自愿的，并且利益应该主要流向被监控的人，而不是某个随机的第三方。**隐私设计**（Privacy by Design）是必须的：数据应尽可能匿名化和聚合。数据处理应在数据离开设备之前在本地进行。你可以通过运动传感器测量建筑占用情况，而无需识别特定个人，这有相应的方法。**以人为本的部署**（Human-Centric Deployment）：问题不应该是“这些数据能支持哪些AI应用？”，而应该是“我们能为人们解决什么问题，而这些问题恰好能作为副产品生成有用的数据？”让我们一石二鸟。这些不仅仅是哲学上的细枝末节，它们是让人们大规模选择加入的实际要求。顺便说一句，我们仅凭存在就已经产生了大量数据。我们身体的热信号、电器使用方式、空间中的移动、电力消耗模式——我们只是没有系统地捕捉它们。问题不在于是否会产生数据，它已经发生了。问题在于我们是否以一种有利于数据生成者的方式来利用这些数据。

<details>
<summary>Original English</summary>

But, there is another version, my friends. Sensors that reduce your energy bill, and you can see the savings on your utility statement every month. Health monitors that catch cardiac arrhythmias before they become heart attacks, building sensors that optimize air quality and reduce respiratory illnesses. That is monitoring for people, technology deployed to improve human flourishing, the best kind of technology. The difference isn't the sensors themselves, it's who controls them, who benefits from the data, and whether participation is genuinely optional with clear value exchange. I personally think the path forward requires transparency. You should always know what sensors exist in your environment, what they're measuring, and where the data goes. Opt-in with value exchange. Participation should be voluntary, and the benefits should flow primarily to the people being monitored, not to some third random party. Privacy by design is a must. Data should be anonymized and aggregated whenever possible. Processing should happen locally before data ever leaves the device. You can measure building occupancy with motion sensors without identifying specific individuals. There's methods for that. Human-centric deployment, the question shouldn't be what AI applications could this data enable? It should instead be what problems can we solve for people that happen to generate useful data as a byproduct. Let's feed two birds with one stone, right? These are not just philosophical niceties. They're pragmatic requirements for getting people to actually opt in at scale. And by the way, we already generate massive amounts of data just by existing. Heat signatures from our bodies, how we use appliances, movement through space, electricity consumption patterns, we're just not capturing a system- atically. The question is not whether data generation happens, it already does. The question is whether we instrument it in a way that benefit the people generating it.
</details>

### 数据质量的误区：基础设施缺失而非标注问题

回到我们最初的起点。《财富》杂志的文章声称AI正在被**劣质数据**（Junk Data）扼杀，认为Scale AI等公司正在生产低质量的标注数据，从而拖累模型性能。该文章的作者（一位计算机视觉公司的联合创始人）声称瓶颈在于数据质量，我们需要更好的标注、更好的过滤和更好的策划。我认为这种说法是**烟雾弹**（Red Herring）。问题不在于我们正在生产糟糕的数据，而在于我们没有生产足够多的**正确类型数据**（Right Kind of Data），因为捕获这些数据的基础设施尚未大规模存在。

试想一下，Scale AI可以整天标注图片。他们可以为物体绘制边界框，对场景进行分类，描述帧中发生的事情，但他们无法：
*   创建关于机器人抓手触摸不同材料时感受的数据。
*   生成关于汽车悬架在不同速度下对坑洼的响应的传感器读数。
*   提供关于建筑物在零度以下如何通过窗户散失热量的热成像数据。
这些数据需要物理传感器部署在真实世界中，测量实际的交互。而这种基础设施之所以尚未大规模存在，并非技术原因。我们知道如何制造传感器，知道如何部署物联网网络，知道如何处理和传输数据。原因一如既往地是经济和社会因素。物联网部署不像大型语言模型那样“性感”，因此遗憾地获得了较少的资金和关注。人们不会在没有看到清晰、切实、即时利益的情况下选择加入传感器网络。传感器部署的商业模式是**领域特定**（Domain-Specific）和**长期**（Long-Term）的，这使得它们对寻求爆炸性增长的风险投资吸引力较低。

<details>
<summary>Original English</summary>

Let me bring this back to where we started. The Fortune article argues that AI is choking on junk data, that companies like Scale AI are producing low-quality labeled data that's dragging down model performance. The author, who's by the way a co-founder of a computer vision company, claims the bottleneck is data quality, that we need better annotation, better filtering, better curation. I think this narrative is a red herring. The problem is not that we're producing bad data, the problem is that we're not producing enough of the right kind of data because the infrastructure to capture it doesn't exist at scale yet. Think about it. Scale AI can label images all day long. They can annotate bounding boxes around objects, classifying scenarios, describe what's happening in a frame, but they cannot create data about how a robot gripper feels when it touches different materials. They cannot generate sensor readings about how a car suspension responds to potholes at different speeds. They cannot produce thermal imaging data about how buildings lose heat through windows in sub-zero temperatures. That data requires physical sensors deployed out there in the real world measuring actual interactions. And the reason that infrastructure does not exist at scale yet is not technical. We know how to build sensors. We know how to deploy IoT networks. We know how to process and transmit data. The reason is as always economic and social. IoT deployment isn't as sexy as LLMs, so it sadly gets less funding and attention. People won't opt into sensor networks without seeing clear, tangible, immediate benefits. The business models for sensor deployment are domain-specific and long-term, which makes them less attractive to venture capital looking for explosive growth.
</details>

### 物理AI的未来：领域特定成功与基础设施普及

因此，真正的瓶颈在于部署策略中的**激励对齐**（Incentive Alignment）。我们需要的不是更好的数据标注公司。我们需要让物联网部署足够引人注目，让人们真正想要它。我们需要：
*   **Fitbit**与NHS（英国国家医疗服务体系）集成，以便患者获得更好的心脏监测。
*   能够显著降低能源成本的**智能建筑**。
*   防止昂贵设备故障的**预测性维护系统**。
我们需要**领域特定**（Domain-Specific）的胜利，以证明基础设施投资的合理性。一旦这些基础设施存在，一旦世界真正被仪器化并大规模生成真实世界数据，那么通用AI实验室就可以构建我们所有人梦想中的世界模型。不是通过模拟现实，而是通过向现实学习。

那么，未来5到10年物理AI的发展意味着什么？我认为我们将进入一个**分叉期**（Bifurcation）。

*   **路径一：领域特定赢家**（Domain-Specific Winners）。那些控制高价值垂直领域传感器基础设施的公司将主导这些领域。例如，特斯拉在自动驾驶领域，因为它们拥有车队数据模式；医疗设备公司在健康监测领域，因为它们拥有可穿戴生态系统和医疗集成；工业自动化公司在制造业领域，因为它们已在工厂车间部署了传感器。这些公司将构建在各自特定领域表现出色的AI系统，但其通用性不强。特斯拉的驾驶AI无法帮助你叠衣服，可穿戴健康监测器也无法在仓库中导航。

*   **路径二：基础设施建设与通用化**（Infrastructure Build-out and Generalization）。我个人认为这更可能发生。OpenAI、Google、Anthropic等通用实验室可以在构建世界模型和物理AI系统方面取得成功，但这只有在**大规模仪器层**（Instrumentation Layer）存在，并且它们能够通过合作或传感器数据成为多方可访问的**商品**（Commodity）后才能实现。

<details>
<summary>Original English</summary>

So, the actual bottleneck is incentive alignment in deployment strategy. We don't need better data labeling companies. We need to make IoT deployment compelling enough that people actually want it. We need Fitbit integrating with NHS so patients get better cardiac monitoring. We need smart buildings that visibly reduce energy costs. We need predictive maintenance systems that prevent expensive equipment failures. We need domain-specific wins that justify the infrastructure investment. And once that infrastructure exists, once the world is actually instrumented and generating real-world data at scale, then the generalist AI labs can build the world models we're all dreaming of. Not by simulating reality, but by learning from it. So, what does this mean for the next 5 to 10 years of physical AI development? I think we're entering a bifurcation. Path one, domain-specific winners, companies that control sensors infrastructure in high value verticals will dominate those domains. Tesla in autonomous driving because they have the fleet data mode, medical device companies in health monitoring because they own the wearable ecosystem and healthcare integrations, industrial automation companies in manufacturing because they've deployed sensors across factory floors. These companies will build AI systems that work extremely well in their specific domain, but don't generalize beyond it. Tesla's driving AI won't help you fold laundry. Wearable health monitors will not really navigate a warehouse. The second path I'm thinking of is infrastructure build-out and then generalization. I personally think this one is more likely. Generalist labs like OpenAI, Google, Anthropic can succeed in building world models and physical AI systems, but only after the instrumentation layer existed a scale where they can access the data either through partnerships or because sensor data becomes a commodity that multiple
</details>

### 物理AI发展的必经之路：循序渐进的传感器部署

这个发展顺序必须是：
1.  首先，通过具有即时价值主张的**领域特定应用**（Domain-Specific Applications）部署传感器。这正在进行中，物联网市场正处于增长阶段。
2.  其次，让数据积累并证明其价值。人们看到利益，采用扩大，网络效应随之显现。
3.  第三，数据访问模型出现。这可能通过像Google Fitbit这样的合作，可能通过**数据市场**（Data Marketplaces），也可能通过类似于ImageNet如何推动计算机视觉突破的**开放数据集**（Open Data Sets）。
4.  第四，通用实验室在来自多个领域的**聚合真实世界数据**（Aggregated Real-World Data）上训练世界模型。只有到此时，才能构建真正理解跨上下文物理现实的AI。

我们现在正处于第一步和第二步之间。那些认识到这种顺序，理解在没有基础设施层的情况下无法直接跳到通用物理AI的公司，才是最终的赢家。其他公司则会烧钱试图通过模拟来理解现实，因为现实是不可战胜的。你可以模拟摩擦力，但最终你必须在真实表面测试你的机器人，并发现地毯的表现与你的模拟预测不同。你可以生成大量合成驾驶场景，但最终你确实需要知道在暴风雪中汽车突然变道时会发生什么。**特斯拉**（Tesla）拥有80亿英里的数据，这些数据来自人们教导他们的汽车真实世界的样子，包括所有模拟器甚至想不到的极端情况和奇怪场景。其他人只有希望、梦想和一个非常好的物理引擎。我更愿意押注前者。

<details>
<summary>Original English</summary>

players can access. The sequence has to be first deploy sensors through domain specific applications with immediate value propositions. This is happening now. The IoT market is growing. Second, let that data accumulate and prove its worth. People see benefits, adoption expands, network effects kick in. Third, data access models emerge. Maybe through partnerships like Google Fitbit, maybe through data marketplaces, maybe through open data sets similar to how ImageNet enabled computer vision breakthroughs. Fourth, generalist labs train world models on aggregated real-world data from multiple domains. Only at this point can you build AI that generally understands physical reality across contexts. We're somewhere between step one and step two right now. The companies that recognize the sequencing, that understand you cannot skip straight to generalist physical AI without the infrastructure layer, are the ones that will win. Everyone else is going to burn money trying to simulate their way to understanding reality because here is the thing about reality. It is undefeated. You can simulate friction, but eventually you kind of have to test your robot on a real surface and discover that hey, carpet behaves differently than your simulation predicted. You can generate synthetic driving scenarios a dime a dozen, but eventually you actually need to know what really happens when a car cuts you off in traffic during a snowstorm. Tesla has 8 billion miles of people teaching their cars what the real world looks like including all the edge cases and weird situations that no simulator would even think to generate. Everyone else has hopes, dreams, and a really good physics engine. I know which one I would bet.
</details>

### 物理AI制胜的关键：控制传感器基础设施

如果你正在这个领域创业，我认为你应该关注以下几点。在**物理AI**（Physical AI）领域获胜的公司，不一定拥有最好的模型，而是那些控制着高流量领域传感器的公司。
*   如果你正在尝试建立一家机器人公司，你需要一个不依赖模拟的**数据收集策略**（Data Collection Strategy），这意味着要么部署自己的传感器，要么与已经拥有传感器的公司合作。
*   如果你正在开发自主系统，你需要大规模访问真实世界的**极端案例**（Edge Cases），这意味着你需要车队数据或同等的数据来源。
*   如果你是一名投资者，或者只是想了解这一切的走向，请关注传感器基础设施的部署地点。**医疗保健**（Healthcare）、**能源**（Energy）、**制造业**（Manufacturing）、**智慧城市**（Smart Cities）——这些是目前真实世界数据正在积累的领域。下一代物理AI将在这里得到训练。

物联网传感器市场预计在未来十年内从180亿美元增长到4220亿美元。这不仅仅是硬件销售，更是正在建设中的基础设施层，它将使每个人都兴奋的物理AI应用成为可能。曾经适用于语言模型的**规模化假设**（Scaling Hypothesis）——即只需输入更多数据，模型就会变得更智能——在某种程度上是有效的，直到它不再有效。现在，质量至关重要，但这里的质量并非指数据标注公司提供的更好标注的图片。它指的是捕获物理交互真实发生时的真实世界传感器数据，包括模拟无法复制的所有复杂细节。我们并非处于**劣质数据危机**（Drunk Data Crisis）中，而是处于**基础设施建设阶段**（Infrastructure Buildout Phase）。叙事应该从“我们需要更好的数据标注”转变为“我们需要在能够证明成本合理性、并作为副产品生成训练数据的高价值应用中部署更多传感器”。那些首先认识到这一点，理解通往物理AI的道路是通过**领域特定传感器部署**（Domain-Specific Sensor Deployment），而不是通过更好的模拟的公司，正是那些将构建出真正在世界中运作的AI系统的公司。

<details>
<summary>Original English</summary>

If you're building in this space, here's what I think you should pay attention to. The companies that will win in physical AI are not necessarily the ones with the best models. They're the ones that control the sensors in high volume domains. If you're trying to build a robotics company, you need a data collection strategy that doesn't depend on simulation, which means either deploying your own sensors or partnering with companies that already have them. If you're working on autonomous systems, you need access to real-world edge cases at scale, which means you need fleet data or equivalent. And if you're an investor or just somebody trying to understand where all of this is going, watch where the sensor infrastructure is being deployed. Healthcare, energy, manufacturing, smart cities, those are the domains where real-world data is accumulating right now. That is where the next generation of physical AI will be trained. The IoT sensor market is projected to grow from 18 billion to 422 billion dollars over the next decade. That is not just hardware sales, that is the infrastructure layer being built that will enable the physical AI applications everyone is so excited about today. The scaling hypothesis that worked for language models, just feed them more data and they get smarter, Turned out to be actually white until it wasn't. Quality matters now, but quality in this context doesn't mean better labeled images from a data annotation company. It means real-world sensor data that captures physical interactions as they actually happen with all the messy complexity that simulations cannot replicate. We are not in a drunk data crisis. We are in an infrastructure buildout phase. The narrative should shift from we need better data labeling to we need more sensors deployed in high-value applications that justify their cost while generating training data as a byproduct. And the companies that recognize that first, that understand the path to physical AI goes through domain-specific sensor deployment, not through better simulation, are exactly the companies that will build the AI systems that actually work in the world.
</details>

我正在开发一个面向非技术专业人士的两级课程，旨在以简单易懂的方式解释AI，并将这些技术机制和基础设施问题分解为可实际应用的框架。如果您愿意花两分钟回答一些问题，直接影响课程内容，链接就在下方。此外，如果您想深入了解Z世代为何讨厌AI并积极破坏它，请查看屏幕上当前播放的视频。现在事态的发展确实相当疯狂。非常感谢您的观看。请订阅，我们下期再见。

<details>
<summary>Original English</summary>

I'm developing a course in two tiers for non-technical professionals where AI is explained simply, by the way, breaking down these kinds of technical mechanisms and infrastructure questions into frameworks you can actually use. If you'd like to take two minutes to answer some questions which directly shape what the course covers, the link is down below. And if you want to dig into why Gen Z people are actually hating AI and actively sabotaging it, check out the video on your screen right now. It's actually pretty wild how things are unfolding right now. Thank you so much for watching. Subscribe, and I'll see you all on the next one.
</details>