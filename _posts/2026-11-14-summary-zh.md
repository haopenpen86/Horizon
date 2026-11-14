---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 44 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [ggml 张量库发布 v1.0.0](#item-tech-news-1) ⭐️ 8.0/10
2. [TorchTitan 在 384 块 GH200 上训练约 1T MoE](#item-tech-news-2) ⭐️ 8.0/10
3. [Nvidia 被指资助 AI 初创公司购买其 GPU 以制造稀缺](#item-tech-news-3) ⭐️ 7.0/10
4. [终端边框不占单元格的技巧](#item-tech-news-4) ⭐️ 7.0/10
5. [双 RTX 4090 驱动的 KORS 全频段实时航空波段收听](#item-tech-news-5) ⭐️ 7.0/10
6. [FAA 全国地面停飞约 4.5 小时后解除](#item-tech-news-6) ⭐️ 7.0/10
7. [微软 Outlook、Teams 与 Copilot 全球宕机逾 12 小时](#item-tech-news-7) ⭐️ 7.0/10
8. [DeepSeek 开放全家桶应用 API](#item-tech-news-8) ⭐️ 7.0/10
9. [OpenAI 解散独立机器人团队，转由通用模型驱动机器人](#item-tech-news-9) ⭐️ 7.0/10
10. [Cloudflare 以 Apache 2.0 开源无状态 AI 代理浏览器 Kitesurf](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [大厂里的意义：规模化影响与组织失调的代价](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [卢特尼克之子旗下坎托削减英伟达持股，引发利益冲突审视](#item-finance-news-1) ⭐️ 8.0/10
2. [芝加哥联储古尔斯比：通胀仍高，美联储“肯定还有工作要做”](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [ggml 张量库发布 v1.0.0](https://github.com/ggml-org/ggml/releases/tag/v1.0.0) ⭐️ 8.0/10

ggml 发布 v1.0.0 版本；它是 llama.cpp 以及大量本地 LLM 推理工具所依赖的开源张量库。当前可获得的发布信息只有版本号和发布日期，没有列出具体 API、性能、后端支持或兼容性变更。因此，这次更新的确定信息是版本号进入 1.0.0，而不是已披露的功能或性能改进。

hackernews · cobychapple · 11月14日 02:28 · [社区讨论](https://news.ycombinator.com/item?id=50493062)

**「背景」** ggml 是一个面向机器学习的张量库，llama.cpp 等本地推理工具建立在其之上。llama.cpp 的发布说明已列出将 ggml 更新至 v1.0.0，显示这一版本已进入下游项目。

**「影响」** 依赖 ggml 的项目在声明版本约束时有了 v1.0.0 这一明确基线；但由于发布条目未说明 API 或后端兼容性变化，开发者升级前仍需自行验证构建和运行行为。

**「社区讨论」** 有用户报告升级后同一 5 万 token 长提示的基准运行时间从 4:22 降至 3:59，并称每月升级常带来 5% 到 10% 的提速；另一名使用仅支持 Vulkan 的 AMD 显卡的用户表示 ggml/llama.cpp 让本地推理变得可用。上述均为个人测试或体验，并非发布方公布的基准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ggml-org/ggml">GitHub - ggml-org/ggml: Tensor library for machine learning</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp/releases">Releases · ggml-org/llama.cpp · GitHub</a></li>

</ul>
</details>

**标签**: `#ggml`, `#local-inference`, `#llama.cpp`, `#open-source`, `#machine-learning-library`

---

<a id="item-tech-news-2"></a>
### [TorchTitan 在 384 块 GH200 上训练约 1T MoE](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

Reddit 帖子作者称，其团队与 TorchTitan/PyTorch 维护者合作，在 JUPITER 超算的 384 块 GH200 上，以 384 路 FSDP 加 4 路 EP 训练约 1T 参数 MoE，达到每 GPU 约 1,300 tokens/s，较起点提升 14 倍。这是团队自述、尚无独立复现的结果；作者把增益归因于全量激活检查点、将检查点经 900 GB/s C2C 链路卸载到 Grace 并按层预取、用 Muon 替代 Adam 以支持 64k token 序列，以及用 FlexShard 按完整专家分片避免额外通信。作者还报告，把 Newton-Schulz 优化器步骤移到 GPU 后，该步骤从 42 秒降到约 2 秒、吞吐提高 35%；按注意力成本分桶、FP8 专家 all-gather、bf16 传输加 fp32 本地累加也各自带来收益。作者同时指出，组限制路由带来 +7% 吞吐但可能损害训练，目前结论未定，并强调该机器只有用户级权限、真正限制在于跨节点带宽。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「背景」** TorchTitan 是 PyTorch 原生的开源大规模训练框架，支持 FSDP2、张量并行、流水线并行等并行组合，可通过 PyTorch nightly 安装（tool-2-1）。此前 PyTorch 团队与 AMD 曾合作用 TorchTitan 在约 1000 块 MI325X GPU 上做 MoE 预训练调优，说明它已被用于超大规模 MoE 场景（tool-2-2）。本次分享把 MoE 规模推到约 1T 参数，硬件换成 JUPITER 超算中的 GH200（Grace Hopper），瓶颈因此集中在 InfiniBand 互联带宽上。

**「可复用性与兼容性提醒」** 对用 TorchTitan/FSDP2 训练大规模 MoE 的团队而言，可直接复用的是按整专家切分的 FlexShard（让 Muon 的 Newton-Schulz 在本地完成、无需额外通信）以及把专家梯度的 reduce-scatter 换成 bf16 all-to-all、再由各 rank 本地升到 fp32 求和的写法。但文中 21% 的吞吐提升与 13.5 GiB 峰值显存下降依赖 FSDP2 的私有开关 \`unshard\_async\_op\`，作者称它“正在成为公开 API”，在正式发布前需要自行打补丁或跟随上游改动才能复现。此外 group-limited routing 带来的 +7% 有代价：作者明确表示早期实验显示限制路由目的地可能损害训练，结论尚未确定，采用前应自行验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/pytorch/torchtitan">GitHub - pytorch / torchtitan : A PyTorch native platform for training...</a></li>
<li><a href="https://pytorch.org/blog/efficient-moe-pre-training-at-scale-with-torchtitan/">Efficient MoE Pre-training at Scale on 1K AMD GPUs with TorchTitan ...</a></li>

</ul>
</details>

**标签**: `#MoE`, `#TorchTitan`, `#PyTorch`, `#distributed training`, `#GH200`

---

<a id="item-tech-news-3"></a>
### [Nvidia 被指资助 AI 初创公司购买其 GPU 以制造稀缺](https://www.techpowerup.com/354814/nvidia-allegedly-engineered-scarcity-by-funding-ai-startups-to-buy-its-gpus) ⭐️ 7.0/10

TechPowerUp 转载的一篇报道再次引发对 Nvidia 的指控：该公司通过资助 AI 初创公司，让后者购买其 GPU，以维持高需求印象并制造供应稀缺。该报道没有提供新的原始证据，而是对《华尔街日报》相关报道的层层转述，因此相关说法仍属未经证实的指控。报道和讨论还涉及循环融资、反垄断，以及 Nvidia 的投资与芯片销售之间的利益关系。

hackernews · speckx · 11月14日 02:52 · [社区讨论](https://news.ycombinator.com/item?id=50493251)

**「背景」** 这则报道并非原始调查：TechPowerUp 转述的是 Wccftech 对《华尔街日报》报道的再报道，核心指控是英伟达通过投资 AI 初创公司，让后者购买其 GPU 并建设数据中心（tool-2-2、tool-2-3）。相关报道称，此事发生在黄仁勋辞任、Colette Kress 出任临时 CEO 之后，Kress 曾推动收缩这类循环融资安排（tool-2-1、tool-2-3）。所谓“循环融资”指供应商向客户提供资金或股权投资，客户再拿这笔钱采购供应商产品，从而同时推高营收和需求表象。

**「潜在影响」** 若这些安排被证实，最直接的影响是 Nvidia 对 AI 初创公司的投资可能不再被视为单纯的财务投资，而会与芯片采购承诺一起接受反垄断审查；依赖其 GPU 的初创公司和数据中心运营商也将需要更仔细地评估融资附带条件与供应优先级。

**「社区讨论」** 评论者最集中的质疑是报道经过多次转述、原始信息不足，有人认为 TechPowerUp 只是转述 Wccftech 对《华尔街日报》的报道，直接读原文更有价值；也有人认为 Nvidia 投资或供货给 Nebius 这类数据中心公司是合理商业行为，可让后者优先获得新芯片、获得更便宜融资，并让 Nvidia 提前确认收入。另有老玩家回顾 GameWorks、PhysX 和 G-Sync 等历史争议，以此质疑 Nvidia 的竞争手法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.explainx.ai/blog/nvidia-engineered-gpu-scarcity-startup-funding-wsj-claimed-vs-verified-2026">WSJ: Nvidia Funded Startups to Buy GPUs — What&#x27;s Verified ...</a></li>
<li><a href="https://www.techpowerup.com/354814/nvidia-allegedly-engineered-scarcity-by-funding-ai-startups-to-buy-its-gpus">NVIDIA Allegedly Engineered Scarcity By Funding AI Startups ...</a></li>
<li><a href="https://todayforai.com/en/items/art-542023e2-c88">Nvidia Allegedly Funded AI Startups to Absorb GPU Oversupply</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI hardware`, `#antitrust`, `#circular financing`, `#GPU scarcity`

---

<a id="item-tech-news-4"></a>
### [终端边框不占单元格的技巧](https://www.joshka.net/cell-borders/) ⭐️ 7.0/10

一篇面向 TUI 开发者的技术文章介绍了让终端边框不占用独立字符单元的绘制方法，讨论范围涉及 Ratatui 和终端渲染能力。文章是技巧说明，并非新版本发布；实际可用性取决于终端仿真器支持哪些协议或渲染特性。

hackernews · vinhnx · 11月13日 23:06 · [社区讨论](https://news.ycombinator.com/item?id=50491423)

**「背景」** 终端以固定字符单元格为基本布局单位，传统 TUI 边框往往要占用整行或整列；另一种思路是用 DECSET 20 重叠加印把线画到已有字符上，但 mintty 是已知少数支持该模式的终端之一。joshka 是 Ratatui 维护者，他先在 Ghostty 的功能请求中提出“在单元格之间画线”的终端协议，并提供了 Ratatui 演示，这为当前文章讨论的免占格边框方案提供了直接前情。

**「影响」** 对 TUI 开发者来说，这类方法可把原本用于边框的单元格让给内容，但是否能采用取决于终端仿真器的支持范围。评论中提到的 overstrike（DECSET 20）目前主要见于 mintty，提示依赖非通用终端能力会带来可移植性问题。

**「社区讨论」** 有评论者认为更该推动终端仿真器普遍实现 overstrike 模式（DECSET 20），并指出已知仅 mintty 支持；也有人质疑既然要改终端协议，为何不设计更彻底的信息密集界面框架，而不是复刻哑终端限制。另有开发者担心新 TUI 框架会持续高频重绘、增加资源开销，并偏好更简单的纯文本接口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.lavx.hu/article/joshka-proposes-a-terminal-protocol-for-borders-that-leave-grid-space-intact">Joshka proposes a terminal protocol for borders that leave ...</a></li>
<li><a href="https://github.com/ghostty-org/ghostty/discussions/14324">Terminal protocol for borders between cells · ghostty-org ...</a></li>
<li><a href="https://github.com/mintty/mintty/wiki/CtrlSeqs">CtrlSeqs · mintty / mintty Wiki · GitHub</a></li>

</ul>
</details>

**标签**: `#terminal rendering`, `#TUI`, `#Ratatui`, `#terminal protocols`, `#developer tools`

---

<a id="item-tech-news-5"></a>
### [双 RTX 4090 驱动的 KORS 全频段实时航空波段收听](https://orcasairband.com/) ⭐️ 7.0/10

orcasairband.com 上线了一个实时收听 KORS（Orcas Island 机场）全频段航空波段（airband）的页面：作者 mmaunder 用一台 ETTUS B210 接收机连接双 RTX 4090 主机，以 CUDA 编写的多相信道化器把整个航空波段切分、解调并检测发射，丢弃数据类传输、只保留语音通话并生成文字转写。页面发布时恰逢 Victoria 发生地面停飞，作者贴出的原始转写包括 2143Z 在 126.400 Victoria Ground 上一段关于“通信问题、流量已停止”的弱信号通话，以及 134.800 Vancouver Centre 上的机组通话。这些转写未经编辑，也未获独立核实，频道计数与内容目前只能视为作者自述。

hackernews · mmaunder · 11月13日 22:04 · [社区讨论](https://news.ycombinator.com/item?id=50490593)

**「背景」** 该项目把 ETTUS B210 软件定义无线电接收机连接到双 RTX 4090 主机，用 CUDA 实现多相信道化器，将整个航空波段（airband）切分为信道后解调并检测发射，同时丢弃数据类传输。作者称，发布时恰逢 Victoria 发生 ground stop，因此这个原本用于监听本地空域的项目意外成了跟踪相关通话的工具。

**「实际影响」** 对航空通信爱好者而言，把整段 airband 一次性信道化意味着可以同时保留多个频率上的通话并按时间回溯，而不必逐个频率扫描；但页面上的转写未经核实，不应被当作航班运行或安全决策的依据。

**「社区讨论」** 评论者 molsongolden 回看页面记录，指出 14:03 有一段管制员确认飞往 Vancouver 的 ground stop 的通话；Scoundreller 则发现自己选中某频率后通话数与左侧计数不符，原因是静噪（squelch）阈值过滤掉了低于门限的通话。ltrg 将该项目类比为此前利用公开 KiwiSDR 接收机解码船舶 DSC 信号的爱好项目。

**标签**: `#software-defined radio`, `#GPU DSP`, `#CUDA`, `#airband`, `#aviation communications`

---

<a id="item-tech-news-6"></a>
### [FAA 全国地面停飞约 4.5 小时后解除](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 7.0/10

美国联邦航空管理局（FAA）于 2026 年 11 月 13 日发布全国性地面停飞指令，暂停离港航班，约 4.5 小时后解除。FAA 的公开说明有限，停飞的具体技术原因尚未得到官方完整确认；现阶段关于电信网络或系统更新的说法主要来自媒体转述和社区评论。

hackernews · zulln · 11月13日 21:05 · [社区讨论](https://news.ycombinator.com/item?id=50489641)

**「背景」** 美国联邦航空管理局（FAA）的全国地面停飞覆盖所有美国机场的离港航班，并会造成降落延误；此次事件的官方原因被描述为临时电信中断。这类指令用于在空管通信受限时暂停起飞，避免航班在无法获得管制服务的情况下升空。

**「实际影响」** 数千架次离港航班被取消或延误，航空公司和旅客在停飞解除后仍需面对积压与排班恢复，出行前应直接核对航班状态而非依赖原定时刻。CBS 新闻援引消息人士称，此次事件源于连接空管系统的网络更新引发重启、崩溃与中断，这意味着运营方在恢复航班的同时还要评估该网络补丁的可靠性。

**「社区讨论」** 评论者用 2009 年 FAA 电信基础设施（FTI）中断作类比，并批评早期讨论缺乏对全国空域系统实际运行方式的了解。对于此次原因，评论中并存两种说法：一是引述《华尔街日报》称 L3Harris Technologies 管理、用于空管员与飞行员通信的无线电网络似乎受影响；二是转述白宫简报称 FAA 部署新设备和技术时给旧系统造成过载。两者均属转述或推测，未获 FAA 完整证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_ground_stop">2026 FAA ground stop - Wikipedia</a></li>
<li><a href="https://www.theguardian.com/us-news/live/2026/nov/13/us-politics-latest-news-updates-democrats-republicans-donald-trump-van-hollen-chuck-schumer?page=with:block-6af791ef8f080d8d1c27a4e8">US flight outage live updates: FAA grounds thousands... | The Guardian</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after more than four hours, but flight ...</a></li>
<li><a href="https://www.cbsnews.com/news/faa-issues-nationwide-ground-stop/">FAA lifts nationwide ground stop that disrupted thousands of ...</a></li>

</ul>
</details>

**标签**: `#FAA`, `#critical infrastructure`, `#network outage`, `#aviation systems`, `#air traffic control`

---

<a id="item-tech-news-7"></a>
### [微软 Outlook、Teams 与 Copilot 全球宕机逾 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

微软 Outlook、Teams 和 Copilot 在 11 月 13 日仍处于宕机状态，故障已持续超过 12 小时，影响全球企业与政府机构的通信。微软将原因归结为服务器问题，称未发现恶意活动，并表示已扩大修复范围，目前出现回稳迹象。受影响方包括澳大利亚、日本和美国的部分政府机构；欧洲交易所 Euronext 的邮件受阻，台湾有金融机构改用传真确认交易。报道指出，这是微软 365 服务今年第二次中断。

telegram · zaihuapd · 11月13日 12:21

**「背景」** Microsoft 365 的 Outlook、Teams 与 Copilot 均为微软托管的云服务，服务端故障会同时波及不同地区的用户，终端本地配置无法规避。该报道还指出，这是微软 365 服务今年第二次中断，但未说明上一次中断的具体时间与范围。

**「实际影响」** 对依赖 Microsoft 365 的机构而言，这次中断直接迫使它们启用备用通道：台湾有金融机构改用传真确认交易，Euronext 的邮件通信受阻，部分政府机构的日常沟通被打乱。微软只表示修复范围已扩大并出现回稳迹象，但未说明全部服务何时完全恢复，因此相关组织仍需准备替代通信与确认手段。

**标签**: `#Microsoft 365`, `#outage`, `#Outlook`, `#Teams`, `#cloud services`

---

<a id="item-tech-news-8"></a>
### [DeepSeek 开放全家桶应用 API](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

据该 Telegram 摘要，DeepSeek 宣布开放一套“全家桶”应用 API：开发者在原有 API 中开启相应参数，即可获得深度思考搜索、文件输入、链接阅读和语音等对话能力，工具调用与上下文拼接由服务端自动完成。摘要称 V4.1-Flash 模型已在三个接口获得支持，Search、Fetch、OCR、ASR、TTS 可分别单独调用。DeepSeek 还开源了可导入历史对话的前端 Demo，并称可基于该 API 将 DeepSeek 网页端本地部署；上述细节来自简短摘要，尚缺独立验证。

telegram · zaihuapd · 11月13日 14:27

**「背景」** 这次更新建立在 DeepSeek 原有 API 的模型调用之上：开发者是在已有请求中开启对应参数，而不是改用一套完全独立的新接口。Search、Fetch、OCR、ASR、TTS 仍可作为单独端点调用，而对话场景中的工具调用和上下文拼接由服务端负责。

**「对开发者的影响」** 对应用开发者而言，直接变化是可以在 Messages、Responses 和 Chat Completions 中启用 V4.1-Flash 的内置搜索、文件输入、链接阅读与语音能力，由服务端完成工具调用和上下文拼接，从而减少自建编排层的需要；若只需单项能力，也可单独调用 Search、Fetch、OCR、ASR、TTS。迁移或新接入时应以 V4.1-Flash 为目标模型，并确认现有客户端使用的接口属于上述三个受支持接口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API | DeepSeek API Docs</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#API`, `#multimodal`, `#developer tools`, `#open source`

---

<a id="item-tech-news-9"></a>
### [OpenAI 解散独立机器人团队，转由通用模型驱动机器人](https://fortune.com/2026/11/13/openai-disbands-robotics-team-as-its-general-models-start-running-robots/) ⭐️ 7.0/10

据 Fortune 报道（经 Telegram 频道转述），OpenAI 已解散其独立机器人团队，把相关研究员重新分配到更通用的研究团队。公司给出的理由是，包括 GPT-6 Astra 在内的通用前沿模型已能直接操控机器人执行任务，因此不再需要专门的机器人团队；OpenAI 同时表示机器人仍是其长期愿景的核心，并仍在自研人形机器人，CEO 的目标是在 2027 年首次公开展示。这不是 OpenAI 第一次调整机器人业务：早期团队于 2020 年解散，2024 年重建并与 Figure 合作，但该合作已于 2025 年 2 月终止。目前该消息仅见于二手摘要，尚无 OpenAI 或 Fortune 原文的直接确认，也没有披露模型如何接入机器人硬件、涉及哪些机器人平台等技术细节。

telegram · zaihuapd · 11月14日 04:00

**「背景」** OpenAI 的机器人业务此前已多次调整：早期机器人团队于 2020 年解散，2024 年重建并与 Figure 合作，但这一合作于 2025 年 2 月终止。此次把独立机器人团队的研究员转入更通用的研究团队，是在上述反复之后再次重组，同时公司仍将人形机器人列为长期方向。

**「对机器人开发者的影响」** 对机器人开发者而言，OpenAI 不再保留独立机器人团队，而是把相关研究并入通用模型团队；同时其已确认 2027 年人形机器人演示目标，这意味着依赖 OpenAI 模型的机器人公司需要把它视为潜在直接竞争者，而不只是基础模型供应商，并应重新评估关键技术栈的供应商依赖。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techtimes.com/articles/329197/20261019/openai-confirms-humanoid-robot-2027-demo-competing-companies-it-once-backed.htm">OpenAI Confirms Humanoid Robot With 2027 Demo, Competing With ...</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#robotics`, `#general-purpose models`, `#AI strategy`, `#humanoid robots`

---

<a id="item-tech-news-10"></a>
### [Cloudflare 以 Apache 2.0 开源无状态 AI 代理浏览器 Kitesurf](https://www.phoronix.com/news/Cloudflare-Kitesurf-Open-Source) ⭐️ 7.0/10

Cloudflare 以 Apache 2.0 协议开源了面向 AI 代理的无状态浏览器 Kitesurf，代码已发布在 GitHub。该工具基于 Cloudflare Workers 构建，无需浏览器容器即可解析 HTML、处理 CSS 并执行 JavaScript。Cloudflare 表示，其目标是给 AI 代理一个轻量高效的浏览器，相比 Chromium 占用更少 CPU 和内存，并能在全球 Workers 网络上按需扩展；这些性能与资源占用的说法目前属于厂商声明，尚无独立基准测试或实现细节佐证。

telegram · zaihuapd · 11月14日 09:33

**「背景」** Cloudflare Workers 是无服务器运行时，而 Kitesurf 依赖其中的 Dynamic Workers 功能为每个页面创建隔离的 worker；据项目文档，Dynamic Workers 属于 Workers 付费计划的一部分，因此自建实例需要该套餐。Cloudflare 将该引擎定位为面向 AI 代理的实验性项目，代码可本地运行，也可部署到自己的 Workers 实例。

**「性能取舍与兼容性」** 对需要大规模并行的抓取或代理任务来说，Kitesurf 的主要代价是延迟：第三方博客 eesel AI 的基准测试显示，它的 CPU 和内存占用比 Chromium 低 3 至 7 倍，但实际耗时（wall time）约为 Chromium 的 1.8 倍，并且对 Web 标准的覆盖尚不完整。因此它更适合轻量的 HTML 解析类任务；团队在用它替换现有 Chromium 或 Playwright 流程前，应先验证目标页面的兼容性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/cloudflare/kitesurf">GitHub - cloudflare / kitesurf : Kitesurf is an experimental browser ...</a></li>
<li><a href="https://blog.cloudflare.com/kitesurf-open-source/">Kitesurf is now open source | Cloudflare Blog</a></li>
<li><a href="https://www.eesel.ai/blog/cloudflare-kitesurf">Cloudflare Kitesurf : the agent browser that trades speed for... | eesel AI</a></li>

</ul>
</details>

**标签**: `#Cloudflare`, `#AI agents`, `#browser automation`, `#open source`, `#Cloudflare Workers`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [大厂里的意义：规模化影响与组织失调的代价](https://seangoedecke.com/how-to-find-meaning-in-large-tech-companies/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月14日 00:00

**「背景」** 肖恩·戈德克（Sean Goedecke）在文中追问：为什么许多人讨厌在大型科技公司工作？常见答案是组织失调妨碍工程师写代码、发布产品，但他认为这解释不了为什么这些人连想都不愿想失调本身。

**「方案」** 作者认为，工程师对“整洁”有近乎本能的强迫倾向，组织失调带来的杂乱会让他们产生生理性厌恶，就像《Anathem》里被迫研读一本复杂却毫无意义的“书”，思考它本身即是一种自我伤害。另一重代价是角色扮演：OKR、某些截止日期、内部培训、营造员工“热情”等在大厂被当作重要的事，长期假装投入会让人怀疑“重要”本身是否只是幻觉。对此他的建议是：别用哲学消解虚无，而要去接触真正重要的事物、少想工作；但大厂也确实能提供意义，即在规模上把事情做对。让 Teams 好一点点，就是改善数百万使用者的生活；每修一个 bug、每加一个功能，都在为用户累计节省数月乃至数年的时间——即便企业软件通常在缓慢变坏，拖慢这一过程同样有价值。软件工程本身很难，在大组织里推动任何事也很难，两者的交集是一片噩梦般的泥沼；但只要你能容忍混乱，并有足够丰富的个人生活来对办公室政治保持健康的超然，它就是一个足够丰沛的意义来源。

**「启示」** 在作者看来，大厂工作的意义不在于手艺本身的精致，而在于规模化带来的实际影响；要获得它，既需要忍受组织的混乱，也需要在工作之外找到支点。

**标签**: `#large tech companies`, `#organizational dysfunction`, `#engineering culture`, `#work meaning`, `#career advice`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克之子旗下坎托削减英伟达持股，引发利益冲突审视](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC 11 月 13 日报道，由美国商务部长霍华德·卢特尼克之子领导的华尔街公司坎托·菲茨杰拉德（Cantor Fitzgerald）在 2025 年 9 月至 2026 年 3 月间，将其证券申报中持有的英伟达股票数量削减 49%，从约 350 万股降至 178 万股，同时仍与英伟达保持密切业务往来。报道称，在英伟达 CEO 黄仁勋辞职、以及 Axios 指卢特尼克多次抵制打击涉嫌对华走私英伟达芯片的公司后，这段关系正受到利益冲突审视；CNBC 明确表示，没有证据表明卢特尼克泄露非公开信息、其子提前知情或公司利益影响了其决策。

rss · CNBC Finance · 11月13日 23:42

**「背景」** 卢特尼克于 2025 年 2 月离开华尔街出任美国商务部长，该部门负责出口管制中的实体清单；此前有报道称，他多次抵制将涉嫌经东南亚向中国转运英伟达芯片的新加坡公司 Megaspeed 列入该清单。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.yahoo.com/news/politics/articles/us-treasury-chief-blames-commerce-145607629.html">US Treasury chief blames Commerce Dept for failure in Nvidia scandal</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#U.S. export controls`, `#Commerce Department`, `#conflict-of-interest scrutiny`, `#semiconductors`

---

<a id="item-finance-news-2"></a>
### [芝加哥联储古尔斯比：通胀仍高，美联储“肯定还有工作要做”](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

芝加哥联储行长古尔斯比 11 月 13 日表示，在 10 月生产者价格指数（PPI，衡量批发价格的指标）同比上涨 6.5%、创 2022 年 11 月以来新高后，美联储在恢复通胀可信度方面“肯定还有工作要做”。市场行情已完全计入美联储在 12 月 8 日至 9 日会议加息 25 个基点的预期。

rss · CNBC Finance · 11月13日 14:22

**「背景」** 古尔斯比目前不是联邦公开市场委员会（FOMC）投票委员，要到 2027 年才有投票权；美国通胀已连续近六年高于美联储 2%的目标。

**「影响」** 若美联储在 12 月如市场预期加息，持有浮动利率贷款的家庭和企业将直接面临更高的借贷成本。

**标签**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#producer price index`, `#interest rate expectations`

---