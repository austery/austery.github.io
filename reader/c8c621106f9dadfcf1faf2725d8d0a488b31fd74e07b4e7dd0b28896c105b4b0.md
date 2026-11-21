---
author: 硅谷101
date: '2026-07-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Xs_vDK0ETK8
speaker: 硅谷101
tags:
  - open-model
  - compute-bottleneck
  - geopolitics
  - research-exchange
  - ecosystem-integration
title: 中国开源模型生态、算力竞争与研究人员交流的深度洞察
summary: 文章探讨了当前中国在开源大模型领域的地位，重点分析了算力瓶颈、国产加速器的表现以及中美AI实验室和研究人员之间的差异。作者通过访问中国的顶尖AI机构（如清华大学、阿里巴巴等），分享了对本土生态的观察，强调了人才交流的重要性，并讨论了未来社会风险与地缘政治背景下的合作趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 播客引言与开场片段

**Nathan Lambert**: 谁拥有中国最好的开源模型？如果你拿枪指着我的头逼我回答，我会说，时至今日，中国实验室面临的最大劣势依然是算力。Meta 或 OpenAI 拥有的 GPU 数量，比所有这些中国公司的总和还要多。

<details>
<summary>Original English</summary>

**Nathan Lambert**: who has the best China open source model? If you put a gun to my head, I would say as of today, the biggest disadvantage that the Chinese labs still face today, yeah, it's compute. Meta or OpenAI have more GPUs than all of these like Chinese companies combined.

</details>

**Host**: 那么，像华为芯片这样的国产加速器究竟表现如何？

<details>
<summary>Original English</summary>

**Host**: So, how good are domestic accelerators such as Huawei chips?

</details>

**Nathan Lambert**: 所有那些公司都在想，如果你能给我华为芯片，我们或许就能获得更多客户。

<details>
<summary>Original English</summary>

**Nathan Lambert**: All of those companies are like, if you can give me Huawei chips, we will like maybe get more customers.

</details>

**Host**: Anthropic 的 CEO 达里奥·阿莫代（Dario Amodei）在短期内对开源权重模型带来的风险看法可能过于激进。你认为美国的 SOTA（最先进）模型领先中国模型多少个月？这个差距是会变小还是变大？……你好，内森，欢迎来到 Valley 101。

<details>
<summary>Original English</summary>

**Host**: Anthropomic CEO Daryl Amade, he's a little too aggressive in the near term about risks posed by openw weight models. How many months do you think US STA models are ahead of the Chinese models? And for that gap, is it going to become narrower or wider? Freeman semi analysis. Nathan. Hello, Nathan. Welcome to Valley 101.

</details>

**Nathan Lambert**: 嗨，感谢邀请。

<details>
<summary>Original English</summary>

**Nathan Lambert**: Hey, thanks for having me.

</details>

**Host**: 你刚从中国的一趟旅行回来，期间你实际上拜访了中国许多顶尖的 AI 实验室。多跟我们讲讲那次旅行吧。

<details>
<summary>Original English</summary>

**Host**: You just came back from a trip to China uh during which you actually visited many of China's leading AI labs. Tell us more about that trip.

</details>

### 中国之行的主要收获与感受

**Nathan Lambert**: 自从我回来以后，人们总是问我：“你最大的收获是什么？”我觉得 AI 领域的情况已经相当透明了，比如谁在构建什么模型之类的事情大家都知道。所以并没有那么多令人超级震惊的发现，不会让你觉得“哦，我有个惊人的独家观点”。对我这个报道这些模型的人来说，这趟旅行的意义在于结识那些正在做事的人，并去捕捉其中的细微差别：他们为什么要这样做？我觉得我个人今年真的学到了很多关于中国的知识。美国有很多人会主观臆断他们为什么要这么做，所以能获得第一手的视点，听到他们说“我们在这里，我们做这些是因为这些原因”，这种感觉非常好。

我预计未来会继续报道开源模型，而尝试这些模型是一个很有趣的生态系统，在这个生态里，美国这边有很大的利益诉求，很多公司正围绕着真正的开源模型智能栈进行构建，这为形形色色的人提供了价值，而同时有很多模型是在中国构建的，这些历史悠久的科技社区过去并没有太多交集和合作。传统上，在 Meta 和谷歌这样的公司有规定，如果你去中国旅行，你的笔记本电脑会被自动禁用（注：指严格的数据安全隔离措施）。所以过去一直存在一堵墙，人们无法轻易地合作，但现在他们正在逐渐走向融合。我对此非常感兴趣。在某些方面，这些模型能够如此具有竞争力确实让人惊讶，但当你了解到那里所有的人才和情况后，你又会觉得这在某种程度上是理所当然的。

就我个人而言，AI 让我充满动力的一大原因是，我认为在未来几年里会存在很多风险，特别是社会风险，比如人们如何获取信息，此外在地缘政治方面，这显然也是一个备受关注的话题。所以，在人们之间搭建桥梁，将真正在做这件事的人性化地展现出来，是非常有用的。因为他们并没有做出很多被贴上政治或极端标签的决策。建立这些联系真的很有帮助，因为这是一个共同的社区，正在朝着这些共同的目标前进，无论你称之为 AGI 还是别的什么目标。所以，能见到这些事情背后的人类，我非常高兴。

<details>
<summary>Original English</summary>

**Nathan Lambert**: People always ask me now that I've been back. It's like, "What are your big takeaways?" And I feel like AI is fairly well known and who is building models and things. So, there's not that many things that are like super shocking. You're like, "Oh, I have this hot take." The trip for me as somebody who covers these models, it's to get to know the people who are doing it and get to pick up on the nuance of why are they doing this? I think I'm personally just learning a lot about China this year. And there's a lot of people in the US that'll just like say why they might be doing this. And just to get the first person accounting of we're here, we're doing this for these reasons is very nice. 

I expect to keep covering open models in the future and trying these models is an interesting ecosystem that's set up that there's a lot of interest in the US and companies that are building around real open model intelligence stack which is serving value for all sorts of people and then a lot of the models are getting built in China and these historic tech communities like have not intermingled a lot and how they work. So there's traditional policies at places like Meta and Google where if you travel to China, your laptop automatically breaks itself. And there's like been a a wall where people can't easily work together, but they're becoming integrated. And I'm just very interested in it. I think it's surprising in some ways that these models are so competitive, but then when you learn more about all the talent there and things, it's like it becomes somewhat normalized. 

And I personally like a lot of the reason that I'm motivated by AI is that I would think that in the next couple years there's like a lot of risks particularly like just social risks and how people are informed and then also geopolitically it's obviously a topic of interest. So just building bridges across people and humanizing the people that are actually doing this because they don't make a lot of the decisions that are listed as political or extreme in any way and just like building these connections is really useful because it is one community that is kind of moving forward towards these various goals whether you call it AGI or whatever you want to say the goal is. So I'm just like very happy to meet the humans behind this.

</details>

**Host**: 是的。太棒了。那么你去了几天，去了哪些城市呢？

<details>
<summary>Original English</summary>

**Host**: Yeah. Great. And how many days did you go uh and which cities?

</details>

**Nathan Lambert**: 对。我想大概住了六七个晚上，主要是在北京和杭州。在北京待了大概三四个晚上，我们就住在奥林匹克中心附近。所以可以去“鸟巢”体育场这类地方跑跑步。那只是一开始找酒店落脚的地方，但随后发现大多数公司都在清华大学附近，那里有整整一个 AI 初创企业集群，这非常有趣。感觉很像湾区，你会觉得“哦，我只需在附近走走，就能穿梭于这个地区所有顶尖的 AI 公司之间”，你不需要跑很远。这非常有湾区的感觉。然后我们还去杭州待了几个晚上，那里是阿里巴巴的所在地。我想 DeepSeek 也在那里。我们没去 DeepSeek 的办公室，不过我们和一些人交流过，并且拜访了阿里巴巴，感觉非常棒。这是我第一次去中国，见到他们感觉很好。

<details>
<summary>Original English</summary>

**Nathan Lambert**: Yeah. So I think it was about six or seven nights and it was primarily in um Beijing in Hjo. So it was like three or four nights in Beijing which we were staying right near the Olympic center. So like go for a jog in this um the bird's nest stadium and all these things. It's just like where you find a hotel but then most of the companies are by Singwa University and there's this whole cluster of of AI startups there which is really interesting. It feels a lot like the Bay Area where you're like oh I can just walk between all the leading AI companies of the region and like you don't have to do anything. It's like a very Bay Area feeling. And then we also went to Hjo for a few nights, which is where Alibaba is. And I think Deep Seek is. We didn't go to the Deep Seek office. We talked to some people and we did visit Alibaba and it's just great. It's my first time in China and nice to see them.

</details>

### 拜访的 AI 实验室与公司概览

**Host**: 那么，这次你拜访了哪些实验室或公司？

<details>
<summary>Original English</summary>

**Host**: So, which labs or companies did you visit this time?

</details>

**Nathan Lambert**: 是的，我尽量把它们列出来。我们还拜访了一堆机器人公司，但我写作的重点并没有放在这上面。在语言模型方面，我们去了两个不同的阿里巴巴办公室。我一到北京下飞机，就直奔他们在北京的办公室去见了一些通义千问（Qwen）的团队成员。然后还见了阿里巴巴达摩院（或者 Kimi / Moonshot），还有智谱 AI（Zhipu）。接着，我和一起撰写 Interconnects 博客的 Florian 一起去了面壁智能（MiniCPM/Muan），他们也有语言模型方面的业务。我们还拜访了清华大学，去了北京的智源研究院（BAAI/Xiai）园区。之后我们去了杭州，拜访了阿里巴巴那边的园区、蚂蚁金服（Ant Group）团队，还有同样隶属于阿里的魔搭社区（ModelScope）。这次旅行很大程度上是作为一个团体组织的，核心是一群在 Substack 上写 AI 相关文章的人组建的，就像我朋友们创立了一个载体，用来做关于 AI 媒体和活动的有趣事情。所以活动主要围绕这个展开。团队的其他成员在上海那边，我想他们肯定交流了 MiniMax，也许还有阶跃星辰（StepFun）。所以，真的包含了很多知名的公司。我觉得大家都有明显的定位，比如 DeepSeek 是最神秘的一家，而字节跳动（ByteDance）也是，当你去拜访各家公司时，他们都会把 DeepSeek 说成是那种神秘的领先者；而谈到字节跳动时，大家就会觉得，哦，这是一家拥有海量资源、让大家都感到敬畏的封闭 AI 实验室，他们的豆包（Doubao）聊天机器人在市场上占据主导地位。当你身处那里时，你很快就能捕捉到这些信息，因为每个人都在谈论这些。

<details>
<summary>Original English</summary>

**Nathan Lambert**: Yeah, I'll try to list many of them. We visited also a bunch of robotics companies which I didn't focus on as much as writing but for language models we visited well I went to two different Alibaba offices. I got off the plane in Beijing and immediately went to meet some quen people in their Beijing office. So there's Alibaba Kimmy which is Moonshot as well Zai and then Florian who writes interconnects with me. We went to Muan which has their language modeling effort and then we also visited Singa University and we visited the Xiai campus in Beijing and then when we went to Hongjo we visited the Alibaba campus there the Antling team and also Model Scope which is also affiliated with Alibaba and then this was a group trip of part of mostly organized around this like sale which is a bunch of substackers that write about AI which is like my friends making a vehicle to do interesting things in AI media and events. So, it was mostly organized around this and then the rest of the group in Shanghai talked to I think definitely Minia Max and maybe Step Fun as well. So, there's really a lot of the names. I think there's obvious missions like Deepseek is the most secretive one and Bite Dance is also like you visit them and they're like all the companies talk about Deepseek as their like kind of mysterious leader and then Bite Dance is like oh the one closed AI lab that has a ton of resources that everybody's like worried about. the Dubau chatbot is the dominant thing. You pick up on these things pretty quickly when you're there because everybody talks about it.

</details>

### 中美生态差异与跨文化理解的谦卑

**Host**: 所以在你的 Substack 文章中，你说你是带着谦卑回来的。这是什么意思？

<details>
<summary>Original English</summary>

**Host**: So in your Substack article, you said you returned with humility. What does it mean?

</details>

**Nathan Lambert**: 是的。我觉得作为一个美国科学家，我其实从未指望过能对中国的科技生态系统或全球层面的中美互动发表什么高见。我当时的形容是，我知道自己懂得不多，而当我离开中国时，我的感觉是，我还有那么多东西要看。就好像我只是看了中国的这两座城市，而且是在一趟繁忙的商务旅行中，感觉就像被塞在面包车里四处穿梭。我们参加了一些很棒的晚宴，看到了北京一些可爱的小区和老建筑之类的东西，但给我的感觉是，我对中国还是知之甚少。要对某件事真正产生直接的直觉和洞察，你有点需要更接近“全栈”的知识体系，以及去体会“这里的人的第一反应会是什么？”、“一个中国研究员的直觉会是什么？”。而作为一个美国人，这可能需要我花一辈子的时间去完全理解。比如，教育体系有什么不同。我们去了清华，他们会谈到他们想要改变某种现状，他们会承认这样一种刻板印象，即中国研究人员在“从0到1”这种范式的科学研究上表现还不够好，虽然这也是个有点模糊的词汇。它到底意味着什么呢？但他们主动提起了这个，而这部分原因在于人才的培养方式，以及人才是如何通过不同层级，从一个比美国还要庞大得多的国内网络中筛选出来的。这些都是人们会谈论的事情，而能够亲眼看到它们真的很有用。今年我读了《Breakneck》和《Apple and China》，这是两本非常精彩的书，讲述了美国科技生态系统与中国的互动。但那仍然只是一种非常局限的视角。所以，这就是为什么我说，好吧，我离开的时候大概就有这种预感，我会觉得我离开时并没有真正理解一切，我依然觉得我还有更多需要学习的东西。

<details>
<summary>Original English</summary>

**Nathan Lambert**: Yeah. So I feel like as an American scientist, I never really expected to have anything to say about the Chinese tech ecosystem or US China interactions on the global level. I described it as like I knew I didn't know a lot and I left and I was like I still have so much to see. It's like I saw these two cities in China and I was on like a busy work trip and feeling like you get teleported around in a van. We went to some great dinners and we saw some cute neighborhoods in Beijing and some of the older buildings and stuff, but it's like I feel like I don't know so much about China. And to like truly have immediate instincts and intuitions about something, you kind of need some more closer to full stack knowledge and appreciation for like what would a person's instinct here be? like what would a Chinese researcher's instinct be? And it's like it's it would take a lifetime for me to fully understand that as an American. 

It's things like how is the education system difference. We went to like Shingua and they would talk about like we want to they would acknowledge the reputation where it's like Chinese researchers haven't been as good at this like 0ero to one style science which is kind of an arbitrary term. It's like what does that actually mean? But they would bring it up and part of this is in like how people are trained and how the talent gets funneled through different layers from a much broader domestic network than in the US. It's like these are things that people would talk about and actually seeing them is useful. This year I've read Breakneck and Apple and China is these two wonderful books on the US tech ecosystems interactions with China. But that's still like a very limited view. So that's why I'm like okay I kind of expected this when I left that I would be like I don't really understand everything I left but I still feel like I have more to learn.

</details>

**Host**: 呃，你们会见的是 C 级别的管理高层，还是中层的 AI 研究员或工程师？你认为这些对话真的有帮助吗？

<details>
<summary>Original English</summary>

**Host**: uh were you meeting with the sea level seway people or the middle level AI researcher or engineer level people do you think those conversation actually helpful?

</details>

**Nathan Lambert**: 是的，我们的目标是会见更多的研究人员，只是为了进行对话交流。我们也瞄准了尝试去接触管理层，特别是在初创公司。所以看起来主要是一开始在和研究人员谈论。我们和一些高管聊过……

<details>
<summary>Original English</summary>

**Nathan Lambert**: Yeah, so we were targeting meeting with more researchers just to get a dialogue. We also targeted trying to get leadership especially at startups. So it seems like mostly starting to talking to researchers. We talked to some executives say

</details>

<!-- chunk 2/12 -->

### 跨国企业文化与媒体应对

**Speaker A**: 像阿里巴巴（Alibaba）这样，或者我们交流过的其中一些人，他们在公司内部非常知名，并且直接与创始人对接。但我认为，当你要进行正式拜访时，很大程度上是为了向那里的人表达尊重。但归根结底，领导者受过更多的媒体培训，有时会告诉你更少的信息，这在某种程度上抑制了细节，以保持与公司官方口径一致。

<details>
<summary>Original English</summary>

**Speaker A**: like Alibaba or some of these people that we talk to are very well known within companies and interface directly with the founders. But I think that when you're going to do like a formal visit, it's a lot of showing respect to the people that are there. But at the end of the day, like the leaders are more media trained and sometimes will tell you less and it kind of suppresses nuance to stay on the company line.

</details>

**Speaker B**: 所以我认为两者兼而有之。我觉得大公司更愿意展示他们的一些资深云业务人员。是的。

<details>
<summary>Original English</summary>

**Speaker B**: So I think it was some of both. The bigger companies I think were more like open to show some of their senior cloud people. Yeah.

</details>

**Speaker A**: 在不透露太多信息的前提下。我觉得有些对话是私下的。我不知道。这可能不是最好的答案，但它是混合的。

<details>
<summary>Original English</summary>

**Speaker A**: Without saying like without giving too much away. I think some of the conversations were off the record. I don't know. It's not the best answer, but it's a mix.

</details>

**Speaker B**: 尤其是周围还有公关人员的时候，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Especially with the coms people around, right?

</details>

**Speaker A**: 是的。就像大部分时候房间里都有公关人员。有些最好的对话是，我宣布我来了。我们在微信上，我给人们发消息。然后你就像去和不在公司办公室的某个随机研究员喝珍珠奶茶（boba），你就会问：“你在研究什么？你在做什么？” 这样就没有那种掩饰感，比如“我在办公室，我的经理坐在我旁边，公关人员坐在我旁边。” 所以那些对话更有趣，但在这次旅行中也更罕见。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Like most of these have comms handlers in the room. Like some of the best conversations were I announce that I'm here. You're I'm on WeChat. I message people. And then you like go get boowo with a random researcher not on the corporate office and you're just like what are you working on like what are you doing and then it's like okay there's not the veneer of like I'm at the office my manager is sitting next to me the comm's people are sitting next to me so those are more fun but more rare of the trip

</details>

### 中国AI公司的务实主义

**Speaker B**: 绝对是。嗯，那你主要问他们什么样的问题？

<details>
<summary>Original English</summary>

**Speaker B**: definitely um so what kind of questions did you mostly ask them

</details>

**Speaker A**: 各式各样的问题都有。所以我想，我一开始比较感兴趣的是对他们来说可能相当好回答的问题，比如：你们为什么要发布这些模型？你们为什么要建立自己的模型？为什么不直接使用深度求索（DeepSeek）的模型？

很多这些公司都非常务实，他们觉得：“我们需要AI来服务我们的用户，我们希望拥有全栈技术，因此我们要自己构建。” 相比之下，在美国有一种作为前沿实验室的诱惑，这似乎仅限于少数精英，但他们并没有因为构建AI模型是一件极其昂贵、几乎不可能的事情而感到太多畏惧，在中国，这就像是所有公司都在做。这就是为什么我们想去拜访美团（Meituan）。它是我们最喜欢的拥有大模型的中国随机科技公司之一。所以我们就是去看看他们在做什么。

他们就说：“是的，我们需要这个来服务我们的智能体（agentic）产品。所以我们构建这个模型。我们的产品需要它。开不开源无所谓。我们也会发布它并获得一些反馈。” 他们对这种开放科学的理念非常务实。

这也会引出不同的话题，比如：你们目前的瓶颈是什么？这显然很快就会在算力上走向死胡同，或者……但他们很多人会说：“华为的芯片很适合推理。我们使用华为进行推理，但不太用于训练。” 很多人会说类似这样的话。在我们的团队中，人们也会想谈论：AI的未来是什么？比如：你认为它将如何影响劳动力市场和经济？你是否觉得作为一个科学家，你有责任去理解和思考这些影响？而在中国我们看到，研究人员不太倾向于在这些方面分享太多观点。

部分原因是企业环境，但我也认为这只是一个比他们受教育时被鼓励谈论的话题更结构化的环境，他们的教育往往是：“我把东西造出来。” 在中国，这种播客生态系统要少得多，在播客生态中，研究人员会因为抛头露面并试图影响公司的方向而受到奖励。他们有点更偏向务实，我认为有时在我的文章中，我会把它与谦逊重叠起来，然而，你可能是一个谦逊的人，但同时你也可能身处一个就是不习惯被问及某些问题的环境中。

<details>
<summary>Original English</summary>

**Speaker A**: there's a distribution so I think that I was interested in to start with something that's probably pretty accessible to them which is like why are you releasing these models like why do you build your model? Why don't you just use DeepSeek's model?

A lot of these companies are very practical and it's like we need AI to serve our users and we want to own the full stack and therefore we're going to build it. And they're much more daunted about building AI models being this like super expensive impossible thing where it's kind of an allure in the US of like being a frontier lab. It's like restricted to an elite few but it's like all the companies. That's why it was like we wanted to go visit Muan. It's one of our favorite like random Chinese tech companies to have big models. So are like just go see what they're doing.

They're like, "Yeah, we need this to serve our agentic products." So we build the model. We need it for products. It doesn't matter if it's open. We'll release it as well and get some feedback. And they're very practical about this open science sort of idea.

And this would lead into different things like what are your current bottlenecks which can obviously quickly be a dead end on compute or but a lot of them are like Huawei chips are good for inference. We use Huawei for inference but not really for training. Like a lot of people would say things like this also in our group people would want to talk about like what is the coming future of AI? So like what do you view on how it's going to impact labor markets and economics and like do you feel like you have a responsibility as a scientist to understand like think about these impacts and that's where we saw in China that researchers are much less inclined to share a lot of views on this.

Some of this is the corporate environment, but also I think it's just like a environment that's much more structured than what they're encouraged to talk about in in their education, which is like I build the thing and it's much less of this like podcast ecosystem in in China where there's researchers that are like rewarded for being visible and trying to sway the direction of the company. It's like a bit more practical-minded, which I think I sometimes in my writing got over overlapped with the humility, whereas like you can be a humble person, but also you could be in an environment where you're just not used to being asked certain questions.

</details>

### 各大AI公司的企业氛围

**Speaker B**: 酷。让我们谈谈你拜访过的一些公司。在你看来，它们彼此之间有多大的不同？我们先谈谈月之暗面（Moonshot）好吗？

<details>
<summary>Original English</summary>

**Speaker B**: Cool. Let's talk about some of the companies you visited. In your opinion, how different were they from one another? Let's talk about Moonshot first, shall we?

</details>

**Speaker A**: 好的。所以，我认为当你走进去的时候，确实能感觉到它们有非常独特的氛围。我认为Kimi（月之暗面）就是其中之一，这些人们看起来非常亲密，他们只是为了做一件很酷的事情的快感而参与其中，他们在做这件很酷的事情的同时建立了一项业务，但他们也只是想：“我们要构建这些模型。我们自己也用它们。” 他们保持着非常紧密的联系，当你去他们办公室时，你能直观地感受到这一点。你会觉得：“哇，这些人真的很团结，关系很铁，他们就是把生活都花在了一起构建这个东西上。”

我把Kimi描述为我们参观过的所有公司中氛围最好的一家，他们看起来很开心，走在自己的道路上，而且并不像一家大公司那么死板。如果你去阿里巴巴，那显然是一家庞大的科技公司，非常企业化。

蚂蚁集团（Ant Group）的团队也有点类似，因为他们也是一家庞大的科技公司。但即使是处于中间位置的一些公司，比如零一万物（Zai），也非常追求AGI（通用人工智能）。他们非常自豪，但至少在我们与他们的互动中，他们没有Kimi和Moonshot那种魅力。这可能只是因为我们在午餐时跟他们只见过几个小时的随机日常。你不能凭此就断定一家公司的发展轨迹。但这也很有趣，因为人们是善于表达的，你可以从中了解到一些东西。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So, I think they do have pretty distinct feelings when you could go into them. I think Kimmy was one where it's like these people seem so close and they're just in it for kind of the thrill of building a cool thing and they're building a business alongside building this cool thing, but they're also just like we're going to build these models. We use them ourselves and they stay very close in a way that's like you just pick up intuitively when you like go to the office. You're like, "Okay, these people are really bonded and they're tight and they're just like spend their lives together building this." 

I describe Kimmy as like the best vibes company of the one that we visited which is just like they seem like they're happy and they're going on their path and it's not very corporate in a way where if you go to obviously Alibaba it's like this is a huge tech company it's very corporate the ant group Antling team has some of that because they're also a huge tech company.

but even in some of the middle it's like Zai was very AGI forwards and they were like had a lot of pride but at least in the interactions we had it wasn't as much of this like charm that Kimmy and Moonshot have. And some of this might just be like random dayto-day like I've met these people for a few hours over lunch. You can't conclude a company's trajectory based off this. But it's also interesting because like people are expressive and you can learn things from that.

</details>

### 年轻的人才与开放的产学界限

**Speaker B**: 月之暗面有一篇名为《注意力残留》（Attention Residues）的论文，其中一位作者是一名17岁的高中生。你知道那个吗？我想那篇论文被埃隆·马斯克（Elon Musk）在X上转发，说这是Kim的令人印象深刻的工作。所以这个高中生现在在中国非常出名。那么这告诉你关于月之暗面的文化是什么？

<details>
<summary>Original English</summary>

**Speaker B**: There was a paper from Moonshot named attention residues with one of its authors being a 17-year-old high school student. You know about that one? I think that paper was reposted by Elon Musk on X saying impressive work from Kim. So this high school student got very famous in China now. So what does that tell you about the culture at uh Moonshot?

</details>

**Speaker A**: 这不像是月之暗面特有的事情，而是那里的人才非常年轻。这些公司都在努力扩大在西方媒体上的足迹，他们很多研究人员都在X上。我认识他们中的几个人。我认为，这些人是在公司里兼做产品和公关的。一个是Kimi的Crystal，还有零一万物的Lou。我见过Lou，不知道我的发音准不准确，但她大概20岁，还是个学生。她打招呼说：“嗨。”我当时就觉得，“哇。” 这些人太年轻了。然后我们遇到的一位Xiai（小米）的研究员Lee，他也还是个博士生，已经是那里的首席研究员之一了。

美国也有这样的人，他们非常有动力，最终进入了前沿实验室。但当你在中国一个接一个地遇到这些深度参与实验室的超级年轻的研究人员时，你会觉得这种现象太多了。感觉这有点像一种结构性的东西，他们吸收这些人才的速度比其他实验室快得多，并且对此也更开放。

<details>
<summary>Original English</summary>

**Speaker A**: It's like less of a Moonshot specific thing, but the this the talent there is very young. These companies are all on a push to have more of a western media footprint and there a lot of these researchers are on X and it's like I knew a few of the people. I think that it's like people that do a mix of product and comms at the company. One is like Crystal, I think at Kimmy, and then Lou at ZI. And it's like I met Lou, I don't know if I'm pronouncing her name exactly right, but she's like 20 and she's still a student. She's like, "Hi." I'm like, "Wow." It's like these people are so young. And then one of the Xiai researchers we met, um, Lee is like also a PhD student and like one of the lead researchers at Xiaomi. There are some people like this in the US which are just extremely motivated end up at a frontier lab. But it just seems like we're getting so many when you meet one after another in China of these super young researchers deeply embedded in this labs. It felt like a bit of a structural just they absorb this talent much more quickly than other labs and are more open about it.

</details>

**Speaker B**: 这太疯狂了。我的意思是，我已经三十出头了。我觉得这些人太年轻了。我觉得我在生活中还算年轻，看到这些真的很酷。但这跟美国不一样吗？

<details>
<summary>Original English</summary>

**Speaker B**: It's wild. I mean like I'm in my early 30s. I'm like these people are so young. It's like I feel young in my life and it's like it's cool to see. But is it different here in the US?

</details>

**Speaker A**: 我觉得是。就像我，我认为美国实验室里的年轻人才……

<details>
<summary>Original English</summary>

**Speaker A**: I think so. Like I I think it like young talents here in US labs.

</details>

**Speaker B**: 是的。所以，有些东西稍微定义了AI2（艾伦人工智能研究所）。它的秘诀在于，比如华盛顿大学（Udub）在你们背后。我们有很多博士生，他们是OLO和其他主要项目的核心人员，他们同时也是在读学生。但这种敞开大门的情况，至少在其他一些实验室就不那么顺畅了。比如我认识少数在实验室工作的博士生，但他们是美国绝对最顶尖的人才。而在中国，感觉学术界（特别是在像清华这样的地方）和附近这些初创公司之间的融合要刻意得多，人才的重叠度也高得多。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So something that defines AI2 a bit. It's like secret sauce is that like Udub is behind you. And we have a lot of PhD students that have been like core to OLO and core to other major projects who are concurrent students. But that sort of open door is at least like less fluid at some of the other labs. Like I know a handful of PhD students that work at labs, but these are like the absolute best of the best in the US. Where in China it feels like the intermingling of academia, especially at a place like Chinua and these startups nearby is much more intentional and much higher overlap for the talent.

</details>

**Speaker B**: 为什么这很重要？

<details>
<summary>Original English</summary>

**Speaker B**: Why does that matter?

</details>

**Speaker A**: 学生很年轻，他们渴望成功，他们生活中没有其他那么多事情。比如我想我今年要结婚了。要考虑家庭。我都30岁了。我还有其他事情。但学生们会想，“这是我生命中的技术。我就是要一直工作，吸收所有的背景知识。” 而且当你构建一个语言模型时，比如我在做后训练，你需要知道预训练团队在做什么。你需要……

<details>
<summary>Original English</summary>

**Speaker A**: Students are young, they're hungry, they have nothing else going much less going on in their life. Like I'm think I'm getting married this year. Think about family. Like I'm 30. I have other things. But students are like, "This is the technology of my life. I'm just going to work all the time and absorb all the context." And when you build a language model, like I work in post-training, you need to know what the pre-training team is doing. You need to

</details>

<!-- chunk 3/12 -->

### 技术认知与研发路径

**Guest**: ……了解你研发“菜谱”的多个阶段。然后你需要找出瓶颈在哪里，并去解决它。因此，你需要储备非常庞大的固定技术知识背景。我觉得这就好比，如果这是你生命中最重要的事情，并且你没有太多的干扰，把所有这些知识装进大脑就会容易得多。有位研究员告诉我们：“哦是的，新学生对于过去深度学习中哪些方法有效并没有先验经验。他们不会去寻找不同的架构之类的。他们只是想知道当前最先进的技术是什么，然后去改进它。”这是一种他们能做到的相对简单的方法。中国的一些研究人员也告诉了我们这一点，他们说：“是的，我们就是这么做的。”

<details>
<summary>Original English</summary>

**Guest**: know the multiple stages of your recipe. And then you need to figure out like what is the bottleneck and go address it. So there's a really big fixed context of technical knowledge that you need. And I think it's just like if it's the biggest thing in your life and you don't have a lot of distractions, it's just easier to put all this into your brain. One of the researchers told us like, oh yes, new students don't have priors for what used to work in deep learning. They're not looking at a different architecture or anything. They're just like, I want to know what the current state of the art is and make it better. And it's kind of like a simple approach that they can do. Some of the researchers in China told us this. They're like, yeah, we that's what we're doing.

</details>

### 中国 AI 公司的“展厅文化”与企业定位

**Host**: 我明白了，我明白了。我们来谈谈阶跃星辰（Jup）。那趟行程怎么样？

<details>
<summary>Original English</summary>

**Host**: I see. I see. Let's talk about Jup. How was the trip there?

</details>

**Guest**: 很有趣。我学到的一点是，中国公司有一种“展厅文化”。当有访客来时，你就会展示公司的历史。阶跃的展厅里每一块展板都展示着不同的 AGI 特性，比如“AGI 加载中”，或者他们的理念是“我们已经实现了 42% 的 AGI”——这是致敬《银河系漫游指南》的梗。你一眼就会注意到，感觉非常惊艳。但另一方面，我觉得我没有像了解 Kimi（月之暗面）的人那样深入了解他们。不过他们对自己的工作非常自豪，也取得了巨大的成功。我觉得这和他们是上市公司（或更受公众关注），并且被美国列入实体清单有关。他们瞬间就被推到了一个让人觉得“哇，这是一家真正的大公司”的地位，而 Kimi 还没有完全达到那种地位。

<details>
<summary>Original English</summary>

**Guest**: It was fun. I think you like so part of the thing that I learned is that Chinese companies have like a showroom culture where when you have visitors you like show the history of your company and JIP's showroom is all like every panel has some different like AGI feature so it's like AGI loading or it's like their thing is that ag we're like 42% of the way here which is from the Hitchhiker's Guide to the Galaxy reference and you just like immediately notice it you're like whoa and but at the other time there like I felt like it I didn't get to know them quite as much as the Kimmy people and but they're very proud of their work and they're they're very successful and I think it's some things of like being public and being randomly entity listed by the US. They're just like immediately vaulted to a wo you're like a real big company status type of thing that Kimmy hasn't quite hit that

</details>

**Guest**: 但在我看来，他们非常相似。当我审视这些模型时，它们有着不同的权衡取舍。如果 Kimi 保持私有化更长时间，而阶跃（JIPU）继续保持公开透明的状态，看看这是否会让他们的文化产生更多分化，将会非常有趣。

<details>
<summary>Original English</summary>

**Guest**: level of but in my mind they're so similar. is like when I look at the models, they have different tradeoffs and it'll be interesting to see if that kind of diverges the cultures a bit more if Kimmy stays private longer and JIPO is staying public

</details>

**Host**: 在二级市场上市可能有时候确实会有所不同，通常会获得更多的关注。

<details>
<summary>Original English</summary>

**Host**: being listed on the secondary market probably sometimes make a difference just normally get more attention.

</details>

**Guest**: 是的。所以阶跃和 MiniMax 现在都有公开的动作，这是好事，因为他们可以在短期内融资。但是，如果他们需要更多资金来训练模型呢？这就更难了，因为你很难进行第二次公开募股。目前的情况有点不明朗，而且眼下市场非常青睐任何走向公众的公司。所以投资需求非常大，但这种局面可能会发生转变。至少目前来看是好的。

<details>
<summary>Original English</summary>

**Guest**: Yeah. So JIPU and Miniax are public now and it's good because they can raise short term but it's like what if they need more capital to raise models? It's harder to do like you don't really do like a second public offering. It's kind of unclear and right now the markets are really rewarding any company that's public. So there's so much demand to invest in it but like that could turn. So like right now it's good.

</details>

**Guest**: 这种事情我说不好，我不做这些决定，但是……

<details>
<summary>Original English</summary>

**Guest**: I don't know. I don't make those decisions but

</details>

**Host**: 确实正反两面都能说得通。

<details>
<summary>Original English</summary>

**Host**: you can make arguments both ways.

</details>

### 开源模型与 API 市场动态

**Host**: 今年早些时候，在 OpenRouter 上，对 Kimi 和阶跃的 API 请求量出现激增，当时正好是开源热潮。你认为这种趋势会继续下去吗？

<details>
<summary>Original English</summary>

**Host**: Earlier this year there was a surge of API requests on open router for Kimmy as well as Japur uh during the open call sensation. Do you think that trend will continue?

</details>

**Guest**: 是的，我们看到出现了多个细分市场。有顶端的 Claude Code 和 Cursor（Codeex），我把它们描述为脑力劳动工具。

<details>
<summary>Original English</summary>

**Guest**: Yeah, we're seeing kind of multiple markets emerge. You have the cloud code and codeex which is like the top end. I describe it as like knowledge work tools,

</details>

**Guest**: 但从本质上讲，未来将会有适应不同工作场景和价格点的智能体。开源模型的优势在于，它们的价格非常低，使得尝试和实验变得更加可行。人们自然而然地会去使用这些已知性能强大且价格更低廉的模型进行实验。同时，这些模型又拥有成熟的品牌，这正是 DeepSeek、阶跃、Kimi、千问（Qwen）这一梯队所处的位置。我个人认为，OpenCog（OpenCaw）本身可能只是一时的热潮，但它所代表的这类智能体将会保留下来。比如现在 Hermes 智能体非常受欢迎，尽管它可能也会经历潮起潮落，被新的取代，但这类可以在 OpenRouter 上的托管模型中运行且成本不高的智能体，本身就非常有趣。

<details>
<summary>Original English</summary>

**Guest**: but essentially there's going to be agents at price points for wherever they work. The thing that makes open models nice is that the price point is so low that the experimentation is much more doable. It's kind of a natural place where a lot of people will experiment on these models that are known to be strong and a step down in price while still having these established brands which is where this whole Deep Sea Japu Kimmy Quen kind of circle lands. Personally, I think like OpenCaw itself is a bit of a a fad where the name but the type of agent it represents will be sticking. So like right now like Hermes agent is far more popular but it's like even this will like come and go and there will be another but it's just like this type of agent that you can run it and it is not super expensive on these like hosted models on open router is is interesting.

</details>

**Guest**: OpenRouter 本身在实际推理市场中所占的比例并不大。在美国，像 Fireworks 和 Together AI 的规模要大得多，他们都开始分享每天处理的 Token 数量。不过 OpenRouter 更偏向社区导向。因此，当你想到那些关注开源模型的人时，就会想到这里，这显然是一种优势。我认为各家公司也在积极利用这一点，因为当他们的模型在上面爆火时，这是一种很好的联合品牌效应，能形成自我强化的循环。

<details>
<summary>Original English</summary>

**Guest**: Open router itself is not a huge proportion of the actual inference market. So like in the US like fireworks and together are much bigger. They both started sharing some numbers on the amount of tokens they're doing every day. But open router is like more of like community oriented. So when you think about people that are following open models, it's like that's where they think and that obviously has an advantage and I think companies are very actively leaning into it because when their models surge on it, they use it's like good co-branding and it feeds into itself.

</details>

### 科技巨头的大模型战略差异

**Host**: 我们来聊聊你去美团和小米的行程吧。这很有趣，因为正如我们讨论过的，情况大不相同。在中国，这就好比 Uber 和苹果正在开发自己的开源模型，而即使在美国，他们也没有这么做。为什么中国会出现这种情况呢？

<details>
<summary>Original English</summary>

**Host**: And let's talk about your trip to Muan and Xiaomi. Yeah, it's uh interesting because as we discussed the story is very different. China, it's almost like Uber and Apple are developing their own open-source models, but even in the US, they are not. Why is this the case in China though?

</details>

**Guest**: 当你问美团时，如果了解美团和小米的企业立场，就会发现他们倾向于说：“我们会有被实际使用的智能体。”就美团而言，你可以把智能体想象成能帮用户打车或者点餐。它能做到这些。

<details>
<summary>Original English</summary>

**Guest**: When you ask Muan, when if you like Mtoan and Xiaomi's corporate position would be like we're going to have agents that are used, you could think of it in Mtoan like an agent could do something for a user to figure out the ride to request or thing to order. like it can do this.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Guest**: 而美国消费者的第一直觉是：“我直接去获取一个 API Key 就可以了。”

<details>
<summary>Original English</summary>

**Guest**: And the first instinct in the US consumer would be I'm just going to get an API key.

</details>

**Host**: 没错。

<details>
<summary>Original English</summary>

**Host**: Exactly.

</details>

**Guest**: 但在中国，大家普遍的想法是：“我们可以自己造，而且成本更低。我们有算力，有技术人才，为什么不自己试着建一个呢？”

<details>
<summary>Original English</summary>

**Guest**: But in China, it's very much like we can build this and it will be cheaper. Like we have compute, we have talent. Why don't we just try to build this?

</details>

**Guest**: 这不仅是美团，有几家公司都是这样，他们会说“我们来构建这些通用模型”。这不仅限于他们自己的使用，他们还可以发布通用模型，让更多人使用。然后他们通过微调，制作出专门的智能体和模型，供内部服务使用。美团就是一个很好的例子，他们不会发布这些专门的模型，但希望在自己的应用中使用。你也可以想象一下小米，它可以驱动汽车上的各项功能。我猜小米汽车就像特斯拉一样，与云端通信，拥有各种接口。虽然你不太清楚具体会是什么样，但 AI 肯定会与所有数字技术交织在一起。

<details>
<summary>Original English</summary>

**Guest**: And this isn't specific to Mtoan, but there's a few companies that are like, we build these general models. And that's not where like our use of them ends, but we can release the general model because more people will use it. And then what they do is they like fine-tune this to make specialized agents and specialized models which they use for their services internally. And Muan's a good example where it's like those specialized models they don't release but they hope to use them in their apps. And you can imagine this with Xiai where it's like it could power features in the car and I'm guessing like Xiai works like a Tesla or something where it communicates with the cloud and there's all these interfaces and you don't really know what this is be but AI is going to be intermingled with like all digital technologies.

</details>

**Host**: 是的，我认为小米是大厂试图包揽一切的另一个典型例子。它涉足大语言模型、机器人模型，还有机器人硬件。它真的是试图把每件事都揽下来自己做。

<details>
<summary>Original English</summary>

**Host**: Yeah, I think Xiaomi is another good example of big corp is trying to do everything. It is doing like LMS and robotics models, robotics hardwares. It is really like trying to do every single thing itself.

</details>

**Guest**: 是的，小米的模型也是非常新的。他们在 2025 年 4 月到 6 月之间发布了 7B 参数的初代 Mimo 模型，然后在 12 月推出了非常受欢迎的 FlashV2 模型，最近好像又发布了 2.5 版本。人们花了很长时间才意识到，这些新模型会不断涌现。看到一个全新的实验室从零开始建立，绝对令人惊讶。他们还从 DeepSeek 和零一万物等地方挖来了人才，比如我忘了名字的那位，好像叫 Fuji，还有 Lui 吧。是的。

<details>
<summary>Original English</summary>

**Guest**: Yeah, it's like Xiai's models are pretty new too. They released a like 7B, their original Mimo model in April to June of 2025 and then come December when they had their FlashV2 model which was very popular and then I think 2.5 was recently. It takes a long time for people to realize that these models are going to keep coming and like it's definitely surprising to see a new lab come from scratch and they hired I don't remember her first name but like Fuji from Deep Seek and Lui. Yeah.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Guest**: 他们似乎正稳步迈向中国顶尖模型构建者的行列。美国这边大部分人还是只停留在关注 DeepSeek、千问、Kimi 和智谱。有些人可能知道 MiniMax，有些可能不知道。

<details>
<summary>Original English</summary>

**Guest**: and they seem on track to be like one of the best model builders from China. People in the US are mostly still at like Deep Seek, um, Quen, yeah, Kimmy and Zai. Some know Minia Max, some probably don't.

</details>

**Guest**: 名单其实很长，但在参观过小米之后，我非常看好他们能继续前进。他们是非常务实的，自己做大模型对他们来说非常合理。他们过去已经完成了那么多不可思议的事情，构建一个 AI 模型似乎比他们造车和做其他硬件还要容易。

<details>
<summary>Original English</summary>

**Guest**: And it's like it's such a big list, but I expect having visited Xiai like I expect them to continue is like very nononsense. It makes sense for them to do this. They've done so many incredible things in the past. It's like building an AI model almost seems easier than building some of the cars and stuff that they have built.

</details>

**Host**: 我觉得美团也是一样，他们也投资了月之暗面最新的融资，这表明美团在 AI 上下注很大。中国公司似乎倾向于构建庞大的生态系统，他们喜欢超级应用，喜欢生态圈，喜欢从零开始什么都自己建。你觉得在 AI 时代，这是正确的道路吗？

<details>
<summary>Original English</summary>

**Host**: I think for Muan they also invested in Moonshot's latest fundraising which indicates Muan is betting big on AI. Chinese companies just tend to have this massive ecosystem. They love the super app. They love the ecosystem. They love to build everything from scratch themselves. Do you think that's the right approach to go during the AI era?

</details>

**Guest**: 尝试一下总是值得的。我认为 AI 因为极其资源密集，本质上就会有利于那些大公司，也就是那些能进入良性循环的公司：“我们有大量的资源。AI 让我们的产品变得更好。我们从中获得了更多的回报。我们可以继续投资。”这样的公司将大获全胜。我认为在美国，很明显可以看出谷歌正在取胜。OpenAI 和 Anthropic 也会发展得很好。显然，像英伟达这样处于这个正向反馈循环中的公司都会非常强大。接下来，看看这种模式在中国如何运作将会非常有趣。我觉得像蚂蚁……

<details>
<summary>Original English</summary>

**Guest**: It's worth to like try your hand at it. So I think AI because it's so resource intensive, it by its nature will benefit very large companies and companies that can get onto this flywheel of like we have a lot of resources. AI makes our products better. We get more returns on this. We can keep investing will win so much. I think in the US it's really obvious to see like Google is winning. Open AI and anthropic will be fine. Like Nvidia obviously like all these companies that are in this feedback loop are going to be so good. And then it's interesting to see how this works in China. And I think like ant

</details>

<!-- chunk 4/12 -->

### 大厂与初创生态的博弈

**Speaker A**：……在不断优化他们的模型，并且他们看到了自己的平台是如何扩张的。比如现在它正在向医疗健康领域扩展，他们经常谈论这一点，而且他们肯定也会在那里应用他们的模型。所以对他们来说，我认为这实际上非常合理。但如果你从一个西方观察者的角度来看，你可能会想，为什么“蚂蚁（Ant Group）”会做这个？那是因为他们没有意识到，当你使用支付宝这样的产品时，背后存在着多么庞大的服务场景。所以，我认为对于这些拥有极大用户覆盖面的公司来说，这确实是顺理成章的。

我担心的是这会压制一部分竞争。比如，像 Kimi 的月之暗面（Moonshot）或者智谱（Zhipu）这样规模较小的公司，如何在这个充斥着超级 App 的生态系统中找到自己的位置？我想，我忘了具体是哪家公司，但他们曾告诉过我们，他们构建了一个智能体（agent）来导航字节跳动（ByteDance）的某个应用，然后字节跳动就把他们封禁了，因为字节不允许他们拿走数据。这就是小型公司和大型公司之间正在显现的边界，或者说小公司正在努力寻找自己的利基市场。我觉得美团（Meituan）处于中间位置，从我的角度来看，我很难准确把握它在科技公司中的体量，也不知道它是否会被行业整合吞噬，或者在语言模型上的支出是否会成为难以承受的负担。这我确实不知道，但我对 AI 作为一项业务是相当看好的。所以我认为，这些早期入局的大多数公司都会活得不错，他们可以卖出大量的 Token，他们在售卖智能，而且未来对此会有巨大的需求。

<details>
<summary>Original English</summary>

**Speaker A**: ...ing their models and they see how their platform spreads like right now it's spreading into health and they talked about this a lot and they will surely also use their models there and it's like for them I think this actually makes a lot of sense but when you look at a western observer you're like why is antling a thing but they don't realize the like broad service area that exists when you're using this alipe thing. So it's like I I think for these companies with very large footprints it actually does make sense. I worry that it suppresses some of this competition. So it's like how did the smaller Kimmy's minaxes and ZIS like fit into this ecosystem where such big apps exist? I think like I forget which one of the companies, but they were telling us how they like built an agent to navigate one of Bite Dance's apps and then Bite Dance banned them because they couldn't take the data and it's like there there's interfaces emerging between the small and the bigger companies or the small companies are trying to find their niche and I feel like mto's in the middle where I don't have a good grasp from my perspective like how big of a tech company it is and is like is it going to get swallowed by consolidation or is the spend going to be too much on the language models where I don't really know, but I'm pretty bullish on AI as a business. So, I feel like most of these companies that are early are going to be okay and sell they sell a lot of tokens, they sell intelligence, and there's going to be a lot of demand for it.

</details>

**Speaker B**：你在文章中写道，中国公司拥有一种“技术所有权（technology ownership）”心态。你能稍微解释一下吗？

<details>
<summary>Original English</summary>

**Speaker B**: You wrote that Chinese companies have a technology ownership mentality. Can you explain that a little bit?

</details>

**Speaker A**：这和一些超级 App 的理念不谋而合。他们看到自己可以构建一些东西并将其优化，如果成功了，他们就会投入更多资金让它变得更高效，并且会根据自己的应用场景进行调整。这就是中国国内许多行业随着时间的推移，成长为世界上规模最大的行业之一的逻辑。这有点像：只要有可能，他们就更倾向于自己去构建（build），而不是去购买（buy），这样他们就能在某种程度上掌控长期的发展轨迹。

我觉得 Dan Wang 在《Break Neck》中说得很对，中国的资本主义竞争比美国还要激烈。因为他们考虑的是更长远的问题：什么能给他们带来最好的利润率？什么能让他们提供最好的产品并击败竞争对手？如果你依赖别人的服务，你是无法击败别人的。如果你身处一个极度竞争的环境，你就必须做到最好，而且必须全部自己来做。

所以这就是我为什么把它看作是一种“所有权心态”，而且在目前看来，这并不是一项不可能承担的预算。我会说，这些实验室为了研发这些模型，每年可能会花费 5 亿到几十亿美元，这是一笔巨款，但对他们来说并非遥不可及。如果模型能力的进步持续攀升，市场最终很可能会走向整合。因为模型能力就像是投资的对数函数（log of investment），虽然会有边际收益递减，但投入越多，模型就会越聪明。不过这是一个非常有趣的时期，我记得我采访蚂蚁（Ant Group）的 Richard 时，他说：“对，我们花了六个月的时间才建立起这个团队来研发这些大模型。”那是因为科技行业中已经储备了大量的人才，他们只需把团队调配过来做这件事即可。我们现在正处在这样一个阶段——我不知道他们还会这样持续多久，但至少目前，这像是一件充满乐趣的事情。

<details>
<summary>Original English</summary>

**Speaker A**: This goes to some of the like super app ideas and they just see that they can build things and make it better and if they succeed they'll put more money into it and keep making it more efficient and they'll tune it to their use cases and this like how the many domestic industries in China have grown over time to be some of the largest in the world. This is how it's kind of like they want to build rather than buy if at all possible so they can kind of own the long-term trajectory. It's like a very I think it's like Dan Wong of Break Neck said that like China's capitalism is more intense in the US cuz it's like they're thinking of even longer term of what gives them the best margins and the ability to provide products and beat competitors and like you don't beat somebody if you're relying on their service and if youre hyper competitive you have to do it all the best and do it all yourself. So that's why I think of it as like this ownership mentality of where it's not currently an impossible line item. I would say that they're probably spending 500 million to billions a year to make these models which is a substantial amount of money but not impossible for these labs. It seems likely that the market will consolidate eventually if progress on capabilities keeps going up. It's like capabilities is like log of investment where it's like you have diminishing returns but if you invest more get smarter. But it's an interesting time where it's like I remember I interviewed Richard from Mantling and he was like yeah it took us six months to set up this team to build these large models that's because there's all this talent in tech already and they just like move the teams to do this. We're in the phase of like I don't know how long they will keep doing it but for now it's like kind of a fun thing.

</details>

### 通义千问（Qwen）与开源策略

**Speaker B**：让我们聊聊你拜访过的其他一些公司吧。比如千问（Qwen）和阿里巴巴。这是一家大型企业，它和月之暗面（Moonshot）以及其他小型实验室是不同的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Let's talk about like some other of the companies you visited. So and Quinn and Alibaba um it's a big corp. It's different from one shot and other smaller labs right?

</details>

**Speaker A**：是的。我认为千问通过持续发布各种参数规模且性能惊艳的小模型，已经赢得了开源 AI 领域的民心。他们在 Llama 3 发布以及 Llama 热度衰退之前就在做这件事了，但恰好在 Llama 的迭代节点以及 Meta 暂停发布模型的同一时期，他们真正找准了自己的节奏。而且他们自己也清楚这一点。

当我们询问他们时，他们表示他们在思考开发者会使用什么，他们希望继续构建能让开发者广泛使用并赖以生存的模型。但是当你观察千问时会发现，他们有一段时间没有开源他们最大的模型了。比如 Qwen Plus 和 Qwen Max 一直是闭源的。这在很大程度上是阿里巴巴云计算基因的体现。就像在美国，你看到 Google Cloud 疯狂的支出和同样疯狂的收益一样。在中国，阿里巴巴作为默认的云巨头，也会发生同样的事情，他们对此心知肚明。

所以，他们不会开源最大的模型。他们可能会告诉我们，不开源是因为没有人会去用它。但我会想，别闹了，这上面能赚大钱，而且我认为 AI 领域确实潜藏着巨大的商业利益。不过最有趣的是，听到不同的人谈论他们对这些小模型的发布是有意为之的，绝非偶然。也许一开始是无心插柳，或者只是想“我们也来试试别人在做的这件事吧”，但现在他们已经有了一套非常成熟的配方，打造出了这些非常受欢迎的 1B 到 10B 再到 30B 规模的模型，这是深思熟虑的策略。听到他们明确表示“是的，我们就是这么做的”，感觉非常棒。

我们也明白这是一个极其耗费时间的事情，所以开源模型其实很困难。在生态系统中需要做大量的工作。我认为他们也感受到了这种压力：我们可以训练更多的模型，但如果我们发布了一个模型，我们就必须去提供支持。我们需要去对接 vLLM，我们需要去对接开源生态系统中的所有这些公司。然而模型研发团队的规模依然很小，他们没有办法把这些工作外包出去。这些工作仍然需要由那些最接近模型研发的人来亲力亲为。所以这里存在两难：你可能会发布太多的模型导致维护不过来，同时他们也没有开源最顶级的模型。

其中一个问题是，AI 投资到底更像是一种 SaaS（软件即服务），还是更接近云计算的支出？无论这是一种刻板印象还是确有其事，美国人普遍认为中国在这类服务上不愿意花钱。比如，类似 Slack 这样的软件在中国市场要小得多，人们可能宁愿在公司内部自己开发一套极简的软件，或者随便下载点什么，大家非常不愿意为软件支付那种“按人头/按月”的订阅费。但所有这些公司都在云端运行，阿里巴巴拥有庞大的业务，许多现代软件都需要通过云来实现。我认为中国市场将逐渐转变观念，把 AI 支出视为类似于云计算的必需支出。虽然可能不会像美国市场的支出那样夸张，但他们会将其视为打造所需技术不可或缺的花费。正因如此，这些云服务厂商将继续稳固存在。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So I think Quinn has won the hearts and minds of open source AI by releasing these small models consistently with incredible performance at all these sizes. They kind of were doing this before Llama 4 and before Llama Faded, but they like really hit their stride right around the same time as Llama 4 happened in Meta Paused. And they know this. So we asked them, it's like they think about things that developers will use. They want to keep building models that developers use and thrive on. But it's like when you look at Quinn, they haven't released their biggest models for a while. So it's like Quen Plus and Quen Max have been closed source. And this is very much of like the cloud side of Alibaba talking where just like the US like you see Google Cloud's crazy expenditures and crazy earnings. It's like Alibaba is the default in China for that to happen and they know this. So like they're not going to release a model like they might tell us they might not release it because no one will use it. But also it's like I'm going to be like look you can make a lot of money on this and I think there's a lot of money to be made in AI. But I think the the most interesting thing is hearing various people talk about them being intentional about these small models and it's like not an accident. Maybe it was at the beginning or like oh let's try to do this thing somebody else is doing but they have a very refined recipe of these 1 to 10 to 30B models that are very popular and that's intentional and it's kind of nice to just like hear how they like they're like yes we do this. We understand it's a time sync so it's hard to release models. It takes a lot of work in the ecosystem. And I think they felt that stress of like we could build more models but if we build a model we have to support it. We have to go to VLM we have to go to all these companies in the open ecosystem and like the modeling team is still pretty small and it's like they don't have a way to like outsource that work. It's somebody build somebody very close to building the model still does this. There's the two ends of you can release too many models and also they haven't releas one of the questions was like is AI investment kind of like a a SAS like this software as a service thing or closer to a cloud spend because one of the whether or not it's a trope or actually true is that the views in the US is that China doesn't spend on these these services where it's like the Slack equivalent is much smaller smaller and people will maybe just like rebuild minimal software in house or download something and much less willing to pay this like per head per seat monthly cost on software. But all these companies do run on the cloud like Alibaba has a large business and like a lot of modern software you need via the cloud. I think that China will shift to be more of viewing that AI spend is like this cloud spend. It might not be as exorbitant as the spend in the US but they'll view it as needed spend to make the technology that they want to make. So therefore it's like these clouds will exist.

</details>

### 云计算生态与基础设施差异

**Speaker B**：这太有意思了，因为当你抵达上海机场，或者乘坐高铁前往杭州时，你会看到阿里云的商业广告牌。比如我刚到北京，第一眼看到的就是阿里云的什么东西。我当时的反应是，好吧，我到了。我认为阿里云和 AWS 之间的一个区别是，AWS 的 Bedrock 实际上同时接入了每一家的大模型、它们自己的模型以及各种小模型。但在中国的云厂商这里，他们只搭载自己的模型。

<details>
<summary>Original English</summary>

**Speaker B**: It's so interesting because when you arrive at the Shanghai airport or you take the highspeed train to Hjo, you will see the Alibaba cloud like a commercial banner like I walked into Beijing and the first thing I saw was like Alibaba cloud something. I'm like okay here I am. I think one difference between Alibaba cloud and AWS is that actually bedrock carry every single big model and their own model and smaller models at the same time. But for China cloud, they only carry their own models.

</details>

**Speaker A**：这是一个巨大的差异。并且我认为美国这种“新一代云（neocloud）”市场是一个庞大的部分，在那里有很多公司将别人的模型作为 Token 转售，或者转售算力。你能报出很多这样的公司名字，比如 CoreWeave、Nebius。

<details>
<summary>Original English</summary>

**Speaker A**: That's a big difference. And I think that this neocloud market in the US where there's just like a lot more people reselling other people's models as tokens or reselling compute is like a huge part of the US market. You could name so many companies. It's like Cororeweave, Nebius.

</details>

**Speaker B**：对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**：还有 Together, Fireworks, Lambda，未来肯定还会有更多。我们之前还讨论过 OpenRouter，而在中国，我不知道有任何与这些相对应的公司。我不认为他们有……所以，很大程度上，这些公司被视为是在英伟达（Nvidia）的支持下运转的。因为英伟达喜欢优先保证生态系统的多样性，避免他们绝大部分的收入过度依赖于 OpenAI 等少数几家公司，这对他们来说更有利。而在中国，这种动态机制似乎并不存在。

<details>
<summary>Original English</summary>

**Speaker A**: Together, Fireworks, Lambda, like there's going to be way more. We talked about open router and like I don't know any of the equivalents of those in China. I don't think they So that's a those companies are largely looked at as being supported by Nvidia in a lot of ways. Like Nvidia likes to prioritize the diversity of the ecosystem because it's better for them to not have most of their revenue be from opening eye like those few companies. And I it seems like that dynamic is not the same.

</details>

**Speaker B**：是的，这非常有趣，因为在中国缺失了这一层。他们没有这种基础设施层或优化层……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that one is interesting because you're missing this layer in China. They don't have the infrastructure or the optimization layer

</details>

<!-- chunk 5/12 -->

### 中美大模型生态差异与多方协作

**Speaker A**: 因为你看看类似的情况。我们现在看到的一个趋势是，比如 Cursor 采用了 Kimi 模型，然后他们在 Fireworks 的 RL（强化学习）沙盒训练环境中进行后训练，并通过 Fireworks 提供服务。这是一个非常有趣的多方协作，用来打造一个非常强大的模型和产品。而在中国，可能需要更加垂直化的整合才能完成同样的事情。

<details>
<summary>Original English</summary>

**Speaker A**: because you look at the likes. So what a trend we're seeing now is like cursor took the Kimmy model and they postrained it within the fireworks like RL sandbox training environment and serve it with fireworks and like that's a really interesting multi-party collaboration to build a like a very strong model and product which might have to be like more verticalized in China to get the same thing done.

</details>

**Speaker B**: 可能中国公司就是想把所有东西都留在内部。是的，这与那种所有权和整合的观念相悖。为了支持一家在这些中间层运营的公司，你必须接受将重要的事情外包出去，无论是 GPU 托管还是推理计算，因为你想把精力集中在其他事情上，这看起来更像是一种西方初创公司的行事风格。

<details>
<summary>Original English</summary>

**Speaker B**: Probably like Chinese companies just want to have everything inhouse. Yeah, it goes against the like the ownership and the integration where it's like in order to support a company that operates in these middle layers, you have to be okay with like offloading a important thing whether it's GPU hosting or inference because you want to focus on something else and that just seems like a more western startup style of things than otherwise.

</details>

**Speaker A**: 是的，是的。我确实认为，相比中国那些规模更大、历史更久的科技巨头，中国的许多模型实验室会更愿意尝试不同的事物。因为比如 Kimi 知道 Cursor 是如何训练他们模型的，他们就会去和 Cursor 交流之类的事情。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. I do think a lot of the model labs in China are going to be more willing to try different things than the bigger older tech companies in China because like Kimmy knows cursor trains their model like they will go talk to cursor and stuff like this

</details>

### 中国 2B 市场的未来与企业文化

**Speaker B**: 由李开复创立的零一万物（01.AI），他们现在经历了一次重大转型，完全转向了 2B 类型的商业模式。在这个时代，你如何看待中国 2B 市场的未来？

<details>
<summary>Original English</summary>

**Speaker B**: and um 01.ai AI founded by Kafuli. They now experienced a major transition to a total like 2B kind of business model. Where do you see the future for China's 2B market during the era?

</details>

**Speaker A**: 这又回到了这些关系能否建立起来的问题上。所以我认为他们中很多人都在想，是否能够成功打入这个面向企业的全球软件市场。我觉得要让我押注他们能否在国内市场胜出真的很难。我认为，是的，你可以利用 AI 的专业知识在另一家公司内部构建它，这对于缺乏 AI 专长的公司来说会非常有价值。但问题在于他们是否愿意这样做，因为如果你依赖外部合作伙伴来做这件事，感觉就像是失去了控制权。就像美国最近的趋势是所谓的“前线部署工程师”（Forward Deployed Engineers），这是个流行词汇，缩写是 FDEs。就像 OpenAI 正在大量招聘这类职位。这种模式在美国会发生，但关键在于，这是否是一种可行的模式——你直接走进一家公司的大门，并真正受到他们的欢迎。这非常有趣，他们打算尝试这种做法。我认为，如果这种模式奏效的话，作为在 AI 时代第一个重新尝试这种做法的人，显然会非常有利。但我只能说我完全不知道结果会怎样。我甚至可以抛硬币来猜，因为这完全取决于这种我无法完全理解的中国商业文化。

<details>
<summary>Original English</summary>

**Speaker A**: It goes back to if these relationships can kind of be formed. So I think a lot of them are wondering if they can hit the kind of use this global to business software market. I feel like I like it's so hard for me to make a bet on domestically whether or not it'll win. And I think that like yes, you can take AI expertise and build it within another company and it'll be very valuable for the company that had less AI expertise, but it's like whether or not this willingness to like you're losing ownership if you're relying on an external partner to do this. It's like the latest trend in the US is like forward deployed engineers is this buzz word FTEEs. It's like OpenAI is hiring a ton and stuff like this where it's like gonna happen in the US, but it's like is that gonna be a like viable thing where you can go through the front door of a company and actually get welcomed to them. It's very interesting. It's like they're going to try this and I think that like if it works, being the first one to retry it in the AI era is going to obviously be so useful, but I'm like I have no idea. Like I could flip a coin like it depends entirely on kind of this like Chinese culture the business that I can't fully understand.

</details>

**Speaker B**: 是的。那你们当时去见了谁？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. But did you who whom did you meet with for

</details>

**Speaker A**: 我们见到了……

<details>
<summary>Original English</summary>

**Speaker A**: I we met with

</details>

**Speaker B**: 李开复？是的。是的，是的。交谈得怎么样？

<details>
<summary>Original English</summary>

**Speaker B**: Kyouli? Yeah. Yeah. Yeah. How was the conversation?

</details>

**Speaker A**: 挺好的。我的意思是，他简直就是一个传奇，能见到他，能见到这样的人真的太酷了。而且他非常专注，他这一生已经取得了那么多成就，他完全可以随心所欲，甚至不再工作。看到他依然在努力解决问题，思考如何重塑他的业务，这本身就是一件非常有“AI 精神”的事情。这就像是把所有这些人又吸引回来，让他们试图去思考构建企业的下一个阶段会是什么样子。

<details>
<summary>Original English</summary>

**Speaker A**: It was good. He's I mean he's like such a legend to meet him and it's so cool to be able to see people like that and he's like it's focused like he could do he's done so much in his life. he can do whatever he wants or not work. And it's like to see him like trying to solve a problem and figure out how to reimagine his business is like a very AI type thing where it's like it's just drawn all these people back to like try to think about what the next phase of building businesses is going to look like.

</details>

### 构建模型的文化与投入成本

**Speaker B**: 为什么李开复的实验室没能成为中国领先的实验室？

<details>
<summary>Original English</summary>

**Speaker B**: Why Kyu's lab failed to become the leading lab in China?

</details>

**Speaker A**: 我其实也不太清楚。你应该去问他。

<details>
<summary>Original English</summary>

**Speaker A**: I don't really know. You should ask him.

</details>

**Speaker B**: 是啊，这是个棘手的问题。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that's a tough question. 

</details>

**Speaker A**: 是的，我认为用 AI 来做事情有很多机会，而构建模型则是一种完全不同的文化。构建模型非常像是不停地转动曲柄，不断地向上攀登资源阶梯。我不认为只有零一万物是在构建了一个模型之后就停下脚步的。我觉得就像在美国，Databricks 之前也在构建模型，然后他们觉得：“我们没必要做这个了，别人已经买单了。”我不知道他们是否有过公开表态，但我认为 Databricks 的很多领导层都会这样告诉你：“我们很高兴不需要为构建这个模型付钱，我们要专注于我们自己的业务。”这就是为什么我感到惊讶，有这么多公司还在不断追求那种成本高得多的万亿参数模型。像零一万物和 Databricks 都在转向较小或者小而密的模型时退出了这场竞赛。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think there's a lot of opportunity for doing things with AI and building models is a different type of culture. The building models is very much like turning the crank and continuing to ratchet up the resource rungs. And I don't think it's just 01 AI that has like built a model and then stops. I think like in the US like data bricks was building models and then they were like no need for us to do this. Other people have got the bill. I don't know if they're on the record, but I think a lot of leadership at data bricks would tell you this. We're like, we're happy to not pay for building this model and we're going to do our business. And I think that that's why I'm surprised that so many companies have kept ratcheting this like 1 trillion parameter which is way more expensive. Like 01 AI and data bricks got out at like small or small dense models. 

</details>

**Speaker B**: 投资少得多。

<details>
<summary>Original English</summary>

**Speaker B**: It's like way less investment.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 所以从某些方面来说，如果你认为自己不会具有竞争力，早点停下来可能比晚点停下来更好，这似乎是明智之举。并不是每个人都需要拥有或者去构建最好的模型，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: So in some ways it might seem smart if you thought that you were not going to be competitive. You better it's better to stop earlier than later. Not everyone needs to have or to to build the best model, right?

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 中美大模型差距与评估

**Speaker B**: 一个老生常谈的问题。你认为美国最先进（SOTA）的模型领先中国模型多少个月？至于这个差距，它会变窄还是变宽？为什么？

<details>
<summary>Original English</summary>

**Speaker B**: A cliched question. How many months do you think US SOTA models are ahead of the Chinese models? Um, and for that gap, is it going to become narrower or wider? Why?

</details>

**Speaker A**: 在传统的基准测试上，这个差距保持在六到九个月已经有一段时间了。在现实世界的实际应用中，尤其是在推理模型的早期阶段，差距非常小，因为这是一个新的范式。当你处于一个新的范式中，去做的回报是非常陡峭的。美国和中国的实验室都在以非常快的进步速度向上攀登，而且中国实验室的发布时间更早。所以如果你和中国实验室的人交谈，他们会说：“我们的模型还在强化学习（RL）阶段。做完这最后一次强化学习大概需要一周时间，然后在完成后的大约一天内我们就会发布它。”而美国的实验室通常有一些流程，需要几周的时间才能把模型发布出来。因此，如果你在思考这种陡峭的进步曲线，你会看到两条不同的线。如果中国在技术上落后，但没有那种在等待发布期间毫无进展的水平线，而且中国发布得更快，那么这就使得用户实际体验到的性能趋于收敛。所以归根结底，性能差距体现在用户可获得的人工智能模型上。而且在我们的对话中，我们讨论了一些问题，比如脑力劳动领域，这主要涉及美国的知识工作者之类的事情。我认为从现实角度来看，美国前沿模型的原始效用在某种难以衡量的方式上确实更加稳健。所以在基准测试的分数上很难看出来。我认为在那些流行的基准测试上，六到九个月的差距会变得稳定，但在那些无形、难以衡量的方面，美国模型将会拉开距离。最好的例子就是 12 月和 1 月开始的这种 Cloud Code 和 Codex 革命。如果一个开源权重模型能够实现这种行为，那是显而易见的，因为全世界都会谈论它，那就是“我不再需要支付 200 美元，而是每月支付 1 美元就能用 OpenAI 的服务了”。很多人会转而使用它。而就目前的录音时间点来看，比如五到六个月的时间里，我真的不期望今年会出现那种非常清晰的分水岭事件来揭示这种差距。而且我们看待这种差距的方式也有点狭隘，没有考虑到 AI 在极其广泛的用例中是如何被实际使用的。

<details>
<summary>Original English</summary>

**Speaker A**: So on traditional benchmarks, it's been like six to nine months for a while. In real world use, especially early in reasoning models, it was very tight because it was a new paradigm. And it's like when you're in a new paradigm, the rewards to doing it are so steep. Both US and Chinese labs are climbing this really fast rate of improvement and the Chinese labs release sooner. So you talk to somebody at Chinese lab, they're like, "Our model's still in RL. It takes about a week to do this last RL run and then we'll release it within like a day of it being done." Where the US labs have some process that normally takes weeks to get the model out. So if you think about if you're on like steep progress, you have two different lines and it's like if China's behind but you don't have this like no progress horizontal is when you're waiting to release it. So China releases it faster. So it kind of like converges the performance that users get. So at the end of the day the performance gap is like the models that are available to people and through this conversation we've talked about a few things like some is like this knowledge work domain which is all this US workers and things like this which I think realistically the raw utility of the US frontier models are just like a bit more robust in a way that's been hard to measure. So it's hard to know on the benchmark numbers. I think the six to nine months on like the benchmarks that are popular will become stable but there's this like intangible unmeasurable where the US models will pull ahead. The best example is like this cloud code and codeex revolution that started in December and January where it's like it'll be very obvious if an open weight model enables this type of behavior because everybody in the world will be talking about it which is like I no longer I can pay $1 a month instead of open AI is $200 a month. a lot of people are going to switch and as of recording that's say like five to six months and I I just like don't really expect that like really clear watershed this year which will like shed some light on the gap and how like the way we're looking at the gap is like a bit narrow to how AI is used in a really broad set of use cases. Now

</details>

**Speaker B**: 为什么我们至今还没有看到一个真正优秀的中国代码模型？

<details>
<summary>Original English</summary>

**Speaker B**: why haven't we seen a really good Chinese coding model as of yet?

</details>

**Speaker A**: 我认为像 Cloud Code 和 Codex 这样受欢迎很大程度上是因为它们非常易于使用。我认为中国实验室将继续攻克编程难题。所以模型的实际代码生成质量将会高得令人难以置信，因为这是基于公开数据，比如 GitHub 上的数据来训练的，你创建谜题，让模型在上面学习解决。但在易用性方面，美国实验室已经占据了很大的领先地位。而且他们在运营方式上也有所不同，美国实验室能获取消费者数据。比如 Cursor 通过人们使用 Cursor 和 ChatGPT 的数据来训练他们的模型，而且 Codex 和 Cloud Code 也是如此。相比之下，所有这些开源权重实验室，他们发布了一个模型，然后配有自己的命令行界面（CLI），但这没那么受欢迎。而且该模型产生的大量使用数据并没有反馈给开发者。所以部分原因在于，那种真实世界的数据对于让模型在一般情况下变得更加稳健来说是非常有用的，而这正是闭源实验室所拥有的巨大优势。

<details>
<summary>Original English</summary>

**Speaker A**: I think a lot of what's popular with cloud coding codecs is that they're just very easy to use and I think the Chinese labs will keep solving coding. So like the actual code quality of the models will be incredibly high and that's based on like public data and things like GitHub and stuff like this and you create puzzles the model model learns to solve there. But it's in this like ease of use thing that the US labs have had a really big lead and there's a difference in how they operate where the US labs get consumer data. So like cursor trains their model on people using cursor and chatgbt and codeex and cloud code are the same while all these open weight labs they release a model and they have their CLIs that are a bit less popular. But a lot of the usage of the model just doesn't go back to the developer. So some of it is a bit of like that real world data is really useful to kind of make the model more robust across general circumstances and that's where the closed labs have a huge advantage.

</details>

### 中国开源模型策略

**Speaker B**: 酷。我确实还有一些关于开源模型的问题。为什么中国实验室发布了这么多强大的开源模型？

<details>
<summary>Original English</summary>

**Speaker B**: Cool. And I do have some open source model questions. Why are Chinese labs releasing so many strong open source models?

</details>

**Speaker A**: 这是一条获取存在感（relevance）的路径。我认为他们知道自己落后了，而且他们希望更多地融入讨论之中。如果没人知道你……

<details>
<summary>Original English</summary>

**Speaker A**: It's a path to relevance. I think they know they're behind and they know they want to become more in the conversation. And if no one knows about you

</details>

<!-- chunk 6/12 -->

### 中美开源模型的发展与竞争

**Speaker B**: ……如果你有一个 API，没人会去在意你的模型。但在这样一个 AI 模型如此宝贵且相当稀缺的世界里，当你将它们开源发布时，会有很多人觉得，“哦，我希望我有自己的 AI 模型，我会去看看并尝试一下。”所以，所有的实验室都非常务实，觉得这就是我们参与到 AI 前沿发展故事中的方式，他们也会继续这样做。我预计这种情况会保持稳定，因为我预计这种“快速跟进”的差距将继续存在。这就是为什么这是一种非常务实的心态。这就像是，我们这样做并没有增加太多风险，它帮助我们实现目标，这也是获得一些客户的唯一途径。所以，我们必须这么做。

<details>
<summary>Original English</summary>

**Speaker B**: ...and you have an API, nobody thinks about your model. But in a world where AI models are so valuable and pretty rare, when you release them openly, there's a lot of people that are like, "Oh, I wish I had my own AI model that are going to take a look and try it." So all the labs are really practical as like this is our way to be in the story of like what is happening at the frontier of AI and they will keep doing this. And I expect this to be stable because I expect this like fast follow gap to continue. And this is why it's like a very practical mindset. It's like there's not much added risk to us doing it. It helps us accomplish our goals. It's the only way to get some customers. So like we've got to do it.

</details>

**Speaker A**: 如果 Meta 未能成为最好的开源模型，这并不意味着美国实际上在将开源模型的领导地位拱手让给中国吧？

<details>
<summary>Original English</summary>

**Speaker A**: If Meta fails to become the best open model, doesn't mean that US actually is losing open model leadership to China.

</details>

**Speaker B**: 在过去的一年里，美国已经将开源模型的领导地位让给了中国。我认为特别是在 2025 年夏天，当时一大批这些新的中国实验室开始变得非常突出。那时 GLM 4.5 和 Kimi K2 作为他们的突破性模型问世。从那一刻起，美国就不再拥有开源模型的领导地位了，我认为自 2025 年夏天以来情况一直如此。任何声称不是这样的人，对于那些真正重要的模型到底来自哪里，都有点自欺欺人。

<details>
<summary>Original English</summary>

**Speaker B**: In the last year, US has seated the open model leadership to China. I think especially in the summer of 2025 when a bunch of these new Chinese labs were starting to get really prominent. That's when um GLM 4.5 and Kimmy K2 came out as their breakthrough models. And like from that point on like the US no longer had open model leadership and that's been the case I think since summer of 2025. Anyone claiming otherwise is a little bit diluted on where the models are coming from that actually matter?

</details>

**Speaker A**: 美国还有机会赶上吗？

<details>
<summary>Original English</summary>

**Speaker A**: Does US still have the chance to catch up?

</details>

**Speaker B**: 他们有机会，因为他们有英伟达（Nvidia），而英伟达的经济利益在于不让 AI 被任何一家公司垄断。实现这一目标的最好方式就是向世界发布开源模型。

<details>
<summary>Original English</summary>

**Speaker B**: They do because they have Nvidia and Nvidia's financial interest is to not have AI be owned by any one company. And the best way to do this is to release open models for the world.

</details>

**Speaker A**: 所以唯一的希望就是英伟达了？

<details>
<summary>Original English</summary>

**Speaker A**: So the only hope is Nvidia?

</details>

**Speaker B**: 现实地、潜在地来看，关于开源模型，我认为像 Meta 和微软这样的公司，他们有由 AI 支持的面向用户或企业的产品，所以他们可以发布开源权重模型。这不会真正损害他们的业务，但在最近几年他们选择不这么做。也许这会分散注意力，也许这是一种营销和安全风险之类的问题。但只要这种情况存在，我认为英伟达就是改变这一现状的最佳位置。就在录制节目的几天前或昨天，黄仁勋宣布了他们的 Neatron 3 Ultra 模型。我对此的看法是，这标志着英伟达重新开始尝试开源模型的第一阶段已经完成，他们推出了 Neatron 3 的 Nano、Super 和 Ultra，这是他们的混合专家模型，其中 Ultra 是最大的，他们随后将用它来在内部生成合成数据以及各种较小的模型并进行蒸馏。所以现在他们已经建立了自己的第一个大模型，他们在构建其他规模的模型并继续改进方面有了更多的灵活性。这就是他们开源模型努力将变得更有趣的地方。就像一旦有人做到了这么大，他们还能继续从那里扩大规模吗？或者像英伟达过去有很多模型都很好，但很快就跌出了使用或报道的周期。

<details>
<summary>Original English</summary>

**Speaker B**: realistically potentially like and open models like I think there's the likes of Meta and Microsoft where they have products whether user enterprise that are supported by AI so they could release openweight models. It wouldn't really hurt their businesses but they've chose not to in recent years. Maybe it's a distraction. Maybe it's a like a marketing and security risk or something. But so long as that stays, I think Nvidia is best positioned to change this. As of recording, like a couple days ago or yesterday, and Jensen announced their Neatron 3 Ultra model. The way I think about this is like that's the completion of the first arc to Nvidia starting to try open models again where they had these Neatron 3 Nano, Super, and Ultra, which is their like mixture of expert models and Ultra is the biggest one, which they will then use to make synthetic data and all sorts of smaller models and distillation inhouse. So now that they have their first big model established, they have a lot more flexibility in building other sizes of models and continuing to improve it. And this is where it'll be more interesting to see their open model efforts. It's like once somebody gets to this big, can they keep kind of scaling it from there? Or Nvidia had a lot of models in the past that were like were good but kind of fell out of the usage or coverage cycle a bit more quickly.

</details>

**Speaker A**: 像 Reflection AI 或者也许是你们这样的小型参与者呢？

<details>
<summary>Original English</summary>

**Speaker A**: How about some smaller players like Reflection AI or maybe you guys?

</details>

**Speaker B**: 是的。所以我觉得会有越来越多的人在开源领域构建模型，开源生态系统可以支持多种多样的模型。这些中小型模型非常有用，因为它们非常便宜，如果你能让它们重复执行一项任务，与使用更大的模型相比，你将节省非常多的钱。这就是为什么在开源模型领域中，人们会有一种追逐前沿的执念，也就是那些大模型，比如 Neatron Ultra 和 Kimi K2 之类的。所以我认为随着时间的推移，这种对最大模型的执念会逐渐消退。比如 Reflection 想要构建一个大模型，但真正能赢得人心的是那些与 Qwen（通义千问）竞争的人，这是一个小模型，世界上每一个研究人员都在基于它进行构建。现在 AI 研究在很大程度上是基于 Qwen 进行的，这简直不可思议。很长一段时间里都是 LLaMA，但现在好像所有的研究人员都知道 Qwen 在这个规模上是如何运作的。他们已经习惯了使用它，对他们来说这是一个非常了不起的成就，我觉得大家对这个讨论得还不够。而且我认为随着时间的推移，这种从小到大的分布会吸引更多层面的兴趣。我觉得对于 Reflection 来说，选择一个服务较少的利基市场可能会更好。比如 AI2 构建的小模型非常适合研究，我觉得 AI2 不应该去追逐前沿，试图去构建一个万亿参数的模型。我认为从慈善的角度来看这是不可能的，而且从战略上做些不同的事情也是件好事。在人们意识到他们在资金上无法跟上前沿之前，我们还有时间去填补不同的利基市场。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So I think there will be many more people building models in the open and the open ecosystem can support like a diversity of models. So these smaller medium-sized models are very useful because they're so cheap and if you can get them to do one task repeatedly, you're going to save so much money over using cler codecs and why there's kind of a fixation in open models of chasing the frontier which is these big models such as Neatron Ultra and Kimmy K2 and whatever. So I think that's kind of something where over time that fixation on the largest model will fade. So like reflection wants to build a big model, but it's like people competing with Quen that will win the hearts and minds, which is this small model that every single researcher in the world is building off of like the extent that AI research right now is done on Quen is incredible. It was llama for a long time, but it's like everybody like all the researchers know how Quen works at that scale. they're used to using it and that's like a really remarkable achievement for them and I think it's like not talked about enough and I think over time that distribution from small to big will have more levels of interest and I think like for a reflection it might be better to like pick a niche that's less served and like AI2 builds small models which are great for research and it's like I don't think AI2 should chase the frontier and try to build a one trillion parameter model I think philanthropically it's not possible but also it's just like good to do something strategically different than like we there's time to fill different niches before people realize they can't financially keep up with the frontier.

</details>

**Speaker A**: 谁拥有中国最好的开源模型？

<details>
<summary>Original English</summary>

**Speaker A**: Who has the best uh China open source models?

</details>

**Speaker B**: 这个情况是起伏不定的。我想我个人希望能花更多时间去尝试各种模型。我会说最好的模型像是 Kimi 和智谱（Zhipu/Zai）。比如 Kimi K2.6 和 GLM 5.1 可能是听说得最多的，像是在实际使用前沿产生了影响，但变化太快了。我觉得在整个 2025 年，DeepSeek 是当之无愧的王者，拥有最好的模型，特别是他们的 V3 和 R1 系列。如果 Xiaomi 拿下桂冠我也不会感到惊讶，而且中国的 Qwen 最大的模型已经被闭源了。这阻碍了他们在最大规模模型上的一些采用和市场份额。但我不知道，如果你拿枪指着我的头逼我选，我会说截至今天，Kimi 和智谱拥有世界上最好的开源模型。

<details>
<summary>Original English</summary>

**Speaker B**: It goes back and forth. I think that I personally want to spend more time playing with the various models. I would say that the best models are like Kimmy and Zai. So like Kimmy K2.6 six and GLM 5.1 are probably the ones that I hear most as like actually making a difference at the frontier of usage, but it so fast. Like I think all of 2025, Deepseek was the like unanimous king with the best models, particularly like their V3 and R1 lines. And I wouldn't be surprised if Xiaomi was to to take a crown and China Quinn's biggest models have been closed. That has held back some of their adoption and mind share with the biggest sizes. But I don't know if you put a gun to my head, I would say Kimmy and Kim Kimmy and Zai as of today are the best open models in the world.

</details>

**Speaker A**: 但竞争很激烈，对吧？情况会随着非常微小的利润率而变化。

<details>
<summary>Original English</summary>

**Speaker A**: But the competition is intense, right? That changes very fine margins.

</details>

### 中美 AI 实验室与研究人员的差异

**Speaker A**: 你在文章中提到了很多中国研究人员。跟我们谈谈你对他们的印象。他们和美国 AI 实验室有什么不同？

<details>
<summary>Original English</summary>

**Speaker A**: You mentioned that a lot of Chinese researchers in your article. Tell us about your impression on them. How are they different from the US AI labs?

</details>

**Speaker B**: 中国有太多的人才了，当你去一个实验室，那里大部分都是在中国长大的中国研究人员。他们通常更年轻。我们去了清华（Tsinghua/Singa）附近的很多地方，那里还有其他顶尖大学。所以当你去实验室时，首先人员构成要统一得多。就像很多中国研究人员，而在这里 AI2 或其他任何地方，我感觉我在和形形色色的人一起工作。作为一个在美国不是移民或父母不是移民的人，我觉得自己都有点不寻常。我与来自世界各地的人共事，无论是欧洲、中东、中国还是亚洲其他地方，在美国的实验室也是如此。美国有很多中国研究人员，但那种人口比例的水平绝对是一种完全不同的感觉。然后我认为我们之前讨论过的一些事情，很多顶尖的美国研究人员都在谈论 AI 将走向何方，这种关于模型哲学或艺术设计的探讨。我觉得这次旅行的组织者，凯瑟琳·雷努尔（Katherine Renul）指出的一个例子是，像阿曼达·阿斯卡尔（Amanda Ascal）那样的人在谈论模型特征并真正去塑造模型的基调。而在中国，这种对话几乎没有出现。在一些领域中，他们谈论的话题，或者他们愿意预测 AI 走向多远的意愿，是相当不同的。除此之外，两边都非常相似。我觉得更具有中国特色且更有趣的事情是，中国最新一代的研究人员似乎在英语表达上更好了。这么多非常年轻的人英语说得棒极了，他们都在推特上关注西方的 AI 生态系统，阅读博客，他们都在写这些论文，而反过来却并非如此。美国的生态系统里很多人完全没有这种意识，他们不会去思考中国正在发生什么。即使有人真的对此感兴趣，想知道这些中国公司是如何发展的，也很难获得关于中国科技生态系统正在发生什么的可靠信息。所以，这存在着非常不同的信息流，这将影响人们的思维方式。而且，为自己周围的事物感到非常自豪并有些自夸，这也是一个相当典型的美国性格特征。这非常美国。

<details>
<summary>Original English</summary>

**Speaker B**: There's so much talent in China whereas you go to a lab and it's mostly like Chinese researchers grew up in China. They're often younger. They lot like we went to a lot of places near Singa and there's other great universities. So it's like you go to the labs for one it's way more uniform and who is there like a lot of Chinese researchers it's like here at AI2 or anywhere I'm like I feel like I work with all sorts of people and as somebody who is like not a immigrant or parents who were an immigrant in the US I'm like I feel a little bit unusual. like I work with people from all over the world whether it's Europe, Middle East, China, other places in Asia and that's in the US labs that's also the case. There's a lot of Chinese researchers in the US, but that's like the population level is like that's definitely a a different feeling there. And then I think some of these things we talked about earlier where a lot of the like top US researchers are like talking about where AI will be going. this kind of philosophical or artistic design of models. And I think it's an example that the organizer of the trip um Katherine Renul pointed out is that like the likes of Amanda Ascal that are talking about like model character and really crafting the tone of the models. It's like that whole conversation didn't really come up in China. It's like there's some pockets there where the topics they talk about or like how far they're willing to project where AI is going is is pretty different. Otherwise, it's so similar. I think the things that are more interesting China specific is like the newest generation of researchers in China seem like even better at speaking English. Like so many of these really young people speak incredible English and they all follow the western AI ecosystem on Twitter and read blogs and they're all writing these papers where the opposite is not true where it's like the US ecosystem a lot of people just have no like they don't think about what's happening in China they don't like it's hard to get reliable information or what I feel like is of what's happening in the Chinese tech ecosystem even if somebody's like really interested in it and wants to know how these companies navigate. So there's these very different information flows that will feed into how people think, but also it's like a fairly American character trait to be like very proud of the stuff around you and like slightly boastful. It's like a very American

</details>

<!-- chunk 7/12 -->

### 硅谷与中国AI实验室的文化差异

**Speaker A**：……硅谷的环境某种程度上在奖励人们做这些事情，而且这在某种意义上让人有点管中窥豹。硅谷显然正在发展自己狭隘的文化以及围绕AI的讨论，比如那些关于“永久底层阶级”的胡言乱语，现在又是“递归自我改进”和“奇点”。当你去中国的实验室拜访时，也会看到一些这种现象的影子，但要少得多。他们很大程度上是从美国那边听来的。他们的反应像是，“哦，这有点奇怪，但我们就当个乐子看吧。”但是当你去旧金山时，你会发现这真的是人们都在讨论的话题。就像那些资深的博士生会觉得，“哦，我现在就需要赚钱。”

<details>
<summary>Original English</summary>

**Speaker A**: ...thing and it's like oh the Silicon Valley kind of en like rewards people from doing this and it's like a bit tunnel vision in a way where Silicon Valley is obviously developing its own narrow culture and discussion around AI with the like permanent underclass nonsense and now it's the recursive self-improvement and the singularity. There's sprinkles of this when you visit the Chinese labs but way less. They like got part of it from the US. They're like, "Oh, that's a little weird but we'll we'll be entertained by it." But when you go to SF, it's like that's really what people talk about. It's like senior PhD students are like, "Oh, I need to make my money now.

</details>

**Speaker B**：“我需要加入一个实验室。”

<details>
<summary>Original English</summary>

**Speaker B**: I need to join a lab."

</details>

**Speaker A**：在旧金山，围绕着AI的时效性以及他们的职业生涯将如何改变，有一种非常紧张的文化氛围。而在中国，我没有感觉到同样的氛围，他们更像是，“我们要去做这件事。”在这方面，他们可能更脚踏实地一些，对事物的焦虑感较少。

<details>
<summary>Original English</summary>

**Speaker A**: There's this very intense culture in SF around the timeliness of AI and how their career is changing that didn't feel the same in China where they're like, "We're going to do this." Maybe a bit more down to earth in that regards like less anxious about things.

</details>

### 华人顶尖人才在AI研究中的角色

**Speaker B**：在当前的这一波浪潮中，您如何看待中国的AI人才？我的意思是，如果你看看美国领先的那些前沿AI实验室，你会看到很多华人研究员，对吧？美籍华人研究员在完成博士学位后在那里工作。嗯，他们可能是移民，也可能是第二代移民。今天，中国人才在AI研究中实际上扮演着什么样的角色？

<details>
<summary>Original English</summary>

**Speaker B**: How do you view Chinese AI talent in the current wave? I mean like if you even look at the leading frontier AI labs in the US, you will see a lot of Chinese researchers, right? Chinese American researchers working there after completing their PhDs. Um they might be immigrants, they might be second generation immigrants. What kind of roles are Chinese talents actually playing in the AI research today?

</details>

**Speaker A**：他们在每家公司里都扮演着至关重要的角色。比如，我认为美国目前限制高技能移民的政治立场对这个国家是不利的。我本人与很多中国人或国际人士共事，我希望他们能够生活在我喜欢生活的这个国家里，并且我很不赞同正在推行的政策。真的。我认为任何在科技行业工作的人都知道这些人才有多么关键。大家也有担忧，比如最近有新闻报道称，一些顶尖AI公司的高管护照被限制出境。美国那些对这些人才重要性很敏感的人，以及日益紧张的地缘政治局势会让他们担心，如果（中国）召回那些顶尖研究人员怎么办，因为美国公司将会受到严重打击。现实就是如此。我不知道短期内是否真的会做出这种召回决定。这完全不在收听这个播客的人群圈子能触及的范围内。做出那个决定的不是这群人。但在美国，人们都在谈论这件事，认为这可能是阻碍科技行业进步的一个主要潜在瓶颈。

<details>
<summary>Original English</summary>

**Speaker A**: They're in every company playing crucial roles. Like I think the US current political stances to limit high school immigration is bad for the country. Like I I want I work with a lot of Chinese or international people and I think that I want them to be able to live in the country where I like to live and I would like like I disagree with the policy that is going on. Yeah. And I think anyone that works in tech knows how crucial this talent is. And I think there's worries as for example there was recent news about like exit bans on passports for some of the top executives AI companies and people in the US that are sensitive to how important this talent is and the rising geopolitical tension will worry like what if they call back the top researchers cuz the US companies will be severely hurt. Like that's that's the reality of it. I don't know if that call gets made at all in the near term. That is not remotely near the circles of people who listen to this podcast. Like that's not who makes that decision. But like people talk about this stuff in the US as being a major potential bottleneck on the tech industry's progress.

</details>

**Speaker B**：看起来你只需要一个人来领导团队，对吧？然后你就有那个模型去……

<details>
<summary>Original English</summary>

**Speaker B**: It looks like you only need one person to lead the team, right? Then you have that model to be

</details>

### AI模型开发中的组织架构挑战

**Speaker A**：……愿景很难。所以在构建语言模型时，一个被低估的问题是，很大程度上这是一个组织架构（org chart）问题，你拥有人才并且你想让模型变得更好，而困难的事情是组织这些人才，弄清楚如何把大问题分解成小问题，从而能让大量的人才汇聚到这一个模型上。

<details>
<summary>Original English</summary>

**Speaker A**: vision is hard. So an undersold thing about building language models is that so much of it is an org chart problem where you have talent and you want to make the model better and the hard thing is organizing the talent and figuring out how to break down the big problems into little problems where a lot of talent can funnel into this one model.

</details>

**Speaker B**：我不知道我是否准备好非常笃定地说出这一点，但这可能就是中国工程师受训的方式，他们可能更适合构建这种组织架构，感觉就像是，他们只会埋头苦干自己的那一小块东西，并为这能为更大的模型做出贡献而感到高兴。我认为这里存在很多不确定性，因为比如前沿实验室实际上是如何运作的，这方面的记录并不多，可能更多的是一种混乱状态，就像人们到处奔走，试图一直都在制造模型。可能这不是最好的比喻，但这绝对是受限于组织架构的，或者说你必须把所有这些人都集中到这一件事上。

<details>
<summary>Original English</summary>

**Speaker B**: I don't know if I'm ready to state this like really strongly, but it like could be the way that Chinese engineers are trained that they like more suited to making these org charts where it's just like they're just going to grind on their little thing and be happy that it contributes to the bigger model. I think there's a lot of uncertainty in this cuz like how the frontier labs actually work is not that well documented and it might just be more of chaos where it's just like people running around trying to make the model all the time. It's like not the best analogy but it's like it's definitely a works chart limited or you have to get all these people into this one thing.

</details>

### 拥抱新范式与中美教育体系差异

**Speaker A**：是的。中国的AI研究人员是否更愿意抛弃旧有假设，直接去吸收最新的范式？如果你看看RL智能体、编程模型以及工具使用，比如，这些并不是DeepSeek发明的，但这家公司以极其高效的方式优化了这项技术。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Are Chinese AI researchers more willing to drop old assumptions and just um absorb the latest paradigm? If you look at RL agents, coding models and tool use for example, wasn't invented by deepseek but the company optimized the technology in an extremely effective way.

</details>

**Speaker B**：我认为这更多地是因为那些新入行且充满活力的年轻研究员。有一句非常冷酷的俗语，叫做“科学的进步是一次一次的葬礼（science advances one funeral at a time）”，这是一种非常惨淡的说法。但这只是说明，新人更愿意接受最新的事物，他们没有理由去捍卫旧观念，因为他们没有既定的过往记录，而且他们想要一头扎进去并抓住这些新事物。从中国潜在更年轻（的科研力量）的角度来看，无论是在工程人才还是领导层，这些人往往背负的先入之见更少，因此这可能是真的。如果你受过科学训练，这是一种常识，越是年轻，就越能产生很多新想法和改变。

<details>
<summary>Original English</summary>

**Speaker B**: I think this is something that's more of just with new and like youthful motivated researchers. There's a very grim saying that's like science advances one funeral at a time which is like the most bleak way of saying it. But this is just that like new people are much more willing to accept the newest things and they have no reason to defend their old ideas because they have no established track record and they want to dive in and take these things. And to the extent that China is potentially younger and both through engineering talent and leadership like those people just have less priors and therefore it might be true. It's something if you're trained in science you it's like the younger you are like that's where a lot of the new ideas and change comes from

</details>

**Speaker A**：对于中国文化来说，这是否意味着……比如要培养出一个真正具有远见的人，那种顶级专家级别的人，会更加困难？

<details>
<summary>Original English</summary>

**Speaker A**: for Chinese culture doesn't mean um it is harder to cultivate someone who is truly visionary for example that level of leading expert

</details>

**Speaker B**：那是我有的印象，而这个印象是建立在理解其文化基于从小就开始的标准化考试之上的。其中一些考试奖励死记硬背，学生们知道如果他们通过了这个考试，他们就能进入下一阶梯最好的学校，而且他们总是处于一种超级竞争的状态，思考着这种阻碍他们进步的关卡。如果我对中国体制的理解有误，请纠正我，但我的理解是，美国的生态系统里这种“关卡”要少一些，不是那种非好即坏来决定命运的模式，它更像是一个连续体，很多最优秀的人去了最好的学校，而次好的学校也非常棒，它们之间是互相融合的。是的，美国也存在文凭主义，但可能没有那么极端。所以，我认为这种（难以培养出有远见的人）情况是非常有可能存在的。一些领导层在私下也会谈论这个，比如这种模式奖励死记硬背。而且教育体系非常难以重塑，即便你有心去改。

<details>
<summary>Original English</summary>

**Speaker B**: that's the impression that I have and the impression is built on like understanding that the culture is built on like standardized testing from such a young age and some of these tests rewarding memorization students know that like if they make this test they get to go to the best school at the next rung and they always are this like super competitive thinking about this kind of gate in their progress and correct me if my understanding of the Chinese system is wrong but that's my understanding where the US ecosystem has like less of these gates where it's like your fate is decided as better or worse and it's more of a like a continuum where a lot of the best people go to the best schools and the second best schools are also very good and they blend through each And yes, there's credentialism, but maybe a bit less extreme. So, I think it's very possible that that is the case. And some of the leadership would off the record talk about this of like this rewards memorization. And it's very hard to rework an education system despite if you want to.

</details>

**Speaker A**：你私下里交谈过的一些科技界领袖说情况就是那样。我的反应是，好吧，我没有任何理由不相信你。

<details>
<summary>Original English</summary>

**Speaker A**: Some tech leaders you talked to off the record said that that was the case. And I was like, okay, I I have no reason to not believe you.

</details>

### “快速跟随者”与未来的中美竞争

**Speaker A**：你形容中国的实验室几乎是为成为完美的“快速跟随者”而建立的。你能解释一下吗？是什么让他们执行得如此之快？

<details>
<summary>Original English</summary>

**Speaker A**: You describe Chinese labs as almost perfectly set up to be fast followers. Can you explain that? What makes them execute so fast?

</details>

**Speaker B**：对，这就是我刚才谈到的各种因素，关于年轻的人才以及那种高度技术驱动并专注任务的文化，可能他们就是死死盯住这件事，而且他们拥有充沛的人才，所以你可以让大家在整个技术栈上工作，并将成果汇聚到一个模型中。我们已经见证过很多次了。一旦你知道某件事是可能的，做起来就会容易一点。而且我们已经看到中国科技经济在其他领域也表现出了这种竞争力。比如，你去看看小米（原词疑为Xiaomi或Xiai's）的科技产品。你走进去，感觉就像苹果商店一样。很有可能他们的设计是受到了iPad和iPhone的启发。而且他们在这方面做得很棒。他们不只是在AI领域这么做。所以我想，我预期他们会在AI领域再来一次。争论的焦点在于，他们重复这种基本操作是否足以让人怀疑，哦，中国会在AI实验室方面超越美国吗？我认为，在资源对等的世界里，他们也许能够做到，或者说他们拥有更多的人才，愿意在5到10年的时间框架内工作更长的时间；但我认为人力天赋只是构建这些模型所需的资源之一。通过主要是计算和数据体现的资本，实际上是最大的杠杆。而比起美国的超大规模公司，他们似乎拥有的资源不成比例地要少。所以我觉得，人才只能带领他们走这么远，但技术是会扩散的，最好的模型会让人更容易构建出更高效的模型。所以它是不是会继续这样推动下去呢？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, this is what I was talking about the various things on the young talent and the culture of just like being very technically driven and focused on their task and potentially like they're just lock in on this thing and they have abundant talent where it's like you can just have people working across the whole stack and funnel it into a model. And we've seen this many times. It's like once you know that something is possible, it's a bit easier to do this. And we've seen Chinese tech economies come for other things. It's like you go into like Xiai's technology. You go into it, it feels like an Apple store. It's very likely they're inspired by the iPad and the iPhone and their designs. And they're good at it. Like they've done this not just in AI. And I'm like, I expect them to do it in AI again. And the debate is whether or not like them doing this fundamentals to keep redoing it is enough for them to like people like to wonder is like oh is China going to leaprog the US AI labs and I think that in an equal resource world they might be able to or they're just like they have more talent that's willing to work more hours over a 5 to 10 year time frame but I think human talent is only one of the resources that it takes to build these models and just like capital through mostly compute and data is actually like the biggest lever. And it seems like they're disproportionately fewer resources than the US hypers scale companies. So it's like I think talent will only take them so far, but the technology diffuses where the best models make it easier to make more efficient like models. So it just kind of like is this going to keep propelling through there?

</details>

**Speaker A**：一个快速跟随者能成为前沿的领导者吗？

<details>
<summary>Original English</summary>

**Speaker A**: Can a fast follower become the frontier leader?

</details>

**Speaker B**：他们能。我觉得AI很奇特，因为它有很高的资源需求。我认为中国走向领导地位的路径是，花很长一段时间到达最终目的地，在这段时间里华为建立起了自己的产能，然后它的净产能变得更大。这就是你在人们谈论权力平衡和芯片时会听到的常见情景。所以我认为大多数人觉得……

<details>
<summary>Original English</summary>

**Speaker B**: They can. I think AI is weird because of the resource requirement. I think China's path to leadership is by it taking a long time to get to the final destination and that's time where Huawei builds out its capacity and then its net capacity becomes bigger. So the common scenario you'll hear in people talking about balance of power and chips. So I think that most people think that

</details>

<!-- chunk 8/12 -->

### 中美AI领军科学家的文化差异与人才流动

**Speaker A**: （这种改变）实现起来还有很长的路要走，但也不要完全排除这种可能性。当我们谈论顶尖AI科学家的文化差异时，你知道，在美国是这样，但如果回看中国，也许小米是个例外，雷军在社交媒体和播客上都非常活跃。还有来自通义千问（Qwen）的林建（Ling），他是千问的顶尖负责人，他在今年早些时候离开了公司。尤其是对于林建，我认为在所谓的“个人主义”和“集体主义”（即从本质上优先考虑公司利益）之间，存在着明显的冲突。你是否看到更多这种类型的冲突从中国实验室显现出来，并进入到西方的生态系统中？我认为有些研究人员会发现他们非常适合这种环境。所以我叫他贾斯汀（Justin），他的英文名。他在这方面做得非常好。我某种程度上认为这就像我们在美国也看到的一样，在科技公司里，那些在外部也能获得巨大影响力的人，可能会与领导层发生冲突，而大型科技公司就会觉得“我们没必要听你的”。然后他们就分道扬镳了，就像我们在美国看到的一样。

<details>
<summary>Original English</summary>

**Speaker A**: it would be a long haul for that to happen but don't rule it out. as we talk about the leading AI scientists culture difference you know here in the US right but I think back to China maybe Xiaomi extend exception with Lui being quite active on social media as well as podcasts there was also Ling from Quinn he was the tap lead of Quen he left the company earlier this year especially for Linguin I think there was apparent conflict between what's called the individualism and collectivism which prioritizes the company's interests per se. Do you see more of that kind of conflict coming out from the China labs >> going into this western ecosystem? I think some of the researchers will find that they are very well suited to this. So I call him Justin, the American name. And it's like he was so good at this. And I kind of see it as something we've also seen in America whereas like people in tech companies that can get a lot of influence externally as well can push against leadership and the big tech companies are like we don't need to listen to you. So then like they part ways like we've seen it >> like right >> like we've seen it in the US.

</details>

**Speaker B**: 我觉得一个著名的例子就是谷歌的一些AI伦理研究人员，比如Timnit（Timn）向谷歌领导层下达了最后通牒，然后他们拒绝了。在大型科技公司内部，你会撞到一些很难打破的墙。我认为这些中国研究人员中的一些人可能会被吸纳进（西方的）这个生态系统，我们可能会再次看到类似的情况。但对于像Kimi或智谱（Zi）这样的初创公司来说，他们会很乐意拥有一个能制造声势、吸引眼球的人，其他问题以后再去解决。这在很大程度上取决于公司的规模。但我认为，如果更多的中国研究人员进入这个领域，那将是一件好事，因为有更多的观点是好的。如果这个世界上的这一部分人能够在美国被看到，让更多的人了解他们是如何思考的，以及他们是如何处理模型的，那对某种全球平衡来说也是有好处的。

<details>
<summary>Original English</summary>

**Speaker B**: I think a prominent example was around the like some of the AI ethics researchers at Google where it's like um Timn sent sent an ultimatum to Google leadership and they said no and it's like like there's walls that you can hit within big tech companies that are hard to hit and I think that like some of these Chinese researchers will probably like get fed into this ecosystem and we might see some of it again but for startups the startups like Kimmy or Zi would love to have a person that is making bringing noise and bringing attention you just figure it all out later. Very much depends on the company size. But I think it would be good if more of the Chinese researchers get into this because it's good to have more views and like this whole part of the world if they can >> be seen in the US so more people understand how they think and how they approach models. It would be good for the kind of global equilibrium.

</details>

**Speaker A**: 是的，那太好了。我们正在努力做到这一点。我们正在尝试邀请更多的中国研究人员来我们的节目。所以，请订阅我们的频道。当你和那些中国研究人员交谈时，中国AI实验室内部的情绪是怎样的？你看到的是更多的自信、焦虑、好奇心，还是更实际的东西？

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, that's great. We're trying to do that. We're trying to invite more Chinese researchers coming to our show. >> Yeah. So subscribe our channel and uh when you talk to the Chinese researchers right what was the mode inside the Chinese AI labs did you see more confidence anxiety curiosity or something more practical

</details>

**Speaker B**: 我认为肯定存在一种无法在算力上跟上步伐的焦虑感，所以中国所有的实验室都想要更多的英伟达算力来训练最新的模型，而研究人员是最能感受到这一点的人，他们是真正撞到资源限制墙的人。但在其他方面，社会焦虑反而较少。我认为在美国，社会焦虑的浪潮非常大，比如我在这里共事的人都会严重担心自己的工作被取代。我就会觉得，“你是我认识的最好的AI研究人员之一。”但即便像这样的人也会说，“我真的非常非常担心这件事。”这反映在更广泛的讨论中，美国CEO们到处宣扬人们将如何失去工作，这并不是一个好的信息传递策略，但这已经非常深刻地植入了现在人们对AI以及数据中心讨论的看法中。这些文化上的“谢林点”（shelling points）似乎完全没有在中国落地。一些开发者被问到什么是AGI时，他们会说“当他们抢走我工作的时候”，但他们并不觉得这像是一片阴云笼罩着他们。他们的态度是：“我想把这个东西造出来，以后的事以后再说。”

<details>
<summary>Original English</summary>

**Speaker B**: >> I think there definitely an anxiety of not being able to keep up in compute so I think it's like all the Chinese labs want more Nvidia compute to train the latest models and the researchers are the people who feel this post it's like they're the people that are hitting the resource constraints but otherwise there's less social anxiety. I think in the US there's a big upswell of social anxiety whether it's people I work with here that are seriously concerned about their job being replaced. And I'm like you're the one of the best AI researchers I know. But like even people like this will be like I'm really really concerned about this. And this is in the broader discourse where American CEOs are going around talking about how people are going to lose their jobs, which is not a good messaging decision, but that's like very deeply embedded in how people think about AI now and the data center discussion. It doesn't seem like any of these cultural shelling points has landed in China. Some of the developers are like, we ask them what is AGI and they're like when they take my job and they're not like it's not like a cloud hanging over them. They're like, I want to build this thing and figure it out later.

</details>

**Speaker A**: 为什么会这样呢？

<details>
<summary>Original English</summary>

**Speaker A**: >> Why is that?

</details>

**Speaker B**: 开发者之间确实存在一些犹豫，或者说感觉变化太快。他们都在使用Claude，尽管据称它在中国是被禁的。他们都用它来工作，并且非常坦诚地告诉我们，“我们喜欢Claude，Claude是最好的模型。”所以，关于软件工作岗位正在发生变化，肯定会产生一些担忧。但是，把AI看作是糟糕和具有破坏性的社会共识，要少得多。在中国，这种观点似乎完全没有确立。我认为他们中的一些人讨论过中国的情况，他们已经经历了太多快速连续的技术变革。随着国家在技术和经济上取得巨大进步，他们觉得，“这就像是下一次浪潮。”他们已经经历了太多这样的事情了，比如中国的超级应用，还有现在的电动汽车。他们的态度就是，“哦，这就是现在的样子。”而在美国，这些变革之间有更多的节奏和间隔。然后，对于最新的这一次变革，它想要推翻现状就会面临更多的惯性阻力。

<details>
<summary>Original English</summary>

**Speaker B**: >> There's some hesitancy around developers or like this is changing a lot. They all use Claude, which is supposedly banned in China. They all use it to do their work and they told us very forthcomingly like we love cloud, like cloud's the best model. So, there's definitely some hesitancy growing around like software jobs are changing, but it's much less of a collective like social opinion on AI is bad and disruptive. like that doesn't feel like it's established in China at all. I think they some of them discussed how China's they've been living through so many technological changes in rapid secession as the company makes so much progress technologically and economically where they're like this is like the next one where they've had so many with these like the Chinese mega apps like they have electric cars now like they're just kind of like oh this is this is just how it is where in the US it's like these changes have come with more cadence in between them and then like this is the latest one and there's kind of like more inertia that it's going to have to move aside. side.

</details>

### AI对齐与安全：中国与美国的视角差异

**Speaker A**: 中国实验室内部有人谈论对齐（alignment）或安全（safety）问题吗？

<details>
<summary>Original English</summary>

**Speaker A**: >> Are people talking about alignment at all, safety issue at all within Chinese labs?

</details>

**Speaker B**: 他们更多使用的是“安全（security）”这个词。公司绝对关心这个问题，但这远不是他们最关心的事情。他们的态度是：“如果我们要发布模型权重，我们要确保它不会带来任何巨大的新风险。”我们也会探讨，比如多模态模型呢？是的，其中一些事情演变成风险的速度确实变快了。但他们绝不是觉得：“我们要发布的这个大型文本LLM智能体是一个重大风险，因此我们不能发布它。”关于这一点，他们会说出很合理的看法，但绝不像在美国那样，听起来几乎像是出于意识形态和根深蒂固的担忧，认为AI，或者下一个AI，将会是一个令人极度担忧的存在。所以我认为他们是经过深思熟虑的，但并没有把它放在首位。是的，可能中国人只是更加务实。

<details>
<summary>Original English</summary>

**Speaker B**: >> The word that's used more is security. >> The companies definitely care about this, but it was much less front of mind. It was like if we're releasing model weights, we want to make sure that it's not >> enabling any gigantic new risk. And we would talk, we would poke at like what about multimodal models? like, yeah, some of these things have moved to be risks a bit faster, but it's much less of this big text LLM agent that we're releasing is a major risk and therefore we need to like not release it. They would say reasonable things about this, but it was not like in the US it can almost sound like ideological and like deep rooted concern that like AI like the next AI is going to be the one that is of a lot of concern. So I think it's measured but not very front of mind. Yeah, probably like Chinese are just being more practical.

</details>

**Speaker A**: 我觉得这很合理。我就觉得这在某种程度上也是我的立场。比如，我支持开源模型，但我不是一个绝对主义者。我不认为每个模型都必须是开源的。Claude的神话有一点营销噱头的成分，但它也是一个令人难以置信的突破性模型。如果他们在拥有它的第一天就直接上传到Hugging Face，那绝对不是件好事。技术扩散是需要时间的，对于具有变革性的事物，其访问权限随时间推移逐渐扩散是合理的。我们目前所处的平衡状态是，闭源模型领先，开源模型紧随其后。这似乎是将技术推向世界的好方法，我认为很多这些公司也会有同感。

<details>
<summary>Original English</summary>

**Speaker A**: >> I felt like it was reasonable. I was like that's it's kind of my stance. It's like I support open models, but I'm not an absolutist. It's like I don't think every model should necessarily be open. Claude mythos is a bit of a like marketing stunt, but also it's like an incredible breakthrough model. It would not be good if that was just uploaded to hugging face the first day that they had it. Like it takes time for technology to diffuse and access diffusing over time for transformative things is reasonable and the equilibrium we're in right now where the closed models are ahead and open models follow it like seems like a good way to get technology into the world and I think that a lot of these companies would feel similarly.

</details>

**Speaker B**: 你认为目前中国实验室在哪些方面是真正领先于美国实验室的？又在哪些方面虽然尚未领先，但发展速度超过了美国人的预期？

<details>
<summary>Original English</summary>

**Speaker B**: >> Which parts do you think Chinese labs are genuinely ahead of the US labs today and which parts are they not ahead but moving faster than Americans expect?

</details>

**Speaker A**: 很多人说中国实验室正在构建更高效的模型，我认为这有点言过其实。因为美国实验室在推理阶段处理的token数量要多得多。所以，他们的动机要强烈得多，比如让Claude的效率提升1%，就能带来数十亿美元的财务收益。所以我认为他们有更多理由去追求高效。但我确实认为，中国实验室因为做开源模型的时间更长，所以在理解人们如何使用他们的开源模型方面，做得更好。我们和阿里巴巴的人谈过，他们在这方面非常用心。而且现在像Kimi、智谱（Zai）以及其他所有已经建立了多个周期的公司，都在跟踪人们是如何使用他们的模型的。这种专业知识是非常短暂且极具价值的。比如我试图弄清楚人们是如何使用WMO的，但这真的很难直接获取信息。但这正是决定他们的模型是否成功的关键，除了那些基准测试之外，最重要的问题是：为什么Cursor选择了Kimi模型？Kimi显然会去深入思考这个问题，或者直接去问他们。而这正是AI前沿领域非常宝贵且难以获得的专业知识。所以他们知道是什么让一个开源模型变得更好，而你只有通过大量发布模型才能获得这种反馈。所以我认为像英伟达（Nvidia）在发布模型方面正在积聚势头，他们会开始获得更多这样的反馈。相比之下，美国有些人的反思是：“我们会在模型准备好时才发布。”但这样他们就完全得不到人们实际使用模型的反馈。是的，这个基准测试结果很好，但这个非常相关的功能却不起作用，为什么呢？我认为，这正是关于开源生态系统如何运作的无形知识正在不断巩固和积累的过程。

<details>
<summary>Original English</summary>

**Speaker A**: So a lot of people say the Chinese labs are building more efficient models and I think that's kind of overblown because the US labs are serving way more tokens at inference. So they're way more incentivized like the financial gain to make cla 1% more effective is like billions of dollars. So I think they have like more reasons to be efficient. But I think that the Chinese labs by doing it longer have a bit better understanding of like how people are using their open models. And we talked to people at Alibaba and they're very intentional about this. but also now the likes of Kimmy and Zai and all these others with these established that have multiple cycles they're following how people are using their models and this expertise is very transient like I try to figure out like how are people using WMO and it's like a masses like it's really hard to get the direct information but is is what makes their model successful or not obviously those benchmarks but then it's like why did cursor choose the Kimmy model Kimmyy's going to think about that Yeah, >> really deeply or ask them and this is like very valuable expertise at the frontier of AI that's hard to get. So they like know >> what makes a bit better open model or not and you only get this from releasing models a lot. So I think like Nvidia is building momentum on releasing models and they'll start to get more of this feedback and then there's reflection in the US that's like we'll release a model when it's ready but they're going to get none of this feedback of people actually use the model and yes this benchmark is good but this very related thing doesn't work. Why? And I think that's like the intangible knowledge of how the open ecosystem works is consolidating

</details>

<!-- chunk 9/12 -->

### 中国AI实验室面临的算力瓶颈与策略

**Speaker A**：让我们来看看相反的情况。目前中国实验室面临的最大劣势是什么？依然是GPU吗？

<details>
<summary>Original English</summary>

**Speaker A**: Let's move to the opposite case. What are the biggest disadvantage that the Chinese lab still face today? It's still GPU.

</details>

**Speaker B**：对，就是算力。估计数据可能不准确，但你可以说，像 Meta 或 OpenAI 拥有的 GPU 数量，比所有这些中国公司的总和还要多，而且事实很可能就是如此。我听到有传闻说，一位 OpenAI 的研究员自己就能分到大约 5000 张 GPU。而这可能占据了中国开源模型实验室研发预算的很大一部分。因此，我认为他们承担风险的余地，以及在算法上能够进行的动态尝试，要狭窄得多。我想他们某种程度上认为，只能去优化当前模型的既定路径，这更像是一种必然之举，因为他们知道能继续把模型做得更好，但整个生态的活力就没那么强了。一家中国实验室曾告诉我们，他们最近一次预训练跑了大概六个月，而且这是一个已经在 Hugging Face 上发布的模型。如果那次训练失败了，那整个系列的模型可能就不复存在了。对公司来说，这是一个非常危险的处境。我认为，在他们现有的算力水平下，他们的表现已经超出了大多数人的预期，但这确实是限制因素。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's compute. There's likely incorrect estimates, but you could say something like Meta or OpenAI have more GPUs than all of these like Chinese companies combined, and they they very well likely do. And I've heard rumors that say like an open AAI researcher has about can get like 5,000 GPUs for themselves. And this is like would be a major proportion of a Chinese open model labs research budget. So I think their aperture for risk and amount of dynamic things they can do algorithmically is much more narrow and I think they're sort of see like just optimizing the current path of the models as much more of a necessity because they know they can keep making this better but it's a less dynamic ecosystem. One of the Chinese labs told us like their latest pre-training run took like six months and this is a model that's out on hugging face and it's like if that run didn't work like that whole line of models just like wouldn't exist and that is a very precarious position to be for the company and I think that they're exceeding most people's expectations with the amount of compute that they have but that is the limiting factor

</details>

**Speaker A**：是的，中国实验室非常渴望获得更多英伟达 GPU 芯片。算力短缺在多大程度上改变了他们的模型策略？

<details>
<summary>Original English</summary>

**Speaker A**: and yes the Chinese labs are desperate for more Nvidia GPU chips how much does comput scarcity change their model strategy.

</details>

**Speaker B**：最重要的一点是，你基本上是根据下游的预期用途，以及训练集群的形态来设计每一个模型的。比如，训练集群会决定训练不同规模模型的效率，同时你也知道还需要对其进行部署推理。所以，由于他们可能只有较小的集群，这将改变他们做此类决策的方式；或者他们可能会降低基础模型架构变更的频率，因为预训练耗时太长。我也确实认为，我们将会在一些较小的实验室看到这种情况——阿里巴巴和字节跳动由于资源丰富可能会有所不同——但像 MiniMax、月之暗面等，大家的期望往往是像 Claude 和 GPT 那样达到 3 到 6 万亿参数的级别，我认为对他们来说要扩大规模会困难得多，除非他们能弄到那些最新的 NVL72 机架和 Blackwell 芯片之类的设备。所以本质上，这些是有天花板的，但这是一个多目标优化问题，比如你的训练集群是什么样、推理技术栈是什么样，他们现在可能还希望模型能在华为的硬件上进行推理。

<details>
<summary>Original English</summary>

**Speaker B**: The biggest thing is that every model you essentially design it based on how you expect it to be used downstream and then what the shape of your training clusters is. So like the training cluster will configure how efficient it is to train a different size of model and then you also know you need to serve it. So based on probably having smaller clusters which is going to change how they do make these types of decisions or maybe they can change their base model architecture less frequently because pre-training runs take longer and I do think that we're going to see for some of these smaller labs I think Alibaba and bite dance with the resources they have is a bit different but like miniax moonshot etc like most expectations are clawed and GPTs are at this like 3 to six trillion parameter range and I think it'll be a lot harder for them to scale up unless they're getting these like latest NVL 72 racks and Blackwell chips and things like this. So essentially there's like there's ceilings to these but it's a multi-optimization problem whether it's like what's your training cluster what's your inference stack they might want it to work on Huawei inference now

</details>

**Speaker A**：还要考虑你的用户是谁，所以他们要兼顾所有这些事情，而我们最终看到的只是 Hugging Face 上的一个参数在几十亿到万亿级别的模型。这很难直接映射，但它绝对是实验室里最有趣的决策之一，而且大多数人不会告诉你。

<details>
<summary>Original English</summary>

**Speaker A**: like who are your users so they do all of these things and we see the output as a model on hugging face of like search billion to a trillion parameters it's hard to map but it it's one of the most interesting decisions in a lab and most people won't tell you.

</details>

**Speaker B**：是的。那么，算力短缺是会倒逼出更高的效率，还是最终会限制其触及前沿的上限？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, does compute scarcity force better efficiency or does it ultimately cap the frontier?

</details>

**Speaker A**：确实有限制，但这更像是改变了你的工作方式。大家都在追求算力效率，因为如果你有更高效的研发流程，如果你把实验的单位成本降低一半，你就能跑两倍数量的实验。这就是非常基础的数学计算，每一个 AI 研究员都希望如此。很难说中国实验室在这方面就一定会做得更好。可能是因为他们拥有的推理算力较少，所以训练出一个在推理时更高效的模型，从而有不同的权衡。我觉得 DeepSeek 就以这些节省内存的创新而闻名，其中一些方法现在已经被广泛使用了，但当你去比较时，可能这仅仅是因为算力过剩带来的多余动作，美国的实验室看到这些可能就会觉得，“嗯，这能给我们带来一点小收益，但不值得费那么大功夫。”

<details>
<summary>Original English</summary>

**Speaker A**: It does, but it's more of like you're changing how you work. Like everybody wants compute efficiency because if you have a more efficient research, if you make your experimental unit half the price, you run twice as many experiments. There's like a lot of very basic math where every AI researcher wants this. It's hard to say that the Chinese labs would necessarily be better at it. It's like maybe because they have less inference compute, they train a model that's more efficient at inference and that has a different trade-off. I think Deep Seek's famous for these like memory saving innovations like some of which are used everywhere now, but it like might just be overkill when you compare like a US lab might look at that and be like h it would give us a small gain but it's not worth the effort or something.

</details>

### 华为芯片在实践中的表现与地缘政治争论

**Speaker B**：那么在实践中，像华为芯片这样的加速器到底有多好用？我听很多人说，它已经可以用于推理，但还不适合用于训练。这几乎是共识了。我们去拜访过一些更普通的、不是做核心大语言模型的公司，他们会说，“是的，我们必须采购华为芯片，但我们并没有实际使用它。”但是，我们交谈过的大多数语言模型公司都已经有了一定规模，大家都拥有用户正在注册使用的服务。比如智谱（Zai），他们的 API 每天要处理数万亿个 Token。所有这些公司都在说，“如果你能给我们提供华为芯片，我们或许能获得更多客户，并且他们正在弄清楚如何将这些芯片用于推理。”但在训练方面，目前似乎只有非常小的模型可以在华为硬件上训练。我个人预计这种现状还会持续一段时间。这就是为什么专注于训练的研究人员依然会说，我想要更多的英伟达芯片。

<details>
<summary>Original English</summary>

**Speaker B**: So how good are accelerators such as Huawei chips in practice? Um I heard many people saying it's ready for inference but not for training. That's mostly the consensus. We would go to some more random companies, so not like core LLM, and they're like, "Yeah, we have to have Huawei, but we don't use it." But most of the LM language model companies we talked to are established enough where it's they all have services that people are signing up for. Zai serves trillions of tokens a day on their API. And all of those companies are like, "If you can give me Huawei chips, we will maybe get more customers and they are figuring out how to use them for inference." But on training, it's only like very small models that could be trained on Huawei. And I personally expect that to be the status quo for a while. That's why researchers focused on training or like I would like more Nvidia trips.

</details>

**Speaker A**：“一段时间”是指多久？我的意思是，你去问一位半导体专家，我估计答案是以年为单位的，而英伟达目前依然遥遥领先，因为英伟达正在引导全球供应链来制造最顶尖的产品，相比之下，在华为这边，“需求是发明之母”，至于他们到底能走多远？我不知道。

<details>
<summary>Original English</summary>

**Speaker A**: A while is how long? I mean, ask a semiconductor expert, but I would expect order of years, whereas like still Nvidia is so far ahead cuz Nvidia is channeling the global supply chain into making the top end products versus necessity is the mother of invention at Huawei and it's like how far do they get? I don't know.

</details>

**Speaker B**：你是怎么看待黄仁勋（Jensen）和 Dwarkesh 最近的争论的？给不太了解背景的听众解释一下，黄仁勋反对严格限制中国获取英伟达 GPU，他认为中国已经拥有能源基础设施、芯片制造能力和 AI 人才，足以开发出先进模型。另一方面，他表示，限制销售只会让英伟达失去一个庞大的市场，同时却无法阻止中国的技术进程。而 Dwarkesh 则是持“中国威胁论”的立场，当然，黄仁勋是有偏见的，因为他想在中国卖出更多芯片，对吧？但你觉得谁是对的？

<details>
<summary>Original English</summary>

**Speaker B**: How do you see the recent debate between Jensen and Darkh? For people who are not very familiar with the context, Jensen argued against the strict limits on Chinese access to Nvidia GPUs, saying that China already has energy infrastructure, chip production capabilities and AI talent to develop advanced models. Independently, he said that restricting sales only cuts Invidia off from a massive market while failing to stop China's technology process. While Daresh was holding the China threat theory and of course Jensen is biased because he wants to sell more chips in China, right? But whom do you think is right?

</details>

**Speaker A**：我觉得实际上我处于中间立场，而且更偏向 Dwarkesh 一边。这最终变成了一个地缘政治的讨论，也就是你是否认为 AI 是一项会被用于此目的的技术？就我而言，我更希望看到传统的美国价值观，比如言论自由之类的事物传播到全世界。我认为将 AI 芯片提供给中国，在改变力量平衡这方面，确实会带来某种程度的风险。作为一个美国人，我的立场就是这样。

<details>
<summary>Original English</summary>

**Speaker A**: I think realistically I'm in the middle and more on Dwaresh's side. It ends up being a geopolitical discussion which is like do you think AI is a technology that is going to be used for this? And it's like I would rather see what is traditional American values of like freedom of expression and all these things spread into the world. And I think that giving AI chips to China does pose some level of of risk in this capacity to like on the balance of power. As an American, that's how I've fallen on this.

</details>

**Speaker B**：很难说到底会到什么程度。当你去听英伟达内部人士的说法时，他们基本上的意思是，美国已经没有多余的电力来建设了。因此，美国国内没法消耗这么多芯片，所以我们想把它们卖给中国。但与此同时，你又看到美国公司要求分配更多的额度，而美国政策制定者也在和那些表示“美国公司本来会买更多”的选民们交谈。所以我算是跟两边都聊过，一边是那些嚷着“我要更多芯片来卖给我的公司”的美国实验室，另一边是我跟英伟达的政策研究员聊，他们却说美国无法支撑更大的体量。所以，真的很难获得真实的基准信息，比如美国到底能消化多少，又有多少是被转移到了这个中国市场。这也是为什么我最终只能给出一个误差范围很大的结论，因为我不知道确切的平衡点在哪里，所以总有一些英伟达在美国绝对卖不出去的芯片，我们应该让他们卖给中国，从而支持英伟达在 AI 领域的领导地位。那么……

<details>
<summary>Original English</summary>

**Speaker B**: It's hard to know like to what extent. So when you listen to people within Nvidia, they essentially are saying there's no more power to build in the US. Therefore, no one in the US would buy these chips, so we sell them want to sell them to China. But at the same time, you have US companies asking for more allocation and US policy makers talking to constituents who are like the US companies would have bought more. So I kind of talked to both parties which is these US labs that are like I want more chips to sell my companies and I talked to policy researchers at Nvidia where they're like the US can't support more volume. So it's so hard to get the ground truth information of like how much would the US buy and what is the diverted to this Chinese market. This is why like I end up with big air bars because I don't know who exact like what the equilibrium is and therefore there's like there's some chips that Nvidia definitely wouldn't sell in the US and we should tell them China and support Nvidia's AI leadership. So

</details>

**Speaker A**：我比较好奇的一个问题是，禁令会不会刺激中国本土更好的 AI 芯片的发展，也就是华为芯片，对吗？

<details>
<summary>Original English</summary>

**Speaker A**: the question I'm more curious is that will the ban uh encourage better AI chips in China which is Huawei chips, right?

</details>

**Speaker B**：这绝对是肯定的。我们之前讨论过软件即服务（SaaS）与云服务的对比，我认为 AI 正在朝着云的方向发展，这将支撑中国涌现出各种需要借助云服务来打造可行产品的新型公司，同时也会产生不断增长的推理需求。我们谈论开放云，我们谈论诸如 Claude Code 这样的应用，你会发现推理需求是客观存在的。我认为中国在采用方面还处于早期阶段。你和中国的开发者交流，他们会说我使用的云服务底层实际上是被路由到了西方的算力资源上。随着中国解锁更多的国内 AI 推理算力，诸如此类的用例和需求，最终都将汇聚到华为能制造出多少芯片这个问题上。所以……

<details>
<summary>Original English</summary>

**Speaker B**: It's definitely the case. We talked earlier about this like software as a service versus cloud and I think like AI is going in the cloud direction and this is going to support all sorts of new companies in China that need this cloud in order to build their viable products and there's going to be this growing inference demand. We talk about open cloud, we talk about cloud code, like the inference demand is there. I think China is earlier on the adoption. So you talk to developers in China and they're like I use cloud like this is getting routed to what is western capacity and it's like as China unlocks more domestic AI inference capacity and these use cases like this demand will all funnel into how many chips can Huawei make. So

</details>

**Speaker A**：这种情况会在几个月而不是几年内到来，就像在中国将会出现像 Claude Code 这样的新应用，它们是如此具有赋能作用，以至于人们对它们有着疯狂的需求。因此我预见这一定会发生，在这个层面上黄仁勋说的有些道理，也就是这才是将要驱动本土 AI 发展的动力。

<details>
<summary>Original English</summary>

**Speaker A**: this is coming in months not years like there will be new apps like cloud code that are so enabling in China that people have crazy demand for them. So I see this happening and in this capacity Jensen is somewhat right where it's like that is what's going to drive the local AI

</details>

<!-- chunk 10/12 -->

### 华为芯片与生态瓶颈

**Guest**: ……技术栈的开发。比如当地实验室有华为芯片，他们正为其设计推理功能。在某种程度上，这正在发生，只是一个比例问题，即人们在多大程度上觉得可以接受。

<details>
<summary>Original English</summary>

**Guest**: ...stack to be developed like the local labs have Huawei chips that they're designing inference for. like in some ways it's happening and it's just a ratio of how much and to what extent is okay for people.

</details>

**Interviewer**: 所以真正的瓶颈其实在于华为的产能，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: So the bottleneck is really on the production capacity for Huawei, right?

</details>

**Guest**: 是的。以及在这些芯片上实际运行模型有多容易的生态系统。所以这就类似于冷却期。

<details>
<summary>Original English</summary>

**Guest**: Yeah. And the ecosystem for how easy it is to actually run a model on these chips. So which is like the cool down.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Guest**: 所以我认为我非常看好人工智能需求将持续增长。因此，需求创造了这种需要。

<details>
<summary>Original English</summary>

**Guest**: So I think like I'm very bullish on AI demand continuing to increase. So therefore like demand creates this need.

</details>

### Anthropic CEO的对华态度与中国数据产业

**Interviewer**: Anthropic的CEO Dario Amodei（转录中称Daryl Amade）一直将自己定位为最直言不讳的科技界领袖之一，警告中国人工智能发展带来的国家安全和地缘政治威胁。你怎么看他的这种做法？

<details>
<summary>Original English</summary>

**Interviewer**: Anthropomic CEO Daryl Amade has consistently positioned himself as one of the most vocal tech leaders warning about the national security and geopolitical threats posted by Chinese AI development. How do you see his approach?

</details>

**Guest**: 我觉得稍微有点太激进了。我认为Anthropic在媒体上的部分表态还是很小心地将对中国政府的担忧与对中国独立科学家的担忧区分开来，但在短期内，他对于开源权重模型等带来的风险表现得稍微有点过于激进了。所以我认为，听到他在这方面充当急先锋，可能会让一些人感到反感。

<details>
<summary>Original English</summary>

**Guest**: I think it's a little too aggressive. Like I think that some of anthropic media is pretty careful about separating the concerns from Chinese government and Chinese individual scientists, but it's a little like he's a little too aggressive in the near term about like risks posed by open weight models and so on. So I think it could be a little offputting to people to hear him kind of be the tip of the spear in that regards.

</details>

**Interviewer**: 并且你提到中国在人工智能数据产业方面的弱点比人们意识到的更重要。你能详细谈谈吗？

<details>
<summary>Original English</summary>

**Interviewer**: And you mentioned that the China's weakness in the AI data industry is more important than people realized. Can you elaborate more on that?

</details>

**Guest**: 最令人惊讶的事情之一是，数据产业在中国的发达程度要低得多。所以，当我们身处这股可以称之为“环境热潮”之中时，像Anthropic和OpenAI这样的公司声称他们有数十亿美元的数据预算，用来从外部供应商那里购买（测试或训练）环境。当我们询问中国公司时，他们则表示：“不，我们并没有真正做这些。我们会自己在内部构建一些。”人们可能会指出字节跳动和阿里巴巴规模更大，有能力建立内部数据团队，但很少有人谈论像去外部供应商那里购买数据这种在美国再正常不过的事情。

在美国前沿实验室的策略中，如果你用略带愤世嫉俗的眼光来看待模型训练，那就是：模型在某方面表现不佳，你就去尝试为它购买一些数据，看看这些数据是否能提升评估结果。这是对美国前沿实验室的一种略微刻薄的看法，认为这就是他们做的无聊工作；当然他们也做了很多更令人兴奋的事情。但这种动态似乎并不存在于中国。这看起来是最大的差异。

很明显，OpenAI的研究人员比中国研究人员拥有更多的算力，因此这些中国初创公司里的人研究的问题也不同，也许他们会寻找看起来更高效的解决方案等等。但数据这方面是唯一让我觉得“好吧，这其实没必要不同，但感觉却非常不同”的地方。

人们目前对美国前沿模型的看法是，它们正在变成一种类似知识工作工具的东西。比如作为一名名义上的知识工作者，我现在使用Claude Code和Codex来辅助我绝大部分的工作。人们看到这种情况也正在医疗保健、法律、咨询、金融领域发生，而美国的模型都将朝着这种能力推进。用于这些领域的大量训练数据来自于这些数据公司网络，他们付钱给专业人士来创建这些训练数据。是的，这里有一个包括Scale AI、Mker（可能是Maker）、Surge、Turing等公司的庞大市场。这里有众多公司，而且市场正在推动它们从离岸人工反馈强化学习（RLHF）偏好数据，转向这种非常高技能的劳动产业。这是一个庞大的市场，各个模型实验室为此支付的费用高达数十亿美元。他们这样做是因为它能产生价值，并使模型在这些智能体任务上表现得更好。

我认为现在的问题是：中国实验室是否会为他们自己的智能体打开这个国内市场，人们是否会使用他们的模型来做这些事情？因为正是这种需求，才会让他们能够购买这些非常昂贵的数据。相比之下，如果中国的人工智能研究人员和知识工作者说“我用Claude就行了”，那Claude就更有理由继续在美国深耕这块，而这一切也将全归属于美国的数据产业。所以我跟我那些在实验室里做后训练的朋友聊天时，他们都认为这些数据公司对于在所有这些领域获得渐进式的性能提升非常重要。所以，如果这在中国不存在，你将不得不非常有创意，比如让人工智能研究人员去凭空编造一个诸如制作Excel电子表格这样的金融问题的数据环境。我就是不认为这是一项人工智能研究人员天生适合去做的工作。这和他们所生活的完全是不同的世界。

<details>
<summary>Original English</summary>

**Guest**: One of the most surprising things is that the data industry is much less developed in China. So when we flew this whole environments craze so to say where companies like Enthropic and Open AI are saying that they have billions of dollars of data budget to buy environments from external vendors. We asked the companies and they're like no we don't really have this. We build some in-house. People would point to the likes of Bite Dance and Alibaba being bigger and being able to build internal data teams, but there's very little talk of like you go and buy some data from an external vendor, which is so normal in the US. 

Like the frontier lab playbook, if you take it a little like cynically in training the models is like the model is bad at something, then you go to try to buy some data for it and you see if the data makes the eval go up. And that's like kind of a cynical take on US Frontier Labs is like the boring stuff that they do. they do much more exciting things. But that dynamic doesn't seem to exist in China. That looks like the biggest difference. 

It's like obviously open AI researchers have more compute than Chinese researchers and then therefore these Chinese startups the people work on different problems and maybe it looks like more efficient solutions and so on. But the data one was the only one was like okay this didn't necessarily need to be different and felt very different. 

How people currently view US frontier models is that they're going into this like knowledge work tool. So like as a nominal knowledge worker like I use cloud code and codecs to now mediate the vast majority of my work and people see this happening for healthcare, law, consulting, finance and the US models are all going to push into this capacity and a lot of the training data for this comes through these data company networks where they're giving money to professionals to create this training data. Yeah, there's a whole market of Scaleai, Mker, Surge, Turring. There's a whole plethora of companies here and the market is pushing them away from offshored preference data for RHF into this very high skill labor industry. And this is a like huge it's measured in billions of dollars of how much people are paying for this across each model lab. And they do this because it serves value. and makes the models better at these agentic tasks. 

And I think it's a question of like do the Chinese labs unlock this domestic market for their own agents and people do using their models for this because that demand is what will let them buy this data that's very expensive versus if the Chinese AI researchers and then knowledge workers are like I'm using claude like claude is just has all the more reason to keep doing this in the US and that's all for the US data industry. So like it's I talk to my friends that do post training at labs and like these data companies are like really important to getting this like incremental performance bump on all of these domains and if so if it doesn't exist in China like you're going to have to be very creative to make like an AI researcher is then going to be making up an environment in data of say like a finance problem of like making an Excel spreadsheet. And I just don't think this is a task that an AI researcher is naturally suited to do. It's like a different world than they live in.

</details>

### 中国市场的应用创新与变现

**Interviewer**: 关于中国的需求和商业模式，我还有几个问题。你知道在移动互联网时代，中国公司非常擅长推出新的App和应用程序。大家都说，像美团、微信和阿里巴巴这样的公司彻底改变了我们的日常生活，所以人们的普遍假设是，一旦模型准备就绪，中国在AI应用方面也会再次行动得更快。你预见到这种情况会发生吗？

<details>
<summary>Original English</summary>

**Interviewer**: I have a few more questions about Chinese demand and business model. You know that during the mobile internet era, Chinese companies are so good at launching new apps, applications. Um, you know, people would say companies like Mtoan, WeChat and Alibaba totally changed our daily lives and assumption is that China will move faster this time as well on AI applications once the models are ready. Do you see that coming?

</details>

**Guest**: 我认为在美国和中国，应用领域都会出现惊人的活力。一些观点甚至认为，美国消费者比中国消费者更习惯于添加新的App，并渐渐习惯使用和为其付费。而在中国，他们有这些“超级App（mega apps）”。这就产生了一个问题：这些超级App能否支持同样多样化的新用例？而在美国，你有像Sora这样的东西……

<details>
<summary>Original English</summary>

**Guest**: I think both in the US and China there's going to be incredible dynamism in the applications. I think some arguments are even like the US consumer is more used to adding new apps and then like going through the like getting very used to it and paying for it than in China where they have these mega apps and it's a question of like can the mega app support the same amount of diversity of new use cases where in the US you have things like Sora which

</details>

**Interviewer**: 它成了排名第一的App，几百万人都在尝试使用。它既可能只是一现的昙花，同时也拥有自己的沙盒环境。它可以提供一种边界更明确的体验。

<details>
<summary>Original English</summary>

**Interviewer**: is the number one app and millions of people try it. It's a flop like and it's its own sandbox. it can be a more defined experience.

</details>

**Guest**: 所以我几乎会说，在软件层面，美国更适合这种对新App的动态试错。

<details>
<summary>Original English</summary>

**Guest**: So I would almost say in the software side, the US is more set up for like this dynamic trial of new apps.

</details>

**Interviewer**: 中国的实验室会担心变现的问题吗？

<details>
<summary>Original English</summary>

**Interviewer**: Were Chinese labs worry about monetization at all?

</details>

**Guest**: 他们没有特别强烈地表达这方面的担忧，不过我们也没有主动问起。我也不认为许多前沿人工智能实验室会对变现如此痴迷。OpenAI和Anthropic确实想要进行IPO。

<details>
<summary>Original English</summary>

**Guest**: Not super vocally, but we also didn't ask. I also don't think that many of the like frontier AI labs are that obsessed with monetization. Open AI and Enthropic want to IPO. Yeah.

</details>

**Interviewer**: 但大多数构建前沿AI模型的人的想法只是想构建最好的模型，并且……

<details>
<summary>Original English</summary>

**Interviewer**: But most people building AP AI models are just like I want to build the best model and

</details>

**Guest**: 如果你假定模型会越来越好、非常有用，那么资金就不会是个问题。

<details>
<summary>Original English</summary>

**Guest**: if you assume the model's going to get better like it they're so useful the funding won't be a problem.

</details>

**Interviewer**: 这取决于你去问谁，对吧？如果你去问一位产品经理，他们可能会关心这个问题……

<details>
<summary>Original English</summary>

**Interviewer**: Depends on whom you ask, right? If you ask a product manager probably they're concerned about

</details>

**Guest**: 或者那些试图支持购买更多算力的管理层。

<details>
<summary>Original English</summary>

**Guest**: or the leadership that's trying to support buying more compute.

</details>

### 中美AI实验室的跨国交流

**Interviewer**: 美国的实验室应该更频繁地访问中国的实验室吗？

<details>
<summary>Original English</summary>

**Interviewer**: Should US labs visit China Labs more often?

</details>

**Guest**: 我认为我们会看到一些美国玩家——特别是那些试图围绕开源模型建立经济价值的中小型玩家（无论是微调API还是专业部署等），想要与中国实验室建立关系，因为中国实验室对分享他们的技术和经验持非常开放的态度。在去过中国之后，我们看到，比如我就收到了很多公司的询问，他们问：“你是如何获得权限去参观所有那些实验室的？我们也想去拜访。”你大可以去了解一下美国境内任何一家基于开源模型工作的知名基础设施或训练公司；如果这种趋势继续发展，那将会迎来一个新时代——这些新公司正在学习如何跨越国界相互合作。

我预计会有更多美国公司前往中国，因为目前的签证情况（去中国）要容易得多。比如我就是利用了免签过境的政策，只要你从不同国家出入境，就非常容易办到，基本上人到了就行。然而，如果一名中国的研究人员或工程师去美国旅行，就不得不经历漫长的签证博弈。

因此，我预计将有更多对开源模型感兴趣的美国中型初创公司前往中国，这很可能会在未来几周到几个月内发生。因为这种事情发展得很快，就在2026年的夏天。

<details>
<summary>Original English</summary>

**Guest**: I think we'll see some US especially small and medium players that are trying to build economic value around open models whether it's a fine-tuning API or specialized deployments or so on want to build relationships with Chinese labs because the Chinese labs are so open to sharing their technology and expertise after traveling to China we've seen like I've gotten inbound from a lot of companies they're like how do you get access to all these labs we would go visit and this is a you could look up a known own either infra or training company in the US that works on top of open models where if this evolves it'll be kind of a new era of these new companies learning to work with each other across borders. 

I would expect more US companies to go to China because it's much easier in the visa situation right now. So I traveled on the visa free transit where you enter and exit through different countries and that's super easy to do. pretty much to show up. Whereas like a Chinese researcher, engineer traveling to the US, you have to wait for the visa games. 

So, I expect more US medium-sized startups that are interested in open models to go to China, which is probably going to happen in the coming weeks to months. Like, this stuff happens fast. The summer of 2026.

</details>

**Interviewer**: 很高兴知道这些。你是Lex Fridman播客节目的常客，他最近去了中国。我想他有一个关于搭货车便车的视频在中国互联网上非常火。你和Lex私下里谈论过你的中国之行或者他去中国访问的兴趣吗？

<details>
<summary>Original English</summary>

**Interviewer**: That's good to know. You've been a frequent guest on the podcast show with Lex Friedman. He was in China recently. I think one of his videos catching a truck ride really going viral on Chinese internet. Do you and Lex actually talk privately about your China trip or his interest in visiting China?

</details>

**Guest**: 我们并没有专门做一个类似于“你觉得中国怎么样？”的复盘。我认为我们俩都只是有兴趣亲眼去看看这片庞大的人口——这群深刻影响着我们赖以生存的科技的人群，并且第一手地观察它，因为那是了解它的最好方式……

<details>
<summary>Original English</summary>

**Guest**: We haven't done a postmortem of like what do you think of China? I think both of us are just interested in seeing this large swath of humanity that influences tech that we live with so much and seeing it firsthand because that's the best way to understand

</details>

<!-- chunk 11/12 -->

### 中美人工智能实验室的预测与对比

**Nathan**: 我的意思是，Lex 去世界各地旅行的次数比我多。他本身就去过很多地方旅行，所以我猜，我不能代表他发言，但我猜在一些动机上是相似的。

<details>
<summary>Original English</summary>

**Nathan**: I mean, Lex has done more world traveling than I have. He's done a lot of other world traveling to begin with, so I would guess I mean I can't speak for him, but I would guess that it's similar in some of the motivations.

</details>

**Interviewer**: 是的，很好。嗯，你能给我们一些对未来 12 个月的预测吗？我们会在中国的实验室看到什么，又会在美国的实验室看到什么？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Great. Um, and can you give us some predictions 12 months from now? What are we going to see in the China labs and where are we going to see in the US labs?

</details>

**Nathan**: 我期望发生的一个决定性事件是，将会出现某种新型的智能体（Agentic）产品，它将成为大家都在谈论的话题。我认为 Claude Code 和 CodeEx 依然会存在，但我觉得还会有其他产品出现，无论是来自谷歌还是其他公司打造的新应用。我觉得，在将复杂的智能体工作流应用于工作这个故事上，我们还处于非常早期的阶段。所以这将是一个新事物。不可预测的是，模型就像现在这样继续不断变得更好，还是我们能在像持续学习（continual learning）这样的领域取得幸运的突破？我猜，更有可能的是你会看到大型和小型 AI 实验室的收入都在继续增长。OpenAI、Anthropic 是公众知名的公司，情况还不错。

<details>
<summary>Original English</summary>

**Nathan**: One of the defining things I would expect is that there's going to be some sort of new agentic product that is going to be what everybody is talking about. I think Claude Code and CodeEx will still be around, but I think there will be others whether it's from Google or somebody else that built a new app. Like I think we're so early in the story of complex kind of agentic workflows across your work. So that'll be a new thing. The unpredictable things are do the models just keep getting better as they are or do we have a lucky breakthrough on something like continual learning? I would guess that it's more like you see the revenue of big and small AI labs alike continue to grow. OpenAI, Anthropic are public and okay.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Nathan**: 但更有趣的是这些中型公司，比如 Fireworks、Space 10，还有一些中国的实验室，像月之暗面（Kimi）、智谱（Zhipu）、MiniMax，它们销售代币（tokens）和模型的组合，规模没那么庞大。在销售智能方面，它们也会做得相当不错，因为对此的需求实在太大了。我预计，人们普遍认为的美国和中国前沿模型之间的差距将会拉大。所以，如果人们以前说差距是三个月，以后他们会说是六到九个月，或者一年，但这不会看起来像是中国的实验室已经整合并且放弃了。比如，我们可能依然会有 DeepSeek V5，会有 Kimi K3，会有 GLM-6 以及所有这些模型。所以，12 个月仍然是一个非常短的时间线，在这期间我们看到了需求的快速增长，市场可能仍然会非常疯狂。我们还没有真正做出反应，还没有完全消化这个需求周期。所以感觉可能还是会像这种趋势的延续。然而，如果你问我三到五年的情况，我会说某家主要的中国实验室可能会因为财务问题而倒闭，比如我不知道，MiniMax 或智谱因为某些融资问题倒闭了，而美国市场也有更多的修正等等，我认为这要等到你进入那三到五甚至十年的时间线才会发生。

<details>
<summary>Original English</summary>

**Nathan**: But more interesting is this medium-size companies together, Fireworks, Space 10, and also some of these Chinese labs like Kimi, Zhipu, MiniMax where they sell a mix of tokens and models and aren't as giant. They're also going to be doing pretty well in terms of selling intelligence because there's just so much demand for this. I would expect the accepted gap between the frontier models in the US and China to have widened. So like if people were saying three months, they'll say six to nine months or they'll say a year, but it won't look like the Chinese labs have consolidated and given up. So like we will probably have a DeepSeek V5, we'll have Kimi K3, we'll have GLM6 and all of these things. So like 12 months is still such a short timeline where we're seeing such a rapid rise in demand where it's like the markets are still probably going to be going crazy. Like we haven't reacted, we haven't fully processed this demand cycle. So it'll still probably feel like a continuation of that. Whereas if you ask me like three to five years and be like uh one of the major Chinese labs might have gone under due to finance like I don't know like MiniMax or Zhipu goes under for some financing thing and there's more corrections in the US market and stuff like I think once you get to that three to five to 10 year timeline.

</details>

### 全球 AI 竞赛与个人影响

**Interviewer**: 酷。这次旅行之后，你对全球 AI 竞赛是更乐观了，还是更担忧了？

<details>
<summary>Original English</summary>

**Interviewer**: Cool. After this trip are you more optimistic or more worried about the global AI race?

</details>

**Nathan**: 我觉得我相当中立。我想我对 AI 的担忧主要集中在比如美国公众舆论对 AI 感到反感，以及这可能会如何阻碍进展上。我认为全球 AI 竞赛大致就是我在地缘政治上预期的那种大图景。就好像是美国处于领先地位，而中国想要赶上，在这其中存在一些微妙的因素，比如芯片的销售量，以及这最终会对生态系统产生什么影响。我认为我的主要作用只是能为这件事带来更多人性的成分，尽我所能让它不至于对双方的人来说成为一种非常极端的境地。让那些正在构建和使用这项技术、但在最高层决策上几乎没有发言权的人，能够有更多的了解。我能做一点微小的贡献，让双方能更好地相互理解。

<details>
<summary>Original English</summary>

**Nathan**: I think I'm pretty neutral. I think most of my worries on AI are like very centered on like US opinion being sour on AI and how that could hurt progress. I think the global AI race is roughly what I would expected geopolitically is this biggest picture. It's like the US is ahead and the Chinese wants to catch up and there's this nuance in terms of how much chips are being sold and what that pin ends up doing to the ecosystem. I think it's mostly just the benefit to be able to bring more humanity to this and like do what I can to make it less of a very extreme circumstance for people on both sides. So people building and using the technology that have very little say on what the highest level decisions are. It's like I could do a small part to make that more understood for both sides.

</details>

**Interviewer**: 好的。非常感谢你，Nathan。我想这就是我所有的问题了。你还有什么想补充的吗？有什么我没问到的问题吗？

<details>
<summary>Original English</summary>

**Interviewer**: All right. Thanks so much Nathan. I think all those are my questions. Anything else you want to add? Any question I didn't ask?

</details>

**Nathan**: 没有了。感谢你邀请我。希望不久的将来我能进行第二次中国之行。还有很多东西值得去看。

<details>
<summary>Original English</summary>

**Nathan**: No. Thanks for having me. I'll hopefully sometime soon go for a second trip in China. There's plenty more to see.

</details>

**Interviewer**: 是的，我们很期待在你下次旅行后进行第二次采访。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, we'll love to have the second interview after your next trip.

</details>

**Nathan**: 谢谢。

<details>
<summary>Original English</summary>

**Nathan**: Thank you.

</details>

### AI2 的使命与运作

**Interviewer**: 好的。非常感谢。对了，跟我们说说你们（AI2）是做什么的吧。

<details>
<summary>Original English</summary>

**Interviewer**: All right. Thank you so much. Yeah, tell us about what you guys do.

</details>

**Nathan**: 好的，AI2 从事各种开源 AI 的研发工作。我觉得它在历史上一直偏向学术，随着时间推移，它越来越走向这种以开发成果（artifact）为导向的开发模式，即你构建模型、代码库和数据集，供社区的其他人在此基础上进行构建。所以我想 MoE 以及这些开源语言模型一直是其中最受欢迎的，但也有比如针对多模态 MoE 的 Earth 以及其他一些项目。此外，AI2 一直以来都以其与 AI 文献的整合而闻名，我认为这方面的应用就是 Semantic Scholar，它被视为搜索学术文献时 Google Scholar 的替代品。而且这个团队已经演变成致力于为科学构建 AI 智能体的团队，这是一个品牌，他们正在构建工具协助人们撰写和理解科学文献。所以我认为，在核心层面，它最深层的文化是非常科学的，并且具有这种社区价值观，也就是为科学界做出许多纯粹的贡献。

<details>
<summary>Original English</summary>

**Nathan**: So, AI2 does all sorts of kind of open- source AI research and development. I think it's historically been fairly academic and over time it's been moving more into this artifact um defined development where you're building models and code bases and data sets that the rest of the community can build on. So I think mo and these open language models has been the most popular one but there's also like mommo the multimodal mo earth and other things and then AI2 has historically been very well known for its integration with AI literature so I think the application there has been semantic scholar which is kind of seen as alternative to Google Scholar for searching academic literature and this team has evolved into building AI agents for science so it's this a brand where they're building tools to assist people in building and understanding the scientific literatur literature. So I think at his core it's c like deepest culture is so scientific and like has this community value of building a lot of just like net good for the scientific community

</details>

**Nathan**: 这一点在那些非常注重细节和关怀的论文中得到了体现，我觉得有很多种不同的方式——你想往哪个方向发展都可以，它体现在很多不同的方面。在 AI2 工作最棒的事情之一就是，你会非常专注于尝试构建被各种研究人员使用的东西。当你作为一名学者去旅行时，你会发现所有这些人都在使用 OLMo 并知道 AI2，这就像是一件持久且伟大的事情。当有实习生或学生研究员出去，进入学术界以及所有其他研究机构时，他们会去传播这种科学价值，这是 AI2 提供的一项很棒的服务。

<details>
<summary>Original English</summary>

**Nathan**: which is really great and that comes through in these papers that are very detail- oriented and caring and I think there's just like so many different ways which way do you want to go there's so many different ways that this comes through and it's the best one of the best things about working at I too is you just like you get so focused on trying to build things that various researchers use when you travel as an academic and you're like all these people are building on OLO and know of AI too and it's just kind of like a lasting thing that is great when there's interns or student researchers and they go out into that academic community and all these other research institutions to kind of spread this scientific value which is a great service that AI2 does.

</details>

**Interviewer**: 是的。你们现在有多少人？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. How many people do you have right now?

</details>

**Nathan**: 大概有 200 人左右。

<details>
<summary>Original English</summary>

**Nathan**: Probably about 200 people.

</details>

**Interviewer**: 哇哦。那是相当多的人了。那么他们大部分是研究人员，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: Oh wow. That's a lot. So most of them are researchers right?

</details>

**Nathan**: 我估计大概有一半的人才是从事传统 AI 研究的技术工程人员，还有工程团队负责支持我们的集群以及我们的一些产品。

<details>
<summary>Original English</summary>

**Nathan**: I would guess probably half of the talent is technical engineering on like the traditional AI research and then there's engineering teams that help support our clusters and um some of our products.

</details>

**Interviewer**: 像你们这样的非政府组织（NGO）实验室和硅谷的其他实验室有什么不同？

<details>
<summary>Original English</summary>

**Interviewer**: How is like a NGO lab different from other labs in Silicon Valley?

</details>

**Nathan**: AI2 是一个完全的非营利组织，这意味着它的大部分资金来自慈善事业。名字里的 Allen 来自 Paul Allen，他是微软的联合创始人之一。此外，我们还有大笔的资助，比如来自美国国家科学基金会（NSF）的。因此，它全都是非营利性资金，实际上并不销售任何产品。它只是把所做的一切免费提供给人们去学习。

<details>
<summary>Original English</summary>

**Nathan**: So AI2 is a full nonprofit which means most of its money comes from philanthropies. So the Allen is on the door which is from Paul Allen one of the co-founders of Microsoft and then also has large grants from u for example from the NSF. So, it's all nonprofit funding and doesn't really sell any products. It just gives everything it makes away for free to for people to learn from.

</details>

**Interviewer**: 哇。所以，我猜你们会有更多的研究自由。

<details>
<summary>Original English</summary>

**Interviewer**: Wow. So, you guys have more research freedom, I guess.

</details>

**Nathan**: 是的。我认为在从封闭实验室到学术界的这道光谱上，就资源而言，我们处于中间位置；在自由度上也是，比如我们有更多的资源，同时我们也感受到要构建出真正优秀的模型的压力。所以这确实稍微压制了一点自由度，但比起那些向着 AGI 冲刺的前沿实验室，这种限制要少得多。不过，如果你去一个真正的学术机构，你会看到他们有一种多样性和思想的火花，这在一家只想着如何支付账单的公司里是得不到的。

<details>
<summary>Original English</summary>

**Nathan**: Yeah. So, I think that on the spectrum of closed lab to academia in terms of resources, it sits in the middle in terms of freedom, which is like we have more resources and we feel pressure to build models that are actually good. So it like does suppress the freedom a little bit but much less than a frontier lab that is like racing towards AGI. But if you go to a true academic institution, you'll see that they have a diversity and kind of intellectual spark that you like won't get at a company just based on the needs of paying the bills.

</details>

### 西雅图与硅谷的氛围差异

**Interviewer**: 西雅图的氛围与硅谷的氛围有什么不同？

<details>
<summary>Original English</summary>

**Interviewer**: How is Seattle vibe different from the Silicon Valley vibe?

</details>

**Nathan**: 它平静多了。比如，这里并没有总是有一群人聚在一起办活动。我个人倒是希望西雅图有更多的人这样做。比如亚马逊、微软等所有的科技公司里都有大型的技术人才中心，希望能有更多这种交流，但现状就是如此。你也无法改变。在某些方面，我认为这是一个更适合安顿下来组建家庭的地方，因为它没那么拥挤，生活节奏也没那么紧张，而且在讨论 AI 时也没有那么狂热。比如，我不是在每一场对话中都会聊到 AI，而在湾区，AI 感觉就像是当下唯一的话题，我也能理解为什么会这样。因为我自己也很投入其中。

<details>
<summary>Original English</summary>

**Nathan**: It's so much calmer. Like there's not events all the time with various people meeting up. I personally wish that more people in Seattle. like there's major tech talent hubs at Amazon, Microsoft, and all the tech companies would have more of this, but it's what it is. You can't fight it. In some ways, I think it's a better place to like settle down and have a family because it's like a bit more spread out and it's a bit less intense and how bright everything is in terms of talking about AI. Like, I don't have AI in every conversation where in the Bay Area, AI feels like it's the only conversation right now, which I understand why. Like, I'm bought in as well.

</details>

**Interviewer**: 但你经常去湾区。

<details>
<summary>Original English</summary>

**Interviewer**: But you visited the Bay Area a lot.

</details>

**Nathan**: 我经常去。我大概一年会去三到八次。

<details>
<summary>Original English</summary>

**Nathan**: I go regularly. I say I go like three to eight times a year.

</details>

**Interviewer**: 好的。

<details>
<summary>Original English</summary>

**Interviewer**: Okay.

</details>

**Nathan**: 我在加州大学伯克利分校上的学，所以我在湾区生活了大概七八年。

<details>
<summary>Original English</summary>

**Nathan**: I went to UC Berkeley, so I lived in the Bay Area for like seven or eight years.

</details>

**Interviewer**: 然后你必须回去，为了跟上到底在发生什么。在湾区，你可看不到这样的风景。一个非常美丽的湖。它叫什么名字？

<details>
<summary>Original English</summary>

**Interviewer**: And then you have to go back to stay in touch with what's actually happening. In the Bay Area, you don't have the view like this. A very beautiful lake. What's the name of it?

</details>

**Nathan**: 嗯，联合湖（Lake Union）。

<details>
<summary>Original English</summary>

**Nathan**: Um, Lake Union.

</details>

**Interviewer**: 这绝对是我梦想中的办公室。

<details>
<summary>Original English</summary>

**Interviewer**: Definitely my dreaming office for sure.

</details>

**Nathan**: 是的。

<details>
<summary>Original English</summary>

**Nathan**: Yeah.

</details>

**Interviewer**: 是的。那么当你去中国访问时，你觉得那里的办公室怎么样，

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. So when you visit China, how do you think the office there,

</details>

<!-- chunk 12/12 -->

### 展厅文化与科技公司办公室

**Speaker A**: 那边的AI实验室办公室，

<details>
<summary>Original English</summary>

**Speaker A**: the AI lab office there,

</details>

**Nathan**: 他们没有这种风景，但它们也是科技公司的办公室，在这一点上它们非常相似。就像我走进去，感觉就像身处一家科技公司，我这辈子去过很多科技办公室，感觉就是这样。展厅文化是不一样的。

<details>
<summary>Original English</summary>

**Nathan**: they don't have this view, but they're also tech company offices where it's like they're pretty similar in that regards where like I go in them and it feels like I'm in a tech company and I've been into a lot of tech offices in my life and it's like okay. The showroom culture is different.

</details>

**Speaker A**: 哦，对，展厅在中国很独特。这是一个非常独特的中国特色，我认为很多人第一次来都必须参观一下，然后就会觉得，好吧，原来是这么回事。

<details>
<summary>Original English</summary>

**Speaker A**: Oh yeah, showroom unique in China. That is a very unique China thing that a lot of people just I think have to visit for their first time and then like okay this is a thing.

</details>

**Speaker A**: 太酷了，太酷了。非常感谢Nathan接待我们。

<details>
<summary>Original English</summary>

**Speaker A**: Cool. Cool. Thank you so much Nathan for having us.

</details>

**Nathan**: 是的，感谢你们来参加办公室参观之旅。再见。

<details>
<summary>Original English</summary>

**Nathan**: Yeah thanks for coming to the office tour. Bye.

</details>