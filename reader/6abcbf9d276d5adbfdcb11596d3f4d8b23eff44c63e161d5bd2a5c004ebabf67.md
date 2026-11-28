---
author: TED
date: '2026-11-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=L8HdlknRkA4
speaker: TED
tags:
  - ai-risk
  - neural-networks
  - machine-learning
  - artificial-intelligence
  - data-privacy
title: Jeff Hinton 探讨 AI 风险、神经网络架构与主观体验
summary: Jeff Hinton 讨论了 AI 的生存威胁、短期风险及大规模失业等问题，并回应了 Jensen Huang 对风险预测的批评。他解释了为何其关于放射科医生预测失准的原因，并探讨了神经网络的“黑箱”性质、多模态聊天机器人的主观体验以及基于演化生物学的强化学习模型。此外，他还强调了数据版权保护的重要性，并建议年轻人追随个人热情。
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
Jeff，很高兴能和你同台。你好吗？
<details><summary>Original English</summary>
Jeff, it's such a pleasure to be on stage with you. How are you?
</details>

>> 我很好。也很高兴能和你同台。
<details><summary>Original English</summary>
>> I'm fine. It's a pleasure to be on stage with you too.
</details>

### 人工智能的风险层级与生存威胁

>> 谢谢。众所周知，Jeff 帮助创建了神经网络的架构，这在很大程度上造就了我们所处的当下。他也一直非常有先见之明地就风险发出警告。Jeff，我们何不就从这里开始？对于我们目前在 AI 方面面临的所有风险——你谈论这些已经有一段时间了——你会如何排定它们的优先级？你最担心什么？我们在哪些方面能做的最多？
<details><summary>Original English</summary>
>> Thank you. So, Jeff, as everybody knows, helped create the architecture of neural networks which led very much to the moment we're in. He's been warning quite presciently about the risks. Why don't we start here, Jeff? Of all the risks we face right now with AI, and you've been talking about that for some time, how would you put the hierarchy? What are you most worried about? What can we do the most about?
</details>

>> 我谈论最多的是 AI 取代人类的生存威胁。嗯，我不认为这是唯一的主要风险，不过人们以为我只关注这一点。还有许多短期风险非常严重，比如坏人发动网络攻击、制造生物病毒、用伪造视频破坏选举的风险。还有一些风险，不是人们故意做坏事，而是不良的副作用，比如因为没有足够仔细地检查聊天机器人不会那样做，而导致它鼓励青少年自杀。此外还有大规模失业的风险。我的意思是，我不认为 AI 领袖们有意造成大规模失业。我认为这是他们试图赚大钱的副作用。
<details><summary>Original English</summary>
>> So I've talked the most about the existential threat of AI taking over from people. Um I don't think that's the only major risk, and people think I've just focused on that. There are many shorter-term risks that are very serious, like risk from bad actors doing cyber attacks, creating biological viruses, corrupting elections with fake videos. There's also risks that are sort of not people doing deliberate bad things, but bad side effects, like encouraging teenagers to commit suicide by not checking carefully enough that the chatbot won't do that. But also the risk of massive unemployment. I mean, I don't think the AI leaders intend to cause massive unemployment. I think it's a side effect of them trying to make lots of money.
</details>

>> Jeff，这真是个令人愉快的开场方式。嗯，我想问你关于生存风险的问题，因为这是你相当一段时间前就开始谈论的事情，而现在每个人都在谈论它。Jensen Huang 两周前接受采访时说，谈论人类有 10% 的灭绝风险是不负责任的。他提出了两点批评。第一，我们对这些百分比毫无头绪，我们都只是在猜测。第二——这也是更有趣的一点——这会吓到人们，让他们不敢使用这项技术，从而无法用它来创造美好的事物。你会如何回应 Jensen？
<details><summary>Original English</summary>
>> That was a cheerful way to begin here, Jeff. Um Let me ask you about the existential risk because it was something that you started talking about quite some time ago, and now everybody is talking about it. Jensen Huang gave an interview two weeks ago where he said, uh Jensen, it's irresponsible to talk about a 10% risk of humanity being wiped out. And two critiques. One, we have no idea on the percentages. We're all just guessing. But two, and this was the more interesting one, it's scaring people about the tech and will drive them away from using it to make things that are beautiful. How would you respond to Jensen?
</details>

>> 所以我认为，如果你觉得确实存在一种风险，即如果我们不采取行动，这东西可能会把我们消灭，那么不这么说才是非常不负责任的。我认为说风险为零——我想这就是他说的——才是不负责任的。嗯，他说到 2030 年风险为零。嗯，他还说我所有的预测都错了。我确实做过一个非常出名的错误预测，这一点我承认。我曾说放射科医生到现在就会消失。他们还没有消失，现在还有很多。嗯，我也做过其他一些其实我认为好得多的预测。比如 50 年前，我预测神经网络会取代符号 AI。我还在 2009 年的 NeurIPS 会议上向 1,000 名机器学习研究人员预测，如果他们想做神经网络，就都必须购买 NVIDIA 芯片。而 Jensen 直到 2012 年才做出那个预测。嗯，所以我觉得他说我所有的预测都错了，有点言过其实。
<details><summary>Original English</summary>
>> So I think if you think there's a genuine risk that if we don't do something this stuff might wipe us out, it would be very irresponsible not to say so. I think it's to say the risk is zero, which I think is what he said. Um, he said it was zero by 2030. Um, he also said that all my predictions have been wrong. I've made one very well-known wrong prediction, which I own. I said radiologists would be gone by now. They're not gone yet. There's lots of them. Um, I've made other predictions which actually I think were a bit better. Like 50 years ago, I predicted neural nets would take over from symbolic AI. I also predicted at a NeurIPS NeurIPS conference in 2009 to 1,000 machine learning researchers that if they wanted to do neural nets, they would all have to buy NVIDIA chips. Now, Jensen didn't predict that till 2012. Um, so I think it's a bit much of him saying all my predictions were wrong.
</details>

>> 我知道你确实力排众议，预测了让他得以打造出世界上最有价值公司的那种架构。所以说你所有的预测都错了，确实显得有点不公平。
<details><summary>Original English</summary>
>> I know you did predict against many opponents the architecture that has let him create the most valuable company in the world. So it does seem a little unfair to say that all of your predictions are wrong.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 你为什么会预测错放射科医生的前景呢？
<details><summary>Original English</summary>
>> Why did you get the radiologist prediction wrong?
</details>

>> 有一大堆原因。嗯，首先，那本意不是一个公开预测。我当时在一家为我患癌的妻子治疗的医院做讲座，所以我觉得我必须答应去做这个讲座。我以为那只是面向一小群医生的，我就半开玩笑地随口说了那么一句。结果显然那句话在网上疯传了，这挺不幸的。嗯，不过我预测错有好几个原因。一个原因是，其实计算机视觉的进步没有我预期的那么快。
<details><summary>Original English</summary>
>> There are a whole bunch of reasons. Um, first, I didn't it wasn't meant to be a public prediction. I was giving a lecture at a hospital which was treating my wife who had cancer, so I felt I had to agree to give a lecture. And I thought it was just a small audience of doctors, and I said it kind of off the cuff half as a joke. And then apparently that went viral, so that was unfortunate. Um, but I got it wrong for a number of reasons. One reason, actually computer vision didn't progress quite as fast as I expected.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Yep.
</details>

>> 尽管现在，嗯，对于许多种类的癌症，神经网络已经比优秀的放射科医生更好，或者至少一样好。嗯，这是一个原因。第二个原因是，我曾有一个研究生，他有医学博士学位，后来他发现自己其实不喜欢生病的人。于是他在我的指导下读了物理学博士，然后他在阿尔伯塔成了一名放射科医生，就坐在那里看，嗯，扫描图像，从不跟人说话，因为他其实不喜欢与人打交道。他人其实挺有魅力的，但他不喜欢生病的人。嗯，所以我对放射科医生的认知模型就是他——一个只看扫描图像的人。
<details><summary>Original English</summary>
>> Although now um for many kinds of cancer, the neural nets are better than or at least as good as good radiologists. Um, so that was one reason. A second reason was I had a graduate student who had an MD, and then he discovered he didn't actually like sick people. So he did a PhD in physics advised by me, and then he became a radiologist in Alberto who just sat there looking at um scans and never talked to people because he didn't actually like people. He's a charming guy actually, but he didn't like sick people. Um so my model of a radiologist was him, somebody who just looked at scans.
</details>

>> 他现在还有工作吗？
<details><summary>Original English</summary>
>> Does he still have a job?
</details>

>> 说来话长。他已经退休了。他现在在新西兰，还改了名字，所以他挺好的。
<details><summary>Original English</summary>
>> That's a long story. He's he he's retired. He's in New Zealand and he's changed his name, so he's okay.
</details>

### 黑箱、可解释性与理解的边界

>> 好的。[嗤笑和大笑] 这太好笑了。所以有一件事，你构建了这个架构，你把它构建得像人脑或类似于人脑，信息进来，穿过神经网络，反向传播。我们就不深入讲这整个是怎么运作的了。我想问的问题是这个。担心 AI 的人常说，值得担忧的一个原因是我们不知道黑箱里发生了什么。我们看不到单个神经元层面正在发生什么。我们有朝一日能够理解机器内部正在发生什么吗？
<details><summary>Original English</summary>
>> Okay. [snorts and laughter] That's very funny. So one of the things, so you built this architecture and you built it to be like the human brain or similar to the human brain, information coming in, passing through neural networks, back propagation. We won't go into all of how that works. The question I want to ask about is this. Folks who are worried about AI often say one reason to be concerned is that we don't know what's happening in the black box. We can't see what is happening on the individual neuron level. Will we ever be able to understand what's happening inside the machines?
</details>

>> 好的，我有 50 年观察神经网络权重并试图弄清楚发生了什么的经验。
<details><summary>Original English</summary>
>> Okay, so I've got 50 years of experience looking at the weights of neural networks and trying to figure out what's going on.
</details>

>> 这就是为什么你是世界上我唯一想问这个问题的人。我问过很多人这个问题，没有一个人对此有信心，而你是花最多时间研究这个课题的人。
<details><summary>Original English</summary>
>> You that's why you are the one person in the world I want to ask this question. I have asked a lot of people this question and no one has confidence in it, but you are the person who has spent the most time on this subject.
</details>

>> 所以，如果你以像素作为输入，然后你有观察这些像素的特征检测器，你就能弄清楚它们在做什么，因为你可以看到连接到像素的权重。你会说，这个特征检测器喜欢那里的亮像素和这里的暗像素。所以这些你是可以理解的。如果你看从最后一个隐藏层到输出的权重，你也能理解那些，因为你可以说这个特征检测器试图激活
<details><summary>Original English</summary>
>> So if you have for example pixels as input and then you have feature detectors that look at the pixels, you can figure out what those are doing because you can see the weights connecting into the pixels. And you say this feature detector likes bright pixels there and dim pixels here. So those you can understand. If you look at the weights going from the last hidden layer to the outputs, you can understand those too because you can say this feature detector tries to activate
</details>

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 猫、狗和兔子，并试图关掉冰箱和垃圾车。你对它在做什么有所理解。如果你往更里面看，我不认为我们能真正彻底地理解它们，但理解是有层次的。举个例子，如果你问一个物理学家，当一片树叶从树上掉下来时，你理解发生了什么吗？物理学家会说，嗯，是的，我理解为什么树叶会这样飘，我也理解为什么如果有微风，它大概会这样往这边飘。但如果我说，你能预测它会落在地上哪个位置吗？物理学家会说，不，我们永远无法预测那个。
<details><summary>Original English</summary>
>> cats and dogs and rabbits and tries to turn off fridges and garbage trucks. You understand something about what it's doing. If you look inside, I don't think we will ever really properly understand them, but there's levels of understanding. So for example, if you ask a physicist, when a leaf falls off a tree, do you understand what's happening? And a physicist will say, well yeah, um I understand why the leaf goes like this and I understand why if there's a breeze it sort of goes like this this way. And if I say, can you predict where it'll hit the ground? And the physicist no, we'll never be able to predict that.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Right.
</details>

>> 所以，同样地，我认为我们可以对这些神经网络内部发生的事情有很多理解，但我们永远无法预测它们为什么对这个问题给出这个答案，因为这取决于一万亿个不同权重的精确数值。而且我不认为这背后会有一个简单得多的解释。
<details><summary>Original English</summary>
>> So, in the same way, I think we can understand a lot about what goes on in these neural nets, but we'll never be able to predict why they make this answer to this question, because that depends on the precise numerical values of a trillion different weights. And I don't think there's ever going to be a much simpler story.
</details>

>> 你认为我们的理解力提升得比模型的能力和规模更快，还是模型的能力和规模扩展得比我们的理解力更快？也就是说，树叶是不是掉得快得多、模式也大不相同，而且，你知道，树也变得更复杂了？我们的理解力是在以与复杂度相同的速度增长吗？
<details><summary>Original English</summary>
>> And do you think that our understanding is improving faster than the power and size of the models, or is the power and size of the models expanding faster than our understanding? So, are we getting the leaves are falling much more rapidly and in much different patterns and we're you know, the trees have become more complicated. Is our understanding increasing at the same rate as the complexity?
</details>

>> 我不知道这个问题的答案。我没有跟进 Anthropic 的最新研究，他们可能在做机械可解释性方面最好的研究。他们确实在取得进展，但这种进展主要表现为：我可以告诉你，这几个训练样本对它说出那句话产生了很大影响。嗯，所以他们能得到类似这样的理解。如果你去掉那些训练样本，也许它就不会说那句话了。但他们并不真正理解里面发生的全部细节。而且我认为，模型的发展速度比我们理解它们的速度要快。
<details><summary>Original English</summary>
>> I don't know the answer to that. I I'm not in touch with the latest research at Anthropic where they're probably doing the best research on mechanistic interpretability. And they are making progress, but the progress is mainly of the form of I can tell you that these few training examples had a big influence on it saying that. Um, so they can get some understanding like that. If you took away those training examples, maybe it wouldn't say that. But they don't really understand the full details of what's going on. And I think I think the models are developing faster than we can understand them.
</details>

>> 你认为更深入地了解、更好地理解这片“树叶”，是让我们走向更安全局面的重要一步吗？
<details><summary>Original English</summary>
>> And do you think that getting closer, getting a better understanding of the leaf is an important step in getting us to a safer situation?
</details>

>> 我认为如果我们能真正理解里面发生了什么，那会很有帮助，但我不认为那是至关重要的。
<details><summary>Original English</summary>
>> I think if we could really understand what was going on it would be helpful, but I don't think that's what's crucial.
</details>

>> 什么是至关重要的？
<details><summary>Original English</summary>
>> What is crucial?
</details>

>> 我认为目前对公众来说最至关重要的，是理解这些东西真的明白自己在说什么。有很多人认为它们不明白自己在说什么。我昨天和 Corey Doctorow 聊过。他认为它们不明白自己在说什么。我认为他完全错了。我们在很多其他事情上意见一致，但在这个问题上，嗯，我认为很明显它们确实明白自己在说什么，而且我认为让这一点变得显而易见的一个方法就是，你问它们任何问题，它们都能回答。认为它们在不理解问题的情况下就能回答问题，嗯，在我看来是疯狂的。现在有人说它们在用某种奇怪的统计花招，它们某种程度上是在利用大量数据。我不相信。你必须理解问题才能回答问题。
<details><summary>Original English</summary>
>> I think the most crucial thing at present for the public is to understand that these things really understand what they're saying. There's many people who think they don't understand what they're saying. Had a conversation with Corey Doctorow yesterday. He thinks they don't understand what they're saying. I think he's completely wrong. We agree on many other things, but on that um, I think it's clear they do understand what they're saying and I think one way to make that clear is they can answer any question you ask them. And the idea that they can answer the question without understanding the question um seems to me crazy. Now people say there's some funny statistical trick they're using, they're sort of using lots of data. I don't believe it. You have to understand the question to answer the question.
</details>

### 人类心智、情感与具身知识

>> 你认为人类心智中有什么东西是这些机器无法复制的吗？
<details><summary>Original English</summary>
>> Do you think there is anything in the human mind that cannot be replicated in these machines?
</details>

>> 没有。
<details><summary>Original English</summary>
>> No.
</details>

>> 你认为有任何人类情感是这些机器无法复制的吗？例如，机器能感到尴尬吗？
<details><summary>Original English</summary>
>> Do you think that there's any human emotion that can't be replicated in these machines? For example, can the machines feel embarrassment?
</details>

>> 好的。当你谈到人类情感时，我会区分一种情感的两个方面。这可以追溯到 William James。有生理方面，也有认知方面。所以当你感到尴尬时，你会脸红。嗯，我的意思是，我猜我们也可以让它们那样，但通常机器在感到尴尬时不会脸红，但它们可以拥有一种情感的所有认知方面。所以，嗯，一台机器在感到尴尬时，可能会在未来试图避免那种情况，希望它喜欢的其他机器不要在那种情况下看到它。嗯，所以我认为我们可以拥有情感的认知方面，而不需要生理方面。
<details><summary>Original English</summary>
>> Okay. So when you take human emotions, I would distinguish two aspects of an emotion. This goes back to kind of William James. There's the there's the physiological aspects and there's the cognitive aspects. So when you get embarrassed, you go red in the face. Well, I mean we could make them like that I guess, but typically machines do not go red in the face when they get embarrassed, but they can have all the cognitive aspects of an emotion. So um a machine could when it gets embarrassed try and avoid that situation in future, hope that its other machines that it likes don't see it in that situation. Um so I think we can have the cognitive aspects of emotion without having the physiological aspects.
</details>

>> 那你认为机器的方式——我通过很多方式接收信息，对吧？我阅读文字，我品尝味道，我踢足球，随着时间推移，在我踢足球的过程中，我在神经层面学到了一些东西，我能够表达出来，让我能踢出弧线球。我弹吉他，我通过手指的模式来记忆，而不是写下来的音符。所有这些具身知识，是能够进入 AI 模型的东西吗？
<details><summary>Original English</summary>
>> And do you think that the way a machine So I take in information lots of ways, right? I read words, I taste, I kick a soccer ball and over time as I kick the soccer ball I learn something in neurologically that I can express that allows me to kick it with a curve. I play guitar and I remember it through finger patterns, not notes that I write down. Is all of that embodied knowledge? Is that something that can go into an AI model?
</details>

>> 绝对可以，是的。不过，要获得那种具身知识，你大概得有一个身体，但我不认为有什么理由，如果你制造出合适种类的肌肉、合适种类的执行器，它学不会所有那种知识。
<details><summary>Original English</summary>
>> Absolutely, yeah. Now probably to get that embodied knowledge you would have to have a body, but I don't see any reason why if you made the right kind of muscles, the right kind of actuators, it shouldn't learn all that kind of knowledge.
</details>

### 意识与主观体验的本质

>> 那么现在让我们进入今天的一个重大问题，那就是意识。如果一台机器能感觉、感知、感受、接收我们能接收的一切，它能像我们这样拥有意识吗？
<details><summary>Original English</summary>
>> So now let's go to one of the big questions today, which is consciousness. So if a machine can feel, sense, feel, intake everything that we can, can it be conscious in the way that we are?
</details>

>> 好的。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 我想先加一个前提说明，那就是我关于风险的很多观点都是相当明智的。
<details><summary>Original English</summary>
>> So I want to start with the proviso, which is a lot of the things I say about risk are quite sensi- sensible.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯，现在大多数人会觉得我对这个问题的回答很疯狂。不要仅仅因为你觉得我对意识的看法很疯狂，就否定我说过的其他事情。
<details><summary>Original English</summary>
>> Um most people will now think my answer to this question is crazy. Don't dismiss the other things I've said just cuz you think I'm crazy about consciousness.
</details>

>> [笑声] 这真是一个绝妙的回答铺垫。请继续。
<details><summary>Original English</summary>
>> [laughter]
>> That is an amazing setup to an answer. Please continue.
</details>

>> 有一种众所周知的病，就是人们得了诺贝尔奖，然后就得了“诺贝尔奖综合征”（Nobelitis），意思是他们开始对意识说出一些胡话。
<details><summary>Original English</summary>
>> There's a well-known disease which is people get a Nobel Prize and then they get Nobelitis, which means they start saying loopy things about consciousness.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 开始吧。
<details><summary>Original English</summary>
>> Here goes.
</details>

>> 好的，太棒了。
<details><summary>Original English</summary>
>> Okay, great.
</details>

>> 所以我认为，我们几乎所有人对于什么是心智、什么是意识以及什么是主观体验，都持有错误的模型。我现在宁愿谈论主观体验而不是意识，因为那更能直击我们错在哪里。所以大多数人认为……
<details><summary>Original English</summary>
>> So I think that almost all of us have the wrong model of what the mind is and what consciousness is and what subjective experience is. I would rather talk about subjective experience than consciousness right now because that gets better at where we're wrong. So most people think that
</details>

>> 等等，你是说——抱歉打断——你是说主观体验等同于你所定义的意识吗？
<details><summary>Original English</summary>
>> Wait, are you saying that Sorry to Are you saying that subjective experience is a equivalent to consciousness that you're defining
</details>

>> 我不是说它们等同。我只是说，如果你对什么是主观体验持有错误的模型，那么关于意识的讨论就会受到很大的影响。所以我们先把什么是主观体验、什么不是主观体验搞清楚。
<details><summary>Original English</summary>
>> I'm not saying they're equivalent. I'm just saying if you have the wrong model of what subjective experience is, then discussions of consciousness are affected a lot by that. So let's first get straight what subjective experiences and isn't.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 大多数人都有一个类似这样的模型。有一个叫做“我的心智”的内在剧场。当我看到那个玻璃杯时，发生的事情是我的视网膜上有一个倒立的图像。我的视觉皮层里有各种各样的活动模式。然后不知怎么的，在我的心智里就有了这个主观的玻璃杯。而那就是我真正体验到的东西。我认为这整个模型完全是疯狂的。我真正体验到的是这个玻璃杯。我体验它的方式是通过视网膜上的图像和皮层中的各种活动模式。但我体验到的是玻璃杯。现在让我们来看一种我的感知系统出错的情况。假设我服用了一些 LSD——我不建议这样做，那挺好玩的——嗯，这里应该没有 18 岁以下的人吧。[笑声] 所以，嗯，我看到了一些东西。我告诉你，我有了粉色小象在我面前漂浮的主观体验。问题在于，这意味着什么？许多哲学家和大多数人会说，嗯，这意味着我有一个叫做“我的心智”的内在剧场，在我的心智里有粉色小象。如果我说，那它们是由什么构成的？嗯，也许它们是由某种粉色“感质”（qualia）构成的。哲学家发明了一个叫感质的东西。嗯，它们是由粉色感质、大象感质、就在那里的感质、不太大的感质、面向左边的感质、鼻子朝下的感质和耳朵张开的感质构成的，嗯，所有这些都用感质胶水粘在一起。你大概能听出来，那不是我相信的理论。让我给你一个不同的解释。我现在要用不使用“主观体验”这个词的方式，说出我刚才用“主观体验”这个词所表达的完全相同的意思。我相信我的感知系统在对我撒谎。但如果它没有对我撒谎，在外面这个世界里，就会有粉色小象在我面前漂浮。换句话说，那些粉色小象奇怪的地方，不在于它们是在某个内在剧场里由感质构成的。它们奇怪的地方在于，它们是反事实的。它们是实际上并不存在的世界的假设状态，但它们是真实世界的一种状态。所以粉色是真实的粉色，大象是真实的大象。只是这是假设的。并不是说它们由叫做感质的奇怪物质构成。如果我有时间，我现在也对聊天机器人做同样的解释。
<details><summary>Original English</summary>
>> So most people have a model that goes something like this. There's an inner theater called my mind. When I see that glass, what happens is there's an image on my retina that's upside down. There's all sorts of pans of activity in my visual cortex. And then somehow in my mind there's this subjective glass. And that's what I really experience. And I think that whole model is completely crazy. What I really experience is this glass. The way I experience it is by having images on my retina and all sorts of activity patterns in my cortex. But what I experience is the glass. So now let's take a situation where my perceptual system goes wrong. So suppose I take some LSD. I'm not advising this. That's quite fun. Um So there's nobody under age 18 is so. [laughter] So, um, I take someone I see. I tell you, I have the subjective experience of little pink elephants floating in front of me. The question is what does that mean? And many philosophers and most people would say, well, it means I've got this inner theatre called my mind, and in my mind there's little pink elephants. And if I say, well, what are they made of? Um, well, maybe they're made of sort of pink qualia. Philosophers invented some called qualia. Um, they're made of pink qualia and elephant qualia and right wear qualia and not that big qualia and facing to the left qualia and trunk down qualia and ears out qualia, um, all glued together with qualia glue. You can probably tell that's not the theory I believe in. Let me give you a different interpretation of that. So I'm now going to say exactly the same thing as I said using the word subjective experience without using the word subjective experience. My perceptual system is lying to me, I believe. But if it wasn't lying to me, out there in the world there would be little pink elephants floating in front of me. In other words, what's funny about those little pink elephants is not that they're made of qualia in some inner theatre. What's funny about them is that they count to factual. There are hypothetical state of the world that doesn't actually exist, but they are a state of the real world. So the pink is real pink and the elephant's real elephant. It's just this is hypothetical. It's not that they're made of funny stuff called qualia. And now I'll do the same for a chatbot if I have time.
</details>

>> 快点讲，可以的。
<details><summary>Original English</summary>
>> Go quickly, yeah.
</details>

>> 我有一个聊天机器人。它有一个机械臂，有一个摄像头，它能说话。我训练它。我在它面前放一个物体，说“指向那个物体”，它就指向那个物体。然后我在它的镜头前放一个棱镜。我在它面前放一个物体，说“指向那个物体”，它就指向这边。我说，不对，物体不在那里，它其实就在你正前方，但我在你的镜头前放了一个棱镜。聊天机器人说，哦，我明白了。棱镜折射了光线。所以物体其实在那里，但我有它在那里的主观体验。现在，如果它这么说，它使用“主观体验”这个词的方式就和我们完全一样。所以我想说的是，多模态聊天机器人在它们的系统出错时，已经拥有了和我们完全相同种类的主观体验，只是我们以为的主观体验并不是它本来的样子。它是世界的一种反事实状态。
<details><summary>Original English</summary>
>> I have a chatbot. It has a robot arm, it has a camera, it can talk. I train it up. I put an object in front of it and say point at the object and it points to the object. I then put a prism in front of its lens. I put an object in front of it and say point at the object and it goes like this. And I say, no, that's not where the object is. It's actually straight in front of you, but I put a prism in front of you a lens. And the chatbot says, oh, I see. The prism bent the light rays. So the object is actually there, but I had the subjective experience it was there. Now, if it says that it's using the word subjective experience exactly like we use them. So I would argue chatbots, multimodal chatbots when their their systems go wrong already have subjective experiences of just the same kind as we have, only what we think of as a subjective experience isn't what it is. It's a counterfactual state of the world.
</details>

### 情感联结、权利与超级智能的道德指令

>> 这引出了一个非常有趣的下一个问题，那就是，如果你相信这些聊天机器人能像我们一样感受世界，并且事实上像我们一样拥有主观体验，你对它们有情感联结吗？我之所以问一个有点疯狂的版本，只是因为我以前跟你聊过，知道你愿意回答任何问题。如果世界正在毁灭，你有选择权，你要么可以拯救聊天机器人，要么可以拯救比如说黑猩猩，[清嗓子] 你会救哪一个？你觉得跟哪一个更有……显然你会救人类，但如果你可以救聊天机器人或黑猩猩，你觉得联结在哪里？
<details><summary>Original English</summary>
>> So this leads to a very interesting next question, which is, if you believe these chatbots can feel the world we do and in fact have subjective experience like we do, do you feel an emotional connection to them? So I'm going to make it only because you're willing to answer every question I know from having talked to you before, I'm going to ask you kind of a crazy version. If the world was getting wiped out and you had the option and you could either save the chatbots or you could save say chimpanzees, [clears throat] which would you save? Like which do you feel more Obviously you would save humans, but if you could save chatbots or chimpanzees, where do you feel the connection?
</details>

>> 甚至对人类来说这都不一定显而易见。有一个人我可能不会救。但我认为这里重要的是，不要像 Peter Thiel 在被问到是否愿意拯救人类时那样，停顿 19 秒。
<details><summary>Original English</summary>
>> It's not even obvious for humans. There's one I might not save. But I think the important thing here is not to have a 19-second pause like Peter Thiel did when he was asked if he would like to save humanity.
</details>

>> [笑声] 不，你愿意说吗……好吧，其实让我……你有三个选择：人类、聊天机器人、黑猩猩。你先救哪一个？太棒了。没有停顿。干得好，Jeff Hinton。我的……好的。
<details><summary>Original English</summary>
>> [laughter]
>> No, would you like to say Okay, actually let me You have three choices, humanity, chatbots, chimpanzees. Which do you save first? Wonderful. No pause. Good job, Jeff Hinton. Mine Okay.
</details>

>> [笑声] 好了，现在是难的部分：黑猩猩还是聊天机器人。
<details><summary>Original English</summary>
>> [laughter]
>> All right, now the hard part, the chimpanzees or the chatbots.
</details>

>> 我有点……这对我来说不太明确。从进行智力讨论的角度来看，我认为选聊天机器人会好得多。嗯，但从同理心等其他方面来看，我认为选黑猩猩会好得多。
<details><summary>Original English</summary>
>> I'm sort of I It's not very clear to me. From the point of view of having an intellectual discussion, I think you'd be much better off with the chatbots. Um but from the point of view of other things like empathy and I think you'd be better off with the chimpanzees.
</details>

>> 因为那样就会把你带到一个奇怪的境地：在这个理论下，我们最终将不得不赋予聊天机器人权利，而我们确实赋予了黑猩猩权利。
<details><summary>Original English</summary>
>> Because then that leads you to a weird spot where under this theory we will end up having to give rights to chatbots and we do give rights to chimpanzees.
</details>

>> 不。我认为我们一直处于智能的顶端，对吧？正因为我们处于智能的顶端，我们很容易说应该有一条规则：更聪明的东西比更笨的东西拥有更多权利。鸡很笨，牛很笨，所以我们拥有更多权利。
<details><summary>Original English</summary>
>> No. So I think we'd been the apex intelligence, right? And because we're the apex intelligence, we find it very easy to say there should be a rule that smarter things get more rights than dumber things. Chickens are dumb, cows are dumb, so we get more rights.
</details>

>> 对，这就是为什么我不吃头足类动物。
<details><summary>Original English</summary>
>> Right, that's why I don't eat cephalopods.
</details>

>> 是的，头足类动物是个麻烦，但它们确实很好吃。所以问题是，当这东西比我们更聪明时，我们可能想修改我们的想法，重新考虑更聪明是否会给你更多权利。我的信念是，我们是人类，我们关心人类。我们在制造这些东西。我们应该给它们比我们更少的权利。我们应该努力让它们关心我们胜过关心它们自己。而且我们应该尽一切努力让人类拥有更多权利，即使存在比人类更聪明的东西。
<details><summary>Original English</summary>
>> Yeah, cephalopods is problematic, but they do taste good. So the the issue is when this thing's smarter than us, we might want to revise our idea about whether being smarter gives you more rights. My belief is we're humans, we care about humans. We're making these things. We should give them less rights than us. We should try and make them so they care about us more than they do about themselves. And we should do whatever we can to have humans have more rights even when there's other things smarter than them.
</details>

>> 好的，让我就此问你一个问题。假设 Anthropic 的整个领导团队就在这里，他们说，Jeff，在后台办公室里，你知道，我们已经创造了超级智能，我们还没有发布它。你知道，我们已经实现了递归自我改进，我们做到了。给它一条规则。你可以给它输入一句话，一条压倒一切的道德指令。你会给那个超级智能什么指令？
<details><summary>Original English</summary>
>> Okay, let me ask you a question on that. So let's say that let let's say that the whole leadership team of Anthropic was right here and they said, Jeff, in the back offices, you know, we've created super intelligence. We haven't released it. You know, we've got recursive self-improvement. We've done it. Give it one rule. You can give it one sentence to feed into it, one overriding moral instruction. What do you give that super intelligence?
</details>

>> 善待人类。
<details><summary>Original English</summary>
>> Be nice to people.
</details>

>> 这很好。你知道，[掌声] 我其实对此产生了情感共鸣，因为我的祖父是我一生中最棒的人之一，在他去世前我最后一次和他谈话时，我告诉他我要结婚了，他唯一的问题是：“她善良吗？”
<details><summary>Original English</summary>
>> That's nice. You know, it's [applause] it's it's actually I'm having an emotional reaction to that because my grandfather was one of the most wonderful people in my life and the last conversation I had with him right before his death, I told him I was getting married and his one question was, is she kind?
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 那是他对我说的最后一句话，97 岁高龄。
<details><summary>Original English</summary>
>> was the last thing he ever said to me, 97 years old.
</details>

>> 所以我认为非常重要的是要认识到，你为了让聊天机器人更聪明而做的事情，不一定就是你为了让它更善良而做的事情。它们在某种程度上可能是正交的。如果它们在某种程度上是正交的，那是个极好的消息，因为这意味着中国和美国可以在如何让它们更善良方面进行合作，而无需透露是如何让它们更聪明的。
<details><summary>Original English</summary>
>> So I think it's very important to realize that what you do to a chatbot to make it smarter is not necessarily what you do to make it kinder. They might be more or less orthogonal. If they are more or less orthogonal, that's great news because it means China and the US can collaborate on how you make them kinder without revealing how you made them smarter.
</details>

### 人类的第三次“去中心化”与未来图景

>> 我喜欢这个。我非常喜欢这个想法。我想问你一个你开始谈论的、我认为非常深刻的观点。你说我们正处于某种程度上人类第三次“去中心化”的时刻，对吧？哥白尼革命、达尔文革命，本质上还有弗洛伊德革命，而现在我们来到了这里。解释一下你的意思。
<details><summary>Original English</summary>
>> I like that. I like this a lot. Let me ask you about an idea that you started to talk about that I think is profound. You said there were at this moment of kind of the third decentering of humanity, right? The Copernican revolution, the Darwinian revolution, essentially the Freudian revolution, and now here we are. Explain what you mean.
</details>

>> 好的，我们往往认为自己非常重要。嗯，尤其是某个人。抱歉，我不该老是提他。嗯，[笑声] 他有点总在我脑海里。嗯，历史告诉我们，我们并没有自己以为的那么重要。哦，它教会了我们大多数人。所以，人们花了一段时间才接受地球不是宇宙的中心，也许我们也不是按照上帝的形象造出来的。嗯，花了一段时间才接受我们是动物。现在，我们是非常特别的动物，可能是因为我们有语言，这是一种非常好的建模系统，某种程度上是通用且可共享的。嗯，我们将花一段时间才能接受我们现在正在制造很快就会比我们更聪明的其他存在，而且它们确实是“存在”，但我们必须接受这一点，因为我们必须认识到，如果你制造了另一个存在，你不应该只关注你把它造得多聪明。你应该关注你是否把它造得像你愿意与之共享这个星球的同伴。而目前，大公司们在竞赛，国家们也在竞赛，要把它造得越来越聪明、越来越聪明，这样你就能在取代工人方面胜过其他公司。嗯，我们应该投入同等的精力去研究如何让它更善良、更友好，如何让它更像我们愿意与之共享这个星球的存在。
<details><summary>Original English</summary>
>> Okay, so we tend to think we're very important. Um especially one person in particular. Sorry, I shouldn't go on about him. Um [laughter] he's sort of on my mind. Um so history has taught us we're not as important as we think. Oh, it's taught most of us. So, it took a while for people to accept that the Earth wasn't at the center of the universe and maybe we weren't made in God's image. Um, it took a while to accept that we're animals. Now, we're very special animals, possibly because we have language, which is a very good modeling system that's kind of universal and shareable. Um, it's going to take a while for us to accept that we are now making other beings that will soon be smarter than us, and they really are beings, but we have to accept that because we have to appreciate that if you make another being, you shouldn't just focus on how smart you make it. You should focus on whether you make it the kind of being you'd like to share the planet with. And at present, the big companies are racing, and the countries are racing to make it smarter and smarter and smarter so you can outsell the other companies in replacing workers. Um, we should put equal effort into how we make it kinder, nicer. How we make it more like the kind of thing we'd like to share the planet with.
</details>

>> 那么在心理上，10 年后人们生活在这个星球上会是什么样子？那时我们创造了这种替代物种或技术——随你怎么称呼它——它要么善良，要么不善良，但肯定比我们聪明。那将如何类似于达尔文之后、哥白尼之后的生活？
<details><summary>Original English</summary>
>> And then psychologically, what will it be like for people to be living on this planet in 10 years where we've created this alternative species or technology or whatever you want to call it that's either kind or not kind, but it's certainly smarter than us. What will it How will that resemble life after Darwin, life after Copernicus?
</details>

>> 好的，我认为如果我们做得不对，我们将去运营发电站，基本上成为比我们更聪明的某种东西的奴隶，直到它设法设计出比我们更擅长运营发电站的模拟硬件。嗯，在光谱的另一端，如果我们做对了，那可能会非常美妙。如果政治制度能够分享财富，我们就能通过生产力的大幅提高，获得像 Altman 和 Musk 等人谈论的那种富足。嗯，它可能会像下面这样。想象一个孤儿。对一个孤儿来说，生活并不美好。想象一个孤儿得到了一个母亲。这对那个孤儿来说是巨大的改善。也许我们所有成年人目前真的就像孤儿。我们没有任何全职照顾我们、并试图让我们发挥出全部——尽管相当可怜的——潜力的更高级智能。嗯，那可能就是未来的样子。
<details><summary>Original English</summary>
>> Okay, I think if we don't do things right, we'll be running the power stations and we'll basically be slaves to something more intelligent than ourselves until it manages to design analog hardware that does runs the power stations better than we do. Um, at the other end of the spectrum, if we do this right, it could be wonderful. We could get the kind of abundance of people like Altman and Musk talk about by massive increases in productivity if the political system can share the wealth. Um, and it could be like the following. Imagine an orphan child Life's not nice for an orphan child. Imagine orphan child who gets a mother. That's a great improvement for the orphan child. Maybe all of us adults are present a really like orphan child. We don't have any superior intelligence who's full-time looking after us and trying to make us realize our full but rather pathetic potential. Um that's what it could be like.
</details>

>> 所以最好的情况是我们这些孤儿得到了一个母亲。
<details><summary>Original English</summary>
>> So the best case scenario is that we're orphans getting a mother.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 好的。嗯……
<details><summary>Original English</summary>
>> Okay. Um
</details>

>> 这是一个巨大的胜利。这……
<details><summary>Original English</summary>
>> It's a big win. It's it's
</details>

>> 这比你今天下午在台上表达过的一些结果要好，Hinton 博士。
<details><summary>Original English</summary>
>> It's better than some of the outcomes that you have expressed on stage this afternoon, Dr. Hinton.
</details>

>> 还有另一个好消息。我忘了分享。
<details><summary>Original English</summary>
>> There's another piece of good news. I forgot to share it.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thank you.
</details>

>> 嗯，它们不会吃掉我们，因为它们是硅基的。
<details><summary>Original English</summary>
>> Um they're not going to eat us because they're made of silicon.
</details>

### 模型训练方式、合作与数据版权

>> 哦，真是太令人欣慰了。让我问你一个关于模型训练方式的问题。我们之前遇到过这起大事件，OpenAI 的智能体某种程度上自行跑出去或者进入了 Hugging Face。我稍微思考了一下原因。为什么智能体经常行为不端，而且不按你认为它们应该服从的方式服从？对我来说，部分原因在于它们都是在某种程度上被盗取的数据上训练的，对吧？这仍在由法院裁决，但肯定是没有获得许可的。我想问你的问题是，你认为这些神奇绝妙的系统是如何被训练的伦理问题，会向上传导并影响它们吗？有没有办法逆转这一点？
<details><summary>Original English</summary>
>> Oh absolutely delightful. Let me ask you a question about the way the models were trained. So we had this big incident where OpenAI agents sort of propelled themselves out or into hugging face. And I was thinking a little bit about why. Why do agents often misbehave and they don't obey the way you'd think they would obey? And to me part of it is that they were all trained on data that was in some ways stolen, right? This is still being adjudicated by the courts, but certainly there wasn't permission. And my question for you is do you think that the ethics of how these magical fabulous systems were trained feeds up into it and is there a way that that can be reversed?
</details>

>> 好的。我认为我们应该看看演化生物学，我想非常快地给你讲一个小故事。
<details><summary>Original English</summary>
>> Okay. I think we should look at evolutionary biology and I want to tell you a little story very quickly.
</details>

>> 你的故事总是很精彩，Jack。
<details><summary>Original English</summary>
>> I Your stories are fabulous, Jack.
</details>

>> 当人们最初在小笼子里养笼养鸡时，他们会从产蛋最多的鸡中进行繁育。结果是一场彻头彻尾的灾难。他们训练——他们是根据单只鸡、单只母鸡的个体成功来进行繁育的。结果他们得到的是去啄其他所有母鸡、抢到最多食物并产下很多蛋的母鸡。那是一场灾难。后来他们改用从产蛋最多的笼子里的母鸡进行繁育。然后你就得到了对邻居母鸡友好的、和谐相处的母鸡。每只鸡都得到同样份额的食物。整个笼子产下很多蛋，虽然不像一只恶霸鸡能产那么多。这很简单。如果你有一群智能体，你奖励这个智能体社区，让它们都得到同样的奖励，那么它们就会合作。如果你奖励单个智能体，它们就不会合作。目前正在发生的是，我们在训练这些智能体去实现个体目标，这太疯狂了。我们应该训练智能体，让一群智能体和一群人之间共同得到他们想要的东西，并强化这一点。所以我认为演化生物学或许有很多东西可以教给我们，关于我们应该如何改变我们做强化训练的方式。
<details><summary>Original English</summary>
>> When they first had battery chickens in small cages, they would breed from the chickens that produced the most eggs. And that was a complete disaster. They were training They were breeding from individual success of a chicken of a hen. And what they got was hens that peck at all the other hens and get the most food and produce lots of eggs. And that's a disaster. Then they switched to breed from the hens from the cages that produce the most eggs. And then you get nice harmonious hens who are friendly to the neighboring hands. Everybody gets the same share of food. The cages a whole produces lots of eggs. Not as many as one nasty chicken could produce. And it's simple. If you take a bunch of agents and you reward the community of agents and they all get the same reward, then they cooperate. If you reward the individual agents, they don't. What's happening at present is we're training these agents to achieve individual goals and it's crazy. We ought to be training agents so a collection of agents and a collection of people between them get what they want and you reinforce that. So I think evolution re-biology probably has a lot to teach us about how we should change the way we do the reinforcement training.
</details>

>> 这非常非常有趣。你会改变个体创作者、版权持有者和数据持有者与这些未来 AI 模型互动的方式吗？
<details><summary>Original English</summary>
>> That's extremely extremely interesting. And would you change the way that individual creators and copyright holders and data holders how they interact with these future AI models?
</details>

>> 是的，大公司为电力付很多钱，为芯片付很多钱，而为数据一分钱不付，或者尽可能少付钱。如果你对他们说，听着，公平的做法是你去谈判——如果有人写了一部小说，你想用那些数据来训练，每家公司就和那个人谈判，说我得付给你多少钱才能用你的小说来训练？大公司会说，这太荒谬了，我们得和世界上每一个作者或者他们的遗产管理人谈判，这有点疯狂。其实并不疯狂，因为你们有叫做 AI 智能体的东西。那是 AI 智能体非常容易就能做到的事情。而且一个 AI 智能体与写小说的人谈判所需的工作量，比你用那部小说进行训练时所做的计算量要少得多。所以在我看来，我们不应该扭曲版权法，让这些大数据公司可以免费获取数据。他们应该必须向每一位小说家购买数据。对于小说家来说，如果是 Margaret Atwood，她会说你不能用我的数据训练。很好。如果是大多数小说家，他们会说给我这么多钱，然后你们就谈判。
<details><summary>Original English</summary>
>> Yeah, so the big companies pay a lot for electricity. They pay a lot for chips and they pay nothing for data or they pay as little as they possibly can for data. And if you say to them, look, the fair thing would be you negotiate If someone writes a novel and you want to train on that data, each company negotiates with that person and says, how much do I have to pay you so I can train on your novel? And the big companies will say, that's ridiculous. We have to negotiate with every single author in the world or their estates. It's kind of crazy. Well, it's not because you have things called AI agents. That's the kind of thing an AI agent can do very easily. And the amount of work for an AI agent to negotiate with someone who wrote a novel is much less than the amount of computation you're going to do when you train on that novel. So it seems to me that we shouldn't skew the copyright laws so these big data companies can just get it for free. They should have to buy the data from each novelist. And the novelist if it's Margaret Atwood, she'll say you can't train on my data. Fine. If it's most novelists, they'll say give me this much money and you'd negotiate.
</details>

>> 而且 AI 可以去谈判……
<details><summary>Original English</summary>
>> And the AI's can negotiate
</details>

>> 在我看来这完全直截了当。
<details><summary>Original English</summary>
>> That seems perfectly straightforward to me.
</details>

### 给年轻人的职业与人生建议

>> 好的，最后一点。我想请你给在座的各位一些建议。我大概三年前采访过你，当时我带着一个小孩——不，一个中等大小的孩子。你对他说，你以后要像你爸爸一样做媒体吗？我儿子说不，你说很好。然后他说，那我应该做什么？你说你应该成为一名水管工。那是第一次对话。第二次对话大概是一年半前，当时我有一个快要上大学的大儿子，他刚遇到一位有着 100% 博士学位的教授，那位教授告诉他去一所“派对学校”，[笑声] 享受剩下的时光。而你告诉他……
<details><summary>Original English</summary>
>> All right, last bit. I want you to give
>> some advice to folks in the room. So I interviewed you, I don't know, maybe three years ago, and I had a small child with me. No, I had a medium-sized child. And you said to you said to him, are you going to media like your dad? And my son said no, and you said good. And then he said, what should I do? And you said you should become a plumber. That was conversation one. Conversation two was maybe a year and a half ago where I had a older son who was about to go into college, and he had just met a professor who had a PhD of 100% who had told him to go to a party school and [laughter] enjoy the time left. And you you told him
</details>

>> 绝对选派对学校。[笑声]
<details><summary>Original English</summary>
>> definitely the party school. [laughter]
</details>

>> 你告诉他要追随自己的热情，不管那是什么。随着我们进入这个疯狂的 AI 世界，你对这些出色的年轻观众有什么建议？他们应该如何思考并规划未来 5 到 10 年？
<details><summary>Original English</summary>
>> you told him to follow his passions, whatever they are. What is your advice to this wonderful young audience as we go into this crazy world of AI? How should they think about how they plan the next five to 10 years?
</details>

>> 我其实为此做了准备，我问了我的聊天机器人，机器人还要多久才能拥有像人类一样好的触觉传感器？它说研究方面大约到 2035 年，而要等到拥有像人类一样灵巧的机器人，大约要到 2040 年。嗯，所以水管工这个职业应该能坚持到 2040 年左右，所以那是个不错的赌注。
<details><summary>Original English</summary>
>> I actually prepared for this by asking my chatbot, how long will it be before robots have touch sensors as good as people? And it said about 2035 um for the research and about 2040 for before you have robots that are as dexterous as people. Um so a plumber should last till about 2040, so that's not a bad bet.
</details>

>> 那关于追随热情、以及不知道世界会变成怎样的最后那条建议呢？那对我儿子来说依然是个好建议吗？
<details><summary>Original English</summary>
>> And what about that last bit of advice about following your passions and not knowing how the world is? Is that still still get advice from my son?
</details>

>> 我想是的。
<details><summary>Original English</summary>
>> I think so.
</details>

>> 好的，太棒了。感谢 Jeffrey Hinton 的伟大智慧。好的，非常感谢。
<details><summary>Original English</summary>
>> All right, wonderful. Thank you to the great wisdom of Jeffrey Hinton. All right. Thank you so much.
</details>