---
author: a16z
date: '2026-09-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qn1QDDBnTA0
speaker: a16z
tags:
  - spatial-intelligence
  - world-model
  - novel-view-synthesis
  - 3d-reconstruction
  - neural-rendering
title: 重构三维视觉智能：Atlas 空间世界模型与新视角预测的技术跃迁
summary: 本访谈深度探讨了新一代空间智能基础模型 Atlas 的核心架构与技术突破。团队分享了从 LLM 的‘预测下一个 Token’到视频模型的‘预测下一帧’，再到空间模型‘预测新视角’的范式演变，阐述了空间上下文、3D 相机位姿、少样本高质量重建、几何与外观解耦，以及向 4D 动态世界和‘AI 完备性’进化的前沿路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ben Mildenhall
  - Justin Johnson
companies_orgs: []
products_models:
  - Atlas
media_books: []
status: evergreen
---
### 空间智能与新视角预测的核心范式

**主持人**: 在通往空间智能的道路上，生成具有空间上下文和几何一致性的像素是一个极其艰难的突破。这正是 **Atlas** 所实现的飞跃。我们知道大语言模型（**LLM**）建立在“预测下一个 Token（Next-Token Prediction）”的基础之上；视频生成模型建立在“预测下一帧（Next-Frame Prediction）”的基础之上；而 Atlas 的本质是——**预测新视角（Novel View Prediction）**。在这个领域，人工智能可以为人类及其工作流程带来巨大的效率跃升，成本降低 50 倍甚至 100 倍。在第一部电影《**黑客帝国**》（The Matrix）中，有一个经典的尼奥后仰避弹镜头，当时制作团队为了那个特效搭建了由数百台摄像机组成的环形阵列、绿幕以及极其复杂的校准。

<details>
<summary>Original English</summary>

**Host**: In the journey toward spatial intelligence, creating pixels that are spatially contextualized and reasoned is a fundamentally difficult step, and that is what **Atlas** has achieved. As we know, Large Language Models (**LLMs**) are built on predicting the next token; video models are built on predicting the next frame. Atlas is fundamentally about **predicting novel views**. This is a real domain where AI can bring massive benefits to people and production pipelines, slashing costs by 50x or 100x. In the first movie of *The Matrix*, there is that famous bullet-time shot where Neo leans back. Back then, they required hundreds of physical cameras, green screens, and extremely expensive calibrations to pull that off.

</details>

**Justin Johnson**: 没错。而在 Atlas 的赋能下，我们现在仅仅依靠三台普通设备——比如架在三脚架上的三部 **iPhone**——就可以实现同样震撼的拍摄效果。完全不需要专门的摄影棚、绿幕或者昂贵的传感器校准。

<details>
<summary>Original English</summary>

**Justin Johnson**: Exactly. And with Atlas, we can achieve that with just three ordinary devices—say, three **iPhones** on tripods. No dedicated studio shooting, no green screens, and no expensive multi-camera calibration required.

</details>

**Ben Mildenhall**: 是的，比如有人投篮或者草莓掉入牛奶碗溅起水花的动态瞬间，从这三台 iPhone 拍摄的视频出发，我们就可以对整个场景进行任意视角的重构与重新构图。你可以让时间在某一瞬间静止，让虚拟摄像机在飞溅的牛奶水滴之间穿梭飞驰，获得这种时间仿佛凝固一般的惊艳画面。事实上，有时甚至只需要两台摄像机就足够了。

<details>
<summary>Original English</summary>

**Ben Mildenhall**: Yes, imagine capturing dynamic moments like someone throwing a ball into a hoop or a strawberry dropping into a bowl of milk with splashes. From just three iPhone video feeds, we can reframe and reconstruct the entire scene from any novel viewpoint. You can freeze time while having a virtual camera fly through the airborne milk splashes, creating that breathtaking frozen-time cinematic effect. In fact, in certain setups, we can even do it with just two cameras.

</details>

**主持人**: 你能用最直观、最精炼的语言概括一下 Atlas 究竟在做什么吗？也就是说，它的输入和输出分别是什么？

<details>
<summary>Original English</summary>

**Host**: Could you explain in the simplest, most intuitive terms what Atlas fundamentally does? What are the inputs and outputs of the model?

</details>

**Justin Johnson**: Atlas 最核心的底层原理就是对新视角的预测。这是我们观察到的一个根本性创新，极其迷人，在此之前没有任何模型真正做到过这一点。正如我们前面所说，大模型预测下一个 Token，视频模型预测下一帧，而 Atlas 则是给定一个场景的若干参考视角或描述，将其编码进我们所说的**空间上下文（Spatial Context）**中。这个空间上下文隐式且精确地刻画了真实三维物理世界。随后，你可以将虚拟摄像机放置在空间与时间中的任意位置，Atlas 就能准确推断并生成出该空间点和时间点所应呈现的真实视觉图像。

<details>
<summary>Original English</summary>

**Justin Johnson**: One of the fundamental principles of Atlas is the prediction of novel views. This is the core capability that we found completely fascinating and fundamentally new—no prior model operated this way. LLMs predict the next token, video models predict the next frame, whereas Atlas takes a set of views or descriptions of a scene and maps them into what we call a **spatial context**. This spatial context implicitly and faithfully represents the 3D physical world. You can then place a virtual camera at any arbitrary point in space and time, and Atlas understands and renders exactly what the world should look like from that precise pose.

</details>

---

### 空间几何一致性与视频生成模型的本质区别

**主持人**: 现在市面上有很多视频模型也宣称自己是“**世界模型**（World Models）”，或者能够生成多角度画面。Ben，你能更具体地解释一下 Atlas 与之前出现的各种多视角生成或视频模型相比，根本差异究竟在哪里吗？

<details>
<summary>Original English</summary>

**Host**: Ben, many video models nowadays claim the title of "world models" and claim to generate new camera angles. Could you explain more specifically how Atlas fundamentally differs from previous generative video models?

</details>

**Ben Mildenhall**: 关键就在于 Justin 刚才提到的**空间上下文**。很多视频生成模型之所以走红，是因为它们能够基于一张单图进行动态外推，或者在首尾两帧之间做插值。现在也有一些模型宣称可以接收 20 张、30 张甚至 50 张参考图片。但 Atlas 的根本特征在于：输入给它的每一帧图像都具有严格的**空间几何分布与三维相机位姿（3D Camera Pose）**。

在其他生成模型中，输入的图片只是一堆散落的视觉概念，模型会依据文本 Prompt 和启发式联想去“脑补”或臆造内容；而在 Atlas 中，每一张参考图像都被锚定在三维坐标系中。这意味着 Atlas 执行的是极高精度的物理几何重构。如果我们在房间的四个角落各拍摄一张照片输入模型，Atlas 会精确还原房间内所有物体的真实空间对应关系，而绝不会像传统生成模型那样在未知角落随意胡乱臆测。它忠实地重现物理真实。

<details>
<summary>Original English</summary>

**Ben Mildenhall**: The distinction lies in the spatial context Justin mentioned. Many video models gained popularity through image-to-video generation or interpolating between first and last frames. Some newer models accept 20, 30, or 50 reference images. But the defining trait of Atlas is that every input frame is grounded in a rigorous **spatial distribution with 3D camera poses**.

In conventional models, images are treated as loose visual cues that the model interprets freely based on text prompts. In Atlas, every image comes with precise camera positioning in 3D space. This enables high-accuracy metric reconstruction. If you take four photos from the four corners of a room and feed them into Atlas, it reconstructs an exact 3D replica of what exists, without hallucinating inconsistent objects or broken spatial relationships in unseen corners. It faithfully adheres to spatial reality.

</details>

**Justin Johnson**: 同时，这种空间能力在创意与生成领域也释放了无限可能。如果你输入两张视角相差很大的照片，传统的 3D 重建算法（如传统的 Structure-from-Motion 或经典 **NeRF**）往往会彻底失败，因为它们依赖密集且重叠的视差匹配；而 Atlas 作为一个生成式基础模型，不仅具备强先验知识来补全未见区域的合理纹理与几何，还能同时严格遵守已见视角的空间硬约束。

<details>
<summary>Original English</summary>

**Justin Johnson**: At the same time, this unlocks massive creative potential. If you feed in just two sparse, wide-baseline photos, classical 3D reconstruction pipelines (like traditional SfM or standard **NeRF**) would completely break down due to insufficient overlap. Atlas, as a generative spatial foundation model, uses its rich learned prior to hallucinate plausible structure in unobserved areas while remaining strictly anchored to the geometric constraints of the observed views.

</details>

---

### 少样本稀疏重建与极端视角泛化

**主持人**: 这非常令人兴奋。那么 Atlas 在稀疏视角（Sparse Views）下的表现究竟能达到什么极限？比如当我们只有极少量的照片时，它是如何做到既保持逼真度又维持全局几何一致性的？

<details>
<summary>Original English</summary>

**Host**: That is truly remarkable. What is the limit of Atlas's performance under extremely sparse views? When given only a handful of photos, how does it maintain photorealism while preserving global geometric consistency?

</details>

**Ben Mildenhall**: 经典的三维重建方法对输入有着严苛的要求：你需要拍摄几十上百张重叠度高达 80% 以上的照片，还要经过冗长的离线特征提取与光束法平差（Bundle Adjustment）。一旦视角稀疏，传统几何方法就会产生大量的几何伪影、黑洞或漂浮物。

而 Atlas 在训练过程中内化了海量三维物理世界的先验规律。当输入仅有一张、两张或三张照片时，模型能够依据物理常识推断出物体背面的形状、阴影的走向以及遮挡区域的深度结构。即便你将虚拟摄像机旋转 180 度绕到物体背后，它依然能渲染出结构完整、光影合理且无接缝的新视角画面。

<details>
<summary>Original English</summary>

**Ben Mildenhall**: Classical 3D reconstruction requires dozens or hundreds of densely captured photos with over 80% overlap, followed by heavy offline bundle adjustment. When views are sparse, traditional geometry-based methods fail catastrophically, producing floating floaters, severe artifacts, and broken surfaces.

Atlas has learned the structural and physical priors of the 3D world during large-scale pretraining. When given only one, two, or three sparse shots, it infers plausible back-surface geometry, consistent lighting, and occlusion relationships. Even if you orbit the camera 180 degrees behind an object, Atlas synthesizes a coherent, continuous, and visually compelling novel view.

</details>

**Justin Johnson**: 我们在训练中观察到一个非常清晰的 **Scaling Law（缩放定律）**：随着模型参数量的增大和高质量多视角空间训练数据规模的扩张，模型预测新视角的能力呈现出持续、单调的提升。它不仅能更好地保留细节纹理（如文字、反射高光和精细毛发），更重要的是，它对宏观空间几何关系的理解变得越来越稳固。

<details>
<summary>Original English</summary>

**Justin Johnson**: We observed a very clear **scaling law** throughout our training runs: as model capacity grows and the scale of high-quality multi-view spatial training data expands, novel view synthesis capabilities improve monotonically. The model preserves fine details—such as typography, specular reflections, and thin structures—while developing an increasingly robust grasp of macro-scale 3D geometry.

</details>

---

### 从静态空间到 4D 动态世界模型的跨越

**主持人**: 这是否意味着我们很快就能通过 Atlas 体验到真正的 **4D 视频**与完全可交互的世界？用户是否可以在生成的动态场景中自由走动？

<details>
<summary>Original English</summary>

**Host**: Does this mean we will soon experience true **4D video** and fully interactive worlds through Atlas? Will users be able to freely walk around dynamic scenes?

</details>

**Ben Mildenhall**: 4D 动态时空重建正是我们的核心演进路线之一。在现实世界中，一切都在发生变化——人会移动，水流会奔涌，光影会变幻。传统的静态 3D 只能捕捉固定的瞬间，而 4D 空间智能要求模型能够同时在时间轴（Dynamics）和空间轴（Novel Camera Views）上进行联合推理。

在训练 Atlas 时，我们处理了包含大量复杂动态变化的现实数据。为了获得纯粹的静态几何，模型必须学会将场景中的**动态物体与静态背景解耦**；反过来，当我们需要重现动态过程时，模型又必须学会预测动态物体的时空演化轨迹。目前的发布版本已经在静态几何与空间相机轨迹控制上达到了工业级可用性，而底层预训练模型中已经蕴含了丰富的 4D 动态先验。

<details>
<summary>Original English</summary>

**Ben Mildenhall**: 4D spatiotemporal modeling is a core milestone on our roadmap. In the real world, everything evolves—people move, water splashes, lighting changes. Static 3D only freezes a single instant, whereas 4D spatial intelligence requires joint reasoning across both the temporal axis and spatial camera trajectories.

When training Atlas on real-world datasets, the model learns to decouple dynamic foreground motions from static background geometry. This allows it to either isolate clean static environments or synthesize full 4D spatiotemporal trajectories. While our current release focuses heavily on metric static reconstruction and high-fidelity camera control, the underlying model already encodes profound 4D dynamic representations.

</details>

**Justin Johnson**: 我想强调的是，从纯学术研究到工业级落地的关键，在于**精细的可编辑性（Editability）与可控性（Controllability）**。过去学术界很多展示往往只是“玩具式 Demo”——你输入一段文本，生成一个粗糙的物体，但你无法精确控制它的尺寸、位置、相机路径以及时序同步。

对于专业级制作和工业应用而言，控制力就是一切。你必须允许创作者明确指定：“我需要这个特定人物在这一确切的 3D 坐标上执行该动作，同时虚拟摄像机以特定的焦距和运动曲线穿过场景。”在引入这种多维条件控制的同时，绝对不能牺牲画质和几何保真度。这就是 Atlas 在工程与算法设计上的核心护城河。

<details>
<summary>Original English</summary>

**Justin Johnson**: I want to emphasize that bridging academic research and industrial-grade deployment hinges entirely on **fine-grained editability and controllability**. In academia, many demos are essentially toys: you type a prompt, a mesh appears, but you have zero control over metric dimensions, camera extrinsics, or temporal synchronization.

In professional VFX and production pipelines, control is paramount. Creators need to specify exact 3D coordinates, exact asset placement, and exact focal lengths and camera trajectories without degrading rendering fidelity. Maintaining an uncompromisingly high quality bar while introducing multi-modal spatial control is the central engineering moat of Atlas.

</details>

---

### 新视角预测与 AI 完备性（AI-Completeness）的哲学思考

**主持人**: 这引发了一个非常深刻的思考。除了更快的推理速度、更高的分辨率之外，你们在空间智能的本质上看到了什么更宏大的图景？

<details>
<summary>Original English</summary>

**Host**: This touches upon a deep philosophical question. Beyond faster inference and higher resolution, what broader vision do you see regarding the fundamental nature of spatial intelligence?

</details>

**Justin Johnson**: 这把我们带回了智能的本质问题。真正的通用智能绝不仅仅是坐在终端前被动地生成文本或解释语言；它必须与三维物理空间发生交互，形成完整的视觉感知-行动闭环。

在计算机科学中，有一个概念叫做 **AI 完备性（AI-Completeness）**。在理论计算中，NP 完全问题（如 3-SAT）可以通过多项式时间归约来解决该复杂度类别下的任何问题；类似地，在人工智能领域，大语言模型将“预测下一个 Token”视为一种 AI 完备的基元任务——因为只要你能完美预测侦探小说最后一页的下一个 Token（“凶手是……”），或者完美预测证明黎曼猜想的下一个数学符号，你就实际上解决了通用智能的所有问题。

<details>
<summary>Original English</summary>

**Justin Johnson**: This brings us back to the fundamental nature of intelligence. True general intelligence cannot merely sit behind a screen parsing tokens; it must interact with the 3D physical world and close the perceptual-action loop.

In computer science, there is the concept of **AI-completeness**, analogous to NP-completeness in complexity theory where solving 3-SAT allows you to solve any NP problem via reduction. In NLP, predicting the next token is widely viewed as an AI-complete primitive: if a model can flawlessly predict the next token at the end of a mystery novel ("The killer was...") or predict the next mathematical symbol proving the Riemann Hypothesis, it has effectively mastered general intelligence.

</details>

**Ben Mildenhall**: 我们的核心信念是：**生成式新视角预测（Generative Novel View Prediction）同样是一个 AI 完备的基元任务**。

从生物进化史的角度来看，大自然为什么赋予了能够移动的动物以眼睛，却没有给静止生长的树木赋予眼睛？因为移动必然伴随着视角的持续更新。为了在移动中生存，生物必须在大脑中构建起周围三维世界的完整内部模型，准确预测新视角的空间几何、遮挡关系、物理规律与因果效应。

如果你拥有一个能够完美预测物理世界任意新视角的生成模型，你不仅能生成完美的视觉图像，更意味着该模型已经彻底掌握了三维世界的物理结构、光线传播、时空连续性乃至因果规律。因此，**预测下一个视角与预测下一个 Token 在智能的本质上具有同等的深远意义**。

<details>
<summary>Original English</summary>

**Ben Mildenhall**: We firmly believe that **generative novel view prediction is equally an AI-complete task**.

Look at it through the lens of evolutionary biology: why did nature bestow eyes upon animals that move, but not upon trees rooted in the ground? Because locomotion fundamentally necessitates the continuous processing of novel views. To navigate and survive, an organism must maintain a rich internal 3D model of reality, accurately anticipating occlusions, geometry, and causal physical dynamics from unseen perspectives.

If a generative model can flawlessly predict any novel view of the physical world, it inherently implies that the model has internalized 3D spatial geometry, optics, temporal coherence, and physical causality. Therefore, **predicting the next view is fundamentally just as profound as predicting the next token**.

</details>

**主持人**: 这是一个极其震撼且富有远见的视角。祝贺团队取得如此突破性的成果，Atlas 的发布无疑为空间智能和世界模型的未来树立了崭新的里程碑。非常感谢两位今天的深度分享！

<details>
<summary>Original English</summary>

**Host**: That is an extraordinarily profound and visionary perspective. Huge congratulations to the entire team on this monumental launch. The release of Atlas sets an entirely new benchmark for spatial intelligence and world models. Thank you both so much for sharing your insights today!

</details>