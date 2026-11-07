---
author: a16z
date: '2026-04-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dvVbA9OcBqs
speaker: a16z
tags:
  - enterprise-ai
  - ai-agent
  - legacy-integration
  - headless-software
  - complexity-paradox
title: 硅谷 vs 现实：大型企业 AI 落地为何步履维艰？——对话 Box CEO Aaron Levie
summary: Box CEO Aaron Levie 与 a16z 合伙人深入探讨了企业 AI 应用的‘理想与现实’。访谈分析了大型企业集成 AI 的真实痛点、从‘软件混合’向‘代理模式’（Agentic Model）的架构转向，以及 Salesforce ‘无头化’战略背后的信号。核心观点指出，AI 并非简单的集成工具，而是更像‘非确定性’的数字员工，且由于系统复杂度的指数级增长，AI 不仅不会消灭工程岗位，反而会创造更多需求。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Box
  - a16z
  - Salesforce
  - OpenAI
products_models:
  - ChatGPT
  - MCP
media_books:
  - The End of Work
status: evergreen
---
### 硅谷与现实的断层

**Steven Sinofsky**: 董事会去找 CEO 说：“我们需要更多的 **AI**。” CEO 说：“好吧，我会找个顾问来做。” 接着他们搞了一个没人知道怎么运作的中心化项目，操作层面完全没对齐，结果注定失败。最有趣的观念是，认为我们写的代码越多，需要的工程师就越少。事实恰恰相反，因为现在的系统比以前更复杂了，这意味着当你要进行系统升级、出现停机或安全事故时，你会面临更多的挑战。在这个领域，工作才刚刚开始。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: So the board goes to the CEO. What does the board say? We need more AI. And what does the CEO said? Oh, okay. I'll get like a consultant to do more AI. And then they have some centralized project that nobody knows how it works. They haven't aligned their operations and those things will fail. The funniest concept that the more code we write, the less we would need engineers. It' be the opposite because now your systems are even more complex than before, which means that you're going to be running into even more challenges of when you need to do a system upgrade or when there's downtime and you have to figure out like what how do I fix that problem or when there's a security incident. I mean, we're just getting started with the jobs on this front.

</details>

**Martin Casado**: 它们会在**集成（Integration）**上撞墙。AI 和 **智能体（Agents）** 无法解决、任何东西都无法解决的一点是：任何超过一千人或成立超过十年的企业，本质上都是一堆等着被集成的“破烂儿”。你不能简单地说它会自动集成，AI 实际上对集成没有任何帮助。

<details>
<summary>Original English</summary>

**Martin Casado**: They're going to hit a wall at integration and and this the thing that's not different about AI and that agents don't fix that nothing fix is that any enterprise of a thousand people or more or that's older than 10 years is just a mass of stuff that's sitting there waiting to be integrated and and you can't just say it's going to integrate. AI actually doesn't help to integrate anything.

</details>

**Steven Sinofsky**: 大家好，我们正在直播。今天我们三个人在这里讨论 AI：我、**Martin Casado**，还有今天头发特别垂直的 **Aaron Levie**。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: Hey, we are here monitoring the situation live and we're very excited to talk about a bunch of AI stuff and we have three of us are here today. Uh there's me, Stevenski and Martin Casado who will wave and say hi. I'm Martin and and Aaron Levy who is is working on the elevation of his hair today. So, we're excited about that.

</details>

**Aaron Levie**: 头发越来越高了，我试着驯服它，但没成功。

<details>
<summary>Original English</summary>

**Aaron Levie**: It just keeps getting more vertical. And I thought I could kind of tame it, but it didn't work.

</details>

**Steven Sinofsky**: 那是 Token 问题，还是参数量（Parameters）的问题？

<details>
<summary>Original English</summary>

**Steven Sinofsky**: And is that just a token issue or a parameter number of parameters issue?

</details>

**Aaron Levie**: 参数太多了。

<details>
<summary>Original English</summary>

**Aaron Levie**: It was too many parameters. Too many parameters.

</details>

**Steven Sinofsky**: 这一周非常忙，但我想把话题拉高一点，聊聊未来的走向。**Aaron**，你是最深入一线的 CEO，每天都在和企业客户交流。你这周跑了那么多客户，有什么最令你兴奋的发现？

<details>
<summary>Original English</summary>

**Steven Sinofsky**: Okay. I have the same thing but in reverse. Okay. So, you listen, you have a distilled model. There you go. My I run local. So, we had a lot of there's been a busy week of things, but we're we want to bubble it up a little bit and just start talking about where where things are are heading. Um, but I'll I'll let I just kick it to you, Erin, and you start where you are the most excited this moment because you have visited a ton of customers this week and have learned a lot. You share a lot on X, but I think you're the most in the trenches CEO who is really talking to customers every single day in the enterprise, which is what the three of us tend to look at the most.

</details>

**Aaron Levie**: 我觉得我最近的工作就是把现实带回硅谷，再把硅谷带进现实。目前这两者之间存在着巨大的鸿沟。这种差距是由**硅谷/工程角色**与世界其他地方截然不同的工作风格造成的。工程师的技术能力极高，时刻紧跟互联网动态，能熟练使用并调试自己的工具。而且 AI 模型在代码领域表现极好，工作结果可验证。但在工程领域能让智能体运作良好的五到十个因素，在普通的**知识型工作**中往往是不存在的。

我观察到大家都在尝试把代码智能体或“计算机操作”智能体的伟大之处装进企业，但企业的**工作流**完全不同：用户没那么懂技术，数据极其碎片化，系统非常陈旧。这不是简单的沟通误解，而是纯粹的工作流和技术栈断层。这就是为什么硅谷和科技初创公司看到的变革，要普及到普通知识型工作中需要数年的时间。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah, I think my uh it feels like my job these days is just bring reality to the valley and then bring the valley to reality as uh as much as possible. And it's a it is a kind of a crazy divide that that that exists at the moment. Caused by Yeah. Well, I think the gap is and Martine, I'm sure you see this, but I think the gap is caused by the styles of work that exist in Silicon Valley and in engineering roles versus sort of the rest of the world. So, and we've talked about this a couple times in in different forms, but but you know, the the technical aptitude of an engineer is just like insanely high. The level of wired inness to what's going on on the internet is insanely high. The the ability to use your own tools and make your own choices is insanely high. And when things go wrong with the systems that you choose, you can just like quickly debug them and then make them sort of work for you. And then obviously you have all the benefits of just the models are really good at code and and the work is verifiable. So you have like, you know, five or 10 things that make agents work in an enterprise context for engineering or at least even a shortcut context for engineering that that tend to be uh there tends to be a gulf between the way you work that way in engineering and the rest of of sort of knowledge work. And so and so a lot of what I see is trying to figure out how do we kind of you know bottle up all of the greatness that is you know what we are seeing from coding agents what we're seeing from agents that can use computers um to how do you bring that into the enterprise where the workflows are are you know quite different the users are less technical the data is much more fragmented the systems are much more legacy and so that that tends to be the divide it's not even that we're like talking past each other like in a in one of those kind of those kind of classic like government versus industry It's it's just literally like there is just a pure workflow and and and technology set divide and and that's why it's going to be you know a number of years for this sort of diffusion to to roll from what we're seeing in Silicon Valley. What we're seeing is tech shortcuts all around the world into the rest of knowledge work.

</details>

### 企业决策的“温差”

**Martin Casado**: 我认为像互联网这样的长期趋势最初都始于个人，而大公司倾向于集中决策。目前许多大公司的个人在使用 **ChatGPT** 等工具时非常高效，但公司本身甚至不知道该如何思考这件事。当你听到“95% 的大公司 AI 项目都失败了”这种统计数据时，那是很荒谬的，因为个人用得很好。

现实是这样的：董事会要求 CEO 搞 AI，CEO 找来顾问，然后启动一个没人懂怎么运作的中心化项目，操作层面没有对齐，结果自然失败。我们说“规模（Scale）”时常想到系统规模或人数，但我认为目前的趋势规模化得很好，但组织不知道如何调整那些围绕数据、治理、合规等运作了十年的陈旧流程。这就是 Aaron 所说的长期趋势与组织决策机构之间的断层。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. I also think that I mean these secular trends like the internet was like this actually start with individuals and big companies tend to make decisions centrally and this is one of the fastest growing secular trends. So like there's probably a lot of individuals in big companies that are doing it where like the big companies themselves don't know even how to think about it. And so when you hear stats like oh like MIT had this stat like 95% of AI efforts in big companies fail like that's clearly silly because I am sure everybody is using chat GPT very effectively. What what they really should be saying is you know whatever like I listen I sit in these boards too. So the board goes to the CEO and what does the board say? We need more AI. And what does the CEO said? Oh okay, I will get like a consultant to do more AI and then they have some centralized project that nobody knows how it works. They haven't aligned their operations and those things will fail. And so I don't you know when we say scale often we we think about things like system scale or number of people's I think the secular trend is scaling wonderfully which is being reflected in the numbers of these companies but organizations don't know how to adjust these kind of you know age-old processes that have been you know worked on on for a decade around you know data and governance and operations and compliance etc. That's kind of right now where I think like Aaron is right between the secular trend and the the organizational decision body. uh and this is something that we actually track very closely because we're starting to see now I would say in the last few months finally some real kind of inroads into the enterprise but it's it's it's tepid because and and the last thing I'll say of this one of the reasons is there's a lot of skepticism because the board wants AI CEO AI failures have created some amount of bruising which is you know you know requiring these companies get past it in order to do kind of the second go at it and so I think this is exactly where we are.

</details>

**Aaron Levie**: 我完全同意。以前通过争论使用哪种语言或架构就能拖延项目好几个月。但在 AI 领域，实验室迭代太快了，甚至连部署智能体的范式都没统一：智能体框架是在计算机内部还是外部？是在云端还是托管？访问哪些工具？技术并不完全通用，这导致了企业的**决策瘫痪**。企业架构团队会担心：“三四年前我在 AI 上选错了路，现在那个方案已经过时了，这次我该押注谁？” 这种技术变革的速度反而降低了技术扩散到核心工作流的能力。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah, I I 100% agree with that. there's also this very interesting um dynamic. you go to an engineering team classically for the past, you know, and you know, Stephen, you can take us back in in history on this one. And one of like the easiest ways to stall a project was just getting the architecture, you know, kind of the the fights on, you know, what language to use, what architecture path to go down, that could take months and months to kind of work through as your teams work through that. um because of the pace of change in AI, um you actually have this incredible dynamic where the the labs uh you know are are obviously leaprogging each other so frequently but with with not the exact same paradigm of how you should deploy agents and how they will work and is the is the is the agent harness in the computer? Is it outside the computer? Do you run it in your cloud? Is it hosted? What tools does it have access to? like we are like this is not a a a point where these are completely fungeable technologies and so that actually creates a a bit of paralysis because now as an enterprise architecture team in the real world you're like man like what what horse do I want to you know kind of get behind and and which architecture path do I want to get behind because I've been burned by doing the wrong thing in AI maybe 3 or four years ago and I went down some path that now is deprecated or not the right strategy anymore so so to some extent the speed of our change in in tech actually reduces the ability for the tech to get diffused into the really really important workflows because now you have a lot of paralysis in in just making decisions.

</details>

### 架构转向：智能体作为“用户”

**Martin Casado**: 六个月前，软件产品公司认为集成 AI 就是在产品里加个聊天框。现在我们看到的是一个巨大的架构和思维转变：**不要把 AI 看作软件，把它看作一个“用户”**。把你自己的产品变成一个 **CLI（命令行界面）** 工具，让 AI 作为智能体去使用它。你不是在融合两者，而是让你的产品更易于被 AI 消费。这意味着在一年内，你可能得对软件架构进行两次重构。

<details>
<summary>Original English</summary>

**Martin Casado**: I actually I I hate to jump in, Steve. I just like there's a like so Aaron is totally correct and there's a there's a very specific instance of this playing out in product companies right now and I'll tell you what it is. So, so, so software product companies um you know circa 6 months ago they viewed integrating AI was like you're actually integrating it into the product right so everybody was like adding like whatever this chat feature or like they you know and so it's kind of like this fusion or this hybrid model what we're seeing instead is instead of viewing AI as software like just view it as a user so instead like take your product make it it a CLI tool and then have the AI be an agent that actually uses it. So you're not fusing the two. You're just making it more useful for AI. This is a very very significant architectural and mental shift, right? And so we started as pure product and then we didn't quite know what the end thing looked like. So we created this, you know, this, you know, AI software hybrid that hasn't worked and now we're kind of going to the agentic model which basically means the agent is going to be whatever it's going to be cloud code or whatever and then my product now just should be something that can consumed by that and like that's the actual modality but you know within a year now you've had to rearchitect your software twice.

</details>

**Steven Sinofsky**: 硅谷的人可能无法理解大公司为什么要做这种押注。如果你只在几家初创公司待过，你的参照系里可能没有“挑选一个要沿用 40 年的应付账款系统”这种概念。

企业里的员工可能会说：“我要用模型来完成我的工作。”但他们会在**集成**上撞墙。AI 并不擅长集成。有人说：“如果是智能体，它就能像用户一样操作。”但如果你打过客服电话就明白，如果系统不奏效，你会被转接到另一个人类主管那里，或者被告知你找错了部门。

现在最令人兴奋的是，每个人都看到了这项技术的潜力。那些不喜欢 AI 的人会说：“看律师事务所里发生的幻觉事件，毁了官司。”原因其实是 25 岁的初级律师已经在成功使用 AI 一年了。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: And I think that that people in Silicon Valley don't quite appreciate when a big company says well we have to map out our bet that we're going to make because like that just seems stupid and you know if you have if your job history is you five two-year stints at startups that went from seed to series A to aqua hire or something. You well you you never you you don't your frame of reference is not you know picking an accounts payable system that's going to last 40 years consequences. Yeah. I I actually I have like all these visual aids today. you have people in in enterprises that are saying I'm going to use the model and do my thing. But they're only they're going to hit a wall at integration. And and this the thing that's not different about AI and that agents don't fix that nothing fix is that any enterprise of a thousand people or more or that's older than 10 years is just a mass of stuff that's sitting there waiting to be integrated and and you can't just say it's going to integrate. AI actually doesn't help to integrate anything. And so even if you change everything, the the people say, "Oh, no. If you make it an agent, then it can just go ahead and and and be a user." But if you're a user, like if you've ever called customer service for something, like literally you get bounced to another human if the system that you're talking to doesn't work and they're like, "Well, that's a manager." Or no, you're you're talking about payment, not reservations.

</details>

### 权限与“虚假生产力”

**Martin Casado**: 情况可能更糟。现在很多公司通过统计 **Token** 使用量来激励员工使用 AI。我昨天和一家著名大公司的员工聊，他说他和同事会让智能体去做一些毫无意义的任务，只是为了刷量。你衡量什么，就会得到什么。这就是“虚假生产力”，产生了一堆可能有问题的产出。

<details>
<summary>Original English</summary>

**Martin Casado**: Well, Ste Steve, it's actually Steve, it's actually a little worse than that. Where is right now many companies are incentivizing people to use AI by counting tokens. Oh, yeah. Yeah. Right. And so I'm not going to say the name of the I I spoke to someone yesterday who works for one of these large companies that famously does this and he's like me and my co-workers have agents do useless tasks just so that we can I'm no joke in No totally. Well you get whatever you measure. So yeah that's right. So like it's like the extreme form of what you're saying, Stephen. You have people that are like being fake productive and producing a lot of, you know, you could say perhaps problematic artifacts just because they're they're using these models.

</details>

**Aaron Levie**: 当年互联网兴起时，每个部门都要搞自己的网站。大公司里充斥着成千上万个“僵尸网站”。关于集成，智能体目前还没有摆脱人类面临的问题。当你被转接到不同的人时，涉及到不同的**访问控制（Access Controls）**。如果智能体绕过这些步骤，就会产生安全风险。

在陈旧的环境中，人类通常靠问 Sally 或 Bob 来获取权限或数据。如果智能体只继承了和你完全一样的权限，它也会到处碰壁。而且不像人类，它不知道去问 Sally。结果就是，很多智能体访问不到正确的数据，或者在非真实数据源的系统中工作。

这就是企业现在的真实工作：升级系统，实现现代化，确保智能体有权访问正确的数据和上下文。

<details>
<summary>Original English</summary>

**Aaron Levie**: When the internet happened, all of a sudden every company needed websites. And so like a very famous moment in time was not too long ago when every internal team had like a team website and they went out and they got like a vendor to write HTML and to create their site and then there was a team. But like there's nothing dumber than having a team website at a large company because a team gets reorganized like 6 months later and so companies were just filled with like with thousands of these dead web is what what the expression was. your point about being passed to the different human, you know, based on the role that you needed to interact with. you know, agents basically don't have any there's no real exception yet for the agent having the same problem because you basically, you know, as you pass through a different human, it's it's a different set of access controls that that that human has. And if an agent can sort of bypass any of those steps, then then that's how you instantly get the security risks that that like you you need to kind of pass through those steps so that way you don't accidentally, you know, get to the wrong piece of information and there's verification. And so there's a lot that that you need to kind of build out for agents to be able to go and and work with all these systems. And and we've talked about this, but like most legacy environments don't have the most authoritative, you know, access controls. So you're always as a human going and saying, "Hey, Sally, can you share that thing with me that that I don't have access to?" Or, "Hey, Bob, what's the number inside your data system for this question?" And so if agents just get the exact same permissions that you had, then they'll just run into these walls everywhere. and they won't be able to complete the process. And unlike a human, they're not going to know to go talk to Sally or ask the question of Bob. So, they're going to just be kind of, you know, stuck.

</details>

### Salesforce 的“无头”信号与身份

**Aaron Levie**: 上周的大新闻是 **Salesforce** 全面转向“无头化（Headless）”，表示希望在所有不同的智能体中被调用。这是一个风向标。大家必须弄清楚在这个无头世界里新的商业模式是什么。是收 API 税？还是给智能体买“席位（Seat）”？这标志着软件将作为背景运行。这让我很兴奋，因为我脑子里立刻出现了 5 到 10 个个人用例，比如在开会前或去某个城市前，让智能体跑遍所有数据系统做情报工作。

<details>
<summary>Original English</summary>

**Aaron Levie**: and so so the big news last week was uh was I I I think you know Salesforce I don't know if they surprised people or not but but I mean based on the reaction it seemed like it was maybe a surprise they they went full headless and they basically said you know like we want to be used everywhere across all of our all the different agents. Um, and I see that as a a little bit of a bellweather because I think as Salesforce goes, so does a lot of of of enterprise software. And I think a lot of people are going to try and, you know, have to figure out what is the new business model in this headless world. You know, do you do you charge a little bit of a a small just API tax? Is there a seat for the agents? So, there's obviously some work to do with that.

</details>

**Steven Sinofsky**: 智能体只是一个实体。很显然，它需要另一个许可证（License）。它必须有自己的**身份（Identity）**。智能体的权限永远不会高于让它去做事的那个人的权限。实际上，它应该被视为组织中的一个“同僚”。在 IT 架构层面，你不能让智能体先拿到结果再来判断是否可行。因为 **LLM（大语言模型）** 是随机性的（Stochastic），你无法像对 SQL 表那样应用规则。我觉得这种“无头”讨论让所谓的“SaaS 启示录”显得更蠢了，因为这将带来使用量的爆发。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: I also think I just I think on this one what's so what's so super cool is is that of course the first step is doing exactly what you described which is just looking stuff up. And so the the most interesting thing is using this notion that an agent is just a an entity. It's mo it's incredibly obvious to me that it's another license. Now, it might have a different license model, but it it has to have an identity. but as you go down the org the agent is never going to have more permissions than the person who's getting it to go do something and in fact it's just going to be like a peer to somebody else in an organization because otherwise you have all of these issues where the peer where a human can just say oh get me a super smart agent that knows everything that I'm not allowed to know.

</details>

### 无头浏览器 vs 像素模拟

**Martin Casado**: 其实在很多领域，“无头 SaaS”甚至可能行不通。举个例子：为什么大家用 **OpenClaw** 时要配一台 **Mac Mini**？主要是为了集成 **iMessage**，因为它没有无头版本。

另一个有趣的例子是：如果你试过用智能体操作无头浏览器，很多网站都有反爬虫措施，无头浏览器根本行不通。所以你得弹出真正的 **Safari** 浏览器。我认为这些模型的训练数据来自于人类在真实、非无头的 App 上操作。所以智能体更倾向于像人类一样使用 App，而不是通过无头版本。

<details>
<summary>Original English</summary>

**Martin Casado**: Exactly. So actually in in fact um so this is playing out in many domains. You can even make the argument that like a a a headless SAS doesn't make sense. And and here's the argument. The argument is let me give you an example. So um if you use openclaw, do you know why you use a Mac Mini with openclaw? It's number one for iMessage. Because there is no headless version. So you're just going to like use it. And then the second one is very interesting which is if you've tried to use headless browsers with agents the problem is is all of the websites um have anti-scraping measures so they don't work and so the reason you use a Mac mini so it can actually use Safari proper.

</details>

**Aaron Levie**: 我持反对意见。任何有良好 API 的软件，智能体绝对首选 API。只有当执行出问题时才会跳到浏览器。

**Martin Casado**: 这些模型是在现有软件的数据和 **RL（强化学习）** 环境中训练的，而那些软件并没有 API。目前我们看到的智能体采用情况，它们看起来更像人类的行为，而不是程序的行为。它们会像人类一样采取行动。

<details>
<summary>Original English</summary>

**Aaron Levie**: Oh no I'm taking the other side on that one big time. Yeah. Yeah. No, but but let me just let let me let me simplify the argument so we could actually have it. h I mean uh I would just say that that that any software that has a good API the agent would absolutely prefer to use the API and then you and then you pop into the browser the moment that you run into some execution problem

**Martin Casado**: However, these models are trained on data and RL environments from existing software that didn't have those APIs. And and and and right now, if you actually look at the adoption and the use of these agents, they look far more like what a human would do than what like a program would do.

</details>

**Aaron Levie**: 随着时间推移，智能体会进化出更好的数据集，针对每个 SaaS 平台的 **MCP（模型上下文协议）** 和 API 进行训练。通过像素导航只是效率低下的临时方案。

**Steven Sinofsky**: 架构的分层（Layers）永远不会消失。比如我们要搜一个文档，搜索 API 肯定比模拟点击快。但现在的“计算机使用（Computer Use）”能力确实惊人。当我看到我能移动鼠标，而另一个东西也在移动鼠标并点击时，我感觉自己已经不懂计算机了。

<details>
<summary>Original English</summary>

**Aaron Levie**: But I I just think to me it's it's more of just an inefficiency of of navigating through pixels versus just you know you you can just you can just

**Steven Sinofsky**: an addage in systems Aaron is that is that layers never go away. You just get layered. Clicking through a 100% right. But but but but the but to to have support the point like the new codecs the computer use that on the desktop is is you know just insane and I I mean Stephen obviously knows you know everything about how it would work. I when I saw my ability to move a mouse and then this other sort of mouse moving and clicking things I was like I don't understand computers anymore.

</details>

### 复杂度悖论：为何工程师需求不减？

**Steven Sinofsky**: 如果现在有一万名员工，每个员工配一个智能体，每个智能体访问系统的频率是人类的 500 倍。现有的 SaaS 产品会因为没法承受这种访问量而崩溃。

**Martin Casado**: 我不觉得这在架构上是多大的转变。如果是只读数据，就做缓存；我们懂怎么处理可变状态。真正的挑战是：当你用 AI 辅助编程时，代码质量往往会随时间推移而下降。你引入的问题和解决的问题一样多。我们还没弄清楚如何管理这种**熵（Entropy）**。大家在现有的系统上用智能体搞一些长期运行的任务，我不太确定我们是否知道如何保持系统的清洁。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: now we're going to have 10,000 new PE people which are the agents for each of those 10,000 employees and they're they're actually hitting it 500 times as much. Okay, so that SAS product will collapse. So like that's the the first order because it wasn't architected for that volume.

**Martin Casado**: I just feel like we understand like whatever if it's readonly data you cache it you know like all the state issues are around mutable mutable globally shared state we understand the limits of those. when you code um with AI, your code kind of gets worse over time pretty materially. And so, it's almost like you're introducing as many problems as you are solutions. And I don't think we've actually figured out how to manage that. I would say anecdotally watching companies struggle with AI coding... I don't think we know how to do that yet.

</details>

**Aaron Levie**: 这是一个绝佳的观点，回到了我们开始讨论的“规模”问题。大公司的高管每天醒来都觉得公司快分崩离析了，所以到处都是约束。这就是为什么那种“一键式生成、氛围驱动编程”的人觉得没问题，因为他们没活在那种需要防止系统崩溃的环境里。

AI 满足了人类对“高产”的渴望。我们感觉自己效率很高，但可能实际上在制造大堆额外的工作。Box 已经全面投入 AI 了，但我们不会吹嘘它带来了 10 倍生产力。因为我们有严密的 **代码审查（Code Review）** 和安全审查。AI 可能完成了 80% 到 90% 的功能开发，但安全审查慢了下来，因为不能有任何意外的代码注入。目前的产出增长大概是 2 到 3 倍。

我对工作岗位保持乐观，因为你依然需要人类在循环中。人类的抽象层次变高了，但你仍需要人类启动流程、审查结果并整合工作。

<details>
<summary>Original English</summary>

**Aaron Levie**: Well, I I love that point because that gets back to where we started, which is the difference between scale and not scale and why it's perfectly rational for big company people to be like, "No freaking way is this coming into our company because a big company is about to the wheels are going to come off a big company... and I I feel this is so critical Steve... AI caters to our need to be productive. So I feel like we feel like we're being very productive and we do all of these things but we may actually be creating like mounds of extra work to do. So so which is why we don't claim that it's a 10x productivity game to our engineering team. It's like no no because we have a lot of guard rails in place... AI built probably 80 to 90% of the feature and the the thing that slowed down the release of it was we have to do a full security review. I do think it's a 2 to 3x gain maybe across the board. By by the way, this is actually why I remain unbelievably optimistic on jobs because I don't think that you like I just think we've gotten it wrong on on thinking you know all the places where you're going to remove humans from this.

</details>

**Steven Sinofsky**: 90 年代初有一本书叫《工作的终结》（The End of Work），在互联网爆发前六个月出版，核心观点是技术革命彻底失败，没有生产力提升，还没了工作。这听起来很蠢。人们曾以为计算机会让会计失踪，结果是：天哪，现在会计能做的事情比以前多得多，因为他们不用整天人肉算数了。AI 是懂行的人的加速器，公司会想要更多这样的人，去处理更多信息。

<details>
<summary>Original English</summary>

**Steven Sinofsky**: this was a book in the 80s called the end of work. sorry it was in the '90s. And this idea that like AI just gets rid of jobs. It's as ancient as like you talked about the accountant. Like one of the things people thought was that computers would get rid of accountants. And and that was like IBM's pitch in like 1965, but what it actually did was like, "Oh my god, we could do so much more with accounting now that they're not like literally just adding numbers all day."

</details>

**Aaron Levie**: 最有趣的观念是，代码越多，工程师就越少。事实恰恰相反，因为系统更复杂了。当系统升级、停机或出现安全事故时，挑战更大。

如果你在硅谷，可能会觉得工程工作就是在 Google 或初创公司写代码。但别忘了，**John Deere** 在做自动驾驶拖拉机，**Eli Lilly** 在设计新的治疗方案。这五千家公司都需要下一代工程师，使用 AI 工具来自动化业务。软件正在“吃掉世界”，这意味着每个人都会拥有大量软件，但你仍然需要专家来提示智能体、审查工作并管理系统。所以，那些“别去学编程”的预言将被证明是彻底错误的。

<details>
<summary>Original English</summary>

**Aaron Levie**: it's like to me it's like the funniest concept that the more code we write the less we would need engineers. to be the opposite because because now your systems are even more complex than before which means that you're going to be running into even more challenges. you sort of forget, well, like John Deere is trying to make automated tractors and Caterpillar is trying to have AI systems and Eli Liy is trying to design even more pharmaceutical therapeutics. Mark and Dre predicted this you know 15 years ago of like software is going to eat the world and what that means though is that everybody's going to have lots of software... but you still need then an expert or a semi-expert... So, so all of the, you know, predictions on don't go into coding and don't go into software engineering, I think, will be proven quite quite wrong.

</details>