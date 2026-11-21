---
author: AI Engineer
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SUqQlvyI3N8
speaker: AI Engineer
tags:
  - agentic-memory
  - experiential-learning
  - memory-lifecycle
  - multi-agent-system
title: 构建经验记忆基础设施：解决AI智能体重复犯错的演进架构
summary: Sparsh Jain 指出智能体重复犯错的主因在于缺乏可演进的经验记忆。仅增加上下文不仅成本高且降低准确率。他提出了涵盖形成、更新与遗忘、检索的记忆生命周期，并结合离线反思评估循环，使智能体能聚合全团队经验实现能力指数级复利。
insight: ''
draft: true
series: ''
category: ai-memory
area: PAI
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 智能体重复犯错的困境

你和你的 AI 智能体一起工作了过去两年。你积累了两年的经验。你的智能体呢？并没有。

团队里的 10 个人使用同一个 AI 智能体，他们累计获得了 20 年的工程经验。你的智能体却依然原地踏步。它只是一次又一次地重复犯同样的错误。

<details>
<summary>Original English</summary>
You work with your AI agent for the last 2 years. You gained 2 years of experience. Your agent No. 10 people on your team work with the same AI agent. They cumulatively gained two decades of engineering experience. Your agent still there. It keeps on repeating the same mistakes again and again.
</details>

我曾与全球最大对冲基金的一位高管交谈，他说：“Sparsh，问题不在于智能体的 AI 不聪明。问题在于它总是一遍又一遍地犯同样的错误。如果我今天纠正了它，那么在下一次会话中，或者换到另一个团队使用时，它又会犯同样的错误。问题是错误实在太多，我们不可能时刻去逐一改进。我们需要一种机制，或者说一套系统来解决这个问题。”

<details>
<summary>Original English</summary>
I was talking to a senior executive at the world's biggest hedge fund and he said, "Sparsh, the problem is not that the AI of the agents are not smart. The problem is that it keeps on repeating the same mistakes again and again. If I course corrected today, then in the next session or with another team, it just makes that same mistake again. And the issue is that there are so many mistakes that we cannot improve those things at all times. We need a mechanism or we need a system to resolve this issue."
</details>

### 上下文并非越多越好

就在那时，我们意识到所有人都在谈论上下文，所有人都在谈论记忆。大家的答案似乎是：我们只要把所有的上下文、所有的记忆都塞给智能体，它自己就会搞明白。

刚开始这样还行，但很快我们就发现在企业级规模下，问题在于上下文可能过于庞大，将所有事实一股脑提供给智能体根本无法提升性能。

<details>
<summary>Original English</summary>
And at that point of time, we realized that everyone is talking about context. Everyone is talking about memory. And the answer is we just need to take all the context, all the memory and give it to agents so that it will figure out. It was good in the start, but soon we realized at enterprise scale the issue is the context can be too big and giving all the facts to the agents just not increase the performance.
</details>

它增加了成本，增加了工作量，增加了整体消耗的时间，最重要的是，它降低了整体的准确率，降低了性能表现。我们由此意识到：**超过一定限度后，更多上下文并不等同于更高的智能。** 当我们刚起步、拥有较小的上下文基数时，确实如此；但超过某一点之后就失效了。我们需要一种更好的机制和途径来解决这个问题。

<details>
<summary>Original English</summary>
It increases the cost, it increases the effort, it increases the overall time taken and on top of that it decreases it decreases the overall accuracy that is there, it decreases the performance. And there we realized that more context doesn't equal to better intelligence after a point. When you have When we are starting, when we have a smaller context base, yes, it means that, but after a point of time, it doesn't mean that. And we need a better mechanism, a better way to solve that problem.
</details>

### 经验记忆的三层结构

于是，我们回到原点重新思考：为什么人类能随着时间推移变得越来越厉害？

那时我们意识到，人类拥有“经验”与“判断力”的技能。当我们学到新东西、犯下错误并进行纠正时，这种判断力就会随着时间推移愈发清晰、敏锐。而这正是许多智能体所缺失的关键一环。我们当时意识到，先前的记忆机制并没有为我们带来真正的学习。

当我们回过头把系统构建出来后，我们的性能提升达到了 10 倍。

<details>
<summary>Original English</summary>
Here, we went to the back the drawing board and think like how why exactly we humans we get better with time. And at that point of time, we realized we humans have the skill of experience, of a judgment. And this judgment clears gets better with time when we learn something, when we make mistakes, and when we course correct. And that is a missing piece from a lot of these agents. And there we realized that at this point of time earlier, the memory was not learning for us. When we came back, when we built the system, the performance gain for us was 10x.
</details>

我们对记忆机制的最终理解是：它分为两部分——**短期记忆**与**长期记忆**。

短期记忆是工作记忆或活动会话记忆。长期记忆又分为两部分：**基于事实的记忆**与**基于经验的记忆**。

<details>
<summary>Original English</summary>
And what exactly we came upon as the understanding of the memory is it's divided into two parts. The short-term memory and long-term memory. Short-term memory is the working memory or active session memory. The long-term memory is divided into two parts. Fact-based memory and experiential memory.
</details>

这种经验记忆层正是此前一直缺失的部分。它们是从我们与智能体交互的所有经历中抽象出来的经验教训。这也是让人类有别于早期 AI 的关键所在。

进一步地，这一经验层可以细分为三类：
1. **基于案例的（Case-based）**：详细的案例与具体的经验；
2. **基于策略的（Strategy-based）**：身处特定情境时，哪种策略对我们奏效、我们应该采取什么；
3. **基于技能的（Skill-based）**：能够被高度抽象和泛化的内容，将其提炼为一项技能，供智能体反复调用。

这就是我们在智能体中构建经验层的方式。经验记忆带来了切实的帮助。

<details>
<summary>Original English</summary>
This layer of experiential-based memory was something that has been missing now. And these are the abstracted out learnings from whatever we do with agents. And this is what makes we humans different from the AI that was here earlier. And further, this experiential layer can be doubled down into three different categories. The case-based, strategy-based, and the skill-based. Case-based is the detailed case and the detailed learning. The strategy is if you were in that particular situation, then what kind of strategy worked for us and what we should use. And then finally, is something that can be abstracted out, generalized very well. We abstract that thing out into a skill which an agent can use again and again. And this is how we built this experiential layer in the agents. This experiential memory is something that helps.
</details>

### 记忆生命周期：形成、更新与遗忘

在那个节点，我们以为自己已经解决了记忆基础设施的问题。但解决这个问题后，我们才意识到这仅仅是个开端。正因为跨过了这一步，我们才得以看清随之而来的其他更大难题。

当前系统的变化非常迅速：数据漂移、系统漂移、整个环境的漂移。世界每周、每月都在变化，在 AI 的岁月里，一年宛如十年。今天还能正常工作的智能体，一个月或一年后可能就失效了，我们必须深入思考如何对其进行更新。

<details>
<summary>Original English</summary>
At this point, we thought we have solved the problem of memory infrastructure. But, solving this problem made us realize that this is just a start of the problem and there are so many other bigger problems out there that form just because we solved this problem and we are able to see it because we reached this stage. And that is in the current times, the systems are changing very fast. The data drift, the system drift, the overall the whole environment drift. The world is changing every week, every month. An year feels like a decade in the AI years. So, the agent that works today doesn't work in a month or a year's time frame and we need to think through how we update that thing.
</details>

在进行了大量实验后，我们对记忆形成了新的理解：记忆绝不是一次性建好就完事的系统，你必须让它随着时间演进并不断完善。最终，我们确立了这套架构。

记忆基础设施生命周期分为三个部分：**形成（Formation）**、**更新（Updation）**与**检索（Retrieval）**。检索非常关键。

形成部分我们刚才已经理解了。更新部分则是让系统保持演进的关键：当产生新经验或新事实时添加新节点；更新旧节点，或者将不再有用的节点停用；最后则是遗忘机制。

<details>
<summary>Original English</summary>
And once we ran through a lots and lots of experiments, we came up on this understanding of the memory is that it's not just you make the system or the memory once, but it's just you have to evolve or make it better with time. And then in the final case, we came upon this architecture. That memory infrastructure pipeline is divided The lifecycle is divided into three parts. The formation, the updation, and the retrieval. Retrieval is very important. Now, formation we already understood right now. The updation is the part which evolves the system in which you add new notes when there are new experiences or facts. You update the older notes or like deactivate the notes which are no longer useful. And then finally, you have this forgetting.
</details>

在更新环节中，并非所有情况下仅存储最终层的判断就足够了。因为如果你只存最终结果，智能体可能会犯错并退回到先前已删除的旧状态。

因此一种更好的方式是：如果进行浅层调研，它只查看活跃节点；如果是深度调研，它会同时查看活跃节点与非活跃节点。非活跃节点记录了系统推导出最终判断所经历的时间轨迹。

最后是遗忘节点，这极其关键，绝对不能遗漏。

<details>
<summary>Original English</summary>
In updation, only storing the final layer of judgment is not enough in all cases. Because if you just store that, the agent can make a mistake and go back to the older point which had which was earlier and we just removed it. So, a better way is if it's a surface level research, it just looks at active nodes. And if it's a deeper research, it looks at the active nodes and the inactive nodes. And inactive nodes are the temporal journey that the system took to get the final layer of the judgment that is there. And then finally is the forgetting node, which is a must of very important here, and we cannot forget it.
</details>

举个例子：20 世纪后期有一位名叫 Sheriv Sherosky 的人，他拥有近乎完美的记忆力，能够做到 100% 的回忆。

你可能会想，如果我们拥有这种记忆，人生岂不是太美妙了？但科学家和研究人员在研究他的一生后发现，很多时候他哪怕做一些很微小的决定，生活都极其痛苦。因为每一点信息都会争夺相同的优先级和权重；人类一秒钟就能做出的决断，在他脑海里却有上百种念头在互相打架，让他不堪重负。

我们的智能体面临的也是这个难题：如果你不断添加、不断堆积，却不遗忘那些不再真实或不再需要的内容，系统最终就会不堪重负，结果根本无法随时间而改善。因此，你必须具备遗忘机制。

<details>
<summary>Original English</summary>
Let me give you an example. In the late 20th century, there was a person named Sheriv Sherosky. This is a human with near perfect memory with 100% recall. Now, you might be thinking, if we have got that particular memory, our life would have been amazing. But when the scientists and researchers studied his life, they started to realize a lot of times, when he even has to make a smaller decisions, his life was miserable because every point used to compete for an equal prioritization and an equal winning in things for something which we humans can take in a decision in a quick second. It was 100 thoughts fighting in his mind. And he gets overwhelmed. And that is the issue with our agents. If you keep on adding everything, if you keep on accumulating everything, and if you do not forget things which are no longer true or which are no longer required, then you might end up in a state where the system gets overwhelmed, and it the results just doesn't get better with time. So, you need to have a mechanism to forget things.
</details>

### 模型作为验证器与精准检索

搭建起这条管线后，我们开始将这种记忆赋予智能体，构建出了经验型智能体，进而打造出能够自我演进的经验型智能体。

但在那之前，一切依然是手动的。我们原以为已经搞定了，但以如今的能力来看，那其实只完成了半套方案。

试问过去 6 个月里，AI 领域发生了什么变化？模型变得更聪明了，但这只是较小的一部分。更大的突破在于：**模型已经聪明到足以充当验证器（verifier）。** 在此之前，我们始终需要人类介入（human in the loop）来复核一切；而现在有史以来第一次，模型本身的智能足以让我们将其作为验证层内嵌到系统自身中，让系统自主随着时间迭代变强。

<details>
<summary>Original English</summary>
Now, once you build this pipeline, we started with providing this memory to agents. We build this experiential agents. Now, we build this evolving experiential agents. But still, everything is manual. We thought we have solved the problem, but what's possible today, it was just half of the solution. Let me ask you a question. In the past 6 months, what has changed in the AI world? The models have become smarter. But that's only a smaller part. The bigger breakthrough is that the model is so smart enough that it can be the verifier. Until now, the situation was we always have to have the humans in the loop to review everything. But now for the first time, the model is smart enough such that we can bake that thing into a layer in itself as a verifier into the system so that the system gets better with time by itself.
</details>

最后是**检索（Retrieval）**环节。在检索维度上，你系统的性能上限完全取决于检索的性能上限。

你可能会问为什么？举个例子：假设我在旧金山工作，在当地有个家，同时我在纽约也有一个家。我走出办公室后对 AI 智能体说：“打开回家的地图。”半路上我才发觉：“这不是我该去的地方啊。”我这才意识到自己原本是要回旧金山的家。对智能体而言，无论纽约还是旧金山，“家”就是“家”，于是它调出了纽约住所的导航。我由此认识到，无论记忆形成、更新以及拥有的知识和经验有多出色，一旦检索器无法给出正确的信息，一切就毫无用处，整套系统形同虚设。这就是为什么系统的检索部分极其关键。

<details>
<summary>Original English</summary>
And then finally, we have this retrieval part. Now, in the retrieval aspect of things, your system's maximum performance can be just equivalent to the maximum performance of the retrieval. You might be asking, "Why?" Let me give you an example. Let's say I work in San Francisco and I have a home here. I also have a home in New York. I got off out of my office and I asked my AI agent, "Pull the maps for the home." Midway through the route, I realize, "This is not a place where I should be going." And then I realize I wanted to go to my San Francisco home. For the agent, the home is home, whether it's New York or San Francisco, and it put the map for the New York home. And there I realize, no matter how good my system is, the formation and the updation and the knowledge I have and the experiences I have, if my retriever doesn't give me the right information, it's just of no use. The whole system is of no use. And that's where the retrieval part of our system is very, very important.
</details>

当这三部分完备——有了形成、更新与检索——我们便补全了整套记忆基础设施的生命周期。过去，我们的智能体在很多场景下仅收集上下文就要花上 20 分钟；如今，由于我们事先整理好了上下文并且清楚所有脉络，同一个智能体只需 2 分钟即可完成。

这带来的不仅是耗时上的优化。它减少了所需投入的精力，节省了 Token 成本，并在长周期任务中全面提升了智能体的表现，因为它不再需要在我们早已思考透彻的事情上反复耗费算力。

<details>
<summary>Original English</summary>
And then finally, once we have this thing, we have the formation, the updation, and the retrieval, this is how we complete the life cycle of the memory infrastructure we have. And let me tell you, earlier for gathering context for our agent for a lot of cases, it used to take 20 minutes. But now if we have gathered that context earlier and we know what all together, that same agent just takes 2 minutes of time and that's not only the improvement in the timing. It It is improving in the efforts it has to make It can make it It improves in the tokens it costs and it overall improves the performance of our agents in the long horizon task because it doesn't have to think through too much in the things we have already thought earlier.
</details>

### 做梦循环与三条黄金法则

这还只是系统的初阶形态。下一阶段是：如何让系统实现自主演进与经验积累？

具体来说，我们构建了“循环”或“做梦循环（dreaming cycles）”的概念。人类在休息或睡眠时，大脑会自动清理不再重要的琐事，把优先度高的事项推到前台，并将剩下的内容重新归纳整理。这样第二天醒来时，人会感到神清气爽、思路清晰。

我们将这种机制引入到了智能体中。我们构建了循环与评估基础设施：剔除不再重要的内容，更新应当优先处理的事项，重新梳理结构；如此一来，在第二天以及后续上下文不断累积的过程中，智能体就能表现得越来越好。

<details>
<summary>Original English</summary>
And this is just the start of the system. Now the next level comes, that is how we made the system self-evolving and experiential. And in that particularly, we built this concept of cycles, our dreaming cycles. Now we humans have a tendency when we take rest or when we sleep, our mind, it cleans the things which are no longer important. It takes a prioritized items to the front and whatever is left, it rearranges and cleans everything. Such that next day when I wake up, I feel very refreshed. I can think clearly. And that is something we built within the agents. We built this looping and the eval infrastructure such that we clean the things which are no longer important, we update the things which should be prioritized and we rearrange the things such that the next day and whenever the context is getting accumulated, the agent is able to perform better and better.
</details>

搭建起这套基础设施后，早前困扰我们的“智能体记不住任何东西”的难题迎刃而解。如今经过两年的积淀，我们赋予智能体的经验已经超越了我们任何单个个体。

在构建这种经验记忆时，我们总结出了**三条黄金法则**：
1. **切勿倾倒全部内容**：必须记住要做到渐进式披露（disclose progressively）；
2. **切勿以为系统一劳永逸**：绝不能建好一次就假设它永远表现优秀，必须持续改进；
3. **从编写 Prompt 转向编写循环（loops）**：因为唯有这样，才能让整套基础设施为你实现真正的自主运作。

<details>
<summary>Original English</summary>
And then finally, once we build this infrastructure, earlier the issue for us was the agents cannot remember anything. But now with the 2 years of experience, we are able to give more experience to the agents than any one of us humans. And we learned that there are three golden rules when we are building this experiential memory. First, do not dump everything. You have to remember you have to disclose progressively. Second, you cannot make a system once and assume it will always perform good. You have to improve the system continuously. And then finally, instead of writing prompts, you have to move towards writing these loops because that is how you make this whole infrastructure for you autonomous.
</details>

对我们而言的一个实例是：在构建好记忆层（形成、更新、检索）后，在其外围搭建可观测性层。

一旦具备了可观测性，我们便将循环层与评估（eval）层结合起来。这样在每次会话之后、每一天结束之后，系统都会自动提取经验、改进自身、进行独立测试，并最终在真实系统中生效变更。

至于针对整套记忆基础设施的循环机制、评估体系以及安全护栏，是一个非常有趣的话题，我会在下一次演讲中专门展开。

<details>
<summary>Original English</summary>
An example for us is once you build this memory layer formation, updation, and retrieval, you build an observability layer around it. Once we have observability, we build this looping layer combined with the eval layer such that which after every session, after every day, extracts the learnings, improves the systems, test it independently, and then finally make the changes in the real system. Now, this looping, this evals, and the security gardens around the whole memory infrastructure is a very interesting topic. But that's a topic for my next talk.
</details>

### 指数级复利的自主智能体团队

回到我们最初面临的“无法积累经验”的问题：现在有了这套方案，每当智能体与我协作，它就沉淀我的经验；当它与团队中任何一名成员协作，它同样汲取他们的经验。

对于作为人类的我而言，一年时间只能获得一年的经验；但这个智能体由于同时与 10 位团队成员协作，它获得了 10 倍的经验，其成长速度超越了团队中的任何一个人。

正因如此，我们已经开始看到这种“人类加 AI 智能体”自主协作团队的成型。据我所知的一些团队，其产出已经达到了 10 倍甚至 100 倍，因为他们打造的这种智能体基础设施及其背后的记忆系统正在强力赋能这些智能体，使其能力远超团队中最优秀的工程师或员工。

预计在未来 6 到 9 个月内，我们将开始看到越来越多自主 AI 公司的出现，其中的智能体彼此紧密协作，并且牢记一切。

<details>
<summary>Original English</summary>
And coming back to the problem we had that we were not getting experiences. Now, with this thing, we whenever the agent work with me, it gains that experience. Whenever it it works with any one of on my team, it gains that experience, too. So, for me as a human, I'm get gaining getting only 1 year of experience in 1 year, but this agent, since it's working with all those 10 members, it's getting that 10x experience, and it's getting better than any one of us in the team. And now, because of that, we have started to see this autonomous teams of humans plus AI agents combined. And in some of the teams I know, like their team is like 10x or 100x because this agent that they have created, this agentic infrastructure and the memory behind it, it's just that is powering them, it's just empowering these agents such that some of these agents are far better than any of the best engineers or people or employees out there in that team. And soon, like in the next 6 to 9 months, we have we will start to see more and more of these autonomous AI companies in which agents are collaborating with each other, and they just remember everything.
</details>

一旦落地了这些机制，无论你现有的效能如何，都将随着时间实现指数级复利。因为它不仅仅向你一个人学习，它向团队里的每一个人学习，并且与日俱增；以至于在不久的将来，你的企业内部将迎来这样一个阶段：这个智能体在不同领域、不同系统中所习得的知识与经验，将超越我们任何单个个体。

最后我想强调的是：无法从错误中汲取教训的人——或者无法从错误中吸取教训的智能体——注定会重蹈覆辙。构建这套记忆基础设施，重回指数级增长轨道，打造一支 10 倍乃至 100 倍效能的卓越团队吧。

<details>
<summary>Original English</summary>
Such that now, if you implement these things, whatever performance you have, it just will compound exponentially with time because it's not learning only with you. It learns with every member of the team and it gets better and better with time such that in the near future there will be a stage within your enterprise where this agent has learned more than any one of our person in the different domains in the different systems. And I would like to tell this one thing is people who do not remember from the mistakes or the agents who do not remember from their mistakes are condemned to repeat it. Build this memory infrastructure and get back to growing exponentially better and build a 10x or 100x team.
</details>