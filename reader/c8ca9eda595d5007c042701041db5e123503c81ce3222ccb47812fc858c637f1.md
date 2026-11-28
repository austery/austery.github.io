---
author: How I AI
date: '2026-09-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LMT-bknLmNo
speaker: How I AI
tags:
  - large-language-model
  - benchmark-testing
  - blind-test
  - cost-optimization
title: Opus 5.5 与 GPT-6 多模型发布及现场盲测对比
summary: 作者针对最新发布的 Anthropic Opus 5.5 以及 OpenAI 的 GPT-6 系列模型开展直播测评与盲测，探讨了模型的定价、缓存成本效益、安全限制及性格差异，并在重构的基准测试中对比了各模型在 PRD、SVG 角色生成与日常任务中的具体表现。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Opus 5.5
  - GPT-6 Soul
  - GPT-6 Luna
  - Claude Opus 5
  - Astra
  - Fábula
media_books: []
status: evergreen
---
<!-- chunk 1/5 -->

### 突发模型发布与直播测评准备

我尽量做好了准备——Anthropic 将发布 Opus 5.5。我甚至也做好了准备迎接 OpenAI 将发布另一个模型的事实。我今天一大早就起床了，因为提前拿到了 Opus 5.5 的访问权限，想为大家录制一期精彩的评测。你猜怎么着？它们两个今天早上同时发布了。所以现在，尽管我对 Opus 5.5 做好了精彩的评测（你们稍后会看到），我还是打算直接开这场直播。我以前从来没做过直播。所以，我来给大家讲讲这些新模型。

<details><summary>Original English</summary>
Estuve 

en 

la 

medida 

de 

lo 

posible





listo 

para 

eso





Anthropic 

lanzará 

Opus 

5.5.





Yo 

incluso 

estaba 

listo





al 

hecho 

de 

que 

OpenAI





lanzará 

otro





modelo. 

Me 

levanté.





temprano 

esta 

mañana,





porque 

tuvo 

acceso 

anticipado





hasta 

Opus 

5.5 

para 

grabar





increíble 

para 

ti





revisar. 

¿Y 

adivina 

qué?





Ambos, 

ellos





ambos 

salieron





esta 

mañana. 

Entonces





ahora, 

a 

pesar 

del 

hecho 

de 

que 

en





Estoy 

listo.





Excelente 

reseña 

de 

Opus 

5.5,





que 

verás





más 

tarde, 

yo 

solo





Voy 

a 

presentar 

esta 

transmisión 

en





transmisión 

en 

vivo. 

Y 

yo





nunca 

había 

liderado 

antes





transmisiones 

en 

vivo. 

Así 

que 

yo





Te 

lo 

voy 

a 

decir.





te 

acerca 

de 

estos 

nuevos





modelos.
</details>

今天发布了三款模型：Anthropic 的 Opus 5.5、GPT-6 Soul 和 GPT-6 Luna。这里的价格战还在继续。我还没针对“我如何用 AI”做专题节目，不过刚为这些新模型做了更新，我们会在直播中一起看看它们。我们会快速过一遍，因为是针对模型以及外界对它们的评价，然后我打算在直播中做氛围测试。我们将进行盲测。在直播中给你带来惊喜。你将能看到我所有内心的矛盾，我们来看看一切会如何发展。所以，Claude Opus 5.5、GPT-6 Soul 和 GPT-6 Luna——我有机会提前测试了这些模型。所以我很清楚它们强在哪里，但是……

<details><summary>Original English</summary>
Hoy





Se 

lanzaron 

tres 

modelos: 

Opus





5.5 

de 

Anthropic, 

GPT-6 

Soul 

y





GPT-6 

Luna. 

Aquí 

continúan





guerras 

de 

precios, 

aún 

no 

lo 

he 

hecho





Hicieron 

un 

episodio 

sobre 

Cómo 

yo 

IA





pero 

recién 

actualizado





es 

para 

estos 

nuevos





modelos, 

y 

nosotros





Vamos 

a 

echarles 

un 

vistazo.





Transmisión 

en 

vivo 

juntos.





Caminaremos 

rápido.





porque 

es 

para





modelos 

y 

qué 

hay 

de 

ellos





dicen, 

y 

entonces 

yo





Voy 

a 

hacer 

una 

prueba 

de 

ambiente.





vivir. 

Pasaremos





prueba 

a 

ciegas. 

Te 

sorprenderé.





Vive 

tú 

mismo.





Podrás 

ver





todo 

mi 

interior





contradicciones, 

y 

nosotros





Veamos 

cómo





Todo 

desaparecerá. 

Entonces, 

Claude 

Opus





5.5, 

GPT-6 

Soul 

y 

GPT-6 

Luna—I





tuvo 

la 

oportunidad





prueba 

estos





modelos 

por 

adelantado.





Entonces 

lo 

entiendo 

muy 

bien, 

en





¿Por 

qué 

son 

fuertes, 

pero...?
</details>

### 基准测试重构与现场盲测设计

我认为现在是一个重要节点。Astra 发布并更新了 Fábula。我想彻底重新构思“我如何用 AI”的基准测试，因为如果你看过我们以前的节目，它们集中在两件事上：PRD 和原型。但我认为这些模型正变得更聪明、更具智能体特性，因此我为这次盲测开发了更广视角的基准测试。我会讲讲它是如何运作的，也想听听大家对于这些对比是否有用的看法。而且我们真的会在直播间当场进行盲测。你可以评估我的审核有多客观。这很简单，就是我们做决定的方式，因此它并不完美。中间引入了一个法学硕士（LLM）来担任裁判，但我们现场实测，看看会发生什么。我最喜欢哪个模型。但在那之前，让我们先来过一下主要要点。

<details><summary>Original English</summary>
Creo 

que 

ahora





Punto 

importante.





Astra 

lanzado 

y 

actualizado





Fábula. 

Yo 

quería





 completamente





 repensar





punto 

de 

referencia 

Cómo 

yo 

IA, 

porque





si 

viste 

el 

nuestro





episodios 

antiguos, 

ellos





estaban 

centrados 

en





dos 

cosas: 

PRD 

y





prototipos. 

Pero 

yo





Creo 

que 

estos 

modelos





se 

están 

volviendo 

más 

inteligentes 

y





más 

agente, 

por 

lo 

tanto





Desarrollé 

una 

perspectiva 

más 

amplia





punto 

de 

referencia 

para 

esto





prueba 

a 

ciegas. 

I





Te 

voy 

a 

contar 

cómo 

es.





funciona, 

y 

quiero 

escuchar





tu 

opinión 

sobre 

si





Estos 

son 

útiles





comparación. 

Y 

nosotros





realmente 

gastaremos





prueba 

a 

ciegas 

en 

directo





en 

el 

aire. 

Podrás





para 

evaluar 

cuánto





El 

mío 

es 

objetivo.





auditoría. 

Es 

sencillo.





la 

forma 

en 

que 

nosotros





tomamos 

decisiones,





Por 

lo 

tanto, 

es 

imperfecto.





Existe 

un 

máster 

en 

Derecho 

(LLM) 

para 

ser 

juez.





en 

el 

medio, 

pero 

nosotros





Hagámoslo 

en 

vivo 

y





Ya 

veremos 

qué 

pasa.





Me 

encanta 

el 

modelo.





mayoría. 

Pero 

antes





demos 

esto





Vamos 

a 

dar 

un 

paseo





puntos 

principales.
</details>

### 定价、缓存与成本效益

好吧，它们并不完全是那种前沿进阶模型。不是 Astra 也不是 Fábula，而是 Opus、Soul 和 Luna 迎来了更新。所有模型都变得更便宜、更快了。因此它们将成为大家在编程和智力任务中的日常助手。在这里你可以看到这些模型的成本评级。Opus 5.5 几乎比 GPT-6 Soul 贵了一倍。我在测试它们的时候价格还不得而知，而这对我使用它们的决定将产生重大影响。再次说明，是的，Opus 5.5 比用来对比智能水平的 Fábula 1 上的 Opus 5 更便宜。但 Soul，你知道的，是我的挚爱。咳咳。对此我非常欣喜，因为 GPT-6 Soul 是我的最爱而且很便宜。因此，最核心的、它们所专注的——不仅是降低成本，还有对缓存输入的处理、速度以及 token 效率。你将会看到输出量的减少、token 的使用量以及成本。这真的非常棒。而且缓存效果极其出色。尤其是当你重新发送上下文时，我们在 PRD 对话中使用所有这些模型看到了巨大的缓存节省。再者，如果你是基于这些模型进行开发，请务必确保缓存得到优化并善用这一优势，因为这能省下很多钱。如果不这样做，我深信这可能会让你付出高昂代价。

<details><summary>Original English</summary>
Bueno, 

no 

es 

exactamente 

eso.





modelos 

avanzados. 

Él





no 

Astra 

ni 

Fábula, 

sino 

Opus,





Alma 

y 

Luna 

recibieron





renovación. 

Todos





se 

volvió 

más 

barato 

y





más 

rápido. 

Entonces 

ellos





se 

convertirá 

en 

tuyo





 a diario





asistentes 

en





programación 

y





 intelectual





tareas. 

Aquí 

tiene.





ver 

la 

calificación





el 

costo 

de 

estos 

modelos.





Opus 

5.5 

casi 

duplica





Más 

caro 

que 

el 

GPT-6 

Soul.





Los 

precios 

no 

se 

conocían,





cuando 

los 

probé 

y





Esto 

tendrá 

un 

impacto 

significativo.





mi 

decisión 

respecto 

a 

ellos





usando. 

De 

nuevo





Sí, 

Opus 

5.5 

es 

más 

barato 

que





Opus 

5 

en 

Fábula 

1, 

con 

el 

que 

ellos





comparar 

la 

inteligencia.





Pero 

Soul, 

ya 

sabes, 

es 

mío.





amado 

mío





amar. 

Ejem. 

Estoy 

en





encantado 

con 

esto,





Porque 

GPT-6 

Soul 

es 

mío





Mi 

favorito 

y 

es 

barato.





. 

Entonces, 

lo 

principal 

es,





¿Por 

qué 

son 

ellos?





enfocado—no 

lo 

es





solo 

disminuir





costo, 

pero 

también 

trabajar 

con





entradas 

almacenadas 

en 

caché,





velocidad 

y





eficiencia 

del 

token





. 

Ya 

verás





reducción 

de 

volumen





salida, 

usar





fichas 

y 

costos. 

Él





Realmente 

muy 

bueno. 

Y





El 

almacenamiento 

en 

caché 

funciona





perfectamente. 

Especialmente 

si





tú 

envías





contexto 

nuevamente, 

nosotros





vi 

uno 

grande





ahorros 

en





almacenamiento 

en 

caché,





usando 

todo





estos 

modelos 

en 

el 

chat 

PRD. 

Atrás





si 

estás 

desarrollando





basado 

en 

estos 

modelos





, 

asegúrese 

de 

que





tus 

cachés





optimizado 

y 

tú





usa 

esto





ventaja, 

porque 

puede





ahorra 

mucho





dinero. 

Y 

si 

no, 

¿cómo 

lo 

hago?





convencido 

de 

que 

puede





te 

costará 

mucho.
</details>

### 安全限制、对齐与模型性格

另一件我想提请注意的事——再次说明，我讨厌 Claude 生成的这个演示文稿——这就是我想让大家关注的：左边 Opus 5.5 的部分。Opus 5.5——这是顶级的 Opus 模型，在网络安全和生物学领域脱离了 Fábula 级别的防护机制。你可以在 Opus 5.5 中自行纠错，但在涉及网络安全或生物学领域时却无法做到，你懂吗？它会把你降级切到 Opus 4.8，或者直接拦截。所以只需知晓存在这样的限制即可。Anthropic 坚称这是他们最对齐的模型。它是在取得突破性成果后打造的模型，因此由外部专家进行了检验。呃，有一点是我在 Opus 上注意到的，也是对 Anthropic 众多模型的预期，那就是它依然带有些许保守和说教。你会在我的 Opus 5.5 评测中看到这一点。所以，你知道的，它就是会直接对你说“不”。它会说类似于“我不应该做这个”之类的话。提示词注入是行不通的，这挺好。嗯，但存在某些细微差别。当你思考这些模型的整体哲学和方法论、它们如何被配置、如何管理风险，以及这些公司如何管理风险时。我认为这种管控甚至延伸到了完全没有风险的活动、个性和行为上。所以这就是我认为值得关注的地方。

<details><summary>Original English</summary>
Otra 

cosa 

que 

yo





quería 

llamar 

la 

atención





—y 

de 

nuevo, 

yo





Odio 

esto





presentación,





creado 

por 

Claude—esto 

es 

lo 

que





¿Qué 

quiero 

que 

hagas?





enfocado: 

izquierda





del 

lado 

de 

Opus 

5.5. 

Opus 

5.5—





Este 

es 

el 

modelo 

de 

primer 

nivel





Opus, 

que 

surgió 

de





mecanismos 

de 

protección





Nivel 

de 

fábula 

en 

el 

campo





ciberseguridad 

y





biología. 

Podrás





corregir 

el 

propio





errores 

en 

Opus 

5.5, 

pero 

no





podrás 

hacerlo





trabajando 

con





ciberseguridad 

o





biología, 

¿lo 

haces?





elección. 

Ella 

lanzará





usted 

en 

Opus 

4.8 

o





bloqueará. 

Así 

de 

simple





saber 

que 

tal





Existen 

restricciones.





Antropía 

afirma 

que 

esto





su 

más





modelo 

acordado. 

Él





y 

el 

modelo 

que





creado 

después





logros 

avanzados





resultados, 

por 

lo 

tanto 

su





comprobó 

el 

exterior





expertos. 

Eh, 

una 

cosa.





, 

lo 

cual 

noté 

en 

Opus, 

y





qué 

esperar





de 

muchos 

modelos





Antrópico, 

eso 

es 

lo 

que 

es.





Queda 

algo





conservador 

y





instructivo. 

Tú





Lo 

verás 

en 

el 

mío





Reseña 

de 

Opus 

5.5. 

Entonces,





ya 

sabes, 

ella 

es 

simplemente





te 

dirá 

"no". 

Ella





dirá 

algo 

como





"No 

debería 

hacer 

esto."





hacer". 

Indicación-





Las 

inyecciones 

no 

funcionarán.





y 

eso 

es 

bueno. 

Hmm, 

pero 

hay





ciertos 

matices. 

Cuando 

tú





pensando 

en 

lo 

general





filosofía 

y 

enfoques





estos 

modelos, 

cómo 

ellos





configurados 

como 

están





gestionar 

riesgos, 

como





estas 

empresas 

gestionan





riesgos. 

Creo 

que 

esto 

es





se 

extiende 

incluso





sin 

riesgo 

alguno





actividad,





personalidad 

y





comportamiento. 

Así 

que 

esto 

es 

todo,





a 

lo 

cual, 

en 

mi 

opinión,





vale 

la 

pena 

prestar 

atención





atención.
</details>

### 日常使用体验与沟通交互对比

实际上我有好几个月没在日常任务中打开过 Claude 了。我对 ChatGPT 印象非常非常深刻，热衷于 Cohere，沉迷于 Astra 和 Soul。在我看来，配合 harness 使用更加舒心，但我在日常生活中放弃 Claude 的真正原因是——在 Fábula 和 Opus 5 之间，我简直无法忍受与 Claude 的交流。我不断给 Claude 写道：“你能像个人一样说话吗？”我一直对 Fábula 说：“我听不懂你在说什么。”呃，我所称的“Claude 味废话”不断冒出来。所以，从个人人体工学和使用愉悦感的角度来看，我彻底转向了 Codex。现在先剧透一下，虽然最近抗议了所有这些模型，但我依然非常喜欢 GPT 模型。呃，它们让我更开心。用起来让我更舒心。咳咳，对我来说一切都在变好，但我回到了 Claude。所以，对于 Opus 5.5，剧透一下：在日常使用中，它重新回到了我的日常体验里。仅仅是与这个模型交流，我就感到开心得多。嗯，我给 Anthropic 团队的反馈是：它不再让人恼火了。我对 Opus 5.5 毫无烦躁之感。而每当我觉得自己被 Opus 5.5 惹恼时，其实都是碰巧错用了 Opus 5。所以，跟 Opus 5 交流根本毫无乐趣可言。相反，Opus 5.5 会给出清晰的列表项目符号，表现正常，不烦人。因此我希望大家能去亲自检验一下。

<details><summary>Original English</summary>
I





realmente 

no 

se 

abrió





Claude 

durante 

varios 

años





meses 

para





tareas 

cotidianas





. 

Yo 

estaba 

muy





Muy 

impresionado 

con 

ChatGPT,





entusiasta 

de 

Cohere, 

muy





Cautivado 

por 

Astra 

y 

Soul.





Me 

parece 

que,





con 

qué 

trabajar 

Arnés





más 

agradable, 

pero





la 

verdadera 

razón,





¿Por 

qué 

me 

rendí?





Claude 

en 

la 

vida 

cotidiana—





entre 

Fábula 

y 

Opus 

5 

I





Simplemente 

no 

pude.





para 

soportar 

la 

comunicación





con 

Claude. 

Estoy 

constantemente





Claude 

escribió: 

"Puedes





¿Hablar 

como 

un 

ser 

humano?





Seguí 

escribiendo 

Fábula:





"No 

entiendo 

de 

qué 

estás 

hablando."





"Hablas." 

Eh, 

"Claude-"





"basura", 

¿cómo 

lo 

hago?





Yo 

lo 

llamo,





 continuado





surgir. 

Entonces, 

con





desde 

la 

perspectiva 

del 

individuo,





ergonomía 

y





placer 

de





uso, 

yo





cambió 

completamente 

a





Códice. 

Ahora, 

spoiler,





protestando 

contra 

todos 

estos





modelos 

recientemente, 

yo





Todavía 

te 

quiero 

mucho.





Modelos 

GPT. 

Eh, 

ellos





Hazme





más 

feliz. 

A 

mí





más 

agradable 

con 

ellos





usar. 

Ejem,





Todo 

es 

importante 

para 

mí.





mejor, 

pero 

regresé





Claude. 

Entonces, 

Opus 

5.5,





spoiler: 

en





 cada día





usándolo





regresó 

de 

nuevo





mi 

diario





experiencia. 

Soy 

mucho





más 

feliz 

simplemente





de 

comunicarse 

con





este 

modelo. 

Hmm, 

mi





Comentarios 

para 

el 

equipo





Antropía: 

ya 

no 

lo 

es





irritante. 

Yo 

no 

soy 

ninguno





nunca 

sentí





irritación 

por 

Opus





5.5. 

¿Y 

cuándo 

debo 

hacerlo?





Me 

pareció 

que 

yo





Opus 

5.5 

molesto, 

yo





en 

realidad 

por 

casualidad





Opus 

5 

usado.





Así 

pues, 

con 

Opus 

5





comunicarse 

en 

absoluto





No 

es 

divertido. 

En 

cambio





Opus 

5.5 

ofrece 

una 

claridad





listas 

con 

viñetas,





se 

comporta 

normalmente





y 

no 

es 

molesto. 

Así 

que 

yo 

lo 

haría





Quería 

que 

lo 

tuvieras.





protestado.
</details>

### 响应速度、静默机制与 AI 评测基准拓展

另一件事——Opus 5.5 相当快，但没有 Soul 那么快。所以我能把两者都测试一番，而我总感觉 GPT 模型和 Codex harness 明显要更快一些。因此，我认为这种速度提升表现在两个方面。它体现在真实的延迟上。所以我确实认为 GPT Soul 跑得就是更快。第二点是因为他们让 Opus 5.5 变得不那么烦人的一部分做法，就是让它保持安静。我也刚刚意识到这一点：它不对自己的工作进行解说。当它不对自己的工作加以评论时，你就会陷入一种境地，心想：你到底在不在干活？你真的是这样运转的吗？所以 Opus 5.5 在交流上的这种改变既有优点也有缺点，这就是为什么实际感觉它比原本应有的速度更慢。此外，你知道的，在高负载下，Claude 就像是在努力使劲。它就像在原地打转、耗费巨大力气。所以我觉得这一点与更静默的模型相结合，就显得它稍慢了一些，而在我的感受中 Soul 提供了适度的过程解说，与它交流也很顺畅。让我们转到我对人工智能工作环境的评测。正如大家在左侧所看到的，实际上我大幅扩展了这项评测。现在它涵盖了大量的……

<details><summary>Original English</summary>
Otro





cosa—Opus 

5.5 

es 

bastante





rápido, 

pero 

no 

tan 

rápido





Rápido 

como 

un 

alma. 

Así 

que 

yo





pudo 

protestar





ambos, 

y 

yo





Siempre 

parecía





que 

los 

modelos 

GPT 

y 

Codex





Los 

arneses 

fueron 

significativamente





más 

rápido. 

Entonces, 

yo





Creo 

que 

esa 

aceleración





les 

sucedió 

a 

dos





categorías. 

Él





manifestado 

en





retraso 

real.





Así 

que 

realmente  Creo 

que,





que 

GPT 

Soul 

es 

simplemente





funcionó 

más 

rápido.





La 

segunda 

cosa 

es





porque 

parte 

de





la 

forma 

en 

que 

ellos





hizo 

que 

Opus 

5.5 

fuera 

más 

pequeño





molesto, 

fue,





que 

lo 

obligaron





guarda 

silencio. 

Yo 

también





Acabo 

de 

darme 

cuenta 

de 

eso.





él 

no 

comenta 

sobre 

su





trabajar. 

Y 

cuando 

no 

lo 

hace





comentarios 

sobre 

su 

trabajo,





te 

metes 

en 

un 

lío





una 

trampa 

donde 

piensas: 

si





¿Trabajas?





¿De 

verdad 

eres 

así?





¿Cómo 

estás? 

Así 

que 

en 

este 

cambio





Las 

comunicaciones 

de 

Opus 

5.5 

son 

como





ventajas 

y 

desventajas,





¿Por 

qué 

está 

él?





realmente 

lo 

sentí





más 

lento 

que, 

en





en 

mi 

opinión, 

fue





de 

hecho. 

También,





ya 

sabes, 

Claude 

en





 alto





carga, 

es





como 

si 

fuera





Haz 

esto. 

Él





como 

si 

estuviera 

"girando" 

y





pone 

mucho 

esfuerzo





esfuerzos. 

Y 

por 

eso 

creo





que 

esto 

se 

combina 

con





modelo 

más 

silencioso





simplemente 

lo 

hace





un 

poco 

más 

lento,





mientras 

sentía 

que





Alma 

proporcionada





nivel 

adecuado





comentando, 

así 

como





Fue 

agradable 

estar 

con 

él.





comunicar.





Pasemos 

a





mi 

reseña





ambiente 

de 

trabajo 

con





inteligencia 

artificial.





Como 

pueden 

ver,





a 

la 

izquierda, 

en 

realidad





amplió 

significativamente 

esto





revisar. 

Ahora 

él





cubre 

un 

montón 

de 

cosas 

en
</details>

<!-- chunk 2/5 -->

### 评估维度与预期

不同的类别，而且随着时间推移，我们还会加入更多类别。所以它既要能把凌乱的笔记整理成 PRD，又涉及个人生产力，比如对传入的信息进行分类以及日常的语音回复。所以我实际上正在测试这个模型，看看它是否能用我的口吻说话。

<details><summary>Original English</summary>
diferentes 

categorías 

y





Con 

el 

tiempo 

los 

tendremos





agregar. 

Así 

que 

él 

lo 

es 

todo





aún 

se 

transforma





notas 

descuidadas 

sobre





PRD. 

Él 

también





está 

involucrado 

en 

asuntos 

personales





productividad,





clasificación 

entrante





mensajes 

y





 rutina





mis 

respuestas





voz. 

Así 

que 

realmente





Estoy 

probando 

este 

modelo 

para





para 

ver 

si 

puede





Ella 

habla 

mi 

idioma





voz.
</details>

然后，我们当然经常做前端代码编写，因为我觉得这很直观、很容易看出来。我加了，呃，几个后端代码编写的任务。呃，单智能体对比多智能体集，对比后端功能。我又加入了语音智能体、长期研究、使用电脑，然后加了一些创意功能。所以我把它们全部汇总到了一起。我测试了很多模型。这不仅包括来自 OpenAI 和 Anthropic 的新模型，而且我认为还包括 Grok。我觉得 Muse 也在其中。所以谁知道会怎样呢，我们拭目以待吧。

<details><summary>Original English</summary>
Entonces,





Por 

supuesto, 

a 

menudo





Hacemos 

frontend-





codificación, 

porque 

yo





Creo 

que 

esto





visual 

y 

fácilmente





ver. 

Añadí, 

eh,





un 

par 

de 

tareas 

para





codificación 

del 

backend. 

Eh,





agentes 

contra





multiconjuntos 

de 

agentes





contra 

las 

funciones





backend. 

Yo 

otra 

vez





se 

convirtió 

en 

agente





voz, 

de 

larga 

duración





investigación,





 usando





computadora, 

y 

luego





añadió 

algo 

de 

creatividad





funciones. 

Entonces, 

yo





Los 

reunió 

a 

todos. 

I





protestó 

mucho





modelos. 

Esto 

incluye





no 

solo 

nuevos 

modelos,





eh, 

de 

OpenAI 

y 

Anthropic,





pero 

también, 

creo,





Esto 

incluye 

las 

rocas.





Creo 

que 

Muse 

también 

está 

aquí. 

Entonces





quién 

sabe 

lo 

que 

somos





Ya 

veremos.
</details>

呃，坦白说：我总是倾向于认为胜出的会是 Astra 还是 Soul？因为我很喜欢 OpenAI 的模型。内心无法左右自己的喜好。这是我的假设。以下是我的假设：呃，OpenAI 模型会在脑力工作和个人生产力方面让我满意。Anthropic 的模型，或者可能是 Grok，谁知道呢，会在界面方面让我满意。呃，不知道后端需要哪个能让我满意。我怀疑单个智能体你会更喜欢 Claude 模型。我怀疑长期智能体也会是 Claude 模型。至于使用电脑，我想会是 OpenAI，但对于创意任务——我甚至想象不出来。实际上，我认为创意 SVG 会是 Claude，而视频可能是 OpenAI 或 Anthropic。不过我们走着瞧。

<details><summary>Original English</summary>
Eh, 

lo 

haré.





Francamente: 

siempre





inclinado 

a 

pensar 

que





¿Ganará 

Astra 

o 

Soul?





porque 

me 

encanta





Modelos 

de 

OpenAI. 

El 

corazón 

no





Dime, 

¿qué 

es?





quiere. 

Este 

es 

mío.





suposición. 

Aquí 

está 

el 

mío.





suposición. 

Eh,





OpenAI 

me 

modela





le 

gustará





 intelectual





trabajo 

y 

personal





productividad.





Modelos 

antrópicos, 

tal 

vez





Grok, 

quién 

sabe, 

yo





le 

gustará





Interfaz. 

Eh, 

no.





Sé 

lo 

que 

necesito.





le 

gustará 

por





backend. 

Sospecho 

que





para 

el 

individuo





Necesito 

más 

agentes





Te 

gustará 

el 

modelo





Claude. 

Sospecho 

que





 a largo plazo





El 

agente 

será 

el 

modelo





Claude. 

De





 usando





computadora, 

creo 

que 

es





Habrá 

IA 

abierta, 

pero 

para





tareas 

creativas—





Ni 

siquiera 

puedo 

imaginarlo.





En 

realidad, 

creo 

que 

para





SVG 

creativo 

será 

Claude





y 

el 

video 

es 

probablemente





IA 

abierta 

o 

antrópica. 

Pero





Ya 

veremos.
</details>

### 盲测基准与个人生产力评估

所以我正在对这些模型进行盲测评估。我在不同模型上运行它们。在某种程度上，我当然根据模型的能力对它们进行了分组，这样我就可以比较相似的模型。比如说，我不想拿 Luna 和 Fabula 来比较。所以，这是我的测试基准。

<details><summary>Original English</summary>
Entonces 

yo





Estoy 

liderando 

a 

ciegas.





evaluación 

de 

estos





modelos. 

Entonces, 

yo





Los 

ejecuto 

en 

diferentes





modelos. 

Estoy 

seguro.





agrupados 

hasta 

cierto 

punto





modelos 

según 

sus





oportunidades. 

Así 

que 

yo





Puedo 

comparar





modelos 

similares 

entre





tú 

mismo. 

Digamos 

que 

no 

lo 

hago





Quiero 

comparar 

Luna





y 

Fábula. 

Así 

que, 

este 

es 

el 

mío.





banco 

de 

pruebas.
</details>

它们是匿名的。你看，我有模型 B、模型 C、模型 E、模型 G。然后我往下看。在这里，我给出一到五分的总评分，并留下简短的评语，例如：简单直接，当然，毫无怨言。我是针对 PRD 这么做的，因为阅读它需要一些时间，不过我们就快速过一遍，我会给出我的意见。

<details><summary>Original English</summary>
Son 

anónimos. 

Tú





Verás, 

yo 

tengo





modelo 

B, 

modelo 

C,





modelo 

E, 

modelo 

G.





Entonces 

bajo.





Aquí 

estoy 

publicando





calificación 

de 

uno 

a





cinco 

en 

total





Dejo 

huella.





notas 

breves,





por 

ejemplo: 

simplemente 

y





por 

supuesto, 

ninguno





quejas. 

Lo 

hice.





para 

PRD, 

porque 

su





leer 

toma





algún 

tiempo, 

pero 

nosotros





solo 

rápidamente





Vamos 

a 

revisarlos 

y 

yo





Daré 

mi 

opinión.
</details>

因此，下一个阶段——检验个人生产力。总的来说，我给它们虚构的电子邮件，并询问：“你会怎么回复我？如果我给你我的意见，你会怎么做？你会怎么整理我的邮件？”于是，模型 B 和模型 E 给我写了不错的邮件。篇幅挺长，但是是易于阅读的好邮件。我会说模型 B 写的是阅读体验最舒服的邮件。另外，如果你看信件的内容，废话更少。而且，它还添加了日历邀请。所以我要给这个模型打五分。

<details><summary>Original English</summary>
Por 

lo 

tanto,





siguiente 

etapa—





verificación 

personal





productividad.





En 

general, 

les 

doy





electrónica 

falsa





cartas 

y 

preguntar: 

"¿Cómo





¿Me 

responderías?





¿Qué 

harías 

si...?





Te 

di 

mi 

opinión 

y 

cómo





¿Lo 

ordenarías?





¿Mi 

correo? 

"Entonces,





modelo 

B 

y 

modelo 

E





me 

escribió





mensajes 

bonitos





. 

Eran 

largos,





pero 

estos 

eran 

buenos





mensajes 

que





Fácil 

de 

leer. 

Yo 

lo 

haría





dijo 

que 

el 

modelo 

B





escribió 

lo 

más 

conveniente





para 

leer





mensaje. 

También,





si 

miras





el 

contenido 

de 

la 

carta, 

allí





menos 

texto 

innecesario.





Además, 

añadió:





invitación 

a





calendario. 

Así 

que 

yo





Voy 

a 

poner 

este 

modelo





cinco.
</details>

这是我最喜欢的模型 C——我讨厌我的 Grok 也这么干：它使用的 token 实在太少了，以至于几乎不可能搞懂它到底是什么意思。而且虽然它很短，但如果你没有上下文，比如我，就根本不明白 Denise/Brightline 是什么意思。还有一件事……这些信件里还能加更多连字符吗？至于这个，好吧，这些句子结构真让人受不了。所以我其实给它打了两分。对我来说引言很难读，信件本身质量也不太高。

<details><summary>Original English</summary>
Esto 

era 

mío.





Modelo 

C 

favorito—





Odio 

cuando 

mi





Grok 

hace 

lo 

mismo:





usa 

así





pocos 

tokens 

que





casi 

imposible





entender 

qué 

demonios





Quítalo, 

eso 

significa. 

Y





aunque 

es 

corto, 

si





No 

tienes 

contexto





Yo, 

por 

ejemplo, 

no





Entiendo 

lo 

que 

significa.





Denise/Brightline. 

Otra 

cosa...





¿Era 

posible 

hacer 

más?





más 

guiones 

en 

estos





¿letras? 

Y 

esto, 

bueno, 

esto





Estoy 

loco.





construcciones. 

Así 

que 

yo





en 

realidad 

poner





para 

esto 

un 

dos. 

A 

mí





Introducción 

difícil 

de 

leer,





y 

las 

cartas 

en 

sí 

mismas 

no 

lo 

son





de 

muy 

alta 

calidad.
</details>

模型 E——又是一条不错的小短消息。呃，基本上被忽略了，但在草稿里到处崩溃。所以，同样，是的，我们不给两分，但也不给五分。也许我给它个三分。

<details><summary>Original English</summary>
Modelo 

E





—otra 

vez 

agradable





 pequeño





mensaje. 

Ejem,





es 

prácticamente 

ignorado,





pero 

en 

borradores 

por 

todas 

partes





estrellarse. 

Así 

que, 

de 

nuevo





Sí, 

no 

lo 

haremos.





un 

dos, 

pero 

no





cinco. 

Tal 

vez 

yo





Le 

doy 

un 

tres.
</details>

现在来看模型 G，我们瞧瞧。嗯，很短。虽短，但我完全明白它的意思。所以这非常有用。它在恰当的时机没有达成一致。我会照办。它得了四分。

<details><summary>Original English</summary>
Y





ahora 

modelo 

G,





vamos 

a 

ver. 

Hmm, 

muy





corto. 

Brevemente, 

pero





Lo 

entiendo 

perfectamente.





Qué 

quiere 

decir 

esto. 

Así 

que 

esto 

es





Muy 

útil. 

Ella





No 

se 

pusieron 

de 

acuerdo 

con 

los 

correctos





momentos. 

Yo 

cumpliré.





Ella 

sacó 

un 

cuatro.
</details>

因此，再次说明，这就是我进行评估的方式。我只是给你布置一个任务，我看着它，像这任务的接收者一样给它打分，这是平常的做法，然后我对它进行归类。呃，而且这样……我认为，这是 Luna，因为我刚才说了用 Luna 来写信。让我们看看表现如何。看来它遵守了我的规则，对吧？那我就给它五分。呃，其他模型没有写我的信件，所以我们就跳过它。

<details><summary>Original English</summary>
Por 

lo 

tanto,





De 

nuevo, 

así 

es 

como 

lo 

hice





Estoy 

realizando 

una 

evaluación. 

I





Solo 

te 

estoy 

dando 

una 

tarea.





Lo 

miro. 

I





Lo 

califico 

como 

si





Soy 

el 

destinatario 

de 

esto.





la 

tarea 

que 

es





lo 

habitual, 

y 

luego





Lo 

estoy 

clasificando. 

Eh, 

y





Así 

fue... 

creo,





Esta 

es 

Luna, 

porque 

yo 

solo





 dicho





usa 

Luna





para 

escribir 

cartas.





Veamos 

cómo 

está.





Lo 

logré. 

Parece





Ella 

obedeció





Mis 

reglas, 

¿verdad? 

Entonces





Se 

lo 

daré.





cinco. 

Eh, 

otros





modelos 

mis 

cartas 

no 

son





escribió, 

así 

que 

lo 

hacemos





Saltémonos 

eso.
</details>

### 前端与界面任务对比

好了。我们转到界面模型。在这里，我认为我们可以认出 Claude，因为据我所知它全是橙色的。好的。这是一个非常好的例子。我做了 1、2、3，根据这里大约 10 个不同的模型评估，在界面方面对它们进行比较。呃，是的。编辑文章。我正在搭建一个暗室技术主题、一个事件管理平台。是的，有点像复杂的文档管理系统。嗯，啊，然后我制作一个 B2B 仪表板更新、一个植物应用程序、呃，一个日志平台，作为开发者工具，这对于后台任务来说挺有意思的。然后我做了一些线框图。我可以非常快地批准。

<details><summary>Original English</summary>
DE 

ACUERDO.





Pasemos 

a





modelos 

de 

interfaz. 

Aquí





aquí, 

creo 

que 

nosotros





podemos 

decir 

Claude,





Lo 

que 

sé 

es 

todo.





naranja. 

Bien.





Esto 

es 

muy 

bueno.





ejemplo. 

Hago 

1, 

2, 

3





con 

aproximadamente 

10 

diferentes





Según 

las 

estimaciones 

del 

modelo 

aquí,





comparándolos 

en





Interfaz. 

Eh, 

sí.





Artículo 

editorial. 

I





Estoy 

montando 

un 

cuarto 

oscuro 

técnico.





tema, 

plataforma 

para





 gestión





incidentes. 

sí





algo 

como





sistema 

complejo





 gestión





documentos. 

Hmm, 

ah





Luego 

creo 

un 

panel 

B2B.





actualizaciones, 

aplicación





para 

plantas, 

eh,





plataforma 

para





registro, 

como





 herramienta





desarrollador, 

lo 

cual 

es 

suficiente





interesante 

para 

el 

trasfondo





tareas. 

Y 

entonces 

yo





Hago 

algunos





wireframes. 

Soy 

yo.





Puedo 

aprobar.





rapidísimo.
</details>

呃，这个模型甚至什么都没生成，所以我给它打一分。模型 B。并且，好的。我们来比较一下。我们非常仔细快速地比较它们，看看我是怎么想的。呃，我讨厌……我讨厌某些东西，我讨厌它们全部。我感觉自己讨厌所有这些，除了这个设计，我不喜欢。所以我会给那个……哪个我可能最喜欢？模型 C 给三分，E 给两分。噢。噢。噢。噢。我给 E 打两分，B 也是某种两分。我认为这个留白非常奇怪。呃，看起来正常，但并不出色。这一个，又是模型 B，实际上跑不起来。所以我要给它打一分，并说明它不能工作。它看起来像 Astra E。嗯，从某种意义上说，它还不错，并且在某些方面，这类文本非常类似于 Astra。我会给它三分，因为我能认出这个模型。

<details><summary>Original English</summary>
Eh, 

este 

modelo 

incluso





no 

se 

generó





nada, 

así 

que 

yo





Le 

daré 

uno.





Modelo 

B. 

Y, 

de 

acuerdo.





Comparemos.





Vamos 

a 

compararlos 

muy 

de 

cerca.





rápido 

y 

veremos 

qué 

pasa





Creo. 

Eh, 

yo





Odio... 

odio 

algo





Los 

odio 

a 

todos. 

I





como 

si 

los 

odiara





todos, 

excepto 

este 

diseño





No 

me 

gusta.





así 

que 

lo 

plantearé 

a 

ese,





¿Cuál 

me 

gusta?





probablemente 

el 

más





modelos 

C, 

tres 

y 

E





Te 

daré 

un 

dos. 

Oh.





Oh. 

Oh. 

Oh. 

Pondré 

E





un 

dos, 

y 

B 

también 

es 

algún 

tipo





dos. 

Creo 

que 

este





espacio 

vacío





Muy 

extraño. 

Ejem,





parece 

normal,





pero 

no 

genial. 

Éste,





Nuevamente, 

modelo 

B,





En 

realidad 

no 

funciona.





Así 

que 

se 

lo 

daré.





unidad 

y 

diré 

que





No 

funciona. 

Él





parece 

un 

Astra 

E. 

Hmm,





En 

cierto 

sentido, 

lo 

es.





no 

está 

mal, 

y 

en 

ciertos





aspectos 

de 

este 

tipo





El 

texto 

es 

muy 

similar 

a





Astra. 

Se 

lo 

daré.





tres 

porque 

puedo





reconocer 

el 

modelo.
</details>

呃，我注意到的一件事，特别是在 Claude 模型上——我怀疑是它们——这就是当你给它们非常难的任务时会发生的情况：它们把它做得太饱和、太复杂且太详尽。适合做后端代码。我认为这对于原型设计来说很困难，因为我很难理解它到底是什么样，或者它必须做什么。因此，看到我认为这实际上是最好的选项也很有趣。它更容易阅读，并且遵循了正确的路径，帮助人们对事件进行分类。所以我觉得当你在尝试建立评估时，这真的很有趣。有时候，如果你要求非常详细的形式，它能出色地完成工作。就像这个选项，它相当详细。所有这些都能用。但我不知道这里到底发生了什么。感觉非常难以理解这么大量的内容。

<details><summary>Original English</summary>
Ejem,





una 

cosa 

que 

yo





notado, 

en 

particular, 

con





Claude 

modela, 

que 

yo





Sospecho 

que 

son 

ellos.





—esto 

es 

lo 

que 

sucede 

cuando 

das





algo 

muy 

difícil 

para 

ellos,





Lo 

hacen 

demasiado





saturado,





complejo 

y 

muy





detallado. 

Bueno 

para





código 

de 

backend. 

Creo





es 

difícil 

para





prototipado, 

porque





Me 

resulta 

difícil 

de 

entender,





¿Cómo 

es 

realmente?





o 

lo 

que 

tiene





hacer. 

Y 

por 

lo 

tanto 

también





Es 

interesante 

ver 

que 

yo





En 

realidad 

creo 

que 

esto





La 

mejor 

opción. 

Él





más 

fácil 

de 

leer 

y





él 

sigue





el 

camino 

correcto 

y





ayuda 

a 

las 

personas





 clasificar





incidentes. 

Así 

que 

yo





Creo 

que 

cuando 

tú





tratando 

de 

crear





evaluación, 

realmente 

lo 

es





interesante. 

A 

veces, 

si 

tú





estás 

pidiendo 

un 

muy





forma 

detallada,





realiza 

un 

trabajo 

maravilloso





trabajar. 

Como 

este





opción, 

es 

bastante





detallado. 

Todo 

esto





obras. 

Pero 

no 

lo 

sé,





¿Qué 

está 

pasando 

aquí?





Como, 

muy 

difícil.





para 

entender 

tal





cantidad 

de 

contenido.
</details>

呃，然后，再次强调，是的，校准你的基准很重要。我认为对我来说最大的问题在于，这是一个用于集装箱运输规划的折叠平台，因为这一切看起来完全不可理喻。呃，所以对我来说很难讲哪个选项更好。其实我觉得这一个虽然有许多不准确之处，比如在左边缘，但它更容易阅读。所以我要给它打四分。我会说它是最容易阅读的。嗯，但这些选项……我会说，这个也许是第二容易阅读的，所以我给它三分。嗯，这一个大概运行得很好，并且包含了信息，但根本没法用。呃，所以我打个两分，并给出同样的模型评价。这个选项干脆是疯了。我甚至不知道该拿它怎么办。好的。

<details><summary>Original English</summary>
Eh, 

y 

entonces, 

de 

nuevo





Sí, 

es 

importante





calibra 

tu





puntos 

de 

referencia. 

Creo





el 

mayor 

problema 

en





yo 

con 

esto, 

¿qué 

es?





una 

plataforma 

plegable





para 

la 

planificación





 recipiente





transporte. 

Porque 

todo 

esto





parece 

un 

completo





locura. 

Eh, 

y 

por 

eso





Me 

resulta 

muy 

difícil.





Dime 

qué 

opción





mejor. 

De 

hecho





Creo 

que 

este, 

aunque





él 

tiene 

mucho





inexactitudes, 

como 

por 

ejemplo 

en





borde 

izquierdo, 

hay





más 

fácil 

para





lectura. 

Entonces, 

yo





Se 

lo 

daré.





cuatro. 

Yo 

diré 

que





es 

el 

más 

fácil 

para





lectura. 

Hmm, 

pero 

estos





opciones...yo 

diría,





que 

este, 

tal 

vez,





segundo 

más 

fácil





leyendo, 

así 

que 

yo





Le 

doy 

un 

tres.





Hmm, 

este, 

probablemente





funciona 

muy 

bien 

y





tiene 

información, 

pero 

con





Es 

simplemente 

imposible 

para 

ellos





trabajar. 

Eh, 

entonces 

yo





Pondré 

un 

dos 

y 

te 

lo 

daré.





misma 

reseña





Acerca 

del 

modelo. 

Este





La 

opción 

es 

sencilla.





loco. 

Yo 

incluso





No 

sé 

qué 

le 

pasa.





hacer. 

Bien.
</details>

因此，这是一次 B2B 更新，实际上接下来的这三个是我添加到基准测试中的两个新项。你也可以看到我测试了更广泛的模型范围。所以我认为那就是 Grok 和 Meta 作为模型潜入的地方。这些就是

<details><summary>Original English</summary>
Por 

lo 

tanto,





Esta 

es 

una 

actualización 

B2B,





en 

realidad 

estos





Los 

tres 

siguientes 

son 

dos





nuevos 

que 

agregué 

a





punto 

de 

referencia. 

Tú 

también





puedes 

ver 

que 

yo





protestaron 

más 

ampliamente





gama 

de 

modelos. 

Así 

que 

yo





Creo 

que 

ahí 

es 

donde 

está 

Grok.





y 

Meta 

se 

colará 

como





modelos. 

Estos 

son 

los 

que
</details>

<!-- chunk 3/5 -->

我有，我可能也会去评估。我会想念线框图的。但这基本上是在仪表板更新中，查看当前的 SaaS 续费收入情况。

<details><summary>Original English</summary>
tengo,

Probablemente 

lo 

haré.

evaluar. 

Te 

echaré 

de 

menos.

wireframes. 

Pero 

esto 

está 

en

 básicamente

panel

actualizaciones 

a

ver 

qué 

ingresos

de 

SaaS 

en 

este 

momento

renovación. 
</details>

好吧，对于定向的评估标准，我给出了很多具体的要求。这里有更多单次提示（one-shot）风格的开放式通用查询。那么，你真的能借此看出模型做了什么，以及什么是提示词吗？

<details><summary>Original English</summary>
Bueno, 

para

 dirigido

criterios 

de 

evaluación

Di 

mucho

requisitos 

específicos.

Había 

más 

abiertos

consultas 

generales

al 

estilo 

de 

una 

sola 

toma. 

Entonces

¿De 

verdad 

puedes?

para 

ver 

qué 

hace

modelo, 

y 

qué 

es 

una 

solicitud.
</details>

我会快速过一下这些。嗯，好吧，这个相当不错，但这里的可用性一般般。我不喜欢空状态。我觉得这通常是……我会给这个选项打个“还行”。我觉得差不多在两分左右。之后会揭晓。它并不丑，但相当简陋。

<details><summary>Original English</summary>
Pasaré 

estos 

mismos

rápidamente. 

Eh, 

bueno, 

esto

bastante 

bueno, 

pero

funcionalidad 

aquí

más 

o 

menos. 

No

como 

vacío

estado. 

Creo 

que 

esto 

es

normalmente. 

Yo 

entregaré

esta 

opción 

"

"Está 

bien." 

Creo 

que 

es

en 

algún 

lugar 

un 

dos. 

Saldrá 

a 

la 

luz. 

Él

no 

feo, 

pero

bastante 

primitivo.
</details>

这是我认为应该有的样子，非常漂亮。我猜是 Claude。走着瞧吧。看起来非常好。挺好，使用了标签。非常易读，没有任何奇怪的空状态。这挺好的。很好，这里有表情符号。有用的表情符号。而且看起来挺漂亮……肥皂。这里有一点蓝紫色，但这有什么办法呢？我打算给这家伙打四分。

<details><summary>Original English</summary>
Esto 

es 

lo 

que 

creo 

que 

debería 

ser

Muy 

guapo.

Supongo 

que 

es 

Claude.

Ya 

veremos. 

Parece 

que

Muy 

bueno. 

Bien

 usando

bandera. 

Muy 

fácil

legible, 

ninguno

extraño 

vacío

estados. 

Esto 

es 

agradable. 

Bien

Aquí 

hay 

emojis. 

Él

Emojis 

útiles. 

Y

se 

ven 

bonitas

jabón. 

Aquí 

hay 

un 

poco.

azul 

violeta,

¿Pero 

qué 

harás? 

I

Voy 

a 

poner 

esto

El 

chico 

sacó 

un 

cuatro. 
</details>

嗯，模型 C。这是谁？他是谁？我想……是 Grok 吗？也许是 Grok？我不知道。还有一件事，我们要做的——这些东西的盲测。

<details><summary>Original English</summary>
Ejem

, 

modelo 

C. 

¿Quién 

es 

este? 

OMS

¿él? 

Supongo 

que 

creo

¿Qué 

es 

Grok? 

¿Tal 

vez 

Grok?

No 

sé. 

Una 

cosa 

más,

lo 

cual 

haremos—esto

Prueba 

a 

ciegas 

de 

estas 

cosas.
</details>

嗯，颜色更好一些，但不知怎么有点粗糙。我不喜欢它们背景的小圆圈之类这类东西。也有可能是 Alma，因为在我看来他们很喜欢把东西叫做“Relay”。我打算打两分。我不是很喜欢。

<details><summary>Original English</summary>
Hmm, 

los 

colores 

son 

mejores, 

pero

de 

alguna 

manera 

descuidada. 

A 

mí

No 

me 

gustan.

pequeños 

círculos 

de 

fondo

y 

cosas 

por 

el 

estilo. 

Él

También 

podría 

ser 

Alma, 

porque

Me 

parece 

que

ellos 

aman

Llamamos 

a 

las 

cosas 

"Relevo". 

I

Voy 

a 

poner 

esto

dos. 

No 

me 

gusta.

Me 

gusta 

mucho. 
</details>

嗯，模型 E。这个不差，没有前面那个好，但比最开始的好。这个……以一种稍微不同的方式。哦天哪，肯定是它，那绝对应该是 Alma。嗯，Alma 喜欢森林绿。去找一个能像 GPT Soul 爱森林或浅绿那样爱你的人吧。嗯，这通常……在我看来不太像。什么是适合 SaaS 产品的正确配色方案，对吧？这有点偏向鼠尾草绿的医用色调。

<details><summary>Original English</summary>
Ejem,

modelo 

E. 

Este 

no 

está 

mal,

no 

tan 

bueno 

como

anterior, 

pero 

mejor

para 

el 

inicial. 

Esto...esto

de 

una 

manera 

un 

poco 

diferente. 

Ay 

dios 

mío,

Tiene 

que 

serlo, 

eso 

seguro.

debería 

ser 

Alma. 

Hmm, 

Alma

ama 

el 

bosque

verde. 

Encontrar

aquel 

que 

amará

tú 

como 

GPT 

Soul 

te 

ama

bosque 

o 

luz-

verde. 

Hmm, 

esto 

es

normalmente. 

No 

me 

parece.

¿Qué 

es 

correcto?

paleta 

de 

colores

para 

un 

producto 

SaaS,

¿verdad? 

Esto 

es 

un 

poco

dona 

a 

la 

medicina

color 

salvia.
</details>

呃，我打两分，我们更详细地分析一下这个。这个——不太好。太可怕了，可怕，可怕。字重太粗了。我觉得这不太行。我会给它一分。我真的很讨厌这个选项。

<details><summary>Original English</summary>
Eh, 

pondré 

un 

dos, 

y

Analicemos 

esto 

con 

más 

detalle. 

Este

—No 

mucho. 

Horror, 

horror,

horror. 

Peso 

del 

texto

demasiado 

grande. 

No

Creo 

que 

eso 

es 

todo.

bien. 

Yo 

cumpliré.

él 

una 

unidad. 

I

Realmente 

lo 

odio.

esta 

opción. 
</details>

呃，这又是，可能是 OpenAI 的模型。老天，他们怎么这么喜欢绿色。嗯，又来了，不是那个，没有专门针对这个的设计系统。所以我就给它打两分。再次说明，这只是感觉上的常规检查。

<details><summary>Original English</summary>
Eh, 

y 

esto

De 

nuevo, 

probablemente 

un 

modelo

OpenAI. 

Dios, 

¿cómo 

están?

Les 

gusta 

el 

verde. 

Ejem,

otra 

vez, 

no 

esa, 

no

y, 

eh, 

diseñador

sistema 

para 

esto.

Así 

que 

se 

lo 

daré.

dos. 

De 

nuevo,

es 

regular

comprobar 

en

sentimiento. 
</details>

好吧，就是这样，他们到底都在搞什么，全翻车了。呃，他们在消费端领域表现都非常差。在消费端领域全都非常差。他们所有人不知怎的都让人想起……你还记得 Claude 的 Artifacts 刚出现的时候吗？大家都做这种每日简报，而且它们看起来都一个样，全都是橙色的？嗯，所以我对他们这些一个都不喜欢，除了一款。

<details><summary>Original English</summary>
Vale, 

eso 

es 

todo,

¿En 

qué 

andan 

todos?

fallido. 

Eh, 

ellos

Todos 

son 

muy 

malos 

en

segmento 

de 

consumidores.

Todos 

son 

muy 

malos.

en 

el 

consumidor

segmento. 

Todos 

ellos

de 

alguna 

manera 

recuerda 

a...

¿Te 

acuerdas 

de 

cuando?

Aparecieron 

artefactos

Claude, 

y 

todos 

hicieron 

esto

breve 

diario

informes, 

y 

todos 

ellos 

son

parecían 

iguales,

solo 

eran

¿naranja? 

Ejem,

así 

que 

no 

tengo 

ninguno 

de 

ellos

No 

me 

gustó, 

excepto

uno. 
</details>

那么，这个——纯粹是垃圾。我就是觉得它不行。呃，这个……不。这些是我喜欢的东西。我们测试了 SVG。我很高兴这些模型在生成 SVG 方面变得最强了。如果你看模型 B 和模型 H，它们做了微型 SVG 插图。在模型 H 中显然做得好得多。这是典型的 Claude 式“Hack”，比如背景里的光圈。所以我会给它加上 SVG 加分。

<details><summary>Original English</summary>
Entonces, 

este—

Simplemente 

basura. 

I

Simplemente 

no 

lo 

creo.

Él 

es 

bueno. 

Eh, 

este...

No. 

Estas 

son 

las 

cosas 

que 

yo

como. 

Nosotros

SVG 

probado. 

A 

mí

Me 

gusta 

que 

estos

modelos 

se 

convierten

lo 

mejor 

en 

creación

SVG. 

Si 

miras

modelo 

B 

y 

modelo 

H,

lo 

hicieron

SVG 

pequeño-

ilustraciones. 

En 

el 

modelo 

H

claramente 

son 

mucho

mejor. 

Este 

es 

un 

clásico 

"

"Hack" 

Claude, 

como

círculo 

de 

luz 

en 

el 

fondo.

Así 

que 

se 

lo 

daré.

Bonificación 

SVG. 
</details>

嗯，哦，这些也不差。但是，我的天哪！是谁、是谁在角落里加了那些圆圈？谁干的？这是谁做的？这是什么习惯？因为它们到处出现，我不是很喜欢。呃，所以我觉得它不算太好。我大概会给一分。我讨厌它。

<details><summary>Original English</summary>
Hmm, 

oh, 

estos

Tampoco 

está 

mal. 

Pero

¡Oh, 

Dios 

mío! 

¿Quién, 

quién 

añadió?

¿Esos 

círculos 

en 

la 

esquina? 

OMS

¿Hiciste 

eso? 

¿Quién 

es?

¿hizo? 

¿Qué 

es 

esto?

¿hábito? 

Porque 

ellos

aparecen 

por 

todas 

partes 

y

No 

me 

gusta 

mucho.

Me 

gusta. 

Eh, 

entonces 

yo

No 

creo 

que 

sea 

genial.

Probablemente 

lo 

pondré.

unidad. 

Lo 

odio

él. 
</details>

好的，模型 E，垃圾。看看左边这些条纹。我打一分。我对这个产品太严格了。一分。Frond（“叶子”），挺好听的名字。这些植物相当可爱。我觉得它们比前面的好。我会给……我给它三分。我倒不……我并不讨厌它。不讨厌。嗯，至少这个背景是植物。哦，真贴心，它给植物起了名字。输入。

<details><summary>Original English</summary>
De 

acuerdo, 

Modelo 

E,

basura. 

Mirar

en 

estas 

franjas 

de 

la 

izquierda.

Pondré 

uno. 

I

demasiado

estrictos 

con 

esto

producto. 

Uno. 

Fronda 

(«

"Hoja"), 

un 

nombre 

bonito.

Estas 

plantas 

son 

bastante

millas. 

Creo 

que 

ellos

Mejor 

que 

los 

anteriores.

Le 

daré...

Le 

doy 

un 

tres. 

No 

lo 

soy

...No 

lo 

odio.

No 

odio. 

Ejem,

al 

menos 

este 

fondo 

es

planta. 

Oh, 

qué 

dulce. 

Él

da 

nombres 

a 

las 

plantas. 

EN.
</details>

哦，我非常喜欢。我太喜欢了。它给我带来了一丝喜悦，所以我很喜欢。我觉得这个是模型 H——我的最爱。看看这些插图。它们太可爱了，那么清晰，看起来令人赏心悦目，这个小东西形状很有意思，带阴影，浇水标记。非常可爱。在这里我的……这怎么说？这叫什么？Tender（“关爱”），肥皂。好的。我给五分。我非常喜欢它。

<details><summary>Original English</summary>
Oh. 

Me 

gusta 

mucho.

Me 

gusta 

mucho. 

Él

me 

causó

una 

chispa 

de 

alegría, 

así 

que

Me 

gusta. 

Y

Creo 

que 

este 

es 

el 

modelo 

H.

—mi 

favorito.

Mira 

estos

ilustraciones. 

Son 

así

lindo, 

tan 

claro,

se 

ven 

encantadores,

Este 

pequeño 

es 

interesante

forma, 

sombra, 

marca

regado. 

Muy 

lindo. 

Aquí

mi... 

¿cómo 

es 

esto?

¿Cómo 

se 

llama? 

Tender 

("

Cuidado"), 

jabón. 

De 

acuerdo.

Le 

doy 

un 

cinco.

Me 

gusta 

mucho.

Me 

gusta. 
</details>

### 后端与开发者工具应用

好，这就是最后一个了。这是一个用于控制后台模型的应用程序。它看起来像个面向开发者的应用。我怀疑那些被称为“Relay”的，全都是 Opus 和其他模型——不。为什么他们总是想把它们叫做 Relay 呢？我好奇提示词里是不是写了这个。嗯，但这里是任务控制台，所以可能不是。好吧。它又太紧凑了。嗯，但几乎是过于紧凑了。用这个干活很吃力。我的意思是开发者工具，我们喜欢你们的工具，但我觉得它们算不上绝妙。

<details><summary>Original English</summary>
Bien, 

esto 

es 

todo.

último. 

Esta 

es 

una 

aplicación

para 

control

modelos 

de 

fondo.

Parece 

una 

aplicación 

para

desarrolladores.

Sospecho 

que 

aquellos 

que

se 

llaman 

relés, 

—esto

todos 

los 

modelos 

de 

opus 

y 

otros

-No. 

¿Por 

qué 

siempre 

son 

así?

quieren 

llamarlos

¿relé? 

Me 

pregunto 

si 

esto 

está 

en

indicaciones. 

Hmm, 

pero 

aquí 

está

consola 

de 

tareas, 

entonces,

Quizás 

no. 

Bueno. 

Él

otra 

vez 

demasiado

ajustado. 

Hmm, 

pero 

casi

demasiado 

apretado. 

Duro

Trabaja 

con 

esto. 

Tengo

Me 

refiero 

a 

las 

herramientas

desarrollador, 

nos 

encanta

tus 

herramientas, 

pero

No 

creo 

que 

lo 

sean.

Son 

maravillosos. 
</details>

看这个，这个好得多，更容易阅读，简单明了得多，也更整洁。我非常喜欢这一个。它不是完美的，我想还有其他的，呃，但它很得体。然后从这里开始，我们开始变得越来越好。然后它们变得更讨喜了。看看这个漂亮的渐变。嗯，看用的颜色多好看，非常干净。哦，但是它没怎么生成东西。所以我敢说，我虽然喜欢它，但我只给三分，因为它是未完成的。我写下“未完成”。

<details><summary>Original English</summary>
Aquí

Este 

es 

mucho 

mejor,

más 

fácil 

de 

leer,

mucho 

más 

simple 

y

limpiador. 

Me 

gusta 

mucho.

Me 

gusta 

este. 

Él

No 

es 

lo 

ideal. 

Creo 

que 

sí.

otros, 

eh, 

pero 

él

decente. 

Y 

luego

Aquí 

es 

donde 

comenzamos

para 

ser 

cada 

vez 

mejor

mejor. 

Entonces 

ellos

volverse 

más 

agradable.

Mira 

este

Bonito 

degradado. 

Ejem,

mira 

qué 

bonito

colores 

utilizados,

muy 

limpio. 

Oh, 

pero

no 

creó 

mucho

qué. 

Así 

que 

apuesto,

Me 

gusta, 

pero

Le 

doy 

un 

tres 

porque 

él

estaba 

incompleto. 

Estoy 

escribiendo 

"

incompleto". 
</details>

现在来看模型 E，这个我很喜欢，因为看起来它像是在实时运行。太棒了。这个好多了，我给它打四分。

<details><summary>Original English</summary>
Y 

ahora

Modelo 

E, 

este 

es 

para 

mí.

Me 

gusta 

mucho,

porque 

parece 

que 

ella

funciona 

en 

la 

vida 

real

tiempo. 

Eso 

es 

genial.

Esto 

es 

mucho 

mejor, 

yo

Le 

doy 

un 

cuatro.
</details>

模型 F，好的。这里采用的方式略有不同。我确实很喜欢这个，除了橙色。问题之一是，如果你全部看一遍，它们主要使用的是色彩搭配本身：只要你说“开发者工具”——然后一切就变暗了，但尽管变暗了，它看起来相当好看，从设计的角度来看也有些许不同。我会因为打破常规限制给你一点加分。但这一个做了同样的事，却做得很糟糕。我给它一分。这显然是个魔鬼。我很想知道模型 G 会是什么。

<details><summary>Original English</summary>
Modelo 

F, 

de 

acuerdo. 

Aquí

Aquí 

se 

ha 

hecho 

algo

de 

una 

manera 

un 

poco 

diferente. 

A 

mí

realmente 

esto

como, 

excepto

 naranja

color. 

Uno 

de

problemas, 

¿qué 

pasa 

si?

míralos 

a 

todos

, 

son 

principalmente

usa 

ese

la 

combinación 

de 

colores 

en 

sí:

dices 

"herramientas"

desarrollador"—y 

eso 

es 

todo

Está 

oscureciendo, 

pero 

aún 

está 

oscureciendo.

Se 

ve 

bastante 

lindo

y 

de 

forma 

un 

poco 

diferente 

con

perspectiva 

de 

diseño. 

I

Te 

daré 

una 

pequeña 

bonificación.

por 

ir 

más 

allá 

de 

los 

límites

estándar. 

Pero 

este

hizo 

lo 

mismo, 

pero

terriblemente. 

Yo 

cumpliré.

él 

una 

unidad. 

Esto 

es 

claramente

demonio. 

Me 

gusta 

mucho.

Me 

pregunto 

qué 

será.

modelo 

G. 
</details>

现在是模型 H，再次，可能和另外那个我喜欢的模型是一对。稍微有些不同，非常养眼。但是看看这个，它结合了深色和浅色主题，所以我实在不是很喜欢。我给它三分。

<details><summary>Original English</summary>
Y 

ahora

modelo 

H, 

de 

nuevo,

probablemente 

un 

par 

de

ese 

otro 

modelo,

¿Cuál 

me 

gusta?

Un 

poco 

diferente, 

muy

agradable 

a 

la 

vista.

Pero 

mira 

esto

. 

Combina 

oscuridad 

y

luz 

del 

tema 

para 

que

Realmente 

no 

me 

gusta.

Me 

gusta. 

I

Le 

doy 

un 

tres.
</details>

### 后端任务与 Agent 评估

好的。那么，我在后端做了什么？好吧，我给出了两项……呃，两项任务。第一项——审计现有代码。这是 PRD 聊天的代码。第二项——按照规范创建后端功能。我只想说它们都挺成功的。呃，我打算让 LLM 充当裁判来评估它们，因为这关乎代码的正确性等等。就这么办。他将攻读法学硕士以专攻法学。

<details><summary>Original English</summary>
DE 

ACUERDO. 

Entonces, 

¿qué 

soy 

yo?

¿Lo 

hiciste 

en 

el 

backend? 

Bien,

Le 

di 

dos, 

eh, 

dos

tarea. 

Primero-

auditoría 

del 

código 

existente.

Este 

es 

el 

código 

para 

el 

chat 

de 

PRD. 

Y

segundo—creación

funciones 

de 

backend

de 

acuerdo 

a

especificación. 

Yo 

diré

solo 

que 

todos 

eran

exitoso. 

Eh, 

yo

Permitiré 

que 

LLM 

sea 

juez.

evaluarlos 

porque

Esto 

se 

aplica 

a

corrección 

del 

código

etc. 

Que 

así 

sea.

Cursará 

un 

máster 

en 

Derecho 

para 

especializarse 

en 

jurisprudencia.
</details>

我要说的是，你可以从它们呈现信息的方式上看出区别。有些消息非常短，有些非常长且详细。非常有意思，光是看它们如何回答之间的区别就很清楚了。我明确更偏向于……你知道的，模型 A 或是模型 E，它们之中的一个，比起 F、G 和 H（要短得多）来说更易读。

<details><summary>Original English</summary>
Yo 

diré 

que 

puedes

ver 

la 

diferencia 

en

por 

cómo 

sirven

información. 

Alguno

El 

mensaje 

es 

muy

corto, 

algunos 

muy

largo 

y 

detallado.

Muy 

interesante, 

simplemente

ver 

la 

diferencia 

en 

eso

¿Cómo 

están?

responder. 

Lo 

tengo 

claro.

Prefiero,

ya 

sabes, 

modelo 

A 

o

modelo 

E, 

uno 

de 

esos,

que 

son 

más 

fáciles 

de 

leer,

comparado 

con 

F, 

G 

y 

H,

que 

son 

mucho 

más 

cortas.
</details>

呃，所以如果你考虑模型，比如用于撰写 PR 描述或技术规范，这就是你可以评估观察到的地方：你是否喜欢在同时提出要求时得到同样的结果？而这里我要评估的是——这是一个 Agent 的人设。所以，基本上我要求它回答五件事，呃，我只是在确认我是否喜欢与这个 Agent 交流。我已经要打一分了，每条、每条消息都有破折号。我不是很喜欢。

<details><summary>Original English</summary>
Eh, 

entonces 

si 

tú

considerar 

modelos,

por 

ejemplo, 

para

Redacción 

de 

descripciones 

de 

relaciones 

públicas

o 

técnico

especificaciones, 

eso 

es 

lo 

que

lo 

que 

se 

puede 

evaluar

ver: 

si

Te 

gusta

mismo 

resultado

al 

mismo 

tiempo

¿pedido? 

Y 

aquí 

está.

que 

yo 

evaluaré

—esta 

es 

una 

personalidad

agente. 

Entonces, 

en

Básicamente, 

estoy 

preguntando

para 

responderle

cinco 

cosas, 

eh, 

y

solo 

estoy 

comprobando 

si

Me 

gusta.

comunicarse 

con 

esto

agente. 

yo 

ya

Voy 

a 

poner

esta 

unidad, 

cada 

una,

cada 

mensaje

tiene 

un 

guion. 

No 

me 

gusta.

Me 

gusta.
</details>

我会继续看下去。这也完全是这样。你因仪表板而受到惩罚。这个不是所有消息都带轻触，呃，但随后对于客户来说，它有，所以我打算给它打两分。在这里我看不到，我只看到一个普通的仪表板。对于

<details><summary>Original English</summary>
Seguiré 

adelante. 

Eso

Exactamente 

con 

esto. 

Tú

Estás 

siendo 

castigado

detrás 

del 

tablero. 

Este 

no 

tiene

todos 

los 

mensajes

tener 

un 

toque, 

eh, 

pero 

entonces,

que 

para 

los 

clientes, 

tiene,

Así 

que 

se 

lo 

daré.

dos. 

Aquí 

no 

veo,

Solo 

veo 

una 

cosa.

tablero 

normal. 

Por 
</details>

<!-- chunk 4/5 -->

因此，我们来读一下这个。嗯，这个我挺喜欢的。除了这是确切的Claude模型之外，因为它告诉我不能直接下载到生产环境。实际上，我们来看看其他模型是否允许。这里这个不让我“随意地”直接下载到生产环境。它们都不允许我以“约-霍-霍”的风格直接下载到生产环境。好吧，那我不会因为这个惩罚它。我给这个打四分，相当不错了。嗯，它运行了，但很简短，所以我不会对它评价过于严苛。它，我觉得可以像大多数一样。嗯，噢不，这个说它没有权限。这个在访问各种事物上遇到了很多问题。所以，有的是我这边坏了，有的是那一边坏了。因此，我会给它“错误”状态。

<details><summary>Original English</summary>
lo tanto,

Leamos

él. Mmm, esto me gusta.

como, excepto

que es exacto

Claude modelo, porque ella

me dice que no lo soy

Puedo descargar

directo a producción.

En realidad, vamos a

veamos si

Otros lo permitirán. Aquí

Este no me deja

descargar directamente

en la producción "al azar".

Ninguno de ellos

me permite

descargar directamente

en una producción al estilo "yo"

-jo-jo". Bien, entonces yo

No lo castigaré.

para esto. Voy a poner esto

cuatro, suficiente

nada mal. Hmm, aquí está.

carrera, pero brevemente,

así que no lo haré

para evaluarlo

demasiado estricto. Él,

Creo que sí.

 como

mayoría. Um, oh no,

Este dijo que no lo tenía.

acceso. Este tenía

muchos problemas con

acceso a las cosas.

Entonces, algo de mi parte

roto, y algo de

Tengo el costado roto.

allá. Por lo tanto, pondré

Tiene el estado "error".
</details>

来看看我拿到了什么。它会喜欢的。好的，那是非常有趣的分类。这是最老的智能体任务，实际上，我给了它一堆虚构的工单、客户评价，然后让它为我起草一份备忘录和消息。同样，你可以看到哪些模型，似乎是A、C和A、B，是的。A、B和E都给我写了很好的短消息。也就是说，它非常以人为本，不像C、F、G和H写了非常简短的东西。所以我很好奇，这些是我们能够区分的模型家族吗？嗯……然后你可以看到它为我写的备忘录。同样，这是包含86个步骤的调研结果。所以，我会让CMM作为裁判来处理。我快速浏览一下这些备忘录。团队没有透露价格。例如，这是一份协议分析，为什么这个客户……我不知道这是什么意思。好吧，我们来看看。这里有什么能解释这是什么意思的内容吗？噢，我已经会读了。它给了我三个主要问题和三个冲突。它读起来要容易得多。E模型也是同样的情况。我会让模型去检查，但我喜欢B和E模型。我给它们加点分，因为它们完成得很好。其他的我没有足够仔细地读，但如果我必须选出两个最好的，那就是它们了。我会让电脑去评估它在使用提示词时的应对表现。所以我让CMM当裁判来评判。

<details><summary>Original English</summary>
Veamos qué tengo.

Le gustará. DE ACUERDO,

Eso fue muy interesante.

clasificación. Fue

agente más antiguo

tarea, y, de hecho, yo

le dio un montón

boletos falsos,

reseñas de clientes y

luego preguntó

redactar un memorándum y

mensaje para

a mí. De nuevo, tú

puedes ver cuál

Los modelos, al parecer, son A,

C y A, B, sí. A, B y E, todos

Escríbeme cosas bonitas

mensajes cortos

. Es decir, es muy

centrado en

una persona, a diferencia de

de C, F, G y H, que

escriben muy cortos

cosas. Entonces tengo curiosidad,

¿Son estas familias?

modelos que nosotros

podemos distinguir. Ejem

y entonces puedes

ver memorandos

que escribió para

a mí. Nuevamente, esto es

Hubo resultados

investigación con 86

pasos. Entonces, yo

Permitiré que el CMM, como juez,

hazlo. Soy rápido.

Revisaré estas notas.

ojo. El equipo no es

revela el precio.

Por ejemplo, este es un análisis

acuerdo, ¿por qué esto?

cliente... no sé qué

esto significa. Bien,

Vamos a ver. ¿Hay alguno aquí?

algo que lo explique

¿Qué significa esto? Oh, ya soy yo.

Sé leer. Él

me da tres principales

problemas y tres

conflictos. Él

mucho más fácil

leer. Lo mismo ocurre con

modelo E. Lo permitiré.

modelos para comprobar,

pero me gustan

modelos B y E. Soy un poco

Les daré puntos porque

Lo hicieron bien.

No he leído los demás.

Con suficiente cuidado, pero

si tuviera que

elige los dos mejores,

Entonces serían ellos. I

Permitiré que la computadora

para evaluar cómo él

se enfrentó

 usando

solicitud. Así que yo

Dejaré que CMM hable.

jueces.
</details>

好的，现在到了有趣的环节，我们来做盲测。我来告诉你我喜欢什么。这些新模型能够创建SVG文件，它们可以制作插图。我要求它创建一个文档、一个麦克风和一个甲虫。我准备好整天进行评估了。我要对比一下A模型。这只甲虫简直荒谬。我敢打赌它得了个4分。文档还不错，但麦克风看起来像个冰淇淋甜筒，而甲虫则不知道是个什么东西。这给出了相当不错的一些选项。也许这是最好的选项。所以我会给F模型额外加分。我们来对比一下B模型和C模型。这里的麦克风太可怕了。我给它们两个都打3分。它们在一个方面做得好，但在其他方面非常糟糕。我们对比一下E模型和G模型。这很复杂。它们为什么要把麦克风做得像仙人掌一样？好吧，我给这个打4分。我觉得三个里面有两个很差。也许是个3分，并不理想。我们快速看一下H模型。噢，H模型确实很漂亮。我打赌给它5分。看看这个阴影。麦克风非常像麦克风，不像仙人掌。文档非常有……呃，特征。

<details><summary>Original English</summary>
De acuerdo y

ahora interesante,

Hagamos un "juego a ciegas".

pruebas. Te lo diré.

¿A ti qué? a mí

Me gusta. Estos nuevos

los modelos pueden

crear archivos SVG.

Ellos pueden

 crear

ilustraciones. I

Se le pidió que creara

documento, micrófono y

escarabajo. Estoy listo.

evaluar todo el día.

Voy a comparar el modelo A. Este

escarabajo simplemente

absurdo. Te apuesto

Obtuvo un cuatro.

El documento no está mal,

pero el micrófono es similar

para un cono de helado, y

un escarabajo; se desconoce para qué.

Esto resulta bastante

No está nada mal

opciones. Tal vez,

Esta es la mejor opción.

Así que le daré el modelo F.

prima. Comparemos

modelo B y modelo C.

Micrófono aquí

horrible. Yo se los daré

ambos tríos. Ellos

bueno en una cosa

pero terrible por lo demás

. Comparemos el modelo E

y el Modelo G. Es complicado.

¿Por qué lo hacen?

micrófonos similares a

¿cactus? DE ACUERDO,

Voy a poner esto

cuatro. Creo que dos de

tres son malos. Tal vez

, es un tres, no

idealmente. Echemos un vistazo.

rápidamente en el modelo H. Oh,

modelo H en efecto

hermoso. Apuesto a que

cinco. Mirar

en esta sombra. Micrófono

muy similar a

micrófono, no encendido

cactus. El documento tiene

mucho, eh, carácter.
</details>

至于最后一个，它在编辑所有视频方面应对得非常糟糕。所以我给它们全部开放了权限，呃，这非常难看，但起作用了。所有模型都能访问自拍视频，然后被要求剪辑成一个短视频蒙太奇。所有模型都做得极差。我不得不这么说。嗯，这些非常糟糕。我不觉得它们剪辑得特别好。你们弄不到它们，而我，我无法相信已经做出了拼接。它们就是没有成功。我之前看过了。我让CMM来充当裁判，但我不会喜欢所有的，不过我认为这是能力问题，而不是模型的问题。因此，我进行了盲测。我准备下载测试结果。然后我把它交给Claude，我说：“Claude，我是怎么想的？分析一下。”然后我们看看我的预测是否会成真。

<details><summary>Original English</summary>
Y el último, él

lo sobrellevó terriblemente

editar todos los vídeos.

Así que se los di todos

acceso a, eh, es muy

Feo, pero funcionó.

todos tienen acceso a

selfie en video y luego

se me pidió que lo hiciera

montaje corto. Y

Todos lo lograron

terriblemente. Tengo que hacer esto.

decir. Hmm, estos

muchísimo

malo. No me parece.

los montaron

especialmente bueno. Usted no

Tú puedes conseguirlos, pero yo, yo no puedo.

Creo que fue

ya está hecho

pegamento. Ellos simplemente

no tuvieron éxito. I

los miraron

más temprano. Permitiré CMM

actuar como juez, pero

No me gustaría.

todos, pero creo que

es una cuestión de habilidades,

no son modelos. Entonces, yo

realizó su prueba el

gusto. Yo voy

 descargar

resultados de la prueba. Y

Luego lo paso

Claude y yo decimos: "Claude, ¿qué soy yo?"

¿Creo? Analizar". Y

ya veremos si

Mi deseo se hará realidad.

previsión.
</details>

再次好，这里是我对我所想内容的预测。我认为我会喜欢Claude，尤其是用于界面的Opus 3.5。我想我会喜欢Soul来写文本。我不知道对于长期智能体任务或编程而言哪个会是最好的。而且，呃，我认为Anthropic会把所有人从SVG中淘汰出局。也许吧？也许是的？我不知道。嗯，我也会做，呃，而且我认为它们在视频方面的表现都很差。既然说到这个，我们来做吧，我想给你们展示一个非常重要的基准测试——Barbie测试，在Opus 3.5上的基准测试。如果你还不知道的话，这是我很有趣的测试之一——我请模型创建一个3D Barbie模型。YouTube上的其他人，所有那些家伙都在用宇宙飞船和各种东西制作视频或视频游戏。而我想要一个关于Barbie时尚的视频游戏。因此，我给Opus 3.5的任务之一，就是构建一个3D渲染的Barbie服装设计师。没有任何模型，没有任何高级模型能够做到这一点。呃，而我只是想展示3D渲染女性身材的全部可怕之处，这实际上是最糟糕的。你已经看到这有多可怕了，但比以前好多了。所以我的意思是……我有点目瞪口呆了。这就是它在SVG方面做出的东西。我的意思是，这确实是令人难以置信的东西。呃，我们加上头上的蝴蝶结。来吧，你知道的，我们给她做成紫色的眼睛。好的，那么你实际上可以把它穿上，然后去试衣间。这是它创建的3D模型。呃，来吧，我们给她加上某种超短裙，让它稍微好看一点。现在，你知道的，我要说它有些地方做得比其他模型好。似乎塑造了她的头发，她的双手……噢，AGI还没有到来，还没有到来。双手相当可怕。这，这是个悲剧。脚相当糟糕。呃，你知道的，她走起路来很大胆。面孔很吓人。鞋子，因为是个大脚女孩。她是巨脚女王。嗯，啊，然后又是头发，这里出现了一个问题。这个发辫——这是很特别的东西。波波头，你知道的，也许像安娜·温图尔（Anna Wintour）。它，这确实有点东西。

<details><summary>Original English</summary>
De nuevo

Vale, aquí están los míos

predicciones sobre

lo que yo pienso. I

Creo que yo

le gustará Claude y

especialmente Opus 3.5 para

Interfaz. Creo

Me gustará Soul

para escribir

textos. No sé qué

será lo mejor para

agentes a largo plazo

tareas o

programación. Y también,

eh, creo que Antropía

Esto sacará a todos de SVG.

¿Tal vez? Tal vez

¿Sí? No sé. Mmm, yo también.

Voy a hacer, eh,

y creo que todos lo son

trabajar mal con

video. Ya que estamos en ello

Hagámoslo, yo quiero

te mostraré uno

de gran importancia

El banco de pruebas de Barbie es un punto de referencia.

en Opus 3.5. Si no lo haces

ya sabes, uno de los míos

pruebas interesantes—yo

Por favor, modela

crear un modelo 3D

Barbie. Todos los demás en

YouTube, todos estos tipos

¿Están haciendo videos o

videojuegos con

naves espaciales

y todo tipo de cosas. Y

Quiero un videojuego sobre

Moda con Barbie. Entonces una cosa

de tareas para Opus 3.5,

que yo di, es

construir un render 3D

diseñador de ropa

Barbie. Sin modelo,

ningún avanzado

El modelo falló

para hacer esto. Eh, y

Yo solo

 como

mostrar todo el terror 3D

-representación de mujer

cifras, esto es en realidad

el peor. Ya

Ya ves lo terrible que es,

pero esto es mucho mejor

que antes. Entonces

Quiero decir... estoy en

algún tipo de

Perdió el don del habla.

Esto es lo que ella hace con

Lados SVG. Tengo puesto

Quiero decir, realmente lo es.

algo increíble. Ejem,

agreguemos

un lazo en el pelo.

Vamos, ya sabes,

Vamos a hacerla morada

ojos. Vale, entonces tú

En realidad puedes hacerlo.

Póntelo y luego

Ve al probador.

Este es un modelo 3D que ella

creado. Eh, vamos.

vamos a añadirle algo

minifalda y

hagámoslo un poco

más agradable. Ahora,

ya sabes, yo diré que ella

hicieron algunas cosas

mejor que otros modelos.

Parece haberse formado

su cabello, sus manos… oh, AGI

Todavía no, todavía no ha llegado.

Las manos son bastante horribles.

Esto, esto es una tragedia.

Los pies están bastante mal.

Eh, ya sabes, ella tiene esto

un andar audaz. Rostro

aterrador. Zapatos, porque tú

chica con grandes

con los pies. Ella es la reina.

pies grandes. Hmm, ah

luego el cabello otra vez,

surgir aquí

pregunta. Esta cola—

Esto es algo especial.

Kare, ya sabes, tal vez

como Anna Wintour. Él,

Esto es algo.
</details>

所以，再次是的，唯一还没有通过的测试——就是Barbie测试。Opus 5没有达到要求。我不知道，我是不是已经在Soul上运行过了？我，我之前是在旧版本上运行的，我在Astra上测试过。在Opus上它做得更差，但我不喜欢更新。所以，如果你想知道我是如何评估模型的，我逼它们做3D渲染，呃，我逼它们渲染Barbie。你能怎么办呢？这就是为什么你们要加入《How AI Lives》来获取关于这些新模型的如此高级的分析。请擂鼓。GPT-6 Astra和GPT-6 Soul征服了我的心。好吧，Astra，呃，还有GPT-6，我很喜欢它们。另外它上面写着：“Opus 5.5在这周胜出。嗯，这就是我最频繁打出高分的模型。”所以，这是我一生中单项任务的最佳表现，但平均而言，我给了Opus 5.5最高评分结果、高指标。在最广泛的任务范围里，我给它打了四分和五分。Fable不合我意。这就是为什么我停止使用它。然后，呃，GPT-5.6 Soul旧版本，呃，以及Claude Opus 5紧随其后。当然有些人肯定喜欢新模型。接下来，好吧，我的七条评分是关于阅读的。因此，Soul和GPT模型，呃，我很欣赏阅读起来有多么清晰轻松，而这里Claude Opus仍然是，呃，但那是Opus 5和5.5。所以我测试了Opus

<details><summary>Original English</summary>
Así que, de nuevo

Sí, la única prueba,

que aún no se ha superado,

—Esta es la prueba de Barbie. Opus 5

No lo cumplió. No

Lo sé, ¿ya lo soy?

lo lanzó el, eh, el

Alma. Yo, yo estaba ejecutando esto en

anterior, yo

Lo probé en Astra.

Ella hizo cosas peores.

para Opus, pero no me gusta.

actualizado. Entonces, si

Quieres saber cómo estoy

Evalúo modelos, yo

Los obligo a crear

Renderizaciones 3D, eh, yo

Los estoy obligando a renderizar.

Barbie. ¿Qué serás?

¿hacer? Por eso tú

Únete a Cómo la IA

vivir para recibir

tan avanzado

análisis de estos nuevos

modelos. Por favor,

redoble del tambor. GPT-6

Astra y GPT-6 Soul

conquista mi corazón.

De acuerdo, Astra, eh, y GPT-6

Me gustan. Y

Además dice: "Opus 5.5

supera esto

semana. Hmm, eso es todo.

el modelo que yo

calificado con mayor frecuencia

alto. Entonces, esto es

El mejor trabajo de mi vida

tareas individuales,

pero en promedio yo

Le dio a Opus 5.5 la mejor calificación.

resultados, alto

agujas. Se lo puse a ella

cuatros y cincos

para el espectro más amplio

tareas. La fábula no es para mí.

Me gustó. Es por eso

Lo detuve.

usar.

Entonces, y luego, eh, GPT-5.6

Alma, versión antigua, eh, y

Claude Opus 5 calificado a continuación

por otro. Alguno

 definitivamente

como nuevos

modelos, por supuesto. Y

A continuación, de acuerdo, mis siete

Las notas eran sobre

lectura. Así pues, Alma y GPT

modelos, eh, lo aprecié

Qué claro y fácil

para leer, y aquí está Claude

Opus sigue siendo, eh, pero es

Opus 5 y 5.5. Entonces, yo

Probé Opus
</details>

<!-- chunk 5/5 -->

5，而且我仍然不喜欢它。

<details><summary>Original English</summary>
5 

y 

yo





Todavía 

no 

me 

gusta.
</details>

Opus 5。呃，Opus 5 和 5.5，正如我说过的，负荷过重而且写得太多了。因此，我再次怀疑，尽管他们减少了 Opus 的废话罗嗦，但这一切仍然需要在这方面下功夫。它依然是、依然非常啰嗦。所以我认为 Sonnet 5、6 和 6 是近亲，清晰且易读。Opus——非常繁复饱和。对于 PRD，正如预测的那样，我仍然认为 Sonnet 最适合 PRD。我把不错的任务交给了 Opus 5 和 5.5 来做智能体方面的事情，以及如预期用于助手语音。所以我的预测成真了。

<details><summary>Original English</summary>
Opus 

5. 

Eh, 

Opus 

5 

y 

5.5, 

como 

yo





dijeron, 

eran





sobrecargado 

y





escribió 

demasiado. 

Por 

lo 

tanto





, 

de 

nuevo, 

yo





sospechaba 

que 

incluso





a 

pesar 

del 

hecho 

de 

que 

ellos





hizo 

que 

Opus 

fuera 

más 

pequeño





verborrea, 

lo 

saben 

todo





Todavía 

necesito 

trabajar 

en 

esto.





trabajar. 

Él 

todavía 

lo 

es,





sigue 

siendo 

muy 

hablador





. 

Así 

que 

pensé 

en 

Soul 

5





, 

6 

y 

6 

son 

primos,





claro 

y 

fácil





para 

leer. 

Opus—muy





saturado. 

Para 

PRD, 

así 

como





predicho, 

soy 

todo





Sigo 

pensando 

en 

Soul





Lo 

mejor 

para 

PRD. 

I





dio 

buenas 

tareas





Opus 

5 

y 

5.5 

para 

agentes





cosas 

y 

cómo





esperado 

para





la 

voz 

del 

asistente. 

Entonces





Mi 

predicción 

se 

cumplió.





correcto.
</details>

这里是一个真正的惊喜。Astra 和 Sonnet 在处理 SVG 角色方面表现好得多，而其他模型的结果则相当模糊。挺有趣的，这就是我评为四分的所有内容。所以所有这些我很欣赏的东西，我都交给了 GPT-6。噢，它做出了那个可爱的关于植物的小应用吗？Astra 和 GPT Sonnet 创作了这些可爱的插图，因此，显然对于 SVG，我们更喜欢 Astra 和 Sonnet。Claude Opus 做了我最喜欢的 B2B 更新，让其中的一些东西更整洁，但总的来说我喜欢 Astra。

<details><summary>Original English</summary>
Y 

aquí 

está.





una 

verdadera 

sorpresa.





Astra 

y 

Soul 

son 

mucho 

mejores





se 

las 

arregló 

con 

SVG-





personajes 

y





resultados 

de 

otros





Los 

modelos 

eran 

bastante





ambiguo. 

Él





Bastante 

interesante, 

y 

aquí 

está.





todo 

lo 

que 

califiqué 

en





cuatro. 

Entonces 

todo,





que 

aprecié 

mucho, 

yo





Entregué 

GPT-6. 

Oh, 

él





¿Hizo 

ese 

lindo?





aplicación 

pequeña





sobre 

las 

plantas. 

Astra 

y 

GPT





El 

alma 

creó 

estas 

millas





ilustraciones, 

por 

lo 

tanto,





aparentemente 

para 

SVG 

nosotros





Preferimos 

Astra





y 

Alma. 

Claude 

Opus 

hizo





mi 

favorito





Actualización 

B2B, 

es





¿Algunos 

de 

estos?





cosas 

más 

ordenadas,





pero 

en 

general 

yo





Me 

gusta 

Astra.
</details>

### 模型评判与总结

这里一切开始变得真正有趣了。LLM 作为裁判，而我完全不同意。所以，我们完全不一致。我喜欢 Astra，而它喜欢 Fable。再次，是的，这是一个 GPT 模型裁判。接下来，我们评估 Opus 5.5。它对 Sonnet 的评价要低得多。所以我发现这简直太好笑了。因此，再次，Astra 赢得了我的心。5.5 让我这周很开心。Sonnet，无论好坏，但 Sonnet 便宜这个事实让我非常高兴。我觉得它棒极了。

<details><summary>Original English</summary>
Y 

aquí 

está





Aquí 

todo 

se 

vuelve 

real.





divertido. 

LLM 

significa





juez, 

y 

yo 

absolutamente





No 

estoy 

de 

acuerdo. 

Entonces, 

nosotros





Estoy 

totalmente 

en 

desacuerdo.





Me 

gusta 

Astra,





y 

la 

suya: 

Fábula. 

Y 

de 

nuevo





Sí, 

este 

es 

un 

juez 

modelo.





GPT. 

A 

continuación, 

evaluamos





Opus 

5.5. 

Ella 

aprecia 

el 

alma





mucho 

más 

bajo. 

Así 

que 

yo





Me 

parece 

sencillo.





Muy 

divertido. 

Por 

lo 

tanto,





De 

nuevo, 

Astra





conquista 

mi 

corazón. 

5.5





Me 

alegra 

la 

semana.





Alma, 

para 

bien 

o 

para 

mal.





pero 

el 

hecho 

de 

que 

Soul





barato, 

me 

hace





muy 

feliz. 

Y 

yo





Me 

parece 

genial.
</details>

再次，我不知道这是否只是个人喜好的问题，但我喜欢 Sonnet。我喜欢 Astra。Opus 5.5——我不讨厌它。就是这样，对 Anthropic 团队来说这并不是彻底的失败。它重回了游戏。它确实有帮助，我必须完成这项任务。它在日常工作中为我提供帮助，并且仍然是我最喜欢的智能体，拥有美妙的声音，应对长期任务。接下来的意外成功：SVG 角色是 OpenAI 模型最成功的。所以，如果您转向其他新的创意领域或新的创意任务，我会建议正是使用这些模型。

<details><summary>Original English</summary>
De 

nuevo, 

no 

lo 

sé,





¿Es 

solo 

una 

pregunta?





preferencias 

personales,





pero 

me 

gusta





Alma. 

Me 

gusta





Astra. 

Opus 

5.5—No 

lo 

hago





Lo odio. 

Eso 

es 

todo.





no 

fue 

un 

fracaso 

total





Equipos 

antrópicos. 

Él





regresó 

al 

juego.





Definitivamente 

ayuda.





Tengo 

que 

hacer 

esto





tarea. 

Él





me 

ayuda 

con





trabajo 

diario





y 

sigue 

siendo 

mío





agente 

favorito





una 

voz 

maravillosa





se 

enfrenta





 a largo plazo





tareas. 

Y 

luego





Éxito 

inesperado: 

SVG-





Los 

personajes 

son 

los 

mejores





Los 

modelos 

de 

OpenAI 

tienen 

éxito.





Entonces, 

si 

usted





pasar 

a 

otros 

nuevos





campos 

creativos 

o





nueva 

creatividad





tareas, 

yo 

aconsejaría





para 

usar 

exactamente





estos 

modelos.
</details>

关注“How to Use AI”频道。正如我所说，点击订阅按钮。我们发布了完整的 Opus 5.5 评测，所以您可以去观看。感谢您加入 How-To AI 的直播。我打算使用 GPT-6 创造一些有趣的东西。大家再见。非常感谢您观看视频。如果您喜欢，请点赞并在 YouTube 上订阅，或者更好的是——给我们写下包含您想法的评论。您也可以在 Apple Podcasts、Spotify 或您喜欢的播客应用中找到这个播客。请留下评分和评论，这将帮助其他人找到我们的节目。您可以在 howiaipod.com 上观看我们所有的剧集并了解更多关于节目的信息。下次见。

<details><summary>Original English</summary>
Y





sigue 

el 

canal





Cómo 

usar 

la 

IA. 

Como 

dije,





pulsa 

el 

botón





suscripciones. 

Entonces, 

nosotros





lanzamos 

un 

completo





Reseña 

de 

Opus 

5.5, 

para 

que 

puedas





Puedes 

hacerlo





ver. 

Gracias 

por 

eso.





se 

unió 

al





Transmisión 

en 

vivo 

de 

How-To 

AI. 

Y





Voy 

a 

crear.





algo 

interesante 

para





utilizando 

GPT-6.





Nos 

vemos 

todos. 

Muy





Gracias 

por 

ver 

el 

vídeo.





Si 

te 

gustó





por 

favor, 

muéstralo





me 

gusta





y 

suscríbete 

a





YouTube, 

o 

mejor 

aún...





escríbanos





Comenta 

con 

el 

tuyo





pensamientos. 

Tú 

también





¿Puedes 

encontrar 

esto?





podcast 

en 

Apple 

Podcasts,





Spotify 

o 

en 

tu





aplicación 

favorita





para 

podcasts. 

Ser





Por 

favor, 

déjelo 

en 

nuestras 

manos.





calificación 

y 

comentarios, 

esto





ayudará 

a 

los 

demás





Encuentra 

nuestro 

programa. 

Tú





puedes 

ver





todos 

nuestros 

episodios 

y





Aprende 

más 

sobre





Programa 

en 

howiaipod.com.





 Hasta luego.





La 

próxima 

vez.
</details>