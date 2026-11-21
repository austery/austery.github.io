---
author: AI Engineer
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=504PvfXou5Y
speaker: AI Engineer
tags:
  - decision-making
  - software-architecture
  - product-development
  - behavior-driven-development
  - continuous-integration
title: 捕捉决策：为人类与AI构建一致性
summary: 本讲座深入探讨了在软件开发中，如何通过架构决策记录（ADR）、产品需求文档（PRD）和行为驱动开发（BDD）等方法，为人类和人工智能代理捕捉并执行关键决策。讲者强调了记忆和上下文对人类和大型语言模型（LLMs）的重要性，并提出了一个以Git Hooks、CI/CD和Linter为核心的“强化循环”，以确保产品设计和代码实现的一致性与可维护性。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Safe Intelligence
products_models:
  - Spec 27
media_books: []
status: evergreen
---
### 决策框架：AI与人类的共通困境

在快速发展的技术世界中，无论是人类团队还是人工智能代理，都面临着在复杂项目中保持决策一致性的挑战。主讲人Michal Cichra，来自Safe Intelligence团队，他在微软和红帽等公司积累了十年经验，目前正致力于解决AI领域中这一核心的“一致性问题”。他指出，决策捕获的故事在每个产品中都会出现，AI的引入使得这些问题暴露得更快。核心问题在于有限的**上下文**（Limited Context），人类会遗忘，而大型语言模型（LLMs）则因其固有的无记忆特性和有限的上下文窗口，频繁遭遇“上下文压缩”（Context Compact）的挑战。这种现象导致团队不断追问“为什么会有这个流程？”、“这个功能的目的是什么？”或“这段代码为何如此？”。为了解决这些问题，系统性地记录和强制执行决策变得至关重要。

<details>
<summary>Original English Source</summary>

>> Hi, I'm Michal. Welcome to capturing decisions for humans and AI alike. Yesterday with a team from Safe Intelligence, we have released Spec 27, a new product to test agents. Before that, I was in Microsoft, Red Hat, and spent in 10 years working on a single product. The consistency problems we face with AI and the story of capturing decisions show up in every product I have seen. And these notes are distilled from the experience. And you can find me at the booth. Um So, BDD, PRD, ADR, like that's a lot of acronyms. Uh why does any of that matter? So, let's unpack it from the end. You probably know this story. Uh I hope it's not an urban legend, uh but scientists put five monkeys in a cage with bananas on a ladder. Then gave them a cold shower every time a monkey tried to get a banana. Other monkeys beaten up the poor fellow. Then they replaced the monkeys one by one and none of the originals remained. And yet, they have beaten up every monkey that tried to climb the ladder not knowing why. So, humans and LLMs, they suffer from the same trait. Limited context. People forget. LLMs context compact. Humans leave. LLMs have no memory.
>> [snorts]
>> After a while of operating a product, the team starts asking, "Why do we have this flow? Why is this goal of this feature? Why is this code shaped like that? Why Where does this belong?" And you might not have the founding engineer available to answer. And these problems show in every org. Uh maybe with AI much sooner than they used to.

</details>

### ADR：架构决策记录的核心价值

**架构决策记录**（ADR: Architecture Decision Record）是一种记录系统架构中“为何”做出某个决策以及“如何”实施该决策的文档。它不仅解释了决策背后的原因，还指明了如何通过引用文档和代码片段来强制执行这些决策。例如，为了防止常见的**N+1查询**（N+1 Queries: 在循环中为每个结果项执行额外的数据库查询，导致性能低下），团队可能决定将代码分层，并通过**Linting**（Linting: 静态代码分析，用于检查代码风格、潜在错误和结构问题）来限制模块间的导入。另一个例子是强制数据库返回**纯数据结构**（Plain Shapes: 简单的、不包含行为方法的原始数据对象），而非**ORM对象**（ORM Objects: 对象关系映射工具生成的对象，通常包含业务逻辑和数据库连接），以避免不必要的查询和数据重复。ADR的核心是概念而非严格的格式，它通过提供“规则是什么”、“为何存在”以及“如何修复”的信息，指导人类和AI代理解决问题。AI代理可以根据ADR查找相关文档，了解决策依据和解决方案。

<details>
<summary>Original English Source</summary>

So, ADR is architecture decision record. It records why you do something and how you enforce it or how you want to do that. And you can cover examples by reference docs and code snippets. For example, we split code in layers to prevent N+1 queries. We enforce that split by linting imports in modules. And we also enforce reading from database returns um plain shapes instead of ORM objects, so we cannot um cannot make these uh these queries and to prevent duplication. And also linting it by module imports. And another like 50 ADRs that define architecture of the product. There is not a single format that that you need to use. It's just a concept. Um It's a text, so there is no specific uh way how to enforce it. You still need a tool to enforce it. But the tool will tell you that this is the rule. Why are you doing this? And how are you supposed to fix it? Then the agent will go and try to find this document why this reason exists and more information about how to fix it. Also, you can define like which files it actually concerns to, like is it some Python files or some folders? And how you actually enforce it.

</details>

### PRD：产品需求的轻量级导航

**产品需求文档**（PRD: Product Requirements Document）是一种相对轻量的文档，用于描述新功能为何存在、它解决了什么问题，以及用户如何通过应用程序与它互动，即**用户旅程**（User Journey: 用户在使用产品或服务时所经历的完整路径和体验）。PRD无需冗长和详尽，只需捕捉核心的“为什么”、所要解决的“问题”、设定的“目标”以及连接这些点的“旅程”。这不仅对未来几周后可能遗忘初衷的自己有益，对AI代理也同样重要，能帮助它们理解功能的上下文和意图。

<details>
<summary>Original English Source</summary>

PRD is a product requirements document. Uh that's something lighter when you're building a feature, you describe why that thing exists and what problems it solves. And how user goes through the app to actually interact with it. What's the journey through the application. It can be very light. It doesn't need to be really long and exhaustive like a massive document. Uh you can just capture why, the problem, and the goal, and the journey that connects them. And it's not just for the agents, but also for you 6 weeks from now when you forget why you did that.

</details>

### BDD：行为驱动开发，可执行的规范

**行为驱动开发**（BDD: Behavior-Driven Development）提供了一个中间层，用人类可理解的语言描述产品行为，并使其可执行和可读。尽管它不是一个新颖的概念，但随着AI代理的兴起，BDD（例如**Cucumber框架**（Cucumber Framework: 一种支持BDD的测试工具，通过Gherkin语言编写易读的验收测试））重新变得重要。BDD规范可以直接与PRD和关键用户旅程关联，形成可读、可执行的闭环，解决了传统**规格驱动开发**（Spec-Driven Development: 通过编写详细的产品规格文档来指导开发过程）中验证产品是否实际遵循规格的难题。AI代理可以读取、理解并评审这些行为规范，从而确保产品行为与预期一致。

<details>
<summary>Original English Source</summary>

Now, BDD. Um it's behavior-driven development. You have probably seen spec-driven development lately, uh but if you practiced it, uh you might have suffered the same thing as me. How do you validate that the product actually adheres to the spec? It's a markdown document, you describe how it's supposed to work, but how do you know it actually works like that? One thing harder than reading an AI code is reading AI tests. Um so, what if you had an intermediate layer that actually describes how the product behaves in a human language? And BDD is not new and shiny, but it's it can be executable and readable. So, enter Cucumber. It's almost forgotten, suddenly useful again. It's definitely easier to review than your average tests. You can connect scenarios directly to your PRDs and critical user journeys. It can be readable, executable, and it closes the loop that a spec-driven [clears throat] development leaves open. These rules, uh these specs are later parsed by steps and they are executed as code. But what you can do is that you can actually write and read these. And you can review these. And you can understand these. The language is on you. It doesn't need to be um enforced. Like you There are multiple ways how to write these uh these features. And that's it, but they describe how you're supposed to go through the application, why this thing exists, and how it runs. And similarly, they can refer back to all the documents that you have about why things exist. So, and as a bonus,

</details>

### 设计系统：构建一致性UI的基石

即使在AI时代，**设计系统**（Design System: 一系列可复用的组件、模式、指南和工具的集合，用于在不同产品和平台间实现设计和代码的一致性）和**模式库**（Pattern Library: 包含可重用UI模式和组件的集合，通常是设计系统的一部分）仍然是构建一致性用户界面（UI: User Interface）的关键。通过明确定义设计语言，例如一个**主按钮**（Primary Button: 界面中最突出、最重要的操作按钮）的颜色、形状和尺寸，并制定“一个页面上只能有一个主按钮可见”等规则，可以有效强制执行设计一致性。组件和模式的定义、预览及其工作方式的展示，不仅方便人类团队复用，也使AI代理能够理解并遵循这些设计原则。通过将小部件组合成大部件，不断复用，可以避免UI设计中的混乱。

<details>
<summary>Original English Source</summary>

making consistent UIs with agents is just another level of hard. Like design system and pattern library are the way to build consistent UIs. Like that was the way before AI and it is the way now. So, you document your language. You say, for example, a primary button is this and that. It is blue. It has this shape. It has this color and it's this size. And you say your rules. You say, "We will have only one primary button visible on a site at any on on a page at any point in time." And then you can enforce these rules. Similarly, you define components and patterns. So, for example, if you have multiple colors of these buttons and multiple states, you define components and you define previews and you demonstrate how they work and you create snippets of previews, so you can actually see them. And the agents can see them. And then you can go and review and like do these actually adhere to the principles that I have? Do they adhere to the visuals? And then you reuse them. As with code, you build these from the ground up from small pieces into bigger ones. You compose them and you reuse them. Otherwise, it's uh chaos like with the code. So,

</details>

### 强化循环：自动化决策的执行机制

要确保团队和AI代理始终遵循这些决策和规范，需要建立一个强大的**强化循环**（Reinforcement Loop: 一种持续反馈和改进的机制，确保系统行为与预设规则和目标一致）。这个循环由**Git Hooks**（Git Hooks: 在Git操作（如提交、推送）前后自动执行的脚本）、**技能**（Skills: 为AI代理定制的特定任务或能力）、**持续集成**（CI: Continuous Integration: 开发者频繁地将代码集成到共享主干，并通过自动化测试验证其正确性的实践）和**代码检查工具**（Linters: 静态代码分析工具，用于发现代码中的风格问题和潜在错误）共同构成。AI代理的目标是提交拉取请求，它们需要使用Git。通过Git Hooks在提交前运行预定义任务，并在CI中再次执行相同任务，可以捕获任何试图绕过规则的行为。这包括代码检查、格式化、类型检查、代码重复、架构检查和文档检查等。代码审查的重点也从琐碎的风格问题转向更高层次的概念。通过强制执行架构规则，例如禁止端到端BDD测试套件访问数据库，或者在渲染模板时禁止直接与数据库交互，可以从根本上防止**N+1查询**等问题。当AI代理的提交因违反规则而被拒绝时，它们会获得反馈并被链接到相关文档，从而学习并迭代改进。

<details>
<summary>Original English Source</summary>

cool. These are cool ideas, but how do I actually enforce this? So, my team and agents stick with it. How do I keep it consistent? Well, with the loop. You probably have heard about closing the loop, reinforcement loop, the harness. How to remind the agent that there are rules and how to follow them. So, our loop is simple. It is git hooks, skills, CI, and linters, and a bunch of other checks. Agent's goal is to deliver a pull request and they To do that, they need to use git. So, we use git hooks git hooks to run predefined tasks and these tasks are later executed on a CI. They are the same tasks that they are executed as as hooks. If, for example, agents would get lazy and not want to execute them or skip them, then they get caught. And we include linting, formatting, type checking, code duplication, architecture checks, document linting, everything that's that's possible. So, there was a time where code reviews were about style and tabs and spaces and there is no space for that anymore. All these things are not for discussion. They are rules and they are enforced and they are automated because there is no space for discussion about these anymore. It's more about the high-level concepts. What you cannot find, you cannot enforce. So, for example, we enforce architecture of the product and of the code. We separate modules um and their imports, so what you can use from where. For example, our end-to-end BDD test suite cannot access database. So, we forbid from accessing any module that could access database and basically force the module to the models to iterate without database and really use only the browser features of the application. Similarly, in the product itself, we enforce we cannot talk to database from rendering templates. So, we know that there are no N+1 queries ever. We just define ways to prevent these problems from happening ever. You cannot keep finding them. You need to prevent them entirely. Then the come the agent tries to commit it and push it and they get feedback on the commit and get rejected and they get linked back to the document and they go read it and fix it. And iterate.

</details>

### 多样化焦点：提升循环效率

尽管强化循环的机制保持不变，但其焦点会根据任务的不同而调整。通过引入不同的**技能**（Skills: AI代理的定制能力），可以为循环提供特定上下文。例如，当提到ADR时，AI代理会查找相关的ADR文档以了解如何操作；PRD技能则帮助代理理解产品需求。对于用户界面循环，一些检查可以被跳过，以便代理能更快地在浏览器中迭代。此外，**测试技能**（Test Skill: 根据代码覆盖率和文件变更识别并运行相关测试的能力）能够智能地识别需要运行的测试子集，而不是整个测试套件，从而提高效率。所有这些技能都旨在为强化循环提供更精确的焦点，但循环本身的核心逻辑始终如一。

<details>
<summary>Original English Source</summary>

So, there are some drawbacks. Um it is Oh, sorry. It's not drawbacks. It Um so, this loop is generic. This loop where they do some work, they they push it and they get feedback and they iterate. But the loop can be multiple things, right? Like sometimes you're working on a product feature, sometimes you're working on a UI, sometimes you're working on more back-end-ish back-end-ish things. So that loop is the same, but what changes is the focus of the loop. So we have different skills. There is ADR that whenever there is an ADR mentioned, the agent will look up ADRs, how to operate with them. How to find code that affect that's affected by these ADRs. For PRD the same. For for UI loop, we actually skip bunch of checks and rather force it to iterate in a browser quickly. And test skill that actually identifies tests to run based on code coverage and file changes. So we run just a focused part of the suite and not the entire suite. And some goal execution that actually keep decisions that the model makes so we can review them later. But all of these provide focus in the loop, but the loop still stays the same.

</details>

### 挑战与展望：上下文管理的艺术

这种方法的一个主要挑战是其对**上下文**（Context: AI模型在处理请求时可访问和利用的信息范围）的重度依赖。在研究初期，AI代理可能会耗尽上下文窗口。然而，主讲人表示，在实际操作中，“上下文压缩”并不可怕，因为重要信息会存留下来，并且AI代理会反复查找这些信息。最终目标是实现AI代理能够基于明确定义的规则自主运行数小时，并且每次迭代都能通过反馈循环进行改进。通过系统记录决策、描述产品部分（例如使用PRD）、利用行为驱动开发的可执行规范（如Cucumber）、构建设计系统来确保UI一致性，并采用强化循环将其整合，可以有效地为人类和AI构建并维护一致性。

<details>
<summary>Original English Source</summary>

There are drawbacks. It is very context heavy. Like you can run out of half of the context in um starting the research. Um but I have no fear of context compacts. Like this actually for like last half year actually works, I think. So in my sessions there 20-50 context compacts and it's it's okay. Because the important things survive and the agent will always look them up again. So and that's the goal anyway, right? Like you want to have multiple hour sessions with a clear goal that agent can operate autonomously with the rules that you define. So that's the goal anyway, like So there are decisions that you can record. There are parts of the product that you can describe why these exist. There is um cucumber or BDD that can have executable specifications that you can actually read and review, understand. Design systems can help you to build consistent UI from components. And um again, enforce it that for example, there are no inline styles anywhere else. And you employ harness to loop it all together. So may the spec be with you. That's it.
>> [applause]
[music]

</details>