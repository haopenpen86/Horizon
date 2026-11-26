---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 42 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [FCC 批准 SpaceX 最多部署 100 万颗 Starmind 卫星](#item-tech-news-1) ⭐️ 8.0/10
2. [英伟达据报暂停向东南亚四国发运 AI 服务器](#item-tech-news-2) ⭐️ 8.0/10
3. [AMD 专用 llama.cpp 分支瞄准本地推理优化](#item-tech-news-3) ⭐️ 7.0/10
4. [Minipg：将 PostgreSQL 打包为单个可执行文件](#item-tech-news-4) ⭐️ 7.0/10
5. [Google 推动 AI 代理接入 Workspace MCP，Gmail 集成无法发信](#item-tech-news-5) ⭐️ 7.0/10
6. [SemiAnalysis 发布 GDPx 基准，Opus 5.5 首日仅得 12%](#item-tech-news-6) ⭐️ 7.0/10
7. [华为拟公布数据引脚密度翻倍的 HBM 芯片](#item-tech-news-7) ⭐️ 7.0/10
8. [三部门印发新一代通信网方案：2030 年建成并适时开展 6G 建设](#item-tech-news-8) ⭐️ 7.0/10
9. [Neuralink 获 FDA 许可启动渐冻症关键脑机接口试验](#item-tech-news-9) ⭐️ 7.0/10
10. [荷兰反对美国 MATCH 法案限制 ASML 对华销售](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [半导体出口额首次超过石油和天然气](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [FCC 批准 SpaceX 最多部署 100 万颗 Starmind 卫星](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 8.0/10

美国联邦通信委员会（FCC）批准 SpaceX 最多部署 100 万颗卫星，用于构建 Starmind 在轨数据处理网络；FCC 称这是美国首次批准太空数据中心星座。这些卫星将运行在 500 至 1002 公里高度。授权要求首颗卫星不晚于 2033 年投入运行、整个星座在 2040 年前全部运行，并附有通信备份、定期进展报告和轨道碎片减缓方案等条件；FCC 还驳回了亚马逊、Viasat 和美国天文学会的反对意见。

telegram · zaihuapd · 11月26日 04:45

**「背景」** 轨道数据中心星座指在卫星上直接处理计算任务、再把结果传回地面的网络，而不是仅让卫星承担通信中继。此类星座在美国需取得 FCC 的频谱与运营授权，且授权会附带部署期限和轨道碎片减缓要求；这些条件决定项目能否从纸面方案进入实际组网。

**「对开发者的实际影响」** 对希望使用轨道算力的开发者而言，这项批准提供的是受里程碑约束的监管路径，而非可立即依赖的服务。TechCrunch 指出，SpaceX 仍需大幅降低卫星制造与发射成本，并解决太空中的处理器散热问题；同时，首颗卫星须在 2033 年前投入运行、整个星座须在 2040 年前完成，相关商业部署因此仍取决于这些条件能否兑现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/space/spacex-million-satellites-data-centers-fcc">SpaceX gets FCC approval for one million space data center ...</a></li>
<li><a href="https://www.satellitetoday.com/connectivity/2026/11/25/fcc-approves-spacexs-1-million-satellite-orbital-data-center-constellation/">FCC Approves SpaceX ’s 1 - Million Satellite Orbital Data Center ...</a></li>
<li><a href="https://techcrunch.com/2026/11/25/fcc-approves-spacex-plan-to-put-ai-data-centers-in-space/">FCC approves SpaceX plan to put AI data centers in space</a></li>

</ul>
</details>

**标签**: `#space computing`, `#orbital data centers`, `#FCC`, `#SpaceX`, `#satellite constellations`

---

<a id="item-tech-news-2"></a>
### [英伟达据报暂停向东南亚四国发运 AI 服务器](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

英伟达据报已要求主要制造伙伴暂停向马来西亚、新加坡、泰国和印度尼西亚发运 AI 服务器，戴尔、美超微等将英伟达芯片组装成整机的厂商已通知四国买家相关订单不能出厂。三名知情人士称，此次冻结与美国商务部上周出台的新一轮出口管制有关；新规要求区域云服务商在 90 天内取得出口许可，并核实客户不含受限的中国实体。这四国此前是中国 AI 公司获取英伟达最先进处理器的中转地，但冻结是否仅为临时措施尚不清楚。

telegram · zaihuapd · 11月26日 07:38

**「背景」** 美国此前已禁止英伟达最先进处理器直接出口中国大陆，因此马来西亚、新加坡、泰国和印度尼西亚成为相关芯片流向中国 AI 公司的中转路径。作为收紧措施，美国商务部上周发布新规，要求区域云服务商在 90 天内取得出口许可，并核实客户中不包含受限的中国实体。

**「交付与合规影响」** 对马来西亚、新加坡、泰国和印度尼西亚的服务器买家和区域云服务商，直接后果是戴尔、美超微等厂商已通知相关整机订单无法出厂，交付时间取决于冻结是否解除；同时新规要求现有数据中心运营商在 90 天内取得出口许可，并核实客户不包含受限中国实体，否则不能继续提供相关算力服务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese ... | TechCrunch</a></li>
<li><a href="https://hwbusters.com/news/ai-chip-export-controls-now-reach-rented-gpus-and-malaysia-and-singapore-need-a-license/">AI Chip Export Controls Now Reach Rented GPUs, and Malaysia and...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI servers`, `#export controls`, `#semiconductor supply chain`, `#US-China tech`

---

<a id="item-tech-news-3"></a>
### [AMD 专用 llama.cpp 分支瞄准本地推理优化](https://devnull.land/amd-specific-llama-cpp) ⭐️ 7.0/10

一个面向 AMD GPU 的 llama.cpp 分支出现在 Hacker News 讨论中，目标是改善 AMD 显卡上的本地大模型推理。现有材料没有给出该分支的名称、版本、实测加速比或明确支持的显卡与 ROCm 组合，因此它目前更像社区优化项目，而非已经独立验证的性能承诺。讨论主要围绕旧款高带宽 AMD 卡，以及为缺少 tensor core、原生 bf16 等特性的硬件优化 llama.cpp。

hackernews · julianlam · 11月26日 17:11 · [社区讨论](https://news.ycombinator.com/item?id=50657265)

**「背景」** llama.cpp 是广泛使用的开源本地 LLM 推理项目，围绕它已出现按硬件架构定制的分支。此次报道的 AMD 专用分支以 llama-cpp-rdna-boosts 的形式维护：它并非完全独立分叉，而是把一组最小改动持续重新应用到固定版本的 llama.cpp 提交上；类似地，社区还有针对 gfx906（MI50/MI60/Vega7）等老卡的专用分支，例如 iacopPBK/llama.cpp-gfx906。

**「影响与采用注意」** 对仍在使用 gfx906 等旧款高带宽 AMD 数据中心卡的用户，这个分支的意义在于继续利用大显存和 HBM 带宽运行本地模型；实际采用前应核对仓库对具体卡型、ROCm 版本和量化格式的支持，因为这类卡缺少 tensor core 和原生 bf16，不能假定其配置与主线 llama.cpp 完全通用。

**「社区讨论」** 评论者指出，2018 年前后的 gfx906 数据中心卡能以约 200 美元提供 32GB HBM2 和约 1TB/s 带宽，但缺少 tensor core 和原生 bf16，因此出现了专门针对 llama.cpp 的优化生态；另有 MI100 用户称，把部分 Nvidia kernel 移植到 ROCm 后获得明显加速，并用原实现做了数值校验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD - specific fork of llama . cpp | devnull . land</a></li>
<li><a href="https://github.com/CypherpunkSamurai/awesome-llama-cpp">GitHub - CypherpunkSamurai/awesome- llama - cpp : An Index of most...</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#AMD`, `#GPU optimization`, `#local LLM inference`, `#open source`

---

<a id="item-tech-news-4"></a>
### [Minipg：将 PostgreSQL 打包为单个可执行文件](https://progrium.github.io/minipg/) ⭐️ 7.0/10

Minipg 项目将 PostgreSQL 打包成一个可执行文件，面向希望以简单 CLI 数据库方式使用 PostgreSQL 的开发者。作者 progrium 在讨论中强调，这不是 PGlite 那类进程内嵌入库，而更接近 SQLite 作为可直接运行的命令行 SQL 数据库的用法；PGlite 仅支持单连接模式，是他另做方案的原因之一。评论者称其复用 PostgreSQL 的 Alpine 镜像但无需 Docker，并依赖较新的嵌入式 hypervisor h9；这些实现细节来自社区讨论，未在给定材料中独立验证。所给材料未说明其 PostgreSQL 版本、支持平台或性能数据。

hackernews · rguiscard · 11月26日 03:00 · [社区讨论](https://news.ycombinator.com/item?id=50650892)

**「背景」** PostgreSQL 通常是客户端/服务器数据库：应用连接一个独立启动、需要配置认证与数据目录的服务进程。minipg 试图把这一层收进单个可执行文件，并用 \`.pgdb\` 目录同时保存数据、配置、凭据和 PostgreSQL 版本；据项目页面，运行 \`minipg app.pgdb\` 会直接打开 psql shell。

**「影响」** 对希望在小型自托管应用中避开 Docker 的开发者，Minipg 提供了直接运行 PostgreSQL 的选项；但它仍是 PostgreSQL 服务器而非嵌入式库，采用前应确认多连接与事务并发行为、平台支持，以及能否满足原本由 PGlite 或 embedded-postgres 覆盖的场景。

**「社区讨论」** t3ntxcles 认为“无内核、按连接 fork 的 PostgreSQL”这一实现很有趣，但质疑 Minipg 相对 PGlite 和 embedded-postgres 的额外价值；Ciantic 则认为它对小型自托管应用有用，同时提醒真实服务器未必适合这类应用。作者 progrium 回应说 Minipg 更接近 SQLite 作为简单 CLI 数据库的用法，并称 PGlite 只支持单连接模式是动机之一；Ciantic 还报告用 Podman 跑官方 PostgreSQL 镜像做单元测试时启动约需 800 毫秒。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://progrium.github.io/minipg/">minipg : PostgreSQL as a single executable</a></li>

</ul>
</details>

**标签**: `#PostgreSQL`, `#databases`, `#single executable`, `#self-hosting`, `#developer tooling`

---

<a id="item-tech-news-5"></a>
### [Google 推动 AI 代理接入 Workspace MCP，Gmail 集成无法发信](https://techstackups.com/articles/google-workspace-ai-agents-mcp/) ⭐️ 7.0/10

据 TechStackUps 报道，Google 正推动 AI 代理通过其 Workspace MCP 服务器访问 Gmail、Docs 和 Drive 等应用，但 Gmail 集成不能发送邮件。报道还称相关访问仅面向合作伙伴，这引发外界质疑该限制究竟出于安全考虑还是商业控制。由于原文未提供具体版本、开放时间或技术文档，目前能确认的只是报道层面的说法。

hackernews · ritzaco · 11月26日 09:44 · [社区讨论](https://news.ycombinator.com/item?id=50653477)

**「背景：Gmail MCP 服务器与 OAuth 授权」** MCP（Model Context Protocol）是让 AI 客户端以统一方式调用外部工具和数据的接口层；按 Google 开发者文档，使用 Gmail MCP 服务器需要先建立 Google Cloud 项目、配置面向 AI agent 的 OAuth 2.0 客户端，再让 AI 应用连接。该文档把 Gmail MCP 服务器向 AI agent 提供的能力描述为读取类操作——搜索邮件、获取会话线程、列出标签——本次报道所称的“不能发信”正落在这类已公开的读写范围之外。与此同时，社区也维护着第三方的 Google Workspace MCP 服务器，把 Gmail、Calendar、Drive、Docs、Sheets 等合并到同一个服务器中，供 agent 跨多个账号访问。

**「影响」** 对需要让智能体发送邮件的开发者来说，报道中的 Workspace Gmail MCP 服务器无法完成发送，只能退回 Gmail API/SMTP 授权，或让智能体操作浏览器；后一种方式更易出错、资源开销也更大。报道同时称发送类能力仅向合作伙伴开放，这意味着第三方智能体在邮件工作流上需要额外设计权限与回退方案，而不能只依赖 Workspace MCP。MCP 规范本身已提供 elicitation 机制，可在工具调用前要求用户确认（tool-3-2），因此把发送能力限定给合作伙伴并非实现人工确认的唯一途径。

**「社区讨论」** 评论中，perdy 认为 MCP 已有 elicitation 机制可在工具调用前要求用户确认，因此把发送邮件功能限定为合作伙伴更像是商业决策而非安全需要；Schnitz 则预测用户会改用浏览器自动化绕过限制，反而更混乱、更耗资源。另有评论提到 API 用量计费和条款限制可能成为类似集成的实际约束。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server">Configure the Gmail MCP server | Google for Developers</a></li>
<li><a href="https://github.com/aaronsb/google-workspace-mcp">GitHub - aaronsb/ google - workspace - mcp : A Model Context Protocol...</a></li>
<li><a href="https://modelcontextprotocol.io/specification/draft/client/elicitation">Elicitation - Model Context Protocol</a></li>

</ul>
</details>

**标签**: `#MCP`, `#Google Workspace`, `#AI agents`, `#API access`, `#email`

---

<a id="item-tech-news-6"></a>
### [SemiAnalysis 发布 GDPx 基准，Opus 5.5 首日仅得 12%](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis 于 11 月 1 日发布 GDPx 基准，用于衡量前沿模型在“最具价值领域”的表现：共 206 个任务，由 14 家专业数据合作方制作，覆盖芯片设计、网络安全、生物、金融、法律、量化交易、递归自我改进、硬件设计、材料科学、对齐与软件工程 11 个领域，并明确排除政府、房地产等按 GDP 占比或 O\*NET 分类选取的行业。该文批评 GDPVal、Agent&\#x27;s Last Exam 等综合基准按经济总量选域的思路，主张 AI 影响在 economy 中分布极不均衡，追踪前沿进展应聚焦高影响领域。其最突出特征是难度：发布当日得分最高的模型 Opus 5.5 仅拿到 12%，远低于多数新基准首秀即超过 50% 的水平。自 GDPx 上线以来，Anthropic 与 OpenAI 均发布了新前沿模型，Google 以 Gemini 4 系列回归，阿里和 Moonshot 也有值得注意的发布；SemiAnalysis 同时指出 Fable 5.2 与 GPT-6.2 Astra 因安全分类器在网络安全、生物、对齐三个领域被触发而压低了总分，若剔除这三域并对默认二元评分的法律、金融改用部分评分，榜单排序会发生变化。

rss · Semianalysis · 11月26日 00:05

**「背景」** GDPVal、Agent&\#x27;s Last Exam 等试图覆盖多个领域的 agentic 基准，是按各行业占 GDP 的比重或美国劳工部 O\*NET 职业分类来挑选任务领域的；SemiAnalysis 认为这种选法偏离了 AI 当前及未来实际产生影响的地方，因此另建了 GDPx。推动新基准的另一原因是现有评测已经饱和：像 Terminal Bench 4.0 这类基准上模型得分已接近上限，难以再区分新发布的模型。

**「实际影响」** 对依赖公开榜单做模型选型的团队而言，GDPx 的低分头部空间意在让其能继续区分后续模型发布，而非像已饱和的 Terminal Bench 4.0 那样失去分辨力；但同一篇分析也说明，安全分类器会让部分模型的 GDPx 分数系统性偏低，因此直接比较原始总分可能误判模型在高影响领域的真实能力，需同时查看剔除网络安全、生物、对齐三域并使用部分评分后的版本。

**标签**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#agentic AI`, `#AI economics`

---

<a id="item-tech-news-7"></a>
### [华为拟公布数据引脚密度翻倍的 HBM 芯片](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

据彭博社报道，华为计划于明年 2 月在旧金山举行的一场会议上发表研究论文，介绍一款新型高带宽内存（HBM）芯片。论文标题显示，该芯片的数据引脚密度是三星电子和 SK 海力士现有量产产品的两倍，理论上可显著提升内存带宽。华为同时推动该部件在中国本土生产；目前 HBM 受美国制裁限制。上述信息来自论文发表计划及厂商主张，尚无量产时间、良率或独立测试数据。

telegram · zaihuapd · 11月26日 05:30

**「背景」** 高带宽内存（HBM）是一种将多颗 DRAM 3D 堆叠、通过超宽接口提供高带宽的内存形式，最初由三星、AMD 和 SK 海力士开发。此次引发关注的是华为计划于明年 2 月在旧金山会议上发表的论文标题；据 wccftech 引述彭博社报道，该论文已列入 ISSCC 的预置议程，标题称其数据引脚密度达到三星和 SK 海力士量产产品的两倍。

**「影响」** 对中国的 AI 芯片厂商而言，这一设计若能在本土制造，可能提供更高带宽的国产 HBM 选择；但华为目前只是计划发表论文，量产时间、良率和平台兼容性均未披露，不能视为已可采购的产品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/High_Bandwidth_Memory">High Bandwidth Memory - Wikipedia</a></li>
<li><a href="https://wccftech.com/huawei-poised-to-grow-chinas-ai-chip-market-next-generation-hbm-design-double-data-pin-density/">Huawei Poised To Grow China’s AI Chip Market With...</a></li>

</ul>
</details>

**标签**: `#Huawei`, `#HBM`, `#semiconductors`, `#AI hardware`, `#US sanctions`

---

<a id="item-tech-news-8"></a>
### [三部门印发新一代通信网方案：2030 年建成并适时开展 6G 建设](https://www.news.cn/politics/20261126/9fe827a2d98741acb60f62d36ba89cf7/c.html) ⭐️ 7.0/10

经国务院同意，工业和信息化部、国家网信办、国家发展改革委于 11 月 26 日发布《新一代通信网建设实施方案》，提出到 2030 年建成覆盖完善、性能领先的新一代通信网。方案明确积极推进 5G-A 网络规模覆盖，并“适时”开展 6G 网络建设，同时要求低轨卫星互联网系统基本建成，工业互联网、车联网等融合网络实现规模化发展。文件还提出加快 6G、卫星互联网、算网融合等标准研制，并推动脑机接口、具身智能、智能网联汽车与新一代通信网融合发展。上述内容为阶段性规划目标，尚非已经建成的网络能力。

telegram · zaihuapd · 11月26日 06:30

**「背景」** 5G-A 是 5G 向 6G 演进的增强阶段，6G 则仍处于标准预研和早期技术验证阶段，两者通常按“先规模部署 5G-A、再视条件启动 6G 建设”的节奏衔接。方案把地面移动网络、低轨卫星互联网以及工业互联网、车联网等融合网络纳入同一“新一代通信网”框架，因此其覆盖对象不止是公众移动通信。

**「对产业的影响」** 对通信运营商和设备商而言，方案要求在 2030 年前推进 5G-A 规模覆盖，并同步开展 6G、卫星互联网、算网融合标准研制；6G 网络建设被表述为“适时开展”，并未给出商用时间表。涉及低轨卫星互联网、工业互联网和车联网的企业因此面临明确的 2030 年阶段性目标，需要按这一时间点评估网络部署和标准兼容安排。

**标签**: `#6G`, `#telecom policy`, `#5G-Advanced`, `#satellite internet`, `#China tech policy`

---

<a id="item-tech-news-9"></a>
### [Neuralink 获 FDA 许可启动渐冻症关键脑机接口试验](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 7.0/10

Neuralink 宣布已获 FDA 临床试验许可，将在美国启动名为“LINK”的植入式脑机接口关键临床试验，面向渐冻症（ALS）患者招募，目标是把大脑信号直接转化为计算机控制指令。公司称这是美国首个获批的此类关键试验；此前其早期研究已在全球为超过 30 名瘫痪患者植入设备。此次许可是进入关键临床阶段，并非器械上市批准，试验数据将作为未来申请上市许可的核心依据。

telegram · zaihuapd · 11月26日 07:15

**「背景」** 脑机接口的关键临床试验属于监管审批前的后期研究阶段，其数据将作为申请医疗器械上市许可的核心依据。Neuralink 此前通过早期研究已在全球为超过 30 名瘫痪患者植入设备，此次则将受试人群转向渐冻症患者。

**「影响」** 若 LINK 的入组和终点按计划推进，Neuralink 可将该试验数据用于上市申请；但在关键试验结果和监管审评完成前，该设备仍未获批，患者只能通过研究途径获得植入。

**标签**: `#Neuralink`, `#brain-computer interface`, `#FDA`, `#clinical trials`, `#ALS`

---

<a id="item-tech-news-10"></a>
### [荷兰反对美国 MATCH 法案限制 ASML 对华销售](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 7.0/10

荷兰外贸与发展合作大臣 Sjoerd Sjoerdsma 11 月 26 日在议会表示，荷兰不会接受美国通过 MATCH Act 进一步限制 ASML 对华销售，并反对该法案的域外管辖效力。荷兰正与欧盟委员会协调，并联合德国、法国游说，争取把该法案从美国年度国防政策法案中剔除。MATCH Act 由美国两党共同提出，要求荷兰、日本等盟友实施更严格的对华出口管制，否则美方将单方面限制其半导体设备；中国约占 ASML 今年销售额的 20%。报道指出，外界预计美国国会 12 月中旬表决，通过可能性很大。

telegram · zaihuapd · 11月26日 14:56

**「背景」** 美国和荷兰此前已禁止 ASML 向中国出口最先进的 EUV 光刻设备。据相关报道，MATCH Act 将把限制范围扩大到较旧的 DUV 浸没式设备，收紧转售管控，并要求荷兰、日本在 150 天内对齐美国的出口管制。

**「影响」** 如果 MATCH Act 相关条款被保留并生效，ASML 等荷兰设备商对华销售将面临更直接的美国单边限制风险；中国业务约占 ASML 今年销售额的 20%，荷兰正试图在国会表决前联合欧盟及德国、法国移除这一域外条款。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/erudite-risk_asiarisk-geoeconomicconfrontation-china-activity-7445742293120368640-qSkK">US lawmakers introduce MATCH Act to restrict AI chip exports to China</a></li>
<li><a href="https://www.fool.com/investing/2026/04/24/the-match-act-could-blow-a-hole-in-asmls-revenue-h/">The MATCH Act Could Blow a Hole in ASML &#x27;s Revenue. Here&#x27;s What...</a></li>
<li><a href="https://overcentral.com/en/netherlands-opposes-match-act-asml-china/">Netherlands Opposes US Bill Restricting ASML Chip Sales to China</a></li>

</ul>
</details>

**标签**: `#semiconductors`, `#export controls`, `#ASML`, `#Netherlands`, `#US-China tech policy`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [半导体出口额首次超过石油和天然气](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

德意志银行基于国际贸易中心数据的分析显示，按过去四个季度的出口总额合计计算，2026 年第一季度半导体出口额首次超过石油和天然气，分别约为 1.61 万亿美元和 1.53 万亿美元。

rss · CNBC Finance · 11月26日 17:52

**「背景」** 人工智能数据中心建设推升了芯片需求；伊朗战争后霍尔木兹海峡石油运输受扰，又帮助第二季度两者差距扩大。

**标签**: `#semiconductors`, `#global trade`, `#AI investment`, `#market volatility`, `#macroeconomics`

---