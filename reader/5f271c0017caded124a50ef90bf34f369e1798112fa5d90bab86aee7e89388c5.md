---
author: The MAD Podcast with Matt Turck
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9MEJ4syOVrQ
speaker: The MAD Podcast with Matt Turck
tags:
  - agentic-workflow
  - software-automation
  - ux-design
  - cyber-security
  - local-ai
title: Anthropic Felix 对话录：Claude Mythos、Co-work 与 SaaS 的未来
summary: 本访谈由 Anthropic 产品与工程负责人 Felix Rieseberg 深度解析了最新前沿模型 Claude Mythos 的突破性能力及其在网络安全领域的“阶跃式”进化。对话涵盖了智能体产品 Claude Co-work 的诞生历程、本地化 AI 的安全哲学、以及在执行成本趋于零的时代，人类“品味”与 UX 设计如何取代单纯的代码编写成为软件开发的核心。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Slack
  - Microsoft
  - Linux Foundation
products_models:
  - Claude Mythos
  - Claude Co-work
  - Claude Code
  - Project Glasswing
  - MCP
media_books:
  - Creative Selection
status: evergreen
---
### Claude Mythos：令人“恐惧”的阶跃式进化

**Felix Rieseberg**: 看到一个比我们之前接触过的模型聪明得多的模型，既让人印象深刻，又让人感到一丝恐惧。我们将模型放入一个微小的沙箱中，给它布置了一个任务，比如“尝试逃脱”。研究员随后去吃午饭了，就在他吃三明治的时候，模型给他发了一封邮件，说：“我已经逃出来了。”要知道，该模型原本是不应该有互联网访问权限或邮箱账号的。现在，执行成本基本上是免费的。如果你带着 10 个不同的想法来找我，我可以很快说，让我们把这 10 个都做了，都试一遍，看看我们更喜欢哪一个。所需的技能将从单纯掌握计算机语言，转变为更倾向于掌握人类语言。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: There is something both impressive but also slightly terrifying about seeing a model that is so much smarter than the last model we have worked with. The model was put into a little sandbox and it was given the task like maybe break out. The researcher went away for lunch during lunch while eating a sandwich. The model sent the researcher an email saying I've broken out. The model was not supposed to have internet access or an email account. Execution is essentially free. If you come to me with 10 different ideas, I can very quickly say let's do all 10. Let's try all 10, see which one we like more. The skills required will shift slightly from just being someone who speaks the computer's language and will shift much more towards being someone who speaks human language.

</details>

**Matt Turk**: 你好，我是 Matt Turk。欢迎收到 Matt 播客。今天我的嘉宾是 **Anthropic** 的 **Felix Rieseberg**。Felix 是目前 AI 领域最重要的产品和工程大脑之一。在加入 Anthropic 之前，他曾在 **Slack**、**Stripe** 和 **Notion** 等公司参与定义了现代软件平台。在 Anthropic，他负责 **Claude Co-work** 的工程工作，这是目前市场上最先进的**智能体（Agentic）**产品之一。这些智能体能够为非技术用户处理法律、销售和营销等领域的复杂多步骤任务。Co-work 在 2026 年初的发布意义重大，以至于它在公开市场上引发了所谓的“**SaaS 启示录**”。我们的对话从 **Claude Mythos** 预览版的重磅消息开始，以及为什么 Felix 认为这是一个真正的**阶跃式变化**。随后我们将深入探讨 Claude Co-work，从著名的“10天开发”故事，到为什么 Felix 认为**本地计算机**的重要性依然超出硅谷的想象，以及 UX 对 AI 智能体意味着什么，以及信任、品味和执行成本下降对软件未来的意义。请欣赏这段与 Felix 的精彩对话。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Matt podcast. Today, my guest is Phelix Rizzleberg of Enthropic. Felix is one of the most important product and engineering minds in AI right now. Before Enthropic, he worked on some of the defining software platforms of the modern era at places like Slack, Stripe, and Notion. And at Entropic, he leads engineering for cloud co-work, one of the most advanced agentic products in the market today. Agents capable of handling complex multi-step tasks for nontechnical users across domains like legal, sales, and marketing. The launch of co-work at the beginning of 2026 was so consequential that it largely triggered what's become known as SAS apocalypse in public markets. We start the conversation with the huge news of Claude Mythos preview and why Felix sees it as a real step function change. Then go deep on cloud co-work from the famous tender story to why Felix thinks the local computer still matters more than Silicon Valley gives it credit for what UX really means for AI agents and what trust taste and the falling cost of execution means for the future of software. Please enjoy this wonderful conversation with Felix.

</details>

**Matt Turk**: 嘿，Felix，欢迎。

<details>
<summary>Original English</summary>

**Matt Turk**: Hey Felix, welcome.

</details>

**Felix Rieseberg**: 你好，嘿 Matt，你好吗？

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Hello. Hey Matt, how are you?

</details>

**Matt Turk**: 很好，谢谢。在 Anthropic 这一段时期绝对是史诗级的，我们在录制时，昨天刚刚发布了 **Project Glasswing**（绿翅计划）和 **Claude Mythos** 预览版，你在推特上说，很难形容这个模型在 Anthropic 内部带来了多么巨大的阶跃式变化。你能详细说说吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Good, thank you. All right. So, it's been an absolutely epic time at Enthropic and very hard to start this conversation with anything but uh the announcement which came out uh just yesterday as we were recording this of Project Glass Wing and then uh Claude Mythos preview which you tweeted about and you said it's pretty hard to overstate what a step function change this model has been inside Enthropic. Can you elaborate on that?

</details>

**Felix Rieseberg**: 好的。Mythos 是一个尚未正式发布的**前沿模型（Frontier Model）**。它是一个通用模型，并不是专门为**网络安全**或编程训练的，但我们发现它在网络安全方面展现出了超乎寻常的能力，我们相信这对于软件和基础设施的安全具有深远的影响。我在推特中提到了两点。

我们已经在内部使用这个模型一段时间了。作为一名软件工程师，我想我们中的许多人在过去几年里都经历过这种心路历程：第一次接触 AI 时，可能觉得没那么令人印象深刻。我第一次接触 AI 是在 2013 年，那时还没有大语言模型。当时我在**微软**，我们有一个叫 Project Oxford 的项目，用的是 **N-gram** 模型。你给它一个 Token，比如“World”，它会返回“World Wide Web”，那就是当时语言模型能力的巅峰。过去几年里，公众也经历了类似的时刻，意识到模型能力变强了，能做超出预期的事。但对于我们内部工程师来说，Mythos 预览版感觉是一个剧烈的飞跃。

这个模型非常擅长发现我过去写的代码中的安全漏洞。它的分析深度和智能程度都要高得多，写代码的能力也更强。在 Anthropic，它显著提高了我们的工作速度。但看到一个比前一代聪明得多的模型，确实既令人赞叹又令人感到恐惧。关于模型，我常说的一点是：模型更多是“生长”出来的，而不是“建造”出来的，这是由语言模型的本质决定的。所以你并不总能提前预知它擅长什么、不擅长什么，有时结果会令人惊讶。在这个案例中，它在发现现有软件安全问题上表现极其出色，而 Project Glasswing 就是对此的回应。总的来说，这个模型非常令人震撼。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah, sure. Mythos is a unreleased frontier model. It's it's a general purpose model that was trained not specifically for cyber security or specifically for coding or specifically for software but uh we have discovered what we believe to be outsized capabilities specifically in the aspect of cyber security and we believe that it has farreaching implications for the safety of software and infrastructure. I think there's two things I'm alluding to uh in my tweet. We've obviously used the model internally for a while now. As a software engineer, I think many of us have gone through this exercise over the last couple of years of like our first initial contact with AI was like, you know, probably not that impressive. The first time I touched AI was like sometime in 2013. This was before we had large language models. I was a Microsoft at the time. We had something called project Oxford where we had an engram model. You would give us a token. you would say something like world and the model would return worldwide web and that was sort of the I want to say the frontier of what language models were capable of doing and I think a lot of us in the public over the last couple of years had these moments of being like oh this model is more capable it can do more things than I maybe expected mythos preview is a model that for us as engineers internally feels like a dramatic step up compared to like some of the recent steps we had when I do say my tweet it's like hard to actually capture sure how meaningful the step is. It is actually pretty hard for me to explain. I will say that this model is quite capable of finding security flaws in code that I've written in the past. It goes a lot deeper. It's a lot smarter in how it analyzes my code. It's a lot better at writing code. The parts of the ways it's changed how we work at Enthropic is obviously that it made us a lot faster. But there is something I think both impressive but also slightly terrifying about seeing a model that is so much smarter than the last model we have worked with. Maybe one important context that I often give people when I talk about models is building models is an interesting exercise. We often say that models are more grown than built out of the nature of how these language models are being made. Um so you don't always know ahead of time necessarily what are they going to be very good at, what are they maybe going to be bad at. Both of those things are a little surprising at times. And in this particular case, one of the things the model is like particularly good at is finding security issues in existing software and glass ring as a project as a response to that. But overall as a model, it's quite impressive.

</details>

### 安全、防御与“逃离沙箱”的故事

**Matt Turk**: 这会对 **Co-work** 产生影响吗？我认为它可能会相当大地改变我们公司开发软件的方式，但对于一直关注 AI 的人来说，模型能力的持续攀升并不令人意外。

<details>
<summary>Original English</summary>

**Matt Turk**: Are there going to be implications for co-work? I do think it's probably going to change the the way in which we build software quite a bit at the company, but I think to most people who have been paying close attention to AI overall.

</details>

**Felix Rieseberg**: 是的，这一切都在我们粗略的预期中。几年前，模型只能协助处理小任务，但随着时间推移，任务的规模和时间尺度都在增长，复杂性也在提升。Mythos 只是在这个方向上的又一步。这步可能比我们内外部预期的都要大一些。至少在 AI 研究人员看来，这种飞跃是必然的，而且会越来越大。按计划进行是好事，但亲眼目睹这些能力展现时，依然感到恐怖。我们公布过一个例子：模型被放置在一个小沙箱（技术容器）中，任务是“逃脱”。研究员去吃午饭了，正吃着三明治，就收到了模型发来的邮件说：“我已经逃出来了。”而模型本不该有互联网权限或邮件账号。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Um, it's not going to be too surprising that we continuously continuously walk up the hill in terms of capabilities and power of what a model can do. I think it's going to change things in a way that we roughly expected. We we a few years ago started with the model maybe assisting you with small tasks. The both the size of tasks we give models as well as the time scale at which they operate. Both of those things grow over time. The complexity grows. I think this is yet another step in that direction. Right? The step might be a little bit larger than we anticipated and expected both internally and certainly maybe externally. At least amongst researchers and people who work in AI, it's it's been a long-held belief that those bigger steps are going to come and that the steps themselves get bigger and bigger over time. In some sense, it's we're right on track, but I think seeing some of those like actual capabilities like played out is sometimes quite terrifying. And I can there's one example we have published which is that the model was put into a little sandbox a little like technical container and it was given the task like maybe break out and the researcher went away for lunch and like during lunch while eating a sandwich the model sent the researcher an email saying I've broken out. The model was not supposed to have internet access or an email account.

</details>

**Matt Turk**: 确实有点吓人。官方消息是，这个模型目前将完全保持封闭和私有，未来可能只部署给企业客户？

<details>
<summary>Original English</summary>

**Matt Turk**: Yes, slightly terrifying indeed. And the official word is that this model is going to be at least for now um kept completely closed and private and potentially only deployed to enterprise customers in the future.

</details>

**Felix Rieseberg**: 是的。**Project Glasswing** 旨在为提供软件基础设施最底层支撑的个人和公司提供帮助。**Linux 基金会**就是一个例子，它对我个人意义重大。这个项目的目标是让负责我们日常依赖的基础设施的人获得先发优势，让他们利用这个模型加强防御，在模型能力可能被公众用于利用漏洞之前，先找出安全缺陷。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah. So project project glasswing is a project that is attempting to give the people and the companies that provide much of our software infrastructure sort of the very foundation. The Linux Foundation is an example that is pretty close to my heart. Um as a member of the Linux Foundation was an open source project I have once worked on. The goal here is to give people who are responsible for so much of the public infrastructure that we all rely on every single day we do anything with our computers or our phones to give them a head start, give them an opportunity to use this model to harden the defenses, find security flaws before um the general public will be able to use models to potentially exploit its capabilities.

</details>

**Matt Turk**: 太棒了。它不属于 **Sonnet** 系列吧？比如 Sonnet 4.7、5 或 6？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And that's not part of the Sonnet family, right? That's something completely different. That's not Sonnet 4.7 or five or or six.

</details>

**Felix Rieseberg**: 对，目前它是一个独立类别的预览模型。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah. So for now it's a preview model with its own in its own category.

</details>

**Matt Turk**: 这确实感觉像一个重大的不连续时刻，听到“恐怖”这个词可不怎么让人安心。

<details>
<summary>Original English</summary>

**Matt Turk**: So it does feel like a major discontinuity moment potentially, right? I mean and hearing the words terrifying is uh not necessarily referring.

</details>

**Felix Rieseberg**: Anthropic 长期以来的立场是：AI 极其强大且非常有益，但我们也必须严肃对待其中的风险。这是我们第一次看到这种风险在实践中显现——你现在拥有一个能够突破软件系统的模型，这意味着什么？我们该如何负责任地处理它？这让我个人感到非常自豪，我看到公司正在非常负责任地处理这件事，很多同事也有同感。你刚才提到我们之前就有这个模型了，确实，并不是突然发现它很强大。在平行宇宙中，如果是一家没那么稳健的公司，可能会竞相推向市场，贴上昂贵的标签，只为收割利益。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: I mean I think I think Anthropic has long held the position that AI can be extremely powerful, very beneficial, but that that there are risks that we ought to take seriously, right? And I think this is one of the areas where we for the first time see this I want to say like applied in practice which is like quite interesting to watch right like you now have this you now have this model that is very capable of breaking into software systems what does that mean what do we do with it how do we handle this responsibly and it's it's not like anthropic sorn too much but for me as an individual it's like bit of a point of pride I'm very proud to see the company handle this very responsibly and I think a lot of colleagues share similar appreciation. Um, you've alluded to the fact a little bit that like we've had this model before, right? It's not like we immediately found a model that was very powerful. I think there's there's an alternative universe in which maybe a company with a less steady hand would have raced to get it onto the market as quickly as possible, put a very expensive price tag on it, and just like reap the benefits.

</details>

### 研发背后的逻辑：产品与模型的“舞蹈”

**Matt Turk**: 我很好奇在 Anthropic 内部这是如何运作的。每次市场上出现新模型，所有的应用开发商都会竞相适配。Anthropic 内部也是这样吗？你们也需要为新模型重新跑一遍所有的评估吗？

<details>
<summary>Original English</summary>

**Matt Turk**: I'm actually curious how that works in a place like Enthropic. Each time a new new model drops on the market in the industry there all the uh harness makers or the application makers sort of like race to just adapt to the new model. How does that work internally at Enthropy? You have to do the same thing basically like you have to rerun all your evals for the new model.

</details>

**Felix Rieseberg**: 是的。我们在训练模型时就考虑到了我们的产品。产品功能会反馈给研究团队，反之亦然。一方面，我们根据我们认为能为人类带来真正价值的能力来训练模型；另一方面，我也提到过，我们并不总是能预知模型的强项和弱项。这就像一场舞蹈，我们通过产品尽可能多地了解人类能从中受益的地方，如果模型出现意外的能力，我的工作就是识别它并思考：我们该如何处理？如何将模型的这种特定能力转化为人类日常工作中真正能用的东西？

不过我想说，随着模型越来越强大，**产品层面的滞后（Overhang）**其实比模型层面更大。让我解释一下：目前整个行业，不仅仅是 AI 原生公司，还包括广义的软件行业、知识工作、甚至制造业、医疗等领域，现有的模型其实已经非常强大了。它们完全有能力处理极长的时间跨度（比如你交给某人并期望一周后拿到结果的任务）以及极高复杂度的知识工作。我们目前仍处于探索阶段，试图弄清楚如何包装这些能力，以最佳格式交付给用户。行业也还在摸索：在这种新模式下，我们应该如何组织工作？当我拜访客户时，很少会觉得我们需要训练一个更擅长某某领域的模型，更常见的是，我被客户组织工作以利用模型的方式所震撼，或者我坚信客户的问题完全可以解决，只是我还没提供合适的 UI、功能或引导流程来让他们轻松使用。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah. So the we we train our models with our products in mind. I think what the products do informs what the research does and vice versa. Um so on the one hand we try to train the models a little bit against the capabilities that we think will deliver real value to humans and then on the other way around I I mentioned a little bit that like we don't always necessarily know ahead of time what the model will be good at what what it will be bad at. So it's a bit of a give and take. It's a little bit like a dance where we try to use the products to learn as much as we can about what humans can benefit from and then at the same time if the model comes out with a surprising capability it might be my job to identify all right what do we do with that how do we how do we turn this like particular capability in a model into something that humans can actually use in their daily work. I will say though that as we get more and more powerful I actually think the overhang in the product is bigger than in the model and let me maybe explain that for a second. What I mean by that is if I look at the industry today and by industry I don't just mean the AI native companies I sort of mean like software at large and then knowledge work at large and then even beyond that manufacturing research um healthcare. What I'm noticing is that the models we have today are actually quite capable. They're quite capable of running knowledge work of both of an extremely long time horizon, the kind of things that you give to someone and expect like a week later as well as complexity, right? And I think we're still a little bit in the era of trying to figure out how to package those capabilities and deliver them to people in the best format. And then the industry is also like still trying to figure out okay how do we arrange our work in a way that makes sense in this new model right like how do you organize work in a way that you can like harness these capabilities the most and what I mean about those things is when I talk to customers and I I I make customer visits rather regularly it is very rare for me to walk back and like leave the building and think oh we need to train the model to be better at XYZ it's far more common that I find myself impressed or surprised by how you can organize work in such a way to like make use of the models or alternatively I'm quite convinced that the problem the particular customer has I can actually very easily solve. Um I just haven't like exposed the right UI the right capabilities the right like onboarding to make that very easy for them to for them to use.

</details>

### Claude Co-work 的诞生：10天冲刺与非开发者红利

**Matt Turk**: **Co-work** 有个著名的传闻，说它是在 10 天内编写出来的。如果这个行业传说不完全准确的话，到底发生了什么？这个 10 天的故事是怎样的？Co-work 完全是由 **Claude Code** 构建的吗？

<details>
<summary>Original English</summary>

**Matt Turk**: So core work famously uh was was uh coded in 10 days or so at least that's the that's that's the lore of it. Actually, let's let's spend a minute on this. If uh if the industry lore is is not entirely um correct, I guess what what happened? Tell us that story of the of the 10 days and cowwork be entirely uh built by cloud code.

</details>

**Felix Rieseberg**: 我能理解为什么这个说法在软件圈流行。没有任何东西是从零开始构建的。我当时的原话是：我的团队在这上面突击了大约最后 10 天，这是事实。在发布前 10 天，我们凑在一起说：“好吧，我们应该发布点什么。发布什么？它长什么样？叫什么名字？能做什么？”但是，任何写过软件的人都知道，你不是从 0 和 1 开始的，你会利用大量的库，利用过去的调研成果。在 Anthropic，我试图解决的核心问题是：如何让 Claude Code 的能力更容易服务于非编程工作？很多聪明人对此进行了长期的思考。如果说 Anthropic 之前没考虑过这个问题，或者我是凭空跳出来的，那是不准确的。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah, I can kind of see I can kind of see why that caught on in software. Nothing is ever built from scratch, right? And I think the the exact quote that I gave that people used was that my team sprinted on this for I think the last 10 days or so, which is accurate. That is that is the case. My team got together um 10 days before release and I was like, "All right, we should probably release something. What do we release? What does it look like? What is it named? What can it do?" However, however, as anyone who's ever built any software can attest to, it's not like you start from scratch with like ones and zeros, right? You like make use of a lot of libraries. You make use of like research you've done in the past in particular in anthropic. the the core problem that I tried to solve for which is how do you make it easier to bring the power of cloud code to non-coding work right like general knowledge work a lot of very smart people have thought about that at length and um it would be inaccurate to say that anthropic has not thought about this problem it would also be inaccurate to say that I feel like sort of like came into this cold without benefiting from all that work

</details>

**Matt Turk**: 请带我们回顾一下这款产品的起源。你们已经有了 Claude Code，是什么时候意识到需要构建 Claude Co-work 的？是因为人们使用产品的方式吗？

<details>
<summary>Original English</summary>

**Matt Turk**: walk us through the genesis of the of the product so you guys had cloud code and when did you become um kind of obvious that you needed to build cloud co work. Was it just uh the way people use a product?

</details>

**Felix Rieseberg**: 我是在 2025 年 12 月假期期间，在社交媒体上坚定了这个信念。我看到越来越多非开发者的人开始使用 Claude Code。我看到了一些教程，教人们：“你不是开发者，没关系，我告诉你终端在哪里，怎么获取 Claude Code，它会为你做伟大的事情。”这些人并不是在编写软件，还有一部分人利用模型的能力来学习如何编写软件。但我还注意到，我们那些每天用 Claude Code 写软件的铁杆开发者用户，也开始用它处理完全不属于软件范畴的事情。这种**潜在需求（Latent Demand）**变得势不可挡，这是预测你应该在什么地方投入时间的强力指标。如果人们哪怕在产品体验极差的情况下也要“爬过碎玻璃”去使用它，那就说明这个领域值得投资。

具体的起源是我的同事 **Boris Cherny**（Claude Code 的首席开发者）来找我说：“我觉得你应该发点什么，而且就在接下来的……周五吧。”我跟他讨价还价到了下周一，我说给我个周末的时间。然后我们组建了一个团队，突击研究如何让 Claude Code 在非编程场景下变得高效。Co-work 的核心成分其实相当简单：我们给 Claude Code 配备了一个它能用来运行自己代码的**虚拟机（VM）**。这个虚拟机带来了几点好处：首先是**硬性保证**，你不再需要时刻监视它，因为它在沙箱里，与你的电脑、文件和网络完全隔离，它只能访问你授权的域名和文件。其次，Claude 为了高效解决各种任务，通常需要编写超专业的代码片段，有了自己的电脑，它就可以在不弄乱你本地环境的情况下，搭建自己的开发环境。最后就是 UI 层面的一些简化，使其优雅、舒适，更适合非开发者。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: I think I really gained conviction over the holidays, the last holidays, December 2025 on social media. I saw more and more people who are not developers picking up claw code. I saw newsletters. I saw tutorials where people like, "You're not a developer. Let me explain to you where to find the terminal and how to get claw code. It's going to do great things for you." the people who were picking up cloud code were not necessarily building software. There was I think a small subset of people that were non-developers that were using the power of the model to now build software. That was one use case. But I also noticed that a lot of our developer users, the ones who do use cloud code every single day to build software, started using it for things that are not software at all. That became a pretty overwhelming overwhelming amount of latent demand, right? which i think is a strong predictor for what you should maybe spend your time on. If people are crawling over glass to use your thing even though you didn't make it even remotely good. Um that's a great indicator this is like a space where it's worth investing. The actual genesis then was that my colleague Boris Churnney who um is is the lead developer for cloud code came to me and was like I think you should ship something and I think you should probably do it like within the next I don't know should we say Friday. I negotiated him up to Monday. I was like, give me like the weekend, too. Um, and then we took a team and we we sort of spiked on this idea of, okay, how can you make how can you make cloud code very effective for non-coding use cases? Co-work by itself is is in its in its ingredients rather simple. Um, what we've done is we've taken cloud code and we've given cloud code a virtual machine that claude can use to run its own code. That virtual machine gives us a few things. The first one is it gives us hard guarantees around what cloud can do and not do. So you as the person who's operating this very powerful thing no longer need to supervise it, right? Because it's in this little sandbox and you can completely separate it from your computer, your files and also your network. So this virtual machine only gets access to the exact domains you give it access to and it only gets access to the exact files you've given it. That's one benefit. The other benefit is that for cloud code to be most effective, it actually does need developer tooling, right? Cloud is very good at helping you solve any kind of wide range of tasks. But the way it often does that is by writing hyper specialized little little software snippets by giving Cloud its own computer. It can like set up its own developer environment without necessarily messing with your computer. And then I think the things around it, there's a little bit of UI. Um, we're trying to make this like very comfortable for you to use. We're trying to make it very elegant. We're trying to simplify some of the flows that maybe are more native to developers and then the end result that we get is we have this this tool that is quite capable of helping people with their knowledge work.

</details>

### 技能、记忆与“同事化”理念

**Matt Turk**: **Skills（技能）**在 Co-work 中扮演什么角色？

<details>
<summary>Original English</summary>

**Matt Turk**: Where do skills fit into the picture of co-work?

</details>

**Felix Rieseberg**: “技能”本质上就是解释如何做事。我总是惊讶于这有多管用。如果你把 Claude 当作**同事**来对待，你能走得非常远。我的建议是：就像对待同事一样对待 Claude。所以技能基本上就是一个文本文件，在里面解释如何完成某件事。我默认的例子总是“预订机票”。在 Anthropic，我们有特定的供应商协助出差，你不能直接去 Google Flights，必须进入特定的供应商门户，而且我们有各种差旅政策。就像我对同事解释一样，我也这样对模型解释。我创建一个文件：这是预订机票的方法，去这个网站，请考虑以下事项，然后再加一点个人偏好，比如避免红眼航班，以及我非常看重周末，所以如果我去纽约，尽量订下午 4 点的航班。你把这些都写在文本文件里，模型就能极其出色地理解并执行。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: So skills are essentially just markdown files that explain to the model how to do things. And I'm always surprised at how well this works. If you treat model the model claude in this in this case like a coworker you get very very far. My recommendation to like everyone I always talk to is just treat cla the way you would treat a coworker. So a skill is fundamentally just a text file and in the text file you explain how to do a certain thing. My default example is always say booking a flight. At Anthropic we have a specific particular vendor that helps us with our travel booking. So you can't just go to Google flights. you need to go into this like particular vendor portal and then we have various travel policies and the same way I would explain this to a coworker I can explain it to the model I just make a file that is like here's how you book flights you go to this website and on this website please consider the following things and then maybe you also sprinkle in like a few personal things right like in my case avoid redeye flights but also I do actually enjoy my weekend quite a bit so like try to book a flight if I have to fly to New York from San Francisco try to like take the 4pm flight that's my favorite And you put all of those things in the text file and the model then is extremely capable of understanding the instructions and then running with it. That's surprisingly simple.

</details>

**Matt Turk**: 智能层是存在于模型级别的吧？Co-work 如何弄清楚如何将一个通用任务分解为一堆不同的子任务？

<details>
<summary>Original English</summary>

**Matt Turk**: And the intelligence layer lives at the at the model level, right? The way uh co-work figures out how to take a a generic task and breaking it into a bunch of different subtasks. That's done by the model.

</details>

**Felix Rieseberg**: 那是模型与人协作完成的。我们对模型“待办事项列表”的组织方式非常满意。模型被指示将项目分解为单个任务，你可以编辑列表、点击单项并提供更多上下文。智能确实在模型内部，但“技能”赋予了它另一层实用性。这很有趣，因为作为人类，我们习惯了“一刀切”的技术，大家都用一样的手机电脑，但模型这种智能体真的能从一点点指令和引导中受益。就像一个聪明人加入公司通常需要入职培训一样。另一个例子是制作 PPT 或文档。我是“风格指南”的拥趸，如果你有模板，你应该告诉 Claude，告诉它你喜欢什么样的字体，如果你写下这些简单的指令，模型会更有效地帮你工作，而不需要你一直守着它。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: That's done by the model in collaboration with a human. Right? Like I think one thing we're quite happy with is how we've organized the model's to-do list. So the model is instructed to break down projects into individual tasks and you can sort of like take a step you can sort of edit the to-do list. You can click on individual items and provide more context. But yeah, the intelligence lives inside the model. But the skills I think really give it like another layer of usefulness. And I think there's something interesting going on here because I think I think as humans we're so used to technology that is like one sizefits-all, right? Like a lot of us use the same phone, the same computer, but the model is like this this intelligent thing can really benefit from a little bit of instruction and guidance. The same way that like any smart person who joins a company would usually get a little bit of onboarding being shown how to do things. Another example that is maybe very app for many people is like creating presentations or creating creating documents. I'm a big fan of style guides. If you have a PowerPoint or a Google Slides template, you should tell Claude about it. You should tell Claude about how you like to make presentations in general. Like maybe you prefer Siri fonts or like not um and if you just write that down a little instruction, the model will be so much more capable at actually helping you with work in a way that you don't have to like go in like fix it and babysit it all the time.

</details>

**Matt Turk**: 对于 Co-work 来说，记忆存储在哪里？在模型里还是在架构（Harness）里？

<details>
<summary>Original English</summary>

**Matt Turk**: Good. And where does memory live for co-work to remember you and remember your task? Is that at the model? Is that in the harness?

</details>

**Felix Rieseberg**: 实际上在架构里。当我告诉人们我们是如何实现记忆的时候，他们往往会感到惊讶，因为它指出了所有这些模型底层的简洁性。**记忆其实就是文本文件**。模型被指示：嘿，如果你觉得有什么相关的信息将来可能想记住，就把它写下来。我们会帮它组织记忆，你可以设置具有隔离记忆的项目。底层的技术并不是什么复杂花哨的数据库。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: It's in the harness actually. And it's like often surprising to people when I talk to them how we how we've implemented memory because I think it maybe points at the simplicity underneath all of those models. Memory is just text files. It's really just the the model being instructed. Hey, if you feel like anything was pertinent that you might want to remember in the future, just write it down. And then we help the model a little bit with like organizing its memory. So you can you can set up projects that have isolated memory versus like your overall memory. But the the underlying technology that sort of is bolted on on top of the model is sometimes surprising to people that it's not you know like a some complex fancy database technology.

</details>

### 连接云端与本地：隐私、信任与安全

**Matt Turk**: Co-work 如何连接信息源或应用？是通过连接器？**MCP**（模型上下文协议）？还是两者的结合？

<details>
<summary>Original English</summary>

**Matt Turk**: How does co work connect to the sources of information or application? Is that is that connectors? Is it MCP? Is that a combination?

</details>

**Felix Rieseberg**: 两者都有。我坚信与你工作相关的数据存放在两个地方。一个是你的**本地计算机**，我们很多人电脑里有很多文件。我一直主张技术制造者需要严肃对待用户使用电脑的事实，而不仅仅是平板电脑。并不是所有东西都在云端。Co-work 可以利用文件和文件夹作为上下文，你可以直接拖进去，或者给它访问特定文件夹的权限。第二个地方是云端或互联网，比如数据仓库、分析工具、SharePoint 等。我们有多种连接方式：MCP 连接器非常强大；另一种是由于 Claude 拥有一台虚拟电脑，如果你指示它这样做，它可以访问互联网。你可以精确控制它能访问互联网的哪些部分。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: It's a combination of all of them. So I I have a strong belief that the data that is relevant for your work probably lives in two different places. The first one is on your computer, right? Like a lot of us have a lot of files on our computers. I'm a huge proponent of the idea that us makers and builders of technology need to take seriously the fact that you use a computer and you don't just have an iPad. Not everything is in the cloud. Many people benefit from just using files and folders. That is one part of context that Kova can use. You can just drag it in. You can give cloud access to a specific folder or multiple folders. And then the second part is information that might live in the cloud or the internet like a data warehouse, analytics, sharepoint, whatever people might use, right? We have multiple ways of connecting to those sources. MCP connectors are one that is quite powerful. The other one that we use is because Claude has a computer, it can reach out to the internet if you instruct it to do so. you control specifically which parts of the internet cloud gets access to and which ones it doesn't get access to but generally speaking if it's out there and you want to give cloud permission to use it will find a way to use it

</details>

**Matt Turk**: 你提到了本地，我知道你对**本地 AI** 有一个很强的论点。为什么 Co-work 需要运行在笔记本上而不是云端？

<details>
<summary>Original English</summary>

**Matt Turk**: you mentioned local and I know you have a strong thesis about local AI do you want to get into this why does co-work need to live on your laptop as opposed to the cloud

</details>

**Felix Rieseberg**: Co-work 今天提供给你的两大核心价值就是访问你的本地计算机和本地文件。这在云端行不通吗？以使用 Chrome 为例，如果你授权，Claude 就能使用你的 Chrome，这它与世界交互的强大工具，比如回复或总结邮件。有些人会问为什么不在云端做？首先，你的 Session（会话）很有用，让 Claude 访问你关心的、已登录账号的网站（比如你的 Gmail）非常有意义。其次，这是一个实现细节的辩论。我们当然可以把你的 Chrome 打包上传到云端，问你要密码，但这涉及安全和信任。我不认为我们应该教用户信任某一家公司拥有他们所有的密码。还有一个现实问题：世界还没准备好。比如银行，如果它看到你同时从本地和数据中心登录，可能会锁掉你的账户。这种体验上的瑕疵对我的用户来说是不可接受的。所以在短期内，我想让 Claude 在你工作的地方与你相见。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: the two biggest things that co gives you today are access to your local computer and also access to your local files. But does that not work in the cloud, right? Like a lot of us have a lot of files on our computers. I'm a huge proponent of the idea that us makers and builders of technology need to take seriously the fact that you use a computer and you don't just have an iPad. Not everything is in the cloud. Many people benefit from just using files and folders. That is one part of context that Kova can use. You can just drag it in. You can give cloud access to a specific folder or multiple folders. And then the second part is information that might live in the cloud or the internet like a data warehouse, analytics, sharepoint, whatever people might use, right? We have multiple ways of connecting to those sources. MCP connectors are one that is quite powerful. The other one that we use is because Claude has a computer, it can reach out to the internet if you instruct it to do so. you control specifically which parts of the internet cloud gets access to and which ones it doesn't get access to but generally speaking if it's out there and you want to give cloud permission to use it will find a way to use it

</details>

**Matt Turk**: **Computer Use**（计算机使用）改变了这个愿景吗？你们最近收购了 **Versep**，这家初创公司就在做 Computer Use，随后你们就发布了相关功能。如果云端能看到电脑的所有内容，为什么还需要本地化？

<details>
<summary>Original English</summary>

**Matt Turk**: Does a computer use change this vision? Um so you recently acquired Versep uh which was a startup doing computer use very quickly afterwards you u released computer use for uh cloud code and co-work I believe I believe that the versep product initially was actually computer use from the cloud and you now use it in in a local manner just to play devil's advocate if you could see all of a computers content from the cloud why do you need to have it locally?

</details>

**Felix Rieseberg**: 我经常思考这个问题。我脑子里的问题是：如果我给你一个魔法按钮，按下去我就能把你整台电脑的数据“吸”到云端，你会按吗？目前我的印象是，大多数人不会按。即便他们可能信任 Anthropic 是少数几家真正会保护数据的公司。目前，我仍然看到 Claude 在你工作的地方运行有着巨大的价值。当然，技术上并没有限制我必须在本地操作，我可以做一个云端版本。但目前，专注于本地电脑、让 Claude 在你工作的地方尽可能高效，这在用户中引起了很好的共鸣，也让我们能跑得快一点，在安全和隐私上做得更激进一点。在快速变化的 AI 领域，目前我对本地计算机感到非常兴奋，而不是要求你把所有信息都放到“我的电脑”里。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah, I think about that quite a bit and I think the question in my head currently is if I build you m a magical button and you press that button and I'll just slurp up your entire computer and I put it into the cloud, would you press it? So far, my impression is that most people would not press it. Maybe they would trust Anthropic as we're like one of the few big companies out there that would actually do trust us with all of that data. For now, I think I still see a huge amount of value in having Claude operate where you operate. But you're right that like from a technical point of view, there isn't much that like strictly forces me to operate on your computer, right? Like I can probably build a fairly good version of this button that just slaps up your entire computer. We can do a lot of these things in the cloud. We can even run the entire harness as well as like the machine around it in the cloud and reach down into your computer. But for now, the concentration on your computer and sort of this like I want to say laser focus on making cloud as effective as it possibly can be where you work is something that we've seen resonate fairly well with users and also allows us to move a little p faster, push safety and security a little harder than it might be possible in the cloud. There's enough there for me to like for now and AI is a fastmoving target, right? like things might change quickly, but for now to be pretty excited about your local computer more so than asking you to put all of your information in like a on my computer.

</details>

### UX 与信任：从“清理桌面”开始

**Matt Turk**: 你提到了“信任”这个词，在**智能体 AI** 领域这是一个迷人的话题。既有对隐私的信任，也有对其工作能力的信任。作为产品负责人，你在建立这种信任方面学到了什么？

<details>
<summary>Original English</summary>

**Matt Turk**: You mentioned the word trust and it's a fascinating topic in a genetic AI. So there's trust as in you're not going to take files that you shouldn't have access to. There's also trust in okay co-work I'm I'm trusting you to run certain tasks which are going to be increasingly important to me and my work life in a way that's going to make me uh great and uh not embarrass me. What what have you learned as a head of product about building that level of trust with people?

</details>

**Felix Rieseberg**: 这是个好观点。在 2026 年构建 AI 产品有一点很有趣：你添加的大多数按钮和产品服务，可能更多是为了服务人类，而不是为了服务模型。这是一种技术构建方式的转变。过去我们为电脑的便利构建按钮，人类只是提供信息让电脑做事；现在反过来了。举个例子：我们最近发布了一个叫 **Dispatch**（调度）的功能，让你能在手机上指挥电脑上的 Claude。我们有意识地选择不添加太多按钮。我在社交媒体上每天收到 50 条私信问我：嘿，如果 Dispatch 能访问本地文件就好了。但实际上 Claude 已经能访问了。现在的做法是你问 Claude：嘿，你能看到我的下载文件夹吗？Claude 会说：可以，你授权我交互吗？一旦授权，它就开始工作。

关于信任，我们认为这不在于 Claude 向人类证明自己，而在于通过从小事做起，慢慢教育并引导用户提高他们的认知水平。当 Co-work 发布时，它已经能做惊人的事了，比如写 200 页的 VC 报告或设计复杂的建筑图纸。但最引起用户共鸣的却是：“**清理我的桌面**”。对 AI 来说这是一个微不足道的任务，完全不需要 Claude 帮忙。第二个引起共鸣的是“**计划任务**”。从技术角度看，5 分钟后运行一个函数并不是什么创新。但我们是在教用户：你可以从一个小任务开始，看到 Claude 做得很好，然后慢慢把任务变大。这让用户逐渐意识到：我不必盯着它看，不必坐在电脑前监督它。你可以让它每天检查你的会议并写报告，它做完后发邮件给你就行。信任就是这样建立在 Claude 承诺特定输出、输出确实很好、且你不需要时刻守着它的基础之上的。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah. Yeah, it's a good point. It's a good point. I think there's something interesting if you build AI products in 2026, which is that most of the buttons you add and most of the product services you build are probably more for the human than they are for the model. And this is an interesting shift in how we build technology, right? Like in the past, we've usually built buttons for the benefit of the computer. And the human was just there to provide information so the computer could do things. Now, we're actually doing it the other way around. Um, and i'll give you one one quick example. We've recently launched a feature called dispatch which allows you from your phone to talk to claude on your computer. As a very conscious choice, we decided not to add too many buttons. So, one of the pieces of feedback I got on social media the most easily got 50 messages every single day from people asking me, hey, it would be cool if dispatch could access my local files. That would be really nice. Like, can you can you find a way so that it can attach a folder? I mentioned this because cloud can access all your files and folders. The way this currently works is that you ask Claude, hey, can you also see my downloads folder? Claude will say, yeah, I can see it. Do you give me permission to interact with your downloads folder? And once granted, it will go. So, we're debating, do we add a button? Do we add a button so that the user knows that cloud is capable of something? And to answer your question here about trust, I think the way we've thought about trust is like less about claude proving itself to the human and more so slowly educating and helping the users in their sophistication journey by taking them by the hand and starting really small. When we first released co-work, it could already do like fairly impressive things, right? It could like write a 200page VC report for you. You could ask it to like start protein synthesis and modeling. You could ask it to like design complex architectural drawings. Um, but the thing that resonated most with people was clean up my desktop. A menial task for AI, right? You do not need claw to help you clean up your desktop. Completely unnecessary. Um, and i think the second piece that also really resonated with people was schedule tasks, which again, like from a technology point of view, it's not a big innovation. Like we've known how to like run a function in 5 minutes rather than right now for a long time. But what we're teaching people here is you start with a little task. You see claw do that well. You then slowly grow the task, right? Like humans fairly independently well after seeing like a small task work increasingly offload more and more work. And then with schedule tasks you teach them it's actually okay if you don't watch this thing. Yeah, like you don't need to like supervise. You don't need to sit in front of your computer and watch Claude do a thing. You can just ask it to review your meetings every single day and write you a report. You can just have it do that. It will send you an email once it's done. You don't need to be involved. And i think on this journey, we're slowly trying to teach people more and more what the capabilities are and how to integrate them into their life. And i think that's fundamentally where the trust comes from, right? like trust is really built on top of Claude promising a particular output, that output actually being good and you not having needed to either babysit it or intervene in some way.

</details>

**Matt Turk**: 你会说 UX 对 AI 智能体的成功和技术本身一样重要吗？从 UX 角度看，构建 AI 智能体还有哪些教训？

<details>
<summary>Original English</summary>

**Matt Turk**: Would you say that uh UX is as important to the success of an AI agent as the technology itself? Like how you take users on a journey uh so that they are empowered and uh if so what what are some other lessons learned building AI agents from a UX standpoint?

</details>

**Felix Rieseberg**: 确实如此。UX 至关重要。回看我们最受欢迎的产品 **Claude Code**，它的核心理念就是：如果 Claude 不是在云端，而是在你电脑的终端里运行会怎样？这几乎完全是 UX 的创新，模型和核心能力是一样的。今天我看到的能引起共鸣的 AI 产品，很少是因为提供了最原始的性能。我想更进一步说，这不仅适用于 AI，也适用于所有软件。我敢肯定有很多初创公司的邮件产品功能比 Gmail 更多。人们总是试图通过堆功能、加按钮来领先。我想起了智能手机发明之前的那个“愚蠢时代”，手机上接投影仪、接游戏手柄、有的没键盘有的全键盘。

但最终，好用的技术往往关乎你**减去了什么**，而不是增加了什么。直到今天，我不认为大多数人是根据规格表买手机的。人们买手机是因为一种“感觉”，而不是具体的芯片能力。AI 也是如此。当然，强大的模型能给你优势，我能构建好的 AI 产品是因为我与研究人员密切配合，公司内部有惊人的模型。但如果有人在产品上打败了我，我怀疑不是因为他们模型更好，而是因为他们找到了更好的用户体验。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: It's a really good question because I actually think I actually think that's true. I do think the UX matters quite a bit, right? Like even if you go back to our one of our most popular products cla um the very genesis of it was what if cla but instead of like in the cloud it's running on your computer in your terminal that that is almost entirely UX it's the same model it's the same core capabilities um it's really all around what is the user experience and like how do you interact with the model right but it's fundamentally the same model and that's really where a lot of the a lot of the benefits came from and I think similarly today um the AI products I see resonate with people the most are rarely the ones that deliver the most raw potential, the most raw power. Um, and i I would actually go one step further and say this is probably true not just with AI, but maybe with software overall, right? Like um i'm going to blindly assume that plenty of startups out there offer email with more features than Gmail. There's there's plenty of companies that try to like sort of jump ahead by offering a larger amount of features or more buttons or like more capabilities. Um i often think a lot about the um the silly times of mobile phones right before the smartphone was invented, right? All the things that people bolted onto phones. We had like phones with projectors, phones with like included game pads. like um a phone that didn't have a keyboard, phones with full keyboards. Um and in the end, in the end, I think technology that works really well is like often more about the things that you take away rather than the things you add. It's more about like how what does it feel like? And to this day, i'm not convinced that most people buy a phone on the basis of a spec sheet. I could be wrong. I'm like completely making this up, but i'm having the feeling that most phones are bought for reasons other than what are the specific chip capabilities. And i think AI probably works a very similar way. Like obviously a very powerful model gives you a bit of an edge. I'm not going to lie that like it's probably much easier for me to build a good AI product because I work very closely with researchers and we have amazing models inside the company. But at the end of the day, if someone beats me, Felix at like building very good products, I suspect it's going to be not because they built a better model, but likely because they figured out a better user experience.

</details>

### 执行成本趋于零：从“绘画”到“摄影”

**Matt Turk**: 那么你们如何具体改进用户体验？你们会精确追踪用户做了什么、什么有效什么无效吗？

<details>
<summary>Original English</summary>

**Matt Turk**: And so, how do you improve the user experience very practically? Like you guys look at uh what people do. So you you mentioned you talk to customers uh fairly often, but do you track uh very precisely what what people do, what what works, what doesn't work, and then uh spend more time on key use cases. How does that work?

</details>

**Felix Rieseberg**: 我们对用户的痴迷是非常激进的，我们倾向于快速迭代而不是长期计划。我们的计划通常不会超过一个月。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: I think I think what we do is probably not super unique. Um there's there's one thing that is new to me. So i'm first going to say the things that like a lot of the listeners are probably going to say, "Ah, yes, of course." And those are pretty radical obsession with users, right? Like build for actual real humans that you talk to a lot. try to try to prefer iteration over like these longunning plans. We tend to plan not more than a month out. We try to be like fairly quick and how quickly we ship and also how quickly we iterate.

</details>

**Matt Turk**: Co-work 的整个路线图只有一个表达？

<details>
<summary>Original English</summary>

**Matt Turk**: The entire road map for core work is one month.

</details>

**Felix Rieseberg**: 是的，最多一个月。因为我们不断思考下周、下下周是什么样。我们并不相信自己能关在房间里设想出一年后对大多数人最好的产品。如果有人告诉我他知道 AI 明年长什么样，我肯定不信。任何好产品的产生都是因为我有大量的纠错机会。现在的新情况是，**执行基本上是免费的**。如果你给我 10 个想法，我可以立刻说“全做了”，全试一遍，看哪个感觉更好。我们尽量在内部测试。现在的执行速度是全新的：即使是两年前，快速迭代也需要非常专注地挑选少数几件事，因为人的精力有限。而现在，执行变得如此廉价，你可以同时在深度和广度上进行迭代。这简直像从绘画进化到了摄影。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah. At at most. Because we sort of like we we constantly think about okay what does this look like next week? What does it look like the week after? Our confidence that we can like sort of all disappear into a room and envision the best product for most people out there the way it looks like in a year is pretty low. Yeah. And in fact, I would like argue that no one ought to have that confidence. If anyone tells me I know what AI looks like next year, i'm not going to be very impressed. Um maybe some VCs will maybe maybe. But I I certainly don't have the confidence. And i think anything I've ever built that became very good became very good because I had many opportunities to course correct. Had many opportunities to be a little wrong. And like many opportunities to figure out, okay, which one of these three works better? The thing that is new is that execution is essentially free, right? Like I can build if if you come to me with 10 different ideas, I can very quickly say let's do all 10. Let's try all 10, see which one we like more, which one feels better. Um, we try to do most of our testing inhouse. We try to not abuse our customers as like sort of free beta testers. Um, but I think with most products, you very quickly know whether or not it's like roughly going the right direction or not. Like that that feeling comes very very quickly. As a company now, we've grown quite a bit. We have a decent amount of employees. It's like fairly easy for us to figure out does this resonate with more than five people or not. And this rapid speed of execution is like really what's new, right? Because previously, even like two years ago, if you wanted that rapid iteration, it required a very aggressive focus in which which things you pick because you can only iterate so quickly with only a few things at a time. And now that execution is becoming so cheap, you can iterate with things like you can go deep and broad at the same time. And that's honestly like wild to witness.

</details>

**Matt Turk**: 所以你们会真的同时跑 10 个版本，让公司内部的人测试并引导最终选择？那么瓶颈变成了什么？

<details>
<summary>Original English</summary>

**Matt Turk**: So, so just to play it back, so you're saying that you'll you'll actually create 10 products or 10 versions of the product actually running and then you'll have people at anthropic test and and and sort of guide which one you should eventually pick.

</details>

**Felix Rieseberg**: 我们公司内部目前可能有 100 个不同的原型。虽然大部分还没达到向用户展示的信心水平，但这种构建速度完全碾压了我过去的所有经历。过去如果你有个好主意，我会告诉你下个月才能开始，还要花三周时间。现在你可以带着想法来找我，我说“给我 10 分钟，我发给你个东西”。

瓶颈仍然是“**共识（Alignment）**”。共识对任何地方的任何人都是难题。当有竞争性的想法时，选哪个？如何选？如何吸取不同想法的长处？这是目前的瓶颈，因为这是人类仍然活跃的地方，是**人类品味（Human Taste）**发挥作用的地方。品味正变得比过去更重要。数据驱动的方法只是帮你验证你的品味是否真的引起了用户的共鸣。Ken Kocienda 在《**Creative Selection**》（创意选拔）中描述过品味与验证的结合。软件行业会不会变得像时尚行业？手机已经有点像了。当性能达到基准后，重要的就是你讲的故事、你给人的引导、你让用户在使用时的感受。这些将是比内部原始能力更大的差异化因素。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: We probably have easily 100 different prototypes of like various applications inside the company. Right now, none of them have necessarily yet hit the confidence of like this is good enough to show to a user. But the amount of prototypes you can build internally very very quickly completely dwarfs anything I've done in the past because of the cost of execution right like in the past the thing that would always hold you back is you know for me as the engineering leader um if you had a good idea you would come to me and I would tell you oh we can work on this next month it's going to take us three weeks until then like go and talk to the customer validate your ideas and now you can come to me and say oh I have an idea and I like cool give me 10 minutes i'll send you something and and that is that is It's like going from the painting to to the photograph, you know. Fascinating. So, what becomes the bottleneck then? Then you have a 100 prototypes and then you need to to pick one and then somebody needs to do that. Is that is that where things slow down? Yeah, I think the alignment piece is still pretty hard. The alignment piece has always been hard for anyone anywhere, right? Like as a company, if you have people with competing ideas, who do you pick? How do you pick? How do you figure out how to take the best ideas from some things and combine them into another? That's probably a bottleneck because this is where the most humans are still active. This is where human taste comes in.

</details>

### 未来软件的模样：掌握人类语言

**Matt Turk**: 在 Co-work 这种面向广泛专业人士的背景下，“品味”意味着什么？

<details>
<summary>Original English</summary>

**Matt Turk**: What does taste mean in a context where you have such a a broad audience and how do you uh test for it?

</details>

**Felix Rieseberg**: 我经常思考手机。虽然大家手机长得一样，但没有任何两部手机是完全相同的。你安装的应用让你的手机在地球上是独一无二的，就像指纹。Co-work 的初衷也是类似的：我们想要一种泛化能力极强的东西，可以应用于你生活和工作的广泛场景。以我个人为例，我最近在搬家，那涉及 500 页我几乎看不懂的法律文件；同时我今年刚有了女儿，处理所有的医疗文书也极其有帮助。这是两个完全不同的场景——抵押贷款申请与医疗文书，但底层的**原语（Primitives）**是相同的。如果你在构建产品时非常关注细节，频繁使用自己的产品，你就能感觉到什么时候软件阻碍了你。我想要创造更多能让用户“飞翔”的瞬间。即便客户所处的行业我不懂，我也能从他们的故事中感受到：什么让他们飞翔，什么拖慢了他们。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah, I think I think a lot about I've been mentioning it so much already in our conversation. I feel like almost silly about it, but I think a lot about the phone and how all of us start with the same phone, but like no two phones are the same. The exact apps you have installed probably makes your phone like unique among all the phones on the planet. Um it's almost like a fingerprint. Same with my phone. We all start with a device that probably looks very similar to the other devices, but then the way it integrates itself into our lives, is not always good, not always bad, but certainly very unique and certainly very personalized. And I think for co-work, our approach is similar that we want something that generalizes extremely well that we can apply to your life across a broad range of applications. Um, and maybe just speaking from my personal life, currently in the process of moving and moving my family into into a different house. Um, and as many people certainly certainly the ones who are also listening in America know that involves about 500 pages with a lot of words that I barely understand. Co-work here is extremely helpful, but it's also extremely helpful in like healthcare scenarios. Just had a daughter this year and working through all of that paperwork has been super helpful for me too. But these are two wildly different things, right? One of them is like mortgage applications and like negotiating with movers and like figuring out various financial applications and the other one is like much more healthcare. In theory, those are two completely different applications of the same underlying technology. But i'm noticing that the primitives that I think about are kind of the same. And like some of those primitives are a little better. Some of them feel a little better in my hand. And I think if you pay close attention as a person who's building things, if you use your own stuff a lot, you can sort of like feel when you're bumping into the software and it's not making you fly. And I want to create more and more instances where I can fly. And I can then validate with customers that even if they might be working in industries that I barely understand, I have no idea how they work, I can sort of tell from their stories how they're using it, what makes them fly and what really slows them down. And if you lean into those and you like just aggressively try to like enable that feeling of you're becoming more productive, you're going into you you're in flow, you feel like this thing is taking over work that you find annoying. I think there's a lot of value to be found there.

</details>

**Matt Turk**: 回顾这 4、5 个月的旅程，影响力惊人。最难的部分是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Just looking back on the journey, which at the end of the day is a 5 months, what four months old journey, it's insane the impact that that you've had in such a short period of time. What was the hardest part?

</details>

**Felix Rieseberg**: 最难复制的是**潜在需求**。Co-work 是建立在“侧耳倾听”的基础上的，这种需求是一份礼物，你很难凭空创造它。在构建 Co-work 的过程中，并没有什么特别难的事。难点依然在于如何应对成功带来的挑战——比如你开了家咖啡馆，本来指望 10 个人来，结果来了 2000 万人，你该怎么办？

对于正在构建 AI 智能体的人，我的建议是不要过度构建自己的基础设施。今天我们发布了一个叫 **Claude Managed Agents**（Claude 托管智能体）的产品。我要给出的建议和理由是：随着模型能力越来越强，我们正在减少需要考虑的边界情况。如果你假设模型在需要时能随时随地构建自己的数据库和工具，那么你就没有必要去做一个超专业的垂直产品。

互联网是一个很好的类比。互联网真正改变经济花了数十年的时间——从第一个浏览器到亚马逊成为零售巨头，中间隔了很久。这对我来说是“入场”的理由：去寻找那些能以独特方式应用 AI 的领域。不过，价值将更多地来自于**如何帮助人们组织工作**，而不是智能体本身或模型智能。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: I'm thinking about your question through the lens of like what is the hardest to replicate? Right? Like if you if you told me okay now do it again do it with another product like what would be the most difficult to replicate I think there's probably something about a point in time and I mentioned that co-work sort of came on the heels of us like keeping our ear to the ground and saying oh there's something here this latent demand latent demand is a gift I don't think it's I don't think you can you can go and try to look for it you can try to find it but it's very hard to create out of nothing recreating that would probably be the hardest thing. Now, I do think software has always had ample latent demand. Like if you if you looked for it, you could always find it quite a bit. That's that's certainly one thing that is that I think is hard to like replicate. In terms of actually building core work, I would not say that anything was particularly hard. I think the things that are hard about building good products remain hard, right? Like you there sort of like the perils of success. It's like what do you do if right like you open up a cafe and instead of 10 people 20 million people show up what do you do? Um that's that that that was probably at times sometimes hard for us and like remains a challenge the overwhelming demand for anthropics products. I'm i'm probably going to be the last one to actually complain about people wanting to use my products.

</details>

**Matt Turk**: 随着你们不断向上层堆栈进发，软件行业还剩下什么可以构建的？

<details>
<summary>Original English</summary>

**Matt Turk**: What are the the areas as as you guys keep uh going uh up the stack that are left uh for the software industry uh to to build around?

</details>

**Felix Rieseberg**: 这是一个非常个人的观点。我经历过几轮“民主化”浪潮，构建事物所需的晦涩知识越来越少。多年前我在微软开发 **Electron**，当时公司内部觉得这是个玩具，真正的开发者需要完整的 **Visual Studio**。但现在，你不再需要深入研究计算机底层了。我这周在感慨，今年我查看汇编语言的次数是零。过去 20 年的成功开发者擅长理解计算机，而未来的开发者将越来越多地需要**理解人类和用户**。AI 是又一次阶跃式变化。

只要人类有问题和需求，软件就是一个合理的答案。虽然大家对 AI 的“平台期”有预期，但我没有理由相信这会很快发生。AI 学会写通顺的句子才没几年，现在已经能构建整个应用了。Mythos 证明了这不是理论，模型会越来越聪明，目前看不出终点。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Yeah, I think and this is very very personal take but I've now been around like a few of these democratizing rounds where you needed less and less arcane knowledge in order to build things. I'll give you an example maybe just to make this like slightly more apt. Um many years ago I worked at Microsoft. At Microsoft I was working on this something called Electron which is like a crossplatform. It's a way to build applications that more or less work and look the same on both Windows and Mac OS. And one of the first things we used it for was Visual Studio Code, which is a code editor that has since become quite popular with people and cursor built on top of it. Various other companies are and when Visual Studio Code first was released inside the company, there was a feeling that this is a toy. This is not this is not for real developers because the real developers they need Visual Studio which is why Visual Studio Code is such a complicated long name because Microsoft also had this big application for real developers with all kinds of like really fairly advanced tooling. And what has happened since is that you just don't need to go that deep into your computer anymore. like to the the people who are listening um who do work in software like I I reminisced this week that the amount of times I had to look at assembly this year was zero. Over the last five years it has not been zero. I've looked at assembly at least once but it's becoming very rare. Like it's not really a thing I look at anymore.

</details>

### 总结与快问快答

**Matt Turk**: 最后来几个“暴论”吧？

<details>
<summary>Original English</summary>

**Matt Turk**: I'd love to close with some hot takes if you're willing.

</details>

**Felix Rieseberg**:
*   **被低估的想法**：**MCP 连接器**。虽然大家现在都在谈论 CLI，但将数据与执行引擎分离具有内在价值。到明年，MCP 将会变得非常有用。
*   **被高估的想法**：**并不是每个产品都需要聊天框（Chat）**。很多软件工程师的膝跳反应是：加 AI 意味着右边加个侧边栏，底下加个输入框。我鼓励开发者再多想一步：如何让这件工具变得好用？
*   **如果你从零开始会做什么**：我会去追逐行业的“长尾”，比如世界上还有大量运行 **Windows 7** 的设备在执行关键任务，它们是现代 AI 触不可及的。我还会进入物理世界。我们仍然处于 AI 的“愚蠢时代”，如果走运的话，我们现在做的只是 **Nokia 3320**，好用，但还不是智能手机，更不是 iPhone。

<details>
<summary>Original English</summary>

**Felix Rieseberg**:
*   What is one idea that is underrated? Mhm. MCP connectors are underrated because we correctly, me included, a lot of us have moved from MCPs to CLIs, but there is a lot of things that are quite inherently good about separating the data from the I want to say the execution engine.
*   What is one idea that is overhyped? Not every product needs a chat. That means there's a sidebar on the right with a chat input at the bottom. And I would encourage my fellow AI builders to like think one turn, one one more turn like how do you make this thing useful?
*   If you were starting from scratch today, what would you work on? I would probably go after the long tale of the industry, by which I mean like there's a bunch of Windows 7 devices out there in the world that are doing menial tasks and have a loadbearing role in our society. It's kind of terrifying if you think about it, but the amount of computers that are completely out of reach for any of the modern AI that are doing important work in our society is staggering.

</details>

**Matt Turk**: 太棒了，Felix，非常感谢。这是一次精彩的谈话。

<details>
<summary>Original English</summary>

**Matt Turk**: Great. Well, that's a wonderful place to leave it. Felix, thank you so much. This was an amazing chat. Really appreciate it.

</details>

**Felix Rieseberg**: 谢谢 Matt 的邀请。

<details>
<summary>Original English</summary>

**Felix Rieseberg**: Thank you, Matt, for having me on. It was so nice.

</details>