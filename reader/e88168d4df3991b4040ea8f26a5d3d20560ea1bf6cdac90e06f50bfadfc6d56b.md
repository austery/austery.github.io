---
author: AI Engineer
date: '2026-11-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=cWrYEBlWpcY
speaker: AI Engineer
tags:
  - bayesian-optimization
  - llm-serving
  - hyperparameter-tuning
  - inference-optimization
title: 基于贝叶斯优化的 VLM 推理服务配置自动调优 Agent 演示
summary: Rohan 演示了一款新构建的优化 Agent。该 Agent 基于 Optuna 运行贝叶斯优化，旨在自动化寻找 VLM 推理服务的最佳配置与参数配方，以减少人工调优耗时。演示展示了运行脚本 tuner.py 的方法及评估报告：在 GPT OSS 120B 上实现了 17.5% 的生成 token 吞吐提升，在 DeepSeek R1 Distill 模型上使吞吐翻倍并将 ITL 降低近半。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Rohan
companies_orgs:
  - DigitalOcean
products_models:
  - Optuna
  - GPT OSS 120B
  - DeepSeek R1 Distill
media_books: []
status: evergreen
---
### 优化 Agent 的目标与贝叶斯优化机制

好的，大家好。我叫 Rohan，今天为大家简要演示我们最近构建的优化 Agent。首先简要介绍该 Agent 的目的和目标，随后我会进入简短演示，并展示我们刚完成的一次历史运行结果。

<details>
<summary>Original English</summary>
All right. Hello everyone. So, my name is Rohan and this is a quick demo on the optimization agent that what has been recently built. So, a quick intro into what the purpose is and what the goal is of this agent and then I'll get into a brief demo and results that from a previous run that we just did.
</details>

我们这里的目标是构建一个 Agent，帮助为任意给定模型找到最佳的 VLM 服务配置。

<details>
<summary>Original English</summary>
So, what the goal is here is to build an agent that helps find the best VLM serving config for any given model.
</details>

其目的是减少手动寻找最佳配置和 VLM 服务配方所需的时间。如果我们能将其自动化，让它在后台运行，并让 Agent 更快地找到配方和优化参数，就能节省大量时间。这就是该 Agent 的目标。接下来进一步介绍该 Agent 具体是如何运作的。

<details>
<summary>Original English</summary>
The purpose is to reduce the time it takes to manually find the best configs and the VLM serving recipe and if we can automate this and have it run in the background and have the agent find the recipes and the optimized parameters faster then it will save a lot of time. So, that's the goal of the agent and a little bit more into how the agent actually does this.
</details>

该 Agent 采用的策略称为贝叶斯优化（Bayesian optimization）。贝叶斯优化是一种用于在任意给定场景中寻找最优数值的技术。在我们这个场景中，就是寻找这些 VLM 配方中的最优数值。

<details>
<summary>Original English</summary>
So, the strategy that the agent uses is called Bayesian optimization and Bayesian optimization is a technique that's used to find the most optimal numbers in any given situation. So, in our situation it's to find the optimal numbers in these VLM recipe.
</details>

它通过数学步骤从本质上缩小搜索空间。通过缩小搜索空间，大幅减少了在运行过程中寻找该配方优化数值所需的时间。贝叶斯优化（BO）是所采用的策略，而 Optuna 则是在搜索循环中运用该策略的工具。Optuna 使用贝叶斯优化：它接收当前配方，即初始配方，贝叶斯优化在此基础上运行，经过多次迭代或多次试验（trials），最终找到优化后的配方。Optuna 基本上在每次试验后获取每个配方，对其进行评估，获得一个分数，运用策略来修改和改进配方，然后在搜索循环中重新运行，直到试验完成。

<details>
<summary>Original English</summary>
It uses mathematical steps that essentially minimizes the search space. So, by minimizing the search space it reduces a lot of the time that it takes in finding the optimized numbers in this recipe during the run. So, BO Bayesian optimization is a strategy that is used but Optuna is the tool that uses a strategy in the search loop. So, Optuna uses Bayesian optimization. It feeds it the current recipe, the starting recipe. Bayesian optimization runs on that and over many iterations or many trials it eventually finds the optimized recipe and Optuna basically takes each recipe after every trial, assesses it, gets a score, uses a strategy to change the recipe, improve and then it reruns it within the uh search loop um until the trials is done.
</details>

### 配置初始配方与运行调优脚本

接下来我们看看具体是如何操作的。目前在一个 Droplet（云服务器）中，例如这个 Droplet 加载了 GPT OSS 120B 模型。

<details>
<summary>Original English</summary>
So let's go a little bit into how we do this. So um currently in a droplet here and this droplet for example has GPT OSS 120B model uh loaded up.
</details>

我们可以查看当前的配方。这里可以看到我们正在对其进行测试的四种机制（regimes）：包括 chat short、chat long、rag 和 batch classify。它们各自有输入的一组 ISL 和 OSL token。所有这些都可以根据我们想要观察的内容进行修改。但大体上，这就是你在下载模型权重时获得的初始配置、初始配方。

<details>
<summary>Original English</summary>
So what we can do is uh we can look at the current um recipe. So what we see here is four regimes, right? That we're testing it on. So there's chat short, there's chat long, there's rag and batch classify. Uh they have their own set of ISO OSL tokens that we're feeding it through. Uh all these um can be changed depending on what uh we want to see. But essentially this is the starting config, starting recipe that you would get when you download the weights of the model.
</details>

继续往下，一旦你在 Droplet 中下载好模型并准备运行此 Agent，就可以粘贴进这条命令。该命令大体上说明了权重来源、激活虚拟环境，并运行名为 `tuner.py` 的脚本。这个脚本基本上需要你指定几项内容：你需要给它指定研究名称（name of the study）；你需要告诉它初始 YAML 文件，也就是我们刚才在上方看到的；你需要告诉它运行所在的硬件；以及你希望执行的试验次数（number of trials）。在这个示例中是 24 次。稍后我还会简要展示另一个包含 9 次试验的历史运行示例。

<details>
<summary>Original English</summary>
Um so moving on, once you have the model downloaded in your droplet and you are ready to run this agent, you paste in this command uh which essentially tells you you know where the where where the weights are coming from, um activate a virtual environment and have um uh or not have but run the script called tuner.py. Uh this script essentially tells you or it it has a couple of things you have to tell it. So you you want to give it the name of the study. You want to tell it the starting YAML file which we just saw above here. You want to tell it the hardware that it's running on and you want to tell it the number of trials that you want. So uh in this example we have 24. Um briefly I'll show you another example of a past run that was run uh that had only nine trials. So
</details>

总之，这就是所执行的命令。通常这些命令需要运行几个小时。对于 GPT OSS，我想大约花费了四到五个小时；对于另一个模型，也花了几小时。

<details>
<summary>Original English</summary>
um anyway uh this is the command that's that's run. Uh typically these commands take um a couple hours to run. I think for the GPT OSS it took about four or five hours and then for the other model it took a couple of hours as well. So we can go
</details>

### 测试报告与优化效果评估

我们可以进入 Agent 完成工作后生成的 HTML 报告。这份报告针对我提到的 GPT-OSS 模型。我们在 HTML 报告中可以看到总共多少次试验中哪一次试验是最佳试验。在这个案例中，总共进行了 50 次试验。

<details>
<summary>Original English</summary>
into the HTML report that's generated after the uh agent finishes its work. So this one is for the GPT-OSS model that I mentioned. Uh what what we see in the HTML report is which trial number was the best trial out of the total of how many trials. So in this case it was 50 trials.
</details>

在运行结束时，你会获得一份优化后的 YAML 文件，其中包含了我们目前在 VLM 服务配方中关注的所有数值。在这个案例中，Agent 发现 256 是优化后的数值，诸如此类。而它衡量准确性（性能指标）的方式是生成的有效吞吐（goodput）token 数量。总体而言，相比初始配置，我们发现生成的 token 数量提升了 17.5%。

<details>
<summary>Original English</summary>
Uh you get so at the end of the run you get an optimized YAML file which includes all the numbers that we currently look for in the BLM serving recipe. So in this case we found or the agent found that 256 was the optimized number so on and so forth. And the way that it's getting the accuracy is the amount of good put tokens that's being generated. So overall we found that from the first config we had an improvement of 17.5% in terms of tokens generated.
</details>

正如我所提到的，这份是针对 GPT-OSS 的。我们这里还有另一份 HTML 报告，针对的是 DeepSeek R1 Distill 模型。在这里我们运行了 9 次试验，其中第 9 次试验效果最好。我们发现 token 吞吐量翻了一倍，且 ITL 改善了近一半，也就是说 ITL 降低了近一半。

<details>
<summary>Original English</summary>
And this one as I mentioned is for GPT-OSS. We have another HTML report here which is for the DeepSeek R1 Distill model. In here we found that or in here we had nine trials that was run and out of the nine the ninth one was the best. Uh we found that token throughput doubled and ITL was improved by almost half aka it was reduced by almost half.
</details>

以上就是关于运行命令以及输出样貌的快速介绍与简要演示。总体而言，你最终会得到一份说明各次试验表现的 HTML 报告，以及一份包含优化配方的 YAML 文件。希望这些内容对大家有所帮助，谢谢。

<details>
<summary>Original English</summary>
So this is a quick intro and brief demo on the commands you run and what the output looks like. In in in general you get a HTML report that tells you um how each trial went and then you also get um a YAML file that has the optimized recipe at the end of the day. So hopefully that was helpful. Thank you.
</details>