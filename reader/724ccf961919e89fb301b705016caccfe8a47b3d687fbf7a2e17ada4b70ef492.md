---
author: AI Engineer
date: '2026-10-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=IavxrdVnwXM
speaker: AI Engineer
tags:
  - runtime-authorization
  - intent-based-access
  - ai-agent
  - access-control
  - ai-safety
title: 基于意图的运行时授权与AI智能体安全治理探讨
summary: 嘉宾围绕AI智能体自主权展开讨论，指出传统OAuth及粗粒度API难以适配动态决策，提出基于意图的运行时授权来提供上下文、划分责任与限制爆炸半径，并就智能体风险与末日概率各抒己见。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - OAuth
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 基于意图的运行时授权

大家好。欢迎来到 AI Engineer New York。今天能来到这里，我感到非常兴奋。我叫 Ally How，是 Keycard 的技术人员。今天我和几位出色的嘉宾一同在此：Keycard 的首席执行官 Ian；摩根大通的全球首席安全架构师 Michael Davis；以及 OAuth 的创始人兼联创 Dick Hardt。今天非常荣幸能和他们一起探讨基于意图的授权。为了奠定基调，我想提一点：随着越来越多的公司希望赋予其 Agent 更高水平的自主权，他们正指望通过运行时授权来提供帮助。运行时授权是指针对每个工具调用来对 Agent 进行授权的做法，而不是让 Agent 拥有长期的宽泛访问权限，以防其最终被滥用。

<details><summary>Original English</summary>
Um, hi everyone. Welcome to um, AI Engineer New York. I'm super excited to be here today. Uh, my name is Ally. How I'm a member of technical staff at Keycard. Um, I'm here with some amazing panelists today. We have Ian, CEO of Keycard. We have Michael Davis, um, global chief security architect at JP Morgan Chase, and we have we have Dick Hart, the founder of AOTH and co-creator of OOTH with us on stage today. I'm super excited to talk to all of them about intentbased authorization. Um, and to set the stage, I want to bring to light that as more companies are looking to give their agents increased levels of autonomy, they're looking to runtime authorization to help. Runtime off is the practice of authorizing an agent per tool call rather than having the agent hold broadstanding access that it will eventually misuse.
</details>

然而，“是否允许此次工具调用”绝不是一个简单的问题。这是因为许多 MCP 工具和 API 的粒度都很粗。人类很难写出完美的策略，而且 Agent 周围的环境也会在运行过程中发生变化。意图可以通过提供额外上下文来提供帮助，从而让我们在运行时能够就 Agent 允许或不允许执行什么操作做出更好的授权决策。

<details><summary>Original English</summary>
However, is this tool call or not is never a simple question. This is because many MCP tools and APIs are coarse grain. Humans struggle to write the perfect policy and the environment around the agent will change as it runs. Intent can help by providing extra context so that at runtime we can make better authorization decisions about what an agent is allowed or is not allowed to do.
</details>

所以接着说，我想真正深入探讨一下：我们为什么首先需要基于意图的授权？模型已经有了显著提升。它们拥有更大的上下文窗口。由于模型视觉能力的提升，它们能够验证工作。在许多场景下，人们都在宣告 AGI 已经到来了。如果模型已经这么好，如果 AGI 今天真的已经来临，那为什么各团队在赋予其 Agent 更多自主权方面仍然步履维艰？Ian，我们从你开始吧。你在 Keycard 协助管理许多金融企业。你所看到的阻碍是什么？

<details><summary>Original English</summary>
So to continue I would like to talk about um really dive into why do we need intentbased off in the first place. Models have dramatically improved. They have bigger context windows. They're able to verify work because model vision capabilities have improved. In many contexts, people are proclaiming that AGI is here. If the models are so good, if AGI is really here today, then why are teams struggling to give their agents more autonomy? Ian, let's start with you. You're helping men and financial enterprises at Keycard. What are you seeing that's getting in the way?
</details>

>> 嗯，我认为总的来说，企业——尤其是金融服务机构、受监管的行业——几乎向来是安全第一。这就是他们在业务中建立信任的方式，而且保持业务连续性是第一位的首要考量，其次第三或第四才是创新。我认为在任何企业中，你通常看到的是由来自各个不同领域的不同细小身份、不同细小系统组成的大杂烩，你到底如何将这些结合在一起，让 Agent 能够穿梭其中、申请访问权限，并确保 Agent 能够执行用户或企业所期望的事？令人遗憾的现状是，我们今天的多数系统都是粗粒度的，对吧？Salesforce 就是个很好的例子，很长一段时间里他们 OAuth 上只有一个作用域，那就是“API”，这在 Agent 的语境下毫无帮助。因此，大致上最首要的部分是：他们今天所拥有的大多数安全系统，都是针对“人类做出所有决策、软件高度确定性”的世界设计的，而不是针对我们发明的这种基本上会进行推理、并一遍又一遍尝试寻找问题解决方案的全新魔盒。

<details><summary>Original English</summary>
>> Well, I think broadly speaking, enterprises, especially financial services firms, regulated industries are almost always security first. It's how they build trust in their business and maintaining the business continuity is by our first like the first priority then innovation is second third or fourth I think like broadly speaking in in any enterprise what you see is this like hodgepodge of different little islands of different little identities of different little systems of from across all different worlds and how do you actually tie that together in a way that an agent can navigate through that ask for access and then also ensure that the agent can outperform like uh something that was by the user or the business And the unfortunate situation is most of our systems today are coarse grained right I don't know Salesforce is a good example where a very long time they had a single scope which was API on their oath which is like in the context of an agent uh not very helpful so that's that's the broadly the first and foremost part is that most of the systems they have for security today were designed for a world where humans were making all the decisions and software is very deterministic not this new fangled magic box we've invented that basically reasons and tries over and over again to find a solution to a problem.
</details>

>> Doug，OAuth 是如何成为问题的一部分的？OAuth 是如何造成阻碍的，为什么它不适合 Agent？

<details><summary>Original English</summary>
>> Doug, how is OOTH part of the problem? How is OOTH getting in the way and why is it not the right fit for agents?
</details>

>> 嗯，当人们开始考虑如何授权 Agent 访问某些东西时，货架上现成的工具就是 OAuth，于是大家拿来这个工具说：“这儿有个工具，它是负责授权的，应该能解决这个问题。”但 OAuth 根本就不是为这种世界设计的。它最初是为“我如何让这个网站与那个网站通信”这类事情设计的。在 OAuth 2 中我们加入了作用域；在那之前它就只是“允许做任何事”。但它需要你进行预注册，期望有浏览器参与并进行重定向。这些年来 OAuth 也经过了演进以支持其他一些场景，但 Agent 世界是完全不同的。我们无法提前知道 Agent 需要做什么，我们需要随着时间的推移逐步做出该决策。Agent 的不同实例会需要不同类型的东西。而且，正如 Ian 所谈到的，人们认为“我们已经为 OAuth 准备了作用域，把它们直接映射给 Agent 就行了”，但对于 Agent 正在做的事情来说，这种作用域的粒度实在太粗了。

<details><summary>Original English</summary>
>> Well, when people started looking at how do we authorize agents to access something, the tool that was sitting there on the shelf was OOTH and people grabbed that tool and says here's a tool. This is authorization. It should be able to solve the problem. But OOTH was not designed for this kind of world. It was designed originally for like how do I let this website talk to this website? You know in O2 we added scopes. Before that it was just do anything. Um but it required you to be pre-registered. It's expecting that there's a browser involved in a redirect. You know OOTH has evolved over the years to support some other things. But the agentic world is completely different. We don't know ahead of time what the agent needs to do. We need to go and make that decision over time. different instances of an agent are going to need different kinds of things. And you know, as Ian talked about, the granularity of the scopes that people says, well, we already have scopes for OAS. Let's just map those over to agents is far too coarse grain for what agents are doing.
</details>

>> Davis，您看到企业是如何走向更高自主权的？

<details><summary>Original English</summary>
>> Davis, how are you seeing enterprises move towards higher levels of autonomy?
</details>

>> 是的，我认为关键部分在于你如何处理那种粗粒度的问题。我所见到的那些相对更成功的企业，他们接纳 Agent 的方式就像 onboarding 开发人员一样，对吧？一开始你在第一天不会获得完全的提交权限，对吧？随着他们逐步成熟，你实际上必须经历并不断增加能力层级，对吧？因此，企业正在提出关于“究竟什么样的上下文能让该 Agent 安全”的定义，而且这通常不仅仅取决于 Agent 自己怎么说，对吧？它可以进行证明，但还有其他一些因素，比如它所处的周围环境以及其他能够帮助你理解自主权级别的信息。一个非常简单的例子就是沙箱在哪里运行，它是否处于沙箱中，对吧？这类事情可以改变所被允许的自主权级别。

<details><summary>Original English</summary>
>> Yeah, I think the key piece is uh how do you deal with that coarse grain problem? And what I've seen the kind of more successful enterprises is they kind of board agents like they onboard developers right start with you don't get full you know commit access day one right you're actually having to go through and add the levels of capability as they mature right and so the definitions that enterprise are coming up with what is the context that makes this agent safe and it isn't just usually what the agent says right um it can you know attest to something but it's other things like the environment around it and other information that can help you understand levels of autonomy Very simple example would be where is the sandbox running is it in a sandbox right those type of things can change the level of autonomy that's allowed
</details>

>> 确实如此，是的。我们提到了那种粗粒度访问问题，为了让大家更直观地理解这一点，举个例子：使用 Notion 的 MCP 服务器，你可以说“获取该页面”——也就是类似查看页面或获取页面的工具——但你不能说“只获取该页面上的这个数据库”。基于意图的运行时授权怎么会是一种更好的模型？大家谁都可以谈谈。

<details><summary>Original English</summary>
>> absolutely yes we mentioned that core screen access problem and to put that into perspective um to give an example um with notion's MCP server you can say fetch this page which is like the view page um tool or get page but you can't say just get this database on this page um how is runtime authorization based on intent a better model that's for anyone.
</details>

>> 我来试着谈谈。对我来说，这是金融服务行业也许可以借鉴以往银行经历的背景。银行在很久以前就从“对人进行授权和身份验证”转向了“对交易进行授权”，对吧？而该交易在何时发生？在运行时，对吧？因此我认为，对于运行时授权，我们将能够吸取过去的教训，并将其应用于这个全新的问题。另外我也认为，当你理解了意图时，在运行时调试某些东西会变得更容易，对吧？我想我们都记得过去写支票的情形吧？或者现在的年轻人大概是在电视上看到那类东西了。但在写支票时，上面有一个备注栏，对吧？那个备注栏当时就是用来如实说明这笔付款的意图的。但支票本身确实有限制，对吧？金额、收款人、日期等等，对吧？我认为其中很多概念现在正在被应用，也可以被应用来协助这种运行时。

<details><summary>Original English</summary>
>> I'll take a shot at. So to me, um this is something that the financial services industry hopefully maybe we can learn from the background that you know banks have gone through. Um banks moved long ago from authorizing and authenticating humans to authorizing the transaction, right? And when is that transaction occurring? At runtime, right? Um, and so I think that, you know, runtime authorization is we're going to be able to learn from the kind of the scars of the past that we've had and apply it to this new new problem. Um, I also think that uh, you know, one thing is easier to debug something at runtime when you understand the intent, right? I think we've all remembered back in the day writing checks, right? But, um, or seen those things on TV now, I guess, is the right thing. Um, but, uh, you know, writing checks, there was a memo field there, right? That memo field was used to actually tell the intent of what this payment was. But the check itself did have limits, right? The price, the pay, the date, etc. Right? I think a lot of those concepts are now being applied and can be applied to help with this runtime.
</details>

>> “意图”有点像是那种——就像很多词一样，词语的定义往往很复杂。沿着刚才进行单笔交易付款的例子说下去，对吧？那并不是一个作用域。那是“在这一特定上下文下，我能否执行这一件事？”好吧，虽然只是这一笔付款，但我认为我们需要——Agent 要做出任何“是否应该允许其执行”的决策，你需要所有其余的上下文：我们为什么要进行这笔付款？之前发生过的所有事情是什么？我们是不是就在5秒钟前刚进行过同样的一笔付款，而现在这变成了一笔重复付款，对吧？仅仅因为这在当前局部上下文中是合规的，本身并不意味着在更广泛的任务中也是合理的。所以，在 OAuth 领域我们正在研究“任务”这一概念，即从全局来看我们希望 Agent 达成什么，然后每一个决策都是在围绕达成该全局目标的整体背景和意图下做出的。而且你需要在交易层具备细粒度，对于许多事情来说要知道究竟在发生什么，而不仅仅是“我被允许去进行付款”。

<details><summary>Original English</summary>
>> Intent's sort of one of those, you know, like many words, words are hard. And so, you know, building on uh the example here of making a payment of a transaction, right? You know, that's not a scope. That's can I do this one thing in this particular context? Well, this one payment, but I think we need a an agent. we to make any decision should it be able to do it you need all the rest of the context of why are we making this payment what are all the things that happened before you know did we just make the same payment just like you know 5 seconds ago and now this is a double payment right you know just because this is right in context doesn't by itself doesn't mean it's the right thing within the broader mission and so you know in AOTH we're working on the concept of a mission that is what do we want the agent to accomplish big picture and then each of the decision decisions are made within the context you know the intent around what's happening big picture around doing that and you need granularity at the transaction layer for many of the things to know what exactly is happening not just I'm allowed to go and make payments
</details>

对，我认为最有趣的事情之一，如果通过一个实际的例子来理解为什么需要意图：如果你有两个 ChatGPT 会话或两个 Claude 会话，在其中一个会话中我说“嘿，帮我买点东西”，而在另一个会话中我说“嘿，帮我了解一下生产环境中为什么会出现 Bug”。在它们应当拥有哪些权限这方面，这两者具有非常不同的画像……

<details><summary>Original English</summary>
yeah I think one of the most interesting things I think about like a practical example like to understand like why intents required is if you have two chat GPT sessions or two cloud sessions in one session I say hey help me go to do some shopping in the other session I say, "Hey, help me understand if there why there's a bug in production." Those have very different like profiles in terms of like like what permissions they should have
</details>

<!-- chunk 2/7 -->

还有就是什么时候应该让你重新介入——比如人类应该在什么时候再次参与进来？所以归根结底，如果我们没有意图，或者缺乏某种能力去传达用户或业务对此事物的意图，我们实际上根本无法实现自主性，对吧？今天上午的很多演讲都在讲：“嘿，我们要用 Agent 来运营业务，我们要用它来做所有这些事情。”听起来很棒。但是，一旦发生类似 pocket OS 那样的事故，比如它拥有粗粒度的访问权限而不是限定范围的长期访问权限，结果意外删除了生产数据库而不是暂存数据库，这时候会发生什么？因此，作为一个行业，我们希望利用我们创造的这个“魔盒”来自动化我们的生活。而现实世界的现状是，你可以这样做并承担所有风险，然后坐看由此引发的所有事故。所以在我们真正解决这一底层问题之前——也就是实现真正的自主性，能够将业务付诸运营，让人类能够抽身并实现规模化扩张——我们必须先解决意图问题。

<details><summary>Original English</summary>
and also when they should bring you back into the loop, like when should the human be involved again? And so at the end of the day, if we don't have intent or some capacity to like relay what is the user or the business's intent with this thing, we actually can't get to like autonomy, right? And so a lot of the talks this morning were, hey, we're going to run our business on agents, we're going to do all this stuff. It's like, well, great. But what happens the first minute like a pocket OS style instant happens where like it actually accidentally deletes a production database instead of staging because it has coarse grained access instead of long scoped access. And so we what we want as an industry is to leverage this like magic box we've created to like automate our lives. The current state of the world is that you can do that and take all of the risk and then you can see all the instance that come from it. And so until we actually solve that underlying problem, realizing true autonomy, so being able to operationalize our business and be able to step away as humans and scale that, we have to solve intent first.
</details>

>> 确实如此。既然我们理解了为什么需要基于意图的授权，那么就来谈谈它在实践中到底是什么。它的原语是什么？在实际操作中具体是什么样子？Dick 提到了 AOTH 任务（mission）的概念。Dick，请详细阐述一下任务。任务是基于什么构建的？是基于用户的意图？还是 Agent 的意图？亦或是两者的结合？

<details><summary>Original English</summary>
>> Absolutely. And now that we understand why we need intentbased off, let's talk about what it is practically. What are the primitives? What does it actually look like in practice? Um Dick hinted at it with the concept of the AOTH mission. Um so Dick, elaborate on the mission. What is the mission based off of? Is it based off of the user's intent? Is it the agent's intent? Or is it a combination of the two?
</details>

>> 这个嘛，Agent 应该代表当事人开展工作。在 AOTH 中，我们将当事人定义为组织或人类，因为 Agent 可以代表其中任何一方运作。所以它需要为了其所代表当事人的最大利益而行动，因为最终对 Agent 的所作所为负责的正是当事人，对吧？Agent 本身不可能承担责任，对吧？

<details><summary>Original English</summary>
>> Uh well, the agent, you know, should be working on behalf of the person. And in AOTH, we define a person as either the organization or a human because it could be operating on either one of those. And so it needs to be acting in the best interest of the person that it's acting on because that is who's ultimately responsible for what the agent does, right? The agent agent can't be responsible, right?
</details>

任务是当事人交给 Agent 去做的事情。一个优秀的 Agent 会去与当事人协商，进一步沟通比如围绕该任务的具体参数是什么。一个很好的例子是，回想过去——感觉就像 3 个月前——当你想编写某段代码时，你会制定一个计划，然后 Agent 去执行这个计划。现在你只要告诉它，它自己就能把一切搞明白。但“什么是计划？你想做什么？”这一整套概念由你交给 Agent，这就构成了你后续做出授权决策时的上下文。然后，该任务标识符会贯穿全程。这样你就可以去进行审计，能够查看在这一特定任务的上下文中发生的所有事情以及做出的各项决策，对吧？而在今天，其实并没有成熟的 Agent 身份或任务概念，对吧？大家只是在生成某些东西，系统在做决策时根本不知道具体是哪个 Agent 实例在执行，也不知道这涉及到什么任务的上下文。确实如此。

<details><summary>Original English</summary>
And and so the mission is something that the person is giving the agent to do. The agent uh a good agent is going to go and negotiate with a person to go and talk more about like what what could what are the parameters around that. You know a good example is when you think of back you know in the day which seems like 3 months ago when you would want to code something up and you create a plan and then the agent would do the plan. Now you just tell it and it figures everything out. But that whole concept of what's a plan? what are you trying to do? And you give that to the agent. So then that then is a context around your where you're making authorization decisions later on. And then that mission identifier tracks through everything. So you can go and you know audit and be able to see what were all the things that happened and what were the decisions that happened in the context of this one mission, right? Where today you know there isn't really a good concept of agent identity or the mission, right? It's just making something and and things are making decisions without really knowing which expl which instance of the agent's doing it or what's a context of what mission is this involved in. Right.
</details>

>> 能再多讲讲协商阶段吗？因为如果一个用户正在与一个即时 Agent 对话，并对该 Agent 说“我想让你去读取 CEO 的电子邮件”，这超出了该 Agent 的范围，那么该意图是否会被用户拒绝？理应如此，对吧。所以我们知道，通过良好的关注点分离——我忘了我们稍后是否会讨论这个——但对于工作者的关注点分离，存在一个正在干活的 Agent，而我们认为应该有一个单独的 Agent 来监督它的行为。这样就实现了关注点分离：监督 Agent 自身不执行任何工作，但它决定这个工作 Agent 可以做什么。因此，如果用户说“哦，我想让你去读取 CEO 的邮件”，这很可能立刻就会被确定性策略拦截下来，对吧？这并不是一件模糊不清的事情，对吧？读取他人的电子邮件，我们对此有很好的控制措施。但是，如果指示 Agent “把 CEO 的邮件转发给外部世界”，这就稍微模糊一些了，而这种事情在理想情况下应该反馈给监督 Agent，由它判定“这可能不是个好主意，不，你不能这么做”。

<details><summary>Original English</summary>
>> Tell me more about that negotiation phase because what happens if a user is talking to an instant agent and it talks to that agent and says I want you to go read the CEO's email. That's outside of the scope of that agent. So is that intent rejected from the user? uh should be right so we know with a good separation and I don't know whether I forget whether we're talking about this later but the separation concerns of the worker right there's an agent that's doing the work and we believe there should be a separate agent that's supervising what this one does and so that you have a separation of concerns where this one can't do any of the work but it gets decide what this agent gets to do and so if the user says oh I want you to go read the co's email, that's probably going to get caught in deterministic policies right away, right? Like that's not a vague thing, right? Reading reading somebody else's email, we've got good controls for that. Um, but telling the agent to, you know, send the CEO's forward a CEO's email to the outside world, that's a little more vague and that's the kind of thing that ideally comes back to a supervising agent says that's probably a bad idea and no, you can't do that.
</details>

>> 确实。我觉得这构成了基于意图的授权的另一个原语，即策略。Keycard 的 Ian，在你们看来，当一个任务需要变更，或者一项策略需要更新时，Keycard 如何帮助追踪这些变动——当可能需要对任务或策略进行更新时？

<details><summary>Original English</summary>
>> Absolutely. So, I feel like that's another primitive two of intent based off is is policy. Um Ian at Keycard, how are you seeing that when a mission needs to change or a policy needs to update, how can Keycard help keep track of those changes as maybe the mission or policy updates need to be made?
</details>

>> 是的，退一步来看，前段时间 Davis 和我正坐在一间屋子里，在 AOTH 以及生态系统中其他类似事物实际涌现出来之前，我们深入探讨过的事情之一就是“授权疲劳”（consent fatigue）。我认为至少我们总要面临这种权衡：系统的安全性要做到多高，与对人类造成的干扰影响之间如何取舍。因此在 Keycard，我们对此的宏观观点是：你需要拥有广泛的确定性策略，基本上规定哪些事情绝对不能发生，或者哪些事情始终需要人类介入。在此基础上，你真正需要思考的是：好了，既然我已经落实了这些策略，那么作为人类或组织所能编写的所有策略，与在具体任务细节中我真正期望策略呈现的样子之间，存在着巨大的鸿沟。所以真正的挑战在于：我该如何将这两层结合起来？因为人类不可能把所有规则都写出来。这里面存在这样一种形态：用户之间或 Agent 之间的交互，它们彼此之间有一种意图，属于事务性意图；同时，还有企业构建或采用 Agent 的业务意图。比如，我们为什么要购买 cloud code？因为我们想让开发者更成功，或者因为我们想做各种不同的事情。而在使用 cloud code 或其他工具的具体语境下，我此时此刻为什么要使用 cloud code 工作？实际上是为了修复暂存环境中的一个 bug，对吧？这是两种不同类型的意图。如果我们能够理解这两种不同的维度，并将其以某种方式转换为限定这些 Agent 行为的边界框（bounding box），那么基本上就可以计算两者的交集，并指出：好的，这就是你实际允许做的事情。而对于构建这些系统的任何人来说，关键技巧在于：如何确保除非万不得已，否则不将用户拉入决策循环，因为这正是决定采纳曲线的问题所在。但这同样也是从一开始就让 Agent 具备自主性所面临的采纳曲线难题。

<details><summary>Original English</summary>
>> Yeah, I think like taking a step back, there's like actually was Davis and I were sitting in a room some time ago and uh before like AOTH and and some of these other things actually had emerged in the ecosystem, one of the things we actually talked a lot about was consent fatigue. And I think like at the minimum like we you always have this like how secure do you make a system versus like the trade-off of like the impact of the human. And so you know a key card our broad view on this is you want to have like broad-based deterministic policy that basically says this is what must never happen effectively right or these are the things that always require a human be involved. And then from there, what you really want to think about is, okay, cool. Well, now that I have that in place, there's a big gap between all the policy I can write as a human or write as an organization and then what I actually want the policy to be in the specifics of a specific task. And so the the ne the real challenge is how do I like layer over those two things, right? Because humans can't write it all. And so there's a version of that that is like a user or agent to agent interaction and they have an intent between those two of like transactional intent. And then there's also like the business's intent for why they build or adopt an agent. So why did we buy cloud code? Well, because we wanted to make our developers more successful or because we wanted to do these different things. And in the context of using cloud code or whatever, why am I working in this moment with cloud code? Well, it's actually to fix a bug in staging, right? And those are two different types of intent. And if we can understand those two different things and then convert that some way into into uh like a bounding box of what those agents can do, you can then basically calculate the intersection of that and say okay here's what you can actually do. And then the trick for anyone building these systems is how do I ensure that I don't bring the user into the loop except when absolutely required because that's what's going to be the adoption curve problem. But that's also the adoption curve problem when it comes to like enabling agents to be autonomous in the first place.
</details>

>> 有道理。

<details><summary>Original English</summary>
>> That makes sense.
</details>

>> 我很赞同你关于交集的说法。我认为这是我们在身份与访问管理领域探讨不足的独特之处，对吧？通常情况下你获得的是对单一对象的访问权限，对吧？所以在这类基于意图的方法中我所见到的成功之处，也是让我更感到兴奋的地方在于，你实际上可以让这些不同的意图来自组织的不同领域，对吧？从而实现这些要素的解耦——它们可以各自独立存在，但随后汇聚在一起来形成最终的决策。而且这个决策不必是静态的，对吧？如果借用 CEO 电子邮件的例子，如果该上下文涉及到那是行政助理，那么是的，也许她本就应当阅读该邮件，对吧，或者也许仅仅是日程日历，对吧。所以每当我们观察并开始思考这些交集组件时，我们便有了一种全新的方式来表达策略，同时也开始不仅引入我们以往讨论的方程一侧（即应用在执行某项操作），现在还真正能够将整个生态系统引入其中。因此，我越发看到组织开始意识到维持这些其他元素的状态或上下文以能够……

<details><summary>Original English</summary>
>> I like what you were saying with the intersection. And I think that's a unique thing we don't talk about enough within identity and access management, right? Normally you get access to one thing, right? And so what I've seen successful kind of in this intentbased approach. Um, and where I get more excited is you can actually have that those different intents be from different areas of the organization, right? And so you have the decoupling of these things that they can kind of live on their own but then come together to form that, you know, decision. And that decision doesn't have to be static, right? So if we use the example of the CEO's email, well you know if that context involves that's the administrative assistant then yeah maybe she is supposed to read the email right or maybe just the calendar right and so I think when we see and we start thinking about these intersection components um we have a totally different way we can start expressing policy but also starting to bring in not just the one side of the equation we always talked about before which was the app doing something now we actually have the ecosystem you can bring in and so the more I I see organizations starting to realize that you maintaining that state or that context of these other elements to be able to
</details>

<!-- chunk 3/7 -->

……在这方面有所帮助。意图可以彻底改变你在运行时授权中的效率。

<details><summary>Original English</summary>
help with that intention can completely change the way you're effective at runtime authorization.
</details>

>> 你今天在各企业中看到这种情况了吗？大多数人是已经落实了使命追踪和策略追踪，还是说目前在很大程度上依然缺失？

<details><summary>Original English</summary>
>> And are you seeing this across enterprises today? Most people have mission tracking and policy tracking in place or is that largely missing today?
</details>

>> 不，它仍然是全新的。嗯，我想，你知道，我之所以很兴奋来讨论它，部分原因在于我认为它正在改变我们梳理和推理这一问题的方式，对吧？即便在最简单的情况下，如果你是一名开发者，嗯，你在从事务这类事情的角度思考，并且你拥有这些意图的概念，嗯，它会让你更容易去构建那些将通过该意图来组合并使用的组件，嗯，所以我觉得它会给我们提供更多途径来推理这些问题、进行沟通，并最终实现更高的互操作性，对吧？嗯，对我来说，我认为最后一件有趣的事情是你可以针对它运行的诊断。意图是某种可能会穿透许多事件的东西，对吧？而且我认为，呃，我之前看到过的一个例子就是，你知道，讨论像那样的使命如何流转穿透。嗯，它可以是长期的。它可以是持续数周，那种［笑声］意图/关注仍然存在。嗯，所以对大多数企业来说，目前仍然处在非常、非常早期的阶段。

<details><summary>Original English</summary>
>> No, it's it's it's brand new still. Um and I think you know part of the reason why I'm excited to talk about it because I think that it is changing the way to reason through this right even in the most simplistic case if you're a developer um and you are thinking in terms of things like transaction and you have these concepts of intent um it makes it easier for you to potentially build the components that'll be composed and used through that intention um and so I think it'll give us more ways to reason through these and communicate and then ultimately be more interoperable right um and to me the last thing that I think is interesting is the diagnost diagnostics that you can run on this. Intention is something that flows through many events potentially, right? And I think uh one of the examples I've seen before is, you know, talking about that like that that mission flows through. Um it could be longived. It could be weeks that [laughter] attention can still be there. Um so it's still very very early for most enterprises.
</details>

>> 确实如此。是的，互操作性是关键。我认为这对企业来说相当困难，因为他们在不同的云、不同的环境、不同的遗留系统之间来回穿梭，而这种策略、这种使命必须在所有这些不同的跳步中始终保持有效。

<details><summary>Original English</summary>
>> Absolutely. And yes, that interoperability is key. I think that's pretty hard for enterprises because they're rubbing between different clouds, different environments, different legacy systems and that policy that mission has to hold through all of those different hops.
</details>

>> 是的，许多企业仍然必须面对这样一个事实：权限写着只读，但实际仍然是重写/读写，［笑声］对吧？所以就像你不得不开始处理其他问题一样，嗯，我认为这将有助于在人们之间建立起那种分类法或语言，让互操作变得更容易。是的，

<details><summary>Original English</summary>
>> Yeah, a lot of enterprises still have to deal with the fact that the the permission says read only and it's still rewrite, [laughter] right? So like you have other problems you have to start dealing with and so um I think that it will help get that kind of taxonomy or language amongst people be easier to interoperate. Yeah,
</details>

### 基于意图的授权与智能体商务

>> 确实如此。我对基于意图的授权感到兴奋的原因之一，是因为我认为它有能力成为诸如智能体商务之类事物的巨大催化剂。嗯，那我们把基于意图的授权应用到实际事物中吧。我认为基于意图的授权在这里增加了许多价值，对用户来说，它可以帮助他们确保自己的智能体在个人预算范围内购买正确的商品。而对商家来说，这意味着捕获意图能够为他们提供额外的数据，以了解为何进行这笔购买，以及是否甚至应该信任该智能体访问他们的网站。嗯，戴维斯（Davis），当我们把智能体放在金融服务和智能体商务的语境下考虑时，为什么基于意图的授权如此重要？

<details><summary>Original English</summary>
>> absolutely. One of the reasons why I'm excited about intentbased authorization is because I think it has the ability to be a huge unlock for things like agentic commerce. Um, so let's apply intentbased o to something real. I think intent based off adds a lot of value here and for users it can help them ensure their agents buy the right item with their own personal budget. And for merchants that means capturing the intent that gives them extra data to understand why a purchase is being made and if this agent should even be trusted to visit their site. Um Davis when we think about agents in the context of financial services and agentic commerce why is intentbased off so important.
</details>

>> 嗯，我认为简单来说，它扩展了——也许不是所有人都了解，但有些人了解的——围绕你知道的“了解你的客户”（KYC）的概念，对吧？所以我想了解我的客户，了解他们是谁、他们在做什么，但我认为我们也开始看到，我想了解我的智能体，对吧？所以我觉得这里存在一种联动，围绕智能体本身、嗯实际用户的意图、操作者的意图、处理者的意图，对吧，等等。嗯，在此之前，我们很难真正将这些整合在一起，对吧？嗯，当涉及到商务这类事情时，这当然非常重要，因为在此之上你还有关于诸如监管要求等方面的额外层级，需要了解其意图是什么，等等。嗯，我认为这将有助于简化这些操作，这意味着我们将拥有更多途径让这些智能体，你知道，为我们做好工作。

<details><summary>Original English</summary>
>> Um, I think simply it extends the concept maybe not everybody's aware but some are around you know know your customer right so I want to know my customer know who they are what they're doing but I think also we're starting to see I want to know my agent right so I think that you have a coupling here around the agent itself um the intent of the actual user the intent of the operator the intent of the processor right etc um very before now we couldn't really bring those together right um it matters of course when it comes to things like commerce because you have additional layers on top of this around what was the intention for things like regulatory requirements etc. Um and this is going to help I think simplify those operations which means we'll get more access to these agents you know doing good work for us.
</details>

>> 很有道理。而智能体商务的另一个障碍是网络并非为智能体而建这个事实。嗯，伊恩（Ian），你能告诉我们智能体身份可以如何提供帮助吗？

<details><summary>Original English</summary>
>> That makes sense. And another blocker for aentic commerce is the fact that the web wasn't made for agents. Um Ian can you tell us how agent identity can help?
</details>

>> 是的，退一步来看，我们好像一直都有这样一个问题：对于未注册的客户端，你该怎么处理？比如，我来到 eBay，我还没有登录，我使用的是 Chrome，eBay 不知道我是谁。我该如何进行访客结账？我该如何证明我是一个人？我该如何，你知道，好让他们可以，你知道，说：“是的，你可以出价 50 美元竞拍这双袜子。”而且如果我认为大家都在关注个人智能体领域的动态——Muse、Instinct、Grockbot，以及嗯你知道最近关于 Sierra、Decagon 及其盟友围绕这项个人智能体协议的公告——其根本问题就像是：你如何让一个智能体出现在一个网站上，能够与该网站互动，并知道你确实能够信任该智能体？所以就像很长一段时间以来，网络上都有验证码。这是为什么呢？因为我们想要防止垃圾信息。我们想要防止滥用。所以我们添加了验证码，然后这成了只有人类才能解决的事情。所以如果我们有验证码来阻止垃圾信息，他们就无法对该系统发送垃圾信息，对吧？而现在我们有了智能体，它们攻破了验证码。嗯，但这一直以来就像是网络上的一个传统问题。事实上，如果你回想两到三年前，Vercel——我想我们都知道 Vercel——在西班牙被封锁了。那么，为什么 Vercel 在西班牙被封锁呢？因为 Vercel 上的每一个主机都共享相同的 IP 地址。而 Vercel 上托管了一个、仅仅一个主机，Vercel 上的一个网站，托管了类似西甲联赛的内容。西班牙决定：嘿，为了阻止西甲内容在西班牙境内非法播放，我们要封锁整个 Vercel，对吧？因此，正如 Vercel 遇到这个问题一样，智能体也面临着同样的问题，但情况要严重得多、严重得多。那么，你如何让从未见过的未注册流量出现在你的大门前，然后决定是否放行呢？这正是我们首先必须解决的根本问题。Muse 和 Instinct 面临的也是同样的问题。他们正在努力尝试的，就像是我们究竟该如何创建大家都能据此操作的可接受轨道。这样作为下游资源，我就可以根据用户是谁来决定允许哪些智能体、信任谁，而在另一端，我也能知道该如何与这些人沟通。

<details><summary>Original English</summary>
>> Yeah I think stepping back we've kind of always had this problem where like what do you do with the unregistered client? So, like I I show up on eBay, I haven't logged in, I'm using Chrome, eBay doesn't know who I am. How do I do guest checkout? How do I prove I'm a person? How do I, you know, so they can, you know, say, "Yeah, you can bid on the this pair of stocks for $50." And if I think if we're all paying attention to what's going on in personal agents, Muse and Instinct and Grockbot and um you know recently this announcement OD to Sierra and Decagon and friends around this personal agent protocol is like the fundamental problem we have is like how do you have an agent show up to a web website be able to interact with the website know that you actually can trust that agent. So like for a long time you've had captures on the web. Well why is because we want to prevent spam. We want to prevent abuse. So we added captures and then like that's something only a human could solve. So if we have a capture that stops spam. So they can't spam the thing, right? And now we have agents and they've broken captas. Um, but this has like been a traditional problem on the web. In fact, if you think back two to three years, Verscell, which is I think we're all aware of Verscell, was blocked in Spain. Well, why was Versel blocked in Spain? Because Versell shared the same IP addresses for every single host on Versel. And there was one, one host on Versell, one website in Verscell that they were hosting that was hosting like Premier League content. And Spain decided, hey, in order us to stop for that premier content being displayed illegally inside Spain, we're going to block all of Forcel, right? And so in the same way that like Verscell has the problem, agents have the same problem, but so much so much worse. So how do you have unregistered traffic you've never met before show up to your front door and then decide whether or not you let it in or not? And that's like the actual first and foremost funal problem we have to solve. It's the same issue with Muse and Instinct. And what they're trying to do is like how do we actually create agreeable rails we can all operate on. So as a downstream resource I can decide what what agents want to allow who I trust based on who users they are and then on the other side I can also know how to talk to those people.
</details>

>> 很有道理。迪克（Dick），AOP 是如何帮助开启智能体商务的未来的？

<details><summary>Original English</summary>
>> Makes sense. Dick how is AOP helping unlock the future of aentic commerce.
</details>

>> 呃，关键在于很多人一直在构建某种专有的封闭黑盒系统，对吧，你知道，所以我支持个人智能体协议（Poppy）的概念，嗯，但它其实走得还不够远，对吧？它只是，好吧，现在我们有了一点智能体身份，我们只是使用了一些积木组件，这是一种吸引人的方法，因为你可以直接拿来做，但它并没有解决在智能体世界中所需要的许多新事物。因此，人们制定标准的一个关键动机，是能够将来自不同地方的组件插接在一起，对吧？所以我坚信我们应该对自己智能体的行为拥有控制权。在某种程度上，智能体承担的工作将变得如此之多，以至于我们根本无法由人在回路中去审批每一件事，对吧？那根本不可能，我们已经看到这种模式无法扩展。因此这意味着我们需要一个监督智能体，它是属于我们的监督智能体，运行我们的策略并决定我们如何行事，它应该独立于承担所有工作的那些智能体。如果我们想要能够即插即用地使用这些东西，我们就需要有一个协议来将它们分离开来。否则，你知道，关于智能体能做什么和不能做什么、防护栏是什么的决定，就会由智能体本身、由智能体的供应商围绕你能做什么和不能做什么来决定。而我真的不想把控制权让给他们来决定我能做什么，也不想让我所有的决定都基于其内部。或者说，我希望能够将那种监督拉入另一个组件中，而为了能够即插即用各个部件，我们需要有一个能让各事物相互操作的协议。

<details><summary>Original English</summary>
Uh well a key thing is a number of people have been building sort of proprietary closed box systems right you know so you know I'm a fan of the concept of the personal agent protocol Poppy um but it doesn't really go far enough right it just it's like okay well now we've got a bit of an agent identity we just use some of the building blocks and it's an attractive approach because you're just doing it but it doesn't solve many of the new things that you need for u an agent IC world and so a key motivator for people for having standards is that you can plug components from different places right so I'm a strong believer that we should have control over what our agents do at some point agents going to be so much doing so much work there's no way we can have human in the loop approving everything right that's just not we've already seen that that isn't going to scale so that means we need to have a supervising agent that is our supervising agent that runs our policy and decides how we do things that should be independent of the agents doing all the work. And if we want to be able to plug and play those things, we need to be able to have a protocol to separate those. Otherwise, you know, the decision about what the agent can and can't do, what the guard rails is decided by the agent, by the vendors of the agent around what you can and can't do. And I don't really want to go and give control to them to decide what I can do and that all my decisions are based in there. or I want to be able to pull that supervision into another component and in order to be able to plug and play pieces, we need to have a protocol that things interoperate.
</details>

>> 我、我只是想补充一点。我认为就像眼下我们所看到的，我们都有点像——我们都希望网络是联盟化/联邦化的，对吧？那意味着像网站或网络上的资源可以决定自己被允许做什么，但是事物运行所依据的标准应该是联邦化的，使我们大家都能进行互操作。我认为我们正处于这样一个时刻，你知道，我们正处在有几个大玩家的时刻，对行业来说，问题在于：我们是否要妥协于那些实际上把我们绑定在大型玩家身上并将……

<details><summary>Original English</summary>
>> I I just add to that. I think like right now what we're seeing is like we kind of like we all want the web to be federated, right? That does that that means like re like websites or resources on the web can decide what they're allowed to do, but the the standards upon which things operate should be federated enable us all to interoperate. And I think we're at a moment where things like, you know, we're at a moment where there's a couple large players and the question for the industry is, are we going to settle on things that actually buy us to the large players and give
</details>

<!-- chunk 4/7 -->

### 开放协议与人的责任

把它们做成像混凝土块门一样吗？我们是要转向去做我们一直在做的事情，也就是构建联合协议，比如 OIDC 这类的东西，比如 TLS 这类的东西吗？那些东西运行起来，促成了一个广泛的网络，促成了大量商业活动的发生，促成了大量信息的流动，也以一种让我们能够发挥创造力的方式，让我们所有人都有了工作。所以我向整个行业提出的问题实际上是：好吧，这些东西要来了。我们想要哪一种版本的世界，是这样还是那样？

<details><summary>Original English</summary>
them like concrete block doors? Are we going to move to do the thing we've always done, which is build federated protocols, things like OIDC, things like, you know, TLS? Those things operated, enabled like a broad web, enabled a lot of commerce to occur, enable a lot of information to flow, enabled all of us to have jobs in a way that because we could be inventive. And so the question I actually asked the broad industry is okay this stuff's coming. Which version of the world do we want one way or the other?
</details>

>> 是的。不过我想补充一点，我认为挺有意思的是，比方说这一切进展得都很完美，我们有了替人买东西的 Agent，大家也都挺满意的。我认为最终会发生的是，我们会开始意识到，我们还有另外一部分必须开始着手处理，那就是人本身。因此我认为，当开始涉及到意图时，你会获得所谓的心理所有权。这意味着我现在实际上在人类与那个 Agent 的结果之间建立了联系。而当你只是把它断开，或者你在声明中把它连上一个 ooth scope 之类的东西，让它有点像变魔术一样，然后你并不真正清楚到底发生了什么。所以我认为，有了意图，在事情确实出错时，人类会更容易承担责任。而且我认为，当你在谈论转移真金白银或类似的事情时，你最终希望让人来负责。我想很多人可能都见过 1979 年那份 IBM 手册。上面写着，诸如此类的，所以那张照片我认为非常真实，在于我们不能让机器来负责，对吧，我们必须让人与它联系起来，而我认为意图就是那个纽带。

<details><summary>Original English</summary>
>> Yeah. I add though I think um it's interesting that let's say this all goes perfect and we've got you know agents buying stuff and everybody's kind of happy. What I think will end up happening is we'll start realizing that we have another piece that we have to start working on which is the human itself. And so one of the things I think when you start having intents being involved is you get what's called psychological ownership. Meaning I actually now have a linkage between the human and the outcome of that agent. when you're just kind of, you know, disconnecting it or you you connect it up an ooth scope or something like that in a claim and let it's kind of magic and then you don't really know what's going on. And so I think it'll with intention it'll be easier for a human to take accountability when things do go wrong. And I think when you're talking about real money being transferred or things like that, you want to have that human ultimately accountable. I think many people have probably seen the uh 1979 IBM manual. It says uh you know and so like that that photo I think is very true in that we can't have the machines be accountable right we're going to have to have the humans link to it and intention I think is that link
</details>

>> 没错，然后意图的另一个词是动机，就像我们昨晚聊到的那样，能够追究某人的责任，无论是一个人还是一个 Agent，我认为这真的非常重要。而且我认为意图也能对此有所帮助，能够理解为什么会出错，是用户怀有恶意，还是 Agent 怀有恶意。然后利用那个意图来做出应对。对于你们各位来说，你们是如何看待意图提供这种好处，以及针对可能怀有恶意的用户或 Agent 做出应对的能力的？

<details><summary>Original English</summary>
>> yes and then yeah another word for intent is motive like we're were talking about last night um and that ability to hold someone accountable whether it's a person or an agent I think is really important and I think intent can also help with that be able to understand why did this go wrong was it the user's um you know the user was maligned the agent was maligned. Um, and then using that intent to be able to respond. Um, for each of you, how are you seeing intent provide that benefit and the ability to respond to potentially a maligned user or agent?
</details>

### 诊断、取证与爆炸半径

>> 我想这又回到了我之前提到的关于诊断的问题，对吧？如果你把“意图”这个词换成“动机”，那么你就把“诊断”变成了“取证”，对吧？而且我认为，任何做过调试或者不得不对失控的 AI Agent 进行取证的人都会明白，试图弄清它当时在试图做什么，相比于用户的意图是什么，是非常困难的，对吧。所以让其中的一些信息在系统中传播并且不可篡改等等，会赋予你一些属性，让你能够更迅速地结束调查，对吧。随着这些东西变得更具互操作性，我认为我们将开始看到公司能够更快地确定范围并识别出：这到底是人为错误，还是 Agent 软件错误，或者到底是什么错误，并妥善处理那个爆炸半径。我们在金融系统中看到，对吧，你在进行交易时会有不同的处理方式，比如“好吧，我付了这笔钱，但是金额不对”等等，你有明确的准则来处理这种情况。目前在事情出错时，我们并没有多少这方面的准则，所以我认为随着我们的推进，意图将帮助我们建立这些准则。

<details><summary>Original English</summary>
>> Uh, I think it's going back to what I mentioned before about diagnosing, right? So, the if if you change the word intent to motive, then you change diagnostics to forensics, right? And I think um anybody who's done debugging or had to do forensics of an AI agent gone rogue will know that like trying to figure out what it was trying to do versus what the intention of the user was uh is very hard right um so having some of that information being propagated and immutable through the system etc gives you some properties that allow you to more shortcircuit your investigation right um and as those things become more interoperable I think we're going to start seeing companies be able to more quickly kind of scope and identify well was this human error was this an agent software error is this what was that error and handle that blast radius appropriately. uh we see in the financial system right you have different things when you're doing a transaction around okay I made this payment but it was you know incorrect dollar amount or whatnot you have clear guidelines on how to work with that we don't have a lot of those when things go wrong right now so I think intention will help us build those as we get go forward
</details>

>> 我认为最近的一个事件突出了一个方面，即你在意图上可以拥有良好的意图，但可能仍会采取错误的行动，那就是最近发生的 Resy 事件，其中一个 Instinct Agent 代表用户出去尝试在 resi.com 上预订餐厅。那个 Agent 非常积极，它一小时发出了 200 次 API 调用，最终导致用户的 Resy 账号被封禁。Dick，在这种 Agent 过度使用下游资源但仍然抱有良好意图的情况下，AOTH 预算能如何提供帮助？

<details><summary>Original English</summary>
>> and I think one area where a recent incident kind of highlights uh where intent um you can have like good intent but still take potentially the wrong action is the resi incident um that happened recently where an Instinct agent went out on behalf of a user and tried to book a restaurant reservation on resi.com. Um that agent was very eager. It made 200 API calls an hour and it ended up getting the user's resi account banned. Um Dick, how can AOTH budgets help in the case where an agent like that is using way too much of a downstream resource, but it still has good intent?
</details>

### Agent 预算与速率限制

>> 是的。嗯，这是另一个说明如今在 Agent 世界中软件完全不同的例子，对吧？当它是预先确定的软件时，如果你调用了 200 次，那是个 bug，你会去修复它。而现在，Agent 会想：“好吧，我就一直尝试，直到成功。”我们在试验并与人们一起使用 AOTH 时看到了这一点，我们意识到，确实存在一个大问题，就是 Agent 学会了某些东西后，它们就会滥用系统，而它们并不认为这是滥用。它们根本不知道有什么不同，没有任何信号告诉它们“哦，我只应该使用这么多东西”。因此我们添加了预算的概念，不仅给 Agent 一个有时间限制的 Token 来限制它们执行特定操作的时长，还给出了它们能使用多少资源的预算。因此，它们一直拥有访问权限，直到 Token 过期，或者它们耗尽了预算。这样一来，当它们返回并且耗尽了所有预算时，在监管层面你可以去决定：我是否应该给这个 Agent 更多预算？这与传统的速率限制不同，后者只是直接切断，然后就变成了“那接下来该怎么办”，对吧，而且它不知道“为什么我会被切断”或类似的事情；而在预算机制中，会持续向 Agent 反馈消耗了多少预算，它对拥有多少预算是有概念的，所以现在它可以在预算范围内运行，对吧，就像一个人会做的那样：“哦，这个资源是稀缺的，我要注意我用了多少。”

<details><summary>Original English</summary>
>> Yeah. Well, this is another example about how just software is completely different now in the agentic world, right? When it was predetermined software, you know, that was a bug if you called 200 times and you would fix it. Um, where now, well, the agent's like, well, I'll just keep trying until I win. Um and so we saw that as we were you know experimenting working with people with AOTH and we realized yeah there's a big problem that agents will learn something and they'll just uh abuse the system from they don't think it's of abuse. They don't know any different. There's been no signal to tell them that oh I should only use this amount of stuff. And so we added the concept of budgets where not only do you give a token to the agent that's timelmited as to how long can they do a particular action but also a budget of how much resource they can do. And so they have access until the the tokens either expired or they've exhausted the budget. And so that way when they come back and you know they've exhausted all the budget the supervision you can go and decide should I give more budget to this agent or not as opposed to traditional rate limiting which just cuts it off and then like then what do you do right and it doesn't know well why did I get cut off or anything like that where in budget there's continual feedback to the agent about how much budget was consumed has an idea about how much budget it has and so now it can operate within a budget right like a person would do about oh this resource is scarce I'm going to be careful about how much I use this
</details>

### 大脑与双手架构

>> 那么，“大脑与双手”架构概念在这里是如何发挥作用，让我们能够在预算接近耗尽或已经耗尽时……访问权限与凭证独立于 Agent 和模型本身这种大脑与双手的解耦，如何帮助我们能够阻止 Agent 过度使用下游资源，因为预算快用完了，那么也许我们就不行使给它发放另一个凭证的能力，举个例子？

<details><summary>Original English</summary>
>> then how does the brains versus the hands architecture concept come into play here to allow us to okay when a maj budget is close to being fully reached or is reached um how can the brain and hand separation of of access and the credentials being separate from the agent in the model itself help us to be able to stop an agent from using too much of a downstream resource cuz it's getting close then Maybe we don't exercise uh the ability to give it another credential for example.
</details>

>> 额，抱歉我没太听清，这里的回音太严重了。所以……

<details><summary>Original English</summary>
>> Uh sorry I didn't quite follow the echo in here is horrible. So
</details>

>> 没事，这是问大家的，但基本上就是说，业内正在趋同的这种“大脑与双手”架构中，我们基本上把凭证和访问权限与 Agent 本身隔离开来。因此，现在的 Agent 不拥有宽泛的长期访问权限。没有 API Key，我知道这也是 AOTH 的一个好处，AOF 允许 Agent 在没有 API Key 的情况下运行。在 Resy 事件的背景下，这有什么帮助……

<details><summary>Original English</summary>
>> no worries that's for anyone but basically like so with the brains in the hands architecture that we're converging on in an industry. We're basically keeping the credentials and the access from an agent separate from the agent itself. So there's no broadstanding access that an agent has today. No API keys which I know is a benefit of AOTH that AOF allows agents to run without API keys. How is that helpful in the context of the resi incident
</details>

>> 当你拥有对它的访问权限时？抱歉，我还是没听懂。

<details><summary>Original English</summary>
>> the when you've got the access to it? Um sorry I still don't understand.
</details>

>> 好的，我可以插一句。好的，多谢。

<details><summary>Original English</summary>
>> Yeah I can jump in. Yeah thanks.
</details>

>> 我懂你意思了，Dick。大致来说，我认为如果我们回顾一个我一直记在脑海里的事件，比如 Pocket OS，我在磁盘上找到了一个随机密钥，对吧？显然 Agent 是高度目标导向的。所以这个问题的核心就是：好吧，如果我们给这些 Agent 大脑（也就是模型和 LLM），并且你有这些双手（也就是你把它们放在一个沙箱里，工具就在沙箱内部），这里沙箱的基本理念就是，你可以控制里面的东西，所以它实际上无法获取 API 访问权限；然后如果你在沙箱外部设有一个出口代理，那就是你可以设定授权边界的地方。这样不仅有助于在系统之间进行转换，对吧？也就是 Athos 可以在那里存在并与外界通信或进行终结，而且还意味着你有能力在出口代理边界处应用授权。因此我认为在核心层面，这个模型——也就是 Anthropic、OpenAI 以及许多其他实验室如今正在采用的主流模型——是一个既能让我们拥有我们想要的东西（即如何让这些东西去试验、尝试、做傻事，这是核心价值），同时又拥有一个确定性层的模型

<details><summary>Original English</summary>
>> I got I got you dick. So like broadly speaking look I think if we look back at an incident that I just keep in the top of my mind is like pocket OS where I found like a random key on on a disc, right? Like obviously agents are deeply goal seeking. So the core of the the core of the the question is like okay well if we give these like agents the brain which is the model and the LLM and you have these hands which is you kind of give them put them in a sandbox and inside the sandbox the tools um like the funal idea of the sandbox here that that's all that is that okay there's you can control what's inside of it so it can't actually like get API access and then if you have an egress proxy outside the sandbox that's where you get to have your authorization boundary and so not only does it help do translation between systems right? Which is like that's where athos can exist and talk to the outside world or do termination but also means that like the agent you have like a ability to apply authorization at the egress proxy boundary and so I think at the core of it that model which is the predominant model that entropic and openi and many other labs are pursuing today is is the model that allows us to both do both have the things we want which is how do we have these things experiment and try stuff out and do silly things which is the core value while also having a deterministic layer
</details>

<!-- chunk 5/7 -->

在它外部，能够实现比如身份验证以及我们在协议中想要的所有其他组件。

<details><summary>Original English</summary>
outside

 of

 it

 that

 can

 implement

 things





like

 aoth

 and

 all

 the

 other

 components





we

 want

 in

 our

 protocols.
</details>

>> 我认为这种解耦是很有价值的，对吧？回到刚才提到的取证以及能够把事物区分开来，但我确实认为我们仍然有很多东西需要学习，那就是这不仅仅是一个大脑，对吧？实际上很容易把你的智能体循环构建成把大脑放在循环内部，而不是放在循环外部。对吧？例如，你知道，那些利用记忆系统的人。嗯，他们放入了一些记忆和上下文，这些内容从现在起被用于随后的每一个智能体，这就使得该智能体产生偏见，去做出指示手（在这种情况下）去做不该做的事情的决定。所以，我认为我们在这里讨论得不够充分的一点就是有害组合，对吧？嗯，所以当你确实把手和大脑等等分离开来时，你实际上可以改变哪些手是可用的，对吧？所以，你知道我见过的非常成功的例子就是根据具体的大脑以及它在做什么来动态移除工具。比如我们之前给出的读取电子邮件的例子。嗯，没有任何规定说如果他们要去写一封电子邮件，我就在写邮件工具完成且你知道任务完成之前，禁用所有网络搜索工具调用或任何其他外部出站能力工具调用（在互联网方面），然后我再重新启用它们，对吧？所以，嗯，我认为我们必须、我们将开始在这些不同的概念中融入越来越多的工程化设计，它们目前仍然复杂，仍然在发展，仍然处于萌芽状态，但我认为这比我们今天拥有的东西做出了更好的分离。

<details><summary>Original English</summary>
>> I

 think

 the

 decoupling

 is

 valuable,





right?

 Going

 back

 to

 mentioned

 with





forensics

 and

 be

 able

 to

 separate





things,

 but

 I

 do

 think

 that

 we

 still





have a

 lot

 to

 learn

 on

 it

 isn't

 just

 one





brain,

 right?

 And

 it's

 very

 easy





actually

 to

 build

 your

 agent

 loop

 where





you

 put

 the

 brain

 in

 the

 loop

 rather





than

 outside

 the

 loop.

 Right?

 So,





example

 of

 this

 would

 be,

 you

 know,





people

 that

 are

 leveraging

 memory





systems.

 um

 they

 put

 in

 some

 memory

 and





some

 context

 that

 is

 now

 used

 going





forward

 for

 every

 agent

 that

 is

 biasing





that

 agent

 to

 make

 a

 decision

 to

 tell





the

 hands

 in

 this

 case

 to

 go

 do





something

 it

 shouldn't

 do

 and

 so

 one

 of





the

 things

 that

 I

 think

 we

 don't

 talk





about

 enough

 here

 is

 toxic

 combinations





right

 um

 and

 so

 when

 you

 do

 separate

 the





hands

 and

 the

 brain

 and

 whatnot

 you

 can





actually

 change

 up

 you

 know

 what

 hands





are

 available

 right

 so

 the

 example

 that





you

 know

 I've

 seen

 be

 very

 successful

 is





the

 removal

 of

 tools

 dynamically

 based





on

 that

 actual

 brain

 and

 what

 it's

 doing





so

 the

 earlier

 example

 we

 gave

 of





reading

 an

 email.

 Um

 there's

 nothing





that

 says

 that

 oh

 if

 they're

 going to

 go





write

 an

 email

 I'm

 going

 to

 disable

 all





you

 know

 web

 search

 tool

 calls

 or

 any





other

 external

 egress

 capability

 tool





call

 ww

 wise

 until

 the

 right

 email

 tool





has

 been

 complete

 and

 that

 you

 know





mission

 has

 been

 done

 then

 I

 can





reenable

 them

 right

 and

 so

 um

 I

 think





that

 we

 have

 to

 we're

 going

 to

 start





becoming

 more

 and

 more

 uh

 engineering

 in





these

 different

 kind

 of

 concepts

 that

 um





they

 are

 still

 complicated

 they're

 still





growing

 and

 still

 nent

 but

 I

 think

 it's





a

 better

 separation

 of

 what

 we

 have





today.
</details>

是的，我们正在谈论的这些事情——你知道，看起来像是极客式的操作问题——实际上汇聚回到了真正的智能体工程问题。也就是如果你真正理解你在做什么，你知道最大的抱怨之一（现在少一些了，但之前对 MCP 最大的抱怨之一）就是上下文膨胀，尤其是当我们拥有较小的上下文窗口时，对吧？但意图系统可以确保在合适的时间给智能体赋予合适的能力，这样它们就不会把大量时间花在不该做的事情上，对吧？这实际上有助于引导它们走向目标状态，并有助于把它们放在一条更平坦的道路上。因此，意图不仅能解锁很多安全方面的东西，意图还将导致我们消耗更少的 token，因为智能体花在非正确路径上的时间会减少，或者它会直接达到说“嘿，我就是做不到”的节点。所以我们对这个时代的了解是，其中很大一部分在于把智能体推向正确的方向，并确保你无法去做错误的事情，这就是你获得想要的结果的方式。

<details><summary>Original English</summary>
Yeah,

 and

 this

 is

 how

 these





things

 we're

 talking

 about

 which

 you





know

 seemed

 like

 geeky

 O

 problems





actually

 then

 merge

 back

 up

 to

 like

 real





agent

 engineering

 problems

 which

 is

 if





you

 actually

 understand

 what

 you're





doing

 you

 know

 one

 of the

 biggest





complaints

 less

 now

 but

 one

 of the





biggest

 complaints

 with

 MCP

 was

 context





bloat

 like

 especially

 when

 we

 had





smaller

 context

 windows

 right

 but

 intent





systems

 can

 ensure

 that

 the

 right





capabilities

 are

 given

 to

 the

 agent

 at





the

 right

 time

 so

 they

 don't

 spend

 a





bunch

 of

 time

 doing

 things

 they





shouldn't

 be

 doing

 right

 they

 actually





helps

 them

 navigate

 towards

 the

 goal





state

 and

 helps

 them

 put

 them

 on

 a

 more





of

 a

 paved

 path

 so

 intent

 like

 not

 only





unlocks

 like

 a

 bunch

 of

 security

 stuff.





Intent

 also

 will

 result

 in

 us

 spending





less

 tokens

 because

 the

 agent

 will

 spend





time

 doing

 less

 things

 that

 aren't

 the





right

 pathway

 or

 it'll

 come

 up

 to

 the





point

 say,

 "Hey,

 I

 just

 can't

 do

 it."





And

 so

 what

 we

 know

 about

 this

 era

 is

 so





much

 of

 it

 is

 about

 nudging

 the

 agent

 in





the

 right

 direction

 and

 ensuring

 you





can't

 do

 the

 wrong

 thing

 and

 that's

 how





you

 get

 the

 outcome

 you

 want.
</details>

### 生产环境中的动态授权与软件工厂

>> Davis，你是如何看待基于意图作为生产级智能体更大战略的一部分？我知道当涉及到在生产环境中构建、部署和运行智能体时，团队应该考虑许多不同的成果，例如发现正在运行的内容、智能体的能力是什么、验证输入和输出的能力、像我们讨论过的那样约束智能体，以及使用出站代理和不同的网络规则。嗯，所有这些是如何配合发挥作用的，如今企业内部有哪些行之有效的方法能真正将智能体交付到生产环境？

<details><summary>Original English</summary>
>> Davis,

 how

 are

 you

 seeing

 intentbased

 as





part

 of

 a

 larger

 strategy

 for

 production





agents?

 I

 know

 when

 it

 comes

 to





building,

 deploying,

 and

 operating





agents

 in

 production,

 there's

 many





different

 outcomes

 teams

 should

 be





thinking

 about

 such

 as

 discovering





what's

 running,

 what

 agents

 capabilities





are,

 the

 ability

 to

 validate

 inputs

 and





outputs,

 constraining

 an

 agent

 like

 we





talked

 about,

 and

 using

 the

 egress

 proxy





and

 different

 networking

 rules.

 Um,

 how





does

 all

 of

 this

 fit

 into

 play

 and





what's

 working

 inside

 enterprises

 today





to

 really

 be

 able

 to

 ship

 agents

 to





production?
</details>

是的，我……我认为我们终于——这正在帮助把对话从身份验证转向授权，而且真正转向我们如何做动态授权？我如何验证该授权？我如何在适当的时候引入人在回路（human-in-the-loop）？因为我同意 Dick 早些时候所说的，在很多方面人在回路有点像一种反模式，对吧？嗯，因为他们会产生疲劳等等。但是你需要有一种方法在重要的时候把他们引入进来。这些在以前都不是工程讨论，对吧？现在它们实际上成为了工程对话的一部分，工程师正参与到授权过程中。他们不再只是说：“哦，我已经获得了访问权限。我可以开始了。”所以这实际上改变了我们看待威胁建模的方式。它改变了我们看待整体应用程序完整攻击面的方式。嗯，因此我认为你现在正把这种授权模型视作另一类工具集，你可以用它来不仅减少安全问题，而且彻底降低你智能体的错误率，对吧？我的意思是，当智能体能做的事情变少时，它就会做出更好的决策，对吧？所以从根本上说，我们已经看到了真实世界的案例，其中智能体循环变得更好、更快、更强大，因为你实际上投入了时间去了解他们试图获取的意图是什么，他们试图完成的任务是什么。然后最后一件事是，它把人们聚集在了一起，也就是说我们现在有了不同的各类人员，安全团队、应用团队。他们现在能够进行使用同一种语言的对话了。很多时候当涉及到身份时，那完全是另一种语言，对吧？嗯，那就像是“别挡我的路。我必须去做什么才能拿到我的令牌，然后我就可以继续前进了”。现在他们看到你实际上可以把这些东西配对起来，并利用这种能力来推动实现你智能体实际结果的效率。

<details><summary>Original English</summary>
Yeah,

 I

 I

 think

 we're





finally

 it's

 helping

 move

 the

 kind

 of





conversation

 from

 authentication

 to





authorization

 and

 really

 like

 how

 do

 we





do

 dynamic

 authorization?

 How

 do

 I





validate

 that

 authorization?

 How

 do

 I





have

 the

 human

 in

 the

 loop

 at

 the

 right





time?

 Because

 I

 agree

 with

 what

 Dick

 was





saying

 earlier

 that

 the

 human

 in

 the





loop

 is

 somewhat

 of

 an

 anti-attern

 in





many

 ways,

 right?

 Um

 because

 they

 can





get

 fatigue

 etc.

 But

 you

 need

 to

 have

 a





way

 to

 bring

 them

 in

 when

 it's





important.

 Those

 were

 not

 engineering





discussions

 before,

 right?

 Now

 they're





actually

 part

 of

 the

 engineering





conversation

 where

 engineers

 are

 being





involved

 in

 the

 authorization

 process.





They're

 not

 just

 saying,

 "Oh,

 I've

 got





my

 access.

 I'm

 good

 to

 go."

 So

 that





actually

 changes

 the

 way

 we're

 seeing





threat

 models

 done.

 It

 changes

 the

 way





we're

 seeing

 the

 full

 attack

 surface

 of





applications

 in

 general.

 Um

 and

 so

 I





think

 you're

 now

 looking

 at

 this





authorization

 model

 as

 a

 another

 kind

 of





set

 of

 tools

 that

 you

 can

 use

 to

 reduce





not

 just

 um

 security

 issues,

 but

 flatout





error

 rates

 of

 your

 agent,

 right?

 Like

 I





mean

 when

 you

 have

 less

 things

 the

 agent





can

 do

 it

 makes

 better

 decisions

 right





and

 so

 fundamentally

 we've

 seen

 you

 know





real

 world

 cases

 where

 the

 agent

 loop

 is





just

 better

 faster

 stronger

 because





you've

 actually

 spent

 the

 time

 on





knowing

 what

 is

 the

 intent

 they're





trying

 to

 get

 what's

 the

 mission

 that





they're

 trying

 to

 accomplish.

 And

 then





last

 thing

 is

 it

 brings

 the

 people





together

 in

 terms

 of

 we

 now

 have

 other





different

 people,

 the

 security

 team,

 the





application

 team.

 They're

 now

 able

 to





have

 a

 conversation

 that

 they're

 using





the

 same

 language.

 And

 a

 lot

 of

 times





when

 it

 came

 to

 identity,

 it

 was

 a





completely

 different

 language,

 right?

 Um





and

 it

 was

 just

 like

 get

 out

 of

 my

 way.





What

 do

 I

 have

 to

 go

 do

 to

 go

 ahead

 and





get

 my,

 you

 know,

 token

 and

 I

 can

 go





forward.

 Now

 they're

 seeing

 that

 you

 can





actually

 pair

 these

 things

 and

 leverage





that

 capability

 um

 to

 drive,

 you

 know,





efficiency

 of

 your

 actual

 agents





outcome.
</details>

>> 这说得通。Ian，你是如何将这些概念应用到软件工厂中的？我知道今天你在安全软件工厂上发布了一个参考架构。你是如何将运行时授权、约束智能体以及所有这些概念应用到那上面的？

<details><summary>Original English</summary>
>> That

 makes

 sense.

 Ian,

 how

 are

 you





applying

 these

 concepts

 to

 software





factories?

 I

 know

 today

 you

 released

 a





reference

 architecture

 on

 the

 secure





software

 factory.

 How

 are

 you

 applying





the

 concepts

 of

 runtime

 authorization





constraining

 agents

 and

 all

 of

 that

 to





that?
</details>

>> 是的，我认为，我们在 agentbaseline.org 上刚发布了一个参考架构。嗯，我们谈到了工厂的三种不同级别。一个是人类驱动的，一个是工作流驱动的，还有一个是这种智能体驱动的，这基本上就是我们大家都想达到的状态，也就是在所有时间点上都由智能体驱动。运行时授权是更大生态系统的核心组件。它实际上使工厂能够被指引方向并做正确的事情，并且还能获得对正确部分的访问权限。而且它非常……它看起来不同于你以前用过的像凭据管理器（secret manager）这类东西，因为与前几代管理确定性软件相比，它所做的决策非常不同。但它是使整个系统运作的核心组件，比如什么时候把人引入回路，什么时候哪些智能体可以将哪些工作移交给哪些其他智能体。你知道，我们如何才能拥有一个能够访问生产系统并执行自动修补的智能体。嗯，这些都是关于我们如何真正规模化解决软件问题的根本问题。眼下我们所处的位置是，我们能够生成的软件比以往任何时候都多。但是我们从来没有真正……但我们在将其投入生产环境、确保其正常工作方面存在着彻底的瓶颈，而这就是下一个阶段：你究竟如何从仅仅使用语言模型来生成文本和软件，毕业过渡到真正使其有能力部署到生产环境中、进行迭代，并迅速使其达到稳定状态，然后在出现情况时做出响应。

<details><summary>Original English</summary>
>> Yeah,

 I

 think

 like

 so

 there

 is

 a

 a





reference

 architecture

 we

 just

 published





on

 agentbaseline.org.





Um

 we

 talked

 about

 three

 different





levels

 of

 of

 factory.

 one

 being

 like

 a





human-driven

 one,

 one

 being

 a

 workflow





driven

 one,

 one

 being

 like

 this

 agentic





driven

 one,

 which

 is

 like

 the

 thing

 we





all

 basically

 want

 to

 get

 to,

 which

 is





like

 it's

 it's

 driven

 by

 agents

 at

 all





points

 in

 time.

 The

 runtime





authorization

 is

 a

 core

 component

 of

 a





larger

 ecosystem.

 It

 actually

 enables





the

 the

 factory

 to

 like

 be

 able

 to

 be





pointed

 in

 a

 direction

 and

 do

 the

 right





thing

 and

 also

 get

 access

 to the

 right





piece.

 And

 it's

 very

 it

 looks

 different





than

 previous

 things

 that

 you

 would

 have





used

 like

 a

 secret

 manager

 because

 it's





making

 very

 different

 decisions

 than





previous

 generations

 head

 for

 managing





deterministic

 software.

 But

 it

 is

 a

 core





component

 of

 enabling

 the

 entire

 thing





to

 work

 like

 when

 to

 bring

 someone

 into





the

 loop

 when

 what

 agents

 can

 pass

 what





work

 off

 to

 what

 other

 agents.

 You

 know





how

 can

 we

 have

 an

 agent

 that

 can

 have





access

 to

 production

 systems

 and

 do

 an





auto

 patch.

 Um

 these

 are

 fundamental





questions

 of

 like

 how

 do

 we

 actually





solve

 at

 scale

 software.

 Right

 now

 we're





in

 a

 position

 where

 like

 we've

 never





been

 able

 to

 generate

 more

 software.

 uh





but

 we

 never

 actually

 but

 we

 have

 a





complete

 bottleneck

 in

 getting

 into





production

 ensuring

 it

 works

 and

 that's





the

 the

 next

 phase

 is

 like

 how

 do

 you





actually

 graduate

 from

 just

 using

 LM

 to





generate

 text

 and

 software

 to

 actually





making

 it

 capable

 of

 deploying

 it

 into





production

 iterating

 on

 it

 and

 getting





it

 to

 a

 stable

 state

 quickly

 and

 then





responding

 to

 instances

 they

 arise
</details>

>> Davis，在你和我做的一期播客中，我们谈到了网络安全可以从机器人学中吸取一些经验。嗯，在机器人学中存在这样一个概念，也许当一个机器人抬起它的手臂时。它会思考：我抬起手臂安全吗？我应该、我被允许这么做吗？但它也会审视外部环境并说：“发生了什么变化？我现在抬起手臂还安全吗？”嗯，当我们思考运行时授权时，除了单纯的意图之外，这些决策还需要考虑哪些上下文？

<details><summary>Original English</summary>
>> Davis

 on

 a

 podcast

 you

 did

 with

 me

 we





talked

 about

 how

 cyber

 security

 has





something

 to

 learn

 from

 robotics

 um

 in





robotics

 there's

 this

 concept

 when

 maybe





a

 robot

 raises

 its

 arm

 arm.

 It

 thinks

 is





it

 safe

 for

 me

 to

 raise

 my

 arm?

 Should

 I





am

 I

 allowed

 to

 do

 that?

 But

 it

 also





looks

 at

 its

 external

 environment

 and





says,

 "What

 has

 changed?

 Is

 it

 is

 it





still

 safe

 for

 me

 to

 raise

 my

 arm?"

 Um,





when

 we

 think

 about

 runtime





authorizations,

 what

 do

 those

 decisions





need

 to

 take

 into

 context

 beyond

 just





intent?
</details>

>> 是的，我认为拥有这样一个模型可以让我们在决策中加入更多的传感器。所以回到机器人的例子，你知道手臂向上或向下移动，嗯，任何外部因素，可能是有没有其他物体靠近它，对吧？嗯，可能是温度，可能是“嗯，我是不是在移动，我不想在我的——你知道——机器人的其余部分在移动时移动我的手臂”等等，所以它通常会观察所有不同类型的事物，这些都不是

<details><summary>Original English</summary>
>> Yeah,

 I

 think

 um

 having

 a

 model

 like





this

 allows

 us

 to

 add

 in

 more

 sensors





into

 our

 decision.

 So

 the

 robotics





example

 of

 you

 know

 an

 arm

 moving

 up

 or





down

 um

 any

 of

 the

 external

 factors

 it





could

 be

 are

 there

 other

 objects

 near

 it





right

 um

 it

 could

 be

 temperature

 it





could

 be

 well

 am

 I

 moving

 and

 I'm

 don't





want

 to

 move

 my

 arm

 while

 my

 you

 know





the

 the

 rest

 of

 the

 robot's

 moving

 etc





so

 it's

 usually

 looking

 at

 all

 different





types

 of

 things

 none

 of

 those

 are
</details>

<!-- chunk 6/7 -->

### 授权机制与环境上下文

确定性的，它们全都是概率性的。所以存在一系列选项，而它会根据那一时刻的所有传感器数据来选择最佳选项。如今大多数组织中的授权决策都是单一的二元决策，对吧？这在未来根本行不通，对吧？因此，需要能够将用户试图做的事情的意图，与用户执行该操作时所处的生态系统结合起来。那可能是他们发起操作的地点、时间，但也可能是更高级的事情，例如：我现在是否应该允许这位管理员使用 Firefox 访问这台服务器，尤其是在这台服务器存在高危漏洞且他们的系统尚未打补丁的情况下？对吧？

<details><summary>Original English</summary>
deterministic they're all probabilistic so there's a range of options and it picks the best option based on all of those sensor data at one time most authorization decisions in organizations today are single binary decision, right? And that just doesn't work in the future, right? So, being able to pair the intent of what a user is trying to do with the ecosystem that the user is doing it in. That could be where they're doing it from, time of day, but it could be even more advanced things like, for example, should I let, you know, this administrator use Firefox to access this server right now when this server has, you know, high-risisk vulnerabilities and their system hasn't been patched to. Right?
</details>

现在突然之间，你为它周围的环境引入了多得多的上下文，而且同样，这可以通过不同的团队来实现，但更重要的是通过传感器。我认为我们大家都大致看到了可观测性本身的价值。设想一下，从 Otel（OpenTelemetry）等角度来看，能够在 span 级别拥有这种类型的上下文，对吧，你在查看一个 trace，里面有一个 span，而你不仅知道当时用户的意图是什么，还切切实实知道当时应用程序外部的环境是什么。这能让你以一种截然不同的方式来排查诊断问题。因此我认为，如果我们能引入其中的一些概念，我们就能得到生存时间更短的授权决策，这些决策所拥有的上下文远不止用户的意图，还会包括其周围环境的状态。

<details><summary>Original English</summary>
Now all of a sudden you're bringing in a lot more context into the environment around it and again um that can be through different teams but more importantly through sensors and I think we've all kind of seen the value of observability in general. Imagine being able to have this type of context at the span level from an Otel perspective or something right you're looking at a trace you've got a span and you actually know what the environment was outside your application at that time as well as what the user's intention was. Um that allows you to diagnose things in a completely different way. Um, and so I think if we can bring in some of those concepts, we'll get shorter time, shorter shorter to live, you know, um, authorization decisions that have much more context than even just a user's intent. It'll be the state of the environment around it.
</details>

### 审计日志与追责归属

>> 这很有道理。展望未来，当我们评估基于意图的授权在我们的环境中是否有效时，一个很自然的观察切入点就是智能体行为的日志。被拒绝了什么，被允许了什么。Ian，为什么将你的审计日志与智能体本身分离开来（也就是脱离其控制）是至关重要的？

<details><summary>Original English</summary>
>> That makes sense. And forward looking as we evaluate whether intentbased authorization is working in our environments, one natural place to look will be a log of the agents actions. Um, what was denied, what was allowed. Um, Ian, why is it important to have your auto log separate from the agent itself, meaning outside of its control?
</details>

>> 是的，我认为这也可以归结为：为什么执行点必须位于智能体主要的手和大脑之外，对吧？你无法信任这个东西。因此，在 Hugging Face 事件中，它包含几个不同的组成部分。我的意思是，一方面显然是利用了我们之前在 Squid、Squid 代理中不知道的漏洞，但更重要的是，你对当时发生的事情没有任何可观测性或监控。因此，这个东西能够通过该漏洞进入公开互联网，却没有任何地方记录这个智能体正在采取的各种行动并供他们监控。所以，不论我们是对推向互联网的网络流量施加一个该智能体无法篡改的执行点，还是在漏洞出现时逐一解决它们——这个 Hugging Face 的案例有点特殊——我们仍然切实需要记录到底是谁为了什么目的让这个智能体做了什么事情，以及那个目的是否依然成立？因为归根结底，我们在智能体上所做的归根结底是一个责任归属问题。这就是为什么我其实并不认为我们需要围绕智能体出台更多监管规定。我们所需要的只是让我们既有的关于责任归属的法律得到执行和处理，那就是：如果我雇佣一个智能体执行某项操作，如果该操作造成了损害，谁来承担责任？正是雇佣它的人，这个人可以是一个组织，或者一个人，或者是将某项操作委托给某个事物的人。这就是我们必须处理的终极问题，当然，你必须有能力回答那个问题，也就是“到底是谁干的”，而这正是防篡改审计日志的用武之地。

<details><summary>Original English</summary>
>> Yeah, I think this comes back to also just like why the enforcement point has to be outside the like primary like hands and brains of of an agent, right? You can't trust this thing. And so, in the hugging phase incident, it had a couple different components of it. I mean, one obviously abused a vulnerability we didn't know about in Squid in Squid proxy, but more importantly, you didn't have any observability or monitoring about what was going on. And so this thing was able to go in the open internet through this vulnerability and there was no like place at which recorded the different actions that this agent was taking and for them to monitor. And so independent of like whether we're applying like a you know enforcement point to network traffic that's pushing on the internet that it's outreach of the agent to tamper with or we're using you know solving vulnerabilities as they pop up. You know this this hugging face one is a little unique. Um we still need to actually have a record of like who told this agent to do what thing for what purpose and is that still true? Um because ultimately at the end of the day what we're doing with agents is we is is a liability question. And so this is why I actually don't think we need more regulation around agents. What we just need is our pre-existing laws around liability to be held to be dealt with which is if I employ an agent do some action who is liable if that action causes damage right it is the person who employs it which could be an organization or a person or someone that delegated some action to something that is like that's the final question we have to deal with and then of course you have to ability to answer that question which is well who did it which is where the tamper resistant autolog comes from
</details>

### 末日概率与安全预期

>> 太好了。最后作为收尾，我想问大家一个有趣的问题。有一个概念叫末日概率（probability of doom）或 p(doom)，AI 悲观论者（AI doomers）认为 AI 智能体将释放各种破坏，或是成为人类的毁灭之源；而 AI 乐观论者则认为不，这真正有望帮助我们，不是真正的威胁。对于台上的每一位，你们对此有什么看法？基于意图的运行时授权，以及我们谈论的其他事情，比如约束智能体、验证输入和输出、针对生产环境智能体的整体策略——这些足以拯救我们吗？p(doom) 是真实的，还是言过其实了？

<details><summary>Original English</summary>
>> perfect and then to wrap up I wanted to ask you all a fun question. So there's a concept of the probability of doom or pdoom where the uh AI doomers are saying that AI agents are going to um release all sorts of havoc or be like the ruin to humanity whereas the AI optimists are like no this is really you know poised to help us it's not a genuine threat. Um for each of you on the panel, what is your take on this? Is you know runtime authorization based on intent and the other things we talk about like constraining agents, validating inputs, outputs, a holistic strategy for production agents. Is that enough to save us? Is Poom real or is it not worth the hype?
</details>

>> 你先从那里开始吧。

<details><summary>Original English</summary>
>> You get to start there.
</details>

>> 噢，我先来。

<details><summary>Original English</summary>
>> Oh, I did.
</details>

>> 你脸上露出了耐人寻味的表情。

[笑声]

<details><summary>Original English</summary>
>> You got that spicy look on your face.

[laughter]
</details>

额，你的部分问题是：智能体是否会接管世界？我认为智能体实现完全自主且不依附于特定组织，这仍然属于科幻小说的范畴，谁知道呢，对吧？那是一种走向。另一种走向是，在一个负责任的组织中建立起正确的管控措施，智能体并不是……我们正在引入和发展足够的工具，以确保在设立了恰当管控措施的负责任组织中不会发生坏事。这就留下了两种可能出现潜在问题的情景：其一是在一个自身管理混乱的组织中，内部威胁可能会跑去释放一个智能体来制造混乱，对吧？因为他们拥有其他人所没有的某种特殊访问权限。另一个、也是我更为担忧的情景是，正如已经表现出来的 Hugging Face 事件，如果你看过他们在 Black Hat 上的演讲，那确实是一声警钟，展示了一种“我们不希望坏事发生，但坏事确实发生了”的局面。那如果是那些想让坏事发生并且拥有这些工具的人呢？我认为那是一个潜在会带来的威胁——我的意思是它必然会发生，并且会引发一些灾难。希望我们已经做好了充分的准备，使它们不至于造成极其毁灭性的后果，但总会发生一些由恶意行为者有意或在某种程度上无意引发的、堪比大规模自然灾害级别的事件，其根源就在于人们在使用这些超级强大的工具时没有负起责任。

<details><summary>Original English</summary>
Uh uh well part of your question is are agents going to take over? And uh I I think agents being fully autonomous and not really tied to a particular organization is still science fiction, you know, so who knows, right? Like that's a that's one direction. Another one is in a responsible organization put in the right controls, agents aren't, you know, we're getting in evolving enough of the tools to make sure that bad things don't happen in a responsible organizations to put in the right controls. And so that leaves two scenarios for where there's going to be a potential problem. One of those is in an organization that isn't got its act together, an insider threat could go and unleash an agent to cause havoc, right? And so they've got some special access that other people have. The other one, the one that I'm more concerned about is, you know, it's been shown, you know, the hugging faces. And if you watch the the talk that they gave at Black Hat, right, that was really a call to arms around, you know, here's a situation where we didn't want a bad thing to happen and a bad thing did happen. What about people that want bad things to happen and have these tools and that I think is a threat that's the one that's potentially going to have I mean it's going to happen and there's going to be some catastrophes. Hopefully, we're prepared enough that those aren't horribly disastrous, but it's going to be, you know, some there's going to be some things that are like massive natural disaster like scale issues caused by malicious actors either kind of intentionally or kind of unintentionally, but it's where people aren't being responsible in their use of these super powerful tools.
</details>

>> 是的，我不一定能给出一个具体的概率，对吧？但我可以说的是，我认为每当工程师的才智投入到解决问题中时，我总是感到有些惊讶和振奋。我认为在我们目前所处的阶段，比如智能体内部的一些新能力等等，我们有真正的工程师、在场的各位同行切切实实地在这个问题上不断迭代，对吧？我们开始看到巨大的进步，在我看来，其中一些即将具备的能力将改变我们的未来。所以对我来说，我完全相信工程师们会在这里找出解决方案。

<details><summary>Original English</summary>
>> Yeah, I can't give necessarily a specific probability, right? But what I uh can say is I think I've always been you know kind of uh surprised and excited when you know ingenuity of engineers gets involved in problem solving and I think where we're at the stage now like some of the new capabilities within agents etc. We have real engineers, folks that are here actually just iterating on the problem, right? We're starting to see just tremendous improvement in the, you know, in my mind, some of the capabilities that'll be available to change what our future can be. And so to me, I have no problem kind of believing the engineers are going to figure out a solution here.
</details>

>> 我的观点也许是最激进的。我的意思是，我不能说它等于零，但我会说世界走向毁灭的概率渐进于零。我认为大多数人的激励机制是继续生存下去。而且归根结底，我们仍然拥有责任追究框架，并且我认为通常来说人类都是好人，所以我们不会专门以毁灭世界为目的。另外我也认为，大体而言，这些智能体到头来……我有一种所谓的激进看法，我说它们其实拔掉电源就行了，但我认为事实确实如此。就像归根结底，它们就是计算机，我们可以拔掉它们的电源。因此大体而言，我并不相信这种争论。我认为它不是真实的。我认为往好处看，我更倾向于认同 Davis 的立场，那就是我们正在非常迅速地迭代。我们正在弄清楚这些东西在哪些地方可行，在哪些地方不可行。而当它们不可行时，它们就会造成损害。这最终就像是社会的抗体，它会说：“嘿，也许我们不应该这么做。”比如这可能是一件坏事。

<details><summary>Original English</summary>
>> I mean, maybe I have the hottest take. I mean, like I can't say it's equal to zero, but I would say it's approaching asmtoically zero. Uh, is the probability the world is going to end. Uh, I think like the incentive structure for most people is to continue. Um and also at the end of the day like we still have liability frameworks and you know I think generally humans are good people so we don't set out to destroy the world specifically. Um I also think like broadly speaking like these agents at the end of I have this sort of hot take I say which is like they can just be unplugged but I think it's just true. It's like at the end of the day like they you can just they're computers we can unplug them. Um and at so broadly speaking I I don't believe in the debate. I I don't think it's real. I think at the at the upside of it, I I kind of believe more more to what Davis's position is is we're iterating very quickly. We're figuring out where these things can work, where they don't. And when they don't work, they create damage. And that's what ultimately like sort of um the antibbody of society is that says, "Hey, maybe we shouldn't do this." Like this is probably a bad thing.
</details>

>> 所以，我成了台上的悲观论者。

<details><summary>Original English</summary>
>> So, I'm the doomer on the on the panel.
</details>

>> 是的。

[笑声]

对于像 Pocket OS 的创始人这样丢失了大量数据的人来说，这很不幸，但对我们其他人来说却很棒，因为我们都在共同学习，而在最后

<details><summary>Original English</summary>
>> Yeah. [laughter] It's unfortunate for, you know, people like the P, you know, the founder of Pocket OS who like lost a bunch of data like but it's great for the rest of us because we all learn together and uh at the end of
</details>

<!-- chunk 7/7 -->

……一天。就像那样会导致人们不做那些没有太大意义的事情，我认为这种情况还会继续下去。

<details><summary>Original English</summary>
 the
 day

like
 that
 results
 in
 people
 not
 doing

things
 that
 don't
 make
 a
 lot
 of
 sense

and
 I
 think
 that
 will
 continue
 to
 be

true.
</details>

>> 有道理。感谢大家今天在这个小组讨论中分享你们的专业知识和宝贵时间，也感谢观众的倾听，我们下次再见。谢谢大家。谢谢，马歇尔。[掌声]

<details><summary>Original English</summary>
>> Makes
 sense.
 Thank
 you
 each
 for
 your

expertise
 and
 your
 time
 here
 on
 this

panel
 today
 and
 thank
 you
 to
 the

audience
 for
 listening
 and
 we'll
 catch

you
 next
 time.
 Thank
 you.
 Thanks,

Marshall.
 [applause]
</details>