---
layout: post.njk
source: https://yage.ai/share/google-stitch-design-md-20260423.html
speaker: yage.ai
title: |-
  Claude Design 和 Google DESIGN.md
  到底是想取代设计师还是想取代码农
date: '2026-04-23'
summary: 本文分析了 AI 设计工具（如 Claude Design, Google Stitch/DESIGN.md）如何优先服务开发者，导致设计师与程序员在小型项目中的角色合并，开发者因其文本化工作流更具优势。Figma 则代表了设计师主导的另一方向。文章指出，AI 在设计领域的未来发展取决于能否弥合工程决策与视觉验证之间的鸿沟。
area: tech-engineering
category: tech-trends
tags:
  - ai-design-tools
  - designer-coder-role
  - agentic-workflow
  - role-convergence
  - design-systems
people:
  - Dianne Alter
  - Jae Lee
  - Mejba Ahmed
  - David East
  - Christine Vallaure
  - Banani
companies_orgs:
  - Anthropic
  - Google
  - Figma
products_models:
  - Claude Design
  - Stitch 2.0
  - DESIGN.md
  - Claude Code
  - Cursor
  - GitHub Copilot
  - Figma MCP server
  - Figma Make
  - Figma AI Skills
  - Figma Code Connect
media_books: []
draft: true
status: evergreen
---

## 一个正在发生的趋势：设计师和码农在小项目上正被合并

这一波 AI
设计工具出来之后，设计师圈子里最常见的焦虑是”我的岗位会不会被取代”。码农圈子里的焦虑是”我现在是不是还得学点设计”。两个岗位各自从自己的角度担心，但一个更简单的观察是：在小公司和简单项目上，这两个岗位已经在事实上合并。一个独立开发者、一个三五人的创业团队、一个需要给
pitch deck 做 mockup 的
PM，现在不用雇设计师也不用雇前端就能把东西做出来。这个现象在企业级产品和高端品牌项目里还不明显，那里对视觉品质、品牌一致性、复杂交互的要求今天的
AI
工具做不到。但从独立项目一路到中型产品这个区间，合并已经是在发生的事。

这篇文章不做”未来会怎样”的预测，只看现在这个趋势在走哪个方向。在岗位合并的地方，一个懂一点另一方的人就够了。那这个人，是懂一点代码的设计师，还是懂一点设计的码农？换句话说，合并之后谁活少钱多？

这个问题在 2026
年这几个月有了一个挺清晰的答案，因为主要玩家都发了新产品，方向出奇地一致。Anthropic
4 月 17 日发布 Claude Design，Google 3 月更新 Stitch 2.0、4 月 21 日又把
DESIGN.md 格式开源成跨工具规范，外加 Lovable、Bolt、v0、Cursor
这一批，全部都是从码农的工作环境出发的。这些工具的入口是输入框，产出是代码，反馈循环是”跑一下看看对不对”。一个从来没写过
CSS
的设计师坐下来用，第一反应会是这东西跟自己平时的工作方式对不上。本文要论证的就是这件事：当前整个
AI
设计赛道的默认答案是让懂一点设计的码农来取代只懂设计的设计师。具体会拆开
Claude Design 和 DESIGN.md
的形态，解释它们看起来像是把设计权交还给设计师、其实仍然是码农工具；然后讲
Figma
正在给出的那条相反方向的答案，以及它到今天只走了哪一半。这个答案不一定是最优的，但对今天主流的产品团队来讲，前一个是默认选择，原因比”谁更聪明”要根本。

## 新发布的几个大产品，全是给码农设计的

先看 Claude Design。Anthropic 4 月 17 日发布，当天 Figma 股价跌约
7%。界面是 claude.ai 左栏的调色板图标，打开是一个对话框加一块实时 HTML
预览。你输入一段自然语言描述你要什么，Claude
生成第一版，然后你通过继续对话、行内评论、拖滑块来调整。输出可以导成
HTML、PDF、PPTX、Canva，也可以直接丢给 Claude Code 接着写代码。

Anthropic
官方给出的五类用户画像：资深设计师、产品经理、创始人、市场人员、销售。后四类的共同点是”想要视觉产出但不想打开
Figma”。The Register 的报道标题是《Anthropic 推出 Claude
Design，因为谁还需要设计师呢？》（theregister.com）。法语评论站
agence-scroll 的原话：“真正的目标用户是非设计师，是那些从来没打开过
Figma 的人。”（agence-scroll.com）产品定位说得很直白。

再看 Google 最近两个动作。3 月的 Stitch 2.0 更新加了 infinite
canvas、语音输入、multi-screen 生成；更值得关注的是 DESIGN.md 的开源，4
月 21 日 Google 把它发成跨工具规范（github.com/google-labs-code/design.md）。Stitch
本身各方评测一致定位为灵感工具，独立设计师 Dianne Alter 在 Qualcomm
开源设计系统上实测后的总结是：“Stitch
生成的截图只能当真实设计文件的参考，不能当设计文件本身。”（designproject.io）

DESIGN.md 并不是 Google 发明的。“用一份 Markdown 文件描述设计系统给
AI 读”这个想法最早出现在 vibe coding 社区（Banani 的 design.md guide
写得很清楚：“vibe coding community started experimenting with moving
stylistic preferences into a separate md instruction
file”），很多独立开发者在用 Claude Code、Cursor 这类工具生成 UI
时发现生成的东西风格漂移，于是自发开始往项目里放一份描述品牌视觉语言的
md 文件当 context。Google 在 2026 年 3 月把这件事内化成 Stitch
的一个产品特性（见 designmd.app：“Standard
introduced by Google Stitch in March 2026”），3 月底 VoltAgent 的
awesome-design-md 仓库启动，短短几周从
Stripe、Vercel、Linear、Notion、Apple、Ferrari、Tesla 等 55
多个网站的公开 CSS 逆向出品牌样本。4 月 21 日 Google 做的动作是把
DESIGN.md 以 Apache 2.0 开源成一份正式规范（github.com/google-labs-code/design.md），配了一个命令行工具和一份
token
命名约定。这个动作的实质是抢占事实标准的话语权：格式本身业界已经在自发用，但没有统一规范；Google
这一步把”以后大家应该怎么写 DESIGN.md”的定义权拿到了自己手里。

DESIGN.md 是一份放在项目根目录的 Markdown 文件，任何 AI agent
打开项目就能读到它。文件里有两层内容并置：前半段是 YAML 写的设计
tokens，定义颜色、字号、间距、圆角、阴影等具体数值；后半段是自然语言写的
prose，解释每一个重要决策的意图。一个最小示例长这样：

```
<code>colors:
  primary: "#B8422E"
  background: "#F7F1E8"
typography:
  heading: "Söhne Mono"

---

这个暖米色做背景是为了把阅读体验往 editorial 的方向拉，
适合长文阅读页面，不适合交易转化页。主色的砖红色在长文语境
里是克制的信号，跟 primary action 按钮组合时不要再叠加饱和的
辅色。Söhne Mono 只用在标题层级，正文保持无衬线。</code>
```

这个形式在业界以前没有过。Design Tokens
Community Group 的 tokens.json 只有结构化数值没有意图；Tailwind 的
config 只有 class 映射也没有 why；Figma 的 Variables 能做语义分层但锁在
Figma 文件格式里，别的 agent 读不到。DESIGN.md 第一次把设计的
what 和 why 放在同一份纯文本里，任何工具都能 git diff 和
version control。

开源的同时 Google 发了一个 @google/design.md
的命令行工具（规范正文见 spec.md），目前有两个子命令。lint
会检查 token 命名是否合规、引用有没有断（比如
{colors.primary} 指向一个不存在的 key）、颜色组合是否满足
WCAG 的 4.5:1 对比度要求，输出结构化 JSON 给 agent
消费。diff 能对比两个版本的 DESIGN.md，分别标出 token
级变动和 prose 级变动，返回一个 "regression": true/false
字段可以直接挂进 CI。这套 CLI 的意思是设计规则从此可以像代码一样
gate：改一个颜色，CI 自动跑 lint
检查你有没有破坏无障碍合规；改一段 prose，diff
能标出哪些判断原则被改了。

开源两周内社区的反响很快。VoltAgent 的
awesome-design-md 集合从 55 多个网站的公开 CSS 逆向出 DESIGN.md
样本，任何人都能把一份 DESIGN.md 丢进项目根目录，让 Claude Code 或
Cursor 按这个品牌的视觉语言生成 UI。Anthropic 的
skills 项目开了一个 issue 讨论把 DESIGN.md 当一等公民跟自己的
SKILL.md 并列。designmd.app 和 design-extractor.com
这样的独立站点把 DESIGN.md 描述成”设计领域的
AGENTS.md”。这是它被关注的真正原因，不是因为它”开源了一个新格式”，是因为它第一次让设计规则跟代码规则拥有同一种工程基础设施：纯文本、可
git、可 diff、可 CI。

DESIGN.md 给谁用，看它的形式就清楚了。YAML
语法、{colors.primary} 引用、命令行 lint、把 DESIGN.md
放进项目根目录跟 AGENTS.md、CLAUDE.md
并列的心智模型，整套都是码农的工作语言。主讲人 David East 是 Google Labs
的 DevRel，Firebase 背景出身。社区那个 55 多个品牌的集合里，DESIGN.md
基本是从网站 CSS 逆向出来的，token 部分准（因为 CSS
本来就是结构化的），prose
部分从品牌的营销页面抄下来就是”值得信赖的金融感”这种话术，不是品牌设计师真正会写在内部文档里的话。DESIGN.md
做的事情是让码农用一种更结构化的方式跟 AI
描述设计系统，设计师本人既不是主要写作者，也不是主要消费者。

## 两种工作节奏的具体差别

输入端：是用文字描述还是用眼睛判断。码农本来就用文字描述意图工作，写代码就是这么做的。把意图描述从代码换成自然语言
prompt，对码农来说是小改动，不是工作方式的颠覆。设计师的日常是用眼睛做判断：这个按钮放这儿对不对、这段文字离图片多远看着舒服、这个色调跟品牌定位是否一致。Claude
Design 和 Stitch
让你输入”把顶部区域再现代一点”，生成结果给你看，再让你在对话里反馈”字再大点”。对设计师，输入端丢掉了她一半的专业能力。独立设计师
Jae Lee 试完 Stitch
之后的原话是：“可选的东西很少，就那么几个颜色、一个取色器、几种 Google
Fonts。”（designerup.co）她期待的是一个能真正编辑的画布，得到的是一个套了壳的对话框。

编辑端：是整屏重新生成还是元素级微调。设计师在 Figma
里的日常操作是”这个 padding 从 16 调到 20、那个行高从 1.4 调到
1.15、这个阴影再柔和一点”，做完立刻看到结果。在 Claude Design 或 Stitch
里你说”把那个按钮往左移 8 像素”，AI
每次解读都不一样；你说”字再细一点”，它可能把整段文字换成另一个字重。Mejba
Ahmed 试过一轮后写：“当你需要把一个东西精确挪 4
个像素，或者让一条基线对齐某个具体网格，Stitch
的自然语言界面就变成了障碍。”（mejba.me）码农本来就不做像素级微调，写完代码看看差不多就行；设计师的工作恰恰在微调上，这种粒度丢失等于把她的核心能力废掉。

交付端：一次性生成还是持续迭代。Google Stitch 的
Experimental 模式下你做完一整个项目才发现导不出到 Figma（Google 员工
Rishabh Chauhan 在开发者论坛亲自确认过）；用
Gemini 3 Pro
模式同样没有导出选项；免费额度用完后会触发一套用户看不到阈值的限流。这些在码农眼里是”工具还不够成熟，等等再用”；在设计师眼里是”花了一下午东西拿不回自己的主工作流”。设计师的工作不是一次性生成一张图就完事，是在一个稳定画布上反复迭代，这一点
Figma 做了十年才打磨到今天的样子。

## 反馈循环的有无决定了谁能先被
agent 接管

三件事放在一起，指向同一个更根本的差别：码农的工作有现成的反馈循环，设计师的没有。这是所有
AI 设计工具为什么优先为码农服务的最深层原因。

码农的工作在过去十年已经被训练得高度文本化。写代码本来就是在用一种混合语言描述意图。更重要的是码农手上有一套完整的反馈循环：生成的代码可以跑、可以测、可以
CI、出 bug 可以打日志看栈。Agent 把他的 prompt
翻译错了，他立刻就知道。这个反馈循环让”码农说自然语言、agent
写代码”这个模式在工程上成立。你不需要码农信任 agent，你只需要码农能验证
agent 的输出，验证不过就重来。

设计师的工作不是这样。她的很多决策是视觉判断、手感、品味，这些东西能不能被自然语言完整表达，行业里从来没有证明过。更麻烦的是反馈循环断了。设计师能看出”这个按钮在
mobile 上触达区域不够大”（视觉判断）、能看出”这个标题跟品牌的 editorial
tone 不搭”（品味判断），但她看不出”这个 API 在 3G
网络下会超时”或”这个组件在 dark mode 下的 focus state 会跟已有 CSS
变量冲突”（工程判断）。如果 agent
生成的东西里夹杂了隐藏的工程决策，设计师在视觉层面没办法验证这些决策，她就是在签一份自己没看过的合同。

换个说法：今天让码农做 principal、让 agent 做
executor，这个模式能跑通，因为反馈通道是现成的，代码能跑能测，agent
翻译错了码农立刻知道。反过来让设计师做 principal、agent 做
executor，这个模式还没跑通，因为反馈通道要现造：agent
必须把工程决策翻译成设计师能在视觉层面验证的东西。这是一个没有现成范式可以抄的产品设计难题。主流
AI
工具选择不碰这个难题，走阻力最小的码农那条路，这不是偷懒，是技术上理所当然的选择。代价是”懂一点设计的码农取代只懂设计的设计师”成为默认结局，不是因为码农更聪明，而是因为码农的工作模式跟当前
agent 技术天然匹配。

## Figma 在做一件不一样的事

到这里结论是所有主流 AI
工具都在让码农吃掉设计师，设计师只能等。但有一个玩家在做完全相反的方向，而且做得没有被主流讨论充分意识到，这个玩家是
Figma。

Figma 过去一年做的 AI 相关动作（Make、MCP server、Code Connect、AI
Skills、Slots）单独看像一堆碎片，但背后的决策原则是一致的：它做的不是”能替代设计师的
AI”，是一套让 agent
必须先经过设计师的规则。这套规则有两条。

第一条，设计师的 Figma 文件是所有 agent
的真相源。这条原则的意思是，不管你是 Claude Code、Cursor 还是
GitHub Copilot，你想写前端代码，应该先来 Figma
读设计师的文件，而不是让码农重新用 DESIGN.md 或者截图给你描述一遍。Figma
把这条原则变成产品的动作是 MCP server：码农在 Cursor 里写代码时，Cursor
会在后台持续读 Figma
文件里的颜色变量、组件定义、布局约束，生成的代码自动跟设计师的源文件对齐。设计师改了按钮圆角，下次
Cursor
生成代码时自动跟着改。设计师在这个循环里不是”交完一份设计文件就没事了”，而是持续定义语义，agent
和码农都从她这里读。

第二条，agent
只能在设计师预设的约束里工作。这条的意思是，agent 在 Figma
画布上不能自由发挥，只能用设计师定义好的组件、变量、字体做装配。Figma
把这条变成产品的动作是 AI Skills：skill 是用 Markdown 写的流程指令，告诉
agent 该怎么在这个 Figma
文件里做事，比如”从代码库同步一个新组件过来”、“基于现有组件生成一个新 UI
屏幕”、“跨代码和 Figma 同步 tokens”。agent 不能离开 skill
规定的边界去发明新视觉。换句话说 Figma 给 agent
戴上了设计师预先设定的脚镣，agent
做的不是”无中生有”，是”在已有语义层上装配”。UX Collective 上 Christine
Vallaure 对这件事的观察是：“agentic AI
的默认方向是往效率走，往那个已经存在的零件库里快速上色。设计师真正要做的事，是先保证那个库里有值得装配的东西。”（uxdesign.cc）

这两条原则加起来，跟 Claude Design 的方向完全相反。Claude Design
说”设计从输入框开始”；Figma 说”设计从设计师的画布开始，画布背后才接
agent”。前者是用 AI 绕开设计师，后者是让设计师成为 agent
生态的上游。Figma 今天是离”设计师主导的 agentic
system”最近的玩家，原因不是技术更强，是出发点对。

但 Figma 也没把事情做完。Figma Make 目前生成的代码只支持
React，设计师想做 Flutter、SwiftUI、Vue、原生 HTML
都不行。更本质的限制是 Figma 仍然是纯前端视角，做不了全栈。设计师如果在
Figma 里说”这里显示用户最近 5 条订单”，她还是需要一个码农定义
API、数据库 schema、加载逻辑。Figma
自己没办法把这个意图翻译成工程决策再给设计师一个视觉表达让她验证。前面讲的”设计师无法验证工程决策”这个问题，Figma
还没解决。所以更准确的说法是，Figma 走完了设计师主导的前半程（agent
在视觉约束下装配），没开始走后半程（agent
把工程决策翻译回视觉）。两段加起来才是完整的”设计师能取代码农”的产品。

## 今天你能做什么

如果你是设计师。不要慌，也不要假装 Claude Design 和
Stitch
是你的工具。它们真正服务的是产品经理、创始人、市场人员，是把”我需要一个粗糙的
mockup”这种活从你的输入队列里拿走了。你的工作会从”帮非设计师把想法可视化”上移到”在他们的粗糙产出上做真正的设计判断”。同时花时间把
Figma 的 AI 路线摸一遍：MCP server、Make、Skills、Code Connect
这一套组合在 2026 年的意义是你第一次可以持续地、系统性地定义一个 agent
生态的语义来源。学这个比学 Claude Design 划算得多。

如果你是码农或产品。这些工具让你能做以前必须找设计师才能做的事，但
Claude Design 和 Stitch
的产出是灵感级的，不是可以直接发布到生产的级别。做内部原型、做给老板看的演示稿、早期验证都可以；做正式上线的产品会在无障碍合规、品牌一致性、边界情况上翻车。如果团队里已经有设计师，别急着学
DESIGN.md，先学 Figma MCP：让 Cursor 或 Claude Code 直接读设计师的 Figma
文件，比任何人工同步的 DESIGN.md 都准确。DESIGN.md
作为在没有设计师的项目里跟 AI 对齐视觉规则的格式是有用的，但不是 Figma
的替代。

如果你在想产品机会。“面向设计师的 agentic
system”不是没人做的空白，Figma 正在做。真正的空白在 Figma
做不到的那几块：非 React
输出的设计-代码闭环、工程决策的视觉翻译、全栈意图标注。这几个方向任何一个做对了，都能服务今天没被好好服务的那群人：想主导全栈产品但不想变成码农的设计师。

设计师和码农这两个岗位在小项目上已经在合并。合并后是懂一点码农的设计师活少钱多，还是懂一点设计师的码农活少钱多？今天主流
AI 工具给的答案是后者。答案之所以成立，不是因为码农更聪明，是因为 agent
技术今天的接口天然贴合码农的工作模式。但这个答案不是唯一答案，Figma
在给另一个答案，而且它走到的位置比主流讨论意识到的要远。哪个答案最终占上风，要看
Figma 能不能把后半程走完，也要看有没有新玩家在 Figma
做不到的那几块上做出东西。如果你两种工作都沾一点，挑一边深下去比两边都浅更重要。