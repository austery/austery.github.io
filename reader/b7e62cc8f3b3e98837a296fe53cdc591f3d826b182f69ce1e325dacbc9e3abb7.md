---
author: All-In Podcast
date: '2026-09-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JEUboZzZGM4
speaker: All-In Podcast
tags:
  - preventative-healthcare
  - early-disease-detection
  - body-scan
  - health-tech
  - scaling-laws
title: 专访 Daniel Ek：从创立 Spotify 到用 AI 重塑预防性医疗（Neko Health）
summary: Spotify 联合创始人 Daniel Ek 做客 All-In 播客，详述创办 Spotify 破局音乐版权体系的历程、退居幕后创立深度科技孵化器 Prima Materia 的思考，以及创办全身健康扫描公司 Neko Health 的初衷。他剖析了美国医疗体系在激励机制上的根本性扭曲，分享了依托传感器与 AI 筛查心血管疾病、糖尿病与黑色素瘤的突破性数据，并深入探讨了算力规模定律、开源 AI 与播客生态的未来。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Daniel Ek
companies_orgs:
  - Spotify
  - Neko Health
  - Prima Materia
products_models: []
media_books: []
status: evergreen
---
### All-In 播客开场与嘉宾介绍

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 好的，大家请安静。欢迎回到 **All-In** 访谈专栏。在 All-In 播客中，我们通常会花上一小时，与我们这个时代最杰出的思想家和创造者展开深度对话，今天自然也不例外。今天做客我们节目的是 **Daniel Ek（丹尼尔·埃克）**。大家对他都很熟悉，他是 **Spotify** 的联合创始人。Spotify 成立于 20 年前，在过去二十年波澜壮阔的历程中，他始终掌舵领航，带领公司走到了今天的辉煌成就：拥有超过 7 亿活跃用户、3 亿多付费订阅用户。然而就在今年 1 月 1 日，他完成了角色转变，升任执行董事长。今天与我一同主持的还有 **David Friedberg（大卫·弗里德伯格）**。Daniel Ek，你好，先生！非常欢迎来到我们的节目。

<details>
<summary>Original English</summary>

**Jason Calacanis**: De acuerdo, por favor, todos. Por favor, regrese a programa de entrevistas All In, donde nosotros, el podcast All In, dedicamos una hora algunos prominentes pensadores, creadores de nuestro tiempo, y hoy no es será una excepción. Con nosotros Daniel Eck. Sabes él, cofundador Spotify, ¿qué es? fundada hace 20 años y él la dirigió durante estos dos Hace décadas estado de emergencia cosas hoy. Encima 700 millones activos usuarios, más de 300 millones de primas suscriptores, pero 1 Enero de este año él cambió y se convirtió presidente ejecutivo conmigo y David Friedberg hoy. Daniel Eck, ¿Cómo está usted, señor? Bienvenido a programas.

</details>

**丹尼尔·埃克 (Daniel Ek)**: 非常感谢你们邀请我，很高兴能与你们共聚一堂。

<details>
<summary>Original English</summary>

**Daniel Ek**: Bueno, muchas gracias, que me invitaron. Es un placer estar contigo.

</details>

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 是的，见到你非常高兴。我们彼此认识有二十年了。我还清楚地记得，当年在一次互联网峰会上，一位有些拘谨的伙伴俯身对我说：“嘿，听听这个。”然后他向我展示了 Spotify。但在那个时代，根本没有任何人愿意为订阅付费。今天，我们肯定要重点聊聊你在医疗健康领域创立的那家令人难以置信的全新初创公司——**Neko Health**。不过，我们还是先回到当年推出 Spotify 的起点：这一切究竟是如何发生的？在当时要打入音乐产业是何等艰难？众所周知，音乐唱片巨头被称为全世界上最难打交道的商业伙伴之一。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Sí, encantado de verte. Nos conocemos. Durante 20 años. I Recuerdo cómo el primero El compañero de Shaky se inclinó a mí en internet cumbre o en algún lugar de allí y dijo: "Oye, escucha" esto". Y lo demostró Tengo Spotify. Pero lo fue en un momento en que ninguno quien no fue atendido suscripciones. Por lo tanto, hoy nosotros Hablemos del tuyo una nueva empresa emergente que es increíble en el campo cuidado de la salud. Pero volvamos a lanzar Spotify y eso ¿Cómo sucedió esto? [ __ ]. Y Entonces, qué difícil fue para abrirse paso en la industria musical industria, que también conocido como el más difícil socios en el mundo. Voy a toda máquina.

</details>

### 商业赞助：Creative Planning 财富管理

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 你是否意识到，随着在投资、税务策略和遗产规划之间的事务愈发繁杂，处理这一切正在变成一项占用你全部精力的全职工作，而这根本不是你原本想要承担的？**Creative Planning** 能够提供帮助。他们由投资经理、注册会计师（CPA）以及遗产规划律师组成的协同团队，可以替你承担绝大部分繁重的琐碎工作，让你高枕无忧。Creative Planning，让财富通力协作。详情请访问 creativeplanning.com/allin。接下来我们全速推进。

<details>
<summary>Original English</summary>

**Jason Calacanis**: O ¿Te diste cuenta? hasta volverse más difícil cosas entre inversiones, impuesto estrategia y planificación patrimonial ¿ Gestionarlo todo se convierte en un trabajo en jornada completa, ¿Algo que no pediste? La planificación creativa puede ayuda. Su coordinado equipo inversión gerentes, contadores públicos certificados y asociado abogados sobre temas la herencia puede realizar una tarea significativa parte de lo pesado trabajo, para que no lo hagas tendrá que hacerlo. Planificación creativa donde funciona la riqueza juntos. Ir a creativeplanning.com/allin. Voy a toda máquina.

</details>

### 创立 Spotify 的开端与瑞典盗版时代

**丹尼尔·埃克 (Daniel Ek)**: 好的。对于这段往事，我通常会先自我调侃一句：当年刚开始干的时候我满头黑发，而到了最后，显而易见，我彻底秃顶了。由此可见这究竟是一条多么艰辛的道路。言归正传，为了交代一下当时的背景：我是在 **2006 年**创立 Spotify 的。那年我才 23 岁，当时的世界与今天完全不同。那是 iPhone 问世之前的时代；当时虽然已经有了 Facebook，但它还仅仅局限在大学校园的大学生之间；而 YouTube 甚至才刚刚冒头。那是一个在我们如今习以为常的现代数字生活出现之前的时代。

当时的世界，特别是整个音乐唱片工业，正经历着前所未有的自由落体式崩塌，因为音乐盗版在当时极度猖獗泛滥。我们先后经历了 **Napster**、**Kazaa** 等一系列 P2P 软件的冲击。当时还有一个名为 **RIAA（美国唱片业协会）** 的组织，四处把美国普通个人消费者告上法庭，起诉他们非法下载音乐。

我当时坐在瑞典，心里暗想：这简直是疯了，这种做法太荒谬了。潘多拉魔盒一旦打开，没有任何办法能把精灵重新塞回瓶子里。当时我和我的联合创始人 **Martin Lorentzon（马丁·洛伦松）** 坐在一起探讨创业点子。Martin 问我：“如果你能做任何想做的事情，你究竟想做什么？”我回答说：“我内心真正的热爱始终是音乐，但这似乎是个极其愚蠢的想法。”他追问：“为什么会是愚蠢的想法？”我向他解释说这太难了，因为你必须与所有唱片巨头签署海量复杂的授权协议，必须理清如何处理版税、著作权许可等千头万绪的问题。

然而 Martin 却不断用“如果……会怎样？”来反问我。在他连珠炮似的追问下，我最终没有了退路。我对他说：“如果我们真能做成这件事情，用户体验到的感觉就好像‘世界上所有的音乐都在你的触手可及之处’。”他听了之后说：“听起来非常棒，那我们放手一搏试试看吧。”于是我们便一头扎进了音乐版权许可的深水区。

最初我们的设想是从第一天起就进军全球市场，但当我们向外界说出这个想法时，所有人几乎都在嘲笑我们。但在某种程度上我也十分幸运，因为事实证明，当时全世界音乐产业环境最恶劣的市场，恰恰是我的祖国——瑞典。之所以如此，是因为早在 2000 年代初，瑞典就已经普及了超高带宽的宽带接入。我们生活在一个超前的未来世界里：人们拥有极高网速的带宽连接，几乎可以随意下载他们想听的任何音乐。甚至连 iTunes 当时在瑞典都没有正式上线运营。市场上可以说完全没有任何正版合法的数字音乐选项。正因如此，当时的瑞典音乐产业损失了大约 80% 的收入。

<details>
<summary>Original English</summary>

**Daniel Ek**: Sí, bueno, eh, yo Normalmente empiezo con lo que yo diga, lo que sería No me preguntaron. sobre esta historia, Dicen que yo tenía cabello cuando yo lo empezó y al final Obviamente, eh, me convertí calvo. Entonces, eh, tú ya ves lo que era un camino difícil. Chistes en broma, solo para para aclarar un poco situación, yo fundado Spotify en 2006. Yo Tenía 23 años entonces, y El mundo parecía un poco de lo contrario. Y eso fue todo. al iPhone, antes, En realidad, existía Facebook. pero fue solo para estudiantes. YouTube, mmm, más no existía. Bueno, esto Conóceme un poco, pero eso fue antes de todo lo que somos ahora lo percibimos como pendiente. Y, eh, y el mundo en ese momento, hmm, y industria musical en Estaba pasando por ese momento. caída libre, porque, hmm piratería musical fue suficiente común. Entonces, tenemos Estaba Napster, teníamos Kazaa, teníamos todo esto, y era una organización bajo nombrada en honor a la RIAA, que presentó ante el tribunal en particular consumidores en los EE. UU. para ilegal descarga de música. Y entonces, estaba sentado en Suecia y pensó en tú mismo, ya sabes, es una locura, Esto es una locura. Ninguno forma de regresar El genio ha vuelto a la botella. Y estamos con el mío cofundador Martin, eh, entonces se sentó y ideas discutidas para startups y ya sabes, Martin me preguntó algo como: "Si pudieras hacer todo lo que lo que quieras ¿hizo? Y yo dije: " Mi verdadero la pasión es música, pero esto Parece muy estúpido idea." Y él es así: " "¿Por qué es una idea estúpida?" Y Le dije que era Es realmente difícil porque, eh, es necesario poner todos estos acuerdos con grabación sonora empresas, entonces necesito averiguar cómo organizar licencias y derechos de autor y para hacer todas estas cosas diferentes cosas. Y él dijo: "A ¿Y si hicieras esto? ¿Eso? Y entonces él continuó apostando estas preguntas "¿Qué, ¿y si?", y finalmente en Se me acaba el tiempo. razones para decir esto. Entonces dije: "Bueno, Creo que podrías hacer algo. para hacer, y si lo haces, y si lo haces hizo algo, entonces sentiría como si todo La música del mundo está contigo cerca de la mano". Y él así: "Bueno, eso suena bien" "Bastante bien." Y yo dijo: "De acuerdo, "Intentémoslo." Empezamos Licencia de música. Primero la idea Consistía en el hecho de que intenta salir mercado mundial con el primer día, y todo simplemente se rieron de nosotros cuando dijimos eso. Pero hasta cierto punto yo afortunado porque Resultó que uno de lo peor mercados musicales en El mundo era mi hogar país, Suecia. Y en parte era uno de los mercados musicales mundo, debido a A principios de la década de 2000 ya tenemos fue súper rápido banda ancha acceso. Así que vivimos en un futuro donde la gente tuvo una tan rápida, eh, conexión con ancho de banda que podría para descargar prácticamente todo lo que buscado. Así son iTunes lo hizo, y iTunes también. en realidad ni siquiera estaba disponible, eh, en mercado. Literalmente no había ninguno opciones legítimas. Entonces, creo que musical la industria perdió alrededor del 80% de sus ingreso.

</details>

### 唱片巨头谈判与流媒体模式破局

**丹尼尔·埃克 (Daniel Ek)**: 这可以说是极其离奇而巧合的一系列事件交织在一起。我和 Martin 实际上拿出了之前在其他初创公司赚到的全部个人积蓄来投入这个项目。当时唱片公司高管的心态是：“既然我们已经损失了 80% 的收入，眼看就要彻底完蛋了，不妨死马当活马医，跟这两个狂妄的年轻疯子签个一年的试运营授权协议吧。如果一年后彻底失败关门大吉，反正他们给的前期保底版税我们已经揣进兜里了。”

这就是当年我们得以撕开缺口的契机。随后我们将产品推向了英国，并在那里取得了巨大的成功。那成了我们通往全球舞台的跳板。

<details>
<summary>Original English</summary>

**Daniel Ek**: Y aquí está. fue algo así como, eh -eh, fue así loco, eh, ya sabes, coincidencia y todo eso, un conjunto de eventos cuando lo entendimos, ya , nosotros, nosotros, de hecho, tomamos todo nuestro propio dinero que ganamos en startups anteriores y lo pusimos en este proyecto. Y los sellos discográficos pensaron: "¿Qué piensas entonces? simplemente ciérralo un año después, pero todo ¿Seguirás recibiendo una bonificación? Así que cerramos este trato de un año. Luego trajimos él al Grande Gran Bretaña, eh, y ¿Lo hizo? Sí, fue un gran éxito.

</details>

**大卫·弗里德伯格 (David Friedberg)**: 我记得后来 **Sean Parker（肖恩·帕克）** 也参与了进来，对吧？

<details>
<summary>Original English</summary>

**David Friedberg**: Quiero decir, ¿no es así? ¿Sean Parker se involucró en ese momento?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 没错。在英国站稳脚跟后，整个故事才真正迎来了质的飞跃。肖恩·帕克联系了我，并亲自写了一封长信向 **Mark Zuckerberg（马克·扎克伯格）** 极力推荐我们。后来他飞到瑞典，成了我们的第一位美国知名投资人和倡导者。再后来，我们便全力向美国进军。

打入美国市场遭遇的阻力可想而知：史蒂夫·乔布斯（Steve Jobs）和苹果公司在数字音乐下载领域占有绝对统治地位，他们最初坚信用户想要“拥有”音乐而非“租用”流媒体。但我们的信念始终没有动摇：极速响应、零缓冲、随点随到的流媒体体验，其便捷程度超越了盗版和下载。最终事实证明，订阅制流媒体彻底拯救并重构了全球音乐产业。

<details>
<summary>Original English</summary>

**Daniel Ek**: Sí, así es. Cuando estuvimos en el Reino Unido, Sean Parker se puso en contacto conmigo. Escribió una carta increíble a Mark Zuckerberg sobre Spotify, vino a vernos a Suecia y se convirtió en un gran defensor e inversor. Luego vino la batalla por entrar en Estados Unidos, con Steve Jobs y Apple dominando las descargas digitales de música. Pero seguimos adelante porque sabíamos que una experiencia de streaming instantánea y sin fricción superaría a la piratería. Y al final, el modelo de suscripción transformó y rescató toda la industria de la música.

</details>

### 从 Spotify CEO 到全职创业：Prima Materia 的诞生

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 那么 Daniel，你是在什么时候开始把目光投向音乐之外的其他领域的？你在过去十几年里全神贯注地担任 Spotify 的 CEO。你是如何开始涉足其他项目和投资的？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Pero cuando tú empecé a pensar en ¿Alguna otra cosa, Daniel? Tú invierte activamente en Spotify durante durante muchos años como Director ejecutivo ¿ Los negocios de la música requerían toda tu atención. ¿Cómo empezaste para lidiar con estos ¿Otros proyectos? ¿Cuál exactamente?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 在整整 12 到 13 年的时间里，我几乎把 100% 的精力都扑在 Spotify 上，在那期间我根本没有在外界做过任何其他实质性投资。后来我和一些朋友聊天时，也曾尝试做过一点点早期天使投资。然而我很快就发现，自己从骨子里热爱的是“亲手从零构建业务（Building）”，而不是坐在看台上指手画脚的“投资（Investing）”。

当时 Chamath（查马斯）也得出了完全相同的结论。对我而言，以纯粹投资人的身份坐在一旁看着别人做决策，会让我感到极其痛苦和被动。这促使我与几位合伙人联合创立了深度科技投资与孵化机构 **Prima Materia**。我们决定把欧洲乃至全球那些最艰难、最复杂的宏观难题作为攻坚目标，尤其是那些需要 10 年以上长期资本投入的深科技领域。

<details>
<summary>Original English</summary>

**Daniel Ek**: Sí, bueno, pasé la mayor parte de 12-13 años antes de que yo comenzó a invertir en otra cosa. Y entonces, hmm, Sabes que estamos contigo. Lo hablamos, hmm, para cenar una semana o algo así, pero mmm, ya sabes, lo haré más tarde. lo intenté un poco invertir. yo ya luego lanzó, eh, Neko, y acabo de darme cuenta, lo que me gusta construir mucho más que invertir y por lo tanto ahora Chamat llegó al mismo conclusión. Me duele muchísimo. observa cómo otros toman decisiones. Así que creamos Prima Materia para abordar problemas científicos y tecnológicos realmente difíciles a largo plazo.

</details>

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 那大概是哪一年？

<details>
<summary>Original English</summary>

**Jason Calacanis**: ¿Qué año fue?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 大概是在 2018 到 2019 年前后。在那段时间里，我开始深度反思，如果我要把接下来几十年的生命投入到除了 Spotify 之外的某项事业中，那这项事业必须对人类社会产生巨大的、根本性的积极影响。这也是我为什么最终全身心投入创办了 **Neko Health**。

<details>
<summary>Original English</summary>

**Daniel Ek**: Eso fue alrededor de 2018 o 2019. Fue en ese momento cuando comencé a pensar en qué quería hacer que tuviera un impacto masivo en el mundo más allá de la música, y ahí es donde comenzó el viaje de Neko Health.

</details>

### 医疗保健的系统性失灵与预防医学的空白

**大卫·弗里德伯格 (David Friedberg)**: 那么 Daniel，你能否详细聊聊这一切究竟是如何萌芽的？你为什么会专门挑选医疗保健这个公认最复杂、最受重度监管且体制极其僵化的赛道？你是怎么锁定这个具体切入点的？

<details>
<summary>Original English</summary>

**David Friedberg**: Entonces, Daniel, tal vez... Sí, ¿Y cómo llegaste a...? Esta idea, ¿verdad? ¿Cómo llegaste a esto? ¿Una idea específica? ¿Por qué la atención médica?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 当我开始审视全球重大难题时，我调研了从新药研发到癌症治疗的各个环节。但当你退后一步看宏观全景时，你会发现一个令人震惊的事实：以美国为例，医疗支出占到了全美 **GDP 的 18%**。而在欧洲，这一比例也在 10% 到 12% 之间，并且还在以不可持续的速度逐年飙升。

更荒谬的是，我们今天所称的“医疗保健（Healthcare）”，在本质上根本不是“保健”，而是彻头彻尾的“被动生病治疗（Sick Care）”。现在的系统只有当你已经出现了明显症状、感到身体不适、器官发生实质性器质病变时，你才会走进医院。而到了那个阶段，治疗成本极其昂贵，患者饱受折磨，临床预后往往非常差。

于是我和后来的联合创始人 **Hjalmar Nilsonne（亚尔马·尼尔森）** 开始深入讨论一个根本性问题：为什么我们不能在疾病最初萌芽、完全没有任何临床表征的潜伏阶段，就提早捕获它？

当你在不同学科专家之间求证时，往往会听到各种分歧。但我们得出的核心认知非常简单明了：**所有精准预测的前提，都始于获取最好、最全面的纵向数据**。在现有医疗体制下，一个普通人几年才做一次几分钟的走马观花式体检，抽几管血，医生看一眼就完事了。你根本没有任何关于自身身体的纵向（Longitudinal）高精度数据追踪。如果你没有基线，你怎么可能在早期发现微小的异常偏离？

<details>
<summary>Original English</summary>

**Daniel Ek**: Y por eso yo comenzó a investigar todo desde medicamentos hasta, eh, ¿Sabes si es posible? crear ¿Medicamentos más eficaces? O Esto tiene que ver con el cáncer y básicamente comenzó con con el fin de en qué concentrarse, ¿Cuál es el problema fundamental? Estados Unidos, eh, gastan el 18% de sus PIB para la protección salud. Y la mayor parte de ese dinero se gasta en lo que en realidad es "atención a la enfermedad" y no en salud preventiva. Solo actúas cuando alguien ya tiene síntomas o está gravemente enfermo. Y luego Surge entonces la pregunta: ¿por qué? no estamos detectando nada ¿En una etapa temprana? Y mi cofundador Hjalmar Nilsonne y yo dijimos: todo comienza con obtener los mejores datos longitudinales. Si tienes datos continuos y completos a lo largo del tiempo, la probabilidad de hacer diagnósticos predictivos y preventivos aumenta exponencialmente.

</details>

### Neko Health 的诞生理念：构建全身多维扫描仪

**丹尼尔·埃克 (Daniel Ek)**: 于是我们反思：过去二十年里硬件和技术领域发生的最重大变革是什么？毫无疑问，智能手机的爆炸式发展带动了各种工业级传感器、高清摄像头、激光雷达以及计算芯片的极致小型化与廉价化。

我们设想：如果我们不再依赖传统医院那些庞大、缓慢、昂贵且互不连通的单项检查设备，而是自主设计并全栈垂直整合一台拥有数百万传感器的“全身三维多模态扫描仪”，会发生什么？

在 **Neko Health**，我们花费了数年时间研发专门的定制扫描硬件舱与人工智能图像识别算法。当用户走进扫描舱时，数千个高清传感器与激光雷达会在短短几分钟内，完成对人体表面乃至皮下浅层组织的微米级三维建模，同时结合无创心血管血流动力学分析、心电图、微循环检测及代谢指标。

<details>
<summary>Original English</summary>

**Daniel Ek**: Y entonces dijimos: bueno, Vale, ¿qué te parece si lo hacemos? Pensamos en lo que sucedió en los últimos 20 años: la revolución de los sensores en smartphones. Hay cámaras de alta resolución, radares, sensores térmicos que son increíbles y accesibles. ¿Qué pasaría si construyéramos una cabina de escaneo de cuerpo entero completamente integrada que pudiera recopilar millones de puntos de datos sobre la piel, el sistema cardiovascular y el metabolismo en cuestión de minutos? Eso fue lo que construimos en Neko Health: una integración vertical de hardware y software para capturar la imagen completa de la salud de una persona.

</details>

### 临床检测流程与三大慢病早期预警

**大卫·弗里德伯格 (David Friedberg)**: 那么目前有哪些临床证据表明，这种早期的观察性多模态数据能够真正逆转或改变严重疾病的进程？你们重点聚焦筛查哪些严重疾病？

<details>
<summary>Original English</summary>

**David Friedberg**: O Hoy existen pruebas que algunos de estos temprano de observación los datos pueden para influir en los resultados? Qué otra cosa ejemplos de serios enfermedades que podemos detectarlo por adelantado, Claro, ¿verdad?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 现代人类面临的最大健康杀手和医疗支出黑洞主要集中在三大领域：第一是**心血管疾病**（如冠心病、动脉硬化、心肌梗死和中风）；第二是**代谢类疾病**（主要是 2 型糖尿病及其并发症）；第三则是**癌症**，特别是发展极快且表征明显的**恶性黑色素瘤（皮肤癌）**。

在 Neko Health 的实际流程中，整个体验耗时大约一小时。在全方位非侵入式扫描完成后，用户会立刻与现场的注册执业医师坐在一起，在一块巨大的全高清可视化屏幕前，逐项分析刚刚生成的个人健康全景报告。

对于心血管，系统通过光电容积描记术（PPG）及动脉脉搏波传导速度（PWV）测量动脉血管壁的硬化程度和内皮功能。对于糖尿病，我们结合无创糖化血红蛋白预警与身体成分代谢风险评估。而对于皮肤癌，我们的高清光学阵列能自动识别并追踪用户全身平均多达数百甚至上千颗痣的尺寸、颜色、不对称性及边缘轮廓演变。

<details>
<summary>Original English</summary>

**Daniel Ek**: En el mundo actual, las principales causas de mortalidad y gasto médico son las enfermedades cardiovasculares, la diabetes y el cáncer, en particular el melanoma. Con Neko, en una sesión de una hora que cuesta unos 500 dólares, el paciente pasa por el escaneo y luego se sienta inmediatamente con un médico. Revisamos la rigidez arterial mediante la velocidad de la onda de pulso (PWV), los riesgos metabólicos para la diabetes tipo 2 y realizamos un mapa dermatológico completo del cuerpo entero.

</details>

### 10 万次身体扫描的早期发现与数据洞察

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 在完成这多达数万次甚至十万次扫描的过程中，你们从数据中发现了什么从未预料到的新情况？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Qué Descubriste algo nuevo, Daniel, ¿qué no hacemos? ¿Lo has visto antes? Tienes ya una gran cantidad de escaneos realizados. ¿Qué te ha sorprendido?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 目前我们已经完成了超过 **10 万次**全身深度健康扫描。虽然这在整个人口基数中仍属于早期样本，但数据揭示的结果令人震撼：

在所有前来扫描的普通无症状人群中，我们有明确的临床随访数据证明，大约有 **1% 的受检者**被当场发现了此前完全不知情、未被确诊的严重潜在疾患。比如完全无感知的严重动脉瘤、隐匿性房颤、未察觉的心脏结构畸形，或是处于极早期、尚未转移的恶性黑色素瘤。对于这 1% 的人而言，这次体检直接挽救了他们的生命，避免了日后突发猝死或晚期恶化。

而更为普适的好消息在于，其余绝大多数参与者都是身体基本健康的普通人。对于他们来说，Neko 的价值在于帮助他们清晰认知自身当前的健康拐点。很多处于亚健康边缘的人，其指标异常主要与长期的慢性压力、不良膳食结构和严重睡眠不足直接相关。

过去医生只会对病人空洞地说“你该多运动、少吃点糖”，病人出门就抛在脑后。但在 Neko，当用户亲眼在屏幕上看到自己动脉硬化的真实图像，看到那条由数十万真实人口数据拟合出的“心血管生理年龄曲线”，并发现自己 35 岁的身体血管年龄居然相当于 50 岁时，那种视觉冲击所带来的行为重塑动力是极其惊人的。

<details>
<summary>Original English</summary>

**Daniel Ek**: Ya hemos realizado más de 100.000 escaneos, y estamos en el tercer año de seguimiento de resultados de salud. Aproximadamente el 1% de nuestros participantes tiene enfermedades o anomalías potencialmente mortales que descubrimos de forma temprana y que no habían sido diagnosticadas previamente, como aneurismas, arritmias graves o melanomas tempranos. Para ese 1%, esto les cambia la vida o directamente se la salva. Y para la gran mayoría que está sana, la capacidad de tener una visualización clara y longitudinal de su salud es un motivador increíble para cambiar hábitos de dieta, sueño y ejercicio antes de que desarrollen una enfermedad crónica.

</details>

### AI 赋能临床医生：从 950 颗痣到全面风险评估

**大卫·弗里德伯格 (David Friedberg)**: 这确实非常震撼。从医学实践来看，如果在传统的诊所体检中，医生只有短短 15 分钟时间，他根本不可能有精力把你全身的每一寸皮肤都仔细查看一遍。

<details>
<summary>Original English</summary>

**David Friedberg**: Exacto. En una visita médica tradicional de 15 minutos, ¿qué probabilidad hay de que un médico revise meticulosamente los cientos o 950 lunares que puedas tener en el cuerpo? Es humanamente imposible.

</details>

**丹尼尔·埃克 (Daniel Ek)**: 你说得太对了。一个普通人体表往往分布着 **500 到 950 颗痣**。在传统的皮肤科门诊中，没有任何一位医生能在肉眼观察下，记住并对比你背部某颗只有两毫米大小的黑痣在六个月内是否发生了细微的形态变化。

而在 Neko，计算机视觉算法会替医生完成所有繁重的机械性比对。AI 会标记出那 2 到 3 颗存在形态异型性或边缘增生的可疑痣，并将它们放大高亮呈现给现场医生。医生不需要把精力耗费在逐一排查上，而是专注于关键决策与病理判断。

这就是我们心目中**人工智能在医疗领域的绝佳落地范式**：AI 并不是要盲目取代执业医师，而是作为认知增强外脑，消除误诊盲区，将医生从低效的体力劳动中解放出来，让他们能够把时间真正投入到与患者的共情沟通和诊疗决策中。

<details>
<summary>Original English</summary>

**Daniel Ek**: Exactamente. Si lo piensas, un ser humano promedio puede tener 950 lunares. Ningún médico puede medir y recordar cada uno de ellos entre visitas. Pero nuestro sistema de visión por computadora puede rastrear cada lunar a nivel submilimétrico, comparar cambios a lo largo del tiempo y señalar al médico los dos o tres que requieren atención. Este es el caso de uso perfecto para la IA en medicina: no sustituir al médico, sino eliminar la carga cognitiva y dotarlo de superpoderes diagnósticos para que pueda centrarse en el cuidado del paciente.

</details>

### Neko 的商业模式与垂直整合优势

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 那么目前公司的管理架构是怎样的？Daniel，你现在是全职担任 CEO，还是以董事长的身份指导业务？

<details>
<summary>Original English</summary>

**Jason Calacanis**: ¿Y tú gestionas esto activamente como Director Ejecutivo, Daniel, o trabajas a tiempo parcial? ¿Cómo se dividen las responsabilidades?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 我拥有一位无与伦比的联合创始人兼 CEO——**Hjalmar Nilsonne**。他是一位极其出色的技术领袖和连续创业者，负责全盘日常运营。而我作为联合创始人兼董事长，把核心精力聚焦在战略顶层设计、产品哲学、组织文化以及全球扩张布局上。

<details>
<summary>Original English</summary>

**Daniel Ek**: Tengo un cofundador y socio increíble, Hjalmar Nilsonne, que es el CEO operativo y un auténtico genio construyendo empresas de ingeniería. Yo participo intensamente como cofundador y presidente, ayudando en la estrategia, el producto, la visión y la expansión internacional.

</details>

**大卫·弗里德伯格 (David Friedberg)**: 我们来算一笔经济账。每位受检者每年的费用大约是 500 美元（在欧洲约合 299 英镑/欧元）。如果把这个模式推广到全体美国人，全美 3.3 亿人口每年在这项预防扫描上的总支出大约是 1600 亿美元，这只占到目前美国每年近 4.5 万亿美元医疗总开支的 3% 到 4%。你们做过这方面的宏观测算吗？它对降低国家整体医疗赤字会产生怎样的深远影响？

<details>
<summary>Original English</summary>

**David Friedberg**: Hablemos de los costos. A unos 500 dólares al año, si todos los estadounidenses se hicieran este escaneo anualmente o cada dos años, representaría entre el 4% y el 8% del gasto médico total de Estados Unidos. ¿Habéis calculado el impacto que tendría esa inversión preventiva en reducir el coste astronómico de los tratamientos hospitalarios tardíos?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 答案是极其惊人的。现阶段 500 美元的年费对很多人来说依然是一笔实质性的开销，但我们之所以能够把高精度的全身扫描压低到这个价位，核心秘密就在于**全栈垂直整合（Vertical Integration）**。

传统医疗体系的仪器设备往往由通用电气（GE）、西门子或飞利浦等巨头层层分包制造，中间叠加上医院采购的暴利回扣与繁琐的保险审批流程，做一次全身磁共振或断层扫描动辄需要数千甚至上万美元。而 Neko 坚持自主研发传感器主板、自主编写算法、自建诊所并自行雇佣培训医护人员。

这种高度整合使我们能够彻底砍掉中间商的水分。我们现在的单体诊所从财务模型上看已经实现了**全面盈利**。随着硬件生产规模从千台级向百万台级迈进，我们的单次硬件摊销和运营边际成本还将继续呈现摩尔定律式的断崖式下降。我们坚信，未来的预防性全身健康检查，完全可以变得像手机年费套餐一样普惠可及。

<details>
<summary>Original English</summary>

**Daniel Ek**: Absolutamente. La gran ventaja de nuestra integración vertical es que diseñamos y construimos todo nosotros mismos: el hardware, el software y la experiencia en la clínica. Eso elimina todos los márgenes abusivos de los intermediarios médicos tradicionales. Hoy en día nuestras clínicas ya son rentables con esa tarifa de 500 dólares al año. Y a medida que escalemos la fabricación de las cabinas y optimicemos la automatización mediante IA, esos costos unitarios seguirán bajando drásticamente. El ahorro que supone detectar a tiempo una cardiopatía o un cáncer antes de que requiera cirugía abierta o quimioterapia hospitalaria de cientos de miles de dólares es monumental para todo el sistema económico.

</details>

### 美国医疗工业复合体的根深蒂固扭曲

**大卫·弗里德伯格 (David Friedberg)**: 既然经济逻辑如此清晰，那为什么以美国为代表的现有医疗体制会病入膏肓到这种地步？在急诊室缝两针为什么敢收 15,000 美元？生产成本只要 30 美元的胰岛素或普通药物，转手为什么能卖出 20,000 美元的天价？即便一位主治医师年薪只有 20 万美元，为什么门诊看病 8 分钟，保险公司账单上却敢列出 6,000 美元的费用？如果你有幸成为一天的“美国医疗总监”，拥有无上权力，你会开出怎样的改革药方？

<details>
<summary>Original English</summary>

**David Friedberg**: Si miras el sistema estadounidense, el costo del servicio en urgencias es de 15.000 dólares por unos puntos. Una medicina que cuesta 30 dólares fabricar se factura a 20.000 dólares. Si un médico gana 200.000 dólares al año, una visita de 8 minutos le cuesta a la aseguradora 6.000 dólares. ¿Por qué está tan roto este complejo médico-industrial y qué harías tú si fueras el emperador de Estados Unidos por un día para arreglarlo?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 根本问题在于**激励机制的彻底倒错（Misaligned Incentives）**。现在的医疗保险与医院体系本质上是建立在“按服务项目收费（Fee-for-Service）”的模式之上的。简单来说：你做的检查越多、开的药越贵、病人在重症监护室（ICU）住得越久，医院和相关利益集团赚到的钱就越多。健康的人无法为这个庞大的机器创造利润，只有生病的人才能成为产生现金流的资产。

另一个鲜为人知的致命漏洞在于**商业保险的投保人流动周期**。在美国，平均一名雇员每隔 2 到 3 年就会更换工作，进而更换医疗保险公司。假设 UnitedHealthcare 或 Aetna 今天为你投入 500 美元做预防性筛查，帮你改善了身体指标，防止你在 10 年后突发心肌梗死；但 10 年后你早就跳槽换成了另一家保险公司。换句话说，当期投入预防成本的保险公司承担了费用，而享受节约大笔医疗赔付收益的却是另一家竞争对手！这种极其短视的结算机制，导致没有商业保险机构愿意为长期的预防医学买单。

这也是为什么 Neko 选择绕开错综复杂的传统医保报销体系，直接面向终端消费者（Direct-to-Consumer）。同时，我们坚持将每一年的临床筛查数据进行去标识化汇总，主动向全社会公开发布年度健康白皮书。唯有把透明真实的数据晒在阳光下，让全社会清楚看到早期干预带来的真实生命获益，我们才能倒逼这个僵化的体制走向变革。

<details>
<summary>Original English</summary>

**Daniel Ek**: El problema central es que los incentivos están completamente desalineados. Todo el sistema médico tradicional opera bajo el modelo de "pago por servicio" (fee-for-service): los hospitales y las farmacéuticas ganan dinero cuando estás enfermo y recibes tratamientos caros, no cuando te mantienes sano. Además, en Estados Unidos la gente cambia de aseguradora cada 2 o 3 años debido al cambio de empleo. Si una aseguradora invierte hoy 500 dólares en tu prevención, los beneficios financieros de evitar un infarto ocurrirán dentro de diez años, cuando probablemente estés en otra aseguradora distinta. Por eso no existe ningún incentivo económico en el sistema para invertir en prevención a largo plazo. Por eso nosotros fuimos directos al consumidor y publicamos nuestros datos anualmente de manera transparente: para demostrar con hechos que la prevención funciona y cambia vidas.

</details>

### 伦敦与斯德哥尔摩人群健康数据对比

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 你们目前在瑞典斯德哥尔摩和英国伦敦都开设了旗舰诊所。在分析这两个完全不同都市的人群数据时，你们观察到了哪些有趣的异同？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Tenéis clínicas en Estocolmo y en Londres. ¿Qué diferencias o patrones habéis aprendido al comparar las poblaciones de esas dos grandes ciudades?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 这两座城市的人群生活方式差异非常显著，并在生理指标上得到了直接映射。斯德哥尔摩的人群普遍拥有较高的户外活动习惯、更为均衡的饮食作息以及较低的日常心理压力，因此在血管弹性及心血管基础指标上表现更为优异。

相比之下，伦敦作为一个节奏极快、高压力的国际金融枢纽，受检人群的心血管生物学指标普遍呈现出较高的皮质醇压力特征，微循环阻力较大，动脉脉搏波硬化指标偏高的比例明显更频繁。通过跨区域的大规模多模态数据比对，我们可以极具说服力地向都市人群证实：长期的城市生存压力与生活节律失衡，是如何在器质性病变发生前，就已经在人体的血管与细胞层面上留下了清晰可辨的生理烙印。

<details>
<summary>Original English</summary>

**Daniel Ek**: La comparación entre Estocolmo y Londres es fascinante. En Estocolmo vemos una población con estilos de vida más activos al aire libre, mejores hábitos de descanso y niveles de estrés basal más bajos, lo que se refleja en una mejor salud arterial. En Londres, con el ritmo implacable de una metrópoli financiera global, observamos una prevalencia significativamente mayor de marcadores de estrés cardiovascular, rigidez vascular temprana y alteraciones en el sueño. Los datos demuestran de manera irrefutable cómo el estrés crónico urbano deteriora la biología humana mucho antes de que aparezcan los primeros síntomas clínicos.

</details>

### 穿戴设备与临床级多模态扫描的互补性

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 很多人手上戴着 Apple Watch，手指上戴着 Oura Ring 或 Whoop 手环。你们未来是否打算自己推出 Neko 品牌的穿戴式硬件？你如何看待穿戴设备与你们全身扫描舱之间的关系？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Mucha gente usa Apple Watch, Whoop o anillos Oura hoy en día. ¿Tiene sentido que Neko cree sus propios dispositivos portátiles o cómo encajan con vuestra cabina de escaneo?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 我们非常推崇这类消费级穿戴设备。但我们自己**绝对不会去重复造轮子做手环**。

两者的定位是高度互补的。消费级穿戴设备的核心价值在于“连续的高频趋势监测（Continuous Trends）”——比如你每晚的睡眠分期、静息心率变异性（HRV）以及每日步数。但受限于体积、电量和传感器原理，穿戴设备无法提供深度的临床级诊断依据。你不可能指望一块手表能看清你后背微米级的恶性黑色素瘤，也不可能测出深层内脏脂肪分布或全身动脉管壁的精准硬化常数。

Neko 提供的是“**极高分辨率的年度黄金基准线（High-Resolution Annual Baseline）**”，而穿戴设备则是“日常的纵向高频脉搏”。两者结合，才能构成对一个人健康全景的完整数字孪生（Digital Twin）。

<details>
<summary>Original English</summary>

**Daniel Ek**: Me encantan esos dispositivos, pero nosotros no tenemos ninguna intención de construir hardware portátil. Cumplen propósitos distintos y complementarios. Los wearables son fantásticos para capturar tendencias diarias de alta frecuencia: cómo dormiste anoche, tu variabilidad de la frecuencia cardíaca (HRV) o tus pasos. Pero un reloj no puede medir la rigidez de tus arterias con precisión clínica ni hacer un mapeo dermatológico submilimétrico de tu cuerpo entero. Neko proporciona la línea base de alta resolución y grado clínico una vez al año, y los wearables complementan ese cuadro con el seguimiento diario.

</details>

### 人工智能演进：模型前沿、算力定律与安全边界

**大卫·弗里德伯格 (David Friedberg)**: Daniel，让我们把视野稍微拉宽一些，聊聊整个科技行业以及目前处于风口浪尖的人工智能。你如何看待前沿基座模型的发展趋势？目前关于大语言模型是否即将撞上算力或数据墙的争论不绝于耳，你对此有何见解？

<details>
<summary>Original English</summary>

**David Friedberg**: Daniel, ampliando el foco a toda la industria tecnológica: ¿cómo ves la evolución de la inteligencia artificial en este momento? Hay mucho debate sobre los modelos de frontera, si estamos llegando a un límite de escala o hacia dónde se dirige el futuro. ¿Cuál es tu perspectiva?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 很多人在讨论 AI 时往往过度关注单一的基准测试分数。但根据我的观察，真正的核心关键始终在于**计算总量的规模定律（Compute Scaling Laws）**。

让我惊讶的是，很多人似乎还没有充分意识到模型训练与推理背后的总算力消耗对模型能力涌现的决定性作用。如果一个系统调动了 10 万张先进图形处理器（GPU）进行海量合成数据微调与深度推理链（Chain-of-Thought）强化学习，它所展现出的推理深度和逻辑稳健性，是那些轻量级模型完全无法企及的。

同时，我们正在从单一文本模式加速迈向**真正的原生多模态（Native Multimodal）与环境语音交互（Ambient Voice）时代**。在不久的将来，人机交互的范式将被彻底颠覆。你不再需要对着键盘打字，你可以随时随地与能够实时观察周围环境、理解多模态传感器信号的超高智力系统进行自然流畅的语音对话，而医疗诊断、科学发现等垂直深水区将成为这项技术释放最大社会价值的主战场。

<details>
<summary>Original English</summary>

**Daniel Ek**: Creo que muchas veces la discusión pública se pierde en detalles superficiales. Para mí, la métrica fundamental sigue siendo el volumen total de cómputo invertido en el entrenamiento y en el tiempo de inferencia. Cuando despliegas 100.000 GPUs optimizadas para razonamiento continuo y datos sintéticos avanzados, las capacidades emergentes son asombrosas. Además, la transición hacia la voz ambiental y el procesamiento multimodal nativo cambiará por completo la interfaz de usuario: interactuar con la IA de manera fluida y conversacional en tiempo real se convertirá en la norma. Y las ciencias aplicadas, como la biología y la medicina, serán las grandes beneficiarias de esta capacidad de cálculo.

</details>

### 开源与闭源 AI 的竞争格局

**大卫·弗里德伯格 (David Friedberg)**: 那么在开源（Open Weights）与闭源（Proprietary API）AI 模型的路线之争上，你持有怎样的立场？

<details>
<summary>Original English</summary>

**David Friedberg**: ¿Y cuál es tu postura respecto al debate entre la inteligencia artificial de código abierto frente a los modelos propietarios cerrados?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 回顾整个计算机工业的技术演进史，开放生态与封闭体系始终处于一种既博弈又共生的动态平衡之中，比如 Linux 与 Windows、Android 与 iOS。历史从未出现过非此即彼的绝对零和结局。

开源模型对于保障全球技术民主化、防止寡头技术垄断、激发开发者社区的底层创新以及保障国家级技术主权至关重要。但与此同时，前沿尖端模型的研发需要动辄数百亿美元的基础设施资本开支与极其严密的国家安全审查边界。

我认为两者的共存不仅不可避免，而且对生态系统的长远健康大有裨益。前沿闭源实验室不断推高智力上限的天花板，而开源社区则以极快的速度跟进，将成熟的技术架构普惠到千行百业的每一个应用边缘。

<details>
<summary>Original English</summary>

**Daniel Ek**: La historia de la tecnología siempre ha sido una danza pendular entre lo abierto y lo cerrado: Linux coexistiendo con Windows, o Android con iOS. No creo que vaya a haber un ganador único. El código abierto es esencial para la soberanía técnica, la privacidad y la innovación descentralizada de los desarrolladores. Al mismo tiempo, los laboratorios propietarios que invierten decenas de miles de millones en supercúmulos de cómputo seguirán empujando la frontera absoluta de la inteligencia artificial. Ambos modelos coexistirán y se retroalimentarán mutuamente.

</details>

### 播客生态的开放性与平台化演变

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 谈到开放生态，Spotify 作为全球最大的音频流媒体巨头，同时也是全球播客消费的核心分发平台。但行业内始终存在一种争论：究竟是应该坚持传统基于 RSS 的开放分发协议，还是应该像 YouTube 或某些应用那样，把内容和受众锁在自己的专属围墙花园之内？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Hablando de sistemas abiertos, Spotify es un gigante indiscutible en la distribución de podcasts. Pero siempre hay debate sobre si los podcasts deben seguir basados en estándares abiertos de RSS o si plataformas como Spotify y YouTube deben crear ecosistemas cerrados. ¿Cuál es vuestra visión sobre el futuro del podcasting?

</details>

**丹尼尔·埃克 (Daniel Ek)**: Spotify 从创立的第一天起，就坚决拥抱开放标准。直到今天，无数创作者依然是通过标准开放的 RSS 协议，使用我们的托管工具将节目一键分发到全球所有其他播客客户端。

我们从来没有把自己视作封闭的垄断孤岛。我们的核心哲学在于：创作者拥有自由选择的权利。如果你希望使用开放协议全网分发，我们提供最强大的开放支持工具；如果你希望利用 Spotify 的原生交互能力——比如高清视频播客、即时评论互动、精准动态广告变现和粉丝付费订阅——我们便为你提供超越传统 RSS 限制的下一代沉浸式平台体验。

开放标准保证了生态的自由与多样性底线，而平台级创新则探索了用户体验与商业变现的上限。这两者从来都不是非黑即白的对立面。

<details>
<summary>Original English</summary>

**Daniel Ek**: En Spotify siempre hemos creído firmemente en los estándares abiertos. A través de nuestras plataformas de creadores permitimos que los podcasters distribuyan sus contenidos a cualquier otro lugar mediante RSS abierto. Creemos que ambos mundos pueden y deben coexistir. El estándar abierto garantiza la libertad y la universalidad del medio, pero si los creadores quieren monetizar mejor, tener video interactivo, encuestas o comentarios en tiempo real, nosotros les brindamos esa infraestructura avanzada dentro de Spotify.

</details>

### 早期创业经历与 Stardoll 岁月

**杰森·卡拉卡尼斯 (Jason Calacanis)**: Daniel，回顾你的个人经历，你在二十出头的时候还曾在 **Stardoll** 担任过高管，经历过早期的互联网摸索。回首当年那段经历，你学到的最宝贵教训是什么？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Mirando hacia atrás en tu carrera, cuando tenías 20 o 22 años trabajaste como CTO o asesor en Stardoll y otras empresas antes de Spotify. ¿Qué lecciones fundamentales aprendiste de esos primeros años como joven tecnólogo?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 那些早期的实战经历是极其残酷却无价的财富。在 Stardoll 期间，面对数千万狂热的年轻用户涌入，我亲身体会到了什么叫真正的系统高并发瓶颈与产品网络效应。

但我学到的最核心的一课，其实是关于**产品与用户的同理心（Empathy）**。作为一个年轻的技术狂热分子，你很容易陷入纯粹的技术执念中，认为写出最优雅的代码就等于成功。然而现实会狠狠给你上一课：技术的唯一价值在于它究竟以多低的门槛、多优雅的交互，解决了真实世界中普通人的真实痛点。无论当年的音乐流媒体，还是今天的 Neko Health 全身预防扫描，底层的逻辑如出一辙：把极其复杂的技术和工程留在看不见的冰山之下，把极致简单、直观且充满人文关怀的体验交付给用户。

<details>
<summary>Original English</summary>

**Daniel Ek**: Aprendí que la tecnología en sí misma no es nada si no está al servicio de una experiencia de usuario transformadora. Cuando eres joven e ingeniero, te enamoras de la arquitectura del código o de la infraestructura técnica. Pero en Stardoll y en las primeras empresas aprendí que la clave de cualquier producto exitoso es la empatía humana: cómo hacer que algo enormemente complejo por detrás se sienta completamente invisible, mágico y sencillo para el usuario final. Esa misma filosofía es la que aplicamos en Spotify y la que ahora guía cada detalle en Neko Health.

</details>

### Neko Health 扩展计划与全篇结语

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 那么对于我们广大收听节目的听众，如果大家想要预约 Neko Health 的全身扫描，目前应该去哪里？你们在美国有具体的落地开设计划吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Para todos los oyentes que nos están escuchando y quieran experimentar el escaneo de Neko Health, ¿dónde pueden apuntarse? ¿Cuándo estaréis disponibles en Estados Unidos?

</details>

**丹尼尔·埃克 (Daniel Ek)**: 大家可以直接访问 **Nekohealth.com**，加入我们的全球候补名单（Waitlist）。

我们在欧洲目前依然处于供不应求的状态，数万人正在排队预约。但让大家感到振奋的是，我们目前正在全力筹备进军美国市场。我们在纽约市的休斯顿街（Houston Street）已经选定了第一家美国旗舰诊所的地址，施工与审批正在紧锣密鼓地推进中。在接下来的 12 到 24 个月内，我们不仅会正式点亮纽约诊所，还将陆续向美国更多核心城市全面铺开。

<details>
<summary>Original English</summary>

**Daniel Ek**: Cualquiera puede visitar Nekohealth.com e inscribirse en nuestra lista de espera. Actualmente tenemos una gran demanda acumulada en Europa, pero nos estamos preparando activamente para expandirnos a Estados Unidos en los próximos 12 a 24 meses. Ya hemos elegido la ubicación de nuestra primera clínica en Nueva York, en Houston Street. Estamos muy emocionados de traer este nuevo paradigma de salud preventiva a Norteamérica.

</details>

**杰森·卡拉卡尼斯 (Jason Calacanis)**: 纽约休斯顿街，那可真是个传奇的好地方。当年很多伟大的先锋工作室就在那附近。非常祝贺你们取得的卓越进展。所有人请记住访问 Nekohealth.com 并注册候补名单。Daniel，非常感谢你今天的坦诚分享，期待下次再会。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Sí, eso es genial, justo en Houston Street, una zona con tanta historia. Enhorabuena por todo el éxito, Daniel. Visiten Nekohealth.com y regístrense en la lista de espera. Muchas gracias por acompañarnos, nos vemos la próxima vez. Adiós. Voy a apostarlo todo.

</details>

**丹尼尔·埃克 (Daniel Ek)**: 感谢大家，再见。

<details>
<summary>Original English</summary>

**Daniel Ek**: Hasta luego. Adiós.

</details>