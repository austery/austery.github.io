---
author: AI Engineer
date: '2026-09-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_gvamfT8H-w
speaker: AI Engineer
tags:
  - document-parsing
  - visual-language-model
  - unstructured-data
  - enterprise-ai
title: 让沉默的协议成为可查询的数据库：DocuSign 与 NVIDIA 的视觉语言模型解析实践
summary: DocuSign 联合 NVIDIA 探讨如何利用专用视觉语言模型 Nemotron-Parse 解决海量非结构化协议数据的结构化提取难题。面对每天处理上百万份包含复杂表格与非标准格式的合同，双方通过端到端 VLM 架构替代传统多阶段 OCR 流程，大幅降低端到端延迟与计算成本，使企业沉睡的协议数据真正转化为可实时检索与驱动 AI Agent 的智能知识资产。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - DocuSign
  - NVIDIA
products_models:
  - Nemotron-Parse
  - NVIDIA NIM
  - Blackwell
media_books: []
status: evergreen
---
### 开场与核心挑战：沉睡的协议数据

**Hiral Shah**: 欢迎大家参加我们的演讲。我是 **Hiral Shah**，在 **DocuSign** 担任产品高级总监，今天和我一起分享的是来自 **NVIDIA** 的 **Sean Sodha**。

<details>
<summary>Original English</summary>

**Hiral Shah**: Welcome everyone to our session. I'm Hiral. I'm a senior director of products at DocuSign and I'm joined by Sean.

</details>

**Sean Sodha**: 大家好，我是 NVIDIA 的产品经理。

<details>
<summary>Original English</summary>

**Sean Sodha**: Hello everyone. I'm a product manager at NVIDIA.

</details>

**Hiral Shah**: 今天 Sean 和我将深入探讨每个企业都面临的一个巨大难题——大规模协议数据的处理与利用。在任何企业与商业合作中，协议都是核心载体，B2B 组织每天都在频繁签署大量协议。海量关键信息（例如价格表、交付条款等）都深藏在这些协议当中，并且它们几乎全是非结构化的格式。我们今天将展示 DocuSign 如何与 NVIDIA 携手合作，攻克这一难题，让这些协议数据变得可用、可读且可直接查询，赋能众多企业组织。

这是我们今天的分享大纲：首先探讨为什么这个问题的规模如此庞大、影响如此深远；接着深入拆解技术架构，分享我们如何在大规模场景下处理复杂文档；最后分享我们在评估各种不同用途的模型时所获得的经验与教训。

谈到为什么这是一个巨大的挑战——现场在座的各位可以举个手，有多少人使用过 DocuSign？我想只要在企业工作过的人，入职签订 HR 文件时大概率都用过。DocuSign 拥有极大的业务规模，而对我们工程师团队而言，这也是一个极其庞大的工程挑战。来看一组数据：我们拥有 **190 万付费企业客户**，覆盖全球 **10 亿用户**，这意味着我们每天需要处理超过 **100 万份协议**。我们需要将这些协议全面结构化、可读化、可查询化并支持业务调用。过去我们与**德勤**（Deloitte）联合开展的一项研究显示，全球企业在协议谈判中锁定了高达 **2 万亿美元的价值**，但由于数据无法提取和利用，这部分价值往往在签署后被彻底闲置，没有任何人能回过头把这些数据重新盘活。

<details>
<summary>Original English</summary>

**Hiral Shah**: So today Sean and I are going to talk about a massive problem that every enterprise faces which is agreement data, large-scale agreement data. Agreements are a big part of any relationship any B2B organization goes through day in day out, and a lot of that data is captured inside those agreements. It's very critical, whether it's pricing tables or key terms, and it's all in a lot of different unstructured format. That's kind of what we're going to show is how DocuSign partnered with NVIDIA are fixing that, making that data available, readable, and usable for a lot of our organizations.

So here is a quick map of our talk today. We'll start with just the stakes: Why does this matter? Why the scale is so large? And then we'll dive deep into the technical architecture of how we are approaching it, how we have tackled this document processing at scale. And then finally, we'll cover what we have learned from our evaluation of all the different models we've tried for different purposes and share our learnings with you.

Just to understand why this is a big problem: when you think about DocuSign, raise your hands, how many of you have used DocuSign? Anyone who's employed probably signed HR docs, right? So it's a massive scale, everyone uses DocuSign. For us, it's a massive engineering problem as well because look at the scale: we have 1.9 million paying customers and a billion users. What does that imply? We process a million agreements a day that need to now be structured, made readable, queryable, and usable. In the past we worked with Deloitte on a study, and it says that there's $2 trillion captured in this agreement negotiated value that no one capitalizes on, no one goes back and gets that data back.

</details>

### 协议数据困境与智能协议管理 (IAM)

**Hiral Shah**: 为什么企业无法利用这些数据？我们称之为“协议陷阱”（Agreement Trap）。协议通常由很多人协同起草，完成签署后便直接归档进某个存储系统，从此沦为数字废墟。没有人真正知道里面写了什么，除非人工一份份翻阅。而协议又是如此复杂：格式五花八门，有纯文本、复杂的嵌套价格表、各种多列布局，且每一份合同的排版都截然不同。比如有的协议是单列文本，有的是三列布局，有的包含横跨多页的表格，甚至还有各种特殊字体与扫描件。如何在大规模吞吐下准确理解这些版面结构，是一道极高难度的技术壁垒。

为此，DocuSign 推出了 **智能协议管理**（Intelligent Agreement Management，简称 **IAM**）平台。我们的目标是打通协议从创建、签署到归档后的全生命周期，将所有非结构化协议转化为结构化的数据库。这个平台不仅让数据变得可被语义搜索，还能无缝连接上层应用与分析工具。

在架构层面，这套端到端系统主要包含几个核心环节：第一步是**协议摄取**（Ingestion），无论文档是通过 DocuSign 原生签署还是从第三方系统导入；第二步是**文档解析与版面还原**（Layout & Vision Parsing），这正是我们与 NVIDIA 深度合作的切入点，利用专门构建的视觉语言模型（VLM）高保真提取版面与表格；第三步是**结构化实体与条款提取**（Extraction）；第四步是**向量化与智能搜索**（Search）；最终通过交互层提供协议洞察与 Agent 自动化能力。在整个流程中，最基础也最关键的一环就是版面解析，如果解析器无法准确识别表格单元格的行列对应关系与多列阅读顺序，下游的所有提取和检索都会产生级联错误。这就是我们选择与 NVIDIA 合作并引入专用模型的原因。接下来我把时间交给 Sean，让他详细讲解模型背后的架构设计。

<details>
<summary>Original English</summary>

**Hiral Shah**: Why can't enterprises leverage this data? It's what we call the agreement trap. Agreements get disconnected, people draft them, they get signed, and then they sit in some repository. Nobody knows what's in there unless you manually open them. And agreements are complex: they come in various formats, plain text, complicated pricing tables, multi-column layouts, and every contract has a unique structure. Some are single column, some are three columns, some have multi-page tables, complex fonts, and scanned images. Understanding layout structure at scale is an extremely hard problem.

That is why DocuSign built IAM, an Intelligent Agreement Management platform. Our goal is to connect the entire agreement lifecycle—before, during, and after signature—and turn unstructured agreements into structured data. This makes them searchable, queryable, and usable by downstream applications.

Looking at the architecture, there are several key layers: First is ingestion, bringing agreements in from DocuSign or third-party systems. Next is the layout and vision parser—which is where we partnered with NVIDIA and leveraged a purpose-built model. Then comes extraction of terms, search and retrieval, and finally analytics and agentic workflows. The layout parser is foundational: if you fail to extract tables and reading order properly at the parser level, downstream extraction and search fall apart. That is why we worked with NVIDIA. I'm going to hand it to Sean to walk through the model architecture.

</details>

### NVIDIA Nemotron-Parse 视觉语言解析架构

**Sean Sodha**: 谢谢 Hiral。大家好，正如 Hiral 前面提到的，这里的核心挑战在于极具挑战性的**超大规模**。当企业每天需要处理数百万份文档、涉及数十 PB 级别的数据时，直接采用常规的端到端超大视觉语言模型（Full VLM）在经济成本和算力延迟上是不可行的。

过去行业常见的做法往往是将任务拆解成传统流水线：先使用传统的 **OCR** 引擎提取字符位置边界框（Bounding Boxes），再通过启发式规则或下游大语言模型去拼接语义。然而，这种多阶段流水线存在严重的误差累积问题，尤其在处理密集嵌套表格、跨页合并单元格、无边框表格以及复杂的非线性排版时，经常出现严重的串行和逻辑错乱。

为了在极致精度与大规模生产部署的高吞吐之间取得最佳平衡，NVIDIA 在 **NeMo Retriever** 体系下设计并推出了专门用于文档解析的视觉语言模型——**Nemotron-Parse**。

该模型采用了精心优化的 **编码器-解码器**（Encoder-Decoder）架构：前端是一个高效的高分辨率**视觉编码器**（Vision Encoder），负责直接接收整页文档图像并提取细粒度的视觉与空间特征，包括网格线、字体样式、排版层次及几何对齐关系；后端是一个轻量级且专门微调过的**文本解码器**（Text Decoder）。它不走传统的两阶段 OCR + LLM 拼接路线，而是端到端地直接输出结构化标记语言（如 Markdown、HTML 表格结构以及带语义标签的层次化文本）。通过将参数规模严格控制在特定区间，Nemotron-Parse 既保留了视觉模型对复杂排版和表格几何结构的强大感知力，又避免了大参数模型高昂的推理成本，可以原生通过 **NVIDIA NIM** 微服务进行高并发部署与硬件加速。

在与通用大模型及传统 OCR 管道的基准对比测试中，Nemotron-Parse 在复杂合同与密集表格解析任务上展现出了极高的准确率和显著的吞吐优势，为 DocuSign 每天数以百万计的合同解析提供了可靠的底层算力支撑。

<details>
<summary>Original English</summary>

**Sean Sodha**: All right. Hello everyone. Real quick, Hiral touched on this earlier, but the massive scale here is what makes this so unique. When you are processing millions of agreements every day across petabytes of documents, throwing a massive general-purpose VLM at every single page is simply too expensive and too slow.

Historically, the industry has relied on multi-stage OCR pipelines: running OCR to get bounding boxes, then using heuristics or downstream LLMs to piece the content together. But those pipelines suffer from cascading errors—especially on dense pricing tables, complex multi-column layouts, borderless grids, and multi-page spans.

To achieve the right balance between high accuracy and production-scale throughput, NVIDIA developed **Nemotron-Parse** within our NeMo Retriever family. It is a purpose-built vision-language model designed specifically for document parsing.

The architecture utilizes an optimized encoder-decoder framework: a specialized high-resolution vision encoder captures visual, layout, and spatial representations directly from the document image, preserving table grids, column boundaries, and typography. A lightweight text decoder then directly outputs structured Markdown, HTML table representations, and clean semantic text end-to-end. This eliminates the brittleness of traditional OCR pipelines while keeping parameter count and latency drastically lower than general-purpose frontier VLMs. It can be deployed efficiently via NVIDIA NIM microservices. In our benchmarks, Nemotron-Parse significantly outperforms standard OCR+LLM pipelines in table extraction and layout reconstruction while delivering superior efficiency.

</details>

### 产品演示：从复杂协议到结构化智能数据

**Hiral Shah**: 接下来让我通过一段系统演示，向大家直观展示借助 Agreement Manager 如何轻松将任何复杂的协议转化为可直接利用的结构化数据。Agreement Manager 是企业签署过的所有协议的中央智能知识库。

在系统中，我们可以调出一份典型的商业主服务协议（MSA）及对应的工作说明书（SOW）。这类文档往往包含极其复杂的费率表（Rate Cards）、阶段里程碑付款细则、分级折扣以及跨页的大型价格清单。如果按照传统的人工录入或早期 OCR 方式，这类密集表格极易发生列错位，导致关键金额与计费单位错乱。

而在集成了 NVIDIA Nemotron-Parse 模型的 DocuSign IAM 平台中，系统能够在后台秒级完成对整份文档的深度视觉解析。模型精准识别出了多栏表格的物理边界与逻辑关联，将原本嵌在 PDF 图像中的二维价格矩阵完整还原为标准的结构化数据对象。

更重要的是，一旦底层解析完成，上层的智能应用与分析工具便能直接调用这些数据。例如，企业法务或采购人员可以直接在搜索栏以自然语言提问：“找出所有在加利福尼亚州有效、且包含 15% 以上提成阶梯费率的供应商合同”，系统无需重新扫描原始文件，便能基于已结构化的数据在数秒内返回精准的匹配结果，甚至自动触发下游的续约提醒与风险合规审查工作流。从非结构化文本到即时可用的商业洞察，这正是我们与 NVIDIA 联合方案所释放的核心价值。

<details>
<summary>Original English</summary>

**Hiral Shah**: Let me show you how easy it is to turn any agreement into structured usable data with Agreement Manager, which is a central repository of every agreement an organization has ever signed.

Let's look at a typical Master Services Agreement (MSA) and Statement of Work (SOW). These documents contain dense rate cards, milestone payment terms, tiered discounts, and multi-page pricing tables. With traditional manual review or basic OCR, dense tables easily suffer from misaligned columns, corrupting critical pricing figures and billing units.

With DocuSign IAM powered by advanced parsing leveraging NVIDIA's Nemotron-Parse model, the system performs deep visual parsing in seconds. It precisely captures physical boundaries, row-column relationships, and converts complex 2D price tables into clean, structured data objects.

Once structured, enterprise teams can instantly query the data using natural language—such as asking: "Find all active supplier agreements in California with tiered rate cards exceeding 15%." The system returns precise answers across the entire agreement repository in seconds and can trigger automated renewal workflows. Turning unstructured documents into actionable business insights in seconds is the core power of this collaboration.

</details>

### 模型评估、性能权衡与未来展望

**Hiral Shah**: 在模型评估与选型过程中，我们深入对比了多种技术路线的权衡。在 DocuSign 每天百万级协议的处理吞吐下，模型效率至关重要。直接采用通用百亿或千亿级的大型视觉多模态模型虽然能取得不错的解析效果，但在推理时延和算力成本上无法满足大规模实时流水线的严苛要求。而通过与 NVIDIA 合作采用针对文档版面与表格专门优化的 Nemotron-Parse 专用模型，我们在保持极高结构化提取准确率的同时，大幅降低了单页处理的算力开销。

接下来，请 Sean 为我们介绍后续的演进路线与更深入的合作计划。

<details>
<summary>Original English</summary>

**Hiral Shah**: In our evaluation across various models, model efficiency was paramount. Given our volume of over a million agreements a day, running massive general-purpose VLMs introduces prohibitive latency and inference costs. By partnering with NVIDIA and adopting the purpose-built Nemotron-Parse model, we achieve high accuracy on complex layout and table extraction while keeping compute costs and processing time under strict control.

I'll let Sean talk through what is coming next in our roadmap.

</details>

**Sean Sodha**: 与 DocuSign 团队的合作非常顺畅且富有成效，我们在未来几个月将继续深化合作。我们从最核心的底层文档解析与摄取问题出发，确保高保真提取非结构化数据；在此基础之上，我们正在将合作拓展至基于 **NVIDIA Agent Toolkit** 的智能体编排系统，探索如何构建能够自主执行跨合同合规审查、智能比对与多步骤复杂分析的生产级 **AI Agent**，真正实现端到端的企业级协议智能化。

<details>
<summary>Original English</summary>

**Sean Sodha**: Working with the DocuSign team has been awesome, and we're going to continue deepening that partnership over the coming months. We started with the foundational layer—how to parse and ingest unstructured documents at scale with high fidelity. From there, we are collaborating on the NVIDIA Agent Toolkit to build and scale production-grade AI agents capable of multi-step reasoning, cross-agreement compliance analysis, and automated workflows.

</details>

### 现场问答：OCR 对比、算力开销与量化部署

**Hiral Shah**: 非常好，我们现场还有一点时间，可以接受几个观众提问。请那位观众先提问。

观众提问的核心问题是：为什么不直接使用传统的 OCR 结合下游大模型，而是必须引入像 Nemotron-Parse 这样的专用视觉模型？

对于 DocuSign 而言，传统 OCR 最大的痛点在于缺乏对版面几何与阅读顺序的深层感知。当遇到复杂的多栏排版或无边框财务报表时，OCR 往往按简单的物理坐标从左到右硬性扫描，导致相邻栏目的文本被错误拼接。Nemotron-Parse 能够直接理解文档的视觉版面拓扑，从根本上解决了这个问题。Sean，你可以从算力与模型架构角度做进一步补充。

<details>
<summary>Original English</summary>

**Hiral Shah**: Perfect. We have time for a couple of questions from the room. Someone there.

To recap the question for everyone: Why not just use traditional OCR with an LLM, and why choose a dedicated visual parsing model like Nemotron-Parse?

From our side, traditional OCR loses layout context and reading order. On multi-column layouts or borderless tables, OCR scans across columns, corrupting the text flow. Nemotron-Parse understands the visual layout topology natively. Sean, please add your perspective.

</details>

**Sean Sodha**: 是的，这主要取决于具体的应用场景与计算周期的分配策略。对于 DocuSign 这种需要将数十 PB 文档转化为可查询数据库的场景，如果在数据摄取阶段只做粗粒度的文本抽取，后续在检索和生成阶段就需要浪费巨大的 LLM 算力去纠错和做冗长的前后文推理，且效果往往难以保障。

通过在摄取阶段投入专用、高效的视觉解析模型算力，将高质量的结构化数据直接固化在数据库中，能够让后续的所有检索和 Agent 查询变得极轻量、极迅速。

<details>
<summary>Original English</summary>

**Sean Sodha**: It really depends on the use case and where you want to spend your compute cycle. When you have petabytes of documents that need to be permanently queryable, doing a sloppy text-only extraction forces you to spend massive LLM compute downstream trying to repair broken context.

By investing compute upfront in a specialized visual parser during ingestion to produce pristine structured data, all downstream retrieval and agentic reasoning become significantly cheaper, faster, and more reliable.

</details>

**Hiral Shah**: 没错，我们采用的是一种面向具体任务的混合架构（Hybrid Approach），针对表格与复杂版面采用专用模块，并在各环节进行深度工程优化。

<details>
<summary>Original English</summary>

**Hiral Shah**: Exactly. We take a purpose-built hybrid approach tailored to the specific needs and use cases. We have published technical blogs detailing how we solve this at scale with modular components.

</details>

**观众**: 你们目前使用的模型量化精度是多少？是在 FP16 还是更低精度？

<details>
<summary>Original English</summary>

**Audience**: What quantization level are you currently using for this model? Are you running FP16 or lower?

</details>

**Sean Sodha**: 目前该解析模型在生产环境中运行在 **FP16** 精度下。但我们已经在积极推进向 **FP8** 以及基于 **Blackwell** 架构的 **NVFP4** 低精度量化迁移，预计在未来几个月内完成上线。

我们在工程优化上的标准方法论是：首先在全精度或半精度下确保提取准确率达到业务要求，确认其为系统创造核心价值；随后在帕累托最优边界（Pareto Frontier）上通过量化与硬件加速技术大幅压榨推理延迟与成本。

<details>
<summary>Original English</summary>

**Sean Sodha**: This model is currently deployed on FP16, but we have clear paths towards moving to FP8 and NVFP4 on Blackwell over the coming months.

Our approach is to first establish high accuracy and verify value creation, and from there aggressively push out the Pareto curve on performance and inference cost through advanced quantization.

</details>

**观众**: 在检索阶段你们是直接依赖向量召回还是直接基于提取出来的结构化字段查询？

<details>
<summary>Original English</summary>

**Audience**: On the retrieval side, are you relying on vector recall or directly querying the extracted structured data?

</details>

**Hiral Shah**: 我们演示中展示的查询主要是直接基于我们从协议中提取并存储在 Agreement Manager 中的结构化数据对象。

由于时间关系，我们的演讲先到这里。如果大家对完整架构细节有更多兴趣，我非常乐意在会后与大家在场边继续线下交流。祝大家在 AI 落地应用探索中取得成功，谢谢大家！

<details>
<summary>Original English</summary>

**Hiral Shah**: The queries shown are coming directly from the structured agreement data that we have extracted and stored in Agreement Manager.

We are right at time. I'm happy to chat offline in the back about our full architecture with anyone interested. Good luck with your AI challenges, and thank you everyone!

</details>

**Sean Sodha**: 谢谢大家！

<details>
<summary>Original English</summary>

**Sean Sodha**: Thank you.

</details>