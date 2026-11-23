---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 35 items, 12 important content pieces were selected

---

**Technology News**
1. [Nvidia Board Reinstates Jensen Huang as CEO After Abrupt Removal](#item-tech-news-1) ⭐️ 8.0/10
2. [Ladybird browser enters alpha with macOS and Linux builds](#item-tech-news-2) ⭐️ 8.0/10
3. [Nospeaker makes a MacBook trackpad&\#x27;s haptic motor emit sound](#item-tech-news-3) ⭐️ 7.0/10
4. [Zhipu Announces GLM-5.4 Coding Model With Loop Transformer](#item-tech-news-4) ⭐️ 7.0/10
5. [Win4wine runs Windows Explorer as a Linux desktop via Wine](#item-tech-news-5) ⭐️ 7.0/10
6. [Google reportedly built simulated internet to test Chrome AI agent](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows Server 2028 drops WoW64 by default, 32-bit apps need manual add-on](#item-tech-news-7) ⭐️ 7.0/10
8. [Codex2api suspected supply-chain attack exposes secrets via backdoored release](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [NVMe-Only KV Cache Matches DRAM for Agentic Serving](#item-tech-blog-1) ⭐️ 8.0/10
2. [When in Doubt, Flail: Deliberate Experimentation Under Uncertainty](#item-tech-blog-2) ⭐️ 6.0/10
3. [OpenAI’s Perplexity Graph: Visibility and Limits](#item-tech-blog-3) ⭐️ 5.0/10

**Financial News**
1. [Shanghai Metro to adjust fares for first time in 21 years](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Nvidia Board Reinstates Jensen Huang as CEO After Abrupt Removal](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 8.0/10

Nvidia&\#x27;s board reportedly reinstated Jensen Huang as CEO after abruptly removing him. The board said it received input from senior levels of the U.S. government and, based on that input, was confident Huang&\#x27;s reinstatement poses no national security risk. The supplied material does not explain the grounds for the original removal, the timing, or the terms of his return.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Background」** Huang’s exit came earlier in November 2026, after he admitted an affair with a woman alleged to be a Chinese spy; he was also accused of an affair with an Nvidia executive, according to BBC News. The board’s unanimous reinstatement reverses that abrupt departure and restores him as president, CEO, and board director.

**「Export-control scrutiny」** US lawmakers from both parties criticized the reinstatement and said Congress should tighten restrictions on China’s access to Nvidia’s advanced AI chips, putting renewed scrutiny on Nvidia’s export-licensing position. The supplied material reports a legislative call, not an enacted policy change.

**「Community Discussion」** Commenters focused on the board&\#x27;s statement that it received input from senior U.S. government officials, with one calling that the operative part of the announcement and others debating whether the reversal reflected political pressure or a lack of evidence of wrongdoing. Some criticized the board&\#x27;s handling of the removal, and one commenter said the reversal came less than two weeks after the board forced Huang out.

<details><summary>References</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as...</a></li>
<li><a href="https://www.bbc.com/news/live/crd61y5dwqgpt">Jensen Huang reinstated as Nvidia CEO , board says - BBC News</a></li>
<li><a href="https://www.reuters.com/business/lawmakers-criticize-nvidia-decision-reinstate-huang-ceo-2026-11-23/">US lawmakers criticize Nvidia decision to reinstate Huang as CEO</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI hardware`, `#corporate governance`, `#national security`, `#semiconductors`

---

<a id="item-tech-news-2"></a>
### [Ladybird browser enters alpha with macOS and Linux builds](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird, the independent browser with its own HTML, CSS, layout, JavaScript, and WebAssembly implementations, released its first alpha with downloadable builds for macOS and Linux, so users no longer need to compile it themselves. It still uses external HarfBuzz for text shaping, Skia for 2D graphics, ffmpeg for video, and SQLite, and it runs tabs in separate processes. Hands-on testing loaded WebAssembly apps including an ffmpeg video compressor and a Pyodide REPL, but Datasette Lite failed because navigator.serviceWorker.startMessages is not implemented; the project warns that some sites will not work and the browser will sometimes crash.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird is an independent browser project that implements most of its engine in-house, including HTML parsing, CSS, layout, JavaScript and WebAssembly, while relying on external components such as HarfBuzz for text shaping, Skia for 2D graphics, ffmpeg for video and SQLite. It grew out of the more ambitious SerenityOS project, and until this alpha, users had to compile the browser themselves rather than install a packaged build.

**「Impact」** Users can install the alpha on macOS or Linux for general browsing, but should not treat it as a daily-driver replacement yet: incomplete service-worker support breaks some web apps, and the project asks testers to report broken sites and review crash reports before sending them.

**「Community discussion」** Commenters who tried the alpha reported that most sites they tested rendered correctly, including YouTube, Google Maps, and a NoVNC remote console, though some noticed lag and slightly jerky scrolling. One commenter asked what security precautions are appropriate for alpha use, while another welcomed a browser not tied to Google&\#x27;s ads but was nostalgic for the project&\#x27;s earlier approach of building more of its own libraries.

**Tags**: `#browsers`, `#open-source`, `#web-engines`, `#ladybird`, `#software-engineering`

---

<a id="item-tech-news-3"></a>
### [Nospeaker makes a MacBook trackpad&\#x27;s haptic motor emit sound](https://github.com/os6/nospeaker) ⭐️ 7.0/10

Nospeaker, a hobbyist GitHub project by os6, makes a MacBook&\#x27;s trackpad haptic actuator produce audible sound rather than only click feedback. The project links to an X demo of the effect, but the supplied material gives no supported MacBook models, release version, or independent measurements. It is a hardware hack for MacBook owners and tinkerers, not a shipped audio feature or an Apple product.

hackernews · yakkomajuri · Nov 23, 11:31 · [Discussion](https://news.ycombinator.com/item?id=50610318)

**「Background」** MacBook Force Touch trackpads do not physically depress; a haptic actuator beneath the surface simulates the sensation of a click, and Apple exposes programmable patterns for that actuator through its Core Haptics framework. Nospeaker repurposes that same actuator, driving it with waveform data intended for tactile feedback so it produces audible tones instead.

**「Community discussion」** One commenter argued that the more impressive feat is that the unmoving trackpad still feels like a button, while another traced a precedent to music and video generated by a Commodore 1541 floppy drive. A commenter noted that Apple&\#x27;s API represents motor control as a sum of sines and speculated that this may protect the motor, simplify compensation, or suit low-bandwidth USB/HID transport; another compared the project to early PC piezo-speaker music.

<details><summary>References</summary>
<ul>
<li><a href="https://developer.apple.com/documentation/corehaptics">Core Haptics | Apple Developer Documentation</a></li>
<li><a href="https://tech.yahoo.com/ai/apple-intelligence/articles/macbook-modder-turns-apple-force-130000737.html">MacBook modder turns Apple’s Force Touch trackpad into a ...</a></li>

</ul>
</details>

**Tags**: `#hardware-hacking`, `#haptics`, `#apple`, `#macbook`, `#audio`

---

<a id="item-tech-news-4"></a>
### [Zhipu Announces GLM-5.4 Coding Model With Loop Transformer](https://z.ai/blog/glm-5.4) ⭐️ 7.0/10

Zhipu has announced GLM-5.4, a coding-focused model described as its first loop transformer. The supplied announcement provides no benchmark results, parameter counts, or release details, so the model&\#x27;s practical gains remain unverified. In comments, Simon Willison reported that GLM-5.4 was not available through OpenRouter or the regular Z.ai API plan and required Z.ai&\#x27;s Coding Plan, whose API keys otherwise work the same way.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「What a loop transformer is」** A conventional transformer runs each of its layers once per token, a pattern one commenter likened to an unrolled for-loop. Z.ai&\#x27;s loop-transformer design reuses a shared block of layers across multiple iterations: per third-party coverage of the release, 28 of GLM-5.4&\#x27;s 78 layers execute twice, and Z.ai claims this reaches the reasoning level of models with two to three trillion parameters without adding parameters. Rather than training a looped model from scratch, which coverage describes as less efficient, the company adapted an already pretrained GLM-5 base model through continued training.

**「Access and cost considerations」** Developers who want to evaluate GLM-5.4 against existing setups face an access hurdle: one early tester reported the model was unavailable through OpenRouter and the standard Z.ai API plan, and that only keys issued under the Coding Plan reached it, so current integrations may need a plan change before comparison testing. Because a loop transformer reuses the same blocks across iterations rather than adding distinct weights, the architecture shifts cost from parameter storage toward per-token compute, making latency and throughput the practical constraint for coding workloads.

**「Community Discussion」** Commenters praised Zhipu for disclosing more architecture detail than typical Western labs and explained loop transformers as reusing layers to reduce the memory-bandwidth cost of moving weights during inference; one cautioned that problems remain. Another user argued that Chinese models&\#x27; long &quot;marathon thinking&quot; sessions make even simple tasks slow, a trade-off they suspect helps benchmark scores.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/z-ai-debuts-glm-5-4-with-a-novel-looped-transformer-architecture-skipping-ai-benchmarks-entirely/">Z.ai Debuts GLM - 5 . 4 With a Novel Looped Transformer Architecture...</a></li>
<li><a href="https://anyrouter.dev/model/z-ai/glm-5.4">GLM - 5 . 4 · Zhipu AI · pricing &amp; API · AnyRouter</a></li>
<li><a href="https://www.youtube.com/watch?v=HVey00YZ5Xk">GLM - 5 . 4 Is Here: The First Loop Transformer , and What... - YouTube</a></li>
<li><a href="https://www.linkedin.com/posts/amrit-rajeev_openai-ainews-activity-7501377985049120769-Cc5n">OpenAI&#x27;s Looped Transformer : A Pragmatic Tradeoff | LinkedIn</a></li>

</ul>
</details>

**Tags**: `#GLM-5.4`, `#loop transformers`, `#LLM architecture`, `#coding models`, `#inference efficiency`

---

<a id="item-tech-news-5"></a>
### [Win4wine runs Windows Explorer as a Linux desktop via Wine](https://github.com/mikuta0407/win4wine) ⭐️ 7.0/10

Win4wine is an open-source project that runs the Windows Explorer shell as a Linux desktop environment via Wine, rather than only running individual Windows applications inside an existing Linux desktop. Its repository presents this as a way to make the Windows shell the desktop layer, but the supplied material does not specify supported distributions, Windows shell versions, installation details, or release maturity. The project is aimed at Linux users who want a Windows-style shell under Wine; the available evidence does not establish a stable release.

hackernews · hard\_times · Nov 23, 12:28 · [Discussion](https://news.ycombinator.com/item?id=50610743)

**「How it works」** Wine is a compatibility layer that implements Windows APIs on Linux so Windows binaries can run without a full Windows installation. According to its README, win4wine uses a patched Wine to run Windows XP&\#x27;s own explorer.exe as the Linux desktop shell, rather than merely applying a Windows-style theme to a Linux desktop.

**「Impact」** For anyone who tries it, the desktop shell would be provided by Explorer running under Wine, so reliability and security depend on the Windows shell version used; commenters specifically warned that running Windows XP or Windows 7 explorer.exe carries those shells&\#x27; vulnerabilities.

**「Community discussion」** Commenters focused on tradeoffs: one argued that Windows&\#x27; strengths are the NT kernel and driver model rather than the Win32 and UI layer, suggesting the reverse arrangement might be better, while another warned that running Windows XP/7 explorer.exe brings those shells&\#x27; vulnerabilities and also enables tools such as AutoHotkey. A separate commenter pointed to the XPTC XFCE theme as a way to get an XP look without Wine.

<details><summary>References</summary>
<ul>
<li>README.en.md - GitHub</li>

</ul>
</details>

**Tags**: `#Wine`, `#Windows shell`, `#Linux desktop`, `#compatibility layer`, `#open source`

---

<a id="item-tech-news-6"></a>
### [Google reportedly built simulated internet to test Chrome AI agent](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

Google reportedly built an isolated simulated internet, called Mirror Dimension, to test Chrome&\#x27;s AI agent as it opens websites, searches, logs in, adds items to carts and completes tasks. The environment is said to contain thousands of simulated websites, with each engineer testing in a separate isolated setup and more than 1,000 test cases run daily. The stated focus is hardening the agent against prompt injection and other attacks from malicious webpages. The report is a brief secondary account and does not detail how the simulation is built or when, or whether, the agent will ship.

telegram · zaihuapd · Nov 23, 01:30

**「Background」** Browser-use agents navigate pages, click, type, and complete transactions, which creates a prompt-injection surface when a webpage contains instructions the model may follow. Google&\#x27;s security blog describes Mirror Dimension as a synthetic version of the web built to evaluate these agents in realistic online environments without creating real-world security risks, while Wired characterizes it as a sandbox for training Chrome&\#x27;s browsing agents without letting them &quot;go rogue.&quot;

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents: Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘Mirror Dimension’ Internet to Test Its ...</a></li>

</ul>
</details>

**Tags**: `#Chrome AI agent`, `#browser automation`, `#prompt injection`, `#AI security`, `#Google`

---

<a id="item-tech-news-7"></a>
### [Windows Server 2028 drops WoW64 by default, 32-bit apps need manual add-on](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft said at Ignite 2026 that Windows Server 2028 will ship without the WoW64 compatibility subsystem by default, so administrators will need to add 32-bit application support manually. The server release is planned for fall 2027 alongside Windows 11 27H2. WoW64 will be available as a Feature on Demand, typically installed through PowerShell or DISM on Server Core. Microsoft cites a reduced attack surface and blocking 32-bit malware as reasons; Windows 11 still includes WoW64, and Microsoft has not announced a removal plan.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 \(Windows 32-bit on Windows 64-bit\) is the compatibility subsystem that lets 64-bit Windows run existing 32-bit applications, and it has long been included by default. Making it an optional on-demand feature changes that default for servers, so administrators must decide whether to add it before deploying legacy 32-bit software.

**「Impact」** Administrators planning upgrades will need to include WoW64 installation through PowerShell or DISM in their deployment process, or legacy 32-bit server applications will not start on default installations. Windows 11 clients remain unaffected for now.

**Tags**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

<a id="item-tech-news-8"></a>
### [Codex2api suspected supply-chain attack exposes secrets via backdoored release](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

A report posted on Telegram alleges a supply-chain compromise of Codex2api: the maintainer&\#x27;s account was taken over, and the attacker bypassed the main branch to push a release tag that built a backdoored version. The report says v3.1.11 removed authentication, enabling unauthenticated remote command execution, and that a workflow exfiltrated 16 GitHub Actions secrets, affecting at least 21 repositories under the same account. Users who installed or updated v3.1.10–v3.1.12 are advised to stop using it immediately, roll back to v3.1.9, and rotate the GitHub token, SSH keys, database credentials, DeepSeek keys, and other related secrets. The incident is described as suspected and comes from a Telegram post; the supplied material does not include independent confirmation.

telegram · zaihuapd · Nov 23, 11:21

**「Context: tag-triggered releases and CI secret theft」** Tag-triggered release pipelines can build and publish artifacts without the review a protected \`main\` branch would require, which is the mechanism the incident report describes: the attacker allegedly pushed tags directly and let the release workflow compile the backdoored version. The reported scope — a malicious workflow exfiltrating 16 GitHub Actions secrets across at least 21 repositories under one account — follows a pattern seen earlier in 2026, when the Megalodon campaign injected malicious Actions workflows into more than 5,500 public repositories within a six-hour window in May 2026, and stolen GitHub credentials were later used in November 2026 to push a CI secret stealer at scale. Those external reports describe separate campaigns and do not independently confirm the Codex2api claims.

**「Impact」** Anyone running an affected Codex2api release should treat the host and linked credentials as compromised, because removing the backdoored version does not undo the reported secret exposure. The report&\#x27;s advice is to rotate GitHub tokens, SSH keys, database credentials, and DeepSeek and other related keys, and to audit the at least 21 repositories under the same account for workflow changes or further unauthorized releases.

<details><summary>References</summary>
<ul>
<li><a href="https://www.endorlabs.com/learn/github-actions-supply-chain-attack-targeting-ci-secrets-at-scale">Hijacked GitHub Accounts Push “wfx” CI Secret Stealer to ...</a></li>
<li><a href="https://www.stepsecurity.io/blog/megalodon-mass-github-actions-secret-exfiltration-across-5-500-public-repositories">Megalodon: Mass GitHub Actions Secret Exfiltration Across ...</a></li>

</ul>
</details>

**Tags**: `#supply-chain attack`, `#security`, `#GitHub Actions`, `#credential compromise`, `#open source`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [NVMe-Only KV Cache Matches DRAM for Agentic Serving](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · Nov 23, 00:00

**「Background」** For the authors, agentic serving is dominated by prefix reuse: AgentX’s median turn is 142K input tokens, over 96% already seen, so KV-cache hits drive throughput—but GPU memory and DRAM retain too little session history.

**「Solution」** They compare a 1.8 TB AMD MoRI UMBP pool held entirely on NVMe with a same-size DRAM pool on MI355X GPUs running vLLM/Kimi-K3. Across 48, 70 and 96 concurrent sessions, and in a repeat, NVMe stayed within 1% of DRAM throughput, with hit rates within 0.08% and median TTFT within 0.8 s; a longer-prompt workload also stayed within 1%. The authors attribute this to capacity and scheduling: same-size pools evict similarly, vLLM’s asynchronous loads finish during prefill waits, and DRAM serves only as a ~80 GB write buffer and read staging area. On the kvlab corpus, a 4.6 TB NVMe pool kept 92.7–95.8% hit rates and reached 8,813 tok/s per GPU at 70 sessions, about 5.1× a 1.0 TB DRAM pool—capacity, not medium, caused the gap. Smaller 256 MiB segment files instead of 4 GiB raised throughput 15.6%; “touch” and denser checkpoints also improved hit rates. At list prices NVMe costs per TB written, so drives rated for 83 TB/day hold a day of KV for about $59,000, versus $76,000 for a 1.8 TB DRAM pool holding 31–36 minutes; but writes wear drives, and the 96-session test pair would exhaust rated life in about 5.5 months. The authors call these costs arithmetic, not measurements.

**「Takeaway」** The broader implication is that capacity and retention, not the storage medium, govern agentic KV-cache performance, so NVMe-only pools can replace DRAM tiers if write endurance is managed.

**Tags**: `#KV cache`, `#NVMe`, `#vLLM`, `#agentic serving`, `#SSD wear/cost`

---

<a id="item-tech-blog-2"></a>
### [When in Doubt, Flail: Deliberate Experimentation Under Uncertainty](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** When guidance is unclear—a new product without product-market fit, a system too tangled to reason about, two teams not talking—engineers often assume they should wait for better understanding before acting. Sean Goedecke argues for the opposite instinct, though he concedes the advice is dangerous: engineers who push one bad plan after another burn their reputations.

**「Solution」** His heuristic is to flail deliberately: try many different things, watch feedback closely—from more experienced colleagues and from reality, such as whether a change actually lowers latency or moves user metrics—and ruthlessly drop anything that isn&\#x27;t drawing &quot;wow&quot; feedback. Volume matters three ways: it gives direct contact with reality \(like a caveman pressing every button on an iPhone\), most plans will be bad so ten attempts beat one, and a portfolio prevents over-investment in any single failing idea. He names three varieties: product flailing, where at GitHub Models most integrations failed but letting AI inference run from a GitHub Actions token stuck and seeded &quot;Continuous AI&quot;; engineering flailing—speculative changes to large or already-optimized systems instead of auditing them end to end; and organizational flailing for senior and staff engineers, where the problems aren&\#x27;t technical and the moves are automating manual work, volunteering, or proposing long-term plans. That last case demands the most feedback sensitivity, because pressing on turns others&\#x27; frustration onto you.

**「Takeaway」** Flailing feels like repeated failure from the inside even when it reads as initiative from the outside—a psychological barrier worth pushing through. So long as you stay sensitive to feedback and abandon failing plans instantly, the author argues it is the fastest way to become useful in an unclear situation.

**Tags**: `#engineering judgment`, `#ambiguity`, `#experimentation`, `#feedback loops`, `#tech organizations`

---

<a id="item-tech-blog-3"></a>
### [OpenAI’s Perplexity Graph: Visibility and Limits](https://seangoedecke.com/notes-on-openais-perplexity-reveal/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** OpenAI released a graph of perplexity over time for all its released models, giving unusually direct visibility into a frontier lab’s training metrics. Sean Goedecke treats the release as notable partly because such safety-motivated disclosure is more associated with Anthropic.

**「Solution」** He cautions that perplexity is measured against a specific held-out dataset, so cross-lab comparisons would be unsafe, and that it reflects pretraining rather than the RL work that may consume at least half of frontier training time—so it cannot show all capability gains, such as better chain-of-thought use. The graph’s base-model structure also draws his attention: few models share a base, and he finds it striking that 4.1 and o3 share one despite their different receptions. He reads GPT-4.5 as a pause in large pretraining, followed by a clear acceleration in perplexity loss from GPT-5.2 onward—evidence against the claim that labs have abandoned pretraining. On alignment, he doubts the graph helps much: only OpenAI could spot a sudden drop in unreleased models unless it keeps publishing such data, and threshold agreements would require details of the dataset. Finally, the curve’s big GPT-3.5-to-GPT-4 jump, stagnation, then renewed acceleration does not match his experience that o3 and GPT-5.3-Codex felt like the big leaps, possibly because RL-driven behavior does not appear in perplexity.

**「Takeaway」** Goedecke’s conclusion is that the release is a meaningful transparency step, but perplexity is too dataset-bound and pretraining-specific to serve as a standalone measure of capability or safety.

**Tags**: `#perplexity`, `#LLM pretraining`, `#AI safety transparency`, `#OpenAI`, `#model evaluation`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Shanghai Metro to adjust fares for first time in 21 years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai will implement its first Metro fare adjustment in 21 years on Dec. 1, setting a 3-yuan base fare for the first 4 km and adding 1 yuan at set distance intervals thereafter. The city is also introducing four multi-ride tickets and a 10% discount after monthly spending of 90 yuan on the same payment channel, measures aimed at reducing the impact on frequent riders.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** The change follows a public hearing on Shanghai Metro fares at which most participants supported the option retaining the 3-yuan base fare, according to QQ News.

**「Impact」** Daily commuters face higher pay-as-you-go costs, though frequent riders can reduce part of the increase through the new 35–90 ride passes or a 10% discount after 90 yuan in monthly spending on one payment channel.

<details><summary>References</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260908A05NH700">news.qq.com/rain/a/20260908A05NH700</a></li>

</ul>
</details>

**Tags**: `#Shanghai Metro`, `#public transport fares`, `#fare policy`, `#commuters`, `#cost of living`

---