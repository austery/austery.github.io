---
author: Latent Space
date: '2026-07-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jhpmMTus5a0
speaker: Latent Space
tags:
  - continual-learning
  - context-rot
  - parameter-efficient-fine-tuning
  - neural-memory
title: AI 内存难题：为什么长上下文不够用？——专访 Engram 联合创始人兼 CEO Dan Biderman
summary: 在本期访谈中，Engram 联合创始人兼 CEO Dan Biderman 与 Latent Space 联合主持人一边制作地中海肉丸，一边探讨了 AI 模型面临的“上下文崩溃（Context Rot）”与内存效率挑战。Dan 结合其计算神经科学博士背景及在 MosaicML 和 Stanford 的研究经历，阐述了 Engram 如何通过参数高效微调（PEFT）及“知识墨盒（Cartridges）”技术，将兆级 Token 的企业数据压缩并内化入模型权重，从而打破 KV Cache 瓶颈，实现更具成本效益的持续学习与长时记忆。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Engram
  - MosaicML
  - Stanford University
products_models:
  - vLLM
  - Llama
media_books: []
status: evergreen
---
### 制作地中海肉丸与开场介绍

**Swyx**: 我太专注于做饭了，兄弟。对不起，我……

<details>
<summary>Original English</summary>

**Swyx**: I'm too absorbed in the cooking, man. I'm sorry. I'm

</details>

**Swyx**: 彻底懵了。呃……

<details>
<summary>Original English</summary>

**Swyx**: fried. Um,

</details>

**Swyx**: 整个节目里我都假装自己是个烹饪专家。这绝对是疯了。开个玩笑。

<details>
<summary>Original English</summary>

**Swyx**: the entire show I pretended to be the cooking expert here. It has to be pure crazy. Just kidding.

</details>

**Alessio**: 嘿，大家，欢迎来到 **Latent Space** 烹饪节目！在这里我们邀请创始人与研究员，并让他们展示厨艺。今天我们迎来了一位非常特别的嘉宾，**Engram** 的联合创始人兼 CEO **Dan Biderman**。

<details>
<summary>Original English</summary>

**Alessio**: Hey guys, welcome to the Laton Space Cooking Show where we invite founders and researchers and let them cook. Today we have a very special guest, co-founder and CEO Dan Bman of Engram.

</details>

**Dan Biderman**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Dan Biderman**: Nice to be here.

</details>

**Alessio**: 是的，感谢你的到来。我听 Jack 提起并与你取得了联系，他说你是个非常棒的厨师。另外，祝贺你们获得了 9800 万美元的种子轮融资。你经常做饭吗？频率如何？我猜你平时一直在不断进行研究和构建系统。

<details>
<summary>Original English</summary>

**Alessio**: Yes, thank you for coming. Um, I heard or we got connected through Jack who was saying that you're a very good cook and again congrats on the $98 million seed round. Do you cook often? How frequent is it? I assume you're constantly researching and building and

</details>

**Dan Biderman**: 是的。我想说，自从我创办这家公司以来，做这种类型的饭菜稍微少了一些。虽然也在做别的事情，但做饭是我从小就开始做的事。我的父母做饭，我的祖父母也做饭，这对我来说是一种放松、消化事物并把事情想清楚的方式。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So, I would say since I started the company, there's a little bit less cooking of this type. Uh, cooking other things, but cooking is something I've been doing since I I was a kid. My parents cook, my grandparents used to cook, and it's it's a way for me to kind of relax and digest things and think things through.

</details>

**Alessio**: 太好了。是的。我很兴奋。今天有点不同，我们实际上将让 Dan 带领我们完成其中一个食谱。你想向我们透露一下我们要制作什么吗？

<details>
<summary>Original English</summary>

**Alessio**: Great. Yeah. Well, I'm very excited. Today's a little different where we're actually going to have Dan lead us through one of the recipes. Do you want to reveal to us what we're making?

</details>

**Dan Biderman**: 是的。我想我们可以做牛肉肉丸，配一些蔬菜，然后让它们炖在某种由白葡萄酒和鸡汤调制成的白酱汁里。这是我最近在特拉维夫探望父母，用他们家里的现有材料做菜时，偶然发现的一种非常棒的地中海风味肉丸。所以，我觉得和你们一起重温这道菜并看看效果会很不错。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So, I was thinking we can make u beef meatballs with some vegetables and have them in swimming in some kind of white sauce with white wine and and chicken stock. It's a pretty nice Mediterranean type meatballs that I've kind of stumbled upon recently when visiting my parents in Tel Aviv and cooking stuff with what they had at home. So, I thought it would be nice to to redo this with you and see how it feels.

</details>

**Alessio**: 太棒了，我很期待。要开始吗？

<details>
<summary>Original English</summary>

**Alessio**: Great. Well, I'm very excited. Do you want to kick us off?

</details>

**Dan Biderman**: 我们要先炒洋葱。我会把它切碎，再切一些大蒜，然后把它们做成丸子煎一下。

<details>
<summary>Original English</summary>

**Dan Biderman**: We're going to fry the onion. I'm going to chop it and going to chop some garlic and then we'll make make them into balls and and fry them up.

</details>

### 军事背景与计算神经科学之路

**Alessio**: 煎它们。太好了。好的，那我们开始吧。我们俩并行操作。太棒了。不过，我想在开始时，我有点好奇你的背景。如果我没记错的话，你曾经想成为一名教授，而且你还有在以色列军队或特种部队的经历。

<details>
<summary>Original English</summary>

**Alessio**: Fry them. Great. Okay. Well, let's get started. We'll both do it in parallel. Awesome. Um, but yeah, I guess to start, I'm kind of curious about your background. So, you wanted to become a professor, if I recall correctly, and you also have experience in the Israeli military or special forces.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 呃，那段经历是如何让你转而成为一家 AI 研究公司的创始人的？

<details>
<summary>Original English</summary>

**Alessio**: Um, how did that turn you into becoming a founder of a research?

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 专注于人工智能研究的公司？

<details>
<summary>Original English</summary>

**Alessio**: AI research company?

</details>

**Dan Biderman**: 是的。我想如果往后看的话，把这些点连起来是很容易的，但在当时并不是。我并不是在成长过程中就规划好要成为一名针对人工智能这一热门话题开展工作的创始人。这都是顺理成章走过来的。我是在特拉维夫长大的，正如你所说，我曾是一名军官，专门从事特种作战，特别是海军特种作战。这非常具有创业精神，基本上就是去发现和识别我们能做的疯狂事情，并向人们证明我们应该投入资源和人员去实际执行它们。所以包含了大量的研究、大量的推介（pitching），以及为了让愿景成真而付出的艰苦努力。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So, I guess uh it's it's easy to connect the dots uh looking backward, but in real time, it was not. I didn't uh grow up planning to be this founder NSF working on this hot topic in AI things came to it. Um so I grew up in Tel Aviv and uh and as you said uh was an officer and and working on special operations specifically naval special operations which was very entrepreneurial. It was uh basically finding and identifying crazy things we could do and and prove to people that we should scale resources and and people to actually do them. So it was a lot of a lot of researching, a lot of pitching and then a lot of hard work to make things real.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 结束那段经历后，我去了大学，在以色列学习了**认知神经科学**。那是一个很有趣的项目，实际上很多以色列小说家、教授、科学家，甚至厨师——那位著名的以色列大厨在许多年前也参加过这个项目。我去了那里，对大脑产生了极大的好奇，对人类行为也很感兴趣。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um and then after I finished this um I went to university um and studied cognitive uh neuroscience in Israel uh in an interesting program where um actually a lot of Israeli novelists and professors and scientists and and even chefs you the Israeli chef went to this program many years before me. Um, and so I went there, got really curious about the brain, curious about human behavior.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 对统计学也很感兴趣。后来我去了纽约，攻读**计算神经科学**的博士学位。这个学术社群非常有韧性，在神经网络成为热门话题之前的几十年里，他们就已经一直在关注它了。是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Curious about statistics. And then I went to to New York to do a PhD in computational neuroscience. Um, which is a community that's been one of those stubborn communities that cared about neural networks for many decades before it was a hot topic. Yeah.

</details>

**Alessio**: 就在硅谷这边。

<details>
<summary>Original English</summary>

**Alessio**: Uh, here in the valley.

</details>

**Dan Biderman**: 是的，我在那里与一些统计学家、物理学家和生物学家一起研究，试图理解如何使用神经网络来理解大脑、理解动物行为。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um so I was there and studied with some statisticians and physicists and biologists trying to understand um how neural networks can be used to understand the brain to understand animal behavior

</details>

**Dan Biderman**: 然后在看到 ChatGPT 之后，我决定要更深入地进入大语言模型（LLM）的世界。因此我开始在 **MosaicML** 工作，在那里我从事了 **LoRA（低秩自适应）** 的开发工作，并结识了一群非常优秀的人。之后，我去了斯坦福大学与 **Chris Ré** 以及 **Scott Linderman** 一起工作，他们两位都是我目前创立的公司的联合创始人。我还在那里结识了我的联合创始人 Sabri，以及其他几位联合创始人 Jack 和 Jesse，他们也分别在康奈尔大学和伯克利大学的实验室里研究非常相似的课题。

<details>
<summary>Original English</summary>

**Dan Biderman**: and uh and then decided that I wanted to go deeper into the LLM world after seeing Chad GPT. So started working at Mosaic uh where I worked on Laura and met a bunch of great people and then from there I went to work with Chris Ray at Stanford and Scott Linderman who both are co-founders of my current company and where I met my co-founder Sabri and my other co-founders Jack and Jesse uh who work on very similar topics from their labs in Cornell and Berkeley.

</details>

**Alessio**: 是的。这听起来是一个非常专注于研究、同时也充满了机缘巧合的过程。稍微回退一下你的背景。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. No, it seems like a very very research focused and also serendipitous. Going back a little on your background.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 以色列特种部队有什么特殊之处吗？因为我记得 **Wiz** 的联合创始人也是特特种部队出身，对吧？

<details>
<summary>Original English</summary>

**Alessio**: Is there something about the Israeli special forces because I think it was a whiz co-founders, right, who are also ex special forces.

</details>

**Dan Biderman**: 是的，我们与 Wiz 的 CEO **Assaf Rappaport** 保持着非常紧密的合作。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Uh we work pretty closely with Assaf Rapaort, the WHIS CEO

</details>

**Alessio**: 他是我的导师。

<details>
<summary>Original English</summary>

**Alessio**: who's a mentor to me.

</details>

**Dan Biderman**: 是的，那里有很多有趣的事情在发生。我想说最重要的一点实际上是，当你在 18 岁加入情报部门或承担责任时，有趣的是你不仅处于学生状态——你不仅仅是低头应付考试和项目，而是要与成年人互动，拥有资源，并为你的预算等事情进行辩论和争取。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um and um yeah, there's interesting things going on. um there I would say the the most important thing is actually uh when you're 18 it's joining the intelligence or taking on responsibility uh the interesting bit about it is that you're not just in a student mode you're not just heads down doing exams and projects rather you interact with with grown-ups and you have resources and you argue your your for your uh budgets and things like that

</details>

**Alessio**: 嗯。

<details>
<summary>Original English</summary>

**Alessio**: um

</details>

**Dan Biderman**: 它迫使你建立起社交技巧和成熟度，这让我受益匪浅。

<details>
<summary>Original English</summary>

**Dan Biderman**: and it forces you kind of build a little bit of social skills, a little bit of maturity. Um, which which I benefited from

</details>

**Alessio**: 嗯，是的。

<details>
<summary>Original English</summary>

**Alessio**: um and um

</details>

**Dan Biderman**: 你知道，世界上许多国家选择不让每个人都服兵役，这是有原因的。服兵役的时间很长，这是一套“打包的交易”。我在不同时期服过兵役，但并不是最近这几年。所以，我并不是在推荐每个人都去参军，但我可以说，它确实会强迫你思考你性格中的其他方面，而不仅仅是智力层面。另外，总的来说，我认为以色列文化是一个允许你获得“多次射门机会”的地方。即使你在高中不是最拔尖的，在军队里仍然可能获得不错的位置；如果你真的很优秀，大学的大门会为你进一步敞开。而且，即使你在服兵役期间没做什么特别有趣的事，到了大学发现自己对科学和工程有深厚的兴趣，你依然能成为最成功的人。我们有一些以色列的学术和技术领袖就是这样的。所以我想说，这主要就像是……

<details>
<summary>Original English</summary>

**Dan Biderman**: you know there's a reason many countries in the world choose not to have everyone go to the army. It's a long time and it's and it's uha package deal and I was uh in the Israeli army in different years, not the ones that are the recent ones. Um, so it's not like I recommend everyone goes to the army, but I would say that it forces you to kind of think about other other aspects of your personality, not just the intellectual ones. And also generally, I would say Israel as a culture is a place where um you can basically you get multiple shots at goal. If you're not the best in high school, um you still might have a a good position in the military. And if you're really good, more doors open up for you for university. And even if you didn't do anything super interesting in in military and got to university and found out you have good and deep inclinations in science and engineering, you can be the most successful person. And we have some of those Israelis who are um leaders uh in various uh academic and technological places. So I would say yeah it's mostly like

</details>

**Dan Biderman**: 你基本上有多次重新分牌的机会。社会更强调社交能力，更强调成熟度和团队协作。但同样，这也是有代价的，就是当你做这些事情时，你的年龄已经偏大了。我 24 岁才开始读大学，这在美国大学里已经是读博士中期的年纪了。

<details>
<summary>Original English</summary>

**Dan Biderman**: you can basically the cards the cards are adult multiple times more emphasis on social aspects more emphasis on being mature on being a team player. Uh but again it comes at a price that you get you you're older when you get to things. Um, so I started college when I was 24, which is uh a middle PhD in and an American

</details>

**Alessio**: 大学的年纪，不过这确实合情合理。这给了你很多射门得分的尝试，也是一种非常美好的文化。现在，让我们快进到今天，回到 Engram。

<details>
<summary>Original English</summary>

**Alessio**: uh university. But yeah, so it makes sense. I think it's great how it gives you a lot of shots on goal and is a very beautiful culture. And now forwarding to today back to engram.

</details>

### 上下文崩溃与神经网络记忆瓶颈

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 是什么促使你们将注意力集中在上下文窗口（Context）这个瓶颈上的？是因为特定的技术突破，还是开源模型的表现，亦或是长视界智能体（Long-horizon agents）遇到的上下文衰减/崩溃（Context rot）问题？还是你个人对这个领域怀有极大的热情？

<details>
<summary>Original English</summary>

**Alessio**: What kind of prompted you to focus on this issue with context? Were there specific breakthroughs? Was it, you know, the performance of open source models or even just the issue of context rot long horizon agents or was it just that you're very passionate about this area as a whole?

</details>

**Dan Biderman**: 是的，我等下就回答。我们能先把这个加热一下吗？

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, I'll answer that in a second. Can we can we heat up some?

</details>

**Alessio**: 好的，我们马上开始。那么……

<details>
<summary>Original English</summary>

**Alessio**: Yes, let's start getting going. So,

</details>

**Dan Biderman**: 这里先炒一下……

<details>
<summary>Original English</summary>

**Dan Biderman**: here to fry up the

</details>

**Alessio**: 太好了。我们可以打开这个电磁炉。

<details>
<summary>Original English</summary>

**Alessio**: Great. So, we can turn on the impulse stove.

</details>

**Dan Biderman**: 好的。我读博期间研究的方向在今天并不是超级流行，但我认为未来它会再次变得极其关键，那就是**半监督学习（Semi-supervised learning）**。也就是在数据非常匮乏的情况下，你没有无限的万亿级 Token 的训练数据，只有非常少量的样本，你必须从中进行外推（extrapolate）并高效地学习，从而在更广泛的场景中达成目标。这也就是如何提升数据效率。我的所有学术研究的图表都在表达同一件事：横轴是某种资源成本，纵轴是准确率，这形成了一条帕累托前沿曲线（Pareto curve）。这就是我的成长底色：效率，如何用更少的资源做更多的事。需要加点盐，我们可以放点盐。

<details>
<summary>Original English</summary>

**Dan Biderman**: So yeah, my my PhD was focusing on on on a field that's not super in vogue today, but I think will become super crucial again, which is semi-supervised learning, which is you have very little data, you don't have infinite trillion tokens of data, a very infinite, you have very small set of examples and from them you want to extrapolate and learn efficiently for uhand and achieve things more more generally. So how to be data efficient. So my whole academic work was basically all of my papers had the same plot were on the x-axis I had some some cost some resource and on the y- axis I had um I had a accuracy sort of parto curve and that's been my my upbringing efficiency how to do more with less um salt. Yeah. Yeah, we can put some salt.

</details>

**Dan Biderman**: 之后我去了斯坦福大学 Chris Ré 的实验室，在那里我们从事关于智能体（Agents）的研究，这些理念被称为 **Minions（小黄人）**。我们探究的问题是：如何让智能体以一种非常经济实宜的方式与庞大的知识库进行交互。在这一理念流行之前，我们就引入了一些涉及子智能体协同的架构模式。抱歉，我刚意识到我们也可以放这个。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, and I went to to Chris Ray's lab um and Stanford at Stanford and there worked on agents on ideas called minions uh and and ask kind of the question of how can we have agents interface with very large uh corpora of knowledge in a way that's economical and when we introduce some patterns that involve sub agents uh a bit before it was uh popular. Oh, sorry. We can also put this I realized

</details>

**Dan Biderman**: 从效率和成本的角度出发，我们开始问自己……

<details>
<summary>Original English</summary>

**Dan Biderman**: and from that perspective of efficiency and of cost um

</details>

**Dan Biderman**: 是否存在一种更高效的交互数据的方式，而不是单纯依赖智能体编排和调度？我们是否能够通过训练的魔力，让模型具有更高的效率、更快的运行速度，并且处理更少量的 Token？Jesse、Sabri 以及我自己在并行开发过程中逐步形成了一些共识。

<details>
<summary>Original English</summary>

**Dan Biderman**: we started asking ourselves actually um is there a more efficient way to interface with data that's not just agentic orchestration and things like this can we actually use the the magic of training to um have models that are efficient faster and and and can operate with fewer tokens and some of these ideas kind of were developed in parallel by some of us uh Jesse, Sabrina, myself.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 核心观点是：如果你有一个非常庞大的知识库，允许模型提前对其进行研究和内化——例如让模型向自己提问、自测、尝试解决其中的问题，然后使用梯度下降以类似于预训练模型的方式对其进行训练。这样，你就可以创建出非常紧凑的上下文表征，之后可以直接将其加载。我们称之为**墨盒（Cartridges）**。这些就像是知识胶囊，你可以把它们加载到模型中，它们代表了一种描述模型世界与语料库的“大脑状态”，其数据压缩比可以达到上千倍。在使用它们时，你可以消耗极少的 Token 获得高精确度，从而避免模型的混乱。

<details>
<summary>Original English</summary>

**Dan Biderman**: Uh and the common theme was that if you have a very large corpus of knowledge um and you allow the model, you give the model time to study it in advance to basically ask itself questions, give itself quizzes, try to solve problems, and then train it using gradient descent in the same way you would pre-train a model. Um then you can create very compact representations of your context that can later on you can load them. We call those cartridges. These are like capsules of knowledge you can load in and out of the model that are like a brain state that describes the model's world and the corpus in a way that's maybe a thousandx more compressed. And when you use them you can basically uh use far fewer tokens be less confused more accurate and things like this. So we got

</details>

**Alessio**: 这些墨盒是特定于任务的吗？

<details>
<summary>Original English</summary>

**Alessio**: and these are task specific cartridges.

</details>

**Dan Biderman**: 它们可以是特定于语料库的，比如公司内部的文档；也可以是特定于任务的，比如学习某种特定的技能。

<details>
<summary>Original English</summary>

**Dan Biderman**: So they can be corpus specific like documents inside a company. They can be task specific like you want to learn a certain skill.

</details>

**Dan Biderman**: 但我们的初衷是，在许多情况下，超越单纯的文本表征是合理的。比如我们现在正在做饭，这里有许多非常棒的食谱或烹饪书，比如 French Laundry 的书。这些是非常了不起的书，我极其敬重它们。但如果说仅仅因为我们手头有这些书并能阅读它们，就代表我们深谙烹饪之道，甚至达到了 Thomas Keller 的水平，这是完全不对的。我们可以照着步骤一步步执行，表现得很像机器人；而现有的 LLM 就像是每一次进入厨房都当作是第一次，一边看着教科书，一边称量每一种食材，机械地做菜。但它们不具备那种捏起一把盐或揉面团的“主厨直觉”。我们在探索的这种训练和创建“墨盒”的过程，就是希望赋予模型这样一种直觉。这超越了孤立的笔记和菜谱本身，而是一种能够实现未知探索、在没有前人经验的领域进行外推和创新的智能。

<details>
<summary>Original English</summary>

**Dan Biderman**: But the idea is that in many cases it makes sense to go beyond textual representations. So when we're cooking now and we have all these like great textbooks or cookbooks here somerat and you know book from French laundry these are amazing books that I I respect. But to say that because we have the books and we can read them to say that we deeply know how to cook to the same level of Samosat or or or Thomas Keller. Yeah. It's incorrect. Right. We can read those things and we can repeat all their steps in a very robotic way and we can come in current LLMs are like coming into the kitchen first time every time reading the textbook uh cooking the dish measuring everything. uh but they don't have the intuition of a of a chef that's pinching salt and needing kneading dough and things like this. So the kind of thing we're after with this kind of uh training and creating those cartridges is this kind of intuition in the models that goes beyond notes and recipes to the kind of intelligence that allows then allows you to come come up with the next recipe thing that hasn't been explored before to do the next uh move and the next extrapolation.

</details>

### 检索增强生成与权重自适应微调的抉择

**Alessio**: 是的。如果对建立这种“直觉”做进一步的展开：你认为这与单纯的信息提取有什么本质不同？以烹饪为例，如果将烹饪书里有用的笔记和相关章节提取出来，提供给模型帮助其理解复杂性，这类似于目前的 RAG（检索增强生成）模式，在上下文中提供信息，然后再产生输出。这两者有什么区别？

<details>
<summary>Original English</summary>

**Alessio**: Yeah, I guess double clicking on building this intuition, could you kind of contextualize it more on how it would be different from extracting let's say using a cooking example if you get all the useful notes and useful section from a cookbook that will help you actually understand all the complexities of making a dish just providing it I guess that would be similar to rag getting just those chunks and then understanding that I guess in context and then providing an output.

</details>

**Dan Biderman**: 是的。那是一种非常优秀的工程方法。顺便说一下，如果可以的话，我现在先往里面加两个鸡蛋。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So, this is this is an excellent method. Um, we do not take the bet that I'm putting two eggs in here if that's okay. Um,

</details>

**Alessio**: 好的。这些切碎的胡萝卜和西葫芦够了吗？

<details>
<summary>Original English</summary>

**Alessio**: and is this enough grated carrot and zucchini?

</details>

**Dan Biderman**: 是的，棒极了。你可以把它放进这里。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, excellent. You can put it in here.

</details>

**Alessio**: 好的。

<details>
<summary>Original English</summary>

**Alessio**: Um,

</details>

**Dan Biderman**: 好的。

<details>
<summary>Original English</summary>

**Dan Biderman**: yeah.

</details>

**Dan Biderman**: 所以我们并不是要在研究路线中彻底否定记录笔记的价值，对吧？

<details>
<summary>Original English</summary>

**Dan Biderman**: So, we're not taking the bet that no need no notes need to be taken, right?

</details>

**Alessio**: 是的。把所有的都倒进去吗？嗯。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. Put all of it inside. Mhm.

</details>

**Dan Biderman**: 世界上最伟大的主厨们都有笔记和书籍，他们记录自己的实验，写明哪些行得通、哪些失败了。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, all the greatest chefs in the world, they have notes and they have books and they

</details>

**Dan Biderman**: 但他们同时拥有大脑、双手和舌头，这些能够让他们回忆起某种味道，知道什么是好吃的，知道哪些操作困难或容易。因此，在我们的所有工作中，绝没有说过文本表征是无用的。我们一直在频繁使用它们，构建 Wiki 和知识库。

<details>
<summary>Original English</summary>

**Dan Biderman**: they have diaries and they document what worked and what didn't work with their experiments, but they also have brains that they also have hands and and uh and uh a tongue that can remind them how something tastes and what worked and what failed and what was easy and what was hard. So uh in all of our work we never say that textual representations are useless. We basically use them all the time and we construct those wikis and knowledge bases and things like this.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 与此同时，我们认为在这之上的更深一层——直觉与学习的层级，其实是以参数数值的形式沉淀下来的。这才是人类主厨的全部体验。世界上最棒的厨师是“所有笔记”与“一个能够阅读并执行这些笔记、在其中进行创新的神经系统”的结合体。当技术足够纯熟时，他们甚至不需要一次次重新翻阅菜谱。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um at the same time what we say is that the layer above those the learn the layer of intuition and learning uh that is in the form of numbers of parameters um is is the full experience of the human chef. the best chef in the world is all the notes combined with a nervous system that reads those notes and can implement them and innovate them and maybe don't return to the same notes over and over again. There are some dishes where they don't need to to reread them.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 我们追求的是鱼与熊掌兼得。对任何知识工作者而言，如果他们不能写笔记、无法记录一天的事件，那显然是劣势；但如果每天晚上都擦除他们大脑的所有记忆，这同样也是灾难性的劣势。

<details>
<summary>Original English</summary>

**Dan Biderman**: And the current problem in um so I was saying that um we want we want the best of both worlds. Every knowledge worker if they can't write notes and they cannot document the events of the day they would be uh in a disadvantage. But if you wipe their brain every evening, they would also be at a severe disadvantage.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 所以我们想结合两者。我们要考虑的是：看着当前知识被创造出来的恐怖速度，智能体代表人类在工作，不断生成各种工件、代码、文档、展示材料。我认为很多人还没有完全意识到，在未来 18 个月里，我们所需要面对的本地知识空间规模将是多么庞大。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um so we want to have the best of both worlds. And uh the thing is that textual representations can take you uh a long way. Uh but the thing we're thinking about is like look the at the rate at which knowledge is being created with now agents working on behalf of knowledge workers creating artifacts code documents uh presentations

</details>

**Dan Biderman**: 我觉得大家可能对那个规模没有什么实感。

<details>
<summary>Original English</summary>

**Dan Biderman**: I think that people don't fully comprehend the size of the

</details>

**Dan Biderman**: 18 个月后我们需要处理的知识空间。

<details>
<summary>Original English</summary>

**Dan Biderman**: of the knowledge workspaces they will deal with in 18 months

</details>

**Dan Biderman**: 很多公司将积累起多达数万亿 Token 级别的数据。

<details>
<summary>Original English</summary>

**Dan Biderman**: um in 18 months many companies would have maybe trillions of tokens which

</details>

**Alessio**: 公司的内部数据吗？

<details>
<summary>Original English</summary>

**Alessio**: of internal company

</details>

**Dan Biderman**: 是内部公司的专有数据。万亿级别听起来很夸张，但如果他们真的是完全 AI Native 的公司，这绝对不是天方夜谭。

<details>
<summary>Original English</summary>

**Dan Biderman**: of internal company data proprietary data I'm talking about like maybe trillions it sounds exaggerated but I don't think it's an impossibility if they're really AI native

</details>

**Dan Biderman**: 万亿 Token 是什么概念？想当年，两三年前我在 MosaicML 的时候，我们将这种级别的规模称为“互联网量级”的数据，这直接就是预训练数据集的规模。

<details>
<summary>Original English</summary>

**Dan Biderman**: and I think and and what are trillions of tokens that like when I was at Mosaic 2 3 years ago like we call this internet scale data pre-training data

</details>

**Dan Biderman**: 试想一下，如果每家公司手头都有互联网量级的数据……

<details>
<summary>Original English</summary>

**Dan Biderman**: so imagine every company has data that it's basically internet scale data

</details>

**Dan Biderman**: 嗯。

<details>
<summary>Original English</summary>

**Dan Biderman**: um

</details>

**Dan Biderman**: 顺便说一下，我可能需要一些盐、胡椒和面包屑。这里没有水槽，所以我的手弄脏了，希望大家能够包涵。

<details>
<summary>Original English</summary>

**Dan Biderman**: and I might need uh salt and pepper and the breadrumbs for this. And we don't have a sink here, so hands will be dirty. I hope the audience here is forgiving.

</details>

**Alessio**: 呃……

<details>
<summary>Original English</summary>

**Alessio**: Um,

</details>

**Alessio**: 必须得把手弄脏。

<details>
<summary>Original English</summary>

**Alessio**: got to get your hands dirty.

</details>

**Dan Biderman**: 是的。我曾经从一位主厨那里听过一条原则：肉类和其他辅料的比例为 1:1 通常是做丸子的健康配比。所以我想，我们这个比例很棒。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Awesome. I guess the principle here I once heard from a chef is that a ratio of one one of meat with everything else is usually a healthy way to make meatballs. So, I think we we're

</details>

**Dan Biderman**: 是的，有道理。这是盐和胡椒。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, that's fair. We are salt and pepper.

</details>

**Alessio**: 很好的肉丸。因为刚刚放了炒洋葱，稍微有点热度。

<details>
<summary>Original English</summary>

**Alessio**: Nice meatballs. They're a bit warm with those fried um

</details>

**Dan Biderman**: 我们回到……

<details>
<summary>Original English</summary>

**Dan Biderman**: We're back with the

</details>

**Alessio**: 欢迎回来。

<details>
<summary>Original English</summary>

**Alessio**: We're back.

</details>

**Dan Biderman**: 带着做好的肉丸重新开始。

<details>
<summary>Original English</summary>

**Dan Biderman**: We're back with the fixed meatballs.

</details>

**Alessio**: 带着我们做好的肉丸。这也是一次团队建设活动。

<details>
<summary>Original English</summary>

**Alessio**: With the fixed meatballs. It's team building activity here.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yes.

</details>

**Dan Biderman**: 噢，把你们带来的调味料放进去吧。我相信你挑香料的眼光。

<details>
<summary>Original English</summary>

**Dan Biderman**: Oh, yeah. Let's put those spices that you brought. I trust you on these ones.

</details>

**Alessio**: 孜然，放一点点，不需要太多。

<details>
<summary>Original English</summary>

**Alessio**: Cumin. Let's put a little bit. Not a ton.

</details>

**Dan Biderman**: 是的，我们不要像上次那样全部倒进去了。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. We won't dump it like last time.

</details>

**Alessio**: 孜然是我妻子最喜欢的香料。

<details>
<summary>Original English</summary>

**Alessio**: Cumin is my wife's favorite spice.

</details>

**Dan Biderman**: 噢，孜然确实太棒了。

<details>
<summary>Original English</summary>

**Dan Biderman**: Oh, yeah. Cumin is great.

</details>

**Alessio**: 我对它倒是有一些复杂的感情。但……

<details>
<summary>Original English</summary>

**Alessio**: I have mixed feelings about it, but

</details>

**Dan Biderman**: 好的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Okay.

</details>

**Alessio**: 很好，很棒。

<details>
<summary>Original English</summary>

**Alessio**: Yeah, it's good. Yeah.

</details>

**Dan Biderman**: 挺好。

<details>
<summary>Original English</summary>

**Dan Biderman**: Good.

</details>

**Alessio**: 好极了。现在该把它们揉成丸子了。

<details>
<summary>Original English</summary>

**Alessio**: Good. So, we have the meatballs. Now is the time to make the balls.

</details>

### 神经网络记忆与外部知识库的边界

**Dan Biderman**: 刚刚我们聊到哪里了？

<details>
<summary>Original English</summary>

**Dan Biderman**: So, we were talking about

</details>

**Alessio**: 我们在聊什么来着？

<details>
<summary>Original English</summary>

**Alessio**: What were we talking about?

</details>

**Dan Biderman**: 我觉得我太专注于做饭了，兄弟。真的很抱歉，我……

<details>
<summary>Original English</summary>

**Dan Biderman**: I think I'm too absorbed. I'm too absorbed in the cooking, man. I'm sorry. I'm

</details>

**Alessio**: 没事，非常好。你刚才在分享你们的技术逻辑：当一家公司拥有的内部数据集规模达到互联网级时，会发生什么。

<details>
<summary>Original English</summary>

**Alessio**: No, it's good. You were pitching things here. You're talking about how companies will have a corpus of data that will be at the scale of the internet.

</details>

**Dan Biderman**: 是的。也许在今天，某些公司并没有这么大的数据量，依靠纯文本表征也可以走得很远。这很好，因为文本表征是具备高可解释性的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Yeah. And maybe maybe today some they don't have it and maybe today you can go relatively far with textual representations. They're also interpretable. They're very good.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 但在达到一定的超大规模时，即便是去实时构建那些文本的表征或索引也会变得极难。如果你有万亿级 Token，你如何能做到让庞大的知识库或 Wiki 实时保持更新？这得有多庞大？而且，当你直接把完全不了解你公司的前沿大模型拉过来做检索推理时，每次要处理那么多上下文，推理成本将是多么高昂？

<details>
<summary>Original English</summary>

**Dan Biderman**: Um but I just think at a certain scale even those textual representations will be hard to make. If you have trillion tokens, how do you create exactly a wiki or an index of those that you keep updated all the time? How big is this um knowledge base that you create? How expensive will it be to process it with frontier models that know nothing about your your company?

</details>

**Alessio**: 所以，主要原因是因为使用外部大模型每次都必须重头读取大量数据，从而让成本极其高昂？这是最主要的痛点吗？

<details>
<summary>Original English</summary>

**Alessio**: So is it just that using frontier models will be expensive because that's start from scratch every time. Is that the main?

</details>

**Dan Biderman**: 成本是一个维度，因为你必须反复阅读内容、消耗极多 Token。这是第一点。

<details>
<summary>Original English</summary>

**Dan Biderman**: So there's the element of expensive because you reread more things, you consume more to tokens. That's one.

</details>

**Dan Biderman**: 但更关键的是第二点：未来 18 个月内，我们让模型在如此庞大的知识库上执行各种长时视界（Long-horizon）的智能体任务时，那些指令很多都是模糊或定义不明确的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. But two is like for the agentic tasks of 18 months from now inside those major repositories of knowledge and asking the models more and more things and under specified ways.

</details>

**Dan Biderman**: 我怀疑模型的准确性会大幅退化，也就是“上下文崩溃（Context Rot）”现象。模型必须读取太多上下文，准确度便随之崩塌。即便上下文窗口技术扩展到 1000 万级别，这种因注意力分散引起的崩溃依然会存在。

<details>
<summary>Original English</summary>

**Dan Biderman**: I suspect that the accuracy of the models would would go down the the phenomenon of context fraught, right? The model has to read more. It will be less accurate and we know this and it will remain the same thing at even at the 10 million uh context window scale.

</details>

**Alessio**: 好的，这合情合理。我们去快速洗个手，马上回来。

<details>
<summary>Original English</summary>

**Alessio**: Okay, that makes sense. Okay, let's go wash our hands real quick. We'll be right back.

</details>

**Dan Biderman**: 好的，我们回来了。手洗干净了。接下来干什么？开始煎肉丸。

<details>
<summary>Original English</summary>

**Dan Biderman**: Great. And we're back. Hands are all clean. So, now what's the next thing? Just frying the meatballs.

</details>

**Alessio**: 是的，煎肉丸。

<details>
<summary>Original English</summary>

**Alessio**: Yeah, let's fry those meatballs.

</details>

**Dan Biderman**: 你能把这个扭开吗？按下然后转动。

<details>
<summary>Original English</summary>

**Dan Biderman**: You want to turn this one? You just press it and then turn it.

</details>

**Alessio**: 非常直观。

<details>
<summary>Original English</summary>

**Alessio**: Very intuitive.

</details>

**Dan Biderman**: 我们放一点油。

<details>
<summary>Original English</summary>

**Dan Biderman**: And we'll put some oil.

</details>

**Alessio**: 好的，把这些放进去。而且……

<details>
<summary>Original English</summary>

**Alessio**: Okay. We could put these in. And

</details>

**Alessio**: 在这个过程中，我想探讨……

<details>
<summary>Original English</summary>

**Alessio**: while we do that, I guess

</details>

**Alessio**: 更多关于长视界智能体的话题。

<details>
<summary>Original English</summary>

**Alessio**: more so on the question of like long horizon agents.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: Engram 想要解决的核心痛点是什么？如果用对方立场最强力的论点（Steel man）来反驳你：也许许多企业内部的数据集根本没有大到必须写入模型权重的程度。那为什么不直接使用 RAG 或是使用现有的、甚至更便宜的开源模型来处理这些任务呢？

<details>
<summary>Original English</summary>

**Alessio**: Um, what's the main issue that Engram is trying to solve? So right now if I were to steal manand the opposing view ummaybe company internal company data isn't actually big enough where I'd need to put it into the weights like what's the issue with just having rag or um having specific models or even cheaper models since open source models are also very performant to handle a lot of tasks.

</details>

**Dan Biderman**: 是的。学术界目前研究的一个极具挑战的问题是：你能否给出一个例子，证明在此例子中只有模型“权重内记忆（In-weight learning）”可以成功，而单纯依靠“上下文检索学习（In-context learning）”必定会失败。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So I would say like um a thorny question in the research community is can you come up with an example where only in weight training would work wherein in context learning will fail.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 结果证明，很难设计出这样一个绝对二分的极端例子。因为对于任何你给出的例子，人们总是会说：“但如果下一代大模型拥有 1000 万的上下文窗口会怎么样呢？”

<details>
<summary>Original English</summary>

**Dan Biderman**: And turns out it's very hard to devise such examples and for every example you give someone can ask well what happens if the the next um the next payable has a 10 million context window.

</details>

**Dan Biderman**: 从我的学术经历和视角来看，我把关于“持续学习”和“模型长时记忆”的问题，本质上都看作是伪装成“长上下文”的问题。

<details>
<summary>Original English</summary>

**Dan Biderman**: Mhm. Um, and the way I see it and kind of my scientific upbringing, I see all of these questions of of continual learning and memory as questions of long context uh in disguise.

</details>

**Dan Biderman**: 如果模型可以塞入整家公司的数据，且在原理上有无限的上下文窗口，那它的瓶颈到底是什么？局限主要有两点。第一，即便是在较小的数据量下我们也知道，模型被塞入的上下文越多，它就越容易困惑和自我矛盾。这就是所谓的“上下文衰减”。你可以硬塞几百万 Token 进模型且不报内存溢出错误，但这并不意味着模型能在这些繁杂的上下文里进行全局的、无损的逻辑推理。这是一点。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, if the models could see a whole whole company data and in principle would have this infinite context window, what then is the limitation? So the limitation is twofold. One is that we know even at very small scales that the more context you feed to the model, the more confused it gets. It's called the context rot. So you can feed in a certain uh number of tokens into the model and not get an error, but doesn't mean that the model can reason in in a in a holistic way about them. That's one thing. And

</details>

**Alessio**: 那上下文压缩（Context compaction）呢？你觉得上下文压缩没有用吗？

<details>
<summary>Original English</summary>

**Alessio**: and what's the problem with compaction? Is compaction not as useful, would you say?

</details>

**Dan Biderman**: 上下文压缩技术在日新月异地进步。是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: So I think compaction is is improving by the day. Yeah. Yeah.

</details>

**Dan Biderman**: 为了方便观众理解，上下文压缩就是让模型自行管理当前的上下文，决定抛弃哪些 Token 并保留哪些。压缩确实有用。然而，当你面向长视界的任务时，压缩在定义上就是有损的。

<details>
<summary>Original English</summary>

**Dan Biderman**: And compaction for those in the audience who don't know what it is, it's like models actually managing their own context uh evicting certain tokens and and keeping others. Uh compaction works. Uh that too when you go into a longer horizon, compaction by definition is lossy.

</details>

**Dan Biderman**: 你丢弃一些，保留另一些。这是一条必然要走的技术路径。但目前大多数压缩算法都是极其确定性的：要么留下，要么丢弃。这在超长会话（Deep session）的探索中容易表现出模型遗忘和混乱的问题。

<details>
<summary>Original English</summary>

**Dan Biderman**: You discard some and keep other things. And I think it's it's a it's a correct way to to go. Uh but it's it's also like very deterministic. Either you're in or you're out. in the current versions of compaction uh show these kinds of uh uh issues when when very deep into the session you can get um confused and you can get um forgetful.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 所以我们认为上下文压缩会是最终图景的一部分。

<details>
<summary>Original English</summary>

**Dan Biderman**: So we think compaction will be part of the story.

</details>

**Alessio**: 好的。

<details>
<summary>Original English</summary>

**Alessio**: Okay.

</details>

**Dan Biderman**: 但我们深信，解决方案的另一部分必须是某种“神经记忆痕迹（Neural Memory Trace）”。这也是一种有损压缩，但它不是以纯文本形式剔除或留存，而是沉淀在大模型的权重表示里。我们目前解决的首要痛点，第一是提升 Token 效率和降低成本。这在去年年底我们刚创立公司时还不是显性痛点，但现在正变得越来越急迫；第二是当你用更少的资源达到同样的效果时，你就能拓展去处理以前根本无法想象的超大规模数据。

<details>
<summary>Original English</summary>

**Dan Biderman**: We think another part of the story is some sort of neural memory trace which too is a lossy thing. it evicts some and and keeps some but not in the text uh representation in the weights representation but I would say the main thing we're trying to solve or the main thing for which continual learning is needed one is token efficiency and cost which is a major issue that wasn't actually an issue when we started the company late last year and became more urgent now and problem number two is if you can do uh if you can do the same thing when with fewer resources is when you scale up to very large resources, suddenly you can take on tasks that were previously not possible.

</details>

**Alessio**: 更长的视界，更强的自适应能力。

<details>
<summary>Original English</summary>

**Alessio**: Way more long horizons, way more uh adaptive

</details>

**Dan Biderman**: 没错，虽然我们还没有完全实现这一终极目标。目前我们首先聚焦于第一阶段的任务：即让大模型能够以极少的 Token 消耗去理解超长上下文，并让其减少混乱。

<details>
<summary>Original English</summary>

**Dan Biderman**: and we're not quite there yet. Uh we're focusing right now on on the first component which is getting these models to reason on large context with fewer tokens and do it in a way that's that's more uh uh less confused.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. Yeah,

</details>

**Dan Biderman**: 但我们相信，长远来看……

<details>
<summary>Original English</summary>

**Dan Biderman**: but we think that eventuallyuh part of the

</details>

**Alessio**: 我来拿。

<details>
<summary>Original English</summary>

**Alessio**: I'll take

</details>

**Dan Biderman**: 对于科学、工程和国防等核心领域的高难度任务，解决方案必将涉及在执行长时视界任务过程中进行基于梯度的实时权重更新。有人把这叫作**测试时计算（Test-time compute）**或**测试时训练（Test-time training）**。其实这些只是针对同一个本质的不同称呼罢了。预训练的存在早已为我们提供了一个现成的存在性证明（Proof of existence）：你可以将天文量级的信息非常紧凑且极其高效地压缩在较少的参数权重里。比如我们最喜欢举的例子：如果你有一个 Llama 70B 模型，你给它输入一篇几万字节的维基百科文章，模型在处理这些数据时，其在 GPU 显存（HBM）中留下的激活状态（KV Cache）将达到恐怖的 80GB。

<details>
<summary>Original English</summary>

**Dan Biderman**: part of the part of the solution for very hard tasks in in science and engineering and defense and all that stuff will involves some form of gradient based updates um during uh during uh doing these long horizon tasks. So some people call this u test time compute or test time training. Um these are just different names for the same thing. I think we have a a proof of existence from pre-training that um you can pack a lot of information in very few numbers very efficiently. Um so the examples we like to give is that uh if you take a llama 70D model and you load one article from Wikipedia which is a few tens of kilobytes and you have the model read this uh the brain state of the model when reading this few tens of kilobytes is like 80 gigabytes 80 gigabytes on on the HBM of the GPU.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah,

</details>

**Dan Biderman**: 这是一个多么疯狂的数量。整个 70B 模型在 FP16 精度下的权重也仅为 140GB 左右。这 140GB 的权重（虽然有损）却能够代表几乎整个互联网的知识！而现在，仅仅为了读取一篇关于泰勒·斯威夫特的维基百科文章，模型消耗的 GPU 显存就跟它装下整个互联网所需的空间处于同一个数量级。这是极度缺乏内存效率的。这就是现在整个系统工程界最聪明的头脑正试图从芯片底层、软件架构与算子内核优化上全力攻克的一个难题：**KV Cache 庞然巨兽**。如果我们能从系统层面换个角度来看待我们正在做的事情：

<details>
<summary>Original English</summary>

**Dan Biderman**: it's an insane amount and the entire set of parameters of this model would be like 140 or or so gigabytes FP16. So those 100 or so gigabytes with some distortion represent the entire internet. And this one article about Taylor Swift is like same order of magnitude memory consumption on the GPU. So it's highly memory inefficient. That's a systems problem. That's the the KV cache monstrosity that the smartest people in the world are trying to solve from the chip side of things and from the

</details>

**Dan Biderman**: 稍微切入一下技术细节：现在的模式是模型不断去做Prefill（预填充），不停地反复阅读文档；而我们的做法实际上是在消除这部分重复的 Prefill 算力损耗，通过将这部分计算转嫁到训练阶段，使得我们可以直接将对应的知识模块（Cartridge）瞬间加载进模型，直接开始 Decoding（解码）或只需微量的 Prefill。这与当前数据中心正在发生的“Prefill 与 Decode 节点解耦（Disaggregated Prefill and Decode）”并在不同专用 GPU 卡上运行的趋势高度吻合。这也是我们早期对这个方向感兴趣的原因之一。

<details>
<summary>Original English</summary>

**Dan Biderman**: from the software and kernel side of things. Um but yeah so I would say another way to look at what we're doing from that angle from the systems angle is basicallyuh if we if we can get a bit more technical instead of doing those uh prefills where the models is reading and reading and reading a a corpus uh we are kind of like the we're destroying prefill we're scaling training compute in some other time so we can load the thing into the model and it can just immediately start decoding or prefill a little bit and this kind of goes a hand in hand with trends in how data centers are built out this aggregating prefill and decode and doing this on different specialized uh cards and uh and this is part of our part of our initial interest in

</details>

**Alessio**: 明白了。看来我们这里准备得差不多了，是时候加点白葡萄酒了。

<details>
<summary>Original English</summary>

**Alessio**: okay so it seems like we're mostly ready here I think it's a good time for our

</details>

**Dan Biderman**: 两边锅里都加吗？

<details>
<summary>Original English</summary>

**Dan Biderman**: white wine on both of them

</details>

**Alessio**: 你来操作吗？

<details>
<summary>Original English</summary>

**Alessio**: you want to do that

</details>

**Dan Biderman**: 是的。你在解释这个技术路径时，有没有什么具体的工业界实际应用案例？比如，我们来设想一下，一家投资银行或者一家律所，他们每天要处理海量的客户档案和案件。

<details>
<summary>Original English</summary>

**Dan Biderman**: yeah and do you have any tangible examples on this when you're talking about your approach. So if you think about umlet's think for example about like an enterprise uh a firm or uminvestment banking a law firm or investment banking they can have many client matters uh many

</details>

**Alessio**: 存在大量的知识工作。

<details>
<summary>Original English</summary>

**Alessio**: like a lot of knowledge work

</details>

**Dan Biderman**: 是的。他们有非常多的客户，而客户一直在做各种融资、并购（M&A）、贷款和交易。

<details>
<summary>Original English</summary>

**Dan Biderman**: a lot yeah so many client matters they have various clients clients do financing mergers and acquisitions and things like this and take loans and do deals

</details>

**Alessio**: 要把这个放上去吗？

<details>
<summary>Original English</summary>

**Alessio**: want to put this on

</details>

**Dan Biderman**: 先不用，我们先让汤汁收浓一点。

<details>
<summary>Original English</summary>

**Dan Biderman**: not yet no not yet we want to let it uh

</details>

**Alessio**: 让它……

<details>
<summary>Original English</summary>

**Alessio**: let it

</details>

**Dan Biderman**: 稍微收一下汁。好的。

<details>
<summary>Original English</summary>

**Dan Biderman**: let it reduce a little bit. Okay.

</details>

**Dan Biderman**: 是的。例如，这正是我们目前与法律 AI 初创公司 **Harvey** 合作解决的问题：极度庞大的文件系统。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. And so, for example, these are the kinds of things we we work with Harvey, very very large file systems.

</details>

**Dan Biderman**: 在这样的系统上，智能体需要面对大量宽泛且极具挑战的全局查询，而这些查询依靠传统的 RAG 几乎是完全无法检索的。例如，如果你想询问：“我们今年有哪些并购（M&A）项目最终没有完成闭环？”为了解决这个问题，你必须把这万亿字节的档案逐个客户、逐个条款地读取。

<details>
<summary>Original English</summary>

**Dan Biderman**: Uh and there's many queries that agents might run into. Either humans ask them or the agents have to solve them, which are these kinds of like ambient hard questions that are not easily searchable with rag. For example, if you want to ask likewhich M&A deals haven't we completed this year. So to actually solve this problem, you have to go client matter by client matter.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 你不能仅依靠某个关键词检索出没有闭环的细节。你必须通读全篇，理解整个故事的发展脉络。

<details>
<summary>Original English</summary>

**Dan Biderman**: Read all the files. You can't read in any place that it was not completed. You have to take the gist.

</details>

**Dan Biderman**: 确认这一环确实没有合拢。目前使用前沿大模型加长上下文或者压缩的技术，看似能解决，但是为了获取这么一个普通人类员工本可以轻易给出答案的全局结论，却需要消耗极其惊人的计算成本。

<details>
<summary>Original English</summary>

**Dan Biderman**: You have to understand the thing hasn't the loop hasn't been closed. Thing hasn't been completed. And now you can solve these tasks with with Frontier models and compaction. And when you ask them to do so, they will consume thousands of dollars for queries that we think are harmless that every employee in the company would be able to answer.

</details>

**Dan Biderman**: 这只是其中一个案例。当我们需要进行“整体大于部分之和”的全局抽象和归纳推理时，神经网络微调的魔力就体现出来了。这也是 Ilya Sutskever 等人在预训练中向我们展示的奇迹：直接把整个互联网打包进这一组模型参数中，模型因此可以产生推理、泛化，甚至对外推测未见的新事物。这正是我们想要让模型拥有的本地知识关联能力。这也是为什么我们不能只在有需要的时候临时抱佛脚做一下 RAG。因为高强度的学习过程，在模型内部建立起了不可替代的知识联想。

<details>
<summary>Original English</summary>

**Dan Biderman**: So this is just like one example. But these kinds of holistic things that are you know you can get the gist if you read everything but you can't find a thing in one thing. The kind of queries where the whole is greater than the sum of its parts. That's where uh this kind of magic of training uh comes in and that's the the magic that that you know Ilia and others have shown us with pre-training right you learn the entire web in these sets of weights and suddenly the model can infer things can generalize can interpolate and extrapolate to new things and that's the kind of knowledge we want to do and it and it's not a not a coincidence that we're training on the entire web and we're not just doing rag over the entire web or putting it in the catalog and reing it in time because we do think that learning from a lot of knowledge somehow creates these associations in the model.

</details>

**Alessio**: 明白了。所以这里有一些是针对当下的具体问题，还有一部分是对 18 个月后数据规模扩张的押注，因为届时企业内部数据的爆发必须要使用已经被预训练证实有效的参数写入方法。

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. So some of it is concrete problems of now other parts of it are bets that in 18 months from now the scale of the data will require the methods that we know from pre-training work.

</details>

**Alessio**: 那么，你们目前是否在为特定的企业提供基于其语料库的参数高效微调（如 LoRA）服务？

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. And so are you doing primer efficient fine-tuning for specific companies like Laura based off of the corpus?

</details>

**Dan Biderman**: 是的。虽然这是我们的短期商业化切入点，但我们的终极雄心是：

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So our ambition in the long term

</details>

**Alessio**: 同样也是起步。

<details>
<summary>Original English</summary>

**Alessio**: but also start

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Yeah.

</details>

**Dan Biderman**: 我们的长期愿景是：未来每一个人都拥有一个专属于他们的模型副本或一部分模型权重。

<details>
<summary>Original English</summary>

**Dan Biderman**: So our ambition in the long term uh is that every person has a has a model or or a part of the model or a set of weights

</details>

**Alessio**: 对的。

<details>
<summary>Original English</summary>

**Alessio**: Yes.

</details>

**Dan Biderman**: 这部分权重直接承载他们的核心专业技能与独有知识，并随着用户与模型共同度过的时间增长而不断进化。你喂入的数据越多，模型就越懂你。

<details>
<summary>Original English</summary>

**Dan Biderman**: uh that that represents their knowledge, their expertise learns from them that the more time they spend with the model, the better it gets for them. The more data they give the model, the better the model is for them.

</details>

**Dan Biderman**: 用户可以完全自主控制这一部分模型权重。

<details>
<summary>Original English</summary>

**Dan Biderman**: They control those sets of weights.

</details>

**Dan Biderman**: 这是属于他们个人的。嗯。

<details>
<summary>Original English</summary>

**Dan Biderman**: It's theirs. Um,

</details>

**Alessio**: 还有米饭。

<details>
<summary>Original English</summary>

**Alessio**: and the rice.

</details>

**Dan Biderman**: 好的，先让汤汁沸腾一下。所以，用户会有动力去不断培育它，就像养一个电子宠物一样。你越精心照料它，它就越聪明。这就是我们希望能创造出的持续学习体验。这甚至可以被推向极端的单人尺度。

<details>
<summary>Original English</summary>

**Dan Biderman**: Uh, and they're incentivized to let let's let it boil a little bit now. Yeah. Um, so they're incentivized to we can we can put the spices. So they're incentivized to to make it better in the same way that you would work with with a Tamagotchi. The more you nurture it, the happier it is. And that's the kind of thing we would like to create with models. So that's the ultimate continual learning. And we think on the extreme scale, on the single human scale. Um,

</details>

**Dan Biderman**: 但正如研究发现的，这不仅是一个纯算法研究问题，更是一个庞大的系统基建（Infra）工程。从更长远的角度看，这些模型更新实际上应当在用户的边缘设备上本地运行。

<details>
<summary>Original English</summary>

**Dan Biderman**: turns out this is not just a research problem. That's a major infra problem. And in the long long term, I do think these things will actually run on people's devices.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 我们已经看到，目前最新的个人电脑端硬件架构正在快速逼近本地流畅运行万亿参数大模型推理的性能门槛。

<details>
<summary>Original English</summary>

**Dan Biderman**: And we're seeing right now the the new hardware on personal computers is already uh you know soon approaching the ability to run inference on close to trillion parameters models

</details>

**Dan Biderman**: 这对个性化智能的发展将具有非凡的意义。但眼下，高密度、富含专业壁垒的超大型语料库依然主要集中在企业端。

<details>
<summary>Original English</summary>

**Dan Biderman**: uh which will be very interesting for that kind of personalization. But in the shorter term we do think that uh the kind of large corporate of knowledge very dense with a lot of expertise u can be found in the enterprise um that's where people spend most of their time that's where AI is is actually being used the most yeah

</details>

**Dan Biderman**: 所以我们先从企业端切入。我们打赌，将参数高效微调方法（如 LoRA、墨盒适配器、外部存储记忆层等我们团队曾深度参与研发的技术）与上下文窗口管理相结合，是解决这个难题的最佳方案。

<details>
<summary>Original English</summary>

**Dan Biderman**: so we we we go there and that's our bet and there we're our bet is that parameter efficient fine-tuning methods like chloral like cartridges like memory layers different things we we contributed to as as a research team um can actually represent knowledge and can be combined with other methods that are like context management traceable methods that that people can can use and understand and and audit.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 这是一个软硬件和算法的有机结合体。

<details>
<summary>Original English</summary>

**Dan Biderman**: So it's a combination.

</details>

**Alessio**: 明白了。

<details>
<summary>Original English</summary>

**Alessio**: Gotcha.

</details>

**Dan Biderman**: 这又回到了那个做饭的类比：好的大厨不仅要有精美的食谱和烹饪日志，还要有一个能在一次次下厨中不断调整、积累直觉的神经系统。

<details>
<summary>Original English</summary>

**Dan Biderman**: So again, it's like it's like the chef that has the cookbook and it has the recipes, has the diary, but also has the nervous system that learns from every session.

</details>

**Alessio**: 这里已经开始沸腾了，这边的电磁炉热效率很高。

<details>
<summary>Original English</summary>

**Alessio**: So it's boiling here. It's all Yeah. Pretty efficient here.

</details>

**Dan Biderman**: 是的，非常强劲的炉子。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, very powerful stove.

</details>

**Alessio**: 太好了。我们稍微把火力调到中低档。

<details>
<summary>Original English</summary>

**Alessio**: Great. And then medium, low, then wanted.

</details>

**Dan Biderman**: 我们来搅拌一下。是的。刚刚加盐了吗？

<details>
<summary>Original English</summary>

**Dan Biderman**: Let's mix it up. Yeah. Salt. Did you put some salt?

</details>

**Alessio**: 好的，我这就放点盐进去。

<details>
<summary>Original English</summary>

**Alessio**: Here. I'll put some salt in.

</details>

**Dan Biderman**: 我们一会儿就能吃上 Alan 友情提供的黄金姜黄饭了。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, we're going to have yellow rice courtesy of Alan.

</details>

**Alessio**: 是的，太好了。我们很快就大功告成了。

<details>
<summary>Original English</summary>

**Alessio**: Yes. Um, great. Well, we're nearly there.

</details>

### 上下文内化与外部化的选择艺术

**Dan Biderman**: 是的，先让这些小家伙们在锅里焖一下。在解决这个难题时，你们如何界定哪些数据应当被彻底内化到模型权重中，而哪些数据应当依然交给外部的 RAG 处理，又在什么时候进行智能体的统筹编排？

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. We'll let the these guys cook for a little bit. with what you guys are attacking, how do you determine what you know should live inside of the weights, what should still kind of be handled with rag, um wher things should be orchestrated.

</details>

**Dan Biderman**: 这是一个极其开放且前沿的研究课题。这不仅仅是 AI 或我们公司在研究的问题，更是人类在探索自身记忆机制时从一开始就面临的根本疑问。也就是说：什么样的知识我们应当彻底融入大脑化为直觉？而什么样的知识适合留在外部纸面上？一个人有必要强行记住他这一生看过的每一帧画面吗？那些拥有绝对记忆超能力（超忆症）的人，其实往往活得并不轻松。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. So, this is a major open question I would say for us and for everyone else and it's not just an open question in in uh AI and in a startup. It's an open question in the study of human memory from its its uh inception. And it's like what kind of knowledge should be internalized and what kind of knowledge should be externalized? Does it make sense for you to remember every thing you've seen as a person? Uh people who have that uh often are not enjoying that capability. Yeah.

</details>

**Alessio**: 是的，那甚至会产生严重干扰，甚至是痛苦的。

<details>
<summary>Original English</summary>

**Alessio**: And it's it can be very distracting. It can be uh it's sometimes very scary.

</details>

**Dan Biderman**: 没错，一定程度的遗忘是健康且必须的。所以有些东西应当记在权重脑区里，有些则应该写在纸面上。这现在依然是个开放问题。最理想的方法是训练模型自己去判定：不需要外部监督信号，大模型可以凭借自我认知判断出“这个问题我可以直接在大脑里给出答案，而那个复杂问题我最好去翻阅外置的数据库笔记”。这涉及到数据的显著性（Saliency）、在数据流中重复出现的频次，以及当大模型直接记住这个事实后能带来多大的推理捷径。例如，你今晚在酒店的房间号，记住它固然好，但遗忘也是无所谓的；然而，你家人的电话号码或家庭住址则是至关重要的知识。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um so a certain amount of forgetting is healthy. Certain things you want to remember in the weights and certain things you want to put in in text. So I would say it's an open research problem. The way to work on it is to train models both to train models to manage it themselves and that's an active area for us have the model know like without any explicit supervision signal to determine this kind of stuff I can pull from my brain and that kind of stuff I rather keep in notes and you can imagine these kinds of things uh relate to like the salency of certain parts in the data how how often the frequency at which they repeat and the affordances of like what can you do when you know this fact from your brain? Uh you can imagine that uh remembering I don't know remembering uh the your room number in a hotel for tonight is less important than remembering your partner's phone number or remembering your address. Right? So

</details>

**Alessio**: 所以是高信号强度的数据。

<details>
<summary>Original English</summary>

**Alessio**: so it's higher signal data to

</details>

**Dan Biderman**: 没错，高信号数据。而且如果完全由人类手工用启发式规则硬编码什么该进、什么该退，就会陷入无休止的“打地鼠”死循环。每一家公司、每一个知识库的数据特征都完全不同。所以终极的圣杯，应当是让大模型在无拘无束的训练中，学会自我管理：不仅拥有可以随时涂涂画画的记事本，还拥有一个基于关联记忆的参数高效权重脑区，由它自己在训练过程中摸索如何调用这两者。我们正致力于此，但仍需大量的核心突破。我希望最终我们能够功成身退，让模型完全自我做主。

<details>
<summary>Original English</summary>

**Dan Biderman**: higher signal data. And now the thing is if you start manually uristically saying this is in this is out then it becomes a whack-a-ole. Okay. Every every person in every enterprise has different data and you can't really very easily pick and choose what goes in, what goes out. So the holy grail is have the model learn for itself. Have it operate with a notebook where it can take notes, have it operate with a with a brain associative parameter efficient thing that it can read from and have it decide when to go to each and do this with training in an unconstrained way. And we're working on it and more breakthroughs are needed. But I think that that is the dream that the model learns what what comes in and what comes out and we get out of the way.

</details>

**Alessio**: 明白。所以这是你们想达成的终极状态：模型完全自主处理，不再需要人类在循环中频繁干预和手动检索。

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. Okay. And so that's the end goal you want to achieve where it's completely autonomous. So there's no human in the loop to kind of tell it what to fetch. Um

</details>

**Dan Biderman**: 循环中的人类应该只作为终端用户存在。如果用户选择显式下令“这个别记”或“这部分一定要背下来”，模型应当听从指令。

<details>
<summary>Original English</summary>

**Dan Biderman**: the human in the loop can be the user and if the user chooses to say keep this in or keep this out. We would like the model to listen to the user.

</details>

**Alessio**: 好的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 但我们不希望模型在每一个原子步骤上都**依赖**人类的介入。用户并不喜欢那种保姆式督导大模型工作的感觉。而且在我们的架构下，用户如果给出一个 thumbs up（点赞）或 thumbs down（点踩），并不是像在一般大模型对话网页端上那样单纯作为云端服务商未来迭代的背景板，而是模型会实实在在地为此消耗算力进行训练，把你的反馈真正“锻炼”进模型权重里，直至完美匹配你的喜好。这就是我们建立用户信任的方式——让用户切实体会到，他们的模型被用心定制了，而且是只为了他们自己。

<details>
<summary>Original English</summary>

**Dan Biderman**: But we would not like to depend on the user. Right. So user feedback is something we can learn from and we can learn from implicitly but we don't want a person supervising every step because that's not the way uh people enjoy using uh language models. But I would say the kind of models that we're building uh unlike other models where you you do thumbs up and thumbs down and you're basically like helping the provider maybe in the next version give you something that's more workable. Yeah. here. If you give a thumbs up or thumbs down or you say something, you know that someone is going to scale compute on what you said and someone's going to go and practice uh to get better at what you said. And this is kind of the thing we want to get to like building trust with the user that they're listened to and they're making a model that's better and it's not generally better for everyone, it's better for them.

</details>

### 团队文化与学术工程人才的配对

**Alessio**: 明白。这样的闭环反馈循环要紧密得多。一般大模型服务商的反馈机制对单次使用的改善确实微乎其微。如果能动用实时的微调机制，那确实可以做到绝对的确定性，把用户的偏好钉在权重里。

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. So the benefit is it being a tighter loop um compared to the like you said a general model provider the UI having a thumbs up thumbs down you don't know if that's actually going to contribute to the feedback. Yeah, there's tighter loop and we use different machinery. If if we allow ourselves to use the machinery of training, we know we can we can hammer that in. There's no uncertainty about it. And and

</details>

**Dan Biderman**: 还有一点很关键：用户所说的并非永远都是对的。即便是像我这样的人，我们也会说错，指责模型犯错实际上错的是我们自己。

<details>
<summary>Original English</summary>

**Dan Biderman**: another important thing to say is not everything that a user tells you is ground truth, right? Not all of us, including myself, are Einsteins and we can say things to the model where we think we're right and the model is wrong.

</details>

**Dan Biderman**: 随着模型能力的飞速跃迁，未来它们在几乎所有领域都知道得比我们多。所以模型也需要拥有甄别有价值反馈和无意义噪声的判别能力。但只要把训练的目标函数设对，让模型自我去探索和调整才是终极方案。

<details>
<summary>Original English</summary>

**Dan Biderman**: And increasingly the models will get better and increasingly they'll know more things than we do. So the model in some way has to learn and understand and kind of like discern what which feedback is valuable and which feedback should be ignored. But there are two I think the holy grail is to get out of the way and have the model learn it if you define the right objectives for training.

</details>

**Alessio**: 懂了。让开道路，让模型自己去学。在这个过程中，有没有什么时刻让你深刻感受到了未来已来，或者当前技术依然缺失了什么？因为让大模型彻底自主管理本地的持续学习，显得极其宏大且富有挑战性。即便只是在目前的软件代码补全智能体中，多文件修改依然很容易翻车。

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. Okay. So get out of the model's way. Have there been any moments that have really kind of shown you what is still needed like or what's still possible because it seems very ambitious to be in an end state where a model autonomously can handle this all. Um and I think like multi- aent setups and even right now too just constrained to coding still has problems. Yeah.

</details>

**Alessio**: 更不用说在真实的企业严肃工作流程里，试错的容忍度极低，很多时候根本不允许出错。

<details>
<summary>Original English</summary>

**Alessio**: Um and so I guess when you get to knowledge work and to specific enterprises it seems a lot higher stakes. Yeah.

</details>

**Alessio**: 所以你目前看到了哪些令人兴奋的、可能实现破局的关键进展吗？

<details>
<summary>Original English</summary>

**Alessio**: Um and you can't make as many mistakes. And so have there been moments or even research topics that you're kind of seeing great progress in right now that can get you there?

</details>

**Dan Biderman**: 我们会在接下来的几周和几个月里陆续分享一系列震撼的研究成果。目前先卖个关子。不过核心的主题，正如当前整个学术和工业界都在密切关注的，正是关于 **Token 效率** 的飞跃——也就是模型用极少的资源去寻找答案和定位核心证据的能力。这也代表了我们对“智能”的本质理解：更聪明并不代表要烧掉更多的算力，而是在面对高难度问题时，消耗更少的资源和能量。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, I would say like we're we will share more of our results like in the coming weeks and months and we're kind of keeping keeping it. Yeah. But I would say the the the theme is and the kind of thing you're seeing and we're not the only ones seeing it, but I would say like we're looking very closely into it is is behaviors around token efficiency, the ability of the models to go where they need to go and solve things faster. Um and and basically it's it's this kind of view of intelligence where getting smarter means um exerting less energy u to to solve increasingly harder problems. Yeah.

</details>

**Alessio**: 好的。针对“Token 效率”，你觉得模型路由（Model Routing）在未来扮演什么角色？我猜对于某些简单的任务，极其廉价的开源模型就可以胜任；而对于复杂的、需要一锤定音的任务，直接上最聪明的闭源模型，反而比用便宜模型来回尝试百十次消耗的综合算力成本更低。

<details>
<summary>Original English</summary>

**Alessio**: And these are the kind of things we're going for. Um and and a lot of it it comes into into life in the form of like efficiency and speed but we will share more of that soon. Um I guess on the token efficiency point, do you also heavily consider like model routing? Because I assume there may be some cheaper models that may do the same job for much less, but there may be some tasks that it may take a much cheaper open source model like $100 worth of tokens when a much smarter model may be able to do it in one shot like very quickly for much cheaper.

</details>

**Dan Biderman**: 路由确实是个极具吸引力的方向。这也解释了为什么目前有这么多的企业和科学家在这个方向上倾注心力，因为我们绝大多数时候都在拿着大炮打蚊子（Overkill）。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, I would say that um routing is an interesting thing. uh and and it there's a reason so many uh enterprises and computer scientists are looking into it because uh we have models that are overkill for many things.

</details>

**Alessio**: 确实，你不需要前沿模型来告诉你做肉丸需要放多少盐。

<details>
<summary>Original English</summary>

**Alessio**: Yeah,

</details>

**Dan Biderman**: 或者下多少水。

<details>
<summary>Original English</summary>

**Dan Biderman**: you don't need Fable to tell you how much like um

</details>

**Alessio**: 没错。

<details>
<summary>Original English</summary>

**Alessio**: water to put

</details>

**Dan Biderman**: 盐和米饭的配比。

<details>
<summary>Original English</summary>

**Dan Biderman**: soft to put and rice and stuff.

</details>

**Dan Biderman**: 但同时，你必须在大脑快要超载的时候，准确知道什么时候该求助于外置的超强大脑。所以路由肯定是方案的重要组成部分。但路由也没那么简单，真正做过的人知道，训练一个靠谱的路由模型是极具挑战的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um at the same time, you do you do need to know when to go to Fable when you are trying to crack something that's that's uh that's above your pay grade. Um so I think c routing is a great direction. Um routing too it's not that easy as someone who's worked on it you can train uh

</details>

**Alessio**: 在这个过程中，面临的最关键工程痛点是什么？

<details>
<summary>Original English</summary>

**Alessio**: or what are the main challenges having the experience of seeing the difficulties of routing.

</details>

**Dan Biderman**: 我们并不指望靠 Engram 单枪匹马做出一款吞噬所有细分工作流的庞然大物。未来的图景必定是多模型共存的。我们的定位就像是你最得力的贴身助手或员工：它熟悉你的一举一动和全部数据，帮你打理日常，并在恰当的时候，带着精确整理过的上下文去向高成本前沿模型发起咨询，甚至让那些高成本模型在后台连续工作几天为你解决最难的关卡。所以路由很棒，但作为一个学术研究领域，它还很不成熟，依然有大量的攻坚战要打。模型版本在疯狂迭代，路由策略也随之剧烈摇摆。

<details>
<summary>Original English</summary>

**Dan Biderman**: So I think routing will be part of the solution there for sure and I think many people not just myself say the solution is multimodal. It's not engram taking over as one model and you teach it things and yeah and uh you can close Stargate. Um that's not our approach here. Yeah. Um the solution will involve some form of routing. Um and in that part of routing, our our thing would be like, you know, your best friend or your employee. You cannot fire someone who's been looking over your shoulder the whole time and can tell you where to look, where to focus, and can even go out and ask fable things in a more targeted way with more context that Fable can then go and work on it for days and solve very high stakes tasks for you. Um so I think routing is great. Uh it's just u it's just uh like any other research area. Uh it's an unsolved thing. There's been progress on it, but a lot of more work is required to actually route things to the the right model at the right time, the right cost. Um and models are continually updated. Uh versions are coming out. So yeah.

</details>

### 持续学习的系统与算力工程挑战

**Alessio**: 确实。目前还有许多未决的问题。现在我想把话题引向你们的团队。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. Okay, that makes sense. It seems like there's still a lot of open questions and even some of the work you're doing is confidential, which makes sense. And as you'll release more, I guess now shifting towards a team. Yeah.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um yeah.

</details>

**Alessio**: 带着如此背景多元的成员工作是怎样一种体验？你们的团队里不仅有你读书期间的教授，还有很多从知名博士项目毕业或中途退学加入的人，比如 Jack。

<details>
<summary>Original English</summary>

**Alessio**: How is it like working with such a mixed group of folks like some who had professors um while you were doing studying and some that you also met and have left their PhDs or finished their PhDs as well like Jack

</details>

**Alessio**: 拥有这样一个多元的顶尖学术精英智囊团。

<details>
<summary>Original English</summary>

**Alessio**: um and yeah having such like a diverse group.

</details>

**Dan Biderman**: 我想说，我们的团队有很多显著的强项。但我不太确定“多元化”是不是其中之一（笑）。因为如果你看我们公司的合照，你会发现里面清一色全是高浓度学术背景的研究员。

<details>
<summary>Original English</summary>

**Dan Biderman**: So I would say uh there's many strengths to our group. Um I'm not sure diversity is one of them. So if you're watching this we have a lot of researchers.

</details>

**Alessio**: 确实，你们可以在团队多元化上再做做文章（笑）。

<details>
<summary>Original English</summary>

**Alessio**: Uh we could we could divers we could diversify a little bit.

</details>

**Dan Biderman**: 没错。但在这个极其窄长且精深的利基市场里——即持续学习、模型长时记忆、将千亿级知识高效泵入大模型参数权重里——我认为我们团队是全世界最顶尖、最垂直专业的一支铁军。而且我们的办公室非常有乐趣。Jack 真的特别幽默。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um I would say um for this niche that we're trying to solve which is memory and continual learning taking knowledge shoving it into weights. I think our team is the most specialized team in that in that kind of thing. Uh and our team our team is fun. You know Jack Jack is is a fun guy.

</details>

**Alessio**: Jack 确实很有活力。

<details>
<summary>Original English</summary>

**Alessio**: Jack is a very fun guy.

</details>

**Dan Biderman**: 他非常善于指导我们如何把极度晦涩的学术黑话转化为清晰直白的公司内外沟通逻辑。Jesse 也扮演着非常关键的互补角色。她长期致力于研究在机器和人类的紧密闭环中，人机协同的边界在哪里。我和 Sabri 稍微偏系统底座和工程架构一点，Scott 和我则专注于统计学底座。正如你所说，我们没有那种传统意义上的多元性，但在大模型研究与系统工程的不同子领域里，大家的技能树点得很不一样。我们目前的策略是，让经验老到的学术大佬，去搭配那些刚从伯克利和斯坦福出山、思维极其敏捷且充满活力的年轻一代天才研究员（比如 Chisa 和 Drew）。

<details>
<summary>Original English</summary>

**Dan Biderman**: uh and and Jack is teaching us a lot of things about how to how to think clearly, communicate our ourselves clearly internally and to the external world. Jesse in the same way very complimentary kind of like approaches. Uh she thought a lot about how humans and AI work together uh in in this closed loop of a machine and and human. Um, yeah, Sabri and I were a tiny bit more on the on the systems side and I was Scott and I worked on statistics. Yeah. So, it's all researchers. It's not diverse in this kind of way, but it is, as you said, diverse in our inclinations. Some of us are more mathy, some of us are more systemsy, some of us are more like AI leaders. And so, it's been interesting. The way we try to do this is to take those PhDs with a lot of experience and pair them up with like those kind of uh you know up and coming rising uh cracked types that that have joined our company. Uh for example, Chisa or Drew from Stanford and Berkeley respectively.

</details>

**Dan Biderman**: 他们都手握数篇顶会论文，带着一往无前的冲劲杀入这个战场。我们安排大牛和他们结成对子，这样可以在他们要踏入不必要的学术“兔子洞”时及时将其拉住，提供过来人的宝贵直觉。老中青两代思维火花的碰撞让我们的办公室极其活跃。在 2025 年的秋冬，那是前沿实验室疯狂抢人、全行业被“AGI 焦虑”笼罩的魔幻时期。但我们所有创始人从第一天起就极其冷静：我们知道这里绝不能办成一个单纯发表论文的学术沙龙或实验室俱乐部。

<details>
<summary>Original English</summary>

**Dan Biderman**: They're they have research backgrounds and have written papers. um but they're kind of um you know entering this field with a lot of momentum and we like to pair them up with someone who's been who's been around the field for a few years has some intuitions can warn them from the rabbit holes and this I think powerful combination of different levels of expertise uh different levels of freshness of thought uh is making our place an interesting one and I would say culturally all of us from day one uh in the in the fall winter of 25 which is was a crazy time in terms of frontier lab uh recruiting and and and AGI anxiety I would say all of us entered into the startup world in a very sober way knowing that it's not just a research club in here it's not just a drone club in here

</details>

**Alessio**: 对，真正缺失的是产品，而产品是需要销售和分发渠道的。

<details>
<summary>Original English</summary>

**Alessio**: the thing that's missing is products and products need to be distributed

</details>

**Dan Biderman**: 没错，你必须通过售卖用户真心喜爱的产品，才能赢得在这个残酷战场活下去并继续探索的权利。

<details>
<summary>Original English</summary>

**Dan Biderman**: and you have to earn the right to play um by selling things that people love

</details>

**Alessio**: 我们目前也正为此拼尽全力。

<details>
<summary>Original English</summary>

**Alessio**: so we're working very hard on that as well

</details>

**Dan Biderman**: 有道理。问个好玩的话题：在你们创始人团队里，谁挑剔美食的品味最在线？你们经常一起点外卖或出去聚餐，有没有谁的品味让你赞不绝口？

<details>
<summary>Original English</summary>

**Dan Biderman**: that makesense I guess more of a fun question. Out of founders, who do you think has the best taste in food? I assume you guys sometimes like order food or even like go out like are there some that stand out to you? Cuz

</details>

**Dan Biderman**: 我想说，我的联合创始人 Sabri 的美食雷达极其敏锐。他是个热爱生活的人，极度热衷于搜寻美食。在公司里他是公认的“海陆大餐（Surf and Turf）”狂热爱好者。

<details>
<summary>Original English</summary>

**Dan Biderman**: I would say um my co co-founder Sabri he's he's consistently uh he loves life. He loves good food. He's very well known in the company as someone who's the surf and turf guy.

</details>

**Alessio**: 好的。他连着午饭和晚饭都吃这个吗？

<details>
<summary>Original English</summary>

**Alessio**: Gotcha. uh it will have it for lunch and dinner and

</details>

**Dan Biderman**: 没错。看他点 DoorDash 往往能带给我不少灵感。Jack 和 Jesse 同样也是美食行家，品味极其高雅。和他们一起探店非常有意思。我们目前在一个类似于公寓的温馨小办公室里办公，所以午餐和晚餐大部分时间都在一起吃。

<details>
<summary>Original English</summary>

**Dan Biderman**: um yeah being on door dash with him has been an inspiration for me. Um and I would say I would say um Jack and Jesse have have good taste as well. Great taste as well. Uh yeah, right. It's it's fun to be with them. And we're now at like a small office like an apartment. So we have all the lunches and and often dinners together

</details>

**Dan Biderman**: 这像个家庭，在家里你每天都要面对父母和兄弟姐妹，有时候待久了也挺烦的，但你这辈子都无法忘却这段并肩作战的日子。

<details>
<summary>Original English</summary>

**Dan Biderman**: and it's it's a bit like a family, you know. We at home you see your parents and siblings. Sometimes it's too much, but it's like, you know, you're you're not never going to forget.

</details>

**Alessio**: 听上去确实太温馨了。你给他们做过饭吗？

<details>
<summary>Original English</summary>

**Alessio**: Yeah. No, it does sound very fun. Have you cooked for them yet?

</details>

**Dan Biderman**: 呃，可能做饭的次数还不够多。也许这个周末我应该露一手。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um have I? Um maybe not enough. Maybe I should. Maybe this weekend I'll cook some.

</details>

**Alessio**: 好的，好的。

<details>
<summary>Original English</summary>

**Alessio**: Okay. Okay.

</details>

**Dan Biderman**: 他们在研究的科学前沿上也在“烹饪”各种大餐。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um they're cooking other things. They're cooking stuff on the science. But yeah,

</details>

**Alessio**: 那是实话，他们在研究端大展身手。

<details>
<summary>Original English</summary>

**Alessio**: that's true. They're cooking on the research.

</details>

**Dan Biderman**: 没错，研究的大餐。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. On the research and

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 好的。我觉得黄金饭应该已经熟了。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. That's great. Okay. The rice should be done.

</details>

**Alessio**: 熟了。

<details>
<summary>Original English</summary>

**Alessio**: Should be done.

</details>

**Dan Biderman**: 我们尝一尝？第一口。

<details>
<summary>Original English</summary>

**Dan Biderman**: Do we want to give it a try? Let's see. But we'll see. First bite.

</details>

**Alessio**: 很不错，味道很好。

<details>
<summary>Original English</summary>

**Alessio**: It's good. It's nice.

</details>

**Dan Biderman**: 噢，确实是的。底部的饭明显熟得更透。也可以让它再稍微焖一会儿。

<details>
<summary>Original English</summary>

**Dan Biderman**: Oh, yeah. It is. Yeah. The bottom is definitely more cooked. Um you can also probably let that sit.

</details>

**Alessio**: 那么这些丸子……

<details>
<summary>Original English</summary>

**Alessio**: Now these guys

</details>

**Dan Biderman**: 应该也可以了。我们可以稍微开盖散热。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Would you say this is ready? These guys are probably ready. Um, we can perhaps open it up a little bit.

</details>

**Alessio**: 好的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah,

</details>

**Dan Biderman**: 让汁水再收一下。

<details>
<summary>Original English</summary>

**Dan Biderman**: let it u concentrate a bit.

</details>

**Alessio**: 好的，我们再收汁两分钟。

<details>
<summary>Original English</summary>

**Alessio**: We can let those guys concentrate for a couple minutes here

</details>

### 持续学习的系统与算力工程挑战

**Dan Biderman**: 之后也许我们就可以直接动手了。

<details>
<summary>Original English</summary>

**Dan Biderman**: and then um and then maybe we can cut those things with our hands right now.

</details>

**Alessio**: 你有什么人才招募计划吗？你们目前在招募哪些特定方向的专家？

<details>
<summary>Original English</summary>

**Alessio**: Do you have any call to actions? Are you guys looking for specific folks, hiring for types of researchers?

</details>

**Dan Biderman**: 我们目前在构建一个极其宏大的、能够实现模型持续自适应学习的复杂架构体系。算法研究层面的开放挑战显而易见：你如何在频繁进行本地权重更新的同时避免灾难性遗忘？如何确保极高的数据利用率和极低的更新成本？我们该让模型去学哪些类型的数据？

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Uh I would say like um what we're trying to build which is those systems that continually learn. Obviously there are many open problems on the research side. How do you do this without destroying the model? How you do it in a cost efficient way? Um what data do you learn from? Um and stuff like that.

</details>

**Dan Biderman**: 但除此之外，这更是一个极其困难的分布式系统底座与硬件调度瓶颈问题。

<details>
<summary>Original English</summary>

**Dan Biderman**: But it's also an extremely ambitious infrastructure problem.

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 如果你真的相信未来每家企业甚至每个人将产生兆级 Token 的独有专有数据。

<details>
<summary>Original English</summary>

**Dan Biderman**: If you truly believe in the possibility that there's going to be trillions of tokens of of u

</details>

**Alessio**: 企业数据。

<details>
<summary>Original English</summary>

**Alessio**: enterprise data

</details>

**Dan Biderman**: 或者是个人数据。

<details>
<summary>Original English</summary>

**Dan Biderman**: or even personal data

</details>

**Dan Biderman**: 如果你相信，为每个人、每个团队定制参数高效适配器（Adapter）是未来唯一的个性化出路，那你立刻就会意识到，你的部署系统将面对数百万个完全不同且动态生成的微型适配器。

<details>
<summary>Original English</summary>

**Dan Biderman**: and if you truly believe that we can get to the level where we have those kinds of parameter efficient adapters for

</details>

**Dan Biderman**: 这些适配器散落存在各处。

<details>
<summary>Original English</summary>

**Dan Biderman**: every person and team you suddenly think about deployments that involve

</details>

**Dan Biderman**: 在运行推理的一瞬间，系统必须以极其恐怖的速度，把它们从冷存的固态硬盘中泵入 GPU 显存里。

<details>
<summary>Original English</summary>

**Dan Biderman**: millions of different endpoints stored in different places

</details>

**Dan Biderman**: 并在运行期间实现近乎无感的动态热插拔、热更新。

<details>
<summary>Original English</summary>

**Dan Biderman**: that need to be efficiently read from disk to HPM.

</details>

**Alessio**: 是的，并在推理时动态调用。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. uh and then use that inference time

</details>

**Dan Biderman**: 一旦我们的商业逻辑被全面验证，我们将很快面临极其恐怖的算力负载与完全颠覆传统架构的全新 AI 调度系统设计。所以，目前能够极大地帮助我们的，第一种人是**大模型性能工程专家与底层研究员**——他们能用各种黑魔法让代码在硬件上跑得飞快。目前我们团队里就有几位这样的超级极客。比如我们的 Cade Daniel，他曾是 Databricks 推理优化的核心带头人，也是当前主流开源推理框架 **vLLM** 的核心代码贡献者之一。

<details>
<summary>Original English</summary>

**Dan Biderman**: um and swapped and updated. It's going to be if things work out for us, this thing h will have a massive compute footprint and many new questions on on systems and and balancing of AI workloads in new ways. So the kind of people that I think um could enjoy them and help us a lot are those uh one uh LLM kind of um performance engineers, research engineers who know how to make things go burr. We have some of them go. Um and we have uh Cade Daniel who uh was one of the inference uh leads at databricks and one of the core contributors of VLM

</details>

**Dan Biderman**: 我们整个公司都极度崇尚硬核的系统开发。我们非常需要拥有大型 API 开发经验、大规模向量及图数据库调优经验的**系统架构师与基础设施工程师（Infrastructure engineers）**。他们将在我们这里面对前所未有的底层系统设计难题。

<details>
<summary>Original English</summary>

**Dan Biderman**: and we are all kind of like u systems inclined but we think infrastructures engineers um people who know how to work uh and um and build those large APIs and databases I think would have very fun time working on questions that they can't find in other places.

</details>

**Alessio**: 是的。我们随时张开双臂欢迎有创意、想干大事、敢于打破陈规且渴望用卓越技术改变世界的人加入我们。

<details>
<summary>Original English</summary>

**Alessio**: Mhm. Um yeah and and generally like we always are are open to to smart and creative people who think out of the box and and are committed to to to working on interesting problems.

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 好的。

<details>
<summary>Original English</summary>

**Alessio**: Uh yeah.

</details>

**Alessio**: 真的很棒。你们团队融合了极具创造力的研究科学家，同时正如你所说，还有着对底层系统架构工程怀有极度热忱的硬核工程师。

<details>
<summary>Original English</summary>

**Alessio**: No that's that's great. It seems like a very creative mix of researchers and people also care about the infrastructure as you said.

</details>

**Dan Biderman**: 没错。刚才说话期间，我脑子里突然闪过一件事：

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Yeah. And also I wanted to say something. I guess I was just thinking about it while I was talking before that

</details>

**Dan Biderman**: 关于我们这种基于权重的持续学习方法：

<details>
<summary>Original English</summary>

**Dan Biderman**: a lot of the use cases for this kind of training and continual learning

</details>

**Dan Biderman**: 我们放一点……

<details>
<summary>Original English</summary>

**Dan Biderman**: uh involve um

</details>

**Alessio**: 把汁收得再干一点点。

<details>
<summary>Original English</summary>

**Alessio**: let's give it a teeny bit more

</details>

**Dan Biderman**: 好的。

<details>
<summary>Original English</summary>

**Dan Biderman**: bit less fluids there.

</details>

**Alessio**: 没问题。

<details>
<summary>Original English</summary>

**Alessio**: Okay.

</details>

**Dan Biderman**: 核心的理念在于，对“高效率”的追求与对“高智能”的追逐在底层是无法割裂的。有些人可能会产生误解，认为做高效率、帮企业省钱的轻量级技术是便宜货，无法进入前沿模型第一梯队，这种观念在科学逻辑上是彻底错误的。

<details>
<summary>Original English</summary>

**Dan Biderman**: So the the point for me is the principle is any kind of like efficiency and intelligence they cannot really be decoupled. Sometimes people think if you're building something that's more efficient that can save you dollars, therefore you're not in the premium category, you're in the uh you know you're making the the cheaper product and that and intelligence this is just um you know purely wrong right so

</details>

**Alessio**: 嗯哼。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 你用同等或更少资源做到的事情越多，未来面对更宏大的场景时，你的潜力就越恐怖。目前大模型行业的 Scaling Law 依然停留在“做更多需要堆更多算力和参数”的堆料逻辑上。

<details>
<summary>Original English</summary>

**Dan Biderman**: the more you can do with less the more ambitious tasks you can solve longer term um so I think that um the current paradigm of scaling with AI has been doing more with more.

</details>

**Alessio**: 确实。

<details>
<summary>Original English</summary>

**Alessio**: Mhm.

</details>

**Dan Biderman**: 这极大拓展了整个行业在通用智能上的广度，并且在未来很长一段时间内依然有效。

<details>
<summary>Original English</summary>

**Dan Biderman**: Uh and it took us extremely far and it will keep being a valuable way to to build intelligence.

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Dan Biderman**: 但我认为下一代大模型的底座范式，正如各大顶尖实验室目前也逐渐达成共识的，必然包含“以少博多（Doing more with less）”的效率跃迁。这是跨越长时视界和解决最高维科学探索难题的先决条件。这也是我希望在超越企业商业效率之外，带给这个世界的技术图景。

<details>
<summary>Original English</summary>

**Dan Biderman**: But I think the next paradigm and many leaders of the labs are seeing it involves certain element of doing more with less um to take on longer horizon tasks and harder problems generally. So I think going beyond enterprises and going beyond efficiency that's where I hope to go.

</details>

**Alessio**: 好的，这完全合情合理。从双向共同提升去考量，确实是一条极具远见的道路，特别是面对极其宏大宏伟的目标时。

<details>
<summary>Original English</summary>

**Alessio**: Yeah. uh if we solve and and and the challenges that we're facing right now. Okay, that makes sense. I think thinking of both couples does seem very important, especially as you want to, like you said, do more ambitious tasks.

</details>

### 烹饪成品品尝与未来展望

**Dan Biderman**: 是的。我们要把菠菜拌进去，还是就让它在汤汁里闷熟？

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. Should we mix in the spinach or just let it steam?

</details>

**Alessio**: 拌进去尝尝吧。

<details>
<summary>Original English</summary>

**Alessio**: Try mix it up. Let's try it.

</details>

**Dan Biderman**: 闷一下会变软。然后我来切这个柠檬，把柠檬汁挤在白酱汁里。

<details>
<summary>Original English</summary>

**Dan Biderman**: It will steam it soften a little bit. And I could cut this lemon. Yeah. And then just squeeze the lemon in.

</details>

**Alessio**: 好的，挤在酱汁里对吧？

<details>
<summary>Original English</summary>

**Alessio**: Okay. The sauce, right?

</details>

**Dan Biderman**: 是的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah.

</details>

**Alessio**: 好了，轻轻挤压。柠檬风味很出彩。太棒了。大家去哪里能联系到你们？

<details>
<summary>Original English</summary>

**Alessio**: Okay. Don't want to squeeze this one. This one adds a little less, but Amazing. And where can people find you?

</details>

**Dan Biderman**: 去哪里找我们？

<details>
<summary>Original English</summary>

**Dan Biderman**: Where can people find us?

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah, I got it.

</details>

**Dan Biderman**: 我们的官网是 `engram.com`。

<details>
<summary>Original English</summary>

**Dan Biderman**: They can find us at engram.com.

</details>

**Dan Biderman**: 也可以在旧金山找到我们。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, they can find us in SF.

</details>

**Dan Biderman**: 想要深入交流底层学术或系统工程的话，可以直接发邮件到 `dan@engram.com` 联系我。另外，除了最底层的算法和科研，随着公司规模迅速铺开，我们在产品经理和商业化运营端也放出了大量职位。希望听到来自行业内聪明大脑的声音。

<details>
<summary>Original English</summary>

**Dan Biderman**: Um, they can write to me uh at dan@angram.com um to talk about things. Um, and yeah, I would say like as we're scaling up different parts of the company that involve engineering, that involve product and business, there's a lot of things to talk about beyond the the frontier AI type research. Uh, and there's a lot for us to learn from smart people.

</details>

**Alessio**: 太棒了，很激动人心。我们该开动了吧？

<details>
<summary>Original English</summary>

**Alessio**: Great. Awesome. That's exciting. Should we try it?

</details>

**Dan Biderman**: 是的。在此我向所有前沿 AI 实验室的大佬发起邀请：欢迎来到我位于旧金山 Noe Valley 的家，和我一起下厨做菜，在美食中碰撞灵感。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah. I I challenge every every leader of a Neolab to come to my house in Noi Valley and cook things with me and uh and I'm sure we can learn a lot from each other.

</details>

**Alessio**: 干杯。

<details>
<summary>Original English</summary>

**Alessio**: Cheers.

</details>

**Dan Biderman**: 好吃。

<details>
<summary>Original English</summary>

**Dan Biderman**: Good.

</details>

**Alessio**: 味道确实很绝。

<details>
<summary>Original English</summary>

**Alessio**: I think it turned out well now.

</details>

**Dan Biderman**: 是的，非常美味。

<details>
<summary>Original English</summary>

**Dan Biderman**: Yeah, very good.

</details>

**Alessio**: 哇，真的太好吃了。我觉得口感里带有一点波斯风情。

<details>
<summary>Original English</summary>

**Alessio**: Wow, that's very good. Um maybe a little bit Persian I would say

</details>

**Dan Biderman**: 搭配这个黄金姜黄饭，太赞了。

<details>
<summary>Original English</summary>

**Dan Biderman**: um with the yellow rice. So great.

</details>

**Alessio**: 我要被圈粉了。好的。

<details>
<summary>Original English</summary>

**Alessio**: I'm a big fan. Okay.

</details>

**Dan Biderman**: 黄金饭与菠菜以及肉丸的汤汁融合在一起，口感很温润，丸子也很软。

<details>
<summary>Original English</summary>

**Dan Biderman**: Sean rice is amazing. Rice and finish is amazing on this one. Actually I'm just going to finish the whole thing after meatballs a bit softer than

</details>

**Alessio**: 是的。

<details>
<summary>Original English</summary>

**Alessio**: Yeah.

</details>

**Swyx**: 整个节目中我都在假装自己是烹饪专家。

<details>
<summary>Original English</summary>

**Swyx**: Swig the entire show I pretended to be the cooking expert here.

</details>

**Dan Biderman**: 好的。

<details>
<summary>Original English</summary>

**Dan Biderman**: Okay.

</details>

**Swyx**: 刚刚简直是疯狂极了。开个玩笑，这个成品打分的话，10 分满分绝对能拿到 8 分甚至 9 分。

<details>
<summary>Original English</summary>

**Swyx**: It has to be pure crazy. Just kidding. This is like a eight out of 10. 9 out of 10.

</details>

**Alessio**: 很好。我想这大概就是我们今天的主要内容了。它确实大获成功。你感觉如何？今天好玩吗？

<details>
<summary>Original English</summary>

**Alessio**: Great. But yeah. No, I think that's basically it. It turned out pretty well. I mean, how was it? Was the fun? Did you enjoy it?

</details>

**Dan Biderman**: 这是我参加过最惬意的播客，很有家的感觉。

<details>
<summary>Original English</summary>

**Dan Biderman**: It was the funnest uh podcast I ever had. Makes you feel at home.

</details>

**Alessio**: 那是心里话。

<details>
<summary>Original English</summary>

**Alessio**: That's true.

</details>

**Dan Biderman**: 在这里很多深奥的科技话题能够以一种极度自然的节奏聊透。

<details>
<summary>Original English</summary>

**Dan Biderman**: Easier to talk about things.

</details>

**Alessio**: 再次感谢你的做客，也希望这是一段有趣的时光。

<details>
<summary>Original English</summary>

**Alessio**: Thank you again for coming and hopefully it was a fun time.

</details>

**Dan Biderman**: 超级开心。

<details>
<summary>Original English</summary>

**Dan Biderman**: It was super fun.

</details>

**Swyx**: 我的神经网络权重已经得到成功微调并更新。

<details>
<summary>Original English</summary>

**Swyx**: My weights have been updated.

</details>

**Dan Biderman**: 太棒了。再次祝你晚安。

<details>
<summary>Original English</summary>

**Dan Biderman**: That's good. Nights again.

</details>