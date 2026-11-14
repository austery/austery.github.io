---
layout: post.njk
source: https://baoyu.io/blog/from-note-taking-app-to-ai-workspace-the-simon-last-interview
speaker: baoyu.io
title: Notion 联合创始人 Simon Last：我从去年夏天起就没写过一行代码了 | 宝玉的分享
date: '2026-03-28'
summary: 本文访谈 Notion 联合创始人 Simon Last，深入探讨了 Notion AI 的演进历程，从写作助手到通用 Agent 的开发挑战与策略。文章强调了 AI 系统需要持续重写以适应模型进步，编码 Agent 是 AGI 的核心且彻底改变了 Simon 的工作方式，使其成为 Agent 管理者。Notion 奉行“模型界瑞士”策略，不绑定厂商，并为 Agent 重新设计了 API。其核心使命已转变为“管理 Agent 替人做事”，预示着生产力工具的新范式。
area: tech-engineering
category: ai-application
tags:
  - ai-agents
  - notion-ai
  - coding-agents
  - future-of-work
people:
  - Simon Last
  - Ivan Zhao
companies_orgs:
  - Notion
products_models:
  - Notion AI
  - GPT-4
  - GPT-5
  - Claude Sonnet 4
  - Claude Code
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-03-28

# Notion 联合创始人 Simon Last：我从去年夏天起就没写过一行代码了

作者：

宝玉

Simon Last 是 Notion 的联合创始人，也是 Notion AI 背后的核心推动者。他和另一位联合创始人 Ivan Zhao 在 2013 年创办 Notion，目前平台用户超过 1 亿。在这期访谈中，Simon 讲了 Notion AI 从 2022 年墨西哥全员大会上的 GPT-4 初体验开始，经历写作助手、语义搜索、通用 Agent 三四次失败，到最近发布 Custom Agent 的完整历程。他还分享了自己怎么用编码 Agent 工作（个人纪录：一个 Agent 连续跑了 13 天），以及 Notion 的使命如何从“帮人做事的工具”变成“帮人管理 Agent 的工具”。

访谈来源：No Priors 播客第 153 期，2026 年 3 月 12 日，主持人 Sarah Guo

原始视频：https://www.youtube.com/watch?v=1dYThQgOyZU

## 要点速览

Notion 的 AI harness（围绕大模型构建的系统层）大约每六个月推倒重写一次，很多公司做了一版就不动了，Simon 认为这是常见错误。

Notion 尝试了三到四次才做出能用的通用 Agent。2025 年 9 月发布 Personal Agent，2026 年 2 月发布可自主运行的 Custom Agent。

编码 Agent 用得好，产出比人写的更健壮；用得差，产出全是垃圾。关键在于验证循环的设计，不是“凭感觉编程”。

Simon 的个人纪录是一个编码 Agent 连续运行 13 天不停。他每天睡前安排任务，目标是第二天醒来 Agent 还没做完。

Notion 为 Agent 专门设计了新 API：页面用自定义 Markdown 方言，数据库用 SQLite 语法，原有的 JSON 格式对 Agent 太冗余。

Notion 自称“模型界的瑞士”，不锁定任何一家模型厂商，已开始上线中国开源模型。

Notion 的使命发生了根本转变：从“为人类创造最好的直接做事的工具”变成"为人类创造最好的管理 Agent 来替你做事的工具"。

## 【1】墨西哥的 GPT-4 时刻

Sarah 问 Simon，听说 Notion 第一次接触 GPT-4 是在墨西哥的公司全员大会上？

Simon 说那是 2022 年。他一直在关注 AI 领域的进展，但直到拿到 GPT-4 的测试权限，事情才变得“非常、非常真实”。当时他和 Ivan 都拿到了一个类似 ChatGPT 的早期界面，两人立刻发现了两件事：一是这个模型够聪明，能理解比较复杂的指令，能帮你写东西、改东西；二是它的知识面极深极广。

> 当我们试用之后，对我们俩来说立刻就很清楚：现在就是开始思考怎么应用它的时候了。它只会越来越好。
> （“When we played with it, it became just instantly clear to both of us, okay, the time is now to start thinking about how to apply this. It's only going to get better.”）

他们立刻形成了一个短期计划和一个长期计划。短期很明显：文档里的写作助手，选中文本让 AI 帮你改写或生成。团队组了一个突击小队，两三个月后就发布了。长期计划更大胆：做一个通用 Agent，给它 Notion 里所有人类能用的工具，让它能自己创建数据库、写文档、做搜索，把这些串起来完成更长链条的任务。

短期计划很快就上线了。长期计划那时候根本跑不通。

【注：Simon 和 Ivan 通过 Twitter 上的 Tools for Thought（思维工具）社区认识，2013 年创办 Notion。Notion 2024 年达到 1 亿用户，2025 年 ARR 约 6 亿美元，估值约 110 亿美元。】

## 【2】从写作助手到语义搜索

Notion AI 的第一个功能是 AI Writer，2023 年 2 月对所有用户开放。这是最容易实现的：单步任务，改写和编辑文本，不需要检索，直接调用模型。

紧接着团队开始做 Q&A 功能：对整个工作空间做语义索引（semantic index，即把文本转化为向量以便按语义而非关键词检索），然后让用户提问，AI 给出基于来源的回答。这个功能 2023 年 10 月上线，但工程量大得多，因为不是简单接入大模型，而是要做一个实时更新的索引系统，还要认真搭建评估体系来保证质量。

Q&A 上线后，Simon 马上意识到应该把索引扩展到 Notion 之外，于是开始接入 Slack、Google Drive 等外部数据源。

Sarah 追问：这些平台自己的搜索也没做好啊，你们凭什么觉得自己能做得更好？

Simon 笑了：对，我们也很困惑为什么大多数公司做索引做得这么差。他的判断是，关键在于两样东西。一是对 AI 有浸泡出来的直觉（他用的词是 AI-pilled savviness），清楚模型能做什么、不能做什么。二是工匠精神和对细节的关注。每个数据源都不一样，你不能用一套方案处理 Slack 和 Google Drive，它们是完全不同类型的信息。必须大量尝试不同的查询，每天使用，不断迭代分块策略和检索流程。

Sarah 问 Notion 工作空间的组织方式千差万别，这对搜索不是很大挑战吗？

Simon 的回答有点反直觉：在向量嵌入（embedding）时代，工作空间的组织结构其实不那么重要了。 AI 不关心你的文件夹树状结构长什么样，它只关心有没有一段文本包含你需要的信息。他现在甚至建议用户：“不要太纠结组织方式，把东西扔进去就行。”

当然，分块策略（chunking strategy，即把长文档切成多大的片段供检索）这些技术决策依然很关键，但那是对用户透明的，跟用户怎么组织自己的东西无关。

## 【3】每六个月推倒重来

Sarah 说 Ivan 让她一定要问一个问题：你们的 AI harness 重写了多少次？

【注：harness 在这里指围绕大模型构建的整套系统层，包括提示词管理、工具调用、上下文拼装、输出处理等。】

Simon 说这已经成了内部的一个梗了。大概每六个月重写一次，而且重写周期在缩短，因为技术进步在加速。

他认为这是很多公司犯的一个关键错误：做了一版就固定下来不动了。你必须时刻关注模型和技术的最新状态，然后围绕当前状态深度设计整个系统和产品。这意味着每六个月就得重写。

> 我觉得这挺好玩的。这是流程的一部分。你可以重新开始，重新思考。
> （“I find it pretty fun. It's part of the process. You get to restart and rethink it.”）

他说他们马上要发布新版 harness，同时已经在想下一版了。

## 【4】编码 Agent 改变了一切

Sarah 接着这个话题问：既然你们这么愿意推倒重来，编码 Agent 是不是让这件事变得更轻松了？

Simon 说完全正确。他 2025 年 4 月左右开始用 Claude Code，从此彻底改变了工作方式。

他把编码 Agent 的演化分了几个阶段：先是 Tab 自动补全的时代，然后是能帮你插入和改写一些代码，但真正的转折是 Agent 开始能端到端地实现、验证和维护代码。

关键在于：你需要认真思考架构和验证循环。不是“凭感觉编程”（vibe coding），不是随口说一句你想要什么就完事了。你得想清楚“我要做什么改动？怎么验证它是对的？怎么安全部署？”然后让 Agent 帮你执行这个过程。

> 用得好的话，你可以做比以前更雄心勃勃的事情，而且比人写的更健壮。用得差的话，产出全是垃圾。
> （“If you do it well, you can be much more ambitious about what you're building and also make it much more robust than you could have done with humans writing it. And then the flip side is, if you do it badly, it's all slop.”）

他还提到了 Notion 内部的一个有趣变化。设计团队做了一个叫 Design Playground 的 git 仓库，就是一个简化版的 Notion，里面有一堆 UI 基础组件和一个内置 Agent。所有设计师都可以快速搭建高保真、可部署的原型。以前讨论设计方案是指着一张静态图说“这个会长什么样？”，现在设计师直接给你一个可以打开的 URL。

整个工程团队都在经历这种变化。内部感觉更混乱了一点，但 Simon 说他喜欢这种混乱：更多原型、更多实验、每个 PR 都更有野心。

Sarah 问：对于涉及数据安全等高风险的部分，你们会画线吗？

Simon 说所有 PR 仍然要做代码审查。现在的 PR 都是 Agent 写的，更大更复杂，这是不好的一面。但好的一面是测试覆盖率大幅提高。他个人现在不会提交任何没有完整单元测试的 PR。

## 【5】100 倍工程师是真的

Sarah 问：AI 工具对团队规模和人才结构有什么影响？

Simon 说核心变化是：每个人的产出上限都大幅提高了，而产出越来越取决于你使用工具的能力和意愿。

但团队规模没有因此显著缩小。Notion 一直喜欢用小规模的突击小队，这在 AI 之前就是对的，AI 之后可能稍微更对一点，但变化不大。

Sarah 追问：普通工程师和那些特别会用工具的工程师之间，差距会不会越来越大？

> 差距更大了。如果你现在会用这些工具，你可以成为 100 倍甚至 1000 倍工程师。最低门槛没变，但上限极大地提高了。
> （“You can be a 100 or 1,000x engineer if you're using the tools right now. The minimum bar has not changed, but the maximum bar has extremely increased.”）

## 【6】三四次失败之后，Agent 终于上线了

Sarah 问：你之前说通用 Agent 那时候还跑不通，现在到什么程度了？

Simon 说他们挣扎了好几年来做 Agent。每次做出来“差不多能用”，但就是不够有用。主要原因是时机太早。他们前后尝试了三到四次。

终于在 2025 年 8、9 月上线了。 现在你在 Notion 里用的 AI 就是一个完整的 Agent，可以访问 Notion 里几乎所有东西：创建数据库、更新内容、创建文档、搜索网页、做研究。每个用户都有一个 Personal Agent，拥有和用户相同的访问权限。

【注：这就是 2025 年 9 月 18 日发布的 Notion 3.0。Notion 将其定位为继 1.0（文档协作）和 2.0（数据库与工作流）之后的第三次重大进化。】

然后在访谈的大约两周前，Notion 发布了 Custom Agent。和 Personal Agent 不同，Custom Agent 默认没有任何权限，你需要手动授权它能访问什么。但一旦授权，它可以在后台自主运行。

比如你可以给它一个数据库用来记录任务，然后把它接到一个 Slack 频道，它就会自动回复 Slack 上的消息并创建任务。或者你可以让它定期搜索网页和工作空间，然后自动填充周报数据库。

【注：Custom Agent 于 2026 年 2 月 24 日正式发布。Notion 称其早期测试者已创建了超过 21000 个 Agent，Notion 内部运行的 Agent 数量已超过员工数。】

## 【7】AGI 的内核是编码 Agent

Simon 说他最兴奋的一个方向是让 Agent 能从一个初始内核出发，自我引导（bootstrap）出新的能力。比如如果某个集成还不存在，Agent 可以自己写代码构建这个集成，部署它，然后使用它。

Sarah 确认：所以 Notion 的 Agent 是那种更广义的定义，写代码也是一种工具？

> 编码 Agent 就是 AGI 的内核。AGI 就会是一个编码 Agent。代码是表达确定性逻辑非常好的原语。
> （“I think of coding agents as the kernel of AGI. AGI will be a coding agent, and code is just a really useful primitive for representing deterministic logic.”）

Simon 认为这对知识工作 Agent 特别有意义：它可以自己”长出”新能力。集成不存在？自己建。需要连接新数据源？自己接。

## 【8】“模型界的瑞士”

Sarah 提出一个竞争格局的问题：Notion 面对的是规模更大的生产力平台和 AI 实验室，它们也在试图做跨数据源的集成和 Agent。Notion 凭什么赢？

Simon 把市场分成三层：实验室（模型商）、软件平台、基础设施。

在模型层面，Notion 把自己定位为“模型界的瑞士”：不绑定任何一家模型商，客户不想被锁定，不同月份不同模型各有优势，Notion 要让用户随时能用到最好的模型，而且能方便地切换。

Sarah 追问：开源模型呢？

Simon 说开源模型确实变得很好了。有四家中国模型现在都“相当不错”，他们刚在 Agent 中上线了其中一款，计划全部接入。这些模型比前沿模型便宜很多，很多场景用它们更合适。

Notion 的定位是：把最好的模型都接进来，做高质量的 Agent 实现，然后提供一个真正适合人和 Agent 协作的工作空间。

【注：截至访谈时，Notion 已支持 GPT-5、Claude Sonnet 4 等前沿模型，以及 MiniMax 等开源模型。用户可在 Agent 设置中选择模型。】

## 【9】为 Agent 重新设计 API

Sarah 问：Notion 现有的结构，比如 blocks、数据库，对 Agent 有用吗？

Simon 说非常有用。但有一个新挑战：要让 Agent 用起来方便。以前 Notion 的 API 是为人类开发者设计的，现在多了一个“新客户”，就是 Agent 本身。

最初这确实是个问题。Notion 的 API 用一种非常冗余的 JSON 格式来表示 blocks，对 Agent 来说又啰嗦又难处理。

他们接受了这个挑战，做了两件事：第一，为页面的读写设计了一种 Markdown 方言，看起来像标准 Markdown，但扩展了对所有 Notion block 类型的支持，模型对这种格式非常擅长。第二，数据库交互用 SQLite 语法，模型也天然擅长 SQL。

Sarah 问怎么搞清楚什么对 Agent 更好？

Simon 说两条路。一是经验主义：不断尝试，发现“哦，它不擅长这个”“哦，这个 Token 太多了，怎么压缩？”二是第一性原理：模型训练数据里有什么？它的先验知识是什么？它天然擅长什么格式？Agent 循环的高效模式是什么？

Sarah 总结：所以你们在做用户研究，只不过用户是 Agent。

Simon 笑着说：对，而且这个”用户”随时可以聊天，你有无限的访问权限，还能写脚本批量测试。

## 【10】13 天不间断

Sarah 问到 Simon 个人的 Agent 工作流。

Simon 说他正在做一个新原型，同时跑着好几个 Agent。他的日常工具是 Claude Code 或 Codex 的命令行版本，他喜欢命令行工具，简单好用。

他现在的目标就是尽可能多地同时运行 Agent，全天候不间断。每天晚上睡觉前，他会确保给 Agent 安排了足够多的任务，保证第二天早上醒来时它还没做完。

Sarah 说：那就是胜利。

> 对，那就是胜利。我的个人纪录是一个编码 Agent 连续跑了 13 天没停过，一直在按任务列表工作。
> （“My personal record is that I've had a coding agent running for, I think it was 13 days straight, without stopping and just basically working through tasks.”）

Sarah 承认自己这周也多次半夜醒来检查 Agent 是不是还在跑。Simon 说他也是，每天睡前都要最后确认一遍它还在转。

Simon 的 Personal Agent 也是他的日常工具，因为它能访问公司工作空间的所有内容。比如访谈前一天晚上，他让 Agent 帮他看 Custom Agent 发布后的用户反馈。

但他最得意的是一个邮件分拣 Agent。这个 Agent 连接了他所有的工作和个人邮箱，每天自动把不需要看的邮件归档。搭建过程很简单：创建一个 Custom Agent，给它邮件访问权限，再给它一个空白 Notion 页面当“记忆”。然后让它去看邮件，反过来“采访”Simon：提出它认为应该归档的邮件，Simon 进行纠正。Agent 用这些反馈自动生成一套规则。头几天 Simon 还在纠正它，几周后他完全取消了审批环节，Agent 就全自动运行了。

Simon 说这彻底解决了他的邮件问题。他工作主要在 Slack 上，95% 的个人邮件和工作邮件他根本不需要看。现在他打开收件箱，里面只有真正需要他处理的内容。

他还有一个反馈路由 Agent。Notion 内部有一个 Slack 频道，同事们会在里面随手发产品反馈和 bug 报告。以前这些反馈有时候有人回应，有时候就被忽略了，因为涉及太多团队。这个 Agent 的全部工作就是把反馈路由到正确的地方。它用类似的“记忆”模式，在实际运行中学习路由规则，久而久之积累了数百条规则。比如如果是移动端的 bug，它知道要路由给移动团队，然后在他们的数据库里创建任务。

Simon 说他在最初会检查 Agent 学到的规则是否合理，但一旦信任它在正常运作，就不再看了。偶尔会出问题，他再去修。

他的通用模式是：先做原型，放在审批模式下密切观察，跑几轮之后确认它在正常工作，然后完全放手。

## 【11】从“做事的工具”变成“管 Agent 的工具”

Sarah 提到 Simon 和 Ivan 最初是在 Tools for Thought 社区认识的。经过这几年的 AI 变革，Notion 的核心定位变了吗？

Simon 说变化相当大。

AI 之前，Notion 的目标是为人类创造最好的直接执行工作的工具。

现在的目标是为人类创造最好的管理 Agent 来替你工作的工具。

> 之前的目标是创造最好的工具让人直接做事。现在的目标是创造最好的工具让人管理 Agent 替你做事。这是一个很大的转变。
> （“Before AI, our goal was to create the best tool for humans to directly perform their work. And then now the goal is to create the best tool for humans to manage agents to do the work for them. That's a big shift.”）

但他接着说了一个重要的发现：Notion 之前构建的所有原语，在 Agent 时代依然非常有用。文档依然需要，Agent 很喜欢写 Markdown。数据库依然需要，结构化数据依然是刚需。如果你有 100 个后台编码 Agent 在同时工作，你不会想要 100 个聊天窗口，你会想要一个看板。 跟以前一样。

Notion 只需要增加一些新原语：Agent 是什么？它怎么跟页面和数据库交互？

Sarah 最后问：过去六个月，你个人的工作方式有什么变化？

Simon 说完全变了。他从 2025 年夏天起就不再手写代码了。

经历了几个阶段：人手动写所有代码→Tab 补全→跟 Agent 对话让它做小任务，但人还在外层循环→现在他设计一个端到端的任务，包括改动和验证，他只负责最外层的确认。如果 Agent 跑偏了，他去纠正。

他现在是 Agent 管理者，不是程序员。

## 【12】让非技术团队也能造 Agent

Sarah 问 Notion 内部是怎么帮非技术团队建立用 Agent 的直觉的。

Simon 说他们定期做内部 workshop 和 hackathon。一个月前他刚跟人力资源团队（People Team）做了一次。这个团队反而成了 Custom Agent 最积极的使用者，因为他们日常就有大量在 Slack 和 Notion 之间来回搬运信息的重复工作。

他的观察是，大家其实都很兴奋想试，只是需要一点推动帮他们起步。一旦跨过“什么是 prompt”、“Agent 怎么被触发和唤醒”这些最初的技术门槛，Agent 的交互方式其实非常符合直觉，因为你就是在跟它说话。

最大的障碍可能不是能力问题，而是信心问题：让人们相信这东西真的能用。

## Q&A

Notion 的 AI harness 多久重写一次？为什么？
大约每六个月一次。因为模型和技术进步太快，系统必须紧贴当前状态设计，做完一版就不动是常见错误。

编码 Agent 对团队规模有影响吗？
个人产出上限大幅提高，但 Notion 的团队规模没有显著缩小。小团队一直更好，这一点在 AI 前后没有本质变化。

Notion 怎么为 Agent 设计 API？
页面读写用 Markdown 方言，数据库用 SQLite。设计方法是经验主义试错加第一性原理推演：既看 Agent 实际表现，也想模型训练数据的先验。

Custom Agent 和 Personal Agent 有什么区别？
Personal Agent 跟用户有相同权限，被动响应用户请求。Custom Agent 默认无权限需要授权，可以按计划或触发器在后台自主运行。

Simon 认为 AGI 会长什么样？
AGI 就是一个编码 Agent。代码是表达确定性逻辑的最好原语，而能写代码的 Agent 可以不断自我扩展能力。

Simon 在这次对话里反复传递的核心信息有三个：第一，AI 系统必须跟着模型能力持续重写，不能做一版就停；第二，编码 Agent 不只是开发者的效率工具，它是 Agent 自我进化的关键能力；第三，生产力软件的定义正在从“人用的工具”变成“人用来管理 Agent 的工具”。

一个值得追问的问题是：Custom Agent 自主运行带来的 prompt injection 安全风险，Simon 在访谈中没有提及，但 Notion 官方文档里已经写了这是他们正在投入的领域。当你的 Agent 数量超过员工数量时，安全和控制的问题只会越来越大。

另一个悬而未决的点：如果 AGI 真的是编码 Agent，那模型厂商自己做的 Agent 跟 Notion 的 Agent 会是什么关系？“模型的瑞士”这个定位，在模型厂商也想做平台的时代，能维持多久？不过 Simon 自己给出了一个方向：管理 100 个 Agent 的人需要什么？不是 100 个聊天窗口，是一个看板。如果这个判断成立，Notion 十多年积累的协作基础设施就不是包袱，而是壁垒。

原始视频：https://www.youtube.com/watch?v=1dYThQgOyZU

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme