---
author: AI Engineer
date: '2026-10-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=eXA2tjRZIbY
speaker: AI Engineer
tags:
  - autonomous-agent
  - root-cause-analysis
  - site-reliability-engineering
  - incident-response
title: Resolve AI 探讨构建用于运维与修复软件的 Agent 系统六大支柱
summary: 文章介绍了 Resolve AI 在构建用于管理和修复生产软件的 Agent 系统中的经验与架构思考。作者指出生产故障排查需要因果推理、预防机制与团队协作上下文，并展示了其系统基于因果证据链排查故障的实际应用。
insight: ''
draft: true
series: ''
category: debugging
area: tech-engineering
project: []
people: []
companies_orgs:
  - Resolve AI
products_models:
  - Slack
  - Grafana
  - Google Cloud Platform
media_books: []
status: evergreen
---
<!-- chunk 1/3 -->

### 欢迎与背景介绍

大家好吗？听得到吗？非常清楚。非常感谢大家来参加这场分享。我叫 Varun，来自 Resolve AI 团队。我们构建 AI 来防范欺诈。实际上，我们创建 Agent 来启动并修复您的软件。在这场分享中，我们将探讨构建用于管理和修复软件的 Agent 系统所需的六大支柱。在开始之前，我想先举手表决了解一下现场的听众情况。我猜你们大多数人都是工程师。有多少人以前轮值过待命（on-call）？请举手。太好了。你们尝试过在轮值期间使用 AI 来协助自己吗？请举手。很好。那些举手的人，你们能说在值班期间 90% 的工作都是由 AI 完成的吗？真的能这么肯定吗？太好了。是的，这正是我们在创立公司时所认识到的。这是一项非常艰巨的任务。因此在这场分享中，我想分享我们的历程、演进过程、走过的路，以及我们在创建这样一个 Agent 系统中所吸取的教训。

<details><summary>Original English</summary>
¿Están todos bien? ¿Lo oyen? Perfectamente. Muy Gracias por venir. esta sesión. Mi nombre es Varún. Soy parte de Resolver equipos de IA. Nosotros creamos IA para defenderse contra fraude. De hecho, creamos agentes para empezar y corrigiendo su software software. Pronto esta sesión nosotros Consideremos seis pilares del agente sistemas que usted será necesario para gestión y reparación tu software. Antes empezar, recoger manos para que yo entienda, ¿Quién está hoy? audiencia. Supongo, la mayoría de ustedes— ingenieros. ¿Cuántos de Has trabajado antes en modo de espera ( ¿De guardia? Levanten la mano. Perfectamente. ¿Lo intentaron? usted usa La IA ayudará yo mismo durante ¿Turnos? Elevar manos. Perfectamente. Aquellos que levantó las manos, o ¿Puedes decir eso? El 90% de tu trabajo está bajo tiempo de servicio ¿Funciona la IA? Puede Claro que sí. ¿afirmar? Perfectamente. Sí, eso es exactamente lo que somos. entendido cuando fundó una empresa. Él muy difícil tarea. Entonces en este Quiero sesiones comparte nuestro viaje, evolución, que pasamos, y nuestras lecciones en creando tal sistema de agentes.
</details>

在深入探讨之前，我想先描述一下我们当下所处的大环境背景。第一波 AI 浪潮完全聚焦在编程上。坦白说，我认为对我们大多数人而言，编写代码的方式已经彻底改变了。我也想解释一下为什么会这样。首先，代码本身是自文档化的，AI 很容易进行分析和理解，从而在下一步为你提供帮助。第二，代码在本质上具有很强的模块化特性。因此，AI 很容易将其拆解为若干部分，推进到下一阶段，并帮助你在此基础上进行扩展和构建。第三，也是最重要的一点，代码属于单一领域范畴。你不需要为了让 AI 在单一领域内进行推理而教授它许多学科。它很容易面向后续步骤展开，这就是为什么我们能拥有如此明确的效率衡量指标。你可以客观地评估 AI 为你解决这个任务的效果有多好。

<details><summary>Original English</summary>
Antes de proceder a Vale, quiero describir el contexto de lo que tenemos hoy. Primera ola La IA estaba enfocada exactamente en programación. Justo diciendo, creo, para la mayoría de nosotros forma de escribir código completamente cambió. Yo también quería explicar por qué Así fue como sucedió. En primer lugar, el código en sí es autodocumentado La IA es fácil de analizar. y entenderlo, para que para ayudarte con siguiente paso. En- segundo, el código a su manera De naturaleza muy modular. Por lo tanto, la IA es fácil rómpelo en pedazos partes, mover a la siguiente etapa, y también para ayudar te expandes y construir sobre ello base. En tercer lugar, y esto Lo más importante es el código. esfera de dominio único. No necesitas hacerlo enseñar IA a muchos disciplinas para que él podría razonar dentro de los límites uno. Él es fácil está orientado hacia próximos pasos y Por eso tenemos indicadores tan claros eficiencia. Tú ¿Puedes objetivamente? para evaluar cuánto Bueno, la IA resuelve esto. tarea para ti.
</details>

但现实中，作为工程师，我们 70% 的时间都花在其他事情上：并不是用来创建新软件，而是用于处理生产系统——系统的上线运行和程序修复。呃，这涵盖了非常广泛的问题，对吧？比如生产软件的运维和发布。

<details><summary>Original English</summary>
Pero en realidad, como ingenieros, nosotros pasamos el 70% de nuestro tiempo en otro: no para creación nuevo software y para trabajar con productividad sistemas—puesta en marcha y Corrección del programa. Eh, y eso cubre amplia gama preguntas, ¿verdad? Como- aquí está la explotación y lanzamiento de software software.
</details>

### 运维任务的三类比喻

通常，所有这些都可以分为三大类。例如，不妨联想一下医疗保健的类比。这是最直观的方式，也是我最喜欢思考的角度。第一类是日常维护与技术服务。把它想象成平时不断出现的琐碎小问题。也许你需要泰诺来止痛，也许你需要安诺，这些就是轮值待命期间需要处理的典型通知告警。第二类是需要全面动员的重大事故（incidents）。这就好比外科手术，系统正在宕机中断，需要所有相关责任人赶到现场来抢修一切。第三类就像是你每天服用的维生素。也就是说，你需要持之以恒地做很多事情来维护系统的正常运转，这可能包括基础设施审计、成本分析，或者平台扩容的工程工作。

<details><summary>Original English</summary>
Por lo general, todo esto es posible. dividir en tres grandes categorías. Por ejemplo, piensa en sobre la analogía con cuidado de la salud. Él la forma más fácil, sobre lo cual también me encanta pensar. El primero es servicio regular y técnico servicio. Imagínalo como algo normal. problemas menores que surgen constantemente. Tal vez necesites Tylenol de alguien dolor. Tal vez tú Necesito Advil. Por lo tanto, Estas son notificaciones típicas mientras estaba de servicio, con cuáles se necesitan trabajar. Segundo categoría—esta incidentes donde Se necesita completo movilización. Él igualmente operación quirúrgica . Los sistemas se están apagando . Se requiere atención todos los que involucrado o responsable de venir y todo para arreglar. Y el tercero categoría—es como la tuya vitaminas diarias. Entonces, necesitas hacer muchas cosas de forma permanente, para apoyar tu capacidad de trabajo sistemas. Esto puede cosas como auditoría infraestructura, análisis de costos o trabajo de ingeniería en plataforma para escalada.
</details>

这些事情从根本上就极其复杂，因为它们并不完全像写代码那样。它们涵盖了众多不同的领域和工具，而这正是当最初对 AI 补贴的狂热退去后我们开始看到的后果。这也正是你现在在新闻中所看到的。大家越来越多地在讨论 AI 生成的代码在生产环境中可能引发的大量问题，并讨论哪些框架最适合解决这些问题。其次，无限 AI 的时代已经画上了句号。也就是说，无限资源的 AI 已不复存在。如今越来越频繁地能听到大家谈论 token、token 优化以及 token 效率。如何改进这些架构？为了精准高效地使用 AI，需要哪些严谨的工程解决方案？第三点是关于一段对话，这段讨论因微软首席执行官萨提亚·纳德拉（Satya Nadella）而广为人知，他在其中谈到了通用基础模型之上针对各类高度专业化工作所需的架构层。

<details><summary>Original English</summary>
Estos cosas fundamentalmente complicado porque ellos no es exactamente como un código. Ellos cubrir una multitud diferentes dominios y herramientas, y eso es todo. tales consecuencias nosotros comenzamos a ver, ¿Cuándo es la primera euforia? de los subsidios de la IA. Y exactamente Esto es lo que ves ahora en noticias. Más están hablando de número de problemas, que puede crear código de IA generado en producción y discutir cuál Los marcos de trabajo son los mejores adecuado para resolver estos problemas. En segundo lugar, la era IA ilimitada ha llegado a su fin. Eso es IA ilimitada Ya no existe. Todo se puede escuchar con más frecuencia hablemos de fichas, optimización de tokens y eficiencia fichas. ¿Cómo puedes? mejorar estos arquitectura, esas ingeniería rigurosa soluciones que se necesitan para una eficacia y uso preciso ¿AI? Y el tercero es conversación que, aparentemente, se hizo popular Gracias a Satya Nadelli, general al director de Microsoft, donde Habló de arquitectura, el piso requerido modelos convencionales para cualquier trabajo altamente especializado AI.
</details>

### 从生成式任务到确定性任务

这里存在着广泛的分类，对吧？当你面对的是内容生成任务时，并没有单一明确的结果或预期产出。你不会也不需要明确告诉 AI 图片、博客或网站到底应该长成什么样。在那种场景下，皆大欢喜。但当你反过来考虑那些存在唯一正确答案的任务时，也就是你希望从 AI 那里获得精准答案时，失望往往就从这里开始了。大多数人称之为“最后一英里”，但这是我在生活中跑过的最漫长的一英里，而 AI 必须攻克它。这就是为什么你需要专门的架构来聚焦在特定问题上。

<details><summary>Original English</summary>
Entonces, hay una amplia clasificación, ¿verdad? Cuando miras tarea de generación, en Tú no estás ahí específico resultado o resultado esperado . No quieres y no lo haces. decirle a la IA exactamente cómo debería verse así imagen, blog o sitio web. Aquí lo tienes. La euforia se instala. Pero cuando lo piensas sobre el reverso tarea donde hay una respuesta correcta, ¿Cuál quieres? para obtener de la IA, exactamente entonces comienza decepción. La mayoría de la gente lo llaman " "la última milla", pero Esta es la milla más larga que he corrido en mi vida. tendrás que superados por la IA. Aquí ¿Por qué necesitas estos? arquitectura, para que centrarse en un problema específico.
</details>

此外，生产系统的运维也是一个涉及众多用户和系统的难题。你不可能单打独斗完成。你需要让各个团队的专家共同参与进来。随着时间推移，我们每个人都专注于不同门类的工程方向。我们跨团队协作，借助 AI 探讨并解决与生产系统相关的各种问题。抱歉，这正是关乎你的生产系统的关键所在。

<details><summary>Original English</summary>
Además, operación sistemas de producción— Esto también es un problema. muchos usuarios y sistemas. No lo haces Esto lo harás tú solo. Tú es necesario involucrar expertos de diversas comandos. Con el tiempo, todos de nosotros especializado en diferentes categorías ingeniería. Nosotros trabajamos en diferentes equipos para discutir y para resolver cualquier problemas para con la ayuda de la IA. Lo siento , se refiere a tu producción sistemas.
</details>

### Resolve AI 的产品架构

总的来说，我们公司 Resolve AI 是从一个核心论点起步的。我们真诚地相信，在生产系统中所执行的所有这些工作——例如错误修复或日常软件维护——主要都应当由 Agent 来执行。这也是我刚才提问的原因：你们能否肯定地说，自己 90% 的工作或是最高效的产出都是由 Agent 完成的？工程师理应只需管理这些能够自我修复并发布软件的 Agent。正因如此，我们创建了 Resolve AI，涵盖了三类 Agent：用于解决日常突发软件问题的服务 Agent；协助管理事故沟通频道、引导你从复杂事故排查到根本原因并予以消除的事故响应 Agent；以及协助处理后台生产任务的后台 Agent，例如监听发布流程、执行必要分析，或是根据特定调查需求触发相应条件。

<details><summary>Original English</summary>
En general, Nuestra empresa Resolve AI comenzó su actividad de uno tesis. Creemos sinceramente, que todo este trabajo que tú actúas en sistemas de producción, como la corrección errores o diarios mantenimiento de software, principalmente tienen ejecutar agentes. Él una de las razones por las que yo preguntó: ¿puedes? Puedes decir con seguridad: que el 90% de su trabajo o mayor rendimiento ¿agentes? Ingenieros acabo de tener para gestionar estos agentes que toman autocorrección y lanza tu software software. Exactamente Por eso creamos Resolve. La IA como tres categorías agentes. Hay agentes de servicio para resolver problemas con Software emergente a diario. Y hay agentes de incidentes que te ayudará a liderar canales de incidentes y para guiarte desde incidente complejo a la causa raíz y su eliminación. Y finalmente, hay antecedentes agentes que te ayudará con producción tareas. ¿Es así? escucha despliegue, o cualquier ¿Qué análisis? ¿Qué necesitas? deben llevarse a cabo, o las condiciones que usted comenzar cuando quiero gastar específico investigación.
</details>

在所有这一切的底层，承载着 Resolve AI 统一的 Agent 架构。这也是我们今天所要探讨的核心：达到这一目标并构建起这套架构到底需要什么。那么，让我们从一个问题开始：为什么必须这么做，对吧？为什么我们不能直接把最大的模型接入生产数据中？当然，模型自身是在不断进步的，它们用于解决软件问题的推理思考能力也在提升。当你专注于某个特定用例并在其上构建专属系统时，效果确实看起来很棒，演示效果也非常出色。但逐渐地，当你开始在不同的使用场景和团队之间进行扩展时，系统里就会开始显现出非常熟悉的裂痕。

<details><summary>Original English</summary>
EN la base de todo esto miente igual arquitectura de agentes Resolver la IA. De eso se trata. hoy y Hablaremos. Y sobre lo que se necesita para para llegar a este punto y Construye esto. Por lo tanto, Comencemos con una pregunta. ¿Por qué ocurre esto? necesario, ¿verdad? ¿Por qué no podemos? solo directo el modelo más grande en ¿Datos de producción? Modelos, por supuesto, están mejorando. Su capacidad de consideraciones para resolución de problemas con el software está mejorando. Esto realmente se parece a efectivo cuando concentrarse en caso específico y crea tu propio sistema Además de eso, Resulta muy bien demostración. Pero gradualmente, cuando tú empiezas escala entre diferentes escenarios uso y equipos, aquí mismo en El sistema se inicia parecer muy grietas familiares.
</details>

那么，当沿着这条路径去扩展产品时，我们所见到的这些裂痕到底是什么？首先你会注意到的是，模型本身确实带有偏见与束缚倾向。这是你在日常工作工具中必须正视的一个非常重要的问题。它们的构建机制倾向于给出迎合你的顺从回答；而且首先，随着具备更强推理能力的新模型不断涌现，你也必须跟上这种迭代步伐。你同样需要不断调整——首先评估哪款模型适合当前任务，然后将其更新替换为更适合的一款，以便

<details><summary>Original English</summary>
Por lo tanto ¿Qué son estas grietas? vimos cuando tú tú empiezas escalar el producto ¿En este camino? Primero, Lo que notarás es que que modelos, por supuesto, tener prejuicios encuadernaciones. Esto es muy algo importante con lo que tienes que lidiar tiene que afrontar directamente en sus trabajadores herramientas. Ellos creado para dar acordado contigo respuesta y, en primer lugar todo cuando aparecen nuevos modelos con mejor habilidades para razonamiento, tú también necesito mantenerme al día a este ritmo. Tú también necesidad constante cambio—primero evaluar qué modelo adecuado para tarea, y luego actualízalo al uno ¿Cuál es más adecuado? para
</details>

<!-- chunk 2/3 -->

你的情况。

第二个方面多少有些被低估了。我们总是把模型与运行过程或结果联系起来。但每个工作流都包含数百种不同类型的任务。例如，有推理任务，有用于验收的确定性任务。还有诸如视觉推理或基于图像的推理、通过 SQL 进行的推理，或者像日志这类内容的推理。现在你看到的周围所有先进模型，每一个都擅长某项任务或特定类型的任务。你需要构想出一个编排机制来在工作流中轮换切换这些模型：首先，它必须能够跟上模型发展的步伐；其次，它必须能够为最佳任务选出最佳模型。

<details><summary>Original English</summary>
tu caso.

Y el segundo es algo

Un momento subestimado.

Siempre nos conectamos

modelo con funcionamiento

proceso o

resultado. Pero

cada flujo de trabajo

tiene cientos de diferentes

tipos de tareas. Entonces, hay

tarea en

razonamiento, hay

determinista

tareas debido a las cuales

Estás aprobando. Hay tales

cosas, en general

razonamiento visual

o razonamiento sobre

basado en imágenes,

razonamiento a través de SQL

o cosas como registros

. Ahora todos los avanzados

los modelos que ves

alrededor, cada uno de ellos

bueno en algo

tarea o una tarea específica

tipos de tareas. Atrás

mecanismo de orquestación

que necesitas

imagina para

alternando entre estos

modelos para

flujo de trabajo, según

Primero, debe ser a tiempo.

para el desarrollo de modelos,

y en segundo lugar, debe

poder seleccionar

el mejor modelo para

La mejor tarea.
</details>

第二个失效模式当然就是上下文窗口了。我知道上下文窗口正在不断扩大，但上下文窗口并不是解决如此艰巨任务的唯一问题。第二部分在于，如果你提供了过大的上下文，模型就会开始“钻研”。它们会开始虚构出根本不存在的假设，或者有时甚至无法带你找到正确答案。而如果你提供的上下文非常有限，它们当然就会“研究不足”。它们无法切中要害，看不到现存的方法，也看不到解决问题可能存在的其他潜在假设。

<details><summary>Original English</summary>
El segundo modo de fallo es

, por supuesto, contextual

ventanas. Yo sé eso

ventanas de contexto

se están expandiendo, pero

ventanas de contexto—esto

no es el único problema para

solución de tal

una tarea difícil.

Segunda parte

es que

si usted proporciona

demasiado grande

contexto, modelos

comenzar "

investigar."

Comenzarán

inventar hipótesis,

que ni siquiera existen,

o a veces pueden

ni siquiera traer

tú al correcto

respuestas. Ahora,

si proporcionas muy

contexto limitado,

por supuesto que ellos "

"Están poco investigados."

No podrán

para ir al grano, en

no serán visibles

de los que existen

formas o qué más

hipótesis potenciales

puede existir para

resolución de problemas.
</details>

特别是对于生产故障事件而言，这会变成一个巨大的难题，因为遥测数据在字面意义上是无限的。你可以随意生成海量的日志行，需要多少就产生多少，指标也是要多少有多少。而现在，当你开始将这些与你的代码及基础设施结合在一起时，正是在那一刻，系统开始出现真正的裂缝。

<details><summary>Original English</summary>
Especialmente para

producción

incidentes se convierte

un problema enorme

, debido a la telemetría

literalmente

infinito. Tú

puedes crear

tantas líneas de registros,

tanto como quieras, y

tantas métricas,

¿Cuánto necesitas?

Y ahora que tú

empiezas a combinar

esto con tu código y

infraestructura,

justo en ese momento en el sistema

están empezando a aparecer

grietas reales.
</details>

第三点，也是我最关注的，是确定因果推理。模型的设计初衷往往是为了迎合你。我是说，我们大家都遇到过这种情况：当你对模型施加过强引导时，它就会开始在任何方向上都顺从你。所以，模型是专门设计来给你连贯顺畅的回答，而不是因果联系。但在生产故障事件中，你唯一追寻的就是像侦探办案一样的因果证据链。究竟是哪些步骤导致了这个特定的事故，以便你能切实修正真正的问题，而不仅仅是打个补丁。特别是当你解决像生产故障根因分析这样棘手的问题时，你需要将因果思维植入到模型和系统中，而不仅仅是拼接回答。

<details><summary>Original English</summary>
Tercero, y mío

El favorito es

determinar la causalidad

consecuente

consideración. Por lo tanto,

Existen modelos para

para complacer

tú. Quiero decir, nosotros

todos se han encontrado

tales casos,

cuando haga clic en

modelo también

fuertemente, y ella

comienza

estar de acuerdo contigo

en cualquier dirección

. Entonces, los modelos

especialmente

diseñado para

para darte coherencia

respuestas, no

causal

conexiones. Pero en

producción

incidentes, lo único que

lo que estás buscando es

causal

cadena de evidencia, como

detective. ¿Qué pasos?

condujo a

específico

incidente para que usted

podría realmente

corrige la correcta

un problema, no solo

crear un parche Ago,

especialmente cuando tú

resolver un problema difícil

un problema como

producción

justificación, tú

es necesario que

pensamiento causal

fue construido en

modelo y sistema, no

solo conectado

respuestas.
</details>

接下来当然就是预防措施。我不会在这个话题上停留太久，但大家都读过有关人工智能删除了某个文件系统或数据库的新闻。对 AI 而言，这也是一种功能，不是吗？并不是错误。AI 可能会认为最彻底的修复方式就是直接删除这段特定代码。你不能因此责怪它。你只需要在系统周围建立预防机制，以确保它能正常工作。AI 在给定的任何场景下工作，需要何种最低访问权限？

<details><summary>Original English</summary>
Y el siguiente

, por supuesto, es

medidas de precaución. I

No seré demasiado.

detente aquí

tema, pero todos

lee las noticias sobre

como la inteligencia artificial

elimina una cierta

sistema de archivos o

base de datos. Entonces, para

La IA también es una función,

¿No es así? Y no

error. La IA podría

decide que

lo más puro posible

La corrección es

eliminación simple

este en particular

fragmento de código. Usted no

puedes culpar

Él por esto. Tú solo

es necesario construir

precauciones

alrededor del sistema para

ella trabajaba

adecuadamente. Cual

nivel mínimo

Se requiere acceso

IA para el trabajo en cualquier

a la cual se le dio

¿Escenarios?
</details>

最后一个是学习闭环。无论你构建什么样的系统，它在理想情况下都应该能面向你的团队或整个组织进行扩展。正如我一开始所说，每当将 AI 用于生产事故时，这是一个多人协作的问题。它涉及许多不同的团队，例如 SRE、平台团队、后端工程师或服务工程师。所有这些人都必须参与进来。而且最重要的是，所有这些人都应当拥有相同的上下文。既然你在其中加入了时间维度的讨论，你的 AI 系统在面对第一百次调查时，就应该具备与先前调查相同的上下文，否则你每次都得从零开始。

<details><summary>Original English</summary>
Y el último—

ciclos de aprendizaje. Cualquier-

¿Qué sistema tienes?

construir, debería ser

escalable para

tu equipo o

toda la organización en

a lo mejor.

Siempre que

utilizando IA

para producción

incidentes como yo

dijo al principio, esto

multijugador

problema. Tiene

muchos equipos diferentes,

como SRE, plataforma

equipos, backend-

ingenieros o

ingenieros de servicio.

Todas estas personas deben

estar involucrado. Y

lo más importante, todos estos

la gente debería tener

mismo contexto.

Ahora que usted

agregar a esto

discusiones de tiempo, tu

El sistema de IA debería

tener lo mismo

contexto

anterior

investigación sobre

investigación número cien

de lo contrario lo harás cada vez

Empiezas desde cero.
</details>

### 六大支柱架构

这些就是我们看到裂缝显现的失效模式。正因如此，我们创建了一个恰好能解答这些问题的 Agent 架构。任何要在特定专业领域运行的 AI 架构，都包含六个核心组成部分。我之所以提到特定领域，是因为基础模型面向的是通用思维。现在，当你想引导这些模型给出特定答案时，你需要关注六个不同的支柱。

<details><summary>Original English</summary>
Estos son los modos

negativas, donde vimos,

¿Cómo se ven?

grietas. Por eso nosotros

creó una agencia

arquitectura que

responde exactamente estas

pregunta. Entonces, hay

seis principales

piezas para cualquier

arquitectura de IA, que

debería funcionar en

un dominio específico

áreas. Razón,

¿Por qué menciono?

específico del dominio

área, consta de

porque los modelos

destinado a

pensamiento general.

Ahora, cuando quieras

para dirigir estos modelos

en un específico

respuesta, tú

necesito cuidar de

seis pilares diferentes.
</details>

第一个是模型编排。正如我已经提到的，模型编排包含两个层面。第一：你如何跟上模型不断更新的步伐，并使用其中最新的模型？第二：你如何为特定任务选择最佳模型？是用 Gemini 进行图像分析？还是用 OpenAI 执行确定性步骤？抑或是用 Claude 进行开放式探索调查？你必须持续评估在特定时刻哪个模型最适合完成任务。因此，这是我们从一开始就建立的机制。

<details><summary>Original English</summary>
El primero es

orquestación de modelos.

Como ya mencioné,

orquestación de modelos

consta de dos

niveles. Primero: ¿cómo estás?

¿Llegas a tiempo para...?

actualización constante

modelos y

usando

¿El más nuevo de ellos? Y

En segundo lugar, ¿cómo?

elige el mejor

modelo para

tarea específica

¿ Quizás Géminis para

¿Análisis de imágenes?

O OpenAI para

determinista

¿pasos? ¿Es posible?

Claude para abrir

¿investigación? Tú

debe constantemente

evaluar qué modelo

es lo mejor para

finalización de tareas en

momento específico.

Entonces, este es un mecanismo,

que creamos a partir de

desde el principio.
</details>

第二个是上下文工程。如今，上下文工程往往被狭隘地简化为数据库或具体实现的方案。“噢，你们是在用 Graph RAG 吗？你们用知识图谱吗？你们用 X、Y 和 Z 吗？”这一切都在于实现细节。但核心问题在于，AI 解决这些问题到底需要多大体量的上下文。大多数情况下，这需要综合运用不同的方法。也许你得使用类似 Graph RAG 的方案来让 AI 启动调查；而当你进入后续步骤时，你必须确定极其精准的工具调用，以免在运行时查询日志、指标、仪表盘或代码等内容时过快消耗 Token。

<details><summary>Original English</summary>
Segundo

—esto es contextual

ingeniería. Ahora

ingeniería de contexto

a menudo reducido únicamente a

bases de datos o

solución para

implementación. Oh, tú

¿Estás utilizando el gráfico RAG?

Usted usa

¿Gráfico de conocimiento? Tú

usar X, Y y

¿Z? Todo reside en los detalles.

implementación. Pero

la pregunta principal en

¿Cuál es el volumen exacto?

Se necesita contexto

La IA para resolver esto

problemas. Y

con mayor frecuencia esto

combinación de diferentes

métodos. Tal vez tú

tendrá que

usar

solución de tipo gráfico RAG,

para que la IA pueda comenzar

investigación. ¿Y cuándo?

vas a

próximos pasos, usted

necesidad de determinar

llamadas muy precisas

herramientas para no

gastar fichas

demasiado rápido bajo

tiempo de ejecución

consultas de registro,

métricas, paneles o

código, etc.
</details>

第三个是因果推理。正如我已经说过的，这是我们融入 Resolve AI 的基本原则之一：根本原因始终存在于证据链之中。导致这一特定问题的具体步骤是什么？如果我们无法建立这条证据链，我们就必须提供置信度较低的信息，并将用户引向其他方向。这适用于任何专用的专业 AI，包括 Resolve AI：如果我们在某个节点之后看不到数据支持，我们就会为你重新指引方向。

<details><summary>Original English</summary>
El tercero es

causal

consideración. Como ya

dijo que era uno de

fundamental

principios que nosotros

Integrado en Resolve AI:

la causa raíz siempre

Residencia en

cadena de pruebas. Cual

fueron los pasos que condujeron

a este en particular

¿Problemas? Si no lo hacemos

podemos instalar

esta cadena, nosotros

tenemos que proporcionar

información con bajo

nivel de confianza

y dirigir

usuario a otro

lado. Esto se aplica a

cualquier

IA especializada,

incluyendo Resolve AI: nosotros

te estamos redirigiendo,

si no vemos los datos

Después de cierto punto.
</details>

接下来，正如我已经说过的，是受控行为。这相当直接。它取决于每个团队、每个组织、权限级别、限制条件或你所在的行业。为确保 AI 正常运行，需要设定哪些具体的熔断保障？这是只读的吗？它有写入权限吗？如果有写入权限，其执行条件是什么，等等。

<details><summary>Original English</summary>
A continuación, como ya he dicho

dijo: "Está controlado"

comportamiento. Es bastante sencillo.

Depende de

cada equipo,

cada organización,

niveles de acceso,

restricciones o industrias,

en el que trabajas.

¿Cuáles son los específicos?

Se requieren fusibles

determinar para el trabajo

¿AI? ¿Esto es lectura? Él

¿registro? Y si el registro,

¿Cuáles son las condiciones para

existe, etc.
</details>

最后一个是系统学习。不妨这样想：你们与 AI 系统的每一次交互都是一次学习的机会。因此，人工智能系统不仅要在调查过程本身中学习，还要学习用户如何与它交互。例如，我是否应该为你提供正向反馈支持？这是否转化为正面评价？我是给你负向反馈吗？或者我是引导你、指导调查朝某个特定方向进行？这些都是不同类型的评估。这引出了最后一部分，评估同样是一个至关重要的阶段。这是任何 Agent 架构的起点和终点。我们正在考虑五个不同维度的评分，正如我刚才提到的。你能提供什么样的正强化？你能提供什么样的负强化？我们是否能够追踪你已经做出了怎样的决策？我们能否以此为基准对你这位工程师进行评估？比如最好的工程师会如何进行这项调查，而你与之相比表现如何？此外，作为人工智能，你又如何自我校准？你如何定义这种置信水平？

<details><summary>Original English</summary>
Y

El último es el sistema

enseñanza. Piénsalo.

sobre ello de esta manera. Cada uno de ustedes

interacción con el sistema

La IA es una oportunidad para

enseñanza. Por lo tanto,

sistema de inteligencia artificial

La inteligencia tiene

aprender no solo en

el proceso en sí

investigación, pero también en

porque como usuario

interactúa con él.

Por ejemplo, ¿debo proporcionar?

positivo para ti

¿apoyo? Por lo tanto,

¿Esto convierte?

¿Para una evaluación positiva?

¿Te doy?

negativo

¿apoyo? O

Te guiaré o

Yo te guiaré

investigación sobre

¿Una dirección determinada? Él

diferentes tipos

evaluación. Él

nos lleva a

la última parte, donde

La evaluación también es

una etapa muy importante.

Este es el comienzo y

punto final para

cualquier

arquitecturas de agentes.

Estamos considerando

calificación de cinco puntos

diferentes niveles, como yo

Ya lo mencioné. Qué

positivo

refuerzo para ti

¿Puedes proporcionarlo? Qué

negativo

refuerzo para ti

¿Puede usted proporcionarlo y si

¿Podemos rastrear?

¿Cómo estás?

¿Ya has tomado una decisión?

¿Podemos estimar?

usted, como ingeniero, en

¿En base a esto? Como si

mejor ingeniero

lo gasté

investigación y cómo

te comparas con él

¿ Y además, ¿cómo lo haces?

Calibre usted mismo como

¿inteligencia artificial? Como

tú defines esto

¿Nivel de confianza?
</details>

<!-- chunk 3/3 -->

这一切都是系统性的。这些都是构建在一个平台中的能力，而且每当出现新模型、新用例或架构发生变化时，都需要不断参考架构。非常棒。

<details><summary>Original English</summary>
Todo esto es sistemático. las calificaciones que construir en uno plataforma, y cuál constantemente necesario referirse a arquitectura, cuando aparece uno nuevo modelo, nuevo caso usar o cambios arquitectura. Empinadamente.
</details>

废话不多说。让我来展示一下在实践中 Resolve 是如何运作的。正如前面所说，我们的平台正是专门为此打造的。我们使用两类智能体：一个是跟进智能体，另一个是事件智能体，当然还有后台智能体。

<details><summary>Original English</summary>
Basta de hablar. Déjame mostrar cómo es funciona en Resolve en práctica. Como ya dijo nuestra plataforma creado específicamente para este. Entonces, nosotros trabajamos con dos categorías de agentes. Uno es el siguiente agente, el otro es un agente con incidentes y, por supuesto, agente de fondo.
</details>

鉴于在座的各位大多数都是工程师，可能对这个系统很熟悉。当然，你们大部分的遥测或可观测性通知都会发送到协作工具中，比如 Slack、Microsoft Teams 或你们使用的其他工具。在这个案例中，我们可以看到 Grafana 是如何向我们 Slack 上的共享频道发送通知的。

<details><summary>Original English</summary>
Dado que la mayoría Si alguno de ustedes está aquí, es ingeniero. Puede que estés familiarizado con este sistema. Por supuesto , la mayor parte de tu telemétrico o de observación Están llegando notificaciones herramientas para colaboración, como Slack, Microsoft Teams u otros, ¿Cómo eres? usar. En este caso que vemos cómo Grafana envía notificación en nuestro Canal compartido en Slack.
</details>

Resolve 会自动抓取这些通知并启动调查。大家已经可以看到系统报告了对数刻度错误，并开始指出已发现通知的根本原因，以及它排除了的其他因素或假设。它提供了简明扼要的根本原因、证据和建议。

<details><summary>Original English</summary>
Resolver automáticamente recoge estos notificaciones y comienza investigación. Tú ya ves que el sistema informes sobre error de escala logarítmica y comienza a señalar causa principal descubierto notificaciones, así como otros factores o teorías que ella rechazado. Ella proporcionó una concisa causa raíz, evidencia y recomendaciones. Pero
</details>

但让我们深入细节。正如前面所说，在大多数情况下这应该是一项协同工作。因此，让我们切换到界面，看看幕后究竟发生了什么。

<details><summary>Original English</summary>
Profundicemos en detalle. Como ya dijo, en la mayoría casos en los que debería ser trabajo conjunto. Por lo tanto, Pasemos a interfaz y Veamos qué está sucediendo en entre bastidores.
</details>

工作始于 Resolve AI 读取作为单独请求进来的通知。它接收该请求并运行若干不同的智能体——实际上是两类智能体——来完成工作。

<details><summary>Original English</summary>
Trabajar comienza con Resolve AI, cuando lee notificación que viene como un artículo separado pedido. Él se lleva esta. solicitud y ejecución varios agentes diferentes, en realidad dos categorías de agentes, para hacer el trabajo.
</details>

第一类智能体本质上是调查员。它们受过训练，能像工程师一样开展调查。首先是查明问题所在，从指标、链路追踪等中收集更多信息；利用追踪和日志确定问题发生的具体位置，然后开始与变更事件或代码及基础设施中的任何新部署进行比对。

<details><summary>Original English</summary>
Primera categoría agentes—esto es, en esencia, investigadores. Están entrenados conducta investigación sí Tal como lo harías tú. ingeniero. En primer lugar, para averiguar qué El problema es, recolectar más información de las métricas, rastreo, etc. Determinar dónde ocurre problema, para utilizando trazas y registros, y luego comienza a compararlo con cosas como eventos de cambio o cualquier ¿Cuáles son los nuevos despliegues? en tu código y infraestructura.
</details>

它主要基于四类数据源进行分析或推理：代码、基础设施、知识库以及可观测性平台。基于这一切，它开始给出我们所见问题的起因或根因。这里有一条调用记录，实际上失败率很高。它将问题追溯到了系统中依然处于激活状态的一些废弃集成。

<details><summary>Original English</summary>
Principalmente él realiza este análisis o razonamiento sobre basado en cuatro tipos de fuentes de datos. Tu código, tu infraestructura, su bases de conocimiento y la suya plataformas observación. En la base de todo esto comienza a dar causa o raíz el problema que tenemos sierra. Aquí hay uno de registros de llamadas, que en realidad tiene alta tasa de fallos. Él rastreó problema hasta algunos obsoleto integraciones que todos sigue activo en el sistema.
</details>

有趣的是，它还展示了其他一些我们通常会据以展开调查的历史版本原因。当时 GCP 运行恰好发生了一次故障。所以，这本来会是一个绝佳的巧合，对吧？

<details><summary>Original English</summary>
Lo interesante es que él también muestra algunos otras versiones antiguas las razones por las que nosotros normalmente comenzaría investigación. En que Hubo un fallo en el momento justo. en el trabajo de GCP. Entonces, esto es sería ideal ¿Coincidencia, verdad?
</details>

回到旨在提供一致答复的 AI 上。那天 GCP 确实在那个确切的瞬间发生了故障。当然，这完全可能是我们所观察到现象的原因；抑或是存在其他流量激增，它察觉到这是因为缺失了集成。这本来会是它顺藤摸瓜的另一条线索。

<details><summary>Original English</summary>
Volviendo a la IA, que está diseñado para proporcionar consistencia respuestas. Por lo tanto, GCP falló ese día. en ese preciso instante. Por supuesto, esto esa puede ser la razón que nosotros Estamos observando. ¿O hay? otros picos de tráfico, lo que él siente debido a la falta de integración. Esto sería otro hilo para el cual comenzaría a tirar.
</details>

假设我是一名刚开始工作的新工程师，而 Resolve 给出了这个作为主要根因。当然，我们也开发了一套系统，使其按照最小信任原则运作。所以，如果我开始高亮选中相关项，它会引导我，以便我能进行更细致的调查。

<details><summary>Original English</summary>
Digamos que soy nuevo. ingeniero que empieza trabajo y Resolve emitió esta como la causa principal. Por supuesto, nosotros también desarrolló un sistema para que ella trabajó para principio confianza mínima. Entonces, si empiezo resaltar elementos, Él me atraerá, para poder ser más detallado Investiga esto.
</details>

在这种情况下，假设我们问问 Resolve：“这是由 GCP 的运行故障导致的吗？”答案就在这里，但还有其他一些我提出的、想和大家分享的具体问题。当时同时还发生过其他部署错误，这也是我追问 Resolve 的地方。

<details><summary>Original English</summary>
En este caso, supongamos, Preguntémosle a Resolve si Esto se debe a un fallo de funcionamiento. ¿En GCP? Entonces, él da La respuesta está aquí, pero hay otras preguntas específicas, que lancé y quiero para compartir con ustedes. También hubo otros errores. despliegue que ocurrió el mismo día tiempo. Para eso estoy. Empujé la Resolución.
</details>

回到刚才所说的：如果你对任何 AI 施加足够的压力，它就会开始顺应并赞同你。而我们开发该系统正是为了让它能够反其道而行之。它给出的回答完全且仅基于其构建的因果证据链。

<details><summary>Original English</summary>
Volviendo a dicho: si tú será suficiente presionar con fuerza cualquier IA, es Comenzará contigo aceptar. Nosotros desarrolló un sistema para que ella pueda hacer esto opuesto. Ella basará su respuestas únicamente a creado por ella causal- consecuente cadena de pruebas.
</details>

既然系统有能力确立这一点，它就能给出极具逻辑性且始终一致的回答。这也使得我能够把自己的同事拉进来，从而真正变成一项协同工作。

<details><summary>Original English</summary>
Dado que el sistema capaz de establecer esto, ella puede dar muy lógico y respuesta consistente . Esto también permite Necesito involucrar a mi propia gente. colegas, para que realmente se convirtió en trabajo conjunto.
</details>

比方说，我可以叫 Anvir：“你能看一眼这个吗？”这允许我直接从 Slack 添加同事，这样我们就可以在这个虚拟的“战情室”中进行协作。

<details><summary>Original English</summary>
Digamos que puedo llamar a Anvir: o ¿Puedes echar un vistazo? ¿él? Esto permite agregar a mi colega directamente desde Slack, para que podamos cooperar en esto virtual " "sala de crisis" .
</details>

### 平台化落地与结语

这是一场简要的演示。正如我今天已经讲过的，这只是架构的一个方面。但现在架构还有另一面，即需要将 AI 转变为完全成熟的系统级产品。如果要面向用户或客户交付，就必须确保整个平台能够可靠运行。这些是需要思考的其他方面，但对此大家都已经非常熟悉了。

<details><summary>Original English</summary>
Era una ambulancia. demostración. ¿Cómo estoy? ya se ha dicho lo que Hoy hablamos —este es solo un aspecto arquitectura. Pero Ahora hay otro lado arquitectura, donde tú es necesario convertir IA para sistemas completamente desarrollados producto. Si usted quiero presentar ¿Es para el usuario o al cliente, usted debe Asegúrese de que todo funciona de forma fiable plataforma. Estos son otros aspectos que deben ser Piénsalo, pero eso es todo. ¿En qué somos todos buenos? familiar.
</details>

好了，我的发言时间到了。如果大家有兴趣了解更多关于 Resolve AI 的信息、有哪些客户正在使用以及具体的使用方式，欢迎前往我们大概是 L28 号的展位。顺便提一句，离开前别忘了去正对出口处拿那些很酷的手提袋。非常感谢大家。

<details><summary>Original English</summary>
Entonces, mi tiempo exhausto. Si usted Es interesante saberlo Más información sobre Resolve AI, sobre qué tipo de clientes tenemos utilizado y cómo Exactamente—visita nuestro stand L28, parece. Y por cierto, antes de partir, toma esos bolsas frías que Ponte de pie recto salida. Muchas gracias.
</details>