---
author: AI Engineer
date: '2026-11-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TvsF67C2F54
speaker: AI Engineer
tags:
  - compiler
  - ai-agents
  - software-architecture
  - performance-optimization
title: Jared 分享在 Bun 中利用 AI 智能体开发提前编译器（AOT）的经验
summary: Bun 的创建者 Jared 分享了在大型项目中利用 AI 智能体开发 AOT 编译器的过程。他强调了在大型项目中，可测试性比具体的构建方案更重要，并分享了如何通过分批次编写代码、利用长生命周期子智能体以及通过持续的引导式提问和主动测量来确保项目质量和性能的经验。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Bun
  - Cloud Code
  - Claude
  - JavaScript Core
  - WebKit
media_books: []
status: evergreen
---
[music]

## 开场与项目背景

>> 大家好。我叫 Jared，是 Bun 的创建者，目前在 Anthropic 工作。Bun 是驱动 Cloud code 的 JavaScript 运行时。最近我合并了一个几百万行代码的 PR，为 Bun 添加了一个提前编译器（ahead of time compiler）。它的基本思路是，与其在运行时承担 JIT 的开销，不如提前把所有代码都编译好。这是一个非常庞大的项目。去年夏天我用 Rust 重写了 Bun，而这个项目规模更大，这个提前编译器比那个项目还要大。我认为目前大型项目面临的挑战之一是：如何有信心地发布由智能体编写的数百万行代码。这就是我今天要讲的内容。

<details><summary>Original English</summary>

>> Hello everyone. My name is Jared. Uh I'm the creator of Bun uh and I work at Anthropic. Um uh Bun is the JavaScript runtime that powers Cloud code. And recently I merged a several million line of code PR um to add an ahead of time compiler uh to to Bun which is uh basically the idea is uh instead of paying the cost of a JIT at runtime, you can uh uh you can compile all the code ahead of time. Um and it's it's like a really big project. Um over the summer I uh rewrote Bun in Rust. Um uh and this is a project on a larger scale. This ahead of time compiler is like a larger project than that. Um and I think one of the challenges right now with large projects is like how do you actually confidently ship a like millions of lines of code written by agents. Um so that's what I'm going to talk about.

</details>

经过一些讨论后，最初的提示词大致是这样的：我们需要让 Cloud code 占用少得多的内存并且运行得更快，我们可以修改 WebKit 或者 Bun。Bun 底层使用的是 JavaScript Core，也就是 WebKit。到现在已经过去一个多月了，这个编译器经历了五次重写。你可以看到前几次都很短，然后我差点就发布了蓝色那版，但当时我觉得这构建时间太长了，编译代码耗时太久，所以我们又重写了一遍。而接下来这一版下周就要发布了。我对这类项目的思考方式是，你真正受限于如何测试代码是否能正常工作。这甚至比你具体采用什么构建方案更重要——你选择如何构建它，完全取决于你如何验证它真的能工作、没有 bug，并且值得信赖。

<details><summary>Original English</summary>

This was like the opening prompt after some discussion with it was like basically uh we need to make Cloud code use a lot less memory and uh and faster and we can modify either WebKit or Bun. Um Bun uses JavaScript Core which is WebKit um under the hood. Uh and it's been a little bit over a month. Um uh uh this is this compiler has gone through five rewrites. Um you can see the like the first couple ones like pretty short. And then I like almost shipped the blue one. Uh and then I was like, this is building way too long. Like it's taking way too long to compile the code. So we wrote it again. Uh and this next one is shipping next week. Uh this is kind of the the way I think about a project like this is like you're really constrained by how you test that the code works. Um so that's like even more important than what you're specifically like like the approach you go with for how to build it is entirely driven by how do you verify that it actually is going to like work and not be buggy and that you can trust it.

</details>

## 为什么做 AOT 编译器而不是用 Rust 重写

稍微补充一点背景，为什么会做这个项目，为什么要做提前编译器？因为在典型的基于 JavaScript 的应用中，大约一半的 CPU 时间都花在了按需编译代码上。你在很多应用中都能看到一种普遍现象：人们把从 JavaScript 起步的代码库重写成 Rust 或 Go 之类的语言，原因就在于 JIT 和单线程应用的组合。JIT 和 AOT 的区别在于，AOT 是提前编译，而 JIT 是边运行边编译。这对于像 Cloud Code 这样的产品尤其重要——比如在使用 Cloud Code 的 iOS 应用时，如果每个 Cloud Code 会话都要同时进行编译，CPU 时间开销会非常大。

<details><summary>Original English</summary>

Um and so just a little more background on like like why this particular project, why the ahead of time compiler? And it's because uh for a typical JavaScript based application roughly half of like the the CPU time is just spent compiling code on demand. Um and so a lot of the general like thing you've seen in a lot of applications where people are rewriting their code bases in in a language like Rust or sometimes Go um it's like when coming from JavaScript, it's because uh like there it's really the the combination of the JIT and that it's a single threaded application. Um so that's sort of the difference between a JIT and AOT is that uh you compile before, whereas with a JIT you compile as you go along. This is particularly important for something like Cloud Code where when using like the Cloud Code like iOS app where the CPU time is a lot uh if you're if you have to have every session of Cloud Code also compiling.

</details>

所以我们讨论过很多次：要不要用 Rust 重写 Cloud Code？因为我们 Bun 团队用 Rust 重写了 Bun，所以我们很擅长重写。但我们最终决定不这么做。原因在于，对于 Bun 来说，用 Rust 重写其实相当容易，因为它的测试是用独立于运行语言的另一种语言编写的。由于所有测试都是用 TypeScript 写的，我们可以在 Zig 版本和 Rust 版本上运行同一套测试。而对于 Cloud Code，Cloud Code 的测试是用 TypeScript 写的，这意味着我们必须把 Cloud Code 的测试套件也移植过去。一旦你开始重写测试，你就再也无法真正信任这些测试了。所以这看起来风险太大了。于是我们换了个思路：如果我们只是让 JavaScript 变得更快，这样就不用用 Rust 重写了呢？这是稍后的另一个提示词。结果是，它确实让 JavaScript 的内存占用降低了大约 4 倍，启动速度大约快了 2 倍。我们正在内部进行狗粮测试（dogfooding），很快就会对外发布。

<details><summary>Original English</summary>

Um so we talked a lot about like like should we rewrite Cloud Code in Rust? Um, because the Bun team us re- rewrote Bun in Rust, so like we're pretty good at rewrites. Um, uh, and we decided not to. Um, and the the reason why is because like for in Bun's case it's actually like pretty easy to do. Like Bun is an easy project to do a Rust rewrite because the tests were written in a language that's independent of the one it runs in. So because all the tests were written in TypeScript, um, we could run the tests on both the Zig version and the Rust version. Whereas for Cloud Code, uh, we like Cloud Code's tests are written in TypeScript. So we would have to port Cloud Code's test suite. And as soon as you're like rewriting the tests, then you can't really trust the tests anymore. Um, so that seemed like it'd be too risky. So instead, what if we just make JavaScript faster so we don't have to rewrite it in Rust? Um, this was another prompt a little bit later. Um, uh, and the result is that it actually did uh have JavaScript's memory like the memory usage uh it uses about 4x less memory. Um, uh, it starts about two times faster. Um, uh, and we we're dogfooding this internally and it'll be external soon.

</details>

## 性能表现与测试策略

接下来是一些基准测试数据，然后我也会更详细地讲讲我们具体是怎么做的。一个有趣的事情是，TypeScript 7 手动把他们的代码从 JavaScript / TypeScript 重写成了 Go，而现在通过 Bun compile 编译的单线程版本，比单线程的 TypeScript Go 移植版还要快。我们之后也会为提前编译版本的 Bun 添加多线程支持，目前还没有做，不过已经有一个 PR 了。稍微讲一下实际的提前编译器：TypeScript 的类型并不一定是正确的，所以编译器把类型当作预测，而不是完全信任它们。这类问题非常适合模型来做，因为模型非常擅长写编译器。

<details><summary>Original English</summary>

Um some more benchmarks uh and then I'll also go into more detail about how we actually did this. Um so like it's it's possible that if an interesting thing is like uh like TypeScript 7 re rewrote their code by by hand um from uh JavaScript / TypeScript to to Go and uh the single-threaded version uh with it you when compiled via Bun compile is now faster than the single-threaded TypeScript Go port. Um and we will add threads also to the ahead-of-time compiled version of Bun, but we haven't done that yet. So there is a PR. Um and so a little bit about like the actual ahead-of-time compiler um uh TypeScript is not type TypeScript types are don't necessarily need to be correct. So it treats types as predictions uh instead of like trusting them. Um and this kind of problem works really well for models because uh they're just really good at writing compilers.

</details>

这大概就是我们当时做这个决定时的思考方式。这里非常关键的一点是，在提前编译这类项目中，你可以运行海量测试，因为我们几乎不需要自己去写测试——虽然我们确实写了很多测试，但我们很大程度上可以信任在项目之前就已经存在的测试。这和用 Rust 重写 Bun 时是一样的，当时我们有 Bun 现有的测试可以跑。而现在做这个编译器，我们有 Bun 现有的测试套件，加上 WebKit 的测试，加上 test 262，再加上 Cloudflare Codes 的测试。此外我们还让 Bun 自己的测试运行器也能在 AOT 模式下运行。这个提前编译器有一个破坏性变更——或者准确地说是两个破坏性变更，这也是这些特定测试失败的主要原因。但这两个破坏性变更主要是出于安全考虑，用来防止原型污染攻击（prototype pollution attacks），同时它们最终也带来了性能收益。

<details><summary>Original English</summary>

Um so so uh uh this is sort of like more about like how you how uh like should we like how we were thinking about this decision. Um and a b a big thing here is like there's so many tests you can run when you're when it's like uh in ahead of time like like for something like this because we don't need to write any tests pretty much ourselves. Like we actually do write a lot of tests, but uh we can largely trust that the tests that predate the project work. Um and this was the same thing with the the Bun Rust rewrite where we had Bun's existing test we we could run. And now with the compiler uh we have Bun's existing test suite plus WebKit's tests plus test 262 plus Cloudflare Codes tests. Um and then we also made it so that way Bun itself the Bun's own test runner could be run in the AOT mode. Uh and like the we have one breaking change with or really it's two breaking changes with the ahead-of-time compiler and that's pretty much why these particular tests are failing. Um but the and the the two breaking changes are actually like, mostly security things, um, to prevent prototype pollution attacks, but they also end up benefiting for performance.

</details>

让这类问题非常适合智能体的原因在于，你可以同时运行一个应用的三个版本：一个用 JIT，一个用提前编译，还有一个不带类型。只要这三个版本表现一致，你就知道至少对那个特定应用来说它是正常工作的。然后你可以把这类问题拿来做大量的模糊测试（fuzz），让 Claude 不断生成代码生成器来对各种模式进行模糊测试，通过这种方式可以抓出很多 bug。

<details><summary>Original English</summary>

Um, so like what makes this particular kind of problem pretty good for agents is like uh, you run it with you can run all three versions of an application, one with a JIT, one with ahead of time compiled, and one also without the types. And as long as the three of them uh, behave the same, then you know that it works at least for that specific application. But then you can take that kind of problem and fuzz it a lot. Um, uh, and just have Claude like turn out code generators to like fuzz different patterns. Um, and you can catch a lot of bugs that way.

</details>

## 五次重写的演进历程

这是一个非常大的项目，就代码量而言，我想这是我参与过的最大项目。其中大部分是测试，也因为我们重写了五次。在做这类项目时，我的思路是分批次进行：先一次性写出大量代码，在初始批次完成后，再集中修复所有问题，确保它能编译通过、通过大量测试，并确保它真正能正常工作。在实际操作层面上，当你处于大批量编写代码的阶段时，你不想频繁运行构建，你只想运行一次构建；否则你会把所有时间都花在编译和等待构建错误上，这对任何人的时间都不是好用法。另外，一旦所有代码都写完了，对于长时间运行的任务，你会希望有很多独立的智能体同时工作。

<details><summary>Original English</summary>

Um, uh, this is a very large project. This is the biggest I think I've worked on uh, in terms of like code volume. Um, most of this is tests, um, and also because we rewrote it five times. Um, when you're like doing this kind of project, what how I think about it is like you have like batches of like okay, we need to write a lot of code at once and then after that initial batch, then it's okay, let's have let's like fix everything, make sure it compiles, make sure it passes a bunch of tests, um, and make sure it like really truly works. Um, and the actual logistics of that are like when you're in the big batch kind of project stage, then uh, you don't want to run builds. You want to run one build because otherwise you're going to spend all your time compiling and like waiting for build errors and it's going to like not be a good use of anyone's time. Uh, and then separately uh, for like longer running like once you have once you've written all the code uh, you want to uh, have it like have lots of individual agents.

</details>

这是这个项目的一点时间线。第一版不是很好，Cloud Code 占用了 1 GB 内存，非常糟糕，而且这一版尽可能多地复用了 JavaScript Core 现有的代码，所以它的上限基本上也就只能做到那样。之后不久，我们在 Bun 自身里加入了一个 TypeScript 类型检查器。这些都是当时的提示词——我们加入了 Bun Check，然后对 Claude 说“嘿 Claude，请使用 Bun Check”。在那之后，Cloud Code 的启动时间快了 2 倍，内存占用减少了大约 3 倍。但代码质量很差（slop），比如这完全不行：任何访问了名为 archive 的属性的对象，它都会假设可能用到了 Bun.archive API。我看了这个之后觉得我们绝对不能发布这个，这不行。

<details><summary>Original English</summary>

Um, this is like a little bit of the timeline um, of this project. Uh, the first one was not very good. Uh, like Cloud Code was a gigabyte um, which is terrible. Uh, uh, and like this used as much as possible from JavaScript Core's existing code. Um, so it was like basically the ceiling was what is is like at only as good as like what it could be from that. Um, uh, so then a little bit after this we added a TypeScript type checker into Bun itself. Um, these were prompts uh, uh, and so we added Bun Check and then we're like hey Claude, please use Bun Check. Um, uh, and then after that startup time got two times faster and uh, in Cloud Code and uh, started using about 3x less memory. But the code was slop. Uh, and like like this is not good. It should never it basically this meant that any object that accessed a property called archive it would then assume that the Bun.archive API was potentially used. Um, and I looked at this and I was like we cannot ship this. This is not good.

</details>

还有另一件事是，当你在做大型规划、让它写一堆设计文档时，它特别喜欢写 Markdown 文档，但这毫无意义，因为谁会去看 1,500 个 Markdown 文件呢，这太不合理了。所以到了这一版——我想这是第三版编译器，也可能是第四版，不，是第三版——为了快速把东西做出来，我同时启动了 140 个智能体，让它们同时写完所有代码，然后让 Cloud Code 跑起来。接着是第四版，这一版代码不慢了，相当不错，性能基本和之前一样。但是编译时间太慢了，因为有 JavaScript 背景的人根本不指望会有任何编译时间。像 Cloud Code 这样相当大的代码库编译要 50 秒，这意味着其他项目也要花个位数秒，人们可不想等那么久。于是我们决定再重写一次，因为在旧版本中编译只花 10 到 20 秒。另外 Claude 有个习惯，它会试着评估一切来判断值不值得做，但你很容易说服自己“你的测量结果很好”，而实际上并不好。还有一部分原因是：为什么这东西有 90 万行代码？它应该小得多才对。于是我们又重写了一次。这一次代码很好，构建时间在 20 秒以内。以后某个时候我们可能会有第六版，但第五版已经非常具备发布条件了，我也在这个项目上投入了足够的时间，是时候发布了。

<details><summary>Original English</summary>

Um, so then uh, uh, this is like yeah and then this is another thing too is like it just like to like when you're doing like a large planning like when you're trying to like have it do a bunch of design docs and stuff it just loves writing Markdown docs and it doesn't make sense because who's going to like 1,500 markdown files is just not reasonable. Uh uh So for this it was like this was like I think the third compiler version, maybe it was the fourth. No, this was the third. Um uh it to like just to kind of fast get it all out 140 agents at the same time, write all the code all at the same time, then get Cloud Code to run. Um uh and then uh this is the fourth one um and this one the code was not slow um pretty good um with like basically the same performance as before. However, the compilation time was way too slow cuz people coming from like a JavaScript background don't expect any compilation time. Um uh so 50 seconds for like Cloud Code is like a pretty large codebase, but this meant that like other projects would take like single digit seconds and people don't want to wait that long. Um so uh we're going to rewrite it again um and and uh cuz in in older versions of this compiler it was taking like 10 to 20 seconds. Uh and then Cloud does this thing where like it'll try to like size up everything to judge whether or not it's worth working on, but it's really easy to convince yourself that like your measurements are good um when they're not good. Uh uh and like part of it was also like why is this 900,000 lines of code this should be a lot like smaller. Um uh so then we did it one more time. And the code was good. And the build time was under 20 seconds. It's possible that we end up with a sixth time sometime later, but the fifth one is like very shippable and I've worked on this for enough time that it's like time to ship it.

</details>

## 智能体工作流与监控

很多时候的过程就是“嘿 Claude，试试这个想法，看看会发生什么”，然后它就会去评估这个想法。我觉得这方面还是有点问题。就像我前面说的，在评估一个改动的影响时，很容易低估或者错误地评估它，然后把自己劝退。所以我认为这一点可能还需要再深入研究。我以前的做法，尤其是在做 Bun 运行时的时候，非常依赖 Claude Code 的工作流来处理事情。而现在有了最新的模型，除了最初一次性编写所有代码的阶段之外，我主要只依赖生命周期很长的子智能体（sub agents）。子智能体这种方式效果很好，因为它们把相关代码的所有上下文都记在“脑子”里，或者说上下文窗口里，这样没那么浪费，而且它们可以持续推进。

<details><summary>Original English</summary>

A lot of this was like just like hey Claude, try this idea and then see what happens and then it would like size up the idea. And I think this is like still kind of not right. Like I think a lot of this are like things that we should try again and not let it like kind of what I said earlier about like sizing up the the impact of a change is like it's really easy to under or to like size it up incorrectly and then talk yourself out of it. So I think this probably needs to be revisited more. My old approach, particularly with like the the Bun runtime, was very much leaning on like Claude code workflows to do things. And pretty much now with the most recent models, I mostly just rely on sub agents that are like very long lived. Except for that initial part where you're like writing all the code all at once. And this with the sub agents it works pretty well because they keep all the context of the relevant code in their head or like in the context window. And that's like less wasteful. And like they can just keep going.

</details>

## 编译器工作原理与边界情况

这里稍微多讲一点编译器不同部分的工作原理。一般来说，如果我们能有把握地证明值的类型是相同的、是单态的（monomorphic），那么它就可以变成一次字段访问；否则，它每次都必须进行检查。它也有一些内联缓存（inline caching），但不多。对于这种规模的项目，有时候确实很难跟进所有事情的进展。所以我非常依赖每小时一次的更新，让它发布一个记分卡，对比我们优先关注的各项指标。通常它在 Slack 里发布时，会展示上一个版本和当前版本，这样很容易看出数字是升了还是降了。不过放在幻灯片里不太管用，因为“上一个版本”只是 JIT。

<details><summary>Original English</summary>

Here's a little more about like how the different parts of the compiler works. Generally it's like there's if we can confidently prove that the value is like the types are the same, that they're monomorphic, then it can become a field access. Otherwise, it has to check every single time. Uh and it has like some inline caching, but not like a lot. Um uh as for the project of this size, you really do need to it's kind of hard to follow sometimes like what everything what everything's happening. So uh I leaned a lot on like just having an hourly update um and where it would post a scorecard comparing a bunch of metrics that we were prioritizing. Um usually though when it was posting in Slack, it would show like a previous and this version, so that way it was easy to see if numbers went up or down. Um but it's like not helpful in a slide cuz the previous one is just the JIT.

</details>

重要的一点是，这些测试绝大多数都不是现编的，它们在项目开始之前就已经存在了，这样我们就能确定智能体不可能篡改它们。V8 Zilly 是 V8 使用的一个 JavaScript 引擎模糊测试工具，我们原本就在使用它，但我们也对它进行了扩展，使其也能测试 TypeScript 类型。同样重要的是，要检查测试是否真的能抓出问题，因为你很容易欺骗自己以为它在找 bug，而实际上它并没有找到 bug。

<details><summary>Original English</summary>

Um the the important thing is like none of these tests for the most part are things that are like made up. Um uh they're things that like pre predated the project so that way we know that like the agent couldn't have messed with it. V8 Zilly is like a JavaScript engine fuzzer that V8 uses. Um so uh and we were already using that in one, but we also extended it to have uh to like test for TypeScript types um as well. Um uh and it's also important to check that the tests actually catch things because it's really easy to fool yourself that it's finding bugs when it 's not finding bugs.

</details>

关于提前编译器的更多数据：在大多数项目中，它通常比 JIT 表现更好，但并不总是如此。你可以在 uglify JS 中看到例外，这基本上是因为如果它必须大量使用解释器——比如有很多 eval 或 new function——那它就不会更快，但大多数应用不会这么做。它几乎就像是你能想到的最接近“一行命令”就能让应用跑得更快的方法。这并非 100% 成立，因为就像你在 uglify JS 中看到的，还有其他情况也是如此，但在多数情况下是成立的。另一件事是 object prototype。这是一个罕见的边界情况，但在 JavaScript 应用中有很多叫作“原型污染”（prototype pollution）的安全漏洞，通常是通过给 object.prototype 赋值来实现的，而这个编译器禁止了这种行为。

<details><summary>Original English</summary>

Some more numbers uh on the ahead of time compiler. Um it generally for most projects outperforms the JIT. Um not always. The you can see in the uglify JS And that's basically if it has to use the interpreter a lot. So if there's a lot of like eval or a new function, um then it's not faster. Um but most applications don't do that. Uh and it's like it's like a make it like it's as close as possible as you can get to like a one liner to like make an application run faster. Um this is not 100% true cuz as you can see uglify JS and there are other cases as well. Um but it is often true. So like yeah the the other thing is object prototype. Uh this is like a a rare edge case but basically there's a lot of security vulnerabilities in JavaScript applications called like prototype pollution. And this usually works by assigning properties onto object dot prototype. Um and the compiler bans that.

</details>

## 日常协作方式与总结

那么在这样一个大型项目中，你整天实际上都在做什么呢？这些是我发得最多的消息，经常发“continue”（继续），另外我的笔记本电脑也老是没电。但更具体地说，你实际做的是一堆引导式提问，比如“我们为什么要这样做？”“我们能这样做吗？”。我最后也经常会说“你能做得更快吗？”或者“怎么花这么长时间？”，因为它有点像会自己说服自己编造出一套规则。而且它往往会低估自己能做到的事情，所以我经常对 Claude 说这类话，好让它更努力地去尝试。

<details><summary>Original English</summary>

So like for a large project like this what do you actually do all day? These are like the top messages that I sent saying continue a lot. Um uh also like my laptop kept dying. Um uh and then like but like more concretely what you actually do is like a bunch of leading questions like why are we doing this? Uh can we do this? Also I end up saying like can you do this faster or like what's taking so long? Cuz it kind of like talks itself into making up rules. Um uh and also it tends to not be uh it tends to like underestimate what it can do. Um so I often end up saying things like this to Claude to to get it to like uh try harder.

</details>

结果就是，在 JavaScript 引擎常用的主要基准测试之一 JetStream 3 中，Bun 在大多数测试项上同时超越了 JavaScript Core 的 JIT 和 Node.js（即 V8 JIT）。而且整个过程中，它一直在用 Cloud Code 来构建 Bun compile 本身，然后再用经过 Bun compile 编译出来的 Cloud Code 版本。所以我的看法是：当你用 Cloud 做一个大型项目时，可测试性极其重要，而且要确保测试真的能测出东西；如果你不积极地重新测量，情况就会变糟，因为同时发生的事情太多了，很容易迷失方向。对于这种尚未发布的大型项目来说，重写比重构更容易。如果你不表现得有野心，模型就会开始只做 0.1% 的改进，而不是 10% 的改进，所以你必须不断推它一把，告诉它“只要更努力一点，你就能做出很酷的东西”。如果你已经安装了 Bun，现在就可以运行 `Bun upgrade --canary`，然后直接运行 `Bun compile` 来体验。谢谢大家。

<details><summary>Original English</summary>

And the result is that uh JetStream three, which is one of the main benchmarks that JavaScript engines use, um uh the Bun outperforms both JavaScript Core's JIT and Node Node.js in like V8 JIT um in most of them. Uh and the whole time like it's been using Cloud Code to like build the Bun compile, like to build Bun compile itself, and then using the build of Cloud Code that was compiled with Bun compile. Um uh so sort of how I think about this is like like the testability thing is super important when you're working on a large project with Cloud uh and to make sure that the tests actually test things. Um and if you're not actively re-measuring, then it's going to like get worse cuz it's just if there's so much stuff going on, it's really easy to lose track. Um uh and like it's easier for large projects like this that haven't shipped yet to uh rewrite than it is to refactor. Um and if you don't act ambitiously, then the models will like start having like 0.1% improvements instead of like 10% improvements. So you kind of have to constantly nudge it to like hey, you can do really cool things if you try harder. Uh you can try this now if you want uh by running Bun upgrade dash dash canary if you have Bun installed. Um and then just Bun compile. Thanks everyone.

</details>