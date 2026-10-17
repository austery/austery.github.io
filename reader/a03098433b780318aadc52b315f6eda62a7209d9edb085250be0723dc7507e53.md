---
layout: post.njk
source: https://yage.ai/share/claude-design-reverse-engineering-20260607.html
speaker: yage.ai
title: |-
  Claude Design 背后的工作分解：从开源插件反向推理一位
  AI 设计师的运作方式
date: '2026-06-07'
summary: 本文通过剖析Anthropic开源的Claude Design工作流插件，揭示了AI设计师的运作逻辑：不是简单依赖模型推理，而是通过任务拆解将设计工作划分为多个评价标准明确的认知单元。文章强调了概念锚点对AI审美输出的重要性，以及将设计评价体系工程化、标准化，并与具体工具解耦的必要性。核心在于将‘如何判断设计好坏’的评价标准框架化，而非单纯提升模型参数能力。
area: tech-engineering
category: ai-application
tags:
  - ai-design
  - design-workflow
  - prompt-engineering
  - ai-evaluation
  - progressive-disclosure
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude
  - Claude Design
media_books: []
draft: true
status: evergreen
---

Claude Design
上线后，社交媒体上反复出现一类帖子：一个人截张图，说花了 5 分钟让 Claude
生成了一整套 brand kit、一个 landing page、一个 marketing
one-pager，“效果比我在 Figma 里做三天还好”。

这些帖子展示了结果，没有解释成因。Anthropic 没在 launch
文章里展开技术细节，Claude Design 的内部 prompt 是封装的。

但他们把一套设计工作流插件开源在 GitHub 上了。这套插件没有标注”这就是
Claude Design 的内部实现”，它和 Claude Design
共享同一个问题域。把它拆开来看，能反向推出一位 AI
设计师是怎么被组织起来的。

## 一次 design sprint，六个人

想象一个设计团队在做 sprint。你走进去，看到的不是一个人对着
Figma，而是六个人在做不同的事。

有人在做设计评审。她在评估布局的 visual
hierarchy，检查交互流程有没有不必要的步骤，对比当前稿和 design system
的一致性。她的输出不是”感觉不太对”，而是按 severity 分级的 finding
list，每个问题带具体 recommendation。

有一个人在管 design system。他在 audit 组件的命名是否一致，token
的使用覆盖率有多少，每个组件的 states 和 variants 是否完整。

第三个人在做 developer handoff。他从设计稿里提取 measurement、token
reference、responsive breakpoint、animate
spec，写出了组件属性表、状态互动矩阵、edge case 覆盖清单。原则写在他的
checklist 第一行：“不要假设任何事。你没写的，开发者就会猜。”

第四个人在写 UX copy。她在给每个 CTA 按钮、error message、empty
state、confirmation dialog 写三个备选，标注 tone 的差异，带上
localization 的注意事项。

另一个人在跑 accessibility scan，按 WCAG 2.1 AA 的每条 criterion
逐项检查颜色对比度、键盘导航和屏幕读者行为。还有一个人在 synthesize
上一轮用户访谈的 transcript，把它们转成 theme、insight、opportunity 和
user segment。

这不是六个不同的人。这是 Anthropic 开源的 Design
插件。它把设计工作分成了六类 activity，每一类给了 Claude
一份专属的操作指引。

## 分成六个不是随意的

把设计 critique 和 research synthesis 的要求混在一个 prompt
里，不是不可以，但效果不好。设计评审关心的是 visual hierarchy 和
usability consistency，它需要的质量标准和对错判断是一套。UX copy
需要的质量标准完全是另一套：clarity、tone、actionability，以及是否用最少的话说出了完整意思。混在一个
prompt 里，模型没法在两个标准之间切换。

人类设计师不会一边画 mockup 一边排 accessibility audit
checklist。这两个工作模式需要的注意力结构不同。Audit 需要逐条对照、做
checklist traversal；critique 需要全局扫描、做 holistic
judgment。把不同注意力模式的任务分开，是为了让每一个子任务有干净的评价标准。

Anthropic 的 plugin 结构暴露了这个判断：六份
SKILL.md，分别定义了各子任务的 context、input、rubric 和 output
format。Claude
在合适的场景下自动加载对应的那份指令。每一份指令的目标词数控制在
1500-2000 词。超出这个范围的知识被移到 references
folder，只在需要时加载。这就是 progressive
disclosure
的工程意义：让模型在合适的时刻只拿到它需要的判断框架，不被无关标准污染注意力。

## 审美不是让模型”画得更好看”

如果说 Design 插件负责的是设计工作流，那另一个独立的 Frontend Design
插件负责的是更难的一件事：让 AI 的前端输出有审美。

普通 LLM 的默认前端输出已经有审美了，但这个审美是训练分布里的
statistical average。它不需要学习什么是好的
design，它只需要学会大多数网页长什么样：Inter 字体、紫色渐变、居中
hero、卡片布局、圆角按钮、白色背景。这不是模型不会做设计，是模型太会做了，但做的是
consensus design。

Anthropic 没有优化模型。它只写了一小段 prompt。这段 prompt
的核心是：先选一个大胆的概念方向，再做执行。

“在你开始写代码之前，先确定你的 aesthetic direction：是 brutalist
minimalism，还是 maximalist chaos，还是 retro-futuristic，还是 art deco
geometric，还是 organic natural。”这一段不是
suggestion，是硬性约束。“永远不要用
Inter、Roboto、Arial、系统字体。不要用紫色渐变在白色背景上。不要收敛到同一套选择。”

模型的本能是往平均走。这句 prompt 告诉它：你先选一个 extreme，然后用
typography、color、motion、composition、background detail 五个维度把
extreme 执行到极致。选了
maximalist，代码就应该有复杂的动画、非对称布局、多层纹理。选了 refined
minimalism，代码就应该在负空间、字距和微妙过渡上用力到强迫症的程度。

这份
prompt只有 42 行。没有调用任何外部模型，没有接入任何
API。它就是一段纯文本，注入到 Claude
的前端任务上下文里。但它做了一件一般 prompt
做不到的事：在模型启动设计思考之前，先把搜索空间从”平均
UI”推向了”有概念方向的 UI”。

这件事说明了一个规律。给更多细节（“按钮用蓝色、圆角 8px、padding
16px”）只能把模型钉在一个具体的平均值上。给一个概念锚点（“这是 brutalist
minimalism”），再让细节全部服务这个概念，模型才有一个不往平均走的理由。概念锚点是
taste 的源头。

## 连接的是信息来源类别，不是特定
SaaS

Design 插件还给每个子任务配了 connector。它的 .mcp.json
里预配置了 Slack、Figma、Linear、Asana、Atlassian、Notion、Intercom
等工具。但指令里并没有对任何子任务说”从 Figma
提取”。它用的是占位符：Design Tool、User Feedback、Knowledge Base、Project Tracker、Product Analytics。在
Anthropic 的插件系统里，这些占位符（源码里写作
~~design tool
等形式）会在运行时被替换成对应用户实际连接的服务。

CONNECTORS.md
把这个抽象讲得很清楚。每个子任务需要的信息属于一个类别：

design critique 需要 Design Tool、User Feedback 和 Knowledge
Base。design handoff 需要 Design Tool 和 Project Tracker。research
synthesis 需要 User Feedback、Product Analytics 和 Knowledge Base。

每个类别是一个 slot，可以插入不同的具体工具。Design Tool 这个 slot
里可以是 Figma、Sketch、Adobe XD 或 Framer。Project Tracker 里可以是
Linear、Asana、Jira 或 Shortcut。User Feedback 里可以是
Intercom、Productboard 或 Dovetail。

这个抽象的价值在这里：设计工作流问的是”有没有方法拿到设计文件的原始结构和
token”，不是”有没有
Figma”。问的是”有没有渠道看到用户的真实抱怨”，不是”用不用
Intercom”。把依赖从具体产品抽成信息类别，组织换工具不会破坏工作流，只是换一个
slot 的填充物。

## Claude Design 不只是个插件

把 Design 插件和 Claude Design 产品等同起来是不准确的。Claude Design
产品还有一个 canvas、一套交互式 refinement 机制、一套从 codebase
自动提取 brand design system 的 onboarding 流程，以及一个把设计打包成
Claude Code 可消费的 handoff bundle 的工程层。这些都是产品体验，不是
plugin 自己就能解释的。

但这里有一个比产品形态更重要的判断。

Design 插件给 Claude 的，不是”更深的设计知识”。Claude
本来就知道什么是一个好的设计。插件给它的是设计领域的
评价体系：怎么 critique 才叫好的 critique，怎么 audit 才叫好的
audit，什么样的 handoff 才算完整，什么样的 UX copy
才算清晰。这些不是能力注入，是判断标准的转移。

这就是
evaluation-first 的思路在 AI
工具设计中的体现：不是让模型更聪明，而是给它一套判断”什么算好”的框架。模型本身是通用
reasoning engine，它不知道怎么 critique 一个设计才是好的
critique，不是因为它不够聪明，是因为它没有被给过 critique
的具体操作结构。这个插件给了它这个结构：先评估 first impression，再按
usability、visual hierarchy、consistency、accessibility
四个维度逐个检查，每个 finding 带 severity 和 recommendation。

同样的分解思路也藏在 Anthropic
的其他开源插件里。engineering 插件把代码审查拆成 bug
detection、project guideline compliance、code
quality；legal 插件把合同审查拆成 NDA triage、compliance
check、vendor risk assessment。去 GitHub
上翻一下，会发现同一个模式：先定义”一个优秀的合同审查者在读合同时的具体思考方式”，再让
AI 去审查合同。

Anthropic 现在有三个设计相关的输出：Claude Design 产品做
text-to-prototype canvas，Design
插件做设计工作流能力包，Frontend Design
插件做代码输出的审美注入。三层处理了同一个问题的三个层次：设计能力的上限不取决于用一个更强的模型做一次更好的生成，而取决于有没有把设计判断分成可管理的认知单元，分配给正确的时刻和正确的上下文。

Skill
类的产品天然面临 commoditization
风险：一旦工作方法和评价体系被标准化并公开，它的差异化窗口就在收缩。Anthropic
选择开源这些插件，恰恰说明他们判断真正的价值不在 prompt
本身，而在整个生态里谁能把评价体系变成产品。把”知道怎么判断”变成一个可分发、可定制、可连接外部上下文的系统。Claude
Design 让人觉得惊艳的核心原因可能就在这里。它不是 model
改了，是工作的组织方式改了。