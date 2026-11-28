---
author: Latent Space
date: '2026-02-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=V7_Ec2WFAWs
speaker: Latent Space
tags:
  - material-discovery
  - generative-ai
  - stochastic-thermodynamics
  - inductive-bias
  - climate-tech
title: 专访 Max Welling：AI for Science 时代，材料创新是万物之基
summary: 深度学习先驱 Max Welling 在访谈中探讨了他从理论物理转向 AI for Science 的历程，重点介绍了新创公司 CuspAI 如何利用生成式 AI 和物理模拟加速材料研发，以应对气候变化。他还深入解析了等变性（Equivariance）在神经网络中的核心作用，并分享了其即将出版的关于生成式 AI 与随机热力学数学统一性的新书观点。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Max Welling
companies_orgs:
  - CuspAI
  - OpenAI
products_models:
  - Variational Autoencoders
  - Graph Neural Networks
  - GPT-4o
media_books:
  - Generative AI and Stochastic Thermodynamics
status: evergreen
---
### 物理处理单元：让自然进行计算

**Max Welling**: 我想把它看作是一种我称之为**物理处理单元（Physics Processing Unit, PPU）**的东西。就像我们有数字处理单元（DPU）一样，现在也有了物理处理单元。

<details>
<summary>Original English</summary>

**Max Welling**: I want to think of it as what I would call a sort of a physics processing unit like a PPU, right? Which is you have digital processing units and then you have physics processing units.

</details>

**主持人**: 所以这基本上是利用大自然为你进行计算。它是目前已知的、甚至是可能存在的最快的计算机。

<details>
<summary>Original English</summary>

**Host**: So it's basically nature doing computations for you. It's the fastest computer known possible even.

</details>

**Max Welling**: 确实。虽然它很难编程，因为你必须进行所有的实验，而且体积非常庞大，你需要做很多准备工作。但在某种程度上，这就是一种计算，这就是我想要看待它的方式。你可以在数据中心进行计算，也可以要求大自然帮你做一些计算。虽然与大自然的接口比较复杂，但这些环节必须无缝协作，才能最终获得你感兴趣的**新材料**。

<details>
<summary>Original English</summary>

**Max Welling**: Uh it's a bit hard to program because you have to do all these experiments also quite quite bulky. It's like a very large thing you have to do. But in a way it is a computation and that's the way I want to see it. You can do computations in a data center and then you can ask nature to do some computations, right? Your interface with nature is a bit more complicated, but then these things will have to seamlessly work together to get to a, you know, a new material that you're interested in.

</details>

### 从量子引力到社会影响力

**主持人**: 今天非常荣幸邀请到 **Max Welling** 作为嘉宾。Max 在职业生涯中做了很多让我感到兴奋的工作。如果你身处深度学习社区，你可能因为他在**变分自编码器（Variational Autoencoders, VAE）**方面的工作而认识他，这项工作经受住了时间的考验。如果你是一名科学家，你可能知道他在**图神经网络（Graph Neural Networks）**和**等变性（Equivariance）**方面的开创性工作。如果你从事材料科学，你可能听说了他的新创业公司 **CuspAI**。Max 有着解决各种酷炫问题的悠久历史。你最初是从**量子引力（Quantum Gravity）**开始的，这与你后来做的其他事情非常不同。对于 AI 工程师和科学家来说，你思考问题的核心主线是什么？什么样的事情会让你兴奋？你是如何决定下一个要研究的大方向的？

<details>
<summary>Original English</summary>

**Host**: Yeah, it's a pleasure to have Max Welling as a guest today. Max has done so much over his career that I've been so excited about. If you're in the deep learning community, you probably know Max for his work on variational autocoders, which has literally stood the test of time or officially stood the test of time. If you are a scientist, you probably know him for his pioneer work on graph neural networks on equivarians. And if you're a material science, you probably know about his new startup, CuspAI. Max has a long history doing lots of cool problems. You started in quantum gravity which is I think very different than all of these other things you worked on. The first question for AI engineers and for scientists what is the thread in how you think about problems? What is the thread in the type of things which excite you and how do you decide what is the next big thing you want to work on?

</details>

**Max Welling**: 这种思考方式其实演变了很多。年轻时，我只是追随那些我觉得超级有趣的事情。我有一种感应器，我想很多人都有，但可能并不常使用——当你对某个问题感到非常兴奋时，你会有一种直觉。比如黑洞内部是什么？宇宙的边界在哪里？或者量子力学究竟是怎么回事？我职业生涯的大部分时间都在追随这些问题。但不得不说，随着年龄增长，情况发生了一些变化。

一个新的维度加入了进来，那就是**影响力（Impact）**。研究二维量子引力，几乎可以肯定你所做的对现实世界没有任何影响，除了发表几篇论文，在这个能量尺度上的世界里什么都不会改变。随着我接近退休（幸运的是还有 10 年左右），我确实想对世界产生积极的影响。我对**气候变化**感到非常担忧。我认为政治在解决这个问题上遇到了困难，尤其是现在，所以我认为最好从技术层面来入手。这就是我们创办 CuspAI 的原因。但材料科学中也有很多非常有趣的科学问题，所以它是将个人影响力与有趣的科学相结合。一方面研究那些让你觉得“哇，这里面有很深奥的东西”的课题，另一方面尝试构建能够对世界产生真正影响的工具。

<details>
<summary>Original English</summary>

**Max Welling**: So it has actually evolved a lot. Um in my young days let's prove I would just follow what I would find like super interesting. I have kind of this sensor I think many people have but maybe not really uh sort of use very much which is like you get this feeling about getting about very excited about some problem right like it could be you know what's inside of a black hole or what's you know at the boundary of the universe or you know what what is quantum mechanics actually all about and so I followed that basically throughout my career but I have to say that as you get older this changes a little bit in a sense that there's a new dimension coming to it and this is impact. Working in two-dimensional quantum gravity, you pretty much guaranteed there's going to be no impact on what you do relative, you know, maybe a few papers, but not in the in this world at this energy scale. As I get closer to retirement, which is fortunately still, you know, 10 years away or so, I do want to kind of make a positive impact in the world. And um I got pretty worried about climate change. Um I think we and um I think we should you know and politics seems to have a hard time solving it especially these days and so I thought better work on it from the technology side and that's why we started cosplay but there's also a lot of really interesting science problems in you know material science um and so it's kind of combining both the impact you can make with it as well as the interesting science so it's sort of these two dimensions like working on things which you feel is like, wow, there's something very deep going on here and on the other hand trying to build tools that can actually make a real impact in the world.

</details>

### 物理学：贯穿 AI 与科学的线索

**主持人**: 当我回顾你研究过的不同领域时，有些似乎是预先关联的，比如物理学与等变性、图神经网络，这些似乎又与 CuspAI 相关。这其中有一条主线吗？

<details>
<summary>Original English</summary>

**Host**: So the the thread that when I look back look at the different things you worked some of them seem preconnected like the physics to to equivariance and yeah and uh graph neural networks maybe and that that seems to be somewhat related to cusp. Do you have a a thread through there?

</details>

**Max Welling**: 是的，我认为**物理学**就是那条主线。在理论物理领域投入了大量时间后，我发现这里既有非常基础且令人兴奋的问题（比如量子引力中尚未解决的前沿问题），也有大量可以利用的数学工具。例如，在粒子物理和广义相对论中，**对称空间（Symmetry Space）**起着极其重要的作用，甚至延伸到了规范对称性（Gauge Symmetries）。

将这些对称性应用于机器学习，我一直认为是一个非常深刻且有趣的数学问题。我和 **Taco Cohen** 一起做了这项工作，他是主要的推动者，我们将研究从简单的旋转对称性一直延伸到球体上的规范对称性等等。还有 **Maurice Weiler**，他曾是我的博士生，他写了一整本关于对称性在 AI 和机器学习中作用的书，我非常推荐，我认为这是一个非常深奥且有趣的问题。

最近，我走了一条略有不同的路径，即研究**扩散模型（Diffusion Models）**与**随机热力学（Stochastic Thermodynamics）**之间的关系。热力学通常是关于平衡态的理论，但随机热力学是为非平衡系统定义的。事实证明，我们用于扩散模型、强化学习、薛定谔桥（Schrödinger Bridges）以及 MCMC 采样的数学，与非平衡系统的物理理论有着相同的数学基础。这让我非常兴奋。我在南非开普敦附近的非洲数学科学研究所授课时，将这些内容整理成了一本书。两年后，书写完了，已经寄给了出版社。这本书主要讨论了自由能、扩散模型（基本上就是生成式 AI）与随机热力学之间的深层联系。

物理学总是让我感到很深奥。我也经常思考量子力学，这是一个极其诡异的理论，实际上没有人真正理解它。这里有一个有趣的故事，可以将我的博士阶段和现状联系起来。我的博士导师是诺贝尔奖得主 **Gerard 't Hooft**，他是我见过最聪明的人，在我印象中他从未在任何事情上错过。而现在他说量子力学是错的，他提出了一套新的量子力学理论。尽管他写下的数学并不复杂，但没人理解他在说什么。他在正面挑战量子力学的“可理解性”。我发现这非常有勇气，也完全被它吸引了。所以我也在尝试思考：我能否以一种更平凡的方式理解量子力学，而不去涉及那些诡异的多重宇宙或波函数坍缩之类的东西？物理学始终是那条主线，我正尝试将物理学应用于机器学习，以构建更好的算法。

<details>
<summary>Original English</summary>

**Max Welling**: Yeah, I think physics is the thread. So, having done, you know, spent a lot of time in theoretical physics, I think there's first very fundamental and exciting questions like things that haven't actually been figured out in quantum gravity. So, there's really the frontier, but there's also a lot of mathematical tools that you can use, right? In for instance, in particle physics, but also in general relativity, sort of symmetry space play an enormously important role. And this goes all the way to to gauge symmetries as well. And so applying these kinds of symmetries to uh machine learning was actually you know I thought of it as a very deep and interesting mathematical problem. I did this with Taco Cohen and you know Tacoan was the main driver behind this went all the way from just simple like rotational symmetries all the way to gauge symmetries on spheres and stuff like that. So and Maurice Wiler who's also here um when he was a PhD student with me you know he wrote an entire book which I can really recommend about the role of symmetries in in AI and machine learning that I find is a very deep and interesting problem. So more recently so I've taken a sort of different path which is the relationship between diffusion models and and a field called stoastic thermodynamics. This is basically the thermodynamics which is a theory of equilibrium. So but then formulated for out of equilibrium systems and it turns out that the mathematics that we use for diffusion models but even for reinforcement learning for shinger bridges for MCMC sampling has the same mathematics as this theor this physical theory of non-equilibrium systems and that got me very excited and actually uh when I taught a course in Ma it is South Africa close to Cape Town at the African Institute for Mathematical Sciences as I turned that into a book. So two years later the book is finished. I've sent it to the publisher and this is about the deep relationship between free energy diffusion models basically generative AI and stoastic thermodynamics. So it's always some kind of I don't know I find physics very deep. I also think a lot about quantum mechanics and it's it's it's a completely weird theory that actually nobody really understands and there's a very interesting story which is maybe good to tell to connect sort of my my PhD back to where I am now. So um I did my PhD with a noble laureate to he brilliant man I've ever met. He was never wrong about anything as long as I've seen him and now he says quantum mechanics is wrong and he has a new theory of quantum mechanics. Nobody understands what he's saying, even though what he's writing down is not mathematically very complex. But he's trying to address this understandability, let's say, of quantum mechanics head on. I find it very courageous and I'm completely fascinated by it. So I'm also trying to think about, okay, can I actually understand quantum mechanics in a more mundane way sort of, you know, without all the weird multiveres and collapses and stuff like that. So the physics is always been the threat and I'm trying to apply the physics to the machine learning uh to to build better algorithms.

</details>

### AI for Science：一场正在爆发的新学科

**主持人**: 所以你仍然非常投入于理解物理和世界。

<details>
<summary>Original English</summary>

**Host**: You are still very involved in understanding and understanding physics and the world.

</details>

**Max Welling**: 是的。虽然我不能说我对物理学贡献了很多，但我对物理学与科学的接口做出了贡献，这被称为 **AI for Science**。这实际上是一门正在兴起的新学科。它不仅是在兴起，我更愿意用“爆发”这个词来形容。

因为我知道，这一领域的投资已经从几亿美金增长到现在的几十亿。现在甚至有一家由 **Jeff Bezos** 支持的创业公司，C 轮融资就达到了 62 亿美金。这太疯狂了，我想这可能是有史以来规模最大的创业公司，而它正处于 AI for Science 领域。这说明我们正在创造一个新的领域，或者说是一个“新机遇”。

<details>
<summary>Original English</summary>

**Max Welling**: Yes. So I would say I'm I'm not I'm not contributing much to physics but I'm contributing to the interface between physics and science and that's called AI for science or science or AI is kind of a super it's actually a new discipline that's emerging. Um and it's not just emerging it's exploding I would say that's the better term because I know you go from investments into like in the hundreds of millions now in the billions. So there's now actually a startup by Jeff Bezos that you know that 6.2 two billion C round right it's like insane like this is the largest you know startup ever I think right and that's in this field AI for science like it tells you something that we are creating a new bubble here right

</details>

**主持人**: 那你认为是什么发生了变化，促使人们开始致力于解决 AI for Science 类型的问题？

<details>
<summary>Original English</summary>

**Host**: so so why do you think it is what has changed that has like motivated people to start working on AI for science type problems

</details>

**Max Welling**: 实际上有两个原因。一是人们一直很自然地将 AI 的新工具应用于科学领域。有两个显著的例子：**蛋白质折叠（Protein Folding）**是一个重大突破；另一个是**机器学习力场（Machine Learning Force Fields）**，有时也称为机器学习原子间势能。这两者都非常成功，而且有趣的是，它们都与对称性有关。

此外，AI 领域的专业人士看到了机会，可以将他们开发的工具应用到广告位投放或多媒体应用之外的领域，进入那些能对社会产生积极影响的领域，比如医疗、药物开发、能源转型的材料、**碳捕捉（Carbon Capture）**。这些都是非常酷且具有影响力的应用。

除此之外，科学本身也非常有趣。这两大领域正在汇合，我们现在已经到了可以有效模拟这些现象、并能显著改进科学方法论的节点。这是一个非常独特的时刻，人们意识到我们正处于新事物的尖端（Cusp）。这也是我们公司名字的由来（CuspAI）。我们正处于新事物的门槛上，这自然会产生巨大的能量。就像是一片处女地，一片绿地，没人去过，我可以冲进去开始“收获”。我认为这就是该领域如此狂热的原因。

<details>
<summary>Original English</summary>

**Max Welling**: so there's two two reasons actually the one one is that people have been applying sort of the tool the new tools from AI to the sciences which is quite natural and there's of course I think there's two big examples you know protein folding is or is a big one and the other one is machine learning force fields or sometimes called machine learning intra atomic potentials both of these have been actually very successful both also had something to do with symmetries which is also cool and sort of people in the AI sciences saw an opportunity to apply the tools that they had developed beyond advertise placement right or you know multimedia applications um into something that could actually make a very positive impact in society like health, drug development, materials for the energy transition, carbon capture, these are all really cool, you know, impactful applications. Beside that the science and the kind of the is also very interesting and sort of the I would say the um the fact that these sort of these two fields are coming together and that we're now at the point that we can actually model these things effectively and move the needle on some of these uh sort of science uh sort of methodologies is also a very unique moment I would say and people recognize that okay now some we're at the cusp of something new which is also whether That's where also what the company is called after. We we're at the cusp of something new and of course that always creates a lot of energy. It's like, okay, there's something. It's like sort of virgin field, right? It's like nobody's green field. Nobody's been there, you know? Um, I can rush in and I can sort of start harvesting there, right? And uh and I think that's also what's causing a lot of sort of enthusiasm in the fields.

</details>

### 材料：数字世界的物理根基

**主持人**: 如果是一个没有深厚科学背景但对此感到兴奋的 AI 工程师，他们该如何参与进来？

<details>
<summary>Original English</summary>

**Host**: If you're an AI engineer... and you maybe don't have a strong science background, but are excited... how does somebody who is not a scientist on a day-to-day basis how do they get involved?

</details>

**Max Welling**: 等我的书出版了，他们可以读读我的书。但说正经的，这意味着我们需要在这些交叉领域建立课程。我不确定，但可能已经有一些大学开设了相关课程，或者你可以找一些在线课程。我们现在参加的这些研讨会也非常好。我曾建议在研讨会开始前增加更多教程，比如先进行一个小时的教程，让人们能够进入这个领域。虽然目前大部分内容还比较难理解，但我认为未来会出现更多易于理解的书籍和内容，包括这个播客。现在视频网站上也有海量的相关内容可以观看。

<details>
<summary>Original English</summary>

**Max Welling**: Well, they can read my book once it's out. But um this is basically saying that there is more. We should create curricula that are on this interface. So I'm not sure there is possibly already some universities actual courses you can take, maybe online courses you can take. These workshops where we are now are actually very good as well. And we should probably have more tutorials before the workshop starts. Actually we've I've kind of proposed this at some point. and it's like maybe first have an hour of a tutorial so that people can get new into the field. But yeah, there's a lot out there. Um most of it is of course inaccessible but I would say um we will create much more books and other content that is more accessible including this podcast I would say right so um I think you know it will come and you know these days you can watch videos and things there's a huge amount of content you can you can go and uh and see

</details>

**主持人**: 追问一下，为什么人们应该参与进来？我们的听众很多对 AI 工程感兴趣，但他们可能在寻求对世界产生更大的影响。AI for Science 提供了哪些纯数字世界无法提供的机会？

<details>
<summary>Original English</summary>

**Host**: so maybe a followup to that... why should they get involved... what opportunities does AI for science provide them to make an impact to you know change the world that working in this the world of pure bits would not.

</details>

**Max Welling**: 我的观点是：**几乎一切事物的底层都是材料**。我们现在非常关注 **大语言模型（LLM）**，这属于软件层。但如果你深入思考，一切的基础都是材料。LLM 的底层是 **GPU**，而 GPU 的底层是**晶圆（Wafer）**，你必须在上面沉积材料。

为了制造 GPU，你需要在晶圆上铺设材料，并用**极紫外光（EUV）**照射以刻蚀结构。这就是一个纯粹的材料学问题，因为我们已经接近了物理缩小的极限，现在的提升主要靠新材料。我们需要快速实现能源转型，否则会毁掉这个世界。比如**电池**，这是一个彻底的材料问题。还有燃料电池、太阳能电池板。现在人们正在硅层上增加新的**钙钛矿（Perovskite）**层，理论上可以捕获 50% 的光能，而现在我们大约只有 22%。

这些巨大的变革完全依赖于**材料创新**。无论你研究什么，如果挖得足够深，我都能告诉你，你所做工作的最底层其实是一个材料问题。在最基础的层面工作是非常美妙的。而且，我们现在可以开始搜索这个“材料空间”了，这在以前是做不到的。过去科学家的工作方式是阅读论文、提出假设、做实验、学习，这个过程非常缓慢。现在我们可以像搜索互联网一样搜索材料空间，不仅是人类制造过的，甚至是宇宙中所有可能的分子。我们可以实现全自动化。我们的愿景是把它变成一个工具：你输入你想要的东西，系统开始运转，实验开始进行，最后产出一份材料清单。然后你查看清单，如果不满意，就微调你的查询。这种基于搜索引擎的科研模式，背后是海量的计算和实验，在遥远的实验室或数据中心进行。这是一个非常光明的前景，可以让我们建立一个更可持续的材料层，解决塑料污染等问题——比如发明一种能在几周内自动降解并转化为肥料的塑料。这些并非不可能。

<details>
<summary>Original English</summary>

**Max Welling**: So so my view is that um underlying almost everything is a material. So we we're focusing a lot on LLMs now. Yeah. Which is kind of the software layer. But I would say if you think very hard underlying everything is a material. So underlying an LLM is a GPU and underlying a GPU is a wafer on which we would we will have to deposit materials... Underlying everything is a material. So I was saying you know there's the LLM underlying the element is a GPU on which it runs and then in order to make that GPU uh you have to put materials down on a wafer and sort of shine on it with sort of EUV light in order to etch kind of the structures in but that's now an actual material problem because more or less we've reached the limits of you know scaling things down and now we are trying to improve further by new materials. So that's a fundamental materials problem. We need to get through the energy transition fast if we don't want to kind of mess up this world. And so there is for instance batteries. That's a complete materials problem, right? There's fuel cells. Um there is solar panels. So that they can now make solar panels with new perovsky layers on top of the silicon layers that can capture, you know, theoretically up to 50% of the light where now we're at I don't know maybe 22 or something, right? So, so these are huge changes all by material innovation and um yeah, I think wherever you go, you know, I can probably dig deep enough and then tell you well actually the very foundation of what you're doing is a material problem. And so I think it's just you very nice to work on this very very foundation and ex also because I think this is maybe also something that's happening now is we we can start to search to this material space. This is this this has never been the case, right? It's like scientists were the the normal way of working is you read papers and then you come up with an hypothesis you do an experiment and you learn etc. So there's a very slow process. Now we can treat this as a as a search engine like we search the internet we now search the space of all possible molecules not just the ones that people have made or they're in the universe but all of them right and and and we can make this kind of fully automated. That's the hope right? You can just type it becomes a tool where you type what you want and something starts spinning and some experiments get going right and then you know outcome a list of materials and then you look at it say maybe not and you refine your query a little bit and you kind of do research with this search engine where a huge amount of computation is and and experimentation is happening you know somewhere far away in some lab or some data center or something like this. I find this a very very promising view of how we can sort of come you know build a much better sort of materials layer underneath almost everything and also a more sustainable materials or plastics are polluting the planet if you can come up with a plastic that kind of destroys itself you know after I don't know a few weeks right and actually becomes a fertilizer these are these are things that are not impossible at all these things can be done right and we should do it

</details>

### CuspAI：加速材料发现的平台

**主持人**: 能给我们介绍一下 **CuspAI** 吗？

<details>
<summary>Original English</summary>

**Host**: can you tell us what a little bit just generally about custoi and And we I have ton of questions.

</details>

**Max Welling**: CuspAI 成立于大约 20 个月前，初衷是我对气候变化的担忧。我意识到，为了将全球升温控制在 2 度以内，我们不仅需要在 2050 年前实现净零排放，在接下来的半个世纪甚至一个世纪里，还必须从大气中移除二氧化碳，其速率大约是目前排放率的一半。这目前还是个未解之谜，如果不解决，升温将远超 2 度，情况会非常糟糕。

所以这套技术必须被开发出来。我和联合创始人 **Chad Edwards** 认为时机已经成熟。目前我们已经成长到约 40 人，筹集了 1.3 亿美金的投资，对于一家欧洲公司来说，这已经很多了。我们构建了一个平台，目前针对一系列材料类别，并且正在不断扩展。随着 LLM 的加入，整个过程变得越来越自动化。我们现在正转向**高通量实验（High-throughput Experimentation）**，将计算平台与实际实验连接起来，以便从实验中获得快速反馈。

我把实验看作是一个环节的终点，但我更想把它看作是“物理处理单元（PPU）”。你有数字处理单元，也有物理处理单元。这本质上是让大自然为你进行计算。虽然它很难编程，体积庞大，但它本质上就是一种计算。你可以在数据中心做计算，也可以要求大自然做计算。虽然接口复杂，但它们必须无缝协作才能获得新材料。这就是我们的愿景。我不想用“超级智能”这个词，因为我不知道它具体指什么，也不想过度推销，但我确实想自动化这个过程，并为化学家和材料科学家提供极其强大的工具。

<details>
<summary>Original English</summary>

**Max Welling**: Yeah. So, Kaspi started about 20 months ago and it was because um I was worried about I'm still worried about climate change and so I realized that in order to get you know to to stay within two degrees let's say we would not only have to reduce our emissions to zero by 2050 but then you know another half century or even a century of removing carbon dioxide from the atmosphere not by reducing your emissions but actually removing it at a rate that's about half the rate that we now emit it and that is a unsolved problem but and if we don't solve it 2° is not going to happen right it's going to be much more and I don't think people quite understand how bad that can be like four degrees like very bad so um so this technology needs to be developed and so this was uh my and my co-founder Chad Edwards um motivation to start this startup and also because you know we saw the technology was ready which is also very good so we're you know the time is right to do it and uh yeah so we now in in the meanwhile we've grown to about 40 people we've kind of collected 130 million investment uh in the into the company which is for a European company is quite a lot I would say it's interesting that right after that you know other startups got even more so that's kind of tells you how fast this this this is growing but yeah we are we are now at the So we've built the platform of course but uh it's it's for a series of material classes and it needs to be constantly expanded to new material classes and it can be more automated because you know we know putting LLMs in and so the whole things gets more more and more automated and now we're moving to sort of high throughput experimentation so connecting the actual platform which is computational to the experiments so that you can get also get fast feedback from experiments and I kind of think of experiments as something you do at the end. Although that's what we've been doing so far. I want to think of it as what I would call a sort of a physics processing unit like a ppu, right? Which is you have digital processing units and then you have physics processing units. So it's basically nature doing computations for you. It's the fastest computer known possible even. Uh it's a bit hard to program because you have to do all these experiments. It's also quite quite bulky. It's like a very large thing you have to do. But in a way it is a computation and that's the way I want to see it. So I want to you can do computations in a data center and then you can ask nature to do some computations right your interface with nature is a bit more complicated but then these things will have to seamlessly work together to get to a you know a new material that you're interested in. And that's that's the vision we have. You don't say super intelligence because I don't quite know what it means and I don't want to oversell it but I do want to automate this process and give a very powerful tool in the hands of the chemist and the material scientists.

</details>

### 人在回路：赋能专家而非取代

**主持人**: 能谈谈你们的平台是如何运作的吗？你们在开发过程中的思路是什么？

<details>
<summary>Original English</summary>

**Host**: can you talk about your platform... explain kind of how it works and like what you your thought processes was in developing it.

</details>

**Max Welling**: 实际上，设计过程并不是什么“高深科技（Rocket Science）”。我最初写下的设计方案至今基本没变。当然，我们增加了一些细节，比如最初我没怎么考虑**多尺度模型（Multiscale Models）**，但后来发现这非常重要。起初我也没怎么想过**自动驾驶实验室（Self-driving Labs）**，但现在我们正处于添加这一环节的阶段。

简单来说，平台包含一个经过训练用于生成候选材料的**生成式组件（Generative Component）**，以及一个**多尺度、多保真度的数字孪生（Digital Twin）**。你会按阶梯进行筛选：先做成本低的计算，剔除明显无用的东西，然后再进行昂贵的模拟，最后缩小到少数几个候选对象进入实验环节。

最近我们还增加了一些 **Agentic（智能体）** 部分。我们有 Agent 专门搜索化学文献并提出实验建议，还有 Agent 自主编排所有需要的计算和实验。这些工具处于不同的成熟阶段。

真正的**护城河**在于你能获取的数据，以及构建平台本身。我想特别提到 Felix Hunker，他负责平台的科学部分，还有 Alessandro de Maria，他负责 MLOps 部分。最近 **Aaron Walsh** 也加入了我们担任首席科学官。我们还有一个合伙人团队。把一种材料带入现实世界极其复杂，必须与领域专家（通常是各大公司）合作。因此，我们只有在找到优秀的工业合作伙伴后，才会投入某个方向的研发。

<details>
<summary>Original English</summary>

**Max Welling**: Yeah, actually it's been surprisingly it's not rocket science. Yeah, I would say it's not rocket science in the sense of the design and basically the design that you know I wrote down at the very beginning. It's still more or less the design. Although you add you add things like I I wasn't thinking very much about multiscale models and come on our radar that actually multiscale is very important. In the beginning I wasn't thinking very much about self-driving labs but now I think you know we that's we are now at the stage we should be adding that. So there is sort of bits and details that we're adding but more or less it's what you see in the slide decks here as well which is there's a generative component that you have to train to generate candidates and then there is a digital twin multiscale multifidelity digital twin uh which you walk through the steps of the ladder you know that they do the cheap things first you weed out everything that's obviously unusful and then you go to more and more expensive things later um and so you narrow things down to a small number those go into an experiment, you know, do the experiment, get feedback, etc. Now, things that also have been more recently added is sort of more agentic uh sort of parts. You know, we have agents that search the literature and come up with, you know, actually the chemical literature and come up with, you know, chemical suggestions or for doing experiments. We have agents which sort of autonomously orchestrate all of the computations and the experiments that need to be done. you know they're in various stages of maturity and they can be continuously improved I would say and so that's basically I don't I think that part is rocket science you know the design of that thing is not like surprising but is is surprising hard to actually build it right so that's that's the thing that is where the mo the moat is in the data that you can get your hands on and the and actually building the platform and and I would say there's two people in particular I want to call out which is Felix Hunker who is actually you know building the scientific part of the platform and Alessandro de Maria who is building the sort of the SCA the kind of this the MLOps part of the platform. Yeah. And so and and recently uh we also added um sort of Aaron Walsh to our team who is a a very accomplished scientist from Imperial College. We're very happy about that. he's going to be our chief science officer and uh we also have a partnerships team that sort of seeks out all the customers because I think this is one thing I find very important in princ it's so complex to do to actually bring a material to the real world that you must do this you know in collaboration with uh sort of the domain experts which are the companies typically so we always we only start to invest in a direction if we find a good uh industrial partner to go on that journey with us

</details>

**主持人**: 在平台演进过程中，你发现是更需要人工干预，还是在逐渐移除人工？

<details>
<summary>Original English</summary>

**Host**: over the evolution of the platform. Did you find... that human intervention... did you start out with having human feedback lots of steps and then like kind of figure out ways to remove you know

</details>

**Max Welling**: 是后者。我们构建工具，工具是非常模块化的。在工作流开始时，很多操作是手动的：先运行这个工具，再运行那个。然后你会发现，哦，这种多孔材料一晃动就会坍塌。于是你增加一个新工具来测试稳定性。随着工具越来越多，你会构建一个智能体（可能是贝叶斯优化器，或者是训练有素的化学 LLM），它会以正确的方式和顺序调用这些工具。

但在最开始，是由化学家把工作流组合在一起的。然后你再考虑如何自动化。例如，一个不懂 **DFT（密度泛函理论）** 的人想做计算，以往必须去找专家。我们能否把这部分自动化？让系统变得足够友好，能针对特定问题选择正确的参数和计算时长。你先自动化一个个小环节，然后是更大的环节，最后整个过程就自动化了。

但我并不认为化学家和领域专家会很快从流程中消失。这更像是一个退却的过程。最初需要专家精确设置参数，后来我们把它自动化了；专家被解放出来去做更高级的决策。最终愿景是：化学家输入需求，获得候选清单，但他仍然是那个决定哪些材料真正可行的人。我并不追求那种“黑暗实验室”——关上门让机器自己去发现新材料。我的愿景是赋能那些在公司和大学里的领域专家。保持谦逊很重要，现实世界极其复杂，有人一辈子都在做这个，我不认为未来 5 年内能完全取代他们。

<details>
<summary>Original English</summary>

**Max Welling**: that that's is the second one. So you build tools. So you so it's much more modular than you think but it's like we need these tools for this application. We need these tools. So you build all these tools and then you go through a workflow actually in the beginning just manually. So you put them at first this tool then run this tool then run this. So so you put them in in in a workflow and then you figure out oh actually you know this this pores material that we we're trying to make actually collapses if you shake it a bit. Okay. Then you add a new tool that says test for you know stability. Right. And so there's more and more tools and then you built the agent which could be a Beijing optimizer or it could be an actual LLM you know maybe trained to be a good chemist that will then start to use all these tools in the right way and the right order. Yeah. Right. But in the beginning it's like you as a chemist are putting the workflow together and then you think about okay how am I going to automate this? Right. One very easy question you can ask yourself is you know every time somebody who is not a super expert in DFT. Yeah. And he wants to do a calculation has to go to somebody who knows DFT. And so could you start to automate that away which is like okay make it so user friendly so that you actually do the right D of for the right problem and for the right length of time and you can actually assess whether it's a good outcome etc. So you start to automate smaller small pieces and more bigger pieces etc. And in the end the whole thing is automated. So so your philosophy is you want to provide a set of specific tools that make it so that the scientists making decisions are better informed and uh less so trying to create a an automated process. I think it's this is sort of the same what you're saying because yes we want to automate. Yeah. But we don't see something very soon where the chemists and the domain expert is out of the loop. Yeah, but but it's a retreat, right? It's like, okay, so first you need an expert to tell you precisely how to set the parameters of the DFT calculation. Okay, maybe we can take that out. We can maybe automate it, right? And so increasingly more of these things are going to be removed. Yeah. Um in the end the vision is it will be a search engine where you where somebody a chemist will type things and we'll get list candidates but the chemist will still decide what is a good material and what is not a good material out of that list right and so the vision of a completely dark lab where you can close the door and you and you just say just you know find something interesting and then it will it will just figure out what's interesting and we'll figure out you know it's like oh I found this new material to blah blah blah blah right that's not the vision I have at least not not for you know a long time so for me it's really empowering the domain experts that are sitting in the companies and in the universities to be much faster in in in developing their materials and I should say it's also good to be a little humble at times because it is very complicated you know to bring to make it and to bring it into the real world and there are people that are doing this for their entire lives. Yeah. Right. And it's like I wonder if they scratch their head and say, well, you know, how are how are you going to completely automate that away like in in in the next 5 years? I don't think that's going to happen at all. Um, yeah. So, so to me, it's a increasingly powerful tool in the hands of the chemists.

</details>

### 登月计划与混合策略

**主持人**: 你之前谈到通过重大突破来吸引人们。你们是在追求渐进式的改变，还是在追逐巨大的飞跃？

<details>
<summary>Original English</summary>

**Host**: I have a question. You've talked before about getting people interested based on having you know sort of a big breakthrough in materials just incremental change. I'm curious... how are you chasing the big change...

</details>

**Max Welling**: 我们采取的是**混合策略**。我们绝对在追求某种“伟大的材料”。同样，这是和合作伙伴一起做的，虽然不能透露具体是什么，但我们有自己的长期目标，你可以称之为“灯塔”或“登月计划”。我们想研发出一种极具影响力的材料，作为“AI 是必不可少”的证明。同时，我们也乐于与目标更温和的公司合作。比如一种是深度的长期合作伙伴，另一种是客户只需要我们帮他训练一个力场或分析某个特定问题，这也没问题。但我们更倾向于那种能真正改变现状的深度合作。

与量子计算或核聚变不同——那些可能需要研究 30 到 40 年，期间什么都没有，最后才是一个大爆发——在 AI for Science 领域，你构建的每一样东西几乎立即就能派上用场。比如我们和芬兰化学公司 Kemira 合作解决水过滤问题，去除水中的永恒化学物质（PFAS）。这种突破会伴随着大量的人工参与。化学家拥有深厚的领域知识，而我们用 AI 提供支持。在这种界面的交互中，美好的事情就会发生。

我认为在完全自动化之前，我们会先看到这种突破性材料的出现。因为自动化是非常垂直化的——解决 A 问题的方法，到了 B 问题可能需要完全不同的实验设置和模型微调。所以，人类专家仍然需要进来指引机器的新方向。

<details>
<summary>Original English</summary>

**Max Welling**: We follow a mixed strategy. So we are definitely going after a big material. Again, we do this with a partner. I'm not going to disclose precisely what it is, but we have our own kind of long-term goal. You could call a lighthouse or, you know, um sort of moonshot or whatever, but um it is going to be a, you know, really impactful material that we want to develop as a proof point that it can be done and that that it will make it into the into the real world and that AI was essential in actually making it happen. At the same time, we also are quite happy to work with companies that have more modest goals. Like I would say one is a very deep partnership where you go on a journey with a company and that's a long-term commitment together and the other one is like somebody says I need I need a force field. Can you help me train this force field and then maybe analyze this particular problem for me? Um and I'll pay you a bunch of money for for that and then maybe after that we will see. And that's fine too, right? But we prefer, you know, the deep partnerships where we can really change something for the good. Yeah. And do you feel like from a platform standpoint, you're ready for that or what are the things that and and again not asking you to disclose proprietary secret sauce, but what are the things generally speaking that need to happen from where we are to where to get those big breakthroughs like that? What I find interesting about this field is that every time you build something, it's actually immediately useful, right? And so unlike quantum computing which or nuclear fusion, so you work for I don't know 20 30 40 years and nothing nothing nothing and then it has to happen. Yeah. Right. And when it happens it's huge. So it's it's quite different here because every time you introduce so you go to a customer and you say so what do you need? Right. Okay. So we work uh let's say on a on a problem like water filtration we want to remove PAS from water right so we do this with a company chimera so they are deep partner for us right so we on a journey together I think that the breakthrough will happen with a lot of human in the loop because there is the chemists who have a whole lot more knowledge of their field and it's us who who will you know help them with AI training and new methods and in that kind these interface these interactions something beautiful will happen and that that will have to happen first before this field will really take off I think and so in the sense that it's not a bubble let's put it that way so there people see that's actual real what's happening so in the beginning it will be very you know with a lot of humans in the loop I would say and I would I would hope we will have this new sort of breakthrough material before you know everything is completely automated because that will take a while and also it is very vertical specific. So it's like completely automating something for problem A. You know you can probably achieve it but then you'll sort of have to start over again for problem B because you know your experimental setup looks very different. You the machines that you characterize your materials look very different. Even the models in your platform will have to be retrained and fine-tuned to the new class. So every time you know you have a lot of learnings to transfer but also you know the problems are actually different and so yes I I would want that breakthrough material before it's completely automated which I think is kind of a long-term vision and I would say every time you move to something new you'll have to start retraining and humans will have to come in again and sort of okay so what does this problem look like and now sort of you know point the the machine again you know in the new direction and and then and then use it

</details>

### 什么是等变性（Equivariance）？

**主持人**: 对于非科学家听众，你能用工程术语解释一下什么是等变性吗？

<details>
<summary>Original English</summary>

**Host**: And for the non-scientists among us... Can you sort of explain... what is equivariance?

</details>

**Max Welling**: 等变性就是将**对称性（Symmetry）**注入神经网络。假设我建立一个神经网络来识别这个瓶子。如果我旋转瓶子，普通的神经网络可能必须完全重新开始识别，因为它不知道旋转后的输入代表的仍然是旋转后的瓶子。

如果你在架构中内置了等变性，那么一旦你在一个方向上训练了模型，它就能自动理解任何其他方向。这意味着你训练模型所需的**数据量大大减少**。这些是对模型权重的约束。你可以将平移、旋转甚至是图神经网络中的置换（Permutations）等对称群硬编码进去。在物理学中，这类群非常多。

<details>
<summary>Original English</summary>

**Max Welling**: So equivariance is the infusion of symmetry in neural networks. So if I build a neural network, let's say that needs to recognize this bottle, right? And then he rotate the bottle, it will then actually have to completely start again because it has no idea that the rotated bottle. Well, actually the input that represents a rotated bottle is actually a rotated bottle. It just doesn't understand that. Where if you build a variance in basically once you've trained it in one orientation, it will understand it in any other orientation. So that means you need a lot less data to train these models and these are constraints on the weights of the model. So the so basically you have to constrain the weight such that it understand it and you can build it in you can hardcode it in and yeah this the symmetry groups can be you know translations rotations but also permutations like in graph neural network there are permutations and in physics of course there's many more of these groups

</details>

**主持人**: 唱个反调：为什么不直接使用**数据增强（Data Augmentation）**，把模型在所有不同方向上训练一遍呢？

<details>
<summary>Original English</summary>

**Host**: to play devil's advocate why not just use data augmentation by your model is in all the different orientations

</details>

**Max Welling**: 数据增强只是不够精确。为什么非要费劲去做无限次的数据增强，而不能直接硬编码进去呢？不过我也得承认，有时数据增强的效果甚至比硬编码等变性更好。

这涉及到优化过程。如果你在优化开始前就对权重施加约束，优化的曲面或目标函数会变得更加复杂，更难找到好的极小值。所以优化过程与你放入网络的约束之间存在复杂的相互作用。在该领域你会听到矛盾的说法：对于某些应用，等变性效果显著；而如果你有海量数据且易于做数据增强，有时直接训练反而更容易优化，效果更好。

这最终是**数据**与**归纳偏置（Inductive Bias）**之间的权衡。如果你的归纳偏置不完美，你会为模型的能力设定一个上限。但如果你确定某种对称性确实存在，很难想象不利用它会更好。这里也有一个“苦涩的教训（Bitter Lesson）”：除非你数据集非常小，否则你必须确保你的架构能够随规模扩展（Scale）。在大语言模型空间中适用的教训，最终在这一空间也同样适用。

<details>
<summary>Original English</summary>

**Max Welling**: as an option it's just not exact why would you go through the work of doing all that where you would really need an infinite number of augmentations to get it completely right um where you can also hardcode it in. Now I have to say sometimes actually data augmentation works even better than hard coding the equarians in and this is something to do with the fact that if you constrain the optimization the weights before the optimization starts the optimization surface or objective becomes more complicated and so it's harder to find good minima. So there is also a complicated interplay I think between the optimization process and and these constraints you put in your network and so yeah you you'll hear kind of contradicting claims in this field like some people and for certain applications it's it works just better than not doing it and sometimes you hear other people if you have a lot of data and you can do data augmentation then actually it's easier to optimize them and it actually works better than putting the aggregants in. Do you think there's kind of a bitter lesson for um mathematically founded uh models and strategies for doing deep learning? Yeah, ultimately it's a trade-off between data and uh and inductive bias. Yes. So if your if your inductive bias is not perfectly correct, you have to be careful because you you you put a ceiling to what you can do. But if you know, you know, the symmetry is there, it's hard to imagine there there isn't a way to actually leverage it. But yeah, so there is a bitter lesson. One of the bitter lessons is you should always make sure you architect your scale unless you have a tiny data set in which case it doesn't matter. Um, but if you you know the same bitter lessons or lessons that you can draw in LLM space are eventually going to be true in this space as well I think. Yeah.

</details>

### 新书：生成式 AI 与物理学的统一

**主持人**: 能谈谈你即将出版的新书吗？

<details>
<summary>Original English</summary>

**Host**: Can you talk a little bit about your upcoming book and tell the listeners like what's exciting about it?

</details>

**Max Welling**: 这本书名为 **《生成式 AI 与随机热力学》（Generative AI and Stochastic Thermodynamics）**。它揭示了一个事实：用于生成图像和视频的生成式 AI 数学，与**非平衡统计力学**（研究分子运动、弛豫到基态或受控状态的学科）的数学实际上是完全相同的。

这非常迷人。事实上，Geoffrey Hinton 和 Radford Neal 很久以前就写下了机器学习的变分自由能。Karl Friston 的自由能原理和主动推理也有相关论述。但现在我们将其与物理学中一个非常新的领域——**随机热力学**联系了起来。这个领域有自己非常有趣的定理，比如涨落定理（Fluctuation Theorems），虽然我们在 AI 中不常讨论，但可以从中获益良多。

这种跨界融合能让我们借鉴天才物理学家们的理论来改进算法。同时，我们也可以利用 AI 模型帮助科学家更好地做实验。书中的内容比较硬核，它将随机热力学中的各种模型与机器学习文献中的各种模型进行了等效。我希望这种**统一感（Unification）**能给人们带来启迪。

<details>
<summary>Original English</summary>

**Max Welling**: Yeah, they should read it. So this book is about so it's called uh generative AI and stoastic thermodynamics. It basically lays bare the fact that the mathematics that goes into both generative AI which is the technology to generate images and videos and this field of non-equilibrium statistical mechanics which is systems of molecules that are just you know moving around and you know relaxing to their ground state or that you can control to have certain you know be in a certain state. The mathematics of these two is actually identical. And so that's fascinating. And in fact, what's interesting is that Jeff Hinton and Radford Neil already wrote down the variational free energy for uh machine learning long time ago. And there's also Carl Friston's work on free energy principle and active inference. But now we've related it to this very new field in physics which is called stoastic thermodynamics or non-equilibrium thermodynamics which has its own very interesting theorems like fluctuation theorems which are which we don't typically talk about but we can learn a lot from and I think it's just it can sort of now start to cross fertilize when we see that these things are actually the same we can like we did for symmetries we can now look at this new theory that's out there developed by these very smart physicists and say okay what can we take from here that will make our algorithms better. At the same time, we can use our models to now help the scientists, you know, do better science, right? And so it becomes a beautiful cross fertilization between these two fields. You know, the book is rather technical, I would say, and it takes all sorts of things that have been done in stoastic thermodynamics and all sorts of models that have been done in in the machine learning literature and it basically equates them to each other. And I think hopefully that sense of unification will be revealing to people.

</details>

**主持人**: 书什么时候出版？

<details>
<summary>Original English</summary>

**Host**: Wait, and when is it out?

</details>

**Max Welling**: 这取决于出版社，但我希望在 4 月份。我将在 ICLR 做主题演讲，如果那时候能把书拿到手里就太棒了，但时间线很难控制。

<details>
<summary>Original English</summary>

**Max Welling**: Well, it depends on the publisher now, but uh I I hope in April um I'm going to give a keynote at Icleair and I would be very nice if I have this book in my hand, but you know, it's hard to control these kind of timelines.

</details>

**主持人**: 非常期待，谢谢 Max。

<details>
<summary>Original English</summary>

**Host**: Yeah, I'm looking forward to it. Great. Likewise. Thank you very much.

</details>