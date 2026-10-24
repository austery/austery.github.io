---
author: AI Engineer
date: '2026-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=XZ0boOjtbNo
speaker: AI Engineer
tags:
  - agentic-web
  - web-development
  - browser-ai
  - coding-agents
  - performance-optimization
title: AI未终结Web，而是与Web共生共荣
summary: 本次会议探讨了AI创新如何改变Web开发，从AI编码代理、调试工具集成、浏览器内置AI API到代理化Web应用。演讲者展示了AI如何通过技能实现自动化编码工作流、通过Chrome DevTools MCP控制浏览器进行性能分析，以及如何利用Web AI API在本地浏览器进行文本摘要、校对和多模态Prompt交互。最后，他们讨论了LLM.txt和Web MCP等新提案，旨在优化网站以适应未来的AI代理浏览，强调了Web开发者需要适应这一新趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Microsoft
  - AWS
  - OpenAI
  - W3C
products_models:
  - Angular
  - Playwright CLI
  - GitHub CLI
  - Chrome DevTools MCP
  - Telegram
  - ChatGPT
  - Gemini
media_books: []
status: evergreen
---
### 引言：AI重塑Web开发

**Yohan**: 大家好，欢迎来到本次会议，我们将讨论Web以及近期**AI创新**如何改变我们Web开发者。

<details>
<summary>Original English</summary>

**Yohan**: Hey folks, welcome to this session where we'll discuss a bit about the web and what the recent AI innovation change for us as web developers.
</details>

**Yohan**: 我叫**Yohan**，在**Microsoft**担任开发者布道师，也是**Angular**的GDE。今天我和**Olivier**在一起。

<details>
<summary>Original English</summary>

**Yohan**: So, let's take just some time for a quick presentation. So, my name is Yohan. I work as a developer advocate at Microsoft. I'm also a GDE for Angular and I'm today with Olivier.
</details>

**Olivier**: 我是**Olivier**，**AWS**的开发者布道师，我也是GDE，但这次是Web方面的。

<details>
<summary>Original English</summary>

**Olivier**: Yeah, I'm Olivier, my developer advocate at AWS and I'm also a GDE, but this time on web.
</details>

**Yohan**: 所以，毫无疑问，我们将讨论AI，更具体地说，在过去的6个月里，**模型质量**的提升改变了Web开发者的游戏规则。不仅是模型本身，还有围绕模型的所有**集成**。AI现在渗透到我们Web应用生命周期的每个阶段。当然包括开发，但也包括调试、性能改进，以及原生集成到浏览器中。

<details>
<summary>Original English</summary>

**Yohan**: So, no surprise here. We'll talk about AI and more specifically, in the last 6 months, the rising quality of the models have kind of changed the game for web developers. And it's not just the models, it's also the integrations all around it. So, AI is now there at every stage of the life cycle of our web apps. For development, of course, but also for debugging, improving the performance, natively also integrated in the browsers.
</details>

**Yohan**: 甚至作为**代理**，越来越多地被看到与人类一起使用我们的Web应用。这也意味着我们必须为此调整我们的Web应用程序。

<details>
<summary>Original English</summary>

**Yohan**: And even coming full cycle as agents increasingly seen using our web apps along humans. That also means that we have to adapt our web applications for it.
</details>

**Yohan**: 所以，今天的计划是涵盖所有这些不同阶段的最新进展：编码，当然还有使用新的**本地AI API**调试和调整我们的应用程序，这些API已经开始出现在我们的浏览器中。最后，**Olivier**将向我们展示如何将您的Web应用升级到新的**代理化Web应用时代**。

<details>
<summary>Original English</summary>

**Yohan**: So, the plan for today is to cover some of the latest progress in all these different stages. Coding, of course, but also debugging and tuning our applications using the new local AI APIs that have started to appear in our browsers. And finally, Olivier will show us how to upgrade your web apps for the new agentic web app era.
</details>

### AI编码代理与技能

**Yohan**: 这是预告。现在是2026年。问题不再是我能否用AI编写Web应用，而是如何从**AI编码代理**那里获得最佳结果。

<details>
<summary>Original English</summary>

**Yohan**: For the teaser. So, it's 2026. It's no longer no longer the question of can I code my web app with AI, but rather how to get the best results out of AI coding agents.
</details>

**Yohan**: 我偶尔仍然听到一些人争论他们无法从AI那里获得好的结果，或者他们向编码代理提问时，结果从未完全如他们所愿。

<details>
<summary>Original English</summary>

**Yohan**: I still hear some folks arguing from time to time that they can't get good results with AI. Or it's never exactly as they want it when they're asking their coding agents.
</details>

**Yohan**: 事实是，今天这主要取决于**技能**。但别误会，这里指的是你安装并与你喜欢的**代码代理**一起使用的那种技能。

<details>
<summary>Original English</summary>

**Yohan**: The truth is that today it's mainly a matter of skills. But don't get me wrong. It's the one that you install and use with your favorite code agent.
</details>

**Yohan**: 如果你从未使用过它们，**技能**是轻量级的插件，以文本格式描述，基于开放规范，目前大多数编码代理都支持。

<details>
<summary>Original English</summary>

**Yohan**: So, if you've never used them, skills are lightweight plugins described in text format based on an open specification that's supported by most coding agents nowadays.
</details>

**Yohan**: 主要用于为你的特定用例、你正在开发的东西添加**领域专业知识**，为你的代理添加内置功能不具备的**新功能**。我们稍后会详细了解，特别是你需要自定义它的时候。

<details>
<summary>Original English</summary>

**Yohan**: Basically, it's useful for adding domain expertise for something very specifically to your use case, to what you're developing. New capabilities that are not built in into your agents. We'll see a bit more about that, especially if you need to customize it.
</details>

**Yohan**: 在这个**代理式代码代理时代**，还有一点非常重要，那就是进行可重复的工作流。所以我们现在会快速演示一下它对你的意义。

<details>
<summary>Original English</summary>

**Yohan**: And also something very important in this agentic code agents era, it's to do some repeatable workflows. So, we'll see just a quick demo now of what it matters to you.
</details>

### 自动化编码工作流演示

**Yohan**: 切换到我的**VS Code**。我们先从一个非常简单的东西开始。实际上，在演示代码之前，我先向大家展示一个我们构建的示例应用程序，我们今天的大部分演示都会使用它。

<details>
<summary>Original English</summary>

**Yohan**: So, moving up to my VS Code. So, let's just start something very simple. Actually, before just moving the code, let's just show you an example application that we've built that we'll use for most of our demo today.
</details>

**Yohan**: 这是**Seine**，一条法国河流的名字。我们有一个电商网站作为例子。这里有一个产品页面，包含描述、评论，可以添加你的评论。

<details>
<summary>Original English</summary>

**Yohan**: So, it's Seine. It's a name of a French river. Just to have like some e-commerce website as an example. Here we have like a product page with a description, some reviews, possibility to add your reviews. Just like having some example for all our demos.
</details>

**Yohan**: 在这个产品中，我想添加一些新内容。所以，我们尝试一个非常简单的提示。我只是要求查看仓库中的**开放问题**，并要求我的编码代理实现第一个。

<details>
<summary>Original English</summary>

**Yohan**: And in this product, I would like to add something new. So, let's just try a very simple prompt. What I'm asking is just to look at open issues in the repo and I'm asking my coding agents to implement the first one.
</details>

**Yohan**: 这会花费一些时间。所以在此期间，我会向你展示幕后发生的事情。你可以看到，我没有特别指定使用什么工具。它已经在尝试运行**GitHub CLI**。

<details>
<summary>Original English</summary>

**Yohan**: So, it will take a quite some time. So, meanwhile, I will have to show you what will happen behind the wood. Just as you can see, I not specifically asked what to use. You can see it's already trying to run the GitHub CLI.
</details>

**Yohan**: 让我们来看看**GitHub**。这个应用程序的仓库中，我创建了一个问题，就是要添加**联系页面**。我描述了我想在这个联系页面中看到什么。当我要求实现第一个开放问题时，它使用了**GitHub CLI**来获取信息，现在正在尝试实现它。

<details>
<summary>Original English</summary>

**Yohan**: Let's move on to show you GitHub. So, basically, this is the repo for this application. I've created one issue that is to add contact page. So, I'm just describing what I want to see in this contact page for my website. And basically, when I ask to implement the first open issue, it has used the GitHub CLI to pull that information and now it's trying to implement that.
</details>

**Yohan**: 我提到了技能。如果我查看仓库中的`.agent/skills`文件夹，可以看到我有几个技能。你已经看到它使用了**GitHub CLI**来访问问题。

<details>
<summary>Original English</summary>

**Yohan**: So, I mentioned skills. So, if I look into my repo inside the .agent/skills folder, you can see that I have a few ones. And you've seen already that it has used the GitHub CLI to access the issues.
</details>

**Yohan**: 这就是实现该功能的技能。我之前已经知道它已经可用了。如果你查看`skill.md`文件，可以看到每个技能都有一个名称，基本上与文件夹名称匹配。它有一个描述。

<details>
<summary>Original English</summary>

**Yohan**: So, this is the skill that implements that. Something I already done know that's already available. If you look into the the skill.md file, you can see that each skill has a name basically matching what you have for the folder name. It has a description.
</details>

**Yohan**: 这是重要部分，技能并非总是加载到你的编码代理中。它是根据实现当前任务所需的条件拉取的。所以描述是为了向你的代码代理解释何时有用，以及你的代码代理何时需要从技能中获取信息到其上下文中。然后你有一个技能的信息，解释**GitHub CLI**的功能，有很多示例命令，并告诉你的代理如何使用它。

<details>
<summary>Original English</summary>

**Yohan**: That's the important part where basically skills are not always loaded into your coding agents. It's basically pulled depending of what's needed to implement the current task. So, the description is there to explain your code agents when it's useful and when your code agents needs to get the information from the skill into its context. And then you have basically the the information for the skill explaining what the GitHub CLI does with a lot of examples command and telling your agent how to use that one.
</details>

**Yohan**: 所以，你可以看到我的仓库中有几个技能。例如，我有一个技能可以更好地进行**前端设计**。这对于我们Web开发者来说很重要。我还有一个技能可以让你使用**Playwright CLI**。

<details>
<summary>Original English</summary>

**Yohan**: So, you can see that I have a few skills here in my repo. I have for example one that's allows to do better front-end design. Something important for us as web developers. I have one that allows to use the Playwright CLI.
</details>

**Yohan**: 例如，你稍后会看到它会录制功能的视频。我用**skill creator skill**也构建了一些自定义技能。所以，你可以通过一个技能来帮助你自定义和构建自己的技能。我实际构建了两个。一个叫做**public tunnel**。

<details>
<summary>Original English</summary>

**Yohan**: For example, you can see that you can see later that it will record a video of the feature, hopefully. I've built also a few custom skills using the skill creator skill. So, yes, you you have a skill that I can help you customize and build your own. And I've built two, actually. One that's called public tunnel
</details>

**Yohan**: 我希望当编码代理实现一个功能时，我能在我的智能手机上测试它。为此，我需要一个在我的开发机和智能手机之间的本地隧道。为了简化，我希望能够直接在我的智能手机上接收URL。所以我构建了这个**Telegram**发送技能，并要求代理向我发送带有URL的消息，这样我就可以直接在智能手机上测试应用程序。

<details>
<summary>Original English</summary>

**Yohan**: that can help send to me what I wanted is basically when a feature is implemented by the coding agent, I want to be able to test it on my smartphone. And to be able to do that, I need like a local tunnel between my dev machine and the smartphone. And to make things easier, I want to be able to receive the URL directly on my smartphone. So, I've built this Telegram send skill and I've asked the agents to send me a message with the URL so I can test the application directly on my smartphone.
</details>

**Yohan**: 这就是我的工作流，它都通过技能运行。我在这里的`agents.md`文件中描述了我的解释，这是一个现在几乎所有编码代理都使用的标准文件。我只是在其中规定，每当代理对网站进行新的更改时，我希望它录制一个短视频。

<details>
<summary>Original English</summary>

**Yohan**: So, this is my workflow and it all works through skills. And basically, what I explain is just described here in my agents.md file, which is a standard file now that is used by almost all coding agents. And I just put in there that every time the agent make a new change to the website, I want it to record a short video.
</details>

**Yohan**: 所以，它将使用**Playwright CLI**来完成，运行开发服务器，创建一个**本地隧道**，并通过**Telegram**发送URL给我。并且，除非我确认完成，否则不要关闭**GitHub issue**。

<details>
<summary>Original English</summary>

**Yohan**: So, it will use the Playwright CLI to do that, run the dev server, create a local tunnel and send me the URL Telegram. And basically, don't close the GitHub issue until I confirm it's done.
</details>

**Yohan**: 它仍在运行。我看到它已经运行了**Playwright CLI**。它正在创建隧道。所以，当它工作时，我会向你展示通知。现在回到幻灯片。结束后我会向你展示。现在交给**Olivier**。我把话筒交给你，展示代理开发的下一步。

<details>
<summary>Original English</summary>

**Yohan**: So, it's still running. I can see that it's it has already run the Playwright CLI. It's moving on to creating the tunnel. So, I will show you the notification when it will be working. Back to the slides right now. I'll show you when it's when it's ended. Now, moving on to Olivier. I leave you the hand to to show you the next step in the development with agents.
</details>

### 利用代理控制浏览器开发工具

**Olivier**: 是的，让我们看看如何使用代理来开发我们的应用程序。现在，你们大多数人已经这样做过了。你可以编写测试来测试你的应用程序。

<details>
<summary>Original English</summary>

**Olivier**: Yes, let's see how we can use agents to develop our application. So, right now, most of you already do this. You can write test to test your application.
</details>

**Olivier**: 或者你可以做很多人会做的事情，你访问网站，进入开发者工具，然后尝试让它工作。

<details>
<summary>Original English</summary>

**Olivier**: And or you can do what more like a lot of people do, you know, you go on the websites, you go in the dev tools and you try to, you know, make it work and everything.
</details>

**Olivier**: 重点是，**Chrome**的开发者工具非常棒。你可以做很多事情。你可以查看控制台问题、动画、计算布局、获取性能。你可以在这里访问所有这些工具。

<details>
<summary>Original English</summary>

**Olivier**: Thing is, on Chrome, the Chrome dev tools are amazing. There's like so many things you can do. You can console issues, animation, the computer layout, you get the performance. You have access to all these tools here.
</details>

**Olivier**: 如果有一个**MCP**可以做到这一点，那就太棒了。就像代理可以调用它一样。这正是**Chrome MCP**所做的事情。

<details>
<summary>Original English</summary>

**Olivier**: It would be amazing if an MCP existed for that. Like an agent can call it. That's what exactly what the Chrome MCP does.
</details>

**Olivier**: 如果你访问**GitHub Chrome DevTool MCP**，你可以在这里找到如何安装它的信息。

<details>
<summary>Original English</summary>

**Olivier**: If you go on the on the GitHub Chrome dev tool MCP here, you have the information on how to install it.
</details>

**Olivier**: **MCP服务器**基本上是一个托管工具的服务器，这些工具可以被你的代理调用。在任何IDE、CLI或你用于代理的任何工具中设置它都非常容易。这就是你需要安装**Chrome DevTools MCP**的方法。

<details>
<summary>Original English</summary>

**Olivier**: Basically, an MCP server is a server that hosts tools that can be called by your agent. And it's very easy to set up on any IDE, any CLI, whatever you use for your agents. And so, this is what you have to put to install the Chrome dev tools MCP.
</details>

**Olivier**: 所以，我在这里完成了。如果我查看我的`MCP.json`，我有我的**Chrome DevTool MCP**。你可以在我的IDE中看到它，并且它有权访问所有这些工具。

<details>
<summary>Original English</summary>

**Olivier**: So, that's what I've done here. If I go to my MCP.json, I have my Chrome dev tool MCP. And you can see that in my IDE here, I have it and it has access to all these tools.
</details>

**Olivier**: 所以，我在**Chrome DevTools**或浏览器中可以做的所有事情，我都可以从这里完成。比如点击、填写表单、获取控制台消息、网络请求、**Lighthouse审计**、页面导航、截图、调整页面大小等等。我可以在这里做所有事情。

<details>
<summary>Original English</summary>

**Olivier**: So, everything I can do in the Chrome dev tools or in the browser, I can do it here. Like click, fill form, get get console message, the network request, the Lighthouse audit, navigate page, take screenshot, everything. Resize page and everything. So, I can do everything from here.
</details>

**Olivier**: 所以，比如说，我有我的代理。如果我打开我的代理窗口，我问：“好的，你知道吗？你能运行应用程序，看看主页在**Chrome浏览器**中如何工作吗？” 如果我这样做，并打开我的开发工具，如果我这样做，它会看到`agent.md`等等。

<details>
<summary>Original English</summary>

**Olivier**: So, let's say for example, I have my my agent here. If I open my agent window and I ask, "Okay, you know what? Can you run the application and see how the main page works in Chrome browser?" So, if I do that and you open my dev my tool here, if I do that, okay, it's going to see the agent.md and everything.
</details>

**Olivier**: 但接着它会说：“好的，要运行应用程序，我需要启动它。” 所以它会查看我的`package.json`。这只是基本引擎在做它们的工作。它会打开一个新终端。

<details>
<summary>Original English</summary>

**Olivier**: But then he's going to say, "Okay, to run the application, I need to start it." So, it's going to have a look at my package.json. That's just like basic engine doing their job. It's opening a new terminal.
</details>

**Olivier**: 它正在运行应用程序。现在为了测试，它需要打开一个**Chrome**。这就是它将调用**NCP工具**的时候。它会说：“好的，我可以导航到一个页面。我可以列出页面。” 我知道它正在打开**Chrome**。我没有碰任何东西。你可以看到，**Chrome**正在被自动化测试软件控制。

<details>
<summary>Original English</summary>

**Olivier**: It's running the application. And now to test it, it's going to need to open a Chrome. And that's when it's going to call the the NCP tool here. Uh so, it's going to say, "Okay, I can navigate to a page. I can list the page." I know it's opening Chrome. I haven't touched anything. You can see like it's Chrome being controlled by automatic test software.
</details>

**Olivier**: 所以，现在它打开了**Chrome**并正在测试。我可以运行或测试。现在我看看它是否能截一些图。我的提示非常非常基础。我只是问：“你能测试主页吗？” 所以它去了那里，截了图并列出了它。

<details>
<summary>Original English</summary>

**Olivier**: So, now it opened the Chrome and it's going to test it. So, I can either like run or test. Now, it I see if it can take some screenshots. So, here my prompt was very very basic. I just asked, "Can you test the main page?" And so, it's going there. It's taking a screenshot and listing it.
</details>

**Olivier**: 然后你可以做任何你想做的事情。你可以说：“好的，你知道吗？我想做其他事情。我想，好的，我们关掉它。” 因为我不再需要它了。

<details>
<summary>Original English</summary>

**Olivier**: Then you can do everything you want. You can say, "Okay, you know what? I want to do something else. I want to Okay, let's let's kill it." Cuz I don't need it anymore here.
</details>

**Olivier**: 我可以说：“你知道吗？我们打开一个新窗口。” 说：“你知道吗？用3G，2G和快速互联网网络运行应用程序，看看应用程序的性能如何，以及它在哪里变慢。” 所以现在目标是控制**Chrome DevTools**，包括网络和性能工具。

<details>
<summary>Original English</summary>

**Olivier**: I can say, "You know what? Let's open a new window." Say, "You know what? Run the application in 3G, 2G, and fast internet network and see how the application performance is and where it slows down." So, now the goal is to control the Chrome DevTools and including the network one and the performance one.
</details>

**Olivier**: 这个提示非常基础。所以你可以更具体一些。我们给它一分钟看看会发生什么。有时我没有要求它，但它会生成截图或**JSON文件**形式的报告。

<details>
<summary>Original English</summary>

**Olivier**: Uh again, this prompt is very basic. So, you can be way more uh specific. Let it Let's give it a minute to see what it's going to go through. Sometimes also I didn't ask for it, but sometimes it will also like generate like screenshots or like JSON files here of reports.
</details>

**Olivier**: 好的。它正在启动应用程序。好的，它正在导航。现在你可以看到，测试一。它将使用`no`或`true`的性能跟踪启动，在快速互联网无节流的情况下进行测试。这很好。

<details>
<summary>Original English</summary>

**Olivier**: Um Okay. Okay, it's launching the application. Okay, it's navigating on it. And now you can see that Okay, test one. It's going to use like a no or true that performance start trace to test it on Okay, fast internet no throttling first. That's good.
</details>

**Olivier**: 它捕获了基线。现在正在进行性能分析。你可以看到，每次你调用工具时，你都能看到它调用的工具是详情。现在它在快速3G上测试。记住，我要求了三次测试，三种不同的连接速度。

<details>
<summary>Original English</summary>

**Olivier**: Um it captured the baseline. Now, it's doing some performance analysis. You can see that every time you call the tool, you can see the tool it calls is the uh the the details. So, now it tests on fast 3G. Remember, I asked like three tests, three different um connection speed.
</details>

**Olivier**: 再给它一分钟。它模拟了性能跟踪启动。好的，它有了。性能分析。然后它将进行最后一次。希望能成功。

<details>
<summary>Original English</summary>

**Olivier**: And let's see. Give it another minute. It emulates performance start trace. Okay, it has it. Performance analysis. And then it's going to do the last one. Hopefully, okay.
</details>

**Olivier**: 好的，让我们看看它是否会在最后生成一份测试报告。有时会，有时不会。这取决于情况。我没有要求一份，所以我们看看它会拿出什么。

<details>
<summary>Original English</summary>

**Olivier**: Okay, let's see if it's going to generate a test like a report at the end. Sometimes it does, sometimes it doesn't. It depends. I haven't asked for one, so let's see what it came up with.
</details>

**Olivier**: 好的。我的窗口还在。它没有打开**Chrome DevTools**，但它在后台使用了工具。正在进行一些性能分析。

<details>
<summary>Original English</summary>

**Olivier**: Okay. And I still have my window here. You don't It doesn't open the Chrome DevTools, but it's using the the tool in the background. Doing some performance analysis.
</details>

**Olivier**: 好的。**LSP图像**和**Stanley**大小。好的。我们给它几秒钟看看它在做什么。它正在检查图像。所以它可能已经注意到图像有些可以优化的地方。它正在检查图像的大小。

<details>
<summary>Original English</summary>

**Olivier**: Okay. LSP image and Stanley size. Okay. Okay, let's give it like just a few seconds to see uh what it's doing. It's checking the images. So, it must have noticed that there's something we can optimize with the with the image, I guess. So, it's checking the the size of it.
</details>

**Olivier**: 它正在分析代码。好的。通常它不会深入到分析代码。所以，我给它15秒。如果它继续，好的，现在完成了。你可以看到它分析了所有内容，并且可以给你所有这些报告，说：“好的，对于每种互联网连接速度，我都有**LCP**、**CLS**、**关键路径延迟**和**随机阻塞节省**。”

<details>
<summary>Original English</summary>

**Olivier**: Um it's analyzing the code. Okay. Usually, it doesn't go that far as analyzing code. So, let's I'm going to give it like 15 seconds. If it continues Okay, now it's done. Okay, you can see that it analyzed everything and it can give you all like a these reports saying, "Okay, for every internet connection speed, I have the LCP, the CLS, the critical path latency, and the random blocking saving."
</details>

**Olivier**: 然后它给你一些指导方针。所以**耳机图片**太大了，通过3G不好。它给你改进的方法。你可以设置高优先级。你有**CSS**的大小和**JavaScript**中的一些问题。你可以为一些**JSON**设置预加载。所以你拥有所有这些可以用来改进你的应用程序的东西。

<details>
<summary>Original English</summary>

**Olivier**: And then it gives you some like guidelines. So, the headphone image is too big, so it don't through 3G is not good. It's giving you ways of improving it. So, you can put a place priority high. You have the size of CSS and some issues in the JavaScript. You can put some like preload for some JSON. So, you have all these that you you can play with them to improve your your application.
</details>

**Olivier**: Yann，你收到通知和演示的最新消息了吗？我们看看。

<details>
<summary>Original English</summary>

**Olivier**: Yann, does it Do you have any any news on your your notification and demo? Uh let's have a look.
</details>

**Yohan**: 是的，我什么都没收到。我们可以检查一下。有时代理会卡住。它失败了，因为它找不到，哦，**token**。是的，我有一个数据文件。我不确定为什么有时它找不到。我有一个数据文件。

<details>
<summary>Original English</summary>

**Yohan**: Yeah, I did not receive anything. We can check. Sometimes the agent gets stuck. Uh it failed because it couldn't find Oh, the token. Yes, I have a data file. I'm not sure why sometimes it failed to to find it. I have a data file.
</details>

**Yohan**: 用它，让我试试。

<details>
<summary>Original English</summary>

**Yohan**: Use it and let me try.
</details>

**Yohan**: 是的。有时代理并不总是能正常工作，尤其是在演示期间。你们都知道。**alpha**是你的消息应用程序，它知道使用哪个频道向我发送**Telegram消息**。所以，是的。好的。我们继续，稍后再回来讨论，好吗？哦，它只是在告诉。

<details>
<summary>Original English</summary>

**Yohan**: Yeah. Sometimes agents not always working, especially during demos. You know that. The alpha is for your um the messaging application like uh Yeah, so so it it knows which channel to use to send me the the Telegram message. So, yeah. Okay. Well, let's let's let's continue and we'll come back to that later, okay? Oh, and there goes just telling it.
</details>

**Yohan**: 所以，让我尝试向你展示。是的，我在智能手机上收到了通知。所以，是的，我们会打开它，这样你就可以看到。是的，你可以看到。

<details>
<summary>Original English</summary>

**Yohan**: Uh so, let me try to show it to you. So, yeah, I received the notification I don't Yeah. I received the notification on my smartphone. So, yeah, we'll open it just so you can have a look. So, yeah, you can see
</details>

**Yohan**: 尝试聚焦。是的，你可以在这里看到录制的功能视频的预览。我将打开链接。所以我们可以看到它制作的**联系页面**的样子。是的，这看起来是一个很棒的联系页面。

<details>
<summary>Original English</summary>

**Yohan**: trying to focus in there. Yeah, can see here preview of the video uh showing the feature it recorded. I will open the link. So, we can see the look of the contact page it did. And yeah, this looks like a great contact page.
</details>

**Yohan**: 是的，我也可以向你展示，因为它正在运行。所以你可以看到现在我们有了这个**联系页面**。所以，是的，它基本上已经完成了，我可以直接测试并查看视频。这是一个非常简单的功能，但可以看到它对于更复杂的功能为什么有用，基本上允许你直接从智能手机上审核所有内容，甚至无需运行任何东西，只需查看视频就能测试。

<details>
<summary>Original English</summary>

**Yohan**: So, yeah, I can also show it to you since I have uh I have it running in there. So, you can see now we have this uh contact page. So, yeah, basically done the thing and I can just test it and have a look at the video. So, this was very simple feature, but can see the why can be useful for more complex feature and basically allow you to review everything directly from your smartphone and even without having to run anything in the case of looking at the video just to be able to test it.
</details>

**Yohan**: 如果你想发送它，我用**Telegram**发送给了自己，但你可以使用**Slack**发送给你的同事，或者任何你能想到的东西。这是你的工作流。是的，这非常棒。

<details>
<summary>Original English</summary>

**Yohan**: Uh if you want to send it, I've sent it to myself using a Telegram, but you can uh for example, use Slack to send it to your coworkers or anything else that you can imagine. It's your workflows. So, Yeah, it's pretty awesome, actually.
</details>

### 浏览器内置AI能力

**Yohan**: 接下来是另一个很棒的东西。我们已经看到，**Olivier**展示了你的开发者工具可以通过**MCP**直接被代理控制。但是你知道你也可以直接在浏览器开发者工具中使用AI吗？

<details>
<summary>Original English</summary>

**Yohan**: Moving on to the next uh nice thing. Uh we've seen that uh with Olivier, your dev your dev tools can be controlled directly by agents through MCP. Uh but do you know also that uh you can use AI directly into your browser dev tools?
</details>

**Yohan**: 你可以直接从浏览器中获得各种见解，帮助你诊断和修复问题。是的，与其描述所有这些功能，不如我直接向你展示。

<details>
<summary>Original English</summary>

**Yohan**: Uh you can get all sorts of insight directly uh from there, from your browser to help you diagnose and fix issues. And uh yeah, instead of just describing any all the kind of things that you can do, let me just show you actually.
</details>

**Yohan**: 回到网站。我们以“关于”页面为例。我们打开开发者工具。我们可以看到有一个错误。

<details>
<summary>Original English</summary>

**Yohan**: So, moving back to the website, uh we'll move on to the about page, for example. Let's open the dev tools. So, we can see that we have an error.
</details>

**Yohan**: 所以，首先，如果你想获得所有新的有用的AI功能，你必须进入开发者工具设置，并确保在**AI创新选项卡**下启用了任何功能。它默认未启用。如果你想获得这种AI辅助，你必须自己动手。

<details>
<summary>Original English</summary>

**Yohan**: So, first thing, if you want to have like all the new useful AI stuff, you have to go to the dev tools settings and make sure that under the AI innovation tab, you have uh enabled anything. So, it's not uh enabled by default. You have to do that yourself if you want to get this AI assistance.
</details>

**Yohan**: 一旦你完成了，例如，在这里，你可以看到我有一个常见的控制台错误，说有一些请求被**CORS策略**阻止了。你可以看到这个小图标。我可以直接点击它，使用AI获取关于这个错误的解释，甚至是一个建议的修复方案，说明这个错误发生的原因以及如何修复它。

<details>
<summary>Original English</summary>

**Yohan**: And once you have done that, for example, here uh you can see that I have like uh uh common error in the console saying that yeah, I have some requests have been blocked by CORS policy. And you can see this uh this little icon in there. I can directly click on it to get an explanation uh uh using AI about this error and even a suggested fix why this error happens and what to do to fix that.
</details>

**Yohan**: 所以，直接在你的控制台中，你无需复制粘贴错误，使用你的编码引擎或**ChatGPT**，它直接在你的开发者工具中。是的，你可以看到它非常全面，并为你提供了各种提示来尝试解决问题。

<details>
<summary>Original English</summary>

**Yohan**: So, directly in your console, you don't have to like copy paste errors uh using that and your coding engines or ChatGPT depending on whatever you're using. It's directly in there inside your dev tools. And uh yeah, you can see it's pretty extensive uh and giving you all sorts of hints uh to try to fix the issue.
</details>

**Yohan**: 所以，我们尝试看看它在其他地方是否有用，例如在网络选项卡中。我们重新加载页面。你可以看到其中一个失败的请求，它有400个错误。同样，我们有这个**“使用AI调试”图标**。所以我点击它。

<details>
<summary>Original English</summary>

**Yohan**: So, let's try to to see where else it can be useful, for example, in the network tab. Let's reload the page. Uh you can see one of the failing request that has like 400 errors. Again, uh we have this debug with AI icon. So, I will click on it
</details>

**Yohan**: 就可以看到我的失败请求已添加到这个聊天界面中。例如，我可以问：为什么请求失败了？

<details>
<summary>Original English</summary>

**Yohan**: and uh just can see that my failing request has been added to this uh chat interface thing. And I can, for example, ask why is the request failing?
</details>

**Yohan**: 所以，我有一个内置的**AI聊天**，它可以直接从开发者工具访问我正在运行的应用程序的上下文。所以，它正在分析为什么这个请求失败了，并给我一些提示，告诉我可能尝试做什么来修复它。它告诉我这是一个坏请求，很可能是因为这是一个不再存在的旧端点。

<details>
<summary>Original English</summary>

**Yohan**: So, I have a sort of built-in uh chat uh with AI that can directly access uh the context of my running application from directly from the dev tools. So, again, uh it's analyzing why this request is failing and saying uh giving me some hints about what I may try to do to try to to fix that. Okay, telling me it's bad request, most likely because uh that's an old endpoint that's no longer there.
</details>

**Yohan**: 是的，我认为你可以直接在浏览器内的开发者工具中做到这一点很酷。你可以做各种有趣的事情，比如。

<details>
<summary>Original English</summary>

**Yohan**: So, yeah, I think that's kind of cool that you can do directly that uh from your dev tools inside your browser. Can do all sorts of uh other fun stuff like, for example, uh
</details>

**Yohan**: 让我以**GitHub**为例。这会更有意义。我进入性能选项卡。

<details>
<summary>Original English</summary>

**Yohan**: Let me move on, for example, to GitHub. Uh this will be more meaningful with that one. I move on to the performance tab.
</details>

**Yohan**: 所以，这次我点击刷新。它会收集关于网页的一些见解，比如运行不同东西需要多长时间以及一些指标。

<details>
<summary>Original English</summary>

**Yohan**: So, uh this time I will click on the refresh uh in there. So, it will gather some insights about the web page like how long does it take to run the different things and some metrics about it.
</details>

**Yohan**: 所以我有了这个**跟踪**。这与**Olivier**之前使用**MCP开发工具服务器**进行的测试有点相似。例如，我可以打开**LCP细分**。同样，你可以看到我有这个**“询问AI”按钮**。所以，我可以使用我在**GitHub网站**上刚刚录制的跟踪来询问它，帮助我优化我的**LCP分数**。

<details>
<summary>Original English</summary>

**Yohan**: So, I have uh this trace. So, it's a bit similar to kind of the test that Olivier did earlier with the MCP dev tool server. For example, I can open the LCP breakdown. And again, you can you can see that I have this ask AI uh button. So, I can ask it using my trace that I just recorded on the GitHub website to help me optimize uh my LCP score.
</details>

**Yohan**: 运行它，它会分析网站的所有跟踪，并告诉我：“好的，这个页面的**LCP**，即**最大内容绘制**，这次是这样。” 并且基本上造成大部分延迟的原因。哦，我无法看到渲染阻塞问题。有时它更详细，有时不。同样，这是AI。

<details>
<summary>Original English</summary>

**Yohan**: So, running it, it will analyze all trace from the website and telling me, "Okay, the LCP, the largest uh contentful paint for this page is uh okay this time." And uh basically what's causing most of the delay uh because uh it's some stuff and Oh, I can't see uh investigate render blocking issues. Sometimes it's more verbose, sometimes not. Again, uh this is AI.
</details>

**Yohan**: 是的。它可以给我一些提示，告诉我需要优化什么。一直以来，它都告诉我主要是因为**CSS**。是的，如果你不确定从何开始，例如优化网站的性能，你可以获得一些提示。

<details>
<summary>Original English</summary>

**Yohan**: So, yeah. Uh it can tell me uh a few uh hints about what I I need to optimize. Uh all the time it was telling me it was mostly because of CSS and yeah, you can get some hints uh if you're not sure about what to to start with uh for example to optimize the performance on on your website.
</details>

**Yohan**: 但它能做的更多。我们回到我们的网站。这次我选择例如关于发送元素。

<details>
<summary>Original English</summary>

**Yohan**: But it can do more than that. Uh let's go back to our send website. Uh this time I will for example uh select this about send elements.
</details>

**Yohan**: 我在**CSS**中。你可以在这里看到，这是这个**H1**。所以，我正在导航DOM，你可以再次看到我有这个**“AI调试”按钮**。

<details>
<summary>Original English</summary>

**Yohan**: Uh I'm in the CSS. You can see here, this is uh this H1. So, here I'm navigating the DOM and you can see again I have this uh AI debug with AI button.
</details>

**Yohan**: 选择它，你可以看到它将这个特定的**H1元素**添加到了上下文中。我可以问，例如，我想改变这个无聊的标题，让它变成一个漂亮的**渐变**。

<details>
<summary>Original English</summary>

**Yohan**: So, selecting it, you can see that is it has added this specific H1 element in the context. And I can ask thing for example, let's say that uh I want to uh change this boring title and make it a nice gradient. So, I will
</details>

**Yohan**: 我会告诉它让文本**CSS**具有漂亮的渐变，并且我希望它与现有的**颜色主题**保持一致，因为我已经在用一些**CSS变量**了。是的。

<details>
<summary>Original English</summary>

**Yohan**: just tell it to make the send text uh CSS have a nice gradient and I want it to be in line uh with the existing color theme because I'm already using some CSS variables. So, yeah.
</details>

**Yohan**: 好的，我们继续。我同意页面可以修改。是的，你可以看到我有一个非常漂亮的渐变，与我网站中所有其他颜色保持一致。你还可以看到一些更有趣的东西，因为我只是实时修改了网页中的**CSS**，但更有用的是直接修改源代码，因为我在这里做的只是非永久性的更改。

<details>
<summary>Original English</summary>

**Yohan**: So, let's continue. I agree that uh the page can be modified. And yeah, you can see that I have very nice gradients uh in line with all the other colors that I have in my my website. And you can see even more something uh interesting cuz from there I just modified uh the the CSS live in the web page, but what could be more useful is to directly modify the source code because here I'm just making non-permanent uh changes.
</details>

**Yohan**: 所以，你可以在那里看到我有这个**未保存的更改选项卡**，其中包含添加到我网页的**CSS**。我可以尝试使用**“应用到工作区”**直接将该更改应用到我的代码。它基本上会要求你将源代码文件夹添加到开发者工具。它将允许开发者工具直接将**CSS修改**应用回你的源代码文件。所以，它现在不仅能够对你的DOM、CSS和JavaScript进行实时修改，

<details>
<summary>Original English</summary>

**Yohan**: So, you can see that I have this unsaved change uh tab in there with uh the CSS that was added to my web page. I can try to apply that change directly uh to my uh code using apply to workspace. What it will ask you basically is to add your source folder uh to the dev tools. And uh it will allow uh the the dev tools to directly do this uh CSS modification back to your source code file. So, it will it's now uh not only able to to do like live modification on your DOM CSS and JavaScript,
</details>

**Yohan**: 还能将这些更改应用回你的原始源代码。所以我认为这非常有趣，尤其是作为Web开发者，我大部分时间都在与**CSS**作斗争。是吧，**Olivier**？

<details>
<summary>Original English</summary>

**Yohan**: but also uh able to uh apply back that changes uh back to to your original source code. So, I think this is very interesting uh especially as uh yeah, as a web developer, I tend to fight with CSS most of the time. Right, Olivier?
</details>

**Olivier**: [笑声]

<details>
<summary>Original English</summary>

**Olivier**: [laughter]
</details>

**Olivier**: 是的，在你对**Chrome开发工具**进行大量更改后，你就不记得哪一行需要复制粘贴到你的**CSS文件**中，然后你会觉得：“我再也找不到了。” 因为它无论如何都会刷新。我们都经历过。

<details>
<summary>Original English</summary>

**Olivier**: Yeah, and after after like you do a lot of changes on the on the Chrome dev tools and then you don't remember which line you had to copy paste on your CSS file and then you're like, "I can't find it again." because then it refreshes anyway. We've all been through that.
</details>

**Olivier**: 是的。我发现那非常有趣。此外，它还减少了你在调试或调整**CSS**时，浏览器和编码代理之间有时会发生的反复切换，因为基本上你将所有东西都集中在一个地方。

<details>
<summary>Original English</summary>

**Olivier**: So, yeah. I found that very interesting. Also, it reduces like the back and forth that you can uh have sometimes between like uh your browser when debugging or tweaking the CSS and uh your coding agents because basically you have everything at one place.
</details>

### 浏览器中的本地AI API

**Olivier**: 好的，我们已经看到了如何用AI编写代码，如何调试。现在我们来看看如何在我们的应用程序中包含AI。你可能已经直接使用了**AI提供商**或**云提供商**的一些**AI API**。但这通常需要进行互联网调用，通常需要付费，使用一些**token**等等。

<details>
<summary>Original English</summary>

**Olivier**: So, now Okay, so we we've seen how to code, how to debug with AI. Let's see how we can just include AI in our application. So, uh you may have used some AI APIs either directly from an AI provider, from a cloud provider. Um but that requires uh to make some calls on the internet, uh usually to pay for it, to use some tokens and everything.
</details>

**Olivier**: 好消息是有一个新的**Web AI API**将直接集成到浏览器中。所以现在它仍然处于草案阶段，我想是在**W3C**下。但你可以看到我们有很多不同的API。我们有**摘要API**，我们有**重写API**，我们有**Prompt API**。

<details>
<summary>Original English</summary>

**Olivier**: The good thing is that there's a new um API called like a web AI API that would come directly in the browser. So, now it's like um still in like a draft, I think under the W3C. But you can see that we have a lot of different API. We have some summarize API, we have some like uh write rewrite, um we have the prompt API.
</details>

**Olivier**: 基本上，让我们看看如何在我们的浏览器中使用它。所以目标是让模型直接在我们的机器上，在我们的浏览器中运行。

<details>
<summary>Original English</summary>

**Olivier**: And uh basically, let's see how we can use that in our browser. So, the goal is to have like a model directly running on our machine in our uh browser.
</details>

**Olivier**: 所以，这里我有一个应用程序，你已经在你的终端看到了。我有一些评论，我也可以添加一些评论。你可能已经在一些网站上看到过，它们会给你所有评论的摘要。所以让我们看看如何实现这一点。

<details>
<summary>Original English</summary>

**Olivier**: So, here I have an application that you've seen it from your end. I have some reviews, I can actually add some reviews. And you may have seen that in in some website now that they give you like a summarize of all the reviews. So, let's see how we can implement that.
</details>

**Olivier**: 我会去我的代码。我有三个不同的演示要做。所以第一个是**摘要**。

<details>
<summary>Original English</summary>

**Olivier**: So, I'm going to go to uh here my code. And I have some I have like three different demos that we're going to uh to do. So, the first one is summarize.
</details>

**Olivier**: 所以我希望当我点击这个按钮时，它能给我所有评论的摘要。所以现在它除了调用这个函数外什么也没做。

<details>
<summary>Original English</summary>

**Olivier**: So, I want to when I click on this button he gives me a summarize of all the all the the reviews here. So, right now he's doing nothing except for like calling this function.
</details>

**Olivier**: 所以，我们先检查一下，因为并非所有浏览器都支持这个API。所以我们看看我的浏览器是否有。然后我将创建一个**summarizer**，像`summarizer.create`。

<details>
<summary>Original English</summary>

**Olivier**: So, let's let's start by checking because not all browser manage like um have that API yet. So, let's see if my browser has it. And then I'm going to create a summarizer summarizer like summarizer.create.
</details>

**Olivier**: 然后我将提供一些选项。我给出的选项是类型。这里的类型是**关键点**。这是默认的。如果你查看这里的文档，你可以看到这里有不同的类型。

<details>
<summary>Original English</summary>

**Olivier**: Uh then I'm going to give some options. So, the options I'm giving the type. So, the type here is key point. It's the default one. If you go on the documentation here, you can see that here are the different types you can have.
</details>

**Olivier**: 所以我们有**TLDR**、**预告**、**关键点**、**标题**。对于每一个，你可以设置不同的长度，你也可以看到句子或单词的大小。所以你可以决定使用哪一个。我给出了评论的预期输入语言和预期输出语言。你可以看到这是一个数组，所以你可以有不同的输出和输入。

<details>
<summary>Original English</summary>

**Olivier**: So, we have TLDR, teaser, key points, headline. And for each of them you can do like a different length and you can see the size of sentence or words. So, you can decide which one you want to use. I'm giving the expect input language of my reviews and the expect output language. You can see that this is an array, so you can have different uh several um um output uh input actually.
</details>

**Olivier**: 好的，我将给出上下文。我将说：“好的，这些是关于一篇文章的评论，你以字符串化的**JSON**形式提供。给我一个人们想法的摘要。”

<details>
<summary>Original English</summary>

**Olivier**: Um Okay, I'm going to give the context. I'm going to say like, "Okay, these are reviews um for an article you give uh as a strong stringified JSON. Give me a summary of what people think."
</details>

**Olivier**: 然后我将提供一个监视器。这个`monitor`函数在这里监视模型的下载。所以这个API的工作方式是，它将在你的计算机上下载模型。它只会下载一次，这很好，因为它现在需要4GB。但一旦完成，它对每个网站都完成了。

<details>
<summary>Original English</summary>

**Olivier**: Then I'm going to um Oops. I'm going to give you a monitor. So, this this function monitor is here to monitor the download of the model. So, how this API works is that it's going to download the model on your computer. It's going to download only once, which is good because it takes 4 GB right now. But when it's done, it's done for every website.
</details>

**Olivier**: 如果你的计算机需要存储，如果你的存储空间不足，**Chrome**会删除它，但默认情况下它会保留它。

<details>
<summary>Original English</summary>

**Olivier**: It's if your computer needs uh storage like your your like storage if you're running low, Chrome is going to delete it, but by default it's going to uh keep it.
</details>

**Olivier**: 所以，我有这个监视器，然后我要做的是调用它。所以我将调用`summarizer.summarize`，并向它提供数据。然后，我只是返回**summarizer**。我只是像我在这里将要做的那样返回响应。

<details>
<summary>Original English</summary>

**Olivier**: So, I have this uh monitor and then what I'm going to do is call it. So, I'm going to like summarizer.summarize and giving it the the data and then uh let's return summarizer. I just return the the response as I'm going to do here actually.
</details>

**Olivier**: 好的。现在我们看看这里有什么。回到这里。我点击**摘要**，现在发生的事情是。

<details>
<summary>Original English</summary>

**Olivier**: All right. So, now let's see what we have here. Going back here. I'm going to click on summarize and now what is happening is that
</details>

**Olivier**: 好的，它在说一些关于模型的事情。所以它再次调用了我的函数。它应该在一秒钟内给我。所以你可以看到，模型已经为我下载好了。所以它直接从0%到100%，因为我不需要再次下载。

<details>
<summary>Original English</summary>

**Olivier**: uh okay, saying something about the model. So, it's calling my function again. And it should give me in a second. So, you can see that my the model was already downloaded for me. So, it goes from like 0% to 100% directly because I don't have to download it again.
</details>

**Olivier**: 你可以在这里看到我所有评论的摘要。所以顾客们非常赞扬耳机的音质和电池寿命。等等。

<details>
<summary>Original English</summary>

**Olivier**: You can see here I have a summarize of all my reviews. So, customers are really praising the headphone for their sound quality and battery life. Blah blah blah blah blah.
</details>

**Olivier**: 只有几件事。要让它工作，你必须激活**Chrome**上的一些标志。所以通常搜索AI就能找到它。

<details>
<summary>Original English</summary>

**Olivier**: Few things there. For it to work, you have to activate some of the flags on Chrome. So, just search for AI usually and you're going to find it. So, just for like uh
</details>

**Olivier**: **Gemini**，你有**Prompt API**，**Proofreader API**，你有**Writer API**，**Rewriter**等等。所以只要启用它们，你就可以在你的应用程序中使用它们。

<details>
<summary>Original English</summary>

**Olivier**: Gemini Gemini and have the prompt API, the proofreader API, you have the writer API, the rewriter and everything. So, just enable them so you can use them in your in your application.
</details>

**Olivier**: 在这里，你还在**Chrome**上拥有这些**on-device internals**。所以你可以看到一些东西。你可以加载一个模型或加载声音模型，然后你可以直接与它交谈。你可以添加图像、音频，调整**top K**、**温度**。

<details>
<summary>Original English</summary>

**Olivier**: Uh here you also have these on-device internals on Chrome. So, you can see a few things. You can load a model or load like uh the sound model and then you can just talk to it. You can add images, audio, play with the top K, temperature.
</details>

**Olivier**: 你可以看到所有**事件日志**。这些是我刚刚使用**摘要**功能时产生的事件日志。

<details>
<summary>Original English</summary>

**Olivier**: You can see all the event logs. So, these are the event logs of what I just did with the summarize.
</details>

**Olivier**: 你可以看到模型的状态，每个API调用使用了多少**token**。所以，是的，这是一个很好的调试方法。现在，我们来看看另一个API。我要看看**Proofreader**。

<details>
<summary>Original English</summary>

**Olivier**: Uh you can see the model status of how many tokens have been used for each of the of the calls of the API. So, yeah, this is like a good way to debug. Now, let's see another API. I'm going to see the proofreader.
</details>

**Olivier**: 保存。检查我是否可以访问API。我正在创建一个**proofreader**。所以监视器是一样的。我只是监视它是否下载模型。

<details>
<summary>Original English</summary>

**Olivier**: So, uh save. Checking if I have access to the API. I'm creating a proofreader. So, the monitor is the same. I'm just monitoring if it downloads the uh the the model.
</details>

**Olivier**: 然后我会说：“好的，我将给你一个预期的复杂语言列表。” 好的，在这里我将说，这将是英语，因为我希望你纠正它。

<details>
<summary>Original English</summary>

**Olivier**: Then I'm going to say, "Okay, I'm going to give you a list of expected complex language." Okay, here I'm going to say okay, this is going to be uh English because I want you to correct it.
</details>

**Olivier**: 然后我有这个，我正在调用**proofreader**。并返回**proofreader**。但这对于修复拼写问题很有用。假设我在这里写评论，我只是说“这 是 一个 非常 好 的 文章。” 我将像“lower”一样说。

<details>
<summary>Original English</summary>

**Olivier**: And then I have this uh I'm calling the proofreader. And returning the proofreader. But now this is useful to um to fix like spelling issues. Let's say I have my write review here and I'm just like this is is a very uh good article. I'm going to say like lower.
</details>

**Olivier**: 好的。所以，例如，我正在写这个，如果我离开焦点，你可以看到我正在调用，我正在调用将进行分析的API。你可以看到它纠正了“这是一个非常好的文章”。所以我犯的所有错误，你可以看到它都更改了。

<details>
<summary>Original English</summary>

**Olivier**: Okay. So, for example, I'm writing this and if I leave the focus, you can see here I'm calling the oops, I'm calling the API that's going to take the analysis. You can see that it corrected like this is a very good article. So, all the mistakes I did you can see that it changed them.
</details>

**Olivier**: 实际上，如果我们有时间吗？我们还有一点时间。让我打印它。如果我打印。

<details>
<summary>Original English</summary>

**Olivier**: And actually if I you know what, let's we have time? We have a little bit of time. Let me print it. If I print the
</details>

**Olivier**: 呃，等等，是`console.log`。

<details>
<summary>Original English</summary>

**Olivier**: uh wait, it's console.log
</details>

**Olivier**: 是的。那很糟糕。

<details>
<summary>Original English</summary>

**Olivier**: Yeah. That was bad.
</details>

**Yohan**: [笑声]

<details>
<summary>Original English</summary>

**Yohan**: [laughter]
</details>

**Olivier**: 这真是好产品。再次退出。好的，点击，点击。你可以看到它再次纠正了。你还可以看到它还给了我正确的输出，以及所有纠正的起始索引、结束索引和更改了什么。所以你甚至可以在你的输入上获得一些纠正功能。

<details>
<summary>Original English</summary>

**Olivier**: This is good products. Again, going out. All right, click clicking on the And you can see that it corrected again. And you can see that it also gives me so the correct corrected output and all the correction with the and start index and index and what it changed. So you can even have like some like correction things if you want on your on your input.
</details>

**Olivier**: 所以这些是两个例子。我将让你进行实际的那个很酷的演示。

<details>
<summary>Original English</summary>

**Olivier**: So these are two examples. I'm going to let you on do the actually the cool one, the cool demo.
</details>

**Yohan**: 是的，我们来添加。所以**Olivier**向你展示的基本上是非常聚焦的API，用于**摘要**、**校对**。但我们也可以访问更通用的API，比如你可能使用过的，例如如果你使用**OpenAI API**或你正在使用的任何AI提供商，只需向它发送你的提示。

<details>
<summary>Original English</summary>

**Yohan**: Yes, let's add So what Olivier showed you is uh basically the very uh focused API for summarization, for uh proofreading, uh but we also have access uh to um like more general API like the one you may have been used uh for example, if you're using the the OpenAI API or whatever uh AI provider you're using to just basically send it uh your prompt.
</details>

**Yohan**: 所以我们有这个**长语言模型创建API**。你可以设置你期望的输入类型，因为你可以发送文本，在我们的例子中，我希望能够发送图像。你也可以将音频作为类型，所以它是**多模态**的。

<details>
<summary>Original English</summary>

**Yohan**: So we have this uh long language model that create API. Uh you can set what kind of expected input you have uh because you can send it text and in our case I want to be able to send it uh images. Uh you can also have audio as a type, so it's multimodal.
</details>

**Yohan**: 现在我有了这个。你基本上构建你的通用提示。所以我想做的是，基本上，根据我上传的图像，自动编写评论。所以我说：“好的，这是一张产品图片，我想生成一个评论描述，在一句话中提及情况，并基本上说明你在收到产品时的感受，并生成标题。” 我希望结果是一个**JSON对象**，包含标题和评论内容。

<details>
<summary>Original English</summary>

**Yohan**: Now that I have uh here uh you basically build your general prompt. So uh what I want to do is basically have uh an auto writing uh of a review based on a uh just an image uh that I upload. So what I say is okay, this is an image of the product and I want to generate a description for a review to mention the condition in one sentence and basically tell how you felt uh when receiving the product and generate also title. And I want uh the result to be a JSON object uh with the title and review contents.
</details>

**Yohan**: 所以，好的，这就是我的提示，就像你尝试使用常规**AI API**时一样。

<details>
<summary>Original English</summary>

**Yohan**: So okay, this is my prompt just like uh when you're trying to use a regular AI API.
</details>

**Yohan**: 下一步基本上是运行**Prompt API**。所以这里的`session.prompt`来获取响应。所以输入的格式基本上是设置一个消息列表。我在这里使用用户消息来发送我们的提示和输入图像。所以内容你可以看到，你可以混合搭配不同类型的内容。

<details>
<summary>Original English</summary>

**Yohan**: And uh next step is basically uh to uh run the prompt API. So session.prompt here to get the response. Uh so the look of the input is basically uh set a list of messages. Here I'm using uh the user message to uh send our prompt in there and the input image. So the content you can see you can mix and match different kind of content.
</details>

**Yohan**: [叹气]

<details>
<summary>Original English</summary>

**Yohan**: [sighs]
</details>

**Yohan**: 我希望输出是**JSON**。所以我需要对响应添加一些约束。所以我只是想说，我的响应需要遵循指定的特定**Schema**。

<details>
<summary>Original English</summary>

**Yohan**: I want to have uh JSON as an output. So I need to add some constraint to the to the response. So I want just to say uh my response needs to follow a specified uh specific schema.
</details>

**Yohan**: 让我们在这里定义**Schema**。**Schema**只是一个**JSON Schema**。我认为我想要一个包含`title`（字符串）和`description`（也是字符串）的对象。

<details>
<summary>Original English</summary>

**Yohan**: So let's define the schema in there. And the schema is just a a JSON plain JSON schema. I think that I want an object that has title that's a string and a description that's also string.
</details>

**Yohan**: 现在我应该拥有所有东西，除了返回结果并在日志中打印它。

<details>
<summary>Original English</summary>

**Yohan**: And now I should have uh everything except to uh return the result and also print that in the logs.
</details>

**Yohan**: 所以，我们来测试一下我们刚刚做的。转到浏览器。

<details>
<summary>Original English</summary>

**Yohan**: So uh let's test what we just did. Uh moving on to the browser.
</details>

**Yohan**: 让我们给它多一点空间。所以我想尝试这个**Prompt API**，基本上是替我写评论。所以我将上传这张图片。这是我收到的耳机。正如你所看到的，状况不是很好。所以我们看看它会写出什么样的评论。

<details>
<summary>Original English</summary>

**Yohan**: Let's give it a bit more space. So I want uh to try this prompt API to basically write the review in my place. So I will upload this image. So this is the headphone I received. As you can see, not in pretty good shape. So let's see what review it will come up with.
</details>

**Yohan**: 如果我选择分析，哦，我只是想在控制台中显示。哦，那可能是新的。它说我没有指定语言。所以，是的，正如你所看到的，**Olivier**总是指定了请求发送的语言。

<details>
<summary>Original English</summary>

**Yohan**: So if I select analyze, oh just want to show the console in there. Oh, that may be new. Uh it's saying that I didn't specify the language. So yeah, as you can see, Olivier has uh always specified in which language the request was sent.
</details>

**Yohan**: 所以，这是结果。你可以看到**JSON**，你可以看到它为我填写了字段。所以是“损坏严重，到货时耳机已破损”。当然，我在收到这种产品时感到失望和沮丧。

<details>
<summary>Original English</summary>

**Yohan**: So uh this is the result. You can see the JSON and you can see that uh it has filled in the the field for me. So devastatingly damaged, broken headset upon arrival. And of course uh I was disappointed and frustrated when receiving uh this kind of uh of product.
</details>

**Yohan**: 所以，是的，我基本上可以直接在那里提交评论，可以看到它为我节省了一些时间，只需上传图片，让AI为我写所有内容。再次强调**Olivier**已经说过的话，但这完全使用在客户端机器上运行的本地模型，完全在浏览器中。

<details>
<summary>Original English</summary>

**Yohan**: So yeah, I can just submit the review in there basically and uh can see saving me some time just uploading the image and have the AI write everything for me. And again uh just recalling what Olivier already said, but this is all using a local model uh running on the client machine entirely in the browser.
</details>

**Yohan**: 所以没有使用任何**Web API**。它完全在浏览器中。所以我认为这很酷，这只是你可以做的事情的一个简单用例，因为这个**本地模型**，正如你所看到的，它是**多模态**的。它可以理解图像，它可以理解音频和文本，你可以做各种事情，而无需支付外部API费用。

<details>
<summary>Original English</summary>

**Yohan**: So nothing and no using any web APIs. It's all within uh the browser. So I think that's pretty cool and this is just a single uh example use case of the kind of things that you can do uh because this uh local model, as you can see, it's uh multimodal. It can understand images, it can understand audio and text and you can do all kind of stuff uh without having to pay like for an external API.
</details>

**Yohan**: 是的，这些API仍然是新的。我的意思是，如果你能切换到我的屏幕。我刚刚打开了**MDN文档**上的**摘要API**，你可以看到它仍然是高度实验性的。但实际上我只是觉得**Opera**已经实现了它。你有**Chrome**。**Edge**也即将推出。

<details>
<summary>Original English</summary>

**Yohan**: Yeah, is it this is this these APIs are still new. I mean, if you can move to my um to my screen. I just I just went to open the the summarize API on on the uh MDN documentation and you can see that it's still like highly experimental and you can see that but actually I just feel like Opera is already implementing it. You have Chrome. Um Edge is coming.
</details>

**Yohan**: 所以API仍然会改变。我们刚刚在你的屏幕上看到的东西实际上是新的。我们一周前尝试时还没有这种语言异常。所以请小心。这些API可能会改变。所以如果你的网站实现了它，你现在知道了。

<details>
<summary>Original English</summary>

**Yohan**: So the APIs can still change. And what we just saw on on your own screen is actually new. We didn't have this like language exception like a week ago when we we tried it. So just be careful. Like these APIs can change. So if you implement it in your website, you know now.
</details>

**Yohan**: 所以，是的，非常实验性，但我也认为它为Web开发者开启了各种可能性，这非常令人兴奋。

<details>
<summary>Original English</summary>

**Yohan**: So yeah, very experimental, but I think also very exciting for the kind of uh possibilities that it opens for for web developers.
</details>

**Yohan**: 我的意思是，你可以拍摄一张图片，然后对图片内容进行解释。我的意思是，我们看到了**你画我猜**的演示，你可以有一张图片，人们可以在屏幕上绘画，然后它会比较图片并给你一个相似度百分比。所以这实际上非常酷，无需依赖任何云、任何在线模型、任何你需要发送的**token**等等。

<details>
<summary>Original English</summary>

**Yohan**: I mean, the fact that you can take an image and come up with uh an explanation what's on the image. I mean, we've seen like some Pictionary demo where you can like you have an image and people can should draw on their on the screen and then it compares the image and give you like a percentage on does it look like the same thing? So it's actually pretty cool without relying on any cloud, any online model, any like token you have to send or whatever.
</details>

**Yohan**: 非常酷。

<details>
<summary>Original English</summary>

**Yohan**: Pretty cool.
</details>

**Olivier**: 好的。是的。

<details>
<summary>Original English</summary>

**Olivier**: Okay. Uh yes.
</details>

**Yohan**: 接下来是什么？回到幻灯片。

<details>
<summary>Original English</summary>

**Yohan**: have next? Back to the slides.
</details>

**Olivier**: 哦。

<details>
<summary>Original English</summary>

**Olivier**: Oh.
</details>

### 为AI代理优化Web应用

**Olivier**: 最后一个，但并非最不重要的部分，因为这意味着AI代理现在为我们做了很多工作，但我们也要为它们做一些工作。

<details>
<summary>Original English</summary>

**Olivier**: Last [snorts] uh but not least section uh because this means okay, AI AI agents do a lot of works for us uh nowadays, but we also have to do some work for them.
</details>

**Yohan**: [笑声]

<details>
<summary>Original English</summary>

**Yohan**: [laughter]
</details>

**Olivier**: 是的，现在你需要一些人类来升级你的网站，以适应代理。所以，是的，代理能够浏览网页。新情况是，你不仅要优化网站以适应人类、可用性、以及良好的**SEO**以在搜索引擎中被发现，现在我们还要考虑代理如何消费和使用你的Web应用。这是一件全新的事情。

<details>
<summary>Original English</summary>

**Olivier**: This is the time that yeah, you actually need some human humans to like upgrade your websites uh for for agents. So yeah, agents are capable of browsing the webs. The new thing is that you have to optimize your website not only for humans, usability uh and good SEO for being discoverable in search engine, but now we are also to think about uh the way agents can consume and use web your web apps. So that's brand new thing.
</details>

**Olivier**: 首先，我们从一个非常简单的提议开始。就像我们已经有了**robots.txt**一样，它已经被搜索引擎采用，这些搜索引擎已经在抓取网页，只是为了提供一些规则，说明这些爬虫如何导航你的网站。我们也有**sitemaps**，用于人类，以更易访问的方式改进他们如何导航网站。我们有这个新的**LLM.txt提案**，它基本上是两者的混合。所以它被代理用作地图，以发现它在你的网站上需要的信息在哪里。

<details>
<summary>Original English</summary>

**Olivier**: And uh first we'll start with just a very simple proposal. Uh just like we already have like robots.txt uh that has been adopted for search engine uh that are already crawling the web uh just to give some rules about how the these crawlers uh navigate to your websites. We also have like sitemaps uh for humans to improve how they can navigate the websites in more accessible way. We have this new LLM.txt proposal that's basically a bit of uh mix of both. So it's used by agents to act as a map uh to discover where it can find the information it needs on your website.
</details>

**Olivier**: 它有点像**robots.txt**和**sitemap**的混合，在格式上是文本文件格式。让我向你展示一个例子。

<details>
<summary>Original English</summary>

**Olivier**: Just kind of mix of robots.txt and uh for the format the text file format and uh the sitemap. And uh let me show you actually like an example.
</details>

**Olivier**: 我已经告诉过你我是**Angular**的GDE。所以我将向你展示`angular.dev`网站的**LLM.txt**。这就是你得到的。你得到一个带有大量链接的**Markdown文件**。所以基本上，如果一个AI想搜索文档，它就不必浏览每个网页来查找所需信息。

<details>
<summary>Original English</summary>

**Olivier**: One uh already told you I'm an Angular GD. So I will show you the LLM.txt for the angular.dev website. So uh this is what you get. You get a markdown file with a bunch of links. Uh so basically if an AI want to search for the documentation, it doesn't have like to go through each web page to try to find the information it needs.
</details>

**Olivier**: 例如，如果我想了解一些关于**动画**的东西，它会直接引导AI代理去查看其中一个文档页面，这取决于你想做什么。这就是**LLM.txt**的基本前提。它让你的代理更容易找到他们需要的内容。

<details>
<summary>Original English</summary>

**Olivier**: Uh for example, if I want to have something about animation, it will basically directly uh guide the AI agents to move on to look at one of these documentation page depending of what you're trying to do. This is uh the basic LLM.txt uh premises. So making it easier for your agents to try to find the content uh that they need.
</details>

**Olivier**: 但它可以更进一步，因为我们有这个**LLM-full.txt**变体，它基本上将你网站的所有内容汇集到一个文件中。所以**Angular**也有一个。

<details>
<summary>Original English</summary>

**Olivier**: But uh it can go a bit further because we have like this LLM uh dash full.txt variants where uh basically it brings in all the contents of your website into a single file. So uh we have also one for Angular.
</details>

**Olivier**: 这个非常广泛，正如你所看到的滚动条。如果你在里面滚动一点，你可以看到我甚至有一些代码示例文件。它是最新**Angular版本**的所有内容，收集在一个文本文件中，你可以将其提供给你的代理。

<details>
<summary>Original English</summary>

**Olivier**: Uh this one is pretty extensive like as you can see the scroll bar in there. If And if you're uh scrolling a bit inside there, you can see that I even have like some code uh file example. It's all the contents of the latest Angular version gather in one single text file that you can feed your agents.
</details>

**Olivier**: 例如，有时使用编码代理的一个困难之处在于，它们的最后一个检查点是基于旧版本的框架，因为你不能总是用新内容训练新模型。是的，有时它会有几个月或几年的延迟。所以它不知道如何使用你的框架的全新最新版本。例如**Angular**。

<details>
<summary>Original English</summary>

**Olivier**: Uh for example, one of them uh difficult thing with uh sometimes with using coding agents is that uh uh their their last checkpoint was based uh using like older version of the frameworks because uh yeah, you can't always train the new model with the the new contents. Yeah, sometimes it have a month or years uh of delay uh regarding the content. So it doesn't know how to use like the the brand new latest version of your framework. Let's say for example for Angular.
</details>

**Olivier**: 所以，如果你想确保，例如，我想使用**Angular**的最新功能和最新版本来编写一个应用程序，我想确保它使用最新的参考资料。我可以将这个**LLM-full.txt文件**提供给我的编码代理。所以，它拥有所有最新的信息，以确保我不会使用训练数据中的旧功能，比如10年前的旧**Angular JS**示例等等。所以，这很酷也很实用。

<details>
<summary>Original English</summary>

**Olivier**: So if you want to make sure that uh for example, I want to code an application using the very latest feature of Angular and the very last version, I want to make sure that it use the most up-to-date reference. Uh I can feed it this LLM uh dash full.txt file uh to my coding agents. So, uh it has all the the up-to-date information to make sure that I don't use like old feature from the training data like old Angular JS example from 10 years ago and stuff like that. So, this is kind of cool and helpful.
</details>

**Olivier**: 例如，为了确保代理可以获得最新信息，这就像一个编码库，但它可以转换为你的网站提供的任何类型的内容。

<details>
<summary>Original English</summary>

**Olivier**: For example, to make sure that agents can have the latest information about this is like for a coding library, but it can be you translated to any kind of content that your website provide.
</details>

### Web MCP：Web应用与代理的无缝交互

**Olivier**: 现在，最后一个但并非最不重要的**Web MCP**。切换到幻灯片，我将把话筒交给**Olivier**，进行我们最后一个有趣的演示。

<details>
<summary>Original English</summary>

**Olivier**: Now, last but not least Web MCP. Moving on to the slides and I will give the hand to Olivier for this one, the very last and fun demo that we have.
</details>

**Olivier**: 是的，我们从实验性的API到高度实验性的。

<details>
<summary>Original English</summary>

**Olivier**: Yeah, we went from from like experimental APIs to like very very highly experimental.
</details>

**Olivier**: 所以，**Web MCP**，你能分享我的屏幕吗？是的。**Web MCP**，我的意思是，如果你想看看它有多实验性，去**Web MCP**的网站。这就是现在的网站。所以，不多。

<details>
<summary>Original English</summary>

**Olivier**: So, Web MCP, can you share my screen, please? Yeah. The Web MCP, I mean, if you want to see how experimental it is, go on the website of Web MCP. This is this is the website right now. So, not not much.
</details>

**Olivier**: 但这个想法是，好的，我们有代理可以浏览网页，正如**Yuan**提到的，它们去检查**LMS**，那会获取文本文件。但我们越来越多地看到AI嵌入到你的浏览器中，你有一个我们称之为**代理式浏览器**的东西。所以基本上它会代表你浏览网页。

<details>
<summary>Original English</summary>

**Olivier**: But the idea is that okay, we have agents can browse the web as Yuan mentioned, they go and they check the LMS, that takes text files. But more and more we're seeing like AI embedded on your browser that you you have like a we we call it like an agentic browser. So, basically it's going to browse the web for you on your behalf.
</details>

**Olivier**: 现在我们有一些工具可以做到这一点。它们会打开一个浏览器，它们会点击和浏览。但它们这样做的方式是试图模仿人类交互。所以它们会通过截图或查看**DOM**来查看页面，然后说：“好的，这里有一个按钮，我可以点击它，获取坐标，然后点击它。” 表单也是如此。

<details>
<summary>Original English</summary>

**Olivier**: And right now we have some tools can do that. They're going to open a browser, they're going to click and browse. But the way they do that is that they're trying to mimic human interactions. So, they're going to look either at the page by taking screenshots or by looking at the DOM and say and like okay, there's a button here that says that I can click on it taking the coordinates, going and click on it. Same for a form.
</details>

**Olivier**: 但基本上，它们试图模仿人类行为。所以网站是为人类设计的，而不是代理。

<details>
<summary>Original English</summary>

**Olivier**: But basically, they are trying to mimic um a human behavior. So, the website I've been designed for humans, not agents.
</details>

**Olivier**: 这正是这个**Web MCP**提案试图解决的问题。目标是让**MCP服务器**，例如，在你的Web应用程序上运行。这样你就可以访问工具。

<details>
<summary>Original English</summary>

**Olivier**: And so, this is exactly what this proposal is trying to fix, the Web MCP. The goal would be to have like an MCP server, let's say, running on your web application. So, you'd have access to tools.
</details>

**Olivier**: 我们知道代理理解工具。代理可以调用工具，因为它们可以访问工具的名称、定义，并且知道何时调用它们。所以，让我向你展示。例如，我再次打开应用程序。这里有一个**“添加到购物车”按钮**。所以你可以看到我的购物车里现在有东西。

<details>
<summary>Original English</summary>

**Olivier**: And we know that tools that agent understand. Agents can call tools because they have access to the name, the definitions, and they know when to call them. So, let me show you. For example, I have the application here again. I have a add to cart here button. So, you can see that I have something in my cart now.
</details>

**Olivier**: 但如果一个AI要这样做，它就必须打开一个**Chrome**，尝试猜测这里有一个按钮，获取坐标，然后点击按钮。

<details>
<summary>Original English</summary>

**Olivier**: And but if an AI would have to do the same, it would have to open a Chrome, try to guess that there's a button here, get the coordinate, and click on the button.
</details>

**Olivier**: 但如果它能实际访问一个工具，比如一个**AI工具**，来调用它呢？所以，这里我有**Chrome**。**Chrome**还不是一个**代理式IDE**。但我有一个扩展，可以显示我的页面上是否注册了任何工具。

<details>
<summary>Original English</summary>

**Olivier**: But what if it could have actually have access to a tool, like an AI tool, to call it. So, here I have Chrome. Chrome is not yet an agentic IDE, but I have an extension here that can show if I have any tool registered on my page.
</details>

**Olivier**: 所以，我们来看看如何在我页面上注册一个工具。我这里有一个**购物车工具文件**，它基本上只是导入**添加到购物车**。**添加到购物车**是我点击**添加到购物车**时调用的函数。它只是向我的购物车添加东西。

<details>
<summary>Original English</summary>

**Olivier**: So, let's see how I can register a tool on my page. I have a cart tool here file that just basically import the add cart. Add cart is the function that is called when I click on add cart here. It just add something to my cart.
</details>

**Olivier**: 所以，我将创建一个工具。如果你还记得你以前创建工具的方式，我们过去常有这些**SDK**。我们过去常有一个**JSON**。

<details>
<summary>Original English</summary>

**Olivier**: And so, I'm going to create a tool. So, if you if you remember if you're creating tool before we had all these SDKs, this is how we used to do. We used to have like a JSON.
</details>

**Olivier**: 你会给它一个名字。你会给它一个描述。所以这里它是一个将物品添加到购物车的工具。并且给我一个**Schema**。所以它接受一个带有物品名称和数量的对象。所以，我没有数据库或其他什么。只是名称和数量。

<details>
<summary>Original English</summary>

**Olivier**: You would give it a name. You would give it a description. So, here it's a a tool to add items to cart. And give me a a schema. So, it's taking an object with the item its item name and the quantity. So, I don't have a database, whatever. So, just the name and the quantity with it.
</details>

**Olivier**: 然后我有执行函数。所以`execute`函数是一个包含业务代码的函数。

<details>
<summary>Original English</summary>

**Olivier**: And then I have the the execute. So, the execute function is a function that's going to have that uh the business code in it.
</details>

**Olivier**: 所以我将获取参数。我正在检索物品和数量。

<details>
<summary>Original English</summary>

**Olivier**: So, I'm going to get the the arguments. So, I'm retrieving the item and the quantity.
</details>

**Olivier**: 我将循环数量，因为我的**添加到购物车**只接受一个。它不管理数量。所以我正在循环并添加到购物车。我只是返回。只是说已经添加了数量物品。

<details>
<summary>Original English</summary>

**Olivier**: I'm going to loop over the quantity because my add to cart only takes one. It doesn't manage quantity. So, I'm looping and adding to cart um what I have. And I'm just returning like whatever. Just say the quantity item has been added.
</details>

**Olivier**: 另一件事是注册我的工具。所以我创建了我的工具，并将其注册到我的页面的**navigator对象**上。现在，如果我回到这里并刷新，你可以看到我的数据扩展在这里，显示我有一个**添加到购物车工具**，我可以调用它。

<details>
<summary>Original English</summary>

**Olivier**: And the other thing to do is to register my my my tool. So, I created my tool and I registered it on my the navigator object of my my page. Now, if I go back here and I refresh, you can see that my my data extension here, see that I have a add to cart tool and I can call it.
</details>

**Olivier**: 所以，我可以说：“好的，我想添加，我不知道，**水瓶**，我想有五个。”

<details>
<summary>Original English</summary>

**Olivier**: So, I can say okay, I want to add I don't know water bottles and I want to have five.
</details>

**Olivier**: 当我在这里执行工具时，基本上，你可以看到它添加了五个**水瓶**。它基本上就像一个AI替我做的。它正在调用注册在我页面上的工具。

<details>
<summary>Original English</summary>

**Olivier**: And when I execute the tool here, basically, you can see that it added like five water bottle. And it's basically like an AI who did it on my behalf. It's calling the tool that is registered on my page.
</details>

**Olivier**: 让我看看。我们还有点时间。我正在测试它。测试我是否可以直接从我的IDE中调用它。

<details>
<summary>Original English</summary>

**Olivier**: Let me see. I had a We have a bit of time. I'm I'm I'm testing it. Testing if I if I can call it directly from my my IDE here.
</details>

**Olivier**: 是的，我知道。我有很多东西。让我看看。

<details>
<summary>Original English</summary>

**Olivier**: Yeah, I know. I have a lot of things. Let me see.
</details>

**Olivier**: 是的。所以，基本上，我甚至可以从这里做。所以，这里我有我的代理。我可以说：“比如，你知道吗，添加。” 好的，我要移除开发工具，这样我就不会有太多工具。添加三个。

<details>
<summary>Original English</summary>

**Olivier**: Yeah. So, basically, I can I could even do it like from here. So, here I have my agent. I can say like, you know, add Okay, I'm going to remove the dev tool so I don't have too many tools. Add three
</details>

**Olivier**: 我不知道。三个**手机笔记本**到我的购物车。

<details>
<summary>Original English</summary>

**Olivier**: I don't know. Three phone laptops to my cart.
</details>

**Olivier**: 所以，我要这样做，如果一切顺利，它将调用注册在我Chrome浏览器网页上的工具。所以我们看看。它说有一个**添加到购物车**。哦，它在做什么？

<details>
<summary>Original English</summary>

**Olivier**: So, I'm going to do that and normally if everything works well, it's going to call the the tool that is registered on my on my web page in my Chrome. So, let's see. So, it said that there is an add to cart. Oh, what is it doing?
</details>

**Yohan**: [清嗓子]

<details>
<summary>Original English</summary>

**Yohan**: [clears throat]
</details>

**Olivier**: 它正在创建一个工具，制作我的内容。好的。所以它正在调用**添加到购物车**工具，**笔记本电脑**，数量三。你可以在这里看到，如果我现在回到我的网页。好的，我们看看。下方三台笔记本电脑。我这里应该有三台笔记本电脑。

<details>
<summary>Original English</summary>

**Olivier**: It's creating tool that makes my content. Okay. So, it's calling yeah, it's calling the tool add to cart, laptop quantity three. You can see here if I go back to my web page now. Okay, let's see. Down three laptop. I should have like three laptops here.
</details>

**Olivier**: 所以，现在我从扩展或我的IDE调用了它，但目标是你的浏览器可以为你做这件事，因为它是一个**代理式浏览器**。它可以导航选项卡并为你做这件事。所以你可以看到我的工具正在我的网页上运行。

<details>
<summary>Original English</summary>

**Olivier**: So, now I called it either from like an extension or from my my IDE, but the goal would be that you your your browser can do it for you because it it's an agent type browser. It can navigate tabs and do it for you. So, you can see that my tool is running on my web page.
</details>

**Olivier**: 代码不多，但甚至有一种更好的方式，我不知道是否更好，但假设你不想在应用程序中添加任何新的**JavaScript**，因为你正在过渡，你只想在你的应用程序上测试这些**MCP工具**，而无需过多更改代码。

<details>
<summary>Original English</summary>

**Olivier**: So, and it's not much code, but there is even like a better I don't know if it's a better way, but let's say you don't want to add some new JavaScript to your application because you're transitioning and you want to just test these these MCP tools on your application without changing much the code.
</details>

**Olivier**: 所以，假设我这里有一个表单。这个表单是用来写评论的。我能做的是，我可以设置一个**工具名称**。

<details>
<summary>Original English</summary>

**Olivier**: So, let's say I have the form here. The form is to write a review. What I can do is I can say okay, I'm I'm going to add a tool name.
</details>

**Olivier**: **写评论工具**。我将给它一个**工具描述**。在这里我将说：“为产品添加评论。”

<details>
<summary>Original English</summary>

**Olivier**: Write review tool. I'm going to give it a tool description. Here I'm going to say like add review to the product.
</details>

**Olivier**: 通过这样做，我将我的表单转换为一个工具。它将获取表单中的所有不同输入，然后将它们转换为参数。我甚至可以做一些**工具参数描述**。你可以说：“给产品评分。” 所以我可以添加一些描述。例如，我将输入设置为**工具参数描述**等于“为评论添加标题”。

<details>
<summary>Original English</summary>

**Olivier**: And by doing that, I've transformed my form into a tool. It's going to take all the different inputs in it and then transform them into arguments. I can even like do some like tool param description. You say like rate the product. So, I can add some descriptions to it. For example, I have the whatever do I have as like the input here. It's like okay, tool param description equal like add a title
</details>

**Olivier**: 噢，错了，为评论添加标题。我可以添加这些，但我不需要。如果我回到这里，你可以看到现在我有我的**写评论**。这是它生成的**Schema**。

<details>
<summary>Original English</summary>

**Olivier**: oops, add a title for the review. And I can add these, but I don't have to. If I go back here, you can see that now I have my write to review. And this is the schema of that it has generated.
</details>

**Olivier**: 你看到它基本上与我们在这里手动添加**Schema**时是相同的。

<details>
<summary>Original English</summary>

**Olivier**: You see it's basically the same thing that we had here when I manually added the schema.
</details>

**Olivier**: 但你可以看到我有我的工具。所以我有**写评论**，它从一到五获取了这里的所有输入选项。我有带有我的描述的评论标题。我添加了“为评论添加标题”，但也有评论文本和评论照片。它自动生成了一些描述。为了做到这一点，它使用了我的**HTML**上最近的标签。

<details>
<summary>Original English</summary>

**Olivier**: But you can see that I have my Where is it? My tool. So, I have that the write the product and it took all the input options here from one to five. I have the review title with my description. I put the add title to review, but also have the review text and the review photo. And it automatically generates some description. And to do that, it took the nearest label on my on my HTML.
</details>

**Olivier**: 所以，如果我查看**添加照片**，你可以看到我有一个**添加照片（可选）标签**，这就是它默认在这里放置的内容。所以我们看看它是否能工作。我将调用**写评论工具**。

<details>
<summary>Original English</summary>

**Olivier**: So, if I go to the add a photo, you can see I have a label add photo optional and that's what it put here by by default. So, let's see if that can work. I'm going to call the write review tool.
</details>

**Olivier**: 我没有照片。我可以说它很好。

<details>
<summary>Original English</summary>

**Olivier**: I don't have a photo. I can say like it's a it's a good for
</details>

**Olivier**: 让我看看我是否可以在这里检查。我可以说标题是“很棒的评论”。我可以说评论文本是“完美的产品”。

<details>
<summary>Original English</summary>

**Olivier**: um let's see if I can inspect so I can see it here. I can say like title awesome review. I can say like review text perfect product.
</details>

**Olivier**: 我要执行这个工具。所以。它在做什么？

<details>
<summary>Original English</summary>

**Olivier**: And I'm going to execute the tool. So, is it doing something?
</details>

**Olivier**: 不，它不应该添加到这里。

<details>
<summary>Original English</summary>

**Olivier**: No, it's not supposed to add it here anyway.
</details>

**Olivier**: 嗯。

<details>
<summary>Original English</summary>

**Olivier**: um
</details>

**Olivier**: 哦，是的。不，不。它应该是这样。

<details>
<summary>Original English</summary>

**Olivier**: Oh, yeah. No, no. It's supposed to like like that.
</details>

**Olivier**: 嗯哼。怎么了？

<details>
<summary>Original English</summary>

**Olivier**: Uh-huh. What's happening?
</details>

**Olivier**: 我说我的文件终于保存了。好的，我们再试一次。所以比如“很棒的产品”。“喜欢它。”

<details>
<summary>Original English</summary>

**Olivier**: I said my file is finally saved. Okay, let's let's try again. For so like awesome product. Love it.
</details>

**Olivier**: 我要执行它。哦，是的。你可以看到它为我填写了表单。是的，这里是“很棒的产品”。它添加了“喜欢它”。我没有图片，但它本可以有。

<details>
<summary>Original English</summary>

**Olivier**: I'm going to execute it. Oh, yeah. And you can see that it filled the form for me. Yeah, the awesome product here. It added love it. I don't have a picture, but it could have it.
</details>

**Olivier**: 但你也可以说：“好的，这很好，因为它填写了表单，但我也希望它验证表单。” 所以，如果我回到我的表单这里，我将设置**工具自动提交**。通过这样做，它将同时填写表单。比如说三。

<details>
<summary>Original English</summary>

**Olivier**: But you can also say okay, this is good because it filled the form, but I want also it to validate the form. So, if I go back to my form here, I'm going to say um tool tool auto submit. By by doing that, it's going to both uh fill the form. Let's say three.
</details>

**Olivier**: 完美。

<details>
<summary>Original English</summary>

**Olivier**: Perfect.
</details>

**Olivier**: 好的，等等。好的。别管那些错误。然后，如果我点击这里执行工具，它将填写表单，但也会验证整个表单本身。它甚至不需要任何人类交互。它将填写并验证。

<details>
<summary>Original English</summary>

**Olivier**: Also, well, wait. Okay. Don't pay attention to the mistakes. And then, if I click execute tool here, it's going to fill the form, but also validate the full form itself. It doesn't even like require any human interaction. It's going to fill and validate.
</details>

**Olivier**: 所以，这再次是高度实验性的。实际上，这个API在10天前又改变了。所以请小心，但要知道这就像我们常说的，就像**响应式设计**。

<details>
<summary>Original English</summary>

**Olivier**: So, this is highly experimental again. And actually, the API changed like 10 days ago again. So, be careful, but just know that it's like we we used to say that that it's like uh you know, responsive design at some point.
</details>

**Olivier**: 在某个时候，你必须为移动设备调整你的网站。如果你没有这样做，那么竞争对手就会这样做，然后人们就不会在移动设备上访问你的网站。所以，我认为这和那是一样的。一旦所有**代理浏览器**进入市场，请确保你的网站已经准备好。所以，你可以开始实验，同样，高度实验性，但开始实验，这样当所有这些新浏览器出现时，你就可以准备好了。

<details>
<summary>Original English</summary>

**Olivier**: You had to adapt your website for mobile. If you didn't do it, then the competition did it, and then people wouldn't go to your website on the mobile. And so, I tend to think that this is the same. Make sure your your website is going to be prepared once we have all the agent agent peak uh browser coming out on the market. And so, you can start experimenting, again, highly experimental, but start experimenting so you're ready when we have all these new browsers coming up.
</details>

**Olivier**: 演示成功了。

<details>
<summary>Original English</summary>

**Olivier**: And the demo worked.
</details>

**Yohan**: [笑声]

<details>
<summary>Original English</summary>

**Yohan**: [laughter]
</details>

**Yohan**: 太棒了。是的，我期望这只是我们Web开发者在不久的将来必须做的事情的一瞥，因为，是的，代理正以非常快的速度进入Web。

<details>
<summary>Original English</summary>

**Yohan**: Nice. Yeah, I expect this is a glimpse of what we'll have to do as web developer in in the near future cuz yeah, agents are coming from the web very fast, and
</details>

**Yohan**: 我期望这个规范已经发展得非常快。它一直很有用。是的，如果你回顾几个月前的状态，它还不能像你展示的那样使用。我特别喜欢如何将现有表单升级为**MCP工具**的功能，因为它使我们这些开发者的生活非常简单，甚至代理也可以为我们实现。

<details>
<summary>Original English</summary>

**Yohan**: I expect the the this specification is already moving very fast. It has been useful. Yeah, if you looked at the state a few months back, it wasn't already usable just like you you shown. I especially like the feature how to upgrade like existing forms as MCP tools cuz it makes the life of developers like us very simple, and even agents to implement that for us.
</details>

**Yohan**: 是的。所以，最后，我们在此次会议中看到的是，基本上，有了AI，它使我们这些Web开发者的生活更加轻松。无论是编写代码、实现更好的工作流、调试（当然非常重要）、展示性能。

<details>
<summary>Original English</summary>

**Yohan**: Yeah. So, uh in the end, what we've seen during the this session is basically with AI, it makes the life of web developers like us easier. Whether it's writing the code, implementing better workflow, debugging, of course very important, showing the performance.
</details>

**Yohan**: 但同时，我们也要帮助AI工具更好地使用我们的网站和Web应用。所以这还处于早期阶段，但你可以开始思考了。

<details>
<summary>Original English</summary>

**Yohan**: But also, we have to help the AI tools be able to better use our website and web apps. So, it's a bit early in the process, but yeah, you can start already thinking about that.
</details>

**Yohan**: **LLMs.txt**现在已经广泛使用了。**MCP**规范也已经广泛使用了，**Web MCP**有望成为下一个大事件。所以，是的，你必须为此做好准备，并希望能最终做出更好的Web应用。

<details>
<summary>Original English</summary>

**Yohan**: LLMs.txt is already widespread nowadays. MCP the norm is already widespread, and Web MCP is coming for the next big thing, hopefully. So, yeah, you have to prepare for that, and hopefully, it will just make better web apps in the end.
</details>

**Yohan**: 是的。

<details>
<summary>Original English</summary>

**Yohan**: Yes.
</details>

**Yohan**: 是的，感谢观看本次会议。那里有一个**二维码**，其中包含了所有资源，演示的代码，以及我们在本次会议中使用的、展示的不同资源的链接。

<details>
<summary>Original English</summary>

**Yohan**: And yes, thanks for for seeing this session. And we have a QR code in there with basically all the resources, the the code for the demo, and the links to the different resources that we've used, we've shown during during this session.
</details>

**Yohan**: 所以，是的，如果你有任何问题，可以在**LinkedIn**上联系我们。在此期间，玩得开心。再见。好的。再见。

<details>
<summary>Original English</summary>

**Yohan**: So, yeah, and just if you have any question, you can ping us on LinkedIn. In the meantime, have fun. Have fun. See you. Okay. Bye-bye.
</details>