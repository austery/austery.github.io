---
author: 硅谷101
date: '2026-07-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ULi-TCF2cQE
speaker: 硅谷101
tags:
  - compute-resource-gap
  - open-source-ecosystem
  - geopolitics
  - model-competition
  - frontier-model-fixation
title: 中国开源模型实力评估与全球AI生态的视角
summary: 文章探讨了当前中国开源模型在算力、人才和生态构建方面的现状。核心观点包括国内面临的计算资源劣势，以及跨地域合作（如中美）中存在的壁垒与融合趋势。同时，文章也分析了美国最先进模型与中国模型的差距变化，并展望了未来开源社区中小型模型的价值及其对前沿大模型的追逐心态的影响。
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

### 中国开源模型实力评估

**主持人**: 兰伯特，谁拥有最好的中国开源模型？如果非要我说一个，就目前而言……

<details>
<summary>Original English</summary>

**Host**: Lambert, who has the best China open source model? If you put a gun to my head, I would say as of today,

</details>

**兰伯特**: ……中国实验室今天仍然面临的最大劣势是算力。Meta 或 OpenAI 拥有的 GPU 比所有这些中国公司加起来还要多。

<details>
<summary>Original English</summary>

**Lambert**: ……the biggest disadvantage that the Chinese lab still face today, yeah, it's compute. Meta or OpenAI have more GPUs than all of these like Chinese companies combined.

</details>

**主持人**: 那么，像华为芯片这样的国产加速器表现如何？

<details>
<summary>Original English</summary>

**Host**: So, how good are domestic accelerators such as Huawei chips?

</details>

**兰伯特**: 所有这些公司都差不多是，如果你能给我华为芯片，我们也许就能获得更多客户。

<details>
<summary>Original English</summary>

**Lambert**: All of those companies are like, if you can give me Huawei chips, we will like maybe get more customers.

</details>

**主持人**: Anthropic 的 CEO Daryl Amade……他在近期关于开源权重模型所带来风险的言论上有点过于激进了。你认为美国最先进的模型领先中国模型多少个月？这个差距是会缩小还是扩大？

<details>
<summary>Original English</summary>

**Host**: Anthropic CEO Daryl Amade, he's a little too aggressive in the near term about risks posed by open weight models. How many months do you think US SOTA models are ahead of the Chinese models? And for that gap, is it going to become narrower or wider?

</details>

**主持人**: Hugging Face 分析。接下来。Nathan Lambert。你好，Nathan。欢迎来到 Valley 101。

<details>
<summary>Original English</summary>

**Host**: Hugging face. Analysis. Fore. Next. Nathan Lambert. Hello, Nathan. Welcome to Valley 101.

</details>

**兰伯特**: 嘿，谢谢邀请。

<details>
<summary>Original English</summary>

**Lambert**: Hey, thanks for having me.

</details>

**主持人**: 你刚从中国回来，期间你实际上访问了许多中国领先的AI实验室。跟我们多聊聊那次旅行吧。

<details>
<summary>Original English</summary>

**Host**: You just came back from a trip to China during which you actually visited many of China's leading AI labs. Tell us more about that trip.

</details>

**兰伯特**: 回来后人们总是问我，你的主要收获是什么？我觉得AI领域，谁在构建模型之类的，大家都挺清楚的。所以，并没有太多让人超级震惊的事情。你不会说，哦，我有个劲爆的观点。对我来说，作为一个报道这些模型的人，这次旅行的意义在于认识那些正在做这件事的人，并深入了解他们为什么这么做。我觉得今年我学到了很多，美国有很多人只会说他们为什么可能这么做，而能获得第一手信息非常好。我期望未来继续报道开源模型，试用这些模型，这是一个有趣的生态系统。美国有很多兴趣和公司正在围绕真正的开源模型智能栈进行构建，这为各种各样的人提供了价值。而很多模型是在中国和这些历史悠久的科技社区中构建的，它们之间过去并没有太多交流与合作。像Meta和Google这样的地方有传统政策，如果你去中国旅行，你的笔记本电脑会自动报废。这就像一堵墙，人们无法轻易合作，但它们正在变得融合。我对这个非常感兴趣。我认为从某些方面来说，这些模型如此有竞争力是令人惊讶的，但当你更多地了解那里的人才等情况时，这又在某种程度上变得正常了。我个人对AI充满热情的一个很大原因是，我认为在未来几年，它会带来很多风险，特别是社会风险以及人们如何获取信息，当然地缘政治上这也是一个引人关注的话题。所以，在人们之间搭建桥梁，将实际从事这项工作的人人性化，是很有用的，因为他们并不做出很多被列为政治或极端的决定。建立这些联系非常有益，因为这是一个朝着各种目标前进的共同体，无论你称之为AGI还是其他什么目标。所以，我很高兴能见到这些幕后的人。

<details>
<summary>Original English</summary>

**Lambert**: People always ask me now that I've been back. It's like what are your big takeaways? And I feel like AI is fairly well known and who is building models and things. So, there's not that many things that are like super shocking. You're like, oh, I have this hot take. The trip for me as somebody who covers these models, it's to get to know the people who are doing it and get to pick up on the nuance of why are they doing this? I think I'm just learning a lot this year and there's a lot of people in the US that will just say why they might be doing this and just to get the first is very nice. I expect to keep covering open models in the future and trying these models is an interesting ecosystem that's set up that there's a lot of interest in the US and companies that are building around real open model intelligence stack which is serving value for all sorts of people and then a lot of the models are getting built in China and these historic tech communities like have not intermingled a lot and how they work. So there's traditional policies at places like Meta and Google where if you travel to China, your laptop automatically breaks itself. And there's like been a wall where people can't easily work together, but they're becoming integrated. And I'm just very interested in it. I think it's surprising in some ways that these models are so competitive, but then when you learn more about all the talent there and things, it's like it becomes somewhat normalized. And I personally like a lot of the reason that I'm motivated by AI is that I would think that in the next couple years it's like a lot of risks particularly like just social risks and how people are informed and then also geopolitically it's obviously a topic of interest. So just building bridges across people and humanizing the people that are actually doing this because they don't make a lot of the decisions that are listed as political or extreme in any way and just like building these connections is really useful because it is one community that is kind of moving forward towards these various goals whether you call it AGI or whatever you want to say the goal is. So I'm just like very happy to meet the humans behind this.

</details>

**主持人**: 好的。很棒。你去了多少天，去了哪些城市？

<details>
<summary>Original English</summary>

**Host**: Yeah. Great. And how many days did you go and which cities?

</details>

**兰伯特**: 好的。我想大概是六个或七个晚上，主要在北京和杭州。在北京住了三四个晚上，我们住在奥林匹克中心附近。所以可以去鸟巢体育场跑步什么的。就是找个酒店住下，但大多数公司都在清华大学附近，那里有一整个AI初创公司集群，非常有趣。感觉很像湾区，你会觉得，哦，我可以步行穿梭于该地区所有领先的AI公司之间，什么都不用做。非常有湾区的感觉。然后我们也去了杭州待了几个晚上，那是阿里巴巴所在地。我想Deep Seek也在那里。我们没去Deep Seek的办公室。我们和一些相关人员聊了聊，也参观了阿里巴巴，感觉很好。这是我第一次来中国，很高兴能见到他们。

<details>
<summary>Original English</summary>

**Lambert**: Yeah. So I think it was about six or seven nights and it was primarily in Beijing and Hangzhou. So it was like three or four nights in Beijing which we were staying right near the Olympic Center. So like go for a jog in this the bird's nest stadium and all these things. It's just like where you find a hotel but then most of the companies are by Tsinghua University and there's this whole cluster of AI startups there which is really interesting. It feels a lot like the Bay Area where you're like oh I can just walk between all the leading AI companies of the region and like you don't have to do anything. It's like a very Bay Area feeling. And then we also went to Hangzhou for a few nights, which is where Alibaba is. And I think Deep Seek is. We didn't go to the Deep Seek office. We talked to some people and we did visit Alibaba and it's just great. It's my first time in China and nice to see them.

</details>

**主持人**: 那么，这次你访问了哪些实验室或公司？

<details>
<summary>Original English</summary>

**Host**: So, which labs or companies did you visit this time?

</details>

**兰伯特**: 好的，我尽量多列一些。我们还访问了一些机器人公司，这方面我关注得不多，没有写太多。就语言模型而言，我们参观了——嗯，我去了两个不同的阿里巴巴办公室。我在北京下飞机后，立刻就去见了……Moonshot 和 Zai，还有和我一起写 Interconnects 的 Florian。我们去了美团，他们有语言模型项目。我们还参观了清华大学，以及北京的小米园区。然后我们去杭州时，参观了那里的阿里巴巴园区，见到了 Antling 团队，还有 Model Scope，它也隶属于阿里巴巴。这次旅行是一个团体活动，主要是围绕一个叫做“Sale”的组织进行的，这个组织由一群撰写AI相关内容的Substack作者组成，就像我的朋友们创建的一个平台，用来在AI媒体和活动领域做一些有趣的事情。所以，大部分行程都是围绕这个安排的。团队其他人在上海，据我所知，他们肯定和 MiniMax 聊了，可能也和 Stepfun 聊了。所以，真的有很多名字。我认为有些是显而易见的，比如 DeepSeek 是最神秘的一个，字节跳动也是，你去访问他们，所有公司都在谈论 DeepSeek，把它当作他们那种神秘的领导者，而字节跳动则是那个拥有大量资源、让所有人都担心的封闭AI实验室。豆包聊天机器人是主导产品。你在那里很快就能感受到这些，因为每个人都在谈论。

<details>
<summary>Original English</summary>

**Lambert**: Yeah, I'll try to list many of them. We visited also a bunch of robotics companies which I didn't focus on as much as writing but for language models we visited well I went to two different Alibaba offices. I got off the plane in Beijing and immediately went to meet... Moonshot as well Zai and then Florian who writes Interconnects with me. We went to Meituan which has their language modeling effort and then we also visited Tsinghua University and we visited the Xiaomi campus in Beijing and then when we went to Hangzhou we visited the Alibaba campus there the Antling team and also Model Scope which is also affiliated with Alibaba and then this was a group trip part of mostly organized around this like "Sale" which is a bunch of Substackers that write about AI which is like my friends making a vehicle to do interesting things in AI media and events. So, it was mostly organized around this and then the rest of the group in Shanghai talked to I think definitely MiniMax and maybe Stepfun as well. So, there's really a lot of the names. I think there's obvious missions like DeepSeek is the most secretive one and ByteDance is also like you visit them and they're like all the companies talk about DeepSeek as their like kind of mysterious leader and then ByteDance is like oh the one closed AI lab that has a ton of resources that everybody's like worried about. the Doubao chatbot is the dominant thing. You pick up on these things pretty quickly when you're there because everybody talks about it.

</details>

**主持人**: 那么，在你的Substack文章里，你说你带着谦卑回来了。这是什么意思？

<details>
<summary>Original English</summary>

**Host**: So in your Substack article, you said you returned with humility. What does it mean?

</details>

**兰伯特**: 是的。我觉得作为一个美国科学家，我从未真正期望过自己会对中国科技生态系统或全球层面的中美互动有什么发言权。我描述为，我知道自己了解不多，离开后我意识到，我还有太多东西要看。我看到了中国的这两个城市，当时我在一次繁忙的工作旅行中，感觉就像被一辆面包车传送来传送去。我们去了很棒的晚餐，在北京看到了一些可爱的街区和一些老建筑等等，但我觉得我对中国了解得太少了。要真正对某件事有即时的直觉和感悟，你多少需要更接近全栈式的知识和理解，比如这里的人本能会是什么？一个中国研究人员的本能会是什么？作为一个美国人，我需要花一辈子才能完全理解这些，比如教育体系有何不同。我们去清华大学时，他们会谈到，他们会承认这样一种说法，即中国研究人员在“从零到一”这种科学方面做得没那么好，虽然这是个有点随意的术语。这到底意味着什么？但他们自己会提起这个，这部分与人们的训练方式以及人才如何通过比美国更广泛的国内网络层层筛选有关。这些都是人们会谈论的事情，亲眼看到它们很有用。今年我读了《Brace New China》和《Apple in China》这两本关于美国科技生态系统与中国互动的精彩书籍。但这仍然是一个非常有限的视角。所以这就是为什么我离开时有点预料到，我会觉得我并没有完全理解我所离开的一切，但我仍然觉得我还有很多要学。

<details>
<summary>Original English</summary>

**Lambert**: Yeah. So I feel like as an American scientist, I never really expected to have anything to say about the Chinese tech ecosystem or US-China interactions at a global level. I described it as like I knew I didn't know a lot and I left and I was like I still have so much to see. It's like I saw these two cities in China and I was on like a busy work trip and feeling like you get teleported around in a van. We went to some great dinners and we saw some cute neighborhoods in Beijing and some of the older buildings and stuff, but it's like I feel like I don't know so much about China. And to like truly have immediate instincts and intuitions about something, you kind of need some more closer to full stack knowledge and appreciation for like what would a person's instinct here be? like what would a Chinese researcher's instinct be? And it's like it would take a lifetime for me to fully understand that as an American as things like how is the education system difference. We went to like Tsinghua and they would talk about like we want to they would acknowledge the reputation where it's like Chinese researchers haven't been as good at this like zero to one style science which is kind of an arbitrary term. It's like what does that actually mean? But they would bring it up and part of this is in like how people are trained and how the talent gets funneled through different layers from a much broader domestic network than in the US. It's like these are things that people would talk about and actually seeing them is useful. This year I read Breakneck and Apple in China is these two wonderful books on the US tech ecosystems interactions with China. But that's still like a very limited view. So that's why I'm like okay I kind of expected this when I left that I would be like I don't really understand everything I left but I still feel like I have more to learn.

</details>

**主持人**: 你见的是高层人士，还是中层的AI研究员或工程师级别的人？你认为这些对话真的有帮助吗？

<details>
<summary>Original English</summary>

**Host**: Were you meeting with the senior level people or the middle level AI researcher or engineer level people? Do you think those conversations actually helpful?

</details>

**兰伯特**: 是的，我们的目标是与更多研究人员会面，进行对话。我们也试图接触领导层，尤其是在初创公司。所以，似乎主要是从与研究人员交谈开始，我们也和一些高管聊过，比如阿里巴巴的，或者我们交谈过的某些人，他们在公司内部非常知名，并且直接与创始人对接。但我认为……

<details>
<summary>Original English</summary>

**Lambert**: Yeah, so we were targeting meeting with more researchers just to get a dialogue. We also targeted trying to get leadership especially at startups. So it seems like mostly starting to talking to researchers. We talked to some executives say like Alibaba or some of these people that we talk to are very well known within companies and interface directly with the founders. But I think...

</details>

<!-- chunk 2/12 -->

### 正式拜访与私下交流的差异

**Speaker A**: 当你进行正式访问时，很大程度上是在向在场的人表示尊重。但归根结底，这些领导者更擅长媒体应对，有时反而说得更少，为了遵循公司口径而压制了细节。

<details>
<summary>Original English</summary>

**Speaker A**: When you're going to do like a formal visit, it's a lot of showing respect to the people that are there. But at the end of the day, like the leaders are more media trained and sometimes will tell you less and that kind of suppresses nuance to stay on the company line.

</details>

**Speaker B**: 所以我觉得两者兼有。大公司似乎更愿意展示一些他们的资深云技术人才，但又不会透露太多。有些对话是私下进行的。我不知道，这不是最好的答案，但情况很复杂。

<details>
<summary>Original English</summary>

**Speaker B**: So I think it was some of both. The bigger companies I think were more like open to show some of their senior cloud people without saying like without giving too much away. I think some of the conversations were off the record. I don't know. It's not the best answer, but it's a mix.

</details>

**Speaker A**: 是啊，尤其是有公关人员在旁边的时候。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, especially with the coms people around.

</details>

**Speaker B**: 对，大多数场合都有公关人员在房间里。最好的对话往往是这样的：我宣布我来了，你在微信上，我给人发消息，然后你就和某个普通研究员一起去喝波波茶，不在公司办公室里，你就问：“你在做什么项目？你在忙什么？”这时候就没有那种“我在办公室，我经理坐在旁边，公关人员也坐在旁边”的伪装。这种交流更有趣，但在这次行程中更少见。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, like most of these have comms handlers in the room. Like some of the best conversations were I announce that I'm here. You're I'm on WeChat. I message people and then you like go get Bobo with a random researcher, not on the corporate office, and you're just like, "What are you working on? Like, what are you doing?" And then it's like, okay, there's not the veneer of like I'm at the office, my manager is sitting next to me, the comm's people are sitting next to me. So those are almost more fun but more rare of the trip.

</details>

**Speaker A**: 确实。那你主要问他们什么问题？

<details>
<summary>Original English</summary>

**Speaker A**: Definitely. Um so what kind of questions did you mostly ask them?

</details>

### 提问与回答：从模型动机到未来影响

**Speaker B**: 问题分布很广。我一开始问的是对他们来说比较容易回答的问题，比如“你们为什么要发布这些模型？为什么你们要自己构建模型，而不是直接用DeepSeek的模型？”

<details>
<summary>Original English</summary>

**Speaker B**: There's a distribution. So I think that I was interested in to start with something that's probably pretty accessible to them which is like why are you releasing these models? Like why do you build your model? Why don't you just use Deepseek's model?

</details>

**Speaker A**: 很多公司都非常务实。他们的想法是：我们需要AI来服务用户，我们想拥有全栈能力，所以我们要自己构建。他们并不像美国那样，把构建AI模型看作是一件超级昂贵、不可能完成的事情，带有一种“前沿实验室”的光环，只限于少数精英。但在中国，这就是为什么我们想去拜访Muan——它是我最喜欢的、拥有大模型的普通中国科技公司之一。我们就想，去看看他们做得怎么样。他们的回答是：是的，我们需要这个来服务我们的智能体产品。所以我们构建模型，因为产品需要它。至于是不是开源，无所谓，我们也会发布出来，获得一些反馈。他们对这种开放科学的理念非常务实。

<details>
<summary>Original English</summary>

**Speaker A**: A lot of these companies are very practical and it's like we need AI to serve our users and we want to own the full stack and therefore we're going to build it. and they're much more daunted about building AI models being this like super expensive impossible thing where it's kind of an allure in the US of like being a frontier lab. It's like restricted to an elite few but it's like all the companies that's why it was like we wanted to go visit Muan. It's one of our favorite like random Chinese tech companies to have big models. So we're like just go see how they're doing. They're like yeah we need this to serve our agentic products. So we build the model we need it for products. It doesn't matter if it's open we'll release it as well and get some feedback. and they're very practical about this open science sort of idea.

</details>

**Speaker B**: 然后这就会引出不同的问题，比如“你们目前的瓶颈是什么？”——这可能会很快在算力问题上碰壁，但很多人会说“华为芯片在推理方面很好，我们用华为做推理，但不太用于训练。”很多人都会这么说。我们团队里也有人想讨论AI的未来，比如“你怎么看待AI对劳动市场和经济的影响？你作为科学家，是否觉得有责任去思考这些影响？”在这方面，我们在中国看到，研究人员不太愿意分享很多观点。部分原因是公司环境，但我认为也是因为那里的环境更加结构化，他们在教育中被鼓励谈论的是“我构建了这个东西”，而像美国那种播客生态，研究人员通过保持曝光度和试图影响公司方向而获得回报，在中国要少得多。他们更务实，我认为在我的写作中，有时会把这与谦逊混为一谈——你可以是一个谦逊的人，但也可能你只是不习惯被问到某些问题。

<details>
<summary>Original English</summary>

**Speaker B**: And this would lead into different things like what are your current bottlenecks which can obviously quickly be a dead end on compute or but a lot of them are like Huawei chips are good for inference. We use Huawei for inference but not really for training. So like a lot of people would say things like this. Also in our group people would want to talk about like what is the coming future of AI? So like what do you view on how it's going to impact labor markets and economics and like do you feel like you have a responsibility as a scientist to understand like think about these impacts and that's where we saw in China that researchers are much less inclined to share a lot of views on this. Some of this is the corporate environment, but also I think it's just like a environment that's much more structured and what they're encouraged to talk about in in their education, which is like I built the thing and there's much less of this like podcast ecosystem in in China where there's researchers that are like rewarded for being visible and trying to sway the direction of the company. It's like a bit more practical-minded, which I think I sometimes in my writing got over overlapped with the humility, whereas like you can be a humble person, but also you could be in an environment where you're just not used to being asked certain questions.

</details>

**Speaker A**: 很好。我们来谈谈你拜访的一些公司。在你看来，它们之间有多大不同？我们先谈谈Moonshot，好吗？

<details>
<summary>Original English</summary>

**Speaker A**: Cool. Let's talk about some of the companies you visited. In your opinion, how different were they from one another? Let's talk about Moonshot first, shall we?

</details>

### 公司文化差异：从Moonshot到其他

**Speaker B**: 好的。我认为当你走进它们时，确实能感受到非常不同的氛围。我觉得Kimmy（Moonshot的产品）是一家这样的公司：这些人看起来非常亲密，他们做这件事纯粹是为了构建酷东西的兴奋感，他们在构建酷东西的同时也在建立业务，但他们也只是说“我们要构建这些模型，我们自己用”。他们看起来非常紧密，你走进办公室时能直觉地感受到。你会想，好吧，这些人真的很有凝聚力，他们很团结，他们就像一起把生命投入其中。我把Kimmy描述为我们拜访过的“氛围最好的公司”，他们看起来很开心，走在自己的路上，不那么公司化。相比之下，如果你去阿里巴巴，那显然是一家巨大的科技公司，非常公司化。蚂蚁集团的Antling团队也有点那种感觉，因为他们也是一家巨大的科技公司。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, I think they do have pretty distinct feelings when you could go into them. I think Kimmy was one where it's like These people seem so close and they're just in it for kind of the thrill of building a cool thing and they're building a business alongside building this cool thing, but they're also just like we're going to build these models. We use them ourselves and they seem very close in a way that's like you just pick up intuitively when you like go to the office. You're like, okay, these people are really bonded and they're tight and they're just like spend their lives together building this. I describe Kimmy as like the best vibes company of the one that we visited which is just like they seem like they're happy and they're going on their path and it's not very corporate in a way where if you go to obviously Alibaba it's like this is a huge tech company it's very corporate the ant group Antling team has some of that because they're also a huge tech company.

</details>

**Speaker A**: 但即使是一些中型公司，比如Zai，也非常以AGI为导向，他们很有自豪感，但至少在我们接触中，没有Kimmy和Moonshot那种魅力。当然，这可能只是随机的一天，我和这些人只共进了几个小时的午餐。你不能据此判断一家公司的轨迹。但这仍然很有趣，因为人是会表达的，你可以从中了解一些东西。

<details>
<summary>Original English</summary>

**Speaker A**: but even in some of the middle it's like Zai was very AGI forwards and they were like had a lot of pride but at least in the interactions we had it wasn't as much of this like charm that Kimmy and Moonshot have. And some of this might just be like random daytoday like I've met these people for a few hours over lunch. You can't conclude a company's trajectory based off this. But it's also interesting because like people are expressive and you can learn things from that.

</details>

**Speaker B**: Moonshot有一篇论文叫“Attention Residues”，其中一位作者是一名17岁的高中生。你知道吗？那篇论文被埃隆·马斯克在X上转发，说“来自Kim的令人印象深刻的工作”。这个高中生现在在中国非常有名。这说明了Moonshot的什么文化？

<details>
<summary>Original English</summary>

**Speaker B**: There was a paper from Moonshot named attention residues with one of its authors being a 17-year-old high school student. You know about that one? I think that paper was reposted by Elon Musk on X saying impressive work from Kim. So this high school student got very famous in China now. So what does that tell you about the culture at Moonshot?

</details>

### 年轻人才与中美差异

**Speaker A**: 这不完全是Moonshot特有的现象，但那里的天才非常年轻。这些公司都在努力扩大在西方媒体的影响力，很多研究员都在X上。我认识其中几个人。公司里有些人既做产品也做公关，比如Kimmy的Crystal，还有Zi的Lou。我见过Lou，我不知道我发音对不对，但她大概20岁，还是个学生。她说“嗨”，我心想“哇”。这些人太年轻了。我们遇到的一位Xiai研究员，李，也是个博士生，同时是小米的首席研究员之一。美国也有这样的人，他们非常有动力最终进入前沿实验室。但在中国，你一个接一个地遇到这些超级年轻的研究员，深度嵌入实验室，感觉这有点结构性优势——他们吸收人才的速度比其他实验室快得多，而且对此更加开放。

<details>
<summary>Original English</summary>

**Speaker A**: It's like less of a moonshot specific thing, but the this the talent there is very young. These companies are all on a push to have more of a western media footprint and there a lot of these researchers are on X and it's like I knew a few of the people. I think that it's like people that do a mix of product and comms at the company. One is like Crystal, I think at Kimmy, and then Lou at Zi. And it's like I met Lou, I don't know if I'm pronouncing her name exactly right, but she's like 20 and she's still a student. She's like, "Hi." I'm like, "Wow." It's like these people are so young. And then one of the Xiai researchers we met, um, Li is like also a PhD student and like one of the lead researchers at Xiaomi. There are some people like this in the US which are just extremely motivated to end up at a frontier lab. But it just seems like we're getting so many when you meet one after another in China of these super young researchers deeply embedded in this labs. It felt like a bit of a structural just like they absorb this talent much more quickly than other labs and are more open about it.

</details>

**Speaker B**: 这太疯狂了。我三十出头，这些人这么年轻。我感觉自己在生活中还算年轻，但……

<details>
<summary>Original English</summary>

**Speaker B**: It's wild. I mean like I'm in my early 30s like these people are so young. It's like I feel young in my life and it's like

</details>

**Speaker A**: 看到这些很酷。但美国的情况不同吗？

<details>
<summary>Original English</summary>

**Speaker A**: it's cool to see. But is it different here in the US?

</details>

**Speaker B**: 我觉得是的。比如，美国实验室也有年轻人才。

<details>
<summary>Original English</summary>

**Speaker B**: I think so. Like I I think like young talents here in US labs.

</details>

**Speaker A**: 对。所以某种程度上，AI2的秘诀在于，华盛顿大学在你身后，我们有很多博士生，他们是Mo和其他重大项目核心成员，同时也是在读学生。但这种开放程度在其他实验室至少没那么灵活。我认识少数在实验室工作的博士生，但他们是美国最顶尖的。而在中国，感觉学术界（尤其是在像Chinua这样的地方）和附近的初创公司之间的人才交融更加刻意，重叠度也高得多。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So something that defines AI2 a bit, it's like secret sauce is that like Udub is behind you and we have a lot of PhD students that have been like core to mo and core to other major projects who are concurrent students. But that sort of open door is at least like less fluid at some of the other labs. Like I know a handful of PhD students that work at labs, but these are like the absolute best of the best in the US. Where in China it feels like the intermingling of academia, especially at a place like Chinua and these startups nearby is much more intentional and much higher overlap for the talent.

</details>

**Speaker B**: 为什么这很重要？

<details>
<summary>Original English</summary>

**Speaker B**: Why does that matter?

</details>

**Speaker A**: 学生年轻，有饥饿感，生活中没有其他牵挂。我今年要结婚了，在考虑家庭。我30岁了，有别的事情。但学生们会说“这是我生命中的技术”，他们会一直工作，吸收所有上下文。当你构建语言模型时，比如我从事后训练工作，你需要知道预训练团队在做什么，你需要了解你流程的多个阶段，然后找出瓶颈并解决它。

<details>
<summary>Original English</summary>

**Speaker A**: Students are young, they're hungry, they have nothing else going they have much less going on in their life. Like I'm think I'm getting married this year, thinking about family. Like I'm 30. I have other things but students are like this is the technology of my life. I'm just going to work all the time and absorb all the context. And when you build a language model like I work in post-training, you need to know what the pre-training team is doing. You need to know the multiple stages of your recipe and then you need to figure out like what is the bottleneck and go address it. So

</details>

<!-- chunk 3/12 -->

### 技术知识的基础与公司文化差异

**Speaker A**: 你需要掌握一个非常庞大的固定技术知识体系。我认为，如果这是你生活中最重要的事情，而且你没有太多干扰，那么把所有这些知识装进大脑就会更容易。一位研究人员告诉我们，新学生没有过去深度学习成功经验的先验知识。他们不会去研究不同的架构或其他东西。他们只是想知道当前最先进的技术是什么，然后让它变得更好。这是一种他们可以采用的简单方法。一些中国的研究人员告诉我们这一点。我们说，是的，我们就是这么做的。

<details>
<summary>Original English</summary>

**Speaker A**: There's a really big fixed context of technical knowledge that you need. And I think it's just like if it's the biggest thing in your life and you don't have a lot of distractions, it's just easier to put all of this into your brain. One of the researchers told us like, oh yes, new students don't have priors for what used to work in deep learning. They're not looking at a different architecture or anything. They're just like, I want to know what the current state-of-the-art is and make it better. And it's kind of like a simple approach that they can do. Some of the researchers in China told us this. We're like, yeah, we that's what we're doing.

</details>

**Speaker B**: 我明白了。我们来谈谈Jup吧。去那里的旅行怎么样？

<details>
<summary>Original English</summary>

**Speaker B**: I see. I see. Let's talk about Jup. How was the trip there?

</details>

**Speaker A**: 很有趣。我觉得你会喜欢。我了解到的一点是，中国公司有一种展厅文化，当有访客时，他们会展示公司的发展历史。JIPU的展厅里，每一块展板都有一些不同的AGI功能，比如AGI加载中之类的。他们的理念是，我们离目标还有42%，这是来自《银河系漫游指南》的梗。你一眼就能注意到，你会觉得“哇”。但另一方面，我觉得我没有像了解Kimmy的人那样深入了解他们。不过他们对自己的工作非常自豪，他们也非常成功。我认为有些事情，比如上市以及被美国列入实体清单，让他们一下子就跃升到了真正的大公司地位，这是Kimmy还没有达到的水平。

<details>
<summary>Original English</summary>

**Speaker A**: It was fun. I think you like. So part of the thing that I learned is that Chinese companies have like a showroom culture where when you have visitors you like show the history of your company and JIPU's showroom is all like every panel has some different like AGI feature so it's like AGI loading or it's like their thing is that AG we're like 42% of the way here which is from the Hitchhiker's Guide to the Galaxy reference and you just like immediately notice it you're like whoa and but at the other time there like I felt like It was I didn't get to know them quite as much as the Kimmy people and but they're very proud of their work and they're they're very successful and I think it's some things of like being public and being randomly entity listed by the US. They're just like immediately vaulted to a wa you're like a real big company status type of thing that Kimmy hasn't quite hit that level of.

</details>

**Speaker B**: 但在我看来，它们非常相似。当我观察这些模型时，它们有不同的权衡取舍。看看这种差异是否会进一步分化它们的文化，将会很有趣。如果Kimmy保持私有化更长时间，而Jipu保持上市状态……

<details>
<summary>Original English</summary>

**Speaker B**: But in my mind they're so similar. It's like when I look at the models, they have different tradeoffs and it'll be interesting to see if that kind of diverges the cultures a bit more. If Kimmy stays private longer and Jipu is staying public,

</details>

**Speaker A**: 在二级市场上市可能有时会带来不同，通常会获得更多关注。

<details>
<summary>Original English</summary>

**Speaker A**: Being listed on the secondary market probably sometimes make a difference just normally get more attention.

</details>

**Speaker B**: 是的。所以，JIPU和Miniax现在已经上市了，这很好，因为它们可以在短期内筹集资金。但如果它们需要更多资金来训练模型呢？那就更难了，因为你不能轻易进行二次公开发行。目前情况还不明朗，而且现在市场对那些上市公司的回报非常丰厚。所以投资需求很大，但这种情况可能会转变。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, JIPU and Miniax are public now and it's good because they can raise short term, but it's like what if they need more capital to raise models? It's harder to do like you don't really do like a second public offering. It's kind of unclear and right now the markets are really rewarding any company that's public. So there's so much demand to invest in it but like that could turn.

</details>

**Speaker A**: 所以现在这样挺好。

<details>
<summary>Original English</summary>

**Speaker A**: So like right now it's good.

</details>

**Speaker B**: 我不知道。我不做那些决定。

<details>
<summary>Original English</summary>

**Speaker B**: I don't know. I don't make those decisions.

</details>

**Speaker A**: 但你可以从两方面来论证。

<details>
<summary>Original English</summary>

**Speaker A**: But you can make arguments both ways.

</details>

### API请求趋势与开源模型市场

**Speaker B**: 今年早些时候，在Open Call热潮期间，Open Router上针对Kimmy和Japur的API请求量激增。你认为这种趋势会持续下去吗？

<details>
<summary>Original English</summary>

**Speaker B**: Earlier this year there was a surge of API requests on open router for Kimmy as well as Japur uh during the open call sensation. Do you think that trend will continue?

</details>

**Speaker A**: 是的，我们看到多种市场正在涌现。有Cloud Code和Codeex，这是最高端的。我将其描述为知识工作工具，但本质上，无论代理在哪里工作，都会有相应价格点的代理。开源模型的优点在于价格非常低，使得实验更容易进行。这是一个很自然的地方，很多人会在这些已知性能强大且价格更低的模型上进行实验，同时这些模型还拥有成熟的品牌。这就是整个Deep Sea、Japu、Kimmy、Quen这类模型所处的领域。就我个人而言，我认为OpenClaw本身这个名字有点像是潮流，但它所代表的代理类型将会持续存在。所以现在Hermes代理要流行得多，但即使是这个也会来了又走，还会有另一个。但关键是，这种你可以运行、并且在Open Router上托管的模型上运行成本不高的代理类型，是很有趣的。Open Router本身在实际推理市场中所占的份额并不大。所以在美国，像Fireworks和Together这样的平台要大得多。它们都开始分享一些每天处理的token数量数据。但Open Router更偏向社区导向。所以当你想到那些关注开源模型的人时，那就是他们思考的地方，这显然是一个优势。我认为公司们正在非常积极地利用这一点，因为当他们的模型在上面流行起来时，这就像是一种很好的联合品牌推广，并且会自我强化。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, we're seeing kind of multiple markets emerge. You have the cloud code and codeex which is like the top end. I describe it as like knowledge work tools, but essentially there's going to be agents at price points for wherever they work. The thing that makes open models nice is that the price point is so low that the experimentation is much more doable. It's kind of a natural place where a lot of people will experiment on these models that are known to be strong and a step down in price while still having these established brands which is where this whole Deep Sea Japu Kimmy Quen kind of circle lands. Personally, I think like OpenClaw itself is a bit of a a fad where the name but the type of agent it represents will be sticking. So like right now like Hermes agent is far more popular but it's like even this will like come and go and there will be another but it's just like this type of agent that you can run it and it is not super expensive on these like hosted models on open router is is interesting. Open router itself is not a huge proportion of the actual inference market. So like in the US like fireworks and together are much bigger. They both started sharing some numbers on the amount of tokens they're doing every day. But open router is like more of like community oriented. So when you think about people that are following open models, that's like that's where they think and that obviously has an advantage and I think companies are very actively leaning into it because when their models surge on it, they use it's like good co-branding and it feeds into itself.

</details>

### 中国公司的AI策略：从零构建与生态系统

**Speaker B**: 我们来谈谈你去Muan和Xiaomi的旅行。

<details>
<summary>Original English</summary>

**Speaker B**: And let's talk about your trip to Muan and Xiaomi.

</details>

**Speaker A**: 是的，这很有趣，因为正如我们讨论过的，情况非常不同。中国几乎就像Uber和苹果在开发自己的开源模型，但即使在美国，他们也没有这样做。然而，为什么在中国会是这种情况呢？当你问Muan，或者Mtoan和Xiaomi的企业定位时，他们会说，我们将拥有可供使用的代理。你可以想象在Maidtoan，一个代理可以为用户做一些事情，比如找出要请求的行程或要订购的东西，它可以做到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it's uh interesting because as we discussed the story is very different. China is almost like Uber and Apple are developing their own open-source models but even in the US they are not. Why is this the case in China though? When you ask Muan when you like Mtoan and Xiaomi's corporate position would be like we're going to have agents that are used you could think of it in Maidtoan is like an agent could do something for a user to figure out the ride to request or thing to order like it can do this.

</details>

**Speaker B**: 而美国消费者的第一反应会是，我直接去拿一个API密钥就行了。

<details>
<summary>Original English</summary>

**Speaker B**: And the first instinct in the US consumer would be I'm just going to get an API key.

</details>

**Speaker A**: 完全正确。但在中国，情况更像是，我们可以构建这个，而且会更便宜。我们有算力，有人才。为什么我们不直接尝试构建这个呢？

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. But in China, it's very much like we can build this and this will be cheaper. Like we have compute, we have talent. Why don't we just try to build this?

</details>

**Speaker B**: 这并非Mwtoan独有，但有几家公司是这样的：我们构建这些通用模型。

<details>
<summary>Original English</summary>

**Speaker B**: And this isn't specific to Mwtoan, but there's a few companies that are like we build these general models.

</details>

**Speaker A**: 我们对它们的使用并不仅限于此，但我们可以发布通用模型，因为会有更多人使用它。然后他们所做的就是微调这个模型，以创建专门的代理和专门的模型，并在内部用于他们的服务。Mron就是一个很好的例子，这些专门的模型他们不会发布，但他们希望能在自己的应用中使用它们。你可以想象一下Xiai的情况，它可以为汽车中的功能提供支持。我猜Xiaomi的工作方式类似于Tesla或其他什么，它与云端通信，有所有这些接口，你不太清楚具体会是什么样子，但AI将与所有数字技术交织在一起。是的，我认为Xiaomi是另一个很好的例子，说明大公司试图包揽一切。它正在做机器人模型、机器人硬件。它真的试图自己做每一件事。

<details>
<summary>Original English</summary>

**Speaker A**: And that's not where like our use of them ends, but we can release the general model because more people will use it. And then what they do is they like fine-tune this to make specialized agents and specialized models which they use for their services internally. And Mron's a good example where it's like those specialized models they don't release but they hope to use them in their apps and you can imagine this with Xiai where it's like it could power features in the car and I'm guessing like Xiaomi works like a Tesla or something where it communicates with the cloud and there's all these interfaces and you don't really know what this is be but AI is going to be intermingled with like all digital technologies. Yeah, I think Xiaomi is another good example of big corp is trying to do everything. It is doing like and robotics models, robotics hardwares. It is really like trying to do every single thing itself.

</details>

**Speaker B**: 是的，Xiai的模型也相当新。他们在2025年4月到6月发布了7B的原始Mimo模型，然后在12月发布了Flash V2模型，这个模型非常受欢迎，最近又发布了2.5版本。人们需要很长时间才能意识到这些模型会不断涌现。看到一个全新的实验室从零开始，并且他们从Deep Seek和Lui那里挖来了Fuji（我不记得她的名字了），这绝对令人惊讶。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's like Xiai's models are pretty new too. They released a like 7B their original Mimo model in April to June of 2025 and then come December when they had their flash V2 model which was very popular and then I think 2.5 was recently. It takes a long time for people to realize that these models are going to keep coming and like it's definitely surprising to see a new lab come from scratch and they hired I don't remember her first name but like Fuji from Deep Seek and Lui. Yeah.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 而且他们似乎有望成为中国最好的模型构建者之一。在美国，大多数人仍然只知道Deep Seek、Quen、Kimmy和Zi。有些人知道Minia，有些人可能不知道。

<details>
<summary>Original English</summary>

**Speaker B**: And they seem on track to be like one of the best model builders from China. People in the US are mostly still at like Deep Seek, um, Quen, Kimmy, and Zi. Some know Minia, some probably don't.

</details>

**Speaker A**: 这个列表很长，但在我参观了Xiai之后，我预计他们会继续保持非常务实的态度。他们这样做是合理的。他们过去已经完成了许多令人难以置信的事情。构建一个AI模型似乎比他们构建的一些汽车和其他东西还要容易。

<details>
<summary>Original English</summary>

**Speaker A**: And it's like it's such a big list, but I expect having visited Xiai, like I expect them to continue like very nononsense. It makes sense for them to do this. They've done so many incredible things in the past. It's like building an AI model almost seems easier than building some of the cars and stuff that they have built.

</details>

**Speaker B**: 我认为对于Muan来说，他们还投资了Moonshot的最新一轮融资，这表明M20在AI上押下了重注。中国公司往往拥有这种庞大的生态系统。他们喜欢超级应用。他们喜欢生态系统。他们喜欢自己从零开始构建一切。你认为这是在AI时代正确的做法吗？

<details>
<summary>Original English</summary>

**Speaker B**: I think for Muan they also invested in Moonshot's latest fundraising which indicates M20 is betting big on AI. Chinese companies just tend to have this massive ecosystem. They love the super app. They love the ecosystem. They love to build everything from scratch themselves. Do you think that's the right approach to go during the AI era?

</details>

**Speaker A**: 值得一试。所以我认为AI，因为它资源密集，本质上会使非常大的公司受益，以及那些能够进入这个飞轮的公司：我们拥有大量资源，AI让我们的产品更好，我们从中获得更多回报，我们可以持续投资，这样的公司将会胜出。我认为在美国很明显可以看到Google正在获胜。Open AI和Anthropic会没事的。Nvidia显然也是如此，所有处于这个反馈循环中的公司都会表现得非常好。然后看看这在中国如何运作也很有趣。我认为蚂蚁集团也在这条路上，他们正在构建自己的模型，并且他们看到自己的平台正在扩展，比如现在正在扩展到健康领域，而且他们……

<details>
<summary>Original English</summary>

**Speaker A**: It's worth to like try your hand at it. So I think AI because it's so resource intensive, it by its nature will benefit very large companies and companies that can get onto this flywheel of like we have a lot of resources. AI makes our products better. We get more returns on those. We can keep investing will win so much. I think in the US it's really obvious to see like Google is winning. Open AI and Enthropic will be fine. Like Nvidia obviously like all these companies that are in this feedback loop are going to be so good. And then it's interesting to see how this works in China. And I think like Ant Group is along this way where they're building their models and they see how their platform spreads like right now it's spreading into health and they

</details>

<!-- chunk 4/12 -->

### 超级应用与科技所有权心态

**Speaker A**: 他们之前已经讨论过很多次了，他们肯定也会在那里使用他们的模型。对我来说，我觉得这其实很有道理。但当你从一个西方观察者的角度看，你会想，为什么蚂蚁金服（Antling）会存在？但他们没有意识到，当你使用支付宝（Alipe）时，背后存在着一个广阔的服务领域。所以，我认为对于这些拥有巨大业务版图的公司来说，这确实是有道理的。但我担心这会抑制一些竞争。问题是，像 Kimmy's、MiniMaxes 和 Zis 这样的小公司，如何融入这个被如此庞大的应用主导的生态系统？我记得是哪家公司来着，他们告诉我们，他们建了一个智能体来导航字节跳动的一个应用，然后字节跳动就封杀了他们，因为他们无法获取数据。小公司和大公司之间正在出现一些接口，小公司正试图找到自己的利基市场。我觉得月之暗面（Moonshot AI）处于中间位置，从我个人的角度来看，我无法很好地判断它到底是一家多大的科技公司，它会被整合浪潮吞没，还是说在语言模型上的投入会变得过于巨大，我真的不知道。但我对人工智能作为一门生意相当看好。所以我觉得大多数早期公司都会过得不错，它们能卖出很多代币。它们出售的是智能，而市场对此会有巨大的需求。

<details>
<summary>Original English</summary>

**Speaker A**: talked about this a lot and they will surely also use their models there and it's like for them I think this actually makes a lot of sense but when you look at a western observer you're like why is antling a thing but they don't realize the like broad service area that exists when you're using this alipe thing. So, it's like I think for these companies with very large footprints, it actually does make sense. I worry that it suppresses some of this competition. So, it's like how did the smaller Kimmy's, Minia Maxes, and Zis like fit into this ecosystem where such big apps exist? I think like I forget which one of the companies, but they were telling us how they like built an agent to navigate one of Bite Dance's apps and then Bite Dance banned them because they couldn't take the data. And it's like there's interfaces emerging between the small and the bigger companies where the small companies are trying to find their niche. And I feel like mtoan's in the middle where I don't have a good grasp from my perspective like how big of a tech company it is and is like is it going to get swallowed by consolidation or is the spend going to be too much on the language models where I don't really know but I'm pretty bullish on AI as a business. So I feel like most of these companies that are early are going to be okay and sell they sell a lot of tokens. They sell intelligence and there's going to be a lot of demand for it.

</details>

**Speaker B**: 你写道，中国公司有一种“技术所有权心态”。你能解释一下吗？

<details>
<summary>Original English</summary>

**Speaker B**: You wrote that Chinese companies have a technology ownership mentality. Can you explain that a little bit?

</details>

**Speaker A**: 这又回到了超级应用的理念。他们就是认为，自己可以构建东西，并把它做得更好；如果成功了，他们就会投入更多资金，让它变得更高效，并根据自己的使用场景进行调优。这正是中国许多本土产业随着时间的推移成长为世界最大产业的方式。他们倾向于自己构建，而不是购买，只要有可能，这样他们就能掌控长期的发展轨迹。Break Neck 的 Dan Wong 说过，中国的资本主义比美国更激烈，因为他们考虑得更长远，思考什么能给他们带来最好的利润率、提供产品的能力、击败竞争对手。如果你依赖别人的服务，你就无法击败对手；如果你处于高度竞争的环境中，你就必须把一切都做到最好，并且全部自己来做。这就是我所说的“所有权心态”，只要这还不是一个不可能实现的成本项。我认为，他们每年可能花费5亿到数十亿美元来制造这些模型，这是一笔巨款，但对于这些实验室来说并非不可能。如果能力进步持续下去，市场最终很可能会整合。能力与投资是对数关系，投入越多，模型就越智能，但回报是递减的。这是一个有趣的时期。我记得我采访过月之暗面的 Richard，他说，他们花了六个月时间组建团队来构建这些大模型，这是因为科技领域已经有现成的人才，他们只是把团队调过来做这件事。

<details>
<summary>Original English</summary>

**Speaker A**: This goes to some of the like super app ideas and they just see that they can build things and make it better and if they succeed they'll put more money into it and keep making it more efficient and they'll tune it to their use cases. And this is like how the many domestic industries in China have grown over time to be some of the largest in the world. this is how it's kind of like they want to build rather than buy if at all possible so they can kind of own the long-term trajectory. It's like a very I think it's like Dan Wong of Break Neck said that like China's capitalism is more intense in the US because it's like they're thinking of even longer term of what gives them the best margins and the ability to provide products and beat competitors and like you don't beat somebody if you're relying on their service and if you're hyper competitive you have to do it all the best and do it all yourself. So that's why I think of it as like this ownership mentality of where it's not currently an impossible line item. I would say that they're probably spending 500 million to billions a year to make these models which is a substantial amount of money but not impossible for these labs. It seems likely that the market will consolidate eventually if progress on capabilities keeps going up. It's like capabilities is like log of investment where it's like you have diminishing returns but if you invest more get smarter but it's an interesting time where it's like I remember I interviewed Richard from Mantling and he was like yeah it took us six months to set up this team to build these large models that's because there's all this talent in tech already and they just like move the teams to do this.

</details>

**Speaker B**: 我们现在处于一个阶段，我不知道他们会坚持多久，但就目前而言，这还挺有意思的。

<details>
<summary>Original English</summary>

**Speaker B**: We're in the phase of like I don't know how long they will keep doing it but for now it's like kind of a fun thing.

</details>

### 通义千问与阿里巴巴的模型策略

**Speaker A**: 我们来谈谈你拜访的其他公司吧。比如通义千问（Quen）和阿里巴巴，这是一家大公司。它和 OneShot 以及其他较小的实验室不同，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Let's talk about like some other of the companies you visited. So, and Quinn and Alibaba, um, it's a big corp. It's different from OneShot and other smaller labs, right?

</details>

**Speaker B**: 是的。我认为通义千问通过持续发布这些性能出色、覆盖各种参数规模的小模型，赢得了开源AI社区的人心。他们早在 Llama 4 和 Llama Faded 之前就开始这么做了，但真正大放异彩是在 Meta 暂停、Llama 4 出现的同一时期。他们自己也清楚这一点。我们问过他们，他们思考的是开发者会用什么。他们希望继续构建开发者使用并赖以发展的模型。但当你审视通义千问时，你会发现他们已经有一段时间没有发布他们最大的模型了。通义千问 Plus 和通义千问 Max 一直是闭源的。这很大程度上是阿里巴巴云在发声，就像在美国，你会看到谷歌云疯狂的支出和收益一样。在中国，阿里巴巴是这方面的默认选择，他们自己也清楚。所以他们不会发布一个模型，他们可能会告诉我们他们不会发布，因为没人会用，但另一方面，他们也可以说，看，你可以用这个赚很多钱。我认为AI领域确实有很多钱可赚，但最有趣的是听到不同的人谈论他们是如何有意地打造这些小模型的。这并非偶然，也许一开始是“哦，让我们试试别人也在做的事”，但他们现在已经形成了一套非常精良的配方，专门打造1B、10B、30B这些非常受欢迎的模型，这是有意为之的。听到他们承认“是的，我们就是这么做的，我们明白这很耗时，发布模型很难，需要在生态系统中做大量工作”，这感觉很好。我认为他们感受到了那种压力：我们可以构建更多模型，但每构建一个模型，我们就必须支持它，必须去对接 BLM，必须去对接开放生态系统中的所有公司。而且建模团队仍然很小，他们没有办法外包这项工作，构建模型的人仍然要非常贴近地做所有事。谨慎有两个方面：一是发布太多模型，二是他们没有发布最大的模型，因为他们想通过云服务来变现。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, I think Quinn has won the hearts and minds of open source AI by releasing these small models consistently with incredible performance at all these sizes. They kind of were doing this before Llama 4 and before Llama Faded, but they like really hit their stride right around the same time as Llama 4 happened in Meta Paused. And they know this. So we asked them, it's like they think about things that developers will use. They want to keep building models that developers use and thrive on, but it's like when you look at Quen, they haven't released their biggest models for a while. So it's like Quen Plus and Quen Max have been closed source. And this is very much like the cloud side of Alibaba talking where just like the US like you see Google Cloud's crazy expenditures and crazy earnings. It's like Alibaba is the default in China for that to happen and they know this. So like they're not going to release a model like they might tell us they might not release it because no one will use it but also it's like I'm going to be like look you can make a lot of money on this and I think there's a lot of money to be made in AI but I think the most interesting thing is hearing various people talk about them being intentional about these small models and it's like not an accident maybe it was at the beginning or like oh let's try to do this thing somebody else is doing but they have a very refined recipe of these 1 to 10 to 30B models that are very popular and that's intentional and it's kind of nice to just like hear how they like they're like yes we do this we understand it's a time sync so it's hard to release models it takes a lot of work in the ecosystem and I think they felt that stress of like we could build more models but if we build a model we have to support it we have to go to BLM we have to go to all these companies in the open ecosystem and like the modeling team is still pretty small and it's like they don't have a way to like outsource that work it's somebody build somebody very close to building the model still does There's the two ends of caution is like you can release too many models and also like they haven't been releasing the biggest models because they want to monetize them in the cloud.

</details>

### AI投入：是SaaS还是云服务？

**Speaker A**: 这次中国之行要探讨的问题之一就是，AI投资到底更像是一种SaaS（软件即服务）模式，还是更接近云服务支出？因为无论这是老生常谈还是事实，美国的一种观点是，中国不在这些服务上花钱，比如Slack的同类产品规模要小得多，人们可能更倾向于在公司内部重建最小化的软件，或者下载一些东西，而不太愿意为软件支付按人头、按座位的月度费用。但所有这些公司确实都运行在云上，比如阿里巴巴就有很大的云业务，很多现代软件都需要通过云来提供。我认为中国会逐渐转变观念，将AI支出视为云服务支出。可能不会像美国那样高昂，但他们会将其视为实现他们想要的技术所必需的支出。

<details>
<summary>Original English</summary>

**Speaker A**: Part of going into China for this trip, one of the questions was like is AI investment kind of like a a SAS like this software as a service thing or closer to a cloud spend, right? Because one of the whether or not it's a trope or actually true is that the views in the US is that China doesn't spend on these these services where it's like the Slack equivalent is much smaller and people will maybe just like rebuild minimal software in house or download something and much less willing to pay this like per head per seat monthly cost on software. But all these companies do run on the cloud like Alibaba has a large business and like a lot of modern software you need via the cloud. I think that China will shift to be more of viewing that AI spend is like this cloud spend. It might not be as exorbitant as the spend in the US, but they'll view it as needed spend to make the technology that they want to make.

</details>

**Speaker B**: 所以，因此，这些云服务会存在。

<details>
<summary>Original English</summary>

**Speaker B**: So therefore, it's like these clouds will exist.

</details>

**Speaker A**: 这很有意思，因为当你到达上海机场，或者乘坐高铁去杭州时，你会看到阿里巴巴云的广告横幅。我走进北京，第一眼看到的就是“阿里巴巴云计划”之类的广告。你知道，就是那种“好吧，我到了”的感觉。

<details>
<summary>Original English</summary>

**Speaker A**: It's so interesting because when you arrive at the Shanghai airport or you take the highspeed train to Ho, you will see the Alibaba cloud like a commercial banner like I walked into Beijing and the first thing I saw was like Alibaba cloud plan something. you know like okay here here I am.

</details>

**Speaker B**: 我认为阿里巴巴云和AWS的一个区别在于，AWS的Bedrock实际上同时承载了每一个大模型、他们自己的模型以及小模型，但中国的云服务只承载他们自己的模型。这是一个很大的区别。而且我认为，美国的新兴云市场，有更多的人在转售别人的模型作为代币，或者转售算力，这是美国市场很大的一部分。你可以说出很多公司的名字，比如CoreWeave、Nebius。还有Together、Fireworks、Lambda，未来还会有更多。我们之前聊过Open Router，但我在中国不知道有哪家是它们的对等公司。

<details>
<summary>Original English</summary>

**Speaker B**: I think one difference between Alibaba cloud and AWS is that actually bedrock carry every single big model and their own model and smaller models at the same time but for China cloud they only carry their own models. That's a big difference. And I think that this Neocloud market in the US where there's just like a lot more people reselling other people's models as tokens or reselling compute is like a huge part of the US market. You could name so many companies. It's like Corweave, Nebius.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: Together、Fireworks、Lambda，未来还会有更多。我们聊过Open Router，但我在中国不知道有哪家是它们的对等公司。

<details>
<summary>Original English</summary>

**Speaker B**: Together, Fireworks, Lambda, like there's going to be way more. We talked about Open Router and like I don't know any of the equivalents of those in China.

</details>

**Speaker A**: 我觉得没有。所以，这些公司很大程度上被视为得到了英伟达的支持。英伟达喜欢优先考虑生态系统的多样性，因为对他们来说，收入不集中在少数几家公司身上是更好的。而且，这种动态在中国似乎并不相同。

<details>
<summary>Original English</summary>

**Speaker A**: I don't think. So that's a those companies are largely looked at as being supported by Nvidia in a lot of ways. Like Nvidia likes to prioritize the diversity of the ecosystem because it's better for them to not have most of the revenue be from opening eye like for those few companies and I it seems like that dynamic is not the same.

</details>

**Speaker B**: 是的，这一点很有意思，因为中国缺少了这一层。他们没有相应的基础设施或优化能力。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that one is interesting because you're missing this layer in China. they don't have the infrastructure or the optimization

</details>

<!-- chunk 5/12 -->

### 中国AI公司的垂直化合作与商业模式

**Speaker A**: 因为你看点赞数。所以我们现在看到的一个趋势是，Cursor 采用了 Kimmy 模型，然后在 Fireworks 的 RL 沙盒训练环境中进行了后训练，并通过 Fireworks 提供服务。这是一个非常有趣的多方合作，旨在构建一个非常强大的模型和产品，在中国，这可能必须更加垂直化才能实现同样的目标。可能中国公司就是希望一切都内部化。

<details>
<summary>Original English</summary>

**Speaker A**: because you look at the likes. So what a trend we're seeing now is like cursor took the Kimmy model and they postrained it within the fireworks like RL sandbox training environment and serve it with fireworks and like that's a really interesting multi-party collaboration to build a like a very strong model and product which might have to be like more verticalized in China to get the same thing done. probably like Chinese companies just want to have everything in house.

</details>

**Speaker B**: 是的。这与所有权和整合的理念相悖，因为要支持一个在这些中间层运营的公司，你必须接受将重要的事情外包出去，无论是GPU托管还是推理，因为你想要专注于其他事情。这看起来更像是一种西方的创业风格，而不是其他。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. It goes against the like the ownership and the integration where it's like in order to support a company that operates in these middle layers, you have to be okay with like offloading a important thing whether it's GPU hosting or inference because you want to focus on something else and that just seems like a more western startup style of things than otherwise.

</details>

**Speaker A**: 是的。我确实认为中国的很多模型实验室会比中国那些更大、更老牌的科技公司更愿意尝试不同的东西，因为像 Kimmy 知道 Cursor 在训练他们的模型，他们会去和 Cursor 之类的人谈。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. I do think a lot of the model labs in China are going to be more willing to try different things than the bigger older tech companies in China because like Kimmy knows cursor trains their model like they will go talk to cursor and stuff like this

</details>

**Speaker B**: 嗯，还有由 Kafuli 创立的 01.ai。他们现在经历了一次重大转型，转向了完全的 2B 商业模式。你认为在AI时代，中国2B市场的未来在哪里？

<details>
<summary>Original English</summary>

**Speaker B**: and um 01.ai AI founded by Kafuli. They now experienced a major transition to a total like 2B kind of business model. Where do you see the future for China's 2B market during the AI era?

</details>

**Speaker A**: 这又回到了这些关系能否建立起来的问题。所以我认为他们很多都在想，他们能否打入这种全球性的企业软件市场。我觉得，对我来说，很难在国内下注它是否会赢。我认为，是的，你可以把AI专业知识带到另一家公司内部，这对那些AI专业知识较少的公司会非常有价值，但问题在于，你是否愿意接受这种——如果你依赖外部合作伙伴来做这件事，你就会失去所有权。就像美国最新的趋势是“前部署工程师”，这个流行词是 FTEE。这很引人注目，他们大量招聘等等，这在美国会发生，但这是否是一种可行的方法，让你能够走进一家公司的大门，并真正受到他们的欢迎？这非常有趣。他们会尝试这个，我认为如果它奏效，成为AI时代第一个重新尝试它的人显然会非常有用，但我不知道。就像抛硬币一样，这完全取决于这种我无法完全理解的中国文化和商业环境。

<details>
<summary>Original English</summary>

**Speaker A**: It goes back to if these relationships can kind of be formed. So I think a lot of them are wondering if they can hit the kind of use this global to business software market. I feel like I like it's so hard for me to make a bet domestically whether or not it'll win. I think that like yes, you can take AI expertise and build it within another company and it'll be very valuable for the company that had less AI expertise, but it's like whether or not this willingness to like you're losing ownership if you're relying on an external partner to do this. It's like the latest trend in the US is like forward deployed engineers is this buzz word FTEEs. It's like opening eyes, hiring a ton and stuff like this where it's like going to happen in the US, but it's like is that going to be a like viable thing where you can go through the front door of a company and actually get welcomed to them? It's very interesting. It's like they're going to try this and I think that like if it works, being the first one to retry it in the AI era is going to obviously be so useful, but I'm like I have no idea. like I could flip a coin like it depends entirely on kind of this like Chinese culture the business that I can't fully understand.

</details>

**Speaker B**: 是的。但是你，你见了谁？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. But did you who whom did you meet with for

</details>

**Speaker A**: 我，我们见了。

<details>
<summary>Original English</summary>

**Speaker A**: I we met with

</details>

**Speaker B**: 直接见了 Kyouli？是的。是的。是的。谈话怎么样？

<details>
<summary>Original English</summary>

**Speaker B**: Kyouli directly? Yeah. Yeah. Yeah. How was the conversation?

</details>

**Speaker A**: 很好。我的意思是，见到他这样一个传奇人物真是太棒了，能见到这样的人真是太酷了。他非常专注，他一生中做了这么多事。他可以做任何他想做的事，或者干脆不工作。看到他试图解决一个问题，并想办法重新构想他的业务，这是一种非常AI化的事情，它把所有这些人吸引回来，试图思考下一阶段的企业建设会是什么样子。

<details>
<summary>Original English</summary>

**Speaker A**: It was good. He's I mean it's like such a legend to meet him and it's so cool to be able to see people like that and he's like it's focused like he could do he's done so much in his life. he could do whatever he wants or not work. And it's like to see him like trying to solve a problem and figure out how to reimagine his business is like a very AI type thing where it's like it's just drawing all these people back to like try to think about what the next phase of building businesses is going to look like.

</details>

**Speaker B**: 为什么 Kyu 的实验室没能成为中国领先的实验室？

<details>
<summary>Original English</summary>

**Speaker B**: Why Kyu's lab failed to become the leading lab in China?

</details>

**Speaker A**: 我不太清楚。你应该问他。

<details>
<summary>Original English</summary>

**Speaker A**: I don't really know. You should ask him.

</details>

**Speaker B**: 是的，这是个很难的问题。是的，我认为用AI做事有很多机会，而构建模型是一种不同的文化。构建模型很大程度上就像转动曲柄，不断提高资源投入的层级。我认为不仅仅是 01 AI 构建了一个模型然后就停止了。我认为在美国，像 Databricks 也在构建模型，然后他们觉得我们不需要做这个了。其他人已经承担了费用。我不知道他们是否公开说过，但我认为 Databricks 的很多领导层会告诉你，我们很乐意不支付构建这个模型的费用，我们将专注于我们的业务。这就是为什么我很惊讶有这么多公司还在继续投入，比如 1 万亿参数的模型，这要昂贵得多，而 01 AI 和 Databricks 推出的是小型或小型密集模型。投资要少得多。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that's a tough question. Yeah, I think there's a lot of opportunity for doing things with AI and building models is a different type of culture. The building models is very much like turning the crank and continuing to ratchet up the resource rungs. And I don't think it's just 01 AI that has like built a model and then stops. I think like in the US like data bricks was building models and then they were like no need for us to do this. Other people have got the bill. I don't know if they're on the record, but I think a lot of leadership at data bricks would tell you this where like we're happy to not pay for building this model and we're going to do our business. And I think that that's why I'm surprised that so many companies have kept ratchet or they like 1 trillion parameter which is way more expensive like 01 AI and data bricks got out at like small or small dense models. It's like way less investment.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 所以在某些方面，如果你认为自己无法竞争，早点停止可能比晚点停止更明智。不是每个人都需要拥有或构建最好的模型，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: So in some ways it might seem smart if you thought that you were not going to be competitive. You better it's better to stop earlier than later. Not everyone needs to have or to to build the best model, right?

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 中美AI模型差距与开源模型

**Speaker B**: 一个老生常谈的问题。你认为美国的SOTA模型领先中国模型多少个月？嗯，这个差距是会缩小还是扩大？为什么？

<details>
<summary>Original English</summary>

**Speaker B**: A cliche question. How many months do you think US SOTA models are ahead of the Chinese models? Um, and for that gap, is it going to become narrower or wider? Why?

</details>

**Speaker A**: 在传统基准测试上，一段时间以来一直是六到九个月。在现实世界使用中，尤其是在推理模型早期，差距非常小，因为那是一个新范式。当你处于一个新范式时，做这件事的回报非常丰厚。美国和中国的实验室都在以非常快的速度攀登改进曲线，而中国实验室发布得更快。所以如果你和中国实验室的人交谈，他们会说，“我们的模型还在RL阶段。完成最后一轮RL大约需要一周时间，然后我们会在完成后一天内发布。”而美国实验室有一些流程，通常需要数周才能将模型发布出去。所以如果你想想，如果你处于陡峭的进步曲线上，你有两条不同的线，如果中国落后，但你没有这种等待发布的水平停滞期。所以中国发布得更快。这在一定程度上收敛了用户获得的性能。所以归根结底，性能差距在于人们可以使用的模型。通过这次对话，我们谈到了几件事，比如知识工作领域，这全是美国工作者等等，我认为实际上美国前沿模型的原始效用只是更稳健一些，这种稳健性很难衡量。所以很难从基准测试数字上知道。我认为在流行的基准测试上，六到九个月的差距会变得稳定，但存在这种无形的、不可衡量的方面，美国模型会领先。最好的例子就是去年十二月和今年一月开始的云代码和 Codex 革命，如果一个开放权重模型能够实现这种行为，那将非常明显，因为全世界都会谈论它，就像我不再需要支付，我可以每月付1美元，而不是 OpenAI 的每月200美元。很多人会切换，截至录制时，这大概已经过去了五到六个月，我只是不太期望今年会出现那个非常清晰的分水岭，这将揭示差距，以及我们看待差距的方式，对于AI在非常广泛的应用场景中的使用方式来说，有点狭隘。

<details>
<summary>Original English</summary>

**Speaker A**: So on traditional benchmarks, it's been like six to nine months for a while. In real world use, especially early in reasoning models, it was very tight because it was a new paradigm. And it's like when you're in a new paradigm, the rewards to doing it are so steep. Both US and Chinese labs are climbing this really fast rate of improvement and the Chinese labs release sooner. So you talk to somebody at Chinese lab, they're like, "Our model's still in RL. It takes about a week to do this last RL run and then we'll release it within like a day of it being done." Where the US labs have some process that normally takes weeks to get the model out. So if you think about if you're on like steep progress, you have two different lines and it's like if China is behind but you don't have this like no progress horizontal is when you're waiting to release it. So China releases it faster. So it kind of like converges the performance that users get. So at the end of the day the performance gap is like the models that are available to people and through this conversation we've talked about a few things like some is like this knowledge work domain which is all US workers and things like this which I think realistically the raw utility of the US frontier models are just like a bit more robust in a way that's been hard to measure. So it's hard to know on the benchmark numbers. I think the six to nine months on like the benchmarks that are popular will become stable but there's this like intangible unmeasurable where the US models will pull ahead. The best example is like this cloud code and codeex revolution that started in December and January where it's like it'll be very obvious if an openweight model enables this type of behavior because everybody in the world will be talking about it which is like I no longer I can pay $1 a month instead of open AI is $200 a month. a lot of people are going to switch and as of recording that's say like five to six months and I I just like don't really expect that like really clear watershed this year which will like shed some light on the gap and how like the way we're looking at the gap is like a bit narrow to how AI is used in a really broad set of use cases.

</details>

**Speaker B**: 为什么我们至今还没有看到一个非常好的中国编程模型？我认为云编程 Codex 流行的很大一部分原因是它们非常易于使用，而且——

<details>
<summary>Original English</summary>

**Speaker B**: Now why haven't we seen a really good Chinese coding model as of yet? I think a lot of what's popular with cloud coding codecs is that they're just very easy to use and

</details>

**Speaker A**: 我认为中国实验室会继续解决编程问题。所以模型的实际代码质量会非常高，这基于公共数据和GitHub之类的东西，你创建难题，模型学习解决它们。但在易用性方面，美国实验室拥有非常大的领先优势，而且他们的运营方式存在差异，美国实验室能获得消费者数据。所以像 Cursor 在人们使用 Cursor 和 ChatGPT 的基础上训练他们的模型，而 Codex 和云代码也是一样，而所有这些开放权重实验室，他们发布一个模型，他们有不太流行的CLI，但模型的很多使用数据并不会反馈给开发者。所以某种程度上，这种真实世界的数据对于让模型在各种情况下更稳健非常有用，这就是闭源实验室拥有巨大优势的地方。

<details>
<summary>Original English</summary>

**Speaker A**: I think the Chinese labs will keep solving coding. So like the actual code quality of the models will be incredibly high and that's based on like public data and things like GitHub and stuff like this and you create puzzles the model model learns to solve there. But it's in this like ease of use thing that the US labs have had a really big lead and there's a difference in how they operate where the US labs get consumer data. So like cursor trains their model on people using cursor and chatgbt and codeex and cloud code are the same while all these openweight labs they release a model and they have their CLIs that are a bit less popular but a lot of the usage of the model just doesn't go back to the developer. So some of it is a bit of like that real world data is really useful to kind of making the model more robust across general circumstances and that's where the closed labs have a huge advantage.

</details>

**Speaker B**: 酷。我还有一些关于开源模型的问题。为什么中国实验室发布了这么多强大的开源模型？

<details>
<summary>Original English</summary>

**Speaker B**: Cool. And I do have some open source model questions. Why are Chinese labs released in so many strong open source models?

</details>

**Speaker A**: 这是一条通往相关性的路径。我认为他们知道自己落后了，他们知道自己想要更多地参与到对话中来。如果没人知道——

<details>
<summary>Original English</summary>

**Speaker A**: It's a path to relevance. I think they know they're behind and they know they want to become more in the conversation. And if no one knows

</details>

<!-- chunk 6/12 -->

### 开源模型的商业逻辑与中美竞争

**Speaker A**: 如果你有一个API，没人会考虑你的模型。但在AI模型如此珍贵且稀缺的世界里，当你公开释放它们时，会有很多人说：“哦，我希望自己也有一个AI模型。”他们会来看一看、试一试。所以所有实验室都非常务实——这是我们参与AI前沿故事的方式。他们会继续这样做，我预计这会保持稳定，因为我认为这种快速跟进的差距会持续存在。这就是为什么这是一种非常务实的心态：我们这样做并没有增加太多风险，它帮助我们实现目标，而且这是获得某些客户的唯一途径。所以我们不得不这样做。

<details>
<summary>Original English</summary>

**Speaker A**: If you have an API, nobody thinks about your model. But in a world where AI models are so valuable and pretty rare when you release them openly, there's a lot of people that are like, "Oh, I wish I had my own AI model." That are going to take a look and try it. So all the labs are really practical as like this is our way to be in the story of like what is happening at the frontier of AI and they will keep doing this and I expect this to be stable because I expect this like fast follow gap to continue. And this is why it's like a very practical mindset. It's like there's not much added risk to us doing it. It helps us accomplish our goals. It's the only way to get some customers. So like we've got to do it.

</details>

**Speaker B**: 如果Meta未能成为最好的开源模型，这是否意味着美国实际上正在将开源模型的领导地位输给中国？

<details>
<summary>Original English</summary>

**Speaker B**: If Meta fails to become the best open model, does it mean that US actually is losing open model leadership to China?

</details>

**Speaker A**: 在过去一年里，美国已经将开源模型的领导地位拱手让给了中国。我认为尤其是在2025年夏天，当一批新的中国实验室开始崭露头角时。那时GLM 4.5和Kimmy K2作为它们的突破性模型问世。从那时起，美国就不再拥有开源模型的领导地位了，而且情况一直如此。我认为自2025年夏天以来，任何声称相反说法的人，对于真正重要的模型来自哪里，都有点自欺欺人。

<details>
<summary>Original English</summary>

**Speaker A**: In the last year, US has seated the open model leadership to China. I think especially in the summer of 2025 when a bunch of these new Chinese labs were starting to get really prominent. It's when um GLM 4.5 and Kimmy K2 came out as their breakthrough models. And like from that point on like the US no longer had open model leadership and that's been the case. I think since summer of 2025 anyone claiming otherwise is a little bit diluted on where the models are coming from that actually matter.

</details>

**Speaker B**: 美国还有机会追赶上来吗？

<details>
<summary>Original English</summary>

**Speaker B**: Does US still have the chance to catch up?

</details>

**Speaker A**: 有机会，因为他们有Nvidia，而Nvidia的财务利益在于不让AI被任何一家公司独占。做到这一点的最佳方式就是向世界发布开源模型。

<details>
<summary>Original English</summary>

**Speaker A**: They do because they have Nvidia and Nvidia's financial interest is to not have AI be owned by any one company. And the best way to do this is to release open models for the world.

</details>

**Speaker B**: 所以唯一的希望就是Nvidia？

<details>
<summary>Original English</summary>

**Speaker B**: So the only hope is Nvidia?

</details>

**Speaker A**: 现实地看，可能还有像Meta和Microsoft这样的公司，它们拥有由AI支持的用户或企业产品，因此它们可以发布开放权重的模型，这不会真正损害它们的业务。但近年来它们选择不这样做。也许是因为分心，也许是营销和安全风险之类的原因。但只要这种情况持续，我认为Nvidia是改变这一局面的最佳选择。就在录制时，大概几天前或昨天，Jensen宣布了他们的Neatron 3 Ultra模型。我的看法是，这标志着Nvidia重新尝试开源模型的第一个篇章的完成——他们推出了Neatron 3 Nano、Super和Ultra，这是他们的专家混合模型系列，Ultra是最大的一个，他们将用它来生成合成数据，并在内部构建各种更小的模型和进行蒸馏。现在他们有了第一个大模型作为基础，在构建其他尺寸的模型和持续改进方面就有了更大的灵活性。这才是观察他们开源模型努力更有趣的地方。一旦有人做到这么大，他们能否继续从中扩展？或者Nvidia过去有很多模型虽然不错，但使用或覆盖周期消退得有点快。

<details>
<summary>Original English</summary>

**Speaker A**: realistically potentially like and open models like I think there's the likes of Meta and Microsoft where they have products whether user or enterprise that are supported by AI so they could release openweight models. It wouldn't really hurt their businesses but they've chose not to in recent years. Maybe it's a distraction. Maybe it's a like a marketing and security risk or something, but so long as that stays, I think Nvidia is best positioned to change this. As of recording, like a couple days ago or yesterday, and Jensen announced their Neatron 3 Ultra model. The way I think about this is like that's the completion of the first arc to Nvidia starting to try open models again where they had these Neatron 3 Nano Super and Ultra which is their like mixture of expert models and Ultra is the biggest one which they will then use to make synthetic data and all sorts of smaller models and distillation inhouse. So now that they have their first big model established, they have a lot more flexibility in building other sizes of models and continuing to improve it. And this is where it'll be more interesting to see their open model efforts. It's like once somebody gets to this big, can they keep kind of scaling it from there? Or Nvidia had a lot of models in the past that were like were good but kind of fell out of the um usage or coverage cycle a bit more quickly.

</details>

**Speaker B**: 那像Reflection AI或者你们这样的小型玩家呢？

<details>
<summary>Original English</summary>

**Speaker B**: How about some smaller players like reflection AI or maybe you guys?

</details>

**Speaker A**: 是的。我认为会有更多人公开构建模型，开源生态系统可以支持多样化的模型。这些中小型模型非常有用，因为它们成本低廉，如果你能让它们重复执行一项任务，相比使用闭源编码器，你将节省大量资金。这就是为什么开源模型领域有一种追逐前沿的执念，也就是那些大模型，比如Neatron Ultra、Kimmy K2等等。我认为随着时间的推移，这种对最大模型的执念会逐渐消退。比如Reflection想要构建一个大模型，但人们与Quen竞争，而Quen赢得了人心——这是一个全世界每个研究人员都在基于其构建的小模型。目前AI研究在Quen上进行的程度令人难以置信。很长一段时间是Llama，但现在每个研究人员都知道Quen在那个规模下是如何工作的，他们已经习惯了使用它，这对他们来说是一个真正了不起的成就。我认为这一点被谈论得不够多。随着时间的推移，从小到大的分布将会有更多层次的兴趣。对于Reflection来说，选择一个服务不足的细分市场可能更好。AI2构建了小模型，非常适合研究。我不认为AI2应该追逐前沿，试图构建一个万亿参数的模型。从慈善角度来说这不可能，而且从战略上做点不同的事情也是好的——在人们意识到自己无法在财务上跟上前沿之前，有足够的时间去填补不同的细分市场。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So I think there will be many more people building models in the open and the open ecosystem can support like a diversity of models. So these smaller medium size models are very useful because they're so cheap and if you can get them to do one task repeatedly you're going to save so much money over using cler codecs and why like there's kind of a fixation in open models of chasing the frontier which is these big models such as an imatron ultra Kimmy K2 and whatever. So I think that's kind of something where over time that fixation on the largest model will fade. So like reflection wants to build a big model, but it's like people competing with Quen that will win the hearts and minds, which is this small model that every single researcher in the world is building off of. Like the extent that AI research right now is done on Quen is incredible. It was llama for a long time, but it's like everybody like all the researchers know how Quen works at that scale. They're used to using it and that's like a really remarkable achievement for them. And I think it's like not talked about enough. And I think over time that distribution from small to big will have more levels of interest. And I think like for a reflection it might be better to like pick a niche that's less served. And like AI2 builds smallo models which are great for research. And it's like I don't think AI2 should chase the frontier and try to build a one trillion parameter model. I think philanthropically it's not possible but also it's just like good to do something strategically different than like we there's time to fill different niches before people realize they can't financially keep up with the frontier.

</details>

**Speaker B**: 谁拥有最好的中国开源模型？

<details>
<summary>Original English</summary>

**Speaker B**: Who has the best uh China open source models?

</details>

**Speaker A**: 这总是在变化。我个人想花更多时间玩各种模型。我会说最好的模型是Kimmy和Zai。比如Kimmy K 2.6和GLM 5.1可能是我听到最多的、真正在使用的前沿领域产生影响的模型。但变化太快了，我认为在整个2025年，Deep Seek都是无可争议的王者，拥有最好的模型，特别是他们的V3和R1系列。如果小米在中国夺得桂冠，我也不会感到惊讶。Quen最大的模型一直是闭源的，这在一定程度上阻碍了它们在最大尺寸上的采用和心智份额。但如果非要我说的话，截至今天，Kimmy和Zai是世界上最好的开源模型。

<details>
<summary>Original English</summary>

**Speaker A**: It goes back and forth. I think that I personally want to spend more time playing with the various models. I would say that the best models are like Kimmy and Zai. So like Kimmy K 2.6 and GLM 5.1 are probably the ones that I hear most as like actually making a difference at the frontier of usage. But it so fast like I think all of 2025 Deep Seek was the like unanimous king with the best models particularly like their V3 and R1 lines. And I wouldn't be surprised if Xiaomi was to to take a crown in China. Quen's biggest models have been closed. That has held back some of their adoption in mind share the biggest sizes. But I don't know if you put a gun to my head, I would say Kimmy and Kim Kimmy and Zai as of today are the best open models in the world.

</details>

**Speaker B**: 但竞争很激烈，对吧？变化很快。

<details>
<summary>Original English</summary>

**Speaker B**: But the competition is intense, right? That changes very fine margins.

</details>

**Speaker A**: 是的，差距非常微小。

<details>
<summary>Original English</summary>

**Speaker A**: very fine margins.

</details>

**Speaker B**: 你在文章中提到很多中国研究人员。跟我们说说你对他们的印象。他们与美国AI实验室有什么不同？

<details>
<summary>Original English</summary>

**Speaker B**: You mentioned that a lot of Chinese researchers in your article. Tell us about your impression on them. How are they different from the US AI labs?

</details>

**Speaker A**: 中国有如此多的人才。你去一个实验室，里面大多是土生土长的中国研究人员。他们通常更年轻。我们去了清华附近的很多地方，还有其他优秀的大学。所以，你去实验室，首先人员构成要统一得多——很多中国研究人员。而在AI2或任何其他地方，我感觉我和各种各样的人一起工作。作为一个在美国的非移民或父母是移民的人，我感觉有点不寻常——我和来自世界各地的人一起工作，无论是欧洲、中东还是亚洲其他地方。在美国的实验室也是如此，那里也有很多中国研究人员，但在人口层面上感觉确实不同。另外，我们之前谈到的一些事情是，很多顶尖的美国研究人员在讨论AI的未来走向，这种模型的哲学或艺术设计。我认为这次旅行的组织者Katherine Renul指出的一个例子是，像Amanda Ascal这样的人在谈论模型性格，真正雕琢模型的语气。所以，这种对话在中国并没有真正出现。在某些圈子里，他们讨论的话题，或者他们愿意对AI未来走向的预测，是相当不同的。除此之外，又非常相似。我认为更有趣的中国特有现象是，中国最新一代的研究人员英语似乎更好了。很多非常年轻的人说一口流利的英语，他们都关注西方AI生态系统的Twitter和博客，并且都在写论文。而反过来则不然——美国生态系统中很多人根本不关心中国在发生什么，他们不去想，即使有人真的感兴趣并且想知道这些公司是如何运作的，也很难获得关于中国科技生态系统的可靠信息。所以存在着这些非常不同的信息流，它们会影响人们的思维方式，但同时也是一种相当美国化的性格特征——对自己周围的东西非常自豪，有点自夸。这是一种非常……

<details>
<summary>Original English</summary>

**Speaker A**: There's so much talent in China whereas you go to a lab and it's mostly like Chinese researchers grew up in China. They're often younger. they lot like we went to a lot of places near Singwa and there's other great universities. So it's like you go to the labs for one it's way more uniform in who is there like a lot of Chinese researchers it's like here at AI2 or anywhere I'm like I feel like I work with all sorts of people and as somebody who is like not a immigrant or parents who are an immigrant in the US I'm like I feel a little bit unusual it's like I work with people from all over the world whether it's Europe Middle East other places in Asia and that's in the US labs that's also the case there's a lot of Chinese researchers in the US but that's like the population level is like It's definitely a a different feeling there. And then I think that some of these things we talked about earlier where a lot of the like top US researchers are like talking about where AI will be going. This kind of philosophical or artistic design of models and I think it's an example that the organizer of the trip um Katherine Renul pointed out is that like the likes of Amanda Ascal that are talking about like model character and really crafting the tone of the models. So, it's like that whole conversation didn't really come up in China. It's like there's some pockets there where the topics they talk about or like how far they're willing to project where AI is going is is pretty different. Otherwise, it's so similar. I think the things that are more interesting China specific is like the newest generation of researchers in China seem like even better at speaking English. Like so many of these really young people speak incredible English and they all follow the western AI ecosystem on Twitter and read blogs and they're all writing these papers where the opposite is not true where it's like the US ecosystem a lot of people just have no like they don't think about what's happening in China they don't like it's hard to get reliable information or what I feel like is of what's happening in the Chinese tech ecosystem even if somebody's like really interested in it and wants to know how these companies navigate. So there's these very different information flows that will feed into how people think, but also it's like a fairly American character trait to be like very proud of the stuff around you and like slightly boful. It's like a very

</details>

<!-- chunk 7/12 -->

### 硅谷与中国的AI文化差异

**Speaker A**: 美国这边，硅谷那种文化会奖励这种行为，有点像隧道视野。硅谷显然在形成自己狭隘的AI文化和讨论，比如“永久底层阶级”那套胡扯，现在又是“递归自我改进”和“奇点”。你去中国实验室的时候，也能看到一点这种影子，但少得多。他们有一部分是从美国学来的，反应是“哦，有点怪，但我们会觉得挺有意思”。但在旧金山，这真的是人们谈论的核心。资深博士生会说：“哦，我现在得赚钱了，我得加入一个实验室。”旧金山有一种非常强烈的文化，围绕AI的紧迫感以及它如何改变他们的职业生涯，这种感觉在中国不一样。在中国，他们的态度更像是“我们要做这件事”。在这方面可能更务实一些，没那么焦虑。

<details>
<summary>Original English</summary>

**Speaker A**: American thing and it's like oh the Silicon Valley kind of like rewards people for doing this and it's like a bit tunnel vision in a way where Silicon Valley is obviously developing its own narrow culture and discussion around AI with the like permanent underclass nonsense and now it's the recursive self-improvement and the singularity. There's sprinkles of this when you visit the Chinese labs but way less. They like got part of it from the US. are like, "Oh, that's a little weird, but we'll be entertained by it." But when you go to SF, it's like that's really what people talk about. It's like senior PhD students are like, "Oh, I need to make my money now. I need to join a lab." There's this very intense culture in SF around the timeliness of AI and how their career is changing that didn't feel the same in China where they're like, "We're going to do this." maybe a bit more down to earth in that regards like less anxious about things.

</details>

### 中国AI人才的全球角色

**Speaker B**: 你怎么看待当前浪潮中的中国AI人才？我的意思是，如果你看看美国领先的前沿AI实验室，你会看到很多中国研究人员，对吧？华裔美国研究人员在完成博士学位后在那里工作。嗯，他们可能是移民，也可能是第二代移民。中国人才在今天的AI研究中到底扮演着什么角色？

**Speaker A**: 他们在每家公司都扮演着关键角色。我认为美国当前限制高中移民的政治立场对这个国家不利。我和很多中国人或国际人士一起工作，我希望他们能住在我喜欢居住的国家，我不同意正在推行的政策。是的。任何在科技行业工作的人都知道这些人才有多关键。而且我认为存在担忧，比如最近有新闻提到对一些顶级AI公司高管实施护照出境禁令，美国那些意识到这些人才重要性的人，以及日益加剧的地缘政治紧张局势，会担心：如果他们召回顶尖研究人员怎么办？因为美国公司将受到严重打击。这就是现实。我不知道这个决定在短期内是否会被做出。这远非收听本播客的人群所能接触到的圈子。那不是做决定的人，但美国确实有人在谈论这可能是科技行业进步的一个主要潜在瓶颈。

<details>
<summary>Original English</summary>

**Speaker B**: how do you view Chinese AI talent in the current wave? I mean like if you even look at the leading frontier AI labs in the US, you will see a lot of Chinese researchers, right? Chinese American researchers working there after completing their PhDs. Um they might be immigrants, they might be second generation immigrants. What kind of roles are Chinese talents actually playing in the AI research today?

**Speaker A**: They're in every company playing crucial roles. Like I think the US current political stances to limit high school immigration is bad for the country. Like I I want I work with a lot of Chinese or international people and I think that I want them to be able to live in the country where I like to live and I would like like I disagree with the policy that is going on. Yeah. And I think anyone that works in tech knows how crucial this talent is. And I think there's worries as for example there was recent news about like exit bans on passports for some of the top executives AI companies and people in the US that are sensitive to how important this talent is and the rising geopolitical tension will worry like what if they call back the top researchers cuz the US companies will be severely hurt. Like that's that's the reality of it. I don't know if that call gets made at all in the near term. That is not remotely near the circles of people who listen to this podcast. Like that's not who makes that decision, but like people talk about this stuff in the US as being a major potential bottleneck on the tech industry's progress.

</details>

### 组织人才与愿景的挑战

**Speaker B**: 看起来你只需要一个人来领导团队，对吧？然后你有了那个模型……

**Speaker A**: 愿景很难。所以，关于构建语言模型，一个被低估的事情是，它很大程度上是一个组织架构问题。你有人才，你想让模型变得更好。困难在于组织人才，并弄清楚如何将大问题分解成小问题，让大量人才可以汇聚到这个单一模型上。

<details>
<summary>Original English</summary>

**Speaker B**: It looks like you only need one person to lead the team, right? Then you have that model to be

**Speaker A**: vision is hard. So, an undersold thing about building language models is that so much of it is an org chart problem where you have talent and you want to make the model better. And the hard thing is organizing the talent and figuring out how to break down the big problems into little problems where a lot of talent can funnel into this one model.

</details>

**Speaker B**: 我不知道我是否准备好非常肯定地这么说，但这可能是中国工程师的培训方式，使得他们不太适合制作这些组织架构图，他们只是埋头于自己的小任务，并乐于为更大的模型做出贡献。我认为这其中有很多不确定性，因为前沿实验室实际运作方式的记录并不那么详尽，可能更像是一片混乱，人们四处奔波试图改进模型，这也许不是最好的比喻，但这绝对是一个受组织架构限制的问题，你必须让所有这些人都投入到这一件事上。

<details>
<summary>Original English</summary>

**Speaker B**: I don't know if I'm ready to state this like really strongly, but it like could be the way that Chinese engineers are trained that they like weren't suited to making these org charts where it's just like they're just going to grind on their little thing and be happy that it contributes to the bigger model. I think there's a lot of uncertainty in this cuz like how the frontier labs actually work is not that well documented and it might just be more of chaos where it's just like people running around trying to make the model all the time is like not the best analogy but it's like it's definitely a works chart limited where you have to get all these people into this one thing.

</details>

### 年轻研究者与范式吸收

**Speaker B**: 是的。中国AI研究人员是否更愿意抛弃旧假设，直接吸收最新范式？如果你看看RL智能体、编码模型和工具使用，例如，这些并非DeepSeek发明，但该公司以极其有效的方式优化了这项技术。

**Speaker A**: 我认为这更多是关于新的、有干劲的年轻研究者。有一个非常悲观的谚语说“科学进步，一次一葬礼”，这是最阴暗的说法。但这只是说明新人更愿意接受最新的事物，他们没有理由捍卫自己的旧想法，因为他们没有既定的记录，他们想要一头扎进去，接受这些东西。就中国可能拥有更年轻的工程人才和领导层而言，这些人先验知识更少，因此这可能是真的。如果你受过科学训练，你越年轻，很多新想法和变革就越可能来自你。但这并不意味着中国文化更难培养出真正有远见的人，比如那种顶尖专家水平。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Are Chinese AI researchers more willing to drop old assumptions and just um absorb the latest paradigm? If you look at RL agents, coding models and tool use for example wasn't invented by deepseek but the company optimized the technology in an extremely effective way.

**Speaker A**: I think this is something that's more of just with new and like youthful motivated researchers. There's a very grim saying that's like science advances one funeral at a time which is like the most bleak way of saying it. But this is just that like new people are much more willing to accept the newest things and they have no reason to defend their old ideas cuz they have no established track record and they want to dive in and take these things and to the extent that China is potentially younger and both through engineering talent and leadership like those people just have less priors and therefore it might be true. It's something if you're trained in science you it's like the younger you are like that's where a lot of the new ideas and change comes from. for Chinese culture doesn't mean um it is harder to cultivate someone who is truly visionary for example that level of leading expert

</details>

### 教育体系与创新文化

**Speaker B**: 那是我的印象，这种印象是基于这样的理解：中国文化从很小的时候就建立在标准化考试之上，其中一些考试奖励死记硬背，学生们知道，如果他们通过了这次考试，就能进入下一个最好的学校，他们总是处于这种超级竞争的状态，思考着他们进步道路上的这种关卡。如果我对中国体系的理解有误，请纠正我，但这是我的理解。而美国的生态系统则没有那么多这样的关卡，你的命运不会因此被决定得更好或更坏，它更像是一个连续体，最优秀的人去最好的学校，第二好的学校也非常好，它们之间相互交融。是的，存在文凭主义，但可能没那么极端。所以我认为这很可能是事实。一些领导层会私下谈论这一点，说这种体系奖励死记硬背，而且即使你想改革，也很难重新设计一个教育体系。

<details>
<summary>Original English</summary>

**Speaker B**: that's the impression that I have and the impression is built on like like understanding that the culture is built on like standardized testing from such a young age and some of these tests rewarding memorization students know that like if they make this test they get to go to the best school at the next rung and they always are this like super competitive thinking about this kind of gate in their progress and correct me if my understanding of the Chinese system is wrong but that's my understanding where the US ecosystem has like less of these gates where it's like your fate is decided as better or worse and it's more of a like a continuum where a lot of the best people go to the best schools and the second best schools are also very good and they blend through each other and yes there's credentialism but maybe a bit less extreme so I think it's very possible that that is the case and some of leadership would off the record talk about this of like this rewards memorization and it's very hard to rework an education system despite if you want to

</details>

**Speaker A**: 你私下交谈过的一些科技领袖说情况确实如此，我当时想，好吧，我没有理由不相信你。

<details>
<summary>Original English</summary>

**Speaker A**: some tech leaders you talked to off the record said that that was the case and I was like okay I I have no reason to not believe you

</details>

### 中国实验室：完美的快速追随者

**Speaker B**: 你形容中国实验室几乎完美地设置为快速追随者。你能解释一下吗？是什么让它们执行得如此之快？

**Speaker A**: 是的，这就是我为什么在谈论年轻人才和文化，这种文化就是技术驱动、专注于任务，可能他们就是锁定在这件事上，而且他们拥有丰富的人才，你可以让人们在各个层面工作，并将其汇入一个模型。我们已经多次看到这种情况，一旦你知道某件事是可能的，做起来就更容易一些。我们已经看到中国经济在其他领域追赶上来，比如你去看小爱（Xiai）的技术，进去感觉像苹果商店，他们很可能受到了iPad和iPhone及其设计的启发，而且他们很擅长这个。他们不仅在AI领域做到了这一点，我预计他们会在AI领域再次做到这一点。争论在于，他们这样不断重复做基础工作，是否足以让他们……人们想知道的是，哦，中国会超越美国的AI实验室吗？我认为在一个资源平等的世界里，他们或许能够做到，因为他们有更多愿意在5到10年的时间里投入更多工作时间的人才。但我认为，人才只是构建这些模型所需的资源之一，而资本——主要通过算力和数据——实际上是最大的杠杆。而且看起来他们拥有的资源与美国超大规模公司相比不成比例地少。所以，我认为人才只能带他们走这么远，但技术会扩散，最好的模型会让制造更高效的模型变得更容易。所以它就会这样持续推动下去。

<details>
<summary>Original English</summary>

**Speaker B**: you describe Chinese labs as almost perfectly set up to be fast followers can you explain that what makes them execute so fast

**Speaker A**: yeah this is why I was talking about the various things on the young talent and the culture of just like being very technically driven and focused on their task and potentially like they're just lock in on this thing and they have abundant talent where it's like you can just have people working across the whole stack and funnel it into a model and we've seen this many times it's like once you know that something is possible it's a bit easier to do this and we've seen Chinese tech economies come for other things it's like you go into like Xiai's technology you go into it feels like an Apple store it's very likely they're inspired by the iPad and the iPhone and their designs and they're good at it. Like they've done this not just in AI and I'm like I expect them to do it in AI again. And the the debate is whether or not like them doing this fundamentals to keep redoing it is enough for them to like people like to wonder is like oh is China going to leaprog the US AI labs? And I think that in an equal resource world they might be able to where they're just like they have more talent that's willing to work more hours over a 5 to 10 year time frame but I think human talent is only one of the resources that it takes to build these models and just like capital through mostly compute and data is actually like the biggest lever and it seems like they're disproportionately fewer resources than the US hypers scale companies. So it's like I think talent will only take them so far, but the technology diffuses where the best models make it easier to make more efficient like models. So it just kind of like is going to keep propelling through there.

</details>

### 快速追随者能否成为前沿领导者？

**Speaker B**: 快速追随者能成为前沿领导者吗？

**Speaker A**: 他们可以。我认为AI之所以特殊，是因为它的资源需求。我认为中国通往领导地位的道路是，需要很长时间才能到达最终目的地，而这段时间里，华为会建设其产能，然后其净产能会变得更大。所以你会经常听到人们谈论力量平衡和芯片。我认为大多数人认为这需要……

<details>
<summary>Original English</summary>

**Speaker B**: Can a fast follower become the frontier leader?

**Speaker A**: They can. I think AI is weird because of the resource requirement. I think China's path to leadership is by it taking a long time to get to the final destination and that's time where Huawei builds out its capacity and then its net capacity becomes bigger. So the common scenario you'll hear in people talking about balance of power and chips. So I think that most people think that it would

</details>

<!-- chunk 8/12 -->

### 中国AI科学家与西方生态的文化冲突

**主持人**: 这可能需要很长时间才能实现，但不要排除这种可能性。当我们谈到顶尖AI科学家的文化差异时，你知道，在美国这边是这样，但我想起中国，也许小米是个例外，Lulu Lee在社交媒体和播客上都很活跃。还有来自Quinn的Ling，他曾是Quinn的技术负责人，今年早些时候离开了公司。特别是对于Linguin，我认为在所谓的个人主义和集体主义之间存在明显的冲突，后者优先考虑公司利益本身。你看到更多这种来自中国实验室的冲突正在进入西方生态系统吗？

<details>
<summary>Original English</summary>

**Host**: It could be a long haul for that to happen, but don't rule it out. As we talk about the leading AI scientists culture difference, you know, here in the US right, but I think back to China, maybe Xiaomi is an exception with Lulu Lee being quite active on social media as well as podcasts. There was also Ling from Quinn, he was the tech lead of Quinn, he left the company earlier this year. Especially for Linguin, I think there was apparent conflict between what's called the individualism and collectivism which prioritizes the company's interests per se. Do you see more of that kind of conflict coming out from the China labs going into this western ecosystem?

</details>

**嘉宾**: 我认为一些研究人员会发现他们非常适合这里。我称他为Justin，他的英文名。他在这方面非常擅长。我有点把这看作我们在美国也见过的情况，就像科技公司里那些能在外部也获得很大影响力的人，可以对抗领导层，而大型科技公司会说我们不需要听你的。然后他们就分道扬镳了，就像我们见过的那样。

<details>
<summary>Original English</summary>

**Guest**: I think some of the researchers will find that they are very well suited to this. So I call him Justin, the American name. And it's like he was so good at this. And I kind of see it as something we've also seen in America, whereas like people in tech companies that can get a lot of influence externally as well can push against leadership and the big tech companies are like we don't need to listen to you. So then like they part ways, like we've seen it.

</details>

**嘉宾**: 就像我们在美国见过的那样。一个突出的例子是谷歌的一些AI伦理研究人员，Timnit Gebru向谷歌领导层发出了最后通牒，他们说不，然后就像在大型科技公司里，你会碰到一些很难逾越的墙。我认为一些中国研究人员可能也会进入这个生态系统，我们可能会再次看到类似情况。但对于初创公司来说，像Kimmy或Zi这样的初创公司会很乐意有一个能制造声势、吸引注意力的人，之后再解决问题。这很大程度上取决于公司的规模。但我认为如果有更多中国研究人员进入这个领域会很好，因为拥有更多观点是好事，如果世界这一部分的人能在美国被看到，让更多人了解他们的想法和他们处理模型的方式，那将有利于全球的平衡。

<details>
<summary>Original English</summary>

**Guest**: Like we've seen it in the US. I think a prominent example was around some of the AI ethics researchers at Google where it's like Timnit Gebru sent an ultimatum to Google leadership and they said no and it's like there's walls that you can hit within big tech companies that are hard to hit. And I think that like some of these Chinese researchers will probably get fed into this ecosystem and we might see some of it again. But for startups, the startups like Kimmy or Zi would love to have a person that is making noise and bringing attention, you just figure it all out later. Very much depends on the company size. But I think it would be good if more of the Chinese researchers get into this because it's good to have more views and like this whole part of the world if they can be seen in the US so more people understand how they think and how they approach models. It would be good for the kind of global equilibrium.

</details>

**主持人**: 是的，太好了。我们正在努力做到这一点。我们正试图邀请更多的中国研究人员来我们的节目。

<details>
<summary>Original English</summary>

**Host**: Yeah, that's great. We're trying to do that. We're trying to invite more Chinese researchers coming to our show.

</details>

**嘉宾**: 是的。所以请订阅我们的频道。当你与中国研究人员交谈时，你在中国AI实验室内部看到的是什么样的氛围？是更多的自信、焦虑、好奇，还是更务实的东西？

<details>
<summary>Original English</summary>

**Guest**: Yeah. So subscribe to our channel. And when you talk to the Chinese researchers right, what was the mode inside the Chinese AI labs? Did you see more confidence, anxiety, curiosity, or something more practical?

</details>

**主持人**: 我认为肯定存在一种焦虑，担心在算力上跟不上。所以我认为所有中国实验室都想要更多的英伟达算力来训练最新的模型，而研究人员正是感受到这种压力的人。他们是遇到资源限制的人。但除此之外，社会焦虑较少。我认为在美国，社会焦虑情绪高涨，无论是与我共事的人，他们非常担心自己的工作被取代。我会说，你是我认识的最好的AI研究人员之一，但即使是像这样的人也会说，我真的非常担心这一点。这在更广泛的讨论中也很普遍，美国CEO们到处谈论人们将如何失去工作，这不是一个好的信息传递决策，但这现在已经深深植根于人们思考AI和数据中心讨论的方式中。这些文化冲击点似乎没有一个在中国落地。一些开发者，我们问他们什么是AGI，他们说当它取代我的工作时，但这并不是悬在他们头顶的乌云。他们的态度是，我想建造这个东西，之后再说。

<details>
<summary>Original English</summary>

**Host**: I think there definitely is an anxiety of not being able to keep up in compute. So I think it's like all the Chinese labs want more Nvidia compute to train the latest models and the researchers are the people who feel this post. It's like they're the people that are hitting the resource constraints, but otherwise there's less social anxiety. I think in the US there's a big upswell of social anxiety, whether it's people I work with here that are seriously concerned about their job being replaced. And I'm like, you're one of the best AI researchers I know, but like even people like this will be like, I'm really really concerned about this. And this is in the broader discourse where American CEOs are going around talking about how people are going to lose their jobs which is not a good messaging decision but that's like very deeply embedded in how people think about AI now and the data center discussion. It doesn't seem like any of these cultural shelling points has landed in China. Some of the developers are like we ask them what is AGI and they're like when they take my job and they're not like it's not like a cloud hanging over them. They're like, I want to build this thing and figure it out later.

</details>

**主持人**: 为什么会这样？

<details>
<summary>Original English</summary>

**Host**: Why is that?

</details>

**嘉宾**: 开发者存在一些犹豫，或者说这种情况正在发生很大变化。他们都使用Claude，这在中国按理说是被禁止的。他们都用它来工作，而且他们非常坦率地告诉我们，我们喜欢Claude，Claude是最好的模型。所以，关于软件工作正在改变的这种犹豫确实在增长，但远没有形成一种集体性的社会舆论，认为AI是坏的、具有破坏性的。这种感觉在中国似乎完全没有建立起来。我认为他们中的一些人讨论过，中国经历了如此多的快速技术变革，随着国家在技术和经济上取得巨大进步，他们觉得这只是下一个变革，他们已经经历了这么多，比如中国的超级应用，现在他们有了电动汽车，他们只是觉得，哦，就是这样，事情就是这样。而在美国，这些变化之间的间隔更长，然后这是最新的一个，需要克服的惯性也更大。

<details>
<summary>Original English</summary>

**Guest**: There's some hesitancy around developers or like this is changing a lot. They all use Claude, which is supposedly banned in China. They all use it to do their work and they told us very forthcomingly like we love Claude, like Claude's the best model. So, there's definitely some hesitancy growing around like software jobs are changing, but it's much less of a collective like social opinion on AI is bad and disruptive. Like that doesn't feel like it's established in China at all. I think they some of them discussed how China's they've been living through so many technological changes in rapid succession as the company makes so much progress technologically and economically where they're like this is like the next one where they've had so many with these like the Chinese mega apps like they have electric cars now like they're just kind of like oh this is this is just how it is where in the US it's like these changes have come with more cadence in between them and then like this is the latest one and there's kind of like more inertia that it's going to have to move aside.

</details>

**主持人**: 人们在中国实验室里讨论对齐问题吗？安全问题呢？

<details>
<summary>Original English</summary>

**Host**: Are people talking about alignment at all, safety issue at all within Chinese labs?

</details>

**嘉宾**: 更常用的词是安全。公司肯定关心这个问题，但这远非首要考虑。他们的态度是，如果我们发布模型权重，我们要确保它不会带来任何巨大的新风险。我们会讨论，我们会追问，那么多模态模型呢？他们会说，是的，其中一些东西的风险上升得更快一些，但远没有到那种“我们发布的大型文本LLM智能体是一个重大风险，因此我们不应该发布它”的程度。他们对此会说一些合理的话，但这不像在美国，有时听起来几乎是意识形态化的，是一种根深蒂固的担忧，认为下一个AI就是那个需要高度警惕的AI。所以，我认为这是有分寸的，但并非首要考虑。

<details>
<summary>Original English</summary>

**Guest**: The word that's used more is security. The companies definitely care about this, but it was much less front of mind. It was like if we're releasing model weights, we want to make sure that it's not enabling any gigantic new risk. And we would talk, we would poke at like what about multimodal models? Like, yeah, some of these things have moved to be risks a bit faster, but it's much less of this big text LLM agent that we're releasing is a major risk and therefore we need to like not release it. They would say reasonable things about this, but it was not like in the US it can almost sound like ideological and like deep rooted concern that like AI like the next AI is going to be the one that is of a lot of concern. So, I think it's measured but not very front of mind.

</details>

**主持人**: 是的，可能中国人只是更务实。

<details>
<summary>Original English</summary>

**Host**: Yeah, probably like Chinese are just being more practical.

</details>

**嘉宾**: 我觉得这很合理。我基本上也是这个立场。我支持开放模型，但我不是绝对主义者。我不认为每个模型都应该开放。Claude的发布有点像营销噱头，但它也是一个不可思议的突破性模型。如果它刚问世的第一天就被上传到Hugging Face，那就不太好了。技术扩散需要时间，对于变革性的事物来说，随着时间的推移逐步开放访问是合理的。我们现在所处的平衡状态，即封闭模型领先，开放模型跟随，似乎是将技术推向世界的好方法，我认为很多公司也会有类似的感觉。

<details>
<summary>Original English</summary>

**Guest**: I felt like it was reasonable. I was like that's kind of my stance. It's like I support open models, but I'm not an absolutist. It's like I don't think every model should necessarily be open. Claude's release is a bit of a marketing stunt, but also it's like an incredible breakthrough model. It would not be good if that was just uploaded to Hugging Face the first day that they had it. Like it takes time for technology to diffuse and access diffusing over time for transformative things is reasonable and the equilibrium we're in right now where the closed models are ahead and open models follow it like seems like a good way to get technology into the world and I think that a lot of these companies would feel similarly.

</details>

### 中国实验室的优势与追赶速度

**主持人**: 你认为中国实验室在哪些方面真正领先于美国实验室，在哪些方面他们没有领先，但进步速度比美国人预期的要快？很多人说中国实验室在构建更高效的模型。我认为这有点夸大其词，因为美国实验室在推理时服务的token数量要多得多。所以，他们有更大的动力，比如让Claude或ChatGPT的效率提高1%，其财务收益就是数十亿美元。所以我认为他们有更多理由去追求效率。但我认为中国实验室由于更早开始做开源，对人们如何使用他们的开放模型有更好的理解。我们与阿里巴巴的人交谈过，他们对此非常有意识。但现在，像Kimmy、Zai和其他已经建立了多个周期的公司，他们正在跟踪人们如何使用他们的模型，这种专业知识是非常短暂的。我试图弄清楚人们是如何使用Qwen的，这非常困难，很难直接获得信息，但这正是决定他们的模型成功与否的关键。显然，基准测试很重要，但问题是，为什么Cursor选择了Kimmy的模型？Kimmy会深入思考这个问题，或者去问他们，这是AI前沿非常有价值的、难以获得的知识。所以他们知道什么能让一个开放模型变得更好，而这只有通过大量发布模型才能获得。所以我认为英伟达正在通过发布模型来积累势头，他们也会开始获得更多这样的反馈。而在美国有一种反思，即我们会在模型准备好时再发布，但他们将完全得不到人们实际使用模型的反馈。是的，这个基准测试很好，但这个相关的东西不行，为什么？我认为这种关于开放生态系统如何运作的无形知识正在那里巩固。

<details>
<summary>Original English</summary>

**Host**: Which parts do you think Chinese labs are genuinely ahead of the US labs today and which parts are they not ahead but moving faster than Americans expect? So a lot of people say the Chinese labs are building more efficient models. And I think that's kind of overblown because the US labs are serving way more tokens at inference. So they're way more incentivized like the financial gain to make Claude or ChatGPT 1% more effective is like billions of dollars. So I think they have like more reasons to be efficient. But I think that the Chinese labs by doing it longer have a bit better understanding of like how people are using their open models. And we talked to people at Alibaba and they're very intentional about this. But also now the likes of Kimmy and Zai and all these others with these established that have multiple cycles. They're following how people are using their models and this expertise is very transient like I try to figure out like how are people using Qwen and it's like a massive like it's really hard to get the direct information but it is what makes their model successful or not. Obviously those benchmarks but then it's like why did cursor choose the Kimmy model? Kimmy's going to think about that. Yeah, really deeply or ask them and this is like very valuable expertise at the frontier of AI that's hard to get. So they like know what makes a bit better open model or not and you only get this from releasing models a lot. So I think like Nvidia is building momentum on releasing models and they'll start to get more of this feedback and then there's reflection in the US that's like we'll release a model when it's ready but they're going to get none of this feedback of people actually use the model and yes this benchmark is good but this very related thing doesn't work why and I think that's like the intangible knowledge of how the open ecosystem works is consolidating there right.

</details>

<!-- chunk 9/12 -->

### GPU算力短缺：中国AI实验室的最大劣势

**主持人**：现在我们来谈谈相反的情况。中国实验室今天仍然面临的最大劣势是什么？

<details>
<summary>Original English</summary>

**Host**: Now let's move to the opposite case. What are the biggest disadvantage that the Chinese labs still is today?

</details>

**嘉宾**：是的，是算力。这个估算可能不准确，但你可以说，Meta或OpenAI拥有的GPU比所有这些中国公司加起来还要多，而且它们很可能确实如此。我听到过一些传言，说一个OpenAI的研究员自己就能拿到大约5000块GPU。而这对于一个中国开源模型实验室来说，可能占其研究预算的很大一部分。所以我认为，他们承担风险的余地和在算法上能做的动态事情的范围要窄得多。我认为，他们更倾向于优化当前模型的路径，这更像是一种必然选择，因为他们知道可以不断改进，但整个生态系统的活力较低。有一个中国实验室告诉我们，他们最新的预训练运行花了六个月时间，而这个模型已经发布在Hugging Face上了。如果那次运行失败了，那整个模型系列就不会存在了。这对公司来说是一个非常不稳定的处境。我认为，以他们拥有的算力，他们的表现超出了大多数人的预期，但算力仍然是限制因素。

<details>
<summary>Original English</summary>

**Guest**: Yeah, it's compute. There's likely incorrect estimates, but you could say something like Meta or OpenAI have more GPUs than all of these like Chinese companies combined, and they very well likely do. And I've heard rumors that say like an OpenAI researcher has about can get like 5,000 GPUs for themselves. And this is like would be a major proportion of a Chinese open model lab's research budget. So I think their aperture for risk and amount of dynamic things they can do algorithmically is much more narrow and I think there see like just optimizing the current path of the models is much more of a necessity because they know they can keep making this better but it's a less dynamic ecosystem. One of the Chinese labs told us like their latest pre-training run took like six months and this is a model that's out on hugging face and it's like if that run didn't work like that whole line of models just like wouldn't exist and that is a very precarious position to be for the company and I think that they're exceeding most people's expectations with the amount of compute that they have but that is the limiting factor.

</details>

**主持人**：是的，中国实验室非常渴望获得更多的英伟达GPU芯片。算力短缺在多大程度上改变了他们的模型策略？

<details>
<summary>Original English</summary>

**Host**: And yes the Chinese labs are desperate for more Nvidia GPU chips. How much does compute scarcity change their model strategy.

</details>

**嘉宾**：最重要的一点是，你设计的每个模型基本上都取决于你期望它在下游如何被使用，以及你的训练集群的形态。训练集群的配置会影响训练不同大小模型的效率，同时你也知道你需要部署它。所以，由于可能拥有较小的集群，这会改变他们做出这类决策的方式，或者他们可能会降低更改基础模型架构的频率，因为预训练运行需要更长时间。我确实认为，对于一些较小的实验室，比如阿里巴巴和字节跳动，它们拥有的资源情况有所不同，但对于MiniMax、月之暗面等公司来说，大多数预期都集中在三到六万亿参数的范围。我认为，除非他们能获得最新的NVL 72机架和Blackwell芯片之类的设备，否则他们很难扩大规模。所以，基本上存在天花板，但这是一个多优化问题，无论是你的训练集群，还是你的推理堆栈，他们可能现在希望模型能在华为的芯片上进行推理。

<details>
<summary>Original English</summary>

**Guest**: The biggest thing is that every model you essentially design it based on how you expect it to be used downstream and then what the shape of your training clusters is. So like the training cluster will configure how efficient it is to train a different size of model and then you also know you need to serve it. So based on probably having smaller clusters which is going to change how they do make these types of decisions or maybe they can change their base model architecture less frequently because pre-training runs take longer and I do think that we're going to see for some of these smaller labs I think Alibaba and bite dance with the resources they have is a bit different but like miniax moonshot etc like most expectations are clawed and GPTs are at this like three to six trillion parameter range and I think it'll be a lot harder for for them to scale up unless they're getting these like latest NVL 72 racks and Blackwell chips and things like this. So essentially there's like there's ceilings to these but it's a multi-optimization problem whether it's like what's your training cluster what's your inference stack they might want it to work on Huawei inference now.

</details>

**主持人**：比如，你的用户是谁。所以他们做了所有这些事情，我们看到的输出是Hugging Face上一个大约6000亿到一万亿参数的模型。这很难映射，但这是实验室里最有趣的决策之一，大多数人不会告诉你。

<details>
<summary>Original English</summary>

**Host**: Like who are your users so they do all of these things and we see the output as a model on hugging face of like 600 billion to a trillion parameters it's hard to map but it it's one of the most interesting decisions in a lab and most people won't tell you.

</details>

**主持人**：是的。那么，算力短缺是迫使提高效率，还是最终会限制前沿发展？

<details>
<summary>Original English</summary>

**Host**: Yeah. So, does compute scarcity force better efficiency or does it ultimately cap the frontier?

</details>

**嘉宾**：它确实有影响，但更像是改变了你的工作方式。每个人都想要计算效率，因为如果你有更高效的研究，如果你把你的实验单元成本降低一半，你就能运行两倍数量的实验。这里有一些非常基础的数学原理，每个AI研究员都想要这个。很难说中国实验室在这方面就一定会更好。也许是因为他们的推理算力较少，所以他们训练出的模型在推理时更高效，这涉及到不同的权衡。我认为DeepSeek以其内存节省创新而闻名，其中一些现在已被广泛使用，但当你比较时，可能会觉得有点过头了。比如，一个美国实验室可能会看着它说，“嗯，这能给我们带来一点收益，但不值得投入这么多精力”之类的。

<details>
<summary>Original English</summary>

**Guest**: It does, but it's more of like you're changing how you work like everybody wants compute efficiency because if you have a more efficient research, if you make your experimental unit half the price, you run twice as many experiments. There's like a lot of very basic math where every AI researcher wants this. It's hard to say that the Chinese labs would necessarily be better at it. It's like maybe because they have less inference compute, they train a model that's more efficient at inference and that has a different trade-off. I think Deep Seek's famous for these like memory saving innovations like some of which are used everywhere now, but it like might just be overkill when you compare like a US lab might look at that and be like h it would give us a small gain but it's not worth the effort or something.

</details>

### 国产加速器（如华为芯片）的实际表现

**主持人**：那么，像华为芯片这样的国产加速器在实际中表现如何？嗯，我听到很多人说它准备好用于推理，但不适合训练。这基本上是共识。我们去一些比较随机的公司，不是核心的大模型公司，他们会说，“是啊，我们不得不用华为。但我们不用它。”但我们交谈过的大多数语言模型公司都已经足够成熟，他们都拥有人们正在注册使用的服务。智谱每天在其API上处理数万亿个token。所有这些公司都说，“如果你能给我华为芯片，我们也许能获得更多客户，他们正在想办法将它们用于推理。”但在训练方面，只有非常小的模型才能在华为芯片上训练。我个人预计这种情况会持续一段时间。这就是为什么专注于训练的研究人员会说，“我想要更多英伟达的芯片。”

<details>
<summary>Original English</summary>

**Host**: So how good are domestic accelerators such as Huawei chips in practice? Um I heard many people saying it's ready for inference but not for training. That's mostly the consensus. We would go to some more random companies, so not like core LLM, and they're like, "Yeah, we have to have Huawei. We don't use it." But most of the LM language model companies we talk to are established enough where it's like they all have services that people are signing up for. Zai serves trillions of tokens a day on their API. And all of those companies are like, "If you can give me Huawei chips, we will like maybe get more customers and they are figuring out how to use them for inference." But on training, it's only like very small models that could be trained on Huawei. And I personally expect that to be the status quo for a while. That's why researchers focused on training or like I would like more Nvidia trips.

</details>

**主持人**：“一段时间”是多久？

<details>
<summary>Original English</summary>

**Host**: A while is how long?

</details>

**嘉宾**：我的意思是，你得问半导体专家，但我预计是以年为单位。而英伟达仍然遥遥领先，因为英伟达正在调动全球供应链来制造顶级产品，而华为则是“需求是发明之母”。他们能走多远？我不知道。我不知道。

<details>
<summary>Original English</summary>

**Guest**: I mean ask a semiconductor expert, but I would expect order of years whereas like still Nvidia is so far ahead because Nvidia is channeling the global supply chain into making the top end products versus necessity is the mother of invention at Huawei and it's like how far do they get? I don't know. I don't know.

</details>

### 黄仁勋与达利文之争：芯片禁令的利弊

**主持人**：你如何看待最近黄仁勋和达利文之间的争论？对于那些不太了解背景的人来说，黄仁勋反对严格限制中国获取英伟达GPU，他认为中国已经拥有能源基础设施、芯片生产能力和AI人才来开发先进模型。他独立地表示，限制销售只会切断英伟达与一个巨大市场的联系，同时无法阻止中国的技术进步。而达利文则持有“中国威胁论”。当然，黄仁勋有偏见，因为他想在中国销售更多芯片，对吧？但你认为谁是对的？

<details>
<summary>Original English</summary>

**Host**: How do you see the recent debate between Jensen and Darkh? For people who are not very familiar with the context, Jensen argued against the strict limits on Chinese access to Nvidia GPUs, saying that China already has the energy infrastructure, chip production capabilities, and AI talent to develop advanced models. Independently, he said that restricting sales only cuts Nvidia off from a massive market while failing to stop China's technology process. while Dar Cesh was holding the China threat theory and of course Jensen is biased because he wants to sell more chips in China, right? But whom do you think is right?

</details>

**嘉宾**：我认为现实地说，我处于中间立场，但更偏向达利文一方。这最终会变成一个地缘政治讨论，比如，你是否认为AI是一种会被用于此目的的技术？我宁愿看到传统的美国价值观，比如言论自由等等，在世界上传播。我认为向中国提供AI芯片确实会在权力平衡方面构成一定程度的风险。作为一个美国人，这就是我的立场。

<details>
<summary>Original English</summary>

**Guest**: I think realistically I'm in the middle and more on Dwaresh's side. It ends up being a geopolitical discussion which is like do you think AI is a technology that is going to be used for this? And it's like I would rather see what is traditional American values of like freedom of expression and all these things spread into the world. And I think that giving AI chips to China does pose some level of of risk in this capacity to like on the balance of power. As an American, that's how I've fallen on this.

</details>

**主持人**：很难知道到什么程度。所以，当你听英伟达内部的人说，他们基本上是在说美国没有更多的电力来建设了。因此，美国没有人会购买这些芯片，所以我们想把它们卖给中国。但与此同时，美国公司要求更多的配额，美国政策制定者与选民交谈，选民们说，美国公司本来会购买更多。所以，我某种程度上与双方都谈过，一边是那些说“我想要更多芯片来卖给我的公司”的美国实验室。另一边是我与英伟达的政策研究人员交谈，他们说，美国无法支持更大的出货量。所以，很难获得关于美国会购买多少以及有多少会转移到中国市场的真实信息。这就是为什么我最终会有很大的误差范围，因为我不知道确切的平衡点在哪里，因此，有些芯片英伟达肯定无法在美国销售，我们应该把它们卖给中国，并支持英伟达在AI领域的领导地位。所以，我不知道。

<details>
<summary>Original English</summary>

**Host**: It's hard to know like to what extent. So when you listen to people within Nvidia, they essentially are saying there's no more power to build in the US. Therefore, no one in the US would buy these chips, so we sell them want to sell them to China. But at the same time, you have US companies asking for more allocation and US policy makers talking to constituents who are like, the US companies would have bought more. So, I kind of talked to both parties, which is these US labs that are like, I want more chips to sell my companies. And I talked to policy researchers at Nvidia where they're like, the US can't support more volume. So, it's so hard to get the ground truth information of like how much would the US buy and what is the diverted to this Chinese market. This is why like I end up with big air bars because I don't know who exact like what the equilibrium is and therefore there's like there's some chips that Nvidia definitely wouldn't sell in the US and we should tell them China and support Nvidia's AI leadership. So I don't know.

</details>

**主持人**：我更好奇的问题是，禁令是否会鼓励中国出现更好的AI芯片，也就是华为芯片，对吧？

<details>
<summary>Original English</summary>

**Host**: The question I'm more curious is that will the ban uh encourage better AI chips in China which is Huawei chips right?

</details>

**嘉宾**：情况确实如此。我们之前讨论过软件即服务与云服务，我认为AI正朝着云的方向发展，这将支持中国各种需要云服务来构建可行产品的新公司，并且会有不断增长的推理需求。我们谈到了开放云，我们谈到了云代码，推理需求是存在的。我认为中国在采用方面还处于早期阶段。你与中国开发者交谈，他们会说，“我使用Claude”，但这被路由到了西方的计算能力。随着中国释放更多的国内AI推理能力，这些用例的需求都将汇聚到华为能制造多少芯片上。

<details>
<summary>Original English</summary>

**Guest**: So it is definitely the case. We talked earlier about this like software as a service versus cloud and I think like AI is going in the cloud direction and this is going to support all sorts of new companies in China that need this cloud in order to build their viable products and there's going to be this growing inference demand. We talked about open cloud, we talked about cloud code like the inference demand is there. I think China is earlier on the adoption. You talk to developers in China and they're like I use claude like this is getting routed to what is western capacity and it's like as China unlocks more domestic AI inference capacity and these use cases like this demand will all funnel into how many chips can Huawei make.

</details>

**主持人**：所以，这将在几个月内发生，而不是几年，比如会有像云代码这样的新应用……

<details>
<summary>Original English</summary>

**Host**: So this is coming in months not years like there will be new apps like cloud code that...

</details>

**嘉宾**：……在中国非常有赋能作用，人们对它们有疯狂的需求。所以我看到这种情况正在发生，在这方面，黄仁勋某种程度上是对的，那就是……

<details>
<summary>Original English</summary>

**Guest**: ...are so enabling in China that people have crazy demand for them. So I see this happening and in this capacity Jensen is somewhat right where it's like that is...

</details>

<!-- chunk 10/12 -->

### 驱动本地AI生态发展的因素

**Speaker A**: 什么会驱动本地AI生态的发展呢？比如本地实验室有华为的芯片，他们正在针对这些芯片设计推理方案。某种程度上，这已经在发生了，问题只是规模多大、到什么程度是人们能接受的。

<details>
<summary>Original English</summary>

**Speaker A**: what's going to drive the local AI stack to be developed like the local labs have Huawei chips that they're designing inference for like in some ways it's happening and it's just a ratio of how much and to what extent is okay for people.

</details>

**Speaker B**: 所以瓶颈其实在于华为的生产能力，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: So the bottleneck is really on the production capacity for Huawei, right?

</details>

**Speaker A**: 是的。还有生态系统的易用性，也就是在这些芯片上实际运行模型的难易程度。这就像是一个冷却期。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. and the ecosystem for how easy it is to actually run a model on these chips. So which is like the cool down.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 所以我认为我非常看好AI需求的持续增长。因此，需求会创造这种必要性。

<details>
<summary>Original English</summary>

**Speaker A**: So I think like I'm very bullish on AI demand continuing to increase. So therefore like demand creates this need.

</details>

### 对Anthropic CEO观点的看法

**Speaker B**: Anthropic的CEO Daryl Amade一直是最直言不讳的科技领袖之一，他不断警告中国AI发展带来的国家安全和地缘政治威胁。你怎么看他的做法？

<details>
<summary>Original English</summary>

**Speaker B**: Anthroic CEO Daryl Amade has consistently positioned himself as one of the most vocal tech leaders warning about the national security and geopolitical threats posted by Chinese AI development. How do you see his approach?

</details>

**Speaker A**: 我觉得有点过于激进了。我认为Anthropic的一些媒体宣传在区分中国政府和中国个体科学家带来的担忧方面做得相当谨慎，但他对近期风险，比如开放权重模型带来的威胁，有点过于激进了。所以我认为人们听到他充当这方面的急先锋，可能会感到有些反感。

<details>
<summary>Original English</summary>

**Speaker A**: I think it's a little too aggressive. Like I think that some of anthropic media is pretty careful about separating the concerns from Chinese government and Chinese individual scientists, but it's a little like he's a little too aggressive in the near term about like risks posed by open weight models and so on. So I think it could be a little offputting to people to hear him kind of be the tip of the spear in that regards.

</details>

### 中国AI数据产业的弱点

**Speaker B**: 你提到中国AI数据产业的弱点比人们意识到的更重要。能详细谈谈吗？

<details>
<summary>Original English</summary>

**Speaker B**: And you mentioned that that China's weakness in the AI data industry is more important than people realized. Can you elaborate more on that?

</details>

**Speaker A**: 最令人惊讶的事情之一是，中国的数据产业远没有那么发达。当我们经历这整波“数据环境”热潮时，也就是像Anthropic和OpenAI这样的公司说他们有数十亿美元的数据预算，用来从外部供应商那里购买数据环境。我们问了中国公司，他们回答说，不，我们并没有这个。我们内部建了一些。人们会指出像字节跳动和阿里巴巴这样规模更大的公司，它们有能力建立内部数据团队，但很少听到有人说，你去从外部供应商那里买一些数据，而这在美国是非常正常的，就像法国实验室的常规做法。如果稍微带点批判性地看，在训练模型时，如果模型在某方面表现不佳，你会尝试去购买一些相关数据，看看这些数据能否提升评估分数。这可以说是对美国前沿实验室的一种批判性看法，是他们做的那些比较枯燥的工作。他们当然也做更令人兴奋的事情，但这种动态在中国似乎不存在。这看起来是最大的区别。显然，OpenAI的研究人员比中国研究人员拥有更多的算力，因此这些中国初创公司的人员研究不同的问题，也许看起来解决方案更高效等等。但数据这一点是唯一一个让我觉得，嗯，这本来不一定要有差异，但实际感觉却非常不同。

<details>
<summary>Original English</summary>

**Speaker A**: One of the most surprising things is that the data industry is much less developed in China. So we when we flew this whole environments craze so to say where companies like Enthropic and Open AI are saying that they have billions of dollars of data budget to buy environments from external vendors. We asked the companies and they're like no we don't really have this. We build some in-house. People would point to the likes of Bite Dance and Alibaba being bigger and being able to build internal data teams but there's very little talk of like you go and buy some data from an external vendor which is so normal in the US like the French lab playbook. If you take it a little like cynically in training the models is like the model is bad at something then you go to try to buy some data for it and you see if the data makes the eval go up and that's like kind of a cynical take on US Frontier Labs is like the boring stuff that they do. They do much more exciting things but that dynamic doesn't seem to exist in China. That looks like the biggest difference. It's like obviously open AI researchers have more compute than Chinese researchers and then therefore these Chinese startups the people work on different problems and maybe it looks like more efficient solutions and so on. But the data one was the only one was like okay this didn't necessarily need to be different and felt very different.

</details>

**Speaker A**: 目前人们如何看待美国前沿模型呢？它们正在成为知识工作工具。比如，作为一个名义上的知识工作者，我现在用Cloud Code和Codex来中介绝大部分工作。人们看到这种情况正在医疗、法律、咨询、金融等领域发生，美国模型都将推动这种能力。而这些模型的大量训练数据正是通过这些数据公司网络获得的，他们付钱给专业人士来创建这些训练数据。是的，这里有ScaleAI、Merker、Surge、Turring等一整套市场。这里有大量的公司，市场正在推动它们从离岸的RLHF偏好数据转向这个高技能劳动力行业。这个市场规模巨大，每个模型实验室为此支付的费用高达数十亿美元。他们这样做是因为这能创造价值，让模型在这些代理任务上表现更好。我认为问题在于，中国实验室能否为自己的代理解锁这个国内市场，让人们使用他们的模型来完成这些任务？因为这种需求才能让他们购买这些非常昂贵的数据。而如果中国的AI研究人员和知识工作者说，我在用Claude，那么Claude就更有理由继续在美国做这件事，这对美国数据产业来说就是全部。所以，我和实验室里做后训练的朋友聊过，这些数据公司对于在这些领域获得这种渐进式的性能提升非常重要。如果中国没有这个，那么你就必须非常有创造力，比如一个AI研究员就得去创造一个金融问题的数据环境，比如做一个Excel电子表格。我认为这不是AI研究员天生适合做的任务。这和他们所处的世界完全不同。

<details>
<summary>Original English</summary>

**Speaker A**: How people currently view US frontier models is that they're going into this like knowledge work tool. So like as a nominal knowledge worker like I use cloud code and codeex to now mediate the vast majority of my work and people see this happening for healthcare law consulting finance and the US models are all going to push into this capacity and a lot of the training data for this comes through these data company networks where they're giving money to professionals to create this training data. Yeah, there's a whole market of Scaleai, Merker, Surge, Turring. There's a whole plethora of companies here and the market is pushing them away from offshored preference data for RHF into this very high skill labor industry. And this is like huge, it's measured in billions of dollars of how much people are paying for this across each model lab. And they do this because it serves value and makes the models better at these agentic tasks and I think it's a question of like do the Chinese labs unlock this domestic market for their own agents and people do using their models for this because that demand is what will let them buy this data that's very expensive versus if the Chinese AI researchers and then knowledge workers are like I'm using claude like claude is just has all the more reason to keep doing this in the US and that's all for the US data industry so like it's I talked to my friends that do post training at labs and like these data companies are like really important to getting this like incremental performance bump on all of these domains. And if so, if it doesn't exist in China, like you're going to have to be very creative to make like an AI researcher is then going to be making up an environment in data of say like a finance problem of like making an Excel spreadsheet. And I just don't think this is a task that an AI researcher is naturally suited to do. It's like a different world than they live in.

</details>

### 中国AI应用与商业模式

**Speaker B**: 关于中国的需求和商业模式，我还有几个问题。你知道，在移动互联网时代，中国公司非常擅长推出新的应用程序。人们会说像美团、微信和阿里巴巴这样的公司彻底改变了我们的日常生活。因此，有一种假设认为，一旦模型准备就绪，这次中国在AI应用方面也会行动得更快。你看到这种情况会发生吗？

<details>
<summary>Original English</summary>

**Speaker B**: I have a few more questions about Chinese demand and business model. You know like during the mobile internet era Chinese companies are so good at launching new apps applications. Um you know people would say companies like Muan, WeChat and Alibaba totally changed our daily lives and assumption is that China will move faster this time as well on AI applications once the models are ready. Do you see that coming?

</details>

**Speaker A**: 我认为在美国和中国，应用层面都将出现令人难以置信的活力。甚至有些观点认为，美国消费者更习惯于添加新应用，然后快速上手并为之付费；而在中国，他们有这些超级应用，问题在于超级应用能否支持同样多的新用例多样性。在美国，你有像Sora这样的东西，它是排名第一的应用，数百万人尝试它，但它失败了。它是一个独立的沙盒，可以提供更明确的体验。所以我几乎可以说，在软件方面，美国更适合这种动态尝试新应用的模式。

<details>
<summary>Original English</summary>

**Speaker A**: I think both in the US and China there's going to be incredible dynamism in the applications. I think some arguments are even like the US consumers more used to adding new apps and then like going through the like getting very used to it and paying for it than in China where they have these mega apps and it's a question of like can the mega app support the same amount of diversity of new use cases where in the US you have things like Sora which is the number one app and millions of people try it it's a flop like and it's its own sandbox it can be a more defined experience so I would almost say in the software side the US is more set up for like this dynamic trial of new apps.

</details>

**Speaker B**: 中国实验室是否担心变现问题？

<details>
<summary>Original English</summary>

**Speaker B**: Were Chinese labs worry about monetization at all?

</details>

**Speaker A**: 没有特别公开地表达过，但我们也没问。我也不认为很多前沿AI实验室那么痴迷于变现。OpenAI和Anthropic想要IPO，但大多数构建AI模型的人只是想说，我想构建最好的模型。而且如果你假设模型会变得更好，它们如此有用，那么资金就不会是问题。这取决于你问谁，对吧？如果你问一个产品经理，他们可能会担心。或者问那些试图支持购买更多算力的领导层。

<details>
<summary>Original English</summary>

**Speaker A**: Not super vocally, but we also didn't ask. I also don't think that many of the like frontier AI labs are that obsessed with monetization. Open AI and anthropic want to IPO, but most people building a AI models are just like, I want to build the best model. And if you assume the model's going to get better, like it they're so useful, the funding won't be a problem. depends on whom you ask, right? If you ask a product manager, probably they're concerned about or the leadership that's trying to support buying more compute.

</details>

### 中美实验室交流

**Speaker B**: 美国实验室应该更频繁地访问中国实验室吗？

<details>
<summary>Original English</summary>

**Speaker B**: Should US labs visit China Labs more often?

</details>

**Speaker A**: 我认为我们会看到一些美国公司，尤其是那些试图围绕开放模型建立经济价值的中小型玩家，无论是通过微调API还是专门部署等等，他们希望与中国实验室建立关系，因为中国实验室非常愿意分享他们的技术和专业知识。在去过中国之后，我们看到，我收到了很多公司的咨询，他们问如何能接触到所有这些实验室，我们想去参观。这就像，你可以去查一下美国一家知名的、基于开放模型工作的推理或训练公司。如果这种情况发展下去，将会开启一个新时代，这些新公司学习如何跨境合作。我预计会有更多美国公司去中国，因为现在的签证情况容易得多。我上次是走免签过境政策，从不同国家入境和出境，这非常容易，基本上直接去就行。而中国的研究人员或工程师去美国，则要等待签证博弈。所以我预计会有更多对开放模型感兴趣的美国中型初创公司去中国，这很可能在未来几周到几个月内发生。这种事情发展很快。2026年夏天。

<details>
<summary>Original English</summary>

**Speaker A**: I think we'll see some US especially small and medium players that are trying to build economic value around open models whether it's a fine-tuning API or specialized deployments or so on want to build relationships with Chinese labs because the Chinese labs are so open to sharing their technology and expertise after traveling to China we've seen like I've gotten inbound from a lot of companies are like how do you get access to all these labs we would go visit and this is a you could look up a known own either impra or training company in the US that works on top of open models where if this evolves it'll be kind of a new era of these new companies learning to work with each other across borders. I would expect more US companies to go to China because it's much easier in the visa situation right now. So I traveled on the visa free transit where you enter and exit through different countries and that's super easy to do. pretty much just show up. Whereas like a Chinese research or engineer traveling to the US, you have to wait for the visa games. So I expect more US medium-sized startups that are interested in open models to go to China, which is probably going to happen in the coming weeks to months. Like this stuff happens fast. The summer of 2026.

</details>

**Speaker B**: 这很好。你经常做客Lex Friedman的播客节目。他最近去了中国。我觉得他一个坐卡车兜风的视频在中国互联网上很火。你和Lex私下聊过你的中国之行或者他对访问中国的兴趣吗？

<details>
<summary>Original English</summary>

**Speaker B**: That's good to know. You've been a frequent guest on the podcast show with Lex Friedman. He was in China recently. I think one of his videos catching a truck ride really going viral on Chinese internet. Do you and Lex actually talk privately about your China trip or his interest in visiting China?

</details>

**Speaker A**: 我们还没有做过事后分析，比如“你觉得中国怎么样？”我想我们俩都只是有兴趣亲眼看看这片影响我们生活中如此多科技的人类广阔区域，因为这是最好的方式。

<details>
<summary>Original English</summary>

**Speaker A**: We haven't done a postmortem of like what do you think of China? I think both of us are just interested in seeing this large swath of humanity that influences tech that we live with so much and seeing it firsthand because that's the best

</details>

<!-- chunk 11/12 -->

### 对全球AI竞赛的看法

**Nathan**: 我觉得自己相当中立。我对AI的大部分担忧，都集中在美国舆论对AI态度变差，以及这可能会阻碍进步上。我认为全球AI竞赛，从地缘政治和大局来看，基本符合我的预期。就是美国领先，中国想追赶，而在芯片销售数量以及这对生态系统最终会产生什么影响方面，存在一些细微差别。我认为，最重要的是能为这件事带来更多人性化的视角，尽我所能，让双方的人们都不至于陷入极端境地。那些构建和使用这项技术的人，对最高层的决策几乎没有发言权。我能做的，就是为促进双方的理解尽一份绵薄之力。

<details>
<summary>Original English</summary>

**Nathan**: I think I'm pretty neutral. I think most of my worries on AI are like very centered on like US opinion being sour on AI and how that could hurt progress. I think the global AI race is roughly what I would expected geopolitically in this biggest picture. It's like the US is ahead and the Chinese wants to catch up and there's this nuance in terms of how much chips are being sold and what that like what that pin ends up doing to the ecosystem. I think it's mostly just a benefit to be able to bring more humanity to this and like do what I can to make it less of a very extreme circumstance for people on both sides. So people building and using the technology that have very little say on what the highest level decisions are. It's like I could do a small part to make that more understood for both sides.

</details>

**主持人**: 好的。非常感谢你，Nathan。我想我的问题都问完了。你还有什么想补充的吗？或者有什么我没问到的问题？

<details>
<summary>Original English</summary>

**Host**: All right. Thanks so much Nathan. I think all those are my questions. Anything else you want to add? Any question I didn't ask?

</details>

**Nathan**: 没有了。谢谢你邀请我。希望不久后我能再去一次中国。那里还有很多值得看的东西。

<details>
<summary>Original English</summary>

**Nathan**: No. Thanks for having me. I'll hopefully sometime soon go for a second trip to China. There's plenty more to see.

</details>

**主持人**: 好的，我们很乐意在你下次旅行后做第二次访谈。

<details>
<summary>Original English</summary>

**Host**: Yeah, we'll love to have the second interview after your next trip.

</details>

**Nathan**: 谢谢。

<details>
<summary>Original English</summary>

**Nathan**: Thank you.

</details>

**主持人**: 好的。非常感谢你。那么，跟我们说说你们是做什么的吧。

<details>
<summary>Original English</summary>

**Host**: All right. Thank you so much. Yeah, tell us about what you guys do.

</details>

### AI2实验室介绍

**Nathan**: AI2从事各种开源AI研究和开发。我认为，从历史上看，它一直比较学术化，但随着时间的推移，它正更多地转向这种明确的开发模式，即构建模型、代码库和数据集，供社区其他成员在此基础上继续开发。所以，我认为Mo和这些开源语言模型是最受欢迎的，但还有像多模态的Mo Earth等其他东西。此外，AI2历来因其与AI文献的结合而闻名。我认为这方面的应用就是Semantic Scholar，它被视为Google Scholar的替代品，用于搜索学术文献。这个团队已经发展成构建用于科学的AI代理。所以，就有了这个ATA品牌，他们正在构建工具来帮助人们构建和理解科学文献。所以，我认为其核心文化是高度科学化的，并且有一种社区价值观，即为科学社区创造大量净效益，这非常棒。这一点体现在那些非常注重细节、充满关怀的论文中。我认为有很多不同的方式可以体现这一点，这也是在AI2工作的最大好处之一。你会非常专注于构建各种研究人员会使用的东西。当你以学者身份旅行时，你会发现所有这些人都基于Elbow和AI2进行构建，这就像是一种持久的影响力。当有实习生或学生研究员离开，进入那个学术社区和其他研究机构时，这种科学价值观得以传播，这是AI2做出的一项伟大贡献。

<details>
<summary>Original English</summary>

**Nathan**: So, AI2 does all sorts of kind of open-source AI research and development. I think it's historically been fairly academic and over time it's been moving more into this artifact defined development where you're building models and code bases and data sets that the rest of the community can build on. So I think Mo and these open language models has been the most popular one but there's also like Mommo the multimodal Mo Earth and other things and then AI2 has historically been very well known for its integration with AI literature. So I think the application there has been Semantic Scholar which is kind of seen as alternative to Google Scholar for searching academic literature and this team has evolved into building AI agents for science. So it's this ATA brand where they're building tools to assist people in building and understanding the scientific literature. So I think at its core it's cult like deepest culture is so scientific and like has this community value of building a lot of just like net good for the scientific community which is really great and that comes through in these papers that are very detail-oriented and caring and I think there's just like so many different ways which way do you want to go there's so many different ways that this comes through and it's the best one of the best things about working at AI2 is you just like you get so focused on trying to build things that various researchers use when you travel as an academic and you're like all these people are building on Elbow and know of AI2 and it's just kind of like a lasting thing that is great when there's interns or student researchers and they go out into that academic community and all these other research institutions to kind of spread this scientific value which is a great service that AI2 does.

</details>

**主持人**: 是的。你们现在有多少人？

<details>
<summary>Original English</summary>

**Host**: Yeah. How many people do you have right now?

</details>

**Nathan**: 大概200人。

<details>
<summary>Original English</summary>

**Nathan**: Probably about 200 people.

</details>

**主持人**: 哦，哇。那真不少。

<details>
<summary>Original English</summary>

**Host**: Oh wow. That's a lot.

</details>

**Nathan**: 所以，他们大部分是研究人员，对吧？我猜大概一半的人才属于传统AI研究的技术工程领域，然后还有工程团队来支持我们的集群和我们的一些产品。

<details>
<summary>Original English</summary>

**Nathan**: So most of them are researchers right? I would guess probably half of the talent is technical engineering on like the traditional AI research and then there's engineering teams that help support our clusters and um some of our products.

</details>

**主持人**: 像NGO实验室和硅谷的其他实验室有什么不同？

<details>
<summary>Original English</summary>

**Host**: How is like a NGO lab different from other labs in Silicon Valley?

</details>

**Nathan**: AI2是一个完全的非营利组织，这意味着它的大部分资金来自慈善机构。Allen on the Door的资金来自保罗·艾伦，他是微软的联合创始人之一，此外还有来自例如美国国家科学基金会（NSF）的大额资助。所以，它完全是靠非营利资金运作，并不真正销售任何产品。它只是把创造的一切都免费提供给人们学习。

<details>
<summary>Original English</summary>

**Nathan**: So AI2 is a full nonprofit which means most of its money comes from philanthropies. So the Allen is on the door which is from Paul Allen one of the co-founders of Microsoft and then also has large grants from u for example from the NSF. So, it's all nonprofit funding and doesn't really sell any products. It just gives everything it makes away for free to for people to learn from.

</details>

**主持人**: 哇。所以，我猜你们有更多的研究自由。

<details>
<summary>Original English</summary>

**Host**: Wow. So, you guys have more research freedom, I guess.

</details>

**Nathan**: 是的。所以，我认为在从封闭实验室到学术界的资源谱系中，就自由度而言，它处于中间位置。这意味着我们有更多的资源，同时也感受到压力，要构建出真正优秀的模型。所以，这确实在一定程度上抑制了自由度，但远不及那些竞相奔向AGI的前沿实验室。但如果你去一个真正的学术机构，你会发现他们拥有多样性和那种智力火花，这是你在公司里因为需要支付账单而无法获得的。

<details>
<summary>Original English</summary>

**Nathan**: Yeah. So, I think that on the spectrum of closed lab to academia in terms of resources, it sits in the middle in terms of freedom, which is like we have more resources and we feel pressure to build models that are actually good. So it like does suppress the freedom a little bit but much less than a frontier lab that is like racing towards AGI but if you go to a true academic institution you'll see that they have a diversity and kind of intellectual spark that you like won't get at a company just based on the needs of paying the bills.

</details>

**主持人**: 西雅图的氛围和硅谷的氛围有什么不同？

<details>
<summary>Original English</summary>

**Host**: How is Seattle vibe different from the Silicon Valley vibe?

</details>

**Nathan**: 平静太多了。不像这里，总是有各种活动，人们聚在一起。我个人希望西雅图有更多这样的人。比如，这里有亚马逊、微软等主要科技人才中心，所有科技公司都应该有更多这样的氛围，但事实就是如此，你无法改变。在某些方面，我认为这是一个更适合安定下来和组建家庭的地方，因为它更分散一些，不那么紧张，也不那么热衷于谈论AI。比如，我不会在每次谈话中都提到AI，而在湾区，AI感觉像是现在唯一的话题，我理解为什么。我自己也深陷其中。但你经常去湾区。

<details>
<summary>Original English</summary>

**Nathan**: It's so much calmer. Like there's not events all the time with various people meeting up. I personally wish that more people in Seattle. like there's major tech talent hubs at Amazon, Microsoft, and all the tech companies would have more of this, but it's what it is. You can't fight it. In some ways, I think it's a better place to like settle down and have a family because it's like a bit more spread out and it's a bit less intense and how bright this everything is in terms of talking about AI. Like I don't have AI in every conversation where in the Bay Area AI feels like it's the only conversation right now, which I understand why. Like I'm bought in as well. But you visited the Bay Area a lot.

</details>

**主持人**: 我定期去。我大概一年去三到八次。

<details>
<summary>Original English</summary>

**Host**: I go regularly. I say I go like three to eight times a year.

</details>

**Nathan**: 好的。

<details>
<summary>Original English</summary>

**Nathan**: Okay.

</details>

**主持人**: 我上的是加州大学伯克利分校，所以我在湾区住了七八年。

<details>
<summary>Original English</summary>

**Host**: I went to UC Berkeley, so I lived in the Bay Area for like seven or eight years.

</details>

**Nathan**: 然后你必须回去才能了解湾区到底发生了什么。你这里看不到这样的景色。一个非常美丽的湖。它叫什么名字？

<details>
<summary>Original English</summary>

**Nathan**: And then you have to go back to stay in touch with what's actually happening in the Bay Area. You don't have the view like this. A very beautiful lake. What's the name of it?

</details>

**主持人**: 嗯，联合湖。

<details>
<summary>Original English</summary>

**Host**: Um Lake Union.

</details>

**Nathan**: 这绝对是我梦想中的办公室。

<details>
<summary>Original English</summary>

**Nathan**: Definitely my dreaming office for sure.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Nathan**: 是的。那么，当你访问中国时，你觉得那里的办公室怎么样？

<details>
<summary>Original English</summary>

**Nathan**: Yeah. So when you visit China, how do you think the office there, the

</details>

<!-- chunk 12/12 -->

### 中国科技公司办公室与展厅文化

**Speaker A**: 人工智能实验室的办公室，他们没有这个视野，但他们的办公室也是科技公司的风格，在这方面其实挺相似的。或者说，我走进去，感觉就像在一家科技公司里。我这辈子去过很多科技公司的办公室，感觉就是，嗯，展厅文化不一样。

<details>
<summary>Original English</summary>

**Speaker A**: AI lab office there, they don't have this view, but they're also tech company offices where it's like they're pretty similar in that regards or like I go in them and it feels like I'm in a tech company and I've been into a lot of tech offices in my life and it's like, okay, the showroom culture is different.

</details>

**Speaker B**: 哦对，展厅在中国确实很独特。

<details>
<summary>Original English</summary>

**Speaker B**: Oh yeah, showroom pretty unique in China.

</details>

**Speaker A**: 那确实是中国非常独特的一个现象，我觉得很多人第一次去参观的时候，才会意识到，哦，原来还有这种东西。好的，非常感谢你，Nathan，感谢你接待我们。

<details>
<summary>Original English</summary>

**Speaker A**: That is a very unique China thing that a lot of people just I think have to visit for their first time and then they're like, okay, this is a thing. Cool. Cool. Thank you so much, Nathan, for having us.

</details>

**Speaker B**: 嗯，谢谢你们来。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Thanks for coming.

</details>

**Speaker A**: 再见。

<details>
<summary>Original English</summary>

**Speaker A**: Bye.

</details>