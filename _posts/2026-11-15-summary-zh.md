---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 31 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [Meta FAIR 与 NYU 拆解多模态视觉编码：预训练可选，视觉专用参数不可省](#item-tech-news-1) ⭐️ 8.0/10
2. [美团开放 1.6 万亿参数 LongCat-2.5 权重，称未用英伟达 GPU](#item-tech-news-2) ⭐️ 8.0/10
3. [MacBook Pro OLED 的 PWM 闪烁测量争议](#item-tech-news-3) ⭐️ 7.0/10
4. [现代大语言模型位置嵌入的技术解析](#item-tech-news-4) ⭐️ 7.0/10
5. [星舰第 15 次试飞飞船首次由发射塔机械臂捕获](#item-tech-news-5) ⭐️ 7.0/10
6. [特斯拉 Cybercab 条款：月费 299 美元才能运行](#item-tech-news-6) ⭐️ 7.0/10
7. [FAA 全国停飞：铜线换光纤维护后新路由器故障](#item-tech-news-7) ⭐️ 7.0/10

**财经新闻**
1. [CNBC：卢特尼克因英伟达涉华审查面临利益冲突质疑](#item-finance-news-1) ⭐️ 7.0/10
2. [美法官驳回美光、三星、SK 海力士撤诉动议，DRAM 价格操纵集体诉讼继续](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Meta FAIR 与 NYU 拆解多模态视觉编码：预训练可选，视觉专用参数不可省](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR 与 NYU 研究团队在一篇预印本中从零训练了 200 多个多模态大模型，在相同数据和计算预算下分别检验视觉编码的三个设计选择，结论是独立的视觉编码器预训练并非必需，但视觉专用参数不能省。主要对比使用 Qwen3-1.7B 和 4B 配置、0.4B 视觉容量，并在 16 个 Cambrian VQA 基准（448px）和 12 个语言基准上评估；四种预训练目标最多只能与从零联合训练的编码器打平，MetaCLIP 预训练延长 6.5 倍虽把 ImageNet 线性探测从 80.4% 提到 84.4%，却没有提升 VQA。无编码器模型在 0.6B 到 6.4B 各规模均落后、约需 3 倍算力追赶；作者提出的“in-fusion”把零初始化的视觉专用权重加到 LLM 前 8 层，在 1.7B 到 6.4B 与编码器方案相当，1.7B 时 VQA 为 45.0（编码器 44.4），且首 token 时间低约 13%。该论文尚未经同行评审，作者也在帖子中披露了自己的作者身份。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 多模态大语言模型长期默认采用预训练视觉编码器（如 CLIP 系列），但近期出现两种相反做法：让编码器与语言模型从零联合训练，或直接去掉编码器。由于已发布模型的数据、算力和编码器预训练设置各不相同，外界很难判断“预训练”“专用视觉容量”“编码器置于 LLM 之前”这三项选择各自的贡献。该研究把这三项拆开，在匹配算力下分别检验。

**「影响」** 对多模态模型团队而言，这项预印本研究的直接含义是：视觉编码器的单独预训练可以省去，编码器置于 LLM 之前也非必需；但无编码器设计仍须为视觉 token 保留专用参数和相应算力，因为在 0.6B–6.4B 的测试规模上，这类模型需要约 3 倍计算量才能追上。作者提出的 in-fusion 方案在前 8 层加入零初始化视觉专用分支，在 1.7B–6.4B 上与标准编码器表现相当，并报告首 token 时间低约 13%，可作为低延迟架构的候选，但适用性仍受该受控实验设置限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.17334">[2611.17334] Unbundling Multimodal Vision Encoding - arXiv.org</a></li>

</ul>
</details>

**标签**: `#multimodal LLMs`, `#vision encoders`, `#pretraining`, `#model architecture`, `#empirical study`

---

<a id="item-tech-news-2"></a>
### [美团开放 1.6 万亿参数 LongCat-2.5 权重，称未用英伟达 GPU](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型正式发布一周后公开了 LongCat-2.5 的权重，采用 MIT 许可证、允许商用；模型总参数为 1.6 万亿，每个 token 激活约 480 亿参数，支持文本、图像和视频输入。团队称该模型面向可自主完成冗长多步骤任务的智能体，尤其是编程任务，且训练全程使用华为升腾加速卡、未使用英伟达 GPU。官方公布的 Terminal Bench v2.1 得分为 88.4，略低于 Claude Opus 5 的 89.1；训练硬件和基准成绩目前均属厂商说法，来源未提供独立验证。

telegram · zaihuapd · 11月15日 11:08

**「背景」** 开放权重意味着公众可以下载模型参数，并在许可证允许的范围内使用，但这并不等同于公开训练数据或完整训练代码。

**「影响」** 对希望商用或再分发模型的开发者而言，MIT 许可证提供了明确的许可依据；但由于缺少独立验证，采用前应自行复测 Terminal Bench 成绩及模型在自有硬件上的推理表现。

**标签**: `#LongCat-2.5`, `#open-weight models`, `#Huawei Ascend`, `#AI agents`, `#AI hardware`

---

<a id="item-tech-news-3"></a>
### [MacBook Pro OLED 的 PWM 闪烁测量争议](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

MacAnorak 的文章审视 MacBook Pro OLED 屏幕的 PWM 闪烁问题，重点放在频率测量和显示敏感用户的实际体验上。相关讨论对既有测量结论提出质疑，并把问题定位为现有 OLED 调光方式下的可用性争议，而非一次产品更新。

hackernews · MacAnorak · 11月15日 13:15 · [社区讨论](https://news.ycombinator.com/item?id=50506719)

**「背景」** PWM（脉宽调制）调光通过快速开关像素来调节 OLED 亮度，频率越低，对闪烁敏感的人越容易察觉到频闪。Notebookcheck 对这款串联 OLED 触屏 MacBook Pro 的评测同样记录到 240 Hz 的 PWM 频率，并指出尽管具备 DC 调光，敏感用户仍可能受到影响。

**「对闪烁敏感用户的影响」** 对闪烁敏感的使用者来说，直接后果是低亮度下使用这块串联 OLED 屏幕可能引发不适，而评论区对实际 PWM 频率仍有分歧——有人复测后认为并非文章所述的 240 Hz，而是双层面板以 480 Hz、180 度反相工作、合计约 960 Hz，这意味着目前连“这块屏到底以多高频率调光”都缺乏共识，买家难以据此评估自身风险。2015 年《Scientific Reports》的研究显示，当画面含有高频空间边缘时，人眼可在超过 500 Hz 的频率下察觉闪烁，远高于通常引用的闪烁融合阈值，因此即便厂商把调光频率提升到数百赫兹，也不能推定对敏感人群无感；在缺少统一测量方法与官方参数的情况下，实地试用并保留退换渠道是较务实的应对方式。

**「社区讨论」** 评论者对 240 Hz 的测量结论提出异议：有人推测串联 OLED 的两层各以 480 Hz、180 度反相调光，在常用亮度下可形成约 960 Hz 的有效频率，但这一解释仍是推测，未形成共识。另有脑震荡经历者报告几乎各类屏幕都会造成不适，并有人呼吁进一步研究 PWM 敏感人群比例以及 CRI、运动模糊等相关因素。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.notebookcheck.net/Amazing-OLED-panel-Apple-MacBook-Pro-14-PROLED-XDR-Review.1438048.0.html">Amazing OLED panel - Apple MacBook Pro ... - Notebookcheck Review</a></li>
<li><a href="https://en.wikipedia.org/wiki/Flicker_fusion_threshold">Flicker fusion threshold - Wikipedia</a></li>
<li><a href="https://www.nature.com/articles/srep07861">Humans perceive flicker artifacts at 500 Hz | Scientific Reports</a></li>

</ul>
</details>

**标签**: `#OLED PWM`, `#display flicker`, `#MacBook Pro`, `#hardware ergonomics`, `#HN discussion`

---

<a id="item-tech-news-4"></a>
### [现代大语言模型位置嵌入的技术解析](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

一篇关于现代大语言模型位置嵌入的技术解析文章在 Hacker News 上被分享；该文章发表在 Sebastian Raschka 的杂志上，侧重实现层面的讲解。文章面向希望理解 Transformer 如何编码位置信息的开发者，属于解释性长文，并非发布新模型、新方法或基准结果。由于原文正文未被抓取，文章涉及的具体模型、公式和代码示例无法核实。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** Transformer 的自注意力本身不区分词序，因此模型需要额外注入位置信息，位置嵌入就是用来表示 token 先后关系的机制。现代 LLM 常采用旋转位置嵌入（RoPE），它通过按位置旋转来表示位置信息；理解这一机制有助于读懂文中关于实现细节的讨论。

**「影响」** 对正在实现或调优 Transformer 的开发者，这篇文章可用于梳理位置嵌入在代码层面的机制；但文章没有提出新的位置编码方案，因此不涉及现有模型训练或推理流程的改动。

**「社区讨论」** 在 Hacker News 讨论中，评论者 programjames 认为文章只覆盖了位置嵌入的实现，真正理解还需要理论视角：位置嵌入是群表示，旋转位置嵌入（RoPE）是平移群的表示。他还指出，可以用这一框架找到并参数化位置嵌入，使其可微、可学习；这属于评论者的观点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://medium.com/ai-insights-cobet/rotary-positional-embeddings-a-detailed-look-and-comprehensive-understanding-4ff66a874d83">Rotary Positional Embeddings : A Detailed Look and... | Medium</a></li>

</ul>
</details>

**标签**: `#positional embeddings`, `#large language models`, `#transformer architecture`, `#deep learning`, `#technical deep-dive`

---

<a id="item-tech-news-5"></a>
### [星舰第 15 次试飞飞船首次由发射塔机械臂捕获](https://www.spacex.com/launches/starship-flight-15) ⭐️ 7.0/10

SpaceX 宣布，星舰第 15 次试飞中，飞船在约 22.5 小时、绕地球约 14 圈的飞行后返回得克萨斯州发射基地，并首次在轨道返回后由发射塔机械臂直接捕获。此次任务还部署了 26 颗新一代星链 V3 卫星。不过，超重型助推器未按计划返回发射塔，而是在墨西哥湾溅落，因此两级同时回收尚未实现。

telegram · zaihuapd · 11月14日 23:49

**「背景」** 星舰由超重型助推器和星舰飞船两级组成，发射塔机械臂捕获是让箭体直接返回发射场、以便重复使用的回收方式。第 15 次试飞的原定目标包括两级同时返回发射塔，但助推器最终未能返回，因此此次只有飞船上级完成捕获，“两级同时回收”仍未实现。

**「复用验证进度」** 这次验证只覆盖飞船被塔臂捕获的环节；由于助推器未能返回发射塔，SpaceX 尚未证明两级可同时回收，后续任务仍需验证助推器回收路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aerospaceamerica.aiaa.org/spacex-achieves-first-starship-tower-catch/">SpaceX achieves first Starship tower catch - Aerospace America</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#reusable spaceflight`, `#Starlink`, `#aerospace`

---

<a id="item-tech-news-6"></a>
### [特斯拉 Cybercab 条款：月费 299 美元才能运行](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

特斯拉网站上的 Cybercab 条款显示，车辆售价为 29,990 美元，车主还须每月支付 299 美元自主驾驶订阅费，否则车辆无法运行。特斯拉可提前一个月通知调价；欠费或违规使用可导致订阅暂停或取消，累计三次警告会停用自动驾驶一周。车辆被限定在指定区域运行，未经授权不得接入网约车、配送或租赁平台。Electrek 指出，Cybercab 与用于 Robotaxi 的 Model Y 使用相同的 AI4 硬件和自动驾驶软件，但面向普通车主的 FSD 仍需人类监督。

telegram · zaihuapd · 11月15日 01:10

**「背景」** Cybercab 是特斯拉的双座自动驾驶车型，个人版与用于 Robotaxi 的 Model Y 共享 AI4 硬件和相同的自动驾驶软件。这里的地理围栏指由软件划定的允许运行区域；Electrek 报道称，个人版 Cybercab 只能在 Robotaxi 地理围栏内使用，这使按月订阅同时承担了软件授权和运行许可的作用。

**「对车主的影响」** 若持续订阅，个人车主每年将额外承担 3,588 美元的用车成本；同时特斯拉可提前一个月调价，使长期持有成本存在不确定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://electrek.co/2026/11/13/tesla-cybercab-personal-use-orders-299-subscription-geofence/">Tesla Cybercab orders open at $29,990 + $299/mo, only in ...</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription model`, `#robotaxi`

---

<a id="item-tech-news-7"></a>
### [FAA 全国停飞：铜线换光纤维护后新路由器故障](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

美国交通部长 Sean Duffy 于 11 月 14 日表示，周五 FAA 下令的全国停飞源于一处偏远设施将老旧铜线更换为光纤的例行维护，新装路由器随后出现问题，导致数千架航班停飞。他称根因尚不明确，可能是硬件故障、配置错误，也可能是承包商 L3Harris 的失误；该路由器每 4 到 5 秒向其他路由器发出逾千次连接请求，干扰了雷达信号与飞机通信。Duffy 同时呼吁国会追加空管现代化资金。

telegram · zaihuapd · 11月15日 02:10

**「背景」** 美国空管与通信系统老化已久：据路透社报道，国会此前已拨款 125 亿美元用于升级，交通部长达菲（Sean Duffy）现又请求追加 500 亿美元用于空管和机场建设。此次涉事的承包商 L3Harris 并非首次进入空管故障调查视野——《达拉斯晨报》称，该公司被部分归咎于 2025 年达拉斯一次空管中断，而本次调查聚焦的正是其安装的设备。

**「待查与追责」** 由于官方仅给出可能原因清单，硬件、配置与承包商操作三种方向仍在调查中，L3Harris 的责任尚未认定；Duffy 的追加预算呼吁也表明，这类老旧基础设施改造中的网络风险已被纳入空管现代化的讨论范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.dallasnews.com/business/airlines/article/l3harris-router-texas-faa-outage-22531968.php">L3Harris routers probed in FAA nationwide ground stop</a></li>
<li><a href="https://www.reuters.com/business/aerospace-defense/us-aviation-shutdown-blamed-l3-harris-installed-router-2026-11-14/">US aviation shutdown blamed on L3 Harris installed router</a></li>

</ul>
</details>

**标签**: `#FAA`, `#network outage`, `#routing failure`, `#infrastructure reliability`, `#aviation`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [CNBC：卢特尼克因英伟达涉华审查面临利益冲突质疑](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC 报道称，美国商务部长霍华德·卢特尼克因其子运营的 Cantor Fitzgerald 与英伟达的关系，以及在英伟达对华芯片出口审查中的角色面临利益冲突质疑。报道援引证券申报称，该机构在 2025 年 9 月至 2026 年 3 月间申报的英伟达持股减少近 50%，同时据 Axios 报道，卢特尼克多次抵制对涉嫌向中国转运英伟达芯片的 Megaspeed 采取行动；相关冲突指控尚无证据证实。

rss · CNBC Finance · 11月15日 19:58

**「背景」** 背景是：英伟达首席执行官黄仁勋近日辞职，此前有报道称他是一起涉及中国政府的间谍图谋的目标，并与一名疑似中国间谍存在婚外情。此事使外界重新审视美国商务部长霍华德·卢特尼克家族与英伟达的关系，以及商务部对中国芯片出口管制的执法。

**「影响」** 美国商务部推迟新的实体清单增列，使被指为对华转运英伟达 AI 芯片的新加坡公司 Megaspeed 暂不被纳入出口限制，尽管五角大楼、国务院、能源部和财政部已推动将其列入（tool-3-1、tool-3-2）；这意味着相关转运渠道继续处于管制之外，直接牵涉英伟达及其客户的出口合规。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Jensen_Huang_spying_scandal">Jensen Huang spying scandal - Wikipedia</a></li>
<li><a href="https://www.npr.org/2026/11/12/nx-s1-6037833/jensen-huang-nvidia-stepped-down">Nvidia CEO Jensen Huang resigns amid spy scandal : NPR</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html">Howard Lutnick&#x27;s sons&#x27; Nvidia ties amid Jensen Huang China ...</a></li>
<li><a href="https://biz.chosun.com/en/en-international/2026/11/11/IILWD5J6MBHCPAPSC6JTHHDATA/">U.S. slows move to sanction Singapore&#x27;s Megaspeed tied to ...</a></li>
<li><a href="https://aiweekly.co/alerts/commerce-delays-entity-list-additions-megaspeed-stays-off">Commerce delays Entity List additions, Megaspeed stays off</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Howard Lutnick`, `#China export controls`, `#conflict of interest`, `#semiconductors`

---

<a id="item-finance-news-2"></a>
### [美法官驳回美光、三星、SK 海力士撤诉动议，DRAM 价格操纵集体诉讼继续](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官 Noël Wise 驳回美光、三星与 SK 海力士要求撤销 DRAM 价格操纵集体诉讼的动议，认为原告提出的新证据足以让三家厂商的同步行为「更像编队飞行」。17 名个人与小企业原告指控三家厂商在一年内四次平行限制 DRAM 供应，使价格最高上涨 500%；这只是程序性裁定，并非认定存在违法行为，三家公司须在 12 月 7 日前回应。

telegram · zaihuapd · 11月15日 16:39

**「背景」** 这起拟议集体诉讼由 17 名个人和小企业提起，指控三家厂商在一年内四次同步限制 DRAM 供应；撤诉动议被驳回后，案件将进入取证阶段，法院尚未裁定是否存在违法行为。

**「影响」** 案件继续推进意味着美光、三星和 SK 海力士需在 12 月 7 日前应诉并进入后续程序；若最终被认定违法，潜在赔偿责任将由这三家供应商承担，而非仅由原告承担。在诉讼之外，内存供应偏紧的影响已波及下游：IDC 指出，DRAM 和 NAND 成本上升正威胁 2026 年智能手机与 PC 的定价和规格；TrendForce 预计三季度 DRAM 合约价环比仍将上涨 13%–18%。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/federal-judge-rejects-memory-makers-defense-samsung-micron-sk-hynix-dram-shortage-lawsuit/">Federal Judge Rejects Memory Makers’ Defense To Advance Class ...</a></li>
<li><a href="https://www.idc.com/resource-center/blog/global-memory-shortage-crisis-market-analysis-and-the-potential-impact-on-the-smartphone-and-pc-markets-in-2026/">Global Memory Shortage Crisis: Market Analysis and the ... - IDC</a></li>
<li><a href="https://www.trendforce.com/presscenter/news/20260703-13134.html">AI Server Demand Continues to Support Memory Prices in 3Q26 ...</a></li>

</ul>
</details>

**标签**: `#DRAM`, `#antitrust litigation`, `#price fixing`, `#Micron`, `#Samsung/SK Hynix`

---