---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 35 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [英伟达董事会重新任命黄仁勋为 CEO](#item-tech-news-1) ⭐️ 8.0/10
2. [Ladybird 进入 alpha：macOS 与 Linux 可直接安装](#item-tech-news-2) ⭐️ 8.0/10
3. [Nospeaker：用 MacBook 触控板触觉马达发声](#item-tech-news-3) ⭐️ 7.0/10
4. [智谱发布 GLM-5.4：首个循环 Transformer 编程模型](#item-tech-news-4) ⭐️ 7.0/10
5. [Win4wine：用 Wine 把 Windows 外壳当作 Linux 桌面运行](#item-tech-news-5) ⭐️ 7.0/10
6. [谷歌搭建模拟互联网测试 Chrome AI 代理](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](#item-tech-news-7) ⭐️ 7.0/10
8. [Codex2api 疑遭供应链投毒：后门版本导致未授权 RCE 与密钥外泄](#item-tech-news-8) ⭐️ 7.0/10

**科技博客**
1. [跳过 DRAM 层：MoRI UMBP 用 NVMe 承载 Agent KV 缓存](#item-tech-blog-1) ⭐️ 8.0/10
2. [不确定时，如何有效地“乱撞”](#item-tech-blog-2) ⭐️ 6.0/10
3. [OpenAI 困惑度曲线笔记：指标、训练与透明度](#item-tech-blog-3) ⭐️ 5.0/10

**财经新闻**
1. [上海地铁票价 21 年来首次调整，起乘价 3 元](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [英伟达董事会重新任命黄仁勋为 CEO](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 8.0/10

英伟达董事会重新任命黄仁勋为首席执行官，此前董事会曾突然将其免职。董事会声明称，在作出决定的过程中收到了来自美国政府高级层级的意见，并据此认为黄仁勋复职不构成国家安全风险。就目前提供的报道内容看，信息主要停留在标题和声明层面，免职的具体原因、法律依据以及复职是否附带条件均未充分披露。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「背景」** 据 BBC 报道，黄仁勋本月早些时候卸任，起因是他承认与一名被指为中国间谍的女性有婚外情，同时还有他与一名 Nvidia 高管存在婚外情的指控。Nvidia 董事会在复职声明中表示，作出这一决定时收到了美国联邦政府高层人士的意见，并据此认为黄的复职不构成国家安全风险。

**「政策与合规影响」** 对英伟达及其中国客户而言，复职决定带来的直接后果是出口管制不确定性上升：路透报道美国两党议员批评董事会恢复黄仁勋职务，并主张国会收紧中国获取英伟达先进 AI 芯片的限制。相关主张目前仍是立法压力而非已生效的新规，但采购方和开发者需要把更严格的许可要求、产品分级及中国区供货条件纳入后续部署评估。

**「社区讨论」** 讨论中最集中的关注点是董事会声明里“收到美国政府高级层级意见”这一句，有评论者认为这才是真正起决定作用的部分。有评论者结合特拉华州 Caremark 判例和其所称的司法部不予起诉态度，推测董事的个人责任风险因此降低，并对不到两周内从免职到董事会一致复职的转变感到意外；也有人反驳在缺乏实质证据前就假定英伟达犯罪的说法。另有评论者批评美国在要求 ASML 和日本芯片企业配合对华限制的同时，却让英伟达获得白宫支持，认为这种做法虚伪。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as...</a></li>
<li><a href="https://www.nbcnews.com/tech/tech-news/nvidia-reinstates-jensen-huang-rcna610864">Nvidia reinstates Jensen Huang as CEO</a></li>
<li><a href="https://www.bbc.com/news/live/crd61y5dwqgpt">Jensen Huang reinstated as Nvidia CEO , board says - BBC News</a></li>
<li><a href="https://www.reuters.com/business/lawmakers-criticize-nvidia-decision-reinstate-huang-ceo-2026-11-23/">US lawmakers criticize Nvidia decision to reinstate Huang as CEO</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI hardware`, `#corporate governance`, `#national security`, `#semiconductors`

---

<a id="item-tech-news-2"></a>
### [Ladybird 进入 alpha：macOS 与 Linux 可直接安装](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird 项目发布了首个 alpha 版本，macOS 和 Linux 用户现在可以直接安装，无需自行编译。该浏览器从零实现 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 等大部分核心组件，仅复用 HarfBuzz、Skia、ffmpeg 和 SQLite 等少数外部库；试用中可见它按标签页分出独立进程。试用报告显示，多数网站和 WebAssembly 应用（如 ffmpeg 视频压缩、Pyodide REPL）可正常运行，但 Datasette Lite 因缺少 \`navigator.serviceWorker.startMessages\` 而失败，作者已提交 issue，源码中对应位置也有 FIXME。官方强调这仍是 alpha：部分网站会不工作、浏览器有时会崩溃，用户可从浏览器内报告损坏站点，并在崩溃后自行决定是否发送崩溃报告。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 起源于更早的 SerenityOS 项目，目标是从零实现浏览器的核心组件；不过它仍借助 HarfBuzz、Skia、FFmpeg 和 SQLite 等成熟库来处理文字排版、2D 图形、视频与数据存储。此次发布 alpha 之前，用户需要自行编译 Ladybird，而现在项目提供了面向 macOS 和 Linux 的预编译安装包。

**「社区讨论」** 多名评论者报告实际站点兼容性超出预期：新闻站点、Proxmox/NoVNC、YouTube 和 Google Maps 可正常加载，其中 NoVNC 被称比 Firefox 更流畅，但也有滚动略顿、视频和地图较卡的体验。另一条讨论认为改用 SQLite、Skia 等成熟组件显著提升了可用性，同时有人怀念 SerenityOS 时期尽量自研组件的黑客精神。

**标签**: `#browsers`, `#open-source`, `#web-engines`, `#ladybird`, `#software-engineering`

---

<a id="item-tech-news-3"></a>
### [Nospeaker：用 MacBook 触控板触觉马达发声](https://github.com/os6/nospeaker) ⭐️ 7.0/10

GitHub 上出现名为 Nospeaker 的爱好者项目，利用 MacBook 触控板内的触觉马达发声，让触控板充当扬声器。项目作者为 yakkomajuri，目前公开材料主要是代码仓库和一段发布在 X 上的演示链接，尚无从独立测试确认其音质、音量或适用机型范围。

hackernews · yakkomajuri · 11月23日 11:31 · [社区讨论](https://news.ycombinator.com/item?id=50610318)

**「背景」** MacBook 的 Force Touch 触控板依靠触觉引擎产生反馈，而不是靠整块面板下沉来形成物理按键行程，因此同一套硬件可以被重新驱动。Apple 的 Core Haptics 允许应用组合和叠加自定义触觉模式，系统控件在受支持设备上也会自动播放触觉反馈。Nospeaker 所做的，是把这类原本用于触觉提示的致动器推到可听频段。

**「实际影响」** 该项目面向 MacBook 触控板硬件，输出的是由触觉马达产生的有限声音，并非通用扬声器替代方案；复现者需要依赖 Apple 的触觉反馈接口，兼容性取决于具体 MacBook 硬件。

**「社区讨论」** 有评论者认为，比起让触控板发声，静止的触控板能模拟出按键手感更令人印象深刻；还有人把它与 Commodore 1541 软驱马达播放音乐的做法相提并论。关于 Apple 的触觉 API，一位评论者推测正弦和表示可能用于防止马达过热、做前馈补偿或降低 USB/HID 带宽，并好奇 Magic Trackpad 2 的 USB 数据流会是什么样。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.apple.com/documentation/corehaptics">Core Haptics | Apple Developer Documentation</a></li>
<li><a href="https://developer.apple.com/design/human-interface-guidelines/playing-haptics">Playing haptics | Apple Developer Documentation</a></li>
<li><a href="https://tech.yahoo.com/ai/apple-intelligence/articles/macbook-modder-turns-apple-force-130000737.html">MacBook modder turns Apple’s Force Touch trackpad into a ...</a></li>

</ul>
</details>

**标签**: `#hardware-hacking`, `#haptics`, `#apple`, `#macbook`, `#audio`

---

<a id="item-tech-news-4"></a>
### [智谱发布 GLM-5.4：首个循环 Transformer 编程模型](https://z.ai/blog/glm-5.4) ⭐️ 7.0/10

智谱（Zhipu）发布 GLM-5.4，称其为首个采用循环 Transformer（loop transformer）架构的模型，定位是面向通用编程的编码模型。按社区中的解释，这类架构让同一组层权重在一次推理中被反复计算，而不是每层只算一次，目的是缓解推理时把整层权重从 HBM 搬进芯片所带来的显存带宽瓶颈。Hacker News 用户报告称，GLM-5.4 目前无法通过 OpenRouter 或 Z.ai 常规 API 套餐调用，需改用 Coding Plan 获取可访问该模型的 API key。由于原始博客内容未能获取，具体参数量、上下文长度和基准成绩尚无法核实，目前也没有独立测评验证其编程能力宣称。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「循环 Transformer 与 GLM-5 基座」** 循环 Transformer 的核心机制，是让同一组共享层在推理时重复执行多次，从而在不增加参数量的情况下增加计算深度；按模型介绍页的说法，GLM-5.4 借此获得接近 2T–3T 参数模型的推理能力。据 wccftech 报道，Z.ai 并未从零训练这一架构，而是基于已预训练的 GLM-5 基座继续训练，使其适配循环机制。另有介绍称，GLM-5.4 的 78 层中有 28 层会运行两次，但相关性能对标仍属厂商说法。

**「接入与延迟的现实约束」** 希望在项目中试用 GLM-5.4 的开发者需要注意接入路径：评论者 simonw 报告该模型未出现在 OpenRouter 或 Z.ai 常规 API 套餐中，他必须改用 Coding Plan 才能拿到可调用新模型的密钥，这意味着已有常规 API 集成的团队需要额外走一遍订阅与密钥配置。另有评论者反映，这类模型在简单任务上也会进行长时间自检，端到端完成时间明显高于前沿模型；而 loop transformer 本身的取舍是用更多逐 token 计算换取更少的权重搬运，因此内存带宽上的节省并不自动等于更低延迟。

**「社区讨论」** 有评论者认为循环 Transformer 是顺理成章的方向，并称赞智谱公开了较多技术细节，与西方公司封闭的做法形成对比；另有用户从推理效率角度解释，循环结构让权重留在芯片上复用，可减少每生成一个 token 时的 HBM 搬运。也有用户抱怨包括该系列在内的中国模型常陷入冗长的“马拉松式思考”，在概念上很简单的任务上仍反复自我怀疑，完成时间明显长于前沿模型——这属于个人使用体验，而非实测结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/z-ai-debuts-glm-5-4-with-a-novel-looped-transformer-architecture-skipping-ai-benchmarks-entirely/">Z.ai Debuts GLM - 5 . 4 With a Novel Looped Transformer Architecture...</a></li>
<li><a href="https://anyrouter.dev/model/z-ai/glm-5.4">GLM - 5 . 4 · Zhipu AI · pricing &amp; API · AnyRouter</a></li>
<li><a href="https://www.youtube.com/watch?v=HVey00YZ5Xk">GLM - 5 . 4 Is Here: The First Loop Transformer , and What... - YouTube</a></li>
<li><a href="https://www.linkedin.com/posts/amrit-rajeev_openai-ainews-activity-7501377985049120769-Cc5n">OpenAI&#x27;s Looped Transformer : A Pragmatic Tradeoff | LinkedIn</a></li>

</ul>
</details>

**标签**: `#GLM-5.4`, `#loop transformers`, `#LLM architecture`, `#coding models`, `#inference efficiency`

---

<a id="item-tech-news-5"></a>
### [Win4wine：用 Wine 把 Windows 外壳当作 Linux 桌面运行](https://github.com/mikuta0407/win4wine) ⭐️ 7.0/10

Win4wine 是一个托管在 GitHub、由 mikuta0407 维护的开源项目，目标是通过 Wine 兼容层运行 Windows 资源管理器（Explorer）外壳，并把它当作 Linux 的桌面环境使用。也就是说，用户在 Linux 上看到的任务栏、开始菜单和文件管理界面，实际来自 Wine 中运行的 Windows 外壳组件，并非原生 Linux 桌面。现有材料没有给出所支持的具体 Wine 版本、Windows 外壳版本或安装条件，项目看起来更接近实验性工具，而非成熟的日常桌面替代品。

hackernews · hard\_times · 11月23日 12:28 · [社区讨论](https://news.ycombinator.com/item?id=50610743)

**「背景」** Wine 是让 Windows 程序无需完整 Windows 系统即可在 Linux 等平台运行的兼容层；Windows Explorer 则是负责桌面、任务栏和文件管理的系统外壳。该项目说明称，win4wine 通过打过补丁的 Wine 运行 Windows XP 自带的 explorer.exe，并把它作为 Linux 的桌面外壳。

**「影响」** 对于希望保留 Windows 外壳操作习惯、又不想更换 Linux 发行版的用户，这个项目提供了一条可以自行尝试的路径。不过，整个桌面体验都取决于 Wine 对 explorer.exe 等外壳组件的兼容程度，因此它更适合作为测试或折腾用途，而非要求稳定性的生产桌面。

**「社区讨论」** 有评论者（londons\_explore）提出，反过来做或许更理想：保留 Windows NT 内核与驱动生态，同时引入 Linux 的开源工具链，因为 Win32 及其界面层只是“平庸”部分。layer8 认为这类方案能运行 AutoHotkey 一类工具，但代价是继承了所模拟的 Windows XP 或 Windows 7 explorer.exe 的漏洞；d3Xt3r 则提到，若只想获得 XP 外观而不使用 Wine，可以使用 XFCE 的 XPTC 主题。

<details><summary>参考链接</summary>
<ul>
<li>README.en.md - GitHub</li>

</ul>
</details>

**标签**: `#Wine`, `#Windows shell`, `#Linux desktop`, `#compatibility layer`, `#open source`

---

<a id="item-tech-news-6"></a>
### [谷歌搭建模拟互联网测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

据蓝点网报道，谷歌为 Chrome 的 AI 代理搭建了一个名为 Mirror Dimension 的模拟互联网，用于在隔离环境中测试其浏览网页和执行任务的能力。该环境包含数千个模拟网站，每名工程师都在单独隔离的环境中测试，每天运行超过 1000 个测试案例。测试覆盖打开网站、搜索浏览、登录、加购和完成任务等操作，重点防御恶意网页中的提示词注入等攻击。目前没有谷歌官方确认，报道也未披露该测试的上线时间或覆盖标准。

telegram · zaihuapd · 11月23日 01:30

**「背景」** 浏览器 AI 代理可以代替用户点击、填写表单和登录；如果它把网页中的恶意内容误当成指令，就会遭遇提示词注入攻击。谷歌安全博客将 Mirror Dimension 描述为一个合成版互联网，让代理能在贴近真实的在线环境中接受测试，同时避免产生真实世界风险；《连线》也把它称为供 Chrome 团队训练浏览代理的大型沙箱。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents: Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘Mirror Dimension’ Internet to Test Its ...</a></li>

</ul>
</details>

**标签**: `#Chrome AI agent`, `#browser automation`, `#prompt injection`, `#AI security`, `#Google`

---

<a id="item-tech-news-7"></a>
### [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上表示，计划于 2027 年秋季与 Windows 11 27H2 一同发布的 Windows Server 2028 将默认不包含 WoW64 兼容子系统，因此开箱无法运行 32 位应用。管理员可通过按需功能（FoD）手动装回 WoW64，在 Server Core 上通常使用 PowerShell 或 DISM；微软称此举旨在减少攻击面并阻止 32 位恶意软件。Windows 11 目前仍保留 WoW64，微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64 是 64 位 Windows 中用于运行 32 位应用的兼容层，长期作为系统默认组件提供，因此管理员通常无需额外配置就能在新服务器上运行旧版 32 位软件。据 wccftech 报道，微软在 Ignite 2026 上介绍了这项调整，这意味着延续数十年的默认 32 位兼容做法将在 Windows Server 2028 上结束；此后，兼容能力需要由管理员显式添加。

**「影响」** 依赖 32 位旧应用的企业在部署 Windows Server 2028 前，需要把 WoW64 作为按需功能加入镜像或安装流程，否则这些应用在默认配置下将无法启动；这也意味着兼容性测试和补装步骤要纳入升级计划。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/microsoft-is-removing-32-bit-app-support-by-default-in-windows-server-2028-but-windows-11-remains-unaffected/">Microsoft Is Removing 32-Bit App Support By Default In Windows ...</a></li>

</ul>
</details>

**标签**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

<a id="item-tech-news-8"></a>
### [Codex2api 疑遭供应链投毒：后门版本导致未授权 RCE 与密钥外泄](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

据 Telegram 频道转述的复盘报告，Codex2api 项目所有者的 GitHub 账号疑似被盗，攻击者绕过 main 分支直接推送 tag，使 Release 流程构建出带后门的版本。其中 v3.1.11 移除了鉴权，等同于可无密码远程执行命令；同时另一个 workflow 将仓库的 16 个 Actions secrets 外传，并波及同一账号下的至少 21 个仓库。报告建议，已安装或升级到 3.1.10–3.1.12 的用户立即停用该版本并回退到 3.1.9，同时轮换 GitHub token、SSH key 以及数据库和 DeepSeek 等相关密钥。上述细节均来自该事件的复盘与群组转述，目前尚无独立第三方验证，应按疑似事件处理。

telegram · zaihuapd · 11月23日 11:21

**「背景」** GitHub Actions 的 secrets 是注入 CI 工作流的凭据；若发布工作流由 tag 触发且有权读取这些 secrets，绕过 main 分支保护直接推 tag 仍可能让构建产物被植入后门并把凭据外传。2026 年 5 月披露的 Megalodon 活动曾在六小时内向 5,500 多个公开仓库注入恶意工作流以批量窃取 secrets，11 月 12 日另有报告称被盗 GitHub 凭据被用于向数千个仓库推送 CI secret stealer。

**「影响与处置」** 直接受影响的是已安装或近期升级到 3.1.10–3.1.12 的 Codex2api 使用者，以及该维护者账号下至少 21 个仓库的 CI 配置；这些仓库的 Actions secrets 可能已经泄露，其中也包括 DeepSeek 等第三方服务密钥。在确认之前，这些用户应停止运行相关版本并回退到 3.1.9，并假定相应 token、SSH key 与数据库凭据已暴露而进行轮换。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.endorlabs.com/learn/github-actions-supply-chain-attack-targeting-ci-secrets-at-scale">Hijacked GitHub Accounts Push “wfx” CI Secret Stealer to ...</a></li>
<li><a href="https://www.stepsecurity.io/blog/megalodon-mass-github-actions-secret-exfiltration-across-5-500-public-repositories">Megalodon: Mass GitHub Actions Secret Exfiltration Across ...</a></li>

</ul>
</details>

**标签**: `#supply-chain attack`, `#security`, `#GitHub Actions`, `#credential compromise`, `#open source`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [跳过 DRAM 层：MoRI UMBP 用 NVMe 承载 Agent KV 缓存](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · 11月23日 00:00

**「背景」** Agent 推理以多轮会话为主：AgentX 回放的中位每轮输入为 142K token，逾 96% 是已见前缀。命中率每提高 1 个百分点约带来 10% 吞吐提升，但 Kimi-K3 每小时写入 2.3–4.6 TB KV，1.8 TB DRAM 池（约 7.6 万美元）只能保留 23–47 分钟。

**「方案」** 作者把 vLLM 的 KV 池直接放到 NVMe，使用 AMD 开源 MoRI 的 UMBP；DRAM 仅留 64GB 写缓冲和 16GiB 读暂存，约占池容量 5%。在 MI355X 上，1.8TB NVMe 池与同尺寸 DRAM 池在 48/70/96 并发会话下吞吐差不超过 1%，两对机器重复仍相近，70 会话的长提示负载也在 1% 内。作者归因于同尺寸、同淘汰策略保留相同 KV，且 vLLM 异步加载把 NVMe 延迟藏在请求等待 prefill 的时间里。工程上，在 AgentX 70 会话下把段文件从 4GiB 降到 256MiB，使命中率从 94.45% 升到 95.65%、吞吐从 11,672 升至 13,492 tok/s/GPU；touch 上报 GPU 已命中的前缀以免池误淘汰；在 kvlab 8 会话、DRAM 池测试中每 7168 token 设检查点，把命中率从 91.4% 提到 95.6%。按标价算术，DRAM 约 4.2 万美元/TB 持有，NVMe 约 0.36 美元/TB 写入，故 1.8TB NVMe 池（按损耗更换）与能存一天的 83TB 池五年成本都约 5.9 万美元，低于 1.8TB DRAM 池的 7.6 万美元；低于约 24 分钟保留时 DRAM 反而更便宜。作者也提醒所有 KV 都写 SSD，96 会话下测试盘约 5.5 个月耗尽寿命，需分布式池分摊写入；成本为标价推算，范围限于特定 AMD/Kimi 负载。

**「启示」** 文章的核心论点是：Agent KV 缓存应优先看命中率与保留时长，同尺寸 NVMe 池可追平 DRAM，并在长保留场景显著降本；但 SSD 寿命与有限负载范围仍是前提。

**标签**: `#KV cache`, `#NVMe`, `#vLLM`, `#agentic serving`, `#SSD wear/cost`

---

<a id="item-tech-blog-2"></a>
### [不确定时，如何有效地“乱撞”](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 工程师常会遇到没有明确指引、也不知道什么做法有用的局面：该谨慎等待更多理解，还是先行动？作者认为多数情况下应有意识地“乱撞”，但警告方式不当会损害职业声誉。

**「方案」** 他的方法是大量尝试不同方案，密切观察同事、用户和实际指标给出的反馈，并果断放弃没有积极反馈的计划。多方案既能增加接触现实的机会，也能避免只押一个计划而过度投入——多数计划本会失败，十个里有一个有效即可。以已退役的 GitHub Models 为例，许多功能和集成没有奏效，但允许用 GitHub Actions token 运行 AI 推理的尝试意外有黏性，后来成为“Continuous AI”的种子。工程上，他反对先彻底摸清庞大且快速变化的系统，主张做若干试探性改动并观察效果，有改善再深挖，否则立即放弃；组织问题上，则可自动化手工工作、主动承担任务或提出长期方案，但此时尤其要读懂反馈，失败就撤能建立信任，忽视反馈则可能把不满引向自己。作者还提醒，执行者内心会觉得像在反复失败，但这种“乱撞感”是需要克服的心理障碍，而非停止实验的信号。

**「启示」** 作者的核心结论是：信息不足时，成效来自扩大试错、保持反馈敏感并快速止损，而非先想出完美答案；这种主观上难受的“乱撞”，是穿越工程与组织不确定性的实用策略。

**标签**: `#engineering judgment`, `#ambiguity`, `#experimentation`, `#feedback loops`, `#tech organizations`

---

<a id="item-tech-blog-3"></a>
### [OpenAI 困惑度曲线笔记：指标、训练与透明度](https://seangoedecke.com/notes-on-openais-perplexity-reveal/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** OpenAI 公布了其已发布模型随时间的困惑度曲线，作者认为这是外界少有的窥见前沿实验室内部训练指标的机会，并据此讨论该指标的能力含义与对齐透明度。

**「方案」** 作者指出，困惑度必须绑定特定留出数据集，因此不同来源的数据只有用同一数据集才可比较；它只反映模型对文本的预测能力，基本属于预训练指标，而据传预训练在前沿模型总训练时间与算力中可能只占一半或更少，强化学习部分的成效无法从中看出。若相信预训练创造能力、强化学习只是激发能力，困惑度可视为能力指标，但链式思维等能力未必与它相关。图中很少模型共享同一基座，作者特别提到 4.1 与 o3 同基座却表现差异很大；GPT-4.5 像是短暂停止扩大预训练的节点，其困惑度与 GPT-5.3-Codex 接近但实用性低得多，而 GPT-5.2 之后困惑度损失明显加速，这与“实验室已放弃预训练、转向强化学习”的流行说法相矛盾。对齐方面，作者欢迎这种透明度，但怀疑其实际作用：突发下降可能只有 OpenAI 自己能发现，除非持续公布未发布预训练模型的数据；若要用困惑度阈值做承诺，还需说明留出数据集。作者的个人体感也不完全吻合曲线：GPT-3.5 到 GPT-4 的跃升很明显，之后大体停滞至 GPT-5.5 再加速，但他认为 o3 和 GPT-5.3-Codex 才是体感上的大跳，可能来自强化学习对思维链或迎合行为的改善，而非困惑度。

**「启示」** 作者的核心结论是，困惑度曲线既显示预训练仍在快速进步，也暴露该指标只覆盖训练的一部分，因而不足以单独支撑能力判断或对齐监督；透明度有价值，但需数据集与方法细节才能兑现。

**标签**: `#perplexity`, `#LLM pretraining`, `#AI safety transparency`, `#OpenAI`, `#model evaluation`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [上海地铁票价 21 年来首次调整，起乘价 3 元](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

据新华社报道，上海公布时隔 21 年的首次轨道交通票价调整，起乘价 3 元、覆盖 0 至 4 公里，此后按 4、4、4、7、7、10、10 公里逐段加 1 元，50 公里以上每 15 公里加 1 元。新票价与计次票、同一支付渠道当月累计满 90 元享 9 折等优惠均自 12 月 1 日起实施，190 元至 390 元四档计次票于 11 月 26 日开售。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海地铁现行票价机制已沿用 21 年；调整前举行的票价听证会上，多数参与者支持起乘价维持 3 元的方案。

**「影响」** 对上海每天通勤的居民来说，3 元起步并按里程加价会直接改变其交通支出，而计次票和当月同一支付渠道累计满 90 元享 9 折，主要用于减轻高频出行人群的负担。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260908A05NH700">news.qq.com/rain/a/20260908A05NH700</a></li>

</ul>
</details>

**标签**: `#Shanghai Metro`, `#public transport fares`, `#fare policy`, `#commuters`, `#cost of living`

---