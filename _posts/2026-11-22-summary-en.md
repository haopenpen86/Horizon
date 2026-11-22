---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 26 items, 6 important content pieces were selected

---

**Technology News**
1. [OpenAI Explores Perplexity as a Measure of Model Intelligence](#item-tech-news-1) ⭐️ 7.0/10
2. [Muru: AI-assisted Rust server for ASGI and WSGI Python apps](#item-tech-news-2) ⭐️ 7.0/10

**Technology Blog**
1. [Good Programming Is Mostly About Avoiding Catastrophic Blunders](#item-tech-blog-1) ⭐️ 6.0/10
2. [Flailing as a Strategy for Ambiguous Engineering Problems](#item-tech-blog-2) ⭐️ 5.0/10

**Financial News**
1. [U.S. Tech Selloff Prompts Asian Market Stabilization Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [Record El Niño Warming Adds Pressure to Food Aid](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Explores Perplexity as a Measure of Model Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI published a post examining perplexity — the degree of surprise a model shows when predicting the next token in a sequence — as a measure connected to model intelligence. The supplied material does not include the article text, so the post&\#x27;s specific claims, figures, and any benchmark it introduces cannot be verified here. Community readers describe the post as presenting a clear relationship between cross-entropy loss and model capability, and several treat it as a notably simple alternative to the more elaborate evaluation benchmarks now common. The discussion also notes that the post itself does not define perplexity, which commenters supplied on its behalf.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Context: what perplexity measures」** In language-model evaluation, perplexity is a next-token prediction metric: lower values mean the model is less uncertain about the actual continuation. OpenAI Chief Scientist Jakub Pachocki’s post uses that measure to examine a plot of OpenAI model losses showing a steep acceleration in 2026, which he attributes mostly to long-term research and compute investments and only in smaller part to automation; an OpenAI employee commenting on Hacker News described the correlation between perplexity and quality as not 1, but not 0 either.

**「Impact」** For teams selecting evaluation methods, the practical question raised is whether a single next-token prediction metric can substitute for task-specific benchmarks. Commenters argue perplexity is cheap and simple but only tracks capability on tasks whose data resembles the model&\#x27;s training distribution, so a specialized model trained on math could show poor general perplexity while still performing well on its target task. That makes perplexity a plausible screening signal rather than a drop-in replacement for benchmark suites, a limitation attributed to readers rather than established by the post.

**「Community Discussion」** Commenters filled in the definition the post omitted: perplexity ranges from 1, when the model assigns probability 1 to every actual next token, up to the vocabulary size for a random predictor. jrflo called the apparent cross-entropy trend shocking given the shift toward reinforcement learning and welcomed a simple benchmark, while tensor was skeptical of claims that particular abilities &quot;emerge&quot; at given perplexity levels because task-specialized small models would distort the relationship. d\_burfoot argued the opposite direction, contending that prediction and compression rate on raw data is exactly the metric that captures progress in extracting world models, citing a 2008 paper of his own.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>
<li><a href="https://news.ycombinator.com/item?id=50601525">Perplexity and Intelligence | Hacker News</a></li>

</ul>
</details>

**Tags**: `#perplexity`, `#language models`, `#model evaluation`, `#OpenAI`, `#AI research`

---

<a id="item-tech-news-2"></a>
### [Muru: AI-assisted Rust server for ASGI and WSGI Python apps](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, the creator of mod\_wsgi, is developing Muru, an AI-assisted Rust server intended to run both ASGI and WSGI Python applications in development and production. Simon Willison points readers to the GitHub project and to Dumpleton&\#x27;s unusually detailed public build log, which ran from Nov. 4 through Nov. 22 and covers worker internals, import-once/fork-many, HTTPS in development, mixed WSGI/ASGI support, releases without restarts, canaries, Kubernetes, scaling to zero, and tracing. The source presents Muru as an in-progress effort rather than a measured or independently evaluated release; Dumpleton says AI may do much of the surface work while he decides what is good enough.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Graham Dumpleton began mod\_wsgi two decades ago as a way to serve Python web applications under Apache, and it became a long-standing deployment option for WSGI apps. Muru extends that work to both WSGI and ASGI, the asynchronous interface that succeeded WSGI for Python web applications. Willison notes that Dumpleton is documenting Muru in public as he builds it, the same approach he took with his earlier project wrapture.

**「AI-agent deployment workflow」** Developers considering Muru can use its MCP server to let an AI coding agent deploy each change as a release, test it, read Muru&\#x27;s observations when something fails, and roll back, according to the project repository. The source provides no independent performance or production evaluation, so teams should verify that workflow and production suitability themselves before depending on it.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/muruhq/muru">GitHub - muruhq/ muru : Routing edge, control plane and Python...</a></li>

</ul>
</details>

**Tags**: `#Python`, `#ASGI/WSGI`, `#Rust`, `#Web servers`, `#Open source`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Good Programming Is Mostly About Avoiding Catastrophic Blunders](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that good programming is less about brilliant insights or elegant new abstractions than about avoiding catastrophic mistakes, because unlike basketball a codebase cannot preserve a durable lead: one blunder can turn an elegant system into a janky one.

**「Solution」** The blunders he names are concrete: introducing a parallel system for the same task, creating a second source of truth, converting a safe synchronous operation into a delicate asynchronous one, adding subtle failure points, or complicating a key interface. Their common root is inconsistency and unnecessary requirements. Inconsistency is dangerous because it destroys trust—engineers can no longer assume code works the sensible way and must hunt for surprises; unnecessary requirements are sticky because later engineers lack context to remove them and they interact combinatorially with every new feature. The author&\#x27;s prescription is therefore to find where the task fits most normally in the existing codebase and to trim it to the smallest set of requirements, treating a clever-pattern impulse as a warning sign of distraction. He scopes this to large commercial codebases with big teams, and notes it applies to AI agents too: current agents are about as consistent as humans but worse at avoiding unnecessary requirements.

**「Takeaway」** The broader claim is that great programming work does not require cleverness and may even be hindered by it; attention to detail and discipline in preserving consistency and rejecting unnecessary requirements are the main defenses against the blunders that matter.

**Tags**: `#software engineering`, `#code quality`, `#simplicity`, `#consistency`, `#maintainability`

---

<a id="item-tech-blog-2"></a>
### [Flailing as a Strategy for Ambiguous Engineering Problems](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** Engineers often face product, system, or organizational problems where the right move is unclear. Sean Goedecke argues that the cautious instinct to wait for fuller understanding can be counterproductive, since understanding is often what experimentation produces.

**「Solution」** His proposed approach is deliberate flailing: try many small interventions, watch feedback from people and reality, and ruthlessly drop ideas that do not get a positive response. Trying many things increases contact with reality and reduces overinvestment, because most guesses will be wrong. He applies this to uncertain product work—where at GitHub Models an Actions-token inference integration proved surprisingly sticky and seeded “Continuous AI”—to opaque systems, where speculative changes can be kept only if they improve things, and to organizational problems, where engineers can volunteer, automate manual work, or propose plans. The author warns that flailing badly can damage a reputation, and organizational flailing especially requires retreating quickly when feedback sours. Internally it may feel like repeated failure even when managers see proactive experimentation.

**「Takeaway」** Goedecke’s thesis is that under deep uncertainty, rapid low-cost probes plus strict feedback discipline outperform waiting for certainty or committing to one grand plan. The discomfort of feeling like you are flailing is, in his view, often a signal that you are learning effectively rather than a sign to stop.

**Tags**: `#iterative experimentation`, `#engineering judgment`, `#ambiguity`, `#feedback loops`, `#organizational engineering`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. Tech Selloff Prompts Asian Market Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

U.S. AI tech shares sold off Friday, with the Nasdaq down 5.28% and the Philadelphia Semiconductor Index nearly 11%, prompting mainland China, South Korea and Taiwan to announce market-stabilization measures. Taiwan will ban short selling below the previous close from Nov. 23 and raise the deposit required to short sell to 150% from 130%; South Korea will relax limits on listed companies&\#x27; daily share buyback orders for three months from Nov. 24, and mainland China lowered the minimum deposit for margin-financing stock purchases to 80% while advancing ChiNext market-making and trading-fee cuts.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** South Korea&\#x27;s stock market stabilization fund is a policy tool intended to fill liquidity gaps in the domestic equity market, and Taiwan&\#x27;s Financial Supervisory Commission has said it will adjust its stabilization measures as global and local market conditions change.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.biggo.com/news/41704fd7-7d88-4cb6-8773-17f6b6f5c964">South Korea Restarts Stock Market Stabilization Fund Preparations...</a></li>
<li><a href="https://focustaiwan.tw/business/202611210013">Taiwan further tightens short - selling amid stock market volatility</a></li>

</ul>
</details>

**Tags**: `#US tech selloff`, `#Asian markets`, `#short-selling rules`, `#margin requirements`, `#market stabilization`

---

<a id="item-finance-news-2"></a>
### [Record El Niño Warming Adds Pressure to Food Aid](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

Record El Niño warming in the central tropical Pacific reached 3.5°C through October, above the previous ~2.75°C record, climate scientist Zeke Hausfather said. The World Food Programme warned in August that the event could push an additional 49 million people into acute food insecurity by end-2027, while global aid funding in 2025 is 30% below its 2022 peak.

telegram · zaihuapd · Nov 22, 14:09

**「Background」** El Niño is a periodic warming of the central tropical Pacific that shifts rainfall and drought patterns worldwide; the 3.5°C anomaly recorded through October compares with a previous record of about 2.75°C, according to Berkeley Earth climate scientist Zeke Hausfather.

**「Who is affected」** Households that depend on World Food Programme assistance in drought-hit countries such as Somalia face the shortfall directly: during a comparable drought there, the agency&\#x27;s reach fell from 10 million people to under 1 million, a gap that a 30% drop in global aid funding since 2022 would widen as need rises.

<details><summary>References</summary>
<ul>
<li><a href="https://e360.yale.edu/features/super-el-nino-agriculture">How This Year&#x27;s Super El Niño Will Worsen Global Hunger - Yale E360</a></li>

</ul>
</details>

**Tags**: `#El Niño`, `#food insecurity`, `#humanitarian aid`, `#climate risk`

---