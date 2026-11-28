---
layout: post.njk
source: https://yage.ai/share/ai-language-choice-20260528.html
speaker: yage.ai
title: AI 写代码，选 TypeScript 还是 Python 是个错问题
date: '2026-05-28'
summary: 文章指出AI编程中语言的选择不应仅依赖训练数据或基准测试，而应关注反馈循环（agentic loop）的速度与错误信号的精确度。Go等语言凭借快速的测试缓存、结构化的接口及精确的编译错误反馈，在AI代理编程模式下表现出比Python更优的工程特性，推动了编程范式从注重语法表现力向注重AI处理效率的重估。
area: tech-engineering
category: software-development
tags:
  - agentic-coding
  - llm-feedback-loop
  - programming-languages
  - developer-efficiency
people:
  - Wes McKinney
  - Armin Ronacher
  - Steve Klabnik
companies_orgs: []
products_models:
  - Claude Code
  - Go
  - Rust
  - TypeScript
  - Python
media_books: []
draft: true
status: evergreen
---

最近 Twitter 和中文技术群里的争论出奇一致：AI
写程序到底用什么语言最好。一派人说 TypeScript，因为有类型系统约束 AI
不乱来。一派人说 Python，因为 AI 在 Python
上训练最多、写得最熟。还有人说
Rust，因为编译器严到”只要通过编译就几乎没有 bug”，等于给 AI
装了一套自动代码审查。

这些讨论有一个共同的前提：语言的优劣取决于 AI
对它的熟悉程度。谁能跑通最多 benchmark，谁能写出最少 bug，谁就赢了。

但这个前提是错的。或者说，它问错了问题。

## 训练数据很重要，但解释不了全部差距

先看数据。Python 在 GitHub 上占了约 17% 的代码推送量，比第二名 Java
高出近 5 个百分点。AI 在 Python 上的表现也确实最好。Multi-SWE-bench 这个覆盖
8 种语言、2132 个真实 issue 的基准测试里，Python 的解决率是
36-48%，TypeScript 只有 2-7%，Go 和 Rust 在 3-7%
之间。差距在十倍以上。

但这个差距不能全甩给训练数据。Java 在 GitHub 上也有 12% 的推送量，和
Python 差距不到两倍，但 AI 在 Java issue 上的解决率只有 Python
的三分之一到一半。Go 的推送量是 TypeScript 的 1.4 倍，AI
表现却差不多。Rust 只有 1.9% 的 GitHub 份额，不到 Go 的五分之一，但
benchmark 表现和 Go 基本持平。

训练数据解释了大概六到七成的方差。剩下三成多是语言本身的设计和生态系统造成的。

MultiPL-E 这个 2022
年的早期研究直接把 HumanEval 这个 Python 基准翻译成 18
种语言来测，发现了一个反直觉的结论：静态类型的存在与否，对 AI
一次性生成代码的准确率几乎没有影响。JavaScript（动态类型）的 pass@1
略高于 Python，Rust（最严格静态类型）显著低于 Python。论文原话是”static
type-checking neither helps nor hinders code generation model
performance”。

但这个结论有个重要的限定：它测的是一次性生成。生成函数体，给定函数签名和注释，能不能一次写对。而在真实开发场景里，AI
不是一次写完交卷的。它要写、要编译、要读报错、要改、要再编译、要跑测试。它是一个循环。

而这个循环的速度，才是真正拉开语言差距的地方。

## 反馈循环的速度，比一次性准确率重要

pandas 的作者 Wes McKinney 在 2026
年 2 月的一个播客里讲了自己一个很具体的转变。他以前所有项目都用
Python，因为 Python 读起来舒服、写起来快。但用了一年多的 Claude Code
之后，他发现规则变了：

> “The bottleneck has shifted: test suite execution speed and compile
> times now matter more than how enjoyable a language is to write in. I
> have been building new projects in Go because the agentic loop — prompt,
> generate, test, iterate — runs faster in compiled languages.”

agentic loop。这是他用的词，也是理解整个问题的钥匙。AI
编程的原子单位不是一次输出，而是一次”轮次”：你说要什么，AI
写一段代码，AI
自己跑编译或测试看看行不行，不行就读报错改，再来一轮。这个循环每快一秒钟，AI
在给定时间里能尝试的轮次就多一轮。尝试越多，最终结果越好。

在这种模式下，语言的某些传统优势会变成拖累。Python
的测试启动慢。import 依赖、解析代码、初始化
fixture，加起来可能好几秒。Go 的 go test ./...
在一秒内完成，而且是增量缓存的。Rust
的编译器虽然被骂”慢”，但对单个文件的类型检查实际上在毫秒级完成。TypeScript
的 tsc --noEmit 也很快。

但快只是反馈循环的一维。另一维是反馈信号的质量。

Python 的运行时错误往往离根因很远。一个 AttributeError
可能意味着某个上游函数的返回值类型不对，但错误栈指向的是调用点，不是污染源。AI
agent
要顺着调用栈往回追几层，才能找到哪里出了问题。每一步都可能猜错、改错、引入新
bug。

Rust 的编译器错误指向的是根因本身。你 borrow 了一个已经 move
的变量，编译器直接告诉你：第 47 行 move 了，第 52
行又用了，而且告诉你建议改法是什么。这对 AI agent
来说是一种精确制导的错误信号：不用猜，直接去改编译器指出的位置。

这也是为什么中国技术群里有人喊”AI 时代的编程语言就该是
Rust”。以前语言要设计得对人友好，容易学、容易读、不容易犯低级错误。但 AI
出现之后，这些都不重要了。反正不是你写代码。你只需要跟 AI 说你要什么，AI
去跟编译器对着干几轮，最终能通过编译的代码，质量基准天然比 Python
高一个量级。

但 Rust 的问题在于，编译器报错”精确”不等于”容易修”。RustAssistant
这个微软研究院在 ICSE 2025 上发表的工具，专门让 LLM 去修 Rust
编译错误，峰值准确率
74%。每四个错误里有一个修不好。在连续五轮的循环里，成功概率是 0.74
的五次方，约 22%。这还是专门优化过的工具。

## Go：意外地成了 AI
最适配的语言

Flask 的作者 Armin Ronacher 是 Rust 社区的资深成员，在 Sentry
写了很多 Rust 基础设施。但他 2025 年自己出来创业做 AI 产品时，backend
选了 Go。

他在自己的博客里写道：“I’ve
evaluated agent performance across different languages, and if you can
choose your language, I strongly recommend Go for new backend
projects.”

他的论证不靠 benchmark，靠的是在 agentic coding
中实际观察到的几个工程特性。第一，Go 的测试缓存，“surprisingly crucial
for efficient agentic loops”。AI agent
改了一个文件，只跑和这个文件相关的测试，一秒内出结果，然后进入下一轮。第二，接口是结构化的。一个类型只要实现了接口要求的全部方法就自动符合接口。这让
AI 不需要处理显式的继承和实现声明，少了很多猜错的机会。第三，Go
整个生态的反向兼容做得太好，十年没有 breaking change，意味着 AI
从训练数据里学到的写法，现在仍然正确。

这和 Ronacher 自己以前对 Go 的态度形成了反差。他过去嫌 Go
啰嗦、表达能力弱、err != nil 到处都是。但在 agentic coding
模式下，这些都不再是问题：啰嗦的部分是 AI
写的，你只是在审查。反而因为啰嗦，AI
的输出更可预测：没有隐式类型转换、没有 exception 的跨层传播、没有反射和
magic method。AI 在 Go 里能犯的错少得多。

Hacker News 上有人概括得精准：Go 是 LLM 的
RISC。指令集少，每一条的意思都清楚，AI 很难猜错。

Wes McKinney 也是同样的转向。Python 是他一手创建的 pandas
的语言，他用 Python 写了十几年。但现在新项目用 Go，理由和 Ronacher
几乎一样：不是因为 Go 更好，是因为在 agentic coding 的反馈循环里，Go
让人和 AI 都更少浪费时间在”这个修改到底对不对”的验证上。

## Rust 的正确打开方式

Rust 在 AI 编程中的表现分化得厉害。

最有说服力的正面案例来自 Steve Klabnik，Rust 社区的元老布道者、《The
Rust Programming Language》的合著者。他曾经长期对 AI
编程持怀疑态度，但在 2025 年底用 Claude Code 在 11
天里写了约 10 万行 Rust 代码，从零创造了一门叫 Rue
的实验性系统编程语言。一个最懂 Rust 的人，用 AI 来写
Rust，产出是他自己手写不可想象的。这个案例的要点不在速度，而在于这件事本身的可能性——以前没
AI 的时候，一个人花一年也未必能完成这种体量的系统编程项目。

另一类正面案例是 Joseph Glanville 做的那种量化实验。他用
interventions/session（每个 AI agent
会话需要人工介入的次数）来比较语言，结论是 Rust 排第一，“head and
shoulders above the other options”。理由是 Rust 的工具输出 token
密度极高：一次编译错误给出了精确的文件、行号、错误原因和建议修复，AI
agent 看了就能直接定位到问题。

但反面的声音同样来自资深开发者。Armin Ronacher 选了 Go 而不是
Rust。matklad（rust-analyzer 的创建者）试过让 AI 一次性生成一个完整的
AWS 集群管理工具，结论是生成的代码”lacked any character
whatsoever”。能跑，但结构糟糕，没人味。

这个分裂不是随机的。它沿着一个明确的轴分布：使用者的 Rust 经验。

审查 AI 生成的 Rust 代码，需要一个人能判断 borrow checker
报错时到底是 AI 写错了，还是 borrow checker
过于保守、应该换一种写法绕过去。前者是简单修
bug，后者需要架构调整。如果审查者不具备这种判断力，就会出现 HN 用户
antonvs 描述的”ML 团队用 AI 写 Rust”的场景：改 40
个文件来实现一个只需要改 1-2
个文件的功能，而且审查者不知道哪些改动是必需的、哪些是 AI
为了安抚编译器而过度工程的。

所以 Rust 的真实定位不是”AI 最好用的语言”，而是”最适合有经验的 Rust
开发者用 AI 加速的语言”。如果你的团队已经熟练使用 Rust，AI
能让效率跃升一个数量级。如果你的团队不具备 Rust 经验，AI 生成的 Rust
代码可能编译通过但架构糟糕，而你缺乏审查它的能力。

## 三种语言，三种循环

如果把反馈循环作为核心框架来重新看这场语言之争，三种语言分别代表了三种不同的循环结构。

Python 的循环是”写 → 跑 → 看日志 → 猜 → 改 →
再跑”。每个环节都有不确定性。报错位置不一定是 bug 位置。修好了这个 bug
可能在别处引入新 bug。但因为 Python 的训练数据量最大，AI
的一次性正确率本身是最高的，所以这个循环虽然慢，但起点高。

TypeScript 的循环是”写 → tsc 检查 → 修类型错误 →
跑”。类型检查这一步在毫秒级完成，而且错误信号精确。问题在于 TypeScript
的类型系统是 unsound
的。通过了类型检查不代表没有类型错误，更不能保证逻辑正确。这让
TypeScript 成为最矛盾的语言：给 AI
的最低限度约束刚好够用，但不够可靠，容易带来”编译通过但逻辑不对”的错误信心。

Go 的循环是”写 → go build（1-2 秒）→ go test（1-3 秒）→ 修 → 再 build
再
test”。这个循环的精妙之处在于每一步都很快，而且每一步的信号都很确定。编译通过意味着没有语法和类型错误。测试通过意味着行为符合预期。当然，前提是你有测试。Go
的测试基础设施是语言自带的、标准化的、增量缓存的，这让 AI agent 不需要花
token 去理解和配置测试工具，直接 go test 就能获得信号。

三种循环里，Go
的每一步之间没有信息损失，没有”可能对但不确定”的中间状态。这不是 Go
作为语言设计的本意，但恰好撞上了 agentic coding 的需求模式。

## 选择框架

如果一定要给一个简单可操作的建议，大致可以这么想。

写 AI/ML 相关的胶水代码，还是 Python。不是因为它最合适，而是因为
PyTorch、JAX、Hugging Face 这些库都在 Python
里，你绕不开。训练数据的绝对优势也让 AI 在 Python
上的一次性正确率最高。

写新项目的后端、CLI 工具、数据处理 pipeline，认真考虑 Go。不是因为 Go
表现更好，而是因为 agentic coding 的反馈循环在 Go 上最快最省
token。你省下的 token 和时间，可以用来让 AI
多做几轮迭代，也可以用来多写几个测试。两者都能提升最终质量。

写对内存安全、并发正确性有硬要求的底层组件，并且你的团队已经有 Rust
心智模型，选 Rust。编译器给你的保证是其他语言不具备的，而且这个保证在 AI
迭代修 bug
的时候扮演了”自动验收”的角色。通过了编译，至少一整类错误已经排除了。

至于
TypeScript，它的不可替代性不在语言特性，而在生态。前端没得选，必须用它或者编译到它的东西。但这个”没得选”恰好也是它的护城河。在
agentic coding 模式下，TypeScript 的类型系统给 AI
提供了刚好够用的约束，而浏览器和 Node.js 的生态给了 AI
最丰富的训练数据。TypeScript 不是最好的 AI
语言，但它是前端领域里唯一的选择。

## 更深一层

这场争论最有趣的地方不在于哪个语言赢了。而在于它暴露了一个正在发生的认知迁移。

以前，我们挑选编程语言的默认标准是”对人友好”：语法直观、工具链好用、社区大、不容易踩坑。Python
是这套标准的完美产物：它几乎就是为了让人感到舒服而设计的。

但 AI
出现之后，选择语言的逻辑翻转了。你在意的不再是它对你是否友好，反正也不是你在写。你在意的是它对这个每天要写几百次、改几百次、验证几百次的
AI 系统是否友好。

这意味着过去几十年 PL
社区默认的最高价值，可读性和可写性，正在被重新定价。编译速度、类型系统的信号密度、测试工具的标准化程度、生态的稳定性和反向兼容性，这些以前是二等指标的东西，在
agentic coding 时代变成了比语法甜度更重要的变量。

Go
是这场价值重估的第一受益者。它不是最漂亮的、不是最强大的、不是最聪明的。但它是最可预测的、最快的、最稳定的。这三个属性恰好是
AI agent 最需要的。Rob Pike 当年给 Go
的定位是”给那些处理不了复杂语言的人用的”。没想到十几年后，这些”人”换成了
AI，这句话反而更准确了。

这也不是说 Python 会衰落或者 Rust 会一统天下。不会的。Python 的 AI/ML
生态是二十年的积淀，一时半会没有替代品。Rust
的内存安全保证在某些领域是不可替代的。Go
的朴实无华在另一些场景是资产。不同的语言会向不同的方向演化。有些会在 AI
时代变得更流行，有些会边缘化。但驱动演化的变量已经变了。

感谢佐治亚小帅对本文选题的建议。