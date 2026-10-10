---
author: 硅谷101
date: '2025-12-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-_JDc0XYsB4
speaker: 硅谷101
tags:
  - ai-infrastructure
  - cloud-computing
  - ai-models
  - ai-agents
  - operational-excellence
title: AI云端狂想曲：亚马逊云科技的算力突围、Agent重构与卓越运营
summary: 随着ChatGPT三周年，AI竞争进入白热化。本文深入探讨亚马逊云科技在re:Invent大会上发布的AI战略，重点关注算力（自研芯片Trainium与英伟达GPU合作）、模型生态（Nova 2系列及Bedrock平台）、Agent（Nova Act与AgentCore）及企业级应用，展现其在AI时代下对“卓越运营”的长期主义追求及全栈生态布局。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Amazon Web Services
  - OpenAI
  - Google
  - NVIDIA
  - Anthropic
products_models:
  - ChatGPT
  - Gemini 3
  - Trainium
  - Nova 2
  - Claude
  - Amazon Bedrock
  - Nova Forge
  - Nova Act
  - AgentCore
media_books: []
status: evergreen
---
### AI算力角逐：云端大战与AWS的战略支点

在**OpenAI**发布**ChatGPT**三周年之际，全球**AI**大战已进入新一轮激战。**谷歌**（Google）在11月下旬重磅发布了**Gemini 3**，并放出**TPU**（Tensor Processing Unit: 谷歌专为机器学习工作负载设计的专用集成电路）集群训练**Gemini**与**Meta**（Meta Platforms: 美国社交媒体和科技公司）大订单的消息，这使得**OpenAI**拉响了“红色警报”（Code Red），也让**英伟达**（NVIDIA: 美国图形处理器和人工智能芯片公司）这样的**GPU**（Graphics Processing Unit: 图形处理器，通用计算能力强）巨头感受到了压力。

随着模型巨头们开启新一轮较劲，**AI云厂商**（AI Cloud Provider: 提供AI计算资源和服务的云计算厂商）在算力市场蛋糕迅速扩张的现状中，既面临着紧张的速度竞赛，也面临着技术创新的压力。面对如今的云端大战格局，全球最大云厂商**亚马逊云科技**（Amazon Web Services, AWS: 亚马逊公司旗下的云计算服务平台）将如何布局下一步棋，成为业界关注焦点。在今年的re:Invent大会上，**AWS**展现了其将整个拉斯维加斯变成**AI**乌托邦的决心，其部署的**AI云基础设施**（AI Cloud Infrastructure: 支持人工智能工作负载的云计算基础设施）规模领先且最为广泛。大会的**2B企业级**（Business-to-Business Enterprise: 面向企业的商业模式）技术创新和案例，直接反映了企业在**AI**应用上的“用脚投票”以及**AI**的实际效益。

### 算力突围：英伟达GPU绑定与Trainium自研芯片

在算力支持方面，**AWS**在2025年末的策略是：继续与**英伟达**的**GPU**进行深度绑定并适配优化，同时大幅提升自研芯片的性能。首先，**AWS**一如既往强调与**英伟达**的合作，致力于成为**GPU**的“最佳栖息地”。这意味着**AWS**不仅部署**英伟达**最先进的**GPU**，更进行深度优化，以实现**GPU**算力极高的可靠性和可用性。例如，**AWS** CEO **Matt Garman**介绍了基于**英伟达GB300-NVL72**构建的**P6e-GB300实例**（P6e-GB300 Instance: 基于特定GPU硬件的AWS计算实例），旨在将**AWS**打造成运行**英伟达显卡**（NVIDIA GPU: 英伟达图形处理器）更优的选择。事实证明，这条道路没有捷径，例如在2025年11月初，**AWS**与**OpenAI**宣布达成380亿美元的多年战略合作，**OpenAI**选择的就是搭载**英伟达GPU**的**Amazon EC2 UltraServers计算集群**（Amazon EC2 UltraServers Compute Cluster: AWS的EC2超算服务器集群），实现极低延迟通信以高效运行**AI**任务。

其次，更受市场关注的是**AWS**的自研芯片。类似于**谷歌**的**TPU**，这种**ASIC专项芯片**（Application-Specific Integrated Circuit: 专用集成电路，为特定功能量身定制）在一定程度上对**英伟达**目前的垄断地位构成威胁。对于**AWS**这样的云厂商而言，这是一场算力突围战。**Matt Garman**透露，在提供多种模型**API**（Application Programming Interface: 应用程序编程接口）调用的**Amazon Bedrock平台**（Amazon Bedrock Platform: AWS提供的完全托管式基座模型服务）上，绝大部分用户都在用**AWS**的自研芯片**Trainium**来做推理，包括**Anthropic**（Anthropic: 美国人工智能安全和研究公司）的**Claude模型**（Claude Model: Anthropic开发的大语言模型）。

在今年的大会上，**Trainium芯片系列**（Trainium Chip Series: AWS自研的AI训练芯片系列）迎来了升级。采用3nm工艺的第三代**AI加速器Trainium3**（Trainium3: AWS第三代AI训练加速器）能效相较上一代提升40%，算力翻倍，为大规模**AI**训练和推理带来高性价比。**Trainium3**的算力提升4.4倍，内存带宽提升3.9倍，每兆瓦功率可处理的**AI token数**（AI Token: 人工智能处理的最小文本单位）提升5倍。此外，**Matt Garman**还在现场剧透了**Trainium4**的消息，其**FP4性能**（FP4 Performance: 4位浮点数计算性能）提升6倍，内存带宽提升4倍，**HBM容量**（High Bandwidth Memory Capacity: 高带宽内存容量）增加2倍，并在性能增强的同时降低能耗。这进一步表明**AWS**对自研**ASIC芯片**的决心和押注。**ASIC芯片**为特定功能或应用场景量身定制，在特定任务上能够实现比**英伟达GPU**更高的效率、更低的功耗和更优的性能。尽管**ASIC芯片**需要一定的适配时间，但一旦适配好，就能实现更高效的训练和推理。**Amazon Trainium**将工具交到开发者手中，显著降低了工作负载的运行成本。

**Trainium系列**的快速发展，得益于**AWS**此前对**Anthropic**的80亿美元投资。在2024年的re:Invent上，**AWS**与**Anthropic**高调宣布了**Project Rainier**，涉及30个数据中心，耗费1.1 GW电力，采用50万块**Trainium2芯片**（Trainium2: AWS第二代AI训练加速器）。这种大规模集群的适配合作，使得**Trainium**不仅在推理，还在大模型的训练上都进行了适配和优化，为**Anthropic**的**Claude**等模型用户提供高性能和低成本的算力服务。有投资人认为，**ASIC**和**GPU**并非对立关系，而是互补关系。各大云厂商在自研**ASIC芯片**上投入的同时，也在竞争谁能更好地托管**英伟达GPU**，提供最佳的**基础设施**（Infrastructure: 基础架构）和配套服务。**ASIC芯片**在特定工作负载上能更有效，并有助于管理利润率和成本结构，同时作为差异化因素对抗其他云供应商。

### 模型生态进化：Nova 2家族与Bedrock平台拓展

除了自研芯片，本次大会的另一大亮点是**亚马逊云科技**的自研模型组合——**Nova模型**（Nova Model: AWS自研的基座模型系列）的更新，极大地扩展和升级了其模型生态。如今，数以万计的客户使用**Amazon Nova**，包括**电通**（Dentsu: 日本广告与公共关系公司）、**Infosys**（Infosys: 印度IT服务公司）、**Blue Origin**（Blue Origin: 贝索斯创立的私人航天公司）、**Robinhood**（Robinhood: 美国金融服务公司）等科技领军企业，以及**NinjaTech AI**（NinjaTech AI: 创新型初创公司）等创新型初创公司。在此基础上，**AWS**正式发布了新一代的**Amazon Nova 2**（Amazon Nova 2: AWS新一代自研基座模型），包括**Nova 2 Lite**、**Nova 2 Pro**、**Nova 2 Sonic**和**Nova 2 Omni**四款模型的更新。

**AWS**的自研模型策略并非与头部最强模型争夺极致性能，而是在与一线模型能力持平的前提下，通过打“性价比”牌，并利用整个云生态的配套加持，为客户提供更多选择。

*   **Nova 2 Lite**（Nova 2 Lite: Nova 2系列中的轻量级推理模型）是一款面向日常工作负载的快速、经济型推理模型，能够处理文本、图像和视频输入，并生成文本输出。它适用于处理文档、从视频中提取关键信息、生成代码、提供基于事实的回答以及自动化执行多步骤的**Agent工作流**（Agent Workflow: 智能体自动执行任务的流程）。
*   **Nova 2 Pro**（Nova 2 Pro: Nova 2系列中智能度最高的推理模型）是**AWS**最智能的推理模型，能处理文本、图像、视频和语音输入，并生成文本输出。它适合用于需要高准确率的高度复杂任务，如**Agent编程**（Agentic Coding: 通过智能体自动生成或优化代码）、长期规划及复杂问题求解。这款模型还可用作“教师模型”，通过知识蒸馏（Knowledge Distillation: 将大模型知识迁移到小模型的技术）将能力迁移到更小、更高效的“学生模型”上，用于特定垂直领域。
*   **Nova 2 Sonic**（Nova 2 Sonic: Nova 2系列中的端到端语音模型）是**AWS**的端到端语音模型，深度融合文本与语音的理解与生成，实现实时、类人对话式**AI**体验。它支持多种语言和富有表现力的音色，具备更高识别准确率，并提供高达100万**token**的上下文窗口，支持长时交互。
*   **Nova 2 Omni**（Nova 2 Omni: Nova 2系列中的统一多模态推理与生成模型）是一款统一的多模态推理与生成模型，可处理文本、图像、视频和语音输入，并同时生成文本和图像。它能处理多达75万单词的文本、数小时音频、长视频以及数百页文档，一次性分析完整产品目录、用户评价、品牌规范和视频素材库，降低了连接多种专业模型的成本与复杂度。

这些主打“全模态”的模型对于企业非常有用，例如**思科**（Cisco: 美国跨国科技公司）和**西门子**（Siemens: 德国工业制造公司）等众多企业已利用**Nova 2模型**构建**Agent威胁检测**（Agent-based Threat Detection: 基于智能体的威胁检测）、视频理解和语音**AI助手**（AI Assistant: 人工智能助理）等多种创新应用。

此外，本次re:Invent大会的另一重点是发布了四家外部模型上线**Amazon Bedrock**，包括来自中国的**MiniMax**（MiniMax: 中国人工智能公司）和**Kimi**（Kimi: 中国人工智能公司），以及**Google**的**Gemma**（Gemma: Google开发的轻量级开放模型）和**英伟达**的**Nemotron**（Nemotron: NVIDIA开发的语言模型）。这使得**Amazon Bedrock**的模型生态更加丰富，对开发者和企业更加友好。

除了模型本身，还有两个模型配套上的亮点：首个面向自建前沿**AI模型**的创新服务**Nova Forge**（Nova Forge: AWS提供的开放训练模型平台）和面向**UI工作流**（User Interface Workflow: 用户界面操作流程）的高可靠**AI Agent**服务**Nova Act**（Nova Act: AWS提供的高可靠AI Agent服务）。**Nova Forge**旨在解决企业在整合私域知识与前沿模型能力时的痛点，通过将企业专有数据与**Nova**模型能力结合，帮助企业打造专属的**Novellas**（Novellas: Nova Forge创建的定制化Nova优化变体）定制模型。目前，**Booking.com**（Booking.com: 荷兰在线旅游平台）、**Reddit**（Reddit: 美国社交新闻聚合和讨论网站）和**索尼**（Sony: 日本跨国科技公司）等多家企业已利用**Nova Forge**构建更契合自身需求的专属模型。

**Nova Act**是用于在浏览器中构建和部署高可靠性的**AI Agent**，实现自动执行各类操作，由定制版的**Nova 2 Lite模型**提供算力支撑，是构建和管理大规模浏览器自动化**Agent集群**（Agent Cluster: 智能体集群）的快捷路径。**Nova Act**在早期客户工作流中达到了90%的执行可靠性，其客户案例包括：**Sola Systems**（Sola Systems: 初创公司）每月自动完成数十万次工作流任务，涵盖支付对账、货运协调和医疗记录更新；**1Password**（1Password: 密码管理软件公司）利用**Nova Act**帮助用户以更少手动操作访问登录信息；**赫兹**（Hertz: 美国汽车租赁公司）通过**Nova Act**实现租车平台端到端测试自动化，将软件交付速度提升5倍；**Amazon Leo**（Amazon Leo: 亚马逊的卫星互联网服务）在服务发布前借助**Nova Act**消除了质量测试瓶颈，大幅减少工程师投入时间。

### Agent赋能：重塑软件开发与协作边界

**Nova Act**的推出显示出**亚马逊云科技**对**Agent**方向的重视，围绕**Agent**打造的一系列生态支持也是今年re:Invent的重点。**AWS**坚信**AI Agent**将成为时代最具变革性的突破之一，并致力于将其平台打造成构建和运行这些**Agent**的最佳选择。

尽管**Agent**在2025年爆发，企业争相部署，但在生产和管理中面临快速规模化部署、记忆过去交互、识别和访问工具、掌握复杂工作流、观察和调试问题等挑战。为帮助客户大规模构建、部署安全的生产级**Agent**，**AWS**推出了**Amazon Bedrock AgentCore**（Amazon Bedrock AgentCore: AWS提供的Agent平台），一款专为安全、大规模构建和部署**Agent**而设计的平台。它包含一系列关键组件，提供大规模运行生产级**Agent**所需的全套服务，客户可使用其构建**Agent**，也可结合任何开源**Agent构建框架**（Agent Building Framework: 用于开发智能体的框架）。

**Bedrock AgentCore**有三项关键新功能：
1.  **Policy in AgentCore**（Policy in AgentCore: AgentCore中的策略管理功能）：企业只需用自然语言描述规则，即可创建精细化策略，定义**Agent**可访问的工具、数据、可执行操作和适用条件，解决了权限问题。
2.  **AgentCore Evaluation**（AgentCore Evaluation: AgentCore中的评估工具）：通过内置评估工具监控**Agent**在实际运行中的表现质量，评估维度包括准确性和帮助性，并可添加自定义评估工具。
3.  **Episodic Functionality in AgentCore Memory**（Episodic Functionality in AgentCore Memory: AgentCore中的情景记忆功能）：情景记忆功能自动保存交互过程中的关键事件和状态，助力**Agent**从过往经验中学习，提升决策水平。

这些功能的核心目标是加速**Agent**从想法到大规模生产落地的进程。

此外，本次还发布了三款新**Agent**：
*   **Kiro autonomous agent**（Kiro Autonomous Agent: 可自主开发和编程的智能体）可自主进行开发和编程，改变了软件开发方式，自动化完成功能交付、缺陷分类、提升代码覆盖率等任务。
*   **Amazon Security Agent**（Amazon Security Agent: AWS的安全智能体）则扮演虚拟安全工程师角色，在应用设计、代码审查与渗透测试等环节充当安全顾问。
*   **Amazon DevOps Agent**（Amazon DevOps Agent: AWS的DevOps智能体）作为虚拟运营专家，协助团队解决并预防运行故障，持续提升系统可靠性与性能。

这些更新强调，构建**AI Agent**的四大支柱——**AI芯片**、**模型生态**、首创的“开放训练模型”平台以及**Agent开发工具**——的全面升级和全生态加速押注，明确传递出关键信息：尽管**AI**正在改变应用开发方式，但云计算的基础属性（安全性、可用性、弹性、成本和敏捷性）比以往任何时候都更加重要。与**谷歌**主推**Gemini**、**微软**（Microsoft: 美国科技公司）倾向**OpenAI**模型不同，**亚马逊**（Amazon: 美国跨国科技公司）在这些巨头中显得最为均衡，其**Nova系列模型**并非主推焦点，而是更关注将**Bedrock**打造成一个**multi-model平台**（Multi-model Platform: 支持多种模型的平台），完整搭建安全、数据存储等配套服务，汇集大量**供给**（Supply: 资源供应）和**需求**（Demand: 市场需求），扮演平台角色，类似于电商模式。

### 卓越运营：AI落地的“不被看见的价值”

除了硬核更新，**AWS**还通过丰富的客户案例展示了企业如何拥抱**AI**策略。例如，**Photoshop**（Photoshop: Adobe的图像编辑软件）的母公司**Adobe**（Adobe: 美国软件公司）正利用**AWS基础设施**（AWS Infrastructure: AWS提供的云基础设施）加速**AI转型**，其一站式平台**Adobe Firefly**（Adobe Firefly: Adobe的生成式AI模型集）包含文本到图像、文本到视频和生成填充能力，由**英伟达GPU**驱动的**Amazon EC2 P5和P6计算实例**（Amazon EC2 P5 and P6 Compute Instances: AWS EC2提供的基于特定GPU的高性能计算实例）进行模型训练，已生成超过290亿份创意资产。**Adobe**还将**AI助手**集成进**Adobe Express**（Adobe Express: Adobe的创意设计应用），与**AWS**的合作保证了这些**Agent**s的高效与安全运行。

传媒巨头**康泰纳仕**（Condé Nast: 美国出版媒体公司），即《**Vogue杂志**》（Vogue Magazine: 康泰纳仕旗下时尚杂志）的母公司，正与**AWS**联手进行现代数字媒体转型。通过**AWS**构建统一内容系统与**数据湖仓**（Data Lakehouse: 结合数据湖和数据仓库特性的架构），利用**AI翻译**（AI Translation: 人工智能翻译）实现内容跨区域发布，数字收入占比达70%。其《**纽约客**》（The New Yorker: 康泰纳仕旗下杂志）付费订阅超过100万。**康泰纳仕**还依托**AWS**合作大型直播活动，如**Met Gala**（Met Gala: 大都会艺术博物馆慈善晚宴），通过对事件和直播流的实时分析，使其时尚社会的**参与度**（Engagement: 用户参与度）远超格莱美奖、金球奖乃至超级碗。正如**康泰纳仕**首席产品官兼首席技术官**Sanjay Bhakta**所言：“纸质媒体定义了我们，数字媒体扩张了我们，而数据将变革我们。”

**蓝色起源**（Blue Origin: 贝索斯创立的私人航天公司）在re:Invent大会上发布了第一艘能自主垂直发射和着陆的航天器，并成功发射着陆**New Glenn号轨道火箭**（New Glenn Orbital Rocket: Blue Origin研发的重型运载火箭），目标重返月球。通过与**AWS**合作，2700个**Agent**进入业务流程，一个月内为70%员工促成超过350万次互动。他们还发布了一款利用**AI**研发的“月球吸尘器”，能将月尘转化为能源，完全由**AI设计**（AI Design: 人工智能设计）。**蓝色起源**更是大胆地将**AWS Agent功能**引入航空系统设计，通过内部**BlueGPT平台**（BlueGPT Platform: Blue Origin内部的AI平台）调用多个**Agent**支持研发，使总体交付速度提升75%。

**亚马逊CTO Werner Vogels**在最后一场keynote演讲中分享了**海洋清理组织**（Ocean Cleanup: 致力于清理海洋垃圾的非营利组织）与**AWS**合作，优化塑料检测模型、预测垃圾移动轨迹、最大化清理效率的案例。在体育赛事领域，**AWS**也展示了其**AI**应用。例如在F1赛车中，每辆赛车配备300个传感器，每秒产生超过110万个数据点，**AWS**提供实时数据传输和精准分析，使得车队在激烈的竞争中获得高效响应。**AWS**与**NBA**的合作也很有意思，**AI**帮助**NBA**追踪和共享统计数据，衡量以前无法量化的球员表现，如**投篮难度**（Shot Difficulty: 篮球投篮难度指标）、**防守综合评分**（Defensive Rating: 衡量防守效率的指标）和**引力**（Gravity: 篮球战术概念，指球员对防守注意力的吸引力）。这种“引力”数据在**AI**出现之前难以记录和分析，而现在已成为**NBA**核心数据指标之一，改变了观众的比赛观看方式。

回顾这次re:Invent大会，**Werner Vogels**强调了“卓越运营”的专业自豪感，即“我们建造的大部分东西，最终都不会有人看到”。**AWS**在**ChatGPT**上线三周年之际，以“长期主义”追求其擅长的“卓越运营”，不追求某一环节的单点领先，而是通过极致优化，让算力、平台、模型、数据管理、**Agent工具**（Agent Tool: 智能体使用的工具）形成全栈的生态支持，真正助力**AI落地**（AI Implementation: 人工智能在实际场景中的应用）。