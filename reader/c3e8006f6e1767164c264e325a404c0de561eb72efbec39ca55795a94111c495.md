---
author: EO
date: '2026-07-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MG0CPqjjOvk
speaker: EO
tags:
  - formalization
  - mathematical-logic
  - human-judgment
  - artificial-intelligence
title: AI 时代的数学与人生：从指标化危机到真理形式化
summary: 著名数学家 Ken Ono 结合自身因五年级数学竞赛失利而误解父亲的成长经历，深刻批判了当今社会对 Benchmark 的过度迷信。他分析了 AI 给数学界带来的身份危机，阐明了科研的本质是探索未知而非套用技术，并指出“形式化”（Formalization）才是 AI 时代追求真理与建立安全防线的关键所在，呼吁人们在算法丛林中守护人类直觉与个人热忱。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Axiom Math
  - Epoch AI
  - OpenAI
products_models:
  - ChatGPT
media_books: []
status: evergreen
---
### 摆脱外部指标：重构人生的真正尺度

在当今这个高度数字化的时代，社会倾向于使用各种**外部指标**（Benchmarks: 用于评估性能或水平的标准参照物）来衡量个人的价值，从学校排名、智商分数到各种标准化的考试成绩。这种将人“指标化”的倾向不仅存在于学术界和工业界，也深深地根植于个人的成长和心理预期中。数学家 **Ken Ono** 讲述了他自己的一段经历：他在五年级时参加了一次学校的数学竞赛，最终获得了第三名。虽然对于一个五年级的孩子来说，第三名已经是不错的成绩，但由于他的父亲是一位声名显赫的著名数学家，年幼的 Ken Ono 看着驱车前来观看比赛的父母，在回程的寂静中感受到了无形的压力。在之后的五十年里，他一直深信自己彻底地失败了，让父母大失所望。直到他父亲在今年一月去世，兄弟姐妹们在清理遗物时，竟然在佛罗里达公寓的一个普通衣柜里，发现了那块珍藏了半个世纪的五年级数学竞赛第三名奖牌。这一刻，他意识到自己误解了父亲整整一生——父亲保留这块奖牌，并不是因为他没有夺冠，而是因为看到了儿子想要做好的决心。

这个故事说明，当我们试图去迎合他人设定的标准时，我们往往忽略了自身的真实成长。这种必须符合某种预设标准的社会压力是极具毒性的。在现实中，除非你是**勒布朗·詹姆斯**（LeBron James）、**拉斐尔·纳达尔**（Rafael Nadal）或是诺贝尔奖得主，否则你总能找到在某些方面比你更优秀、达成了你无法企及之成就的人。如果因此而不断地自我怀疑，你就没有给予自己许可去过真正属于你的人生。研究表明，在人们临终前的诸多遗憾中，排名第一的往往是“没有机会去过真正属于自己、而非迎合他人期望的生活”。因此，我们必须打破这种盲目对比的恶性循环，重构衡量人生的真正尺度。

<details>
<summary>Original English Source</summary>
Hi, my name is Ken Ono. I'm a mathematician. I work at Axiom Math and the University of Virginia, but in my life, I was not a good student in college. In fifth grade, we had a a math contest and I got third. Now, third is pretty good out of a fifth grade, but my father was a famous mathematician. They came to the competition and son of famous mathematician gets third in Hampton Elementary School. I thought for 50 years of my life that I had utterly failed. But the reason I bring this up is that when my dad passed away in January, we were cleaning up his belongings and of all the things that he could have kept and it was just in a closet now was that plaque from my fifth grade contest. And I thought, "Wow, I had misinterpreted that event my whole life." It actually meant something to him to keep a plaque where I didn't win, but I got third place. What he saw, I'm sure, was that I wanted to do well. What worries me about what you just said is this need to compare your personal situation now with others. That sounds horrible. If you have to live up to the standards set by someone else, then you're not living for yourself. You're not giving yourself credit. Whatever pressures someone may feel that inspires them to constantly be comparing themselves to others, I consider that toxic. Because you know what the brutal truth is? The brutal truth is if you're not LeBron James or Raphael Nadal or a Nobel Prizewinning scientist, the reality is you will always be able to find someone that looks better, achieve something that you cannot do, and you're not then giving yourself permission to live the life that was meant for you. It's important to give yourself permission to live your life. And this might be morbid, but one day you will be on your deathbed. You may only have a few days left. And someone might ask you some questions. What are your five deepest regrets? And this comes up all the time. I'm not making this up. I think the number one regret is I wish I had the chance to live the life that was meant for me.
</details>

---

### 智能的试金石：大模型与数学家的身份危机

当我们将目光从个人心理转向技术前沿时，会发现人工智能（AI）领域同样在上演着一场关于“基准测试”的狂热竞赛。各大人工智能公司不断推出更加先进的**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统），并在各种标准化的测试集上竞争极高的分数。然而，这种竞争正在对数学家和科学家的传统身份认同产生前所未有的冲击。大约一年前，Ken Ono 受雇于 **Epoch AI** 公司，任务是编写极其困难的数学问题，用以评估最顶尖大语言模型的推理能力。原本他以为这是一份轻松赚取外快的差事，但在实际编写过程中，他惊讶地发现，虽然模型有时会犯错，但它们展现出的推理链条（Reasoning Traces）之深、跨度之广，已经达到了令人惊叹的水平。这直接导致了数学家们的“身份危机”，这种危机感类似于19世纪末传统的佃农第一次面对内燃机拖拉机时的无助——他们意识到自己赖以生存的手艺可能即将失去独特的价值。

这种身份危机的底层逻辑在于，过去的历次技术革命（如电梯、拖拉机）主要是在减轻人类的体力劳动，而这一次 AI 触及的却是人类的核心心智技能。随着 AI 公司开始引入**自对弈**（Self-play: 强化学习中系统与自身进行对抗或协作以提升能力的训练机制）等技术，AI 系统的自主计算与学习能力将呈现指数级增长。这让当前许多数学系以及计算机系的学生和年轻学者感到深切的焦虑：他们花费数年时间苦读并积累的专业知识和技能，在能够熟练操作大语言模型的人面前，似乎变得不再具有壁垒。这种 disruption（颠覆）是真实且不可回避的，迫使我们必须重新思考人类智力的真正定义。

<details>
<summary>Original English Source</summary>
We live at a time where the world places so much emphasis on benchmarks. how these AI firms and the state-of-the-art large language models are competing for these crazy scores. There's a lot of anxiety over benchmarks. Almost exactly one year ago, I was part of a group of mathematicians hired by a company called Epoch AI to write very difficult math problems that would serve as a benchmark for state-of-the-art large language models. And I thought it would be easy money. We were paid. But last year I found it very difficult to write some of these problems. Strictly speaking the models would make mistakes but when you studied the reasoning traces it was frightening how far these large language models have come. So I think the right way to describe it is well as an identity crisis. Maybe it was something like being the sharecropper, the farmer in the late 19th century who comes face to face with the first combustion engine tractor, recognizing that well maybe there's no future for my work as a sharecropper. What to do next? What's next for a mathematician? It was pretty devastating honestly seeing these models solve problems that were on my research program. The difference now is the work is mental. That is the stuff of identities. And where are we now? We are now at a point where many of those skills can be done automatically. And AI companies are talking about what's called selfplay. They want their AI systems to play with themselves. And so where does that leave us? Well, mathematics, it's it is devastating. It would be dishonest to say that a student who's graduating from college now with a bachelor's degree in mathematics or who is in graduate school now isn't deeply worried about all the years of effort they put into learning a trade, learning a body of knowledge that now anybody who can type if they have access to a large language model. So there's no dancing around that fact. This is very disruptive.
</details>

---

### 重新定义探索：从技术熟练度到提出好问题

面对这一看似“毁灭性”的危机，数学家们开始重新审视自己工作的本质。Ken Ono 坦言，如果数学家的成功仅仅依赖于记忆和堆砌已有的定理与技术去证明新定理，那么这项工作确实是可自动化的。但真正的科学研究并非如此。研究的起点往往是一个你根本无法回答的问题；在尝试回答并不断经历失败的过程中，你得以逐步理清问题的脉络，进而产生一系列新的问题，并最终可能证明某个定理。这种“两步向前、一步向后”的探索过程是无法被简单自动化的。AI 带来的变革，实质上是降低了人类进行科学探索的门槛。

这就如同现代人驾驶汽车一样：我们不需要掌握复杂的化学反应原理和精密的机械工程设计，只需学会加油或充电，就能极大地扩展我们的空间活动能力。同样的道理，大语言模型就像是一个无所不知的“超级图书管理员”，能够将人类积累的全部知识在瞬间联系起来，从而释放了科学家的精力。在 AI 的辅助下，数学家不再需要花几个月甚至几年时间去手动计算2000万个案例，而是可以在睡觉时让系统代劳，从而专注于更具创造性的逻辑建构。因此，衡量一个学者的标准，将从“掌握了多少已有的解题技术”转变为“是否能提出真正符合人类本能的、具有启发性的好问题”。如果我们能灵活地将 AI 视作协作者（Co-pilot），我们便能在这场技术浪潮中重塑人类在发现过程中的独特价值。

<details>
<summary>Original English Source</summary>
When I was a graduate student and a young assistant professor, I would have said that I was most proud of my works that depended on the accumulation of knowledge involving years of effort... My view has changed on that... There's actually something quite hollow about how I viewed myself as a mathematician that I only recognized recently. If my success as a mathematician relied only on my ability to learn techniques that somehow could be put together to prove a theorem, well then maybe that was actually automatable. Now, make no mistake, that's not what we do for a living in mathematics and in most fields. Research begins with a question that you're probably not able to answer. You try to answer and by failing you learn a little bit more about that conjecture and the work that you do sheds light on a path that might reveal a long list of questions... this is how you learn it's it's really the proverbial two steps forward one back and when you recognize that research is not ask a question, you get an answer. You realize that the AI tools are lowering the burden for your ability to actually perform discovery. Typical person that drove a car today doesn't have the foggiest idea of chemical reactions and engineering advances that had to come to fruition before they could actually get in the car and drive... Is that bad? No. Because think about all the things that mankind can do now because they can travel great distances very quickly. What that opens us up to. And I think that's going to be our future... So what makes a good question? ... If you genuinely want to know the answer to a question, then that's a great question. You should never ever doubt your interest in a subject.
</details>

---

### 迈向真理之争：以形式化构建 AI 时代的安全防护

在厘清了人机协作的宏观逻辑后，我们需要进一步探究 AI 在科学研究中的具体应用路径。Ken Ono 指出，人工智能在科学界的应用主要可以划分为三种形态：
* 第一种是公众最为熟悉的**生成式对话助手**（如 ChatGPT 等问答机器人）；
* 第二种是基于海量数据的**超凡搜索与模式匹配**，例如约翰·尊佩（John Jumper）与德米斯·哈萨比斯（Demis Hassabis）凭借解决蛋白质折叠的 AlphaFold 系统荣获诺贝尔化学奖；
* 第三种则是被寄予厚望的**形式化**（Formalization: 将人类自然语言或逻辑转化为精确的计算机可读代码的过程，也称作可验证代码验证）。

在当今这个充斥着“直觉代码”（Vibe Coding: 指完全依赖 AI 生成、未经严格形式化验证的计算机代码）的世界里，代码的漏洞和不确定性大幅增加。形式化技术的引入，就是为了解决这些隐藏的不确定性。例如，Ken Ono 的团队目前正与哈佛大学杰出的数学经济学家斯科特·科米纳斯（Scott Kominers）合作，致力于将经济学中的经典理论进行数学形式化。在这一过程中，他们惊奇地发现，一些此前被奉为经典的基石性定理在具体的边界条件和逻辑推导上存在着疏漏。以诺贝尔奖得主罗伯特·奥曼（Robert Aumann）于1976年提出的著名定理“我们无法同意分歧”（We Agree to Disagree）为例，对其进行形式化验证的过程在经济学界引发了极大的轰动，许多学者纷纷加入这一行列。因此，在 2026 年及以后的 AI 竞争中，人类的核心关切不应仅仅是堆砌更多的计算资源（Compute），而应该是借助形式化工具去追求更多的“绝对真理”。通过这种数学语言的严密转化，我们不仅能够让 AI 辅助证明悬而未决的数学猜想，更能为复杂的金融系统、网络安全和人机伦理制定出牢固的守卫性防线（Guardrails）。

<details>
<summary>Original English Source</summary>
The easiest way to make a mistake in the era of AI is to confuse what people are saying when they're talking about AI. It's important to first understand that AI comes in many different forms. The forms of AI that most people encounter these days would be the chat GPT... AI's ability to use machine learning techniques to conduct a superhuman search... This is how John Jumper and Dennis Hassus won the Nobel Prize in chemistry for solving protein folding. And the third part of AI is where I think there is so much hope. The third part of AI is called formalization. And the idea in formalization is to take human natural language, transform it into computer code, which is an enhanced or at least an exact interpretation of the human language and then have AI study this code and look for vulnerabilities. It's called verifiable computer code. We live at a time now where an enormous proportion of the computer code that's written and deployed in the world is not the stuff of human programmers. It's called vibe coding. But make no mistake, that code is not perfect. And so the space that we're in now in terms of formalization is to cut back on those inefficiencies. Our company is partnering with Scott Commoners. He's a very distinguished economist at Harvard, a mathematical economist. And in our work, we are formalizing... mathematical theories in economics. 2026 is the 50th anniversary of a very famous theorem by the Nobel laurate Robert Alman... can we agree to disagree... So this is our future. So I said, what are the opportunities for AI? One is how do we use AI to best guardrail the other forms of AI? Cyber security will need legions of computer scientists, also ethicists, make no mistake, and lawyers... this is 2026, 2027, I don't believe now, is the race for more compute. It really should be the race for more truth. And I think that, and I hope I'm right, will be by means of formalization. When a scientist says that a fact is formally verified, this statement is true. End of story.
</details>

---

### 守护人类直觉：在算法丛林中寻找个人热忱

尽管形式化验证能够提供绝对的“是/否”逻辑真理，但在高风险的现实场景中，如何运用这些事实依然需要依赖人类独特的**情感智能**（Emotional Intelligence: 识别、理解和管理自己及他人情绪的能力）与道德评判。例如，在军事冲突中，自主无人机或许能够通过算法识别出特定的地面目标，但决定是否扣动扳机、如何权衡附带伤亡、如何区分平民医院与军事据点，这些高风险决策背后所包含的人类同理心和伦理判断，是任何冰冷的算法都无法取代的。令人担忧的是，现代社会正在滥用这种算法的便利，在招聘、教育等领域实施冰冷的“打分制”与“复选框”过滤，这抹杀了人类个性的复杂度和生命的无限可能。

为了打破这种算法驱动的平庸陷阱，我们必须捍卫人类的直觉和独特的热忱。Ken Ono 举了他的一位博士生罗伯特·施奈德（Robert Schneider）的例子。罗伯特曾是著名独立摇滚乐队 Apples in Stereo 的主唱，也是 Neutral Milk Hotel 乐队的制作人。在巡演过程中，由于老旧的模拟音响设备经常损坏，为了省下高昂的修理费，这位大学肄业生买了一本电子学书籍，并被书中的“欧姆定律”深深震撼。这种对科学规律纯粹的创造性直觉，促使他决定重返校园，攻读数学并最终在 Ken Ono 的指导下取得了数学博士学位。罗伯特的传奇经历和 Ken Ono 自身作为少数族裔在巴尔的摩克服歧视、从“四眼仔”的偏见中汲取力量的成长轨迹共同证明了：
* 成功的道路从来不是按照既定配方（Grades, Schools, Standard Careers）去盲目勾选复选框；
* 人生的力量源于对自己独特 passion（热忱）的坚持，哪怕这一热忱在当时并不流行；
* 面对由 AI 和算法交织而成的未来，保持灵活（Flexible）的姿态，去主动拥抱和追逐那些命中注定的机遇，才是人类在算法丛林中安身立命的根本。

<details>
<summary>Original English Source</summary>
A large language model is something like the most incredible librarian. A librarian who's read everything. But that doesn't mean you want your librarian to be your neurosurgeon. In very high stakes situations, you need taste. You need human judgment. And of course, on top of that, you need someone with the emotional intelligence to understand how decisions impact people... I think in most cases that we care about the most that are high stakes when you want a person involved. Everywhere you look, we have adopted a system where we are replaced by numbers. we are replaced by what an algorithm seeks... And I'm sorry if you want to find the cure for cancer, it's not going to be a bunch of check boxes. If it was, we would have already found the cure for cancer. I had a graduate student, his name was Robert Schneider. He was actually and still is a famous independent rock artist. He was producer for a band called Neutral Milk Hotel and lead singer for a band called Apples and Stereo... decided that he was going to start learning electronics... got his math degree, and found his way into my office. And when he said when I saw Ohm's law, it made me stop and think about what is it that I am producing when I'm writing and singing music. Electrical circuits populate my brain. That's a creative part. ... I've had 35 PhD students. But if if we were to go through them one by one, I could tell you a story. ... We have no shortage of students who mistakenly think that the path to success is you go to the right schools, you get the right grades... That's a mindless way of going about one's life. It's not actually giving yourself permission to live the life that was meant for you. I'm a Japanese kid that grew up in a very white suburb of Baltimore, Maryland at a time when it wasn't good to be Japanese. I wore glasses. I was Mr. Four Eyes. But that gave me strength. ... The moral of this conversation is there's very little you can do about the world that's around you. So, how can you choose a life that's meant for you? Be flexible and embrace and chase opportunities that were that seem to be destined for you.
</details>