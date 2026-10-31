---
author: a16z
date: '2026-07-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Fpg_8aiBxx4
speaker: a16z
tags:
  - ai-agent
  - healthcare-it
  - workflow-automation
  - fintech-saas
title: 对话 Lassie 创始人：AI 代理如何彻底重塑医疗与小企业行政工作
summary: 本期访谈深入探讨了医疗 AI 初创公司 Lassie 的创业历程。创始人 Steijn Pelle 与 Frédéric Renken 分享了他们如何通过亲自嵌入牙科诊所，利用 AI 代理自动化极端繁琐的保险账单与行政流程，并深入分析了 AI 时代 SaaS 的交付革命与小企业未来的防守护城河。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Lassie
  - Robinhood
  - Superhuman
  - a16z
products_models:
  - Lassie AI
media_books: []
status: evergreen
---
### 行业痛点与 AI 机遇

**Frédéric**: **AI**在硅谷被过度炒作，但在爱荷华州（Iowa）却被低估了。我实际上认为，软件以前只是把纸质格式存储的内容转移到数据库里，最初是通过绿屏电脑在本地实现数字化，但人们仍然需要手动去完成所有的具体工作。

<details>
<summary>Original English</summary>

**Frédéric**: AI is overhyped in Silicon Valley but underhyped in Iowa. I would actually argue software just kind of took things that were stored in paper format and then they made them available first on prem via green screen computers but people still had to do the work.

</details>

**Alex**: 我永远忘不了我所看到的景象，在 **Yelp** 上排名第一的超级用户，每个月竟然要花 200 个小时在处理纸质文件和行政文书上。

<details>
<summary>Original English</summary>

**Alex**: I never forgot what I saw the number one great adopter on Yelp spending 200 hours a month on paperwork.

</details>

**Frédéric**: 这些模型虽然在海量数据上进行了训练，体积庞大，但它们实际上并不知道如何具体执行这些工作。起初，我们其实是作为“人机协同”（human in the loop）中的那个人类。我们算是通过这种方式，自己动手自动化解决了我们自己的问题。

<details>
<summary>Original English</summary>

**Frédéric**: The models are trained on so much data and they're so large and yet they actually don't really know how to do any of this work. Initially we were actually the humans in the loop. We kind of automated away our own problems.

</details>

**Alex**: 每一家初创公司与行业巨头之间的博弈，最终都取决于初创公司能否在巨头获得创新能力之前，先一步建立起自己的分销渠道。

<details>
<summary>Original English</summary>

**Alex**: The battle between every startup and incumbent comes down to whether the startup gets the distribution before the incumbent gets the innovation.

</details>

**Steijn**: 我们过去会说：“嘿，我们实际上构建了这个 **AI 代理**，它已经能够直接为你提供数十个小时的劳动力。” 对方随后就会非常迅速地采用它。他们把我们看作是能够帮他们真正运转起整个诊所业务的人。

<details>
<summary>Original English</summary>

**Steijn**: We come by and we say, "Hey, we actually have built this agent that can provide you already with tens of hours of labor. They then adopt it like very quick. They see us as someone they break in to like actually run the practice [music] for them."

</details>

**Olivia**: 关医生（Dr. Quan）对你们有一个非常精彩的评价：**Lassie** 并不是在取代人类，而是将人类从身兼数职的繁重行政束缚中解脱出来。

<details>
<summary>Original English</summary>

**Olivia**: There was a great quote from Dr. Quan about you guys, which is that Lassie isn't replacing humans, but like freeing them from wearing so many hats.

</details>

**Alex**: 这并不是说 AI 会抢走所有工作。在很多情况下，企业实际上是根本招不到人。

<details>
<summary>Original English</summary>

**Alex**: It's not like, oh, AI is going to take the jobs. In many cases, you can't find somebody.

</details>

**Olivia**: 你们是如何决定开发功能的优先级，以及决定销售给谁的？在你们的设想中，是否存在这样一个世界：面向牙医的 Lassie 会让面向物理治疗师的 Lassie 变得更好？

<details>
<summary>Original English</summary>

**Olivia**: How are you prioritizing what you build, who you sell to? Is there a world where Lassie for dentists makes Lassie for physical therapists better?

</details>

**Steijn**: 我们的终极目标是...

<details>
<summary>Original English</summary>

**Steijn**: The end goal here is that

</details>

### 创业故事的起源

**Olivia**: 欢迎两位，非常感谢你们今天加入我们。

<details>
<summary>Original English</summary>

**Olivia**: so welcome and thank you for joining us.

</details>

**Steijn**: 谢谢你们的邀请。很高兴能来到这里。

<details>
<summary>Original English</summary>

**Steijn**: Thank you for inviting us. Excited to be here.

</details>

**Olivia**: 也许我们可以从最基本的开始。**Steijn**，这家公司的起点源于你和你的牙医**关医生（Dr. Quan）**之间的一场对话。他当时对你说了什么，促使你决定辞去在 **Robinhood** 的科技高薪工作，转去亲自动手帮他处理账单和收款？

<details>
<summary>Original English</summary>

**Olivia**: Maybe we'll start with the basics. So, Stein, this whole company started with a conversation with you and your own dentist, Dr. Quan. What did he tell you that made you decide to quit your tech job at Robin Hood and go process payments for him by hand?

</details>

**Steijn**: 是的，我以前从未想过我的“美国梦”会是这个样子的。这非常有趣。我当时还在 Robinhood 工作。我来到这个国家是为了创办一家公司的。所以在工作了大约六年之后，我从阿姆斯特丹搬到了硅谷，我一直在寻找一个真正困难的问题来解决。

<details>
<summary>Original English</summary>

**Steijn**: Yeah, I did not know that my American dream would look like this. It was interesting like I was at Robin Hood at the time. And I came to this country to start a company. So after 6 years I moved from Amsterdam to Silicon Valley like I was looking for a hard problem to solve.

</details>

**Olivia**: 不过我很好奇，当他向你提出这个提议时，你当时是躺在牙科椅上吗？当你的嘴张着、电钻还在嘴里响的时候，他能听清你回答的是“好”还是“不好”吗？

<details>
<summary>Original English</summary>

**Olivia**: though I have to ask when he gave you this offer were you like was it like that kind of reclined? Could could he actually process your answer as yes versus no if your mouth was open and drills were in your mouth or how did that go down?

</details>

**Steijn**: 哈哈，其实直到现在我还没有长过蛀牙，所以谢天谢地，当时还没有用上钻头，希望一直保持下去。

<details>
<summary>Original English</summary>

**Steijn**: Well up until now I don't have cavities so you know there was no drilling happening yet. So you know knock on wood

</details>

**Olivia**: 只是例行检查。

<details>
<summary>Original English</summary>

**Olivia**: examination.

</details>

**Steijn**: 没错，完全正确。在检查完之后，他把我拉到了一边。

<details>
<summary>Original English</summary>

**Steijn**: Exactly. Exactly. Yeah. No like he took me aside like after that.

</details>

**Olivia**: 好的。

<details>
<summary>Original English</summary>

**Olivia**: Okay.

</details>

**Steijn**: 因为他知道我一直在四处寻找可以切入的复杂商业问题。那次预约结束后，他向我展示了他们后台的工作流。我一开始在想，这会不会只是他这一家诊所的问题？但这讲不通，因为他是一位非常出色的牙医。

<details>
<summary>Original English</summary>

**Steijn**: Because he knew that I was looking for this like hard problem. I was roaming around. And then like after like that appointment he showed me kind of like what was going on. And then I thought maybe it's him, right? But that didn't really make sense to me because he is a great dentist.

</details>

**Olivia**: 是的。

<details>
<summary>Original English</summary>

**Olivia**: Yeah.

</details>

**Olivia**: 你当时是如何说服他们让你进去，甚至深入到业务核心并接触他们的财务数据的？

<details>
<summary>Original English</summary>

**Olivia**: Um, how did you convince them to let you in and to kind of look through the the heart of the business and get into the financials?

</details>

**Steijn**: 是的，这听起来确实有点怪，对吧？“你好，我是 Robinhood 负责用户增长和推荐计划的，我能来你这上班吗？顺便提一下，这位是 **Frédéric**，他在 **Superhuman** 做产品，我们能不能帮你们代处理账单并接管财务？” 我想，这其实是我们能够成功的第一个信号。

<details>
<summary>Original English</summary>

**Steijn**: Yeah, it's a little weird, right? It's like, hello, I work at Robin Hood on growth on the referral program. Uh, can I get a job like here? And by the way, Frederick worked at Superhuman on product. can we do the billing for you and take over the finances? Um I think that was the first sign that we had a real business.

</details>

### 从数据库到 AI 代理的技术演进

**Alex**: 是的。那么从技术角度来看，**Frédéric**，你们是从 2020 年开始做这个业务的，当时在技术可行性上和现在截然不同。你们的产品构建过程随着时间的推移发生了怎样的变化？你当时认为可能实现的，与你现在认为可能实现的有什么区别？

<details>
<summary>Original English</summary>

**Alex**: Yeah. And from a technical perspective. So Frederick you the business started in 2020 and so much was different then in terms of what was even possible to build like how has your product building process changed over time. How is what you thought possible then different from what you think is possible now?

</details>

**Frédéric**: 是的，我之前做过一个关于“软件起源”的主题分享。软件最初的本质就是把物理文件柜里的东西搬进数据库里。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah. Well, so I've given this whole presentation on the origin of software was basically take a filing cabinet and put it in it to a database

</details>

**Alex**: 我们可以把这门生意的“零时刻”定为 **Saber** 系统。因为以前航空公司只能把座位预订信息存在文件柜里，Saber 系统是 **IBM** 和**美航（American Airlines）**的联合项目，这就是为什么 Saber 的英文拼写有两个 A（SABRE）。但后来...

<details>
<summary>Original English</summary>

**Alex**: and kind of pick the time equals zero moment for that with this company the Saber Systems because airlines would just keep reservations in filing cabinets. Saber Systems was a joint project between IBM and American Airlines. That's why Saber is spelled with two A's, Saber. Um but then that evolved.

</details>

**Frédéric**: 嗯。

<details>
<summary>Original English</summary>

**Frédéric**: Mhm.

</details>

**Frédéric**: 因为在 2023 年，所谓的“下一个词预测”（LLM的机制）在实际操作、执行任务或进行背景调查时表现并不好。你无法依赖纯粹的统计概率推理来运行一家诊所的实际核心流程，因为容错率太低了。

<details>
<summary>Original English</summary>

**Frédéric**: Um because in 2023 it's like you know next word prediction wasn't really good at like going and executing tasks, which is basically what AI is. Uh that was not good enough to go say I'm going to go run my practice or you know do background checks. I know I'm going to have statistical, you know, inference play out, which is too risky.

</details>

**Alex**: 但其实像 **Toast**（餐饮SaaS巨头）这样的软件在 1985 年完全就可以存在了。

<details>
<summary>Original English</summary>

**Alex**: but like Toast could have existed in 1985.

</details>

**Alex**: 当时人人都有 IBM PC，运行得挺好，微软的 DOS 系统也很稳定。那为什么 1985 年没有诞生一家餐饮软件巨头呢？首先，当时系统太难用了。其次，存在典型的“先有鸡还是先有蛋”的问题。你很难说服一家大型餐厅去用这个系统。

<details>
<summary>Original English</summary>

**Alex**: Like you know, everybody had an IBM PC. They worked pretty well. Microsoft DOS worked pretty well. Why didn't why wasn't there a restaurant software company in 1985? Well, number one, it was too hard to use. But then number two is you have this chicken-and-egg issue because could you get a big restaurant that wanted to adopt it?

</details>

**Frédéric**: 这确实是极佳的行业合作机会。

<details>
<summary>Original English</summary>

**Frédéric**: It was a great collaboration.

</details>

### 小诊所的经营困境与人才短缺

**Alex**: 我人生中去过的第一个牙医——希望他能听到这期播客——叫罗纳德·斯卢普（Dr. Ronald Sloop）。他是我父母刚搬到佛罗里达州时结识的第一位朋友。我已经从佛罗里达搬走了，但他一直在那里做牙医，直到退休。

<details>
<summary>Original English</summary>

**Alex**: Um so um my my first dentist hopefully he's listening to this podcast. His name is Ronald Sloop. Um it was my parents like first friend when they moved to Florida. I'm from Florida. Um he retired as a dentist.

</details>

**Steijn**: 他是荷兰人吗？这个名字听起来非常有荷兰特色。

<details>
<summary>Original English</summary>

**Steijn**: Was he a Dutch uh guy? He sounds very Dutch though.

</details>

**Alex**: 不是，他是波兰或乌克兰那一带的阿什肯纳兹犹太人，我家里人也是那一带出来的。他现在大概 75 或 80 岁了。他之所以选择退休，部分原因是他失去了帮他管理账簿和行政的“得力女干事”。

<details>
<summary>Original English</summary>

**Alex**: No, you know, Ashkenazi Jew from, you know, somewhere in Poland, Ukraine, whatever my family's from, too. So, you know, uh, but, you know, he's probably 75, 80 years old right now. But part of why he retired was he lost his like, you know, key woman that did the books and everything else.

</details>

**Alex**: 后来他把诊所卖给了一位年轻的医生，自己彻底退出了牙医界。所以当他看到你们的融资公告时，他惊呼：“我的天，这太棒了！”这绝非吹捧，因为我父亲也看到了这篇报道并打电话给我。我和斯卢普医生聊过。

<details>
<summary>Original English</summary>

**Alex**: And then he sold his practice to his like junior practitioner and now he's out of the dentistry business. So, he saw this announcement. He's like, oh my god, this is amazing. And I'm not talking this up because my dad called me about this because he saw the press release. I talked to Dr. Sloop.

</details>

**Alex**: 这就是为什么他现在退休了无所事事，只能在南加州打高尔夫球（他显然是从佛罗里达搬过去的）。因为现在要雇到一个靠谱的行政人员实在是太难了。所以这并不是“AI 会抢走工作”的问题。在很多地方，你根本招不到人。

<details>
<summary>Original English</summary>

**Alex**: Like this is why he's now like doing nothing with his life. Just like playing golf or something in Southern California. He moved there from Florida apparently. Um because it's just too hard to hire the person. So it's not like oh AI is going to take the jobs. In many cases you can't find the staff.

</details>

**Steijn**: 没错。因为如果诊所临时出现空缺，你可能只能遇到一个只说荷兰语的人。为什么不雇他呢？因为有荷兰人上门求职的概率大概只有百分之一。

<details>
<summary>Original English</summary>

**Steijn**: Because, you know, there might be a guy that only speaks Dutch that shows up. Yeah. Like, why not hire somebody who speaks Dutch? Well, because there's only a one in a hundred chance that a Dutch person shows up.

</details>

**Steijn**: 从同心圆的逻辑来看，金融交易构成了更核心的一环，而且规模庞大。

<details>
<summary>Original English</summary>

**Steijn**: Um, concentrically around that, you have like you know big on financial transactions that's even bigger.

</details>

**Steijn**: 这些业务完全有立足之地。再往外层看，则是更外围的同心圆。

<details>
<summary>Original English</summary>

**Steijn**: Where SaaS can exist for these businesses. But then you go to the concentric circle around that, which is just like the rest of the workflow.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 我们看到，仅在美国就有大约 16 万家牙科诊所，它们每年在行政文书工作上的支出大概在 20 万美元左右。有趣的是...

<details>
<summary>Original English</summary>

**Alex**: And we also see that so like the um there are about 160,000 dental practices in the US alone and they spend roughly $200,000 a year on like administrative costs. And then the interesting thing is...

</details>

**Steijn**: [发出轻蔑的笑声]

<details>
<summary>Original English</summary>

**Steijn**: [snorts]

</details>

**Steijn**: 他们一旦采用我们的系统，速度非常惊人。这很有意思。而且...

<details>
<summary>Original English</summary>

**Steijn**: they then adopt it like very quick. So it's super interesting to see. And then indeed like...

</details>

### AI 代理在医疗场景中的落地与验证

**Olivia**: 是的，关医生对你们有一个非常精彩的评价：**Lassie** 并不是在取代人类，而是把人类从各种行政杂务中解放出来。

<details>
<summary>Original English</summary>

**Olivia**: Yeah, there was a great quote from Dr. Quan about you guys, which is that Lassie isn't replacing humans, but like freeing them from wearing so many hats.

</details>

**Olivia**: 你们的宣传视频里还有一段他说自己现在可以去给孩子的足球队当教练的画面，因为他终于有空了。他们真的很需要这个。

<details>
<summary>Original English</summary>

**Olivia**: your launch video had a clip of him talking about how he can actually coach his kids soccer teams now because he has time. They do really appreciate it.

</details>

**Steijn**: 是的，他们确实非常感激。

<details>
<summary>Original English</summary>

**Steijn**: They do.

</details>

**Olivia**: 你们在技术上是如何实现这一点的？让产品达到这个水平的开发过程是怎样的？

<details>
<summary>Original English</summary>

**Olivia**: How did you approach the technical build process for that? What was it like getting the product to that level?

</details>

**Frédéric**: 我想我们已经探讨过一部分了，但我想强调一个巨大的不同点。

<details>
<summary>Original English</summary>

**Frédéric**: Um I think another part we already kind of talked about it, but I think a huge difference between us and others...

</details>

**Frédéric**: 我们在夜间运行这些闭环的自动化任务。

<details>
<summary>Original English</summary>

**Frédéric**: loop at night.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Frédéric**: 哈哈，是的，这也是工具必须具备的功能。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah. [laughter] Needs to go into the tool.

</details>

**Frédéric**: 我们从一开始就非常专注。初期阶段，我们其实就是那个“人机协同”里的人类，通过这种方式来摸清所有真实的边缘情况。

<details>
<summary>Original English</summary>

**Frédéric**: We from the very beginning we focused on um you know initially we were actually the humans in the loop, figuring out the edge cases that way.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 对于诊所老板而言，他们不在乎后台是怎么跑的。比如，我们干脆让斯卢普医生的名字在这期播客里彻底出名吧。

<details>
<summary>Original English</summary>

**Alex**: For a business it also doesn't matter that much right like if um let's make Dr. Sloop famous in this podcast.

</details>

**Steijn**: 他会学到新东西的。

<details>
<summary>Original English</summary>

**Steijn**: he's going to learn.

</details>

**Alex**: 哈哈，如果斯卢普医生说他可以成为我们的客户，也许我们应该谈谈如何重新激活他这个老客户。

<details>
<summary>Original English</summary>

**Alex**: Yeah. If Dr. Sloop said he can become a customer. So maybe we should talk about reactivating him [laughter]...

</details>

**Steijn**: 我们完全可以重新激活他。

<details>
<summary>Original English</summary>

**Steijn**: We could reactivate him.

</details>

**Alex**: 是啊，他听起来确实像是有这个意向的人。

<details>
<summary>Original English</summary>

**Alex**: Yeah, we he might he might come out. That's how he sounded.

</details>

**Alex**: 哈哈，这简直是 B 轮融资的绝佳创业故事：我们成功让斯卢普医生重操旧业，重返牙医市场。

<details>
<summary>Original English</summary>

**Alex**: Yeah. Yeah. [laughter] Dang. That's the series B story. We got Dr. Sloop out of retirement.

</details>

**Olivia**: 牙医行业本来人手短缺，现在问题解决了。

<details>
<summary>Original English</summary>

**Olivia**: We had a dental shortage and now we don't [laughter] have dentists coming out of retirement.

</details>

**Alex**: 这样全美又有上千万人能享受到优秀的牙科保健服务了。对于 Lassie 来说，这非常合适。

<details>
<summary>Original English</summary>

**Alex**: We got 100 million more people in the states that get good dental care. Um that's fine for Lassie.

</details>

**Frédéric**: 它能帮助行政人员省下 10 到 20 个小时。即便有少数棘手的索赔件需要你亲自处理，但绝大多数流程都处于自动驾驶状态，这让经营一家小诊所变得异常轻松。

<details>
<summary>Original English</summary>

**Frédéric**: it saves 10 20 hours. Um if there are a handful of claims that you need to file yourself, but the majority kind of like is on autopilot makes it tremendously more easy to run a business.

</details>

### 系统对接与软件集成的博弈

**Alex**: 是的。从实施和客户导入（onboarding）的角度来看，你们主要是选择与诊所现有的执业管理软件（Practice Management Systems）进行接口集成，还是会迫使他们更换掉原有的整套软件？

<details>
<summary>Original English</summary>

**Alex**: Yeah. From an implementation and onboarding perspective, you guys integrate with existing practice management systems for the most part versus kind of making them switch a bunch of software to use you?

</details>

**Alex**: 很多时候，初创公司做出了惊人的创新，但却做不成一家伟大的公司，因为往往面临尴尬的结局：你做出了新东西，但最终只能卖给那些掌握着分销渠道的巨头。

<details>
<summary>Original English</summary>

**Alex**: which is an amazing innovation but a terrible company because you really have very few outcomes that are good. You either end up selling to one of the...

</details>

**Alex**: 行业巨头拿走了几乎所有的商业红利，因为他们手里掌握着全部的客户资源。因此，我认识到许多初创公司的关键瓶颈在于分销。

<details>
<summary>Original English</summary>

**Alex**: and they take all the economics because they have all the customers. So that hence you know my recognition was like the thing that a lot of startups lack is distribution.

</details>

**Alex**: 比如那家由 **Idealab** 和一众风投基金投资的公司，他们做的功能就是让你在 **Outlook** 里直接搜索邮件，体验非常丝滑。但问题在于...

<details>
<summary>Original English</summary>

**Alex**: And this company that was funded by Ideal Lab and all these VCs, you know what they did? It was like search for your Outlook email, which was so good, but...

</details>

**Alex**: 但另一方面，在很多传统行业中，从来没有诞生过任何占据统治地位的软件巨头，因为以前唯一的解决方案就是招人来纯手工解决。

<details>
<summary>Original English</summary>

**Alex**: uh but the other is that there are a lot of categories where there never was an incumbent software company because the only job to be done was like manually hiring people.

</details>

**Frédéric**: 确实是这样。我们看到的正是这个局面——这里面根本不存在一个现成的行业霸主。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah. And we see exactly that is that um there isn't an incumbent...

</details>

**Frédéric**: 市场上根本没有软件能快速或者轻松地把这个特定流程跑通。

<details>
<summary>Original English</summary>

**Frédéric**: that kind of like does this job or can do this job like quickly.

</details>

**Alex**: 哈哈，以前在这个岗位上的“行业巨头”通常叫贝蒂（Betty），而她两周前刚刚辞职了。这就是牙医们面对的现状。

<details>
<summary>Original English</summary>

**Alex**: Well, the incumbent was named Betty and she quit two weeks ago. That's the incumbent.

</details>

**Frédéric**: 或者是外包给传统的账单代理机构。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah. Or or a billing agency.

</details>

**Alex**: 没错，斯卢普医生当年的老助理就是诊所的“核心基础设施”。

<details>
<summary>Original English</summary>

**Alex**: It's Dr. Sloop's old assistant. That's the incumbent.

</details>

**Steijn**: 或者说，是外包给一些位于海外或美国本土的代账机构。这就是牙科诊所目前实际在进行竞争的对手，这也是痛点所在。

<details>
<summary>Original English</summary>

**Steijn**: or version of that that like is somewhere overseas or in the states. Uh so that's indeed exactly like what you're competing with and that's what in...

</details>

**Steijn**: 如果你带着他们以前从未见过的、如今技术才支持的新型软件上门，他们会非常乐意采纳，你就能迅速增长。这非常令人兴奋。

<details>
<summary>Original English</summary>

**Steijn**: Um and then if you show up with software that they have never seen before which is now possible they will adopt it and you can grow. Um which is very exciting.

</details>

### “最后一公里”的落地与分销挑战

**Olivia**: 关于客户导入，我想我们听众也很想知道：你们具体是如何做本地推广和上门 onboarding 的？

<details>
<summary>Original English</summary>

**Olivia**: that adoption. Well, I imagine the other part of the question for you, I'd love to hear your thoughts on this. Um, or I'm sure our audience would love to hear...

</details>

**Olivia**: 你如何让这个导入流程完全自动化？因为对于向小商家售卖软件的业务模式而言，这直接决定了商业模型能否算得过来账。

<details>
<summary>Original English</summary>

**Olivia**: right? Like how do you actually do the onboarding?

</details>

**Frédéric**: 是的。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah.

</details>

**Olivia**: 如果你们必须为全美每一家诊所都亲自派人上门做初始化，那这个业务就很难规模化。

<details>
<summary>Original English</summary>

**Olivia**: Um, and how much of that can you automate? Because that's part of what makes a business that is selling these things work or not work,

</details>

**Olivia**: 因为你不能每次都派一个自己人去每一家诊所。

<details>
<summary>Original English</summary>

**Olivia**: right? Because if you have to, you know, send your own Betty...

</details>

**Alex**: 亲自跑遍全国的每一个办公室，确实不可行。

<details>
<summary>Original English</summary>

**Alex**: to every single office in the country. Yeah,

</details>

**Steijn**: 如果能让客户直接在后台下载 Lassie 应用，那体验会极其丝滑。但现实是，这些传统系统和流程目前还非常手工化。

<details>
<summary>Original English</summary>

**Steijn**: it would be amazing if it's just like download the lassie app like these these systems and processes are very manual...

</details>

**Alex**: 这又回到了我常说的那句话：“AI在硅谷被过度炒作，但在爱荷华州被严重低估了。”

<details>
<summary>Original English”>

**Alex**: and um I kind of think like AI is overhyped in Silicon Valley but underhyped in Iowa...

</details>

**Alex**: 爱荷华州有千千万万个这样的小商户。你们究竟打算如何为 Lassie 解决“最后一公里”的下沉分销难题？

<details>
<summary>Original English</summary>

**Alex**: and like there are a lot of people in Iowa like how do you solve that last mile distribution problem for Lassie?

</details>

**Steijn**: 是的，这是一个超级有趣的问题。假设我们能通过挨家挨户敲门来让他们尝试这个产品，接下来的挑战就是如何让产品真正融入他们的日常工作流。

<details>
<summary>Original English</summary>

**Steijn**: Yeah. Yeah. I think uh it's a super interesting problem. Assume you can knock on all these doors and get them to try it, right? Then like how do you get it embedded?

</details>

### 未来路线图与跨行业扩张的终极目标

**Olivia**: 确实。顺着这个思路，除了牙科诊所，你们未来完全可以为其他类型的医疗或健康诊所开发功能。

<details>
<summary>Original English</summary>

**Olivia**: yeah I guess to that point like there's more you can build and are building for dental practices then there's all these other types of healthcare practices.

</details>

**Olivia**: 你们是如何对未来的功能迭代和客户群体进行优先级排序的？你认为是否会有这么一天，为牙医开发的 Lassie 核心能力，能直接让针对物理治疗师的 Lassie 产品变得更好？

<details>
<summary>Original English</summary>

**Olivia**: how are you prioritizing what you build, who you sell to. Is there, you think, a world where Lassie for dentists makes Lassie for physical therapists better?

</details>

**Steijn**: 这涉及我们的宏伟蓝图（Master Plan）。

<details>
<summary>Original English</summary>

**Steijn**: The master plan.

</details>

**Olivia**: 没错。

<details>
<summary>Original English</summary>

**Olivia**: Yes.

</details>

**Steijn**: 我们已经进展到聊宏伟蓝图的环节了吗？

<details>
<summary>Original English</summary>

**Steijn**: Are we at that part of the episode?

</details>

**Olivia**: 哈哈，是的。

<details>
<summary>Original English</summary>

**Olivia**: Yes.

</details>

**Steijn**: 好的。我觉得主要分为三个阶段。我们的终极愿景是：让每一个小企业都能够实现自我运转，而所有的繁杂行政庶务都由 AI 代理来代劳。

<details>
<summary>Original English</summary>

**Steijn**: Um, yeah. I think three steps like the end goal here is that every small business should run itself, right? And the busy work is done by agents.

</details>

**Olivia**: 最终目标是赋能和帮助所有的线下实体小企业。

<details>
<summary>Original English</summary>

**Olivia**: But the end goal is to help them all.

</details>

**Olivia**: 太棒了，我非常喜欢这个宏伟蓝图。这是一个非常宏大且令人兴奋的愿景。你们两位过去都深度参与过许多明星初创公司的规模化扩张，比如 Robinhood 和 Superhuman。在 Lassie 的成长过程中，有哪些过往的经验是你们直接应用进来的？

<details>
<summary>Original English</summary>

**Olivia**: Amazing. I love that as a master plan. It's a good one. A big one. Um you both have been part of scaling many important companies in the past. Robin Hood, Superhuman. What are the lessons you are carrying over?

</details>

**Frédéric**: 我们现在应用了许多在 Superhuman 期间学到的经验和方法论。首先就是极度专注于找准“理想客户画像”（ICP），并在前 100 位客户身上做到产品体验的绝对极致。

<details>
<summary>Original English</summary>

**Frédéric**: There's a bunch of stuff that we're applying now that I learned at Superhuman. Um I think for one focusing on the right ICP and being really crisp about making the product experience outstanding for them.

</details>

### 团队建设与行业专长的平衡

**Alex**: 这一点非常关键。

<details>
<summary>Original English</summary>

**Alex**: that's safe to say.

</details>

**Alex**: 普通人通常一年看两次牙医，这已经算很不错了。对于大多数人来说...

<details>
<summary>Original English</summary>

**Alex**: You go twice a year. That's pretty good. I think for the average...

</details>

**Olivia**: 牙医通常会建议一年看两次，对吧？

<details>
<summary>Original English</summary>

**Olivia**: you're supposed to, right?

</details>

**Alex**: 哈哈，是的，当然。

<details>
<summary>Original English</summary>

**Alex**: Yeah, of course.

</details>

**Olivia**: 我只是在履行我作为一个普通病患的义务。

<details>
<summary>Original English</summary>

**Olivia**: I'm just doing my [laughter]...

</details>

**Alex**: 这确实不是必须要到处宣扬的义务。

<details>
<summary>Original English</summary>

**Alex**: not a saving duty to say.

</details>

**Olivia**: 那么，能跟我们聊聊现在团队的规模吗？在招聘时，你们是倾向于寻找具有牙科行业背景的人才，还是更看重其他维度的特质？

<details>
<summary>Original English</summary>

**Olivia**: Um when you're Well, maybe tell us like how big is the team now? When you're hiring, are you looking for expertise in dental? What are the kinds of talents you want?

</details>

**Steijn**: 是的，这也是我们目前最核心的关注点。因为我们已经在巨大的市场中找到了极佳的“产品与市场契合度”（PMF），接下来需要快速跑通规模化。

<details>
<summary>Original English</summary>

**Steijn**: Yeah. Uh which is now mainly on our mind, right? Because like we found there a really great product market fit in a large market where you can go and scale.

</details>

**Steijn**: 我们目前有两个招聘原则。首先，基本常识依然有效：你需要寻找具有“高成长曲线”（steep slope）的通用型人才。

<details>
<summary>Original English</summary>

**Steijn**: Um we we currently have two takes on that like one not much has changed contrarian maybe take here. You still need people with steep slope.

</details>

### AI 时代的防守护城河与小企业防御力

**Alex**: 如果以前每个小商家都能随手雇到一个像贝蒂这样得力的行政经理，事情会容易得多。但现在你必须随时准备应付人员变动。

<details>
<summary>Original English</summary>

**Alex**: if it's so much easier if everybody can hire Betty right? Just materialize a Betty.

</details>

**Steijn**: 是的。

<details>
<summary>Original English</summary>

**Steijn**: Yeah.

</details>

**Alex**: 这会带来什么改变？我的意思是，对于小企业来说，未来创办和运营一家企业可能会变得极其简单，但这也可能意味着...

<details>
<summary>Original English</summary>

**Alex**: Um how does that change? I mean like it could actually work out where like small businesses it's much easier to start one and run one but then...

</details>

**Olivia**: 因为如果思考 AI 时代的商业护城河（Moats）...

<details>
<summary>Original English</summary>

**Olivia**: because you do have if you think about moats in the AI era in general...

</details>

**Olivia**: 我们通常是在软件和科技公司的语境下去探讨护城河。

<details>
<summary>Original English</summary>

**Olivia**: we often talk about it with respect to software companies.

</details>

**Alex**: 确实。

<details>
<summary>Original English</summary>

**Alex**: Y.

</details>

**Olivia**: 如今在各类无代码或新型开发平台上复制一个现有的软件功能变得太容易了。

<details>
<summary>Original English</summary>

**Olivia**: um so it's so easy to go replicate XYZ software. I did it on Replit or I did it on Lovable or I did it on Claude. You hear this all the time.

</details>

**Alex**: 但是，要想去全盘复制或物理克隆斯卢普医生的线下牙科诊所，难度则完全是另一个量级的。

<details>
<summary>Original English</summary>

**Alex**: Um much much harder to say I'm going to go replicate Dr. Sloop's practice.

</details>

**Steijn**: 是的。

<details>
<summary>Original English</summary>

**Steijn**: Yeah.

</details>

**Alex**: 让线下实体小企业具备坚固防守壁垒的核心原因之一，在于它需要真实的人类团队协作来提供物理世界的最终交付。

<details>
<summary>Original English</summary>

**Alex**: But one of the things that makes a small business somewhat defensible is actually it is an accumulation of people that are required to deliver the end service.

</details>

**Steijn**: 是的。

<details>
<summary>Original English</summary>

**Steijn**: Yeah.

</details>

**Alex**: 这让我想起了洋基队的传奇棒球运动员尤吉·贝拉（Yogi Berra），他经常说一些看似毫无逻辑但耐人寻味的话。

<details>
<summary>Original English</summary>

**Alex**: And it's like uh if you know who Yogi Berra is, you know, famous Yankees baseball player that said all these things that make no sense.

</details>

**Steijn**: 是的，我知道他。

<details>
<summary>Original English</summary>

**Steijn**: Yeah.

</details>

**Alex**: 尽管听起来很荒谬，但他经常被后人引用。我最喜欢的一句是：“那地方太挤了，现在都没人去了。”

<details>
<summary>Original English</summary>

**Alex**: And um but like quoted often though, right? And my one of my favorite ones, \"it's so crowded nobody goes there anymore.\"

</details>

**Steijn**: 哈哈，确实逻辑说不通。

<details>
<summary>Original English</summary>

**Steijn**: Yeah. It doesn't make sense.

</details>

**Alex**: 但我的问题是：如果启动和日常维持一家小企业的行政门槛被 AI 降到了几乎为零，你觉得整个线下小商业的竞争格局会发生什么变化？

<details>
<summary>Original English</summary>

**Alex**: Um but I guess my question is how do you think small business changes if it's easier to run a small business and start one?

</details>

**Steijn**: 我们目前的看法是，之前的软件和服务假设了市场需求是存在上限的。但如果以牙科诊所为例，你会发现需求其实非常充沛。

<details>
<summary>Original English</summary>

**Steijn**: Yeah, I think our our current take on that is that this assumes there's a cap on kind of like demand and if you just look at the dental practice, but there isn't.

</details>

### 应对生成式 AI 的技术迭代与数据壁垒

**Alex**: 回头看，你们是在 2020 年创立这家公司的，那可以说是生成式 AI 爆发前夜。而在那之后，我们迎来了波澜壮阔的生成式 AI 革命。

<details>
<summary>Original English</summary>

**Alex**: Yeah. So you started the business in 2020 and that was like arguably pre-AI or pre what we think of as being this generative AI revolution...

</details>

**Alex**: 从“技术表现还不够好”到未来技术爆发，你觉得未来的技术曲线会怎么走？这会是一个关于通用人工智能（AGI）何时降临的问题吗？

<details>
<summary>Original English</summary>

**Alex**: where it's just not quite good enough and then what do you think the curve of that looks like when so it's not you know it's like a question of AGI...

</details>

**Frédéric**: 我觉得很有意思的一点是，基础模型虽然在海量公开数据上进行了训练，参数巨大，但它们在没有私有上下文的情况下，依然不知道如何具体执行垂直行业的精细任务。

<details>
<summary>Original English</summary>

**Frédéric**: I think one thing that's interesting is that the models are trained on so much data and they're they're so large and yet they actually don't really know how to do any of this work.

</details>

**Frédéric**: 我们在这一块拥有巨大的防守优势。因为我们能直接从他们的行业 ERP（管理软件）中，提取所有脱敏的历史数据来进行推理。

<details>
<summary>Original English</summary>

**Frédéric**: I think we have a big advantage there because we have all of this like historical data out of their ERPs that we can look at and kind of infer how to do it.

</details>

**Alex**: 这让我想起了一件事。我的医疗保险公司 **Cigna** 每次只能给我邮寄纸质支票。我当时想，我是不是错过了什么数字化的选项？

<details>
<summary>Original English</summary>

**Alex**: right? So I was thinking about this because Sigma, who I have for my health insurance, will only send paper checks. I was like, \"Oh, I must have missed something.\"

</details>

**Alex**: 但随着技术的发展，现在所有人手里都拥有了近乎免费的 AI 代理，可以不眠不休地在后台跟保险公司反复进行账单撕扯和博弈。

<details>
<summary>Original English</summary>

**Alex**: But now that everybody has this like superpowered thing that costs effectively nothing to go argue in perpetuity, it's like I can argue with you and...

</details>

**Alex**: 那么，对于保险报销和欠款催收这些环节，这种技术对峙会如何重塑诊所与保险公司之间的商业博弈？你们肯定深入思考过这个问题。

<details>
<summary>Original English</summary>

**Alex**: but like how does that change the business dynamic of things like insurance payments and collections? I mean, I'm sure you thought about this a lot...

</details>

**Alex**: 因为牙医面临的大多数账单博弈，其对手盘其实都是体量庞大的保险巨头。

<details>
<summary>Original English</summary>

**Alex**: because in many cases the counterparty that the dentist is dealing with is the insurance carrier.

</details>

**Frédéric**: 没错。

<details>
<summary>Original English</summary>

**Frédéric**: Yeah. Right.

</details>

**Alex**: 牙科诊所的大部分应收账款和核心收入，都直接来自于这些保险公司的结付。

<details>
<summary>Original English</summary>

**Alex**: A big part of the accounts receivables or or revenue comes from insurance companies,

</details>

**Frédéric**: 是的。

<details>
<summary>Original English</summary>

**Frédéric**: right?

</details>

**Frédéric**: 是的，这非常微妙，因为这个领域受到极其严格的合规监管。如果一位牙医做了一个牙冠（Crown），只要我们能帮他向保险公司提供完全合规、无可挑剔的临床事实陈述（Narratives），赔付流程就会变得非常顺畅。

<details>
<summary>Original English</summary>

**Frédéric**: Um yeah, I think it's quite interesting because um it's pretty like well regulated. So um if a dentist does a crown like and you provide them with the correct narrative, we can automate the approval.

</details>

**Steijn**: 然后保险公司就会直接结账。此外，因为我们非常深地扎根于牙科行业，我们观察到一个非常有趣的行业动态。我花了一段时间才真正理解这一点。

<details>
<summary>Original English</summary>

**Steijn**: And then they will like bait that out. Uh the other thing because indeed we are very deep in this industry. Um that is interesting dynamic um it took me a while to understand this but...

</details>

### 下沉市场的交付模式革命

**Olivia**: 显然，全美有大量的牙科诊所极度渴望甚至迫切需要像 Lassie 这样的产品，但他们的物理分布极为分散，零星分布在全国各地。

<details>
<summary>Original English</summary>

**Olivia**: So obviously there are a lot of dental practices that want or even desperately need products like Lassie, but they are distributed and they're all over the place.

</details>

**Steijn**: 是的。这与目前硅谷主流的软件交付打法完全不同。目前大多的 AI 初创公司只是套壳了基础模型，然后做个轻量级的网页应用。但我们选择做深度集成并重塑整个交付流，直接把完整的工作结果交付给医生。

<details>
<summary>Original English</summary>

**Steijn**: Yeah, this is a very different playbook than where currently I think the cutting edge is. It's like you have these models good enough and apply them into deep vertical workflows to deliver the work itself.

</details>

**Olivia**: 非常感谢你们两位今天抽空跟我们交流。这是一次极其精彩的对话。我们对 Lassie 的未来感到非常兴奋。任何听到这期播客的人...

<details>
<summary>Original English</summary>

**Olivia**: Thank you both so much for coming to chat with us today. This was awesome. We are very very excited for the future of Lassie. Uh, anyone who's listening...

</details>

**Steijn**: 谢谢。

<details>
<summary>Original English</summary>

**Steijn**: Oh, yeah.

</details>

**Olivia**: 再次感谢你们，祝进展顺利。

<details>
<summary>Original English</summary>

**Olivia**: Amazing. Great. Well, thank you guys again.

</details>

**Frédéric**: 非常感谢，谢谢你们的款待。

<details>
<summary>Original English</summary>

**Frédéric**: Thank you so much. Thanks for hosting us. [music]

</details>