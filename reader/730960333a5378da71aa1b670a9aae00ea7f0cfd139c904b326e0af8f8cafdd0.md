---
author: AI超元域
date: '2026-03-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GIhRIztU3R4
speaker: AI超元域
tags:
  - compute-use
  - ai-automation
  - code-generation
  - skill-creation
  - ai-agent
title: Cloud Code Compute Use：AI 赋能的自动化办公新范式
summary: 本视频深入评测了Cloud Code最新版原生支持的Compute Use功能。通过实操演示，展示了Cloud Code在操控Mac国际象棋、自动化测试iOS应用、以及协同Codex生成登录页Demo等方面的强大能力。特别强调了其通过创建和调用Skill来固化学习经验，从而实现高效自动化办公的潜力。同时提及了Cloud Code源代码泄露事件。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Cloud Code
  - Compute Use
  - Skill
media_books: []
status: evergreen
---
### Cloud Code 迎来 Compute Use

Cloud Code 的最新版本现已原生支持 **Compute Use** 功能。这是继 Cloud 桌面应用中的 CoWork 及 Code 支持 Compute Use 功能之后，Cloud Code CLI 正式加入此项能力。这意味着 Anthropic 将整个 Cloud 生态系统打造成比 Open Cloud 更为强大和完善的平台，Cloud 正在逐渐变得越来越像 Open Cloud，并逐步蚕食其生态。无论在性能还是体验上，Cloud 的表现都远超 Open Cloud。值得注意的是，Cloud Code 的源代码近期已通过 npm 注册表中的一个文件泄露，完整源代码已被发布至 GitHub。若本期视频点赞量破千，下期将制作一期分析 Cloud Code 源代码的视频。在上上期视频中，我们已演示过如何在 Cloud 桌面应用中使用 CoWork 或 Code 来操控电脑，实现真正的 Compute Use。本期视频将重点在 Cloud Code CLI 版本中全面测试其新增的 Compute Use 功能，并深入探究其效果。

### 象棋对弈：AI 的自主决策与学习

在 Cloud Code 中，我们通过 Compute Use 功能让 Cloud Code 操控 MacOS 自带的国际象棋游戏，并让其自主决策进行对弈。虽然 Cloud Code 在最终输掉了这一局象棋，但它将此次操控象棋学到的技巧和最佳实践固化成了 **Skill**，并将其推送到了我的 GitHub。这样，下次 Cloud Code 再执行下国际象棋任务时，就不需要反复摸索，而是可以直接从已有的 Skill 中获取最佳实践。

下面我们就开始测试如何在 Cloud Code 中操控电脑，实现真正的 Compute Use 场景。要使用 Cloud Code 内置的 Compute Use 功能，首先需要确保 Cloud Code 已升级到最新版本，然后启用与 Compute Use 相关的 MCP。具体操作如下：
*   输入斜杠命令 `/mcp`，找到 **Compute Use** 这个 MCP，选中并按 Enter 键进入。
*   按空格键将其启用，此时 Status 会显示为 Connected。
*   在 MacOS 系统设置的“隐私与安全”中，确保终端被授予了“屏幕录制”功能。

完成以上设置后，我们就可以进行测试了。我们继续使用 MacOS 自带的国际象棋游戏。由于在录制视频前已通过 Compute Use 方式让 Cloud Code 下了国际象棋并固化了最佳实践为 Skill，在此可以直接调用该 Skill 来操控国际象棋，速度会更快。输入提示词：“为我下国际象棋游戏，全部由你决策，不要问我。” 发送后，Cloud Code 将全程全自动地进行国际象棋游戏。在开始前，需要授予其在此 Session 中拥有电脑操控的权限。

重置国际象棋到初始化状态后，Cloud Code 开始移动棋子。可以看到，它走棋的速度比上上期视频演示 Cloud 桌面应用 Compute Use 功能时还要快。这是因为在制作视频前，已将下国际象棋的经验和最佳实践固化成了 Skill，通过 Skill 执行下棋速度非常快，并且能非常丝滑地移动棋子。游戏结束后，提示黑方获胜，并给出了关键教训。至此，我们成功通过 Cloud Code 全自动下了这局国际象棋。虽然最终输了，但整个过程非常顺畅。

接下来，让 Cloud Code 将这次学到的经验固化到 Skill 中。输入提示词：“让它将这次学到的经验写入 Skill”，然后发送。下次再让它下国际象棋时，它就会更加顺畅，甚至可能赢。这次失败对于桌面版国际象棋游戏来说，其操控流畅度比之前用 Cloud 桌面应用在 Code 中通过 Compute Use 自动下棋的效果要好非常多。Cloud Code 会更新 Skill，将学到的经验写入其中。这里展示了它学到的经验和教训。通过这种方式，在使用 Cloud Code 执行各种任务时，当出现踩坑或执行失败的情况，就可以让它将学到的经验写入 Skill，使对应场景的 Skill 越来越完善。下次 Cloud Code 使用该 Skill 执行相同任务时，效果会更好。

### iOS 应用测试：模拟器中的自动化验证

接下来，我们加大难度，让 Cloud Code 操控 iOS 模拟器来测试开发的 iOS 应用。这个 iOS 背单词应用是我在之前的视频中演示 Cloud Code 编程能力时开发的一个 Demo。现在用这个项目进行测试。先在 Xcode 中打开应用，并在模拟器中启动。然后让 Cloud Code 操控模拟器对这款应用进行自动测试。这里打开的是 iPad 模拟器，它已经启动。

让 Cloud Code 通过模拟器测试这款背单词应用的效果。在 Cloud Code 中清空上下文后，输入任务提示词：“通过 Compute Use MCP 在 Xcode 模拟器中为我测试当前背单词 App。” 发送后，Cloud Code 将在模拟器中自动测试这款背单词应用的效果。追加提示：“背单词 App 已经在模拟器中打开，在桌面上。” 允许其访问应用后，它生成了测试任务，包括测试首页功能、单词学习功能、练习功能，以及统计设置页面。

可以看到，它点击了“开始学习”，然后点击了“翻转单词卡片”。接着点击了“切换单词”，通过模拟滑动手势切换了单词。再次点击“翻转单词卡片”，然后滑动单词卡片，向左滑，提示左滑成功。为节省时间，不再继续测试。通过刚才的测试可以发现，Cloud Code 确实能够在模拟器中为我们自动测试开发的 App。

### 代码生成：Codex 与 Cloud Code 的协同

接下来，我们测试让 Cloud Code 通过 Compute Use 操控 Codex 的桌面应用，开发一个简单的程序。输入提示词：“让它通过 Compute Use MCP 操控 Codex 桌面应用开发一个登录页的 Demo，并且告诉它 Codex 已经打开显示在左侧。” 发送后，观察它能否在 Codex 的对话输入框输入提示词并自动发送。

需要允许权限。可以看到，底部开始输入提示词，并自动点击发送。在左侧 Codex 需要允许权限，Cloud Code 成功点击了授予 Codex 权限的按钮，Codex 开始进行开发。Codex 开发完成后，自动在浏览器中打开了开发的页面。Cloud Code 中提示 Codex 已完成，生成了完整的登录页。任务完成，通过 Compute Use MCP 操控 Codex 桌面应用成功生成了现代登录页 Demo，并给出了成果总结。

### Skill 系统：固化 AI 经验，提升效率

接下来，让 Cloud Code 将刚才操控 Codex 桌面应用的步骤和最佳实践写成一个 Skill。这样，下次执行类似任务时，它就会直接通过 Skill 实现。输入提示词：“将操控 Codex 的整个流程的最佳实践写成 Skill，让 Cloud Code 将整个流程固化成一个 Skill。” 这样下次执行时就不需要耗费大量时间进行尝试。

提示 Skill 已创建成功并已安装。通过这种方式，每当用 Cloud Code 完成对应的 Compute Use 任务，都可以让它将整个流程的最佳实践写成 Skill，下次只需调用该 Skill 就能更快速地完成整个操作流程。

### 总结与展望

通过 Compute Use 制作表格、PPT、PDF 等操作，在上上期视频测试 Cloud 桌面应用 CoWork 和 Code 的 Compute Use 功能时已演示过，本期视频不再重复测试。本期视频通过三个典型案例测试了 Cloud Code 新增的 Compute Use 功能。测试表明，Cloud Code 能够比较顺利地执行 Compute Use 任务。并且，我们可以让 Cloud Code 将执行任务时学到的经验直接写成 Skill，这样下次执行重复任务时，它就能更精准地完成相应的 Compute Use 任务。

本期视频就到这里，欢迎大家点赞、关注和转发，谢谢观看。