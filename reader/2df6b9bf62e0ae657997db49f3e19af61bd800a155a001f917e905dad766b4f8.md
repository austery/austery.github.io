---
author: AI Engineer
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=VXfRt_H-V08
speaker: AI Engineer
tags:
  - ai-agents
  - governance
  - registry-system
  - enterprise-architecture
  - mlops
title: Amplifon如何通过“Amplify”项目构建企业级AI代理注册系统
summary: 本访谈详细介绍了 Amplifon 为应对AI开发中的混乱局面，通过“Amplify”项目构建企业级注册系统的过程。内容涵盖了AI网关、MCP注册表、A2A代理注册表以及应用场景注册表的设计与实现，强调了治理、平台和工厂三大支柱，旨在实现AI应用的标准化、可扩展性和可追溯性，并简化开发者的工作流程，最终实现AI的规模化、负责任的应用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Amplifon
  - Quantica
products_models:
  - Amplify program
  - MCP registry
  - A2A registry
  - AI gateway
media_books: []
status: evergreen
---
### AI 开发的混乱与 Amplifon 的解决方案

**Sonny Merla**: 当三大洲的数十个团队都在构建 AI 代理，每个团队都在连接自己的系统，重塑自己的安全模型，部署自己的基础设施时，会发生什么？只会带来混乱。
<details>
<summary>Original English</summary>

**Sonny Merla**: What happens when you have dozen of teams across three continents all building AI agents, each one wiring up their own connections, reinventing their own security model, deploying their own infrastructures? You get chaos.

</details>

**Sonny Merla**: 大家好，我是 Sonny Merla，Amplifon 的全球数据科学与 AI 经理，今天我和 Mauro Luchetti，AI 卓越中心经理，以及 Mattia Redaelli，Quantica 的 AI 工程师（Quantica 是负责设计和构建我们即将介绍的技术解决方案的团队）一起来。
<details>
<summary>Original English</summary>

**Sonny Merla**: Hi, I'm Sonny Merla, Global Data Science and AI Manager at Amplifon, and I'm here today with Mauro Luchetti, AI Center of Excellence Manager, and Mattia Redaelli, AI Engineer at Quantica, the team that design and build the technical solution that we are about to describe.

</details>

**Sonny Merla**: 今天，我们将向大家展示 Amplifon 如何通过启动自己的 **Amplify 项目**，来解决这个问题，特别是我们如何设计一个**企业级注册系统**，用于 **MCP** 和 **A2A 代理**。
<details>
<summary>Original English</summary>

**Sonny Merla**: Today, we are going to show you how Amplifon tackled down this problem by launching their own Amplify program, and specifically how we design an enterprise-grade registry system for MCP and A2A agents.

</details>

**Sonny Merla**: 对于不了解 Amplifon 的朋友们，Amplifon 是全球领先的**听力护理解决方案**提供商。我们在全球 26 个国家开展业务，拥有超过 20,000 名员工，并在全球经营超过 10,000 家门店。
<details>
<summary>Original English</summary>

**Sonny Merla**: For who don't know Amplifon, Amplifon is the world leader in hearing care solutions. We operate across 26 countries around the globe. We are more than 20,000 people, and we operate over 10,000 stores across the globe.

</details>

**Sonny Merla**: 我们正处于 **AI 转型**之中。目前，我们正在试验各种 **AI 解决方案**和技术，因此面临着挑战，例如构建稳定可靠的解决方案，以及如何根据中央定义的指导方针，负责任地**扩展**它们。
<details>
<summary>Original English</summary>

**Sonny Merla**: We are in the AI transformation. Right now, we are experimenting with AI solutions, technologies, and so we are facing challenges like building solutions that are stable over time, and understanding how to make them scale responsibly accordingly to guidelines that are defined centrally.

</details>

**Sonny Merla**: 那么，Amplifon 是如何决定大规模采用 AI 的呢？我们在 2025 年 1 月启动了 **Amplify 项目**。这是一个全球性、跨职能的项目，旨在为 **AI 采用**设定规则。它基本上由一个**运营模式**和一个**执行计划**组成。
<details>
<summary>Original English</summary>

**Sonny Merla**: So, how Amplifon decided to adopt AI at scale? We launched in January 2025 the Amplify program. It's a global and cross-functional program designed to set the rules for the AI adoption. And it is basic basically composed by an operating model and an execution plan.

</details>

**Sonny Merla**: **运营模式**基于两个主要来源：**控制塔**（control tower）和**委员会**（committee）。控制塔是一小群核心人员，他们决定**安全**、**法律**、**技术**的指导方针，以及**战略**重点和优先开发的**用例**。然后是委员会，负责在各国以及公司层面执行战略，并更精细地优先排序用例，以释放组织价值。
<details>
<summary>Original English</summary>

**Sonny Merla**: The operating model is based on two main sources, the control tower and the committee. The control tower is a limited set of people including chief decide deciding what are the guidelines for security, legal, technology, but also what are the strategy the the focus for the strategy, and so the use cases to develop us first. Then there is the committee that has the responsibility for running the strategy in the countries, but also in the the corporate side. So, prioritizing also the use cases more granularly, those are to to release the value to the organization.

</details>

**Sonny Merla**: Amplify 项目的主要关注点是什么？我们有三个：**治理**（governance）、**平台**（platform）和**工厂**（factory）。在治理方面，我们希望确保与 **AI 法规**、中央定义的战略和指导方针保持一致。这还包括让人们了解项目的存在、游戏规则，以及我们如何交付和推广价值。
<details>
<summary>Original English</summary>

**Sonny Merla**: Which are the main focus of the Amplify program? We have three of them, governance, platform, and factory. So, the governance, we want to ensure the alignment with AI regulatory, also the strategy and the guidelines that we define centrally. So, it's also a matter of make the people aware of the existence of a program, the also the rules of the play, and also then make all the people informed of how we deliver and roll out the value.

</details>

**Sonny Merla**: 然后是平台方面。我们需要建立开发者和实施团队赖以运作的**基础设施**，认证基础设施和工作方式，以提供可扩展 **AI 应用**的流程和服務。
<details>
<summary>Original English</summary>

**Sonny Merla**: Then there is the platform side. So, we have to set up the infrastructure on which we operate as developers and implementation teams. So, certifying infrastructures and way of working to deliver processes and also services to scale AI application.

</details>

**Sonny Merla**: 然后是工厂。这是整个故事中最实际的部分。**开发团队**需要专注于将解决方案推向市场，并关注**跨国家**的推广，这对 Amplifon 非常重要。因此，要将解决方案视为**可扩展**且可在不同领域**重复使用**的。
<details>
<summary>Original English</summary>

**Sonny Merla**: Then we have the the factory. So, this is the most practical part of the story. So, we have the development teams that needs to have a focus on rolling out solutions to the market, also caring about the rollout across countries that is very important for for Amplifon. So, thinking about the solution as a scalable scalable and also reusable across different domains.

</details>

**Sonny Merla**: 那么，作为一个试图在组织内广泛推广 AI 的组织，我们看到了哪些主要问题？我们肯定预见到**维护和运营问题**、**治理和合规问题**，以及**企业规模化扩展**的问题。
<details>
<summary>Original English</summary>

**Sonny Merla**: So, which are the main problems that we see as an organization that tries to roll out AI at scale in a pervasive way in the organization? So, we foresee for sure maintenance and operations problems, governance and compliance problems, but also enterprise scaling.

</details>

**Sonny Merla**: 所以，开发者需要如何开发以使解决方案长期稳定。
<details>
<summary>Original English</summary>

**Sonny Merla**: So, how the developers needs to develop to make the the solution stable over time.

</details>

**Sonny Merla**: 从维护和运营方面开始，即使我们开发和推出的 **AI 应用**和 **AI 代理**的核心是生命周期很短的 **LLM 模型**，我们也希望确保能够解决在推出的用例中，这些 LLM 的使用问题。因此，我们希望做好准备，随时迅速采取行动，以应对模型使用的任何中断。
<details>
<summary>Original English</summary>

**Sonny Merla**: Starting from the maintenance and operations side, uh even the short life cycle of the LLM models that are at the core of the AI application and the AI agents that we develop and roll out, we want to be sure that we are able to address the the usage of this kind of LLM LLMs across the the use cases that we we roll out. So, we want to be ready and prepared to act promptly every time we we see a disruption in the model we use in the use case.

</details>

**Sonny Merla**: 另一方面，在**治理和合规**方面，我们需要确切知道我们在组织中何处使用 AI，主要用例是什么，这既是为了满足**监管**要求，也是为了了解组织内的整体使用情况。因此，我们想要一个**目录**（catalog）。我们希望有一种方式来了解单个用例所使用的**资产**。也就是说，它们实现了什么，使用了什么来创建信息的**谱系**（lineage）。
<details>
<summary>Original English</summary>

**Sonny Merla**: Um on the other side with the governance and compliance, we we need to be sure to know about where we use AI in the organization, what are the main use cases, also for the regulatory point of view, but also for the usage across the organization. So, we want to have a catalog. We want to have a way to understand also the assets used by the single use cases. So, what they implemented, what they used to also create a sort of lineage of the information.

</details>

**Sonny Merla**: 另一方面，还有一个问题与我们在组织内跨多个团队开发 AI 解决方案的方式有关，这些团队在不同的**基础设施**上运行。因此，我们希望至少在治理方面实现**开发集中化**。然后，具备**清晰的指导方针**，能够在不同的基础设施和团队中实现**复用**。
<details>
<summary>Original English</summary>

**Sonny Merla**: On the other side then there is a a point related to the the way we develop AI solution in the organization across multiple teams that operates on different infrastructures. So, we want to make the developments at least in terms of governance centralized. Then so with clear guidelines, reusable also on different infrastructures and different teams.

</details>

**Sonny Merla**: 这就是我们的目标。我们希望简化**开发者**的工作，让他们能专注于用例中的**业务逻辑**，避免在每次需要处理**安全**、**部署**和**维护**用例时都要重复造轮子。
<details>
<summary>Original English</summary>

**Sonny Merla**: This is the the goal. So, we we want to make easy the life of developers to focus on the business logic inside the use cases, avoiding to reinvent the wheel every time we need to to take to take care about the security, but also the deployment and maintenance of the the use cases.

</details>

**Sonny Merla**: 那么，现在我请 Mauro 来介绍我们在 Amplifon 如何处理这些问题。
<details>
<summary>Original English</summary>

**Sonny Merla**: So, now I let Mauro to introduce how we address these topics at Amplifon.

</details>

### AI 网关与注册表系统

**Mauro Luchetti**: 谢谢 Sonny，让我们从更技术性的角度来探讨这个问题。我们首先构建的组件是为了，你知道，解决这些问题，那就是 **AI 网关**（AI gateway）。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Thank you, Sonny, and let's try to bring more technical point of view in this. The first component that we built in order to, you know, let's try try to to address those problems are an AI gateway.

</details>

**Mauro Luchetti**: 首先，它为我们带来了**统一的访问**。所以，所有想使用模型的开发者都可以使用这个网关，并指向**统一的端点**，使用 Amplifon 目录中的所有模型。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: First of all, it brings us unified access. So, all the developers that want to use a model, they can use this gateway, and they can point to the unified endpoint, and use all the models that Amplifon has in in its catalog.

</details>

**Mauro Luchetti**: 然后是**安全方面**。如果你想使用模型，你必须连接到网关。你必须进行**身份验证**，我们通过**内部 ID 集成**（intra ID integration）完成了这一点。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Then there's a security aspect. If you want to use the models, you have to, you know, connect to the gateway. You have to authenticate yourself, and we have done this with the intra intra ID integration.

</details>

**Mauro Luchetti**: 然后是**预算方面**，因为 Amplifon 有很多用例。如果一个用例来找你申请使用这些模型的预算，你可以在这个 AI 网关中设置一个**预算**。比如，**每月成本**，或者按周、按月等设置预算。当开发者使用这些预算时，它会逐渐消耗，并可以告知开发者剩余预算。这样他们就可以控制开销。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Then there's a budgeting aspect because obviously Amplifon has lots of use cases, and if a use case came to you and asked for, you know, for budget for using those those models, you can set in this AI gateway a budget. So, a cost monthly cost, or I mean, yeah, you can set it monthly, weekly, and so on, but you can set a budget, and while the developers are using those budgets, it erodes, and it can brings to developers you know, the remaining part of those budgets. So, they can they can control it.

</details>

**Mauro Luchetti**: 然后是**控制方面**。所有通过 **LLM 模型**进行的请求或响应，以及我们为所有请求之上需要设置的**分析**，都使用连接到此 AI 网关的中央**审计**、**监控**和**分析工具**来完成。然后，对于**治理**部分，我认为这是入口点，是顶层。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: And then there's the the the control aspect. So, all the you know, all the requests that are are done through LLM models or responses, all those all the analytics that we need to put in place on top of all the requests are done using a central auditing monitoring and analysis tools obviously connected to this AI gateway. And then for the governance part, I mean, this is the entry point. This is the top layer, I would say.

</details>

**Mauro Luchetti**: 然后我们有三个不同的注册表。第一个是 **MCP 注册表**。正如大家所想象的，所有工具、与 Amplifon 系统的所有集成、以及我们想为 LLM 模型提供的所有功能，都通过这个 MCP 注册表暴露，它是所有可用工具的**中央目录**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: And then we have three different registries. The first one is the MCP registry. So, as you as you can imagine, all the tools, all the integration with Amplifon systems, all the functionalities that we want to provide to LLM models are exposed through this MCP registry, which is the the the central catalog of all all available tools.

</details>

**Mauro Luchetti**: 然后是 **A2A 代理到代理注册表**（agent-to-agent registry）。它是一个包含所有已实现和可用代理的完整目录，并使用**代理卡**（agent card）标准。它暴露代理卡，并允许开发者连接到已开发的代理。最后是**应用场景注册表**（use case registry），它连接所有这些信息、所有这些元数据，并实现真正的**治理功能**、**谱系**（lineage）功能，再次将所有这些方面联系起来。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Then there's the A2A agent-to-agent registry. So, it brings it's a full catalog of all implemented of all available agents, and it uses agent card standard. It exposes agent card, and also it can it can give the developer the ability to connect to already developed agents. And then there's the use case registry, which is the you know, the registry that connects connects all those all those information together, all those metadata together, and bring out the real governance functionality, the lineage functionality, and again connects all those aspects together.

</details>

**Mauro Luchetti**: 让我们更详细地了解每个注册表。我不想在这里详细介绍 MCP 是什么，但我们开始于社区维护的**官方 MCP 注册表**。这是所有可用 MCP 服务器的公共社区目录，我们在此基础上进行构建。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Let's try to go in more detail about each of those registry. I don't want to obviously tell anybody what MCP is not at this conference, but we started from the official MCP registry maintained by the community. This is the you know, the the public community-wide catalog of all available MCP servers, and we essentially build on top of that.

</details>

**Mauro Luchetti**: 因此，Amplifon 构建了自己的**私有 MCP 注册表**，作为功能扩展，并增加了我们希望添加到每个注册服务器的企业级上下文。它包含两部分主要内容：内部 Amplifon 团队为特定系统、特定集成、Amplifon 希望提供的特定工具构建的**自定义内部服务器**，以及一套经过 Amplifon 批准、认证供 Amplifon 用例使用的精选**公共服务器**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: So, Amplifon has built its own private MCP registry as an extension in functionalities, and also in you know, enterprise context that we want to add to each of the registered servers. It contains two main things. As you can imagine, the you know, the custom internal servers that the the the the internal Amplifon team have built for specific system, specific integration, specific tool that Amplifon want to provide, and also a curated set of public server that have been approved that have been, you know, certified by Amplifone for for for Amplifone use cases.

</details>

**Mauro Luchetti**: 在这个目录中注册的所有这些服务器都添加了一些额外的**企业级元数据**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: And both these servers that we want that we register in in this catalog are enriched with some additional enterprise metadata.

</details>

**Mauro Luchetti**: 让我们看看这些元数据。首先是**所有权**（ownership）。每个服务器都有一个所有者，即负责该服务器的团队、用例或项目。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Let's let's see what are those metadata. First of all, the ownership. Each server has an owner. So, which is which team, which use case, which project is in a way owner is responsible for that specific server.

</details>

**Mauro Luchetti**: 服务器运行的**环境**（environment），例如是否在**开发**（dev）、**测试**（test）或**生产**（prod）环境中运行。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: What are the environment in in which the server is running. So, it is running is it running in dev, test, prod, and so on.

</details>

**Mauro Luchetti**: **认证模式**（authentication model）是什么？开发者如何使用该服务器？需要部署哪些机制？**成本归属**（cost attribution）。这与 AI 网关功能和我们之前描述的预算方面相关。这样做的目的是了解每个服务器的实际支出。然后是**应用场景关联**（use case linkage）。即哪些用例实际上在使用特定的服务器。这些不仅仅是“锦上添花”的元数据，它们真正实现了**影响分析**（impact analysis）功能。在这里，我们实现了**治理**（governance）和**可审计性**（auditability）。我们拥有 AI 工具存在及其被 Amplifon 开发者使用的完整追踪记录。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: What are the authentication model? So, how I can effect how I can as a developer use that server? What are the mechanism that I need to put in place? The cost attribution. So, this is linked to the AI gateway functionality, the budgeting aspect that we have described before. And this is done in order to see what server spending what essentially. And then the use case linkage. So, what are the use cases that are effect that are actually using that specific that specific server. And these are not simply, you know, metadata that are nice to have. This is something that really bring out the impact analysis functionality. This is where effectively we enable the governance and the auditability. And we have the complete trail of what AI tooling exist and how they are they are being used by Amplifone developers.

</details>

**Mauro Luchetti**: 然后是第二个注册表，即**八路注册表**（eight way registry）。它完全基于**代理卡**（agent card），描述代理的身份、端点、能力、支持的模式、认证要求等。我们构建了一些**蓝图**（blueprints），后面会讲到。基本上，当一个代理部署时，它会通过 **CI/CD 集成**自动将其代理卡发布到注册表中。这样，任何其他代理或开发者都可以发现并与之交互。从某种意义上说，我们正在努力使所有代理开发实现**自文档化**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: And then we have second registry which is the eight way registry. This is fully based on the agent card that, you know, describe the agent's identity, its endpoint, the agent capabilities, the supported modalities, authentication requirements, and so on. We have built some blueprints and then we talk about those blueprints. But essentially, when an agent is deployed, it automatically publish publishes its agent card to the registry via CICD integration. So, in this way any other agent, any other developer can discover this new agent and obviously can interact with it. So, in a way we are trying to make all those agent development self-documenting.

</details>

### 连接与实践

**Mauro Luchetti**: 现在，我们将看到**应用场景注册表**（use case registry）如何将这另外两个注册表连接起来。我们如何从业务角度使用 MCP 注册表和八路注册表？我们希望有一个应用场景注册表，以将代理和工具映射到组织中采用的特定应用场景。这就是我们设计这个特定**构建块**（building block）的原因，它包含单个用例使用的资产信息、它们的实现、它们使用的模型（也用于我们之前提到的维护主题）。此外，还可以了解我们如何以及在哪里开发和部署了这些类型的用例。例如，哪个系统服务于特定的用例，以及哪些其他方面会受到该用例的影响。例如，如果我们有多个用例之间的连接，我们希望在一个界面中清晰地看到它们，这个界面可以成为所有人的目录。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Now, we will see how use case registry connects those two other registry together. How do we can use the MCP registry and eight way registry from a business point of view? We want to have a use case registry. So, to map the agents and the tools in specific use case adopted across the organization. And this is the reason why we designed this specific building block that aims to contain the information of what are the assets used by the single use case, what they implement, what are the models they used also for the maintenance topic that we mentioned before. And also understand how and where we develop and deployed this kind of use cases. For example, which is the system that serve the use case the specific use case and what are all the other impacted by this use case. So, for example, if we have connection among multiple use cases, we want to see that clearly in interface that can be a catalog for for everyone.

</details>

**Mauro Luchetti**: 现在让我们看看它在实践中是如何工作的。让我们来演示一下我们开发的、为组织实现所有这些注册表的平台。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Let's see now how it works in practice. So, let's go in a walk through of the the platform that we developed and that implement all these registries for the organization.

</details>

**Mauro Luchetti**: 好的，我们还想简要介绍一下我们的平台。这里您可以看到是**主页**。您可以进入**目录**（catalog），也就是我们之前详细描述的 MCP、八路和应用场景。我们还有 **AI 网关**部分，在这里定义了目前企业可用的 **LLM**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Okay, so we wanted also to give you a brief overview of our platform. Here you can see that is the home page. You can go into the catalog, so what we described in detail before, so MCP, eight way, use cases. We also have the AI gateway part where we define what LLMs are available in the enterprise right now.

</details>

**Mauro Luchetti**: 回到**仪表板**（dashboard），如果我们进入目录，这就是我们即将部署到**生产环境**的平台。这里我们有一些**演示数据**。目前定义了六个实体：应用场景、MCP 和八路代理。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Going back to the dashboard, if we move on to the catalog, this is the platform that we are going to deploy in production soon. Here we have demo data. So, we have six entities defined until this point. We have use cases, MCP, and eight way agents.

</details>

**Mauro Luchetti**: 进入应用场景部分，如果我们打开一个示例应用场景，我们可以定义它的状态、版本、描述、使用的**资产**。例如，一个代理（agent）和一个 MCP 服务器，它正在使用哪些 **AI 模型**，以及应用场景的**生命周期历史**。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: Going into the use cases part, if we open a sample use case for instance, we can define its status, its version, its description, assets used. So, for instance, an agent and then MCP server, what AI models it's using, and the life cycle history of the of the use case.

</details>

**Mauro Luchetti**: 如果您转到创建应用场景页面，您可以看到我们可以定义名称、描述、应用场景的状态、所有权以及与之关联的资产。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: If you go on to the create use case page, you can see that we can define a name, a description, the status of the use case, the ownership, and also the assets linked to that.

</details>

**Mauro Luchetti**: 如果我们转到 **AI 工具**部分，即 MCP 服务器，您可以看到我们有两个示例 MCP 服务器。实际服务器的 JSON 在这里描述。在**八路代理**中，我们也可以看到**代理卡**（agent cards）的相同内容。例如，这里有一个 **LangChain 测试代理**，它测试来自代理卡的这些能力和描述。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: If we move to the AI tool section, so MCP servers, you can see that we have two sample MCP servers. So, the actual server JSON is is described here. We can also see into the eight way agents the same thing for agent cards. So, for instance, here we can define the we can have the long chain test agent that test these capabilities and description from the agent card.

</details>

**Mauro Luchetti**: 我们还定义了**检查器**（inspector）页面，您可以在其中选择一个 MCP 服务器，并在另一个选项卡中启动检查器。这样您就可以连接并检查该 MCP 提供的功能。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: We also define the inspector page where you can select an MCP server and you can launch the inspector in another tab. So, you can also connect and check what that MCP is providing you.

</details>

**Mauro Luchetti**: 我们还有相同的检查器，用于检查与八路代理卡的兼容性。您也可以在这里进行同样的操作。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: We also have the same inspector that is just checking for compatibility with the eight way agent card. And you can do the same here.

</details>

**Mauro Luchetti**: 我们还提供了**小部件**（widgets）。为了方便开发者，您可以直接使用表单定义 MCP 的 **server.json** 和八路代理卡的 **agent card**，然后在本地预览，而不是从仓库的实际 JSON 文件开始，特别是当这是您第一个服务器时。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: We also have widgets. So, you can in order to make the life of the developer easier, define the server.json for MCP and the agent card for eight way with a form and then preview it here instead of starting from the actual JSON on the repo if it's the first, let's say, server for you.

</details>

**Mauro Luchetti**: 我们还可以检查**谱系**（lineage）。例如，您可以进入一个应用场景，打开您想检查的应用场景，然后打开**对象谱系**（object lineage）。在这个谱系视图中，您可以看到，例如，这里的“**AI 票据优化**”应用场景连接到一个代理，连接到另一个代理，并且还连接了 **AI 模型**。因此，我们可以获得应用场景的完整谱系，并且正如 Maurice 之前所说，能够确保在谱系的某些部分受到中断或问题影响时，能够及时做出修改，并回溯到受影响的应用场景。
<details>
<summary>Original English</summary>

**Mauro Luchetti**: We can also check the lineage because, for instance, you can go on to the use case, open a use case that you want to check, open the object lineage. In this lineage view, you can see that, for instance, the use case here that is ticket optimization with AI is connected to an agent, is connected to another agent here, and also has AI models connected to it. So, we can have the full lineage of the use case and also be able, as Maurice said before, to be sure and also make modifications in case some parts of the lineage are affected by an outage or a problem and go back to the use case affected.

</details>

### 企业开发周期与 CI/CD

**Mattia Redaelli**: 接下来，关于**企业开发周期**，我们讨论了很多关于**元数据**和**注册表**的内容，但 Amplifon 的开发者实际上是如何开发 MCP 服务器和代理到代理服务器以部署到**生产环境**的呢？我们部署并开发了两个仓库，一个用于 MCP，一个用于代理到代理协议。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: So, moving into the enterprise development cycle, so we talked a lot about metadata and registries, but how do actually Amplifone developers develop MCP servers and agent to agent servers to deploy them in production? We deployed and developed two repositories, one for MCP and one for agent to agent protocol.

</details>

**Mattia Redaelli**: 这两个仓库是 GitHub 上的**模板仓库**。因此，开发者和团队可以从这些模板开始，逐步迁移到生产环境。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: These two repositories are template repositories on GitHub. So, then developers and teams can start from from them and work their way up to production environment.

</details>

**Mattia Redaelli**: 我们的想法是，这两个**蓝图**（blueprints）实际上提供了**样板代码**（boilerplate），以及现成的**基础设施**和**工具**。例如，**Docker 文件**、**包管理器**。两者都是 **FastAPI** 服务器，因此暴露方式相同。此外，**认证**和**成本跟踪**（cost tracking）也是在蓝图内部处理的。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: The idea is that these two blueprints actually have boilerplate provided and also infrastructure and tooling already present. So, for instance, Docker files, package manager, both are fast API servers, so they are exposed in the same way. And also the authentication and cost tracking cost tracking is handled inside the blueprint.

</details>

**Mattia Redaelli**: 我们还集成了 **LongFuse**，这是一个我们在平台层面部署的**可观测性工具**。因此，开发团队还可以跟踪他们的代理，运行评估，并检查代理的性能。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: We also have an integration to LongFuse, which is an observability tool that we deployed at the platform level. So, the development teams can also trace their agents, run evaluations, and check how the agent is performing.

</details>

**Mattia Redaelli**: 此外，**八路服务器蓝图**是**无关框架**的（agnostic），它不基于特定的框架，如 LangChain 或 Agno，而是由接口和端口组成，这样每个团队都可以使用自己喜欢的框架来实现解决方案。重要的是，它们提供与蓝图中保存的相同的接口。这样，开发对开发者来说就更容易了，他们可以专注于代理的实际价值。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: Also, the eight way server blueprint is agnostic, so it's not based on a particular framework, so LongChain or Agno or any other framework, but actually is composed of interfaces and ports so that every team can implement their own solution in their framework of choice. The important thing is that they provide the same interface that we saved in the in the blueprint. So, that uh the development is uh easy on the developers and they can focus on the actual value of the agent.

</details>

**Mattia Redaelli**: Mauro 提到了我们在 **A2A 蓝图**和 **MCP 蓝图**中已经实现的 **CI/CD**。想法是，一旦你完成了开发，你可以标记一个特定的分支，GitHub Action 就会启动。它不仅会在我们的构件仓库（artifact repository）中发布 Docker 镜像，还会发布该代理的元数据，即八路协议的代理卡和 MCP 的 server.json，到注册表的后端代理。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: So um Mauro talked about the um CICD uh that is in place in the um uh A2A uh blueprint and also the MCP blueprint. Uh the idea is that uh once you are ready with your development, uh you can tag um a certain branch and uh GitHub action so uh starts and uh uh all not only publishes the Docker image on our artifact repository, uh but also publishes the metadata of that agent so the agent card for uh agent-to-agent protocol and the server.json uh for MCP uh onto the uh backend uh let's say proxy of the the catalog of the registries.

</details>

**Mattia Redaelli**: 在这张图中，我们还可以看到，如果任何 AI 代理需要调用 MCP 或 A2A 代理，它们可以通过我们部署的 **APG AI 网关**进行。这两个代理（MCP 的和 A2A 的）会查找实际的代理和 MCP 目录，以检索代理想要调用的后端的确切 URL，然后代理会通过另一个头（header）进行身份验证，以访问实际的服务器。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: Um in this image we can also see that um in case any AI agents uh needs to call either an MCP or an A2A proxy, um the idea is that they can go through the um APG AI gateway that we deployed and um these two proxies, so the MCP one and the uh A2A one, um go uh look up into the uh actual catalog of uh agents and MCPs to retrieve the actual URL of the backend that the agent uh wants to call and then the agent authenticate itself uh with another header um onto the the actual server.

</details>

### 成果与未来展望

**Mattia Redaelli**: 所以，从商业角度来看，我们通过 Amplify 平台和开发的注册表实现了什么？我们现在有一个**目录**，用于实现治理。我们看到了在整个组织和多个团队中部署的 MCP 和 A2A 服务器。我们对跨用例采用的**应用场景、代理、工具和模型**进行了**完整可追溯**。然后，我们为开发者提供了**生产就绪的蓝图**，以便他们从标准化的基础开始，专注于用例中的业务逻辑。此外，还有用于将服务器部署到生产环境以及将元数据导入注册表的 **CI/CD 流水线**。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: So to bring it back to the business perspective, what we achieved with the amplify platform and the registry uh we developed, we have right now a catalog uh to to make the governance happen. So we see the MCP and A2A server that we deploy across the organization and across multiple teams. Uh we have a full traceability of the use cases, agents, tools, and also models adopted um across across the use cases. Then we have the production ready blueprints for developers to start from something standard across across teams, but uh ready for building and focusing on um the business logic in the use cases. Then we have the CICD pipelines that ties for deploying the servers to production, but also the metadata into the registry.

</details>

**Mattia Redaelli**: 当然，这个平台的工作仍在进行中，我们正在不断增长其能力。所以，请随时与我们联系，保持沟通，如果您有类似的观点或想讨论其他内容，都非常欢迎。谢谢。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: Of course, it is still in progress the the work on this platform, so we are keep growing the capabilities. Uh so feel free to to reach out to us and keep in touch if you have any similar uh point of view or also uh something different that you want to discuss, more than welcome. Thank you.

</details>

**Mattia Redaelli**: 随时与我们联系。
<details>
<summary>Original English</summary>

**Mattia Redaelli**: Feel free to reach out.

</details>