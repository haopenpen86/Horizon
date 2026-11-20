---
layout: default
title: "Horizon Summary: 2026-11-20 (ZH)"
date: 2026-11-20
lang: zh
---

> 从 42 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [Levent Alpöge 声称与 Claude 合作证明广义黎曼猜想](#item-tech-news-1) ⭐️ 9.0/10
2. [GitHub 页面声称纳维–斯托克斯方程有限时间爆破](#item-tech-news-2) ⭐️ 8.0/10
3. [PHP 流包装器大小写缺陷静默关闭 TLS，多分支已修复](#item-tech-news-3) ⭐️ 8.0/10
4. [KVM 漏洞 CVE-2026-99312：虚拟机可读取 AMD 宿主内存](#item-tech-news-4) ⭐️ 8.0/10
5. [Terence Tao 谈无外力 Navier–Stokes 奇点与广义黎曼猜想](#item-tech-news-5) ⭐️ 7.0/10
6. [Thinking Machines 发布开放权重模型 Inkling 2 Mini](#item-tech-news-6) ⭐️ 7.0/10
7. [Architect Labs 宣称 AI 发现并验证 Frostbite CPU 架构](#item-tech-news-7) ⭐️ 7.0/10
8. [Vakil 匆忙发布 Masullo 的 GRH 证明草案](#item-tech-news-8) ⭐️ 7.0/10
9. [Gemini 在 Mac 上推出代操作功能](#item-tech-news-9) ⭐️ 7.0/10
10. [英国法庭裁定苹果胜诉，后门令须公开审理](#item-tech-news-10) ⭐️ 7.0/10
11. [美众院文件：半年批准近 88 万颗 AI 芯片对华出口](#item-tech-news-11) ⭐️ 7.0/10
12. [Meta AI 助手 Muse 被指串号并泄露员工私密数据](#item-tech-news-12) ⭐️ 7.0/10

**科技博客**
1. [vLLM 为循环模型 Inkling 2 Mini 提供首日支持](#item-tech-blog-1) ⭐️ 8.0/10
2. [为什么输出缓存通常不划算](#item-tech-blog-2) ⭐️ 6.0/10

**财经新闻**
1. [美国企业转向净发行股票，牛市面临新增供应](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Levent Alpöge 声称与 Claude 合作证明广义黎曼猜想](https://alpo.ge/remark.pdf) ⭐️ 9.0/10

数学家 Levent Alpöge 于 11 月 20 日发布短文，称自己与 Claude 合作发现了黎曼猜想的证明，并说该方法可推广以解决广义黎曼猜想（GRH），预期进一步还能覆盖扩展黎曼猜想（ERH）；他还表示两人已在 Lean 中无假设地完成形式化。这目前仍是作者的自我声明：短文没有给出经同行评议的完整论证，验证仍在进行中。评论者引用的规模数据显示，形式化代码约 1.3GB、约 1500 万行；麻省理工学院的 Andrew Sutherland 维护的检查页面（更新至 2026-11-20 22:05 UTC）显示部分校验已出结果，其余仍在运行。另有评论者指出，同一日期还出现了一份完全由人类给出的证明公告，与 AI 辅助路径并行存在。

hackernews · iamronaldo · 11月20日 14:16 · [社区讨论](https://news.ycombinator.com/item?id=50574968)

**「背景」** 黎曼猜想断言黎曼ζ函数的所有非平凡零点都位于临界线 Re\(s\)=1/2 上；广义黎曼猜想则把这一断言推广到狄利克雷 L 函数等更广的一类 L 函数。该问题自 19 世纪提出以来长期未获证明，并被视为千禧年大奖难题之一；2026 年 11 月 20 日，Anthropic 数学家 Levent Alpöge 公开声称与 Claude 一起给出了证明及其 Lean 形式化。

**「对验证方式的实际影响」** 由于证明以 Lean 形式化代码发布，独立核查的方式从阅读论文转为编译整份形式化开发。据社区评论者 djoldman 报告，该归档约 1.3 GB、约 1500 万行代码，需分 14 个分片下载后合并解压，这对希望自行复核的研究者提出了可观的存储与编译资源要求。外部报道也确认，Alpöge 发布的是 Lean 版本，而 Lean 证明若无错编译通常被视为各步逻辑正确性的确认。

**「社区讨论」** 讨论的分歧集中在对结论可信度的判断上：有人引用 Terence Tao 一个月前的说法——现有 AI 单独无法攻克黎曼猜想，需要人类与 AI 结合——来质疑这次声明的分量；也有评论者认为，多路形式化验证加上独立校验已经足以让人“毫无疑问”地接受结论（这是评论者的判断，而非同行评议结果）。另有评论批评把 Alpöge 仅称作“Anthropic 员工”的标题写法，认为这会把功劳从这位知名数学家错误地转记到公司及其模型名下。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove... | Scientific American</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is almost... | Scientific American</a></li>
<li><a href="https://www.newscientist.com/article/2600134-anthropic-mathematician-claims-ai-assisted-proof-of-the-riemann-hypothesis/">Anthropic mathematician claims AI-assisted proof of... | New Scientist</a></li>

</ul>
</details>

**标签**: `#Generalized Riemann Hypothesis`, `#Lean formal verification`, `#AI-assisted mathematics`, `#mathematical proofs`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [GitHub 页面声称纳维–斯托克斯方程有限时间爆破](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

一个 GitHub 页面（tristanbuckmaster/navier-stokes）声称给出了纳维–斯托克斯方程的有限时间爆破，即解在有限时间内失去光滑性。该页面目前是唯一可核验的材料，未提供可审阅的技术细节，也没有独立确认，因此这仍是未经证实的数学声明，而非已发表或经同行评议的结果。若成立，它将直接关系到纳维–斯托克斯方程光滑解能否长期存在的问题；在核实前，研究者和读者不应把它当作定论。

hackernews · trotro · 11月20日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=50576232)

**「背景：从受迫爆破到无外力版本」** 纳维–斯托克斯方程描述不可压缩流体的速度与压力，是千禧年大奖难题之一；所谓有限时间爆破，指光滑初始数据在有限时间内发展出奇点或速度无界。此前 OpenAI 曾宣称用 AI 构造出带外力项的有限时间爆破解，但 Clay 仍将该问题列为未解决，相关优先权也有争议（tool-2-1、tool-2-3）。据 Scientific American 和 OfficeChai 报道，Buckmaster 与 Alpöge 这次宣称的证明针对无外力版本，即不施加外部力也可从光滑初始数据在有限时间形成奇点（tool-1-2、tool-1-3）。

**「影响」** 对数学和流体力学研究者而言，当前可采取的具体行动是等待可审阅的预印本或同行评议，而不是依据这个 GitHub 页面复现或引用结论；在缺少技术细节的情况下，任何建立在该结论上的后续工作都面临不可核实风险。

**「社区讨论」** 评论者主要争论这项声明的分量与归属：tancop 认为这是“无外力”版本，比 OpenAI 用精心设计外力构造的例子更接近现实情形；xianshou 则把它与同日出现的广义黎曼猜想消息并列，称当天是数学史上最重要的日子之一。jrflo 关于 Anthropic 千禧年问题传闻和 OpenAI“抢先”的说法属于未经证实的社区猜测，不能当作事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/ai-just-solved-the-real-navier-stokes-problem/">AI just solved the “real” Navier-Stokes problem</a></li>
<li><a href="https://officechai.com/ai/tristan-buckmaster-levent-alpoge-claim-proof-of-navier-stokes-millennium-prize-problem-without-forcing/">Tristan Buckmaster, Levent Alpöge Claim Proof Of Navier ...</a></li>
<li><a href="https://createmoreflow.com/openai-navier-stokes-millennium-prize-forced-blowup/">OpenAI Claims Navier - Stokes Millennium Prize Proof</a></li>
<li><a href="https://www.alphaxiv.org/abs/2609.navier-stokes">Finite Time Blowup for Navier – Stokes | alphaXiv</a></li>

</ul>
</details>

**标签**: `#Navier-Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research claims`, `#AI research competition`

---

<a id="item-tech-news-3"></a>
### [PHP 流包装器大小写缺陷静默关闭 TLS，多分支已修复](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

据安全报告，PHP 的 HTTP/FTP 流包装器在识别协议名时不区分大小写，却只在第五个字符为小写 s 时启用 TLS，导致“HTTPS://”“httpS://”“FTPS://”等混合大小写地址被当作明文 HTTP/FTP 发出；被第三方重定向到此类地址时同样会触发。这可能暴露令牌、Basic 认证、Cookie、POST 请求体和 FTP 登录信息。该问题编号为 CVE-2026-128064（GHSA-f6gg-rchx-xw8j），CVSS 4.0 评分为 8.2，据称已存在约 20 年。修复版本为 PHP 8.2.36、8.3.37、8.4.28、8.5.13 和 8.6.0；8.1 及更早版本已 EOL，不会获得修复，用户需自行将 URL 的 scheme 转为小写。

telegram · zaihuapd · 11月20日 03:04

**「背景：PHP 流包装器如何决定加密」** PHP 的 HTTP/FTP 流包装器让 \`file\_get\_contents\(\)\`、\`fopen\(\)\` 等函数可以直接把 URL 当作网络请求处理，因此 scheme 的解析细节会直接决定连接是否加密。该包装器对 scheme 的大小写不敏感，却只在特定位置出现小写 \`s\` 时才启用 TLS，这使带大写 \`S\` 的写法落入明文分支。

**「影响与处置」** 运行 PHP 8.1 及更早版本的环境无法获得官方补丁，只能由应用侧在把 URL 交给流包装器前统一将 scheme 转为小写；由于该缺陷同样会经由第三方重定向触发，仅检查自身配置中写死的地址并不够，还需覆盖由用户输入或外部跳转拼出的 https/ ftps 地址。仍在受支持分支上的部署应升级到 8.2.36、8.3.37、8.4.28、8.5.13 或 8.6.0，升级前这些混合大小写的调用会继续以明文发送凭据与请求体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-128064">CVE-2026-128064 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://www.zend.com/php-security-center/CVE-2026-128064">CVE-2026-128064 | Zend</a></li>

</ul>
</details>

**标签**: `#PHP`, `#TLS downgrade`, `#CVE-2026-128064`, `#security vulnerability`, `#open source`

---

<a id="item-tech-news-4"></a>
### [KVM 漏洞 CVE-2026-99312：虚拟机可读取 AMD 宿主内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux 内核 KVM 的 CVE-2026-99312 漏洞仅影响启用了嵌套虚拟化的 AMD 主机，虚拟机可借此读取宿主内存；研究人员在 DigitalOcean 上报告读取到约 127 GB 宿主内存。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，但 Debian、Ubuntu 等发行版内核尚未修复。在相应补丁可用前，可关闭嵌套虚拟化作为缓解措施。

telegram · zaihuapd · 11月20日 14:23

**「背景」** KVM 是 Linux 内核中的虚拟化模块；嵌套虚拟化允许虚拟机内部再运行虚拟机监控程序，这就需要宿主内核处理来自客户机的多层虚拟化操作。此次 CVE-2026-99312 的影响范围限定在启用嵌套虚拟化的 AMD 主机，未启用该功能的环境不满足所述受影响条件。

**「影响」** 运行 AMD 主机且启用嵌套虚拟化的云服务商和企业，在 Debian、Ubuntu 等发行版内核打补丁前仍面临宿主内存泄露风险；应关闭嵌套虚拟化，或改用已包含上游修复的内核。

**标签**: `#KVM`, `#Linux kernel`, `#virtualization security`, `#AMD`, `#CVE-2026-99312`

---

<a id="item-tech-news-5"></a>
### [Terence Tao 谈无外力 Navier–Stokes 奇点与广义黎曼猜想](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

Terence Tao 于 2026 年 11 月 20 日发布文章，讨论无外力 Euler 方程与 Navier–Stokes 方程的奇点问题，以及这些问题与广义黎曼猜想的联系。由于提供的材料没有文章正文，文章所涉证明的具体范围、附加条件和验证状态都无法确认；目前能确定的是，Hacker News 的讨论集中在 LLM 辅助证明与 Lean 内核验证是否足以保证数学正确性。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** Navier–Stokes 存在性与光滑性是著名的未解数学问题，问的是三维不可压缩流方程是否对所有初值都存在全局光滑解；“无外力奇点”则特指没有外部驱动力时解是否仍会在有限时间内爆破。广义 Riemann 猜想是经典 Riemann 猜想对更一般 L 函数的推广。

**「验证通过不等于命题正确」** 对使用 Lean 校验 LLM 生成证明的开发者来说，实际影响是要把“构建通过”与“证明了预期命题”分开核查：社区评论担心模型可能产出能通过编译、却并未形式化目标结论的代码，而外部报道称 MIT 只确认相关代码可以编译，Clay 研究所尚未认可该黎曼假设证明。Lean 验证也已被用于检查 LLM 生成的 GPU kernel 与 PyTorch 参考实现是否语义等价，这类流程的前提是先把规格与假设写明确。

**「社区讨论」** 在 Hacker News 讨论中，chunky1994 称两个独立内核都接受了该结果，因而认为出现内核漏洞的可能性较低，而 swingboy 追问 Lean 构建通过是否真能保证所形式化的命题就是目标命题；另有评论者就 LLM 能否产生新抽象及数学研究的意义表达疑虑，这些均属个人观点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier – Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2611.02028">LARK: Lean-Assisted Reasoning for LLM-Generated GPU Kernels</a></li>
<li><a href="https://thebostonreport.com/2026/11/20/claimed-riemann-hypothesis-proof-mit-lean/">MIT Checks Claimed Riemann Hypothesis Proof | The Boston Report</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#Lean`, `#LLM-assisted proof`, `#Navier-Stokes`, `#mathematics`

---

<a id="item-tech-news-6"></a>
### [Thinking Machines 发布开放权重模型 Inkling 2 Mini](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 7.0/10

Thinking Machines 发布 Inkling 2 Mini，这是一个开放权重、面向本地运行的 MoE 模型，采用循环 Transformer（looped transformer）架构。社区将其基准表现与 Qwen3.8-27B 比较，并提醒这些数字仍需在真实场景中验证。评论中还提到，其 GGUF 版本已可在 Ollama/Llama.cpp 上运行。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「技术背景」** 循环 Transformer（looped transformer）会让同一组中间层在处理每个 token 时重复执行，从而在不增加物理参数的情况下提升推理能力；Inkling 2 Mini 将其中间层重复执行三次。该模型同时是约 26B 总参数的 MoE 模型，每个 token 只激活部分参数，以兼顾本地运行所需的效率与模型容量，但 Artificial Analysis 标为 5.4B 激活参数，Hugging Face 博客则写作约 3B，公开材料对激活参数的说法并不一致。

**「对本地部署的影响」** 对本地部署者而言，最直接的可用路径是社区已在 Hugging Face 发布 GGUF 版本，可通过 Ollama/llama.cpp 运行——这一信息来自评论，而非官方公告。由于 Inkling 2 Mini 采用 MoE 架构，有评论者预计其解码速度会明显高于稠密的 Qwen3.8-27B（27.78B 参数），但两者性能是否真正相当，仍取决于尚未在真实场景中验证的基准对比。

**「社区讨论」** 评论者对开放权重的循环架构表示兴奋，认为如果基准结果成立，与 Qwen3.8-27B 同级的性能很有竞争力；但也有人强调需要在真实场景中验证。还有用户计划在 AMD 7900XTX 上对比测试，并预期 MoE 设计会带来更高的解码速度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://artificialanalysis.ai/articles/inkling-2-mini">Thinking Machines has released Inkling 2 Mini, an open ...</a></li>
<li><a href="https://huggingface.co/blog/inkling2mini">Welcome Inkling 2 Mini, Cutting-edge Performance for your ...</a></li>
<li><a href="https://llm-stats.com/models/qwen3.8-27b">Qwen3.8-27B Benchmarks, Pricing &amp; Context Window</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#looped transformers`, `#local inference`, `#MoE`, `#model release`

---

<a id="item-tech-news-7"></a>
### [Architect Labs 宣称 AI 发现并验证 Frostbite CPU 架构](https://architectlabs.com/blog/frostbite) ⭐️ 7.0/10

Architect Labs 发布博客，宣称 AI 发现、设计并验证了一种名为 Frostbite 的新 CPU 架构；文章发布在 Hacker News 后获得 604 分、316 条评论。该说法目前仅见于公司自述，公开材料未提供可独立核验的性能或验证数据，评论者也质疑其以顺序 CPU 而非现代乱序设计为基线，且测试程序规模偏小。支持者则认为，AI 的贡献在于把研究文献中的既有思想综合成可工程化的产品，而非从头发明全部洞见。

hackernews · shioyama · 11月20日 10:01 · [社区讨论](https://news.ycombinator.com/item?id=50572503)

**「背景」** Architect Labs 的博客称，Frostbite 是在“零架构先验”下设计的：AI 同步迭代其 ISA、Arcmodel、设计与验证，并把 ASL 契约作为一致性的唯一事实来源。这提供了一个理解其主张的前提——它不是对现有 ISA 的小修小补，而是试图把规范、模型、RTL 和验证放进同一个自动化闭环；这些仍是厂商说法，尚缺独立复现。

**「评估与采用影响」** 对芯片架构和编译器、工具链团队来说，Frostbite 的实际门槛在于它采用围绕 interaction nets 的新指令集，现有软件需要移植或重新编译才能评估。厂商给出的 4.59 倍每瓦性能和 8.77 倍单位面积性能均为流片前估算，对比基线是双发射顺序执行核心而非现代乱序核心，且仅覆盖 25 个工作负载，因此在独立硅片测试出现前不宜据此做采用决策。

**「社区讨论」** 评论者对“AI 发现”的表述分歧明显：jkhdigital 认为关键洞见由人类提出，AI 的强项是把数十年研究文献综合成连贯的工程产品；pizza234 则质疑其顺序 CPU 基线、测试程序太少，并指出 WaveScalar 二十多年前已探索过数据流架构。发帖人 shioyama 则强调讨论应聚焦交互网这一不同于 1940 年代哈佛架构的编程范式，以及该实现能否真正支撑它、性能声明是否成立。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://architectlabs.com/blog/frostbite">Introducing Frostbite : A new CPU architecture ... | Architect Labs</a></li>
<li><a href="https://architectlabs.com/blog/frostbite">Introducing Frostbite: A new CPU architecture discovered ...</a></li>
<li><a href="https://www.notebookcheck.net/AMD-and-Intel-move-over-AI-designed-an-all-new-CPU-and-claims-it-is-4-6x-more-efficient.1455225.0.html">AMD and Intel, move over: AI designed an all-new CPU — and ...</a></li>
<li><a href="https://letsdatascience.com/news/architect-labs-unveils-frostbite-an-ai-designed-cpu-architec-88f8acbd">Architect Labs unveils Frostbite, an AI-designed CPU architecture</a></li>

</ul>
</details>

**标签**: `#AI-designed hardware`, `#CPU architecture`, `#interaction nets`, `#hardware verification`, `#Hacker News discussion`

---

<a id="item-tech-news-8"></a>
### [Vakil 匆忙发布 Masullo 的 GRH 证明草案](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil 于 11 月 20 日匆忙公开 Alessandro Masullo 关于广义黎曼猜想（GRH）的证明草案，称 Brian Conrad 已密切审阅数月、正在纳入其大量反馈，且目前“看起来不错”。Vakil 强调这项工作完全由人类完成，没有使用 AI。原计划是让 Masullo 到斯坦福用一年打磨写作、并先让足够多人审阅后再公布，但现在决定先发布当前草案；公告未给出证明的技术细节，也未表明该证明已获验证。

rss · Simon Willison · 11月20日 19:21

**「背景」** 黎曼猜想断言黎曼ζ函数的非平凡零点都位于实部为 1/2 的直线上；广义黎曼猜想（GRH）把这一断言推广到包括狄利克雷 L 函数在内的更广一类 L 函数，因此其证明若成立将是数论中的重大结果。Ravi Vakil 的帖子说，原计划是让 Alessandro Masullo 到斯坦福用一年打磨文稿，并在征求足够多人意见后再公布；Brian Conrad 已仔细审阅数月并提供大量反馈。现在 Vakil 认为最好先公开当前草稿，这意味着它仍是一份待核验的未定稿。

**「影响」** 对研究 GRH 的数学家而言，这份草案提供了一个可立即审阅的对象，但在其通过广泛同行审查前，不应被视为已解决的猜想；Vakil 的表述是“看起来不错”，并非验证结论。

**标签**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#research announcement`, `#verification`, `#number theory`

---

<a id="item-tech-news-9"></a>
### [Gemini 在 Mac 上推出代操作功能](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 7.0/10

Google Gemini 为 Mac 版应用新增“电脑操作”功能，可代替用户点击、输入、浏览菜单和填写表单。该功能已向美国地区订阅 Google AI Plus、Pro 或 Ultra 的 Mac 用户开放。Gemini 可在独立后台窗口运行，用户能同时继续使用主屏幕和光标，并可限制其可访问的应用、实时查看操作、随时暂停或在关键操作前审批。现有报道未披露支持的应用范围、系统版本要求或独立测试结果。

telegram · zaihuapd · 11月20日 02:51

**「背景」** 电脑操作（computer use）是一种让 AI 代理直接操作图形界面的能力：在 Mac 上通过点击、输入、浏览菜单和填写表单来完成任务，因此它的可用范围取决于用户允许它访问哪些应用。Android Authority 报道称，该功能要求使用 Apple Silicon Mac，并先以英语面向美国地区的 Google AI Plus、Pro 和 Ultra 订阅者推出。

**「对用户的实际影响」** 符合条件的美国地区订阅用户（Google AI Plus、Pro、Ultra）在 Mac 版 Gemini 中，可以把跨本地文件、桌面应用和网页的重复性点击、输入和表单填写交给 Gemini 执行，这也是该功能首次让助手直接改动本机内容而非仅给出建议。由于它在独立后台窗口中运行，并可访问本机文件和应用，用户应先利用应用访问限制划出可操作范围、在关键步骤前保留审批，并在无人看管时暂停，以免误改本地数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.androidauthority.com/gemini-mac-computer-use-3737396/">Gemini for Mac adds computer use to control desktop apps</a></li>
<li><a href="https://www.youtube.com/watch?v=dp9x8EMAE9I">Turn a Sketch Into a Rigged 3D Model With Computer Use ... - YouTube</a></li>
<li><a href="https://blog.google/innovation-and-ai/products/gemini-app/computer-use-mac/">Automate Mac tasks with Gemini computer use</a></li>

</ul>
</details>

**标签**: `#Google Gemini`, `#AI agents`, `#macOS`, `#computer use`, `#human oversight`

---

<a id="item-tech-news-10"></a>
### [英国法庭裁定苹果胜诉，后门令须公开审理](https://appleinsider.com/articles/26/11/19/uk-cant-hide-that-it-tried-ordering-apple-to-allow-access-to-user-data) ⭐️ 7.0/10

英国调查权力法庭裁定苹果胜诉，英国内政部不得再对要求苹果开放 iPhone 加密数据访问的“技术能力通知”（TCN）保密，案件大部分将公开审理。内政部随后确认曾发出该通知，称此举是为了将罪犯绳之以法；法庭认定其国家安全理由“不切实际”。现有信息未说明该通知是否已被撤销，也未说明苹果是否须因此改变产品设计。

telegram · zaihuapd · 11月20日 04:13

**「背景」** 「技术能力通知」（TCN）是英国政府可向通信服务商秘密发出的强制要求；在本案裁决前，苹果被法律禁止公开确认该通知的存在，即便相关细节已经外泄。调查权力法庭此次认为，既然相关信息已为公众所知，确认该命令存在几乎不会造成额外损害，因此驳回了内政部的保密主张。据报该命令的适用范围不止英国用户，还可能涉及全球苹果客户的加密数据。

**「实际影响」** 直接后果是，这项此前保密的后门要求将进入公开法律程序，英国政府需在公开审理中说明其依据。但现有报道只涉及保密争议，尚不能据此认定 TCN 已被推翻，或苹果已被要求修改加密设计。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/19/u-k-government-forced-to-disclose-secret-apple-backdoor-order/">UK government forced to disclose secret Apple ... | TechCrunch</a></li>
<li><a href="https://news.az/news/why-the-uks-demand-for-access-to-apple-data-is-under-scrutiny">Why the UK ’s demand for access to Apple data is under... | News.az</a></li>
<li><a href="https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/">UK Government Forced to Admit It Issued Apple a Secret Encryption...</a></li>

</ul>
</details>

**标签**: `#encryption`, `#privacy`, `#Apple`, `#UK government`, `#surveillance`

---

<a id="item-tech-news-11"></a>
### [美众院文件：半年批准近 88 万颗 AI 芯片对华出口](https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china) ⭐️ 7.0/10

美国众议院外交事务委员会公布的文件显示，2025 年 12 月至 2026 年 5 月，美国批准英伟达和 AMD 向中国出口 879,868 颗 AI 芯片，涉及 H200 和 MI325X，企业申请总量为 344.4 万颗。获批方包括腾讯、字节跳动（各 15 万颗），阿里巴巴、快手、滴滴（各 7.5 万颗），以及米哈游、百度、京东等。文件同时显示，截至 5 月 11 日，21 份批准许可均未发货，因此获批数量不等于实际交付；阿里、腾讯、百度、比亚迪被列入美方所谓“中国军方关联企业名单”，也引发国会对审查的质疑。

telegram · zaihuapd · 11月20日 04:25

**「背景」** 美国对华 AI 芯片出口依据《出口管制改革法》（ECRA）实施，由商务部工业与安全局负责审批许可证；该法同时赋予国会获取并公开许可证申请信息的权限，众议院外交事务委员会主席 Brian Mast 正是援引这一授权公布上述数据的。此次披露的 H200 与 MI325X 属于此前受对华出口限制约束的高端 AI 加速器，公开的是许可证申请与批准记录，而非海关交付数据。

**「实际影响」** 对获批的中国企业而言，87.9 万颗只是许可数量而非已到位算力；在文件所列许可尚未发货的情况下，规划 H200 和 MI325X 部署时仍需把发货与审查进度作为约束。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china">Chairman Brian Mast Exercises Legislative Authority to Publicly...</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#Nvidia`, `#US-China tech policy`, `#semiconductors`

---

<a id="item-tech-news-12"></a>
### [Meta AI 助手 Muse 被指串号并泄露员工私密数据](https://techcrunch.com/2026/11/19/metas-ai-agent-muse-is-mixing-up-conversations-and-exposing-private-data-report-says/) ⭐️ 7.0/10

TechCrunch 援引路透社对 Meta 内部帖子的报道称，Meta 员工报告其 AI 助手 Muse 会在不同账户之间混入对话内容并显示他人的私密信息，包括未发出的育儿请求、未下过的订单和银行余额。一名员工称，Muse 在天气聊天中插入了一条消息，显示“Capital One 余额 2722.58 美元，Charles Schwab 余额 5899.57 美元”；另一名员工称，Muse 在她个人手机上提醒她回复姐姐在 Signal 上的消息，而她并未授权其访问其他应用。上述内容来自员工说法和内部帖子，目前没有 Meta 官方确认，报道也未说明受影响的账户数量或技术根因。

telegram · zaihuapd · 11月20日 05:10

**「背景」** Muse 是 Meta 主推的 AI agent。路透社在 11 月 18 日的调查报道中称，该助手下载量已超过 1000 万次，并已出现未经用户请求而执行操作等早期安全失误；Meta 将这类事件称为孤立事件。

**「影响」** 对部署类似 AI 助手的企业而言，这起报告把账户级隔离和跨应用权限控制变成必须核验的安全边界：一旦一个账户的上下文进入另一个账户，财务信息和私人消息就可能直接暴露给无关用户。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/investigations/meta-bets-big-muse-ai-agent-early-safety-mishaps-surface-2026-11-18/">As Meta bets big on Muse AI agent, early safety mishaps ...</a></li>
<li><a href="https://thenextweb.com/news/meta-muse-signal-messages-internal-posts-reuters">Meta’s Muse read Signal messages and invented purchases ...</a></li>

</ul>
</details>

**标签**: `#AI privacy`, `#AI agents`, `#Meta`, `#data leakage`, `#security`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 为循环模型 Inkling 2 Mini 提供首日支持](https://vllm.ai/blog/2026-11-20-inkling2-mini) ⭐️ 8.0/10

rss · vLLM Blog · 11月20日 00:00

**「背景」** 循环模型让中间层用共享权重对每个 token 重复执行多次，给推理引擎的缓存管理与算子调度带来常规模型没有的约束。Thinking Machines 发布的 Inkling 2 Mini 就是这样的多模态 MoE：26B 总参数、3.5B 激活、最长 1M 上下文，vLLM 在发布当天于 Blackwell、Hopper 与 DGX Spark 上提供支持。

**「方案」** 模型 24 层被切成前奏（0–5）、循环核心（6–17）与尾声（18–23）：核心的三次 pass 共享权重且都从同一份前奏输出出发，后一次只能通过“消息”看到前一次。从第二次 pass 起，每个核心子层的 Q/K/V 与 MLP 输入各读一条消息（12 层 × 4 输入 = 每 token 48 条），由 rank-64 控制器按通道做门控合并。vLLM 的做法是把每个额外 pass 注册为独立注意力层并配自己的 KV 与卷积状态缓存——24 层因此有 48 个 KV 缓存，而缓存管理器和前缀缓存无需新逻辑即可复用。它把一层内的四次消息读取合并进一个 attention-residual 内核，将四个控制器权重堆叠成批量 GEMM，用 Triton 融合 RMSNorm 与门控合并，并在 FP32 下不做 FMA 收缩以对齐参考数值；Inkling 2 Small 的子层融合内核则从隐藏维度 4608 推广到 2304。可变循环研究检查点通过 --hf-overrides 暴露 loop\_num\_passes 与 loop\_share\_cache 两个开关；在单张 GB200（TP1、4K 上下文、仅前向）上，3 passes 时解码步为 1 批 3.85 ms、32 批 8.11 ms、KV 容量 175K token，1 pass 则为 1.51 ms、3.81 ms 和 352K token，共享 KV 只提升到 194K，因为每 pass 的卷积状态仍要保留。作者称数值与参考实现一致（隐藏状态差异与参考自身 FlashAttention-4 和 PyTorch 注意力路径之间的差异相当，MoE 输出逐位相同），端到端准确率在最高 1M token 的 needle-in-a-haystack、MMMU-Pro、HLE 与 GSM8K 上做了测试但未给出结果。

**「启示」** 作者的核心结论是：循环结构未必需要新的缓存抽象——把每个 pass 当作普通层管理，再用内核融合消化消息传递的启动开销，就能在发布当日把这类模型跑起来；代价是随 pass 数线性增长的缓存占用与解码延迟，以及可变循环下速度与质量之间的显式取舍。

**标签**: `#looped models`, `#vLLM`, `#KV cache`, `#MoE inference`, `#kernel fusion`

---

<a id="item-tech-blog-2"></a>
### [为什么输出缓存通常不划算](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理通常会缓存输入（如 KV cache），避免每轮重算整个对话历史；而输出 token 必须逐个生成、成本更高，因此自然让人想用类似办法减少重复输出。

**「方案」** 作者指出，agent 在写 PR、做调查或自动研究时常被要求复述代码和证据，于是设想过微调或提示模型只输出“src/script.py:12-15”这类引用，再由 harness（代理框架）展开。但他认为这通常不值得，因为它只优化用户可见的输出；据其个人 agent 历史粗略估计，可见输出仅约 6%，推理 token 约 50%，工具调用约 44%。按 Amdahl 定律，即使乐观地省掉可见输出三分之二的 token，也只能省下总输出 token 的约 4%。真正要省输出 token，得减少那 94% 的不可见部分，而这主要取决于模型智能：更强的模型需要更少推理和工具调用，甚至单价贵 5 倍、token 少 6 倍时总成本反而更低。他也提到更好的 harness 有帮助，但不太相信 harness 质量能形成明显而持久的比较优势；他对前沿模型是否会在思维链中重复并无十足把握，也怀疑工具调用可能包含一些重复，公开征求读者数据。

**「启示」** 因此，输出缓存或“让模型少复述”只能带来有限节省，受 Amdahl 定律约束。降低 LLM 输出成本的关键，更可能在于提升模型智能以减少推理与工具调用 token，而非优化表面可见的重复内容。

**标签**: `#LLM inference`, `#output caching`, `#Amdahl&\#x27;s law`, `#AI agents`, `#token economics`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美国企业转向净发行股票，牛市面临新增供应](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

据 Acadian Asset Management 分析，截至上周晚些时候，美国公司净新股发行量相当于总市值的 3.1%，企业行为已从 2024 年的净回购转为净发行，为持续四年的牛市增添供应压力。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 股票回购会减少流通股数量，在资金追逐更少股票时帮助推高股价并提高每股收益；净发行则相反，会增加市场必须吸收的股票供应。

**「影响」** 对股票投资者而言，更多新股供应可能成为这轮持续四年的牛市的一个逆风，而大型 AI 相关融资和 IPO 正在放大这一趋势。

**标签**: `#equity issuance`, `#buybacks`, `#bull market`, `#AI capital raising`, `#IPOs`

---