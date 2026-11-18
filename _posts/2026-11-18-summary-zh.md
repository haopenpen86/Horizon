---
layout: default
title: "Horizon Summary: 2026-11-18 (ZH)"
date: 2026-11-18
lang: zh
---

> 从 40 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Nginx HTTP/2 未认证 RCE 公开：1.30.7 与 1.31.9 修复](#item-tech-news-1) ⭐️ 9.0/10
2. [Google 发布 Gemini 4 Neon，技术细节尚未公开](#item-tech-news-2) ⭐️ 8.0/10
3. [Java4Shell：CVE-2026-114938 无需认证 RCE 漏洞](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 撤出法国：DNS 解析器不应承担反盗版拦截](#item-tech-news-4) ⭐️ 7.0/10
5. [Google DeepMind 宣布 Genie 4 可用，访问条件不明](#item-tech-news-5) ⭐️ 7.0/10
6. [微信小微测试日活达 3000 万，计划部分端侧推理](#item-tech-news-6) ⭐️ 7.0/10

**科技博客**
1. [vLLM 用 FlyDSL MonoKernel 加速 AMD GPU 低并发解码](#item-tech-blog-1) ⭐️ 8.0/10

**财经新闻**
1. [美联储会议纪要：官员预计还需加息，并担忧 AI 推升通胀](#item-finance-news-1) ⭐️ 8.0/10
2. [美联储理事沃勒称 12 月可能需加息 50 个基点](#item-finance-news-2) ⭐️ 8.0/10
3. [美芯片新规引发合规担忧，五家银行暂停 4.8 亿美元字节跳动 GPU 贷款](#item-finance-news-3) ⭐️ 7.0/10
4. [英国下议院通过移民与庇护法案](#item-finance-news-4) ⭐️ 7.0/10
5. [腾讯 2026 年三季度营收逊预期，资本开支超预估](#item-finance-news-5) ⭐️ 7.0/10
6. [中韩宣布自贸协定服务与投资后续谈判实质性结束](#item-finance-news-6) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Nginx HTTP/2 未认证 RCE 公开：1.30.7 与 1.31.9 修复](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 9.0/10

Xint 公开了名为 NGINX2Root 的利用链：其中 5 个 nginx 漏洞与一个 Linux 内核缺陷串联后，攻击者可从 nginx 访客环境取得主机 root 权限。CVE-2026-123007 是 HTTP/2 流控内存破坏漏洞，未认证攻击者可在 worker 进程中执行命令。nginx 1.30.7 和 1.31.9 已于 11 月 18 日修复相关 10 个 CVE，Rapid7 已发布 PoC，目前尚无在野利用报告。无法升级的部署应关闭对外 HTTP/2；HTTP/2 在 nginx 中并非默认启用。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「背景」** Nginx 以 master-worker 模式处理请求，worker 通常并非以 root 运行；本次披露所称的“打到主机 root”依赖把 Nginx 漏洞与 Linux 内核缺陷串联起来，而不是单一 HTTP/2 缺陷直接完成。HTTP/2 在 Nginx 中需要显式启用，社区讨论据此认为实际暴露面取决于哪些服务器开启了该协议。

**「处置建议」** 启用 HTTP/2 的 nginx 实例应在升级到 1.30.7 或 1.31.9 前关闭对外 HTTP/2；否则未认证攻击者可在 worker 进程中执行命令，而公开 PoC 已降低利用门槛。未启用 HTTP/2 的部署不受该入口影响，但仍应核对实际监听配置，不能把“默认关闭”当作已核查。

**「社区讨论」** 有评论者指出，相关修复似乎提前约一周出现在开源仓库中，提交信息还写有报告者 Xint.io，认为在补丁发布前至少应公告建议关闭 HTTP/2；另一名评论者补充，HTTP/2 并非 nginx 默认启用，使用率约为 12%。还有评论关注利用链中用于容器逃逸的 Linux SCTP 缺陷：它似乎尚无公开 CVE 编号，可能仍在与内核和发行版协调修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cycode.com/blog/nginx2root-cve-2026-123007/">NGINX2Root (CVE-2026-123007): Affected Versions, How to Check ...</a></li>
<li><a href="https://computingforgeeks.com/nginx-cve-2026-123007/">nginx CVE-2026-123007: Check, Disable HTTP/2, Patch ...</a></li>
<li><a href="https://research.jfrog.com/post/nginx2shell-all-you-need-to-know-about-cve-2026-123007-and-cve-2026-123633/">Nginx2Shell: All You Need to Know About CVE-2026-123007 and ...</a></li>

</ul>
</details>

**标签**: `#nginx`, `#http2`, `#remote-code-execution`, `#security`, `#vulnerability-disclosure`

---

<a id="item-tech-news-2"></a>
### [Google 发布 Gemini 4 Neon，技术细节尚未公开](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

Google 于 11 月 18 日在官方博客发布题为《Introducing Gemini 4 Neon》的文章，宣布推出 Gemini 4 Neon 模型。除模型名称和发布渠道外，所提供材料未包含任何可核实的规格信息：没有参数规模、上下文长度、基准测试分数、定价，也没有说明它是已向用户开放还是仅处于宣布阶段，以及通过哪些产品或 API 提供。因此，Neon 相对前代 Gemini 模型的具体改进，目前无法从现有证据判断。

hackernews · yigitdemirag · 11月18日 21:34 · [社区讨论](https://news.ycombinator.com/item?id=50552424)

**「背景」** Google 将 Gemini 4 Neon 放在同一代 Gemini 4 模型家族中：按 Google DeepMind 的模型卡，Carbon 面向最困难的长周期项目，Hydrogen 负责快速日常执行，而 Neon 主打深度与效率的平衡。Google Cloud 的文档则把它描述为面向智能体企业工作流、具备低延迟的高性能编码、多步推理与多模态理解能力的模型。

**「对选型的影响」** 对正在评估模型的开发者而言，直接后果是选型不能只看综合榜单：有评论者指出 Neon 在综合指数上高于 Carbon，但 Carbon 仍被定位为“长周期”模型，并在 CritPt 这类研究级推理评测中得分更高；另一条评论引用 vals.ai 数据称 Neon 以约 40% 的成本达到 Fable 5.2 约 99% 的表现。上述对比均来自社区评论而非 Google 公布的数据，实际采用前应按自身任务重新评测。

**「社区讨论」** 在 Hacker News 的讨论中，有评论者对 Sol、Astra、Neon、Carbon 等层出不穷的模型名称表示疲劳，认为厂商内部清晰的使用场景划分并没有传达给外部用户。另有使用者称，尽管基准分数接近，实际使用中最新 Gemini 模型在整体智能感上仍不如 Anthropic 的 Opus 5.5；也有人指出 Google 把 Neon 定位为总体更聪明、而 Carbon 仍是“长时程”模型，并引用 vals.ai 的数据称 Neon 以约 40% 的成本达到 Fable 5.2 约 99% 的性能——这些均为评论者的个人判断或转述，未获原始材料确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/gemini/4-neon">Gemini 4 Neon | Gemini Enterprise Agent Platform | Google ...</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-neon/">Gemini 4 Neon - Model Card — Google DeepMind</a></li>

</ul>
</details>

**标签**: `#Gemini`, `#Google AI`, `#model release`, `#LLM benchmarking`, `#AI industry`

---

<a id="item-tech-news-3"></a>
### [Java4Shell：CVE-2026-114938 无需认证 RCE 漏洞](https://censys.com/advisory/cve-2026-114938/) ⭐️ 8.0/10

一则 Telegram 聚合帖称，Java 曝出无需认证的远程代码执行漏洞 CVE-2026-114938，CVSS 4.0 评分为 9.2，且已潜伏近 4 年。帖子列出的影响范围包括 Java 17（17.0.6 及之后全部 17 线）、21、25 和 27；标准 Java 8/11 通常不受影响，但 Oracle Java 8 Performance Pack 例外。该漏洞仅影响带 AVX-512 VBMI 的 x86-64 服务器处理器，大致对应 2021 年及以后发布的 Intel 处理器（Ice Lake 及更新世代 Xeon）和 2022 年及以后发布的 AMD 处理器（Zen 4 及更新 EPYC/Ryzen），ARM64 不受影响；帖子未提供补丁状态或独立验证信息。

telegram · zaihuapd · 11月18日 03:55

**「背景」** 该漏洞位于 OpenJDK 的 Base64 解码器，而不是应用层代码；在部分 x86-64 处理器上，Java 运行时会启用该解码器的一条优化实现。Sophos 的公告称，该漏洞于 2026 年 11 月 17 日公开披露，并指出评分存在口径差异：Oracle 按 CVSS 3.1 评为 8.1，发现者按 CVSS 4.0 评为 9.2。

**「影响」** 对运行 Java 17/21/25/27 且部署在支持 AVX-512 VBMI 的 x86-64 服务器上的组织，这意味着这些机器可能暴露于无需认证的远程代码执行；运营者需要按 CPU 指令集和 Java 版本盘点资产，并把 Oracle Java 8 Performance Pack 纳入例外排查。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-java4shell">Advisory: OpenJDK Base64 Vulnerability - Java4Shell (CVE-2026 ...</a></li>
<li><a href="https://blog.qualys.com/vulnerabilities-threat-research/2026/11/17/how-to-find-mitigate-and-patch-the-critical-java4shell-flaw-cve-2026-114938-now">How to Find, Mitigate, and Patch the Critical Java4Shell Flaw ...</a></li>

</ul>
</details>

**标签**: `#Java`, `#CVE-2026-114938`, `#remote code execution`, `#security vulnerability`, `#server infrastructure`

---

<a id="item-tech-news-4"></a>
### [Quad9 撤出法国：DNS 解析器不应承担反盗版拦截](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

在 Quad9 撤出法国后，一篇分析文章主张，DNS 解析器不应成为反盗版执法的落点：要求解析器屏蔽域名，会把版权执法转化为对网络基础设施的普遍过滤。文章讨论的是政策与法律争议，而非新的技术能力或独立测量结果；其核心问题是，DNS 层拦截把审查、隐私和法律责任压力转嫁给了解析器运营者。对法国用户和依赖公共 DNS 的机构来说，直接后果是可用解析服务的选择变少，并需要重新评估 DNS 过滤带来的隐私与合规风险。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「背景」** 法国法院此前就 beIN Sports 相关屏蔽命令，要求 Quad9 屏蔽被指传播未经授权体育直播的域名；Quad9 拒绝执行，并宣布于 2026 年 11 月 24 日停止向法国用户提供 DNS 解析服务。它因此成为第二家退出法国的 DNS 解析器，这次撤出同时影响其安全过滤和普通解析服务。

**「影响」** 对法国用户和机构而言，最直接的行动项是确认所用 DNS 解析器是否仍可用，并在必要时改用其他公共解析器、ISP 提供的 DNS 或自建解析器；分析认为，若把拦截义务继续压在 DNS 层，解析器运营者将面临要么配合过滤、要么退出市场的选择。

**「社区讨论」** 评论区对责任归属存在分歧：skrebbel 追问应把矛头指向误判的法院还是荒谬的立法，trentnix 则把不以起诉盗版者为核心的反盗版措施视为压制言论的后门。bemtevi 从用户体验出发认为，只有让正版观看更便宜、无 DRM 且更方便，才可能真正减少盗版。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://cyberinsider.com/quad9-to-leave-france/">Quad9 to leave France after court orders piracy-related DNS ...</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet censorship`, `#piracy`, `#privacy`, `#internet governance`

---

<a id="item-tech-news-5"></a>
### [Google DeepMind 宣布 Genie 4 可用，访问条件不明](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind 宣布 Genie 4 已可用，但提供的材料几乎没有模型能力、基准测试或地区支持范围的具体信息。评论者引述公告称，访问层级为“符合条件的 Google AI Ultra 订阅者”，不过该说法未在源内容中得到进一步说明。公告本身也未独立给出可验证的性能数据或兼容性条件。

hackernews · leumon · 11月18日 18:49 · [社区讨论](https://news.ycombinator.com/item?id=50550415)

**「背景：从研究预览到订阅开放」** Genie 是 Google DeepMind 的世界模型，可根据提示生成可交互环境。TechCrunch 在 2026 年 10 月 27 日报道称，Genie 4 以研究预览形式发布，新增实时音频、更逼真的世界和实时操控，并由 Gemini 负责规划步骤、检查生成帧；Google 的 Project Genie 页面则称 Google AI Ultra 订阅者现在可以用它生成带实时音频和编辑功能的交互式世界。

**「影响」** 对希望试用 Genie 4 的开发者而言，最直接的障碍是访问资格不透明：一位英国评论者称，其非 Workspace 的 Gmail 账户在 Ultra 订阅下仍只看到 Genie 3，且不确定限制来自地区还是账户类型；在官方说明缺失时，用户无法据此判断自己能否使用。

**「社区讨论」** 评论中最具体的经验是访问混乱：一位英国用户称 Ultra 订阅页面仍显示 Genie 3，无法判断是地区还是账户类型所致。另有评论者争论这类世界模型能否成为游戏引擎，或对其潜在负面后果表示不安，但这些都属于观点而非已验证的能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/">Project Genie update featuring Genie 4</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more realistic... | TechCrunch</a></li>

</ul>
</details>

**标签**: `#generative-world-models`, `#google-deepmind`, `#ai-model-release`, `#interactive-environments`, `#product-availability`

---

<a id="item-tech-news-6"></a>
### [微信小微测试日活达 3000 万，计划部分端侧推理](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

腾讯在 2026 年第三季度财报中表示，微信 AI 助手“小微”的测试范围已扩大，日活跃用户达到 3000 万，并正逐步接入微信聊天、朋友圈、公众号和视频号。腾讯称小微使用面向成本效率优化的 WeLM 定制模型，推理成本较低且持续下降；未来部分推理任务预计在用户设备端运行。上述用户规模与成本表述均来自腾讯，未披露独立测试结果或全面开放时间。

telegram · zaihuapd · 11月18日 11:35

**「背景」** 微信本身已是高频通信入口。第三方统计显示，其用户每日发送超过 450 亿条消息，并发起 4.1 亿次语音和视频通话，这为评估小微这类内嵌助手的测试规模提供了基数参照。

**「测试状态与端侧计划」** 小微仍处于测试阶段，日活达到 3000 万说明更多用户会在聊天、朋友圈、公众号和视频号中接触到它；但现有信息没有说明各场景的具体功能边界、支持机型或退出方式，用户不宜把它当作稳定可依赖的功能。腾讯只表示未来“预计”有部分推理在用户设备端运行，未给出时间表；若该计划实施，功能可用性和响应速度可能因手机性能而异。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://resourcera.com/data/social/wechat-statistics/">WeChat Statistics 2026 : Revenue, Users &amp; More (Global Data)</a></li>

</ul>
</details>

**标签**: `#WeChat`, `#Tencent`, `#AI assistant`, `#on-device inference`, `#consumer AI`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 用 FlyDSL MonoKernel 加速 AMD GPU 低并发解码](https://vllm.ai/blog/2026-11-18-flydsl-monokernels) ⭐️ 8.0/10

rss · vLLM Blog · 11月18日 00:00

**「背景」** 交互式代理要等当前解码结束才能调用下一个工具，低并发下响应速度比总吞吐更重要。小批量解码仍串行执行大量 GPU 内核，每个内核工作量很小，却要承担调度、启动和完成开销；HIP 图只减轻 CPU 启动成本。

**「方案」** 作者用持久化 MonoKernel 把多个依赖阶段放进一次启动：线程块跨阶段复用，前序计算时预取后续权重，用带标签邮箱传递中间结果，并在内核内完成跨 GPU 归约。边界按模型定制，如 DeepSeek-V4.1-Flash 将标准层拆为 K1（注意力前端、KV 缓存写入）和 K2（注意力后端、FFN、两次 TP all-reduce），MiniMax-M3 只融合 FFN。FlyDSL 让作者控制布局、同步和下精度矩阵指令，按模型、TP 和步宽即时编译；vLLM 保留调度器、KV 缓存、采样和 HIP 图，每步由 plan\(\) 选择 mono 或原生路径，默认关闭，不支持时启动即报错。作者报告，TP2 MI355X 同节点上 DeepSeek-V4.1-Flash 并发 1 的 P90 交互性从 318.1 升至 429.1 tok/s/user；GLM-5.2 在 TP8、MI350X 上把解码步从约 2459 个内核降至约 210 个，batch 1 每 token 从 13.70 ms 降至 5.92 ms。但收益集中在低并发，步宽受推测 token 与图填充限制，MI300X/MI325X 需额外权重副本，部分基线来自历史运行，部分配置的精度仍在评估。

**「启示」** 作者的核心结论是：在低并发交互式解码中，按模型定制持久化 MonoKernel、把调度、预取和跨卡通信压进单次启动，能在不替换 vLLM 其余栈的前提下显著降低延迟；代价是收益集中于低并发，且仍需逐模型验证精度和资源开销。

**标签**: `#LLM inference`, `#GPU kernel fusion`, `#vLLM`, `#AMD ROCm`, `#low-latency decoding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储会议纪要：官员预计还需加息，并担忧 AI 推升通胀](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

美联储 10 月会议纪要显示，几乎所有与会官员认为未来可能有必要进一步加息，以确保通胀及时回到 2%；当月美联储以 10 票赞成、2 票反对的结果将联邦基金利率目标区间维持在 3.75%至 4%。纪要还把人工智能相关需求列为“通胀风险的重要来源”，并警告 AI 相关债务快速膨胀且融资结构复杂不透明。

rss · CNBC Finance · 11月18日 19:41

**「背景」** 会议纪要记录的是美联储政策会议的讨论，并非新的利率决定；自那次会议以来公布的通胀数据仍显示物价涨幅远高于 2%目标。

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#AI financing risk`

---

<a id="item-finance-news-2"></a>
### [美联储理事沃勒称 12 月可能需加息 50 个基点](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

美联储理事克里斯托弗·沃勒 11 月 18 日表示，联邦公开市场委员会在 12 月 8 日至 9 日的会议上可能有必要将基准利率上调 0.5 个百分点，以更强力地遏制通胀；他称这可能意味着要“震慑”市场。

rss · CNBC Finance · 11月18日 15:13

**「背景」** 美联储在 2025 年因担忧就业市场而降息三次，但今年通胀重新升温，多数通胀读数高于 3%；美联储已于 9 月进行三年多来首次加息，并在 10 月按兵不动。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [美芯片新规引发合规担忧，五家银行暂停 4.8 亿美元字节跳动 GPU 贷款](https://www.bloomberg.com/news/articles/2026-11-17/banks-pause-480-million-chip-loan-tied-to-china-s-bytedance) ⭐️ 7.0/10

据彭博社报道，美国最新 AI 芯片出口管制出台后，五家银行暂停推进一笔 4.8 亿美元贷款，该贷款原计划为字节跳动在马来西亚的数据中心采购英伟达先进 GPU。借款方新加坡云服务商 Aolani Cloud 表示，正与监管机构和融资伙伴评估新规以确保合规。

telegram · zaihuapd · 11月18日 05:11

**「背景」** 美国此次收紧的规则针对包括马来西亚在内的东南亚数据中心芯片出口，并限制中国 AI 企业远程调用当地先进 AI 芯片，但对美国云服务公司设有豁免（tool-1-1、tool-1-3）。分析人士预计，这会让东南亚数据中心的建设和运营面临延期与成本上升，而非终止当地的 AI 建设（tool-1-1）。

**「影响范围」** 新规要求新加坡、马来西亚等国的数据中心运营商购买先进 AI 芯片须取得许可证，因此这些地区依赖英伟达 GPU 的云服务商和数据中心项目，可能同时遭遇采购审批延迟和融资收紧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U . S . chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>
<li><a href="https://forums.hardwarezone.com.sg/threads/us-to-restrict-chinese-remote-access-to-ai-chips-from-southeast-asian-data-centers-report.7231761/">US to restrict Chinese remote access to AI chips from Southeast...</a></li>
<li><a href="https://www.businesstimes.com.sg/companies-markets/telcos-media-tech/banks-pause-us480-million-chip-loan-tied-chinas-bytedance">Banks pause US$480 million chip loan tied to China’s ByteDance</a></li>
<li><a href="https://www.gate.com/news/detail/NVDA/bytedance-480m-loan-stalled-after-us-tightens-ai-chip-export-rules-25700410">ByteDance $480M Loan Stalled After US Tightens AI Chip Export ...</a></li>

</ul>
</details>

**标签**: `#US chip export controls`, `#ByteDance`, `#GPU financing`, `#data centers`, `#Nvidia`

---

<a id="item-finance-news-4"></a>
### [英国下议院通过移民与庇护法案](https://www.bloomberg.com/news/articles/2026-11-17/uk-s-house-of-commons-passes-controversial-immigration-bill) ⭐️ 7.0/10

英国下议院以 290 票赞成、94 票反对通过《移民与庇护法案》，法案拟将多数移民申请定居的基准居住年限从 5 年延长至 10 年，并提交上议院审议；目前尚未成为法律。

telegram · zaihuapd · 11月18日 05:51

**「背景」** 该法案于 2026 年 6 月 30 日提交下议院，并已完成二读和委员会阶段；它目前还不是法律，在下议院通过后仍需上议院审查。

<details><summary>参考链接</summary>
<ul>
<li>Immigration and Asylum Bill: Progress of the bill</li>
<li>UK MPs Reject Plan to Protect 5-Year Settlement ...</li>

</ul>
</details>

**标签**: `#UK immigration policy`, `#asylum reform`, `#residency rules`, `#health and social care visas`, `#House of Commons`

---

<a id="item-finance-news-5"></a>
### [腾讯 2026 年三季度营收逊预期，资本开支超预估](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布的 2026 年第三季度财报显示，营收 2073 亿元，同比增长 8%，低于市场预期；归母净利润 636 亿元，同比增长 0.8%。当季资本开支 814.33 亿元，远超市场预估的 554 亿元，单季自由现金流为负 691 亿元；腾讯还称，WorkBuddy 日均 Token 用量超过 100 万亿，为国内大语言模型产品最高。

telegram · zaihuapd · 11月18日 09:20

**「背景」** 资本开支指用于服务器、数据中心等长期资产的支出；此前百度也因 AI 算力投入增加而出现单季自由现金流为负（经营现金流不足以覆盖资本开支），显示这轮 AI 基础设施建设正普遍推高中国大型科技公司的支出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://robotbelt.com/baidu-q2-capital-spend-triples-ai-first-tier/">Baidu Q2 capex triples as Li Yanhong vows AI comeback</a></li>

</ul>
</details>

**标签**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#China tech`

---

<a id="item-finance-news-6"></a>
### [中韩宣布自贸协定服务与投资后续谈判实质性结束](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中韩两国于 11 月 18 日宣布，自贸协定服务与投资后续谈判已实质性结束；中国承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑、金融等领域的开放。双方还同意将视听节目共同制作范围从电影扩大到电视剧、动画、综艺和纪录片；目前这只是宣布的谈判节点（自 2018 年 3 月启动，历时约 8 年 8 个月），部分技术事项仍待工作层面协商，协议尚未最终签署生效。

telegram · zaihuapd · 11月18日 10:02

**「背景」** 中韩自贸协定服务与投资后续谈判于 2018 年 3 月启动，历时 8 年 8 个月；此次宣布的是谈判实质性结束，部分技术事项仍需在工作层面继续协商。

**「影响」** 若协议后续签署生效，韩国电影和游戏企业在中国市场将适用最惠国待遇，旅游、法律、建筑、金融等服务企业则受益于相关领域扩大开放，中韩合拍范围扩至电视剧、动画、综艺和纪录片也会影响内容制作合作；但目前仅为谈判实质性结束，部分技术事项仍待工作层磋商。

**标签**: `#China-South Korea FTA`, `#services and investment`, `#trade policy`, `#cultural industries`, `#market opening`

---