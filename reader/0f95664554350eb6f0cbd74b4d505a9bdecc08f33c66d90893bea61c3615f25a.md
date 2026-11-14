---
author: Veritasium
date: '2026-06-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8HBDE-msUjw
speaker: Veritasium
tags:
  - number-theory
  - prime-numbers
  - twin-prime-conjecture
  - mathematics
title: 孪生素数猜想与张益唐的突破：探寻无限靠近的素数距离
summary: 本期访谈深入探讨了数学史上最古老的未解难题之一——孪生素数猜想。视频回顾了从维戈·布伦的筛法改良，到GPY团队遭遇的瓶颈，最后详细讲述了默默无闻的华人数学家张益唐如何在逆境中实现突破，首次证明素数间存在有界距离。随后，詹姆斯·梅纳德与陶哲轩领导的Polymath项目更是将这一间距极限大幅缩小，展示了数学界攻克“不可能”难题的非凡历程。
insight: ''
draft: true
series: ''
category: science
area: knowledge-meta
project: []
people:
  - 张益唐
  - James Maynard
  - Terence Tao
  - Viggo Brun
  - Chen Jingrun
companies_orgs:
  - Annals of Mathematics
  - Polymath
  - American Institute of Mathematics
  - Brilliant
products_models: []
media_books: []
status: evergreen
---
### 2013年一封神秘的邮件

**[Derek]**: 2013年4月17日的早晨，《**数学年刊**》（**Annals of Mathematics**）收到了一封奇怪的电子邮件。这封邮件声称包含了一份长达50页的证明，涉及数学界最古老的未解难题之一。连伟大的数学家埃德蒙·兰道（Edmund Landau）都称这个问题是“不可攻克的”。但这份证明并非出自著名教授之手，而是来自一个无名之辈。（欢快的音乐）一个曾经在赛百味（Subway）餐厅工作了多年的人。

<details>
<summary>Original English</summary>

**[Derek]**: On the morning of the 17th of April, 2013, the journal Annals of Mathematics received a curious email. It claimed to contain a 50 page proof relating to one of the oldest unsolved problems in mathematics. A problem that great mathematician Edmund Landau called unattackable. But this proof didn't come from a famous professor, it came from an unknown. (bright music) Someone who had once spent years working at a subway restaurant.
</details>

**[嘉宾]**: 所以，他们当时的想法是，好吧，这肯定是不可能成立的，但管他呢。你知道的，我们会把它发给一位审稿人看看。

<details>
<summary>Original English</summary>

**[Speaker]**: So, they're like, okay, surely this isn't gonna work out, but whatever. You know, we'll send it to a referee.
</details>

**[Derek]**: 他们本以为只需一个下午就能找出其中的错误，但他们并没有发现。于是，他们又重新审视了一遍，仔细研究了这类证明通常会崩溃的脆弱环节，但依然没有发现任何问题。很快他们意识到，他们正在见证一项重大突破。

<details>
<summary>Original English</summary>

**[Derek]**: They expected to find a mistake in an afternoon, but they didn't. So, they went through it again, closely studying the fragile parts where a proof like this normally falls apart, but still nothing. Soon they realized they were witnessing a breakthrough.
</details>

**[嘉宾]**: 噢，天哪，他做到了。

<details>
<summary>Original English</summary>

**[Speaker]**: Oh, damn, he did it.
</details>

### 什么是孪生素数猜想？

**[Derek]**: 那么，他究竟是如何做到的？专家们错过了什么？他正在研究的又是什么问题呢？他当时正在研究一种攻击数论中最难的未解问题之一的新方法——**孪生素数猜想**（**twin prime conjecture**）。孪生素数是指两个相差仅为2的素数（因为素数除了2都是奇数，所以它们之间刚好隔了一个数字，比如11和13，或者17和19）。随着你在数轴上不断向上，素数变得越来越稀少，而孪生素数则变得更加罕见。但**孪生素数猜想**声称，这样的素数对有无穷多个，你永远不会穷尽它们。但这究竟是真的吗？

<details>
<summary>Original English</summary>

**[Derek]**: So, how did he do It? What did the experts miss and what was the problem he was working on? He was working on a new way to attack one of the hardest unsolved problems in number theory, the twin prime conjecture. The twin primes are prime numbers separated by just one number, like 11 and 13 or 17 and 19. As you go up, the number line, primes become rarer and twin primes become rarer still. But the twin prime conjecture claims that there are infinitely many of them you never run out. But is it true?
</details>

**[Derek]**: 解决这个问题的一种方法是，在数轴上不断向上的过程中，观察连续素数之间的差距。（欢快的音乐）起初这些差距似乎是混沌无序的，但如果你将它们取平均值，一个清晰的趋势就会显现出来。两个素数之间的平均差距增长的大致规律，约等于数字N的自然对数。举个例子，在100附近的素数，其平均间距大约是4.6。而在1000附近的素数，平均间距则是6.9。对数增长得非常缓慢，但它们确实会永远持续增长。所以，当N趋向于无穷大时，素数之间的平均差距也会趋向于无穷大，如果你指望总是能找到仅仅相差两步的素数，这听起来可不太令人鼓舞。

<details>
<summary>Original English</summary>

**[Derek]**: Well, one way to approach this problem is to look at the gaps between consecutive primes as you go up the number line. (bright music) Now, at first they seem chaotic, but if you average them out, a clear trend emerges. The average gap between two primes grows roughly as the natural logarithm of the number N. So, for example, the average gap between primes around 100, is approximately 4.6. The average gap between primes around 1000 is 6.9. Logarithms grow very slowly, but they do keep growing forever. So, as N approaches infinity, the average gap between primes also goes to infinity, which is not particularly encouraging if you expect to always be able to find primes that are just two apart.
</details>

**[Derek]**: 但是如果你开始检查很大的数字，比如在一百万之后，你很快就能找到一对孪生素数：1,000,037和1,000,039。超过十亿之后，有1,000,000,007和1,000,000,009。事实上，我们甚至发现过这样巨大的孪生素数：2,996,863,034,895 乘以 2的1,290,000次方，然后再加减一。那是一对各自长达388,342位的数字！如果出于某种原因你想要把它们印在一本书里，每个数字大约需要占据260页纸。所有这些都说明，只要我们继续寻找，我们一直在发现孪生素数。但当然，你不能通过这种方式来证明孪生素数猜想，因为你无法从物理上将所有数字一直检查到无穷大。

<details>
<summary>Original English</summary>

**[Derek]**: But if you start checking large numbers, then after a million you quickly find the twin primes, 1,000,037 and 1,000,039. Past a billion, there's 1,000,000,007 and 1,000,000,009. In fact, we have found a twin prime that's as large as 2,996,863,034,895 times two to the power of 1,290,000 plus or minus one. That is a pair of numbers each 388,342 digits long. If you wanted to print those in a book for some reason, you would need around 260 pages per number. All of this is to say that as far as we've looked, we've kept finding twin primes. But of course, that is not how you solve the twin prime conjecture, because you cannot physically check all the numbers out to infinity.
</details>

### 用估算法逼近极限

**[Derek]**: 所以，我们需要另一种方法。大约100年前，数学家们似乎觉得利用一种更为复杂的方法，他们正在接近真相。1923年，英国数学家哈代（Hardy）和李特尔伍德（Littlewood）弄清楚了如何估算应该存在多少对孪生素数。为了做到这一点，他们从数论最引以为傲的成就之一——**素数定理**（**prime number theorem**）开始。该定理告诉你，对于一个附近为N的大数，它是素数的概率大约等于N的自然对数分之一。

<details>
<summary>Original English</summary>

**[Derek]**: So, we need another way. And around 100 years ago, it felt like mathematicians were getting close with a more sophisticated method. In 1923, English mathematicians, Hardy and Littlewood figured out how you can estimate how many twin primes there should be. To do it, they started with one of the crowning achievements of number theory, the prime number theorem, which tells you that the odds of a large number near N being prime are roughly one over the natural logarithm of N.
</details>

**[Derek]**: 让我们做一个简单的例子来看看他们是如何运用这一点的。假设你想算出137,037是素数的概率。好吧，你只需要把它代入公式，就能发现它成为素数的几率大约是8.5%。当然，你也可以用同样的技巧来计算137,039是素数的几率，同样大概也是8.5%。那么，这两个数字同时都是素数的概率是多少呢？你只需要把这两个概率相乘，大约会得到0.7%的几率。

<details>
<summary>Original English</summary>

**[Derek]**: So, let's do a quick example to see how they use this. Say you wanna find the odds that 137,037 is prime. Well, you just plug that in and find that it has about an eight and a half percent chance of being prime. Of course, you could use the same trick to find the odds that 137,039 is prime, which is also around 8.5%. So, what are the odds that both of them are prime? Well, you just multiply those odds together, that gives you around a 0.7% chance.
</details>

**[Derek]**: 我们在这里稍作了简化，因为我们假设素数是相互独立的，而实际上并非如此。但先把这一点放在一旁，对于一个大数N和N+2，它们同时是素数的概率，就是 1/ln(N) 乘以 1/ln(N+2)。对于很大的N来说，这个加2是微不足道的。所以，我们得出结论：对于大小为N的任何一对数字，它们成为孪生素数的概率大致是 1/ln(N) 的平方。但这套方法存在的问题在于，随着你走向更大的数字，一对数字成为孪生素数的几率是在不断下降的。因此，为了计算出N以内所有的孪生素数，我们需要把每个位置上的几率相加。换句话说，我们要把这个表达式，从第一个素数2开始，一直积分到那个数字。

<details>
<summary>Original English</summary>

**[Derek]**: Now we are simplifying a little here because we're assuming that primes are independent, which they're not. But putting that to one side, the odds of both a large number N and N plus two being prime, is one over ln(n) times one over ln(n) plus two, for large N the plus two is insignificant. So, we get the odds of any pair of numbers of size N being a twin prime are roughly one over ln(n) squared. But of course, the problem with this approach is that the odds of a pair being a twin prime decrease as you go to larger numbers. So, to count all twin primes up to N, we add up the odds at every single position. In other words, we integrate this expression from the first prime two up to that number.
</details>

**[Derek]**: 现在，哈代和李特尔伍德进一步完善了这个论证，以解决素数其实并不是完全独立的事实。但这所增加的，仅仅是在最前面加上一个修正系数。所以最终的表达式看起来像这样。（欢快的音乐）现在，让我们来画出它所预测的、直到一万亿的孪生素数的数量。我们可以看到它一直在增长，如果我们填入实际的数量，你会发现它极其接近，到了1万亿的时候，我们的估算只差了0.001%。

<details>
<summary>Original English</summary>

**[Derek]**: Now Hardy and Littlewood refine this argument further to account for the fact that primes aren't really independent. But all that added is just this correction factor upfront. So, the final expression looks like this. (bright music) Now let's plot how many twin primes, this predicts up to 1 trillion. We see that it keeps growing and if we fill in the actual count, you'll notice that it is extremely close to the point where by 1 trillion, our estimate is only off by 0.001%.
</details>

**[嘉宾]**: 唯一的问题是，这只不过是一个估算，或者说是数学家们所称的**启发式方法**（**heuristic**）。它可以大致告诉你期望能有多少对孪生素数，但它无法保证它们永远不会停止出现。正如陶哲轩（Terry Tao）所说，据我们所知，可能存在着某种庞大的阴谋，即每当一个数字N决定要成为素数时，它都和它的邻居N+2达成某种秘密协议，说“你不再被允许成为素数了”。所以我们需要的是一个严格的、无懈可击的数学证明。但事实证明，要找到这样一个证明极其困难。

<details>
<summary>Original English</summary>

**[Speaker]**: The only issue though, is that this is just an estimate or what mathematicians call a heuristic. It can tell you roughly how many twin primes to expect, but it can't guarantee that they never stop. As Terry Tao puts it, for all we know, there could be this fast conspiracy that every time a number N decides to be prime, it has some secret agreement with its neighbor N plus two saying you're not allowed to be prime anymore. So, what we need is a rigorous airtight mathematical proof, but finding such a proof it turns out, is extremely difficult.
</details>

### 布伦筛法与误差累积

**[Derek]**: 最早真正尝试这一点的数学家之一是一位29岁的挪威人，维戈·布伦（**Viggo Brun**）。布伦是在第一次世界大战初期的几年里进行研究的，当时由于交通被切断，欧洲的数学中心大多无法涉足，他的大部分工作都是在挪威宁静而与世隔绝的环境下完成的。他的目标很简单：试图证明孪生素数的数量（或者说计数）总是在增加的。为了做到这一点，他拿起了一个有着2000年历史的素数计数工具，并试图将其改造以适用于孪生素数。这种工具的普通版本被称为**埃拉托斯特尼筛法**（**sieve of Eratosthenes**），它的工作原理大概是这样的。

<details>
<summary>Original English</summary>

**[Derek]**: One of the first mathematicians to really try was a 29-year-old Norwegian Viggo Brun. (bright music) Brun was working during the early years of the first World War, and with travel disrupted and Europe's mathematical centers largely out of reach, much of his work happened in quiet isolation back in Norway. His goal was simple to try and prove that the number or count of twin primes always increases. And to do this, he took a 2000 year old prime counting tool and tried to adapt it for twin primes. Now the normal version of this tool is called the sieve of Eratosthenes, and it works something like this.
</details>

**[Derek]**: 假设我们想找出100以内的素数。首先我们划掉1，因为那不是素数。然后我们圈出第一个素数，也就是2，并且我们划掉它所有的倍数。我们对3做同样的事：圈出它，然后划掉它的倍数，再对5和7重复这个过程。通过这四个非常迅速的操作，你的10乘10网格上剩下来的每一个数字，都是一个素数。此时，我们在7这里停下筛法，我们本可以继续用11或30去筛选，但事实证明我们不需要这么做。那是为什么呢？因为下一个素数是11，那么让我们检查100以内能被11整除的数。22是11的两倍，但因为它能被2整除，所以我们早就把它抓出来了。我们还有33，但它能被3整除。同样的逻辑适用于55和77。那11乘以11呢？你会注意到那是121，这并不在我们的范围内。因此，100以内所有的11的倍数，都已经被更小的素数抓取过了。所以用11去进行筛选将不会再划掉任何新的数字。

<details>
<summary>Original English</summary>

**[Derek]**: Say we want to find the primes up to 100. First we remove one because that's not prime. Then we circle the first prime, that is two, and we remove all of its multiples. We do the same for three. Circle it and remove its multiples, (bright music) and then repeat that for five and seven. And with these four very quick operations, every single number that's left on your 10 by 10 grid is a prime number. Now we stop the sieve at seven, and we could keep going sieve by 11 or 30, but it turns out that we don't have to. So, why is that? Well, the next prime is 11. So, let's check the numbers below 100 that are divisible by 11. 22 is two times 11, but since it's divisible by two, we already caught it. We also have 33, but that is divisible by three. And a similar logic holds for 55 and 77. But what about 11 times 11? Well notice that is 121, which is not in our range. So, every multiple of 11 below 100 was already caught by a smaller prime. So, sieving by 11 would cross out nothing new.
</details>

**[嘉宾]**: 所以，埃拉托斯特尼（Eratosthenes）有这样一个观点：你只需要筛选到最大为该数字平方根大小的素数即可。

<details>
<summary>Original English</summary>

**[Speaker]**: So, Eratosthenes, has this idea that you only need to sieve out the primes that are at most square root, the size of the number.
</details>

**[Derek]**: 但还有第二种方式来形象化这个筛法。把数轴拿出来，让每一个素数发射出一道波，波长就等于那个数字的大小。所以，来自2的波会降落在每一个相隔2的数字上，来自3的波落在每一个相隔3的数字上，以此类推。现在，请注意，无论一道波落在哪儿，那个数字就一定是合数。但是，那些逃过了之前所有波及的数字呢？它们就必须得是素数。于是你最终得到了这个极其美妙的关于筛法的可视化展示。这两种方法都让识别素数变得异常简单。

<details>
<summary>Original English</summary>

**[Derek]**: But there's also a second wave to visualize this sieve. Take the number line and let each prime send out a wave with the wavelength equal to the size of that number. So, the wave from two lands on every second number and the wave from three on every third and so on. (bright music) Now, notice that wherever a wave lands, that number has to be composite. But the numbers that escape every preceding wave, well those have to be prime. And so you end up with this beautiful visualization of the sieve. (bright music) And both of these methods make it incredibly easy to identify the primes.
</details>

**[嘉宾]**: 但布伦并不关心留下来的是哪些具体的素数，他只需要知道留下了“多少个”。为了做到这一点，他计算了所有被划掉的数字，然后用总数减去这个数量，因为没被划掉的无论是什么都必定是素数。所以，让我们用这个方法来找出100以内的素数数量。我们可以保持一个滚动的计数。所以，我们从100开始。我们将要扔掉所有2的倍数。好吧，还剩下50个数字，没问题。然后我们打算扔掉3的倍数。那么100以内有多少个3的倍数呢？100除以3并不是一个整数。它是33又三分之一的样子，但我们不能扔掉分数个数。所以，好吧，忘记那个愚蠢的小分数。我们同样对待5和7的倍数，但现在计数值变成了负数。哦，原来有些数字被划掉了两次，比如6，它是2和3的倍数。所以当我们在移除2的倍数时划掉了它一次，在移除3的倍数时又划掉了一次。因此，我们必须把它加回来一次。同样的事情发生在了10的倍数身上（它是2乘以5），14（2乘以7），15（3乘以5），等等。所以，我们把这些重叠的部分加回来，现在的计数升到了28，但它仍然不太对劲。

<details>
<summary>Original English</summary>

**[Speaker]**: But Brun didn't care about which primes were left, he just needed to know how many were left. And to do this, he counted all the numbers that were crossed out and then subtracted this from the total, since whatever is not crossed out must be prime. So, let's use this to find the number of primes below 100. We can keep a running count. So, we'll start with 100. We're gonna throw out all the multiples of two. Well, that's 50 numbers left, okay? Then we're gonna throw away multiples of three. Well, how many multiples of three are there less than 100. 100 divided by three is not a whole number. It's like 33 and a third, but we don't throw out fractions. So, okay, forget that stupid little fraction. We do the same for the multiples of five and seven, but now the count has gone negative. Well, it turns out that some numbers got crossed out twice, like six for example, it's a multiple of two and three. So, we crossed it out once when we removed multiples of two and again when we removed multiples of three. So, we have to add it back once. The same thing happens for multiples of 10, which is two times five, 14 which is two times seven, 15, which is three times five and so on. So, we add these overlaps back and now the count rises to 28, but it's still not quite right.
</details>

**[嘉宾]**: 现在我们已经把2乘3乘5的倍数三重地加了回来，所以我们需要再次减去。

<details>
<summary>Original English</summary>

**[Speaker]**: Now we've triple added back in the multiples of two times three times five, so that we need to subtract one more time.
</details>

**[Derek]**: 同样的事情也发生在42上（它是2乘3乘7），还有70（2乘5乘7）。还有一个第四个三重交叉，也就是2乘3乘5乘7，即105，但它已经大于100了。所以在这里它毫无贡献。但为了保持模式的完整性我们还是把它写进去。在处理完三个因数的重叠之后，我们再把由四个因数构成的组合加回来：2乘3乘5乘7，即210。那也大于100了，所以它的贡献也是0。最后，我们把起初那四个用于筛选的素数自己加回来，并且减去1，因为它一开始也被算在内了。于是，最终的计数定格在25个素数上。这个不断在减去和加回数字中交替的过程被称为**容斥原理**（**inclusion exclusion**）。它使得找出一个给定数字范围内有多少个素数变得极其简单。现在这个方程看起来依然有些杂乱，但实际上我们可以将其重写成这种形式。请注意，我们添加的每一个素因数都仅仅是在这个级数里增加了一个额外的项。比如2在这里，3在这儿，5到这边，7跑到那儿。如果我们尝试在某个更大的数值范围内寻找素数，而且我们想要加上11作为素因数，它仅仅会多增加一个“1减11分之一”的项。一般而言，如果我们让这个筛法一直运行到某个素数P，并且P小于N的平方根，那么这个计数约等于这个公式。

<details>
<summary>Original English</summary>

**[Derek]**: The same thing happens for 42, which is two times three times seven, and 70, which is two times five times seven. There's a fourth triple two, three times five times seven, which is 105, but that's already bigger than 100. So, it contributes nothing here. But we'll write it in to keep the pattern complete. After the triples, we add back the quadruple, two times three times five times seven, which is 210. That's also bigger than 100, so it contributes zero as well. And finally, we add back the four sieving primes themselves and subtract one because it was included in the count. So, the count lands at 25 primes. This process of alternating between subtracting and adding numbers back in is called inclusion exclusion. And it makes it super easy to find out how many primes there are up to some given number. Now this equation still looks a little bit like a mess, but actually we can rearrange it into this form. Now notice that every prime factor we added just adds an additional term in this series. We've got the two that goes over here, the three goes over here, five goes over here, and seven goes over here. And if we were trying to find primes for some higher number and we wanted to add 11 as a prime factor, it would just add one additional one minus one over 11 term. Now in general, if we keep the sieve going up to some prime P, which is less than the square root of N, then the count becomes approximately this.
</details>

**[嘉宾]**: 但这仍然只是单单对素数的计数。布伦真正想要的是孪生素数的计数。因此，在这一环节他改造了他的筛法，去寻找N和N+2都是素数的情况。举个例子，当你在用5做筛选时，你正如往常那样移除能被5整除的数字N。但在那之上，你还需要移除那些使得N+2能被5整除的数字。所以，你也要移除23，28，33等等，因为在那些情况下，N+2分别是25，30，35等等。这就意味着，普通的筛法里一个素数P大约移除了每P个数字中的1个，而孪生素数筛法则移除了2个。于是这将计数方程改变成了现在这样，其中2之后所有项的分子都变成了一个2。现在，如果我们画出该公式预测的孪生素数的数量图，我们会发现它的增长大致符合“N除以N自然对数的平方”的规律，这与我们的启发式估算是相吻合的。所以看起来布伦似乎做到了，但可惜情况并非如此。

<details>
<summary>Original English</summary>

**[Speaker]**: But this is still just the count of primes. What Brun really wanted was the count of twin primes. And so this is the part where he adapted his sieve, to find a case where both N and N plus two are prime. For example, when you're sieving by five, you remove the numbers where N is divisible by five, just as before. But in addition, you need to remove the numbers where N plus two is divisible by five. So, you also remove 23, 28, 33 and so on because in those cases, N plus two is 25, 30, 35 and so on. So, this means that while in the ordinary sieve a prime P removes about one out of every P numbers, the twin prime sieve removes two. And this changes the count to this, where the numerator for all the terms after two, ends up getting a two. Now, if we plot the count of twin primes that this predicts, we see that it grows roughly like N over the natural logarithm of N squared, just as for our heuristic. And so it seems like Brun did it, but unfortunately that is not the case.
</details>

**[嘉宾]**: 我们说过100除以3等于33又三分之一，先别管那点微小的误差，那些小小的误差，事实证明要控制这些误差非常困难，因为像这样的小误差实在太多了。每一个误差最多是1，它是一个舍入误差。

<details>
<summary>Original English</summary>

**[Speaker]**: We said that 100 divided by three is 33, and a third, but forget about that little error, those little errors, it's very difficult to control those errors 'cause there are so many of those little errors. Each one of them is at most one it's a rounding error.
</details>

**[Derek]**: 让我们再次以传统的埃拉托斯特尼筛法为例，当我们只用一个素数去筛选时，我们只有除以2这一项。所以那只有1个舍入误差；当有两个素数即2和3时，会有3个独立的舍入误差；但是如果是3个素数：2、3和5，那就已经有7个独立的舍入误差了，它们分别对应容斥原理公式中的每一项。所以你可能开始察觉到了这里面的普遍规律。1个素数会产生“2的1次方减1”个项，2个素数产生“2的2次方减1”个项，3个素数产生“2的3次方减1”个项。一般来说，如果你用K个素数去筛选，你大约会得到“2的K次方减1”个误差项，但我们可以忽略掉那个减1，因为它不会造成太大影响。所以这意味着如果你正在筛选普通素数，误差的增长大致跟2的K次方成正比。但是如果你在筛选孪生素数，情况会变得更糟。此时的误差增长大致就像4的K次方了。所以这就非常非常快地引发了大量的问题。

<details>
<summary>Original English</summary>

**[Derek]**: Take the traditional sieve of Eratosthenes again, when we're sieving with just one prime, we just have an over two. So, one rounding error, with two primes, two and three, there are three separate rounding errors, but with three primes, two, three, and five, there are already seven separate rounding errors, each for one term in the inclusion exclusion. And so you might start to see the general pattern here. One prime gives two to the power one minus one terms, two gives two to the power two minus one terms, and three primes gives two to the power three minus one terms. In general, if you sieve by K primes, you get roughly two to the power K minus one error terms, but we can drop the one because it doesn't really make much of a difference. So, that means that if you're sieving for normal primes, the error grows roughly like two to the power K. But if you're saving for twin primes, it gets even worse. And now the error grows roughly like four to the power K. And so this causes a lot of trouble very, very quick.
</details>

**[嘉宾]**: 然后对于孪生素数来说，情况还要更糟。主要的主项增长要缓慢一些，但误差项的增长却快得多。所以它的起步依然是很慢的。很快你就能看出一旦这些误差项开始占据主导地位，你就有大麻烦了。所以他面临的问题是：他拥有的这个主项，它确实以他预想的方式在增长，但是随后它就被那些误差项给超越并压倒了。

<details>
<summary>Original English</summary>

**[Speaker]**: And then here for the twin primes, it's even worse. The main term grows a bit more slowly, but the error term grows much faster. So, it still starts off slow. And so you can quickly see that once these error terms start dominating, you get into trouble. So, the issue he was facing is he had this main term and the main term, you know, it grew in the way he wanted to, but then it just got overtaken and dominated by those error terms.
</details>

**[Derek]**: 完全正确。在一般情况下的分析中，特别是分析数论中，本质上就是你所相信的那个反映真相的主项（如果它确实是真相的话），与试图在数学上证明误差项处于更低阶状态之间的对抗。

<details>
<summary>Original English</summary>

**[Derek]**: Exactly. And that's all of analysis, in general analytic number theory in particular is the fight between the main term that you think is the truth, if it actually is the truth, and getting the error term to be provably lower order.
</details>

**[嘉宾]**: 所以对于孪生素数，主项的增长大概是这样的，类似于N除以N自然对数的平方。但那并非真实的计数，因为为了得到真实计数，我们必须加上和减去那些误差项，这使得我们得到了一个上限和下限。现在你能看到问题所在了。因为真正的计数可能落在这个范围里的任何一处，并且如你所见，其中很大一片区域都是负数。因此，为了证明这个猜想，我们必须证明的是：这个下限始终是正数并且在不断增长。但这正是我们使用这种筛法时遭遇瓶颈的地方。因为我们用来筛的素数越多，这些误差项就越容易累积起来，而我们就无法证明下界为正。

<details>
<summary>Original English</summary>

**[Speaker]**: So, for twin primes, the main term grows roughly like this, something like N over the natural logarithm of N squared. But that's not the true count, because to get the true count, we must add and subtract the error terms, which gives us this upper and lower bound. And now you can see the problem. Because the true count can be anywhere in this range, and as you can see, a big swath of it is negative. So, to prove the conjecture, what we must do is we must show that this lower bound is always positive and growing. But that is where we run into a problem with the sieve we've been using. Because the more primes we sieve by, the more those error terms start to accumulate and we just can show this.
</details>

**[嘉宾]**: 所以布伦最终意识到，如果你削弱筛法，你不需要一路筛到X的平方根，而是筛到比那更小的某个值，并且非常谨慎地处理你的容斥原理，你实际上就可以处理掉那些误差项。

<details>
<summary>Original English</summary>

**[Speaker]**: And so what Brun eventually realized is that if you weaken the sieve, if you don't sieve all the way up to square root X, but to up to something less than that, and you are very careful about your inclusion exclusion, you can actually take care of those error terms.
</details>

**[Derek]**: 所以，只需要用较少的因子来运行筛法，也就是仅仅筛到N的“10分之1次方”。结果，他成功地获得了对误差项足够的控制权。但这是一种折衷。假设你想找出100亿以内的所有素数，利用平方根的方法，你需要用筛法筛选到100亿的平方根，也就是10万。但这会给你带来大量的误差项。而使用布伦的方法，你只需要筛到100亿的10分之1次方，那仅仅是10而已。但这有个问题。因为布伦没有用所有的素数去筛，有一些存活下来的数字根本不是素数，而是一些带有许多素因数的数字，在布伦的情况下，最多能有9个素因数。所以他最终实际证明的是：存在无穷多对相差为2的数字，其中每个数字最多有9个素因数。

<details>
<summary>Original English</summary>

**[Derek]**: So, run a sieve by fewer factors, only up to N to the power one over 10. And as a result, he gained enough control over the error term. But this chooses a trade off. Say you wanted to find all the prime numbers up to 10 billion, then using the square root method, you would need to sieve up to the square root of 10 billion, which is 100,000. But that gives you a lot of error terms. But with Brun's method, you would only need to sieve up to 10 billion to the power one over 10, which is just 10. But there's a catch. Because Brun, didn't sieve by all the primes, there were some survivors that weren't prime at all, but numbers with many prime factors, in Brun's case up to nine. So, what he actually ended up proving is that there are infinitely many pairs of numbers two apart, where each number has at most nine prime factors.
</details>

**[嘉宾]**: 布伦的技术之后被不断地改进、再改进，我们从9个素因数推进到了7个，再到3个。直到1973年，中国数学家**陈景润**（**Chen Jingrun**）横空出世，他证明了存在无穷多个素数P，使得P+2最多只有2个素因数。

<details>
<summary>Original English</summary>

**[Speaker]**: Brun's techniques were improved and improved and improved, and we went from nine prime factors to seven prime factors to three prime factors. Until in 1973, a Chinese mathematician Chen Jingrun comes along and proved that there are infinitely many prime P, where P plus two has at most two prime factors.
</details>

**[嘉宾]**: 这已经是你能不用真正证明它，但无限接近证明孪生素数猜想的极限了。我们被卡住了，就好像我们已经到达了所能接近的最极限，无法再往前迈进半步。

<details>
<summary>Original English</summary>

**[Speaker]**: This is as close as you could get to proving the twin prime conjecture without actually getting there. We're stuck like we're like as close as we can get and no further.
</details>

### GPY方法与“不可能”的墙壁

**[嘉宾]**: 没错。所以那是一种逼近思路，一种逼近孪生素数机制的途径。还有另一种。那另一种机制是，两个连续素数之间的最小间距能有多小？所以我们不再说它们相差为2、且其中一个是素数另一个我们则试图减少它包含的素因数个数。我们转而要求两者都必须是素数，但是我们试着缩小它们之间的距离。

<details>
<summary>Original English</summary>

**[Speaker]**: Right. So, that's one approximation, one mechanism for approximating twin primes. There's another. So, the other mechanism is what's the smallest gap between two consecutive primes? So, instead of saying they differ by two and one of them's prime and the other one, well, we're gonna try to get, you know, reduce the number of prime factors that it has. Instead we're gonna say both numbers must be prime, but let's reduce the distance between them.
</details>

**[Derek]**: 我们回顾一下，平均而言，连续素数之间的间隔大约是N的自然对数。因此问题变成了，我们至少能不能证明存在着比那个平均间隔更近的素数对？几十年来，数学家们不断地在攻克这个问题。到了1988年，这个间距已经下降到了大约平均间距的四分之一。这意味着如果在一个极其庞大的量级上平均间距是100，那么有些素数之间的距离必定有时会缩减到大约25之内。然后到了2005年，Goldston、Pintz和Yildirim（简称**GPY**）证明了一个令整个数学界震惊的结果。

<details>
<summary>Original English</summary>

**[Derek]**: Now remember, on average consecutive primes sit about the natural logarithm of N apart. And so the question became, can we at least prove that primes come closer than that average gap? For decades, mathematicians kept chipping away at this problem. By 1988, the gap had dropped all the way down to roughly a quarter of the average gap. This means that say the average gap is 100 at some enormous scale, then primes must sometimes come within about 25 of each other. But then in 2005, Goldston, Pintz and Yildirim, proved a result that shocked the mathematical community.
</details>

**[嘉宾]**: 并且他们宣布了一个引人注目的结果的证明：素数间距的界限被推到了平均值的0%的0%。

<details>
<summary>Original English</summary>

**[Speaker]**: And they announced the proof of a spectacular result, 0% bounded gaps of 0% of the average.
</details>

**[Derek]**: 等等，什么？

<details>
<summary>Original English</summary>

**[Derek]**: Wait, what?
</details>

**[嘉宾]**: 他们证明了你可以把这个比例变得随你想要的那么小。这意味着这个间距可以是平均间距的十分之一、百分之一，甚至是一百万分之一。它可以随你所愿地小到任意程度，而且素数有无穷多次会变得如此接近。

<details>
<summary>Original English</summary>

**[Speaker]**: They proved that you can make the fraction as small as you want. This means the gap could be one 10th or 100th, or even 1000000th of the average gap. It could be as arbitrarily small as you like, and infinitely often primes get that close.
</details>

**[嘉宾]**: 在我年轻的时候，我们根本不知道存在比，比如十分之一个logX更小的间距，或者有无穷多对素数对。然后Goldston和Yildirim想出了攻克它的方法。

<details>
<summary>Original English</summary>

**[Speaker]**: When I was young, we didn't know there were gaps of size, less than say one 10th log X or infinitely many primes pairs and Goldston and Yildirim, came up with a method to attack that.
</details>

**[Derek]**: 但是这个方法也接近了另一个更重大的东西——两个素数之间存在一个**绝对有界距离**（**absolute bounded gap**）。

<details>
<summary>Original English</summary>

**[Derek]**: But the method also came close to something even bigger, an absolute bounded gap between two primes. (bright music)
</details>

**[嘉宾]**: 这确实是个重大的突破。

<details>
<summary>Original English</summary>

**[Speaker]**: And so that was like a big thing.
</details>

**[Derek]**: 为什么大家都有这么大的渴望，想要把0%或者是任意小，推进到一个确切的数字边界上呢？

<details>
<summary>Original English</summary>

**[Derek]**: What was the big desire to go from 0% or arbitrarily small to a concrete bounded gap?
</details>

**[嘉宾]**: 因为我们认为两个连续素数之间有无穷多次距离为2的界限，而现在我们证明的是它的间距是logX，而X是在不断变大的。

<details>
<summary>Original English</summary>

**[Speaker]**: Well, because we think that the bound between two consecutive primes infinitely often is two, and right now we're showing that it's log X, and X grows.
</details>

**[Derek]**: 如果他们能够推进到有界距离，他们就会有一种全新的手段去攻击孪生素数猜想了。唯一的问题是，他们的工具似乎撞到了一堵墙。于是在2005年，**美国数学研究所**（**American Institute of Mathematics**）召开了一次会议，把世界上这个领域最顶尖的专家们全召集了起来。GPY团队，Andrew Granville，Kannan Soundararajan等等，齐聚在加利福尼亚州待了一个星期，大家的目标非常明确：证明素数之间存在有界距离。

<details>
<summary>Original English</summary>

**[Derek]**: If they could get to bounded gaps, then they had another method to attack the conjecture. The only problem was that it seemed like their tool ran into a wall. And so in 2005, the American Institute of Mathematics convened a meeting, gathering all the world's leading experts on this problem. GPY, Andrew Granville, Kannan Soundararajan, all gathered for a week in California with one explicit goal, to prove a bounded gap between primes.
</details>

**[嘉宾]**: 那时我还只是个年轻的研究生，很幸运能去参加这个会议。你被世界上在这个主题上最拔尖的专家们包围着。我们整整花了一个星期。这一个星期的最终结论，基本上就是这件事是不可能的。并且Soundararajan展示了为什么想做到这件事是不可能的。因此对我来说，事情就这么敲定了，而且你知道的，这不打算成为我的毕业论文题目了，我得去研究别的东西，于是我就去做别的事了。但有一个人没有参加那场会议，他就是**张益唐**（**Yitang Zhang**）。

<details>
<summary>Original English</summary>

**[Speaker]**: I was a young graduate student, I was very lucky to get to go to this meeting. You're surrounded by the world's top experts on this subject. We spent an entire week. And the upshot of this week was basically that it's impossible. And Soundararajan shows how it's not possible to do this thing. And so as far as I was concerned, that was that, and I, you know, this wasn't gonna be my thesis problem, I'd have to do something else and I went off and and did other things. But there was one person who was not at this meeting, Yitang Zhang.
</details>

### 张益唐的突围

**[Derek]**: 张益唐在中国长大，大约在30岁的时候搬到了美国，准备去拿他的数学博士学位，但他从未拿到过任何推荐信，因此在找工作时步履维艰。他有一段时间甚至住在自己的车里，最终为了谋生打零工打了整整七年，其中就包括在赛百味餐厅记账和整理收据。然而，在做着所有这些琐事之余的空闲时间里，他会开车去当地的图书馆，阅读有关数论的书籍和期刊。直到1999年，他终于等到了好运气。他的一个朋友帮他在新罕布什尔大学找了一份讲师的工作。现在他终于可以把所有的时间都花在做他最热爱的事情上——数学。张益唐说，当他还是个孩子的时候，他就“幻想过有朝一日能解决一个重大的数学难题”。到了2010年，他已经确定了自己要主攻的重大难题：素数之间的有界距离。但要理解他研究的具体内容，我们需要先明白GPY团队究竟建立了一套怎样的体系。

<details>
<summary>Original English</summary>

**[Derek]**: Zhang grew up in China, and around the age of 30 moved to the U.S. to get his PhD in mathematics, but he never got any recommendation letters and so struggled to find a job. He ended up living in his car for time and ultimately working odd jobs for seven years, including at Subway, where he kept the books and sorted receipts. Yet, while doing all of that in his spare time, he would drive down to the local library to read books and journals on number theory. (bright music) Then in 1999, he got a lucky break. One of his friends helped him get a job as a lecturer at the University of New Hampshire. So, now he could spend all his time doing what he loved most, math. Zhang said that when he was a kid, he "Imagined there would be a day that I would solve a major math problem." And by 2010, he had identified his major problem to focus on, bounded gaps between primes. But to understand what he was working on, we need to understand what exactly it is that GPY had built.
</details>

**[Derek]**: 你看，他们想在一个有界的区间内找到两个素数。为了达到这个目的，他们想象出了一种上面布有几个洞的模板。所以，让我们也做一个一样的模型，为了方便这个例子，我们假设这个模板的跨度直径为6，孔洞位于0，2，和6的位置上。接下来，我们把这个模板放在数轴的任何地方，比如说从12开始。接着我们问一个简单的问题：我们透过洞看到了几个素数？在这个例子中，我们看到了12、14和18，它们都不是素数。所以我们记下0。接着我们把模板向旁边平移一个单位，然后重复这个过程，看到了13、15和19，其中有两个是素数。所以我们记下2。然后我们就一直这么做下去。如果你把它滑得再远一点，我们再次同时捕获到两个素数，23和29。现在，如果你在数轴上一直滑动这个模板，而它能够一直持续不断地捕捉到成对的素数，那么你就证明了在有界区间内，素数对有无穷多次地存在。在这个例子里界限就是6，因为那是我们模板的跨度直径。但这种方法有两个问题。第一，我们并不清楚所有素数的精确位置。第二，当然，你不可能拿着模板在数轴上永远滑下去，因为它是无限长的。

<details>
<summary>Original English</summary>

**[Derek]**: See, they wanted to find two primes within a bounded gap. And to do this, they imagined a stencil of sorts with some holes in it. So, let's do the same, and for the sake of this example, let's say the stencil has a diameter of six and holes at spot zero, two and six. Next we place the stencil anywhere on the number line, say starting at 12. And we ask a simple question, how many primes do we see? In this case, we see 12, 14, and 18, none of which are prime. So, we write down zero. Next we shift the stencil over one spot and repeat, 13, 15, and 19, two of which are prime. So, we write down two. And then we keep doing this. If you slide it a bit further, we catch two primes again, 23 and 29. Now, if you keep moving the stencil across the number line and it keeps catching two primes, then you have proven that infinitely often pairs of primes exist within a bounded gap. Six in this case, since that's the diameter of our stencil. But there are two problems with this approach. The first is that we don't know exactly where all the primes are. And the second is that of course you can't keep sliding a stencil down the number line forever because well, it's infinitely long.
</details>

**[Derek]**: 幸运的是，有一个简单的方法可以绕开第一个问题。你看，虽然我们不知道所有素数的具体位置，但我们确实知道它们在平均情况下的表现。比如说，我们取出一段数轴，从某个巨大的数字X到2X，那么我们无法精准预测这一段里的哪些数字会是素数。但我们能做的是，把它代入素数定理，并估算出平均而言能有多少个素数。而GPY团队意识到，他们可以对他们的模板方法做类似的操作，去建立一个某种意义上的“求平均机”。你所做的就是设置好你想要的模板，输入你的数值区间，然后机器就会输出它在每一个位置上所捕捉到的素数的平均数。所以，让我们在不使用机器的情况下做一个快速的例子，来看看这有何帮助。我们使用之前一样的模板，并且将区间设为20到40。实际上，在真实情况中你会使用一个大得多的区间，但为了简化，我们就用这个。要找到平均值，你只需把模板放在区间的开头，看看你透出来的都是哪些数字，20，22和26。这些都不是素数，所以捕获到的素数总数是0。然后我们把模板平移一格，看到了21，23和27。其中一个是素数，所以我们将总数增加1。现在让我们一直平移模板，把我们看到的所有素数相加。没有素数，就加0，有两个素数，就加2，以此类推。

<details>
<summary>Original English</summary>

**[Derek]**: Fortunately, there is an easy way to get around that first problem. See, while we don't know exactly where all the primes are, we do know how they behave on average. For example, say we take some stretch of the number line from some very large number X to two X, then we can't predict exactly which numbers in this stretch will be prime. But what we can do is put this into the prime number theorem and estimate how many primes to expect on average. (bright music) And GPY realized they could do a similar thing for their stencil method to build an averaging machine of sorts. All you do is you set up the stencil you want, input your range, and out comes the average number of primes it caught per position. So, let's do a quick example without the machine to see how this helps. Let's use the same stencil from before and use the range 20 to 40. Now, in reality, you would use a much larger range, but for simplicity, let's stick to this. To find the average, you just place the stencil at the start of your range, and you'll look at which numbers you see, 20, 22 and 26. None of which are prime and so the total prime count is zero. Then we shift the stencil over one spot and see 21, 23 and 27. One of which is prime, so we increase the total by one. Now let's keep shifting the stencil and keep adding all the primes we see. No primes, so add zero, two primes, add two, and so on.
</details>

**[Derek]**: 如果你一直移动模板直到末尾，你会在21个起始位置上一共找到14个素数。因此，平均值就是14除以21，也就是每个位置大约捕获0.67个素数。在这个通过手工逐一检查每个位置的例子里，我们能看到模板有好几次都成功地在一个位置上同时捕获了两个素数。但这个“求平均机”不会告诉我们这些。它所输出的只有一个平均值，而这个平均值本身无法保证它真的同时抓住了两个素数。因为你同样可以想象出这样一种情形：把这14个素数均匀地分散在14个各自独立的位置里。即便平均值是0.8、0.9甚至1，同样的道理依然成立。我知道这概率很小，但确实有可能每个位置刚好就只抓到了一个素数，从而使得平均数是1。但如果平均值大于1呢？如果在总计里我们找到了22个素数呢？那么，即便每个位置都抓住了一个素数，你依然会多出来一个素数，它无处可去，只能挤进那其中一个位置里。换句话说，如果平均值大于1，那么这就保证了至少有一个位置同时捕捉到了两个素数。所以这就是游戏的核心了：让素数的平均数突破1。但这仍然留下了一个问题。即使你做到了，那这又怎么帮你证明你能一路延伸到无穷远处，并持续获得有界的素数间隔呢？你需要记住，你刚刚是对任何一个大数X证明了这件事，那么也就没有力量能阻止你把那个X替换成2X，然后把2X替换成4X，再把4X替换成8X，这样一路延展到无穷大。所以，如果你能证明任意大数X区域内的平均间隔超过1，凭借这种巧妙的设计，它会立刻延展到无限远，而你也就证明了你的有界间隔。

<details>
<summary>Original English</summary>

**[Derek]**: Now, if you keep shifting the stencil all the way until the end, you find a total of 14 primes across 21 starting positions. (bright music) And so the average is 14 over 21, or about 0.67 primes per location. Now in this case where we checked every spot by hand, we could see that the stencil caught several positions with two primes in them. But the averaging machine doesn't tell us this. All that spits out is an average, and that average alone can't guarantee that it caught two primes at once, because you could just as well imagine spreading all of these 14 primes over 14 individual positions. And the same would be true if the average was 0.8, 0.9, or even one. I know it's unlikely, but it could be that every position only caught one prime to bring the average to one. But what if the average was larger than one? What if we found 22 primes in total? Well, even if every position had caught one prime, you would still have one prime left over and that needs to go in one of those other positions. So, in other words, if the average is above one, then that guarantees that at least one position caught two primes. And so that's the game. Get the average number of primes above one, but that still leaves one question. Even if you could do that, then how does that help you prove that you keep getting bounded gaps all the way up to infinity? Well, remember you just proved that for any large number X, so there's nothing stopping you from replacing that X with two X, and that two X with four X, and then you could replace the two X with four X and the four X with eight X, and so, on all the way up to infinity. So, if you can prove that the average gap is above one for any large number X, then with this clever setup, it immediately extends all the way out to infinity, and you would've proven your bounded gap.
</details>

**[Derek]**: 不幸的是，如果仅靠当前的输入参数运行机器，模板会光顾很多根本抓不到素数的位置，这把平均值拖慢了，意味着它永远到不了1之上。因此，GPY对他们的机器做了最后一点微调。他们意识到，某些起始位置抓到素数的概率就是比别的要高。例如，如果模板仅仅落在偶数上，那么除非它包含了2，否则它给出的素数数量永远是0。所以，在赋予权重的时候，这些位置不应该跟其他位置受到同等对待。同理，如果你模板中的一个或多个数字能被3、5、7或者别的小素因数整除，那么模板里包含素数的概率也就大大降低了。所以它们的权重同样也该减少。于是，GPY对每一个位置都做了几个像这样简单的检查以分配权重，并估计了该位置含有素数的概率大小。这把他们的求平均机转变成了一个**加权求平均机**（**weighted averaging machine**）。结果，那个加权平均值扶摇直上。利用这台升级过的机器，他们证明了，如果你挑选任何一个大数X，那么在X到2X的区间内，你可以使得加权平均值无限接近于1，但就是无法突破1之上。他们已经非常近了，但却撞上了南墙。一堵来自于他们权重的墙。因为要想弄清楚如何对不同的位置赋予权重，他们需要知道素数在所谓的**等差数列**（**arithmetic progression**）中是如何分布的。等差数列基本上就是步长全部相等的一系列数字。所以，3，7，11，15，这就是一个步长为4的等差数列。GPY需要知道素数分布在具有各种不同步长的等差数列中的情况。幸运的是，他们知道20世纪60年代的一个定理，可以完美用来做这件事。

<details>
<summary>Original English</summary>

**[Derek]**: Unfortunately, running the machine with just the current inputs, the stencil visits many positions where it catches zero primes, this drags the average down and means it will never get above one. So, GPY made one final tweak to their machine. They realize that some starting positions are more likely to catch primes than others. For example, if the stencil only lands on even numbers, it will always give zero primes unless it includes two. So, those positions should not be weighted equally to the others. Similarly, if you can divide one or more of the numbers in the stencil by three, five, seven, or other small prime factors, it's also more unlikely you have primes in your stencil. So, they should also be weighted less. Now, GPY did a few simple checks like this for each position to assign it a weight, and estimate of how likely it is that this position contains primes. This turned their averaging machine into a weighted averaging machine. And as a result, that weighted average shot up. With their updated machine they proved that if you pick any large number X, then in the range X to two X, you could get the weighted average arbitrarily close to one, but not above one. They were close, but they ran into a wall. A wall that came from their weights, because to figure out how to weigh different positions, they needed to know how primes are distributed in something known as an arithmetic progression. These are basically just series of numbers where they're all the same step size apart. So, 3, 7, 11, 15, that's an arithmetic progression with a step size of four. Now, GPY needed to know how primes were distributed over many such arithmetic progressions with all kinds of different step sizes. Fortunately, they knew of theorem from the 1960s they could use to do exactly this.
</details>

**[嘉宾]**: 它是平均意义上的黎曼假设的替代品，而事实证明在很多这样的算术应用中，这正是实际所必需的东西。

<details>
<summary>Original English</summary>

**[Speaker]**: It's the substitute for the Riemann hypothesis on average, and it turns out that that's what's actually necessary in a lot of these arithmetic applications.
</details>

**[Derek]**: 但那个定理并非放之四海而皆准。它仅仅在步长达到X的平方根或者说“X的二分之一次方”时才有效。这个代表二分之一的学术术语叫做**分布级数**（**level of distribution**）或 Theta（$\theta$）。它决定了步长能开到多大，并依然能在这些数列中获取可靠的素数计数。尽管数学家们相信这个定理在超越二分之一次方的情况下依然成立，但这从未被证明过。而这恰好就是麻烦所在。当GPY带着这个上限天花板去进行计算时，他们发现他们能拿到的最大加权平均值就是2乘以Theta。换言之，他们无限逼近了1，但就是跨不过去。

<details>
<summary>Original English</summary>

**[Derek]**: But that theorem doesn't work everywhere. It only works for step sizes up to the square root of X or X to the one half. The technical term for this one half is the level of distribution or theta. It tells you how large the step sizes can be while still getting a reliable count of primes in those progressions. And mathematicians believed that the theorem worked beyond X to the half, but this was never proven, and that is where the trouble lies. When GPY ran their calculation with this ceiling, they found the maximum weighted average they could get was two times theta. In other words, they got really close to one, but they could never actually cross it.
</details>

**[嘉宾]**: 他们的研究方法表明，如果你能超越那个二分之一，你只要能做到0.5000001，那么他们就不再只是得到平均间距0%的差距，而是能够得到有界间隔。素数之间的距离就会被固定在一个确切的距离上。

<details>
<summary>Original English</summary>

**[Speaker]**: They showed in their method that if you could get beyond a half, you could do 0.5000001. Then instead of just getting 0% of the average gap, they can get bounded gaps. The primes would be some fixed distance apart.
</details>

**[Derek]**: 这就是2005年那场会议核心想探讨的问题。他们不断地试图突破那个二分之一的壁垒，但最终却得出结论：那是不可能的。从2010年开始，张益唐也花了两年时间对着这个问题死磕，他深入研究并内化了GPY的论证，夜以继日地工作仅仅是为了找到一条出路。（欢快的音乐）但在2012年夏天，张益唐精疲力竭，并且依然一无所获。为了清空思绪，他去科罗拉多州拜访了一位朋友，在那里，某天晚上当他们等待出发去听音乐会时，张益唐独自一人走到后院，寻找平时经常在这个庄园里漫步的鹿，但一只鹿都没来。所以他就是那样边走边想，然后突然之间，答案就浮现在了他的脑海里。他并没有带任何笔记或纸张，但张益唐相信他的想法是行得通的。

<details>
<summary>Original English</summary>

**[Derek]**: That's what the 2005 meeting was all about. They kept trying to push past that one half barrier, but they ended up concluding that it was impossible. From 2010 on, Zhang spent two years hacking away at it as well, internalizing the GPY argument, working day and night just to try and find a way through. (bright music) But by the summer of 2012, Zhang was exhausted, and had nothing to show for it. Hoping to clear his head, he visited a friend in Colorado, where one evening while they were waiting to leave for concert, Zhang stepped outside alone into the backyard, looking out for the deer that usually roamed the property, but no deer came. So, he was just walking and thinking when all of a sudden the answer came to him. He hadn't brought any notes or paper, but Zhang believed his idea would work.
</details>

**[Derek]**: 你看，GPY当时需要计算无数种含有各种大小不同步长的等差数列中的素数。但张益唐将注意力集中在了一个特殊类的步长上，那些仅仅由很小的素因数构成的步长。他意识到他能够重新组织这些误差项，使其成为一种能让它们彼此大幅抵消的形式。这使得他终于打破了二分之一那道壁垒的限制，尽管只超出了极其微小的一丝丝：仅仅是584分之一。在接下来的一年里，张益唐完善了他的证明。随后在2013年4月17日，他向《数学年刊》发送了那封奇妙的邮件。

<details>
<summary>Original English</summary>

**[Derek]**: You see, GPY had to count primes in many different arithmetic progressions with all sorts of step sizes. But Zhang focused on a special class of step sizes, one's built only from small prime factors, and he realized he could reorganize the error terms into a form where most of them get canceled out. This allowed him to push past the half barrier by a tiny fraction, just one over 584. Zhang spent the next year finalizing his proof, and then on the 17th of April, 2013, he sent off that curious email to the Annals of Mathematics.
</details>

**[嘉宾]**: 是的，《数学年刊》差不多每隔一天就会收到一份“黎曼假设的证明”，所以他们觉得，好吧，这肯定是不对的，但管他呢。你知道的，我们就找个审稿人看看。然后他们想，那我们就花这个下午的几个小时吧，我们会找到错误的，然后我们会对年刊说，你知道的，抱歉，这行不通。差距就在这里。接着他们就开始读了，然后因为他们是专家嘛，所以他们就往回翻。他们快速翻阅着，心想：是，这部分能行，这能行，但是等等，你在这儿肯定会卡住的。结果他们往后翻了五页，然后说：“喔，这真有意思。原来你是打算用这种方式来处理那个问题的。”好吧，但你接下来会遇到另一个问题，就像试图在房间里铺一块地毯。你想：“好，我知道那个角落，那个角落肯定会把你绊倒，哪怕你设法搞定了那边。”然后他读到处理那个角落的地方——不，他裁剪得恰到好处，它跟那个角落严丝合缝。等等。接着他们又翻了五页。等到那个星期结束的时候，他们已经重构了整个证明，一切都是正确的。

<details>
<summary>Original English</summary>

**[Speaker]**: Now, the Annals gets a proof of the Riemann Hypothesis every other day, so they're like, okay, surely this isn't gonna work out, but whatever. You know, we'll send it to a referee. And they're like, well, let's spend a few hours this afternoon. We'll find a mistake. We'll tell the annals, you know, sorry, it didn't work out. Here's where the the gap is. And they start reading it, and then they flip back, because they're experts. So, they can just flip through like, yeah, this'll work, this will work, but wait a second, you're gonna get stuck here. And they flip five pages and they're like, oh, that's interesting. That's how you're gonna handle that. Okay, but then you're gonna have another, it's like trying to lay down a carpet in a room. You're like, okay, I know that corner, that corner's gonna screw you up even if you managed to make it work over there. And then he goes over there, no, he cut it just right. It fits in that corner. Wait a second. And then they flip, you know, five more pages and by the end of the week, they've reconstructed the proof and everything's right.
</details>

**[Derek]**: 哇哦。

<details>
<summary>Original English</summary>

**[Derek]**: Wow.
</details>

**[Derek]**: 张益唐设计的模板跨度覆盖了7000万，上面分布有350万个孔槽。通过证明必定有两个孔槽永远能够捕捉到素数，他成功证明了7000万这个有界间距的存在。消息传开后，整个数学界都感到难以置信。

<details>
<summary>Original English</summary>

**[Derek]**: Zhang's stencil had 3.5 million slots, spread across a span of 70 million. And by proving two of those slots always catch primes, he proved a bounded gap of 70 million. When the news broke, mathematicians were in disbelief.
</details>

**[嘉宾]**: 基本上这就是个在领域里完全不知名的人。当我在开始读张益唐论文并开始意识到它很可能是正确的时候，我当时还以为那可能是我认识的某个人用了化名，免得如果被证实搞错了就会尴尬出丑。

<details>
<summary>Original English</summary>

**[Speaker]**: It was basically an unknown in the field. I actually thought when I started reading Yitang Zhang's paper and started realizing it was probably correct, I thought it was probably one of the people I knew under a pseudonym, trying to avoid being embarrassed by being wrong. If they were wrong.
</details>

**[Derek]**: 但很显然并不是这样，张益唐确有其人。仅仅一年多之后，他就被授予了麦克阿瑟“天才奖”（MacArthur Genius Grant）。

<details>
<summary>Original English</summary>

**[Derek]**: Of course it wasn't, Zhang was real. And just over a year later he was awarded the MacArthur Genius Grant.
</details>

**[嘉宾]**: 对我来说，这是数学界特别有意思的一面。我认为这是极少数对成就和成功的评定标准保持真正诚实的领域之一。他寄去了一份论证，大家严肃地对待了它。他们仔细审查了。起初他们并没有觉得那会是一个真正的证明。但他们坐在那里，给予了这份论证应得的时间，随后他立即被奉为了英雄，这正是他应得的待遇。对我而言，这表明了数学界的风气运作良好。我们是在做正确的事情。我觉得2013年什么《科学美国人》之类的杂志封面，刊登了张益唐的故事，讲述他在完全与世隔绝的情况下埋头苦干，找出了素数间的有界间隔。或许正是因为他的与世隔绝，使得他没有受到我们其他人那样群体思维的限制。不去理会那不是什么——要知道，我们曾经都被告知那是个不可能的问题。

<details>
<summary>Original English</summary>

**[Speaker]**: To me, this is a really interesting aspect of mathematics in particular. I think it's one of the very few fields where we have a truly honest approach to success and what counts as success. He sent in an argument, people took it seriously. They looked at it. They didn't think that he had a true proof. They sat there, they gave him the time that the argument was due, and he was immediately made a hero as he should have been. To me, it shows that mathematics culture works. We're doing the right thing. I think the cover of like Scientific American or whatever in 2013 is the story Yitang Zhang and how he got this bounded gap between primes toiling in complete isolation. And maybe it's because he was in isolation that he didn't have the group think that the rest of us did. To know that this was not, we were all told it's an impossible problem.
</details>

### Polymath与大幅缩减的距离

**[Derek]**: 在认识到有界间隔并不只是个不可能的梦想之后，人们开始重新打磨张益唐的方法以优化它。陶哲轩（Terence Tao）牵头组织了一个名为 **Polymath** 的在线合作团体，他们锐化了这个方法。以至于每过一个月、一周甚至每一天，那个上限数字都在不断被压低。一名当时的参与者描述了开会时的情景：“我记得那时的会议期间，每天大家都在疯狂刷新屏幕，就为了看看现在创造新世界纪录的究竟是谁。”最终，他们把数字一路拉低到了4680。

<details>
<summary>Original English</summary>

**[Derek]**: After realizing a bounded gap was not an impossible dream, people reworked Zhang's method to optimize it. Terence Tao spearheaded an online group called Polymath, and they sharpened the method. So, every month, week or day, that upper bound kept coming down. One of the attendees described being at a conference at the time, as I remember, sort of day by day, everyone was refreshing their screens to see who had the world record now, and ultimately they got the number all the way down to 4,680.
</details>

**[嘉宾]**: 与此同时，有一位名叫**詹姆斯·梅纳德**（**James Maynard**）的年轻博士后，他刚在牛津大学拿到博士学位，导师是另一位解析数论的世界级顶尖专家Roger Heath-Brown。那时他在蒙特利尔跟Andrew Granville共事。面对这个问题，他脑子里有一种完全正交的，从完全不同的角度出发的方法。在这之前，他已经在独立地取得了一些十分渐进的发展。

<details>
<summary>Original English</summary>

**[Speaker]**: Meanwhile, there's a young postdoc named James Maynard, who just got his PhD at Oxford with Roger Heath-Brown and other one of these analytic number theory world experts. And he's working with Andrew Granville, in Montreal. And he has a completely orthogonal approach to this problem that he'd been making some very incremental progress on independently.
</details>

**[Derek]**: 当梅纳德刚开始涉足时，他的导师明确地警告过他：“我希望你不要全职在这个问题上耗着，因为我非常有把握你注定会失败的。”但梅纳德无视了这个警告。他提出了一套攻克该问题的别样方法，仅仅在几个月内，他就让它奏效了。他进一步将间距缩小到了600。但他的方法同时还证明了别的什么东西。

<details>
<summary>Original English</summary>

**[Derek]**: When Maynard started, his advisor explicitly told him, "I hope you won't work on this problem full time, because I'm really pretty confident you're going to fail." But Maynard ignored the warning, and came up with a different way to attack the problem, and within just a few months, he got it to work. Further bring down the gap to 600. But his method also proved something else.
</details>

**[嘉宾]**: 他可以在一个有界的窗口里弄到3个素数。你在这个窗口里想放几个素数，边界就会随之调整，而且他的数字要更好。这套方法跟那个“二分之一指数”毫无关系。

<details>
<summary>Original English</summary>

**[Speaker]**: He can get three primes in a bounded window. The bound has to change depending on how many primes you wanna put in that window, and that his number is better. And the method has nothing to do with the exponent one half.
</details>

**[Derek]**: 等等，什么？

<details>
<summary>Original English</summary>

**[Derek]**: Wait, what?
</details>

**[嘉宾]**: 那个“二分之一”纯粹就是个海市蜃楼。它就是一个误导人的红鲱鱼（red herring）。

<details>
<summary>Original English</summary>

**[Speaker]**: One half was a pure mirage. It was a red herring.
</details>

**[Derek]**: 这太疯狂了。二分之一根本不是一个根本性的极限。你看，原来GPY团队的平均值之所以被卡在2乘Theta，是因为梅纳德的平均值大致呈现为“Theta 除以（2乘以K的自然对数）”的增长趋势，此处的K代表模板上的孔洞数量。所以，梅纳德所需要的一切，仅仅是足够数量的孔洞，这方法就奏效了。

<details>
<summary>Original English</summary>

**[Derek]**: That is crazy. One half was not a fundamental limit at all. See where GPY average was stuck at two times theta, Maynard's average grew roughly like theta over two times the natural logarithm of K, where K is the number of slots in the stencil. So, all Maynard needed was enough slots and it worked.
</details>

**[嘉宾]**: 只需要任何大于零的数就行了。当你向上走到二分之一的时候，由于你有了那个二分之一的条件，你确实会得到更好的数值。但这个有界间距仅仅需要达到——比如说0.01就行了，根本不需要0.50101。令人好奇的是，陶哲轩（Terry Tao）也独立地想到了同一种方法。他告诉了Ben Green，Ben Green在和Andrew Granville会面时说，“嘿，Terry有了一个新的想法，他觉得能把这事儿推得更远。”然后Granville回答说，“等一下。我的博士后梅纳德，他正在做一模一样的事情。我们得让这两个人互相交流一下。”Terry是个菲尔兹奖得主，到了这个时候他就像个超级重量级的选手。而James才是个刚拿博士学位的新人，于是Terry说：“你拿去吧，我不需要这个荣誉了。你知道的，这是你的主意，你放手去做吧。”

<details>
<summary>Original English</summary>

**[Speaker]**: You need any number greater than zero. When you go up to one half because you have one half, you'll get better numerics. But the bounded gaps you could do, just going up to, you know, 0.01, not 0.50101. Now, curiously, Terry Tao independently has the same approach. He tells Ben Green about it, Ben Green is meeting with Andrew Granville, and says, "Hey, Terry's got this new idea that he thinks is gonna get even farther." And Granville, says, wait a second. My postdoc, Maynard, is doing exactly the same thing. We gotta get these two guys to talk to one another. Terry's a Fields medalist, he's like a super heavyweight by this point, whereas James is this, you know, fresh PhD, and Terry says, you take it, I don't need this. You know, you this, it's your idea, you go with it.
</details>

**[Derek]**: 到2014年初，梅纳德加入了陶哲轩的Polymath团队。

<details>
<summary>Original English</summary>

**[Derek]**: By early 2014, Maynard joined forces with Tao's Polymath group.
</details>

**[嘉宾]**: 很显然，600在某种程度上只是一次概念证明，同样的方法能够得出更小的数字。但如果把所有潜力都榨干，也许你还能借用些别的新思路。因此，目前的世界纪录是：相差不超过246的素数对有无穷多个。

<details>
<summary>Original English</summary>

**[Speaker]**: It was clear that somehow 600 was just a proof of concept, and the same methods would give something smaller, but there were extra ideas that you could maybe use to squeeze everything out. And so the current world record is that there's infinitely many pairs of primes that differ by no more than 246.
</details>

**[Derek]**: 并且这个数字目前就停滞在这里了。在2022年，詹姆斯·梅纳德凭借他在素数间距上的研究工作，获得了数学界的最高荣誉——菲尔兹奖（Fields Medal）。

<details>
<summary>Original English</summary>

**[Derek]**: And that for now is where it stops. In 2022, James Maynard was awarded the Fields Medal, Mathematics, highest honor for his work on prime gaps.
</details>

**[嘉宾]**: 是的，我想这就是逼近孪生素数两个主要流派的一个基本轮廓：陈景润代表的那个方向，还有张益唐和梅纳德的方向。而张益唐缺席了那次会议的故事，也说明了他恰巧因为没有在场，从而不知道那是个“不可能的”难题。

<details>
<summary>Original English</summary>

**[Speaker]**: Yeah, I think that's the basic outline is the kind of two directions of approximation to twin primes Chen's direction, Brun, Chen, whatever, versus Zhang and Maynard, and this story that the Zhang wasn't at this meeting, so he didn't know it was impossible.
</details>

**[Derek]**: 这让我想起了“一英里四分钟”的挑战，当时每个人都认为这是不可能的。没人能做到。

<details>
<summary>Original English</summary>

**[Derek]**: It reminded me of the four minute mile where everyone thought it was impossible. No one did it.
</details>

**[Derek]**: 然后在1954年，罗杰·班尼斯特（Roger Bannister）史无前例地打破了这一纪录。在确信这是有可能完成之后，仅仅过了46天，另一位叫约翰·兰迪（John Landy）的赛跑运动员也打破了纪录。到1956年底的时候，已经有10个人打破了那项纪录，所有的突破都源于他们知道那是“可能”的。那么，有没有可能把这个间距进一步压得更低呢？有这种可能吗？实际上，数学家们已经找到了进一步缩小间距的方法，但所有的这些结果都是在特定的前提条件下的。例如，有一个**埃利奥特-哈伯斯坦猜想**（**Elliot-Halberstam conjecture**），它假设素数在等差数列中是均匀分布的，或者说“分布级数可以取大到1”。而在2013年，梅纳德证明了，如果你假设这个猜想是成立的，那么间距会立刻暴跌到仅仅只有12。一年之后，Polymath小组证明了如果你假设该猜想的进阶更强版本成立，这个间距将会直接降到6。但如果不假设任何前提，目前的极限依然是246。我想问问你，你觉得我们终究会解决孪生素数猜想吗？

<details>
<summary>Original English</summary>

**[Derek]**: And then for the first time ever, Roger Bannister broke it in 1954, and after knowing it was possible, just 46 days later, another runner called John Landy broke it as well. And by the end of 1956, 10 people had broken it, all from knowing that it was possible. So, what about pushing that gap down even lower? Is that possible? Well, mathematicians have found ways to bring it down even more, but all of these results are conditional. For example, there is the Elliot-Halberstam conjecture, which assumes primes are spread evenly across arithmetic progressions, or that the level of distribution can be taken as large as one. And in 2013, Maynard showed that if you assume this conjecture is true, then the gap plummets to just 12. A year later, the Polymath Group proved that if you assume an even stronger version of this conjecture, the gap drops all the way down to six. But without assuming anything, 246 still stands. Let me ask you, do you think we're gonna solve the twin Prime conjecture?
</details>

**[嘉宾]**: 我完全确信人类最终会解决孪生素数猜想。当你问我关于这类重大的、举世闻名的数学难题，比如孪生素数猜想或是黎曼猜想之类的问题时，通常我用来绕过这个问题的一种方式是：假设你在时间轴上是随机分布的，那么你大概可以预期自己刚好处于猜想从被提出到被解决的“中点”附近。因此，如果你没有任何别的信息，一个合理的猜测就是：一个难题目前未被解决的时间有多长，它在未来保持悬而未决的时间大概就会有多长。但这显然不适用于孪生素数猜想，因为我们并不清楚它究竟——

<details>
<summary>Original English</summary>

**[Speaker]**: I am totally convinced that humanity will eventually solve the twin prime conjecture. Often when I'm asked about some of these big famous problems like Twin Primes or Riemann or something like that, one way of kind of avoiding the question is that if you imagine you are randomly distributed in time, you'd expect to be sort of typically roughly halfway through when the conjectures been open for. So, an actual guess, if you have no other information, is to guess that a problem will be open for as long as it has been open for already. But obviously this doesn't work for twin primes, 'cause we don't know whether it's-
</details>

**[Derek]**: 确实。

<details>
<summary>Original English</summary>

**[Derek]**: Right.
</details>

**[嘉宾]**: （全场大笑）——它到底是125年历史了，还是说像有2000年那么古老。所以我认为去凭空猜测是很愚蠢的。但很显然它需要一个极其绝妙的大主意，并且也许，它也仅仅只需要一个绝妙的主意。

<details>
<summary>Original English</summary>

**[Speaker]**: (all laughing) - 125 years old or whether it's like 2000 years old. So, I think it's a fools game to guess, but it clearly needs a really big idea, but maybe it only needs one big idea.
</details>

**[Derek]**: 尽管如此，我们无法确切知道这一切是不可能的，这或许——仅仅是或许，已经是最好的结局。因为如果我们确定无疑地知道这一切绝无可能，那么我们在过去的一个世纪里可能就会错失绝大部分的这些发明创造和新方法论了。所以，有时候什么都不知道反倒是件好事。

<details>
<summary>Original English</summary>

**[Derek]**: Although maybe, just maybe, not knowing this with certainty is for the best. Because if we knew for sure that this was impossible, then we would've likely missed out on most of these inventions and new methods over the past century. So, sometimes it pays not to know everything.
</details>

**[Derek]**: 要知道，在开创这个频道之前，我曾经是一家辅导机构的教师，老实说，那是我在那时为止找到过的最好的一份工作。我能够成为那个可以给我的学生提供关键“大主意”的人，从而帮助他们茅塞顿开。想要最快地学会某样东西，最好的方式就是身边坐着一个早已懂行的人。只可惜，并非所有的学生都有机会得到那样的辅导。不过，这样的情况已经成为了过去式。我们的长期赞助商Brilliant，刚刚推出了Koji，它是一个革命性的个人导师，使得一对一学习面向所有人变得触手可及。Koji可以观察你所做的一切，并解答所有的疑问。他甚至能在屏幕上为你写写画画，就像一个真实坐在你旁边的人那样，帮你解释各种绝妙的“大主意”。他会提出启发性的问题，一步一步陪你解答难题，并且实时适应你的学习进度。你的口袋里，就装进了一个世界级的私人导师。从五年级一直到大学及以上，Koji可以协助你解决数学和编程学习上的方方面面。每门课程都由来自麻省理工、哈佛、斯坦福以及加州理工学院的专家倾力设计。它是你深度接触数学和编程，认真思考并享受乐趣的绝佳方式，尤其是对于正在放暑假的学生来说，它可以帮你保持头脑敏锐或者为下一学年提前打好基础。所以，点击下方链接免费开始体验Brilliant的导师功能吧，你还可以升级到Premium版本以获取全套辅导支持。现在，Brilliant为Veritasium的观众提供了年度Premium订阅独家八折优惠。只需前往 brilliant.org/veritasium，你可以扫描屏幕上的二维码或者点击描述栏中的链接。在这里我想感谢Brilliant赞助了这期视频，也感谢你们的观看。

<details>
<summary>Original English</summary>

**[Derek]**: You know, before I started this channel, I was a teacher at a tutoring company, and honestly, it was the best job I'd had up until that point. I could be the person who gave my students that one big idea that would help everything click. You know, the fastest way to learn something is to have someone next to you who already understands it. Unfortunately, many students don't have access to that kind of support. That is, until now, our long-term sponsor Brilliant, has just launched Koji, which is a revolutionary personal tutor that makes one-on-one learning accessible for everyone. Koji can see what you do and answer any questions. He can even draw onscreen to help explain those big ideas, just like a person sitting next to you. He asks guiding questions, walks you through problems step by step, and adapts to where you're at in real time. You get a world class personal tutor in your pocket. Koji can help you work through math and coding streams from grade five through college and beyond. Each course is designed by experts from places like MIT, Harvard, Stanford, and Caltech. It's a great way to get seriously engaged with math, coding, think hard and have fun, especially for students on summer break to stay sharp or get ahead for next year. So, click the link below to get started with Brilliant's tutor for free, and you can also upgrade to Premium to get full tutor support. Right now, Brilliant is giving Veritasium viewers a special 20% off an annual premium subscription. Just go to brilliant.org/veritasium. You can scan this QR code or click the link in the description. So, I wanna thank Brilliant for sponsoring this video and I wanna thank you for watching.
</details>