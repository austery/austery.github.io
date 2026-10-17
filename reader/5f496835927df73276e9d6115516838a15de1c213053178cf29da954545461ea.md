---
author: AI Engineer
date: '2026-10-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=eXA2tjRZIbY
speaker: AI Engineer
tags:
  - autonomous-agents
  - incident-response
  - context-engineering
  - causal-reasoning
  - agentic-evals
title: 生产环境运维智能体的六大支柱架构
summary: Resolve AI 联合创始人 Varun 深入剖析了生产系统自治运维的技术难点，指出从代码辅助走向生产运维（On-call）的本质区别。针对大模型在运维场景下的偏见固化、上下文过浅及破坏性操作风险，系统性阐述了生产级智能体系统的六大核心支柱：模型编排、上下文工程、因果推理、受控防护、学习闭环与系统化评估。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Varun Krovvidi
companies_orgs:
  - Resolve AI
  - Microsoft
  - Google Cloud Platform
products_models:
  - Claude
  - GPT-4
  - Gemini
  - Grafana
  - Slack
media_books: []
status: evergreen
---
### 运维范式转移：从代码生成走向自治生产运维

现代软件工程的第一波 AI 浪潮主要集中在代码补全与辅助编程领域，这从根本上重构了工程师编写代码的方式。代码本身具有极强的自解释性与高度模块化特征，属于单一领域的垂直系统，大语言模型无需跨越多学科知识背景即可进行确定性推理，因此评估代码辅助的效果具有清晰客观的标准。然而，当工程师试图将 AI 引入生产环境运维（**值班巡检**，On-call: 工程师负责保障生产系统高可用、排查突发故障的轮值机制）时，却发现传统辅助手段完全无法支撑 90% 以上的实际运维任务。**Resolve AI** 的创立初衷正是为了攻克这一高壁垒难题：构建能够自主排查并自动修复生产软件缺陷的智能体系统。生产环境的故障排查与维护并非孤立的代码修改，而是一个涉及多团队协同、高风险决策以及海量非结构化数据的复杂现实系统。

<details>
<summary>Original English Source</summary>

¿Están todos bien? ¿Lo oyen? Perfectamente. Muy Gracias por venir. esta sesión. Mi nombre es Varún. Soy parte de Resolver equipos de IA. Nosotros creamos IA para defenderse contra fraude. De hecho, creamos agentes para empezar y corrigiendo su software software. Pronto esta sesión nosotros Consideremos seis pilares del agente sistemas que usted será necesario para gestión y reparación tu software. Antes empezar, recoger manos para que yo entienda, ¿Quién está hoy? audiencia. Supongo, la mayoría de ustedes— ingenieros. ¿Cuántos de Has trabajado antes en modo de espera ( ¿De guardia? Levanten la mano. Perfectamente. ¿Lo intentaron? usted usa La IA ayudará yo mismo durante ¿Turnos? Elevar manos. Perfectamente. Aquellos que levantó las manos, o ¿Puedes decir eso? El 90% de tu trabajo está bajo tiempo de servicio ¿Funciona la IA? Puede Claro que sí. ¿afirmar? Perfectamente. Sí, eso es exactamente lo que somos. entendido cuando fundó una empresa. Él muy difícil tarea. Entonces en este Quiero sesiones comparte nuestro viaje, evolución, que pasamos, y nuestras lecciones en creando tal sistema de agentes. Antes de proceder a Vale, quiero describir el contexto de lo que tenemos hoy. Primera ola La IA estaba enfocada exactamente en programación. Justo diciendo, creo, para la mayoría de nosotros forma de escribir código completamente cambió. Yo también quería explicar por qué Así fue como sucedió. En primer lugar, el código en sí es autodocumentado La IA es fácil de analizar. y entenderlo, para que para ayudarte con siguiente paso. En- segundo, el código a su manera De naturaleza muy modular. Por lo tanto, la IA es fácil rómpelo en pedazos partes, mover a la siguiente etapa, y también para ayudar te expandes y construir sobre ello base. En tercer lugar, y esto Lo más importante es el código. esfera de dominio único. No necesitas hacerlo enseñar IA a muchos disciplinas para que él podría razonar dentro de los límites uno. Él es fácil está orientado hacia próximos pasos y Por eso tenemos indicadores tan claros eficiencia. Tú ¿Puedes objetivamente? para evaluar cuánto Bueno, la IA resuelve estos problemas.

</details>

### 生产系统的工程鸿沟：精度、成本与多主体协同

当技术演进迈入第二阶段，行业开始直面 AI 生成代码进入生产环境所带来的海量衍生问题，无限 Token 的无节制消耗时代已然终结。将智能体部署至生产系统必须攻克三大工程维度的严苛约束：首先是**工程严谨性**（Engineering Rigor: 确保系统在长链路排障中保持极高推导精度而非幻觉概率），生产系统无法承受概率性猜测带来的停机风险；其次是**Token 经济学**，构建智能体必须在有限的上下文开销与精确执行之间取得平衡；最后是**多主体协作属性**（Multi-player Dynamics: 涉及 SRE、平台工程、后端研发等多角色的协同决策），排障绝非单人游戏，AI 必须在一个动态、分布式且多角色的认知网络中运作。通用基础模型是为广泛认知设计的基石，若缺乏针对生产系统专门设计的智能体架构，AI 绝无可能自主驾驭复杂的生产故障。

<details>
<summary>Original English Source</summary>

Pero cuando estamos yendo a sistemas de producción, entonces Aquí todo cambia radicalmente. En los últimos dos o tres meses Vimos un cambio en esto área. En primer lugar, tales las empresas como Cursor y Cognition comenzaron hablar sobre temas similares en noticias. Más están hablando de número de problemas, que puede crear código de IA generado en producción y discutir cuál Los marcos de trabajo son los mejores adecuado para resolver estos problemas. En segundo lugar, la era IA ilimitada ha llegado a su fin. Todo el mundo ahora entiende que las fichas tienen un límite. Cada ficha cuesta dinero y eficiencia fichas. ¿Cómo puedes? mejorar estos arquitectura, esas ingeniería rigurosa soluciones que se necesitan para una eficacia y uso preciso ¿AI? Y el tercer momento— recientemente fue entrevista muy interesante general al director de Microsoft, donde Habló de arquitectura, el piso requerido modelos convencionales para cualquier trabajo altamente especializado AI. Entonces, estos tres factores indican que ahora es un momento muy oportuno hora de hablar de arquitectura agentes cuando esto refiere a tu producción sistemas. En general, Nuestra empresa Resolve AI comenzó su actividad de uno tesis. Creemos sinceramente, que todo este trabajo que tú actúas en sistemas de producción, como la corrección errores o diarios mantenimiento de software, totalmente se puede automatizar con agentes de IA.

</details>

### 原生智能体的系统裂隙：偏见固化与上下文缺失

构建面向生产环境的自研智能体时，初期的原型演示（Demo）往往表现惊艳，但一旦推向跨团队、跨系统的真实生产规模，架构的裂缝便会迅速暴露。第一大痛点是**模型固有偏见**（Model Bias & Anchor Effect: 大模型倾向于过早锁定最初看到的蛛丝马迹，并在错误方向上持续自我强化），模型极易产生认知锚定，沿着伪相关线索越陷越深；第二大痛点是**浅层上下文与盲目探查**（Shallow Context: 因缺乏全局系统拓扑与高精度观测数据而陷入臆断），模型无法洞察关键数据链路，往往在次要表象上浪费海量资源；第三大痛点是缺乏受控的安全防线，模型可能判定最彻底修复系统报错的方法就是直接执行 `DROP TABLE` 或清空文件系统；最后是**缺乏跨时空学习闭环**，面对涉及 SRE、平台与业务研发的多轮事件响应，缺乏统一的历史上下文沉淀，导致 AI 在每次面对同类事故时都只能从零开始盲目摸索。

<details>
<summary>Original English Source</summary>

Y cuando construyes tu propio sistema Además de eso, Resulta muy bien demostración. Pero gradualmente, cuando tú empiezas escala entre diferentes escenarios uso y equipos, aquí mismo y comienzas a notar grietas. ¿Y cuáles son estas grietas? vimos cuando tú tú empiezas escalar el producto ¿En este camino? Primero, Lo que notarás es que que modelos, por supuesto, tener prejuicios encuadernaciones. Esto es muy algo importante con lo que tienes que lidiar tiene que afrontar. Modelos tienden a tener un gran prejuicio sobre ciertas cosas. Por lo tanto, si la IA ve algún tipo de evidencia, él simplemente comenzará profundizar en ellos. Y se moverá en esta dirección hasta que encuentra una solución, que él mismo considera correcto. O él simplemente se atascará y lo hará continuar profundizando en uno y el mismo madriguera de conejo. ¿Con qué frecuencia lo haces? te diste cuenta de cómo La IA se atasca en el código. y no puedo salir ¿de este? Esto se debe a cómo fueron entrenados. Y segundo— este contexto. Si tú proporcionas muy contexto limitado, por supuesto que ellos " "Están poco investigados." No podrán para ir al grano, en no serán visibles de los que existen formas o qué más hipótesis potenciales puede existir para resolución de problemas. Especialmente si esto concierne a tu código y sistema, no solo conectado respuestas. Y el siguiente , por supuesto, es medidas de precaución. I No seré demasiado. detente aquí tema, pero todos lee las noticias sobre como la inteligencia artificial elimina una cierta sistema de archivos o base de datos. Entonces, para La IA también es una función, ¿No es así? Y no error. La IA podría decide que lo más puro posible La corrección es eliminación simple este en particular fragmento de código. Usted no puedes culpar Él por esto. Tú solo es necesario construir precauciones alrededor del sistema para ella trabajaba adecuadamente. Cual nivel mínimo Se requiere acceso IA para el trabajo en cualquier a la cual se le dio ¿Escenarios? Y el último— ciclos de aprendizaje. Cualquier- ¿Qué sistema tienes? construir, debería ser escalable para tu equipo o toda la organización en a lo mejor. Siempre que utilizando IA para producción incidentes como yo dijo al principio, esto multijugador problema. Tiene muchos equipos diferentes, como SRE, plataforma equipos, backend- ingenieros o ingenieros de servicio. Todas estas personas deben estar involucrado. Y lo más importante, todos estos la gente debería tener mismo contexto. Ahora que usted agregar a esto discusiones de tiempo, tu El sistema de IA debería tener lo mismo contexto anterior investigación sobre investigación número cien de lo contrario lo harás cada vez Empiezas desde cero. Estos son los modos negativas, donde vimos, ¿Cómo se ven? grietas.

</details>

### 生产级智能体 Harness 的六大核心支柱

为化解上述裂隙，必须超越单一提示词工程，建立一个专为特定运维领域设计的智能体系统架构（**智能体运行支架**，Agentic Harness: 包裹、约束并赋能底层模型与外部环境交互的运行时框架）。该架构由六大关键支柱紧密啮合构成：

1. **动态模型编排**（Dynamic Model Orchestration）: 解决模型生命周期与能力适配问题。一方面实现对最新大语言模型的无缝热拔插，另一方面针对任务特征实施路由编排——例如调用 **Gemini** 分析系统架构图与监控面板图像，调度 **OpenAI** 执行严格确定性的工作流步骤，利用 **Claude** 展开发散式的全局根因假设探查。
2. **多模态上下文工程**（Context Engineering）: 告别粗暴单一的向量检索或 GraphRAG 堆砌，核心在于精准计算排障所需的最小充分上下文集合。在初始排查阶段通过知识图谱定位异常服务，进入执行排查时则实施精确的受控工具调用（Tool Calling），避免在查询海量分布式日志、指标指标流或代码库时瞬间耗尽 Token 窗口。
3. **因果推理链机制**（Causal Reasoning）: 确立以证据链为核心的根因推导原则。智能体必须还原出触发事故的完整时序与因果路径；若证据链出现断裂，系统必须主动降低可信度评分（Confidence Score）并指引工程师介入，坚决杜绝无证据支撑的臆测。
4. **受控行为与动态安全防护**（Guardrails & Controlled Behavior）: 结合组织细粒度权限控制、合规限制与行业基准，构建智能体的权限防火墙。明确界定哪些日志可直接读取、敏感数据何时脱敏，以及阻断任何危险的写入与删除操作。
5. **人在回路的学习反馈闭环**（Learning Loops）: 将每次排障交互转化为系统进化的燃料。记录工程师对推断结果的正向确认、负向反馈及路径修正，使智能体系统在经历第 100 次排障时具备前 99 次累积沉淀的组织特异性上下文。
6. **全生命周期系统化评估**（Systematic Agentic Evaluation）: 贯穿智能体架构起点与终点的多维评级体系。建立五级基准指标，量化比对 AI 的排查轨迹与资深主任工程师的最佳实践，校准置信度评级，并在底层模型迭代或架构升级时提供严谨的回归基准。

<details>
<summary>Original English Source</summary>

Por eso nosotros creó una agencia arquitectura que responde exactamente estas pregunta. Entonces, hay seis principales piezas para cualquier arquitectura de IA, que debería funcionar en un dominio específico áreas. Razón, ¿Por qué menciono? específico del dominio área, consta de porque los modelos destinado a pensamiento general. Ahora, cuando quieras para dirigir estos modelos en un específico respuesta, tú necesito cuidar de seis pilares diferentes. El primero es orquestación de modelos. Como ya mencioné, orquestación de modelos consta de dos niveles. Primero: ¿cómo estás? ¿Llegas a tiempo para...? actualización constante modelos y usando ¿El más nuevo de ellos? Y En segundo lugar, ¿cómo? elige el mejor modelo para tarea específica ¿ Quizás Géminis para ¿Análisis de imágenes? O OpenAI para determinista ¿pasos? ¿Es posible? Claude para abrir ¿investigación? Tú debe constantemente evaluar qué modelo es lo mejor para finalización de tareas en momento específico. Entonces, este es un mecanismo, que creamos a partir de desde el principio. Segundo —esto es contextual ingeniería. Ahora ingeniería de contexto a menudo reducido únicamente a bases de datos o solución para implementación. Oh, tú ¿Estás utilizando el gráfico RAG? Usted usa ¿Gráfico de conocimiento? Tú usar X, Y y ¿Z? Todo reside en los detalles. implementación. Pero la pregunta principal en ¿Cuál es el volumen exacto? Se necesita contexto La IA para resolver esto problemas. Y con mayor frecuencia esto combinación de diferentes métodos. Tal vez tú tendrá que usar solución de tipo gráfico RAG, para que la IA pueda comenzar investigación. ¿Y cuándo? vas a próximos pasos, usted necesidad de determinar llamadas muy precisas herramientas para no gastar fichas demasiado rápido bajo tiempo de ejecución consultas de registro, métricas, paneles o código, etc. El tercero es causal consideración. Como ya dijo que era uno de fundamental principios que nosotros Integrado en Resolve AI: la causa raíz siempre Residencia en cadena de pruebas. Cual fueron los pasos que condujeron a este en particular ¿Problemas? Si no lo hacemos podemos instalar esta cadena, nosotros tenemos que proporcionar información con bajo nivel de confianza y dirigir usuario a otro lado. Esto se aplica a cualquier IA especializada, incluyendo Resolve AI: nosotros te estamos redirigiendo, si no vemos los datos Después de cierto punto. A continuación, como ya he dicho dijo: "Está controlado" comportamiento. Es bastante sencillo. Depende de cada equipo, cada organización, niveles de acceso, restricciones o industrias, en el que trabajas. ¿Cuáles son los específicos? Se requieren fusibles determinar para el trabajo ¿AI? ¿Esto es lectura? Él ¿registro? Y si el registro, ¿Cuáles son las condiciones para existe, etc. Y El último es el sistema enseñanza. Piénsalo. sobre ello de esta manera. Cada uno de ustedes interacción con el sistema La IA es una oportunidad para enseñanza. Por lo tanto, sistema de inteligencia artificial La inteligencia tiene aprender no solo en el proceso en sí investigación, pero también en porque como usuario interactúa con él. Por ejemplo, ¿debo proporcionar? positivo para ti ¿apoyo? Por lo tanto, ¿Esto convierte? ¿Para una evaluación positiva? ¿Te doy? negativo ¿apoyo? O Te guiaré o Yo te guiaré investigación sobre ¿Una dirección determinada? Él diferentes tipos evaluación. Él nos lleva a la última parte, donde La evaluación también es una etapa muy importante. Este es el comienzo y punto final para cualquier arquitecturas de agentes. Estamos considerando calificación de cinco puntos diferentes niveles, como yo Ya lo mencioné. Qué positivo refuerzo para ti ¿Puedes proporcionarlo? Qué negativo refuerzo para ti ¿Puede usted proporcionarlo y si ¿Podemos rastrear? ¿Cómo estás? ¿Ya has tomado una decisión? ¿Podemos estimar? usted, como ingeniero, en ¿En base a esto? Como si mejor ingeniero lo gasté investigación y cómo te comparas con él ¿ Y además, ¿cómo lo haces? Calibre usted mismo como ¿inteligencia artificial? Como tú defines esto ¿Nivel de confianza? Todo esto es sistemático. las calificaciones que construir en uno plataforma, y ​​ cuál constantemente necesario referirse a arquitectura, cuando aparece uno nuevo modelo, nuevo caso usar o cambios arquitectura. Empinadamente. Basta de hablar. Déjame mostrar cómo es funciona en Resolve en práctica.

</details>

### 实战推演：从 Grafana 告警到虚拟作战室的自主排障

在真实的系统实操演示中，**Resolve AI** 直观展示了六大支柱协同运转的具体流程。监控系统 **Grafana** 触发错误率暴增告警并自动推送到内部的 **Slack** 协作频道。Resolve 智能体实时捕获该告警事件，无需人工介入即可启动自动化根因排查。智能体首先分析日志分布并识别出异常的对数级错误激增，顺藤摸瓜检索关联的分布式链路跟踪；进一步比对代码提交历史时，系统敏锐捕获到当时正处于代码冻结期（Code Freeze），排除了近期发版引入缺陷的假设。

智能体随即展开跨维度关联排查，实时比对底层基础设施监控与外部服务状态，精准定位到该时刻 **Google Cloud Platform**（GCP）底层基础设施发生瞬时故障，导致网络连接中断。在锁定外部因果证据后，智能体在协作界面中生成具备置信度评估的排障报告，并支持直接在 Slack 线程中 @ 调用其他领域的工程师（如 Anvir），一键组建多角色协同的**虚拟作战室**（Virtual War Room: 在发生重大生产事故时，多部门技术骨干快速会商、共享上下文并执行恢复操作的应急协作空间），实现从告警触发、证据链构建到人机协同处置的完整自治闭环。

<details>
<summary>Original English Source</summary>

Como ya dije, el punto de partida es notificaciones herramientas para colaboración, como Slack, Microsoft Teams u otros, ¿Cómo eres? usar. En este caso que vemos cómo Grafana envía notificación en nuestro Canal compartido en Slack. Resolver automáticamente recoge estos notificaciones y comienza investigación. Tú ya ves que el sistema informes sobre error de escala logarítmica y comienza a profundizar en los registros. Y a medida que avanza investigación, ella empieza formular varias hipótesis. Ella ve eso ahora tiempo congelación del código. ¿Por qué es esto? importante? Porque significa que código reciente no cambió. Y ella empieza buscar fuera del código. Y luego ella ve que había un problema en el trabajo de GCP. Entonces, esto es sería ideal ¿Coincidencia, verdad? Volviendo a la IA, que está diseñado para proporcionar consistencia respuestas. Por lo tanto, GCP falló ese día. en ese preciso instante. Por supuesto, esto esa puede ser la razón. Y luego ella comienza a comparar registros con la infraestructura subyacente y ve una coincidencia. Después de este sistema Resolver problemas específicos respuesta con un cierto grado de confianza. Esto es sólo un ejemplo cómo funciona esto. Y por supuesto, puedo usar " "sala de crisis" virtual, donde puedo involucrar a mi propia gente. colegas, para que realmente se convirtió en trabajo conjunto. Digamos que puedo llamar a Anvir: o ¿Puedes echar un vistazo? ¿él? Esto permite agregar a mi colega directamente desde Slack, para que podamos cooperar en esto virtual " "sala de crisis" . Era una ambulancia. demostración. ¿Cómo estoy? ya se ha dicho lo que Hoy hablamos —este es solo un aspecto arquitectura. Pero Ahora hay otro lado arquitectura, donde tú es necesario convertir IA para sistemas completamente desarrollados producto. Si usted quiero presentar ¿Es para el usuario o al cliente, usted debe Asegúrese de que todo funciona de forma fiable plataforma. Estos son otros aspectos que deben ser Piénsalo, pero eso es todo. ¿En qué somos todos buenos? familiar. Entonces, mi tiempo exhausto. Si usted Es interesante saberlo Más información sobre Resolve AI, sobre qué tipo de clientes tenemos utilizado y cómo Exactamente—visita nuestro stand L28, parece. Y por cierto, antes de partir, toma esos bolsas frías que Ponte de pie recto salida. Muchas gracias.

</details>