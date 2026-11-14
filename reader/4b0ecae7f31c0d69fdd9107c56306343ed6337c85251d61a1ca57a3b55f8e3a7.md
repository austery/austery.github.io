---
author: The Pragmatic Engineer
date: '2026-05-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=q9xD36NCtZ8
speaker: The Pragmatic Engineer
tags:
  - rust-programming
  - memory-safety
  - async-rust
  - ownership-model
  - system-programming
title: 为何 Rust 独树一帜：对话 Google 工程师与 Tokio 维护者 Alice Ryhl
summary: Google Android Rust 团队成员、Tokio 核心维护者 Alice Ryhl 深入解析了 Rust 的核心优势。访谈涵盖了 Rust 的所有权模型、借用检查器和内存安全等关键概念，探讨了其在 Linux 内核中的最新进展、独特的语言治理模式以及 AI 在系统编程中的应用前景。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Alice Ryhl
companies_orgs:
  - Google
  - Mozilla
  - Rust Foundation
products_models:
  - Rust
  - Tokio
  - Android
  - Linux
media_books:
  - The Rust Book
status: evergreen
---
### Rust 的核心魅力：可靠性与性能

**主持人**: 如果要你推销一下为什么值得关注或使用 **Rust**，你会怎么说？

<details>
<summary>Original English</summary>

**Host**: What would your pitch be on why it's worth checking out Rust or working with Rust?

</details>

**Alice Ryhl**: 你需要一种**可靠**的语言，一种能尽可能减少 Bug 的语言。这就是 Rust 的核心理念。

<details>
<summary>Original English</summary>

**Alice Ryhl**: You need a language that's reliable that's going to have as few bugs as possible. That's the idea of Rust.

</details>

**主持人**: Rust 正在悄然传播，成为构建可靠且高性能应用的首选语言。但它究竟有何不同？**Alice Ryhl** 是 Google Android Rust 团队的软件工程师，也是 Rust 事实上的异步运行时 **Tokio** 的核心维护者，同时还是 Rust 语言团队的顾问。在今天的对话中，我们将涵盖：为什么无论你现在使用 TypeScript 还是 C++，Rust 都值得考虑；**所有权（Ownership）**、**借用检查器（Borrow Checker）**和 **`unsafe`** 关键字是如何工作的；新手学习 Rust 时常遇到的坑；Rust 如何在没有“仁慈独裁者”的情况下进行治理；以及 **RFC** 和**版本（Additions）**机制是如何运作的。如果你想了解为什么这么多工程师说“只要能通过编译，就能正常运行”，这一集非常适合你。

<details>
<summary>Original English</summary>

**Host**: Rust is quietly spreading as a language of choice to build reliable and performant applications. But what makes it different? Alice Ryhl is a software engineer working on Google's Android Rust team, a core maintainer of Tokio, the de facto async runtime for Rust, and is a Rust language team adviser. In today's conversation, we cover the pitch on why Rust is worth to consider whether you're using TypeScript or C++ today. how concepts like ownership, the borrow checker, and the unsafe keyword work, and what are things that trip up newcomers to Rust, how the language is governed without a benevolent dictator, and how RFC's and additions work, and many more. If you want to understand what makes Rust different and why so many engineers say once it compiles, it works, this episode is for you.

</details>

### 从 Minecraft 模组到 Tokio 维护者

**主持人**: Alice，欢迎来到播客。很高兴你能来。你是如何进入软件工程领域的？

<details>
<summary>Original English</summary>

**Host**: Alice, welcome to the podcast. It's really nice to have you here. How did you get into software engineering?

</details>

**Alice Ryhl**: 实际上，这一切都始于 **Minecraft**（我的世界）。我想为 Minecraft 写自己的模组，所以我学习了 **Java**。虽然在模组制作上没走多远，但那就是起点。

<details>
<summary>Original English</summary>

**Alice Ryhl**: It actually all started with Minecraft. I wanted to write my own mod for Minecraft, so I learned Java. I didn't get very far with the Minecraft modding, but that's where it started.

</details>

**主持人**: 后来你是如何继续的？上大学了吗？

<details>
<summary>Original English</summary>

**Host**: How did you continue? Did you go to university?

</details>

**Alice Ryhl**: 那是在我上高中之前。高中毕业后，我当了一年的全职软件工程师。然后我开始读本科，修了三年，接着又读了两年的硕士。

<details>
<summary>Original English</summary>

**Alice Ryhl**: This was just before I started in high school. And then after high school, I had a year where I worked full-time as a software engineer. And then I moved on to starting my bachelor. Did that for 3 years and then I did a masters for 2 years.

</details>

**主持人**: 你是怎么去 Google 的？是大学毕业后直接去的吗？

<details>
<summary>Original English</summary>

**Host**: How did you end up at Google? Was that straight out of university?

</details>

**Alice Ryhl**: 实际上，我在读硕士的同时就开始了兼职工作，毕业后转成了全职。

<details>
<summary>Original English</summary>

**Alice Ryhl**: Actually started part-time at the same time as when I started my masters and then I switched to full-time after I finished.

</details>

**主持人**: 你是如何参与到 Rust 社区的？是在 Google 期间还是之前？

<details>
<summary>Original English</summary>

**Host**: How did you get involved with the Rust community? Was was it at Google? Was it before Google?

</details>

**Alice Ryhl**: 哦，在那之前很久。我接触 Rust 已经很长时间了。上学时，我花了很多时间在 **Rust 用户论坛**上回答问题，大概发了 10,000 个帖子。后来我也开始在一些聊天服务器上活跃，比如 **Tokio** 的 Discord 服务器。我一直在回答问题，看到常见问题时，我就会去修改文档。这就是我进入 Tokio 团队的经历，现在我是其中的维护者之一。

<details>
<summary>Original English</summary>

**Alice Ryhl**: Oh, way before. I've been doing Rust for a long time. When I was in school, I spent a lot of time on the what's called the Rust users forum. Well, I was answering questions really. I have maybe 10,000 posts on there or something. At some point, I also started being active in some chat servers, the Discord server for something called Tokyo. I kept doing that, answering questions. When I saw common questions, I would fix the documentation. That's how I got into Tokyo, which I'm now one of the maintainers of.

</details>

### 揭秘 Tokio：Rust 的异步心脏

**主持人**: 对于那些不太熟悉 Rust 和 Tokio 的人来说，Tokio 在 Rust 中扮演什么角色？为什么它很重要？

<details>
<summary>Original English</summary>

**Host**: And then for those of us not as familiar with Rust and and Tokyo, what is Tokyo inside of Rust and why is it important?

</details>

**Alice Ryhl**: **Tokio** 是 Rust 的**异步运行时**。你可以把它看作是 Rust 使用异步（async）时的“标准库”。如果你拿它和浏览器中的 **JavaScript** 对比，你可以把 Tokio 类比为浏览器本身。在 JavaScript 中，有一个事件循环（event loop）处理所有待运行的任务，然后逐个执行。特别是在使用 `await` 时，任务可以暂停，然后另一个任务在同一个线程上开始运行。Tokio 做的也是类似的事情，它有一个待运行任务队列。不同于 JavaScript 的是，Tokio 可以是**多线程**的，所以你可以有多个并行运行的队列。

<details>
<summary>Original English</summary>

**Alice Ryhl**: So Tokyo is well, it's an asynchronous runtime for Rust. You can think of it as the standard library for Rust when you're using async. I mean, if you compare with something like JavaScript in the browser, you might compare Tokyo with the browser itself. For example, in JavaScript, you have this loop, this event loop which has all the tasks that are able to run and then they get executed one after the other. And especially if you use the await stuff, then you can have tasks pause and then another task start running on the same thread. And Tokyo does something similar. It has a queue of things that are able to run and then it will run them. So unlike JavaScript, Tokyo can be multi-threaded. So you can have multiple cues running in parallel.

</details>

**主持人**: 这看起来是 Rust 语言和生态系统中非常核心的一部分。你是如何倾向于这个方向的？

<details>
<summary>Original English</summary>

**Host**: This seems like a pretty core part of of Rust as a language, as a as a ecosystem. How did you gravitate towards this?

</details>

**Alice Ryhl**: 我喜欢 Rust 的一部分原因在于这种感觉：**当你写完代码并能通过编译时，它就能正常工作**。当然，这必须打上引号，因为显然还是可能有 Bug 的，但这是很多 Rust 用户的共同感受。

<details>
<summary>Original English</summary>

**Alice Ryhl**: I think part of what I liked about Rust is this feeling that as you write the code when it compiles it works. I mean this has to be in quotes right because obviously it's possible that there are bugs but this is something a lot of people say about Rust and there's a reason people say it even though it's not necessarily literally true.

</details>

### 类型系统与“十亿美元的错误”

**主持人**: 其他语言相比之下如何？

<details>
<summary>Original English</summary>

**Host**: How do some other languages compare to begin with?

</details>

**Alice Ryhl**: 首先，要让一种语言给人这种感觉，必须有**类型系统**。即便与其他拥有类型系统的语言相比，我认为 Rust 做得更好。经典的例子是 **Java 的 `null`**。**Tony Hoare** 发明了 `null`，他称之为自己的“**十亿美元错误**”，因为这太容易导致程序崩溃了。而在 Rust 中，他们非常擅长确保调用函数时不会出现 `null` 的情况。

<details>
<summary>Original English</summary>

**Alice Ryhl**: I think to have a language that feels this way you have to have a type system. That's where it all starts. Yeah, I do think that even compared to other languages with type systems, I think Rust does a better job than many languages, even others with type systems. I mean, the the classic example is Java's null. It was Tony hair who invented the null and he called it his billiond dollar mistake because it's so easy to have I mean every time you call a function you might have a crash in your program and in Rust I think they're really good at making sure that when you call a function there's no chance that it might be null right that problem just doesn't exist so you can't have that kind of crash.

</details>

**主持人**: 所以你必须显式地说这个对象可能是 `null`？

<details>
<summary>Original English</summary>

**Host**: and so you have to explicitly say this object might be null?

</details>

**Alice Ryhl**: 是的，编译器会**强制**你在使用前检查 `null`。你不会像在 Java 中那样忘记检查。

<details>
<summary>Original English</summary>

**Alice Ryhl**: and so you have to explicitly say this object might be null and then the compiler will force you to check for null before you use it. So you can't forget like you can in Java.

</details>

### Rust 的崛起：超越 PHP 与 Go

**主持人**: 让我们谈谈 Rust 的整体情况。它诞生于 2006 年，随着时间的推移似乎变得越来越流行。你知道 Rust 现在的规模或普及程度吗？

<details>
<summary>Original English</summary>

**Host**: Can we talk about Rust as a whole? This was a language that was created in in 20 years ago in 2006 and it feels like it's become a lot more popular over time. Do you know of like the scale that Rust is at in terms of usage or popularity or or things that among the Rust Rust community numbers that are known there?

</details>

**Alice Ryhl**: 我发现一件挺有趣的事，最近我看了一下 **TIOBE 指数**，Rust 实际上已经超过了 **PHP** 和 **Go**。

<details>
<summary>Original English</summary>

**Alice Ryhl**: One thing I found kind of funny, I I checked here all the the day and uh we have actually overtaken PHP and Go on the Tyobi index.

</details>

**主持人**: 哇。我的总体感觉也是 Rust 出现在越来越多地地方。更多公司在基于 Rust 构建，比如 **Oxide** 决定全投入 Rust。Rust 正在成为构建高性能应用的热门选择，甚至越来越多地向 **Linux 内核**贡献代码。作为一个熟悉 TypeScript、Java 等语言的工程师，你会如何推销 Rust？

<details>
<summary>Original English</summary>

**Host**: Wow. Cuz the feeling I have again in general is that Rust is popping up in more and more places. More companies are building on Rust. Oxide is a good example. they decided to go all in on Rust and like there's a sense of of Rust is is becoming a popular place to build I guess high performance applications even increasingly contributing to to the kernel as an engineer who you know might know other languages from like Typescript Java etc. What would your pitch be on why it's worth checking out Rust or working with Rust?

</details>

**Alice Ryhl**: 这在很大程度上取决于你原本使用哪种语言。

<details>
<summary>Original English</summary>

**Alice Ryhl**: That depends a lot on which language you're coming from.

</details>

### 给 TypeScript 开发者的推销词：后端可靠性

**主持人**: 让我们假设是来自 **TypeScript**。

<details>
<summary>Original English</summary>

**Host**: Oh, let's come from Typescript.

</details>

**Alice Ryhl**: 对于 TypeScript，Rust 适合作为**后端语言**，用于 API 服务器。一种说法是：你不想因为 Web 服务器出问题而在半夜被叫醒。你需要一种**可靠**的语言，尽可能减少 Bug。Rust 通过 **Enum（枚举）**类型来处理类似 `null` 的问题。

<details>
<summary>Original English</summary>

**Alice Ryhl**: The pit from TypeScript would be a lot different than the pit from C++. But okay, so to begin with, I think when it comes to TypeScript, Rust fits in as the backend language. That's where I would put it. I wouldn't use it in the front end. I think it's a pretty good fit for backends, API servers. One way to put it is you don't want to be waking off at night because there are problems with your web server. You need a language that's reliable, that's going to have as few bucks as possible. I mean, obviously, it would be nice if it had zero bucks, but you know, it's going to be hard to get there, but as few bucks as possible. That's the idea of Rust. I mean, I already mentioned null, but it does a lot of stuff like that. So there's no null checking and and this is done through you know it has this enum type.

</details>

**Alice Ryhl**: 另一件非常棒的事是**错误处理**。Rust 不使用异常（Exceptions），而是将错误作为**值**返回。它使用一个 Enum，要么是结果（Result），要么是错误（Error）。通过**问号操作符（`?`）**，处理错误变得非常简单，但它是**显式**的。如果你忘了放问号，那就是编译错误。

<details>
<summary>Original English</summary>

**Alice Ryhl**: the other thing I think is quite good is uh error handling. So on one hand Russ doesn't really use exceptions. So it actually returns the error as a value. So you return a value that's either using an enum either the result or the error. And the way this is done is that there's an operator question mark which says so you write my function and then question mark at the end. And this means if this function fails return the error. So it's really easy to handle errors but it's not zero characters like like it is with exceptions right? So it's explicit on the other hand and if you forget to put the question mark that's a combination error.

</details>

**主持人**: 还有文档处理，对吧？

<details>
<summary>Original English</summary>

**Host**: Another thing I quite like is how it handles documentation.

</details>

**Alice Ryhl**: 是的。在 Rust 中，你可以使用三个斜杠（`///`）编写文档注释。最棒的是，你可以在文档中写示例代码，而 **Rust 会将所有示例转化为测试（Doc-tests）**。这意味着如果你更改了底层代码，你的示例测试就会失败。你绝不会忘记更新文档中的示例。此外，还有像 **Serde** 这样的库，通过宏自动生成代码来验证输入的 **JSON** 格式，非常高效。

<details>
<summary>Original English</summary>

**Alice Ryhl**: how it handles documentation. How does it for one when you have a comment you make it into a documentation comment by having three slashes instead of two. Now the thing is you can of course write examples in your documentation and Rust makes all examples into tests. This means that if you change the underlying code now your test fails. And so this means that you can't even you can't forget to update your examples in your documentation. ... Yeah. So there's a pretty cool library called Surya (Serde) in Rust where you you have your strct so your type you know with fields and then you can say I want to be able to pass this from for example JSON and then SA will it's a macro it will generate code which checks the JSON that it's in the same format it has all the fields you need and they have the right types and it generates native code that's specific to that particular shape of JSON. So the charge are really efficient.

</details>

**主持人**: 我最近还了解到 Rust 的 `switch` 语句（在 Rust 中叫 `match`）。如果你漏掉了一个枚举值，它也会报错。

<details>
<summary>Original English</summary>

**Host**: and there's this thing which again I I learned just very recently thanks to thanks to you as we're talking ahead of this is the switch statement right so in almost every language you have a you have a switch for an enum and you handle cases and then you might have a default or you know everything else and sometimes you forget one of them.

</details>

**Alice Ryhl**: 没错，**`match` 是穷尽性的（Exhaustive）**。如果你漏掉了一个分支，那就是编译器错误。未来当你添加新的枚举变体时，编译器会告诉你所有需要更新代码的地方。这让**重构**变得非常简单：修改代码，然后修复编译器报错，直到它不再“尖叫”为止。

<details>
<summary>Original English</summary>

**Alice Ryhl**: that's right so in rust it's not called pitch it's called match but it's the same idea you can match on your enum and then you can have a branch for each possibility at rank B and if you are missing one that's a compiler error of course you can have a catch all case if you want to but most of the time you would just list all the cases and then in the future when you add a new variant the compiler will tell you oh you need to update your code here here and here and I think this is kind of leads to another way that Rust really helps with reliability, which is that if you're refactoring, I think Rust is really good at telling you all the places you need to update. I've done this sometimes where I would refactor something. I change the code. I change the return type or whatever it is, and then I just fix the compiler errors and until the compiler stops shouting.

</details>

### 给 C++ 开发者的推销词：消灭内存安全漏洞

**主持人**: 那么对于 **C++** 开发者呢？

<details>
<summary>Original English</summary>

**Host**: What about the pitch from C++?

</details>

**Alice Ryhl**: 对于 C++，这个推销词更强。在 C++ 中，如果你犯了一个错误，通常会导致**安全漏洞**。哪怕只是简单的索引越界，也是安全隐患。

<details>
<summary>Original English</summary>

**Alice Ryhl**: So, here I actually think it's even stronger. The thing with C++ is that if you make a mistake, right, in in JavaScript, maybe you take down your server, which is already bad enough, but in C++ when you make a mistake there, now it's actually a security vulnerability most of the time. If you do something as trivial as you did an off by one in your IRA or whatever it might be, that's a security vulnerability and that this just keeps happening.

</details>

**主持人**: 让我们谈谈**内存安全（Memory Safety）**。

<details>
<summary>Original English</summary>

**Host**: Let's talk about memory safety.

</details>

**Alice Ryhl**: 内存安全的核心理念是：无论你写的代码多么愚蠢，它都不会出现某一类 Bug。比如读取数组越界、访问已销毁的对象（**Use-after-free**）等。在内核中，一个经典的例子是：如果你设法利用这种漏洞将进程结构体中的 `user ID` 写入零，那么你就是 **root 用户**了。一旦攻击者成为 root，一切就失控了。Rust 彻底消灭了这一整类 Bug。

<details>
<summary>Original English</summary>

**Alice Ryhl**: Memory safety is this idea that no matter how stupid the code you write is, it's not going to have a certain class of bugs. And this is the, you know, the kind of bug that usually leads into security vulnerabilities. You know, the kind of thing where you read past the array and you just look at random memory or you destroyed an object and then you used it afterwards. ... let's say you have some object and it has a field called user ID. And it's pretty common for code to write zero zeros to memory. But if you write a zero to the user ID, now you're root. ... Once you're rooe, you're lost.

</details>

### 垃圾回收 vs. 自动清理

**主持人**: 为什么 Rust 不像 Java 或 C# 那样使用**垃圾回收（Garbage Collector）**？

<details>
<summary>Original English</summary>

**Host**: Why is it a good or a bad thing to have a garbage collector? Java has a garbage collector. C# has a garbage collector.

</details>

**Alice Ryhl**: 垃圾回收器意味着有一小段代码会定期检查所有对象，清理不再使用的内存。而在 Rust 或 C++ 中，**变量在离开作用域（Scope）时会被自动清理**。对于嵌入式或内核等底层场景，垃圾回收带来的性能开销和不可控性是不可接受的。即使在后端，垃圾回收导致的**延迟峰值（Latency Spikes）**也可能是一个问题。

<details>
<summary>Original English</summary>

**Alice Ryhl**: So, a garbage collector says once you've done using your objects, there's going to be a little piece of code that checks all of your co your objects and says this is not used anymore and then it cleans it up. Whereas in languages like Rust or C++, the variable is cleaned up at the end of the scope when it goes out of scope. ... For embedded use cases, this might simply be not possible or unacceptable. ... Even for back end, it can be a problem because if you have a request incoming right when it checks all of your objects like you have some sort of latency spike.

</details>

### 核心概念：所有权与借用检查

**主持人**: 很多人抱怨在与**借用检查器（Borrow Checker）**“博弈”。你能解释一下**所有权模型**吗？

<details>
<summary>Original English</summary>

**Host**: One thing I've read is on forums people complaining about fighting so-called fighting the borrow checker. What can make it challenging? ... Rust's ownership model. What what is the ownership model?

</details>

**Alice Ryhl**: **所有权**就是：如果一个变量包含某个对象，那么该对象是它**独占**的。例如，如果你让 `B = A`，这被称为**移动（Move）**。之后再使用 `A` 就会报错，因为内容已经移走了。这在没有垃圾回收的情况下非常重要，因为我们要确保在 `B` 离开作用域时只清理一次内存。

<details>
<summary>Original English</summary>

**Alice Ryhl**: The ownership is just the idea that if you have a variable containing some object then the object is only there. It's kind of exclusive. So for example, if you have a variable let A equals your string or whatever and then you do let B equal to A, then this is a move. And so this means that using A afterwards is now a compiler error because its contents have been moved away. And of course this is important when we don't have a garbage collector because then when B goes out of scope, it has to clean up the string. Now if A was also valid then when they both went out of scope it would clean up the string twice which is not legal.

</details>

**Alice Ryhl**: **借用（Borrowing）** 则是创建**引用（Reference）**。借用检查器会确保在对象被清理前，所有的引用都已停止使用。它还保证：同一时间只能有一个写入者，或者任意数量的读取者，二者不可兼得。

<details>
<summary>Original English</summary>

**Alice Ryhl**: another pointer type we have in Rust is called the reference. ... creating a reference is called borrowing. ... the borrow checkout checks that the reference is like the last use of the reference is before the object goes out of scope. ... So you can only have one writer at a time or you can have any number of readers. It checks that on the scope like in a function.

</details>

### 逃生舱：`unsafe` 关键字

**主持人**: Rust 还有一个关键字叫 **`unsafe`**。它到底是做什么的？

<details>
<summary>Original English</summary>

**Host**: we talked about memory safety, but there is a keyword in in Rust called unsafe. What does this do and in what cases do people typically use?

</details>

**Alice Ryhl**: `unsafe` 基本上是一个**逃生舱**。Rust 保证如果你不使用 `unsafe`，你的代码绝不会出现那类严重的安全漏洞。但如果你使用了它，编译器会允许你执行一些无法自动证明安全的操作，比如**不检查长度就访问数组元素（`get_unchecked`）**。这通常用于追求极致性能的代码，或者用于向语言添加新特性（如构建 **Vector** 这种底层结构），亦或是调用 **C 语言库**。

<details>
<summary>Original English</summary>

**Alice Ryhl**: the what is unsafe is the escape hatch essentially. ... What Rust ensures is that if you have no use of unsafe, then no matter how stupid your code is, you will never have one of those bugs. ... generally when unsafe is used, it's to add a new feature to the language. ... As long as you design your API right, you can add new language features by using unsafe. The other classic example would be to call into a C library.

</details>

### 语言治理与 Linux 内核的未来

**主持人**: Rust 是如何治理的？它不像 Linux 有一个“仁慈独裁者”。

<details>
<summary>Original English</summary>

**Host**: Can we talk about how the language is is built? Who builds Rust? ... one interesting difference compared to some other popular languages like like Python or projects like like Linux is they have a benevolent dictator for life and Rust does not.

</details>

**Alice Ryhl**: Rust 由多个团队治理（语言团队、库团队等）。如果没有团队的共同签署，改动就不会发生。我们使用 **RFC（Request for Comments）** 流程来做重大决策。这需要编写详细的文档，解释动机、用户指南和参考级说明。

<details>
<summary>Original English</summary>

**Alice Ryhl**: today there's the rust project which has a bunch of different teams. ... Honestly, if the team doesn't sign off on it, it doesn't happen. ... The RFC request for comment is the way the ROS project makes big decisions but you know big ones is important to say. ...motivation, guide level explanation, reference level explanation.

</details>

**主持人**: Rust 在 **Linux 内核**中的地位有什么变化吗？

<details>
<summary>Original English</summary>

**Host**: Can we talk a little bit about Rust in the Linux kernel on on how that has evolved?

</details>

**Alice Ryhl**: 变化非常大。就在 2025 年 12 月的峰会上，我们达成一致：**Rust 在 Linux 内核中不再是实验性的（Experimental）**。这证明了它确实行得通，现在它在稳定性上有了更高的地位。

<details>
<summary>Original English</summary>

**Alice Ryhl**: The the the most recent Linux plumbers from December 2025 was there. The big news were that at the Linux kernel maintainer summit, we agreed that Rust is no longer experimental in the kernel. That was really big for us compared to the previous year.

</details>

### AI 在系统编程中的角色

**主持人**: 你在日常工作中会使用 **AI 工具**吗？

<details>
<summary>Original English</summary>

**Host**: Do you use any of the AI tools for your day-to-day work building Tokyo, uh contribute contributing to Rust projects?

</details>

**Alice Ryhl**: 我一直在尝试使用。我挺喜欢 **Gemini 的命令行界面**，非常简洁。Rust 实际上是 AI 代理的一个很好的候选语言，因为编译器能提供极强的反馈，帮助 AI 修正错误。我曾用 AI 帮我编写过一些补丁和基准测试（Benchmark），它能非常聪明地修改现有代码并生成分析脚本，节省了不少繁琐的工作。

<details>
<summary>Original English</summary>

**Alice Ryhl**: So, I have been trying to use them. Honestly, I'm still learning how to use these tools, but I have used them. I I quite like the Gemini command line interface. ... Rust could be a pretty promising candidate for to use for agents because they can get more feedback and it's just hard it's harder to to ship certain type of bugs. ... I have actually written a few patches with AI myself. ... saved me time if nothing else.

</details>

### 学习资源与建议

**主持人**: 对于想要学习 Rust 的资深工程师，你有什么建议？

<details>
<summary>Original English</summary>

**Host**: for a senior engineer who would like to learn Rust or you know just build with it what would your suggestion to be to get started.

</details>

**Alice Ryhl**: 首先是官方的 **《Rust 权威指南》（The Rust Book）**，它非常出色。其次，最好的学习方法是做一个实际的项目，比如 Web 服务器。此外，还有 **rustlings** 这样的互动练习。对于进阶开发者，我推荐 **Jon Gjengset** 的书，适合想要进一步深挖的读者。

<details>
<summary>Original English</summary>

**Alice Ryhl**: the Rust book which is so it's on the official Rust website is actually really good. ... honestly the way you learn a language is you have you have a project. You you implement some sort of project with it. I mean maybe some sort of web server or something. ... John Ganget (Jon Gjengset) has another book that I think is really good and this book is kind of aimed at the intermediate Rust developer. ... there's this thing called rustlings and the idea is that they give you some unfinished rust code and your task is to finish it.

</details>

**主持人**: 非常感谢你，Alice。这对话非常有启发性，我学到了很多。

<details>
<summary>Original English</summary>

**Host**: Awesome, Alice. Thank you. Thank you. Thank you so much for this. This was really interesting and I've learned a bunch.

</details>

**Alice Ryhl**: 谢谢邀请我。希望大家像我一样喜欢探讨 Rust 的细节。

<details>
<summary>Original English</summary>

**Alice Ryhl**: Thank you for having me on. I hope you enjoyed getting into the details about Russ as much as I did.

</details>