---
author: AI Engineer
date: '2026-07-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iRcX54EO5g8
speaker: AI Engineer
tags:
  - ai-agent
  - feedback-loop
  - developer-tooling
  - software-engineering
title: 给 AI 戴上“氧气面罩”：通过反馈循环与自定义工具链重构开发流
summary: 本演讲探讨了 AI 代理在遗留系统开发中的局限性与信任赤字，指出‘反馈循环’是决定 AI 开发成败的关键。演讲者介绍了 Poolside 内部的 VS Code 插件测试工具 Spoolside，并呼吁工程师转型为 AIX（AI 体验）工程师，优先为 AI 构建调试和验证工具，使其能自主复现与解决问题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 信任裂谷：反馈循环的分水岭

在当今的开发者社区中，关于 AI 编码代理的体验存在着巨大的鸿沟。部分开发者在 Twitter 或 Reddit 上宣称自己“再也不用手写代码，AI 已经包办了一切”；而另一部分开发者在尝试将 AI 引入生产环境后，却愤怒地抱怨它产出的全是垃圾。

导致这种两极分化的核心原因，不仅在于**绿地项目**（Greenfield Project）与**遗留系统**（Brownfield Project: 在现有代码库和架构上进行开发与维护的项目）之间的差异，更在于**反馈循环**（Feedback Loop: 执行结果流回系统并作为输入调整后续行动的闭环机制）的完整性。在绿地项目中，AI 拥有极佳的直觉，它按照常规逻辑编写组件和服务即可顺利运行；但在遗留系统中，往往潜伏着未知的“恶龙”——废弃的代码、未被察觉的依赖以及复杂的历史上下文。当 AI 代理声称“我已经完美实现了新认证流程”时，它真正的意思是：“在我的有限视野和已有输入中，这段代码看起来应该可以工作。”如果缺乏实时的验证机制，这种“盲目自信”就会转化为用户的信任赤字。怀疑者在看到代码无法运行后会立即选择放弃，而善用 AI 的人则会引导 AI 去查看日志并重新尝试。为了弥合这一裂谷，我们必须为 AI 建立更强大的闭环验证手段。

<details>
<summary>Original English</summary>

Hi everyone. So I'm Joan from Poolside. If you haven't heard of us, we're one of the handful of companies that are making their own foundational model from scratch their own LM and coding agents. Check us out if you if you're not aware some cool stuff and you should hear more soon. But what I want to talk to about today is this. You have people seeing AI and using AI and getting vastly different experiences. If you're on Reddit, if you're on Twitter, you're going to see people that say, oh yeah, I'm never like touching code anymore. The AI is is doing everything for me. It's fantastic. And others that say, what are you talking about? I'm trying it in my production app. It produces absolute garbage. What are you guys working on to do apps? What are you doing? And there is multiple ways to try to to to understand what's going on there. One way is to say, this guy is a shill from open AI trying to sell you AI. Or this one is an entity that doesn't care about anything and is just like lying. He didn't even try it. Another is to say, well, maybe someone is working on a greenfield app and that's nice and easy. Whereas someone else is working on brownfield on a legacy application. That's complicated and agents are not there yet. But personally, I think that doesn't quite hold up. We've seen people using AI in legacy applications with good success. I have myself. So at least on my own experience, I know that can work. So what's the difference? What's the difference really between brownfield and greenfield? The difference is that with greenfield, the agent's intuition is correct. The agent's writing the code and expect, you know, if I write the components here, if I write the service, it's going to work. I I think that's going to be fine. And he's right cuz it has very good intuition. On brownfield, however, there be dragons. You're going to have things that the agent is not expecting. Maybe you know, like dead ends, code that's not used anymore, things that it is not aware of in in different part of the code that it hasn't even looked at. And that's where the big difference between those two is the feedback loop. And everybody is somewhat talked about it in in in the background of the talks we've seen over the past three days. But I think that's the difference with getting these results. So you you've got your agent that says, yeah, I've implemented the new auth flow and it's all working perfectly. What the agent means really is, well, to the best of the of my capabilities, to the best of what you have given me, that sounds like it should work. Maybe the agent was able to verify its work. Maybe it wasn't. But as far as it knows, it's working. If you're a skeptic of AI, you're going to see that first quote, see that it's indeed not working and just sees, you know, I'm a liar, I'm incompetent or like you cannot trust the AI. And that's I think where this cleavage in between those two type of users. Like the first category is going to see some things. Oh yeah, actually, you know what? It's not working agent. Can you try again? Check those logs or whatever. Whereas those ones are just going to give up. But I think we can make this still better.

</details>

### 自主复现：打破盲目自信的工具链

为了提升 AI 代理的可信度，Poolside 内部开发了一款名为 **Spoolside**（Spoolside: 专为测试集成于编辑器中的 AI 代理而构建的内部命令行工具）的 CLI 工具。它允许 AI 代理像人类工程师一样，以非常低的 token 损耗去感知和操作应用界面。

由于我们的产品并非普通的 Web 页面，而是一个深嵌在 VS Code 内部的插件，这使得传统的屏幕截图或简单的 DOM 树压缩方案难以奏效。Spoolside 扩展了这一边界，为 AI 代理提供了丰富的交互接口：
* **日志提取**: 能够实时捕获并分析前端与后端服务的运行日志；
* **服务重启**: 允许 AI 自动重启出错的微服务以尝试修复；
* **高层级控制**: 赋予 AI 访问特定菜单、导航至指定页面、发送交互消息并等待响应，甚至上传图片的能力。

通过这些高层级命令的组合，AI 代理在着手修复缺陷前，必须实现**自主复现**（Self-reproduction: AI 独立模拟并触发特定缺陷以验证其存在的过程）。如果 AI 宣称发现了一个 bug，但在运行工具链后却无法复现它，那么其给出的修复方案也是不可信的。只有当 AI 具备了先复现、后修复、再验证的闭环能力，人类工程师才不需要耗费时间进行手动 code review 和本地运行测试，进而真正放心地让 AI 代理在夜间通宵自动工作。

<details>
<summary>Original English</summary>

At Poolside, I've created a little CLI tool called Spoolside. Yeah, I might be good at programming. I'm not good at naming things. That basically allows it to test our applications effectively. Some of the stuff you've already seen in things like G stack for instance being able to take screenshots of the applications, being able to take a snapshot, that is to say like a very token compressed version of what's going on on a web page and use it. But our application is not a web page. It's an extension within VS code. So already lucky takes an extra step to get there. But with that, our AI can interface with it just like it would with a normal web page. But we take it further. We have thing to extract logs from different services, from the back end, from the front end, ways to restart different services, high level commands. Can you access a specific menu? Can you go to this page? Can you send a message to the agent? Wait for it to reply, send another message, upload an image and do that and it can stack things like somewhat efficiently and a bit like we've talked with coding tools this morning. And that's pretty useful cuz then the agent is able to test what it's doing. If it's working on a bug, it can actually reproduce the bug before it starts working on that on that. The agents are very eager. Yeah, I know what's going on. You just need a margin there. You just need to go and add this code. But until it reproduces the bug, I don't trust you. And that's the big thing.

</details>

### 转型 AIX 工程师：给 AI 戴上“氧气面罩”

Spoolside 并不是一个开源或通用的商业产品，它的核心价值在于向我们揭示了软件工程师在 AI 时代的角色转变。我们正在从传统的“产品功能开发”，转型为 **AI体验工程师**（AIX Engineer: 专注于为 AI 代理设计更优工作环境、工具链及接口的工程师）。

这一转型的核心思维是：**先给 AI 戴上氧气面罩**。正如飞机安全指引中要求乘客在协助儿童前先为自己佩戴氧气面罩一样，工程师必须在指挥 AI 开发新功能之前，先为 AI 建立健全的自服务与验证环境。这意味着我们要专注于优化代码库的易读性、编写辅助 AI 的 CLI、接入 MCP（Model Context Protocol）协议，甚至重新设计产品接口。例如：
* **量身定制的表征**: 如果你在 Unity 中开发 3D 游戏，可以为 AI 生成一个 ASCII 码的 3D 世界二维投影，使其更易于理解空间状态；
* **简化的权限流**: 为 AI 模拟极其方便的、具备多角色登录的测试环境；
* **启发式“坏味道”审查**: 引导 AI 审查自身的操作日志，识别诸如在测试脚本中滥用 `sleep(15)` 这样暗示着设计缺陷的**代码坏味道**（Code Smell: 代码中暗示可能存在更深层次设计或实现缺陷的表征特征）。

尽管在前期为 AI 构建这些工具链会略微拉低当前的开发速度，但一旦你开始规模化部署多个 AI 代理并让它们长时间自主运转，这种基础设施层面的投资将会带来呈指数级增长的回报。

<details>
<summary>Original English</summary>

It's maybe without that the agent is able to still have good intuition and fix the issues. But I don't trust it and then I'm going to have to go and verify it myself and I'm wasting time and I cannot then take that agent and start running it overnight for instance. This is a first step to trust. And the point of this is not Spoolside. It's not something you're going to find on GitHub to use for yourself. It's to build your own. I think as engineers, that's our new role. We are going to have to focus less on the product and more on trying to make the AI work on the product. How can we make it easy for it? That can be those tools. That can be improving the code base so that it's easier to work on. That can be improving knowledge bases. You can implement this as a CLI, as a skill, as an MCP. In my case, it's a CLI cuz I like things simple. But like there are many different variations of it and I think it's going to be different from people to people and problem to problem. But yeah, I think in 2025, we had product engineers that were, you know, like very focused on doing everything with the product. But now that AI is getting quite good, you want to focus more on making sure that that velocity is not a trap, that you're not going to multiply errors or compound errors, that you're going to actually verify what you're doing, making it easy for you to to verify as well with like presenting the work that the AI done and everything around that. And so I think we're all going to become AIX engineers essentially. And yeah, it's a bit like when you're in an airline and they say, oh, you put your mask on yourself before you fit you put your your mask on your children. It's the same with AI. You need to put the mask on the AI. You need to make sure that it's self-served before you try to work on features. Even if it slows you down right now, it's an investment that pays off as soon as you start multiplying agents and running things over time. And that's me done with two minutes to spares. So thank you very much. Any question from anybody? Yes. I think they're quite ephemeral in the sense and that I guess is a personal preference. But I do feel like automated test can be sometimes a bit too rigid and hard to predict and hard to like work over time. So I like something that mimics the way I would test it like a human would go and test the application. The way I find those is in the first stage where I work with the AI, I try even though, you know, like I can see that the button is a bit to the left and I want to tell the AI that. What I want is the AI to realize that by itself. So whenever I encounter that sort of problem, I take a step back and try to think on how to make the AI realize the problem by itself. Another thing is re-attractive loop. After you've done that many times, look past over your logs, ask an AI, did you notice any issues, any any any stink? Are you doing sleep for instance? Calling sleep parentheses 15 everywhere is a stink that like there is something that should be wait for whatever like a comment that could be there. Is there anything that you keep doing over and over like running storybooks? And another thing is really think about like your own product. If you're making, say, a game in Unity, like do you want an ASCII representation of your 3D world in for for your AI? If you're making something with lots of permissions, different logins that your AI can take very easily. It's it's really your new role to think about all that. That's what I think anyway. And I think we're it for time. Thank you very much.

</details>