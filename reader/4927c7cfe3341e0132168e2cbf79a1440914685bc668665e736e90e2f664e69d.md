---
layout: post.njk
source: https://blog.qiaomu.ai/gpt-image-2-6-prompting-guide
web_feed:
  articleId: cmw46l4ry001t9eyet72hgmg1
  feedSourceId: cmoynk2ty0000yeud307bv9ji
  guid: https://blog.qiaomu.ai/gpt-image-2-6-prompting-guide
  sourceUrl: https://blog.qiaomu.ai/gpt-image-2-6-prompting-guide
speaker: 向阳乔木
title: GPT Image 2.6 提示词完全指南：从生图到改图，27 个官方案例拆解 · 乔木博客
date: '2026-11-05'
summary: 本文详细介绍了 GPT Image 2.6 的提示词使用指南，涵盖了从生图到修改的 27 个官方案例拆解。指南重点讲解了 new 参数 complexity（控制模型规划深度）、SVG/GIF 输出、markup 参数（用于编辑时圈定修改区域）以及 Flare 和 Sunburst 两个模型的选型逻辑。文章提供了撰写提示词的 8 条原则，包括先定义结果、描述可见细节、精确文字加引号等，并以 27 个案例展示了如何针对不同需求（如生图、改图、SVG 输出、人像写实、信息图、广告图、产品抠图等）进行提示词的结构化编写和参数调优，并给出了从旧模型迁移到 2.6 的六步流程。
area: tech-engineering
category: ai-application
tags:
  - gpt-image-2-6
  - image-prompting
  - ai-tooling
  - image-generation
  - image-editing
people:
  - 向阳乔木
companies_orgs:
  - OpenAI
products_models:
  - GPT Image 2.6
  - gpt-image-2.6-flare
  - gpt-image-2.6-sunburst
media_books: []
draft: true
status: evergreen
---

GPT Image 2.6 提示词完全指南：从生图到改图，27 个官方案例拆解 · 乔木博客

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# GPT Image 2.6 提示词完全指南：从生图到改图，27 个官方案例拆解

AI教程

·

2026年11月5日

·

76 次阅读

·

约 53 分钟

© 2026

·

向阳乔木

同一句提示词：“一支足球队在体育场里庆祝夺冠，纸雕风格”。

交给 GPT Image 2.6 Sunburst 跑三次，只改一个参数 complexity。

low 档把 CHAMPIONS 横幅挂在最前面，挡住了球员

medium 档给奖杯加了月桂花环、球衣上多了队徽

high 档把横幅挪进看台，前景完整留给球员和蓝色纸质球衣的褶皱。

提示词一字未改，构图却从“摆满元素”变成了“有主次”。

complexity 是 OpenAI 在 GPT Image 2.6 里新加的参数，控制模型动笔前“想多久”。

同一次更新还加入了 SVG 和 GIF 输出、用红圈圈出修改位置的 markup 参数。

OpenAI 开发者文档最近更新了《Image prompting》指南，把 2.6 的选型、参数、迁移流程、8 条提示词原则和 20 多个生图、改图案例全部摊开，每个案例都附了 Flare（火焰） 和 Sunburst （日冕）两个模型的实际输出。

下文按原指南顺序整理，全部示例图都保留.

每个案例的提示词按原文结构与要素重写成可直接复用的英文版本，并配中文说明。

> 原文链接：OpenAI Image prompting guide。

## 两个模型：Flare 求快，Sunburst 求细

GPT Image 2.6 分成两个型号：

gpt-image-2.6-flare：小模型，适合响应速度最重要的场景。

gpt-image-2.6-sunburst：基础模型，适合对细节、版式或编辑精度要求高的场景。

两者都支持生成、编辑和透明背景。

选型逻辑很朴素：看重速度就从 Flare 起步，画面对细节、排版、改图准确度要求高就从 Sunburst 起步。

已有项目迁移，官方给了一张对照表：

现在的情况

先测哪个

重点看什么

GPT Image 2 效果已经够用，或在用 2.5 Flare

gpt-image-2.6-flare

现有提示词下的质量和响应时间

GPT Image 2 搞不定复杂任务，或在用 2.5 Sunburst

gpt-image-2.6-sunburst

决定图能不能用的那些细节

还有一条省钱建议：如果 Sunburst 达标，拿同样提示词、参考图、尺寸和质量设置再跑一遍 Flare，在自己的真实业务上对比效果和耗时。

小模型够用，就没必要为大模型多付等待时间。

## 参数表：quality 管画得多细，complexity 管想得多深

API 参数和提示词分开设置，提示词只负责描述画面。

参数

GPT Image 2.6 的取值

model

gpt-image-2.6-flare 或 gpt-image-2.6-sunburst

quality

能渲染多少视觉细节，比如纹理、小字。auto、low、medium、high、xhigh、max

complexity

2.6 新增。 渲染前规划多少。low、medium、high，不填时两个模型都默认 high

size

auto 或支持的尺寸，如 1024x1024（方图）、1536x1024（横图）、1024x1536（竖图）

background

auto、opaque、transparent。透明 PNG、WebP 要解码检查 alpha 通道，SVG 也支持透明

output_format

png、jpeg、webp；生成任务新增 svg 和 gif。只有 JPEG、WebP 支持 output_compression

markup

新增。 编辑时传入透明 PNG 标注层，像素尺寸须与第一张输入图一致

两个参数容易混。

打个比方，quality 像画笔的精细程度，决定小字和纹理能不能画清楚。

complexity 像动笔前打草稿的时间，决定东西摆在哪、谁挡谁。

所以官方的调参顺序是：

复杂版式先用默认 complexity，看标签和相互关联的物体放得对不对。

对比 complexity 档位时，quality 保持不变。

版式对了但小字看不清，就固定 complexity，再比较不同 quality。

几条限制：

自定义尺寸长宽都必须是 16 的倍数，宽高比在 1:3 到 3:1 之间。横版幻灯片示例用的是 1536x864。

编辑图片时不要传 input_fidelity。

GPT Image 2.6 不支持 reasoning.summary。

## 迁移六步：一次只动一个变量

从旧模型迁到 2.6，官方给的流程有像做 A/B 实验：

存一份基线。 收集有代表性的提示词、参考图和当前模型的输出，难改的图、精确文字、产品几何形状、透明素材都要覆盖到。

测对应的模型。 2.5 Flare 先试 2.6 Flare，2.5 Sunburst 先试 2.6 Sunburst，GPT Image 2 用户看上面的对照表。

第一轮对比保持一致。 提示词、参考图、尺寸、质量、输出格式全部不变，complexity 留默认。

逐项检查结果。 文字、版式、人物身份，以及编辑后应该保留的细节。连续编辑要检查每一步的中间结果，不能只看最终图。

一次只调一个参数。 要么动 quality，要么动 complexity，别同时动。每个请求重复几次，统计达标率和耗时。

按业务分批上线。 先切一小部分流量，跟踪响应时间、失败率、重试次数和每张被采纳图片的成本，再扩大范围。

从 GPT Image 1 或 1.5 迁移的团队，还要查对应模型的参考页确认参数差异和停用日期：GPT Image 1.5 计划在 2026 年 12 月 1 日停用，GPT Image 1 已在 2026 年 10 月 23 日停用。

另有一条提醒：如果某块区域必须像素级不变，就把改好的部分合成回原图，别指望模型一个像素都不动。

## 写提示词的 8 条原则

这一节是整份指南的骨架，后面所有案例都在反复应用这 8 条。

1．先定义结果。

写清主体和用途（产品图、广告、示意图），说明构图、画幅和摆放要求。复杂需求可以拆成“场景、主体、细节、约束”几个带标签的小节。

2．选一种好维护的格式。

短句、段落、类 JSON 结构、指令、标签都能表达同样的意图，挑最容易读、最容易改的一种就行，不需要什么特殊语法。

3．描述看得见的细节。

写材质、光线、颜色和画面媒介。要照片感就明确写“photorealistic（写实）”或“real photograph（真实照片）”，并描述取景和纹理。相机参数只是外观提示，模型不会真的做物理模拟。广角、电影感、弱光、雨夜、霓虹这类场景，要写出尺度、氛围和颜色，光靠“氛围感”之类的情绪词不够。

4．把人和动作说具体。

写身体取景、相对大小、视线方向和与物体的互动。

官方举的例子：“full body visible, feet included”（全身入镜，包括脚），“looking down at the open book”（低头看着摊开的书），“hands naturally gripping the handlebars”（双手自然握住车把）。

5．精确文字要加引号。

必须出现的文字放在引号里，说明位置和字体。生僻词或品牌名必要时逐个字母拼出来。要求“不要多余文字”，生成后检查拼写和清晰度。小字、密集信息或多种字体，对比 medium 和 high 两档质量。

6．把“改什么”和“保留什么”分开写。

编辑时写“只改 X”，再列出要保留的东西：人物身份、几何形状、版式、光线、标签。同时写明排除项，比如不要多余文字、logo、水印。精细的局部修改，还要点名饱和度、对比度、箭头、机位和周边物体都不能变。

7．给每张参考图分配角色。

按编号说明每张图的用途：主体、风格、服装还是背景，再讲清楚它们怎么组合、哪个元素挪到哪里。

8．有节奏地迭代。

把上一轮输出作为下一轮的输入，每次只提一个修改，并重复强调需要保留的内容。“same style as before”这类说法可以延续上下文，但结果开始跑偏时，要把关键约束重新写一遍。先对比结果，再决定加不加新指令。

下面的案例大多不设置 complexity，用的是默认值。

官方也提醒，这些提示词要根据自己的图片和需求调整。

## 生成篇：12 个案例

除了 complexity 对比，每个案例都放了 Flare 和 Sunburst 两张输出，前一张是 Flare，后一张是 Sunburst。

### 案例 1：complexity 对比，开放式提示词收益最大

提示词只给场景和材质，奖杯、队服、文字全部留给模型决定。

设置：只用 Sunburst，每档一张，size="1024x1536"、quality="medium"、PNG。

```
<code class="language-text">A premium handcrafted illustration in layered paper-cut style: a football team celebrating a championship win inside a packed stadium.</code>
```

三档的结果见文章开头。low 档皇冠奖杯加前景横幅；medium 档加了月桂花环和队徽，横幅仍挡在队伍前面；high 档把 CHAMPIONS 标语移到看台，前景留给球员。

适用边界：版式、文字、风格都已经写死的提示词，调高 complexity 可能看不出差别。只改一个细节的定点编辑，建议从 low 开始，确认周边细节没被动过。

### 案例 2：直接输出 SVG 矢量 logo

想要一个能缩放、能改路径换颜色的 logo，就把案例 7 的 Field & Flour 面包店 logo 提示词发到 POST /v1/images/generations，设置 output_format="svg"、n=1。

SVG 同样支持 background="transparent"，标志周围会透出底下的颜色。

注意事项：不要传 stream、partial_images、output_compression 和 prompt_rewriter；返回的 data[0].b64_json 做 base64 解码后，存成 .svg 文件。

Flare 画了一个金色面包，下面两行奶油色字标；Sunburst 画的是冒着热气的面包夹在麦穗中间，下面是字标和擀面杖。

### 案例 3：生成循环 GIF

循环动画的关键是给主体一个起始姿势，让它最后回到原位，同时说明镜头动不动。

设置：POST /v1/images/generations，output_format="gif"，gpt-image-2.6-sunburst，size="512x512"，quality="high"，complexity 默认 high。frame_count=9、frame_duration_ms=200，合起来是 1.8 秒一圈。

```
<code class="language-text">At dusk in a snowy pine forest, a small monkey in an olive-green hooded coat stands in front of a warmly lit wooden cabin. It holds a glowing amber paper lantern at chest height. Slowly it raises the lantern, looks up, blinks, and then lowers the lantern back to the exact starting pose. The lantern stays in its hands the whole time and the camera does not move. The motion should loop seamlessly.</code>
```

GIF 的更多限制见官方生图指南中的“GIF settings and limits”一节。

### 案例 4：写实人像，靠描述照片本身

描述一张照片，就写主体、取景、光线和质感。这个案例要求抓拍构图，并明确排除重度修图。设置：1024x1536，quality="medium"。

```
<code class="language-text">A photorealistic candid photograph of an elderly sailor on a small fishing boat. Weathered, sun-worn skin with visible wrinkles and pores; a few faded traditional sailor tattoos on his forearms. He is calmly fixing a fishing net while his dog sits close by on the deck. Shot like 35mm film: medium close-up, eye level, 50mm lens. Soft coastal daylight, shallow depth of field, light film grain, natural color balance. The image should feel honest and unposed, with real skin texture, worn materials and everyday details. No glamorization and no heavy retouching.</code>
```

最后一句“不美化、不重度修图”很关键。模型默认倾向把人修得光滑好看，写实场景要主动压住这个倾向。

### 案例 5：用信息图讲清一个流程

写清楚要讲的流程、给谁看、要传达哪些信息。

示意图要检查标签和事实关系，光看好不好看不够。设置：1024x1536，medium。

```
<code class="language-text">Make a detailed infographic showing how an automatic coffee machine (Jura-style) works and how everything flows through it: from the bean hopper to the grinder, the dosing scale, the water tank, the boiler and onward. The goal is to understand the flow both technically and visually.</code>
```

这条提示词很口语，像跟设计师随口交代需求。这也印证了原则 2：格式不重要，意图清楚就行。

### 案例 6：广告图里的精确文字

把必须出现的文案加引号，并说明出现几次。写清受众和视觉方向，别塞无关指令。设置：1024x1536，medium。

```
<code class="language-text">A culturally cool fashion ad for Thread, a hip young streetwear brand. A group of friends hanging out together, with the tagline "Yours to Create." Make it a polished campaign image for a youth streetwear audience: stylish, contemporary, energetic and tasteful. Clean composition, strong color direction, natural poses, premium fashion-photography feel. Render the tagline exactly once, clear and legible, built into the ad layout. No other text, no watermarks, no unrelated logos.</code>
```

### 案例 7：可复用的品牌 logo

描述品牌，以及定义这个标志的形状。要求剪影在小标签和大招牌上都能一眼认出。

```
<code class="language-text">Design an original, non-infringing logo for Field & Flour, a neighborhood bakery. The feel should be warm, simple and timeless. Use clean, vector-like shapes, a strong silhouette and balanced negative space. Favor simplicity over detail so it reads well both tiny and large. Flat design, minimal strokes, no gradients unless truly needed. Fully transparent background: a single centered logo with generous padding and clean alpha edges; no solid backdrop, no scenery, no checkerboard, no watermark.</code>
```

设置：需要能放到任意背景上的位图 logo，用 output_format="png" 加 background="transparent"。两个模型都用 1024x1536、quality="medium"、n=1，要更多变体就调大 n。

Flare 是面包压在弧形田垄上，配上下排列的字标；Sunburst 是金色麦穗环绕面包。

### 案例 8：调用历史和现实世界知识

写出地点和日期就能设定一个历史场景，模型会自己推断背景细节。

但服装、布景、周边环境的历史准确性要人工核对。设置：1024x1536，medium。

```
<code class="language-text">A realistic outdoor crowd scene in Bethel, New York, on August 16, 1969. Photorealistic, with period-accurate clothing, staging and surroundings.</code>
```

提示词里没提“伍德斯托克音乐节”，只给了时间和地点。模型需要自己知道那天那里发生了什么。

### 案例 9：把故事变成四格漫画

把故事拆成清晰的视觉节拍，一格一个节拍。

描述具体、以动作为主，画面才好读、节奏才对。设置：1024x1536，medium。

```
<code class="language-text">Make a short vertical comic-style reel with 4 panels.
Panel 1: The owner walks out the front door. Behind the window glass the pet looks small, eyes wide, paws pressed high on the pane; the house has suddenly gone quiet.
Panel 2: The door clicks shut and the silence breaks. The pet slowly turns toward the empty house, its posture changing, eyes sharp with possibility.
Panel 3: The house is transformed. The pet lounges across the couch as if it owns the place, crumbs scattered nearby, a beam of sunlight crossing the room like a spotlight.
Panel 4: The door opens. The pet sits perfectly by the entrance, alert and composed, as if nothing ever happened.</code>
```

### 案例 10：UI 效果图，当它已经上线了来写

把产品当成已经存在的东西来描述，重点写布局、层级、间距和真实的界面元素。

官方点名了一个反面做法：用概念图的语言写，结果会像设计草稿，不像已上线的界面。设置：1024x1536，medium。

```
<code class="language-text">A realistic mobile app UI mockup for a local farmers market, showing today's market. Include a simple header, a short list of vendors with small photos and categories, a small "Today's specials" section, and basic location and opening hours. It should feel practical and easy to use: white background, subtle natural accent colors, clear typography, minimal decoration. It should look like a real, well-designed, beautiful app for a small local market. Place the UI mockup inside an iPhone frame.</code>
```

### 案例 11：科学教育插图

生物、化学、课堂讲解、扁平科学图标、示意图、学习素材都适合。

写法要像教学设计需求单：受众、教学目标、视觉形式、必需标签、科学约束。

要求干净扁平的视觉体系：图标风格统一、箭头清楚、标签好读、留足空白方便学生扫读。准确性重要时，明确列出必须有的组成部分和不能出现的东西。标签密集或要放进课件的图，用 quality="high"。设置：size="1536x1024"，quality="high"。

```
<code class="language-text">A simple biology diagram titled "Cellular Respiration at a Glance" for high school students. Show how a cell turns glucose into energy through glycolysis, the Krebs cycle and the electron transport chain, with arrows linking each step. Label the key molecules: glucose, pyruvate, ATP, NADH, FADH2, CO2, O2 and H2O. Style it like a clean classroom handout or slide: white background, simple icons, clear labels, easy-to-read text. Avoid tiny text, extra decoration, or anything that makes the diagram harder to follow.</code>
```

### 案例 12：幻灯片、图表，按交付物规格来写

这类提示词要写成交付物规格说明，别写成插画需求。

点明具体交付物（幻灯片、流程图、图表、页面图），定义画布和层级，直接给出真实的文字和数据，描述视觉语言。

再加上实用约束：字体好读、间距讲究、没有装饰性杂物、没有千篇一律的图库照片感。

数字和标签直接写进提示词。演示文稿用横版尺寸，小字、图例、坐标轴、脚注用 quality="high"。设置：size="1536x864"，quality="high"。

```
<code class="language-text">A single pitch-deck slide titled "Market Opportunity" that looks like a real Series A fundraising slide from a YC-backed startup. Clean white background, modern sans-serif type similar to Inter, crisp minimal layout.
Content:
- A TAM / SAM / SOM concentric-circle diagram in muted blues and grays
- Specific, believable market sizes: TAM: $42B, SAM: $8.7B, SOM: $340M
- Below it, a clean bar chart of market growth from 2021 to 2026 with a subtle upward trend
- Small footnotes: "AGI Research, 2024" and "Internal analysis"
- A company logo placeholder in the bottom-right corner
It should look like it came from a deck that actually raised money: highly readable text, clear data hierarchy, polished spacing, professional startup visual language. Avoid clip art, stock photos, gradients, shadows, decorative elements, or anything generic or overdesigned.</code>
```

官方特别说明，提示词里的数字和引用来源都是虚构的。

使用前要核对每一个数字，包括模型自己额外加上的百分比。

## 编辑篇：9 个案例

编辑用 client.images.edit，传入参考图。

需要蒙版的局部修改，见官方生图指南的“editing with a mask”一节。

### 案例 13：用红圈标注要改的地方（markup，2.6 新增）

在要改的物体上画个圈，再用文字说明怎么改。这里的目标是厨房餐桌上的条纹花瓶。

请求方式：一次 multipart 的 POST /v1/images/edits，带两个文件，原始厨房照片作为 image，透明的红圈标注层作为 markup，两张都是 1200 × 900 像素。

限制：markup 只作用于第一张输入图，其余图片只当参考；传了 markup 就不要再传 mask 和 prompt_rewriter。设置：quality="medium"、size="auto"、PNG。

原始厨房照片：

透明标注层，以及叠加后的预览：

```
<code class="language-text">Recolor the striped vase inside the red circle to a solid cobalt-blue ceramic. Keep its shape, the dried stems and the rest of the kitchen exactly as they are. Remove the red circle from the final photo.</code>
```

两个模型都把花瓶改成了钴蓝色，保留了干花枝，也去掉了红圈。

官方建议再把整张图和原图对比一遍，看有没有改到别处。

以前做局部编辑要准备黑白蒙版，现在画个圈就行，操作门槛低了很多。

### 案例 14：翻译图中文字，版式不动

输入是案例 5 里两个模型各自生成的咖啡机信息图。要求替换文字、保持设计不变，然后检查译文质量，以及有没有漏翻的原文。设置：1024x1536，quality="high"。

```
<code class="language-text">Translate all the text in this infographic into Spanish. Leave every other aspect of the image unchanged.</code>
```

### 案例 15：迁移视觉风格

给参考图一个具体角色（调色板、质感或画面媒介），新主体单独描述。输入是一张像素风游戏截图。设置：1024x1536，medium。

```
<code class="language-text">Using the same style as the input image, generate a man riding a motorcycle on a white background.</code>
```

### 案例 16：保留人物身份，只换衣服

输入是一张女士在博物馆的照片，加三张服装参考：米色夹克、白色背心、灰色靴子。

要点是写明人物哪些部分必须固定，只允许衣服变化。

同样的写法也适用于必须保持可识别的产品或物体。设置：1024x1536，medium。

```
<code class="language-text">Dress the woman using the clothing shown in the provided images. Do not alter her face, facial features, skin tone, body shape, pose or identity in any way; keep her exact likeness, expression, hairstyle and proportions. Replace only the clothing, fitting it naturally to her existing pose and body with realistic fabric behavior. Match lighting, shadows and color temperature to the original photo so the outfit looks photographed, not pasted on. Leave the background, camera angle, framing and image quality unchanged. Add no accessories, text, logos or watermarks.</code>
```

这条提示词里，“不许改”的部分比“要改”的部分长得多。这正是原则 6 的样子。

### 案例 17：组合多张参考图

图 1 是街景中的女士，图 2 是一位女士和一只狗。

要点是说清哪个元素移动、移到哪里、什么不能变。设置：1024x1536，medium。

```
<code class="language-text">Take the dog from the second image and place it into the setting of image 1, right beside the woman, matching image 1's lighting, composition and background. Change nothing else.</code>
```

### 案例 18：透明背景产品抠图

提示词里要求主体独立，同时在 API 里设 background="transparent"，两边都要写。

用 PNG 或 WebP，保留返回的 alpha 通道，PNG 不要传 output_compression。

官方原话一针见血：“A drawn checkerboard is not transparency.”画出来的灰白棋盘格不等于透明。后续再编辑时，也要重复“保持透明背景”。

输入是一张洗发水产品照。设置：1024x1536，medium，background="transparent"，output_format="png"。

```
<code class="language-text">Extract the product from the input image and isolate it on a fully transparent background.
Output: the product centered, crisp silhouette, no halos or fringing.
Keep the product's geometry and label legibility exactly as they are.
Only light polishing. No solid backdrop, no checkerboard, no scenery, no shadow.
Do not restyle the product; just remove the background and keep clean alpha transparency.</code>
```

### 案例 19：线稿变写实照片

草图转渲染，能把潦草的线稿变成写实概念图，同时保留原始意图。

提示词当规格说明来写：先锁住版式和透视，再用可信的材质、光线、环境增加真实感。

加一句“不要新增元素或文字”，防止模型自由发挥。

输入是一张河谷线稿。设置：1024x1536，medium。

```
<code class="language-text">Turn this drawing into a photorealistic image.
Keep the exact layout, proportions and perspective.
Pick realistic materials and lighting that fit what the sketch intends.
Do not add any new elements or text.</code>
```

### 案例 20：移除一个物体

明确点名要删的那一个物体，其余全部保留。

人物、姿势、光线、构图都不变，编辑才能保持局部。

输入是一位戴蓝帽子、手拿花的男士。设置：1024x1536，medium。

```
<code class="language-text">Remove the flower from the man's hand. Change nothing else.</code>
```

### 案例 21：把人物放进新场景

在新场景里保留人物身份。

写明自然光线、可信细节、身体取景、视线方向和与场景的互动，并说明哪些面部特征和比例不能变。

不要传 input_fidelity。输入是案例 16 的博物馆女士照片。设置：1024x1536，medium。

```
<code class="language-text">A highly realistic action scene: this person is running away from a large, realistic brown bear that is tearing through a campsite. It should look like a real photo someone could actually have taken, not an over-enhanced, cinematic movie-poster shot. She is centered in the frame but looking away from the camera, wearing outdoorsy camping clothes, with dirt on her face and rips in her clothing. She is clearly scared but focused on getting away while the bear wrecks the campsite behind her. Setting: Yosemite National Park, believable natural details, dusk, natural light and realistic colors. Grounded, authentic and unstyled, as if captured in a real moment. Avoid cinematic lighting, dramatic color grading or stylized composition.</code>
```

“避免电影感”在这里反复出现了三次。模型面对动作场面，天然会往大片海报的方向走，要写实就得一再压住。

## 多轮迭代：一次只改一处

先出一张图，检查，再把它作为下一轮输入。每次追问都收窄范围，才看得出是哪一步起了作用。

### 案例 22：先出起始图

输入是案例 18 的洗发水照片，广告牌标题要逐字引用。设置：1024x1536，medium。

```
<code class="language-text">A realistic billboard mockup of this shampoo in a highway scene at sunset.
Billboard text (EXACT, verbatim, no extra characters):
"Fresh and clean"
Typography: bold sans-serif, high contrast, centered, clean kerning.
The text appears once and is perfectly legible.
No watermarks, no logos.</code>
```

### 案例 23：只改一个条件

把两个模型各自的广告牌输出传入下一次编辑请求。

这条短短的追问只改天气，场景其余部分保持不变。设置：1024x1536，medium。

```
<code class="language-text">Make it look like a winter evening with snowfall.</code>
```

### 案例 24：绘本角色一致性

做一本有多张插图的绘本，先建立一个可复用的角色参考图。

之后每次换环境、换剧情，都重复角色的关键特征。

第一步，确立角色。定义外貌、比例、服装和基调。设置：1024x1536，medium。

```
<code class="language-text">Create a children's book illustration that introduces the main character.
Character:
- A young storybook hero inspired by a little forest outlaw
- A simple green hooded tunic, soft brown boots and a small belt pouch
- A kind face with gentle eyes; brave but warm
- Carries a small wooden bow, used only to help, never to hurt
Theme: protects and rescues small forest animals such as squirrels, birds and rabbits.
Style:
- Children's book illustration with a hand-painted watercolor look
- Soft outlines, warm earthy colors, whimsical and friendly
- Picture-book proportions: a slightly oversized head and an expressive face
Constraints:
- An original character (no copyrighted characters)
- No text, no watermarks
- A plain forest background so the character stands out</code>
```

第二步，续写故事。复用各自模型的角色图，描述新场景，同时重复外貌约束。设置：1024x1536，medium。

```
<code class="language-text">Continue the children's book story with the same character.
Scene: after a winter storm, the same young forest hero gently helps a frightened squirrel out of a fallen tree. The hero kneels beside the squirrel, reassuring it.
Character consistency:
- The same green hooded tunic
- The same facial features, proportions and color palette
- The same gentle, heroic personality
Style: children's book watercolor, soft lighting, snowy forest, a warm and comforting mood.
Constraints: do not redesign the character; no text; no watermarks.</code>
```

“Character consistency”这一节每张图都要带上，相当于给角色建了一张随身携带的身份证。

## 更多工作流：家装、贺卡、周边

### 案例 25：换掉房间里的家具

只换一件家具，不重建整个场景。

官方把这叫“surgical realism”，手术式写实：换一个物体，机位、光线、阴影和上下文都不动，让结果像一张真实照片，看不出重新设计过。

输入是案例 13 那张有白色椅子的厨房照片。设置：size="1536x1024"，medium。

```
<code class="language-text">In this room photo, replace ONLY the white chairs with wooden chairs.
Keep the camera angle, room lighting, floor shadows and surrounding objects.
Leave everything else unchanged.
Photorealistic contact shadows and fabric texture.</code>
```

### 案例 26：节日贺卡

描述场景、情感基调、材质、光线和精确文案。

想要 3D 立体卡或实拍卡片的效果，要写出纸张层次、纤维、折痕和柔和的影棚光。设置：1024x1536，medium。

```
<code class="language-text">Create a Christmas holiday card illustration.
Scene: a cozy Christmas setting with an old teddy bear resting in a keepsake box; its fur is slightly worn and it has small stitched repairs. It sits by a window while snow falls outside. The scene hints that the child has grown up, but the memories remain.
Mood: warm, nostalgic, gentle, emotional.
Style: premium holiday-card photography, soft cinematic light, realistic textures, shallow depth of field, tasteful bokeh lights, print-quality composition.
Constraints: original artwork only; no trademarks, watermarks or logos.
Include ONLY this card text (verbatim):
"Merry Christmas — some memories never fade."</code>
```

### 案例 27：收藏级周边

用产品摄影的语言：材质、包装、印刷清晰度。

设计保持原创、不侵权，多出几个角色或包装变体做比较。设置：1024x1536，medium。

```
<code class="language-text">A collectible action figure of a vintage-style toy propeller airplane: rounded wings, a front-mounted spinning propeller, slightly worn paint on the edges, classic childhood proportions, presented as a nostalgic holiday collectible in blister packaging.
Concept: inspired by the simple toy planes children played with over the winter holidays; it should evoke warmth, imagination and childhood wonder.
Style: premium toy photography with realistic plastic and painted-metal textures, studio lighting, shallow depth of field, sharp label printing, high-end retail presentation.
Constraints: original design only; no trademarks, watermarks or logos.
Include ONLY this packaging text (verbatim):
"Christmas Memories Edition"</code>
```

## 跑通完整示例

官方给了一段 Python 和 Ruby 脚本，用选定的 2.6 模型生成 4 个 logo 变体和 1 张透明抠图。

准备：pip install openai（或 gem install openai），设置 OPENAI_API_KEY，把产品图存成 input_images/shampoo.webp。

运行 python demo.py gpt-image-2.6-flare，换成 gpt-image-2.6-sunburst 就能测大模型。

脚本核心逻辑大致如下（Python）：

```
<code class="language-python">import base64, sys
from pathlib import Path
from openai import OpenAI
</code>
```

client = OpenAI()
model = sys.argv[1]  # gpt-image-2.6-flare 或 gpt-image-2.6-sunburst

# 1. 生成 4 个透明背景 logo（提示词用案例 7）

logos = client.images.generate(
model=model, prompt=LOGO_PROMPT,
size="1024x1536", quality="medium",
background="transparent", output_format="png", n=4,
)
for i, item in enumerate(logos.data, 1):
Path(f"logo-generation-{i}.png").write_bytes(base64.b64decode(item.b64_json))

# 2. 透明背景抠图（提示词用案例 18）

cut = client.images.edit(
model=model,
image=[("shampoo.webp", Path("input_images/shampoo.webp"), "image/webp")],
prompt=EXTRACT_PROMPT,
size="1024x1536", quality="medium",
background="transparent", output_format="png",
)
Path("extract-product.png").write_bytes(base64.b64decode(cut.data[0].b64_json))

更多提示词可以看 OpenAI Cookbook 的 image-gen-models-prompting-guide.ipynb。

## 交付前的四项检查

图片用出去之前，官方要求过一遍：

每个字都能读清吗？和要求的文字一致吗？示意图的标签和关系对吗？

人物身份、产品形状、标签和参考图细节都还在吗？

编辑是不是只改了要求改的地方？

需要透明背景的，解码后的文件里真的有透明像素吗？

每次换提示词或换模型，都要在有代表性的输入上重新比较质量、延迟和成本。

## 落到手上：三步用好 2.6

通读 27 个案例，规律其实很集中。

描述能看见的东西，用引号锁住文字，把“要改的”和“不能改的”分开写，一次只动一个变量。

准备接入或迁移到 GPT Image 2.6 的团队，可以按这个顺序动手：

先建一套 20 到 30 条的基线提示词，覆盖自家业务里最难的几类图：带精确文字的、要保持产品形状的、要透明背景的。用同样的设置跑 Flare 和 Sunburst，记录每张被采纳图片的耗时和成本，Flare 能过就别上 Sunburst。

开放式创意提示词试 complexity=high，定点编辑从 low 起步；小字看不清时再调 quality，两个参数分开调。

局部编辑优先用 markup 画圈，必须像素级不变的区域，改完合成回原图，别把这份保证交给模型。