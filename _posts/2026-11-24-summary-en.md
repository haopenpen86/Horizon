---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 34 items, 15 important content pieces were selected

---

**Technology News**
1. [Check Point management servers targeted by campaign that forges admin sessions via V8 PRNG](#item-tech-news-1) ⭐️ 8.0/10
2. [Quad9 Pulls DNS Service From France Over Legal Constraints](#item-tech-news-2) ⭐️ 8.0/10
3. [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](#item-tech-news-3) ⭐️ 8.0/10
4. [VMware vCenter vmdir auth bypass CVE-2026-123903 patched after zero-day use](#item-tech-news-4) ⭐️ 8.0/10
5. [Ternary Bonsai 2.5 27B runs at ~22–30 tok/s on 24GB Macs, users report](#item-tech-news-5) ⭐️ 7.0/10
6. [Hacker News Debates Deterministic VMs for Multithreaded Profiling](#item-tech-news-6) ⭐️ 7.0/10
7. [Simon Willison names three LLM inflection points in twelve months](#item-tech-news-7) ⭐️ 7.0/10
8. [Z.ai&\#x27;s GLM-5.4 debuts looped transformer, limited to Coding Plan](#item-tech-news-8) ⭐️ 7.0/10
9. [Singapore&\#x27;s Wong Says It Won&\#x27;t Be a Conduit for Evading US Chip Controls](#item-tech-news-9) ⭐️ 7.0/10
10. [Novartis CEO: AI won&\#x27;t cure cancer in a decade, may cut R&amp;D 4 years](#item-tech-news-10) ⭐️ 7.0/10

**Technology Blog**
1. [ERNIE 5.5 Flash Preview Gets Day-0 vLLM Plugin Support](#item-tech-blog-1) ⭐️ 7.0/10
2. [vLLM-GR Adds Beam-Search Serving for Generative Recommendation](#item-tech-blog-2) ⭐️ 6.0/10

**Financial News**
1. [Utah Drops Criminal Charges Against Kalshi After Platform Suspends State Operations](#item-finance-news-1) ⭐️ 7.0/10
2. [New York Fed&\#x27;s Williams says more work needed to bring inflation to 2%](#item-finance-news-2) ⭐️ 7.0/10
3. [Xiaomi Q3 Adjusted Net Profit Falls 56.8% as EV Deliveries Top 100,000](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Check Point management servers targeted by campaign that forges admin sessions via V8 PRNG](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 8.0/10

An active intrusion campaign is exploiting Check Point security management servers, according to a GreyNoise report discussed on Hacker News. Details quoted from the report in the thread describe the actor scanning and then attacking an HFS server starting 2026-10-02 13:17:45 UTC: each POST to the loginSrp1 endpoint returned a signed session cookie whose &quot;sid&quot; value came from JavaScript&\#x27;s Math.random\(\), and by performing several logins in succession the actor collected enough output to reconstruct the internal state of the Node.js V8 PRNG, recover the HFS session-cookie signing key, and forge a signed admin session cookie. The supplied material does not establish how initial access was obtained; one commenter notes that the link between multiple Check Point customers suggests CVE-2026-16232 was the vector, but that is presented as an inference rather than a confirmed finding.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Background」** Check Point confirmed active exploitation of CVE-2026-16232 in July 2026; the vulnerability is an authentication bypass in the SmartConsole login process that allows an unauthenticated remote attacker to bypass authentication. That earlier management-plane flaw provides context for the current intrusion campaign against Check Point security management servers.

**「Impact」** Because the technique turns repeated ordinary logins into a signing-key recovery and admin session forgery, exposure of the management interface is the operative risk: commenters pressing on whether every affected organization had its Check Point Security Management Server reachable from the internet point to that exposure as the condition the campaign depends on, and operators should treat internet-facing management servers accordingly.

**「Community discussion」** Commenters split on blame, with one arguing that Math.random should itself be made secure rather than leaving hundreds of applications to use it correctly, while others focused on the unresolved initial-access question and whether the victims had internet-exposed management servers. A separate comment predicted that less sophisticated criminals will increasingly use LLMs and compute to attack any online service, including critical infrastructure — a forecast, not a reported finding.

<details><summary>References</summary>
<ul>
<li>CVE-2026-16232: Active Exploitation Requires Immediate Management Plane Remediation - Check Point CheckMates</li>
<li>CVE-2026-16232 - CVE Record</li>
<li>CVE-2026-16232: Check Point SmartConsole Authentication Bypass</li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#Check Point`, `#intrusion campaign`, `#PRNG`, `#session forgery`

---

<a id="item-tech-news-2"></a>
### [Quad9 Pulls DNS Service From France Over Legal Constraints](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 8.0/10

Quad9 has deactivated its DNS service for users in France, citing French legal constraints. As of Nov. 24, 2026, a community test of 9.9.9.9 returned REFUSED with EDNS Extended DNS Error 18 \(Prohibited\) and the message “Service unavailable due to French legal constraints.” The withdrawal affects French networks and devices that rely on Quad9 for domain resolution.

hackernews · farrokhi · Nov 24, 08:33 · [Discussion](https://news.ycombinator.com/item?id=50625384)

**「Background」** Quad9 is a public recursive DNS resolver: it translates domain names into IP addresses for users rather than hosting content itself. Its France shutdown followed a demand from beIN Sports, a sports rightsholder, that Quad9 block domains it says are tied to piracy streaming; rather than comply, Quad9 disabled French service on November 24, 2026, as its notice states.

**「Impact」** French networks or devices that hard-code 9.9.9.9 must be reconfigured to use another resolver or a forwarding proxy, because direct queries to Quad9 are being refused. This includes router, operating-system, and application DNS settings that pin Quad9.

**「Community Discussion」** One commenter responded by publishing a caching DNS proxy for French users that forwards to Quad9 over DoH, DoT, and Do53 for IPv4 and IPv6, with separate filtered and unfiltered endpoints. Another commenter questioned why users need public resolvers at all, saying self-hosted Unbound with Pi-hole works well at home and asking whether it scales.

<details><summary>References</summary>
<ul>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad 9 Service Deactivation in France | Quad 9</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad 9 Is Leaving France : Why DNS Resolvers Are... | Tech Stackups</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet infrastructure`, `#privacy`, `#France`, `#legal/policy`

---

<a id="item-tech-news-3"></a>
### [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

Baidu has open-sourced ERNIE 5.5 Flash Preview, publishing weights under Apache 2.0 on Hugging Face and ModelScope. The mixture-of-experts model has 280B total parameters, 14B active per token, and a 1M-token context window; Baidu says it is the first post-trained model built on ERNIE 5.5 Flash Base. It can be deployed and fine-tuned with vLLM or SGLang. A circulating benchmark chart reports 46.5 on Terminal-Bench 4.0 and 71.2 on DeepSWE v1.1, but Baidu has not said whether those results were independently verified.

telegram · zaihuapd · Nov 24, 07:32

**「Background」** A mixture-of-experts \(MoE\) model divides its parameters into specialized experts and activates only a subset for each token; in this release, 14B of the 280B total parameters are active per token, reducing inference compute compared with a dense model of the same total size. Baidu describes ERNIE 5.5 Flash Preview as the first post-trained model derived from ERNIE 5.5 Flash Base.

**「Impact」** Teams can self-host and fine-tune the weights through vLLM or SGLang and redistribute modified versions under Apache 2.0; those considering deployment must account for the full 280B-parameter model even though only 14B parameters are active per token.

**Tags**: `#open-source-llm`, `#baidu-ernie`, `#mixture-of-experts`, `#model-release`, `#apache-2.0`

---

<a id="item-tech-news-4"></a>
### [VMware vCenter vmdir auth bypass CVE-2026-123903 patched after zero-day use](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom released patches covering 23 vulnerabilities across its VMware product line, centered on CVE-2026-123903, a 9.8-severity authentication bypass in vCenter&\#x27;s directory service \(vmdir\). According to the report, anyone able to reach vCenter over the network could bypass authentication and enter the system directly. The same report states the flaw was exploited as a zero-day just days before the patches were released. The source is a brief aggregation and does not list affected vCenter versions, the exact exploitation mechanism, or indicators of compromise.

telegram · zaihuapd · Nov 24, 14:50

**「Background」** VMware Directory Service \(vmdir\) is the vCenter directory service at the center of this authentication bypass, so the flaw affects vCenter&\#x27;s management plane rather than a peripheral component. A GitHub CVE page for CVE-2026-123903 lists vCenter 8.0 U3k and earlier, as well as 9.0.x and 9.1.x below the fixed builds, as affected.

**「Impact」** Because the bypass requires only network reachability rather than credentials, administrators should treat any internet-exposed or broadly reachable vCenter management interface as an immediate exposure and prioritize applying Broadcom&\#x27;s update; the source does not specify workarounds or confirm which versions are affected, so version and mitigation details must be checked against the vendor advisory before relying on them.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/dinosn/CVE-2026-123903">dinosn/ CVE - 2026 - 123903 : CVE - 2026 - 123903 : VMware vCenter vmdir ...</a></li>

</ul>
</details>

**Tags**: `#vCenter`, `#VMware`, `#vulnerability`, `#zero-day`, `#security`

---

<a id="item-tech-news-5"></a>
### [Ternary Bonsai 2.5 27B runs at ~22–30 tok/s on 24GB Macs, users report](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B is a newly announced ternary-quantized model, available in a Q2 GGUF, that community users report running at roughly 22–30 tokens/s with up to 128k context on 24GB Apple Silicon Macs. One Mac Mini M5 Pro test measured 22.3 tok/s generation, 222.9 tok/s prompt processing, and a 2.12 s first token; another user reported similar speeds through Unsloth Studio and described its agentic calls as solid. The claimed frontier-level SWE-bench Verified performance has not been independently verified, and commenters are unsure how much reflects genuine capability versus benchmark-specific tuning. No official source content was available for this item beyond the announcement and user reports.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Background」** Ternary quantization stores each model weight at one of three discrete levels instead of full precision; ternary refers to a base-3 system, whose digits can be 0, 1, and 2 or, in balanced form, −1, 0, and 1. Bonsai 2.5 27B applies this low-bit approach to a 27-billion-parameter model, which is why community reports focus on running it within consumer memory.

**「Impact」** For local-inference users, the reported combination of 128k context within 24GB of memory and 20–30 tok/s generation makes batch agentic coding on consumer Macs plausible, though these figures come from individual user tests rather than vendor-published benchmarks. One commenter also raises whether ternary weights have hardware acceleration beyond FPGAs, an open compatibility question for anyone expecting the format to be accelerated on existing GPUs or NPUs.

**「Community discussion」** Commenters are skeptical of the SWE-bench Verified comparison: nik\_s says the score is reported to match Opus 4.6 and wonders how much reflects &quot;benchmaxxing,&quot; benchmark drift, or genuine progress in small models, while hatthew asks for direct comparisons against equivalently small Q1/Q2 quants such as Qwen3.8. syntaxing reports that in practice the model outperformed a Q4 Inkling 2 mini on agentic calls, which is one user&\#x27;s experience rather than a controlled benchmark.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Ternary_numeral_system">Ternary numeral system - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#ternary quantization`, `#small language models`, `#local inference`, `#SWE-bench`, `#GGUF`

---

<a id="item-tech-news-6"></a>
### [Hacker News Debates Deterministic VMs for Multithreaded Profiling](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

A blog post arguing that deterministic virtual machines can support Brendan Gregg-style performance analysis has drawn interest from performance engineers, along with scrutiny of how the method handles multithreaded and asynchronous systems. In the Hacker News thread, commenters focused on a claimed single-threaded VM design, the difficulty of inferring cross-thread dependencies from flame graphs, comparisons with rr-style record/replay, and whether the approach can locate critical paths in coroutine or fiber-based async code. The article body was not included in the supplied material, so the VM&\#x27;s specific capabilities and measured results remain unverified.

hackernews · kqr · Nov 24, 10:50 · [Discussion](https://news.ycombinator.com/item?id=50626413)

**「Background」** The linked post is a practitioner&\#x27;s reflection on Brendan Gregg-style profiling; flame graphs are the thread&\#x27;s reference point for visualizing sampled stack traces. The author describes Rewind, a deterministic VM he has used to find heisenbugs, make profile-guided optimization reproducible, and make Nix builds bit-reproducible \(tool-1-1\), which supplies the record/replay premise for the discussion of multithreaded and async workloads.

**「Impact」** For teams profiling high-throughput multithreaded or async services, the thread raises a practical compatibility concern: a deterministic VM that serializes execution may not reproduce the contention and cross-thread timing that dominate such systems, and async critical paths may still require framework-level instrumentation to connect continuations to a request.

**「Community discussion」** Commenters were skeptical that flame graphs alone can explain multithreaded behavior, with one saying cross-thread dependencies are hard to infer, while another pointed to Nvidia&\#x27;s &quot;speed of light&quot; ceiling analysis as a way to reason about absolute performance limits. Questions about async critical paths and rr-style record/replay remained open in the supplied discussion.

<details><summary>References</summary>
<ul>
<li><a href="https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg">Worshipping at the altar of Brendan Gregg - fzakaria .com</a></li>

</ul>
</details>

**Tags**: `#performance-analysis`, `#profiling`, `#flame-graphs`, `#deterministic-vm`, `#record-replay`

---

<a id="item-tech-news-7"></a>
### [Simon Willison names three LLM inflection points in twelve months](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

In a November 24 retrospective, Simon Willison argues that LLM coding agents crossed three practical inflection points in twelve months. He dates the first to November 2025, when Anthropic released Claude Opus 4.5 and OpenAI released GPT-5.1 Instant, GPT-5.1 Thinking, GPT-5.1-Codex and GPT-5.1-Codex-Max; he says these made coding agents reliable enough that their default results were usually right for his daily work. The second is the June/July 2026 arrival of “Fable class” models—including Claude Fable 5, a defanged Claude Mythos that the US government placed under export controls before it returned on July 1—which he says can solve goals by using tools and acting proactively. The third is September/October 2026 progress in 3D modeling and game development, including Claude Opus 5.5 \(released September 22\), GPT-5.6 Sol, GPT-6 Astra and Gemini 4; the supplied excerpt ends before Willison resolves whether Fable 5.2 is another inflection point.

rss · Simon Willison · Nov 24, 23:02

**「Background」** Claude Code launched in February 2025 alongside Claude 3.7 Sonnet, roughly nine months before Claude Opus 4.5 arrived. In Willison&\#x27;s account, the earlier coding agent required enough correction that it did not feel like a clear accelerant, which is the baseline against which he measures the Opus 4.5 shift.

**「Impact」** For developers, Willison’s account makes tool use and sustained autonomy—not just single-turn answer quality—the relevant test: he describes Fable-class models spinning up their own screenshot tooling and triangulating a beep with five microphones. It also implies that model selection can hinge on whether a model’s default output is reliable enough to avoid constant correction, the threshold he says Opus 4.5 crossed.

**Tags**: `#LLM coding agents`, `#AI engineering`, `#Claude Opus 4.5`, `#LLM capabilities`, `#retrospective`

---

<a id="item-tech-news-8"></a>
### [Z.ai&\#x27;s GLM-5.4 debuts looped transformer, limited to Coding Plan](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai has released GLM-5.4, its first model built on a looped transformer architecture, in which a group of weight-shared layers runs for multiple iterations per forward pass, deepening the network without increasing the parameter count. The model is not yet available as open weights — Z.ai says it will open-source them after &quot;necessary safety hardening&quot; — and it currently cannot be reached through the regular API, only through the Coding Plan subscription, whose key works with the shared OpenAI-compatible Responses API at https://api.z.ai/api/v1. Z.ai published no benchmark numbers, and Simon Willison&\#x27;s hands-on check was limited to his pelican SVG test, which he called &quot;not great&quot; at max effort and roughly comparable in quality to GLM-5.3. The release follows Thinking Machines Lab&\#x27;s Inkling 2 Mini on November 20, which also uses a looped design, running its middle layers three times for every token.

rss · Simon Willison · Nov 23, 23:40

**「Background」** Standard transformers run each layer once per forward pass. A looped transformer instead reuses a group of weight-shared layers for several iterations, refining hidden states and gaining effective depth without increasing the parameter count. The same approach appeared earlier that week in Thinking Machines Lab&\#x27;s Inkling 2 Mini, which runs its middle layers three times per token.

**「Access and compatibility」** Developers who want to evaluate GLM-5.4 now must go through Z.ai&\#x27;s Coding Plan subscription, because the model is not yet reachable via the regular API; Simon Willison found the coding-plan key works against the same OpenAI-compatible Responses endpoint at https://api.z.ai/api/v1. Self-hosting is not an option yet either, since Z.ai says it will release weights only after &quot;necessary safety hardening,&quot; and tooling lags the release: the existing llm-zai plugin does not yet support 5.4, which led Willison to publish a stopgap llm-glm plugin he expects to retire once the older one catches up.

**Tags**: `#LLM architecture`, `#looped transformers`, `#GLM-5.4`, `#Z.ai`, `#AI model release`

---

<a id="item-tech-news-9"></a>
### [Singapore&\#x27;s Wong Says It Won&\#x27;t Be a Conduit for Evading US Chip Controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said the country will not be used as a conduit for companies seeking to evade US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. The statement followed the US Commerce Department&\#x27;s addition of Megaspeed and six other Southeast Asian firms to a trade blacklist the previous day; the Federal Register cited a significant risk that they would divert advanced computing products to unauthorized users, and the listings include affiliates in Malaysia and Thailand. Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also on the list; Alibaba said it had never diverted controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** Megaspeed, the Singapore-based firm at the center of the inquiry, bought billions of dollars of Nvidia hardware for data centers across Southeast Asia, including Malaysia, and has been under US investigation since 2024 over suspicions it supplied those chips to China without US authorization, according to Wikipedia&\#x27;s account of the company. Megaspeed says it takes its obligations under US export-control law &quot;extremely seriously&quot; and is committed to working constructively and transparently with the US government.

**「Impact」** The blacklisting creates a direct compliance hurdle for Megaspeed, the six other named firms, and their Malaysian and Thai affiliates when sourcing US-controlled advanced computing products, while Singapore&\#x27;s investigation puts Nvidia chip transactions routed through the city-state under closer scrutiny.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Megaspeed">Megaspeed - Wikipedia</a></li>
<li><a href="https://www.megaspeed.ai/">MegaSpeed .Ai</a></li>

</ul>
</details>

**Tags**: `#semiconductor export controls`, `#Singapore`, `#Nvidia`, `#AI chips`, `#trade blacklist`

---

<a id="item-tech-news-10"></a>
### [Novartis CEO: AI won&\#x27;t cure cancer in a decade, may cut R&amp;D 4 years](https://www.ft.com/content/1e5a9d70-221d-461d-ae03-dc235b1db340) ⭐️ 7.0/10

Novartis CEO Vas Narasimhan, who also sits on Anthropic&\#x27;s board, said AI will not cure cancer in the next 5 to 10 years, and that merely compressing average drug development from 12 years to 8 years would take roughly a decade. The clearest gains, he said, come in preclinical discovery — a stage that usually takes about four years and could be shortened by up to two — while he expects the success rate for programs entering human trials to rise from 8% to 12%. Animal testing and clinical trials cannot be skipped. Narasimhan argued the tech industry applies an &quot;engineering mindset&quot; to medicine even though humans understand only about 5% of what happens in the body, far less than in programming or language. His estimate contrasts with Anthropic&\#x27;s CEO, who has said diseases such as cancer will become &quot;relics of history&quot; within a decade; Eli Lilly&\#x27;s CEO has also publicly expressed doubt.

telegram · zaihuapd · Nov 24, 08:54

**「Why this estimate matters」** Drug development conventionally takes about 12 years from early discovery to approval, and only roughly 8% of programs that enter human testing succeed — the baseline Narasimhan is measuring AI against. His skepticism is aimed at predictions from AI leaders, including Anthropic CEO Dario Amodei, that AI could reduce cancer and other diseases to historical artifacts within a decade, a claim Eli Lilly&\#x27;s CEO has also publicly doubted.

**「What this means for drug developers」** For pharma R&amp;D planners, Vasant Narasimhan&\#x27;s estimates put AI&\#x27;s near-term payoff almost entirely in preclinical discovery — shaving up to two years off a roughly four-year pre-human phase — while animal studies and clinical trials still cannot be skipped. Any timeline or budget model that assumes AI compresses the trial stage, or that banks on the projected rise in human-trial success from 8% to 12% before it is realized, is running ahead of what Novartis says it has achieved.

**Tags**: `#AI drug discovery`, `#pharmaceutical R&amp;D`, `#AI hype`, `#Novartis`, `#healthcare AI`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash Preview Gets Day-0 vLLM Plugin Support](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** Baidu&\#x27;s ERNIE team and the vLLM team released day-0 support for ERNIE 5.5 Flash Preview, a sparse mixture-of-experts model with 280B total parameters, 14B activated per token, and a 1M-token context. Rather than maintaining a fork or a model-specific container, they packaged the model code and optimizations as a standalone plugin that runs with the official vllm==0.32.0 wheel.

**「Solution」** The vLLM-ERNIE plugin registers ERNIE architectures through vLLM&\#x27;s vllm.general\_plugins entrypoint and imports the model code lazily, so environments serving other models incur no overhead. For inference, the authors fuse ERNIE&\#x27;s new attention, routing, and output-head operations, pre-folding fixed mixing weights and concatenating router and gate weights at load time while keeping outputs numerically aligned; they report 1.55x to 6.53x per-kernel speedups over naive implementations. FlashIndexer adds a small router that selects a few sparse indexer heads per token and pre-filters low-scoring candidates, which the authors say yields a 1.4x speedup at 1M context without changing downstream sparse attention. The default checkpoint stores routed experts in MXFP4 using W4A8 quantization-aware training, with an FP8 KV cache and FP4 indexer, while a bundled three-layer DSpark draft model proposes up to seven tokens per step and reportedly exceeds 4.0 mean acceptance length on coding and agent workloads. vLLM features such as prefix caching, chunked prefill, CUDA graphs, speculative decoding, and PD disaggregation work without ERNIE-specific code.

**「Takeaway」** The authors argue that a lazy-loaded plugin lets model-specific kernels and features ship on the model&\#x27;s schedule while reusing vLLM&\#x27;s serving stack and upstream improvements. The performance claims are team-reported and are not accompanied by independent benchmark methodology.

**Tags**: `#vLLM`, `#ERNIE`, `#inference optimization`, `#kernel fusion`, `#speculative decoding`

---

<a id="item-tech-blog-2"></a>
### [vLLM-GR Adds Beam-Search Serving for Generative Recommendation](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 6.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** Generative recommendation models such as OneRec turn a viewer’s history into semantic IDs for candidate items, and a serving system must produce a usable candidate set within one request’s latency budget. That requires exploring many short generation paths rather than returning a single sequence.

**「Solution」** vLLM-GR is an open-source framework built on vLLM that adds a beam session spanning the whole search to vLLM’s scheduler, model execution, and paged KV cache. EngineCore owns each session, the scheduler dispatches prefill and decode stages, and beam selection records each surviving path’s score and parent so the next decode can read the right KV state. Users submit a complete search through Python, OpenAI-compatible HTTP, or gRPC; search can cover the full vocabulary or be constrained to catalog semantic IDs, with per-stage beam widths and per-parent limits. Prompt KV is shared across beams, and the host prepares the next stage while the accelerator runs the current one. The author reports P99 results for OneRec-1.7B across NVIDIA GPUs and Ascend NPUs: at beam width 256 and batch sizes 4 and 8, vLLM-GR had the lowest P99 among the backends shown on all six accelerators, including 369.4 ms versus 1,280.1 ms for SGLang and 428.1 ms for NVIDIA SID-GR on H20 at batch size 8. At batch size 1 on RTX PRO 6000, however, NVIDIA SID-GR reported 28.25 ms versus 29.21 ms. The post cautions that these charts come from separate runs with different timing definitions, sample counts, and backend settings.

**「Takeaway」** The launch argues that extending a general LLM serving stack with session-aware beam search, catalog constraints, and KV reuse can make wide generative-recommendation searches practical across accelerators; its broad latency claims remain qualified by uneven benchmark conditions and a roadmap that still includes ranking, longer histories, and distributed KV cache.

**Tags**: `#generative recommendation`, `#inference serving`, `#beam search`, `#KV cache`, `#vLLM`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Utah Drops Criminal Charges Against Kalshi After Platform Suspends State Operations](https://www.cnbc.com/2026/11/24/utah-drops-charges-against-kalshi-after-it-halted-operations-in-state.html) ⭐️ 7.0/10

Utah dismissed its 14 criminal charges against prediction-market platform Kalshi and co-founders Tarek Mansour and Luana Lopes Lara on Tuesday, a day after the company suspended operations in the state. The dismissal is without prejudice, meaning the state could refile the charges — which alleged illegal gambling — if Kalshi resumes operating in Utah.

rss · CNBC Finance · Nov 24, 20:45

**「Background」** Kalshi is an online prediction market where users trade yes-or-no contracts on the outcome of real-world events, including sports; Utah&\#x27;s case treated that activity as illegal gambling. The Commodity Futures Trading Commission, which considers itself the sole regulator of such markets, sued Utah a day before the state filed its 14 criminal charges.

**「Impact」** Other prediction-market platforms face heightened state scrutiny after Utah’s attorney general warned that companies which “promote, support, or enable gambling” will be held accountable, even as federal jurisdiction over the sector remains disputed.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kalshi">Kalshi - Wikipedia</a></li>
<li><a href="https://v3-kalshi.com/">Kalshi — Regulated Sports and Politics Predictions</a></li>

</ul>
</details>

**Tags**: `#prediction markets`, `#Kalshi`, `#regulation`, `#criminal charges`, `#CFTC`

---

<a id="item-finance-news-2"></a>
### [New York Fed&\#x27;s Williams says more work needed to bring inflation to 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Federal Reserve President John Williams said Monday that policymakers still have &quot;work to do&quot; to bring inflation back to the Fed&\#x27;s 2% goal, and that further interest rate increases can unfold &quot;over time.&quot; Markets are fully pricing a quarter-percentage-point increase at the Federal Open Market Committee&\#x27;s Dec. 8-9 meeting, from the current target range of 3.75%-4%.

rss · CNBC Finance · Nov 24, 13:33

**「Background」** Inflation has stayed well above the Fed&\#x27;s 2% target while the economy keeps growing, and officials have disagreed over how fast to raise rates — Williams has favored a measured approach. He said he expects inflation to move closer to 2% in 2027 and reach the goal the following year, and his remarks are expected to be the last major policy statement from a Fed official before the December decision.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#FOMC`

---

<a id="item-finance-news-3"></a>
### [Xiaomi Q3 Adjusted Net Profit Falls 56.8% as EV Deliveries Top 100,000](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

Xiaomi reported Q3 2026 adjusted net profit of RMB 4.884 billion, down 56.8% year on year but slightly above a RMB 4.746 billion market estimate, while EV deliveries in the quarter reached 100,975.

telegram · zaihuapd · Nov 24, 10:09

**「Background」** The profit drop came as prices for memory chips and other core components rose and Xiaomi increased research spending to RMB 9.24 billion, with gross margin at 20.2%.

**Tags**: `#Xiaomi`, `#quarterly earnings`, `#electric vehicles`, `#smartphones`, `#profitability`

---