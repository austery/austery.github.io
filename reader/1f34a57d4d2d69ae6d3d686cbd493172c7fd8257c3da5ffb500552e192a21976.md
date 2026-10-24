---
author: Dwarkesh Patel
date: '2024-11-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5fkqmNzFni8
speaker: Dwarkesh Patel
tags:
  - scaling-hypothesis
  - deep-learning
  - computational-power
  - neural-networks
  - agi-prediction
title: AI 扩展假说的形成：一位观察者的历史视角
summary: 本转录记录了一位个体在观察人工智能（AI）扩展演变过程中的智识历程。最初，他怀疑仅凭巨大计算力就能催生高级AI的“联结主义”论点，但通过细致追踪深度学习、模型规模和计算资源的趋势，他逐渐转变了观点。GPT-1、GPT-2，尤其是GPT-3强大的少样本学习能力，验证了“扩展假说”对观察者而言的有效性，让他认识到AI的进步主要源于规模而非单纯的算法突破。他将自己的观察方法与他人的即时反应进行对比，强调了持续的趋势分析塑造了他的个人智识历史。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - GPT-1
  - GPT-2
  - GPT-3
media_books: []
status: evergreen
---
### AI 扩展假说的形成：一位观察者的历史视角

**Speaker**: 中文翻译内容...

<details>
<summary>Original English</summary>

**Speaker**: You're one of the only people outside of OpenAI who in 2020 had this detailed empirical model of scaling. And I'm curious what processes you were using at the time which allowed you to see the picture that you painted in the scaling hypothesis post that you wrote at the time.

</details>

**Speaker**: 所以，我想如果我要给这段历史一个智识史的叙述，对我而言，它可能始于 2000 年代中期，那时我读了更多关于 Ray Kurzweil 的文章。当时，他们提出了这种根本性的联结主义（connectionist）论点，即如果你拥有足够的计算能力，就能够发现匹配人脑的神经网络架构。而在此之前，在有如此大量的计算能力可用之前，人工智能似乎基本是徒劳的。对我来说，我认为这个论点非常不可靠，因为它非常像是“建好它，它们就会出现”（build it and they will come）的进步观，我就是不认为它是正确的。我认为，仅仅因为你拥有了一个像非常巨大的超级计算机，它能匹配人脑，然后就能凭空召唤出正确的算法，这是多么荒谬的说法。算法非常复杂，它们很难，需要深刻的洞察力，或者至少我当时是这么认为的。而且这看起来是极其困难的数学问题，你不能仅仅购买一堆计算机，然后期望从中获得高级人工智能。这看起来完全是异想天开。所以我知道这个论点，但我非常怀疑，也没有太在意。但是，Shane Legg 和其他人在这方面非常积极，在接下来的几年里。作为我对超人类主义（transhumanism）、LessWrong 和 AI 风险的兴趣的一部分，我特别密切关注 Legg 的博客文章，他通过 Kurile 和 Morac 的更新数据来推断这种趋势，并给出这些非常精确的预测，比如我们将在 2019 年左右迎来第一个通用系统，随着摩尔定律的持续。然后到 2025 年，将会有具备通用能力的类人智能体。而到 2030 年，他预测我们应该拥有 AGI（通用人工智能）。

<details>
<summary>Original English</summary>

**Speaker**: So I think if I had to give an intellectual history of that, for me, I think it would probably start in the mid-2000s when I was reading more of Ray Kurzweil. Um, at the time, they were making this kind of fundamental connectionist argument that if you had enough computing power, um, that that could result in discovering the neural network architecture that matches the human brain. And until that happens, until that, that amount of computing power is available, AI just seemed basically futile. And to me, I think I found this argument very unlikely, um, because it's very much a kind of "build it and they will come" view of progress, which I just didn't think was correct. Um, I thought that it just seemed ludicrous to suggest that, you know, just because you'd have some like really big supercomputer out there, um, which matches the human brain, then that would kind of just summon out of non-existence the correct algorithm. Algorithms are really complex, they're hard. Um, they required deep insight, or at least I thought they did. Um, and it seemed like really difficult mathematics. You can't just like buy a bunch of computers and then expect to get this advanced AI out of it. Um, it just seemed like totally magical thinking. So I knew the argument, um, but I was super skeptical and I didn't pay too much attention. Um, but then Shane Legg and some others were very big on this, um, in the years following. And as part of my interest in transhumanism and LessWrong and AI risk, I was paying close attention to Legg's blog posts in particular, um, where he's extrapolating, kind of, out the trend with updated numbers from Kurile and Morac. And he's giving these kind of very precise predictions about how, you know, we're going to get the first generalist, uh, system around 2019, as Moore's Law keeps going. And then by 2025, would have kind of humanish Agents with generalist capabilities. And that by 2030, he said we should have AGI.

</details>

**Speaker**: 然后 Dan Neff 和 Alex Neff 出现了。当它们出来时，我心想，哇，这似乎是联结主义（connectionism）观点的非常令人印象深刻的成功案例。但是，这只是一个孤立的成功案例，还是，你知道，这就是 Kurile、Morac 和 Shane Legg 一直在预测的，即我们会获得 GPUs，然后更好的算法就会自行出现？所以我开始对自己说，你知道，这是值得关注的趋势。也许它不像我最初想的那么愚蠢。我继续阅读深度学习（deep learning）的文献，一次又一次地注意到数据集的大小不断增大，模型似乎在不断变大。GPUs 性能缓慢提升，从一个 GPU，你知道，最便宜的消费级 GPUs 到两个，然后最终是八个。你可以清楚地看到，神经网络（neural network）一直在扩展，从这些极其小众的个人用例，几乎一无所获。这种（能力）范围不断变得越来越广，越来越广。我对我说，哇，难道就没有什么事情是 CNN 做不到的吗？我每天在 arXiv 上看到人们将 CNN 应用于其他事物。这种渐进的、涓滴式的进展一直在我的生活中不经意间发生着。你知道，每隔几天，就会有新的进展出现，我就会想，嗯，也许智能（intelligence）确实就是大量的计算（compute）应用于大量的数据（data），应用于大量的参数（parameters）。也许 Morac、Legg 和 Kur 是对的。我只是注意到这一点，然后继续想，嗯，如果这是真的，那将会有很多影响。所以我想，那里并没有一个真正的“尤里卡”时刻。只是持续地观察着这个趋势，而其他人似乎都看不到，除了少数几个人，比如 Ilya Sutskever、Schmidhuber。我只是关注着，并注意到随着时间的推移，世界越来越像他们的世界，而不是我的世界，在我的世界里，算法非常重要，你需要深刻的洞察力才能做事情，你知道。他们的世界一直在发生着。

<details>
<summary>Original English</summary>

**Speaker**: And then Dan Neff and Alex Neff came out. And when those came out, I was like, wow, um, this seems like a very impressive success story for the connectionism view. Um, but is it just an isolated success story, or, you know, is this what Kurile and Morac and Shane Legg had been predicting, that we would get GPUs and then get better algorithms would just kind of show up? Um, so I started thinking to myself that, you know, this is something, it's a trend to keep an eye on. Um, and maybe it's not quite as stupid as an idea, um, as I originally thought. And I just keep reading deep learning literature, notice again and again that the data set size just kept getting bigger, the models seem to keep getting bigger. The GPUs slowly CPT up from one GPU, you know, the cheapest consumer GPUs to two, and then eventually they were trading on eight. And you can just see the fact that the neural network just kept expanding from these incredibly niche individual use cases, which you next to nothing. Um, the youth just kept getting broader and broader and broader. I'd say to myself, wow, is there anything that CNN's can't do? As I just see people applying CNN to something else, you know, every individual day on arXiv. This gradual trickle of drops kind of just kept hitting me in the background as I was going on, um, with my life. You know, every few days, like another one would drop and I'd go like, huh. Um, you know, maybe intelligence really is just like a lot of compute applied to a lot of data, applied to a lot of parameters. Um, maybe Morac and Legg and Kur were right. And I just note that and kind of continue on thinking to myself like, huh, if that was true, it would have a lot of implications. So I think there wasn't really like a Eureka moment there. It was just continuously watching this trend that no one else seemed to see, except possibly a handful of people like Ilya Sutskever, um, Schmidhuber. Um, and I would just pay attention and notice that the world over time looked more like their world than it looked like my world, um, where algorithms are super important and you need like deep insight to do stuff, you know. Um, their world just kept happening.

</details>

**Speaker**: 然后 GPT-1 出现了。我心想，哇，这个无监督的**情感神经元**（unsupervised sentiment neuron）竟然能自己学习，对吧？这看起来非常惊人。它也代表了一种非常以计算为中心（compute-centric）的观点：你只需要构建 Transformer 模型，智能就会随之而来。然后 GPT-2 出现了，我经历了一个“顿悟”的时刻。看看它的提示（prompting）和总结（summarization）能力，我心想，天哪，我们真的活在他们的世界里了。然后 GPT-3 出现了，那确实是关键的考验。它是一个巨大、巨大的规模升级，是神经网络历史上最大的规模升级之一，从 GPT-2 到 GPT-3。而且它并非只是一个超级狭窄的特定任务。它真的像是关键的考验：如果扩展性是假的，那么 GPT-3 的论文本应完全不令人印象深刻，也不会展现出任何重要的东西。而如果扩展性是真的，那么你就能自动获得比 GPT-2 看到的更令人印象深刻的结果。所以我打开了第一页，也许是第二页，看到了**少样本学习（few-shot learning）**的图表。我心想，天哪，我们真的活在扩展的世界里了。Legg、Morac 和 Kur 是对的。然后我转向 Twitter，其他人都在说：“哦，这表明扩展性效果很差，为什么，它甚至都不是最先进的（state-of-the-art）。” 这让我非常生气。我不得不把所有这些东西都写下来。有人在网上错了。

<details>
<summary>Original English</summary>

**Speaker**: And then GPT-1 came out. And I was like, wow, this unsupervised sentiment neuron is just learning on its own, right? Um, that seemed pretty amazing. Um, it also was a very compute-centric view. You just build the Transformer and the intelligence will come. And then GPT-2 came out. And I had this holy moment. You look at the prompting and the summarization, like, holy, do we live in their world? And then GPT-3 comes out. And that was really the crucial test. It was a huge, huge scale-up, one of the biggest scale-ups in all of neural network history, going from GPT-2 to GPT-3. And it wasn't like it was a super narrow specific task. It really seemed like it was the crucial test. If scaling was bogus, then the GPT-3 paper should have just been totally unimpressive and wouldn't show anything that important. Whereas if scaling were true, you would just automatically be guaranteed to get so much more impressive results out of it than you had seen with GPT-2. So I opened up the first page, maybe the second page, and I saw the few-shot learning chart. And I'm like, holy, we are living in the scaling world. Legg and Morac and Kur were right. Then I turned to Twitter, and everyone else was like, "Oh, you know, this shows that scaling works so badly, why, it's not even state-of-the-art." And that, I was, that made me really angry. I had to write all this stuff up. Um, someone was wrong on the internet.

</details>