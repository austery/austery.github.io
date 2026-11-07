---
author: AI Engineer
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ra8X7_bnujw
speaker: AI Engineer
tags:
  - ai-agent
  - eval-benchmarking
  - the-bitter-lesson
  - software-architecture
  - enterprise-ai
title: 黑石集团与 Norm AI CTO 对谈：AI Agent 落地、苦涩的教训与软件开发范式转移
summary: Norm AI CTO Scott Worley 与黑石集团 CTO John Stecher 探讨了企业级 AI Agent 落地策略。双方强调数据战略、直通处理（STP）和评估体系（Eval）在金融与合规场景中的关键地位，并讨论了“苦涩的教训”对技术路线的影响：在模型迅速迭代的背景下，评估投资回报率、容忍一次性内部应用并果断推倒重写已成为高效开发的新常态。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - John Stecher
  - Scott Worley
companies_orgs:
  - Blackstone
  - Norm AI
products_models: []
media_books: []
status: evergreen
---
### 开场介绍与企业级 AI Agent 的关注点

**>>**: 我是 Scott Worley，Norm AI 的首席技术官。今天非常荣幸能与黑石集团（Blackstone）的首席技术官 John Stecher 同台交流。据我了解，John 基本上同时承担着三份全职工作：负责黑石的所有技术业务，为其投资项目提供技术建议，同时还作为黑石被投企业在所有技术事务上的资源支持。我有遗漏什么吗？
<details><summary>Original English</summary>

>> I'm Scott Worley. I'm the CTO of Norm AI and I'm privileged enough to be sharing the stage here with John Stecher who's the CTO of Blackstone. Um From what I understand, John has basically three full-time jobs. It sounds like you've responsible for all of the technology at Blackstone, also advises on their investments and is as well as serves as a resource for the portfolio companies for all things technology. Did I miss anything?
</details>

**>>**: 没有，概括得完全准确。
<details><summary>Original English</summary>

>> Nope, all perfectly mapped.
</details>

**>>**: 这确实是一份很酷的工作。如果你还不熟悉黑石是做什么的，那大概是走错会场了。所以我就不展开介绍了。不过大家可能还不太了解 Norm 是做什么的。简单来说，Norm 是一家在法律和监管领域开展业务的 AI 公司。我们拥有一个企业级 AI 平台，目前已部署在全球一些规模最大的金融机构中；此外，我们还有一家关联律所 Norm Law，我们的 AI 平台也为该律所提供支持。

从去年年底到今年整整一年，所有人都在争相探索如何部署 AI Agent。现在我很想听听你在黑石是如何思考这个问题的，以及你们如何确保走在正确的方向上？
<details><summary>Original English</summary>

>> And so cool job. Yeah, and if you're not familiar with what Blackstone does, then you probably have wandered into the wrong conference. Um so I'm not going to go into that, but you may not know what Norm does. So really briefly, uh Norm's an AI company and we operate in the legal and regulatory space. We have an enterprise AI platform that's deployed in some of the largest financial uh institutions in the world and then we also have an affiliated law firm, Norm Law, and our AI platform also supports that.

Um so since the end of last year and certainly all of this year, everyone's been racing to figure out how to deploy AI agents. Now I'd love to hear how you're thinking about this at Blackstone and how you're trying to make sure you get this right.
</details>

### 数据战略、直通处理（STP）与工程效能

**>>**: 确实，随着技术的大幅进步，尤其从去年二三月份以来，这场竞赛就全面打响了。单从上下文窗口的扩大以及支持更长时间运行任务的能力来看，就已经让人们能够创造出更多的价值。

我们一直重点关注的一件事，也是我认为被投企业中每家公司在咨询和合作时都需要放在首位的，那就是要在 AI Agent 领域取得成功，首先必须理顺自己的数据体系。对于很多雄心勃勃拥抱 AI、希望构建尽可能多的 Agent 并迫切想要挖掘其价值的企业来说，我所见到的最大障碍和绊脚石，就是缺乏一个统一协调的数据战略：没能把数据从事务型系统中迁移出来，放入便于 Agent 访问、轻松管理与调用的平台，这样最终一定会失败。因此这是我们最关注的事情之一。作为一家大型资产管理公司，我们拥有海量的数据——自营专有数据与公开数据交织在一起。我们必须将这些数据移出原有系统，转化为能从 AI 角度充分利用的形态。

我认为第二点，虽然本质上与 AI 无关，但你可以利用 AI 去探索出最佳实现方式，那就是“直通处理”（Straight Through Processing, STP）依然至关重要。大家总把 Agent 当作世界上最核心的差异化能力来讨论，这常常让我感到惊讶。我自己在公司内部构建代码时，借助 factory 等多种工具，花时间让 Agent 协助我构思、理解人们现有的业务流程，但同时确保自己编写的代码能优化直通处理，然后在过去人类需要针对各种死记硬背的事务做决策的地方，用 Agent 注入所需的智能。这就是我每天花大量时间思考的两大核心要素。

而在 Agent 本身方面，最关键的是退一步去审视：我们希望构建 Agent 去更好地处理哪些工作，从而将我们的投资专业人士、财务专业人士和工程师的脑力周期解放出来，让他们去从事更高价值的工作？在软件开发生命周期（SDLC）中，编写功能测试用例、性能测试用例以及升级底层依赖库，往往是每个工程师的梦魇。做这行 27 年来，我对此深恶痛绝。而让 Agent 去完成这些工作，翻新我的代码和源代码，对于我们团队的交付速度起到了决定性的提升。那么，Norm 是如何考虑这个问题的？
<details><summary>Original English</summary>

>> Yeah, I mean I think the the race has definitely been on as like the technology has improved mightily uh since you know really like February, March of last year. Like just in terms of context windows being able to run stuff for significantly longer amounts of time have like resulted in people being able to produce just more value.

And one of the things that like we've been focused on a lot and I think every company in our portfolio advise on and work with all the time that they need to have top of mind for like being successful with AI agents in general is you have to get your data story right. And so like one of the biggest things, impediments, and tripping points that I see for companies out there when they want they're all in on AI, they want to build as many agents as possible, they really want to kind of extract value. If they don't have a cohesive data strategy that's moving stuff out of transactional systems into something that can be accessed and easily managed and recalled from like an agent perspective, it is going to fail. And so that's been one of the biggest things that we've been focused on you know as a big asset manager we have a ton of data proprietary data public data all woven together. We have to move that into out of systems into something that we can really leverage from an AI perspective.

I think the second thing that you know has nothing to do with AI but you can leverage AI to actually figure out how to do the best possible way is straight through processing still matters. I'm always shocked at how everybody just talks about like agents as being the biggest differentiator in the world. The thing that I've leveraged myself using factory and a couple other ways to go off and build code inside of the firm is like taking time having agents help to craft something for me understand the workflows out there that people are doing and then make sure that I'm like actually writing code to optimize for straight through processing and then using agents to inject an intelligence where necessary where humans were making decisions in the past for a variety of wrote work things. So that's really like the two key elements that I I spend a ton of time thinking about every single day.

And then the biggest thing from an agent perspective is really stepping back and looking at like what is work that we want to build agents to do better to offload like intellectual like cycles from our investment professionals our finance professionals our engineers such that they can do higher value work. And there's a ton of stuff when you think about in the software development life cycle writing test cases functional test cases performance test cases version versioning forward libraries underneath applications. It's the bane of every engineer's existence. I've hated it for 27 years that I've been doing this. Having an agent be able to go off and do these things for me and renovate my code and my source code has made all the difference in the world for the velocity that we deliver at. So how are you thinking about it at Norm?
</details>

### 从刚性工作流到 Agentic 架构与评测体系

**>>**: Norm 成立于 2023 年，大概是在 GPT-1 推出 3 年、或者说是 4 年之后，但比思维链（Chain of Thought）出现早了大约一年。所以在技术发展进程上，那是一个很有趣的时期。我记得我们第一次团队线下聚会是在斯坦福大学校园里呆了一周。尽管具体的具体时间线我可能记不太清了，但当时给人的感觉就像是上下文窗口突然从 4K、8K 跃升到了 128K，紧接着多模态就来了，所有东西仿佛一下子全涌现出来了。

随后，前沿技术发布有一段时间放缓了脚步。在 2024 年初，很多公司（包括我们自己在内）都在尝试把这些模型部署进业务工作流和生产软件中。于是我们在系统各个层面增加了大量的结构化设计。无论是从我们如何将内容输入并最终构建进模型的上下文（我们有非常具体的操作方式），还是在模型调用的编排顺序上，比如在检查一致性以及最终将内容提炼成有用输出方面需要采取哪些步骤，整个架构最终看起来就像是一个庞大的 MapReduce 系统。我们为 Agent 搭建了大量的脚手架，并且非常严格地约束模型的运行方式，它更像是一个死板的工作流。这确实让我们获得了高质量、高准确性，而且非常一致的输出，而一致性对身处监管领域的我们而言至关重要。

但在这个过程中发生了一件很巧的事：为了对这个庞大系统进行回归测试，我们积累了一套规模非常庞大的评估样本，实际上包含了数万个由专家手工标注的样例。因此，当后来明确证明 Agent 是切实可行的时候——我所说的 Agent，简单来说就是给大模型一个系统或一组可用工具，设定目标，并提供自我验证的机制，让它自行探索以最佳方式完成任务——我们就能直接拿这套基准测试集，迅速在新引入的 Agent 架构上运行。

这时我们见证了很多人都经历过的那个时刻：看着团队倾注心血写出来的几十万行代码，突然意识到其中绝大部分都已经过时了，甚至实际上成了阻碍。为了迅速跟进这一变化，我把工程领导团队召集起来，租了一辆 Sprinter 面包车开往纽约上州。那是在一场大雪之后，我们住进了一家 Airbnb，当时我们达成共识：“先暂时把 Norm 现有的东西抛在脑后。如果我们要从零开始，结合现有的认知，我们今天应该构建一个怎样的平台？”

闭门讨论后，我们形成了一整套规范，明确了这个新平台需要具备的两大能力：第一，为客户交付 Agent 驱动的体验；第二，使平台适于将 AI 作为协作开发者，与我们自己的研发团队并肩协作。从那以后，我们一直在这个方向上推进执行。

你有什么想问的吗？
<details><summary>Original English</summary>

>> Yeah so Norm was founded in 2023 so you know that's 3 year I guess 4 years after GPT-1 but still a year before there was like you know chain of thought. So it was like an interesting time in terms of development. I remember when we had our first team get together we were at Stanford's campus for a week and I mean, I'm probably misremembering the exact timeline, but it felt like we went from 4K to 8K to 128K context windows and then we had multimodal and everything just felt like it was kind of coming all at once. And then there was a bit of a time where things did slow down when it was coming from the frontier. And so I think like a lot of companies in like early 2024, you know, we were trying to deploy these models as part of like our workflow and as part of like our production software. And so we ended up adding a lot of structure to the system and and and this comes from you know, all different parts of the stack. So whether that was from like how we went and took the content that we knew needed to be like eventually added to context to the models and we had like very specific ways in which we did that or if there was like you know, just the sequencing of the models, if there was like steps we needed to do in terms of looking for consistency and then ultimately like distilling everything down into some useful output. We ended up with like something looked like a large like map reduce problem effectively, right? Whereas like we had a lot of scaffolding for the agents and we were very particular about like how these well, I would say it's really just how these models ran. It was much more like a workflow. And what this allowed us to do was get like really, you know, high quality and also with accurate very accurate, but also just very consistent, which is very important for us in the regulatory space outputs.

Um, but then one fortuitous thing as part of doing this cuz we wanted to have a some way to regression test this big system. We ended up with a really large set of evaluation samples. We had tens of thousands actually of like hand labeled examples by experts. And so as soon as we moved to a place where it was like clear that agents were actually a thing and by agents I simply mean you know, given like an LLM a system or given it a set of tools that it can use, give it some goal and give it some way to verify itself against that goal, allowing it just to go figure out how to do the thing in the best way possible. We were able to just take this benchmark set and just immediately run on top of it with some of these more agentic approaches and we saw, you know, I think a lot of people had this moment where you're staring at hundreds of thousands of lines of code your team had really thoughtfully written and realizing most of it was pretty obsolete and was just kind of actually in in

And so to update quickly on this, what we did was we um we took I got the engineering leadership team. We actually rented a a Sprinter van, and we drove to Upstate New York. It was actually after a big snowstorm. We had an Airbnb, and it was like, "Forget norm for a minute. Let's just say what would we build today as far as a platform, knowing what we know right now um if we were going to be starting over?" And then from that, we left with basically a set of specs about like what this platform needed to be able to do to enable two things. One, deliver agentic experiences to our clients. And then also um it needed to be amenable to having AIs like co-developers alongside of our own development team. And that's what we've been executing against uh ever since then. So, I think this Do you have a question?
</details>

### 高准确率诉求下的 Eval 核心价值

**>>**: 没问题，我想说的是，Scott，你恰好点出了一个关键问题，那就是你刚才提到的评估（Eval）。在金融服务行业，对 Agent 交付成果的质量门槛要求极高。因此，必须深入思考该使用怎样的评估集来对 Agent 进行基准测试，确保它们执行任务的产出合理、一致且可复现。我亲眼见过，只要底层模型版本一更新，得到的答案就会改变，返回信息的准确性就会出现偏差。所以拥有优秀的评估集，能够持续运行并真实衡量系统的健康状况，是成功的首要前提。同样地，如果底层运行的测试框架（Harness）发生变化，或者数据发生变化，结果也会不同。因此在金融服务领域，保证准确性的责任标准是极高的……
<details><summary>Original English</summary>

>> No, no. I was going to say, I think you hit on like a key point, Scott, which is like the eval side of the fence that you were talking about before. If you're working in financial services, like the the quality bar for what agents have to deliver on is very, very high. And so, I think really thinking through like what is your eval set for how you basically test your agents, what they're actually, you know, whatever work they're performing, that the output makes sense, and it's consistent and repeatable. And I've seen across the board as model versions change underneath the covers, you get different answers. You get skew in terms of the accuracy of information that comes back. So, having good evals so that you can run those consistently and really measure the health of a system is paramount to success. Same thing happens if harnesses change that you're running stuff on top of, you'll get different answers. Data changes, different answers. So, it's it's something where I think, you know, if you're trafficking in financial services, like the duty to be accurate is like
</details>

**>>**: *(轻笑)*
<details><summary>Original English</summary>

>> [snorts]
</details>

**>>**: 标准高高在上，如何达到这个标准是我们时时刻刻在思考的问题。
<details><summary>Original English</summary>

>> up here, and hitting that is like something like we think about all the time.
</details>

### “苦涩的教训”与算力演进

**>>**: 确实如此。这也顺理成章地引出了我们一直在讨论的“苦涩的教训”（The Bitter Lesson）这个概念。大家都对其很熟悉：那些由聪明人针对问题殚精竭虑打造的手工系统，往往最终都会被依靠算力扩展的系统所取代。Rich Sutton 最初在 2019 年阐述了这一点，但其实自神经网络诞生伊始就是如此。回溯到 20 世纪 50、60 年代 Rosenblatt 的感知机时期，《纽约时报》等媒体就曾报道称这是第一台能产生自主原创思想的机器。

历史上专家系统与联结主义之间的争论非常引人入胜，当时在英国甚至引发了激烈争论，导致许多 AI 研究被叫停。但一件有趣的事情是，回到 80 年代，IBM 翻译实验室的负责人曾说过一句非常契合“苦涩的教训”的话：“每当我解雇一名语言学家，我的模型表现就会提升”。雇佣语言学家苦思冥想语言规则，反而不如单纯基于概率去训练统计模型。

快进到今天，这种现象随处可见。我们在很多方面都触及到了这一点。我很想知道，在规划产品路线图以及团队成员向你提出项目构想时，你为黑石做技术决策时是如何把这个教训牢记于心的？
<details><summary>Original English</summary>

>> Definitely. I think this leads nicely into this concept that we've been talking about just like with the bitter lesson. So, like everyone's familiar with it, and you know, this is this idea that these hand-crafted um systems built by, you know, clever people thinking hard about the problem will often times eventually be dominated by systems that scale with compute. Right? And that this is actually I think Rich Sutton originally talked about this in 2019, but this has been since the beginning of neural networks. If you go back to like the '50s and '60s like with Rosenblatt's little perceptron, I think the New York Times ran an article or somebody did saying it was the first first machine that could ever have its own original thoughts, you know? And so and there was actually it's there's actually quite a fascinating history here of how the you know, expert systems and the connectionists and what ended up happening a lot of it actually was highly litigated in in England and a lot of AI research was dismantled, but one funny thing if you go back to the 80s even, there was a lead at IBM's translation lab and he made a comment, which is very much the bitter lesson, every time I fire a linguist my models improve, right? No, the point of having these like linguists in there and trying to think about all the rules of language versus like training a statistical model based on just probabilities. And so we speed up to today and like we see this all the time. We've been touching on lots of points about this and I'm curious when you think about your road maps, when people on your team are bringing you project ideas, like how do you keep this in mind as you're thinking about this for Blackstone?
</details>

### ROI 评估与“等待下一代模型”的技术决策

**>>**: 我们做的大量工作归结为一个简单的公式：只要给予足够的算力，未来任何问题在软硬件层面迟早都是可解的。埃隆·马斯克也从能源等角度谈到过这点。这是一幅宏大的蓝图，包含方方面面。但在现实中该如何落地？

从我作为 CTO 的视角出发，在与工程师、产品人员、SRE 团队和利益相关者沟通时，我投入大量时间去做的就是明确需求背后的投资回报率（ROI）。无论是构建 Agent、整理数据，还是开发仪表板、交易平台等，我都会评估团队提出的需求究竟能产生多大 ROI，以及在当下实际构建它所需承担的真实成本。我会权衡这个方程，然后做出决策：这是否属于模型性能即将大幅提升、6 个月后算力将绰绰有余，从而不值得在今天硬着头皮去攻克的领域？如果是，推迟开发、留待新一代模型来解决会是更好的选择。

我们以前确实做过这样的决定：宁可等待模型变得更高级再去解决这些问题，因为到那时成本会更低，而且当下构建该应用的需求并不紧迫，今天做出来相比 6 个月后做出来并不会产生实际的业务增量价值。这是我们经常面临并在深思熟虑后做出的权衡。

但另一方面，你也不能一味空等。如果总是等着新模型、新技术的出现，就什么也做不成。如今各类软件开发框架的妙处在于，只要你充分利用它们，从概念规划（比如用 Fable 与产品经理或业务方一起明确定义）到编写代码、再到做出可运行的概念验证（POC），速度之快令人惊叹。我所说的可运行概念验证，是指用户可以进行点击交互的系统。虽然它尚未通过网络安全审查，也没有我们在金融行业为了确保规模化生产部署所需的一切配套，但能极其迅速地形成 POC 或价值验证（POV）。

因此，我极力鼓励工程师经常做的一件事就是：尽快拿出 POC，不要纠结于写 PPT 或做无谓的繁文缛节。充分利用 Token——我认为在某种程度上斤斤计较 Token 成本是一种谬论，更应该关注的是创造价值。放手去创造价值、制作 POV，拿到用户面前快速迭代；如果不适用，果断扔掉。这样做所花费的时间和资金反而要少得多。这就是我们解决问题的重要思路。尽管这并未直接对应“如何应对算力增长让研发更容易”的长期议题，但思考的时间尺度更为敏捷和短期。
<details><summary>Original English</summary>

>> Yeah, I mean a lot of what we do is like, you know, simple equation is is giving enough compute every problem is solvable by like hardware and software at some point in time in the future. It's Elon talks about this energy-wise, etc. So it's like it's a big map, it's a whole bunch of stuff. How do you bring it back to reality? Like what I spend a lot of my time doing from like my seat working with engineers in my team, with product people, with our SRE function, with like stakeholders is really trying to define like, you know, what is the ROI of what I'm being asked to work on. And so like when I think of building agents, I think about you know, getting data into the right spot, think about building dashboards, trading platforms, whatever it is. It's like if I look at like what's the ROI that's going to be created from the actual ask that's coming in to me from a team perspective and then like what's the what's the true cost of actually building something today? Like how can I balance that equation and then I make a decision of like, you know, is this something where the models are going to get good enough? I'm going to have more than enough compute in 6 months that it's not worth trying to tackle the problem today. It's better to delay it and actually address it with one of the new models. We have made that decision before is like let's actually wait for the model to become slightly more sophisticated so that we can solve these problems with it because it will cost less at that time and the need for that application to be built today isn't pressing. There's no like real business value increase that can be like will be created because it's produced today versus 6 months from now. So, that's a trade-off that we actually, you know, make regularly and I think about regularly.

Um the other thing that we do is like you don't want to wait too long to basically build something. And so, you can always be waiting for the new model, waiting for the new technology, or whatever else. Like the beautiful thing with like all of the various different software development harnesses today is if you lean into them, it's amazing how quick you can go from like concept, mapping out your planning and concept with like Fable for like, you know, just hey, work with me and let's define this with the product person or with the stakeholder to actually writing code to having it like a workable proof of concept. And when I say workable proof of concept, it's something people could click through, interact with, whatever else it is. Doesn't have cybersecurity review, doesn't have all the other things that you need to do in our industry to make sure you like put something into production that scales, but you can get to a POC or a POV very quickly. And so, like that's one big thing I try to encourage all my engineers to do frequently is like just get to POC. Don't worry about PowerPoints, don't worry about anything else. Leverage tokens, which like I think it's a fallacy to be like counting tokens in some way, shape, or form. It's better to think about producing value. Go off, produce value, produce POVs, put it in front of people, iterate on it quickly, and throw it away if you don't need it. You will spend far less time and money doing those types of things. And so, that's like a big way that we think about trying to solve it. It doesn't maps into the parallel like the you know, the how do you deal with increasing compute, making it easier to do these things, but like I just I think in a much shorter time frame.
</details>

### 通用能力的涌现与“导管”型架构设计

**>>**: 很有意思，你触及了很多人都在思考的核心问题。回溯到 2023 年，我们团队刚坐在一起讨论要构建什么时，其实就已经意识到了“苦涩的教训”，并思考过“如何避免踩进这个陷阱”。如今在我看来，这显然是一个渐进的光谱，并非非黑即白的二元抉择，不存在某种可以一劳永逸吸收前沿进展且完全无需推倒重来的完美架构。

归根结底在于：哪些地方我们希望大力投资，哪些地方采取保守投资？正如你所说，我们当下需要可用的系统，但同时心知肚明某些投入可能很快会过时。我们围绕 Agent 的底层原语构建了相当复杂的系统，例如测试框架、沙箱环境、数据导出机制等等。我们也希望确保在前沿实验室或第三方推出新成果时，系统能够顺畅吸收。因此，核心挑战往往在于“何时更新认知”。

对我而言，一个深刻颠覆认知的典型例子就是 Claude Code。倒不仅仅是因为它提供了可在本职工作中使用的工具，而是它消除了我此前对“如何实现真正通用化”的怀疑。Claude Code 带来了什么？它不仅能编写代码，还能执行代码，相当于以可验证的方式运行一台计算机。在那一瞬间我意识到，实现真正通用智能的要素已经齐全了；如果能规模化做到这一点，几乎所有知识工作（乃至我们今天看到的部分非知识工作领域）都能胜任。如今人们使用的各类 AI 助手也是如此，面对前所未见、完全分布外（Out-of-Distribution）的问题，它可以在后台启动一台计算机去执行操作。这在消费级场景表现惊艳，如今也正在企业级场景落地。

这一瞬间让我明确了投资重点：除了继续投入 Agent 侧的构建，正如 John 提到的，更要重点投入数据的采集、提炼，以及如何将其作为状态提供给模型，同时全力打造基准测试与评估体系。以我们的关联律所为例，律所与 Norm 是一同从零成长起来的。我们直接与律师合作建立评估基准。相比于传统的路线图（比如“何时能做一个具备这三项功能的 Agent”），我们建立了一套评分卡，用来衡量 Agent 甚至人类在各项维度上完成任务的成功率，并观察系统随着时间推移的整体进步。只要对底层系统做出通用性改进，律师就能看到工作流效率的提升。同时这也避免了重蹈覆辙——回到我们最初层层包裹复杂结构的老路上，因为我们后来发现，如果去掉那些前置结构，反而能获得更好的表现。
<details><summary>Original English</summary>

>> Yeah, it's so interesting cuz it's like, you know, I mean, you touched on so many things that I think everybody's probably been thinking about, too. And if you go back to 2023 when we were originally like sitting around as a small group talking about what we're building, we were aware of the better lesson then. We talked about it. We said, "How do we not get in this trap?" And I think at this point, it's just really evident to me that it's like it's definitely a gradient, right? It's not this binary thing about you can somehow build the perfect technology to index into all the up you know, everything coming in from the frontier in a a that you don't have raft to throw things away.

really it gets down to like where did we want to invest heavily and where are we willing to invest conservatively because like you said, we need something today, but at the same time we're just aware that like some of these investments we make particularly around things like we've built, you know, fairly complicated systems around all of our agent primitives. So, the harness, the sandbox, how egress works, you know, all of these things and we we also want to make sure that as like things are coming out either from like a frontier lab or from like a a third party that we're able to index into that. And so, I think a lot of it is just kind of when do you update? And I that's one of the hardest things to do and I like for me a good example was I really updated really hard on cloud code. Not so much that it was suddenly tools that like in my profession that we could use that were really incredible. What it really was for me was just this idea cuz I was a bit skeptical up to that point of how we would get something that was like truly generalizable. It's like, well, what does cloud code give you? Well, you can write code and then it can execute the code and like we're basically running a computer in some verifiable way. At that moment, I was like, well, we have all the ingredients for like a truly generalizable intelligence because if you can go do this at scale, then I mean, you know, of course like you can basically do anything in terms of most knowledge work and actually even outside of knowledge work, which we're seeing some today. And you fast forward to now and like all these tools that people are using these like AI assistants and things, this is why they're so amazing. It's cuz you can ask a question that's never seen before fully out of distribution. It can spin up a computer and go do this thing in the background. And for consumer, it's amazing and then we're also seeing this now within the enterprise, too.

And so, for me that moment was like, well, where are we going to invest heavily? Of course, we still need to invest in what we're building on the agent side, but going back to what uh John mentioned, how we do our data capture and distillation and how we make this available as like state to these models. And then also just how we do our benchmarks and evaluations. It's And so, with like the law firm for example, we have this really unique situation where we started this law firm, um you know, from nothing. So, we we've kind of grown together, they've grown with Anom together. And so, we work directly with lawyers to develop to stand up these benchmarks and evaluations. And effectively, rather than think of a traditional road map, like when when are you going to build an agent that can go do these three things? It's let's have a scorecard that determines when an agent or when a human even is has success is successful at completing these tasks across the various dimensions. And then we want to be able to see this system improve over time. So, as we make general improvements to the system, we should see an uplift to these, you know, these things like an attorney would expect to improve their workflow, but at the same time not not getting kind of going back to the state that we were originally where we had added a lot of structure to it in a way that ultimately we found that we were actually we could get even better performance if we were to remove that up front
</details>

### 企业级落地的硬骨头：基础设施、合规与可观测性

**>>**: 结构。没错。另外必须看清的是，虽然现在产出概念验证（POC）或价值验证（POV）非常快，但对于大部分研发工作而言，真正艰难的硬骨头依然是推进到生产环境。我指的是构建能够在金融服务机构乃至任何大型企业既有基础设施中稳定运行的底层架构。这是一个被许多人严重低估的挑战。如果你是向企业销售 AI 工具的厂商，你会发现买方的落地难度极高，我日常工作中就经常处理这类问题。

另一个难题是网络安全与系统可支持性。虽然 Agent 在这方面有所进步，但仍需确保生成的软件真正具备可追溯性，并能接入 SRE 平台，从而在生产环境中实现全面监控。这些依然是我希望大家深入思考的问题。在 Agent 辅助下，这些领域目前尚未开始规模化解决，虽然未来一定会实现，但现阶段仍是我日常重点考量的事情。
<details><summary>Original English</summary>

>> structure. Yeah. I think like another thing that's important to think through is like you can produce, like I was saying, a lot more proof of concepts, proof of value very quickly. I still think like the hard yards for a lot of development out there is getting it to production. And what I mean by that is like infrastructure buildout that actually runs inside of the infrastructure that's available inside of any financial services or enterprise company for that matter out there. Like that is a challenge that a lot of folks like underestimate. If you're selling AI tools, it's that is hard on the other side, just so you know, I deal with it quite a bit.

The other thing is is just like dealing with like the cybersecurity side of the fence and the supportability side of the fence. And so like one thing I've noticed, you know, the agents are getting better at this now, but it's making sure that the actual software that's being written is truly traceable and it feeds into your SRE platform so that it can be monitorable in production. Those are things still that like I like to have people think about. It's like they haven't started to scale yet with agents. They will, but it's something that from my perspective I think about regularly.
</details>

### 核心原语的人工把关与“用完即弃”的软件资产观

**>>**: 很有道理。我们的应对方法——相信很多其他公司，甚至包括你们可能也是这样做的——就是在代码库中保留一部分必须完全由人工监管的区域，涵盖架构设计、构建、代码归属权，乃至对任何代码变更的最终审批。这些就是我们的核心原语（Core Primitives）。你可以在这些原语之上构建上层功能，但上层应用在未经人工审查的情况下绝不允许擅自修改底层核心系统。

这正是基于你刚才提到的原因：对我们而言，数据安全不仅和交付速度同等重要，甚至更加优先。面对高度敏感的数据，我们必须搭建全套的基础设施保障，确保绝不在这些核心技术栈上盲目冒进。这有时会很纠结，因为可能会有人向你展示一个非常炫酷、令人兴奋的 Demo，但你看了之后可能会感到不寒而栗，心想：“这确实很棒，但若要在生产中达到这种能力，会暴露太多我们目前尚无法承载的安全风险。”

所以这永远是一种权衡。我们选择在核心原语上大力投资，而在那些随着前沿模型演进而容易过时的领域保持审慎投资。我们希望保持通道畅通。正如我今天早上向团队描述的那样：“在整个平台中，我们要为来自技术前沿的创新铺设‘导管’（Conduits），而不是筑起‘大坝’（Dams），以免外部前沿智能涌入时因为你的架构设计不当而无法被底层技术栈吸收。”同样，这是一个渐进的过程，我们难免会有判断失误或成功的地方。关键在于保持清醒认知并充分沟通，锁定核心模块，同时对“推倒重来”持完全开放的心态。

我觉得大家现在都越来越适应这一点了。从事软件开发 27 年来，有时觉得像过了 100 年，有时又觉得只过了 5 年。如果对比今天与 10 年前的软件开发模式，最根本的变化在于：10 年前开发一款软件需要耗费大量的时间、精力和资金，凝结了巨大的智力资本。那就像木已成舟、船已出海，从你完成设计并开始编写代码那一刻起，这艘船就必须尽可能远航，直到抵达大洋彼岸。

而如今我已经非常习惯于：绝大部分内部应用基本上都可以用完即弃。构建它们、让它们在特定时间点发挥特定作用，同时坦然接受它们会以远快于以往的速度被淘汰，然后着眼于下一步。因此，无论是我还是优秀的工程师，核心挑战在于不断反问自己：“我是该重写它，还是重写的成本已经低于持续升级现有版本的维护成本？”十年前任何人的脑海里都不会冒出这种问题。如果你当年说要重写一个内部系统，CFO 会觉得你疯了。但放在今天，这已经成为所有人都应认真践行的合理路径，因为重新开发出的全新应用最终可能带来大得多的业务价值。这是我鼓励大家去做的，听起来你们在 Norm 也实践得非常深入。
<details><summary>Original English</summary>

>> Makes sense. And we our approach to this, I'm sure a lot of other companies and maybe even you guys have taken this approach as well, is there's parts of our code base that we like still require like complete human oversight from when it comes to designing, building, code ownership, even approving any kind of changes to the code base. And these are like our core primitives. And these are things where, you know, basically you can build things on top of these, but the things you build on top of these are not allowed to like change these systems without having like human review. And it's because of things you mentioned is like, you know, data security for us is, you know, is is is like as paramount as delivering quick. It's actually more important. So, and for depends on where you are and if whether it's a consumer product or for us with obviously working with highly sensitive data, like we have to build in so much infrastructure around this and ensure that we're not ever getting out ahead of like, you know, these parts of the stack, which it can be hard cuz maybe somebody brings you and I'm sure you've seen this like a really cool demo and it's really exciting and you're looking at it terrified cuz we're like, "This is the This is very cool, but to get to this point in terms of capabilities, like it would expose so much that we're not able to do yet." So, I think it's just always that trade-off.

So, we just, you know, basically we invest heavily in these things and then invest conservatively in places where we realize as the frontier continues to improve, um we want to make sure we do we have like conduits. The way I described it actually this morning with the team was like, "Basically throughout our platform we want to have like conduits for what's coming from the frontier. You don't want to have dams where like the intelligence is coming in and it can't quite get into your stack because you built things in such a way." Again, it's a gradient. We're going to get some of it wrong, some of it right. Just being very cognizant of it, talking about it a lot, and making sure that our core pieces are are locked down, but then also, you know, being very open about um just ripping and replacing. I think that's like a thing that I think everybody's gotten really good at.

I I think that's like one of the biggest I mean I like I I've been doing this for 27 years. Sometimes I feel like it's been like 100 years. Other times I feel like it's been five. I think the the thing that's like really made a material difference like when I I look at the ability to write software today versus what I was doing 10 years ago was 10 years ago it took so much time, effort, and money, and people's like intellectual capital to produce a piece of software. It was almost like the ship had sailed. Like by the time you designed it and started writing code, it was out to sea and you were going to ride that baby for like as long as you could until it got to the other side of the ocean. And like what I've become very comfortable with today is like for the most part a lot of like internal applications can be just thrown away. It's build them, have them work for a purpose in a point in time, but understand that they're going to disappear at some point in time a lot now much more quickly than ever before, and then just think about like what comes next. And so I I think one of the challenges with like sitting in my seat or any like good engineer seat should be constantly questioning like, you know, should I rewrite this and does it cost me less to rewrite it than it cost me to keep versioning the current version forward? And that is like a question that a decade ago never would have came up in anyone's head. If you went to say I want to rewrite an internal application, like your CFO would have looked at you like you were insane. And I think now it's a completely relevant thing that all of us should be doing cuz net new applications might produce way more business value at the end of the day. So, it's just something that I encourage folks to do. It sounds like you guys are doing quite a bit at Norm.
</details>

### 总结与展望：工程本质的回归

**>>**: 没错，正是这种“过去昂贵的东西如今变得极为廉价”的观念转变。如果不快速更新认知，就会掉队。正如你所感慨的，感觉像过了 27 年、5 年还是 100 年，如果你过度拘泥于 6 月份的技术范式，到了 10 月份，可能技术已经发生了相当于过去 10 年的飞跃。

好的，我们只剩大约一分钟了。最后你有什么想向大家分享的结语吗？
<details><summary>Original English</summary>

>> Yeah, exactly. And I think it's just that concept of what used to be expensive that's now cheap. And if you don't update quickly on that, then it's, you know, it like you it's incredible you said it feels like 27 or 5 years or 100 years or 5 years. It's like that if you over if you over index too hard on something that was in June and now it's October, like, you know, it it feels like in some ways there's been like 10 years of technological advancement. So, um Well, great. We only have a minute or so left. Are there any closing remarks you
</details>

**>>**: 我觉得最后留给听众的一个核心收获是：我们讨论了许多前沿话题，而最让我每天充满工作激情的，是重回工程本身的纯粹乐趣。我很看重的一点是，我早年在 IBM 做了 10 年硬核的底层工程师，在那个远古时代用记事本和 VI 针对 RISC 机器编写指令级代码。那段经历虽然极其硬核 Geek，但对我而言乐趣无穷，至今仍让我怀念。

随着职业资历越来越深，日常写代码的门槛往往变得越来越高，比如处理流式数据时由于繁重的脚手架配置让人望而却步。而 AI 的出现让人重新焕发了亲手构建系统的活力——因为我们从未丢失系统架构设计的沉淀。我看到很多入行 10 年、20 年、30 年的资深工程师，他们对系统设计复杂度的理解始终没有变，而现在他们终于能够借助这些出色的 Agent 将这份深厚认知转化为现实产出。

因此，无论对于创业还是在企业内构建软件，这都是一个令人无比振奋的时代，因为展现在我们面前的是一个可以去尽情创造的全新世界。这就是最让我感到激动的地方。
<details><summary>Original English</summary>

>> I mean, I think like the the one thing I'd like leave the audience on if you if you want like, you know, like good takeaways from this, it's like we talked about a lot of like very interesting things. I think like what makes me like excited to go to work is like it's cool to get back to engineering. One of the things that like I value is like, you know, I was a hardcore low-level engineer for 10 years at IBM and like wrote like, you know, this is way back in the day of using notepad and VI to write like instruction level code for RISC machines. It was like awesome. It's nerdy as all heck. No one does this stuff anymore, but it was like fun for me. I still enjoy those days. As you get more senior in your career, it like the barrier to actually writing code on a daily basis disappears or it becomes more like hard to get through like dealing with a stream like processing stuff off a stream. It's just all these things are like, oh my god, I can't even get started cuz the scaffolding is so hard. With like AI, it's been like reinvigorating to get back and actually build stuff cuz it's like I never lost my knowledge on how to architect things. I see this with a lot of engineers out there. They understand because they've been in the market 10, 20, 30 years. They understand the complexity of system design which hasn't changed and now they can actually express that knowledge with these new cool agents. And so I think it's a super exciting time to be like starting a company, working at a company and like building software cuz there's like a whole new world that we can create out there. So that's what like excites me. So
</details>

**>>**: 非常感谢，荣幸之至。
<details><summary>Original English</summary>

>> well thank you so much. It's been an honor.
</details>

**>>**: 好的，感谢大家今天邀请我们来到这里，非常感谢。
<details><summary>Original English</summary>

>> Yep, thank you guys for having us here today. I appreciate it.
</details>