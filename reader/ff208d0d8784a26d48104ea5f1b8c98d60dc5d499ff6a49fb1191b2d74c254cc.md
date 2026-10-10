---
author: AI Engineer
date: '2026-08-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CoEIs6Xm8m8
speaker: AI Engineer
tags:
  - open-source
  - open-weights
  - inference-cost
  - ai-adoption
  - supply-chain-security
title: 开源已死，开源万岁：开放权重模型的经济学逻辑
summary: Cline创始人Saoud Rizwan指出，AI已从根本上改变软件开发，开源社区因AI生成的垃圾PR、恶意供应链攻击而凋零。但他认为开放权重模型将因经济效率胜出——推理成本正急剧下降，企业将转向GLM、DeepSeek等更便宜的模型。他呼吁美国实验室认真对待开放权重，否则将失去对技术发展的控制权。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Saoud Rizwan
  - Brian Armstrong
companies_orgs:
  - Cline
  - Anthropic
  - OpenAI
  - Coinbase
  - Facebook
products_models:
  - GLM
  - DeepSeek
  - Claude
  - GPT
  - Open Compute Project
media_books: []
status: evergreen
---
### 开源社区的凋零：AI时代的信任危机

我是Saoud，Cline的创始人。几年前，我将Cline作为一个开源项目启动。有些人可能知道，它是最早的编程代理（coding agent）——在Claude订阅和Codex订阅出现之前，人们必须为每一次API请求付费，费用极其高昂。那时还没有提示缓存（prompt caching），有些用户一天就要支付数百美元。但对许多人来说，这是他们的第一个"AGI时刻"——第一次看到大语言模型（LLM）能够端到端地完成他们的工作，他们就此上瘾。我认为，如果Cline不是开源的，它不会取得今天的成功。因为开源让开发者能够检查我们的代码、信任它，并连接任何API，让他们在花费大量资金时感到安心，知道自己没有被坑。

我们是第一个添加自定义规则（custom rules）和计划模式（plan mode）等功能的项目，其中很多想法来自我们项目周围那个令人难以置信的开源社区。然而，将我生命的大部分时间投入到开源建设中，看到整个开源社区在过去两年里因AI从根本上改变了软件开发的方方面面而枯萎、消亡，真的令人心碎。GitHub实际上已经变成了一个充斥着SLOP PR（低质量AI生成的拉取请求）、问题和安全报告的档案馆。曾经的社区感已转变为对彼此是否负责任地使用这些工具的深度怀疑和不信任。因为AI编码对项目可能极其危险，每个人都不得不边做边学，尤其是那些依赖信任第三方的开源项目。

<details>
<summary>Original English</summary>

Hi, I am SA, founder of Cline. I started Cline as an open source project a few years ago. Some of you might know it as the first ever coding agent, back before the Claude subscription and the Codex subscriptions, when people had to pay for each and every API request, which got extremely expensive. This was before prompt caching became a thing, and so there were people that paid hundreds of dollars a day using Cline. But for a lot of people, it was their first AGI moment. It was the first time they saw LLMs be able to do their jobs end to end, and they got hooked. I don't think Cline would have been as successful as it is if it wasn't open source, because it allowed these developers to inspect our code and trust it, and connect to any API, so they could be comfortable with spending so much money on it, and know that they weren't getting screwed over.

We were the first to add things like custom rules and plan mode. A lot of that came from talking to and learning from this really incredible open source community we had around the project. Having spent most of my life building open source, it's really heartbreaking to see the broader open source community wither and die over the last two years, because of how AI has fundamentally changed everything about software development. GitHub is effectively an archive of SLOP PRs and issues and security reports, where the sense of community before has turned into this deep skepticism and distrust of each other's responsible use of these tools. Because AI coding can be extremely dangerous to a project, and everyone's kind of had to learn that on the fly, but especially open source projects that rely on trusting third parties.

</details>

### 防御性反应：从全面封禁到关闭PR

开源项目正在以各种方式应对AI的冲击。**Zig**（驱动Bun的语言）的行为准则本质上禁止了所有AI的使用——你不能在拉取请求、问题甚至评论中使用它。原因是，对Zig核心团队来说，他们重视贡献者胜过贡献本身。因此，审查PR的主要目标不是添加新代码，而是帮助培养新的、能随时间获得信任的贡献者，而AI辅助完全破坏了这一点。**curl**的CEO发帖称，他的项目实际上正被AI生成的错误报告"杀死"，他们甚至考虑几十年来首次关闭漏洞赏金计划。**tldraw**则自动关闭所有拉取请求，无论是否为AI生成。情况已经糟糕到GitHub添加了一项功能，可以完全禁用第三方拉取请求——这真的很可悲，因为拉取请求正是成就GitHub今天地位的东西。我们可能会看到许多大型开源项目选择启用这一功能。

所以当我说开源已死时，我指的是它的一部分，比如社区——它不再值得培养了，尤其是因为构建软件变得如此便宜。此外还有供应链攻击的风险。你们肯定看过各种软件被攻破的报道。依赖第三方软件变得比以往任何时候都更危险——一次单一的攻破，就能让一长串贡献者全部沦陷。举个例子，**LiteLLM**是一个Python包，每天有约350万次下载。它被攻破了三个小时，攻击者利用他们使用的GitHub应用窃取了PyPI发布令牌，发布了一个被攻破的版本，该版本会安装一个凭证收割器，窃取你的API密钥、SSH密钥、加密货币密钥，还会安装一个允许远程命令执行的后门。这件事之所以能这么快被发现，纯粹是运气——因为恶意软件有个bug，如果你运行LiteLLM MCP服务器，会导致Cursor崩溃。一位安全研究员注意到了这一点并查明了原因。但如果它再存在久一点，就会造成灾难性的破坏，尤其是因为许多LiteLLM用户是企业客户和拥有内部网关的开发者。

<details>
<summary>Original English</summary>

So this is the code of conduct for Zig, which is the language that powers Bun. They essentially ban all use of AI. You can't use it on pull requests or issues or even comments. The reason for this is that to them, the core Zig team, they value contributors more than they do the contributions. The primary goal for reviewing PRs and things isn't to add new code, but it's to help grow new contributors who can become trusted over time. AI assistance completely breaks that.

This is a post from the CEO of curl, who says that his project is effectively being doxxed by AI generated bug reports, and they're even considering shutting down their bug bounty program for the first time in decades. This is tldraw. They're automatically just closing all pull requests, whether they're AI generated or not. It's gone so bad that GitHub added a feature to disable third-party pull requests altogether, which is really sad because pull requests were the thing that made GitHub what it is today. We're probably going to see a lot of big open source projects opt into this.

When I say that open source is dead, I mean some parts of it, like the community, it's just not worth cultivating anymore, especially because building software is so cheap. Also the risk of supply chain attacks. It's become more dangerous than ever to depend on third-party software, where it takes a single compromise and a massive chain of contributors to get pawned. Just as an example, LiteLLM is a Python package. It gets like three and a half million downloads a day. They were compromised for three hours, where attackers used a GitHub app that they used to steal their PyPI publishing tokens and publish a compromised version of the package that would install a credential harvester that would steal your API keys, your SSH keys, your crypto keys, and also install a backdoor that lets them do remote command execution. The only reason this was even caught as quickly as it was was just pure luck, because the malware had a bug in it where it would cause Cursor to crash if you ran the LiteLLM MCP server. A security researcher noticed that and was able to figure it out. But if this had been out any longer, it would have caused catastrophic damage, especially because a lot of the people using LiteLLM are enterprise customers and developers that have their own internal gateways.

</details>

### 推理支出的疯狂：补贴、锁定与价格欺诈

尽管有这些负面现象，我相信开源的一些部分会留存下来并变得更加重要——比如允许他人在公共领域自由使用你的东西并在此基础上构建。这些方面将比以往任何时候都更重要，尤其是开放权重（open weights）模型，因为其经济影响巨大。为了解释原因，我想看看当前推理支出（inference spend）的情况。有一份来自某匿名公司CFO的报告称，他们在一个月内意外在Claude上花费了5亿美元，因为他们没有在Anthropic仪表板上为数千名员工设置使用限制。另一份来自Uber CTO的报告称，在他们向组织推广Claude后，95%的工程师在使用它，70%的提交代码来自Claude，每用户月支出高达2000美元，他们在短短四个月内就用完了整个2026年的预算。

疯狂的是，AI实验室自己也在亏损。Semi Analysis的图表显示，他们对Claude Code和Codex订阅进行了实验，给它们长期限的编码任务直到用完每周限额。他们发现，200美元的Claude套餐能提供约8000美元的API使用量，而200美元的Codex订阅能提供约14000美元的API使用量。策略很明显：他们本质上是在补贴这些服务，直到尽可能多的工程师依赖他们的工具——CI中的代理、后台云代理、循环代理等等。感觉这些实验室的每一个新功能和营销推动，都是一种新的工作流，让你标准化使用、消耗更多令牌、被更深地锁定。然后，一旦你被困住，你的开发者没有这些工具就无法工作，价格欺诈就不可避免了。这不是理论——我们正在与我们交谈的一些客户身上实时看到这种情况。举个快速调查：你们中有多少人基本上在Claude中断或GPT中断时就停止工作了？是的，我也是。

我认为这就是为什么我们看到Anthropic和OpenAI从API业务转向大力投资应用层——因为他们知道那是他们可以设置这类陷阱的地方，为模型不可避免地成为商品的那一天建立护城河。

<details>
<summary>Original English</summary>

Despite all of this, I believe there are some parts of open source that are sticking around and becoming more important, like allowing others to use your thing freely in the public domain and build on top of it. Those parts are going to become more important than ever, particularly with open weights models because of the economic impact. To help explain why, I want to look at what's happening with inference spend right now.

This is a report from an anonymous CFO at an unnamed company where they accidentally spent $500 million on Claude in a single month because they didn't set the usage limits on their thousands of employees on their Anthropic dashboard. This is another report by Uber CTO, where after they rolled Claude out to their organization, 95% of their engineers were using it, 70% of their committed code came from Claude, and their monthly spend per user was up to $2,000. They said they used their entire 2026 budget in just four months.

The crazy part is that the AI labs are losing money too. This is a chart from Semi Analysis where they ran experiments with Claude Code and Codex subscriptions, giving them long-horizon coding tasks until they exhausted their weekly limits. They found that a $200 plan for Claude would give them about $8,000 worth of API usage, and a $200 subscription to Codex would give them about $14,000 worth of API usage. The strategy is pretty obvious. They're essentially going to subsidize this until they have as many engineers dependent on their tooling as possible, with agents in their CI and background cloud agents and looping agents. Every new feature and marketing push from these labs seems to be a new workflow to standardize on, to use even more tokens and to be locked in even more. Then inevitably the price gouging, once they've got you trapped where your developers can't work without the tools. This isn't theoretical. We're seeing this happen live with some of the customers that we talk to.

Quick show of hands: how many of you basically stop working whenever there's a Claude outage or a GPT outage? Yeah, same. I think that's a reason why we've seen Anthropic and OpenAI go from being API businesses to investing so much into the application layer, because they know that's where they can set these sorts of traps and build their moat for the day that these models inevitably become a commodity.

</details>

### 开放权重模型的崛起：智能不再是唯一标准

但我实际上不认为这个策略会奏效——这就是我今天想传达的信息：这感觉非常短视。我们在世界上注意到的是，无论你的CLI代理有多少功能，开发者和企业都会转向任何能给他们带来最大性价比的东西。看看当前的开放权重模型，其中许多是在中国构建的，我们会注意到，尽管它们落后于美国的闭源竞争对手，但我们正处于一个拐点：原始智能领先不再那么重要了。因为这些模型已经足够强大，你不需要在所有工作中都使用最好的那个。成本对这些企业来说正变得极其重要，而它们直到现在都在视而不见。

我们都能感觉到，要从这些模型中获得最佳输出，更多的问题在于你给代理访问什么上下文和工具，而不是它的原始智能。有了正确的AI原生开发基础设施——项目技能、规则、验证系统和质量门——即使是一个平庸的模型也能产生与更智能模型相似的结果，只是可能需要更多令牌。智能更好地分布在系统和对模型的护栏中，这样你就不必那么依赖模型本身，或依赖终端开发者对模型的责任使用。

我们最近分享了一个轶事经验：我们怀疑GLM优于Opus的基准测试，于是在Cline仓库的一个真实bug上测试了它们。虽然两个模型都修复了问题，但GLM在成本和代码质量方面胜出。GLM使用了双倍的令牌，但成本只有一半。Opus完成得更快，工具调用次数只有一半。但GLM清理了死代码，并在完成前验证了构建编译通过，而Opus没有——它留下了一堆类型错误，还破坏了生产构建。这让我们感觉到GLM被训练为花费更多令牌来验证其输出，这没问题，因为令牌本来就便宜，真正重要的是最终结果。

由于这些开放权重模型能以稍多一点的令牌提供相同的输出，我们看到行业采用并标准化这些模型的迹象。**Coinbase** CEO Brian Armstrong表示，他们已在内部LLM网关中默认使用GLM和Kimmy，这使他们的AI支出减少了近一半，而令牌使用量持续增长。我认为我们会看到其他企业构建自己的内部工具并进行路由，以最经济高效的方式使用这些代理，即使这意味着无法使用Claude Code等产品中的最新功能。

<details>
<summary>Original English</summary>

But I don't actually think the strategy is going to work. That's the message I wanted to get across today — that this feels very shortsighted. What we're noticing happen in the world is that it doesn't matter how many features your CLI agent has, developers and businesses will just jump to whatever offers them the best value for their dollars.

If we look at current open weights models, many of which are built in China, we'll notice that although they've lagged behind the American closed source competitors, we're at an inflection point where raw intelligence lead doesn't matter as much anymore. Because these models are powerful enough where you don't always need the best one for all your work. Cost is becoming extremely important to these businesses that have kind of turned a blind eye until now.

I think we all kind of feel it that to get the best output from these models, it's more a problem of what context and tools you give the agent access to, and less about its raw intelligence. With the right AI native development infrastructure, with project skills and rules, systems of verification and quality gates, even a mediocre model can produce similar results as a more intelligent model — it just might take more tokens. The intelligence is better placed in the system and guardrails around the model, so that you don't have to be as reliant on the model or your end developer's responsible use of the model itself.

We recently shared an anecdotal experience where we were skeptical of the benchmark saying that GLM was better than Opus. So we tested them on a real bug from the Cline repo. While both models fixed the issue, GLM was the winner in terms of cost and code quality. GLM used twice as many tokens but only cost half as much. Opus finished faster, used half as many tool calls. But GLM cleaned up dead code and verified that the build compiled before completing, while Opus didn't. It left a bunch of type errors and it broke the production build. That gave us the sense that GLM was trained to spend more tokens verifying its output, which is fine because the tokens are cheaper anyways, and it's really the end result that matters.

Because these open weights models can deliver the same output with a little bit more tokens, we're seeing signs of the industry adopting and standardizing on these models. This is Brian Armstrong, the CEO of Coinbase, saying that they've defaulted to using GLM and Kimmy in their internal LLM gateway, and that this has cut their AI spend by nearly half while their token usage continues to grow. I think we'll see other businesses building their own internal tooling and routing to work with these agents in the most dollar efficient way for them, even if it means not having access to the latest new feature in something like Claude Code.

</details>

### 开放计算的历史启示：标准化驱动成本革命

我们正在看到15年前开放计算（Open Compute）发生过的同样事情。给那些没听说过的人快速讲个历史课：2011年，Facebook刚开始构建分布式计算基础设施和数据中心，但等他们建成时，亚马逊和谷歌已经抢先一步，所以这不再是竞争优势。马克说："好吧，我们把它开源，看看会发生什么。"于是他们把自己投入大量精力和金钱设计的数据中心、服务器、网络、冷却机架等所有物理硬件设计都免费送了出去——发布了原理图和CAD文件，称之为开放计算项目。他们看到的是整个供应链围绕它重新组织。

在开放计算之前，每家公司都设计自己的专有服务器，制造商进行小批量、高度定制化的生产，价格昂贵。但当Facebook的设计成为共享的开放标准后，突然间每个人都订购同样的东西，制造商可以进行大规模标准化生产，使这些组件商品化。没有单一供应商能收取溢价，整个行业的价格都下降了，包括Facebook自己。Facebook发现，通过免费赠送这些设计，他们创造了推动自身成本下降的市场，并在未来节省了数十亿美元。这里的教训是：行业会采用并标准化他们可以在其基础上构建的东西，即使它不是最好的。

考虑到我们已经为未来5年的AI基础设施建设锁定了多少资本支出，开放权重模型只会变得更便宜。有估计称，到2030年我们将花费近3万亿美元，创造超过100吉瓦的新数据中心容量，大约是当前全球容量的两倍。像Baseten和Fireworks这样的托管提供商，他们的全部目的就是击败竞争对手。他们会利用基础设施效率提升——专用硬件、缓存、批量处理技巧、推理专用芯片——来进一步降低成本。到2030年，估计在1万亿参数的LLM上进行推理的成本将比今天低90%。

我们看到10年前使云商品化的同类成本削减技巧正在推理领域发生。2014年，谷歌在GCP Live三月发布会上宣布将计算降价32%、存储降价68%。AWS在几天内以类似的降价反击——那是AWS当时的第42次降价。从2015年起，一旦原始计算和存储成为商品，超大规模云服务商就不再主要在这些方面竞争，而是转向数据库和无服务器等其他领域。我认为，因为开放权重允许这些托管提供商如此激进地竞争和优化成本，我们将看到这些外国开放权重模型被大规模采用——因为当涉及金钱时，市场是极其高效的，这些闭源实验室收取的荒谬API费用对大多数知识工作来说将不再值得。

<details>
<summary>Original English</summary>

We're seeing the same thing that happened with Open Compute 15 years ago. Quick history lesson for those that haven't heard of this. In 2011, Facebook was just getting started on building out distributed computing infrastructure and data centers. But by the time they built it, Amazon and Google already beat them to the punch, so it wasn't a competitive advantage. So Mark said, "All right, let's just open source it and see what happens." They took the designs for their data centers, their servers, their networking and cooling racks, all the physical hardware they spent all this energy and money building, and they just gave it away. They published schematics and CAD files and everything, and called it the Open Compute Project. What they saw was that the entire supply chain reorganized around it.

Before Open Compute, every company designed its own proprietary servers. Manufacturers were doing small production runs of very custom hardware, which was expensive. But when Facebook's designs became this shared open standard, suddenly everyone was ordering the same thing, and manufacturers could do massive standardized production runs, commoditizing these components. No single vendor could charge a premium, and the price of everything came down for the whole industry, including Facebook itself. What Facebook found was that by giving these designs away, they created the market that drove their own costs down and saved them billions of dollars down the road. The lesson here is that the industry will adopt and standardize on something that they can build on top of, even if it isn't the best thing.

With how much capex we've locked in for the next 5 years for AI infrastructure buildout, open weights models are only going to get cheaper. There's estimates that we'll spend nearly three trillion dollars and create over 100 gigawatts of new data center capacity by 2030, roughly doubling global capacity today. Hosting providers like Baseten and Fireworks, their whole purpose is to beat each other, to beat the competition. They'll use infrastructure efficiency gains like dedicated hardware, caching, batching volume tricks, and inference specialized silicon to drive cost down even more. By 2030, the estimates are that inference on a 1 trillion parameter LLM will cost 90% less than it does today.

We're seeing the same sort of cost cutting tricks that commoditized the cloud 10 years ago happening in inference. In 2014, Google at their GCP Live March announcement said they would cut compute by 32% and storage by 68%. AWS fired back with similar cuts within days — this was AWS's 42nd price cut at that point. From 2015 onwards, once raw compute and storage were a commodity, the hyperscalers stopped competing on it as much and started competing on other things like databases and serverless. Because open weights allows these host providers to compete and cost optimize so aggressively, we'll see mass adoption of these foreign open weights models. When dollars are involved, the markets are extremely efficient, and the absurd API costs that these closed labs charge just won't be worth it anymore for most knowledge work.

</details>

### 战略呼吁：开放权重是保持领先的唯一路径

所以，这是我谦卑地请求美国实验室认真对待开放权重。因为在我们意识到之前，我们正在投资的所有这些基础设施可能都建立在席卷全球的外国模型之上，使GPT和Claude变得无关紧要。市场份额和采用率极其重要。如果外国模型成为标准，就没有理由再切换回GPT、Claude或Gemini，无论边际改进如何——然后我们就失去了对这项技术发展的控制。谁知道如果我们没有Anthropic和OpenAI这样的公司以其他实验室可能不会的方式大力投资安全研究，世界会走向何方。

我认为，一项如此具有变革性的技术的发展，与构建它的人民和国家的理想深深相连。要将这些价值观注入这项技术的未来，我们需要保持领先。我不是说我们要开源我们的研究——我认为那才是我们保持领先的原因。我们需要做的是开放我们的模型，开始发布更多开放权重模型。众所周知，开放权重模型远没有那么有用——你可以使用它们，提取训练轨迹，更容易地训练你的模仿模型，但无法实现跨越式发展。这将使模型以允许更多竞争、采用和为客户提供更好价格和价值的方式被行业使用。我认为这就是我们在这一关键时刻保持领先的方式。

我和Cline如此相信这个开放权重的未来，以至于本周早些时候我们推出了一个开放权重订阅计划。通过基于量的折扣和与推理托管提供商的合作，我们可以提供相比直接API成本显著折扣的价格。我们计划随着这些模型变得更便宜而继续增加使用配额。你可以通过那个链接 client.bot/pass 注册。如果你想感受GLM和DeepSeek这样的模型已经走了多远，以及你不再需要最昂贵的闭源前沿模型访问权限来完成工作，可以试试。Cline也是开源的，你可以自带API密钥使用任何其他提供商，可以在CLI、VS Code和JetBrains中使用。我们会持续在模型发布时添加最新模型。这是感受最新模型有多好的好方法，尤其是开放权重模型，因为你无法通过Claude或ChatGPT订阅访问它们。好了，这就是我的演讲。谢谢。

<details>
<summary>Original English</summary>

This is me humbly requesting the American labs to take open weights more seriously. Because before we know it, all this infrastructure that we're investing in could be built on foreign models that take the world by a storm and make GPT and Claude irrelevant. Mind share and adoption is incredibly important. There's a chance that if the foreign models become the standard, there won't be a reason to switch back to GPT or Claude or Gemini, no matter what the marginal improvements are. Then we lose control over the development of this technology. Who knows where the world is headed if we don't have the likes of Anthropic and OpenAI to invest so heavily into safety research in ways that perhaps these other labs wouldn't.

I think the development of a technology this transformative is deeply tied to the ideals of the people and the nation that's building it. To instill those values in the future of this technology, we need to keep the lead. I don't mean we need to open source our research — I think that's what gives us the lead. We need to open up our models and start releasing more open weights models, which as we know are not nearly as useful. You can use them and extract the traces and train your copycat models on them more easily, but not in a way that can leapfrog. This would make models more usable by the industry in a way that allows more competition and adoption and better price and value for customers. I think that's how we keep our lead during this very critical moment.

Me and Cline believe so much in this open weights future that we launched an open weights subscription plan earlier this week. Through volume-based discounts and partnerships with inference host providers, we can offer significant discounts compared to paying for these models at direct API cost. We plan on continuing to increase the usage quota for these models as they become cheaper. You can sign up at that link client.bot/pass. If you'd like to get a feel for how far models like GLM and DeepSeek have come, and how you don't need the most expensive closed frontier model access to get work done anymore. Cline is also open source, and you can bring an API key and use any other provider. You can use it on your CLI, VS Code, and JetBrains. We continue to add the newest models whenever they're released. It's a good way to get a feel of how much better the latest model is, especially with open weights, because you can't access those with Claude or ChatGPT subscriptions. Cool, that is my presentation. Thank you.

</details>