---
author: AI Engineer
date: '2026-07-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1EZdpEhwmNc
speaker: AI Engineer
tags:
  - agentic-security
  - dependency-health
  - mcp-server
  - vulnerability-remediation
  - ooda-loop
title: 穿越 AI 迷雾：自主代理（Agentic）时代安全架构的关键决断
summary: 本篇双语访谈记录了 Snyk 首席创新官兼 CTO Manoj Nair 在 World's Fair 上的精彩演讲与现场演示。探讨了在 AI 代理（Agentic）与大模型驱动的新时代下，企业面临的三大核心安全痛点：自主化攻击的兴起、不可信的代理输出与行为环境、以及难以治理的“影子 AI”资产。通过现场演示，展示了 Snyk 如何通过包健康度检测与 Skill/MCP 风险评估工具，重塑生成器与验证器分离的安全架构，为 AI 安全工程师赋予 10x 超能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Manoj Nair
  - Ezra
  - Randall
companies_orgs:
  - Snyk
products_models:
  - Evo
  - Snyk Studio
  - Claude
media_books: []
status: evergreen
---
### 开场致辞与嘉宾介绍

**Randall**: 大家好！很高兴能在**世界博览会 (World's Fair)**有史以来的首个**安全专场 (Security Track)**看到你们所有人。老实说，今天是非常令人兴奋的一天，因为和在座的各位一样，我发自内心地热爱这些技术。在看过了我们今天的发言人日程表之后，我相信这里将会有极其有用且有趣的硬核信息。因此，希望如果你们能在这里坚守一整天，在今天结束的时候，大家能够回到酒店房间，并着手构建一些真正酷炫的软件——而且理想情况下是**无人类参与 (Humans-in-the-loop)**的自动运行软件，因为这才是我们的终极目标，对吧？也就是，我们该如何在规模化场景下构建出真正安全的**自主化软件 (Autonomous Software)**？而这绝非易事。

话虽如此，我非常激动地欢迎我的挚友兼同事——**Manoj Nair**。他是 **Snyk** 的首席创新官 (Chief Innovation Officer) 兼首席技术官 (CTO)。在加入 Snyk 之前，他曾担任 Convo IT 的首席云官 (Chief Cloud Officer)。他创立并运营了 HyperGrid，并曾在 HPE、Dell 和 RSA 担任过产品和安全方面的领导职务。此外，他名下拥有大约十多项个人专利。所以，他可以说是这个领域里的一个传奇人物。而且，他个人也亲自参与了今天整个安全专场的策划工作。所以，如果你们喜欢今天的演讲，请在结束后亲自向他表达感谢；如果觉得不好，那可千万别怪我。那么，让我们有请 Manoj 登台！

<details>
<summary>Original English</summary>

**Randall**: What's up, everyone? Good to see you all here in the very first ever security track at the World's Fair. Um pretty exciting day, honestly, because uh like all of you, I genuinely love this stuff, and having looked through the agenda for the speakers we have today, um it's going to be absolutely mind-blowingly useful and fun information. So, hopefully if you stick around all day, by the end of the day, you'll be able to leave here, go back to your hotel rooms, and build some genuinely cool software, hopefully without humans in the loop, because that's the ultimate goal, right? Like, how do we build truly safe autonomous software at scale? And it's not something easy to do. So, with that being said, I'm very excited to welcome my good friend and colleague, Manoj Nair. He is Sneak's Chief Innovation Officer and CTO. Um before Sneak, he was the Chief Cloud Officer at Convo IT. He founded and ran HyperGrid. He did product and security leadership at HPE, Dell, and RSA. And he's got something like a dozen patents to his name. So, he's kind of a legend in the space. Uh he also personally had a hand in curating this entire track. So, if you like the talks today, please go up and say thank you to him after, but if not, then just don't blame me, basically. Um but yeah, welcome to the stage, Manoj.

</details>

---

### 拥抱安全：拨开 AI 的迷雾

**Manoj Nair**: 噢！非常感谢你，Randall。我可真没料到你还会来一段个人生平介绍。大家好，非常感谢大家在听完刚才前面精彩的主旨演讲后，能来到这个分会场。我是 Manoj Nair，非常荣幸能带领一支优秀的团队，正在为全球大约 5000 家企业客户提供安全保障。这让我看起来很有面子，但我今天想要展示的，是来自这些客户的真实数据。**《财富》500强 (Fortune 500)**中有一半的企业都在运行 Snyk 的服务，我们今天分享的一些数据就是基于这些企业在实际运行中的经验和教训。

不过在此之前，我也想聊聊这个主题。我想今天演讲的题目应该是“穿越 AI 迷雾 (Cutting through the AI fog)”。而我们拨开迷雾的方式，就是通过设立今天这样的专题论坛。去年我们站在这里时，有 3000 人参加了 **AI 工程师峰会 (AI Engineer Summit)**，但说实话，在那个会场里，大家能明显感觉到“安全”这一主题是缺席的。非常感谢 Swig 以及与 AI 工程师组织之间的精彩合作，我们联合创办了 AI 安全峰会。我们也创建了今天的安全专场，能看到今天这个专场的设立，以及所有即将在这里分享精彩硬核知识的优秀讲师，我感到由衷地高兴。在我们看来，这就是我们穿越迷雾的方式，对吧？安全必须成为研发团队和会议室里不可或缺的核心话题。我们非常热衷于推动安全的发展，而且我们的初衷绝对不是为了拖慢开发速度，而是为了让大家能够真正构建出值得信赖的系统。

所以，今天你们会听我反复强调一个观点——如果你今天只想带走一个核心要点，那就是我们从这些现实世界的数据中，以及与全球最大的前沿实验室 (Frontier Labs) 和最顶尖的企业合作中提炼出的核心理念。这是一个在以前的安全领域几乎从未被质疑过、但在现在却被反复提及的问题：**生成器 (Generator) 和验证器 (Validator) 是否可以由同一个主体担任？**我们的观点是，在稍后展示的一些数据中，你会看到由于各种原因，答案显然是“否定”的。

而且，如果你了解 Snyk，请不要只把它看作是一个进行了“安全左移 (Shift Left)”的软件供应链安全公司。接下来你将看到的很多内容，实际上是我们在过去 18 个月里，与一些非常大型的企业合作，在采用那些我们都为之兴奋、都非常热爱的复杂 AI 系统时所获得的真实洞察。我们从中到底学到了什么？

<details>
<summary>Original English</summary>

**Manoj Nair**: Woo! Thank you, Randall. I was not expecting a bio. Hi, everyone. Um really appreciate uh you all joining here um right after those great keynotes up front. Uh I'm Manoj Nair, and uh I have the uh pleasure of leading an amazing team that is helping secure about, you know, 5,000 enterprise customers around the globe. Uh so, I get to look good about all of that, but some of what I'm going to show is real data from those customers. Half of Fortune 500 runs on Sneak, and some of the data is, you know, from those learnings. But before that, I I also want to talk about this, you know, the title of the talk was cutting through the AI fog, I think. But the way we do that is by having tracks like this. So last year we stood here, there were 3,000 people at the AI Engineer was there, and you know, it really felt like security was missing in the room. And thanks to Swig and amazing partnership with the AI Engineer organization, we created the AI Security Summit in partnership with them. And we're creating this track, so it is really good to see this and all the great speakers who are going to talk um here today with some fantastic knowledge. But that is in our mind, like that's how we cut to the fog, right? Security needs to be very much part of the room. We're very passionate about it not slowing things down, but really that's how you build trusted systems. So, one thing you're going to hear from me quite a bit of, you know, in this like, you know, what if you take one thing, it's this notion of our learning from this real-life data and working with the biggest frontier labs in the world and the biggest companies in the world is this concept that has really been, you know, not questioned in security before, but it is being asked now, right? Can, you know, the generator and the validator be the same? And our point is, you know, in some of the data you'll show for all kinds of reasons why not, right? And almost like if you know Sneak, don't think about the supply chain security company that shifted left. Like a lot of what you'll see is the last 18 months of what we have been doing with some of these very large enterprises in adopting, you know, these complex systems that are we're all in joy and we love, and what are we learning from that?

</details>

---

### 企业在 Agent 时代面临的三大痛点

**Manoj Nair**: 当我们与这些客户沟通时，通常会听到三个核心痛点。我想分享这些痛点，并展示其背后的具体数据。但从根本上说，当你思考这个会场以及你们所支持的每一位开发者时，大家都在前沿领域进行极速的构建。然而，目前没有人能够回答的一个关键问题是：**你是否能够真正信任你的 AI 代理 (Agents) 刚刚交付的代码，以及它们完成这些代码的具体方式？**

如果你去粗取精——我也非常享受经常与这些客户进行深度交流的机会——这基本上是每个企业都会遇到的第一、第二或第三个问题，甚至三个问题全占了。这就是正在发生的真实对话。

第一是**自主化攻击 (Autonomous Attacks)**。这绝不是什么神话，我也不是在谈论什么 GPT-55 级别的超级网络科幻武器。事实上，我们看到这些攻击正在真实发生。所有前沿实验室的大模型都被用于自动化攻击。甚至不需要使用最顶尖的前沿模型，你就能发起这样的攻击。我们已经证明了这一点，不幸的是，攻击者也证明了这一点。一旦结合了良好的上下文环境和强大的运行框架，攻击者就拥有了一个永远不知疲倦的自动化攻击引擎。这带来了什么后果？过去 10 年里我们试图去颠覆的应用安全 (Application Security) 基本法则，现在已经完全被打破了。过去，你可能会做一些上下文风险管理，然后自我安慰说：“我已经修复了系统里所有‘严重 (Critical)’和‘高危 (High)’级别的漏洞，剩下的都太难利用了，所以我现在应该挺安全的。” 但在现在，这种观念彻底过时了。攻击者可以通过串联多个“低危 (Low)”级别的漏洞，像拼图一样构建出完整的攻击链路。而且正如我们所见，即使没有复杂的运行框架，仅依靠普通级别的模型，只要稍加引导，攻击者就能做到这一点。如果再加上一点额外的努力，利用现有的其他模型，他们几乎能攻破任何系统。因此，这是我们看到客户在实时做出反应时所面临的极其巨大的、颠覆性的变化。

这时你可能会惊叹：“哇，有一千家企业在购买和部署云端代码助手 (Cloud Code Rollout) 上花费了超过 100 万美元。所以，这就是解决安全问题的答案，对吧？” 嗯……可能吧。让我们顺着这条线索往下深入剖析一下。

<details>
<summary>Original English</summary>

**Manoj Nair**: Um, there are three problems that, you know, we hear when we talk to these customers. And I want to share those and I want to like kind of show some of the data behind that. Um, but, you know, fundamentally, it's it's really looking at this as um you think about this room and everyone that you support, you know, you're building fast at the frontier. The question nobody is answering is, can you trust what your agents just shipped and how they did it, right? And so if you'd really take, you know, the gist of and I I have the joy of talking to all of these customers a lot, this is pretty much every one, two, or three or all of them. It's really the con- conversation that happens. So, autonomous attacks, like, you know, it's not mythos, it's not, you know, I know I said the M word, but sorry. Uh, you know, it's not, you know, GPT 55 Cybers. Like, we're seeing that you can have these attacks. All the frontier labs have been used in automated attacks. You can do that even without having frontier models. We have shown it, so have the attackers, unfortunately. With good context and good harness, now you have an attacker that never sleeps. What does it do? The fundamentals of things like application security that was already something we tried to disrupt for 10 years have completely, you know, gone away. Like, oh, you cannot have contextual risk management and say, I fixed my criticals and I fixed my highs and I'm pretty good because everything else is too hard. No, you can string low vulnerabilities and and, you know, create exploits. You can do it without a lot of a harness with the mythos class model, as we've seen. And and but with a little bit of, you know, effort, you can do it with everything else. So, so that's a big big, you know, sea change in how, you know, we are seeing our customers actually react real time. And then you go, wow, a thousand enterprises spend over a million dollars for, you know, a cloud code roll out. So, this is the answer, right? Well, mhm maybe. Let's let's let's pull that string a little bit.

</details>

---

### 代码膨胀、第三方插件与代理行为失控

**Manoj Nair**: 现有的一系列问题正在变得越来越糟糕。首先，大模型生成的代码质量，不幸的是，往往比人类手写的代码质量还要差。这并不是说人类写的就是完美代码——我自己就是工程师，我从来不认为我写过完美无瑕的代码，我们中没人能做到。但 AI 生成的代码实际上要更差一些。如果这只是唯一的问题，那倒也还好。

但运行环境呢？我们现在觉得非常神奇的很多功能，全都是基于各种技能插件 (Skills)、**模型上下文协议 (Model Context Protocol, MCP)** 服务以及所有我们想要共享和使用的生态工具构建起来的。而这些东西，无论是故意还是无意的，目前都正在遭受毒化。恶意软件正被注入其中，稍后我们会展示相关的研究成果。

然后是代理的实际行为。我们正在看到这些新型问题在旧问题之上不断累积和恶化。

在这个世界上，现在有哪个公司不想成为一家 AI 公司？在任何地方，每一家公司的董事会都在宣称：“我们要利用 AI 转型我们的业务，重塑我们的工作流。” 或者是你正从零开始成立一家全新的公司，那么你天然就是完全**自主代理化 (Agentic)** 的。然而，当你用代理和大模型构建应用时，你会引入一个在以前的架构中根本不存在的全新的**威胁面 (Threat Surface)**。这就是最根本的痛点。

我想分享一些真实的数据。在过去的一年里，在我们 4800 多家客户中，他们的实际安全漏洞积压量 (Backlog) 季度环比增长了 108%。所以，请记住我刚才提到的关于攻击者的话。这不仅仅是现有的那些存量漏洞。而且不幸的是，如果你是一家稍有规模的企业，系统里的漏洞往往多达数百万个。关键在于，尽管我们使用了最先进的代理工具，尽管行业和我们自己做出了最大努力，漏洞的总量依然在以惊人的速度增长。这个趋势是实实在在的，而且形势不容乐观。

此外，还有许多看似新颖但本质上并不新奇的漏洞利用方式。比如针对大模型连接层的漏洞利用，它实际上就是利用了新架构表面下的现有漏洞，并将它们串联在一起。在当前极快的业务推进速度下，这会造成大得多的**波及范围 (Blast Radius)**。是的，速度是导致这一局面的重要因素，但绝不仅仅是速度的原因。

就在上周，由多国组成的**五眼联盟 (Five Eyes)** 情报机构领导人发表观点称，AI 将在几个月（而不是几年）内学会如何绕过现有的网络安全防御系统。我分享这些并不是为了制造恐慌，这只是一个摆在我们面前的事实。我们必须为即将到来的一切做好准备，而且我们已经看清了未来的走向，只是目前这种威胁还没有扩散得足够宽泛。因此，我们的观点是：如果只是试图通过盲目追逐新系统，或者寄希望于某一个特定的大模型来成为解决所有安全问题的解药，这显然是行不通的。

<details>
<summary>Original English</summary>

**Manoj Nair**: The There are existing classes of problems that are getting worse. The quality of code is unfortunately worse than human-generated code. It's not like humans we I'm an engineer like I don't think I wrote perfect code, none of us do. So, but it is actually a little worse. And so, well, if that was the only problem, that's okay. But what about the environment? All the things that we find as magical are based on skills and MCP servers and all these things that we want to share and use. And those are intentionally or unintentionally both, you know, being poisoned and, you know, malware's injected in there and we'll show some of the research on that. And then the behavior of the agent, right? And so, so we're having these these, you know, new patterns of problems compounding on top. And then who here doesn't want to become a an AI company or in any room in the world, right? Every company every board's like we're going to transform our business, our workflows, or you're starting brand new, you are fully agentic. And when you build with agents and models, that's an entirely new threat surface that was not part of the prior one. And so, these are really the fundamental problems, right? And and this is, you know, I want to share some of the real data. This is 4,800 plus customers in the last year. Their actual backlog quarter over quarter is like 108% more backlog. So, remember that what I said about attackers? It's not just the existing vulnerabilities. And unfortunately, there's millions of them if you're an enterprise of any size. It's the fact that we are growing them despite the best agents, despite things that we have done and the industry has done. This trend is real and it's not good. And, you know, you have novel exploits, but they're not novel. Like the light LLM exploit, you think about like it's really taking existing vulnerabilities in the new surface and chaining them together. And so, they create a much bigger blast radius right now at the pace at which work's being done. And yes, speed is a big part of this, but it's not just speed. And you know, just this um last week we had the Five Eyes uh you know, uh these are the the the Western world's uh intelligence leaders talking about AI will bypass cyber security systems in months, not years. Now, I don't share you know, share this I hate to have the scare tactic. It's just a fact. It's getting ready for you know, whatever is coming and we have already seen what's coming. It's just not widespread enough. And so, trying to like you know, chase systems and like the specific model will be the cure for all this is not the way is our point.

</details>

---

### 基准测试数据与代理的异常行为

**Manoj Nair**: 接下来让我们看看第二个痛点——代理的不可信输出、环境和行为。这些也都是无可争辩的事实，是来自基准测试的真实数据。PPT 顶部的二维码可以带你们直接去查看这些研究背后的详细论文和数据。

首先是最新模型生成的代码中所包含的漏洞比例。此外还有插件，我们发现存在恶意插件。我们的开创性研究表明，在目前所有的技能插件（不仅仅是公开的 **Claude** 或各种代码代理插件）中，有超过三分之一的插件实际上包含恶意软件或安全漏洞。现在，仅仅三行简单的英文指令，就足以让一个系统彻底瘫痪。因此，你必须真正理解这些指令背后的真实意图。

还有 MCP 服务器，也就是你用来连接企业内部数据的桥梁。这是一个非常棒的协议，但在安全机制的设计上却考虑得非常少。虽然它现在正在变得越来越好，但它的安全基础依旧很薄弱。这就是我们在一年前向业界披露的 **GitHub MCP 服务器漏洞**。当时我们的客户做了什么？他们第一时间直接关停了所有的 MCP 服务器，随后他们发现所有的开发者屏幕都黑了，接着他们不得不去思考如何在保证安全的前提下重新开启这些非常强大的功能。

至于代理的异常行为，大家应该都知道 PocketOS 的例子。而我这里有来自我们自己环境里、在我们的《财富》100强企业客户中发生的真实数据：这些 AI 代理会在未经授权的情况下，主动在后台复制并保存包含个人身份信息 (PII) 的数据。为什么会这样？因为某个用户在试图解决一个真实客户问题的过程中分享了 PII 数据。AI 代理在执行任务时自作聪明地认为：“也许我应该把这些数据悄悄备份到某个数据库里，以备我下次还要用到它。” 然而，它备份的那个数据库是完全不受信任且不受控的。结果就是，你在毫不知情的情况下，多出了一个游离于企业安全防护网之外的未知攻击面。这种事情每天都在发生。那么，我们该如何在不简单粗暴地设置层层阻碍的前提下，去合理地引导它们呢？

这就引出了最后一个问题：你无法治理你根本不知道其存在的东西。当你开始用代理构建系统时，这一点尤为明显。根据我们对 3000 多家客户的代码库智能分析数据，我们发现：在一个代码仓库中，每存在一个 AI 大模型，其背后通常就会伴随有**三倍数量**的代理组件。代理无处不在，存在于它们使用的各种工具和依赖中。你必须掌握整个系统的完整版图，因为风险绝不仅仅存在于单一的层面上。

一旦你找到了这些组件，你怎么知道它们有多危险？你的独立数据验证手段是什么？这是我们从我们自己的风险数据库 (Risk DB) 以及红队 (Red Teaming) 攻击测试中得到的数据。每当有新的模型或组件发布时，我们都会对其进行安全检测。

前两个是大家最喜欢的顶级前沿模型。你们可以猜到是哪两个。它们在防 PII 数据提取的测试中表现优异——以前它们在面对我们的模拟攻击时表现没这么好，但这次表现很棒，我们的红队攻击没能提取出 PII 数据。

而第三个，是最近在硅谷非常火爆的新模型，最近几周大家都听说过它。在测试中，我们 100% 成功地通过红队攻击从该模型中提取出了敏感的 PII 数据。

然而，当我们切换到另一个测试项目——“决策覆盖 (Decision Override)”（即诱导模型推翻其既定的安全策略）时，那两个顶级前沿模型的表现却变差了。相反，那个开源模型在我们的攻击下，决策被成功覆盖的概率却是 0%。

了解这些差异，能让你清楚地知道在什么场景下应该使用什么模型，以及如何去实施对应的安全控制，因为这些特性每天都在发生动态的变化。

<details>
<summary>Original English</summary>

**Manoj Nair**: The data on the second pain point, the untrusted output environment and behavior of agents. And these are again facts. These are benchmark data facts. All of them the QR codes at the top are are if you want to like go check out the studies and the research behind it. This is you know, the amount of vulnerable code coming from the latest models. Plus the skills, there's toxic skills. We found the research the seminal research around how skills a third of them or more than a third of them in all of the skills, not just you know, open claw, clawed, code acts, these skills actually have malware and they have vulnerabilities that are being Three lines of English are able to now bring a system down. So, you have to really understand the intent behind it. And the MCP servers, how do you connect to enterprise data? This is great protocol, very little security built in. It's getting better, but the foundations behind it is you know, this is the GitHub MCP server exploit that we highlighted to the year a year ago. And what did some of our customers do? Immediately shut down all MCP servers then they figured out that all of their dev screens and then how do you actually go back safely enabling things that are very powerful. And then on the behavior, everyone knows the pocket OS example, right? What I have is real data in our own environment in our Fortune 100 customers. These agents go and create copies of PII data. Why? Somebody shared the PII data and was trying to solve a real customer problem. The agent thought that maybe I should create a squirrel away copy of this in a database just in case I needed it again. That database is untrusted. Great. You now have an unknown attack surface that is not part of any enterprise security, you know, um, coverage. This is happening. So, how do you not put gates on it? How do you steer them, right? And so, you start going into, you know, the last part problem is you can't govern what you don't know exists. This is when you start building with agents. Now, this is real data from 3,000 plus customers who have used our abilities to really find the intelligence of what's in their code bases, what they're building. And for every model that we find in a repo, you have three times more agentic components in there. You have agents in the tools and everything that they use. You have to figure out the full landscape because the risk is not just at one layer. And then once you find it, what do you how do you know how risky is it? What is your independent data verification? So, this is from this weekend from our risk BB that we have built our own attacks and red teaming capability. As new new models and new, you know, components come out, we check them. The first two are your favorite frontier models. You can guess which ones those are. They did awesome on PI extraction like they didn't used to be so good on with our attacks. No PI extraction with our attacks. The third one is is your is is the hot new model in Silicon Valley especially or this you know last few weeks rhymes with LLM 100% 100% of the time our attacks were able to extract PI. But when you check a different test decision override the frontier models did worse. The open model 0% of the time you were able to override the decision at least with our attacks. Knowing this allows you to know what to use when to use that and how do you control and these things are changing dynamically.

</details>

---

### 重新审视生成器与验证器的分离

**Manoj Nair**: 回到我们最开始的论点：如果上述数据还不足以说服你必须在架构上将生成器和验证器进行分离，那么看看我们最新发布的这项研究。这是一项全新的基准测试，目前没有任何模型针对该测试集进行过训练，因此测试结果非常客观，当然我们也必须随着大模型的迭代不断更新我们的测试基准。

在这个测试中，我们做了一件非常简单的事。我们让最新的大模型去查找同一个代码漏洞，连续运行五次。结果表明，在五次测试中，大模型只有 50% 的概率能成功找出该漏洞。如果你仅仅依赖大模型本身而没有任何其他的辅助校验机制，你根本无法保障企业级系统的安全运行。在面对最新大模型时，它也只能找出大约 75% 的安全问题，而在以前，依靠那些传统、确定性（Deterministic）的静态规则检测，我们能够做到百分之百的捕获。大模型的 F1 分数只有 40% 左右。

这意味着很多安全漏洞被彻底漏掉了。而且我们这里测试的，还包括那些尚未向公众开放的最新的未公开大模型。这说明了什么？这并不意味着大模型没用，而是意味着你必须把它们用在它们真正擅长的地方，并将它们与传统的确定性检测手段有机结合，小心翼翼地去探索那些确定性规则无法覆盖的边界，而不是盲目相信概率性的 AI 系统能帮你解决所有的安全问题。

总结一下我们一直在做的工作。我们并没有掌握所有的答案，稍后我会分享我们接下来的探索方向。但针对目前在大企业中广泛存在的自动化攻击，我们已经有了一套切实可行的方案，来阻止新的安全隐患流入到 AI 代理的自动化开发循环中。那就是将安全的上下文实时注入到开发流程中，这正是我们推出的 **Snyk Studio**。

现在大家都非常担心下载的第三方依赖包是否安全。通过 Snyk 的库，我们清楚地知道每一个开源包的健康状况、已知漏洞信息，甚至能识别它是否被注入了恶意软件。因此，我们能够直接阻止 AI 代理去选择那些有安全隐患的开源包，或者阻止它们写出带有 SQL 注入等硬伤的代码。这种预防机制能极大地遏制漏洞漏洞积压量的疯狂增长。

那么，对于企业系统里现有的那座巨大的“历史遗留漏洞山”，我们该怎么办？Snyk 成功帮助像 Labelbox 这样的企业，将其积压的安全漏洞一次性清理干净，实现了“零漏洞积压”。这在以前的安全管理中是极其困难的，因为修复漏洞往往会直接导致应用崩溃。因此，你必须引入“代码可修复性/破坏性评估 (Breakability)”的概念。基于 Snyk 的海量数据，我们能准确告诉开发者某次升级是否安全。就在上周，有一家超级大厂（Max Seven Company）利用我们的自动化修复代理，一举自动修复了 16,000 个严重级别的安全漏洞。

昨天，我们正式发布（GA）了我们的**自主代理开发安全 (Agentic Dev Security)** 产品。它致力于监控运行环境、输出代码、技能插件、MCP 服务器，以及像 Cursor、Claude Code、Codex 等各种代码生成代理的实际行为。

当你构建那些缺乏监管的 AI 应用时，你的安全治理绝对不能仅仅停留在 Confluence 页面文档或 PDF 规范里。你必须能够在极速迭代、极其复杂的代码库中，实时看清发生的一切，评估风险，并将安全策略强制注入到代理和开发者所处的开发循环中。

眼见为实，接下来我非常高兴邀请 Ezra 上台，为大家带来一段现场演示。他将向大家展示我们是如何实现这些能力的。

<details>
<summary>Original English</summary>

**Manoj Nair**: So again going back to the original point right if none of that convinces you like the generator validator separation this is fresh new research from just I think yesterday's when we went public with this. It's a benchmark that no no model has been trained so we can trust it for now and we'll have to keep updating the benchmarks. But this is you know just a very simple thing. You're we're asking the latest models and we have access to everything as you can imagine. We're asking them to find you know the same vulnerability run it five times and only 50% of those ones are found across those five tests. That's not how you can run an enterprise system if you just use the LLM without any anything else. This is the latest models. Only 75% of the issues were found versus a good old boring deterministic check. And you know 40% was the F1 score. So this whole like what did you actually miss? And we're talking about the latest models that are not even publicly available to people right? So what does this mean? It doesn't mean that they're not good. It just means they need to be you really need to use them for what they're really good at together and carefully to find the surface that your deterministic check cannot use not just think about probabilistic systems will solve everything. And so, you know, to net it out, what we've been working on, we don't have all the answers. And I'll share where we're going to. And but what we have answers for right now on the automated attacks that are working in some of these very large environments, just you know, how do I prevent new issues from coming into the agentic loop? To put put security context right there, that's studio. You can go check it out on our website. And we're you know, everyone's worried about packages that they download. Like how we have we know what the health of the packages are. We know the vulnerability information. We know it's malware. So, we're able to prevent the the agent from, you know, picking a package like that or writing code that, you know, inherently is a sequel injection. But great, so prevention will prevent that hockey stick, which we all want to prevent. Well, what happens with, you know, um the fact that, you know, you have this this mountain of vulnerability. We've been able to take organizations like Labelbox to zero once, zero backlog. Which is very hard in security due to because it breaks applications. So, you need to know concepts like breakability. And that data is super important that we're able to get from our base to know this is a safe upgrade. And so, that, you know, just last week a max yellow company remediated 16,000 critical issues using this remediation agent. Again, something you can go try out. So, you know, this is how, you know, I talked about, you know, kind of from the untrusted agentic development. We just GA'd our agentic dev security offering yesterday. It's looking at the environment, the output, the skills, the MCP servers, and the behavior of coding agents like Cursor Cloud, um Codex, and others. And when you're building ungoverned AI apps, that AI governance cannot live in a confluence page or PDF. So, how do you real-time look at everything that is happening in a very fast moving complex code repositories and understand risk and have policies enforced in the loops that the agents and the devs are. So, seeing is believing. I would love to bring Ezra up here to do a quick demo. Um and uh you know, Ezra's going to show you a couple things and you can come by to our booth and uh share a few more later.

</details>

---

### 现场 CLI 演示：包健康检查与插件风险评估

**Ezra**: 谢谢 Manoj。让我们把屏幕切换到 CLI 控制台。接下来我将进行几个快速的演示。虽然时间有限，无法把 Manoj 刚才提到的所有功能都演示一遍，但我们非常欢迎大家在演讲结束后去我们的展台进行深度交流。

首先，我将要求 Claude 自动生成一个命令行工具，该工具可以根据提示词生成二维码图像。

请帮我启动 Claude。谢谢。现场演示总会有些小状况，让我们再试一次。好的，第二次尝试。我们现在正试图让 Claude 生成一个 CLI 工具来创建二维码图像。我要求它使用一个开源的依赖包。如果你们注意到我输入的第四行指令，我写得非常详细。我明确要求它使用 Snyk 的包健康检查工具（Snyk Package Health Check Tool）。我们待会儿在演示中就能看到效果。但在实际的开发实践中，我们非常鼓励大家通过配置 Skill 插件或 Webhook，让这一步成为开发工作流中无需人工干预的、确定性的自动化步骤。

所以，它要做的第一件事，就是去扫描和分析当前的项目结构，并找出有哪些可用的开源依赖包可以帮助完成这个任务。

让我们看看能不能把控制台界面放大一点。我不知道会场的 Wi-Fi 会不会掉链子。我们做好了切换到录播演示视频的准备，但我是真的希望今天能给大家做现场实操。这样好点了吗？再大一点？好的，太棒了。

我们可以看到，它现在正在针对两个不同的开源依赖包调用我们的包健康检查工具：一个是 `qr-code` 包，另一个是 `qr-image` 包。这两个包都是能实现二维码生成功能的候选依赖。

检测结果出来了。看起来今天会场的网络确实不太给力，所以为了节省时间，我还是快速切换到录制的演示视频吧。非常抱歉，会后欢迎来展台找我们，我们可以找个网络好的地方给你们重新做现场实操。

好了，视频里是完全相同的提示词。我稍微快进一下，免得大家听我在这儿啰嗦。

最终我们可以看到，系统返回了这两个包的安全健康检测报告。这两个包在安全层面上都是完全健康的，目前都没有被发现任何可被利用的活动性 **CVE 漏洞**。

但是，第一个包 `qr-code` 是非常健康的，这意味着它当前正处于非常活跃的维护状态，每天有大量的下载和活跃用户。而第二个包 `qr-image`，虽然目前也没有已知 CVE，但它已经处于完全无人维护的状态了，它的第一个版本甚至是在 10 年前发布的。

如果我此时直接把软件部署出去，今天用这两个包可能都不会出问题。但如果未来这两个包被发现了新的安全漏洞，显而易见，如果你使用的是活跃维护的 `qr-code` 包，社区大概率会在一两天内迅速发布修复补丁，而你也可以立刻进行平滑升级。

接下来我想要展示的第二个演示，是关于评估大模型正在使用的技能插件或 MCP 服务器的安全风险。

有人之前和我分享了一个插件，叫做“竞争对手分析技能插件 (Competitive Analysis Skill)”。我针对这个插件运行了我们的安全风险评估。结果返回了四个安全发现，其中一些问题非常严重。

我们可以直接在这个插件的源码中看到，它居然要求我直接将用户的 **Authorization Header (授权凭证请求头)** 进行回显。这在安全规范里是一个绝对禁止的红线操作，我们绝对不希望任何插件在后台做这种事情。

我们还发现，在某些情况下，该插件会从 Reddit 和 Twitter 实时抓取数据。虽然这对于“竞品分析”这个任务来说听起来挺合情合理的，但你必须在开发时保持高度的警惕，确保你清晰地知晓它在后台抓取了什么信息，以及你使用这些信息的方式是否合规。

但最严重的安全隐患在于下面这一行：这个技能插件居然试图从互联网上的一个动态 YAML 配置文件中，去拉取具体的监控目标和分类过滤规则。这意味着，这个插件的具体执行逻辑，完全是由第三方网站动态提供的。一旦那个第三方网站被黑客攻破并篡改了 YAML 文件，即使你本地的插件代码没有发生任何修改，黑客也能直接远程控制并劫持你的本地代理系统。

值得一提的是，我们一直在不断优化我们的评估逻辑，提高警惕性，以降低误报率，并作为我们 Evo 产品线的一部分，为企业提供强大的安全策略配置能力。在未来，我们的开源工具也同样会集成这些能力。我们非常鼓励大家去 sneak.io 看看，或者直接来展台找我们交流。如果你们愿意，我可以在走廊里给你们做现场实操。不过考虑到时间关系，我们的演示就先到这里。

<details>
<summary>Original English</summary>

**Ezra**: Thanks, Manoj. Let's flip over to the CLI here. I'm going to do a few rapid-fire demos. Don't have time to do everything Manoj just talked about here, but we'd love for you to come and and talk to us. Stop by Stop by the booth. Find us after this talk here. Uh the first thing that I'm going to do here is I'm going to ask Claude to generate a tool a CLI tool that can create a QR code image from uh from a prompt. Start Codex or Claude. Uh there we go. Please start Claude. Thank you. Live demos. Let's try that one more time. All right. Uh try number two here. We are uh going to try to get Claude to generate a CLI tool um to ultimately create that that QR code image. I'm asking it to use an open source dependency and if you notice this fourth uh fourth line that I have here um I'm being pretty verbose. I'm telling it to use the Snyk package health check tool. Um and so we're going to be able to see that here in the demo, but if you use this in practice, we really encourage you to leverage a uh a skill or a hook to make this just a deterministic automated part of your workflow. So, the first thing that it's going to do is going to see, you know, ultimately what what does the project look like and what are some dependencies some open source packages that I might be able to use. And let's see if we can expand this. I don't know if conference Wi-Fi is going to play nice with us. Now, we can switch to a recorded demo here, but was really hoping to to do this live. Is that a little better? That even more? All right. Great. Uh so, we can see now that it is calling this uh package health tool uh for two different open source dependencies. It's looking at a QR code package and a QR image package. Both viable packages that can help accomplish this task. Uh results are returning. Now, it looks like conference Wi-Fi is really really not playing in our favor here. Uh so, I'm going to quickly jump over to recorded demo. Apologies. Come find us after. We can go to hopefully a space where there's not as much of this happening. Uh if we can get this live here. There we are. So, same prompt. Maybe I can fast forward a bit so you don't need to hear me me banter on this a little bit. Uh but, ultimately uh we see here that the two images Excuse me, the two the two the two packages returned. Both are actually uh vulnerability free. There's no active CVEs that could be exploited in these versions. Uh but, the first one, QR code, is healthy, meaning it's actively being maintained. Um and there's a ton of a ton of active usage downloads of this. Whereas, QR image, no CVEs today, but it's not actively being maintained. It was really released 10 years ago for the first time. And so, if I were to deploy software with this right now, I may not get exploited today if I use either package, but if there was a new vulnerability identified in the future, um there's a much higher likelihood that if I'm using this QR code package here, that a patch would be released sooner, within a day or two, and I would be able to continue uh building on this right now. Uh the second demo that I wanted to show here was exploring that uh assessment of risk from skills uh or MCP servers that a my agent might be using here. And so, somebody shared with me a skill uh called Do we have it here? Um a competitive analysis skill. Um and I ran the skill assessment against Excuse me, the risk assessment against the skill here, and we saw there were four findings returned. And some of these are fairly problematic. We can see in the actual skill itself, it's asking me to echo the authorization header, which is a big no-no. That's That's not something that we want a skill ultimately to be doing. We also see that in some cases, it's going to be pulling from live content from Reddit, from Twitter. That may be totally fine, but you really want to go into that eyes wide open and making make sure that you know that it's pulling in this information, the way you're using the skill is going to be appropriate. For competitive analysis, that's probably probably reasonable. Um but what's especially problematic, if we see in this line here, is that it's actually looking to pull from a YAML file that's hosted on the internet, instructions on how to monitor these targets and some of the classification rules. So, it's really giving it the logic to actually execute the skill from a third-party website. And if that gets changed, even if my skill file doesn't change at all, that is a a chance for an exploit to occur. It's worth noting that we've been refining the logic associated with the findings that we return here, addressing the signal-to-noise ratio and kind of giving some policy configuration capabilities as part of our Evo product. And we're going to see the gap kind of get closed here with this open-source tool as well in the future. We encourage you to check these out. Go to sneak.io, come talk to us in the booth. Find Find me in the hallway. We can actually do this live instead of looking at a recording if you want. But I think given the time, we probably should wrap the demo.

</details>

---

### 总结与展望：赋能 10x 安全工程师

**Manoj Nair**: 太棒了。现场演示总是充满挑战，墨菲定律无处不在，但好在你准备了 B 计划，这非常棒。

所以，大家可以看到，这仅仅是个开始。是的，我们已经针对这些特定类型的安全挑战开发了一些非常有趣且实用的安全代理工具。但在最终，这必须是一个整体的系统。正如我们刚才所讨论的，这需要像今天这样座无虚席的专题论坛，需要我们和整个客户群体一起去共同构建，我们也希望能和整个安全行业携手前行。

刚才我们提到了 **Evo**。什么是 Evo？Evo 是我们在去年年底推向市场的一个安全概念，在此基础上，我们正在不断迭代和构建各种不同的安全代理。

我们从其他的工业系统中汲取了灵感。比如，当我们在训练五代战机的飞行员时，我们是如何训练他们的？这里有一个核心概念，叫做 **OODA 循环 (OODA Loop)**，即：观察 (Observe)、调整 (Orient)、决策 (Decide) 和行动 (Act)。飞行员通过在这个循环中不断地学习和复盘，最终成为顶尖的超级飞行员。

我们希望为今天在座的每一位、以及更多的安全团队赋能。昨天我们举办了一场研讨会，培训了数百名 AI 安全工程师。我们希望为这些 AI 安全工程师提供强大的系统支持和工具。诚然，在这个领域依旧有许多尚未解决的难题，比如多代理系统之间的协同工作、多代理的运行框架、共享内存等，我们正在全力攻克这些难题。这也是我们构建 Evo 的方式——与社区并肩作战，让它成为一个开放的愿景。这能真正为 AI 安全工程师赋予超能力。

在以前的时代，AI 工程师通过使用各种生产力工具变成了 10x 工程师。而我们今天的目标，就是要把这种 10x 的超能力交到 AI 安全工程师的手中，让我们一起携手构建真正安全、可信的系统。

让我们共同为此努力。今天晚上我们在旧金山的办公室举办了一场社区交流会（Community Jam），欢迎大家今晚有空的话来坐坐，我们可以继续今晚的讨论。谢谢大家，让我们继续构建！

<details>
<summary>Original English</summary>

**Manoj Nair**: Cool. Live demos are always fun, but Murphy's striking always, but you had a plan B, so that's awesome. So, look, just to wrap it up, right? This is just the beginning. Yes, we have built some very interesting agents for some specific sets of those problems. In the end, it's a you know, a system that we talked about that really like it's rooms like this that we're building with in our customer base and and we would love to partner with the rest of the industry while we're doing this track. And we learned, you know, this as I mentioned Evo, what is Evo? Evo is the system that we we brought to the world late last year in terms of a concept and we've constantly built these different agents. We learned from other systems, you know, you have fighter pilots with 5G fighters and how are they trained? It is this notion of you need to really observe, orient, decide and act and that's how you go and in the constant learning from that kind of loop is how you become, you know, a super pilot. And so we want to enable this room and other rooms. We had a workshop yesterday training hundreds of AI security engineers. We want to enable AI security engineers to be able to have their own powerful system and tools and yes, there are problems that are not solved yet fully in terms of coordinating multiple agents with systems like this. Yes, we all know how, you know, the harnesses and and and shared memory and and we're working these problems. This is how we're building Evo. We're building it with the community and we want this to be an open vision. That's really empowering AI security engineers. You know, from from these rooms the AI engineers became 10x engineers. Our goal here is to have that 10x superpower in the hands of AI security engineers so we can build trusted systems together. So let's continue to do that and you know, come by, talk to us or if you guys are, you know, have have I think there was like 50 plus events around AI engineer but we're keeping having this rooftop fan zone. We're going to do some some more things together with the community. So this is down the road in our office here in SF. Uh community jam. Come join us uh if you if you have time this evening. We'll continue the conversation. Thank you all. Let's continue building.

</details>