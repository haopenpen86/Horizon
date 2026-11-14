---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 32 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Lovable 应用因 RLS 不足暴露护照信息与逾 20 万条私信](#item-tech-news-1) ⭐️ 8.0/10
2. [星舰第 15 次试飞完成飞船塔捕，助推器未回收](#item-tech-news-2) ⭐️ 8.0/10
3. [EFF 称科技公司再次试图改写隐私概念](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI 解散独立机器人团队，称通用模型已可直接操控机器人](#item-tech-news-4) ⭐️ 7.0/10
5. [意大利因 Facebook 相册读取违规罚 Meta 8.05 亿欧元](#item-tech-news-5) ⭐️ 7.0/10

**科技博客**
1. [大型科技公司中如何寻找意义](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [卢特尼克因英伟达出口审查面临质询，其家族公司持股与业务关系受关注](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Lovable 应用因 RLS 不足暴露护照信息与逾 20 万条私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

Crissy Field 的安全研究发现，一批用 Lovable 构建的应用因 Row-Level Security（RLS）配置不足，暴露了护照信息和超过 20 万条私信。受影响的是这些应用的终端用户，以及需要为数据库权限负责的开发者。Lovable 安全负责人 Igor 在讨论中称，平台会在每次发布前自动扫描应用，并提供对所有用户免费的深度 SAST 扫描和修复流程；这些是厂商说法，尚无独立验证。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景」** 行级安全（RLS）是 PostgreSQL 和 Supabase 中按用户限制可读写数据行的机制；策略缺失或过于宽松时，客户端请求可能读到不属于当前用户的记录。Lovable 让用户通过提示生成应用，而此次争议集中在底层 Supabase 的默认权限设置是否让这类错误更容易发生。

**「影响」** 对受影响应用的用户来说，护照信息和私信既然已暴露，就应按敏感数据泄露处理；对开发者来说，平台提供自动扫描或 SAST 并不证明每张表的 RLS 策略已经正确，发布前仍需核对客户端可访问的接口和行级权限。

**「社区讨论」** Lovable 安全负责人 Igor 表示根因是应用 RLS 不足，并称平台已提供发布前自动扫描、免费 SAST 和修复流程。评论者则把部分责任指向 Supabase 的默认权限：一人引用 Supabase 讨论称问题虽被宣称在 10 月 30 日修复，但现有项目仍可能沿用旧默认值；另一人主张数据库应默认拒绝，并配合最小权限 API 和自动化鉴权测试。

**标签**: `#security`, `#row-level-security`, `#supabase`, `#lovable`, `#data-exposure`

---

<a id="item-tech-news-2"></a>
### [星舰第 15 次试飞完成飞船塔捕，助推器未回收](https://x.com/i/broadcasts/2brajgZlOKRMka) ⭐️ 8.0/10

据提交信息，SpaceX 的星舰第 15 次试飞以发射塔机械臂接住返回的飞船收尾。此次试飞于 11 月 13 日从得州进行，飞船成功入轨并部署全部 26 颗 Starlink V3 卫星，其中 3 颗带摄像头用于检查隔热瓦；它按计划在轨约 22 小时、绕地球约 14 圈后返回 Starbase。助推器则因技术问题中止返场，改在墨西哥湾受控溅落后爆炸，具体原因未公布，原定的助推器与飞船“双塔捕”未能实现。

hackernews · ls612 · 11月14日 21:22 · [社区讨论](https://news.ycombinator.com/item?id=50500963)

**「背景」** 星舰的“塔捕”不是让飞行器自行着陆，而是让助推器或飞船垂直降回发射塔旁，由塔上的机械臂夹住承接点。Flight 15 是 SpaceX 首次同时尝试回收助推器和飞船：11 月 13 日发射后助推器未能返场，飞船入轨并于 11 月 14 日返回得州发射塔被捕获。

**「后续影响」** 对 SpaceX 而言，这次飞行的直接后果是：飞船在入轨并部署 26 颗 Starlink V3 卫星后返回，被发射塔机械臂夹住，说明载荷入轨与飞船回收可以压在同一次任务里完成；但助推器中止返场、溅落爆炸，原定的“双塔捕”和整箭复用仍未得到验证。因此，星舰后续发射节奏和 Starlink V3 的部署速度，取决于助推器回收故障的排查结果，以及这艘回收飞船隔热瓦在飞行后的实际状态，而不是单次捕获成功本身。在两级都稳定复用之前，投资分析中提出的每次 2000 万至 3000 万美元边际成本目标仍只是目标值，而非实测成本。

**「社区讨论」** 评论普遍把这次飞船回收视为可复用性的关键一步，有人称若隔热瓦经受住再入，下一步就是双塔捕和重复使用同一批飞船，从而显著降低入轨成本。也有评论认为助推器这次只差“几吨推进剂和氧化剂”就可能同时被接住，并提醒最终入轨质量比仍不清楚，完全可复用比部分可复用更有价值。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/14/spacex-plans-to-try-first-ever-catch-of-starship-rocket-from-orbit.html">SpaceX catches upper stage of Starship rocket in historic first</a></li>
<li><a href="https://www.floridatoday.com/story/tech/science/space/spacex/2026/11/13/spacexs-starship-flight-15-launches-from-texas-reaches-orbit-but-misses-booster-catch/92758185007/">SpaceX&#x27;s Starship Flight 15 launches from Texas, misses ...</a></li>
<li><a href="https://www.usatoday.com/story/tech/space/2026/11/14/spacex-flight-15-catches-starship-makes-history/92785462007/">SpaceX catches Starship for first time at Texas launch tower</a></li>
<li><a href="https://spaceodysseyhub.com/articles/starship-economics-investor-analysis-2026">Starship Economics: An Investor&#x27;s Field Manual (2026)</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#reusable launch`, `#spaceflight hardware`, `#engineering milestone`

---

<a id="item-tech-news-3"></a>
### [EFF 称科技公司再次试图改写隐私概念](https://www.eff.org/deeplinks/2026/11/tech-companies-are-trying-shift-entire-concept-privacy-again) ⭐️ 7.0/10

电子前哨基金会（EFF）于 11 月 14 日发布评论文章，讨论科技公司再次试图重塑“隐私”概念的努力。可用材料没有提供文章点名的公司、具体技术机制或已生效的政策变化，因此当前可核实的内容主要是政策评论立场，而不是已落地的新隐私规则或产品变更。

hackernews · gslin · 11月14日 12:45 · [社区讨论](https://news.ycombinator.com/item?id=50496602)

**「背景」** 这篇 EFF 评论的出发点是隐私边界正从“个人选择是否披露自己的信息”转向“旁观者被动暴露”：智能眼镜和可穿戴设备能持续录音、转写并用 AI 描述周围人的活动，使未使用设备的人也难以避开记录。文章以 Meta 和 Google 的智能眼镜、Apple Watch 的 Audio Intelligence 转写功能以及 Amazon Bee 等为例，说明争议核心已从用户自身的数据控制扩展到公共与半公共空间中被记录者的同意问题。

**「对参会者与组织的影响」** 对日常参会者来说，直接的后果是“不被记录”需要自己主动争取：评论描述的常态是每场会议都有可见或不可见的 AI 记录者，退出并不容易，可行的做法是在会前明确要求关闭记录。对允许使用这类工具的组织而言，部署前需要核查三点：录音的同意与合法性要求、数据存储时长，以及会议内容是否被用于模型训练——这些正是隐私风险集中的环节。

**「社区讨论」** Hacker News 上最具体的经验来自 toddmorey：几乎所有职业会议——包括经理与同事的一对一——都被可见或不可见的 AI 参会者录音并上传，他询问能否把“本次会议不需要转录，请关闭 AI 笔记工具”变成常规。其他评论者则引用《世界人权宣言》第 12 条反对数据融合，建议用公开身份、一次性身份和物理隔离等个人防御手段，并把当前录音产品与 Google Glass 遭遇的反弹相比较；这些是个人观点和争论，不是对 EFF 文章的独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.my/items/46520/tech-companies-are-trying-to-shift-the-concept-of-privacy-again">Tech Companies Are Trying to Shift the Concept of Privacy (Again)</a></li>
<li><a href="https://briefly.co/anchor/Privacy_technologies/story/tech-companies-are-trying-to-shift-the-entire-concept-of-privacy-again">Key takeaways: Tech Companies Are Trying to Shift the Entire ...</a></li>
<li><a href="https://smartkeys.org/ai-meeting-notetaker-policy/">AI Note-Takers in Meetings: Consent, Privacy and Etiquette Rules</a></li>
<li><a href="https://fireflies.ai/blog/are-ai-notetakers-safe">Are AI Notetakers Safe? Privacy Risks, Consent Laws, and What ...</a></li>

</ul>
</details>

**标签**: `#privacy`, `#AI notetakers`, `#surveillance`, `#data fusion`, `#digital rights`

---

<a id="item-tech-news-4"></a>
### [OpenAI 解散独立机器人团队，称通用模型已可直接操控机器人](https://fortune.com/2026/11/13/openai-disbands-robotics-team-as-its-general-models-start-running-robots/) ⭐️ 7.0/10

据 Fortune 报道，OpenAI 已解散其独立机器人团队，并将相关研究员重新分配到更通用的研究团队。公司表示机器人仍是其长期愿景的核心，并称此次调整是因为 GPT-6 Astra 等通用前沿模型已经能够直接操控机器人执行任务，无需再保留专门的机器人团队。报道还提到，OpenAI 在 2024 年重建机器人团队并与 Figure 合作，但该合作已于 2025 年 2 月终止；公司目前仍在自研人形机器人，CEO 提出的目标是 2027 年首次公开展示。上述内容来自一篇简短的二手转述，其中关于 GPT-6 Astra 能力和 2027 年展示计划的说法均未获得独立确认，也未说明重组涉及的具体人数或岗位安排。

telegram · zaihuapd · 11月14日 04:00

**「背景」** OpenAI 的机器人团队此前已多次调整：早期团队于 2020 年解散，2024 年重建并与 Figure 合作，但该合作于 2025 年 2 月终止。此次解散后，相关研究人员被划入 Mark Chen 和 Greg Brockman 负责的更通用研究团队，机器人工作仍在继续。

**「影响」** 对于被重新分配的研究员来说，直接后果是机器人方向的工作转入通用模型团队，而不是继续以独立团队的形式推进，这可能导致对外合作或专门招聘的接口发生变化；不过，由于来源没有披露人员规模、汇报关系和是否涉及裁员，目前还无法判断实际影响范围。关注 OpenAI 具身智能进展的开发者与潜在合作方，短期内更可能通过通用模型的能力更新，而不是机器人团队的专门发布，来获取相关信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://theroboticsmedia.com/article/openai-disbands-robotics-team-gpt-6-astra">OpenAI Disbands Robotics Team, Bets on GPT-6 Astra Instead</a></li>
<li><a href="https://madrobot.blog/2026/11/13/openai-disbands-robotics-team-gpt-6-astra/">OpenAI reorganises its robotics team as GPT-6 Astra runs robots</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#robotics`, `#general-purpose AI`, `#humanoid robots`, `#organizational change`

---

<a id="item-tech-news-5"></a>
### [意大利因 Facebook 相册读取违规罚 Meta 8.05 亿欧元](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10321080) ⭐️ 7.0/10

意大利隐私监管机构 Garante Privacy 对 Meta 罚款 8.05 亿欧元，原因是 Facebook 的 Android 应用在未取得具体同意的情况下读取了约 2000 万意大利用户的相册照片、视频和元数据。涉事功能是 2023 年上线的相册推荐，默认开启，其授权提示被认定过于笼统。Meta 须在 60 天内将其改为默认关闭并单独征得用户同意，否则不得向未有效授权的用户启用该功能。

telegram · zaihuapd · 11月14日 14:37

**「背景」** 涉事功能是 Facebook 自 2023 年起提供的相册推荐工具，会从用户手机相册中挑选照片和视频，供用户发布到社交平台。此次争议因此集中在应用对本地相册的访问和推荐机制上，而不是用户主动上传的内容。

**「整改影响」** Meta 若未在 60 天内完成默认关闭和单独同意的调整，相册推荐功能将不得对未有效授权的意大利用户启用，这会直接影响该功能在当地的可用性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/articles/italy-fines-meta-805-million-161834604.html?fr=sycsrp_catchall">Italy fines Meta €805 million over Android app&#x27;s photo access</a></li>

</ul>
</details>

**标签**: `#隐私监管`, `#Meta`, `#Android 权限`, `#用户同意`, `#科技行业合规`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [大型科技公司中如何寻找意义](https://seangoedecke.com/how-to-find-meaning-in-large-tech-companies/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月14日 00:00

**「背景」** 许多工程师讨厌在大型科技公司工作，通常的解释是组织失能阻碍了他们写代码、交付产品。但 Sean Goedecke 认为这不足以说明问题：如果真的只是这样，这些人本该有兴趣理解失能、学会绕开它，而现实中很多人连思考它都觉得难受。

**「方案」** 作者认为，工程师对“整洁”有一种近乎本能的强迫，组织混乱就像脏房间一样令他们生理性排斥。而在大公司里，人们被迫对 OKR、内部培训、人为鼓动的士气等难以认真对待的事表现出热情，这是一种“角色扮演”；长期如此，会让人觉得“重要”本身也是幻觉。他借用哲学系常被问到的存在焦虑问题给出解法：少想工作，回到孩子、散步、读书这些真正重要的事上。不过他指出，大公司仍有一处实在的意义来源：你参与的软件被数百万人使用，把 Teams 改进一点点，就是改善数百万人的生活；每修一个 bug、加一个功能，都在为使用者累计节省数月乃至数年的时间，即便软件整体在缓慢变差，拖慢这个过程本身也有价值。代价是必须容忍混乱，并有足够丰富的个人生活，才能对职场政治保持健康的疏离。

**「启示」** 在作者看来，意义不取决于组织是否整洁，而取决于是否把规模当作杠杆：只要你能忍受混乱、并让工作与个人生活保持距离，改进被数百万人使用的软件本身就是一种实在而值得的成就。

**标签**: `#large tech companies`, `#workplace meaning`, `#organizational dysfunction`, `#software engineering careers`, `#career essay`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克因英伟达出口审查面临质询，其家族公司持股与业务关系受关注](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

据 CNBC 11 月 13 日报道，美国商务部长霍华德·卢特尼克因抵制对涉嫌向中国走私英伟达芯片的企业采取打击行动而面临质询；他此前领导、现由其子经营的坎托·菲茨杰拉德在 2025 年 9 月至 2026 年 3 月间将申报的英伟达持股数量减少约 49%，至 178 万股。坎托称这些申报持股与客户互换交易有关、独立持仓并不重要；报道称相关关系引发利益冲突质疑，但无证据显示卢特尼克分享了非公开信息。

rss · CNBC Finance · 11月13日 23:42

**「背景」** 黄仁勋因与一名被怀疑为中国间谍的女性有恋情而辞去英伟达 CEO 职务，这一事件令美中芯片出口管制受到关注；他和美国商务部长霍华德·卢特尼克均被传唤，将于下月到参议院委员会作证。卢特尼克主管出口管制，Axios 报道称，尽管特朗普已授权相关管制，他仍多次抵制对新加坡 Megaspeed 等涉嫌向中国转运英伟达芯片的公司实施限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/live/2026/11/12/business/nvidia-jensen-huang-resigns">Nvidia Updates: Huang ’s Resignation Reverberates Through...</a></li>
<li><a href="https://www.theguardian.com/technology/live/2026/nov/13/nvidia-jensen-huang-to-testify-before-congress-live-latest-updates">Calls for crackdown on China chip exports – as it happened | Nvidia</a></li>
<li><a href="https://www.axios.com/2026/11/11/trump-lutnick-nvidia-china-chip-export-controls">Trump backed Nvidia chip controls aimed at China 3 times as...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#conflict of interest`

---