---
author: Beyond Coding
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=W1uG25of2t0
speaker: Beyond Coding
tags:
  - code-review
  - ai-assisted-development
  - guardrail
  - specification-driven-development
  - software-testing
title: 【双语访谈】如何破局 AI 时代的代码审查瓶颈：从智能守护到规格说明驱动开发
summary: 本期访谈深入探讨了 AI 自动生成代码带来的代码审查瓶颈问题。随着代码生成速度提升数十倍，审查阶段成为研发管线的新瓶颈。嘉宾分享了通过构建包含静态检查（如 Semgrep）、行为测试（TDD/ATDD）和架构约束的智能环境（Guardrails），让 AI 代理在无人工干预下实现自我纠错与迭代，从而将审查重心从具体实现提升至架构与规格说明层面的前沿实践。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - Amazon
  - OpenAI
products_models:
  - Claude Code
  - GitHub Copilot
  - Semgrep
media_books: []
status: evergreen
---
### 破局代码审查瓶颈

**嘉宾**: 你该如何扩展和规模化代码审查流程？因为现在这已经成为了阻碍资深工程师的瓶颈，让他们精疲力竭。其中一个答案是：根本不要进行任何形式的代码审查。

<details>
<summary>Original English</summary>

**[Guest]**: How do you scale the reviewing process? Because now that is blocking your senior engineers, it burns them out. One answer is: don't do any code reviews at all.

</details>

**主持人**: 欢迎收听本期节目。我们在这里讨论了目前软件工程中最大的瓶颈——代码审查。以及你对规格说明驱动开发（Specification-driven Development）有什么看法。在这些守护规则（Guardrails）中，哪些给你们带来了最大的价值？我们使用的工具套件（例如使用 Claude Code 或是基于 Codex 的工具）究竟有没有关系？

<details>
<summary>Original English</summary>

**[Host]**: This is Flywheel AI, engineering excellence, and we discussed the biggest bottleneck in software engineering right now: code reviews. What do you think of specification-driven development? Which of these guardrails gave you the most value? Does it matter which harness I use: Claude Code or Codex?

</details>

**嘉宾**: 这关系非常重大。从员工正在做的事情中我们可以极其明显地看到，如果只是塞给人们一把“手枪”（也就是 AI），然后对他们说：“拿去用吧，但注意别把互联网给炸了。”那是远远不够的。

<details>
<summary>Original English</summary>

**[Guest]**: It matters immensely. You see what employees are doing is that they give people a handgun, which is AI, and then say, "don't blow up the internet, but use it."

</details>

**主持人**: 这正是当下的顶尖工程师们正在解决代码审查瓶颈的方法。目前，随着我们编写和生成的代码越来越多，在构建阶段，代码审查确实演变成了一个严峻的瓶颈。我刚从 **Google I/O** 大会回来，那是上周的事情，等这期节目上线时可能就是几周前了。即便在谷歌这样人才济济的公司，他们也承认代码审查目前是一个瓶颈，而且我们还没有找到很好的解决办法。

<details>
<summary>Original English</summary>

**[Host]**: This is how the best engineers are solving the code review bottleneck right now. Here's the full episode: as we generate more code, this is already in the build phase where code review becomes a bottleneck. I've just come back from Google I/O. That was last week, and when the episode comes out, it will be a couple of weeks ago. And even there, Google and their people acknowledge that code reviews are a bottleneck, and we don't know how to solve it.

</details>

**嘉宾**: 是的，谷歌是一个非常有趣的案例。因为在 2025 年，他们就已经报告称有 50% 的代码是靠 AI 生成的，接着他们还在推动这个比例达到 75%。我总是喜欢观察这些行业巨头都在做些什么。因为一方面，你会看到所有这些令人疯狂的数据，比如效率的显著提升。我们会听到类似“我们用 AI 自动化了我们整个部署流程并对其进行了扩展”这样的案例，但我们极少能够真正看到他们具体是怎么实现的，对吧？他们通报了所有这些效率提升的成果，但你该如何把这些成果转化为你自己的日常工作呢？这部分内容对大公司来说往往是缺失的。

如果你仔细研究一下他们发布的内容和撰写的文章，你大致可以看到，他们采用了一种优先处理审查的机制，这更像是迫在眉睫的需求。因为他们已经意识到，现在生成代码的成本变得非常低廉，瓶颈正在转移到其他地方。现在有些人（这可能会是另一个话题）会争辩说，编写代码从来都不是软件工程的瓶颈，这取决于你如何看待软件工程。但事实情况是，AI 能够源源不断地生成看似聪明的代码，这导致了审查环节以及资深工程师所面临的压力剧增。

我认为大公司目前正在应对这一挑战的手段是制定审查政策。例如在 **Amazon**，此前曾发生过几起因为 AI 生成的代码而导致重大收入损失的线上故障。随后他们出台了相关政策，规定某些关键的代码部分或系统组件在合并或部署之前，必须由资深工程师进行人工审查。因此，他们已经意识到，在某些情况下，AI 生成的代码必须比其他情况受到更严格的审视。

所以你可以看到这一点。但与此同时，你也会看到其他公司说：“没关系，我们把整个拉取请求（PR）的审查过程都自动化了，采用这样的方式。”我会把这看作是横向和纵向两种扩展工程能力的维度。横向的维度是指对现有流程进行自动化，比如对目前的拉取请求进行审查。你可以规定，对于创建的任何 PR，都会自动使用像 Copilot 这样的工具进行审查。这也是很多公司正在做的。但是，他们并没有真正探讨这样做究竟能如何提高代码的质量，对吧？他们只是在对现有的人力流程进行自动化改造。

而在纵向维度上，如果你有一个项目和一个小规模的专业团队，你会让他们构建自己的专属工具，以确保产品能够按照他们的预期方向进行开发和交付。因此，他们会更深入地为自己的编码代理（AI Agents）以及交付软件的工具链定制专属的构建环境。他们并没有一套能直接套用到自己产品上的万能蓝图，而是需要去不断精雕细琢。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, Google was an interesting case because in 2025, they already reported that 50 percent of the code was AI generated, and then they are pushing for 75 percent. I always like to look at the big players to see what they do, because on one side, you see all of these crazy numbers, like efficiency gains. "We automated our entire deployment there with the AI and expanded it," for example, but very seldom do you actually see how they do that, right? So they report all of these gains. But then how do you translate that to your own work? That part is often missing for the big companies.

I think if you look a little bit about what they've published and what they write, you can kind of see that they have like an approach that prioritizes reviewing, more like it becomes most urgent because they've identified that now that you can generate code very cheaply, the bottleneck is moving somewhere else. Now some people, and this is another topic, but some people would argue that writing code was never the bottleneck, depends on how you see software engineering. But the truth of the matter is you generate a lot of smart code. So now you have more pressure on your reviewing, on your senior engineers. And I think what the big companies are doing right now is they are combating that with policies on reviews. In Amazon, for example, there have been some instances where there were outrageous revenue loss due to AI generated code, and then they put policies in place where they require some parts of the code or some parts of the systems to be reviewed by senior engineers before anything gets merged or deployed. So they are identifying that, you know, for some cases, AI generated code has to be scrutinized much stronger than in other cases.

So you can see that. And at the same time, you see other companies that say, "okay, we automate our entire PR review process," applying like this. How would you say... I like to think about it as a little bit like there's a horizontal way of scaling engineering and a vertical one. The horizontal one is where you automate processes you currently have, like PR review. You can say any PR that is created is automatically reviewed with Copilot, for example. And that's what a lot of companies do. But then they don't really talk about how that improves the quality, right? So they are automating the human pipeline that we have. What's in the vertical axis? The vertical axis is if you have a project and a small specialized team, you let them build their own tooling to make sure that the product ships and it's developed in the way that they intend to. So they are more involved in building custom-built environments for their coding agents and for the tools to deliver the software. Like, they don't have a blueprint that applies to their product automatically. They refine it. Yeah.

</details>

---

### 智能反馈环境建设

**主持人**: 这就是我所看到的各种能力的叠加。我们在这一端有模型本身，而在模型的周围有专门围绕它构建的代理（Agent）框架。而你刚才提到的是这些代理框架所运行的“环境”。那么，我们应该如何看待它们呢？

<details>
<summary>Original English</summary>

**[Host]**: And this is what I see as stacking of capabilities. So right, we have the model on one hand, then the agent kind of harnessed around a model specifically, and you're talking about an environment in which this agent harness operates. Well, how should we view them?

</details>

**嘉宾**: 也许我们应该退一步来看。当我们审视软件工程时，我认为到了今天，这已经是一个非常成熟的流程了。如果在 AI 时代到来之前，大家都知道软件开发生命周期（SDLC）是怎样的。其中的一部分审查工作是由人类完成的，而且这种方式是行之有效的，因为当时交付代码的速度并没有快到让人来不及审查的程度。但现在，随着 AI 的出现，情况已经彻底改变了。

所以现在的关键问题变成了：我们该如何扩展和规模化代码审查流程？因为现在这已经成为了阻碍资深工程师的瓶颈，让他们精疲力竭。有相关的研究表明，团队的认知负荷正在不断累积，人们甚至开始不再理解他们自己的代码库，因为他们根本没有时间去仔细看每一行代码，或者他们不想去审查 AI 生成的那些边缘情况代码。

因此，问题在于你该如何缓解这一现象？其中一个答案是：根本不要进行任何形式的代码审查。好，但接下来的问题是，你该怎么做到这一点？

我认为一种可行的方法是：精细地设计代理（Agents）运行的反馈环境。这样一来，你就不需要时刻让一个“人在回路中”（Human in the loop）去给代理反馈那些常见的错误。我们可以从非常简单的事情开始做起。

比如我称之为自动化的代码格式化或安全性检查。很多团队其实早就已经有了这些，比如集成了像 **SonarQube** 这样的工具来提供反馈，然后由人类开发者接收这些反馈并去修复代码。而现在有了这些系统反馈，代理完全可以自动去完成修复。所以，如果你能把关于“它们做错了什么”的反馈直接提供给代理，并且让这个反馈尽可能贴近代理实际生成代码的地方（也就是说，在开发者的本地电脑上，而不是非要等到代码提交到 GitHub 甚至发起 PR 之后），那么你就会突然进入一个全新的境地。在这里，你是在给代理设计反馈机制，从而帮助代理在不需要人类干预的情况下独立运行很长时间。这就是我所说的构建这类环境的含义。

而且我认为开始做这件事其实很容易。其中的很多操作感觉就像是我们以前一直在做的事情，但区别在于，现在你是把这些反馈喂给 AI 代理，而不是再由人类去阅读并处理了，对吧？现在的一些模型在Pinpoint（精准指出）它们的错误后，其自我纠错能力是令人惊讶的。只要环境能给它们提供这样的反馈，它们自己就能把代码改对。

<details>
<summary>Original English</summary>

**[Guest]**: But maybe we should just go back one step. So we look at software engineering. I think it's a very established process by now, like if we think before the era of AI. Yeah, software development lifecycle, everybody knows it. And part of the reviews were done by humans, and it would work because code wasn't delivered faster than you could review it. That has changed now with AI. And so the question now becomes: well, how do we scale the reviewing process, right? Because now that is blocking your senior engineers, it burns them out. There are studies about that, where you know, cognitive debt is growing, people don't understand their own codebase because they just don't have the time to look at everything, or they don't want to look at the agent-generated code, etc.

And so the question is: how do you mitigate that? And one answer is: don't do any code reviews at all. Okay. But then the next question is: how do you do that? So I think one way to do it is to engineer the environment in which the agents operate with intention, so that you don't have to be the human in the loop to give the agent feedback on common things. And it starts with very simple things. So like I've just... let's call it automatic code formatting, or a security check. Lots of teams have integrated tools like SonarQube or something that gives you feedback, that then a human would take and fix the code with. And with the feedback from those systems, agents can do that automatically. So if you provide agents feedback on what they're doing wrong, and hopefully as close as possible to where the agent actually generates the code (which means on the developer's laptop, not necessarily in GitHub after your major commit or your PR), then you're suddenly in this world where you're trying to engineer feedback to the agents in a way that helps the agents to run for a long time without human intervention. So that's what I mean by building these types of environments. Yeah.

And I think it's very easy to get started with it. A lot of it will feel like, "but we've been doing this before," but now you're giving the agent that feedback, you're not taking it as a human anymore, right? And some of the models are surprisingly good at self-correcting themselves once you pinpoint to them what they did wrong and let the environment give that feedback. Yeah.

</details>

---

### 提效工具链的抉择

**主持人**: 在这个公式里，底层运行的代理框架（Harness）有关系吗？我究竟用的是 GitHub Copilot、Claude Code 还是 Codex，这会有影响吗？

<details>
<summary>Original English</summary>

**[Host]**: Does the harness in this equation... does it matter which harness I use: GitHub Copilot, Claude Code, Codex?

</details>

**嘉宾**: 是的，绝对有影响。在我的经验中，代理框架甚至比底层的模型更为重要。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, absolutely. What in my experience, the harness matters more than the model.

</details>

**主持人**: 真的吗？

<details>
<summary>Original English</summary>

**[Host]**: Okay.

</details>

**嘉宾**: 我的意思是，代理框架负责提供工具，提供某种形式的提示词注入，提供记忆层以及所有类似的基础支持，然后将这些信息提交给大语言模型（LLM）来生成响应。例如对于 LLM 来说，一旦发起了工具调用（Tool Call），代理框架就必须具备为 LLM 执行该工具调用的能力。这关系极大。

我曾在我的一个项目中做过一个实验，尝试根据规格说明和测试去实现一个工具。我当时有一整套完整的规格说明，也就是规格说明驱动开发（Specification-driven Development）。这也是现在很多人喜欢做的事情，他们认为如果把产品规格写得足够精细，就能完全按照规格来实现它。不幸的是，这并不完全现实。但我做了一次尝试，结果失败了。

接着我换了个思路：“如果我采用验收测试驱动开发（ATDD）的想法，在最开始就生成所有的行为测试（Behavior Tests），然后以此作为给代理的反馈，让它顺着我的规格去实现会怎么样？”在两组不同的代理框架中，我使用的都是当时最顶尖的模型。结果是，取决于我所使用的底层代理框架，这个任务在一个框架里成功了，在另一个框架里却失败了。

<details>
<summary>Original English</summary>

**[Guest]**: I mean, the harness is what provides the tools, what provides some type of prompting, provides the memory layer and all of these things, that then get submitted to the LLM to generate responses. For example, with the LLM, once a tool call is made, right? The harness provides the capability to execute the tool call for the LLM. It matters immensely. I made an experiment in one of my projects where I tried to implement a tool based on specifications and tests. So I had a full suite of specifications like specification-driven development, like many people like to do nowadays. Say like the idea is that if you specify your product exactly enough, you will be able to implement it exactly according to specifications, which is unfortunately not true. But an attempt that I made, and that failed. And then I thought, "okay, what if I use the ATDD idea and just generate all of the behavior tests up front, and then let that be the feedback to the agent who tries to follow my specifications?" And depending on the harness that I used, it worked or didn't work, even though I was using the top frontier model in both harnesses. Okay.

</details>

**主持人**: 那么哪个框架给你带来了最好的效果呢？

<details>
<summary>Original English</summary>

**[Host]**: Which harness gave you the best results?

</details>

**嘉宾**: 这个排位一直在变。在那个时候，表现最好的是 **Claude Code**。而现在，我会说在具体的代码实现工作上，优势已经转移到了 Codex 这边。但这类技术就像是移动的靶子，这也是你不能停止尝试和实验的原因之一。

软件工程师往往有一种倾向，试图把所有事情都系统化并固定为一套标准流程。比如觉得：“好了，我了解这里的规则了。”但我认为这在当前是行不通的，因为技术的发展速度依然太快了。也许我不该把话说得太绝对。它在某些层面上确实管用，但如果你在公司政策中强制规定“我们必须只使用 Claude Code”，谁知道下一个版本发布时会发生什么呢？到时候它的表现可能会完全不同，因为不同的模型有不同的怪癖和不同的“性格”。比如有些模型非常擅长遵循极其具体的指令，而另一些模型则非常擅长在人类没有提供足够上下文时去“填补空白”。所以你在选择使用哪种模型和框架时需要非常小心。

<details>
<summary>Original English</summary>

**[Guest]**: Well, that keeps changing all the time. At that time, it was Claude Code. Now I would have said... I would say that it shifted to Codex for implementation work. But that's one of those things that's like a moving target, which is also one of the reasons why you can't really stop experimenting. There is this tendency for software engineers to try to systematize things and make it a process. And "okay, this is those, I know the rules." I don't think that works. Things are still moving too quickly. Okay, maybe I should walk that back a little bit. It works at some level. But if you define in your policy "we must only use Claude Code," who knows what will happen when the next release comes out? Yeah, it might behave completely differently because the models have different quirks and different personalities. Some are very good at instruction following, others are very good at filling in the gaps if you don't provide enough context as a human. So you need to be careful which model you use as well. Yeah.

</details>

---

### 规格说明驱动开发

**主持人**: 我想具体探讨一下你对代理框架的建议。但在此之前，顺着你刚才关于规格说明驱动开发以及通过这种方式解决代码审查瓶颈的思路，你提到在模型以这种方式遵循指令时，测试驱动开发（TDD）的方法要比单纯的规格说明驱动开发效果更好？

<details>
<summary>Original English</summary>

**[Host]**: I want to zoom in on what you recommend for harnesses. But before we do, following your train of thought of specification-driven development and solving the code review process in that way, you mentioned the TDD approach worked better than the specification-driven development approach with a model following instructions in that way?

</details>

**嘉宾**: 嗯，规格说明驱动是我第一次尝试，结果并不理想。这属于典型的“我写了完美的提示词，但模型做出来的东西却完全偏离了我的意图”。但是，当你在此基础上加入测试反馈，直接指出模型在哪里偏离了轨道时，在我的那个特定案例中，它就能够顺利完成任务了。而且我会说，这种经验在一定程度上是可以复用到其他项目中的。不过这确实非常依赖于项目的具体情况，这又让我们回到了那个论点：你必须愿意去亲自实验，看看什么才是行之有效的。

<details>
<summary>Original English</summary>

**[Guest]**: Well, I would say, specification-driven was my first attempt, yeah. And that didn't go well. It was a typical, "okay, I create the perfect prompt, and then the model does something different that I didn't intend." But when you give those feedbacks, in addition to telling the model where it went off track, that worked for me in that particular instance. And I would say, you know, those might be transferable to other projects, but it really depends on the project. Which again, brings us back to the need to be willing to experiment with what works.

</details>

**主持人**: 明白。而且我理解这种反馈是以自动化的方式运行的，对吧？你拥有规格说明，然后执行代码。接着反馈并不是由你人工去告诉它做错了什么，那这种反馈具体是以什么形式呈现的呢？

<details>
<summary>Original English</summary>

**[Host]**: Yeah. And this feedback, just so I understand, this is in an automated way, right? So you have specs, then you have execution, and the feedback is not you telling what it did wrong. But what does that feedback look like?

</details>

**嘉宾**: 没错。当你在使用一些命令行界面（CLI）工具时，你有能力去利用我们所说的“停止钩子”（Stop Hook）。也就是说，当代理完成它的阶段性工作时，代理框架会触发一个事件，即 `Stop Hook`。你可以将其与你正在运行的 Shell 脚本关联起来。通过这种方式，你可以自动化运行你的测试套件或安全守卫。

我喜欢把它们称为“守卫”（Guardrails）。你需要去设计这些守卫，让它们能够输出自然语言文本，比如：“这是被禁止的，请用另外的方式来实现它。”你可以根据你作为人类会写出的提示词来构建这些反馈。

一旦触发了这个事件，就会促使大语言模型继续针对发现的问题进行修改。你也可以将这些反馈与类似 Codex 机制里的 `Rough Loops` 结合起来。我们还拥有 `Goal` 命令，这真的很有帮助。它们会不断循环运行，直到彻底解决问题。

<details>
<summary>Original English</summary>

**[Guest]**: Exactly. So when you're using things like CLI tools, you have the ability to feed back what is called, for example, a stop hook. So when the agent is done with its work, yeah, the harness triggers an event, which is a stop hook. And you can wire that up to a shell script that you run, for example. So you can automate running your test suite or your guardrails. I like to call them guardrails. And then you need to engineer your guardrails so they actually output like natural language text: "This is forbidden, do it in this and that way." So you base the feedback on the prompt that you would write as a human. So then you trigger that, and then that triggers the LLM to continue working on the thing. And you can pair these feedbacks that you give with things like rough loops, you know, Codex mechanism. And we have the `Goal` command, which really helps, so they will just keep running for longer until they've fixed the issue.

</details>

**主持人**: 是的，`Rough Loops` 特别允许你在循环中反复运行你想达成的任何目标，让它不断迭代。这种反馈机制会作为输入提供给它，从而纠正并引导它达成目标。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, rough loops specifically allow you to run whatever you want to do in a loop, right? So it goes over and over. And this feedback mechanism would then be the input, to get it right and to correct it, go to something similar.

</details>

**嘉宾**: 没错，背后的核心思想是完全一致的。

<details>
<summary>Original English</summary>

**[Guest]**: The idea is the same. The idea is the same.

</details>

**主持人**: 明白了。那么在你建立的这些守卫规则中，哪些带给你的价值最大？你刚才已经提到了代码静态检查（Linting）和一些安全控制，你还有更多具体的例子吗？

<details>
<summary>Original English</summary>

**[Host]**: Yeah. And which of these guardrails that you've put in place gave you the most value? You mentioned linting already and some security controls. Do you have more examples?

</details>

**嘉宾**: 有的。我以前其实并不了解，但从那以后我成了 **Semgrep**（语义 Grep）的忠实拥趸。因为它可以让你为那些能在代码中捕捉到的特定模式编写规则。

我经常举的一个例子是：在 Python 代码中，我不希望在任何方法定义中使用可变默认值。大家都知道，在 Python 的方法参数中你可以设置默认值。但在我的经验中，这是后期进行代码审查和调试时最让人头疼的 Bug 来源之一。因此，我直接定制了一条检测这类代码模式的 Semgrep 规则来阻止它。这条规则会触发错误提示：“你不能以这种方式编写代码，这违反了团队的代码规范。”

Semgrep 真的非常灵活。每当我审查 AI 编写的代码（而不是我自己去逐行阅读）时，遇到类似问题我就会追问它：“你为什么要用这种方式写？这毫无道理。”这些瞬间会立刻触发我，让我意识到：“好吧，让我们为这种特定模式再加一条守卫规则。”

所以随着时间的推移，你实际上是在不断塑造你的开发环境，让它一步步变得更加严密，并高度契合你作为人类开发者的偏好，或者说符合你心目中优秀代码该有的样子。这不仅仅是关于代码的“美感”或“品味”，更是因为你希望确保 AI 生成的代码对于人类来说易于阅读和维护。即使作为人类你不想去读它，但对于 AI 来说，代码本身就是上下文。这就是为什么代码质量在今天依然至关重要的原因。

如果你不把这一点做好，AI 很快就会被自己写出来的糟糕代码给绕进去，陷入混乱。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, so I didn't know before, but I've since become a great fan of semantic grep (Semgrep). Because it allows you to put rules for things that it could catch in code, for example, certain types of code constructs. The example that I always give is: I don't want any default values in any of my methods in Python, for example. You know, you can set default values for parameters in Python methods. And this, in my experience, is one of the greatest sources of frustration when you have to review and debug the code later. So I just prevent that by putting a rule that detects these code patterns. And that then triggers an error: "You must not write it in that way, it's against policy." So semantic grep is really flexible. And whenever I interrogate the AI about the code that it wrote, instead of reviewing the code myself, some of these issues come up: "Why did you do it that way? It doesn't make any sense." They immediately trigger me: "Okay, let's add another guardrail rule for this particular type of pattern." So what then happens over time is you're shaping your environment, you're iterating towards it to be tighter and tighter, to be aligned with your preferences as a human, or how you think code should look like. And part of that is not only taste, but also you want to enforce that the AI generates code that is easy to read, not only for humans, even if you don't want to read it as a human, but also for AI. Code is context. That's why code quality matters. Yes, and if you don't watch it, the AI is going to confuse itself by the code.

</details>

**主持人**: 是的，代码库的可持续性向来要求它保持简单且易于修改。即便有了 AI 代理，这个视角也从未改变。尽管我们现在允许自己去生成更多的代码，但堆积在外面的代码如果不够简单，可能就不会那么容易修改，构建在上面的系统也会变得非常脆弱。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, the sustainability of codebases has always been that it needs to be simple and easy to change. And though that perspective hasn't changed with agents, we allow ourselves to generate more code, and the code that is out there might not be simple and might not be as easy to change. The building on top of that might be quite brittle.

</details>

**嘉宾**: 确实。而且作为人类，我们以前常常会给自己找借口，比如：“只要这个模块化做得好，其中一个模块乱一点也没关系，只要它做好了隔离就行。”

<details>
<summary>Original English</summary>

**[Guest]**: Yes. And well, as humans, we also allow ourselves this little exception or say, "as long as this modularity is there, it doesn't matter if one of the modules is messy or something, as long as it is isolated, right?"

</details>

**主持人**: 隐藏在抽象之后。

<details>
<summary>Original English</summary>

**[Host]**: Behind abstractions. Yes.

</details>

**嘉宾**: 是的。这也是我在 AI 身上发现的规律。如果你能保持系统的模块化，那会对你有极大的帮助。比如在模块之间定义非常清晰的边界，拥有绝对不允许随意更改的、定义明确的接口。

我认为这把我们带到了另一类守卫规则前，也就是架构约束（Architectural Constraints）。现在很多编程语言都拥有架构单元测试（Architectural Unit Tests）工具。这些测试运行速度极快，它们只去分析代码库中不同模块之间存在什么样的依赖关系。它们能迅速给出结果。你可以规定，比如：“禁止 UI 层直接访问数据层，必须强制要求它通过业务逻辑层。”

因为 AI 也倾向于在模块之间建立一些人类绝不会做的非常诡异的交叉连接。如果你让 AI 去设计你的系统并画出系统图，你会看到各种让你抓狂的奇葩设计。因此，你需要把它们规范到架构单元测试中。我将其视为另一种形式的守卫。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah. And there's also something that I found with AI. If you keep things modular, that helps a lot. If you have very clear boundaries between modules, if you have well-defined interfaces that are not allowed to change, for example. And I would say that brings us to another type of guardrail, which is architectural constraints. So a lot of languages, they have architectural unit tests, and those unit tests execute extremely quickly. They only look at, you know, what dependencies exist between different modules of your codebase, so they can analyze it very quickly. And you can say, "okay, prevent, let's say, the UI from accessing the database directly, enforce that it always has to go through the business logic layer," or something like that. Because the AI also tends to make these weird interconnections between modules that a human would never do. Or if you just let the AI design your system and then draw your plot of your system diagram, you will see the weird things that emerge, and you encode them into additional architecture unit tests. Yeah, which I would count as another form of guardrail.

</details>

---

### 认知负荷与防范

**主持人**: 那么有什么事情是你会归类为“依然属于人类的职责，无法融入自动化守卫”的呢？

<details>
<summary>Original English</summary>

**[Host]**: Is there anything that you would say: "well, this is then still kind of part of the human responsibility that would not fit in automated guardrails?"

</details>

**嘉宾**: 当然有。如果我们回看传统的软件工程方法，它向来围绕着：“我们想构建什么？”“我们该如何构建它？”以及“我们该如何保持它的可维护性？”保持代码库的干净和简单意味着我们可以长期保持高效。

而我们以前是如何通过架构来实现这一点的呢？我们会在最开始定义好架构，然后开始深入到各个模块中去实现它们。我认为这套流程在今天应该保持不变。目前的模型还没有聪明到能够完全独立搞定这些的地步。

我目前的工作流首先是完全搞清楚我想构建什么，确保没有任何歧义。然后勾勒出这个软件系统在宏观上应该是什么样子的，比如这可能是几个相互通信的微服务，或者在单个服务级别上，是不同的模块进行交互，以及在这些模块中我们需要哪些具体的函数。

也就是说，你指定了几乎整个系统架构，唯独没有写具体的实现代码。一旦你做到了这一点，你就可以把这些设计编码为规则。我认为这对于缓解人们常说的“认知失调”（Cognitive Dissonance）极为重要。这种认知失调源于不进行代码审查，导致你不再理解自己的代码库，作为人类无法再对其进行逻辑推理。这往往发生在你不再理解系统架构以及新系统各个组件之间如何交互的时候。因此，你必须尽一切努力去阻止这种情况的发生。

<details>
<summary>Original English</summary>

**[Guest]**: Yes. So something... I mean, if you look at software engineering and we're going back to the tradition of doing it, it always used to be: "Okay, what do we want to build? How do we build it? How do we keep it maintainable, right?" Keeping the codebase clean and simple means we can go fast for a long time. And how do we do that as well with architecture, right? We define the architecture up front, and then we started diving into the modules. How do we implement each of them? I think that should still stay the same. The models are not there yet where they can do that on their own. And my workflow now includes first understanding exactly what I want to build, exactly, so that there's no doubt, and then sketching out how this might look as a software system, right? Could be different services talking to each other, could be on a service level, your different modules talking to each other. Which functions do I need in the modules? So you specify pretty much the entire architecture, except the implementation. And once you have that, you can already encode that as rules. Yeah, you know. So this, I think that's extremely important to, also to combat... I think on social media, people already talked about the cognitive dissonance that comes from not reviewing code, where you don't understand your codebase anymore, and you're not able as a human to reason about your codebase anymore. That comes when you don't understand the architecture anymore and how components talk to each other within the software system. And yeah, you need to do everything to combat that as much as possible.

</details>

**主持人**: 我很难想象未来会走向何方。因为我非常同意你的看法，如果我能理解我的软件系统，我觉得这正是未来软件工程师最核心且能够保留下来的技能。而具体的代码实现，我们已经在逐步实现自动化了。而且我觉得只要有足够的守卫规则，我们可以把代码审查收缩到只审查最核心的逻辑，甚至是系统的行为。

我看到现在有人在直接审查“规格说明”，这也会保留下来。但如果我站在一个普通工程师的角度，比如一个在大公司里工作的听众，你可能还不是特别了解你的系统，那要在前期就把所有的拼图都拼好是相当困难的。我们该怎么做呢？在动手之前需要做多少调研？以前在 AI 时代之前，人们往往是边做边探索、边迭代改进的。但现在这种工作方式已经完全不同了。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, it's very hard for me to imagine where this is going to go. Because I agree with you, if I understand my software system, I feel like that's the skill that's really going to remain for engineers specifically. And I do believe that the implementation we're already automating. And I feel like with enough guardrails, we can hold code reviewing to where only the essence, potentially the behavior... I see people reviewing specifications. That will then also remain. But if I put myself in the shoes of an engineer, maybe someone that's listening who is in a bigger organization, you might not already know your system, then it's quite difficult to be like, "Okay, piece the puzzle in advance there." How much investigation do I need to do? That's all work that would happen up front now. And potentially before AI, you would do that kind of as you go, and you would iterate and you would improve. That way of working is now different.

</details>

**嘉宾**: 是的，现在你必须在你的方法论上表现得非常非常有条理，这也是为什么很多人会觉得有些抗拒的原因。因为正如你刚才所说，你不能再只靠“边做边探索”了，你必须把所有最艰难的思考工作都放到最前头。

你可能需要对你的具体实现方案进行几次迭代，从而对优秀的代码长什么样有一个更好的概念。这其实很常见，但你可以通过交互式编码（Live Coding）来完成这个过程。我认为在未来很长一段时间里，这都会成为一种新常态，直到技术再次发生变革。

但我总是喜欢问人们一个有趣的问题：“如果你都不知道自己想构建什么，你又怎么可能开发出软件呢？”这显然是不可能的。所以你做的工作其实是一样的，只是现在你把它放到了最前面。它可能会让你觉得更紧张、更费脑力，但也意味着它正在成为一门独立的学科。

当人们在讨论“既然 AI 可以生成所有的代码，那初级工程师该去做什么”时，我会说，这显然是他们可以去学习的东西，这是一项非常有价值的技能。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, it's very, very, very difficult to be messy in your approach now, which is why some people might resist it. Because, you know, doing all the hard work up front, right? You're not just discovering, as you just said, as you go, you're doing all the hard work up front. You probably have to do a couple of iterations on your implementation to get a better idea of how it actually looks like. So that's not uncommon, but you can do that with live coding, yeah, right? And I think that is going to be the new normal for some time to come before things change again. But the interesting part is that, you know, I always ask people: "Well, how could you develop software if you didn't know what you wanted to build?" Right, that's also not possible. So you're doing the same work. Now, it's just that you're doing it up front, right? It might feel more intense, more involved, but that also means that this is becoming its own discipline. And when people think about, "you know, what should junior engineers do, now that AI can generate all the code," I would say, well, this is clearly something they can learn. That's an invaluable skill. Yeah.

</details>

---

### 认知投降与代理协作

**主持人**: 的确。我发现优秀的软件工程师往往可以归为两类。一类就像你刚才提到的，在动工之前会盯着屏幕，甚至是在疫情之前在办公室里，我看到他们拿着纸和笔，在动手写任何代码之前先画图、写写画画。这真的是一项非常有趣的技能。而另一类人则完全相反，他们觉得：“这对我来说太难空想了，我必须开始敲键盘写点东西。”但他们依然能以极高的效率交付工作。这刚好是第一类工程师的镜像反转。

<details>
<summary>Original English</summary>

**[Host]**: Right. I've seen the best software engineers kind of fall into two categories. The ones who are like you mentioned, someone had to build something, and I saw them stare at their screen (this was still before COVID while we worked at the office five days a week) and I saw them with kind of pencil and paper, and he was like writing stuff and drawing things out before even doing any hands-on. Yeah, and you know that's a very interesting skill. And then you see people who are like, "it's very hard for me to imagine, and I have to start typing," but then they're still fascinating and extremely effective in the way they operate. But it's completely like the inverse of what the first engineer would do.

</details>

**嘉宾**: 确实如此。但好消息是，如果你允许自己去这样做——也就是在确定最终的规格说明之前，先去进行原型设计和探索性开发。你能在迭代想法的过程中切实感受到 AI 带给你的速度。我经常发现自己会对着手机聊上一个小时，仅仅是为了去探索某一个想法。这可能是一个有些跑偏的想法，也许我不该花这么多时间，但它真的能让你学到很多关于如何思考系统的知识。它能够提升你作为工程师的格局，因为现在你不仅在思考“我该怎么去实现它”，还在思考“我们真正需要的是什么？客户需要的是什么？”你可以看到，工程师的思想高度被大大提升了。他们开始更多地从产品层面去思考，而不是像以前那样纠结于“我该怎么用代码把这个写出来”。

<details>
<summary>Original English</summary>

**[Guest]**: Absolutely. And the cool thing is that if you allow yourself to do that, like to do the prototyping to go into this discovery before you put your specifications, not in stone, but before you kind of say, "okay, this is what we want to build," is that it's all incredibly rewarding. I really enjoy that because you really feel the speed that AI gives you when you iterate through ideas. I oftentimes find myself talking to an iPhone for one hour just to explore this idea, and maybe a tangent idea, and that maybe I should have gone on. But it teaches you so much about how you can think about systems, and it also elevates us as engineers because now you're not only thinking about, "okay, how do I implement this," but you also think about, "what do we actually need, right? What does the customer need?" So you can see that, I think, engineers get much more elevated. They start to think at that product level much more now because of that. And that's just going to continue versus before they were thinking about, "okay, but how do we write this in code?"

</details>

**主持人**: 这对你来说感觉如何？因为我聊过的很多工程师在面对并行的工作任务时，大脑里在疯狂运转，又有如此强大的执行力在支撑，到了一天结束的时候，他们往往觉得精疲力竭。

<details>
<summary>Original English</summary>

**[Host]**: How's it been for you? Because a lot of engineers I talk to, when they parallelize work, there's a lot of stuff going up here in terms of thinking, and execution power all of a sudden, and at the end of the day, they're exhausted.

</details>

**嘉宾**: 是的，这确实容易导致职业倦怠，因为你不断地暴露在各种刺激中，并且在频繁地进行上下文切换（Context Switching）。比如你可能需要等待 20 分钟让代理给你反馈。这是非常现实的问题。我上周和一位开发者聊天，他说他觉得自己快崩盘了。他每天都处于一种高度紧张和随时待命的状态，因为他一直在不停地被动做出反应。

我认为应对这种情况的唯一手段就是纪律。首先，你必须清晰地意识到自己在做什么。其次，你必须学会如何在同一个项目的不同子任务之间进行交替，而不是在完全不同的项目之间切换。

比如，优化代理框架运行的环境，这本身就是一个独立的项目，与你真正要去构建的那个业务系统项目是平行的。我会在两件事情之间交替进行。当我等待一个代理去完成某项任务、想看看它会产出什么结果时，我会直接切换到另外一件事情上，比如在同一个代码库里开启另一个与不同代理的会话，开始向它追问代码库的结构。这样我能让自己保持在相同的上下文里，避免在不同项目之间进行剧烈的硬切换。

如果我不这么做，结果就是我必须在会话中不断敲字：“请告诉我，我们过去这半小时里都做了些什么？”我必须让它来帮我回顾记忆。

有时候这确实挺微妙的。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah. Well, they burn out because you're constantly exposed to stimuli and you're constantly context switching. Because, they... AI takes 20 minutes to respond to you. That's real, that's absolutely real. I talked to a developer last week who said he's burned out. He's just stressed, just on standby because he's concurrently reacting all the time. I think that's 100 percent real. As with anything, I think the way to combat that is discipline. Well, okay, the first step is you have to be aware of what you're doing. But you also learn how to interleave tasks, maybe on the same project but different things. So the work on the environment that guides the agent, that's its own project besides the actual project that you try to build. So, and I keep iterating between the two. So when I'm waiting for an agent to complete something, because I want to see what it does or how it did, I would just switch to something else. I might start another session with a different agent on the same codebase and start interrogating the agent about the codebase. And so I stay kind of in the same context, but I don't switch between projects as hard. Yeah. And if I don't do that, one thing that happens is that I keep having to type in the session: "Now please tell me, what did we do in the last half hour?" So it has to remind me what it did. And, it's weird sometimes, 100 percent.

</details>

**主持人**: 是的。我以为 Claude Code 会自动处理这部分？比如如果你离开一个会话太久，它会主动给你提供一个摘要，你就不用再去问了。不过这可能属于他们正在解决的某种用户体验（UX）问题。

我们刚才提到了“认知负荷”，这对于真正热爱手艺或专注工作的工程师来说，会是一个非常关键的话题。另外，我上周和 **Addy Osmani** 聊天时，他提到了一个我此前从未听过的概念——**“认知投降”（Cognitive Surrender）**。也就是说，人们直接放手让 AI 代理去掌控方向。如果出了问题，那是 AI 的错；如果成了，那也是 AI 的功劳。他们完全放弃了自己应当承担的责任。我觉得在当前技术演进的过程中，这是极其危险的。我认为像我们今天这样的对话对于给人们提供视角、挑战什么该放手以及什么该保留为你的个人责任，是无比重要的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, I thought Claude Code does that automatically. Now if you're out of a session for too long, it gives you like a summary, so you don't have to ask anymore. Yeah, there... maybe some UX problem they're solving, I think.

And we already mentioned cognitive debt is going to be a very crucial topic that engineers who really care about this craft or about their work care about. And also, I spoke with Addy Osmani last week. He mentioned this, which I hadn't heard of: "cognitive surrender," where people are like, "the agent just takes the wheel." And if there's a problem, it's the agent's fault. And if it works, it's also the agent. But then, they really just let go of what they're responsible for. And I feel like that's quite risky in the way we are evolving. I think conversations like you and I are having are incredibly important to give people perspective and to also challenge what goes away and what remains as part of your accountability.

</details>

**嘉宾**: 确实。有趣的是，很多企业目前做的事情，就是直接给员工发一把“手枪”（AI），然后对他们说：“别用它把互联网给炸了，但也记得去用它。”

未来一切都会被规范化。关于你被允许用 AI 做什么、不能做什么，都会有具体的规章制度。就像我前面提到的亚马逊的例子，他们已经在“哪些代码比其他代码更关键”以及“如何对其进行审查”之间做出了政策层面的明确区分。我们很快就会看到同样的做法普及开来，成为软件工程师日常流程的一部分。比如某些规定会非常明确：“请千万不要去碰我们的计费系统，求你了。”我觉得这在不久的将来就会成为常态。

而且，很多我们不想去做的脏活累活，也可以外包给 AI。因此，“不做任何代码审查”这个点子，听起来可能很激进，但当你试图去落地时，会发现伴随着很多具体细节。比如有像静态守卫这样成本极低且能够快速执行的确定性手段；紧接着，讨论的重心就会转移到架构和规格说明上，变成在前期验证规格说明，而不是在后期去审查具体的代码实现。

同样地，即使你在后期需要作为人类去审查系统架构，你依然可以使用 AI 来辅助。你可以与 AI 进行对话，甚至使用一个专门的代理，专门用来检测是否有任何改动违反了你在项目中试图实现的特定架构设计。你完全可以在你所有的代码变更上运行一次自动化扫描，并以此为切入点，再由人类开始介入审查。通过这种方式，你依然可以实现高度的自动化。这其实只是关于：“我应该看哪里？哪里是我不需要看的？”

否则的话，我实在看不出我们该如何扩展代码审查这一环节。代码生成的效率已经提升了 10 倍甚至 100 倍，压力必然会全部转移到下游的所有系统上。而首当其冲的就是人类在回路中的代码审查。所以我们必须尽一切努力将其最小化。

<details>
<summary>Original English</summary>

**[Guest]**: Absolutely. And the funny thing is, basically, what employers are doing is they give people a handgun, which is AI. And then say, "don't blow up the handgun, but use it," right? So there's a lot of use of AI, but all of that is going to be standardized. There are going to be policies on what you are allowed to do and what not with AI. And the example I gave with Amazon, right? They already made a policy distinction between your code that is more critical than other code, and how that should be reviewed. So we're just going to see the same thing, and it's just going to be another form of the process for software engineers, right? Where you have to define stuff, where if you just want to yolo it... "Okay, let's not touch the billing system, please." I think that's going to be normal pretty soon.

And also, a lot of the review work that we don't want to do, we can outsource to AI as well. So the idea of not doing any code reviews comes... I mean it's kind of like a loaded idea, right? But when you attempt to do that, a lot of realizations have to come with it, right? There are cheap wins like guardrails, right, that are deterministic, that execute cheaply and quickly. And then the conversation shifts towards architecture and specifications, and more validating specifications up front, rather than the code later. And likewise, even when you have to review the architecture later as a human, you can still use AI for that, right? You have a conversation with the AI, maybe have a specialized agent that you particularly set up to review for any violation of a specific type of architecture that you're trying to implement in your project. So you can also do an automatic scan over all of your code changes, and then use that as the point to start looking into it as a human, right? So you can still automate a lot. And it's really just about: "Okay, where should I look? Where don't I have to look?" Yeah, otherwise I don't see how we're going to scale the review part. The code generation is ten times faster or a hundred times faster. The pressure is going to be on all of the systems that come downstream from that, absolutely. And part of that is the review with the human in the loop. So we have to try to minimize that as much as we can.

</details>

---

### 自动化测试与最佳实践

**主持人**: 是的。我觉得输入的生产力我们很容易就能成倍提升，我们可以快速把更多的想法付诸实践。但要在生产环境中利用各种测试来对它们进行把关，审查流程确实是真正的瓶颈所在。你提到的这几点，确实是解决代码审查拼紧的重要拼图。即便以我们目前拥有的模型能力还无法完全实现“彻底脱离人类回路”这一终极目标，但我确实看到了守卫规则的价值。我也看到了应该尽可能多地去覆盖行为和功能测试。我觉得在今天，没有任何借口不去写测试了，因为你可以根据你期望的行为直接自动生成测试，对吧？如果你修复了一个 Bug，把它写成测试，这在以前就是最佳实践，但在今天更是没有理由不去这样做了。这显然是一个趋势。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, I feel like the input we can likely scale faster, right? We can just execute on more ideas. The reviewing things in production with different tests... the reviewing process is really the challenge. Some of the things that you mentioned, I do see those as ingredients to solving this puzzle, that is the code reviewing process. Not having a human in the loop at all, if that's the big goal that we're working towards, even though it might not be feasible now with the models we have, I do see guardrails in there. I do see catering as much as you can. Behavior, functionality. I don't think there should be any reason to not write a test anymore because you can just generate the test according to the behavior that you want, right? If you solve a bug, if you make a test of that, that was already good practice, but there's no reason to not do that anymore nowadays. So that's a trend.

</details>

**嘉宾**: 是的。而且人们往往会忽略一点，生成一个测试通常是一段非常小且逻辑单一的代码，大语言模型把它写对的概率，要远远高于你让它直接去写一个复杂的微服务。因此，在编写测试时这也非常有帮助。即使你是自动生成它们（就像我做的那样），出错的概率也是非常低的。

<details>
<summary>Original English</summary>

**[Guest]**: Yes. And what also people often forget is that generating a test is a small piece of code. The chances of the LLM not doing it right are much smaller than when you tell the LLM, "generate me microservices." Yeah, right? So that's also another point that I think helps when you write tests, because even if you generate them automatically (which is what I do), the chances of failure are relatively slim.

</details>

**主持人**: 我见过也聊过其他一些团队，他们非常彻底地拥抱了规格说明驱动开发。这已经成为了他们的核心工作流。他们使用某种特定的规格说明框架，并且对这种方法非常满意。我也很想邀请他们上我们的节目。但我注意到他们似乎并没有像你我所讨论的那样，把这些守卫规则深入融合到他们的代码审查流程中。他们所做的是，让整个审查流程高度围绕着“规格说明”来进行，他们审查的正是规格说明本身。而且我相信他们一定也有一些守卫规则，用来确保规格说明中的内容能够被准确地翻译和实现为代码。对我来说，这里面唯一的风险只在于可能存在的非确定性行为。但我认为这是一个非常有趣的尝试。

<details>
<summary>Original English</summary>

**[Host]**: I have seen and spoken to other teams, and they fully adopted specification-driven development as their workflow. They use one of the specification frameworks, and they're very happy with their approach. That's why I want to have them on the podcast. But they mentioned that they have not built the guardrails like you and I are discussing within their code review process. What they have done is their review process now very much revolves around the specification, and that is what is reviewed. And I do think they have some guardrails in place to make sure that whatever is in the specification is also translated into code in a certain way. For me, there's only kind of the risky part, which is the non-deterministic behavior that can be in there. But I think that's an interesting approach.

</details>

**嘉宾**: 是的，你提到这一点很好，因为“守卫”并不一定仅仅意味着一段提示词。我觉得最开始守卫这个词确实是这么定义的，但它们同样可以是完全确定性的。我非常喜欢这种规格说明驱动的开发方法，但主要是因为它能让团队成员对要构建的东西达成清晰的共识。

但如果你直接把规格说明丢给一个大语言模型并观察它的行为，你会惊讶地发现，仅仅过了 5 分钟它就会开始偏离你的意图。原因往往是你某些地方写得不够明确，或者留下了可以被随意解读的空间。于是你不得不去反复修改你的规格说明，试图让它变得完美，但当你切换到另一个模型时，它可能又失灵了。

<details>
<summary>Original English</summary>

**[Guest]**: Yes, and actually good that you mentioned it, because guardrails do not also mean just a prompt, right? That's, I think, how guardrails started to be defined, if I'm not mistaken, but they can be deterministic as well. The specification-driven development approach, I really like that, but mostly because it gives a human clarity of what is being built. If you give that to an LLM and you observe what it does, you'll be surprised that after five minutes already, it starts to deviate from your intentions because you didn't specify something clearly enough or there was some room for interpretation anywhere. So you can iterate on your specification, trying to get it perfect, and then you switch the model, and it doesn't work anymore.

</details>

**主持人**: 那么这是否意味着，在你的视角里，规格说明驱动开发在未来会消失，还是说它是一个目前行之有效的方法？你如何看待它的未来？

<details>
<summary>Original English</summary>

**[Host]**: So does this mean for you, your perspective, what do you think of specification-driven development? Is it something that works now, but it's going to be gone in the future? How do you see that?

</details>

**嘉宾**: 我认为这依然是探索你想构建什么的产品设计过程的一部分。非常重要的一点是，这些规格说明在后面可以被用作自动化测试的输入，去校验：“我们真的实现了这个吗？我们是怎么实现的？它是否符合我们的编码规范？”你可以把这些问题交给 AI 去做深入的调研。所以规格说明会继续存在。

有些人喜欢把规格说明写得极其详尽，甚至把它当成代码来写。我觉得没必要，它毕竟只是一份用来达成团队共识的文档。它只需要规定系统的一部分行为和功能。

相比之下，我认为对你所构建的东西进行“细粒度”的行为规格定义要重要得多。

这里有关于测试驱动开发（TDD）的一个经典理论：如果你所有的代码都被删光了，但只要你还保留着所有的测试，你就能重新构建出你的软件。这就是 TDD 的核心理念之一。但在我过去的工作中，我第一次真正看到这个理论发挥威力，是因为我编写了完整的行为测试来给 AI 代理提供闭环反馈，同时我把最初的规格说明作为初始提示词来启动具体的代码实现。这是我职业生涯中第一次在实际项目中看到这套流程运转成功。这确实不可思议。

<details>
<summary>Original English</summary>

**[Guest]**: Well, I think that is part of that discovery product process of what you're trying to build. I think it's extremely important to have that, that can also be used as automated tests later, like checking: "Did we actually do this? How did we do this? Did we do this in accordance with our coding principles?" Those are questions you can then give to an AI to investigate, so the specs will stay there. People like to go in-depth with specifications, like they treat it as if it was code. It's not, right? It's just a document of shared understanding. I would say that specifies part of their behavior, part of what is being built. I think a fine-grained behavior specification of whatever you're building is much more important. There was this idea of TDD where if you have all of your tests and your software gets deleted, but you still have your tests, you can rebuild your software. That was one of the ideas of TDD. And I've seen it work for the very first time when I had behavioral tests implemented that would give the agent feedback, and I had a specification as a prompt to start the implementation. That was the very first time in my life I had seen this actually work in my project.

</details>

**主持人**: 这确实非常令人惊叹。我很好奇对于现有的庞大代码库来说，如果我们在实践中抛弃掉旧代码，假设这个团队已经坚持做 TDD 很长时间了，AI 是否真的能够仅凭这些保留下来的行为测试，就完美地重新生成一模一样的系统。

<details>
<summary>Original English</summary>

**[Host]**: That's still quite incredible. I wonder if with existing codebases, right? A lot of this is in theory, which is why it's quite the challenge. But I wonder if, indeed, if you would throw out the code, if people have been doing TDD in that codebase for quite a while, if an AI indeed can then generate the code exactly how it is according to the behavior that was captured.

</details>

**嘉宾**: 是的，如果你周末有空闲的算力或时间，你完全可以试一试。这听起来是一个非常有趣的实验。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, if you have some time to burn, you can try that over the weekend.

</details>

---

### 本地演练与实践

**主持人**: 我注意到，在软件工程进入 AI 代理时代之前，大公司往往是规则的制定者，很多小团队都会仰望并学习他们的最佳实践、行业惯例以及技术博客。而现在，游戏规则被彻底拉平了。因为技术迭代太快了，正如你提到的，仅仅过去几个月，代理框架及其能力就发生了解构与重组，这也为我们所有人提供了一个平等的实验舞台。

你在日常中是如何进行实验和自我提升的？许多人常常会有一种在后面拼命追赶、害怕落后的焦虑感。

<details>
<summary>Original English</summary>

**[Host]**: That seems like an interesting experiment. But what I have noticed is that also, the bigger companies previously, before AI agentic software engineering, I feel like they were trailblazing and a lot of smaller organizations were looking up to good practices, best practices, conventions and blog posts of what is out there. And what's happening right now, I feel like the playing field is quite equal, because everything is very quickly evolving, as you already mentioned. Over a few months, harnesses and their capabilities are pushing what is effective and all of a sudden what is now possible, which gives us a very interesting playing field to experiment with. How do you typically experiment to educate yourself? People have a constant trying to catch up, feeling behind type of thing.

</details>

**嘉宾**: 我觉得每个试图跟上步伐的人多多少少都会有这种感觉。我习惯使用不同规模的具体项目来进行实验。

我手头有几个不同的项目。其中一个是纯 AI 代理生成的项目，我从始至终没有看过一眼它的代码，完全只通过提示词让它去开发。另一个项目我则尝试了 TDD 的方法，利用行为测试和守卫规则来指导开发。

还有一个项目包含了多个微服务，结构要复杂得多，主要是事件驱动（Event-driven）的系统。我会使用在这些项目里总结出的不同方法去不断给它们增加新功能，并仔细观察：AI 到底是怎么做的？它在哪里犯了错？

每当我看到 AI 做出了一些诡异的事情，我就会立刻把对策写进我的默认守卫规则库中。所以我现在有一个通用的模板库，针对不同的编程语言有默认的项目配置，并且预装了我在不同项目中验证过非常有用的守卫规则。

因此，实验的过程包含了大量与 LLM 的直接沟通。我发现一个非常有用的技巧是让 LLM 去解释它自己。比如在我给它分配一个复杂的任务之前，我会先问它一个非常简单的问题：“请告诉我，你对我们接下来要做的事情是怎么理解的？”

通过这种方式，我能对比它理解的内容与我实际表达的意思之间的偏差，你也能看到不同的模型是如何以截然不同的方式去解读同一句话的。这能让你对模型的“性格”或行为模式有一个非常直观的认知。

另外，我也总是喜欢尝试各种最新的工具。比如当子代理（Sub-agents）的概念出来时，我立刻去做了尝试。我发现人类对于这些子代理之间到底在交流什么、它们是怎么协同的，完全处于一种“黑盒”状态，缺乏任何内省（Introspection）机制。

于是我自己开发了一套系统，每当代理要唤起一个子代理时，我会强制让它在另一个终端窗口里运行。这样我就可以实时看清它给子代理发送了什么信息。

相信我，你会看到模型之间在说一些极其荒谬和诡异的话。你也能发现在把任务交接给子代理的第一步时，模型就已经开始偏离轨道了。

所以，尽可能去透视底层发生的事情，监控代理之间传递的信息和它们的行为，这对于整个编排（Orchestration）系统来说是无比重要的。我大部分关于模型行为和多代理协同的认知，都是通过观察这些底层细节学到的。因此我花了很多时间在这些事情上，去不断修正自己对模型的理解并应用到工具链中。

<details>
<summary>Original English</summary>

**[Guest]**: But I think that's normal for everybody who's trying to keep up with things. So I like to use projects. I have a couple of different projects that are on a different scale. One project is purely agent-coded. I have never looked at the code, I've only prompted it to do stuff. I have one project that is a toy project, that's the one that I used for the TDD approach with a behavioral test and guardrails, where I test that type of approach. I have another project that consists of multiple microservices, which is much more complex, which is mostly event-driven. And I keep adding features to them using these different methodologies that I set up for this project, and just observe: what does the AI do? What does it do wrong? And more often than not, I see the AI do something weird, and then I make that immediately part of my default guardrails. So I kind of have a repository where we have default project setups for different languages, and that is preloaded with a certain type of guardrails that I found useful in the projects that I do. So the experimentation involves a lot of communicating with the LLM. I really found it useful to ask the LLM to explain itself. So if I give it a complex task, I ask: "Please tell me what your understanding is of what we are trying to do." A very simple question. So I'm trying to find out what the model understood of what I said versus what I actually said, and you can see how models interpret things differently. And that gives you an idea of, you know, personalities is too far, but what type of behavior does it exhibit, probably the better term to use. So I do that a lot.

I try out the latest tools that they give us. Like when sub-agents came, I tried that out. I concluded that I have zero visibility about what the agents are doing, like what are they communicating with, I have no introspection. So then what I would do is I try to add introspection to that. And I built my own assistant where I told the agent, "please spawn a sub-agent, but do it in a different terminal." So I can actually see what you sent to that different agent. And yeah, well, you'll see the weirdest things that the models tell each other, right? You can already see how the model started to deviate like at the first step when the handoff of the task happens. So trying to look under the hood as much as possible: what information gets exchanged, monitoring what the agents are doing when they talk to each other. I think those are incredibly important things for the orchestration itself. And I learned the most from looking at those types of things, of what the model is doing, how they talk to each other. So I think that is how I spend most of the time to refine my understanding of what the models do and also trying to apply what they give us in terms of tools.

</details>

**主持人**: 如果有听众也想把这些开发方法应用到他们已有的生产环境和日常工作中，并且他们的团队目前可能很少甚至完全没有采用这些工具，你想给他们推荐的第一步是什么？

<details>
<summary>Original English</summary>

**[Host]**: If someone is listening and they want to apply agentic software engineering to their own way of working, some piece of code that is already live in production, and likely the team has already adopted some practices or not at all, and they want to kickstart something, what is step one that you would recommend for an individual developer? And they could be within a team, I think that's the most profound case.

</details>

**嘉宾**: 我觉得最简单且成本最低的起点就是引入静态的守卫规则。比如你们团队应该已经有了代码格式化工具和静态代码检查（Linter）。你可以在此基础上尝试去写几条 Semgrep 规则，用来强制推行你们代码库中已有的最佳实践。

你甚至可以直接去问 AI：“在我们的代码库中，有哪些常见的反模式（Anti-patterns）？”然后让它帮你写一条简单的 Semgrep 规则去检测它们。

如果你在团队里遇到了阻力，那就退而求其次。你很难去强行说服一个完全不相信这些理念的人。但你完全可以在你本地的机器上跑这些工具，你不需要强迫团队里的每个人都去使用它，你只用它来规范你自己写的代码。

你可以用一段简单的脚本来检测这个文件是你创建的还是别人创建的，如果是你自己的代码，就去跑你的守卫规则。

最关键的一点在于，你必须去衡量或者感受，在引入这些守卫规则前后，你的开发效率以及你被卷入细节的程度发生了怎样的变化。因为一旦你体验到这些守卫规则能帮你分担掉大量枯燥的纠错工作、让你不需要整天去当 AI 的“监护人”时，你就绝对再也回不去了。这真的非常省心。

<details>
<summary>Original English</summary>

**[Guest]**: I would say the simplest is: start with guardrails, static checks. Or they should have, of course, a code formatter. You should have a linter. Try to write some Semgrep rules that enforce some of the best practices that you see in your codebase. You can ask AI, for example, "what are some anti-patterns that we use in the codebase?" and write a simple test that flags them. If you work in a team, have a team discussion. You know, if you get resistance, well, then try the next best thing. It's really difficult to convert people who are not buying into the ideas of trying to improve the codebase, and streamlining it with tests or with guardrails. But you can run all of these things on your local machine. You don't have to enforce everybody to use it, but you can use it for the code that you write yourself. You know, you pair it up with a smart script that checks whether you created that file or somebody else, and where you enforce your guardrail rules. And the key point is: you should measure, or at least get an impression of how it works with those guardrails that you put in place versus without them. Because once you see that they actually help you do more work and be less in the loop, you will not go back. I don't think it's... yeah, it becomes really convenient to not have to worry about and babysit the model all the time.

</details>

**主持人**: 这确实很吸引人。“监护”（Babysitting）这个词，也是我在与大家的对话中一直试图去消解的。我一直在寻找最好的方式，可能是通过实验，进入持续改进的循环；也可能是通过捕捉 AI 的行为，并将其转化为守卫规则供代理去学习；或者直接从团队的拉取请求（PR）反馈中提炼规则。

<details>
<summary>Original English</summary>

**[Host]**: I can see that, right? This term, "babysitting," I'm trying to get rid of in the conversations that I have with people, and I'm trying to figure out what the best way is. It could be indeed kind of experimenting and going into this cycle of continuous improvement. And it could be you catching behavior you want as guardrails for the agent to then pick up and do something with. And it can also be feedback that you get from your team, right? And you can create a pull request, then this feedback from your team, yes, it can also then catch things in more guardrails.

</details>

**嘉宾**: 这确实是另一个绝妙的点子。你完全可以对 AI 说：“嘿，去分析我这个项目里所有的会话日志（Session Logs）。”AI 会直接读取你本地的配置文件，仔细研究你和它的所有历史对话。

然后你可以问它：“你有没有发现，在哪些地方我不得不反复向你强调和纠正同一件事情？”

通过审查这些会话日志，你可以精准找出模型在哪些地方容易犯错，以及你必须在哪里进行干预。然后，直接把这些纠错点转化为静态检查规则。

<details>
<summary>Original English</summary>

**[Guest]**: And that's also another idea. So what you can do is you can just say: "Hey, analyze my session logs on this project." It'll go into your home folder, and will start looking at all of your conversations. And you can ask if it sees any patterns where I had to repeatedly remind it of a certain thing. So you can examine your session logs to see where the model goes wrong, where you also have to correct it, and turn that into a static check, right?

</details>

**主持人**: 这听起来就像是我梦寐以求的产品。

<details>
<summary>Original English</summary>

**[Host]**: This feels like a product that I would want to have, yeah. Which is actually not a bad idea.

</details>

**嘉宾**: 哈哈，这其实只是一项技能（Skill）。你完全可以自己写一段脚本或者让 AI 帮你写。这非常简单，大概只需要花 15 分钟，然后你就能在工作中用起来了。

<details>
<summary>Original English</summary>

**[Guest]**: Yeah, well, actually it's a skill. You can just use a skill. It's easy, it takes like 15 minutes, and then you can use it absolutely.

</details>

**主持人**: 我们前面提到，不同的代理框架可能会带来完全不同的效果。但在很多大公司里，员工往往没有自主选择工具的权力，公司直接统一采购了 GitHub Copilot，大家只能在这一种框架下工作。你对这些开发者或这些企业有什么建议吗？

<details>
<summary>Original English</summary>

**[Host]**: We mentioned different harnesses might have different results. Yeah, and in organizations, people just get one harness. And that's right, we've gone all-in on GitHub Copilot because of all the models, you know, but it's only one harness. And would you recommend anything to either those developers or those organizations?

</details>

**嘉宾**: 这确实是一个很棘手的问题。如果你作为开发者完全无法选择自己的工具，我相信没有哪个开发者会觉得开心。

我认为在这种情况下一方面的科普和教育会有所帮助。目前行业里已经有很多关于不同代理框架对比的研究报告了。我们有充足的证据表明，仅仅依赖某一家特定的工具，是无法让你始终保持在技术前沿的。

因此，这里面有很多理性的论据可以去向上沟通。我理解企业天然有一种去标准化、统一管理工具的倾向。但 AI 工具绝对不像你以前选采购软件那样，选定一个就可以安稳运行五年。AI 领域的逻辑完全不是这样的。企业必须真正理解 AI 技术演进的独特性。

<details>
<summary>Original English</summary>

**[Guest]**: That's a really difficult one. If you cannot choose your tools as a developer, I don't think any developer is really going to be happy with that. I think education would help in that case. You know, there are studies out there that compare harnesses. We have enough evidence to suggest that relying on one particular tool is not going to keep us at the edge. So there are lots of arguments to be made. I understand that organizations, you know, have this desire and tendency to just standardize things. But it's not like you select a product and then you run with it for five years. That's not how AI works. And that just needs understanding of what AI actually means.

</details>

**主持人**: 是的。我觉得这正是很多人所忽视的，因为我们现在已经超越了单纯比较模型的阶段，代理框架所起到的作用往往超过了底层的模型本身。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, I feel like that's missing, right? Because we are now beyond models specifically, and the harness might matter more than the model itself.

</details>

**嘉宾**: 确实。不过作为独立开发者，在有限的工具选择下，你依然可以去主动发掘你手头这款特定工具最擅长处理哪些场景。比如它可能特别擅长写 PR 文档，或者非常擅长某类特定 Bug 的调试。找出这些强项，然后在对应的场景里把它的价值发挥到最大。

<details>
<summary>Original English</summary>

**[Guest]**: Well, there's another thing you can do as a solo developer: try to find out at what things your particular harness is good. Maybe it is at, you know, writing pull request documentation. Maybe it's really good at debugging. Try to find the use cases where you can still use it, and then you use it for that. Yeah, absolutely.

</details>

**主持人**: 明白。对于我们的听众，我想征求你的建议：如果他们这周能抽出一小块时间，去跑一个具体的实验，你最希望他们去实验什么？

<details>
<summary>Original English</summary>

**[Host]**: For the people listening, I'm trying to do this new thing because I want your advice on what experiment you want people to run. If they have a week's time, and they can do one experiment as kind of their budget of time they have, what would you want them to do an experiment with?

</details>

**嘉宾**: 这取决于你目前在公司里处于什么角色。但对于开发者来说，你有几个不同的方向。你是想在与 AI 协作的代理工程（Agentic Engineering）上更进一步？还是想去精进你本地的守卫规则？又或者是想更深地理解不同模型的行为特质？这是你需要先明确的首要问题。

不过，如果你是一个刚刚接触守卫规则的新手，我极力推荐你去了解一下 Semgrep。

尝试把你平时在拉取请求（PR）中会对同事提出的某一条人工代码审查意见，翻译并编码为一条静态规则。就像我前面提到的在 Python 中禁止参数默认值，或者比如“绝不允许直接吞掉异常，所有 Error 必须被向上抛出或妥善记录”等等。

试着在你的开发环境中配置好这样一条规则，然后仔细观察你的 AI 代理在面对这样一个受到约束的环境时会做出什么样的反应。

着手去建立这些属于你自己的守卫规则，去不断优化和迭代它们。我认为这是一件投入产出比极高的事情。你很快就会看到非常直观的效率提升。尽管有些人可能会觉得：“这不就是我们以前早就有了的静态代码检查吗？”但区别在于，你现在是在用静态规则去编码你作为人类开发者的主观偏好。

<details>
<summary>Original English</summary>

**[Guest]**: Well, that depends on where you are in the organization, I'd say. But for developers, I mean, there are a couple of options, and it depends on what you want. Do you want to get better at agentic engineering, like working with AI? Do you want to get better at putting in your guardrails? Do you want to get better at understanding how the models behave? So that's the first question. But whatever you want, there's an infinity of many different options of what to do. I would recommend: if you want to get started with guardrails, start looking at semantic grep (Semgrep). Let's try to encode some of your human feedback that you would give in a PR as a rule. And the example that I gave earlier with no default values in method parameters could be one example. Another one could be: "let's never swallow any errors, and any error must always be propagated," something like that. Just start experimenting with that and see how your agent reacts to that environment. So setting up, I think, the guardrails so that you can start to improve them and iterate on them, I think that's very worthwhile. And you will see, I would argue that you will see wins very quickly. Even though you might think, "but we had those static code checks first," now you're doing it in a way that you encode your human preference as rules right now. Yeah.

</details>

**主持人**: 好的，非常感谢你今天做客我们的节目并分享了这么多真知灼见，这对我们极具启发性。

<details>
<summary>Original English</summary>

**[Host]**: So the customer for your particular project, clearing. And thanks so much for going on. This was really valued. This is really good. Thank you.

</details>

**嘉宾**: 谢谢。

<details>
<summary>Original English</summary>

**[Guest]**: Thank you.

</details>

**主持人**: 感谢大家的收听。如果你听到了这里，请在评论区留下你的看法，告诉我们你对这一期节目的想法。我们下期节目再见。

<details>
<summary>Original English</summary>

**[Host]**: If you're still with us, let me know in the comment section what you thought of this episode. And we'll see you in the next one.

</details>