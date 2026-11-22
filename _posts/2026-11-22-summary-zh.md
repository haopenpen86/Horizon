---
layout: default
title: "Horizon Summary: 2026-11-22 (ZH)"
date: 2026-11-22
lang: zh
---

> 从 26 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [OpenAI 发文讨论困惑度与模型智能](#item-tech-news-1) ⭐️ 7.0/10
2. [Muru：Graham Dumpleton 的 Rust ASGI/WSGI 服务器](#item-tech-news-2) ⭐️ 7.0/10

**科技博客**
1. [好代码的关键在于避免灾难性失误](#item-tech-blog-1) ⭐️ 6.0/10
2. [不确定时，先小步试错](#item-tech-blog-2) ⭐️ 5.0/10

**财经新闻**
1. [美股科技股大跌 亚洲多市场推出稳定措施](#item-finance-news-1) ⭐️ 9.0/10
2. [厄尔尼诺海温破纪录，世界粮食计划署警告粮食援助承压](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 发文讨论困惑度与模型智能](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 发布了一篇题为《Perplexity and Intelligence》的文章，讨论困惑度（perplexity）作为与语言模型智能相关的度量。现有材料没有提供文章正文，因此其具体结论、数据和适用范围无法从现有材料核实。文章引发了关于交叉熵、能力“涌现”和评测基准的社区讨论。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度衡量模型在给定前文时对下一个 token 的预测有多“意外”，并与交叉熵损失直接相关；理论上最优值为 1，最差可相当于词表大小。OpenAI 首席科学家 Jakub Pachocki 在 11 月 22 日的文章中把这一指标与模型能力联系起来；据该文，OpenAI 模型的损失曲线在 2026 年出现陡峭加速，公司主要将其归因于长期研究和算力投入，较小部分归因于自动化。

**「影响」** 对依赖困惑度做模型评估的开发者来说，相关讨论提示该指标会受任务和训练数据影响，不能单独当作跨任务的通用能力排名；在目标任务上仍需配合其他评测。

**「社区讨论」** 有评论者指出原文没有定义困惑度，并解释它衡量模型预测下一个词元（token）的意外程度，最好为 1、最差等于词表大小；也有人对交叉熵损失与智能之间呈现清晰趋势感到意外，并追问 GPT-4.5 和 o1 在时间线上的位置。另有评论者质疑能力会在特定困惑度“涌现”，认为专门训练数学的小模型在其他任务上的困惑度可能更高。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>

</ul>
</details>

**标签**: `#perplexity`, `#language models`, `#model evaluation`, `#OpenAI`, `#AI research`

---

<a id="item-tech-news-2"></a>
### [Muru：Graham Dumpleton 的 Rust ASGI/WSGI 服务器](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

曾创建 mod\_wsgi 的 Graham Dumpleton 正在开发 Muru，这是一个以 AI 辅助方式编写的 Rust 服务器，目标是在开发和生成环境中运行 ASGI 与 WSGI Python 应用。Simon Willison 的帖子主要指向 Dumpleton 从 2026 年 11 月 4 日到 11 月 22 日连续发布的 19 篇开发记录，涉及 worker 结构、WSGI/ASGI 共存、开发环境 HTTPS、发布与重启、无服务网格的金丝雀部署、Kubernetes 集成以及缩容到零等设计。现有材料属于项目作者的开发叙述，尚未提供独立评测或正式版本兼容性信息。

rss · Simon Willison · 11月21日 23:56

**「背景」** WSGI 是 Python Web 应用与服务器之间的传统同步接口，ASGI 则在此基础上加入了异步通信能力。Muru 的作者 Graham Dumpleton 在 20 年前启动了 mod\_wsgi，此后一直关注 Python Web 应用在生产环境中的服务方式。

**「对开发者的影响」** 使用 WSGI 或 ASGI 的 Python 开发者可以评估 Muru 将两类应用并排挂载、在同一进程中交接的能力，以及通过 MCP 服务器让 AI 编码代理执行发布、测试、读取故障观测和回滚的工作流。但现有材料没有给出版本号、基准测试、稳定版状态或生产采用证据，因此这类评估仍应把 Muru 视为早期项目，不能据此认定其性能或可靠性已优于现有服务器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/muruhq/muru">GitHub - muruhq/ muru : Routing edge, control plane and Python...</a></li>

</ul>
</details>

**标签**: `#Python`, `#ASGI/WSGI`, `#Rust`, `#Web servers`, `#Open source`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [好代码的关键在于避免灾难性失误](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月22日 00:00

**「背景」** 许多工程师把写好代码等同于提出卓越洞见或漂亮的新抽象，但作者认为，在大团队维护的大型商业代码库里，真正决定成败的是避免灾难性失误。

**「方案」** 他借用棋类和网球作类比：不犯大错就能击败大多数对手。与篮球不同，编程无法积累稳固的领先优势——一次失误就可能把优雅的代码库变得脆弱。典型失误包括为同一任务引入并行系统、为关键数据制造第二个事实来源、把安全的同步操作改成脆弱的异步操作、增加隐蔽故障点，以及复杂化关键接口。作者把根源归结为不一致和引入不必要需求：前者破坏信任，让工程师不得不提防意外；后者会因实现者掌握上下文而长期滞留，并随功能增加产生组合爆炸。因此写代码时应寻找最符合现有代码库的位置，把任务裁剪到最小需求集合；若开始想着用巧妙模式实现，反而应警惕自己偏离重点。作者也限定，这主要针对大团队的大型商业代码库，且同样适用于驱动 AI 编程代理——当前代理在一致性上接近人类，但更不擅长剔除不必要需求。

**「启示」** 作者的结论是，优秀编程未必需要聪明，甚至可能被聪明拖累；持续保持一致性、克制额外需求、专注避免失误，才是大型代码库中更可靠的取胜方式。

**标签**: `#software engineering`, `#code quality`, `#simplicity`, `#consistency`, `#maintainability`

---

<a id="item-tech-blog-2"></a>
### [不确定时，先小步试错](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 面对缺乏明确指引、不知道什么会有帮助的局面，作者认为谨慎等待往往不如主动“乱试”；但乱试不当也会损害声誉。

**「方案」** 有效做法是：多尝试不同方案，密切关注来自专家和现实的反馈，并迅速放弃没有正反馈的方案。多方案还能避免过度投入——只有一个计划时，人不愿承认失败；有十个计划时，则只在乎其中一个成功。作者区分三类场景：产品尚未找到产品市场契合时，可在边缘试探；他在 GitHub Models 的多数功能并不成功，但“用 GitHub Actions token 运行 AI 推理”意外有粘性，后来成为 Continuous AI 的种子。面对庞大复杂、快速变化的系统，与其先通读全貌，不如做一批推测性改动，无改善就放弃，有改善再深挖。组织问题也可尝试自动化手工工作、接手任务或提出长期计划；多数尝试可能无用，但必须及时接收反馈，否则继续推进失败方案会让人把不满指向你。作者强调，这个过程从内部感受像反复失败，但管理者可能看到的是主动实验。

**「启示」** 因此在高度不确定时，有效工程判断不是先掌握全貌，而是低成本试探、对反馈敏感并快速止损；“乱试”的不适感并不等于危险信号。

**标签**: `#iterative experimentation`, `#engineering judgment`, `#ambiguity`, `#feedback loops`, `#organizational engineering`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大跌 亚洲多市场推出稳定措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国 AI 科技股周五遭遇大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数重挫近 11%。中国内地、韩国和中国台湾地区随后分别推出融资、回购和卖空相关稳定措施。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 融资保证金比例是投资者借钱买股票时必须自付的资金占比，下调该比例意味着同样的本金可以撬动更多杠杆；禁止“平盘以下卖空”，则是禁止在当日收盘价之下继续做空。韩国用于填补股市流动性缺口的股市稳定基金属既有政策工具，台湾金融监督管理委员会称此次暴跌为短期现象，并表示将视市况调整稳定措施。

**「影响」** 这些调整将直接改变台湾市场卖空与融券交易条件、降低内地融资买入的最低保证金要求，并影响韩国上市公司未来三个月的回购操作空间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.biggo.com/news/41704fd7-7d88-4cb6-8773-17f6b6f5c964">South Korea Restarts Stock Market Stabilization Fund Preparations...</a></li>
<li><a href="https://focustaiwan.tw/business/202611210013">Taiwan further tightens short - selling amid stock market volatility</a></li>

</ul>
</details>

**标签**: `#US tech selloff`, `#Asian markets`, `#short-selling rules`, `#margin requirements`, `#market stabilization`

---

<a id="item-finance-news-2"></a>
### [厄尔尼诺海温破纪录，世界粮食计划署警告粮食援助承压](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

据伯克利地球气候学家 Zeke Hausfather，截至 10 月，用于衡量厄尔尼诺强度的中热带太平洋升温已达 3.5℃，超过此前约 2.75℃的纪录，并预计在初冬达到约 4℃的峰值。世界粮食计划署 8 月警告，这可能到 2027 年底新增 4900 万急性粮食不安全人口，使总数达到 2.74 亿，而全球援助资金 2025 年较 2022 年峰值下降 30%。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 厄尔尼诺是指赤道中东太平洋海温异常偏高的现象；此次用于衡量其强度的升温已达 3.5℃，超过此前约 2.75℃的纪录，并预计在初冬升至约 4℃的峰值。

**「影响」** 依赖粮食援助的急性粮食不安全人群将直接受到挤压：世界粮食计划署的援助资金较 2022 年峰值减少 30%，这意味着需求上升的同时，可覆盖人数反而收缩——在索马里旱情期间，该机构覆盖人数已从 1000 万降至不足 100 万。

**标签**: `#El Niño`, `#food insecurity`, `#humanitarian aid`, `#climate risk`

---