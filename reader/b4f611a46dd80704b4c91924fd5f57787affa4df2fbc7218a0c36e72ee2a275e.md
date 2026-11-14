---
author: a16z
date: '2026-09-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yTNMEYeCgWw
speaker: a16z
tags:
  - cancer-vaccine
  - mrna-technology
  - personalized-medicine
  - neoantigen-prediction
  - immunotherapy
title: Moderna CEO 深度拆解 mRNA 个性化癌症疫苗：从三期临床突破到 AI 算法与工业化量产
summary: Moderna CEO 斯特凡·班塞尔做客 a16z 播客，深度解读其与默沙东合作的个性化 mRNA 癌症疫苗（mRNA-4157）在黑色素瘤三期临床中取得的历史性突破。对话涵盖 mRNA 递送与新抗原算法预测机制、42天全流程个性化生产与监管路径，以及向早期肺癌、胰腺癌和自身免疫疾病扩展的宏伟蓝图。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Moderna
  - Merck
  - Andreessen Horowitz
products_models:
  - mRNA-4157
  - Keytruda
media_books: []
status: evergreen
---
### 癌症疫苗历史性突破

**斯特凡·班塞尔**: 这是有史以来第一次有**癌症疫苗**被证实有效。整个肿瘤领域为此探索了20多年，进行过超过1000次临床试验，但此前全部以失败告终。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: It's the first time there is a cancer vaccine working. The field has been doing that for 20 plus years, more than a thousand clinical trials that have all failed.

</details>

**豪尔赫·康德**: 这次究竟有什么不同？**mRNA 技术**到底具备什么特质，能以传统方法无法做到的方式来训练免疫系统？

<details>
<summary>Original English</summary>

**Jorge Conde**: What was different this time? What is it about mRNA technology that enables the immune system to learn in a way that other approaches were unable?

</details>

**斯特凡·班塞尔**: 我们人体内其实随时随地都在产生癌细胞。我们的**免疫系统**训练有素，基本上能在非常早期就察觉到这些癌细胞并将其清除。但如果肿瘤已经长大，核心问题就在于你该如何重新训练免疫系统？我们所做的，基本上就是获取你肿瘤的活检组织，读取其 DNA 的全部字母；然后对你体内的健康细胞做完全相同的事情。接着我们逐字、逐核苷酸进行比对。随后通过算法识别出哪些突变最具相关性。当把这个药物注射进体内后，它就能教会免疫系统识别它此前遗漏的、专属于你个人癌细胞的特征指纹。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: We all have cancer cells all the time in our body. Our immune system is very well trained. Basically notice those cancer cells very early and get rid of them. But if your cancer grows, then the question is how can you retrain immune system? We're going to basically take a biopsy of your tumor. We're going to read all the letters of its DNA. And then we're going to do the same things with a healthy cell of your body. And we're going to literally compare letter by letter, nucleotide by nucleotide. And then we're going to use an algorithm to identify which one of those mutations are the most relevant. And so when this is injected in your body, it teaches the immune system the signature of your cancer cell that it missed.

</details>

**豪尔赫·康德**: 这种疗法在监管上是如何审批的？因为每个病人的剂量和序列都完全不同，显然不可能去单独批准每一剂药。

<details>
<summary>Original English</summary>

**Jorge Conde**: What gets regulated here? Because every dose is different. So obviously every dose doesn't get approved.

</details>

### 对话背景与重磅发布

**豪尔赫·康德**: 大家好，欢迎收听 **a16z** 播客。我是**豪尔赫·康德**（Jorge Conde），a16z Bio + Health 团队的通用合伙人。今天我非常激动地再次邀请到 **Moderna** 首席执行官**斯特凡·班塞尔**（Stéphane Bancel）。

长期听众可能还记得，斯特凡曾在2020年12月来到过 a16z 播客，当时我们讨论了 Moderna 为研发 **mRNA 新冠疫苗**所付出的全部努力。如果大家回顾那一期节目，就会听到 Moderna 面对新型病毒时反应何其迅速——在极短时间内完成病毒基因分析，实质上“打印”出了能保护人类免受 COVID-19 感染的疫苗，从而让我们在抗击新冠大流行中占据了极佳的先机。我们将那期节目命名为《制造疫苗的机器》。

而今天在2026年8月，我们再次展开对话的原因，是因为 Moderna 发布了一项关于 mRNA 技术在癌症治疗领域的重大进展。因此我想把话筒交给你，斯特凡，再次热烈欢迎你回来。我们不妨先从新闻本身谈起：Moderna 与**默沙东**（Merck）在本月初宣布，你们在**黑色素瘤**（Melanoma）的三期临床试验中取得了极其令人鼓舞的结果。能否请你先为我们介绍一下，这次发布了什么？你们在这项三期试验中观察到了什么？随后我们将深入探讨 Moderna 在癌症领域的整体布局。

<details>
<summary>Original English</summary>

**Jorge Conde**: Hi. Um, welcome to the a16z podcast. Uh, I'm Jorge Conde, a general partner on the a16z Bio + Health team. I am thrilled today to welcome back Moderna CEO Stéphane Bancel. Um, for folks that have been longtime listeners may recall, uh, Stéphane joined us on the a16z podcast back in December of 2020. Um when we were talking about all of the work Moderna did to uh bring us the the mRNA COVID vaccine and at the time um if you can go back and listen to that episode you'll hear um how quickly um Moderna was able to react to the existence of the virus to analyze it uh to essentially print a vaccine um that would protect people against against the the COVID-19 uh vaccine and hence put us in a much better position uh with respect to the to the COVID pandemic. We titled that episode "The Machine that Made the Vaccine", and the reason why we're talking again today in August 2026 uh is because Moderna has uh put out news uh on a really big advancement on what they can do with mRNA technology when it comes to cancer. And so I want to hand it over to you uh Stéphane. Again a very big welcome. Thank you for coming back. But maybe the place to start is let's uh let's lead with the news. Um you uh Moderna and Merck uh announced uh earlier this month in August that uh you had uh conducted a phase three clinical trial in melanoma and have gotten uh very encouraging results. So why don't I hand it over to you and tell us uh what have you announced? What have you seen in this phase three trial and then I do want to dig in into what Moderna is doing in cancer.

</details>

### 三期临床核心数据

**斯特凡·班塞尔**: 太棒了。豪尔赫，非常感谢再次邀请我们，非常高兴能再次与你交流。确实，就在上周，我们与默沙东的同仁共同宣布了这一消息：在利用 mRNA 技术探索个体化癌症治疗方案长达10年之后，我们的**三期临床试验**取得了阳性结果。这在许多维度上都是历史性的“第一次”——这是在黑色素瘤领域，历史上首次出现某种药物的效果显著优于单独使用 **Keytruda**（帕博利珠单抗，可瑞达）；对于黑色素瘤患者而言这是一件大事；同时这也是人类历史上首次证实癌症疫苗切实有效。

如你所知，该领域在此方向探索了20多年，进行过超过1000次临床试验但全部折戟。如果我们回顾二期数据并结合上周的公告：我们达到了这项研究的**主要终点**，即**无复发生存期**（RFS，Recurrence-Free Survival），也就是延缓或阻止癌症复发或死亡。

不仅主要终点达标，令我们自己都感到惊喜的是——因为这只是第一次中期分析，并不是试验的最终总结——我们竟然在首次中期分析中就达到了**次要终点**，即**无远处转移生存期**（DMFS，Distant Metastasis-Free Survival）。这个指标通常需要更长的时间才能成熟显现，因为它衡量的是肿瘤是否向原发部位之外发生远处转移。我们也达到了这一终点，这极为出色，完全超出了我们最初的预期，意味着药物的疗效极其强劲。

我们很快就会在顶级肿瘤医学年会上公布完整数据。但为了给大家一个清晰的方向感：几个月前在2026年春季的 **ASCO**（美国临床肿瘤学会年会）上，我们展示了二期试验的长期随访结果。该二期试验同样是针对单独使用 Keytruda 的随机对照研究，数据显示：在治疗5年后，与单用 Keytruda 相比，联合治疗组的复发风险降低了约50%。在肿瘤学界，5年无病生存通常被临床医生视为临床治愈，因此这是一件极其重大的突破。如果查看二期试验的全部数据，接受联合治疗并在手术切除黑色素瘤的患者中，有约80%的人在5年后依然处于无病生存状态。

我们对这对整个肿瘤领域所代表的意义感到无比振奋。我们目前正与监管机构紧密配合推进上市申报，争取让这款药物尽快造福患者，希望最快在2027年获批上市，我们会竭尽所能加速推进。我们在马萨诸塞州马尔堡（Marlborough）的工厂已经就绪，我们已经彻底打通了为每一个具体的个体规模化定制生产药物的完整工艺。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Wonderful. So Jorge, thank you so much for having us back. We're very happy to be to be with you. So indeed uh last week now uh we shared the news with our colleagues at Merck that after working 10 years on a individualized uh treatment against cancer using mRNA technology that the phase three was positive. It's a it's a first of many. It's the first time that there is an agent in melanoma that is better than Keytruda alone so it's a big deal for patient of course with melanoma. It's the first time there is a cancer vaccine working. Uh the field as you know has been doing that for 20 plus years. I think more than a thousand clinical trials that have all failed. Um and um if you look at the phase two data because what we announced last week is that we met the primary endpoint of the study which was recurrence-free survival i.e. people having the cancer back or dying that we met.

And then to our own surprise because this was the first interim analysis—this is not the end of a study, it's a first interim of a study—and what was a surprise even to us is we met the secondary endpoint which was distant metastasis-free survival which is of course takes more time to mature because it means that you have distance metastasis from your primary tumor and we also met that uh endpoint which was great again unexpected from our side but again means it is really good. Um we will share the data very soon at a big medical oncology conference which is as you know what the field does. But just to give you a sense maybe to orient kind of directionally we showed at ASCO the big you know oncology conference in the spring of 2026 a few months ago that our phase two study which was also randomized against Keytruda alone—so the same type of study—showed that around 50% of people had recurrence-free survival versus people only getting Keytruda and this is 5 years after treatment. And as you know in oncology five years is considered by doctor like a cure and so it's a big big deal. And if you look at the data from overall that phase two you had around 80% of people that were disease-free five years after their treatment and their surgery of melanoma. And so we're very excited about what it means for the field. Uh we are working very hard already with regulators to file so that the drug can be available to patient as soon as possible and we hope in 2027 and we're going to try to make it as fast as we can. Uh the factory is ready in Massachusetts where we have figured out how to make and scale a product for every human being at a time.

</details>

### 为何联合免疫检查点

**豪尔赫·康德**: 这里面包含的信息量实在太大了。这无疑是黑色素瘤治疗乃至未来更广泛肿瘤治疗领域的一项非凡突破。斯特凡，我们能否把这其中的机制逐层拆解开来？首先，对于那些不太熟悉现代癌症疗法的人来说，你能否解释一下：什么是 Keytruda？为什么单独使用 Keytruda 还不够？为什么在 Keytruda 之外，必须联合使用 Moderna 研发的这款特定 mRNA 癌症疫苗？

<details>
<summary>Original English</summary>

**Jorge Conde**: Well, there's I mean there's so much to to unpack here. So this is an extraordinary uh advance uh for the the treatment of in this case melanoma and hopefully over time cancers more broadly. Uh so let's unpack some of this if we could Stéphane. Uh the first one um uh talk to us uh for folks that are less familiar with cancer treatments. Uh why is Keytruda what is Keytruda and why is Keytruda alone not sufficient? Why was Moderna necess—or the the this particular mRNA cancer vaccine necessary in conjunction with Keytruda?

</details>

**斯特凡·班塞尔**: 当然可以。如果看一下 Keytruda，它是大众可能听过的一款最具代表性的**肿瘤免疫疗法**。如果不做过于晦涩的生物学解释，通俗来说：它就像一个能打开牢门、释放猎犬的分子，释放出来的免疫细胞会主动去攻击你体内的癌细胞。

**免疫检查点抑制剂**（Checkpoints）的奇妙之处在于，只要它们起效，效果就极其惊艳——这些患者在接受治疗5年后往往能够实现临床治愈，体内彻底没有残余病灶。然而，如果查阅已发表的 Keytruda 三期临床数据，只有约60%的患者在5年后依然保持无病状态。对于这60%的人而言这如同奇迹，但也意味着还有40%的患者虽然经历了艰苦的抗癌治疗，药物却并未对他们产生实质效果。而且免疫疗法往往伴随着严重的毒副作用，与化疗或放疗不同，免疫疗法的副作用多数是严重的**自身免疫性疾病**。

因此，当你观察接受免疫检查点抑制剂治疗的患者群体时，无论他们使用的是抗 PD-1 单抗还是抗 CTLA-4 单抗，你会发现患者体内的 T 细胞虽然被大量激活扩增，但这些 T 细胞就像一群在黑暗房间里盲目狂吠乱窜的猎犬——它们根本不知道具体的敌人在哪里，于是只能漫无目的地在全身游走。在很多情况下，它们由于缺乏明确的目标定位，最终导致了严重的自身免疫毒性，却没有真正摧毁肿瘤组织。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Sure. So if you look at Keytruda which is kind of one of the leading immunotherapy that people might have heard of is basically if I oversimplify for non-biologist it's basically a molecule that basically open the gates for letting the dogs out that are going to go and attack your cancer from your immune system if you want. Um the thing about checkpoints is when they work they're fantastic because those people 5 years after treatment are cured in the sense they have no remaining disease. Uh but only 60% of people are disease free after five years if you look at the phase three published data of Keytruda. So again for those 60% of people it's amazing but it means that there's 40% of people where you go through the treatment you're fighting for cancer and the treatment doesn't really work for you and also what is difficult is those treatments are wonderful but they a lot of time come with very serious side effects very different from chemotherapy or radiotherapy. The side effect of immunotherapy are mostly immune disease.

So you see people if you look at the label or the clinical studies people that get checkpoints whether it's anti-PD-1 or anti-CTLA-4 that have a lot of T-cells expanded. But if you take my analogy, you unleash the dogs in a dark room. And they're going crazy, they are barking, they are running around, and they attack whatever because they don't know what they are looking for. And in many cases they attack the self which create those autoimmune disease and they don't attack the cancer.

</details>

**豪尔赫·康德**: 明白了。

<details>
<summary>Original English</summary>

**Jorge Conde**: Mhm.

</details>

**斯特凡·班塞尔**: 所以我们需要设计一款产品，回到刚才的猎犬类比，就是精准地教会这些猎犬要寻找什么样的气味与敌人。这正是我们技术的精妙之处：Keytruda 负责松开锁链释放猎犬，而我们的 mRNA 癌症药物则负责给猎犬一张清晰无比的照片，告诉它们：“这就是你们必须消灭的目标，去找到它并彻底摧毁它。”

<details>
<summary>Original English</summary>

**Stéphane Bancel**: So that we could design a product to basically teach if I go back to the dog analogy to teach those dogs what to look for very specifically. And that's really the beauty about our technology is if you think about Keytruda basically unleash the dogs but our mRNA individualized cancer treatment gives the picture of what the dog should look for and says: "This is what you're looking for, go get it and destroy it."

</details>

### 个性化定制与传统疫苗

**豪尔赫·康德**: 好的，这正是**个性化癌症疫苗**（Personalized Cancer Vaccine）在黑色素瘤治疗中产生巨大冲击的机制所在。稍后我们会回到“个性化定制”这个极其引人入胜的话题，无论从技术、商业还是生物学角度它都令人惊叹。但在那之前，我想先厘清一个术语定义：很多人听到“疫苗”这个词，脑海中浮现的都是预防性疫苗，比如注射后预防小儿麻痹症或预防新冠。但在肿瘤领域，这实际上是一种**治疗性疫苗**（Therapeutic Vaccine）。你能否解释一下这两者在概念上的异同？

<details>
<summary>Original English</summary>

**Jorge Conde**: Okay. Okay. So now that that's where the personalized cancer vaccine um uh technology will make a big impact on the treatment of melanoma. So that we'll come back to the personalized piece because I think that's just fascinating not only from a technology and business perspective but biology perspective. But before we get there, help me define what is a vaccine here. Because as folks think about vaccines historically, they think about it in a preventative context—you get a shot to prevent polio or prevent COVID. Here you have cancer, so it's a therapeutic vaccine. How should people think about that distinction?

</details>

**斯特凡·班塞尔**: 你总结得非常精准。整个领域之所以一直沿用“疫苗”这个词汇——这不是我们发明的提法，而是沿袭了学术界20多年来上千次临床试验的传统——是因为其本质都是**训练和教育免疫系统**。如果你思考新冠疫苗或流感疫苗，我们在健康人体内注射一段病毒特征的遗传指令，让免疫系统在真正遭遇病毒前做好识别与防御准备。

而在人体内，无论是受外界诱变因素影响，还是细胞正常分裂复制过程中 DNA 突变积累导致的癌细胞产生，我们的免疫系统原本具备很高的警觉性，可以在极早期发现并清除异常细胞。但如果癌细胞逃脱了监管发展成肿瘤，核心挑战就在于如何重新纠正并强化免疫系统的识别能力。正因如此，科学界将这种肿瘤发生后的治疗性免疫训练方法同样命名为“疫苗”。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: It's a great characterization and the reason the field has used the word vaccine—it was not us using it, we just follow the field as I mentioned there been a thousand plus clinical trial—is because it's about teaching your immune system. If you think about a COVID vaccine or flu vaccine, you teach your immune system so it's ready when the virus comes to you.

Here, whether it's outside factors or just as you have cell replication and you have mistakes that happen that create mutation of DNA that are cancer cells, our immune system is very well trained to basically notice those cancer cells very early and get rid of them. But if your cancer grows, then the question is how can you retrain the immune system? So I think that's why the field use the word vaccine for that approach as well. Even as you said it's a therapeutic treatment approach post cancer, it's about the teaching of the immune system.

</details>

### mRNA 为何能破局千次失败

**豪尔赫·康德**: 明白了。正如你刚才提到的，整个肿瘤领域在过去尝试过无数次，大约1000次临床试验无一例外全部折戟。而如今，你、Moderna 与默沙东团队在此取得了成功。这一次究竟有什么根本性的不同？mRNA 技术到底蕴含了怎样的特质，能让免疫系统以传统方式完全无法实现的高效机制完成学习？

<details>
<summary>Original English</summary>

**Jorge Conde**: Okay. And so as you point out, the field has tried this many times before. A thousand on the order of a thousand clinical trials um have have tested this theory. They've all failed. Uh you and Moderna and Merck have succeeded here. Um what was different this time? What is it about mRNA technology that enables the immune system to learn in a way that other approaches uh were unable uh uh to be successful?

</details>

**斯特凡·班塞尔**: 我认为核心差异由两个关键要素构成：其一是 **mRNA 递送与表达技术**本身的生物学机制；其二是通过为每一个单独的人量身定制药物所实现的**高度个体化**（Individualization）。

让我逐一详细剖析。首先在 mRNA 底层技术方面：早在2015年，我们就与颁发诺贝尔生理学或医学奖的瑞典**卡罗林斯卡学院**（Karolinska Institute）共同发表过重磅论文。我无法评价其他采用不同修饰核苷或脂质纳米颗粒（LNP）的 mRNA 公司，但就 Moderna 的技术而言，当我们把 mRNA 注射进人体肌肉组织后——不论是新冠疫苗、流感疫苗还是这款个性化癌症疫苗——mRNA 分子会顺着淋巴系统精准富集到淋巴结，并被**抗原呈递细胞**（APC，Antigen-Presenting Cells）吞噬摄入。正如大家所知，APC 细胞是整个人类免疫网络中最核心的枢纽。

我们在卡罗林斯卡学院的研究中就已经从机制上完全证实：mRNA 能够高效穿透细胞膜进入 APC 内部，利用宿主细胞自身的核糖体将 mRNA 携带的遗传指令翻译成**新抗原蛋白**，并从细胞内部直接呈递到细胞表面。

这一机制与过去肿瘤界绝大多数癌症疫苗有着天壤之别。以往的癌症疫苗基本都是通过生物反应器体外生产重组蛋白或合成多肽片段，然后注射进患者体内。重组蛋白进入血液循环后，只能在血管内循环游弋。虽然外周免疫细胞也能遇到它们，但那种接触方式是被动且低效的，根本无法像 mRNA 这样从 APC 内部完成高质量的抗原加工与内源性呈递。我们深信，这种内源性抗原呈递是激活强效免疫应答极其关键的核心机制。

第二项颠覆性要素就是彻底的个体化。在过去的几十年里，科学界不仅大多依赖多肽或蛋白技术，而且几乎都在尝试寻找**共享抗原**（Shared Antigens）——试图找到一种在所有黑色素瘤或肺癌患者身上普遍存在的公共突变蛋白。然而现实是，癌症本质上是一种高度异质性的 DNA 基因疾病。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Yeah, I think there's there are two components. Uh, one is the mRNA technology and I think the other one is the individualization by designing a product for one human at a time. So, let me go through those two.

On the technology of mRNA side, what we have known and published uh actually with Karolinska as you know the institute in Sweden that give the Nobel Prize of medicine back in 2015 is that with our technology—I cannot speak about other mRNA companies that have different mRNAs, different lipids and so on—but with our technology when we inject our mRNA in a muscle whether it's a COVID shot or flu shot or this cancer treatment basically the mRNA goes down to your lymph node and enters the APCs, the antigen presenting cells, which as you know are key component of your immune cells, and the mRNA gets inside the APCs. This we've demonstrated and proven at the time with Karolinska. And then it basically translates the message contained in the mRNA inside the APCs, inside your immune cells, and presented from within. So we think it's a very important differentiation from most of the previous vaccine in cancer in the field that were made by protein or peptide that basically are made in reactors, are injected in the in the in the patient, but basically turn into the blood. Because as you know recombinant or protein when you inject them they just go into your blood and they turn around, so your immune system sees them but not in the same manner from within as it done with the mRNA. So we think that's one very important component of uh immune presentation if that makes sense.

The other component is really individualization. In the past a lot of time people have tried with non-mRNA i.e. protein technology or peptide, but also we tried a shared antigen. Whereas here what we said is because cancer is a disease of DNA...

</details>

### 新抗原算法与34个突变位点

**豪尔赫·康德**: 确实如此。

<details>
<summary>Original English</summary>

**Jorge Conde**: Mhm.

</details>

**斯特凡·班塞尔**: 正是因为过去20年间**全基因组测序**的成本发生了断崖式下降，我们今天能够实现这样的流程：我们首先取得患者肿瘤的活检组织，测序读取其完整的 30 亿对 DNA 碱基序列；然后我们提取患者健康体细胞做相同的深度测序。我们将正常细胞与癌细胞的基因组进行逐字、逐核苷酸的比对。

随后，我们利用自主研发的预测算法，在患者肿瘤中发现的数百乃至数千个突变中，基于免疫学与肿瘤生物学的最前沿认知，精确计算并筛选出免疫原性最强、最相关的突变。我们从中精选出多达 **34 个最具相关性的突变新抗原位点**，将编码这34个位点的基因序列拼接串联成一条长链 mRNA 分子。我们在大约30到40天内为该患者完成全定制合成与质检，送达医院为患者进行肌肉注射。

当这剂 mRNA 注入体内后，它就能精准教会免疫系统识别该患者癌细胞专属的突变指纹——这不是其他通用病人的公共抗原，而是百分之百专属于该患者肿瘤细胞的精准靶点。我们在 ASCO 大会上展示并发表的二期临床数据显示：**不同患者之间的新抗原重合度极低，约 90% 的新抗原位点在人与人之间是完全不同的**。

当我们最初启动这个项目时，业内对此一无所知，因为大家过去都在寻找共享抗原。我们当时也在猜想：患者之间的重合度会是2%、5%还是90%？实际数据证明，高达90%的靶点在个体之间完全不同。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: What we're going to do here because the cost of sequencing have dropped so much in the last 20 years is we're going to basically take a biopsy of your tumor. We're going to read all the letters of its DNA, the 3 gigabytes of of these genes. And then we're going to do the same things with the healthy cell of your body. And we're going to literally compare letter by letter, nucleotide by nucleotide. And then we're going to use an algorithm to identify over your hundreds or thousands of mutation which one based on the current knowledge of a field of immunology and cancer which one of those mutations are the most relevant. We select the 34 that we believe are the most relevant and we stitch them together into one big mRNA molecule which we make in 30ish days for you that is injected then in a hospital intramuscularly. And so when this is injected in your body, basically it teaches the immune system the signature of your cancer cell that it missed. Not the signature of every other patient with a shared antigen, but the very specific signature of your cancer cell.

And what we we showed at ASCO and we published from a phase two study, but we believe it's the same thing in the phase three because it's mechanistic, is that around 90% of the antigen are different patient to patient. Because when we started we had no idea because again the field came from shared antigen. So when we started like we have no idea we're going to get 2%, 5%, 90% of same antigen across all the patient. Actually 90% of antigen are different from a human to another one.

</details>

**豪尔赫·康德**: 令人惊叹。也就是说，这种疗法能够成立的唯一途径，就是通过完全的个性化定制。

<details>
<summary>Original English</summary>

**Jorge Conde**: Wow. So the only way this can work is through personalization, individualization.

</details>

**斯特凡·班塞尔**: 毫无疑问，确实如此。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Exactly.

</details>

**豪尔赫·康德**: 在对比正常组织与肿瘤组织的基因组差异时，我很想知道你们是如何确定将 **34** 作为最佳突变位点数量上限的？背后必然有深刻的考量。另外，驱动这一切的**算法黑盒**究竟是如何工作的？这是 Moderna 独有的专有算法，还是行业通用技术？能否带我们一窥这个黑盒内部的秘密？

<details>
<summary>Original English</summary>

**Jorge Conde**: You know assuming that that carries over. Um, and so in that regard, uh, you know, if you're doing, let's say, this normal to tumor comparison of of of the genome, you find the differences. I'm curious how you arrive at 34 as up to 34 as the right number. Um, I'm sure there's a very good reason for that. Um, but what is the algorithm that enables you to do that? Is this something that's proprietary to Moderna? Is this something that is known within the field? Help us understand like help us look into that black box.

</details>

### AI 算法演进与数据飞轮

**斯特凡·班塞尔**: 好的。我可以透露一部分关于这个黑盒的设计逻辑，但不会涉及核心机密，因为其中凝聚了极大量的 Know-How 与专利保护。

在起点阶段，我们整合了学术界公开的所有免疫学数据库、顶级文献，并与全球顶尖的免疫学家和肿瘤学家深度合作。以此为基石，我们在过去十年中生成并积累了海量的内部专有实验数据。同时，我们还与诊断公司、细胞治疗公司等合作伙伴建立战略协同，获取了海量的患者 T 细胞图谱等高质量训练数据。

这里有一个极具启发性的事实：我们上周公布的三期临床阳性数据，所使用的算法版本我称之为 **mRNA-4157 1.0 版**。因为三期试验所用的算法与二期、一期完全一致，而这项临床研究已经启动了近10年，这意味着这套算法在本质上是10年前写就的！

即便是基于这套10年前的 1.0 算法，临床数据已经极其惊艳：二期临床5年随访显示80%的患者实现无病生存。但不可否认，仍有20%的患者未能产生应答。现在我们拥有了完整三期临床患者的所有组织样本、血液随访标本和基因组测序数据，我们正在全力进行深度数据挖掘，去剖析为什么某些患者应答极好，而另外20%的患者没有应答。

我们将探究是否有可优化的算法参数，并基于严谨的科学证据向美国 FDA 申请将预测算法从 1.0 升级迭代至 **2.0 版本**。当然，全过程必须在极度严谨受控的框架下进行以确保疗效不出现回退。

这就像我们经常谈论的人工智能一样，大家常开玩笑说：“今天你所见到的 AI，是你余生中能见到的最差版本。”这对于我们的个体化 mRNA 算法同样适用——**今天 Moderna 展现的 1.0 版本，将是医学史上你能见到的最简陋的一代版本**。这让我们不仅对黑色素瘤中那20%未应答患者的后续解决方案充满信心，更对攻克胰腺癌等传统免疫疗法束手无策的“冷肿瘤”充满了希望。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Sure. So I want to share a little bit about the black box—not too much because there's a lot of know-how and and things are very confidential to us—but basically we started with of course what is known in the field. And so we basically use a lot of database and publication and a lot of scientists and doctors kind of best-in-class in immunology and in oncology. And then from that starting point we used a lot of internal data that we generated over time. We also partnered with some companies that because they are having the diagnostics space or they are let's say cell therapy and other space in oncology had access to a lot of data, a lot of T-cell mapping and so on that were very useful for the learning.

The thing that is interesting about the data we showed last week is this is what I consider mRNA-4157 version 1.0. Because the algorithm from the phase three was the same from the phase two, was the same from phase one. But because we've been doing this for 10 years, it's a 10-year-old algorithm. So as you look at the data it works pretty well, right? As we said about the phase two data 80% of people are disease-free after 5 years, it's amazing for those patients, but there's still 20% of patients that don't respond. And so one of the thing we're going to be doing now that we have access to a phase three patient data and samples is to go back and mine that data to figure out why some patient responded and why some other patient did not respond. Because we have access to all their blood sample, the sequence, everything, and we're going to try to see can we improve the algorithm. Uh and we will go to the FDA if we find scientific reason why we should change the algorithm to go from let's say 1.0 to a 2.0 algorithm and then change it. Of course, we have to do that in a very controlled way to ensure we don't lose efficacy very obviously.

But the way I think about it is like when we talk about AI, we always joke that the current version of AI is the worst we're going to see in our lifetime. Well, it's exactly the same for this mRNA therapy, which is the current version of mRNA therapy at Moderna is the worst version you're going to see for the rest of medical history. And so that gives me a lot of hope not only in melanoma for those 20% of patient that don't respond, but also for potentially other tumors that have been really hard in the field like you know pancreas cancer and others where immunotherapy doesn't work. We want to be able to learn a lot about the technology using also what the field has learned in the last 10 years. Because the field has learned a lot as you know, this is even not in 1.0. So that's why I'm so excited about what's coming next.

</details>

### 工艺流程与42天生产周期

**豪尔赫·康德**: 真是令人振奋。回想起来，你我相识已久，我有幸从最早期的日子就见证了 Moderna 的成长。

<details>
<summary>Original English</summary>

**Jorge Conde**: That's fantastic. So, um, looking back, uh, you and I have had, we've known each other for a very long time. Uh, I won't depress you or me by saying how long,

</details>

**斯特凡·班塞尔**: 当时你还非常年轻，简直就像还在上幼儿园一样。（笑）

<details>
<summary>Original English</summary>

**Stéphane Bancel**: But you were very young. You were in kindergarten! [laughter]

</details>

**豪尔赫·康德**: 哈哈，但我确实见证了最初阶段的 Moderna。有一点从过去到现在始终未变：你骨子里是一位纯粹的工程师，从第一天起就对工艺、流程控制、运营和极致效率有着近乎偏执的追求。而这恰恰是个性化癌症疫苗能够落地的关键支柱。

我们不妨对比目前肿瘤领域另一类重磅的个性化疗法——**CAR-T 细胞疗法**。在 CAR-T 中，需要提取患者的 T 细胞并在体外进行复杂的活细胞扩增与基因改造，这涉及到极其繁琐的活细胞供应链，面临批次失败、耗时冗长等瓶颈。而在 Moderna 的体系下，你们是如何实现个性化端到端工业化交付的？从获取活检组织到给患者注射（needle-to-needle），目前需要多长时间？未来又将如何演进？

<details>
<summary>Original English</summary>

**Jorge Conde**: But so I've had the benefit of seeing Moderna from the earliest days. Yes. And one thing that is true that was true then is true today is first of all you are an engineer at heart and you have from the very beginning been obsessed with process, with operations, with being efficient. And those pieces are really essential here. Um, and let me maybe one way to frame it is I think a lot of people think about the other big personalized therapy that exists in cancer is CAR-T cell therapy, right? And in that case, CAR-T cell therapy for folks that may be less familiar, you're taking cells from a human, you're genetically modifying them, you're growing them up, and then you're putting those cells back into a human. And there's a lot of failure points, there's a lot of complexity, it's very expensive, and it takes a long time. Here you're doing something very different. Talk to us about the operational feat that is personalized cancer vaccine manufacturing. What does that needle-to-needle time look like? How do you think about that and how do you execute on that?

</details>

**斯特凡·班塞尔**: 当然。目前从穿刺活检到疫苗制备完成送达医院（needle-to-needle），**全流程大约需要 42 天**。随着我们持续推进自动化改造与流程精益化，这个时间还会进一步缩短。我们现阶段的目标是将生产交付周期压缩到约30天，而在未来我们有信心将其缩短至几周以内。

让我为大家拆解这 42 天内的关键工序：
1. **活检与运输**：医院对患者肿瘤进行穿刺取样，样本通过冷链火速运抵我们的中心实验室。
2. **双基因组测序**：同步完成肿瘤组织与健康血液细胞的 DNA/RNA 深度测序（生成数以 G 计的数据）。
3. **算法预测与设计**：算法管道自动比对、识别突变并完成 34 个新抗原位点的排序与拼接，生成数字化的质粒分子序列。
4. **DNA 模板合成**：利用自动化生物合成系统合成出物理 DNA 模板。
5. **mRNA 转录与加帽**：在无细胞体外转录体系中，以 DNA 为模板酶促合成 mRNA 分子并完成加帽修饰。
6. **LNP 纳米脂质体包裹**：将合成的 mRNA 原液包裹进专有的纳米脂质颗粒中，确保其稳定性与靶向递送能力。
7. **无菌分装与质检**：完成冻干/无菌灌装，并执行极其严苛的质量控制与无菌检测，随后空运发往患者所在医院。

这里与 CAR-T 存在一个本质的物理与生物学差异：**我们的全流程完全不涉及活细胞培养**（Cell-Free Process）。

在传统生物制药以及 CAR-T 中，你必须依赖活细胞反应器。正如所有生物工程师所知，细胞是非常脆弱的，如果在反应器中施加过高压力或改变流体剪切力，细胞就会大面积死亡，因此整个行业不得不使用数千升的庞大反应罐与极低浓度的液体环境。而 Moderna 的核心工艺是**无细胞化学合成**，整个反应体系体积极小，所有试剂均处于高浓度状态。这种高密度无细胞体系让我们能够构建高度紧凑、模块化、完全由计算机算法与工业机器人控制的全自动微型生产线。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Sure. So the time is around 42 days now needle to needle. So from taking the biopsy to getting the vaccine in hospital ready for you. I think we're going to be able to improve that as we still have a lot of efficiencies to work on and automations and so on. We are aiming for 30-ish days, and then I think over time we'll be able to get to a couple of weeks.

If you think about the steps: you have the biopsy, you ship the sample to us, we do the sequencing of the tumor and the sequencing of the healthy cell from your blood, then we do the run the algorithm, then we need to do the DNA of the 34 mutations, then you make the mRNA from that DNA template, then you formulate it with a lipid nanoparticle (LNP), then you put it in a vial, you test it for release, and you ship it back to the hospital.

And the big difference with CAR-T, which was your question, is we have no cells in our process. It is a cell-free process. Where in CAR-T you have cells and big reactors and you have big volumes because as you know the reason you have big volumes in biotech industry is if you compress the cells too much they die. You have the same issue with CAR-T, so it's all everything is huge. In our case, because we don't have cells, the volumes are tiny. The concentrations are very high. And so the equipment is very small, which allows us to automate a lot of the process using robotics and software.

</details>

### 工业化产能与定制门槛

**豪尔赫·康德**: 达到规模化之后，仅就黑色素瘤这一项适应症而言，你们每年大约需要生产多少剂个性化疫苗？

<details>
<summary>Original English</summary>

**Jorge Conde**: And at scale, how many roughly how many for let's say let's just focus on melanoma how many doses would you need to produce in a given year?

</details>

**斯特凡·班塞尔**: 目前凭借正在进行的9项临床试验，我们已经累计生产了数千剂个体化药物。我们在马萨诸塞州马尔堡的专属工厂，年产能已经达到**数万剂**级别。随着工艺和自动化技术的持续升级，同一厂房内的单位产出还会成倍提升。如果查看全球黑色素瘤的发病率，单座工厂数万剂的产能已经能够完全覆盖黑色素瘤市场的全部需求。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: So we've already got thousands of doses because of nine clinical studies that are ongoing. The facility will be able to make—the one in Marlborough, Mass—tens of thousands of doses. And then as we keep improving the technology that number is going to go up in the same facility and then we might need to build several other facilities. But if you look at the incidence of melanoma, if you have tens of thousands of doses you're going to cover easily the melanoma market.

</details>

**豪尔赫·康德**: 你们目前是否公开过对生产成本（COGS）和产品定价的考量框架？

<details>
<summary>Original English</summary>

**Jorge Conde**: Yeah, I can believe that. Have you disclosed how you think about COGS and price or is that something that...

</details>

**斯特凡·班塞尔**: 我们目前尚未正式披露。我们需要先与默沙东团队完整公布三期临床数据，并基于该疗法为患者和医疗系统创造的临床价值，与医保支付方进行深入沟通后再行确定。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: We have not disclosed yet. We need first to disclose the data with our Merck colleagues. We need to engage with the payers once we can share the data in terms of what is the value being driven there and so on. But this has not been discussed yet.

</details>

**豪尔赫·康德**: 围绕“个性化”这个概念，相信你也关注到了前段时间 **GitLab** 创始人兼 CEO Sid Sijbrandij 在确诊骨肉瘤（Osteosarcoma）后开启“创始人模式”自救的故事。未来像 Sid 这样的超级极客患者，是会普遍寻求与 Moderna 这样的平台合作，还是说这种 N=1 的自制自救模式会与工业界长期并行发展？

<details>
<summary>Original English</summary>

**Jorge Conde**: So maybe one place to focus is on this concept of personalization. I'm sure you've seen the story of the GitLab founder who went founder mode on his own osteosarcoma. Number one: do the future Sids of the world come to Moderna, or is this N-of-1 phenomenon something that you think will just happen and exist in parallel?

</details>

**斯特凡·班塞尔**: 我坚信绝大多数患者最终都会选择 Moderna 这样的工业化平台，因为这兼具无可比拟的安全性和便利性。

任何注射类生物制品的生产都伴随着极高的污染风险。如果在给患者注射的药物中混入了哪怕一个细菌，都可能引发致命的**脓毒症**（Sepsis）；而且在多步骤的精密合成中，任何人为失误都会导致质量失控。而在经过 FDA 严苛 GMP（良好生产规范）验证的工业化全自动化工厂中，这种风险被降到了最低。

这就像人类使用工具的历史一样：当你身处原始洞穴且街上没有刀具店，为了养活家人你当然只能亲手去打磨石刀；但当街角开了一家能提供高品质、经过安全验证的刀具店时，你自然会把宝贵的时间精力投入到其他更有价值的事情上。随着生物医药工业化水准的提高，专业化分工必然是最终归宿。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: So I think they will come most of them to Moderna because it is just going to be easier and safer. Because as you know making an injectable product always carries risk of contamination of a product. If you inject to somebody a product that has even one copy of bacteria, you might give the patient sepsis. Then you always have a question of quality because when you have a multi-step process, a mistake can happen. And of course, if it's industrialized and has been validated in terms of Good Manufacturing Practice kind of FDA standard, you have much less chance of this happening.

So, it's a bit like every tool in life, which is: do you make your first knife because there's no knife store and you are in a cave and you need to feed your family? Yes, of course you make your first knife because you have to feed your family, right? But when you have a store making high-quality knives down the street, you're going to use your time to do something else. So I think it's a bit of the same phenomenon which is like in any technology: when you have industrial scale of high-quality product, you use your time as a human to do something else with your time.

</details>

### 个性化药物监管路径

**豪尔赫·康德**: 在这样的个性化世界中，监管体系是如何运转的？正如你刚才所说，每一剂药的序列都独一无二，FDA 不可能去逐个审批具体的分子。监管的核心到底是在审评 mRNA 合成工艺、预测算法，还是在审评整个端到端的一体化系统？请帮我们建立一个清晰的认知框架。

<details>
<summary>Original English</summary>

**Jorge Conde**: And in that world, how does the regulatory apparatus function here? In other words, you mentioned earlier you along with Merck will prepare a regulatory filing soon. What gets regulated here? Because every dose is different, so obviously every dose doesn't get approved. Is it the process for synthesizing mRNA? Is it the algorithm? Is it a combination of the entire system? Help us understand that and build intuition around how we think that these kinds of personalized medicines will be regulated in the future.

</details>

**斯特凡·班塞尔**: 幸运的是，行业已经有了先例。正如你提到的 CAR-T 疗法，它获批的途径与我们即将提交的完全一致——监管机构批准的是**工艺生物制品许可申请**（Process BLA），而不是针对单一固定分子的 Product BLA。

Moderna 旗下目前已有5款传统产品获批上市，那些属于典型的固定产品批准。而对于这款个性化癌症疫苗，从当年启动临床试验提交研究性新药申请（IND）开始，我们申报的就是一个**工艺流程 IND**（Process IND）。

在过去十年中，我们与 FDA 展开了极为密集且持续的深度沟通。在每一个阶段性节点，从一期进入二期、再到三期试验前夕的“二期临床结束会议”（End of Phase 2 Meeting），我们都与 FDA 就试验方案设计、算法验证指标、GMP 生产控制协议达成过详尽的书面共识。

FDA 最核心、最合理的诉求在于**工艺稳健性与可重现性**：如果从前端输入相同的肿瘤活检与健康血液样本，通过你们这个黑盒系统，最终交付给患者的个体化制剂是否具备高度确定、一致且受控的质量输出？我们通过大量实验数据向 FDA 充分证明了整个算法与制造流程的极高稳健性。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Yes. So the good news is there are precedents as you mentioned CAR-T. CAR-T was also approved in the same way as we believe this mRNA will be which is as a process BLA not a product BLA. So as you know Moderna has five products approved, so that's really product approval. On this one, the whole process since we started in the clinic the IND was a process IND.

Because we had to ask the FDA can we go to the clinic, do you think it's safe and do you think we have a good control of a process so we can do safely a phase one study. So we already had that discussion just to go into the clinic years ago. And then before we started every phase three we need to have end of phase two meeting and agree the design of a study, the manufacturing protocol with the FDA. So those discussions have happened for years. There's been a lot of discussion, a lot of engagement. Several times we've had technical questions on the manufacturing front where we basically requested additional meetings to ask the guidance, to also educate them on the technology, what we've learned and so on. So there's already been a lot of discussions and there's a very clear regulatory pathway in terms of approving the entire process.

Basically, what the FDA wants to know, which is very legitimate, which I would want for my own family sake obviously, which is: if you get the same sample at the beginning—the tumor and the blood—do you get the same product made at the end of a big black box? And that's what we have to demonstrate first to ourselves and then with the data to the FDA so that we have really robustness overall process. So if we have the same input, we're going to get the same output going to patient as an individualized medicine.

</details>

### 拓展三大适应症方向

**豪尔赫·康德**: 展望黑色素瘤之外的广阔天地，Moderna 在其他癌种上的拓展雄心是怎样的？这种个性化 mRNA 疫苗是否适用于广泛的实体瘤？在哪些癌种上最有希望取得突破？

<details>
<summary>Original English</summary>

**Jorge Conde**: How do we think about moving beyond or how do you all think about moving beyond melanoma? Is this an approach that's going to be applicable to a broad range of cancers? Are there cancers that are much more likely where this is going to be a viable option versus others? And sort of what's your—I'll use the word—what's the ambition here for where cancer vaccines can happen?

</details>

**斯特凡·班塞尔**: 我们的雄心非常宏大。因为在机制上，我们已经确凿证实：**Moderna 的技术能够成功教育并诱导人体生成全新的（de novo）抗原特异性 T 细胞**。我们在今年 ASCO 上公布了接受治疗前后黑色素瘤患者的血液 T 细胞图谱数据——结果不仅显示原有 T 细胞得到了扩增，更重要的是诱导产生了此前患者体内根本不存在的、专门针对 mRNA 所编码新抗原的全新 T 细胞克隆。

基于这一机制验证，我们正沿着**三大战略方向**进行全面推进：

1. **全面进军免疫检查点已获批的癌种（联合疗法）**：PD-1 单抗与我们的 mRNA 癌症疫苗作用机制完全正交互补，两者结合能产生强大的协同倍增效应。目前我们已经在**非小细胞肺癌**（NSCLC）进入三期临床，并在**肾癌**（Kidney Cancer）和**膀胱癌**（Bladder Cancer）开展二期临床试验。
2. **前移至超早期肿瘤（单药疗法）**：在早期肿瘤中，临床医生通常不愿使用免疫检查点抑制剂，因为其自身免疫毒副作用过于沉重。例如对于通过低剂量螺旋 CT 筛查出的**一期早期肺癌患者**，我们在2026年春季启动了一项重磅三期临床——在手术切除后，将 Moderna 的 mRNA 疫苗作为**单药辅助治疗**（不联合 Keytruda），其安全性与常规流感疫苗相当（仅表现为一过性疲劳发热），极大地改善了早期患者的获益风险比。
3. **攻坚检查点抑制剂无效的“冷肿瘤”**：例如**胰腺癌**（Pancreatic Cancer）和**胃癌**（Gastric Cancer）。这两大癌种在历史上对 Keytruda 完全不产生应答，临床试验全部失败。但由于我们能够原位激活全新的 T 细胞，我们正在这两个领域积极开展探索；同时还可与针对特定突变（如 KRAS 突变靶向药）的全新小分子药物开展正交联合治疗。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: The ambition is pretty big because we believe we have demonstrated at least to ourselves and we hope to the world that we are able to create an education of T-cells. And this we showed it even this year: we took the blood before treatment, after treatment of cancer patient melanoma with our technology, and we showed that not only we have an expansion of the T-cells, but we have de novo new T-cells being created that recognize what we code in the mRNA that was not in the patient's body before the treatment. So we really in my book have proven to ourselves and to the clinical community that Moderna's technology can teach the immune system to develop new T-cells to go attack your cancer.

So based on that there are basically I would say three different vectors we're going after in terms of expansion from melanoma:

First, we're going everywhere where Keytruda works. Because as I told you we believe the mechanism of action of a PD-1 and Moderna's therapy are totally orthogonal. So we think these allow to have synergistic element and efficacy for the patients. And so we are in phase three for lung. We're in phase two for kidney cancer, bladder cancer. So we have a whole slew of studies ongoing where the world knows that Keytruda works, and we believe you're going to see a material improvement versus Keytruda alone.

The second vector is to go early in disease where checkpoints work. And the best example is we announced in the spring of 2026 starting a phase three study for patients with stage one lung cancer as a monotherapy without checkpoint.

And we are doing that because we believe when you go early in disease checkpoints are not used because of the side effect that they bring. Because if you have stage one cancer, the medical field thinks it's worth monitoring your cancer versus giving you a checkpoint because not everybody's going to respond, but everybody's going to get pretty serious lifelong side effects like autoimmune disease. But what if you could have an mRNA made for cancer patient that has lung disease stage one, which you can find easily with screening? The idea is you do a surgery which is standard of care, and you give our monotherapy which the side effect is similar to a vaccine—you know you might feel tired for a day but that's it.

The third vector is where checkpoints don't work, so of course it's where you have the highest risk. But because the mechanism of action is different from a checkpoint, we and Merck believe that there's a very good scientific rationale to go try. So two places we're trying right now is pancreas cancer and also gastric cancer. Those two cancer types checkpoints and Keytruda do not work. But we think because again the mechanism of action is different from checkpoint and we know now that we have a proof that we can create de novo T-cells, we think it's an experiment worth running. And as you know literally yesterday Revolution Medicines had a wonderful new medicine approved for pancreas cancer using the KRAS mutation. What if you could combine that medicine and our therapy? Those are very orthogonal mechanisms of action.

</details>

**豪尔赫·康德**: 哇，这真是给广大癌症患者及其家庭带来了巨大的希望与曙光。

<details>
<summary>Original English</summary>

**Jorge Conde**: Wow. Well that that gives a lot of reason for I think cancer patients and their families to have a lot of hope for the future of novel therapies in this field.

</details>

### 自免疾病与全平台未来

**斯特凡·班塞尔**: 是的。更重要的是，正如我刚才强调的，这仅仅是 1.0 版本。我正在极力推动我们的算法与研发团队打破思维定势，利用最前沿的 AI 技术去全面挖掘海量临床数据，特别是死磕那 20% 在5年后仍未应答的患者亚群，探明未应答的根源，进而迭代优化我们的预测算法。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Yes, and on top of what we just said remember this is version 1.0. So what I saw is very powerful and I'm really pushing our team to think really outside the box and to do a lot of analysis and to use AI to look at that gigantic set of data that we have, which is what are the things we can learn from the clinical studies to understand about the people that did not respond. Because I think you always learn more from things that don't work than things that work. So I want to obsess about the 20% of patients that do not respond 5 years out so we can understand why they did not respond and can we tweak anything in the algorithm or in the technology to be able to help them.

</details>

**豪尔赫·康德**: 这确实不可思议。看到你们将一个最初并非为突发大流行设计的底层技术平台，在面对新冠大流行时敏锐调转方向拯救了数以亿计的生命，如今在十年之后又成功将平台重定向回你们最初创立时矢志攻克的重大疾病领域，这太令人震撼了。

<details>
<summary>Original English</summary>

**Jorge Conde**: Wow, that's remarkable. And just to wrap, I think it's remarkable to see how you were able to take a technology platform that originally wasn't built for a pandemic, point it at a pandemic, create a vaccine for millions and millions and millions of people, and essentially point it back towards treating some of the diseases that you had originally intended 10 years later as you described.

</details>

**斯特凡·班塞尔**: 确实如此。此外在今年年底前，我们针对儿童罕见肝脏遗传病的后期关键临床试验即将读出数据。在早期一/二期试验中，接受治疗长达3年的患儿状态极佳。

更令我兴奋的是，在今年6月的年度科学日上，我们正式宣布 mRNA 平台的下一座珠穆朗玛峰是——**自身免疫性疾病**（Autoimmune Diseases）。我们在感染性疾病和肿瘤领域对免疫系统的理解已经极其深厚。过去制药工业在自免领域做的主要是缓解症状，治标不治本；而我们希望利用 mRNA 从源头上调节异常免疫细胞，实现对自免疾病根源的治疗。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: It's very remarkable. And the piece that's going to be exciting or maybe to close is before the end of the year we should have our pivotal study—so late stage study—for rare genetic disease for kids that have rare genetic disease of the liver. The phase 1/2 has shown kids three years on drug doing fantastic.

And in June we had our annual science day and we announced that the next mountain where we are pointing mRNA platform is autoimmune disease. Because if you think about it we've learned a lot from infectious disease which are mediated by the immune system, and cancer we just been talking a lot about immune system. So we learned so much about the immune system that we think we have some very novel approach on how to treat the root cause of autoimmune disease not the symptoms which is what the pharma industry has been doing. It's of course very helpful to patients to treat the symptoms so we can have higher quality of life, but it doesn't treat the root cause. And we think we might have found ways to use the immune system to treat the root cause of autoimmune disease. So we're quite excited about what's to come.

</details>

**豪尔赫·康德**: 在自身免疫疾病方面，未来的技术路线是设计标准化的通用调制产品，还是走全流程的个性化定制路径？

<details>
<summary>Original English</summary>

**Jorge Conde**: Would the theory there be that you'd have personalized autoimmune modulators or would this be more a product or more a process?

</details>

**斯特凡·班塞尔**: 我们正在双线并进。我们在今年春季公布的是面向所有患者的通用型产品；但目前最让我感到兴奋且仍在实验室阶段推进的，是**个体化自免疗法**——直接靶向并精确清除那些将自身组织误认为外来敌人的异常免疫细胞克隆，彻底消除自免疾病的根源。虽然目前尚处于早期，但这代表了未来的无限可能。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: So, we're doing both. What we presented in the spring was a product that would be the same for everybody. But what I'm the most excited about which is in the lab still is the ability to do individualized autoimmune treatment where you target directly to the immune cells that are attacking your body as self when you have an autoimmune disease and to have basically part of your immune system going attacking those immune cells that are out of order so that you are able to take the cause of immune disease out. Again, it's still early days but that's what I'm excited about today.

</details>

**豪尔赫·康德**: 从传染病到恶性肿瘤，再到未来的自身免疫性疾病，当你们准备好时，我们非常期待邀请你回到 a16z 播客录制第三集，完成这壮丽的三部曲！

<details>
<summary>Original English</summary>

**Jorge Conde**: Well, going from infectious disease to cancer to eventually autoimmune disease, we would love to have you back on the podcast to film episode 3 and complete the trilogy when you're ready.

</details>

**斯特凡·班塞尔**: 太棒了，一言为定。

<details>
<summary>Original English</summary>

**Stéphane Bancel**: Wonderful.

</details>

**豪尔赫·康德**: 斯特凡，非常感谢你再次做客 a16z 播客。一如既往，见到你非常高兴，再次向你们取得的历史性突破表示热烈祝贺！

<details>
<summary>Original English</summary>

**Jorge Conde**: Stéphane, thank you so much for joining us on the a16z podcast. As always, it's great to see you, and congratulations!

</details>