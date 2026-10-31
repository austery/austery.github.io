---
author: AI Engineer
date: '2026-08-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KLDdXOw6jIc
speaker: AI Engineer
tags:
  - generative-ai
  - multimodal-ai
  - world-model
  - model-deployment
title: Google生成式模型团队访谈：NanoBanana 2 light与Gemini Omni Flash发布及FDE机制探讨
summary: 访谈回顾了团队推出的NanoBanana 2 light与Gemini Omni Flash API，探讨了多模态感知、世界模型以及前向部署工程师（FDE）连接下游实际需求与模型改进的作用。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - Google Cloud
  - Google DeepMind
products_models:
  - NanoBanana 2 light
  - Gemini Omni Flash
  - Omni
  - Veo
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 开场与嘉宾介绍

[music]

欢迎线上直播间以及现场的各位回来。在各个主舞台主题演讲的间隙，我们通常会安排这种较长的对谈，来探讨一些特别重要、但并没有重大发布时刻的内容。今天非常荣幸能邀请到负责 Omni、VO、Nano Banana 等全球顶尖生成模型的团队成员来到现场。Demetrio，我最早关注到你，是因为你在网上晒办公室。[笑声] 我觉得你大概算得上是 Google 的头号办公室网红了，至少在旧金山是这样。我想你也挺喜欢骑自行车的，还喜欢拍——

<details><summary>Original English</summary>
[music]

and welcome back for those on the stream

and those those in person. um we take tend to basically take these longer sessions between uh all the sort of mainstage keynotes to reflect on things that um you know are particularly important but like don't have like a significant like sort of launch moments. Today we're very lucky to have people working on Omni and VO Nano Banana like the you know the world's best generative models here with us. Uh, Demetrio, I I I first saw you when you were posting about your office. [laughter] Um, I think you're you're probably number one uh Google Google's number one office influencer at least in in San Francisco. I think you like you like to bike as well. You like to take photos of
</details>

>> 骑车过来。

<details><summary>Original English</summary>
>> bike here.
</details>

>> 是的。不过，你也参与了视频模型的工作。

<details><summary>Original English</summary>
>> Yeah. Um, but you know, but also you work on video models.
</details>

>> 没错。

<details><summary>Original English</summary>
>> That's right.
</details>

>> 另外，Shane，我记得好像是在一次晚餐上认识你的。

<details><summary>Original English</summary>
>> Um, Shane, I I met you I think at like a dinner.
</details>

>> 没错。我记得你当时还想拉我投资其中一家公司，我都忘了是哪家了。

<details><summary>Original English</summary>
>> Yeah. Um and uh and uh and I I remember you were trying to get me invested in like one of the companies. I forget forget which one.
</details>

>> 那事就别提了。[笑声]

<details><summary>Original English</summary>
>> Forget about that. [laughter]
</details>

>> 不过现在，你正在负责 Omni Thinking，还有各种——

<details><summary>Original English</summary>
>> But now but now you're um now you're working on Omni Thinking. Um and and just you know a bunch of other
</details>

>> Gemini RL。

<details><summary>Original English</summary>
>> Gemini RL.
</details>

>> 对，对。还有 Nicole，负责其余的生成式媒体模型、Nano Banana，以及你们刚刚发布的全部内容，实际上就是本周刚刚推出的。

<details><summary>Original English</summary>
>> Yeah. Yeah. Uh and Nicole also uh the rest of the gen media models uh nano banana and uh all and everything you just launched actually even this week. Uh,
</details>

>> 是的，我们上线了一些 API。

<details><summary>Original English</summary>
>> yeah. We launched some APIs.
</details>

>> 没错，没错。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah.
</details>

>> 我倒是还没拉你投过什么项目，不过也许我该试试。

<details><summary>Original English</summary>
>> And I haven't tried to convince you to invest in anything, but maybe I should.
</details>

>> 我其实一直尽量不去做投资者，可大家总是不由分说地来劝我。我心想，好吧，我也没那么有钱，但面对其中一些项目，你又很难忍住不去尝试投资。对于我们这些不在前沿实验室工作的人来说，这已经是我们能接触到的最近距离了。所以，既然你离这些业务最近，而且我们刚刚完成了发布，不如来回顾一下，这周到底上线了什么？大家应该去体验哪些东西？

<details><summary>Original English</summary>
>> I mean, so I try not to be an investor. People just convince me anyway. I'm like just, okay, well, I'm not that rich, but know like you can't not try to invest in some of these things. And, you know, for those of us who are not working at a Frontier Lab, this is the best this closest we'll ever get. Um, so yeah, actually, let's kind of recap since you're closest to it and we just did it, like what was launched this week? What should people go try out?
</details>

### 本周新品发布：NanoBanana 2 light 与 Gemini Omni Flash

>> 好的。昨天我们有两个发布节点。其中一个是推出了 NanoBanana 2 light，这是 Nano Banana 模型家族中最快、成本最低的图像模型，而且效果比初代 NanoBanana 更好。所以对大多数人来说，无论是生成还是编辑，这款模型都可以替代大家熟悉并喜爱的初代 Nano Banana，并且它的效果非常接近主流更大型模型的前沿水准。这确实令人兴奋。我觉得看看那些演示或者大家做过的尝试就会发现，达到大约 3 秒左右的延迟，在构思和迭代上就能解锁非常多的可能性，用起来非常过瘾；而且模型的质量也达到了相当出色的水平，你不仅可以用它来快速迭代，还可以直接把其中的一些输出用作现成的成品。这真的很让人振奋。

另一个发布则是，我们终于推出了在 I/O 大会上预告过的 Gemini Omni Flash API。非常感谢大家的耐心等待。这也是我们首次向开发者开放这些 API，主要提供非常令人期待的视频生成和编辑功能，在定价上与 Y31 fast 保持一致。因此，希望我们是在以非常棒的价格为大家提供极其出色的质量。

<details><summary>Original English</summary>
>> Yeah. Um so yesterday we had two launch moments. Uh one of them we launched NanoBanana 2 light uh which is our fastest, cheapest um image model in the nano banana model family. Um and it's better than the original NanoBanana. Um so really for most people um that model replaces what you you know used and love the original Nano Banana for across like generation and editing and it gets really close to the frontier quality of of the kind of mainland bigger models. So that that's really exciting. I think if you look at some of the demos or like things that people have been trying like getting kind of that like 3 second latency just unlocks a whole bunch of things that you can do with like ideation and iteration and it's just really fun and the model's getting to a point where like the quality is really good um where um it you know you can use it for iteration but you can also use some of those outputs as just kind of like ready um production output. So that's really exciting. Um and then second launch we finally um launched the Gemini Omni Flash APIs um that we pre-announced at IO. So thank you for waiting. Um and that you know is the first time that we're making the APIs available for developers and it's basically really exciting kind of video generation and editing and we're pricing it the same as Y31 fast. So we're getting you kind of like really really good quality for a really awesome price hopefully. Um
</details>

>> 是的，太不可思议了。实际上，在你们第一次发布 Omni 时，还和今天未能到场的 Logan 一起录了一期播客，你们在视频里加了一只树懒、一碗拉面之类的东西。其实我一直很想把这些效果用到我们的视频里，之前只是因为没有 API，毕竟我得把整个流程自动化才行。所以非常感谢你们提供了 API。

<details><summary>Original English</summary>
>> yeah, I mean that that's incredible. I'm actually really So when you guys launched Omni for the first time, you also did a podcast uh with Logan who couldn't be here today uh and you added like a sloth uh and and Ramen and all these all these things. I actually really want to do that to our videos. I just didn't have an API for it because obviously I have to automate the whole thing. So thank you for the API.
</details>

>> 那是我最喜欢的用例，大家都应该试试。我加了一只猫，可能是所有动物里最普通的一种了。如果不清楚我们在聊什么，建议大家去搜搜看，非常搞笑。这是团队里的 Feurer 做的。

<details><summary>Original English</summary>
>> Uh that is my favorite use case. Everybody should do that. Um I got a cat which is probably like the most boring of the animals. Um if you don't know what we're talking about, you should look it up. It's very funny. Feurer. um Furer who's um you know on on the team did that.
</details>

>> 要想了解这东西到底能干什么、获取灵感，Furer 绝对是首选关注对象。

<details><summary>Original English</summary>
>> Furer is the number one guy you should follow for you should follow ideas on okay what can this thing do?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 对吧。

<details><summary>Original English</summary>
>> Right.
</details>

>> 没错，他在这方面确实极具天赋。

<details><summary>Original English</summary>
>> Yes. He he's he's amazing at that.
</details>

>> 过去两年我一直想请他来 AIE，但他一直没能成行。其实他本人来过现场，只是因为保持匿名而不愿上台演讲。

<details><summary>Original English</summary>
>> I've tried to get him for the last two years to come to AIE. He hasn't made it yet. He's actually come in person. He just didn't want to speak because he's anonymous.
</details>

>> 我知道。

<details><summary>Original English</summary>
>> I know.
</details>

>> 我很想说出他的真名，但我不能说。

<details><summary>Original English</summary>
>> I I want to say his real name but I can't say his real name.
</details>

>> 别，[笑声] 我们别这么对他。不过大家真的应该关注他，他太厉害了。

<details><summary>Original English</summary>
>> No [laughter] no we won't we won't do that to him. But you should really follow him. He's amazing.
</details>

>> 这些工作全是他做的。录播客的时候我其实在办公室碰到过他，当时我都没认出是他，因为他的胸卡上写的并不是 Popers。

<details><summary>Original English</summary>
>> He did all that work. I actually met him uh in the office uh when we did the podcast I think and I didn't realize it was him. So his badge doesn't say Popers.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 我懂。

<details><summary>Original English</summary>
>> I know.
</details>

>> 他以前在 Replicate，Replicate 内部有个梗，就是人人都叫 Deep Fates。Deep Fates 是 Replicate 里的一个神秘人物。Replicate 是一家非常酷的公司，他也曾是其中的一员。

在深入讨论 Omni 之前，我想了解的一点是：添加猫咪、添加树懒，确实非常酷、非常可爱、也很好玩。

<details><summary>Original English</summary>
>> So he used to be part of uh Replicate and Replicate had this joke where like everyone was Deep Fates. Deep Fates is this like kind of mysterious character and replicate. Replicate is very cool company and both was part of it. Um, so, okay, one thing I want to get on there before I go into like sort of the the the the sort of omniper is we added cats, we added sloths, very cool, very cute, very fun.
</details>

### 主力应用场景与未来展望

>> 能否启发一下大家，除了演示之外，有哪些更偏向主力生产的实际用例？

<details><summary>Original English</summary>
>> Uh, what are the, you know, inspire people as to like what are the more sort of workhorse use cases that maybe are not just demos, you know?
</details>

>> 好的。显而易见，该模型的核心主打能力——或者说有两点：其一，是能够以任意内容作为输入，并在另一端输出视频。当然在未来，正如我们此前预告过的，我们也希望输出其他模态；但本质上这意味着，你可以用一组现有的图片作为故事板，可以用一段音频作为角色说话的参考声音，然后在另一端生成视频。这在短片制作，或者像我们在 YouTube 上推出的 Shorts 等场景中，解锁了大量功能，能帮助创作者更轻松地制作内容。

另一个重点显然是视频编辑。这也是让我们非常兴奋的一点，我们正在让它变得更简单，因为现在你可以直接使用自然语言输入一段视频，添加或删除某些内容。树懒当然是个有趣的例子，但我们显然也考虑过一些面向消费者的场景，比如你海滩度假拍的视频太嘈杂，你想去除噪点，过去你可能不会去处理，因为没有工具或者不知道该找什么工具。所以这是一个可以使用的场景。

我们还看到许多人将其用于营销广告活动的物料制作，随着 API 的开放，我很期待看到更多此类用例。因为在第一方产品中我们显然无法看到全貌，但我非常期待大家开始在 API 中去探索这些方向。以上就是涌现出的一些高层面的应用。

人们也用它来制作教学材料。是的，那非常令人兴奋。我想我们大家都探讨过对未来教育的憧憬：一切都可以为你量身定制，根据你的知识水平和喜欢的风格进行个性化适配，而这正是迈向那个方向的一步。

<details><summary>Original English</summary>
>> Yeah. So, so obviously the hero capability of the model or maybe there's two like one is the ability to kind of take in anything as input and then get video on the other side. Obviously in the future and and we've kind of talked about this as a pre-announce like we want to get the other output modalities out as well but basically what that means is you know you can take a set of images that you have as maybe a storyboard. You can take like an audio track as a reference of you know like a voice that you want a character to speak and then you can get a video on the other side. So like that just unlocks a whole bunch of things that you can do in like you know short film production or you know shorts we've launched on YouTube as well um to help creators kind of like create um content more easily. Um and then the other one is obviously video editing. Like that's another thing that we're really excited about that we're just making easier because now you can use natural language to take a video, you know, add something, remove something. Sloth is obviously like fun example. Um, but there there's obviously kind of there's consumer use cases that we kind of had in mind where, you know, you could take your beach vacation video that was too noisy and you want to clean up that noise. Maybe in the past you wouldn't have because you didn't have the tools or you didn't know what the tools were that you needed to go to. So, that's one use case that you can, you know, go to. We've seen a lot of folks use it for kind of marketing ad campaign creation and I'm excited to see more of those use cases as we launch the APIs. um because obviously like we don't we don't see all of it in the first party products but I'm really excited for people to start to explore that um in the API. So those are just some of the kind of like high level um things that have come up. U people also use it to create like education materials. Yes. Um and like like that's really exciting. I think we're all we've all kind of talked about being excited about the future of education where like everything can be kind of customized to you and personalized to your knowledge level and the style that you prefer and and so this is kind of just like a step in that direction.
</details>

>> 是的，我昨天其实刚用了一下，不过我父母正好来访，碰到了一个非常有趣的用例。他们从亚马逊上买了一款心仪的小工具，说明书却只有英文，里面还有大量的图表示意。我拍了张照片，对它说：“把这个翻译成罗马尼亚语，

<details><summary>Original English</summary>
>> Yeah. I I I sort of actually used just none of yesterday, but my my parents are visiting and there was there was a very fun sort of use case. They I bought some gadget off from Amazon that they wanted and the instructions to use it was were only in English and there was plenty of diagrams or whatever and I took a picture of it and said, you know, translate this into Romanian. Yes.
</details>

>> 并且保持其他所有内容完全不变”，对吧？效果太惊艳了，看起来完全一模一样，而且翻译得非常到位。大体上是这样，不过底层使用的其实就是 Gemini——

<details><summary>Original English</summary>
>> And keep everything else the same, right? So it was amazing, right? Like it was just like, yeah, it looks identical and it has, you know, it's perfectly translated. I mean, more or less, right? But it's it's you know using Gemini under the hood
</details>

<!-- chunk 2/8 -->

显然，去做那种翻译。所以你也能看到视频方面的这种用例，对吧，比如 Omni 里的文本渲染能力确实达到了非常高的水平。所以你可以想到很多用例，比如文本渲染、翻译、内部化/本地化，各种对很多人真正有用的事情，以及更广泛的应用途径，比如你可以给视频重新配音，或者无论你想做什么。能想到的事情有很多。

<details><summary>Original English</summary>
obviously to kind of do the translation and so you can you can see this use case for video as well right like the the power of text rendering in in in Omni is is quite next level. So and you could you could you could think about plenty of use cases of like both text rendering translation internalization all sorts of things that would be actually genuinely useful to a lot of different people and sort of broader access to either you could like redub a video or whatever it is that you wanted to do. like there's plenty of different things that you could you could think about doing.
</details>

>> 是的。在我播客中进行的最具启发性的对话之一，就是和处于这些领域前沿的人、研究人员交谈。我和 xAI 视频团队（Grok 视频团队）的 Ethan 聊过一次，他基本上在说，下一波趋势实际上不仅仅是单一模型，更像是视频智能体（video agents）。我不知道这个术语是否能引起共鸣，显然这对强化学习非常相关。但这基本上有点像放弃尝试实际上一遍过搞定所有事情。你也有同感吗，还是说趋势朝哪个方向发展仍然是一个悬而未决的研究问题？[喷笑]

<details><summary>Original English</summary>
>> Yeah. Um one of the most enlightening conversations I have on my podcast is with uh just people researchers at the frontier of these things. Um I had one with um Ethan from the XAI video team, the Grock video team who was basically saying like you know the next trend is actually not just like single model, it's more like video agents. Um, and I don't know if that terminology resonates uh obviously for for very relevant for RL. Uh, but it was it was basically kind of like giving up on like trying to do everything in in effectively one pass. Um, do you feel that same way or is it still an open research question which way the trends are going? [snorts]
</details>

### 视频基础模型与因果表征

>> 是的。最让我感到兴奋的，实际上是符号类的基础模型和这种视频基础模型能够真正协同工作。在某种程度上，如果你看生成式图像生成、视频生成的开端，很多其实始于语言模型足够好、能够提供非常详尽的描述文本（captioning），比如 Stable Diffusion 时代或 DALL-E 2 时代。所以，语言是一种极其有用的表征。一是它具有某种普遍性，但另一个更偏技术的点——也就是我的假设——是机器学习中一件非常困难的事情是这种虚假相关（spurious correlation）。你不知道这种具有预测性的特征到底是不是因果因素。有两种途径：一种是我们拥有极其多样化的训练数据，来自因果图的每一次干预；另一种是对因果信息进行条件约束，而用语言进行条件约束，某种程度上就像是在对世界的因果信息进行条件约束。所以……

<details><summary>Original English</summary>
>> Yeah. So um what kind of excite me most is really when the symbolic kind of foundational models and this kind of like video foundational model can actually kind of really work together and u in a way the if you look at the beginning of the generative sort of like image generation video generation a lot of it kind of started when the language model got good enough to provide a very detailed captioning like from stable fusion days or kind of dowi 2 days. So um so basically like language is extremely u helpful representation uh one is that it's kind of universal but the other kind of more um technical thing like kind of my hypothesis is like um one very difficult thing about machine learning is um this sort of like spirious coordination. So you don't know you know if the if this kind of feature right that's kind of predictive is actually causal factor or not. There are two ways. One is we can have really diverse data training data like from every intervention of the causal graph. The other is you condition the causal information and conditioning the language is kind of like conditioning like a coal information of the of the kind of world. So um
</details>

>> 也就是 prompt 或者概念？

<details><summary>Original English</summary>
>> which is a prompt or a concept what
</details>

>> 对，没错。所以如果你看我们如何去描述这段视频、这种图像，实际上非常贴近你会如何描述背后的这种因果关系，也就是它是如何生成的。因此，一方面这确实能带来极其丰富的泛化能力，并且能造就一个出色的模型。另一方面，八个月前我们发布了一篇评测论文，题为《视频模型作为零样本学习者与推理者》（Video Models: Zero-shot Learners and Reasoners）。

<details><summary>Original English</summary>
>> yeah exactly so if you look at like you know how we going to describe this video how this kind of image is actually very close to you know how would describe this kind of causality you know behind this like how this is kind of generated. So one is like that can really allow for very rich generalization and then uh very kind of just like a good model. Um the other is so eight months ago uh we put the evaluation paper called video models zero shot learners and reasoners.
</details>

>> 对。那篇论文已经确认发表了。后来 N-Banana 团队跟进了一篇 Vision Banana 论文，基本上就是用 N-Banana 来做的。但核心思想是，视频模型在处理时空信息方面是一种极其优秀的基础模型。所以许多经典的计算机视觉任务都可以实现零样本。当你输入一个视觉测试题时，它能够去解答——当然绝对还有很多需要改进的地方——并且在机器人学这类场景中，它展现出了非常好的物理直觉，就像世界模型一样。我认为关键确实在于将视觉推理和文本推理交织在一起。显然，究竟是做成统一模型，还是仅仅做成智能体协作，我认为这会是一个渐进的过程。我设想最终所有东西都会融合进单一模型里。

<details><summary>Original English</summary>
>> Yes. So that was a kind of you know it's it's a confirmed paper and then later on actually the N banana team followed up with a vision banana paper that basically used n banana to do but essentially the idea is uh video model is extremely good sort of a foundation model for space and time kind of information. So um classic computer vision tasks a lot of could be kind of zero shorted and when you like say feed in some like a visual quiz uh it can you know there's definitely like a lot to improve it can kind of solve and it can um like robotics kind of like seeing it has really good kind of physical intuitions like word model uh and I think the the key is really the kind of mix of the visual kind of reasoning and then the text kind of reasoning kind of all tied together Um obviously you know like whether doing it you know as kind of unified model versus like just kind of agent coation I think that's more like uh it's going to be more kind of incremental you know how it's going to I imagine everything's going to go into like a single model eventually
</details>

>> 但眼下，如果你把非常出色的视频理解、图像理解以及 Gemini 以智能体的方式与 Omni 结合起来，其实能做的事情非常多。我们的团队也正在这方面进行大量的探索。

<details><summary>Original English</summary>
>> but right now there's like a lot you can do if you uh basically take like really good video understanding image understanding Gemini agentically with anomy and that's actually gonna yeah our team is like exploring a lot
</details>

### 单一模型演进与模态迁移

>> 好，这里面包含的信息量很大。我觉得我越来越感到好奇的一个问题是：对你们来说，一切最终都会走向单一产品吗？现在你们推出了多个模型，Omni 这个命名确实暗示了最终一切都会消失、合并进 Omni 系列中。这是目前的规划吗？

<details><summary>Original English</summary>
>> yeah okay that there's a there's a lot in there um I I think uh one question I I am increasingly starting to wonder is does it all trend towards one product for you guys right like now you have multiple models out the naming of omni does imply that eventually everything will go away and it just goes into omnis um is that the plan
</details>

>> 会这样吗？[笑] 我不知道，我想也许吧。我的意思是，我认为最终……我认为在工程、研究和产品上存在各种不同的权衡。出于同样的原因，比如……抱歉，它是叫 Nano Banana Light 吗？我不知道具体产品名称叫什么。

<details><summary>Original English</summary>
>> is it [laughter] I don't know I I think I think uh maybe I mean I think eventually I I think there's sort of different trade-offs engineering research product trade-offs in like it's like for the same reason like the the sorry how is it called nano banana light I don't know what the product name
</details>

>> Nano Banana Tight。

<details><summary>Original English</summary>
>> nanob banana tite
</details>

>> Nano Banana 2 Light，对。它服务于特定的细分场景，对吧？它未必适合立刻塞进与那个能做 4K 30 秒视频的模型完全相同的模型 checkpoint 里，对吧？它们可能无法以完全相同的方式进行训练，对吧？所以我不知道，这取决于你看多长远的未来。当然，从现在起五年后，它们会全部变成同一个模型吗？很可能。但六个月后，我们可能仍然会有多个不同的模型在做不同的事情，因为从务实角度来看，这些权衡决定了我们应该保留多种不同类型的模型。

<details><summary>Original English</summary>
>> nano banana too light yeah right it's it's it's it serves a particular niche right and it probably doesn't necessarily fit immediately in the same model literally checkpoint as uh something that can do 4K you know uh 30 secondond videos right like they're probably not like trainable in the same quite way, right? Like, so I I don't know. It depends on how how far into the future you look like. Sure, in five years from now, will they all be the same model? Probably. Uh but like, you know, six months from now, we'll we'll probably still have, you know, multiple different models doing different things because kind of from pragmatically the trade-offs are such that we we should have multiple different kinds of models.
</details>

>> 是的，我……

<details><summary>Original English</summary>
>> Yeah, I
</details>

>> 我觉得没错。顺着这一点来说，我们确实把它命名为 Gemini Omni，因为我们希望暗示未来的方向，也就是 Gemini 会变成完全端到端的多模态输入和输出，对吧？所以这绝对是朝那个方向迈出的一步。我认为我们很可能会看到它朝着 Omni 也能生成图像、编辑图像以及处理所有这类事情的方向发展。但 Doo 说得对，我认为在走向那一步的过程中，其中一些更专用的模型有着一系列非常非常有用的应用。所以我们可能也会继续在这些模型上投入，因为这满足了现阶段的某种需求，而这种需求在一年后可能就不存在了。此外还有一个研究问题，就是不同模态之间究竟存在多少迁移（transfer），对吧？我想可能有人会相信写代码和视频生成之间存在某些迁移，而我觉得大多数人未必这么认为，但你可以尝试去设想那里可能存在某种联系；或者把它们放在一起、试图同时学习这两项任务可能是一种浪费。所以我认为这是一个有趣的问题：图像和视频之间显然存在某种迁移，它们差别没有那么大；同时学习输出视频和音频是有价值的，因为音画联合本来就是自然形态。此外还有其他一些不是那么显而易见的模态交叉，比如 3D 表征与编程，不知道，也许有诸如此类的东西。所以我认为探索其中的不同切入点是值得的，我们也在积极地做这件事，重点放在人们真正想用这些模型来做什么上。

<details><summary>Original English</summary>
>> I think that's right. And and just on that note, I mean, we did call it Gemini Omni because we wanted to hint at the future where Gemini just becomes fully multimodal in and out, right? And so so it's definitely a move in that direction. I think we'll probably see a move in the direction where Omni also generates images and edits images and all those kinds of things. But Doo is right that I think on the way there, there's a bunch of really really useful applications of some of these more specialized models. And so we we will probably continue to work on those as well because like that serves a certain need at this point in time that may not exist you know a year from now. There's also like a research question about like just how much transfer there is between different kinds of modalities, right? I think you may believe that there's some transfer between coding and video generation and I think most people don't necessarily believe that but they you know you could try to think that there is some some there something there or it could be a waste right to put them together to try to learn these both tasks at the same time right so I think it's it's it's interesting sort of question to which extent like image and video obviously kind of there's some transfer like kind of not that different there's value in in learning to output video and audio at the same time because joint audio visual is you know that's how that's how it is. Um and then there's you know other kind of intersections of modalities that are not super obvious right like 3D representation coding I don't know maybe uh things like that right so like I think it's worth sort of exploring the different corners there and we are actively doing that um with a focus towards like what people actually want to do with these models
</details>

>> 对。有一件事让我感到有些意外，但同时也觉得尚未得到充分的解答，那就是：什么是正确的中间表征？比如描述文本（captioning），对吧？xAI 在做 captioning，Omni 也在做 captioning。我理解 captioning 在图像上是如何运作的，也理解你可以把它拓展到视频中并在时间维度上进行引导。只是这感觉非常低效，一定有……我觉得应该有更好的东西。也许是代码，也许我们生成……显然我认为很多视频是通过 FFmpeg、Matplotlib 以及——那个 3Blue1Brown 做的叫什么来着——Manim，很多视频是通过代码生成的，也许那就是最优的表征。关于它是否更好，或者单纯用英语就足够了（all you need），有什么假设吗？

<details><summary>Original English</summary>
>> yeah um what one thing I feel I feel like uh I'm surprised by but also I feel like it's insufficiently answered is what is the correct intermediate representation Um, so captioning, right? XI does captioning. Omni does captioning. Um, and I I I understand how captioning works for images. Um, and I understand that you can extend it into to video and and sort of guide it across time. It just feels very inefficient. It there's got to be I feel like there should be something better. Uh maybe it's code and maybe we generate you know and obviously I think a lot of um ffmpeg and mapplot um what's the three blue one brown one manm um a lot of like video is generated through code and maybe that's like the optimal representation uh any hypothesis as to like is is it better or is just English all you need
</details>

>> 这个嘛，鉴于……我处于

<details><summary>Original English</summary>
>> well as so I'm in the
</details>

<!-- chunk 3/8 -->

Gemini，他们知道我们做了很多强化学习智能体（RL agent），当然也有编程方面的工作，所以是的，我们确实在探索代码表示形式。
<details><summary>Original English</summary>Gemini and they know we do like a lot of RL agent and of course kind of coding so yeah We we're definitely exploring the coding representations.</details>

>> 是的。
<details><summary>Original English</summary>>> Yeah.</details>

>> 作为一种更好的表示方式。是的。
<details><summary>Original English</summary>>> As kind of better kind of way to represent. Yeah.</details>

>> 但是，你知道，你的概率估计是多少，比如［笑声］如果我们只输出二进制代码，比如我们只是，你知道，输出纯粹的 0 和 1 呢？
<details><summary>Original English</summary>>> But you know like do you what's your probability estimate on like [laughter] if we just output binaries like we just you know like just it's just ones and zeros.</details>

>> 嗯，我想类似的一个讨论基本上是，语言是否是正确的表示形式，对吧。比如，一个问题是，比如有的教授会问，为什么思维链（channel of thought）必须用自然语言？
<details><summary>Original English</summary>>> Um I I guess maybe a kind of similar discussion was like um basically is the language the right representation like right. So uh one kind of question for example uh professor you know like some ask is like you know why why does the channel of thought need to be in the natural language?</details>

>> 是的。
<details><summary>Original English</summary>>> Yes.</details>

>> 它能不能就只是某种连续的标记（continuous tokens），纯粹是某种量的额外计算？
<details><summary>Original English</summary>>> Can it just be the kind of any kind of like continuous tokens just any amount of you know additional computations.</details>

>> 嗯，一方面显然测试阶段的自适应计算（test-adaptive compute）会带来更好的结果。确实是这样，但真正让思维链行之有效的原因是——你知道，四年前我写了《Large Language Models are Zero-Shot Reasoners》，然后是自我改进（self-improvement）。所以我很早就知道这一点，但它真正起效的原因是，目前行之有效的方法是大幅扩展预训练，而这基本上学到了大量的智能。现在有很多扩展强化学习（scaling RL）的研究，但那些要提取信息仍然是极其计算密集型的。你真正希望智能依赖于预训练，所以基本上通过将推理绑定在自然语言上，你就直接利用了预训练中的智能；而如果你去掉了这种约束，你就无法做到这点。最近我觉得不仅在文本领域有很多进展，在多模态领域的进展很大程度上也是由文本作为一种绝佳的表示形式所推动的。
<details><summary>Original English</summary>>> Um so one is like obviously the test like adaptive compute is going to give like you know better results. So it's that but what really kind of made CH thought so you know like four years ago I wrote you know the larger model zero sort reasoner and then self-improvement. So I kind of know from the very early day but the reason like it works really well is um right now the recipe that works is the pre-training that scales a lot and then that basically like learns a lot of intelligence. there are a lot of you know scaling RL but those are still like extremely kind of comput incent intensive to extract the information and um you really want to rely the intelligence on that so basically by tying the sort of like a reasoning in the natural language you basically directly use the intelligence of the pre-training to it while if you remove that kind of constraints then you're not um and these days uh I feel the a lot of advancements in the texts but also doing this kind of multimodal space is very driven by this uh kind of text as a kind of great uh sort of representation.</details>

>> 是的，它是一个很好的骨架。
<details><summary>Original English</summary>>> Yeah, it's a good backbone.</details>

>> 是的。
<details><summary>Original English</summary>>> Yeah,</details>

>> 我觉得对我来说甚至比那更简单。文本就是我们沟通的方式。所以从根本上讲，如果你正在构建人类要与之交互的产品，如果是文本界面，我们无论如何都会以某种方式使用文本，对吧？虽然不是所有事物都如此。所以我认为默认采用文本是很自然的。
<details><summary>Original English</summary>>> I I think to me it's even simpler than that. It's text is is how we communicate. So I think fundamentally if you're building kind of products that humans will be interfacing with um like like that we will be using text somehow if it's a text interface, right? Not not for everything. So I think it's it's natural to default to that.</details>

### 世界模型与多模态表示

>> 是的。显然有一些讨论，你知道，一些强化学习极大主义者（RL maximalists）会说，哦，我们不在乎这类通道之类的东西，它就只是额外的计算。
<details><summary>Original English</summary>>> Yeah. Obviously there's like a conf discussion you know some arrow like arrow maximalists is like oh we don't care about you know kind of channel those kind of like stuff it's just just additional compute</details>

>> 当然，但我个人……是的。
<details><summary>Original English</summary>>> sure but I personally yeah</details>

>> 强化学习极大主义者，我想知道谁符合这个描述，David Silver？
<details><summary>Original English</summary>>> ro maximalists I wonder I wonder who who qualifies in that description David silver</details>

>> 啊，好的，是的。他们刚刚离开去创办自己的项目了。很有意思。好的，我是说，我对更好的表示形式非常感兴趣，因为我觉得这是我们今天在世界博览会上策划的主题之一，也就是世界模型。你提到了“世界模型”这个词，但它并不是一个被非常唯一定义的概念。我觉得大家都在趋向于某种理想中的版本。
<details><summary>Original English</summary>>> ah okay yeah I mean they they've just left to to start their thing um interesting okay so uh I I mean I think I'm very interested in just like better representations because I think that's one of our themes that we're curating today uh at the world fair is world models. You mentioned the word world models but it's not something that's like super well defined. I think everyone's like sort of converging on some version of it that is like the ideal.</details>

>> 当然。现在什么都被称为世界模型了。它有点像……
<details><summary>Original English</summary>>> Sure. Everything is a world model now. It's sort of a</details>

>> 这就没那么有用了，对吧？
<details><summary>Original English</summary>>> it's not it's not that useful, right?</details>

>> 我刚刚在 ICLR 世界模型研讨会上发表了主题演讲。是的。基本上，我非常建议大家去看看 Jitendra Malik 给出的定义。他是加州大学伯克利分校计算机视觉领域的元老级教授。
<details><summary>Original English</summary>>> So I just gave a keynote at the IER world model workshop. Yeah. And then uh yeah essentially uh I definitely encourage to check out the definition by Jandra Matic. He's like the you know OG computer vision professor UC Berkeley.</details>

>> 关于世界模型，他确实有一些很有分量的话要说。
<details><summary>Original English</summary>>> Uh he has pretty you know bit of word to say about world model</details>

>> 但也可以看看 Schmidhuber 在 1990 年左右是如何定义世界模型的，基本上就是基于模型的（model-based）。对我来说，世界模型基本上就是基于模型的强化学习中的模型，我觉得这足以用来描述它，但显然……Fei-Fei 写过一篇不错的博文，剖析了这个问题。
<details><summary>Original English</summary>>> but also kind of Schmidt Herburver's kind of how he defined the world model from 2019 like 1990 sort of uh uh you know like Wayne was just basically just that kind of model base. Uh for me the word model is basically just the model in the model based RL and I feel that has sufficient to describe but obviously you know there are like a lot of uh FE had a kind of nice blog post about what about yeah this kind of broken down</details>

>> 嗯，但是是的。
<details><summary>Original English</summary>>> um but yeah</details>

>> 是的，我是说，我先结束这部分的讨论，但我确实认为，把语言当作万物穿过的窄通道来依赖，仍然是一种有损压缩。不，不，不。但我们并没有这样看，对吧？我们基本上是在说视频模型和语言模型结合在一起。
<details><summary>Original English</summary>>> yeah I mean so you know I I'll end this part of the conversation but like I I do think that language to me relying on language as like the sort of like the narrow pipe through which everything goes through um still is like a lossy compression. No, no, no. But we're not seeing that, right? We're basically saying the video model and the language together.</details>

>> 所以，我认为单靠语言是不够的。这就是为什么我们觉得视频是一种非常互补的模型。对吧？现在很多人把 Video Omni 看作只是用来生成漂亮的视频，但我认为我们的愿景远不止于此。它是一个缺失的基础模型，如果你想打造能够媲美人类而非仅仅是单一领域的通用人工智能（AGI），它是绝对必须的。
<details><summary>Original English</summary>>> So, so I think the language alone is uh not sufficient. That's why we feel like the video is a very complement model. Right? Now the um you know kind of v omni many people feel as uh you know generating kind of pretty videos but I think our vision it's it's much more than that. It's a missing foundational model that's absolutely required if you want to make the AGI that match to humans not just a jacked one.</details>

### 从视觉理解到生成的研究演进

>> 是的。好的。另一件事，你在视觉方面也提到了，我很好奇就你们的研究生涯而言，这种发展在某种程度上是怎样平行的。比如，我认为基本上很多做视觉的人都跨界去做了更多的模型，很多做视觉的人也变成了做生成式视频和图像的人。这是否就像把“图像到文本”反过来变成现在的“文本到图像”那么简单，比如……
<details><summary>Original English</summary>>> Yeah. Um okay. So one one other thing you know you you mentioned on the vision side um and I'm kind of curious how sort of uh parallel you know in terms of your research careers um this development is like I think basically a lot of vision people have crossed over into more model people um a lot of vision people also become generative video and image people and is it just as simple as you know reversing uh image to text and then now it's text to image like</details>

>> ［笑声］
<details><summary>Original English</summary>>> [laughter]</details>

>> 如果……我是说，这在实际上就是扩散过程（diffusion process）。我只是看到与我交流过的人的职业路径，看到了研究方向的这个总体趋势，我只是想让你们两位反思一下这一点。
<details><summary>Original English</summary>>> is is that if I mean that effectively was the diffusion process. Um I I just you know I I just see the career paths of the people that I talked to and and see and I I I see this overall trend of research directions and I just wanted you to guys to sort of reflect on on that.</details>

>> 我的确是走的那条路，对吧。我很久以前开始做计算机视觉，做目标检测、识别之类的事情。我认为那只是更简单的问题，对吧。生成就是更难，它是不同类型的映射，对吧。逆向映射并不像把你用的网络反转过来那么简单，对吧？它更加模糊，比如从“猫”这个词生成一张猫的图像。而且在某些方面它也是一个闭环，因为你的视觉工作会创造合成标签，进而继续……
<details><summary>Original English</summary>>> I mean I certainly went that way right I I started long time ago uh doing computer vision sort of object detection recognition things like that. Uh I think just that's just simpler problem right just generation is just harder like it's a it's a different kind of mapping right you map from the the inverse mapping is not as simple as just inverting the the kind of network you use right it's it's a it's it's more ambiguous right to go from cat to image of a cat and in some ways it's also a loop because your vision work creates the synthetic labels that then continues</details>

>> 当然［笑声］。我不知道，我试图去验证我关于领域如何发展、职业生涯如何在这个过程中演进的理论。
<details><summary>Original English</summary>>> I mean sure [laughter] I don't know I don't know I try to validate my my sort of theories about how fields develop how how careers has progressed through this</details>

>> 理解端做得越好，我们看到生成端也会变得越好，对吧，所以……
<details><summary>Original English</summary>>> I mean for like the the the better the understanding side gets like we have seen that the generation side also gets better right so like like</details>

>> 这完全是自举（bootstrapping），是的。
<details><summary>Original English</summary>>> it's completely bootstrapping yeah it's</details>

>> 所以这个论点绝对是成立的。而且我想，是的，我认为很多人确实有这种转变。我确实与很多从图像理解转到图像生成的人共事过，然后其中一些人又转向了视频，因为视频就像是下一步，有更多的维度可以处理。所以我很好奇你的……
<details><summary>Original English</summary>>> and so like like like there's definitely they're there to that thesis and I think yeah I think a lot of people have kind of like I I definitely worked with a lot of um image understanding people who became image generation people you know and then some of them have moved on to video because it's kind of like the next thing where you have so many more dimensions to work with so yeah I'm curious about you spec as your</details>

>> 所以我非常建议从理解和识别开始，因为那基本上就是判别器，随后会带来更好的生成，而其中的桥梁基本上就是强化学习。我的历程是，我最初从事生成对抗模型（GAN）的算法研究，做一些类似 MNIST 的生成，然后我从事强化学习和机器人技术。大约六年前，我领导了一个灵巧操作（dexterity）方面的登月项目，那时还很早，但我看到现在大家都在做。四年前，我基本上意识到这种符号化 AGI 的发展速度将远远快于物理世界的 AGI 对应物。所以我决定转向语言模型等方向。最近我和 Doomi 以及 Omni 团队合作，我非常享受那里的合作。我非常喜欢、也非常推荐研究人员去做的事情是，一定要去探索或者至少接触各个社区顶尖人物在关注什么、他们如何思考问题。所以当我看到视频模型时，它让我想起了很早期的语言模型，当时的早期语言模型就像是一种创意的演示，对吧，你试着写个故事，比如像 GPT-2 以及那个时期的 LSTM 之类的……
<details><summary>Original English</summary>>> so I definitely like recommend start with understanding recognition because that's basically discriminator and then that's going to lead to better generation and that's what the bridge is basically reinforcement learning so my um my kind of journey is I initially kind of worked on the algorithmic research in the gent model against some like you know amnest kind of generation and then I worked on like RL and robotics um and then like six years ago I was like leading like a moonshot on the dexterity it was pretty early but I see now everyone's kind of doing uh four years ago I basically kind of figured out that this like symbolic AGI is going to accelerate much faster than the kind of physical AGI kind of counterpart. So uh I decided to kind of like language models and then those things. Um and then recently kind of work with Doomi and then like omni team I quite enjoy kind of collaboration there. the what I quite enjoy uh what I recommend definitely to the researcher is to uh definitely kind of explore or at least like get exposure to what the top people in each of the community are like looking at how they kind of think about problems. So when I look at the video model to me it kind of reminds me like pretty early on sort of like language model where like very early language model was a kind of creative sort of demo right you kind of like try to write like a story like mobile and then like you know GBD2 and then those kind of days like LTM kind of</details>

<!-- chunk 4/8 -->

### 视频模型与多模态统一的路径

……时期，对吧。然后，你知道，做指令微调（instruction tuning）确实能让它在某种程度上用作聊天机器人，但在聊天机器人那个阶段，它仍然有非常多的幻觉，指令遵循（instruction following）能力也不够好，所以没法用于推理。而当在预训练和用于推理的后训练中做得足够好之后，你知道，这种测试时扩展（test-time scaling）和强化学习（RL）确实爆发了，催生了许多表现最好的模型。现在我认为视频模型就像我们之前提到的，它是一个互补的基础模型，我可以想象它会沿着类似的路径演进：它的指令遵循能力会大幅提升，在减少幻觉方面也会大幅改善，以至于演变成一个非常可靠的世界模型，这样我们就可以把类似视频的时空模拟与文本模拟结合起来，去解决任意的 AGI 问题。而且我认为，文本模型与图像、视频模型之间的区别仍然在于，我们在多媒体领域似乎还没有真正把理解与生成统一起来。我的意思是，当然这取决于你从哪个层面去思考这个问题，但总体而言，据我所知，并没有那么多前沿模型能够真正同时擅长视频的理解和生成，对吧？这是一个有趣的挑战。我并不是说我们一定要这么做，但我认为这在逻辑上是站得住脚的，也就是理解和生成是同一枚硬币的两面，所以在某种程度上它们应该被整合在同一个模型里。但我们并不一定总是这么做。所以，是的。

<details><summary>Original English</summary>
 days

 right

and

 then

 you

 know

 uh

 instruction

 tuning

you

 actually

 kind

 of

 make

 it

 usable

 as

 a

chatbot

 but

 then

 at

 the

 chatbot

 stage

 it

still

 had

 so

 much

 hallucinations

 and

instruction

 for

 wasn't

 good

 enough

 so

 it

couldn't

 use

 for

 reasoning

 and

 when

 I

got

 good

 enough

 um

 in

 pre-training

 and

post-

 trainining

 for

 reasoning

 then

 you

know

 this

 kind

 of

 test

 time

 scaling

 the

RL

 really

 took

 off

 to

 like

 many

 of

 the

kind

 of

 best

 performing

 models

 and

 right

now

 I

 think

 the

 video

 model

 is

 as

 we

mentioned

 it's

 it

 is

 a

 complimentary

foundational

 model

 and

 I

 can

 imagine

it's

 going

 to

 follow

 a

 similar

 path

 it's

going

 to

 be

 very

 uh

 it's

 going

 to

improve

 a

 lot

 instruction

 following

 a

lot

 of

 uh

 this

 it's

 going

 to

 improve

 a

lot

 in

 reducing

 coordinations

 to

 extend

that

 it

 become

 a

 very

 reliable

 world

model

 so

 we

 can

 kind

 of

 like

 intermixed

video

 like

 space-time

 simulation

 was

 a

text

 simulation

 to

 solve

 like

 arbitrary

AGI

 problems.

 Also

 like

 I

 think

 the

difference

 still

 is

 between

 sort

 of

 text

models

 and

 like

 image

 video

 models

 is

that

 like

 we

 haven't

 quite

 unified

understanding

 and

 generation

 in

 in

multimedia

 I'd

 say

 yet

 like

 I

 mean

 I

think

 I

 think

 without

 going

 to

 the

details

 of

 course

 there's

 like

 it

depends

 on

 on

 at

 which

 level

 you're

thinking

 about

 this

 but

 generally

 like

there's

 not

 that

 many

 as

 far

 as

 I

 know

models

 sot

 kind

 of

 you

 know

 frontier

models

 that

 are

 genuinely

kind

 of

 good

 at

 both

 understanding

 and

generation

 of

 of

 let's

 videos,

 right?

Like

 it's

 a

 it's

 a

 it's

 an

 interesting

challenge.

 I'm

 not

 saying

 that

 we

 should

do

 this.

 Uh

 but

 but

 I

 think

 uh

 it

 kind

of

 stands

 to

 reason

 that

 like

 you

 know

understanding

 and

 generation

 are

 two

sides

 of

 the

 same

 coin.

 So

 they

 they

kind

 of

 should

 be

 in

 the

 same

 model

 in

some

 ways.

 Uh

 but

 we

 don't

 necessarily

always

 do

 that.

 So

 yeah.
</details>

>> 你也提到了音频，对吧？是的。它有视频那么难，还是在本质上有所不同？如果是的话，在哪些方面不同？三年前一个有趣的方向是大家开始用……我想是用扩散模型来做音频，也就是类似 Riffusion 的那种方法。我不知道你们有没有看过。我只是觉得这非常有趣：如果我们人类感知中的一种模态——音频——与视频不同，但对机器来说，实际上完全是一回事，就像它们看两者没有任何区别。

<details><summary>Original English</summary>
>> Uh

 you

 mentioned

 audio

 as

 well,

 right?

Yeah.

 Uh

 is

 that

 as

 hard

 as

 video

 or

qualitatively

 different?

 If

 if

 so,

 in

what

 way?

 Uh,

 one

 of

 the

 interesting

directions

 three

 years

 ago

 was

 people

using

 um,

 I

 guess

 diffusion

 to

 do

 audio

uh,

 as

 in

 like

 the

 the

 sort

 of

 refusion

approach.

 I

 don't

 know if

 you

 you

 guys

saw

 that.

 Um,

 and

 I

 just

 think

 it's

 like

very

 interesting

 if

 a

 modality

 that

 we

perceive

 which

 is

 audio

 is

 different

than

 video

 actually

 two

 machines

 is

exactly

 the

 same

 like

 there's

 they

 see

no

 difference.
</details>

### 音视频联合生成的逻辑

我觉得在技术层面上确实有一些差异，但相对来说比较小。从我的角度来看，音频进入我的视线是在我们发布 V3 的时候，我认为那是第一个实现联合……

<details><summary>Original English</summary>
I

 mean

 I

 think

 on

 a

 technical

 level

there

 are

 some

 differences

 but

 I

 think

they're

 like

 relatively

 minor.

 I

 think

from

 my

 perspective

 audio

 came

 into

 into

my

 life

 when

 we

 shipped

 V3

 which

 was

 I

believe

 the

 first

 model

 that

 did

 like

 a

joint
</details>

>> 带着切金条之类的片段。

<details><summary>Original English</summary>
>> with

 the

 slicing

 of

 the
</details>

>> 是的，是的，切金条之类的。它是第一个实现这种联合音视频生成的模型。是的。在……我的意思是，之前也有其他模型在底层做了一些类似智能体拼接的处理，但这个模型是真正做到了一次性生成所有内容。我们这么做的原因是因为我们觉得——而且我认为这是正确的选择——我们觉得只有把它们同时生成才合理，因为从机器学习的角度来看，存在一个潜在的、因果的生成过程，对吧？就像有什么东西在产生你在说话的动作，并不是先生成像素，然后音频再通过某种其他过程生成出来；嘴唇必须与音频同步运动，对吧？所以，我认为这解决了之前模型存在的很多问题，或者说解决了人们以前做视频生成的方式，以前的方式就像是：好，我们先生成像素，然后在上面硬凑一个东西，让嘴唇随着我们生成的音频动起来。那效果非常差。

[笑声]

所以，我认为那对我来说就是……我的意思是，在 V3 之后，人们就会觉得：“你模型里怎么会没有音频呢？这毫无道理，一旦有了音频，你就必须具备这项能力。”所以我认为那是正确的选择，把它们做进一个单一的生成模型里，我认为是正确的选择。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 the

 gold

 bars

 or

 whatever.

Um

 it

 it

 was

 the

 first

 model

 that

 did

this

 sort

 of

 joint

 audiovisisual

generation.

 Yes.

 uh

 like

 in

 the

 in

 the

 I

mean

 there

 are

 there

 were

 other

 models

that

 did

 kind

 of

 you

 know

 kind

 of

 kind

of

 agentic

 hacking

 under

 the

 hood

 but

this

 one

 was

 truly

 sort

 of

 you

 know

generating

 everything

 at

 once

 and

 we

 the

reason

 we

 did

 that

 is

 because

 we

 felt

and

 I

 think

 was

 the

 right

 choice

 we

 felt

that

 like

 uh

 it

 only

 makes

 sense

 to

generate

 them

 at

 the

 same

 time

 because

there

 sort

 of

 kind

 of

 like

 from

 a

machine

 learning

 perspective

 there's

 one

latent

 kind

 of

 you

 know

 causal

 kind

 of

you

 know

 generative

 process

 right

 like

there's

 something

 that

 generates

 you

speaking

 it's

 not

 the

 pixels

 and

 then

the

 the

 audio

 or

 somehow

 somehow

generated

 by

 some

 other

 process

 like

 the

lips

 have

 to

 move

 in

 sync

 with

 with

 the

with

 the

 audio,

 right?

 So,

 I

 think

 that

that

 solved

 a

 lot

 of

 the

 issues

 that

previous

 models

 had

 or

 the

 way

 that

people

 did

 video

 generation

 before

 where

it

 was

 like,

 okay,

 we

 generate

 the

pixels

 and

 then

 we're

 going

 to

 hack

something

 on

 top

 of

 it

 that

 like

 moves

the

 lips

 with

 the

 audio

 that

 we

generate.

 And

 that's

 was

 very

 bad.

[laughter]

And

 so,

 I

 think

 I

 think

 that

 was

 that's

to

 me

 that's

 the

 the

 I

 mean

 after

 V3

like

 you

 know

 people

 were

 like

 what

 do

you

 mean

 like

 there's

 no

 audio

 in

 your

model?

 like

 that

 makes

 no

 sense

 like

once

 it's

 there

 like

 you

 you

 have

 to

have

 it.

 So

 I

 think

 that

 was

 that

 was

the

 right

 choice

 and

 doing

 it

 to

 one

single

 generative

 model

 I

 think

 was

 was

the

 right

 choice.
</details>

### 感官体验与语言表达的局限

>> 有一件事我也想问问你们的看法。我发现音频与图像、视频相比的一个不同之处在于，音频信息较少被语言化。我的意思是，文本转语音（TTS）之类的当然很简单，对吧，但是当你脱离这些，比如怎么去描述音乐？怎么去描述一个人说话的语气、音高？我觉得这方面的语言表达是匮乏的。有趣的是，你也会在其他两件事上看到这种情况，比如味觉，还有比如触觉……

<details><summary>Original English</summary>
>> One

 thing

 I

 kind

 of

 want

 to

 also

 can

 ask

you

 guys

 an

 opinion

 as

 well

 once

 one

difference

 I

 find

 the

 audio

 and

 then

against

 the

 image

 and

 video

 is

 like

 the

audio

 information

 is

 less

 verbalized.

 I

mean

 of

 course

 the

 TTS

 and

 stuff

 is

trivial

 right

 but

 the

 when

 you

 get

 her

outside

 like

 how

 to

 describe

 music

 how

do

 you

 describe

 this

 like

 this

 person's

tone

 kind

 of

 pitch

 I

 feel

 the

 sort

 of

the

 verbalization

 is

 insufficient

 and

the

 interesting

 thing

 is

 that

 you

 kind

of

 see

 that

 in

 two

 other

 things

 like

taste

 taste

 sense

 and

 also

 uh

 say

 um

touch
</details>

>> 比如嗅觉，还有另一个有趣的现象是肤色。对于肤色，用来描述肤色的语言相当有限，原因是由于我们对微小的差异扰动极其敏感——是不是肤色——因为那基本上向我们传达了这个人会不会杀我，或者我能不能和这个人做朋友这类信息。我觉得嗅觉、味觉、肤色以及声音这类东西，与极其原始的生存机制紧密相连，以至于我们的感官系统极其敏锐，以至于难以……嗯，举个例子，我问过一位专业品酒师之类的人，他基本上说他会用类似相亲约会、描述伴侣的语言来描述口感，因为没有足够的词汇来描述。嗯，所以我有点好奇。是的，你们有这种感觉吗？

<details><summary>Original English</summary>
>> like

 smell

 and

 then

 the

 another

interesting

 thing

 is

 the

 skin

 color

 so

skin

 color

 the

 the

 language

 is

 pretty

limited

 to

 describe

 the

 skin

 color

 and

the

 reason

 is

 that

 we're

 extremely

 uh

sensitive

 to

 the

 small

 difference

perturvations

 or

 not

 skin

 color

 because

that

 basically

 shows

 us

 is

 this

 person

going

 to

 kill

 me

 or

 is

 can

 I

 befriend

this

 person

 kind

 of

 those

 kind

 of

information

 and

 then

 I

 feel

 the

 smell

tastes

 um

 skin

 color

 and

 like

 sound

 kind

of

 stuff

 is

 very

 very

 tied

 into

primitive

 a

 like

 survival

 kind

 of

 stuff

and

 so

 our

 sort

 of

 sensory

 system

 is

 so

sensitive

 that

 it's

 intractable

 to

 Um,

so

 for

 example,

 I

 asked

 like

 one

 the

wine

 sort

 of

 taster

 and

 then

 like

professional

 and

 then

 he

 basically

 said

he

 kind

 of

 use

 like

 a

 language

 from

 like

a

 dating,

 you

 know,

 describing

 like

 a,

you

 know,

 partner

 as

 a

 way

 to

 describe

the

 taste

 because

 there's

 no

 sufficient

vocab

 to

 describe.

 Um,

 so

 I'm

 kind

 of

curious.

 Yeah.

 Do

 you

 guys

 feel

 that?
</details>

>> 我想，在某种程度上，视觉信息也是如此，对吧？当你想起某种风格或某种美学时，对吧？就像有些人就是拥有发展得更充分的品味，无论是味觉还是视觉品味与审美，对吧？我觉得当你想去描述任何我们在感官上体验到的东西时，语言往往都会成为一种限制因素。正如你刚才所指出的，我认为这就是为什么我们正在投资世界模型，为什么我们正在推动感知和生成这方面的发展，因为这在我们作为人类探索世界的过程中占据了很大一部分。在具身智能（embodied AI）探索世界的过程中也是很大一部分。而且我确实认为，语言虽然让我们走到了今天，而且大概还能带我们走得很远，但在很多这类领域里，它确实让人感到局限。是的，我也不太知道该怎么去描述感官和味觉。不过，是的，我也很好奇。

<details><summary>Original English</summary>
>> I

 think

 well

 to

 some

 extent

 I

 think

 the

same

 is

 true

 for

 visual

 information,

right?

 when

 you

 think

 about

 like

 a

certain

 style

 or

 a

 certain

 aesthetic,

right?

 Like like

 there

 are

 some

 people

who

 just

 have

 a

 much

 more

 kind

 of

developed

 like

 whether

 it's

 palette

 or

kind

 of

 visual

 taste

 and

 aesthetic,

right?

 Like

 I

 I

 think

 language

 just

tends

 to

 be

 a

 bit

 of

 a

 limiting

 factor

when

 you

 are

 trying

 to

 describe

 any

 of

these

 things

 that

 like

 we

 experience

with

 sensory

 information.

 And

 to

 your

point

 earlier,

 I

 think

 that

 is

 the

 kind

of

 the

 reason

 why

 we

 are

 investing

 in

world

 models

 and

 why

 we

 are

 pushing

 on

kind

 of

 the

 like

 perception

 and

 like

generation

 side

 of

 things

 because

 it

 it

is

 such

 a

 large

 part

 of

 how

 we

 as

 humans

navigate

 the

 world.

 It's

 a

 large

 part

 of

how

 like

 embodied

 AI

 navigates

 the

world.

 Um,

 and

 and

 I

 do

 I

 do

 think

language

 like

 does

 have

 a

 lot

 of

 it's

it's

 gotten

 us

 very

 far

 and

 it

 can

probably

 get

 us

 really

 far,

 but

 it

 it

feels

 limiting

 in

 a

 lot

 of

 these

 kind

 of

areas.

 And

 yeah,

 I

 don't

 I

 don't

 really

know

 how

 to

 describe,

 you

 know,

 like

sense

 and

 taste.

 Um,

 but

 yeah,

 I'm

curious

 to

 me.
</details>

>> 嗯，我……是的，我不知道自己是否对这个问题有过那么深入的思考。所以，呃，是的，我对音频给不出一个很好的答案。我的意思是我不知道边界在哪里，因为我在想 Omni 在音频方面有什么做不好的，但我发现那些似乎都是可解决的问题，比如通过更多数据或更好的数据之类的方式。所以我不知道我们是否已经把前沿推到了触及某种源于人类进化所施加的限制。我不知道。他感受到了图文描述（captioning）的局限，这正是我之前……

<details><summary>Original English</summary>
>> Um,

 I

 I

 yeah,

 I

 don't

 know

 that

 I

 have

thought

 that

 deeply

 about

 this

 yet.

 So,

uh,

 yeah,

 I

 mean

 yeah,

 I

 don't

 have

 a

good

 answer

 about

 audio.

 I

 mean

 like

 I

don't

 know

 the

 limit

 because

 I'm

thinking

 about

 like

 well

 what

 is

 what

 is

Omni

 bad

 at

 in

 terms

 of

 audio

 but

they're

 all

 like

 solvable

 problems

 I

find

 uh

 so

 like

 with

 more

 data

 or

 better

data

 or

 whatever

 it

 is

 so

 I

 don't

 know

like

 that

 we

 have

 pushed

 the

 frontier

 so

much

 that

 like

 we

 are

 have

 hit

 some

 sort

of

 limits

 that

 are

 rooted

 in

evolutionary

 uh

 kind

 of

 you

 know

 limits

imposed

 by

 humans.

 I

 don't know.

 He's

feeling

 the

 limits

 of

 captioning

 which

is

 the

 the

 thing

 I

 was
</details>

>> 是的，没错。[笑声] 世界上存在很多信息，这也基本上联系到了你刚才提到的我们为什么做世界模型。你只需要 srefs，sref 476，然后那就是你的……那就是你的旅程所做的事，对吧？我猜也许我没法描述这种感觉，但是……

<details><summary>Original English</summary>
>> Yeah,

 exactly.

 [laughter]

 There

 there's

a

 lot

 of

 information

 in

 the

 world

 and

 it

connects

 to

 basically

 why

 we

 do

 work

modeling

 you

 mentioned.

 You

 just

 need

srefs

 sref476

and

 then

 that's

 your

 that's

 what

 your

journey

 does,

 right?

 I

 guess

 maybe

 I

can't

 describe

 this

 vibe

 but
</details>

>> 嗯，我认为提供这些参考样本的意义就在这里，对吧？因为哪怕只是描述某人如何说话、他们的语气、韵律以及所有这些东西，我认为甚至有些术语连我以前都不知道是什么意思，对吧？现在……

<details><summary>Original English</summary>
>> well

 well

 I

 think

 that

 that's

 kind

 of

the

 point

 of

 providing

 some

 of

 these

references,

 right?

 Because

 because

 like

even

 just

 describing

 how

 someone

 talks

and

 like

 their

 tone

 and

 and

 like

 procity

and

 all

 of

 these

 things

 like

 I

 think

 I

think

 some

 of

 these

 terms

 even

 like

 I

didn't

 used

 to

 know

 what

 they

 mean,

right?

 Well,

 now
</details>

>> 是的。言语不流利（disfluencies）……就像存在一整套词汇，如果你不是深入某个领域——实际上人类大多数领域都是如此——你甚至都不知道它意味着什么。嗯……

<details><summary>Original English</summary>
>> yes.

 Dispuencuencies

 ex

 like

 like

 there

there's

 kind

 of

 an

 entire

 vocabulary

that

 even

 if

 you're

 not

 kind

 of

 steeped

in

 a

 domain,

 which

 is

 true

 for

 actually

like

 most

 human

 domains

 that

 like

 you

don't

 even

 know

 what

 it

 means.

 Um
</details>

<!-- chunk 5/8 -->

而且有时这也是一个问题，比如如果我们没有把重点放在那些事情上，你知道，在大语言模型上，它们在那些领域可能也存在欠缺，对吧？然后我们在生成端的另一侧就会感受到它们，因为我们从根本上依赖语言模型对世界的理解来去表征它。嗯，所以我，是的，这一切有点又回到了你之前关于将语言作为中介的问题。嗯，不过是的，我认为正如 De 所说，其中一些可能只是重点领域以及我们不一定尽全力去推进的事情，随着我们逐步推进，我们会发现真正的上限在哪里。

<details><summary>Original English</summary>
 and

sometimes
 it's
 also
 a
 question
 of
 like

if
 we
 haven't
 focused
 on
 those
 things,

you
 know,
 with
 the
 large
 language
 models

that
 they
 may
 also
 have
 gaps
 in
 those

areas,
 right?
 And
 then
 we
 feel
 them
 on

the
 other
 side
 with
 generation
 because

we're
 like
 fundamentally
 relying
 on
 on

the
 language
 models
 understanding
 of
 the

world
 to
 then
 be
 able
 to
 like
 represent

it.
 Um,
 so
 I
 yeah,
 it
 all
 kind
 of
 goes

back
 to
 your
 question
 about
 like
 the
 the

language
 as
 an
 intermediary.
 Um,
 but

yeah,
 I
 think
 to
 De's
 point
 like
 some
 of

these
 might
 just
 be
 like
 focus
 areas
 and

things
 that
 we
 haven't
 necessarily

pushed
 on
 as
 much
 as
 we
 can
 and
 like
 as

we
 will
 we
 will
 discover
 what
 the
 actual

ceiling
 is.
</details>

>> 是的，作为一名播客主持人，我经常思考声音的问题。

<details><summary>Original English</summary>
>> Yeah,
 as
 a
 podcaster
 I
 think
 a
 lot
 about

sound.
</details>

>> 嗯，而且我想抛出几点来供大家讨论，万一能触发你们的某些想法呢。嗯，我有三个大致的音频领域，也就是音乐、人声、音效，你知道，这样粗略划分是不是能涵盖所有内容；然后即便在人声内部，咱们就只聚焦在人声上，先不管另外两个。嗯，房间声响，比如大房间、小房间、面对面、在车里、通过电话的回声感，所有这些都是可以打标签的，但我们的体验却大不相同。我常常觉得 AI 视频的特征之一就是它具有录音室品质，因为它是在录音室视频中录制的，因为那是你的训练数据。而且对我来说，那确实是一件……实际上最有趣的事情就是，嗯，当我向那些对世界模型需求持怀疑态度的人解释时，我就是用这个来说服他们的，因为你即便在音频上也需要它，比如“我离你更远，所以我听起来应该稍微轻柔一点或者更扩散一些”，而且视频模型需要捕捉到这一点，因为如果它们要制作沉浸式视频和音频，你就需要那个。

<details><summary>Original English</summary>
>> Um,
 and
 and
 I
 I'll
 just
 offer
 a
 couple

things
 for
 discussion
 in
 case
 in
 case
 it

triggers
 anything
 with
 you
 guys.
 Um
 I

have
 three
 domains
 of
 rough
 audio
 which

is
 like
 a
 music
 voice
 SFX
 you
 know
 is

that
 rough
 okay
 covers
 everything
 and

then
 also
 even
 within
 voice
 let's
 just

let's
 just
 focus
 on
 voice
 forget
 the

other
 two
 um
 room
 sound
 like
 the
 the

echoiness
 of
 like
 big
 room
 small
 room
 in

person
 in
 a
 car
 over
 a
 phone
 all
 these

like
 are
 labelable
 but
 we
 experience

them
 very
 differently
 and
 I
 I
 often

think
 like
 one
 of the
 tells
 of
 a
 AI

video
 is
 that
 it
 is
 studio
 quality

because
 it
 was
 recorded
 in
 a
 studio

video
 because
 that's
 your
 training
 data

and
 like
 and
 and
 to
 me
 that's
 one
 thing

actually
 like
 the
 most
 interesting
 thing

is
 just
 uh
 when
 I
 tell
 this
 is
 how
 I

convince
 people
 who
 are
 kind
 of

skeptical
 about
 the
 need
 for
 world

models
 because
 you
 need
 it
 even
 for

audio
 about
 well
 I'm
 further
 away
 from

you
 so
 I
 should
 sound
 a
 little
 bit

softer
 or
 more
 diffused
 and
 like
 the
 the

video
 models
 need
 to
 pick
 that
 up

because
 if
 they're
 going
 to
 do
 immersive

video
 and
 audio
 you
 need
 that
</details>

>> 我很喜欢那个例子，基本上就是录音室品质与否的问题。在某种程度上，我们没有足够的语言来真正描述这种回声，或者正在发生的某种噪音，我们就是没有足够精准的词汇。而且，如果你……基本上我认为拥有相对信息丰富的描述文本非常重要的原因，就是我们有点依赖自然语言作为一种表征，但如果你基本上没有足够的表征，那就意味着以语言为条件，生成是非常多模态的。如果能从 BAE 那种非常早期的 GMBA 类的研究中学到什么的话，其核心思想就是我们真正希望把大部分的随机性捕捉在潜在表征中，然后给定 Z 的 X 应该类似于确定性的，所以，是的。

<details><summary>Original English</summary>
>> I
 I
 I
 love
 that
 example
 of
 basically

like
 studio
 quality
 or
 not
 in
 a
 way
 like

we
 don't
 have
 enough
 language
 to
 really

describe
 like
 like
 this
 kind
 of
 echoing

or
 like
 some
 kind
 of
 noise
 kind
 of

happening
 we
 just
 like
 don't
 have

precise
 enough
 and
 uh
 if
 you
 um
 you
 know

basically
 the
 reason
 that
 I
 think
 it's

quite
 important
 to
 have
 like
 relatively

information
 rich
 like
 kind
 of
 captioning

is
 that
 we
 kind
 of
 rely
 on
 the
 natural

language
 as
 a
 representation
 but
 if
 you

basically
 don't
 have
 enough
 uh

representation
 that
 basically
 means
 the

condition
 on
 the
 language
 the
 generation

is
 very
 multimodal
 and
 if
 you
 anything

can
 learn
 from
 the
 BAE
 kind
 of
 like
 you

know
 very
 old
 you
 know
 GMBA
 kind
 of

research
 the
 idea
 is
 we
 really
 want
 to

capture
 most
 of
 the
 stoasticity
 in
 the

later
 representation
 and
 then
 the
 the
 X

given
 the
 Z
 should
 be
 kind
 of
 like

deterministic
 so
 yeah
</details>

>> 是的，是的。嗯，那我希望在那些方面有更多进展，而且我确信你们正在做……

<details><summary>Original English</summary>
>> yeah
 yeah
 um
 well
 I
 hope
 I
 hope
 there's

more
 uh
 progress
 there
 and
 I'm
 sure
 you

guys
 are
 doing
</details>

### 面部微表情与真实感

>> 我甚至觉得面部表情也是这样，对吧？也许这正好触及了你所说的我们非常敏感的事情，对吧？我认为你通过人们的面部表情也能辨别出很多 AI 内容……紧张。

[笑声]

<details><summary>Original English</summary>
>> I
 even
 actually
 like
 facial
 expressions

right
 and
 maybe
 this
 gets
 to
 your
 point

about
 like
 things
 that
 we're
 very

sensitive
 to
 right
 I
 think
 you
 can
 tell

a
 lot
 of
 AI
 content
 also
 just
 by
 from

like
 people's
 facial
 expressions

stressful.

[laughter]
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 是的。我们尽量不去增加这种情况，但你知道，嗯，或者比如皮肤纹理，对吧？就像现实生活中让事物看起来真实的东西。比如，你知道，我可以从你点头的方式，或者从你微表情的变化方式看出你对我所说内容的反应。我们好像还没有完全跨越那道鸿沟。我认为我们比一年前进步了太多。

<details><summary>Original English</summary>
>> Yes.
 And
 we
 try
 not
 to
 contribute
 to
 it,

but
 you
 know,
 um
 and
 or
 or
 like
 skin

textures,
 right?
 Like
 like
 the
 things

that
 kind
 of
 make
 things
 look
 real
 in

real
 life.
 Like
 I
 you
 know,
 I
 can
 tell

from
 the
 way
 you're
 nodding
 or
 from
 the

way
 like
 your
 micro
 expressions
 are
 kind

of
 changing
 of
 like
 how
 you're
 reacting

to
 what
 I'm
 saying.
 Like
 we
 haven't

quite
 crossed
 that
 chasm.
 I
 think
 like

we're
 we're
 so
 much
 better
 than
 we
 were

a
 year
 ago.
</details>

>> 是的。嗯，但是在人类极其敏感的很多这类事情上，还有很大的提升空间。而且我认为图像可以说是已经达到了那个水平，因为我看到了很多确实看起来与现实难辨真伪的图像，我都分不清它们到底是不是生成的。

<details><summary>Original English</summary>
>> Yeah.
 Um,
 but
 there's
 so
 much
 more

headroom
 kind
 of
 in
 a
 lot
 of
 those

things
 that
 like
 we
 as
 humans
 are
 super

sensitive
 to.
 And
 like
 I
 think
 image

arguably
 probably
 is
 there
 because

there's
 there's
 a
 lot
 of
 kind
 of
 images

that
 I
 will
 see
 that
 like
 really
 do
 look

indistinguishable
 from
 reality
 and
 I

can't
 tell
 if
 they're
 generated
 or
 not.
</details>

>> 比现实更好。

<details><summary>Original English</summary>
>> Better
 than
 reality
</details>

>> 嗯，或者说那是另一……

<details><summary>Original English</summary>
>> um
 or
 well
 that's
 a
 different
</details>

>> 不，我觉得那是其中一个悖……

[笑声] 比我在度假时拍的照片还要好。是的。我们团队不久前做过的一个有趣的实验就是，我们能不能生成比真实视频更好的视频，对吧？所以你直接采用某个视频的相同提示词，然后……

<details><summary>Original English</summary>
>> No,
 I
 I
 think
 that
 one
 of
 the
 parad

[laughter]
 better
 than
 what
 I
 would
 take

on
 my
 vacation
 as
 a
 photo.
 Yes.
 One
 of

the
 one
 of the
 fun
 experiments
 that
 we

did
 a
 while
 ago
 in
 the
 team
 is
 is
 like

can
 we
 generate
 videos
 that
 are
 better

than
 than
 real
 videos,
 right?
 So
 you

just
 take
 the
 same
 caption
 from
 like
 oh

yeah
 some
 video
 and
 then
</details>

>> 循环利用它。是的。就是试着去描述一段真实视频，然后用 omni 生成对应的版本，接着进行人工评估。结果怎么样？结果如何？然后人类在很大程度上更偏好 AI 生成的……

<details><summary>Original English</summary>
>> recycle
 it.
 Yeah.
 Just
 just
 try
 to
 like

describe
 a
 real
 video
 and
 then
 generate

the
 equivalent
 version
 with
 omni
 and

then
 do
 a
 human
 eval.
 How
 does
 how
 does

it
 do?
 And
 then
 humans
 largely
 prefer
 AI

generated
</details>

>> 幅度。

<details><summary>Original English</summary>
>> margin.
</details>

>> 但因为那是……因为那是强化学习过程……

<details><summary>Original English</summary>
>> But
 because
 it's
 because
 it's
 the
 RL

process,
</details>

>> 那就是强化学习过程在起作用。

<details><summary>Original English</summary>
>> that's
 the
 RL
 process
 working.
</details>

>> 无论你怎么去合理解释它。这不一定是那个旧过程。就像我认为这只是……我并不是说这是一个好结果。我只是说我们的优化方式在某种程度上可能触发了人类大脑中的某些东西，让人觉得，噢，它看起来……很多视频看起来就是更好。比如我不是……是的，是的，是的。在细致审视、在更深层次的审视下，它们实际上不会更有用或怎么样，但如果你直接将随意的 YouTube 视频与……

<details><summary>Original English</summary>
>> It's
 however
 you
 want
 to
 rationalize
 it.

It's
 not
 necessarily
 the
 old
 process.

It's
 just
 like
 I
 think
 it's
 just
 I'm
 not

saying
 this
 is
 a
 good
 result.
 I'm
 just

saying
 is
 we
 have
 optimized
 in
 a
 way

that
 like
 kind
 of
 potentially
 sort
 of,

you
 know,
 triggers
 something
 in
 the

human
 brain
 that
 like,
 oh,
 it
 looks
 it

looks
 all
 a
 lot
 of
 the
 videos
 just
 look

better.
 Like
 I'm
 not
 Yeah.
 Yeah.
 Yeah.

on
 on
 inspection
 on
 on
 deeper
 inspection

they
 they
 would
 not
 actually
 be
 more

useful
 or
 whatever
 but
 like
 if
 you
 just

say
 side
 by
 side
 random
 YouTube
 video

versus
</details>

>> 它的生成版本放在一起对比，它看起来就是会更好，因为画面更锐利、更有 HDR 感，呃，肤色也更好；再说一次，它并不是更逼真……

<details><summary>Original English</summary>
>> generated
 version
 of
 it
 will
 you
 will

just
 have
 a
 it
 will
 just
 look
 better

because
 it's
 more
 it's
 a
 sharper
 more

HDR
 uh
 you
 know
 the
 skin
 tone
 is
 is
 is

better
 it's
 not
 again
 it's
 not
 more

realistic
</details>

>> 呃，它不一定能解决你的问题，但它看起来更好。

<details><summary>Original English</summary>
>> uh
 it
 doesn't
 solve
 your
 problem

necessarily
 but
 it
 it
 looks
 better
</details>

>> 我觉得这也取决于人的敏感度。我出生并成长在日本，我觉得我所了解的一点是，他们在某些方面极其极其敏感，比如你知道的，这就是为什么在建筑、美食这类东西上，他们拥有……

<details><summary>Original English</summary>
>> I
 I
 since
 also
 depend
 on
 the
 sensitivity

of
 the
 people.
 Uh
 I
 was
 born
 raised
 in

Japan
 and
 I
 think
 one
 thing
 I
 kind
 of

know
 is
 like
 they're
 extremely
 extremely

like
 sensitive
 about
 like
 you
 know

that's
 why
 you
 know
 like
 architecture

like
 food
 and
 stuff
 like
 they
 have.
</details>

>> 嗯，所以我跟那里的一位漫画艺术家聊过，他对生成式 AI 感到有些反感，他提到的一个细节就是眼神注视……

<details><summary>Original English</summary>
>> Um
 so
 I
 talked
 to
 like
 a
 mangar
 like

like
 artist
 there
 and
 he's
 like
 he's

kind
 of
 disgusted
 by
 like
 the
 generation

AI
 and
 one
 kind
 of
 thing
 he
 mentioned
 is

like
 the
 eye
 gaze
</details>

>> 眼神注视，那一点点细微的差异。

<details><summary>Original English</summary>
>> eye
 gaze
 that
 slight
 difference
</details>

>> 让……让他觉得有点诡异，觉得不自然。

<details><summary>Original English</summary>
>> makes
 me
 makes
 him
 kind
 of
 feel
 creepy

about
 like
 unnatural
</details>

>> 比如目光稍微偏了一点。

<details><summary>Original English</summary>
>> like
 if
 you're
 looking
 a
 little
 bit
 off.
</details>

>> 是的。就是……是的。就是它看起来太假了。是的。说到了点子上。所以我觉得这确实取决于敏感度，并且……

<details><summary>Original English</summary>
>> Yeah.
 It's
 just
 uh
 Yeah.
 just
 like
 uh
 it

looks
 too
 fake.
 Yeah.
 To
 the
 point.
 So

So
 I
 think
 it
 does
 depend
 on
 the

sensitivity
 and
</details>

>> 是的，是的。我只是想说，人类偏好并不是衡量你应该优化什么的特别可靠的晴雨表，如果你只是去问人们喜不喜欢这个，你得到的结果不一定是你想要的。

<details><summary>Original English</summary>
>> Yeah.
 Yeah.
 All
 I'm
 saying
 is
 like
 you

know
 human
 preferences
 are
 like
 a
 not

particularly
 like
 uh
 reliable
 barometer

of
 like
 what
 you
 should
 be
 optimizing

for
 like
 if
 you
 just
 ask
 people
 do
 you

like
 this
 or
 not
 you
 not
 necessarily
 get

what
 you
 wanted.
</details>

### 审美敏感度与提示词工程

>> 是的。让我稍微补充一点，四年前有一场关于提示词工程是否会消失的争论，我……你知道，一些非常有权势的人说它会消失，但我基本上表示它不应该消失，因为提示词工程——具体去明确指明那些细节——就像是当你受到 AI 控制时，你能够对输出进行某种控制的唯一途径。而能让你进行提示词工程的，正是那种敏感度。所以确实，也许现在 AI 可以做很多自动提示，并且能够生成足够好的东西，但如果真是那样，永远不要满足，永远不要满足于 AI 生成的内容，永远微调你的敏感度，并始终去针对差异进行提示。

我觉得这与普通人未经训练的眼睛也有很大区别——我自己就会把自己归入那类人，你知道，我有一些审美感知，而且我做这行的时间也足够长，所以我也有自己的偏好。嗯，但你看你举的漫画艺术家的例子，那是可能磨砺了几十年技艺的人。嗯，任何从事这项工作的人，无论是设计还是建筑，对吧？你就是拥有完全不同层次的专业知识，并且能看到普通人看不到的东西。但 Doom 说得对。就像如果我们去看……如果你在街上随便调查 10 个人，他们可能都会更喜欢那种过度平滑、非常饱和的感觉……

<details><summary>Original English</summary>
>> Yeah.
 Let
 let
 me
 just
 kind
 of
 add
 one

thing
 but
 like
 four
 years
 ago
 there
 was

a
 like
 debate
 that
 if
 the
 prompt

engineering
 is
 going
 to
 disappear
 and
 uh

my
 my
 like
 you
 know
 some
 very
 powerful

people
 say
 you
 know
 it's
 going
 to

disappear
 but
 I
 basically
 said
 like
 it

shouldn't
 because
 the
 prompt
 engineering

like
 sort
 of
 you
 know
 specifying
 that
 is

like
 the
 the
 only
 way
 you
 can
 sort
 of

control
 the
 output
 sort
 of
 you
 know
 when

you
 have
 like
 sort
 of
 control
 by
 the
 AI

and
 what
 allows
 you
 to
 prompt
 engineer

is
 really
 that
 sensitivity.
 So
 sure

maybe
 like
 right
 now
 the
 AI
 can
 do
 a
 lot

of
 autoprompting
 and
 that
 and
 it
 can

generate
 something
 that's
 sufficient
 but

uh
 if
 it's
 like
 that
 never
 be
 satisfied

like
 never
 be
 satisfied
 with
 the
 AI's

generated
 content
 always
 fine-tune
 your

sensitivity
 and
 always
 kind
 of
 keep

prompting
 the
 differences.
 I
 I
 think
 to

the
 there's
 also
 a
 big
 difference

between
 like
 the
 average
 human
 untrained

eye
 which
 I
 I
 would
 put
 myself
 in
 that

bucket
 you
 know
 like
 I
 have
 I
 have
 some

aesthetic
 sensibilities
 and
 I've
 done

this
 long
 enough
 that
 you
 know
 like
 I

have
 I
 have
 a
 preference
 um
 but
 you
 know

like
 your
 example
 of
 a
 manga
 artist
 like

that's
 somebody
 who
 has
 honed
 a
 craft

like
 over
 possibly
 many
 decades.
 Um,
 and

anybody
 who
 does
 that,
 whether
 it's
 like

design,
 architecture,
 right?
 Like
 you

you
 you
 just
 have
 a
 very
 different
 level

of
 like
 expertise
 and
 you
 see
 things

that
 like
 the
 average
 human
 will
 not

see.
 But
 Doom
 is
 right.
 Like
 when
 we

look
 at
 if
 you
 were
 to
 just,
 you
 know,

um,
 poll
 10
 people
 on
 the
 street,
 they

would
 probably
 prefer
 the
 like
 overly

smooth
 like
 very
 saturated
 kind
 of
</details>

>> 这叫做 Instagram 滤镜。

<details><summary>Original English</summary>
>> It's
 called
 the
 Instagram
 filter.
</details>

>> 就是这样。确实就是……是的。[笑声] 嗯，你知道，所以这里也有一点疑问：如果你不作指定，你的默认美学风格会是什么样？不过话说回 Shane 的观点，

<details><summary>Original English</summary>
>> It
 is.
 It
 is
 the
 Yeah.
 [laughter]
 Um,

and
 you
 know,
 and
 and
 so
 there's
 also
 a

little
 bit
 of
 a
 question
 of
 like
 what

does
 your
 default
 aesthetic
 look
 like
 if

you
 don't
 specify?
 But
 then
 to
 Shane's

point,
</details>

<!-- chunk 6/8 -->

我们一直在努力让这些模型在遵循指令方面表现得更好，这样当你希望引导它们得出不同的结果时，你就能做到——无论通过语言还是通过参考物，因为语言有时局限性太大了。嗯，所以这些模型在这方面不断进步，但它们在这上面还有大量工作要投入。你作为一名产品总监，是否会感到为全世界设定默认风格的压力？就像，我是说……[笑声]

<details><summary>Original English</summary>
one of the things we always try to get these models better at is instruction follow so that like when you want to get them to a different outcome like you should be able to whether that's through language or whether that's through references because language is sometimes too limiting. Um, and so like these models continue to get better at it but they so much at work. Do do you feel pressure as a as a product director to set the default for the world like I mean [laughter]
</details>

>> 算是吧。

<details><summary>Original English</summary>
>> kind of
</details>

>> 也许我应该感到压力，我不知道，我还没想过这个问题。

<details><summary>Original English</summary>
>> maybe I should I don't know I haven't thought about this
</details>

>> 你知道的，必须有人来定一个默认值，默认值总归是要存在的。

<details><summary>Original English</summary>
>> you know you know it's like someone has to have a default the default has to exist
</details>

>> 其实我想说，我们确实考虑过这个问题。嗯，而且我觉得其中有一点……例如，如果你看一下 nanobanana 的生成内容，当 nanobanana pro 发布时，nanobanana 信息图表简直出现了一次大爆发。

<details><summary>Original English</summary>
>> actually I will say like we have thought about this um and I I think one of the so for example actually like if you look at nanobanana generations we had like an explosion of nanobanana infographics when nanobanana pro came out
</details>

>> 我试过，是的。

<details><summary>Original English</summary>
>> I tried it yeah
</details>

>> 嗯，对。

<details><summary>Original English</summary>
>> um yeah
</details>

我觉得 NeurIPS 的论文好像全都是……你知道的，好多都生成了信息图表。你们能对其运行一下你们的水印检测，看看有多少篇吗？

<details><summary>Original English</summary>
I think Nurb's papers were like all you know so so many had like infographics generated. Can you run your uh watermarking on it and see how many
</details>

>> 呃，我们大概可以，我们还没那么做过。但我看到……我的 Twitter 上全都是，也许这也只是我算法的偏差，但它们真的无处不在。嗯，这其实挺让人痛苦的，因为我觉得我们的默认审美有点太……太杂乱了。我认为这个模型有点像个过分热心的学生，刚学到了东西，你知道的，就像“哦，我知道关于这个概念的所有这些信息，让我把它们全塞进同一张图片里”。日本的信息图表还要繁密 5 倍。[笑声]

<details><summary>Original English</summary>
>> uh we pro we probably could we have we haven't done that but I saw so like my Twitter was maybe this is just also like the bias of my algorithm but they were everywhere um and it was actually very painful because um I think our default aesthetic was a little bit too it was too cluttered like I think that the the model is like a bit of an overeager student that just like learned you know it was like oh I know all these like I know all this information about this concept let me like shove into the same image. Japanese infographics 5x that [laughter]
</details>

>> 或者也许是，你知道的……但它就是……而且……

<details><summary>Original English</summary>
>> or maybe it was you know um but it just and and
</details>

>> 等等，所以同样的提示词、同样的内容，如果是日语的话，它就会……

<details><summary>Original English</summary>
>> wait so same prompt same content if it's in Japanese it's
</details>

>> 密集，密集。

<details><summary>Original English</summary>
>> density density
</details>

>> 哦，哇。

<details><summary>Original English</summary>
>> oh wow
</details>

>> 因为在日本就是那种风格。

<details><summary>Original English</summary>
>> because that's the style in Japan
</details>

>> 对，某种非常……你知道的，官僚风，并且[笑声]对此还有一个专门的知名词汇，是的。

<details><summary>Original English</summary>
>> yeah some like very you know bureaucrat and [laughter] there's a famous word for it yeah
</details>

>> 不，但我们确实会经历这个过程。在 Omni 上，我们是一起经历的，对吧？就像在最后，我们做了一些微调，然后就像“好吧，我们更偏好哪种风格”，对吧？就像你所知道的……

<details><summary>Original English</summary>
>> no but we do do go through this process with Omni we did it together right like where like we had like a bunch of like we like at the very end okay like this is we did some tuning and like okay what kind of style do we prefer right like you know
</details>

>> 是更柔和一些，还是更饱和一些？

<details><summary>Original English</summary>
>> is it more muted more saturated
</details>

>> 我们的饱和度很高。

<details><summary>Original English</summary>
>> we had a lot of saturation
</details>

>> 是的，有……我觉得 Nicole 只是有了 PTSD 所以把它忘了，但她当时非常深入地参与了这件事，比如“好吧，我们基本上更偏好哪种调色板”，对吧？这并不是那种……你必须在其中做出权衡取舍，比如……

<details><summary>Original English</summary>
>> yeah there was there were I think Nicole just has PTSD so has forgotten about it but she was very much involved in this of like okay which which kind of color palette do we basically prefer right and it's you know it's it's it's not something that like you have to make a a trade-off there like uh
</details>

>> 而且……而且这是因为最终做决定的成了我们，对吧？实际上确实是这样，最终是由模型团队来决定的。你完全可以合理地提出质疑：我们是做这件事最合适的人选吗？还是说我们其实应该与那些真正具有创意视角、更像是艺术总监的人合作，并且有……我们在这点上有点反复权衡。嗯……

<details><summary>Original English</summary>
>> and and and it's because it ends up being us right like actually it is true like it it ends up being the modeling teams and you could ask the question legitimately of like are we the best people to do that or should we actually work with someone who like has a really creative point of view and is more of like you know an art director and like has like and we kind of go back and forth on this um
</details>

>> 我们有可信测试人员，我就是其中之一。

<details><summary>Original English</summary>
>> we have the trusted testers I'm on
</details>

>> 确实，我们有可信测试人员，他们给了我们很多反馈，我们对此非常认真对待。

<details><summary>Original English</summary>
>> we do we have trusted testers who give us a lot of feedback and we take that serious
</details>

>> 顺便说一句，组织得非常好，比如每周开例会之类的，非常棒。

<details><summary>Original English</summary>
>> very well organized by the way to have these like weekly calls and stuff like it's it's amazing
</details>

>> 嗯，Logan 的团队承担了其中很大一部分工作，所以要把赞誉送给 Logan，他今天没能来到现场。嗯，我们在 Google 内部其实也有很多人，比如 Fulfur，给了我们极其大量的……不，不，不，是真的，在发布新检查点时给了我们海量的反馈。有时会是我们没注意到的东西，对吧？我们可能会觉得“哦，这个优化看起来还行”，然后他们就会回过头来说“你们干了什么？你们把我的草坪彻底毁了，因为现在的细节全糊了”。

<details><summary>Original English</summary>
>> um Logan's team does a lot of that so kudo kuda kudos kudos to Logan um who couldn't be here today um and we have a lot of people actually internally at Google like Fulfur who give us like a ton of No, no, no. Truly like who give us a ton of feedback on like when we when we release new checkpoints and like sometimes it will be stuff that we like don't see right like we would be like oh yeah this optimization seems okay and then they would come back what have you done like you completely ruined my grass you know because now the detail is all blurry.
</details>

>> 我觉得他刚才注意到了——虽然现阶段这也不是什么超级机密了——我们的模型往往会在手上加上戒指、结婚戒指。这确实是，是的。

<details><summary>Original English</summary>
>> I think he just noticed not not a super secret at this point but like that our model tends to put rings wedding rings on on on hand. That's yeah
</details>

>> 非常奇怪。我以前从没注意到这一点，但他……他刚看到了，基本上就有一个人造毛皮频道。

<details><summary>Original English</summary>
>> very strange. I had never noticed that but he's like he I just saw it and there's a faux fur channel basically.
</details>

>> 呃，他发帖说，我当时心想“为什么每只手上都有结婚戒指？”我觉得那太奇怪了。

<details><summary>Original English</summary>
>> Uh he posted I was like why is there wedding ring in every hand? I'm like that's strange.
</details>

>> 这听起来是非常普遍的奖励作弊。

<details><summary>Original English</summary>
>> That sounds very common reward hacking.
</details>

>> 是的，是的，是的。所以……但你知道，这是我们在开发过程中未必会注意到的东西，对吧？是一个口头伪影，还是……

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. So but you know something that we would not have we would not have noticed necessarily while while developing this right is an oral artifact or
</details>

>> 我……我不知道，你们确实有大量基于偏好的机制，然后你知道，人类可能会偏好那种虚假关联，奖励作弊可能会以很多奇怪的方式发生。是的。

<details><summary>Original English</summary>
>> I I don't know you do have like a lot of preference based and then you know you may can prefer that sperious correlation reward hacking it can happen like in many weird ways. Yeah
</details>

>> 确实会，确实是。

<details><summary>Original English</summary>
>> it does. It is
</details>

### 视频评估与人工评测

>> 呃，这与另一个话题有关，我再次尝试把这些主舞台的内容作为引子或关联。呃，我们有评估专场，有 Character AI 和 YouTube 讨论他们如何评估视频。嗯，你们是如何评估视频的？

<details><summary>Original English</summary>
>> uh this was related to another topic that again I I try to use these mainstage things as introductions or ties in. Uh we have the eval track we have character AI and YouTube talking about how they evaluate videos. Um how do you evaluate videos
</details>

>> 除了 Fulfur 之外？[笑声]

<details><summary>Original English</summary>
>> apart from furer [laughter]
</details>

>> 并不是所有人都有一个 Fulfur，但同时，你知道，我认为需要有一些更量化的东西。

<details><summary>Original English</summary>
>> not everyone has a fauxur but also you know I think there needs to be something more quantitative
</details>

>> 嗯，我是说，你通过改进 Gemini 来改进视频的评估。嗯，那……不，不，那绝对是一种方法。呃，其实这非常困难。

<details><summary>Original English</summary>
>> well I mean it's you improve Gemini to improve the evaluation for video. Um that's that's no no that's that's definitely one way uh it's actually very hard.
</details>

>> 非常困难。让评测员去评估视频中的内容非常困难，尤其是像美感这样的东西，对吧？有些东西会相对客观一些，比如尤其当我们讨论图像，看一下信息图表的文本渲染，那其实还好，对吧？因为你可以用 OCR 把文字提取出来，然后看看“好吧，这个字母乱了”，那么整个素材其实就没用了，因为在渲染文本中如果确实错了一个字母，你就根本无法使用该素材。对吧。所以那些东西会更容易自动化打分一些。嗯，根据我们的发现，我们确实非常依赖人工去审视内容，所以我们确实做了大量的人工评估。我们做了大量的人工评估。

<details><summary>Original English</summary>
>> It's very hard. It's very hard um to get like you know audators to evaluate things in a video like including especially things like aesthetics right like that it's like there are some things that are a little bit more objective like especially when we talk like let's say we talk about images and we look at like infographics text rendering that's actually fine right because like you can kind of OCR things out and then you can look at like okay this letter is like messed up and then the whole thing is actually useless because if like literally if a letter is off in render text you just can't use that asset. Right. So th those things are like a little bit more auto ratable. Um from what we found we do rely a lot on humans looking at things and so we do do a lot of human evals. We do a lot of human evals.
</details>

>> 做大量的人工评估，而且每次 Jane 都像……嗯，而且每次我们有了新模型，我们都想做更多的事情，想塞进更多的能力，然后我们就必须运行更多的评测。嗯，到了某个阶段，你确实会遇到两个彼此非常接近的模型，然后我们真的就是根据并排对比输出来做决定。有时是在一个房间里，比如我待过的会议室里有我们大约 10 个人，我们就是并排看着视频，然后商量“你更喜欢这个还是更喜欢那个？”就像，哦，哇，这……

<details><summary>Original English</summary>
>> Do a lot of human ev and every time Jane is like um and every time we have a new model we like want to do more things and we want to like gem in more capabilities and then we have like more emails that we have to run. Um, and then at some point you do get two models that are like kind of close to each other and then like we literally make decisions based on like looking at outputs side by side. Sometimes like in a room like I've been in rooms where there's like 10 of us and we're just like looking at video side by side and we're like do you prefer this or do you prefer that? like oh wow it's
</details>

>> 我的意思是，但这确实极其复杂，你添加的能力越多……你知道，即使只是一项能力，但它就像几乎属于 AGI 完全型的能力，比如视频编辑，对吧？想想把视频编辑作为一个……以及带音频的编辑，还有……

<details><summary>Original English</summary>
>> I mean but it is it is genuinely very complicated the more capabilities you add like you know even just the one capability but it's like almost AGI complete capabilities like video editing right like think about video editing as a and like editing with audio and
</details>

>> 我的剪辑师听到这个会非常开心的。

<details><summary>Original English</summary>
>> my editor will be very happy to hear this
</details>

>> 编辑是生成式媒体中最难的问题。

<details><summary>Original English</summary>
>> edit the hardest problem in g media
</details>

>> 我不知道它是不是最难的，但它绝对名列其中，对吧？就评估的复杂性而言，自由形式的视频编辑是你可以做任何操作的，比如……

<details><summary>Original English</summary>
>> I mean I don't know if it's the hardest but it's definitely there right like uh in terms of like complexity of of evaluation like free form video editing is you can do anything like
</details>

>> 是的，呃，而且我在这上面花了很多钱，很难评判……

<details><summary>Original English</summary>
>> yes uh and like I I spent a lot of money on that and it's very hard to tell me
</details>

>> 比如添加那些，我们又没有一个“添加树懒”评估，对吧？我们……

<details><summary>Original English</summary>
>> like adding those we don't have like add a sloth eval right like uh that we
</details>

>> 那么，现在我们应该有了。

<details><summary>Original English</summary>
>> well now we should
</details>

>> 现在我们应该有了，对，对对。但类似这样的事情，要追踪它并不是那么容易。

<details><summary>Original English</summary>
>> now we should yeah yeah yeah but like things like that like it's it's it's not that easy to track
</details>

>> 我想我只是对你们的样本量感到惊讶，对吧？要测试你们模型的整个表面覆盖范围，你们依然依赖于数百这种量级？

<details><summary>Original English</summary>
>> I think I'm just surprised at the sample size that you have right like to to test the entire surface of your models you still rely on a magnitude of hundreds
</details>

>> 不，不不，我们做……是的，我们对数千项内容进行大量的人工评估。嗯，我认为还有诸如实时实验这样的因素，对吧？在更大的规模下，你也能从中获得关于某些更细微差异的信号。此外还有自动打分器，我认为在 LLM 领域这绝对是一个定义非常明确的范畴，而在多媒体模型中则处于更初期的阶段。有时候你仍然必须依赖人类的判断，我们确实依赖那些具有非常确立的审美风格的人的反馈，以及那些在日常工作流中使用这些模型的人的反馈，对吧？因为我们也可能……你可能拥有一个模型，它……

<details><summary>Original English</summary>
>> no no no so we do like yeah well we do we do a ton of human evals on like on like you know thousands of things. Um I I think there's also like an element of you know we can talk about things like live experiments right like which which is also where you get signal on like like some of these more minute differences at like much larger scale then there's auto raers which is definitely kind of a more it's a very well defined space I think for LLMs much more nent for media models and then like sometimes you still do rely on human judgment and we do rely on things like feedback from people who just like have a very owned like aesthetic and and people who just like use these models in their workflows dayto-day, right? Because we could also like you could have a model that
</details>

<!-- chunk 7/8 -->

### 早期测试与视频理解中的语义一致性

在人类评估的某些切片上确实表现很好，但随后它又确实会破坏某个人的工作流程。所以这就是为什么我们会做像早期访问计划这样的事情，并且我们尝试获取反馈，然后在更广泛地发布某些东西之前尝试将其整合进去。我觉得肖恩根据他的表情……

<details><summary>Original English</summary>
does really well on some slice of human evals, but then it like really breaks a workflow for somebody. And so this is why we do like early access programs and we try to get feedback and then we like try to incorporate it before we release something more broadly. I feel like Shane had a hot take based on his
</details>

>> 每次我们谈到这个时总会有这种表情。

<details><summary>Original English</summary>
>> expression always when we were talking about this
</details>

>> 各种各样的人类工作，你知道，都应该逐渐被摊销。然后有趣的是视频理解，尤其是像针对像AI生成……比如检测AI生成的内容是一个非常有趣的视觉任务。

<details><summary>Original English</summary>
>> every kind of human sort of you know work should be gradually kind of amortized and then the interesting thing is the video understanding especially like against like AI gener like detecting air stuff is extremely interesting uh visual task
</details>

>> 然后像其中的一些比如美学或这种视觉质量，但对于某些情况，比如语义上讲不通。例如，你从电影中截取一个著名场景，并尝试去构建它，然后如果你生成它，它可以在那里生成一些东西，但在某些时候，有些语义信息讲不通，比如它实际上是不一致的。那么AI真的能检测出这一点吗？所以当我评估AI视频时，就像是“哦，我觉得我太聪明了”，你知道，就像AI仍然有点落后，但我们应该付出很多努力。我认为视频理解是一项极其重要的智能任务，超越了单纯的美学或偏好。嗯，是的，我们应该始终努力去摊销人类……

<details><summary>Original English</summary>
>> and then like some of it kind of aesthetics or this kind of visual quality but for some of the kind of cases like semantically doesn't make sense for example you're taking like some like a famous scene from a movie and try to sort of um construct that and then if you kind of generate it uh it can generate something there but at some point some of the semantic information doesn't make sense like it's actually inconsistent. So can the AI actually detect that? So when I evaluate the AI videos like oh I feel I'm so smart you know like like AI is still kind of behind but we should make like a lot of effort. I think the video understanding is extremely uh important intelligence task uh beyond just the pure aesthetics or the preference. Um and yeah we we should always try to amatize the human
</details>

>> 人工标注。是的。

<details><summary>Original English</summary>
>> human label. Yeah.
</details>

### 数据需求与具身智能数据

>> 是的。嗯，你们需要什么数据？实际上很多和我聊过的人都想见到你们。呃，他们……我是说他们想友善地对待这件事。他们有大量的视频数据。他们有游戏数据。他们有现实世界的视频数据。他们有图像。他们有标注人员。你们想要什么？

<details><summary>Original English</summary>
>> Yeah. Um, what data do you need? A lot of people I talked to wanted to get in front of you actually. Uh, they I mean they want to be nice about it. They have a lot of video data. They have gaming data. They have real world video data. They have images. They have labelers. What do you want?
</details>

>> 你这是在提供提议吗？

<details><summary>Original English</summary>
>> Are you like offering?
</details>

>> 我只是在……这就是你们征集……好吧。好吧。我们收到……我相信你们收到了很多推介，对吧？你们遇到很多人想跟你们谈。什么才是……实际上我认为信号就是这个问题，从噪声中筛选出信号是主要问题，所以创建一个不错的API，比如“好吧，如果你真的做了A、B和C，我们对此感兴趣”……

<details><summary>Original English</summary>
>> I'm just like this is your request for like Okay. Okay. We get I'm sure you get a lot of pitches, right? You get a lot of people want to talk to you. what's like I think actually it's the signal is this problem this sorting out signal from noise is the main problem so creating a nice API of like okay if you actually do a b and c we are interested in that
</details>

>> 嗯，这里有个诱导性问题，所以我不知道是否有那种容易回答的……你知道，是不是做……我认为我们确实已经有了大量的数据。我认为这很难……

<details><summary>Original English</summary>
>> um loaded question there so uh I don't know that there's like an easy like you know did you do I think we we do already have a lot of data I think it's it's
</details>

>> 很难谈论这个。

<details><summary>Original English</summary>
>> hard to talk about this
</details>

>> 你知道，你想谈论公开的事情，我不想让你惹上麻烦。是的，

<details><summary>Original English</summary>
>> you know you want to talk about the public I don't want to get you in trouble Yeah,
</details>

>> 但我觉得……

<details><summary>Original English</summary>
>> but like I think
</details>

>> 不，不。我只是想说……很难在不……你知道，在不试图……在不……我必须考虑我透露了关于我们项目的什么内容，以及我们要走向何方。嗯，通常是高质量的数据。我想也许……也许我们就这么说吧，对吧，这不是秘密……

<details><summary>Original English</summary>
>> No, no. What I just want to say is like hard to talk about this in a sort of you know without trying to without I have to think about the what I am revealing about our project and what where we're going. Um generally high quality data I think maybe maybe let's just put it this way right it's not not the secret
</details>

>> 具身，不好意思。

<details><summary>Original English</summary>
>> embodied I'm sorry
</details>

>> 具身数据。

<details><summary>Original English</summary>
>> embodied data
</details>

>> 我是说……

<details><summary>Original English</summary>
>> I mean
</details>

>> 是的，当然。我是说我们已经在某种程度上公开宣布过了，对吧，我们有某种机器人合作，对吧，就像……所以我认为这就像……或者……但是，因为我们在GDM有一个机器人团队，所以你知道，他们总是对这类事情感兴趣。嗯，我是说具体对于Omni，我认为我们只是对高质量数据很感兴趣，对吧，比如你知道，它不是某种……不一定是像，哦，随意的YouTube视频，而是你知道，一些专业拍摄的内容，诸如此类的东西，对吧。那些东西正是我们一直在寻找的，比如……呃，是的。

<details><summary>Original English</summary>
>> yeah sure I mean we have sort of announced I think publicly right that we we have some sort of robotics collaboration right like so I think it's like a like or or but you because we have a robotics team at GDM so you know they're always interested in things like that um I mean for Omni specifically I think we're just quite interested just high quality data right like you know it it's not some sort of not necessarily like oh random YouTube video but like you know some a some more professional shop things like that right the things that those are those are things that we're always on the lookout for like uh and yeah
</details>

### Agent工作流与隐性知识

>> 而且我认为，你知道，也许在某种程度上这对于一些Agent工作也更容易回答，比如人们试图去做的实际任务到底是什么，对吧？如果你自己做，或者如果你和供应商一起做，这些事情实际上是很难制造出来的。比如实际的……比如如果你正在创建一场营销活动，那会是什么样子的，对吧？比如，你是否从“这是我的新产品的图片”开始，然后我想把它变成视频广告，并且我想把它变成一堆适配所有这些不同广告格式的资产，我需要把它们推送到各种平台上进行推广，然后你就像是从这个走向那个，你在沿途经历的那种任务轨迹到底是什么样子的？像那样的东西真的很有用，而且实际上有点难以获取，对吧？因为我们并不总是拥有合适的第一方界面让人们实际在上面做其中的一些事情，或者你可能与某个供应商合作，但他们也没有那个产品界面，对吧？大量这类信息存在于人们执行这些任务的场所，所以这有点难以获取。如果有人弄明白了这一点，你应该联系我们。

<details><summary>Original English</summary>
>> and I think for you know maybe this is easier to some extent to answer for like some of the agentic work as well like like like actual kind of like what are the tests that people are trying to do right these things are actually kind of difficult to manufacture if you're doing it yourself or if you're like doing it with a vendor, like what is the actual like if you're creating a marketing campaign, like what does that look like, right? Like do do you start from here's like a picture of my new product and then I want to turn that into a video ad and I want to turn that into a bunch of assets that like fit fit all these different ad formats that I need to push onto various platforms to promote and then like so you kind of go from this to that and like what is that kind of trajectory of tasks that you're that you're like you know experiencing along the way like that is really useful and that is actually kind of difficult to get right u because like we don't always have the right firstparty surface where people are actually doing some of these things or like you might work with someone who's a vendor but they don't also don't have that product surface right like like a lot of this kind of information lives in the places where people are doing these tasks and so that's kind of difficult to get like if anyone's figured that out you should reach out to us
</details>

>> 每一个思维通道，是的，每一个……［笑声］思维。

<details><summary>Original English</summary>
>> every channel of thought yeah every [laughter] thought
</details>

>> 每一个想法，是的。也许还有中国实验室正在使用的数据。

<details><summary>Original English</summary>
>> every thought yeah and maybe the data the Chinese lab is using
</details>

>> 是的，是的。呃，你知道，我自己作为一个媒体人，对吧？有那么多的播客创作者和市场部门的人，以及所有这些人，他们很乐意成为你们的数据，你知道，就像在我头上戴上一个脑机接口……

<details><summary>Original English</summary>
>> yes yeah uh you know as a media person myself, right? Like there's so many podcasters and people in in marketing departments and all these like they would happy to be your data like you know just like put a BCI on my head
</details>

>> 然后播客……［笑声］看我做的东西。呃，因为你知道，就是有做不完的工作，有这么多的工作，而这都需要在某种程度上成为大宗商品。显然你可以成为一个艺术……像工匠一样，在极高质量的内容上你可以成为好莱坞，但实际上很多工作是大宗商品，并且应该能够被模型化，我们希望你们去做……

<details><summary>Original English</summary>
>> and podcast [laughter] watch my things uh because like you know there's just endless amount of work to do like there's so much work and this is all like this needs to somewhat be commodity like obviously you can be an art like an artisan like you can be Hollywood for like the really high quality stuff but actually a lot of work is commodity and like should be modelable and we want you to do
</details>

>> ［笑声］

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 而且，但正如德米斯所指出的，我们确实需要高质量的内容，对吧，我们确实需要高质量的。

<details><summary>Original English</summary>
>> And but we we want the high quality to Demi's point right like we do want we want the high quality.
</details>

>> 我们需要大宗商品。是的。是的，是的。你们两方面都想要。

<details><summary>Original English</summary>
>> We want commodity. Yeah. Yes. Yes. You want on both sides.
</details>

>> 嗯，我……我只是……

<details><summary>Original English</summary>
>> Um I I just
</details>

>> 感谢你的拉拢推销。［笑声］

<details><summary>Original English</summary>
>> Thank you for the solicitation. [laughter]
</details>

>> 呃，你知道，我们也……我也增加了一个数据质量赛道。我认为人们想了解比如在AI领域如何提高门槛，对吧？很大程度上就是教育市场，教育研究人员、工程师和创始人，告诉他们“这是我们要走的方向”，很多就是“别再做那个了，做这个，改做这个”，而且我觉得人们会听的。

<details><summary>Original English</summary>
>> Uh I you know we we we also I also added a data quality track. I I think that uh people want to understand like what uh at AI like how to raise the bar, right? like like the and a lot of it is just educating the market and educating researchers and engineers and founders on like this is where we're going a lot of this is stop doing that do this do this instead and I'm like people will listen
</details>

>> 是的，我不知道……呃，到那种程度，你知道。

<details><summary>Original English</summary>
>> yeah I don't know uh to that extent you know
</details>

>> 但我认为就这一点而言，这里面同样投入了大量的技巧，对吧？并且有很多过程。就像即使以营销活动为例，你并不是在五分钟内就创造出来的，对吧？你经历了一个过程，你在不断迭代，你选择某样东西而不是另一样东西是因为出于某种原因你喜欢它，比如也许视线方向是正确的，对吧？我们只是不知道这些事情，对吧，因为我们中没有人是市场总监，而且模型也不知道这些事情。

<details><summary>Original English</summary>
>> but I think to that to that point like there's a lot of again just like craft that goes into this right and there's a lot of process like you even to the marketing campaign example you don't create that in like five minutes right you like go you go through a process and you iterate and you like pick something over something else because you liked it for whatever reason like maybe the eye gaze was correct right like we just we don't know these things right because none of us are marketing directors and like the models don't know these things
</details>

>> 我甚至对自然语言也是这么说的，我总是说99%的信息都在人的内心深处，你只能通过主动对话和与他们交朋友来提取它。所以互联网上的大部分东西有点像是那样的结果、产物，是的，但是你知道，所有的轨迹是什么？你知道，这个人是如何获得写这篇论文的灵感的？

<details><summary>Original English</summary>
>> I even kind of say this for the natural like a language as well like I I always kind of say 99% of information is inside people you can only extract it through active dialogue and befriending them so most of the stuff on the internet is like sort of the outcome the output of that yes but you know what are what are all the trajectories you know how did this person have this inspiration to write this paper
</details>

>> 起点是什么？灵感是什么？引发它的对话是什么？这类东西都在人的内心深处。所以甚至在语言领域也是那样，我认为创作领域也有些类似，有大量的暗知识。

<details><summary>Original English</summary>
>> what is the starting point what is the inspiration what are the dialogue that sparked it those kind of stuff is kind of inside people so even you know those kind of like even the language space is kind of that I think the creative is kind of similar as well there's a lot of dark knowledge
</details>

>> 是的，就像你写小说一样，对吧？一本小说能打动你，是因为你通常会对故事、轨迹或角色产生某种个人共鸣，对吧？如果你读过当今大语言模型写的大多数东西，它开始陷入这些默认的模式，语言开始变得非常相似，所有的描述听起来都非常相似。你可以很快读出来并觉得“哦，这没什么意思，因为我无法产生共鸣”，对吧？嗯，再次说明，那有点像是一种人类的专业知识。

<details><summary>Original English</summary>
>> yeah it's like when you write a novel right like a novel speaks to you because like usually there's some sort of like a personal connection that you feel to like the story or the trajectory or the characters right like if you read most of the stuff that's written by LLM's today like it's, you know, it's it's it starts it falls into these like default par patterns and like the language starts to feel really similar and all the descriptions sound really similar. You can kind of like quickly read it as like, oh, this is not that interesting because like I can't connect to it, right? Um, and again, that's that's kind of like a human expertise.
</details>

>> 最近有一件好事是Google Cloud和Google DeepMind有点……

<details><summary>Original English</summary>
>> One nice thing recently is the Google Cloud and the Google Deep Mind are kind
</details>

<!-- chunk 8/8 -->

### 前向部署工程师（FDE）与下游真实用例反馈

开始针对产品工程师投入更多的 FDE（前向部署工程师）。而且我也看到在创意、比如生成式媒体（GenMedia）领域也有一些招聘。所以我觉得这些确实是关键的投入方向，因为我们觉得光靠大量公开数据能做的事情是有局限的，但真正通过这样的合作，我们能够提供更好的模型和产品，而且也能获得反馈。

<details><summary>Original English</summary>
of starting to invest a lot more in the FTEEs for the product engineers. And I also kind of saw some uh recruiting for the creative you know gem media kind of space as well. So I think those are kind of really the effort because we we kind of feel that you know what we can kind of do with a lot of public data there's limits but really you know partnering with that we can provide kind of better models and products and yeah we kind of feedback
</details>

>> 我们这里也首次设立了 FDE 序列，每个实验室都在宣布这个。这真的很疯狂。我非常想做的一件事——而且我在 Cognition 也是这么推动的——就是不仅把 FDE 当作销售和解决方案团队，还要让他们成为评估（evals）、也就是评估人员。

<details><summary>Original English</summary>
>> uh we have an FD track here for the first time every lab is announcing it. It's it's crazy. Um, one thing I'm actually very keen on doing and I push I push for this at Cognition as well is to turn the FDES not just into sales and solutions but also to EVAL's uh eval workers.
</details>

>> FDE 不是销售，FDE 的范畴远比那大得多。那你是怎么定义 FDE 的？因为［笑］我确实把它看作销售，比如你越是为客户定制解决方案……

<details><summary>Original English</summary>
>> FD is not the sales FD is way way bigger than that. How do you frame FDs then? Because [laughter] I do think about it as sales like you're you know the more the more you customize the solution for
</details>

>> 我把后训练（post-training）定义为预训练到最终用户体验之间的任何环节，任何环节都是后训练。

<details><summary>Original English</summary>
>> so I define post training as anything between the pre-training and the final user experience anything anything is a post training
</details>

>> 对我来说，当我最初了解很多关于……我的意思是，FDE 大概最初是源于像 Palantir 那样的模式，所以历史沿革可能有所不同。但我认为核心确实在于，不仅要和他们一起工作并确保他们知道如何使用，而且还要提炼出基本上能对双方都有帮助的洞察。他们可以在使用模型的方式上加入很多 harness（测试与运行框架），而我们则可以在极其上游的层面进行改进。所以如何把客户的反馈传导到模型构建中，我觉得这更像是我希望 FDE 承担的角色。是的。

<details><summary>Original English</summary>
>> and to me when I first sort of you know learned a lot about I mean FD kind of I guess originally you know came from like path here and then that so I guess the kind of history is different but yeah I think the key is really that um you know the key is like not only to kind of work uh with them and ensure that they kind of know how to but also to sort of code like derive kind of insights that can basically kind of help both parties. They can put the like a lot of harness how they use the model. We can improve like very upstream. So how to get the customer feedback to the modeling I feel is the kind of more the the role I I kind of want for the fds. Yeah.
</details>

>> 是的。是的。甚至就此而言，抱歉插一句，比如如果你想和我们或者至少和我交流——我不会随便替你答应时间——但对我们来说，能够真正去和正在使用我们模型的人交流，去了解他们在哪些地方遇到了困难，这真的非常有帮助。因为再次说明，这就是你实际尝试去使用它们解决的现实世界任务，对吧？比如我会去和那些用我们的一些图像模型做室内设计的人交流，他们会说：“嘿，我真的很想采用这个图案，但我想要把它缩放到大概 10 种不同尺寸的地毯上，有时我会有非常定制化的地毯尺寸，然后模型就无法以同样的方式复刻出这个图案”；或者，“我想给这些耳环做试戴，而耳环有特定的大小，我的头也有特定的大小，如果你真的要试戴东西，这就必须合乎常理”，而模型在诸如此类现实世界中实际会发生的许多事情上往往会表现不佳，对吧？所以这对我们很有用，因为其中有些事情我们并没有想到，因为我们不会把模型用在那些任务上。

<details><summary>Original English</summary>
>> Yeah. Yeah. and and even for sorry just on that like if you want to talk to us or at least me um I I'm not going to offer up your time um but I it's really helpful for us to actually talk to people who are using our models and like understand where they're struggling uh because again that just like it's it's the real world task that you're actually trying to use them for right like I will talk to people who do kind of interior inter interior design with some of our image models um you know and they will say hey like I really want to take this pattern pattern, but then I want to scale it across like 10 different ruck sizes and sometimes I have like a very custom ruck size and then the model fails at like replicating the pattern the same way or you know I want to do a try on for these earrings and then the earrings have a certain size and then like my head has a certain size like it has to make sense if you're actually trying to try things on and like the models kind of fail at a bunch of these things that like actually happen in the real world, right? Um and so that that's like useful for us because for some of these things like we don't think about because we don't you know we don't use the models for those tasks
</details>

>> 或者比如，我认为就像你提到的广告活动之类的，人们会有品牌语言之类的概念，这……

<details><summary>Original English</summary>
>> or like um you know I think to your point about ad campaigns or whatever like people have like notions of brand languages or whatever like which is
</details>

>> 是的。

<details><summary>Original English</summary>
>> yes
</details>

>> 就像一堆写着各种要求的图片或 PDF，这也是一个相当模棱两可的问题，比如什么是宜家的品牌语言？是蓝色和黄色吗？我是说，那并不是非常……

<details><summary>Original English</summary>
>> like a a bunch of images or PDFs saying things you know it's a pretty kind of you know ambiguous question as well what is the IKEA brand language you know is it is it blue and yellow I mean that's that's not a very like
</details>

>> 但比如到底是什么色调的蓝，对吧。

<details><summary>Original English</summary>
>> but like what shade of blue you know.
</details>

>> 是的。是的。是的。所以这里面有……而且品牌是相当具体的，他们确实在意究竟是哪种色调的蓝。它不应该只是随随便便的一种蓝和随随便便的一种黄。那样就不是宜家了，对吧？我只是随手举个例子。但这正是属于……这并不一定是我们开发前沿模型的必然使命范围，但我们从根本上确实想要打造出能让人用来解决具体任务的产品，而不仅仅是研究产物，对吧？所以我觉得去了解人们到底在意什么，是很有用的。

我相信很多人都非常感激你们的工作，而且还有很多事情可以做，单是过去哪怕短短几年里，你们就已经取得了如此大的进展，比如像 Nano、Banana、Veo 和 Omni，我不知道你们还在酝酿些什么，但我们非常兴奋。这就是那种……比如 Sora 关闭时我感到非常失望的事情之一，我认为对于生成式模型，需要有更广泛的探索，而不仅仅局限于写代码。［笑］我认为那是……

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. So there there's like, you know, and the brands are pretty spec, you know, pretty, you know, like they they do care about the shade of blue. It's not shouldn't just be a random blue and a random yellow. That's not going to be IKEA, right? I'm just thinking about an example. But like this is the kind of stuff that, you know, it's not necessarily part of our like, you know, developing frontier models kind of, you know, necessarily mandate, but it's something that we do want to we do want to fundamentally like build products that people will use to solve concrete tasks, not just not just research artifacts, right? So I think it's useful to understand what people do care about. Uh well, I'm sure a lot of people are very grateful for your work and there's a lot more to do that you've made so much progress over the last like even just couple years of like Nano Banana and Theo and Omni and uh I don't know what else you got cooking but we're very excited like you this is one of those things where like I was very disappointed you know when Sora shut down and and I think like there needs to be more general exploration of uh you know generative models and not just you know coding. [laughter] I think I think that is
</details>

>> 我们显然喜欢写代码。

<details><summary>Original English</summary>
>> we obviously like this.
</details>

>> 我们热爱写代码。热爱写代码，而且……是的。非常感谢你们抽出时间。这真是一次由衷的愉快交流，我迫不及待地想看看接下来会呈现出什么样的新成果。

<details><summary>Original English</summary>
>> We love coding. Love coding and and uh yes uh but thank you so much for your time. Uh it's been a real pleasure and I can't wait to see what this looks like next.
</details>

>> 感谢邀请我们。非常棒的问题。

<details><summary>Original English</summary>
>> Thank you for having us. Great question.
</details>

>> 谢谢大家。［掌声］

<details><summary>Original English</summary>
>> Thank you everyone. [applause]
</details>