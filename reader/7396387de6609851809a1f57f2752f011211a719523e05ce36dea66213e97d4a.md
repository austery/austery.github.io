---
author: a16z
date: '2026-09-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tQI35CSNB08
speaker: a16z
tags:
  - mathematics-understanding
  - ai-reasoning
  - problem-solving
  - informal-mathematics
  - knowledge-acquisition
title: 数学的本质、AI理解能力与人类推理的哲学探讨
summary: 文章探讨了数学的本质目标是产生理解而非论文，并对比了不同AI模型在贴近人类推理方面的差异。重点分析了AI在解决埃尔德什单位距离问题等复杂数学难题上的自主创造力，以及数学家如何应对AI浪潮、追求非形式化理解的价值，并展望了数学教育在AI时代应如何培养下一代数学审美和批判性思维。
insight: ''
draft: true
series: ''
category: science
area: knowledge-meta
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### 数学的本质与 AI 的理解能力

**Daniel**：数学的目标从来不是为了生产数学论文，而是为了产生某种理解。也许其中一部分理解能够驻留在模型的权重之中，但对我而言，这种方式感觉相当令人不满意。

<details>
<summary>Original English</summary>

**Daniel**: The goal of mathematics is not to produce mathematics papers. It's to produce some kind of understanding. Maybe some of that understanding resides in model weights. To me, that's like pretty unsatisfying.

</details>

**Host**：对比 Anthropic 与 OpenAI，你能察觉出它们在贴近人类推理方式上有什么不同吗？

<details>
<summary>Original English</summary>

**Host**: Comparing Anthropic with OpenAI, do you detect any differences in how that is similar to human reasoning?

</details>

**Daniel**：它们在完全自主的情况下肯定不擅长于此，但如果给予一些提示，你确实可以让它们做出一些很有意思的事情。数学的很多进步往往来自于“百花齐放”——让人们追随自己的好奇心去探索，随后知识的边界便会以某种相对均衡的方式向外扩展。

<details>
<summary>Original English</summary>

**Daniel**: They definitely are not good at it autonomously, but with some hints, you can kind of get them to do something interesting. A lot of progress in mathematics comes from like letting a thousand different flowers bloom and people pursue their own curiosity and then the boundaries of knowledge expand in some fairly uniform way.

</details>

**Host**：到目前为止，最令你印象深刻的研究成果是什么？

<details>
<summary>Original English</summary>

**Host**: What has been the most impressive result so far?

</details>

**Daniel**：目前为止我最喜欢的由 AI 完全自主得出的成果，是对埃尔德什单位距离问题（Erdős unit distance problem）的解决。之前有一个引理我想证明，但所有前沿模型都做不到。于是我自己手动推导了大量实例，随后意识到：“哦，也许这就是它可能成立的某种原因。”一旦我给出了那个提法，模型很快就证明了那个更完善的陈述。

<details>
<summary>Original English</summary>

**Daniel**: My favorite fully autonomous result by an AI so far is the solution to the Erdős unit distance problem. There was some lemma I wanted to prove none of the frontier models could do it. So I like worked out a ton of examples on my own and I realized oh well maybe like here's some reason why it could be true. Once I had that statement, the models were able to very quickly prove that sort of better statement.

</details>

**Host**：那么数学界究竟应该如何最好地适应并从中获益呢？

<details>
<summary>Original English</summary>

**Host**: How should like the mathematics community kind of best adapt and benefit from this?

</details>

**Daniel**：嗯……

<details>
<summary>Original English</summary>

**Daniel**: Um...

</details>

### 嘉宾介绍与数学家眼中的 AI 浪潮

**Host**：Daniel，非常高兴能邀请到你！Daniel 是多伦多大学的数学教授。多伦多也是我的家乡，所以这让人格外兴奋。不过最特别的地方在于，Daniel 是一位真正一线在职的数学家，而且他一直非常直言不讳地表达自己对数学领域中 AI 演进的看法。我感觉如果两周没跟你交流，就会冒出什么全新的进展，而你总是非常有自己的见解……

<details>
<summary>Original English</summary>

**Host**: I am so excited to have you on, Daniel. And so Daniel is a professor of mathematics at the University of Toronto. Toronto is my hometown, so also very exciting. But the thing that is most special here is Daniel's an actual practicing mathematician and in addition he's been incredibly vocal about his evolving views of AI in math. And so I feel like every if I just don't check in with you, you know, like in two weeks something different has been revealed, and then you're very kind of like what do you call it? So you...

</details>

**Daniel**：我确实有很多观点。

<details>
<summary>Original English</summary>

**Daniel**: I have a lot of opinions.

</details>

**Host**：你确实有很多独到的见解，这正是我想深入探讨的。我最感兴趣的不单单是探讨能力是如何提升的——虽然在数学领域这绝对是各大头条的焦点——而且你对于一线数学家应该如何应对思考得非常深入。这为我们提供了一个机会去探讨数学真正的特殊之处。这不仅仅是“嘿，AI 在这里取得了巨大进展”，而是去深入剖析数学家究竟在做什么。顺着这个思路，考虑到最近的所有进展，或许我们可以从目前对你而言最令人印象深刻的成果聊起，然后我们再逐步展开。

<details>
<summary>Original English</summary>

**Host**: You have a lot of opinions. Exactly. So I want to get into that. So, I mean, you know, one of the things that I'm most interested in is not just like a discussion of how the capabilities have advanced. I feel like in math, you know, that's definitely the headline, etc., but also, you've been very thoughtful about how practicing mathematicians should respond. And so that kind of gives us a chance and opportunity to talk about actually what is special about math, you know, like it's not just like, hey, AI has been really making progress here, but like delve into what actually mathematicians do. And so maybe like with that arc in mind we can start with what has been the most impressive result so far given all the recent progress for you, and then maybe yeah we'll kind of take it from there.

</details>

### 埃尔德什单位距离问题与 AI 的创造力

**Daniel**：好的。现在已经涌现出了很多成果，有些是完全自主生成的，有些是半自主生成的，还有一些则是 AI 的实际贡献根本不明确。它们分布在许多不同的领域，因此我能谈论的也仅限于我有一定专业积累的方向。如果你去问另一位数学家，很可能会得到截然不同的答案。

就我而言，目前最喜欢的由 AI 完全自主完成的成果是对埃尔德什单位距离问题的求解，这一成果大概是在五月中旬公布的。我之所以喜欢它，是因为在某种程度上它显得颇具创造力。以往我们看到的一些成果，往往更偏向于将某些已知的技巧以某种聪明的方式加以应用；或者属于我称之为“最后一公里”的工作——即一组人类数学家已经完成了非常深入的前期工作，然后 AI 只是完成了最后一步。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. So okay, so there have you know now been a lot of results, some of them produced autonomously, some produced like semi-autonomously, some whose like where the AI contribution is just not at all clear. They're in a lot of different areas so anything I say is kind of you know I can only really comment on things that I you know have some expertise on, so it's quite possible that if you talk to a different mathematician you'll get like different answers here. So my favorite like fully autonomous result by an AI so far is the solution to the Erdős unit distance problem, which I think was announced in mid-May. So at least what I liked about that is it seemed to me that like it was in some ways a little bit creative. So I think some of the results we've seen have had kind of the flavor of like you know you kind of take some known techniques and apply them in maybe a clever way, or you I don't know they have kind of been some kind of results I would characterize as like last mile, like where some recent work was done like quite deep work done by a group of human mathematicians and then the AI kind of took the final step.

</details>

**Host**：确实如此。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Daniel**：但在单位距离问题上，这个结果有些出人意料。首先，我个人的感觉是该领域的学者原本普遍认为该猜想是成立的，结果却找到了一个反例；其次，它引入了来自另一个领域的技巧。我认为那些技巧本身并不是特别深奥或新颖，大多是 60 年代的经典思想，但对于研究平面点集构型这一领域来说却是全新的，因此这非常酷。而且随后的发展证明它极富启发性。

<details>
<summary>Original English</summary>

**Daniel**: But yeah, with the sort of unit distance problem, I think it was something where the result was like a little unexpected. So first of all my sense was like that people working in the area thought it was true and then there was a counterexample found, but then also it like brought in some techniques from from another area. I think those techniques were like not especially uh you know like deep or new. They were sort of classical ideas from the 60s, but they were new to this area of studying you know point configurations in the plane, and so that was pretty cool and then afterwards we got to see like it was kind of fruitful so...

</details>

**Host**：一群数学家随后借鉴了这些思路，并用它们找到了其他许多有趣的开放性问题的反例，比如实数上的和积猜想（sum-product conjecture）。

<details>
<summary>Original English</summary>

**Host**: A bunch of mathematicians took those ideas and used them to find counterexamples to a bunch of other interesting open questions, so for example like the sum-product conjecture over the real numbers.

</details>

**Daniel**：没错。我通常就是这样去评判一个成果有多酷的：事后回过头来看，它所引入的新想法（如果有的话）是否能用来做其他事情？它们是否增进了我们对某些事物的理解？我认为这或许是目前为止我知道的这种类型成果的最主要范例。

<details>
<summary>Original English</summary>

**Daniel**: Um, so that's at least one way I like to think about how cool a result is, like you look at it post-hoc and you see like, oh well, you know, were whatever new ideas that were introduced, if any, like kind of useful to do other things, like did they improve our understanding of something? And I think that's maybe so far the main example I know of of a result of that form.

</details>

### 符号推演与数学直觉的本质差异

**Host**：你能对此进行评价真的很有意义。因为正如你所说，那个成果在五月份公布，随后媒体上充斥着铺天盖地的报道，对于非专业数学家来说，很难去体会这些新闻标题背后的实质差异。你刚才已经开始梳理出一种分类框架，去剖析那份证明的独特性。因此，这正好可以作为一个切入点，探讨你所感受到的模型差异，以及数学家实际上到底在做什么。

大众对数学家工作最朴素的理解，或许就是我们按照逻辑规则在进行符号推演。这也正是为什么强化学习（RL）在此类任务上如此成功的原因——因为与其他领域相比，它的验证成本相对较低，而且规则非常明确。如果在这方面达到超人水平，你可能就很擅长解题。但这种看法显然忽略了数学中最核心、最迷人的部分。正如你也提到过的，任何尝试过做数学的人都知道，数学的真谛在于“理解”与追求真理、在于在困惑中前行并建立直觉。推导强大逻辑结论的能力固然是不可或缺的工具，但绝非全部。

所以，当你形容它“最令人印象深刻且富有创造力”时，能否谈谈如何将单纯超乎寻常的逻辑推导能力，与真正的创造力区分开来？它在推动真正的数学研究活动方面又起到了什么作用？

<details>
<summary>Original English</summary>

**Host**: Yeah, I think it's really meaningful that you're commenting on this because, you know, that result came out to your point in May and there's been so much kind of like so many headlines so far, and it's kind of probably hard for somebody who's not a practicing mathematician to appreciate the differences in these headlines. And so you kind of already started laying out sort of a taxonomy of like what is different in that proof, and so it'd be kind of interesting maybe to use as that as kind of both an excuse to talk about where you sense the model differences are and what like mathematicians actually do. So in this case, I mean the most kind of maybe naive understanding of what mathematicians do is that we're pushing around symbols in a logical manner. And this is why, you know, RL is so successful at this because you can kind of both verify it somewhat cheaply compared to other domains and then also, you know, because like the rules are quite legible, and so you can kind of like you know if you're if you're superhuman at that you might be good at math. But I think that of course betrays most of actually what is interesting about mathematics, which is perhaps I think you said this as well, but I think anybody who's tried to do math is sort of like it's about the understanding and sort of getting at truth, remaining confused, and developing intuitions. And very little—I mean the tool to do that stuff is of course in having really good, very strong abilities to push out logical applications. But maybe if you can kind of talk to speak to like, you know, when you say it's most impressive and creative, like decoupling the just the inhumane maybe feats of just like logical implication from like where is it being creative? What is kind of what is it helping engender in terms of like mathematical activity as well?

</details>

**Daniel**：好的。首先，你刚才用“非人类”（inhuman）来形容它，但实际上我觉得那段论证非常具有人类思维的特征。OpenAI 公布了部分思维链（Chain of Thought），那非常容易辨识，几乎就像是我自己在试图解决问题时所能想象出的思考过程。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. Okay. So, first of all, I mean you kind of characterized it as like inhuman in some way. I actually think the argument was very human-like. You know, OpenAI released some chain of thought, it was very recognizable. It was like kind of, you know, if if I tried to imagine like my chain of thought in trying to solve a problem, like it might look kind of like that.

</details>

**Host**：是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Daniel**：当然，我们没有看到原始完整的思维链，也许他们对此做了一些清洗。

<details>
<summary>Original English</summary>

**Daniel**: Um you know we haven't seen the raw chain of thought, so maybe they...

</details>

**Host**：也许他们做了一点过滤和净化，是的。

<details>
<summary>Original English</summary>

**Host**: Maybe they cleansed it a little bit, yeah.

</details>

**Daniel**：是的，或者模型在思维链中途说了脏话，他们把那些内容清理掉了，这我们无从得知。但至少公开的总结看起来非常通顺易懂。我认为这其实是我研究过的大多数 AI 数学成果的普遍特征：它们看起来一点也不“非人类”，完全像是人类数学家能够写出来的东西。

如果你直接看模型的原始输出，通常也都是可以理解的，尽管行文格式可能没那么优雅规范。它并不像围棋中的“第 37 手”那样神鬼莫测，它就像是一个人类数学家在做数学研究，或者说像人类在做某几类特定的数学题。所以，这些模型在很多方面目前依然算不上非常出色……

<details>
<summary>Original English</summary>

**Daniel**: Yeah. Or maybe, you know, maybe the model liked to swear a lot in the middle of the chain of thought and they cleaned that up or something. We don't know. But like at least the summary seemed pretty legible. And I would say that's actually like kind of typical of most of the results that I've studied. Like they don't seem inhuman at all. They seem absolutely like something a human mathematician could produce. And they're like typically understandable if like not so well written if you just like look at raw model output. It's not like there's some, you know, move 37 or whatever. It's like a human mathematician doing math. It's like a human mathematician doing certain types of math. So like they're definitely the models are still like not very good...

</details>

<!-- chunk 2/9 -->

### 自然语言推理与非形式化思考

**Speaker A**: 在某些数学研究活动中——我指的不是具体哪个数学分支，而是你在尝试解决问题时会采取的某些特定思考步骤——模型似乎并没有做到，但它们在某些特定事情上又非常擅长。它们在某种程度上表现得有些“非人”，比如它们不知疲倦，而且掌握了海量的信息。但是，如果你仅仅去阅读它们的最终输出，其实并不觉得有什么“非人类”之处。

<details>
<summary>Original English</summary>

**Speaker A**: ...at some mathematical activities. And here I don't mean like by field, but just like certain things you do when you try to solve a problem the models don't seem to be doing, but certain things they're very good at. So, the ways they might be a little bit inhuman is like they don't get tired. They know a lot. But if you have to just read the final output, it doesn't seem kind of inhuman.

</details>

**Speaker B**: 这很有意思。显然我们无法从开发这些模型的研究实验室那里获得太多内部信息，比如他们的训练配方是什么，或者他们是如何推进推理能力的。但我们至少知道一件事——我认为 OpenAI 在这方面起到了带头作用——那就是自然语言中的推理正是他们成功扩展（scale up）的核心，而不是通过把大量经过 Lean 形式化验证的证明作为训练语料库推进的，这非常令人惊叹。另一方面，有趣的是，目前尚不清楚大量的数学训练数据（如果他们大规模使用了这些数据的话）是否真正反映了数学家的思考方式。因为大部分数学知识并没有以可读的思维轨迹形式记录下来。大多数发表的论文都非常精炼且经过反复润色，教科书更是很少展示某个理论是如何被构思和发展出来的动机。这也是为什么人们通常更容易通过直接与研究人员交谈来把握研究方向和思考方式。所以在我们进一步讨论分类之前，我很想知道：当你审视这些模型及其输出，对比 Anthropic 和 OpenAI 时，你是否发现了它们与人类推理相似之处的差异？另外，你对于为什么自然语言推理能够如此有效地实现扩展（尽管它并不形式化）有什么看法或见解吗？

<details>
<summary>Original English</summary>

**Speaker B**: It's interesting because I mean obviously we can't get too much of information from the labs who are producing these models of like why, you know, how of what the training recipes are or how they're kind of advancing in reasoning. But at least one of the things we do know, and I think kind of OpenAI spearheaded this, is this like reasoning in natural language is actually what they happen to scale up, and it's not actually pushing a lot of Lean verified proofs as like the training corpus, and that's kind of amazing. On another side, what's kind of interesting is it's not clear that a lot of the mathematical training data, if they use that to a large extent at all, is reflective of how mathematicians think, if that's fair, because a lot of it is not like legible as traces, right? Like most of the papers are crisp and like polished. The textbooks certainly just show very little motivation of how something is developed, which is why it's like usually easier to kind of follow research direction by actually talking to the researchers and how they're thinking about it. So kind of curious before maybe even going to the taxonomy as an excuse, like when you're examining these models and their results comparing Anthropic with OpenAI, do you detect any differences in how that is similar to human reasoning? And then also if you have any comments or insights on perhaps why natural language scales so well that way even though it's...

</details>

**Speaker A**: 好的。首先，我非常赞同你刚才提到的观点，即它们主要是在进行自然语言推理，而不是依赖 Lean 这样的形式化系统。我认为这意味着——虽然你经常听到很多人说“数学是一个可验证的领域，所以这解释了模型在数学上的进展”等等——但我感觉，正因为它们主要是在扩展非形式化推理（informal reasoning），这些技术很可能会非常好地泛化到其他领域。这只是我的推测。

<details>
<summary>Original English</summary>

**Speaker A**: Okay. So first of all, I really like your point by the way that they're mostly doing natural language reasoning rather than Lean. Like I think that suggests to me that—you know you hear a lot of people say like "math is a verifiable domain, like that explains the progress" whatever—like my sense is that because they're primarily scaling informal reasoning, probably the techniques are going to generalize to other domains pretty well. That's just my guess.

</details>

### 前沿模型的解题风格与局限

**Speaker A**: 关于你问到的 Claude 和 ChatGPT 的对比。

<details>
<summary>Original English</summary>

**Speaker A**: Okay. Um, you asked a little bit about like Claude versus ChatGPT.

</details>

**Speaker A**: 我的感觉是它们在能力上非常相似。我和 ChatGPT 打交道的时间要比 Claude Fable 多得多，但在很多情况下，比如 OpenAI 发布了某个问题的解答，Anthropic 也会展示类似的能力。

<details>
<summary>Original English</summary>

**Speaker A**: My sense is that they're pretty similar in terms of capabilities. I've played around a lot more with ChatGPT than Claude Fable, but you know, it seems like there's a lot of cases where, you know, OpenAI will drop a solution to some problem and Anthropic will say, "Oh, you know, we can do that too." Exactly.

</details>

**Speaker A**: 所以实际上它们能解决的问题集非常相似，而这在人类数学家所做的工作中只占了相对较小的一部分。值得注意的一点是，我们看到模型给出的解决方案具有某种特定的风格。这并不令人意外——这些解法往往依赖于模型的长处，比如它们能够死磕并完成漫长的计算，或者从许多不同领域、甚至人类数学家未曾涉猎的大量论文中调集技术性想法。但在直觉或全局视角方面，它们显得较弱。作为一名数学家，我的很多日常工作其实是建立在某种非常非形式化的哲学或直觉之上，比如我认为某件事物可能在某种意义上与另一件事物类似，接着我的大部分工作就是去琢磨如何将这种直觉精确化，并通过能否解决某个问题、或者能否发现并理解之前不明白的有趣现象，来检验自己是否真正理解了它。到目前为止，即便是模型产出的最好成果中，也很少看到这种类型的推理；它们更多表现为极其擅长套用现有的已知技巧。

<details>
<summary>Original English</summary>

**Speaker A**: So, it actually seems like they're solving a very similar collection of problems and it's like kind of a small, you know, relatively small portion of what human mathematicians do. So yeah, one thing that is interesting is like we see the solutions have a certain flavor, right? There'll be things that—this isn't surprising—like there'll be things that rely on the model strengths, like their ability to like grind out a long computation or like you know pull together kind of technical ideas from many areas, or like maybe many papers that you know a human mathematician might not have read. But they seem like weaker in things like intuition or like having some big picture point of view. Like a lot of what I do as a mathematician is like I have some kind of philosophy that's like very non-rigorous, like maybe I think this thing is kind of analogous to that thing, and then like a lot of what I'm working out is like figuring out how to make that precise, and like trying to measure the extent to which I've succeeded in understanding that by like can I solve a problem or whatever, like can I find an interesting phenomenon which I don't understand and then now I understand it. And like so far, even the best results the models are producing, you don't see that much of this kind of reasoning. It's more like they're very, very good at applying some known techniques...

</details>

**Speaker B**: 需要明确的是，能够极其擅长应用所有已知技巧本身就是一件非常强大且了不起的事情。

<details>
<summary>Original English</summary>

**Speaker B**: ...which is to be clear, that's like a very powerful thing to do, to be very good at applying like all known techniques.

</details>

**Speaker A**: 确实，历史上有很多数学家通过做出这种风格的高质量工作取得了卓越的职业成就，而模型产出的很多成果在这方面也确实质量很高。但这依然只是数学家所关注的领域中一个相当狭窄的切面。不过，目前确实能看到迹象，所有前沿模型都开始有能力处理一些更为模糊的任务。例如，我曾尝试让 Fable 和 ChatGPT 5.6 去做一些理论构建（theory building）的工作。它们在自主完成这方面确实不够擅长，至少在我搭建的脚手架下是这样。但在给予定提示的情况下，你可以引导它们做出一些有趣的东西。当然，当你给模型提示时，很难界定哪些部分归功于模型，哪些部分来自你自己。但我的经验是，如果它们现在能在得到上百比特提示的情况下完成任务，也许六个月后它们就能在没有提示的情况下独立完成了。

<details>
<summary>Original English</summary>

**Speaker A**: There are mathematicians who have had great careers doing very high quality work of that flavor, and I think a lot of what the models are producing is high quality in that way, but it's like some kind of fairly narrow band of what mathematicians care about so far. I do think there's signs of all the frontier models starting to be able to do more fuzzy things. So like I've tried to get both Fable and ChatGPT 5.6 to do some kind of theory building. And they're not good. They definitely are not good at it autonomously, at least with like whatever scaffolding I've set up. But with some hints, you can kind of get them to do something interesting. When you give the models hints, it's always a little hard to tell like what part is from the model and what part is from you. But my experience is that like if they can do it with like a hundred bits of hints or whatever, in six months maybe they can do it without hints.

</details>

### 工具选择与心智模型的差异

**Speaker B**: 是的，我认为确实有迹象表明它们在以某种方式吸收这些隐性、未成文的数学知识。我很想深入探讨直觉以及模型目前表现欠佳的地方，但你刚才提到过一个小细节：从公开信息来看 Anthropic 和 OpenAI 势均力敌，但你个人使用 ChatGPT（或 5.6）要多得多，这是为什么呢？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, you know, I do think there's signs that they're also kind of somehow picking up some of this like implicit and unwritten mathematical knowledge. Okay. I would love to go into the intuition part and where it sucks at, to put it in a very basic way, but you actually mentioned a small detail which is that you know from the public you've gleaned that Anthropic and OpenAI are probably neck and neck, but you personally are using a lot more ChatGPT—like why is that, or 5.6?

</details>

**Speaker A**: 为什么会这样？我也说不清，我觉得可能纯粹是一种使用惯性吧。

<details>
<summary>Original English</summary>

**Speaker A**: Well, why is... I don't know. I mean I just think it's just inertia, like I have...

</details>

**Speaker B**: 确实如此。

<details>
<summary>Original English</summary>

**Speaker B**: Pretty sure of it.

</details>

**Speaker A**: 另外一个原因是 ChatGPT 更早就展现出了较强的数学能力。

<details>
<summary>Original English</summary>

**Speaker A**: One thing is that ChatGPT got better at math earlier. So...

</details>

**Speaker A**: 在很长一段时间里，Claude 模型在数学前沿研究中基本派不上用场，直到 Opus 4.5 或 Opus 4.6 左右，它们才大致追赶上来。

<details>
<summary>Original English</summary>

**Speaker A**: ...like for a long time, the Claude models were just like not useful for research math, and then I think maybe around Opus 4.5 or Opus 4.6 they like more or less caught up.

</details>

**Speaker B**: 明白。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 不过一些测试向我表明它们现在基本并驾齐驱。因此在我的日常工作中，除了专门做对比实验时，我通常就固定使用其中一个，某种程度上也是随意的选择。

<details>
<summary>Original English</summary>

**Speaker A**: But you know, some experimentation suggests to me they're pretty neck and neck, and so for my own work, you know, except when I'm just experimenting, I mostly just stick with one and sort of random.

</details>

**Speaker B**: 对于像我们这样身处实验室之外的人来说，比较它们在前沿能力上的细微差别非常有趣。正如你所说，这里面可能有使用惯性的因素。但在我个人的体验中，5.6 的陈述解释要清晰得多。而且尽管前沿模型的能力边界参差不齐（jagged），但在向我解释研究结果时，我总觉得 5.6 能更准确地构建出对我的心智模型（theory of mind），即准确判断出我已知和未知的内容。相比之下，Fable 可能会花力气解释一些显而易见的基础概念，但随后突然跳跃并默认“你显然应该知道这些深奥知识”。

<details>
<summary>Original English</summary>

**Speaker B**: As people outside of labs like us, it's really interesting just to compare how they differ on the frontier. And I mean, to your point it might be a little bit of momentum. I do think that at least from my anecdotal experience 5.6 has been a lot more clear in exposition, and there's a little bit—and this might not be true, obviously the models are just incredibly jagged at the frontier—but in the explanations of results to me, I always find that 5.6 is giving a more accurate theory of mind of what it assumes I know and don't know. Whereas Fable might be explaining something very trivial but then just like jump at like, "Well, you know, obviously you should know these things," and...

</details>

**Speaker A**: 我倒觉得它们两者在心智模型理解上都挺差的。

<details>
<summary>Original English</summary>

**Speaker A**: I find they're both pretty bad at theory of mind.

</details>

### 数学研究的本质与 AI 带来的转变

**Speaker B**: 好的，那说明从你的专业视角来看，你提出的问题显然要深刻得多。那么我想顺着刚才的线索继续探讨：你提到模型可能开始获得更好的数学直觉甚至是理论构建能力。在我们深入这个话题之前，或许可以先请你梳理一下：作为一名数学家，你的核心日常活动究竟是什么？特别是在你所从事的代数几何领域，它与组合数学或其他数学领域的工作风格可能大相径庭。能否请你简要勾勒一下这个领域的全貌，并解释一下在 AI 出现之前你的数学研究活动是怎样的，以及在 AI 介入之后它正在发生怎样的转变？

<details>
<summary>Original English</summary>

**Speaker B**: Okay, great, so from your eyes you're probably asking much deeper questions. Okay, so the thread that I really wanted to pull on was when you're talking about the models maybe starting to get better intuitions or even theory building. So maybe before we even dive into that, it would be useful to kind of talk through like what is your primary activity as a mathematician. Especially in your area of algebraic geometry, it probably has a very different flavor than a combinatorialist or some other areas. So if you can give a brief lay of the land and then kind of explain what your mathematical activity was pre-AI and then maybe how it's kind of changing with AI.

</details>

**Speaker A**: 好的。我认为数学家有很多不同的类型，你可以将数学家置于许多不同的评价维度谱系之上。当然，很多数学家主要热衷于解决未决的公开难题（open problems）……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So I mean I think there are a lot of different kinds of mathematicians. There's like a lot of different spectra on which one can put a mathematician. So definitely a lot of mathematicians like solving open problems.

</details>

**Speaker B**: 嗯。

<details>
<summary>Original English</summary>

**Speaker B**: Mhm.

</details>

<!-- chunk 3/9 -->

### 问题解决者与理论构建者

**数学家**：我认为自己更偏向于解决未决问题（open problem）那一类人。我把自己看作一个“问题解决者”（problem solver），而不是——打个比方，数学界有一种分类方式，就是将人划分为“问题解决者”与“理论构建者”（theory builder）。

<details>
<summary>Original English</summary>

**Mathematician**: Uh and then I think I'm one of those like I like to solve an open problem. That's uh I think of myself as a problem solver as opposed to like one you know one other taxonomy you could have is a problem solver versus a theory builder. Mhm.

</details>

**数学家**：至少对我而言，一个未决问题的意义在于，它应该用来衡量你在理解某件事物上的欠缺程度。所以它就像是一个基准（benchmark）。

<details>
<summary>Original English</summary>

**Mathematician**: Um at least for me, the point of an open problem is it's supposed to measure your failure to understand something. So it's kind of like a benchmark.

</details>

**数学家**：对，比如我非常喜欢的一个问题是格罗滕迪克-卡茨 p-曲率猜想（Grothendieck–Katz p-curvature conjecture）之类的课题。它衡量的正是我们在理解微分方程方面的不足。也就是说，存在某个我们渴望理解的极其基本的数学对象；如果我们无法解答这个猜想，我们就知道自己其实还没有真正理解它。

<details>
<summary>Original English</summary>

**Mathematician**: Um right like you know one problem I really like is the Grothendieck p-curvature [gross decap curp] whatever that is. It measures something about our failure to understand differential equations. So it's like there's some very basic object we would like to understand. If we can't answer this conjecture we know we don't understand it.

</details>

### 攻克难题与建立类比

**数学家**：那么在实践中，你该如何着手去解决一个旨在衡量你认知盲区的问题呢？当然，你首先会试图去更好地理解这个对象。而在实践中，这意味着你要去寻找那个让你无法理解的最小情况（smallest situation），并在其中反复摆弄和摸索。一旦你取得了突破，你就会仔细审视自己为了获胜所发展出来的工具，并尝试将这些工具升华成某种理论。

<details>
<summary>Original English</summary>

**Mathematician**: Mhm. Okay. So in practice like how do you get at a problem which is supposed to be measuring something you don't understand? Well like of course you try to understand the thing better. And in practice what that means is like well you try to find the smallest situation where you can't understand something and fiddle around with it, and then once you win you stare at like what you developed to win and try to turn that into some theory.

</details>

**数学家**：这是你可能会做的一件事：尝试去解决一个问题，并在这个过程中建立起对该情境的一种全新理解。此外，你也可能只是隐约产生某种直觉，觉得这个事物与另一个事物之间存在关联。然后你可能会开始列一张对照表：比如性质 A 对应性质 A'，性质 B 对应性质 B'，以此类推。

<details>
<summary>Original English</summary>

**Mathematician**: Um so that's one thing you might do. You might try to like solve a problem and in so doing develop some kind of new understanding of the situation. You might also just like have some feeling that like this thing is related to this other thing. And you know you might start building a table like oh this property A is related to property A prime, property B is related to property B prime, and so on and so forth.

</details>

**数学家**：例如在我自己的研究工作中，很大一部分动机来自于代数簇的同调（homology of algebraic varieties）与基本群表示（representations of fundamental groups）之间的某种类比。这涉及一些非常高深的内容，但这种类比极其富有成效，在一侧出现的任何现象，几乎都能在另一侧找到对应的镜像。在过去三四十年里，卡洛斯·辛普森（Carlos Simpson）、望月拓郎（Takuro Mochizuki）等人为了实现这一构想，创造出了大量极其优美的数学理论。

<details>
<summary>Original English</summary>

**Mathematician**: So for example in my work a lot of it is motivated by some analogy between homology of algebraic varieties and representations of fundamental groups. Okay, so that's some fancy stuff. But this analogy is like very very fruitful and really any phenomenon that appears on one side, you can find an analog on the other side. And so trying to realize that dream has led to a lot of beautiful mathematics of the last like 30 or 40 years by people like Carlos Simpson and Takuro Mochizuki and others.

</details>

**数学家**：所以在这里，本质上就是有人注意到了某种类比的存在，而正是这种类比催生了巨大的理论发展。它的终点其实并没有一个具体的未决问题——尽管随着研究深入，你自然会提出许多未决问题。但它背后始终贯穿着一种你试图去实现的哲学构想，而这种哲学在本质上其实并不是那么严格的符号推导。

<details>
<summary>Original English</summary>

**Mathematician**: And so here it's really just like someone noticed like here's an analogy and then that analogy has led to a huge amount of developments. There's not really like an open problem at the end although of course like as you develop this you come up with lots of open problems. There's just like a philosophy that you're trying to realize and that philosophy is like super not rigorous actually. It's not like symbol pushing at all.

</details>

### 寻找正确的问题与实验数学

**数学家**：这也是我非常喜欢的另一类学术活动。除此之外，很多时候你所做的事情，其实是在努力探寻什么是“正确的问题”。面对一个你感觉自己并不理解的对象，搞清楚“自己究竟不知道什么”本身就是一件极具挑战性的事。网上可能会列出各种未决猜想的清单，但这些清单在很多层面上并不能真正反映出我们的认知空白——因为很多时候，仅仅是提出一个有价值的猜想就已经极其困难了。

<details>
<summary>Original English</summary>

**Mathematician**: Um yeah so that's another kind of activity that I like. Um yeah, beyond that a lot of what you do, a lot of the activities, you're actually trying to figure out what the right question is even. Like here you have some object you feel like you don't understand it, and figuring out what you don't know is actually a very challenging thing to do. So there's a list of you can go online and list open conjectures or whatever, and this doesn't really capture in a lot of ways what we don't know, like often finding the conjecture is really really hard.

</details>

**数学家**：一个很好的例子就是贝赫和斯维讷通-戴尔猜想（Birch and Swinnerton-Dyer conjecture，千禧年大奖难题之一）。它揭示了椭圆曲线的 L 函数与对应方程解集（即解群的秩）之间优美的深刻联系。这个猜想是首批依靠“大数据”发现的猜想之一：贝赫和斯维讷通-戴尔在 20 世纪 60 年代整理了椭圆曲线的大量统计数据，作为最早期的计算机辅助数学研究之一，他们把这些统计数据绘制成图表，并敏锐地注意到图表中某条直线的斜率与他们已知的某种代数不变量密切相关，这正是该猜想的起源。所以很多时候你只是在计算具体的例子，做着类似科学实验的工作：运行一个实验，然后努力为实验结果寻找理论解释。

<details>
<summary>Original English</summary>

**Mathematician**: A good example of this is like the Birch and Swinnerton-Dyer conjecture which is one of Millennium Problems, is this beautiful relationship between L-functions of elliptic curves and the set of solutions to the corresponding equations of the rank of the group of solutions. It was discovered by, it was like the first big data conjecture. So Birch and Dyer had found all these statistics on elliptic curves in the 60s like this one of the first ever computer-aided bits of mathematics, and they graphed these statistics and they noticed that the slope of some line on a graph was related to some other algebraic invariant they knew, and that was the source of this conjecture. So a lot of the time you're just working out examples and doing kind of science like you run an experiment and you try to figure out an explanation for that experiment.

</details>

### AI 在数学研究与编程中的应用边界

**数学家**：回到 AI 这个话题，我认为迄今为止，AI 在某些工作上的帮助明显要比在其他工作上大得多。某种现象越是模糊，或者你脑海中越是缺乏一个精确的问题，AI 的用处往往就越小。你刚才问我在日常生活中如何使用 AI，我发现对于那些在 AI 出现之前我就已经思考了三四五年的老课题，AI 其实并没有太大用处。它在很大程度上只是谷歌搜索的替代品：比如我可能会用它来了解某个相关领域，或者以前我可能会去谷歌搜索并阅读一篇论文，现在我可能会选择直接与 AI 进行讨论。这确实节省了一些时间，但它并没有真正为我做深度智力工作。

<details>
<summary>Original English</summary>

**Mathematician**: And so I think going back to AI, I think like these are things where AI seems so far to help a lot more in some things than other things. The more vague a phenomenon is or the less you have a precise question in mind, the less useful it happens to be. And so you were asking like how I use it in my daily life, like actually what I found is that the projects that I have that kind of predate AI, like the projects I've been thinking about for three or four or five years, it's just not that useful. It's primarily kind of a substitute for Google or something, like I might use it to learn about some related topic or something where I would have earlier Googled something and then read a paper, maybe I'll discuss it with AI instead. So it saves some time for sure. It's not really doing deep intellectual work for me.

</details>

**数学家**：但另一方面，因为我自己的编程水平很差，而现在我有了一位编程能力极强的“好朋友”（AI），所以我一下子开展了许多编程相关的课题。过去如果我遇到一个用编程会非常有效的问题，我可能会拖延上整整六个月，直到我找到——

<details>
<summary>Original English</summary>

**Mathematician**: But then you know, because I suck at coding, and so now I have you know my good friend who's really good at coding and now I have all these coding projects because suddenly, well if I had a question where coding would have been really useful I would have procrastinated on it for six months until I—

</details>

**主持人**：——直到你找到一个不知疲倦的博士生。

<details>
<summary>Original English</summary>

**Host**: —tireless PhD student.

</details>

**数学家**：完全没错！所以现在我接手了所有这些课题，在这些课题中编程确实极其有用。

<details>
<summary>Original English</summary>

**Mathematician**: Exactly. Yeah. So, so yeah, now I picked up all these projects where yeah, coding is really useful. Like—

</details>

**数学家**：这些模型非常擅长处理高度并行化的任务。比如如果你想寻找某种反例或特例，你可以直接让它并行测试一千个例子，或者每次测试十个例子，让十个不同的子智能体同时处理，这非常有效。但这属于不同性质的活动，相当于在我之前所从事的工作之上额外叠加的新维度。

<details>
<summary>Original English</summary>

**Mathematician**: —the models are like very good for kind of massively parallel things. Like if you want to find an example of something, you can just ask it to find, you know, work through a thousand examples in parallel or maybe 10 examples at a time, you know, 10 different subagents and like that's really useful. But these are like kind of different activities which are on top of what I was doing before.

</details>

### 纯数学的研究动机：审美与社会学现象

**主持人**：我很想就这个话题深入探讨一下。

<details>
<summary>Original English</summary>

**Host**: I'd love to dig in.

</details>

**数学家**：好的，请讲。

<details>
<summary>Original English</summary>

**Mathematician**: So yeah, go.

</details>

**主持人**：抱歉打断你。你刚才提到有些项目你已经思考了三到五年，我不知道把这些归类为“理论构建”层面是否准确？因为你刚才把自己描述为一个“未决问题解决者”。这种需要深度思考的部分到底是什么？或许对于我们的听众来说，也有必要解释一下：大多数纯数学研究并不是为了外部实际应用而驱动的；应用数学至少有外部现实需求作为动机，来解释为什么某种形式结构值得研究。而纯数学几乎完全像是一种社会学现象——威廉·瑟斯顿（William Thurston）在 70 年代也曾提出过类似的观点，即当越来越多的数学家开始研究某一事物时，大家可能会逐渐汇聚到某些有趣的结构上。但人们究竟为什么偏好研究某些事物，或者认为它们是“优美”的？驱动你个人的动力是什么？或许你也可以谈谈整个数学界的普遍情况。

<details>
<summary>Original English</summary>

**Host**: Yeah. Sorry. Cuz you were mentioning there's projects that you've been working on for like 3 four five years and I don't know if it's correct to say like those are more of the theory building aspect of it cuz you did characterize yourself as like an open problem solver, or what is the thing that is because like the deep thinking part? Maybe kind of for this audience it might also be useful to kind of explain: most of pure math, it's not being motivated by—nothing on applied math, but applied math at least there's some external motivation for why a certain formal structure might be interesting to study. Whereas this one, it seems almost sociological, and to some extent I think Thurston made some comment or point about this in the 70s that it is a sociological phenomenon of more and more mathematicians start examining something then you'll maybe converge on some interesting structures. But there's some reason why people would prefer to study something or they think it's beautiful—like what is it that drives maybe you in particular and then maybe you can make a more general comment about the profession.

</details>

**数学家**：确实，有些人完全是由“美感”或审美考量所驱动的。但我自己尽量不让自己被这种因素所驱动。

<details>
<summary>Original English</summary>

**Mathematician**: Yeah. I mean, so definitely some people are like motivated by like beauty or kind of aesthetic considerations. I try not to be motivated by that.

</details>

**主持人**：我认为那也是一种限制，对吧？

<details>
<summary>Original English</summary>

**Host**: I think that's a bad way like—Well, one thing like that sort of limits you, right?

</details>

**数学家**：我在年轻数学家身上有时会看到一种误区：他们面对一个命题，心里大致知道该如何证明它——

<details>
<summary>Original English</summary>

**Mathematician**: One thing kind of a failure mode I see among young mathematicians sometimes is like you have something and you kind of think you know how to prove it—

</details>

**数学家**：——但是那个证明过程感觉非常“丑陋”，于是他们就放弃了。但问题在于，如果你判断错了、那个方法其实并不丑陋呢？为什么要给自己设限？你应该坚持做下去。

<details>
<summary>Original English</summary>

**Mathematician**: —and then like the proof feels really ugly and you decide—but like okay, I mean what if you're wrong and it's not ugly? Why limit yourself, you should—

</details>

**主持人**：对于听众而言，你能具体阐述一下数学中的“丑陋”究竟指什么吗？因为我能凭直觉感受到什么是丑陋，但具体该如何去描述它？

<details>
<summary>Original English</summary>

**Host**: —for this audience like what is ugly? Because I have an intuition of what's ugly, but like what is that, kind of spell out?

</details>

**数学家**：我其实也不太清楚，因为我自己并没有强烈的审美偏好。但人们有时确实会有这种感觉，比如当一个证明涉及大量繁琐的——

<details>
<summary>Original English</summary>

**Mathematician**: I don't really know, I don't really have aesthetic feelings, but people sometimes feel this way, like maybe it involves a lot of—

</details>

<!-- chunk 4/9 -->

### 数学研究的审美与科学视角

**Speaker A**: ……枯燥繁琐且毫无启发性的纯粹计算。

<details>
<summary>Original English</summary>

**Speaker A**: ...grinding calculation that's not illuminating or...

</details>

**Speaker B**: 但在我看来，你应该不择手段去赢得证明。我喜欢把我所做的事情看作是某种物理学研究，只不过处理的是抽象概念。所以，相比于追求所谓的“美”，我更倾向于去思考：什么才是最本质、最基础的？什么能够为进一步的深入理解开辟最广阔的道路？我引入的这个新想法，是否能在宏观层面广泛帮助人们理解这个数学对象？

我想从某种意义上说，这其中确实包含了一些审美考量，但我更倾向于以“做好科学研究”为导向，而不是试图去“搞艺术创作”。不过在这个问题上存在着巨大的观点分歧，很多数学家会觉得自己更接近诗人或诸如此类的角色。

<details>
<summary>Original English</summary>

**Speaker B**: ...but you should win by any means necessary in my opinion. I like to think of what I'm doing like doing kind of physics except with concepts. So, instead of beauty, I try to think about maybe what is fundamental, what's going to open up further understanding most. Am I introducing a new idea that will be broadly useful to understand this object?

And I guess in some sense there's some aesthetic consideration there, but I think the orientation of trying to do good science rather than trying to do art is what I prefer. But there's a huge variety of opinions here and lots of mathematicians think of themselves as being closer to poets or something.

</details>

**Speaker B**: 我确实广泛认同的一点是：数学的进步似乎主要来自于人们去追随各自个人的好奇心。从历史上来看，至关重要的一点就是拥有许多持有不同兴趣和视角的人，正是因为大家各探索各的，知识的边界才会不断向外扩张、扩张。然后突然之间，就会出现一些充满机遇的转折点——某个新概念或新思想被引入进来，你便能瞬间势如破竹地推演并解决一整串我们之前无法理解的问题。

<details>
<summary>Original English</summary>

**Speaker B**: What I do think is broadly true is that progress comes in mathematics from people sort of pursuing their personal curiosity. And that it's been crucial historically that there's a lot of different people with different views of what's interesting, and then the frontier of knowledge expands and expands, and then suddenly you have these opportunistic situations where a new idea has been introduced and you now can suddenly cascade through a bunch of other things that we didn't understand before.

</details>

### AI 模型的局限与长周期数学难题

**Speaker A**: 是的。那么回到那些需要攻坚三、四、五年的难题上，在哪些方面模型目前依然没有太大用处呢？换种方式问：当你进行深度思考时，究竟是因为这类问题很难直接形式化表述，还是更多因为你一直在思考那些更本质的概念物理机制？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean, so then going back to the three, four, five year problems and where are the models sort of not useful? Kind of ask it another way: when you're doing the deep thinking, is it just that it's just not clear that you formulate it as a problem, and it's more that you're thinking about what are the fundamental physics of...

</details>

**Speaker B**: 在某些情况下，问题其实是有着非常清晰明确的表述的。比如对于某些我可能已经思考了近十年的问题，它就是一个明摆在那里、我极度渴望去证明的猜想。

我认为模型在其中某些问题上没有发挥作用的一个原因在于：这些猜想本身很可能是真的。例如像单位距离猜想这类问题，此前数学界的普遍信念认为它是真的，但最终却被证实是假的。而这意味着存在一个具体的反例构造，你可以通过构造性方法去直接反驳它。

另一方面，我思考的很多东西——尽管说不定明天就有人能找到曲率猜想假设的反例从而让我显得很蠢——但在通常情况下，这些猜想都是嵌入在一个极其庞大宏伟的理论框架之中的，这代表着我们其实已经拥有了非常多的证据表明它们是真实的。正因如此，这里并不存在一个你可以信手拈来直接反驳它的反例构造。你必须以某种方式深入其中——在这个庞大的理论大厦里，某些核心构件目前仅仅处于猜想状态，而你可能需要真正解决掉其中的部分猜想才能取得最终胜利。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, so in some cases, I mean, there is a well-stated problem here. Like, I've been thinking about things for maybe 10 years now at this point for certain problems, sometimes there is just a conjecture that I would like to prove that is there.

I think one reason the models might not be useful for some of these things is the conjectures are true. For example, this unit distance problem, the general belief in the community was that it was true, and then it turned out to be false. And so what that means is that there's a specific construction you can do to refute it.

On the other hand, I think a lot of the things I think about—maybe someone will come up with a counterexample to the curvature conjecture hypothesis tomorrow and I'll look like a fool—but in general, these conjectures fit into some very broad theoretical framework, which means that we actually have a lot of evidence that they're true. And so that's part of it: there's not a construction you can do to refute it. You need to somehow... we have this giant framework where certain pieces of it are only conjecturable, and you probably need to resolve some of those conjectures to win.

</details>

### 新理论构建与已知技巧的迁移

**Speaker B**: 同时我们也非常清楚地意识到，要解决这些猜想，必须要引入非常重大且深邃的全新思想。当然你无法绝对断言，也许存在某种极其精巧的构造能让你绕过提出重大新理论的需要，这谁也说不准，我们完全有可能在未来发现这一点。但就我目前的直觉而言，至少对于我一直在思考的大多数问题来说，仅凭以极其强悍的技巧去堆叠现有的已知方法是远远不够的，你必须开发出全新的数学工具和技术。需要明确的是，我并不是断言模型永远无法做到这一点，只是说截至目前它们似乎还不具备这种能力。

<details>
<summary>Original English</summary>

**Speaker B**: We also have a pretty good sense, I think, that very serious new ideas are needed to resolve those conjectures. So of course you can't be sure, like maybe there's some very clever construction that will let you avoid having a big new idea. I don't know, it's quite possible we'll find this out, but my sense is that for at least a lot of the things I've been thinking about, they're just not accessible to applying known techniques in a very technically strong way, so you need to develop a new technique. Just to be clear, I'm not saying the models won't be able to do this, it's just so far they seem not to.

</details>

**Speaker A**: 这正是我想要深入探讨的核心要点。正如你所指出的，我们固然可以去校准并预测模型未来为何能在这方面做得更好，但眼下的事实确实是：如果只是给出一个反例的具体构造，模型似乎表现得相当强悍；但如果必须开始构建全新的理论，或者像你所说，必须开创全新的技术工具体系来证明一个猜想为何成立，模型就会挣扎得多。这大概是因为它目前很大程度上依赖的是将其他领域已经出现过的既有技巧迁移过来，而这也正是为什么单位距离问题可能会是一个更具创造性的突破结果，因为它在很大程度上是在自主地从某个意想不到的交叉领域引入工具。

<details>
<summary>Original English</summary>

**Speaker A**: Actually, that's exactly the point that I wanted to delve into because to your point, it's like, okay, we can try to calibrate and forecast why they would get better at this, but it is true that just providing a construction for a counterexample, they seem to be strong on. If you have to start developing either new theory or, to your point, techniques, machinery to prove why a conjecture is true, it struggles more. And it's probably because a lot of what it's drawing on is also just techniques that have happened in other areas and they're porting it over. And to your point, that's why maybe the unit distance problem was such a more creative result because it was maybe doing more of that on its own.

</details>

**Speaker B**: 它的确是从另一个领域，或者至少是从某个完全出人意料的领域汲取了养分。

<details>
<summary>Original English</summary>

**Speaker B**: It was like from another, at least it was drawing in something from an unexpected area.

</details>

### 理论构建能力的强化学习与演进路径

**Speaker A**: 没错，正是如此。所以接下来的问题并不是说 AI 做不到——鉴于 AI 的进步如此之快、水平越来越高，我们绝不能排除这种可能性——而是说，在你看来，为什么发展这种全新的理论和方法体系会显得格外困难？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Exactly. Exactly. And so maybe then to kind of ask the question—it's not that because now we're like, okay, fine, AI is getting so good so fast we can't count it out—but why, what do you think it has to... you're spelling out what it has to get better at, but maybe some more feelings on why it's particularly hard to then develop that new theory and technology?

</details>

**Speaker B**: 这是一个极好的问题。我的推测是，这其实完全是可行的，只是目前尚未被攻克而已。或许我们只是需要一种截然不同的强化学习（RL）训练环境。就现阶段而言，我的预期是能力增长的整体上升轨迹仍将持续，我对 AI 能力的持续演进并不持怀疑态度。

但毫无疑问的一点是：构建一套理论、或者对一个理解尚浅的对象逐步建立深刻认知的这种能力，本身要模糊得多。所以训练起来可能会困难得多。比如你可以对模型下达指令：“去建立你对 Zeta 函数的深层理解，一旦你证明了黎曼假设就给你奖励”，但你很难设计出能够对其过程进行即时奖赏的中间节点或过程奖励指标。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's a good question. I think you just need a different... my guess actually is it's probably totally doable, and it just hasn't been done yet. Like maybe you just need a different RL environment. I don't know. Yeah. So at this point my expectation is just that the trajectory will continue upwards. I'm not a skeptic of continued capabilities growth.

Yeah, I think what is definitely true is that the skill of developing a theory or building your understanding of some poorly understood object is a fuzzier one. So it might be harder. I guess you can tell it, "develop your understanding of zeta functions, then once it proves the hypothesis you give it a reward," but it's kind of harder, I think, to come up with some intermediate things that you can reward.

</details>

**Speaker B**: 话虽如此，整个数学学科本身就提供了海量难度各异的猜想。这或许正好解释了为什么在这些领域其实已经能看到一些渐进式的进展。可以推想，研究人员正在尝试让模型去解决大量不同梯度的问题，而其中某些问题必然会锻炼并培养出一部分构建理论的能力。人类同样能够发展出这些技能——有时候人类博士生会从导师那里获得正向反馈，导师会根据人类的品味或经验说“这是一个好想法”之类的话。这也可能是我们可以采用的一种训练路径。但我总体的预期是，随着模型整体能力的持续跃升，我们在这些理论构建领域同样会看到同步的突破。

<details>
<summary>Original English</summary>

**Speaker B**: That said, I do think mathematics as a whole provides a lot of conjectures of varying levels of difficulty, so maybe this explains why there seems to be a little bit of progress in these areas. Presumably they are trying to get it to solve lots of problems, and some of those problems develop at least some of the skills of theory building. And humans are able to develop these skills. Sometimes they get rewards from their PhD advisors, and their advisor says, "Oh, that's a good idea," or something based on some element of human taste or whatever. And that might be something one can do too. But yeah, my expectation is that just as part of continued capabilities growth, we'll see growth in these areas too.

</details>

### 课程体系与人类认知压缩的本质

**Speaker A**: 是的，我很喜欢你的这个视角——将这些难度逐步递增的数学猜想视作为人类以及 AI 量身定制的一套渐进式课程体系。这甚至可能触及到对某些人来说过于哲学化的问题：它探究了为什么人类在数学上会有特别擅长或特别不擅长的表现。当我们去发展一套全新理论时，究竟是什么让人类感到举步维艰，又是什么让少数人格外游刃有余？

这或许也与我们为何能为物理学构建出优美的理论结构相通：世界并非所有部分都是显而易见可被理解或清晰形式化的，但总有某些部分确实如此。我们之所以竭尽全力去构建理论，可能是因为人类的大脑面临着巨大的信息压缩压力——我们无法直接吞吐未经压缩的海量现实，必须依靠更加精细优雅的理论压缩模型来理解世界。我不知道这种理解是否准确……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And I like the framing where you're sort of casting these increasingly difficult conjectures as a form of curricula for both humans and of course AI. And maybe kind of getting a little bit too philosophical for some people's tastes, it gets at the question of why are we particularly good or maybe particularly bad at math too. What is it that we're either struggling to do or some people are particularly good at when you develop new theory?

Maybe it's related to why can we formulate good structures for physics as well. It's just not obvious all parts of the world are kind of understandable and legible that way, but some parts are, and therefore we try to do it because there's maybe compressive pressures on our minds because we can't understand anything beyond compressing stuff more finely. I don't know if that's also the correct interpretation of...

</details>

**Speaker B**: 我个人对将“信息压缩”作为衡量数学价值或趣味性的评价指标是持有一点怀疑态度的，不过……

<details>
<summary>Original English</summary>

**Speaker B**: I think that's... I mean, I'm a little bit skeptical as like compression as a metric of interest, but it's...

</details>

<!-- chunk 5/9 -->

### 人类“无法硬算”的局限如何催生概念发现

**Speaker A**: 这绝对可以算作我们为什么会去构建某种理论的人类学原因。我认为事实确实如此，甚至可以说，我们无法纯靠死算硬磨的这种“无能”，对我们做出科学发现的能力其实至关重要。

举个例子，我目前发表过一篇论文，其中模型确实发挥了作用，它们证明了几个引理。

<details>
<summary>Original English</summary>

**Speaker A**: Definitely, like as an anthropological reason for why we do a certain theory building. I just think it's true, and in fact, I think our inability to just grind is kind of important to our ability to make discoveries. So, just as an example, I have one paper out so far where the models were kind of useful. They proved a couple of lemmas.

</details>

**Speaker A**: 当时的具体情况是，我们基本上已经证明了主要结论，但还有几个引理让我不太满意，因为它们看起来不是最优的。于是我开始与模型合作——当时用的是 Gemini Deep Think，那会儿它还处于前沿水平，现在已经不是了。

<details>
<summary>Original English</summary>

**Speaker A**: So this is some situation where we had kind of proven the main result and then there were some lemmas I was unhappy with, like they seemed not to be optimal. And so I worked with—actually this was with Gemini Deep Think, which at the time was also on the frontier, no longer man.

</details>

**Speaker A**: 我当时就是配合它来尝试证明这些引理。整个过程是这样的：有一个引理我想证出来，但模型做不到，当时所有的前沿大模型全都不行。于是我自己动手推演了大量的具体算例，随后我意识到：“噢，或许这里面存在某种它之所以成立的深层原因。”也就是说，我找到了该引理一个更好的数学表述形式。

一旦有了这个更好的命题表述，虽然我可能自己也能很快证出来，但模型同样非常迅速地给出了证明。所以你看，我们最初无法直接证明它的局限，反而倒逼我们改进了结论本身的表述。

然而换作现在，如果你把当时模型证不出来的原始引理扔给 ChatGPT-5.6 Pro，它会吐出一段你所见过最糟糕的证明——长达 10 页纯粹、野蛮、毫无洞见的硬算推导。诚然，这也是一份完全合格的证明，但它绝不会引导我们去发现那种解释“为什么我们发现的结论会成立”的优美概念性解释。

所以，我们能找到更好的证明，恰恰是因为我们算不下去。其实说“算不下去”也不准确，真实情况是——我也承认这和我之前抱怨证明太丑有点双标——我意识到这种恶心枯燥的硬磨证明行得通，但我自己在心理上实在无法忍受去做这种死算。

<details>
<summary>Original English</summary>

**Speaker A**: Where I kind of worked with it to prove the lemmas. And so what happened here was there was some lemma I wanted to prove, and the models couldn't do it. None of the frontier models could do it. And so I worked out a ton of examples on my own and I realized, "Oh, well, maybe here's some reason why it could be true." So I found a better statement of the lemma. And then, once I had that statement, probably I could have done it pretty fast, but also the models were able to very quickly prove that sort of better statement.

So our inability to prove it led to an improvement in the result. Okay, now you can take the original lemma I had that the models weren't able to prove, put it into ChatGPT-5.6 Pro, and it will output like the worst proof you've ever seen: like 10 pages of just brutal calculation with no insight whatsoever. And so, this would have been a perfectly fine proof, but it would not have led to this discovery of what I think is a kind of beautiful conceptual explanation for why this thing we discovered was true.

So we found a better proof because we couldn't do—I mean, I say we couldn't do the calculation, but what actually happened (and here I understand that I'm being hypocritical about my complaints about ugly proofs before) is like I realized this horrible grind proof would work and I just could not bring myself to do it.

</details>

**Speaker A**: 于是我转而去寻找另一种论证方式。虽然现在的模型已经能够相当可靠地处理非常冗长复杂的技术性计算了。

<details>
<summary>Original English</summary>

**Speaker A**: And so I looked for another argument. And it's not—yeah, but you know, now the models can do very long technical calculations pretty reliably.

</details>

### 数学的非形式化理解与概念压缩

**Speaker B**: 是的，平心而论，我觉得我能理解你的意思。你并不是说仅仅因为证明看起来丑陋就回避去证明某些东西，而是说你总得先迈出第一步，而最终大家追求的都是洞见。所以，哪怕你可能不好意思直接承认，但这背后依然是由审美驱动的，或者纯粹就是源于“我渴望真正理解它”。如果“理解”意味着让它变得更简单一点、或者信息压缩度更高，那么我就获得了理解。这也触及了一个深刻的哲学问题：究竟什么是理解？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, I mean, to your credit, I don't know. I think I understand why you're saying it's like: don't just shy away from trying to prove something just because it seems ugly, because you have to take the first step, right? And eventually you try to work towards insight. And so, you might be shy about admitting it, but it is still maybe driven by whether it's aesthetics or just pure, like "I want to understand." And if understanding just means it's a little bit simpler or more compressed, then I've gotten understanding. It's just like a deep philosophical question too, like what it is.

</details>

**Speaker A**: 对吧？我们做数学时之所以采用非形式化数学（informal mathematics），而不是把 ZFC 集合论等冗长生硬的形式化符号串直接写出来，除了篇幅原因之外，正是因为我们在试图以一种能够真正获得非严格但具洞察力的理解的方式来呈现它。

<details>
<summary>Original English</summary>

**Speaker A**: Right? Like I mean of course there's a reason we do informal mathematics rather than writing out long formal strings of symbols of ZFC or whatever, even though besides length, it's just like somehow we're trying to put it in a way where we are actually getting some non-rigorous understanding out. Yeah.

</details>

**Speaker B**: 我觉得在某种程度上……

<details>
<summary>Original English</summary>

**Speaker B**: I think somehow...

</details>

**Speaker B**: 没错，这甚至关乎为什么这种追求会有所助益。再说回来，这究竟是因为我们无法硬算，还是因为当我们追求更高压缩度的表达时，这种理解往往也能跨界帮助我们理解其他领域？当我们在追求这两者时，它们往往能奇迹般地重合在一起。我不知道这能否算作一个定量的结论，但这种重合确实带有一种神奇的色彩。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And even how that relates to why it helps. And again, is it because of our inability to grind, or is it because if we are pushing towards something that's more compressive, it also hopefully ascends on—does it help understand other fields as well? And it is somewhat magical that when we try to optimize for both, they tend to coincide. I don't know actually if that's a quantitative statement, but why that is is kind of magical.

</details>

**Speaker A**: 至少有些时候确实是这样。

<details>
<summary>Original English</summary>

**Speaker A**: It's at least sometimes true, yeah.

</details>

### AI 时代数学界的适应与学术激励困境

**Speaker B**: 没错，或者说我们本身就天然倾向于挑选那些能够重合的领域，所以我们才把构建那样的理论称为“好理论”。但无论如何，这正是我们能够去研究和理解的东西，而且非常凑巧的是，这些领域在数学成果上往往也异常丰富。

既然谈到了这里，我觉得有两条线索可以继续深挖。既然你已经认同（或者说坚信）AI 的数学能力将持续提升，并且已经能完成你日常工作中的一部分事情，那么数学界应当如何最好地适应并从中获益？

站在一个如今已经没有时间再做数学研究的人的角度来看，这太棒了，因为我可以随手涉猎更多东西，会有大量成果涌现出来；但我也能体会到你刚才提出的深刻观点——这可能会削弱人们去真正追求理解和数学发展的正确动机。所以我很想多听听你对此的看法。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, exactly. Or we certainly bias towards the cases in which it is, that's why we call that a good theory to build. But it's very much, I think, this is what we can study and understand, and therefore it's also very convenient that it was rich in kind of mathematical results there.

Yeah, I mean, okay, so I think there's two things that we can pull on, which is: given you believe that mathematical ability of AI is going to continue advancing and can do some of the things that you're doing nowadays, how should the mathematics community best adapt and benefit from this?

I mean, as somebody who doesn't have the time to practice mathematics anymore, this is very great because I can maybe dabble more, there's a lot of results that can come out. But I can also see where you've made the more precise point of: we can not motivate the right kind of behavior of understanding and development. And so I would love to hear more about your views there.

</details>

**Speaker A**: 好的。首先，看到能力越来越强的模型不断涌现并产出高质量的结果，这显然令人非常兴奋——至少有一部分是高质量的结果，当然也有大量的学术垃圾。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So, first of all, it is clearly really exciting that there are increasingly capable models that are producing high quality results. At least some high quality results, also a lot of slop.

</details>

**Speaker A**: 确实有些好东西。因此随着模型变得极其强大，我的期望是它们能够解答许多曾让我夜不能寐、苦思冥想的问题，让我得以知晓这些答案，这真的非常令人振奋。要知道，很多人当初投身数学，很大程度上就是因为热爱学习数学本身。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, some good stuff. And so, as the models get really capable, my hope is that they will answer a lot of the questions that I've been kept up at night thinking about, and I'll get to learn the answers. I think that's really exciting. And a lot of people got into math largely because they enjoyed learning math.

</details>

**Speaker B**: 确实。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 作为一个数学系学生，你入门做的第一件事就是学习别人已经做出来的成果，而且在开始自己做研究之前，你通常得这样学上 20 年——也许不用整整 20 年，但……

<details>
<summary>Original English</summary>

**Speaker A**: Like the first thing you do as a math student is you learn stuff that other people did, and you do that for like 20 years before you start doing—maybe not quite 20 years, but...

</details>

**Speaker B**: 15 年。

<details>
<summary>Original English</summary>

**Speaker B**: 15 years.

</details>

**Speaker A**: 运气好的话可能要 20 年，如果你起步早的话。

<details>
<summary>Original English</summary>

**Speaker A**: If you're lucky, 20 years, yeah, if you started early. Yeah.

</details>

### 数学的真正目标与人类学术生态的维系

**Speaker A**: 是的。话虽如此，数学的终极目标绝不是为了生产数学论文，而是为了产生某种理解。诚然，也许一部分“理解”最终会沉淀在模型的权重参数之中，但对我而言，那种形式是非常令人不满意的。

我个人做数学的动力，在于满足我个人的好奇心。我认为每个人都应当具备探索好奇心的能力，但这需要一套极其庞大的支撑体系。如果你没有投入巨大的时间和心血让自己达到能够有意义地参与其中的水平，你根本不可能去研究那些我认为具有根本性意义的问题。

更进一步说，即便站在金字塔尖、在最前沿从事高精尖数学研究的那一小群人，他们也依赖于一个极其庞大的社会体系支撑——那是由数以万计、数以百万乃至数以十亿计努力学习数学思维的人共同构成的。你需要一个完整的数学共同体来支撑前沿的少数人；如果没有这整套培养输送管道，前沿也就无从谈起。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So that said, the goal of mathematics is not to produce mathematics papers; it's to produce some kind of understanding. So maybe some of that understanding resides in model weights or something, but to me that's pretty unsatisfying.

My own motivation for doing mathematics is that I would like to satisfy my own personal curiosity. I think people should have the capability to do that, and that requires a pretty substantial apparatus. It's simply not the case that you can study the questions I think are fundamental unless you've invested a huge amount of time and effort getting to the point where you can meaningfully do so.

And then moreover, even the small group of people doing fancy research math on the frontier relies on a huge apparatus of thousands and millions or billions of people who are trying to learn to think mathematically. You need an entire mathematical community to support a small group of people who are on the frontier. Without the pipeline, the pipeline doesn't exist.

</details>

**Speaker A**: 所以，如果你认为培养能够有意义地参与前沿数学研究的人力资本至关重要，那么你就必须建立激励机制，去鼓励这些人真正投入时间和心血提升自我，以便他们能够参与其中，并以高质量、有意义的方式开展研究。

然而就目前而言，我认为现有的数学研究激励机制并没有鼓励人们这样做。比如现在一名正在找教职的博士后，在整个学术界做出调整之前的这几年里，拿到职位的最佳策略就是尽可能多地刷论文去解决旧猜想等；而他们完全可以通过像玩老虎机一样不断向大模型下指令……

直到模型吐出一个有望是正确的证明结果。这样一来，你甚至都不需要去深入挑选和理解……

<details>
<summary>Original English</summary>

**Speaker A**: So if you think that's important—development of human capital that can meaningfully engage with frontier mathematics—I think you still have to incentivize those people to actually invest their time and effort getting to the point where they can engage, and then do so in a high quality, meaningful way.

Right now, I think the existing incentive structures for math research do not encourage people to do that. Right now, if you're a postdoc on the market and you want to get a job, maybe for the next couple of years before the community adapts, the best way to do that is you want to produce a lot of papers which maybe prove old conjectures or whatever. And you can do that by playing the slot machine until the model produces a hopefully correct proof of such a result. So you don't even have to pick...

</details>

<!-- chunk 6/9 -->

### AI 证明的同质化与人类数学直觉

**Speaker A**: 提前知道定理。比如你可以做这样一个实验：用 Codex，让它去网上找代数几何领域最近提出的五个猜想并给出证明。我自己就做过这个实验，经过一番反复交互，差不多在一个小时内，就得到了三篇……可以说是挺糟糕的论文……

<details>
<summary>Original English</summary>

**Speaker A**: the the the theorem in advance. So like here's an experiment you can do. You can take codex, you can say go online, find five recent conjectures in algebraic geometry and prove them. And uh, okay, I've run this experiment and with some back and forth, I was able to, you know, in an hour get like three, you know, quite bad papers,

</details>

**Speaker B**: 但证明是正确的论文。

<details>
<summary>Original English</summary>

**Speaker B**: but correct papers.

</details>

**Speaker A**: 确实是正确的论文。现在它们就保存在我的硬盘里，等着我发邮件联系相关学者，但把时间花在核验这些结果上并不是什么好的利用方式。不过，你确实能看到很多人正在这么做。因此，提交到 arXiv 预印本平台的论文数量出现了暴增，其中绝大多数都没什么意思，当然也有一部分是有价值的。

<details>
<summary>Original English</summary>

**Speaker A**: Um, which, okay, are now sitting on my hard drive waiting for me to email the relevant people, but this is not like a good use of my time to invest results. But yeah, you you definitely see people doing this. Um, so there's, you know, been a huge uptick in post to archive, mostly not very interesting. Um, some of it is interesting.

</details>

**Speaker B**: 但很多内容显然质量不高，即便证明出的结论在放到一年前可能会获得极高评价，但字里行间完全看不出有真正的人类深度参与其中的痕迹。这并没有促进人类智力资本的积累或理解力的提升。有时候我们甚至能看到这样的情况：在短短两三天内，出现了三四篇甚至五篇论文，针对完全相同的定理给出了完全相同的证明。这显然就是有人在拿模型当老虎机刷结果。

<details>
<summary>Original English</summary>

**Speaker B**: Um, but, you know, a lot of it is kind of clearly low quality, even if in so far as the like even if the result is something that would have been like kind of highly rewarded a year ago, just like the there's sort of no evidence that a human being is actually engaged with it. Like there's no development of human capital or understanding. Like sometimes, you know, we've seen examples where like three or four or five papers with the exact same proof of the exact same theorem have come out in within a couple days of each other, which is clearly, you know, some situation where someone's playing the slot machine. Yeah.

</details>

**Speaker A**: ChatGPT 往往会极其一致地找到完全相同的路径。

<details>
<summary>Original English</summary>

**Speaker A**: Chat GPT is kind of consistently finding the same.

</details>

**Speaker B**: 这点非常有意思。它在某种程度上发生了“模式坍缩”（mode collapse），局限在了特定的推理路径上。

<details>
<summary>Original English</summary>

**Speaker B**: But that's also interesting. It's like not it's kind of mode collapsed on like certain paths of reasoning.

</details>

**Speaker A**: 没错。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 百花齐放与高维数学探索空间的萎缩风险

**Speaker A**: 而且我认为，随着模型性能的提升，这个问题并不见得就会自然消失。也许能解决，但也可能解决不了。就像我之前提到的，数学领域的很大一部分进展，都源于“百花齐放”，让不同的人追随各自的好奇心去探索。这样一来，人类知识的边界就能在数学这个极其高维的空间中，以一种相对均匀的方式向外拓展。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And I think it's like not obvious that this problem goes away as the models get better. Like maybe it does, but maybe it doesn't. Like I think a lot of what I was saying earlier is that a lot of progress in mathematics comes from like letting you know a thousand different flowers bloom and people pursue their own curiosity and then you know the boundaries of knowledge expand in some kind of fairly hopefully fairly uniform way and like this really highdimensional space of mathematics

</details>

**Speaker A**: 然后在某个机缘巧合的时刻，你就会突然获得意想不到的实际应用，或者解开过去悬而未决的老问题。但如果我们将数学探索完全从属于模型偏好的探索方向，目前还不清楚我们得到的究竟是一个被复制了一千遍的单一数学家，还是真正有一百万个各不相同的数学家在做一百万件完全不同的探索。抛开数学界必须通过改变激励机制来适应这一现状不谈，我认为这对于各大 AI 实验室来说，其实也是一个相当危险、必须引起重视的信号。因为一方面，促成他们当前成功的涌现推理能力固然极其强大，也赢得了大量的公关头条；但另一方面……

<details>
<summary>Original English</summary>

**Speaker A**: and then like opportunistically you you suddenly get some applications or like answers to old questions we found. Uh and it's like not clear to me that if if you know we kind of subordinate mathematical exploration to what the model want to pursue like if what you're getting is like one mathematician duplicated a thousand times or like actually you know a million different mathematicians doing a million different things. You know, I think actually that's pretty I mean, you know, aside from like okay, math has to adapt um by changing incentive structures, I think this is actually a pretty um um maybe dangerous or something that the labs have to pay attention to because you know on one side what's been successful for them is that this emergent reasoning capability is obviously incredibly powerful and we've been I mean it's creating a lot of like great PR headlines. But

</details>

**Speaker B**: 正如你所指出的，也是我非常关注的一点：人类数学家的直觉来自于各种各样奇特而多元的视角，正是这种多样性构筑了无比广阔的研究前沿，供人们从中汲取灵感、建立跨领域的连接并产出更多成果。如果各大实验室推出来的证明确实都在高度趋同，那是因为它们在技术层面上都是从同一批文献资料中汲取营养——这正是它们目前的强项所在。然而，它们最初的直觉是从哪里培养出来的？是从人类数学家的实践中习得的。目前根本不清楚模型是否能自发涌现出更强大、更多样化的全新直觉。也许未来可以，但我现在看不到明确的理论依据。而且，仅靠测试期计算（test-time compute）和各种后训练扩展（post-training scaling）是否真能引入全新的认知能力，学界对此依然存在巨大争议。我认为数学恰恰是研究这一问题的绝佳切入点，因为模型在哪些地方擅长、在哪些地方失败，以及人类数学家的长处究竟在哪里，在数学语境下都可以被非常精确地界定和考察。说了这么多，我的核心观点是：如果我们不能激励足够多的人类继续深入参与数学探索，那么与其他领域不同，数学可能无法在缺乏人类协助的情况下持续产出真正卓越的成果。

<details>
<summary>Original English</summary>

**Speaker B**: you know to your point and also like where my interests tend to is that like human mathematicians they are coming from all sorts of weird intuitions that like you know and that is why you end up developing you know to your point the frontier that is so diverse that you actually can draw from and then be able to connect and produce a lot more. And so it if it's true that most of these like proofs that are being pushed out by the labs are converging on very similar things because they are technically drawing on the same body of literature. Um and that's where they're strong at now. It's it's not clear that I mean one you know where are they developing their intuitions? It's from practicing mathematicians. It's not clear where that other emergent you know stronger diverse intuition might be coming from. It might come but I don't have a good theory for where it comes from. And it's also just not clear that you know just with like test time compute and various post-training scaling that you can even I mean it's a huge debate whether you could introduce new capabilities and it's like precisely I think it should be studied in the math context because like where it's good at and where it fails um and where human mathematicians are good is exactly a very kind of like precise um question to study it on. Um, so this is like a long way of saying that I it is unclear to me that we'll maybe produce um if we don't incentivize enough people to interact with it, maybe unlike other domains, it it might not actually uh continue producing uh a superior uh uh result uh without human aid.

</details>

### 超人类模型下的社会设计与人类主体性

**Speaker A**: 是的，让我顺着这个思路再进一步推演一下。假设模型最终真的在各个维度上全面超越了人类，以至于人类甚至无法再为其提供任何有实质意义的认知增量。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, let me actually push push a bit further even. So like let's suppose the models become like really robustly superhuman like even like we're not even adding like meaningful cognitive capacity. Okay.

</details>

**Speaker A**: 我认为，即便到了那个地步，人类依然没有输。

<details>
<summary>Original English</summary>

**Speaker A**: I claim like still actually we we still won.

</details>

**Speaker B**: 好的，请讲。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Great.

</details>

**Speaker A**: 作为人类数学家。为什么呢？因为这关乎我们希望如何构建人类社会的问题。也许……

<details>
<summary>Original English</summary>

**Speaker A**: Human mathematician. So, right. So, why? So, like it's because the you know there's like a it's like there's a question about how we've we're designing society, right? Like maybe uh

</details>

**Speaker A**: 最理想、最高效的状态是让模型包揽所有的数学研究，并在高度非均匀但极其多样化的路径上自行推进，也许根本不需要人类来提供多样性。这或许是最优解，而且最终能带来海量的应用和更深层次的理解等等。然而，某件事情在效率上是“最优”的，并不意味着我们人类就一定要这么做。

<details>
<summary>Original English</summary>

**Speaker A**: the optimal uh situation is like you have the models doing all sorts of math research and like that leads to very in you know in this like highly you know whatever non-uniform diverse way like maybe you don't need humans to add that kind of diversity. It's like maybe that's the optimal thing to do and like in the end that leads to lots of applications and lots of imp proofed understanding and so on. It's like despite like something being optimal doesn't mean you do it

</details>

**Speaker A**: 没错，完全没有理由认为，如果我们把数学研究的控制权全盘移交给模型，任由它们自行其是，它们就一定会做出对人类而言最理想的事情。事实上，如果我们只是工具化地去定义目标，比如告诉模型“让我们的生活变得更好”之类的话……

<details>
<summary>Original English</summary>

**Speaker A**: right like there's no reason to think that you know if we hand over control of whatever math research to the models and just let them do their own thing that it will do the optimal thing. Um and in fact like if you you know if we are if we kind of instrumentalize what we want them to do like we want to say like oh you know make our life better or whatever

</details>

**Speaker A**: 它们所选择采取的行动，未必会去广泛探索丰富多样的有趣基础研究。它们可能会直接走捷径，我们根本无法预测未来会发生什么。

<details>
<summary>Original English</summary>

**Speaker A**: it might not be the case like be that that like what they decide to do that is like is is pursue a wide variety of interesting research right like they might just try to take the direct path we don't know what's going to happen

</details>

**Speaker A**: 如果你也认同这种广泛的基础研究具有不可替代的价值——我坚信这是人类或模型所能从事的最有价值的事情之一——那么确保它持续发生的最好方式，就是维系一个拥有广泛兴趣的人类社群。这个社群能够不断促使模型去探索，并协助我们共同设计一个以此为导向的人类社会。

<details>
<summary>Original English</summary>

**Speaker A**: um so I don't know if you believe that there is any value in sort of this broad-based like uh fundamental research which I do look I think that's like one of the most valuable as human humans or or whatever or the models can be doing like I think the easiest way to guarantee it happens is like to keep a community with like broad interests who are like pushing the models to do and like helping us to design a society where like that's what we're what we're pushing for.

</details>

**Speaker B**: 赞同。至少对我而言，我对未来的美好愿景是：人类不会被彻底剥夺能动性，我们对未来的走向依然拥有掌控力。如果是这样，人类最终所做的一切，都应当由人类自身的兴趣和价值来驱动。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Like I think at least you know my my hopeful vision for the future is that like humans are not like totally disempowered like we have some control over where we're going and like if that's the case like what we end up doing is going to be driven by human interests

</details>

**Speaker A**: 因此，我们需要有一群拥有广泛多样兴趣的人，同时他们还要具备将这些兴趣付诸实践的能力——我们需要聪明、积极投入、不仅具备数学思维而且具备全方位深度思考能力的人。

<details>
<summary>Original English</summary>

**Speaker A**: and so you want to have people who have lots of different interests and also the capabilities to actually pursue them like you want people who are like smart and engaged and like you know well can do not just like mathematical thinking but all sorts of thinking.

</details>

### 数学思维的教育价值与人类深度思考能力

**Speaker B**: 是的，非常赞同。一个巨大的隐忧在于，随着 AI 的不断演进，我们并没有开发出合适的人机交互与协同界面来激励人类继续保持深度思考的能力。我们太容易彻底放弃思考并将一切外包出去，而模型目前甚至还不擅长那种顶层的全局结构性思考。但即便如此，人们依然极易放弃自己的思考能力。尤其在数学领域，退一步讲，哪怕从个人的自私角度来看，追求数学思维最大化（math max）本身就是一个绝佳的教学训练抓手，能让人在思考各种复杂问题时变得极其严谨。虽然这并不是职业数学家研究数学的初衷，但对我们很多人来说，这确实是我们做这件事情的重要意义所在。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. I mean, yeah, a great fear is like as AI advances, we don't develop the right ergonomic um kind of interfaces to actually encourage us to also be good continue to be good thinkers and and it's so easy to kind of um relinquish that because you just off and and the models aren't even good at that level of like you know thinking where it's like the top level structure but despite that it's it's so easy to and so especially for math I mean just like you know another selfish reason is um if you kind of math max you know I think it's actually a great pedagogical um uh excuse to actually get just really rigorous at thinking about various things. I mean this is not why mathematicians do it. Um but as just somebody that's part of what we do

</details>

**Speaker A**: 确实如此。因为学习数学能为思考很多事情提供极佳的思维框架，而不仅仅局限于数学本身。作为一名刚有两岁孩子的父亲，我自己也经常深入思考这个问题。这不在于盲目刷题和苦练——虽然适度练习仍然有益，但绝不应过度沉溺于刷题——回想起我过去与几位匈牙利数学家密切合作的经历……

<details>
<summary>Original English</summary>

**Speaker A**: Okay, great. Because it was kind of, you know, I thought it just really helped give me a very um good framework to think about many things, not just mathematics. And as somebody who's also, you know, now a parent of a 2-year-old, I kind of think about this a lot, too. you know, it's it's not about kind of grinding, even though whatever it's still good, but like not to not to um on grinding too much, but you know, just hearing I I used to collaborate a bunch with some Hungarian mathematicians, um

</details>

<!-- chunk 7/9 -->

### 数学教育的普及与 AI 的深远影响

**Speaker A**：……在他们当中，我听说在布达佩斯，他们在小学阶段就会教群论。我当时就想，我们绝对应该这么做，而且应该继续坚持这么做。现在 AI 在解释概念方面已经做得相当不错了，而且获取门槛大幅降低，我们实际上可能更应该大力推广这种教育。这样或许有助于把更多人带到学科前沿，而不仅仅是停留在表面。

<details>
<summary>Original English</summary>

**Speaker A**: ...among them, and I heard that in Budapest, they would just teach group theory when you're in primary school. And I'm like, well, we should definitely do that. We should continue doing that. Now that AI is somewhat good at explaining, but it's far more accessible, we should actually probably proliferate that even more. And so maybe that helps with bringing more people to the frontier rather than just...

</details>

**Speaker B**：是的。这也是我一直关注的事情。当然，我主要谈论数学，因为那是我的专业领域。但我认为思考这个问题的一个好处在于，数学是首批受到高质量模型重大影响的行业之一。不过我认为，我们可能只是首批将这种影响如此公开化展现的行业之一。就我的感觉而言，还有很多其他行业正在经历同样的事情……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I mean, this is something I'm concerned about, right? And of course I mostly talk about math because that's like where I live. But I think one nice thing about thinking about this is that we're one of the first professions to have a significant impact of high quality models. Although I think maybe we're one of the first professions for it to happen so publicly. You know, my sense is that there are plenty of other professions that are...

</details>

**Speaker A**：百分之百。比如编程。

<details>
<summary>Original English</summary>

**Speaker A**: 100%. Coding.

</details>

**Speaker B**：编程确实如此。但不仅如此，我认为你在电脑上做的任何事情，目前大概都有巨量的工作是由模型完成的，只是大家还没有对此进行公开的反思和审视。

<details>
<summary>Original English</summary>

**Speaker B**: Coding. But also just like, I mean, I think that anything you do at a computer, like probably a huge amount is being done by the models at this point, and then like they're not having a public reckoning about it.

</details>

**Speaker B**：因为数学能力对公司、对研究实验室来说非常有用，所以他们拿出来公开讨论的频率大概比其他领域都要高得多。不过话说回来，我认为在这个领域保持人力资本的一个原因在于，它是所有行业的一个缩影：我们大概率依然希望人类能切实地参与这个世界，成为拥有真才实学、受过专业训练技能的专家等等。而且实际上非常巧合的是，数学界在这里与教育紧密交织在一起，因为我们现在也看到高等教育和中等教育正面临着来自 AI 的诸多挑战。

<details>
<summary>Original English</summary>

**Speaker B**: Because math capabilities are useful for the company, for the labs to talk about, I think probably a bit more publicly than everyone else. But yeah, I mean I think one reason to try to maintain human capital in this area is just like it's a model for all professions: like presumably we still want people who are like meaningfully engaging with the world and like experts and have talents and trained skills and so on. It's actually very convenient that the math profession is so entwined with education here, because I think we're also seeing some amount of challenges among college and secondary education coming from AI too.

</details>

### 教育中的双峰分布与认知能力的保持

**Speaker A**：正如你所说的，它也是一个绝佳的学习工具。

<details>
<summary>Original English</summary>

**Speaker A**: So as you said, I mean it's also an amazing tool to learn.

</details>

**Speaker A**：我听说有些人已经开始谈论他们课堂上出现的双峰分布了：一部分人真正搞清楚了如何利用这些新工具，而另一部分人则只是让 AI 替自己写作业，然后其他一切考核都一塌糊涂。

<details>
<summary>Original English</summary>

**Speaker A**: You know, I've heard people start talking about a bimodal distribution in their classes, where there's some people who are really figuring out how to take advantage of new tools, and other people who are just letting them do their homework and then bombing everything else.

</details>

**Speaker B**：不幸的是，我认为现有的体系适应得不够快。但我们显然希望生活在一个能够培养出更优秀思考者的世界里。我认为哪怕仅仅从纯粹的优化博弈角度来看，这也对我们更有利。

<details>
<summary>Original English</summary>

**Speaker B**: Unfortunately I don't think that adapts fast enough, but it's like we definitely want to be living in a world where we're producing better thinkers. I think even if we talk about just the pure kind of optimization game, I think that's better for us.

</details>

**Speaker A**：作为人类个体，我觉得如果恰恰在 AI 崛起的时刻我们自己的思维能力反而退化了，那将是一件非常糟糕且麻烦的事。而任由这种情况发生又实在太容易了。所以我们应该深入思考如何真正利用并驾驭它来提升我们自己，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: And so, as just a human being, I'm like that would be pretty inconvenient if we became worse thinkers just as AI ascends. And it's too easy to let that happen. So we should kind of be thinking hard on how to actually take advantage of this and harness it for our own improvement, right?

</details>

**Speaker B**：没错。观察现状是很有趣的：模型以目前的能力水平确实能让你做更多的事情。它们能让你以足够低廉的成本去做许多以前不会去做的事。但在很多情况下，我并不觉得它们真正提升了产出成果的质量。

<details>
<summary>Original English</summary>

**Speaker B**: Well, yeah. I think it's sort of interesting to observe like the models at their current level of capabilities let you do a lot more. They let you do a lot of things you wouldn't have done more cheaply than—you know, cheaply enough to do them now. But it's not clear to me that like in many cases they're actually improving the quality of outputs.

</details>

**Speaker B**：是的。而且我认为这是一种普遍现象：当一项新技术出现时，它做某件事的质量可能比以前稍逊一筹，但成本却便宜得多，于是突然之间就会涌现出大量低质量的产出，挤占了以往的高质量成果。但我认为完全有可能以一种在各个维度上都切实提升质量的方式去使用这些工具，这只需要更多的深思熟虑，以及对制度进行重新设计以形成实际的激励机制。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And I think this is common, like you have a new technology that's doing something a little bit worse than was previously done but much cheaper, and so you get a lot of suddenly a lot of low quality outputs that are displacing previous high quality outputs. But I think it's possible to use the tools in a way that actually improves the quality along every dimension. It just requires some thoughtfulness and some redesign of institutions to actually incentivize that.

</details>

**Speaker A**：对，希望市场机制能在这方面发挥作用。我确实觉得那些最高价值的事情仍然需要人们去高效地使用工具，而且目前如果没有人类专家的参与，模型本身还不够好。但正如你所说，绝大多数可能处于更初级、入门级别的角色更难适应这种转变。因此，如果以一种无法让人获得提升的方式去使用 AI 模型，那将是一个巨大的错误。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Well hopefully capitalism works there. I do feel like that the most high value things do require people to use it effectively and and right now the models are not good enough without like the human experts to actually participate. But to your point there's a vast majority of maybe like more junior and entry level kind of roles—it's harder for those roles to adapt as well. And so the thing that would be a mistake is to use the AI models in a way that doesn't...

</details>

**Speaker A**：基本上，你必须不断提升自己，利用模型来加深你的理解。人性本能往往很容易偷懒，你必须抵抗这种惰性，因为一旦你偷懒，就是你注定要落败的时刻。请原谅我用了这种充满竞争性的字眼，但现实确实如此：把思考完全让渡给模型实在太容易了。模型并不能真正地思考。因此，在技术演进如此迅速的当下，至关重要的一点是你要不断锤炼那些思维能力，切实利用工具来增强这些能力，而不是放弃它们。

<details>
<summary>Original English</summary>

**Speaker A**: Basically you need to be ascending and using the models to deepen your understanding. And it's so easy for human nature just to be lazy and you have to resist that because that is the moment that you will kind of lose basically. And so, forgive the very competitive language, but it really is that: it's just so easy to relinquish the thinking to the models. The models can't really think. And so as things are ascending so fast, it's like critical that you continue developing those facilities and actually leverage it to improve those facilities rather than relinquish. Yeah.

</details>

### 学术产出、水论文与公众对数学的关注

**Speaker B**：对，没错。我认为，在半专家注意力或模型对数学问题的关注度出现爆发式增长之后，一件令人欣慰的好事是——尽管我之前一直在抱怨各种劣质灌水论文（slop papers）等等，也就是那些并非真正高质量成果的东西。但这些劣质论文往往实际上出自专业学者之手；我并不是说学术界内部没有追求大量发文的激励机制，那本身就是灌水论文的一个来源。当然，现在肯定也有来自非专业人士的劣质论文，但在我看来，这实际上并不是一件坏事。虽然这确实导致互联网上充斥着大量文档，人们可能不得不仔细梳理才能弄清楚某个问题到底有没有被解决。但对我而言，仅仅是有这么多人对数学感到兴奋，本身就是一件非常积极的事情。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. I mean, one thing I think has been nice about sort of this vast increase in semi-expert attention or model attention on math problems is like now there's been—okay, I've been complaining about slop papers or whatever, like people who are not producing really high quality stuff. Often that's actually coming from professionals; it's not—I'm not saying within academic mathematics there are incentives to produce a lot of stuff, and that's one place the slop comes from. So there's definitely also slop coming from non-experts, but that I kind of actually don't see as a net negative. Like okay, now there's a lot of documents on the internet one might have to comb through to figure out if a problem has been solved or not. But to me it seems like just the fact that there's lots of people excited about math is kind of a positive. So that's like a nice...

</details>

**Speaker A**：我完全同意。现在我也能参与讨论了。

<details>
<summary>Original English</summary>

**Speaker A**: I totally agree. I know I get to talk...

</details>

**Speaker B**：而且这显然不仅是稍微有点积极，而是非常正面的。

<details>
<summary>Original English</summary>

**Speaker B**: And not even kind of a positive, obviously.

</details>

**Speaker A**：是的，完全没错。这就像聚光灯突然打在了数学上，我可以更尽情地探讨数学了。其实我挺好奇的，你对昨天刚公布的关于秩为 30 的椭圆曲线有什么看法吗？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. No, exactly. It's like suddenly there's a spotlight on it and I can nerd out about math more. I was actually kind of curious, you've got any comments on the—I guess this is another constructive result, but the elliptic curve of rank 30 that just came out yesterday.

</details>

### 秩为 30 的椭圆曲线构造与 AI 参与

**Speaker B**：确实有这么回事。

<details>
<summary>Original English</summary>

**Speaker B**: That's right.

</details>

**Speaker A**：对，没错。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah.

</details>

**Speaker B**：我们目前其实还没有关于它的任何具体细节。

<details>
<summary>Original English</summary>

**Speaker B**: Well, I mean, we don't have any details about it yet.

</details>

**Speaker A**：我知道，目前外界有一些传闻。

<details>
<summary>Original English</summary>

**Speaker A**: I know. There's rumors.

</details>

**Speaker B**：是的，我们不知道它是怎么做出来的。我的意思是，据说是通过 Claude 模型，由 Levent Poge 提供提示词……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, we don't know how it—I mean, so it was due to I guess Claude Fable prompted by Levent Poge and... right.

</details>

**Speaker B**：还有一位合作者，很遗憾我把名字给忘了。也许你可以在后期制作时加上。

<details>
<summary>Original English</summary>

**Speaker B**: A collaborator whose name I unfortunately forget. Maybe you can add it in post.

</details>

**Speaker A**：我只知道他的 Twitter 账号。

<details>
<summary>Original English</summary>

**Speaker A**: I just know the Twitter handle.

</details>

**Speaker B**：行，我们可以后期补上。近期很多不错的成果都出自 Levent，但其中 AI 的自主程度到底有多高尚不明确。依我的感觉，其中有些是半自主生成的，而不是全自主。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, we can. So yeah, I mean, a lot of these nice recent results have come from Levent with unclear amounts of autonomy. So my sense is that some of them are semi-autonomous rather than fully autonomous.

</details>

**Speaker B**：对于这个具体结果，我们对所采用的方法一无所知。所以，这确实是一个很有意思的构造性成果，但在不了解具体方法的情况下，很难去评价其重要性到底有多大。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, with this we don't know anything about the methods. So yeah, this is a fun construction. Without knowing about the methods, it's very hard to say how significant it is.

</details>

**Speaker A**：确实如此。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**：我想说的是，如果你想了解数学界在历史上是如何看待这类成果的，大家通常会觉得很酷，但并不会认为这是一个天大的突破。这种成果通常会被收录在某人的纪录追踪网站上。

<details>
<summary>Original English</summary>

**Speaker B**: What I would say is that if you want to understand kind of historically such results have been understood by the community, they're like cool, but I wouldn't say they're like a big deal. So like the typical place a result like this might go is like someone's website of records.

</details>

**Speaker A**：比如并不是……

<details>
<summary>Original English</summary>

**Speaker A**: Like not...

</details>

**Speaker B**：这并不是能够登上《数学年刊》（Annals of Mathematics）级别的成果。

<details>
<summary>Original English</summary>

**Speaker B**: It's not an Annals level result.

</details>

**Speaker B**：对，它算不上顶刊级别的成果。但话虽如此，它确实很酷，而且历史上确实有几位非常有才华的数学家对这类问题情有独钟，诺姆·埃尔基斯（Noam Elkies）或许就是其中最著名的例子。埃尔基斯和克拉古纳奇（Zev Klagsbrun）等人长期以来一直在刷新这一纪录，他们最近刚刚找到了一个秩为 29 的例子。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it's not an Annals... but that said, it's cool, and it's like a—definitely there are a few very, very talented mathematicians who like these kinds of questions, Noam Elkies being maybe the most famous example. So Elkies and Klagsbrun are the ones who kind of have been pushing this record for a while, and they recently found a rank 29 example...

</details>

**Speaker A**：也就是此前的纪录。

<details>
<summary>Original English</summary>

**Speaker A**: Example which was, you know, the previous record.

</details>

**Speaker B**：是的。他们都是真正的数学家。我认为人们喜欢看到这种进展，现在模型能够做到这种事情确实很酷。但正如我常说的，对于模型产生的结果，你只有在事后复核时才能真正评估它的价值。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. You know, so those are mathematicians. And I think people like it, and it's cool now that the models can do this sort of thing. But yeah, one thing I always say about a model result is like you cannot evaluate it except in retrospect.

</details>

<!-- chunk 8/9 -->

### 数学研究中的不确定性与 AI 解题验证

**Speaker A**：人类数学研究也是如此。有时候我们认为某个问题极其重要，或者觉得它必然需要非常深刻的新思想才能解决，结果可能根本不需要；而有时候它又确实需要，你在事先是根本无法确切知晓的。因此，当这类问题被攻克时总是令人兴奋，但要想弄清楚它究竟有多大的学术意义，你依然必须深入审视其证明过程。比如 Levent、Claude，我想还有 Ava Howell，可能是第三位合作者。

<details>
<summary>Original English</summary>

**Speaker A**: And like this is also true of human mathematics. Like sometimes a problem we thought was really important or would require really deep new ideas does not, and sometimes it does and you can't really know in advance. So it's always exciting when a problem like that gets solved, but then like to figure out how significant it is, you still have to look. And like well Levent and Claude and I think Ava Howell maybe is the third collaborator.

</details>

**Speaker B**：好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker A**：他们目前还没有公布具体是如何做到的。所以……

<details>
<summary>Original English</summary>

**Speaker A**: Have not yet told us how they did it. So...

</details>

**Speaker B**：他们一直以来都比较保密吗？我记得他们之前发布过一些关于其他成果的推理追踪记录（traces）。

<details>
<summary>Original English</summary>

**Speaker B**: Have they been mostly more secretive? I think they've released some traces for stuff. But...

</details>

**Speaker A**：是的，对于这一个成果，除非我漏掉了什么，否则他们目前应该还没有公布。Levent 很喜欢在推特上发布他的研究成果，不过他也一直在逐步发布一些 PDF 格式的研究报告。我觉得他只是在互联网上享受探索的乐趣。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so for this one, I think they haven't yet, unless I missed it. Yeah, Levent likes to tweet out his results, but yeah, he has been slowly releasing some kind of PDF writeups, too. I think he's just having fun on the internet.

</details>

**Speaker B**：确实是这样。这让我想起你刚才提到的观点——我们需要评估这些结果究竟是如何得出的。不久前我邀请了来自 OpenAI 的 Mark Zelki 和 Metab Swani，他们提到目前最令人欣喜或着迷的一点，就是生成的证明相对都比较短小精悍。它们并不是动辄 200 页的冗长论证，这也恰好呼应了你之前关于繁琐死磕（grinding）的观点。不过，这会不会是事后筛选的结果——正因为证明很短才被挑选出来展示，还是说你发现平均而言也是如此？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. It reminds me of when you're saying, you know, you have to evaluate how the results came. I had Mark Zelki and Metab Swani on from OpenAI recently, and they were saying how what's kind of been the most charming or delightful is just that the proofs have been relatively short. They're not like 200-page, and you know maybe corresponding to your grinding point as well. But maybe this is kind of optimized for in retrospect—it was picked that it was short, or do you find that on average...

</details>

### 短证明与长证明的验证困境

**Speaker A**：只是我们无法确定长证明是否正确。比如 OpenAI 最近公布的 10 个数学问题列表，它们全部都在 Lean 中完成了形式化验证。

<details>
<summary>Original English</summary>

**Speaker A**: ...just not sure if they're true. Um, so for example, uh, you know, with these this recent list of 10 problems uh, released by OpenAI, those were all formalized in Lean,

</details>

**Speaker A**：这当然是证明它们正确性的极佳证据。但我毫不怀疑，肯定还有很多问题他们无法在 Lean 中形式化，比如因为所需的前提定理和概念尚未被收录到数学库（Mathlib）中。

<details>
<summary>Original English</summary>

**Speaker A**: which is of course a very good evidence that they're true. I have no doubt that there were a lot more that they could not formalize in Lean, like because the prerequisite options have not been put into Mathlib yet for example.

</details>

**Speaker A**：而且很可能还有很多篇幅更长的证明，而篇幅一长，核对验证就会变得极具挑战性。

<details>
<summary>Original English</summary>

**Speaker A**: Um there were probably more that were longer which also makes it challenging to check.

</details>

**Speaker B**：明白。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**：所以这是我的推测。实际上我们在 arXiv 上确实看到了非常冗长的机器生成证明。例如最近有人贴出了一篇声称解决了“正特征下的奇点消解（resolution of singularities in positive characteristic）”的论文，整整有 800 页的 AI 生成内容。虽然我没有通读它，也没有直接挑出其中的具体错误，但这绝不可能是正确的——如果真的证明了，那将是一项极其重大的划时代成果。只要你对当前模型的认知足够理性客观，就知道这完全超出了现有模型的能力范围。

<details>
<summary>Original English</summary>

**Speaker A**: Um so yeah this is my guess and we do actually see very long generated um proofs on the arXiv. Um so for example someone recently posted a claimed proof of resolution of singularities in positive characteristic which was 800 AI generated pages. Um it's like definitely I mean I'm sorry I haven't read it I haven't got an error but there's no way it's correct like this will be a major result. It's just not within the capacities of the current models if you're reasonably well calibrated.

</details>

**Speaker B**：确实，完全赞同。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah.

</details>

**Speaker A**：而且绝对没有任何人类去通读核对过它，现在的模型也根本没有能力审查这种体量的证明。所以我认为，模型目前之所以能产出精巧简短的成果，仅仅是因为只有这种长度的证明是我们人类能够核查验证的。

<details>
<summary>Original English</summary>

**Speaker A**: Um and it's definitely no human has read it. Definitely the models are not able to check this kind of thing. Yeah. Um so well I mean um yeah. So this is my expectation is that the reason it's producing short clever things is just like that's what we can check.

</details>

**Speaker B**：没错。如果让它去生成冗长、繁重或难以核验的内容，它也能做出来，但是……

<details>
<summary>Original English</summary>

**Speaker B**: Yep. And you can get it to produce long things that are grindy or hard to check. But then...

</details>

### 前沿能力与长程脚手架的权衡

**Speaker B**：是的，我们还需要逐步发展才能达到那一阶段。这其实更能客观反映前沿模型能力的真实边界，从某种略显局限的角度来看，而不是盲目认为它“就擅长做这种精巧的事情”。我认为这种评价非常公允。尤其如果你观察代码等相邻领域，情况也是类似的对吧？我记得读过 Cursor 发布的一篇测试长流程（long-horizon）测试框架（harness）的文章，当时他们试图用 Rust 重写 SQLite。那项测试非常清晰地展现了我们距离真正实现长程自主目标还有多远。这与数学证明非常相似：任务周期极长，你必须通过一整套测试用例来验证实现的正确性；而且你必须依赖专门的框架系统，而不仅仅依靠裸模型本身。整个过程耗时漫长，你还可以对比前沿模型与非前沿模型作为规划器（planner）时的表现及能力差异。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, yeah, we'll have to get there. This is actually more what it says about capabilities, frontier capabilities, rather than in a perhaps more negative way rather than, hey, it's just, you know, so good at these clever. No, I think that's totally fair. I mean, especially if you look at an adjacent domain like code, right? Um remember reading something Cursor put out about testing their long horizon you know, harness. In this case they're trying to reproduce SQLite in Rust and it was just so telling like how far we are from that. And that seems like a very comparable task of like it's very long, you have to make sure there's something to verify that it's a correct implementation by testing a suite of cases. But you know you actually need a harness there in this case, it's not just like the raw models and it takes a while, and you can actually compare with different frontier versus non-frontier models, who's the planner, etc. like differences in their capabilities as well.

</details>

**Speaker A**：是的。而且在实践中，要引导模型生成长篇证明，基本上必须借助特定的框架系统（harness）。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I also think in practice like the uh to elicit a long proof, you kind of need a harness.

</details>

**Speaker B**：没错。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**：然而，当你构建一个以“生成证明”为目标的框架时，它往往会降低输出的可靠性，因为系统此时的首要目标只是为了挤出产物。例如 GPT-4 / o1 这类前沿推理模型通常会尽力避免给出错误陈述，虽然错误仍会发生，但当你反问它“这是否正确”时，它往往能承认错误。然而，当你试图激发它的发散构思与创造力，试图让它跳出极度严谨但保守的思维定势以推进证明时，情况就不同了。现在很多人试图套利学术数学领域的声誉机制，想方设法诱导模型生成大量证明，而这些证明往往缺乏严格核验。为了刷出大量内容，往往只能以牺牲可靠性为代价。因此我认为，任何能引导模型生成 250 页论文的框架系统，大概率都没有对其输出的严谨性进行严格把控。

<details>
<summary>Original English</summary>

**Speaker A**: And um when you make a harness whose goal is to elicit a proof, I think it often decreases reliability because you're just trying to produce output. Um so like ChatGPT Pro like really tries not to say wrong stuff for example and although you know it happens and then you'll ask it like oh was that correct and it'll say no. Um but uh you know when you're trying to get it to ideate like you try to get it to be creative. You try to get it out of this very like you know rigorous rut in order to like you know actually get it somewhere. And I think if your interest is in—I mean there are a lot of people who are you know trying to arbitrage the prestige mechanics of academic mathematics and trying to elicit a lot of proofs which are not necessarily being checked and in order to do that I think you just decrease the reliability in order to get a lot of stuff. Um, so you know, I think any harness that can elicit a 250 page paper is probably not being very careful about what it's producing.

</details>

**Speaker B**：所以你的意思是，可靠性下降或不可靠，纯粹是因为底层能力尚未达到要求，而框架却强行给它施加了超长流程的任务负荷？

<details>
<summary>Original English</summary>

**Speaker B**: And and you're saying that it's decreasing or it's not reliable just because it's the capability isn't there yet and so it's just kind of forcing a long longer horizon task on it.

</details>

**Speaker A**：是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

### 全局结构审查与模型的宏观验证短板

**Speaker A**：在实践中，人类专家在核验 250 页的长篇论文时，也不可能逐行进行逐字核对。人类理解并检验这类长文的方式，是先把握论证的整体全局结构，并从各个维度进行压力测试——例如：“这个论证方式是否能推出某个已知为假的命题？”或者“它在某个特殊边界情况下是否依然成立？”等等。而目前的模型似乎还不具备这种对证明进行模糊“单元测试”的全局宏观审视能力。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean in practice like how does like a human checking it like can't check a 250 page paper either like you know you can't reliably check it line by line. What you try to do to understand it is you try to like understand the overall global structure of the argument and you like stress test it in various ways like would this argument imply something else that I know to be false? Like oh does it work in this special case? Blah blah blah. And also the models seem not to be able to do that kind of like more I don't know fuzzy like unit testing a proof very well yet.

</details>

**Speaker A**：事实上，我最喜欢用来测试模型的一项测试（目前还没有模型能够通过），源自几年前发表的一篇论文——这里我就不点名了。那篇论文是错误的，但它声称证明了一个重大成果，且研究领域与我非常接近，所以我当时立刻下载并开始阅读。要在其中找到具体的某处硬伤极其困难，但从其论证的大框架结构来看，显然是不可能成立的。如果将它的逻辑稍作推广，就会推导出一个明显强到荒谬且不可能为真的结论。

<details>
<summary>Original English</summary>

**Speaker A**: So actually like one of my favorite tests for the models which they haven't succeeded at yet is there's a paper, I won't name it, that came out a couple years ago that was wrong, and it was in close enough area to myself that was claiming some big result like I immediately downloaded and started reading it. And it was very hard to find the actual specific error, but it was also very clear from the structure of the argument that it couldn't work. It was like arguing something that was too strong to be true if you kind of took that a little bit further.

</details>

**Speaker B**：明白。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**：我和其他几位领域内的专家立刻意识到这篇论文有问题，于是给作者发了邮件，几方反复沟通探讨，直到最终有人准确定位出了那个极其具体的细微错误所在。

<details>
<summary>Original English</summary>

**Speaker A**: Um so me and a bunch of other experts like immediately realized it was wrong and we emailed the author and we kind of went back and forth until someone figured out what the precise specific error was.

</details>

**Speaker B**：好的。

<details>
<summary>Original English</summary>

**Speaker B**: Okay.

</details>

**Speaker A**：到目前为止，AI 模型似乎完全无法胜任这种工作。那个具体的错误本身非常隐蔽微小，而模型既找不出具体错误，也缺乏这种宏观把控全局结构、进行大局观压力测试的能力。

<details>
<summary>Original English</summary>

**Speaker A**: Um and so far the models seem not to have been able to do this. Like the specific error is quite subtle and but they're also not able to do this kind of overall uh kind of big picture test.

</details>

<!-- chunk 9/9 -->

### AI 辅助架构、数学推理与 Harness 的协同演进

**提问者**：……检查，这在某种程度上就像人们在实践中检查论文一样。

<details>
<summary>Original English</summary>

**Interviewer**: ...checking, which is kind of like how people in practice check papers.

</details>

**提问者**：是的，确实如此。这有点像我们在写代码时看到的情况：模型在语法层面上表现非常出色，但在更高层次的架构设计上仍然非常薄弱。也许未来它会上升到那个高度，但可能需要一些 Harness（测试运行框架 / 脚手架）的辅助。谁知道呢？我的意思是，对于 Harness 和模型之间需要多大程度的协同演进、哪一个是必不可少的，人们的看法一直在不断变化。但随着下一个更强模型的出现，对 Harness 的依赖可能会减少。所以我觉得在数学领域，看看你是否会在 Harness 方面做一些实验，以及它是如何带来改进的，将会非常有趣，因为这正是通用推理能力的标志。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Yeah. Which is kind of it mirrors you know why in code it's like it's so clear it's good at the syntax, but you know higher level architectural stuff is still very weak. Maybe it'll ascend there, but probably need some harness help. Who knows? I mean, people have, you know, evolving opinions on how much the harness and the model have to co-evolve and which one is necessary, but the next model requires less. So, I feel like in math, it'd be very interesting to see if you do any experiments with the harness there and how that improves, because it is a mark of general reasoning. Yeah.

</details>

**Daniel**：是的。我确实有一些自己写的简易小 Harness 和 Codex 工具，但就我个人而言，我其实并不太享受全自动化的数学研究（autonomous mathematics）。所以我基本上不用 Harness 去做全自动证明，我主要还是用它来帮助我自己理解问题。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. I mean, I do, you know, I have my own sort of bad little harness and Codex, but you know, I personally, I do not enjoy autonomous mathematics very much, so I mostly do not use the harness. I mostly try to use it to help me understand stuff.

</details>

### 数学教育的本质价值与 AI 时代下的思考

**提问者**：好的，这完全合情合理。确实如此，你并不希望把自己的工作完全自动化剥离掉，因为这需要你始终保持在回路中（human-in-the-loop）去理解它，而这种理解正是参与其中的必要条件。

最后作为收尾，我很想聊聊——这可能是一件你还没深入思考过，或者其实已经思考了很多的事情：我记得你有一个刚学会走路的孩子，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: Okay. No, it's totally fair. Yeah. Exactly. You don't want to automate your job away, because that does involve you being in the loop to understand it, which is, you know, necessary to participate. Maybe to finish off, I'd love to—and this could be just something you haven't thought about or actually thought a lot about—I think you also have a toddler, right?

</details>

**Daniel**：对的。

<details>
<summary>Original English</summary>

**Daniel**: Yeah.

</details>

**提问者**：是的，一个三岁的小孩？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. A three-year-old?

</details>

**Daniel**：对，三岁。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. Three-year-old.

</details>

**提问者**：太棒了。相比一年前，她又长大了一岁，你可能对此有了更多的思考。比如，你现在是如何考虑她的教育的——特别是她在数学方面的启蒙？并不是要去死记硬背或刷题（grind），而是如何将对数学的热爱传递给她，以及如何去应对 AI 带来的变化？

<details>
<summary>Original English</summary>

**Interviewer**: Great. Right. So you're one year more advanced and probably, you know, have more thoughts on this. Like how are you thinking about her education in math? And you know, not to grind, but really just how to pass on the love of it, and how to react to AI.

</details>

**Daniel**：是的，她现在三岁，还从没用过 AI。她最近开始学习做加法了，这就是我们目前在数学上达到的进度。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. So she's three. She's never used AI. She is starting to add, that's about as far as we are in math.

</details>

**提问者**：那已经很不错了！

<details>
<summary>Original English</summary>

**Interviewer**: That's more than—

</details>

**Daniel**：她可以通过数手指来算个位数的加法，能很稳地数到 30，大概数到 50 左右算半稳定吧。我为此感到非常自豪。

<details>
<summary>Original English</summary>

**Daniel**: She can add single-digit numbers by counting on her fingers, and count up to like maybe 30 reliably and 50 semi-reliably. So I'm very proud of that.

</details>

**提问者**：真棒，太好了。

<details>
<summary>Original English</summary>

**Interviewer**: That's good. Yeah.

</details>

**Daniel**：是的，我确实一直在鼓励她。我们会一起讨论各种形状之类的话题。实际上几天前，我去叫她起床，发现她整个人躲在被窝里。我问她：“Sophia，你躲在被子下面干嘛呢？”她说：“噢，我正在做数学呢。”

<details>
<summary>Original English</summary>

**Daniel**: Yeah, I definitely encourage that. We talk about shapes and stuff. Actually a couple days ago I woke her up and she was like hiding under the blankets, and I was like, "Oh, what are you up to under there, Sophia?" And she was, "Oh, I'm doing some math."

</details>

**提问者**：哈哈，我好像在推特上看到你发过这条，太逗了。

<details>
<summary>Original English</summary>

**Interviewer**: Oh, I did. I think you tweeted about that. That was horrible [funny].

</details>

**Daniel**：是的，特别好玩。所以你看，我觉得她能感觉到我很喜欢数学，也因此对数学产生了兴趣。

我想说的是，二十年之后，等她完全成年并开始独立做自己的事情时，这个世界很可能会变得非常不一样。但我认为，我们教育人类的大部分核心目标，面对世界的形式演变其实是非常稳健（robust）的。学习数学的初衷一直都是为了能够清晰地思考，并更好地理解这个世界。即使未来存在能力极其强大的 AI，这种理解世界、清晰思考的追求依然是人类想要去做的。

这同样适用于阅读大量书籍以及学习人文学科等领域。我认为数学专业以及更广泛的教育所蕴含的真正价值观，绝对是我们想要去守护和传承的东西，我也希望能把这些品质传递给我的女儿。至于现有的教育机构需要做出多大程度的变革来确保这一目标的实现，可能是一个很值得深入探讨的开放性问题。但至少在个人层面上，我确实在努力让我三岁的女儿相信：数学是一件超级酷的事情。

<details>
<summary>Original English</summary>

**Daniel**: Yeah, it was great. So, you know, I think she has some sense that I like math and she's into it because of that. Um, yeah. I mean, I would say I think the world is probably going to look pretty different in, you know, 20 years or whenever she's fully adult and doing her own thing. But you know, I think a lot of what we educate people for is pretty robust to changes in the nature of the world. The reason to learn math has always been to think clearly and better understand the world, and presumably that's something you want to do even if there are extremely capable AIs. And this is also true, you know—I personally like math a lot, but also the reason to read a lot of books and do the humanities and so on. So I think the actual values of the math profession and education more broadly are things we definitely want to try to preserve, that I hope to instill in my daughter. You know, how much institutions have to change to make sure that happens is maybe an open question I think a lot about. But yeah, at least at a personal level, I'm definitely trying to convince my three-year-old that math is super cool.

</details>

### 从二十面体到群论：培养下一代的数学审美

**提问者**：百分之百赞同。

<details>
<summary>Original English</summary>

**Interviewer**: Oh yeah, 100%.

</details>

**Daniel**：她最早学会说的几个词之一就是“正二十面体”（icosahedron）。

<details>
<summary>Original English</summary>

**Daniel**: One of her first words was icosahedron.

</details>

**提问者**：是什么词？

<details>
<summary>Original English</summary>

**Interviewer**: Was what?

</details>

**Daniel**：在我父母家，她一岁的时候我父母送了她一个正二十面体的小玩具。倒也不完全是严格意义上的第一个词，但她确实很早就认识了柏拉图多面体（Platonic solids）。

<details>
<summary>Original English</summary>

**Daniel**: My parents gave her a little icosahedron toy when she was one. Not literally a first word, but she learned the Platonic solids quite early.

</details>

**提问者**：哇，太厉害了，非常有趣！

<details>
<summary>Original English</summary>

**Interviewer**: Oh, very good. Very fun.

</details>

**提问者**：接下来该学群论（Group Theory）了。这其实是非常自然的发展路径。

<details>
<summary>Original English</summary>

**Interviewer**: Next up, group theory. I mean, it's like very natural. That's right.

</details>

**Daniel**：确实如此！其实等我进一步教她加法和减法的时候，我们就会把它们放在一般群（general group）的背景下去讲。

<details>
<summary>Original English</summary>

**Daniel**: Yeah. I'm actually, when I teach her about addition and subtraction further, we'll do it in the context of a general group.

</details>

**提问者**：太棒了！至少你给出了底层的动机和数学结构，很多人在教学中往往会跳过这一部分。是的，也许这就是数学专业的研究生们也可以关注的方向——训练更年轻的一代学会使用 AI 来真正提升自己的数学素养，而不是在缺乏深度理解的情况下盲目依赖工具。

太棒了。Daniel，非常感谢你能来参加我们的节目！

<details>
<summary>Original English</summary>

**Interviewer**: Oh, very good. Well, at least you give the motivation. I think a lot of people probably skip that part. Yeah. And you know, maybe this is how math grad students can also focus, like training the next, much younger generation to use AI in service of actually getting better at math, rather than just lacking understanding. Wonderful. Okay. Well, thank you so much, Daniel.

</details>

**Daniel**：谢谢你，聊得非常开心。

<details>
<summary>Original English</summary>

**Daniel**: Thank you. It was a lot of fun.

</details>

**提问者**：是的，非常愉快。我认为很快就会看到更多的突破与进展，非常期待以后有机会能再和你聚在一起深入探讨。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Yeah, it was a lot of fun. And yeah, I mean, I think there's going to be a lot more progress very soon. I'd love to maybe catch up and chat again.

</details>

**Daniel**：太好了，期待下次再聊！

<details>
<summary>Original English</summary>

**Daniel**: Sounds great.

</details>