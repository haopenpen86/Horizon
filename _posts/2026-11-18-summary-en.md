---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 40 items, 13 important content pieces were selected

---

**Technology News**
1. [Nginx patches HTTP/2 flaws behind NGINX2Root unauthenticated RCE chain](#item-tech-news-1) ⭐️ 9.0/10
2. [Google Announces Gemini 4 Neon Model](#item-tech-news-2) ⭐️ 8.0/10
3. [Telegram post reports critical Java RCE CVE-2026-114938](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9&\#x27;s France exit and the case against DNS piracy blocking](#item-tech-news-4) ⭐️ 7.0/10
5. [Google DeepMind says Genie 4 is available, limited to eligible AI Ultra subscribers](#item-tech-news-5) ⭐️ 7.0/10
6. [WeChat Xiaowei AI assistant expands testing to 30 million daily users](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [FlyDSL MonoKernels in vLLM: Low-Latency Decode on AMD GPUs](#item-tech-blog-1) ⭐️ 8.0/10

**Financial News**
1. [Fed minutes: officials see more rate hikes ahead, flag AI inflation risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed’s Waller says half-point December rate hike may be needed](#item-finance-news-2) ⭐️ 8.0/10
3. [Five Banks Reportedly Pause $480 Million ByteDance-Linked GPU Loan After US Chip Rule Change](#item-finance-news-3) ⭐️ 7.0/10
4. [UK Immigration and Asylum Bill Passes House of Commons](#item-finance-news-4) ⭐️ 7.0/10
5. [Tencent Q3 2026: AI capex far above forecasts, free cash flow negative](#item-finance-news-5) ⭐️ 7.0/10
6. [China and South Korea announce substantive end to services and investment FTA talks](#item-finance-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Nginx patches HTTP/2 flaws behind NGINX2Root unauthenticated RCE chain](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 9.0/10

Xint disclosed NGINX2Root, a chain of five Nginx vulnerabilities plus a Linux kernel flaw that it says can take an attacker from an Nginx visitor to host root. The key Nginx issue, CVE-2026-123007, is an HTTP/2 flow-control memory-corruption bug that allows unauthenticated command execution inside a worker process. Nginx 1.30.7 and 1.31.9 fix 10 CVEs, but the full chain also depends on the separate kernel flaw; Rapid7 has published a proof of concept and the report says there is no in-the-wild exploitation yet. Administrators who cannot upgrade should disable external HTTP/2, the report advises.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** HTTP/2 is an optional NGINX module rather than a default, so exposure depends on deployments having explicitly enabled it, as commenters noted. The disclosed path is a chain: the HTTP/2 flow-control memory corruption gives an unauthenticated attacker code execution inside an NGINX worker, and commenters identified the separate escalation leg as a Linux SCTP kernel flaw that lacked a public CVE number at the time of discussion.

**「Impact」** Operators running nginx with HTTP/2 enabled and who have not moved to 1.31.9 or 1.30.7 remain exposed to pre-authentication code execution inside the worker process, so those who cannot upgrade immediately should turn HTTP/2 off for internet-facing listeners. Because the full NGINX2Root chain adds a Linux kernel SCTP privilege escalation to escape to host root, running nginx inside a container should not be treated as containment; check whether your distribution has shipped a backport before assuming an OS package update is sufficient.

**「Community discussion」** Commenters criticized the disclosure timeline, arguing that the fix was visible in the open-source repository about a week before the advisory and that a temporary advisory to disable HTTP/2 could have reduced exposure. Another noted that HTTP/2 is not enabled by default and cited W3Techs&\#x27; estimate that 12% of servers use it, while a third flagged the Linux SCTP privilege-escalation flaw used in the chain as an apparent zero-day without a public CVE.

<details><summary>References</summary>
<ul>
<li><a href="https://cycode.com/blog/nginx2root-cve-2026-123007/">NGINX2Root (CVE-2026-123007): Affected Versions, How to Check ...</a></li>
<li><a href="https://computingforgeeks.com/nginx-cve-2026-123007/">nginx CVE-2026-123007: Check, Disable HTTP/2, Patch ...</a></li>
<li><a href="https://research.jfrog.com/post/nginx2shell-all-you-need-to-know-about-cve-2026-123007-and-cve-2026-123633/">Nginx2Shell: All You Need to Know About CVE-2026-123007 and ...</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#http2`, `#remote-code-execution`, `#security`, `#vulnerability-disclosure`

---

<a id="item-tech-news-2"></a>
### [Google Announces Gemini 4 Neon Model](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

Google announced Gemini 4 Neon, a new model in its Gemini family, in a blog post dated Nov. 18, 2026. The supplied announcement provides no specifications, pricing, availability, or compatibility details, so the model&\#x27;s capabilities and intended users are unconfirmed. Public discussion centered on how Neon fits Google&\#x27;s crowded naming scheme and on benchmark comparisons with other Gemini and competitor models.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Background」** Gemini 4 Neon is part of a tiered Gemini 4 lineup rather than a single flagship model: Google&\#x27;s model card casts Carbon as the option for the hardest long-horizon projects and Hydrogen as the fast everyday model, with Neon positioned to balance depth and efficiency. Google documents the model as \`gemini-4-neon\`, available through the Gemini API and its enterprise agent platform for coding, analytical reasoning, and production workflows.

**「Model selection」** For teams picking among Gemini variants, commenters argue that headline scores do not map cleanly to fit: Neon reportedly scores higher overall than Gemini 4 Carbon, yet Carbon is described as still positioned for long-horizon and research-scale reasoning, where it leads on evals such as CritPt. One commenter also reported that Neon comes within roughly 1% of Fable 5.2&\#x27;s performance at about 40% of the cost on vals.ai — an unverified, single-source claim that buyers should check against published API pricing and task-specific evals before switching.

**「Community Discussion」** Commenters criticized the proliferation of model names across Google, Anthropic, and OpenAI as difficult to map to use cases. One said Gemini models still feel less capable than Anthropic&\#x27;s Opus 5.5 in general use despite benchmarks, another argued Neon is positioned as more intelligent overall but weaker than Carbon on research-scale reasoning, and a third cited a vals.ai result showing performance within about 1% of Fable 5.2 at about 40% of the cost; these are commenter claims, not independently verified here.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/gemini/4-neon">Gemini 4 Neon | Gemini Enterprise Agent Platform | Google ...</a></li>
<li><a href="https://aistudio.google.com/docs/models/gemini-4-neon">Gemini 4 Neon - Gemini API | Google AI Studio</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-neon/">Gemini 4 Neon - Model Card — Google DeepMind</a></li>

</ul>
</details>

**Tags**: `#Gemini`, `#Google AI`, `#model release`, `#LLM benchmarking`, `#AI industry`

---

<a id="item-tech-news-3"></a>
### [Telegram post reports critical Java RCE CVE-2026-114938](https://censys.com/advisory/cve-2026-114938/) ⭐️ 8.0/10

A Telegram aggregator post reports CVE-2026-114938, an unauthenticated Java remote code execution vulnerability rated CVSS 4.0 9.2 and described as present for nearly four years. According to the post, it affects JDK 17 from 17.0.6 onward, plus JDK 21, 25, and 27; standard Java 8/11 are generally unaffected except for Oracle Java 8 Performance Pack. The report limits exposure to x86-64 server processors with AVX-512 VBMI—roughly Intel Ice Lake-and-newer Xeon and AMD Zen 4-and-newer EPYC/Ryzen—while ARM64 is unaffected. The post provides no independent confirmation, exploit details, patch availability, or disclosure timeline, so the claim remains unverified.

telegram · zaihuapd · Nov 18, 03:55

**「What the flaw is in」** The vulnerability sits in an optimized Base64 decoding implementation that OpenJDK uses on x86-64 processors, which explains why it is limited to certain server CPUs rather than all Java deployments. It was publicly disclosed on November 17, 2026, with differing severity ratings: Oracle rates it 8.1 under CVSS 3.1, while the researchers who reported it rate it 9.2 under CVSS 4.0.

**「Impact」** For operators, the practical exposure is limited to hosts that match both the affected JDK range and the AVX-512 VBMI x86-64 CPU requirement. The post supplies no patch or mitigation details, so teams would need separate vendor confirmation before treating it as remediation guidance.

<details><summary>References</summary>
<ul>
<li><a href="https://censys.com/advisory/cve-2026-114938/">Nov 18 Advisory: OpenJDK Remote Code Execution (Java4Shell ...</a></li>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-java4shell">Advisory: OpenJDK Base64 Vulnerability - Java4Shell (CVE-2026 ...</a></li>

</ul>
</details>

**Tags**: `#Java`, `#CVE-2026-114938`, `#remote code execution`, `#security vulnerability`, `#server infrastructure`

---

<a id="item-tech-news-4"></a>
### [Quad9&\#x27;s France exit and the case against DNS piracy blocking](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Quad9 has withdrawn from France in a dispute over DNS-level anti-piracy blocking, and this analysis argues that DNS resolvers are the wrong enforcement point for such measures. It frames the episode around internet blocking, privacy, and legal overreach rather than treating DNS filtering as a neutral copyright remedy. The supplied material does not detail the legal order’s scope or timing, so the specific obligations Quad9 faced are not established here.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** DNS resolvers map domain names to IP addresses, which makes them a potential chokepoint for blocking access to sites. In October 2026 a Paris court ordered the nonprofit resolver Quad9 to block domains accused of distributing unauthorized sports broadcasts; Quad9 said it would stop serving French users on November 24, 2026, affecting both its cybersecurity filtering and general DNS service, and TorrentFreak reported it was the second DNS resolver to leave France.

**「Impact」** French users who relied on Quad9 need to choose another public resolver, and the case makes the compliance-or-exit tradeoff concrete for other independent DNS providers.

**「Community Discussion」** Several commenters reject DNS blocking as a piracy remedy: one calls non-prosecution anti-piracy efforts a backdoor to speech suppression, while another argues the paid option must be easier than piracy, citing subscription friction and DRM. A separate thread asks whether blame belongs with the French court’s interpretation or the lawmakers who wrote the rule, and another commenter says enforcement is moot because AI companies have already consumed copyrighted works.

<details><summary>References</summary>
<ul>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>
<li><a href="https://torrentfreak.com/dns-resolver-quad9-will-leave-france-after-court-orders-piracy-blocking-penalty/">DNS Resolver Quad9 Will Leave France After Court Orders ...</a></li>
<li><a href="https://cyberinsider.com/quad9-to-leave-france/">Quad9 to leave France after court orders piracy-related DNS ...</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet censorship`, `#piracy`, `#privacy`, `#internet governance`

---

<a id="item-tech-news-5"></a>
### [Google DeepMind says Genie 4 is available, limited to eligible AI Ultra subscribers](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind&\#x27;s blog announced that Genie 4, the next version of its generative world-model project, is now available. The supplied material carries no technical detail — no model architecture, benchmark numbers, or independently measured capabilities — so the post as reported establishes availability rather than verified performance. According to a reader quoting the page, access is restricted to &quot;Eligible Google AI Ultra subscribers,&quot; and that same commenter, browsing from the UK on a non-Workspace Gmail account, found the Ultra plan still listing Genie 3 instead of Genie 4. Whether that reflects a regional rollout limit or a page that has not been updated is unresolved in the available evidence.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Earlier Genie context」** Genie 4 is the latest in Google DeepMind&\#x27;s Genie line of generative world models, which aim to produce interactive, playable environments from prompts rather than hand-built game engines. TechCrunch reported on October 27 that Genie 4 entered a research preview with real-time audio, more realistic worlds, and real-time steering, with Gemini acting as a director that plans steps and checks frames while Genie generates the visuals.

**「Access and impact」** For anyone wanting to try Genie 4, the binding constraint described so far is the subscription tier rather than the model: the announcement reportedly gates use behind an eligible Google AI Ultra plan, and one reader said their Workspace account could not obtain that tier at all. The commenter also noted that a previous Genie version was US-only, leaving non-US subscribers unable to tell whether the Genie 3 listing they see is a regional restriction or a documentation lag.

**「Community reaction」** The most concrete thread is about access: one commenter asked Google to state plainly how to pay for the product, reporting that Ultra showed Genie 3 rather than Genie 4 and that their Workspace account was ineligible. Other commenters diverged from capability talk — one said they increasingly wanted none of these technologies and wished for more discussion of negative consequences, while another praised DeepMind&\#x27;s output as craft-driven and questioned how it could become profitable, and a third speculated about Genie-style models eventually serving as game engines.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/">Project Genie update featuring Genie 4</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more realistic... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#generative-world-models`, `#google-deepmind`, `#ai-model-release`, `#interactive-environments`, `#product-availability`

---

<a id="item-tech-news-6"></a>
### [WeChat Xiaowei AI assistant expands testing to 30 million daily users](https://mp.weixin.qq.com/s/r3NthxJZQJgztyLADwNV4A) ⭐️ 7.0/10

Tencent said in its 2026 third-quarter earnings report that testing of WeChat&\#x27;s Xiaowei AI assistant has expanded to 30 million daily active users. The assistant is being gradually integrated into WeChat chat, Moments, official accounts, and Channels. Xiaowei uses a custom WeLM model optimized for cost efficiency; Tencent claims its inference costs are low and continuing to decline. Tencent also expects some inference tasks to run on users&\#x27; devices in the future.

telegram · zaihuapd · Nov 18, 11:35

**「WeChat&\#x27;s baseline usage」** WeChat already handles enormous daily traffic — its users send more than 45 billion messages and make 410 million voice and video calls per day, spending an average of 90 minutes in the app — so embedding an assistant into chat, Moments, official accounts and Channels puts it in front of habitual, high-frequency activity rather than a standalone app. That existing usage base is the context for Tencent reporting 30 million daily active users for Xiaowei during its expanded test.

**「Practical effect」** For users included in the expanded test, Xiaowei is being integrated into chat, Moments, official accounts and Channels, so AI assistance reaches places where they already read and post rather than requiring a separate app. Tencent says only that some inference is expected to run on user devices in the future, with no device requirements or timeline, so on-device processing is not yet a stated compatibility factor.

<details><summary>References</summary>
<ul>
<li><a href="https://resourcera.com/data/social/wechat-statistics/">WeChat Statistics 2026 : Revenue, Users &amp; More (Global Data)</a></li>

</ul>
</details>

**Tags**: `#WeChat`, `#Tencent`, `#AI assistant`, `#on-device inference`, `#consumer AI`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [FlyDSL MonoKernels in vLLM: Low-Latency Decode on AMD GPUs](https://vllm.ai/blog/2026-11-18-flydsl-monokernels) ⭐️ 8.0/10

rss · vLLM Blog · Nov 18, 00:00

**「Background」** Interactive agents put decode on the critical path: a coding agent must finish its current action before calling the next tool, so low-concurrency serving optimizes per-user responsiveness over throughput. At small batch sizes each decode step is a chain of dependent kernels whose dispatch, startup, and drain costs loom large; HIP graphs remove only the CPU-side launch overhead.

**「Solution」** The authors&\#x27; MonoKernels, written in AMD&\#x27;s FlyDSL Python DSL and MLIR compiler, keep a fixed grid of thread blocks persistent across several dependent stages in one launch: blocks take ready downstream work without a new kernel boundary, prefetch projection or expert weights during earlier compute, and hand off results through tagged mailboxes at tile granularity, with TP all-reduces inside the kernel. Boundaries are model-specific — DeepSeek-V4.1-Flash splits standard layers into K1 \(attention front, KV-cache update\) and K2 \(attention back, all-reduce, MoE\); MiniMax-M3 first fused only the FFN half — and each kernel is JIT-compiled for its model, TP size, and step widths. vLLM ships it as opt-in \(--monokernel\) specialized decode with model-owned code and a per-step plan\(\) that falls back to stock layers for prefill, mixed batches, or overly wide steps, preserving HIP graphs and speculative decoding. Reported gains: DeepSeek-V4.1-Flash on TP2 MI355X rises from 318.1 to 429.1 tok/s/user at concurrency 1; an MI325X layer drops from 32 kernels in 320 µs to 2 in 115 µs; GLM-5.2 falls from ~2,459 to ~210 kernels per step. Accuracy stayed within noise where tested, but gains shrink at higher concurrency, step width is capped, and some baselines are historical rather than same-node.

**「Takeaway」** The authors conclude that interactive-serving latency is better won by redesigning kernel boundaries and schedules than by speeding up individual operators, with FlyDSL MonoKernels now merged opt-in for five models in vLLM improving concurrency-1 interactivity or time per output token by 1.20×–2.26× as a low-concurrency latency optimization, not a throughput one.

**Tags**: `#LLM inference`, `#GPU kernel fusion`, `#vLLM`, `#AMD ROCm`, `#low-latency decoding`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes: officials see more rate hikes ahead, flag AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

Federal Reserve officials judged in October that further increases to the benchmark interest rate would likely be needed to return inflation to their 2% goal, according to minutes released Wednesday, after the committee voted 10-2 to hold the rate at a range of 3.75%-4%.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** Officials are weighing whether price pressures tied to the Iran war and President Donald Trump&\#x27;s tariffs are temporary or becoming entrenched, and Fed staff warned that off-balance-sheet leasing commitments and circular financing among AI-related firms could amplify losses if returns on AI investment disappoint.

**「Impact」** Futures traders are fully pricing a quarter-point increase at the Dec. 8-9 meeting, a move that would raise costs on borrowing tied to the benchmark rate, such as credit cards.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#AI financing risk`

---

<a id="item-finance-news-2"></a>
### [Fed’s Waller says half-point December rate hike may be needed](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

Federal Reserve Governor Christopher Waller said Wednesday that the central bank may need a half-percentage-point rate hike at its Dec. 8-9 meeting to “shock people” and combat inflation, while futures markets fully price only a quarter-point increase.

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed cut rates three times in 2025 before raising them in September and holding steady in October, and most inflation readings have stayed above 3%—above its 2% target—after energy prices spiked and tariff effects lingered.

**「Impact」** A half-point increase would be twice the quarter-point move futures markets fully price, a sharper tightening that would raise borrowing costs for households and businesses.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [Five Banks Reportedly Pause $480 Million ByteDance-Linked GPU Loan After US Chip Rule Change](https://www.bloomberg.com/news/articles/2026-11-17/banks-pause-480-million-chip-loan-tied-to-china-s-bytedance) ⭐️ 7.0/10

Five banks reportedly paused a $480 million loan intended to fund Nvidia GPU purchases for a ByteDance data center project in Malaysia after new US AI chip restrictions raised compliance concerns. Borrower Aolani Cloud, a Singapore cloud provider, said it is assessing the rules with regulators and financing partners.

telegram · zaihuapd · Nov 18, 05:11

**「Background」** The loan pause follows new US export rules covering AI chips sent to Southeast Asian data centers, with an exemption for US cloud providers; analysts expect such rules to delay projects and raise costs rather than halt the region’s buildout.

**「Impact」** The stalled loan leaves Aolani Cloud’s Malaysia data-center project without its intended GPU financing, which could delay ByteDance’s planned access to advanced Nvidia chips there.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U . S . chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>
<li><a href="https://www.businesstimes.com.sg/companies-markets/telcos-media-tech/banks-pause-us480-million-chip-loan-tied-chinas-bytedance">Banks pause US$480 million chip loan tied to China’s ByteDance</a></li>
<li><a href="https://www.gate.com/news/detail/NVDA/bytedance-480m-loan-stalled-after-us-tightens-ai-chip-export-rules-25700410">ByteDance $480M Loan Stalled After US Tightens AI Chip Export ...</a></li>

</ul>
</details>

**Tags**: `#US chip export controls`, `#ByteDance`, `#GPU financing`, `#data centers`, `#Nvidia`

---

<a id="item-finance-news-4"></a>
### [UK Immigration and Asylum Bill Passes House of Commons](https://www.bloomberg.com/news/articles/2026-11-17/uk-s-house-of-commons-passes-controversial-immigration-bill) ⭐️ 7.0/10

The UK House of Commons passed the Immigration and Asylum Bill by 290 votes to 94, sending it to the House of Lords; the bill would raise most migrants’ settlement residency requirement from 5 to 10 years and tighten asylum rules.

telegram · zaihuapd · Nov 18, 05:51

**「Background」** The bill was introduced in the House of Commons on 30 June 2026 and has completed earlier stages, but it is not yet law and now faces further scrutiny in the House of Lords.

**「Impact」** If enacted, most migrants would wait 10 years rather than 5 to apply for settlement, while eligible health and social care visa holders earning at least £25,000 could still use the 5-year route.

<details><summary>References</summary>
<ul>
<li>UK&#x27;s House of Commons Passes Controversial Immigration Bill</li>
<li>Immigration and Asylum Bill: Progress of the bill</li>

</ul>
</details>

**Tags**: `#UK immigration policy`, `#asylum reform`, `#residency rules`, `#health and social care visas`, `#House of Commons`

---

<a id="item-finance-news-5"></a>
### [Tencent Q3 2026: AI capex far above forecasts, free cash flow negative](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent&\#x27;s reported third-quarter 2026 revenue rose 8% year on year to RMB207.3bn, missing market expectations, while quarterly capital expenditure reached RMB81.4bn against an expected RMB55.4bn, leaving free cash flow at negative RMB69.1bn, according to a Cailian Press report. Tencent also said its WorkBuddy product is China&\#x27;s most-used AI application by daily token volume, at more than 100 trillion tokens a day — a company claim not independently verified.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** Tencent&\#x27;s swing to negative free cash flow fits a wider pattern among Chinese platform companies funding AI compute buildouts, with Baidu also reporting negative free cash flow — a net outflow of RMB7.954 billion — as its capital spending tripled.

**「Why it matters」** If capex keeps exceeding the cash Tencent&\#x27;s operations generate, the company would have less free cash for the buybacks and dividends its shareholders have relied on.

<details><summary>References</summary>
<ul>
<li><a href="https://robotbelt.com/baidu-q2-capital-spend-triples-ai-first-tier/">Baidu Q2 capex triples as Li Yanhong vows AI comeback</a></li>

</ul>
</details>

**Tags**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#China tech`

---

<a id="item-finance-news-6"></a>
### [China and South Korea announce substantive end to services and investment FTA talks](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

China and South Korea announced on November 18 the substantive conclusion of follow-up negotiations on services and investment under their free trade agreement. China committed to most-favored-nation treatment for South Korean films and games and wider opening in tourism, legal, construction and finance, while both sides agreed to expand audiovisual co-production from films to TV dramas, animation, variety shows and documentaries; the talks began in March 2018, and some technical matters remain for working-level discussion.

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The follow-up talks began in March 2018 under the existing China–South Korea free trade agreement, and the announcement came after a Nov. 18 summit between President Lee Jae-myung and President Xi Jinping; some technical items still need working-level negotiation.

**「Impact」** Once finalized and implemented, the commitments would improve market-access terms in China for South Korean film, gaming, tourism, legal, construction, finance and audiovisual firms.

<details><summary>References</summary>
<ul>
<li><a href="https://www.chosun.com/english/national-en/2026/11/19/NTPG5ZDJMBAKLH427BSO5LHJKU/">Korea-China FTA Service, Investment Negotiations ...</a></li>
<li>South Korea-China FTA Services and Investment Talks Concluded After 8 ...</li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#services and investment`, `#trade policy`, `#cultural industries`, `#market opening`

---