---
author: a16z
date: '2026-07-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=cO1f2wOxSH4
speaker: a16z
tags:
  - agentic-workflow
  - model-fine-tuning
  - open-source-vs-closed-source
  - productized-architecture
title: 人工智能智能体驱动的业务入口与开源模型演进
summary: 文章探讨了人工智能智能体作为业务首要入口的角色，以及在企业应用中从前沿闭源模型向微调后的开源模型的迁移路径。核心观点包括：早期使用前沿模型以快速交付价值；随着规模扩大和对延迟的考量，转向需要精细控制的小型、可微调的模型（如开源模型）；最终强调了“产品化思维”和“玻璃盒模式”，即为客户提供高度自主、透明且易于迭代的核心架构，而非不透明的黑盒服务。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 播客预告片段 (Podcast Intro Snippets)

**Speaker A**: AI 智能体（Agent）应该成为你业务的首要入口。无论是主动还是被动地与客户互动，每一次交流都应该由 AI 来处理。

<details>
<summary>Original English</summary>

**Speaker A**: An AI agent should just be the front door of your business. And every interaction, whether it's like reactive or proactive with a customer, should be handled by AI.

</details>

**Speaker B**: 这个叙事主导了 2026 年上半年，那就是 Anthropic、OpenAI 它们是最后的初创公司。它们将接管一切。

<details>
<summary>Original English</summary>

**Speaker B**: This narrative dominated the first half of 2026, which is that Anthropic, OpenAI. They're the last startups. They're going to take over everything.

</details>

**Speaker C**: 即便一旦你拥有了 AGI，智能体仍然需要一个地方来存储工作、从中提取信息并对事物进行推理。我不认为整个软件行业会在任何实质意义上消失。不幸的是，前沿实验室（Frontier Labs），他们确实有小模型，但你无法真正以你想要的方式控制它们。因此，今天我们 90% 的工作流都是在开源模型上运行的……

<details>
<summary>Original English</summary>

**Speaker C**: Even once you have AGI, agents are going to need somewhere to store work and pull information from and reason about things. I don't think software as a whole in any meaningful way is going away. Unfortunately, the Frontier Labs, they do have small models, but you can't really control them in the way that you want. So, today 90% of our workflow is on open source

</details>

**Speaker D**: ……在我们需要它们执行的具体任务上。它们实际上超越了大型、聪明的最先进（SOTA）模型。

<details>
<summary>Original English</summary>

**Speaker D**: on the specific task we want them to do. They actually outperform the large smart state-of-the-art model.

</details>

**Speaker E**: 我们构建的并不是一个擅长做客服的智能体，而是一个遵循业务流程的智能体。

<details>
<summary>Original English</summary>

**Speaker E**: The thing that we built was not an agent that does customer support well, but rather an agent that follows business process. Well,

</details>

**Speaker F**: ……与其让我们必须去写这些标准作业程序（SOPs），它就能直接把所有这些都做了。比方说，如果我们实现了 AGI，模型能做各种我们今天甚至无法想象的事情。那么 Decagon 的护城河是什么？或者说，为什么十年后 Decagon 依然有存在的理由？

<details>
<summary>Original English</summary>

**Speaker F**: instead of us having to write these SOPs, it just does all of that. Let's say like we hit AGI and the models can do all sorts of things we can't even imagine today. What's Decagon's moat and like why does Decagon like 10 years from now still have a right to exist?

</details>

### 开场与开源模型之争 (Welcome & The Open Source Debate)

**Host**: 嘿，大家好，欢迎回到演播室。

<details>
<summary>Original English</summary>

**Host**: Hey guys, welcome back to the studio.

</details>

**Guest**: 感谢邀请我们。

<details>
<summary>Original English</summary>

**Guest**: Thanks for having us.

</details>

**Jesse**: 是的，很高兴见到大家。

<details>
<summary>Original English</summary>

**Jesse**: Yeah, good to see you.

</details>

**Host**: 谢谢你们来到这里。在进入客服领域之前，其实我想稍微拓宽一点话题。Jesse，我打算稍微提一下你最近写的一篇文章，那篇文章传播得很广，因为它正中当下关于开源与闭源模型之争的讨论热点核心。随后，Thinking Machines 和 Llama 3（译注：原转录为 Kimk 3，推断为 Llama 3 等开源模型）——你知道的，一些非常有趣的开源模型紧接着就发布了。围绕着“在人工智能领域，尤其是在企业界，掌握自己的命运意味着什么”，以及“不同用例下的演变是什么样的”，出现了一场非常有趣的辩论。既然这正是当下的热门话题，我们不如就从这里开始吧。

<details>
<summary>Original English</summary>

**Host**: Thank you for being here. Before we get into customer support, um I actually wanted to widen out a bit. Um, and uh, Jesse, I'm going to actually um, mention a piece that you wrote recently that went pretty viral because it's right in the middle of the zeitgeist of conversation right now on open source versus closed source models. then thinking machines um Llama 3 you know some of some very interesting open source models came out sort of right after um and there's this really interesting debate going on around what does it mean to own your destiny when it comes to AI especially in the enterprise um and what does that evolution look like by use case um so actually since that's a pretty live topic right now why don't we start there

</details>

**Jesse**: 听起来不错。为了让大家有更具体的概念，我先来讲讲我们的发展历程。当我们在任何项目中刚起步时，目标仅仅是让东西能跑起来，对吧？所以，当你的目标只是让产品先运转起来时，你当然会直接使用前沿模型（Frontier models），因为你想尽快把产品推向市场并实际交付价值。所以，我们当时使用的是 OpenAI 和 Anthropic 的模型，在那段时间里，它们在模型性能上可以说是你追我赶。

然后，发展到某个阶段，随着我们的规模不断扩大，我们开始与越来越大的公司合作，他们拥有数以百万计的客户。而且我们还推出了我们的语音智能体，对吧？所以“延迟”（latency）成了一个巨大的考量因素。问题不再仅仅是你能不能提供出色的回答，而是你必须非常快速地给出反馈。而降低延迟——同时也要让我们的智能体按照我们想要的方式运行——唯一的方法就是使用更小的模型。当你想要转向较小的模型时，不幸的是，虽然那些前沿实验室确实有小模型，但你无法真正以你想要的方式去控制它们，而且大多数开箱即用的小模型，在我们想让它们执行的任务上表现得并不够好。所以，你必须对它们进行微调（fine-tune），必须去改造它们。

于是，我们就在那时开始关注开源模型了。这大约是一年多以前的事情。而且它效果非常好，因为如果你仔细想想智能体内部的工作机制，对吧？在我们的智能体里，它的工作就是进行对话。因此它需要同时处理很多事情。比如，它要做的第一步可能是：“嗯，这个人正在谈论什么话题？” 或者它可能要做的另一件事是：“哦，这个进来的家伙是不是个想搞破坏的恶意用户？” 它有所有这些需要去执行的任务。而每一个单独的任务，并不需要大模型的全部智能。所以你知道，所有的前沿模型显然都非常聪明，但它们能做一堆截然不同的事情，比如它们会做数学题，也能写代码。但你只需要它们精通那一个特定任务就可以了。

这就是为什么你可以使用一个小模型，如果你对它进行微调，让它在这个特定任务上表现得非常出色，它就能和大模型一样好，甚至更好，对吧？所以这就是我们的第一步。大约一年前，我们决定：“好吧，让我们开始使用这些开源模型。” 我们采用了那些较小的模型，然后，这也是为什么我们现在有一支研究团队——这是一支开销非常庞大的团队，但我们之所以拥有这支团队，是因为我们需要那些极其擅长提取这些开源模型、对它们进行微调等等的人才。

所以，时至今日，我们 90% 的工作流都是建立在开源模型上的。再说一遍，主要原因是考虑到延迟，为了真正优化我们的语音智能体。我认为在过去的一年里，我们看到了巨大的进步，无论是在它的声音表现还是交互感觉上，同时它还保持了很高的准确率。然后，剩下的 10% 显然我们仍在使用闭源模型和前沿模型，用于很多新项目或新产品。我认为这正是整个行业的发展方向。如果你要概括一下的话，每一个模型你都可以从三个维度来评估：成本、智能和延迟。根据你的需求，你总想在这三者的极限边缘游走，有时候你还可以做些权衡，对吧？所以在我们的案例中，我们知道我们其实是在智能方面做出了妥协，因为我们要做的就只是那一个任务，但现在我们获得了这些延迟上的优势。

<details>
<summary>Original English</summary>

**Jesse**: sounds good um so I'm gonna talk about our journey first uh just to make it very concrete for people so when we started the any uh the goal was just to get something working, right? So if when you get something when you're the goal is to get something working, of course you're just going to use the frontier models because you want to get something out there and have actually deliver value. And so we were using opening anthropic at that time they were kind of like one uping each other in terms of how the how the models performed. And then at some point as we got to larger scale and we started working with larger and larger companies and they had you know millions of customers and then we we also have uh we also launched our voice agent right so a big factor became latency so it wasn't just like can you deliver good responses you have to deliver them really fast and uh the only way to get latency down um but also kind of you make our agent operate the way we want it to is to use smaller models and when you want to go to smaller models unfortunately the the Frontier labs, they do have small models, but you you can't really control them in the way the way that you want and most small models out of the box are not going to be good enough at the task that we want them to do. So, you have to fine-tune them, you have to change them. And so, that's when we started looking at open source. So, this was about year plus ago. And um it worked really well because if you think about it in the agent, right? So, in our agent, our agent's job is to have conversations. So, it needs to do a lot of things at once, right? And like one one the first step it might do is like hm what topic is this person talking about or and something else it might do is oh is this person a bad actor that's coming in and trying to mess things up. There's all these like tasks it has to do. Each individual task doesn't need all of the intelligence of a big model. So you know all the frontier models are obviously very smart but they can do a bunch of different things. Like they can do math they can do coding. Like you just need them to be good at that one task. And so that's why you can use a smaller model and if you fine-tune it to be really good at that task and can be just as good or better than the big models, right? So that was that was step one for us. You know, about a year ago, we were like, okay, let's start using these open source models. Uh we we we took the small ones and then um you know, that's why we have now a uh a research team and it's a very expensive team, but it's we we have it because, you know, we need people that are really good at taking these open source models and and tuning them and and so on. So today 90% of our workflow is on open source and um you know again the main reason was for latency to really optimize our voice agents and um I think we've just over the last year we've seen tremendous improvement in like how how it sounds how it feels and but still also like keeping the accuracy high um and then the remaining 10% of course we're still using the uh the closed source models and the frontier models for a lot of you know new new projects or new products and uh I think that's just where the industry is moving to. So if you kind of were to generalize this every model you can kind of evaluate along three dimensions. It's you know cost intelligence and latency and depending on what you need you want to kind of be at the limit of those three and sometimes you can trade off right so in our case we knew that we actually pull back on intelligence because we all had to do was that one task but now we get these latency advantages.

</details>

**Host**: 其实我想就这一点稍微追问一下，因为很多时候，你也知道，当你在 Twitter 上看到这类辩论时，权衡往往变成了：“哦，我们到底是想要极其昂贵的最聪明的模型，还是可以把它变笨一点，让它更便宜？” 我其实认为这是一种错误的权衡预设，对吧？

<details>
<summary>Original English</summary>

**Host**: I want to push a tiny bit on that point actually because um often times you know when you see these debates being had on Twitter the the trade-off tends to be oh do we want uh you know the smartest model that is very expensive or can we like dumb it down a little bit and get it cheaper. I actually think that is a false trade-off, right?

</details>

**Jesse**: 是的，因为我们在实践中看到的是，即便你使用了一个所谓的“更笨”的模型，你也能让它——我们已经在实践中见证了这一点——你能在那个特定任务上让它达到更高的性能。所以当我们微调更小、更笨的模型时，它们只是没有那么通用，但在我们希望它们执行的具体任务上，它们实际上超越了大型、聪明、最先进的模型，对吧？所以最终我们三样都得到了：它在特定任务上做得更好，它更便宜，而且它更快。

<details>
<summary>Original English</summary>

**Jesse**: Because what we've seen in practice is even if you have a quote dumber model, you can get it, and we've seen this in practice, you can get it to higher performance on that specific task. So when we fine-tune smaller, dumber models, it's that they're just not as general purpose, but on the specific task we want them to do, they actually outperform the large, smart, state-of-the-art models, right? So we end up getting all three things. It is better at the toss. It is cheaper and it is faster.

</details>

**Host**: 那么你是否觉得，到了今天，其实你们在 Decagon 几乎不需要为任何事情使用最前沿的模型了？因为你们的性能已经非常出色了。

<details>
<summary>Original English</summary>

**Host**: And so do you feel like today like you need the most Frontier models for really anything at Decagon because your performance is very good already. So

</details>

**Jesse**: 我们确实需要，我们经常还是会需要它们来处理辅助任务，对吧？也就是当你有一些辅助模型来支持我们主要的对话流程时。如果你有一个智能体，它正在帮助客户改签，或者它正在协助他们处理医疗保健中的某个流程，那么这些都是定义明确的路径。所以我们有调优过的智能小模型来做那些事。

但比方说，我们最近推出了“自动驾驶”（Autopilot），对吧？这是我们用来改进核心对话智能体的一个智能体。那么，对于像 Autopilot 这样的产品，它执行的是一项非常复杂的工作，对吧？它的任务是：“我要去回顾刚才发生的一百万次对话。我要努力找出其中的趋势。我要创建核心主要模型的各种变体，看看哪些变体表现得更好。” 因此，这变成了一个更加宽泛、开放式的探索性任务。所以，我们认为对于这类工作，非常聪明、能够尝试很多新事物的前沿模型就非常有意义。

<details>
<summary>Original English</summary>

**Jesse**: we we do and we often need them we often end up needing them for auxiliary tasks, right? Where when you have uh when you sort of have auxiliary models to our sort of primary conversational flow, right? you have an agent and it's helping a customer with their rebooking or it's helping them with a process in healthcare then these are like well-defined pots. So we have smart bos models to do that but we've for instance recently launched do autopilot right which is our agent that improves the core conversational agent. Now, for something like autopilot, it is doing a very complicated job, right? It's saying, I'm going to go and review a million conversations that just happened. I'm going to try and find trends. I'm going to create variants of the primary model and see which of those variants does better. So, now this is a much more broad open-ended exploratory task. So, we think for jobs like that, frontier models that are very smart, that can try out a lot of things make a lot of sense.

</details>

**Host**: 你认为……我的意思是，你们显然走到了这一步，而且你也提到了，Jesse，你们有一支研究团队，对吧？你们推出了 Decagon Labs。但在正式推出之前，这一直是你们文化的一部分。你觉得其他的企业也会在“训练后的开源模型应用”（post training open source models）方面达到这个水平吗？

<details>
<summary>Original English</summary>

**Host**: H do you think that um I mean you guys obviously and you referenced it um Jesse that you have a research team right you guys launched Decagon Labs but even before the formal launch it's always been a part of your culture um do you think that enterprises will get there as well on post training open source models

</details>

**Guest**: 哦，有意思，你觉得这需要多长的时间线？

<details>
<summary>Original English</summary>

**Guest**: oh okay interesting what's the timeline

</details>

**Jesse**: 是的，我觉得……我认为他们会达到那个水平的。但这可能需要比人们想象的更长的时间，因为你知道，即便是对于我们的专业团队来说，微调这些模型也是一件绝非易事的工作。

<details>
<summary>Original English</summary>

**Jesse**: yeah I think I think they'll get there but it'll probably take longer than people think because you know even with our team fine-tuning these models is non-trivial

</details>

<!-- chunk 2/11 -->

### 开源模型与前沿模型的权衡

**Speaker A**: 这不仅仅是说，“哦，好吧，我们决定使用开源模型了。”就好像，“我们只管用开源就行了。” 并不是这样的。你必须获取数据，然后更重要的是，你必须拥有良好的评估机制。如果你看看我们的评估，你会发现，我们的评估机制是针对我们自身业务非常特定的。你不能只是随便拿一个公开的评估集，然后指望它就能完成工作。我们是在我们自己的任务上进行测试，因此我们必须生成我们自己的基准测试和评估集。不过，我认为重点是，在某个特定阶段，使用开源模型是绝对更好的选择。因为当你的用例已经固定下来，当你大规模投入生产环境，并且你非常确定代理（agent）的形态基本上就是这样时，你就没有任何理由不去使用开源模型了。因为你会获得延迟方面的优势，同时你也会获得成本方面的优势。我的意思是，同样地，我们最初并不是为了成本优势才这么做，但这就像是一个很好的附带好处，对吧。

<details>
<summary>Original English</summary>

**Speaker A**: it's not just like oh you And it's like all right, we made the decision to use open source. Like let's just use open source. Like you have to get the data. And then more importantly, you have to like have good eval. Um and if you think about our evals, right, our evals are very specific to us. You can't just like use some public eval set and like that that just does the job. It's like we're testing it on our task and so we have to generate our own benchmarks and evals. Uh but I think the point is that um at a certain point it's strictly better to use open source models because when your use case is solidified and you're in production at scale and you're pretty sure this is the the sort of shape of the agent then there's no reason not to use open source because you you get these latency benefits and at the same time you get the cost benefits. I mean again we didn't do these for cost benefits but that's like a nice side effect right

</details>

**Speaker B**: 一旦你达到了那个阶段，你就会觉得，为什么还要为这个去使用前沿模型呢？但是对于所有那些全新的、带有某种实验性质的东西，或者就像 Asha 刚才所说的那样，对于那些你真正需要高智能水平的产品而言，你仍然会去使用前沿模型。而且使用前沿模型简直要容易得多。你知道，他们已经在操心基础设施的问题了，而你只需要，比如，只需要调用 API 就行了。我认为这就是为什么目前在企业中，尽管大家对开源有着极大的炒作热情，但实际上开源推理（inference）的份额现在正在下降。原因在于人们正在不断启动所有这些新的用例。而在你启动新用例的时候，你当然会先使用前沿模型，直到它们能够正常工作为止。

<details>
<summary>Original English</summary>

**Speaker B**: and once you're there it's like why why use Frontier for that? But for everything that's new and sort of experimental or you're as Asha was saying what or like kind of these products where you really need the intelligence you're still going to use frontier models and it's just so much easier to use frontier models you know they're worrying about the infra you just like like they just um you just use the APIs and I think that's why in enterprises right now even though there's there's a lot of hype for open source the sort of share of of open source inference is actually going down right now because people are spinning up all these new use cases and if you're spinning up new use caseas is of course you're going to use the frontier models until until they're working.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 但在这些用例中，你知道的，有一些可能会消失，但像其中的一些用例可能会留存下来。企业会觉得，“好的，太棒了。我们希望继续交付这个功能并把它推广出去。”

<details>
<summary>Original English</summary>

**Speaker B**: But of those use cases, you know, some might die off, but like some might like the enterprises are like, "Okay, great. We want to keep shipping this and like roll it out."

</details>

**Speaker A**: 一旦达到那个阶段，他们就有强烈的动机去使用开源模型了。因为它要便宜得多，也快得多。

<details>
<summary>Original English</summary>

**Speaker A**: Once it's at that point, they're heavily incentivized to use open source. It's way cheaper and faster.

</details>

**Speaker B**: 在那个时候，他们或许可以在内部团队自己完成，又或许他们需要一些人员的帮助，来协助他们进行微调。但这种转变最终是一定会发生的。我只是觉得这个过程可能会有些缓慢。甚至就我们现在的经验来看，

<details>
<summary>Original English</summary>

**Speaker B**: At that point, they'll maybe they can do it in house or maybe they'll need help uh from people to to help them fine-tune it. But that that will eventually happen. I just think it'll be kind of slow. Even right now in our experience

</details>

**Speaker B**: 比如，企业有很强烈的意愿想要转型，但他们一次只能处理这么几个用例。你知道，那里存在着一种惯性。他们必须，你必须走完所有的流程，比如模型风险治理，以及所有的安全审查等等。所以，我认为这需要时间，但最终一定会实现。

<details>
<summary>Original English</summary>

**Speaker B**: like enterprises have a lot of desire to move but they can only do so many use cases at once. You know they there is inertia there and they have to you have to go through all the you know model risk governance and all the security things and so um I think it'll take time but it will get there.

</details>

### 模型格局的快速迭代

**Speaker A**: 是的。我认为企业去构建他们自己的、你知道的、“炫酷实验室套件”之类非常有意义的另一个原因是，这些模型的形态在不断地发生变化，对吧。我们并非只是构建好我们自己的一套开源模型，然后，你知道，就大功告成了，我们就可以继续去做下一件事情，或者也许两年后再来重新审视这个。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. the the the other reason I think it makes a lot of sense for uh enterprises to kind of build their you know cool bundle of labs is that the shape of these models is changing constantly right we don't just build our set of open source models and then you know it's done we can move on to our next thing and maybe we'll revisit this in two years

</details>

**Speaker B**: 你们往往需要一直不断地训练新的模型。

<details>
<summary>Original English</summary>

**Speaker B**: you often need to train new models all the time

</details>

**Speaker A**: 因为，

<details>
<summary>Original English</summary>

**Speaker A**: because

</details>

**Speaker B**: 随着技术前沿的变化，随着模型能力的变化，你们会为它们想出新的用例。你会发现一些新的应用场景，你会想，“哦，这个任务似乎正在被大量重复，因为现在我有了一个全新的，你知道，前沿模型或开源模型，它现在具备了以前所没有的能力，对吧？” 所以我们发现自己总是需要不断地训练全新的模型，并淘汰掉那些不再相关的老模型，因为你知道，也许前沿技术已经向前推进了许多。开源模型的前沿技术也已经进步了很多，你知道，这个模型开箱即用就能完成很多以前无法完成的事情。所以我们……

<details>
<summary>Original English</summary>

**Speaker B**: as the frontier changes as the capability of the models changes you come up with new use cases for them. You find new places where you're like, "Oh, this task seems to be getting repeated a lot because now I have this totally new like, you know, frontier model or open source model that now has this capability that they didn't have before, right? So we find ourselves constantly training net new models and deprecating old ones that are no longer relevant because you know maybe the frontier has advanced a lot. The open source frontier has advanced a lot and you know the model out of the box can do a lot of things that it couldn't do before. So we

</details>

**Speaker A**: 因为模型的整体格局变化得实在是太快了。

<details>
<summary>Original English</summary>

**Speaker A**: because the model landscape is changing so quickly.

</details>

**Speaker A**: 在某种程度上，Decagon Labs 就像是一个模型工厂，对吧？我们真正建立它的目的在于……比如，压缩从一个新模型发布，到针对我们特定任务进行过有用微调的模型从另一端“产出”的时间间隔。

<details>
<summary>Original English</summary>

**Speaker A**: Uh Dagon Labs is in a way a model factory of sorts, right? We really built it to um like uh compress the time between new model coming out and you know useful fine-tuned to our task model kind of popping out the other end.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 就是因为这种情况无时无刻不在发生。

<details>
<summary>Original English</summary>

**Speaker A**: Just because happens all the time.

</details>

### 自建与外包的权衡 (Build vs Buy)

**Interviewer**: 从人才的视角来看，你们是如何考虑哪些部分应该在内部保留的？相比之下，现在还有一个非常广泛的生态系统，你知道，有可能是 RL（强化学习）即服务，或者是评估即服务等等。比如，你们有什么样的框架来决定，“嘿，这是任务关键型的，我们需要做得最好”，还是说“是的，如果能把它外包出去就太好了”？

<details>
<summary>Original English</summary>

**Interviewer**: How do you guys think about what to inhouse from a talent perspective versus there's also a pretty broad ecosystem right now that is you know could be RL as a service eval etc. like how do you guys what's your framework for hey this is mission critical and we need to do this best versus yes it'd be great to you know outsource this.

</details>

**Speaker A**: 嗯，你知道，在实践中我们已经看到，有很多与模型训练相关的事情是与我们所拥有的具体用例紧密耦合的。

<details>
<summary>Original English</summary>

**Speaker A**: Um you know in practice we've seen that so many things uh relevant to model training are so tightly coupled to the use case that we have

</details>

**Speaker A**: 对，所以我们发现，当我们有一些想要进行微调的开源模型时，我们最终需要在内部构建大量的工具。我们发现，如果我们能够明确地根据客户的最终结果来定制我们的评估机制，这要比仅仅看模型随着时间推移的损失曲线要好得多，对吧。我们不仅仅是在问：“哦，我能完成这一个特定的任务吗？” 我们是在端到端地衡量整个系统。我们不仅仅是在说：“这个模型在某项任务上表现得好吗？” 我们是在看：“这个模型是否正在与所有其他模型协同工作，共同交付我们所关注的最终客户成果？” 正因为这对于我们的设置来说是如此地独特，所以在实践中我们发现，我们需要构建大量用于训练和评估这些模型的基础设施。不过，对于其他一些事情，比如获取标记数据，以及衡量我们数据集的多样性，我们就会觉得：“是的，这些是所有公司都面临的共同任务。” 在这种情况下，我们就希望能从其他供应商那里购买现成的服务，因为那将能帮助我们把模型更快地投入到生产环境中。归根结底，我们唯一关心的事情就是：我们如何才能尽可能快地将最好的模型投入生产。

<details>
<summary>Original English</summary>

**Speaker A**: right that we find that we end up needing to build a lot of tooling internally when we have um open-source uh open source models that we want to fine-tune we find that if we can clearly tailor our eval to customer outcomes it's way better than just looking at like loss curves over time right we're not just saying oh can I do this one specific task. We're measuring the entire system end to end. We're not just saying is this model good at this task. We're saying is this model working in concert with all these other models delivering the end customer outcome that we care about. And because that is so unique to our setup, we've found that in practice, we've needed to build a lot of uh a lot of the infrastructure that we need to train these models and evaluate them. Now, for other things like getting labeled data and measuring the diversity of our data sets, we're like, "Yep, these are tasks that are common across fossil companies." In which case, we want to buy things from other vendors because that'll just help us get those models to production faster. Ultimately, the only thing that we care about is how can we get the best model to production as quickly as we can.

</details>

### Token经济学与性能优先

**Interviewer**: 所以听起来，你知道，现在有很多人在讨论类似“token 经济学（tokconomics）”，以及实际运行这么多模型的成本有多么昂贵。但基于这次对话，听起来你们好像并没有花太多时间真正去考虑这些模型的成本。这是对的吗？对你们来说，最重要的其实还是性能表现。

<details>
<summary>Original English</summary>

**Interviewer**: And so, it sounds like, you know, there's a lot of talk right now about like tokconomics and how expensive it is to actually run a lot of these models. Based on this conversation, it doesn't sound like you guys spend that much time actually thinking about the cost of these models. Is that correct? It's really about the performance for you.

</details>

**Speaker B**: 性能、延迟和准确性绝对是决定这一切的大多数因素的驱动力，对吧？成本是一个很好的额外好处，你知道，令人惊讶的是，这恰恰是少数几个你能似乎“免费”得到所有好处的任务之一，对吧？比如，我们实际上并不需要在成本、延迟和性能之间进行权衡取舍。因此，仅仅通过优化驱动因素——也就是延迟和性能——我们就能顺理成章地将降低成本作为一个不错附带收益。

<details>
<summary>Original English</summary>

**Speaker B**: Performance uh latency and accuracy is definitely the driver factor for most of this, right? Cost is a nice benefit in that, you know, uh surprisingly this is one of the few like tasks where you kind of get all the things for free, right? like we we don't actually have to trade off cost and latency and performance and so just by optimizing for the driver is actually latency and performance and we just get cost as a nice side benefit

</details>

**Interviewer**: 那么你认为这是属于 Decagon 公司独有的运营方式呢，还是你觉得关于“token 经济学”的讨论，因为某些原因，只是没有以同样的方式影响到你们？

<details>
<summary>Original English</summary>

**Interviewer**: and do you think that's like something that's unique to the way Decagon is run or do you think there's something about like this conversation about tokconomics that for some reason just doesn't affect you guys in the same way? 

</details>

**Speaker B**: 不，我认为如果你是一家处于成长阶段的公司，那么说实话，比如很明显我们必须对我们的成本负责，但这并不是最优先的事项，对吧？最高的优先级仅仅是实现增长。当你与客户交谈时，他们并不真正关心你的成本是多少。他们只关心你的代理程序表现得有多好。

<details>
<summary>Original English</summary>

**Speaker B**: No, I think if you're a growth stage company, then you're honestly like obviously we have to be responsible with our costs, but that's not the highest priority, right? The highest priority is just growing. And when you're talking to a customer, they don't really care what your costs are. They just care about how well your agent performs.

</details>

**Speaker A**: 所以，这才是最主要的方面。实际上，如果你看看我们代理的输出单位（unit of output），在我们的例子中就是一次对话，那才是我们客户真正关心的东西。他们并不真正在乎那次对话对我们来说花费了多少成本，或者里面包含了多少个 token。而实际上，随着时间的推移，我们在每次对话中使用的 token 数量反而在上升。因为我们实际上在进行更多的模型调用，从而提高质量，执行更多的检查，以及并行处理更多的事情。而这就是我们目前所处的阶段。就像最终，你知道，如果我们已经赢得了市场，那么那时候就该说，好的，是的，你知道，现在是时候审视我们的成本，看看我们是否能进一步优化了。但这只是不是目前的首要任务。

<details>
<summary>Original English</summary>

**Speaker A**: So that's um that that's the main thing. So actually, if you look at like our unit of output of our agent, which is in our case a conversation, um that's really what our customers care about. They don't really care about how much that conversation costs to us or how many tokens are in it. And actually over time, the number of tokens we're using per conversation has gone up because we're actually doing more model calls to make the quality better, to do more checks, to um paralyze more things. And that's just the stage we're in right now. Like eventually, you know, if we've won the market, then like that's when it's like, okay, yeah, you know, now it's time to look at our cost and see if we can optimize further. But it's just not the top priority.

</details>

**Speaker B**: 是的。我也认为，我们作为一家公司，与许多在 X（推特）上谈论 token 经济学的人所处的阶段是不同的。因为关于 token 经济学的辩论实际上主要围绕着：“嘿，我今天正在使用一个前沿模型，我应该怎么分析我的成本？我是不是该转向开源模型？” 在那种情境下，我实际上觉得这是完全合理的。如果我们整个业务都在独家使用前沿模型运行，我也会非常关心成本，我也会考虑很多关于那方面的事情。但是一旦你已经，一旦你已经……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I also think we as a company are at a different stage than a lot of people that are talking about tokconomics uh on on on X right because the tokconomic debate really is around uh hey I'm on a frontier model today should I like how do I analyze my cost and should I move to open source right and there I actually think it makes complete sense if we ran our entire business exclusively on frontier models I would care a lot about cost and I would think a lot about that but once you're already once you've already

</details>

<!-- chunk 3/11 -->

### 应用层与基础设施层的虚假二元对立

**Speaker A**: 突然之间就变成了，好吧，现在我们知道该如何看待开源模型了，我们也知道如何拆解问题，我们知道如何非常非常快地构建、训练和部署这些模型。突然之间，成本方面的问题变得不再那么紧迫。但如果你仍然处于所有事情都使用前沿模型的阶段，那么我认为考虑工具化（toolics）就非常有意义了。

<details>
<summary>Original English</summary>

**Speaker A**: made the jump to saying okay now now we know how to think about open source models and we know how to decompose a problem we know how to uh build train and deploy these models very very quickly all of a sudden that the cost aspect becomes a lot less pressing um but if you're still in the world where you're using frontier models for everything then I do thinking about toolics makes makes a lot of sense

</details>

**Speaker B**: 我只想做一个元观察，刚才的很多对话其实都是在讨论诸如训练模型之类的事情，对吧？我们讨论了强化学习，这真的打破了我认为一直存在的一种关于“什么是 AI 应用”的长期误解。我想稍微深入探讨一下这个争议，因为我认为这是一种主导了 2026 年上半年的叙事，那就是 Anthropic 和 OpenAI，他们是最后的初创公司。他们将接管一切。而应用层公司，它们只是带有全职员工（FTEEs）的浅层用户界面（UI），只是附加了一些实现而已。我们刚才稍微谈到了 Decagon Labs，你们能分享一下，你们是如何看待这种可能存在的“应用与基础设施公司”的虚假二元对立的？显然你们远不止是 UI 或实现层。过去几周到处流传的关于 Agent 实验室的流行描述，这能准确描述你们吗？你们是如何定位 Decagon 的？

<details>
<summary>Original English</summary>

**Speaker B**: I just want to make this meta observation that a lot of the conversation even just now has in about things like training models, right? Uh we're talking about reinforcement learning and um it really does blow away what I think is, you know, a lingering misperception about what an AI application is. Um and just to get into that debate a little bit because I think it's sort of this narrative that dominated the first half of 2026, which is that anthropic open AI, they're the last startups. They're going to take over everything. applications, their thin UIs with FTEEs, you know, with implementation attached to it. Um, you know, we talked a little bit about Deck Gun Labs, but can you guys just share what is your like how do you think about this potentially false dichotomy of app versus infrastructure company? Um, clearly you guys are so much more than the UI or the implementation. Um and uh you know does agent lab you know popular uh description um floating around the last couple of weeks like does that describe it like how do you guys think of decagon?

</details>

**Speaker A**: 我来给一个简短的视角，就从一个企业客户的角度来说，然后我们也许可以更广泛地谈谈整个行业。假设我是一家财富 100 强的公司，对吧？我审视着外面所有的用例，我面临一个选择：是与一家应用公司合作，还是利用这些实验室从头开始构建？我认为在某些情况下，与实验室合作是很有价值的。我觉得如果你看看我们的情况，对吧？我们刚才讨论了所有这些微调的事情。我认为人们普遍存在的一个误解是，你知道，微调是一种为该客户进行定制的方法。但实际上，我们所做的大部分微调，都是为了我们的用例（比如客户服务用例）而进行的定制。

<details>
<summary>Original English</summary>

**Speaker A**: Um so I'll give a quick perspective just like from the from the POV of like an enterprise and then maybe we can talk about like broader the industry. So let's say I'm like a Fortune 100 company, right? and I'm looking out there on all my use cases and I have a choice of partnering with an application company or uh sort of using the labs and building from scratch. Um I think there is a lot of merit to partnering with the labs in certain cases. I think if you look at our case right like we we just talked about all this fine-tuning stuff. I think a common misconception that people have is you know fine-tuning is is a way to like customize it for that customer. In fact, most of the fine tetuning we do is like customizing it for our use case, like the customer service use case.

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker A**: 对我们来说，做这件事是值得的，因为这就是我们的全部业务，对吧？我们在所有这些不同的客户群体中部署这些智能体。因此，投入大量时间和研究，弄清楚如何调整这一个模型，使其擅长选择客户服务主题，对我们来说是值得的。但如果你是企业，为了这些像客户服务一样的行为而去微调一个模型，真的值得动用你们宝贵的研究资源吗？可能不值得，对吧？所以这就是人们与应用公司合作的一个原因。另一个原因是——

<details>
<summary>Original English</summary>

**Speaker A**: And it's worth it for us to do it because that's all we do, right? We do these agents across all of these different customers. And so it is worth it for us to put in a ton of time and research into like how do you tune this one model to be good at selecting customer service topics. But if you're the enterprise, is it really worth your valuable research resources to like tune a model for these like customer service behaviors? Probably not, right? So that that's like that's one reason why people um partner with applications. Another reason is

</details>

**Speaker A**: 假设我确实投入了工程努力，利用前沿模型自己构建了某个智能体。而且，正如我之前提到的，我并不是在微调它的行为，而是在教 AI 我自己的流程。需要重申的是，这不能通过微调来实现，而是发生在上下文中（in context），因为如果你针对这些流程进行微调，那么每次你更改流程时，都必须把之前的微调逆转过来，这毫无道理。所以，你得构建逻辑，并在其中构建你的业务逻辑，然后你上线了这个智能体，到了第二天，你查看对话记录时发现：“哦，其实我需要更改这三个地方。”

<details>
<summary>Original English</summary>

**Speaker A**: let's say I do put in the engineering effort to build like a some agent myself using the frontier models. Um and you know to my earlier point you know I'm not fine-tuning for behavior but I'm I'm sort of teaching the AI my own procedures. And again that doesn't happen through finetuning that that happens like in context because if you were to fine-tune on that you would have to reverse it every single time you you change your procedures which doesn't make sense. And so you kind of build out your logic and you're building your business logic in well then you launch the agent and then the second day you look at your conversations and you're like oh well actually I need to change these three things

</details>

**Speaker A**: 这就需要投入更多的工程精力，并且这是一种持续不断的工程投入。我认为，当用例需要一个更广阔的平台时，人们就会选择与应用公司合作。使用我们微调过的东西，以及使用我们在模型之上构建的软件堆栈来捕获业务逻辑，会带来很多价值。而那些东西跟模型本身毫无关系，对吧？比如，业务逻辑是如何被这个 AI 捕获的？你如何处理有人因为航班取消而打来的电话，而且他们需要同时为三个人重新预订？这属于 AI 需要了解的业务逻辑，你要将其编码，但这与模型本身无关。因此，这就必须存在于应用层。我认为这就是应用层仍将大放异彩的地方，因为你仍然需要那里的应用功能，而不仅仅是模型。实验室本身也会具备更多应用能力，但那些会是相当通用的。比如，你也许可以构建能够做这件事或那件事的通用智能体，但是——

<details>
<summary>Original English</summary>

**Speaker A**: and now it's more engineering effort to do that and it's like constantly engineering effort. I think people will partner with applications when the use case calls for a broader platform where there's a lot of value in using you know the stuff that we've fine-tuned and using the the software stack we've built on top of the models to capture business logic and that stuff has nothing to do with the models right like how how the business logic gets captured by this AI like how do you handle someone calling in because you know their flight was canceled and they need to rebook three people at once it's like that is business logic that the AI needs to and you're encoding that, but that has nothing to do with the models themselves. And so that that has to exist in the application layer. I think that's where applications will still shine because you still need the application there and it's not so much the models. And the labs themselves will have more application capabilities, but those will be fairly general. Like they're you can maybe build general agents that can do this thing or that thing. But

</details>

**Speaker A**: 对于很多像我们这样的核心垂直领域，我们的观点是，你需要的是一种非常深入的东西，它拥有所有的集成，拥有捕获业务逻辑的全部能力，能够运行测试和实验，然后审查对话、进行 QA（质量保证），而且还要有能让合规团队监控发生之事的工具。这就是我们对此的看法。所以它并不是非黑即白的，在某些用例中，使用前沿模型确实有意义，但对于这些核心垂直领域来说，做得超级深入才是明智之举。

<details>
<summary>Original English</summary>

**Speaker A**: for a lot of these like core verticals like ours, our our our thesis is that, you know, you're going to need something that's like very deep and has all the integrations, has all the ability to capture business logic, has the ability to run, you know, tests and experiments and then review the conversations and run QA and like, you know, have tooling for your compliance team to monitor like what's happening. So that that's our thesis on it. And so it's kind of it's it's not black and white like there will be some use cases where it does make sense to use the the frontier models but there will be these like core verticals where going super deep makes sense.

</details>

**Speaker C**: 是的。我也认为，大家现在都有点渗透到了别人的领域中，对吧？就像——

<details>
<summary>Original English</summary>

**Speaker C**: Yeah. I also think you know everyone is kind of bleeding into everybody else's space a little bit right like

</details>

**Speaker A**: 趋同融合。

<details>
<summary>Original English</summary>

**Speaker A**: that's a convergence

</details>

**Speaker C**: 所有的实验室都在其之上构建应用，因为他们有理由这么说：“这就是企业能从我们这里获得更多的方式，这也是企业通过使用我们的产品看到投资回报率（ROI）的方式。”而对于我们这些在应用层的人来说，我们意识到，嘿，通过构建我们自己的模型，我们可以针对我们关注的用例，榨取到更多的性能，并降低延迟和成本，对吧？我认为这种分化、这种相互渗透是合理的，而且我相信它会继续下去。不过我并不太买账“实验室才是最后的初创公司”这种世界观，我认为这对于 SaaS 公司和新的 AI 初创公司来说都是如此，因为在某种程度上，我们人类就有点像是通用人工智能（AGI），而人类需要使用软件来做很多事情。你需要把东西放进数据库，你需要用 CRM 来追踪事情。我认为，即使你拥有了 AGI，我们所有的 AGI 智能体也都需要一个地方来存储工作、从中提取信息，并对事物进行推理。所以我认为，某类专门为了让人类工作而构建的 SaaS 公司可能会面临一点压力，但我并不认为软件作为一个整体会以任何有意义的方式消亡，我仍然认为在应用层面上——

<details>
<summary>Original English</summary>

**Speaker C**: all the all the labs are building applications on top of it because rightly so they're saying this is how the enterprises do us more right and this is how the enterprises see ROI from using our products uh us on the application layer we're realizing that hey we can squeeze out a lot more performance and latency and cost for the use cases that we care about by building our own models, right? Which and and I think this uh this split this kind of bleed over makes sense and I think it'll continue. I'm not as bought into the the labs are less startup view of the world though and I think this is true both for SAS companies and for the new AI startups because in a way we human beings are kind of AGI right and human beings have needed to use software for lots of things you know you need databases to put stuff in you need CRM to track things and I think even once you have AGI all our AGI agents are going to need somewhere to store work and pull information from and reason about things. So I think you know a certain class of SAS companies that were solely built for people to do work might face a bit of heat but I I don't think software as a whole in any meaningful way is going away and I still think you know on the application layer

</details>

**Speaker C**: 有太多不同种类的工作需要完成，而这些工作能够以更快、更高效、更廉价的方式来执行。所以我认为，应用层公司永远都会有一席之地，也许从长远来看，应用层公司只是变成了特定垂直领域的实验室，因为你的主要产品最终变成了在执行这些特定任务方面非常出色的模型。但我认为，应用层很可能会一直存在下去。

<details>
<summary>Original English</summary>

**Speaker C**: there's so many different kinds of work that that need to be done that can be done faster more efficiently more cheaply uh so I think there will always be a space for application layer companies maybe in the long term application layer companies just become labs for specific verticals, you know, because your primary product ends up being the models that are just really good at doing those specific tasks. But I think the application layer is probably here to stay.

</details>

### 前置部署工程师与 AI 工作流

**Speaker B**: 我也想稍微借你刚才顺带提到的一点引申一下。

<details>
<summary>Original English</summary>

**Speaker B**: Uh I also want to kind of pick on another thing that you kind of said in tossing.

</details>

**Speaker C**: 嗯，请说。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah, please.

</details>

**Speaker B**: 也许这是一个更犀利的观点：应用层公司是否只是前置部署（forward deployed）公司，在做“最后一英里”的工作？

<details>
<summary>Original English</summary>

**Speaker B**: And maybe this is like a a spicier take of oh are application layer companies just for deployed companies that are kind of doing the last mile of work.

</details>

**Speaker C**: 是的。对。好吧，其实我是说那是一个误解，但我认为这确实是一个很普遍的想法。是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yes. Right. Well, well, I was saying that's a misperception, but I think it is a common one. Yeah,

</details>

**Speaker B**: 我认为这是个很热门的话题。再次声明，我不是要在科技推特（Tech Twitter）上挑事，说什么“哦，你知道，我们需要带回前置部署工程师”，你也知道，现在每家公司都在大量招聘前置部署工程师。我认为这其实是个陷阱。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's a really hot thing. Also, again, not to pick on tech Twitter to be like, oh, like, you know, we need to bring back the four deployed engineer and you know, every company is hiring tons of four deployed engineers. Uh, I think this is a trap

</details>

**Speaker B**: 真的。

<details>
<summary>Original English</summary>

**Speaker B**: actually.

</details>

**Speaker C**: 哦，详细说说。好吧。我对这点的看法是，前置部署工程师对于早期阶段的 AI 公司来说是必要的，或者说是新近变得必要的，因为工作流是全新的，对吧？如果你在 5 年前建立一家 SaaS 公司，大多数 SaaS 产品已经被探索得相当透彻了，对吧？你大致知道用户想做什么，你的工作也许是提出稍微更整洁的工作流，但总体上你知道用户想用一个设计应用或一个 CRM 或者——

<details>
<summary>Original English</summary>

**Speaker C**: Oh, same more. Okay. My my view on this is that for deployed engineers are necessary or newly necessary for early stage AI companies because the workflows are new, right? If you're building a SAS company 5 years ago, most SAS products are pretty well explored, right? like you roughly know what the user is trying to do and your job is maybe come with a slightly cleaner workflows but broadly you know what the user is trying to do with a design app or a CRM or

</details>

<!-- chunk 4/11 -->

### 产品化与前线部署

**Speaker A**: 但从长远来看，我认为他们应该专注于构建产品，对吧？一旦你清楚了工作流程是什么，你就不应该再依赖前线部署工程师了，因为一旦你掌握了工作流程，如果你能将其产品化，你就应该将其产品化，然后成为一家典型的、具有科技公司规模扩展属性的公司。

<details>
<summary>Original English</summary>

**Speaker A**: Uh but long term, I think they should just be building product, right? Like once you know what the workflow is, you should not be relying on four deployed engineers anymore because once you know what the workflow is, if you can productize it, you should productize it and then become, you know, typical company with these scaling properties of a tech company.

</details>

**Speaker B**: 是的。如果你做不到这一点，那你只是在打造一个披着华丽外衣的咨询外包公司罢了。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And if you can't do that, then you're just building a glorified consulting truck.

</details>

**Speaker C**: 嗯，我很想深入探讨一下这个问题，因为我知道当我们在大概三年前整整开始合作时，你们提出了这个想法，当时有两件相对非共识的事情，现在感觉已经变成行业标准了。第一件是你们启动 AI 客户服务时，很多人说，“那只是一个基于 GPT 的套壳应用”。我们就“为什么并非如此”讨论了很多。然后你们做的第二件事是说，“嘿，我们实际上想自己亲力亲为地完成这项工作，我们不想仅仅成为一个软件平台”。现在我们有了一个专门的术语来称呼它，那就是“AI 智能体”之类的概念。并且，你们让“智能体产品经理（Agent PMs）”和“前线部署（Forward Deployed）”在硅谷成为了一种全新或者更常见的一种角色类型。但是你们的智能体产品经理或前线部署团队从你们刚起步到现在其实已经演变了很多。所以我想聊聊，在早期它实际上是什么样子的？然后随着你们开始了解这些工作流程并能够更好地将它们产品化，这个职能对于你们团队来说是如何演变的呢？是的，如果你看看我们许多的前线部署团队，他们在以这样或那样的方式构建产品，对吧？所以，举例来说，我们所有的前线部署工程师都在构建核心产品，对吧？他们的工作是深入一线并去理解，当我们与企业合作时，他们需要哪些我们目前产品还无法实现的功能。但这部分产出的不只是专为某个客户构建的一次性功能，而是会以某种方式贡献给核心产品，使得接下来 10 个提出相同需求的客户能直接免费获得该功能。

<details>
<summary>Original English</summary>

**Speaker C**: Well, I'd love to dig into this more because I know when we started working together, probably almost exactly three years ago, and you guys landed on this idea, there were two things that were relatively contrarian that now feel kind of standard. The first was when you started an AI customer service, a lot of people were like, that's a G GPT rapper. And we talked a lot about like why that's not the case. And then the second thing you did was say like, hey, we actually want to do the work ourselves, like we don't want to just be a software platform. And now we have the term for that. That's like AI agents and everything. and you've popularized agent PMs and forward deployed as a new type of role or more common type of role um in Silicon Valley, but your like agent PM/forward deployed team has actually evolved a lot since you first got started to now and so would love to talk about that like in the early days what did it actually look like and then as you started to learn about these workflows and were able to productize them better um how has that function actually evolved for you guys? Yeah, if you look at a lot of our four deployed teams, they are building product in one way or another, right? So all of our for deployed engineers for instance build core product, right? Their job is to go in and understand as we're working with an enterprise, what are the things that they need that the product does not do today, but the output of that is not a one-off thing that is just built for that customer. It is something that is contributed to core product in a way that the next 10 customers that ask about the same thing get it for free.

</details>

**Speaker A**: 对吧？同样地，我们的智能体产品经理也在与客户合作，以了解目前的产品在哪里存在不足？这在企业内部究竟如何才能实现部署？为了使它能在企业内部署，我们需要在核心产品中添加哪些新功能？所以在一天结束时，所有这一切最终都归结为产品的改进，无论是通过实际的产品功能改进，还是老实说通过流程优化。比如我们与非常庞大的企业合作，帮助他们度过这个转变期，从“好的，这是你们目前组织结构的现状”，到“我们可以引导你们完成流程改造、引入新技术，迈入这个 AI 智能体为你们完成大量工作的新世界”。因此，他们的许多产品工作也包括将“我们如何促成这一点”以及“我们如何帮助公司度过这一转型”的大量经验进行流程化。

<details>
<summary>Original English</summary>

**Speaker A**: Right? Uh similarly our agent PMs are working with our customers to understand you know how is the product broken today? How can this actually be deployable within an enterprise? What are the new things that we need to build to our core product to make it deployable within an enterprise? Uh so at the end of the day all of this boils out boils down into product improvements either through actual product improvements or through honestly process improvements right like we work with very very large enterprises and we help them through the journey to go from okay this is what your or looks like today here is how we can take you through changing your processes through implementing new technology into this world where AI agents are doing a lot of work for you. So a lot of their product work is also processizing a lot of you know how we make that how we help a company through that transition.

</details>

### Palantir 模式与软件公司的规模化

**Speaker C**: 而且你以前在 Palantir 担任过部署策略师。所以你非常熟悉 Palantir 普及的那种前线部署模式。你在 Palantir 做的和你在 Decagon 构想的这个角色，两者之间有多大不同呢？我认为在硅谷，人们对“前线部署（FD）”这个词的使用非常宽泛。

<details>
<summary>Original English</summary>

**Speaker C**: And also you used to be a deployment strategist at Palunteer. So you're very familiar with the forward deployed model that Palunteer popularized. How different is that at what you did at Palanteer versus the way you conceptualize this role at Deagon. So I do think people use the term FD very loosely at Silicon Valley.

</details>

**Speaker B**: 是的。而且我认为将“免费咨询工作”和“实际开发产品”这两者混为一谈是很危险的。你知道 Sham，也就是现在的 CTO 创始人，他内部曾经有一句话——我想现在应该已经被写了很多次了。他会说，“前线部署工程师吃进痛苦，排泄出产品。” 不，那是有点……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And I think it's it's dangerous to mix the two of free consulting work versus actually doing product. Uh you know Sham um who's the CTF founder today had had a phrase um internal I think now it's been written about a ton. He would say uh forward deployed engineers eat pain and excrete product. No, that was kind of

</details>

**Speaker A**: 是的，我认为这就像是一个巨大的误解，因为人们会觉得，“哦，Palantir 是如此热门的一家公司，他们做得那么好，这看起来就像是一种酷炫的去实施事物的方式。” 但首先，很少有公司（如果有的话）能做到 Palantir 所做的事情，也就是从一开始就签下巨额订单，从而让投入那么多精力变得物有所值。因此，我认为很多正在采用这种超级前线部署策略、说着“嘿，我们会为你搞定任何 AI 用例”的人，他们最终将不得不面对一个问题：“好吧，我们能找到一个可扩展的产品吗？”否则你只是在建立一个类似现代埃森哲（Accenture）那样的东西。如果你想这么做，那这也没什么不好的，但我认为人们容易将两者混淆，觉得“嘿，我正在建立一家热门的软件公司，你看，我们也有全职测试工程专家（FTEEs），那是我们的大战略。”因此，这一直是我们从一开始就非常留意的事情——我们在核心上将自己视为一家产品主导的公司，对吧？也就是说，我们在构建一个任何人都可以使用的核心产品，我们来这里不仅仅是为了——即使我们现在有一个庞大的团队——只要什么用例冒出来我们就去构建什么，因为最终所有东西都必须整合到核心产品中，否则你根本无法实现规模扩展。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think it's a it's like a massive misconception because people are like, "Oh, Palunteer is such a hot company and like they're doing so well and like this is like a cool take on how to implement stuff." But first of all, very few companies, if any, can do what Palanteer does, which is like close massive deals off the bat and like it's kind of worth it to spend all that effort. So I think a lot of the uh you know people that are doing this like super forward deployed strategy and like hey we'll do any AI use case for you um they will eventually have to reckon with like okay can we find a product that's scalable otherwise you are just building like a a modern like accent or something which yeah could be could be good if if that's what you want to do but I think people kind of conflate the two it's like hey I'm building a hot like software company and you know we also have FTEES and like that's our big strategy So that's something that we've generally been very mindful about from the beginning is that we really view ourselves uh in our core it's a it's a productled company right um in in the sense of you know we're building a a core product that everyone can use and we're not just here to even though we have a large team now just like build whatever use case that pops up because you know ultimately everything has to go into the core product otherwise you can't scale essentially

</details>

**Speaker B**: 当然，与此同时我应该说，在某种意义上，我们也算是销售主导的，因为产品是由销售反馈来指导的。所以我们并不是坐在那里凭空想出要开发的产品。所以你就有这样一种体系，正如刚才说的，我们有所有这些人员，在某种意义上是被部署到前线的，他们与客户合作得非常紧密，但他们的工作不仅仅是到处随机启动新的用例，或者只是做客户想要的任何事情。因为在短期内，这实际上可能会带来更大的合同，你也可以到处寻找客户的痛点在哪里，但长期来看，这很难实现规模化。所以他们的工作是将从销售中获取的那些认知汇总到核心产品中。在一天结束时，我们的目标是：我们应该拥有市场上最好的产品，并且能够比其他任何人更快地对其进行迭代。而且至少在我们的领域里，我们的愿景是，在这个领域的赢家将是非常产品驱动的。

<details>
<summary>Original English</summary>

**Speaker B**: um at the same time of course you know I should say we also kind of salesled in sense of like the product is informed by sales. So we're not sitting there and just you know coming up with product to build and so you kind of have this system where as a was saying we have all these people that are you know for deployed in the sense of they work very closely with our customers but their job isn't just to spin up like random new use cases here and there and like just doing whatever the customer wants because in the short term that it could actually lead to like larger contracts and you can kind of hunt for wherever the the pain is but then long term it's just very difficult to scale. So their job is to kind of compile all of those learnings from sales into a core product. And the goal at the end of the day is like we should have the best product out there and like be able to iterate on that faster than anyone else. And that's in our space at least our our vision of like hey the the winner in this space is going to be very product driven.

</details>

### AGI 时代的人类职业

**Speaker C**: 我其实想顺着你谈到的关于前线部署工程师（FD）实际上在改进产品这个线索往下聊。你知道，Decagon 是一家非常产品驱动的公司。为了开启这个话题，我说一件看起来似乎毫不相干的微小轶事。我刚才试图说服更广泛团队中的某个人，不要离开 a16z 去一家前沿实验室（Frontier Lab）。我的理由之一是，在这里有一份很好的长期职业规划。那个人给我的回应是，我们将拥有 AGI，长期来看我们不需要职业。这真的触动了我，因为我原以为我已经吞下了 AGI 的“红药丸（了解真相）”，但我其实没有从这个角度去思考过。我很好奇，我们谈论到了产品的改进，对吧？你能为我们具体化一下吗？当你在为你自己或你的客户改进产品时，有没有哪些令你大吃一惊的“啊哈（oh）”时刻？比如，“天哪，我没想到 AI 能做到那个。” 随后我当然也要问问你对 AGI 及其时间表的看法，因为你们正处在企业使用 AI 的摸爬滚打的战壕中。所以你们可能有与我们不同的视角。

<details>
<summary>Original English</summary>

**Speaker C**: I actually want to pull on this thread of you know that you talked about where your FDs are actually approving the product. You know Decon is a very product driven company. Um, so just to kick off with a very small seemingly unrelated anecdote, but um I was just trying to convince uh someone on the broader team to not leave a 16Z for a Frontier Lab. And one of my arguments was that there was a good long-term career here. And the response uh that this person gave me was we'll have AGI, we don't need careers in the long term. Um, and it really hit me because I thought I was AGI pill, but I had really not thought about from that perspective. Um, and I'm curious, you know, we talk about the product improving, right? Can you make that concrete for us? Like what are some of the oh moments as you improve your product for your customer either from your end or your customer's end if you can share on like, oh my god, I didn't realize AI could do that. And then of course I'm going to ask you your thoughts on AGI and what that timeline looks like because you're in the nitty-gritty trenches of the enterprises using AI. So you may have a different perspective than you know we do.

</details>

**Speaker A**: 我想说的第一件事是……我相当确信在 AGI 之后仍然会有职业存在。这样说的原因在于……

<details>
<summary>Original English</summary>

**Speaker A**: The first thing I want to say is uh I'm like certain there will be careers after agi. The reason for that is

</details>

**Speaker B**: 就像我们的大部分工作一样。

<details>
<summary>Original English</summary>

**Speaker B**: like most of our jobs

</details>

**Speaker A**: 肯定，我们的工作从一开始就有点像是被虚构出来的。大部分工作都是毫无意义地制造出来的。一个非常真实的工作……

<details>
<summary>Original English</summary>

**Speaker A**: for sure are for jobs are kind of like made up to begin. Most jobs are made selfless. A very real job

</details>

**Speaker B**: 除非你是在比如修建基础设施，或者种植食物之类的。否则，就像大多数工作都像是在其他事物之上构建的抽象层一样，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: unless you're like building infrastructure or like growing food or something. It's like like most jobs are kind of like layers of abstraction built on top of like other stuff, right?

</details>

<!-- chunk 5/11 -->

### AGI时代的职业与Agent的演进

**Jesse**: 这并不是说这些工作没有价值。只是它们在某种程度上是被创造出来的。所以当AGI（通用人工智能）到来时，它会改变人们的工作，但人们依然会创造出新的工作，因为你仍然需要为其他人提供服务和做事情，诸如此类。所以我真的不认为在AGI之后，职业会消失。我不觉得人们只会无所事事地坐着。

我想分享一个观察，对我来说，那绝对是在我们构建产品的早期阶段，也就是开发Duet的时候。我们正在解决的核心问题，回到“销售主导”这一点，就是我们与许多客户交谈时，他们会说：“是的，我们希望从你们为我们构建的产品中获得的价值是，我们可以把它放在客户面前，它可以进行对话，给他们带来更好的体验。而且，在运营上也为我们省了很多事。你们不仅在帮我们节省成本，还让我们的客户更满意。”这就是我们构建的第一个Agent，也是我们在前一到两年里致力于开发的核心Agent。而在我们这边，构建这个Agent需要做大量的工作。比如，我们必须编写这些流程代码，我们创造了自己的一套流程格式，称之为“Agent操作程序（AOP）”，用来教AI如何做事。我们还必须编写各种工具，让这些程序能够访问系统、调用API等等。在那之后，我们还需要创建所有的测试，以确保这东西能正常工作，并能够模拟各种不同的场景。在这之后，一旦它们投入生产，我们就得手动去阅读对话，对吧？即使我们正在构建的核心产品本身就是一个Agent，其中也包含了大量的工作。

所以，Duet到底是什么呢？它有点像是一个独立的Agent。它像是一个更大、更慢的第二个Agent，但它的工作就是去执行我刚才描述的所有任务。所以现在，我们不需要再手动编写这些AOP，不需要向他们的系统编写集成和工具，也不需要编写测试和监控对话，Duet可以直接完成所有这些事情。它是一个足够聪明的第二个Agent，能够处理所有这些工作。这感觉非常神奇，因为你简直可以直接告诉它：“嘿，目前我还没有构建任何东西，但这里有一堆我的记录，这里有一些文档。你去想出一个最好的方法，把我想要的这些程序都执行好。”

<details>
<summary>Original English</summary>

**Jesse**: And that that isn't to say like the jobs aren't valuable. It's just they're kind of made up. So when AGI is here, like it'll change people's jobs, but every people sell jobs because you're still going to do things for other humans and and whatever. So I I don't really believe that careers will be gone after AGI. I don't think people are just going to be sitting around.

I'll say one observation which is like for me it was definitely um duet so early days when we're building the product right like the the core problem we're solving again being back to salesled is we talked to a bunch of customers and they're like yeah the value we want to get out of what you're building for us is that we can put it in front of customers they can have conversations and it's giving them much better experience and also it's like you know way easier for us operationally right it's like you're saving cost and you're making customers happier so that's that's like the first agent that we built and that was like the core agent we we worked on for the first like year year to two years and the agent on our end when we were building it consisted of a ton of stuff like we would have to um you know write these procedures and we kind of create our own format of procedures we call them agent operating procedures that teach the AI how to do things we had to write these tools that the procedures can use to access systems and pull APIs and whatever and then after that we need to like create all these tests to make sure that this thing is working well and that you can kind of simulate all these different sit situations and afterwards once they're in production like we would manually be reading conversations, right? There's like a ton of work that goes into it even though the core product we're building is is itself an agent.

And so what duet is is it's kind of a separate agent. It's like a second agent that's much bigger, much slower, but its job is to do all the tasks I just described. So now instead of us having to write these AOPs and write these integrations and tools into their systems and write these tests and monitor the conversations, do just does all of that, right? So it's like a it's a second agent that is smart enough to do all these things and um it's it just feels very magical because you can just literally tell it like hey I've nothing built yet so far, but here's a bunch of transcripts I have and here's some documentation. like you go figure out the best way to like do these all these procedures I want

</details>

**Jesse**: 然后它就会去执行。接下来，它还会自发地编写与这些程序配套的测试和模拟。一旦你完成了这些，并将它实际放到客户面前，它就会成为监控所有对话的角色，它会标记出哪些地方做得好，哪些地方做得差。它会说：“是的，我读了这上千段对话，事实上在这个话题上我们表现得很糟糕，我注意到了这点，并且我已经为你起草了这些改进方案。”这就让人觉得：“哇，这就像是一个能包揽一切的Agent。”这非常神奇，因为首先，在我们刚创办公司时，这是不可能实现的。只有当所有的推理模型变得更好时，这一切才成为可能。当然，Anthropic、OpenAI 正在构建这些推理模型，主要是为了那些大型云代码之类的场景，但它们在像 Duet 这样的应用上也表现得非常好。这也是一个令人惊叹的时刻，让人觉得：“哦，哇，首先你可以清楚地看到模型随时间的进步。”

<details>
<summary>Original English</summary>

**Jesse**: and it'll go do it and then of its own accord it'll also write the tests and simulations that go along with those and once you're done with that and you actually put in front of customers it'll be the one that's monitoring all the conversations and it'll flag things where things are going well or poorly and it'll say like yeah I read you know these thousand conversations and actually there's this one topic that we do really poorly on and I've noticed that and I've also drafted these improvements for you so it's like wow It's like one agent that can do all of that. And so that that's very magical because well first of all it was not possible when we first started the company. It only became possible when all the reasoning models got better and of course anthropic open are making these reasoning models mostly for like the cloud codes of the world but they are also really good for like duet for example and that was kind of like a moment where it's like oh wow like first of all you can just see the improvement over time of the models.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Jesse**: 其次，它可以完成所有这些任务。我们原本不期望AI能够同时处理所有这些任务，但它确实做得非常好。我认为这是一个非常直观的感受：“好吧，哇，这些模型正在变得越来越好，它们变得非常通用。”你知道，它们能做所有这些事情。很显然，这些模型并没有针对我们的特定任务（比如编写流程和测试）进行过训练，但它们依然很擅长做这些。

<details>
<summary>Original English</summary>

**Jesse**: And two, it can do all these tasks where it just would not be able we would not have expected AI to be able to do all these tasks at once, but it can do them very well. And um I think that's that was like a very visceral moment of like, okay, wow, the models are getting a lot better and they're becoming like very generalized, you know, like they can do all these things. Like clearly the models were not trained on like our specific task, which is you writing these procedures and and writing these tests, but they're still good at it.

</details>

**Speaker B**: 另外，回答你关于我们是如何想出所有这些东西，以及产品是如何改进的另一个问题。Jesse 刚才谈到的每一件事，都是我们的前线部署人员实际操作后，我们再去弄清楚如何将其产品化的结果。例如，我们意识到：“嘿，当我们接触一个新客户时，我们需要花这么多时间手动编写AOP。” 我们就在想：“哇，这太耗时了，我们该如何将其产品化？” 于是我们把它做进了 Duet。第二部分我们称之为 Duet Autopilot，因为在我们构建了 Duet 之后，人们开始使用它来编写内容，然后我们又发现：“哦，哇，在Agent上线后，对其进行迭代（比如审查对话、弄清楚如何改进它）仍然需要花费大量的时间。” 于是我们觉得：“太好了，让我们将其产品化为 Duet Autopilot。” 事实上，AOP 本身也是在这种确切的场景下诞生的。因为在 AOP 之前，你必须用代码编写所有这些流程，然后我们发现：“哦，这需要耗费大量的部署工程工作来用代码编写所有这些东西。哇，如果我们能通过用纯文本编写来将其产品化，那岂不是更简单、更高效吗，对吧？” 所以我们对于产品改进和部署工程投资的思考方式是，一切都围绕着“我们能从前线部署工作中将什么产品化，从而使工程师和团队中任何面向客户的资源不需要如此深度介入”来展开。

<details>
<summary>Original English</summary>

**Speaker B**: And also um to your other question of how you know how did we come up with all of this and how how did the product improve every single thing that Jesse just talked about was the result of four deployed people doing things and us figuring out how to productize it right so for instance um we realized that hey when we go into a new customer we need to spend all this time writing up the AOPs manually and we're like wow this is quite a lot of time how do we productize this and we built that into duet and then the Second part which we called duet autopilot was uh once we built duet you know people were using duet to write things up and then we're like oh wow there's still a lot of time that goes into iterating upon the agent right once it goes live like reviewing conversations figuring out how to improve it and we're like great let's productize that as det autopilot in fact AOPs themselves were a result of this exact scenario because before AOPS you would have to write all these procedures in code and then we found that oh it's taking a lot of for deployed engineering work to write all these things in code. Wow, wouldn't it be so much easier and efficient if we could productize it by writing it in plain text, right? So the way we think about like product improvements for deployed engineering investment, everything is built around what can we productize from forward deployed work so that engineers and any kind of customerf facing resources on our team don't need to be kind of as heavily involved.

</details>

### 护城河与未来的企业AI

**Host**: 我能就这个思路直接问你一个尖锐的问题吗？我们之前已经讨论过为什么 OpenAI 和 Anthropic 不会是最后的初创公司，你们也谈到了为什么有空间容纳更具体的用例和特定公司。但是，你们也曾有过那种“哦”的时刻，觉得这些实验室变得越来越强，模型也变得越来越好。那么从长远来看，假设我们实现了 AGI，模型能够做我们今天甚至无法想象的各种事情。在这一切发生之后，Decagon 最终的护城河是什么？为什么 Decagon 在 10 年后仍然有存在的理由？

<details>
<summary>Original English</summary>

**Host**: H can I ask you as like kind of a blunt question on this line of thinking? So I know we've already talked about like why open Aan anthropic won't be the last startups and you've talked about like why there's room to have like much more specific use cases and specific companies but you know you you you've also got had like oh moments where you're like these labs are getting so much better and the models are getting so much better. Um and so long term let's say like we we hit AGI and the LA the models can do all sorts of things we can't even imagine today. What's decagon's moat at the end of the day after all of that and like why does decagon like 10 years from now still have a right to exist?

</details>

**Speaker B**: 我认为在短期内，护城河实际上是与企业资源协同工作的能力。我的意思是，今天模型的能力远远大于它们在企业内部的实际应用。你不能仅仅拿一个模型说：“我只要给这个模型企业内部所有东西的访问权限，它就会自己弄清楚一切。” 在现实中，这些东西并不是这样运作的。要让这样的模型在企业内部可部署，假设每个模型都是完美的，不会犯任何错误，但为了在企业中部署，你需要这么做：“好吧，我需要一种方法来告诉模型它能做什么、不能做什么，并确保它不会做出任何灾难性的错误。” 接着，“我需要一种方法，确保企业内的数百人能够协作，以确保 Agent 在他们作为专家的用例中表现得如预期一样。” 然后，“我需要一种方法来测试这个模型，确保它没有越过我设定的任何监管红线，并通过测试确保它运作良好。” 最后，“我需要一种方法来审查发生的数百万次对话，以便为我团队的其他人提取洞察”，对吧？所以，你需要围绕这些模型构建大量的基础设施和软件，使它们能够在企业中部署，让它们能够与这些公司拥有的所有传统系统协同工作。因此，我认为在接下来的几年里，这可能是这些模型能够发挥作用的首要条件。至于以后，当它变得商品化，因为 Agent 可以动态地构建这些东西时，我不知道，我们三年后再看。顺便说一句，我认为只有...

<details>
<summary>Original English</summary>

**Speaker B**: I think in the short term actually it is the ability to work with enterprise resources and what I mean by this is that the capability of models today is far greater than they are being used for within the enterprise right by which you can't just take a model and say I'm just going to give this model access to everything within the enterprise and I'll it'll just figure everything out right like that's practically not how these things So to make models like this deployable within the enterprise, right? Like let's assume that every model is like just perfect and makes no mistakes. But to make something like this deployable within the enterprise, you need to say, okay, I need a way to be able to tell the model what it can and cannot do and make sure that it cannot do anything like catastrophically wrong. Then I need a way to make sure that, you know, hundreds of people within the enterprise can collaborate to make sure that the agent is behaving as expected in the use cases in which they are experts. Then I need a way to be able to test this model and make sure that it doesn't cross any like regulatory lines that I have and test it, make sure it works well. Then I need a way to, you know, look over the, you know, millions of conversations that happen for me to extract insights for the rest of my teams, right? Right. So there's a lot of just infrastructure and software that you need to build around these models to make them deployable within an enterprise to make them be uh work with all the legacy systems that these companies have. And so I think for the next few years that's probably going to be a you know the primary thing that these models need to be able to work. uh now once that gets commoditized because the agents can build that on the fly that I don't know and we'll figure out in three years from now by the way I think just

</details>

<!-- chunk 6/11 -->

### 向大型企业销售AI：从“大卫与歌利亚”的悬殊较量到双雄争霸

**Interviewer**: 听你们刚才的讲述，非常明显的一点是，你们几位极其深刻且透彻地理解了究竟应该如何向企业级客户销售人工智能（AI）产品。而且，我这里指的不仅仅是你们所熟悉的那些中端市场客户，或者是那些刚刚完成首次公开募股（IPO）的新兴公司。我正在谈论的，是世界上一些规模最大、最顶级的跨国巨头和顶级企业。嗯，而且我认为这一点变得尤其引人入胜且极其有趣，因为你们两位创始人在技术层面上都非常非常硬核，是极其精通技术的专业人士，但同时，在“走向市场”（Go-To-Market）的商业推广战略和销售执行力上，你们也简直就像是敏锐而极具攻击性的“猛兽”一样，充满了无尽的野心与无与伦比的行动力。嗯，所以我非常希望能够稍微深入地探讨一下这个特定的话题。嗯，但是你也知道，这种感觉就像是，你们成功地扭转了一个原本看起来极其艰难的开局。一开始，这种市场竞争的动态格局，给人的感觉更像是一个势单力薄的“大卫”，不仅要面对一个，而是要面对多个实力悬殊、极其强大的“歌利亚”巨人的围剿。然而，你们却将这种看似完全不对等的市场动态，实实在在地转化成了现在这样——主要是你们（Decagon）与 Sierra 之间展开的“双雄争霸”的激烈赛马格局。嗯，所以，请更加详细地与我们分享一点，为什么世界上一些规模最为庞大的顶级企业客户，最终都会选择从你们这里购买产品和解决方案。而且，我认为对于我们这些人——你知道的，也就是那些在过去十多年里一直密切研究应用软件行业发展轨迹的人来说——真正让我们感到非常不可思议和引人注目的是，你们达成这些交易的销售周期竟然短得令人感到疯狂。我的意思是，我绝对确信，你们带着强烈的商业紧迫感，肯定还希望这些销售周期能够变得更快，但是，就像通常情况下的行业惯例那样，你通常不可能如此迅速地将规模如此之大、金额如此之高的合同，销售给体量如此之庞大、内部流程极其复杂的企业，对吧？那种级别的企业销售，有时候光是走流程就需要耗费长达两年的漫长时间。所以，嗯，也许可以就这一点再多分享一点深入的见解。这是一个包含了很多层面的长问题，但核心就是：你们是如何将这种惊人的商业化成功发展起来的？你们在创立这家企业的时候，就已经自带了这种成熟的商业化直觉和销售能力了吗？究竟是什么样独特的价值主张，引起了这些大型跨国公司的强烈共鸣，从而让你们能够如此顺利地切入他们的业务，并以如此惊人的速度向前推进？

<details>
<summary>Original English</summary>

**Interviewer**: listening to you guys it's very clear that you guys deeply understand how to sell AI to the enterprise and I don't just mean you know mid-market newly IPOed companies I'm talking about some of the largest companies in the world um and I think this is particularly interesting because you you both are very very technical but also go to market animals Um, so I want to talk a little bit about that. Um, but you know, it just feels like you've turned what maybe started as feeling more like a David and Goliath with multiple Goliaths. Um, uh, market dynamic to really a two-horse race between you and Sierra. Um, so share a little bit more about why some of the largest enterprises in the world are buying from you guys. And I think what's really remarkable to us as people have, you know, studied application software for, you know, over a decade, the sales cycles are crazy fast. I mean, I'm sure you guys with urgency want them to be faster, but like usually you don't sell contracts that big to enterprises that big, right? That takes two years sometimes. So, um, maybe just share a little bit more on this is a long question, but like how did you grow that commercial? did you come with that into founding the business and what's resonating with these large companies that enables you to get in and move so quickly?

</details>

**Decagon Founder**: 是的，我的意思是，我们对于 Sierra，以及这个领域的其他各位同行，总体上都怀有非常深厚的敬意，尤其是对于那些规模庞大的大型平台，就像他们所有人一样。我认为，那些大型平台本身的动作和反应速度，可能会显得稍微有些缓慢。但是我认为，我们已经与那些平台中的许多团队打过交道、见过面了，他们绝对都是非常有能力、极其胜任工作的优秀团队。只是，他们目前所处的境地，要求他们必须同时针对许许多多不同的复杂事项进行优化和平衡。嗯，关于 Decagon 对比 Sierra 的问题。我的意思是，我们最近刚刚签下的一个客户，实际上正是主动停用了 Sierra 的产品和服务，从而转投到了我们 Decagon 的怀抱。当我们向他们询问做出这种转变的具体原因时，嗯，它基本上又回到了这个关于“部署模式”（deployment model）的核心问题上。这就好像，你知道的，当他们之前与 Sierra 合作的时候，服务交付主要依赖于全职的驻场工程师或者说是前线部署工程师（FTEs，Forward Deployed Engineers/Full-Time Equivalents）。这就让整个系统感觉就像是一个完全不透明的“黑盒”。在那个黑盒里，你知道，那些全职工程师确实非常优秀，但是，客户如果想要做任何事情，都必须通过这些工程师才能完成。所以，如果他们想要构建哪怕是全新的客户交互旅程（journeys），或者，嗯，甚至只是想对自己系统对话中究竟在发生什么获得一个稍微更深入一点的理解和洞察，他们都无能为力。然后，随着时间的不断推移，这种对外部人员的绝对依赖，在很大程度上就形成了对他们推进业务速度的一种巨大阻力。对吧？所以，在最开始的初始部署阶段，那种手把手的保姆式服务确实是很好的；但是，随后随着时间的推移，也许那些全职工程师被调配去负责其他项目或其他事情了，这时候客户就会发现，他们仅仅是为了获取系统内部正在发生什么的基本洞察，就需要耗费相当长的一段时间，更不用说再去构建全新的客户交互旅程了，对吧？所以，在过去长达一整年的时间里，他们也许仅仅只构建了……嗯，我想他们当时告诉我们的是，只构建了三个新的旅程。

<details>
<summary>Original English</summary>

**Decagon Founder**: Yeah, I mean we we have a lot of respect for for Sierra and also just you know other folks in the space generally the big platforms like they all I think the platforms themselves move a bit slower but I think that we've we met a lot of those teams they're very competent teams they're optimizing for a lot of different things at once. uh Decon versus Sierra. I mean our our most recent customer actually uh turned off of Sierra to come to Dekagon and sort of the reasoning if when we asked them was um it was this kind of goes back to this like deployment model. It's like you know when when they worked with Sierra it was mostly FDES and it just felt like a black box where you know the the FDs were good but they had to go through the FDS for everything. So to build new journeys or to uh even get like a deeper understanding of what was happening in the conversations and then over time that that kind of just created a lot of drag on how quickly they could move right so in the initial deployment that was good but then over time maybe the FDES were staffed other things and it just took them a while uh to get insight into what was happening and then build out new journeys right so over over the course of the year they maybe built out uh I think they said three

</details>

### 产品化思维与透明的“玻璃盒”模式

**Decagon Founder**: 嗯，所以，他们之所以最终决定找到我们并与我们合作，正是因为他们经历了那种深深的挫败感和无力感。他们渴望能够采用一种截然不同的模式，一种在本质上更加高度“产品化”（productized）的模式，对吧？这又完美地契合了我们在企业愿景中极其强调的“以产品为驱动”（product driven）的核心理念。我们的想法是，客户理应拥有一个属于他们自己的核心产品基础架构。在这个架构下，即使我们依然在现场为他们提供各种帮助，即使我们依然提供前瞻性的部署支持，那也应该仅仅是一种辅助性的服务，其最终目的是为了帮助他们构建起一个他们自己就能够完全独立使用、能够进行极其快速的自我迭代，并且在某种程度上，能够将一切控制权都牢牢掌握在他们自己手中的强大产品，对吧？因此，相比于那种不透明的“黑盒”（black box），我们更喜欢把我们的这种模式称之为“玻璃盒”（glass box，即白盒/透明盒）方法。并且，嗯，是的，所以在短短大约一个月的时间里，他们就已经在 Ducky（Decagon的产品/平台）上迅速上线了大约七个全新的客户交互旅程。

<details>
<summary>Original English</summary>

**Decagon Founder**: um and so the reason they came to us is because they they had that frustration and they wanted to kind of have a different model where it was a lot more productized, right? Back to us being like very product driven in our vision. It's they should have a a core product that even if we're there helping them, even if we are forward deployed, it is like a in in service of helping them build a product that they can use themselves and iterate really fast and and kind of have everything in their control, right? So, we like to call this like a glass box approach instead of a black box. And uh and yeah, so within a basically a month they spun up like seven new journeys on Ducky.

</details>

**Interviewer**: 哇哦。这确实令人惊叹。是的。主要是因为速度上的巨大反差。

<details>
<summary>Original English</summary>

**Interviewer**: Wow. Yeah. Mostly

</details>

**Decagon Founder**: 而他们之前可是足足花了一整年的时间，才勉强完成了三个。

<details>
<summary>Original English</summary>

**Decagon Founder**: and it had taken three a year to get three.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Decagon Founder**: 好的。非常有趣。所以这实际上很大程度上就是关于产品迭代速度的问题。就像，会有一些企业团队真的非常喜欢这种自主感，他们会觉得：“嘿，太棒了，我们完全拥有对系统的控制权。”我们自己的团队，特别是我们团队中那些完全没有技术背景的业务人员，都可以直接进入系统，亲手去进行各种操作配置，而且他们能够清晰地理解在那些AI客户对话中究竟发生了什么。或许，在市场上也存在着另外一些团队，他们实际上就是喜欢那种：“嘿，你们作为供应商，帮我们把一切都包办了吧。”嗯，存在那种倾向的模式。但这正是这两种不同方法论之间的根本差异所在。而这也正是为什么我想说，我们在那些真正追求自主和速度的企业那里，取得了非常巨大成功的原因所在。然后，如果我们把视角拉远一点，仅仅单纯地讨论如何向大型企业进行销售这个问题。是的。我的意思是，这确实是一个，嗯，你知道，Asha 和我以前都绝对从未涉足过的领域，我们以前从来没有任何向企业进行大规模销售的经验。而且我认为，这仅仅是刚好碰巧我们两个人都非常享受这种过程，嗯，我们都觉得销售工作令人感到无比兴奋和刺激。

<details>
<summary>Original English</summary>

**Decagon Founder**: Okay. Interesting. So it's just kind of the speed of iteration like some teams will really like this like hey we have control of it. We our teams especially our non-technical people can come in and do things and they understand what's happening in the in the conversations. And maybe there's other teams out there that actually do like the like, hey, you guys do everything for us and uh that approach. But that that's kind of the difference in the approaches and that's why we've been I would say having a lot of success there. And then zooming out just selling to the enterprise. Yeah. I mean this is something that uh you know Asha and I have never sold to the enterprise before and I think it just so happens that both of us um find sales exciting

</details>

**Decagon Founder**: 而且进入企业级销售领域，对我们来说有点像经历了一条极其陡峭但非常快速的学习曲线。所以，我不认为……老实说，我认为这其中的很大一部分成功，都是顺理成章、自然而然发生的，仅仅是因为我们所处的这个AI领域现在实在是太火热、太炙手可热了。而且，总体来说，在与这些企业高管的商务对话中，我们实际上并不需要真的费尽心机去试图说服人们，让他们觉得：“嘿，你应该投资这个领域。”更多的交流情况是像这样的：“嘿，你们已经决定要投资AI了，而我们，正是最适合你们、最正确的解决方案和实现路径。”所以，这就变成了：“那么，就请像合作伙伴一样与我们携手吧。”而且，嗯，是的，在与那些庞大的企业打交道时，真正的关键点仅仅在于，你得知道如何在这个极其庞大且错综复杂的组织架构中游刃有余地穿梭导航，并且，你必须真正具备深刻的同理心，去设身处地地理解他们真正在乎和看重的价值是什么，以及他们内心深处真正害怕和担忧的风险是什么。

<details>
<summary>Original English</summary>

**Decagon Founder**: and the enterprise it was kind of like a quick learning curve for us. So, I don't think I think a lot of it honestly came kind of naturally just cuz our space is so hot and like generally in these conversations we're not really having to convince people to like invest in this space. It's like more of hey, we're the right approach for you. So, like you partner with us and uh yeah, with the enterprises it's it's really just about like navigating the orgs and really having empathy for what they value and what they're afraid of.

</details>

### 早期销售团队的建设与市场强攻策略

**Decagon Founder**: 嗯，所以是的，我的意思是，我们只不过是回到了那种“以销售为导向”（sales-led）的底层思路上，对吧？就像我们从创立公司的第一天起就确定的那样，我们当时就说：“嘿，我们一定要在市场推广（go-to-market）这一端建立起极其强大的统治力。”而这种强大的市场端力量，将会反过来为我们的产品研发提供宝贵的指导和信息输入，尽管我们内心深处一直抱有这种“产品驱动”的核心哲学。比如，我们绝不想仅仅是关起门来，凭空做梦般地想出一些随机的、不接地气的产品功能去盲目构建。嗯，所以，我们一直都将这种极其重视市场的DNA深植于公司之中。然后在早期的那些日子里，我们确实就是，是的，在市场上极其凶猛地拼命推进。而且我想我也必须强调一点，我认为我们算是有点受到了命运的眷顾，非常幸运地拥有了一支极其强悍、战斗力极强的早期销售团队。

<details>
<summary>Original English</summary>

**Decagon Founder**: Um, so yeah, I mean we we just back to being salesled, right? Like we we always from the beginning were like, hey, we're going to be like extremely strong on the go to market side and that's going to inform the product even though we have this product driven philosophy like we don't want to just be dreaming up random products to build. Um, so we always had that DNA and then in the early days we were just yeah pushing really hard and I think I also want to say I think we got kind of blessed with a a really strong early sales team

</details>

**Decagon Founder**: 并且我们在那个销售团队中，确实汇聚了一大批非常有才华、能力极其出众的精英人才。正是这批人，帮助我们在与，你知道的，那些巨无霸级别的大型企业进行谈判和对话时，真正获得了巨大的杠杆优势和商务筹码。

<details>
<summary>Original English</summary>

**Decagon Founder**: and we have a lot of really talented people in that group and that helped us really get leverage as we were talking to you know the big enterprises

</details>

**Interviewer**: 我记得，在你们公司早期的那些时候，他们其中的一些销售人才，甚至是通过冷邮件或直接主动找上门（cold applied）的方式，来申请加入你们团队的。

<details>
<summary>Original English</summary>

**Interviewer**: some of whom cold applied to you guys in the early days I remember.

</details>

**Decagon Founder**: 是的。对的。没错。

<details>
<summary>Original English</summary>

**Decagon Founder**: Yes. Yeah. Yeah.

</details>

**Interviewer**: 是的。完全是冷启动式的主动申请。嗯。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Cold cold applied. Um

</details>

**Decagon Founder**: 因为我认为他们当时已经在这个AI行业领域里工作了，而且他们从远处就已经在密切关注，并且敏锐地看到了 Decagon 当时正在着手开启的一系列具有颠覆性的事情。

<details>
<summary>Original English</summary>

**Decagon Founder**: cuz I think they were working in the in the space already and they they were seeing from afar like what Decagon was starting to do.

</details>

**Interviewer**: 是的，绝对如此。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**Decagon Founder**: 是的。所以他们中的一些人甚至拥有的像是那种完全非传统的销售背景，你知道。因此，他们是带着非传统的销售经验，跨界进入到这个前沿科技销售领域的。我们在早期拥有的另外一种非常普遍的典型员工画像，就是那些简直像是……常春藤盟校（Ivy League）里的顶级运动员一样的人，我猜可以这么形容。而那些具备这种高度竞争性和自律性画像的人，在某种程度上为我们这整个销售群体奠定了极其优良的素质基础。而且你知道，随着业务的爆发，我们不得不以极快的速度去扩张和扩大那支团队的规模，而这在任何时候都绝非易事。所以，在员工的赋能培训体系（enablement）、内部流程以及组织结构建设方面，确实还有一些事情是我们目前仍在拼命追赶和努力完善的。但是，嗯，因为我们在销售端一直保持着那种无与伦比的高强度，而且整个公司里的每一个员工都清醒地知道，就像你知道的，在这个公司里，一切的起点都是销售，并且这种以销售为核心的紧迫感会像波纹一样，不断地反向传递到研发和运营等每一个后方环节……嗯，你知道，我们始终保持着那种高度一致的专注力。

<details>
<summary>Original English</summary>

**Decagon Founder**: Yeah. So some of them had like non traditional sales backgrounds, you know. So they had nontraditional sales backgrounds. They're coming into sales. The other profile we had a lot of in the early days were just like like Ivy League athletes, I guess. And those profiles were kind of a good foundation for the group. And you know, we've had to scale that team really fast, which is never easy. So there are things that we're still trying to catch up on in terms of enablement and and or structure, but um because we've always had that intensity on the sales side and the whole company knows that like you know everything starts with sales and it kind of propagates back um you know we've always had that focus.

</details>

### 产品化部署与消除企业内部阻力

**Decagon Founder**: 那个，你知道，我认为极大地帮助了我们的另一件至关重要的事情，嗯，你知道，回扣到你早些时候提出的那个核心疑问，也就是“你们究竟是如何能够如此迅速、令人难以置信地达成并完成其中一些规模巨大的企业级交易的”？那是因为，嗯，我认为我们当时展现出了极度的好奇心和探索欲，我们一直在绞尽脑汁地思考，我们究竟应该如何将企业内部复杂的部署过程，提取并转化成可以标准化的产品功能，对吧？我的意思是，我们绝对不是那种只会傲慢地对客户说：“嘿，这里有一个已经做好的产品。我们将把它直接扔过墙给你们，然后，你知道的，你们大概要苦苦摸索一年之后才能真正把这个系统用起来”的公司。绝对不是。因为在许许多多这类大型企业的内部，除了“这个创新产品到底能不能为我的业务带来实际效果”这个首要疑问之外，他们内部团队还需要面临和回答的一个极为现实的问题是：“我到底能不能真的在现有的IT架构下，把这个极其复杂的系统成功上线并投入实际运行？”对吧？而且，在很多这类大型企业的现实环境中，要做到这一点实际上是极其错综复杂、充满挑战的，尤其是当你身处于金融服务等受到极其严格监管和高度安全审查的特殊行业时，情况更是如此。所以，我们实际上在前期投入了大量的心血和时间，去将客户旅程中的那一部分，也就是涉及落地部署的每一个关键环节，绘制和梳理得非常详尽、极其完善。这样一来，当我们就这样满怀信心地走进这些大型企业中的任何一家时，我们都能够以一种非常颗粒度极高、极其细致入微的专业方式，引导他们清晰地了解整个过程：我们究竟将如何从今天的第一次初次接触和会议，一步一步稳扎稳打地走向最终 100% 成功上线并全面投入生产环境的最终目标。

<details>
<summary>Original English</summary>

**Decagon Founder**: the, you know, the other thing I think that helped us a lot, um, you know, to your earlier point about how did you get some of these large deals closed so quickly was, uh, I think we were very curious about how we could productize parts of it within the enterprise, right? By which I mean, we aren't a company that just says, "Hey, here's a product. We'll throw it over the wall and, you know, you get it a year later." Because within a lot of these enterprises, the question they have internally in addition to will this product work for me is can I actually get this live? Right? And within a lot of these enterprises, it's actually complicated, especially if you're in financial services and you're regulated for instance. So we actually spent a lot of time sort of uh mapping out that part of the journey very well. So that when we walk in to one of these enterprises, we can walk them through in very granular detail, how we go from this first meeting today to going live at 100%.

</details>

**Decagon Founder**: 所以，是的，你知道，我们会非常专业地告诉客户：“在这个现阶段，对于像你们这样体量和行业的公司来说，嗯，这很可能就是你们内部需要遵循的AI模型风险评估与合规审查流程。这是你们的系统测试和安全验收流程理应呈现的标准化样子。这是我们应该如何严谨地执行初步的灰度发布和试点推广的方式。如果在这个过程中出现任何哪怕是最微小的异常或问题，这也是我们应该如何敏锐地去捕捉它们的方法，这是我们将如何以最快速度去修复它们的预案，以及，这是我们将如何通过建立机制，来确保它们绝对不会再次发生的可靠保障。”所以，我们所销售的产品本身以及其背后的技术能力部分，固然是极其重要的基石，但是对于这些规模庞大的大型公司来说，同样甚至更为重要的一点是，我们能够积极地帮助他们全面、系统地梳理和思考整个复杂的落地流程，以确保能够真正地将这项前沿技术成功部署到他们的实际业务中，并在大规模的生产环境中稳定运行。因为我深刻地认为，这往往是其他那些试图向大型企业销售软件的科技公司最容易忽略、也最不擅长的一个关键痛点。

<details>
<summary>Original English</summary>

**Decagon Founder**: So yeah, you know, at this stage for a company like you, uh this is what your model risk process is likely to be. This is how uh your testing process should look like. This is how we should do the initial roll out. This is how we should catch any issues that come up and how we're going to fix them and how we'll ensure that they don't happen again. So the product and technology part of what we sell is important, but for these large companies, equally important is us uh helping them think through the process to actually get this deployed and at scale because I think that is something that often gets overlooked by by tech companies selling into enterprise.

</details>

**Interviewer**: 是的，绝对是这样，你说得太对了。而且，嗯，顺便说一句，我也完全可以亲自向大家证明和担保你们早期市场推广（Go-To-Market）团队的那种令人惊叹的强大实力，因为我曾经亲自接触并见过他们中的许多精英成员。嗯，话虽如此，我还是不想轻描淡写地掩盖一个事实，那就是你绝对无法想象，有多少次，有一位掌握大权的企业决策者曾私下里对我坦言，其中一个……

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, for sure. And um by the way, I can also personally attest to the strength of your early go to market team, having met a bunch of them. Um, that being said, I don't want to underplay how many times a decision maker has told me that one of the

</details>

<!-- chunk 7/11 -->

### 创始人参与销售的重要性

**Speaker A**: 许多人选择 Decagon 的众多原因之一，就是他们想要在你们身上下注。他们会直接说：“我们认为 Decagon 的创始团队行动将是最快的。这是一个节奏非常快的市场。它每周甚至每天都在变化，我们认为你们能看清棋局并走出正确的棋，因为这不是那种，你知道，在一年甚至六个月内一切都会保持不变的市场。”所以，我很好奇——我的意思是，不要透露太多机密——作为创始人，你们在销售上花了多少时间，这随着时间推移又是如何演变的？

<details>
<summary>Original English</summary>

**Speaker A**: ...reasons of many, right, that they're going with Decagon is they want to make a bet on you guys. They're they'll literally say, "We think the founding team of Decagon is going to move the fastest. This is a very fast-paced market. it's changing on a weekly if not daily basis and we think that you guys are going to look at the chess pieces and make the right moves because it's not sort of like a oh everything's going to be the same in you know a year or even six months type of market. Um so I'm curious I mean don't give up too much alpha here but how much time do you guys spend on sales as founders and how has that evolved over time?"

</details>

**Speaker B**: 呃，我可能把我的大部分时间都花在这上面，大概 80% 吧。

<details>
<summary>Original English</summary>

**Speaker B**: >> Uh I probably spend most of my time like 80% maybe.

</details>

**Speaker C**: 是的。对，我觉得很大程度上就是为了推动速度。所以，部分原因在于，作为创始人之一，你就是必须参与这些会议，而且，你知道，人们想要见见创始人，但同时也是为了弄清楚我如何能成为推动我们团队走得更快的主要力量，以及推动这种合作关系进展得更快。其中一件事就是，你知道，现在我们与世界上几个最大的银行、航空公司和电信公司合作，无论你走得多快，它们仍然是庞大的组织，这需要时间。因此，我们真正努力去做的一件事就是，你知道，把项目拆解开来，这样我们就不必一次性部署到所有的领域和每个用例中，而只是挑选一两个最重要的用例，先拿下一个胜利。

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah. Okay. Um, and yeah, I think a lot of it is just pushing speed. So, some of it is like, hey, like as one of the founders, you just have to be in calls and like, you know, people want to meet the founders, but also it's just how can I be the sort of the main force that's pushing our team to go faster, but also just like the the partnership to move faster. One of the things with that is like you know now we work with you know several of the largest you know banks in the world and airlines and and telos and no matter how fast you go like there's all there it's those are still like massive organizations and it will take time and so one of the things that we really try to do is you know kind of take the project and piece meal it so we're not just deploying across every surface area every use case at once that's really just pick you know one or two of the top use cases and just get a win.

</details>

**Speaker B**: 我觉得这很有帮助，对吧？如果你在一家大银行里斡旋，这就不会像，你知道，你只是很快地签下一个大单，对吧？至少对我们来说不是，也许有些人能做到，但是，是的，这仍然需要大量的努力，而且需要时间。所以你必须想出办法，从流程的角度、组织架构的角度以及产品的角度来设计一些东西，来不断缩短这个周期，并找到一些巧妙的策略，而这就需要创始人的参与。你不能真的指望一个销售团队能不断想出新的配置方案，因为你知道，他们不对产品负责。他们也不对公司运行的端到端流程负责。

<details>
<summary>Original English</summary>

**Speaker B**: And

>> I would say that's that's been helpful, right? If you navigate like a big bank like it's not going to be like a quick like, you know, you just close a big deal,

>> right? At least for us it's not maybe some people can do it but um it's yeah it's still a lot of effort and it's it takes time and so you have to figure out ways to you know design things from a process perspective and an oracle perspective and in a product perspective as well that like just keep shortening that and like finding clever tactics and uh that kind of takes founder involvement. um you you wouldn't really expect a like a a sales team to just like constantly be coming up with new configurations there because you know they're not responsible for the product. They're not responsible for you know the end to end you know process that the company runs.

</details>

**Speaker B**: 所以我认为创始人参与其中非常重要。然后，销售人员的工作就是在销售层面去执行，比如建立标杆项目，以及理顺组织架构等。我们要花大量时间与销售潜客和现有客户沟通的另一个原因还在于，市场变化太快，我们需要能够非常迅速地了解，今天有哪些事情是我们没在做但应该迅速去做的。因为模型的能力一直在变化，随着模型的推出，人们会看到发生的其他事情，然后他们会觉得：“哇，这太酷了。我在别处看到了这个，而你们却没在做。”所以，我们需要能够非常紧密地跟进这个反馈循环，因为这是我们绝对不想失去的。

<details>
<summary>Original English</summary>

**Speaker B**: >> So having the founder involved there is very important I would say and then the sales people their job is to kind of execute on the sales side like build champions and navigate the org and so on. The other reason um to also spend a ton of time with both sales prospects and existing customers is also because the market is changing so quickly being able to really quickly understand

>> what are the things that we are not doing today that we should be

>> doing very quickly right because model capabilities are changing all the time as models roll out people are seeing other things that happen and they're like oh wow this is really cool and like I'm seeing this here and you guys aren't doing that as well. Um so being able to like stay really really close to that feedback loop because um that's something we never want to never want to let go of.

</details>

### 产品路线图与从客服到AI管家的演变

**Speaker A**: 是的。你们想谈谈这如何影响了产品路线图吗？意思是，可能在两年前左右，Decagon 的大多数客户都完全专注于客户支持，而现在我会说实际情况并非如此。你们已经将愿景拓宽，现在主要像是为你们的客户提供一个 AI 管家。你们想谈谈这二者之间的实际区别是什么吗？而且在实践中，这对你们的销售团队和产品团队意味着什么？

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Do you want to talk about how that like informs product roadmap? Meaning

>> probably like two two years ago or so uh most of Decagon's customers were focused purely on customer support and nowadays I would say that's that's actually not true. You guys have broadened your vision to mostly like to be like an AI concierge for your customers. Do you want to talk about what the distinction between those two actually is and in practice like what that means for both your sales teams and your product teams?

</details>

**Speaker B**: 所以你知道，当我们最初推出的一批我们售卖的用例时，它们都是在客户支持领域的。原因是，第一，那是我们许多早期客户面临的最大挑战之一；第二，这也是当时模型能力的极限所在，对吧？也就是那几乎就是它们所能做到的极限。然而，现在随着模型变得更好，我们的客户也意识到了：“嗯，为什么我需要有一套模型只是用来了解我的客户遇到问题时的需求，而当他们来向我购买东西时又需要另一套模型呢？”对吧？因此，我们有一个客户最初是针对客户支持与我们一起上线的。然后他们意识到，他们觉得：“嗯，现在你们非常了解我们的产品了。你们也了解它所具备的功能，因为在做客户支持时必须了解这些。你们知道我们喜欢如何与客户沟通以及我们的品牌调性。那么，你们能帮我们处理入站销售吗？”对吧？当有客户进来时，回答关于我们的问题，做一些需求探索，然后，你知道，如果这笔交易价值足够大，就把它分配给合适的企业级销售代表。我们还有另一个客户，开始将我们用于很多运营工作流中，对吧？所以，一旦我们开始在那个客户的账户上看到任何问题，我们现在就能够主动联系他们。因为归根结底，我们构建的东西，而且从一开始就是有意这样构建的——并不是一个能把客户支持做得很好的智能体，而是一个能很好地遵循业务流程的智能体。归根结底，在日常运营工作流中执行任务、对某些客户支持问题进行销售线索资格审查，只不过是一个遵循业务流程的智能体在起作用。我们在构建它时就赋予了足够的灵活性，让它能做所有这些事情，因为我们意识到：“嘿，到了某一个节点，模型将会变得更好。”而事实也正是如此。

<details>
<summary>Original English</summary>

**Speaker B**: >> So you know all the when we launched the original set of use cases that we sold were in customer support. Um and the reason was because one that was one of the biggest challenges that a lot of our early customers were facing and two that was where the capabilities of the models ended at the time right like that is all that is the pretty much the limit of what they were capable of doing. Now, however, as models have gotten better and our customers have realized, well, why would I have one set of models that just learns about my customers when they have another when they have a problem and something else when they come to me to buy something, right? And so, we had a customer that we originally went live with them for customer support. Uh, and then they realized they were like, well, you know a lot about our product now. You know about the capabilities that it has because you need to do that for customer support. you know how we like talking to our customers and our brand. Um, can you help us with inbound sales, right? When someone comes in, answer questions about us, do some discovery and then, you know, assign it to the right uh uh enterprise rep if it's, you know, a deal of large enough value. We had another customer that um started using us for a lot of operational workflows, right? So uh we are able to now proactively reach out to them once we start seeing um any kind of issues on on that on that customer's account. Um because ultimately at the end of the day the thing that we built and we kind of built this intentionally from the start was not an agent that does customer support well but rather an agent that follows business process well right and executing on operational workflows doing sales lead qualifications on certain customer support questions at the end of the day is just an agent following a business process. And we kind of built it flexibly enough to kind of do all these things because we realized that hey at a certain points the models are going to get better and they have.

</details>

**Speaker A**: 那么模型具体在哪些方面变得更好，从而使你们能够做到这一点呢？

<details>
<summary>Original English</summary>

**Speaker A**: >> And what do they specifically get better at that allows you to do that?

</details>

**Speaker B**: 具体来说就是遵循指令的能力。所以，你看，在几年前你使用模型时，你必须给它非常严格的指导，非常具体的指令，你不希望它偏离这些指令。随着模型变得更聪明，你就可以给它越来越宽泛的指导、越来越大的指令，并相信模型有足够的常识去像人类一样理解它们，并在一定程度上填补任何缺失的空白，对吧？因为对于客户支持而言，你可以让模型遵循一条非常严密的路径，这就是你真正需要的全部。然而对于销售资格审查，你多少希望它去问一些开放式的问题以探索需求。对话将会不可避免地出现起伏和迂回，所以你需要模型能够用合理的内容来进行填补。因此，具体来说这就是模型这些年来有所提升的地方。

<details>
<summary>Original English</summary>

**Speaker B**: >> It is specifically the ability to follow instructions. Well, right. So when you had um models, you know, let's say a few years ago, you'd have to give it very very tight guidance, very specific instructions that you didn't want it to deviate from. And as the models got smarter, you could kind of give it broader and broader guidance, bigger and bigger instructions, and just trust that the models have good enough sense to interpreted like a human would and kind of fill in any missing gaps, right? Because for again for customer support, you can have a very tight path that the model should follow. And that's all you really need. Whereas for sales qualifications, you kind of want to ask open-ended discovery questions. The conversation is going to kind of bob and weave. And so you need the model to kind of fill in with reasonable things. So that's specifically kind of what the what the models got better at over the years.

</details>

**Speaker C**: 是的。我觉得如果你去想，比如“未来的 12 个月产品路线图是什么？”因为现在事物发展得太快了，所以对此真实的回答可能是：我们就边走边看。我们当然知道现在正在开发什么，但现实是，在今天的 AI 领域中，想要制定一个精确到细节的 12 个月路线图是非常困难的。你可能只是有一些你想去构建的东西的主题，但理想情况下，如果你有这些想法，你现在就应该去把它们做出来，因为现在构建东西太快了。所以我认为这是一个因素，但长期愿景对现在的我们来说依然非常清晰，那就是，我们使用了“管家”（concierge）这个词，但这其实仅仅意味着：嘿，一个 AI 智能体应该成为你的企业或品牌的前门，无论是对客户被动响应还是主动接触，每一次互动都应该由 AI 来处理。我们已经看到 AI 在这方面非常擅长，对吧？客户服务就像是其中一大支柱，全都是这些入站的互动；但为什么不同时让它能够去做所有这些其他的事情呢。所以随着时间的推移，我们并不是试图自己去弄清楚这些事情究竟是什么。我们现在有很多客户会向我们传递信号，告诉我们他们在意什么，而那些就将成为我们要去构建的东西。

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah. Um I think if if you think about you know what is the like 12 month product road map because things are moving so fast like the answer the real answer to that is like we kind of like see how it evolves and we obviously know what we're working on now but I think realistically in in today's AI world it's very difficult to have like a a 12-month road map to a tea. you maybe know have like some themes of what you want to build but ideally if you have those things you just build it like right now because it's so so fast to build things now so um I would say that that is that is one element but then the sort of long-term vision is still very clear to us now right which is we use the term concierge but really it just means like hey an AI agent should just be the front door of your business or your brand and every interaction whether it's like reactive or proactive with a customer uh should be handled by by AI and we've already seen that AI is very good at that right customer service is like a huge pillar of that where it's all these inbound interactions but why not have also be able to do all these other things. So over time again we're we're not trying to figure out on our own what these things are. We kind of have now have a lot of customers that will give us signal on the things that they care about and those will be the things that we built.

</details>

<!-- chunk 8/11 -->

### 模型的进步与目前的瓶颈

**Interviewer**: 我们聊了很多关于模型变得越来越好，而且很显然，你们团队的能力甚至跑在了这种技术进步的前面。你们目前观察到的一些瓶颈是什么？无论是在模型能力方面还是其他方面。我也在想，是不是在持久化记忆（persistent memory）方面？我不知道你们是否觉得这一块已经达到了你们期望的水平，或者可能存在其他瓶颈，但我很好奇，你们希望能看到什么样的进步，以及是什么在拖慢你们的脚步？

<details>
<summary>Original English</summary>

**Interviewer**: We've talked a lot about how the models are getting better and obviously your capabilities are moving along even ahead of that progress. What are some of the bottlenecks right now that you're seeing? Whether that's on the capability side. I don't know, it could also be around persistent memory. I don't know if you guys feel like that's kind of up to snuff on where you would like it, or could be other bottlenecks, but curious like what would you like to see and what's kind of holding you back?

</details>

**Speaker A**: 招聘。

<details>
<summary>Original English</summary>

**Speaker A**: Hiring.

</details>

**Interviewer**: 明白了。所以瓶颈更多不在 AI 本身，而是在于……

<details>
<summary>Original English</summary>

**Interviewer**: Got it. So, it's less on the AI side. It's actually like...

</details>

**Speaker A**: 实际上，我们对 token 的消耗量极大，但我们总是希望能招募到更多优秀的人才。我觉得现在有太多的东西需要去构建，所以……

<details>
<summary>Original English</summary>

**Speaker A**: It's actually like we are voracious consumers of tokens but we would always love more great people. I think there's so much to build these days that it's you know...

</details>

**Interviewer**: 那你们为什么不直接雇佣 AI 智能体（AI agents）来帮你们做这些事呢？

<details>
<summary>Original English</summary>

**Interviewer**: And why can't you hire AI agents to do the things that you're doing?

</details>

**Speaker A**: 是的，我们绝对是 token 的重度消费者，我们在这上面的花费非常庞大。但是，你懂的，有些事情我目前觉得还没到能让 AI 智能体来决定“该开发什么”的地步，或者是让它们具备那种……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, we are voracious consumers of tokens, really like our token bills are very very large. But you know there are still things I don't quite yet think we're at the point where we can have the AI agents make decisions on what to build and kind of have that...

</details>

**Speaker B**: 那种能判断“这个功能是否已经完成”的品味。

<details>
<summary>Original English</summary>

**Speaker B**: ...the taste of is this done yet.

</details>

**Speaker A**: 没错，所以我们可以把很多具体的执行步骤外包出去，但我认为它们目前还达不到能决定要开发什么、要舍弃什么等这类事情的水平。

<details>
<summary>Original English</summary>

**Speaker A**: Right, so we can outsource a lot of specific execution steps but I don't yet think they're at the point where they can make the call on what to build, what to exclude, things like that.

</details>

### AI 发展是否改变了招聘需求？

**Interviewer**: 既然模型在不断进步，那么自你们三年前创立公司以来，这是否改变了你们的招聘需求？因为很多人会觉得，“哦，现在你可以打造出一个人的独角兽公司（one-person unicorns）”，诸如此类……

<details>
<summary>Original English</summary>

**Interviewer**: So the models are improving, have they since like you found it three years ago, has it changed your hiring needs at all? Because a lot of people are like, "Oh, you can build like one-person unicorns, you know, like..."

</details>

**Speaker A**: 是的，我觉得这种论调确实经常被抛出来，但我认为一个简单的反例就是：所有那些 AI 编程初创公司都在疯狂地招人。你要知道，他们可以说是这些模型最成熟、最资深的用户了，但他们却在疯狂扩招。我认为原因就在于：现在每个人都能使用这些工具。所以如果我们的竞争对手正在使用它们并构建更多的功能，我们就也需要构建更多的功能，对吧？如果有人说，“这是我们的产品路线图，现在我们可以只花三分之一的时间就把它完成”，然后他们就停止招人了。我们只会把这解读为：“哇，我们可以在三分之一的时间内完成它，太好了！那我们就能构建三倍于之前的产品。”结果你会发现每个人都在打同样的算盘。因此，大家都不仅需要继续招募更多的人手，同时也会交付更多的产品。所以，这对模型的消费者来说是件大好事，但我并不认为它在实质上改变了我们的招聘计划。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, you know, I think this argument does get tossed around a lot, but I think an easy counter example to this is all the AI coding startups are hiring like crazy. You know, they're like the most sophisticated users presumably of these models and they are hiring like crazy. I think the reason is just because everybody has access to these tools and so if our competitors are going to use them and build more things, we need to build more things, right? If somebody else said, "Oh, here's our road map and now we can get through it in a third of the time." And then they just stop hiring. We would just take that to mean, "Wow, we can get through it in a third of the time. Great, let's build three times as much stuff." And turns out everybody, you know, does the same calculus. So, everybody both needs to keep hiring more and ships more. So, it is great for consumers of these models. But I don't think it has materially changed our hiring plan.

</details>

**Interviewer**: 这太有意思了。我本来以为你会说些诸如“语音模型的延迟”之类的问题，但看来在技术瓶颈这方面，情况并不是……

<details>
<summary>Original English</summary>

**Interviewer**: It's so funny. I thought you were going to say something like, I don't know, latency of voice models or something like that, but it seems like on the technological bottleneck side, it's...

</details>

**Speaker A**: 是的，我们确实还在等待一些技术的成熟，对吧？比如说，语音到语音（voice-to-voice）模型就是一个我们非常感兴趣且仍有大量研究在进行的前沿领域。还有就是，让更小参数的模型在开箱即用时变得更加聪明。所以，仍然会有一些我们非常关心并且密切关注的技术进展。但是从商业角度来看，目前的瓶颈较少在于模型端，而更多在于：你到底能不能快速地建立起一家公司。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, there's still stuff that we're waiting for, right? Like voice-to-voice models is an interesting frontier that there's still research happening on. You know, getting smaller models to be smarter out of the box, right. So there are going to be still developments that we are watching closely that we care about, but from a business perspective it's less on the model side and more on the just like can you build the company fast.

</details>

### “Grind Slop” 与办公室文化

**Interviewer**: 嗯，既然我们正好聊到了招聘和团队，你也知道，我觉得“grind slop”（无意义的内卷加班）已经成了 X（推特）上的一个热门话题。这其实很搞笑，因为作为一名风险投资人，我得承认——你们这帮人可是出了名的每周在办公室待上六到七天的。我希望这段话播出后你们不会被打上“grind slop”的标签，但你们确实在为了你们的团队和客户不断拼搏（hustling）。看到这种拼搏精神在某种程度上被反转嘲讽，真的挺有意思。所以我很好奇，你们对外界这种论调有什么看法？虽然“grind slop”是一个很泛泛的词，但你们确实很拼，而且在你们的办公室里也充满了战友情谊和激情。所以能不能多谈谈这一点，以及你们是如何塑造这种文化的？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, actually maybe since we're on the topic of hiring, and you know I feel like 'grind slop' has become this theme on X. And it's so funny because, you know, as a VC, like I'll admit, you guys are famously in the office six, seven days a week. I hope this doesn't get marked as grind slop now, but you know, constantly hustling for your teams and your customers. And it's so funny to see that kind of turned on its head. And so I'm just curious, what are your thoughts on the narrative out there and like, grind slop is such a general term, but like you guys grind, but there's also a lot of camaraderie and excitement in the office. So just say more about that and like how you're building the culture.

</details>

**Speaker A**: 是的，我觉得“内卷（grind）”是个很微妙的词。我们自己从来没有发布过关于“grind slop”的内容，因为我们认为努力工作就只是努力工作……我不觉得人们是为了“卷”而努力工作的。这只是因为确实有很多事情需要去做。人们之所以把大部分时间花在办公室，主要是因为：嘿，这是我们生命中一段非常有趣的时光，我们想要充分发挥我们的才华和潜力，不想荒废它。我认为这是最主要的原因。这也是实现主要目标的手段——即你能不能做出一个好产品，你能不能在这个领域赢下来。而它的其中一个结果就是大家工作得更加努力了。

从一开始，我们确实有一种办公室文化，但我们从不强制员工周末加班，我们也不真的在乎他们在办公室待了多长时间。人们待在办公室，只是为了我们能最大化地沟通，这就是我们的看法。我不觉得我们是在病态地内卷或者有着异常的野心，我只是觉得我周围有很多像我们这样充满野心的人，所有这些人都这样，所以这就成了一种常态。每个人都在努力工作，所以这很正常。所以，我并不觉得它是什么被我们看作非常特别的东西。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I mean grind is a funny term. We have never posted grind slop because we kind of view that like working hard is just like I don't think people are working hard to grind. It's just like oh there's a lot of stuff to do. People spend time there mostly because like, hey, this is like a fun time of our life. Like we want to take advantage of our talent and sort of potential so that it's not wasted. I think that's the main reason, and it's a very sort of like many orders from the main goal which is like can you build a good product and can you win in a space, and it's like one of the effects of that is that people work harder. 

And even from the beginning, like yes we have an office culture, but like we're never mandating people to come in on the weekends. We don't really care how long they are in the office. It's just people are in the office just so that like we can maximize communication and that's how we view it. Like I don't view ourselves as abnormally grindy or abnormally ambitious. I think we just like I have a lot of ambitious people around me like us and all these people so it kind of just becomes normal and like everyone works hard so it's just kind of like normal. So I don't think it's something that we view as you know something like super special.

</details>

**Speaker B**: 对的。而且我们在很大程度上把我们正在做的事情看作是一项团队运动，对吧？在我们的组织架构里，不同部门之间几乎没有界限，你会非常普遍地看到工程师参加早期的销售会议，你会看到销售人员在调试产品的功能，你也会看到我们的 APM（助理产品经理）团队深入参与到两端的工作中。因此，我认为要让这种职能上如此不同的团队协同工作，很大程度上需要大家都在办公室，因为每个人都在一起碰撞想法。

其次，这也让工作在某种程度上变得有趣，因为每个人都在为了某个非常具体的结果而协同工作。无论是为了让交易顺利进行而为某个客户准时交付这个功能，还是为了发布某个新产品。正因为有这么多不同的团队在一起工作，就形成了一种“我们同舟共济，一起把这件事做成”的氛围。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And we kind of also view a lot of what we do very much as a team sport, right? Where we very rarely have lines between our orgs in that you will very commonly see engineers on early stage sales calls. You will see salespeople like debugging parts of the product. You will see our APM team in absolutely both ends of the spectrum. And so I think being able to have teams that are so kind of disparate from a function perspective all working together kind of needs people in the office because everybody's kind of jamming on ideas together, but two it also makes it fun in a way because you know everyone is like working together towards some very specific outcome right? It's either building this thing for this customer in time for the deal to close or launching this new thing. And because it's so many different teams working together, it's kind of a we're all in this together to get this across the line.

</details>

### 公司规模扩张时的文化传承

**Interviewer**: 没错。那么随着公司规模的扩张，你们是如何保持这种文化的呢？你们最近设立了很多新的办公室，有了新的澳大利亚办公室、伦敦办公室，纽约办公室也在飞速扩张。当你们两人都在旧金山的时候，你们是如何维持那种文化的呢？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Well, and how does that scale as you know, you've launched a lot of new offices recently. You have a new Australia office, London office, your New York office is growing like crazy. How do you maintain that culture when you guys are both in San Francisco?

</details>

**Speaker A**: 我也不完全清楚。我的意思是，我不认为这对我们来说是一个已经解决的问题。我们一直在努力解决它，而且每一次公司进入下一个发展阶段时，我们都必须设立一些新的制度，只是为了确保每个人都能理解我们的文化，并且保持极高的责任感。而且这里面是有压力的，因为它本来就该有压力。所以这是我们不断在添加的东西，因为在公司最初只有 100 人的时候，这其实没那么重要，大家都互相认识。但随着你的成长，一些新员工可能没有人向他们传达过愿景，或者没有人向他们传达过文化。

而且，我知道 Ben 曾跟我们谈论过 A16Z 的文化，对吧？比如它是非常注重行动导向的，你不能只是在里面塞一些虚无缥缈的东西。所以，是的，随着我们的成长，我们正努力在这些方面做得更好。另外一点是，我们会让每一位新入职的员工在刚开始的时候来旧金山待上几周，这样他们就能沉浸在原汁原味的文化氛围中。然后，对于每一个新的办公室——现在纽约和伦敦的办公室已经足够大了，它们本身就自带了原汁原味的 Decagon 文化——但对于全新设立的办公室，我们实际上会派一些人从这些中心枢纽过去那边待上几个月，真正去……

<details>
<summary>Original English</summary>

**Speaker A**: I don't know. I mean, yeah, I don't think it's a solved problem for us. Like we're constantly working on it and like every single time the company gets to the next phase there's like new things we have to institute to just make sure that everyone understands the culture and there's like very high accountability and um you know there is pressure because there should be and so that's something that we're constantly adding on because in the first 100 people it doesn't really matter because everyone kind of knows each other, but like as you grow people might not have no one's communicated the vision to them or communicated the culture to them. 

And um yeah, I know like Ben was talking to us about the A16Z culture, right? It's like how it's very like action-oriented and you can't just like put fluffy stuff on there. And so yeah, it's all these things that we're trying to do a better job of as we grow. Uh the other thing is also we bring everybody that we hire out to San Francisco for a couple weeks when they start so they're kind of immersed in the kind of the original kind of soup of culture. Uh, and then for every new office, right, at this point, New York and London, all these offices are big enough that they have the original Decagon culture there anyway, but for brand new offices, we actually have people from one of these hubs go out and spend a few months there really...

</details>

<!-- chunk 9/11 -->

### 维护初期企业文化与国际化扩张的契机

**Speaker A**: ……直到办公室规模变得足够大，并且形成了它自身那种独特的文化，这样一来，它才不至于变得与最初的 Decagon 文化相差太远。实际上，谈到国际化这个话题，我们在去年引进了 Ragu Raghuram，显然，他是 VMware 的前任首席执行官。除了进行投资之外，他还在帮助我们建立大量的国际化能力。我认为我们已经观察到的一点是，我们这类人工智能公司正被极其快速、过早地拉向国际市场。比如，对于你们来说，现在设立一个澳大利亚办公室似乎还为时过早，除非你确实有切实的客户需求在推动你们这么做。考虑到你们公司成立的时间并不算久，你们目前的业务规模实际上已经相当大了。不过，也许你可以多谈谈这一点，比如这是否意味着你们的产品能够很好地适应并无缝转化到这些其他地区的市场中？在企业级客户的关注点和忧虑方面，是更多了还是更少了？或者说，它在某种程度上只是与美国市场的情况相当？

<details>
<summary>Original English</summary>

**Speaker A**: until the office becomes big enough and has its own kind of culture so that it doesn't kind of become too different from what kind of the original decagon culture was. Actually on the topic of international we're so we brought on Ragu Ragnaram last year obviously former CEO of VMware and in addition to investing he's helping us build out a ton of our international capabilities and I think one of the things that we've seen is that our AI companies are just getting pulled internationally way earlier like for you to have an Australia office it seems premature except for the fact that you have customer poll your scale is quite large for you know how long ago you were founded. Um but maybe say more about that like does that translate like does your product translate well to these other geos are there more enterprise concerns or fewer or is it kind of just comparable to the US market?

</details>

### 人工智能的普及与跨越语言障碍的优势

**Speaker B**: 是的，我认为这里存在两个主要趋势。首先，人工智能现在已经成为一种如此普遍且具有颠覆性的现象，以至于外面的每一位潜在买家，你懂的，都已经尝试过 ChatGPT 或者其他类似的产品了。因此，从公司董事会和高管层（C-suite）那里传来了大量的、自上而下的巨大压力，要求他们在某些具体方面必须尽快采取行动、动起来。如果你考虑一下这些企业中的许多家，他们会思考：“嗯，我们究竟该如何采用人工智能呢？好吧，你知道的，让我们来部署一些负责编写代码的智能体（coding agents），还有，我们来做客户服务相关的 AI 应用吧，因为那些看起来是最显而易见、最容易落地的应用场景。” 所以，正如你所指出的那样，市场上确实存在着大量的拉动力。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think there's two trends. one is that AI is just such a phenomenon that every buyer out there has you know tried chat GBT or whatever and so there is a lot of just top down pressure from boards and sees to just get moving on something and if you think about a lot of these businesses they're like hm how do we adopt AI well it's you know let's do some coding agents and like let's do customer service because those are like the obvious ones and so there is a lot of pull to to your points

</details>

**Speaker C**: 紧接着的另一个显著趋势是，借助于人工智能，处理语言层面的问题变得容易多了。所以……

<details>
<summary>Original English</summary>

**Speaker C**: and then the other trend is that language is a lot easier with AI. So

</details>

**Speaker B**: 没错，

<details>
<summary>Original English</summary>

**Speaker B**: yeah,

</details>

**Speaker C**: 在过去，可能存在的一个重大障碍会是，“哦，我的语言无法适用”，或者 “我的应用程序就是不能在德语环境下正常运行”，或者……

<details>
<summary>Original English</summary>

**Speaker C**: in the past maybe a blocker would be, oh, my language just doesn't work in or my app just doesn't work in German or

</details>

**Speaker B**: 对的，

<details>
<summary>Original English</summary>

**Speaker B**: right,

</details>

**Speaker C**: 随便是哪种特定的语言，对吧？但是现在，去调整你的应用程序以适应不同国家和地区的语言已经变得容易得多了。所以……

<details>
<summary>Original English</summary>

**Speaker C**: pick your language, right? But now it's a lot easier is to adapt your app. So

</details>

### 国际化扩张的权衡与本地化挑战

**Speaker B**: 我认为正是因为有了这些原因，国际化扩张的整体速度大大加快了。但与此同时，对吧，我们也希望确保我们的精力没有被分散得太稀薄。因此，这就需要在两者之间寻求一种微妙的平衡，在这种情况下，究竟什么是完美的答案变得非常不清楚。但是，你知道，我们已经在某种程度上做出了深思熟虑的决定，明确了我们愿意真正投入大量资源去开拓哪些市场。而且如果我们决定要进行投资，我们就会，你知道，真金白银地、确确实实地大力投入其中。通常情况下，那些我们选择的市场是我们已经自然而然地通过美国办公室或其他渠道获得了一些客户的地方。

<details>
<summary>Original English</summary>

**Speaker B**: I think for those reasons, international has been a lot faster. Like at the same time, right, like we also want to make sure that we're not getting spread too thin. And so it's kind of this balance where it's like very unclear what the perfect answer is, but you know, we've kind of made a determination of like which markets we're okay with really investing in and if we're going to invest, we're going to, you know, really invest. And generally those markets are ones where we've already just like naturally picked up some customers out of the US office or something.

</details>

**Speaker C**: 是的。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker B**: 然后现在情况就像是，是时候往那些地方部署专业人员了。因为，是的，即便存在这些让人更容易走向国际市场的积极趋势，比如你所了解到的这些，但也存在着其他一些你通常不会真正提前去考虑到的事情，对吧？比如你必须满足数据驻留（data residency）的严格要求，有所有这些方方面面的合规性规定。而且，那里还有本地的竞争对手，他们就是比你更深入地了解当地市场的运作方式，所以你必须非常妥善地去应对和驾驭这一切挑战。

<details>
<summary>Original English</summary>

**Speaker B**: And then now it's like time to deploy people. Um because yeah even though these there are these trends that make it easier to go internationally like you know there's also other things that you don't really think about right like you have to have data residency there's all these things where and there's like local competitors which are just know the market a lot better and so you have to navigate that well.

</details>

### 本地竞争、行业整合与通用平台的优势

**Speaker A**: 是的，绝对如此。你是否认为，对于我们所熟知的那些大型软件和产品类别，存在着让本地竞争对手生存的空间？我的意思是，确实存在属于他们的生存空间。我认为真正的问题在于，从长远来看，是否会出现行业整合（consolidation）？而且，你可以将这种说法同时应用于不同的地理区域，同时也适用于不同的垂直行业领域，以及不同的细分市场，对吧？所以，总会有人在不同的地方找到属于他们自己的利基市场（niche）。比如，我们的观点是，我们之所以在横向扩展上进行如此广泛的构建，原因在于我们坚信，在我们所处的这个领域里，最终的赢家将会是那些通用型的横向平台。这个领域并没有那么多极其垂直化、能够让你看到一个纯粹的垂直解决方案存活下来的东西。而且从历史上看，这在我们这个特定领域一直都是成立的，对吧？比如 Salesforce，它非常具有横向普适性；Zendesk，也是非常横向化的。像所有这些领先的解决方案都是高度横向化的，因为相比于拥有非常特定于某个垂直领域的单一功能，你通过拥有这种庞大的系统规模以及一个极其健壮、稳定且有深度的产品，能够获得多得多的竞争收益。随着时间的推移，我们当然也会在现有架构中构建，你知道的，特定于垂直领域的专属功能，但是我们的核心观点是，从垂直行业和某种市场的宏观角度来看，行业整合终将无可避免地发生。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah absolutely. Um do you think there is a like a space for like local competitors to the large categories that we know about? I mean there is space for them. I think the question is like long-term is there consolidation and it's it's you you could say that for both geographies but also verticals and then also market segments, right? So like there are going to be people that find their niche in different places. Like our view the reason why we've kind of built so horizontally is that we believe that in our space the winners are going to be horizontal. there's just not that much that is like super verticalized that where like you could see a a pure vertical solution surviving and historically that's just been true in our space right like Salesforce very horizontal Zenness very horizontal like all these solutions are very horizontal because you just gain more from having that scale and having a very robust and deep product than you do from like having very vertical specific features and over time we're also going to build you know vertical features into it but our view is that like from a vertical and sort of market point of view there will be consolidation.

</details>

### 人工智能礼宾服务对传统 CRM 系统的影响

**Speaker A**: 顺着关于行业整合这个相关的话题，但也许不仅仅是地理区域上的物理整合。我十分好奇，如果人工智能礼宾服务（AI concierge）真的变成了企业与其客户之间的核心交互界面，你觉得像 CRM（客户关系管理系统）以及所有这些，你知道的，对于最终客户来说非常重要、传统上用于记录核心数据的记录系统（systems of record），对吧？这些系统在这个由 AI 驱动的新世界中会如何演变？你是否预见到了在这些特定领域会发生任何形式的整合？就你们自己所扮演的角色和定位而言。

<details>
<summary>Original English</summary>

**Speaker A**: Just sort of on related to consolidation but maybe not just geographic consolidation. I'm curious if AI concierge becomes really the interface between the business and its customers. Do you see what like how does CRM and all of these you know sort of traditional data very important systems of record right for the end customer um how do those evolve in this new world and do you see any consolidation there in terms of your own role

</details>

**Speaker B**: 是的，我并不觉得……我不认为这必然是一个非此即彼、互相排斥的选择，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: yeah I don't um I don't think it's necessarily an either or right

</details>

**Speaker B**: 因为归根结底，我们在这里正在做的核心事情是，试图让人们能够民主化地访问或获取这些高端的礼宾服务（concierges），对吧？这意味着什么呢？这就好比，如果你去一家企业，你在那里每年消费 10 万美元，你肯定会得到最顶级、最个性化的专属待遇。他们会确切地知道你是谁，你的个人偏好究竟是什么。举个例子，他们想要帮助你购物，他们甚至可能会为了你一个人包下整个商店、停止对外营业。

<details>
<summary>Original English</summary>

**Speaker B**: because ultimately what we're what we're doing here is trying to democratize uh access or availability of these concierges, right? Which is if you were going to a business where you were spending $100,000 a year, you would get the most personalized treatment. They would know exactly who you are, what your preferences were. They want to help you, you know, shop, for instance. They'll shut the whole store down for you.

</details>

**Speaker A**: 实际上，我不知道他们是否真的会为了某个客户那么做……

<details>
<summary>Original English</summary>

**Speaker A**: Actually, I don't know if they do that for,

</details>

**Speaker B**: 但你完全明白个中大致的意思，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: but you get the general, right?

</details>

**Speaker A**: 你以前肯定从来没有亲身体验过那种级别的待遇。

<details>
<summary>Original English</summary>

**Speaker A**: You've never you've never tried that before.

</details>

**Speaker B**: 我确实没亲身试过那些。然而，重点在于，如果你去一家你只消费 10 美元的企业，他们绝对没法为你提供这样无微不至的服务，因为在商业经济上这对他们来说根本就不划算，对吧？这并不是因为他们缺乏为自己的客户提供这种极佳服务的意愿。这纯粹是因为他们的单位经济效益（unit economics）根本无法支撑这种高昂的做法。

<details>
<summary>Original English</summary>

**Speaker B**: I've never tried those. Um, however, if you're at a business where you're spending $10, they can't do this for you because they can't make it economical, right? It is not a lack of desire to do this for their customers. It is just that the unit economics don't support that.

</details>

**Speaker B**: 因此，实际上，我们在这里所做的一切就是在向市场传达，好吧，如果你能够仅用 10 美分的超低成本就为他们提供那样顶级的体验，突然之间它在经济上就变得极为划算了，那么企业们自然会极其渴望去这么做。现在回到你刚才提到的，这是否意味着 CRM 将会随之消亡？我的明确答案是否定的，因为如果你在一家企业中，你知道，如果你今天运营着一家公司，你的礼宾服务人员是一个活生生的人类，他们仍然会将你的信息录入到 CRM 系统中，以便他们日后可以进行准确的追踪和跟进。所以，我认为当我们普遍拥有了这些人工智能体（AI agents）时，它们同样会需要一个稳固的地方来统一存放和管理这些关键信息。

<details>
<summary>Original English</summary>

**Speaker B**: And so, effectively, all we're doing here is saying, okay, if you could give them that experience for 10 cents, all of a sudden it is economical and they'd want to do that. Now to the point of does that mean CRM go away? I mean my answer is no because if you had u you know if you have a company today where the con your concierge is a human being they still write your info in a CRM so they can track it for later. So, and I think when we have these AI agents, they will need somewhere to put that information.

</details>

**Speaker B**: 所以，我不一定认为那些起辅助作用的底层软件组件会凭空消失，因为对于我们来说，当我们正在倾注心血构建这些礼宾服务时，我们的核心目标真正聚焦于我们该如何创造那种令人惊叹的绝佳用户体验？我们仍然必然需要一些基础设施，把那些产生的海量数据安全地放在某个地方，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Um, so I don't necessarily think those kind of auxiliary pieces of software go away because um for us as we're building these concierges, our goal really is how do we create that great experience? We will still need places to put that data somewhere, right?

</details>

**Speaker C**: 是的，毫无疑问。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah.

</details>

**Speaker C**: 我实际上认为 CRM 未来可能会发展得相当不错。它们将会有细微的不同，在某种意义上说，CRM 从某种途径来看就像是结构化的数据库，你知道，人们有时对它们感到极为沮丧的地方恰恰在于它们的图形交互界面真的很难使用等等。但在不久的未来，也许就只有那些人工智能体在后台高效地使用这些界面，而作为人类用户的你甚至不再需要去面对那些繁琐的图形化交互界面或者类似的东西了。因此，CRM 依然会非常有其存在的价值，因为它们牢牢掌握着企业真实数据的唯一来源（source of truth），而且你知道，在那之后，这些人工智能体，它们只是会越来越频繁地收到系统的请求，因为正是这些智能体在不知疲倦地使用它们。所以，这就是一个未来完全可能存在的世界，在这个世界里，人们对 CRM 架构的发展前景是相当看好的。

<details>
<summary>Original English</summary>

**Speaker C**: Um, I actually think CRM could do quite well. um they'll they'll be slightly different in the sense of like CRM are kind of databases in a way and you know the frustration people have with them sometimes is that the interfaces are really difficult to use etc but in the future maybe the agents are just using the interfaces and you don't you don't even have graphical interfaces or whatever and so the CRM are still very valuable because they they hold the source of truth and you know then the agents they're just kind of getting pinged a lot more because the agents are are using them so that is one possible world that's that's kind of bullish on CRM and

</details>

**Speaker C**: 对于我们个人来说，比如目前为止在我们自己公司 Decagon，对于从头构建一个 CRM 系统，我们是完全没有任何渴望的，因为我们认为在智能体层面（agentic layer）有太多令人兴奋、值得去深度开发的东西，那才是我们希望集中所有精力去深耕的领域。

<details>
<summary>Original English</summary>

**Speaker C**: for us personally like so far with Decagon there's like we have zero desire to build a CRM because we think there's so much to do in the agentic layer and that's where we want to focus

</details>

**Speaker A**: 是的，完全明白了。所以 SaaS（软件即服务）商业模式并没有死。

<details>
<summary>Original English</summary>

**Speaker A**: yeah okay so SAS is not dead

</details>

### 利用 AI 提升个人生产力与解决业务环境上下文的瓶颈

**Speaker A**: 太棒了。也许最后一件事是，在我们正式开始录音之前，我们刚刚还在闲聊，提到你们自己也在私下里做了一些小规模的 AI 实验，就在你们积极探索如何，你知道，让你们自己的日常生活和工作变得更具生产力和效率的时候，而且听起来你们似乎还基于此做了一些相当有趣的事情。

<details>
<summary>Original English</summary>

**Speaker A**: cool maybe um last thing is we were chatting right before we we started recording that you guys have done some little AI experimentation on your own as you just figure out how to you know make your own life more productive and effective and also it sounds like you've done something kind of interesting.

</details>

**Speaker B**: 是的，没错。你知道，我认为在过去这几年的飞速发展中，这些语言模型已经变得非常聪明了，并且你知道，我们俩在工作中经常会利用它来集思广益，激发全新的想法，对吧？因为它们在提出那些跳出框架的绝妙想法方面确实是表现得非常聪明的。然而，我深刻意识到的一个核心瓶颈是，至少对于我所负责的大部分高阶工作来说，真正的瓶颈在于业务环境上下文（business context），对吧？围绕着我们想要推进的每一个想法，都存在着大量的上下文背景信息，比如关于，好吧，我们在现实中所受到的各种资源限制条件，我们正在努力实现的长远目标，以及诸如此类的复杂事情。每一次都必须向那些 AI 智能体重新解释这些错综复杂的上下文，是一件非常痛苦且困难的事情，所以我实际上花费了一段相当长的时间，专门为自己构建了一套量身定制的智能体，以便能够妥善地捕获和维持所有的业务上下文。因此，它现在的运作方式就像是无时无刻不在我的肩膀上方敏锐地注视着我所做的一切，并且不断地在后台自动汇编关于我的业务背景资料，比如：“哦，这些是我们近期已经成功录用的人才，这些是我们团队接下来还需要去招聘的空缺岗位，这些是我们目前正在积极跟进和谈判的商业交易，这些是摆在桌面上的紧迫问题。这些是我们当下所面临的重大挑战。” 通过这种方式建立上下文环境，所以，到了后来，我就能直接轻松地去找它，对它说：“嘿，有一个这样新来的关键人物，我们……”

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Um, you know, I think the models have gotten very smart uh over the last several years and you know the two of us will often use it to brainstorm ideas, right? Because they are genuinely very smart at at coming up with great ideas. However, the bottleneck I realize at least for a lot of the work that I do is business context, right? there's a lot of context for every idea around okay the constraints that we have the goals that we're going for and things like that that is difficult to reexlain to the agents every time and so I actually spent a while building agents for myself to capture all the business context well so it just kind of looks over my shoulder all the time and is constantly compiling context on oh here are the people that we've hired here are the people that we need to hire here are the deals that we're working on here's here are the problems. Here are the current challenges that we have. So that later on I can just go to it and say, "Hey, there's this new person that we're

</details>

<!-- chunk 10/11 -->

### AI 与决策外包

**Speaker A**: “考虑招人。你觉得呢？”现在它能自动进行合理的推断，比如，我们有两个非常相似的候选人，你知道，这些候选人有这类缺点或者缺乏某些技能。因此，如果我们雇佣这个人，就又多了一个有着同样问题的人。所以我们需要互补的人才。因此这可能不是最合适的人选，或者你知道在这个交易中，我们正在重蹈覆辙，因为我们没有及早验证这些事情，所以这次我们应该稍微早点去验证。所以这一切真的都是关于如何很好地捕捉上下文，因为我的工作就是基于大量的上下文来做决定。因此，如果我能越来越多地把这部分工作外包给模型，也许我能更快地让自己“失业”。

<details>
<summary>Original English</summary>

**Speaker A**: "thinking of hiring. What do you think?" And now it's able to automatically reasonable, well, we had two candidates that were very similar and you know, these candidates had these kind of uh drawbacks or skills that they didn't have. And so if we hire this person, it's going to be another person that has those, you know, kind of exact same things. So we need someone complimentary. So this is probably not the best person to have or >> you know in this deal we're barreling down a very similar path because you know we didn't validate these things early enough so this time we should validate them uh uh slightly earlier. So it's really all about how do you capture context well because then you know my job is making decisions with lots of context. So if I can outsource that more and more to a model maybe I can put myself out of job quicker.

</details>

**Speaker B**: 听起来你像是在创造 Jesse。就是这样。

<details>
<summary>Original English</summary>

**Speaker B**: >> Sounds like you created Jesse. There we go.

</details>

**Speaker A**: 我确实认为作为独立创始人的一大挣扎，就是你没有可以交流想法的人。所以你得出结论的速度要慢得多。

<details>
<summary>Original English</summary>

**Speaker A**: >> I do think um like one of the big struggles of being a solo founder is you don't have anyone to bounce ideas off of. So you just arrive at conclusions a lot slower.

</details>

**Speaker B**: 你们过去都是独立创始人，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: >> You guys were both solo founders in the past, right?

</details>

### AI 作为头脑风暴伙伴

**Speaker A**: 是的。所以就像我们在一起工作，我认为之所以轻松得多，是因为我们可以，你知道的，更快地在事情上进行迭代。你差不多就是把想法说出来，是的，现在你可以和 Fable 或者类似的东西交谈。老实说，感觉相当不错。似乎非常有创意，因为过去它们就像是那种只会附和的人，对吧？它们只会同意你的观点。“哦，那是个好主意。”但现在它们会说：“不，那是个坏主意。别那样做。”

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. So like us working together, I think the reason it was so much easier is that we could, you know, iterate on things much faster. You kind of just talk something out >> and uh yeah, now you've talked to Fable or whatever. It's like it's pretty good, honestly. seem like very original >> because in the past it's just like they just kind of are kind of sick fence, right? Where they just agree with you. Oh, that's a good idea. But now they're like, "No, that's a bad idea. >> Don't do that."

</details>

**Speaker A**: 实际上有一阵子，Mark 曾经发布过他给 Claude 用的提示词，大致就是，你知道的，“反驳我，非常直接点”之类的话。所以，我实际上也用过一次。效果很好。关于这个有个有趣的故事，我非常喜欢它，因为它会非常激烈地同意我，也会非常激烈地反驳我。然后我把它给我妻子看，我说：“啊，这太棒了。你也应该用用。”她用上了，结果，你知道，过了一天她说：“哇，Claude 一整天对我都太刻薄了。我不得不把它关掉。”就像它一直对我说，“是的，它就是那么激烈地在反驳我。”

<details>
<summary>Original English</summary>

**Speaker A**: I actually uh for a while Mark at one point had uh uh posted the prompt that he used for Claude where it's like, you know, disagree with me, be very direct, things like that. So, um I actually used that for one. It was great. And the the funny story on this was I really enjoyed it because it would agree with me very aggressively. It would disagree with me very aggressively. And um I took it to my wife and I was like, "Ah, this is great. You should use it." She put it on and then, you know, a day later she was like, "Wow, Claude was being so mean to me all day. I had to turn it off." Like he just kept telling me, "Yeah, it was just disagreeing with me so aggressively."

</details>

### X (推特) 与 LinkedIn 的平台差异

**Speaker B**: 太不可思议了。嗯，既然我们在谈论创始人使用 AI 做事的话题，我就不得不提到 Brian Chesky 刚刚经历的整个 AI 垃圾内容“惨败”（也许这个词有点过了）。我想提一下，因为你们两位在过去几年里都大大提升了知名度。而且你知道，我算是提到了 Jess，你写的那些文章正好切中了大家想讨论的时代精神，并且提出了非常与众不同的观点。你知道，那正是我们所看到的完全切中要害的东西。你们恰好在正确的时间传达了正确的信息，切入了对话。正确时间的独特信息。你们写作时会用 AI 吗？另外，这是一个更偏宏观层面的问题，X（推特）以及 X 上的情绪对你们来说有多重要？

<details>
<summary>Original English</summary>

**Speaker B**: >> Amazing. Um well, since we're on this topic of f founders using AI to do things, um I have to bring up the whole uh AI slop um fiasco maybe is a strong word that Brian Chesy just went through. Um and I want to bring it up because um you both have grown your profile a lot over these last few years. And you know, you know, I sort of mentioned Jess, you had these pieces that were just hitting the zeitgeist of the discussion that everyone wanted to have and came in with a very differentiated take. Um, and uh, you know, that's the kind of stuff that we see exactly hit on. You know, you're hitting the conversation right at the, you know, right message, right time. Uh, unique message, right time. Um, do you use AI for writing? Um, and separately, um, this is a more of a meta question, but how important is X and like the sentiment on X to you?

</details>

**Speaker A**: 呃，是的，在我们早期的大部分时间里，主要使用的是 LinkedIn，理由是，嘿，我们的客户在 LinkedIn 上。你知道，我们不太可能让某人在推特上看到我们，然后就变成了客户。但我认为我们在 X 上学到的一点是，或者至少我在反思这一点，X 就像是人们谈论的时间线。而且那条时间线上的大部分内容并不是真正关于你的公司的。如果你在 X 上非常像是在自我推销，那根本就不会获得任何关注度。

<details>
<summary>Original English</summary>

**Speaker A**: >> Uh, so yeah, for most of our early days, it was mostly LinkedIn with the reasoning of like, hey, our customers are on LinkedIn. You know, we're not going to get someone seeing us on Twitter and then coming as a customer probably. But I think the the sort of learning we had with X is or at least I was kind of reflecting on it. X is kind of like like the timeline that people talk about. >> And most of that timeline is not really about your company. Like if you're if you're very like >> just like promoting yourself on X like it's going to get no traction whatsoever.

</details>

**Speaker C**: 完全同意。

<details>
<summary>Original English</summary>

**Speaker C**: >> Totally.

</details>

**Speaker A**: 但它有点像每个人都在阅读的单一时间线。所以它有点像在对每个人进行精神控制，让大家都去思考同一件事。

<details>
<summary>Original English</summary>

**Speaker A**: >> But it is sort of like a single timeline that everyone reads. So it kind of like it kind of like mind controls everyone to be thinking about the same thing.

</details>

**Speaker C**: 是的。这就是在其中拥有一定话语权的价值所在。这个人是在听谁说呢？有个叫 Jeremy Giffon 还是什么的人，上过我喜欢的 Patrick O'Shaughnessy 的播客，他发表了一些言论，大意是说，你知道，过去世界上重要的身份象征是每个人都想成为亿万富翁，因为他称之为“牧师阶层”之类的。所以亿万富翁就像是牧师阶层，但实际上，如今当人们成为亿万富翁后，他们想成为 X 的影响者，因为那些人才掌握着真正的权力，他们能影响整个世界的想法。所以，我想这也是在 X 上保持一些存在感的一个原因。而且现在当我在 X 上发帖时，我并不真的特别去发关于 Decagon 的内容，更多的是关于我们对正在发生的事情的看法。所以，我认为那是个不错的方式。但这确实非常不同。

<details>
<summary>Original English</summary>

**Speaker C**: >> Yes. And that's where it's valuable to have some say in it. And uh who was this guy listening to? There's like there's this guy like Jeremy GeFon or something who's on Patrick Ashanti's podcast who I like and he was like doing he like made some claim about how like you know it used to be that >> like the the the big status symbols in the world is like everyone wants to be a billionaire cuz like he calls it like the priest class or whatever. So it's like billionaires are the priest class but nowadays actually it's when people become billionaires now they want to become ex influencers because like those people hold the real power because they can like influence what the whole world's thinking about. >> Um so that's like one reason to have some presence on X I suppose >> and when we now when I post on X I don't really post about like Decon specifically it's more more about you know our thoughts on what is happening. So, I think that's that's like a good good way to do it. And but it is very different.

</details>

**Speaker B**: 都是你自己写的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: >> You write it all yourself, right?

</details>

**Speaker C**: 是的。我的意思是 AI 在帮助你头脑风暴写什么话题这方面挺有用的。我觉得那相当不错。但我认为那也算是一个经验教训，那就是 LinkedIn 和 X 的运作方式非常不同。你不能只是想出一些很酷的东西，然后在两边发一样的内容，因为很少有东西能在两边都表现得很好。是的。所以像 LinkedIn 非常适合发经典的内容。你可以发布公告，谈论你的产品，或者融资之类的。我猜你也可以在 X 上融资，但 X 更多的是关于将自己置身于每个人都在关注的那条单一时间线的顶端。

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah. Um I mean AI is good for um sort of helping you brainstorm like what topics to write about. I think that's that's pretty good. >> But I think that was that's kind of like a learning that like LinkedIn and X work very differently. You can't just like come up with something cool >> and >> like post the same thing on both >> because like very few things like do well on both. >> Yeah. So like LinkedIn's really good for you know classic stuff. You're making announcements and um talking about your product and you know fund raise or whatever. I guess you can do fundraising on X as well but X is a lot more about kind of like placing yourself on top of that single timeline that everyone's on.

</details>

**Speaker B**: 那么这是不是说得太简单了：把 X 用于招聘，尤其是 AI 研究人才等，或许还有生态系统的建设；然后把 LinkedIn 更多地用于企业客户？还是说你们确实看到企业首席信息官（CIO）也在关注 X？硬性归因显然很难。

<details>
<summary>Original English</summary>

**Speaker B**: >> And is that so is it too much of a simple you know simplification to say X for hiring especially you know AI research talent etc. um maybe ecosystem as well and then LinkedIn more for enterprise customers or are you actually seeing enterprise CIOS pay attention to X? Hard attribution is hard obviously.

</details>

**Speaker C**: 是的，这很难，因为你知道，我觉得你可能会说，“哦，我在 X 上发了个帖子，然后 All-In 播客上的人就在谈论它”，而且我确实看到 CIO 们也注意到了，所以这就像是间接地我确信我们吸引了一些 CIO 的目光。CIO 本人会整天刷 X 吗？可能不会，但如果你是那条主要时间线的一部分，那就总会有这些次级效应，然后主流媒体的记者就会联系你，如果他们写了关于你的报道，就像 Ashan 最近上了《纽约时报》，你知道，如果他们写了你，那肯定会吸引眼球，所以你就是……

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah, it's hard because you know I think you could say like oh well you know I I I made a post on X and then you know the people on all in podcast were talking about it and like CIOS definitely that I saw that so it's like a >> like indirectly I'm sure we got like some eyeballs from CIOS like is the CIO themselves like scrolling X all day maybe not >> but if you are part of that major timeline then you have there's always these like secondary effects and then and then like reporters will reach out to like from like mainstream media and then if they write about you then like Ashan was on the New York Times recently you know it's like if they write about you then those for sure get eyeballs so >> you were

</details>

**Speaker B**: 嗯。但那只是开源的东西。

<details>
<summary>Original English</summary>

**Speaker B**: >> Mhm. But it was just open source stuff.

</details>

**Speaker A**: 哦，Kimberly 只玩 X。所以，你没有放下一篇文章。我没看到。

<details>
<summary>Original English</summary>

**Speaker A**: >> Oh, Kimberly's only on X. So, >> you didn't put the next article. I didn't see it.

</details>

### AI 与就业叙事

**Speaker B**: 嗯，既然我们触及了 X 上的热门话题，我猜最后一个问题可能是……其实这是一个比较严肃的问题，但我认为随着 Anthropic 的视频，它似乎又重新回到了大众的视野中，或许它从未离开过，就是关于随着工作方面的进展越来越好，以及围绕这一点的相关信息传递。这显然是个敏感话题，但它很有趣，因为我真的认为客户支持可能是第一个你可以真正做完整个工作的端到端用例，或者抱歉，我应该说“完成”整个工作，“取代”是个错误的词，相比之下，编程一开始总是“结对编程”。你们怎么看……你知道我们之前开过玩笑，但你知道我们并不完全是在开玩笑，AI 实际上是在创造就业机会，我很好奇你们如何反转人们只会失去工作这种叙事？对吧，比如你们是否看到了员工在 AI 辅助下的技能提升，就是你知道，也许他们以前做这份工作，而现在他们在做别的事情。

<details>
<summary>Original English</summary>

**Speaker B**: >> Um, I guess maybe a last uh question would be just since we touched on like hot button X topics. um one and this is kind of a serious one actually but it sort of re-entered the narrative I think with um you know the anthropic video and it's just sort of maybe never left the narrative but it's on this concept as progress gets better around jobs um and the messaging around that um it's a sensitive topic obviously but it's interesting because I really think customer support was maybe the first endto-end use case where you could really take an entire job um or sorry do an entire job I should say take is the wrong word um versus coding was always you know pair programming to start with um how has that you know we we sort of joked before but I you know we weren't really joking that um AI is actually creating jobs I'm curious how do you turn that narrative on its head that folks are just losing their jobs right like do you see the upleveling of folks folks with AI where you know maybe they were doing this job and now they're doing something else.

</details>

**Speaker C**: 是的。我的意思是我们经常看到这种情况。因为如果你还记得早些时候我们谈论“我们到底在做什么？”的时候。嗯，我们发现在我们的很多客户中，对于像客户支持这样的东西，实际上就是需求大于供给，对吧？当公司意识到这一点时，他们会觉得，好吧……

<details>
<summary>Original English</summary>

**Speaker C**: >> Yeah. I mean we we we see this all the time. Uh because uh if you recall earlier on when we were talking about okay what are we truly doing? Um, we found that in a for a lot of our customers, there's actually just more demand for things like customer support than there's supply, >> right? >> Where companies realize that they're like, okay,

</details>

<!-- chunk 11/11 -->

### AI与工作：消除单调，释放潜力

**Jesse**: 如果我们进行客户支持的成本下降了 30%。他们中的大多数人并没有立刻说，好吧，现在我要做的是，你知道的，裁掉 60% 的团队。他们说的是，既然这个对我的客户来说显然很有价值的东西现在便宜得多了，那我就多做一些，这样我的客户就能留存更长时间，这样他们就不会有那么高的流失率，这样他们就能更快地被激活，诸如此类的事情。

<details>
<summary>Original English</summary>

**Jesse**: If our cost of doing customer support drops by 30%. Most of them are not just immediately saying, okay, now what I will do is, you know, let go of 60% of my team. They're saying okay now that this thing which is clearly valuable for my customers is much cheaper let me do more of it so that my customers retain for longer so that you know they don't turn off as much so that they activate sooner things like that

</details>

**Jesse**: 你知道，我们在早期有一个客户，嗯，大概是在两年半以前吧，他们说，你知道，我们的工单量，也就是我们每个月收到的客户支持咨询量，我想大概是一个月 50,000 左右，这是基于他们当时现有的服务渠道。一旦他们开始使用我们，他们说，哇，原来我们的客户有这么多问题。他们说，让我们让客户支持变得更容易获得，对吧？所以不再仅仅把它放在一个地方，比如埋在一个支持面板里。他们说，让我们在每个页面上都提供支持，让我们在人们更容易卡住的地方让它更显眼。让我们甚至为免费用户提供即时支持，而不仅仅是付费用户。对，所以因为这种……

<details>
<summary>Original English</summary>

**Jesse**: You know we had a customer in the early days um they and this was you know probably two and a half years ago at this point um where they said you know our ticket volume you know the amount of customer support inquiries that we get uh per month was I I think I think it was like 50,000 a month or something based on uh you know the existing surfaces that they had. Once they started using us they said wow turns out our customers have a lot of problems they said let us make support more easily accessible right so instead of it just being in one part like buried within a support panel. They're like let's put support on every page and let's make it more prominent in places where people are more likely to get stuck. Let's allow immediate support for even free users rather than only paying users. Right. So because of this kind of

</details>

**Host**: 对支持有更多潜在需求。是的。

<details>
<summary>Original English</summary>

**Host**: there's more kind of latent demand for support. Yeah.

</details>

**Jesse**: 呃，需求大于供给。所以自动化这些事情并不一定会导致人们只是把他们的整个团队都裁掉。

<details>
<summary>Original English</summary>

**Jesse**: Uh than there is supply. So automating things doesn't necessarily result in just kind of people laying off their entire teams.

</details>

**Host**: 这可能是我听说过的现实生活中杰文斯悖论 (Jevons paradox) 最好的例子了。所以这很令人兴奋。

<details>
<summary>Original English</summary>

**Host**: That may be the best example of Jevons paradox in real life that I've heard. So it's exciting.

</details>

**Jesse**: 是的。我认为这就像，嗯，AI 在某种程度上会消灭一些工作岗位，但不会消灭职业，因为像目前正在做的那些工作本来就不应该由人类来做。就像它们非常单调和低微。这就像是一个超级高频的用例，人们只是在接电话。我当时觉得，“好吧，让我点这里，点这里，然后，好吧，这就是答案，对吧？” 而这些应该由 AI 来完成。但实际上有几乎无限多的事情人们可以去做，让他们的客户更开心，你知道，更好地照顾他们。所以人们最终会去做这些事情，而越来越多单调重复的事情会被 AI 吞噬。所以，那……那就是我们认为会发生的事情。

<details>
<summary>Original English</summary>

**Jesse**: Yeah. I think it's like uh AI will uh kill jobs but not careers in a way because like those jobs that are being done currently should not be done by humans. Like they're very mundane and menial. It's like it's like a super high volume use case and people are just like kind of picking up the phone. I was like, "Okay, let me click here, click here, and like, okay, here's the answer, right?" And that should be done by AI. But there is actually like a near infinite amount of things that people could be doing to make their customers happier and, you know, take care of them more. And so people will end up doing those things and more and more of the mundane repeatable things will get eaten up by AI. So that that's that's what we think will happen.

</details>

**Host**: Jesse，我想在几个月前的一个播客上，也许是 Patrick O'Shaughnessy 的播客上，你曾提到，即使你的客户在使用 BPO（业务流程外包）来做客户支持，你也并没有真正看到 BPO 出现裁员。结果只是那些员工转而去做其他事情了。现在还是这样吗？

<details>
<summary>Original English</summary>

**Host**: Jesse, I think on a podcast, maybe Patrick O'Shaughnessy's podcast a couple months ago, you had mentioned that even your customers when they've been using BPOs for customer support instead, you haven't actually seen like layoffs at the BPO. It just turns out that those employees have gone and done other things instead. Is that still true?

</details>

**Jesse**: 哦，呃，我的意思是，这真的取决于具体情况。所以，肯定有这样的场景，人们大幅减少了对 BPO 的使用，或者不再需要 BPO 了。还有一些其他情况，他们完全没有处于削减成本的模式中，他们的目标是要么业务增长如此之快，以至于他们不想让运营规模随着业务增长而扩大，所以通过我们的产品他们可以保持某种扁平化什么的；要么就是，是的，实际上我们仍然需要人，但现在有所有这些他们可以去做的其他事情，而且可能更多是能创造收入的事情。嗯，你知道，这甚至对我们来说也是一个很大的领域，就像随着 AI 的成熟，你首先从这些削减成本的用例开始，因为那些很容易，但随后像创造收入的用例也应该能够通过这种对话式界面来完成，所以，是的，这真的取决于客户，但是，嗯，你知道，我们肯定有客户已经做出了巨大的改变。

<details>
<summary>Original English</summary>

**Jesse**: Oh, uh, I mean, it's it's it really depends on the situation. So, there are definitely scenarios where people use their BPOs a lot less or don't need the BPO anymore. There are other situations where they are not in cost cutting mode whatsoever and their goal is to either their business is growing so quickly that they don't want to scale their operations along with their growth and so with Decagon they can kind of like keep it flat or whatnot or it's yeah actually we still need people but now there's all these other things they could be doing and it could be more revenue generating things. um you know as that's like a big area for for us even is like as the AI matures you first start with these cost cutting use cases because those are easy but then like revenue generating use cases should also be able to be done through this conversational interface so yeah there's it really depends on the customer but um you know we definitely have customers that have made massive changes

</details>

**Host**: 实际上我想在这个令人振奋的基调上结束今天的访谈，嗯，只是重复一下 Jesse 说的：它可能会消灭工作，但不会消灭职业。我很喜欢这句话。嗯，非常感谢你们的加入，伙计们。很高兴能邀请到你们。

<details>
<summary>Original English</summary>

**Host**: actually I'd like to end it on that uplifting note um and just to repeat what Jesse said it may kill jobs but not careers I love that um thank you so for joining us, guys. A pleasure to have you.

</details>

**Guests**: 感谢邀请。

<details>
<summary>Original English</summary>

**Guests**: Thanks for having us.

</details>