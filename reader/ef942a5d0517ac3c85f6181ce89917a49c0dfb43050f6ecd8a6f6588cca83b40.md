---
author: TED
date: '2026-06-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=W23KEEcFqTk
speaker: TED
tags:
  - misinformation
  - consensus-algorithm
  - social-media
  - reinforcement-learning
  - community-feedback
title: 让极化成为事实校验的动力：社区笔记的设计、算法与未来
summary: 在这场 TED 2026 访谈中，唐凤对话社区笔记的核心开发者。他们深入探讨了该系统如何利用独特的跨立场共识算法减少虚假信息传播，如何利用对抗和极化提高信息准确性，以及未来人机协作寻找共同立场的愿景。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - X
  - TED
products_models: []
media_books: []
status: evergreen
---
### 社区笔记的初衷与机制

**基斯·科尔曼**: 我们创建**社区笔记（Community Notes）**，是因为我们希望能构建一个信息更加通达、认知更加明晰的世界。随着它推广应用到互联网的更多地方，这意味着更多的人将能够获取到准确的信息。所以，这确实是一件非常棒的事情。

<details>
<summary>Original English</summary>

**Keith Coleman**: We built Community Notes because we wanted to build a better informed world. And as it scales to more parts of the internet, that means more people have access to accurate information. So yeah, it's awesome.

</details>

**唐凤**: 太好了，那我们来看看一条社区笔记。这就是一条笔记，它到底是什么？

<details>
<summary>Original English</summary>

**Audrey Tang**: Great, so let’s look at a Community Note. That's a note. So what is it?

</details>

**杰伊·巴克斯特**: 我们现在看到的这就是一个真实的社区笔记例子。简单来说，左边发贴的内容是关于伊朗的，声称美军**林肯号航空母舰**遭到了袭击，并出现了人员伤亡。但实际上，这张配图是由 AI 生成的。右边这个显示“读者添加了他们认为人们可能想要了解的背景信息”的部分，就是一条社区笔记。在这里，它实际上给出了关于这张图片错误之处的许多具体细节。事实证明，这种深入细节的程度，是政治光谱两端的人们相比于通用的虚假信息警告，实际上更信任社区笔记的一个重要原因。而这些笔记最初能够呈现在这里，是因为它们是由普通的平台用户，即社区笔记的贡献者撰写的。在它们被展示给所有用户并附在帖子下方之前，必须经过具有不同视角的贡献者打分并判定为“有帮助”。如果不满足这一条件，它们就不会被公开显示。另外需要指出的一点是，许多最优秀的笔记并不仅仅是事实核查，它们也可以为那些虽然表述正确但容易产生误导的帖子补充必不可少的背景信息。

<details>
<summary>Original English</summary>

**Jay Baxter**: So this is a real example of a Community Note we're looking at. So basically here, the post on the left is about Iran, and it’s saying the USS Lincoln has been damaged and there are casualties. But actually the image is AI-generated. So this thing on the right here that says “readers added context they thought people might want to know” -- that’s a Community Note. And what it's doing there is it's actually giving a lot of specific details about what's wrong in the image. And it turns out that that level of detail it goes into is a big reason why people on both sides of the political spectrum actually trust Community Notes more than a generic misinfo warning. The way these get here in the first place is they're actually written by a regular user, a Community Notes contributor, and before they show on the platform to everyone and attach on the post, they are rated helpful by people from different perspectives. So they’re not shown unless that happens. Another quick thing to call out is actually a lot of the best notes are not just fact-checks. They can add context to posts that are correct but otherwise misleading.

</details>

**唐凤**: 好的，所以它是一个针对新闻的背景信息引擎。但它也适用于官方账号、广告或者其他任何类型的帖子吗？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, so it’s a context-engine for news, but is it also for official accounts or ads or any kind of post?

</details>

**基斯·科尔曼**: 是的，该项目一个非常重要的原则就是所有帖子都是适用的。这意味着国家元首发布的帖子，以及我们公司自己发布的帖子，都有可能被添加笔记。正如**埃隆·马斯克**喜欢指出的那样，他自己的帖子也会被添加笔记。它经常能够识别出 AI 生成的图像，最近关于伊朗冲突的帖子里就有大量这类情况。它还检测到了世界领导人的深度伪造音频。它也覆盖了更轻松的题材，比如娱乐、时尚等等。正如你在上方所看到的，我们甚至对最近两届美国白宫政府的帖子都进行了多次笔记注解。至少在其中一个案例中，白宫实际上删除了帖子，并发布了更新后的声明。你可以想象一下，那是一个普通的人，一个互联网上的普通人写下了那条笔记。要知道，这并不是什么名人。他们只是在网上浏览，发现白宫说错了话，输入了这条笔记，提交了上去，然后突然之间，自由世界的领导人就更改了他们的公开声明。对普通人来说，这就像是一种超级力量。因此你可以理解为什么他们会有如此强烈的动力去为社区做贡献。

<details>
<summary>Original English</summary>

**Keith Coleman**: Yeah, so a really important principle of the program is that all posts are eligible. That means posts from heads of state [and] posts from our company can get noted. As Elon likes to point out, his posts get noted. It regularly identifies AI-generated imagery. [There has] been a ton of that recently with the Iran conflict. It [has] detected deepfake audio of world leaders. It covers lighter subjects like entertainment, fashion, etc. And as you can see up here, we’ve even had multiple notes on both recent White House administrations. And at least in one case, the White House actually took down the posts [and] issued an updated statement. And you can imagine there was a person, a random person on the internet, [who] wrote that note. You know, this isn’t a famous person. They went out there, saw the White House said something wrong, typed in this note, put it up there, and then suddenly, leaders of the free world changed their public statement. That’s like a superpower for people. So you can see why they're motivated to contribute.

</details>

### 诞生背景与信任机制

**唐凤**: 是的。（掌声）我听说是一个青少年促成了那次白宫的撤稿，这确实是一种超级力量。但是它的机制到底是什么？你能带我们回到十年前，在这一超级力量被发明并分发之前吗？是什么促成了这项发明？

<details>
<summary>Original English</summary>

**Audrey Tang**: Yeah. (Applause) So a teenager, I heard, caused that retraction, and it really is a superpower. But what is the mechanism? Can you take us back 10 years ago before this superpower gets invented and distributed? What caused the invention?

</details>

**基斯·科尔曼**: 对我而言，这一切的起点可以追溯到 2016 年。那时我只是一个普通的 **Twitter** 用户。我关注着 2016 年的大选。那一年有三场电视辩论，但每天在 Twitter 上也都在进行着辩论。那是我获取信息的地方，也是全世界关注焦点所在。我记得当时我获得了很多好的信息，但同时也很难分辨哪些信息是真实的。当时我站在旁观者的角度，一直在想：这个世界将如何解决这个问题？我们如何以一种行之有效、且在极化环境中让人们感到公平的方式来做到这一点？然后时光快进三年。那时我已经在 Twitter 工作了，当时整个行业已经尝试了许多方法。**Facebook** 建立了一个庞大的事实核查计划，Twitter 也在与事实核查机构合作。我们内部也有专门的团队来审查帖子，以判定它们是否具有误导性。但这些做法存在很多问题。非常明显，这些解决方案并没有从根本上解决问题。首先是速度问题。通常的事实核查，为了让大家有个直观的感受，往往需要两到四天才能反馈结果，这在互联网时间里简直就像是无穷无尽。其次是规模问题。通常情况下，人们一天只能审查大约 10 个帖子或话题。即使你能解决这两个问题，信任才是最根本的核心问题。当时有太多人完全不希望也不信任科技公司来决定什么是准确的，什么是不准确的。因此，我当时交接了正在管理的团队，去尝试开发一些疯狂的新想法，其中之一最终就演变成了现在的社区笔记。

<details>
<summary>Original English</summary>

**Keith Coleman**: I mean, the origin, for me, goes back to 2016. I was just a Twitter user then. I was following the 2016 election. There were three televised debates that year, but every day, there was a debate on Twitter. So that’s where I was following. That’s where the world was following. I remember getting a lot of good information, but it was also hard to tell what was true. And I was thinking, just sitting on the outside, thinking like: How is the world going to solve this problem? How are we going to do this in a way that works, and that people feel is fair amidst polarization? So then fast-forward three years. I was working at Twitter at that point, and the industry had tried a lot of stuff by then. Facebook had built a huge fact-checking program. Twitter was working with fact-checkers. And we also had internal teams that would try to review posts and decide whether they were or [were] not misleading. And there were a bunch of issues with it. It was just very clear these solutions were not solving the problem. There were issues with speed. So typical fact checks, just to put it in perspective, were often coming back in two to four days, which is like, infinity in internet time. Scale was an issue. Typically, people could review, I don’t know, order of 10 posts or topics a day. And even if you could solve those, trust was the fundamental issue. There were just a lot of people who did not want, or trust, tech companies to be deciding what was or was not accurate. And so, I was managing a team at the time, handed that off and just went to go prototype crazy new ideas, one of which became Community Notes.

</details>

**唐凤**: 好的，所以这个疯狂的想法，简单复盘一下，就是自下而上的思考方式：让人们去信任互联网上的陌生人。在极化程度极高的环境中，就像你刚才提到的那样，为什么人们会去信任完全陌生的普通人呢？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, so the crazy idea, just to play back, is to think from the bottom up: asking people to trust random strangers on the internet. And amid a very high PPM -- polarization per minute -- environment, as you just alluded to, why would people trust random strangers?

</details>

**杰伊·巴克斯特**: 是的，这确实是一个非常好的问题，也是我们在刚开始时经常被问到的问题。但现实情况是，政治光谱两端的人们确实非常信任社区笔记。我认为这其中有几个非常关键的原因。首先是它背后的工作流程。它是完全开放、透明且可验证的。在社交媒体世界中，这其实是一件相当不可思议的事情——你实际上可以下载生产环境中运行的真实算法代码。你可以下载真实的社区笔记和评分数据，自己在本地运行代码以验证我们是否在后台进行干预。我们没有所谓的“超级覆盖按钮”，所以它完全是由用户说了算。其次，这些笔记本身的质量非常高。它们用事实说话，往往极其准确。而这背后的核心原因，我认为在于我们的算法原理。该算法不依赖任何外部权威，而是通过寻找那些**在过去曾持有不同意见的人所达成的一致性**来决定展示哪些笔记。有时候，我们称之为“出人意料的共识”或者“桥接”。

<details>
<summary>Original English</summary>

**Jay Baxter**: Yeah, it’s a really good question, and it’s one we got all the time getting started. But the reality is people do trust Community Notes on both sides of the political spectrum. And I think there’s a couple [of] big reasons why. One is the process behind it. It’s totally open, transparent, verifiable. You can actually -- and this is pretty wild in the world of social media -- you can actually download the real algorithm code that runs in production. You can download the real data, the Community Notes and ratings, [and] run the code on the data to verify that there is no funny business that we're doing on our end. There’s no override button. So it’s really by the people. I think secondly, the notes are just really good. So they speak for themselves, they tend to be really accurate. And the main reason behind that is, I think, the principle behind the algorithm that doesn't ingest any sort of external authority, it actually decides what notes to show by looking at agreement from people who have disagreed in the past. And sometimes we call that “surprising agreement” or “bridging.”

</details>

### 算法如何利用极化

**唐凤**: 听起来是时候进行可视化展示了。我们有左右两个阵营，人们发布笔记，然后会发生什么？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, it sounds like [it’s] time for a visualization. So we have two wings, and people post notes, and then what happens?

</details>

**杰伊·巴克斯特**: 好的。为了让大家直观地了解，我们现在看到的每一个圆点都代表一条社区笔记。Y 轴代表我们的算法认为该笔记“有帮助”的评分等级。X 轴代表该笔记所处的观点立场。你可以看到左边和右边分布着红色和蓝色的圆点。那些就是极化的笔记——它们只被某一侧立场的人认为有帮助。非常重要的一点是，这类笔记绝对不会在平台上向所有公众展示。实际上，唯一会向大家展示的笔记，是位于顶部绿色椭圆区域里的那些。这些笔记被那些在日常中通常意见不合的人共同认为是有帮助的。这里其实还引入了一个社区自律的机制。如果你写了太多位于底部的低质笔记，你甚至会失去撰写社区笔记的权限。这个算法非常酷的一点是，如果你将它与那种幼稚的赞同/反对投票系统（比如简单多数决定制）进行对比，后者最终只会展示极具偏见的笔记。而我们的算法实际上巧妙地**利用了党派偏见和两极分化**。对于任何关于极化话题的社区笔记，在网络上总会有人倾向于去反对它。因此，在他们对这条笔记打出“有帮助”之前，他们会从各个可能的角度进行事实核查，非常仔细地去检验其来源。因此，以这种方式最终脱颖而出、被认为是有帮助的笔记，往往极其准确，倾向于使用一手来源，并且在语言表述上保持中立。

<details>
<summary>Original English</summary>

**Jay Baxter**: Yeah, OK, so just to orient you: what we’re looking at here is every dot is a Community Note. The y-axis there is how helpful our algorithm thinks the note is. And the x-axis is the point of view of the note. So you can see on the left and the right the red and blue. Those are polarizing notes -- so only really found helpful by people on one side or the other. And it's super important that those don't actually show on the platform. Actually, the only notes that show to everyone are the ones in the green oval at the top. Those are the ones that are found helpful by people who typically disagree. There’s actually a bit of a community moderation element here too, where if you write too many of the notes on the bottom, you can actually lose your privilege for writing Community Notes. And one thing that’s really cool about this algorithm. If you compare it to something like a more naive upvote-downvote system, like a majority rules type of thing, something like that would just end up showing really biased notes. Our algorithm actually takes advantage of partisanship and polarization. So for any Community Note on a polarizing topic, there’s always going to be someone out there who's really predisposed to disagree with that note. So before they’re going to rate it helpful, they're going to go fact-check it from every angle possible. They're going to really check the sources in a lot of detail. And as a result, the notes that are actually found helpful in this way, tend to be really accurate, tend to use primary sources and tend to be pretty neutral in their language.

</details>

### 零否决权与去中心化

**唐凤**: 好的。所以两边的人在把两极分化转化为动力——本质上是地热能——之后，共同提升了某些内容，让双方都很满意。但那个被备注笔记的博主可能就没那么高兴了。假设有一位国家元首被标记了，而这位元首恰好有你们 CEO 的电话，于是直接打电话给埃隆说：“明天早上之前必须把这个撤掉。”他会怎么回答？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, so people on both sides, after turning polarization into essentially fuel, right, geothermal energy, [are] uplifting something and both sides are happy. But the person getting noted may not be very happy. So [let’s] say, a head of state gets noted, and the head of state happens to have the phone number of your CEO and just calls Elon and says, "Take it down by tomorrow morning." What would he say?

</details>

**基斯·科尔曼**: 确实会有这样的电子邮件、电话等找过来。幸运的是，我们的回答非常简单：我们这里根本没有覆盖或者撤回笔记的按钮。所以，如果你对笔记不满意，你需要去跟广大用户进行沟通。这在项目创立之初确实被认为是一个非常疯狂的想法。我们当时走进一个装满了信任与安全专家成员的会议室，跟他们说：“听着，最后能公开展示的笔记是由大众决定的，我们无权将其撤下。”

<details>
<summary>Original English</summary>

**Keith Coleman**: Yeah, so emails like that, calls or whatever, they do come in. Fortunately, the answer is really simple: we have no override button. So if you're not happy with a note, you need to take it up with the people. And this [was] kind of a crazy idea when we started. We went into a room full of trusted safety people and we’re like, “Hey, so the notes that show are going to be the ones that the people decide, and we can’t take it down.”

</details>

**唐凤**: 没有任何否决权。

<details>
<summary>Original English</summary>

**Audrey Tang**: There's no veto.

</details>

**基斯·科尔曼**: 没有任何否决权。他们当时听了非常震惊，问我们：“什么？你们是认真的吗？那要是出现了一条很糟糕的笔记该怎么办？”但我们认为，如果最终的评判代表的是科技公司的意见，那么怎么可能会有人信任它呢？它必须是来自公众大众的意见。因此，我们坚守了这一原则。所有团队最终都支持并遵循这一原则。我们现在没有任何办法手动更改一条笔记的状态。这真的非常棒。

<details>
<summary>Original English</summary>

**Keith Coleman**: There's no veto. And they’re like, “What? Are you serious? What if there's a bad note?" But I think the point was if it’s the tech company’s opinion, why is anyone going to trust it? It needs to be the people's opinion. And so we stuck to that principle. Everyone got behind it. And we have no way of changing the status of a note. Which is wonderful.

</details>

### 传播抑制与行为改变

**唐凤**: 确实太棒了。那么，在被附上社区笔记之后，帖子本身会发生什么变化？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, it is wonderful. And so what happens to the post after it gets noted?

</details>

**杰伊·巴克斯特**: 我们在左边看到的是一个极具代表性的普通帖子，这是一个真实的帖子。我们正在观察它在一段时间内的浏览量变化。Y 轴代表浏览量，X 轴代表帖子发布后的时间。你可以看到这个帖子在刚开始时传播得极快，呈爆发式增长，直到它被添加了笔记——就是那个绿点和黄色虚线标出的时间点。在那之后，它的浏览量增长几乎完全平息了。非常神奇的一点是，该帖子其实并没有被我们的推荐算法进行降权处理。这完全是由于我们所说的“**用户自发行为**”造成的——人们在看到笔记后意识到这个帖子是不准确的。因此，他们对它的点赞和转发自然就变少了。我认为这太酷了。而且，由于我们的数据是完全开源开放的，许多来自全球各地的学术研究人员在对此进行研究后，也得出了相同的结论。来自**斯坦福大学**、**麻省理工学院**、**华盛顿大学**、**巴黎大学**和**卢森堡大学**的学者们，都发现了非常相似的结果：在帖子被应用了笔记后，其转发量会下降大约 50%（即降低为原来的二分之一）。在社交媒体的运营规模下，这是一个非常巨大的变化。在典型的 A/B 测试中，哪怕能带来 1% 到 5% 的改变就已经算是很大的成果了。我认为其中非常鼓舞人心的一点是，我们通过这项以及其他研究发现，人们并不仅仅是一味地固执己见。当一条笔记应用到帖子上时，他们对该帖子核心主张的认同度确实会随之降低，我认为这非常棒。不过，这也有点像是一把双刃剑，因为帖子作者在帖子被标记笔记后，往往更有可能会选择直接删除自己的帖子。所以在这种情况下，那些最优秀的笔记反而不经常能被人们看到。对此我有些纠结。虽然大家在这个问题上的看法并不完全一致，但就我个人而言，我宁愿看到原帖加上笔记的组合，也不希望两者都消失，因为原帖中那个错误的论断很可能并不会在世界上彻底消失——你或许还会在 X 平台之外的其他地方看到它。对我来说，阅读很多社区笔记反而增加了我在阅读网上海量信息时的审视精神。

<details>
<summary>Original English</summary>

**Jay Baxter**: So what we’re looking at on the left is a typical, representative post. This is actually a real post. And we're looking at how many people have seen it over time. So the y-axis there is views and the x-axis is the time since post creation. And you can just see this thing’s going super viral at the start, all the way up, until it gets noted. So that's the green dot with the yellow dotted line there. Basically after that point it totally flattens out [and] gets almost no more views. And the kind of crazy thing about this is it's actually not getting down-ranked by our For You algorithm. This is actually just because of what we call “organic user behavior,” where basically people are realizing now that the post is incorrect because the note's on it. So they're just liking it less and reposting it less. I think this is really cool. And one thing that I also love is, because our data is totally open, a lot of researchers from around the world have looked into this and found the same thing. So people from Stanford, MIT, UW, Paris and Luxembourg have all actually found a very similar thing: reposts will drop by about 50 percent, or 2X, after a note is applied. This is really big in the scale of social media. One or five percent, one would be pretty big in the scale of typical A/B tests. One thing that I think is really heartening about this is that we know from this and other studies ... that people are not just entrenched in their beliefs. When a note is applied to a post, they’ll agree with the core claims in the post less, and I think that’s really cool. I guess there’s a little bit of a mixed blessing here though, because actually post authors will also be more likely to delete their posts after they get noted. So in that way, the best notes actually get seen very infrequently. So I'm torn about that, because just for me personally, I think not everyone agrees on this, but for me personally, I’d rather see a post and a note than neither at all, because that’s probably not the only time in the world where you’re ever going to see that particular wrong claim -- maybe you’ll see it off X somewhere in another post. And for me, seeing a lot of notes has kind of increased the skepticism that I have when reading things.

</details>

**基斯·科尔曼**: 是的，我认为关于这张图表还有一点需要提及，就是这些反应能够完全自发地发生，这本身就是一件非常了不起的事。人们经常假设这个世界是极端对立的，确实，它的感觉也确实非常对立。但是，这里的用户只是在看到帖子和修正信息后做出了自己的选择：“这些内容有错，那我不要去转发了。”而且这种现象正发生在政治光谱的各个阶层中。我们一再看到这种行为模式。我们在最开始设计这个产品时，对来自左右翼的数百人进行了深入访谈。非常明显的一点是，大多数人只是想要了解这个世界的真实运行情况。他们知道自己可能会接触到错误的内容，他们只是想要筛选并辨别出真相。这正是上述行为在现实中的体现。当给予他们真实的信息时，他们会倾向于做出明智的决定。人们有时会认为，在应对误导性信息的领域工作一定非常艰难，会经常感到悲伤或沮丧。但实际上，做这项工作让我感到非常乐观，因为我们看到了有很多共识存在，而且大众实际上是非常理性的。

<details>
<summary>Original English</summary>

**Keith Coleman**: Yeah, I think one other thing to mention about this graph is it's kind of a big deal that this happens organically. People often assume the world is very polarized -- certainly it feels very polarized. But [the] people here, they’re just making a choice where they see a post. They see a correction, and they’re like, “Things are wrong. I'm just not going to share it." And that's happening across the political spectrum. And we’ve seen that pattern again and again. When we first were designing the product, we did interviews with hundreds of people, left and right. And it was really obvious that most people just want to know what's going on in the world. They know they're consuming incorrect stuff. They just want to sift through it. And this is just showing that in action. When given information, they're going to try to make a good decision. I think people often assume, man, it must be tough to work in the space of misleading information. You must get sad all the time, whatever. Actually, I feel very optimistic working on it because we see there’s quite a lot of agreement, and people are actually quite reasonable.

</details>

### 防范协同操纵

**唐凤**: 哇，好的。所以极化指标（PPM）在走低。

<details>
<summary>Original English</summary>

**Audrey Tang**: Wow, OK. So the PPM is going lower.

</details>

**基斯·科尔曼**: 我希望如此，似乎它比大家感受到的要低一些。

<details>
<summary>Original English</summary>

**Keith Coleman**: I hope, it seems like it's lower than it might feel.

</details>

**唐凤**: 太好了。那现在让我提出一个更为尖锐和怀疑的观点。任何在互联网上待过五分钟的人可能都会想：“一定会有方法来操纵这个系统的，甚至有很多种方法。”举个例子，我曾合作撰写过一篇名为《恶意 AI 群体》（*Malicious AI Swarm*）的论文。其中谈到了一个人如何构建大约 5000 个智能体——机器的那种。它们中有些被编码为偏左立场，有些被编码为偏右。它们表现得和普通人完全一样，甚至也会为社区笔记做贡献。当遇到有争议的问题或选举时，它们就会在关键时刻制造出一种“出人意料的共识”，并对一些本来是真实的信息强行打上“错误笔记”的标签。你们将如何应对这种情况？

<details>
<summary>Original English</summary>

**Audrey Tang**: Amazing. So let me now push on a more cynical take. Anyone who [has] spent five minutes on the internet is probably thinking “Now there’s going to be a way to game this, maybe many ways to game this.” And just one example: I co-wrote a paper called "Malicious AI Swarm." It talks about one person forming like 5,000 agents -- the machine kind. And some are coded left, some coded right. They behave completely normally. They even contribute to Community Notes. And just when the controversial issue or election happens, then they manufacture a surprising agreement and just “note” something that is actually true. How do you deal with that?

</details>

**杰伊·巴克斯特**: 是的，对抗操纵确实是一个真实存在的问题。人们总是试图钻社交媒体算法的空子，社区笔记也不例外。我想指出的一点是，那种寻找“出人意料共识”的机制确实对你刚才描述的那种更为初级的攻击手段提供了一定的防御力。如果有大量持有相同观点的人蜂拥而上，试图强行展示一条错误的笔记，这是不会起作用的。但对于像你描述的那种更为复杂的协同攻击，我们确实部署了多重防御机制。举几个例子：我们要求绑定来自可信运营商的已验证电话号码，这能够大大提高我们正在面对的是真人的概率。我们会去寻找在过去打分行为极其相似的打分者，并且在处理时，我们可能会把他们视为同一个人，以此来限制高度协同的一致性行为所带来的影响。此外，我们会去提取打分者的随机样本，如果他们的评分行为与那些自我选择的、可能具有恶意企图的打分者有着明显的区别，这就是一个非常重要的判别信号。我们还有其他机制，比如“打分者声誉系统”来应对低质量的用户。但最核心的一点是，即使有了所有这些防线，社区笔记有时候也还是会出现错误。然而，因为这种情况非常罕见，我们反而获得了某种**自我纠错的属性**——那些错误的笔记会吸引大量的关注，并吸引大批打分者迅速给它们打出“无帮助”的分数，随即它们就会停止展示。我认为这种自我纠错的属性在突发新闻事件的场景下尤为重要。几个小时前还是真实的信息，在之后可能就发生了变化。所以，笔记不是一成不变的，这非常好。

<details>
<summary>Original English</summary>

**Jay Baxter**: Yeah, manipulation is a real thing. People are always trying to game social media algorithms, and Community Notes is no exception. So I think one thing to call out is that surprising agreement mechanism does provide a bit of a defense against a more naive attack than the one you describe. There's a lot of people with the same view, all piling on, trying to get an incorrect note showing -- that’s not going to work. But for a more sophisticated attack, like the one you describe, we do have a lot of defenses in place. So just to name a few, we do things like requiring a verified phone number from a trusted carrier, just to increase the probability that we're dealing with real humans. We look for raters who have rated things very similarly in the past. And actually, we might treat them as the same person just to limit the influence of really similar behavior. Another thing is we can look at random samples of raters, and if they're rating things very differently than self-selected, possibly malicious raters, then that's a very important signal. And we have other things too: there’s “rater reputation” to deal with low-quality people. But I think another key thing to call out is even with all these defenses, Community Notes are incorrect sometimes. Now because it is really rare, we actually get this self-correcting property where the incorrect notes attract a lot of attention, and they’ll draw a lot of raters to go quickly rate them not helpful, and then they'll stop showing. And I think that self-correcting property is super important also in a breaking-news situation, right? Something that was true a few hours ago, may not be anymore. So it's great that notes are not set in stone.

</details>

### 人机协同与反馈学习

**唐凤**: 好的。笔记出错这件事本身也会成为瞩目的焦点，然后人们会递归地去进行优化。确实，我在 X 平台上观察这种现象已经有一段时间了，因为我长期以来都是其中的贡献者。这感觉确实像魔法一样，简直就像是“维基百科（Wikipedia）”或者是“Grok百科”。当有大批人涌入处理某个争议话题时，效果会变得特别好。但要是换成另一种情况呢？一个刚刚快速发展的冷门非主流话题，并没有足够的初始关注度来冷启动并达成那种“出人意料的共识”。我也经常看到五个小时、十个小时过去了，还是没有达成任何共识。你们打算如何解决这个速度问题？因为正如你指出的，到了第二天，事情的时效性早就过了。

<details>
<summary>Original English</summary>

**Audrey Tang**: OK. Notes being wrong is noteworthy and people recursively improve. Indeed, I've seen it happening on X for quite a while because I was a long-time contributor. It just feels like magic. It's like Wikipedia or Grokipedia. When many people swarm into some controversy, it gets really nice. But what about the other situation: a niche topic just developing fast. There's just not enough attention to bootstrap the initial surprising agreement. I’ve also seen like five hours, 10 hours go by without any consensus at all. How are you going to tackle this speed problem? Because as you pointed out, next day, it's already gone.

</details>

**杰伊·巴克斯特**: 首先，在速度的基准对比上，正如基斯之前提到的，传统行业先进的事实核查服务往往需要花费数天时间，而社区笔记通常缩短到了几小时的级别，所以它其实已经快了非常多。对于一个全新的帖子，笔记最快在 20 分钟内就能展示出来。而如果网络上已经存在针对相同 URL、图片或视频的既有笔记，那么该笔记甚至能瞬间进行匹配并展示。除此之外，人们非常喜欢的一点是，如果有人在某条社区笔记正式生成之前就已经浏览并互动了相关的原贴，我们会在笔记生成后向其发送一条推送通知，让他们能第一时间获得修正信息。尽管如此，我认为持续提升社区笔记的响应速度对我们而言依旧至关重要。人们渴望即时的背景信息，这完全是合理的。为此，我们在去年开放了一个**面向 AI 贡献者的开放 API**。在社区笔记完全开放的精神下，这其实是一件有些疯狂的事：就像普通人可以撰写笔记一样，我们允许普通人去开发他们自己的 AI 笔记撰写工具，并将笔记提交到我们的系统中。到目前为止，我们观察到这种模式运行得非常理想。AI 生成的笔记速度极快，而且质量也相当不错。不过，这毕竟是 AI，它们肯定也会有犯错的时候。因此，我们目前采用且运作良好的一种处理方式是，我们依然保留了人类的审核层——让普通人以评判人类撰写笔记的相同方式，来对这些 AI 提交的笔记进行打分。而我们现在努力推进的方向是建立一种机制，让人类和 AI 能够更加高效地进行协作，共同以更快的速度写出更优质的笔记。

<details>
<summary>Original English</summary>

**Jay Baxter**: Well first, just to level set on speed, I think Keith already mentioned the previous state-of-the-art fact-checking would often take on the order of days, and Community Notes is usually more in the order of hours, so it is already quite a bit faster. Notes can appear as often as in about 20 minutes on a brand-new post. But they can actually appear instantly if there's already another note out there that’s matching on a URL or image or video. I think on top of that, one thing that people really like is if someone actually sees a post and engages with it before a Community Note is appearing, we'll actually send them a push notification later so they get the correction as soon as the note comes out. Now, even with all that, I think it’s super important for us to keep making Community Notes faster. People want instant context -- and rightfully so. To that end, what we've done last year is we actually opened up, an open API for AI contributors. And this is a little bit of a crazy thing in the totally open spirit of Community Notes, just like a regular person can be writing notes, we let regular people write their own AI-note writers and submit notes to our system. And what we've seen so far is it's actually working really well. The notes are really fast and they’re quite good. But you know, definitely because it's AI, they're wrong some of the time. So the way [we] treat this now that’s been working well is we still have a human layer where humans rate the notes in the same way as any other human-authored note. And what we're working towards now is a way for AI and humans to collaborate more effectively, to co-write better notes faster.

</details>

**唐凤**: 所以人类并不仅仅是在投赞成或反对票，而是在与 AI 模型进行深度协同。

<details>
<summary>Original English</summary>

**Audrey Tang**: So humans are not just downvoting or upvoting but working with AI models.

</details>

**基斯·科尔曼**: 是的。核心想法是：我们能否让普通人和 AI 共同撰写、共同创造这些内容？这是否能让我们以更快的速度和更大的规模来做到这一点？你在屏幕上看到的正是这种协作形式的具体呈现，这非常新颖。如果一个帖子产生了对背景信息的需求，也就是人们正在请求对该帖子添加笔记时，AI 会先进行首次尝试。当然，人类也可以撰写，但 AI 会先行试水。在屏幕显示的这个真实案例中，AI 最初认为这段视频拍摄于 2017 年——但事实证明并不是。因此，人类用户进入系统并指出：“嘿，事实上这段视频是 2022 年拍摄于乌克兰的。”然后，一大批人对此进行评估并留下了具体的改进建议。他们还可以针对文体风格或语气留下建议，比如指出“我认为这个来源存在偏见”或者“我认为你应该使用第一手资料，这样会更具公信力”。接着，AI 吸收了这些改进意见，重新生成了笔记，而这次通常就能够写正确。这非常酷的地方在于，首先，在人们非常关心的帖子上，我们直接获得了一条更为优质的笔记。其次，所有人类做出的纠正和意见，都会转化为非常有价值的**训练数据**，并反馈给 AI。这样你就可以训练它以后不再犯类似的错误。你可以让它从一开始就更擅长进行事实调研。你也可以让它的立场更中立、偏见更少。因此，所有的这些人性化建议不仅带来了更好的笔记，也塑造了更好的 AI。

<details>
<summary>Original English</summary>

**Keith Coleman**: Yeah. The idea is can we have humans and AI co-write these things together, co-create them together? And does that allow us to do this at a much faster speed and larger scale? What you’re seeing on the screen here is an example of what that looks like. This is new. If there’s demand for a note, like people are requesting a note on a post, AI will take a first shot at it. Humans can write too, but AI will take a shot. And in this case, this is based on a real example, the AI thought this video was from 2017 -- and it turns out it wasn't. So humans go in there and they’re like, “Hey, actually, this is from 2022 in Ukraine.” And a bunch of people rate it and they make these suggested improvements. They can also leave suggestions on style or tone. So they can say, “Hey, I think this source is biased” or "I think you should use a primary source. It's going to be more trustworthy." And then the AI takes that, regenerates a note and usually gets it right. And what's cool about this is first, you get a better note on this post people care about. But two, all of those corrections, all those suggestions are training data that you can feed back into the AI. So you can make it less likely to make that mistake again. You can make it better at researching in the first place. And also you can make it more neutral, less biased. So all these human suggestions make better notes, and they make better AI.

</details>

**唐凤**: 好的。所以简单来说，这并不是让 **Grok** 来主导并包揽所有的人类决策。它本质上是由人类来传授 AI——也就是协同学习。这样一来，像一侧的“气候正义社区”与另一侧的“圣经创世守护社区”这两种不同的圈子之间的概念转化，AI 模型就能学会如何在这两者之间进行翻译。在这之后呢？它们是否会变得更加擅长这种社会文化层面的翻译工作？这是否是一种为 AI 模型提供奖励的全新方式？它是如何运行的？

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, so just to play it back, this is not Grok helping humans to such a degree that it takes over all the judgment calls. It is basically human teaching AI -- collaborative learning -- so that the translation between communities like climate justice on one side [and] biblical creation care on the other, the AI model learns how to translate -- and then what? They become better at this kind of translation? Is this a new way to reward AI models? How does it work?

</details>

**杰伊·巴克斯特**: 我们有时候将这种模式称为“**基于社区反馈的强化学习（RLCF）**”，以区别于那种可能只使用了少数非典型代表性人群、极易引入偏差的传统“基于人类反馈的强化学习（RLHF）”。在社区笔记的场景中，它的运行模式表现为直接训练模型去撰写笔记，让生成的笔记有最大概率能够被一个经过模拟的、在过去通常持有不同意见的跨立场评估群体判定为“有帮助”。

<details>
<summary>Original English</summary>

**Jay Baxter**: There's this thing that we sometimes call reinforcement learning from community feedback, as opposed to just reinforcement learning from human feedback, which maybe would use potentially a smaller bias set of non-representative people. And in the case of Community Notes, what it would look like is directly training the model to be writing notes that would be maximally likely to be found helpful by a simulated set of raters who typically disagreed in the past.

</details>

### 应对深度伪造

**唐凤**: 好的，这确实非常棒。

<details>
<summary>Original English</summary>

**Audrey Tang**: OK, well, that's really nice.

</details>

**基斯·科尔曼**: 是的，这很酷。

<details>
<summary>Original English</summary>

**Keith Coleman**: Yeah, it's cool.

</details>

**唐凤**: 即使如此，未来某一天我打开 X 平台，依然可能会看到满眼充斥着极其低劣的垃圾内容（Peak Slop）。现在生成合成媒体、甚至是虚假的情感互动，其边际成本下降得如此之快。有时候我确实会觉得，无论我们发明了怎样的纠错机制，都无法以足够快的速度来应对这种垃圾内容泛滥的危机。那么，现场的各位为什么应该相信社区笔记和这种协同式笔记模式，能够不断进化并满足未来的需求呢？

<details>
<summary>Original English</summary>

**Audrey Tang**: So still, someday I just open X, and I just see peak slop. The marginal cost for generating synthetic media, even synthetic intimacy, is now falling so fast. Sometimes I feel that whatever corrective mechanism we invent, [it] is not going to be fast enough for this kind of peak slop situation. So why should anyone here believe that Community Notes and collaborative notes will evolve to meet the demand?

</details>

**基斯·科尔曼**: 在过去的六周左右时间里，伴随着伊朗冲突，我们确实见证了我在这个误导性信息防护领域中所见过的最大规模的合成媒体浪潮。但我必须说，我们目前正处于这一领域的最前沿。这是目前已经投入运行的、规模最大且速度最快的解决方案。这全都是非常新颖的问题，所以我们不知道什么方法一定会彻底奏效。我们无法保证问题会被百分之百解决，但我认为有很多理由让我们保持乐观。对于像合成媒体泛滥这样的挑战，我们既可以不断扩大事实修正的覆盖规模，也可以从根本上改变这个系统的底层激励机制和运作逻辑。在扩大修正规模方面，我们刚才讨论了 AI 的应用。用数据来说话，在过去的四个月里，我们在 X 平台上公开展示的社区笔记数量就整整翻了一倍。对于一项已经规模化的服务来说，四个月内实现 2 倍的增长并不是一件微不足道的事。我认为这其中显然还有巨大的增长空间，未来是 10 倍还是 100 倍？总之，它拥有着非常明显的成长天花板。而在另一端的激励机制方面，人们之所以去发布这些虚假和垃圾内容，主要原因之一是他们可以通过各种创作者流量分成计划从中获利。因此，我们最近针对该政策做出了非常关键的调整：如果你的帖子被标记了社区笔记，你将无法通过该帖子获得任何广告收益分成。另外，如果你发布了关于战争或冲突的 AI 生成合成素材却未明确标注说明，你将被直接暂停三个月的创作者广告分成资格。如果再犯，你将被永久剥夺分成资格。这是一项非常有分量的惩罚性改变，它将从根本上重塑人们底层的发帖动机。（掌声）

<details>
<summary>Original English</summary>

**Keith Coleman**: So definitely in the last six weeks or so, with the Iran conflict, we've seen the biggest surge in synthetic media that I've seen, at least in the kind of misleading info space. And I will say like, we're on the frontier here. So this is the highest-scale, highest-speed solution that exists. These are new problems, so we don’t know what’s going to work. We can’t guarantee the problem will be solved, but I think there’s a bunch of reasons to be optimistic. For that problem, like [the] synthetic media surge, we can both scale up the corrections, and we can both change the fundamental incentives and dynamics of the system. So in terms of scaling corrections, we talked about AI. Just to put some numbers on that, in the last four months alone, we've doubled the number of notes that are showing on X. So that’s not trivial for a scaled service -- 2X in four months -- I think there's clearly headroom on that. Is it 10X, 100X? But there's clearly headroom to grow. The other thing on the incentive side, one of the reasons people post these things is they can make money off of it through creative revenue-sharing programs. And so we've recently put into place some changes to the policies there where, if your post is noted, you can't make money off it. Also, if you post AI-generated footage of a war or conflict and you do not clearly call it out, you are suspended from the revenue-sharing program for three months. If you do it again, you're suspended forever. That’s kind of a big deal. Those will shape the underlying motivations people have. (Applause)

</details>

### 寻找共识的未来

**唐凤**: 我们的策展人克里斯在我们之前交流时，提出了一个我认为非常具有洞察力的问题。我们刚才一直在讨论防御性的话题，比如防范各种操纵、通过激化情绪来获取流量等问题。但社交媒体在未来是否可以实现另外一种可能：不仅仅是在挑唆人们相互对抗，而是真正将大众彼此联结，放大社会中达成共识与“桥接”的声音？而你们当时回答说：我们正好有这样一个演示项目。

<details>
<summary>Original English</summary>

**Audrey Tang**: Chris, our curator, when we talked earlier, asked this, I think, very insightful question because we've been talking about defense, right? Defending against all those manipulations and engagement through enragement and so on. But is there a future in which social media, instead of pitting humans against one another, puts people and connects them with each other, elevating the voice, that bridge? And you’re like: we have just the demo.

</details>

**基斯·科尔曼**: 是的，我们正在着手构建这个项目。这是一个极具想象力的未来。我们目前正在运行一个试点计划，你在屏幕上看到的正是该项目的具体样貌。在社区笔记的实践中，我们能找出那些能够被不同背景、不同立场的人共同判定为“有帮助”的纠错性信息。那如果我们能够顺着这个逻辑，去找出那些被具有不同观点立场的人所**共同赞同和喜爱的观点或意见**呢？在试点程序中，一旦发生这种情况，就会呈现你在屏幕上看到的界面：该帖子将直接获得一个特有的标签标注，显示为“被具有不同视角的群体共同点赞”。例如，我们在这个案例中发现：大家非常高兴看到达美航空在 TSA（美国运输安全管理局）获得全额资金支持之前，不允许国会议员跳过正常的排队安检程序。

（掌声）

是的，你们与成千上万持有相同看法的人站在一起。而且我们在大量的议题中都看到了这种跨越立场的普遍共识，甚至是在很多你们平时认为极具争议性的话题上。在移民问题、经济体制、税收政策、国际冲突等方面，都广泛存在着这类共识。世界上确实存在着大量的一致性，哪怕无法在所有事情上达成一致，但也已经非常可观了。这一试点的核心概念在于，如果我们可以识别出这些共识，我们甚至不需要在刚开始时通过算法去刻意推广它——仅仅是让大家看到这种共识存在的事实本身，就已经足够了。首先，我认为大家会觉得这很有意思，能满足好奇心。其次，这或许能起到正向激励的作用。也许这会促使人们在网络上表达意见时，开始更多地以一种更易于寻找共识的方式去进行表述，并进一步推动这些共识性观点获得更多的关注和共鸣。

<details>
<summary>Original English</summary>

**Keith Coleman**: Yes, we are building this. This is an awesome future. So we have a pilot running, what you're seeing on the screen is what this looks like. The idea in Community Notes, we find, [is] kind of like corrections or context that's helpful to people from different points of view. What if we could find the ideas or opinions that are liked by people from different points of view? And then when it happens in the pilot program, you see what you're seeing on the screen here. The post will just get a call out saying "liked by people from different perspectives." And we see this: people were very happy to see Delta not allow Congress to skip the TSA line until TSA was funded. (Applause) Yeah, you're among millions of people who also feel this way. And we see this agreement across a lot of topics, [even] things that you think of as controversial. We see it across immigration, across the economy, taxes, international conflicts, etc. There really is a lot of agreement out there, not on everything, but there's quite a bit of it. And the concept is if we can identify that, [then] we don’t need to boost this to start -- just to show people when there's agreement on something. First of all, I think they'll find it interesting, it's a curiosity. Second, it might incentivize more of that. Like maybe people will try to speak more in a way where they can find that agreement. And get more momentum behind those ideas.

</details>

**杰伊·巴克斯特**: 这是一个非常好的观点。正如社区笔记能够让不实帖子的传播范围变窄一样——即便该算法没有在推荐机制中实施人工降权，你在这里可能也会看到极其类似的正向二阶效应。让这些群体间的共同立场成为大众的共同常识，将会带来深远而积极的改变。

<details>
<summary>Original English</summary>

**Jay Baxter**: That's a really good point. I think in the same way that Community Notes ... cause posts to spread less -- even though there’s no downranking in the algorithm -- you’ll probably see something analogous here where there's just a positive second-order effect from making that common ground common knowledge.

</details>

**唐凤**: 所以它是一个**共同常识引擎**，能将社会中的极化冲突转化为大家都可以和谐共处的力量。这确实具有非凡的远见。而关键在于，因为这一套系统和数据是完全开源和公开的，这意味着不仅在 X 平台上，像 **Bluesky** 或者是 **Truth Social** 等其他的任何社交平台，都可以无缝接入这套数据流。这样 AI 就能从中进行学习，并将不同的社区重新彼此联结起来。那么，如果我们将这个引擎应用到社交媒体之外的现实社会中呢？你能为我们勾勒一幅它在现实中应用的愿景吗？

<details>
<summary>Original English</summary>

**Audrey Tang**: So it's a common knowledge engine that turns polarization into what we can all live with. This is truly visionary. And the thing about it, because this thing is open-source, it is open data, means that not just X but rather Bluesky, Truth Social, everybody, can just plug in that stream. And so AI can learn from that and then connect the communities back together. So what if we apply this engine beyond social media? Can you paint a picture of what that would look like?

</details>

**基斯·科尔曼**: 我的思绪经常会飘向这样一个场景：试想一下，如果有一届国会，里面的每一个人都仅仅专注于去落实那些社会大众早已达成普遍共识的具体事务上，不论是在移民、税收还是其他什么领域，我认为人们都会为之欢呼。

（掌声）

是的，我们在这些议题上其实有非常多的共识。如果我们所做的所有事情就是去推进这些已经达成共识的领域，我认为人们会对这个世界未来发展的走向感到非常满意。因此我的希望是，通过类似的系统和项目，如果能够以互联网的尺度识别出社会的共同立场，它将让为人类创造一个令人期待的未来变得容易得多。希望我们能在这方面提供帮助。谢谢大家。

（掌声）

<details>
<summary>Original English</summary>

**Keith Coleman**: So where my head always goes is imagine for one session of Congress, everyone just focused on delivering where there was agreement, whether it’s immigration, taxes, whatever, I think people would be stoked. (Applause) Yes. I would be stoked. There's a lot of agreement on these topics. If all we did was pursue the areas of agreement, I think people would be pretty happy with the direction the world was going. And so my hope is, with programs like this, if we can identify common ground at internet scale, it'll make it a lot easier to create a future that humanity likes. And so hopefully we can help with that. Thank you. (Applause)

</details>

**唐凤**: 在此，杰伊、基斯，感谢你们成为最杰出的建设者，并向我们证明了一个更为健康的社交媒体未来并非遥不可及的科幻小说，它已经来到我们身边。谢谢。

<details>
<summary>Original English</summary>

**Audrey Tang**: And with that, Jay, Keith, thank you for being our best builders and showing us that a pro-social media future is not in some sci-fi. It's already here. Thank you.

</details>

**杰伊·巴克斯特**: 谢谢你，唐凤。

（欢呼声与掌声）

<details>
<summary>Original English</summary>

**Jay Baxter**: Thank you, Audrey. (Cheers and applause)

</details>

### 策展人的反思与展望

**唐凤**: 我是唐凤，我与非常优秀的迪维亚·西达斯一同担任了本届 **TED 2026** 的客座策展人。

<details>
<summary>Original English</summary>

**Audrey Tang**: I’m Audrey Tang, and I’m a guest curator along with the fantastic Divya Siddarth at TED 2026.

</details>

**迪维亚·西达斯**: 作为客座策展人，我们得以邀请那些做着杰出工作的实践者登上 TED 的舞台，帮助他们找到与世界分享这些卓越成果的途径。同时，我们也试图在我们认为最顶尖的时代智慧与我们最关心的问题——如 AI、民主等宏大命题——以及 TED 现场观众乃至更广阔的世界之间，建立起深刻的对话。

<details>
<summary>Original English</summary>

**Divya Siddarth**: As guest curators, we get to bring people who are doing incredible work onto the TED stage, help them find ways to share that work with the world and be able to create a dialogue between what we think are some of the best ideas out there and solving the problems we care about the most: AI, democracy -- these big questions -- and the TED audience and really the wider world.

</details>

**唐凤**: 我们之所以选择访谈这种互动形式来引介基斯和杰伊，是因为我们深感传统的 18 分钟个人演讲形式，固然精妙，却无法充分展现他们工作的全貌和精髓。因为他们的任务是训练 AI 去理解不同圈子之间的差异（比如气候正义社区与圣经创世守护社区），以及这种社会文化翻译在促进民主中所能发挥的多重作用。因此，我刚才在他们的每一个回答中都试图给他们施加极其严苛的追问，而他们的应对表现得堪称典范。

<details>
<summary>Original English</summary>

**Audrey Tang**: And we chose the interview format to bring Keith and Jay in because we really feel that the 18-minute talk format, as good as it is, is not doing full justice to their job, which is training an AI to understand the differences between, say, climate justice communities and the biblical creation care communities and the various different aspects that this social translation can do to our democracy. So I tried to push them really hard in every answer they gave, and they took it like champions.

</details>

**迪维亚·西达斯**: 我觉得这次访谈最棒的地方之一在于，虽然谈话的很大一部分都在围绕着社区笔记这一本质上是偏向于防御性的模式展开——即我们明知这个世界上充斥着不实信息，并努力去阻止这些坏内容的野蛮蔓延。但我个人特别钟爱访谈的结尾：如果我们将这一逻辑反转过来，会是什么样的图景？我以前其实并未对这个反向的维度进行过太深的思索。但正如我们可以识别出人们能够达成共识的纠错内容一样，我们同样可以识别出人们所赞同的正面信息和建设性的解决方案，并让这些成为大众在线上关注的焦点，而不是整天被那些极力分裂大家的负面垃圾信息所裹挟。

<details>
<summary>Original English</summary>

**Divya Siddarth**: I think one of the great things about this talk is [that] a lot of it is about Community Notes, which is a fundamentally defensive approach, right? We understand that the world is full of lots of bad information, we try to prevent the bad stuff from spreading. But I love the ending, which is on what would it look like if we flipped this? And I hadn't thought about that as much before, where if we flipped this to say, “As much as we know the kinds of corrections people agree on, we could also figure out the kinds of information and positive solutions people agree on and make that actually be the thing that people are focused on online instead of all the other stuff that they tend to focus on online.”

</details>

**唐凤**: 访谈的结尾谈到，数据正如肥沃的土壤。只有在这个土壤上让不同的社区加深彼此的理解，我们才能像照料花园一样，共同培育并守护这些茁壮成长的 AI 智能体。它们伴随着我们的社区共同成长，忠诚于社区本身，不带任何剥削和压榨，而是专注于重新滋养和唤醒我们之间那份深藏的共识与温情。

<details>
<summary>Original English</summary>

**Audrey Tang**: The ending talks about [how] data is soil, so that the understanding between different communities tend together this garden of AI agents that grow with our communities, loyal to communities and not trying to extract anything, but just to regenerate our deep understanding.

</details>