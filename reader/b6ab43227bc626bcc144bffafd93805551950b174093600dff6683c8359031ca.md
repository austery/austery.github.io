---
author: Latent Space
date: '2026-11-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8cGfJOU3AlQ
speaker: Latent Space
tags:
  - diffusion-models
  - image-generation
  - robotics
  - open-source-models
title: Black Forest Labs 团队访谈：从 Stable Diffusion 到 Flux 与机器人领域的演进
summary: Black Forest Labs 的联合创始人 Andreas Blattmann 和 Dustin Podell 分享了团队从 Stability AI 分裂创立的原因，强调了模型潜在价值的释放。他们讨论了 Flux.1 系列模型在图像编辑和修复中的应用，并探讨了从图像生成到视频模型再到机器人领域的研发趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Andreas Blattmann
  - Dustin Podell
companies_orgs:
  - Black Forest Labs
  - Stability AI
products_models:
  - Flux.1
  - Flux Context
  - SDXL
  - ControlLoRA
  - Stable Diffusion
media_books: []
status: evergreen
---
<!-- chunk 1/14 -->

### 开篇介绍：Black Forest Labs 与图像/视频生成的前沿

很高兴为大家带来我们与 Black Forest Labs 合作的这一期节目。我们今天的嘉宾是 Andreas Blattmann（大家也叫他 Andy），他是潜扩散（latent diffusion）技术的共同发明人，这项技术最终被 Stable Diffusion 和 Stability AI 发扬光大并进行了规模化；后来他们与 Stability AI 核心图像生成团队的一批成员分道扬镳，创立了 Black Forest Labs。另一位嘉宾是 Dustin Podell，我和他也是在节目中讲述的故事之一里认识的，他一路从普通工程师、兼职 Web 开发者晋升为 Stability AI 的模型与研究主管，现在在 Black Forest Labs 工作；他是 SDXL、ControlLoRA 的创造者，也是 SD3、Flux Ultra、Flux 1 以及 Flux Context 的后训练负责人。我们会深入探讨所有这些细节。

大家可能知道，有时我们非常荣幸能与某些嘉宾有着深厚的渊源，他们就是其中之一。你们可能在 Robin Rombach 那期节目中听过，我们聊到在某届 NeurIPS 上互相介绍，并第一次见到 Black Forest Labs 的团队，那是紧接着 Stable Diffusion 发布之后的事情。但大家可能还没听过、而且我们只在这一期里讲述的故事是：Latent Space 这个播客本身就是因为 Stable Diffusion 而诞生的。根据当时所看到的景象，正是它的发布直接促使我下定决心辞掉工作、全身心投入 AI 领域。今天的嘉宾 Dustin 也有着同样的经历，Robin 也是如此。因此，我们与这支最终创立了 Black Forest Labs 的团队有着非常非常深厚的纽带。

现在我们也对他们的下一步充满好奇：他们已经打造出了图像生成和视频生成领域数一数二的开源及闭源权重模型。我认为特别是 Flux Context，如果你还不了解图像编辑模型的话——我确实认为，它最终会成为全面替代 Canva、Photoshop 以及你在常规创意工作流中可能用到的许多其他流程和编辑器的工具之一。它不会取代最高端的那部分市场，但对于普通的日常编辑，除了直接调用模型并让它帮你完成图像编辑之外，你为什么还会想用别的呢？我们显然也是这样处理这类视频剪辑的，全是由 AI 工具完成，我自己再进行审核。

他们目前也在涉足机器人领域。这正好与一系列模型实验室的发展轨迹相契合，这些实验室都在沿着这一方向探索：从 Runway 这类图像生成出发构建世界模型，再到视频模型，如今又延伸至机器人模型。我认为在我们最近的很多期节目中都有很多呼应之处，比如我们即将发布的 Artificial Analysis 那期节目，他们也在转向机器人领域。很明显，当你看到一大批处于前沿的顶尖聪明人都朝着同一个方向倾注精力时，说明距离某种真正重大的突破可能只有 6 到 12 个月了。这在我过去四年的播客生涯中一直是一个贯穿始终的主题，现在也不会改变，所以请大家拭目以待。

这是我能指出的最显而易见的趋势，但对于那些对广义扩散模型领域感兴趣的人来说，这里面也有很多有趣的背景故事。随着时间推移，我们会做更多探讨。我在考虑办一场针对洛杉矶生成式媒体领域的 AI 工程师活动，聊聊生成式媒体领域与创意艺术，以及这种复杂关系正在如何演变——坦率地说，我认为它正在走向成熟。

最后，对于老听众们，我们开始向赞助商开放合作了，他们都是我们真正钦佩、尊重并希望展示其成果的团队。第一期是与 Supabase 合作，我想你们很多人都很喜欢；今天的第二家赞助商是 Deepgram，大家将在节目中段听到更多关于他们的介绍。

你应该给机器人演示一次动作，然后它就应该能够照着做出来，这才是真正的超人智能……就像在 Stability 那样，我们本质上无法将这些模型的全部潜在价值充分发挥出来……没能真正捕捉到模型本身价值的失误……到目前为止，我们总共筹集了 4.5 亿美元的资金……目前，去年 12 月公布的最新营收已超过 1 亿美元……成立 BFL 并不是为了做一家图像生成实验室……视频建模实际上是理解我们这个世界底层运转机制的核心手段……可能也就训练了 6 个小时，4 个小时的训练，这是一次非常非常短的训练运行。突然之间，我好像从中看到了一种显而易见的通用能力正在涌现，因为它是……[音乐]

<details><summary>Original English</summary>
Happy to bring to you our episode with Black Forest Labs. Our guest today are Andreas Blackman. He also goes by Andy who is co-inventor of latent diffusion the technique that eventually got scaled up by stable diffusion and stability AI and they eventually split with a bunch of uh the core stability AI image gen folks to form blackforce labs and Dustin Podell who I also met with an uh at one of the stories that we tell and who worked his way up from just being a regular engineer a freelance like web developer person into a model and research lead at stability AI and now uh blackforce Labs, creator of SDXL, Control Laura, post training lead on SD3, Flux Ultra, Flux 1, and Flux Context, and we go into all of these details. Um, as you may know, sometimes we're very honored to have an extended history with some of our guests, and this is one of them. You might have heard in our Anjida episode where we talked about introducing each other at one of the neuropsises and meeting Black Forest Labs for the first time. And uh this is right after stable diffusion. But what you may not have heard and we only tell this story in this episode is how latent space itself was started because of stable diffusion directly uh crediting the launch for me basically quitting my job to go all in on AI based on what we saw. And today's guest Dustin also had that experience and so did Vivu. And so we have a very very strong tie with the team that basically led up to Black Forest Labs and now we're also interested in what's next for them like they have created some of the best open and closed weights models for image generation and video generation. I think especially flux context if you're not aware of image editing models. I do think that this is in the in the limit one of the things to fully replace Canva and um and Photoshop and a bunch of other workflows and editors that you might use in a normal creative workflow. It is not going to replace the top end of the market. But for regular normal everyday edits, why would you not want anything else other than to query your model and ask it to do image editing for you? Uh we do this obviously with this kind of video editing. It's all clanker done and I do review it and they're also moving into robotics. And so this ties in with a minieries of model labs that have been pursuing this direction building world models from image gen life with runway uh as well as um video models and now robotics models and so I think a lot of things rhyme in a lot of our recent episodes like even the artificial analysis episode that we're going to release soon they're also going to robotics and like it seems pretty obvious that when you see a whole bunch of smart people who are at the frontier all leaning one direction that you're probably 6 to 12 months out from some kind of really big breakthrough. This has been a consistent theme over my last four years of podcasting. It's not going to change now, so look out for it. Um, that's the most obvious call out I can make, but there's also a lot of interesting lore for people interested in the general diffusion space. U, we're going to do a little bit more over time. I'm thinking about an AIE LA where we talk about the generative media field and the creative arts and how uh the complicated relationship is evolving um and I think maturing to be honest. And finally, for those longtime listeners, uh we are starting to open up to advertisers, people that we really admire and respect and want to showcase what they're working on. Um the first one was with Superbase which I think a lot of you enjoyed and the second one today is brought to you by Dgram and you'll hear more from us at the midpoint of the episode. You should be showing a robot in action one time and then it should be able to do this and this would be truly a superhuman intelligence like at stability that we couldn't essentially leverage the value of what the models could be as well. Mistakes of not being able to actually capture the value of the models themselves. We raised all in all $450 million in funding so far. Currently the last that was published in uh December was more 100 million revenue. PFL was not founded to be an image generation lab. Video modeling is actually the central means to understanding how our world basically works. Maybe like 6 hours of training, 4 hours of train. It was it was very very short training run. And all of a sudden, like I saw what felt like a clear generality coming out of it because it was [music]
</details>

### 团队渊源与扩散模型溯源

>> 好，终于迎来了我们的 BFL 专题。欢迎两位，Andreas 和 Dustin。

<details><summary>Original English</summary>
>> Okay, finally our BFL pod. Welcome guys. Andreas and Dustin.
</details>

>> 很高兴来到这里，非常感谢。

<details><summary>Original English</summary>
>> Great to be here. Thank you so much.
</details>

>> 是的，太棒了，感谢邀请我们。我知道我们想聊这期已经聊了很久了。

<details><summary>Original English</summary>
>> Yeah, definitely. Thank you for having us. I know we've chatted about doing this for a long time.
</details>

>> 是的。我们之前请 Robin 上过几次节目，也就是在那时我在维也纳见到了你们。我想那是在某一届 ICML 上，或者……

<details><summary>Original English</summary>
>> Yes. So, we've had an on a couple times and that's where I met you at Vienna. I think one of the ICMLs or
</details>

>> 是不是其中一个……是不是那个屋顶活动，或者……

<details><summary>Original English</summary>
>> was this like one of the like was it was the like rooftop event or
</details>

>> 有一年维也纳接连办了两次大会。

<details><summary>Original English</summary>
>> there was a year where there were two Viennas back toback.
</details>

>> 对，对，对。

<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah.
</details>

>> 先是 ICLR，接着是 ICML。

<details><summary>Original English</summary>
>> That was first eye clear and then it was ICML.
</details>

>> 我真不知道他们是怎么搞定这事的。[笑声]

<details><summary>Original English</summary>
>> I don't know how they do this thing. [laughter]
</details>

>> 不管怎么说，当时你们刚刚准备推出 BFL，我们一起吃了顿饭，你们当时就说：“噢，我们正在考虑离开 Stability 之后下一步做什么”等等。总之恭喜你们。你们想怎样介绍自己呢？或许我们可以先来一段简明扼要的自我介绍。我叫 Andy，是 Black Forest Labs 的联合创始人。我开发扩散模型已经……哇，我想大概有七年了。我很早很早以前就认识了 Robin 和 Patrick。我想从我们在海德堡大学相识算起，到现在已经整整 7 年了。我原本来自德国，在那里我们开始研究图像领域的扩散建模。从某种意义上说，我们大家都有物理学背景，而把扩散这一普遍的物理现象映射到机器学习和生成建模上的这种范式，对我们来说有一种哲学层面的美感，这也是我们投身其中的原因。后来，我们开发了许多如今为扩散模型、图像生成、视频生成以及现在的动作预测提供支持的基础算法，我想我们稍后会聊到动作预测。

<details><summary>Original English</summary>
>> Anyway anyway uh and at the time you guys had were like just about to launch BFL like we had a dinner and like you were like oh we're thinking about what's next after stability and uh all that. So anyway congrats. How do you like guys like to introduce yourself? Maybe we'll sort of get a crisp uh self intro up front. So I'm Andy. I'm a co-founder of Blackboard Labs. Been developing diffusion models for oh wow I think seven years now. U met Robin and Patrick way way back in the day. I think it's yeah 7 years now since we met at H Highleberg. I'm from Germany originally and there we started looking into yeah just diffusion modeling for images. uh we're all having a kind of a physics background um in some sense and this this paradigm of just like mapping this general physical phenomena of diffusion to machine learning and generative modeling had a a kind of a philosophical kind of beauty to us that's why we got into this and then yeah developed a lot of the I guess fundamental algorithms that are powering diffusion models today or image generation video generation and also action prediction today I guess we'll talk about this later.
</details>

>> 我们会聊到的。是的，这其中的关联对于大家来说并不是一眼就能看出来的——从图像生成跨越到动作预测。

<details><summary>Original English</summary>
>> We'll talk about it. Yeah, of a kind related to it's not immediately obvious to people image generation to action prediction.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 但我们可以展开聊聊。另外我想提的一点是，很多人不知道这层关系：黑林山（Black Forest）是德国的一片森林，实际上是一座山脉，

<details><summary>Original English</summary>
>> but we can talk about that. Uh and then one thing I did want to comment is a lot of people don't know the relationship. Black Forest is a forest in Germany. It's a mountain range actually,
</details>

>> 不过，是的，它基本上是以德国的一个地区命名的。有趣的是，我和 Robin 在读博期间第一次相识，后来发现我们出生的地点相距大概只有 10 英里，这非常有意思，最终这也促使我们回到了德国。

<details><summary>Original English</summary>
>> but um yeah, it's it's a region in Germany basically named after and funnily Robin and me we we first met during our PhD and then we figured out we were actually born I don't know 10 miles away from each other um and that was that was pretty fun and then eventually that led us also to come back to Germany.
</details>

>> 太棒了。[笑声]

<details><summary>Original English</summary>
>> Beautiful. [laughter]
</details>

>> 整个欧洲看起来都像这副模样。

<details><summary>Original English</summary>
>> All of Europe looks like this.
</details>

>> 你能看到实验室正好就在那正中央。

<details><summary>Original English</summary>
>> You can see the lab right in the middle there.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的，是的。额……

<details><summary>Original English</summary>
>> Yeah. Yeah. Um,
</details>

>> 所以你们这样命名是因为你们来自这里。没错。我们这样命名是因为，其实当时我们成立了这个研究实验室，在那个时候我们基本上可以自由选择在哪里开展工作。没有人规定我们说，好吧，你们必须去旧金山或者其他什么地方。所以我们决定：好，我们实际上想从我们出生的弗赖堡开始做起，它基本上就在黑林山脚下，或者说是黑林山里的一座城市，事情就是这么来的，公司后来也就是在那里起步的。

<details><summary>Original English</summary>
>> so you named it because you're from here. Exactly. We named it because actually, um, we founded this research lab and back in the day we could basically pick where we wanted to do it. No one said us, okay, you have to come to say SF or whatever place. So we decided, okay, we want to be actually starting this at the place where we were born in Fryborg, which is like at the foot of the Black Forest basically or a city in the Black Forest and that's how it came and that's how uh then the company also started there.
</details>

>> 是的。CompVis 也在海德堡。

<details><summary>Original English</summary>
>> Yeah. Confis also H highleberg
</details>

>> CompVis 当时正是在海德堡，没错，我们就是在那里相遇的。后来我们搬到了慕尼黑，那全都是……

<details><summary>Original English</summary>
>> confis was in H highidleberg exactly that's where we met we then later moved on to Munich that was all
</details>

>> 也就是做出 Latent Diffusion 的那个团队。

<details><summary>Original English</summary>
>> which is the team that did lat diffusion
</details>

>> 都是在读博期间完成的，没错。就在那时，我们开发出了这种潜扩散算法。

<details><summary>Original English</summary>
>> through our PhD exactly and and that is when we developed this latent diffusion algorithm
</details>

>> 顺便说一句，我非常喜欢你们播客的名字 Latent Space，我其实很好奇这个名字是怎么来的。

<details><summary>Original English</summary>
>> I really like your name by the way your podcast name lat space I I I I would actually be curious how that came together
</details>

>> 我可以说说，我可以聊聊这个，不过你先请继续。

<details><summary>Original English</summary>
>> I can talk I can talk about it but yeah go ahead
</details>

>> 额，正是如此，我们当时在大学里开发了这种潜扩散算法，然后基于这个研究项目，我们对该算法进行了扩展，最终有效地引向了 Stable Diffusion。是的，从那以后，这就成了一段未曾停歇的探索旅程。

<details><summary>Original English</summary>
>> um and exactly we developed then this lat division algorithm at the university and then based on this research project we scaled bought the algorithm which led to stable diffusion um then effectively and yeah since then it's been a constant uh journey
</details>

<!-- chunk 2/14 -->

可以说是坐上了火箭，能有这样的经历真的超级、超级开心，而且我们还结识了像达斯汀（Dustin）这样非常棒的人。

<details><summary>Original English</summary>
on a rocket ship you could say which is super super fun to to have and we've met amazing people like Dustin as well um
</details>

>> 他算是我们这里最资深、而且我想也是最核心的研究人员之一了，不过对，我们稍后会更详细地了解这些。

<details><summary>Original English</summary>
>> who's who's one of the the kind of oldest and and like yeah most I think relevant researchers that we have but yeah we'll we'll learn more about that
</details>

### 潜在空间与命名渊源

>> 我们待会儿再好好夸夸他。我觉得潜在扩散（latent diffusion）以及广义上的变分自编码器（VAE）也是如此，对我们来说，Latent Space 就是这样一个总体的概念。甚至我们的 Logo 其实也是一个 VAE，它的理念就是你可以把事物转化到某些空间中，然后去探索与当今现有事物相邻的可能，接着你又可以某种程度上把它重新转化回来。

<details><summary>Original English</summary>
>> we'll guess him up later uh I think latent diffusion and just generally like VAE as well and and then for us Lin space uh is this general idea even our logo is actually a VAE and it's this idea that you can translate things into spaces and then explore things that are adjacent to what exists today um and then you can sort of re translate back
</details>

>> 我当时觉得，这对于创造力和生成来说真是一个太酷的洞见了，直到我深入研究 Stable Diffusion 之前，我都未曾真正理解过。Stable Diffusion 的发布改变了我的人生，我创办 Latent Space 是因为 Stable Diffusion，我辞掉工作也是因为 Stable Diffusion。噢，哇。

<details><summary>Original English</summary>
>> and I thought that it was like such a cool insight for creativity and generation that I never really understood until I studied stable diffusion like the launch of stable diffusion changed my life I started in space because of stable diffusion I quit my job because of stable diffusion Oh wow.
</details>

>> 因为我当时心想：好吧，我对 AI 的所有认知都是错的，因为我现在居然能在自己的笔记本电脑上运行它了。

<details><summary>Original English</summary>
>> Cuz I was like, okay, everything I know about AI is wrong because I can run this on my laptop
</details>

>> 如果我在这件事上判断错了，那我还在哪些事情上判断错了？

<details><summary>Original English</summary>
>> and like if I was wrong about this, what else am I wrong about?
</details>

>> 所以有这么一层原因。不过另外还有一层关系是和特里·普拉切特（Terry Pratchett）有关，我不知道大家知不知道。

<details><summary>Original English</summary>
>> Uh so there there's that. Um but then there there's another relationship with um Terry Patchet which I I don't know if people have
</details>

>> 这位作家，他提出了 L-空间（L-space）的概念，也就是图书空间（library space）。在幽冥大学（Unseen University）——那是一所巫师大学——里面有一只红毛猩猩担任图书管理员。那基本上是一个汇集了所有可能存在的书的图书馆。所以如果你拥有一个囊括了所有可能书籍的图书馆，你在理论上就可以直接走进去，找到一本适合你的书。而那就是潜在空间。

<details><summary>Original English</summary>
>> writer he has this concept of Lspace uh which is library space u where he has orangutan that's like the librarian in unseen university which is wizard university uh and it basically is a library with all possible books. So if you have a library of all possible books, you can just theoretically go in there and find a book that is right for you. Uh and that is lat space.
</details>

>> 所以我最初看到它时叫它 Lspace。后来我的一位读者把 latent.space 域名送给了我，于是就变成了 Latent Space。

<details><summary>Original English</summary>
>> Uh so I originally saw called Lspace. Uh one of my readers donated late in space and then became late in space.
</details>

>> 太神了。[笑声]

<details><summary>Original English</summary>
>> Amazing. [laughter]
</details>

### 达斯汀进入扩散模型领域的历程

>> 达斯汀，能聊聊你是怎么进入扩散模型以及整个 AI 领域的吗？

<details><summary>Original English</summary>
>> Dustin like uh yeah what was your journey into diffusion and AI in general?
</details>

>> 好，好。我的背景和安迪（Andy）、罗宾（Robin）以及团队其他人稍微有点不同。我不是来自德国那边的团队，但我和这些伙伴们合作得非常愉快。坦白说，听到你提到在 Stable Diffusion 发布时辞掉了工作，这挺有意思的，因为最初发布 Stable Diffusion 时我并没有和他们在一起工作，而它实际上也是促使我当时辞职的原因。所以我——你造成了大规模失业。[笑声]

<details><summary>Original English</summary>
>> Yeah. Yeah. So I I came from a little bit of a different background than than Andy and Robin and team. So I'm I'm not from the German side, but I've still had a fantastic time working with these guys. And uh honestly, it's funny you mentioned that you quit your job when stable diffusion came out because uh the original stable diffusion I was not working with these guys at and it was actually a cause for me to quit my job at the time. So I um you caused mass unemployment. [laughter]
</details>

>> 我其实很好奇，在 Stable Diffusion 发布时，究竟有多少人因此彻底改变了人生方向。我真的非常想知道它带来的连锁分支效应。不过我也不知道，我们可以做些理论上的推测。这确实超级有意思，因为在旧金山湾区这边，它产生了巨大的冲击。而在哪里呢？在当时我们待着的德国，在那一天——

<details><summary>Original English</summary>
>> I'm actually curious like the numbers of people that just like changed their life direction when stable diffusion dropped. I I would actually be very curious to know kind of the branching effects from that. But I don't know. We can we can theorize on it. That's actually super interesting because here in SF in the Bay it had this huge impact. Where is it? In Germany where we stayed back in the day that day,
</details>

>> 人们其实根本没怎么注意到，因为那里的人离这些东西太远太远了。当然在德国也有几个人参与了开源社区，

<details><summary>Original English</summary>
>> people didn't really notice it because like the people were so so far away from that. Like there are a couple of people obviously that that have been involved in the open source community also in Germany
</details>

>> 但绝大多数人并没有真正注意到 2022 年夏天的那次发布，这非常有意思。然后你再看看这里发生的一切，对我们来说，这种反差真的超级耐人寻味。

<details><summary>Original English</summary>
>> but the majority of people didn't really notice uh that drop in summer 2022 which was really interesting and then you see what happens here like yeah that that was to us that was really kind of super interesting.
</details>

>> 是的。不过不管怎样，我想介绍一下我的一点背景。在 BFL，我是早期加入的创始研究员之一，当时我们团队规模稍微大一些，我相信稍后我们会讲到整件事是怎么演变过来的历史。但我的背景传统上其实完全不在机器学习领域。我过去大概有 10 年左右的时间是一名软件研究或软件开发人员。到了 2020 年初，也就是 2020 年代前后，我开始对开源 AI 产生了极其浓厚的兴趣。我看到了生成对抗网络（GAN）以及其他生成媒体领域的早期工作，我一直在紧密跟踪。我自己也在私下里做一些实验，这让我感到非常兴奋。我记得我最初关注的是潜在扩散（latent diffusion）的工作，我一直在跟进，并对此感到非常兴奋。然后，其中一件让我觉得“好吧，这也许是一件更严肃、更有分量的事情”的契机，其实是向 Midjourney V1 致敬。

<details><summary>Original English</summary>
>> Yeah. But but anyway, so I I guess to give a little background on me, so I I uh at BFL, I uh I'm one of the founding researchers that joined in with the uh we had a bit of a larger team that I'm sure we'll get into the history of kind of how that all came to be. But my background is not actually traditionally in, you know, the ML space whatsoever. I was traditionally a software research or a software developer for, you know, around 10 years or so. Early in 20, you know, around the 2020s, I became very very interested in just like open source AI. I saw like the kind of the early work in GANs and other you know in generative media and I was tracking with it. I was experimenting with it a little on the side. It got me quite excited. I mean and I remember following originally the the late infusion work. I was actually I was I was following that and quite excited about it. And then uh the one you know one of the things that kind of tipped me off to go okay maybe this is something a little bit you know a little bit more serious is actually uh shout out to uh Midjourney V1.
</details>

>> 哇。在它刚发布的时候，我记得当时就在想：好吧，这确实正走向一个方向，我能预见到这会产生相当大的影响。随后真正为我彻底改变一切的那个重大时刻、那次重磅发布，正如我们聊到的，就是 Stable Diffusion 的发布。当时我在洛杉矶的一家软件工作室工作，Stable Diffusion 一出来，我基本上当天就递交了辞呈，心想：好吧——

<details><summary>Original English</summary>
>> Wow. um back when that came out and I I remember thinking like okay this this is actually going in in a direction I I can see this being quite impactful and then the one big moment the big drop that really changed everything for me as we talked about was the stable diffusion release and at the time I was working at a software studio down in Los Angeles stable diffusion came out and basically that day I turn in my resignation and said okay
</details>

>> 当时的计划是什么样的？

<details><summary>Original English</summary>
>> what was what was the plan like
</details>

>> 计划嘛，我当时看待它的方式、我脑海中勾勒的景象是：我看到了这个东西，感觉它完全就像是横空出世的一个魔法，我认为正在从事这项工作的人一定是奥术巫师，我必须竭尽所能去弄清楚他们到底注入了什么样的魔法、符文或技术，才让这一切发生，并把它推向世界产生如此巨大的影响。我当时也不是完全与世隔绝，我在 Stable Diffusion 的 Discord 群里，我在里面甚至有朋友，一直在与社区互动。那么当时大家是把它看作开源版的 Midjourney，还是说大家并没有做这种——

<details><summary>Original English</summary>
>> the the plan so so the way the way that I saw the way that I like envisioned it at the time I saw this thing that felt like it literally felt like a magical thing that came out and I viewed okay the people that are working on this must be like arcane wizards and I need to do whatever I can to understand like what magic or what runes or what things that they did to imbue in this to make this happen and let this go out to the world and have this have this impact. It wasn't like I was just totally disconnected at the time. I was in the stable diffusion discord. I actually had friends in there. I was I was kind of interacting with the community. So when was it viewed as basically open source majourney or like like do people not make
</details>

>> 我两个群都在。我记得当时有很多诸如此类的讨论，比如“噢，Stable Diffusion 正在产生如此深远的……”你知道，当时有非常多的讨论。我还记得那时候 Midjourney 的 Discord 和 Stable Diffusion 的 Discord 都在讨论它所产生的影响。事情过去很久了，所以我记不清确切的——

<details><summary>Original English</summary>
>> there was I mean I I was in both I remember there were a lot of kind of uh discussions around this like oh stable diffusion was it's having such a you know there there was a lot of discussion and I remember the midjourney discord and the stable diffusion discord around that time around the the impacts it was having I mean it's been a long time so I can't remember the exact
</details>

### Discord 社区生态与 BFL 团队成型

>> 确切细节了，我也不想妄加评论。你看，Midjourney 现在发展得很好，他们做得——我是说[笑声]他们做得棒极了。但对我来说，我当时更关注的是底层技术本身，以及我现在可以在家里自己运行它这一事实。然后我真正看到的，是这整个开发者社区把它带回家并在上面进行开发。我自己也在上面不断钻研折腾，结识了一大批非常聪明、优秀的人，其中有些人现在也来到了 BFL，一起踏上了这段旅程。仅仅是那种社区互动、共同学习、开发和构建的时刻，对我来说就产生极为深远的影响。对我来说非常幸运的是，我当时抓到了一个工作机会加入到了 Stability，正好赶上了这一切的起步阶段。我其实并不是一开始就和他们几位共事，我是花了一段时间才一步步参与进来的，如果我们愿意的话，稍后也可以聊聊那段历史。

<details><summary>Original English</summary>
>> nature of it I don't want to speak on you know journey is doing fine like they're doing I mean [laughter] they're doing great um but for me it was more just like I was very interested in the fundamental technology and then the fact that I could now run this at home and then really the thing I saw was then just this community of developers actually like taking it home developing on it. I was hacking away at it. I was meeting a bunch of other really really smart great people some of which are actually at BFL now that have have come along for the journey. That moment of just community interaction and and learning and developing and building together was really an impactful moment for me. Lucky luckily enough for me I was able to find a kind of a job opportunity to get myself into stability at the time where uh you know that this this was starting and it it I didn't actually start working with these guys right away. It took me a while to kind of to kind of work my way up to that and we can go into that history later if we want.
</details>

>> Stability 当时有好几个不同的团队，对吧？语言模型、Stable Music——

<details><summary>Original English</summary>
>> Stability had a bunch of different uh teams right LM stable music
</details>

>> Harmoneai 音频团队。那时候感觉就像——我不知道该怎么形容——就像是你抓了一帮人……Discord 算是当时很多事情发生的集聚地。我[笑声]不知道，我不知道为什么整个——

<details><summary>Original English</summary>
>> harmony the audio team. It was it was like I don't know the way I would kind of describe it is like uh if you grabbed a bunch of Discord was kind of the space that a lot of this happened at the time. I [laughter] don't know. I don't know why the whole
</details>

>> 就像是一个 Discord 社群化为了实体形态。那是一个汇聚了形形色色不同背景的人的大熔炉，大家聚在一起，仅仅是因为对这项——

<details><summary>Original English</summary>
>> It's like if a discord had it was a physical manifestation. It was a melting pot of very different people that came together. We're just like interested in this
</details>

>> 涌现的新技术产生了浓厚兴趣。显然，这也是我们团队——这是我们团队、我们的创始团队最令人兴奋的特质之一：

<details><summary>Original English</summary>
>> emerging new technology that came obviously and that's also how we like this is one of the most exciting things about our team, our founding team is
</details>

>> 它由截然不同的背景交汇而成。比如我们有纯正硬核的学术研究分支，同时我们也有来自开源社区的人，比如达斯汀，他是通过一种完全不同的轨迹进入这个领域的。

<details><summary>Original English</summary>
>> it comes from very different backgrounds. like we have this hardcore academia research branch and then we have people who were from the open source community like like Dustin um who actually got why a very different kind of trajectory into this space
</details>

>> 但我认为正是这一点让我们团队如此强大。我们拥有这些多元的背景，而且我认为很少有团队拥有这样的历程，特别是这样一段共同走过的经历。

<details><summary>Original English</summary>
>> but I think this is what makes our team so strong. We have these diverse backgrounds and there's yeah there's rarely a team I think that that has this history also this kind of joint history together.
</details>

>> 是的，没错。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 这真是太不可思议了，那种——

<details><summary>Original English</summary>
>> This is just amazing that that like
</details>

>> 是的。我们可以先多聊聊你们的其他几位联合创始人。我之前做过一期。当时我也身处那个领域，对吧？说真的，你知道，我也曾是一个非常——

<details><summary>Original English</summary>
>> Yeah. And we can go into more of your other co-founders first. Uh I I did one. So I was also in that space, right? Like literally, you know, I was also a very
</details>

<!-- chunk 3/14 -->

受 Stable Diffusion 的影响。我走错了路。
<details><summary>Original English</summary>
influence of stable diffusion. I did the wrong thing.
</details>

>> 我基本上走了 ComfyUI 这条路，为 Stable Diffusion 构建用户界面。你似乎走对了路，走向了研究方向。
<details><summary>Original English</summary>
>> I basically went down the path of comfy UI where I build UIs for stable diffusion. You seem to have done the right thing where you went to research.
</details>

>> 很有意思你提到了 Comfy，因为我以前直接和他共事过，我是说 Comfy 加入……开过播客。是的。我觉得他搬到了这里。
<details><summary>Original English</summary>
>> Well, it's funny you mentioned Comfy cuz like I used to work directly with I mean comfy join had the pod. Yeah. I think he he moved here.
</details>

>> 是的，是的。他就像我的邻居一样。
<details><summary>Original English</summary>
>> Yeah. Yeah. He he's like my neighbor.
</details>

### 从开源探索到全职研究

>> 怎么……他是一名研究员。你是怎么成为一名研究员的？[笑声]

我这个人就是，一旦对某件事产生兴趣，就会痴迷到放不下的地步，非要把把它拆解开、搞清楚它的方方面面不可。所以对我来说，我当时已经在尝试拆解模型，并与那个开源领域的很多人交流。不仅包括开发者，还有其他研究人员。我是说，还记得谈到另一个 Discord 社区，你知道，当时的 Luther Discord。那时我结识了很多人，我一直在向他们学习，读了很多论文，只是努力去吸收并为自己弄明白。

加入 Stability 对我来说也是另一个重大节点。最初我并不是作为研究人员加入的，我是作为工程师加入的。但我所有的空闲时间基本上都花在了任何我能结交的研究人员身上。你知道，向那里的 Scott Holly 博士致敬，他在音频团队工作，在那里给了我很多指导。在某个时刻，我设法溜进了那里的集群，让自己获得了一些闲置算力的访问权限。

而且我真的就是——我对待它的方式就像我学大部分东西一样，也就是开源黑客式的探索、尝试各种东西、读论文、尝试实现不同的工作成果，看看模型是如何训练的、它们是如何学习的，我不知道。我的意思其实就是这样，并没有什么神奇的秘诀，只是我感到很兴奋，只是想去了解它。我想把它拆开，直到我弄明白它是如何工作的。
<details><summary>Original English</summary>
>> How does a He's a researcher. How do you become a researcher? [laughter]

I'm someone that's like when I get interested in something I am obsessive to the point of I cannot put it down until I pull it apart and figure out every aspect of it. And so to me I'd already been experimenting with pulling the models apart talking to a lot of different people in that open source space. So not just like developers but other researchers. I mean remember talk about another discord the you know the Luther discord back then. At that time I met a lot of people who I were I was just learning from and I was reading a lot of papers and just trying to uptake and understand for myself.

Joining stability was also another major point for me. Originally I didn't join as a researcher. I joined as an engineer. But all of my free time I spent with essentially any researchers I was able to make friends with. You know shout out to uh Dr. Scott Holly there who worked on the audio team who mentored me quite a lot there. And at some point I was able to to sneak my way onto the uh onto the cluster there and got myself access to you know some idle compute.

And I I I really just like I treated it like I treated how I learned most things which is just open source hacking trying things reading papers trying to implement different pieces of work and just seeing how I don't know how models trained how they learned and and I mean that was really it like there was there was no magic to it other than just I was excited and I just wanted to learn about it. I wanted to tear it apart until I understood how it work.
</details>

>> 我的意思是，这就是开源的最佳体现。
<details><summary>Original English</summary>
>> I mean this is open source at its best.
</details>

>> 是的。我认为通常最好的学习方式就是亲自去尝试各种东西，而且他当时也……
<details><summary>Original English</summary>
>> Yeah. I think that that's generally how you learn best just trying out things and he was also
</details>

>> Luther。
<details><summary>Original English</summary>
>> Luther.
</details>

>> 是的。是的。有关联，但不是在图像生成这边。不过在当时，一切都非常容易上手魔改，对吧？开源模型之间的差距就像是……
<details><summary>Original English</summary>
>> Yeah. Yeah. affiliated but not on the uh image gen side. But back then everything was like very hackable, right? The the delta between open models was like
</details>

>> 在闭源且优秀的模型与开源模型之间的差距相当巨大，对吧？所以语言模型领域的人在做后训练。很多搞 news 的人就是从这里起步的。你知道，你可以看看早期的 Stable Diffusion。
<details><summary>Original English</summary>
>> pretty drastic between what was closed and good, right? So people on language model side were doing post training. That's where like a lot of the news guys started in this. You know, you can look at early stable diffusion.
</details>

>> “这看起来太糟糕了”，然后……
<details><summary>Original English</summary>
>> This looks so bad and
</details>

>> 看看我们今天达到了什么水平。这真的很疯狂。但你们两位都扮演了非常具有影响力的角色。比如你做了 SDXL，你做了 latent diffusion。我们会回顾所有的历史，但是……
<details><summary>Original English</summary>
>> where we get to today. It's pretty crazy. But you both had pretty, you know, impactful roles. like you did SDXL, you did latent diffusion. We'll get through all the history, but
</details>

### 迈向视觉智能与系统 1

>> 对于那些没有密切关注这个领域的人来说，我们今天处于什么阶段？现状是什么样的？我知道 Flux 3 视频已经推出了。Flux 3 Action，我们现在就像用 7B 模型来做机器人技术。你们在这个领域的最新进展是什么？

我们创办 Black Forest Labs 时，最初是一个图像生成实验室，对吧？作为某种 Stable Diffusion 及类似成果的延续。我认为这曾是我们第一年的重心，但随后我们意识到，图像生成固然不错，但这项技术可以解锁多得多的东西。
<details><summary>Original English</summary>
>> for people that haven't super followed the space, where are we today? Like what's the what's the state of things? I know Flux 3 video is out. Uh Flux 3 Action, we're now like 7B doing robotics. What's the latest in the space with you guys?

We started as an image generation lab when we started Black Forest Labs, right? As a kind of legacy of stable diffusion and the likes. Um and that has been I think our our thing for the first year but then we realized okay you actually image generation is nice but this technology can unlock so much more.
</details>

>> 嗯。那时我们开始慢慢转向我们所谓的视觉智能，这基本上就是试图获得我们人类所拥有的直觉智能——比如当我们接球时，我们理解物理规律，却不一定知道如何用数学方式去描述它；或者当我们抓起一个瓶子时，我们准确地知道该怎么做，因为我们在童年时期已经做过成千上万次，也许没有十万次，我不知道，但做过很多次，对吧？我们希望将这种知识、这种与语言模型智能截然不同的智能形式，转化为基于像素学习的模型，这意味着不仅是图像，还包括视频，或许还有音频——与其说像素，不如说自然信号可能是个更好的术语——
<details><summary>Original English</summary>
>> Mhm. And that's when we slowly went into what we call visual intelligence, which is basically trying to get our intuitive intelligence that we people have when we say when we catch a ball and just understand physics without actually knowing how to mathematically describe it or something or when we grab a bottle and just know exactly how to do this because we've done it 100,000 maybe not 100,000 times, I don't know, but a lot of times in in our childhood, right? We want to be transforming that knowledge and that form of intelligence which is very different from language model intelligence into models and learning based on pixels which means not only images but also videos and maybe also audio say not pixels but natural signals is maybe a better term
</details>

>> 这真正开启了这一领域，这就是我们所意识到的。我们意识到，我们拥有真正能实现这一点的算法，那就是扩散或流匹配（flow matching）。正是从那时起，我们说好，我们需要拓展，从图像生成拓展到基本上所有的自然表征，这基本上催生了 Flux 3——一个从图像、视频、音频以及动作中进行多模态学习的单一模型，我们稍后可以讨论这些是如何整合在一起的——
<details><summary>Original English</summary>
>> that really unlocks this and that is what we realized and we realized hey we have the algorithm to actually do this which is diffusion or flow matching and that is when we just said okay we need to extend and from image generation to basically all the natural uh representations which led to flux 3 basically which is one model that learns multimodal from images videos audios also actions we can talk about how this comes together later
</details>

>> 真正实现这一点，套用 Daniel Canaman 的说法——我不知道你是否读过《思考，快与慢》——它是一种系统 1 智能，而不是系统 2 智能，你或许可以……
<details><summary>Original English</summary>
>> to really get this to to keep it with Daniel Canaman I don't know if you read thinking fast and slow it's a kind system one intelligence it's not system two intelligence that you could maybe
</details>

>> 现在是系统 1 模型了。
<details><summary>Original English</summary>
>> system one models now
</details>

>> 可……[笑声] 也许语言建模是系统 2。
<details><summary>Original English</summary>
>> may [laughter] maybe language modeling is system two
</details>

>> 但我们目前专注于系统 1，这对于所有直觉性的、需要与现实世界交互的事情都极其重要。这就是为什么从高层次来看，它也如此适用于机器人技术。这就是我们经历的历程，现在我们真正专注于此，最终显然是要把这两个系统结合起来，形成我们人类也拥有的这种广泛、非常广泛的智能方式。
<details><summary>Original English</summary>
>> but we focused for now on system one which is extremely important for everything that is intuitive and that requires real world interaction. That's why at on a high level it's also so good for robotics. So that's been the journey and now we're really focusing on that and in the in in the end obviously um it's about combining both of these systems into this broad very very broad way of intelligence that we humans also have.
</details>

### 融资规模与世界模型争议

>> 我想深入探讨一下历史和所有这些事情。但为了让前面的听众了解概况，作为一家生成式媒体公司，你们已经赚了相当大一笔钱了，对吧？我不知道具体数字是多少，也许你可以在这里概述一下。你们……
<details><summary>Original English</summary>
>> I want to go into sort of uh history and all these things. Uh but just to also recap for the for people at the front, you're already making a significant money as a generative media company, right? Um I don't know what the the numbers are and and maybe you can sort of recap there. You
</details>

>> 筹集……你们筹集了一笔多得惊人的资金。到目前为止，我想我们总共筹集了 4.5 亿美元的资金。
<details><summary>Original English</summary>
>> raised you raised a ridiculous amount of money. We raised I think all all in all $450 million in funding so far. Um
</details>

>> 是的，所以比 Stability 多得多。有什么已经公布的收入里程碑吗？目前公布的最低数据，最近一次是在 12 月发布的，是突破了 1 亿美元营收，从那时起我已经可以……[笑声]
<details><summary>Original English</summary>
>> yeah, so there's way more way more than stability. Uh any revenue milestones that you've that you've announced? kind of the lowest currently the last that was published in uh December was 100 million in revenue crossed that since I can can [laughter]
</details>

>> 如果你融了 4.5 亿，显然肯定是超过了那个数字，确实如此，你知道的。无论如何，我只是想说，你们并不需要转型……
<details><summary>Original English</summary>
>> clearly clearly have crossed that if you raise 450 exactly you know yeah anyway I'm just saying like you did not have to pivot
</details>

>> 需要明确的是，我们并没有转型，我们只是在拓展。就像这个模型，它确实是在所有数据上训练出来的。
<details><summary>Original English</summary>
>> and to be clear we're not pivoting we're just extending like this this model is really it's trained on everything
</details>

>> 这一直都是计划之中的。
<details><summary>Original English</summary>
>> there's always been the plan
</details>

>> 显然，要创作艺术作品，你也需要这种视觉智能，来制作我们在这里看到的视频。
<details><summary>Original English</summary>
>> and obviously to to create artworks you also need this visual kind of intelligence to create a video that we see here
</details>

>> 你需要知道物理规律是如何展开的。我需要知道……模型需要理解这其实很有意思。但是，模型需要理解，比如这只水豚的手臂并没有直接掉落脱离，它必须遵循由物理学所描述的某种定律。它只是并没有在描述定律本身，它只是在描述输出结果，就像我们人类不懂物理学，但我们懂得如果我让球掉落，它就会向下掉一样。

对的。是的。我认为世界模型有不同的概念，显然我们可以探讨这一点：你是在哪里学到这一点的？这有点像“苦涩的教训”（bitter lesson）版本，即你只是在一堆输入源上学习；还是你必须在物理上实际构建 3D 模型的结构，并以此来进行某种学习？
<details><summary>Original English</summary>
>> you need to know that how physics play out. I I need to know that the model needs to understand this is actually interesting. Uh but but the model needs to understand that the arm of this say this this this capibara or what it is is not just falling away that it has to follow some law that is described by physics. It's just not describing the law itself. It's just describing the output in a similar way that we humans don't understand physics but we understand that if I let a ball fall, it just falls down. Right. Yeah. Well, I think there's there's different concepts of a world model and obviously that's something that uh we can get into where can you learn this is sort of the bitter lesson version where you just learn on a bunch of input sources or you have to actually physically structure the 3D model and and kind of learn from that
</details>

>> 完全没有 3D 模型，仅仅基于自然数据进行学习。我们也有一些三角测量，就像来自我们的眼睛一样，对吧？我们有两只眼睛，这赋予了我们对 3D 感知的一点理解，但实际上在很大程度上，即使你闭上一只眼睛，我们仍然可以了解很多关于这个世界的信息。这基本上就是这些模型正在学习的东西：你直接从自然数据、2D 视频数据中学习，而这些数据显然包含了很多 3D 理解，因为如果你想生成围绕一个物体的平移镜头，你就需要能够想象出它从背面看是什么样子的；如果我看着你，我基本上对你的后背长什么样有一个很好的理解。
<details><summary>Original English</summary>
>> no no 3D model at all just learning on based on natural data. We we also we have a bit of triangulation like from our eyes right we have two eyes and that gives us a kind of slight understanding of 3D perception but effectively to a very large extent even if you would like close one eye we could still kind of learn a lot about the world that is what these models are basically learning like you just learn from natural data 2D video data that obviously has a lot of 3D understanding because if you want to generate a pan around an object you need to be hallucinating how it looks from behind and if I look at I have a pretty good understanding of how your back looks basically.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah,
</details>

>> 因为我以前见过，对吧？所以，这赋予了你一种隐式的 3D 理解。
<details><summary>Original English</summary>
>> because I've just seen it before, right? So, this is gives you an implicit 3D understanding,
</details>

>> 但它确实是在 2D 视频上训练出来的。
<details><summary>Original English</summary>
>> but it's really trained on kind of 2D videos.
</details>

>> 是的。我在试着借用对立的观点，反面观点，对吧？比如像 Gary Marcus 那种“AI 什么都没学会”，或者我都忘了这类观点的著名批评者都有谁了，但基本上就是说，这就好像模型从未真正生活过，我作为一个模型只能看到输入，我从未……我没有……
<details><summary>Original English</summary>
>> Yeah. I'm trying to steal the counter argument, the the opposite argument, right? Like this like the Gary Marcus like I'll don't learn anything or I I forget who are the famous critics of this kind of stuff, but basically it's like it's like I have never lived I as a model I only see on inputs. I've never I don't
</details>

<!-- chunk 4/14 -->

……有亲身体验。你可以对我的后背建模，因为你也是人类，而且你也可以对其他人类建模。不过，可能这种类比也不完全准确，因为我显然是很赞同你的立场的，但我觉得人们之所以批评这种世界建模方法，原因就在于：没错，你可以越来越逼近、越来越逼近，但你永远无法触及该事物存在的核心本质，因为你从未对事物本身建模，你建模的只是围绕该事物最可能的某种约束。
<details><summary>Original English</summary>
have personal experience. you can model my back because you are also a human but and you can model other humans but and maybe maybe this analogy isn't isn't exactly correct because I was obviously I'm sympathetic to your your side of the story but like I I think that is how people criticize this approach to world modeling which is that yes you can approximate closer and closer closer but you'll never quite get something core to the to the existence of the thing because you never modeled the thing you modeled uh uh the most likely you know uh sort of uh constraint around the thing.
</details>

>> 是的。我是说，在某种程度上你也可以认为我们也是按同样的原理运作的，对吧？你可以说，好吧，我们有具身实体，我们不断地接收数据，而且显然我们也在定期更新，但从某种原理上讲，我们仍然只是在接收这些来自世界的经过过滤的信号。我是说，我们的眼睛在处理信号时存在各种古怪的情况，我们的大脑某部分甚至不得不去“脑补”（幻觉）出一些信息，因为我们视野中心有盲点等等。但从根本上讲，我认为我们在这边接收这种自然数据并构建一个我们能据此行动的世界模型，与这些模型从数据中学习，这两者之间其实没有那么大的区别。显然信号的形式是不同的——它们被转换成了像素，或者声波，并通过其他途径处理——但信息依然存在，模型依然可以吸收这些信息并构建出这种世界的表征，从而基本上让你能基于它来进行操作。
<details><summary>Original English</summary>
>> Yeah. I mean, I I think to some degree you could argue that we operate under the same principle, right? Like you can say like that we are, you know, okay, we have this embodiment. We're constantly like taking in data and like obviously we we regularly update, but in some principle like we're still just taking in these like filtered signals from the world. I mean, there's all sorts of wacky things with how our our eyes process and we have to, you know, part of our brain kind of has to hallucinate some of the info because we have the blind spot in the center and and and other aspects of this. But fundamentally like I don't think there's that much of a difference between you know how we like we're we're out here taking in this natural data and building this model of the world that we're we're able to act on versus like these models also learning from. Obviously, it's the signals are different that they're, you know, okay, they're turned into to into pixels or, you know, into into waveforms and process through this other mean, but like the the information is still there for the model to take in and build this like representation of the world that then you can essentially operate with.
</details>

### 人类学习中的观察与交互

>> 是的，我其实之前还在和 Lucas Bayer 争论过这点。他现在应该是在 Meta，之前在 Google 和 OpenAI。他在苏黎世，离弗赖堡（Fireborg）挺近的，他时不时会过来。我们当时在讨论人类学习的问题——我们当时在说，好吧，我们其实不需要交互，而交互在我看来对学习更高级的智能形式是很重要的；最开始是观察，这也是我们人类婴儿时期的学习方式，对吧？我们一开始只是躺在那儿观察事物，单凭这点我们就学到了很多东西。这其实可以完全对应到我们目前训练这些模型的方式，它们只是观察大量的 2D 视频、音频，然后从中学习。而我认为下一步将是闭环到真正与世界交互，因为我也认为这在我们认知周围世界的基本学习方式中非常重要。我们可以去敲敲碰碰，然后发现，噢，这两者之间存在关联——
<details><summary>Original English</summary>
>> And yeah, I was actually arguing this with Lucas Bayer. Uh he's also um he's with Meta now, I think, formerly Google um and OpenAI. He's in Zurich, which is pretty close to Fireborg, and he he's coming over from time to time. We were we were debating this um on on human learning like he was he was we were saying okay we actually don't need interaction which would be kind of the I think what I would say is important for learning like higher forms of intelligence it's like first it's observation that's also how we humans learn when we're babies right we just lie around first and we we observe things and from that alone we learn so much this is what what you can actually exactly map to what how we're currently training these models they just observe a lot of 2D 2D videos, audio and then they learn from it. And I think next step would also be getting closing the loop to actually interaction with the world because that's also in how I think that that's very important in how how we learn basically around the world. We can then tap and we see oh there's a correlation between
</details>

>> 比如我敲击木头，就会伴随发出声音，对吧？我就可以通过操控世界来更好地理解它。我认为人类主要就是这样学习的，至少我个人是这样学的。而他其实说他认为大部分是靠观察，我觉得这非常有意思，因为如果真是那样的话，我们只需要加大力度做目前正在做的事情，那基本上就能释放出极其惊人的……
<details><summary>Original English</summary>
>> I knock on wood and there's a sound attached to it, right? I I can just like manipulate the world then and to to understand it better. That's how I think how humans are mainly learning at least how I personally learned. Um and he was actually saying he thinks the majority is observation which I found very interesting because uh that would that would if if that would be true then we just need to do what we're currently doing more and that could basically unlock uh an insane
</details>

>> 涌现量，只要有良好的先验。对吧？我们已经看到，给语言模型增加新的模态，并不会因为加入了视觉就获得性能翻倍这种完整的收益，但如果你有良好的先验，是有微小的收益，还是巨大的收益？这很值得观察。我认为有很多技术层面的东西梳理起来会很有意思。比如高斯泼溅（Gaussian splatting）曾是一件大事，World Labs 做了很多 3D 数据。视频生成输出与其他方案之间的权衡在哪里？不过我觉得对播客听众来说，聊聊历史会很有意思。你参与过非常早期的 Stable Diffusion、SDXL，甚至在此之前的 Latent Diffusion，
<details><summary>Original English</summary>
>> amount of this is like emergence with good priors right we've seen adding new modalities to say language models you don't get like the full benefit of you know doubling your performance since you've added vision to a language model but if you have good priors um you know is there light benefit. Is there a big benefit? It's it's interesting to see. I think there's a lot of technical stuff that'll be interesting to walk through. Like gshian splatting was a big thing. World Labs did a lot of 3D data. Where are the trade-offs between video generation output versus what else? But I think something fun for listeners of the podcast would be the history. You worked on, you know, very early stable diffusion, SDXL, latent diffusion even before that,
</details>

>> 还有 Video Diffusion。
<details><summary>Original English</summary>
>> video diffusion as well.
</details>

>> 还有 Video Diffusion。这里基本上有大量的流行热词。比如 LCM、LoRA、流匹配（flow matching）、旧式提示词工程，你能把这一切都教给我们吗？[笑声] 不是，有意思的是，这些缩放定律（scaling laws）到底有多强？
<details><summary>Original English</summary>
>> Video diffusion. Basically, there's a lot of buzzwords here. um you know LCM Laura flow matching old prompting can you teach us everything [laughter] no what's interesting like how big are these scaling laws
</details>

### AI 技术树与 SDXL 的演进

>> 我其实做过一个类似科技树的东西。我想做一款类似于《文明》的游戏，但里面的科技树是 AI 的核心论文，你可以消耗研究点数去解锁它们。科技树大概就是这样：一开始是 GAN，然后……等等，接着扩散模型就出现了，但在那之外还有很多核心节点。
<details><summary>Original English</summary>
>> so uh I've actually built like a tech tree like I wanted to build this game where it's like civilization but the tech tree is AI uh like key AI papers so to spend research points and get it and so like these are the tech trees right like first it's GANs then uh you know dot dot dot like the indiffusion happened but you like there's a lot of core points beyond that.
</details>

>> 我会玩那个游戏的。[笑声]
<details><summary>Original English</summary>
>> I'd play that game. [laughter]
</details>

>> 好的，不管怎样，简单介绍一下这个游戏：你扮演一个 Neolab 角色，你必须把预算花在 GPU 或研究人员上，然后[笑声]你得收集数据，而且还有所有这些零碎的技术细节可以去研发。是的。
<details><summary>Original English</summary>
>> So, so, so, okay. Anyway, just to pitch the game, it it's like you role play as a Neolab and you have to you have to spend on like uh GPUs or researchers and then [laughter] you have to collect data and like there's there's all these like little things that you can research. Yeah.
</details>

>> 得了吧，赶紧做出来。我们现在身处 V……[笑声] 编程的世界。我明天就想玩上。
<details><summary>Original English</summary>
>> I come on, whip it up. Let's we're in the V [laughter] coding world. I want to play it tomorrow.
</details>

>> 事实证明，我觉得游戏平衡非常难做，因为……你们玩过吗？我已经把它做出来了。
<details><summary>Original English</summary>
>> It turn I think uh game balance is really hard because I had you guys played I I have I I've built it.
</details>

>> 噢，太棒了。但是游戏平衡真的很难。我觉得这简直就像个 AGI 级别的难题，因为一旦你找到了一种获胜途径，就总是能那样赢，作为游戏来说就没意思了。你需要多种获胜方式，而且需要一些高风险的方式——你大概率会输，但也可能会赢。
<details><summary>Original English</summary>
>> Oh, fantastic. But uh there's like game balance is really hard. It's actually like a AGI hard problem I feel like because you know once you find a way to win they just always win like that and it's not interesting as a game. You need multiple ways to win and like you need high-risk ways to you probably lose but maybe you win.
</details>

>> 是啊。顺便说一句，这也是 dance 里面地图的经典问题。
<details><summary>Original English</summary>
>> Yeah. Maps classic problem in dance by the way.
</details>

>> [笑声]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 所以我觉得，VU 感兴趣、我也感兴趣的一件事，就是给我们的听众普及一下：如果你听过很多术语，那么真正对这个领域产生重大影响的关键节点都有哪些？而且你们很多……你亲身经历了其中的很多阶段。
<details><summary>Original English</summary>
>> So I think I think one thing that VU is interested in I'm interested in teaching our audience like like what are the key points that like if you're uh if you've heard a lot of terms like what are the key things that have really impacted the field and you know a lot of you have you've lived through a lot of
</details>

>> 我还想说，对于想要进入这个领域的人来说，这也是很好的面试题——如果你在招人的话也适用，就是你应该了解其中的大部分内容。我认为在某些节点上出现了一些很有争议或者不同的路线，比如自回归图像生成对比扩散模型、两种骨干网络，或者高斯等等所有这些东西。人们应该了解的关键点有哪些？我就不设限了，交给你来发挥。
<details><summary>Original English</summary>
>> I'd also say this is a great way for people that want to get into the space good interview questions if you're hiring as well like you should know most of these things I think there's some points where there's like spicy you know different paths that's popped up so auto reggressive image gen versus diffusion two backbones or glassions all these things. What are the key things people should know? You know, I'll leave it I'll leave it pretty blank.
</details>

>> 我觉得首先可以是 SDXL，也许可以先稍微聊聊 SDXL。我——
<details><summary>Original English</summary>
>> I mean, first would be SDXL maybe talking about SDXL a bit. I
</details>

>> 正想说我们在 SDXL 里都做了哪些事情？[笑声]
<details><summary>Original English</summary>
>> was going to say what were the what were the things we did in STXL? [laughter]
</details>

>> 噢，不。千万别提 refiner（精炼器）。
<details><summary>Original English</summary>
>> Oh, no. Please not the refiner.
</details>

>> 等等，为什么是这种反应？
<details><summary>Original English</summary>
>> Wait, why that reaction?
</details>

>> 要做个梳理的话，SDXL 是一项重头工作，它首次尝试让模型的使用体验变得真正好用。这倒不是说 Stable Diffusion 1 和 2 不好——我是说它们当时非常令人兴奋，用起来很有趣——但在 SD1 到 SDXL 期间身处该领域的任何人，都会看到开源社区涌现出了海量的工作，研究如何微调这些模型、如何让这些模型更具美感、如何让这些模型支持多宽高比……如果有人还记得的话，最初的 Stable Diffusion 只能生成正方形图像，因此 SDXL 是首次尝试去真正发布一个基础基座模型，在模型本身中内化融入很多这类通用的改进。SDXL 涵盖了——这是我们第一次进行大规模的多宽高比训练，当时在 packing 技术出现之前，有一种我们可以采用的高效方法，本质上是分桶式（bucket style）训练，也就是在大规模下对各种不同分辨率的图像进行训练；这是我们第一次真正划分多个训练阶段，即从预训练阶段推进到实际开发类似于后训练的数据集，所以在 SDXL 中进行了大量的数据工作；我正在回想所有其他方面……然后我会给你们讲一点关于 refiner 的幕后故事，也许还有一些未能最终合入模型的内容。这就是最终模型的整个过程——
<details><summary>Original English</summary>
>> So, SDXL was a big piece of work in trying to make the models feel good to use for the first time if I was to kind of like lay anything out. Not to say like stable diffusion one two weren't you know I mean they were very exciting they were very fun to use but uh to anyone that was like in the space at the time between the period of SD you know SD1 to SDXL uh we saw a ton of work out in the in the open source community working on how do we fine-tune these models how do we make these models you know more aesthetic how do we make these models into like you know multi- you know if any remember is like the original stable diffusions were only able to do square images and so SDXL was the first work of trying to actually release like a found like the base foundation model kind of with a lot of these general improvements implicit in the model. So uh SDXL involved you know the first time we did large scale uh multi-aspect training there was a you know at the time uh this was before uh packing there was like an efficient way we could do essentially bucket style training so training you know on all sorts of different resolutions of of images in you know a large scale this was the first time we did multiple actual training stages so taking it from pre-training actually developing like post-training sets so the there was a lot of data work that was done in SDXL all I'm trying to think like all the other aspects and then uh I'll I'll give you kind of like a little bit of a backstory on the refiner and maybe maybe some things that uh didn't quite make it in. So here here was the whole process of the final
</details>

<!-- chunk 5/14 -->

### SDXL 与 Refiner 架构

发布的模型本质上……SDXL 从根本上来说与最初的 Stable Diffusion 运作方式类似。它是一个潜空间扩散模型（latent diffusion model），接收文本输入。它有，你知道的，你有一个带噪潜变量，获取文本的上下文，实际在潜空间中生成图像，然后由 VAE 进行解码。在此之后，refiner（精炼器）实际上是另一个完整的扩散模型，它的全部目的基本上不是去处理粗糙的图像，而是因为 SDXL 在我们所谓的高频细节上并不是最擅长的——也就是像皮肤纹理、草地纹理这种精细细节的超分辨率。它并不是一个放大器（upscaler），因为它实际上并没有改变分辨率，但是它……它……

<details><summary>Original English</summary>
 release

 model

 is





essentially

 SDXL

 fundamentally

 worked





similar

 to

 the

 original

 stable





diffusions.

 It

 was

 a

 latent

 diffusion





model

 took

 in

 text.

 It

 had

 you

 know

 you





had

 a

 noisy

 latent

 took

 the

 context

 of





the

 text

 actually

 generated

 the

 you

 know





generated

 the

 imagery

 in

 latent

 space





and

 then

 a

 VA

 decoded

 it

 and

 then

 from





there

 the

 refiner

 was

 actually

 another





full

 diffusion

 model

 that

 the

 uh

 the





whole

 point

 of

 it

 was

 to

 take





essentially

 what

 was

 not

 a

 rough

 image





but

 SDXL

 wasn't

 the

 best

 at

 what

 we





would

 call

 high

 frequency

 detail

 which





is

 this

 like

 the

 fine

 detail

 like

 skin





texture

 texture

 of

 grass

 upscaling.

 It





wasn't

 an

 upscaler

 cuz

 it

 didn't





actually

 change

 the

 resolution,

 but

 it





it
</details>

>> 对，在细节层面上放大了，在某种程度上是对它进行了精炼。

<details><summary>Original English</summary>
>> yeah,

 upscaled

 in

 terms

 of

 in

 terms

 it





refined

 it.
</details>

>> 我之所以觉得它有点别扭，是因为我参与了这项工作——不仅是我，参与这个项目的整个团队都非常出色。我一点也不想把功劳全揽在自己身上，因为有很多非常优秀的人在这个项目上付出。我们做了大量工作，试图在保持这种通用性的同时提升模型的细节质量，但我们就是没有完全达到目标。于是就有了这样一个旁支工作：“好吧，还有什么其他方法可以做到这一点？”这就是 refiner 诞生的契机。实际上，refiner 原本是一个……这么说吧，这里面有一点不为人知的秘史：曾经有一个版本的 SDXL 从未发布过，那是一个不同的架构，效果没那么理想，但它已经训练到了相当靠后的阶段，甚至到了后训练阶段。refiner 就是那个模型，它是一个完整的扩散模型。

<details><summary>Original English</summary>
>> The

 reason

 I

 thought

 it

 was

 janky

 is

 cuz





I

 worked

 I

 not

 just

 me

 the

 whole

 team





that

 worked

 on

 this

 was

 was

 fantastic.

 I





don't

 want to

 take

 all

 the

 credit

 at

 all





cuz

 there

 were

 there

 were

 a

 lot

 of





fantastic

 people

 that

 that

 worked

 on





this.

 We

 did

 a

 lot

 of

 work

 to

 try

 to





push

 the

 detail

 quality

 of

 the

 model





while

 trying

 to

 keep

 this

 like





generality

 and

 we

 just

 didn't

 quite

 get





there.

 And

 so

 then

 there

 was

 this

 like





side

 track

 of

 work

 of

 like

 okay

 what

 are





other

 methods

 to

 do

 this

 and

 this

 is





where

 the

 refiner

 came

 into

 being

 with





actually

 the

 refiner

 was

 actually

 a





model

 that

 was

 it

 was

 what

 was

 supposed





to

 so

 this

 is

 a

 little

 bit

 of

 the

 secret





lore

 is

 there

 was

 a

 version

 of

 SDXL

 that





was

 never

 released

 uh

 it

 was

 a

 different





architecture

 that

 didn't

 quite

 work

 as





well

 but

 it

 was

 trained

 pretty

 far

 along





even

 to

 like

 the

 post-

 training

 stages





uh

 the

 refiner

 was

 that

 model

 it

 is

 a





full

 diffusion

 model
</details>

>> 你完全把那件事给忘了。

<details><summary>Original English</summary>
>> you

 completely

 forgot

 about

 that
</details>

>> 是啊，［笑］它……refiner 是一个完整的扩散模型，而那个模型的一个特点是，它在这些高频细节上的表现略好一些，只是它的结构生成能力非常差。于是就诞生了这样一个想法：如果我们基本上……

<details><summary>Original English</summary>
>> yeah

 [laughter]

 it

 like

 the

 refiner

 was





a

 full

 diffusion

 model

 and

 the

 one

 thing





about

 that

 model

 is

 it

 had

 a

 little

 bit





of

 better

 performance

 on

 these

 high





frequency

 details.

 It

 just

 had

 very

 poor





structure.

 And

 so

 this

 whole

 idea

 came





of

 like

 what

 if

 we

 essentially

 like
</details>

>> 不同的模型负责不同的任务。

<details><summary>Original English</summary>
>> different

 model,

 different

 job,
</details>

>> 不同的模型负责不同的任务。我们拿来那个模型，做了大量工作，切实推动了……你知道的，推动了它实际精炼这种高频细节的能力。然后我们构建了基本上这样一个流水线（pipeline）。对，这就是 XL 的那部分——

<details><summary>Original English</summary>
>> different

 model,

 different

 job.

 We

 we





took

 it,

 we

 did

 a

 lot

 of

 work

 to

 really





push

 the,

 you

 know,

 the

 work

 on

 how

 well





it

 could

 actually

 refine

 this

 high





frequency

 detail.

 And

 then

 we

 made

 this





this

 essentially

 this

 pipeline.

 Yeah.





Which

 is

 the

 XL

 part
</details>

>> 随后这就变成了：好吧，两者结合在一起是一个性能更强的模型，或者说整体上是一个性能更强的系统。接着那也就是我们最终在这里发布的东西。

<details><summary>Original English</summary>
>> which

 which

 then

 became

 okay

 this





together

 is

 like

 a

 more

 performative





model,

 you

 know,

 or

 a

 more

 performative





system

 altogether.

 And

 then

 that

 was





what

 we

 ended

 up

 releasing

 here,
</details>

>> 这实际上很有意思。那是早期的开创性工作之一，真正深入研究了在这个扩散轨迹中，到底哪一部分轨迹学习了什么样的特性。对吧，因为你是在……学习这些结构性特性的。

<details><summary>Original English</summary>
>> which

 is

 actually

 interesting.

 It

 was





one

 of

 the

 early

 pioneering

 works

 of





like

 actually

 that

 looked

 into

 okay

 what





kind

 of

 properties

 learned

 in

 which

 part





of

 the

 trajectory

 of

 this

 diffusion

 kind





of

 uh

 trajectory

 right

 because

 you

 have





these

 structural

 things

 that

 are

 learned
</details>

>> 越靠近噪声端——如果你越靠近噪声端，然后那些精细的、高分辨率的高频细节则是在更靠后的阶段出现，基本上更靠近纯净图像端。现在已经有一堆不同的书籍对这一点进行了分析，但实际上你的确……你沿着这条从噪声到纯净图像的轨迹生成时，是从低频走向高频的，对吧？但当时人们对此并没有真正的清晰认知，或者说到那时可能只是非正式地有一些了解。而这项工作是首批基本上利用了这一点并表明：“好的，我把这种轨迹分解开，我有两位专家，一位负责结构，另一位基本上负责纹理。”

<details><summary>Original English</summary>
>> closer

 to

 the

 noise

 if

 if

 you

 come





closer

 to

 the

 noise

 and

 then

 you

 have





the

 fine

 high

 resolution

 uh

 high





frequency

 stuff

 that

 comes

 further

 down





and

 and

 is

 closer

 to

 kind

 of

 um

 the





clean

 image

 basically

 and

 like

 today





there's

 a

 bunch

 of

 different

 books

 that





actually

 analyze

 this

 but

 you

 do





actually

 you

 you

 kind





you

 generate

 from

 low

 frequency

 to

 high





frequency

 if

 you

 go

 from

 like

 noise

 to





clean

 image

 right

 along

 this

 trajectory





but

 that

 was

 not

 really

 known

 like

 it





was

 informally

 maybe

 a

 bit

 known

 by

 then





and

 this

 was

 it

 was

 one

 of the

 first





works

 to

 basically

 exploit

 this

 and

 say





okay

 yeah

 I

 actually

 I

 dissect

 this

 kind





of

 trajectory

 and

 I

 I

 have

 two

 kind

 of





experts

 one

 for

 the

 structure

 and

 the





next

 for

 the

 texture

 basically
</details>

>> 没错，现在我们在架构中有了调制机制（modulation），比如以时间步（time step）为条件来兼顾这一点，诸如此类；但这确实是最早真正做出这种区分的工作之一，而且如你所见，它的效果相当不错。

<details><summary>Original English</summary>
>> and

 yeah

 right

 now

 we

 have

 modulation





which

 is

 like

 condition

 on

 the

 time

 step





to

 actually

 account

 for

 that

 as

 well

 and





stuff

 like

 that

 in

 the

 architecture

 but





that

 was

 really

 the

 first

 one

 of

 the





first

 works

 to

 to

 really

 um

 make

 this





distinction

 and

 it

 as

 you

 see

 it

 worked





quite

 well.
</details>

>> 是的，它确实效果相当好。我想我之所以至今仍耿耿于怀，是因为当时我希望这单一模型在所有方面都极其出色，而我感到……

<details><summary>Original English</summary>
>> Yeah,

 it

 did

 work

 quite

 well.

 I

 guess





the

 reason

 I

 I

 still

 hold

 frustration





because

 at

 the

 time

 I

 wanted

 this

 one





model

 to

 be

 so

 good

 at

 everything

 and

 I





felt
</details>

>> 对，也许当时觉得这有点像走捷径。现在我的看法有些不同了，因为我是说，我们看到系统和模型协同工作能取得令人惊叹的效果；但在当时我记得那种感觉，而且我现在依然留着这种旧日的挫败感，你知道的，就是当年的情绪。这其实也是很合理的，因为你始终应该选择可行的最简单解决方案，如果你随后遇到某种情况，你需要……

<details><summary>Original English</summary>
>> Yeah,

 maybe

 it

 was

 like

 a

 little

 bit

 of





a

 copout.

 Now

 nowadays

 I

 take

 a

 a

 bit

 of





a

 different

 view

 cuz

 I

 mean

 we

 see





systems

 and

 models

 do

 incredible

 work





together

 but

 at

 the

 time

 I

 remember





feeling

 and

 I

 still

 just

 have

 this

 like





kind

 of

 old

 frustration

 you

 know

 just





just

 from

 back

 then

 it's

 also

 very

 fair





because

 you

 should

 always

 go

 with

 the





simplest

 solution

 that

 works

 and

 if

 if





you

 then

 have

 a

 kind

 of

 a

 you

 need
</details>

>> 在什么节点上我需要一个机器精炼器（refiner）。是的，在扩展（scaling）方面，无论最简单的……

<details><summary>Original English</summary>
>> at

 which

 point

 do

 I

 need

 a

 machine





refiner.

 Yeah,

 this

 is

 like

 when

 it





comes

 to

 scaling,

 whatever

 the

 simplest
</details>

>> 可行方案是什么，你就应该采用什么，这基本上在统计学中也算是一种剃刀原则。

<details><summary>Original English</summary>
>> solution

 is

 that

 works,

 you

 should

 go





with

 kind

 of

 a

 bit

 of

 a

 razor

 as

 well

 in





in

 statistics

 basically.
</details>

>> 所以，你看，Runway 当时也在做他们的 Gen-1 和 Gen-2，在这点上 Anastasis 也承认了 Gen-2 是流水线模式［笑］，他们只是没有公开承认，而你们的是开源公开的，所以你们不得不承认。［笑］我认为如果回到那个时期，现在进入这个领域的人大概没见过 200 到 500 步的扩散过程，对吧？就像你说的，先出来一个背景，几分钟后细微的细节才逐渐显现。而且它当时也非常适合折腾，对吧？这个发布出来大概是个 3B 参数、能在 8GB 显存上运行的模型。所以如果你不是实验室，只是在家里做这个，只有一两张 GPU，尽可能用更少比特运行通用方案，你肯定会用流水线。没错，那就是你能直接看到差异的地方。

<details><summary>Original English</summary>
>> So,

 you

 know,

 runway

 was

 also

 kind

 of





doing

 their

 gen

 one

 and

 gen

 two

 and

 uh





Anastasis

 on

 on

 this

 part

 also

 said





admitted

 that

 gen

 two

 was

 pipeline

 like





[laughter]





they

 just

 didn't

 admit

 it

 whereas

 yours





was

 public

 so

 you

 had

 to

 admit

 it.





[laughter]

 I

 think

 if

 you

 go

 back

 to

 the





time

 too

 like

 people

 I

 don't

 people





coming

 into

 the

 space

 today

 haven't

 seen





200

 500

 steps

 of

 diffusion

 right

 like

 as





you

 say

 like

 you

 have

 a

 background

 and





then

 minutes

 later

 you

 have

 little

 fine





details

 coming

 in

 uh

 it

 was

 also

 very





tinkerable

 right

 this

 came

 out

 as

 what





like

 a

 3B

 works

 on

 8

 gigs

 of

 RAM

 so

 as





much

 as

 you

 could

 bit

 or

 less

 and

 do

 the





general

 approach

 if

 you're

 not

 a

 lab

 and





you're

 just

 doing

 this

 at

 home

 you

 you





have

 like

 one

 or

 two

 GPUs

 you're

 going





to

 do

 pipeline

 Right.

 It's

 like

 that's





how

 you

 can

 see

 the

 differences

 right





there.
</details>

### 转向视频扩散与数据过滤研究

>> 是的，没错。至于视频，其实在 Stable Diffusion 之前，我已经做视频很长一段时间了。我当时在英伟达从事视频生成工作。在那里有一篇论文《Align your Latents》，基本上是与 Stable Diffusion 同期进行的。我们基本上将这种潜空间扩散算法映射到了视频上，这在当时是自然而然的下一步。能够一口气把事情推进下去非常令人兴奋。你可以想象，Stable Diffusion 当时相比其他模型如此高效背后的压缩逻辑，同样适用于视频，因为视频多了一个时间维度，而这个时间维度也是可以压缩的，对吧？所以这完全说得通。我起初在英伟达做这个，然后当我们加入 Stability 之后，基本上是在 SDXL 之后……

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Uh

 so

 video

 I've

 been





working

 on

 video

 for

 quite

 a

 actually





already

 before

 stable

 diffusion.

 I

 was





working

 on

 uh

 video

 generation

 for





Nvidia.

 Um

 had

 a

 paper

 there

 align

 your





latence

 where

 we

 basically

 map

 the

 was





actually

 in

 parallel

 to

 stable





diffusion.

 We

 basically

 mapped

 this





latent

 diffusion

 algorithm

 to

 video





which

 was

 the

 the

 natural

 next

 thing

 to





to

 to

 do.

 It

 was

 very

 exciting

 to

 kind





of

 then

 just

 at

 once

 keep

 things

 moving





and

 you

 can

 imagine

 the

 kind

 of





compression

 um

 reasoning

 behind

 why





stable

 diffusion

 was

 so

 efficient





compared

 to

 other

 models

 in

 the

 in

 the





time

 also

 holds

 for

 video

 where

 you





actually

 have

 this

 temporal

 dimension





that

 you

 can

 also

 compress

 right

 so

 that





made

 a

 ton

 of

 sense.

 uh

 worked

 on

 this





for

 first

 for

 Nvidia

 and

 then

 when

 we





when

 we

 basically

 joined

 stability

 we

 um





basically

 after

 I

 think

 after

 SCXL

 um
</details>

>> 嗯。我们开展了 Stable Video Diffusion 的研发，它基本上首次将这种潜空间扩散方法应用到了视频资产上。但重要的是，这项工作很大程度上在于调查数据过滤的影响。我们觉得——或者说我个人当年觉得——这在学术研究中过去和现在都非常不受重视。因为当我们思考这些模型在做什么时，本质上我们是在估计一个概率分布，而数据集正是产生这个概率分布的基础，对吧？如果你拥有完美的算法，拥有世界上能学会任何东西的最佳算法，

但是你的数据非常糟糕，比如平均而言都是模糊的视频或图像，而且视频里动作幅度不大，那么无论你的算法多么优秀，你的模型学到的都会是这些。因此模型输出的结果实际上会非常糟糕，看起来很不理想。所以对于想要训练这些模型的人来说，数据是最重要的抓手之一。在整个研究领域，以前几乎很少有人讨论数据，因为学术界的很多人只是在跑基准测试（benchmarks）和微调算法。但如果你讨论前沿模型，显而易见我们现在都知道数据极其重要，对吧？而这正是我们想要真正分享一些背景、提供更多参考的地方。所以我们研究了数据量的大小，然后你就会面临这种权衡：我希望用海量数据进行训练……

<details><summary>Original English</summary>
>> Mhm.

 We

 worked

 on

 this

 this

 um

 stable





video

 diffusion

 which

 basically

 first





applied

 this

 this

 latent

 diffusion

 um





approach

 to

 video

 asset.

 But





importantly,

 this

 this

 work

 was

 a

 lot





about

 investigating

 the

 effects

 of

 data





filtering

 which

 as

 we

 felt

 or

 as

 I





personally

 felt

 back

 in

 the

 day

 were





like

 in

 research

 and

 they

 still

 are

 very





much

 underappreciated

 like

 data

 is

 just





like

 when

 we

 think

 about

 what

 these





models

 are

 doing

 effectively

 we're





estimating

 a

 probability

 distribution





and

 the

 data

 set

 is

 what

 gives

 rise

 to





this

 probability

 distribution

 right

 and





if

 you

 have

 the

 perfect

 algorithm

 the





best

 algorithm

 in

 the

 world

 that

 that





just

 learns

 anything

 you





But

 your

 data

 is

 very

 bad

 and

 you

 have





like

 on

 average

 blurry

 videos

 or

 images





and

 like

 like

 not

 a

 lot

 of

 motion

 in

 the





videos,

 your

 model

 will

 learn

 that

 no





matter

 how

 good

 your

 algorithm

 is.

 So





what

 comes

 out

 of

 the

 model

 will





actually

 be

 very

 bad

 and

 like

 like

 not





nice.

 So

 the

 data

 is

 one

 of

 the

 most





important

 levers

 that

 you

 have

 as

 one





who

 who

 wants

 to

 train

 these

 models.

 And





in

 the

 entire

 research

 field,

 there

 was





never

 much

 talked

 about

 data

 because

 a





lot

 of

 people

 from

 the

 research





community,

 they

 just

 worked

 on





benchmarks

 and

 like

 tweaked

 the





algorithms.

 But

 if

 you

 talk

 about





frontier

 models,

 obviously

 we

 know

 that





by

 now

 that

 data

 is

 extremely

 important,





right?

 And

 and

 that

 is

 what

 we

 wanted

 to





be

 really

 like

 sharing

 a

 bit

 like





sharing

 more

 context

 on.

 So

 we





investigated

 how

 much

 data

 like

 and

 then





you

 have

 this

 this

 trade-off

 I

 want

 to





be

 training

 on

 a

 lot

 of

 data
</details>

>> 数量与质量的权衡。

<details><summary>Original English</summary>
>> quantity

 versus

 quality
</details>

>> 没错，最佳平衡点在哪里？那就是我们在那里探究的问题。此外还有一张非常有趣的图表——

<details><summary>Original English</summary>
>> exactly

 where

 is

 where's

 the

 sweet

 spot





that

 was

 what

 we

 investigated

 there

 and





then

 also

 a

 very

 interesting

 chart
</details>

>> 我们应该调出来看看。

<details><summary>Original English</summary>
>> we

 should

 pull

 up
</details>

>> 马上就来，我们可以直接看它。我们做的最令人兴奋的实验不是关于数据的那个，实际上如果你往下看一点……

<details><summary>Original English</summary>
>> coming

 coming

 we

 can

 actually

 take

 it





the

 most

 exciting

 experiment

 that

 we

 did





it

 was

 not

 the

 data

 one

 but

 actually

 if





you

 go

 down

 a

 bit

 um
</details>

>> 我们随后——这又回到了我们之前讨论的内容——我们随后展示了，仅仅在……上进行预训练

<details><summary>Original English</summary>
>> we

 then

 and

 it

 comes

 back

 to

 what

 we





discussed

 earlier

 we

 then

 showed

 that





just

 pre-training

 on
</details>

<!-- chunk 6/14 -->

纯 2D 视频能让你基于它以极快的速度微调显式 3D 模型。如果看这篇论文的最后一段，就在这里，这些就是模型的 3D 视角。所以我们实际做的是，拿来训练好的这个视频模型，然后我想是在 3D 数据上微调了 1000 步，就从中得到了一个 3D 模型。这又回到了那个问题：要某种程度上理解 3D 世界，究竟需要什么？只要 1000 步……
<details><summary>Original English</summary>
plain 2D videos allows you to fine-tune the explicit 3D model extremely fast from it. So if you go to the to the last paragraph here of the of the paper, here we go. These are these 3D uh 3D um views here of of the model. So what we actually did is we took this video model that we trained and then we had I think 1k fine-tuning steps on 3D data and we got a 3D model out of it. And and that that comes back to the question, okay, what what do you actually need to to kind of understand the world in 3D, right? Only one K
</details>

>> [笑]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 这一发现表明，该视频模型虽然仅在纯视频上训练，但实际上具备了惊人程度的 3D 理解力，你只需稍微聚焦一下，就能从中得到一个 3D 模型。这真的是……这是我们较早期的实验之一，从中我们发现，原来确实可以在某种程度上通过在纯视频上训练来获得对世界的理解。从研究角度来看，我认为这是这篇论文里最有趣的实验。
<details><summary>Original English</summary>
>> finding that shows that this video model although only trained on on plain video actually had this insane amount of 3D understanding and you just took a bit of a a focus to get a 3D model out of it and that that is really like that was one of the early experiments where we saw okay this is actually kind of you can get world understanding through training on plane video and like from a research perspective this was like I think the most interesting experiment um in this paper
</details>

>> 这篇论文也相当短，这里甚至有一节解释了整个流程，对吧？大概有三四个阶段。预训练，一些后训练，呃对，第一阶段，图像预训练、视频、后……呃，视频预训练，
<details><summary>Original English</summary>
>> also pretty short paper there's like a section here where you even explain the pipeline, right? There's like three, four stages. Pre-training, some post-trainining, uh yeah, stage one, image pre-training, video, post uh video pre-training,
</details>

>> 视频微调，然后 1000 步，就能把它做成 3D 的，对吧？太不可思议了。
<details><summary>Original English</summary>
>> video fine-tuning, and then 1,000 steps, you can also make it 3D, right? Crazy.
</details>

>> 呃，当时我不记得自己具体做了什么，但基本上存在这种时间一致性问题：如果你直接把扩散拉长并试图拼接各帧，那是行不通的。所以在很久以前的一个黑客松项目里，我都忘了当时具体用的什么方法，但我们解决了这种时间一致性，把它扩展到了 15 到 20 秒。当时耗费了极长时间，但那是个非常凑合的方案，因为你在一个下午就能做出来，对吧。但关键在于，你需要这种……
<details><summary>Original English</summary>
>> Uh at the time, I I don't remember what I did, but there was basically this temporal consistency problem where if you just stretch out diffusion and try to stitch frames, it wouldn't work. So a very old hackathon project where I I forget the method we even used but we fixed this temporal consistency to like scale it out to 15 20 seconds. It took forever but it was a very hacky solution cuz you could do this in an afternoon right. But you critically you need this kind of
</details>

>> 在时空上学习，也就是在时间维度上学习。如果只是把一个非常快的扩散模型拼接在一起，就会出现这种闪烁，即便固定了随机种子并加上大量特效也一样。但你会意识到，就像在……如今每个人都在使用 Transformer，按 Transformer 的行话来说，你也需要在时间维度上引入注意力机制，以便从中学习，对吧，进而理解到底……
<details><summary>Original English</summary>
>> learning over spatial temporal kind of over the temporal dimension. Then if you just stitch together kind of a very fast diffusion model you don't you have this flickering even even if you you fix the seed and you do a ton of effects but you realize you need to like in in currently every or today everyone is using transformers so in the transformer speak you need the attention over the temporal dimension as well to kind of learn from that right and then understand what is actually
</details>

>> 连贯的运动基本上到底是什么样子的。
<details><summary>Original English</summary>
>> what how does consistent motion look like basically
</details>

>> 据我所知——我们在聊 Grok Imagine 那部分时也问过这个问题——视频端没有任何有用的压缩，对吧？全都是一帧、一帧、一帧、一帧、一帧。
<details><summary>Original English</summary>
>> and as far as I understand we asked this of the on the gro imagine part as well uh there's no compression in the video side that is useful right you have frame frame frame frame frame.
</details>

>> 没错。[笑]
<details><summary>Original English</summary>
>> Exactly. [laughter]
</details>

>> 这是最简单的版本，但它……
<details><summary>Original English</summary>
>> It's the simplest for version but it's
</details>

>> 我是说，如果去看 MP4 编解码器，里面有非常精妙的压缩，但显而易见那是有损的。是的，你必须以某种方式把各帧连接起来，提取出连贯运动到底……
<details><summary>Original English</summary>
>> I mean well well if you then look at MP4 codecs you you have very smart compression but that is lossy obviously. Yeah. and and you need to kind of you need to connect the frames in a way and like like extract what what what how how how
</details>

>> 连贯运动基本上到底是什么样的。我认为没有任何视频模型会公开暴露这一点，但关键在于你在时间注意力机制里往前回溯多远，因为有时候确实需要更长……或者可能需要更具自适应性。比方说，如果某个物体被遮挡随后又重新出现，你希望前后是同一个物体，但要是它被遮挡了很长时间呢？
<details><summary>Original English</summary>
>> how kind of consistent motion looks like basically I don't think any video model exposes this but kind of how far you look back in the uh temporal attention because sometimes you do need longer uh or it needs to be more adaptive maybe uh for example if uh something gets oluded and then comes out again you want you want them to be the same but what if like how long is it oluded
</details>

>> 原则上，这取决于你想要解决的问题，对吧？如果你想打造一个具备长记忆、能够生成虚拟世界的模型，那么显然就需要找到一种能够大幅、大幅、大幅往前回溯的方法。
<details><summary>Original English</summary>
>> I mean principally that that depends on on the on problem you want to be solving, right? If if you if you want to be creating a kind of a a long memory model that that that can can create your virtual worlds, then you obviously need to find a way to look back very very very long.
</details>

>> 超级记忆。
<details><summary>Original English</summary>
>> Super memory.
</details>

>> 我觉得这也是当下最令人兴奋的研究课题之一。长上下文就是极其重要。
<details><summary>Original English</summary>
>> That is that is just I think also one of the most exciting research problems to work on these days. Long context is just extremely important.
</details>

### 从 SD3 到流匹配 (Flow Matching)

>> 我不知道在切到 Black Forest Labs 之前还有没有别的内容。呃，在 Stable 的领域里还有别的吗？
<details><summary>Original English</summary>
>> I don't know if there's more there before we cut over to Black Forest Labs. Uh anything else in the stable world?
</details>

>> 呃，我是说还有 SD3，那是你在离开前做的最后一篇论文……
<details><summary>Original English</summary>
>> Uh S I mean there's S3 that was the last paper that you did before you
</details>

>> 对，对。我觉得 SD3 是一篇挺重磅的论文。
<details><summary>Original English</summary>
>> Yeah. Yeah. SD3 was a I felt like a pretty big paper
</details>

>> 那篇……[笑] 我想说，那算是我们在 Stability 工作的一个集大成之作……
<details><summary>Original English</summary>
>> that that was a [laughter] was a I think one culmination of our work of man stability I would say like
</details>

>> 对，完全是。
<details><summary>Original English</summary>
>> yeah absolutely
</details>

>> 算是你们的毕业论文。[笑]
<details><summary>Original English</summary>
>> we your graduation thesis [laughter]
</details>

>> 你要这么说也行，是的，确实。
<details><summary>Original English</summary>
>> if you want yes I mean
</details>

>> 不，这篇论文真正的核心在于更深入地去理解：在从数据到噪声的整条轨迹中，模型到底在哪一段学到了哪些特性，以及我们在训练中投入的大部分算力必须花在什么地方，
<details><summary>Original English</summary>
>> no this this paper was really about understanding more in which part of this trajectory from data to noise does the model actually learn what properties and where do we have to spend most of our computation that we put in training
</details>

>> 才能让模型的性能最大化。
<details><summary>Original English</summary>
>> to maximize the performance of the model.
</details>

>> 对。所以在此之前，显然这也是从经典扩散模型向流匹配的转变，基本上采用了一种略有不同的范式。
<details><summary>Original English</summary>
>> Yeah. So before and obviously that was also the transition from classic diffusion to flow matching with a slightly different uh paradigm basically
</details>

>> 你们称之为整流流（rectified flow）。
<details><summary>Original English</summary>
>> you call it rectified flow.
</details>

>> 没错。呃……
<details><summary>Original English</summary>
>> Exactly. Um
</details>

>> 这也是第一次使用像扩散 Transformer（Diffusion Transformer）这类架构，对吧，走得更远了一点。是的，有非常多的改变：比如从卷积架构转向 Transformer 架构；把概率模型从扩散模型转为流匹配，在数学上简单得多，这超级、超级棒。
<details><summary>Original English</summary>
>> this was also the first time I used like diffusion transformers right with the a bit further. Yeah. So lot lots of changes like going from a convolutional architecture to a transformer architecture changing the probabilistic model from from a diffusion um to basically flow matching which is way simpler mathematically which is super super nice
</details>

>> 我觉得你应该为那些没听过的人定义一下其中一些术语，[笑] 扩散，还有流匹配，你们当时是怎么想到这些概念和这些东西的，对吧？
<details><summary>Original English</summary>
>> I think you should actually define some of those terms for people that haven't heard [laughter] latusion you know flow matching what how did you come up with the concept of these ter things too right
</details>

>> 这个流匹配不是他想出来的。我们……没错，流匹配并不是我们提出来的，我们只是看到了这种算法在某种程度上更加通用。因为对于扩散模型，你进行转换的两个分布中，始终必须有一个是标准正态分布；而流匹配则不再有这一限制。在解决把一个概率分布转换为另一个概率分布这类问题时，它不再将其视为随机微分方程的解，而是实际将其视为常微分方程的解。这在数学上把一切都彻底简化了，并且可以说是让快速采样变得更加可行得多。因为显然，当我们训练好模型后，我们始终希望用尽可能少的步数，基本上实现尽可能快的采样，对吧。

有些人会说流匹配其实是扩散模型的一种特例；另一些人可能会说，流匹配算法实际上是对扩散模型的推广，因为无论两个分布的形状如何，你都可以在它们之间进行转换，不需要假设其中一个是标准正态分布。但总体而言，它同样可以被看作是一个模型，其学习的本质是两个分布之间进行转换的向量场；一旦模型学到了该向量场，你就可以直接对其进行数值积分，这就像通过欧拉前进步来求解 ODE 一样容易。所以它在许多方面非常相似。但在我看来，它在数学上更简单，从它能在哪些类型的概率分布之间进行转换的角度来看也更通用，这就是我们基本上选择它的原因；而且第三点正如所说的，基于这些流匹配模型也更容易推导出一个快速模型。大体上就是这样。
<details><summary>Original English</summary>
>> well he didn't come up with flow match we we exactly we we didn't come up with flow matching we just saw this algorithm as something that is in a way more general because you can like for diffusion you always need one of your two distributions between which you're basically translating needs to be a standard normal that does not hold for flow matching anymore and instead of approaching this kind of problem to to to um transform one probability distribution into the other with a seeing it as as a solution of a stoastic differential equation. you're actually seeing it as a a solution of an ordinary differential equation which simplifies everything completely like mathematically completely and makes also fast sampling much more um feasible you could say because what we always do obviously is when we have trained the model we want to get be making as many steps as little steps as possible to basically sample as fast as possible right some people would say it's it's actually a special case of of diffusion flow matching other others might say okay it's actually a generalization of flow matching of diffusion the flow matching algorithm because you you you go from you can translate between two distributions no matter how they are shaped and you don't need this this kind of um standard normal basically guess to to be one one of them but yeah in general it can be seen as again a a model that learns basically to a vector field between two that that that translates between two distributions and once the model has learned that vector field you can just integrate it numerically which is then as easy as solving a OD by means of an oil or forward uh step basically. So it's it's it's very similar in in many respects. Um but it was just like I would say mathematically easier more general from from the the the kinds of probability distributions that it can can translate between and that's why we basically uh went with it and maybe as a third party said it's also easier to derive a fast model from those uh flow matching models. Basically,
</details>

>> 它简单得多，扩展性也更好，处理起来容易得多，而且还带来了很好的性能优势。扩散领域之前变得相当复杂。
<details><summary>Original English</summary>
>> it was it was much simpler and more scalable like it was it was it was much much easier to work with and then had this like nice performance benefit as well. So like I don't know there the the the diffusion space got quite complicated.
</details>

>> 我们能确定它没有损失吗？它是以一种可接受的方式存在有损吗？
<details><summary>Original English</summary>
>> Are we satisfied that there's no loss? Is like is it is it lossy in acceptable ways?
</details>

>> 你说的有损，是指相比完整扩散模型有损失，还是指……
<details><summary>Original English</summary>
>> Lossy you mean lossy compared to full diffusion or
</details>

>> 对。好，那它就很不错，是一个严格的改进。
<details><summary>Original English</summary>
>> Yeah. Okay. So then it's good. It's a strict improvement.
</details>

>> 没错，确实是一项改进。
<details><summary>Original English</summary>
>> Exactly. It's it's it is an improvement.
</details>

>> 是的，它实际上就是在噪声和数据之间画一条线。正如 Andy 所说，原本在如何在两个分布之间进行映射上存在着非常复杂的空间，而它将其简化成了直接画一条线这种最简形式……
<details><summary>Original English</summary>
>> Yeah. I mean it's it's effectively just drawing a line between like you know noise to data really. It's it's it's like it it it kind of took this like there was this complex space on like how do you map between these two uh the you know the like these two distributions as Andy was saying and it simplified it down to like the simplest of just drawing a line
</details>

>> 因为你想走捷径，但要是分布凹凸不平呢？
<details><summary>Original English</summary>
>> because you're trying to do a shortcut like what if it's a bumpy distribution.
</details>

>> 对，对，问题就在这里。
<details><summary>Original English</summary>
>> Yeah. Yeah. That's that's the thing.
</details>

>> 这篇论文最重要的一部分，或者说最重要之一，就在于……
<details><summary>Original English</summary>
>> And like the most important part of the paper or one of the most important like on on the on
</details>

<!-- chunk 7/14 -->

### 训练轨迹与计算分配

……概率建模这方面，实际上是在研究从噪声到图像的轨迹，以及哪些部分真正重要，哪些不重要。因为如果我们只是像平时那样分步训练，对吧？我们总是在从数据到噪声的这个过程中，每次只针对某种步长进行训练，然后我们在流匹配（flow matching）中用一个模型来近似这个方向。如果你只是在数据和噪声之间均匀地对这些步骤进行采样，你实际上可能会花费大量时间去优化那些根本无关紧要的东西。所以这篇论文的一个核心部分就是——

<details><summary>Original English</summary>
 the probabilistic modeling side um was actually looking at the trajectory from noise to image and which parts really matter and which don't because if you just like we we we train this in kind of steps, right? We we we always on on this part from data to noise, we only always train on one kind of step and then we approximate this direction in flow matching um with a model. And if you just sample those steps in between data and noise uniformly, you might actually spending a lot of time optimizing for things that actually don't matter. So one one central part of the paper was
</details>

>> 我们应该把算力花在哪里？从数据到噪声的这条轨迹中，哪些部分承载的信息最重要——

<details><summary>Original English</summary>
>> where should we spend our compute? Which parts of this trajectory from data to noise carry the information that's most important
</details>

>> 因为这正是你在训练时应该投入大部分算力的地方，对吧？在训练期间对这些部分进行过采样，而对其他不那么重要的部分进行欠采样。这实际上就像是对我们在 SDXL 中谈到的内容的进一步深化探索——当时是针对细化器（refiner），我们花时间在轨迹末端训练 refiner 来学习这些高频细节；而这更像是在整个空间中探索应该把时间花在哪里，从而打造出最通用、最能有效学习数据的优质模型。是的。

<details><summary>Original English</summary>
>> because there this is where you should spend the bulk of your compute at training, right? And over sampling these parts during training and then under sampling other parts that are less important. It's it's effectively like a further like a a much further better exploration of part of what we talked about with SDXL which was like the refiner we spent time like training the refiner on the end of this trajectory to learn these high frequency details and this was like more of an exploration of the entire space of where like you should spend time to make the most like general good model to learn the data. Yeah.
</details>

### 图像文字生成与模型扩展

>> 太厉害了。关于 SD3，我确实注意到了图像中的文字生成，这也是你们重点展示的亮点。曾经有一段时间，图像生成模型根本完全无法处理文字，后来能生成的文字越来越多，而现在就像是：“看，这是我们漂亮的排版。”我觉得这能归功于 Diffusion Transformer（DiT）吗，还是说……

<details><summary>Original English</summary>
>> Amazing. Uh one thing I did pick up with SD3 was text uh in images which you guys showed off a lot. There was a time when images could just straight up not do text and then they did more and more text and then now it's like you know here's here's here's our nice typography. I feel like it was can we attribute that to the diffusion transformer or
</details>

>> 我不知道能不能说全靠 Diffusion Transformer。我的意思是，我认为其实纯粹就是……

<details><summary>Original English</summary>
>> I I don't know if I could say it was the diffusion transformer. I mean I I think it really was just
</details>

>> 更好的模型。是更好的建模和更好的数据。从根本上说，尽管我很想归功于某些花哨的技术——不知为何，人们总想找个高大上的归因——但事实真的只是它能更好地对世界进行建模了。

<details><summary>Original English</summary>
>> better model. It was better modeling and better data like it was fundamentally like as much as much as I want to like as as much as like I don't know you always want to attribute some fancy thing it really was just that it it could model the world better.
</details>

>> 这是数据层面的事情。而且就像你训练的所有东西一样，你始终需要标注文本（caption），对吧？如果你的 caption 没有描述在某处呈现出的文字，你的模型就学不会它，对吧？所以，这也是大家经常……

<details><summary>Original English</summary>
>> It's a data thing. It's also like what you always need like for everything that that you train on, you need a caption, right? If your caption doesn't describe the text that is visualized somewhere, your model will not learn it, right? So, um that's also something that that is often
</details>

>> 有时候我们花大量时间讨论某个算法的细枝末节。到头来，这又印证了那个“苦涩的教训”（Bitter Lesson），对吧？

<details><summary>Original English</summary>
>> sometimes we spend a lot of time talking about the nitty gritted details of some algorithm. In the end, it's again the better lesson, right?
</details>

>> 简单、可扩展的架构几乎永远是最有效的。我甚至想说永远是最有效的。

<details><summary>Original English</summary>
>> Simple scalable is is almost always the most effective. I would say always the most effective.
</details>

>> 没错。但你显然可以用聪明的方式去扩展规模；而且如果你要投入海量算力，你就应该尽可能高效地使用它，只用在刀刃上。基本上这也是这篇论文的核心所在，对吧？

<details><summary>Original English</summary>
>> Yeah. But you can obviously scale in a smart way and still if if you if you spend tons of compute you should be spending it as efficiently as possible and only where it matters and that is also at the heart of this this paper basically right
</details>

>> 我觉得那段时间写 prompt 也容易多了。我们以前总要在里面加……

<details><summary>Original English</summary>
>> I think prompting also got a lot easier at this time um we used to have the
</details>

>> “4K”。对。

<details><summary>Original English</summary>
>> 4K yes
</details>

>> 还有那个 Greg 是谁来着？那位可怜的艺术家。

<details><summary>Original English</summary>
>> who was the Greg guy the poor artist
</details>

>> 现在你应该……

<details><summary>Original English</summary>
>> and now you should
</details>

>> Greg Rutkowski（格雷格·鲁特考斯基），对。我不知道他最近怎么样了［笑］。希望他一切都好。希望他过得不错。

<details><summary>Original English</summary>
>> Greg Rowski yes I wonder how he's [laughter] I hope it's doing well. I hope it's doing well.
</details>

>> 是啊。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且，交代一下当时的背景，那是 DALL-E 3、Midjourney、Ideogram v1 的时代，没有任何东西是开源的。

<details><summary>Original English</summary>
>> And also, you know, for context, this is when Dolly 3 midjourney ideoggram v1 nothing was open.
</details>

>> 所以，你能看到的这种质量的模型，要么是旧版的 Stable Diffusion，要么……

<details><summary>Original English</summary>
>> So, anything that you would see of this quality was either old stable diffusion or
</details>

>> 基本上全是闭源工具。是的。

<details><summary>Original English</summary>
>> pretty much a closed closed closed tool. Yeah.
</details>

### 创立 Black Forest Labs 与开发 FLUX.1

>> 然后你们做出了重大决裂，创立了 Black Forest。那整个时期是怎样的？基本上你们得离开原公司，从零开始建立一个实验室。

<details><summary>Original English</summary>
>> Then you had to make the big break to Black Forest. Uh what was that whole period like? Right. Like basically you had to leave and start a lab from scratch.
</details>

>> 我觉得那可能是最令人兴奋的时期之一。我们所有人都有这种感觉，因为当你处于隐身研发期（stealth）时，你们就只是一个小团队。我们当时只有……

<details><summary>Original English</summary>
>> I think it was probably one of the most exciting times. Uh, we all had because when you're in stealth, you're just like you're a small team. We were
</details>

>> 13个人。我想当我们刚开始的时候，我们先去了法国，在法国山里的一座小木屋度过了非常开心的一周。

<details><summary>Original English</summary>
>> 13 13 people. I think when when when we started, we first went to France, had a had a had a a fun little week in in in the mountains in France in a in in a chalet.
</details>

>> 整整一周都在写代码、聚在一起。Dustin 想出了一些非常酷的技术，让我们的模型一致性大幅提升。我还记得那件事。那真是太好玩了。那是非常神奇的一周，那实际上就是我们的创立期团建（founding offsite）。也就是在那个时候，我们开始训练 FLUX.1。三个月后，公司带着这款模型正式亮相，我觉得它基本上震撼了所有人。至少它也深深震撼了我们自己。确实如此。

<details><summary>Original English</summary>
>> Spent the entire week just hacking, hanging out. Dustin figured out some really cool uh um uh stuff to make our models way more consistent. I I I I remember that. That was so fun. That was a magical week. That really was our kind of founding off site. That is when we started um training flux one which 3 months later um resulted in this nice company launch basically with a model that that I think blew pretty much everyone away. Uh at least it blew us us also away. Oh yeah.
</details>

>> 在商业层面上，这直接打开了局面——仅仅成立公司3个月就发布了这款模型，而且反响非常非常热烈。对，那真是太棒了。所以那是……

<details><summary>Original English</summary>
>> Like commercially what what this directly unlocked like only only having having kind of incorporated the company for 3 months and then releasing this model and it was like yeah just like was received very very well. Right. That was that was amazing. Uh so that was
</details>

>> 但你们刚着手做这件事的时候，有预料到会这样吗？我是说，你们必须把所有算力集群搭建起来，准备好所有数据，必须彻彻底底从零做起。

<details><summary>Original English</summary>
>> but like did you know that when you started this I mean you had to get all the the you know the clusters together like all the data you had to start from scratch scratch.
</details>

>> 我们确实必须从零开始。是的。但我们基本上知道该怎么做。

<details><summary>Original English</summary>
>> We had to start from scratch. Yes. But we knew what to do basically.
</details>

>> 那当然。

<details><summary>Original English</summary>
>> Yeah obviously
</details>

>> 我们积累了大量的经验。而且……

<details><summary>Original English</summary>
>> we we had a lot of experience. Um and
</details>

>> 但你们当时有……你们刚刚完成了 SD3。你们当时是在探索某种想要验证的假设吗……

<details><summary>Original English</summary>
>> but like do you did you have a you just did SD3. Did you have a hypothesis like that you were exploring
</details>

>> 比如会有哪些不同的做法？我们在整个这段时间里，甚至在加入 Stability 之前，显然就已经积累了大量的知识，对吧？所有这些融会贯通在一起。而且当时我们还有了一支齐聚一处、高度专注的团队，这在以前是从来没有过的；因为如果你在一家公司的不同部门分散工作——正如 Dustin 所说，Dustin 之前其实并不在我们团队里——

<details><summary>Original English</summary>
>> of like what you would do differently? We we we've obviously gathered a lot of lot of uh knowledge like in these entire times even even before uh stability as well, right? And that all culminated and then we also had a team that that just like was in one place basically that was very focused which had never been the case before because like that's just like if if you're working from from very different parts of one company also as Dustin said Dustin was actually not in our team before
</details>

>> 所以我们基本上组成了一支极佳的团队，花了很多时间聚在一起讨论我们究竟要如何设计这个模型的学习过程。这些讨论就是在那次团建中进行的，接着我们就直接启动了，并取得了那样的成果。

<details><summary>Original English</summary>
>> and that like we basically had had a super nice team together spend a lot of time together discussing how we would actually design the the the kind of learning process of this model which was at this off site and then we just kicked off and that result.
</details>

>> 当时的讨论是围绕“什么是 FLUX.1”展开的，还是更广泛地探讨未来几年技术会走向何方？这个愿景里有多少是类似……

<details><summary>Original English</summary>
>> Was it like discussions of what is flux one or was it broader where do things go in a few years? How much of this vision was like
</details>

>> 这个我想插一句。创办这家公司的原因之一，不得不说，是因为在 Stability 期间经历的一些挫败。你知道，从我们的角度来看，我们看到了自己的模型在世界上产生的巨大影响。我们不仅看到了来自开源社区的影响，还看到了外界创立、运营并相当成功地使用我们模型的公司。我们深知我们的模型所具备的吸引力和巨大潜力，但遗憾的是，我觉得我们在 Stability 内部也感到自己根本无法充分发挥出这些模型的潜在价值。所以，这不仅在于我们坚信自己团队真正从事研究、落实执行、打造这些模型并将它们推向世界的能力，同时也是我们去纠正那些低效与失误的机会——那些由于无法真正捕捉到模型本身价值而导致的失误。因此，这也是我们坚信自己能够走下去的重要原因，因为我们在做这件事情、产生这种影响力方面有着过往的成绩，我们认为这种势头可以延续下去，而且我们完全可以以此为基础打造一家成功的公司。现在回过头来看，我认为这是一个非常好的立论点。

<details><summary>Original English</summary>
>> well I I guess if I can jump in and say like I mean one of the reasons the company was started I I I will say there were some frustrations of time at stability. You know we saw from our our side we saw the impact that our models had made out in the world. We saw not just the impact from like the open source world but also we saw companies that were started and run and and and quite successfully used our models out in the world like we knew there was a lot of draw and a lot of potential in what our models could do and unfortunately I think we also felt that uh at stability that we couldn't essentially leverage the value of what the models could be as well. So, not only did we have the belief in like our team's ability to actually do the research and perform and build these models and and get them out into the world, but this would be our shot to kind of correct those um inefficiencies or mistakes of not being able to actually capture the value of the models themselves. And and so that was also a big part of the belief of why we thought we could, you know, go forward cuz we I mean we had this record of doing doing this and making this impact and we figured that could continue on and we could actually make this uh you know successful company out of it which now I mean I think it's I think it's gone pretty good thesis.
</details>

>> 我也认为这是一个很好的立论。

<details><summary>Original English</summary>
>> I think it was a good thesis.
</details>

>> 正如我之前所说的——

<details><summary>Original English</summary>
>> As I've said before,
</details>

>> 没错。［笑声］

<details><summary>Original English</summary>
>> yeah, [laughter]
</details>

### 赞助播报：Deepgram 语音基础设施

>> 我们一直在讨论如何生成图像和视频，以及如何提升模型的感知理解能力，但语音方面呢？这就是今天广告的主题。我们在 AIE 这边与 Deepgram 合作已久，他们最近收购了 Pipecat，而 Pipecat 也是 EIE 的重要赞助商。因此，Deepgram 正在成为所有 Agent 语音基础设施中最关键的拼图之一。本期节目由 Deepgram 赞助。如果你正在构建语音 Agent，你需要跟上人们现实中真正的说话方式。这意味着要在语境中理解词汇，并保持足够低的延迟以确保对话顺畅流动。这正是 Deepgram 语音模型和实时基础设施的用武之地。每 5000 家机构中就有一家在生产环境中使用他们的语音转文本、文本转语音以及语音 Agent API。其核心优势在于高准确率、低延迟和高成本效益，让你能够大规模构建和运行语音体验。你可以使用云端……

<details><summary>Original English</summary>
>> we've been talking about how we can generate images and video and improve the perceptual understanding of models, but what about voice? And that's the subject of today's ad. Uh we've been working with Deepgram Graham for a while for on the AIE side and they recently acquired Pipcat which has also been a big sponsor of EIE. So Dgram is becoming one of the critical pieces of voice infrastructure for all agents. So this episode is sponsored by Dgram. If you're building a voice agent, you needed to keep up with how people actually talk. That means understanding words in context and keeping latency low enough for a conversation to flow. That's what Deepr speech models and real-time infrastructure are built for. One in 5,000 organizations uses speech to text, text to speech, and voice agent APIs in production. The focus is accuracy, low latency, and cost efficiency. So you can build and run voice experiences at scale. You can use the cloud
</details>

<!-- chunk 8/14 -->

API，或者自行部署，包括在本地部署。而且 Flux 文本转语音还有一个优惠：花一美元，送一美元额度，最高可达 500 美元。免费注册或了解更多信息，请访问 dgr.com/context is everything。Deepgram，Context is everything。感谢 Deepgram 为我们带来本期节目。现在我们回到访谈。
<details><summary>Original English</summary>
APIs or deploy it yourself, including on premises. And there's an offer on Flux text to speech. Spend a dollar, get a dollar in credits up to $500. To sign up for free or find out more, go to dgr.com/context is everything. Dgram. Context is everything. Thanks to DGA for bringing us this episode. And now we'll go back to the interview.
</details>

### 从图像生成到通用技术与具身智能

>> 那么，当时你们看到的是什么样的用例呢？因为我觉得很多人直接就奔着好莱坞去了，比如觉得“那就是我们的目标”，或者像 Emad 以前常说的“我们要重拍《权力的游戏》第八季”。
<details><summary>Original English</summary>
>> Well, and like what use cases were you seeing, right? Because I think a lot of people went straight to like Hollywood like we you know that's our goal or like uh IMAD used to say we will make Game of Thrones season 8 again.
</details>

>> 我是说，我正在努力回想。我不知道自己能不能记起这家公司的名字。这甚至可能在 SDXL 之前。但有那么一家公司，大概火了一两周，在网上疯传，任何人都可以拍一张自己的照片，然后它就像是生成了……
<details><summary>Original English</summary>
>> I mean I I'm trying to remember this. I can I don't know if I'll be able to remember the name of this company. This this might have even before SDXL. Um but it was a company that for like a week or two it went viral where anyone could take like a picture of themselves and then it like created
</details>

>> 变老的版本之类的。
<details><summary>Original English</summary>
>> uh the older version or so.
</details>

>> 变老的版本，它用了老式的 DreamBooth 风格微调，效率极其低下。但它一下子就爆火了，所有人都在用，大家都很兴奋。模型可以做出那么多东西，我们看到其中蕴含着巨大的潜力，看到每个人都想用它。而且你知道，我们看到了模型未来的走向。当时它们还做不了排版印刷，显然我们知道排版印刷会很重要，最终我们在 SD3 上做到了，以此类推。所以这不仅仅是某一个单独的用例，而是我们看到这是一项通用技术，具有巨大的潜力，并且在未来会持续增长并展现潜力——现在这种潜力正在更多地扩展到物理世界。但对，这其实已经是我们当时看到的潜力了。
<details><summary>Original English</summary>
the older version and it used like the old dream booth style fine-tuning which was extremely inefficient and then but it it like blew up like everyone was using this everyone was excited about it the models could make so many things and we saw that there was a lot of potential and how everyone wanted to use it and you know we we saw where the models were going to you know at the time they couldn't do typography we knew obviously okay typography is going to be important and we we eventually got there with SD3 and and then so on so it wasn't the just one use case it was we saw that this was like a general technology that had a lot of potential and that was going to continue to grow and have potential in the future which now is expanding into you know the the physical world a lot more and but yeah this this was actually already the potential we saw that like
</details>

>> 对，对，完全是这样。
<details><summary>Original English</summary>
>> yeah yeah absolutely
</details>

>> 创立 BFL 本意并不是为了做一家图像生成实验室，更多是因为 Flux 模型实在太出色了，所以我们随后顺势加以利用，因为它为我们提供了一个很好的起步。
<details><summary>Original English</summary>
>> BFL was not found to be an image generation lab it was more of a kind of a matter of the the the flux model being so good that we then capitalized on it as well because it gave us a kickstart
</details>

>> 但当我们向种子轮投资者推介这家公司时，明确表示我们希望做视频，因为我们把它看作……其实早在 2023 年我们还在 Stability 时，我就在一个播客里分享过这个观点。我们当时说，视频建模其实是理解我们世界基本运转方式的核心手段。因为正如我之前所说的，人类本质上也是先观察世界，然后开始与世界交互，并由此学到大量东西。所以这始终是我们的核心论点。然后显然我们不得不走了一段可以说非常成功的弯路，也就是通过图像生成。最终你总是会面临“我该把时间花在哪里”的问题。遗憾的是，这是我们无法克服的客观限制——一天只有 24 个小时。
<details><summary>Original English</summary>
>> but when we pitched the company to investors for the seed series it was clear we want to be working on video because we see that as a I think we shared this on a podcast actually back in 2023 already when we we're still at stability. We saying okay this like video modeling is actually the central means to understanding how our world basically works because again what I said earlier right essentially we humans are also first observing the world then starting to interact with it and by that we we learn so much so that was always the thesis and then obviously we had to kind of take this detour which was very successful I would say to through image generation and eventually and then you always like face the the the kind of the issue of okay where do I spend my time on that that's unfortunately a thing we we we we cannot get across that the day only has 24 hours unfortunately
</details>

>> 但最终，我认为 Flux 3 真正代表了我们长期以来看到的演进方向，以及大家长期以来一直想做的事。
<details><summary>Original English</summary>
>> but eventually I think flux 3 is really like where we saw this going for a long time and what you wanted to be doing for a long time
</details>

>> 这就是为什么我们对这款模型的发布感到如此兴奋：它能够生成视频，能够生成图像，能够生成音频，能够充当机器人大脑去真正应用于实际的制造工作流中。今年我们还有很多东西要陆续推出。
<details><summary>Original English</summary>
>> and that's why we're so excited about like having the model out there being able to create videos being able to create images being able to create audio being able to act as a robot brain to actually kind of work in real manufacturing workflows and there's there's a lot of stuff coming this year still
</details>

>> 我们在物理 AI 方面还有待宣布的内容。但真的，正如 Dustin 所说，我们的目标始终是创造最通用的技术，而且我们看到这正在发生，这也是为什么我们如此……
<details><summary>Original English</summary>
>> that we we have to announce on on on on the physical AI side but really like as Dustin said our goal was always to create the most general technology and we see this happening currently which is why we're so
</details>

>> 对，基本上就是非常兴奋。
<details><summary>Original English</summary>
>> yeah so excited basically
</details>

>> 是的，我是说我认为你们也走了一条保持专注的正确道路，对吧？如果我没记错的话，Flux 1 是和 xAI 联合推出的，在他们拥有自己的模型之前，它是他们的图像生成模型；这是很棒的合作。但这确实是一个很好的解决方式，回答了“我们是否要自己建立分发渠道”的问题。甚至最新的 Flux 3 Max 也是与 fal 合作进行后训练的，他们做了很多推理蒸馏，他们很擅长这个，对吧？所以这很有意思。但看起来你们现在正在扩展……你们关于机器人的最新成果叫什么来着？
<details><summary>Original English</summary>
>> yeah I mean I think you guys also took the right paths to stay focused right like if I'm not mistaken flux one launched with XAI it was their image gen model good partnerships before they had their own but like you know that's a good way to solve do we build distribution ourselves even to the latest Lux 3 Max is postrained with foul they do a lot of infrance distillation they're good at that right so it's interesting but it seems like you're expanding now towards uh you have what's the latest one with robotics um
</details>

### 可控性与 Flux 图像编辑

>> Flux Action。但在讲那个之前，还有一个需要涵盖的，就是基于上下文的图像编辑。
<details><summary>Original English</summary>
>> flux reaction action before we get there's one more one to cover which is image editing in context
</details>

>> 当然，我们有一个……
<details><summary>Original English</summary>
>> sure uh we have a K uh
</details>

>> 网站上的这段发展历史也很棒，我刚才其实在看，真是……
<details><summary>Original English</summary>
>> also really nice uh history right here on the website I was actually That is
</details>

>> 这很奇妙。我们公司现在到了这样一个阶段：很多事情就自然而然地发生了，我甚至会觉得：“噢，原来我们还有这个。”不过，在上面没能看到 Flux 1，我其实有点遗憾，毕竟它是最初的那一款。不过没关系，我觉得挺好的。
<details><summary>Original English</summary>
>> it's it's weird. We're now at the stage of company that like things just happen and I I'm like, "Oh, we have this." Um, but I was I was kind of sad flux one wasn't on there to view, but it's like the original one. But yeah, but it's it's fine. It's uh I think
</details>

>> 哪怕单看这里的视觉展示，也许有人会把它剪辑出来，从最初的 Stable Diffusion XL 一直到所有这些，能看到整个演进过程。但有一点我确实想在某个时候聊聊，我个人已经看不出太大的技术进步了。你给我看最前沿的图像、视频模型，很多中国实验室也在发布，它们很难评测。我知道人们很在乎这个。我曾和 BFL 的 Sumit 聊过……好吧，业内人士确实在进行非常激进的 A/B 测试。在评测上大家关心的东西有很多，但对我而言，从某种程度上讲，它们看起来都非常逼真。
<details><summary>Original English</summary>
>> even just the visuals here, like maybe someone will clip it off original stable diffusion XL to all the you see the progression. But one thing I do want to cover at some point, I no longer personally see the progression. Right. You show me state-of-the-art image video models. A lot of Chinese labs are putting them out. It's hard to eval. I know people care. I've talked to Sumit at BFL about. Okay. No, actually people in the industry aggressively AB test industry. There's there's a lot that people care about on evals, but there's also a level of it all looks very realistic to me. Um,
</details>

>> 剩下的就是提示词编写水平的问题了。
<details><summary>Original English</summary>
>> the rest is prompting skill issues.
</details>

>> 我觉得这里有，对，[笑声] 我觉得有很多细微的挑剔点，比如以前手部有问题，现在文字有时也依然存在问题。所以……
<details><summary>Original English</summary>
>> I think there's a Yeah, [laughter] I think there's a lot of little nitpicks like there were hands there's still issues in tech sometimes. So,
</details>

>> 现在手部依然有问题。
<details><summary>Original English</summary>
>> there still hands issues.
</details>

>> 不，以前手部确实有问题。此外在感知和空间布局上也存在问题，比如我正在重新设计我的客厅，生成的糟糕透顶。
<details><summary>Original English</summary>
>> No, there were hands issues. There there's issues in perception and layout like I'm redesigning my living room. It's horrible.
</details>

>> 可控性，我认为大规模实现可控性才是我们需要解决的问题。控制这些模型的方法有很多，也许这正好可以自然过渡到 Flux Context，因为那是我们长期以来看到的一个痛点。大家为了让模型保持角色一致性，去训练了大量的 LoRA，对吧？我当时还得在 Replicate 上……带着各种，你知道……[笑声]
<details><summary>Original English</summary>
>> Controllability is I think controllability is the the thing we need to solve like large scale. There's so many ways you can control these models and maybe that that is a good sec into into flux context as well because that that was a pain point that we saw for a lot of time. People were training so many Lauras for just to get this character consistency into models, right? I had to [clears throat] replicate back then with you know all the [laughter]
</details>

>> 接着我们就迎来了 Dustin 的这场精彩宣讲。那也是在法国北部的一处地方。
<details><summary>Original English</summary>
>> and then we had this uh amazing pitch of Dustin. It was also north side also in France actually.
</details>

>> 那是在另一间小木屋里，我好像……很多事情都是在小木屋里发生的。
<details><summary>Original English</summary>
>> It was it was another cabin where I like a lot of things happen in
</details>

>> [笑声] 我们应该去……
<details><summary>Original English</summary>
>> cast [laughter] we should go to
</details>

>> 我们真的很喜欢……
<details><summary>Original English</summary>
>> we really like
</details>

>> 你们应该多去去。
<details><summary>Original English</summary>
>> you should do more.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后我们听了 Dustin 的宣讲，他确实看到了这种潜力，意识到“好吧，我需要把这种上下文搞定。我必须不仅能用文本作为提示词，还能用图像作为提示词来进行图像编辑”，你知道的。
<details><summary>Original English</summary>
>> And and then we had this pitch of Dustin who actually kind of saw this potential and okay I need to I need to get this like context. I I I need to be able to prompt not only with text but also with images for image editing and that you know.
</details>

>> 对。对。是的，我是说我做了这个……我……
<details><summary>Original English</summary>
>> Yeah. Yeah. No, I mean I so I did this like I I
</details>

>> 而且也是在引发大热潮之前。我听过的版本是，Flux Context 最初就像是你和另外一两个人搞出来的。
<details><summary>Original English</summary>
>> prehype as well. I've heard the story that flux context was like you and one or two other people.
</details>

>> 是的。很长一段时间里，它基本上就是我的一个副业项目，后来我把我们团队的一个数据人员拉了进来，说：“来，我们一起把这个东西做出来。”所以对我来说，就像 Andy 刚才说的，它最初始于我在法国某个小木屋里做的一次宣讲。本质上我喜欢在每次团建或者每次大家聚在一起的时候做这种展示，在会上我会试着审视整个领域的发展现状、我认为该领域的未来走向，以及思考有哪些事情是我们还没做的，或者这些模型在哪些方面有潜力做出新颖且有用的东西——那些可能我们眼下还没关注到、或者尚未被解决的问题。

所以我当时其实做了一场展示，我知道这个词现在已经是世界上被滥用得最厉害的词了，但在当时我把它称为全能模型演示。因为在那个时候，关于其他编辑模型已经有了很多研究成果，如果我们回想一下，当时有早期的 Prompt-to-Prompt，然后还有……为什么我想不起名字了……那次宣讲的核心观点本质上是：这些模型显然正在学习关于这个世界的深度关系，这一点会不断得到印证，核心就在于这些关系。对我而言，比如这种关系就像是：可乐罐放置在桌面上，这个瓶子摆放在这里。当你给模型输入提示词，说“我想要一张狗戴帽子的照片”，它需要知道帽子应该戴在……
<details><summary>Original English</summary>
>> Yeah. So for for a long time it was basically my side project and then I stole one of our one of our data guys a little bit into it and said I'm come we're we're building this thing. So for me like so so yeah as Andy was saying it originally started as a pitch of mine at some uh some cabin in France that uh I did essentially like a I I like to do these presentations every you know every offsite or every time we get together where I try to look at like the state of the field and where I think the field is going and kind of where like what what is something we're not doing or something where these models have a potential to do something novel and useful that you know maybe we're not looking at right now or maybe isn't solved. And so I actually did a presentation on I know this is like the most overloaded word in the world at this point but I was like oh it's the omni the omni model presentation at that point because um there was a lot of research work out there at the time on you know other editing models if we remember back to I think there was the old prompt a prompt and then there's uh why can I not remember the name of this um the pitch was essentially these models are clearly learning like these deep relationships about the world and this is going to keep coming up it's about these these relationships and to me you know like the relationship of like okay this cocaine hand is sitting on top of a table. This bottle is sitting here. And you prompt the model and you go, okay, I want a photo of a dog wearing a hat and it needs to know, okay, the hat is on
</details>

<!-- chunk 9/14 -->

### 图像编辑与模型通用性

狗的上方。它……它需要具备这种通用理解能力。我当时心中的想法是，既然模型已经拥有了所有这些空间知识，如果我们基本上构建出正确的数据，并以正确的方式训练模型——比如以正确的方式训练一个已经预训练好的模型——我们应该就能通过非常非常少的训练，激发出通用的图像编辑能力。捕捉这些已经预先建立好的关系：事物何时存在、何时不存在，以及这些关系、图像内部的这些空间关系是如何运作的。

然后基本上就变成了这样，大概三到……我记不清具体的时间线了，我和我从别处挖来的那一个数据人员在旧金山办公室里，基本上只是在构建早期的测试训练数据集。我记得当我看到这显然效果相当好时的那一刻：我们制作了一个实际上极小的数据集，只是打上了非常高质量的标签。它基本上就是在描述图像中的简单关系，仅此而已。它并不像你给现代编辑指令模型输入提示词那样。它就只是字面上描述这些关系。

我训练了这个模型，我的意思是大概也就训练了六个小时、四个小时。这是一次非常非常短的训练运行。突然之间，我看到从中展现出了明显的通用性，因为那好像是一个摄影数据集。它就只是一些物体的照片，但即便仅凭那些，我就看到了比如我能把一个 logo 放一件衬衫上。我能放……我能做到，虽然当时效果还不算好，但这显然表明模型正在学会在这两个概念之间建立注意力关联，并利用这些预训练好的关系。

然后我带着那个成果去了我们的下一次公司团建（off-site），展示了结果。随后在大概几个月的时间里，它基本上变成了一个更偏全公司范围的项目，我们真正投入了精力，把人拉了进来，真正做出了改进。这主要是一个数据集项目。我会说，它主要就是一个数据集项目。

<details><summary>Original English</summary>
top of the dog. It it needs to have this general understanding. And my kind of theory in mind at the time was that since the model already has all of this like spatial knowledge, if we essentially build the right data and train the model like train an already pre-trained model the right way, we should be able to evoke essentially like general image editing with very very little training. capturing these already like pre-built relationships of when things are are there, when they're not there, uh, and how these like relationships, this these spatial relationships inside of an image work. And then essentially what it became is like a three to form, I don't remember the timeline of uh, me here over in our SF office with the one data guy I stole building out essentially just early test training data sets. And and I remember the moment I saw that this was like clearly working quite well when we made this effectively tiny data set of just very like highquality labeled. It was essentially describing like simple relationships in an image and that was really it. Uh like it wasn't a way that you would prompt a modern like edit instruct model. It was just literally describing these relationships. And I trained the model for like I mean it was maybe like six hours of training, four hours of training. It was it was very very short training run. And all of a sudden like I saw what felt like a clear generality coming out of it because it was I think it was like a photography data set. It was just like photos of stuff but even just from that I was seeing like I can put a logo on a shirt. I can put like I can do and it wasn't good. It was just like the model was clearly learning to attend between these two concepts and use these pre-trained relationships. And then I took that to our next off-site, showed results, and then it became this essentially more companywide project for about, you know, a couple months where we really put effort in, brought people in, you know, really improved essentially. It was mostly a data set project. Like I'll I'll say it was mostly a data set project.
</details>

>> 然后在最终……

<details><summary>Original English</summary>
>> And then in the endation,
</details>

>> 然后 Axel 做了大量非常出色的蒸馏工作来让它提速。随后我们基本上就能够将这个模型推向世界了。对此我感到相当自豪。是的。这是首个真正做到这种角色一致性编辑的模型，而且是在极高的速度下完成的，这再次让如此多的人能够使用它。

<details><summary>Original English</summary>
>> and then there was a lot of there was a lot of very nice distillation work by Axel that was done to to speed it up. Then we essentially were able to put out put this model out in the world. And I I was quite proud of. Yeah. It was the first kind of model to really do this character consistent editing right in in like high speed that made it again accessible to so many people.
</details>

>> 对大多数人来说，生成某种内容、与它对话、对它进行修改是非常普遍的做法。在此之前，图像生成需要耗费相当长的时间，而且你需要重新生成整张图像。你无法更改……

<details><summary>Original English</summary>
>> For most people, it's very common to generate something, chat with it, change it. Before this, image generation took quite a while and you needed to recreate the image. You couldn't change the
</details>

>> 同一个角色。不会是同一个人。你……

<details><summary>Original English</summary>
>> same character. You wouldn't be the same. You
</details>

>> 或者你必须把你给不喜欢的部分打上遮罩，然后再填充。

<details><summary>Original English</summary>
>> or you need to mask uh something that you don't like and then fill in.
</details>

>> 是的。我只是想摆脱那种“老虎机”式的模式。基本上，每个人都不得不像玩老虎机一样，不停地写提示词、写提示词、写提示词，而非常明显的是，迭代式编辑是一种有效得多的方式。

<details><summary>Original English</summary>
>> Yeah. I just I wanted to get away from the slot machine. Essentially, everyone had to do the slot machine prompt and prompt and prompt and prompt and it was very clear that like iterative editing was like a much more effective.
</details>

>> 我那粗糙的 ComfyUI 工作流就是直接生成 10 个不同的版本换来换去。[笑声] 是的。

<details><summary>Original English</summary>
>> My crappy comfy UI was that like it just swapped out like 10 different versions. [laughter] Yeah.
</details>

>> 我最喜欢的部分……我仍然会换来换去，比如我现在就乐于生成四张、生成……比如重做某个东西时就做 10 次迭代，然后……

<details><summary>Original English</summary>
>> My favorite part I still swap out like I'm enjoy living generate four generate like redoing something just make 10 iterations and
</details>

### 基础模型与工作流整合

>> 然后是的，最终某一张就足够好了。我最喜欢的情景是你要向“R and Jesus”（随机数之神）祈祷，因为那完全是个随机数。基本上，对我而言，所谓基础模型（foundation model）的概念就是类似这样的东西：大家用来做这做那的这一整套繁琐小工作流以及所有这些不同的工具，我们都要用一个模型来替代。

<details><summary>Original English</summary>
>> and then yeah eventually that one's good enough. My favorite is that you pray to R and Jesus because it's a random number. Uh basically you know to me this concept of what is a foundation model is something like this where it's like okay you know all these little workflows that you guys do to like do that and do that and do that and all these different tools we're going to replace that with one model
</details>

>> 而那确实正是我们正在努力构建的方向，对吧，这也是 Flux 的发力点所在……

<details><summary>Original English</summary>
>> and that's that's actually what we're building towards right and that was where flux
</details>

>> 这对我来说是一个非常清晰的顿悟时刻。

<details><summary>Original English</summary>
>> this was a very clear aha moment for me
</details>

>> 我不知道……我从未尝试过 prompt to prom，但我认为对我来说，最接近 Flux Context 的是 Quinn image。Quinn 那帮人做得非常棒，他们做了一个 Photoshop 图层模型。是的，那很……

<details><summary>Original English</summary>
>> I don't know the I never tried prompt to prom but I think uh to me the closest has come to flux context is Quinn image which like the Quinn folks are doing really good like they had a photoshop layer model. Yeah, it was
</details>

>> 是的。没错，他们那边正在做相当酷的东西。

<details><summary>Original English</summary>
>> Yeah. No, no, I mean they're doing doing pretty cool stuff over there.
</details>

>> 很有意思的是，这其中有多少东西归根结底都回到了“全靠大量优质数据”。

<details><summary>Original English</summary>
>> It's interesting how much of this just comes back to it was a lot of good data.
</details>

>> 是的，我的意思是针对优秀的概念使用了针对性的优质数据。我都不知道该怎么描述我们这儿的情况了，不过是的，我认为有一点让我感到惊讶的是——再次谈谈 Stability，Stable Japan 对吧。日本整个国家出台了这样的法律，规定如果你在有版权的内容上进行训练，我们会为你提供保护……

<details><summary>Original English</summary>
>> Yeah, I mean it was it was targeted good data for what is it a good concept. I I don't know what how to even describe us here but yeah I I think one thing that I'm surprised by is so you know comment on stability one more time stable Japan right Japan had this like whole law of like we will protect you if you train on copyright
</details>

>> 开放任何东西……

<details><summary>Original English</summary>
>> I'll open anything up
</details>

>> 作为一个国家。我当时就想，哦，Stable Japan，有趣的是后来什么都没发生。[笑声]

<details><summary>Original English</summary>
>> as a country and I was like oo stable Japan like it's interesting nothing happened [laughter]
</details>

>> 我一直想去参观那个办公室，实际上我一直没去成，还挺遗憾的。

<details><summary>Original English</summary>
>> I always wanted to visit that office I was sad I never did actually
</details>

### 全模态尝试与数据权衡

>> 我觉得就你的 omni 观点而言，那也是一个有趣的时期。还有另外两个，Gemini 显然是最新的全模态模型。对于 Meta 那款我之前没意识到的 2023 年图像模型，他们加入了单一嵌入、热力图以及……

<details><summary>Original English</summary>
>> I think uh on your omni point as well it was an interesting time there were the two others Gemini is obviously the latest omni uh image which I didn't realize is 2023 from Meta. They threw in one embedding heat maps and
</details>

>> 深度。那是一个大项。

<details><summary>Original English</summary>
>> depth. That's a big one
</details>

>> 你知道，我觉得那非常早期，但确实很酷。我认为这项工作已经取得了进展。绝对有了越来越新的成果。

<details><summary>Original English</summary>
>> which you know I'm like oh very early but like it's cool. I I think this work has progressed. There's definitely newer newer.
</details>

>> 是的。比如 IMU……

<details><summary>Original English</summary>
>> Yeah. So like I amu
</details>

>> 你知道，这也就是另一种颜色，对吧，RGB 还有无论那是什么。

<details><summary>Original English</summary>
>> you know this is just another color right there RGB a whatever that is.
</details>

>> 是的。没错。所以到底有多少种颜色？

<details><summary>Original English</summary>
>> Yeah. Right. So like how many colors are there?
</details>

>> 哦，有趣的是，这还是“全进全出”的。所以如果你想的话，可以从文本到热力图。你可以从 IMU 到……对此有很大的市场。

<details><summary>Original English</summary>
>> Oh the fun thing this was also all all in all out. So you can go text to heat map if you want. You can go IMU to de big market for that.
</details>

>> 但有趣的是，并没有视频输出，而我认为这算是……

<details><summary>Original English</summary>
>> But interestingly, you know, no video out, which is I think the the kind of the
</details>

>> 核心的东西，也就是我们为了从根本上更好地理解世界所需要的东西，对吧？我认为这一直是我们所做事情的核心。

<details><summary>Original English</summary>
>> the central thing that that we need to to to to understand basically the world better, right? This this is I think what what's said what has always been at the core of what we we're doing.
</details>

>> 是的。好的。那么在我们结束这类数据或知识产权的讨论之前，是否存在某种整个行业都知道极具价值的特定数据？如果有数据供应商在收听，他们该如何向你们推销？他们该如何接触你们？这在很大程度上取决于你想要解决什么类型的问题。这极其重要。如果我要训练一个机器人，显然我需要大量的自我中心（第一人称）视角数据，我认为这并不是什么秘密，对吧，因为那正是这台机器未来所需要的。

<details><summary>Original English</summary>
>> Yeah. Okay. Well, before we leave the the sort of data disc or IP discussion, is there a particular kind of data that is uh everyone in an industry knows is like valuable? uh if people if if I have have a data vendor listening how do they sell to you what how do they approach you depends heavily on what you what type of problem you want to be solving that's just super important if if I train a a a robot I obviously need a lot of egocentric data I think that's not a secret right because that that is just how this thing will be will be
</details>

>> 自我中心视角，是的。

<details><summary>Original English</summary>
>> egocentric or yeah
</details>

>> 我的意思是，对你们来说也是有好处的，对吧？在语言模型方面，有很多人在构建强化学习环境，是否有某种类似的领域是人们应该过来做的……

<details><summary>Original English</summary>
>> I mean there's also a benefit for you guys right on the language model side there's a lot of people doing our environments is there a parallel that people should come do
</details>

>> 我是在帮你拉供应商呢，是的。哦，实际上有非常多的数据供应商来找我们……

<details><summary>Original English</summary>
>> I'm trying to get you vendors yeah it's Oh, we have so many data vendors actually that that approach
</details>

>> 太多了。是的，确实很多……

<details><summary>Original English</summary>
>> too many. Yeah. Yeah. It's a lot of
</details>

>> 哦，好吧。什么是好的，什么是坏的？

<details><summary>Original English</summary>
>> Oh, okay. What what is good versus bad?
</details>

>> 这同样取决于你处于训练的哪个阶段，以及你的实际目标是什么。我认为这里存在权衡，我们之前就谈过这个，对吧？数据规模与质量之间的权衡。这就是你在每一次训练运行中必须做的事，就像你进行的每一次大规模预训练一样，你必须重新找到那个最佳平衡点。因为取决于你可能使用的架构，情况可能又会大不相同。而这也是你必须进行的核心预训练实验或预缩放实验之一：你基本上需要做一个梯度测试（ladder），以在规模化的情况下理解或预测我到底需要多少数据，以及质量应该如何，从而在数据量与数据质量这两个维度之间找到最佳平衡点。

<details><summary>Original English</summary>
>> It again depends on which stage of the training you are um and what your effective goal is. I think there's a there's a trade-off between we had this already, right? scale of the data versus um versus the quality. And that is what you have to for every training run like large scale pre-training run you do again you have to kind of find find that sweet spot out because depending on the architecture you you might be using uh that might look very different again and that is one of the central pre-training experiments like or pre-scaling experiments that you need to do you need to do a ladder basically um to understand at scale how much or to to predict at scale how much data do I actually need and how should the quality look like so where's the sweet spot between like these two dimensions of data quantity versus data quality.
</details>

>> 还有没有其他我们想提出来的重大飞跃？Flux 1 Context 算是一个重大飞跃。Flux 2、Flux 工具、Action，我们稍微聊过一些。还有其他……

<details><summary>Original English</summary>
>> Any other major jumps that we want to call out? So flux one context was a big one. Flux 2, flux tools, action, we talked a bit about any other
</details>

>> 我觉得三种规格非常重要，就比如你知道的 dev 模型和 schnel……

<details><summary>Original English</summary>
>> I mean I think the three sizes that's very important in terms of like you know the the dev models and the schnel
</details>

>> 是的，那是……

<details><summary>Original English</summary>
>> yeah what is
</details>

>> 在德语中意味着快速。啊。

<details><summary>Original English</summary>
>> means fast in German. Ah
</details>

>> 是的，我想你在书里大概讲过那个，不过是的，我认为就包括你有开源版本、有闭源版本，并且涵盖了不同的性能区间，我认为这很合理。是的。是的。我的意思是，如果说还有什么值得关注的，那就是……好吧，唯一一件让我感到挺遗憾、我们没能完全融入 Flux Context 的事情，就是它仅支持单图编辑。因为我是说，很明显存在……

<details><summary>Original English</summary>
>> yeah I think you probably covered that in the book but yeah I think that that like is you you have open source you have the closed source and you you have the range of performance I think that makes sense. Yeah. Yeah. I mean I guess if like anything to track on is like okay one the one like thing that made me quite sad that we didn't quite get in with flux context is it was only single image edit because I mean I s it was very clear that there was like
</details>

<!-- chunk 10/14 -->

对多图输入有极大的需求，你知道，大家希望能够放入很多很多不同的图片，并且建立关联——这里用“参考”（reference）这个词更准确。是的，很多很多不同的参考图。

<details><summary>Original English</summary>
a huge need for for multi-image like people you know want to be able to put in many many different images and relate reference is a better word here. Yeah. Yeah, many many different references
</details>

>> 我觉得目前 Grok 算是这方面的王者。

<details><summary>Original English</summary>
>> which I think Grock is like king right now.
</details>

>> 是的，这个我不太了解。

<details><summary>Original English</summary>
>> Yeah, I I don't know this.
</details>

>> 我知道 Midjourney 在风格库（style books）方面做了不少工作，你可以在里面建立——

<details><summary>Original English</summary>
>> I know I know Mid Journey does quite a bit on style books where you can build up
</details>

>> 参考。你是说他们一直非常擅长做风格参考，但这里更偏向泛化的场景。比如之前的 Flux 上下文只接受一张图片，所以你只能针对同一张不够好的照片去迭代，但你本来完全可以提供同一个人的三张不同照片。

<details><summary>Original English</summary>
>> reference. You mean they've always been very good at like the sty style reference, but this is more just like general like like f flux context would only take one image and so it was just you can only iterate without a bad photo of one person that's but you could have three different photos of the same person.
</details>

>> 但它其实已经足够通用了。我记得当时其实挺有意思的，大家都在做一些工作流，把一堆图片拼成一张图来模拟这种效果。不过到了 Flux 2，我们终于能够花时间去构建数据，并真正进行更大规模的训练，来支持当时我记得是 10 张参考图。所以本质上是构建了更大的上下文空间供模型处理。

<details><summary>Original English</summary>
>> But it was actually general enough. I remember it was it was actually quite funny. People were like doing workflows where they were stitching a bunch of like images into one image to like emulate it. But then with Flux 2, we finally were able to like spend the time to to to kind of build out the data and actually do this larger scale training for handling I think it was 10 reference images at the time. So essentially building up much more context to work within.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这在很大程度上又是一个数据问题，你就是需要有包含这么多参考图的数据。对吧。

<details><summary>Original English</summary>
>> Which is again also a lot of to to a large extent a data data um problem that you just need a data as these many references. Right.
</details>

### 多图上下文与评估基准

>> 这是否存在一个实际的上限？比如说，行业标准大概是 10 个角色或 18 个角色，就差不多了，对吧？

<details><summary>Original English</summary>
>> Is there a practical limit? So you know let's say the industry standard is like 10 characters or 18 characters. That's it, right?
</details>

>> 对，我不需要 100 个。

<details><summary>Original English</summary>
>> Yeah. I don't need 100.
</details>

>> 显然，你可以展示一些夸张的数字，比如一张图甚至一段视频里能放进多少个角色或多少张图片，但要给我搞出 100 个参考对象，那就得靠 Agent 来做了 [笑声]。

<details><summary>Original English</summary>
>> Obviously, you can show crazy numbers on I don't know how many on how many characters you or like like images you can get into one image or also video, but there are like that is agent work then to to get me 100 reference [laughter]
</details>

>> 那反而是简单的事了，对吧？交给 Agent 做就行。

<details><summary>Original English</summary>
>> which is the easy thing, right? It's agent work.
</details>

>> 但接下来我得去检查它。我得审查 100 张图片看是不是我想要的。这其实也是一个很棘手的创意问题，比如我该把这些东西放在哪里——

<details><summary>Original English</summary>
>> But then I need to check it like I I then I have to review 100 images if that is actually what I it's actually also a hard creativity problem like how should I where should I put these things
</details>

>> 100 张图片。所以我觉得在不过度纠结数字的前提下，任何超过 10 个参考项的内容，人类理解起来也已经很吃力了。我想，比如你说好我们要制作一段视频，我显然可以在里面放进 50 个人，但如果你看那些最经典的电影，核心角色能有几个？

<details><summary>Original English</summary>
>> 100 images like So I think without like like overindexing on the number everything that goes up like like over over 10 10 references is also hard to follow for a human. I think like if you say okay we want to be creating a a video right I obviously can can put in 50 people there but if you look at the mo like the the most important movies how many central characters do we have
</details>

>> 最多也就五六个。

<details><summary>Original English</summary>
>> like five six maximum
</details>

>> 除非是《复仇者联盟》。

<details><summary>Original English</summary>
>> unless you're Avengers.
</details>

>> 没错。[笑声] 那样的话，到某个阶段其实就已经逼近了人类在一段 2 分钟的片段里实际所能处理的信息极限。回到评估的话题，我知道你之前提到了 evals，为更大的上下文模型构建评估集会变成一个庞大得多的流程。比如我们最终发布了一个开源评估集，叫 context bench，它是基于我们内部用来评估上下文的 bench 构建的。而随着你把参考项的数量规模往上推——

<details><summary>Original English</summary>
>> Exactly. that [laughter] that is then also it's at some point approaching the the kind of limit of what we humans can actually kind of process in in a 2 minutes clip or something. This also gets way like coming back to the I know you mentioned the evals earlier building evals for larger like contextual models becomes a much bigger process like even for like we we ended up releasing a uh an open eval set for um it was context bench which was built off the internal bench that we used to evaluate context and then as you scale up how many references
</details>

>> 噢，这个我还没看过，好吧。

<details><summary>Original English</summary>
>> oh I haven't seen this okay
</details>

>> 对对，去看看 ContextBench 吧。这项工作耗费了很大精力，但整理这些东西其实还挺好玩的。

<details><summary>Original English</summary>
>> yeah yeah please contact this was a lot of work but kind of it was actually quite fun to put this together
</details>

>> “把猫变得非常胖”。

<details><summary>Original English</summary>
>> make the cat very fat
</details>

>> 是啊，真的，我记得当时我和另外几个人就坐在旧金山办公室的后屋里。我和 Tim 一直在笑。Tim Dawhorn 也是我们团队非常棒的一位伙伴。

<details><summary>Original English</summary>
>> yeah I mean it We lit I remember sitting in the back room of our SF office with like a few of the other guys. Like me and Tim were were laughing. Tim Dawhorn is another one of the great great guys.
</details>

>> 所以你们就是嗑了点大麻软糖然后就开始搞吗？[笑声]

<details><summary>Original English</summary>
>> So like do you just like take some edibles and just go like [laughter]
</details>

>> 其实就是大半夜坐在那里，字面意义地随手输入各种内容，找一些图片，然后敲下最蠢的词句。

<details><summary>Original English</summary>
>> I mean you just you're sitting there late sitting there late at night literally just typing in the like we're just pulling images and typing in the stupidest things.
</details>

>> 但那是真实的测试，我不知道该怎么说。因为——

<details><summary>Original English</summary>
>> I mean that like but it's like real like I don't know. So because
</details>

>> 毕竟你最终显然需要往前走一步，去确定什么才是基准真相（ground truth）。

<details><summary>Original English</summary>
>> in the end you obviously need to kind of make one step to make it a kind of what is ground truth.
</details>

>> 你得确保——

<details><summary>Original English</summary>
>> You you need to make sure that
</details>

>> 确保某处有一个基准真相。

<details><summary>Original English</summary>
>> you have a ground truth somewhere.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 不，这基本上只是一个基准测试（benchmark）。它其实只有输入，

<details><summary>Original English</summary>
>> No, this is just a benchmark basically. It's just inputs,
</details>

>> 对吧？但输出在哪里？

<details><summary>Original English</summary>
>> right? But where's the where's the output?
</details>

>> 评估在哪里？

<details><summary>Original English</summary>
>> Where's the eval?
</details>

>> 有意思的地方就在这里，对吧？你直接去问人。这是一个公开的 bench，给所有人展示：这就是评估基准。然后你拿出两个模型，你想——

<details><summary>Original English</summary>
>> I mean that is the interesting thing, right? You just ask people. This is a public bench to give everyone like this is the eval. And then you you have two models that you want to be
</details>

>> 对，对。所以从这个意义上说它并不是一个验证集，它只是一个评估。

<details><summary>Original English</summary>
>> Yeah. Yeah. So it's not a validation set in that sense. It's just a email.
</details>

>> 这纯粹就是 Dustin 坐在屋子里搞出来的，大概 80% 都是这样，它——[笑声]

<details><summary>Original English</summary>
>> This is just Dustin sitting in a room genuinely like 80% of this is that like it it's um [laughter]
</details>

>> 深受我们意大利团建的影响，我想。

<details><summary>Original English</summary>
>> heavily influenced by by our uh I think by our Italy offsite uh
</details>

>> 就像玩填字游戏（Mad Libs）一样做那种组合爆炸式的尝试，但这比纯随机更有结构。

<details><summary>Original English</summary>
>> when you do like a Mad Libs like like a combinatorial explosion type thing that is more structured than just random.
</details>

>> 所以我们现在确实在做更多类似的事情。我想说的是，这里面公开的那套集合，我们必须过滤掉某些内容，因为内部版本里确实有些非常蠢的东西。但我花了很多时间，我喜欢看大家究竟是怎么用我们的模型的。而且我本身就是一个非常喜欢亲自去用我们模型的人。我认为非常、非常重要的一点是，你必须去测试和试玩——就真的是去“玩”你的模型，比如玩梗做表情包，像我这样。去按人们真正想要的方式去用它。就像我说的，我来自 Discord 开源社区，在那儿你能看到大家在做各种极度愚蠢的事情，但大家乐在其中。所以这套测试集里，除了试图涵盖一堆实际用例——那些非常重要的生产级用例之外，我也想确保这模型用起来是有趣的，你知道的，所以——

<details><summary>Original English</summary>
>> So so I mean now we're do we definitely do more stuff like this. I will say that so one other thing is there were I mean there were certain things we had to like filter out for the public set on here cuz it's just there were some very dumb things in the internal thing you know in the internal set but um [gasps] I don't know I I spend a lot of time I like to see how people actually use our models like and I I'm someone that actually really likes to use our models I think it's very very important that you test and play like really just play I'll say play with your models like memes like me like yeah like use it for what people actually want to use it for like I came like like I said I came from Discord open source communities on this you see people doing the stupidest things, but it's like this is people are having fun with it and it's so a lot of the set, you know, besides trying to cover a bunch of actual use cases, uh, like production use cases, which which are very important, I also want to make sure it's just like the models are fun to use, you know, and so
</details>

>> 很好的氛围感。

<details><summary>Original English</summary>
>> good good vibe vibe.
</details>

>> 没错，是的。

<details><summary>Original English</summary>
>> Exactly. Yeah.
</details>

>> 三年前我可能低估了这一点。那时觉得，对，这不就是做表情包嘛；对，这不就是花个三十多块钱订阅玩玩嘛。但它其实会转变成非常真实的严肃工作。

<details><summary>Original English</summary>
>> What I think is like I I underappreciated three years ago, which was like, yes, this is memes. Yes, this is like a mid-30 whatever subscription, but like it actually becomes very real work.
</details>

>> 是的，完全没错。因为他们先是玩着玩着做出了乐趣，接着就会想：“噢，我可以在——”

<details><summary>Original English</summary>
>> Yeah. Exactly. Absolutely. Because they've done it for fun, then they're like, "Oh, I can do this at
</details>

### 模型开发中的采样与反馈机制

>> 实际上，当你对这些模型做自动化评估时，整个领域里大家显然都在做很多针对人类的评估，但每种评估都会有盲区，你应该尽可能把多个独立的评估结合起来，以便尽可能全面地掌握——

<details><summary>Original English</summary>
>> Effectively also like when you when you automatically eval these these models like there's a bunch of obviously human evals that everyone is doing in the field, but every evaluation will have their blind spots and you you should be combining as many independently as possible to get a
</details>

>> 掌握关于模型表现究竟如何的尽可能准确的整体情况。但这并不会免除你亲自去——或者说这根本不是一种负担，亲自去对模型进行采样实际上非常有趣，去真正弄清楚优势在哪里、劣势在哪里。这是模型开发的核心部分，也就是——

<details><summary>Original English</summary>
>> picture that is as good as possible of like how the model is performing. But that doesn't like remove the burden from you to kind of or it's not a burden. It's actually super fun to then sample the model yourself and actually understand where are the strengths, where are the weaknesses like this is this is a core part of developing a model is actually
</details>

>> 在开发时不断采样，并检查：“它有没有达到我预期的状态？”对吧。

<details><summary>Original English</summary>
>> constantly sampling when developing it and checking a is it is it where I would expect it to be right
</details>

>> 在某种程度上这也关乎你们真正在意的东西，对吧？这些就是你们的用例。如果你们想让某些方面变得更好，这是一种很好的方式：建一个小基准，然后看看各方面表现如何。确实是这样。我非常认同做模型的人必须真正喜欢——

<details><summary>Original English</summary>
>> at some level it's like what you guys care about too right like these are your use cases it's a good way for if you want something to get better like make a little benchmark and see how things perform. No, absolutely. I I think it's very important that the people building the models actually like
</details>

>> 真正想去用这个模型。我觉得这非常重要。

<details><summary>Original English</summary>
>> like want to use the model. Like I think this is very important.
</details>

>> 这跟比如麦克风品牌试图用它来拍产品照之间有很大差别。那是他们可以针对性做极值优化的极小众用例，相比之下——

<details><summary>Original English</summary>
>> There's a big distinction in this and like the microphone brand trying to you know use it for product photos. A very niche use case that they can minmax on compared to removing
</details>

>> 相比之下这是非常通用的。是的。不过我确实有一个疑问或者说好奇：Midjourney 有一个非常著名的循环机制，就是依托 Discord，每个人都能看到其他人在用什么提示词，你会得到四个选项，你从中选一个，而这个选择就成了下一个模型的反馈数据。你们为什么完全没做这种机制？

<details><summary>Original English</summary>
>> very general. Yeah. I I I think one thing I do doubt or question is that a very well-known midjourney is loop which is the it's discord. Everyone sees like other people prompting you get the four options you choose the four that is feedback for your next model. How come you didn't do any of that?
</details>

>> 我们没有公开且大规模地去做这件事。所以每一个——

<details><summary>Original English</summary>
>> We didn't do it publicly at scale. So, so every one of
</details>

>> 这么做没有价值吗？它可能是有价值的，但我认为价值只在一定限度之内。如果你越过了某些界限，你得到的信号其实就相当……在早期阶段，我们确实看到了这种微调带来的惊人潜力，对吧，比如 Midjourney 的 V5 之类，非常惊人；

<details><summary>Original English</summary>
>> Isn't it valuable to do? It can be valuable but I think only up to a certain extent and if you then like cross certain limits the signal that you get is pretty pretty like early days we saw these insane potential right of this this this tuning uh say of of majour's models like V5 or something crazy
</details>

>> 但如果你的基座模型达到了一定的实力水平，你其实就不会再拿到那些能明确看出模型因此而获得提升的极佳样本了，而且这里面也夹杂了大量的噪声。所以其实有很多其他的方法可以让你——

<details><summary>Original English</summary>
>> but if your base model just reaches a certain certain kind of level of strength it's actually you don't get these super good examples anymore where you can clearly see the model improving from this and this is also a lot of noise. So there are there are a lot of other ways how you can actually
</details>

>> 我之前也跟某个人争论过这个问题。

<details><summary>Original English</summary>
>> I had this debate as well with someone
</details>

<!-- chunk 11/14 -->

在当时那非常有用，因为提示词遵循能力还不怎么好，对吧？呃，当两者都做得不够好时，评判哪一个更能遵循提示词的主观性就很强，对吧？所以你会有很多针对这方面的偏好微调，这里面信号非常强，大家确实更喜欢这个。现在回到我之前提过很多次的一个观点，比如——

<details><summary>Original English</summary>
where back then it was very useful because prompt adherence wasn't great right uh it's pretty judgmental on which one follows the prompt better when neither of them do it great right so you have a lot of preference tuning towards there's very high signal and okay the people prefer this now back to my point a lot earlier like
</details>

>> 如果我拿出排名前五的模型，让它们把一张床移掉，在我看来结果都会差不多。这种偏好里的信号就没那么强了，对吧？它们填补得都相当好，因为……

<details><summary>Original English</summary>
>> if I take the top five models and tell them to remove a bed it's all going to look the same to me the preference there's not that much signal right? They're all filling it in pretty good because there's like
</details>

>> 它们非常理解这项任务。所以对我来说，评测的那一面就有点不复存在了。看起来都……【清喉咙】都还行。但是……

<details><summary>Original English</summary>
>> they understand this task very well. So that side of the eval for me is kind of gone. It all it all looks [clears throat] fine. But
</details>

>> 是的。

<details><summary>Original English</summary>
>> yeah,
</details>

>> 我正想插一句说，这其实是我转向上下文最喜欢的部分之一，那就是终于不再只是……

<details><summary>Original English</summary>
>> I was going to jump and say that was actually one of my favorite parts of of moving into context is finally it wasn't just like
</details>

>> 我……我不知道，终于变成了：好吧，它到底有没有完成这项任务？

<details><summary>Original English</summary>
>> I I don't know. It was finally just like okay did it actually just do the task
</details>

### 自回归图像生成与扩散模型

>> 而且……而且我真的很喜欢面对这些非常清晰、具体的任务。关于结构还有最后一点，然后我们就想聊聊具身智能和机器人。嗯，自回归图像生成。

<details><summary>Original English</summary>
>> and and I really enjoyed getting to these like very kind of clear concrete tasks. One more part of the texture and then we want to go into robotics in action. um auto reggressive image gen.
</details>

>> 这似乎是一个大趋势，Gemini 和 ChatGPT（Chad）都在这么做。呃，在你的心目中，它的影响有在我们看来那么大吗？你懂我的意思吧？比如我……我觉得这似乎是一个非常大的转变，因为这样你就可以通过对话进行编辑了。这就像是从上下文、呃，Flux 语境下顺理成章迈出的下一步，不再是用图像和文本提示词来编辑，而是通过对话的方式与一个……与一个模型协作。

<details><summary>Original English</summary>
>> It seems like a big trend with both Gemini and Chad doing it. Uh like is that as big an impact in in your mind as it is in ours? You know what I mean? Like I I it seemed like a very big change because then you could conversationally edit. It is the like the next obvious step from cont uh a flux context where instead of editing with an image and and text prong you're conversationally working with a with a model
</details>

>> 我觉得这并不仅仅是自回归模型独有的特性，它只取决于你在什么数据上进行训练。而且，你同样也可以让扩散模型具备语言能力，对吧？

<details><summary>Original English</summary>
>> that I would say is not a a feature of auto reggressive models only it's just based on the data you train on it and like you you can get language capabilities into a diffusion model as well right
</details>

>> 是的。

<details><summary>Original English</summary>
>> yes
</details>

>> 我们知道这是行得通的。而且，呃，我说过长期来看，我们相信这也将是指向的方向，也是我们正在努力的方向，那就是引入更多模态，包括这个语言部分，对吧？所以这不是……这不是算法本身的问题，嗯，这基本上只是一个你把重心放在哪里的问题。我认为这两种方法都非常令人兴奋，都有很多优势，也都有很多缺点。

我会说自回归模型在数据效率上要高得多，你在数据上能把它们训练得好得多。因为对于扩散模型来说，你有一条从数据到噪声的轨迹，对吧？而你用来训练的每一个训练样本，实际上……因为在这之间有一条从数据到噪声的连续路径。它为你产生无限多的训练样本，因为对于某一个样本，你可以在这条从数据到噪声的轨迹上挑选每一个可能的点来去噪。显然，如果你只在这一个……呃，样本上训练，模型就会过拟合。从理论上讲，这就相当于一个训练样本——或者说一个数据点——产生了无限多的训练样本。

然而，自回归模型基本上可以在所有 token 上并行训练，并从每个训练样本中获取最大梯度。这是训练方面。所以在这一块，我会说自回归模型的数据效率更高。然而，在采样、在采样阶段，自回归模型必须……逃不过这一点，它们必须自回归地一个接一个地生成 token，因为它们在类似……类似数据方向上是迭代进行的，对吧？而扩散模型，你可以直接把 50 步蒸馏降到 4 步，以此把它大幅提速，这在自回归那边是根本不可能的，因为你必须自回归地一个接一个接一个地生成 token。所以这只是两种……两种……

<details><summary>Original English</summary>
>> which we know is is uh working and um I said long term this is where we believe this will this will also go point to and where we're working towards which is to also get more modalities in including this language part right so it's not it's it's not a question of the of the of the algorithm there um it's just a question of like what you focus on basically I think both approaches are extremely exciting and have a lot of strengths and a lot of like shortcomings I I would say autogressive models are way more data efficient you can train them way better in data because every like you have for for diffusion models you have this trajectory from data to noise right and every training example you're training on is effectively because you have this continuous path from data to noise in between. It's giving you rise to infinitely many training examples because you can pick every possible spot to dn noiseise from from this trajectory between data and noise for one example. Obviously, the model would overfit if you would only train on on this one uh example. Theoretically, it's just like one training example is giving or one data point is giving rise to infinitely many training examples. Whereas all regressive models can just train on all the tokens in parallel basically and get the maximum gradient from each training example. That's the training side. So there I would say our regressive models are more data efficient. However, at the sampling at sampling time or regressive models have to don't get across that. they have to autogressively create one token after the other because they're iterative in this like like data direction, right? And diffusion models you can just go down and distill 50 steps down to four and by that you can speed that up so much which is on the autogressor side just not possible because you have to auto reggressively generate token after token after token. So these are just two two um
</details>

>> 等等，你这么说听起来就像是它更差……所以在……所以自回归生成在那方面确实有局限性；但另一方面，扩散在训练时的数据效率方面也是一种局限。所以我们……实际上我觉得……我两种方法都喜欢。我们很久很久以前也一直在研究自回归模型，我觉得两者都超级让人兴奋。

<details><summary>Original English</summary>
>> wait you make it sound like it's just worse than so so autogressive generation is in that respect it has a limitation but on the other side if fusion has in in the terms of data efficiency at training is also limitation so we we actually I think it's I I like both approaches we've also been working on autogressive models like long long back and both is super exciting I would say
</details>

>> 所以在……呃，数据效率上，自回归胜出了。

<details><summary>Original English</summary>
>> so on uh data efficiency auto reggressive wins out though
</details>

>> 好吧，那扩展规模方面……呃，我想在与同时做过类似 ChatGPT 和图像生成的人交流之后，你能看到的另一大亮点，就是你如何能像智能体那样加入循环。这样模型就能以智能体的方式……你知道，生成某些内容，对其进行推理，编辑图像，并继续这一工作流程，它们可以做到这一点。

<details><summary>Original English</summary>
>> okay so scale um I guess the one of the other big things that you see having talked to people that worked on both like chachbt and genen is how you can add in the loopl like aentically so models can do agentically you know generate something reason on it edit the image and continue that workflow they can do that
</details>

>> 而且这是……【清喉咙】但这跟扩散生成中的流水线化是两码事，对吧？它全是同一个——比方说——同一个模型在做，而在……

<details><summary>Original English</summary>
>> and this is [clears throat] but this is separate than pipelining in diffusion generation right it's all the one say model doing it where
</details>

>> 当你在数据层面把这训练进去时，你知道，你是可以将其扩展的。呃，我想扩散模型在这方面有应对方案吗？

这本身并没有什么固有限制，说明你不能让一个基于扩散的模型去做完全相同的流程，让它能够胜任所有这些方面。就像我……我之前理解错了，基本上是 nano banana 出来之后，我就觉得，天呐，自回归才是王道，但你的意思是……

<details><summary>Original English</summary>
>> as you train that in on a data level you know you can scale that um I guess is there a counter to this in diffusion There's no inherent limitation to that you couldn't have a model that is diffusion based do the exact same process that can do all of these aspects like I I had the wrong basically nano banana happened and I was like holy like auto reggressive is a thing but you're saying
</details>

>> 我觉得，难道我说错了吗，那难道不是……

<details><summary>Original English</summary>
>> I think am I wrong that isn't
</details>

>> 那个我认为是基于扩散的，我认为那个自……就像它是……

<details><summary>Original English</summary>
>> was I think it is diffusion based I think the auto like it is
</details>

>> 而且我在这里并没有什么内部消息，所以我可能是错的，但我相当肯定它……它具备语言组件来做类似自回归的事情，但它是……我认为这就是我们会称之为 Transfusion 模型的东西。所以它……呃，你知道，它基本上两者都能做，但并没有……是的，并没有什么内在限制说你……你必须采用这种方式还是另一种方式，这并不是说我们……他们在……他们在探索。

<details><summary>Original English</summary>
>> and I don't have like insider knowledge here so I might be wrong but I'm pretty sure it's it has the language component to do like autogressive but it is like I think It's what what we'd call like a transfusion model. So like it's uh you know it can essentially do both but there's no Yeah. There's no inherent limitation that says you you you have to do it one way or another and it's not like we're there they're they're exploration.
</details>

>> 对，对。我现在的理解是，这并不是……这并不是板上钉钉的共识，而我之前还以为已经形成了一股大家从扩散转向自回归的浪潮，为了……

<details><summary>Original English</summary>
>> Yeah. Yeah. What I'm getting is that it's not it's not settled consensus and I thought it was that there was a wave of people shifting from diffusion to auto regression for
</details>

>> 我觉得目前在这一方向上有很多……有很多令人兴奋的研究正在进行。我想说确实有一些非常亮眼的工作问世。显然，我们已经看到模型在那条战线上表现得极好。流匹配（flow matching）那边同样也是如此，也在不断改进。我觉得这个争论还没有尘埃落定。目前在两个方向上都依然有大量的重……重点研究在进行。而且我认为……我认为密切关注两者并且……你知道，去尝试两者，对……

<details><summary>Original English</summary>
>> I think there's a lot of there there's a lot of exciting research on that end right now going on. Like I will say there there's some very impressive work out there. Obviously, we've seen models work extremely well on that front. The same is going on for for flow matching is also improving. Like it I would say the debate is not settled yet. Like there there's still significant re research on both fronts going on right now. And I think I think it's important to watch both and be you know try both be
</details>

>> 对……感到兴奋，你知道的……

<details><summary>Original English</summary>
>> excited about the you know
</details>

>> 最终同样的情况也发生在别处。我们有……我们基本上有 VAMP，这同样超级超级有趣。对吧。

<details><summary>Original English</summary>
>> finally the same is happening for what as well. We have we are vamps basically which is super super interesting as well. Right.
</details>

>> 是的。最后另一件事我想是，也有针对文本的扩散模型，对吧。所以也有一些这类探索。所以这……这里面有好处。当然有速度，对吧？你可以……

<details><summary>Original English</summary>
>> Yeah. The the last other thing I guess is there's also the diffusion for text right. So there's also some of that. So it's there's benefits. There's of course speed, right? You can
</details>

>> 我们已经在……比如在文本上我们已经看得很清楚了，对吧？如何……

<details><summary>Original English</summary>
>> we see that already like with tax we see it clearly, right? How
</details>

>> 我们有了 Diffusion Gemma，大家也可以拿来玩玩。

<details><summary>Original English</summary>
>> we got diffusion gemma that people can play around with too.
</details>

>> 它们能达到同等水平吗？这只是资金和数据投入的问题，还是……你知道……

<details><summary>Original English</summary>
>> Will they ever reach parody? Is it just a matter of investment in money and data or like you know
</details>

>> 我觉得很大程度上是数据问题。

<details><summary>Original English</summary>
>> I would say a lot of it is data.
</details>

>> 如果……如果它行不通，为什么行不通？我的简单回答是，我们是从左到右进行推理的。我们不会……你知道，扩散到视觉中去推理。与此同时，你……我不知道，对于自回归模型，我认为很多人喜欢关注 token 的……你知道，一步一步的过程，但与此同时，它也可以并行化。就像我们……我们无法同时读完整本书，而那些模型却可以做到，所以……是的。

<details><summary>Original English</summary>
>> If if it doesn't work why doesn't it work? My simple answer is like we we reason left to right. We don't reason you know and diffuse into into vision. At the same time you like I don't know we with autogressive models I think a lot of people like to focus on the the the you know step by step of the of the tokens but at the same time it also can parallelize like we we can't just take in a whole book at the same time as well which those models can so there yeah
</details>

>> 而且你可以在潜空间（latent）里思考。

<details><summary>Original English</summary>
>> and you can think latent
</details>

>> 我完全理解，所以这就是……我的意思是，这是一个合理的疑问：为什么用于文本的扩散模型始终没有真正流行起来？而且你知道，现在它像是慢慢地稍微好一点了，但是……

<details><summary>Original English</summary>
>> I totally get it so that's I mean that is the valid question like how come diffusion for text never took off and you know now it's like slowly slightly better but like
</details>

>> 我认为这只是哪种方法起步更早的问题，而且它已经成为语言模型的……我的意思是，我觉得正如你所言，如果你说它在数据上效率更高，而且全世界都在大搞模型扩展，那么这边确实有它的道理；但这并不意味着就没有一些细分领域或用例，在特定规模下你能得到非常好的效果。比如，是的，Diffusion Gemma 相当不错，它达到了一定标准，而且运行速度非常快，对吧？如果你需要那个，那就太棒了。

<details><summary>Original English</summary>
>> I think it's just like a matter of which approach was was earlier and has been like becoming for language model I mean I think as your point you said if it's more data efficient and the world has been doing a lot of scaling there's a side there that doesn't mean that there aren't pockets where there's use cases that you can get really good things at a certain size the example is like yes diffusion Gemma is pretty good and it meets a bar and can run really fast right if you want that that's great
</details>

>> 是的，我的意思是，在自回归语言方面，它……我认为归根结底是因为它简单、可扩展，而且它当时就在那里。

它就像一条非常……我的意思是，这显然是一条非常成功的轨迹。大量的资金、时间和研究都投入到了打造……

<details><summary>Original English</summary>
>> yeah I mean on the auto reggressive language front it's it's I think it really comes down to it was simple it was scalable it was there It was like a very I mean it's clearly been a very successful trajectory. A lot of time and and money and research has gone into to making
</details>

<!-- chunk 12/14 -->

行得通。

现在扩散模型领域有很多非常令人兴奋的研究。而且我想把这个概念区分开来，因为扩散语言模型其实分成了两个阵营，我认为很多人往往没有意识到这一点：一类是离散扩散语言模型——我几乎不太愿意真把它们称作扩散模型，像 Diffusion Gemma 以及像 Mercury 代码那样的 Mercury 模型就属于这一类，它更偏向这种掩码风格的模型，从掩码跳到 token，但它仍然处于离散空间；而与此相对的是，现在正掀起一股关于连续扩散语言模型的研究浪潮，它们实际上是在运作……我不想直接说是流匹配（flow matching）模型，但它们本质上是运作在去噪空间里的，所以更像是……
<details><summary>Original English</summary>
that work. There's right now a lot of very exciting research on the diffusion front, you know, and I and I'd like to separate the notion there's because there's diffusion language is really two camps and I think a lot of people tend to not realize this because there are discrete diffusion language models which I almost don't I don't like to call them diffusion models really and this is where like the diffusion Gemma and like the mercury code like mercury models live which is is more of this like masking style model where where it it jumps from a mass to a token but it's still in the discrete space versus now there's a big wave of research right now going on continuous diffusion language models which those are actually operating as like you know I don't want to say flow matching models but they're they're operating in this like essentially dnoising space so so more like
</details>

>> 如果我没记错的话，这个曾用于音频。
<details><summary>Original English</summary>
>> this was used for audio if I'm not mistaken
</details>

>> 音频生成。
<details><summary>Original English</summary>
>> the audio generation
</details>

>> 连续。
<details><summary>Original English</summary>
>> continuous
</details>

>> 连续扩散。
<details><summary>Original English</summary>
>> continuous diffusion
</details>

>> 它可能被用于……
<details><summary>Original English</summary>
>> it's probably used for
</details>

>> 它适用于一切视觉建模、音频建模。
<details><summary>Original English</summary>
>> it's for everything visual modeling audio modeling
</details>

>> 我在这方面的最后一个趣味问题是：我们是否有好方法在纯扩散文本模型上做类似 PO 风格的强化学习？
<details><summary>Original English</summary>
>> my last fun question there is um do we have a good way to do like your PO style RL on pure diffusion text models.
</details>

>> 有，实际上我们正在做这个。
<details><summary>Original English</summary>
>> Yeah, we we're doing this actually.
</details>

>> 好的，明白。
<details><summary>Original English</summary>
>> Okay. Okay.
</details>

>> 所以在 Flux 3 上我们做了这个，它带来了巨大的收益。是的。
<details><summary>Original English</summary>
>> So for flux 3 we did this and and it has had tremendous u gains that it borrows. Yeah.
</details>

### Flux Action 与世界动作模型

>> 说到 Flux Action，这就涉及非常近期的发布以及你们正在开展的工作了。你们是如何切入这个方向的？到目前为止的反馈和影响如何？
<details><summary>Original English</summary>
>> So flux action this is coming to very very recent launches and and work that you're doing. How do you approach this? What is your what is the feedback and impact so far?
</details>

>> 是的，关于我们具体是怎么做的：基本上还是同样在视频、图像、音频等所有模态上一起进行预训练，然后你就拥有了这个理解世界的超通用模型；接着你实际上可以接入一些动作预测数据。基本上，你是在这个机器人的状态空间中加入某种预测，这基本上是对“机械臂在这里”的一种参数化描述——每个关节都将通过平移和旋转来描述，基本上就是六个自由度。然后你把这个和视频一起进行预测。既然模型已经能够对视频进行推理，知道在视频空间中为了完成某项任务需要生成什么，那么增加这个新的维度——也就是我们所说的状态空间——并将其一同预测出来，实际上就非常简单了。给定一段先前的视频作为条件输入，再加上一条指令，模型基本上就会生成下一段动作，从而去完成……
<details><summary>Original English</summary>
>> Yeah, it's actually like how how we approach it. Basically you you pre-train on again videos, images, audio, everything together and then you have this very general model that understands the world and then it actually you can can take a bit of action prediction data. Basically, you add kind of predictions in the state space of this robot, which is basically a kind of a parameterization of here is this robot arm. Um, which every joint will be described by a uh translation and a rotation, six degrees of freedom basically. And then you predict that together with a video. And since the model can already reason about the video and what it needs to create or to to fulfill a certain task in video space, it's actually very simple to then add this new dimensionality or this this new dimension, the state space how we call it, and then basically predict that as well. Given a chunk of earlier video, condition it on that an instruction basically the model creates the next chunk of actions to basically fulfill um
</details>

>> 这个动作。而且这套方案效果极其出色。我们可以在现实世界中做，比如用在实体机器人上；我们也可以在仿真中做，比如电脑操作也是将其映射到数字世界的一种形式；我们还可以让模型去玩游戏，诸如此类。所有这些都是由这个单一的 Flux 3 模型赋能的。然后你也会发现它的能力极其强大，因为我们拥有这种非常通用的预训练，不仅局限于传统的机器人数据，而是涵盖了各种各样的数据，这赋予了模型一种内在构建的理解力，你随后也能在性能中看到这一点。而且作为一个扩散模型，它速度也相当快，正如我们在这里看到的，基本上使用的是这些蒸馏版本，对吧。
<details><summary>Original English</summary>
>> this action. And this this works extremely good. It's we can do it in the real world like for real world robots we can do it in simulation like computer use is also kind of a mapping of that to the digital world and we can like we can make the model play games right and stuff like that. So this is all enabled by this this single flux three model. And then you see also that it's extremely capable because we have this very general pre-training which is not only limited to say classic robot data but actually all kinds of data that gives a model just this inherent build understanding that you also see then in performance and [snorts] being a diffusion model is also pretty speedy as we see here um with a with a with these distilled uh versions basically right.
</details>

>> 你会把这个称为世界模型还是世界动作模型？你有自己倾向使用的称谓吗？
<details><summary>Original English</summary>
>> Would you call this a world model or world action? And do you have a term you like to use?
</details>

>> 这是世界……这个是世界动作模型。“世界模型”这个词我不太喜欢用，它太……
<details><summary>Original English</summary>
>> It's a world. This this one is a world action model. I think the word the term world model I don't like to use. It's so
</details>

>> 我想法一样，在我看来目前它就像“全能（omni）”这个词一样了。
<details><summary>Original English</summary>
>> I'm in the same boat. It feels like omni to me at this point.
</details>

>> 不如称之为视觉智能模型，因为它能完成所有这些基础的事情，对吧？
<details><summary>Original English</summary>
>> Let's call this a visually intelligent model because it can do all these these basic things, right?
</details>

>> 我想我在这些模型中看到的区别在于，你不仅是在预测视频或世界，你还在预测动作状态，对吧？所以一方面是世界上正在发生什么？状态是什么？但另一方面也是要预测下一个动作是什么。所以它就像是有两种输出，对吧？所以……
<details><summary>Original English</summary>
>> I guess the the distinction that I see in these models is you're not just predicting video or worlds, you're also prediction action states, right? So one is what is happening in the world? What is the state? but also what is the next action to predict. So it's like sort of two outputs, right? So
</details>

>> 是否有一个你们作为目标的行业标准帧率？
<details><summary>Original English</summary>
>> is there a target frame rate uh that you target that is industry standard
</details>

>> 因为你不必预测那么远。这是我的构想，我的想法。
<details><summary>Original English</summary>
>> because you don't have to predict out that far. It's my plan. It's my idea.
</details>

>> 你是指实时因子方面的表现吗？比如目前模型运行的大概是 10 FPS，我认为相当小……
<details><summary>Original English</summary>
>> You mean in terms of the real time factor like how how it's like 10 FPS I think um what the model currently runs pretty small
</details>

>> 而且你外推的大概是 1 FPS 还是 5 帧……抱歉，是 1 帧还是 5 帧之类？
<details><summary>Original English</summary>
>> and you're projecting out like one FPS or five F sorry one frame five frames whatever.
</details>

>> 我得去查一下。我想是一小块帧序列，我估计大约在 9 到 21 帧之间，然后它再进行预测，接着模型再次以先前的生成结果以及机器人在运行时摄像头实际感知到的内容为条件，然后基本上进一步往后预测。所以它是分块进行的，基本上可以说在时间上并不是自回归式运行的，而是一种分块预测。我真正想探究的是，视频预测这一侧在很大程度上是为了预测你所做操作的结果。但这样一来，模型外部可能需要某种长程规划器来协调动作……
<details><summary>Original English</summary>
>> I would have to look it up. I think it's it's a small chunk of of frames. I would say like in between 9 and 21 frames that it then predicts again and then the model is conditioned on the previous uh generations again and what the camera when it runs on the robot what the camera actually perceives right and then you basically predict this uh further. So it's it's it's a bit of a chunk. It's not uh running autogressively so to say in in in time basically but it's a chunk prediction. What I'm driving at is like this video prediction side that is very much for predicting the results of what you do. But so probably you need some kind of long range planner existing outside of that model that will coordinate the actions that
</details>

>> 我是说，这就是我们之前讨论语言侧的原因。
<details><summary>Original English</summary>
>> I mean this is this is why we're discussing the language side earlier.
</details>

>> 是的，没错。就目前的运行情况而言，我们看到并没有涉及高级规划器之类的东西。这只是一个在一个循环中运行的模型。
<details><summary>Original English</summary>
>> Yeah. Yeah. So as it runs right now what we see is that there's no plan like like high level planner involved or something. This is just a model running on a on a on a loop.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 一些有趣的……
<details><summary>Original English</summary>
>> Some of the interesting
</details>

>> 我们与 Dina Robotics 合作做的那些。
<details><summary>Original English</summary>
>> what we did with Dina Robotics.
</details>

### 微调与情境学习：通向超人视觉智能

>> 是的。Dina 有一个，Runway 也有一个。聊聊微调这一侧吧。如果我想采用你们的通用模型，针对一台执行新任务的新机器人进行微调——不是什么超级疯狂的任务，但属于分布之外的、它没见过的东西，比如我自己的家用机器人，我可以编程教它如何使用人形机械臂等等。那个流程是怎样的？需要多长时间？它在可微调性方面有多重要？另外同样地，由于这个模型非常通用，而且预训练非常理想，相比之下它花费的时间……基本上你需要若干个小时。我想我们展示过一个例子，将其与同样开源的 Power 5 进行了对比，对吧，训练它所需要的数据量减少了 8 倍。那是针对工业应用的，我们基本上只需要大约 4 小时的数据，就能达到足以满足该基础应用的成功率。
<details><summary>Original English</summary>
>> Yeah. Um, Dina has one, uh, Runway has one. I guess talk about the fine-tuning side. So, if I want to take your general model, fine-tune it for a new robot with a new task, not something super crazy, but you know, something that's out of distribution, it hasn't seen, say it's my own home robotics, I can program in how to use a humanoid arm or whatever. Uh, what is that process like? How long does it take? How important is that in fine-tunability? Also again like since this model is so general and then the pre-training was so nice um it it takes like compared basically you need a bunch of hours I think we showed one example um where we compared it with um I think it was power 5 which was also open source right it took eight times less data to basically train on it that was for industry application it was like 4 hours of data that we that we needed basically to get to a success rate that was like good enough for this basic application
</details>

>> 这是你们现在想要不断爬山攻坚的方向，还是说……
<details><summary>Original English</summary>
>> and is that a thing you kind of want to hell climb on right now or is that like
</details>

>> 我们回到上下文这个思路……
<details><summary>Original English</summary>
>> we go back to the context thought
</details>

>> 我们不应该去做微调……
<details><summary>Original English</summary>
>> we shouldn't be doing fine tuning
</details>

>> 我们的目标以及目前正在极其……
<details><summary>Original English</summary>
>> what we what we're targeting and what Bill we're working on right now extremely
</details>

>> 审慎且高度聚焦投入的，是机器人领域的上下文学习（in-context learning）。这意味着你应该只需要向机器人示范一次动作，然后它就应该能够执行，而这才是真正的超人级智能。就像你看看我们小时候学习走路，学习正确使用大拇指去抓取这个 cam，对吧？我们要做成这件事需要数周甚至数月的学习。我们的愿景是，自主机器人应该能够观察任何动作一次，然后就能够执行它。
<details><summary>Original English</summary>
>> carefully and with a lot of focus in context learning for robotics this is you should be showing a robot in action one time and then it should be able to do this and this would be truly a superhuman intelligence like if you if you look at how long it takes us as children to learn walking to learn using our thumb correctly to grab this cam for instance, right? This is like weeks and even months of of learning that it takes us to do this. Our vision is that robotic like an autonomous robot should be able to observe any action once and then be able to do it.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 那才是一种明确具有超人水准的视觉智能，也是我们想要达到的目标。
<details><summary>Original English</summary>
>> That is what would be a clearly superhuman kind of visual intelligence and that is what we want to be reaching.
</details>

>> 现在的行业标准是怎样的？比如我们需要多少次演示？
<details><summary>Original English</summary>
>> What is the standard now? Like how many demonstrations do we need?
</details>

>> 大概至少需要 4 小时的微调数据。
<details><summary>Original English</summary>
>> It's around like 4 hours of fine tuning you need at least.
</details>

>> 但即使是 4 小时也已经相当不错了。我认为 2027 年将会是……
<details><summary>Original English</summary>
>> But even even four hours is pretty good. I I would say 2027 will be the year where we will
</details>

>> 中期训练（mid-training）在这里也是一个有意思的环节，对吧？这是指比如我想从制造业跨入医药领域，比如填充药丸胶囊，具体针对不同的细分领域，是应用在这个阶段吗？
<details><summary>Original English</summary>
>> mid training is an interesting one in here too, right? So is this like I want to go from manufacturing to maybe maybe medical stuff like filling pill capsules like specifically like different niches for example is that where
</details>

>> 我的意思是，这个模型的训练是非常通用的。因此，即使是中期训练阶段——也就是在微调之前——它可能就已经能够处理扔给它的很多任务了，甚至当前这个版本可能就能处理很多你交给它的任务。微调实际上只是为了彻底敲定细节，你知道，在机器人领域，你希望达到你所预期的某种精度水平。
<details><summary>Original English</summary>
>> I mean the model the model is trained quite generally. So even even the midra like before fine-tuning it might be able to handle many of the like even this version might be able to handle many of the tasks you throw at it. The fining is really just nailing, you know, in the robotics world, you want to you want to act you want a certain level of accuracy you expect out of it.
</details>

>> 没错。这只是标准、常规的大规模中期训练，然后我们再进入这个微调阶段。
<details><summary>Original English</summary>
>> Exactly. This is just a standard plain large scale mid training and then we move on to this finetuning stage
</details>

<!-- chunk 13/14 -->

在这一步，我们加入了高质量的机器人数据——

<details><summary>Original English</summary>
where we add the high quality robotics data in
</details>

>> 然后我们就得到了这进一步的提升。但你可以看到，其实在训练中期，模型就已经在相当好的程度上能够完成这些任务了。

<details><summary>Original English</summary>
>> and then we get this this this further bump. But you see that already to to a to a somewhat good extent um on mid-raining the model can actually do these tasks.
</details>

>> 我想另一个有意思的点是，它是一个 7B 模型对吧？这主要是受限于这些模型部署的场景吗？

<details><summary>Original English</summary>
>> I guess the other interesting thing is it's a 7B right? Is that mostly just constraint from these things are deployed?
</details>

>> 没错。你希望拥有一个尽可能小的模型，因为如果你想把它加到制造业中，基本上你首先需要它能够在端侧运行，而且还要是实时的。

<details><summary>Original English</summary>
>> Exactly. You want to be having you want to be having a model that is as small as possible because you need to be
able to act first on device if you want to be adding this to a manufacturing basically and then also in real time
</details>

>> 而这是以 Flux 3 为主干网的？

<details><summary>Original English</summary>
>> and this is on the backbone of Flux 3.
</details>

>> 是的，嗯。

<details><summary>Original English</summary>
>> Yes. Mhm.
</details>

>> 那么像图像和音频这类所有的东西——

<details><summary>Original English</summary>
>> And do we so is like the image and audio all that stuff
</details>

>> 全都是，基本上全都是从这一个模型衍生出来的。我们拥有这个多模态模型——

<details><summary>Original English</summary>
>> all like this is this is derived from this one model basically we have this multimodal model
</details>

### 通用基础模型与衍生应用

>> 理解这一点非常重要：它是在庞大的图像、音频语料库上训练出来的。在此基础上，我们可以衍生出我们基本上在这个夏天发布的所有东西，包括 flux video、flux video edit、flux action、flux image、flux image client。我们还从中衍生出了一个放大器（upscaler），我们有一个非常棒的 4K 视频放大器，我觉得它超快，而且只能用极力推荐来形容，真的非常好。这一切都是由这一个模型驱动的。这展示了训练这类高度通用模型的过程随着时间的推移是如何产生复利效应的，因为你可以从中衍生出所有这些应用，对吧。

<details><summary>Original English</summary>
>> that that is really important to understand this has been trained on a huge corpus of images audio and from that we can derive everything that we basically released this summer which was flux video flux video edit flux action flux image flux image client we also derived an upscaler from it we have a super nice 4K uh video upscaler which is I think super fast also can only recommend it's really good and this is all powered by this one model and this this shows how training these very general models actually compounds then over time because you can derive all these applications from them right
</details>

>> 视频放大器和图像放大器之间有区别吗？难道不是——

<details><summary>Original English</summary>
>> is there a difference between a video upscaler and an image upscaler isn't
</details>

>> 视频放大器，我们之前谈到了时间一致性。很显然，如果你用一个完全没有时序理解能力的放大器，你就会再次遇到画面闪烁的问题，

<details><summary>Original English</summary>
>> a video upscaler we talked about the temporal consistency obviously if you would have a upscaler that would have like like no temporal understanding then you would have this flickering again this
</details>

>> 尤其是在高频细节上。比如两张图像并排放在一起看时，你可能看不出太大差异；但如果你在两张图像之间来回切换——每个经常看大量图像的人都会做这种基本操作，就是在两个标签页中各打开一张图，然后左右来回切换——他们就能看出哪怕一丝一毫的差异。如果你在视频放大器中没有这种时序组件，这在时间维度上就等同于闪烁。这就是它区别于图像放大器的地方。

<details><summary>Original English</summary>
>> especially in the high frequencies you then real like like you don't see this too much when you comp like look look at two images side by side you don't see that much but if you switch between the images that's that's one of the basic uh tasks that everyone who's looking a lot of images does just opening two images in two tabs and and then switching left right they see every single single difference and that would just amount to kind of flickering in temporal space if you wouldn't have this temporal component in the video upscaler and that's what makes it difference from a image upscaler
</details>

### 机器人评估与 2027 年展望

>> 关于真实机器人的评测以及如何规模化扩展，有什么想说的吗？比如我经常看到什么“把海绵放进碗里三次”之类的评测［笑］。而且在某种程度上，如果你看我们的 Dapod，真的有人在进行单次测试，因为你必须在实际规模下测试。但是拜托，海绵放碗里三次测试成了两次，只要重新开始［哼笑］再做一遍，你就能做到三次全中，对吧？［笑］

<details><summary>Original English</summary>
>> any notes on real robot evals and how to scale this Like I I see, you know, sponge in bowl three times like [laughter] and and at some level like if you look at our Dapod, there are literally people just one off testing robots cuz you have to test in real scale. But like come on, two out of three runs on Sponge and B. Just restart, [snorts] do it again, you can be three out of three, right? Like [laughter]
</details>

>> 这是一个很难的问题。我认为大家一直在努力解决的一件事，就是缩小 Sim-to-Real（仿真到真实）的差距。随着时间的推移，这会变得越来越好。但老实说，无论你在哪里做评估，它都是一件痛苦的事。你看内容生成的评估也同样痛苦，比如你问——

<details><summary>Original English</summary>
>> it's it's a hard problem. I think one one one uh thing that's constantly being worked on is just closing the SIM trial gap. And this will get better and better and better over time. But to be honest, evas no matter where you do it, it's a painful thing. It's also painful when you when you look at the content creation evas like ask
</details>

>> 问三个不同群体的评判者什么是一张好图片，你就会得到三种完全不同的答案。

<details><summary>Original English</summary>
>> three different groups of voters what a good image looks like and you would get you we you will get three different answers.
</details>

>> 还会为此爆发口水战。

<details><summary>Original English</summary>
>> You have wars over it.
</details>

>> 我们确实会为此争论不休［笑］。

<details><summary>Original English</summary>
>> We have wars over this [laughter]
</details>

>> 但这就是生成式建模的现状，评估本身就是非常困难的。

<details><summary>Original English</summary>
>> but that's evas are just for generative modeling. Evals are just hard.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这在商业层面已经发展到什么程度了？

<details><summary>Original English</summary>
>> Is this already like how developed is the commercial site?
</details>

>> 我们会有——

<details><summary>Original English</summary>
>> We will have
</details>

>> 更多进展。［笑］我不能透露太多，但很快就会有由 DFL 驱动的机器人投入生产实机运行，并且——

<details><summary>Original English</summary>
>> more. [laughter] I cannot tell too much but there will be soon for DFL powered robots in productions live and
</details>

>> 2027 年将成为机器人之年。

<details><summary>Original English</summary>
>> 2027 will be the year of robotics.
</details>

>> 噢，绝对是。

<details><summary>Original English</summary>
>> Oh absolutely.
</details>

>> 好，关于预测多说几句吧。到 2027 年我们会走向何方？发展的提速会有多快？

<details><summary>Original English</summary>
>> Okay. Say more on predictions. Where where do we go from this in 2027? How how fast do things pick up?
</details>

>> 强化学习（RL in learning）是一个非常大的方向。我们首先会看到这些技术在真实制造工厂中的首批商业应用。这也是为什么我们拥有德国基地是一件好事，因为那里有大量的工业数据，

<details><summary>Original English</summary>
>> Sing yeah in learning is a big is a big thing. We'll see first we'll see first commercial applications of these things in real manufacturies. That's that's why it's actually good that we have this German base because there's a ton of uh industry data
</details>

>> 而且显然有巨大的合作潜力。我也想说，大家对机器人技术非常饥渴。

<details><summary>Original English</summary>
>> and um obviously lots of potential for partnerships. People are really hungry for robotics, I would also say.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 所以这里面有一整套我们希望利用的协同效应，真正把 2027 年打造成机器人之年。

<details><summary>Original English</summary>
>> So there's a there's a good bunch of um of synergies that we want to be using to actually make 2027 the year of robotics.
</details>

>> 我对相关研究非常兴奋，这方面的研究进展也极其迅速。因此我推测机器人技术会提升得非常快。

<details><summary>Original English</summary>
>> I I'm very excited about the research the research on this is also moving very quickly. So I I suspect that robotics will improve very quickly.
</details>

>> 是的。但是机器人涉及很多物理制造层面的限制，这方面又如何呢？你可以扩大技术规模，可以扩大模型规模，但物理限制很难改变，对吧？所以在预测上，到 2027 年，现实中我们在机器人领域会走到哪一步？我能买到某种开箱即用、能够单次示范学习的东西吗，比如——

<details><summary>Original English</summary>
>> Yeah. What about the side of like robotics is very physical manufacturing constraints like you can scale up tech you can scale up models but that's it's pretty hard to affect right so predictions 2027 where where where are we realistically on robotics can I buy something off the shelf that can single shot learn like
</details>

>> 我推测到了 2027 年晚些时候，人们将能够在自己家里用上一些相当有趣的机器人。我是指，不管它是——能不能做精细动作任务等等这些，我不知道，但我推测……再次声明，这完全只是预测。我对此没有任何事实依据，但我推测明年可能会出现一些有趣的设备，至少面向像我们这样懂技术的人群是一个利基市场；并不是说普通大众都会去买，但在你家里可能会有一些有趣的、具有潜在实用价值的机器人。

<details><summary>Original English</summary>
>> I suspect like later 2027 like people will be able to get some some quite interesting robotics in their house I mean I whether it's you know is it going to be able to do like fine motor tasks and all this I I don't know but I suspect like and again this is just entirely predictive. I I have no baseline for this, but I I I suspect next year there might be some some interesting like you know at least niche for like the the tech side of people like us, not like you know uh the average person would be picking this up but some interesting potentially useful robotics in your house
</details>

>> 而在制造业方面，我认为 2027 年会是一个爆发之年，因为相比之下制造业受限更多，对吧？它不像自动驾驶之类的那样具有长尾效应，对吧？也不像——

<details><summary>Original English</summary>
>> and for manufacturing I think 2027 will be a year because manufacturing is like more restricted right than than kind of it it isn't that long tail as like say autonomous driving and stuff like that right or or like
</details>

>> 消费级机器人，理想状态下你希望它做任何你想做的事情。但对于制造业，我认为很有可能会看到大量实际应用在 2027 年被机器人技术解锁，所以——

<details><summary>Original English</summary>
>> consumer robotics where you can just like do you would ideally like to do this thing to do anything you want but for manufacturing I think there's a very good chance that we will see like a lot of applications actually being unlocked by robotics in 2020 so
</details>

>> 这基本上也是我们正在为之努力的方向。

<details><summary>Original English</summary>
>> and that's what we are also working towards basically
</details>

>> 确实非常如此。

<details><summary>Original English</summary>
>> very much so
</details>

### 团队背景与大众对 AI 的认知

>> 太棒了。我是说这让人很兴奋，你们那里看起来是个非常有意思的地方，有机器人实验室、视频模型——

<details><summary>Original English</summary>
>> awesome I mean exciting it seems like very fun place you guys have robot labs video models
</details>

>> 研发大楼，你们就差一辆会飞的车了。

<details><summary>Original English</summary>
>> building you're just missing the flying car
</details>

>> 你多次提到了德国，但你们在旧金山也有相当大的办公室。我之前其实都不知道欧洲那边有这么大的规模，而在旧金山有一家名叫 Black Forest 的公司，拥有举足轻重的存在感。

<details><summary>Original English</summary>
>> you mentioned Germany a lot but you also have a pretty big SF office I actually didn't know there was a big European side there's a substantial SF presence called Black Forest.
</details>

>> 借此机会也邀请大家来我们这里做客，呃——

<details><summary>Original English</summary>
>> And this like inviting everyone to come over to our place uh
</details>

>> 汤森街（Townsend Street）410 号。非常非常棒的地方。我们不是一家单纯的欧洲公司，我们是一家在欧洲和美国都有根基的公司，而且我们基本上是在全球开展业务。

<details><summary>Original English</summary>
>> 410 Townson Street. Uh super super nice and we we we're not a European company, not like we company with roots both in Europe and the US and we were acting globally basically.
</details>

>> 很有意思。我们请你上节目也是因为你正好来城里访问，我们就觉得：“好，我一定要请到他。”

<details><summary>Original English</summary>
>> It's fun. We got you on because you're visiting in town and we're like, "Okay, I should have."
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 大家怎么能帮到你们？招聘吗？

<details><summary>Original English</summary>
>> How can people help you hiring?
</details>

>> 对，我们在招人——

<details><summary>Original English</summary>
>> Yeah. looking for
</details>

>> 我觉得只要在市场宣发上支持我们，多谈谈我们的模型，在美国这边也帮我们打开知名度就行。在技术社区里我们已经很有名了，

<details><summary>Original English</summary>
>> I think just just uh supporting us in marketing talking about our models um helping us also here I think in the US getting getting our name out out in the community we're well known
</details>

>> 但我觉得在更广泛的大众社会中还没有那么知名。那里有一些大玩家，对吧？这也是我们在 2027 年需要改变的地方，真正把我们的名声打出去，因为我们拥有极其强大的技术。我认为这正是大家所看到的，我们长期以来构建了几乎所有人都在使用的核心支柱技术。基本上，现在也是时候把我们的品牌推向更广泛的受众了。

<details><summary>Original English</summary>
>> I think for for like like in the broader society not that much there's a big players right that's also what we need to change in 2027 really kind of getting our name out because we have extremely strong technology I think that that that's what we saw we have a long history of having built like the core pillars of like what everyone is using basically it's now also time to get our name out um to the kind of broader audience.
</details>

>> 是的，但在科技界我认为我们非常知名，不过——

<details><summary>Original English</summary>
>> Yeah, but the the tech community I think we're well known but
</details>

>> 除此之外——

<details><summary>Original English</summary>
>> apart from that
</details>

>> 告诉你妈妈关于 FLUX 的事。这非常有趣，整个生成式领域——显然我是一个做市场营销的人，经常帮助公司做营销。你们非常不一样，因为总体而言生成式媒体在大众心目中的名声非常复杂微妙，对吧？通常我会建议：在 TikTok 或 Instagram 上做个营销活动吧，但你很可能会被喷得体无完肤，仅仅因为他们太讨厌 AI 了，

<details><summary>Original English</summary>
>> tell your mom about flex. So, it's it's very interesting that the overall gen obviously I'm a marketing guy and I help companies in marketing all the time. You guys are very different cuz generative media in general has a weird mixed reputation in the broader population, right? Like normally I would suggest oh have a Tik Tok or Instagram marketing campaign but pretty much you'll be killed in just because they hate AI so much,
</details>

>> 对吧？所以找到那些不被视作“AI”、只被当作“用科技能做到的普通事情”的细分领域就非常有意思。嗯。

<details><summary>Original English</summary>
>> right? And so it's very interesting to find a niches where this is isn't regarded as AI. It's just normal a thing you can do with tech. Mhm.
</details>

>> 但它不是 AI，因为我认为你一旦说是 AI，大众就会立刻——

<details><summary>Original English</summary>
>> But it's not AI because I think the moment you say it's AI, the population will just
</details>

>> 举起草叉反抗。

<details><summary>Original English</summary>
>> have pitchforks.
</details>

>> 我不知道你对此有没有什么回应、想法或者探索。

<details><summary>Original English</summary>
>> I don't know if you have any response or thoughts or explorations about that.
</details>

>> 我觉得很重要的一点是，始终要强调我们是以负责任的态度来做这件事的。我们的模型不会去制造铺天盖地的垃圾内容之类的，对吧？它们真正落地在实际用例中，融入很多专业的日常工作流，只是在帮助专业人士改善工作生活——

<details><summary>Original English</summary>
>> I think it's important to to just always also emphasize that we we we take this responsibly. We're like like not our models are not creating like avalanches of slop or something, right? They they actually live in real use cases. uh lots of like professional workflows and they just help making the lives of like professional
</details>

<!-- chunk 14/14 -->

### 病毒式传播与图像修复用例

让从事这项工作的人轻松得多，并且极大地提高生产力。
<details><summary>Original English</summary>
people who work with this way easier and just increasing productivity so much.
</details>

>> 这就像是 Photoshop。
<details><summary>Original English</summary>
>> It's Photoshop.
</details>

>> 没错。这真的很不可思议，到那时你的工作效率会提高那么多。在内容方面，这确实就是类似的目标。这根本不是为了让人们失业，完全不是。它只是为了让每个人的生活都轻松得多。
<details><summary>Original English</summary>
>> Exactly. It's so crazy like how how much more productive you are then. And that that's really the the kind of the goal of this on the content side. It's not about putting people out of work. Not at all. It's just like making everyone's life so much easier.
</details>

>> 是的。我不是那个意思。我只是觉得，如果我在你们团队工作，这就是我目前的 GTM（走向市场）难题，也就是我们如何让人们在基本上……你知道，像 Whisper Flow 那样掀起一波小小的病毒式传播，因为大家会觉得“哦，对，我知道怎么用这个，这不是 AI，它只是 Whisper Flow”，或者是 Granola，同样的事。我认为生成式媒体还没有经历过那种跨越，除了 Nano Banana，以及无论何时 ChatGPT 迎来其——
<details><summary>Original English</summary>
>> Yeah. I wouldn't say that. I'm just like if I worked on your team like this is the the my GTM problem right now which is like how do how do we get people to basically you know go viral in the same way that maybe whisper flow goes a little bit viral cuz they're like oh yeah I understand how to use this is not AI it's just whisper flow is granola same thing I think that that there the generous media hasn't had that crossover except for Nano Banana and then whenever Chachi PT had the
</details>

>> 吉卜力工作室时刻，对。
<details><summary>Original English</summary>
>> studio Gibli moment yeah
</details>

>> 那样的时刻。那种跨越就是大家会觉得“哦，这是一个我想要参与进去的有趣潮流”。
<details><summary>Original English</summary>
>> those kinds of Like that is the crossover where it's like oh like this is a fun trend that I want to hop on.
</details>

>> 之前也有过反响很好的时刻，比如你提到的“看看变老后的自己”，那引发了巨大的轰动。人们会——
<details><summary>Original English</summary>
>> There were moments that hit well like your point of the see yourself as you're older like that had a huge moment. People would
</details>

>> 看着自己 80 岁时的样子，发给家人。确实有过这样的时刻，但没有什么特别……
<details><summary>Original English</summary>
>> look at themselves as their 80s send it to their family. Like there have been moments but nothing is super
</details>

>> 我觉得其中一个难点在于，其实很难预测这类病毒式传播的时刻。比如我……Nano Banana 是他们内部的名字，后来他们就直接沿用了，因为大家就是喜欢这个名字，它就传开了。补充一下背景，实际上，我们看到使用量极大的一个主要用例，也是我们不一定料想到的，就是图像修复。
<details><summary>Original English</summary>
>> I I think one of the difficult pieces is it's actually very hard to predict one of these like viral moments. Like I like Nano Manana was the like their internal name and then they just kept it because it it like people just like the name and it stuck. for context. Actually, the one big use case that we saw a ton of usage on that like, you know, we didn't necessarily expect was image restoration as well.
</details>

>> 是的，有大量的……我看到了许多非常棒的例子，人们拿着老旧受损的家庭照片，然后进行修复，
<details><summary>Original English</summary>
>> So, there was a ton of like I saw amazing amazing examples of people, you know, taking old degraded family photos and then restoring them,
</details>

>> 给照片上色、修补好，而且它能够与原照保持非常非常高的相似度。我觉得那其实是我们经历过的我最喜欢的时刻之一，大家向家人展示这些修复后的照片，以及由此引发的反应。我真的非常享受它所带来的那一积极时刻。但就像我说的，我们往往无法预测下一个爆点会是什么。即使在过去，即使回溯到 Stable Diffusion 时代，它也——
<details><summary>Original English</summary>
>> colorizing them, fixing them up, but but and it was able to keep like a very very high level of uh of similarity to the to what the original would have been. And then I don't know that that was actually one of my favorite moments that we've had of people showing like their family these kind of restored photos and the reactions from it. And I I really really enjoyed that like positive moment that that it brought. But like I said like we so often we can't predict like what the thing is going to be you know it's it's even with uh even with our old you know even back in the stable diffusion days it was
</details>

>> 网上流行的趋势总是令人出乎意料，它们就这样自然而然地冒出来了。你无法去规划它们。我认为一旦这些趋势出现，显然你就需要去充分利用它们，而且你应当始终在问——
<details><summary>Original English</summary>
>> always surprising what the trend was you know online like it just kind of they just kind of emerge they emerge. kind of plan them. I think once you have them, you need to to kind of exploit them obviously and you should be always asking
</details>

>> 下一个大事件是什么？下一个模型尚未具备的——
<details><summary>Original English</summary>
>> what is the next big thing, the next capability that it has not been
</details>

>> 具备的能力，或者说模型一直无法做到的事情是什么？那会是什么？然后尝试将其融入你的模型中，去下注。其中一些会奏效，另一些则不会。但始终保持这种心态是极其重要的：“嘿，我们接下来应该研发什么，能给人们带来大量的快乐或生产力的提升？”对吧。
<details><summary>Original English</summary>
>> able or like like that models have not been able to do. What would that be? And then trying to to bake this into your model, making bets. Some some of them will work, some others will not work. But this is just extremely important to to kind of always have this mindset of hey what what is the next thing we should be working on that will just bring a lot of joy or like productivity increases to people right
</details>

### 结语与未来展望

>> 这正是研究的领域所在，你们做得很棒。非常感谢你们分享自己的故事。我希望更多的人能了解你们这个团队，因为大家已经看到了很多关于模型的讨论，但我觉得这也是我第一次看到、听到关于——
<details><summary>Original English</summary>
>> well that is the domain of research you guys are doing amazing job so thank you for sharing your story uh I hope more people come to know you as a team because they they've seen a lot a lot of the model buzz but uh I I feel like this is also the first time I've seen I've heard the full story of
</details>

>> 是的，谢谢。非常感谢邀请我们。
<details><summary>Original English</summary>
>> yeah thank Thank you. Thank you so much for having us.
</details>

>> 非常感谢。终于能做这次访谈真的很开心。
<details><summary>Original English</summary>
>> Thank you so much. I mean, this is a It's fun to finally have gotten to do this.
</details>

>> 是啊，筹备了一年时间。另外，我也买了一批 Micro Duck，我很期待看着它们到处跑。
<details><summary>Original English</summary>
>> Yeah. Yeah. I mean, it's a year in the making, but also, you know, I bought a bunch of uh micro ducks and I, you know, I'm looking forward to them running around.
</details>

>> 你有吗？我想弄一个。我感觉我错过了能买到它们的窗口期。你有门路吗？
<details><summary>Original English</summary>
>> Do Do you have like I I want to get my hands on. I feel like I missed the window of these being available. You have connections.
</details>

>> 我肯定能……我肯定……[笑] 外面不管谁能帮我弄到一只 Micro Duck，给我一只 Micro Duck 吧。
<details><summary>Original English</summary>
>> I'm I'm sure I'm sure I [laughter] Whoever out there can get me a micro duck. Give me a micro duck.
</details>

>> 我给你弄一只。
<details><summary>Original English</summary>
>> I'll get you duck.
</details>

>> 好的，太完美了。
<details><summary>Original English</summary>
>> Okay, perfect.
</details>

>> 我买了一批，因为我知道这会成为圣诞节的热门礼物。
<details><summary>Original English</summary>
>> I bought a bunch cuz I know this going to be a hot gift for Christmas.
</details>

>> 是啊，是啊，是啊。感觉……
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. Yeah. feel like uh
</details>

>> 不过，是的，2027 年的机器人技术，那也就一年左右的时间了。我们拭目以待，看看这一切会走向何方，但我对这种方法非常乐观，我认为你们解释得非常透彻。
<details><summary>Original English</summary>
>> but but yeah you know robotics 2027 that's you know one year away like you know we we'll see we'll see where this all learns but I'm very optimistic about this approach and I think you guys have explained it very well.
</details>

>> 太棒了。是的。太精彩了，太好了。谢谢你。太酷了，谢谢。好的，谢谢你们。[音乐]
<details><summary>Original English</summary>
>> Fantastic. Yeah. Amazing. Awesome. Thank you. Cool. Thanks. All right. Thank you. [music]
</details>