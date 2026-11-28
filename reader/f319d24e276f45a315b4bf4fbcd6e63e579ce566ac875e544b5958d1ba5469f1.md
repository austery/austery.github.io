---
author: a16z
date: '2026-11-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RwYz8XhZiu0
speaker: a16z
tags:
  - ai-impact
  - drug-discovery
  - life-sciences
  - model-capabilities
title: OpenAI 在生命科学领域的战略与 AI 赋能药物研发的进展
summary: OpenAI 的生命科学团队通过训练模型、开发产品及与学术界合作，旨在加速基础科学研究并缩短药物研发周期。通过收购 Orchestra Bio，OpenAI 旨在解决模型能力悬垂问题，提供更高效的工具以管理复杂的监管申报数据。此外，团队强调通过“受信访问”机制确保生物安全，并预测 AI 将显著放大生物技术领域的专业能力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - A16Z
  - Orchestra Bio
  - Moderna
products_models:
  - GPT Rosalind
  - Codex
  - '03'
media_books: []
status: evergreen
---
<!-- chunk 1/2 -->

哪怕是世界上最顶尖的医生，有时也不得不告诉患者，他们所患的病症目前尚无任何治疗方法。
<details><summary>Original English</summary>
Even the best doctors in the world sometimes have to tell their patients that no treatment exists for the condition that they have.
</details>

>> OpenAI 的使命是确保通用人工智能（AGI）惠及全人类。这个女孩在九岁时就生病了，她为了确诊等待了 20 年。直到我们将 03 部署到她的病历档案中，我们才弄清楚疾病的根本原因是什么。该模型在理解临床信息以及帮助拓展临床诊疗专业能力方面，已经达到了超人类水平。
<details><summary>Original English</summary>
>> OpenAI's mission is to ensure [music] that AGI benefits all humanity, which was this girl became sick when she was nine and she waited 20 years for a diagnosis. And it [music] wasn't until we deployed 03 to her file that we figured out [music] what the underlying cause of disease was. The model's already superhuman at the ability to understand clinical information and [music] to help scale the expertise of clinical care.
</details>

>> 如果 OpenAI 能挥动魔法棒并说，我希望存在这类数据集来帮助我们把模型打造得更好。
<details><summary>Original English</summary>
>> If open AI could wave a magic wand and say, I wish these kinds [music] of data sets existed to help make our models even better.
</details>

>> 在模型训练方面，数据是最大的瓶颈之一。所以我觉得
<details><summary>Original English</summary>
>> Data is one of the biggest bottlenecks [music] when it comes to training models. And so I think
</details>

### 开篇与 OpenAI 生命科学战略

>> 大家好，我是 Jay，a16z 的合伙人，负责领导健康和生物技术公司的投资。我的合伙人 Jorge 也来到了现场，同时我们的朋友、来自 OpenAI 生命科学团队的 Joy 和 Ashoka 也加入了我们。欢迎两位。
<details><summary>Original English</summary>
>> Hi everyone, I'm Jay, a partner at A16Z where I lead investments in health and biotechnology companies. I'm joined by my partner Jorge and we are joined by our friends Joy and Ashoka of OpenAI Life Sciences. Welcome.
</details>

>> 感谢邀请我们。
<details><summary>Original English</summary>
>> Thanks for having us.
</details>

>> Joy，我想直接切入正题。几周前我很有幸邀请到了你的同事、OpenAI 健康部门负责人 Karen Singal 来到播客，我们当时讨论了在每个人口袋里实现无限速率医疗智能的前景，这听起来令人惊叹，而且似乎离现实也不太遥远了。但即使是世界上最好的医生，有时也不得不告诉患者，他们所患的疾病目前没有任何治疗方法。跟我们聊聊你们在 OpenAI 正在做的工作吧。你是否感到乐观：终有一天，借助你们正在构建的工具，AI 将帮助我们为现存的每一种病症找到并设计出治疗方法？
<details><summary>Original English</summary>
>> Joy, I want to dive straight into it. I uh was fortunate to have uh your colleague Karen Singal, the head of OpenAI Health on the podcast uh just a few weeks ago and we talked about the promise of medical intelligence at unlimited rates in everyone's pocket which sounds amazing and seems like we're not too far away from from happening. But even the best doctors in the world sometimes have to tell their patients that no treatment exists for the condition that they have. Tell us about the work you're doing at OpenAI. Are you optimistic that one day with the tools you're building, AI will help us identify and design a treatment for every condition out there?
</details>

>> 是的，我认为这个目标大概是该领域大多数人最为兴奋的。往大处看，OpenAI 在生命科学领域的总体战略和目标是什么呢？我想说其实有三大支柱。第一是训练最好的模型。这是我们从一开始就一直在做的事情。然后是打造最好的产品，以加速科学家和制药商的工作，这也是 Ashoka 发挥作用的地方。第三点是真正与学术界、生物科技公司和制药公司合作来展示这些能力，去展现 AI 能够带来的实实在在的益处。OpenAI 的使命是确保 AGI 惠及全人类。我认为生命科学是我们能为世界带来的最明确、最无可争议的善行之一，也可能是最具影响力的事情，因此我们在这里投入了大量的资金、算力和用于训练模型的 GPU。所以，是的，我认为真正的北极星是达到这样一个节点：我们能看到自己正在显著加速基础学术科学并真正推动那里的前沿，同时也能看到在确定靶点乃至将成果推向并穿透临床流程的时间线大大缩短。
<details><summary>Original English</summary>
>> Yeah, I think this is a goal that I would say most people in the field are the most excited about. I think zooming back out, you know, what is OpenAI's general strategy and goal in the life sciences. And I would say there's really three pillars. The first is to train the best model. This is the the thing that we have been doing since, you know, the very beginning. Um and then also to make the best product to accelerate the work of scientists and drug makers and that is where Ashoka comes in. And the third one is to really demonstrate these capabilities um in collaboration with um academics with um biotechs and pharma companies to showcase you know what real good that AI can do. So open AI's mission is to ensure that AGI benefits all humanity. I think the life sciences is you know one of the most unambiguous uncontroversial goods that we can do for the world and possibly the most impactful and so we have made a ton of you know huge investments here in terms of both capital um hack uh GPUs to train the models. So yeah, I I think you know the the Northstar really is getting to a point where we can see we are meaningfully accelerating both basic academic science and really pushing the frontiers there and also seeing accelerated timelines and um identifying targets all the way to bringing things um to and through the clinic.
</details>

### 工具构建与收购 Orchestra Bio

>> 你们正在为科学家构建工具。Joy，你和你的团队围绕 GPT Rosalind 开展了大量工作，为科学家构建了一系列工具。而 Ashoka 来到这里的缘由是，Ashoka 是 Orchestra Bio 的创始人，而该公司最近被 OpenAI 收购，这也是为了拓展你们向科学家提供的工具规模。跟我们讲讲你们一直在打造的工具，并谈谈为什么收购了 Ashoka 的公司。
<details><summary>Original English</summary>
>> You all are building tools for scientists. Joy, you've built uh you and your team have built a lot of the work around GPT Rosalind building a number of tools for scientists. And then the reason why Ashoka is here is Ashoka was the founder of Orchestra Bio who uh was recently acquired by by OpenAI also to expand the amount of tools that you're making available for scientists. Tell us about the tools that you've been building and tell us why you acquired Ashoka's company.
</details>

>> 好的。我认为当今模型存在的一个最大现象就是我们所说的“能力悬垂”（capability overhang）。这意味着模型能做很多事情，但没有人知道，因此也就没有人能够获取这些能力。举例来说，最初的 AI 产品就像 ChatGPT，那个外壳基本上是一个界面，一个让你能更轻松地与模型对话的聊天界面。后来我们有了 Codex，那是下一个迭代版本，它让模型既能控制你的电脑，又能成为程序员非常出色的副驾驶（co-pilot）。而我们真正想做的是，为科学家、生物科技和制药领域带来一个像 Codex 对程序员那样出色的工具。我们在训练 GPT Rosalind 时，模型在化学和结构生物学方面都具备所有这些非常有趣的能力，我们在基准测试中看到模型表现非常出色，但我们反复看到的一个问题是，大家不知道如何使用这些模型，甚至不知道该用什么提示词、该问什么问题。我认为这正是需要围绕模型打造一个异常出色的产品或工具外壳的地方，从而真正让人们能够获得这种能力。这正是 Ashoka 加入的契机，因为当时我们拥有一个模型，却没有很好的使用途径；而 Orchestra 正在构建出色的产品。我认为我们在路线图以及对 Orchestra 在如何加速发现和开发未来的愿景上高度一致。所以，我们就是这样建立联系的。
<details><summary>Original English</summary>
>> Yeah. Um, I think one of the biggest things that we see with models today is that there's what we call a capability overhang. And this means that there's a lot of things the models can do, but no one knows about it. And so, no one has access to that. And so, for example, you know, thinking about um the original AI product was like chat GBT that harness was basically a interface, a chat interface allowed you to talk to the model so much more easily. Um and then we have codeex that was kind of the next iteration that allowed the model to you know both control your computer and also um become a really good co-pilot for programmers and what we really want to do is bring something that is as good as codeex for um coders um for to scientists and to biotech and pharma. So I think when we are training GPT Roseland we have all these like interesting capabilities in the model in both you know chemistry and structural biology we see that the models are doing really well on the benchmarks but one uh repeated theme we've seen is that people don't know how to use the models they don't know even like what prompts to use what questions to ask um and I think this is really where you need a exceptionally good product or good harness around the model to really make that capability accessible to people um and this is where Ashoka came in because I think we we had a model um there wasn't a great way to use it. Orchestra was building amazing product. I think we're very aligned in the road mapap the future that we see for orchestra on how to accelerate discovery and development. So yeah that that was kind of how we got connected.
</details>

>> 好的，Ashoka，让我们请你加入对话。在 Orchestra 时，你和团队打造了一些了不起的工具，帮助科学家与合作伙伴进行协调，把单个药物研发项目内发生的工作全部串联起来，并跨药物研发项目展开协作。为什么加入 OpenAI 如此合情合理？与 Joy 和团队一起工作感觉如何？
<details><summary>Original English</summary>
>> Okay so Ashoka let's get you in the conversation at orchestra. You and the team built some amazing tools to help coordinate scientists with their partners and the work that's happening all in a single drug program and then work across drug programs. Why did joining OpenAI make so much sense and uh what's it been like working with Joy and the team?
</details>

>> 好的。回到让 AGI 惠及全人类的使命。回顾我个人的生活和经历，年轻时我父亲是一名医生，他说过：我希望等到你从医学院毕业时——可惜我从未走上那条路，但我认为我现在可能弥补了这一点——我们回头看我现在给患者的治疗手段（他是一名肿瘤科医生），会觉得它们是极其原始野蛮的。我认为我们已经看到了令人难以置信的进步，诸如抗体、mRNA、细胞基因疗法等新平台技术的出现。我深信 AI 也是这些能力之一。我成长过程中学到的另一件事是，人们在医疗系统中的体验，受到诊治他们的临床医生专业能力的极大限制。在我自己的经历中，以及我许多与我父母交谈过的朋友的经历中，他们是世界一流的，愿意为你花时间，理解你的病情。正如你们与 Karen 和 OpenAI 团队交流时提到的，在临床护理专业能力出现短缺的情况下，模型在理解临床信息和帮助扩展临床护理专业能力方面，已经达到了超人类水平。因此，在构建和扩展 Orchestra 的过程中，我的兴趣一直在于：你如何推动药物的前沿向前发展，以及如何构建使整个行业能够发现和开发药物、并专注于完成最佳工作的技术。而能够将如何运行研究、药物项目、研发活动和临床试验的能力，与每隔 3 到 4 个月就会涌现出令人惊叹的新能力的最前沿模型结合在一起——我确实认为这是一个拐点：我们如何将运行药物项目、临床试验等能力带给整个行业，并使之与我们正在开发的前沿模型能力紧密结合起来。
<details><summary>Original English</summary>
>> Yeah. So, kind of coming back to the mission of you know AGI to benefit all of humanity. I think when I think about my own personal life and experience, uh, when I was younger, you know, my dad's a physician and he said that, you know, I hope that, you know, by the time that, you know, you, you know, get out of medical school, which I unfortunately never went down that pathway, but I think I've maybe made up for it now. Uh, that we'll look at the treatments that I'm giving my patients, he's a cancer doctor, as being barbaric. Uh, and I think we've seen such incredible advances in terms of new platform technologies, you know, antibodies, mRNA, cell gene therapies, and so on. uh and I truly believe AI is one of those capabilities. The other thing that I learned growing up is just that the experience people have with the health system uh is so limited by the expertise of the clinician treating them. So, you know, in my experience and the experience of probably many of my friends who have talked to my parents, um you know, they're world class. They give you the time of day. They understand your condition. And you know as you talked to Karen and the open eye team it's you know the model is already superhuman at the ability to understand clinical information and to help scale the expertise of clinical care uh when we have a shortage of that. So you know in building and scaling orchestra you know my interest has been you know how do you push the frontier of drugs forward and how do you build technology that enables the industry uh to discover and develop drugs uh and focus on on on doing their best work. um and the opportunity to bring the capabilities of how you run you know studies and drug programs and campaigns and clinical trials alongside the bleeding edge model where you know every 3 to four months there's just amazing new capabilities coming uh I do think it's that inflection point of how can we bring the capabilities of running drug programs uh and clinical trials and other uh capabilities to the entire industry uh and make that really tightly knit with the model capabilities that we're developing as
</details>

### 生命科学的 3D 价值链：发现、开发与分发

>> 好的，我们已经讨论了构建最顶尖模型、将其部署到最佳工具外壳中、并提供给科学家进行他们想做的任何工作的抱负。接下来让我们谈谈如何将其引入行业、将在哪里发挥作用以及你们将构建的所有内容。Jorge 和我几年前写过一篇博文，探讨软件和 AI 触及生命科学价值链各个环节的机遇，我们使用了一个由发现（Discovery）、开发（Development）和分发（Distribution）构成的巧妙的 3D 框架。我们非常希望以此为脉络贯穿整个对话，以了解大家将要做些什么。也许 Ashoka，我就直接问你了。OpenAI 如何考虑在我们提到的生命科学价值链的这三个 D 维度上构建工具？在这三个领域是平分秋色吗？你们是从早期阶段开始并逐步推进到后期阶段吗？帮我们了解一下未来有哪些值得期待的内容。
<details><summary>Original English</summary>
Okay, so we've talked about the ambition to build the very best models and then deploy that in the very best harness and be available to scientists for whatever work they they want to do. Let's talk about how to bring that to industry and where that will play out and all the things that you'll build. Jorge and I wrote a blog post a few years ago about the opportunity for software and AI to touch every part of the life sciences value chain and we used a a cute framework from discovery, development, and distribution. And so we'd love to kind of use that to run through the conversation uh and understand um what you all are going to do. So maybe I'll shook I'll just go over to you. How does OpenAI think about building tools across the three Ds that we mentioned in the life sciences value chain? Is it equal across the three? Are you starting in the earlier areas and moving later? Help us understand what to look forward to.
</details>

>> 我认为我们在这三个领域都怀有巨大的雄心，但也必须认识到它们之间是多么不同，其工作流程是多么迥异。在发现阶段，如果考虑从靶点到 IND（新药临床试验申请）的过程，我们真正聚焦的是如何拓展和放大专业新药发掘人员（drug hunters）的能力。这表现为多种形式，可以是模型和其他能力，它们能够执行高度专业化的科学任务，比如在海量文献中检索，或者大规模分析基因组数据，甚至是生成化学结构和候选分子。所以存在这些核心能力，但这些都属于单项任务，而这些任务处于由不同研究、项目活动和其他工作流程构成的长链条上，最终都汇总到一个总体的药物项目中。因此，不仅要构建帮助人们完成这些高度专业化任务的能力，并利用超人类的模型能力来帮助放大该专业水平，而且还要确保真正编排起整个工作流——无论是针对一项研究还是整个药物项目。并且在过程中的每一步，都要捕获所产生的所有证据，特别是隐性知识（tacit knowledge）。正如上一波软件即服务（SaaS）浪潮（例如在我曾工作过的公司）真正帮助了信息的结构化和存储，但所有那些隐性知识——比如我们为什么选择那个分子？反对这一主张的反事实依据或混杂证据有哪些？——所有这些才真正构成了推动你穿过早期发现阶段的证据链。因此，我们能做些什么来帮助你大规模管理这些内容，并同时开展更多并行实验以在更短时间内探索空白空间？

而在开发阶段，核心真正关乎时间和成本。当你考虑到监管申报、生产制造和临床时，这是你真正触及患者的地方。因此，法规、质量极其关键。但对该行业来说，在实践中这就意味着海量海量的文件材料，这至关重要，因为过程即产品。你如何知道自己使用的是符合质量门槛的正确药物，以便在正确的就诊环节以正确的剂量施用于正确的患者？这里存在巨大的机遇，而大语言模型在理解非结构化和半结构化信息方面表现极其出色。因此，我们在压缩诸如监管申报、监控和跟踪临床试验进展等任务的时间方面发现了大量机会。

最后，当我们进入分发领域时，与我们在 OpenAI 健康部门的伙伴合作令人十分兴奋。因为 OpenAI 的 ChatGPT 拥有 12 亿用户，其中有 3.3 亿用户在询问健康问题。在消费者端、临床医生端和支付方端，所有这些群体突然都获得了一种能够对临床医学的诸多复杂性进行推理的能力。因此，针对某些药品分发的方式——比如你是否参加了正确的会议？你是否读到了正确的论文？你是否听到了正确的信息？——我认为这里存在巨大的机遇，能够真正打破人们在适当时机、针对对应诊断获得正确治疗的方式。
<details><summary>Original English</summary>
>> I think we have huge ambitions across all three areas, but we also have to recognize how different they are and how different the workflows are. So you know on the discovery side if you think about from target to IND what we're really focused on is how do we uh scale and amplify um the abilities of expert drug hunters and that comes in many many forms that could be um model and other capabilities to that are that can perform highly specialized scientific tasks like search through an enormous corpus of literature or analyze genomic data at scale uh or even generate uh chemical structures and candidates. Um, so there are core capabilities, but those things are tasks and those tasks sit on a long chain uh of different studies, campaigns, and other workflows that all move up to an overall drug program. So creating not only the ability to help uh folks do these highly specialized tasks and maybe use superhuman ability of models uh to help amplify that expertise but also make sure that that is actually orchestrating an entire workflow be that a study or an entire drug program and at every step of the way capturing all of the evidence that's generated particularly the tacet knowledge like the last wave of software as a service you know at companies that I have worked in really helped in structuring and storing the information, but all of that task knowledge like why did we select that molecule? Like what are some of the counterfactuals or the confounding evidence against this claim, all of that is really what comprises the chain of evidence that advances you through the early stages of discovery. So what can we do to help you manage that at scale and also run a lot more experiments concurrently to explore wide space in less time development is really about time and cost. uh when you think about uh you know regulatory submissions manufacturing and clinical this is where you're touching patients. So the regulation and the quality and the uh and is is incredibly important. Uh but what that turns out to in practice for the industry is massive massive massive piles of documentation which is critically important because again the process is the product. How do you know that you're putting in the right drug that passed the quality bar to admit it to the right patient at the right encounter in the right dose? So there's a lot of opportunity and LMS are phenomenal at understanding unstructured and semi-structured information. So we find a lot of opportunities in compressing time to do things like regulatory submissions, uh monitor and track what's going on in your clinical trials. And then lastly, when we get into distribution, uh this is where it's, you know, exciting to collaborate with our partners on the health side of OpenAI because, you know, OpenAI has 1.2 2 billion users of chat GPT. Uh uh but 330 million of those uh users are asking health questions. On the consumer side, on the clinician side, on the payer side, all of these groups suddenly have access to a capability that can reason through a lot of the complexities of clinical medicine. So, you know, some of the ways that you know, you know, medicines are distributed like, did you go to the right conference? Did you read the right paper? Did you hear the right thing? Um, you know, I think there's a lot of opportunity to really upend how people get the right treatment at the right time for the appropriate diagnosis.
</details>

### 深入药物发现与智能体群体

>> 如果我们暂时深入探讨一下“发现”这一环节，我在生物科技领域待了很长时间，在我看来，这是 AI 所能带来的超人类智能能够真正发挥作用的最有前景、最引人入胜的领域。但如果我们拆解开来，“发现”这个名称的含义表明，这里最基本的单元是洞见（insight）。我们如何生成洞见，以及我们如何实际做出决策来帮助我们将该洞见推进为最终能够形成药物并产生影响的东西？如果以最基本的方式看待发现，谈到产品时，你提到了 Codex，当你设想科学家身边可以拥有的产品，以赋能和支持对独特洞见的探寻时，我们目前处于什么水平？OpenAI 目前在产品以及支持科学家开展该项探索方面处于什么阶段？
<details><summary>Original English</summary>
>> You know, if we dig in on the on the discovery piece for for a second here, you know, I spent a lot of time in biotech and to me this is the most, you know, promising and fascinating fascinating area for, you know, superhuman intelligence, the superhuman intelligence that AI can bring us um can really have to bear. But like if we tease it apart the the name discovery the implication here is that the fundamental unit of what matters here is an insight. How do we generate an insight and how do we actually make decisions that will help us advance that insight into something that will ultimately be impactful in the form of a medicine. So if we think of discovery in its sort of most basic way, when you think about product, you talked about codecs, when you think about the product that a scientist could have alongside them to to enable um and to support this uh call it search for a unique insight. Where where are we today? Uh where is open AAI today in terms of product um and in supporting uh scientists in that endeavor?
</details>

>> 我个人觉得非常令人兴奋的一点是，那些正在不断推出的数学成果。这类智能体团队部署了 10,000 个智能体，你抛出一个问题，因为数学是可验证的，你也可以验证部分进展，从而解决极其复杂的问题，比如千禧年大奖难题、斯托克斯方程等。我认为由此自然会引出一个问题：我们什么时候能在生物学中看到类似的情景？生物学中的千禧年难题又是什么？我认为生物学的问题形式往往与数学截然不同，很多内容完全是探索性的。在过去的 10 到 20 年里，我们通过下一代测序技术、高通量检测产生了海量的数据。我认为目前的限制因素实际上是如何从这海量数据中获取洞见，而不一定仅仅是缺少足够的数据，这与数学所处的范式截然不同——数学中只是给你一个命题陈述，要求你证明这个命题。
<details><summary>Original English</summary>
I think something that I personally find um incredibly exciting is you know the the math results that have been rolling out right these kind of um agent teams that you know deploy 10,000 agents you throw out a problem and because math is verifiable you can verify also partial progress you can solve incredibly complicated problems like the millennium prize problems stokes etc and I think you know there's a natural question that comes from that it's like when are we going to see something similar in biology and you know what are double millennium prices in biology. I think biology tends to have a very different form of problem than math and that a lot of things are really exploratory and I think you know since the in probably the last like 10 20 years we've had a huge amount of data generated from nextg sequencing from high throughput assays and I think the limiting factor has actually been like gaining insight from this massive amount of data and not necessarily just you know not having enough data which is like a very different regime from math, right? Where just here is a question statement and I need you to prove this question statement. Um,
</details>

>> 这太引人入胜了。所以你认为答案就在那里？我们拥有数据，答案就在其中，只是需要向该任务投入足够的超人类智能？
<details><summary>Original English</summary>
>> that's fascinating. So, you think that the answers are there? We have the data, the answers are there. It's just a matter of applying enough super human intelligence to the task.
</details>

>> 是的，我的意思是并不总是都在那里。我认为确实有些数据集里的答案是存在的，只是人类的注意力跨度是有限的。在过去的经历中，我拿到了系统生物学的博士学位，我也曾产生过一些这种高通量检测数据。当数据回到你的桌面上时，你会有这种极度兴奋的感觉，觉得这里面蕴藏着某种洞见；但随后你也会产生这种令人瘫痪的焦虑：我该如何找到它？因为这个数据集和搜索空间实在太庞大了。我认为我们现在正在进入一个不同的范式：我们拥有成千上万个智能体，可以追踪这个数据集中每一个可能的假设，它们也可以相互交流，还可以与人类交流。我认为我们现在首次不再受限于人类的注意力，你可以关注这个数据集中的一切，榨取出其中所有的精髓和洞见。

我认为这是我觉得非常令人兴奋的应用之一。这涉及到例如我们与 Perturb AI 开展的合作，他们是我们早期的合作方之一，他们在小鼠大脑中进行了这种体内扰动测序（in vivo Perturbation-seq）。我们获得了 2,000 次扰动、800 万个不同细胞的数据，这是一个非常庞大的数据集。当我们向这个问题投入 2,000 个智能体时，它发现的一些洞见是之前人类进行人工排查时未能发现的，而那花费了人类许多许多个月的工作。

举个例子，有两个在同一个蛋白质复合体中协同工作的不同基因。我们发现，如果在大多数细胞类型中敲低这两个基因，它们会产生类似的结果。但是在某一种特定的细胞类型中，敲低其中一个基因，许多事情都会发生变化；而敲低另一个基因，却没有任何改变。这对基础生物学以及特定疾病都具有重要意义，在此案例中就是结节性硬化症（tuberous sclerosis）。但想象一下，一个研究生要从这个由 800 万个细胞乘以 2,000 个基因组成的矩阵中找出这种模式，需要花费多长时间。所以我认为这代表了一个新的范式：现在我们仅仅通过扩展 token 和智能体规模，就能够获取潜藏在数据集中的所有这些洞见。
<details><summary>Original English</summary>
>> Yeah, I mean it's not it's not always there. I think there are definitely some data sets where the answer is there, but it just you know human attention span is limited, right? And you know in my past life I did a PhD in systems biology and I've also generated some of these high throughput assays and then when the data lands back on your desk you get this feeling of you know intense excitement that okay there's like some insight in here but then you also get this like paralyzing anxiety of how am I going to find it because this data set and the search space is so big and I think we're entering a different regime now where we have these tens of thousands of agents that can go after every single possible hypothesis in this data set and they can also talk to each other. They can talk to the humans and I think for the first time now we are no longer limited by human attention. You can pay attention to everything in this data set and squeeze all the juice and insight out of them. Um and I think that is one of the um applications that I find to be really exciting and this you know has to do with you know for example the work that we did with perturb AI which has been one of our um early collaborators where they did this invivo perturbation seek in uh my brains and we got I think um 2,000 perturbations 8 million different cells which is just like such a massive data set and when we threw 2,000 agents at this problem some of the insights that it found were not found before when humans did a manual pass and this is like many many months of human work. Um, an example is for example two different genes that work together in the same protein complex. And we found that if you knock down um both of these genes in most cell types, they have similar outcomes. But in one specific cell type, one of the genes you knock it down, a bunch of things change. The other gene you knock it down, nothing changes. And so this has implications for like basic biology and also for a specific disease. In this case, it's tuberosclerosis. Um but imagine how long it would have taken for a grad student to find that pattern out of this like 8 million cell by 2,000 gene matrix. So I think this is you know just a new regime now where we can we can get all of these insights that are living in the data set just by scaling tokens and agents
</details>

>> 这是否已经反映在产品中了？比如如果我今天是一名科学家，如果我是 X 制药公司的湿实验科学家，我能获得这种能力吗？
<details><summary>Original English</summary>
>> and is that already reflected in product like if I'm a scientist today do I have access to this capability if I'm a wet lab scientist at pharma company X
</details>

>> 是的，目前不一定具备 2,000 或 10,000 个智能体的规模，但科学家使用 Codex 调用许多子智能体、甚至由一个智能体协调许多其他智能体的能力肯定是具备的。我认为这可能是普及最快的使用方式之一：一个表面上在软件工程方面表现惊艳的工具，突然之间让众多不同的科学家能够探索他们所拥有的如此广阔的数据空间。我想你们已经看到了很多令人兴奋的成果，人们回过头去查看他们在博士期间研究过的数据，或者他们进行过的其他实验，而过去他们受限于自己能够提出的假设数量以及实际能够运行的分析数量。因此，即使没有成千上万个智能体的完整团队，我认为我们已经看到成效了；而且在我们的合作中，当你把规模大幅扩展时，我们看到了许多令人兴奋的前景。
<details><summary>Original English</summary>
>> yeah not necessarily with the 2,000 or 10,000 agents yet but um you know certainly like the ability of a a scientist you know using codeex use many many sub aents you know, even an agent orchestrating many other agents. Um, I think that's probably been one of the fastest uh adoptions in the use of things. It's that, you know, a tool ostensibly that's amazing at software engineering can suddenly allow so many different scientists to explore such a wide space of data that they have. I think you've you know seen a lot of exciting results where people go back to the data they looked at from their PhD or other experiments that they've run and they were sort of limited by you know what are the number of hypotheses I can put through and the number of analyses that I can actually run uh so even without this full you know team of thousands of agents I think we're already seeing that u but it does you know you know in our collaborations we're seeing a lot of exciting promise when you scale that up massively
</details>

>> 谈到洞见，关于普通的新药发现工作，有一件引人入胜的事情：因为其中很大一部分是在试图应对不确定性，所以最大的价值来源之一就是知道下一步该做什么。你有一个假设，做了一项实验，得到了一个结果；你分析了一个大型数据集，产生了一个新颖的洞见。而“下一步该做什么”这个问题，在某种程度上正是成就一位伟大新药发掘人员的核心所在——他们知道下一步该做什么。
<details><summary>Original English</summary>
>> and one of the things that u you know if we talk about insights. Um, one of the fascinating things about you know your average discovery effort is um because so much of it is about um trying to navigate through uncertainty. One of the biggest uh sources of value is knowing what to do next. So you have a hypothesis, you run an experiment, you get a result, you generate, you know, you you analyze a large data set, you generate a novel insight. The what to do next question is always, you know, in some ways that's really what makes a great drug hunter a great drug hunter is they know what to do next.
</details>

>> 当涉及药物发现时，目前的工具是否有能力帮助普通科学家思考“下一步该做什么”这一挑战？
<details><summary>Original English</summary>
>> Are the tools capable of helping the average scientist today think through the what to do next challenge when it comes to discovery?
</details>

>> 是的，我认为这就是为什么我们考虑放大专家能力的原因。同样是那些人在查阅这些非常复杂的数据集，然后在决定下一步该做什么时，凭借自己的技能和品味，他们会想：“我想查阅文献，我想与世界顶级专家交谈，我非常想做这件事。”我们可以通过这种方式真正放大这种专业能力——比如你说：“好的，你想查阅文献，那如果你查阅 1,000 篇或 5,000 篇论文呢？如果你查阅你甚至从未想过的专家和研究团队的工作呢？如果我们梳理整个互联网上的知识库等等呢？”或者在工具外壳方面，查阅你实际进行的所有其他实验以及你在内部积累的知识库又会怎样？所以，我认为归根结底，“下一步该做什么以及为什么”是终极的稀缺资源，也是最难寻觅的要素，而这正是让一位杰出科学家成为杰出新药发掘者的原因。因此，我们将当今的工具和系统视为极佳的放大器。而且我认为，当达到该领域的顶尖人士会惊叹“哇，这是一个全新的洞见，我不知道自己能否独立想出来”的程度时，你将会看到巨大的突破。
<details><summary>Original English</summary>
Yeah, I mean I think one that's why we think about like amplifying the expertise of of folks where you know those same folks who are looking through these really complex data sets and then in deciding what to do next their own skill and their own taste they're like you know what I really want to like look at the literature I really want to talk to a world-class expert I really want to do this and we can really amplify that expertise uh by saying okay you want to look at the literature what if you looked at you know a thousand papers or 5,000 papers what if you looked at you experts and and groups that you never even thought of. Um what if we look through the whole corpus of knowledge you know on the internet and things like that uh or or you know on the kind of harness side what about all the other experiments that you actually ran and the accumulated knowledge you have internally so I think that's where you know ultimately the what to do next and why is like the ultimate um kind of scarce resource and like the most rare thing to to find that what's that's what makes an outstanding scientist an outstanding drug hunter. So we view the the tools and systems today as great amplifiers of that. Uh and and um I think you know you will see you know a huge breakthrough when you get to the point at which you know some of the best in the field are like wow that's a that's a novel insight that you know I don't know I would have come up with myself.
</details>

### 靶点发现与分子设计

好的，从宏观层面来看，发现的挑战正如我们所讨论的，是在寻找新颖的洞见，并试图弄清下一步该做什么。但在宏观层面上，它实际上包含两个部分：一是你在努力弄清楚靶向什么来对疾病产生影响；二是你在努力弄清楚是否能设计出一个能击中该靶点并产生相应临床效果的分子。在发现的最早阶段，这就是两个核心的大问题。
<details><summary>Original English</summary>
Okay, so just at a very high level, the challenge of discovery, right? And we talked about it. It's, you know, you're looking for a novel insight. You're trying to figure out what to do next. But at a very high level, it it's really there's two parts is you're trying to figure out what to target to have an impact on disease. And then you're trying to figure out can you design a molecule that will hit that target and to have the appropriate clinical effect right at the earliest stages of discovery. that those are the sort of the two giant questions.
</details>

>> 我该靶向什么，以及我能否制造出某种物质以安全有效的方式击中该靶点？而剩下的各个“D”环节则是关于实际验证这一点的。OpenAI 目前在支持寻找靶点或设计击中靶点的分子方面处于什么水平？
<details><summary>Original English</summary>
>> What do I target and can I make something to hit that target in a safe and effective manner? And then the rest of the the D's are about, you know, actually proving that out. Um, where is uh open AI today in supporting the ability to help find the target or make design the molecule that will hit the target.
</details>

>> 我会说，靶点发现方面的很多工作与我们讨论过的智能体团队工作类似。现在你能够获得此前无法获得的所有这些洞见，仅仅是因为你现在能够投入无限的注意力，并在你可以用于该问题的 token 数量上最大限度地进行测试时扩展（test-time scaling）。我认为，一旦你有了靶点，进入分子设计阶段，它就会变成一个具体得多的优化问题。这在另一个维度上也很有趣，因为现在你可以考虑模型是否能够协调这些不同的化学工具或专用的蛋白质设计工具来制造出一种新的蛋白质。我认为甚至更有趣、我们已经开始看到曙光的一点是，模型展现出类似于世界上大概只有 10 到 100 个人才具备的能力：能够看着蛋白质序列（即蛋白质的一级字母序列），并在脑海中可视化出 3D 结构；或者他们能够看着一个分子并指出：这个特定的候选分子存在缺陷（liability），或者我们需要以这种特殊的方式修改它，使其能更好地与蛋白质结合。这些能力正是我们从一开始就希望构建到 Rosalind 中的。我认为开始看到这些能力从我们的内部模型训练中涌现出来，是我在过去几周里看到的最令人兴奋的事情之一。
<details><summary>Original English</summary>
Yeah, I would say that um a lot of the work and kind of the target discovery side is similar to you know the the agent teams work that we were talking about where now you can get all these insights that you otherwise wouldn't be able to just because you're able to now pay infinite attention and just maximally um do test time scaling on the number of tokens that you can spend on a problem. I think once you have a target and it comes to more on the molecular design part, I think it becomes a much more concrete optimization problem which is also interesting in a different way because now you can think about you know can the model orchestrate these different um chemistry or specialized protein design tools to make a new protein. Um, I think something that is even more interesting that we're starting to see glimmers of is the model's ability to act like, you know, these probably 10 to 100 people in the world that can kind of look at a protein sequence. It's like the primary letters of a protein and visualize the 3D structure in their head or they can look at a molecule and say okay this particular product molecule is a liability or we need to change it in the special way to bind to the protein better. these capabilities is what you know starting from the very beginning what we want to build into Rosalind and I think you know starting to see these things emerge out of our internal model training is I think I want the most exciting things of the the the last few weeks that I've seen
</details>

>> 所以我认为，在未来大约三到六个月内，我们利用 AI 设计分子的方式将会发生很大变化。
<details><summary>Original English</summary>
>> and so I think you know the way that we design molecules with AI I think it's going to change a lot in the next I would say three to six months
</details>

### 临床开发与试验运营

>> 好的，太棒了。概括起来，你实际上描述了两类能力：一类能力是扩展人类能力的吞吐量，比如你提到的 1,000 个、10,000 个智能体，能够完成 10,000 名研究生的工作，而且只需几秒钟；你们描述的第二类能力则围绕超人类能力展开。也许世界上只有一两位新药发掘专家能够脑补出蛋白质的三维结构，思考其结构中的缺陷等等，并提出修改建议，但这不是普通人类所具备的能力。

让我们用这个视角来谈谈“开发”。下一个“D”的核心在于，一旦你拥有了有前景的科学假设，你希望在哺乳动物体内以及随后的在人体中测试该候选药物的安全性和有效性。接下来我们谈谈临床试验工作的复杂性。Ashoka，从工具外壳的角度来看我很好奇，对于制药和生物科技领域中负责设计临床试验的临床开发人员，你们希望为他们构建哪些工具？这些人可以期待哪些工具？
<details><summary>Original English</summary>
>> okay excellent so to to synthesize you're really describing two sets of capabilities one set of capability which is scaling the throughput of human capacity. So you're talking about a thousand agent, 10,000 agents that can do the work of 10,000 grad students but do it in a matter of seconds. And then the second set of capabilities that you all are describing are around um superhuman capabilities. You know, maybe there is one or two drug hunters in the world that can visualize a protein and think about liabilities in the structure and so on and so forth and make make suggested edits, but that's not the capability of an average human. Let's say let's use that lens to talk about development. So the next D is all about once you've got a promising scientific hypothesis, you want to test the safety and effectiveness of that therapeutic candidate um in mammals and then in humans. And so let's talk about the complexity of of trial work. And Ashoka, I'm curious from a from a harness perspective, what are some of the tools that you're looking to build for clinical development folks in pharma and biotech who are designing clinical trials? What are some of the tools that those folks can look forward to?
</details>

>> 是的，这是一个很好的问题。临床试验和临床开发是一套极其庞大的活动，也是耗费资金最多的地方。它的范围涵盖了诸如：如何为试验本身设计方案（protocol）；如何检索迄今为止进行过的所有试验文献和出版物，并与许多个人协作以综合确定适宜的方案和试验设计；然后是你将在哪里开展这项试验？应该使用哪些临床试验中心（sites）？为了首先进入这项试验，应该对哪些患者群体进行亚型分类？如何让这些试验中心启动？临床试验中的大量工作都外包给了其他合作伙伴，而申办方（sponsors）需要开展大量工作来维持对试验中心发生的一切、以及试验本身中患者发生的一切的监督。

然后就进入了日常的临床运营。根据研究的架构，你可能纯粹是在寻找安全信号；也可能是一项你在寻找安全性和早期疗效信号的试验。随后你想利用这些来设计二期和三期临床试验，而维持该试验的日常运营是一项浩大的工程，申办方团队需要对照临床方案监控所有进展，而试验中心方则需要依据标准操作规程（SOP）和方案开展大量工作，涉及所有这些不同的系统——EDC、CTMS、eHR、方案、TMF 以及各种三个字母和四个字母缩写的系统。这是极其庞大的工作量，而且这些工作很容易彼此脱节、数据不一致，所有这些都会影响你以统计学上有效的方式使用这些数据来了解疗效的能力。

因此，在该流程的每一个环节，我们都在与业内不同的合作伙伴、生物科技公司、大型制药机构、CRO（合同研究组织）和 CDMO（合同研发生产组织）紧密合作，试图开发出大家在各个环节所需的产品功能。但举个例子，正如 Joy 提到的，扩展算力和扩展智能体能力如何在日常工作中发挥作用：这可以像所要求的注意力和监督力度一样直接。你有一个方案，有一个入组目标，对各项活动的推进日程有所有的预期，但这绝不是试验实际推进的方式。你的入组进度可能会落后；实际对治疗的反应可能会出乎意料；你可能会遇到需要综合分析的不良事件。而完成所有这些工作，都需要人员深入挖掘并分析分散在所有这些不同系统中的海量数据。而这正是智能体能够极其擅长的事情。

我们能否让一个设计良好的试验推进得更快？生物学本身存在极限，所以从这个角度来看答案是否定的。但你可以采取很多措施来防止试验偏离轨道。很多试验实际上无法按时完成，原因在于入组问题或者试验中心的问题。因此，我们如何才能真正扩展专业能力和运营能力，让人们能够大规模运行试验？我们在其中看到了一个巨大的机遇。
<details><summary>Original English</summary>
>> Yeah, it's a great question and I think you know clinical trials and clinical development is this you know massive set of activities. It's where most of the money is spent. You know, it ranges from things like, you know, how do I design the protocol uh uh for the trial itself and how do I, you know, scan the corpus of all the trials that have been run to date and all the publications and collaborate with the number of individuals to triangulate to the appropriate protocol and trial design. Then there's, you know, where am I going to run this trial? Um what sites should I use? Um what are the um patient populations that I should be subtyping in order to enter this trial in the first place? How do I get those sites activated? Um, a lot of the work in clinical trials is externalized to other partners [clears throat] and there's a lot of work that sponsors need to do to maintain oversight of everything that's going on at the sites, everything that's going on with the patients in the trial itself. Then you get into like the day-to-day clinical operations where depending on the structure of the study, you may be looking for, you know, purely safety signals. It could be, you know, like a uh, you know, trial where you're looking for safety and some early efficacy signals. Then you want to use that to design your phase twos and threes and running the day-to-day operations of that trial is a massive effort and endeavor both on the folks on the sponsor side trying to monitor everything that's going on against the protocol but then on the the trial site side where there's a lot of um uh work that needs to be done in compliance with SOPs in compliance with the protocol spanning all these different systems the EDC the CTMS the HR the protocol the TMF and every three and four letter system it's an enormous amount of work and it's really easy for that work to get out of sync with one another to you know for the data to not agree all of which impacting you know your ability to use that data in a statistically valid way to understand the efficacy of your treatment. So at every single step in that process, we are working closely um with different partners in industry, biotechs and and large pharma organizations, CRO and CDMOs trying to develop what are the product capabilities that you need uh in each uh but you know to to use you know as an example you know what you know Joy mentioned of like how can scaling compute and scaling what agents can do help in a day-to-day basis that could be as straightforward as you know what is the attention and oversight required you have a protocol, you have an enrollment target, you have all the things that you expect to happen in terms of the schedule of activities, but that's never how the trial actually goes. Um, you know, your enrollment could be off um, you know, at your sites. Uh, the actual response that they're getting to the treatment might be unexpected. You may have adverse events that you need to triangulate. And doing all of that work requires people to dig into and analyze a huge amount of data split across all these different systems. uh and that is something that agents can be really really good at. Uh and you know can we make a trial that is welldesigned happen faster. There are limits to biology. So the answer is no on that. But there's a lot that you can do to prevent it veering off track and so many trials don't actually finish on time you know because of enrollment issues because of you know issues with their sites. Uh so how can we really like scale uh the the expertise and the operational capacity for people to run trials at scale um and that's where we see you know as an example a big opportunity.
</details>

>> Ashoka，正如你刚才所言，在将药物送到患者手中的过程中，临床开发是耗时最长的主流程。这是我们花费时间最多、耗费金钱最多的环节，也是我们发现自己犯了错误、发生失败的地方。那些都是代价高昂的惨痛失败。人们往往会认为，AI 提高该过程效率的潜力是巨大的。鉴于这里的种种复杂性，我首先想向两位请教的是，我们在哪些方面开始看到 AI 在提高该流程效率方面展现出成效？
<details><summary>Original English</summary>
>> So Shoka so as you just said you know clinical development is the the the long pole in the tent when it comes to getting a drug to a patient. It's where we spend the most time. It's where we spend the most money and it's where we make the most where we find out we've made the mistakes right where things fail, right? That's where you know that is these are the big uh costly expensive failures. One would think that the potential for uh AI to make that process more efficient the potential for that is enormous. Um so the first question I I would love to ask you guys is given all of the complexity here where are we starting to see some inroads with where AI has proven to be uh helpful in in making this a a more efficient process?
</details>

### 患者招募与临床试验匹配

>> 一种思考方式是将其分为三个领域：我们能否设计出更好的试验？我们能否将合适的患者纳入试验？第三个则是，我们能否减轻实际执行试验所需的运营负担？刚才我主要谈了第三点。不过关于中间这一点：当我们谈论试验的人员招募时，我记得在十多年前，数字健康热潮处于最早期阶段，我相信 Jay 一定经历过很多个熬夜思考的夜晚，试图弄清楚我们如何获取这些临床数据和基因组数据，以及我们如何将患者与试验相匹配。你去参加任何会议，实际参与试验的患者人数与希望参与试验的人数相比差距悬殊。这是一个极其复杂的推理问题，我们在十年前拥有的工具包包括提取所有这些信息、编写规则和规则引擎来尝试将人们与试验匹配。而它确实无法应对包含和排除标准、患者所处的疾病阶段、如何将其与试验方案进行匹配等复杂问题。

鉴于我们在消费者端拥有庞大的用户群体，鉴于 ChatGPT 在临床环境中的使用，我们看到了巨大的机遇：将这些与临床试验端正在发生的事情结合起来。因为从一开始让患者入组试验，就是决定试验最终需要多长时间的最主要决定因素之一，同时关系到你是否招募到了针对所需队列的正确人群。因此，我认为我们在这方面已经看到了阶跃式的变化。你不可能简单地把所有东西都套进关系型数据库表中来将某人与临床试验匹配，这就是为什么存在这些入组与排除标准，为什么需要专家进行审查。但我确实认为，我们现在已经到了可以在筛选人员资格以及将我们业务的消费端与企业端整合方面取得巨大飞跃的节点。
<details><summary>Original English</summary>
So one way to think about it is like three areas. So can we design better trials? Um can we get the right patients into the into the trials. Uh and then the third is like can we reduce the operational burden that it takes to actually execute that trial. Um so you know I just recently talked about that third one. Uh but maybe this middle one. So we talk about uh enrollment of folks into a trial. uh and you know I remember 10 plus years ago uh you know the you know the digital health you know boom was kind of you know at the its earliest innings and you know as I'm sure Jay has has met many a late night trying to figure out you know how do we get this clinical data and this genomic data and how do we match patients to trials and you go to any conference and like you know the number of patients who are actually in trials versus who want to be in trials and it's a really really complex reasoning problem where some of the tools in the toolkit that we had, you know, 10 years ago were, you know, extracting all this information, you know, handwritten rules and rules engines to try and match people to the trials. And it really wasn't able to uh, you know, get to the complexity of like the inclusion exclusion criteria, you know, where the patient was on their journey, how you match that against the protocol and things like that. Um so that's something where we see immense opportunity again given you know the huge user base that we have uh in on the consumer side uh given you know the use of chat GBT in clinical settings bringing that together with what uh is happening on the clinical trial side because you know just getting the patients enrolled into the trial in the first place can be one of the single biggest determinants of how long it ultimately takes uh and did you get the right population for the cohort that you were looking for. Um, so that's one where I think we've actually seen a step function change in, you know, you can't just like fit everything into a relational database table to match somebody to a clinical trial. That's why these inclusion exclusion criteria are there. That's why you need experts reviewing them. But I do think that we are at the point where um we can make a big leap uh in terms of uh the ability to get and screen people for their eligibility and bring the consumer um and and enterprise side of our business together.
</details>

>> 这太引人入胜了。所以存在这样一种可能的情景：ChatGPT 能够帮助消费者意识到有一项适合他们的试验。
<details><summary>Original English</summary>
>> That's fascinating. So there's a world where um ChachiPT could help a consumer realize that there's a trial that they would be a match for.
</details>

>> 是的，可以是消费者本人，也可以是临床医生。当临床医生查看病历、只有 20 分钟或 25 分钟宝贵时间时，同一个能够调取他们所有就诊记录和问题清单等内容的系统，不仅可以检索文献，还可以根据某人在该疾病中的进展情况检索我的学术医学中心当前正在开展的项目。归根结底这主要是医生和临床人员时间的稀缺性。这如何能被呈报为一个可供临床试验协调员筛选其试验资格的对象？而在下游还有一整套工作流，收集证据和信息以完成审核，利用当今的模型能力这是完全可行的。在制药端、申办方端以及学术医疗中心和医疗系统端存在着不同的机会，我们可以让这两端更加紧密地结合在一起。
<details><summary>Original English</summary>
>> Yeah. It's it could be the the consumer themselves. It could be the clinician who again when you think about when they're looking at their chart and they have 20 minutes or 25 minutes and that scarce time. you know, the same system that can pull, you know, all their encounters and their problem list and so on can also be searching through not just the literature, but what's going on at my academic medical center right now based on the progression somebody has had in this disease. Um, where, you know, it's it's really just the scarcity of physician and clinician time, right? Uh, and how could that be teed up as something that, you know, a clinical trial coordinator could get in as somebody to screen uh for their eligibility of a trial. Um, and then there's a whole set of workflows downstream of that. all of that gathering of evidence and information to clear through that. Um that is something that feels you know quite possible with the models capabilities today. Um and there are different opportunities on you know the pharma side sponsor side as well as the academic medical center side uh and and health system where uh we can bring these two sides closer together.
</details>

### 监管申报与材料汇总

>> 是的。那么让我们来看紧随其后的下一步。你设计了临床试验，成功完成了入组，进行了临床试验并产生了必要的数据。现在你必须把所有这些整理成文档，提交给监管机构进行审批，在此案例中就是 FDA。那么有两个问题：第一，对于听众而言，请讲讲为监管申报收集所有必要文档的过程有多么痛苦和费心；问题的第二部分是，我们在哪里能看到人工智能所带来的显而易见的赋能？
<details><summary>Original English</summary>
>> Yeah. So maybe well let's take the next step downstream from that. Yeah. Um so you've uh designed a clinical trial, you've enrolled it successfully. Um you've generated the you know you run the clinical trial experiment, you've generated the necessary data. Now you have to take all of that and document it uh and submit it to the to the regulatory authorities
>> uh for for approval in this case the the FDA. Um so uh two questions there. One is uh uh for the listeners talk through how pain painful uh and painstaking the uh process for uh assembling all the documentation necessary for regulatory filing is um and the second part of that question is and you know where do we see the obvious leverage that we can get from from artificial intelligence?
</details>

>> 这是一个很好的问题。无论你是提交 IND、生成临床试验的 CSR（临床研究报告），还是准备提交 BLA（生物制品许可申请），监管申报过程都是一个需要将所有知识、所有发现和所有专门技能汇集为监管机构可审阅材料的关键节点。这是一个极其痛苦的过程，因为你面对的是对人类庞大知识库的大规模管理，没有任何单个人或一组人能够把这些全部装在脑子里。我们今天所做的就是通过增加参与人数来扩展管理这些上下文的能力。因此这在根本上关乎人力和时间。这包括你如何记录前期的流程，如何组织这些信息和知识，以及如何向监管机构展示。而这正是大语言模型特别擅长的领域：如何对大量结构化、非结构化或半结构化信息进行推理，将其编译成这套证据包并大规模组织这些信息。这既需要模型能够解读这些信息，又需要这个工具外壳和上下文层来大规模管理这些信息。

因此，我们在生命科学领域广泛观察到，这是接受和普及最快的领域之一。首先是因为该技术与问题高度匹配；其次，这种大规模管理上下文的能力可以得到根本性的加速和压缩；第三，所有相关方都能从中获得巨大的收益。没有人是在敷衍了事，他们实际考虑的是：我们如何扩展团队的能力，以确保我们准确记录、报告并提交了所有内容，达到合适的质量阈值？因为归根结底，这样做既关乎速度——我们如何更快进入市场；但也关乎质量，因为尽管你投入了更多的人力关注，你是否仍有遗漏？特别是利用今年推出的模型，你正处于一个转折点：从帮助我更快地完成某件事，转变为有效扩展我的团队在材料提交给 FDA 之前发现问题、缺陷、异常值并加以核实的能力。
<details><summary>Original English</summary>
>> Yeah, it's a great question. So, you know, the regulatory process, whether you're submitting your IND, you're creating the the CSR from your clinical trial, um you're trying to submit your BLA, is this moment in time where you need to collect all of the knowledge and all the findings and all of the knowhow into something that is legible for regulators. Uh so it's an incredibly painful process because again you're talking about managing this enormous corpus of human knowledge that no single person or set of persons uh can keep in their heads. So what we do with that uh today is scale the ability to manage that context by scaling the number of people involved. So it's it's fundamentally people and time. Uh and it's how you document the processes leading up to it, how you can organize that information and knowledge, how do you present that uh to regulators and that is also something that large language models specifically um are extremely well attuned for. How can you reason over large amounts of structured or semistructured or structured unstructured or semi-structured information to compile it into this package of evidence and organize this information at scale um is where you both need the model to be able to interpret that information but also this harness and context layer to manage that information at scale. So I think what we see in in uh life sciences broadly is that's where uh you've seen some of the fastest uptake because there is one the technology matches the problem uh two it is something where the ability to to manage this context at scale uh can be radically accelerated and compressed and three there is a huge benefit to all parties involved. Nobody's rushing through this. what they're actually looking at this is how do we scale the ability of our our teams to ensure we've documented and recorded and submitted everything accurately to an appropriate quality threshold because ultimately doing that is both a speed thing how do we get to market faster um but it's also a quality thing because as much as you scale that human attention um what are you missing and I think particularly with models that have come out this year you've sort of at that tipping point from you are helping me do something faster to your effectively scaling my team's ability uh to catch problems uh and and issues and outliers and things like that that need to be reconciled uh before they go in front of the FDA.
</details>

>> 我经历过的年代里，向 FDA 申报材料时你必须把所有内容打印出来，装满成千上万份文件，大家甚至要租用 U-Haul 货车。人们过去常常为此拍照，然后一路开车运到华盛顿特区。这太疯狂了。显然我们现在不再这样做了。另一件同样确凿的事情是，AI 在生成监管申报材料方面的所有潜力都是真实存在的。FDA 已经发出信号表明他们希望实现现代化，并且他们也希望部署技术来审查、评估，并最终帮助对是否批准监管申报做出裁决。从你们的视角来看，你们是否看到监管机构正朝着这个方向前进，使得评估端也能实现效率提升？
<details><summary>Original English</summary>
>> So, I'm old enough to remember that when you uh filed uh uh uh with the FDA, you used to have to print everything out and you would load up thousands of documents and people would rent U-Hauls. They used to take photos of this and they would like drive it down to DC. It was wild. Obviously, we don't do that anymore. Um, the other so that great. The next the other thing that's true though is that all of the uh potential here for AI in generating the regulatory submissions is there. The the FDA has signaled they want to modernize and they want to also deploy technology to review, evaluate and ultimately uh you know help render a judgment on whether you approve or not a regulatory submission. um from your vantage point are you seeing the the regulatory agencies um moving in that direction to enable uh efficiency to come on the evaluation side as well?
</details>

>> 是的，我认为近年来 FDA 确实研究了很多不同的调控手段：比如我们如何确保美国公司能够更快开展一期临床试验；我们如何对临床试验数据进行持续提交而不是等到最后；以及在 FDA 人员队伍中使用 AI 的意愿和开放态度。我认为我们看到了很多积极的信号。你刚才也切中了要害：我们从装满文件的 U-Haul 货车转变为了电子文档提交；而现在我们正迈向由团队加上智能体形式的伙伴协同生成和汇总的阶段。而在监管方面，我认为对监管机构而言这是一个极好的机会来提升自身能力：他们如何在海量信息中搜寻大海捞针式的问题？如何使这成为一个更加持续的过程？过去有 Pre-IND 会议和 IND 会议，在这些单一的时间节点上提供反馈。因此，我确实认为有机会将监管流程从单一时间节点转变为更加连续的过程，因为此前这种方式受限于需要投入的工作量。要使这些系统真正可靠并达到让人类专家与智能体队友协同工作的程度，还有很多工作要做，但我确实认为我们开始思考一种更加持续、迭代的新范式，而不是在最后才收到一辆装满文件的 U-Haul 货车。
<details><summary>Original English</summary>
Yeah, I think like there are, you know, certainly in recent years the FDA has looked at a lot of different levers to pull, right? You know, how do we uh ensure US companies can get to phase one trials sooner. Um how do we you know, do maybe continuous submission of data for clinical trials instead of waiting till the end. Uh and then uh you know, a willingness and openness to um use AI, you know, in the workforce of folks in the FDA. So, I think we're seeing a lot of promising signals there. And I think you've also, you know, hit the nail on the head of like, you know, we went from like a U-Haul filled with documents to, you know, electronic submission of documents. Uh, but really now we're moving into, you know, what are people doing, you know, with their team plus their teammates in the form of agents to help generate and aggregate this. But, you know, on the regulatory side, I think it's, you know, a really exciting opportunity. So, so that uh for for the regulators to uplevel their own capabilities. How do they search for the needle in the haystack problems that they're looking for? How can you make this a much more continuous process? You know, you have things like, you know, your PIND meeting and your IND meeting. You have these like singular points in time where you provide feedback. So, I do think there's opportunities to make the regulatory process rather than like a single point in time a more continuous process because, you know, you were sort of bounded by uh how much effort it took to do before. uh and there's a lot of work to do to make these systems you know really reliable to the point at which you know you have these human experts um you know with their with their teammates but I do think we start start thinking about different paradigm that is much more continuous and iterative uh rather than you know a U-Haul full of documents that you get at the very end
</details>

### 药品生产制造与工艺转移

>> 考虑开发阶段时，最后一个需要攻克的难关就是生产制造。
<details><summary>Original English</summary>
>> so the last the last big sort of boulder to break when you're thinking about development is manufacturing
</details>

>> 制造极其复杂，正如制药过程中的许多步骤一样。
<details><summary>Original English</summary>
>> and manufacturing is extraordinarily complex as many of the steps in the process of of making a medicine are
</details>

>> 这里的复杂性还在于它是流程中非常昂贵的一部分，企业会投入巨额资金来确保生产流程准确无误，确保符合最终获批的监管要求。你在 Orchestra Bio 的经历中也谈到了这一点，制造环节的任何错误都会产生连锁反应，甚至是海啸般的影响，导致临床试验推迟、获批延期。
<details><summary>Original English</summary>
>> um
>> the complexity there is also it's a very expensive part of the process right you would companies invest an incredible amount of money in getting their manufacturing processes right and making sure that they meet you know the regulatory requirements uh for for ultimate approval any mistake and you talk about this in in your in your um experience with orchestra bio um any mistake in the manufacturing um uh side of the house can have ripple effects or even tsunami-l like effects on delaying clinical trials, delaying approvals.
</details>

>> 你能谈谈你在实际工作中看到的情况吗？在生产制造方面会出现什么问题？AI 又能如何帮助确保工作顺利进行？
<details><summary>Original English</summary>
>> Can you talk a little bit about what you saw in the trenches and what can go wrong in uh with respect to manufacturing and what uh AI can help make uh things or what AI can help make go right?
</details>

>> 当然可以。业内人士非常熟悉各方和各团队之间如何进行知识转移。我们经常谈论大规模管理上下文、大规模管理信息。打个比方，仅仅因为我能读懂米其林三星主厨准备烹饪的食谱，并不意味着我就能成为米其林三星主厨。
<details><summary>Original English</summary>
>> Yeah, absolutely. So, you know, folks in the industry are really familiar with like how do you transfer knowledge between parties and groups, right? And we talk a lot about managing context at scale, managing information at scale. And you know, to use an analogy, you know, just because like I can read, you know, a recipe of a Michelin star chef's uh, you know, something that they're going to cook does not make me a Michelin star chef.
</details>

>> 我总是跟 Jorge 这么说。是的。[笑声]
<details><summary>Original English</summary>
>> I tell that to Jorge all the time. Yeah. [laughter]
</details>

>> 当你考虑到生物制剂、小分子的生产时，这些都是极其复杂的配方、操作规程和专门知识的集合。出于成本和速度的考虑，这些工作越来越多地被外包给国内外的 CDMO。随之而来的权衡是，你需要将你在实验室规模或中试规模下（相当于在你的厨房或一家餐馆里）行之有效的方法和专门技能转移到临床试验规模和商业化规模。所以在制造中存在技术转移（tech transfer）过程：我们如何把我的专门技能转移给另一个机构？接下来是制造一批产品并送入临床试验所需的实际生产批次；最后是用于实际商业化上市的放大生产。在该过程的每一步，你都需要持续监控生产工艺中每个组分的每一个参数、人员在设施内的物理移动方式、环境信号，以及人们随手写下的每一项内容，你都需要持续进行监控和巡视。

这是智能体可以提供帮助的一个典型例子。当你把工艺转移给另一个机构时，你试图进行这种核对和差距分析工作：我们能做什么，他们能做什么；并将你行之有效的方法与他们试图复制或放大的工艺进行细致的核对。进入实际的批次生产阶段后，存在很多情况（甚至在细胞疗法中）批次可能正在等待质量控制审核，尚未放行给患者，因为你需要经历非常细致的流程来审查生产中记录的所有不同参数和属性。

智能体可以在诸多方面提供帮助，例如：如今很多制造依然采用纸质批记录，智能体可以识别手写体、核查所有不同参数、对照既定范围进行核对；此外还可以进行偏差调查。例如，我们发生了一次温度偏差，一家知名制药公司的人曾提出这样一个问题：“我们如何知道冰箱故障导致的温度偏差是否会延误我们的临床试验？”这听起来像是：“你这话是什么意思？”如果一个智能体通盘扫描后发现你出现了温度偏差，比如冷冻箱或冷藏箱失效了 3 到 4 个小时，我们是否有数据知道这是在可容忍范围内的？事实上，这是否反映出我们的设施存在问题？如果存在设施问题，那可能是需要解决的系统性问题，我们可能需要重跑这个批次，需要解决这个设施问题，所有这些交织在一起都会导致批次无法及时准备就绪供试验使用。因此，你是在复杂的操作规程和知识体系中进行溯源追踪：我们如何在大规模生产中、在适宜的公差范围内正确运行极其精密的工艺。虽然大家自然把很多注意力放在了临床和监管上，但我认为 CMC（化学、生产与控制）实际上是智能体产生巨大影响的一块非常成熟的领域。
<details><summary>Original English</summary>
So, so when you think about the manufacturing of, you know, biologic, small molecules, these are the most incredibly complex set of recipes, procedures, and knowhow that increasingly for cost and speed reasons are being externalized to CDMOs, you know, domestically and overseas. Uh and the trade-off of that is you need to take your knowledge and knowhow of what worked at lab scale or at pilot scale. You know the equivalent being like in your kitchen or in a restaurant and and get that to clinical trial scale and commercial scale. So you know in manufacturing there is the tech transfer process. How do we take my knowhow and transfer it to this other organization? Um then there is the actual you know manufacturing runs required to get this you know batches uh created and in into clinical trials and then lastly the scale up for actual commercial launch. And at every step in the process you need to uh constantly surveil every single parameter of every single component of your process. How people physically move in the facility. The environmental signals um every single thing people scribble down. you need to be constantly surveilling and monitoring that. So that is a prime example of where agents can help because when you think about youre transferring your process to another organization, you're trying to do this reconciliation and gap analysis effort of what can we do and what can they do and meticulously reconcile your process that works to their process that they're trying to replicate or scale up. Then when you get into just the manufacturing of the batch, um there are so many instances, you know, even in cell therapy where the batches could be waiting in quality control and they're not released yet to patients because you need to go through a very meticulous process of reviewing all the different parameters and attributes that were recorded in the manufacturing of this. So agents can help with things like look today a lot of manufacturing is on paper batch records reading the handwriting looking through all the different parameters reconciling that against the established uh uh ranges but then doing investigations figuring out you know we had a temperature deviation and an example that somebody at a you know well-known pharma said is like how do we know if a temperature deviation in a in a refrigerator uh issue uh can delay our clinical trial and it's like well what do you mean by that well if an agent scans through and sees that you had a temperature deviation where you know the freezer went out for a refrigerator went out for 3 or 4 hours do we have data to know that that's tolerable uh and in fact do we actually have a facilities issue and if we have a facilities issue that might be a systemic problem that we need to address where we need to possibly rerun this batch we need to solve this uh facilities problem all of that can converge in delaying uh uh batch being ready uh for the trial itself. So you're tracing through complex procedures and a corpus of knowledge of how do we run a very precise process at scale properly within the appropriate tolerance ranges. Uh and this I think a lot of attention has been placed on clinical and regulatory of course but I think CMC is actually uh an area that is very ripe for for agents to make a big impact.
</details>

### 药品分发与患者触达

>> 在发现和开发这两个方面，我觉得我们讨论了一个非同寻常的数据问题，以及 AI 和推理模型如何帮助解析海量数据，以及在监管、生产和临床试验中处理极其繁重的文书工作。这涉及大量由人类完成的案头工作，而 AI 非常擅长处理这些。听起来你们正在构建工具，帮助贯穿整个价值链的研究人员和药物开发者处理大量的文书工作。当我们谈到药品分发以及将药物分发给患者时，患者和医生在获取药物的过程中也必须处理大量的文书材料：保险文件、预先授权（prior authorizations）、毫无道理的拒赔等等。当你们审视药品分发这一价值链环节并思考将要构建的工具时，消费者可以期待你们在解决分发问题上带来什么？
<details><summary>Original English</summary>
So across both discovery and development, I feel like we've talked about an extraordinary data problem and how AI and reasoning models can help parse through enormous amounts of data as well as enormous amount of paperwork certainly in regulatory, manufacturing, clinical trials. It's a lot of human paperwork that's done that AI is just very good at doing. And you all are are it sounds like building tools to help researchers and drug developers across the value chain deal with a lot of paperwork. When we talk about distribution and distributing a medicine to patients, there's a lot of paperwork that patients have to go through and physicians have to go through in getting access to the medication. Insurance paperwork, prior authorizations, denials that don't make sense and so on and so forth. when you all look at the medicine distribution part of the value chain and you think about tools that you're going to build, what can consumers look forward to from you all on solving the distribution problem?
</details>

>> 是的，我认为其中一点在于，消费者已经在极其广泛地使用这些工具，来设法获取适合他们且切题的医疗护理。许多许多人会利用它来做准备：“面对我所患的这种病症，我该如何与医生沟通？”其中最大的难题之一甚至在于如何将他们所感受到的症状转化为医生在 20 分钟的就诊时间内能够理解并综合推断实际病情的表述。而且，从那之后他们可能需要应对保险问题。我曾在一家联邦医疗保险（Medicare）公司工作过，当你身边坐着一群聪明的精算师，连他们自己都在努力费劲去理解所有的预先授权规则、福利条款以及人们该如何使用它们，那么一个不是精算师的普通人该如何弄懂他们享有的福利并获得报销呢？

因此，我认为该系统存在很多自发的使用和采纳：“我需要使用这种药物或进行该项手术，也许我遭到了保险拒赔。”很多时候整个系统是用非常非常粗放的手段构建的，例如限制利用率或确保合理性；这些非常粗放的手法虽然是为了控制成本而设立的，但对人们来说处理和应对起来却极其困难。人们并不是天生就会做护理协调，或者懂得如何向保险机构提出申诉。因此，我认为如今很多人都在使用 ChatGPT 来帮助与医疗服务提供方和支付方沟通，了解如何整理证据。

我们正开始与临床医生以及支付方展开一些令人兴奋的合作，在这一等式的两端提供帮助。因为我认为没有人希望使用这些造成巨大医疗障碍的极其粗糙的手段。尽管这令人兴奋而且不可思议，但我认为也不应该仅仅依靠患者和消费者去使用 ChatGPT 来应对这些。我认为医疗系统和保险机构端的系统正处于升级之中，从而使我们能够运用适当的精准度来帮助人们获得所需的医疗服务。
<details><summary>Original English</summary>
>> Yeah, I mean I think like one of the things is that consumers are already using the tools like so extensively uh in how to get the care that uh is is appropriate and relevant for for them. So many many folks will you know use this to prepare for how do I talk to my doctor about you know this condition I have and one of the biggest problems is even translating you know the symptoms that they have into something a doctor in a 20inut you know uh encounter can can understand and triangulate to what's actually going on uh and um you know but from there you know they might not need to navigate insurance and I worked at a Medicare company and when you sit around a bunch of brilliant actuaries who they themselves are struggling to understand all of our prior authorization rules and our benefits and how people can use them. How would the average person who is not an actuary navigate the you know the benefits that they have and how to get their care reimbursed. So I think there's a lot of organic usage and adoption of the system of hey I have you know this medicine that I that I want to take or the procedure you know maybe I had an insurance denial like and and oftent times I think the entire system uh is engineered with very very blunt instruments where you know we are going to throttle utilization or we're going to make sure that this is justified and these very very blunt instruments exist to contain cost but they're very very difficult for people to to manage and navigate. People do not wake up being care navigators or knowing how to appeal to their insurance providers and so on. So I think today a lot of folks are using their chat GPT to help navigate that with both the providers and the payers to understand how to compile that evidence. And I think, you know, we're starting to do some exciting work both with uh the the clinicians as well as the payers uh to help on both sides of that equation because I don't think anybody wants to have these incredibly blunt instruments that really create enormous barriers to care. And nor do I think should it just be on the patient and the and the consumer to use chat GPT to help navigate that though exciting and amazing as that is. Um I think these systems on the on the healthcare uh and the health system and and and the insurer side are in the midst of being upgraded uh so we can apply the appropriate level of precision uh to helping people get their care.
</details>

### 数据瓶颈与愿望清单

>> 让我们稍微转换一下话题，加入第四个 D，那就是数据（Data）。在我们开始这次对话时，你提出了一个我认为非常迷人的观点：如果你能将无限的注意力投入到海量数据集中，我们就能从中提取出某种隐藏的或潜在的洞见。在哪些数据薄弱领域我们需要更多的数据？如果 OpenAI 能挥动魔法棒说“我希望存在这类数据集来帮助我们把模型打造得更好”，你们是否有这份数据集的愿望清单？它们会是什么样子，或者会包含什么？
<details><summary>Original English</summary>
>> Let's shift gears a bit uh to we'll add a fourth D uh which is data. Um and you started uh uh when we started this conversation uh uh you made that com a comment that I just found fascinating which is this idea that if you can bring infinite attention to bear on massive sets of data there are sort of hidden or latent insights that we could draw from that. Where are the shallow pockets that where we need more data? If if open AI could make wave a magic wand and say I wish this kind these kinds of data sets existed to help make our models even better. Do you have a wish list of what those data sets could look like or would be?
</details>

<!-- chunk 2/2 -->

### 数据瓶颈与生物学噪声

>> 是的，绝对是这样。嗯，我认为在训练模型方面，数据是最大的瓶颈之一，因为正如人们常说的“垃圾进，垃圾出”。如果你没有极高质量的数据，通常你的模型就学不到任何有用的东西。我们在生物学中经常看到这种情况，相比之下，比如编程甚至 ChatGPT 对话，用户输入一句话，那句话就是确定的，周围基本没有什么噪声。但在生物学中，一个实验室做一组实验会得到一种结果，另一个实验室执行完全相同的协议，可能因为海拔差异，或者温度差异，又或是空气中的某些因素，他们就会得到完全不同的结果。所以我觉得噪声是让生命科学模型训练变得非常困难的关键因素之一。我们在细胞扰动数据等方面经常看到这一点。而且你所使用的实验技术中也存在很多偏差。例如，当你进行基因敲低或扰动，然后测量细胞随后发生的变化时，捕获分子以及读取分子的方式都存在偏差。所有这些噪声都会被放大。因此，我希望能有更多真正干净、低噪声的数据，其中的信号具有高度外显性，我们能够基于该信号进行训练。我们的团队确实在模型训练的整个流程中注入了这种生命科学知识，这意味着涵盖预训练、中训练以及强化学习或后训练阶段。因此，在获取数据之后，将数据塑造成模型在我们训练过程中可以使用的形式，本身也是一个很大的瓶颈。具体来说，我认为生物学中无噪声的数据类似于测序数据。比如生命之树的基因组，这种数据是没有噪声的，因为一旦你知道基因组中的某个字母是什么，那个字母就是确定的。此外，比如结构生物学也是噪声低得多的领域，因为你大致知道蛋白质的形状。当然，蛋白质会移动，它们可以改变形状，也就是我们所说的构象。但这比起人类健康数据来说，噪声仍然要小得多。电子健康档案是出了名的噪声大。这是因为人类健康通常是一个时间点状态，对吧？但你是在时间中移动的，当前的健康状态并不是你的永久状态。人生病，又痊愈。医生记录的内容中存在噪声，患者何时选择就医、何时不就医也存在噪声。因此，比起结构生物学这种极低噪声、高信号的数据，这类健康数据实际训练起来极其困难。
<details><summary>Original English</summary>
>> Yeah, definitely. Um, I think data is one of the biggest bottlenecks when it comes to training models because I think, you know, as people tend to say trash in, trash out. If you don't have really high quality data, generally your model's not going to learn anything useful. We see this a lot in biology versus, you know, things like coding or even chat GPT conversations where, you know, a a user is going to type a sentence and that sentence is what it is. there's kind of no noise around that. But in biology, you know, you can one lab can do a set of experiment, get one set of results, another lab can do exactly the same protocol and maybe it's a elevation difference, maybe it's like a temperature difference or something in the air, they just get something completely different. And so I think noise is one of the more um it's it's what makes life sciences very difficult to train on. And you know, we see this a lot with you know, cell perturbation data for example. And there's also a lot of biases in the experimental techniques that you do. So for example, when you do um gene knockdowns or perturbations and then you measure what happens to a cell afterwards, there's biases in the way that you capture the molecules and in the way that you read the molecules. And so all of these noise will just kind of amplify. So I think you know the type of data I wish we had more of is you know really clean low-noise data where you know the signal is a highly penetrint and we can uh be able to train on that signal and our team really you know kind of adds in this like life science knowledge across the pipeline of model training and that means you know like things in pre-training things in mid-training and things in reinforcement learning or post-training and so a lot of um the bottleneck too after we get the data trying to shape the data into a way that the models can use in our training process. Uh concretely, you know, what I think is like noiseless and biology are kind of like sequencing data. You know, here's like the genome of the tree of life like that is not noisy because once you know what a letter is in a genome, that that letter is what it is. Um and then you know things for example like structural biology which is also uh a lot more low noise because you roughly know the shape of a protein. Um, of course the proteins move around. They can change shapes, what we call confirmations. But this is still kind of a lot less noisy than if you look at, for example, human health data. Electronic health records are notoriously noisy. And this is because human health in general is a um a point in time, right? But you're kind of moving through time where there is like the current state of health is not your permanent state. People get sick, people get better. There's also noise in what doctors write down. there's noise and you know when patients choose to go to the hospital and not and so that data is actually incredibly difficult to train on than something that is you know just very uh low noise high signal like structural biology.
</details>

### 数据工厂与数据半衰期

>> 我们花了很多时间与从事初创企业的创始人交流，看到许多创始人的雄心是生成能引起你们兴趣的数据。实际上，现在涌现出了一批全新的公司——数据工厂公司。
<details><summary>Original English</summary>
>> So um we we spend a lot of time with founders who are working on you know their startups and and you know we see many founders whose ambition is uh to generate data that will be interesting to you. Um and in fact there is a an entire crop of company emerging the data factory company
</details>

>> 确实。
<details><summary>Original English</summary>
>> indeed
</details>

>> 他们就在那里，全神贯注地听你分享，迫不及待想知道答案。对于那些有抱负建立数据工厂的创始人，你会给出什么建议？
<details><summary>Original English</summary>
>> they're out there. They're listening to you intently. They're sitting on the edge of their seats. What would you advise a founder that is um uh has the ambition to build a data factory?
</details>

>> 问得很好。我个人确实经历过大批试图向我们出售各类数据的人潮。我认为数据有许多不同的形式。有些人只是想卖给我们实验数据，说“嘿，我做了一个实验，你想要原始数字吗？这是一个 CSV 文件”。也有人更多在做我们可能称之为人类专家数据的事情，或者类似于记录一个人在做什么，比如一个人提问，然后给出好答案的定义。我认为这两种数据有不同的用途：对于那种包含数字的 CSV 文件，这可能有助于建立模型理解自然世界的基础能力，非常有用；另一种类型则更偏向我们所说的后训练，即你现在拥有了一个具有很多原始智能的模型，但你需要以一种能够与用户沟通的方式展现这种智能。这时很多评估标准就派上用场了，比如模型是否提供了适当的背景信息？是否讨论了相关要点？是否说明了其确定性或不确定性以及最终答案？所以我认为我们需要这两者，以便让模型对每个人都发挥最大作用。我没有具体的建议。不过我认为我们看重的通常是高质量。对于原始实验数据，我们会采取一些非常直接的技巧来检查这些数据是否包含信号、是否干净。而对于更多后训练形式的数据，很多时候你必须亲自阅读并判断它是否合理。现在的模型实际上已经变得相当有能力，我们甚至可以让另一个模型来评估数据并告诉我们数据是否良好，所以在某种程度上这就像形成了一个闭环。
<details><summary>Original English</summary>
>> That is that is a good question. I definitely have you know personally experienced the flood of people trying to sell us uh different types of data. I think the the data takes many different forms. There are people just trying to sell us kind of experimental data to say hey I did an experiment you just like want the raw numbers. Um here's like a CSV file. There's also people who, you know, more kind of do what we might call like human expert data or, you know, things that are like here's like what what a person is doing. Um maybe a person asks a question and then here's like a definition of what a good answer is. I think there's different uses for these two types of data for you know the kind of like CSV file of numbers. This is a maybe fundamental capability of the model in order to understand the natural world and that is very useful. The other type is you know kind of more what we think about post- training which is you have a model now it's it has a lot of raw intelligence but you need to bring out that intelligence in a way that it's able to communicate with the user and so here's you know where a lot of these rubrics come in that's like okay did a model like um give you a proper background did it talk about these around points did it talk about its certainty or uncertainty and it final answer and so I I think you know we do need both in order to make a model that is maximally useful for for everyone. Um I I don't have like specific advice. I do think you know the things that we look for is generally high quality and you know for raw experimental data there are some just very uh obvious tricks that we will do to see okay does this does this data contain signal um is it clean and I think you know for the kind of more post- training shaped data a lot of that just kind of you have to read it and see if it it makes sense the models are actually getting quite capable now that we can kind of you know have another model evaluate the data and tell us if if the data is good so It's kind of like gone full circle in a way.
</details>

>> 你们对新数据的需求会随时间推移逐渐达到渐近线饱和，还是你们预期它会持续存在？
<details><summary>Original English</summary>
>> Does your appetite for new data asmmptote over time or is it something you just expect
</details>

>> 会一直持续？
<details><summary>Original English</summary>
>> will persist?
</details>

>> 我认为大多数数据集都有半衰期。数据类型可能会改变半衰期的长短，但总体而言，数据集的价值随时间呈指数级衰减。这主要是因为我们对数据极度渴望，如果无法在某个数据源上训练，我们就会寻找其他替代品。通常，当数据集之间存在某种相关性、且来自同一领域时，数据集之间就会发生我们所谓的正向迁移。因此，假设我们无法获得某一种数据，我们会在大量其他类型的数据上进行训练，最终无论如何都会获得我们真正想要的那种能力。所以我想说，并不是所有数据都具有永久价值，但我认为对越来越复杂数据的需求将是持续的。
<details><summary>Original English</summary>
>> I would say that most data sets have a halflife. Um the type of data changes maybe the halflife but I think there is in general an exponential decay in how valuable a data set is over time. And that's just because, you know, we're very hungry for data. And if we can't train on one data source, we'll find another substitute. And generally, when data sets are somewhat correlated, if they're from the same field, then there's what we call positive transfer between the data sets. And so, let's say we're unable to get one type of data, we'll train on lots and lots of other types of data and we'll eventually get that capability that we truly wanted anyway. Um so I would say that you know there's not all data will be permanently useful but I think the need for more and more complex data is going to be constant
</details>

>> 顺着 Jorge 的问题继续。所以你是说单一数据集的需求可能会经历指数衰减。
<details><summary>Original English</summary>
>> to build on Jorge's question. So you're saying that the demand for an individual data set might experience exponential decay.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 但比如 OpenAI 或大型实验室整体对训练数据的需求呢？你预期它是随时间呈指数级增长、线性增长，还是同样会衰减？
<details><summary>Original English</summary>
>> But let's say open AAI or the large labs demand for training data in general. Do you expect that to to exponentially increase over time, linearly grow, decay over time as well?
</details>

>> 我不认为它会随时间衰减。我预计它可能会呈线性增长。部分原因在于，我们越来越擅长生成自己的数据，无论是通过合作伙伴，还是通过模型自身深度思考并为我们生成新的合成数据。因此我认为我们仍然需要新鲜的新数据。我认为生命科学与编程的区别在于我们高度植根于物理世界。你无法真正完全模拟一个人：如果你给一个人某种化学物质，他们会如何反应？目前我们还没有建立在物理和机制基础上的模型方法。而相比之下，像编程这样的领域，你可以让模型生成一个代码库，并让其他智能体在这个代码库也就是合成数据上运行，对吧？这在生物学中并不完全适用。所以我确实预计，随着时间推移，生物学对数据的渴求会持续高于编程等领域。
<details><summary>Original English</summary>
>> I don't think it'll decay over time. I would expect it to grow possibly linearly. And some of this is because, you know, we're just getting really good at generating our own data uh either through partners or through, you know, the the model just thinking really hard and generating new synthetic data for us. And so I think um we're still going to need kind of like fresh new data. I think the difference between life sciences and coding is that we're very grounded in the physical world. And so you can't really fully simulate like a human. If you gave a human a chemical, how are they going to react? That is we don't have you know today a physically mechanistically grounded way to model that. But versus you know something like coding you can have the model generate a codebase and you can have other agents operate on that codebase on like your synthetic data right uh that doesn't quite apply to biology and so I do expect biology to kind of you know remain more data hungry than something like coding over time
</details>

### 与生命科学初创企业的生态合作

>> 顺便提一下，对于所有正在构建数据工厂初创企业的创始人，我们会把你们的手机号码［笑声］打在屏幕上，他们可以直接联系你们。好的，另一个问题：现在有很多创始人在为生命科学构建 AI 工具。他们应该如何看待自己与 OpenAI 的共存关系？或者他们该如何与 OpenAI 合作？又或者该如何避开 OpenAI？鉴于你们在该领域的北极星目标和野心，构建生命科学 AI 公司的创始人应该如何将 OpenAI 视为合作的“前门”？
<details><summary>Original English</summary>
>> so by the way um for all of the founders out there that are building their data factory startups what we'll do is we'll just have your cell phone number [laughter] show up on screen and they can just reach out to you guys directly um okay so another question There are so many founders out there that are building AI tools for the life sciences. How should they think about how they exist alongside open AI or how they partner with open AI or um you know how they run away from open AI like how do they think about what is that you know given your northstar and your ambition in the space how should a founders that are building AI companies for the life sciences think about open AI as a front door uh for partnership.
</details>

>> 这正是 OpenAI 中“开放”（open）的含义所在。我认为我们确实希望成为一个该行业用来完成所有日常工作的平台，但如果没有围绕它建立的庞大生态系统，我们就无法成为支持这一切的平台。当你回顾 ChatGPT、Codex 以及所有让它腾飞的因素时，关键就在于它如何接入人们开展工作的其他各个场景。因此，人们可以开发非常多不同的专用工具，在药物发现和药物研发流程中构建不同的组件。我对那些创始人想说的是，人们开展工作的场景正越来越多地转向 ChatGPT 和 Codex，就像当年迁移到微软 Office 套件、台式电脑和移动设备上一样。越来越多的人意识到，以它为前门是与所有这些不同计算工具及产品进行交互的最简单方式。从我们的角度来看，接入并集成尽可能多的这类系统的能力，让科学家能够使用完成工作所需的全部工具和系统，而无需费心去弄清楚如何将所有部件连接在一起。因此，我认为插件和 MCP 生态系统、连接器是至关重要的，因为人们正在改变如今的工作方式，我们真心希望在他们所在的地方与他们相遇。所以我想说，去打造一些插件吧，让我们携手合作。
<details><summary>Original English</summary>
>> Well, that is the open and open AI like I think we really want to be a platform that um you know the industry uses to do all of their day-to-day work but we won't be a platform uh to to allow that if we don't have all this huge ecosystem around it. So I think when you look at you know chatgpt and codeex and all the different things that made it take off it's how it plugged in to all the other places where people did their work. So there are so many different specialized tools that uh people can develop and different components in the drug discovery and drug development journey uh that I would say the thing I would say to those those founders is that more and more of where people are doing their work much like you know went into you know the Microsoft office suite and to desktop computers and mobile and so on is moving into chat GPT and codecs and increasingly people are realizing that the easiest way to interact with all these different computational tools and and uh and products is with that as the front door. Uh and from our perspective, the ability to plug into and integrate to as many of those systems as possible uh allows you know scientists to use all the tools and systems that they need to to get their work done um without needing to figure out how to connect all those pieces together. So I think the you know the plug-in and MCP ecosystem the connectors are critical because people are changing how they work today and we really want to meet them where they are. Uh so I would say um you know create some plugins and let's work together.
</details>

### 波士顿儿童医院案例与长程注意力

>> Joy，你提到的支柱之一是与学术界、制药界等各类团体合作生成证据，证明 AI 在这项事业中可以成为非常强大的工具。你们曾与波士顿儿童医院合作，你能谈谈那个项目包含哪些内容，以及它向我们展示了什么吗？
<details><summary>Original English</summary>
>> So one of the pillars you brought up Joy was working with various groups be they academia be they pharma to generate the evidence um that you know AI can be a very powerful tool here in this endeavor. you've worked with Boston Children's Hospital. Uh can you talk a bit about what that project uh entailed and what it showed us?
</details>

>> 是的，我认为这个项目极其精彩地展示了 AI 如今如何能够切实、积极地改变人类生活。这实际上是我团队一年多前与波士顿儿童医院合作的一个项目，如果大家还记得 o3 时代的话。当时他们的做法是给 o3 deep research 模型大约三到四百个未解决的病例，这些患者我们知道他们生病了，也拥有他们的基因组序列，但我们一直找不出诊断结果，不知道他们为什么生病、到底出了什么问题。这些孩子正在经历可怕的诊断……
<details><summary>Original English</summary>
>> Yeah, this is one of the projects that I think is a most beautiful demonstration of how AI can meaningfully and positively impact human lives today. This is actually a project that my team did with Boston Children's Hospital um more than a year ago and you know back in 03 time if people still remember what what this model was and what they did was they gave the model um 03 deep research around 3 to 400 unsolved cases of um people who we knew were sick. We had their genomic sequences but we couldn't figure out a diagnosis for you know why they were sick. What is actually wrong with them? These are children that are going through what is the horrible diagnostic
</details>

>> 奥德赛。
<details><summary>Original English</summary>
>> opposite.
</details>

>> 是的，完全正确。而且他们当中现在也不全都是孩子了。我要讲讲其中一个特别鼓舞人心的案例：这位女孩在九岁时发病，等待确诊等了二十年，直到我们将 o3 应用到她的病历档案中，我们才找到了潜在的病因。通常来说，这并不是治愈疾病的方法，但它是这段旅程的第一步。想想看，人们为了获取关于自身情况的答案不得不等待那么久，如果我们能将这些模型广泛部署，这是每个人都应该能够获得的能力，对吧？此外还有另一个案例，回想起刚才提到的无限注意力示例，我们遇到了一个案例，模型不仅阅读了患者的输入文件以及他们所有的不同突变，模型还判断出该文件中的信息不够充分。它实际上回溯到了测序仪输出的原始数据和原始读取片段（raw reads），重新进行了分析，并指出：“虽然所有这些内容质量都很低，但仍然可以进行分析，我认为这才是真正的致病原因。”随后我们进行了后续测序，结果证实模型是正确的。没有任何人类临床医生会有时间和精力去对每一位患者的每一个潜在突变都做这种事，投入如此多的精力是完全不可能的。但现在我们可以借助模型做到这一点。我认为这还是在 o3 时代，落后于目前的模型许多代，试想一下我们如今使用 GPT-6 Astra 能做到什么。这是我们非常期待与临床合作伙伴继续推进的一项研究方向。
<details><summary>Original English</summary>
>> Yes, exactly. And not all of them are children anymore. Um so I'll I'll talk about this one particular case which was really inspiring in which um this girl became sick when she was nine and she waited 20 years for a diagnosis and it wasn't until we deployed 03 to her file that we figured out what the underlying cause of disease was. And generally you know this is not a cure for a disease but it is kind of the first step on this journey and just thinking about you know how long people had to wait for answers about themselves and how if we just can deploy these models widely this is something that everyone should have access to right um and then there was another case too you know kind of calling back to the uh infinite attention example we had a case where the model um didn't only read the input file of you know here's the patient, here's all the different mutations that they have. The model decided there wasn't enough information in that file. And it actually went back to the raw data and the raw reads that were coming out of the sequencing machine and it redid this analysis and said, "Okay, all of these things were low quality, but it analyzed it anyway and said, I think this is actually the cause of disease." And then we actually did follow-up sequencing and turns out that the model was right. And no human clinician is going to have the time and attention to do this for every single potential mutation in every single patient. It's just impossible to pay that much attention. But now we can do that with the models. And so I think you know this was 03 time right this is like many many model generations behind. So imagine what we can do with you know GBT6 Astra today. And this is um a line of research that we're very excited to continue with our uh clinician partners.
</details>

>> 真是个精彩的故事。
<details><summary>Original English</summary>
>> That's a fantastic story.
</details>

### 可追溯性、人类判断与生物安全

>> 好的。我们谈到了数据，以及生成新数据并通过模型运行来发现新颖见解。从人类判断的角度来看，如果一个 AI 系统得出了专家无法立刻理解其推导过程的结论，类似于波士顿儿童医院的案例，我们需要从那里生成什么证据来理解该结论？在理解我们尚未完全搞懂的 AI 系统结论时，人类判断在其中扮演什么角色？
<details><summary>Original English</summary>
>> Okay. So we we spoke about data and generating new data to ident and run that through models to identify novel insights. From a human judgment perspective if a AI system identifies or comes to a conclusion that experts don't meatily understand how it arrived at that conclusion. It's similar to the Boston children's example as one example. What evidence do we need to do we need to generate from there to make sense of that and how can where does human judgment come in in making sense of a AI system conclusion that we don't fully understand?
</details>

>> 是的，问得非常好。我认为这就是从模型能力过渡到评估框架（harness）和底层上下文变得至关重要的节点。生命科学行业的一个概念是可追溯性和监管链：我如何知道并追踪每一个步骤，以确保我能够信任实验中产生的结果？在这种情况下，几乎存在一个等价的“证据链”概念，对吧？因此，当模型得出结论时，你如何汇编所有支持性证据并一路回溯，使人类能够在比他们自行得出该结论更少的时间内对其进行评估。我认为这是一个关键的基础组成部分，如果你想在药物发现和研发中大规模使用这些系统，输入的可追溯性和可解释性能让拥有适量时间的人实际审查这些输出并得出相同的结论。你会在发现和研发的许多产品功能中看到这一点。因为你不仅要确保自己不会放大错误，还要在核心系统中真正建立信任，而且随着时间的推移，系统会越来越擅长理解什么样的证据适合用来得出结论。
<details><summary>Original English</summary>
>> Yeah, it's a really great question and I think this is where you go from model capability to where the harness and the underlying context becomes critical. uh you know a concept in the industry uh for for life sciences is traceability and chain of custody like how do I know and how do I follow every single step to know that I can trust the outcome uh that was that was generated in an experiment and in this case there's almost an equivalent concept of like chain of evidence right so when when a model comes up with a conclusion uh how can you compile all of the supporting evidence and trace that all the way back so that a human can evaluate that in less of the amount of time than it would have taken them to come to that conclusion. So I think this is like a critical and foundational component if you want to use these systems at scale and discovery and development that the traceability of inputs and the explanability of inputs could allow somebody with you know the appropriate amount of time to actually review those outputs and come to the same conclusion. And you're going to see this in, you know, a lot of product capabilities across discovery and development. Uh because, you know, instead of like you want to make sure you're not amplifying errors, you want to actually build trust in the core system and over time the system gets better and better at understanding what is the appropriate evidence to come to a conclusion.
</details>

>> 顺着这个思路继续深入，因为人类判断很重要，建立信任的能力也很重要。OpenAI 如何看待不单单是犯错、而是有人故意试图滥用该技术来做危险事情的影响？关于这种信任与安全的问题，你们是如何应对的？如何在避免过度限制——以至于实际限制了人们利用 OpenAI 进行真正科学发现的能力——与设置充分的防护栏以防止利用该技术制造危险局面之间找到适当的平衡？
<details><summary>Original English</summary>
>> So maybe just to pull on that thread um because you know the importance of judgment of human judgment, the importance of being able to build trust. Um how do you how do uh how does OpenAI think about um the implications of not getting things wrong but someone intentionally trying to m misuse the technology to to to to do something dangerous. So this question of trust and and safety um how how have you all approached that and how do you find the right balance between not having it be overly restrictive so you're actually restricting uh people's ability to to to use open AI for genuine scientific discovery but guard railing sufficiently so that you know we're not in you know creating dangerous situations with this technology
</details>

>> 对。我认为我们在考虑生物安全和生物防范时最早注意到的事情之一，就是仅凭阅读提示词几乎无法判断一个人的意图。如果一个人在讨论某种植物疾病，表面上你可以认为他们可能试图寻找植物的利用漏洞，或者只是在进行正常的学术研究，又或者是在试图寻找治疗方案。我们在非常早期就决定，由于无法轻易从这类对话中获取信号，思考有益部署模型能力的正确途径应当基于受信访问。受信访问意味着你在正规机构工作，比如制药公司或生物技术公司，我们知道你对这些模型能力具有合法的应用场景。例如，你在 Moderna 工作是因为要研发疫苗；通过验证你确实是自称的那个人，并且你工作的公司是一个合规合法的实体，我们就可以建立信任。我们能够为你提供完整的模型能力，而无需去猜测你要做什么然后在特定事项上阻拦你。这为我们的许多合作伙伴带来了巨大的能力释放，因为现在他们可以自由地向模型询问任何想问的内容，而不必担心弹出红框拦截。
<details><summary>Original English</summary>
>> right I think one of the earliest things we noticed when we were thinking about you know biosafety and biocurity is that it is almost impossible to tell what a person's intention is from reading their prompts. Uh, and I think, you know, if a person is talking about a plant disease, you could ostensibly think that maybe they're trying to find an exploit in the plant or they're trying to just study like a normal academic study or trying to find a cure. And very early on we decided that because we can't easily pick up signal from these kind of conversations, the right way to think about beneficial deployment of model capabilities should really be based on trusted access. And trusted access means that you know you work at a legitimate institution. Maybe this is like a pharma company, maybe this is a biotech company, but we know that you have a legitimate use case for these model capabilities. So for example, you work at MADNA because we're making vaccines and um from validating that you really are who you say you are, the company you're working for is a legitimate place, then we can say, okay, well, we trust you now. We can um give you the full model capabilities without, you know, trying to guess who you're trying to do and then blocking you on specific things. And you know, this has been really uh a huge unlock for a lot of our partners because now it's kind of like they have the freedom to ask the model whatever they want and they don't have to be worried about kind of like a red uh box showing up.
</details>

>> 我认为这种方式实际上比单纯建立极严格的监控系统更安全的理由在于，生物技术或制药公司通常会追踪所有试剂的来源，记录科学家所做的一切，而这种追踪和记录作为一家 AI 公司是不可能做到的，那会造成极大的侵入性。因此，这带来了两全其美的效果：我们能够确认你是一个受信人员，我们希望为你提供最大的模型能力，供你推动科学前沿、发现疾病的新疗法；同时我们也知道，他们的行为受到了雇主和实验室的监控。我认为这能让我们以最快的速度前进。
<details><summary>Original English</summary>
>> And the reason why I think this, you know, actually more secure than if we had just a like very intense monitoring system is because when you look at a like biotech or pharma company, they generally track the provenence of all the reagents. They log everything that a scientist is doing and this kind of tracking and logging is impossible for us as a AI company to do. It would just be hugely invasive. And so I think this gives you the best of both worlds where we can say okay you are a trusted person. We want to give you the maximum amount of uh model capabilities for you to push frontiers of science to discover new cures for diseases. And we also know that, you know, what they're doing is monitored by their employers, by their labs. And I think this allows us to just, you know, move at maximum speed.
</details>

### 未来展望：单人生物技术公司与行业放大器

>> 我很想聊聊未来。我们探讨了非常广泛的内容。我对你在 open health 团队的同事 Karen 也提到过，ChatGPT 仅在几年前发布，这本身就令人惊叹、备受鼓舞且令人谦卑。因此，如果去预测遥远的未来，哪怕是三到五年后，听起来都像是在空谈理论，谁也不知道会发生什么。但为了给我们一些可以期待的东西，在药物发现、开发、分发或生命科学其他领域中，有什么是今天感觉不可能，但在短短几年内一个小团队就能做出的非凡成就？请就你们正在从事的工作给我们一些值得期待的前瞻。
<details><summary>Original English</summary>
>> I'd love to talk a little bit about the future. We covered a lot of ground. Uh I mentioned this to your colleague Karen um on the open health team that it is amazing and inspiring and humbling that chat GPT just came out just a few years ago. And so if we start making predictions about the distant future even 3 to 5 years from now sounds academic who knows what what might happen but um to sort of give us something to look forward to. What is something across discovery development distribution or elsewhere in the life sciences where today it feels impossible but a small team in just a few years could do something pretty extraordinary. just give us something to to look forward to about the work uh that you all are doing.
</details>

>> 我想你可以将生命的技术栈想象为底层是物理学，然后考虑原子及其相互作用，再发展为化学，接着是生物学，最后到人类。我认为我们将看到的纳维-斯托克斯级别的突破，首先将发生在原子系统层面，并从少数原子系统发展到化学反应，再到结构生物学，最终扩展到细胞系统和整个生物体。但我认为所有这些系统在某种噪声上限之内都将被所谓“解决”，可能就在接下来的两年内。但我预计我们会从更接近数学的领域开始。当然，我所说的“解决”只是指在该领域取得基础性突破。我认为有很多事情，尤其在药物发现方面，仅仅受限于生物学的速率限制，我们无法从根本上改变这些速率常数，但我认为模型能力领域将会涌现出许多非常激动人心的成果。
<details><summary>Original English</summary>
>> I think you can really imagine kind of the the light uh stack of life as you know um physics at the bottom and then you think about atoms and how they interact and how that grows into chemistry and then biology and then humans. I think the type of um Navier Stoke level breakthroughs that we're going to see is going to first happen at more of the atomic systems level and I think that will kind of grow from um few atom systems to chemical reactions to structural biology and eventually it'll build up to you know um systems of cells entire organisms but I think all of these will become quote unquote solved up to some noise ceiling in the system um probably over the the next two years but I I expect we will start closer to um math and of course when I say solve I just mean you know having foundational breakthroughs in the area. Um I think there's a lot of things you know especially when it comes to drug discovery that are just limited by the rate of biology and I don't think that you know we're going to be able to fundamentally change those rate constants but I think there are a lot of really exciting things that all come out of the model capability world.
</details>

>> 是的，在发现和开发端，设想一个人就能创办一家生物技术公司，启动多条管线并将其推进到临床试验，真正放大这些能力与专业知识，这是该未来的一种愿景。但我也认为，这能真正大规模扩展任何组织中任何个人的能力，使其能够发挥最高水平的专业资质（operate at the top of their license）。无论你是在制造部门、制药公司、临床运营还是在药物发现领域，这些系统如何帮助你更快、更高质量地完成现有工作，探索更广阔的空间——我认为这将是一股提升整个行业的浪潮。当然存在一些实质性的约束，比如人类生物学的发展速度本身就有限，监管也是一个需要改变的大杠杆；但从生物技术与大型药企的对比中，行业已经见证了小团队在创造突破性药物方面能够做到什么。我确实认为这是整个行业的巨大放大器，当然在生物学中也存在一些根本性的限制。
<details><summary>Original English</summary>
>> Yeah, and I think on the discovery and development side like I think you know envisioning a world where one person can start a biotech company and launch many programs and get those to clinical trials and really amplifying that those abilities and expertise is one you know version of this of this future but I also think you know really like massively scaling the ability of any individual at any organization uh to do their like to to operate at the top of their license. So whether you are in you know manufacturing and a pharma company and clinical operations in discovery and so on um how can these systems help you uh do the existing work you're doing faster and at higher quality explore wider space like I think it will that's a rising tide that will lift uh the entire industry there are some substantial constraints right like you know human biology only moves so quickly regulation is a big lever that needs to to be changed uh but a you know the industry has seen um you know in its biotech versus pharma like what can small teams do in order to make breakthrough medicines and I do think this is a great amplifier uh for the whole industry um with some fundamental limits of course in in biology.
</details>

>> 你认为我们很快能看到单人生物技术公司吗？
<details><summary>Original English</summary>
>> You think we'll see one person biotech anytime soon?
</details>

>> 非常看好。是的。
<details><summary>Original English</summary>
>> Very much so. Yes.
</details>

>> 再次祝贺 OpenAI 收购 Orchestra Bio。听起来未来有很多令人振奋的工作要展开，再次感谢两位做客 a16z 播客。
<details><summary>Original English</summary>
>> Congratulations to OpenAI again on acquiring orchestra bio. It sounds like uh a lot of exciting work to come and thank you again for joining the A16CTC podcast.
</details>

>> 非常感谢邀请我们，非常愉快。
<details><summary>Original English</summary>
>> Thank you so much for having us. That was fun.
</details>

>> 好的。
<details><summary>Original English</summary>
>> All right.
</details>