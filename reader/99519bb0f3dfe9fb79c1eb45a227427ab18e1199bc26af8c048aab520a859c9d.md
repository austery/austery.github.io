---
author: Dwarkesh Patel
date: '2026-03-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Q8Fkpi18QXU
speaker: Dwarkesh Patel
tags:
  - ai-impact
  - mathematical-research
  - scientific-discovery
  - data-driven-science
  - human-ai-collaboration
title: 陶哲轩谈AI如何改变数学研究与科学范式
summary: 世界顶级数学家陶哲轩在访谈中探讨了人工智能对数学研究和科学发现的深远影响。他以开普勒行星运动定律的发现为例，类比AI在科学探索中通过海量数据驱动的试错过程。访谈深入讨论了AI在概念生成、辅助证明、加速科研流程等方面的潜力与挑战，并思考了科学验证、同行评审、以及人类与AI协作在未来数学和科学发展中的作用，强调了适应性思维的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Terence Tao
  - Johannes Kepler
  - Isaac Newton
  - Tycho Brahe
  - Nicolaus Copernicus
  - Aristarchus of Samos
  - Johann Bode
  - William Herschel
  - Albert Einstein
  - Charles Darwin
  - Thomas Huxley
  - Lucretius
  - Shawn
  - Carl Friedrich Gauss
companies_orgs:
  - OpenAI
  - Jane Street
  - Bell Labs
  - Institute for Advanced Study
  - Mercury
  - Choice Financial Group
  - Column NA
products_models:
  - GPT-4o
  - ResNet
  - Mathematica
  - Wolfram Alpha
  - Lean
  - Google Web Search
  - Labelbox
media_books:
  - The Harmonics of the World
  - The Clockwork Universe
  - The Origin of Species
  - Principia Mathematica
status: evergreen
---
### 开普勒与AI时代的科学发现

**Dwarkesh**: 今天，我与**陶哲轩**（Terence Tao）聊天，他无需介绍。特伦斯，我想先请你重新讲述一下**开普勒**（Kepler）是如何发现行星运动定律的故事，因为我认为这将是讨论数学AI的一个很好的切入点。

<details>
<summary>Original English</summary>

**Dwarkesh**: Today, I'm chatting with Terence Tao, who needs no introduction. Terence, I want to begin by having you retell the story of how Kepler discovered the laws of planetary motion because I think this will be a great jumping off point to talk about AI for math.

</details>

**Terence Tao**: 我一直对天文学有业余爱好。我喜欢早期天文学家如何揭示宇宙本质的故事。开普勒是在**哥白尼**（Copernicus）工作的基础上进行研究的，而哥白尼自己又是在**阿里斯塔克斯**（Aristarchus）工作的基础上进行的。哥白尼非常著名地提出了**日心说模型**（heliocentric model），即行星和太阳并非围绕地球运行，而是太阳位于太阳系的中心，其他行星围绕太阳运行。哥白尼认为行星的轨道是完美的圆形。他的理论与希腊人、阿拉伯人和印度人几个世纪以来的观测结果相符。开普勒在研究中学习了这些理论，他发现哥白尼预测的轨道大小比例似乎具有某种几何意义。他开始提出，如果你将地球轨道包在一个**立方体**（cube）中，包围立方体的外层**球体**（sphere）几乎完美地匹配了**火星**（Mars）的轨道，依此类推。当时已知有六颗行星，它们之间有五个空隙，而正有五种完美的**柏拉图立体**（Platonic solids）：立方体、**正四面体**（tetrahedron）、**正二十面体**（icosahedron）、**正八面体**（octahedron）和**正十二面体**（dodecahedron）。

<details>
<summary>Original English</summary>

**Terence Tao**: I've always had an amateur interest in astronomy. I've loved stories of how the early astronomers worked out the nature of the universe. Kepler was building on the work of Copernicus, who was himself building on the work of Aristarchus. Copernicus very famously proposed the heliocentric model, that instead of the planets and the Sun going around the Earth, the Sun was at the center of the solar system and the other planets were going around the Sun. Copernicus proposed that the orbits of the planets were perfect circles. His theory fit the observations that the Greeks, the Arabs, and the Indians had worked out over centuries. Kepler learned about these theories in his studies, and he made this observation that the ratios of the size of the orbits that Copernicus predicted seemed to have some geometric meaning. He started proposing that if you take the orbit of the Earth and you enclose it in a cube, the outer sphere that encloses the cube almost perfectly matched the orbit of Mars, and so forth. There were six planets known at the time and five gaps between them, and there were five perfect Platonic solids: the cube, the tetrahedron, icosahedron, octahedron, and dodecahedron.

</details>

**Terence Tao**: 所以他有这个理论，他认为这个理论绝对优美，你可以把这些柏拉图立体嵌入到行星的球体之间。它似乎很吻合，在他看来，上帝对行星的设计与柏拉图立体的这种数学完美性相符。他需要数据来证实这个理论。当时，世界上只有一份真正高质量的数据集。**第谷·布拉赫**（Tycho Brahe），这位非常富有、古怪的丹麦天文学家，设法说服丹麦政府资助建造这个极其昂贵的观测站。事实上，那是一个岛屿，他在那里用了几十年的时间，用肉眼观测了所有的行星，比如火星和**木星**（Jupiter），至少在天气晴朗的每个晚上都进行观测。他是最后一位肉眼天文学家。他拥有所有这些数据，开普勒可以用它们来证实他的理论。

<details>
<summary>Original English</summary>

**Terence Tao**: So he had this theory, which he thought was absolutely beautiful, that you could inscribe these Platonic solids between the spheres of the planets. It seemed to fit, and it seemed to him that God's design of the planets was matching this mathematical perfection of the Platonic solids. He needed data to confirm this theory. At the time, there was only one really high-quality dataset in existence. Tycho Brahe, this very wealthy, eccentric Danish astronomer, had managed to convince the Danish government to fund this extremely expensive observatory. In fact, it was an entire island where he had taken decades of observations of all the planets, like Mars and Jupiter, at least every night for which the weather was clear, with the naked eye. He was the last of the naked-eye astronomers. He had all this data which Kepler could use to confirm his theory.

</details>

**Terence Tao**: 开普勒开始与第谷合作，但第谷对数据非常嫉妒。他一次只给他一点点数据。开普勒最终只是窃取了数据。他复制了数据，并不得不与布拉赫的后代打了一架。他确实得到了数据，然后他失望地发现，他那优美的理论并不完全奏效。数据与他的柏拉图立体理论有大约10%的偏差。他尝试了各种修正，移动圆形轨道，但都不是很奏效。但他在这个问题上努力了多年，最终，他想出了如何利用数据来推导出行星的实际轨道。那是一项极其巧妙、天才的数据分析。然后他发现，轨道实际上是**椭圆形**（ellipses），而不是圆形，这对他来说是令人震惊的。

<details>
<summary>Original English</summary>

**Terence Tao**: Kepler started working with Tycho, but Tycho was very jealous of the data. He only gave him little bits of it at a time. Kepler eventually just stole the data. He copied it and had to have a fight with Brahe's descendants. He did get the data, and then he worked out, to his disappointment, that his beautiful theory didn't quite work. The data was off from his Platonic solid theory by 10% or something. He tried all kinds of fudges, moving the circles around, and it didn't quite work. But he worked on this problem for years and years, and eventually, he figured out how to use the data to work out the actual orbits of the planets. That was an incredibly clever, genius amount of data analysis. And then he worked out that the orbits were actually ellipses, not circles, which was shocking for him.

</details>

**Terence Tao**: 所以他推导出了**行星运动的两大定律**（two laws of planetary motion）：椭圆轨道，以及等面积定律（equal areas sweep out equal times）。十年后，在收集了大量数据之后——像**土星**（Saturn）和木星这样的遥远行星对他来说最难研究——他最终推导出了**第三定律**（third law），即行星完成轨道所需的时间与其到太阳距离的某个幂成正比。这些就是著名的**开普勒三大行星运动定律**（Kepler's laws of motion）。他无法解释它们。这一切都由实验驱动，直到一个世纪后**牛顿**（Newton）才提出了一个理论，同时解释了这三大定律。我想对你提出的观点是，开普勒是一个**高温大型语言模型**（high-temperature LLM）。牛顿提出了为什么行星运动三大定律必然成立的解释。

<details>
<summary>Original English</summary>

**Terence Tao**: So he worked out the two laws of planetary motion: the ellipses, and also that equal areas sweep out equal times. Then ten years later, after collecting a lot of data—the furthest planets like Saturn and Jupiter were the hardest for him to work out—he finally worked out this third law, that the time it takes for a planet to complete its orbit was proportional to some power of the distance to the Sun. These are the three famous Kepler's laws of motion. He had no explanation for them. It was all driven by experiment, and it took Newton a century later to give a theory that explained all three laws at once. The take I want to try on you is that Kepler was a high-temperature LLM. Newton comes up with this explanation of why the three laws of planetary motion must be true.

</details>

**Dwarkesh**: 当然，开普勒发现行星运动定律，或者说弄清不同行星相对轨道的方式，正如你所说，是一项天才之作。但纵观他的职业生涯，他只是在尝试各种随机关系。事实上，在他写下行星运动第三定律的书中，这只是《**世界的和谐**》（The Harmonics of the World）中的一个旁白，这本书只是关于这些不同行星如何具有不同和谐的。地球上之所以有如此多的饥荒和苦难，是因为地球是“mi-fa-mi”，那是地球的音符。这一切都是随机的占星术，但其中包含了**立方平方定律**（cube-square law），它告诉了周期与行星到太阳距离的关系。正如你所详述的，如果你将它与牛顿的**F=ma**和**向心加速度**（centripetal acceleration）方程结合起来，你就会得到**平方反比定律**（inverse-square law）。所以牛顿解决了这个问题。

<details>
<summary>Original English</summary>

**Dwarkesh**: Of course, the way that Kepler discovers the laws of planetary motion, or figures out the relative orbits of the different planets, is as you say a work of genius. But through his career, he's just trying random relationships. In fact, in the book in which he writes down the third law of planetary motion, it's an aside on The Harmonics of the World, which is just a book about how all these different planets have these different harmonies. And the reason there's so much famine and misery on Earth is because the Earth is mi-fa-mi, that's the note of Earth. It's all this random astrology, but in there is the cube-square law, which tells you what relationship the period has to a planet's distance from the Sun. As you were detailing, if you add that to Newton's F=ma and the equation for centripetal acceleration, you get the inverse-square law. And so Newton works that out.

</details>

**Dwarkesh**: 但我认为这个故事很有趣的原因是，我觉得**大型语言模型**（LLM）可以做那种尝试随机关系20年的事情，其中一些毫无意义，只要有一个像布拉赫数据集那样可验证的数据银行。“好吧，我要尝试关于音符、柏拉图物体或不同几何形状的随机事物，我有一种偏见，认为这些轨道的几何形状有一些重要的东西。”然后其中一个奏效了。只要你能验证它，这些**经验规律**（empirical regularities）就能推动实际的深度科学进步。传统上，当我们谈论科学史时，**思想生成**（idea generation）一直是科学中享有声望的部分。一个科学问题包含许多步骤。你必须识别一个问题，然后你必须识别一个好的、富有成效的问题来研究。然后你需要收集数据，找出分析数据的策略，并提出假设。

<details>
<summary>Original English</summary>

**Dwarkesh**: But the reason I think this is an interesting story is that I feel LLMs can do the kind of thing of trying random relationships for twenty years, some of which make no sense, as long as there's a verifiable data bank like Brahe's dataset. "Ok, I'm going to try out random things about musical notes, Platonic objects, or different geometries, I have this bias that there's some important thing about the geometry of these orbits." Then one thing works. As long as you can verify it, these empirical regularities can then drive actual deep scientific progress. Traditionally, when we talk about the history of science, idea generation has always been the prestige part of science. A scientific problem comes with many steps. You have to identify a problem, and then you have to identify a good, fruitful problem to work on. Then you need to collect data, figure out a strategy to analyze the data, and make a hypothesis.

</details>

**Dwarkesh**: 此时，你需要提出一个好的假设，然后你需要验证。然后你需要撰写并解释。有十几个不同的组成部分。我们所颂扬的是那些顿悟的**天才时刻**（eureka genius moments）——思想的产生。开普勒当然不得不循环尝试许多想法，其中几个没有奏效。我敢打赌，有许多他甚至根本没有发表，因为它们不符合。那是过程的重要组成部分，尝试各种随机事物，看看它们是否有效。但正如你所说，它必须与等量的**验证**（verification）相匹配，否则就是敷衍。我们赞美开普勒，但我们也应该赞美布拉赫勤奋的数据收集，其精确度比以前任何观测都高十倍。额外的**小数精度**（decimal point of accuracy）对于开普勒获得他的结果至关重要。当时他正在使用**欧几里得几何**（Euclidean geometry）和最先进的数学来将他的模型与数据匹配。

<details>
<summary>Original English</summary>

**Dwarkesh**: At this point, you need to propose a good hypothesis, and then you need to validate. Then you need to write things up and explain. There are a dozen different components. The ones we celebrate are these eureka genius moments of idea generation. Kepler certainly had to cycle through many ideas, several of which didn't work. I bet there were many that he didn't even publish at all because they just didn't fit. That's an important part of the process, trying all kinds of random things and seeing if they worked. But as you say, it has to be matched by an equal amount of verification, otherwise it's slop. We celebrate Kepler, but we should also celebrate Brahe for his assiduous data collection, which was ten times more precise than any previous observation. That extra decimal point of accuracy was essential for Kepler to get his results. He was using Euclidean geometry and the most advanced mathematics he could use at the time to match his models with the data.

</details>

**Terence Tao**: 所有方面都必须发挥作用：数据、理论和假设生成。我不确定现在假设生成是否仍然是瓶颈。自那时起一个世纪以来，科学已经发生了变化。传统上，科学的两大范式是**理论**（theory）和**实验**（experiment）。然后，在20世纪，**数值模拟**（numerical simulation）出现了，所以你可以进行计算机模拟来测试理论。最后，在20世纪末，我们有了**大数据**（big data）。我们进入了**数据分析**（data analysis）的时代。现在，许多新进展实际上是由首先分析**海量数据集**（massive datasets）驱动的。你收集大型数据集，然后从中提取模式以推导思想。

<details>
<summary>Original English</summary>

**Terence Tao**: All aspects had to be in play: the data, the theory, and the hypothesis generation. I'm not sure nowadays that hypothesis generation is the bottleneck anymore. Science has changed in the century since. Classically, the two big paradigms for science were theory and experiment. Then in the 20th century, numerical simulation came along, so you can do computer simulations to test theories. Finally, in the late 20th century, we had big data. We had the era of data analysis. A lot of new progress is actually driven now by analyzing massive datasets first. You collect large datasets and then draw patterns from them to deduce thoughts.

</details>

**Terence Tao**: 这与科学过去的工作方式有点不同，过去你做一些观察或有一个突如其来的想法，然后收集数据来测试你的想法。那是经典的**科学方法**（scientific method）。现在它几乎颠倒了。你先收集大数据，然后尝试从中获得假设。开普勒也许是第一批早期**数据科学家**（data scientists）之一，但即使是他也没有从第谷的数据集开始分析。他首先有一些先入为主的理论。现在看来，我们取得进步的方式越来越少地依赖于此，仅仅因为数据变得如此庞大和有用。

<details>
<summary>Original English</summary>

**Terence Tao**: This is a little bit different from how science used to work, where you make a few observations or have one out-of-the-blue idea, and then collect data to test your idea. That's the classic scientific method. Now it's almost reversed. You collect big data first, and then you try to get hypotheses from it. Kepler was maybe one of the first early data scientists, but even he didn't start with Tycho's dataset and then analyze it. He had some preconceived theories first. It seems like this is less and less the way we make progress, just because the data is so much more massive and useful.

</details>

**Dwarkesh**: 哦，有意思。我觉得你所描述的20世纪科学实际上很好地描述了开普勒身上发生的事情。他确实有过这些想法——1595年和1596年是他提出**多边形**（polygons）和柏拉图物体理论的时候——但它们是错误的。几年后，他得到了布拉赫的数据，直到经过二十年的随机尝试，他才得到了这种经验规律。这实际上感觉更接近于布拉赫的数据类似于一个**大型模拟数据库**（massive data bank of simulations），而现在你有了数据，你可以继续尝试随机事物。如果不是这样，开普勒就会在那里写关于和谐与柏拉图物体的书，而没有什么可以实际验证的了。

<details>
<summary>Original English</summary>

**Dwarkesh**: Oh, interesting. I feel like the 20th-century science that you're describing actually very well describes what happened with Kepler. He did have these ideas—1595 and '96 is where he comes up with the polygons and then the Platonic objects theory—but they were wrong. Then a few years later, he gets Brahe's data, and it's only after twenty years of trying random things that he gets this empirical regularity. It actually feels a bit closer to Brahe's data being analogous to some massive data bank of simulations, and now that you've got the data, you can keep trying random things. If it wasn't for that, Kepler would be out there just writing books about harmonics and Platonic objects, and there would be nothing to actually verify against.

</details>

**Terence Tao**: 数据极其重要。我试图区分的是，传统上，你提出一个假设，然后用数据来检验它。但现在有了**机器学习**（machine learning）、数据分析和**统计学**（statistics），你可以从数据开始，通过统计学推导出以前不存在的定律。开普勒的第三定律有点像这样，只不过布拉赫有数千个数据点，而开普勒只有六个数据点。对于每颗行星，他都知道轨道的长度和到太阳的距离。有五个或六个数据点，他做了我们现在称之为**回归分析**（regression）的工作。他将一条曲线拟合到这六个数据点上，得到了**平方立方定律**（square-cube law），这非常了不起。但他很幸运，这六个数据点给了他正确的结论。这不足以真正可靠。

<details>
<summary>Original English</summary>

**Terence Tao**: The data was extremely important. The distinction I was trying to make was that traditionally, you make a hypothesis and then you test it against data. But now with machine learning, data analysis, and statistics, you can start with data and through statistics work out laws that were not present before. Kepler's third law is a little bit like this, except that instead of having the thousand data points that Brahe had, Kepler had six data points. For every planet, he knew the length of the orbit and the distance to the Sun. There were five or six data points, and he did what we would now call regression. He fit a curve to these six data points and got a square-cube law, which was amazing. But he was quite lucky that these six data points gave him the right conclusion. That's not enough data to be really reliable.

</details>

**Terence Tao**: 后来有一位天文学家，**约翰·波德**（Johann Bode），他使用了相同的数据——到行星的距离——并受到开普勒的启发，他预测行星到太阳的距离形成了一个**偏移几何级数**（shifted geometric progression）。他也拟合了一条曲线，只是缺少了一个点。火星和木星之间有一个很大的空隙。他的定律预测有一个缺失的行星。这有点像一个**异想天开的理论**（crank theory），但当**赫歇尔**（Herschel）发现了**天王星**（Uranus）时，到天王星的距离正好符合这个模式。然后**谷神星**（Ceres）在**小行星带**（asteroid belt）被发现，它也符合这个模式。人们非常兴奋，认为波德发现了这个惊人的新自然定律。但后来**海王星**（Neptune）被发现，它的位置完全不符。基本上这只是一个**数字巧合**（numerical fluke）。

<details>
<summary>Original English</summary>

**Terence Tao**: There was a later astronomer, Johann Bode, who took the same data—the distances to the planets—and inspired by Kepler, he had a prediction that the distances to the planets formed a shifted geometric progression. He also fit a curve, except there was one point missing. There was a big gap between Mars and Jupiter. His law predicted that there was a missing planet. It was kind of a crank theory, except when Uranus was discovered by Herschel, the distance to Uranus fit exactly this pattern. Then Ceres was discovered in the asteroid belt, and it also fit the pattern. People got really excited that Bode had discovered this amazing new law of nature. But then Neptune was discovered, and it was way off. Basically it was just a numerical fluke.

</details>

**Terence Tao**: 有六个数据点。也许开普勒没有像强调前两条定律那样强调他的第三定律的原因之一是，即使他没有现代统计学知识，他本能地知道有六个数据点，他对结论必须有所保留。

<details>
<summary>Original English</summary>

**Terence Tao**: There were six data points. Maybe one reason why Kepler didn't highlight his third law as much as the first two laws is that instinctively, even though he didn't have modern statistics, he kind of knew that with six data points, he had to be somewhat tentative with the conclusions.

</details>

**Dwarkesh**: 更明确地问一下这个类比：如果未来我们有越来越智能的AI，这个类比是否仍然成立？我们将拥有数百万个AI，它们可以出去寻找所有这些经验规律。听起来你认为科学的瓶颈不再是为每个给定领域找到更多类似于行星运动第三定律的东西，以便以后有人可以说：“哦，我们需要一种方法来解释这个。让我们算出数学。这就是引力的平方反比定律。”

<details>
<summary>Original English</summary>

**Dwarkesh**: To ask the question about the analogy more explicitly, does this analogy make sense if in the future we have smarter and smarter AIs? We'll have millions of them, and they can go out and hunt for all these empirical irregularities. It sounds like you don't think the bottleneck in science is finding more things that are the equivalent of the third law of planetary motion for each given field, so that later on somebody can say, "Oh, we need a way to explain this. Let's work out the math. Here's the inverse-square law of gravity."

</details>

**Terence Tao**: 我认为AI已经将**思想生成**（idea generation）的成本降至几乎为零，这与互联网将**通信成本**（cost of communication）降至几乎为零的方式非常相似。这很了不起，但它本身并不能创造**丰裕**（abundance）。现在瓶颈不同了。我们现在面临的情况是，人们突然可以为一个给定的科学问题生成数千种理论。现在我们必须验证它们，评估它们。这是我们必须改变科学结构才能解决的问题。传统上，我们建立**壁垒**（walls）。过去，在我们没有AI“**垃圾**”（slop）之前，业余科学家有他们自己的宇宙理论，其中许多价值很小。我们建立了**同行评审**（peer review）出版系统，以过滤并试图隔离高信噪比的想法进行测试。

<details>
<summary>Original English</summary>

**Terence Tao**: I think AI has driven the cost of idea generation down to almost zero, in a very similar way to how the internet drove the cost of communication down to almost zero. It’s an amazing thing, but it doesn't create abundance by itself. Now the bottleneck is different. We're now in a situation where suddenly people can generate thousands of theories for a given scientific problem. Now we have to verify them, evaluate them. This is something which we have to change our structures of science to actually sort this out. Traditionally, we build walls. In the past, before we had AI slop, we had amateur scientists have their own theories of the universe, many of which were of very little value. We built these peer review publication systems to filter out and try to isolate the high signal ideas to test.

</details>

**Terence Tao**: 但现在我们可以大规模生成这些可能的解释，其中一些是好的，很多是糟糕的，人类审稿人已经不堪重负。许多期刊报告说，AI生成的投稿正在淹没他们的投稿。很高兴我们现在可以用AI生成各种东西，但这意味​​着科学的其他方面必须跟上：验证、确认和评估哪些想法真正推动了学科发展，哪些是死胡同或误导。这不是我们知道如何大规模做的事情。对于每一篇论文，我们可以在几年内通过科学家之间的辩论达成共识。但是当我们每天生成一千篇这样的论文时，这就不奏效了。

<details>
<summary>Original English</summary>

**Terence Tao**: But now that we can generate these possible explanations at massive scale, and some of them are good and a lot are terrible, human reviewers are already being overwhelmed. Many journals are reporting that AI-generated submissions are just flooding their submissions. It's great that we can generate all kinds of things now with AI, but it means that the rest of the aspects of science have to catch up: verification, validation, and assessing what ideas actually move the subject forward and which ones are dead ends or red herrings. That's not something we know how to do at scale. For each individual paper, we can have a debate among scientists and get to a consensus in a few years. But when we're generating a thousand of these every day, this doesn't work.

</details>

### AI时代的科学评估与范式转变

**Terence Tao**: 这里有一个极其有趣的问题。如果你有数十亿的AI科学家，不仅要如何衡量哪些是真正的进步，还要如何……这实际上是人类科学必须面对并且某种程度上已经解决的问题，而我实际上不确定我们是如何解决的。比如说，在1940年代，如果你在**贝尔实验室**（Bell Labs），有这些新技术出现。**脉冲编码调制**（Pulse-code modulation），你如何传输信号？如何将信号数字化？如何通过模拟线路传输它们？所有这些关于工程约束和细节的论文，然后有一篇提出了**比特**（bit）概念的论文，它对许多不同领域都产生了影响。你需要一个系统来审视它，然后说：“好的，我们需要将它应用于**概率论**（probability），我们需要将它应用于**计算机科学**（computer science）等等。”

<details>
<summary>Original English</summary>

**Terence Tao**: There's this incredibly interesting question. If you have billions of AI scientists, not only how do you gauge which ones are real progress, but how do you... This is actually a question that human science has had to face and we've solved somehow, and I’m actually not sure how we solved this. Let's say in the 1940s, if you're at Bell Labs and there are these new technologies coming out. Pulse-code modulation, how do you transfer signals? How do you digitize signals? How do you transfer them over analog wires? There are all these papers about the engineering constraints and the details, and then there's one which comes up with the idea of the bit, which has implications across many different fields. You need some system which can then look at that and say, "Okay, we need to apply this to probability. We need to apply this to computer science," et cetera.

</details>

**Terence Tao**: 在未来，AI将提出这种统一概念的下一个版本。你如何在数百万篇论文中识别它，这些论文可能确实构成了进步，但其通用统一思想的含量却少得多？这在很大程度上是**时间的考验**（test of time）。许多伟大的思想在首次提出时并没有得到很好的接受。直到其他一些科学家意识到他们可以进一步发展并将其应用于自己的领域……**深度学习**（Deep learning）本身长期以来都是AI的一个利基领域。完全通过数据训练而非第一性原理推理来获取答案的想法极具争议，它花了很长时间才开始结果。你提到了比特。除了现在普遍使用的**零一**（zero-one）计算机体系结构之外，还有其他建议。

<details>
<summary>Original English</summary>

**Terence Tao**: In the future, the AIs are coming up with the next version of this unifying concept. How would you identify it among millions of papers that might actually constitute progress, but which have much less in terms of general unifying ideas? A lot of it's the test of time. Many great ideas didn't actually get a great reception at the time they were first proposed. It was only after some other scientists realized that they could take it further and apply them to their own... Deep learning itself was a niche area of AI for a long time. The idea of getting answers entirely through training on data and not through first principles reasoning was very controversial, and it just took a long time before it started bearing fruit. You mentioned the bit. There were other proposals for computer architectures than the zero-one that is universal today.

</details>

**Terence Tao**: 我认为还有**三进制逻辑**（trits, three-valued logic）。在另一个宇宙中，也许会出现不同的范式。例如，**Transformer**是所有现代**大型语言模型**（large language models）的基础，它是第一个足够复杂的深度学习架构，能够捕捉语言。但它不一定非得是这样。可能还有其他架构率先做到了这一点，一旦被采用，它就会成为标准。评估一个想法是否会富有成效的一个原因在于它取决于未来。它也取决于文化和社会，哪些被采纳，哪些不被采纳。数学中的**十进制数字系统**（base ten numeral system）极其有用，比**罗马数字系统**（Roman numeral system）好得多。

<details>
<summary>Original English</summary>

**Terence Tao**: I think there were trits, three-valued logic. In an alternate universe, maybe a different paradigm would have shown up. The transformer, for example, is the foundation of all modern large language models, and it was the first deep learning architecture that really was sophisticated enough to capture language. But it didn't have to be that way. There could've been some other architecture that was the first to do it and once that was adopted, it would become the standard. One reason why it's hard to assess whether a given idea is going to be fruitful is that it depends on the future. It depends also on the culture and society, which ones get adopted, which ones don't. The base ten numeral system in mathematics is extremely useful, much better than the Roman numeral system, for instance.

</details>

**Terence Tao**: 但同样，十并没有什么特别之处。它之所以对我们有用，是因为所有其他人都使用它。我们已经对其进行了标准化。我们所有的计算机和数字表示系统都围绕它构建，所以我们现在就被它束缚住了。有些人偶尔会推崇十进制以外的其他系统，但阻力太大了。我们不能孤立地看待任何一项科学成就，并在不了解过去和未来背景的情况下给它一个客观的评级。因此，它可能永远无法像对待更局限的问题那样，通过**强化学习**（reinforcement learn）来解决。

<details>
<summary>Original English</summary>

**Terence Tao**: But again, there's nothing special about ten. It's a system that is useful for us because everyone else uses it. We've standardized it. We've built all our computers and our number representation systems around it, so we're stuck with it now. Some people occasionally push for other systems than decimal, but there's just too much inertia. It's not something where you can look at any given scientific achievement purely in isolation and give it an objective grade without being aware of the context both in the past and the future. So it may never be something that you can just reinforcement learn the same way that you can for much more localized problems.

</details>

**Terence Tao**: 通常在科学史上，当一个新理论出现，事后我们意识到它是正确的，它似乎会产生一些推论，这些推论要么毫无意义，因为它们是错误的，我们后来才意识到它们为什么是错误的，要么它们是正确的，但在当时看起来却非常不可思议。正如你所说，阿里斯塔克斯在公元前三世纪就提出了日心说。古雅典人会说：“这不可能，因为如果地球围绕太阳转，我们应该看到恒星的相对位置发生变化，而唯一不会发生这种情况的方式是它们距离太远，以至于你察觉不到任何**视差**（parallax）。”这实际上是正确的推论。但有时推论是错误的，我们只需要提升到更高的理解水平。

<details>
<summary>Original English</summary>

**Terence Tao**: Often in the history of science when a new theory comes up that in retrospect we realize is correct, it seems to make implications that either make no sense because they're wrong, and we realize later on why they're wrong, or they're correct but seem wildly implausible at the time. As you talked about, Aristarchus had heliocentrism in the third century BC. The ancient Athenians were like, "This can't be because if the earth is going around the sun, we should see the relative position of the stars change as we're going around the sun, and the only way that wouldn't be the case is if they're so far away that you don't notice any parallax," which is actually the correct implication. But there's times when the implication is incorrect and we just need to graduate to a better level of understanding.

</details>

**Terence Tao**: **莱布尼茨**（Leibniz）曾指责牛顿，并不同意牛顿的**引力理论**（theory of gravity），理由是它暗示了**超距作用**（action at a distance），他们不知道其机制，而牛顿本人也对**惯性质量**（inertial mass）和**引力质量**（gravitational mass）是同一个量感到震惊。所有这些问题后来都由**爱因斯坦**（Einstein）解决了。但这仍然是进步。所以，对于AI的同行评审系统来说，问题将是：即使你可以证伪一个理论，你如何注意到它相对于之前的理论仍然构成了进步？通常，最终正确的理论最初在许多方面都更糟糕。哥白尼的行星理论比**托勒密**（Ptolemy）的理论更不准确。

<details>
<summary>Original English</summary>

**Terence Tao**: Leibniz would chide Newton and disagree with Newton's theory of gravity on the basis that it implied action at a distance, and they didn't know the mechanism, and Newton himself was sort of stunned that inertial mass and gravitational mass were the same quantity. All these things later were resolved by Einstein. But it was still progress. So the question for a system of peer review for AI would be: even if you can falsify a theory, how would you notice that it still constitutes progress relative to the thing before? Often, the ultimately correct theory initially is worse in many ways. Copernicus's theory of the planets was less accurate than Ptolemy's theory.

</details>

**Terence Tao**: **地心说**（Geocentrism）到那时已经发展了一千年，他们做了许多调整和日益复杂的**临时修正**（ad hoc fixes），使其越来越准确。哥白尼的理论简单得多，但准确性差很多。直到开普勒才使其比托勒密的理论更准确。科学总是在进步。当你只得到部分解决方案时，它看起来比一个不正确的理论更糟糕，但这个理论却以某种方式完成到可以回答所有问题的程度。正如你所说，牛顿的理论有很大的谜团。它们具有质量等效和超距作用，这些问题直到几个世纪后才通过一种概念上截然不同的方法解决。

<details>
<summary>Original English</summary>

**Terence Tao**: Geocentrism had been developed for a millennium by that point, and they had made many tweaks and increasingly complicated ad hoc fixes to make it more and more accurate. Copernicus's theory was a lot simpler but much less accurate. It was only Kepler that made it more accurate than Ptolemy's theory. Science is always a work in progress. When you only get part of the solution, it looks worse than a theory which is incorrect but somehow has been completed to the point where it kind of answers all the questions. As you say, Newton's theory had big mysteries. They had the equivalence of mass and action at a distance, which were only resolved with a very conceptually different approach centuries afterwards.

</details>

**Terence Tao**: 通常，进步的取得不是通过增加更多理论，而是通过删除你头脑中的一些假设。地心说之所以能持续这么长时间的一个原因是我们有一个观念，即物体自然倾向于保持静止。这是**亚里士多德物理学**（Aristotelian notion of physics）的观念，所以地球在运动的想法……为什么我们都没有摔倒？一旦你有了牛顿的**运动定律**（laws of motion）——运动中的物体将保持运动等等——那么它就说得通了。从概念上讲，意识到地球在运动是一个非常大的飞跃。它感觉不到在运动。

<details>
<summary>Original English</summary>

**Terence Tao**: Often progress has to be made not by adding more theories, but by deleting some assumptions that you have in your mind. One reason why geocentrism held on for so long is we had this idea that objects naturally want to stay at rest. This is the Aristotelian notion of physics, and so the idea that the Earth was moving… How come we weren't all falling over? Once you have Newton's laws of motion—an object in motion remains in motion and so forth—then it makes sense. Conceptually, it's a very big leap to realize that the Earth is in motion. It doesn't feel like it's in motion.

</details>

**Terence Tao**: 最大的进步，比如**达尔文**（Darwin）的**进化论**（theory of evolution），是物种并非静态不变的观念。这并不明显，因为你在有生之年看不到进化。好吧，现在我们实际上可以看到，但它看起来是永久和静态的。现在我们正在经历一场**认知哥白尼革命**（cognitive Copernican revolution），我们曾经认为人类智能是宇宙的中心，而现在我们看到存在着截然不同类型的智能，它们具有截然不同的优势和劣势。我们对哪些任务需要智能，哪些不需要智能的评估，必须进行相当大的重新排序。

<details>
<summary>Original English</summary>

**Terence Tao**: The biggest advances, like Darwin's theory of evolution, is the idea that species are not static. This is not obvious because you don't see evolution in your lifetime. Well, now we actually can, but it seems permanent and static. Right now we're going through a cognitive version of the Copernican revolution, where we used to think that human intelligence is the center of the universe, and now we're seeing that there are very different types of intelligence out there with very different strengths and weaknesses. Our assessment of which tasks require intelligence, which ones don't, has to be reordered quite a bit.

</details>

**Terence Tao**: 试图将AI融入我们的科学进步理论以及什么是难、什么是易，我们正面临很大的困难。我们必须提出以前从未真正问过的问题。或者哲学家们可能问过，但现在我们都必须处理它。

<details>
<summary>Original English</summary>

**Terence Tao**: Trying to fit AI into our theories of scientific progress and what is hard and what is easy, we're struggling quite a lot. We have to ask questions that we've never really had to ask before. Or maybe the philosophers had, but now we all have to deal with it.

</details>

**Dwarkesh**: 这引出了一个我一直非常好奇的话题。你提到了达尔文的进化论。有一本书叫《**发条宇宙**》（The Clockwork Universe），作者是**爱德华·多尔尼克**（Edward Dolnick），它涵盖了我们正在讨论的这段历史时期的大量内容。他在书中有一个有趣的观察。**《物种起源》**（The Origin of Species）于1859年出版。**《自然哲学的数学原理》**（Principia Mathematica）于1687年出版。所以《物种起源》比《原理》晚了两个世纪。从概念上讲，达尔文的理论似乎更简单。达尔文的同时代生物学家**托马斯·赫胥黎**（Thomas Huxley）读了《物种起源》后说：“怎么会没想到呢，真笨。”从来没有人会这样评价《原理》，责备自己没有比牛顿更早发现引力。

<details>
<summary>Original English</summary>

**Dwarkesh**: This brings up a topic I've been very curious about. You mentioned Darwin's theory of evolution. There's this book, The Clockwork Universe by Edward Dolnick, which covers a lot of this era of history we're talking about. He has this interesting observation in there. The Origin of Species was published in 1859. Principia Mathematica was published in 1687. So The Origin of Species comes out two centuries after Principia. Conceptually, it seems like Darwin's theory is simpler. There's a contemporaneous biologist to Darwin, Thomas Huxley, who reads The Origin of Species and he says, "How stupid not to have thought of that." Nobody ever says that about Principia, chiding themselves for not having beaten Newton to gravity.

</details>

**Dwarkesh**: 所以问题是为什么花了更长时间？似乎很大的一个原因是你刚才所说的。**自然选择**（natural selection）的证据在某种意义上是压倒性的，但它是累积和回顾性的，而牛顿可以说：“这是我的方程。让我看看月球的**轨道周期**（orbital period）和它的距离，如果它们一致，那么我们就取得了进步。”**卢克莱修**（Lucretius）实际上在公元前一世纪就有物种适应环境的想法，但直到达尔文才有人真正谈论它，因为卢克莱修无法进行实验并强迫人们关注。

<details>
<summary>Original English</summary>

**Dwarkesh**: So there's a question of why did it take longer? It seems like a big part of the reason is what you were saying. The evidence for natural selection is overwhelming in a certain sense, but it's cumulative and retrospective, whereas Newton can just say, "Here are my equations. Let me see the moon's orbital period and its distance, and if it lines up, then we've made progress." Lucretius actually had this idea that species adapted to their environment in the first century BC but nobody really talks about it until Darwin because Lucretius couldn't run some experiment and force people to pay attention.

</details>

**Dwarkesh**: 我想知道我们事后是否会发现，在那些具有这种**紧密数据循环**（tight data loop）的领域中，即使它们在概念上更困难，我们也能更容易地验证它们，从而取得更大的进展。

<details>
<summary>Original English</summary>

**Dwarkesh**: I wonder if we'll in retrospect end up seeing much more progress in domains which have this kind of tight data loop where you can verify them quite easily, even though they're conceptually much more difficult.

</details>

**Terence Tao**: 我认为科学的一个方面是，它不仅仅是创造一个新理论并验证它，而是将其传达给其他人。达尔文是一位了不起的**科学传播者**（science communicator）。他用英语，用自然语言写作。我说话像——不，放松点。我必须摆脱我的技术思维。他用**通俗英语**（plain English）说话，不使用方程，他综合了许多不同的事实。进化的细枝末节在过去就已经被研究出来，但他有一个非常引人注目的愿景。

<details>
<summary>Original English</summary>

**Terence Tao**: I think one aspect of science is that it's not just creating a new theory and validating it, but communicating it to others. Darwin was an amazing science communicator. He wrote in English, in natural language. I'm speaking like a— No Lean. I have to get out of my technical mindset. He spoke in plain English, didn't use equations, and he synthesized a lot of disparate facts. Little pieces of evolution had been worked out in the past, but he had this very compelling vision.

</details>

**Terence Tao**: 再次，他仍然遗漏了一些东西。他不知道**遗传机制**（mechanism for heredity），他没有**DNA**。但他的写作风格很有说服力，这帮助很大。牛顿用**拉丁语**（Latin）写作。他为了解释自己的工作，发明了全新的数学领域。他所处的时代，科学家们也更加隐秘和竞争。**学术界**（Academia）仍然存在竞争，但在牛顿时代甚至更糟。他隐藏了一些他最好的见解，因为他不想让他的竞争对手获得任何优势。据我所知，他也是一个有些令人不快的人。直到牛顿去世几十年后，其他科学家用更简单的语言解释他的工作，才广为流传。

<details>
<summary>Original English</summary>

**Terence Tao**: Again, he was still missing things. He didn't know the mechanism for heredity, he didn't have DNA. But his writing style was persuasive, and that helped a lot. Newton wrote in Latin. He had invented entire new areas of mathematics just to explain what he was doing. He was also from an era where scientists were much more secretive and competitive. Academia is still competitive, but it was even worse back in Newton's day. He held back some of his best insights because he didn't want his rivals to get any advantage. He was also a somewhat unpleasant person from what I gather. It was only a couple of decades after Newton when other scientists explained his work in much simpler terms that they became widespread.

</details>

**Terence Tao**: 阐述的艺术、论证的艺术以及创造叙事也是科学中非常重要的一部分。如果你有数据，这会有所帮助，但人们需要被说服，否则他们就不会进一步推动它，也不会投入最初的精力去学习你的理论并真正探索它。这是另一个很难通过强化学习来做的事情。你如何衡量自己的说服力？

<details>
<summary>Original English</summary>

**Terence Tao**: The art of exposition and making a case and creating a narrative is also a very important part of science. If you have the data, it helps, but people need to be convinced, otherwise they will not push it further or take the initial investment to learn your theory and really explore it. That's another thing which is really hard to reinforcement learn on. How can you score how persuasive you are?

</details>

**Terence Tao**: 嗯，有很多营销部门都在尝试做这个。也许AI尚未被优化为具有说服力是件好事。科学有其社会性。尽管我们以其客观性为荣，其中包含数据、实验和验证，但我们仍然需要讲故事并说服我们的同行科学家。这是一件软性的、模糊的事情。它是数据和描绘叙事的结合，它是一个关于空白的叙事。

<details>
<summary>Original English</summary>

**Terence Tao**: Well, there are entire marketing departments trying to do this. Maybe it's good that AI is not yet optimized to be persuasive. There's a social aspect to science. Even though we pride ourselves on having an objective side to it, where there's data and experiment and validation, we still have to tell stories and convince our fellow scientists. That's a soft, squishy thing. It's a combination of data and painting a narrative, and it's a narrative of gaps.

</details>

**Terence Tao**: 即使是达尔文，正如我所说，他的理论有些部分无法解释。但他仍然可以说服人们，未来会发现**过渡形式**（transitional forms），会发现**遗传机制**（mechanism of inheritance），而他们也确实发现了。我不知道你如何能够如此精确地量化这一点，以至于你可以开始进行强化学习。也许这将永远是科学的人类一面。

<details>
<summary>Original English</summary>

**Terence Tao**: Even with Darwin, as I said, there were pieces of his theory he could not explain. But he could still make a case that in the future, people would find transitional forms, that they would find the mechanism of inheritance, and they did. I don't know how you can quantify that in such a precise way that you can start doing reinforcement learning. Maybe that will be forever the human side of science.

</details>

### 数据分析的价值与AI在数学领域的进展

**Dwarkesh**: 我从阅读和观看你关于**宇宙距离阶梯**（cosmic distance ladder）的资料中有一个收获……顺便提一下，我强烈推荐大家观看你与**3Blue1Brown**合作的宇宙距离阶梯系列。一个收获是，许多领域的**演绎过剩**（deductive overhang）可能比人们意识到的要大得多。如果你对如何研究一个问题有正确的洞察力，你可能会惊讶于你能从世界中学到更多。我不知道你是否认为这是你正在研究的历史时期天文学的产物。或者仅仅是基于目前地球上发生的数据，我们实际上可以比我们所知的推断出更多？

<details>
<summary>Original English</summary>

**Dwarkesh**: One takeaway I had from reading and watching your stuff on the cosmic distance ladder… By the way, I highly recommend people watch your series with 3Blue1Brown on the cosmic distance ladder. One takeaway was that the deductive overhang in many fields could be so much bigger than people realize. If you just had the right insight about how to study a problem, you might be surprised at how much more you could learn about the world. I wonder if you think that's a product of astronomy at the particular times in history that you're studying. Or is it just that based on the data that is incident on the Earth right now, we could actually divine a lot more than we happen to know?

</details>

**Terence Tao**: 天文学是第一批真正拥抱**数据分析**（data analysis）并从现有信息中榨取所有可能信息的科学之一，因为数据是瓶颈。现在仍然是瓶颈。收集**天文学数据**（astronomical data）确实很难。天文学家在从微小数据痕迹中提取各种结论方面堪称世界一流，几乎就像**福尔摩斯**（Sherlock）。我听说许多量化对冲基金更喜欢聘用天文学博士，实际上。他们出于其他原因也对从各种随机数据中提取信号非常感兴趣。

<details>
<summary>Original English</summary>

**Terence Tao**: Astronomy was one of the first sciences to really embrace data analysis and squeezing every last possible drop of information out of the information they had because data was the bottleneck. It still is the bottleneck. It's really hard to collect astronomical data. Astronomers are world-class in extracting all kinds of conclusions from little traces of data, almost like Sherlock. I hear that for a lot of quant hedge funds, their preferred hire is an astronomy PhD, actually. They are also very interested for other reasons in extracting signals from various random bits of data.

</details>

**Dwarkesh**: 好的，说到巧妙的想法，我的一个听众**肖恩**（Shawn）解决了**简街**（Jane Street）为我的听众设置的难题，并在**X**上发布了一篇精彩的**逐步解说**（walkthrough）。就上下文而言，简街训练了一个**ResNet**，打乱了所有96层，然后挑战人们只使用模型的输出和训练数据，将其按正确顺序重新排列。你不能**暴力破解**（brute force）这个问题——可能的排序比宇宙中的原子还要多。所以肖恩把问题分成了两个不同的部分。首先，将这些层配对成48个不同的**块**（blocks）。其次，将这些块按正确顺序排列。

<details>
<summary>Original English</summary>

**Dwarkesh**: Okay, speaking of clever ideas, one of my listeners, Shawn, solved the puzzle that Jane Street made for my audience and posted a great walkthrough on X. For context, Jane Street trained a ResNet, shuffled all 96 layers, and then challenged people to put them back in the right order using only the model's outputs and training data. You can't brute force this – there's more possible orderings than atoms in the universe. So Shawn broke the problem into two different parts. First, pair the layers into 48 different blocks. And second, put those blocks in the right order.

</details>

**Dwarkesh**: 对于配对，肖恩意识到在一个训练有素的ResNet中，**残差块**（residual block）中两个**权重矩阵**（weight matrices）的乘积应该具有独特的**负对角线模式**（negative diagonal pattern）。这是模型防止残差流失控的一种方式。通过这一见解，他能够恢复正确的配对。对于排序，肖恩注意到如果他根据其**残差贡献**（residual contributions）的大小对块进行排序，模型似乎会改进。从这个粗略的近似值开始，他结合了一个巧妙的**排名启发式算法**（ranking heuristic）和**局部交换**（local swaps）来恢复确切的正确顺序。他的完整逐步解说已链接在描述中。不过，如果你没有及时解决这个难题，也别担心。还有一个关于**后门大型语言模型**（backdoored LLMs）的难题，连简街都不知道如何解决。你可以在**janestreet.com/dwarkesh**找到它。好的，回到特伦斯！

<details>
<summary>Original English</summary>

**Dwarkesh**: For pairing, Shawn realized that in a well-trained ResNet, the product of two weight matrices in a residual block should have a distinctive negative diagonal pattern. This arises as a way for the model to keep the residual stream from growing out of control. From this insight, he was able to recover the right pairings. For ordering, Shawn noticed that the model seemed to improve if he sorted the blocks by the size of their residual contributions. Starting with that rough approximation, he combined a clever ranking heuristic with local swaps to recover the exact right order. His full walkthrough is linked in the description. Don't worry if you didn't get to this puzzle in time, though. There's still one up about backdoored LLMs that even Jane Street doesn't know how to solve. You can find it at janestreet.com/dwarkesh. Alright, back to Terence!

</details>

**Terence Tao**: 我们确实没有充分探索如何从各种信号中提取额外信息。随便举一个研究例子，我记得曾经读到过，人们试图衡量科学家实际阅读他们引用的论文的频率。你如何衡量这一点？你可以尝试调查不同的科学家，但他们有一个巧妙的技巧。许多引文都有小的**错别字**（typos），比如数字错误或标点符号几乎错误。他们测量了错别字从一个参考文献复制到下一个参考文献的频率，他们可以推断作者是否只是复制粘贴参考文献而没有实际检查它。

<details>
<summary>Original English</summary>

**Terence Tao**: We do under-explore how to extract extra information from various signals. Just to pick one random study, I remember reading once that people were trying to measure how often scientists actually read the papers that they cite. How do you measure this? You could try to survey different scientists, but they had a clever trick. Many citations have little typos, like a number is wrong or punctuation is almost wrong. They measured how often a typo got copied from one reference to the next, and they could infer whether an author was just copying and pasting a reference without actually checking it.

</details>

**Terence Tao**: 从中，他们能够推断出人们关注程度的某种衡量标准。所以有一些巧妙的技巧可以提取……你之前提出的这些问题，即我们如何评估一项科学发展是否富有成效、有趣或代表真正的进步……也许数据中确实存在这种现象的有用指标或足迹。我们可以检查引文以及在会议中提及某事物的频率。也许有很多**科学社会学**（sociology of science）研究可以做，以实际检测这些事情。也许我们应该请一些天文学家来处理这个问题，实际上。

<details>
<summary>Original English</summary>

**Terence Tao**: From that, they were able to infer some measure of how much attention people were paying. So there are some clever tricks to extract… These questions you posed earlier of how we can assess whether a scientific development is fruitful, interesting, or represents real progress… Maybe there are really useful metrics or footprints of this phenomenon in data. We can examine citations and how often something is mentioned in a conference. Maybe there's a lot of sociology of science research to be done that could actually detect these things. Maybe we should get some astronomers on the case, actually.

</details>

**Terence Tao**: 这很好地引出了，从外部看来，数学AI正在取得的进展。你最近发表了一篇帖子，指出在过去的几个月里，AI程序已经解决了**埃尔德什问题**（Erdős problems）中约1100个问题中的50个。我不知道这是否仍然正确，但大约一个月前你说暂停了，因为低垂的果实已经被摘走了。首先，我很好奇情况是否仍然如此，即我们已经摘走了低垂的果实，现在我们正处于这个**平台期**（plateau）？

<details>
<summary>Original English</summary>

**Terence Tao**: That brings us nicely to the progress that, from the outside, it seems like AI for math is making. You had a post recently where you pointed out that over the last few months, AI programs have solved fifty out of the eleven hundred odd Erdős problems. I don’t know if it’s still correct, but as of a month ago you said that there had been a pause because the low-hanging fruit had been picked. First of all, I'm curious if that is still the case, that we have picked the low-hanging fruit and now we're at this plateau currently?

</details>

**Terence Tao**: 看起来确实如此。在AI的辅助下，大约50个问题已经解决，这很棒，但还有大约600个问题待解决。人们现在仍在努力解决其中一两个问题。我们现在看到的纯AI解决方案少了很多，即AI一次性解决问题的情况。这种情况曾经发生过一个月，现在已经停止了，并非没有尝试。我知道有三次独立的尝试，让**前沿模型AI**（frontier model AIs）同时攻击所有问题。它们发现了一些次要的观察结果，或者发现一些问题已经在文献中解决了，但尚未出现任何进一步的纯AI驱动的解决方案。

<details>
<summary>Original English</summary>

**Terence Tao**: It does seem so. Fifty-odd problems have been solved with AI assistance, which is great, but there's like six hundred to go. People are still chipping away at one or two of these right now. We're seeing a lot fewer pure AI solutions now where the AI just one-shots the problem. There was a month where that happened and that has stopped, not for lack of trying. I know of three separate attempts to get frontier model AIs to just attack every single one of the problems simultaneously. They pick out some minor observations, or maybe they find that some problem was already solved in the literature, but there hasn't been any further purely AI-powered solution yet.

</details>

**Terence Tao**: 人们目前正在大量使用AI。有人可能会使用AI生成一种可能的**证明策略**（proof strategy），然后另一个人会使用单独的AI工具来批判它、重写它、为其生成一些**数值数据**（numerical data），或者进行**文献调查**（literature survey）。有些问题是通过许多人类和许多AI工具之间的持续对话解决的。但这似乎是一次性的事情。

<details>
<summary>Original English</summary>

**Terence Tao**: People are using AI a lot currently. Someone might use AI to generate a possible proof strategy, and then another person will use a separate AI tool to critique it, rewrite it, generate some numerical data for it, or do a literature survey. Some problems have been solved by an ongoing conversation between lots of humans and lots of AI tools. But it does seem like it was this one-off thing.

</details>

**Terence Tao**: 也许这些问题的一个类比是，你置身于一个充满悬崖峭壁的山脉中。也许有一堵三英尺高的小墙，一堵六英尺高的墙，然后是十五英尺高的墙，再然后是一些一英里高的悬崖。你试图攀爬尽可能多的这些悬崖，但周围一片漆黑。我们不知道哪些高，哪些矮。所以我们尝试点亮一些蜡烛，制作一些地图，慢慢地我们发现其中一些是可以攀爬的。其中一些我们可以识别出墙上可以首先到达的部分路径。

<details>
<summary>Original English</summary>

**Terence Tao**: Maybe one analogy for these problems is that you're in some sort of mountain range with all kinds of cliffs and walls. Maybe there's a little wall which is three feet high, and one that's six feet high, and then there's fifteen feet high, and then there are some mile-high cliffs. You're trying to climb as many of these cliffs as possible, but it's in the dark. We don't know which ones are tall, which ones are short. So we try to light some candles and make some maps, and slowly we figure out some of them are climbable. Some of them we can identify a partial track in the wall that you can reach first.

</details>

**Terence Tao**: 这些AI工具就像**跳跃机器**（jumping machines），它们可以跳到两米高，比任何人都高。有时它们跳错了方向，有时它们会坠毁，但有时它们可以到达我们以前无法到达的最低矮的墙顶。我们只是让它们在这片山脉中随意跳跃。曾经有一段激动人心的时期，它们确实能够找到并到达所有低矮的墙。也许下次模型取得重大进展时，它们会再次尝试，更多的墙会被攻克。但这是一种不同的数学研究方式。通常我们会**爬山**（hill climb），做一些小标记，并尝试识别部分事物。

<details>
<summary>Original English</summary>

**Terence Tao**: These AI tools, they're like jumping machines that can jump two meters in the air, higher than any human. Sometimes they jump in the wrong direction, and sometimes they crash, but sometimes they can reach the tops of the lowest walls that we couldn't reach before. We've just set them loose in this mountain range, hopping around. There was this exciting period where they could actually find all the low ones and reach them. Maybe the next time there's a big advance in the models, they will try it again, and a few more will be breached. But it's a different style of doing mathematics. Normally we would hill climb, make little markers, and try to identify partial things.

</details>

**Terence Tao**: 这些工具要么成功，要么失败。它们在创造**部分进展**（partial progress）或识别应首先关注的**中间阶段**（intermediate stages）方面表现不佳。回到之前的讨论，我们无法像评估一次性成功或失败那样评估部分进展。

<details>
<summary>Original English</summary>

**Terence Tao**: These tools either succeed or they fail. They've been really bad at creating partial progress or identifying intermediate stages that you should focus on first. Going back to this previous discussion, we don't have a way of evaluating partial progress the same way we can evaluate a one-shot success or failure of solving a problem.

</details>

**Dwarkesh**: 你刚才说的有两种不同的思考方式。其中一种对AI的进步更悲观，另一种更乐观。悲观的说法是：“哦，它们只能达到一定高度的墙，这没有人类达到的高。”第二种是，它们具有这种强大的特性，一旦达到某个**水位线**（waterline），它们就可以解决该水位线上所有可用的问题，这是我们人类根本无法做到的。

<details>
<summary>Original English</summary>

**Dwarkesh**: There's two different ways to think through what you've just said. One of them is more bearish on AI progress, and one of them is more bullish. The bearish one being, "Oh, they're only getting to a certain height of wall, which is not as high as humans are reaching." The second is that they have this powerful property that once they achieve a certain waterline, they can fill every single problem that is available at that waterline, which we simply can't do with humans.

</details>

**Dwarkesh**: 我们无法复制一百万个你，并给每个你一百万美元的**推理计算**（inference compute），让你同时对一百万个不同的问题进行一百年的**主观时间研究**（subjective time research）。但一旦AI达到陶哲轩的水平，它们就能做到。一旦它们达到中级水平，它们就能做到中级版本。我们现在应该看空AI的原因，就是我们尤其应该看多AI的原因。甚至不是当它们达到**超人智能**（superhuman intelligence）的时候，而仅仅是当它们达到**人类水平智能**（human-level intelligence）的时候，因为它们的**人类水平智能**在质量上比我们的人类水平智能更广阔、更强大。

<details>
<summary>Original English</summary>

**Dwarkesh**: We can't make a million copies of you and give each of them a million dollars of inference compute and have you do a hundred years of subjective time research on a million different problems at the same time. But once AIs reach Terence Tao-level, they could do that. Once they reach intermediate levels, they could do the intermediate version of that. The same reason that we should be bearish now is the reason we should be especially bullish. Not even when they achieve superhuman intelligence, but just when they achieve human-level intelligence, because their human-level intelligence is qualitatively wider and more powerful than our human-level intelligence.

</details>

**Terence Tao**: 我同意。它们擅长广度，而人类擅长深度，至少人类专家如此。我认为它们非常互补。但我们目前进行数学和科学的方式侧重于深度，因为那是人类专业知识所在，因为人类无法做到广度。我们必须重新设计我们进行科学研究的方式，以充分利用我们现在拥有的这种**广度能力**（breadth capability）。我们应该投入更多的精力来创建非常**广泛的问题类别**（broad classes of problems），而不是一两个真正深入、重要的问题。

<details>
<summary>Original English</summary>

**Terence Tao**: I agree. They excel at breadth, and humans excel at depth, human experts at least. I think they're very complementary. But our current way of doing math and science is focused on depth because that's where human expertise is, because humans can't do breadth. We have to redesign the way we do science to take full advantage of this breadth capability that we now have. We should have a lot more effort in creating very broad classes of problems to work on rather than one or two really deep, important problems.

</details>

**Terence Tao**: 我们仍然应该有深刻、重要的问题，人类仍然应该致力于解决它们。但现在我们有了另一种做科学的方式。我们可以通过首先让这些**广泛、中等能力的AI**（broad, moderately competent AIs）来绘制地图并进行所有简单的观察，从而探索全新的科学领域。然后识别某些**困难的孤岛**（islands of difficulty），人类专家可以过来解决这些问题。我非常看好未来**互补性科学**（complementary science）的发展。最终，你希望同时获得广度和深度，并以某种方式获得两全其美。但我们需要练习广度方面。它太新了。我们甚至还没有充分利用它的范式。但我们会做到的，然后科学将变得面目全非，我认为。

<details>
<summary>Original English</summary>

**Terence Tao**: We should still have the deep, important problems, and humans should still be working on them. But now we have this other way of doing science. We can explore entirely new fields of science by first getting these broad, moderately competent AIs to map it out and make all the easy observations. And then identify certain islands of difficulty, which human experts can then come and work on. I see very much a future of very complementary science. Eventually, you would hope to get both breadth and depth and somehow get the best of both worlds. But we need practice with the breadth side. It's too new. We don't even have the paradigms to really take full advantage of it. But we will, and then science will be unrecognizable after that, I think.

</details>

### AI对编程与数学研究效率的影响

**Dwarkesh**: 关于互补性这一点，程序员们已经注意到，由于这些AI工具，他们的生产力大大提高了。我不知道你作为一名数学家是否有同感，但**情绪化编程**（vibe coding）和**情绪化研究**（vibe researching）之间的一个巨大区别似乎在于，对于软件来说，重点是通过你的工作对世界产生一些影响。如果它能让你更好地理解问题，或者想出一些干净的**抽象**（abstraction）来体现在你的代码中，那对最终目标是至关重要的。

<details>
<summary>Original English</summary>

**Dwarkesh**: To this point about complementarity, programmers have noticed that they're way more productive as a result of these AI tools. I don't know if you as a mathematician feel the same way, but it does seem like one big difference between vibe coding and vibe researching is that with software, the whole point is to have some effect on the world through your work. If it leads to you better understanding a problem or coming up with some clean abstraction to embody in your code, that is instrumental to the end goal.

</details>

**Dwarkesh**: 而对于研究来说，我们关心解决**千禧年大奖难题**（Millennium Prize Problems）的原因是，大概在解决它们的过程中，我们发现了新的**数学对象**（mathematical objects）或新技术，从而增进了我们文明对数学的理解。所以证明对中间工作是至关重要的。我不知道你是否同意这种**二分法**（dichotomy），或者它是否能以任何方式解释我们在软件与研究中将看到的相对提升。

<details>
<summary>Original English</summary>

**Dwarkesh**: Whereas with research, the reason we care about solving the Millennium Prize Problems is that presumably that in the process of solving them, we discover new mathematical objects or new techniques that advance our civilization's understanding of mathematics. So the proof is instrumental to the intermediate work. I don't know if you agree with that dichotomy or if that in any way will explain the relative uplift we'll see in software versus research.

</details>

**Terence Tao**: 当然在数学中，**过程**（process）往往比问题本身更重要。问题只是衡量进步的一种**代理**（proxy）。我认为即使在软件中，也有不同类型的软件任务。如果你只是创建一个网页，它做的事情与成千上万个其他网页相同，那就没有什么技能可学。好吧，可能个人程序员仍然可以学到一些技能。但对于**样板代码**（boilerplate-type code），你绝对应该将其外包给AI。

<details>
<summary>Original English</summary>

**Terence Tao**: Certainly in math, the process is often more important than the problem itself. The problem is kind of a proxy for measuring progress. I think even in software, there are different types of software tasks. If you just create a webpage that does the same thing that a thousand other webpages do, there's no skill to be learned. Well, there is still some skill maybe that the individual programmer could pick up. But for boilerplate-type code, it's something that you should definitely offload to AI.

</details>

**Terence Tao**: 有时一旦你编写了代码，你仍然需要维护它。升级它并使其与其他事物兼容存在问题。我听说程序员报告说，即使AI可以创建工具的第一个原型，使其与所有其他事物结合并以他们想要的方式与现实世界交互，这是一个持续的过程。如果你没有从编写代码中获得的技能，这可能会影响你日后维护它的能力。

<details>
<summary>Original English</summary>

**Terence Tao**: Sometimes once you make the code, you still have to maintain it. There are issues with upgrading it and making it compatible with other things. I've heard programmers report that even if an AI can create the first prototype of a tool, making it mesh with everything else and making it interact with the real world in the way they want is an ongoing process. If you don't have the skills that you pick up from writing the code, that may impact your ability to maintain it down the road.

</details>

**Terence Tao**: 所以是的，当然数学家们，我们已经用问题来建立**直觉**（intuition）并训练人们对什么是真、什么是可预期的、什么是可证明的、什么是困难的有很好的认识。立即得到答案实际上可能会抑制这个过程。我之前区分了理论和实验。在大多数科学中，理论方面和实验方面是平等的。数学一直很独特，它几乎完全是理论性的。

<details>
<summary>Original English</summary>

**Terence Tao**: So yes, certainly mathematicians, we've used problems to build intuition and to train people to have a good idea of what's true, what to expect, what is provable, and what is difficult. Just getting the answers right away may actually inhibit that process. I made a distinction between theory and experiment before. In most sciences, there's an equal division between the theoretical side and the experimental side. Math has been unique in that it's almost entirely theoretical.

</details>

**Terence Tao**: 我们非常重视尝试对事物为什么是真或假有连贯、清晰的理论。我们没有进行过很多实验来研究，如果我们有两种不同的方法来解决问题，哪种更有效。我们有一些直觉，但我们没有进行大规模研究，例如，我们选取一千个问题并进行测试。但我们现在可以这样做。我认为**AI类工具**（AI-type tools）将真正革新数学的**实验方面**（experimental side），你不再那么关心个体问题和解决它们的过程，而是希望收集关于哪些方法有效、哪些方法无效的**大规模数据**（large-scale data）。

<details>
<summary>Original English</summary>

**Terence Tao**: We place a premium on trying to have coherent, clean theories of why things are true and false. We haven't done many experiments as to, if we have two different ways to solve a problem, which is more effective. We have some intuition, but we haven't done large-scale studies where we take a thousand problems and just test them. But we can do that now. I think AI-type tools will actually revolutionize the experimental side of math, where you don't care so much about individual problems and the process of solving them, but you want to gather large-scale data about what things work and what things don't.

</details>

**Terence Tao**: 就像如果你是一家软件公司，你想推出一千个软件，你并不想手工制作每一个并从每一个中吸取教训。你只想找到能让你扩展的**工作流程**（workflows）。**大规模数学**（mathematics at scale）的理念尚处于起步阶段。但那正是AI将真正革新这一学科的地方。

<details>
<summary>Original English</summary>

**Terence Tao**: The same way that if you're a software company and you want to roll out a thousand pieces of software, you don't really want to handcraft each one and learn lessons from each. You just want to find what workflows let you scale. The idea of doing mathematics at scale is at its infancy. But that's where AI is really going to revolutionize the subject.

</details>

**Dwarkesh**: 我觉得关于AI对科学有多大好处的这些对话中的一个症结是，我认为你提到了，它们正在使用现有的技术并对其进行修改。了解仅仅使用现有技术能取得多大进展会很有趣。如果我查看顶级数学期刊，有多少论文是在提出新技术，无论这意味着什么，而不是在新问题上使用现有技术？这种**悬而未决**（overhang）有多大？如果你只是将所有已知技术应用于所有开放问题，这会极大地提升我们文明的知识，还是不会那么令人印象深刻和有用？

<details>
<summary>Original English</summary>

**Dwarkesh**: I feel like a big crux in these conversations about how good AI will be for science is, I think you said this, that they're using existing techniques and modifying them. It would be interesting to understand how much progress one can make simply from using existing techniques. If I looked at the top math journals, how many of the papers are coming up with a new technique, whatever that means, versus using existing techniques on new problems? What is the overhang? If you just applied every known technique to every open problem, would that constitute a humongous uplift in our civilization's knowledge, or would that not be that impressive and useful?

</details>

**Terence Tao**: 这是一个很好的问题，我们还没有足够的数据来完全回答它。当然，人类数学家所做的大部分工作……当你面对一个新问题时，我们首先会做的事情之一是查看过去在类似问题上有效的所有标准方法，然后逐一尝试它们。有时这会奏效，并且仍然值得发表，因为问题很重要。有时它们几乎奏效，你必须再添加一个**小技巧**（wrinkle），这也很有趣。

<details>
<summary>Original English</summary>

**Terence Tao**: This is a great question, and we don't have the data to fully answer it yet. Certainly, a lot of work that human mathematicians do… When you take a new problem, one of the first things we do is we look at all the standard things that have worked on similar problems in the past, and we try them one by one. Sometimes that works, and that's still worth publishing because the question was important. Sometimes they almost work, and you have to add one more wrinkle to it, and that's also interesting.

</details>

**Terence Tao**: 但进入顶级期刊的论文通常是那些现有方法可以解决大约80%问题，但有20%难以解决，需要发明新技术来填补空白的论文。现在很少有问题能在不依赖过去文献的情况下解决，所有想法都凭空出现。这在过去更常见，但现在的数学已经非常成熟，不首先利用文献会是一个很大的劣势。AI工具在第一部分做得很好，即尝试所有标准技术来解决问题，而且在应用这些技术时犯的错误通常比人类少。

<details>
<summary>Original English</summary>

**Terence Tao**: But the papers that go into the top journals are usually ones where the existing methods can kind of solve 80% of the problem, but then there is this 20% which is resistant and a new technique has to be invented to fill in the gaps. It's very rare now that a problem gets solved with no reliance on past literature, where all the ideas come out of nowhere. That was more common in the past, but math is so mature now that it's just so much of a handicap to not use the literature first. AI tools are getting really good at the first part of that, just trying all the standard techniques on a problem, often making fewer mistakes in applying them than humans.

</details>

**Terence Tao**: 它们仍然会犯错，但我已经在一些我能做的小任务上测试过这些工具，有时它们能发现我犯的错误。有时我能发现它们犯的错误。现在差不多是平局。但我还没有看到它们迈出下一步。当论证中存在漏洞，没有任何方法奏效时，你该怎么办？它们可以提出随机的东西，但我发现追逐它们试图让它们奏效，却发现它们不奏效，浪费的时间比节省的时间还多。

<details>
<summary>Original English</summary>

**Terence Tao**: They still make mistakes, but I've tested these tools on little tasks that I can do, and sometimes they pick up errors that I make. Sometimes I pick up errors that they make. It's about a tie right now. But I haven't yet seen them take the next step. When there are holes in the argument where none of the things are working, then what do you do? They can suggest random things, but often I find that trying to chase them down to make them work, and finding they don't work, wastes more time than it saves.

</details>

**Terence Tao**: 我认为通过这种方法，我们目前认为困难的一些问题将迎刃而解，特别是那些没有得到足够关注的问题。在埃尔德什问题中，AI解决的50个问题几乎都是文献中基本没有涉及的问题。埃尔德什提出过一两次问题。也许有人随便尝试了一下，但没能成功，但他们从未写过任何东西。但结果表明，有一个解决方案，它只是将一种鲜为人知的**晦涩技术**（obscure technique）与文献中的其他一些结果相结合。

<details>
<summary>Original English</summary>

**Terence Tao**: I think some fraction of problems that we currently think are hard will fall from this method, especially the ones that haven't received enough attention. With the Erdős problems, almost all of the 50 problems that were solved by AIs were ones for which there was basically no literature. Erdős posed the problem once or twice. Maybe some people tried it casually and couldn't do it, but they never wrote up anything. But it turned out that there was a solution, and it was just combining this one obscure technique that not many people know about with some other result in the literature.

</details>

**Terence Tao**: 那就是AI能达到的中等水平，这真的很棒。它解决了50个这样的问题。所以我认为你会看到一些孤立的成功。但我们发现……有些人对这些埃尔德什问题进行了大规模的扫描。如果你只关注那些在社交媒体上广为传播的成功案例，它看起来很惊人。所有这些几十年没有解决的问题，现在都在迎刃而解。但每当我们进行系统研究时，任何一个问题，AI工具的成功率可能只有1%或2%。

<details>
<summary>Original English</summary>

**Terence Tao**: That's the median level of what AI can accomplish, and that's really great. It clears out 50 of these problems. So I think you will see some isolated successes. But what we found… Some people have done large-scale sweeps of these Erdős problems. If you only focus on the success stories, the ones that get broadcast on social media, it looks amazing. All these problems that haven't been solved for decades, now they're falling. But whenever we do a systematic study, on any given problem an AI tool has a success rate of maybe 1% or 2%.

</details>

**Terence Tao**: 只是它们可以大规模购买，你只需选择赢家。这看起来很棒。我认为在成百上千的真正有声望、困难的数学问题上也会发生类似的事情。一些AI可能会很幸运地真正解决它们，并且会有一些**后门**（backdoor）来解决其他人都错过的​​问题。这将获得大量的宣传。但随后人们会在他们自己喜欢的问题上尝试这些奇特的工具，他们将再次体验1%到2%的成功率。当它们工作时和不工作时，信号中会有很多**噪音**（noise）。

<details>
<summary>Original English</summary>

**Terence Tao**: It's just that they can buy scale, and you just pick the winners. It looks great. I think there'll be a similar thing happening with the hundreds of really prestigious, difficult math problems out there. Some AI may get lucky and actually solve them, and there will be some backdoor to solve the problem that everyone else missed. That will get a lot of publicity. But then people will try these fancy tools on their own favorite problem, and they will again experience the 1% to 2% success rate. There'll be a lot of noise amongst the signal of when they're working and when they're not.

</details>

**Terence Tao**: 收集这些真正**标准化数据集**（standardized datasets）将变得越来越重要。现在正在努力创建一套标准的挑战问题供AI解决，而不是仅仅依赖AI公司只发布他们的成功案例而不披露他们的**负面结果**（negative results）。这也许能更清楚地说明我们实际所处的位置。尽管我认为值得强调的是，AI已经取得了巨大的进步，模型能够应用一些没有人认为适用于特定问题的技术。

<details>
<summary>Original English</summary>

**Terence Tao**: It will be increasingly important to collect these really standardized datasets. There are efforts now to create a standard set of challenge problems for AIs to solve, and not just rely on the AI companies to only publish their wins and not disclose their negative results. That will maybe give more clarity as to where we're actually at. Although I think it's worth emphasizing how much progress in AI it constitutes already, to have models that are capable of applying some technique that nobody had written down as applicable to this particular problem.

</details>

**Terence Tao**: 这种进步既令人惊叹又令人失望。看到这些工具的实际应用，这是一种非常奇怪的感觉。但人们适应得也很快。我记得20年前**谷歌网页搜索**（Google's web search）刚问世时。它把所有其他搜索引擎都远远甩在后面。你在首页就能看到相关的结果，正是你想要的。这很了不起，但几年后，你就会觉得用谷歌搜索任何东西都是理所当然的了。

<details>
<summary>Original English</summary>

**Terence Tao**: The progress is simultaneously amazing and disappointing. It is a very strange feeling to see these tools in action. But people also acclimatize really quickly. I remember when Google's web search came out 20 years ago. It just blew all the other searches out of the water. You're getting relevant hits on the front page, exactly what you wanted. It was amazing, and then after a few years, you just took for granted that you could Google anything.

</details>

**Terence Tao**: 2026年水平的AI在2021年将会令人震惊。现在我们认为很多东西——**人脸识别**（face recognition）、**自然语音**（natural speech）、解决大学水平的数学问题——都是理所当然的。

<details>
<summary>Original English</summary>

**Terence Tao**: 2026-level AI would be stunning in 2021. A lot of it—face recognition, natural speech, doing college-level math problems—we just take for granted now.

</details>

**Dwarkesh**: 说到2026年的AI，你曾在2023年预测，到2026年，它将成为数学领域的同事？如果使用得当，它将是一个值得信赖的**合著者**（co-author）。

<details>
<summary>Original English</summary>

**Dwarkesh**: Speaking of 2026 AI, you made a prediction in 2023 that by 2026 it would be like a colleague in mathematics? A trustworthy co-author if used correctly.

</details>

**Terence Tao**: 回想起来，这看起来相当不错。

<details>
<summary>Original English</summary>

**Terence Tao**: Which is looking pretty good in retrospect.

</details>

**Dwarkesh**: 是的，我非常满意。那么让我们看看你是否能延续这一连胜纪录。你个人因为AI而生产力提高了两倍。你认为那是哪一年？

<details>
<summary>Original English</summary>

**Dwarkesh**: Yeah, I'm pretty pleased. So let's see if you can continue this streak. You personally are 2x more productive as a result of AI. What year would you say that?

</details>

**Terence Tao**: 生产力，我认为，并非一个一维的量。我确实注意到我做数学的风格正在发生很大的变化，以及我所做的事情类型。例如，我的论文现在有很多代码，很多图片，因为现在生成这些东西太容易了。

<details>
<summary>Original English</summary>

**Terence Tao**: Productivity, I think, is not quite a one-dimensional quantity. I'm definitely noticing that the style in which I do mathematics is changing quite a bit, and the type of things I do. For example, my papers now have a lot more code, a lot more pictures, because it's so easy to generate these things now.

</details>

**Terence Tao**: 以前需要我花费数小时才能完成的图表，现在我几分钟就能完成。但在过去，我根本不会在论文中放入图表。我只会用文字来描述。所以很难衡量两倍意味着什么。一方面，我认为我今天会写的论文，如果我没有AI辅助，肯定需要五倍的时间。但我不会那样写我的论文。

<details>
<summary>Original English</summary>

**Terence Tao**: Some plot which would have taken me hours to do, now I can do in minutes. But in the past, I just wouldn't have put the plot in my paper in the first place. I would just talk about it in words. So it's hard to measure what 2x means. On the one hand, I think the type of papers that I would write today, if I had to do them without AI assistance, would definitely take five times longer. But I would not write my papers that way.

</details>

**Dwarkesh**: 五倍？

<details>
<summary>Original English</summary>

**Dwarkesh**: 5x?

</details>

**Terence Tao**: 是的，但这些都是**辅助任务**（auxiliary tasks）。比如进行更深入的文献搜索或提供更多的**数值计算**（numerics）。它们丰富了论文。我所做的核心工作，即实际解决数学问题中最困难的部分，并没有太大变化。我仍然用纸笔来做。但有很多小事。我