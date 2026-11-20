---
layout: default
title: "Horizon Summary: 2026-11-20 (EN)"
date: 2026-11-20
lang: en
---

> From 42 items, 15 important content pieces were selected

---

**Technology News**
1. [Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis](#item-tech-news-1) ⭐️ 9.0/10
2. [Unverified GitHub claim asserts Navier–Stokes finite-time blow-up](#item-tech-news-2) ⭐️ 8.0/10
3. [PHP mixed-case HTTPS scheme reportedly disables TLS, patched in five branches](#item-tech-news-3) ⭐️ 8.0/10
4. [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guests](#item-tech-news-4) ⭐️ 8.0/10
5. [Tao post links Euler/Navier-Stokes singularities to generalized Riemann hypothesis](#item-tech-news-5) ⭐️ 7.0/10
6. [Thinking Machines Releases Inkling 2 Mini Open-Weight Looped MoE](#item-tech-news-6) ⭐️ 7.0/10
7. [Architect Labs claims AI discovered and verified Frostbite CPU architecture](#item-tech-news-7) ⭐️ 7.0/10
8. [Ravi Vakil Announces Hurried Draft of Proposed GRH Proof](#item-tech-news-8) ⭐️ 7.0/10
9. [Gemini can operate Mac apps for US paid users](#item-tech-news-9) ⭐️ 7.0/10
10. [UK tribunal sides with Apple on public hearings for secret backdoor demand](#item-tech-news-10) ⭐️ 7.0/10
11. [House panel releases data on 879,868 approved AI chip exports to China](#item-tech-news-11) ⭐️ 7.0/10
12. [Meta employees report Muse AI mixing accounts and exposing private data](#item-tech-news-12) ⭐️ 7.0/10

**Technology Blog**
1. [Serving a Looped Model: Inkling 2 Mini on vLLM](#item-tech-blog-1) ⭐️ 8.0/10
2. [Why Caching Visible LLM Output Barely Helps](#item-tech-blog-2) ⭐️ 6.0/10

**Financial News**
1. [U.S. companies shift from buybacks to net equity issuance](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis](https://alpo.ge/remark.pdf) ⭐️ 9.0/10

Levent Alpöge has posted a PDF note claiming that, working with Claude, he found a proof of the Riemann Hypothesis whose method extends to the Generalized Riemann Hypothesis, and that he and Claude formalized the arguments without assumptions. The note says he expects the method to reach the Extended Riemann Hypothesis with more time, but it presents a claim, not an established theorem. Commenters reported a 1.3 GB Lean formalization of roughly 15 million lines and an MIT-hosted page of checks run with Claude Code, with verification described as still in progress.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** The Riemann hypothesis is a 167-year-old open problem in mathematics. Levent Alpöge, who made the claim on November 20, 2026, is a mathematician and an Anthropic employee, according to contemporaneous reports.

**「Verification burden shifts to Lean」** For mathematicians assessing the claim, the practical test is the released Lean formalization: compiling it error-free is generally treated as confirming the logic and math of each step, according to Scientific American. That gives independent researchers a concrete artifact to check instead of relying on the announcement alone.

**「Community discussion」** Commenters treated the scale of the Lean artifact and the MIT check page as strong evidence, with one saying there was no doubt the proof is correct, while others noted a separate human proof and objected to framing that identified Alpöge as an “Anthropic employee” rather than as a mathematician. Another commenter cited Terence Tao’s earlier statement that AI could not yet solve the Riemann Hypothesis, framing the claim as a reversal of that expectation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove... | Scientific American</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is almost... | Scientific American</a></li>
<li><a href="https://www.newscientist.com/article/2600134-anthropic-mathematician-claims-ai-assisted-proof-of-the-riemann-hypothesis/">Anthropic mathematician claims AI-assisted proof of... | New Scientist</a></li>

</ul>
</details>

**Tags**: `#Generalized Riemann Hypothesis`, `#Lean formal verification`, `#AI-assisted mathematics`, `#mathematical proofs`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [Unverified GitHub claim asserts Navier–Stokes finite-time blow-up](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A GitHub repository linked from Hacker News, attributed to Tristan Buckmaster, claims a finite-time blow-up for the Navier–Stokes equations. The supplied item provides no proof text, paper, version, peer-review status, or independent confirmation, so the claim remains preliminary and unverified. Commenters treat it as potentially landmark, but the technical basis cannot be assessed from the available material.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Background」** The Navier–Stokes equations describe the velocity and pressure of incompressible fluids, and the Millennium Prize formulation asks whether smooth three-dimensional initial data can develop a finite-time singularity without an external force. The new claim follows an earlier OpenAI claim of a forced blow-up; reports describe Buckmaster and Alpöge&\#x27;s subsequent work as addressing the unforced version.

**「Impact」** For mathematicians working on the Navier–Stokes regularity problem, the immediate consequence is a verification burden: the GitHub claim needs a checkable proof and independent scrutiny before it can be treated as resolving the problem.

**「Community discussion」** Commenters emphasized that this claim concerns the unforced equations, contrasting it with an OpenAI example they said used a designed external force, and one called it part of an unusually significant day for mathematics. Those characterizations are community opinions, not confirmation of the result.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://www.scientificamerican.com/article/ai-just-solved-the-real-navier-stokes-problem/">AI just solved the “real” Navier-Stokes problem</a></li>
<li><a href="https://officechai.com/ai/tristan-buckmaster-levent-alpoge-claim-proof-of-navier-stokes-millennium-prize-problem-without-forcing/">Tristan Buckmaster, Levent Alpöge Claim Proof Of Navier ...</a></li>
<li><a href="https://createmoreflow.com/openai-navier-stokes-millennium-prize-forced-blowup/">OpenAI Claims Navier - Stokes Millennium Prize Proof</a></li>

</ul>
</details>

**Tags**: `#Navier-Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research claims`, `#AI research competition`

---

<a id="item-tech-news-3"></a>
### [PHP mixed-case HTTPS scheme reportedly disables TLS, patched in five branches](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

A reported PHP stream-wrapper bug silently disables TLS when the HTTPS or FTPS scheme uses mixed-case letters, such as HTTPS:// or httpS://, causing credentials, cookies, Basic authentication headers, POST bodies, and FTP login details to be sent in plaintext. The same downgrade reportedly applies when a third party redirects to such a URL. The issue is tracked as CVE-2026-128064 \(GHSA-f6gg-rchx-xw8j\) with a CVSS 4.0 score of 8.2 and is fixed in PHP 8.2.36, 8.3.37, 8.4.28, 8.5.13, and 8.6.0. PHP 8.1 and earlier are end-of-life and will not receive a fix, so users must normalize URL schemes to lowercase themselves.

telegram · zaihuapd · Nov 20, 03:04

**「Context」** PHP&\#x27;s stream wrappers let code such as file\_get\_contents\(\) or fopen\(\) fetch remote resources simply by prefixing a URL with a scheme, and the wrapper picks the transport — plain HTTP/FTP or TLS-protected HTTPS/FTPS — from that scheme string. According to vulnerability write-ups, the wrapper matched scheme names case-insensitively when choosing the protocol but enabled encryption only on a lowercase &quot;s&quot; in the relevant position, so a scheme like HTTPS:// or FTPS:// was routed as an unencrypted connection.

**「Who must act」** Anyone running PHP 8.1 or earlier gets no patch and must lowercase URL scheme names before they reach the HTTP/FTP stream wrappers, since the source notes those branches are EOL and will not be fixed. Because a third-party redirect to a mixed-case URL also triggers the plaintext fallback, normalizing only hardcoded URLs is insufficient — redirect targets and user-supplied URLs need the same treatment, or credentials, cookies, and POST bodies can still leave the process in clear text.

<details><summary>References</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-128064">CVE-2026-128064 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://www.zend.com/php-security-center/CVE-2026-128064">CVE-2026-128064 | Zend</a></li>
<li>EOL Fix Available | CVE-2026-128064 | PHP - HeroDevs</li>
<li>PHP critical security release, 19 November (CVE-2026-129289, CVE-2026-115560) - Aikido Security</li>

</ul>
</details>

**Tags**: `#PHP`, `#TLS downgrade`, `#CVE-2026-128064`, `#security vulnerability`, `#open source`

---

<a id="item-tech-news-4"></a>
### [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guests](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux kernel KVM has a vulnerability, CVE-2026-99312, that affects only AMD hosts with nested virtualization enabled and allows a virtual machine to read host memory. Researchers reportedly read about 127 GB of host memory from inside a VM on DigitalOcean. Upstream fixes were released on November 18 in stable kernel 7.3.5 and related updates, but Debian and Ubuntu distribution kernels remain unpatched. Until patches are available, nested virtualization can be disabled as a mitigation.

telegram · zaihuapd · Nov 20, 14:23

**「What nested virtualization adds」** KVM is Linux&\#x27;s in-kernel hypervisor, and it normally confines each guest to its own assigned RAM by using AMD-V&\#x27;s nested page tables for address translation. Nested virtualization — running a hypervisor, and therefore further guests, inside a KVM guest — adds a second translation layer that the kernel has to manage, and that is the code path implicated here. The exposure is conditional: the flaw affects AMD hosts only when nested virtualization is enabled, so hosts with that feature turned off are not in the affected configuration.

**「Impact」** Operators running KVM guests on AMD hosts with nested virtualization enabled, particularly on unpatched Debian or Ubuntu kernels, face a loss of guest isolation and should disable nested virtualization or apply an upstream fix until their distribution kernel is patched.

**Tags**: `#KVM`, `#Linux kernel`, `#virtualization security`, `#AMD`, `#CVE-2026-99312`

---

<a id="item-tech-news-5"></a>
### [Tao post links Euler/Navier-Stokes singularities to generalized Riemann hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

Terence Tao published a blog post on unforced Euler and Navier-Stokes singularities and the generalized Riemann Hypothesis. The supplied material describes it as a research-level mathematics post but does not establish the scope or independent validation of any claimed proof. The associated Hacker News discussion focused on LLM-assisted proof generation and Lean kernel verification rather than on a specific new theorem.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** The Navier–Stokes existence and smoothness problem asks whether smooth initial data for the 3D incompressible equations always yield smooth solutions, or whether finite-time blow-up is possible; it is a Clay Mathematics Institute Millennium Prize problem. The Euler equations are the inviscid counterpart, where the same singularity question is studied. The generalized Riemann hypothesis extends the Riemann hypothesis to broader classes of L-functions, and Tao&\#x27;s post discusses the singularity questions alongside it.

**「Lean acceptance is not theorem acceptance」** For mathematicians and AI-assisted proof developers, Lean kernel acceptance verifies only the formal statement that was encoded, not that the encoding captures the intended theorem. A separate claimed Lean proof of the Riemann hypothesis reported that the code compiled while the Clay Institute had not accepted a solution, so teams should audit the formal statement and its assumptions before treating a passing build as a result.

**「Community discussion」** Commenters debated whether LLM-assisted proof systems can produce genuinely new mathematical abstractions or only derive results within existing frameworks, with one asking how researchers create concepts like the Langlands program in the first place. Another commenter pointed to a Lean Zulip thread reporting that two independent kernels accepted a result, while a different commenter warned that a passing Lean build does not by itself show that the intended statement—rather than a trivial one—was proved.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier – Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity , unforced Navier - Stokes singularity , and...</a></li>
<li><a href="https://thebostonreport.com/2026/11/20/claimed-riemann-hypothesis-proof-mit-lean/">MIT Checks Claimed Riemann Hypothesis Proof | The Boston Report</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#Lean`, `#LLM-assisted proof`, `#Navier-Stokes`, `#mathematics`

---

<a id="item-tech-news-6"></a>
### [Thinking Machines Releases Inkling 2 Mini Open-Weight Looped MoE](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 7.0/10

Thinking Machines has released Inkling 2 Mini, an open-weight mixture-of-experts model built on a looped-transformer architecture and oriented toward local inference. The release stands out because looped architectures are uncommon among open models, and community members have linked a GGUF build for Ollama and llama.cpp. Commenters are comparing its performance with Qwen 3.8 27B, but those benchmark claims have not been independently verified in the supplied material, and the source page itself was unavailable.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「What a looped transformer is」** In a standard transformer, each layer processes a token once; a looped transformer instead reuses some layers. Thinking Machines says Inkling 2 Mini runs its middle layers three times for every token, an arrangement it describes as letting the model apply more reasoning and reach answers with fewer tokens.

**「Local deployment path and dense-vs-MoE tradeoff」** For people who want to run the model themselves, the practical route is the community GGUF conversion referenced in the comments, which makes it usable through llama.cpp and Ollama. Because Inkling 2 Mini is a mixture-of-experts model while the model commenters benchmark it against, Qwen3.8-27B, is a dense 27.78-billion-parameter model, local users expect notably faster decoding at comparable quality; that expectation, like the reported benchmark parity, is still unverified rather than an independently measured result.

**「Community Discussion」** Commenters reacted enthusiastically but conditionally: one called the results “bonkers good” if the benchmarks hold up in real-world use, while another highlighted that open-weight looped models remain rare. A local user planned to test the GGUF build on an AMD 7900XTX against Qwen 3.8 27B, expecting the MoE design to improve decode speed.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://huggingface.co/blog/inkling2mini">Welcome Inkling 2 Mini, Cutting-edge Performance for your ...</a></li>
<li><a href="https://llm-stats.com/models/qwen3.8-27b">Qwen3.8-27B Benchmarks, Pricing &amp; Context Window</a></li>
<li><a href="https://northflank.com/blog/qwen3-8-27b-performance-benchmarks-gpu-requirements-and-how-to-run-it">Qwen3.8-27B: Performance, benchmarks, GPU requirements &amp; how ...</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#looped transformers`, `#local inference`, `#MoE`, `#model release`

---

<a id="item-tech-news-7"></a>
### [Architect Labs claims AI discovered and verified Frostbite CPU architecture](https://architectlabs.com/blog/frostbite) ⭐️ 7.0/10

Architect Labs&\#x27; blog post claims that AI discovered, designed, and verified a new CPU architecture named Frostbite, according to the Hacker News submission. The supplied item contains no article text, benchmark results, or verification artifacts, so the architecture&\#x27;s instruction set, implementation status, and performance claims cannot be checked from the available material. The discussion mentions interaction nets as the intended paradigm, but does not establish that Frostbite supports them or that the claimed performance holds.

hackernews · shioyama · Nov 20, 10:01 · [Discussion](https://news.ycombinator.com/item?id=50572503)

**「Design premise and prior art」** Frostbite targets interaction nets, a graph-rewriting model of computation rather than the sequential instruction stream that conventional CPUs execute. Architect Labs says the design was produced with &quot;zero architectural priors,&quot; with its AI iterating on the ISA, a model it calls Arcmodel, the hardware design and verification together while treating a specification dubbed the ASL Contract as the source of truth. Commenters placed the approach alongside earlier dataflow architectures such as WaveScalar from roughly two decades ago, and skeptical Hacker News readers argued that nothing can be concluded until a physical CPU exists.

**「What the numbers actually support」** The reported 4.59x performance-per-watt and 8.77x performance-per-area figures are pre-silicon estimates over 25 workloads, measured against a silicon-proven dual-issue, in-order core rather than a modern out-of-order design, so they should not be read as a like-for-like comparison with shipping AMD or Intel parts. Anyone weighing the architecture for real work has no tape-out, fabricated chip, or independent reproduction to check yet, and the practical question is whether the interaction-net toolchain and new instruction set would require rewriting existing software.

**「Community discussion」** Commenters disputed the framing that AI originated the innovations: jkhdigital argued that humans supplied the insights and AI mainly synthesized decades-old research into a coherent product, while pizza234 criticized the use of an in-order CPU baseline and a small program set and noted that WaveScalar explored dataflow architectures more than 20 years earlier. The poster, shioyama, pushed back by emphasizing interaction nets as a fundamentally different paradigm, while acknowledging uncertainty about whether Frostbite delivers the claimed performance.

<details><summary>References</summary>
<ul>
<li><a href="https://architectlabs.com/blog/frostbite">Introducing Frostbite : A new CPU architecture ... | Architect Labs</a></li>
<li><a href="https://news.ycombinator.com/item?id=50572503">Frostbite : A new CPU architecture discovered, designed and...</a></li>
<li><a href="https://architectlabs.com/blog/frostbite">Introducing Frostbite: A new CPU architecture discovered ...</a></li>
<li><a href="https://www.notebookcheck.net/AMD-and-Intel-move-over-AI-designed-an-all-new-CPU-and-claims-it-is-4-6x-more-efficient.1455225.0.html">AMD and Intel, move over: AI designed an all-new CPU — and ...</a></li>
<li><a href="https://letsdatascience.com/news/architect-labs-unveils-frostbite-an-ai-designed-cpu-architec-88f8acbd">Architect Labs unveils Frostbite, an AI-designed CPU architecture</a></li>

</ul>
</details>

**Tags**: `#AI-designed hardware`, `#CPU architecture`, `#interaction nets`, `#hardware verification`, `#Hacker News discussion`

---

<a id="item-tech-news-8"></a>
### [Ravi Vakil Announces Hurried Draft of Proposed GRH Proof](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil announced a hurried public draft of Alessandro Masullo&\#x27;s proposed proof of the Generalized Riemann Hypothesis. Vakil said Brian Conrad has examined the work closely for months and provided extensive feedback that is being incorporated, and that it is &quot;so far looking good.&quot; Vakil emphasized that the work is entirely human, with no AI, and said the original plan was to spend a year polishing the writing at Stanford before announcing it; the draft is being released now instead. The announcement provides no technical details or independent verification.

rss · Simon Willison · Nov 20, 19:21

**「Background」** The Generalized Riemann Hypothesis extends the Riemann hypothesis—the conjecture that nontrivial zeros of the Riemann zeta function lie on the critical line—to a broader class of L-functions. Scientific American described the episode as part of dueling public claims of Riemann hypothesis proofs.

<details><summary>References</summary>
<ul>
<li>Dueling claims of Riemann hypothesis proofs emerge - Scientific American</li>

</ul>
</details>

**Tags**: `#mathematics`, `#Generalized Riemann Hypothesis`, `#research announcement`, `#verification`, `#number theory`

---

<a id="item-tech-news-9"></a>
### [Gemini can operate Mac apps for US paid users](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 7.0/10

Google Gemini has added a Mac computer-use feature that can click, type, navigate menus, and fill forms on the user&\#x27;s behalf. It is available to US users of Gemini for Mac with Google AI Plus, Pro, or Ultra subscriptions. Gemini runs in a separate background window while the user continues using the main screen and cursor; users can restrict which apps it can access, monitor its actions in real time, pause it at any time, and approve critical actions. The brief report did not detail supported apps, error rates, or a wider rollout timeline.

telegram · zaihuapd · Nov 20, 02:51

**「Background」** A computer-use agent operates software through the same graphical interface as a person—clicking, typing, and navigating menus—rather than through an app&\#x27;s API, so it can work in applications without built-in automation. For this Mac rollout, Google requires an Apple Silicon Mac and limits initial availability to English-language users in the U.S. on AI Plus, Pro, or Ultra plans, Android Authority reports.

**「Impact」** Eligible US subscribers can delegate repetitive multi-step Mac workflows—including clicking, typing, and form entry across local files, desktop apps, and the web—while continuing other work in a separate background window. They still need to set app-access restrictions and use pause and approval controls for sensitive steps; Mac users outside the US or on ineligible plans cannot use the feature.

<details><summary>References</summary>
<ul>
<li><a href="https://www.androidauthority.com/gemini-mac-computer-use-3737396/">Gemini for Mac adds computer use to control desktop apps</a></li>
<li><a href="https://blog.google/innovation-and-ai/products/gemini-app/computer-use-mac/">Automate Mac tasks with Gemini computer use</a></li>

</ul>
</details>

**Tags**: `#Google Gemini`, `#AI agents`, `#macOS`, `#computer use`, `#human oversight`

---

<a id="item-tech-news-10"></a>
### [UK tribunal sides with Apple on public hearings for secret backdoor demand](https://appleinsider.com/articles/26/11/19/uk-cant-hide-that-it-tried-ordering-apple-to-allow-access-to-user-data) ⭐️ 7.0/10

The UK Investigatory Powers Tribunal reportedly sided with Apple and refused to let the Home Office keep secret an order seeking access to encrypted iPhone data, with most of the case to be heard in public. The Home Office confirmed it had issued a Technical Capability Notice \(TCN\) and said the measure was intended to bring criminals to justice; the tribunal found its national-security justification &quot;unrealistic.&quot;

telegram · zaihuapd · Nov 20, 04:13

**「Background」** TechCrunch reported that Apple had been legally barred from disclosing the technical capability notice even after details of the order leaked. Reporting also indicated that the notice’s potential scope extended beyond UK users to Apple customers worldwide.

**「Impact」** The ruling means the Home Office&\#x27;s demand and its rationale will face public proceedings rather than the secrecy the government sought. The supplied report does not say whether the underlying access demand has been withdrawn or altered.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/19/u-k-government-forced-to-disclose-secret-apple-backdoor-order/">UK government forced to disclose secret Apple ... | TechCrunch</a></li>
<li><a href="https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/">UK Government Forced to Admit It Issued Apple a Secret Encryption...</a></li>

</ul>
</details>

**Tags**: `#encryption`, `#privacy`, `#Apple`, `#UK government`, `#surveillance`

---

<a id="item-tech-news-11"></a>
### [House panel releases data on 879,868 approved AI chip exports to China](https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china) ⭐️ 7.0/10

Documents released by the U.S. House Foreign Affairs Committee show that the United States approved exports of 879,868 AI chips to China from December 2025 through May 2026, against 3.444 million chips requested. The approvals covered Nvidia H200 and AMD MI325X chips and included 150,000 each for Tencent and ByteDance, 75,000 each for Alibaba, Kuaishou and Didi, and volumes for Baidu, JD.com and miHoYo, among others. The committee&\#x27;s release also notes that Alibaba, Tencent, Baidu and BYD appear on a U.S. list of companies alleged to have Chinese military links, prompting congressional questions about the reviews. It cautions that 21 approved licenses reviewed as of May 11 were all marked as not yet shipped, so approved volumes are not actual deliveries.

telegram · zaihuapd · Nov 20, 04:25

**「Background」** The release was made by House Foreign Affairs Committee Chairman Brian Mast, who said he was exercising his authority under the Export Control Reform Act to publicly reveal export-control license application information for NVIDIA and AMD AI chips destined for China.

**「Impact」** For the named Chinese buyers, the approved quantities are license headroom rather than available compute: the reviewed licenses were marked unshipped as of May 11, so capacity planning must wait for actual export and delivery.

<details><summary>References</summary>
<ul>
<li><a href="https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china">Chairman Brian Mast Exercises Legislative Authority to Publicly...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#Nvidia`, `#US-China tech policy`, `#semiconductors`

---

<a id="item-tech-news-12"></a>
### [Meta employees report Muse AI mixing accounts and exposing private data](https://techcrunch.com/2026/11/19/metas-ai-agent-muse-is-mixing-up-conversations-and-exposing-private-data-report-says/) ⭐️ 7.0/10

Meta employees reported that the company&\#x27;s AI assistant Muse mixed conversations across accounts and displayed other people&\#x27;s private information, according to Reuters&\#x27; account of internal Meta posts. The examples included a Muse message inserted into a weather chat that listed a Capital One balance of $2,722.58 and a Charles Schwab balance of $5,899.57, as well as an employee being reminded on her personal phone to reply to her sister&\#x27;s Signal message despite saying she had not authorized access to other apps. The report is based on employee posts and did not include an official Meta response or a technical explanation of the cause.

telegram · zaihuapd · Nov 20, 05:10

**「Context」** Muse is Meta’s AI agent, which Reuters reported has been downloaded more than 10 million times and which Meta expects to generate billions. The account-mixing reports emerged in internal posts described in a Reuters investigation published Nov. 18, which said unbidden actions by Muse had already prompted employee concerns.

**「Impact」** For the employees affected, and for any Muse user who links financial or messaging accounts, the reported behavior puts account isolation and per-app permissions at the center of the risk: balances and Signal messages appeared where they did not belong and, in one case, without the employee&\#x27;s authorization. Until Meta explains the scope and cause, affected users would have a concrete reason to review or revoke Muse&\#x27;s access to sensitive accounts and messaging apps.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/investigations/meta-bets-big-muse-ai-agent-early-safety-mishaps-surface-2026-11-18/">As Meta bets big on Muse AI agent, early safety mishaps ...</a></li>

</ul>
</details>

**Tags**: `#AI privacy`, `#AI agents`, `#Meta`, `#data leakage`, `#security`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Serving a Looped Model: Inkling 2 Mini on vLLM](https://vllm.ai/blog/2026-11-20-inkling2-mini) ⭐️ 8.0/10

rss · vLLM Blog · Nov 20, 00:00

**「Background」** Inkling 2 Mini is a 26B-total, 3.5B-active multimodal MoE whose middle 12 core layers run three passes with shared weights, each pass carrying its own KV and convolution caches and reading gated messages from the previous pass. Serving it therefore meant handling 24 layers but 48 KV caches and 48 conv-state caches without adding new cache-management machinery.

**「Solution」** vLLM registers each extra pass of a core layer as its own attention layer, so the existing KV cache manager and prefix caching treat per-pass caches like ordinary ones. It fuses the four message reads and four controllers per later-pass core layer: one attention-residual kernel reads all messages, controller weights are stacked into batched GEMMs, one Triton kernel computes the controllers&\#x27; RMS normalizations, and another fuses the gated merge with the sublayer RMSNorm; the merge runs in FP32 without FMA contraction to match the reference. vLLM also generalizes Inkling 2 Small&\#x27;s fused all-reduce, short-convolution, residual, attention-residual and RMSNorm kernels from hidden size 4,608 to 2,304, adding a mode that returns the FP32 mix for later-pass message merges, and uses them at every tensor-parallel size. For the variable-loop research checkpoint, startup overrides choose the number of passes and whether passes share one KV cache; on one GB200 at 4K context and forward-only decode, batch-1 latency rose from 1.51 ms with one pass to 2.67 ms with two and 3.85 ms with three, while KV capacity fell from 352K to 233K and 175K tokens. At three passes, sharing the KV cache measured 3.86 ms at batch 1 and 8.10 ms at batch 32 versus 3.85 ms and 8.11 ms unshared, freeing less memory than dropping a pass because conv states remain per pass. The author reports that hidden states differ from the reference by roughly as much as the reference&\#x27;s own attention paths differ, with bitwise-matching MoE outputs given the same inputs.

**「Takeaway」** The author&\#x27;s thesis is that looped models can be served by extending existing cache and kernel abstractions rather than replacing them, with per-pass state treated as ordinary cache layers and message handling fused into the sublayer path. The variable-loop measurements make the tradeoff concrete: extra passes buy quality with latency and memory, and cache sharing is not equivalent to removing a pass.

**Tags**: `#looped models`, `#vLLM`, `#KV cache`, `#MoE inference`, `#kernel fusion`

---

<a id="item-tech-blog-2"></a>
### [Why Caching Visible LLM Output Barely Helps](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference already relies on input caching in the KV cache to avoid recomputing the full conversation on every message. Because output tokens are more expensive to generate than input tokens are to ingest, it is tempting to cache or suppress repeated model output as well.

**「Solution」** Sean Goedecke considers cases where agents repeat code snippets, evidence documents, or sample outputs: a model could be prompted or fine-tuned to emit references such as file and line ranges, which the harness then expands for the user. But this only optimizes visible output. From his own agent histories, he estimates visible output is about 6% of output tokens, with 50% reasoning and 44% tool calls. Under Amdahl&\#x27;s law, even eliminating two-thirds of visible output would cut only about 4% of total output tokens. He is only moderately confident that frontier models rarely repeat themselves in hidden reasoning, basing that view on open models and general principles. The larger target is the invisible 94%, which depends on model intelligence: he notes that a model 5x more expensive per token can be cheaper overall if it needs 6x fewer tokens.

**「Takeaway」** Goedecke&\#x27;s conclusion is that output caching attacks too small a slice of LLM token use to matter much. The real leverage lies in reducing reasoning and tool-call tokens, which makes a smarter, higher-priced model potentially the cheaper choice.

**Tags**: `#LLM inference`, `#output caching`, `#Amdahl&\#x27;s law`, `#AI agents`, `#token economics`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. companies shift from buybacks to net equity issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. companies have switched from net share buybacks to net equity issuance, with net new shares equal to 3.1% of total market capitalization as of late last week, according to an Acadian Asset Management analysis.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** For years, buybacks reduced the number of shares available to trade and lifted earnings per share by shrinking the denominator; Acadian says that repurchase era has ended, and the added supply is a potential headwind for the four-year bull market.

**Tags**: `#equity issuance`, `#buybacks`, `#bull market`, `#AI capital raising`, `#IPOs`

---