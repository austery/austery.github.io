---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jebp4V0vh30
speaker: AI Engineer
tags:
  - hyper-personalization
  - retrieval-augmented-generation
  - web-development
  - edge-computing
title: 基于大语言模型与边缘交付的敏捷站点超个性化构建
summary: 演讲者介绍了利用 Adobe Experience Manager 边缘交付与大语言模型构建超个性化敏捷站点的实践，通过将整个网站作为语料库构建 RAG，实现实时模块级定制与快速页面生成，并探讨了评估与智能体生成工具。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Adobe
  - Cerebras
  - Google
products_models:
  - Adobe Experience Manager
  - Gemma 4
  - Promptfoo
  - OfOneLabs
media_books: []
status: evergreen
---
<!-- chunk 1/2 -->

### 引言与敏捷站点概念

>> 大家好。感谢各位的光临。嗯，我今天想和大家聊聊敏捷站点（Agility Sites），也就是我们所说的构建超个性化网站。我不只是要聊这个，我还打算向大家展示我们正在构建的东西。
<details><summary>Original English</summary>

>> Hello. Thank you for coming. Um I'm going to talk to you about Agility Sites, how we call it as building hyper-personalized websites. I'm not going to just talk about it. I'm going to show you what we're building.
</details>

嗯，我从事这个项目已经有一段时间了，我们将尝试向大家展示今天借助人工智能可以做到什么。
<details><summary>Original English</summary>

Um I've been working on on this project for for a bit now, and we'll try to show you what is possible today with with AI.
</details>

呃，我在 Adobe 工作，我是 Adobe Experience Manager 也就是内容管理这一产品的主任科学家，知道这款产品的人可能不多。我们为许多大品牌运营着大量的网站资产，而我的背景是在开源领域，呃，为许多基金会和项目做过贡献。
<details><summary>Original English</summary>

Uh I work at Adobe at a I'm a principal scientist at a product that not many people know, Adobe Experience Manager, content management. We run a lot of uh website properties for big brands, and my background is in in open source, uh contributing to to a lot of foundations and projects.
</details>

什么是敏捷站点？我们又是如何构建它的？
<details><summary>Original English</summary>

What are Agility Sites, and how are we building this thing?
</details>

所以，我们正在寻找能够察觉正在浏览的用户意图的站点。用户在做什么？用户试图达到什么目的？最终目标是为当前浏览的用户个性化这些页面，从而最终呃促成更高的参与度或呃转化率，无论营销团队希望达成什么。
<details><summary>Original English</summary>

So, we're looking for sites that are uh looking at the what intent the user browsing uh has. What is the user doing? What is the user trying to achieve? And the end goal is to personalize these pages for the for the current user browsing, so that eventually this uh drives uh higher engagement or uh conversions, whatever the marketing teams want to want to achieve.
</details>

这些页面是根据正在访问该网站的用户以及用户在做什么进行实时个性化的。
<details><summary>Original English</summary>

And these pages are personalized in real time based on the on the user that is uh accessing the site, and what is the what is the user doing.
</details>

### 技术栈与基于模块的个性化

我们使用的技术栈是 AEM 边缘交付（AEM edge delivery）。这是我们拥有的产品部分，呃所有内容都部署在边缘，然后我们有一个后端服务，通过不同的大语言模型提供商或大语言模型服务来支持这种体验。我们使用 Cerebras 来实现快速推理，或者也可以使用，我们也尝试过 Bedrock 以及很多其他的。今天我将展示 Cerebras，大家会看到其中的原因。
<details><summary>Original English</summary>

The stack we're using is AMH delivery. So, this is the part of the product we we have, uh where all the content is on the edge and then we have back end service that powers this experience with different LLM providers LLM services we use Cerebras for fast inference or we can use also we tried bedrock and and a bunch of others. I'll be showing Cerebras today and you will see the reason why.
</details>

对这些内容进行个性化的引擎使用的是富内容和模块（blocks）。网站上的不同模块会根据用户的用户画像进行定制。
<details><summary>Original English</summary>

The the engine that is personalizing this this bits is using the rich content and blocks. So different blocks on the site are customized depending on on what the user persona is.
</details>

我们不希望整个网站都是生成的。我的意思是，如果你和营销人员交谈，他们有非常严格的品牌规范。你不能直接凭空捏造或者出现幻觉。所以个性化的是网站的不同部分，我们把整个网站作为语料库。我们基于整个网站构建了一个 RAG。因此生成的内容是以现有网站为依据的。
<details><summary>Original English</summary>

We don't want the the whole site to be generated. I mean if you talk to marketing people they they have a very strict brand guidelines. You don't want to just come up with our have some hallucinations there. So the what is personalized is different sections of the site and we use the whole site as a corpus. We built a rack from the whole site. So what is generated is grounded on on the existing site.
</details>

我们试图解决千篇一律的问题。我们希望实现超个性化的体验。此外，我们也希望帮助我们的客户进行更多的自动创作。不必去创建网站的成千上万种不同变体，而是借助 AI 来完成这项工作，然后再进行多层次的个性化。
<details><summary>Original English</summary>

We tried to solve the problem where one size fits all. We want hyper-personalized experiences. Also we want to help our customers to do more automatic authoring. So not having to create thousands of different variations of the site but use AI for this and then do these multiple layers of of personalization.
</details>

我们正在做的一些事情的例子，我会在演示中展示。比如即时用户画像适配、查询生成——当用户在网站上搜索内容时，结果页面会为他们进行定制，还有呃推荐之类的功能，在您浏览网站一段时间后，我们可以创建一个页面，根据我们认为您在寻找的内容来推荐一些东西。
<details><summary>Original English</summary>

Some examples of what we're doing or I'll show in the demo. It's instant persona adaptation, query generation when the user search for something on the site, the page with the results is customized for them and also uh, something like recommendations where after you browse the site for a period of time, we we can create a page that recommends something based on on on what you are what we think you are looking for.
</details>

对于营销人员而言，呃他们可以用自然语言来定义这种策略，并且他们可以使用分析数据来驱动个性化闭环，以及最终目标是什么，这又如何反过来进行调整以适配个性化并改进那整个循环。在这次大会上大家都在讨论闭环，这就是其中的一个循环。
<details><summary>Original English</summary>

For marketers, uh, they can define this strategy on natural language, and they can use analytics to to drive the loop of personalization, and what is the end goal, and how this goes back again to change to adapt the personalization to improve that uh, whole cycle. Everybody's talking about loops in this conference, so that's that's one of the loops there.
</details>

架构是什么样的呢？它是一个动态的前端加上一些模块，就是我之前提到的，结合呃边缘交付服务，基本上就是将这些模块组合起来，呃它们通过 AI 实时进行更新。
<details><summary>Original English</summary>

How the architecture look like? So, it's a dynamic front end with some blocks, what I mentioned before, and with uh, edge delivery services is basically you compose these blocks, and uh, they are updated on on real time through with the AI.
</details>

### 模型评估与性能考量

在后端，呃我们进行模型和提供商的评估，我们意识到的一点是，这在很大程度上取决于具体的网站。因此，我们准备了一系列提示词，我们针对种类极其丰富的模型和提供商运行这些提示词，然后查看准确率，查看速度，但这将高度取决于网站的类型，比如网站有多大，网站面向的不同领域是什么，它属于什么类型的商业模式等等。所以我们持续运行这种评估。我们使用 Promptfoo。呃有人听说过 Promptfoo 吗？
<details><summary>Original English</summary>

The back end, uh, we we do the um, evaluation of the models and the providers, and one thing we realized is is that this is very dependent on the site. So, we have a bunch of prompts, and we look uh, we run it across a huge variety of uh, models and providers, and then we look at the accuracy, we look at the speed, but this is going to depend highly on what type of site, like how big is the site, how I don't know, what different what different um, area is the site targeting, what what type of commerce it is, and so on. So, we we run this this um, evaluation continuously. We use uh, Promptfoo. Uh, anybody heard about Promptfoo?
</details>

好的，有几个人。
<details><summary>Original English</summary>

Okay, some people.
</details>

Promptfoo 允许您针对多个模型和提供商来评估模型提示词，您可以使用本地模型以及许多兼容 OpenAI 的提供商等等，基本上支持很多。
<details><summary>Original English</summary>

So, Promptfoo allows you to evaluate models um, prompts against my multiple models, providers, and you can do local models and any of the a bunch of open AI compatible uh providers and and uh a lot of them, basically.
</details>

我们关注两件事。为什么？准确率。那通常是人们所追求的，但同时我们也追求速度，因为我们不希望网站生成需要超过 1 到 2 秒的时间，对吧？因为人们呃这已经被证实了，网站速度越快，产生的转化率就越高，或者对用户来说体验就越好。
<details><summary>Original English</summary>

We look for two things. Why? Accuracy. That's that's typically what people look for, but also we want the speed because we don't want the site generation to take more than 1 or 2 seconds, right? Because people uh this is already uh proven that people want the the faster the site, the more conversions it it generates or the the better the experience it is for the user.
</details>

嗯是的，我提到过不同的网站可能有不同的需求。呃所以，您可能需要根据具体的网站来运行这种模型的评估。
<details><summary>Original English</summary>

Um yeah, what I mentioned is different sites may have different requirements. Uh so, you may have to run this uh evaluation of models depending on the site.
</details>

这是一个示例，呃我们为这个示例网站固定了其中的一些查询，因此我们有 15 个提示词。
<details><summary>Original English</summary>

This is a an ex uh we we secured this some of these queries, so we have a 15 prompts for this example site.
</details>

嗯在顶部大家可以看到，使用基于 Cerebras 运行的上周刚刚发布的 Gemma 4 模型，我们在生成页面时可以获得 1.1 秒的平均延迟。
<details><summary>Original English</summary>

Um we have uh at the top you can see with Cerebras on the Gemma 4 model that was announced last last week, we can get an average latency of 1.1 seconds generating a page.
</details>

您可以将它与第二名相比，第二名是 4.6 秒，对吧？所以差距是非常巨大的。这也是为什么呃我们在这种用例中使用 Cerebras。
<details><summary>Original English</summary>

You you can compare that to the second one, which is 4.6 seconds, right? So, the difference is huge. And that's why uh we use Cerebras for for this use case.
</details>

而且呃大家可以看到，不同的提供商、不同的模型具有不同的速度。这里是呃让我，我可以向大家展示这里的完整内容。不是这个，是这个，对吧？在底部我们有其他任务。
<details><summary>Original English</summary>

And uh you can see that different providers, different models have different um different speeds. And here is uh let me I can show you the whole thing here. Not this one, this one, right? So, at the at the bottom we have other other tasks.
</details>

有时呃其中一些可能表现不错。它们不需要做到完美，只要足够快，就已经足够好了。因此，这正是大家需要做出的决策类型，去权衡模型对您的用例来说是否足够好。
<details><summary>Original English</summary>

Sometimes uh maybe some of them may be good. They don't need to be perfect, but they're good enough if they're fast enough. So, that's going to be the the kind of decisions that you need to make on whether the model is good enough for your use case or not.
</details>

是的，我们关注的是，是的，平均 1.1 秒。而接下来的几个则从 4 秒往上递增。而且您不需要一个庞大的大语言模型来做这类工作，因为您是在生成文本、决定把模块放在哪里以及如何组织网站，完成这些并不需要大量的信息。
<details><summary>Original English</summary>

Yeah, we're looking Yeah, average 1.1 seconds. And then the the next ones are going from 4 seconds higher. And you don't need a huge LLM to do this sort of work because you are generating text, you are deciding where to put blocks and how to organize the website, you don't need a lots of information for that.
</details>

### 个性化机制与推荐实现

因此，这些浏览行为和查询呃正在被记录下来。这些就是我们从用户那里收集的指标或数据，并被输入到大语言模型中以实现网站的个性化。在这个示例中，我们根据用户画像对主推卡片（hero card）、产品、博客信息流以及导航进行了个性化。
<details><summary>Original English</summary>

So, this browsing and the queries uh is are being recorded. So, these are the metrics or the the the data we gather from the user, and this is fed into the LLM to personalize the site. And then in this example, we personalize the hero card, the products, the blog feeds, and and the navigation based based on the persona.
</details>

此外，包括一些按钮，比如我们的号召性用语（call to action）导航，也同样可以个性化。
<details><summary>Original English</summary>

Also, what are some of the buttons like our call to action navigation, you can also we can also personalize those.
</details>

我们创建了一个“为你推荐”（for you）页面，我稍后会向大家展示，这是一个推荐页面。这是一个很有意思的场景，因为这个页面是您可以预先生成的，对吧？当用户浏览您的网站时，您收集这些信号，并可以持续在后台生成。因此在这种情况下，您就不需要那么高的速度了。
<details><summary>Original English</summary>

We we create and I'll show you the a for you page, which is a recommendation. And this is a interesting one because this you could pre-generate, right? As the user browses your site, you gather these signals, and you could keep generating in this. So, in this case, you wouldn't need so such a big speed.
</details>

但那很有趣，因为如果用户想要购买某种东西，您可以直接显示：“好的，为你推荐这三款产品，或者类似的内容。”
<details><summary>Original English</summary>

But but that's interesting because it it would be if a user wanted to buy something, you could just say, "Okay, for you, I will recommend these three products or or something like that."
</details>

嗯是的，随后他们就能看到这个推荐，如果他们点击过去，那部分内容可以已经为他们预取完毕了。当然，随着用户在网站各处浏览等等，您必须保持更新。所以这也是进行多次生成、多次调用大语言模型时需要考虑的成本影响因素。
<details><summary>Original English</summary>

Um Yeah, and then they can see this recommendation, and if they go there, that that could be pre-fetched for them. And obviously, you have to keep updating it as the user navigates around the site and and so on. So that that's also something to consider on the cost cost implications of doing multiple generations, multiple LLM calls.
</details>

当用户执行查询时，系统会向他们展示动态个性化的页面。
<details><summary>Original English</summary>

When when the user runs a query, dynamic personalized page is shown to them.
</details>

这些查询也会被归类到不同的人群画像或意图类型中。这个人试图在网站上做什么？是试图买东西？还是仅仅为了获取信息？因此可以让营销人员来决定划分什么类型的群体、设置多少个群体以及希望如何与客户打交道。AI 则会为这些人群选择相应的模块和建议。
<details><summary>Original English</summary>

When the these queries are also grouped into personas or intent types. So what is this guy what is this guy trying to do in the site? Is trying to buy something? Is trying to just get information? So you can get marketers to decide what type of groups, how many groups you want to have, how you want to deal with with customers. And the AI will choose the the blocks and the suggestions for for those groups of people.
</details>

嗯，而且我们可以适配，是的，不同的模块、模块的顺序以及媒体内容。您也可以处理媒体内容。我们考虑的事情之一是，今天或昨天刚发布了一个模型，nano banana light。所以
<details><summary>Original English</summary>

Um And we can adopt yes, the the different blocks, the the the sequence of the blocks and media. You could also do media. One of the things we consider is there was some a model announced today or yesterday the the nano banana light. So
</details>

<!-- chunk 2/2 -->

你甚至可以非常快速地即时生成图像。显然没有文本那么快，但这同样也是……我不知道像营销人员这样的人是否会想要生成图像。这在很大程度上取决于质量，是否符合品牌调性。

<details><summary>Original English</summary>
 you

 could

 even





generate

 images





very

 fast

 on

 the

 fly.





Obviously

 not

 as

 fast

 as

 text,

 but





that's

 also

 something

 that

 would

 be





I

 don't

 I

 don't

 know

 if

 it's

 that





something

 like

 marketing

 people

 would





want

 to

 have

 generated

 images.

 That





depends

 on

 on

 the

 quality

 a

 lot

 if

 it's





on

 brand.
</details>

在这个示例中，我们有一个产品网站，然后有指南、体验、版块，LLM 的整个回复都基于此进行溯源。而且还有对比。我们可以对定制的产品进行对比，产品页面也可以为用户进行定制。

<details><summary>Original English</summary>
And





the

 site

 in

 this

 example

 we

 have

 a

 a





product

 site





and

 then

 we

 have

 guides,

 experiences,





blocks

 and

 the

 whole

 response

 of

 the

 LLM





is

 grounded

 there.

 And





there's

 comparisons.

 We

 can

 do





comparisons

 between

 products

 that

 are





tailor

 and

 the

 product

 pages

 can

 be





tailored

 for

 the

 for

 the

 user.
</details>

### 技术架构

好的，这是技术栈的一些情况。我不打算在这里花太多时间，但是在浏览器端，你有几个层级。在浏览器端，来自……我得到……我得到……我得到，从用户那里获取信号，然后我们有后端。我们可以有后端，我们把其中一些运行在 Google，一些运行在我们的 Cloudflare。所以，后端基本上只是调用 LLM，并使用在站点上构建的 RAG 进行一些推理，以完成生成。

<details><summary>Original English</summary>
Okay,

 this

 is

 this

 is

 a

 bit

 of

 the





stack.





Um

 not

 going

 to

 spend

 too

 much

 time





here,

 but

 the

 browser

 you

 have

 some





layers.

 You

 have

 the

 browser

 where

 the





signals

 get





get





uh





from

 I

 got

 I

 got

 I

 got

 so





I

 got

 from

 the

 from

 the

 user

 and

 then

 we





have

 the

 back

 end.

 Uh





we

 can

 have

 the

 back

 end.

 We

 run

 this





some

 of

 these

 in

 in

 Google.

 Some

 of





these

 are

 in

 our

 Cloudflare.

 So,

 the





back

 end

 is

 basically

 just

 calling

 the





LLM

 and

 doing

 some

 reasoning

 using

 the





rack

 that

 is

 built

 on

 on

 the

 site

 to

 do





the

 generation.
</details>

显然你必须有向量数据库、推理机制，而那显然的业务管理器正在提供……在边缘提供页面和静态内容的服务。

<details><summary>Original English</summary>
And

 you

 have

 obviously

 you

 have

 to

 have





the

 vector

 database,

 the

 inference

 uh





machinery

 and

 uh





that

 obvious

 business

 manager

 is

 doing





the

 serving

 the





the





at

 the

 edge

 is

 serving

 the

 the

 pages

 and





the

 static

 content.
</details>

### 单人受众演示与实时生成

所以，让我展示给你们看，因为我觉得这……我们称之为“单人受众”，因为在营销领域，他们总是梦想着能够为每个个体实现个性化。所以，是的，我们称之为单人受众。我手上有这个网站。这是一个完全生成的示例网站。它是一个咖啡设备网站。所以我可以去阅读一些故事，也可以去浏览一些产品。

<details><summary>Original English</summary>
So,

 let

 me

 show

 you

 because

 I

 think

 this





is

 uh

 so,

 we

 call

 this

 uh

 audience

 of





one





because

 the

 idea

 of

 in

 marketing





they

 they

 always

 dream

 on

 being

 able

 to





personalize

 things

 for

 each

 individual.





So,

 we

 call

 it

 yeah

 audience

 of

 one.

 So,





I

 have

 this

 this

 site.

 Uh

 this

 is

 a

 site





that

 is

 absolutely

 generated





uh

 example

 site.

 It's

 a

 coffee





uh

 machinery.

 So,

 I

 can

 go

 and

 and

 read





some

 stories





and

 I

 can

 go

 and

 look

 at

 some

 products.
</details>

让我们来看看这款产品。我可以在这里待上一段时间。让我们点击这里。好的，我在网站上四处浏览，我有这个调试工具，它……让我到这里来，我想。看看。

<details><summary>Original English</summary>
Let's

 go

 and

 look

 at

 this

 product.





I

 can

 spend

 some

 time

 here.





Uh





let's

 go

 and

 click





here.





Okay,

 so

 I'm

 I'm

 browsing

 around

 the





site

 and

 I

 have

 this

 debugging

 tool





thing

 uh

 which





Uh





let

 me

 go

 here,

 I

 think.





Let's

 see.
</details>

下面是浏览行为提供给我们的信号。我不知道你们能不能看清楚，因为我自己看不太清楚。所以，用户被归入“探索”类别。我们有访问过的页面，然后有在每个页面上花费的时间。所有这些数据现在都可以供 LLM 使用。

<details><summary>Original English</summary>
So,

 down

 there

 is

 the

 signals

 that

 the





that

 the

 browsing





is

 giving

 us.

 So,

 I

 don't

 know

 if

 you





can

 see

 it

 much

 because

 I

 cannot

 see

 it





much.

 The

 So,





the

 user

 is

 bucketed

 into

 the

 exploring





category.

 We

 have

 the

 pages

 that

 have





have

 visited,

 and

 then

 we

 have

 how

 much





time

 is

 spending

 on

 each

 page.

 All

 of





this

 data

 is

 now

 available

 for

 the

 LLM.
</details>

所以，如果我转到这里，我已经有了一个基于我的浏览器为我生成的“为你推荐”页面。你不会注意到它与其它所有内容略有不同，但如果我来到这里并运行一个查询，比如我想……我正在寻找一台露营时冲泡咖啡的咖啡机。

<details><summary>Original English</summary>
So,





if

 I

 go

 here,

 I

 already

 have

 a

 for

 you





page

 that

 was

 generated

 for

 me





and





based

 on

 my

 browser.





And

 you

 will

 not

 notice

 that

 it's





slightly

 different

 than

 everything

 else,





but

 if

 I

 go

 here

 and

 I

 run

 a

 query





like

 I

 want

 I'm

 looking

 for

 a

 coffee





machine

 to





uh

 prepare





coffee





while

 camping.
</details>

这个网站……这是刚刚为我生成的。然后你会看到一些东西，比如文本是定制的：“露营不应该意味着妥协你的……”随便什么习惯。露营咖啡小贴士，被推荐的设备是 coffee agile 以及 nano，这些都很适合露营旅行，对吧？

<details><summary>Original English</summary>
The

 site

 is

 this

 was

 just

 generated

 for





me.





And

 then

 you're

 going

 to

 see

 some

 things





like

 the

 text

 is

 customized.

 Camping





shouldn't

 mean

 compromising

 on

 your





uh

 whatever

 routine.





Uh

 the

 coffee

 tips

 for

 camping

 um





machinery

 that

 are

 being

 recommended

 are





coffee

 agile

 and

 um

 or

 the

 nano,

 which





are





good

 for





for

 the





for

 a

 camping

 trip,

 right?
</details>

所以，你们看到了这有多快。我要在这里运行一个类似的、我刚才在这里展示的内容，而且我可以在这里的调试模式下运行它。你们会看到，我们把这个放大一点。

<details><summary>Original English</summary>
So,

 you

 saw

 how

 fast

 this

 was.





I'm

 going

 to

 run

 it

 here

 something





similar

 that

 I

 had

 here

 and

 I

 can

 run

 it





on

 the

 debug

 mode

 here.





And

 you

 will

 see,

 let's

 make

 this





bigger.
</details>

生成该页面总共耗时 164 秒。这包括了一次去往 LLM 的往返请求。这是使用运行在 Cerebras 上的 Gemma 4。也就是来自 Google 的 Gemma 模型，运行在 Cerebras 极速芯片之上。我们达到了每秒 2,300 个 token。我会说，这还不错。

<details><summary>Original English</summary>
Total

 time

 164

 seconds

 to

 generate

 the





page.

 So,

 this

 includes

 a

 round

 trip

 to





the

 LLM.

 This

 is

 using

 Cerebras

 Gemma

 4.





So,

 the

 the

 Gemma

 model

 from

 Google





running

 on

 Cerebras

 on

 their





very

 fast

 chips.





Uh

 we

 get





2,300





tokens

 per

 second.





Which

 is

 not

 bad.





I

 would

 say.
</details>

>> [哼笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 如果我再运行一次，大概也是类似的情况。LLM 耗时是 1 秒。同样是每秒 2,200 个 token。这在以前是我们只能梦想的事情。

<details><summary>Original English</summary>
>> And

 if

 I

 run

 it

 again,

 uh

 probably





something

 like

 that.





Uh

 the

 LLM

 time

 is

 1

 second.

 And

 again,





2,200

 tokens

 per

 second.





This

 is

 something

 that

 we

 only

 dreamed





about

 before.
</details>

在这个示例网站上，我们还有一些其他选项。因为我们一直在向客户展示这个，所以我们有能力更改不同的模型、温度、token 数等等。我们可以展示并尝试不同的模型，看看它们的表现如何。除了使用 Prompt Full 进行自动化测试之外，我们还可以手动过来点击各种选项，看看它是如何工作的。

<details><summary>Original English</summary>
On

 the

 on

 this

 site

 example

 site,

 we





have

 some

 other

 options.





Uh





so,

 because

 we

 we've

 been

 showing

 this





to

 customers,

 so

 we

 have

 the





the

 ability

 to

 change

 the

 different





models,

 temper

 temperature,

 tokens,

 and





so

 on.

 And

 we

 can

 uh





we

 can





show

 uh

 and

 try

 the

 different

 models

 and





see

 how

 they

 behave.

 Besides

 the





automatic

 test

 with

 Prompt

 Full,

 then

 we





can

 uh

 manually

 come

 and

 and

 click





things

 and

 see

 and

 see

 how

 that

 how

 that





works.
</details>

### OfOneLabs 与智能体网站生成

而且我们还有 OfOneLabs。我们构建了这个工具，可以为我们想要的任何网站生成一个智能体网站。如果有人想为客户做演示，只需来到这里输入 URL。在不到一个小时的时间内，你就拥有了一个智能体网站。我上周对 AI engineering 网站就这么做过。

<details><summary>Original English</summary>
And

 uh





we

 also

 have





uh

 OfOneLabs.





So,

 we

 have

 we

 build

 this

 tool

 that





generates

 an

 agentic

 site

 for

 any

 site





we

 want.

 So,

 if

 somebody

 wants

 to

 have

 a





demo

 for

 a

 customer,

 come

 here





and

 enter

 the

 URL.

 In

 less

 than

 an

 hour,





you

 have

 an

 agentic

 site.

 I

 did

 this





last

 week

 with

 the

 AI

 engineering

 site.
</details>

我得到了这个只有一个搜索框和一些其他内容的网站。让我在完整页面中打开它。不是这个。对，好的。

<details><summary>Original English</summary>
And





I

 got

 this

 site

 that

 is

 just

 a

 search





box

 and

 a

 few

 things.





And





let

 me

 open

 it

 here,

 the

 full

 page.

 Not





this

 one.

 Yeah,

 okay.
</details>

我可以输入“欧洲 AI 会议”。这些建议也是 AI 生成的。然后我得到了一个更加侧重于……它应该更加侧重于这些欧洲会议的页面。

<details><summary>Original English</summary>
So,

 I

 could

 say





Europe

 AI

 conferences.





So,

 these

 suggestions

 are

 also

 AI





generated.

 And

 I

 get

 a

 page

 that

 is





more

 focused

 on





It

 should

 be

 more

 focused

 on

 on

 the

 on





this

 European

 conferences.
</details>

如果我回去，我刚才回去了吗？我可以像之前对 Arco 那样搜索任何内容。作为一个具体……之前有一个生成了很好的并排对比。让我看看是不是这个。好的，这里，这个。

<details><summary>Original English</summary>
If

 I

 go

 back,

 did

 I

 go





I

 can

 search

 for

 anything

 the

 same

 way

 I





did

 with

 with

 the

 Arco.

 So,

 I

 as

 a





specific

 There

 was

 someone

 that

 was





generating

 a

 good

 comparison

 side

 to





side.





Let

 me

 see

 if

 this

 one.

 Okay,

 here.

 This





one.
</details>

我去查看，这里生成了一个具有相当不错对比的页面。如果我正在看两场会议，需要做出决定，如果我们弄清楚用户想要这样做，这非常棒，因为这可以在线即时为他们提供并排对比。

<details><summary>Original English</summary>
I

 went

 and

 this

 generated

 a

 page

 with





a

 pretty

 good

 comparison.

 If

 I'm

 looking





at

 two

 conferences

 and

 I

 need

 to

 decide,





if

 I

 figure

 out

 that

 the

 user

 wants

 to





do

 that,

 this

 is

 great

 because

 that





gives

 them

 a

 side-by-side

 comparison

 on





the

 fly.
</details>

### 未来展望与多端体验

现在，我觉得这已经很酷了，但接着我们……我有了这个想法。很多人都在讨论：网络是否……网络仍然是未来吗等等。没有人知道。但我们也可以利用这种单人受众、这些生成式网站来做一些事情。设想一下你拥有你的个人助理，你通过……在这个例子中是通过 Google 提出一个查询，你说“我想买……”我不记得具体的查询语句是什么了。大概类似于“我想买一台机器”，然后我在我的 Google TV 上得到了这个结果。对吧？所以这是完全根据我的查询进行个性化定制的。

<details><summary>Original English</summary>
Now,





this

 this

 is

 I

 think

 this

 is

 cool





already,

 but

 then

 we

 have

 I

 have

 this





idea

 that





probably

 the

 I'm





a

 bunch

 of

 people

 are

 we

 are

 talking





about

 is

 the

 web

 that

 is

 is

 the

 web

 the





future

 still

 and

 so

 on.

 Nobody

 knows.





But

 we

 can

 also

 do

 something

 with

 this





with

 this

 audience

 of

 one,

 this





generative

 sites.

 So,

 imagine

 you

 have





you

 have

 your

 personal

 assistant

 and

 you





ask

 a

 query

 through

 in

 this

 case

 through





Google

 and

 you

 say

 I

 want

 to

 buy

 I

 don't





remember

 what

 the

 query

 said.

 It

 was





something

 like

 I

 want

 to

 buy

 a

 machine





and

 I

 get

 this

 on

 my

 Google

 TV.





Right?

 So,

 this

 is

 absolutely





personalized

 to

 my

 query.
</details>

好吗？不，退回。这完全是根据我的查询定制的。我就在我的客厅里。我不需要手机，不需要电脑，什么都不需要，只需要我的声音，以及某种可以向我展示完全为我个人定制的内容的设备。好的，就是那个。

<details><summary>Original English</summary>
Okay?

 No,

 go

 back.





This

 is

 absolutely

 personalized

 to

 my





query.

 So,

 I'm

 there

 in

 my

 living

 room.





I

 don't

 need

 a

 phone,

 I

 don't

 need

 a





computer,

 I

 don't

 need

 anything,

 just

 my





voice

 and

 something

 that

 will





kind

 of

 show

 me





something

 that

 is

 absolutely





personalized

 to

 to

 me.





Okay,

 so

 that

 one.
</details>

所以，我刚才尝试展示的，也希望大家能从本次活动中记住的，就是这现在已经成为可能。从现在开始，它只会变得更好。它只会变得更便宜，只会变得更快。你们将能够为网站和其他事物获得巨大的个性化定制选项。你们可以通过意图驱动来实现这一点。“我的用户想要做什么？我的用户想买什么？”这类问题。你们可以专门为他们拼装出一个页面。你们还可以通过多种模型来做到这一点，最终它只会越来越快，对吧？

<details><summary>Original English</summary>
So,





what

 I

 was

 trying

 to

 show

 and

 hopefully





you

 remember

 from

 this

 session

 is

 that





this

 is

 now

 possible.





It's

 only

 going

 to

 get

 better

 from

 here





on.

 It's

 only

 going

 to

 get

 cheaper,

 it's





only

 going

 to

 get

 faster.





And

 you

 will

 uh

 be

 able

 to

 have

 uh





huge

 personalization

 options

 for

 sites





and

 for

 other

 things.





And

 you

 can

 do

 this

 with

 intent

 driven.





So,

 what

 is

 the

 what

 is

 my

 user

 trying





to

 do?

 What

 does

 my

 user

 want

 to

 buy?





These

 sort

 of

 questions.

 And

 you

 can

 uh





assemble

 a

 page

 just

 for

 them.





And

 you

 can

 also

 do

 this

 with

 uh





multiple

 models

 and

 and

 eventually





it's

 just

 going

 to

 be





faster

 and

 faster,

 right?
</details>

那么，就是这样。谢谢大家的到来，希望你们领会到了这个思路。谢谢。

<details><summary>Original English</summary>
So,





that's

 it.

 Um





thank

 you

 for

 coming

 and

 I

 hope

 you

 you





got

 the

 idea.

 Thanks.
</details>

>> [掌声]

<details><summary>Original English</summary>
>> [applause]
</details>