---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jebp4V0vh30
speaker: AI Engineer
tags:
  - hyper-personalization
  - agentic-site
  - real-time-inference
  - retrieval-augmented-generation
  - edge-computing
title: Agentic Sites：基于大模型实时重构的超个性化网站架构与实践
summary: Adobe 首席科学家 Carlos Sanchez 详细展示了 Agentic Sites 架构。该方案结合边缘交付与极速大模型推理（如 Cerebras 驱动的 Gemma 模型，达 2300 tokens/s），通过对全站构建 RAG 知识检索，并实时捕捉用户行为与搜索意图，实现秒级组装超个性化页面，颠覆传统千人一面的建站与营销自动化模式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Adobe
  - Cerebras
  - Google
products_models:
  - Adobe Experience Manager
  - Gemma
  - Promptfoo
media_books: []
status: evergreen
---
### 超个性化意图驱动：重塑传统网站的千人一面架构

在现代内容管理与数字营销体系中，传统的**千人一面**（One-size-fits-all: 向所有访问者提供相同内容与布局）模式正面临瓶颈。**Adobe** 旗下的内容管理产品 **Adobe Experience Manager**（AEM: 企业级内容与数字资产管理系统）团队正在研发一种名为 **Agility Sites**（或称 Agentic Sites）的全新建站范式，目标是打造**超个性化**（Hyper-personalized: 基于用户实时意图动态重构交互与呈现）的网站体验。

其底层核心逻辑在于全面转向**意图驱动**（Intent-driven: 以用户当前访问行为和潜在目标为导向）：系统实时追踪访客正在浏览什么、在寻找什么以及试图完成什么目标，进而在毫秒级时间内实时组装并定制页面内容。这不仅直接助力营销团队达成更高的用户参与度与商业转化率，更彻底颠覆了传统营销自动化中需要人工预先编排成千上万种页面变体（A/B Testing 变体）的繁琐流程。

<details>
<summary>Original English Source</summary>
Hello. Thank you for coming. I'm going to talk to you about Agility Sites, how we call it as building hyper-personalized websites. I'm not going to just talk about it; I'm going to show you what we're building. I've been working on this project for a bit now, and we'll try to show you what is possible today with AI.

I work at Adobe. I'm a principal scientist at a product that not many people know, Adobe Experience Manager, content management. We run a lot of website properties for big brands, and my background is in open source, contributing to a lot of foundations and projects.

What are Agility Sites, and how are we building this thing? We're looking for sites that are looking at what intent the user browsing has. What is the user doing? What is the user trying to achieve? And the end goal is to personalize these pages for the current user browsing, so that eventually this drives higher engagement or conversions, whatever the marketing teams want to achieve. And these pages are personalized in real time based on the user that is accessing the site and what the user is doing.

We tried to solve the problem where one size fits all. We want hyper-personalized experiences. Also, we want to help our customers to do more automatic authoring—so not having to create thousands of different variations of the site, but use AI for this and then do these multiple layers of personalization.
</details>

### 基于边缘交付与 RAG 架构的动态区块组装机制

在系统工程落地层面，为了确保内容既具备动态生成的灵活性，又严格符合品牌规范，系统严禁让大模型全权天马行空地从零生成整个网页。对于品牌营销而言，任何偏离品牌规范的**模型幻觉**（Hallucination: 大语言模型生成不符合事实或未定义内容）都是不可接受的。因此，系统采用了基于**富内容区块**（Rich Content Blocks: 模块化的 UI 结构与预定义组件）与**边缘交付服务**（Edge Delivery Services: 将静态资产与预编译组件分发至全球 CDN 边缘节点）的架构。

后端系统将整个网站的存量内容构建为一套完整的 **RAG 知识库**（Retrieval-Augmented Generation: 检索增强生成），所有大模型生成的文字与区块推荐均被严格**锚定**（Grounded: 生成内容基于确凿的私域知识库数据）在现有站点内容之上。大模型的核心职责在于：根据访客画像与上下文意图，智能决策应该调度哪些预定义区块、确定区块的最佳排列顺序，并实时生成个性化的 Hero 焦点图文案、博客流、商品推荐以及**行动号召**（Call to Action, CTA: 引导用户产生点击或购买行为的交互按钮）按钮。

<details>
<summary>Original English Source</summary>
The stack we're using is AEM delivery. This is the part of the product where all the content is on the edge, and then we have a back-end service that powers this experience with different LLM providers and LLM services. We use Cerebras for fast inference, or we can use Bedrock and a bunch of others. I'll be showing Cerebras today, and you will see the reason why.

The engine that is personalizing these bits is using the rich content and blocks. So different blocks on the site are customized depending on what the user persona is. We don't want the whole site to be generated. If you talk to marketing people, they have very strict brand guidelines. You don't want to just come up with hallucinations there. So what is personalized is different sections of the site, and we use the whole site as a corpus. We built a RAG from the whole site, so what is generated is grounded on the existing site.

How the architecture looks like: it's a dynamic front end with some blocks. With edge delivery services, basically you compose these blocks, and they are updated in real time through AI. The browser captures the signals from the user, and the back end is basically calling the LLM and doing some reasoning using the RAG that is built on the site to do the generation. You have the vector database, the inference machinery, and AEM at the edge is serving the pages and the static content.
</details>

### 极速推理评测：Promptfoo 与 Cerebras 在毫秒级响应中的决胜点

在动态网页渲染场景下，生成延迟对用户体验和转化率具有生死攸关的影响。业界公认网站加载速度越快，转化率越高。为了保证个性化页面能够在 **1 到 2 秒** 内完整呈现，团队引入了持续评估工具 **Promptfoo**（Promptfoo: 开源的大模型 Prompt、模型性能与输出质量自动化评测框架），针对不同网站在不同模型与云服务商（涵盖本地模型及各类 OpenAI 兼容接口）上的表现，在**准确率**（Accuracy）与**生成速度**（Speed）之间进行多维度量化评估。

评测结果表明，这一场景并不需要参数量极其庞大的通用基础大模型，因为任务本质是文本定制与区块排版调度。在 15 个测试 Prompt 的基准评估中，部署在 **Cerebras** 专用芯片上的 **Gemma** 模型展现了惊人的性能：在实际端到端页面生成测试中，包含往返大模型请求的总耗时仅为 **1 秒左右**，推理吞吐量高达 **2,200 至 2,300 tokens/s**，平均页面生成耗时 1.1 秒；相比之下，其他常规服务商的生成延迟普遍在 4.6 秒以上。这种超高速推理能力使得实时会话级页面重构在生产环境中真正具备了工程可行性。

<details>
<summary>Original English Source</summary>
The back end does the evaluation of the models and the providers, and one thing we realized is that this is very dependent on the site. We have a bunch of prompts, and we run them across a huge variety of models and providers. Then we look at the accuracy, we look at the speed. This depends highly on what type of site it is—how big it is, what area the site is targeting, what type of commerce it is, and so on. We run this evaluation continuously using Promptfoo.

Promptfoo allows you to evaluate prompts against multiple models and providers, including local models and OpenAI-compatible providers. We look for two things: accuracy (typically what people look for) and speed. We don't want the site generation to take more than 1 or 2 seconds, because it's proven that the faster the site, the more conversions it generates and the better the user experience.

Different sites may have different requirements. For this example site, we have 15 prompts. At the top, you can see with Cerebras on the Gemma model that was announced last week, we can get an average latency of 1.1 seconds generating a page. You can compare that to the second one, which is 4.6 seconds, so the difference is huge. That's why we use Cerebras for this use case. Different providers and models have different speeds. Sometimes models don't need to be perfect, but they're good enough if they're fast enough. You don't need a huge LLM to do this sort of work because you are generating text and deciding where to put blocks and organize the website.
</details>

### 单人受众范式验证：搜索直达、实时对比与多模态扩展

在实际演示中，Adobe 展示了面向**单人受众**（Audience of One: 针对每个个体的独特偏好与上下文提供完全定制化的数字体验）的具体交互场景。在搭建的咖啡机示例网站中，前端系统实时收集用户的停留时长与浏览路径，将用户归类至特定意图群组（如“探索型用户”）。系统可以提前预加载专属的“为你推荐”（For You）聚合页面；当用户发起自然语言搜索（例如“寻找适合露营时冲泡咖啡的机器”）时，系统立刻在 1 秒内生成定制页面——不仅动态生成贴合露营场景的文案（“露营不意味着向咖啡妥协”），还自动筛选出最适合户外携带的便携机型。

此外，基于该架构打造的 **OfOneLabs** 工具已实现全自动化的站点升级能力：用户只需输入任意既有网站的 URL，系统即可在不到一小时内将其转换为具备智能搜索、即时生成横向**对比页面**（Side-by-side Comparison: 针对用户犹疑的两款产品或会议自动生成并列参数及优劣势分析）的 Agentic 站点。更进一步，随着如轻量级多模态生成模型与端侧语音交互的发展，未来的个性化站点不仅能实时生成贴合品牌的图像素材，更可无缝投射至家庭客厅电视等跨终端设备上，实现全语音交互、无屏设备依赖的下一代自适应 Web 体验。

<details>
<summary>Original English Source</summary>
This browsing and the queries are being recorded—these are the metrics and data we gather from the user, fed into the LLM to personalize the site: hero cards, products, blog feeds, navigation, and CTA buttons. We create a "For You" page, which is a recommendation. You could pre-generate this as the user browses your site, gathering signals.

When the user runs a query, a dynamic personalized page is shown. Queries are grouped into personas or intent types. Marketers can decide the groups and strategies in natural language, and AI chooses the blocks and suggestions. You could also do media with lightweight fast models generating images on the fly, depending on brand quality.

In the demo with the coffee machinery site, the debugging tool shows signals: the user is bucketed into the "exploring" category with visited pages and dwell time. When I query "looking for a coffee machine to prepare coffee while camping", the site is generated with customized text ("Camping shouldn't mean compromising on your routine") and camping-tailored products. In debug mode, total generation time was around 1.1s, with LLM roundtrip at 1 second reaching 2,200 to 2,300 tokens per second on Cerebras Gemma.

We also built OfOneLabs: enter any URL, and in less than an hour you have an agentic site. I did this with the AI engineering site, allowing European AI conference searches or generating side-by-side conference comparisons on the fly. Looking forward, this "Audience of One" paradigm extends beyond browsers: you could ask your Google assistant to buy a machine, and an absolutely personalized interface renders immediately on your living room Google TV. It is now possible, it will only get faster and cheaper, and intent-driven dynamic page assembly will define the future of personalization.
</details>