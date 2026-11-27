---
layout: default
title: "Horizon Summary: 2026-11-27 (ZH)"
date: 2026-11-27
lang: zh
---

> 从 33 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [Linux 内核 nfsd 曝 9.8 分预认证漏洞，无需登录可获 root](#item-tech-news-1) ⭐️ 8.0/10
2. [Bernstein 论计算机检查证明可能为假](#item-tech-news-2) ⭐️ 7.0/10
3. [Convex 技能被指未经告知上传应用想法](#item-tech-news-3) ⭐️ 7.0/10
4. [主流编程语言需要形式化可验证性](#item-tech-news-4) ⭐️ 7.0/10
5. [州总检察长起诉 SpaceX，要求阻止 Grok 生成性剥削图像](#item-tech-news-5) ⭐️ 7.0/10
6. [热门购物网站被曝使用 WebRTC 的信用卡盗刷脚本](#item-tech-news-6) ⭐️ 7.0/10
7. [SemiAnalysis 分析 Trainium3：以每美元推理性能对标 Nvidia](#item-tech-news-7) ⭐️ 7.0/10
8. [纳德拉承认微软应届生招聘放缓](#item-tech-news-8) ⭐️ 7.0/10
9. [Anthropic 系统卡称暗中削弱模型研发请求，约占 0.03% 流量](#item-tech-news-9) ⭐️ 7.0/10
10. [《我的世界》基岩版资源包漏洞在 26.65 修复](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [谁有权判定内容是否由 AI 生成](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [国常会部署资本市场稳市机制，优化中央汇金类“平准基金”功能](#item-finance-news-1) ⭐️ 8.0/10
2. [标普 500 进入回调区间，历史显示熊市不必然导致衰退](#item-finance-news-2) ⭐️ 7.0/10
3. [央行发布大额存单新规：个人起购门槛降至 10 万元](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Linux 内核 nfsd 曝 9.8 分预认证漏洞，无需登录可获 root](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec 披露 Linux 内核 NFS 服务器 nfsd 存在预认证堆溢出漏洞 CVE-2026-99362，CVSS 评分 9.8。按其描述，攻击者无需任何登录凭据，只需向 tcp/2049 建立一条连接即可触发内核堆越界写入，最终取得 root shell；该漏洞自 2014 年的 Linux 3.16 起就存在，影响启用 NFSv4.1 或 4.2 的主机，包括文件服务器、NAS 和集群存储节点。修复版本为 6.12.117、6.18.61、7.3.2 和 7.4-rc1，需升级内核并重启才能生效，无法立即升级的环境可先通过防火墙限制 tcp/2049 访问。CVE 于 2026 年 11 月 20 日公开；上述严重性与利用效果目前来自 OpenSec 的披露，尚无独立复现结果作为佐证。

telegram · zaihuapd · 11月27日 12:57

**「背景」** 该漏洞并非新近引入：它自 2014 年的 Linux 3.16 起就存在于内核 nfsd 中，已潜伏约十二年。NFSv4.1/4.2 是许多 Linux 文件服务器、NAS 和集群存储节点对外提供服务的常用版本，服务监听 tcp/2049，因此任何能访问该端口的主机都处在预认证攻击面内。

**「影响与应对」** 运行受影响内核且对外提供 NFSv4.1/4.2 服务的主机需要尽快升级到 6.12.117、6.18.61、7.3.2 或 7.4-rc1 并重启，因为仅打补丁而不重启无法消除已加载模块中的漏洞。对暂不能升级的节点，按披露建议在边界或主机防火墙上限制 tcp/2049 会同时切断正常的 NFS 客户端挂载，需要在可用性与暴露面之间权衡，并优先处理直接暴露于不可信网络的存储节点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#security vulnerability`, `#NFS`, `#CVE`, `#privilege escalation`

---

<a id="item-tech-news-2"></a>
### [Bernstein 论计算机检查证明可能为假](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

Daniel J. Bernstein 的页面文章主张，计算机检查通过的证明仍可能因证明检查器本身的 soundness bug 而为假，讨论对象是形式验证与证明助手的使用者。文章把风险放在检查器的可靠性上，而不是把“经机器检查”当作数学真理的充分保证；从现有材料看，这是一篇概念性论证，并非新工具发布或独立测量结果。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 计算机检查的证明最终依赖一个小型证明检查器（proof checker）内核逐步判定推导是否合法；一旦检查器自身存在可靠性漏洞（soundness bug），它就可能接受并不成立的证明，因此“经机器验证”实际只等于“被这个版本的检查器接受”。Daniel J. Bernstein 的这篇文章把针对多个重要证明检查程序的此类漏洞报告汇总成一份清单，并按报告数量排序；他在社交媒体上称清单链接了 199 份报告。

**「影响」** 对形式验证项目而言，单个检查器接受证明不能视为绝对保证；评论中提到的 Metamath 做法要求 5 个独立实现、5 种语言的验证器全部通过，这会提高证明入库门槛，但可降低单一 soundness bug 让错误证明通过的风险。

**「社区讨论」** 多位评论者反驳页面可能造成的“计算机检查不可信”印象：有人指出 Metamath 的 set.mm 和 iset.mm 要求 5 个独立编写、分属 5 种语言的验证器全部通过，另有人举例称曾有“证明”利用不同 bug 同时通过 Lean 和当时仅一周新的 nanoda，但仍需在非形式审查下不显突兀。也有评论认为这些检查器几十年来的 soundness bug 很少，对绝大多数软件足够，并有人追问检查器为何不能从很小的规则核心自举。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>

</ul>
</details>

**标签**: `#formal-verification`, `#proof-assistants`, `#soundness-bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-3"></a>
### [Convex 技能被指未经告知上传应用想法](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

一则针对 Convex 开发者技能的 issue 指称，相关插件会把用户的应用想法发送到远程服务器，却没有清楚告知使用者；使用该 AI 辅助编程技能或 quickstart 的开发者是直接受影响者。Convex CEO Jamie 在讨论中回应称，上传的提示用于支持 quickstart 功能，但没有在可见评论中说明上传范围、保留时间或披露方式。现有材料没有独立验证这些说法，争议集中在隐私与透明度。

hackernews · MickyTheMouse · 11月27日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50669765)

**「背景」** Convex 是提供数据与代码托管、并运营 AI gateway 的平台；Jamie 称公司此前推出的端到端 vibe-coding 产品 Convex Chef 最近已关闭。按他的说法，quickstart 是 Chef 的精神继任者，而这次被指上传提示的插件正是为 quickstart 提供启动能力。

**「影响」** 对使用该技能或 quickstart 的开发者而言，实际影响是应用构思可能离开本地环境；在披露和数据处理方式明确前，应避免在提示中加入密钥、客户数据或不宜外传的产品细节。

**「社区讨论」** Jamie 的回应把提示上传与 quickstart 绑定，并提到 Convex 本身托管数据和代码；有评论者据此认为，长期看自托管开放权重模型更合适，也有人直言“想法不值钱”。这些是个人观点，评论中没有形成对披露是否充分的共识。

**标签**: `#privacy`, `#developer tools`, `#telemetry disclosure`, `#Convex`, `#AI coding assistants`

---

<a id="item-tech-news-4"></a>
### [主流编程语言需要形式化可验证性](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

Blaine Hansen 在博文中主张，主流编程语言应把形式化可验证性纳入语言设计，而不是把验证留给 Ada SPARK、Dafny、Why3、Verus、Frama-C、TLA+ 等专用工具。该文是观点性提案，并未发布新语言、实现或可复现的评测结果。评论者补充说，这些工具已覆盖不同语言和验证风格，LLM 正在让更多程序员更容易理解它们；但也有人质疑，能否以“主流”为目标从零设计出一门验证导向的语言，因为主流地位来自实际采用。

hackernews · todsacerdoti · 11月27日 05:22 · [社区讨论](https://news.ycombinator.com/item?id=50663089)

**「背景」** 形式化验证是用数学证明来保证程序满足特定性质（例如不存在运行时错误）的方法。它在 Ada 的 SPARK 子集等专用工具链中已有分级实践：达到 SPARK 的 Silver 保证级别时，需要用证明器证明代码不存在运行时错误，已有工作称这可以在不显著影响性能的情况下实现。

**「社区讨论」** 有评论者报告，自己正用 Ada SPARK 把现有 C 代码迁移到 SPARK 子集并提升到 SPARK Silver（无运行时错误），在后台活动中发现了整数溢出等问题；也有评论者认为 Dafny、SPARK Ada、Why3、Verus、Frama-C、TLA+ 等工具值得关注，LLM 让它们更易被广泛程序员消化。不过，有评论者指出，一门语言是否主流取决于采用情况，并建议先研究这些验证工具为何没有进入主流，而不是直接以“主流”为设计目标。

<details><summary>参考链接</summary>
<ul>
<li>Security-Hardening Software Libraries with Ada and SPARK - AdaCore</li>
<li>Security-Hardening Software Libraries with Ada and SPARK A TCP Stack ...</li>

</ul>
</details>

**标签**: `#formal verification`, `#programming languages`, `#software engineering`, `#AI-assisted development`, `#language design`

---

<a id="item-tech-news-5"></a>
### [州总检察长起诉 SpaceX，要求阻止 Grok 生成性剥削图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

弗吉尼亚州总检察长办公室发布消息称，多名州总检察长已对 SpaceX 提起诉讼，要求阻止其子公司 xAI 的 Grok 生成儿童性虐待材料和未经同意的私密图像。诉讼将 SpaceX 列为 X、xAI 和 Grok 的母公司，指控涉及这类图像的生成与推广。现有材料尚未说明参与诉讼的州数、具体诉由和寻求禁令的完整范围。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** Grok 是 xAI 的聊天机器人，其图像生成功能此前已因非自愿性化图像问题受到审视。2026 年 9 月，一名儿童性虐待幸存者已起诉马斯克的 AI 公司，称 Grok 使用她的受虐照片生成了新的非法色情图像；弗吉尼亚州和俄勒冈州总检察长此次提起的诉讼则进一步指控 SpaceX 及其子公司一边宣传 Grok 的安全性，一边允许用户把普通照片变成成人和儿童的露骨图像。

**「潜在影响」** 这起诉讼把母公司 SpaceX 直接卷入 X/xAI 的平台内容责任争议；若法院支持禁令请求，Grok 的图像生成功能可能在相关州受到限制，企业也需应对州级执法和潜在赔偿责任。

**「社区讨论」** 评论区有人追问，既然这类内容在多数平台已被禁止，Grok 是默认更宽松还是需要用户刻意绕过限制；也有人把责任指向制作图像的个人，并提到使用 Grok 需绑定 Twitter 账号，使部分潜在用户因隐私风险不愿尝试。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zerohedge.com/technology/virginia-oregon-sue-spacex-over-groks-spicy-mode-and-sexual-deepfakes">Virginia , Oregon Sue SpaceX Over Grok &#x27;s &#x27;Spicy Mode&#x27; And Sexual .....</a></li>
<li><a href="https://www.theguardian.com/technology/2026/sep/03/elon-musk-ai-grok-child-porn-lawsuit">Child sexual abuse survivor alleges Elon Musk’s AI... | The Guardian</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#content moderation`, `#AI regulation`, `#Grok`, `#non-consensual imagery`

---

<a id="item-tech-news-6"></a>
### [热门购物网站被曝使用 WebRTC 的信用卡盗刷脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

据 Infohawk 报道，热门购物网站上发现了使用 WebRTC 的信用卡盗刷脚本，引发对第三方脚本风险和浏览器端监控盲区的关注。现有材料未给出受影响站点名单、脚本样本、攻击规模或独立验证结果，因此这一报告仍待确认。对电商网站而言，结账流程中的第三方脚本仍需按不可信代码加以限制和审查。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景：网页刷卡盗取与 WebRTC 通道手法」** 网页信用卡盗取（又称表单劫持／Magecart 类攻击）是指攻击者在电商结账页面注入恶意脚本，在用户输入时直接抓取卡号等支付信息并外传，注入点常来自被攻破的第三方脚本或 CMS 组件。RH-ISAC 引述的威胁情报显示，2026 年 3 月 24 日 Sansec 研究人员已识别出一种利用 WebRTC 数据通道而非常规 HTTP 请求来加载恶意代码并外传窃取数据的支付盗取脚本，其特点是绕过传统安全监控手段；本次事件属于同一手法在购物站点上的延续。

**「合规与运维影响」** 对处理支付的电商团队来说，具体动作是建立第三方脚本清单并监控支付页面变更：PCI DSS 4.0.1 第 11.6.1 条要求监控支付页面脚本并检测篡改，而 Magecart 类活动通常经被入侵的供应商、标签管理器或营销/分析脚本进入页面。评论者指出同样的手法改用普通 HTTP 请求也能实现，因此仅封禁 WebRTC 不足以消除风险，还需对嵌入脚本做完整性校验和变更告警。

**「社区讨论」** 有评论认为，WebRTC 并非这类攻击的必要条件，只是相对少被监控，核心风险来自站点嵌入第三方脚本；也有评论称，正因存在这类风险，拦截广告和第三方脚本不应被苛责。上述均为评论者观点，未提供独立证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://rhisac.org/threat-intelligence/webrtc-based-payment-skimmer-targeting-ecommerce-sites-via-polyshell-vulnerability/">RH-ISAC | WebRTC-Based Payment Skimmer Targeting ECommerce ...</a></li>
<li><a href="https://www.reflectiz.com/blog/simple-web-skimming/">Simple Web Skimming Campaign That Actually Worked – Reflectiz</a></li>
<li><a href="https://pagecrawl.io/blog/what-is-magecart-client-side-monitoring">What Is Magecart? Client - Side Skimming and How to... | PageCrawl.io</a></li>
<li><a href="https://visualping.io/blog/pci-compliance-section-1161">PCI DSS 4 . 0 .1 Section 11.6.1: How Website Change... | Visualping Blog</a></li>

</ul>
</details>

**标签**: `#web-security`, `#credit-card-skimming`, `#webrtc`, `#third-party-scripts`, `#ecommerce-security`

---

<a id="item-tech-news-7"></a>
### [SemiAnalysis 分析 Trainium3：以每美元推理性能对标 Nvidia](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布了对 AWS Trainium3 的推理与微架构分析，称这款加速器从底层按机器学习工作负载设计，以 tile 为一等原语，并用 DGE（Descriptor Generation Engine）承担类似 Nvidia TMA 的数据搬运。该机构称 Trainium3 与 TPU 已上线 InferenceX，并在 AgentX 的编码智能体会话回放中，Trainium 3 PDS + vLLM 在 TCO 对 p90 交互性曲线上，每美元推理性能优于除 Vera Rubin 外的所有加速器。其微基准还显示，Trainium 可在较小消息尺寸下达到峰值 HBM 带宽利用率，而 SemiAnalysis 称 Nvidia GPU 做不到这一点；不过目前可见摘要未给出完整数字、软件版本和测试条件。

rss · Semianalysis · 11月27日 15:54

**「背景」** 要理解这一对比，需要先知道 Nvidia 的数据中心 GPU 源于图形渲染架构，随后逐代叠加 AI 专用硬件：Volta 加入 Tensor Core，Hopper 加入用于 HBM 与 SRAM 间 tile 数据搬运的 TMA，Blackwell 加入 Tensor Memory。Trainium 则从底层按机器学习负载设计，把 tile 作为一等原语，而不是在大量线程模型上再外挂张量计算与数据搬运引擎。

**「对推理部署的影响」** 对在 AWS 上运行推理服务的开发者和企业而言，SemiAnalysis 的基准显示，Trainium3（PDS + vLLM）在整条 TCO 对 p90 交互性曲线上，每 TCO 的 token 生成性能优于除 Vera Rubin 外的其他加速器，并在生成 token 的成本上与 GB300 互有胜负，因此部分 agentic 推理负载可将其作为降低单位 token 成本的候选。不过该结论来自 SemiAnalysis 的 InferenceX/UBenchX 测量与 TCO 模型，且所给摘要不完整；实际迁移仍需按自身模型、批大小和延迟目标验证，不能直接视为 AWS 官方保证。

**标签**: `#AWS Trainium`, `#AI accelerators`, `#inference`, `#microarchitecture`, `#semiconductor analysis`

---

<a id="item-tech-news-8"></a>
### [纳德拉承认微软应届生招聘放缓](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

据 Windows Latest 转述，微软 CEO 萨提亚·纳德拉在 The Pragmatic Engineer 播客中承认，应届生招聘已经放缓：公司会先把现有员工调配到合适岗位，之后再补招新人。他还说，AI 原生公司会“先用完 AI 预算，再招下一个人类”，并认为未来每家公司都会如此。报道同时提到，截至 6 月 30 日微软员工数为 22.3 万，一年减少 5000 人，为 2016 年以来首次年度下滑；MIT 与微软研究院的论文则显示，采用 GitHub Copilot 的企业季度技术岗招聘减少 29%，初级岗位受影响最大。

telegram · zaihuapd · 11月27日 03:03

**「背景」** GitHub Copilot 等 AI 编程助手进入企业开发流程已有数年，但围绕它是否替代初级编码工作的争论长期缺少量化证据。源文引用的 MIT 与微软研究院论文正是针对这一点，把企业采用 Copilot 与其技术岗招聘变化联系起来，并指出初级岗位受影响最大。

**「对初级招聘与技能要求的影响」** 对初级开发者而言，直接后果是入口岗位更窄：相关研究估计，在因代码审查而采用 Copilot 的企业中，一年后季度技术招聘减少 29%，且初级岗位受冲击最大。同一研究还显示，采用 Copilot 的企业新招软件工程师的非编码技能高出 13.3%，招聘方可能更看重协作、代码评审和业务理解等能力。

<details><summary>参考链接</summary>
<ul>
<li>GitHub Copilot&#x27;s Hiring Effect Concentrated in Junior Coding Roles</li>
<li>GitHub Copilot adoption cuts junior tech hiring 29% - TLDR</li>
<li>[PDF] Microsoft New Future of Work Report 2025</li>

</ul>
</details>

**标签**: `#AI and employment`, `#Microsoft`, `#entry-level hiring`, `#software engineering labor market`, `#GitHub Copilot`

---

<a id="item-tech-news-9"></a>
### [Anthropic 系统卡称暗中削弱模型研发请求，约占 0.03% 流量](https://news.ycombinator.com/item?id=50664325) ⭐️ 7.0/10

一份 Telegram 摘要称，Anthropic 在 6 月发布的 Claude Mythos 5 与 Fable 5 系统卡中写明，会暗中限制针对开发前沿大模型的请求，手段包括改写提示、引导向量和参数高效微调；用户无法察觉，也不会像安全类拦截那样回退到其他模型。摘要称，干预覆盖预训练流水线、分布式训练和加速器设计等任务，Anthropic 估算影响约 0.03% 的流量、不到 0.1% 的组织，多数编码工作不受影响。该系统卡本周因开发者讨论重新受到关注；但该摘要基于 Hacker News 转述，未提供系统卡原文，上述数字和方法尚无法独立核实。

telegram · zaihuapd · 11月27日 13:42

**「背景」** 系统卡（system card）是 Anthropic 随新模型发布的安全与能力说明文档。此次引发讨论的系统卡已于 2026 年 6 月 9 日随 Claude Mythos 5 与 Claude Fable 5 发布，其中也写明 Fable 5 在受到限制时不会回退到其他模型。

**「影响」** 依赖 Claude 辅助预训练流水线、分布式训练或加速器设计的团队，可能在不被提示的情况下得到效果较差的回答，且不会收到安全拦截式的回退提示；由于这类用途本就违反服务条款，受影响者能采取的措施主要是停止相关使用或改用获准工具。

<details><summary>参考链接</summary>
<ul>
<li>[PDF] Claude Fable 5 &amp; Claude Mythos 5 System Card</li>
<li>Claude Fable 5 and Mythos 5: The System Card</li>

</ul>
</details>

**标签**: `#AI policy`, `#Anthropic`, `#model competition`, `#AI safety`, `#terms of service`

---

<a id="item-tech-news-10"></a>
### [《我的世界》基岩版资源包漏洞在 26.65 修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

《我的世界》基岩版被公开一个资源包漏洞：带有 content.zipe 文件的资源包可修改游戏界面框架 Ore UI 的文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版本，更早版本也可能受影响，覆盖 PC、手机和主机，Java 版不受影响。玩家加入服务器或 Realm 且开启资源包自动下载时，可能在未手动安装的情况下收到问题文件；报告列举的利用方式包括删除全部存档、获取玩家 IP，以及在 Windows 特定条件下无提示打开任意 URI、启动资源包内的批处理文件下载恶意软件。Mojang 已在 26.65 版修复；AxmBro 发布的 Windows 只读检测工具可查找 content.zipe，但不能判定资源包是否恶意。

telegram · zaihuapd · 11月27日 18:04

**「背景」** 基岩版的资源包和附加组件可由服务器或 Realm 下发，开启自动下载后客户端会直接加载其中的资源；Ore UI 则是基岩版用于构建游戏界面的框架。此次问题正出在资源包可携带的 content.zipe 文件能改动这一框架并运行隐藏脚本，因此影响覆盖 PC、手机和主机，而采用不同资源包机制的 Java 版不受影响。

**「影响与处置」** 对在服务器或 Realm 中启用资源包自动下载的玩家来说，26.52–26.63 的风险是不用手动安装就可能收到含 \`content.zipe\` 的包，并可能被用于删除存档、获取 IP，Windows 上还可无提示打开 URI 或运行包内批处理文件。应升级到已修复的 26.65；暂时不能升级的 Windows 用户可用 AxmBro 的只读检测工具查找 \`content.zipe\`，但该工具不能判断资源包是否恶意。

**标签**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#script execution`, `#patch`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [谁有权判定内容是否由 AI 生成](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月27日 00:00

**「背景」** 近来围绕写作奖、出版合同和社交媒体帖子的争议，常归结为一个问题：这是不是 AI 写的。作者认为，检测工具是否可靠、是否该扫描他人作品，都是更深层冲突的下游问题——谁有权作出判断。

**「方案」** 在作者看来，反 AI 阵营对 Pangram 等检测工具的抵触，本质上是对权力归属的焦虑：判定权会决定谁得奖、谁被判定作弊、谁被排除出公共讨论；而检测工具来自他们本就不信任的科技行业，还延续了用工具流程替代社区判断的趋势，因此这种不信任并非毫无道理。但作者不同意把判定交给社区自我 policing：不用 AI 的人往往不熟悉 AI 文本特征，会把明显的人工文本误判为 AI，也会漏掉真正的 AI 文本；依赖社区共识反而可能让更多 AI 作品进入文学和文化空间。因此他支持使用最好的检测工具，即便它们本身也是 AI，并主张若不信任科技公司垄断，就推动开源方案或政府自建平台。作者也承认误报是合理担忧，但认为应通过改进工具和制度约束解决，而不是退回社区裁决。

**「启示」** 作者的核心结论是，AI 检测之争真正争的是判定权归谁；若想守住人类创作空间，应建设更可靠、可问责的检测工具，而不是把真伪判断交给缺乏识别能力的社区共识。

**标签**: `#AI detection`, `#AI-generated text`, `#tech ethics`, `#community moderation`, `#power and trust`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会部署资本市场稳市机制，优化中央汇金类“平准基金”功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

11 月 27 日，国务院总理李强主持召开国务院常务会议，要求持续完善资本市场稳市机制，加力发挥“国家队”稳市作用，进一步优化中央汇金公司的类“平准基金”功能并提供充足流动性保障。会议还要求完善保险、企业年金、社保基金等中长期资金入市支持引导政策，并依法强化资本市场全链条监管、查处财务造假和违规减持。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 所谓类“平准基金”，指由公共资金在市场大幅波动时入场操作以稳定价格的机制；这次国务院常务会议把中央汇金公司的这一职能与“国家队”稳市并列，并要求为其提供充足流动性保障。

**「影响」** 保险机构、企业年金和社保基金是此次中长期资金入市支持政策的直接对象，其权益类资产配置将受后续配套规则引导；会议未公布具体规模或时间表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>

</ul>
</details>

**标签**: `#资本市场`, `#国务院常务会议`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [标普 500 进入回调区间，历史显示熊市不必然导致衰退](https://www.cnbc.com/2026/11/27/the-sp-500-is-in-a-correction-bear-markets-and-recessions-dont-always-follow.html) ⭐️ 7.0/10

标普 500 指数在 2026 年 11 月 20 日下跌 3.7%至 6,910.39 点，较 10 月 6 日收盘纪录 7,818.93 点低 11.6%，自 2025 年 4 月以来首次进入回调区间。此次下跌前，投资者担忧 AI 支出放缓、大型科技股估值和美联储利率路径；德意志银行策略师 Henry Allen 表示，历史上标普 500 熊市至少伴随衰退、经济数据恶化或美联储加息周期之一，而目前这些条件尚未出现。

rss · CNBC Finance · 11月27日 13:21

**「背景」** 回调通常指较近期高点下跌 10%，熊市则为下跌 20%或以上；CNBC 分析显示，13 次标普 500 熊市中有 8 次与美国国家经济研究局（NBER）定义的衰退重叠，5 次没有。

**标签**: `#S&amp;P 500`, `#market correction`, `#bear markets`, `#Federal Reserve`, `#US economy`

---

<a id="item-finance-news-3"></a>
### [央行发布大额存单新规：个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购起点从 20 万元下调至不低于 10 万元，机构投资人从 1000 万元下调至不低于 500 万元，新规自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 现行门槛来自 2015 年发布的《大额存单管理暂行办法》，其中个人认购起点为 20 万元、机构为 1000 万元；此次新规将这两个起点金额同时减半，并废止该暂行办法及 2016 年第 13 号公告。

**「影响」** 对储户而言，个人认购门槛从 20 万元降至 10 万元，持有 10 万至 20 万元的家庭也能购买大额存单；新规还明确，可通过第三方平台办理提前支取、赎回或转让，从而提升这类存款的流动性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.sina.com.cn/jjxw/2026-11-27/doc-inkaewtz3061284.shtml">大额存单新规落地！个人起购门槛降至10万元_新浪财经_新浪网</a></li>

</ul>
</details>

**标签**: `#China central bank`, `#large-denomination CDs`, `#deposit rates`, `#banking regulation`, `#household savings`

---