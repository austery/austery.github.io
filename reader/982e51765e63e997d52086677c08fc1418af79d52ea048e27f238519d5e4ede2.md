---
author: AI Engineer
date: '2026-11-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RdQCY_-SXbA
speaker: AI Engineer
tags:
  - formal-verification
  - retrieval-augmented-generation
  - financial-ai
  - deterministic-systems
  - data-security
title: AI 查不到就编不出数字：Kepler 创始人谈金融级确定性与验证架构
summary: Kepler 联合创始人兼 CEO 探讨了华尔街仍不信任 AI 的核心根源在于结构性幻觉与缺乏确定性。他拆解了数值错误的三大来源（检索错误、抽取错误、心算错误），提出通过代码确定性生成指针、确定性计算工具与多层安全检索，使模型仅能通过解引用指针输出事实与数字，从架构底层实现免于数值幻觉的验证系统。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Venu Ganesh
  - Jack
companies_orgs:
  - Kepler
  - Citadel
  - Candlestick Capital
  - Turbopuffer
  - Anthropic
  - OpenAI
  - Jane Street
products_models: []
media_books: []
status: evergreen
---
### 华尔街的不信任与形式化验证现状

大家好，我叫 Venu Ganesh。很高兴今天能来到这里。我是 Kepler 的 CEO 兼联合创始人。

这场演讲会挺有意思，因为它源于三个月前发生的事情。大约三个月前——可能会有一点重叠——我在 AIE World Fair 上发表了一场演讲，主要是围绕验证展开的，以及为什么大多数机构在 AI 信任生态中都需要某种形式的验证。

昨天大多数人都看到我和 Jack 一起登台，探讨了为什么曾执掌 Citadel 最大账本、后来创办了 Candlestick Capital 的 Jack，至今仍然不信任 AI。

在过去这三个月里，大约有 2.7 亿美元的风投资金涌入了形式化验证层。甚至有一家风投拿着 Kepler 自己的商业计划书（pitch deck）给了我们的竞争对手，然后做出了一款连标语都跟我们一模一样的产品。我并不耿耿于怀，可能就一点点吧；但好笑的是，他们抄错了部分。所以，我今天想为在座的各位实践者讲清楚：你不能仅仅在流程最后随便挂上一个验证层了事。

几个月前我做那场分享时，Anthropic 刚好发布了一篇关于 Kepler 工作原理的文章，阐述了为什么这种做法非常强大且独特。

<details>
<summary>Original English</summary>
Hi everyone. My name is Venu Ganesh. Um, excited to be here today. Uh, I'm the CEO and co-founder of Kepler. Um, this is going to be kind of an interesting talk because it comes from what happened 3 months ago. So, 3 months ago, uh, I think there's a little bit of an overlap, but I gave a talk at AIE World Fair, uh, uh, really around verification, um, and why that most institutions need verification in some form of the trust ecosystem of AI. Well, yesterday most of you saw Jack and I were on stage talking about why Jack, who ran Citadel's biggest book, and started Candlestick Capital, still doesn't trust AI.

Since that 3-month period, there's been about a 270 million dollars of VC money that got poured into formal verification layers. A VC actually took Kepler's own pitch deck and gave it to a competitor, and produced something that has our same tagline. I'm not bitter, just a little, but the funny thing is they copied the wrong part. And so, what I want to do is actually give you, the practitioners today, you can't just tack verification on at the end. And so, uh, when I gave that chat or that talk a few, um, months ago, uh, Anthropic had just published an article on how Kepler does what it does, and why it's really powerful and and really unique.
</details>

所以我想要深入探讨我们底层实现的技术细节。归根结底，这一切都源于一个非常简单的洞见：华尔街仍然不信任 AI。

大多数人认为原因是这样的：AI 会进行估算，它会出现幻觉，前沿模型会胡编乱造。从根本上说确实如此，这也是其中的一个组成部分。但真正核心的底层问题在于，我们迫切想要使用的这项技术存在结构性问题。

也就是说，如果你真去和那些构建 RAG 平台的人交流，他们大多数人会说：“模型最终会变好，或者改进到能够消除幻觉的程度。”

这种说法毫无意义。

你知道“幻觉”的另一个叫法是什么吗？阿尔法（Alpha，超额收益）。

阿尔法是机构赚钱的方式。你和你的分析师所拥有的创造力，正是让你的机构脱颖而出的机制。否则，地球上应该只有一家公司才对。

所以，当你提出关于数据从何而来这类简单问题时，一方面是模型本身会胡编乱造，另一方面则是贵公司的内部数据从未真正反映在这种系统架构中。

<details>
<summary>Original English</summary>
So, what I want to do is get into the technical side of how we do the thing that we do, and ultimately this is driven by one very simple insight, Wall Street still doesn't trust AI.

Most people think it's because of this. Uh, AI will estimate things. It will hallucinate things. A frontier model will make stuff up. And ultimately it is, and that's a component of it. But the actual core underlying problem is we have a structural problem in this technology that we're all so desperate to use. Meaning, if you actually chat with people that are building rag platforms, most of what they'll say is, "Well, the models will eventually get good or get better to the point they will eliminate hallucination."

That is a nonsensical term.

You know another word for hallucination? Alpha.

Alpha is how a firm makes money. The creativity that you have and that your analysts have is a mechanism through which you can be a unique firm. Otherwise, there should be only one company on Earth.

So, when you ask these types of simple questions around where data comes from, there is a piece of this that the model will just make things up, and there's a piece of this that your firm's internal data is never actually reflected in this setup.
</details>

### 金融级工作成果的信任与错误归因

那么我们现在看到了什么？我们看到每个手握支票簿的人都在买下他们能买到的一切。形形色色的 RAG 平台，有些机构试图自研，有些机构在做智能体（agent）试点。我今天早上刚开了一个客户会议，有人说他们其实是一家“AI-first”的公司，意思是他们用一个 Copilot 智能体在跑所有的东西。

那么，为什么我们没有看到基本面投资发生彻底转变，实质上——为什么我们没有全变成 Jane Street？为什么这种情况还没有发生？

挑战实际上来自这样一个理念：为了让你能够产出自己信服的工作成果，你必须能够信任它；这意味着一旦出错，你必须能追究到责任人。

所以我们总能看到类似这样的数据：80% 的财务高管信任数字，但其中 31% 的人发现了错误。

那么我们真正需要的是什么？

作为构建者本身，我们需要这样一种局面：我们为 AI 应用收到的评估，不仅仅停留在“把东西 RAG 化”上。

这些话其实是我们从特定的——我不想说是竞争对手，而是其他人那里摘录的反馈：有些产品 Demo 效果极好，表现得就像一个非常聪明的实习生；或者只要你接入正确的结构化信息，答案就是对的，但最后那 10% 依然会出错。

<details>
<summary>Original English</summary>
So, what are we seeing right now? We're seeing everyone with a checkbook buy everything they can. Every rag platform, some firms are trying to build, some firm some firms are running agent pilots. I had a a customer meeting this morning where someone said they were actually an AI-first firm, which means they have one co-pilot agent running all the stuff.

So, why are we not seeing the complete switch of fundamental investing becoming effectively, why are we not all Jane Street? Why Why is that not happened yet?

And so, the challenge really comes from this idea of in order for you to produce work product that you believe in, you have to trust it, meaning you have to blame somebody who gets it wrong.

So, we see numbers like this all the time, where 80% of finance execs trust numbers, but then 31% find those errors.

So, what do we actually need?

We need a situation where the reviews that we're getting for AI apps, as builders ourselves, do more than just ragify things.

And And these are quotes we've actually pulled from specific uh I don't I don't want to say our competitors, but other people, where things demo super well and they behave like a really smart intern. Or things are right if you just hook up the right structured information, but that last 10% still gets things wrong.
</details>

### 数值错误的三大根源与确定性工具

所以我想探讨的是——我们很幸运，拥有像 Turbopuffer 这样的优秀合作伙伴，我昨天也发表过类似的分享——我们究竟是如何进行验证的？我们在架构上如何构建一个在数值上不会产生幻觉的系统？

我们来探讨一下。

错误的数字或错误的事实来自三个源头：

第一，你检索到了错误的文档。比如我抓取了一份文档，是不知道从别处哪儿弄来的随机构件。如何解决这个问题？检索正确的文档。但这本身就很复杂。正确的文档到底是我自己机构内部对这只股票估值的分析，还是某个我比谁都信任的分析师的报告？这是第一点。

第二种失败模式：我们拿到了正确的源文件，却从中提取了错误的数字。假设我们要查 Palantir 在 2023 年的营收。如果我看的是 2025 年的 10-K 报告，上面写着 Palantir 2023 年的营收是多少，我最好确保那个数字对应的是 2023 年，而不是 2025 年。因此，这里的解决办法通常是我们设置一个过滤器来检查每一个引用。但这里依然存在问题，因为这种过滤只是事后生效的。而形式化验证在这里其实起不到作用，因为内容早就已经被生成出来了。

第三是心算（mental math）。模型不会做数学运算，它们只是在预测下一个 token。对于那些会说我们拥有确定性模型的人，很好，我们确实有。但我们同样有一个只需要一个 CPU 周期就能做好两个数相加的硬件，那我为什么不用那一个 CPU 周期呢？

因此，第三种失败的对策是：让我们使用现有的确定性工具来实际计算数值和实体，而不是依赖某种外部工具。

<details>
<summary>Original English</summary>
So, what I want to do is we're lucky, we have great partners and folks like Turbo puffer and I gave a similar chat yesterday about this, but how do we actually do the verification? How do we architecturally build a system that does not hallucinate numerically?

So, let's talk about it.

Now, wrong numbers or wrong facts come from three sources.

Either one, you retrieved the wrong document. So, I pulled a document, some random thing from somewhere else. How do you fix this? Well, by retrieving the right document. But, that in itself is complicated. Is the right document my own firm's internal analysis of what this stock is going to be worth? Is it, let's say, uh some analyst who I really trust more than anyone else? That's piece one.

Now, failure two. We get the right source and we pull the wrong number out of that source. Let's say we're trying to figure out what the revenue for, I don't know, Palantir was back in 2023. Well, if I look at the 2025 10K that says Palantir's 2023 revenue was this, I better make sure that that number corresponds to 2023 and not 2025. So, the fix here is really we have a filter that actually checks each citation. But, this is still a problem because that filter only applies after the fact. And formal verification doesn't actually help here because the thing has already been produced.

Three is the mental math. Models don't do math. They predict the next token. Now, for those of you who are going to say we have deterministic models, great, we do. We also have one CPU cycle that's good at adding two numbers together. Why don't I use that CPU cycle?

So, third failure is let's use deterministic tools that we already have to actually compute numbers and entities rather than relying on some external tool.
</details>

### Kepler 的架构：代码预处理与指针解引用

所以，这就是我们的做法。这就是 Kepler 背后的秘诀——至少对于第一部分来说，此外还有一大堆其他东西。我们在架构上有着根本性的不同。

所有的数字都是由代码写入的。代码在预处理过程中所做的是：为唯一标识符分配指针。

也就是事实，比如 10-K 报告中的某个数字。

这一步是在庞大的预处理与上下文关联步骤中运行的，从而实现从非结构化数据流转到结构化数据存储。

随后，模型实际上扮演了一个聪明分析师的角色。它找出解决问题的方法，但本身并不亲自去计算解题。也就是说，它负责规划。

它会说：“我要去这里检索这个来源，检索这个实体，然后执行这个操作。”

而检索是由代码和数学运算完成的。

在搜索阶段直接从 10-K 里抽取数字，其 token 成本极其高昂。Anthropic 和 OpenAI 应该感谢你们为了疯狂堆 token（token maxing）支付了那么多费用，但你们的大多数公司并不喜欢这样，至少现在不再喜欢了——尽管我知道曾经有一段时间，有人靠堆 token 拿到了奖金。

<details>
<summary>Original English</summary>
So, here's what we do. This is the magic behind Kepler, at least for piece one, there's a whole bunch of other stuff. We are architected fundamentally differently.

Code writes every number and what code does in pre-processing is we assign pointers to unique identifiers. Meaning facts. Meaning something like a number in a 10K. This operates in a giant pre-processing and contextualization step. Such that all of this exists, going from unstructured data to a structured data store.

Then, the model is effectively a smart analyst. It figures out how to go about solving the problem, but not actually being the thing to solve the problem itself. So, it plans. It says, "I'm going to go here and retrieve this source and retrieve this entity and do this thing."

Code and math do the retrieval. By actually pulling a number out of a 10K at like a search time, that's a hugely expensive token cost. And Anthropic and OpenAI should thank you for paying all those tokens in token maxing, but most of your firms don't like that, at least anymore. I know there were people getting bonuses from token maxing for a while. Um
</details>

接下来的核心部分是：一旦模型读取了这两个指针，它在结构上是无法自行生成数字的。

也就是说，除非模型拥有解引用（dereferencing）该指针的机制，否则该数字或该事实在结构上就无法出现在 Kepler 的输出中。

当然，我们确实会运行一个后处理步骤，也就是验证步骤。好笑的是，上一家公司仅仅抄袭了验证这一部分，但前面的所有结构性机制他们都没能做出来。

因此，你作为用户实际看到的内容是：比如营收从某一金额到另一金额，并且你可以在物理上点击这些交互标签（chips），精确查看我们是如何获取到该信息的。

在我过去的工作经历中，我有过一段机会——我曾担任 Citadel 的业务工程负责人。因此我曾跨部门工作，以摸索出我们究竟需要构建什么样的软件来帮助我们产生阿尔法。

你知道 Citadel 令人惊叹的地方在哪里吗？投资组合经理（PM）都极具天赋、极其聪明，但只有当他们与确定性的工具和技术结合在一起时，才能发挥作用。

这正是基本面投资背后的神奇洞见。

基本面投资者非常擅长理解数据，但前提是数据必须是正确的。

所以，当你构建像 Kepler 这样的系统时，你真正要做的是查找正确的信息，然后巧妙地处理你尚未掌握的信息。

<details>
<summary>Original English</summary>
Now, the next piece of this is really once the model's actually read both these pointers, it can't structurally generate numbers. Meaning unless the model actually has a mechanism of dereferencing that pointer, that number or that fact cannot be generated in Kepler's output.

Now, we do run a post-processing step, which is the verification step. And this is the piece that was kind of funny where the last company just copied the verification piece, but all the structural stuff beforehand didn't make it.

So, what you as a consumer actually see is you see something like the revenue is this amount to this amount, and you physically can click on these chips and see exactly how we got the information.

Now, in my past life, I had an opportunity. I I was head of business engineering at Citadel. So, I worked across um the firm to figure out effectively what do we need to produce software that helps us generate alpha. You know the crazy thing with Citadel? PMs are so talented and so smart, but they work when they're paired with deterministic tools and technology. And that's kind of the magical insight behind fundamental investing. A fundamental investor so good at understanding data, but that data has to be right.

And so, when you build a system like Kepler, what you effectively have to do is look up the right information and then be clever about the information you don't have.
</details>

### 宽泛检索、剪枝与确定性寻址

让我打个比方。大多数买方研究员或买方投资者会尝试使用工具，或者自己搭建现金流折现（DCF）模型，然后去寻找并搜索他们所缺失的信息。他们会安排 GLG 或 Guidepoint 的专家访谈电话，寻找行业专家，与管理层沟通。同样的系统逻辑在这里也完全适用。

所以我们的做法是：选择这条路径，并将我们能够确定性存储的信息确定性地存储下来。

当遇到无法进行确定性存储的信息时，我们会运行类似的预处理步骤来抓取信息，并将这些信息存储在一个混合存储机制中——该机制由 Turbopuffer（顺便说一句，这个工具棒极了）和一系列其他机制组合而成。最终，我们结合使用重排序（re-ranking）以及真正传统的方式——比如通过点调用 `.get` 方法进行指针解引用——将内容提取到我们的系统中。

为什么这一点至关重要？

因为查表寻址（lookup）不会出错，而搜索可能会出错。如果你用相同的查询语句运行相同的 10 次搜索，模型的概率本质意味着其天然带有熵。这其实是一个契机，而这正是我们在此所做出的改变。

我们具体的实现方式是对其进行拆解，这在整个 SEC 文件的处理中同样适用。

我们会频繁地丢弃候选文档。

这意味着我们不仅必须持续关注哪份来源是对应哪项信息的正确来源，还必须从全局视角判断我们应该停止查阅哪些文档。

因此，我们运行 ANN（近似最近邻）加上 BM25 来取回一组候选文档，通常多达 200 份；接着我们进行倒数排名融合（RRF），实质上取回 60 份文档，这可能是理解此过程最好的方式。

然后我们使用交叉编码器（cross-encoders）。我们尝试将查询语句与实际切块后的文档拼合在一起，以此获得最终结果。

这样做的好处在于我们可以进行非常宽泛的检索。你知道大语言模型不擅长做什么吗？不擅长做大范围宽泛检索。它们倾向于制定一个计划，然后寻找最快或最容易的广度优先搜索机制——实际上往往是深度优先搜索机制，即抓取到第一篇文档就继续往下走。因此，我们允许系统先展开非常广泛的检索，然后再从那里进行收窄。

大语言模型不喜欢做宽泛检索的原因是成本太高；相比于拿到第一个命中结果、获得奖励函数反馈就直接往下推进而言，横跨一大堆不同来源进行审视的效率要差得多。

<details>
<summary>Original English</summary>
So, let me give you the parallel. Most folks and most buy-side researchers or buy-side investors try to use tooling or build DCFs on their own and then they find and search for information they don't have. They schedule GLG or Guidepoint calls. They find experts. They speak to management. The same system actually applies here.

So, what we do is we pick the path and we store the information deterministically that we can actually store deterministically. When we have information we can't store deterministically, we run similar preprocessing steps to grab information, store that information in a hybrid storage mechanism, which is a combination of Turbo Buffer, which is awesome by the way, and a bunch of other um mechanisms. And then we ultimately use a combination of re-ranking with literally old-school like pointer dereferencing like dot get methods to pull things into our system.

Now, why this matters is a lookup cannot get it wrong. Search can. If you're running the same 10 searches with the same query, the probabilistic nature of models means there's inherent entropy. That's actually an opportunity. And so, that's what we've changed here.

Now, how we do this is we break this down and this occurs across of the SEC world as well. Um we are frequently throwing candidate documents away. Meaning we consistently have to look at not only what source is the right source for what information, but also which documents should we stop looking at kind of globally. So, uh we run ANN plus BM25 to get back a set of documents. It's usually up to 200. Uh we do reciprocal uh ranking We effectively get 60 documents back. It's probably the best way to think about this. Um then we do cross-encoders. We try to figure out exactly the query and the actual document chunked together and get those results that way.

What that allows us to do is we can search really wide. You know what LLMs aren't good at doing? Searching really wide. What they try to do is create a plan and find either the fastest or easiest breadth-first search mechanism actually made depth-first search mechanism of actually like getting the first document and moving forward. So we allow this to search really wide and then narrow from there. The reason LLMs don't like searching wide is because it's expensive. It's because looking across a bunch of different sources is significantly worse than getting the reward function back with your first hit and going from there.
</details>

### 安全优先架构与租户边界

好，接下来我想多谈一点安全性，因为这极其重要。

Kepler 在构建之初就秉持着“安全优先”的思维与理念。

谈到客户文档——这尤其针对在座的开发者们——有一件事目前根本没人在讨论。没有人在讨论到底使用了哪种 OAuth 令牌，以及检索文档时采用了何种用户级权限隔离机制，这其实非常可怕。

那么我们来聊聊在人们试图自建的这些系统中，问题是如何发生的，以及你该如何修复它：

1. **忘记过滤租户**：突然之间，Citadel 可以检索 Millennium 的所有文档了，那你可就有大麻烦了。
2. **调用方冒充其他机构**：也就是说，我可以声称自己在假冒另一个实体，并以此方式查询文档。
3. **搜索返回过期信息**：我们在全球范围内都会遇到这个问题，甚至在 Google 搜索结果中也是如此。
4. **直接读取绕过了搜索规则**：意味着你没有真正查询完整的信息语料库，或者缺乏白名单机制，你只能拿回单次搜索到的那份孤立文档。
5. **命中未填充的索引**。

解决所有这些问题的方法——此处列出了具体细则——是在底层内置安全约束的前提下对搜索进行范围限定（scoping）。

这是我认为很多人在尝试自建系统时忽略的另一个关键部分。

不可避免地，人们终将开始关注查询这些信息时的安全性。对华尔街的人来说，阿尔法是最难以捉摸的东西。因此，确保你拥有一套良好的机制来切实约束每次查询返回的文档集合，是至关重要的。

<details>
<summary>Original English</summary>
Okay, so um I want to talk a little bit about security here cuz it's super important. Kepler was built with a security-first mindset and security-first mentality. Now client documents, and this is specifically targeted towards the builders here, this is a thing that no one's chatting about. No one is actually talking about the security of what OAuth token is used and what user-scoped mechanism of retrieving documents, which is actually pretty scary.

So let's talk about how things go wrong in these systems that people are trying to build and how you can fix it.

First and foremost, you forget to filter the tenant. All of a sudden Citadel can search through all the Millennium's documents, you will be in a lot of trouble.

Second, a caller claims to be another firm. Meaning I can claim that I'm impersonating this other entity and querying documents that way.

Third, search returns information that's out of date. We've had this problem kind of globally and even Google search results.

Fourth, direct read skips the search rules. Meaning you're not actually querying the full corpus of information or like there's not an allow list, you only get back the single document that you did the search. Five, you hit an index that isn't populated.

The way to actually solve all these problems, and there's individual things listed here, is actually scoping searches with security built in. That's kind of another critical piece that I think a lot of people miss when they're trying to build these systems themselves. Inevitably, people will start caring about the security associated with querying this information. Alpha is the most elusive thing out there, especially for folks on Wall Street. So, making sure you have a good mechanism of actually constraining the set of documents that come back with each query is really important.
</details>

### 验证闭环与通用事实溯源

好了，现在我们来谈谈验证，也就是这里的最后一个环节。

这大概是我们最知名的部分，但前面提到的那些工作我们也同样在做。

我们的实现方式是：预先处理信息，并将其确定性地存储下来。

我们拥有像代码这样的系统来实际写入各个单独的指针。

之后，模型只有在数据库中确实存在这些指针时，才能读取它们并取回信息。如果我从哈希表（hash map）中提取一个不存在的键，我什么都拿不到。

正是这种结合，使我们能够切实确保检索到的信息确实来自其宣称的来源。

虽然这里展示的是我们 Source ID 的隐匿版本，但它们本质上是哈希值。这些都是非常简单的事情，你完全可以在自己的系统和架构中实现，以确保提取出的事实确实是真实存在的。

太棒了。

关于我们如何做验证就先讲这么多。现在我想聊聊这在全球范围内能带来什么样的赋能。

这使我们能够对来源于经过真实扎根的数据语料库的事实进行验证。

而你作为一名构建者、初创公司创始人，或者正在苦苦思索“我该如何让我的输出值得信赖”的人，实际上只需要做好几件事：你必须向人们证明，当你构建这些理论上用于寻找阿尔法（或任何目标）的智能体时，你所使用的信息对于你所服务的受众而言，是切实相关、具体且最重要的是准确的。

这样一来，我们最终达成了一种约定：引用要么通过验证，要么在搜索阶段得到修正，要么直接被明确拒答。仔细想想，这非常不可思议。

如果模型无法解析（deresolve）该指针，它就无法输出那个数字。

这是一件非常了不起的事情。这意味着整个体系——不仅仅是数字，我们来谈谈事实。比如我们在各地都能看到的法庭判例被 AI 凭空捏造的案件。那我们为什么不能构建一个系统，将判例确定性地存储起来，让我们在这份列表中检索，从而避免一个原本根本不存在的法例突然冒出来？

因此，这项技术和这种机制在全局上具有相当广泛的适用性。

<details>
<summary>Original English</summary>
Okay. Now, let's talk about verification, which is the last piece here. This is probably what we're known most for, but we do the other stuff I mentioned as well. Um how we do this is by pre-processing information and storing it deterministically. We have systems like code that actually write individual pointers. The model can only then read those pointers and grab information back if they exist in the database. If I grab something out of a hash map that doesn't exist, I don't get anything back. And so, this combination is what allows us to actually make sure the information that we retrieved actually came from the source that it came from.

Now, this is a kind of hidden version of what our source IDs look like, but these are hashes, and these are very simple things that you can do in your own system and your own setup to ensure that you're pulling back facts that in fact do exist.

Cool.

So, that's a little bit about how we do verification. Now, I want to chat a little bit about what this enables kind of globally. This enables us to verify facts that come out of our grounded corpus of data. Now, you as a builder, or you as a startup creator, or you as someone who's trying to figure out how do I trust my outputs, really just need you to do a couple of things. You need to show people that as you're creating these agents that are theoretically looking for alpha, or whatever they'd be looking for, you're using information that is actually relevant and concrete, and most importantly accurate, to the set of people that you're trying to service.

So, we end up with a contract where citations are either verified, corrected at search time, or flat out refused. This is crazy if you think about it. If a model cannot deresolve that pointer, it cannot print that number out.

So, that's kind of an insane thing. It means that the whole and not just a number, let's talk about facts. Like we see these court cases all over of precedents being hallucinated. Well, why can't we create a system that just has the precedent stored deterministically and allows us to search through that list and not have a random court case that never existed all of a sudden start existing?

So, this tech and this this mechanism and this technology actually becomes fairly globally applicable.
</details>

### 从搜索转向基础设施架构

我今天站在台上向大家公开我们的实现方式，是因为我极度担心华尔街永远不会信任这项技术。

因为有太多其他公司，或者太多在内部自建的团队，已经在这些机构内部埋下了恐惧。目前的情况已经演变成：绝大多数金融领域的 AI 工具仅仅被用来排版 PowerPoint 幻灯片。尽管很多人夸夸其谈，但至今没有人真正从头到尾完整构建出一个 DCF 模型。如果真有人做出来了，华尔街上的每家公司早就会在一夜之间全部采纳。

这就是我的担忧所在。我的担忧源于一个非常简单的事实：要让我们真正从这项技术中获取价值，我们必须能够构建出人们切实能够信任且能够验证的技术。

这不仅在金融领域适用，在很多不同的行业都是如此。因此，请大家在这场演讲中各取所需，推动人们真正用上这项技术，否则我们所有人都将面临失业。

现在我想带大家看看当我们看到这一结果时发生了什么。当我们走完整个流程时——这实际上是我们真实生产环境中的一些数据。

“拒答”指的是模型无法产出数字的情况。也就是说模型会说：“我无法解引用这个指针，因此我无法给出这个数字。”

我们看到拒答率出现了大幅下降。至于它为什么没有降到零，是因为模型本质上依然是概率性的。

这意味着它在推理阶段事后依然可能会虚构数字。因此，在这一步之后，我们还设立了另一个后处理步骤。

但我想通过这张幻灯片说明的是：仅仅通过建立一个让模型必须解引用自身指针的系统，你就能够打造出一个非常强大、高度可验证的 AI 平台。

<details>
<summary>Original English</summary>
And the reason I'm on stage telling you how we do what we do is because I'm terrified that Wall Street never trusts this technology because of the fear that so many other companies or so many build-it-at-home folks have been uh instituting in these organizations. It's It's gotten to the point where the vast majority of finance AI tools right now are being used to format PowerPoint presentations. We still haven't actually built a DCF cradle to grave despite what most people are saying. And if we had, every single company on Wall Street would have adopted that overnight.

So, this is my fear. My fear comes from a very simple fact. For us to actually get value out of this technology, we need to be able to build technology that people actually can trust and can verify. That isn't just true in finance, it's true in a bunch of different industries. So, please take what you need to from this presentation and get people using this technology, otherwise we're all going to be out of a job.

Now, I want to try through what happened when we saw this. So, when we went through this whole process, um this is actually some of our our real production data here. Um refusals are when the model does not is not able to produce a number. Meaning, the model will say, "I couldn't dereference this pointer, therefore I could not produce this number." We saw that drop super drastically. Now, the reason that it didn't drop to zero is because models are still probabilistic. Meaning, it can still make up numbers after the fact during inference. So, there was another pre- a post-processing step after this that we we have as well. But my point with this slide is just by creating a system where the models have to dereference their own pointers, you can actually create a very powerful, very verifiable AI platform.
</details>

这也正是我对各位的恳求。在你们进行构建和确定范围的过程中，面对所使用的任何工具，都要追问他们：你们能真正验证这些数字吗？问问他们是否能看到来源在哪里——不是某种事后打上去的批注，而是能够直接点击那个数字（无论是计算出来的、提取出来的，还是两者的结合），从而确保你能够信任这个洞见。

而所有这一切，最终都将成为破局的关键。所以，作为供应商或构建者，请多问问这些问题：

- 模型是否真正写入了指针？
- 它是否切实建立了一套验证输出的机制？
- 每条引用的来源是否都经过了校验？
- 算术运算的来源是否经过了核对？
- 你是否有机制去拦截不该发送给客户或消费者的文件？
- 最重要的是：凭空捏造出来的数字会面临怎样的处理？凭空捏造的事实会如何应对？以及我到底该如何处理这类幻觉？

所以，整个平台实际上是要把一个非常简单的道理讲得非常明白：我们可以拥有世界上最聪明的模型，我们可以用上令人惊叹的酷炫技术，但我们仍然面临着从一开始就存在的相同数据库问题——如果我去检索一行数据，而那个列对应的值根本不存在，我就拿不到返回结果。

我们现在已经走出了 AI 的“搜索阶段”。我们需要构建基础设施。我们需要去构建脚手架（scaffolding）、测试挽具（harnesses）与底层基质（substrates），或者无论当下风投圈流行什么酷炫的词汇，只要它们能切实让我们用好这项技术。

这就是我的挑战，也是我对各位的呼吁。

希望大家能走出去，构建出引人入胜的成果；但我更希望你们构建出令人信服且值得信赖的成果。

非常感谢大家。

>> [掌声]

>> 嘿。

<details>
<summary>Original English</summary>
And that to me is my ask to all of you. As you go through the building process, as you go through the scoping process, any tool that you use, ask them if you can actually verify the numbers. Ask them if you can see where the sources are, not in terms of some after-the-fact annotation, but click on the number, whether it's a calculation, whether it's an extraction, or some combination of the two, to make sure you trust the insight.

And all of this ultimately is going to be the unlock. So, you as a vendor or you as a builder, ask these questions.

Does the model actually write pointers? Does it actually create a mechanism for verifying the output? Is every citation source checked? Is arithmetic source checked? Do you have a mechanism for stopping files that reach clients or customers that it shouldn't reach? And most importantly, what happens to a number that came from nowhere? What happens when the when a fact comes from nowhere? And how do I actually handle these kinds of of hallucinations?

So, this whole platform is actually to make a very simple statement very obvious, which is we can have the smartest models in the world. We can hit some crazy cool piece of technology, but we still have the same database problems that we've had from the beginning, which are I cannot if I search through a a row and that column does not value doesn't exist, I won't get a retrieval back.

We're now out of the search phase of AI. We need to be building infrastructure. We need to be building scaffolding and harnesses and substrates or whatever the cool VC term is these days that actually enable us to make use of this technology. So, this is my challenge and my ask to all of you. Um I hope you go out there and build something compelling, but I hope you go build something compelling that you can trust.

Thank you.

>> [applause]

>> Hey.
</details>