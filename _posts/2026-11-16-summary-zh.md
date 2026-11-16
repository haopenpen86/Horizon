---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 44 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 发布：可扩展 KV 缓存默认开启、Model Runner V1 移除](#item-tech-news-1) ⭐️ 8.0/10
2. [阿里 Qwen4-Max 上线，2.4 万亿参数支持百万上下文](#item-tech-news-2) ⭐️ 8.0/10
3. [Jiff 1.0 发布：Rust 日期时间库](#item-tech-news-3) ⭐️ 7.0/10
4. [Marimba：冻结 ASR 编码器的语音查询模型](#item-tech-news-4) ⭐️ 7.0/10
5. [duetto：免微调、采样时约束的实时爵士 MIDI 伴奏](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [中国 10 月消费、工业与投资数据全面低于预期](#item-finance-news-1) ⭐️ 8.0/10
2. [卢特尼克因英伟达“间谍”风波受质询，其子执掌的公司与英伟达有业务往来](#item-finance-news-2) ⭐️ 8.0/10
3. [美国将先进 AI 芯片出口管制延伸至远程访问](#item-finance-news-3) ⭐️ 8.0/10
4. [英特尔及 CEO 陈立武遭股东集体诉讼，被指隐瞒 PC 需求疲软](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 发布：可扩展 KV 缓存默认开启、Model Runner V1 移除](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 已发布，包含 1,061 个提交、412 名贡献者（其中 120 人为新贡献者），新增 10 个模型，并默认启用「可扩展 KV 缓存」：在 CUDA 和 ROCm 上，KV 缓存按预热与 CUDA graph 捕获之后实际空闲的显存来分配，官方称多数模型因此获得更大的缓存、更高吞吐，并在高并发下降低 TTFT。代价是部分 H200 模型在并发 128 时每 token 解码延迟（TPOT）上升 6–18%，可用 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache 退回旧行为。该版本同时移除了 Model Runner V1，V2 成为唯一的 GPU runner，默认 --block-size 由 16 改为 64。升级硬性条件包括 huggingface\_hub &gt;= 2.0.0（另需 tokenizers &gt;= 0.23.3、timm &gt;= 1.0.30）、ROCm 10.0 取代 ROCm 7.2 镜像，且 fp\_quant 检查点与 Marlin W4A8 不再可用。

github · khluu · 11月16日 23:22

**「背景」** KV cache 是推理引擎为自回归解码缓存的注意力键值状态，容量越大通常可支撑更高并发，但会占用显存；vLLM 过去按 \`gpu\_memory\_utilization\` 估算其大小，v0.34.0 改为在预热和图捕获后按实际空闲显存确定。Model Runner 则是 GPU 上执行模型前向、采样及图捕获的运行路径，vLLM 已在 V2 上承接双批重叠等能力，因此本次删除 V1 会直接影响仍显式启用 V1 或依赖其 logits processor 的部署。

**「影响」** 现有部署升级前需逐项核对破坏性变更：设置 VLLM\_USE\_V2\_MODEL\_RUNNER=0 会导致启动直接失败，V1 的 logits processor 需迁移到 vllm.v1.worker.gpu.sample.logits\_processor；依赖旧分页行为的服务应显式传入 --block-size 16（ROCm paged attention 仍使用 16）。使用 fp\_quant 或 Marlin W4A8 的检查点将无法加载，后者需改用 --quantization humming 配合 VLLM\_HUMMING\_INPUT\_QUANT\_CONFIG。

**标签**: `#vLLM`, `#LLM inference`, `#KV cache`, `#model serving`, `#hardware acceleration`

---

<a id="item-tech-news-2"></a>
### [阿里 Qwen4-Max 上线，2.4 万亿参数支持百万上下文](https://mp.weixin.qq.com/s/pJUt0xwD6H-WMyzd8TjZaQ) ⭐️ 8.0/10

阿里通义千问正式上线旗舰模型 Qwen4-Max，采用总参数 2.4 万亿的稀疏 MoE 架构，原生支持视觉理解和百万 Token 长上下文。官方称其前端编程能力在 Code Arena 盲测中位居全球前列，但该说法尚未经过独立验证。成本方面，单个任务平均费用从 26.58 元降至 11.16 元，降幅近 58%，Token 消耗减少近 50%，API 定价同步下调。团队还表示后续将推出规模更小的 Qwen4 系列并公开模型权重，这部分目前只是计划，尚未发布。

telegram · zaihuapd · 11月16日 02:52

**「背景」** 稀疏 MoE（混合专家）会把模型拆成多个专家网络，每个 token 只激活其中一部分；因此，“2.4 万亿总参数”并不等于每次推理都会调用全部参数，这直接关系到推理成本与吞吐。阿里云发布稿将 Qwen4-Max 称为 Qwen 家族迄今最强的模型；信源则称其成本相较上代明显下降。

**「对开发者的影响」** 对需要长上下文、视觉理解或编程辅助的开发者而言，按官方公布的单任务费用，Qwen4-Max 的 API 使用成本较上代明显下降；但在选型前仍应自行测试其代码质量与长上下文表现，因为现有性能排名来自官方转述而非独立评测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.alibabacloud.com/blog/alibaba-unveils-qwen4-max-new-ai-teammate-for-work-creativity-and-discovery_603783">Alibaba Unveils Qwen4-Max: New AI Teammate for Work ...</a></li>

</ul>
</details>

**标签**: `#Qwen`, `#Mixture-of-Experts`, `#large language models`, `#multimodal AI`, `#open-weight models`

---

<a id="item-tech-news-3"></a>
### [Jiff 1.0 发布：Rust 日期时间库](https://burntsushi.net/jiff/) ⭐️ 7.0/10

Jiff 1.0 已发布；这是一个由 burntsushi 开发、面向 Rust 开发者的日期时间库，涉及日期、时间和时区处理。现有材料只确认了 1.0 版本和项目定位，没有提供具体 API、兼容范围或发行说明细节；有评论提到，项目文档明确说明 Jiff 并非适用于所有场景。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「背景」** 在 Jiff 之前，Rust 生态中最常用的日期时间库是 chrono。一位维护 chrono 约五年的前维护者在讨论中表示，人们采用它主要是因为 API 稳定，任何向更好设计改进的尝试都会遇到阻力。Jiff 是 burntsushi 开发的替代方案，此次发布的是 1.0 版本。

**「对 Rust 项目选型的影响」** 对于新启动的 Rust 项目，一篇 2026 年 9 月的第三方库对比文章建议直接选用 Jiff，理由是它内建处理夏令时跳变（DST gap）与歧义时间，而 chrono 把这类情况留给调用方自行处理；但该文同时指出，如果代码库庞大或依赖已假定使用 chrono，继续留在 chrono 上更现实。Jiff 官方文档另提供与其他主流 Rust 日期时间库的逐项对比，可用来评估替换范围与成本。

**「社区讨论」** 前 chrono 维护者 quodlibetor 回顾说，自己接手维护的部分原因是 chrono 的 API 不理想，但用户真正看重的是稳定性，改进尝试常遇阻力，最终因倦怠而停止维护；他对 burntsushi 开发 Jiff 表示感谢。其他评论一方面赞赏 Jiff 明确承认并非所有场景都适用，并希望生态更多采用它；另一方面，也有开发者表示在 Rust 中仍倾向使用成熟的 chrono，并询问对 TAI、UT1 等时间尺度以及长跨度天文计算的支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.pistack.xyz/posts/2026-09-21-rust-datetime-libraries-chrono-jiff-time-hifitime-comparison/">Tired of Timezone Bugs in Rust? chrono vs jiff vs time vs ...</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/_documentation/comparison/index.html">jiff::_documentation::comparison - Rust - Docs.rs</a></li>

</ul>
</details>

**标签**: `#Rust`, `#datetime`, `#library release`, `#open source`, `#time zones`

---

<a id="item-tech-news-4"></a>
### [Marimba：冻结 ASR 编码器的语音查询模型](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

Reddit 帖介绍的 Marimba 论文提出一种“系统一”式语音模型：用户对 8 秒音频窗口提出是/否、选项或评分问题，模型返回校准后的概率，而每个窗口只对冻结的 Qwen3-ASR-0.6B 编码器做一次前向计算。术语检测先从解码器的贪心解和 4 个束搜索假设打分，再做 Platt 校准；语种识别复用 ASR 模型自身的语言分数，话轮结束和说话人变化/人数则读取冻结第 18 层或第 12 层的轻量读出。作者报告，在同一组 1000 个公开问题上，该模型在 9 项测试中的 6 项匹配或超过 30B-A3B 的 Qwen3-Omni，语种识别在 300 个 FLEURS 片段上达到 100%，说话人变化 AUROC 为 0.966–0.980，说话人数超过 pyannote 3.1；这些均为自报结果。作者也承认，话轮结束读出在 Smart Turn 数据上训练，因此该行属于分布内，且在 Smart Turn 自身测试集上 AUROC 0.930 低于 Smart Turn v3.2 的 0.982，在 CochlScene 场景分类上所有任务头仅为随机水平。

reddit · r/MachineLearning · /u/solanotodesch · 11月16日 15:47

**「背景：被冻结复用的 ASR 编码器」** Marimba 的核心做法是不训练新的音频主干，而是复用现成的语音识别模型作为特征提取器：每个 8 秒音频窗口只做一次冻结编码器前向，再在其上接轻量读出层或对解码假设打分。据 Hugging Face 模型页，Qwen3-ASR-0.6B 属于 Qwen3-ASR 家族（另有 1.7B 版本），支持多语言语音识别与语种识别，覆盖 52 种语言和方言；这也解释了 Marimba 为何能直接取用该模型自带的语种分数，而不另训一个语种分类头。

**「实际影响」** 对需要做语音查询的开发者，可行路径是安装 marimba-audio、使用 Apache-2.0 权重的模型，让单个冻结的 Qwen3-ASR-0.6B 编码器每 8 秒窗口执行一次前向计算，就可以同时支撑词项检索、语种识别、说话人变化与计数、轮次结束等多类问题，其中词项查询完全不需要训练；但该模型无法通过零样本迁移覆盖新任务（作者自测场景分类时所有任务头都处于随机水平），新增任务必须自行标注数据、重训读出层并重新校准，而轮次结束这一项因为训练数据来自 Smart Turn，作者也提示其成绩只是分布内结果。这种“冻结编码器 + 小型任务头”的路线此前也被用于多语种轮次结束检测，可减少按语种分别重新训练的开销。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/Qwen/Qwen3-ASR-0.6B">Qwen/ Qwen 3 - ASR - 0 . 6 B · Hugging Face</a></li>
<li><a href="https://hub.valency.io/works/W_nexjsy8z">Towards Multilingual End -of- Turn Detection using Frozen Speech ...</a></li>

</ul>
</details>

**标签**: `#speech recognition`, `#audio foundation models`, `#calibration`, `#model efficiency`, `#zero-shot learning`

---

<a id="item-tech-news-5"></a>
### [duetto：免微调、采样时约束的实时爵士 MIDI 伴奏](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

Reddit 用户展示了一个名为 duetto 的项目：它把预训练的 Anticipatory Music Transformer 直接用作实时爵士 MIDI 键盘搭档，不进行微调，而是在每次采样前用规则层修改 logits，屏蔽不允许的音符，并对当前和弦音、强拍导音或引用乐句的下一音加权。演示曲为 160 bpm 的《Autumn Leaves》；作者报告独奏音符约 61% 来自引用的 Weimar Jazz Database 乐句或主题，其余由模型生成，并称服务器预采样约 1 秒音乐、在演奏者输入时重采样未播放部分以降低延迟。作者在 3080 Ti 上测得中模型约 12 ms/音、大模型约 18 ms/音，大模型在 Jetson Orin Nano 上约 90 ms/音；代码可免费用于非商业用途。他也指出系统仍会偏离演奏者、响应难以预测，模型想法与规则之间的平衡很脆弱：偏置过强像乐句本，过弱又不像爵士。

reddit · r/MachineLearning · /u/GGAllin43 · 11月16日 09:19

**「背景：预训练模型与采样时控制」** duetto 复用的是预训练的 Anticipatory Music Transformer（Thickstun 等，2023）；该模型以交错的事件序列和控制序列进行 anticipatory 音乐生成，可将外部控制信号纳入生成过程。它按离散音符事件逐个预测下一个事件，因此 duetto 无需微调，只需在每次采样前改写 logits 来施加规则和引导。

**「对实时符号音乐开发者的影响」** 对做实时 MIDI 伴奏或可控生成的开发者来说，这个项目给出了一个可复现的替代路线：不微调预训练模型，而是把规则层的掩码与偏置全部放在采样阶段，作者报告的推理开销约为 12 ms/音符（medium）和 18 ms/音符（large，3080 Ti），large 模型在 Jetson Orin Nano 上约 90 ms/音符仍可现场演奏，说明该方案能落在边缘设备上运行。需要注意两点实际约束：代码仅限非商业用途，商用需另行授权；作者也坦言模型与规则的配比很脆弱，偏置过强会退化成“乐句手册”，过弱则失去爵士语感，采用者需要自行调参验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer</a></li>
<li><a href="https://paperswithcode.co/paper/2306.08620">Anticipatory Music Transformer (arXiv...) | Papers with Code</a></li>

</ul>
</details>

**标签**: `#music generation`, `#transformer models`, `#sampling-time control`, `#real-time inference`, `#open-source code`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中国 10 月消费、工业与投资数据全面低于预期](https://www.cnbc.com/2026/11/16/china-retail-sales-october-industrial-output-investment.html) ⭐️ 8.0/10

中国 10 月社会消费品零售总额同比增长 0.4%，低于分析师预期的 0.8%；规模以上工业增加值增长 4.8%，低于 5.3%的预期；前 10 个月固定资产投资同比下降 8.1%，差于预期的 7%降幅。

rss · CNBC Finance · 11月16日 03:53

**「背景」** 三季度中国 GDP 同比增长 4.5%，已从三年低点回升，但今年固定资产投资的下滑幅度为新冠疫情时期以外所未见；分析人士把消费疲软归因于持续五年的房地产市场低迷侵蚀了家庭财富。

**「影响」** 由于 10 月出口同比增长 35.2%、成为主要增长支撑，花旗研究分析师警告，欧盟若进一步加征贸易措施，加上全球人工智能资本开支周期可能回落，将令依赖外需的中国制造商和就业承压。

**标签**: `#China economy`, `#macroeconomic data`, `#retail sales`, `#industrial output`, `#fixed-asset investment`

---

<a id="item-finance-news-2"></a>
### [卢特尼克因英伟达“间谍”风波受质询，其子执掌的公司与英伟达有业务往来](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC 报道，美国商务部长霍华德·卢特尼克因其前公司坎托·菲茨杰拉德与英伟达的关系面临质询：据证券文件分析，该公司报告的英伟达持股数量在 2025 年 9 月底至 2026 年 3 月底期间下降约 49%，从约 350 万股降至约 178 万股，市值从 6.52 亿美元降至 3.10 亿美元。据 Axios 报道，同期美国情报和 white house 官员施压卢特尼克打击涉嫌经新加坡向中国转运英伟达先进 AI 芯片的 Megaspeed 公司，他多次予以抵制；CNBC 同时指出，没有证据表明卢特尼克泄露了非公开信息，也没有证据表明其子事先知晓相关情报担忧或持股变动与警告有关。

rss · CNBC Finance · 11月16日 12:14

**「背景」** 据《纽约时报》2026 年 10 月报道，英伟达 CEO 黄仁勋在一起涉华间谍疑云中成为目标，相关调查还牵出新加坡公司 Megaspeed；而美国商务部负责执行芯片出口管制，卢特尼克在出任部长前领导 Cantor Fitzgerald，该公司现由其子经营。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Nvidia_alleged_spying_scandal">Nvidia alleged spying scandal - Wikipedia</a></li>
<li><a href="https://www.nytimes.com/2026/11/09/business/economy/nvidia-megaspeed-investigation-huang.html">U.S. Commerce Dept. Inquiry Into Megaspeed Was Halted After ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#US-China relations`, `#Commerce Department`, `#conflict of interest`

---

<a id="item-finance-news-3"></a>
### [美国将先进 AI 芯片出口管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 8.0/10

美国商务部 11 月 16 日发布临时最终规则，将先进 AI 芯片和服务器的出口管制延伸至远程访问，以堵住经由第三国数据中心规避限制的渠道；据 The Verge 报道，向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口这类芯片需申请许可。

telegram · zaihuapd · 11月16日 14:44

**「背景」** 此前，美国对先进 AI 芯片和服务器实施出口许可管制，企业仍可能把设备放在第三国数据中心，让中国客户远程调用算力来绕过限制；美国商务部工业与安全局（BIS）此次发布临时最终规则，就是为了堵住这条通道。

**「影响」** 在新加坡、马来西亚、泰国、印度尼西亚和巴西运营数据中心的企业，向境外客户提供先进 AI 芯片算力前须先取得美国政府许可，而英伟达等厂商经由东南亚数据中心向中国 AI 开发者出租芯片的渠道将直接受影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China’s Remote Access to Nvidia’s AI Chips</a></li>
<li><a href="https://wccftech.com/the-u-s-shuts-chinas-access-to-advanced-chips-via-singapore-brazil-indonesia-malaysia-and-thailand-as-scott-bessent-gives-nvidia-10-days-to-show-it-did-not-goose-its-revenues/">The U.S. Shuts China&#x27;s Access To Advanced Chips Via Singapore...</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/commerce-closes-chinas-backdoor-to-nvidia-chips-after-white-house-steps-in-01167199">Commerce closes China’s backdoor to Nvidia chips after White ...</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China’s Remote Access to Nvidia’s AI Chips</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#US Commerce Department`, `#data centers`, `#semiconductor policy`

---

<a id="item-finance-news-4"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼，被指隐瞒 PC 需求疲软](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

英特尔及其 CEO 陈立武、CFO 津斯纳被股东提起集体诉讼，指控公司在 10 月 29 日发布不及预期的第四季度营收和利润预测之前，隐瞒了个人电脑（PC）需求疲软和库存积压的影响。诉讼称，该预测公布后次日股价下跌 28.6%，市值蒸发约 1400 亿美元；这起诉讼由一家密歇根州养老基金牵头，上周五在圣何塞联邦法院提起，代表在 2026 年 7 月 23 日至 10 月 29 日期间买入股票的投资者。

telegram · zaihuapd · 11月16日 11:10

**「背景」** 英特尔是美国芯片制造商，陈立武自 2025 年起出任 CEO。据彭博报道，英特尔 10 月 29 日发布的第四季度业绩预测不及市场预期，这使其股价创下四十多年来最差单日表现；股东在诉讼中称，公司此前未充分披露个人电脑（PC）需求疲软的影响。

**「影响」** 在 2026 年 7 月 23 日至 10 月 29 日期间买入英特尔股票的投资者属于这起拟议集体诉讼的覆盖范围，可能通过诉讼寻求赔偿。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Lip-Bu_Tan">Lip - Bu Tan - Wikipedia</a></li>
<li><a href="https://www.bbc.com/news/articles/cw62p42p288do">Investors sue chip giant Intel after 29% stock plunge</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-10-29/intel-outlook-hurt-by-weak-market-for-personal-computer-chips">Intel Earnings: (INTC) Stock Sinks After PC Slump, Supply ...</a></li>
<li><a href="https://www.techpowerup.com/354906/intel-faces-class-action-lawsuit-over-pc-sales-slowdown-disclosures">Intel Faces Class Action Lawsuit Over PC Sales Slowdown ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#shareholder class action`, `#stock plunge`, `#earnings guidance`, `#semiconductor`

---