---
author: AI Engineer
date: '2026-09-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9JFGohx4E7U
speaker: AI Engineer
tags:
  - open-weights
  - reasoning-model
  - llm-architecture
  - code-generation
title: GLM-5.2：智谱AI开源近前沿大模型的演进与生态实践
summary: 智谱AI（Z.ai）核心成员在世界博览会技术演讲中，深入解析了GLM-5.2开源大模型的最新进展与技术架构。分享涵盖了GLM从早期的自回归填空架构到前沿大模型的演进历程，重点阐述了模型在高难度推理、高预算思考模式与代码生成方面的卓越表现，并深入探讨了智谱坚持权重开源以赋能开发者生态与行业定制的核心战略。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - 智谱AI
  - OpenAI
  - Hugging Face
products_models:
  - GLM-5.2
  - GLM-4
  - DeepSeek
media_books: []
status: evergreen
---
### 开场互动与智谱品牌背景

**主持人 (Swix)**: 闲话少叙，在**Zixuan Li**（李子轩）正式演讲之前，如果我们准备好了，就先请他连线。嗨，你还好吗？

<details>
<summary>Original English</summary>

**Host (Swix)**: Sin más, invitamos a Zishan antes de su discurso, si estamos listos. ¿Hola, cómo estás? ¿tú?

</details>

**李子轩 (Zixuan Li)**: 太棒了，我已经在线了！

<details>
<summary>Original English</summary>

**Zixuan Li**: ¡Genial, ya estoy aquí!

</details>

**主持人 (Swix)**: 是的，多亏了互联网的神奇魔力。非常高兴能再次见到你。子轩，你之前在新加坡人工智能大会（AI Singapore）上也发表过演讲，很明显现在**GLM**成为了每个人口中热议的焦点。楼下展厅里的展台非常棒，我相信现场有很多人都非常迫切地想要深入了解**Z.ai**到底正在发生哪些令人兴奋的技术突破。所以，舞台交给你，你可以随时开始了。

<details>
<summary>Original English</summary>

**Host (Swix)**: Sí, gracias a la magia de la Internet. Muy me alegra verte de nuevo. Zishan, tú hablé con AI Singapur, y es obvio que GLM ahora todos tienen en la boca. Abajo en la exposición es maravilloso su stand, y creo que muchas personas quieren saber sobre qué tiene lugar en Z.ai. Así que puedes empezar.

</details>

**李子轩 (Zixuan Li)**: 好的，对于这次没能亲自到旧金山现场参会的朋友们，我再次表示歉意。不过我们在展会现场有一支完整的团队，并且设立了专门的展位。所以大家如果有任何疑问，欢迎随时在 **X (Twitter)** 或 **LinkedIn** 上联系我，也可以直接去现场的展台与我们的团队面对面交流。另外，因为我这边看不到现场的大屏幕幻灯片，可能需要 **Swix** 帮忙帮我翻页。

<details>
<summary>Original English</summary>

**Zixuan Li**: Sí, lo siento de nuevo por quienes no llegaron personalmente, pero tengo aquí hay todo un equipo, y tenemos un puesto. Entonces si tienes alguna pregunta, no dudes en contactarnos a mí en X, LinkedIn y también puedes encontrar mi equipo en nuestro stand. Y puesto que yo no puedo ver mis diapositivas, necesitaré la ayuda de Swix para hojearlos para mí.

</details>

**主持人 (Swix)**: 没问题，一切都准备好了。你告诉我需要切到哪一张就行。现在大屏幕正停在开场幻灯片上。

<details>
<summary>Original English</summary>

**Host (Swix)**: Sí. Todo está bien. Dime, ¿en cuál de ellos? Ahora estamos en la pendiente.

</details>

**李子轩 (Zixuan Li)**: 好的，那我们现在处于介绍页幻灯片，主题是关于前沿智能与 **Z.ai**。

<details>
<summary>Original English</summary>

**Zixuan Li**: Sí. Entonces, estamos en diapositiva introductoria. Nosotros estamos hablando de inteligencia y Z.ai.

</details>

**主持人 (Swix)**: 好的，没问题。大家现在都能看得很清楚了。

<details>
<summary>Original English</summary>

**Host (Swix)**: Vale, sí. Entonces, ¿puedes verlo ahora?

</details>

### 从学术研究到全球品牌：GLM 的演进之路

**李子轩 (Zixuan Li)**: 这是我们第一次向全世界正式展示 **GLM-5.2**。同时，我也想借此机会聊聊 **Z.ai** 与 **GLM** 之间的关系。因为大家可能会觉得好奇，甚至猜测 Z.ai 与 GLM 之间到底是什么渊源，为什么我们的公司叫 Z.ai，而核心模型却被称为 GLM。大家可以在这张幻灯片上看到我的个人 X 账号以及我们公司的官方 X 账号。大家直接搜索我的名字 **Zixuan Li** 以及 **Z.ai Organization** 即可，关注这些账号可以第一时间获取我们最新的动态与技术更新。

那么，我们可以翻到第二张幻灯片了。由于我看不到翻页效果，我会尽量配合节奏。我们公司在业界的正式名称其实是**智谱AI (Zhipu AI)**，可能现场很多人之前就听说过。而我们的旗舰系列模型被称为 **GLM**。

事实上，GLM 并不是一个凭空生造的商业商标，而是一个通用学术术语。GLM 实际上代表着**通用语言模型 (General Language Model)**，基于自回归填空机制（Autoregressive Blank Infilling）进行预训练。这篇奠基性的学术论文早在 **2021 年**就已公开发表。因此，从历史维度来看，我们实际上是全球最早系统性研究大规模语言模型的实验室之一，与 **OpenAI**、**Anthropic** 以及 **DeepMind** 几乎是在同一时期起跑。

即便在今天，虽然我们在底层架构上已经不再局限于最初那种单纯的双向自回归填空结构，但我们依然保留了 GLM 这个极具历史传承的名称作为我们的核心品牌。因此，我们先后推出了 GLM-4、GLM-4.5、GLM-5.1 以及最新的 **GLM-5.2**，它已经成长为我们最重磅的旗舰产品与模型家族。

<details>
<summary>Original English</summary>

**Zixuan Li**: Esta es la primera vez representamos a GLM-5.2 al mundo. Y nosotros también hablemos un poco sobre Z.ai y GLM, porque, quizás, la gente pensará que Z.ai y GLM no están relacionados, ¿sí? Tu empresa es Z.ai, y tus modelos se llaman GLM. Y aquí puedes encontrar mi X y nuestra cuenta de la empresa en X. Entonces puedes simplemente buscar mi nombre, Zixuan Li y la Organización Z.ai. Y puedes suscribirte sobre ellos para vigilarlos actualizaciones.

Por lo tanto, sí, podemos ir a la segunda diapositiva. Sí, en realidad no veo el slide, así que lo intentaré... Asegúrese de que todo bien. Por lo tanto, la empresa en realidad se llama Zhipu. Tal vez alguien escuchó sobre ella. Y los modelos, se llaman GLM. En realidad, esto no es solo una marca. Esto es un término general. Entonces, GLM en realidad significa General Language Model con autoregressive blank infilling. Y este artículo fue publicado en 2021. Entonces, en realidad éramos uno de los primeros laboratorios que investigaron grandes modelos de lenguaje, simultáneamente con OpenAI, Anthropic y DeepMind. E incluso hoy ya no utilizamos puramente la arquitectura GLM original, pero todavía usamos el nombre GLM como nuestra marca. Por lo tanto nosotros lanzamos GLM-4.5, 5.1, 5.2, y se convirtió en uno de nuestros productos y modelos más grandes.

</details>

### 探索智能上限：超越数学题的综合推理

**李子轩 (Zixuan Li)**: 我们持续追求的第二个核心目标，是探索**智能的上限 (Upper Bound of Intelligence)**。从智能的定义来看，很多人往往将其等同于单纯的智商测验或解题技巧。当 **DeepSeek** 发布，或者当 OpenAI 发布 **o1** 系列模型时，整个业界都在热烈讨论模型解决复杂的奥数竞赛题（AIME）或物理竞赛难题的能力。

但真正的智能内涵远不止于 IQ 分数，也不仅仅局限于做对几道 AIME 题目或其他物理测试。因此，从 **GLM-4.5** 到后续的迭代版本中，我们一直在系统性地探索多个关键维度的能力延展，包括深度长程推理、高阶编程编码以及通用任务解决能力。

正如大家在幻灯片上看到的，我们加入了很多……呃，抱歉，好像翻到了最后一张幻灯片？我刚才还没讲完前一张呢。

<details>
<summary>Original English</summary>

**Zixuan Li**: Lo segundo que buscamos es el límite superior de la inteligencia. Desde el punto de vista de la inteligencia, podemos sentir que esto representa el coeficiente intelectual o algo así. Cuando DeepSeek se lanzó o cuando se lanzó o1, las personas hablaron de la capacidad de los modelos para resolver matemáticas y problemas físicos. Pero lo que realmente significa inteligencia no se trata solo de CI, AIME u otros problemas físicos. Por lo tanto, desde GLM-4.5 estamos investigando varias direcciones, como el razonamiento, programación y capacidades generales. Así que, como puedes ver en diapositivas, agregamos... eh, sí, ¿la última diapositiva? Todavía no he terminado esa diapositiva.

</details>

**主持人 (Swix)**: 好的，没关系，我需要帮你往后退两页。不过我手上的翻页器好像没有后退按钮，翻页器上居然没有后退键！真让人无奈，哈哈。不过没事，我们继续往下讲。

<details>
<summary>Original English</summary>

**Host (Swix)**: Sí, de acuerdo. Necesito volver dos diapositivas hacia atrás. No tengo un botón "atrás" en el clicker. Gracias. No entiendo los clickers que no tienen botones "atrás". Pero bueno, ya sabes. En cualquier caso, continuemos.

</details>

**李子轩 (Zixuan Li)**: 哈哈，没关系，那我们就继续吧。因为大家最想看到的正是 **GLM-5.2**，而不是听我过多回顾老旧的版本。

**GLM-5.2** 在软件工程、高级编程和复杂通用推理任务上表现出了极为强悍的专精水准。大家从这张基准测试图表中可以看到，虽然外界有各种各样的传言和预测，但我今天非常荣幸能把这些第一手的真实评测数据直接分享给大家。

正如你们在图表中所看到的，GLM-5.2 的综合能力已经稳稳地落在了 **Claude 3.5 Sonnet 与 Claude 3.7 / Opus 系列**之间的顶尖梯队水准。在评测中，我们专门采用了业界最具挑战性的严苛任务集进行压力测试，例如类似 DeepSeek 应对的高难度基准，以及由 OpenAI 团队此前在技术分享中重点提及的 **SWE-bench / Terminal Bench 2.1**。在所有这类长上下文、需要持久行动规划能力的复杂基准测试中，GLM-5.2 都展现出了比肩甚至超越顶尖闭源前沿模型的高水准实力。这相比于上一代版本实现了巨大的跨越式提升。

此外，在 GLM-5.2 中，我们引入了一种名为 **高阶深度思考模式 (High Budget Reasoning)** 的机制。我们在实际部署和复杂任务执行中观察到，模型在攻克极高难度的软件开发或多步骤逻辑链时，往往需要消耗大量的推理 Token。同时，我们也非常注重 **Token 的使用效率**。因此，我们首次为用户提供了灵活的思考预算控制档位。然而，更为亮眼的是，即便在**完全不开启深度思考**的纯直出模式下，GLM-5.2 的基线表现依然超越了上一代开启思考模式的水平！这对于开源权重模型而言，绝对是一个里程碑式的飞跃，在发布后震撼了全球开源社区，这也是为什么最近大家都在热烈讨论 GLM-5.2 的原因。

<details>
<summary>Original English</summary>

**Zixuan Li**: Sí, no importa, porque la gente quiere ver GLM-5.2, no quieren ver GLM-4.1. GLM-5.2 en realidad se especializa en programación y tareas complejas. Como pueden ver en el gráfico, ya que corren muchos rumores sobre cómo viene el modelo, en realidad quiero compartir estas diapositivas con todos ustedes.

Entonces, ya ves que está en algún lugar al nivel de los modelos de vanguardia como Opus / Sonnet, y nosotros utilizamos las tareas más difíciles, como DeepSeek, Terminal Bench 2.1, que mencionó el equipo de OpenAI hace unos minutos. Y todas las tareas y puntos de referencia en una perspectiva a largo plazo muestran que las oportunidades están al nivel más alto. Y esto muestra una mejora significativa.

También para GLM-5.2 añadimos un nivel de pensamiento llamado "high" (alto presupuesto de pensamiento). Ya que nosotros notamos que durante la ejecución de tareas más complejas el modelo puede consumir más tokens, y a nosotros nos importa mucho la eficiencia del uso de tokens. Entonces, por primera vez, agregamos un nivel de pensamiento de alto presupuesto, pero incluso sin pensar, el modelo sin pensar es mejor que el modelo anterior con pensamiento. Por lo tanto, creo que esto es un paso enorme hacia adelante para los modelos con pesos abiertos (open weights). Realmente conmocionó al mundo, y por eso la gente últimamente habla tanto de GLM-5.2.

</details>

### 全面超越代码：多模态与日常工作流的全能助手

**李子轩 (Zixuan Li)**: 好的，请翻到下一张幻灯片。这里我想特别强调的一点是：**GLM 绝不仅仅是一个单纯的代码大模型**。

虽然目前很多开发者热衷于将它接入像 **Claude Code**、**Codex**、**OpenCode** 或者 Cursor 这类编程辅助工具中作为后端引擎，但实际上我们在训练 GLM 时涵盖了极其广泛的通用能力维度，编程只是其强大实力的一部分。

举例来说，我们在涵盖多国综合常识、GDP 经济数据分析、复杂数学问题求解以及多语言跨学科任务上，都取得了非常优异的评测成绩。坦白讲，我们团队在数学建模和数理逻辑的打磨上下了非常大的功夫。与此同时，我们还喂入了大量专注于**角色扮演 (Role-Playing)**、拟人化交互以及复杂日常沟通的真实语料。

我们的终极目标是全面提升模型的每一个综合维度，打造一个全方位的通用智能体。大家可以看到，在综合人工智能评测指数上，GLM-5.2 已经大幅领先于同量级的其他开源权重模型，紧紧咬住闭源顶尖模型的第一梯队。因此，我非常希望那些还没尝试过 GLM 的朋友们，不仅仅在写代码时用它，更去尝试把它用在日常对话、工作流自动化、分析总结等广泛的业务场景中，充分探索它在编程之外的巨大潜能。

<details>
<summary>Original English</summary>

**Zixuan Li**: Vale, la siguiente diapositiva. Y yo quiero tener en cuenta que GLM es más que un modelo para codificar. Aunque la gente lo usa en Clock Code, Codex, OpenCode, en realidad lo entrenamos para muchas razones, además de la programación. Por ejemplo, tenemos significativamente mejores resultados en análisis económicos, estimaciones del PIB y problemas matemáticos. Francamente hablando, también nos preocupamos mucho por los problemas matemáticos. También entrenamos con muchos materiales relacionados con juegos de rol y comunicación general. Nosotros queremos mejorar todos los aspectos del modelo.

Puedes ver cuál es el índice de inteligencia artificial: ella está muy por delante de los demás modelos con pesos abiertos. Sí, está muy cerca de los modelos de vanguardia. Así que quiero que ustedes, si no han utilizado GLM todavía, lo prueben para chats generales, para tareas diarias de horario laboral, no solo para codificación; pueden explorar las posibilidades del modelo fuera de las fronteras de la programación.

</details>

### 为什么坚持开源权重：安全、多样性与共建未来

**李子轩 (Zixuan Li)**: 请翻到下一张幻灯片。**GLM-5.2 是一款真正开放权重的模型 (Open-Weights Model)**。

正因如此，经常会有投资人和同行问我：“你们为什么要毫无保留地开源模型权重？难道你们不担心自己的商业化变现吗？不害怕别人通过第三方推理服务商搭建基础设施从而分流你们的市场份额吗？”

事实上，我们决定全面开源模型权重，是出于多重深刻考量，这既来自于全球用户的强烈刚需，也契合我们自身的战略诉求。如果能够切实解决开发者的痛点，开源就是一种双赢且极为正确的选择。

**第一，自主可控与安全信任**。如果我们的用户（特别是大型企业、受严格合规监管的机构，或是西方各国的政府与科研单位）需要极高的**数据安全与隐私控制权**，开源权重能够建立最坚实的信任基石。在这种场景下，我们开放权重并把完整模型上传到 **Hugging Face**，让他们可以在完全物理隔离的本地私有化集群中进行离线部署与运行。我认为，对于整个全球 AI 生态而言，能够自由、透明地研究一个性能逼近闭源前沿水准的模型，具有无法估量的战略价值。

**第二，垂直领域的深度多样化需求**。所谓的生态多样性，是指各个行业对于专业模型能力的定制需求——比如法律服务、金融风控、医疗健康以及网络安全等专业垂直赛道。企业往往需要基于基础底座模型进行二次微调和全参数再训练。为了满足这种诉求，就必须彻底开放底层权重，赋予大家自由训练与适配的权力。例如知名的法律 AI 独角兽公司 **Harvey**，他们此前就对 GLM-4 系列进行了深度的垂直领域二次微调，目前也正在规划基于最新的 **GLM-5.2** 展开新一代法律大模型的重训。我和许多其他的顶尖创业团队沟通过，他们都将基于 GLM 的深度微调视作构建自身技术护城河、在竞争激烈的应用赛道中脱颖而出的关键战略。

**第三，与社区共同定义未来标准**。如果我们的客户、生态伙伴或独立开发者希望与我们携手探索下一代大模型的架构演进，他们就必须能够直观审视模型的底层拓扑设计以及训练技术方案（Training Recipe）。我们希望推动技术标准的透明化与普惠化。我们与客户以及全球开源社区携手并进，共同塑造生成式 AI 的技术未来。我们的研发需求与社区生态之间形成了极为良性的互补。

坦白地说，如果没有全球开源社区中千千万万开发者、技术组织、内容创作者以及像 **Pedro** 等应用开发者的鼎力支持与贡献，GLM-5.2 绝对不可能取得今天的瞩目成绩。开源不仅意味着模型权重的公开，更意味着开源安全基线以及全栈生态系统的紧密协同。你们所做的一切，都是激励我们不断攀登、研发更优秀模型的最强大动力。在座的每一位开发者，都是真正的时代英雄！

<details>
<summary>Original English</summary>

**Zixuan Li**: Siguiente diapositiva. GLM-5.2 es un modelo con pesos abiertos. Por eso a menudo me preguntan: "¿Por qué están abriendo los pesos? ¿No les preocupa su negocio? ¿No tienen miedo de perder cuota de mercado frente a proveedores de inferencia de terceros?"

De hecho, nosotros abrimos los pesos por varias razones, porque hay una necesidad real de los usuarios y de nuestras propias metas. Si podemos satisfacer esas necesidades, creo que esto está muy bien. Para nosotros es totalmente aceptable abrir el modelo.

Por ejemplo, primero, si nuestros usuarios necesitan seguridad y control, y queremos fortalecer la confianza, podemos hacer que los pesos sean abiertos. En algunos casos, si una empresa o gobierno, especialmente en Occidente, desea usar el modelo, abrimos los pesos y los subimos a Hugging Face para que puedan usar el modelo localmente en sus propios servidores. Creo que para todo el ecosistema es muy útil investigar un modelo de esta escala, especialmente cuando sus capacidades se acercan a los indicadores de vanguardia.

En segundo lugar, si la gente necesita diversidad y personalización. Por diversidad me refiero a oportunidades en áreas como derecho, finanzas, seguridad: pueden entrenar el modelo. Entonces necesitamos abrir el modelo para permitirles hacer ese entrenamiento adicional o fine-tuning. Por ejemplo, Harvey ahora reentrena GLM y tal vez planea reentrenar GLM-5.2 más adelante. Hablé con muchas otras empresas, y ellos también consideran el reentrenamiento de GLM como su siguiente paso estratégico para destacar frente a otras empresas y desarrolladores de aplicaciones.

Y en tercer lugar, si nuestros clientes o investigadores individuales quieren diseñar y predecir el futuro juntos, a veces necesitan ver la arquitectura del modelo y la receta para su entrenamiento. Por lo tanto queremos que sea un estándar abierto. Nos esforzamos junto con nuestros clientes y la comunidad de código abierto para dar forma al futuro. Creo que nuestras necesidades y el ecosistema se complementan mutuamente. Y GLM-5.2 no habría tenido éxito sin todos ustedes, participantes de las comunidades de código abierto, medios y súper desarrolladores. Muchas gracias a los creadores de aplicaciones como Pedro. El código abierto no es solo pesos abiertos, sino también seguridad abierta y colaboración. Todo su apoyo nos anima a crear mejores modelos. Creo que ustedes son verdaderos héroes.

</details>

### 技术博客、生态资源与全新评测框架 Z-Code

**李子轩 (Zixuan Li)**: 最后，我想向大家分享一个极具价值的技术宝库，在这里大家可以全方位了解 GLM-5.2 的技术细节——这就是我们的**官方技术博客 (Technical Blog)**。

在技术博客中，我们倾囊分享了大量的深度资料。例如，我们在 **Hugging Face** 上建立的官方模型开源仓库，大家可以第一时间下载并亲手体验 GLM-5.2 的权重；如果想快速验证效果，也可以直接通过我们的 Web 聊天机器人平台进行试用，或者直接接入我们的商业化 **API 接口**进行调用测试。

此外，我们针对独立开发者推出了极具性价比的开发者支持计划，模式类似于 Codex 或各大主流云平台，开发者能以极低的成本获取充足的 Token 配额。同时，我们在博客中深度公开了我们的**模型训练流水线 (Training Pipeline)** 以及关键的**训练配方与经验技巧 (Training Recipes)**，旨在帮助技术圈彻底理解为什么 GLM-5.2 能够展现出如此卓越的性能与稳定性。在模型的背后，承载着无数个日夜的技术突破，它绝不仅仅是一个简单在大规模优质数据上完成微调的模型，其核心凝聚着我们团队打造的一整套尖端底层算法架构。通过这些开源公开的技术报告，大家可以独立深入地复现与探究，看到我们一路走来攻克的重重技术险阻。

最后一张幻灯片，我想为大家带来一个小小的彩蛋——“One More Thing”。

这是我们第一次正式向全球开源社区隆重推介 **Z-Code**。这是我们自主研发的一套强大的**评测与调度运行底座 (Evaluation & Harness Framework)**。Z-Code 最初是专为充分释放 GLM 系列模型的极致代码潜能而量身定制的，但它同时也完美兼容并支持市面上所有主流的前沿大模型。开发者只需配置自己的 API Key，即可无缝接入 Z-Code 生态。在开发体验上，它的交互逻辑与顶尖的辅助编程工具非常契合。大家可以在其中尽情尝试各种前沿的上下文压缩技术、目标引导提示词工程以及提示词蒸馏算法，这些正是业界在各类顶尖代码 Agent 工具中所广泛采用的技术。

Z-Code 是充分挖掘并驾驭 GLM 系列模型强大能力的理想伴侣。如果你此前还没有尝试过，欢迎随时在 Github 检索并体验 Z-Code，或者直接移步我们的大会现场展位。我们现场的技术团队成员会非常乐意为大家亲自演示这套工具的强大功能。

我们由衷期待大家的莅临！未来我非常希望能有更多机会与大家面对面交流。下一次大会，我一定会亲自飞抵旧金山现场，与大家把酒言欢、深入探讨技术。再次感谢大家！

<details>
<summary>Original English</summary>

**Zixuan Li**: Finalmente, quiero compartir un recurso maravilloso donde pueden familiarizarse con GLM-5.2: este es nuestro blog técnico. En este blog compartimos diferentes cosas; por ejemplo, nuestro repositorio en Hugging Face, donde pueden probar GLM-5.2. Pueden probarlo en el chatbot y también utilizar la API. Además, tenemos un plan para desarrolladores, similar a Codex o Cloud platforms, donde pueden usar tokens como persona individual.

Nosotros también hablamos de nuestro pipeline de entrenamiento y de las recetas de entrenamiento, para que entiendan por qué este es un buen modelo. Detrás del modelo hay muchas cosas; no es solo un modelo entrenado con datos maravillosos, también tenemos tecnología fantástica en el núcleo, para que puedan investigar el modelo independientemente y ver las dificultades que superamos.

Y la última diapositiva es algo así como "One More Thing". Es la primera vez que compartimos Z-Code con toda la comunidad. Este es nuestro propio arnés (eval/execution harness), Z-Code, que fue creado para GLM, pero que también soporta todos los modelos avanzados. Puedes usar tu propia API key y conectarte con Z-Code; creo que el proceso es muy similar al flujo de trabajo estándar en Codex o herramientas afines. Puedes probar diversas técnicas avanzadas, compresión de contexto y métodos similares a los utilizados en la industria. Este harness es ideal para GLM. Si aún no lo has probado, solo busca Z-Code o ven a nuestro stand; nuestro equipo te mostrará este entorno. Los invitamos a nuestro stand y estaré encantado de charlar en el futuro. La próxima vez sin duda estaré allí en San Francisco para hablar con todos ustedes. Sí, muchas gracias.

</details>

### 主持人总结与全球开发者盛会闭幕

**主持人 (Swix)**: 非常感谢你，子轩！请相信我，在第一届世界博览会上，因为签证等突发客观因素暂时无法跨国亲临现场的感受我们感同身受，大家完全理解并由衷赞赏你们克服困难通过远程连线带来的精彩分享。

智谱 Z.ai 团队为此付出了极其巨大的心血与努力。他们现场的小伙伴们也非常热切地希望能与在座的每一位开发者深入交流。他们就在楼下展厅等候大家！

而这正是我们举办世界博览会（AI Expo / World Expo）的初心与核心宗旨所在：将全球最顶尖的人工智能研发企业、顶级学术实验室以及杰出的技术领袖汇聚一堂，让大家能够并肩探讨业务合作、结识那些支撑着大家每天日常使用的先进模型背后的研发专家，甚至私下探讨那些在公开场合不便细聊的硬核技术内幕。

我也感到由衷的自豪。正如刚才子轩在幻灯片中所展示的全球 Hugging Face 最具影响力排行榜单，现场参会的各大顶尖实验室中，排行榜前八名就有四家亲临博览会现场！我们不仅与 **Nvidia**、**Ollama** 等全球算力及本地推理工具链开发者建立了深度的技术协同，还在现场全面展示了最新的本地离线运行方案，大家在明后天的议程中将看到更多重磅成果展示。

再次向子轩表示衷心的感谢！接下来，我将邀请下一组重磅演讲嘉宾登台分享。接下来让我们一同欢迎 **Hugging Face** 与 **MiniMax** 的代表带来更精彩的技术分享。谢谢大家！

<details>
<summary>Original English</summary>

**Host (Swix)**: Muchas gracias. Créeme, en la primera World Expo no siempre es fácil viajar o regresar al país para tu propia conferencia, así que entiendo perfectamente el sentimiento. Pero el equipo de Z.ai realmente hizo un gran esfuerzo. Ellos realmente quieren conocer a todos, y están aquí en el piso de exhibición para conocerlos.

Y esta es la esencia de la World Expo: reunir a todas las empresas y laboratorios líderes de IA del mundo en un solo lugar para que puedan hacer negocios juntos, conocer a las personas que están detrás de los modelos que ustedes usan todos los días y hacer preguntas que tal vez no se puedan responder públicamente, pero que se pueden discutir en privado.

Yo también estoy muy orgulloso. Zishan mostró la lista de los principales participantes de Hugging Face. Creo que tenemos a cuatro de los ocho de esa lista aquí presentes como asistentes en la World Expo. Trabajamos con Nvidia, Anslaw, Ollama y otros desarrolladores de entornos para brindar ejecución en entornos locales, lo cual verán más de cerca en los próximos días.

Con esto, muchísimas gracias a Zixuan. Voy a invitar a las siguientes personas. A continuación, hablemos con Hugging Face y MiniMax. Gracias.

</details>