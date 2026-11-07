---
author: AI Engineer
date: '2026-10-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oixzVKMAXG0
speaker: AI Engineer
tags:
  - ai-agent
  - internal-tools
  - saas-replacement
  - optimistic-ui
  - software-architecture
title: 告别粗制滥造：如何用 AI Agent 构建媲美商业级 SaaS 的内部工具
summary: 随着 AI 编程代理普及，“SaaS 已死”的论调甚嚣尘上，但仓促生成的工具与真正打磨精良、令人愉悦的软件之间存在巨大鸿沟。Railway 工程师分享了用 Agent 重构全套内部营销与运营系统的实践，提出技术栈抽象、自动保存、乐观更新、URL 状态化及端到端验证等关键设计原则。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Mahmoud Abdelwahab
companies_orgs:
  - Railway
products_models: []
media_books: []
status: evergreen
---
### 破除“SaaS 已死”的幻象：从粗糙原型到精致软件的鸿沟

在 AI 编程助手普及的当下，“SaaS 已死”几乎成了一种普遍论调。人们开始质疑：如果只需吩咐 AI 代理（Agent）就能独立构建并维护工具，为什么还要向第三方厂商付费？然而，这种乐观叙事忽略了一个至关重要的隐性要素——随手拼凑的“半成品”与真正令人身心愉悦、打磨精致的生产力软件之间，存在着巨大的工程体验鸿沟。

为了验证内部自研的可行性，我在 **Railway** 展开了一次实践：用一套统一的自研全能工具，彻底替换掉团队原本用于市场营销的一整套商业 SaaS。该工具涵盖了 Railway 官网内容、更新日志（Changelog）与博客的管理发布，支持群发邮件、全社交媒体一键同步与多媒体资产管理；系统内部甚至集成了轻量级 **客户关系管理**（CRM: 管理外部创作者合作关系的系统）、任务追踪、发布排期日历以及实时协同编辑。从底层构建到全自动化部署，整个系统完全借助 Agent 与 Railway 平台驱动。在此过程中，我总结出了一套确保新增功能始终保持高水准与一致性的核心设计法则。

<details>
<summary>Original English Source</summary>

La gente ha estado aquí desde hace bastante tiempo. Dicen que el SaaS está muerto. En este punto es ni siquiera algunos Idea sensacional. ¿Por qué pagar? a alguien por crear y mantenimiento herramientas si ¿Puedes hacer esto? ¿independientemente? Simplemente pregunta al tuyo agente para hacer esto. Para mí hay uno elemento faltante, lo cual rara vez se menciona recuerda: esto es un gran la brecha entre el trabajo Software creado "en rodilla", y software, ¿Cómo sería yo realmente? software usado lo cual trae placer, pulido y agradable en el trabajo. I en realidad fui a un viaje para reemplazar un conjunto de productos SaaS, Quiénes somos en Railway utilizado para marketing, y solo creado universal herramienta para nosotros. Esta herramienta te permite controlar contenido para Sitio web del ferrocarril, lista de cambios y blog. Podemos úsalo para enviar cartas, simultáneo publicaciones en todos redes sociales y gestión archivos multimedia del sitio. Incluso hay un mini CRM allí, para que podamos trabajos en vía con externo creadores. Existe un sistema seguimiento de tareas y planificación lanzamientos, porque es necesario coordinar mucho cosas y horario su salida. HAY calendario, así como comentarios y edición en en tiempo real y todo Esto está construido por con la ayuda de agentes. I Yo diría que me sentí un gran avance cuando salió GPT-6, y todo funciona en Ferrocarril. Todo es automático se desarrolla y déjame te guiaré a través de principios que yo Yo solía garantía: cuando yo Estoy agregando una nueva función, ella realmente pulido y armoniza con el resto solicitud. Simultáneamente Estos son los principios que usted puedes pedir prestado y aplicar cuando creando el tuyo propio herramientas. Por lo tanto, en lugar de hablar oficina aburrida, yo decidió cambiar situación y hacer Esto está afuera. Aquí Increíblemente hermoso. Ahora estoy en Edimburgo, Escocia y esto Simplemente irrealista. I Estoy sentado en un banco, y aquí está ¡Qué vista tengo! Absolutamente maravilloso. lugar. Este formato El rendimiento es algo para mí inusual porque yo Te lo voy a decir. te sobre el camino creando nuestro propio interno herramientas y sobre conclusiones propias, pero También entiendo que El paisaje está cambiando muy, muy rápido. Entonces, todo lo que digo, puede completamente cambiar en cuestión de minutos meses. ¿Quién sabe? Entonces, No sé. Considere esto mi advertencia. Pero la grabación se realizó en otoño. 2026. Ahora Octubre. Eso es todo. Por lo tanto, habiendo terminado con esto, Pasemos al primero. punto:

</details>

### 技术栈抽象依然关键：给 Agent 提供可靠的基石与规范约束

许多人鼓吹在 AI 时代编程语言和框架已不再重要，认为只要交给 Agent，任何技术栈都能跑通。但工程实践表明：**技术栈选择不仅依然重要，而且直接决定了系统的上限**。当你构建的是每天都要高频使用的高保真工具时，为 Agent 提供一套具备可靠**抽象层**（Abstractions: 封装复杂底层逻辑的高内聚代码架构）的基础代码库至关重要。

当代码库具备清晰的模式与约束时，Agent 在实现新功能时便无需每次“重新发明轮子”，而是严格遵循现有架构规范，产出高度一致的代码。在现代 Web 资源与内容管理场景中，**Payload CMS** 展现出了极高的抽象设计水平。虽然完全可以让 Agent 从零手写一个 CMS，但借助成熟的脚手架与抽象库，能让系统在扩展时规避大量低级架构缺陷，形成稳定可靠的演进基础。

<details>
<summary>Original English Source</summary>

pila tecnológica Todavía importa. Ahora mucha gente dice, lo cual no importa, qué idioma programación o marco que lo usas porque puedes simplemente para preguntarle a su agente para crear cualquier Eso, y lo hará. Y aunque lo soy hasta cierto punto Estoy de acuerdo, me di cuenta. es esto: cuando tú crear una herramienta quién serás realmente para usar y proporcionar al agente base de código adecuada con confiable abstracciones, en como resultado, trabajando, Digamos, sobre una nueva función, tú obtienes mucho más consistente resultado similar a lo que ya has construido más temprano. La razón es muy simple: el agente no lo hace necesario cada vez inventar la bicicleta cuando él intentando agregar nueva función o para introducir nuevos plantillas. Él simplemente seguirá plantillas existentes. Y respecto a la elección, No me parece. tan importante, siempre y cuando estás correctamente codificación estructurada base. Pero mi elección hoy es la biblioteca de uno apilar para cualquier cosa en desarrollo recursos web. Y si estás creando algo contenido relacionado Definitivamente lo recomendaría Seleccione la carga útil. Confiable una experiencia maravillosa abstracción. Soy mía. tiempo inmerso en estudio y comparación de CMS porque No creo que deba hacerlo. Vale la pena crearlo desde cero, aunque puedo. Pero claro, ¿quién? ¿Lo sabe? Tal vez en todo futuro cambiará. Pero sí, lo es. principal primero el momento con el que yo colisionaron.

</details>

### 打磨高频交互体验：自动保存、即时响应与容错防御机制

当人们仅仅作为普通用户使用商业成熟 SaaS 时，很难察觉界面背后投入了多少细致入微的交互考量。然而，一旦尝试自研日常高频工具，老旧的服务端渲染表单跳转那种生硬、阻滞的体验便会彻底暴露。若想让软件具备“高级质感”，必须主动指示 Agent 实现一系列常规提示词不会自动生成的现代交互模式：

1. **静默自动保存与离开保护**：文档与内容编辑器必须具备后台自动保存能力，绝不能强迫用户频繁手动点击“保存”。同时，在存在未提交更改时触发浏览器标签页防误关保护，构成双重防丢屏障。
2. **乐观更新**（Optimistic UI: 界面在网络请求发出前立即呈现操作成功状态，后台异步完成同步）：消除无休止的 Loading 等待圈，实现即时、丝滑的操作反馈；仅在网络失败时执行静默回滚并弹窗警示。
3. **撤销优先于二次弹窗确认**：传统的“点击删除 -> 弹出确认弹窗 -> 确认删除”严重打断心流。优雅的做法是立即从界面移除该项，同时展示带有倒计时提示的操作撤销栏（Undo Toast），为用户提供纠错窗口。
4. **归档机制替代物理删除**：避免粗暴的物理删除，在系统全生命周期中引入归档（Archive）与解包恢复能力，确保搜索与主视图保持精简的同时数据永不丢失。
5. **URL 状态持久化与无限滚动**：将筛选条件、排序规则及视图参数完整映射到 **URL 参数** 中，确保团队协作时能实现毫秒级的状态复现与无缝共享；在数据呈现上采用平滑的**无限滚动**（Infinite Scrolling）机制取代繁琐的分页按钮。

<details>
<summary>Original English Source</summary>

Cuando tú usar muchos productos SaaS, que te guste y qué vas a usar todos los días Como usuario, usted poco te das cuenta. Pero cuando estás intentando para reproducir tal experiencia, rápidamente ¿Entiendes cuánto? preocupaciones y pensamientos invertido en varios procesos. Por ejemplo, algo simple como: "Oh, Quiero tener capacidad de enviar correo electrónico o publicar algo." Esto es fácil de hacer para con la ayuda del anciano buena aplicación con renderizado en lado del servidor y los formularios que usted enviar. Pero si lo intentas crear algo que se utilizará ¿Qué haces cada día? ¿Lo harás a menudo? para contactarte, piensas: "Oh, esto no debería ser así para sentir." Hay todo una serie de plantillas que, como pude observar, los agentes normalmente no usado si No se lo dices directamente. pregunta, y aquí está la mía lista. Así que nosotros Vamos a repasarlos. uno por uno. Y el primero —Esto es guardado automático. Descubrí que si yo, Digamos que creo algún editor documentos, guardado automático—esto función básica, sin lo cual es indispensable. Entonces en lugar de presione manualmente "guardar", simplemente Solicitar el sistema automáticamente mantener el progreso en en el fondo de no bloqueó trabajar; Sí, puedes. continuar imprimir, y eso es todo. almacenado automáticamente. Otro un paso que se puede dar hacer—esto prohibir el cierre pestañas del navegador, si hay no salvados cambios. Entonces es como dos niveles de protección que garantizar que lo que está arriba ¿A qué te dedicas? Definitivamente no desaparecerá. Tú tú también puedes ir más y agregar cooperación en en tiempo real para era posible editar documento simultáneamente. Y de nuevo sí, mi agente sin ningún esfuerzo se enfrentó agregando esto funciones. Fue algo. como una solicitud, discusión de cómo Esto funcionará y luego, después de 700 millones de tokens, en Tengo una rutina. tiempo real. En general, diría que que esto es lo primero, con ¿Qué agentes son malos? enfrentarse con vista del supermercado experiencia. Otro plantilla, sobre la cual agentes completamente olvida esto optimista renovación. En cambio para demostrar a un grupo de usuarios indicadores cargando en cada acción, tú mostrarles el estado éxito-"optimista"—y en sincronización en segundo plano los cambios que hicieron. Si la sincronización o funcionamiento con cualquier Sin motivo alguno Acabas de tener éxito cancelar la acción y informar usuario: "Oh, "Algo salió mal." Por supuesto, no merece la pena. aplicar a ciegas optimista Actualizaciones por todas partes. HAY escenarios en los que es mejor espectáculo al usuario indicador carga y esperar confirmación de que todo tuvo éxito. Pero en general, optimista Se están realizando actualizaciones interfaz significativa más rápido, más ágil y él se rinde instante. Así que yo Estoy seguro de que puedes simplemente para preguntarle a su agente: "Oye, quiero implementar optimista Actualizar dónde está adecuado. Vamos. "Hagamos un plan." Y él te dirá todos los lugares donde Eso tiene sentido. De nuevo Sí, el agente no lo hace. es difícil construir. Tú solo necesito preguntar y para saber exactamente qué Solo pregunta. En el mío opinión, continuación ideas optimistas Se proporcionan actualizaciones usuarios oportunidades cancelar ciertos comportamiento. Aquí, por ejemplo, si preguntas Agregue a su agente posibilidad de eliminación registros, él normalmente creará un botón eliminación: tú Presionarlo, tal vez aparecerá una ventana confirmación, usted prensa "confirmar", y luego La entrada ha sido eliminada. Pero mucho una experiencia más agradable para el usuario será opción de cancelar esta acción. Entonces, ellos haga clic en "eliminar", al instante eliminar un elemento de interfaz, pero diles: "Oye, tienes varios segundos para cambiar "Tu decisión." Y si no son nada hacer, significa, lo que realmente quieren borra la cosa y luego estás haciendo esto operación. En otro en caso de que haga clic en "cancelar", tú solo Devuelva todo tal como está. era. Es como tú realizar una operación en modo segundo plano. Él simplemente pospuesto acción que nos derriba al siguiente punto —archivo. Tú vale la pena preguntar agregar agente posibilidad registros de archivo y desempaquétalos atrás, porque a veces necesita completamente ocultar algo de interfaz o, digamos, con resultados de búsqueda y archivar—eso es todo una forma de hacerlo. No debes fuerza El usuario piensa: « Bueno, si no lo quiero para verme, yo tendrá que hacer esto eliminar". Lote La mejor experiencia es solo tengo posibilidad registros de archivo. Por lo tanto, creo que esto El patrón es obligatorio debe serlo. Otro importante para mí momento—este es el estado de la URL-direcciones. Tienes para preguntarle a su agente para almacenar estado en la URL cuando Esto es, por supuesto, apropiado. Esto es extremadamente útil porque cuando tienes, digamos, lista de registros, y usted ¿Los quieres? filtro o Ordenar por un conjunto de condiciones, preservación de estos parámetros en la URL-La dirección permite es fácil transmitirlos a otra persona; y luego otro miembro del equipo podrá ver con claridad lo que querías para él para mostrar. Y una más un pequeño detalle que Los agentes no implementan "fuera de lo común" es infinito desplazándose. No quiero sigue presionando "descargar más" o botón "siguiente" página". Durante datos de desplazamiento debe para ser cargado automáticamente. No tienes que pulsar "página siguiente." Y Al final simplemente Ya veré: "Oh, he llegado" hasta el final". Esto es muy una cosa pequeña, pero cuando usted usa algo todos los días, yo Creo que tiene que ser de gran importancia.

</details>

### 统一设计规范与技能注入：让系统维持高度一致性

在规模化构建过程中，Agent 最大的通病是缺乏全局上下文意识，极易产出风格各异的孤岛模块。解决这一问题的有效策略是：**明确命令 Agent 将既有的成熟页面作为基准样本（Reference Spec）**。无论涉及界面布局、数据抓取契约还是操作流转，强制复用已有模式，能大幅降低错误率，确保模块间风格的一致连贯。

更进一步的做法是将工程偏好固化为 Agent 的专属**技能集**（Skills / Custom Instructions）。在构建这套营销工具时，我常态化激活了三类核心能力：
* **界面与工程规范技能**：定义排版字体、间距栅格与友好统一的错误边界提示。
* **交互动效工程技能**：封装流畅过渡动画与微交互逻辑。
* **基础设施平台技能（Railway Skills）**：让 Agent 直接掌握与 Railway 基础设施通信的能力，自主调配对象存储桶、数据库实例、服务编排及环境配置。

<details>
<summary>Original English Source</summary>

Otra plantilla que, como he notado, significativamente mejora el resultado—Esto es una clara indicación agente usar páginas existentes como enlace. Él preocupaciones interfaz, adquisición de datos, principio de funcionamiento y estructura general, lo cual me permitió determinar una vez, ¿Cómo debería verse? resultado de calidad y entonces simplemente repetidamente usa esto para otras funciones. Para ser sincero, a veces incluso cuando Le dices al agente: "Usar página de acceso como muestra", él solo no hace esto. No Sé que si se convierten modelos a veces "más estúpido", pero tal Realmente sucede. Sin embargo, en general yo... dijo que el mío tasa de éxito más alto cuando pregunto agente: "Usar página existente como muestra, porque es proporciona más coherente costumbre experiencia. Sí, durante usar programa que piensas: "Ah, es verdad." coincide con otro parte de la aplicación". Si tienen un concepto común, por ejemplo, si dos partes de la aplicación—Estas son listas de registros, que se pueden crear, actualizar, eliminar o para ver, entonces deberían ser casi idéntico. Él me lleva a Siguiente punto: cuando tienes el tuyo propio preferencias por algo, valen la pena diseñar como habilidades del agente. Entonces tu agente cuando algo creará, será bastante claramente para seguir estos habilidades. Crear toda nuestra interna herramientas, yo entendió que A menudo recurro a hasta tres habilidades agente. Dos de ellos relacionado con el diseño-ingeniería. Primero simplificó la creación mejor interfaz, fuentes, diseños y también generalmente el mejor mensajes sobre errores. El segundo es conjunto de habilidades de diseño ingeniería, gracias a lo cual se ha vuelto más fácil implementar lo mejor animación y similares cosas. Bueno, por supuesto, último en la lista, pero no en importancia —Habilidades de agente ferroviario. Todo lo que creé para nosotros en Railway, trabajamos en El ferrocarril en sí, por supuesto, absolutamente todo. Eso es cubos, bases de datos, la propia aplicación, servidor real El tiempo lo es todo. Para el agente podría ser efectivo trabajar con el ferrocarril y para desplegar todo necesario, solo darle habilidades Ferrocarril, y él lo afronta. Y Sí, solo tú configurar todo habilidades del agente, en mi opinión, final y la etapa más importante Hay un control.

</details>

### 闭环验收与真实端到端测试：构建经得起考验的生产力工具

整个构建闭环中最关键的最后一步，是**严格的端到端环境验证**。传统工作流中，Agent 往往在完成静态类型检查和单元测试后便草草宣称“构建成功”，但实际运行往往漏洞百出。必须对 Agent 建立严格的验证契约：要求其利用真实基础设施完成真正的**端到端测试**（End-to-End Testing: 模拟真实用户与生产环境的完整流程验证）。

当赋予 Agent 自主执行真实测试与排错循环的权限后，你会观察到质的飞跃：Agent 会自主尝试部署、在真实环境中捕获异常、反思并修复缺陷，直至全流程彻底通畅。唯有将底层抽象、高阶交互模式、统一技能规范与严格端到端验证结合起来，我们才能摆脱粗制滥造的原型玩具，真正用 AI 构建出稳定可靠、充满愉悦感且能匹敌顶级商业 SaaS 的内部工具。

<details>
<summary>Original English Source</summary>

Por lo tanto, agentes usualmente cuando les pides algo crear, dicen: "De acuerdo, ya lo implementé. función, ensamblaje exitoso, pruebas Aprobado, todo está bien, ¿Verdad? Pero yo notaste que cuando tú de hecho de cheques como resultado, a veces te pones muy experiencia no laboral. Entonces cuando tienes la menstruación controles, diferencia se vuelve llamativo porque literalmente lo ves, como dice el agente, "De acuerdo, Yo lo creé. Yo soy esto. Lo probé. No lo es Funcionó. Yo soy esto. "Yo lo arreglaré." Y él continúa trabajando, y al final dice: "De acuerdo, Estoy totalmente de acuerdo. protestó." Y yo sentí este avance en usar computadora cuando se volvió realmente muy, Muy bien Y ahora, cuando yo quiera agregar una nueva función, Solo digo al final: "Bueno, tienes comprobar si La función funciona desde de principio a fin, usando real infraestructura para de principio a fin pruebas". Y agentes bastante capaz de esto hacer. Tú solo tengo que decírselo. Y cuando tienes todos estos elementos, diría yo, Obtendrás confiabilidad interno herramientas que se puede hacer rápidamente crear, que funciona correctamente de forma estable. Eso es todo. Este era mío. lista de principios, que yo uso, cuando creo alguno interno herramientas. Espero que lo fueran útil para ti, pero más importante aún, te inspiró crea el tuyo propio interno herramientas que agradablemente para usar, que son perfecto y traer alegría. Y Espero que tú tú también puedes convertirte Nivel SaaS de su empresas. En esto Gracias por ver, y nos vemos en Siguiente video.

</details>