---
layout: post.njk
source: https://yage.ai/share/ai-chat-privilege-survey-20260417.html
speaker: yage.ai
title: |-
  找律师之前「先问问
  AI」：在美国，这些准备笔记已经不受法律保护
date: '2026-04-17'
summary: 在美国，使用消费者版 AI（如 ChatGPT）为法律事务做的准备，即使之后交给律师，也不受律师-客户特权保护，可能成为可被披露的证据。此判决提醒用户需谨慎对待 AI 交互的保密性。
area: society-thinking
category: politics-society
tags:
  - ai-tools
  - legal-tech
  - data-privacy
  - attorney-client-privilege
  - court-rulings
people:
  - Jed S. Rakoff
  - Bradley Heppner
  - Anthony Patti
  - Sam Altman
companies_orgs:
  - Anthropic
  - OpenAI
  - Google Gemini
  - GWG Holdings
  - DOJ
  - FBI
products_models:
  - Claude
  - ChatGPT
  - Gemini
media_books: []
draft: true
status: evergreen
---

## 一个被严重低估的使用场景

很多人在真的付钱找律师之前，会做一件看起来非常合理的事：先自己理一遍事情经过，想想自己这边有什么弱点、对方可能怎么打、哪些条款对自己不利。以前这件事用
Word 文档或者笔记本完成，现在越来越多人用 ChatGPT 或 Claude。AI
可以帮你把散乱的事实整理成时间线，指出你没想到的法律角度，甚至起草一份辩护草稿供自己琢磨。

这个使用场景里藏着一个多数人没意识到的法律风险。2026 年 2
月，美国纽约南区联邦法院在一起证券欺诈案里判决：被告用 Claude 准备的 31
份辩护思路文件，既不受律师-客户特权保护，也不属于 work-product
豁免，必须全部交给检方。判决里最重要的一句话是：事后把这些 AI
对话交给律师，不能把本来不受保护的内容变成受保护的。换句话说，你在找律师之前做的”自我准备”，在法律上不会因为你之后找了律师而获得任何追溯性的保护。

对不熟悉美国法律的读者，这里需要先补一层制度背景，否则后面的讨论容易错位。

## 律师-客户特权是什么，以及为什么这件事值得单独关心

美国法上的 attorney-client
privilege，直译是”律师-客户特权”，但它和通常说的”律师保密义务”不是同一件事。律师的保密义务是职业伦理层面的：律师不能主动把客户的事情告诉别人。特权则是证据法层面的：在法院诉讼或政府调查中，客户和律师之间符合特定条件的通信，对方不能强制你或你的律师出示、对方不能传唤律师去作证；甚至如果这些通信因为失误被对方看到了（比如邮件误发、文件误交），你仍然可以请求法院把它从证据里排除，特权本身不会因为一次意外泄露就丧失。简单说，保密义务约束的是律师该不该说，特权决定的是法官能不能强迫你说、对方律师能不能拿这段通信当证据用。

这个区别在日常生活中感受不到，卷入纠纷时就很关键，而且特权真正的威力要在当事人有过错的场景下才看得清。假设一起车祸之后你跟律师坦白：“其实那天我看了一眼手机，绿灯亮了我才抬头”。如果这段对话受特权保护，对方律师在诉讼中没办法把它调出来——即便对方不知怎么辗转拿到了这段对话的副本，法院也会拒绝采信。如果不受保护，这段自白跟你发给朋友的一条微信没有法律地位上的区别，都可以被要求交出、都可以成为让你承担全部责任的证据。特权的逻辑不是”保护无辜”，而是”即便你真的做错了事，也应当能够毫无保留地跟律师讨论该如何应对”——因为只有当事人对律师说真话，律师才能给出真正有用的辩护。这是美国法律刻意设计的激励结构。美国的民事诉讼有一套叫证据开示（discovery）的制度，强度远超许多其他法域：诉讼一旦启动，双方几乎有义务交出所有与案件相关的书面材料，包括邮件、短信、云盘文档、聊天记录。特权是这个大网上少数几个法定例外之一。

能享受特权的几类关系是有限的：律师-客户、医生-患者、治疗师-患者、神职人员-忏悔者、夫妻。核心要件都类似：关系本身具备法律认可的保密预期，对话内容是为了该关系的专业目的，交流渠道没有不必要地暴露给第三方。任何一个要件不满足，特权就不成立。

现在把这个制度框架对准本文开头那个使用场景：你在找律师之前用 ChatGPT
整理案情。首先，Claude 或 ChatGPT
不是律师，不满足”律师-客户”的关系前提。其次，你输入的内容被平台保留并可能被用于训练、可能应法律程序被交给第三方，保密预期不成立。第三，这些对话发生在你聘请律师之前，不存在律师的指示。三个要件全部失败。Rakoff
法官 2026 年 2 月的判决把这个逻辑第一次明确地写进了司法意见里。

更反直觉的一层是：这件事不可以通过”把文档给律师看一下”来修复。普通人直觉上会觉得，既然我之后找了律师、把这份
AI
起草的笔记给他看了、我们一起讨论了，这份笔记就成了律师工作的一部分，应该受保护。法官明确否决了这个直觉。原文是：“Non-privileged
communications are not somehow alchemically changed into privileged ones
upon being shared with
counsel.”意思是：非特权通信不会因为事后交给律师就变成特权通信。这句话被各大律所的客户提示反复引用，因为它击穿的正是普通人最容易依赖的那层心理安全网。

所以本文的核心判断一句话：在美国的法律体系里，目前用消费者版
ChatGPT 或 Claude
做的任何”法律性”自我准备（无论是找律师之前还是找律师之后自行使用），都应当被当作未来可能被对方律师、检察官或监管机构读到的书面材料来对待。不是因为会真的被读到，而是因为法律上阻止别人读到的防火墙并不存在。

## 判决本身：事实背景与三层论证

2026 年 2 月 17 日，纽约南区联邦法院法官 Jed S. Rakoff 在 United
States v. Heppner（案号 25-cr-00503-JSR）签发书面意见。判决
Memorandum 全文被告 Bradley Heppner 是 GWG
Holdings（已破产的零售债券发行商）的前主席，被指控通过壳公司挪用投资人资金超过
1.5 亿美元。DOJ
起诉信息在 2025 年 10 月 28 日由大陪审团作出，11 月 4
日解封并发出传票，Heppner 次日被捕。被捕当天 FBI
搜查其达拉斯住所，在电子设备上发现 31 份他与消费者版 Claude
的对话记录。内容是他让 Claude
帮忙拟的辩护思路，讨论”面对起诉事实该如何抗辩、法律上可以如何主张”。这些对话发生在收到大陪审团传票之后、正式起诉之前。他的律师事后确认：“counsel
did not direct Heppner to run Claude
searches”，也就是他完全是自己跑去找的 Claude。BKLW
案件分析

这一事实模式几乎就是本文开头那个”找律师之前先用 AI
理一遍”场景的刑事版放大镜。Heppner 和绝大多数个人 AI
用户的行为链条是同构的：先用消费者 AI
整理思路、产出一份可以拿给律师看的草稿，再带去见律师。区别仅在于他已经被刑事调查、涉案金额上亿，所以政府直接拿着搜查令上门取证。对普通读者理解判决的射程而言，重点不在他涉案多严重，而在这条行为链条在法律上每一步为什么都不成立。

Rakoff 的推理分三层，每一层独立地足以让特权失效。

第一层是律师-客户特权的基础要件：通信必须发生在律师与客户之间。Rakoff
直接写道：“In the absence of an attorney-client relationship, the
discussion of legal issues between two non-attorneys is not protected by
attorney-client privilege. … Because Claude is not an attorney, that
alone disposes of Heppner’s claim of privilege.”（Memorandum 第 6–7
页）Reuters的报道里给出了更锋利的版本：“No
attorney-client relationship exists, or could exist, between an AI user
and a platform such as Claude.”

第二层是保密预期要件。Rakoff 专门援引了 Anthropic
的消费者隐私政策原文，认定该政策明确约定 Anthropic 会收集 inputs 和
outputs、用于训练模型，并保留在涉及 claims, disputes, or litigation
时向政府监管机构和其他第三方披露的权利。既然平台用自己的条款预告了披露可能，用户”could
have had no reasonable expectation of
confidentiality”。这一推理和具体的搜查令无关：政策本身就破坏了保密预期。Dentons
判决分析

第三层是”事后不能补救”，也是对普通用户最具打击力的部分：“Non-privileged
communications are not somehow alchemically changed into privileged ones
upon being shared with counsel.”（引自 Freshfields
博客 和 NatLaw
Review 的总结）同样逻辑下 work-product
豁免也失败。这条豁免要求材料”由律师或在律师指示下”为预期诉讼准备，Heppner
的自发行为不满足要件。

## 法官留了两扇门，但两扇门都不通向普通用户

Rakoff 明确在意见中留出两种例外。

第一扇门是 Kovel 延伸理论。如果律师正式指示客户使用
AI 作为翻译、助手、数据分析工具（类比 1961 年的 United States v.
Kovel 中律师聘请的会计师），AI
可能被视作律师的”代理人”，因此保持特权链。Rakoff 写道：“Had counsel
directed Heppner to use Claude, Claude might arguably be said to have
functioned in a manner akin to a highly trained professional who may act
as a lawyer’s agent within the protection of the attorney-client
privilege.”（Memorandum 第 7–8
页）这扇门对律师有用，对个人用户几乎没用。普通人在跟 ChatGPT
聊天之前，通常没有律师在那儿指示什么。

第二扇门是企业版 / 零数据保留协议。Rakoff
没有正面裁决，但在 dicta 中暗示：如果 AI
服务的合同条款承诺不用于训练、不对外披露、零数据保留，confidentiality
要素可能成立。O’Melveny 的分析写得比较直白：“some generative AI tools
(including Claude) offer enterprise versions that provide assurances of
confidentiality and make clear user inputs will not be used for
training—which could at least arguably give rise to a ‘reasonable
expectation of confidentiality’。”O’Melveny
客户提示但这扇门同样对个人用户基本关上：OpenAI 的 ChatGPT
Enterprise、Anthropic 的 Claude for Work、Google Workspace Gemini
都是组织订阅产品，年费以数万美元起计，普通用户没有这种合同。

哈佛法律评论的评论员 Elizabeth Guo
指出了这两扇门之间的矛盾：判决同时抬高了两个门槛，既要厂商架构过关，又要律师正式介入，普通客户的日常
AI 使用被夹在中间没有安全港。Harvard
Law Review

## 相反的判例：关键在于”谁在拿笔”

Heppner 不是唯一的判例。密歇根东区的治安法官 Anthony Patti 在 2026 年
2 月 10 日（比 Heppner 的台上裁定还早了几小时）在 Warner v.
Gilbarco 中得出了相反结论：一位无律师代理的 pro se 原告，她自行用
ChatGPT 起草就业歧视诉状的行为，被认定属于个人的
work-product，不必交给被告雇主。Patti 写道：“ChatGPT (and other
generative AI programs) are tools, not persons, even if they may have
administrators somewhere in the background.”Warner
v. Gilbarco 判决

再往前，2024 年 8 月北加州的 Tremblay v. OpenAI 案中，Judge
Martínez-Olguín 认定原告律师精心构造的 ChatGPT prompts 属于”opinion work
product”：因为 prompts 里嵌着律师的 mental impressions，所以受保护。Tremblay
判决

Baker Donelson
律所把两组案件的区别浓缩成一句话：区别在于是谁拿着笔。律师拿笔，对话里带着律师思路，work-product
可能成立；客户自己拿笔，独立去咨询 AI，则不成立。判例的分歧并不在于”AI
对话能不能受保护”，而在于”这段对话的源头是不是律师的思考”。对绝大多数把
ChatGPT 用作日常助手的普通人来说，这个区别的答案稳定地指向：不成立。

## 平台政策：三家厂商其实都在同一条线上

关于”我付了订阅费应该能有更多保护吧”这种直觉，需要直接用隐私政策文本来校正。

OpenAI 的隐私政策（2026 年 2 月 6 日版）写得很坦率：OpenAI Privacy
Policy

> “If we are legally required to retain your data (for instance, we
> receive a lawful subpoena) then we may retain it for the duration of the
> relevant legal or regulatory obligation.”

其 Law
Enforcement Policy 规定：对于非内容数据（账户信息），需要 subpoena
或等效文书；对于内容数据（你的 prompts 和
outputs），需要搜查令或等效文书。2025 下半年的透明度报告显示，OpenAI
收到 224 件非内容请求（披露 146 件，涉及 307 个账户）和 75
件内容请求（披露 62 件，84
个账户）。这些数字不是假设，是正在发生的事。

Anthropic 在 2025 年 8 月更新消费者条款，引入”opt-in
训练同意”：同意用于训练的用户，数据保留期从 30 天延长到 5
年；不同意则维持 30 天。商业客户默认不用于训练。Anthropic
政策更新关于政府请求，Anthropic 的 Law Enforcement
Requests 说明 明确：“Anthropic PBC discloses account records solely
in accordance with our Terms of Service and applicable law.”
有效法律程序同样开门。

Google Gemini 的消费者默认保留期是 18 个月，用于人工审阅的对话可能被
Google 独立保存长达 3 年，即便用户关闭了 Activity 记录。Gemini Apps
Privacy Hub

三家公司的政策结构完全同构：都收集 prompts 和
outputs，都保留响应合法程序的权利，都把”法律允许时通知用户”作为软承诺。Heppner
判决里援引 Anthropic 政策的那段推理，放到 ChatGPT 或 Gemini
上几乎可以原样成立。STACK Cybersecurity 的总结是：判决的依据不是”Claude
这个品牌”，而是”消费者版 AI 的隐私政策结构”本身；换个
logo，推理不变。STACK 分析

## 对普通用户的三种具体场景

第一种是本文开头就点到的场景：真的在找律师之前”先问问
AI”。这是 Heppner
裁决最直接打击、也最容易被低估的场景。你在预约律师之前，用 ChatGPT
把整件事从头到尾梳理一遍，让它帮你分析己方弱点、预测对方可能的攻击角度、整理一份带时间线的事实陈述。这整个流程看起来是负责任的准备工作，既节省了律师按小时计费的钱，也帮律师更高效地切入案情。

在法律上，这份梳理文档的地位和你存在云盘里的任何一份 Word
文档没有区别，甚至更脆弱：它不仅存在你这边，还同时在 AI
厂商的服务器上有一份。后面如果纠纷升级到诉讼，对方律师通过两条路径都能把它拿到。一条是在
discovery 中直接要求你交出”与本案有关的任何 AI 工具对话记录”，另一条是向
OpenAI、Anthropic 发第三方
subpoena。把对话交给你自己的律师看过、一起讨论过，都不改变这份文档本身的法律性质。它还是非特权通信。

更具体的伤害在对话内容本身。人在整理案情给 AI
看的时候，倾向于把话说得比跟律师面对面时更直白，因为面对一个看起来不会评判你的机器更容易松口。一位合同纠纷当事人可能会输入”我知道我当时签的时候有点冲动，条款里那条违约赔偿条款我确实没仔细看”。这句话和他在法庭上需要坚持的立场完全相反。一旦这段对话被
discovery
到，这句话会被对方律师印出来做展示证据。讽刺的是，越是认真准备、越是诚实地跟
AI
交代细节的人，越容易给自己埋炸弹。跟专业律师面对面时，即便是诚实的客户也会在律师”等一下，这部分先别说，让我问你一个具体问题”的引导下把话说得更有结构。AI
目前还不会做这种引导性保护。

第二种是工作和合同纠纷中的日常 AI 使用。你用 ChatGPT
起草了一封辞职信、分析过一份供货合同里哪条对自己不利、让 AI
帮忙回复过一封让你火大的客户邮件。这些看似日常的使用，在后续真的卷入劳动仲裁、合同违约、商业诉讼时，都会成为
discovery 请求的目标。Fisher Phillips 在其 2026
年的客户提示里直接写道：“AI-generated ESI, especially from notetakers,
meeting summaries, auto-drafted emails, and chat assistants, is becoming
a core discovery battlefield in employment cases.”Fisher Phillips 提示Ward and
Smith 给离婚客户的提示更直白：“Receiving a subpoena demanding ‘all
communications with AI-based tools, including prompts, inputs, and
outputs’ related to your divorce or custody dispute is now a realistic
possibility.”Ward
and Smith

第三种是把 AI 当情绪出口。Sam Altman 在 2025 年 7 月
Theo Von 的播客里亲口承认这个缺口：“People talk about the most personal
sh** in their lives to ChatGPT… if you talk to a therapist or a lawyer
or a doctor about those problems, there’s legal privilege for it… And we
haven’t figured that out yet for when you talk to ChatGPT.”TechCrunch
2025-07-25持照治疗师受 therapist-patient privilege、医生受
physician-patient privilege、神职人员受 clergy
privilege，这些特权在绝大多数美国州法律下严格保护对话内容。跟 ChatGPT
的对话不在任何一类特权下。如果你后来卷入监护权争夺、人身伤害索赔、保险纠纷，对方律师拿到你跟
AI
倾诉的情绪记录的法律障碍极低。而这类对话里往往包含”我知道我那天喝了一点酒所以开车的时候反应慢了”、“其实我对我孩子确实失控过一两次”这种在法律层面极为昂贵的自白。

## 律师们开始写进合同里的新条款

实务界反应很快。纽约的 Sher Tremonte 律所在 Heppner
判决当日发布客户提示，并把这条写进了客户协议：“disclosure
of privileged communications to a third-party AI platform may constitute
a waiver of the attorney-client privilege”（经 Reuters 转引）Kobre
& Kim 的合伙人 Alexandria Gutiérrez Swette
的标准表述已经进入各大报刊：“We are telling our clients: You should
proceed with caution here.”

Debevoise & Plimpton
给律所客户的操作建议是：如果确实需要在律师指示下用 AI
做研究，建议在对话开头写明”I am doing this research at the direction of
counsel for X litigation.”，这是为了给未来可能的 Kovel agency
主张预留一个书面锚点。Debevoise
客户提示但需要明白这是律师为了应对不确定性做的预防动作，不是法律上已经承认的豁免；而且适用对象是有律师代理的客户，不是普通用户。

## 一个可以装进脑子里的判断框架

判例还会演化。“AI
privilege”在国会立法或州层面也许有朝一日会被承认。佐治亚理工的隐私法学者
Peter Swire
就建议只对”聊天机器人明确承担律师或医生角色”的有限情形赋予特权，而不是对所有
AI
交互一刀切。但在立法承认之前，对普通用户而言，以下几条判断基本够用：

默认假设 1：你跟消费者版 ChatGPT / Claude / Gemini
的所有对话，都应当被当作”未来可能被他人读到的书面材料”来写。不是因为会真的被读到，而是因为预期自己的行为可以承受被读到的后果。和
email、短信、微信消息是同一类风险，而不是和私人日记或律师对话同类。

默认假设
2：付费订阅不等于保密。让对话更不容易被平台用于训练的，是
Enterprise、Edu、API + ZDR 协议这三种，而不是 Plus / Pro / Team
这种个人订阅。组织订阅通常要求法务介入签合同。

默认假设
3：删除不等于消失。平台在面对诉讼保全令、监管调查、刑事搜查时都可能被要求保留甚至提供”用户以为已删除”的数据。Temporary
Chat
这类功能的保护强度取决于平台当下是否处于司法令覆盖期，不是一个可以长期依赖的属性。

默认假设 4：当你真的卷入诉讼或调查时，不要再上去独立地跟 AI
聊案情。哪怕你觉得”只是想理清思路”。这件事 Rakoff
判决里用最直白的语言说过了：事后交给律师不能解毒。如果律师建议你用
AI，请让他写明”at my direction”；不建议的情况下，停手。

默认假设 5：对情感性、治疗性、高私密度的内容，慎用
AI。不是因为 AI
会主动泄密，而是因为一旦你进入任何诉讼程序（哪怕只是保险理赔或工伤认定），这些内容缺乏治疗师-患者特权那种法律防火墙。

这波判例真正重要的点，不是多少普通人会被拖进法庭，事实上多数人不会。重要的是，AI
正在成为一种”比邮件更像日记、但比日记更像证据”的中间态工具。Heppner
判决给这件事落下了第一块定锚：在法律系统看来，它更靠证据一侧。这个定位会影响之后十年
AI
如何被设计、被监管、被日常使用。在立法出来之前，调整自己的使用直觉，比等到自己出事时再去查资料便宜得多。