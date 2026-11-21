---
author: House of El - AI
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=SZgyuBbMy7c
speaker: House of El - AI
tags:
  - ai-transparency
  - model-evaluation
  - consumer-protection
  - tech-regulation
  - software-reliability
title: AI产品透明度缺失与监管困境：混乱舆论下的万亿估值迷局
summary: 视频探讨了AI公司在追求万亿估值的同时，产品透明度与可靠性不足的问题。作者通过个人体验、学术研究及Anthropic与OpenAI的技术细节，指出服务架构变更、静默降级与频繁弃用给开发者带来了巨大成本。作者认为关于AI灭绝与恐慌的极端公众舆论掩盖了基础的消费者权益与监管诉求，使科技巨头得以在缺乏透明度的情况下维持垄断并规避审查。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Sam Altman
  - George Akerlof
  - Serena Booth
  - Miles Brundage
  - Berhane Acnu
companies_orgs:
  - Anthropic
  - OpenAI
  - Stanford University
  - UC Berkeley
  - Carnegie Mellon University
  - HKUST
  - University of Oxford
  - The Alan Turing Institute
  - Lovable
products_models:
  - Claude
  - Claude Opus 5.5
  - ChatGPT
  - GPT-4
media_books:
  - Harvard Data Science Review
status: evergreen
---
### AI产品的基本可靠性与透明度缺失

AI行业渴望获得万亿美元的估值，但它仍然无法为客户提供某种更为基本的东西：一个可用、可靠的产品。而且我越是调查这些公司的运作方式，就越怀疑这种透明度的缺失是否是它们真正有动力去解决的问题。2026年7月，Anthropic在代表Claude付费订阅用户提起的拟议集体诉讼中被列为被告。诉称消费者支付了相同的费用，但幕后的变动降低了服务质量。这些指控尚未在法庭上得到证实，但我对此产生了兴趣，因为在过去几周里，我自己也有着相当相似的经历。

<details>
<summary>Original English</summary>
The AI industry wants trillion-dollar valuations, but it still cannot offer customers something far more basic, a working, reliable product. And the more I investigate how these companies operate, the more I wonder whether that lack of transparency is a problem they're actually incentivized to solve at all. In July 2026, Anthropic was named in a proposed class action lawsuit brought on behalf of paying Claude subscribers. The allegation was that consumers were paying the same fees, but changes behind the scenes had reduced the quality of the service. Those allegations haven't been established in court yet, but I became interested because over the past few weeks, I've been having a rather similar experience.
</details>

我在研究、写作、编程、构思等诸多方面大量使用AI。我有着成熟的工作流、详细的提示词指令，并且对这些模型能做什么和不能做什么有着相当充分的了解。但最近举个例子，Claude Opus 5.5开始需要我投入如此多的额外监督，以至于我常常发现自己在怀疑自己到底有没有节省时间。我精心编写的指令被忽略，模型本应做出的假设它就是不做，到了某一刻，我甚至觉得还不如自己动手做。显然，在这件事上我并不孤单。在Reddit上，大家都在描述完全相同的事情，不仅是Claude，ChatGPT也是如此：遗忘指令、输出不稳定、原本正常运行了数周的工作流突然崩溃。但奇怪的是，还有完全另一群用户表示他们那边一切正常。这就好像不同的人在一种庞大的“ABCDEFG式测试”中接收到了同一产品的不同版本。

<details>
<summary>Original English</summary>
I use AI extensively in my research, writing, coding, ideation, you name it. I have established workflows, detailed instructions, and a reasonably good understanding of what these models can and cannot do. But recently, just as an example, Claude Opus 5.5 started requiring so much additional supervision from me that I generally found myself wondering whether I was saving any time at all. Instructions I'd written carefully were being ignored, assumptions the model should have been making it just wasn't making, and at a certain point I thought just I might as well do this myself. And apparently, I'm not actually alone on this one. Across Reddit, people are describing the exact same thing, not just with Claude, with ChatGPT as well. Forgotten [snorts] instructions, inconsistent outputs, workflows that had been running fine for weeks suddenly falling apart. But the strange bit is this, there is also a completely separate group of users saying everything is fine for them. Almost like different people are receiving different versions of the same product in a giant ABCDEFG style testing.
</details>

那么，我们如何知道究竟发生了什么？这些不再是实验性的玩具了。这些公司需要我们依托它们的工具围绕这些系统构建业务，将它们整合到我们的软件和生活中，并越来越依赖它们来处理重要工作。所以在这个视频中，我想弄清楚当我们甚至无法判断产品是否发生变化时，我们到底在为什么买单。我想看看当开发者把业务押注在他们无法检查的服务上时会发生什么。我想带大家顺着资金流向去探寻，因为这些公司可能确实有理由希望我们对其产生依赖。接着，我想提出一个我认为还没有人足够清晰地问过的问题：

有没有可能，所有关于毁灭的恐慌、裁员的风波、末日的讨论，以及四处蔓延的黑客攻击，有没有可能这种混乱恰恰是这些公司彻底规避监管所需要的环境？

<details>
<summary>Original English</summary>
So, how do we know what's actually happening? These are not experimental toys anymore. These companies need us to on their tools to build businesses around these systems, integrate them into our software and lives, and increasingly rely on them to do the important work. So, in this video, I want to find out what we're actually paying for when we cannot even tell if the product has changed. I want to look at what happens when developers bet their businesses on services they cannot inspect. I want us to follow the money because there is a reason these companies might want us dependent on them. And then I want to ask something that I don't think anyone is asking clearly enough.

Is it possible that all the extinction panic, the lay of drama, the apocalypse discourse, the hacking left and right? Is it possible that chaos is exactly the environment these companies need to avoid being regulated at all?
</details>

### “变笨”的直觉与实证研究

当Anthropic在9月份发布Claude Opus 5.5时，它被宣传为针对编程、专业工作和复杂任务的重大升级。起初它表现非常出色。我的意思是，在我想揍它之前，我通常非常喜欢那个模型，而我是一个非常崇尚非暴力的人。但在数周内，用户开始反映该模型遗忘细节、引入代码错误，需要比以前多得多的手把手指导。到了10月20日，有些人已经彻底切换回GPT了。顺便说一句，这不仅仅发生在Claude身上，这并非单一的Anthropic故事。ChatGPT用户以及OpenAI开发者论坛上的人们也在描述非常类似的情况：推理能力退化、上下文丢失、工作流莫名其妙地失效。

现在，这些人常得到的回复是：“这是技能问题，你不会写提示词，你用了错误的设置。”有时候也许确实如此，对吧？这毕竟不是严格受控的实验。但如果有人已经成功运行相同的工作流数周，突然之间需要两倍的人工介入，“去成为更好的提示词工程师”并不是一个令人信服的答案。它可能是正确的答案，但证据在哪里呢？

<details>
<summary>Original English</summary>
When Anthropic released Claude Opus 5.5 back in September, it was presented as a substantial upgrade for coding, professional work, and complex tasks. And initially, it was brilliant. I mean, I generally adore that model before I wanted to smack it, and I say that as a very non-violent person. But within weeks, users started reporting that the model was forgetting details, introducing bugs, requiring far more hand-holding than before. By October 20th, some had switched back to GPT entirely, and this wasn't just Claude, by the way. This is not an Anthropic story. ChatGPT users and people on OpenAI's developer fora were describing a very similar thing. Deteriorating reasoning, lost context, workflows that just kind of stopped working. Now, the response these people often get is, "It's a skills issue. You don't know how to prompt. You're using the wrong settings." And sometimes, maybe that is true, right? It is not exactly a controlled experiment. But if somebody has been running the same workflow successfully for weeks, and suddenly it requires twice as much hand-holding, "Become a better prompt engineer" is not exactly a satisfying answer. It might be the right answer, but where is the evidence?
</details>

我们这里讲求科学，所以让我们寻找一些证据。2024年，斯坦福大学和加州大学伯克利分校的研究人员在《哈佛数据科学评论》上发表了一项经过同行评审的研究，直接测量了ChatGPT的行为是否随时间发生变化。他们在不同月份针对GPT-4测试了相同的问题，发现该模型遵循明确指令的能力崩溃了。原本应该清晰输出的代码突然被包裹在多余的格式中，导致自动化流程中断。在简单格式化任务上的指令遵循率从99%以上暴跌至1%以下。相同的模型名称，相同的API，底层的模型本身可能同样具备能力，但它就是不再听从你的要求。所以这并不是一件新鲜事。我知道这是一项2024年的研究，但这并非凭空臆想。斯坦福测算出了结果，哈佛发表了论文，对吧？我们并不是凭空想象出来的。

<details>
<summary>Original English</summary>
Well, we're people of science here, so let's look for some evidence. In 2024, researchers at Stanford and UC Berkeley published a peer-reviewed study in the Harvard data science review that directly measured whether ChatGPT's behavior changed over time. They tested the same questions on GPT-4 across different months, and they found that the model's ability to follow explicit instructions collapsed. Code that should have been output clearly was suddenly wrapped in extra formatting that broke automated pipelines. Instruction following on simple formatting tasks dropped from above 99% to below 1%. Same model name, same API, the model may have just been as capable underneath, but it had just stopped listening to what you asked it to do. So, this is not a new thing. I know this is a 2024 study, and it's also not an imaginary thing. Stanford measured it, Harvard published it, right? We didn't just imagine this.
</details>

现在，这是否意味着Opus 5.5具体发生了退化？可能，但并不必然。一位独立开发者创建了Live Nerf，这是一个公开记录的实验，反复对照固定基准测试Opus 5.5。截至11月3日，在经历了三个为期10天的对比周期后，它并未发现具有统计学显著意义的性能下降。这当然有参考价值，但这里有一个盲区：Live Nerf上的那些测试使用的是数学和知识性问题。它们不会生成冗长的对话、创意工作或复杂的软件工程项目。因此，Live Nerf可以告诉你该模型依然会做数学题，但它无法告诉你该模型在长达4小时的编程过程中是否停止了准确阅读你的指令。而这正是大多数抱怨的真正来源。

<details>
<summary>Original English</summary>
Now, does this mean Opus 5.5 specifically has been degraded? Maybe, but not necessarily. An independent developer created Live Nerf, which is a publicly documented experiment that repeatedly tests Opus 5.5 against a fixed baseline. By November 3rd, after three 10-day comparison periods, it had not found a statistically significant deterioration. That matters, of course, but there is a catch. Those tests on Live Nerf use mathematical and knowledge questions. They don't produce long conversations, creative work, or complex software projects. So, Live Nerf can tell you the model still does math, but it cannot tell you whether the model has stopped reading your instructions properly on a 4-hour coding session. And that is where most of the complaints are actually coming from.
</details>

### 幕后变更：模型未动，服务已退化

所以我们陷入了僵局，对吧？用户声称有变化，而一组测量数据显示没有。我们到底该相信谁？有趣的地方就在这里，因为事实证明答案可能两者皆是。2026年4月，Anthropic针对Claude Code相关的投诉发布了一份工程调查报告，他们发现了导致产品变差的三处独立变动，而其中没有任何一处涉及更改模型本身：

首先，他们将默认的推理算力档位（reasoning effort）从“高”调低至“中等”。推理算力是指模型在回答之前进行的计算工作量。更多的推理通常意味着更好的结果，但也意味着更长的等待时间和更高的成本。Anthropic表示部分用户遇到了过长的延迟——这意味着响应时间过长——所以他们直接调低了该参数。那是他们做出的合情合理的工程权衡，然而用户开始反映Claude感觉不那么聪明了，Anthropic最终撤销了这一决定。想想看：模型完全没有改变，但产品却出现了可衡量的性能下降。Anthropic称他们已在产品内部对话框中解释了这一改动，但请注意，这发生在大量用户投诉立刻爆发之后。这在我看来非常可疑，有点像买了瓶无糖百事可乐，结果给你的却是可口可乐，对吧？

第二个变动是一个软件漏洞（bug），导致系统在对话闲置后丢弃其早期的推理过程。因此Claude仍能继续回答，但越来越记不得自己当初为什么做出此前的决定。

第三个变动是他们添加了一条促使回答更加简短的指令。该指令与其他指令产生了不良冲突，从根本上降低了代码编写质量，因此他们将其移除了。

现在我们涵盖了三处变动、三种不同的解释、三项在无人触动模型本身的情况下导致产品变差的方式，而且在人们真正开始投诉之前，没有一项变动向用户公布过。请记住，这就是他们希望你依赖的产品。平心而论，Anthropic公布了这项调查并解释了发生的事情，这是值得肯定的。但请注意这种规律：透明度发生在受损之后，而不是在事前，也不是在事中，而是事后公诸于众。

<details>
<summary>Original English</summary>
So, we're stuck, right? Users say something changed, one set of measurements says it didn't. Whom do we actually believe? Well, this is where it gets interesting because it turns out the answer might be both. In April 2026, Anthropic published an engineering investigation into complaints about Claude code, and they found three separate changes that had made the product worse, none of which involved changing the model itself.

First, they turned down the default reasoning effort from high to medium. Reasoning effort is how much computational work the model does before answering. More reasoning generally means better results, but it also means longer waits and higher costs. Anthropic said some users were experiencing excessive latency. That means it took a long time, so they just dialed it down. That is a legitimate engineering trade-off that they made, except users started saying Claude felt less intelligent, and Anthropic eventually reversed the decision. Just think about that. The model hadn't changed at all, but the product had become measurably worse. Anthropic says they explained the change in an in-product dialogue, but just be mindful of the fact that this happened after an immediate wave of complaints. This is very sus to me. It's a bit like buying a bottle of Pepsi Max and just getting Coca-Cola instead, right? The second change is a software bug that caused the system to discard its earlier reasoning after conversations were left idle. So, Claude could keep answering, but increasingly without remembering why it had made previous decisions. The third one is that they added an instruction to make responses shorter. It interacted badly with other instructions and basically reduced coding quality, so they removed it. And now we've covered three changes, three different explanations, three ways the product got worse without anyone touching the model itself, and none of them were announced to users before people actually started complaining. Remember, this is the product they want you to depend on. To Anthropic's credit, I guess, they published this investigation and explained what happened. But notice the pattern. The transparency came after the damage, not before, not during, exposed.
</details>

还记得我之前提到感觉不同的人接收到了同一产品的不同版本吗？这就是证据：早在2025年9月，Anthropic就承认存在三处基础设施漏洞，断断续续地降低了响应质量。其中一个问题起初影响了不到1%的请求，但随后流量分配方式的调整增加了受影响用户的数量。因此，部分客户收到了劣化的回答，而其他人则体验到了看似正常的表现。想象一下买三瓶可口可乐，两瓶是好的，另一瓶口感就是不行，想想针对这种情况的质量保证吧，对吧？这正是大家目前所描述的规律。一些用户说Opus 5.5坏掉了或者被“暗削”（nerfed），另一些人则说对他们来说挺好的；人们的本能反应是认为某些人在凭空想象，但我们有切实记录的证据表明，由于用户不可见的问题，同一服务确实对不同的人表现出了不同的行为。

<details>
<summary>Original English</summary>
And remember earlier when I said that it felt like different people were receiving different versions of the same product? Well, here is the proof for that. Back in September 2025, Anthropic acknowledged three infrastructure bugs that had intermittently degraded responses. One problem initially affected fewer than 1% of requests, but then changes to how traffic was distributed increased the number of affected users. So, some customers were getting degraded responses, while others experienced apparently normal performance. Imagine buying three bottles of Coca-Cola, two of them are fine, and another one is just not that great. Think about quality assurance for that, right? This is exactly the pattern people are describing right now. Some users say Opus 5.5 is broken or nerfed, as they like to call it. Others say that it's fine for them, and the instinct is just to assume that some people are imagining things, but we have legit documented proof that the same service really has behaved differently for different people because of problems the users could not see.
</details>

### API开发者面临的不透明架构风险

信息量很大，我们来梳理归纳一下。我所担忧的并非公司必须保证每次都给出完全相同的答案。我并不是这个意思，这些系统的运作方式本就不是如此。我担心的是，我们在为一个无法检查其内部运行机制、绝对无法控制其配置、且几乎没有任何手段去检测其变动的产品付费。而这正是这些公司希望使其不可或缺的产品，是万亿估值所依托的基础。当你写一封邮件、写一份文档，或是调试一个好玩的小型临时编码项目时，这已经足够令人沮丧了。但试想一下，你正在为拥有合同约定、财务承诺和法律责任的客户构建实际应用，当该应用依赖于一项行为可能在毫无预警的情况下发生改变、甚至更糟的是发生改变时你根本无法检测到的服务，会发生什么？

现在一个显而易见的疑问是：严肃的开发者不会构建在面向消费者的聊天订阅之上，对吧？他们不会去用 claude.ai 或 ChatGPT 网页端应用，而是使用 API，API允许你指定使用哪个模型、控制设置并围绕它构建自己的应用。这样一来问题肯定就消失了，对吧？

<details>
<summary>Original English</summary>
That was a lot of info, so let's bring it all together. My concern is not that companies should guarantee identical answers every time. I'm not saying that. That is not how these systems work. My concern is that we're paying for a product whose internal workings we cannot inspect, whose configuration we definitely do not control, and whose changes we have almost no ability to detect. And this is the product these companies want to make indispensable. This is what the trillion-dollar valuations are built on. This is frustrating enough when you're writing an email, or you're writing a document, or debugging a cute little side vibe coded project, but just imagine you're building an actual application for customers with contracts, financial commitments, and legal liabilities. What happens when that application depends on a service whose behavior can change without warning, or worse, without you even being able to detect? Now, the obvious question is that serious developers don't build on consumer chat subscriptions, right? They're not going to claw.ai or chat GPT web app. They're going to use an API which lets you specify which model to use, control settings, and build your own application around it. So, surely the problem disappears, right?
</details>

我去查阅了Anthropic关于模型ID和版本控制的文档，起初我发现了一些反驳我自身论点的内容。Anthropic明确保证，当开发者选择固定的模型ID（pin model ID）时，在该标识符的生命周期内底层模型保持不变。权重不会改变，配置不会改变。如果Anthropic发布更新的模型，它将获得一个新的ID。OpenAI也给出了类似的建议：使用固定版本并运行自己的评估基准。这是切实的保护措施，我想对两家公司提供这种机制予以肯定。

但我继续阅读Anthropic的文档时，发现了另一段内容。它解释道，虽然模型本身保持不变，但为其提供服务的周边基础设施可能会改变。负责路由请求、应用安全检查、决定响应生成方式的组件，所有这些实际上都会改变。Anthropic承认，即使模型权重没有变化，这些改动也能改变模型的实际表现。用大白话向大家解释就是：你可以请求同一个模型，发送完全相同的指令，却获得不同的体验，因为模型外围的环境发生了变动。

这绝不仅仅是理论上的担忧，朋友们。2024年，卡耐基梅隆大学和香港科技大学的研究人员发表了一项研究，测试了当底层API更新时提示词会发生什么变化。他们发现，在API更新后，大约59%的提示词与模型组合准确率出现下降；而在这些下降中，有十分之七的降幅超过了5个百分点。这是一个重大问题。因此，上个月管用的提示词这个月可能完全失效，而这并不是因为你做错了什么。

<details>
<summary>Original English</summary>
Well, I went to Anthropic's documentation model IDs and versioning and I found something that initially challenged my own argument on this one. Anthropic explicitly guarantees that when developers select a pin model ID, the underlying model stays fixed for the lifetime of that identifier. The weights don't change, the configuration doesn't change. If Anthropic releases an updated model, it's going to get a new ID. OpenAI makes a similar recommendation. Use pin versions and run your own evaluations. That is real protection and I want to give both companies credit for providing this.

But, when I kept reading Anthropic's documentation, I found another paragraph. It explains that while the model itself stays fixed, the infrastructure around serving it can change. The components that route requests, apply safety checks, determine how responses are generated, all of those can actually change. And Anthropic acknowledges that these changes can alter what the model actually does, even when the model weights haven't changed. Just in plain English for everyone in the audience, you can ask for the same model, send it the same instructions, and get a different experience because something around the models has shifted. And this is not just a theoretical concern, my friends. In 2024, researchers at Carnegie Mellon and HKUST published a study that tested what happens to prompts when the underlying API updates. They found that roughly 59% of prompt and model combinations lost accuracy after an update. And of those drops, seven in 10 were larger than five percentage points. That's a big deal. So, a prompt that worked last month might generally not work this month and it's not because you did anything incorrectly.
</details>

现在，单靠答案不同并不必然证明存在问题。这些系统是概率性的，它们即使在没有任何改变的情况下也可能产生不同的输出。但如果所有这些在你听起来都无关紧要，让我带你了解一个真实的现实场景，以此说明此事的严重性。假设你构建了一个用于阅读合同并标记需要人工审核条款的应用程序。你已经对其进行了广泛的测试，确立了你认为可接受的错误率，并围绕其当前已知的局限性设计了整套流程。顺便说一句，人们为此向你付费；这意味着如果你未能达标，他们也可以起诉你，对吧？然后，服务基础设施发生了一项改动，改变了它遗漏某种特定类型条款的概率。你的应用程序没有改变，你的提示词没有改变，你这边的任何东西都没有改变，你的模型标识符没有改变，但你的业务所依赖的行为现在却发生了偏移，而且你可能还不是第一个发现出问题的人。也许你第一次意识到不对劲，是客户打电话来投诉的时候。再次记住，这些公司希望你构建的正是这种类型的应用程序，那是整套说辞的核心：“请把我们整合到一切之中，请依赖我们，但同时我们可能随时更改产品，而且我们不会告诉你。”拜托！

<details>
<summary>Original English</summary>
Now, different answers alone don't prove a problem necessarily. These systems are probabilistic. They can produce different outputs without anything changing at all. But if all of that sounds like a nothing burger to you, let me guide you through a legit real-world scenario just to illustrate the seriousness here. Imagine you've built an application that reads contracts and flags clauses requiring human review. You've tested this extensively, established acceptable error rates to you, and designed a whole process around its currently known limitations. And people are paying you for this, by the way. That means that they can also sue you if you fail to deliver, right? Then there is a change to the serving infrastructure, which alters how often it misses a particular type of clause. Your application hasn't changed, your prompts haven't changed, nothing on your side has changed, your model identifier hasn't changed, but the behavior your business depends on now has shifted, and you might not be the first person to discover that something's wrong, either. Maybe the first time you figure out something is sus is when a client calls to complain. And remember, again, these companies want you to build exactly this kind of application. That's the whole pitch. Integrate us into everything. Depend on us, please. But also, we might change the product at any time, and we're not going to tell you about it. Come on.
</details>

### 模型退役的跑步机效应与商业动因

还有一个我们尚未讨论的复杂问题：模型并不是永久提供的。Anthropic和OpenAI都会公布退役时间表，所以他们不是在毫无预警的情况下直接关停，但最终你依然必须进行迁移。用一个语言模型替换另一个并不完全等同于更换电视遥控器里的电池。不同的模型以不同的方式遵循指令，会犯不同的错误，有着不同的行为模式。因此你需要测试、进行质量保证，结果发现在你的客户真正在意的12处细节上，替代模型的表现稍有不同。你修复了这些问题，再次测试，而当你完成这些的时候，又有新模型推出了，整个周期又得重新开始。

这就是当前使用AI开发的现实：开发者被锁死在一个持续适应的循环中。2025年，来自牛津大学和艾伦·图灵研究所的一个团队在AAAI（顶级AI学术会议之一）上发表了一篇论文，将此描述为整个“语言模型即服务”（LMaaS）模式的一个根本性问题。他们指出，封闭的API服务破坏了可复现性、可靠性，尤其是信任度，因为用户无法访问内部结构，而提供商只需极短的预先通知就可以弃用模型。所以我们谈论的不再是Reddit上的抱怨，这是经过同行评审的计算机科学界观点，表明这种商业模式本身就制造了问题。

新模型层出不穷，这有利于技术进步，我当然也对此表示支持。但如果你真正想构建稳定的系统，你就像是在一台向上倾斜的跑步机上奔跑，而卖给你跑步机的公司控制着速度。每一次迁移都耗费工程时间，每一次莫名其妙的性能倒退都需要大量排查，每一轮测试都需要有人买单。因此，真正的生产力算式不仅是“AI让这项任务快了多少”，还包括“维持依赖AI的系统正常运转需要多少工作量”。

这里存在着不对称性。提供商控制着基础设施、发布时间表和弃用决策；开发者控制着他们自己的应用，却不得不去适应在别处做出的决定。我不禁在想：为什么？为什么制造着这个星球上最受热捧技术的公司，能够容忍它们对待客户的方式中存在这种程度的失常？要么是它们无法解决，要么可能是它们根本不想解决。而或许所有关于AI毁灭人类文明、AI四处攻击系统的喧嚣以及其他戏剧性事件，恰好是它们所需的掩护，这样就没有人要求它们解决这些问题了。

<details>
<summary>Original English</summary>
There is another complication that we haven't discussed yet, the fact that models are not offered forever. Both Anthropic and OpenAI publish retirement schedules, so they're not switching things off without a warning, but eventually you still have to migrate. And replacing one language model with another is not exactly like upgrading the battery in your television remote. Different models follow instructions differently. They make different mistakes. They behave in different ways. So you test, you run quality assurance, you discover that the replacement behaves slightly differently in 12 places your customers actually care about. You fix those, you test again, and by the time you're done, there is a new model coming and the cycle starts all over again. That is the current reality of developing with AI. Developers are locked into a continuous adaptation cycle. And in 2025, a team at Oxford and the Alan Turing Institute published a paper at AAA, that's one of the top AI conferences, describing this as a fundamental problem with the entire language models as a service problem. Closed API services, they argued, undermined replicability, reliability, and above all, trustworthiness because users have no access to the internals and providers can deprecate models with minimal notice. So, we're not talking Reddit complaints anymore. This is peer-reviewed computer science saying the business model itself creates the problem. New models arrive constantly, which is great for progress, and of course, I'm rooting for that. But if you're actually trying to build something stable, you are running on a treadmill uphill, and the company selling you the treadmill controls the speed. Every migration takes engineering time, every unexplained regression takes a lot of investigation, every round of testing is work somebody has to pay for. So, the real productivity calculation is not just how much faster does AI make this task, it's also how much work does it take to keep the AI dependent system functioning. There is an asymmetry there. The provider controls the infrastructure, the release schedule, and the retirement decisions. The developer controls their own application, but has to adapt to decisions made elsewhere. And I kept thinking, why? Why would companies building the most hyped technology on this planet tolerate this level of dysfunction in how they treat their customers, huh? Either they can't fix it, or maybe they don't want to. And maybe all of the noise about AI destroying civilization, AI hacking things left and right, and the rest of the drama is exactly the cover they need so that nobody asks them to.
</details>

我们将在赞助商Lovable的信息之后深入探讨这一切。大家知道我一直提醒你们即将到来的考试——顺便说一句是用拉丁语考的。上周我告诉大家我们本周会做一次模拟考试，好让你们熟悉考试形式，并明白我对此是非常认真的。所以我用今天视频的赞助商Lovable搭建了一个考试系统。Lovable是一款软件开发工具，它允许你通过日常口语描述需求来构建可运行的应用程序。作为一名计算机科学家，通常我会自己编写这样的系统，但这意味着要处理数据库、托管、身份认证、部署等一整套琐事。而这一次，我只描述了我想要的考试门户，Lovable就将其构建了出来。然后，我上传了我实际YouTube视频的文字记录，让Lovable根据我们讲解过的内容生成题目，并附带答案和解析。我还搭建了一个考官仪表盘，可以在那里查看大家的分数、大家卡在哪些题目上以及每个人的表现——目前所有这些都是匿名统计的。你们的模拟考试现已通过视频描述栏中的链接上线：10道题目，每题四个选项，外加一点拉丁语的小惊喜。如果你想为自己的业务构建点东西，可以通过我描述栏中的链接尝试Lovable，享受5美元折扣。构建这个东西我玩得非常开心。

<details>
<summary>Original English</summary>
We'll get into all of that right after a word from today's video sponsor, Lovable. Now, many of you know that I've been warning you about the examination that's coming, which by the way will be in Latin, and last week I told you we'd be doing a mock exam this week just so you can familiarize yourselves with the format and understand that I'm quite serious about this. So, I built one using Lovable, the sponsor of today's video. Lovable is a software creation tool that lets you build functioning applications by describing what you want in plain language. I'm a computer scientist, so normally I'd build something like this myself, but that means dealing with databases, hosting, authentication, deployment, the works. Instead, I described the examination portal I wanted and Lovable built it. Then, I uploaded transcripts from my actual YouTube videos and asked Lovable to generate questions based on what we've covered, complete with answers and explanations. I also built an examiner's dashboard where I can see your scores, which questions you struggled with, and how everyone performed, all anonymously for now. So, your mock examination is now available through the link in the description, 10 questions, four answers each, and a few Latin surprises. And if you'd like to build something for your own business, you can try Lovable through my link in the description and get $5 off. I generally had a lot of fun building this.
</details>

在插播之前，我们已经确认了开发者确实拥有一些切实的保障机制，尤其是固定模型标识以及公开的退役时间表，但他们依然面临着性能变化、迁移成本以及在自身控制范围之外做出的决策。我想去理解这一切背后的商业动机，因为当我们谈论OpenAI和Anthropic时，有时谈论它们的口吻就好像它们只是恰巧顺便卖卖订阅的研究实验室，但它们当然不是。OpenAI上一轮完成的融资估值为8520亿美元，据报道正在就以1.2万亿美元估值进行新一轮融资展开早期洽谈；Anthropic已向美国证券交易委员会（SEC）提交了S-1招股书，准备进行人类历史上规模可能最大的公开上市之一，目标估值超过2万亿美元。而在整份招股说明书中，正如我们之前讨论过的，那些数字听起来像是凭空捏造出来的：承诺了大约8950亿美元的计算基础设施投资，其中绝大部分无法撤销，诸如此类。这些简单事实根本算不上无可指摘，对吧？

但更重要的是，为了支撑这种规模的估值，投资者需要相信这些公司在未来能够创造巨额收入。而收入并不会因为模型在基准测试中得分优异就凭空产生，对吧？客户必须真正使用这项技术，企业必须加以整合，开发者必须基于此构建应用，而且理想情况下，从服务提供商的角度来看，他们会不断回头购买。在我看来，这正是依赖性在商业上变得必要的地方。当一家公司围绕某个AI提供商构建了核心工作流，迁移转换就变得代价高昂。我们所面对的是新的提示词、不同的系统集成、额外的测试以及错误处理逻辑的变动。经济学家将此称为“转换成本”，它们对企业很有价值，因为当离开的过程极其痛苦时，客户流失的可能性就会降低。这并不能证明有人在故意制造问题，但它确实解释了为什么深度嵌入客户的工作流是一门好生意——尤其在产品并不完美的时候。也许恰恰是在它不完美的时候，因为迁移体验越糟糕，客户黏性就越高。

现在你开始明白为什么透明度实际上可能不在任何人的优先级榜首了，对吧？如果你的客户能够清晰地将你的产品与竞争对手进行比较，转换就会变得更容易；如果他们甚至弄不清楚自己得到了什么，他们往往会选择留下来。难怪没有人急于发布详细的变更日志，对吧？

<details>
<summary>Original English</summary>
Before the break, we established that developers have some real protections, particularly through pinned models and documented retirement schedules, but they still face performance changes, migration costs, and decisions made outside their control. I want to understand the commercial incentives behind all of this because when we talk about OpenAI and Anthropic, we sometimes discuss them as though they're research labs that happen to sell subscriptions on the side, but of course they're not. OpenAI's last close funding round valued it at $852 billion. It's reportedly in early talks for a round at $1.2 trillion, and Anthropic has filed its S-1 with the SEC ahead of what could be one of the largest public listings in human history so far with a target valuation above $2 trillion. And throughout the whole prospectus, as we've discussed before, the numbers sound like something pulled out of a hat. Committed to roughly $895 billion in computing infrastructure, the vast majority of which cannot be canceled, yada yada. Simple stuff that's not damning at all, right? More importantly though, to justify valuations at this scale, investors need to believe these companies can generate enormous future revenue. And revenue doesn't appear because a model scores well on a benchmark, right? Customers have to actually use the technology. Businesses have to integrate it, developers have to build on it, and ideally from the provider's perspective, they keep coming back. This is where dependency becomes commercially necessary in my view. When a company builds an important workflow around an AI provider, switching becomes expensive. We're talking new prompts, different integrations, additional testing, changes to failure handling. Economists call this switching costs, and they're valuable to a business because customers are less likely to leave when leaving is painful. That doesn't prove anyone is deliberately creating problems, but it does explain why getting deeply embedded in customer workflows is good business, maybe especially when the product isn't perfect. Maybe especially when it isn't perfect, because the worse the migration experience, the stickier the customer. And now you start to see why transparency might not actually be at the top of anyone's priority list, right? If your customers can clearly compare your product to a competitor's, switching becomes easier. If they can't tell what they're even getting, they tend to stay put. Well, no wonder nobody's rushing to publish detailed change logs, right?
</details>

最让我触动的部分是我们之前谈到的那台跑步机。开发者不断地迁移、测试、修复、适配，所有这些工作都需要消耗更多的AI：调用更多的API去测试新模型，耗费更多的计算资源进行质量保证，消耗更多的Token去重写先前失效的提示词。这种业务流转本身，在一定程度上制造了对引发该流转的产品的需求。弃用模型不仅是一种麻烦，听起来更像是一台收入引擎。每一次模型退役都在把资金重新注入系统。我不知道这是有意为之还是无心之举，但对我而言，这其中的经济学逻辑令人难以忽视。

顺便说一句，金融市场对此也并非完全信服。几天前，雅虎财经计算出芯片和存储类股票自10月6日以来蒸发了大约3.7万亿美元的市值。我并不是说这证明了AI正在走向失败，但它确实表明整个投资叙事已经变得多么敏感。顺带提一句，山姆·奥特曼最近声称个人电脑自带内存是低效的，数据中心可以更好地对其进行管理。由于这句话实在太愚蠢，他后来当然收回了该言论。这与本期视频无关，但我确实希望你们注意到这些人是如何一本正经地胡说八道的。顺便说一句，如果你一路跟上了所有这些数字，在经历了这场疯狂之后，我奖励你这只喝着橙汁的可爱小红熊猫。

<details>
<summary>Original English</summary>
But the part that got to me is that treadmill that we talked about earlier. Developers constantly migrating, testing, fixing, adapting. All of that works requires more AI, more API calls to test the new model, more computer run quality assurance, more tokens to rewrite prompts that broke before. The churn itself generates in part the demand for the product causing the churn. Depreciation is not just an inconvenience, it's starting to sound like a revenue engine. Every model retirement puts money back into the system. I don't know if this is intentional or not, but the economics are a little bit hard to ignore for me. The financial markets are not entirely convinced either by the way. A few days ago, Yahoo Finance calculated that chip and memory stocks had roughly $3.7 trillion in market value since October 6th. I'm not saying that proves AI is failing, but it does show how sensitive this entire investment story has become. Just as an aside, Sam Altman recently suggested that it's inefficient for personal computers to have their own RAM, and that data centers could manage it better. He walked it back of course because of how dumb of a thing to say that is. That has nothing to do with this video, but I do want you to notice the kind of nonsense these people say with a straight face. If you're still following all of these numbers by the way, I award you this tiny red panda cutie with all orange aid after dealing with this madness.
</details>

### 末日论与极度恐慌如何掩盖消费者维权与监管

抛开可爱动物不谈，我刚才展示给你们的一切都引向了一个问题，我想你们大概已经猜到了：你真的认为这些公司会主动提供透明度吗？因为我对此越来越怀疑了，而通常这种情况下就需要监管介入。然而围绕AI的公众对话——至少在我看来——已经变得如此歇斯底里，完全沉浸在“这些系统究竟会拯救我们还是毁灭我们”的争论中，以至于没有人去问那些乏味的基础问题。我开始觉得这可能根本不是偶然。

在展开讨论之前，我首先想声明清楚一点：我认为担忧AI安全有着充分合理的理由。网络攻击、自主系统、就业冲击，以及未来更强大AI出现的可能性——我花了很多时间阅读关于这些风险的研究，也做过相关的视频。我绝不是在贬低或忽视这些风险。但我对当前该话题上的公众舆论演变越来越感到沮丧，因为我认为它实际上是在服务于我们本应进行审查的那些公司。一方面，AI被吹捧为能解决人类面临的一切问题；另一方面，它又被渲染为将毁灭文明、消灭所有工作，并在明天下课吃午饭前开启末日审判。而与此同时，人们今天正在为实际的产品买单，试图弄清楚随着购买而来的究竟有哪些权利和保障，却几乎没有任何人在严肃地讨论这一点。

<details>
<summary>Original English</summary>
But cute animals aside, everything I just showed you leads to one question, and I think you already probably know what it is. Do you really think these companies are going to volunteer transparency on their own? Because I'm starting to doubt this, and normally this is where regulation steps in. Except the public conversation about AI, at least in my view, has become so hysterical, so consumed by whether these systems will save us or destroy us, that nobody's asking the boring questions, and I'm starting to think that might not actually be an accident.

Now, before I get into this, I want to be clear about something first. I think there are legitimate reasons to worry about AI safety. Cyber attacks, autonomous systems, employment disruption, the possibility of much more capable AI in the future. I have spent a lot of time reading the research on those risks. I've made videos on that. I am not dismissing it in any way, but I am growing increasingly frustrated with what the public conversation is becoming on this topic because I think it's actually serving the companies we should be trying to scrutinize instead. On one side, AI is going to solve every problem humanity has ever faced. On the other, it's going to destroy civilization, eliminate every job, and start the apocalypse before lunch tomorrow. And meanwhile, people are paying for actual products today trying to work out what rights and protections come with that purchase, and almost nobody is talking about this seriously.
</details>

这就是我认为正在发生的事情，我想非常谨慎地陈述，因为我并不是在指控某种阴谋，我并不确切知道背后是怎么回事，我只是想思考各方利益动机可能是如何结合的。再次强调，这些纯属我个人的观点。我认为关于AI的公众舆论越是混乱，留给那些枯燥而关键的问题的空间就越小。比如：“作为付费客户，你们究竟欠我什么？”当话语权被灭绝情景和乌托邦承诺所主导时，由于其他议题表面上看起来如此重大，这个问题就被当成不值一提了。当机器人都可能毁灭人类的时候，你怎么还能去关心模型弃用呢？天呐！

我不认为这些公司需要去刻意制造混乱，我认为它们只需要暂时不去解决混乱。因为在当前这个监管迟缓、公众情绪在恐惧与狂热之间剧烈摇摆、无人能对真正的风险达成共识的环境中，恰恰是最适宜去追逐万亿估值的环境，而且期间根本不会有人要求你提供产品的基本透明度。无论这是否属于刻意为之，在我看来结果都是一样的：杂音淹没了关键信号。而这个信号其实很枯燥，信号不过就是：“我的产品变了什么？你们为什么不告诉我？”

<details>
<summary>Original English</summary>
Here is what I think is happening, and I want to be very careful about how I say this because I am not alleging a conspiracy. I don't actually know what is going on. I just want to think about how the incentives might be aligned. And again, these are just my own opinions. I think the more chaotic the public conversation about AI becomes, the less space there is for the boring essential questions. Questions like, what do you actually owe me as a paying customer? When the discourse is dominated by extinction scenarios and utopian promises, that question gets treated as beneath the conversation because the rest of it is apparently so consequential. How can you worry about model deprecation when the robots might kill everyone? Oh my god, L. And I don't think these companies need to manufacture the chaos. I think they just need to not solve it temporarily because the current environment where regulation is slow, where public sentiment swings between terror and euphoria, where nobody can agree on what the actual risks are, that environment is precisely the one in which you can pursue a trillion-dollar valuation without anyone demanding basic transparency about your product. Whether this is intentional or not, the result to me appears to be the same. The noise drowns out the signal, and the signal is kind of boring. The signal is just what changed in my product and why won't you tell me?
</details>

目前确实出现了一些监管举措。欧盟的《人工智能法案》（AI Act）包含了关于透明度、模型文档记录和风险管理的义务。根据其关于通用人工智能的规定，提供商必须对其模型进行文档记录，并向顺位下游的开发者提供特定信息。2026年8月，Anthropic解释了其为Claude生成的文本添加数字水印的计划，部分原因正是为了遵守欧洲的透明度规定。所以，监管机构目前似乎足够重视去追踪AI是否代写了我们的文章，但为什么他们不够重视去追踪我们花钱购买的AI是否发生了变更？服务提供商是否应当披露对性能产生实质性影响的改动？当基础设施变动可能导致开发者已部署的应用崩溃时，他们是否应该获得有实质价值的信息？朋友们，这些不是关于超级智能的问题，这些都是关于消费者权益保护的问题。

一如既往地，像我这种书呆子一样，我深入查阅了文献本身，阅读了关于该主题的多篇论文。我想分享一下它们阐述的内容，因为研究这些问题的人不仅仅是在凭空感受，他们正在开展实验，发表同行评审成果，并实际为监管应该是什么样构建论据体系。所以我想用通俗的语言梳理他们的发现。请跟紧我，最后会得出逻辑清晰的脉络。

<details>
<summary>Original English</summary>
Now, there is some regulation happening. The European Union's AI Act contains obligations around transparency, model documentation, and risk management. Under its general-purpose AI provisions, providers have to document their models and provide specified information to downstream developers. And in August 2026, Anthropic explained its plans to watermark text produced by Claude, partly to comply with European transparency requirements. So, regulators right now appear to care enough to track whether AI wrote our essays, but why don't they care enough to track whether the AI we're paying for has changed? Should a provider have to disclose changes that materially affect performance? Should developers get meaningful information about infrastructure changes that could break applications they've already deployed? These are not questions about superintelligence, my friends. They are questions about consumer protection. As always, like the nerd I am, I went into the literature itself and read several papers on this topic, and I want to share what they said because these people working on this are not just vibing. They're running experiments, publishing peer-reviewed work, and actually building the case for what regulation should look like. So, I want to walk through what they found in plain words. Stay with me. There will be an order in the end.
</details>

### 学术界的法律与市场视角：消费者保护与信息披露

2025年，一位名叫塞雷娜·布思（Serena Booth）的研究人员在机器学习顶级会议ICML上发表了一篇论文，论证如果我们能够切实执行现有法律，现存的消费者权益保护法就已经是一项强有力的AI安全工具。我们无需从零开始构建一套全新的法律框架。人类社会现存用于保护买方免受信息占优的卖方侵害的法律完全可以适用于此，她当然是对的。欧洲有关数字内容和服务的法规已经确立了企业修改向消费者提供的服务时所必须满足的条件：提供商可能必须解释改动原因、提前发出通知，并允许客户终止服务。我们并不是从一张白纸起步。几个世纪以来我们一直在规范商业关系，我实在难以理解为什么仅仅因为AI是一门新技术，我们在这一层面的诉求就要降低。

1970年，经济学家乔治·阿克洛夫（George Akerlof）发表了一篇关于当买方无法区分优质产品与劣质产品时会发生什么的论文。结论是市场会退化：优质卖家离场，因为他们无法证明自身的品质；劣质卖家留下来，因为没有人能看出区别。这个人因此获得了诺贝尔奖，那篇论文就是《柠檬市场》（The Market for Lemons）。2026年，来自哥廷根、代尔夫特和哥伦比亚大学的研究人员测试了该理论是否特别适用于AI领域。他们在人机交互顶级会议CHI上发表了该论文，发现的情况与阿克洛夫的预测完全一致：在缺乏信息披露的情况下，用户无法合理校准对AI的依赖程度；当系统表现良好时他们使用不足，而在系统表现糟糕时他们又过度依赖。但是哪怕仅仅是做出了披露——仅仅告诉人们系统的准确率——就能显著改善结果。因此，透明度绝非锦上添花的附属品，它是阻止市场走向腐烂的核心要素。

<details>
<summary>Original English</summary>
In 2025, a researcher named Serena Booth published a paper at ICML, that's the top machine learning conference, arguing that existing consumer protection law is already a powerful tool for AI safety if we can actually enforce it. We don't need to invent entirely new legal frameworks from scratch here. The laws societies already have for protecting buyers from sellers who know more than they do can apply here, and she's right, of course. European rules governing digital content and services already establish conditions under which companies can modify services supplied to consumers. Providers may have to explain changes, give advance notice, and let customers leave. We're not starting from here. We've been regulating commercial relationships for centuries now, and I'm struggling to understand why AI being new should make us less demanding on this front. In the year 1970, the economist George Akerlof published a paper about what happens when buyers can't tell good products from bad ones. The conclusion was that the market degrades. Good sellers leave because they cannot prove their quality. Bad sellers stay because nobody can tell the difference. This guy won the Nobel Prize for it. The paper market for lemons. In 2026, researchers at Göttingen, Delft, and Columbia tested whether that theory applies to AI specifically. They published this paper at CHI, which is the top conference on human-computer interaction, and they found exactly what Akerlof had predicted. Without disclosure, users cannot calibrate their reliance on AI. They underuse it when it's good and over-rely on it when it's bad. But even disclosure, just telling people the accuracy of the system, substantially improved outcomes. So transparency is not a nice to have. It is what stops the market from rotting.
</details>

今年早些时候的另一篇论文由迈尔斯·布伦戴奇（Miles Brundage）及50多位合著者共同发表，指出前沿AI目前受到的独立审查甚至少于普通消费品或财务报告，比烤面包机受到的审查还要少。他们的提议是建立一套以上市公司审计方式为蓝本的结构化审计框架，因为眼下我们完全是在凭空听信这些公司的一面之词；而正如我们所见，它们的话有时只是在问题发生数周后发布的事后复盘报告。

2026年5月，伯哈内·阿克努（Berhane Acnu）与其合作者在技术公平与问责领域的顶会FAccT上发表了一项研究，梳理了AI公司实际上如何影响监管制定。他们构建了一套包含27种不同企业俘获（corporate capture）机制的分类学体系，分析了100篇新闻报道，并在现实运作中发现了这27种机制生效的249个具体案例。其中最常见的策略，就是将监管塑造成对创新和国家利益的威胁。

<details>
<summary>Original English</summary>
Another paper from earlier this year, a paper by Miles Brundage and more than 50 co-authors, argues that frontier AI currently receives less independent scrutiny than ordinary consumer products or financial reporting. Less scrutiny than a toaster. Their proposal is a structured auditing framework modeled on how we audit public companies because right now we're taking these companies at their word, and as we've seen, their word sometimes comes in the form of postmortem published weeks after the problem. In May 2026, Berhane Acnu and collaborators published a study at FACT, that's the leading conference on fairness and accountability in technology, that mapped how AI companies actually influence regulation. They built a taxonomy of 27 different mechanisms of corporate capture, analyzed a hundred news articles and found 249 instances of those mechanisms in action. And the most common strategy was framing regulation as a threat to innovation and national interest.
</details>

### 理性诉求与呼吁：破除恐惧，要求透明度

如果你完整听完了所有这些内容，干得漂亮。让我们再看一眼这只可爱的小水獭。我打算让这个视频画面多播一会儿，因为在上一个视频里你们反映它放得太短了。

没有任何人能够合情合理地要求一个概率性系统永远给出完全相同的答案。我在这里说的绝不是这个意思。监管机构不应该阻止公司修复错误或发布更好的模型，当然不应该。而且我认为也不应该强迫公司公布其专有的模型权重，我并不是这个主张。但是朋友们，强行索要一家公司的商业机密，与要求它在发生实质性变更时予以告知，这二者之间有着天壤之别。

如果提供商发布切实的性能变更通知会怎样？如果它们公开记录重大的配置变更，提供清晰的版本历史，赋予开发者足够的信息去排查意料之外的性能退化呢？试想一下，当一个模型退役时，该公司能够协助你进行迁移，特别是如果它在过去的6个月里一直在劝说你围绕该模型构建业务的话。这能解决一切问题吗？当然不能。但这将开始弥合公司对其产品的认知与允许客户了解的信息之间的鸿沟。而恰恰正是这类监管，在整个公共对话都被“AI是否会毁灭人类”或者“老天保佑千万别有人用AI写了封邮件”的极度恐慌所吞噬时，变得难以被提出和推动。再次说明，朋友们，我无法百分之百断言，但这对于那些宁愿完全不受监管的公司来说，确实显得相当便利。

<details>
<summary>Original English</summary>
If you sat through all of that, well done. Let's watch this cute little otter again. I'm going to leave this video play for a while as in the last one you told me that it was too short. Nobody can reasonably require a probabilistic system to produce identical answers forever. That is not what I'm saying here. Regulators shouldn't prevent companies from fixing bugs or releasing better models. Of course not. And I don't think companies should be forced to publish their proprietary weights either. I'm not saying that. But there is a vast difference, my friends, between demanding a company's trade secrets and asking it to tell you when something material has changed. What if providers publish meaningful performance change notices, huh? What if they publicly document that major configuration changes, offered clear version histories, gave developers enough information to investigate unexpected regressions? Imagine that when a model gets retired, the company helps you move, especially if it's been the last 6 months telling you to build your business on that model. Would that fix everything? Of course not. But it would start to close the gap between what the company knows about its products and what a customer is allowed to know. And that is precisely the kind of regulation that becomes harder to demand when the entire our conversation is consumed by whether AI will destroy the human race or God forbid if somebody used AI to write an email, the absolute horror of that. This, my friends, again, I cannot say for certain, but it does feel pretty convenient for the companies who would rather not be regulated at all.
</details>

我在网上看到的反AI情绪已经变得如此喧嚣，以至于我真的开始为此感到担忧。而我是作为一个赞同其中许多不满情绪的人说这番话的。我在许多视频中都说过，这些公司的融资方式存在真正的财务脆弱性；从网络安全角度来看存在真实的危险；也有严重的环保问题。我向你们保证，我绝没有否定这些问题中的任何一个。但舆论氛围已经变质了。我的意思是，AI触及的一切突然间都被视作拙劣低劣，包括代码在内。开发者甚至在探讨如何隐瞒他们在部分代码库中使用了AI模型的事实，就好像使用一个真正能帮助你编写更好软件的工具是一件可耻的事情一样。这已经不是健康的怀疑态度了，这是恐惧。

恐惧不会带来审慎的监督，恐惧只会全盘排斥。我不断回到整个视频的核心问题：*Cui bono?*（谁从中获益？）因为受益的绝不是我们。一个大家过于恐惧和愤怒以至于无法对AI展开批判性探讨的环境，恰恰是这些公司面临更少审查而非更多审查的环境。歇斯底里产生不了监管，只会产生混乱。正如我们所见，混乱恰恰是那种你可以追逐2万亿美元估值、却不会有太多人要求你提供产品基本透明度的环境。

因此，我的呼吁如下：对于我那些不具备太多技术背景的观众，请保持开放的心态，请继续阅读，请继续学习，不要让喧嚣取代你自己的判断；而对于技术背景更深厚的观众，请与我一起承担起责任，向身边不一定具备技术背景的人清晰地解释这些事情。因为没有人能从恐惧中获益，除了那些宁愿不受任何质询的公司。我们需要把透明度作为产品的一部分。那是我们理应去要求的，但如果我们忙于恐惧它，我们就无法提出这项要求。

如果你想了解AI是否真的会毁灭我们所有人，我其实梳理过这背后真正的科学事实。就是你屏幕上正在显示的这个视频，那是我建议大家接下来观看的视频。

<details>
<summary>Original English</summary>
The anti-AI sentiment I'm seeing online has become so loud that I'm generally starting to worry about it. And I say that as somebody who agrees with a lot of the frustrations. I've said in many of my videos that real financial precarity in how these companies are funded. There are genuine dangers from a cybersecurity perspective. There are serious environmental concerns. I am not dismissing any of that, I promise you. But, the discourse has become something else. I mean, everything AI touches is suddenly sloppy, including code. Developers are asking how to hide the fact they used an AI model on part of their codebase, as if using a tool that genuinely helps you build better software is something to be ashamed of. That is not healthy skepticism, that is fear. Fear does not scrutinize, fear just rejects. And I keep coming back to the question from this entire video. Cui bono? Who benefits from that? Because it ain't us. An environment where people are too afraid angry to engage critically with AI is an environment where these companies face less scrutiny, not more. The hysteria doesn't produce regulation, it produces chaos. And as we've seen, chaos is exactly the kind of environment in which you can pursue a $2 trillion valuation without that many people demanding basic transparency about your product. So, here's what I'm asking. To my less technical viewers, please keep an open mind. Please keep reading. Please keep learning. Don't let the noise replace your own judgment. And to my more technical viewers, please join me in taking the responsibility to explain this stuff clearly to the people around us who don't necessarily have the technical background. Because nobody benefits from fear except the companies that would rather not be questioned. We need transparency as part of the product. That is what we should be demanding, and we cannot demand it if we're too busy being afraid of it. If you want to understand whether AI really will kill us all, I actually looked at the real science behind this. That's the video on your screen right now. That's the video that I would watch next.
</details>