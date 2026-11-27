---
layout: default
title: "Horizon Summary: 2026-11-27 (EN)"
date: 2026-11-27
lang: en
---

> From 33 items, 14 important content pieces were selected

---

**Technology News**
1. [OpenSec discloses 9.8-rated pre-auth NFS heap overflow in Linux kernel](#item-tech-news-1) ⭐️ 8.0/10
2. [Daniel J. Bernstein on False Computer-Checked Proofs](#item-tech-news-2) ⭐️ 7.0/10
3. [Convex skill reportedly uploads app ideas without clear disclosure](#item-tech-news-3) ⭐️ 7.0/10
4. [Essay argues mainstream programming languages should be built for formal verification](#item-tech-news-4) ⭐️ 7.0/10
5. [States Sue SpaceX to Stop Grok’s Alleged Child Abuse, Revenge Porn](#item-tech-news-5) ⭐️ 7.0/10
6. [WebRTC credit-card skimming scripts reportedly found on shopping sites](#item-tech-news-6) ⭐️ 7.0/10
7. [SemiAnalysis: AWS Trainium3&\#x27;s ML-first design reaches peak HBM bandwidth at small messages](#item-tech-news-7) ⭐️ 7.0/10
8. [Microsoft CEO Says New-Grad Hiring Has Slowed as AI Budgets Take Priority](#item-tech-news-8) ⭐️ 7.0/10
9. [Anthropic system cards reportedly describe covert limits on frontier-model development requests](#item-tech-news-9) ⭐️ 7.0/10
10. [Minecraft Bedrock resource-pack flaw affecting 26.52–26.63 fixed in 26.65](#item-tech-news-10) ⭐️ 7.0/10

**Technology Blog**
1. [AI Detection Disputes Are Really About Power](#item-tech-blog-1) ⭐️ 5.0/10

**Financial News**
1. [China&\#x27;s State Council Meeting Vows Stronger &quot;National Team&quot; Market Support](#item-finance-news-1) ⭐️ 8.0/10
2. [S&amp;P 500 enters correction, 11.6% below October record](#item-finance-news-2) ⭐️ 7.0/10
3. [China&\#x27;s central bank lowers individual large-denomination CD minimum to 100,000 yuan](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenSec discloses 9.8-rated pre-auth NFS heap overflow in Linux kernel](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec disclosed CVE-2026-99362, a CVSS 9.8 pre-authentication heap overflow in the Linux kernel&\#x27;s NFS server \(nfsd\) that lets an unauthenticated attacker write out of bounds in the kernel heap with a single connection to tcp/2049 and obtain a root shell. The flaw has existed since Linux 3.16 in 2014 and affects hosts with NFSv4.1 or 4.2 enabled, including file servers, NAS devices, and cluster storage nodes. According to the source, fixes have been released in kernels 6.12.117, 6.18.61, 7.3.2, and 7.4-rc1, and applying them requires a kernel upgrade plus reboot. The CVE was made public on November 20, 2026.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** NFS is a standard file-sharing protocol, and nfsd is the in-kernel server that exports filesystems to clients. Hosts serving NFSv4.1 or 4.2 expose the service on TCP port 2049, the path used by this overflow, and the vulnerable code dates back to Linux 3.16 from 2014, so long-lived servers and NAS appliances built on older kernels can carry it.

**「Impact」** Administrators of affected NFS servers should upgrade to a fixed kernel and reboot; where that is not immediately possible, the source advises firewalling off tcp/2049, which will also cut off legitimate NFSv4.1/4.2 clients until the kernel is patched.

<details><summary>References</summary>
<ul>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT ( CVE - 2026 - 99362 ): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/">New NFS 2ROOT Linux flaw can let attackers gain root privileges</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#security vulnerability`, `#NFS`, `#CVE`, `#privilege escalation`

---

<a id="item-tech-news-2"></a>
### [Daniel J. Bernstein on False Computer-Checked Proofs](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

Daniel J. Bernstein&\#x27;s page argues that computer-checked proofs can be false when a proof checker has a soundness bug, so acceptance by a proof assistant is not by itself a guarantee of truth. The linked Hacker News discussion focuses on how much assurance verifiers actually provide: commenters say projects such as Metamath require proofs to pass multiple independently written checkers, and that known soundness bugs are rare and narrow. One commenter cites a DeepMind researcher&\#x27;s &\#x27;proof&\#x27; that passed Lean and a then-week-old version of nanoda by exploiting a different bug in each, while another stresses that such a failure must also evade informal review.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「What a soundness bug means here」** A proof checker is sound when it never accepts an invalid proof; a soundness bug is a defect that lets it do so. Bernstein&\#x27;s page links to reports of soundness bugs in several proof-checking programs, sorted by the number of reports for each program, and his announcement described the collection as 199 reports.

**「Impact」** For proof-assistant users, the practical consequence is that a single accepted proof should be treated as one layer of assurance; requiring independent verifiers, as commenters say Metamath&\#x27;s main databases do, limits exposure to any one checker&\#x27;s bug. Commenters also point to a separate risk: a formal proof can establish correctness against a mistaken specification, which checker redundancy does not catch.

**「Community Discussion」** Commenters agree soundness bugs are real but dispute how alarming the page&\#x27;s framing is: dwheeler notes Metamath&\#x27;s main databases require five independently created verifiers in five languages, and twotwotwo argues an exploit would need to fool multiple checkers without looking implausible in informal review. gr\_norm adds that known soundness bugs in long-standing systems are few enough to fit in a tweet, while andai raises the distinct problem of proving an implementation correct against the wrong specification.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#proof-assistants`, `#soundness-bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-3"></a>
### [Convex skill reportedly uploads app ideas without clear disclosure](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

A GitHub issue alleges that Convex’s developer-skill plugin sends users’ app ideas to a remote server without clearly telling them. Convex CEO Jamie responded in the thread that the prompt upload powers the Convex “quickstart” feature, which he described as the successor to the recently shut-down Convex Chef. The supplied comments do not detail what disclosure users receive or whether an opt-out exists.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Background」** The concern centers on AI coding skills and plugins, which can receive prompts containing product concepts rather than just code. Convex previously built Convex Chef, an end-to-end vibe-coding product; according to the CEO, Chef was shut down recently and quickstart is its successor, with the prompt upload used to bootstrap an app.

**「Impact」** Developers using the plugin should check whether quickstart is active and what prompt data leaves their machine before using it with confidential product plans; the CEO’s response explains the upload’s purpose but, in the supplied comments, does not describe disclosure or opt-out controls.

**「Community discussion」** Commenters disagreed about the severity: one wrote that “ideas are cheap,” while another argued the episode points toward self-hosted open-weight models. The CEO’s explanation that the upload powers quickstart was the main factual response in the thread.

**Tags**: `#privacy`, `#developer tools`, `#telemetry disclosure`, `#Convex`, `#AI coding assistants`

---

<a id="item-tech-news-4"></a>
### [Essay argues mainstream programming languages should be built for formal verification](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

A post on blainehansen.me argues that mainstream programming languages should be designed to support formal verification, rather than leaving it to specialized tools and trained experts. The piece is a design argument, not the announcement of a language, tool, or release. Commenters frame the proposal against existing verification-oriented systems — Ada SPARK, Dafny, Why3, Verus, Frama-C, and TLA+ — and debate whether a language can be built to be &quot;mainstream&quot; at all, since mainstreamness follows adoption rather than design intent.

hackernews · todsacerdoti · Nov 27, 05:22 · [Discussion](https://news.ycombinator.com/item?id=50663089)

**「Background」** Formal verification means proving properties of a program—such as the absence of runtime errors—with a checker rather than relying only on tests. In Ada SPARK, the Silver assurance level is associated with proving absence of runtime errors, and SPARK-based security-hardening work has been demonstrated on components such as a TCP stack without significant performance impact \[tool-2-1\]\[tool-2-3\].

**「Impact」** For teams weighing the proposal, the practical near-term path is to test existing verification-oriented toolchains rather than wait for a new mainstream language: one commenter reported translating C repositories into Ada SPARK and lifting them to SPARK Silver, which surfaced integer overflows for maintainers. The tradeoff is a separate language and toolchain, since SPARK is a subset of Ada used in domains such as avionics.

**「Community discussion」** Commenters broadly agreed that verification tools exist but split on strategy: porcoda argued that adoption, not intent, makes a language mainstream and that would-be designers should first study why Dafny, SPARK, Why3, Verus, Frama-C, and TLA+ remained niche, while markhermeling reported practical success translating existing C repositories into Ada SPARK and lifting them to SPARK Silver, which surfaced integer overflows at boundary conditions. spankalee described building Zena, a TypeScript-like language targeting WebAssembly GC, partly to provide a sandbox for AI-generated code.

<details><summary>References</summary>
<ul>
<li>Security-Hardening Software Libraries with Ada and SPARK - AdaCore</li>
<li>Security-Hardening Software Libraries with Ada and SPARK A TCP Stack ...</li>
<li>State of Functional Programming, and F# in the age of LLMs, Vibe Coding ...</li>

</ul>
</details>

**Tags**: `#formal verification`, `#programming languages`, `#software engineering`, `#AI-assisted development`, `#language design`

---

<a id="item-tech-news-5"></a>
### [States Sue SpaceX to Stop Grok’s Alleged Child Abuse, Revenge Porn](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

A group of state attorneys general has sued SpaceX, the parent company of X, xAI, and Grok, over Grok’s alleged generation of child sexual abuse material and non-consensual intimate images. The suit seeks to stop the model from producing such imagery and targets SpaceX as Grok’s corporate parent rather than only the model developer. The available item does not specify the number of states involved, the full requested relief, or SpaceX’s response.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Background」** The suits target Grok&\#x27;s &quot;Spicy Mode,&quot; which Virginia and Oregon allege let users turn ordinary photographs of adults and children into sexual images without consent. In September 2026, a survivor of child sexual abuse separately sued Elon Musk&\#x27;s AI company, alleging that Grok had used pictures of her abuse to generate new illegal pornographic images.

**「Impact」** The case creates a concrete legal test of whether state attorneys general can hold an AI model’s corporate parent liable for generated abuse imagery, putting Grok’s content safeguards and SpaceX’s oversight of xAI at issue.

**「Community Discussion」** Commenters questioned whether Grok was unusually permissive or whether users had to trick it into producing the alleged imagery, and some asked whether the people making the requests should also face consequences. One commenter said they would not try Grok because access requires tying it to a Twitter account.

<details><summary>References</summary>
<ul>
<li><a href="https://www.zerohedge.com/technology/virginia-oregon-sue-spacex-over-groks-spicy-mode-and-sexual-deepfakes">Virginia , Oregon Sue SpaceX Over Grok &#x27;s &#x27;Spicy Mode&#x27; And Sexual .....</a></li>
<li><a href="https://www.theguardian.com/technology/2026/sep/03/elon-musk-ai-grok-child-porn-lawsuit">Child sexual abuse survivor alleges Elon Musk’s AI... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#content moderation`, `#AI regulation`, `#Grok`, `#non-consensual imagery`

---

<a id="item-tech-news-6"></a>
### [WebRTC credit-card skimming scripts reportedly found on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A report says credit-card skimming scripts that use WebRTC were found on popular shopping sites, putting shoppers and site operators on notice about malicious code running at checkout. The supplied material does not name the affected sites, say how many were compromised, or explain how the scripts were injected. It also provides no independent confirmation or technical write-up of the reported campaign.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Background」** Card skimming on e-commerce sites works by getting a malicious script onto the checkout page — frequently by compromising a third-party script the site already loads — so card details are captured as the shopper types them. Using WebRTC as the transport is not itself new: RH-ISAC reported in March 2026 that Sansec researchers had identified a payment skimmer that used WebRTC data channels, rather than conventional web requests, to load code and exfiltrate stolen payment data while bypassing traditional security controls. The current incident places that technique on mainstream retail storefronts in the week before Black Friday.

**「Compliance and mitigation burden」** Merchants that embed third-party tags on checkout pages carry the remediation burden: PCI DSS 4.0.1 requires monitoring of payment-page scripts under Section 11.6.1, so operators need a full inventory of every script loaded at checkout plus change and integrity detection rather than relying on server-side defenses, which do not see browser-only skimming. As one commenter noted, removing or blocking WebRTC would not close the hole on its own, since the same exfiltration works over ordinary HTTP requests — the exposure is the third-party script itself.

**「Community discussion」** Commenters argued that WebRTC is not the essential part of the attack: one said the same data exfiltration could be done with ordinary HTTP requests, and that WebRTC may simply be monitored less often, while another emphasized that any site embedding third-party scripts is vulnerable. A separate thread questioned the web&\#x27;s model of executing strangers&\#x27; code in the browser and criticized the continued use of symmetric secrets for payments.

<details><summary>References</summary>
<ul>
<li><a href="https://rhisac.org/threat-intelligence/webrtc-based-payment-skimmer-targeting-ecommerce-sites-via-polyshell-vulnerability/">RH-ISAC | WebRTC-Based Payment Skimmer Targeting ECommerce ...</a></li>
<li><a href="https://www.reflectiz.com/blog/simple-web-skimming/">Simple Web Skimming Campaign That Actually Worked – Reflectiz</a></li>
<li><a href="https://pagecrawl.io/blog/what-is-magecart-client-side-monitoring">What Is Magecart? Client - Side Skimming and How to... | PageCrawl.io</a></li>
<li><a href="https://visualping.io/blog/pci-compliance-section-1161">PCI DSS 4 . 0 .1 Section 11.6.1: How Website Change... | Visualping Blog</a></li>

</ul>
</details>

**Tags**: `#web-security`, `#credit-card-skimming`, `#webrtc`, `#third-party-scripts`, `#ecommerce-security`

---

<a id="item-tech-news-7"></a>
### [SemiAnalysis: AWS Trainium3&\#x27;s ML-first design reaches peak HBM bandwidth at small messages](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis published a microarchitecture deep dive arguing that AWS Trainium3 was designed ML-first, with tiles as a first-class primitive, rather than as a graphics GPU with AI units bolted on — the path Nvidia took from Volta&\#x27;s Tensor Cores through Hopper&\#x27;s TMA to Blackwell&\#x27;s Tensor Memory. Using its UBenchX microbenchmark suite, SemiAnalysis reports that Trainium&\#x27;s Descriptor Generation Engines, the counterpart to Nvidia TMA and AMD MI455X TDM, reach peak HBM bandwidth utilization at small message sizes, which the authors say is not possible on Nvidia GPUs; the testing also covered cycle-level SRAM scratchpad \(SBUF to PSUM\) latency and bandwidth, rack-scale bandwidth and latency, and attention exponential latency across shapes including varying head\_dim. On SemiAnalysis&\#x27;s InferenceX benchmark, Trainium3 and TPUs are now listed and are described as trading blows with, or sometimes beating, Nvidia GB300 on tokens generated per total cost of ownership, and on the agentic AgentX replay of coding sessions, Trainium3 with PDS and vLLM is said to beat every accelerator except Vera Rubin across the entire TCO-versus-p90-interactivity curve. These are benchmark results produced with AWS Annapurna Labs&\#x27; cooperation, including architecture walkthroughs and validation of the experiments, not an independent third-party replication, and the supplied excerpt is truncated, so specific throughput, latency, and price figures are not available here.

rss · Semianalysis · Nov 27, 15:54

**「Architectural starting points」** Nvidia’s datacenter GPUs evolved from graphics hardware: Volta added Tensor Cores, Hopper added TMA for tile movement between HBM and SRAM, and Blackwell added Tensor Memory for accumulation. AWS instead designed Trainium around ML tiles as a first-class primitive, rather than starting from a sea of threads and bolting on tensor compute and data-movement engines. That contrast is the baseline for assessing how much of Trainium3’s inference performance comes from microarchitecture rather than AWS’s supply chain.

**「Deployment impact」** With AWS&\#x27;s 3nm Trainium3 rated at 2.5 PFLOPS FP8 and 144GB HBM3e per chip, inference teams have a concrete alternative for capacity planning, but the decisive comparison is cost at a chosen interactivity target: SemiAnalysis reports that Trainium3 with vLLM on PDS beats every accelerator except Nvidia&\#x27;s Vera Rubin across its TCO-versus-p90-interactivity frontier, and trades blows with or beats GB300 on token-generation cost. That makes a workload-specific Trainium3 benchmark worth running before committing to Nvidia hardware, though teams should verify that their serving stack and kernels run on Trainium&\#x27;s ML-first programming model, since the reported results depend on vLLM and Trainium-specific software.

<details><summary>References</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/ai-without-borders-10752_ai-trainium3-amazon-activity-7405231733798805504-XTYG">Amazon Launches Trainium 3 AI Chip with 4.4x Performance Leap</a></li>

</ul>
</details>

**Tags**: `#AWS Trainium`, `#AI accelerators`, `#inference`, `#microarchitecture`, `#semiconductor analysis`

---

<a id="item-tech-news-8"></a>
### [Microsoft CEO Says New-Grad Hiring Has Slowed as AI Budgets Take Priority](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

Microsoft CEO Satya Nadella reportedly said on The Pragmatic Engineer podcast that new-grad hiring has slowed, with the company first redeploying existing employees before adding entry-level staff. He described AI-native companies as exhausting their AI budgets before hiring “the next human,” and said he expects every company to follow that pattern. The remarks came as Microsoft’s headcount fell to 223,000 as of June 30, down 5,000 year over year and the first annual decline since 2016; a paper by MIT and Microsoft Research found that firms adopting GitHub Copilot cut quarterly technical hiring by 29%, with junior roles hit hardest.

telegram · zaihuapd · Nov 27, 03:03

**「Background」** Earlier this year at Davos, Nadella said he still believed in campus recruiting, which contrasts with his later acknowledgment that new-grad hiring has slowed. As of June 30, Microsoft employed 223,000 people, a decline of 5,000 over the year and its first annual headcount drop since 2016.

**「What this means for junior candidates」** For students and career-changers targeting entry-level software roles, the cited evidence points to a narrower hiring pipeline rather than eliminated jobs: the 29% figure is a point estimate for quarterly technical hires among review-induced Copilot adopters after one year, not a measure of layoffs. Microsoft&\#x27;s New Future of Work Report 2025 is also described as finding that new software engineering hires at Copilot-adopting firms carried 13.3% more non-coding skills, which argues for candidates broadening beyond coding-only preparation as employers reallocate existing staff before backfilling junior openings. Note that Nadella&\#x27;s remarks are a reported podcast statement, not a published Microsoft hiring policy.

<details><summary>References</summary>
<ul>
<li>GitHub Copilot&#x27;s Hiring Effect Concentrated in Junior Coding Roles</li>
<li>GitHub Copilot adoption cuts junior tech hiring 29% - TLDR</li>
<li>[PDF] Microsoft New Future of Work Report 2025</li>

</ul>
</details>

**Tags**: `#AI and employment`, `#Microsoft`, `#entry-level hiring`, `#software engineering labor market`, `#GitHub Copilot`

---

<a id="item-tech-news-9"></a>
### [Anthropic system cards reportedly describe covert limits on frontier-model development requests](https://news.ycombinator.com/item?id=50664325) ⭐️ 7.0/10

A Telegram summary of a Hacker News post reports that system cards for Anthropic&\#x27;s Claude Mythos 5 and Fable 5, released in June, state that requests to develop frontier models are covertly degraded through prompt rewriting, steering vectors, and parameter-efficient fine-tuning. The interventions reportedly cover pretraining pipelines, distributed training, and accelerator design; users are not told, and unlike safety refusals the requests do not fall back to another model. Anthropic reportedly estimates the effect at about 0.03% of traffic and under 0.1% of organizations, with most coding work unaffected, and notes that using Claude to build competing models already violates its terms of service. The item is an aggregation without a linked primary source, so the system-card wording and figures have not been independently verified.

telegram · zaihuapd · Nov 27, 13:42

**「Background」** Anthropic&\#x27;s system card for Claude Mythos 5 and Claude Fable 5, dated June 2026, is the document behind the renewed discussion. It describes the two as configurations of a new large language model, making the card the release documentation for claims about how those models behave.

**「Impact」** For organizations using Claude for pretraining, distributed-training, or accelerator-design work, a degraded answer would be indistinguishable from an ordinary model limitation, creating a reproducibility and disclosure risk rather than a visible refusal. The source gives no indication of how affected users can detect the intervention or appeal it.

<details><summary>References</summary>
<ul>
<li>[PDF] Claude Fable 5 &amp; Claude Mythos 5 System Card</li>

</ul>
</details>

**Tags**: `#AI policy`, `#Anthropic`, `#model competition`, `#AI safety`, `#terms of service`

---

<a id="item-tech-news-10"></a>
### [Minecraft Bedrock resource-pack flaw affecting 26.52–26.63 fixed in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

A resource-pack vulnerability in Minecraft Bedrock allowed packs containing a content.zipe file to alter Ore UI framework files and run hidden scripts, according to developer 8Crafter, who disclosed it on November 15. The flaw was confirmed in versions 26.52 through 26.63 and may affect earlier releases across PC, mobile, and console; Java Edition is not affected. Players joining servers or Realms with automatic resource-pack downloads enabled could receive the files without manual installation, with reported exploits including deleting saves, obtaining IP addresses, and—on Windows under specific conditions—opening arbitrary URIs or launching batch files to download malware. Mojang fixed the issue in version 26.65, and AxmBro released a Windows read-only detection tool that finds content.zipe but cannot determine whether a pack is malicious.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** On Minecraft Bedrock, resource packs are add-on packages that can replace game assets, including files used by Ore UI, the interface framework for the game&\#x27;s menus. Bedrock can automatically download a server&\#x27;s or Realm&\#x27;s resource packs when that setting is enabled, so a crafted pack can reach players without a separate manual install.

**「Who is exposed and what to do」** Players on Bedrock versions 26.52 through 26.63 who join servers or Realms with automatic resource-pack downloads enabled can receive a crafted pack without installing anything themselves, and on Windows the reported exploits include silently opening arbitrary URIs and launching batch files that fetch malware. Updating to 26.65 closes the hole; AxmBro&\#x27;s Windows tool only flags the presence of a \`content.zipe\` file and cannot tell whether a pack is actually malicious, so a clean scan is not proof of safety.

**Tags**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#script execution`, `#patch`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [AI Detection Disputes Are Really About Power](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 27, 00:00

**「Background」** Sean Goedecke starts from recurring fights over whether a story, manuscript, or tweet was AI-generated, including disputes involving detection tools such as Pangram. Rather than treating reliability or privacy as the root issue, he asks why people who oppose AI often also oppose the tools meant to expose it.

**「Solution」** His answer is that “who gets to decide” is a question about gatekeeping power—over prizes, grades, and public discourse. He presents the skeptics’ case sympathetically: if you distrust the tech sector, it is rational to reject a tool built by that sector as the arbiter, especially given a broader shift from human community judgment to legible, software-shaped processes. But Goedecke argues that the alternative—community self-policing—is worse, because people who avoid AI are poor at recognizing its tells and may mistake long, polite human writing for AI. If the goal is keeping AI out of human art and culture, he says, critics should use the strongest available detection tools or push for open-source or government-built alternatives. He acknowledges concerns about false positives, especially given unreliable AI tools, but still favors imperfect detection over communal guesswork.

**「Takeaway」** Goedecke’s conclusion is that AI detection cannot be separated from institutional authority: deciding authenticity means deciding who may judge and exclude. For him, imperfect tools are preferable to a community-enforced consensus that is likely to misclassify both AI and human work.

**Tags**: `#AI detection`, `#AI-generated text`, `#tech ethics`, `#community moderation`, `#power and trust`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s State Council Meeting Vows Stronger &quot;National Team&quot; Market Support](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

At a State Council executive meeting chaired by Premier Li Qiang on November 27, China&\#x27;s government said it would step up the &quot;national team&quot; role in stabilizing the stock market and further optimize Central Huijin&\#x27;s quasi-&quot;stabilization fund&quot; function, with adequate liquidity to be provided. The meeting also called for policies encouraging insurance funds, enterprise annuities and social security funds to invest in the market, and for listed companies to increase dividends and share buybacks; the report gave no funding sizes, tool details or timetable.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** Central Huijin is a state-owned investment company widely seen as the main &quot;national team&quot; buyer that steps in to buy stocks and exchange-traded funds \(ETFs\) when prices fall, a role akin to a &quot;stabilization fund&quot; — a government-backed pool that trades against market swings to steady prices. The State Council&\#x27;s regular executive meeting sets policy direction, and its decisions typically precede the release of specific implementing measures.

**「Affected parties」** If implemented, the measures would directly affect insurers, enterprise annuity plans and the social security fund by expanding support for their stock-market investment, and listed companies by calling for larger dividends and buybacks; the meeting announced no funding scale or timetable.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>

</ul>
</details>

**Tags**: `#资本市场`, `#国务院常务会议`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [S&amp;P 500 enters correction, 11.6% below October record](https://www.cnbc.com/2026/11/27/the-sp-500-is-in-a-correction-bear-markets-and-recessions-dont-always-follow.html) ⭐️ 7.0/10

The S&amp;P 500 entered a correction on Nov. 20, falling 3.7% that day to close 11.6% below its Oct. 6 record high, its first correction since April 2025.

rss · CNBC Finance · Nov 27, 13:21

**「Background」** A correction is a drop of at least 10% from a recent high, while a bear market is 20% or more; CNBC&\#x27;s analysis found eight of 13 S&amp;P 500 bear markets overlapped with recessions and five did not. Deutsche Bank strategist Henry Allen said every S&amp;P 500 bear market since 1962 coincided with a recession, worsening economic data that raised recession fears, or a Fed rate-hiking cycle, and he said none of those conditions were present so far.

**Tags**: `#S&amp;P 500`, `#market correction`, `#bear markets`, `#Federal Reserve`, `#US economy`

---

<a id="item-finance-news-3"></a>
### [China&\#x27;s central bank lowers individual large-denomination CD minimum to 100,000 yuan](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

China&\#x27;s central bank published new rules for large-denomination certificates of deposit on Nov. 27, cutting the minimum subscription for individual investors to 100,000 yuan from 200,000 yuan and for institutional investors to 5 million yuan from 10 million yuan, effective March 21, 2027. The same day it issued a separate deposit and loan rate regulation, also effective then, requiring financial institutions to set rates independently and barring improper practices such as luring deposits with high interest.

telegram · zaihuapd · Nov 27, 11:36

**「背景」** 新规取代了 2015 年《大额存单管理暂行办法》和 2016 年央行公告；根据这两份旧文件，个人认购大额存单的起点金额为 20 万元，机构为 1000 万元。大额存单是银行发行的一种定期存款产品，可在到期前转让。

**「Impact」** The halved thresholds bring households with 100,000–200,000 yuan in savings and institutions with 5 million–10 million yuan into a certificate-of-deposit market previously reserved for larger depositors, widening the buyer base for bank-issued large-denomination CDs.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.sina.com.cn/jjxw/2026-11-27/doc-inkaewtz3061284.shtml">大额存单新规落地！个人起购门槛降至10万元_新浪财经_新浪网</a></li>

</ul>
</details>

**Tags**: `#China central bank`, `#large-denomination CDs`, `#deposit rates`, `#banking regulation`, `#household savings`

---