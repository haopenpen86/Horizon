---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 34 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [Check Point 安全管理服务器遭入侵，攻击者伪造管理员会话](#item-tech-news-1) ⭐️ 8.0/10
2. [Quad9 因法国法律限制撤出该国 DNS 服务](#item-tech-news-2) ⭐️ 8.0/10
3. [百度开源文心 5.5 Flash Preview：280B 参数、Apache 2.0](#item-tech-news-3) ⭐️ 8.0/10
4. [vCenter vmdir 9.8 分免鉴权漏洞获补丁](#item-tech-news-4) ⭐️ 8.0/10
5. [三元量化模型 Bonsai 2.5 27B 可在 24GB Mac 上跑 128k 上下文](#item-tech-news-5) ⭐️ 7.0/10
6. [HN 讨论确定性虚拟机与多线程性能分析](#item-tech-news-6) ⭐️ 7.0/10
7. [Simon Willison 复盘十二个月内 LLM 的三个拐点](#item-tech-news-7) ⭐️ 7.0/10
8. [Z.ai 发布 GLM-5.4，首个循环 Transformer 模型](#item-tech-news-8) ⭐️ 7.0/10
9. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-tech-news-9) ⭐️ 7.0/10
10. [诺华 CEO：AI 十年内难治愈癌症，研发周期或缩短四年](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [vLLM 首日支持 ERNIE 5.5 Flash Preview：插件与推理加速](#item-tech-blog-1) ⭐️ 7.0/10
2. [vLLM-GR：生成式推荐的推理服务框架](#item-tech-blog-2) ⭐️ 6.0/10

**财经新闻**
1. [犹他州撤销对 Kalshi 创始人的刑事指控](#item-finance-news-1) ⭐️ 7.0/10
2. [纽约联储威廉姆斯：通胀回落到 2%仍需努力，可能随着时间逐步加息](#item-finance-news-2) ⭐️ 7.0/10
3. [小米三季度经调整净利同比降 56.8%，汽车交付超 10 万辆](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Check Point 安全管理服务器遭入侵，攻击者伪造管理员会话](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 8.0/10

GreyNoise 报道了一起针对 Check Point 安全管理服务器的活跃入侵活动。讨论中引述的攻击记录显示，攻击者于 2026 年 10 月 2 日扫描并开始利用 HFS 服务器：HFS 的 loginSrp1 登录端点每次 POST 都会返回一个签名会话 Cookie，其中的 sid 值来自 JavaScript 的 Math.random\(\)；攻击者连续多次登录，收集足够输出后重建 Node.js V8 PRNG 的内部状态，进而恢复会话 Cookie 的签名密钥，并伪造出签名管理员会话 Cookie，从而取得该主机的访问权限。上述技术细节来自文章被引述的段落，原始报道正文未能获取，因此受影响的 Check Point 产品版本范围、修复或缓解措施以及确切的初始入侵途径在现有材料中尚不清楚。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「背景」** 此前公开的 CVE-2026-16232 是 Check Point SmartConsole 登录流程中的认证绕过漏洞：未经认证的远程攻击者可利用它绕过登录。Check Point 已在 2026 年 7 月确认该漏洞遭到主动利用，这为理解当前针对 Check Point 管理服务器的入侵活动提供了直接前情。

**「影响」** 对把 Check Point 安全管理服务器管理接口暴露在互联网上的组织而言，直接后果是攻击者无需有效口令，就能凭伪造的管理员会话获得管理权限。现有材料没有给出官方补丁或缓解说明，管理员应优先收敛管理接口的公网访问，并排查 HFS 登录端点出现的连续登录与异常会话记录。

**「社区讨论」** 评论者 omh 指出，文章并未讲清初始访问方式，并质疑多起 Check Point 客户受害是否意味着这些组织的安全管理服务器都直接暴露在互联网上，同时把 CVE-2026-16232 视为可能的入口，但这一关联仍是推测。另一位评论者 20after4 认为，问题根源在于 Math.random 不应被用于安全场景，应当让随机数生成器默认具备安全强度，而不只是逐个修正误用它的应用。

<details><summary>参考链接</summary>
<ul>
<li>CVE-2026-16232: Active Exploitation Requires Immediate Management Plane Remediation - Check Point CheckMates</li>
<li>CVE-2026-16232 - CVE Record</li>
<li>CVE-2026-16232: Check Point SmartConsole Authentication Bypass</li>

</ul>
</details>

**标签**: `#cybersecurity`, `#Check Point`, `#intrusion campaign`, `#PRNG`, `#session forgery`

---

<a id="item-tech-news-2"></a>
### [Quad9 因法国法律限制撤出该国 DNS 服务](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 8.0/10

Quad9 已将其公共 DNS 解析服务撤出法国，原因是法国法律限制。社区用户报告该措施自 2026 年 11 月 24 日起生效：从法国查询 9.9.9.9 会收到 REFUSED，并带有 EDE 18（Prohibited）及“因法国法律限制服务不可用”的说明。提供的材料没有披露具体法律条款或限制范围，因此尚不能确认这是否只影响法国境内的解析请求，还是也覆盖其他接入方式。

hackernews · farrokhi · 11月24日 08:33 · [社区讨论](https://news.ycombinator.com/item?id=50625384)

**「背景」** Quad9 是一家非营利公共 DNS 解析器，负责把域名解析成 IP 地址。用户改用这类公共解析器，通常可以绕开本地 ISP 默认 DNS 的域名封锁，因此它也可能成为版权方要求封锁域名时针对的对象。此次争议源于法国体育版权方 beIN Sports 要求 Quad9 封锁其认定与盗版流媒体有关的域名；Quad9 没有执行这些 DNS 封锁，而是在 2026 年 11 月 24 日停止为法国用户提供服务。

**「影响」** 对法国境内直接使用 Quad9 的用户而言，依赖 9.9.9.9 的域名解析会失败，需要改用其他递归解析器、组织内部解析器或社区提供的转发代理；把公共解析器地址硬编码在设备或应用中的部署方式，在法国也不再可靠。

**「社区讨论」** 有社区用户贴出自己搭建的 Quad9 转发代理，支持 DoH、DoT、Do53、IPv4 和 IPv6，供法国用户作为替代；另一名用户则实测确认 9.9.9.9 返回 REFUSED/EDE 18。也有人提出家庭场景可用 Unbound（例如配合 Pi-hole），并质疑为何要依赖 Quad9、1.1.1.1 或 8.8.8.8 等公共解析器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad 9 Service Deactivation in France | Quad 9</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad 9 Is Leaving France : Why DNS Resolvers Are... | Tech Stackups</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet infrastructure`, `#privacy`, `#France`, `#legal/policy`

---

<a id="item-tech-news-3"></a>
### [百度开源文心 5.5 Flash Preview：280B 参数、Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

百度于 11 月 24 日开源文心 5.5 Flash Preview，权重以 Apache 2.0 协议在 Hugging Face 和 ModelScope 开放，开发者可用 vLLM 或 SGLang 部署和微调。该模型采用 MoE 架构，总参数 280B、每 token 激活 14B，支持 1M token 上下文，百度称其是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型。流传的基准图显示 Terminal-Bench 4.0 得 46.5 分、DeepSWE v1.1 得 71.2 分，但百度未说明这些成绩是否经过第三方独立验证。

telegram · zaihuapd · 11月24日 07:32

**「背景」** 文心 5.5 Flash Preview 采用 MoE 架构：280B 是总参数规模，但每个 token 只激活 14B 参数，因此推理时实际参与计算的参数远少于总参数。Apache 2.0 是宽松的开源许可证，允许使用、修改和商用，但分发时需保留版权与许可声明。

**「实际影响」** 对希望自托管或微调的团队而言，Apache 2.0 协议允许直接获取权重并接入现有 vLLM/SGLang 流程；但 280B 总参数意味着仍需为完整权重准备相应的内存和存储资源，且上述基准分数在独立复现前不宜作为选型依据。

**标签**: `#open-source-llm`, `#baidu-ernie`, `#mixture-of-experts`, `#model-release`, `#apache-2.0`

---

<a id="item-tech-news-4"></a>
### [vCenter vmdir 9.8 分免鉴权漏洞获补丁](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布覆盖 23 个漏洞的补丁，其中 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903 评分为 9.8。该漏洞允许任何能访问 vCenter 的攻击者绕过认证进入系统；据报道，它在补丁发布前几天已被作为零日利用。现有材料未列出受影响版本范围或临时缓解措施，零日利用说法也来自报道而非独立确认。

telegram · zaihuapd · 11月24日 14:50

**「漏洞背景」** vmdir 是 vCenter 的目录服务组件；此次漏洞出在该组件的鉴权环节，因此只要能访问 vCenter 管理接口，攻击者就可能绕过登录直接进入系统。第三方 CVE 汇总列出的受影响范围包括 vCenter 8.0 U3k 及更早版本，以及低于修复构建的 9.0.x 和 9.1.x；实际范围仍应以 Broadcom 公告为准。

**「影响」** 运行 vCenter 且管理接口可被不可信网络访问的团队，应优先应用本轮补丁，并在修补前限制对该接口的访问；该漏洞不需要有效凭据，只要网络可达即可触发。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/dinosn/CVE-2026-123903">dinosn/ CVE - 2026 - 123903 : CVE - 2026 - 123903 : VMware vCenter vmdir ...</a></li>

</ul>
</details>

**标签**: `#vCenter`, `#VMware`, `#vulnerability`, `#zero-day`, `#security`

---

<a id="item-tech-news-5"></a>
### [三元量化模型 Bonsai 2.5 27B 可在 24GB Mac 上跑 128k 上下文](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Bonsai 2.5 27B 是一个 27B 的三元（ternary）量化模型，以 Q2 GGUF 形式发布，正因能在消费级硬件上以可用速度运行而受到关注。社区用户在一台 24GB 内存的 Mac Mini M5 Pro 上实测约 22–25 tok/s，并能轻松容纳 128k 上下文，认为这使其有望用于本地 agentic coding。有评论称其 SWE-bench Verified 得分与 Opus 4.6 相当，但这属于尚未验证的说法，且原始公告未提供可供核实的基准细节。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「背景」** 三值（ternary）指以 3 为基、只取三种取值的表示方式；在量化模型中通常对应每个权重只保留三种可能值，从而把每个权重的存储开销压缩到远低于常规 16 位格式的水平。这正是 27B 规模的模型能被装进 24GB 内存的消费级 Mac、并以 128k 上下文运行的前提。评论者提到的 Q2 GGUF 也表明，该模型以约 2 位的低比特文件形式分发。

**「影响」** 对本地开发者而言，直接后果是 24GB 内存的 Mac 即可承载 128k 上下文，用于批量的 agentic coding 任务。但采用前需要自行验证：目前缺少与 Qwen3.8 等同尺寸 Q1/Q2 量化模型的直接对比，三元权重除 FPGA 外是否有硬件加速也仍无明确答案。

**「社区讨论」** ariwilson 报告在 Mac Mini M5 Pro（24GB 内存）上生成速度约 22.3 tok/s、首 token 约 2.12 秒，并称 128k 上下文可以轻松放入内存；syntaxing 通过 Unsloth Studio 测到相近速度（预填充约 300 tok/s、生成约 30 tok/s），认为其 agentic 调用表现扎实，甚至优于 Q4 量化的 Inkling 2 mini。nik\_s 则质疑 SWE-bench 上的“前沿级”表现可能混合了针对基准的优化、基准本身的漂移，以及小模型约滞后六个月追上前沿的常态；hatthew 希望看到与同等规模量化模型的直接对比，Lramseyer 追问三元权重除 FPGA 外是否有硬件加速。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Ternary_numeral_system">Ternary numeral system - Wikipedia</a></li>

</ul>
</details>

**标签**: `#ternary quantization`, `#small language models`, `#local inference`, `#SWE-bench`, `#GGUF`

---

<a id="item-tech-news-6"></a>
### [HN 讨论确定性虚拟机与多线程性能分析](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

Hacker News 上围绕一篇关于确定性虚拟机性能分析与 Brendan Gregg 式剖析方法的博客文章展开讨论。评论者关注该虚拟机据称采用单线程设计，认为这在高吞吐多线程流水线中会限制性能分析；也有人表示对用火焰图分析多线程程序已失去兴趣，因为跨线程依赖难以推断。讨论还涉及与 rr 记录/回放工具的对比，以及异步工作负载（C++ 协程、fiber、future）的关键路径分析是否可行。

hackernews · kqr · 11月24日 10:50 · [社区讨论](https://news.ycombinator.com/item?id=50626413)

**「背景」** Brendan Gregg 式剖析常以火焰图展示采样调用栈，帮助定位 CPU 热点；但在多线程程序中，火焰图本身不直接给出跨线程依赖，这也是该文讨论的背景之一。Farid Zakaria 的文章转向确定性虚拟机：Rewind 这类 VM 可以重放同一段执行，使剖析和优化更可复现。文章称，作者已用它查找 heisenbugs、让 profile-guided optimization 可复现，并让 Nix 构建达到比特级可复现。

**「对开发者的影响」** 对分析多线程或异步系统的开发者而言，评论指出的限制意味着仅靠单线程确定性虚拟机或火焰图可能不足以还原跨线程及续体依赖；若要定位异步关键路径，评论者认为可能需要在框架中嵌入请求上下文等额外手段。

**「社区讨论」** 一位评论者借 Nvidia 的“speed of light”方法主张先确定理论上限，再判断实际性能差距；另一位则提到 sleep profiling 或 CPU stall profiling 可作为替代思路，但需要在 Linux 内核中做权衡，或增加 CPU 设计复杂度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg">Worshipping at the altar of Brendan Gregg - fzakaria .com</a></li>

</ul>
</details>

**标签**: `#performance-analysis`, `#profiling`, `#flame-graphs`, `#deterministic-vm`, `#record-replay`

---

<a id="item-tech-news-7"></a>
### [Simon Willison 复盘十二个月内 LLM 的三个拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison 在 11 月 24 日的回顾文章中，把过去十二个月 LLM 与编码智能体的变化归纳为三个能力拐点，并以 Claude Opus 4.5 发布一周年作为参照。他称第一个拐点在 2025 年 11 月：Opus 4.5 是首个配合 Claude Code 使用时默认结果通常正确的模型，同期 OpenAI 的 GPT-5.1 Instant、Thinking、Codex 和 Codex-Max 也让 Codex 变得可靠。第二个是 2026 年 6—7 月的“Fable 类模型”：只要给出目标和工具，Claude Fable 5 等模型就能自主、强力地解决问题；Fable 5 曾受美国出口管制，7 月 1 日才恢复。第三个是 2026 年 9—10 月的 3D 建模与游戏开发能力，他将 9 月 22 日发布的 Opus 5.5 视为首个“理解乐趣”的模型，称其用 12 小时试玩和平衡让一款 RTS 从无聊变得有趣。

rss · Simon Willison · 11月24日 23:02

**「背景」** 这篇回顾基于作者在 AI Engineer Code Summit 的主题演讲，并以 2025 年 11 月 24 日发布的 Claude Opus 4.5 为时间锚点：到本文发布时，该模型恰好推出一周年。Claude Code 则早在 2025 年 2 月 24 日随 Claude 3.7 Sonnet 推出，因此 Opus 4.5 面世时，Claude Code 已有约九个月的使用历史。

**「影响」** 对使用编码智能体的开发者而言，这篇回顾给出的实际判断是：模型选型应看它在给定目标和工具后能否自主完成多步任务，而不只看代码补全质量；按 Willison 的定义，Claude Fable 5/5.1/5.2、Opus 5.5、GPT-6 Astra 以及可能入围的 Gemini 4 Neon 是这一门槛的当前代表。

**标签**: `#LLM coding agents`, `#AI engineering`, `#Claude Opus 4.5`, `#LLM capabilities`, `#retrospective`

---

<a id="item-tech-news-8"></a>
### [Z.ai 发布 GLM-5.4，首个循环 Transformer 模型](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai 发布 GLM-5.4，称这是其首个采用循环 Transformer 架构的模型：一组共享权重的层在一次前向传播中重复运行多次，以在不增加参数量的情况下加深网络。该模型目前尚未开放权重，Z.ai 表示将在完成必要的安全加固后，以负责任的方式开源。GLM-5.4 暂不能通过常规 API 使用，只能通过 Coding Plan 订阅访问；Simon Willison 验证该订阅的 API key 可用于同一 OpenAI 兼容端点 https://api.z.ai/api/v1，并为此编写了 llm-glm 插件。Willison 的 pelican 测试显示 5.4 与 5.3 质量相近，未提供基准测试结果。

rss · Simon Willison · 11月23日 23:40

**「背景：循环 Transformer 是什么」** 传统 Transformer 的每一层在一次前向传播中只运行一次；循环 Transformer（Loop Transformer）则让一组共享权重的层迭代多次，反复精化隐藏状态，从而在不增加参数量的前提下加深网络。Z.ai 称 GLM-5.4 是其首个采用该架构的模型，而这已是近期第二例：据原文，Thinking Machines Lab 于 11 月 20 日发布的 Inkling 2 Mini 同样采用循环结构，将模型中间层对每个 token 运行三次，以更少 token 完成推理。

**「对开发者的实际影响」** 希望使用 GLM-5.4 的开发者目前无法通过常规 API 调用，必须订阅 Z.ai 的 Coding Plan；不过该套餐与常规 API 共用同一个 OpenAI 兼容的 Responses API 端点（https://api.z.ai/api/v1），Coding Plan 的密钥可以直接调用新模型，因此迁移成本主要是订阅方式，而不是改代码。现有 llm-zai 插件尚未支持该模型，Simon Willison 为此另发了 llm-glm 插件，这显示第三方工具链的适配会滞后于模型上线。模型权重尚未开放，Z.ai 仅表示会在完成安全加固后开源；同时该发布未公布基准测试结果，团队若要评估其在编码或多模态任务上的实际表现，需自行测试。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/z-ai-debuts-glm-5-4-with-a-novel-looped-transformer-architecture-skipping-ai-benchmarks-entirely/">Z . ai Debuts GLM - 5 . 4 With a Novel Looped Transformer Architecture...</a></li>

</ul>
</details>

**标签**: `#LLM architecture`, `#looped transformers`, `#GLM-5.4`, `#Z.ai`, `#AI model release`

---

<a id="item-tech-news-9"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会成为企业规避美国芯片出口管制的通道，当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单；《联邦公报》称，这些企业存在向未获授权用户转移先进计算产品的“重大风险”，名单还包括它们在马来西亚和泰国的关联实体。路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 也在名单中；阿里巴巴回应称，从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 公开资料显示，Megaspeed 自 2024 年起就因涉嫌未经美国政府许可向中国供应英伟达芯片而接受美方调查；该公司公开表示重视美国出口管制合规，并愿与美政府合作。美国对先进计算芯片的出口管制以最终用户和用途为条件，因此经第三国转口的交易会尤其受到审查。

**「影响」** 对在新加坡及东南亚采购或转售英伟达等先进计算芯片的企业而言，Megaspeed 正被调查、7 家东南亚企业被列入美国贸易黑名单，意味着相关交易将同时受到美国清单限制和新加坡当局审查；阿里巴巴已因子公司 Apex Enterprise Solutions 在列而公开否认转移受管制芯片。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Megaspeed">Megaspeed - Wikipedia</a></li>
<li><a href="https://www.megaspeed.ai/">MegaSpeed .Ai</a></li>

</ul>
</details>

**标签**: `#semiconductor export controls`, `#Singapore`, `#Nvidia`, `#AI chips`, `#trade blacklist`

---

<a id="item-tech-news-10"></a>
### [诺华 CEO：AI 十年内难治愈癌症，研发周期或缩短四年](https://www.ft.com/content/1e5a9d70-221d-461d-ae03-dc235b1db340) ⭐️ 7.0/10

诺华 CEO 万思瀚（Vas Narasimhan）表示，AI 不会在未来 5 到 10 年内治愈癌症；即便只是把药物研发平均周期从 12 年压缩到 8 年，也大约需要十年。他把提速主要归因于人体试验前的早期发现阶段：这一步通常耗时 4 年，最多可缩短 2 年；他预计进入人体试验的成功率可从 8% 提高到 12%，但动物实验和临床试验仍无法跳过。这一判断与 Anthropic CEO 关于癌症等疾病可能在十年内成为“历史遗迹”的说法相左，礼来 CEO 也公开表示怀疑；万思瀚同时担任 Anthropic 董事。上述内容为高管估计，并非已经实现的研发成果。

telegram · zaihuapd · 11月24日 08:54

**「背景」** 新药研发从早期发现、动物实验到多阶段人体临床试验，通常以十年计，且最终获批概率长期偏低；这正是万思瀚把“缩短四年”和“成功率从 8% 提到 12%”视为需要约十年才能实现的目标的背景。此前 Anthropic CEO 公开称癌症等疾病可能在十年内成为“历史遗迹”，诺华的判断则明显更保守。

**「对药企研发规划的含义」** 按万思瀚给出的数字，AI 的可量化收益集中在进入人体试验前的早期发现阶段：这一步通常约 4 年，最多可缩短 2 年；他同时预计人体试验成功率从 8% 提升到 12%。这意味着药企在排期与预算上应把 AI 当作压缩临床前周期、提高候选分子质量的工具，而不能据此假定动物实验和临床试验本身会加速——总周期从 12 年降到 8 年仍需约十年才可能实现。

<details><summary>参考链接</summary>
<ul>
<li>Anthropic director Vas Narasimhan bets AI can speed Novartis R&amp;D - Fierce Biotech</li>

</ul>
</details>

**标签**: `#AI drug discovery`, `#pharmaceutical R&amp;D`, `#AI hype`, `#Novartis`, `#healthcare AI`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 首日支持 ERNIE 5.5 Flash Preview：插件与推理加速](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** ERNIE 5.5 Flash Preview 是 280B 总参数、14B 激活的稀疏 MoE 模型，支持 1M token 上下文和工具调用，面向长程 Agent 任务，推理成本是其设计核心；百度 ERNIE 团队与 vLLM 合作，希望发布当天即可在官方 vLLM 上部署。

**「方案」** 方案是独立 vLLM-ERNIE 插件：安装 vllm==0.32.0 后放入同一环境，vLLM 通过 vllm.general\_plugins 自动注册；注册只记录模块路径，配置命中 ERNIE 架构才导入模型代码，因此不影响其他模型，也无需 fork 或专用镜像。针对 VHA、Multi-Router Latent MoE 和 MultiMax 输出头等结构，团队在加载时预折叠固定参数，并将 FP8 量化、路由、门控和分段激活融合进单 kernel，官方称单 kernel 比逐算子实现快 1.55–6.53 倍。FlashIndexer 用仅依赖当前 token 的小型 head router 动态选择索引头，再以阈值预过滤缩小 top-k 候选，团队测得 1M 上下文约 1.4 倍加速。默认权重将路由专家设为 MXFP4（W4A8）并用 QAT 对齐训练/推理数值，其余权重和 KV 缓存用 FP8；3 层 DSpark 草稿模型每步最多提议 7 个 token，团队报告真实编程与 Agent 负载平均接受长度超过 4.0。插件还复用前缀缓存、CUDA graph、PD 分离和 KV 卸载等能力。

**「启示」** 作者认为，独立插件能在不等待上游合并的情况下实现新模型首日支持，并把模型专用优化与 vLLM 主干解耦；但加速数据和接受长度均为团队自报，独立验证仍有限。

**标签**: `#vLLM`, `#ERNIE`, `#inference optimization`, `#kernel fusion`, `#speculative decoding`

---

<a id="item-tech-blog-2"></a>
### [vLLM-GR：生成式推荐的推理服务框架](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 6.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 生成式推荐服务需要在单次请求的延迟预算内，把用户历史转成一组可下发的候选物品。模型用语义 ID 表示物品，因而必须并行探索多条候选路径，并保证结果能映射到真实目录中的物品。

**「方案」** vLLM-GR 的做法是把束搜索嵌入 vLLM 引擎：复用其调度器、模型执行和分页 KV 缓存，并增加贯穿整次搜索的 beam session。EngineCore 管理会话，调度器把 prefill/decode 分派给 worker；模型 runner 打分，beam selection 记录存活路径的分数与父节点，下一步 decode 再按父索引读取对应 KV。各候选共享用户历史的 prompt KV，目录约束则把搜索导向能映射到真实物品的语义 ID；离线 Python、OpenAI 兼容 HTTP 和 gRPC 均可一次提交完整搜索并返回候选及分数。作者给出的 P99 基准覆盖六种加速器、1,024 输入 token、束宽 128/256 和批大小 1/4/8；束宽 256 且批大小 4/8 时 vLLM-GR 在所示后端中最低，例如 H20 批大小 8 为 369.4 ms，而 SGLang 为 1,280.1 ms、NVIDIA SID-GR 为 428.1 ms，但文章也承认各图来自计时口径、样本数和后端设置不同的独立运行，部分后端版本未记录，且小批量下并非总是领先（RTX PRO 6000 批大小 1 为 29.21 ms，SID-GR 为 28.25 ms）。路线图还列出排序、MoE、变长束、在线调度和分布式 KV 缓存等尚未完成的方向。

**「启示」** 作者将 vLLM-GR 的核心价值定位为把推荐候选搜索纳入服务引擎，使共享 KV、目录约束和束调度成为可复用能力，而非单点加速。其公布的尾延迟结果支持高束宽、较大批量下的优势，但基准透明度与模型、功能覆盖仍限制外推。

**标签**: `#generative recommendation`, `#inference serving`, `#beam search`, `#KV cache`, `#vLLM`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [犹他州撤销对 Kalshi 创始人的刑事指控](https://www.cnbc.com/2026/11/24/utah-drops-charges-against-kalshi-after-it-halted-operations-in-state.html) ⭐️ 7.0/10

犹他州于周二撤销了对预测市场平台 Kalshi 及其两位联合创始人 Tarek Mansour 和 Luana Lopes Lara 的刑事指控，此前该公司于周一以法律不确定性为由暂停了在犹他州的运营。这些指控于 10 月 28 日提起，共 14 项，州方称 Kalshi 在犹他州经营非法赌博业务。

rss · CNBC Finance · 11月24日 20:45

**「背景」** Kalshi 是受美国商品期货交易委员会（CFTC）监管的预测市场平台，用户可就事件结果买卖合约；在犹他州 10 月 28 日提出指控的前一天，CFTC 已起诉该州，主张自己才是这类市场规则的唯一制定者。

**「影响」** 对犹他州用户而言，Kalshi 周一暂停当地业务后，他们就无法再使用该平台。这次撤诉属于“不带偏见”的驳回，意味着一旦 Kalshi 恢复在犹他州的运营，州方仍可重新提起同样的 14 项刑事指控；因此，其他预测市场平台在逐州扩张时仍要面对类似的法律风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://kalshi.com/">Kalshi - Prediction Market for Trading the Future</a></li>

</ul>
</details>

**标签**: `#prediction markets`, `#Kalshi`, `#regulation`, `#criminal charges`, `#CFTC`

---

<a id="item-finance-news-2"></a>
### [纽约联储威廉姆斯：通胀回落到 2%仍需努力，可能随着时间逐步加息](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席威廉姆斯周一表示，美联储仍需做更多工作才能让通胀回到 2%，并暗示未来可能随着时间逐步加息。市场完全计入美联储 12 月 8 日至 9 日会议将把利率从 3.75%-4%上调 25 个基点，而威廉姆斯未直接谈及这一预期。

rss · CNBC Finance · 11月24日 13:33

**「背景」** 美国通胀仍远高于美联储 2%的目标，官员们对加息速度存在分歧；威廉姆斯预计通胀将在 2027 年更接近 2%，并在次年达到目标。

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#FOMC`

---

<a id="item-finance-news-3"></a>
### [小米三季度经调整净利同比降 56.8%，汽车交付超 10 万辆](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

小米集团发布 2026 年第三季度财报，经调整净利润为 48.84 亿元，同比下降 56.8%，但仍略高于市场预期的 47.46 亿元；营收为 1072.4 亿元，同比下降 5.2%。当季汽车交付 100,975 辆，手机业务出货 3070 万台，手机均价创历史新高。

telegram · zaihuapd · 11月24日 10:09

**「背景」** 利润承压与存储芯片等核心元器件涨价及研发支出增至 92.4 亿元有关，集团当期综合毛利率为 20.2%。

**标签**: `#Xiaomi`, `#quarterly earnings`, `#electric vehicles`, `#smartphones`, `#profitability`

---