---
author: Harvard Business Review
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=evQcbeOlvWc
speaker: Harvard Business Review
tags:
  - generative-ai
  - accelerated-computing
  - organizational-structure
  - ai-safety
  - quantum-computing
title: 英伟达黄仁勋谈生成式AI、扁平化管理与算力演进
summary: 英伟达创始人兼CEO黄仁勋在HBR Live访谈中探讨了生成式AI的本质机制、芯片设计与检索增强应用，阐释了应对出口管制与行业竞争的策略，并分享了扁平化组织架构、危机意识文化及量子计算与加速计算的协同关系。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Jensen Huang
companies_orgs:
  - NVIDIA
  - TSMC
products_models: []
media_books: []
status: evergreen
---
### 开场介绍与生成式AI的本质

**INTERVIEWER**: 黄仁勋是英伟达（NVIDIA）的创始人兼首席执行官，英伟达是AI驱动计算领域的全球领军企业。它为众多行业制造软件和硬件。它的技术可以说是名副其实地推动着我们走向未来。作为一名受过专业训练的电气工程师，黄仁勋于2005年与两位联合创始人在一家丹尼餐厅（Denny's）创办了这家公司。公司目前的年收入达到260亿美元，在全球拥有26,000名员工。黄仁勋，感谢你在我知道对你来说很早的清晨、而且可能也是非常忙碌的一天加入我们。我们非常感激你抽出时间。
<details><summary>Original English</summary>
**INTERVIEWER**: Jensen Huang is the founder and CEO of NVIDIA, a world leader in AI-driven computing. It makes both software and hardware for a host of industries. Its technology is quite literally propelling us into the future. As an electrical engineer by training, Jensen launched the company with two cofounders in 2005 at a Denny's restaurant. It now earns $26 billion in annual revenue and employs 26,000 people around the world. Jensen, thank you for joining us in what I know is an early morning for you, probably a busy day for you. We really appreciate you making the time.
</details>

**JENSEN HUANG**: 很高兴来到这里。
<details><summary>Original English</summary>
**JENSEN HUANG**: I'm happy to be here.
</details>

**INTERVIEWER**: 好的。在开始之前，我想告诉所有观众，我们也想回答大家的问题。请把问题发在“向演讲嘉宾提问”的聊天框中。我们会尽可能多地解答。那么我们现在正式开始。黄仁勋，正如我刚才所说，英伟达生产的技术可以说是实实在在地驱动着未来。我说的是正在推动AI和生成式AI创新的芯片与处理器。我很想听听你的看法。作为一个硬件从业者，你对AI、对生成式AI有什么看法？你认为它会彻底改变我们的工作和娱乐方式吗？还是现在下结论还为时过早？
<details><summary>Original English</summary>
**INTERVIEWER**: Good. OK, now, before we start, let me just tell everyone in the audience we want to answer your questions too. Put them in the ask the speaker chat. We'll get to as many as we can. So let's take it away. So, Jensen, as I just said, NVIDIA's producing technology that is quite literally driving the future. I'm talking about the CHIPS and processors that are driving innovation in AI and generative AI. I'd love your view. As a hardware guy, what's your thought on AI, on gen AI? Do you think it will revolutionize how we work and play? Or is it simply too soon to tell?
</details>

**JENSEN HUANG**: 生成式AI的核心在于软件理解数据含义的能力。它当然能够理解字词、字母、词语、句子和段落的含义，并发现其中的关联与模式。通过大量的示例，它能摸索出——学习到数据的表征，甚至理解其含义。因此它理解结构。它理解信息是如何构建的以及信息的含义。这不仅适用于英语，也适用于像素、3D物体、蛋白质和化学物质。我们现在使用这种深度学习方法来学习众多不同类型数据的表征，几乎包括任何具有结构的数据。而物理世界中，在我们生活的世界里，有许多东西都具有结构。

一旦我们能够理解数据的含义，并且能将一种模态与另一种模态关联起来，例如，我们可以把图像中猫的像素与“猫”这个词关联起来，一旦你能在一个模态与另一个模态之间做到这一点，你就可以进行转换翻译。因此你可以从英语翻译成中文，从中文翻译成法文。你当然也可以从英语转换为像素，这就是生成式AI；或者从像素转换为语言，这就是图像标注（captioning）。你也可以进行文本到文本的转换，比如摘要等等。因此，这个基础模型，这种学习了数据表征的模型，是极其强大的。现在AI行业、计算机行业正在做的，就是将所有这些表示形式、生成方法和转换方法融合到各种有趣的应用程序中。所以我认为，这种兴奋的核心在于学习表征、学习含义以及跨越模态的基本能力。这实在是极其强大。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well, at the core of generative AI is the ability for software to understand the meaning of data. It can understand the meaning of words, of course, letters, and words, and sentences, and paragraphs, and find the relationships and patterns. And from a lot of examples, it figures out the-- learns the representation of the data and even understand its meaning. And so it understands the structure. It understands how it's constructed and the meaning of the information. This applies to English. It applies to pixels, 3D objects, proteins, chemicals. We've now used this deep learning method to learn the representation of a whole lot of different types of data, almost any data with structure. And so there are a lot of things in the physical world, in the world that we live in, that has structure. Once we can understand the meaning of the data, and we can associate one modality to another modality, for example, we can associate the pixels of a cat in an image with the word cat, once you could do this for one modality to another modality, then you can translate things. And so you could translate from English to Chinese, Chinese to French. You can also, of course, translate from English to pixels, which is generative AI, or from pixels to language, which is captioning. Or you could go from text to text, summarization, so on and so forth. And so this basic model, the model that has learned representation of data, is incredibly powerful. And so now what the AI industry, what the computer industry is doing is mixing all of these types of notations, and generative methods, and translation methods into all kinds of interesting applications. And so I think at the core of this excitement is the fundamental ability to learn representation, learn meaning, and to go from one modality to another. And that's just incredibly powerful.
</details>

### AI在芯片设计与企业数据检索中的实际应用

**INTERVIEWER**: 我猜我们的大多数观众大体上都对生成式AI有所了解，也许正在试用它。但除了做实验之外，真正在使用它、应用它的人可能相对较少。你有没有看到一些让你感到惊叹的、已经在实际中落地的应用案例，也许是利用了英伟达的技术？
<details><summary>Original English</summary>
**INTERVIEWER**: I'm guessing that our viewers, by and large, are familiar with gen AI, maybe are playing around with it. Probably relatively few are using it, are applying it, other than through experimentation. Do you have examples, maybe using NVIDIA technology, of applications that you're amazed by, that you're seeing out there already?
</details>

**JENSEN HUANG**: 我们正在使用AI来设计我们的芯片，寻找最优布局，帮助我们将晶体管连接成电路，并在前所未有的规模上帮助我们优化设计。我们开始使用AI来帮助我们从故障中判断Bug可能源自哪里，是哪一行代码导致了该Bug。所以我们正在使用生成式AI来帮助我们完成从芯片设计、芯片优化到定位故障原因的方方面面。

当然，正在发生的最强大的事情之一是生成式AI进行下一步预测——如你所知，它预测下一个词，或者下一个字母、下一个词、下一个句子、下一个段落。它预测下一个像素。它预测视频的下一帧。所以它做出对下一项事物的预测。这些预测可能会产生幻觉。非常有效的方法之一——其中之一当然是提供大量上下文，即人们为了设定背景、设定上下文所做的大量提示词，在向模型提问或要求它执行任务之前对模型进行前置预热条件设定。

真正有用的技术之一是检索增强（retrieval augmentation）。它的含义是，一个无论是结构化还是非结构化、表格化或非表格化的数据库，经过了向量化处理。对数据库进行向量化或嵌入（embedding）需要你学习所有数据彼此之间的关系，就像我之前提到的学习数据表征一样。通过学习表征和对数据库进行向量化，你就能够理解其含义。

所以现在真正令人兴奋的是，你可以将数据库向量化。你可以将其连接到一个大语言模型上。而那个大语言模型基本上允许你与自己的数据对话。每家公司内部都有海量的数据。其中大部分数据目前处于休眠状态。它们很难被使用。有时候你必须对它执行大量的查询。也许你查询的是一个关系型数据库。但现在你可以拥有一个真正理解含义的数据库。因此你可以对数据库进行语义搜索。它会提取出你原本意图查询的信息。你获取该嵌入向量，并将其与你向模型输入的提示词结合进行增强。这样一来，伴随这个提示词的上下文、背景信息和增强信息就丰富得多了。

因此，现在真正变得十分普遍的是，由于能够理解你意图的大语言模型的存在，与应用程序交互变得非常简便。其次，所有这些现在可以被向量化的数据库，随后可用于增强提示词和查询。所以跨越整个公司的应用场景真的非常惊人。当然，一个有趣的场景是，如果你的公司有一个庞大的客户服务部门，客服代表们正在录入他们与客户的互动记录，无论是问题、投诉还是任何情况，或者你引导客户获得的帮助，所有这些都以某种方式记录在一个非常庞大的数据库中。但如果现在这个数据库被向量化了，你可以直接与数据库对话，那岂不是太神奇了？“人们最不满的事情是什么？”“我们开始看到哪些趋势？”“如果我们想改善公司的客户服务，可以采取的前两三项措施是什么？”你可以像与人交谈一样与你的数据库交谈。这真的很强大。
<details><summary>Original English</summary>
**JENSEN HUANG**: We're using AI to design our chips, to find optimal placements, to help us connect transistors into circuits, and help us optimize designs at a scale that isn't really possible before. We're starting to use AI to help us determine from a failure where the bug likely started from, which line of code was responsible for the bug. And so we're using generative AI to help us from everything from designing the chip, optimizing the chip, to understanding where the failures are. One of the most powerful things that's happening, of course, is that generative AI predicts the next-- as you know, it predicts the next word or the next letter, next word, next sentence, next paragraph. It predicts the next pixel. It predicts the next frame of a video. So it makes a prediction of the next thing. These predictions could hallucinate. And one of the really effective ways is to-- one of them, of course, is providing a lot of context, a lot of prompts that people do to set the background, set the context, precondition the model before you prompt it, before you ask it a question or before you ask it to do something. One of the things that's really useful is retrieval augmentation. And what that means is a database that, whether it's structured or unstructured, tabular or otherwise, that has been vectorized. Vectorizing or embedding a database requires you to learn the relationship between all the data among each other, just like you're learning the representation of the data that I was talking about before. And by learning the representation and learning the-- vectorizing the database, you could understand its meaning. And so what's really exciting now is that you could vectorize a database. You can connect it to a large language model. And that large language model essentially allows you to talk to your data. And every company has a ton of data in their company. Most of that data is now dormant. It is hard to use. Sometimes, you have to do a lot of queries on it. Maybe it's a relational database that you're doing a query on. But now you could have a database that actually understands meaning. And so you could do a semantic search into the database. It brings back out the information that you meant to query. And you take that embedding, and you augment that with the prompt that you're prompting the model with. And so now the context, the background information, the augmented information with this prompt, is much richer. And so the thing that is really quite generalized now is the ease of being able to interact with applications because of large language models that understand your meaning. And then, secondarily, all of these databases that you can now vectorize, which could then be used to augment the prompts and the queries. And so the applications across your company is really quite amazing. One of the fun things, of course, if you're a company with a large customer service department, and customer service agents are inputting their interactions with customers, whether it's problems or complaints or whatever it is, help that you're routing the customer through, all of that is somehow captured in a very large database. But wouldn't it be amazing if now that database was vectorized, and you can just talk to the database. What are the things that people are most upset about? What are some trends that we're starting to see? If we want to improve the customer service of our company, what are some of the top-- what are the top two or three things that you can do? You could talk to your database like you're talking to a person. And that's really powerful.
</details>

### 技术剧变下的组织敏锐度与第一性原理

**INTERVIEWER**: 那么我想在这里转换一下话题，谈谈2023年经营一家科技公司面临的一些挑战。首先，面对不断变化的对新产品、新服务的需求，你如何跟上步伐？你又如何打造一个能够想象未来并跟上如此巨大变化步伐的管理团队？
<details><summary>Original English</summary>
**INTERVIEWER**: So I want to shift here a little bit and talk about some of the challenges of running a tech company in 2023. And for starters, how do you keep up with constantly shifting demand for new products, for new services? And how do you build a management team that can imagine the future and keep pace with so much change?
</details>

**JENSEN HUANG**: 这个嘛，你必须去学习。首先，我们周围的人都是精通计算机科学和电气基础与底层领域的行家里手——他们可能是编译器专家，可能是芯片设计专家，可能是处理器设计专家，也可能是互连技术专家等等。所以你的公司各处都有专家，他们在各自的领域都是出类拔萃的。

与此同时，你希望你的公司尽可能保持敏锐。因此，随着公司规模越来越大，信息在组织内部自由流动而不被困在孤岛中的能力变得至关重要。尤其是当整个行业发展如此迅速时，你希望对可能来自某处的非常微弱的信号保持警惕。它可能是一篇意料之外的研究论文；它可能与数字生物学有关；也可能与机器人技术有关。而机器人技术的信息不知怎的能够被泛化，从而可能对我们训练聊天机器人有所帮助。强化学习这项技术最初发明是为了让火柴人活动、制作动画、活动手指之类的事情，以及玩游戏。但事实证明，人类反馈强化学习（RLHF）在微调大语言模型方面可能相当有用。

所以你希望能够看到邻近领域甚至无关领域的发展，并且能够以某种方式将其提炼归结回第一性原理，然后推演到其他领域的有用应用中。因此，这种从扎实基础与公司内部专业知识出发、保持对微弱信号的敏锐度、并能够追溯到第一性原理的基本能力至关重要。当你做出某些观察时，回到第一性原理去思考：为什么那很重要？原因是什么？与该现象相关的主导动力学规律是什么？然后，能够将它们泛化。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well. You got to learn. First of all, we're surrounded by people who are expert in the art, in the fundamental and the foundational parts of computer science and electrical-- they could be compiler experts, or they could be chip design experts, or they could be processor design experts or interconnect experts or so on and so forth. And so you've got experts all over your company. And they're the best in the field of what they do. Meanwhile, you want your company to be as alert as possible. And so the ability for information to be moving freely in your organization, without being trapped in silos, is something that's really important as the company gets larger and larger. Especially when the industry is moving so fast, you want to be alert of very weak signals that could be coming from somewhere. And so it could be a research paper that's coming out of left field. It could be related to a digital biology. It could be related to something in robotics. And somehow, that robotics information, it could be generalized in such a way that it could be useful for how we train a chat bot maybe. Reinforcement learning was something that was really invented for articulating, and animating stick figures, and articulating fingers, and things like that, and playing a game. But it turns out that reinforcement learning, human feedback, could be quite useful in fine tuning a large language model. And so you want to be able to see developments in adjacent fields or even unrelated fields and be able to somehow distill it back down to first principles and then extrapolate it to useful applications in other domains. And so that fundamental ability of starting from really good foundation, expertise in the company, the ability to stay alert of weak signals, and then being able to go back to first principles. When you make some observation, go back to first principles on, why is that important? And what is the reason? What are the governing dynamics associated with that phenomenon? And then, be able to generalize them.
</details>

### 地缘政治限制与中国市场竞争

**INTERVIEWER**: 还有影响你们业务的政治问题。我很想听你谈谈，英伟达如何应对在对华销售上蒙受我认为数十亿美元损失的局面，这部分是由于美国对向中国出口先进制程芯片施加限制所致。
<details><summary>Original English</summary>
**INTERVIEWER**: And then, you have the political issues that affect your business. I'd love to hear you talk about how NVIDIA is coping with the loss of I think it's billions of dollars in sales to China, partly as a result of US restrictions on sales of sophisticated chips to China.
</details>

**JENSEN HUANG**: 这个限制是性能规格限制，并不是绝对的全面禁令。这些限制与我们GPU的性能水平有关。这就像对CPU和计算机的限制一样，其历史可以追溯到很久以前。这些限制规管的是处理器的性能水平或可执行的计算量。因此，我们首先必须做的是遵守法规，明确限制标准是什么，并尽我们最大的能力，在市场上提供既能遵守限制规定、又能保持竞争力的产品来服务客户。

这里的挑战在于，本土市场，特别是在中国，有大量的竞争对手。因此我们必须在遵守出于国家安全考虑而制定的法规的前提下，在市场上参与竞争。所以这并不容易。这是一个巨大的挑战。竞争对手的动作非常迅速。所以这和其他事情一样，你必须保持敏锐，尽你所能做到最好。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well, the restriction is a capability restriction, is not an absolute restriction. The limitations are related to the performance levels of our GPUs. And this is like restrictions of CPUs and computers that has gone back a very long time. The restrictions limit the level of capability or the amount of computation that a processor can do. And so the first thing that we have to do is comply with the regulation, and understand what the limits are and, to the best of our ability, offer products in the marketplace to serve customers that can still be competitive while complying with the restrictions. And so the challenge there is that the local markets, especially in China, has a lot of competitors. And so we have to compete in the marketplace while, of course, complying with the regulations that are inspired by national security. And so it's not easy. And it's a great challenge. And the competitors are moving quickly. And so it's like anything else. You've got to stay alert and do the best you can.
</details>

**INTERVIEWER**: 听起来你的意思是你们不会放弃那个市场。你们正在允许的范围内寻找途径，如果我理解得没错的话，去创造新产品或探索进军该市场的新途径。这样说准确吗？
<details><summary>Original English</summary>
**INTERVIEWER**: So it sounds like you're saying you're not giving up on that market. You're finding ways within what's allowable, finding ways to, if I have you right, create new products or new approaches to that market. Is that fair?
</details>

**JENSEN HUANG**: 只有在新产品对客户持续具有吸引力的情况下才会如此。我们首先要做的是了解法规限制的内容。我们要做的第二件事是向市场推出客户可能仍会觉得有吸引力的产品。但没有任何保证。我是说，竞争对手正在想出各种各样吸引客户的方法。因此，我们将尽可能推出完全符合法规的最佳产品，以此为基础走一步看一步，观察客户是否依然被我们提供的产品所吸引。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well, only if the new products continues to be attractive to customers. The first thing that we have to do is understand what the regulation limits. And the second thing we do is go propose products to the marketplace that customers might still find attractive. But there's no guarantees. I mean, competitors are coming up with all kinds of ways to attract the customer. And so we'll float the best possible products that we can that are fully compliant with regulations, and take it from there, and see if customers are still attracted to the products that we offer.
</details>

### 自主系统安全、冗余与人机协作（Human in the loop）

**INTERVIEWER**: 明白了。好的，我现在想看一个观众提问。这个问题来自Steven。我不知道Steven身在何处，但他的问题是：你认为AI是否总是需要人类的监督？
<details><summary>Original English</summary>
**INTERVIEWER**: Got it. OK, I want to go to an audience question now. And this is from Steven. I don't know where Steven is. But the question is, do you think that AI will always need human supervision?
</details>

**JENSEN HUANG**: 人在回路（human in the loop）是相当重要的。如你所知，在机器人领域，你可以有不同级别的自主性。而在达到极高可靠性指标（大量个9的安全性）以及各种不同维度的安全保障之前，大多数自主级别都需要它。例如在自动驾驶汽车的情况下，如果你希望自动驾驶汽车能够在你全家在后座睡觉时完全自主地送达目的地，你需要相当有把握地确保传感器系统、计算系统、车辆控制系统等所有环节都具备多样性与冗余度。

因此举例来说，你可能会坚持确保既有摄像头，又有雷达，还有激光雷达。你甚至可能有冗余的转向控制、冗余的制动动力学系统等等。这些设置能让你确信，无论处于何种条件下，影响功能的关键部件都具有多样性和冗余度。在许多方面，多样性与冗余度是智能、自主智能的重要组成部分。

即使在公司内部，我们也有多样性和冗余度。请注意，我们在公司里经常谈论多样性，因为这让公司更具韧性。我们有冗余的方式来做同一件事，我们尝试从不同角度分析同一个问题。也许销售部门由市场部门做辅助补充，市场部门又由其他部门辅助补充等等。通过不同类型的方式来确保公司的活力和韧性。大多数自主系统，无论是一辆机器人汽车还是一个大型组织，都希望以具备多样性和冗余度的方式来进行设计。

然后，在此之上，你需要人在回路中。有时你达到了某个级别，认为车内不再需要人类参与；但也许你在车外设置了人在回路中，对有效性进行监控。这比如空中交通管制，并没有什么不同。你有两名飞行员，你也有冗余的自动驾驶系统，但你同时还有空中交通管制。飞行员之间还会相互关照留意。因此，自主系统为了最大程度的安全性和可靠性，有许多不同的设计方式。

这一套思考方式同样必须运用在生成式AI上。我们必须发明保障安全的技术。我们必须应用工程方法来设计安全的系统，以及确保安全性的验证系统。最后，在相当长的一段时间内，我们很可能会——不是可能，我们必然会有“人在回路”。例如，当你从下一批数据中学习时，在向全世界发布之前，你要安排人员进行验证、测试和红队对抗，而不是让它完全自行持续学习和持续更新。所以我们确保安全的方法有很多，人在回路就是最好的方式之一。
<details><summary>Original English</summary>
**JENSEN HUANG**: A human in the loop is pretty important. As you know, in robotics, you could have different levels of autonomy. And most of the levels of autonomy, until you have a great deal of nines, of safety, and safety in all kinds of different ways. So for example, in the case of a self-driving car, if you want the self-driving car to be able to take your family while they're sleeping in the backseat fully autonomously, you want to be fairly assured that the sensor system, the computing system, the vehicle control, all of it has diversity and redundancy. And so for example, you might insist on making sure that you have cameras, as well as radars, as well as lidars. You might even have a redundant steering control, and redundant braking dynamics, and so on and so forth. And these things give you assurance that, irrespective of the conditions, that the critical components that affects the functionality has diversity and redundancy. Diversity and redundancy is an important part of intelligence, autonomous intelligence, in a lot of ways. Even in companies, we have diversity and redundancy. Notice we talk a lot about diversity in companies because it allows the company to be more resilient. We have redundant ways of doing the same thing, where we're trying to analyze the same problem from different perspectives. Maybe the sales organization is augmented by the marketing organization, which is augmented by so on and so forth. And different types of ways to ensure the vibrancy and the resilience of the company. And most autonomous systems, whether it's a robotic car, or it's a large organization, wants to be designed in such a way that you have diversity and redundancy. And then, above that, you want you want human in the loop. Sometimes, you get to a level where you don't believe you need human in the loop inside the car. But maybe you have human in the loop outside the car. And you're monitoring the effectiveness. This is no different than air traffic control, for example. You have two pilots. You also have redundant autopilot systems. But you also have air traffic control. And pilots keep an eye out for each other. And so there's a lot of different ways that autonomous systems are designed for maximum safety and reliability. This is going to happen-- the same line of thinking will have to be done for generative AI. We have to invent the technologies for safety. We have to apply engineering methods that allows us to design systems that are safe, validation systems that ensure safety. And then, lastly, for quite a long time, we will likely-- we will not likely. We will surely have human in the loop. For example, while you're learning from the next batch of data, before you release it out into the world, you have humans validate it, and test it, and red team it instead of just have it be continuously learning and continuously updating all by itself. And so there are a lot of different methods that we ensure safety in. Human in the loop is one of the best ways.
</details>

### 英伟达的企业文化与危机意识

**INTERVIEWER**: 是的。我很想多了解一些英伟达的企业文化。你们的一位副总裁曾被引述说过：“在英伟达工作每天都感受到生存危机。我们觉得公司明天就要破产了。”所以我想知道，这是刻意为之的吗？你是试图灌输一种偏执感来激发创新吗？
<details><summary>Original English</summary>
**INTERVIEWER**: Yep. I'm interested in hearing more about NVIDIA's culture. One of your vice presidents was quoted as saying, "Working at NVIDIA feels existential every day. We feel like the company is going to go bankrupt tomorrow." So I wonder, is that deliberate? Do you try to instill a sense of paranoia to try to spur innovation?
</details>

**JENSEN HUANG**: 你不需要刻意去灌输它。如果你不认为自己身处险境，那很可能是因为你把头埋在了沙子里。没有任何公司能保证活下去。而我们的优势在于白手起家创办了这家公司，并且经历过——并非夸大其词的濒临倒闭，而是几次切切实实濒临倒闭的亲身经历。我们不必假装公司总是处在危险之中。公司确实时刻都处在危险之中，我们能感受到这一点。我和公司都不需要那种“我们一定会成功”的保证才能做到最好。

所以我认为，公司生存在抱负与绝望之间，生存在这个区间之内的某个位置，比永远乐观或永远悲观要好得多。因此，我认为保持适度的审慎乐观，并清醒现实地认识到公司随时可能陷入危险，我们必须保持专注和敏锐，尽全力做好工作，不断赢得继续经营的权利——我认为拥有这些感觉和这种清醒认识，对公司来说是非常有益且健康的。
<details><summary>Original English</summary>
**JENSEN HUANG**: You don't have to instill it. If you don't think you're in peril, it's probably because you have your head in the sand. There are no companies that are assured survival. And we have the benefit of having built the company from the ground up and having not exaggerated circumstances of nearly going out of business, actual experiences of nearly going out of business, a handful of times. We don't have to pretend that the company is always in peril. The company is always in peril. And we feel it. And I don't need, and the company doesn't need, assurance that we will do well in order to do our best work. And so I think the company living somewhere between aspiration and desperation, living somewhere within that spectrum, is a lot better than either always optimistic or always pessimistic. And so I think a guarded level of optimism and realistic understanding that the company could be in peril at any given time, and we have to stay focused and alert, and do our best work, and constantly earn the right to be in business. Those feelings and that sensibility, I think, is really good and healthy for companies to have.
</details>

### 扁平化管理哲学与复杂系统工程

**INTERVIEWER**: 据我所读到的资料，你的管理风格有些与众不同，你保持着非常扁平的组织架构，而且极少开一对一的会议。谈谈你的管理哲学吧。
<details><summary>Original English</summary>
**INTERVIEWER**: From what I've read, your management style is somewhat unusual, that you maintain a very flat organizational structure, that you have very few one-on-one meetings. Talk about your theory of management.
</details>

**JENSEN HUANG**: 组织架构的设立，是为了让公司能够开展工作，为了尽可能高效地运转。对于一家处于发展如此迅速的科技领域的公司来说，真正重要的事情之一是——我们发明了这项名为加速计算的技术，而在过去，摩尔定律——现在已经远远没有那么快了，但在过去的时代，摩尔定律会每5年将性能提高10倍，每10年提高100倍。但是在加速计算领域，我们在10年里推进了大概1,000到100,000倍。

所以当你前进得如此迅速时，你要确保信息尽可能快地在公司内部流动。你希望公司尽可能保持步调高度一致。而且，我们公司制造的是极其复杂的产品。人们以为我们的GPU就像我们为游戏玩家设计的插卡一样。它们确实是，我们以巨大的自豪感和喜悦制造它们。但是我们为AI制造的GPU重达70磅，拥有35,000个零件。在这些35,000个零件中，有8个来自台积电（TSMC）。它们消耗10,000安培电流。显而易见，它们非常重，你得用机器人来制造它们。而这些计算机是如此先进，以至于需要一台超级计算机来测试另一台超级计算机。

因此，我们正在制造的这些GPU极其复杂，运行它们需要大量的软件。对于像我们这样一家从底层芯片进行设计、打造系统、开发软件、制造所有网络和所有硅光子技术、并将其接入大型数据中心、协助各家公司搭建和运营这些基础设施的企业而言，公司的信息必须非常快速地在内部流动，切切实实做到没有壁垒、没有边界。

因此，我们构建了一套组织架构，使我们一方面能够跨越这一极其复杂的计算技术全栈开展工作，另一方面能够打造出不可思议的复杂产品，并且在以光速演进时感到非常自如。如果你想要建立这样一家公司，你最不希望看到的就是信息按层级逐级传递。如果纵观大多数组织，顶层只有两三个人。如果是从那种模式开始，那么在接触到真正在处理底层事实的人之前，中间的管理层级和各级经理可能会达到7层、8层、9层甚至10层。我不希望出现那种情况。所以实现这一目标的最佳方式，就是让最高管理层尽可能保持扁平。仅通过这样做，我们就可能从公司里减少了3到4个管理层级。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well, an architecture, an architecture is designed for the company to do its work, to operate as efficiently as possible. And one of the things that is really important for a company in technology that's moving as quickly as it is-- we invented this technology called accelerated computing, whereas Moore's law, in the past-- it's no longer nearly this fast. But Moore's law, in the older days, would increase performance by a factor of 10 every 5 years and a factor of 100 every 10 years. But in the case of accelerated computing, we're moving somewhere between 1,000 to 100,000 times every 10 years. And so when you're moving that fast, you want to make sure that information is flowing through the company as quickly as possible. You want the company to be as aligned as possible. And also, our company builds really complicated things. People think our GPUs are like the add-in cards that we designed for gamers. And they are. We build those with great pride and great joy. But the GPUs that we build for AI weigh 70 pounds. They have 35,000 parts. Out of those 35,000 parts, 8 of them come from TSMC. They consume 10,000 amps. Obviously, they're so heavy, you use robots to manufacture them. And the computers are so advanced that it takes a supercomputer to test another supercomputer. And so these GPUs that we're building are insanely complex. And it requires a lot of software to run it. And for a company like us that designs the fundamental chips, creates the systems, create the software, and creates all the networking and all the silicon photonics, and connect it into a large data center, and help companies stand it up and operate it, our company information has to really move quickly through the company and really, really have no barriers and no boundaries. And so we architected a company that allows us to be able to work across this really complicated stack of computing technology on the one hand, build incredibly complicated things on the other hand, and be very comfortable moving at light speed. And if you want a company like that, then the last thing you want is for information to pass along hierarchically. And if you look at most organizations, there are only 2 or 3 people at the top. And if that starts that way, then the number of layers of management and layers of managers before you get to somebody who is actually dealing with ground truth could be 7, 8, 9, 10 layers. And I didn't want that to happen. And so the best way to do that is to put the most-- at the highest level to be as flat as possible up there. And so we probably reduced 3 or 4 layers of management out of our company just by doing so.
</details>

### 量子计算展望与结语

**INTERVIEWER**: 好。我们还有时间再回答一个简短的问题。我想再引入一个观众的问题。这个问题来自Leon。问题是：关于量子计算你能谈谈什么？你们在多大程度上进行了投资？关于这一点你有什么看法？
<details><summary>Original English</summary>
**INTERVIEWER**: Yeah. So we have time for one more quick question. I wanted to bring in one more audience question. This is from Leon. And the question is, what can you say about quantum computing? To what extent are you investing in it? And what can you say about that?
</details>

**JENSEN HUANG**: 为了制造世界上下一代速度更快的计算机，你需要世界上运行速度最快的计算机来帮助你完成设计、仿真并为其创建新算法。而世界上速度最快的计算机就是英伟达的加速计算系统。因此我们并不制造量子计算机，但我们与量子计算生态系统中的几乎所有人合作，从从事基础量子计算设计的人员、算法开发人员，到研究经典-量子计算机架构的架构师。我们几乎与那里的每一个人都有合作。

量子计算机要真正实现工业化应用可能还要再过10年，甚至20年。当它到来时，它很可能会成为连接到英伟达加速计算系统上的一个加速器。部分计算将在量子计算机上完成，而大量的计算将继续在经典计算机上进行，用于执行前处理、后处理等等。因此，我非常期待量子计算机变得有用且高效的那一天。而当那一刻到来时，经典计算机，特别是加速计算和AI，将成为其中非常重要的组成部分。
<details><summary>Original English</summary>
**JENSEN HUANG**: Well, in order to build the world's next fast computer, you need the world's fastest computer to help you design it, simulate it, create new algorithms for it. And the world's fastest computer is NVIDIA's accelerated computing systems. And so we don't build quantum computers. But we work with just about everybody in the quantum computing ecosystem, from people who are doing the basic quantum computing design, to algorithm developers, to architects who are working on classical quantum computers, architectures. And so we work with just about everybody out there. The quantum computer won't come along in a real industrial way for probably another decade, and maybe 2. And when it gets here, it'll likely be an accelerator that's connected to the NVIDIA accelerated computing systems. And some of the computation will be done on quantum computers. And a lot of the computation will be done on classical computers doing preprocessing, postprocessing, and so on and so forth. And so I'm looking forward to when quantum computers are going to be useful and effective. And when it comes, classical computers, and particularly, the accelerated computing and AI, will be a very big part of it.
</details>

**INTERVIEWER**: 好的，我们的时间到了。黄仁勋，非常感谢你今天来到HBR Live与我们交流。
<details><summary>Original English</summary>
**INTERVIEWER**: All right, so we're out of time. But Jensen Huang, thank you very much for being here with us today on HBR Live.
</details>

**JENSEN HUANG**: 我很高兴来到这里。非常感谢。
<details><summary>Original English</summary>
**JENSEN HUANG**: I'm delighted to be here. Thanks a lot.
</details>

**INTERVIEWER**: 好的。
<details><summary>Original English</summary>
**INTERVIEWER**: OK.
</details>