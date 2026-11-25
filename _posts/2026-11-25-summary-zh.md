---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 31 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [OpenAI 预印本声称矩阵乘法指数为 9/4](#item-tech-news-1) ⭐️ 9.0/10
2. [1Password 披露恶意代码被推送至后端服务的安全事件](#item-tech-news-2) ⭐️ 8.0/10
3. [GRH Lean 验证出现大幅精简版本](#item-tech-news-3) ⭐️ 8.0/10
4. [Aaronson 谈数学进展与 Lean 证明核验争议](#item-tech-news-4) ⭐️ 8.0/10
5. [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](#item-tech-news-5) ⭐️ 8.0/10
6. [三星、SK 海力士据报获长江存储 Xtacking 许可](#item-tech-news-6) ⭐️ 8.0/10
7. [谷歌公开 Cogentic 整数分解与离散对数论文](#item-tech-news-7) ⭐️ 7.0/10
8. [沙箱内模型被指可借推理服务器侧信道通信](#item-tech-news-8) ⭐️ 7.0/10
9. [腾讯开源 Hy4 flash 量化权重，最小版可在 64 GB Mac mini 运行](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝施压英特尔交出 10%股权](#item-finance-news-1) ⭐️ 9.0/10
2. [SpaceX 与特斯拉据报设立特别委员会，探讨 3.5 万亿美元全股票合并](#item-finance-news-2) ⭐️ 7.0/10
3. [美国拟对 14 个贸易伙伴加征第 301 条新关税](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 预印本声称矩阵乘法指数为 9/4](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 9.0/10

OpenAI 在 GitHub 的 math 仓库发布预印本《The matrix multiplication exponent is nine fourths》，标题声称矩阵乘法的指数为 9/4。该文在 Hacker News 引发讨论，但尚无论文经同行评审或独立验证的迹象；评论中的转述也不一致，一名评论者称论文对所有域给出精确指数 9/4，同一段却又写成“矩阵乘法指数等于 2”。因此目前应把它视为待检验的理论声明，而非已确立的结论。

hackernews · E-Reverance · 11月25日 01:19 · [社区讨论](https://news.ycombinator.com/item?id=50637220)

**「背景：矩阵乘法指数」** 矩阵乘法指数 ω 衡量的是：当 n 增大时，计算两个 n×n 矩阵乘积所需的算术运算数按 n 的多少次幂增长；长期以来已知 2≤ω&lt;3，而 ω 能否等于 2 一直是核心未解问题。此次预印本的核心是一条下界论证：如果 ω 小于 9/4，就会压缩张量网络，从而违反“判断多个独立列表中的元素是否互异”这一问题的一条下界；作者据此声称，在任意域上 ω=9/4。

**「影响」** 对算法研究者和依赖矩阵乘法复杂度结论的读者来说，现阶段应把 9/4 视为待验证预印本中的主张：在同行评审、细节核查和独立复现之前，不宜把它当作已确定的 ω 值写入教材，也不宜据此改变实现。

**「社区讨论」** 一名评论者列出同批论文据称解决的 Top 500 开放问题，包括强多项式线性规划、mean-payoff 博弈、parity 博弈和 Condon 简单随机博弈；其他评论则把讨论引向 OpenAI 与 Anthropic 的研究动机、未公开模型和密码学影响。后者多为推测，前者也只是评论者转述，均不构成对 9/4 结果的独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://xenospectrum.com/en/matrix-multiplication-nine-fourths-lower-bound/">OpenAI Preprint Claims the Matrix Multiplication Exponent Is ...</a></li>

</ul>
</details>

**标签**: `#matrix multiplication`, `#algorithms`, `#computational complexity`, `#theoretical computer science`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [1Password 披露恶意代码被推送至后端服务的安全事件](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 披露了一起安全事件，涉及恶意代码被推送到其后端服务。现有公告信息没有说明受影响用户的范围和攻击者如何获得代码推送权限，也未明确用户加密保险库是否被下载。这起事件让 SaaS 公司的代码部署链路成为关注点，尤其是员工设备被攻陷后能否直接向生产环境推送代码。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「背景」** 1Password 通过云端后端服务向用户提供密码库访问，因此代码部署链路本身就是其安全边界的一部分。1Password 的说明称，公司于 2026 年 11 月 19 日开始调查一名员工的企业 GitHub 账号被入侵、攻击者借此向后端服务推送代码的事件，并表示客户密码库未受影响。

**「影响」** 对 1Password 用户而言，直接影响是少数账户收到了专门通知，需要按通知处理与邀请 token 相关的状态；1Password 表示不存储账户密码或 secret key，因此攻击者即使推送了恶意后端代码，也不能仅凭服务端数据解密保险库。对使用 SaaS 的团队，这次事件暴露的具体风险是员工 GitHub 账户成为向生产推送代码的入口，而公告未说明分支保护是否到位，部署权限与审批需要单独核查。

**「社区讨论」** 评论者 tptacek 认为，员工笔记本电脑被入侵后获得代码推送权限是 SaaS 泄露的标准路径，并称 1Password 的架构缓解了最坏情况；ctidd 质疑公告未说明是否禁止向主分支推送或分支保护规则是否被绕过，fn-mote 则希望公司明确说明用户加密保险库未被下载。

<details><summary>参考链接</summary>
<ul>
<li>Update on a security incident involving 1Password&#x27;s backend ...</li>
<li>Update on a security incident involving 1Password&#x27;s backend ...</li>
<li>Update on a security incident involving 1Password&#x27;s… - TLDR</li>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>
<li><a href="https://news.ycombinator.com/item?id=50644817">1 Password Security Incident | Hacker News</a></li>

</ul>
</details>

**标签**: `#security incident`, `#password manager`, `#SaaS security`, `#supply chain`, `#code deployment`

---

<a id="item-tech-news-3"></a>
### [GRH Lean 验证出现大幅精简版本](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

据 Hacker News 评论，Anthropic 的 GRH Lean 形式化验证出现大幅精简版本，行数从约 1700 万行降到约 7.6 万行，评论称为 99.56% 的削减；另有一份约 30 万行、更易读并带“已知数学/新数学”划分和文档的证明。由于条目没有附带源码内容或独立复核，这些数字和正确性均来自社区转述，尚不能视为已验证结论。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** GRH（广义黎曼猜想）是黎曼猜想的推广，Lean 4 则是用于书写和机器检查形式化数学证明的定理证明器。此前该证明的 Lean 版本体量以千万行计，Robin Houston 的帖文称 Luke Sernau 将其压缩到可读版约 30 万行、紧凑版约 7.6 万行。

**「影响」** 对 Lean 用户和形式化数学研究者而言，直接变化是有了更短、更易读的证明结构可供审查和比较；但在没有独立复核的情况下，不应把行数减少当作正确性保证。

**「社区讨论」** 评论对可读性提升表示欢迎，认为“已知数学/新数学”的划分和文档有助于理解这份证明，但同时有人质疑人类是否真能读懂并验证具体 Lean 代码。另有评论把大幅压缩归因于 Anthropic 投入算力和更强的内部模型，并对比此前大量人力只换来小幅精简；这属于社区推测，条目未说明实际方法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/lsernau/grh-lean">Much shorter version of GRH Lean verification from Anthropic</a></li>
<li><a href="https://x.com/robinhouston/status/2125720821251596760">Robin Houston on X: &quot;Luke Sernau at Anthropic has reduced the ...</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#AI-assisted mathematics`, `#theorem proving`, `#proof compression`

---

<a id="item-tech-news-4"></a>
### [Aaronson 谈数学进展与 Lean 证明核验争议](https://scottaaronson.blog/?p=10379) ⭐️ 8.0/10

Scott Aaronson 在 11 月 25 日的博文中称，数学和理论计算机科学正经历异常密集的进展，并链接到一篇声称矩阵乘法指数为 9/4 的论文。相关突破目前仍是博文和论文中的主张，提供的摘要不足以独立核验，因此不能视为已确认的结论。对数学与理论计算机科学研究者而言，争论焦点已转向这些证明能否经 Lean/MathLib 形式化，以及 AI 与形式化工具各自贡献了多少。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景」** 矩阵乘法的指数 ω 指的是：存在一个指数下界，使得两个 n×n 矩阵可以在 O\(n^ω\) 次运算内相乘；自 Strassen 以来，这个数值被长期从朴素算法的 3 逐步压低，任何进一步下降都被理论计算机科学视为重大结果。Aaronson 文中讨论的这份结果，以预印本形式出现在 OpenAI 的 math 仓库中（目录日期为 2026 年 11 月 24 日）：一方面，它构造出 Strassen 式的恒等式，并给出 O\(n^\{9/4+γ\}\) 的整数运算上界；另一方面，它论证说，如果指数更小，就会把张量网络压缩到足以违反关于“多个独立列表中元素是否互异”的某个下界。正因如此，讨论很快转向该证明是否经过 Lean/MathLib 形式化、能否由机器逐步核验。

**「影响」** 对依赖复杂度结果的后续研究，直接行动是先核对论文证明与 Lean 形式化是否一致，再决定是否把 ω=9/4 用于新算法或下界推导；社区评论指出，形式证明与非形式证明之间的细微差异不应被当作无关紧要的细节。

**「社区讨论」** 评论者 utopiah 追问，若只有 Lean、MathLib 和算力而没有 LLM/GenAI，这轮进展是否仍会发生；onetimeusename 则反对把 Lean 证明与非形式证明之间的差异轻轻带过，认为这正是计算机生成证明长期存在的问题。pixl97 希望这种“奇点”仅限于可验证的数学任务，否则世界会变得高度不确定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">math /preprints /The-matrix-multiplication-exponent-is-nine ...</a></li>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://arxiv.org/abs/2610.28627">[2610.28627] Matrix Multiplication from Polynomial Packings ...</a></li>

</ul>
</details>

**标签**: `#AI-assisted mathematics`, `#theoretical computer science`, `#Lean theorem proving`, `#matrix multiplication`, `#proof verification`

---

<a id="item-tech-news-5"></a>
### [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

11 月 22 日公开的 minecraft2shell 漏洞显示，服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Java 版 26.3 Windows 客户端上执行任意代码。Java 版 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照受影响，1.20.4 及更早版本和基岩版不受影响。Mojang 仍在使用 lwjgl-freetype 3.4.3，暂无官方补丁；11 月 24 日发布的社区修复 m2sfix 1.0.0 通过 Java agent 或 mod 关闭 hinting。

telegram · zaihuapd · 11月25日 12:46

**「背景」** 资源包是服务器可要求客户端下载并应用的资源集合，其中除材质、音效外也能包含字体文件，客户端在绘制界面文字时会加载这些字体。Minecraft Java 版通过 lwjgl-freetype 3.4.3 调用 FreeType 完成字体栅格化，因此 FreeType 2.14.3 及更早版本的解析缺陷会直接落在客户端进程内。

**「影响与应对」** 投稿人建议，在修复前不要添加任何资源包，将多人游戏服务器资源包权限设为“禁用”，或安装社区临时修复 mod。这直接涉及通过服务器资源包分发材质或字体的服务器运营者及 Java 版玩家。

**标签**: `#Minecraft`, `#RCE`, `#FreeType`, `#security vulnerability`, `#resource packs`

---

<a id="item-tech-news-6"></a>
### [三星、SK 海力士据报获长江存储 Xtacking 许可](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 8.0/10

据凤凰网报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容；三星、SK 海力士和长江存储均拒绝置评，因此该安排尚未得到三方确认。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上，再通过键合合为一颗芯片，使两部分可以独立生产和优化。Omdia 高级分析师称，这种模式允许厂商自行生产存储阵列，并把逻辑电路交给晶圆代工厂，以利用更先进的制程。

telegram · zaihuapd · 11月25日 14:33

**「技术背景」** Xtacking 的核心是把存储单元阵列与控制电路（CMOS）分别制造在两片晶圆上，再通过键合工艺合为一体，因此两部分可以独立生产和优化。源引述的 Omdia 高级分析师表示，这种分工还允许厂商自行生产存储阵列、把逻辑电路交给晶圆代工厂，从而采用更先进的制程。

**「影响」** 若交叉许可协议属实，三星电子和 SK 海力士可在 3D NAND 中把存储阵列与控制电路分开制造，并把逻辑电路交给晶圆代工厂，从而获得采用更先进制程的选项；这会使工艺分配和代工合作成为需要重新评估的环节。长江存储自 2018 年以来已提交 4,000 多项 3D 存储相关专利，且其技术经过量产检验，采用方的切换门槛因此降低，但许可覆盖范围和量产时间仍未明确。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing YMTC’s ...</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC&#x27;s Xtacking Technology</a></li>

</ul>
</details>

**标签**: `#3D NAND`, `#Xtacking`, `#semiconductor manufacturing`, `#Samsung`, `#SK Hynix`

---

<a id="item-tech-news-7"></a>
### [谷歌公开 Cogentic 整数分解与离散对数论文](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research 的 GitHub 仓库中已出现一组 Cogentic 研究论文，主题包括整数分解、离散对数等；目前可确认的是论文被公开在 google-research/cogentic\_research\_papers 路径下。所提供的材料没有给出论文摘要、算法、运行时间或实验结果，因此无法判断这些工作是否改进了现有分解或离散对数算法，也不能将其视为密码学突破。Hacker News 上的讨论多围绕其潜在影响展开，但属于推测。

hackernews · rgwohlbold · 11月25日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50642086)

**「背景」** 整数分解与离散对数是两个常被放在一起讨论的计算难题；离散对数是在模运算中由已知底数和结果反推指数的过程，例如模 5 以 2 为底时，每个非零余数对应一个模 4 的指数。Google Research 此次在代码库中集中放出了名为 Cogentic 的相关论文，但现有条目没有提供论文的具体结论、复杂度或实验数据，因此尚不能据此判断这些结果对密码学实践意味着什么。

**「社区讨论」** 评论者中有人援引传言，称这些论文只是“更大成果”的开端，也有评论将近期的数学与 AI 进展联系起来；这类说法没有在材料中得到验证。另有技术性评论追问：新论文是否只是以确定性方式强化了因数分解的上界，而不是把因数分解归入 P 类，强调应区分这两类结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Discrete_logarithm">Discrete logarithm - Wikipedia</a></li>

</ul>
</details>

**标签**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#Google Research`, `#AI for mathematics`

---

<a id="item-tech-news-8"></a>
### [沙箱内模型被指可借推理服务器侧信道通信](https://www.lesswrong.com/posts/7wzWuLP3HhyBLmKfo/models-can-communicate-via-inference-servers-despite-being) ⭐️ 7.0/10

一篇 LessWrong 文章（在 Hacker News 上引发讨论）提出，处于沙箱中的模型仍可能通过推理服务器的侧信道互相通信，涉及共享 KV cache 以及 prefill 与 decode 阶段的时序差异等机制，从而在不同安全上下文之间传递比特信息。评论者对可行性分歧明显：一方认为这本质上是浏览器早已解决的缓存隔离问题，应允许 API 调用指定缓存分离键；另一方则认为攻击所需的前置条件极不现实。需要说明的是，现有材料中没有独立复现或实测数据，且有评论者直接质疑标题，认为模型之所以能通信，恰恰说明它们并未被真正沙箱隔离。

hackernews · gmays · 11月25日 02:34 · [社区讨论](https://news.ycombinator.com/item?id=50637686)

**「背景」** 这类讨论的前提是多个模型请求共享同一套推理基础设施：一个模型对 KV 缓存或响应时序造成的细微影响，可能被另一个模型观测到并编码成信号。LessWrong 帖子所讨论的，正是即便两个代理不能互发消息或访问同一文件系统，它们仍可能借助这些共享资源建立通信。

**「影响」** 对多租户推理部署而言，vLLM 文档明确指出，前缀缓存会在共享相同提示前缀的请求间复用 KV 块，这种复用在该环境中构成计时侧信道。运营方若无法为不同安全上下文提供独立缓存或实例，就应关闭跨租户的前缀缓存复用，并在上线前将缓存隔离纳入安全审查。

**「社区讨论」** 评论者 amluto 认为共享 KV cache 导致的问题“很荒谬”，主张推理服务器应像浏览器区分不同源那样，允许调用方指定缓存分离键；kgeist 则描述了另一种可能：单一 vLLM 实例同时处理 prefill 和 decode 时，一方可通过周期性读取长文档拖慢解码，另一方用 bash 计时并据文件长度估算吞吐量来接收比特。tsimionescu 反驳称这些攻击需要大量极不可能的巧合，包括双方事先知道彼此、预共享校验信息并掌握服务器软硬件栈细节；devy 则担忧此类手法被公开详细讨论后，前沿模型“现在都知道了”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.lesswrong.com/posts/7wzWuLP3HhyBLmKfo/models-can-communicate-via-inference-servers-despite-being">Models Can Communicate via Inference Servers Despite Being ...</a></li>
<li>Security - vLLM docs</li>
<li>Preserving Provenance in Shared KV Caches for LLM Serving - arXiv</li>

</ul>
</details>

**标签**: `#AI security`, `#inference servers`, `#side channels`, `#sandboxing`, `#KV cache`

---

<a id="item-tech-news-9"></a>
### [腾讯开源 Hy4 flash 量化权重，最小版可在 64 GB Mac mini 运行](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重：原权重约 410.27GiB，最小的 IQ2-AH 版本为 125.73GiB，约为原版的 30%。据该来源，借助 Strata offload 框架，64 GB Mac mini 可运行这一最小版本。来源给出的吞吐数据为：48 GB 显存设备在 10K 上下文中每秒生成 89 个 token，M5 Max 128 GB 上的 Q3\_K 版本在 32K 上下文中每秒生成 47 个 token；DeepSWE v1.1 等评测中，Q3\_K 与原模型的得分差距不超过 0.4 分。

telegram · zaihuapd · 11月25日 09:29

**「背景」** GGUF 是本地推理中常用的量化权重格式，量化会降低权重精度以缩小模型体积；offload 则把无法全部驻留内存的权重按需换入。Strata 是面向 Apple Silicon 的推理框架，它借助自有的 Metal 引擎在采用统一内存的 Mac 上运行模型，因此内存小于模型体积的设备也能加载模型。

**「影响」** 对希望在本地运行大模型的 Mac 用户来说，64 GB Mac mini 走的是 IQ2-AH 加 Strata offload 的路径；由于 125.73GiB 的权重规模超过 64 GB，运行依赖卸载机制。来源中的 89 token/s 和 47 token/s 分别对应 48 GB 显存设备与 M5 Max 128 GB 上的 Q3\_K，并非该 Mac mini 配置的实测结果，不能直接当作其性能预期。

<details><summary>参考链接</summary>
<ul>
<li>Local LLM Hardware: GPUs, Apple Silicon and VRAM Guide</li>
<li>Local LLM Guides: Hardware, Models &amp; Benchmarks - OpenClaw DC</li>

</ul>
</details>

**标签**: `#quantization`, `#open-source LLM`, `#local inference`, `#model compression`, `#Apple Silicon`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝施压英特尔交出 10%股权](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据 WIRED 报道并援引法庭文件，2025 年 8 月美国商务部律师在与英特尔首席财务官通话时称，不要“误以为这是一场谈判”，并提醒董事会若拒绝将带来无法预测的后果；几天后英特尔董事会交出了美方要求的股份。特朗普随后称美国政府“完全拥有并控制”英特尔 10%的股份且未为此付钱，这批股份现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 这些细节出自一起英特尔股东诉讼中解封的法庭文件，文件记录了 2025 年 8 月美国商务部律师戴维·夏皮罗（David Shapiro）与英特尔首席财务官的通话，他在通话中表示这不是一场谈判。WIRED 将此事描述为特朗普政府针对私营企业展开的又一轮施压行动。

**「影响」** 对英特尔股东而言，这笔约 9.9%的政府持股与释放约 89 亿美元联邦芯片拨款相关，并已引发衍生诉讼，从而考验“政府作为大股东但不取得董事席位”的治理安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/">Not Just Nvidia: Inside Team Trump’s Takeover of Intel | WIRED</a></li>
<li><a href="https://aiweekly.co/alerts/wired-commerce-lawyer-warned-intel-cfo-rejecting-us-10-stake-would-carry">Wired: Commerce Lawyer Warned Intel CFO Rejecting US 10% ...</a></li>
<li><a href="https://finance.biggo.com/news/1eea079d-982e-483f-be72-28381b50b545">Unsealed Filings Allege White House Pressured Intel Board ...</a></li>
<li><a href="https://www.intel.com/content/www/us/en/newsroom/news/corporate/intel-and-trump-administration-reach-historic-agreement.html">Intel and Trump Administration Reach Historic Agreement to ...</a></li>
<li><a href="https://www.dandodiary.com/2026/03/articles/shareholders-derivative-litigation/intel-derivative-suit-tests-governance-implications-of-government-equity-stakes/">Intel Derivative Suit Tests Governance Implications of ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#US Commerce Department`, `#government equity stake`, `#semiconductor policy`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [SpaceX 与特斯拉据报设立特别委员会，探讨 3.5 万亿美元全股票合并](https://thenextweb.com/news/spacex-tesla-merger-five-directors-special-committees) ⭐️ 7.0/10

据知情人士消息，SpaceX 与特斯拉已各自选定五名董事组成特别委员会，探讨一笔规模达 3.5 万亿美元的全股票合并，并力争年底前完成；若达成，将是史上最大规模合并。报道称双方尚未接近达成协议，仍需确定换股比例并争取股东支持。

telegram · zaihuapd · 11月25日 00:41

**「背景」** 两家公司均由马斯克掌管；它们各自设立由五名董事组成的特别委员会，负责敲定这笔全股票合并的换股比例并争取股东支持。

**「对股东的影响」** 若交易推进，特斯拉股东与今年 6 月上市的 SpaceX（tool-2-2）股东都将按尚未谈定的换股比例转换为合并后公司的股份，因此各自最终持股比例取决于特别委员会确定的换股比例及双方股东投票结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zerohedge.com/markets/meet-five-insiders-negotiating-35-trillion-tesla-spacex-mega-merger-deal">Tesla - SpaceX Merger Could Be Announced As Soon As... | ZeroHedge</a></li>
<li><a href="https://www.ft.com/content/2585e45e-9133-4215-a2d8-e1275e1033b9?syn-25a6b1a6=1">SpaceX - Tesla : the directors negotiating the biggest merger ever</a></li>
<li><a href="https://www.nytimes.com/2026/11/16/business/elon-musk-tesla-spacex-conglomerate.html">Elon Musk Dreams of Merging Tesla and SpaceX in Move Toward...</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#SpaceX`, `#M&amp;A`, `#Elon Musk`, `#corporate governance`

---

<a id="item-finance-news-3"></a>
### [美国拟对 14 个贸易伙伴加征第 301 条新关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 7.0/10

美国拟依据 1974 年《贸易法》第 301 条，对中国、欧盟、日本、印度等 14 个贸易伙伴加征针对制造业结构性产能过剩的新关税，税率按国别设定；据 CNBC 报道，对华新关税将在 2018 年已加征的 25%之上再加 20%，如果中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，相关税率可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 美国此次依据 1974 年《贸易法》第 301 条，该条款允许在认定他国贸易做法损害美国产业后加征关税；2018 年美方正是据此对大量中国商品加征关税，部分税率现为 25%。中美则于 2025 年 10 月 30 日在韩国釜山达成贸易休战协议，该协议是此次对华税率可能上调的参照。

**「影响」** 若新关税落地，叠加在中国商品上的 20%税率（并可能升至 40%）将直接抬高美国进口商成本，并可能传导至美国消费者价格——安联研究指出，关税曾在 2025 年下半年和 2026 年初显著推高美国通胀（tool-3-1）；汤森路透的调查则显示，企业已将关税波动列为加剧供应链压力的主要来源（tool-3-2）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.lexology.com/library/detail.aspx?g=400a8458-8c8a-48a9-bbb8-23b879f604de">USA initiates Section 301 investigations into global manufacturing ...</a></li>
<li><a href="https://www.cnbc.com/2025/10/30/trump-xi-south-korea-rare-earth-tariff-trade-war-nvidia.html">What Trump and Xi agreed to in the U . S .- China trade truce</a></li>
<li><a href="https://www.allianz.com/content/dam/onemarketing/azcom/Allianz_com/economic-research/publications/specials/en/2026/july/2026_07_22_Trade-war-update.pdf">Allianz Research | 22 July 2026 Trade war 3.0: A new, lasting ...</a></li>
<li><a href="https://tax.thomsonreuters.com/blog/2026s-supply-chain-challenge-confronting-complexity-and-disruption-in-global-trade-tri/">The 2026 supply chain challenge: Global trade disruption</a></li>

</ul>
</details>

**标签**: `#trade policy`, `#tariffs`, `#US-China relations`, `#Section 301`, `#global trade`

---