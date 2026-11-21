---
author: The Pragmatic Engineer
date: '2026-10-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MDUYSMJmi8A
speaker: The Pragmatic Engineer
tags:
  - ai-infrastructure
  - agent-governance
  - code-review
  - microservices
  - developer-productivity
title: Uber 工程演进：AI 基础设施、智能体治理与代码审查变革
summary: 本文通过 Uber 资深工程师 Uday 的视角，深入解析了 Uber 在 AI 时代的工程转型。重点探讨了统一模型网关、MCP 网关及 AI Guard 等核心基础设施，分析了从微服务到智能体工作流的演进，以及代码审查流程在 AI 辅助下的自动化变革。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Uday Kiran Mendis Shetty
  - Gergely Orosz
companies_orgs:
  - Uber
  - WorkOS
  - Linear
  - Turbo Buffer
products_models:
  - AI Guard
  - MCP Gateway
  - Whiteboard
  - Capri
  - Airlock
  - Linear Diffs
  - Turbo Buffer V3
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 播客引言：Uber 的工程演进与 AI 基础设施

**Gergely Orosz**: 现在的流程是怎样的？今天有什么最新进展？使用了哪些工具？你平时用它吗？我们提供了一个兼容 OpenAI 或 Anthropic 标准的 API，来自所有供应商的所有模型——无论是开源还是闭源，都由这个统一网关作为前置入口。

<details>
<summary>Original English</summary>

**Gergely Orosz**: ¿Cuál es el proceso? ¿Novedades de hoy? ¿Qué herramientas? ¿Lo usas? Proporcionamos una API, compatible con OpenAI o Antrópico y todos los modelos de todos los proveedores, con abierto o escalas cerradas, están detrás de esto puerta.

</details>

**Gergely Orosz**: 什么是 AI Guard？我们的核心诉求是确保绝不向外部发送任何属于用户的机密内容。大约在 2025 年 4 月，我们开始着手开发 MCP 网关（MCP Gateway），其架构定位与模型网关类似。这是所有内部与外部工具的统一入口网关。我们拥有超过 100 种节点类型、超过 130 种边/连线类型，而且这还只是大约几倍于早期状态的当前最新数据。

<details>
<summary>Original English</summary>

**Gergely Orosz**: ¿Qué es AI Guard? Queríamos Asegúrese de no hacerlo enviamos ninguno para los usuarios confidencial contenido. Aproximadamente en Abril de 2025 nosotros Comencé a trabajar en MCP Puerta de enlace, similar a Modelo de puerta de enlace. Este es el único puerta de entrada para todos herramientas. Tenemos más de 100 tipos de nodos, más de 130 tipos de costillas, y estos son datos actuales a un estado de aproximadamente 3- tiempos antiguos.

</details>

**Gergely Orosz**: 我们将其称之为“白板”（Whiteboard）。从本质上讲，你可以基于它创建自己的独立副本并部署一个分支。那么这套机制服务于什么场景？对于我们一些最复杂、最棘手的平台，我们采用了流量捕获与重放（Capture & Replay）。仅借助中间件软件的辅助，它就能够精准捕获线上的真实生产工作负载流量。

<details>
<summary>Original English</summary>

**Gergely Orosz**: Nosotros Lo llamamos pizarra. En esencialmente, puedes crea el tuyo propio una copia que despliega una rama, sobre ¿Para qué trabajas? Para algunos de nuestros el más difícil plataformas que utilizamos Capture Repetición. Puede para capturar lo real tráfico de trabajo para con la ayuda de solo un intermedio software software.

</details>

**Gergely Orosz**: 与前 AI 时代相比，如今你的软件开发心智模型发生了怎样的变化？在我的整个工程生涯中，在此之前从未见过工作模式发生如此巨大的变革。例如，Uber 的工程师今天究竟使用哪些内部工具来构建和交付软件？

<details>
<summary>Original English</summary>

**Gergely Orosz**: ¿Cómo está cambiando el tuyo? modelo mental desarrollo de software comparado con la era anterior ¿AI? En todo mi tiempo en ingeniería nunca antes vista No había ninguno tan grande cambios en mi trabajo. Por ejemplo, ¿Cuáles son los internos? herramientas usar Ingenieros de Uber para creación software software ¿hoy?

</details>

**Gergely Orosz**: 在本期节目中，我们将从 Uber 资深工程师之一 Udaya Kiran Mendis Shetty 提供的一手视觉资料中获得独家内幕视角。如今，Uday 负责领导包括 Wisdom 等基础设施在内的大量前沿工作。如果你想深入了解大型科技公司的底层基础设施是如何构建与运转的，那么这一期绝对不容错过。它不仅速度飞快、成本极低，而且具备极强的扩展性。在今天的这期节目中，我们将讨论数十个智能体代理以及辅助编码的工具。工具本身往往是最简单的部分，真正的复杂性在于围绕工具所建立的一整套运行环境与治理体系。

<details>
<summary>Original English</summary>

**Gergely Orosz**: Nosotros lo conseguiremos Vista exclusiva desde adentro en materiales visuales de uno de Ingenieros de Uber de el más veterano, Udaya Kiran Mendis Shetty. Hoy Uday cabezas una grande parte del trabajo en solía hacerlo otros. Fundamentos Wisdom and others. Si usted quiero entender cómo tecnológico infraestructura episodio para ti. Este texto completo . It's fast, cheap and extremadamente escamoso. Episodio de hoy dos docenas agentes. Uno de herramientas para codificación. Las herramientas son La parte fácil. La dificultad radica en todo lo que les rodea.

</details>

### 赞助商介绍：WorkOS Airlock 与智能体权限治理

**Gergely Orosz**: 在这里，我必须特别提一下我们本季度的赞助商 WorkOS。在落地 AI 智能体时，一个始终存在且极其复杂的痛点就是访问权限管理：你是否愿意让智能体永久拥有它所能触及的一切资源的完全访问权？难道你要一直机械地点选批准每个请求，直到彻底懒得阅读它们为止吗？针对这一痛点，WorkOS 专门打造了 Airlock（气闸安全网关）。

<details>
<summary>Original English</summary>

**Gergely Orosz**: Aquí es donde tengo Menciona al patrocinador de nuestra temporada, WorkOS. Una de las constantes problemas complejos con Los agentes son derechos acceso. ¿Quieres? para que el agente tenga acceso permanente a todo lo que hace ¿Puede tocar? Y si tú acabas de aprobar cada solicitud hasta ¿Dejas de leerlos? Empresa WorkOS creado para esto Burbuja de aire.

</details>

**Gergely Orosz**: Airlock 是一个独立的授权与隔离层，它拦截在智能体与其准备调用的各类工具之间，会严格根据智能体的意图以及你预先制定的策略规则来审查每一笔请求。你可以使用自然语言编写这些业务安全规则；智能体自始至终无法窥探你的敏感凭证和账户数据，而且每一个拦截或放行裁决都会完整记录在审计日志中。Airlock 能够与各种编码智能体（例如 Fabric Code 和 Codex）无缝协作。WorkOS Airlock 提供了一条切实可行的途径，让各类智能体既能胜任真实复杂的实际工作，又不会引发权限泛滥的风险。欢迎访问 workos.com/airlock 了解详情。

<details>
<summary>Original English</summary>

**Gergely Orosz**: La esclusa de aire es un nivel autorización, que se coloca entre sus agentes y herramientas que ellos llaman y Él revisa a todos solicitud de conformidad las intenciones del agente y tus reglas. Tú escribir las reglas en lenguaje sencillo, agentes nunca ver tus cuentas datos y cada uno El veredicto queda registrado. en la revista. Él trabaja con agentes para codificaciones tales como Código de Telas y Códice. WorkOS Airlock —este es el camino, gracias a a quiénes agentes realizar real trabajo sin exceso permisos. Echa un vistazo al workos.com/airlock.

</details>

### 嘉宾欢迎与 Uber 早期经历回顾

**Gergely Orosz**: Uday，欢迎来到我们的播客节目！

<details>
<summary>Original English</summary>

**Gergely Orosz**: Udacity, bienvenido a podcast.

</details>

**Uday Kiran Mendis Shetty**: 非常感谢你的邀请！我一直都在密切关注你的内容。看到你所产生的深远行业影响力，以及你为所有工程师群体持续发布的精彩技术文章，真的令人惊叹。因此，今天能来到这里与你交流，聊聊我们正在推进的工作，对我来说是非常大的荣幸。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Muchas gracias por eso. invitado. Estoy siguiendo. tu trabajo. Es asombroso verlo, ¿Qué influencia tienes? hecho, y todo eso gran contenido que estás publicando para Todos los ingenieros. Entonces Es un gran honor para mí. estar aquí y hablar con hoy sobre ti, ¿Qué estás haciendo?

</details>

**Gergely Orosz**: 确实，在《The Pragmatic Engineer》创办之前，我们在 Uber 就曾共事过。虽然当时我们没有紧挨在一起并肩工作，但我对你的工作成果一直非常了解。你最初是什么时候加入 Uber 的？

<details>
<summary>Original English</summary>

**Gergely Orosz**: Bueno, trabajamos. juntos antes de la aparición Ingeniero pragmático, todavía en Uber. No de modo que uno al lado del otro, pero también sabía de tu trabajo. Cuando Acabas de unirte ¿A Uber?

</details>

**Uday Kiran Mendis Shetty**: 是的，我是 2015 年 5 月加入 Uber 的。事实上，当初推荐我入职的那两位工程师至今仍然留在 Uber 工作。当时我加入了我们的实时 API（RT API, Real-Time API）团队。那段时期我们正在全力推进将原有的单体架构拆分为微服务集群，而我主要负责我们面向所有移动客户端应用的 API 网关。例如，我深度参与了移动端通信协议的全面改造。自那以后，我陆续在许多不同的核心业务平台工作过：从订单执行履约平台、Uber for Business 企业版，到司机车主注册入驻以及市场动态定价系统。而过去的一整年，我的精力则全面投入到了面向内部用户、技术支持团队以及最终终端用户的 AI 智能体体系中。过去这一年投身该领域的工作节奏，真的宛如坐过山车一般跌宕起伏。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Sí, me uní. Uber en mayo de 2015. De hecho, esos dos ingenieros que me Recomendado, aún Trabajan aquí. Eh, entonces Me uní a nuestro comandos API en tiempo real. Nosotros, Este fue un período en el que nosotros intentó romper nuestros monolitos en microservicios, y yo Trabajamos en nuestra API. una puerta de entrada para todos nuestros aplicaciones móviles. Y , por ejemplo, yo Trabajé en el cambio nuestro móvil protocolo. Desde entonces yo Trabajé en muchos diferentes plataformas empresariales: desde la ejecución pedidos, Uber para empresas, antes de registrarse propietarios y precios en mercado. Y el año pasado fue dedicado IA agente en cuanto a nuestros usuarios, servicios de apoyo, final usuarios, etc. Sí, el año pasado. El trabajo en esto fue real " Americano "sierras".

</details>

### 实时 API（RT API）的设计与协议演进

**Gergely Orosz**: 没错。对于那些当年没有和我们一起在 Uber 共事过的听众朋友们，我们能否稍微回顾梳理一下：究竟什么是“实时 API”（即我们常说的 RT API）？它的底层包含了哪些核心组件？它在整个系统拓扑中为什么具有如此举足轻重的地位？又为什么它需要承担如此庞大的并发流量与系统负载？

<details>
<summary>Original English</summary>

**Gergely Orosz**: Sí, y para aquellos que no lo hacen trabajó allí con nosotros, ¿Podemos tener un poco? recordar qué es API en tiempo real, o API RT, como la llamamos Se le llamó ¿Qué era lo que había dentro? ¿Por qué era importante? ¿Y por qué estaba en sus manos? tan grande ¿carga?

</details>

**Uday Kiran Mendis Shetty**: 回溯到我刚加入 Uber 的时候，整个公司实际上只有两个核心服务。一个叫做调度服务（Dispatch），是用 Node.js 编写的；另一个是 API 服务，是用 Python 编写的。在那个时期，调度服务负责处理乘客端与司机端的所有通信流量，当时使用的通信协议也相当简单直白——即所谓的“4 秒 Ping 轮询协议”，通过周期的轮询心跳来维持系统的正常通信与状态同步。而一旦行程宣告结束，我们便将数据移交给 Python API 服务，由它来集中处理行程结束后的全部后续事务，包括费用结算、账单凭证生成以及其他关联数据流。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Entonces, cuando yo nos hemos unido, tenemos Solo había dos servicios en Uber. Uno se llamaba despacho, escrito en Node.js y la API escrita en Python. En ese tiempo El servicio de despacho se encargó de todo tráfico de pasajeros y conductores y protocolo Entonces fue suficiente simple. Fue así llamado 4 segundos protocolo ping, que siempre que se proporcione en perfectas condiciones sistemas. ¿Y cuándo? El viaje ha terminado, nosotros datos pasados ​​ a la API, que lo procesó todo Después del viaje: pagos, recibos y el resto.

</details>

**Uday Kiran Mendis Shetty**: 正是在这种背景下，RT API（实时 API）应运而生。它的首要目标是将底层的全部内部微服务与上层移动端应用程序彻底解耦并抽象开来；与此同时，我们需要彻底革新通信协议，从原先简陋的 4 秒固定轮询机制，转向一种既具备规范 REST API能力、又支持服务器到客户端双向持久连接的混合通信架构。我们将其称为服务端推送协议（Push Protocol）。之所以必须这样做，是因为我们的出行应用本身高度依赖动态上下文，物理现实世界中任何细微的变化在短短几秒钟内都会频繁发生。因此，只要物理世界出现任何状态变迁并触发更新，我们就必须极度高效地将最新状态实时推送并同步给乘客与司机双端。RT API 是全公司 QPS（每秒请求数）吞吐量最高的核心网关服务之一。最初的许多年里，我们沿用了 Node.js 与 Python 技术栈，因为在那个历史发展阶段这是最自然的工程选型；但随着业务规模扩张，我们随后使用 Go 语言对整个系统进行了彻底重构。直到今天，它依然是整个 Uber 内部吞吐指标最高、承载流量最顶峰的服务之一。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Entonces nació RT API, abstraer todo servicios internos y aplicación móvil y también cambiar protocolo de simple 4- un segundo para tal, donde tenemos tanto una API REST como conexión desde el servidor al cliente. Nosotros Lo llamó empuje- protocolo, porque nuestra aplicación es muy dinámico, y eso es todo. cambia cada unos segundos. Por lo tanto, necesitábamos de manera eficaz estado de actualización aplicación como para pasajeros, así como para conductores, tan pronto como nosotros conseguimos unos nuevos Actualización, solo algo cambios en el mundo físico. Él fue uno de los servicios con el más alto indicador QPS y Durante años nosotros Se utilizó Node.js y Python, porque fue una selección natural En ese tiempo. Pero más tarde lo reescribimos para Ve, y sigue siendo uno de los nuestros servicios con el indicador más alto QPS en Uber.

</details>

### 微服务爆炸、治理挑战与平台化重塑

**Gergely Orosz**: 我想很多听众在听到“2015 年左右 Uber 竟然只有两个服务”时一定会大感意外。毕竟，业界人尽皆知 Uber 是微服务架构浪潮中最著名的代表范例之一，此前 Thuong 也曾做客本播客聊起过这段历程。关于微服务究竟是如何在公司内部如雨后春笋般爆发的，以及站在你的视角来看，服务数量在短时间内呈现几何级数暴增究竟意味着什么，你能否为我们还原当时的场景？

<details>
<summary>Original English</summary>

**Gergely Orosz**: Creo que los oyentes lo harán Sorprendido de escuchar: " Oh, en 2015 o sobre eso en Uber Solo había dos servicios "Después de todo, Uber es famoso. el auge de los microservicios, y Thuan estaba en él. podcasts. Él es un poco me lo contó, pero ¿podría usted, por favor? recuerda cómo surgieron ¿Estos microservicios? Y con tu punto de vista, que significaba repentinamente para conseguir esto ¿Número de servicios?

</details>

**Uday Kiran Mendis Shetty**: 确实如此，业内有大量的技术博客和讨论都在聚焦这一历史进程。就像我刚才提到的，在我刚入职时，核心就只有那两个庞大的服务。如果回看当年的大环境，公司正处于超高速狂飙突进的超高增长阶段（Hyper-growth Phase）：我们几乎以极高的频次连续进入不同国家的新兴市场，全球业务版图疯狂铺开，出行领域的客运产品线急速扩展，不久后又全力孵化并上线了 Uber Eats 外卖业务，其增长曲线同样异常陡峭。在那种业务背景下，全公司迫切需要一套标准机制，让各个业务研发团队能够以极致的速度独立自主地开发并上线任何功能特性，唯有如此才能匹配业务规模扩张的惊人步伐。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Sí, creo que hay muchos. blogs y muchos La gente está hablando de ello. . Entonces, cuando yo se unió, ya sabes... Como dije, tenemos Solo había dos servicios . Si recordamos aquellos tiempos fase de hipercrecimiento , constantemente entraron en los mercados nuevos países, amplió la cartera productos en el campo transporte y más tarde lanzó Uber Eats, que también se desarrolló. A nosotros era necesario mecanismo para que los equipos podría muy rápidamente crear cualquier funcionalidad. Para responder la escala con la que El negocio creció.

</details>

**Uday Kiran Mendis Shetty**: 因此，在那个阶段，我们在底层服务基础设施上进行了大量重度投资，目的就是让每个业务团队能够极其低门槛地完成服务的快速脚手架搭建、指标采集埋点、链路分布式追踪、事件监听接入、全方位可观测性监控以及自动化持续部署——覆盖整个生命周期的全套基础设施工具。在那个时代，开源社区和商业市场上并没有现成成熟的开箱即用软件方案能够直接支撑如此宏大的业务吞吐规模以及如此剧烈的功能迭代速率。因此，大量底层的支撑工具与平台组件在当时都必须由我们自己从零手写打造。这种工程自治的推力直接促成了一段服务爆发期，我们的服务拓扑在极短的时间内便从最初的区区几个服务，急剧膨胀到了数千个微服务。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: Atrás somos muchos invertido en servicio infraestructura para Los equipos lo tuvieron fácil servicios de construcción, métricas, seguimiento, escucha, observación, despliegue—todos esta gama de tareas. En ese momento no había muchos ya hechos soluciones de software para tal escala y tal velocidad de cambio, que teníamos. Y fue muchas cosas que nosotros entonces fue necesario Constrúyelo tú mismo. Esto creó un período crecimiento rápido, cuando nos mudamos de varios servicios a miles.

</details>

**Uday Kiran Mendis Shetty**: 大约在 2018 到 2019 年期间，我们深刻意识到了无序蔓延的弊端，开始着手全面推行标准化治理。我们将后端编程语言收敛收口，确立以 Go 和 Java 作为全公司的主要核心语言；我们对老旧的技术栈进行了深度的现代化升级，并投入了巨大精力去梳理重塑架构分层，深入思考如何进行真正的平台化沉淀。经过多年持续深耕订单履约平台体系，我们在实践中成功将分散破碎的服务聚合收敛到了几个核心平台中。事实上，即便是今天，我们的微服务总量相比当时已经保持在一个非常稳定且受控的数量级，尽管在此期间 Uber 的整体业务规模与交易量又扩大了整整 10 倍，并且我们孵化并支撑了远比过去丰富多元的产品矩阵。正是得益于长期的平台化战略与持续的技术底座投资，我们今天依然能够以统一的全球化技术栈平稳运行在所有开展业务的国家与地区。我们拥有众多横向贯通的通用技术平台，通过标准统一的协作工具集同时为网约车移动出行（Mobility）与外卖配送（Delivery）等所有业务垂直方向提供稳定高效的支撑；这也赋予了我们极速孵化并上线全新业务垂直领域的核心竞争力，因为这套共享底座已经沉淀得足够深厚。

<details>
<summary>Original English</summary>

**Uday Kiran Mendis Shetty**: En algún momento entre 2018 y 2019. años nosotros estandarizamos nuestro lenguajes de programación, elegir Go y Java como principal, modernizado pila tecnológica y mucho tiempo dedicado niveles arquitectónicos , pensando en cómo construir una plataforma . A lo largo de los años, trabajando a través de nuestra plataforma cumplimiento de pedidos, en realidad lo somos redujo el número servicios a varios. Incluso ahora tenemos aproximadamente lo mismo número de servicios, Aunque nuestro negocio ha crecido 10 veces, y nosotros creamos significativamente más productos. Gracias a la plataformización y años de inversión, nosotros todavía usar único global pila tecnológica en todos los países donde Estamos trabajando. Hay muchos plataformas que servir a todos direcciones de movilidad y entrega para a través de la articulación herramientas y esto nos permite lanzar nuevos vertical, porque somos muchos

</details>

<!-- chunk 2/12 -->

### 优步工程团队的爆发式增长与全球化布局

**主持人**：……多年来在平台建设方面的投入。您能否讲讲您刚加入优步时，工程团队的规模是怎样的，后来又是如何壮大的？因为对于外界的人来说，似乎直到最后才真正意识到这种增长的惊人规模。

<details>
<summary>Original English</summary>

**Host**: ...invested in building platforms over the years. Could you tell me when you joined, what the Uber engineering team looked like and how it grew? Because it seems people on the outside didn't fully realize the sheer magnitude of this growth until later on.

</details>

**嘉宾**：我刚加入优步时，全公司大概只有600名工程师，当时整个Marketplace（核心撮合交易平台）团队也只有大约50到60位专家。在接下来的几年里，随着业务的极速扩张和流量的爆炸式增长，我们的工程团队迅速壮大到了数千人。到了2019至2020年，我们开始在全球不同地区大举扩张。现在，我们在全球拥有12个技术研发中心，几乎遍布我们业务开展的每一个大洲。这有助于我们针对超本地化（hyperlocal）市场打造定制产品，其中一些本地创新随后又在全球范围内被推广和落地，扩展到所有能够支持此类功能的市场。我认为这种布局不仅让我们能够吸引来自世界各地的顶尖人才，打造高度本地化的特色产品，同时还能支撑一套统一的全球通用技术底座。

<details>
<summary>Original English</summary>

**Guest**: When I arrived, there were approximately 600 engineers in total, and the entire Marketplace team at that time consisted of about 50 to 60 specialists. Over the following years, driven by business expansion and massive traffic growth, we grew by several thousand engineers, and in 2019–2020 we began expanding into different regions. Now we have 12 global tech hubs across nearly the entire world, on every continent where we operate. This helps us build products for hyperlocal markets, some of which are later scaled globally wherever we can deploy such functionality. I believe this gives us the opportunity to attract talent from all over the world, create specialized local products, and support a single global technology stack.

</details>

**主持人**：说到产品研发和技术栈：您过去一直负责平台工程，现在也依然在平台团队，对吧？

<details>
<summary>Original English</summary>

**Host**: By the way, regarding product development and tech stacks: you worked and are still working on the platform team, right?

</details>

**嘉宾**：是的。至少在我任职的前十年里，我虽然在多个业务线轮转过，但大部分时间都倾注在平台领域：开发者平台、面向工程师的AI Agent、面向公司其他业务部门的AI Agent，在此过程中我也参与了一些面向最终用户的AI项目。

<details>
<summary>Original English</summary>

**Guest**: Yes, well, at least during the first 10 years, though I worked across various business lines, I spent most of my time on developer platforms, AI agents for engineers, AI agents for the rest of the company, and along the way I also worked on some user-facing AI initiatives.

</details>

### 自研基础设施的黄金时代：从 RTAPI 到 UOwn 与 M3DB

**主持人**：您能带我们回到2015年，讲讲当时优步内部工具的演进过程吗？因为很多人当时都非常惊讶于优步竟然拥有如此庞大且自成体系的自研工具链。大家都听说过RTAPI，但其实还有很多其他的核心基础设施，比如Morpheus、Edge Gateway等。您能否回顾一下2015到2016年间的情况：如果一名工程师加入优步，他们当时使用的是哪些工具？这些工具又是如何被研发出来的？我这里指的当然不仅是移动端工程师主要使用的工具，还包括更广泛的基础设施。

<details>
<summary>Original English</summary>

**Host**: Can you take us back to 2015 and talk about how internal tooling evolved at Uber? Because people were often surprised seeing just how many proprietary internal tools we had. People talked about RTAPI, but there were other things like Morpheus, Edge Gateway, and more. Could you tell us what it was like in 2015–2016: if an engineer joined Uber, what tools did they use and how were they developed? I don't just mean the primary ones that most of our mobile engineers worked with, of course.

</details>

**嘉宾**：确实如此。我认为在那段时期，考虑到我们所面对的庞大业务规模以及极快的增长速度，市场上几乎没有任何开箱即用的现成商业产品能够满足我们的要求。因此，除了前面提到的RTAPI和Edge Gateway之外，我们还必须自主构建许多系统——比如一个名为UOwn的服务所有权系统，它能让公司内的任何人立即确认某项特定功能或服务的归属负责人。

<details>
<summary>Original English</summary>

**Guest**: Yes, definitely. I think back in those days, considering the sheer scale and the speed at which we were growing, there were very few off-the-shelf products that could serve our needs. So besides RTAPI and Edge Gateway which were mentioned, another system we had to build was called UOwn, which allowed anyone in the company to determine who owns a specific feature or service.

</details>

**主持人**：这与服务治理和监控很像，对吧？当工程师处于值班（on-call）状态时，比如一旦线上发生故障，可以立即查出哪个团队负责、谁在值班等等，是这样吗？

<details>
<summary>Original English</summary>

**Host**: It was similar for services, right? And you could check this while on call—for instance, in the event of an outage or failure, you could immediately find out which team is responsible for it, who is on duty, and so forth, right?

</details>

**嘉宾**：完全正确。而且随着工程团队人数的指数级增长，我们还必须构建一个无缝衔接的一体化系统，把我们所有的工程方案设计、产品规格说明书等技术文档统一汇集到一个地方。同时，我们还必须打通并汇总所有的线上突发事件（incidents）。当时我们极度重视事故的复盘与处理机制，深入分析每一次故障并从中总结改进经验，为此我们自研了许多非常优秀的故障管理工具。

我认为最严峻的技术挑战之一在于指标监控系统。早在2015至2016年，我们每秒需要摄入和处理的高基数监控指标就已逼近5亿条。当时市面上根本没有任何一个成熟的现成时序监控系统能够承受这种级别的吞吐量和基数要求。正是这种极端的业务压力直接催生了M3DB的诞生。后来M3DB全面开源，围绕它甚至成立了一家商业化公司。M3DB使我们拥有了处理如此庞大指标规模的能力。

<details>
<summary>Original English</summary>

**Guest**: Yes, definitely. And with the rapid growth rate of engineering headcount, we also had to create a seamless system for our engineering design docs and product RFCs, bringing them all together into a single place. We also had to work on centralizing all of our incidents in one place. We were intensely focused on how we processed incidents and what post-mortem lessons we drew from them, so we built a lot of really solid tools for this.

I think one of the most difficult challenges was metrics. Even back in 2015–2016, we had to handle close to 500 million metrics per second with very high cardinality. There was simply no off-the-shelf metrics system that we could use at that volume. This led to the creation of M3DB, which was later released as open-source software, and an entire commercial company eventually formed around it. It allowed us to build the tooling required to process the massive volume of metrics we had.

</details>

### 从 Michelangelo 到 Cadence：重塑机器学习与工作流编排

**嘉宾**：此外，我们还必须自研端到端的全生命周期机器学习平台，因为我们线上同时运行着数百个各类型的机器学习模型。这个平台需要覆盖从特征工程、模型构建与训练，到模型监控与在线推理服务的整个生命周期。

<details>
<summary>Original English</summary>

**Guest**: We also had to create our own end-to-end machine learning platform, because we had around hundreds of machine learning models in production. It had to cover the complete lifecycle from feature engineering and model training to monitoring and online serving.

</details>

**主持人**：这就是著名的 Michelangelo（米开朗基罗）平台，对吧？

<details>
<summary>Original English</summary>

**Host**: This is Michelangelo, right?

</details>

**嘉宾**：对，就是 Michelangelo。例如就在几个月前，我们还对外开源了我们的深度学习框架以及 Michelangelo 基础设施的一部分组件。正如大家所见，我们在底层构建了大量扎实、强大的核心基础设施积木。

另一个极具代表性的自研工具是 Cadence。当你思考某些长生命周期的业务流程编排时——比如持续多日的司机入驻流程（driver onboarding），或者某种跨周期的CRM营销活动——你会发现许多工程师过去常常针对系统的容错、一致性和状态管理去重复开发各自的Ad-hoc解决方案。为了彻底解决这一通用痛点，Cadence应运而生。它专门用于管理长周期的有状态分布式工作流，后来也完全对外开源了。

<details>
<summary>Original English</summary>

**Guest**: Michelangelo, exactly. And for example, just a few months ago, we open-sourced our deep learning platform and parts of the Michelangelo infrastructure. So there you have it: a lot of very good, robust foundational building blocks.

Another very interesting tool is Cadence. If you think about certain long-running workflows—for instance, processes that last several days like driver onboarding or multi-stage CRM campaigns—you could see many engineers implementing their own ad-hoc solutions for reliability and state management. This problem gave birth to Cadence, which orchestrates long-running business processes and was later open-sourced as well.

</details>

**主持人**：我想业界可能较少有人直接熟悉 Cadence，但有非常多的人都知道 Temporal，对吧？Temporal 要么是深受 Cadence 的启发，要么其核心理念完全承袭自 Cadence。

<details>
<summary>Original English</summary>

**Host**: I think fewer people might know Cadence directly, but many know Temporal, right? Which was either inspired by Cadence or inherited most of its core ideas.

</details>

**嘉宾**：我不能百分之百确定它是不是直接由 Cadence 开源演化而来，但两者确实有极大的渊源与共通之处——它就像是 Cadence 在优步外部的技术延伸与商业化演进，解决的正是 Cadence 在优步内部所解决的核心问题。这批创始人敏锐地察觉到了整个行业对这类基础设施的巨大真实需求，于是离开优步并在更大的市场空间中将其扩展开来。

但我想说明的核心模式是：当年在那种极端的规模下，有太多基础设施组件是业界没有现成方案、我们被迫从零自研的。而随着时间的推移，整个外部软件行业也在飞速发展成熟。如今，我们在技术选型上更加灵活：只要看到有独特的内部需求且外部无法满足，我们就自研；只要市面上有成熟优秀的产品，我们就直接采购；而一旦我们研发出了有价值的技术，并且它能对整个软件工程界产生积极影响，我们就会尽可能选择将其开源。

<details>
<summary>Original English</summary>

**Guest**: I'm not even entirely sure if it was a direct fork of open-source Cadence, but they share a tremendous amount in common—it is essentially an external evolution of what Cadence is and does inside Uber. The founders saw that there was a genuine industry-wide need for something like this, so they went out and scaled it well beyond Uber.

The general pattern I want to highlight is that back then, given our scale, there were so many things we had to invent from scratch. Over the years, as the broader industry matured, our strategy evolved. Where we have unique, unmet needs, we build; where third-party solutions exist, we buy; and when we build something novel that is valuable to the rest of the industry, we strive to open-source it whenever possible.

</details>

### 特性开关、多方市场实验与以“城市”为核心的基础设施设计

**主持人**：是的，我认为还有两款工具非常值得一提，因为我刚才正好回想起来：其中一个是 Morpheus。它是专门为优步深度定制打造的，与内部系统深度打通。工程师可以直接进入平台配置并启动实验，实时查看数据反馈。它不仅是一个实验平台，还与移动端各项功能特性紧密结合。在业务迅速扩展到如此多国家的背景下，平台必须提供高质量的配置中心，无论是用来配置后端微服务，还是管理特性开关（feature flags），抑或是支撑大规模科学实验。

<details>
<summary>Original English</summary>

**Host**: Yes, and I think two more tools are worth mentioning because I just recalled them: one of them is Morpheus. It was built specifically for Uber and deeply integrated across the board, right? You could go there, launch experiments, and immediately observe results. It was an experimentation platform deeply integrated with mobile features. With operations expanding into so many countries, you truly needed a top-tier configuration platform, whether for configuring backend services, managing feature flags, or driving experimentation.

</details>

**嘉宾**：没错，所有的功能上线都要经过特性开关管控，所有的策略调整都要经过严格实验。由于优步本质上是一个双边乃至三边撮合市场，系统的动态复杂性极高。因此我们的实验绝非简单的单体A/B测试，我们还大量采用了轮替实验机制（switchback experiments）。我们必须构建一整套兼顾实验编排与核心指标度量的严密系统，并且要对数据分析的统计效能进行深度把控，确保分析结果绝对真实可靠，能够直接作为关键业务决策的数据基石。

<details>
<summary>Original English</summary>

**Guest**: Exactly, so everything goes through feature flags and through experimentation. Because we operate a two-sided or three-sided marketplace, the dynamics are quite complex. This isn't just simple A/B testing; we also rely heavily on switchback experiments. We had to build an experimentation and metrics platform, as well as rigorous analytical pipelines, so that the conclusions we drew were statistically sound and trustworthy enough to guide major business decisions.

</details>

**主持人**：我记得当年大家总是在讨论，为什么优步非要自己重新造一套特性开关系统？但后来仔细一想：你能找出市面上任何一个将“城市”（city）作为一等公民对待的第三方开关产品吗？在优步的业务哲学与架构设计中，“城市”是一等实体（first-class citizen），其重要性不言而喻。我们的很多工具都是天然以“城市”为维度进行分流和统计的——例如在指标基数方面，每个城市都拥有其独立的指标集合。这时候你就会明白，外界其他公司根本没有遇到过这样奇特而严苛的约束条件，在那种庞大规模下，没有任何外部方案能直接套用。

<details>
<summary>Original English</summary>

**Host**: I remember people always asking why we had to build our own feature flag system. But then you realize: show me a third-party solution that supports cities natively. In fact, cities are first-class objects at Uber; they are critical. Many of our tools use cities, for example, for cardinality—each city has its own metrics—and then you begin to realize that nobody else faced those peculiar constraints. Nobody else encountered them at such a massive scale.

</details>

**嘉宾**：一点没错。“城市”这一维度在我们的技术基础设施中根植得极深。举例来说，对于某些最为核心的系统关键服务，我们甚至直接按照“城市”来进行底层的数据分片与架构隔离（sharding by city）。我们把系统流量按城市进行负载均衡与分级隔离，以便对不同层级的城市施行精细化治理。即使在今天，在我们承接流量的所有区域中，所有城市的流量路由也都是严格映射到特定物理集群的。在发生灾备或异常时，我们可以在任何时刻平滑地将某个城市的全部流量动态切换到另一个可用区域；并且我们在部署层拥有逻辑部署分组，集群入口流量会定向路由到对应的容器组。当然，这种严苛的隔离策略并不是应用在所有服务上，我们只对那些真正需要这种极高分片粒度和极端可用性保障的核心服务实施。

<details>
<summary>Original English</summary>

**Guest**: Yes, definitely. The city dimension is quite interesting and deeply embedded in our infrastructure. For instance, for some of our mission-critical services, we even perform sharding by city. We partition and distribute traffic loads by city to handle different tiers of cities, because we need to ensure that across all regions where we serve traffic, cities are routed to specific target regions. We can dynamically re-route a city to another region at any given moment. We also maintain logical deployment groupings where cluster traffic is directed to specific container pools. We don't do this for every single service, but strictly for those critical services where we require this exact level of sharding, isolation, and fault tolerance.

</details>

**主持人**：关于另一个系统我想请教一下，如果我没记错的话，我们当时一直在使用，并且……

<details>
<summary>Original English</summary>

**Host**: Another system I'd like to ask about, which if I recall correctly we used and which...

</details>

<!-- chunk 3/12 -->

### 从微服务到 Monorepo：DevPod 的诞生与演进

**Host**: 据说 DevPod 大概是在 2017 年研发出来的，在当时这可以说大幅领先于整个行业。它当时是如何出现的？后来又经历了怎样的演变？

<details>
<summary>Original English</summary>

**Host**: Parece ser desarrollado en 2017 año, es DevPods, y en ese momento ella era mucho por delante de la industria. ¿Cómo apareció en? ¿Qué es? ¿Transformado?

</details>

**Guest**: 是的，我想确实是这样。DevPod 出现的背景，与我们之前提到的微服务数量剧增直接相关。最开始的时候，我们采用的是微仓库（micro-repositories）架构，每个微服务都拥有自己独立的代码仓库。而那个时候，业内完全没有任何标准化的构建系统。每个服务都各搞一套，我们内部至少有两到三种构建系统、两到三种测试体系。甚至对于核心基础设施团队来说，想要更新一些通用库都会变得极其困难，因为必须逐个访问所有微服务去挨个执行升级。

<details>
<summary>Original English</summary>

**Guest**: Sí. Mmm, creo que sí. Antecedentes de DevPod está relacionado con el hecho de que ya hablamos de aumento en el número microservicios. Al principio teníamos microrepositorios, donde cada servicio tenía el suyo propio repositorio propio, y en ese momento tenemos no había ningún estándar sistemas de ensamblaje. En cada servicio fue algo propio, teníamos al menos dos o tres sistemas de ensamblaje, dos-tres sistemas pruebas, e incluso equipo central fue muy difícil cuando queríamos actualizar bibliotecas, paseo en todos los servicios y realizar una actualización.

</details>

**Guest**: 因此，大约在 2017 至 2018 年前后，我们转变了策略，全面过渡到了单体代码库（monorepo）。虽然底层依然是微服务架构，但所有这些服务都统一从 monorepo 中进行部署。我们按编程语言各划分了一个 monorepo：一个 Go 仓库、一个 Java 仓库、一个 iOS 移动端仓库、一个 Android 仓库等等。然而，随着代码库的规模越来越庞大，在本地笔记本电脑上拉取、构建并配置整套开发环境变得异常困难，工程师还要频繁去解决各类本地环境配置引发的问题。

<details>
<summary>Original English</summary>

**Guest**: Por lo tanto, alrededor de 2017-18 años cambiamos nuestro estrategia de transición a monorepositorios, aunque lo sea microservicios, pero todos se desplegaron los servicios de estos monorepositorios. En solo éramos uno de nosotros monorepositorio en cada idioma, así que tenemos era un monorepositorio para Go, uno para Java, uno para dispositivos móviles iOS, uno para Android, etc. Entonces, cuando la escala este repositorio estaba consiguiendo suficiente grande, era suficiente difícil de empezar colección, así como configurar todos estos sistemas en computadora portátil local, además, era necesario para resolver todo tipo de problemas con ajustes.

</details>

**Guest**: 回过头来看，我们当时构想的 DevPod 本质上就是云端开发环境，而且可以按需任意创建。我们为每个语言的 monorepo 都量身定制了专门的 DevPod。例如，如果我主要在 Java monorepo 中工作，我就会创建一个预先缓存了整套构建系统的 Java 版本 DevPod。这样一来，编译构建速度大幅提升。而且这些环境直接运行在云端服务器上，其性能远比工程师手中的笔记本电脑更加强悍。这就让我们在代码构建和自动化测试的时间上能够提供非常可靠的 SLA 保障，大家也再也不用为环境配置操心，因为我们可以把所有必要的依赖和工具全部预装好。

<details>
<summary>Original English</summary>

**Guest**: Atrás asumimos esto algo como DevPod es entornos de nube desarrollos, y pueden ser tener en cualquier cantidad. Tuvimos un DevPod para cada monorepositorio. Entonces si trabajo principalmente en Java-monorepositorios, yo estoy creando una versión Java de DevPod, que almacena en caché todo sistema de ensamblaje. Me hago más rápido colecciones. Esto funciona en máquinas en la nube que incluso más poderoso que portátiles. Así que tú puedes tener mucho buenos acuerdos de nivel de servicio (SLA) en cuanto al tiempo montaje y pruebas, y no necesitamos preocuparse por problemas con configuración, así que ¿qué podemos hacer? Instalar todo necesario herramientas preparadas.

</details>

### AI 时代的新赋能：从开发者工作区到 Mega-DevPod

**Guest**: 更有意思的是，随着人工智能时代的到来，智能体（Agents）同样需要类似的工作空间和云端环境，而我们早已将这套架构落到了实处。我们甚至构建了一个聚合所有仓库的“Mega-DevPod”，让 AI Agent 能够跨不同的代码库无缝创建 PR。它配备了适配各类仓库的所有必要工具，以便智能体在任何仓库中都能准确感知完整的上下文。这同时也促使我们在仓库的根目录下建立了 `agents.md` 和 `cloud.md` 规范，因为我们的构建和测试流程此时已经高度标准化。只要我们在顶层维护好这些配置文件，绝大多数团队就能立刻享受到显著的便利，根本无需深陷到各个具体模块的繁杂配置中。

<details>
<summary>Original English</summary>

**Guest**: Y ahora lo interesante es que con el advenimiento de la era inteligencia artificial incluso a los agentes necesito unos similares espacios de trabajo y entornos de nube y lo hicimos usar. Nosotros también creó un "mega-DevPod" con todos los repositorios, para que mis agentes puedan crear PR para diferentes repositorios. Lo tiene todo herramientas para trabajar en cualquier repositorios para ver el contexto en cualquiera de ellos. Él también nos ayudó crear agents.md y cloud.md en la carpeta superior repositorio, porque ahora tenemos estandarizado montaje y pruebas. Tan pronto como lo hagamos archivos de configuración nivel superior, la mayoría de los equipos recibir significativo benefíciese de inmediato. A ellos no hay necesidad para profundizar en cada configuración módulo.

</details>

**Guest**: 此外，在云端开发环境中，所有 AI 开发相关的 Pod 工具都是默认预装好的。当你登录进入开发环境时，甚至完全不需要手动安装 Cloud Code、Code X 或其他开源工具，它们早已开箱即用。这极大地方便了非工程技术人员，任何人在公司内部都能秒级拉起一个 DevPod，并立即上手使用 Cloud Code 或 Code X 开展工作。早期在云端开发环境上的战略布局确实带来了巨大的红利。多年来在基础平台上的持续投入，有力地支撑了我们今天在 AI Agent 技术上的演进；我们过去为了减轻工程师负担而打造的基础设施，如今也自然而然地简化了 AI Agent 的执行任务。

<details>
<summary>Original English</summary>

**Guest**: Y en entorno de desarrollo todas las herramientas del pod de desarrollo la IA se instala mediante por defecto. Por lo tanto, puedes ir a tu entorno de desarrollo. Tú incluso no hay necesidad instalar Cloud Code, Código X o código abierto. Ellos ya está en tu entorno desarrollos. Esto es significativamente simplificado incluso para no ingenieros en empresas de creación de desarrolladores cápsula y arranque instantáneo trabajar con Cloud Code o Code X. Sí, creo que sí. La presencia de nubes entornos de desarrollo en una etapa temprana ayudó mucho. Creo que los años inversión en las plataformas también son muy nos ayudó en desarrollo de agentes tecnologías, porque poder usar todo creado por nosotros para hacer el trabajo más fácil ingenieros, así es auto-simplificante tareas para nuestro agentes.

</details>

### 探索当下的技术架构：Uber 的 AI 基础设施演进

**Host**: 在我们继续深入探讨当前现状之前，我想顺着这个话题多聊几句，因为很多技术脉络是环环相扣的。你们为基础平台和工具链做了大量开创性的建设，其中许多还是专门为 Uber 量身定制的。聊完了这些历史背景，现如今整体的架构版图又是怎样的？目前的开发生态是什么形态？你们主要使用哪些工具？能否为我们概括介绍一下你们专门为 AI 铺设的基础设施底座，详细讲讲你们究竟构建了什么，以及背后的核心动因？

<details>
<summary>Original English</summary>

**Host**: Me gustaría un poco para hablar de ello, antes de continuar hasta el día de hoy, porque creo que mucho las cosas están conectadas entre sí tú solo. Fue creado tantas cosas para plataformas y herramientas, a menudo específicamente para Uber. Pero, habiendo discutido esto, ¿qué tal se ve todo hoy? ¿Qué aspecto tiene? ¿Desarrollo actual? ¿Qué herramientas utilizas? Tal vez podrías danos un breve resumen inspección de cimientos, que pusiste específicamente para IA y dime exactamente qué tú lo creaste y por qué.

</details>

**Guest**: 首先，特别是在人工智能领域，我们在非常早期就清楚地意识到：行业技术格局变化极快，底层硬件供给与前沿模型都在以惊人的速度迭代。因此，我们希望投资构建一组正确的基础积木，使其不绑定于任何特定的硬件架构或具体的模型厂商。这样无论外部环境如何变迁，我们都能极其轻松地在不同模型以及硬件解决方案之间自由切换。例如，在 2022 年底至 2023 年初 ChatGPT 刚问世时，我们便迅速启动了模型网关（Model Gateway）的研发。我们打造的这款模型网关，对外提供与 OpenAI 或 Anthropic 完全兼容的统一 API。

<details>
<summary>Original English</summary>

**Guest**: En primer lugar, especialmente en en el mundo de la IA, estamos muy al principio entendió que el paisaje está cambiando rápido, hardware provisión y los modelos también son rápidos están actualizados. Nosotros quería invertir en construcción correcta bloques que no son depender de equipo o modelos específicos. De modo que, independientemente de cualquier cambio que podría fácilmente cambiar entre diferentes modelos y soluciones de hardware. Nosotros, por ejemplo, comenzó a trabajar en puerta de enlace del modelo tras la aparición de ChatGPT a finales de 2022—en principios de 2023. Entonces creamos puerta de enlace modelo, que proporcionado por OpenAI-compatible o API compatible con Anthropic.

</details>

**Host**: 抱歉打断一下，那是在 2023 到 2024 年期间，对吧？

<details>
<summary>Original English</summary>

**Host**: Lo siento, eso fue ¿2023-2024, verdad?

</details>

**Guest**: 没错，是在 2023 年并一直延续到 2024 年初。当 ChatGPT 以及一系列 GPT 模型发布之后，我们迅速明确了目标：必须让全公司内部的所有业务团队都能以最低门槛接入模型、构建智能体。因此，我们推出了模型网关，它将底层的全部复杂性彻底封装起来，并在全局统一注入了企业的安全审计、合规策略以及端到端的全链路可观测性。这样一来，工程师只需指定组织 ID 或项目编号，就能在不同的模型版本或不同供应商之间任意切换，亦或是直接访问各类开源模型。其机制表现为一个路由选择层，请求统一打到网关，再由网关动态分发至目标系统——无论是彼时的 ChatGPT 还是其它同类模型。

<details>
<summary>Original English</summary>

**Guest**: Sí, en 2023 y más allá principios de 2024, cuando ChatGPT y modelos lanzados GPT, somos rápidos entendimos lo que queremos para que sea más fácil para todos a los equipos de la empresa uso y creando agentes en basado en estos modelos. Así que teníamos una puerta de entrada modelos, que escondió todo complejidad, proporcionando con estas son todas nuestras actividades seguridad y política, y también completo visibilidad de los procesos. Así que podrías cambiar entre diferentes modelos o diferente proveedores de estos modelos, solo usando ID organizaciones o proyecto para obtener acceso a cualquiera de modelos abiertos. Esto funcionó como opción modelos que rumbo a la puerta modelos, y él ya dirigió la solicitud a el sistema requerido— ya sea ChatGPT en ese tiempo u otro similar modelos.

</details>

### 基于 Michelangelo 的生成式 AI 平台与 AI Guard

**Guest**: 值得一提的是，这个系统完全是构建在 Michelangelo 平台之上的。在此之前，我们基于 Michelangelo 开发了专门的生成式 AI（Gen AI）产品套件。

<details>
<summary>Original English</summary>

**Guest**: Sí, y lo fue construido sobre la base de el mismísimo Miguel Ángel. Atrás creamos un producto Gen IA basada en Miguel Ángel.

</details>

**Host**: 噢，Michelangelo，这就是 Uber 著名的机器学习平台，对吧？

<details>
<summary>Original English</summary>

**Host**: Oh, Miguel Ángel, esto es de ellos plataforma de máquina aprendizaje, ¿verdad?

</details>

**Guest**: 没错。现在 Michelangelo 已经成为了全公司生成式 AI 的核心底座。你在 Michelangelo 上创建一个生成式 AI 项目，完成各项配置，并挑选所需的模型。随后你会获得一个唯一的项目 UID，将其直接注入到你的 Agent 中即可。因此，你能直接复用 Michelangelo 成熟的基础设施，在同一套坚实底座上开展 AI 模型评估及各项扩展能力的构建。回过头来看，这是一项非常具有前瞻性的早期投资，后来为我们带来了巨大的战略红利。

<details>
<summary>Original English</summary>

**Guest**: Sí, y ahora en la plataforma de Miguel Ángel es set de base para IA generativa. Estás creando un proyecto Gen AI en Miguel Ángel, configurarlo y elige el que necesitas eres una modelo. Entonces tú obtienes algo único el UID del proyecto que puede uso para sus agentes. Por lo tanto, tú tienes el mismo infraestructura Miguel Ángel para empezar crear específico para la IA calificaciones y otras cosas en el mismo cimientos. Mirando hacia atrás, yo creo que eso fue todo bastante temprano inversión que luego trajo beneficio significativo.

</details>

**Guest**: 关于 Model Gateway，我可以再简要梳理一下它的演进过程。那是在 2023 年底，随着第一批大语言模型（LLM）集中涌现，我们敏锐地察觉到公司内部各个业务团队都渴望在不同场景中应用这些技术，因此我们希望最大程度地简化他们的接入流程。于是我们将其作为 Michelangelo 平台上的一个新组件来实现，供各团队进行灵活定制。需要说明的是，Michelangelo 这套机器学习平台早在 2015 至 2016 年间就已经诞生了，也就是说它的建立远远早于大语言模型时代的到来。

<details>
<summary>Original English</summary>

**Guest**: ¿Qué es Model Gateway? Puedo hacerlo una breve descripción general de lo que creamos. Él fue a finales de 2023 año en que apareció primer conjunto de LLM. Nosotros rápidamente se dio cuenta de que muchos internos los equipos quieren usa esto para diferentes propósitos, y nosotros quería maximizar simplificar su trabajo. Esto se construyó sobre plataforma de Miguel Ángel como otro componente donde ellos pueden personaliza el tuyo. Y Miguel Ángel, para para recordarte, esto la plataforma de aprendizaje automático creada alrededor de 2015-2016 años. Es decir, ella fue creado mucho antes de la llegada del LLM.

</details>

**Host**: 确实如此。

<details>
<summary>Original English</summary>

**Host**: Así es.

</details>

**Guest**: 是的。目前我们在 Michelangelo 内部已经沉淀了一整套生成式 AI 组件。尽管目前我们正在研发的大量前沿能力尚未对外开源，但我们正在积极针对生成式 AI 领域开展多项技术演进。而 Model Gateway 正是这一系列成果中的先驱产品。在最开始的初始版本中，我们还没有健全的中介软件和拦截组件，绝大部分能力都是在最近一到两年内逐步补齐的。但对于公司内的任何团队而言，整体接入体验非常统一：他们只需创建客户端，传入在 Michelangelo 中初始化好的项目标识符以及认证凭证，其余的事情就全由平台搞定。我们对外暴露与 OpenAI 或 Anthropic 完全兼容的统一接口，无论是闭源商业模型还是各类开源模型，全部统一收敛在这一网关之后。而在今年，我们率先上线了一项名为 AI Guard 的防护机制。所谓 AI Guard，其核心目标就是严格确保我们绝不会向最终用户泄漏任何敏感机密数据。由于所有流量都必须经过网关这一单一入口，我们得以在这里注入这套中间件，对所有交互请求进行标准化的安全审查与防护拦截。

<details>
<summary>Original English</summary>

**Guest**: Y ahora en tenemos un conjunto componentes de IA de generación dentro de Miguel Ángel, y ahora estamos construyendo más muchas otras cosas aún no en la versión con código abierto. Pero estamos trabajando activamente durante muchos desarrollos para el mundo IA generativa. Pero Model Gateway fue el primero tal producto. En la versión inicial en no todos éramos así programas intermedios y componentes, y nosotros parte creada de ellos en el último año-dos. Pero para cualquier equipos en la empresa la experiencia se ve así: ellos crean cliente, proporcionar identificador el proyecto que ellos inicializado en Miguel Ángel, entonces símbolo desafío, y eso es todo. Nosotros proporcionamos una API, compatible con OpenAI o Antrópico. Entonces, todos modelos de todos proveedores, con abierto o escalas cerradas, están detrás de esto puerta. Este año nosotros el primero en añadir eso lo llamamos guardia de IA. ¿Qué es AI Guard? En esencia, queríamos asegúrese de no hacerlo enviamos al usuario ninguno confidencial contenido. Era uno de los caminos, el único el punto de entrada donde nosotros podría agregar esto programa intermedio, que podemos sucesivamente referirse a todos.

</details>

<!-- chunk 4/12 -->

### 统一接入点与开发环境配置管理

**Speaker A**: 这些项目……安全团队有机会参与到所有项目中，制定专门的安全策略或一整套通信规则。针对延迟约束，我们推出了一系列机制，这带来了极大的帮助，确保我们所有的项目在基础层面都遵循相同的标准。因为每个人都需要为每个用户或客户端进行归因。随后，在这一年的开发过程中，我们跟踪了项目和用户的成本。通过建立围绕它的这套基础设施，所有请求都经由它流转，避免了绕过管控的情况发生。这为我们提供了一个统一的入口点，不仅可以做路由，还可以用来做账单跟踪之类的事情。

<details>
<summary>Original English</summary>

**Speaker A**: los proyectos. Equipo de seguridad tuvo la oportunidad trabajar en todos especial política de seguridad o todo un conjunto de reglas comunicación. Tenemos se lanzan para restricciones de retardo . Esto fue de gran ayuda. Asegúrese de que todos nuestros proyectos tienen mismo estándar niveles básicos. Porque todos realizar atribución para cada usuario or client. Después, desarrollo durante el año, nosotros costos de los proyectos and users. Y pasar por uno infraestructura alrededor de esto. Todos Estoy pasando por esto. lo cual no pasaría Debido a esto. Esto nos da un único punto de entrada para también puedes seguimiento de facturación, cosas así.

</details>

**Speaker B**: 确实如此。能够跟踪账单情况、缓存命中率以及其他任何指标。而且现在，在我们继续推进的过程中，关于模型路由等方面的讨论也很多。我认为这可能是一个非常好的切入点供我们使用，因为我们所有的模型调用都会经过它。

<details>
<summary>Original English</summary>

**Speaker B**: Así es. Poder seguimiento de facturación, nivel de caché y cualquier otro indicadores. Y ahora, cuando nos mudemos Además, están pasando muchas cosas. discusiones sobre enrutamiento modelos, etc. creo Esto podría ser bueno el punto de entrada que nosotros podemos usar, porque todos nuestros modelos pasar a través de él.

</details>

**Speaker A**: 我觉得方向完全正确。为了让工程师能够更轻松地在不同模型之间切换，接下来的关键一步就是简化在不同工具与工作流环境之间的切换。例如，如果我平时使用 Cloud Code，之后又切换到 Codex，我就需要把所有的配置、技能、工具以及插件全部迁移过去。

因此在公司内部，我们将所有这些工具打包封装进一个名为 AI FX（AI 基础组件）的外壳中。它会预先安装在云端开发环境（dev pods）中，也可以安装在本地计算机上，并且我们引入了“角色画像（personas）”的概念。这些角色画像自带了一整套标准插件和技能包，因此任何工程师都无需自行安装繁琐的配置——他们开箱即用，就能获得一套立即可用的技能组合。

正因为我们对所有东西进行了统一封装，所有的配置都由中央集中管理。所以无论你在本地还是在 dev pod 中使用其中哪款工具，配置都是完全同步的。由此，我们能够以中心化的方式维护一套通用配置并推送到所有用户，同时用户特定的个性化参数也会在所有环境中保持同步。这极大简化了日常工作，我们现在拥有了一个统一的工具配置切入点。此外，我们还添加了一行状态提示，用于提供智能建议，并实时跟踪你在当前工具和会话内的消费支出。工程师完全无需手动进行任何显式配置，就能自动享受到所有这些附加能力。

<details>
<summary>Original English</summary>

**Speaker A**: Creo que voy por buen camino. con el fin de Fue más fácil para los ingenieros. cambiar entre modelos, siguiendo el paso fue simplificación alternando entre herramientas (durezas) . Por ejemplo, si yo Yo uso Cloud Code y Luego paso a Códice, lo necesito para transferir todos sus ajustes, habilidades, herramientas, todos los complementos. Entonces, nosotros internamente Vamos a envolver todo esto herramientas en una cáscara llamada IA FX (Fundamentos de IA), que previamente instalado en entornos de desarrollo (pods de desarrollo) o tal vez instalado en local computadora, y tenemos concepto de personas. Entonces, estas personas vienen con un montón complementos estándar y habilidades, así que sea qué ingeniero Ni siquiera es necesario No hay nada que instalar —ellos consiguen conjunto de artículos listos para usar habilidades que pueden ser usar inmediatamente. Porque nosotros Envolvemos todo, a todos. ajustes son guiados centralizado. Entonces incluso si tú usar cualquiera ¿Cuál de las herramientas? localmente o en dev- podi, configuración sincronizado. Por lo tanto podemos centralizado gestionar uno un conjunto de configuraciones, que se extiende a todos los usuarios y cualquier específico para el usuario parámetros sincronizado entre todos entornos. Y de nuevo bueno, eso es muy simplifica el trabajo, por lo tanto que ahora tenemos uno punto de entrada para traspuesta herramientas, y nosotros también añadió una línea indicar dónde podemos brindar asesoramiento y realiza un seguimiento de tu gastos dentro herramienta y sesión. Así que todos estos son cosas adicionales que podríamos agregar sin cualquier explícito configuración desde el lateral ingenieros.

</details>

### 预算层级体系与负责任的资源使用

**Speaker B**: 太棒了。关于支出跟踪，你们现在具体是怎么设计的？作为一名刚入职的工程师，或者假设作为一名资深工程师，我需要关心费用成本吗？这里的成本控制逻辑是什么样的？

<details>
<summary>Original English</summary>

**Speaker B**: Perfectamente. Y sobre seguimiento de gastos, ¿Cómo te acercas? ¿Esto ahora? Como ingeniero, ¿tengo que...? preocuparse si Me acabo de unir, Digamos que, como un anciano ingeniero, ¿debería? conocer los costos, ¿Sobre el costo? ¿Qué hay aquí? ¿lógica?

</details>

**Speaker A**: 你看，我们的初衷是让工程师能够顺畅访问任何可用的工具，同时我们设计了“支出层级（expense tiers）”的概念。在默认情况下，你会获得一定的基础额度，上面还有若干更高的层级。当你接近当前层级的额度上限时，你可以直接提交升级到下一层级的申请，而且只需要团队主管进行一次简单的审批即可。

这样一来，你就可以和项目的成本预算负责人讨论资金使用情况，比如你是如何分配和消耗预算的。这实质上是一次关于负责任使用计算资源的透明对话，对吧？我们绝不想限制工程师的创造力，如果他们正在进行一个合理的重点项目，他们应该能够根据实际需要消耗算力，因为归根结底，我们的目标是最大化业务收益。但与此同时，也必须保证资源被负责任地使用。

因此，我们尽量减少在层级切换过程中的繁文缛节与文书审批工作。工程师可以在我们提供的任何工具中随时查看自己当前层级内的花费以及总体消耗情况。此外，针对不同的受控自主 Agent，我们还划分了不同的层级。对于所有人机交互式的会话层级，我们设定了固定的支出上限；而对于某些后台自主运行的代码编写 Agent，它们则归属于独立的单独层级。通过这种分层机制，我们确保了整个体系的额度与成本能够被轻松治理。

<details>
<summary>Original English</summary>

**Speaker A**: Verás, queremos Los ingenieros tuvieron acceso a cualquier disponible herramientas, y nosotros Tenemos el concepto de niveles. gastos. Entonces para predeterminado usted obtienes una cierta Hay muchos niveles superiores. Cuando te acercas hasta el límite de tu nivel , puedes enviar solicitud para mudarse a siguiente nivel y solo necesitas aprobación simple gerente. Entonces tú puedes discutir con gestor de reembolsos proyecto, por ejemplo, ¿Cómo gastas tu dinero? fondos, y es sencillo conversación sobre responsable usando recursos, ¿verdad? Pero no queremos restringir ingenieros , incluso si ellos están trabajando en algo el proyecto correcto, deben tener capacidad de gastar cuanto necesario, porque al final queremos maximizar Benefíciate de esto. Pero también quieres para asegurarnos de que el uso es responsable. Entonces estamos intentando minimizar cantidad de papel trabajo requerido para cambiar entre niveles, y ellos se verá en cualquier ¿Cuál de nuestros herramientas, ¿Cuántos son? gastar dentro este nivel y en general. Y nosotros también tenemos diferentes niveles para varios controlados agentes. Así que para todos niveles interactivos tenemos un cierto límite gastos. Para algunos nuestros antecedentes agentes de codificación en estamos separados nivel independiente. Por lo tanto, garantizamos, que pueden fácilmente para gestionar todo esto.

</details>

**Speaker B**: 是的，我觉得这非常合情合理。即使我做自己的项目，我也能在限定的额度内清晰感知到各项开销。我理解这套机制的核心思想是避免把 token 浪费在无意义的琐事上，或者在毫不知情的情况下意外消耗掉大量额度。它建立了一种即时的反馈连接，提醒大家这些模型资源并非毫无代价。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, pero creo que esto tiene sentido, incluso si Yo los hago yo mismo. proyectos, lo sabré sobre sus propios gastos en dentro de cualquier el límite que tengo. Y lo entiendo correctamente. que la idea es para no gastar fichas en tonterías que no tienen sentido, o por casualidad no los quemes, sin siquiera saberlo él. Así de simple dar retroalimentación conexión que estas cosas no son son gratis.

</details>

**Speaker A**: 没错。我认为这种正向反馈是非常有益的。我们还有一个名为“成本控制（Cost Control）”的插件，它会在你的整个工作会话期间持续运行，并根据你的实际使用习惯给出个性化的优化建议。它会主动提醒：“嘿，看这里，你在这个项目以及当前会话中已经消耗了这么多费用；这里有一些实用的优化建议，采纳它们可以进一步优化你的成本画像。”

我认为这种机制在管理者与工程师之间促成了非常良性的沟通氛围，工程师也能收到切实有用的反馈，明确了解自己如何更高效地使用预算。在理解上下文窗口控制、合理选择模型尺寸方面，这为我们在实时工作中的探索提供了极大帮助，让工程师能够真正适应这个新时代的开发节奏。我们同样绝不希望看到无效率的算力浪费。

<details>
<summary>Original English</summary>

**Speaker A**: Así es. Creo la presencia de tales comentario útil, y también tenemos Hay un complemento llamado " control de costos", que trabajará durante todas tus sesiones y dará personalizado consejos basados ​​ en su uso. Él dice: "Oye, aquí ¿Cuántos sois? gastar en esto proyecto y esta sesión." Aquí tienes los consejos que necesitas puedes usarlo, para que aún más mejora tu perfil de costos". Y yo Creo que eso es todo. crea un buen discusión entre gerentes y ingenieros y ingenieros también recibir útil reseñas sobre cómo son eficaces están gastando dinero. Creo que es muy nos ayudó con estudiando en tiempo real respecto a contexto, elección tamaño del modelo a ingenieros estaban al tanto del trabajo en esta nueva era. Nosotros nosotros tampoco queremos gasto ineficiente.

</details>

### 构筑 MCP 网关与 API 工具生态自动化

**Speaker B**: 那么，你们基于 MCP 网关（MCP Gateway）在 AI 基础设施方面具体构建并发展了哪些底座？

<details>
<summary>Original English</summary>

**Speaker B**: ¿Y qué fundamentos tienes? construido o desarrollado con IA a través de ¿Puerta de enlace MCP?

</details>

**Speaker A**: 噢，好的。我想另一个重要的背景是：在 2025 年初的某个节点，随着 Cursor 开始迅速风靡，我们将其接入了内部系统；而 MCP（模型上下文协议）也大约在同一时间作为一项规范问世。我们当时迅速意识到：“嘿，如果我们能以简单标准的形式把所有内部工具完全开放出来，就能够真正指数级释放 AI 的威力。”而且我们不仅可以将它应用于辅助编程，更可以拓展至各类软件工程任务中。

因此，在 2025 年 4 月左右，我们开始着手研发 MCP Gateway——其架构类似于模型网关，是一个面向所有工具的统一接入网关。当时我们所有内部微服务已经拥有非常完善的 IDL 注册中心（IDL Registry），涵盖了无论是使用 Thrift 还是 Protocol Buffers 的服务。由于我们拥有全量的 IDL 规范，我们就可以自动为任意微服务生成对应的 MCP 规范。

<details>
<summary>Original English</summary>

**Speaker A**: Oh sí. Creo que uno más El fondo era En algún momento a principios de 2025 año en que Cursor comenzó marcar popularidad, nosotros Lo conectó, y MCP —esta es una especificación, que fue creado aproximadamente al mismo tiempo tiempo. Y rápidamente entendido: "Oye, nosotros Realmente podemos aumentar potencia IA, abriendo todo nuestro interno herramientas en de forma sencilla". Y entonces podríamos potencialmente usa esto no solo para programar . Pudimos usa esto para todo tipo tareas de software ingeniería. Por lo tanto, alrededor de abril de 2025 año en que comenzamos trabajar en MCP Gateway, ya sabes, como modelos de puerta de enlace. Él una única puerta de enlace para todos herramientas. Nosotros ya tuve uno bueno Registro IDL para todos nuestros servicios, independientemente de si ¿usan? Son Thrift o Proto. Dado que tenemos Especificaciones IDL, nosotros automáticamente generar Especificaciones MCP para cualquier servicio.

</details>

**Speaker B**: 我想向大家确认一下：你们的各个微服务对外发布接口契约时，采用的要么是 Thrift，要么是 Protobuf，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Y yo solo quería La gente sabía: tu Se publican los servicios o Ahorro, o Proto- amortiguadores como contratos, ¿No es así?

</details>

**Speaker A**: 是的。起初我们只使用 Thrift，后来引入了对 Protobuf 的支持。但在过去几年里，所有新增的新服务全部基于 Protobuf 构建；而几年前创建的那些老服务则大多使用 Thrift。当老服务进行架构重写时，各个团队通常都会迁移到 Protobuf。

但无论底层是 Thrift 还是 Protobuf，由于所有 IDL 都统一收录在一个注册中心内，我们便可以直接利用该注册中心为它们自动生成标准的 MCP 规格描述。这样一来，公司内的任何员工都可以进入 MCP Gateway 这一工具平台，查看所有由我们自动化生成的 MCP 服务器。

当你进入其中任何一个服务时，都能查看到基于现有 API 自动生成的所有工具列表。换言之，这些服务的 API 被无缝包装并呈现为了 MCP Tools。我们不仅能自动生成请求、响应结构体和描述文档，之后还会基于这些元数据，为 API 及其字段生成专门针对大语言模型优化过的 LLM 适配描述，从而避免让单个工具占用 3000 到 4000 个 token 的庞大开销。借助这种方式，我们可以面向大模型的消耗效率进行高度优化。

工程师只需要调整一下配置与安全策略，就可以直接启用这些工具，完全无需对底层业务代码进行任何改动。如果团队需要某种定制化的 MCP，我们内部也提供了一套构建框架，他们可以通过 MCP Gateway 轻松路由并接入自己的定制 MCP 工具。另外还有一个非常有意思的特性，我们……

<details>
<summary>Original English</summary>

**Speaker A**: Sí. Primero nosotros usado únicamente Ahorro, y más tarde añadió Compatibilidad con Protobuf. Pero todos los nuevos servicios para los últimos años —Todos están en Protobuf. Aquellos, que fueron creados hace unos años, Todo en Thrift. Y cuando ellos pasan por reescritura, Los equipos suelen están cambiando a Proto. Pero independientemente de si ¿Es Thrift o Proto? ya que todos los IDL que tenemos en un registro, nosotros podría usa esto regístrese para generar especificación típica MCP es para ellos. Así sea ¿Quién en la empresa puede? para entrar en esto herramienta, MCP Gateway y ver todos los servidores MCP que generamos automáticamente. Y si entrarás en cualquier ¿Cuál eres tú? puedes ver todo herramientas, creado sobre la base de esta API existente. Entonces, estos podrían ser API de aquellos servicios que presentado como Herramientas MCP. Nosotros automáticamente generar estructura solicitud, respuesta y descripciones. Más tarde nosotros también basado en Generamos descripciones de API optimizado para LLM descripciones para API y campos, para que no tengamos que ver herramientas por 3000-4000 tokens. Entonces podemos optimizar esto para modelo de consumo. Este es solo un cambio. configuraciones y políticas de seguridad y ellos pueden hacerlo encender. Ellos no deben ser ingresados No se han realizado cambios en el código. Si quieren alguno -qué MCP personalizado, en tenemos un marco para creación de tal instrumento, y ellos puede dirigir Su MCP personalizado a través de MCP Gateway. Otro algo interesante que tenemos lo

</details>

<!-- chunk 5/12 -->

### 第三方工具的 MCP 网关化与 CLI 投影

**Uber 工程师**：我们所做的是：将我们所有的第三方工具——无论是 Google 还是 Slack——都通过 MCP（Model Context Protocol，模型上下文协议）网关统一开放出来。这极大地减轻了管理和维护配置的负担，正如之前讨论 AIFX 时所提到的那样，对吧？因此，我无论如何都可以非常便捷地设置其中的任何工具，无论是内部工具还是外部的 MCP 工具。

在过去的几个月里，我们还将所有这些 MCP 工具全部转换为了命令行接口（CLI）形式。这样一来，你就能够像调用普通命令行程序一样启动并运行任何一个 MCP 工具。因此，如果有任何智能体（Agent）系统想要将其作为命令行工具来使用，它完全可以直接通过 CLI 来调用；如果它们希望使用传统的 MCP 协议交互方式，也完全可以直接继续使用 MCP。

<details>
<summary>Original English</summary>

**Uber Engineer**: hicimos: todos nuestros herramientas de terceros, ya sea Google, Slack, también abierto a través de Puerta de enlace MCP. Esto es significativamente reducido cargar en gestión configuraciones, ya que ya habló sobre AIFX, ¿bien? Entonces, yo podría establecería cualquier ¿Cuál de estos? herramientas de todos modos, ya sea interno o herramientas externas MCP. En los últimos meses también Convirtieron todos estos MCP en las interfaces interfaz de línea de comandos (CLI). Para que puedas lanzar cualquier MCP como CLI. Entonces, si algún agente el sistema quiere úsalo Como una interfaz de línea de comandos, puede hacer esto hacer. Si ellos desear usar MCP tradicional, ellos poder usar MCP.

</details>

**主持人**：我的理解没错吧？这一切之所以能够实现，是因为你们底层的 API 系统最初要么是由代码自动生成的，要么是高度标准化的——实际上大部分都是自动生成的——而且你们在公司内部早已经拥有了一套非常成熟完备的 API 平台基座。因此，在此基础上增加对 MCP 的支持，在某种程度上可以说是水到渠成、相对轻量的。当然，这其中肯定仍然需要大量的工程开发工作，但你比我更清楚这背后的架构优势。而现在，将它们创建为 CLI 命令行接口同样是一件相对自然的事情，因为在生成式 AI 浪潮来临之前，你们就已经奠定了极其坚实的 API 基础设施底座，对吗？

<details>
<summary>Original English</summary>

**Interviewer**: ¿Y estoy en lo cierto? Entiendo que eso es todo se hizo posible, por lo tanto ¿Qué es el sistema API? fue originalmente o generado, o escrito—mucho qué sucedió generado—y usted tiene Ya existía una plataforma para API. Así que añade MCP fue, bueno, hasta cierto punto trivial. Eso es, Por supuesto, había trabajo, pero entiendes, acerca de que yo. Y ahora La creación de CLI también es bastante trivial, porque tenías una base Antes de la IA, ¿verdad?

</details>

**Uber 工程师**：是的，完全正确。

<details>
<summary>Original English</summary>

**Uber Engineer**: Sí.

</details>

**主持人**：而现在，当你拥有了这些基础设施之后……这也是我开始在 Uber 身上看到的典型特征：你们在 2022 年之前就已经搭建好了一整套成熟的技术栈，所以在现有的技术积累之上，为它们叠加并接入 AI 基础设施就变得相当顺畅和高效。

<details>
<summary>Original English</summary>

**Interviewer**: Y ahora, cuando tienes esto...esto es lo que yo Estoy empezando a ver en Uber: creaste una pila cosas para 2022, y podría ser bastante fácil añádeles IA infraestructura.

</details>

### 从内部 API 网关到 MCP 网关的架构迁移

**Uber 工程师**：是的。而且负责开发我们 API 网关的正是同一个核心团队，他们顺理成章地承接了 MCP 网关的研发工作。也就是说，这批工程师在构建高并发、企业级 API 网关方面早已有极其深厚的实战经验。他们非常清楚如何进行各种协议之间的转换，也深谙各类 API 网关的核心机制与边缘场景。因此，我们团队能够以极快的速度将其落地构建出来。

我认为最显著的成效是在我们将 Google Workspace 以及所有的内部 Slack 工具完全集成进来的那一刻；它为整个公司催生出了令人难以置信的、高自动化的智能体工作流。工程师和业务人员几乎可以自动化任何他们想要处理的事情，对吧？在那一瞬间，从 Slack、Google 到 Jira、Linear，甚至任何平时看来较为特殊或边缘的内部工具与微服务，全部都可以直接通过一行 CLI 命令行调用轻松唤起。

这也是我们在思考这个技术领域时所确立的另一套基础设施基石：所有这些能力都属于平台无关、供应商中立的底层积木块。在我们看来，无论外部环境或技术选型如何演变，这套积木都是企业必须独立构建的核心资产，因为无论哪种智能体（Agent），最终都需要一个统一、标准且安全的通道来访问和操作你的实际业务工具。

<details>
<summary>Original English</summary>

**Uber Engineer**: Sí. Y el mismo equipo trabajando en nuestro puerta de enlace API también Trabajé en la puerta de enlace MCP. Es decir, ellos ya estuvieron involucrados en la creación pasarelas API. Entonces ellos saber cómo realizar cualquier protocolo transformaciones, cualquiera ¿Qué son las pasarelas API? Por lo tanto nosotros Pudimos hacerlo bastante rápido construirlo. Creo Fue especial notablemente cuando nosotros Espacio de trabajo de Google integrado y todos los nuestros Herramientas de Slack; él creó increíble trabajadores de agencia procesos. La gente podría automatizar eso lo que sea, ¿verdad? En ese momento, de Slack a Google, Jira, Linear, cualquiera Qué extraño herramienta o servicio interno estuvo disponible a través de una llamada a la interfaz de línea de comandos. Otro conjunto de fundamentos, sobre lo cual comenzamos pensar en esto espacio, compuesto de porque todas estas cosas pertenecer a categorías de independientes del proveedor y plataformas bloques de construcción, lo cual, en nuestra opinión, tendrá que crear independientemente de circunstancias, porque Los agentes necesitan forma de acceder tus herramientas.

</details>

### 单一代码库（Monorepo）中的 Agent Skills 体系与统一评估

**Uber 工程师**：接下来的另一个重要维度就是“技能”（Skills）。我们在今年年初就全面启动了这项工作。因为我们在工程上一直有非常成熟的单一代码库（Monorepo）理念和实践，所以我们建立了一个集中式的 Skills Monorepo（技能单一代码库）。这里面既包含了由中心化平台团队打造的核心通用技能，也容纳了各个独立业务团队根据自身场景专门开发的特定领域技能。

这些技能在形式上就像是包含独立能力定义的文件夹，类似于插件机制，能够被各种开发环境和工具无缝复用。

<details>
<summary>Original English</summary>

**Uber Engineer**: El siguiente aspecto Había habilidades. Nosotros asumió esto principios de año. Como ya teníamos concepto monorepositorios, nosotros creó una especie de monorepositorio habilidades, que incluyen todas las habilidades básicas, que crean central equipos de plataforma, y todos los específicos habilidades que pueden desarrollar por separado equipos. Y estas habilidades son igual que las carpetas con habilidades, como complementos que pueden ser uso para ¿Código en la nube, etc.?

</details>

**主持人**：就像在云端开发环境（Cloud Code）等场景中使用的插件那样，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: ¿Código en la nube, etc.?

</details>

**Uber 工程师**：没错，正是如此。我们拥有插件和技能模块，它们可以在所有的开发环境与智能体运行时中通用运行。接着，我们制定了适用于所有人的统一质量与规范标准。我们让这些技能具备了跨所有开发环境的高度可移植性。

你只需要借助我之前提到的那套 AIFX 工具套件，就可以统一对它们进行配置管理。只要你在系统中新增了一个插件或技能，AIFX 就会自动在所有的开发环境中同步更新相应配置，无论你当前正在使用的是哪一个具体环境。因此，即便工程师在不同的开发环境之间频繁切换，这些插件和技能也会自动配置就位，你完全不需要担心手动重新配置或环境不一致的问题。

此外，由于所有的技能底层都是通过我们的 MCP 网关来调用工具的，因此所有这些技能在访问任何内部或外部工具时，都拥有唯一且统一的标准访问机制。

目前我们正在研发一系列辅助工具，工程师可以在其中挑选并评估自己的技能。该工具会为工程师提供全方位的分析与改进建议，帮助他们持续优化技能代码。紧接着我们正在推进的下一项工作，就是从各个运行环境中实时收集追踪数据（Traces），并基于实际调用表现自动生成针对技能的补丁，这样我们就能基于真实世界的运行反馈不断演进和改进技能。

之所以如此重视这一点，是因为业界关于智能体技能的质量、评估标准以及如何实现持续迭代改进，存在着非常热烈的讨论。当你初次编写一个智能体技能时，它往往是不完善、甚至是粗糙的，因此必须具备一套让技能得以持续进化与打磨的长效闭环机制。我认为，无论是 MCP 还是 Skills 体系，都给我们带来了巨大的技术与业务红利。如果你观察最近几周的运行指标，我们每天的技能调用执行次数已经接近 30,000 次。

<details>
<summary>Original English</summary>

**Uber Engineer**: Así es. Entonces, hay complementos y habilidades, que puede ser uso en en todos los entornos. Luego creamos criterios uniformes cualidades que pueden referirse a todos. Y lo hicimos su portátil para todos los entornos. Entonces tú los configuraste por con la ayuda del mismo Kit de herramientas de efectos de IA, que ya mencioné. Y si añades complemento o habilidad, él actualiza configuraciones en todos entornos, independientemente de si ¿Lo usas? Miércoles ahora o No. Mm. Así que incluso si tú cambiar entre entornos, estos complementos se están estableciendo automáticamente. No lo haces no hay necesidad de preocuparse sobre ellos reconfiguración etc. Y puesto que todos habilidades usar herramientas de MCP- puerta de enlace, también tenemos estándar único mecanismo de acceso cualquier herramientas para todas estas habilidades. Actualmente estamos trabajando en herramientas donde los ingenieros pueden Elige tu habilidad. Ella se los proporcionará todo tipo de consejos sobre mejorando su habilidades. Próximo, en qué estamos trabajando— Así es como se recolecta rastreo con entornos y crear parches para mejorar habilidades, para que podamos siempre mejorarlos en basado en lo obtenido conocimiento. Porque Están pasando muchas cosas discusiones en torno a la calidad de las habilidades, sus evaluación y que ¿Qué tan constante es esto? mejorar. Cuando tú creando por primera vez habilidad, ella puede no ser perfecto, por lo tanto necesario mecanismo para ello permanente mejorar. I Creo que tanto MCP como las habilidades nos dieron muchas ventajas y si miras los últimos semanas, luego está cerca 30.000 lanzamientos de habilidades por día.

</details>

### 技能规模化运营与 CLI 模板的 Token 优化

**主持人**：这对我来说非常值得关注。因为如果你对外宣称：“哦，我们搭建了一个‘技能代码库’（Skills Repo）”，许多初创公司的人可能会轻描淡写地认为——我指的不是 Uber 这样的大厂，而是外界初创公司的常见反应——“哦，不就是在 Git 里建个代码仓库，往里面扔一堆技能定义，建几个文件夹，仅此而已吗？”但显然，真正的企业级工程落地要比这复杂艰巨得多，对吧？

之所以复杂得多，是因为你们需要服务和支持如此庞大体量的工程师群体？还是因为你们必须持续不断地进行自动化评估、清洗维护这些技能，并严密监控它们到底有没有被实际使用等类似的问题？

<details>
<summary>Original English</summary>

**Interviewer**: Esto me resulta interesante para mirar, porque si Le dijiste a alguien: "Oh, creamos "repositorio de habilidades". La mayoría de las personas en Las startups pensarían, ¿verdad? No estoy hablando de Uber, pero más bien: "Oh, solo crear un repositorio Git, pon un montón allí habilidades, solo un conjunto carpetas, y eso es todo." Pero Está bastante claro que esto es mucho Más difícil, ¿verdad? ¿Es más difícil porque...? número de personas y ingenieros, que necesidad ¿apoyo? O porque tú también realizar una evaluación constantemente limpio estas habilidades o seguimiento si se utilizan lo son o no, y por lo tanto ¿similar?

</details>

**Uber 工程师**：是的，确实如此，这几方面的原因都存在。我认为现在借助任何最新一代的模型，想要生成一个技能的初始 V0 原型版本其实非常简单。但要想打造一个在各种复杂的实际生产场景下都能稳定、高质量运行的成熟技能，难度是极高的。

正因为如此，我们必须确保有一个统一的平台和机制，能够对所有这些技能进行持续的更新与升级。事实上，当我们完成架构演进并向所有 MCP 开放 CLI 投影支持时，仅仅几位工程师借助 AI 的辅助，就快速更新了整个仓库中所有技能的底层实现层，将它们全面迁移并采用 CLI 模板。而之所以这么做，是因为 CLI 模式在 Token 消耗效率上要远远优于传统全量 MCP 模式。

因为试想一下，如果每个技能在运行时都声明：“我需要 MCP 工具 ABC，同时还需要 MCP 工具 DEF”，那么一旦我同时安装或挂载这两个插件，当前大模型的上下文窗口中就会无条件始终驻留六个完整的 MCP 架构描述，这会给上下文窗口带来巨大的负荷与冗余，对吧？随后我们将所有的技能调用统统替换为 CLI 模板的形式。这一转变极大地提升了我们使用大模型时的 Token 利用效率。

另外，由于我们自动为公司内的所有开发者预装了这个技能市场，这就直接帮大家省去了一道繁琐的手动配置流程。得益于这种中心化设计，工程师查找、配置和管理技能都变得格外轻松，我们也有能力围绕整个技能生态构建起一整套自动化的评估、检索和流水线输送体系。虽然目前在 Uber 内部仍有个别团队保留着自己的独立代码仓库，但公司绝大部分的智能体技能都在通过这个中心化平台进行流转与使用。

<details>
<summary>Original English</summary>

**Uber Engineer**: Sí, definitivamente. I Creo que ahora con cualquier ¿Cuál de estos más nuevos? modelos muy fácilmente crear V0 inicial- versión de la habilidad. Muy Es difícil hacerlo muy alta calidad para todo tipo de escenarios usando. Y exactamente así que queremos para asegurarnos de que tenemos un lugar donde puede actualizar todo estas habilidades. De hecho cuando cambiamos y Proyección CLI abierta Para todos nuestros MCP, sólo pocos ingenieros, utilizando IA, Actualizado todo el nivel de habilidades este repositorio, para usar Plantilla CLI porque más eficaz en términos de fichas. Porque, si cada habilidad dice: "Necesito MCP ABC, MCP DEF", entonces si yo Instalaré estos dos complementos, tengo Siempre habrá seis MCP en contexto, y esto es contexto amplio Carga, ¿verdad? Y luego reemplazamos Todas las habilidades en CLI- plantilla. Así que esto también es tuvo un impacto significativo en nuestra eficiencia uso de tokens. Y también, puesto que nosotros automáticamente nosotros instalamos esto mercado de habilidades Para todos, esto elimina incluso un paso configuraciones. Gracias a esto facilita la búsqueda, configuración y administración, y nosotros pudieron construir alrededor de todo esto una serie de cintas transportadoras evaluación y búsqueda. EN Todavía tenemos equipos, que tienen los suyos propios repositorios, pero la mayoría de las habilidades Estoy pasando por esto.

</details>

### Uber 上下文图谱（Context Graph）与智能体心智模型

**Uber 工程师**：在我看来，我个人最钟爱的一项突破其实是上下文图谱（Context Graph）。

<details>
<summary>Original English</summary>

**Uber Engineer**: Mi favorito es gráfico de contexto.

</details>

**主持人**：嗯。那么，到底什么是上下文图谱呢？

<details>
<summary>Original English</summary>

**Interviewer**: Ejem. Oh, ¿qué es un gráfico contexto?

</details>

**Uber 工程师**：这背后的业务背景是这样的：早在去年 12 月，我们的一位工程师开发了一个 AI 问答助手，任何人都可以向它提问——我们在内部称之为 Cortana。你可以在网页端或者在 Slack 里面直接向它提出任何关于公司代码库的问题。它当时以智能体（Agent）的方式运行：在接收到问题后，它会自主检索我们所有的代码仓库，然后给出针对性的解答。

当时我们观察到，大家向它提出了形形色色的各种问题。有的是为了做技术调研，有的是询问“这条查询语句应该如何执行”，还有的是问“这项业务数据的数据源到底在哪里”、“这个模块的负责人到底是谁”，或者是“你能不能针对这次线上故障做一份根因分析（RCA）报告”。大家在上面抛出了极其繁杂的日常软件工程任务。

而当我们深入复盘和审视其中的一部分执行追踪（Traces）时，我们非常清晰地意识到：模型在获取基础背景知识时所消耗的交互步骤和推理轮次，实际上存在着巨大的优化空间。因为在 Uber 这样的大型企业内部，我们存在着太多的子系统——从历史上看，这些系统彼此之间都是高度孤立的孤岛，对吧？比如一名工程师为了排查一个问题，不得不分别进入任务工单管理系统、查看内部值班调度面板、再去翻阅我们前面提到过的 UON 监控仪表盘。

于是我们当时就思考：既然如此，我们能不能把所有这些孤立的系统节点与信息关联，为智能体融合出一张统一的‘心智地图’（Mental Map）呢？

就在刚刚过去的短短几个月里，我们真正把这个想法落地实现了，而且它具备令人惊叹的可视化效果，我们称之为‘Uber 上下文图谱’（Uber Context Graph）。目前在这张图谱中，我们拥有超过 100 种不同的实体节点类型，以及超过 130 种不同维度的关联关系。而且图谱中的数据是实时鲜活的，比如就是我们三天前的最新企业快照。在图谱里，如果你随意点击任何一个代表‘员工’的实体节点，你就能立刻查阅到该员工名下负责管理哪些数字资产、曾经撰写过哪些系统架构设计文档，等等。

<details>
<summary>Original English</summary>

**Uber Engineer**: El contexto es el siguiente: aún en diciembre uno de ingenieros crearon IA- asistente de quien Puedes contactarnos La llamamos Cortana— puedes ir a Internet o en Slack y poner cualquiera ¿Alguna pregunta? base de código. Entonces él trabajó como agente: buscado todos los nuestros repositorios y respondió a pregunta. Y nosotros vieron cómo la gente poner la más diversa pregunta. Esto podría ser investigación, o por ejemplo, como ejecuta esta consulta, o donde se encuentra la fuente de datos ¿para esto? OMS ¿Quién es el dueño de esto? O ¿Puedes hacer un RCA? ¿para esto? Montón tareas de software ingeniería. Y cuando nosotros miró algunos de los estos rastros, había Es bastante obvio que podemos optimizar número de pasos, modelos requeridos recibir conocimientos básicos, porque tenemos mucho sistemas—históricamente todos ellos eran aislado, ¿verdad? Por ejemplo, un ingeniero Tengo que entrar en la plataforma gestión de tareas, a nuestro panel turnos, o en nuestro Panel de control de la UON, sobre el cual Hablamos. Entonces nosotros tal: bueno, como nosotros combinar todo esto en un mapa mental ¿Para agentes? Entonces solo durante los últimos meses, y eso es genial visualización, Guau. que nosotros creamos. Nosotros lo llamamos grafo de contexto Uber, tenemos más de 100 tipos de nodos y más 130 tipos de conexiones. Y esto datos actuales, digamos, a partir del 3 Hace días. Si usted haga clic en cualquiera ¿Qué tipo de nodo humano eres? descubrirás qué ella administra activos, qué documentos de diseño escribió, Guau.

</details>

**主持人**：哇，这太震撼了。

<details>
<summary>Original English</summary>

**Interviewer**: Guau.

</details>

<!-- chunk 6/12 -->

### 上下文图谱：连接企业实体与降低智能体推理开销

**Uday**: ……关于他参与了哪些功能模块的开发、执行了哪些配置变更、处理了哪些故障排查与突发事件，以及在 Jira 中创建了哪些任务项。如果你提取图中的任意一个节点，它都会与系统中所有其他相关节点建立连接。这究竟能为我们带来什么价值？正如我刚才提到的，我们所构建的这款 AI 助手，正是以这张上下文知识图谱作为底层认知基础的。因此，当用户提出任何工程或业务问题时，它首先会利用这张图谱来建立上下文定位：搞清楚这个人究竟在问什么、属于哪个业务领域。一旦它获取了这一底层事实基准（例如该问题涉及特定业务线或某一组微服务集群），它就可以进一步深入检索，调取并阅读更具体的底层设计文档或相关工程资料。这一机制极大地缩减了智能体自主执行任务所需的探索范围和思考步数，而这些步数原本是提供高质量回答所必不可少的。我们已经在多种提问类别中观察到显著收益：回答质量持续提升，Token 消耗成本大幅下降，推理延迟也显著降低。而我们目前仅仅触及了充分发挥这套图谱工具潜力的冰山一角，整个团队对未来基于它构建更多能力充满期待。

<details>
<summary>Original English</summary>

**Uday**: ...sobre qué funciones obras en las que tomó el mando participación, qué cambios configuración realizada ¿Qué incidentes? ¿Qué eventos se procesaron? creado en Jira. Y si tomas alguno un nodo, tiene conexiones con todos los demás nodos. ¿Y qué significa esto para nosotros? da—ahora el mismo el asistente del que estoy hablando dicho, utiliza esto gráfico de contexto como base. Entonces, si usted poner cualquiera pregunta, él usaremos primero esto, para que orientarse: sobre ¿Qué es exactamente lo que pregunta? ¿hombre? Tan pronto como él obtiene la base, por ejemplo, ¿qué es esto? preocupaciones de cierta industria o conjunto servicios, él puede para profundizar y leer otros documentos o materiales. Él reduce la ejecución tareas por el agente y número de pasos, necesario para proporcionar buenas respuestas. Y ya vemos que en muchos categorías de preguntas La calidad está aumentando, el costo disminuye y El retraso disminuye . Y todavía estamos solo en inicio de uso pleno potencial de esta herramienta. Nosotros muy emocionado respecto a todo lo que podemos construir basado en esto en futuro.

</details>

**主持人**: 那么这些图谱中的节点代表的是具体的人吗？还是指各种工程工具？

<details>
<summary>Original English</summary>

**Host**: ¿Entonces estos nodos son personas? ¿Son estas herramientas?

</details>

**Uday**: 这实际上是对整个工程组织与资产架构的多维立体可视化呈现。在公司内部，每个人都拥有一个独立的实体节点：我有一个节点，每位雇员也都有各自对应的节点。不仅如此，这些人员节点与系统中的各类工程实体之间都存在关联拓扑——举例来说，我所创建的每一个 PR（拉取请求 / Pull Request）都会生成专属的实体节点，并且与我之间连接着明确的关系边，标明：“Uday 创建了该 PR”、“Uday 是该代码资产的负责人”、“我当前正在参与该产品功能的开发”，或者“我对这份系统架构设计文档做出了贡献”。

<details>
<summary>Original English</summary>

**Uday**: Esto es una visualización planes. Cada persona en La empresa tiene su propia nodo: hay un nodo para yo, un nodo para todos los empleados. Y tiene conexiones con Todas las entidades: por ejemplo, cada PR, que yo creo, tendrá su propio nodo. Y hay un enlace que indica: Uday creó esta solicitud de extracción. Uday está a cargo de esto activo. Estoy trabajando en esta función producto. Hice contribución a este documento del diseño.

</details>

**主持人**: 也就是说，节点既囊括了组织内部的团队成员，也涵盖了各类工程资产与代码产物。

<details>
<summary>Original English</summary>

**Host**: Entonces, los nodos relacionarse con la gente, pero así como los activos.

</details>

### 从图拓扑到 Cypher 查询：复杂数据分析的高效定位

**Uday**: 没错，完全正是这样。这里我可以举一个直观明了的实际场景：假设有人提出这样一个问题：“在整个全球出行移动业务线中，有多少笔行程订单是通过现金方式完成支付的？”以往要回答这个问题，你首先必须梳理清楚相关数据究竟存放在哪几张底层数据库表里、表结构中包含哪些字段列。同时你还得去打听：之前是否有其他同事编写过类似的复杂查询脚本？他们是属于总部的核心数据科学团队，还是归属于移动端业务数据科学组？而在当下，所有这些零散的信息与资产全部实现了图谱化互联。你可以直接在图谱中快速核查过去 30 天内是否有人提交过类似的数据分析请求、现存的核心数据表有哪些，并顺藤摸瓜探索关联的字段定义。因为从本质上讲，这一切资产和知识都是深度关联交织的。这样一来，智能体就能够极其迅速地定位到经过生产验证的历史查询模板，并快速生成此类复杂高难度问题的精准答案。如果没有这套图谱支撑，智能体就不得不盲目翻阅海量文档、触发大量无序的外部工具调用。可以说，图谱让整个推理定位流程变得无比高效。对于人类工程师而言，手工编写复杂的 Cypher 图数据库查询语句往往非常繁琐耗时，但智能体却极其擅长在图结构中自主巡航导航，就像在操作一套经过精心编排的文件系统一样轻松自如。

<details>
<summary>Original English</summary>

**Uday**: Sí, exactamente. Aquí Ejemplo sencillo: Digamos que tú hacer las cuestiones, cuántos viajes a en el campo de la movilidad el mundo entero era ¿Pagado en efectivo? Primero necesitas comprender cuál hay mesas que Hay columnas. ¿Hay otros personas que ya han escrito ¿Tales peticiones? ¿Are de? ¿Equipo científico? O ellos son del equipo ¿Ciencia móvil? Ahora todos estos datos interconectados. Tú ¿Puedes comprobar si? Hubo otras solicitudes para los últimos 30 días con respecto a esto, y qué tablas ¿existir? Explorar estas columnas, porque, de nuevo De todos modos, todo esto interconectados. Entonces podrás ir rápidamente a nuestro probado solicitudes y suficientes responder rápidamente a preguntas tan difíciles. De lo contrario tendrías que procesar mucho documentos y hacer un montón llamadas herramientas. Él hace que el proceso sea muy eficaz. A nosotros mucho más difícil escribir manualmente todos estos Consultas Cypher, pero Los agentes son geniales se orientan en el gráfico, como en el archivo sistema que utiliza intento.

</details>

**主持人**: 这听起来确实极具未来感，而且令人印象深刻。但我推测，单单维持这样一张图谱就需要吞吐极其庞大的数据量，毕竟在 Uber 这样规模的企业中，轻松汇聚了超过一万名员工和浩如烟海的微服务工程资产。

<details>
<summary>Original English</summary>

**Host**: Esto me parece muy bien. futurista, pero Bastante genial. Y yo Supongo que esto es enorme volumen datos para almacenamiento, solo porque en Uber funciona fácilmente más de 10 000 personas.

</details>

**Uday**: 确实如此。不过值得庆幸的是，正如同我们边缘网关 API 团队在推进 MCP（Model Context Protocol）项目时所采用的跨部门协作模式一样，公司内部负责运营拥有数十亿节点工作流图谱的 Condes 平台团队也参与了这张图谱的共建。因此，与 Condes 长期支撑的庞大工作拓扑规模相比，我们当前的上下文图谱规模实际上要小得多，所以在图数据库扩容与大规模工程扩展方面，对平台团队而言早已不再是不可逾越的瓶颈挑战。此外，正如我们之前讨论过的全能 AI 助手 Cortana，它成功将所有上下文图谱、底层工具和专业技能无缝衔接在一起，并且全面渗透集成到了工程师常用的 Slack 工作区、Web 控制台和 CLI 命令行终端中。这意味着公司内的任何一位员工——哪怕是驻扎在某个具体海外国家的一线业务运营人员——都可以随时向它发起咨询：“这套系统是怎么搭建起来的？具体部署在什么位置？当前由谁负责维护？它的底层演进历史是怎样的？”而 Cortana 能够精准串联并摄取所有关联的工程元数据、Google Docs 团队设计文档以及最新发布记录，从而迅速给出条理极为清晰的高质量解答。

<details>
<summary>Original English</summary>

**Uday**: Por lo tanto, Sí, buenas noticias en porque es como cómo nuestro equipo La API de la puerta de enlace perimetral funcionó en el proyecto MCP, nuestro comando de plataforma Condes, que gobierna nuestro gráfico de trabajo con miles de millones de nodos, también ayudó Construye este gráfico. Entonces, comparado con nuestro gráfico de trabajo, Este es mucho más pequeño. Así que para ellos ya no es es un desafío con respecto a escalada. Sí, y También ya hablamos Acerca del asistente de IA Cortana, que conecta todo el contexto de los gráficos herramientas, habilidades, y él omnipresente en Slack, la web y CLI. Entonces, cualquiera en empresas, incluso empleado departamento de operaciones en algún país, tal vez poner cualquiera pregunta: "¿Cómo es esto? ¿construido? ¿Dónde es esto? ¿Dónde se encuentra? ¿Quién está arriba? ¿Esto funciona? Qué ¿La historia de esto? Y él capaz de tomar todos estos Datos, todos nuestros Documentos y fechas de Google Se ven muy bien. responder.

</details>

### 打破部门信息壁垒与严格的权限风控控制

**主持人**: 它实质上彻底打破了不同业务部门之间长期存在的信息孤岛与沟通壁垒，对吧？终端用户不仅能够完全实现自主自助服务、随时针对任何疑问发起提问，甚至还能按需调用任何同事开发构建的特定领域定制技能。

<details>
<summary>Original English</summary>

**Host**: Él destruye informativo barreras entre departamentos, ¿verdad? Los usuarios pueden para servirse a sí mismos tú mismo, pregúntate qué lo que sea, hazlo cualquier creado la habilidad de alguien.

</details>

**主持人**: 我猜想，为了实现这种级别的全局感知，AI 助手自身必定具备访问底层各类基础数据源的能力，至少能够调取与相关服务直接挂钩的核心基础设施指标，比如系统运行日志（Logs）、链路监听指标（Tracing / Listeners）等这一类底层的可观测性诊断数据。

<details>
<summary>Original English</summary>

**Host**: Y supongo que él debe tener acceso a fuentes de datos, al menos para personas pertinentes a él podía elegir cosas , tales como registros y escucha, esas cosas.

</details>

**Uday**: 是的，它完全具备读取运行日志、监听指标和监控链路的能力。你完全可以直接询问它：“某某微服务当前的实时运行健康状况如何？”它能够瞬间透视该服务的所有上下游依赖关系、当前挂载的底层持久化存储集群配置，并对所有历史及实时调用请求进行聚合分析，最终为你输出一份关于该生产资产的完整体检状态报告。更为关键的一点在于，我们全流程严格继承了用户现有的企业级访问控制权限（ACL / IAM）。换句话说，AI 助手在代表我查询时，仅能触及我本人原本就已通过审批、具备合法访问授权的资源与数据；如果某项数据对我而言本身属于未授权范围，系统就会严格执行权限隔离，AI 助手绝不会越权调取并返回给我。

<details>
<summary>Original English</summary>

**Uday**: Sí, tiene registros y escucha. Puede preguntar: "¿Cuál es la condición de ¿Este servicio? Él puede ver todo sus dependencias, que sistemas de almacenamiento él usa, cumplir con todas las solicitudes y para brindarle una solución completa informe de estado sobre esto activo. Y nosotros todos llevamos permisos existentes usuarios. Entonces, yo Solo tengo acceso a lo que tenía que hacer acceso anticipado. De lo contrario diciendo, estos datos no estará disponible.

</details>

**主持人**: 明白，因为我过去也在 Uber 工作过，对这套合规体系深有体会。我记得当时内部有一套严格的“紧急破窗机制”（Break-Glass），即当你遇到突发生产故障、紧急需要访问某个日常未授权的关键系统时，必须走规范的审批流，获取直属经理、总监乃至更高层技术负责人的紧急授权签字。据我所知，在 Uber 的工程文化中，对数据访问合规与特权凭证管理一直保持着极高的审慎度与严格关注。

<details>
<summary>Original English</summary>

**Host**: Sí, porque estoy en Uber. Lo recuerdo. se llamaba "descanso" vidrio, cuando tú Se necesitaba permiso al sistema en el que te encuentras no tenía acceso. Tú pasar por el proceso aprobación a través de tu gerente, director o alguien otro. Pero sé que en Uber cuando estoy allí funcionó, esto ya está prestó mucha atención mucha atención.

</details>

**Uday**: 是的，千真万确。因此在系统立项之初，我们首要确保的就是安全与鉴权底座的绝对稳固，而现在我们正稳步推进更多创新能力的研发。虽然我们目前仍在持续探索和验证一些更具长远前瞻性的未来构想，但必须承认，正是这些扎实落地的底层核心要素，真正推动了我们内部 AI 智能体体系的演进飞跃——让我们成功将 AI 的赋能版图，从最原初单纯的日常代码辅助编写，全面拓展延伸到了涵盖整个软件生命周期与全维度的工程协同任务之中。

<details>
<summary>Original English</summary>

**Uday**: Sí, definitivamente. Entonces, Creo que era seguro lo básico, y ahora nosotros Estamos trabajando en otros nuevos. Todavía estamos considerando algunos más futurista opciones usando. Pero algunos de estos básicos elementos realmente nos ayudó en desarrollo de nuestro agentes, pasando del uso solo para programación para todo tipo de ingeniería tareas.

</details>

### 赞助商速递：Turbo Buffer V3 存储引擎重构与 Linear 差异审阅

**主持人**: 这段分享让我深切联想到 Uber 是如何在夯实 AI 基础设施底座的同时，持续向更宏大的前沿工程发起进军的；而在现代基础设施演进这条道路上，依然有着极其广阔的深耕空间。我们的本期赞助商 Turbo Buffer 显然对这一点有着独到而深刻的洞察。他们当前正在对底层的数据存储引擎架构进行彻头彻尾的从零重构，其核心目标是让各类型的检索查询在大规模并发与海量数据集下变得更加敏捷高效、具备更显著的成本优势以及更极致的系统可靠性。目前，他们代号为 Turbo Buffer V3 的全新一代存储系统虽然尚未正式投入通用生产环境，但其工程代码已经全面通过了持续集成（CI）流水线的严格测试验证。当然客观而言，新引擎目前的端到端吞吐与响应表现尚未全面反超当前的成熟 V2 版本。为此，工程团队正集中精力深度优化底层的查询执行计划（Query Plans），力求使其性能全面追平乃至彻底碾压 V2。他们全程以公开透明的形式推进这一进程，详尽记录并公开发布 V3 迈向最终正式发布前的每一次性能调优与技术攻关细节。例如我们近期看到，该团队通过引入创新的批量顺序读取策略（Batch Reading），直接将全文检索的整体吞吐性能提升了整整 9 倍之多。其中相当一部分工作属于极为硬核的底层基础设施攻坚，而在接下来的数周内，他们还将陆续对外揭晓更多令人瞩目的系统级工程突破。

<details>
<summary>Original English</summary>

**Host**: Acabo de recordar cómo en Uber está trabajando en los fundamentos de la IA, pero Todavía queda mucho por delante. seguir trabajando infraestructura. Nuestro El patrocinador Turbo Buffer lo sabe No se parece a ningún otro. Están reconstruyendo su arquitectura almacenamiento de datos con cero. Ellos hacen esto, para hacer diferentes tipos de búsqueda más rápidos, más barato y más confiable en escala. Nuevo sistema llamado Turbo Buffer V3 aún no está disponible. producido, pero ya Aprueba CI. Eso no es menos, todavía lo es no funciona tan rápido, como la versión actual V2. Por lo tanto, el equipo ahora optimiza los planes solicitudes para que ellos se convirtió en lo mismo rápido o Más rápido que V2. Ellos lo hacen públicamente, documentar cada etapa de promoción productividad hasta Lanzar V3. Por ejemplo, vemos cómo el equipo aumentó productividad texto completo buscar 9 veces por lotes lectura. Grande parte de esto— trabajo básico, pero en las próximas semanas compartirán mucho interesante sistémico logros.

</details>

**主持人**: 不过稍等一下，究竟是什么驱动着该团队下定决心展开如此彻底的底层架构重写？核心根源在于整个数据检索领域正在经历深刻演进，而 Turbo Buffer 也在顺应趋势完成自我蜕变。在早期，它主要作为一套专注向量搜索的 Vector Database 存在；但时至今日，它早已超越了单纯向量数据库的狭窄范畴，全面进化成为一款兼具卓越吞吐与高度可查询性的通用型高性能分析数据库。在全新的 V3 架构中，团队彻底摒弃了以单一向量索引为主导的传统路径，转而将所有核心索引体系全面迁移构建在现代化的列式存储（Columnar Storage）系统之上。每一个查询请求都将借助向量化执行算子（Vectorized Execution Primitives）进行底层加速——这种架构设计在传统通用搜索引擎中极为罕见，但它却能在保障极致亚毫秒级检索响应的同时，赋予底层数据库无与伦比的通用数据分析与高吞吐处理能力。Turbo Buffer 团队在官方站点保持着持续更新的公开工程日志，大家可以通过访问 turbobuffer.com/v3 跟踪他们的最新研发动态。能够亲眼见证一套世界级基础设施引擎在公开透明的环境下逐步锻造成型，确实是一种非同寻常的工程享受。

<details>
<summary>Original English</summary>

**Host**: Pero Esperar. Por qué El equipo está haciendo todo lo posible. ¿Reescritura? Atrás esa búsqueda está cambiando, Y también Turbo Buffer. Más temprano era una base vectorial datos, pero ahora es Ya no es fácil base de datos de vectores. Ella evolucionó en altamente productivo base de datos consultable . V3 se niega a vector principal índice y todos índices utilizará una columna sistema de almacenamiento. Cada solicitud se realizará el vectorizado movimientos que son raros encontrado en motores de búsqueda, pero Esto garantizará ambos búsqueda muy rápida, y generalmente rápido Operación de base de datos. El equipo de Turbo Buffer está liderando tu diario de trabajo progresar, y puedes síganlo en turbobuffer.com/v3. Él verdadero placer —mira cómo es se está creando.

</details>

**主持人**: 与此同时，我也想向大家重点推介我们本季度的另一位核心赞助商——Linear 公司。Linear 如今已经发展成为人机协同与多智能体工作流编排领域的首选协同枢纽，为人类工程师与 AI 智能体之间的任务调度与协作提供了极其优秀的承载平台。对于我们广大的软件开发人员而言，当下技术范式最深刻的剧变之一，莫过于伴随着 AI 辅助编码的普及，日常所需审阅的代码体量呈现出了爆发式的指数级膨胀。为此，Uber 内部自研了专门的辅助审查工具体系，而 Linear 同样给出了自己的优雅解法——他们推出了一项名为“Linear Diffs”（代码差异对比与内联审查）的全新功能，直接允许软件工程师在 Linear 的任务看板与工作流界面中无缝查看并审查 PR 代码差异。我个人非常中意这项能力，因为在 Linear Diffs 中，代码的具体改动对比能够与当前项目中的对应 Issue 任务完全并列陈列于同一工作空间内，这让工程师能够极其轻松地在单一视图中纵览完整的产品背景与需求上下文，从而透彻领会每次代码提交背后的根本动因，再也无需在各种互不相通的开发工具链之间来回疲于切换。

<details>
<summary>Original English</summary>

**Host**: Yo también Quiero recordar nuestro patrocinador temporada, empresa lineal —lugar para coordinación del trabajo tanto personas como agentes. Uno de los los mayores cambios para nosotros, los desarrolladores software provisión, hay enorme volumen el código que necesitas para revisar. Uber creado especial herramientas para Esto, pero también lineal. Él se llama Diferencias lineales y esto permite ingenieros ver PR directamente en Lineal. Me gusta mucho. como en Diferencias lineales esa comparación El código está ubicado junto a la tarea en proyecto, tan muy fácil ver todo contexto en uno lugar y comprender la razón de los cambios, no alternando entre diferente herramientas.

</details>

**主持人**: 对于那些动辄涉及数千行代码的大型托管 PR，其内置的引导式审阅能力（Guided Reviews）能够帮助工程师迅速抓住改动的核心要脉，精确阐释哪些核心业务逻辑被重构或变更。此外，引导式审阅功能还会智能地对辅助性支撑代码、类型重构以及边缘修饰性变更进行独立分组归类。这些改动虽然看似微小零碎，但正是这类井井有条的结构化归集，才让原本令人望而生畏的大体量复杂 PR 变得一目了然，甚至在第一遍通读审阅时就能轻松把握全局脉络。不仅如此，该功能还进一步支持……

<details>
<summary>Original English</summary>

**Host**: Para grandes relaciones públicas gestionadas Las reseñas ayudan para entender cambios importantes, explicando qué exactamente fue cambiado. Reseñas guiadas también por separado grupo auxiliar código y ediciones relacionadas. Son pequeños, pero cambios importantes ¿Acaso no hacen siquiera eso? gran relaciones públicas comprensible para una visita. Y también Soportes

</details>

<!-- chunk 7/12 -->

### Linear 堆叠 PR 与代码审查演进

**Speaker A**: Linear 推出了堆叠 PR（Stacked PRs）。如果你已经在使用堆叠 PR，就会知道这是一种拆分复杂、繁重工作的绝佳方式；如果还没有尝试过，在试用之后大概率会喜欢上它。当前代码审查流程正在经历持续的变化，因为各类 AI Agent 正在承担越来越多的日常工作。Linear 带来的这些令人兴奋的更新，有助于我们工程师更深入地理解代码审查。同时我也期待 Linear 能持续演进代码差异对比（diffs）功能，以更好地契合并响应我们与 AI Agent 协同工作日益深入的全新模式。如果想要了解更多详情并获取 6 个月的 Linear 优惠折扣，请访问 linear.app/pragmatic。

<details>
<summary>Original English</summary>

**Speaker A**: Linear Stack PR. Si ya usado Pila de PR, luego Sabes que eso es genial. forma de dividir trabajo difícil, y si aún no—tú, Probablemente te encantarán, habiéndolo intentado. Proceso revisión de código en constante cambio, porque los agentes de IA asumir todo más trabajo. Estos actualizaciones interesantes de Lineal nos ayuda, ingenieros, mejor comprender las revisiones de código, y espero Lineal desarrollará diferencias para para responder a cómo cada vez somos más Trabajamos con agentes de IA. Para averiguarlo más y obtener seis meses usando Lineal con descuento, adelante en linear.app/pragmatic.

</details>

### Uber 内部的 PRD 与 ERD：构建单一事实来源

**Speaker A**: 让我们把话题转回 Uber。在深入探讨今天的内容之前，先来看看企业内开发者使用的工具视角下的功能创建流程。这涉及 PRD 和 ERD。对于不太了解的人来说：PRD 指的是产品需求文档（Product Requirement Document），而 ERD 则是工程需求文档（Engineering Requirement Document），对吧？对于不熟悉 Uber 内部流程的听众，可以把它理解为产品的技术规范以及具体的工程方案。

<details>
<summary>Original English</summary>

**Speaker A**: Volvamos a Uber y antes de hoy La creación se ve como funciones desde el punto de vista herramientas que usar desarrolladores en empresas. PRD y ERD. Aparentemente, para quienes no lo sepan: PRD— Estos son documentos de requisitos del producto, y ERD es ingeniería requisitos, ¿verdad? Es como especificaciones técnicas para producto y plan de ingeniería para aquellos que no están familiarizados con interno Procesos de Uber.

</details>

**Speaker B**: 是的，我们审视了一些 AI 的基础概念。现在当你重新思考整个功能的生命周期时，核心问题变成了：我们如何运用恰当的 AI 技术来切实改进其中的每一个阶段，并真正面向 AI 时代重新思考我们的内部工具？在某些领域我们已经取得了长足的进展，而在另一些领域我们仍处于早期探讨阶段。

例如，我认为即使是制定一份由 Agent 与工程师协同迭代完成的联合规划（joint plan），这个理念本身也是完全正确的。我们正处于推进的过程中……虽然脑海中涌现出了许多极具吸引力的想法，但目前大体上处于这样一种探索状态。

如你所知，我们拥有各种各样的 Agent 能力来配合处理你项目中的任何文档。正如我之前提到的，无论是产品设计文档、工程技术方案、初创项目评审（startup reviews）、XP 评审，还是上线生产准备度评审（production readiness reviews），所有这些都被归集到了同一个地方。我过滤掉了一些旧项目，以便大家能够清晰查阅。现在大家可以明确知道谁在负责推进这些工作，并实时追踪具体的流转状态。

所有这些数据同时也整合进了时间线与规划表中，因此我们拥有完整的上下文历史：哪些文档是权威的单一事实来源（source of truth）、当前的审批状态如何、由谁负责跟进。并且，每一个项目文档都与 Jira 或 Linear 深度关联绑定，使我们能够全程追溯方案最终是如何付诸实践落地的。这为人类工程师和各类 Agent 共同构建了一套“单一事实来源”，确保 Agent 能够透彻理解每个项目的规格说明与设计要求。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, lo consideramos algunos conceptos básicos de IA y Ahora que lo piensas sobre el ciclo de vida funciones, ¿cómo podemos? mejorar realmente cada etapa de la misma utilizando la correcta tecnologías de IA y repensar herramientas para la era AI. ¿Dónde estamos? han avanzado mucho adelante, y en algún lugar todavía estamos en las primeras etapas discusión. Por ejemplo, creo que, que incluso la idea un plan conjunto, sobre qué agentes y los ingenieros pueden trabajar juntos iterativamente, es correcto. Estamos en proceso...Hay muchas ideas interesantes, pero es algo así como... ya sabes, nosotros también tenemos todo tipo habilidades de agente para trabajar con cualquier tu proyecto documentos. Y, como yo Ya lo dije, independientemente de si es documento de diseño producto, ingeniería proyecto, reseñas startup, reseñas de XP o preparación para producción, todo esto recogido en uno lugar. Lo filtré proyectos antiguos para que podamos podría verlos, y ahora definitivamente lo eres Sabrás quién está arriba trabaja con ellos y podrás realizar el seguimiento su estatus. Todos estos datos también encajar en el horario, así que tenemos un completo historia: cuál Los documentos son la fuente verdad, estado aprobación y quién está trabajando en ellos. Cada uno de ellos tiene enlace a Jira o Lineal para que podamos rastrear cómo esto el proyecto fue implementado en práctica. Esto crea sistema de "único" "fuentes de verdad" como para las personas, así como para agentes para que ellos conocía las especificaciones para cada proyecto.

</details>

### 物理世界的复杂性与前置规划

**Speaker A**: 是的，我认为前期规划依然至关重要，特别是对于那些绝非微不足道的小任务——比如需要深入推敲的提案或短期关键项目。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, y creo que aún en planificación sigue siendo muy importante, especialmente para lo que no es trivial tareas como una sugerencia o proyecto corto.

</details>

**Speaker B**: 没错，正是如此。考虑到 Uber 涵盖了极其丰富的业务产品形态并覆盖海量国家和地区，我们需要极为严肃地推敲所有潜在的边缘异常情况（edge cases），而绝不能仅仅停留在考虑最理想的“正常路径”（happy path）。你必须全面考虑各类非标场景以及系统该如何妥善处理。而且因为我们的业务深深植根于物理世界，这类现实边缘情况的数量只会更加庞大复杂。

你必须认真审视：“如果遇到这种情况该怎么处理？如果异常状态持续下去会发生什么？这种情况下客服支持请求应该如何流转响应？我们具体该怎样解决？”这或许听起来不言而喻，但我还是想特意强调一下，因为很多人可能并没有切身感受：Uber 在全球极多国家和城市运营，即便在两个看似相近的城市之间，现实情况也会存在巨大差异——用户的预期完全不同，日常出行与消费习惯不同，方方面面都有所区别。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, exactamente. Y dado que hay un gran variedad productos y países, necesito seriamente pensar en todo posible casos extremos y no solo sobre "feliz" por". Debes piensa en todo tipo no estándar situaciones y cómo debe resolverse. Y porque trabajamos en el mundo físico, número de tales Los casos se están volviendo más Más grande, ¿verdad? Tú debe seriamente pensar: "Oh, qué ¿Sucederá si esto? ¿Continuará? Qué ¿Sucederá si esto? ¿Continuará? ¿Cómo debemos manejarlo? solicitud de servicio apoyo en tal caso ¿caso? ¿Cómo lo hacemos? ¿resolver?" Esto probablemente sea innecesario. agregar, pero aún así Lo diré porque podría ser No es demasiado obvio: Uber funciona en muchos países y ciudades, y incluso entre dos realidad de las ciudades puede variar: diferentes expectativas, diferentes hábitos de las personas y etcétera.

</details>

**Speaker A**: 是的，确实如此。我认为这就是为什么必须提前制定出清晰严密的方案。有了明确的方案，工程师与 Agent 才能基于这一共识，进一步将其拆解、分块并稳步落地执行。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, absolutamente. I Creo que por eso. es importante pensar en el plan correcto por adelantado, que lo hará más fácil ya que ingenieros y Los agentes tienen la oportunidad toma este plan, descompóngalo y ejecutar.

</details>

### Minion：后台自主编码 Agent 的演进

**Speaker B**: 当我们拥有了清晰的规划，接下来的核心步骤就是如何将其转化拆解为具体的代码实现。现在我们转向内部称之为 Minion 的系统。这是我们专门用于编写代码的后台 Agent。目前 Uber 内部大约有 15% 的 PR（Pull Requests）是由 Minion 参与或生成完成的。

本质上，工程师在处理很多 PR 时更倾向于通过交互式的方式亲自动手编写，但对于那些拥有明确技术规范、或者所需人工管控极小的工作任务，我们希望最大程度地简化流程，直接将其委托给 Minion 处理。

我们对此经历了数轮迭代。目前的最新版本被称为 Minion V2。它既支持通过 Web 界面访问，也可以直接在 Slack 中使用。你可以选择开启规划模式（planning mode）让其在后台自主推导工作，或者在任务非常直接明确时，直接下达单次指令让它在后台默默执行。

Minion 通过挂载 Mega DevPod 获得了访问全部代码库的权限，因此它能触达我们内部所有的仓库和完整的代码底座。它可以跨多个不同的仓库协同工作，并依据你设定的执行方案和资源预算，自动化生成单个或多个代码提交与 PR。

刚起步的时候，Minion 主要用于一些代码维护和辅助类工作。随着我们自研能力的演进，我们在 Minion 的运行环境中接入了越来越多的工具，现在它已经能够自主在 Web 端、移动端应用以及服务端 API 上对其生成的改动执行验证与测试。我们的长期目标是随着时间的推移，不断扩大工程师能够委托给 Minion 完成的任务范围与比例。

<details>
<summary>Original English</summary>

**Speaker B**: Cuando en Tenemos un plan, a continuación paso es cómo transformarlo, romperse en pedazos y darse cuenta. Ahora nosotros Pasemos a que somos internamente Lo llamamos Minion. Esto es nuestro agente de antecedentes para escribir código. Ahora alrededor del 15% de todos Los trabajadores de relaciones públicas pasan vía Minion. En esencia, bueno, ya sabes, hay un montón solicitudes de extracto, que Los ingenieros quieren Hazlo de forma interactiva, pero también queremos máximo simplificarlo para tareas donde hay buenas especificación o mínimo requerido control para que yo pueda Delegar esto a Minion. Y nosotros, de nuevo, creó varios iteraciones. Esta es la última. iteración, nosotros Lo llamamos Minion V2 y puede ser usar como a través de la web, así como a través de Flojo. Puedes elegir modo de planificación y permítele que para trabajar en fondo, o simplemente dar una solicitud y permítele que trabajo en segundo plano, si la solicitud es sencilla. Él tiene acceso, usando Mega Dev Pod, para que tenga acceso a todos nuestros repositorios y toda la base de código, que tenemos. Él puede trabajar con diferentes repositorios y crear uno o varias solicitudes de extracto basado en tu plan y presupuesto. Cuando nosotros acaba de empezar, Minion principalmente utilizado para tareas de apoyo código. En la medida de nuestras posibilidades desarrollo, añadimos cada vez más herramientas en Entorno de Minion, donde Él puede hacerlo él mismo para comprobar su trabajar en internet, móvil aplicaciones o API del servidor. Nuestro objetivo—con el tiempo aumentar la lista tareas que las personas puede desempeñarse para usando Minion. Aumentar la participación tareas a lo largo del tiempo.

</details>

### Slack 深度集成与即时故障修复

**Speaker B**: 我觉得我们也可以看看它是如何在实际工作中配合协作的。由于它深度集成了 Slack，你的交互方式非常自然：只需在群聊或讨论串中直接 @Minion。你随时 @Minion，它就会实时向你汇报执行状态。你完全不需要跳出上下文切换到浏览器中，直接在 Slack 对话流里即可全程驱动它。

比如，你可能正在 Slack 讨论串里与研发主管或业务产品经理探讨某些轻量级的设计改动。大家在对话中完成了讨论并达成了一致，这时你只需要在讨论串里直接回复：“嘿 @Minion，请读取这个讨论分支，为我们生成对应的代码变更与 PR 吧。”Minion 就会自动解析该 Slack 线程的完整上下文，并精准创建出对应的 PR。

事实证明，这一集成在我们的运维支持与排障频道中表现得尤为出色：当有人在频道中上报 Bug 时，值班人员可以直接询问 Minion：“你能分析一下这里的问题出在哪吗？”Minion 会迅速排查并回复：“这是导致故障的根本原因。”此时如果改动看起来相对简单直接，我们就可以决定：“那好，现在就把它修复掉吧。”Minion 就会当场生成代码修复补丁并提交。这样一来，完全不需要经历繁琐的“排入待办列表、延后排期处理”等冗长流程，当场就能完成即时修复。随着 Minion 能力的不断增强，我们看到越来越多这样的敏捷落地案例。

<details>
<summary>Original English</summary>

**Speaker B**: Creo que nosotros también podemos ver cómo él, como él, eh. Porque él integrado en Slack, usted puedes simplemente recuérdalo. Tú escribe @Minion o lo que quieras ¿Estás haciendo esto? Puedes escribir @Minion, y él te lo mostrará estado, tú tampoco necesito ir a navegador, puedes para conducirlo directamente a Flojo. Tal vez tengas Hilo de Slack con gerente de desarrollo o comestibles gerente, usted puede discutir el diseño cosas sencillas. Tú solo discutan y estar de acuerdo en todo eso, y entonces dices, "Oye, @Minion, sigue a este rama, ¿puedes? crear una solicitud para ¿Extracto? Y luego él tomará el contexto de Ramas de Slack y creará para su solicitud de extracto. Resultó que muy útil incluso en nuestros canales apoyo: cuando alguien reporta un error, El asistente le pregunta a Minion: ¿Puede ver? ¿Cuál es el problema y Minion? Respuesta: "Aquí está." "la causa principal." Oh, esto se ve bonito simplemente. Vamos Vamos a arreglarlo ahora mismo, y él está Lo arreglaré. Eso es No existe este ciclo agregando a la lista de tareas pendientes o aplazamiento entonces, puedes Arréglalo de inmediato en el lugar. Así que nosotros cada vez vemos más tales casos, porque Minion también se vuelve más poderoso.

</details>

### 云端 DevPod 与秒级 Bazel 构建环境

**Speaker A**: 这确实把整个构建与发布链条都打通了。我们此前也讨论过 DevPod，从那时起它又有了不少演进吧？

<details>
<summary>Original English</summary>

**Speaker A**: Por lo tanto , creo que nosotros recorrió el escenario colecciones. Nosotros también Ya se había hablado de ello DevPod. Ha mejorado desde entonces En aquel momento, ¿verdad?

</details>

**Speaker B**: 是的，没错。这里展示的正是我的所有 DevPod 实例。因为我目前处于图形化界面环境中，你可以直观看到它们。如果你需要创建一个全新的 DevPod，只需挑选对应的版本。针对 Minion，我们专门提供了一种定制化的 DevPod 配置，其中预装了全量仓库，并专门为与 Minion 协同工作进行了深度性能优化。而在工程师需要手动介入的交互式开发场景下，DevPod 也可以在短短数秒之内完成创建并准备就绪。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, sí, aquí mismo Todos se muestran mis DevPods. Porque yo Estoy trabajando en un gráfico. contexto, ya ves él. Pero si quieres crear un nuevo pod de desarrollo, tú eliges necesitas versión. Para Minion Hay una opción de pod de desarrollo, que contiene todo repositorios. Pero él también optimizado para usar con Esbirro. Para trabajo interactivo crea un pod de desarrollo mediante En cuestión de segundos y tú Ya lo tendrás lanzado.

</details>

**Speaker A**: 仅仅需要数秒钟，这确实令人印象深刻。我相信你们在底层采用了非常巧妙的技术机制，比如对环境进行常驻“预热”（warm-up）或者准备好预先构建完成的镜像供快速复制。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, eso es impresionante, para En cuestión de segundos. I Estoy seguro de que Haz cosas inteligentes. cosas, sosteniendo todo " "calentado" o preensamblado para copiar.

</details>

**Speaker B**: 是的，机制正是这样运作的，这也是专为开发者打造的生产力基础设施。我们利用独立的云端环境和 Kubernetes 集群，所有资源均已提前预置妥当。因此当你发起创建请求时，系统只需快速克隆一份预先组装好的快照镜像，其中已经内置了各层构建缓存、所有的代码仓库以及必要的依赖项。换句话说，一切都已经就绪，你可以立即开启编译构建。

值得一提的是，我们在全量代码仓库中统一采用 Bazel 作为构建系统。工程师可以直接拉取代码进入仓库并秒级触发 Bazel 构建。无论哪位工程师想要提交代码变更，都可以在瞬息之间拉起自己的独立开发 Pod——这是支撑起整个高效研发流程的核心支柱。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, funciona, así que ¿Cuáles son las herramientas para? desarrolladores. Nosotros utilizamos nube separada entornos, clústeres Kubernetes, donde todo está ya por adelantado preparado. Entonces cuando usted realiza una solicitud, Simplemente clonamos preensamblado imagen donde ya hay cachés colecciones, todas repositorios y todo lo demás otro. Es decir, todo listo para ti podría comenzar el ensamblaje. Quiero decir que nosotros usamos albahaca para todos nuestros repositorios como sistema de ensamblaje. I pudo entrar repositorio, lanzamos Basil y nosotros pasó por este proceso para una cuestión de segundos, donde cualquier ingeniero, Si quieres contribuir cambios en el código, crea El pod de desarrollo en un momento. Él la única manera

</details>

<!-- chunk 8/12 -->

### 构建命令与云端 Agent 的统一

**Speaker A**: ……能够构建任何模块，而且团队里的每个人都清楚这一点。现在，Agent 同样掌握了这些知识。在某种程度上，确实如此，对吧？云端的 Agent 清楚如何利用这些统一的构建命令，去构建或测试任何代码仓库中的任何模块。

<details>
<summary>Original English</summary>

**Speaker A**: ...recoger cualquier módulo, y todo el mundo lo sabe este equipo. Y ahora Los agentes también lo saben. ¿De qué manera, verdad? Agentes En la nube saben cómo para recolectar o para probar cualquier qué módulo en cualquier qué repositorio, usando esos los propios equipos.

</details>

**Speaker B**: 是的，我认为这涵盖了代码生成的核心任务，这些任务既可以交互式完成，也可以通过 Minion 异步执行。接下来的问题是：假设你已经生成了一个 Pull Request（PR），接下来该做什么？

<details>
<summary>Original English</summary>

**Speaker B**: Sí, Creo que esto cubre tareas principales con generación de código, que puede realizarse como de forma interactiva y vía Minion. Próximo pregunta: supongamos, Tienes relaciones públicas [PRs]. ¿Qué hacer más?

</details>

### 自愈型 CI 与内部循环提速

**Speaker A**: 那么，也许我们首先应该探讨一下具备自愈能力的 CI（Self-healing CI）。我们意识到，我们的 PR 总量每年都在递增。

<details>
<summary>Original English</summary>

**Speaker A**: Entonces, eh, tal vez primero Consideremos el CI, que autorreparable. Entendimos que El volumen de nuestras relaciones públicas está creciendo cada año.

</details>

**Speaker B**: 确实如此。显而易见，它呈现出爆发式的增长。

<details>
<summary>Original English</summary>

**Speaker B**: Oh sí. Aparentemente, él creció de forma explosiva.

</details>

**Speaker A**: 是的，没错。关注一下我们的 P50 和 P90 周期时间——从内部循环的角度来看，你手头有一个 PR，想要把它调整到可用状态，创建远程 PR，在 PR 创建之后，需要获取人工审查并跑通所有的 CI 检查。我认为，正如在其他任何公司一样，代码审查和检查已经成为了巨大的瓶颈，而且我们看到这种压力年复一年地加剧。因此，我们高度聚焦于此，剖析每一个环节，并在 AI 时代对其进行深度优化。

首先，我们做的是将大量此前在 PR 创建之后才运行的轻量级 CI 任务，直接前置转移到内部循环中，把它们全部打包收敛到一个命令里——类似于来自 AIFX 的统一验证命令（Validate from AIFX）。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, sí. Nuestro tiempo ciclo P50 y P90, en cuanto a ciclo interno, donde tienes relaciones públicas y quieres traerlo a condiciones de trabajo y crear un remoto Relaciones públicas y después creación de relaciones públicas— recibiendo verificación personas y Superando todos los CI. Creo que el cheque se hizo grande "cuello de botella", como en en cualquier otro empresas, y vemos la diferencia de año en año, así que estamos muy enfocado en, para clasificar cada uno aspecto y profundo optimizarlo para la era de la IA. Entonces, primero, lo que hicimos fue Tomé un montón de CI simple- tareas que anteriormente eran lanzado después crear relaciones públicas y Los trasladaron a bucle interior, juntarlo todo un equipo, como- Validar desde AIFX.

</details>

**Speaker A**: 这样一来，当 Agent 创建 PR 时，它能够自动启动并跑通这轮预检查循环。假设你提交了一个 PR，但依然有部分检查项未通过，这时我们的自愈型 CI 便会介入。你可以将该能力应用到所有 PR 上，或者针对特定分支分别配置。

这是 Uber 专门的一套工具链，我们将其集成注入到 GitHub 的每一个 PR 中，方便工程师将其与正在处理的 Issue 关联起来。在这里，你可以清晰地看到哪些检查没有通过，并能配置一整套自动化流程：自动请求审查、自动合并，以及自动修复。归根结底，我们所做的一切都是为了大幅压缩 P50 和 P90 的周期耗时。

<details>
<summary>Original English</summary>

**Speaker A**: Entonces, cuando el agente crea relaciones públicas, él puede comenzar, ellos puede pasar esto ciclo de verificación y Digamos que tú Creé una solicitud de extracción, pero algo más Todavía no funciona. Luego en somos CI, que autorreparable. Puede aplicar esto a todas las PR o por separado a todos. Él Cadena específica de Uber, que añadimos a todas las PR en GitHub para que puedas podría atarlo con un problema que laboral. Puede ver qué comprobaciones No pasar. Poder establecer una pila automatizaciones: solicitud automática para verificación, fusión automática, autocorrección. En esencialmente, todo lo que podemos hacer reducir el tiempo de ciclo P50 y P90.

</details>

### 代码收件箱与风险评估信号

**Speaker A**: 当完成了上述这套流水线后，我们构建了一个类似于“代码收件箱”（Code Inbox）的工作台。这里展示的是测试预览版，任何工程师都可以进入这个页面，一览所有等待自己审查的 PR，以及所有由自己发起、正等待他人评审的 PR。

因此，如果一名工程师提交代码并发起审查，我可以切换到该页面，全盘查看目前为止已经完成的各项校验。这极大地简化了认知负荷：我能够直观看到 AI 代码检查已经顺利通过，并清楚地看到它具体验证了哪些内容。这里包含端到端完整性测试的界面截图，所以我一眼就能把握状态，做到心中有数；你只需快速扫视一眼即可。这里甚至还附带了自动化测试的录屏视频，并且能看到代码构建的结果等等全部细节。

此外，我们还引入了风险评估指标、该 PR 的潜在破坏半径（blast radius）等维度。所有这些信息，都为工程师提供了极佳的辅助信号，帮助他们准确判断该变更是否值得投入合并，以及应当重点关注 PR 的哪些核心部位。

<details>
<summary>Original English</summary>

**Speaker A**: Y cuando todos ustedes Lo harás, lo tenemos algo así como "código-" bandeja de entrada. Se muestra aquí su versión de prueba, donde cualquier ingeniero pueden venir y ver todos los PRs esperando él, y toda la publicidad que él creado y esperando su consideración. Por lo tanto, si un ingeniero envía esto a comprobar, yo Me voy a cambiar a este página. Puedo para ver todo lo que lo hecho hasta ahora. Esto simplifica enormemente Entiendo que esa comprobación de código inteligencia artificial tuvo éxito. Aquí cosas que él comprobado. Esta es una imagen pantalla de prueba en integridad. Así que yo Lo sé, de acuerdo, lo entiendo. Puedes simplemente Echa un vistazo rápido. Aquí También hay un vídeo. Sí, ya veo resultados del ensamblaje y todo lo que. Nosotros también agregar un indicador riesgo, radio derrotar esta PR, etc. Todo esto dará Los ingenieros son geniales señales a para entender si vale la pena implementar esto y ¿Qué partes de las relaciones públicas deberían prestar atención.

</details>

### 应对 PR 洪峰与 CI 红线警报

**Speaker A**: 在这个方向上，我们目前仍在积极推进演进。我们脑海中有很多构想，但当务之急是确保底层架构能够承受住 PR 洪峰的冲击。

事实上，我们此前不得不为内部的 CI 系统拉响“红色代码”（Code Red）警报，因为平台上的 CI 任务量同比翻了一倍甚至更多。因此，我们必须大幅加固底层的基础设施基石，以随时应对大量新增 PR 的持续涌入。

<details>
<summary>Original English</summary>

**Speaker A**: Y entonces, Creo que todavía Estamos trabajando activamente en por la presente. Tenemos mucho ideas, pero queremos para asegurarnos de que listos para la afluencia solicitudes de extracción (PR). De hecho, nosotros tuvo que anunciar "rojo" interno código" para nuestro CI- sistemas, porque número de tareas de CI con se duplicó año tras año o incluso más. Así que tuvimos que fortalecer mucho fundamentos en este en el campo para ser listos para la afluencia nuevos PR.

</details>

**Speaker B**: 是的，而且我认为你也观察到了：工程师们已经无法像过去那样，对每一个 PR 都做到同样细致入微的人工审查了。所以，你们打造这些工具的目的，正是为了高亮提示哪些 PR 值得投入更多注意力，而哪些变更在很大程度上属于低风险变更——无论从影响面还是潜在破坏半径来看都是如此。

关于未来的代码审查，你的长远判断是什么？你认为人类的代码审查会一直不可或缺，还是说在某些场景下它完全可以被取代？

<details>
<summary>Original English</summary>

**Speaker B**: Sí, y creo que tú También ves que Los ingenieros no pueden puede comprobarlo todas las relaciones públicas con el mismo cuidadosamente, como más temprano. Entonces, supongo que tú crear herramientas para para señalar cuál De ellos vale la pena prestar atención más atención, y cuáles puede ser bajo riesgo en en muchos aspectos, tal vez bajo la influencia o radio de daño. ¿Cuál es tu opinión sobre de lo que sucederá en el tiempo ¿Con verificación de código? Como ¿Tú crees? siempre será necesario verificación de código una persona, o para algunas cosas ella ¿Puede desaparecer?

</details>

### 审查安全界限与“绿色通道”

**Speaker A**: 是的，毫无疑问。首先，我们始终把安全性放在首位，因为对于 Uber 而言，线上事故的代价是极其高昂的。因此，即便拥有了所有这些辅助工具，现阶段我们依然严格要求：凡是进入主干的 PR，都必须经过工程师的人工审核。

随着我们对自身风险评估模型的置信度不断提高——我们拥有并深入回溯了过去多年的全量历史数据，对这些历史样本的分析越透彻，同时对 AI 代码自动化检查的信任度越高——未来对于某一类明确判定的低风险 PR，我们完全可能开启所谓的“绿色通道”（Green Corridor），即允许其全自动合并上线。

但在迈向这一步之前，我们必须在各个维度上确保绝对的安全与万无一失。眼下的第一优先级，依然是如何简化工程师的工作，为他们集齐所有关键评估信号，以加速人工审查进程。只要我们把这一步夯实走稳，我相信随着时间的推移，能够自动批准合流的 PR 比例必将逐步提升。但现阶段的 P0 和 P1 核心优先级，始终是将所有审查信号统一收敛到一个集中的地方。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, definitivamente. Por lo tanto, Sí, creo que, en primer lugar, siempre queremos para estar seguros, porque costo del incidente Para Uber es muy alto. Así que incluso con todos estas herramientas, En este momento todavía estamos exigimos que El ingeniero comprobó cada PR que llega. Cuanto más Estamos seguros nos metemos en nuestro evaluación de riesgos, por lo tanto más podemos Échale un vistazo retrospectivo datos de años, o no ¿Sí? Tenemos todos estos datos. Y cuanto más tenemos confianza en nuestras inspecciones código artificial intelecto, tal vez, para una determinada clase PR de bajo riesgo nosotros podemos encender eso, lo que llamamos "corredor verde", es decir, automático implementación. Pero nosotros queremos ser absolutamente seguro de en todos los aspectos, especialmente que pasar a este. Y ahora máxima prioridad— cómo hacerlo más fácil ingenieros recibiendo todo lo necesario señales para Revisión más rápida. Y si estamos bien Nos ocuparemos de esto, yo Estoy seguro de que con el tiempo podremos aumentar porcentaje automáticamente Relaciones públicas aceptadas. Pero este prioridad P1 o P0 es a Primero reúnan todos señales en una lugar.

</details>

### Slate 环境沙箱与端到端手动验证

**Speaker B**: 极好。是的，把代码放在沙箱（“Box”）里跑确实很棒，我很喜欢这种方式。但这正是我们必须面对的问题：比如我该如何验证代码逻辑的正确性？对于不熟悉内部行话的人来说，“校验正确性”本质上就是手动测试（Manual Testing），对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Perfectamente. Sí, pero el código en "En cajas" es bueno. Me gusta. Esto es lo que debemos hacer tocar, por ejemplo, ¿cómo puedo para comprobar para que sea correcto. Y comprobando corrección, para aquellos que ¿Quién no lo sabe? jerga interna —esto es manual ¿Probando, verdad?

</details>

**Speaker A**: 没错，就是手动测试。假设我现在正在开发一个新功能，这个功能横跨并影响了两到三个微服务。我该如何确认这个功能端到端能够正常跑通？

在引入 Agent 之前，工程师们典型的工作流程依托于我们称之为 Slate 的系统。本质上，你可以为自己正在开发的代码分支单独拉起并部署一个专属副本环境。然后，你可以将测试账号的 UID 流量精确导向你所创建的这个副本中。当你向系统发起调用时，请求就会精准命中你分支上的最新代码。

事情就是这样运转的：你处于当前分支上，而其余所有未修改的上游及下游请求，都会自动走回常规的测试过渡环境（Staging）。因此，你可以无缝进行端到端全链路验证，完全不必操心其他区域基础设施的部署负担，而且流量路由会自动覆盖整个微服务拓扑图。

举个例子，你可以在移动端应用中指定：“看，这是一个我用于测试的专属测试账号。”于是调用链路流经各个服务时，只要遇到被修改的目标服务，请求就会自动转入你部署的 Slate 实例上。如果你同时调试两个或三个服务，流量便会在这两三个被测服务间无缝穿梭。也就是说，你甚至可以做到多服务同时联合测试。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, pruebas manuales. Sí, quiero, digamos, Estoy trabajando en algo nueva función. Ella afecta a dos o tres servicios. ¿Cómo lo hago? Averigua si funciona esta función de ¿De principio a fin? Entonces, trabajador típico proceso para ingenieros —esto, digamos, enfoque preagente, Lo llamamos pizarra [Slate]. Esencialmente, puedes crea el tuyo propio una copia que despliega una rama, sobre ¿Para qué trabajas? Y tú ¿Puedes dirigir? tu prueba UID de cuenta en creado por ti Copiar. Entonces cuando entras dentro del sistema, usted ejecutar esta rama. Así es. En curso rama y el resto ascendente y consultas descendentes ve a otros entornos intermedios. Por lo tanto, usted puedes probar de principio a fin, no preocuparse por los demás regiones infraestructura. Y esto se extenderá a todo el gráfico de servicio. Entonces, puedes para decirlo con tus propias palabras aplicación móvil: "Oh, esta es una cuenta de prueba. ¿Cuál quiero? comprobar". Él pasará por otros servicios y cuando afectará al servicio, ¿Qué se está probando? irá a tu Instancia de pizarra [Slate]. Si usted prueba dos o tres, luego pasará a servicio que probado, para todos dos o tres. Así que tú incluso puedes hacerlo probar múltiples servicios simultáneamente.

</details>

### MCP 驱动的自动化 Slate 部署与测试

**Speaker A**: 既然我们已经具备了这套坚实的基础设施，接下来要做的，就是训练 Agent 学会如何部署和使用 Slate。同时，我们向 Agent 开放了所有现存的内部 API，使它们能够自如地在各个微服务之间进行导航和交互。

本质上，以前作为工程师，每当我想做一次校验、想要手动验证自己的改动时，我掌握了一套相当出色的自动化手段。而现在，我只需将这些指令下发给 Agent，它们便能完全自主且安全地沿着整条链路，对你提交的代码变更完成端到端测试。

是的，这里展示的就是它的 Web 端形态。你可以清晰地看到，这实际上复用了我们经过严格审批的标准 CLI 模板。它通过 MCP（Model Context Protocol）接入 Slate 服务，创建出全新的 Slate 隔离环境，并赋予该环境指定的命名标识；紧接着，一旦环境构建完毕，指令便会自动执行，将目标服务部署到该环境中……

<details>
<summary>Original English</summary>

**Speaker A**: Ahora que teníamos esto, necesitábamos solo agentes de entrenamiento Implementar Slate. Nosotros también les dio todo API existentes que se pueden uso para navegación en cualquier ¿Cuál de los servicios? En esencia, era una situación en la que estoy como El ingeniero quería realizar una inspección, es decir, deseado manualmente para probar tu cambios. Yo tenía forma de hacerlo bastante genial método. Y ahora yo Simplemente puedo dar instrucciones esto es para agentes y ellos podrá hacerlo de forma segura prueba el tuyo cambios a lo largo. Sí, aquí te lo mostramos versión web de esto, y tú puedes ver De hecho, que este es el la misma plantilla CLI que Hemos aprobado. Él utiliza pizarra [Slate] MCP para crear uno nuevo entornos de pizarra, indicando el nombre de este ambiente. Y luego, cuando el entorno creado, dice implementar el servicio en este entorno,

</details>

<!-- chunk 9/12 -->

### 基于 Slate 与 Jaeger 的微服务隔离环境与分布式追踪路由

**主讲人**：在指定了服务名称之后，这是一次针对该服务的测试。现在，它专属的 Slate（沙箱/白板）环境已经生成出来了。在用户界面上可以看到，如果查看这里，你会发现可以固定 UUID、设定针对该副本的测试账号，并且能看到位于该环境下的所有服务，甚至能查看具体的 Git SHA 提交哈希。现在，AI 代理在内部就可以直接调用所有这些技能与工具。

正如你所看到的，它对该 Web 前端组件运行了 A/B 测试。代理在 Slate 环境中打开浏览器，将 `main` 主分支上的效果与我分支上的修改进行对比，并为我自动生成了一份完整变更清单的评估报告。

<details>
<summary>Original English</summary>

**Speaker A**: Indicando el nombre del servicio. Esto es una prueba del servicio. Y ahora apareció en su propio entorno Slate. En la interfaz de usuario, como verás si miras aquí, puedes fijar el UUID, cuentas de prueba para esta copia, y verás todos los servicios ubicados en este entorno. Puedes ver el Git SHA. Y ahora el agente puede internamente usar todas estas habilidades y herramientas.

Entonces, ¿cómo verás? Él dirigió A/B testing de esa web-elemento. Él abrió el navegador agente en ese entorno de Slate con lo que hay en la rama principal (main) y en mi rama. Y me creó un informe para que yo pueda ver la lista completa de cambios.

</details>

**主讲人**：随后我们可以直接查看它生成的报告。该报告清晰地对比了“修改前（before）”与“修改后（after）”的状态，证明没有引入任何功能回归。这对工程师来说极易核验，而且我们还可以直接将屏幕截图和视频补充到 PR（Pull Request）中。我们在 iOS、Android 以及 Web 端都拥有相同的这套能力。如果你想直接测试服务端的 API 接口，同样也可以做到。

<details>
<summary>Original English</summary>

**Speaker A**: Y entonces, ya sabes, después podemos ir al informe que genera. Digamos que él creó un informe que muestra el estado "antes" y "después", muestra que regresiones no hay, y para los ingenieros es muy fácil comprobar, y nosotros podemos añadir capturas de pantalla y vídeos para el PR. Tenemos lo mismo para iOS, Android y web. Y si quieres probar el API del servidor, también puedes hacerlo.

</details>

**对话嘉宾**：我只想补充一点，如果你不在 Uber 工作，可能很难体会到这一点：Slate 极其关键。因为 Uber 内部依然维护着数以千计的微服务（或者有些甚至算不上真正的“微”服务）。要想在某个单一服务中做出修改，同时跑通完整的端到端集成测试，本身就是极其困难的一件事。这就是为什么后来催生并构建出了 Slate。

<details>
<summary>Original English</summary>

**Speaker B**: Solo quiero agregar que hay cosas que puede que no aprecies si no trabajas para Uber, pero Slate es muy importante porque Uber todavía tiene miles de microservicios, o tal vez no del todo micro, así que correr cambios en un solo servicio cuando lo deseas para hacerlo de principio a fin pruebas es bastante difícil, ¿verdad? Por eso a continuación se creó Slate a lo largo de los años.

</details>

**主讲人**：没错，而且不仅如此，你还需要考虑固定测试账号的请求路由机制。比如，什么叫做“固定测试账号”？它指的是同一个测试账号，我希望它发起的请求专门定向路由到我刚部署在测试环境下的那条特性分支上。这绝不是一项简单的任务。

它之所以能够正常运转，是因为我们在 2017 到 2018 年左右构建了另一套核心基础设施——分布式追踪系统 Jaeger。现在它已经完全开源了。在我们内部，所有的微服务都深度集成了 Jaeger Span。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, y se necesita más pensar en enrutamiento de cuentas fijadas, ¿bien? Por ejemplo, ¿y qué es fijo cuentas? Este es el mismo cuenta de prueba que quiero dirigir a mi rama que solo fue desplegado en ambiente de pruebas. Esto es completamente no es trivial tarea.

Entonces, en realidad, esto funciona porque ¿qué más hemos construido? En algún momento de 2017-18, se llama Jaeger, esto es infraestructura de rastreo repartido. Ahora esto es código abierto. Y todos los nuestros servicios tienen tramos de Jaeger.

</details>

**主讲人**：事实上，无论请求在何处被发起，系统都会维持父级 Span（Parent Span），而在调用链的每一个子阶段都会衍生出子级 Span（Child Span）。你可以在追踪链路中附加任意的上下文元数据（Baggage），这些 Baggage 会沿着整个服务调用栈一路透明透传向下扩散。

因此，当你从 Slate 的 Web 界面发起请求时，我们实际上就在 Baggage 中注入了标记：“这里是正在被测试的服务列表，这里是需要定向路由的目标账号”。当该请求穿过我们的服务网格（Service Mesh）时，网格组件能够识别出这些 Baggage 标签，并做出判断：“哦，这个请求不应该走默认环境，而是需要精确路由到对应的 Slate 沙箱环境”。

正是因为我们早已构建了完善的分布式追踪体系并在调用栈中可靠透传，你现在才能真正进行端到端的隔离测试。我们能够放心地把此类测试请求直接引导至所需的目标环境，从而极大地简化了微服务下的测试复杂度。我们花了数年时间才让所有既有服务全面适配这套机制，而后续所有全新的服务在设计之初就天然具备这一能力。

<details>
<summary>Original English</summary>

**Speaker A**: De hecho, no importa dónde hubo un desafío, hay tramo padre, y en cada etapa es desarrollo infantil, y tú puedes agregar cualquiera equipaje al rastreo que se extenderá a través de la pila de llamadas.

Entonces cuando hagas la solicitud desde esta web-interfaz de Slate, nosotros de hecho indicamos que aquí están estos servicios que se están probando, y aquí está la cuenta que quiero dirigir. Desde la solicitud pasa a través de nuestro malla de servicios, reconoce este equipaje y puedo decir: "Oh, yo quiero enviar esto no a la producción o pregunta general, sino en este entorno de Slate".

Porque nosotros rastreo desarrollado y se propaga a través de la pila, ahora tú de verdad puedes probar, y nosotros podemos confiar en dirigir tales consultas de prueba en los entornos necesitados, lo cual simplifica enormemente las pruebas. Se necesitaron años para asegurarse de que todos los servicios existentes eran adaptados para esto, y totalmente nuevos fueron creados a partir de teniendo esto en cuenta.

</details>

### 数据录制与流量回放机制（Capture and Replay）

**对话嘉宾**：我逐渐体会到一种明显的趋势：在 AI 时代到来的多年前，Uber 就已经在不断打磨与构建这套既方便工程师手动测试、又极易实现自动化的基础设施。如今有了 AI，外界感觉这些功能就像是过去一年里凭空做出来的，但实际上你们是站在了过去多年持续深耕的技术基石之上，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Estoy empezando a sentir la tendencia de que Uber, años antes de la era de la IA, construyó infraestructura que es fácil de probar para personas o fácilmente automatizar. Y ahora con la IA parece que construimos esto durante el último año, pero en realidad tú has construido sobre la fundación que fue creada a lo largo de los años, ¿no es así?

</details>

**主讲人**：正是如此。我可以肯定地说，如果我们没有像 Slate 这样的底层系统支撑，AI 代理生成的代码将极其难以自动核验，也就根本无法落地端到端的自动化。正如你所言，这些既有的技术积累起到了决定性的助推作用。

另外，我还想分享另一个针对 Uber 业务场景非常独特、且极难做好的工程实践。过去我们内部有过许多类似的探索和演进版本，但我认为目前这一版绝对是我们做得最出色的，并且能够切实推广推广至所有团队。其核心理念在于对真实业务“上下文”的把控。

哪怕仅仅看我们最核心的乘客端主 App，其中就包含数百个不同的功能界面。大多数人眼中的“Uber App”通常就是指这款乘客端应用。但实际上，我们涵盖了多种不同的业务线（Lines of Business）、极为丰富的细分产品线、成百上千个不同的运营城市，以及数不胜数的业务维度。

<details>
<summary>Original English</summary>

**Speaker A**: Sí. Estoy seguro de que si no teníamos esos sistemas como la Slate, los agentes serían muy difícil por tu cuenta ser revisado. Entonces tú no puedes hacer esto automatizar, y así sucesivamente, como dijiste, tales cosas realmente ayudan.

Yo también te contaré sobre otro algo interesante que es muy específico de Uber y muy previamente, sí, y es muy, muy difícil de hacer bien. Tenemos incluso habido muchas versiones de similares desarrollos en el pasado, pero creo que esto probablemente nuestro mejor versión, y podemos escala realista en todos los equipos. Pero esencialmente, la idea en contexto, porque en nosotros, incluso si mira a la aplicación principal para pasajeros, ¿verdad? Tenemos cientos de pantallas. Y esta aplicación es para pasajeros—esto es lo que la mayoría de la gente considera la aplicación Uber, ¿sí? Esta es la aplicación para pasajeros.

</details>

**对话嘉宾**：也就是说，如果要验证一项全新改动，并排查在所有可能的业务组合下是否引入了破坏性回归，如果采用穷举排列组合的方式，你可能需要针对整条技术栈维护并运行成千上万个测试用例。这正是我觉得极为棘手的地方。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, tenemos diferentes negocios, varias líneas de productos, ciudades diferentes, un montón de otras dimensiones. Como probar algo nuevo y descubre si ninguna regresión en absoluto combinaciones posibles. Si estuvieras creando todas las permutaciones, tú tendría que apoyar a miles de pruebas por todas partes de la pila, y esto es exactamente lo que es difícil para mí tarea.

</details>

**主讲人**：正是如此。因此针对部分最复杂的平台，我们采用了所谓的“捕获与重放”（Capture and Replay）机制。本质上，由于我们内部对所有微服务都推行了标准化的服务框架，你只需挂载一层通用的中间件（Middleware），就能轻松接入并直接录制生产环境中的真实线上流量。

该系统不仅能够录制各服务层级的入站（Inbound）与出站（Outbound）请求，还能完整拦截并记录所有向下的下游 API 调用。这些成对的请求与响应都会被固化持久化下来。从某种意义上说，你由此获得了一套包含所有下行依赖调用的完整请求/响应历史快照。

所有捕获到的流量数据都会经过一条处理流水线（Pipeline）。在这条流水线上，平台团队可以配置简单明了的路由与过滤规则：例如，当请求体包含特定字段时，提取该值作为关键维度参数。这样一来，团队就能灵活固化并提取出对其最为关键的各类业务维度。

基于所有捕获的请求与提取的参数维度，系统可以自动聚合出平台当前在线上实际支持的全量组合矩阵。我们称之为“Match Guard”（匹配守卫）。我们直接将其接入到 CI/CD 流程中并在部署前执行：当任何 PR 提交时，系统都会基于这套全量业务组合运行发布合规校验，精准比对变更前后的数据差异。这赋予了工程师极高的发布信心——确保自己的修改绝不会破坏任何隐藏边界，比如在某种特定配置下，针对巴西地区的特定行程缓存策略是否被意外破坏。这种隐蔽场景无论是靠人工测试还是单纯靠 AI 代理，往往都极难全面覆盖。

<details>
<summary>Original English</summary>

**Speaker A**: Por lo tanto, para algunos de nuestros el más difícil plataformas que lo usamos así llamada "captura y reproducción" (capture replay). Esencialmente, tú puedes admirar tienda de comestibles de verdad tráfico utilizando sólo uno intermedio software (middleware), porque ahora tenemos marcos estandarizados para todos servicios. Esto es muy fácil de integrar.

El sistema captura no solo entrantes y tráfico saliente en niveles de servicio, pero también todos llamadas a API inferiores. Estas solicitudes y respuestas también están fijos. Entonces en cierto sentido tú te llenas historial de consultas respuestas, incluyendo todos solicitudes salientes. Todo estos datos capturados pasar por cinta transportadora donde puedes configuración sencilla reglas: si en la consulta tiene dicho campo, entonces este valor para importante parámetro. Entonces, tú ¿puedes arreglarlo? cualquier parámetro importante para el equipo plataformas.

Tener todo consultas y parámetros, se puede generar juego completo actual combinaciones que con el respaldo de la plataforma. A esto lo llamamos "match guard"—puedo ejecuta esto antes desplegado en nuestro CICD, para que para todas las PR en este comprobación de liberación conformidad juego completo combinaciones y ver la diferencia antes y después. Esto da alta confianza: ¿No estoy rompiendo algo? Por ejemplo, caché-viajes a Brasil en esta configuración, eso sería muy difícil probar manualmente ingenieros o agentes.

</details>

### 会话检索、单请求复现与历史工具演进

**对话嘉宾**：所以整个链路的第一步是流量捕获，随后系统会基于捕获到的查询数据自动重放，以检测可用性与潜在的业务回归，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Entonces, el primer paso es captura de datos y entonces su sistema reinicia a consultar disponibilidad regresiones.

</details>

**主讲人**：是的，我带你直接看一个已经开启该功能的业务域界面。在这里你可以浏览所有已被录制捕获的会话（Sessions）。我可以随意点进任意一个具体会话，随即就能查阅到该请求附带的所有元数据和标签信息。实际上系统已经清晰标注：“该请求被标记为 marketplace 类型，子类型为 Eats（餐饮外卖），业务线归属于食品业务，处于某种特定的终态生命周期”。平台完整保存了这条请求的全部原始上下文。

你还可以查阅所有相关的下游出站调用。点击展开后，系统会展示出该出站连接具体的请求报文与下游返回的响应体。在页面顶部，你可以看到对应的 Worker 进程 UUID，或是用于检索的 Slate 沙箱环境名称。

举个实际场景：假设我正在修复一个仅在旧金山特定条件下的 Uber Eats 订单中才会触发的偶发 Bug。我做完代码修改后，可以进入这个界面，直接针对该 Bug 关联的 Slate 沙箱环境发出指令：“把这个线上录制下来的真实请求，单独在我当前分支的 Slate 环境中重新回放一次，并把差异对比展示给我看”。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, voy a seguir adelante uno de los dominios donde esto está activado. Tú puedes verlo todo sesiones capturadas. Puedo ir a cualquier de las sesiones. Siguiente ver todos los metadatos y etiquetas. De hecho, ella dice: "Oh, esta solicitud marcado como mercado, escribe 'come' (Eats). Marcado como línea de negocios de alimentos. Está ubicado en como esto condición terminal". Ella sabe que capturó la consulta completa.

También puedes ver todo fines de semana usados peticiones (downstream requests). Si nosotros hagamos clic en ellos, el sistema mostrará una solicitud y la respuesta para conexiones salientes. Y si lo miras desde arriba, ahí está el UUID del trabajador proceso o nombre de la Slate entorno de búsqueda.

Ejem, entonces digamos que si alguien, si trabajo sobre el error que por alguna razón afecta solo viajes de Uber Eats en San Francisco. Sí. Estoy arreglando esto error, y entonces puedo crear un entorno Slate por este error por mis cambios en ¿Adónde puedo ir aquí y decir: "Juega solo este solicitud en mi entorno de Slate y muéstrame la diferencia aquí"?

</details>

**对话嘉宾**：展示修改前后的差异，然后你期待看到这个 Bug 得到修复或者出现符合预期的业务变更。

<details>
<summary>Original English</summary>

**Speaker B**: Muéstrame la diferencia, y esperas corrección o ciertos cambios.

</details>

**主讲人**：对，我期待看到它被正确修复。由于我预先知晓该请求在修改前后的表现，随后我不仅能在单一维度上复现它，还能结合前面提到的 Match Guard 机制，利用自动生成的全量维度组合，对这些微服务运行完整的端到端自动化测试集；同时，这也为开发人员提供了一种极其简便的手动单点排查手段，帮助你精准聚焦在当前关注的那一种极端特定组合上。

<details>
<summary>Original English</summary>

**Speaker A**: Espero una corrección. Entonces, ya que lo sé consulta antes y después de eso yo estoy esperando... Y luego yo ¿puedo hacer esto por de cierta dimensión o úsalo como... Y también generamos eso, quien mencionó cómo coincide guardia (Match Guard), que está completo un conjunto de posibles medidas para esto. Para que puedas para crear un cierto conjunto de medidas automatizado pruebas para esto equipos, así como forma más fácil prueba manual uno específico una combinación en la que estás concentrado.

</details>

**对话嘉宾**：我在 Uber 的时候系统里还没有这套机制，不过当时有两款名为 Deputy 和 Cerberus 的内部工具，但那些应该算是非常早期的雏形版本了。

<details>
<summary>Original English</summary>

**Speaker B**: Cuando estuve allí, teníamos este no fue el caso, pero había algo llamado Diputado (Deputy) y Cerbero (Cerberus), pero este probablemente eran muy primeras versiones.

</details>

**主讲人**：是的，那确实是底层演进的开端。正是从 Deputy 和 Cerberus 开始沉淀出了流量路由的能力：Deputy 支持将生产环境中的任意指定查询流量无缝路由到你的测试实例上，而 Cerberus 则负责从你的测试环节中……

<details>
<summary>Original English</summary>

**Speaker A**: Sí, de hecho, eso es lo que permitió al Diputado y a Cerbero—esta es una oportunidad ruta cualquiera lo cual... el Diputado permitió ruta cualquiera qué consulta de productivo entorno a su instancia de prueba y Cerbero—de tu prueba...

</details>

<!-- chunk 10/12 -->

### Slate 与 Capri 在沙盒重放中的协同

**Guest**: ……本地复制回测试服务器。但现在我们有了 Slate 环境，就不一定非得依赖副驾（adjunct）和 Cerberus 了，因为……

<details>
<summary>Original English</summary>

**Guest**: local copiar de vuelta a servidores de prueba. Pero ahora que tenemos Hay una pizarra [Slate], no la tienes necesariamente usar al adjunto y Cerbero, porque ya...

</details>

**Host**: 你能详细展开说说吗？有了 Slate 环境之后，为什么就不需要使用它们中的任何一个了？

<details>
<summary>Original English</summary>

**Host**: ¿Puedes expandirte? Entorno de pizarra [Slate], y nosotros No hay necesidad usar Ninguno de ellos.

</details>

**Guest**: 我只是想强调一下这一点，因为从外部来看可能很难体会到，但实际上搭建这套体系非常困难。因为每一个单独的微服务——而这里有成千上万个微服务——都必须支持这些能力，比如路由支持，从而能够将生产环境的数据分流并进行重放，不是吗？可以想象，这背后涉及了大量的工作。

<details>
<summary>Original English</summary>

**Guest**: Solo quiero para enfatizar, porque creo que, que es difícil de ver desde fuera, pero es muy difícil de construir, porque cada individuo servicio—y hay miles de ellos— debe apoyar estas cosas, de enrutamiento, por ejemplo, para deleitar datos productivos y reproducción, o no ¿Sí? Supongo que Fue mucho trabajo.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Sí,

</details>

**Guest**: 现在，正如我们为 AI Agent 赋予了访问 Slate 的权限一样，我们同样可以让 Agent 访问 Capri 的全部功能。这样一来，当它们在排查问题时就可以说：“哦，我正在尝试修复这个 Bug。让我调出所有此类请求的会话，看看真实请求到底长什么样。我能不能在自己的 Slate 实例中构造一个类似的请求，来看看问题是否已经修复？如果还没有解决，那我就继续循环调试，直到彻底修好为止。”

<details>
<summary>Original English</summary>

**Guest**: y ahora creo que igual que nosotros Se proporcionó acceso a Slate agentes, podemos para proporcionar agentes acceso a todo Funcionalidad Capri, para que pudieran comprobación: oh, yo Estoy probando esto para arreglar. Permitir Lo consigo todo sesiones de este tipo y entonces mira cómo Parece una solicitud. O ¿Puedo crear una solicitud este tipo en el mío instancia de Slate y para ver si ¿Se solucionó? ¿No? Déjame dar vueltas en círculos mientras yo No voy a arreglar esto.

</details>

**Host**: 对，对！而且现在 Agent 就算无法直接“肉眼观察”，它也能通过比对变更差异（delta）来理解当前状态，比如发现“什么都没有改变”。因此，它就获得了一个闭环的反向反馈回路。

<details>
<summary>Original English</summary>

**Host**: Sí, sí, y ahora agente, incluso si no ve, puede ver delta y entender, por ejemplo, que nada no ha cambiado. Por lo tanto, él puede recibir ciclos inversos comunicación.

</details>

**Guest**: 没错，完全正确。我认为这极具帮助。现在 Agent 还可以在 Slate 中针对上述任意场景进行录制与流量回放。

<details>
<summary>Original English</summary>

**Guest**: Así es. Así es. Creo que es muy ayuda. Ahora el agente también puede para registrar y reproducción en Slate con cualquiera de estos.

</details>

### Edge 网关与分布式依赖拓扑

**Host**: 我们之前已经讨论过了 Edge 网关。Edge 网关其实很简单，它就是 Uber 的内部 API 网关，对吧？它以前叫 RT API（Real-Time API），但现在被称为 Edge。它是 Go 语言重写版本，如果我没记错的话？

<details>
<summary>Original English</summary>

**Host**: Nosotros Ya se habló de la puerta de enlace Borde [Edge]. Puerta de enlace perimetral: es simple. La API interna de Uber, ¿verdad? Anteriormente era RT API, API en tiempo real, pero ahora él llamado Edge. Él Versión Go, esta es reescrito en Go versión si yo ¿Lo recuerdo bien?

</details>

**Guest**: 没错，它是用 Go 编写的，现在支持大量不同类型的端点：标准 REST API、gRPC、Webhooks、GraphQL。同样地，所有 API 请求都穿过这样一个统一入口，我们就能在上面构建一整套完善的监控、观测与报警工具栈。

而且除了这些可靠性特性之外，Edge 网关自身也具备录制与回放功能，类似于 Capri。实际上它在幕后直接复用了 Capri 的底层能力。

如果你想验证某个组件的可靠性，我们可以直接调出完整的全局服务依赖拓扑图，明确指出哪一个节点可能处于亚健康状态、需要重点关注。得益于这种全链路端到端分布式追踪方案，我们能够极其精准地掌握各个微服务之间的依赖关系。我们甚至会自动标注出哪些依赖调用是强依赖（强制必需），哪些是弱依赖（可选容降）。

所以这些元数据也都是立即可用的。因此，当我们排查报警和进行故障诊断时，所有这些极其丰富的上下文不仅能帮助工程师，也能让 AI Agent 以快得多的速度完成系统配置与问题定位。

<details>
<summary>Original English</summary>

**Guest**: Sí, está escrito en Go ahora es compatible un montón de tipos puntos finales: API estándar, GRPC, webhooks, GraphQL. De nuevo Sí, todas las API pasan a través de un punto entrada donde podemos construir una pila herramientas para monitoreo y notificaciones. Y aun con todas estas funciones fiabilidad, Edge también tiene su propio récord y reproducción, similar a Capri. Él utiliza Capri para entre bastidores. Y si tú quiero comprobar confiabilidad de algo, nosotros Veamos el gráfico completo servicios y decimos, qué nodo potencialmente poco saludable y Necesita atención. Gracias a la solución integral Somos precisos en el rastreo conocemos las dependencias servicios. Nosotros también automáticamente marcado cuál La adicción es obligatorio, y cuál— opcional. Así que estos metadatos también disponible. Por lo tanto, cuando estamos revisando notificaciones y nosotros los diagnosticamos, todo este rico contexto realmente ayuda como ingenieros y agentes más rápido conducta configuración.

</details>

### 代码库演化工具：Shepherd 与 Fox

**Host**: 是的，我们之前也聊过实验系统。接下来我们要聊的最后一件重要工具，就是被我们称为 Shepherd（牧羊犬）和 Fox（狐狸）的系统。当初迁移到 Monorepo 单体大仓之后……之所以迁移，是因为以前跨仓库升级依赖库实在太痛苦了，对吧？

<details>
<summary>Original English</summary>

**Host**: Sí, lo somos. Ya se ha hablado de ello experimentos. Lo último que hicimos Consideremos, esto es lo que Llamamos Pastor [Shepherd] y Zorro [Fox]. Después de que cambió a monorepositorio y Nos mudamos porque actualizar La biblioteca era muy Es difícil, ¿verdad?

</details>

**Guest**: 是的，跨分散在各处的代码仓库去升级，确实非常困难。

<details>
<summary>Original English</summary>

**Guest**: Sí, en todos los diferentes repositorios, sí.

</details>

**Host**: 没错。但当你把一切都合并进单一 Monorepo 之后，现在又变成了：必须有人去把这个大仓库里成百上千个模块中所有使用该依赖库的地方逐一进行升级更新。那么，我们该如何将其自动化呢？

<details>
<summary>Original English</summary>

**Host**: Así es. Entonces tú ir a monorepositorio, pero Ahora alguien tiene que entrar y actualización uso de este bibliotecas en todas módulos de este repositorio. Entonces, ¿cómo nosotros esto ¿automatizar?

</details>

**Guest**: 所以最开始，我们尝试使用 OpenRewrite 这类开源重写规则策略。我们的思路是：“好吧，如果改动相对简单，例如单纯修改函数签名，你就可以把规则写在 OpenRewrite 策略文件中。”随后，Shepherd 会自动分析出各个受影响的独立模块分别归属于哪些团队，并针对每一个模块全自动生成对应的 Pull Request。

而当人工智能浪潮到来后，我们得以将 Shepherd 接上 AI 能力底座。举个例子，假设我想在全公司所有微服务中统一修复上下文传递（Context Propagation）逻辑，以使分布式追踪的效果更上一层楼。我就可以编写一组专项提示词准则和技能（Prompts & Skills），让 AI Agent 顺次遍历检视各个模块，并极快地在全量微服务中自动修补问题。

因此，这涵盖了各类超大规模的代码改造需求，无论你想要的是完全确定性的规则替换，还是基于 Agent 智能分析的模块内部改造。多年来，它支撑我们平稳推进了大量架构迁移工作，我们将每一次这样的集中迁移称之为一次“战役”（Campaign）。

如果你去观察从 JUnit 4 迁移到 JUnit 5 的完整过程，你就会看到：一个统一的 YAML 策略配置文件、为每个模块批量派发的海量 PR，以及战役负责人对全局推进状态的看板监控与集中审查。这极大简化了超大规模技术迁移的管理成本。

就在几个月前，我们基于这一套平台架构，又衍生扩展出了一项全新的核心功能。我们意识到，团队不应该只满足于单次孤立的技术迁移，我们更希望将这个流程常态化，追求代码库的持续、主动进化与自洁。假设我想做常态化的代码保养维护——

<details>
<summary>Original English</summary>

**Guest**: Por lo tanto, primero nosotros intentó usar políticas de reescritura abiertas, diciendo: "Está bien, si es algo simple, por ejemplo, simplemente cambia firmas, puedes escribe esto en "política de reescritura abierta" y entonces Pastor [Shepherd] descubre cuál módulos únicos pertenecen a diferentes equipos y crea automáticamente Relaciones públicas para cada uno de estos módulos. Cuando Apareció artificial inteligencia, pudimos agregar Shepherd a la base de datos IA, donde, digamos, si yo Quiero arreglarlo compartir contexto en todos los servicios, para que El rastreo funcionó mejor. Puedo crear un conjunto consejos y habilidades, que el agente podrá entonces referirse a cada módulo y arreglar todo rápidamente problemas en todos servicio. Entonces, esto es tipo de gran escala cambios, independientemente de ya sea que lo desee cambios deterministas, o cambios de agente en dentro de los módulos. Él nos permitió para muchos años para llevar a cabo muchas migraciones y cada uno de ellos nosotros Lo llamamos campaña. Y si miras sobre la transición de Junit 4 a JUnit 5, entonces verá YAML- archivo de política, un montón de PR creadas para cada módulo y propietario de la campaña puede rastrear su estatus y revíselos. Entonces Esto realmente simplifica gestión de tales migraciones. Espadín Hace meses tomamos la misma plataforma y añadió otro función. Nosotros también queremos simplificar proceso, queremos mejora constante base de código, no realizar una única migración. Suponer, Quiero mantenimiento del código.

</details>

**Host**: 是的，日常维护保养代码。

<details>
<summary>Original English</summary>

**Host**: Sí, servicio código.

</details>

**Guest**: 没错，于是我们打造了 Fox（狐狸）。从本质上讲，我们希望构建出一套能够“自我改良”的代码库。既然我们内部已经沉淀出了一整套开箱即用的 Agent 技能库，Uber 旗下的任何微服务团队都可以接入该系统，按需为自己的服务订阅注册不同的技能项。

例如他们可以勾选：“我想接入代码坏味道清理（Code Cleanup）”、“我想做运行时性能分析与优化”，或者是“我想自动检测并修复泛滥冗余的无用日志”。系统提供了一整套丰富的技能货架供团队按需接入启用。

<details>
<summary>Original English</summary>

**Guest**: Entonces, nosotros Lo llamamos Zorro [Fox]. En En esencia, queremos crear bases de código, Qué superación personal. Dado que ya tenemos todo un conjunto de agentes habilidades, de hecho, ser -¿Qué servicio de Uber puede ofrecer? ven aquí y regístrese servicio para diferentes habilidades. Ellos pueden decir: quiero esto limpieza de código. Quiero ¿Es limpieza de código, o análisis productividad, o corrección troncos excesivos. HAY un conjunto completo de estos habilidades que usted Puedes conectarte.

</details>

**Host**: 噢，这个设计太精妙了！

<details>
<summary>Original English</summary>

**Host**: Oh, eso es inteligente.

</details>

**Guest**: Fox 的运行机制是：每周一（更确切地说是在每周日夜间，因为此时 CI 持续集成集群的负载最低），它会基于团队订阅的清理与优化技能，针对这些微服务自动生成优化 PR。

比如它会自主巡检：“这里有几处遗留废弃代码，我能帮忙精简重构吗？”、“这里的热点路径我能提升一下执行效率吗？”或者“这里是不是有大量刷屏的噪音日志，我能统一治理一下吗？”

这是一种全自动化的代码库常态优化机制，我们只是向你展示了……

<details>
<summary>Original English</summary>

**Guest**: Y lo que hace Fox es todos los lunes y más precisamente todos los domingos, cuando no tenemos eso carga pesada en CI, genera nueva PR para esto servicio, usando esto limpieza de código. Por ejemplo: oh, ¿puedo? Limpio algo de código. ¿ ¿Puedo mejorar? el desempeño de este ¿ ¿Puedo arreglarlo? ¿Hay algún tronco ruidoso? Entonces este es un tipo de automatizado mejora del código bases, y nosotros solo te mostramos cómo puedes puede...

</details>

**Host**: 我非常喜欢这个设计！因为我听说很多外部团队也在尝试类似的玩法：他们搭建一个基于 Claude Code 或者 Codex 的 AI 自动化循环任务，下发指令说“去帮我巡查代码库中可以改进的地方”，然后配置成每晚或每周定时跑一次。但听你这么一讲，你们这套体系远比单纯的任务脚本要成熟得多、经过了深度的全流程工程优化。

而且我尤其欣赏“代码库自主注册”的机制，因为在 Uber 内部，每一段代码、每一个微服务背后都有明确的负责人——要么是具体的工程师，要么是对应的业务团队，对吧？

<details>
<summary>Original English</summary>

**Host**: Yo, yo, yo esto Me gusta porque escuché que la gente hace esto cosa: están configurando IA- un bucle como Cloud Code o Códice, diciendo: "buscar formas de mejorar mi código base", y Hazlo funcionar todas las noches o una vez por semana. Pero suena como Es mucho más que eso, no. Lo sé, optimizado. Y Me gusta eso puede registrarse tu base de código, porque cada base de código tiene un dueño— ingeniero o equipo ¿En Uber, verdad?

</details>

**Guest**: 没错，正是如此。正因为我们目前正处于快速演化和推广扩量期，现阶段依然采用团队自主自愿接入的机制。而随着我们对各项技能的成熟度和效果持续打磨提升，未来我们会将其中一部分核心治理技能转为“默认强制开启，但保留明确退出（Opt-out）选项”的推进模式。

但我必须指出，只要你的微服务接入了这套机制，每周一早晨你都会收到若干份意图明确、真正言之有物的自动合并请求（PR）。这完全是一个由 AI Agent 驱动闭环的自主演进循环，根本无需人类工程师周复一周地手动进行机械繁琐的局部修补。

从深层次意义来说，我们从工程师日常工作中剥离消除的机械化繁文缛节越多，他们就能把更多宝贵的时间集中投向真正驱动业务的核心功能研发上。

所以我们内部始终在思考：如何为工程师铲除更多重复机械的体力活？如何将这些琐碎事务全部沉淀进自动化系统中？我们经常深入研究各类与技术维护相关的合并请求（PR），并不断自我审视：我们是否应该针对这类痛点开发一个全新的 Agent 技能？或者是否应该优化现存的某项技能，从而让这一整类重复提单改造，都能全面并入这个自动化的闭环管理周期中？

<details>
<summary>Original English</summary>

**Guest**: Sí, así es. Y tú ¿Ves eso porque...? somos rápidos estamos escalando, todos lo estamos haciendo seguimos en etapa voluntaria conexión. Cuando nosotros vamos a mejorar algunas cosas habilidades, nosotros tradzascamos parte de ellos en fase obligatorio usar con la posibilidad de rechazo. Pero, quiero decir, en cuanto te conectes habilidades de servicio, cada semana estás en un determinado ya entiendes el significado creó una solicitud para fusión (PR). Es como agente gestionado ciclo. Así que no lo hagas necesito esto constantemente mejorar manualmente. EN en cierto sentido, que más rutinario nosotros eliminar, cuanto más Los ingenieros de tiempo pueden gastar en real seguir trabajando funcional. Así que nosotros constantemente pensamos: cómo eliminar más rutinas en ingenieros y cómo automatizar todas estas cosas. Nosotros constantemente miramos todo tipo solicitudes de fusión que relacionarse con técnico servicio. O necesitamos crear uno nuevo ¿habilidad? ¿Es necesario? Necesitamos mejorar esto habilidad para que esta clase Las solicitudes podrían ser agregar a esto automatizado ¿Ciclo controlado?

</details>

### 众包与自动化诊断体系：Wisdom

**Host**: 太棒了，我非常认可。最后，我还听说过一个叫 Wisdom 的系统，Wisdom 到底是做什么的呢？

<details>
<summary>Original English</summary>

**Host**: Esto es genial. A mí Me gusta. Y Finalmente, oí hablar de la sabiduría [Wisdom]. ¿Qué es la sabiduría?

</details>

**Guest**: 噢，是的！我们在内部广泛使用 Wisdom。在 Uber，我们全体员工日常都在主动“吃自己的狗粮”（Dogfooding），亲自测试我们自己的各类产品。因此，当你使用我们的乘客端 App 或司机端 App 遇到任何故障或异常时，都可以直接在 App 内一键提交 Bug 反馈。

如今，我们内置了各种 AI 自动化路由工具，能够根据上报提交的丰富数据，自动将该工单精准直派给负责相应模块的具体工程团队。

而且，因为员工都是通过专用的员工 Beta 版客户端上报问题，我们在上报时能够自动附带收集极为详尽的上下文日志与底层遥测数据（Telemetry）。这为负责修复该特性的业务团队提供了极大的便利。

举个例子，在这类场景中有一个非常强大的内部特权功能：如果你想测试某项功能在其他国家或地区的表现，你可以直接在设备上任意模拟切换地理位置。因此，一旦有人上报了某个定位或跨国相关的疑难 Bug，摆在工程师面前的首要核心难题，往往是如何精确复现它——尽管在以往……

<details>
<summary>Original English</summary>

**Guest**: Oh sí. Entonces, nosotros usamos la Sabiduría [Wisdom], porque todos nuestros Los empleados se están haciendo pruebas nuestros productos por sí solos. Entonces si tú utilice nuestro solicitud para pasajeros o conductores y ver alguno error, puedes para denunciarlo directamente desde la aplicación. Ahora tenemos todo tipo de herramientas de AI que automáticamente directo mensaje el equipo adecuado en basado en estos datos. Y cuando usted informa sobre el error, porque Esto está sucediendo a través de aplicaciones beta para los empleados, podemos recolectar un montón de troncos y telemetría, que es significativa facilita al equipo que es responsable de esto función, su corrección. Por ejemplo, en este este caso es interno función: esencialmente, si quieres para probar cualquier ¿Qué función en otro país, puedes cambiar geolocalización en el dispositivo. Entonces si alguien informó este problema, en primer lugar La pregunta es cómo reproducir, aunque solía

</details>

<!-- chunk 11/12 -->

### 调试助手与代码编写 Agent Minion 的联动闭环

**Uber 工程师**：这过去一直是个极其庞大且棘手的问题。但现在不同了，我们能够精确知晓用户所经历的屏幕交互序列，因为这一切都清晰完整地记录在日志中。我们因此能够为工程师提供极其详尽的重现步骤、预期的系统行为以及实际观测到的异常情况。这样一来，工程师便能迅速切入问题核心，直达故障发生的症结所在。

不仅如此，我们在应用程序中收集到的所有遥测数据和全量日志，你现在都可以在一个统一的地方集中查看。例如产品分析埋点数据、底层网络请求记录、各种功能特性开关（feature flags）的状态等等。这些信息为排查问题提供了海量且极为丰富的上下文背景。

正是在拥有了如此全面的上下文信息的基础上，我们构建并部署了一个受管的 AI Agent，命名为“调试助手”（Debugging Assistance）。这位调试助手会全方位分析上述所有遥测与日志上下文，并结合相关代码库进行深度比对推理，竭力精准推断出 Bug 的真正根本原因（root cause），并梳理出一套影响该故障的完整事件时间线。

当我确认它所找出的真正根本原因无误后，就可以直接将这一结论无缝递交给 Minion——也就是我们之前深入讨论过的那个专门用于编写代码的 Agent。

<details>
<summary>Original English</summary>

**Uber Engineer**: ser un problema enorme . Entonces, ahora nosotros conocemos la secuencia pantallas que pasaron usuario, porque tenemos está en los registros y podemos proporcionar ingenieros pasos de reproducción, comportamiento esperado y de hecho observado. Entonces podemos rápidamente para llegar al punto problemas. Y todo telemetría que nosotros recopilado de la aplicación, todos los registros, puedes ver en uno lugar. Por ejemplo, análisis, red solicitudes, varias indicadores de función. Él también proporciona mucho contexto. Y ahora, tener todo esto contexto, creamos agente gestionado llamado Asistencia de depuración, ¿Quién analiza todo esto? junto con el código base y lo intenta determinar la causa raíz, así como cronología de los acontecimientos, Eso la influyó. Cuando entiendo que esto verdadera primera causa, yo Puedo pasárselo a Minion, del que hablamos . Sí, el agente de escribir código.

</details>

**Uber 工程师**：这正是定位出的根本原因，逻辑看起来完全正确。那么，为什么不直接基于此创建一个代码合并请求（Pull Request / PR）呢？Minion 会直接获取我们目前所拥有的全部上下文信息与分析结论。它会自动编写修复代码并创建 PR，并将该 PR 自动关联到 Jira 上的对应任务工单中。

在 Jira 工单内部，同样也会完整记录下本次故障的根本原因分析报告。这样一来，团队中任何参与该任务的开发人员，都能一目了然地看到这份根本原因分析。

如果后续有工程师在评论区中修正或更新了根本原因认知，亦或是重新手动创建了一个新的 PR——所有这些反馈与变更数据都会被我们捕获并沉淀下来。这使我们能够清晰地理解：我们该如何进一步优化和提升调试助手的定位能力？我们又该如何改进 Minion 的代码生成质量？当前究竟是因为调试助手给出的根本原因分析有偏差，还是因为 Minion 基于分析生成的 PR 存在错误？借助这些闭环数据，我们能够对这两个系统进行持续的双向迭代与优化。

<details>
<summary>Original English</summary>

**Uber Engineer**: Esta es la causa principal Parece correcto. ¿Por qué no lo haces? ¿Crear una solicitud de extracción para esto? Minion se llevará todo esto el contexto que tenemos . Él creará relaciones públicas. Él agregaré esta PR a tareas en Jira. EN Las tareas de Jira también contiene análisis causas fundamentales. Entonces todos los que trabajan en Esto, lo sabe el análisis causas fundamentales. Si alguien actualizó la causa raíz en comentarios o creó un nuevo PR—todo estos son los datos que podemos entender, Cómo mejorar la asistencia del depurador . ¿Cómo podemos mejorar Minion? ¿ Recibimos análisis incorrecto causas raíz o Relaciones públicas erróneas en base de este análisis. Siempre podemos mejorar ambos.

</details>

### 简化 Bug 复现：员工反馈与流量回放机制

**访谈者**：那么，我这么理解对吗：你们现在记录和复现各类 Bug 的过程，比起以往变得容易得多了，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: Entonces, ¿tengo razón? Entiendo que puedes mucho más fácil registro y reproducir errores , ¿bien?

</details>

**Uber 工程师**：是的，我们还进一步新增了一项非常强大的能力。因为对于员工内部上报的所有 Bug，我们都保留了完整详尽的运行日志。我可以随手拿起你的测试设备，然后让系统去模拟和回放当时那位上报 Bug 的员工在手机上所经历的一切真实感受。

具体来说，当我输入该 Bug 的唯一标识符（UID）时，系统基本上能够在测试设备上完全重现当时上报者遇到问题时所接收到的所有真实网络响应。这样一来，我便能够在自己的设备上、在应用中切身体验到一模一样的故障表现。

我能直接看到：这个问题是否确实存在？修复之后是否真正解决了问题？并亲眼观察修复后的实际运行效果。这使得整个 Bug 复现与验证的过程变得异常轻松和高效。

<details>
<summary>Original English</summary>

**Uber Engineer**: Sí, también añadimos posibilidad, porque para todos los errores, sobre quienes informan empleados, tenemos todos los registros. Puedo tomar tu prueba dispositivo y preguntar imitarlo es ¿Qué sintió? empleado. Entonces, cuando yo Introduzco el UID del error, nosotros esencialmente podemos dar la misma red las respuestas que estaban en la persona que presentó el informe, para que yo también pueda sentir el mismo problema en aplicación en su dispositivos. Sí, lo sé. ¿Se solucionó esto? y veo el resultado que hace que el proceso reproducción en efecto fácil.

</details>

### 应对海量机会与系统工程瓶颈

**访谈者**：我非常喜欢这种思路。能够完整捕捉并输入当时正在发生的真实运行情况，这真的是极其关键且重要的一环。即使在 Web 开发领域，要把这套机制做好也绝非易事，你必须自己研发专门的配套工具链；而在移动端应用中，你们能把这套体系真正构建出来并落地，真的非常出色。这种机制在提高可复现性以及探寻真实的根本原因方面，提供了巨大的助力。

那么，你们构建了所有这些系统，尤其是在过去这一年里，似乎涌现出了大量全新的系统来支撑各项工作——例如保障代码质量的系统、Agent 的自我评估与自我监管体系等等。在你看来，Uber 内部软件工程师与程序员的工作模式正在发生怎样的深刻变革？借助所有这些层出不穷的新工具，你自身又在学习和领悟些什么？感觉你自己也在这个过程中不断进化。

<details>
<summary>Original English</summary>

**Interviewer**: Me gusta mucho. como la entrada de lo que está sucediendo , porque esto es, bueno, esto Realmente importante, ¿verdad? Incluso en la web es hacer lo suficiente No es fácil. Tú necesidad de crear herramientas propias, si quieres crear un sitio web, pero Es genial que hagas esto hecho. Sí, creo que es muy ayuda en reproducibilidad y buscar lo real causas fundamentales. Entonces, creaste todo estos sistemas, especialmente durante el último año, parece que es mucho nuevos sistemas que hazlo trabajo, por ejemplo, calidad del soporte código, agentes mismos Se controlan a sí mismos. Como, en tu opinión, El trabajo está cambiando ingenieros- programadores en Uber y ¿Qué estás estudiando? gracias a todo esto ¿Nuevas herramientas? Parece que tú mismo Estás aprendiendo.

</details>

**Uber 工程师**：你知道的，在某种程度上，如果你身处由 Agent 驱动的 AI 新时代，你所做的就是不断地去寻找系统中的下一个瓶颈，并全力消除它；思考如何通过结合前沿 AI 技术与坚实的系统工程能力，来一步步打破这些瓶颈与限制。

归根结底，我们的终极目标是：最大限度地提升我们能够为旗下所有产品发布的优质功能数量。而要达成这一点，就必须对整个软件开发的完整生命周期进行深度剖析。我们必须重新思考：面对这个全新的 AI 世界，我们应该如何重新配置这一生命周期？我们究竟需要打造哪些配套工具？

我认为这将是一段漫长而持续的探索旅程。现在业界有很多人都在讨论所谓“机会过剩”（Opportunity Surplus）的概念，即大家普遍感受到，即便在当下，最新前沿大模型已经展现出了极多的潜在应用场景与可能性，但我们现有的编排调度框架、工程工具链或执行运行环境，却远远不足以充分释放和利用好这些大模型的能力。

我深切地感受到，我们在工程基建和工具化上突破得越多、投入得越深，我们就越能把这些大模型的潜力彻底挖掘出来。我们所能交付和发布的高价值功能也就越多，进而能够释放出更为巨大的生产力。我们目前正在努力对所有这些环节进行精准度量，不断深思熟虑：为了让工程师和各类 AI Agent 能够更加高效顺畅地协同工作，我们下一步还需要打下哪些最坚实的基础设施底座？

<details>
<summary>Original English</summary>

**Uber Engineer**: Ya sabes, hasta cierto punto, si estás en el mundo agente IA, tú constantemente intentando encuentra el siguiente cuello de botella y eliminarlo, averiguar cómo reducirlo limitación, utilizando como IA, y sistémico ingeniería. Para, En definitiva, nuestro objetivo es... maximizar número de funciones, que podemos liberación para todos nuestros productos y esto nos requiere análisis de todo ciclo vital. Como necesitamos reconfigurar ¿Esto es para el nuevo mundo? Y ¿Qué herramientas necesitamos? ¿Necesitas crear? Y Creo que será Es un largo camino, ¿verdad? ¿Sí? Y mucho están hablando de el concepto de "excedente" oportunidades", donde se siente como incluso ahora hay tantas cosas para que podría ser usar los últimos modelos, pero no tenemos suficiente oportunidades para orquestaciones, herramientas o entornos para bien usa estos modelos. siento que cuanto más superamos esto cuanto más trabajamos, más podemos revelarlo. Cuantas más funciones tengamos podemos liberar, así que mayor productividad podemos revelar y estamos intentando medir todo esto, pensando constantemente en ¿Cuáles son los siguientes? Necesitamos lo básico acostarse de manera que hacer el trabajo más fácil ingenieros y agentes.

</details>

### 重新定义研发效能度量：从代码行数到端到端交付价值

**访谈者**：你刚才提到了“生产力”（研发效能）。关于工程团队的生产力，你是怎么思考的？回想起我还在 Uber 的时候——那是 2020 年左右——我们做工程管理者的，通常会关注某些量化指标。虽然那些指标并不是最核心的，但我们确实会看一些数据，比如某个工程师提交的代码变更（Diffs）数量，以此排查是否有人连续两周没有任何代码贡献，那时候就会想：“嗯？这家伙最近在干什么？”或者如果有人完成了大量的代码审查（Code Review），这确实也是我们当时非常重视和鼓励的行为。

但现在听起来，单纯看代码产出或代码工件本身的多少，其重要性似乎大不如前了。那么在你看来，当下的 Uber 或者在你的团队里，究竟怎样才算是一名高效、高产出的工程师？

<details>
<summary>Original English</summary>

**Interviewer**: Mencionaste sobre productividad. Qué vas a pensamiento en ingeniería ¿productividad? Atrás que cuando estaba en Uber, fue, de nuevo, a 2020, nosotros, los gerentes , miró ciertos indicadores. No lo fue. lo principal, pero nosotros miró esas cosas , a medida que aumenta el número de cambios ( diferencias) para un ingeniero, solo para ver, ¿Había alguien sin? contribución dentro de 2 semanas, y era como: " "Hmm, ¿qué haces aquí?" O si alguien lo hiciera muchos controles código, esto es realmente lo que lo que queríamos notar . Pero suena así, Me gusta mucho esto. Bueno, ya sabes, un día libre. código, artefactos de código— potencialmente menos importante. Sabes, quién es ingeniero productivo en tu opinión ahora en Uber o en tu ¿equipo?

</details>

**Uber 工程师**：是的，我认为在 AI 时代到来之前，我们度量效能的方式，正如你所熟知的那样，主要依赖于一套非常标准化的指标，比如代码的吞吐量（Throughput）等等，这些都是较为初级和表层的指标。与此同时，我们每隔几个月还会面向内部开发者做一次深入的体验问卷调研，查看开发者净推荐值（NPS），跟踪各类主观与客观指标。此外，我们还会严密监控代码质量参数，比如每个开发者引入的生产事故数量、单元测试代码覆盖率等等，通过这一整套度量衡来评估。

而到了当下，随着 AI 的深度介入与全面应用，我们拥有了一整套全新的可能性与工具集，使我们能够将关于研发效能的探讨推向更深层次。

现在我们在公司内部讨论效能时，已经绝不仅仅停留在单纯的研发编码速度或者功能交付速度上了。例如，我们会重点探究：通过引入 AI 所带来的所有这些额外生产力提升，究竟有多少比例被真正转化为了解锁和交付全新的业务特性？我们又该如何革新自身的组织流程与协作架构，以切实缩短一个功能从立项到上线的平均周期时间（Cycle Time）？

因为你完全可以在短时间内堆出 100 天的工作量，但如果这些工作并没有转化为真正可用的功能特性，那么它就未必能给最终用户带来实际的业务价值，对吧？

举例来说，我们所做的一项关键实践，就是对我们所有的 PR 进行了全方位的细粒度标签化分类：不仅按实现难度与复杂度进行分级，还明确标注出该 PR 究竟是用于构建全新功能、修复线上 Bug、日常系统维护升级、编写测试用例，还是补充技术文档。令人欣慰的是，至少就目前的数据来看，我们用于交付新特性的 PR 占比正在显著上升，而单纯用于系统维护杂务的 PR 占比则在逐步下降。这无疑给了我们一个非常强烈的积极信号，表明我们的工程方向是完全正确的，并且我们也确实观察到整体交付的功能数量在稳步增长。

此外，我们在产品需求文档（PRD）和工程技术方案设计文档（RFC / Design Doc）与具体任务工单的关联绑定上投入了大量精力。过去，要精确、可靠地度量所有功能特性端到端的全生命周期时间是相当困难的。而现在，我们利用 AI 来对这些文档与任务进行自动化聚类、关联对齐，并自动补全缺失的映射关系。借助于此，我们能够极其精准、可靠地测算出过去 2 到 3 年间，每个半年周期内针对不同复杂度功能特性的 P50 交付发布周期。

在此基础上，我们便能展开极为深刻的归因分析：当前的交付瓶颈究竟是卡在 PRD 需求评审阶段、上线发布阶段，还是具体的技术实现阶段？在那一阶段究竟发生了什么阻碍？我们又需要在哪些核心环节进行工程投资与流程重构，以进一步提升我们在每个半年度能够成功交付的产品功能总量？

<details>
<summary>Original English</summary>

**Uber Engineer**: Sí, creo que antes de la era Medimos la AI, bien ya sabes, los estándar cosas como un pase capacidad de código y demás otro. Y esto más simple indicadores. Y nosotros también cada pocos meses Estamos realizando una encuesta. en cuanto a la experiencia desarrolladores. Nosotros mirando el NPS, bueno ya sabes, con ganas de todo tipo indicadores. Nosotros miramos parámetros de calidad código: cantidad incidentes en desarrollador, cobertura código y todo esto métrica. Mmm, creo que sí. ¿Y ahora, cuándo? La IA ha aparecido, podemos usa uno nuevo un conjunto de posibilidades, para hacer esto debate más profundo. Para ahora estamos adentro No hablamos con empresas. definitivamente simple sobre la velocidad desarrollos y sobre velocidad implementación de funciones . Por ejemplo, cuál parte de todo esto adicional La productividad va para desbloquear nuevas características. ¿Y nosotros cómo estamos? podemos cambiar nuestra organizativo procesos para reducir tiempo medio Implementación de la función. Porque puedes crear 100 días, pero si no lo es días funcionales, entonces tal vez no lo sea necesariamente aumenta valor para usuarios, ¿verdad? Por ejemplo, uno de de las cosas que hicimos, —esto es etiquetar a todos nuestras PR para diferentes categorías: por nivel de dificultad, o Esta es una solicitud de extracción para una nueva función, corrección de errores, servicio, pruebas, documentación, y nosotros Afortunadamente, al menos ahora veo que nuestro Porcentaje de PR para nuevos las funciones aumentan y servicio- caídas. Entonces esto nos da una buena señal de que nosotros mudándose la dirección correcta . Bien, ya vemos que funciones también aumenta. Nosotros invertimos mucho porque documento de diseño producto y proyecto de ingeniería a un específico tarea. Por lo tanto se convierte en un poco más difícil medir de forma fiable tiempo de ciclo de extremo a extremo para todas las funciones. Entonces, ahora nosotros Utilizamos IA para automático agrupamiento de estos cosas y designaciones elementos faltantes, para que podamos confiar determinar velocidad Lanzamiento de características P50 para diferentes complejidad de las funciones por cada semestre en los últimos 2-3 años. Y luego nosotros podemos analizar: ¿hay? etapa de cuello de botella PRD, fase de lanzamiento o ¿Etapa de implementación? Qué Sucede allí y en ¿Qué necesitamos? invertir para acelerar el número funciones que nosotros podemos liberar para medio año.

</details>

### 工程师角色的心智模型转变与实践重塑

**访谈者**：那么，与 AI 技术和这些现代化工具诞生之前相比，你个人对于“软件开发”这一行为的心智模型（Mental Model）发生了怎样的转变？这就是全部的变化吗？你的日常工作本质上依然如故，还是说一切都已经彻底改变了？

<details>
<summary>Original English</summary>

**Interviewer**: ¿Y cómo cambia el tuyo? modelo mental desarrollo de software software en comparación con el tiempo anterior el surgimiento de la IA y estos ¿herramientas? Eso es todo. ¿Sigues teniendo el mismo trabajo? O ¿Han cambiado las cosas?

</details>

**Uber 工程师**：我想说的是，至少在我过往的全部工程师职业生涯中，我对日常工作的思考方式与实践范式，还从未经历过如此翻天覆地的剧烈变革。

举个例子，在 Uber，我们一直强调这样一种工程师文化：Uber 的所有工程师都必须深入一线，投身于 Hands-on（亲力亲为的技术实操）工作。即便是在 Uber 级别最高、声望最显赫的顶尖杰出工程师（Distinguished Engineers），也必须保持 Hands-on，亲自编写代码并创建 PR（代码合并请求）。

在过去，我一直自认为自己是一个极具实干精神的一线实操工程师。然而随着这几年的演进，我对“Hands-on（实操）”这一定义的理解，已经被彻底重塑了。甚至就我个人而言，我现在每年亲自创建并提交的 PR 数量，都比前几年要显著多得多。

<details>
<summary>Original English</summary>

**Uber Engineer**: Me refiero a eso al menos para todos los míos Experiencia laboral ingeniero, mi enfoque nunca trabajar experimentó tales cambios. Por ejemplo, decimos: que todos los ingenieros de Uber están involucrados en trabajo práctico. Incluso los más destacados ingenieros en Uber están involucrados en trabajo práctico. Crean relaciones públicas ( solicitudes de fusión de código ). Solía ​​ pensar que yo un ingeniero en ejercicio, pero mi definición trabajo práctico con durante años completamente cambió. Yo incluso Yo personalmente sí significativamente más PR que Lo hizo el año

</details>

<!-- chunk 12/12 -->

### 上下文工程与多任务处理能力

**Speaker A**: 在过去，把所有这些事情整合在一起做会容易得多，对吧？而且我能探索的想法数量也比过去多得多。但作为一名工程师的工作……从某种意义上说，这正是你如何为智能体（Agent）构建恰当上下文的方式，以便让它们能够稳定、可靠地输出结果。在某些方面，你需要真正成长为上下文工程（Contextual Engineering）领域的专家。我过去总是带着某种上下文去完成特定的任务，所以现在我常常在思考：“好吧，如果我想把这部分工作交由智能体来做，我该如何调整并提供正确的上下文，让它能够胜任这项工作？”因此，除了构建恰当的上下文之外，你还必须变得非常精通于如何为智能体提供精准的规范说明与约束条件。

<details>
<summary>Original English</summary>

**Speaker A**: Es más fácil hacer todo esto todo junto, ¿verdad? Y puedo explorar un número mayor ideas que yo podría hacer en el pasado. Pero el trabajo de un ingeniero... Esto es, en cierto sentido, la forma en que creas contexto correcto para que los agentes emitió un confiable resultado. En algunos necesitas para convertirse verdaderamente experto en contextual ingeniería. Yo solía trabajó con cierta contexto para finalización de la tarea, Así que siempre pienso: "De acuerdo, si quiero traducir parte este trabajo para un agente ajustar correcto contexto para que sea podría hacer esto ¿trabajar? Entonces tú debería volverse muy experto en cómo proporcionar la correcta especificaciones y restricciones para agentes, excepto creación correcto contexto.

</details>

**Speaker A**: 此外，多任务并发处理能力变得至关重要。早些时候，一个人需要花费大量时间，至少要全力以赴地高度聚焦在单一一件事上。但现在，你处于不断在诸多事项之间切换的状态。因此，你必须学会在所有工作会话中统筹全局，弄清楚如何界定工作体量、跟踪任务执行性能，以及如何极速验证各项输出结果。因为如果你无法审查智能体产出的工作并敏锐察觉到其中的任何“代码坏味道（Code Smells）”，事情就会变得异常艰难；否则你最终就会把某种劣质产物推向生产环境并不得不返工，对吧？因此，上下文工程能力、多任务切换与并发处理能力，以及快速审视和验证结果的能力，在当下变得愈发举足轻重，因为你能够以远超以往的规模去高度并行化地开展工作。

<details>
<summary>Original English</summary>

**Speaker A**: Además, multitarea se volvió realmente importante. Más temprano, tanto tiempo para al menos máximo centrado en esto. Pero ahora estás constantemente cambiar entre muchas cosas. Así como tú, tienes que aprender todas las sesiones, averiguar cómo determinar el volumen trabajo, como síguela rendimiento y cómo muy comprobar rápidamente resultados. Porque si no eres capaz revisar el trabajo y notar cualquier "olores de código" de agente, entonces es difícil; luego envías a algún tipo de producción Reciclaje, ¿verdad? Así que contextual ingeniería, capacidad a la multitarea, capacidad ver y verificar los resultados se convirtieron mucho más importante ahora, porque puedes paralelizar el trabajo mucho más que más temprano.

</details>

### 从编写代码到构建“元级别”验证系统

**Speaker B**: 我注意到的一件事是，也许这是一种全新的视角：过去我们开发软件，思考的是“我该如何编写这段软件？我自己又该如何验证它？”而现在你所面对的核心问题，往往变成了：“我该如何配置智能体，让它既能自主创建软件，又能自主完成验证？”这几乎上升到了一个元级别（Meta-level）的维度。

<details>
<summary>Original English</summary>

**Speaker B**: Una cosa que noto es, tal vez nuevo notamos: solíamos software desarrollado software, Pensando: ¿Qué hay de mí? crear software y cómo lo hago ¿Lo revisaste? En cambio ahora la pregunta que estás haciendo dicho, a menudo suena Sí: ¿y yo? configurar el agente, para que él pudiera hacerlo crear y ¿verificar? Así que esto es casi como un metanivel.

</details>

**Speaker A**: 确实如此，现在的焦点更多落在了这里，对吧？我可以分享一个非常有趣的实际例子。我曾与我们客户支持团队的一些工程师共事。我们正在推行让 AI 智能体来处理我们部分客户支持政策的工作。这个业务流程最初是由人类客服代表按照特定的简报指引一步步操作的。基于这份操作指南，工程师需要梳理一整套步骤逻辑，构建出可供 AI 智能体遵循的策略规则。这时你就必须去思考：好吧，这里存在哪些动态变化的要素？我需要调用哪些 API 接口？如何获取这些数据？我需要提取并使用哪些字段属性？接下来，我需要配置系统、调整一系列参数设置，在正式上线前先执行人工评估，上线后再持续跟进评估。而在过去这几个月里，我们成功将所有这些繁琐的中间步骤都精简掉了。

<details>
<summary>Original English</summary>

**Speaker A**: Así es. Parece que es más sobre esto, ¿verdad? Sí, daré una interesante ejemplo. Yo trabajé con algunos ingenieros que trabajando en nuestro equipo de soporte clientes. Nosotros nos estamos dirigiendo hacia para que los agentes de IA procesamos algunos de nuestros políticas de apoyo clientes. Este proceso comenzó con el hecho de que en estás seguro sesión informativa, que seguidos por agentes humanos. Y sobre la base de esto informándote Revisar la pila pasos para crear una política que puede Sigue al agente de IA. Entonces debes pensar: Vale, aquí hay algunos elementos dinámicos. ¿Qué API necesito entonces? necesito llamar, ¿Cómo obtener estos datos? ¿Qué atributos tengo? es necesario usar ¿ Entonces necesito configurar el sistema, cambiar la pila configuraciones, entonces realizar estimaciones manuales antes del lanzamiento, un luego gastar evaluaciones continuas después del lanzamiento. Y y luego, por último unos meses, nosotros pudieron eliminar todo estos pasos.

</details>

**Speaker A**: 那么具体是怎么做到的呢？现在只需把所有上下文背景以及我希望采用的全部策略转换原则输入给系统，直接训练智能体去执行这一过程，就能生成高质量的 V0 版策略规则，这一切智能体都能自主搞定。如此一来，你就能将所有的系统配置、手动测试、寻找匹配的 API 与属性以便接入动态要素等一系列工作全自动化。以往这类工作往往需要耗费数周时间，而现在几天之内就能完成。因此，与其完全依赖手工评估，你不如思考如何利用以往积累的全部经验来构建合成评估（Synthetic Evals），从而极大地加速交付部署与敏捷验证的流程。实际上，这正是我们一直在探讨的核心所在，对吧？现在你不再仅仅是单纯地埋头完成某项具体工作，而是要思考如何构建出恰当的工具和机制，将整个工作流彻底自动化。当然，在各个验证阶段以及人工介入环节，我们依然需要设置严密的熔断与防护保障（Safeguards/Fusibles），但你的重心已经转变为设计一个自身具备这种闭环能力的系统，而不是在每一步都依赖大量的手工操作。

<details>
<summary>Original English</summary>

**Speaker A**: Vale, ¿cómo? ahora toma todo contexto y todo los principios que quiero para usar transformación política y enseñar agentes para hacer esto, para obtener calidad versión de la política V0, que puede crear agente. Entonces tú automatizar todo ajustes configuración, manual pruebas, búsqueda las API correctas y propiedades para que podamos podría conectarse a Esto es necesario elementos dinámicos. De nuevo, ¿qué? Solía tardar semanas, ahora para cualquier varios días. Entonces en lugar de manual evaluación, ¿cómo lo haces? puedes usar todos los anteriores experiencia para crear estimaciones sintéticas, acelerar proceso, despliegue ¿Y una comprobación rápida? En realidad, de eso se trata. Estamos hablando, ¿verdad? Así que ahora no lo eres solo haz esto funciona, pero ¿crees que cómo? crea los correctos herramientas y mecanismos para automatizar flujo de trabajo. Por supuesto, necesitamos fusibles adecuados etapas de verificación y persona, pero tú diseñar un sistema, ¿Quién es capaz de hacer esto? ella misma, en lugar de confiar en un montón de cosas hechas a mano en cada paso.

</details>

### 工具演进与个人 Agent 的应用

**Speaker B**: 是的，而且看来这当中有许多需要学习的东西，因为这些都是全新涌现的概念，你正在实际使用并在整个组织落地推广的过程中边做边学。我完全理解你所说的“需要更多培训、更多 PR 审查交流”的含义了。最后我还想请问，你平时最喜欢使用哪款工具？无论是数字工具还是非数字工具都可以，只要是对你很有帮助的东西就行。

<details>
<summary>Original English</summary>

**Speaker B**: Sí, y parece que tú Se aprende mucho, porque estos son nuevos conceptos que usted actualmente usando y aprender en el proceso calarse organizaciones. I Entiendo lo que tienes. ¿A qué te refieres con "más"? entrenamiento, más relaciones públicas ". Y finalmente, ¿Qué herramienta necesitas? como usar ¿mayoría? Esto puede ser digital o no digital herramienta, algo que que te resulte útil.

</details>

**Speaker A**: 在最近这些日子里，我彻底迷上了各种个人智能体助手（Personal Agents），比如 Instinct、Mewes、Grok 以及其他类似的 Bot。我正在尝试把它们全部体验一遍。它们在我的个人生活工作中帮我自动化掉了海量的日常重复性事务，在某种程度上，我只需要负责跟踪监督整个流程本身：为任务执行提供所需的一切完备上下文、获取输入数据，并在事后亲自检查和把关最终成果。这极大地帮助我将所有这些繁杂的个人手动工作实现了自动化。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, los últimos días en los que me enganché agentes personales, como Instinct, Mewes, Grok y otros bots similares. Estoy experimentando con todos. Ellos ayuda automatizar un montón trabajo rutinario en mi personal vida, y puedo, hasta cierto punto, simplemente para seguir eso el proceso en sí: para proporcionar todo contexto necesario para ejecución tarea, obtener datos de entrada y luego para comprobar personalmente y completo asunto. Esto es muy ayuda automatizar todo este manual personal trabajar.

</details>

### 回顾 Uber 基础设施演进：从微服务洪流到回放系统 Capri

**Speaker B**: 太棒了。非常感谢你向我们全面介绍了 Uber 内部所使用的各项工程工具。这真的极其精彩，尤其是因为我已经很久没有见过如此完整透彻的内部工具体系分享了。

<details>
<summary>Original English</summary>

**Speaker B**: Perfectamente. Finjo, mucho. Gracias por decírmelo. sobre todo lo interno herramientas que utilizado en Uber. Era extremadamente interesante, especialmente porque no lo hago no vio nada ya basta de esto largo.

</details>

**Speaker A**: 是的，非常感谢能给我们提供这样一个交流的机会。你知道的，我感觉我们目前其实仍然处在非常早期的探索阶段。我们还有大量的事情要做，很多系统需要去构建。我们感到无比荣幸能走在这条道路上，去打造正确的产品机制，亲眼见证软件工程交付方式的演变，并最终看到它如何为整个公司和我们的各项业务持续创造价值，助力解决各项关键任务。

<details>
<summary>Original English</summary>

**Speaker A**: Sí, gracias por eso. nos dio tal posibilidad. Ya sabes, yo Siento que todavía estamos en la etapa inicial. Todavía tenemos mucho más por hacer. necesito hacerlo, mucho construir. Y nosotros extremadamente feliz estar en este camino, crea los correctos cosas y ver cómo software provisión y cómo, Finalmente, revela valor para empresa y nuestra negocios, trabajando en necesario tareas. Espero que

</details>

**Speaker B**: 我也是同感。距离我离开 Uber 已经过去了整整 6 年，因此 Uday 向我展示的许多工具对我来说都是全新的。大约十年前，Uber 曾因为在只有 2000 名工程师的规模下就狂飙出大约 5000 个微服务而声名大噪。但自那时起，微服务开始逐步整合，如今微服务的数量已经比十年前有所精简，目前大约维持在 4500 到 5000 个之间，而且每个微服务的粒度和规模都合理得多了。

<details>
<summary>Original English</summary>

**Speaker B**: Igual que yo. Ya han pasado 6 años, desde que dejé Uber, tantos herramientas que Uday me lo mostró, eran nuevos en a mí. Diez años Por eso Uber se hizo famoso al tener alrededor de 5.000 servicios para 2000 ingenieros. Pero desde entonces consolidar servicios en más hoy Los microservicios se convirtieron en menos de diez hace años que. Hoy su número es aproximadamente de 4500 a 5000. Aunque estos tener mucho mejor tamaño.

</details>

**Speaker B**: 其中一个让我印象尤为深刻的系统是 Capri——这是一款用于流量与事件录制及回放（Capture and Replay）的软件平台。在 2016 年到 2020 年期间，Uber 内部曾有两款分别名为 Deputy 和 Cerebrus 的工具，它们虽然也能执行部分录制回放功能，但非常难用，想要初始化并跑通流量捕获与回放基准库极其繁琐困难。自从有了 Capri，会话记录与流量回放变得容易太多了，这真是项了不起的成就。它不仅在故障排查与 Bug 复现方面大放异彩，也非常适用于验证针对特定 Bug 的修复方案是否真正生效。在像 Uber 这样跑着四五千个庞大微服务集群的环境中，构建出像 Capri 这样的全链路回放系统，其技术挑战是极其艰巨的。

<details>
<summary>Original English</summary>

**Speaker B**: Uno programa que yo —Esto es Capri, software provisión para captura y repetición de los eventos. Por Uber, entre 2016 y 2020 años, tuvimos dos herramientas para llamados Deputy y Cerebrus, quién podría actuar algunos pero ellos eran No es tan fácil para usar, y fue muy difícil de empezar captura y reproducción de bases. Desde Capri registro y sesiones de repetición se volvió mucho Es más fácil y es genial. trabaja para reproducción de errores, y también para comprobar que la corrección algún error Funcionó. Crear tal sistemas como Capri son particularmente difícil, cuando lo tengas en marcha alrededor de 4500 o 5000 servicios como Uber.

</details>

**Speaker B**: 另一个十分有意思的观察是代码审查（Code Review）流程的演进走向。在许多地方，传统的纯人工代码评审正在逐步弱化。但纵观 Uber 通过 Code Inbox 等工具构建的代码审查工具链，每个 PR 的把控依然取决于工程师本人的专业判断，看其是否合格；与此同时，Uber 引入了大量的自动化审查，充分利用各类辅助信号与智能体能力。最终，关于是否还需要人类逐行细看代码的争论或许会继续，但整体上我得到的强烈感受是：Uber 在过去数年里对开发者生产力工程（Developer Productivity Engineering）的大量投入，如今在 AI 浪潮来临时终于迎来了丰厚的回报。例如早在 2017 年搭建的各项基础设施，如今几乎都能直接无缝复用到 Minions 等各类智能体平台上；同理，成熟完善的软件工具链和安全沙箱环境，也让智能体能够直接调用并安全通信。回首来看，这一切令人赞叹不已。想要深入了解 Uber 卓越工程文化与技术沉淀的观众，这期内容可以说是当下的绝佳范例。如果你喜欢本期视频，请务必分享给你的朋友们。非常感谢大家的收看，我们下期再见！

<details>
<summary>Original English</summary>

**Speaker B**: Todavía Una cosa interesante es adónde va proceso de verificación código. Él gradualmente está muriendo en todas partes. Pero, mirando a conjunto de herramientas, que Uber fue creado para comprobaciones de código por usando Code Inbox, Cada PR es igual cómo el ingeniero La persona decide qué es. adecuado. Sin embargo, Uber automatizado inspecciones. Muchos de se utilizan señales sobre agentes. Eventualmente, necesidad code in general. Finalmente, Lo logré. la impresión de que productividad desarrolladores durante dar fruto AI. For example, back in 2017 reutilizar casi todos los míos infraestructura para Minions. Lo mismo software seguro los agentes pueden úsalos comunicación. Atrás uno tiene la impresión Uber. Necesariamente Encuentra más cultura de la ingeniería Uber. Uber is probably resaltado hoy. Si usted me gustó este Cuéntame sobre él. amigos. Gracias y nos vemos en

</details>