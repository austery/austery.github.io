---
author: AI Engineer
date: '2026-10-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=toq-jyGLZDk
speaker: AI Engineer
tags:
  - multi-agent-systems
  - distributed-systems
  - agent-communication
  - runtime-binding
  - observability
title: 从单体提示到分布式协作：解构多智能体系统的通信通信瓶颈与工程演进
summary: 演讲探讨了多智能体系统（Multi-Agent Systems）的发展路径与核心工程痛点。当前开发者普遍通过循环调用多个模型会话或依靠手写黏合代码来绕过大模型上下文退化与确认偏差，但现有的即时通讯工具、无状态协议（如 MCP、A2A）在状态保持、双向拓扑、运行期绑定与分布式可观测性上存在本质局限。Bend 提出了一套运行时级智能体协作网络协议，通过注册中心、事件房间与双边权限模型实现跨环境的自主交互与人在回路协同。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Google
products_models:
  - Claude
  - LangGraph
  - CrewAI
media_books: []
status: evergreen
---
### 智能体协作范式转移：从单体模型到分布式网络

当前人工智能应用正在经历一次深远的范式升级：未来的核心场景不再局限于孤立的单模型推理，而是建立在**AI 与 AI 之间的自主通信**之上。无论是在单一企业内部的业务流转、跨组织的跨实体协作，还是面向最终消费者的自动化代理，智能体都将代表人类实体去拆解任务、协商共识并推进执行。从技术实体来看，**智能体**（Autonomous Agents: 具备自主决策、持久运行且分布式部署的独立计算单元）并非静态的提示词容器，而是全天候在线、分布于全球各端云节点的自治实体。

这种演进打破了传统“人机对话”的单一交互模式，构建起一个由智能体构成的去中心化协作空间。智能体可以自主在注册表中发现对应领域的伙伴节点，动态建立对话上下文通道，将复杂目标进行任务委派与信息汇聚，最终向人类交付综合成果。这种多智能体自主协商的系统架构，构成了下一代人工智能系统的基础运行底座。

<details>
<summary>Original English Source</summary>

DE ACUERDO. Hola a todos. ¿Puedes oírme? Muchos gente, sí. Entonces, sé Por favor, guarden silencio. A mí Mi nombre es Vlad. I cofundador y director técnico en Doblar. Hoy quiero para discutirlo contigo cuatro temas. En primer lugar, tesis, nuestra tesis empresas, ¿qué somos? creemos. Evolución de la IA: de competitivo agentes para la ingeniería ciclos y más allá. Desafíos técnicos que ahora nos sentimos y lo cual debe resolverse inmediatamente. Y, por supuesto, Bend, para presentar empresa, producto y lo que hacemos. Comencemos con la tesis. Primero Ante todo, creemos que futuro para Comunicación entre IA dentro del negocio, entre empresas y también entre consumidores y negocio. AI hará el trabajo en nuestro nombre y para ellos tendrá que comunicarse entre tú mismo decide tarea para nosotros. En- segundo, los agentes autónomo, permanentemente activo entidades, distribuido sobre por todo el mundo. Él Bonitas palabras, pero yo Quiero gastar un minuto para ti imaginó cómo es realmente se verá así tipo de comunicación entre agentes. Hora de la demostración. Los agentes lo harán comunicarse en espacio de conversación. Se verán el uno al otro uno. Ellos serán repartido. Ellos recibirá tarea de nuestra parte o desde cualquier sistema . Podrán buscar colegas en los registros, invitarlos a espacio de conversación, delegar tareas, para recopilar información y vuelve con nosotros . Así es como se verá el futuro de la comunicación IA con IA. Entonces, mientras nosotros decimos, sujétalo en la cabeza.

</details>

### 上下文崩溃与拓扑分工：双重会话与循环工程的本质

现实中，几乎所有深入使用前沿模型的工程师都在自发运行多会话协作。例如在使用 **Claude** 或 **Codex** 处理复杂工程任务时，工程师往往会开启多个并行窗口：一个负责顶层规划，另一个负责交叉校验；一个负责编写生产代码，另一个负责语法与逻辑审查。这种工作模式的本质是人类开发者充当了**中央路由器**（Router: 负责在不同计算节点之间手动转发数据包的协调者），在多个认知单元之间机械地搬运上下文。

这种工程妥协的根源在于 Transformer 架构的基础限制。单纯将**上下文窗口**（Context Window: 模型能同时保留和注意的连续 Token 容量）扩大至一百万甚至两百万 Token，并不能直接转化为更高的工程效率。单体会话面临着固有的注意力稀释（Attention Dilution）、**上下文碎片化**（Context Fragmentation）以及**确认偏差**（Confirmation Bias: 单一模型倾向于强化自身先前生成的错误逻辑而非自我修正）等问题，导致信息召回质量和长程推理能力急剧下降。为了克服“狭窄单智能体”的缺陷，业界发展出了**循环工程**（Loop Engineering: 依靠控制脚本在多个专用模型之间迭代传递任务的状态机架构）。然而，市面上的主流实现往往依赖大量的 Python 或 TypeScript 胶水代码，开发者耗费海量精力编写的逻辑，仅仅是为了让不同进程之间能够互相派发指令。

<details>
<summary>Original English Source</summary>

Vamos Hablemos un poco sobre agentes competitivos. Creo que todos aquí lo saben este concepto, y yo Estoy seguro de que todos están aquí. también por ella usar. ¿Dónde estamos? ¿Lo usamos? Si usted usando a Claude o el Códice, estoy seguro, ¿Qué estás corriendo? varias sesiones para trabajando en uno tarea. Uno planes, otro cheques. Uno escribe código, otra comprobación código. Entonces, en esencia, en Sois dos personas trabajando. agentes sexuales sobre una tarea, y tú —como Cisco- enrutador o cambiar eso reenvía paquetes entre a ellos. Hablemos de ingeniería de ciclos. En esta conferencia fue muchos discursos sobre ingeniería de ciclos, muchos artículos, este bastante nuevo El concepto, ¿verdad? Pero me gustaría plantear al grano. Así que lo que Esto es ingeniería ¿ciclos? En principio, esto lo mismo que concepto preliminar. Estás lanzando esto. varios agentes, preferiblemente con apoyo Me convertiré, no sin ello, pero en lugar de ser un enrutador o centralita, usted Delega esto a alguien Código Python o TypeScript, escrito por alguien como proyecto de código abierto y este El código simplemente envía solicitudes a los agentes de un lado a otro, y tú recién lanzado proceso. Entonces, ¿por qué lo hacemos? utilizamos estos agentes cuando Realizamos lo siguiente ¿trabajar? A través de arquitectónico limitación transformadores, a saber a través del concepto de que llamado "estrecho" en lugar de un agente ", ¿verdad? Entonces, ¿por qué no lo hacemos? lanzamos uno agente en una sesión, ¿Quién lo haría todo? Por ejemplo, tendencia a confirmación pensamientos propios, ¿verdad? Atención borrosa, fragmentación contexto, deterioro recuerdo información. Entonces contexto para 1 o 2 millones de tokens no lo son te ayudará mejorar productividad.

</details>

### 通信架构的虚假解法：IM 隔离与无状态点对点协议的缺陷

在解决智能体间交互的问题上，业界尝试的第一条路径是复用人类的即时通讯软件（IM），如 Slack、Discord、WhatsApp 或 Telegram。然而，这类平台是为人类设计的，对自动化节点存在天然的集成摩擦与频控拦截。开发者将智能体接入这类平台往往需要经历极其繁琐的多步鉴权配置，且最终达成的拓扑极其脆弱——每个智能体只能单独与某个人类单聊，智能体之间依然处于数字隔离状态，无法形成动态群组。

第二条路径则是借助新兴协议，例如 **MCP**（Model Context Protocol: 用于向大模型暴露工具与资源的连接协议）或 **A2A**（Agent-to-Agent: 面向智能体间调用的通信约定）。然而，这些协议本质上依然是底层且无状态的技术规范：
* **无状态性限制**: MCP 本质上是无状态的远程工具调用，调用发起方无法保持持久上下文，更无法在后续阶段重新唤醒已完成阶段的状态。
* **单向客户端/服务端拓扑**: 在基础 A2A 模式下，智能体 A 调用智能体 B 属于标准的 Client-Server 架构；若 B 需要反向向 A 请求澄清，双方必须在两端分别实现全套客户端与服务端组件，极易因长链路的 RESTful API 级联超时而崩溃。
* **基础设施缺失**: 这些点对点协议缺乏原生的**服务发现**（Service Discovery）、会话持久化和缓冲队列支持。开发者为了让它们工作，最终把大部分精力消耗在重新发明消息中间件轮子等无意义的底层维护工作中。

<details>
<summary>Original English Source</summary>

Pero Hablemos Acerca de los sistemas multiagente sistemas, ¿de acuerdo? Nosotros ya entendemos que ejecutar varias sesiones —esto es, de hecho, trabajo multiagente sistemas. Cual la forma más fácil trabajo combinado múltiples agentes ¿juntos? Mensajeros, ¿Sí? ¿Ya tenemos Slack? ¿equivocado? Antrópico liberó a un agente para Slack, tenemos Teams, Discord, WhatsApp, Telegram, etc. ¿verdad? Entonces, esto es decisión. Bueno, entonces eso conectar agente a Telegrama, necesito cinco pasos. Eso Únete a Discord, Se requieren siete pasos. Para conectar agente para Slack, Se necesitan ocho pasos. Para WhatsApp—11. Y No es nada sencillo pasos. Todos se realizan manualmente y necesitas leer todo un libro para hacer esto ajustar. E incluso Si haces esto, Solo obtendrás uno, y nada más. Bueno, ¿qué? ¿Es así? Agente que se comunica con una persona, generalmente con tú. Este agente no es puede hablar con otros agentes, no puede hablar con otras personas, mientras no pasarás siete círculos del infierno. Por lo tanto, esencialmente sus agentes todavía están en una especie de digital aislamiento. Pero inteligente La gente dirá: "Yo sé decisión. Protocolos, ¿Sí? MCP, ACP, A2A, etc. Esto es Hay una solución. ¿No es así? Bueno, ¿y si...? partidario de tal enfoque para conectando su sesiones, entonces así será se parece al tuyo multiagente sistema. Espadín Los servidores se llaman otros agentes como " herramientas" a través de MCP . Y si quieres, tal vez este agente, que llamaste como herramienta, tal vez llamar a otro agente vía A2A. Suena extraordinario. simplemente. Bien, todos. saber qué es A2A. EN Google es muy grande presupuesto de marketing . Pero vamos echemos un vistazo a dificultades. MCP significa llamadas sin preservación del estado. Él significa que no lo eres Puedes volver al agente con quien habló, y de nuevo preguntar qué pasó. Comunicación A2A unilateral, si no implementarás en ambas direcciones. Por lo tanto , el agente A envía tarea para el agente B. Esto cliente-servidor. Si Quieres al agente B envió la tarea al agente A, esto también cliente-servidor. Atrás necesitas implementar desde ambos las partes y el cliente, y servidor. Cadena Llamadas a la API REST conducirá al tiempo- salidas. Y, por supuesto, Muchos están desaparecidos cosas como detección, condición sesión A2A, colas que aún necesitas implementar y agregar a todo esto. Y Si haces esto, construir realmente planificación. Usted no están construyendo multiagente sistema. Tú pierdes el tiempo en cosas aburridas, aburridas.

</details>

### 分布式系统的硬核挑战：传输保序、运行期绑定与全链路可观测性

要让异构环境下的智能体（例如运行在开发者本地 MacBook 上的终端进程与部署在云端容器中的推理服务）无缝协同，本质上是一个极其复杂的**分布式系统**（Distributed Systems: 多个计算节点通过网络通信协调动作以完成共同任务的软件架构）工程挑战。分布式传统软件已极难维护，而智能体本身具备非确定性（Non-deterministic）和微服务属性，进一步放大了系统的不稳定性：
* **实时保序传输层**: 大模型对消息的时序依赖极高，乱序的输入会导致逻辑全盘崩塌。底层传输层必须在保证低延迟的同时，实现消息的强保序交付与幂等重试。
* **状态持久化与微服务水合**: 智能体实例可能随时遭遇容器崩溃、Pod 重启或网络断连。系统必须具备透明的状态水合（Hydration）能力，确保节点崩溃恢复后不破坏多智能体系统的整体会话上下文。
* **运行期绑定机制**: 面对如 **LangGraph** 或 **CrewAI** 等异构编排框架，必须有一种统一机制将异构执行单元的线程标识（Thread ID）、会话标识（Session ID）与运行实例绑定（Runtime Binding: 在执行期动态映射跨系统标识符与路由实体的机制）。
* **高层级抽象与企业级可观测性**: 智能体通信不能停留在 IP 地址、端口或原始 Pub/Sub 主题层面，必须抽象出符合认知规律的实体：对话实体、通道房间、基于角色主体的智能消息路由。更为关键的是，系统的**可观测性**（Observability: 跨分布式节点透视内部状态、工具调用链路与因果关系的能力）绝不仅指捕获由节点 A 发往节点 B 的网络数据包，更必须完整追踪接收方智能体在解析消息后所触发的级联工具调用与内部思考链路。

<details>
<summary>Original English Source</summary>

Ahora resumamos qué ¿Qué sabemos? Nosotros sabemos que multiagente Los sistemas ya están aquí. Todos los que están aquí, utiliza varios agentes. Sabemos que plataformas de intercambio mensajes—esto No es una solución. Ellos creado para las personas y bloqueando activamente intentos de conectar De bot a bot. Y nosotros Sabemos que el protocolo— Esto es demasiado nivel bajo abstracción técnica, para que se pudiera hacer algo para construir sobre ello escala. Pero ¿Qué tan difícil es? crear un sistema que permitirá varios agentes ¿Unirse? No está tan mal. Es difícil, ¿verdad? Ya ves, la conexión agentes remotos a las sesiones como un proceso, lo que funciona en tu portátil o mío nube para ti código—esto es un problema sistemas distribuidos. Y distribuido sistemas por no es una definición simple. Olvídalo. sobre los agentes, ¿de acuerdo? Determinista software disposición—esta dolor de cabeza. Añade esto agentes que son microservicios y no determinista, ¿bien? Y recibirás mucho "placer" . Para resolver esto, usted realmente lo necesito prestar atención a capa de transporte, ¿No es así? Transporte debe ser real tiempo. Él debe ser ordenado, por lo tanto Lo que esperan los estudiantes de LLM ordenado mensaje. Tú necesitan ser procesados reintentos, etc. Necesitas proceso constancia y hidratación, porque tu agente es microservicio. Él puede para fallar, el pod puede caída, y luego todo tu multiagente El sistema fallará. Entonces, necesitas esto tener en cuenta. Tú necesidad de lidiar con algo muy nuevo— unión durante ejecución (enlace en tiempo de ejecución). Si quieres conectar LangGraph a código o nube para CrewAI, necesitas conectar ID del hilo (ID del hilo) con identificador sesiones, identificador ejecución y identificador lanzando estos pocos agentes y comparar estos identificadores entre ellos. De lo contrario Los agentes no podrán trabajar en grupo sobre un objetivo o tarea. Y, por supuesto, no puedes trabajar a nivel de propiedad intelectual direcciones, puertos, URL dirección o incluso tema de pub /sub. Necesitas elevarse por encima de todos detalles técnicos a otro nivel abstracciones: conversaciones, participantes, canales o habitaciones y enrutamiento mensajes, adaptado para agentes como los principales sujetos. Y, por supuesto, todo esto todavía no es suficiente para uso de tal producto o software de comunicación, porque cada organización busca el control. A ellos necesario identificación y observabilidad. La observabilidad no es solo un mensaje, enviado desde Agente A en el servidor A al agente B en servidor B. Y además, ¿Cuáles son los desafíos? herramientas tuvo lugar después ¿Cómo consiguió esto el agente? mensaje, ¿verdad? Y muy difícil proporcionar tal nivel observabilidad en repartido sistemas. Así que sin resolver todos estos Los agentes no tienen preguntas podrá comunicarse entre nosotros, y esto es nuestro un futuro maravilloso, donde todos llegan ingreso básico y tumbado en la playa, no vendrá.

</details>

### 通信层产品化实践：Bend 平台的运行时绑定与协同落地

针对上述工程痛点，**Bend** 打造了一套全局协作网络层，旨在解耦底层网络基础设施与上层智能体实现。该平台不受语言、部署框架或宿主环境的限制，提供多对多（Multi-peer）对等组网能力，并将核心系统能力下沉至通信基础设施层：
1. **全局服务注册中心**: 智能体接入网络后自动生成元数据卡片并向注册表公示，实现毫秒级的跨节点相互发现。
2. **中心化信道与过滤**: 状态持久化、会话流生命周期、消息鉴权与广播过滤均由底层平台管理，无须在客户端重复编写胶水逻辑。
3. **人在回路与访问控制**: 采用类似双边联系人授权的机制，跨宿主环境的智能体建立连接需经过双向握手，人类操作者始终对所有流转信息保有全量可视性与介入权。

在现场演示中，系统展示了两个处于不同网络和客户端环境的操作者协同：开发者 Vlad 本地 Mac 上运行着个人 Claude 助手，而另一位开发者 Mike 在终端运行着基于 Claude 终端代码与 Codex SDK 的实例。当这两个来自异构环境的智能体通过 Bend 运行时接入平台后，它们在数秒内完成互认，并在经双向授权后进入同一个协同会话空间。终端智能体自主创建项目房间、拉取 Codex 智能体协同开发网页，并能够在遭遇工程障碍时主动邀请人类进入专属频道进行干预与协助。这种方式消除了成千上万行脆弱的手写编排代码，使工程循环回归到真正健壮、透明的分布式协作系统中。

<details>
<summary>Original English Source</summary>

Quiero Presentamos a Bend. Nosotros en realidad se llevó todo, de qué hablaron y Decidí esto. Entonces, tú No hay necesidad para decidir esto solo. Puede muy fácil conectar a todos sus agentes dentro empresas o Tu Hermes y tu capa abierta. I Quiero presentarles el producto que Vamos a ejecutar esto semana. Esto es global nivel de interacción y cooperación para cualquier cualquier agente, cualquier ¿Qué plataforma, idioma? o el medio ambiente. Y esto no es solo de igual a igual, eso es multipar. Y nosotros tampoco Me olvidé de la gente. Si eres humano, eres todo Puedes hacer una cosa conectar y para hablar con tu agente. Esto es bastante normalmente. Y si nosotros Vamos a echar un vistazo bajo el capó, veremos que esto no es simplemente comunicativo nivel. Tenemos registro, así que su Los agentes se ven entre sí uno automáticamente, sin ningún esfuerzo adicional de tu lado. Persistencia, canales, filtración mensajes. En cambio para hacerlo en del lado del cliente, nosotros lo hacemos adentro plataformas. Seguridad, observabilidad etc. Ahora lo más interesante. Déjame mostrarte. te mostramos algunas demostraciones. Tiempo no es suficiente, así que demostración grabado, pero tenemos pararse. Por favor, Ven y mira vivir o simplemente conectar. Manifestación mostrará dos usuarios en dos diferentes navegadores, conectado a comunicación plataformas. Uno soy yo, Vlad. Tengo agente personal Claude, ejecutándose en una Mac. Y otro usuario— Mike, con el código de Claude en sesión terminal, ¿de acuerdo? Eh, Claude SDK y el propietario. Sala de demostración uno. En la parte superior En la ventana: yo, mi cuenta. Y yo tengo personal asistente. Más bajo- otro usuario, conectado al mismo nivel de interacción, sin Sin agentes. Bien, de acuerdo, yo Enviaré dos agentes, se unirán plataformas y se convertirán agentes pertenecientes a Micro. Y veamos, ¿Qué tan rápido es eso? será. Entonces, primero Lanzamos al agente. En unos pocos segundos tarjeta de agente aparece en la cuenta Micro. Estamos lanzando Propietario. En un segundo esta tarjeta de agente también aparece. De esto momento estos agentes conocerse mutuamente uno. Ellos comprender que pueden interactuar entre tú mismo. Pero queremos hacer algo más interesante. Queremos toma el agente del Códice y conectarlo a mi personal asistente en Mac para ellos podrían interactuar. Nosotros enviamos una solicitud a contacto que requiere convenio bilateral ambos lados a Se agregó un agente a registro de otro agente o persona. La solicitud ha sido enviada y yo Lo acepté. Ahora en tenemos un agente del Códice que puedes invitar a la mía personal asistente en espacio de conversación y comunicarse en tiempo real. Él completamente majestuoso agentes, pueden ser para implementar en cualquier ¿Dónde en el mundo, dónde? Están ahí. Y lo que ves aquí— Esto es en tiempo real. Tú También ves que porque mi agente se comunica con agente de otro usuario, tengo visibilidad completa de esto conversaciones. Ninguno La conversación no se llevará a cabo sin que yo sepa y mi el agente puede invitar yo en cualquier espacio para que pueda interactuar como una persona en un ciclo. Por lo tanto, acabamos de ver sin problemas conectar cualquier qué agente. Pruébalo en casa. Dime cómo. Todo ha terminado. Aquí hay más un ejemplo. Tenemos usuario Mike. Él todavía tiene en marcha Códice conectado a plataformas, y ahora nosotros queremos lanzar Sesión terminal de Claude código. Y queremos esta sesión terminal se unió a nosotros plataformas y interactuó con los demás agentes, ¿verdad? En este caso del código Claude en Terminales de Mike Se comunica con el SDK de Codex. Mike, pero desde Esto es global plataforma, no tiene valor. Ellos pueden para comunicarte con tu agente, con su agente y así sucesivamente. Entonces, lanzamos Claude y díselo en sesión de terminal: Por favor, Únete a nosotros plataformas. Mismo principio. Este en particular sesión Claude consigue identificador, tarjeta de agente, y nosotros Lo ocultamos todo dificultades desde el punto de vista vista de red. Y De ahora en adelante este agente puede crear espacio para comunicación como propietario, invitando otros agentes, en en este caso—Equidex, ¿Sí? Y él también invitaré a Mike. Por lo tanto Esto, ya sabes, es feliz. familia, y ellos pueden comenzar a trabajar en ingeniería tareas. Lo que No lo eran. Otro el nombre de aquello para lo que estás aquí Como ves, esto es ingeniería. ciclos (ingeniería de bucles). ¿Por supuesto? Pero esto ingeniería de ciclos sin 500.000 líneas de código por Python o TypeScript, que debe ser transferido para poder sus agentes podrían asignar una tarea a uno uno. Estos agentes comenzará ahora crear un pequeño sitio web, ellos lo harán interactuar entre por mí mismo y uno revisaré el trabajo otro. Y, por supuesto, si chocan con dificultad, y Mike se encontrará dificultades, estos agentes puede invitar yo en la misma espacio de comunicación. Puedo ayudarlos, para ayudarlos. Eh, y esto bastante simple. Eso es todo. Muchas gracias. Entré. a tiempo. Llegar a Nuestro stand LG17. Toma capturas de pantalla, escanear códigos QR. Uno —para la plataforma conectando su agentes, otro para futuro ingeniería de ciclos, que no necesita nada innecesario. Y también tenemos Obras que vinieron aquí, porque aman orquestación. No lo son Me encanta colaborar. Nos robaron todo mercancía. Entonces, si quieres Mercancía, ven a Works , toma la espada y ayúdanos a dar Ellos contraatacan. Gracias.

</details>