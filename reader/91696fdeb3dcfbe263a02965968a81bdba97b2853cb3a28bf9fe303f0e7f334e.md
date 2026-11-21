---
author: AI Engineer
date: '2026-07-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tJFjeMBKbIY
speaker: AI Engineer
tags:
  - ai-trustworthiness
  - financial-ai
  - decision-support
  - data-traceability
  - accountability
title: 为备忘录而生，而非演示：如何构建让金融决策者信任的 AI
summary: 资深投资人 Shawn Chan 结合 15 年跨境交易与 200 场投资委员会的经验，深刻剖析了 AI 时代金融决策的核心痛点——信任。文章对比了演示（Demo）与备忘录（Memo）的本质区别，指出了 AI 导致信任崩溃的六个微观场景，并提出了重构信任的五项技术规范，指明只有真正对决策负责并具备数据可追溯性的 AI 系统，才能赢得专业投资人和金融机构的信任。
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
### 演示与备忘录的本质之辨：金融决策中的“信任游戏”

在金融投资领域，决策的本质并非追逐智力，而是追逐**信任**。演讲者 Shawn Chan 拥有 15 年跨境交易（涉及香港、中国大陆、英国、美国）的经验，参与过 200 场投资委员会会议。他指出，过去 15 年里，他的核心工作就是对那些聪明、自信的人提交的商业报告进行评估，并在公司决定投入上亿美元之前，决定是否相信这份文件。如今，这类自信呈现报告的角色有一部分变成了**智能聊天机器人**（Chatbots）。这些机器人语法完美、排版精美，而且被追问时从不防御，显得极其自信。然而，**自信**（Being sure of yourself）和**正确**（Being right）是两种截然不同的技能。金融界最自信的人往往错得最惨，而 AI 只是更快地学会了这种“自信装蒜”的技巧。

这揭示了金融 AI 产品的致命伤：几乎所有的金融 AI 产品都是为了在**演示**（Demo）阶段取悦人们 5 分钟而设计的，却几乎没有一个能够经受住**备忘录**（Memo）阶段的严苛审视。在“备忘录”阶段，决策者的整个工作就是“不被取悦”，而是挑错。
* **演示（Demo）机器**：只需一个干净的文档输入，输出一个流畅的答案，能让会场在 5 分钟内发出“噢”的赞叹。例如让手机总结一封长邮件。
* **备忘录（Memo）机器**：在真正的资金调动前，需要应对来自委员会的真正质疑。备忘录必须面对数以百页的文件、监管申报、电话录音和各种相互矛盾的信息。备忘录的工作不是让人赞叹，而是在长达数小时的辩论中“存活”下来。

“演示”与“备忘录”之间的差距极其昂贵。2023年2月，某科技巨头在推广其全新 AI 助手的演示中，AI 助手在回答一个关于太空望远镜的简单问题时给出了错误的事实。这仅仅是在一个营销演示中的一句话，却导致该公司股价在一天内下跌了约 8%，蒸发了近 1000 亿美元的市值。因为没有人在发布前问一句：“这个结论是从哪来的？大家检查过了吗？”在真金白银面前，每一句演示台词都必须承受备忘录级别的审查，这世上再也没有绝对安全的“演示”了。

<details>
<summary>Original English Source</summary>

Good afternoon. Thank you for being here, day four of our conference, a room with no windows. Right just after lunch. You are the strongest people in this building.
Let me start with a confession. For 15 years, my job has been one thing. I sitting in a room, a very smart, confident person hands me a piece of paper, and before my company spends a hundred million dollars, I have to decide, do I believe this paper? This year, my job still exactly that. Except now, some of time, the very confident person handing me the paper is a chatbot.
And honestly, the chatbot is often better written than humans, better grammar, nicer formatting, never get defensive when you ask a follow-up question, very very sure of itself. The problem is being sure of yourself and being right are two different skills. Some of most the confident people I have ever met in finance were also the most wrong. AI just learned that trick faster than rest of us.
So, here my whole talk in two sentence. First, almost every AI finance product is built to impress people for five minutes, and almost none are built to survive a room whose entire job is to not be impressed. Second, and this is the part I promised the organizers added the exact same same skills that fix your product is the skills that gets investors like me to write you a check. Same muscle. I've proved both. And I'm telling this now, this week, because a lot of you are about to get pulled into exactly this. Your CEO saw a demo somewhere. Your biggest customer suddenly has a compliance department, or you are 3 months from raising your next round. When any of those days arrive, I'd rather you to hear the hard part from someone who sit on the other side of the table, than discover them live in a room in front of the people who bill by hour.
A quick bit about me. I promise this is the boring part, and I will keep it fast. 15 years of cross-border deals, Hong Kong, mainland China, the UK, the US. Mergers, IPOs, big strategic investment on names you'd actually recognize, the kind of companies that go public, and your LinkedIn feed won't shut up about it for a week. Along the way, I've sit in about 200 investment committee meetings. I have the grey hairs to prove it. I checked. It's not genetics. And here the part that matters for second half of this talk. I've also read hundreds and hundreds of pitch decks, founders' decks, bankers' decks. 47 slide seed decks. I have seen fonts that should be illegal.
200 committee meetings taught me one thing. No textbook says outlawed. The number on the page is not what gets a deal approved. Trust is a number. What gets a deal approved? Money doesn't follow intelligence. Money follows trust, and the trust is fragile, especially when the thing that wrote the page has never once in its entire life said the words, "I'm not sure."
Let me give you one small taste of what those rooms feel like. Early in my career, a very polished, very expensive banker present a beautiful slides full of confident wrong numbers. One senior person in room asked a one quiet question, "Where does this number come from?" The banker posed what felt like an entire physical quarter. The pose taught me more about finance than 3 years of exams did.
So, I'm not here as a builder. I don't build these systems. I sit across the table from them and from the founders selling them, deciding whether to trust them. Today, I'm going to give you both halves of that. What breaks trust in your product and what builds trust in your pitch.
Let's define two machines that everyone keep confusing. Machine one is a demo. One clean document in, one fluent answer out is the whole job is to make a room go oh for 5 minutes. Machine two is a memo. The real document is a real committee race before real money moves. Hundreds of pages, filings, transcripts, broken notes, scratches, someone's rushed notes from a call last Tuesday. Half the sources disagree with each other and the memo's job is not to make you go oh. Its job's to survive an argument. Basically, a family dinner except somebody's uncle brought a spreadsheet.
Here's everyday worship of the gap. Ask your phone to summarize a long email. That's a demo. It's not just sound plausible for 10 seconds. Now, imagine that some same phone has to stand in front of a bank and defend out loud why you deserve a mortgage. Suddenly, plausible isn't enough. Now, it has to be right and it has to prove it. That second situation is what a memo actually is.
Now, you might think the demo world and the memo world never touch. Let me tell you about the most expensive typo in history. February 2023, one of the biggest tech company on the earth launches its shiny new AI assistant with a promotional demo. In that demo, the assistant answers a simple question about a space telescope and it gets a wrong the wrong answer. One sentence one wrong fact about a telescope in marketing demo, the market noticed the company's stock dropped around 8% in a day. That's roughly $100 billion of value gone because of unchecked sentence. $100 billion for one sentence. Nobody in that company asked the one question. Every junior analyst on my team is trained to ask before anything leaves the building, wait. Where does this claim come from? Did everyone check it? So, here's the punchline. Even the demo failed the memo test. The moment real money is watching and the real money is always watching. Every sentence become a memo sentence. There is no safe demo anymore.

</details>

### 信任瓦解的六大微观场景：AI 系统的数据硬伤

在日常使用中，AI 系统对信任的侵蚀往往在以下六个看似微小、却极易预测的场景中默默发生：

1. **来源可信度混淆 (Source Credibility Confusion)**：AI 检索系统（RAG）往往将所有信息源一视同仁。然而，审计申报中的数字是会计师在宣誓后的证词，分析师简报只是聚会上朋友的闲聊，而内部邮件则相当于电梯里听到的传闻。曾有昂贵的 AI 工具把半年前群聊里某个人的粗略猜测当成至理名言 confident 地输出，而真正的审计数字就躺在距离该数据三行之遥的官方申报中。如果系统无法区分审计证词与群聊流言，它就没准备好处理真金白银。
2. **数据矛盾与一致性缺失 (Data Contradiction)**：在备忘录中，第 1 页写着营收增长 18%，第 11 页不显眼的表格却写着 17.4%，这 0.6% 的偏差足以杀死整个项目。决策者关心的不是缺失的比例，而是当事人在简单数学上没把关，在核心问题上会如何“掉链子”。美国某大型房地产公司使用算法大规模自动买房，算法极度自信，但房屋市场的实际价格并不买账。最终，公司计提了近 5 亿美元的资产减记，关闭了整个部门，并解雇了四分之一的员工。
3. **强行平滑冲突 (Contradiction Smoothing)**：当不同来源出现矛盾时（例如 CEO 在电话会上的表态与官方财报申报存在差异），这种分歧（Gap）恰恰是尽职调查中最有价值的部分。然而，AI 倾向于听起来流畅且讨喜，当听到冲突时，它会偷偷选择一个读起来更顺畅的版本并继续前进，掩盖了冲突的存在。
4. **事实与推测混同 (Melting Facts and Guesses)**：AI 喜欢将事实与主观预测融合成一句话，例如“公司可能会在下个季度获得批准”，听起来像事实，但本质上是推测。如果系统将两者熔接，投资委员会就无法看清真相。在某个项目里，一个推测在三版演示文稿的改写中逐渐演变成了“批准已收到”，最后批准并未按期而至，导致了一场极其尴尬的电话沟通。
5. **可追溯性匮乏 (Lack of 30-Second Traceability)**：如果无法在 30 秒内证明一个说法的出处，那么这个说法有多正确都不重要。曾经有纽约律师使用聊天机器人写辩护状，引用了 6 个完美的法庭案例，但这些案例全是 AI 虚构的。律师甚至怀疑地问 AI “这些案例是真的吗？”，AI confident 地回答“是的”。最终，律师被法官罚款。在关键会议中，如果面对质疑你无法“一键直达”源段落，而是要在几十个网页标签页中疯狂翻找，信任就会瞬间崩溃。
6. **责任主体缺位 (Accountability Deficit)**：加拿大某航空公司的客服机器人 confident 地向一位遭遇丧亲之痛的客户承诺可以先买全价票事后申请折扣，但该政策纯属 AI 虚构。在仲裁法庭上，航空公司的辩护理由居然是“机器人是一个独立的法律实体，应为其自身行为负责”。这种说法就如同“狗吃了我的作业”一样荒唐，法庭不予采信，判决航空公司赔偿。你无法将责任外包给软件，在任何真实决策的底部，必须有一个实实在在的**人**签字负责。

<details>
<summary>Original English Source</summary>

Six ways trust quietly breaks. Which source do you believe? Do the numbers agree? Do you hide contradictions or show them? Is that a fact or a guess? Can you prove it in 30 seconds? And whose name is actually on the decision? Six. Keep count with me. I will keep each one short and I will bring receipts.
Model one. Not every source deserves the same trust, but most AI system treat them like they do. Think of like this, a number from an audit filing is your accountant speaking under oath. A number from a analyst note is a friend at a party confident probably from someone's internal email is a thing you overheard in in a elevator. Most of retrieval systems can't tell them these apart. They grab whichever text is close to your question and hand it over like a gospel. True story. Anonymized. I know I once watched a very expensive AI tool confidently called a number from a group chat someone's rough guess texted six months earlier. The model loved the confident freezing. The real audit number was the three rows away in the actual filings. The AI just liked the group chat version better. It sounded more enthusiastic. If your system can can't tell an accountant under oath from a rumor in a group chat, it it is not ready for real money.
Model two. The numbers have to agree each other everywhere, every time. Here's a memo that already died. Page one says revenue growth 18% page 11 little table nobody reads for fun says 17.4 nobody in the room cares about the missing 0.6. They care about what it what it means if this person didn't check the easy mathematics what did they not check on the hard stuff. That memo didn't pass not because of the number because of what number you implied. And if you want the industrial strength version of this failure remember the giant American real estate company that let algorithm to buy houses at scale. The algorithm was extremely confident about the house prices the house disagreed. The company ended up writing off around half a billion dollars shut the whole unit down and let a quarter of the staff go. The model wasn't stupid the model was unsupervised nobody built a boring mechanic machinery that forces the numbers to keep agreeing with reality after lunch day. Fluent and a confident remember is not the same as right.
Model three surprises people. A contradiction is not a bug a contradiction is a gift. If the CEO says one gross number on the earning call and the official filing says the different a different one, the gap is the single most interesting thing in the real story highs. Real diligence leaves for that gap. AI does the opposite. It is a trained to sound smooth and helpful. So, when it hears a conflict, it quietly picks whichever version reads nicer and moves on. You never even learn there was a disagreement. I've sit through exactly these CEO's number and the filing numbers meaningfully different. Neither one Nobody Nobody flagged it. Everyone just used the nicer one. We caught it because one person happened to have both documents open at once. Pure luck. Luck is not a control. Your job as a builder isn't resolve the argument. It's to make sure that the argument happens in front of a human instead of quietly along inside box.
Model four. Facts and the guesses have to live in separate box. And the fluent AI loves melting them into one smooth sentence. Example, the company will likely receive approval next quarter. Reads like a fact. Sounds like a fact. it is a guess. Somebody buys the estimator wearing fact shaped the clothing. A committee's entire job is to agree with the guesses while trusting the facts. If your system melts them together, the committee can't find them seems, and then all all they can do is to is is approve or reject the genuine map of the document. You should not spend a hundred million dollars on maps. I watched approval accept soon. Turn across three drafts of a demo into approval received. Nobody lied. The guess just rose its fact costume a little longer each rewrite until nobody remembered it then it started as a guess. The approval did didn't arrive on schedule. That was an uncomfortable phone call. This fix almost embarrassingly cheap. Label your guesses, a tag, a color, anything that survives being copy pasted into someone else's slides three weeks later.
Model five, if nobody can find where a claim come from it doesn't matter how right it is. You've all heard about the New York's lawyer. Uh he filed a legal brief written with a chat bot's help. The brief cited six court cases, beautiful citations proper proper formatting, very convincing. One small issue, the cases didn't exist. The AI invented invented all six. And here, my favorite detail, the part that should be taught in school. Before filing, the lawyer got suspicious, so he asked the chatbot, "Are these cases real?" And the chatbot said, "Yes." That is like asking the guy who sold you the watch whether the watch is real. The judge fined him. The story went around the world, and my second favorite detail, the fake cases even had a real real estate surrounding names and the page numbers. The AI didn't just lie, it just the formatting. It cited itself beautifully, wrong but beautifully. The license is a 30-second test. When someone points at a sentence and says, "Show me where this come from." You either click once or land on exact source paragraph, or you open seven browser tabs and start swiping. I have personally been the guy with seven tabs in a real meeting while the room full of people watched my scroll. 10 out of 10. Would not recommend. If you remember only one sentence from this whole talk. The click-through is a product. Everything else is well-written packaging.
Model six, my favorite, because it's the most human someone has to sign. Here's the story you probably know. An airline website chatbot told a grieving customer he could book a full-price ticket now and claim a bereavement discount afterwards, that the policy didn't exist. The chatbot made it up politely, fluently, confidently. The customer took the airlines to a tribunal. And the airlines' defense, this is real, was was that the chatbot is called a separate legal entity responsible for its own action. That is the corporate version of my dog ate my homework. The tribunal didn't buy it. The airline paid, and every one of us in our boardroom quietly took a note that day. You can't outsource accountability to your own software. At the bottom of every real decision, a human signs. If your architecture doesn't have a fundable human at the end of it, you you have not built a product. You have built an excuse generator. So, build your AI around that accountable person, not instead of them.

</details>

### 重构信任防线：金融级 AI 的五项技术规范与融资逻辑

针对上述信任危机，Shawn Chan 提出了五项针对性的技术解决规范（The Cures），这是他在准许任何 AI 系统接入真实交易前，向供应商提出的强硬要求：

1. **每项主张附带源凭证 (Receipts for Every Claim)**：系统内的每一句话都必须直接链接到其原始数据段，并标明该数据源的信任评级，而非仅仅在文末提供一个笼统的参考文献列表。
2. **事实与推测视觉分离 (Visible Separation of Facts and Guesses)**：一览页面便能瞬间识别出哪些是经过验证的客观事实，哪些是基于模型的最佳推测。
3. **数据一致性自动校验 (Auto-agreeing Numbers)**：建立自动校对机制，如果文内数字发生冲突，系统应当直接拒绝生成备忘录，而不是留给人类在凌晨两点去手工核对。
4. **矛盾冲突显性化呈现 (Surfacing Contradictions)**：当多源数据发生碰撞时，系统应当“举手”示警并列出冲突点，绝对不允许为了追求可读性而擅自将其平滑或抹平。
5. **人类审批与审计日志沉淀 (Audit Trail of Human Approval)**：系统的每一个变更、每一次审核确认都必须留有完整的审计追踪日志（Audit Trail），明确记录谁在何时对哪项决策修改签字负责。

这些技术要求解决的不是“更强大的大脑模型Benchmark”问题，而是最朴素的“管道传输与诚实度”问题。未来在金融 AI 领域的赢家，绝对不是靠跑分指标胜出，而是因为他们能够让一个在深夜 11 点疲惫不堪、充满怀疑的投资经理，在不需要疯狂打开七个标签页核对的情况下，敢于直接信任系统的输出。

这也构成了创始人们后续的**融资逻辑**。当你离开投行或风投的演示会议室后，你的商业演示文稿（Pitch Deck）会立即进入下一阶段的考验：它会被直接写成一份内部的“投资备忘录”。你在口头上说的每一个数字、每一个承诺，都会被投资团队拿到后台数据室（Data Room）中去挨个核对。这就是为什么前文提到的所有文档规范同样适用于创始人自身——你的融资过程，本质上也是一场备忘录级别的严苛审计。

<details>
<summary>Original English Source</summary>

Okay, the fix. Five things. Each one is a direct cure for a story you have just heard. This is almost a word for word. What I demand from our vendor before lighting their system near a live deal.
One, every claim comes with a receipt. Each sentence linked us straight to its source paragraph with the source trust level attached. Not a citation tab at the end.
Two, fact and the guesses stay visibility separate. At glance at the page, I insistently see what's proven and what's somebody's best estimate.
Three, numbers agree with each other automatically. The system refuse to ship a memo where the figures don't match. No human checking at 2:00 in the morning.
Four, contradictions get surfaced, never smoothed over. When sources disagree, the system raises its hand instead of picking the front layer answer.
Five, a real human approval gate and is logged. Who reviewed what change when they signed. That log is audit trail.
Notice what's not on the list. A smart promoter not One of these is a bigger brain problems. All five plumbing and honesty problems. The winners in the in this category won't win on benchmark points. They will win because a tired, skeptical finance person can trust their output at 11:00 at night without opening seven tabs.
Now, the part I promised, the money. Many of you are not just the building AI products. You are raising for them or you will be. So, let me tell you what actually happens after you leave the pitch meeting. Your deck becomes a memo. Literally, literally, literally, someone like me sits down and writes an internal memo about you. Every number you said out loud gets checked get get checked against your data room, what which means everything I just told you about the documents apply to you personally. Four lessons. Okay, my time's up. Thank you.

</details>