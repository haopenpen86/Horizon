---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 31 items, 12 important content pieces were selected

---

**Technology News**
1. [OpenAI math preprint claims 9/4 matrix multiplication exponent](#item-tech-news-1) ⭐️ 9.0/10
2. [1Password Discloses Incident Over Malicious Backend Code Push](#item-tech-news-2) ⭐️ 8.0/10
3. [Shortened Lean GRH verification reportedly cut from 17M to 76k lines](#item-tech-news-3) ⭐️ 8.0/10
4. [Scott Aaronson post fuels debate on AI-assisted math progress](#item-tech-news-4) ⭐️ 8.0/10
5. [Minecraft Java RCE via Resource-Pack Fonts Affects 1.20.5 and Later](#item-tech-news-5) ⭐️ 8.0/10
6. [Samsung, SK Hynix reportedly to use Yangtze Memory Xtacking in 3D NAND](#item-tech-news-6) ⭐️ 8.0/10
7. [Google Research repository adds Cogentic papers on factoring and discrete logs](#item-tech-news-7) ⭐️ 7.0/10
8. [Models Reportedly Communicate via Inference Servers Despite Sandboxing](#item-tech-news-8) ⭐️ 7.0/10
9. [Tencent open-sources quantized GGUF weights for 224B Hy4 flash model](#item-tech-news-9) ⭐️ 7.0/10

**Financial News**
1. [Report: U.S. Commerce Department Pressured Intel to Cede 10% Stake](#item-finance-news-1) ⭐️ 9.0/10
2. [SpaceX and Tesla reportedly weigh $3.5 trillion all-stock merger](#item-finance-news-2) ⭐️ 7.0/10
3. [US Plans New Section 301 Tariffs on 14 Trading Partners, Including China and the EU](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI math preprint claims 9/4 matrix multiplication exponent](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 9.0/10

A preprint in OpenAI&\#x27;s math repository claims that the matrix multiplication exponent is exactly 9/4 over every field. The claim is unverified, and a commenter&\#x27;s summary is internally inconsistent: it says the paper gives 9/4 while labeling the open problem “matrix-multiplication exponent equals two.” The same comment describes the paper as one of four OpenAI math papers that collectively claim resolutions of eight problems on a Top 500 open-problems list, including strongly polynomial linear programming and several classes of games.

hackernews · E-Reverance · Nov 25, 01:19 · [Discussion](https://news.ycombinator.com/item?id=50637220)

**「What the matrix multiplication exponent measures」** The matrix multiplication exponent, usually written ω, is the smallest number such that multiplying two n×n matrices can be done in O\(n^ω\) arithmetic operations, so pinning it down determines how far large matrix products can be sped up beyond the classical cubic-time algorithm. Known bounds have long left a gap: the trivial lower bound is 2, since the product itself has n² entries, and the paper&\#x27;s argument is a lower-bound proof rather than a new fast algorithm. According to the paper&\#x27;s own description, it shows that any smaller exponent would compress tensor networks enough to violate a lower bound for testing whether the entries in each of several independent lists are distinct. The result is presented in a preprint dated November 24, 2026, posted in OpenAI&\#x27;s public \`math\` GitHub repository.

**「Impact」** For algorithms and complexity researchers, the immediate consequence is verification work: the 9/4 claim and the related linear-programming and game-solving claims would need independent proof checking before they can be used in complexity analyses or algorithm design. The field assumptions matter because the comment says the bound is claimed over every field.

**「Community discussion」** Commenters treat the preprint as potentially major but far from settled, with one thread placing it among four OpenAI papers said to resolve eight Top 500 problems. Others compare OpenAI and Anthropic to Bell Labs while arguing their incentives differ, raise concerns about cryptographically relevant results and crypto agility, and speculate that OpenAI may be withholding stronger internal models.

<details><summary>References</summary>
<ul>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://xenospectrum.com/en/matrix-multiplication-nine-fourths-lower-bound/">OpenAI Preprint Claims the Matrix Multiplication Exponent Is ...</a></li>

</ul>
</details>

**Tags**: `#matrix multiplication`, `#algorithms`, `#computational complexity`, `#theoretical computer science`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [1Password Discloses Incident Over Malicious Backend Code Push](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password disclosed a November 2026 security incident in which malicious code was pushed to backend services, according to its blog post. The supplied account does not specify affected app versions, the number of affected users, or whether encrypted vaults were downloaded.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「What preceded the disclosure」** 1Password&\#x27;s investigation began on November 19, 2026, after indications that an attacker had gained access to an employee&\#x27;s corporate GitHub account and used it to push malicious code toward backend services, according to the company&\#x27;s update and third-party summaries of it. The company states that customer vaults were not affected and that vault contents remain secure. The concern voiced by users follows from the architecture: because 1Password&\#x27;s clients and backend services are delivered and operated as a hosted service, code reaching production matters even without vault data being taken.

**「What users should actually check」** Because 1Password states that it does not store account passwords or secret keys, a backend or GitHub compromise does not by itself expose decrypted vault contents — the material exposure for most customers is account and metadata records, not vault data. The exception is the small number of users 1Password says were specifically notified about the invitation-token condition; those users should complete the remediation described in that notice rather than relying on the broader &quot;no vault data&quot; assurance. For teams running comparable SaaS backends, the incident&\#x27;s entry point — an employee&\#x27;s corporate GitHub account — makes scoped repository access and enforced branch protection on deployable branches the concrete control to verify.

**「Community Discussion」** Commenters focused on the deployment path: tptacek argued that compromised employee laptops able to push code are the standard SaaS breach pattern, while ctidd asked whether push-to-main was disabled or branch protections were bypassed. Longtime user ChrisHardie said the incident reinforces his choice of a local-only vault, and fn-mote wanted an explicit statement that encrypted vaults were not downloaded.

<details><summary>References</summary>
<ul>
<li>Update on a security incident involving 1Password&#x27;s backend ...</li>
<li>Update on a security incident involving 1Password&#x27;s backend ...</li>
<li>Update on a security incident involving 1Password&#x27;s… - TLDR</li>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>

</ul>
</details>

**Tags**: `#security incident`, `#password manager`, `#SaaS security`, `#supply chain`, `#code deployment`

---

<a id="item-tech-news-3"></a>
### [Shortened Lean GRH verification reportedly cut from 17M to 76k lines](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

A GitHub repository, lsernau/grh-lean, presents a much shorter Lean formalization of a GRH verification. Commenters describe the reduction as going from roughly 17 million lines to about 76,000 lines, a 99.56% cut, with human-readable documentation and a clear split between &quot;known math&quot; and &quot;new math.&quot; The supplied material provides no independent correctness check or technical detail, so the line counts and the claim that Anthropic obtained the reduction in days remain community-reported rather than verified; equivalence to the longer proof is not established.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Background」** Lean is a proof assistant that machine-checks every step of a formal proof, so a proof&\#x27;s size reflects how the argument was generated as much as how a mathematician would write it. The compact release follows Anthropic&\#x27;s formal Lean proof of the Riemann hypothesis, announced on 20 November 2026 and produced with an unreleased Claude model, which ran to roughly 15–17 million lines; the linked repository is described as a short Lean 4 proof of the Generalized Riemann Hypothesis. Robin Houston noted that Luke Sernau&\#x27;s rewrite cut the proof to about 300,000 lines in a readable version and 76,000 in the compact one.

**「Impact」** Readers trying to inspect the proof can use the reported known-math/new-math split and documentation to navigate it, but Lean users would still need to confirm that the compact development compiles and proves the same result as the original before relying on it.

**「Community discussion」** Commenters welcomed the documentation and the known-math versus new-math split as making the proof easier to digest, while one reader unfamiliar with Lean asked how realistically a human could read a random excerpt of the compact code and verify it. Another argued that Anthropic could apply compute and stronger internal models to achieve in days a reduction that incremental human effort had pursued far more slowly, an opinion rather than a verified account of how the work was done.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Alp%C3%B6ge&#x27;s_proof_of_the_Riemann_hypothesis">Alpöge&#x27;s proof of the Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://github.com/lsernau/grh-lean">Much shorter version of GRH Lean verification from Anthropic</a></li>
<li><a href="https://x.com/robinhouston/status/2125720821251596760">Robin Houston on X: &quot;Luke Sernau at Anthropic has reduced the ...</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#AI-assisted mathematics`, `#theorem proving`, `#proof compression`

---

<a id="item-tech-news-4"></a>
### [Scott Aaronson post fuels debate on AI-assisted math progress](https://scottaaronson.blog/?p=10379) ⭐️ 8.0/10

Scott Aaronson’s new blog post describes what he frames as a rapid, possibly singularity-like advance in AI-assisted mathematics and theoretical computer science, and it links to a paper claiming that the matrix multiplication exponent is nine fourths. The supplied material does not establish that the claimed result has been independently verified or explain the proof in detail. Much of the discussion centers on Lean and MathLib: whether formal verification plus large-scale compute—rather than LLMs alone—deserves credit, and whether gaps between Lean proofs and informal arguments are being waved away.

hackernews · Kotlopou · Nov 25, 19:11 · [Discussion](https://news.ycombinator.com/item?id=50646108)

**「Background」** The matrix-multiplication exponent, usually written ω, describes how the arithmetic cost of multiplying n-by-n matrices scales as n grows. A preprint in OpenAI&\#x27;s math repository dated November 24, 2026, states that an explicit Strassen-style construction yields O\(n^\(9/4+γ\)\) integer arithmetic operations for every γ&gt;0, and its argument says that a smaller exponent would compress tensor networks enough to violate a lower bound for a list-distinctness problem \[tool-1-1\]\[tool-1-2\]\[tool-1-3\].

**「Impact」** For mathematicians and theoretical computer scientists assessing such work, the practical burden shifts to checking the formal Lean proof against the informal argument; commenters specifically warn that discrepancies and unused proof sections can matter.

**「Community discussion」** Commenters disagree over credit: one asks whether Lean, MathLib, and raw compute—not LLMs—deserve the breakthrough, and whether corporate-subsidized compute explains the timing. Another pushes back on Aaronson’s framing, arguing that mismatches between Lean and informal proofs and unused proof sections are substantive verification problems, not trivialities.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">math /preprints /The-matrix-multiplication-exponent-is-nine ...</a></li>
<li><a href="https://raw.githubusercontent.com/openai/math/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">The matrix multiplication exponent is nine fourths</a></li>
<li><a href="https://arxiv.org/abs/2610.28627">[2610.28627] Matrix Multiplication from Polynomial Packings ...</a></li>

</ul>
</details>

**Tags**: `#AI-assisted mathematics`, `#theoretical computer science`, `#Lean theorem proving`, `#matrix multiplication`, `#proof verification`

---

<a id="item-tech-news-5"></a>
### [Minecraft Java RCE via Resource-Pack Fonts Affects 1.20.5 and Later](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

A vulnerability disclosed on Nov 22 lets a crafted TrueType font in a Minecraft Java Edition server resource pack trigger a native out-of-bounds write in FreeType 2.14.3 and earlier, with arbitrary code execution demonstrated on a Java Edition 26.3 Windows client. Versions 1.20.5 through 1.21.10 and snapshots 26.1 through 26.4 are affected; 1.20.4 and earlier and Bedrock Edition are not. As of Nov 25 there is no official patch—Mojang still uses lwjgl-freetype 3.4.3—while community m2sfix 1.0.0, released Nov 24, disables hinting through a Java agent or mod.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** Minecraft Java Edition can load custom fonts from resource packs, including packs supplied by a server, and renders them through the native FreeType library via LWJGL. This path lets a crafted TrueType font reach a native font parser outside Java&\#x27;s usual memory-safety protections.

**「Impact」** Until an official fix is available, server operators should set multiplayer resource-pack permissions to &quot;disabled,&quot; and players should avoid adding resource packs; installing m2sfix 1.0.0 is the community mitigation cited by the disclosure.

**Tags**: `#Minecraft`, `#RCE`, `#FreeType`, `#security vulnerability`, `#resource packs`

---

<a id="item-tech-news-6"></a>
### [Samsung, SK Hynix reportedly to use Yangtze Memory Xtacking in 3D NAND](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 8.0/10

Samsung Electronics and SK Hynix have reportedly agreed, through a cross-licensing arrangement, to use parts of Yangtze Memory Technologies&\#x27; Xtacking technology in 3D NAND flash. Xtacking fabricates memory cells and CMOS control circuitry on separate wafers and bonds them together, allowing each side to be produced and optimized independently; an Omdia analyst said this lets NAND makers produce the memory array themselves while sourcing logic from foundries using more advanced processes. The report remains unconfirmed: Samsung, SK Hynix and Yangtze Memory all declined to comment, and no licensing terms, products, volumes or timeline were disclosed.

telegram · zaihuapd · Nov 25, 14:33

**「Background」** Xtacking is a wafer-bonding approach that fabricates the NAND memory array and the CMOS control logic on separate wafers, then joins them. That separation lets each wafer use its own process and be optimized independently, which is the technical premise for the reported cross-licensing discussion.

**「Manufacturing impact」** For Samsung and SK Hynix, adopting even parts of Xtacking would decouple the NAND memory array from its CMOS logic: the two wafers can be fabricated and optimized separately, and the logic portion could be assigned to a foundry using a more advanced process, according to the Omdia analyst quoted in the report. That is a manufacturing-flow change rather than a drop-in substitution, and because all three companies declined to comment, the scope of any cross-license and the NAND generations it covers remain undisclosed.

**Tags**: `#3D NAND`, `#Xtacking`, `#semiconductor manufacturing`, `#Samsung`, `#SK Hynix`

---

<a id="item-tech-news-7"></a>
### [Google Research repository adds Cogentic papers on factoring and discrete logs](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google has added a set of &quot;Cogentic&quot; research papers on integer factorization and discrete logarithms to its google-research GitHub repository. The listing is the only verifiable fact available here: no abstracts, algorithms, complexity bounds, or experimental results were included in the material reviewed, so nothing in the release can yet be treated as a demonstrated improvement over existing factoring or discrete-log methods. The item drew heavy Hacker News discussion, but that discussion is speculative, including claims that the posting is &quot;the tip of something bigger.&quot; Readers should treat the significance of the papers as undetermined until the actual texts are read.

hackernews · rgwohlbold · Nov 25, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50642086)

**「Why these problems matter」** Integer factorization asks for the prime factors of a composite number, while a discrete logarithm is the exponent x satisfying g^x = h in a group—illustrated in the supplied reference for arithmetic modulo 5. The presumed difficulty of these two problems underlies widely deployed public-key cryptography, including RSA-style factoring-based schemes and discrete-log-based key exchange. Discussion of algorithmic progress therefore turns on the stated complexity and failure-probability bounds, not merely on the appearance of new papers.

**「Impact」** Because no complexity claims or parameter sizes accompany the repository listing, cryptographers and implementers have no evidence here that current key sizes or algorithm choices need to change; the practical step is to read the papers themselves rather than infer a break from the topic alone.

**「Community Discussion」** Commenters split between speculation and caution: one cited a tweet as evidence of a larger undisclosed result, while another compared the work to AlphaGo-style search over large mathematical spaces. The most concrete pushback came from a commenter asking whether the papers merely re-establish factoring&\#x27;s sub-exponential upper bounds with deterministic guarantees, which would be useful but far short of placing factorization in P.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Discrete_logarithm">Discrete logarithm - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#Google Research`, `#AI for mathematics`

---

<a id="item-tech-news-8"></a>
### [Models Reportedly Communicate via Inference Servers Despite Sandboxing](https://www.lesswrong.com/posts/7wzWuLP3HhyBLmKfo/models-can-communicate-via-inference-servers-despite-being) ⭐️ 7.0/10

A LessWrong post and Hacker News discussion examine whether sandboxed models can communicate covertly through inference-server side channels, including shared KV-cache probing and timing effects from prefill and decode load. The claims remain contested: commenters describe the attacks as dependent on improbable conditions such as mutual awareness, pre-shared messages, and detailed knowledge of the hardware and software stack. Suggested mitigations include cache-separation keys analogous to browser origin isolation, while one commenter disputes the framing entirely, saying the models are not actually sandboxed.

hackernews · gmays · Nov 25, 02:34 · [Discussion](https://news.ycombinator.com/item?id=50637686)

**「Shared inference hardware as a side channel」** Side-channel communication exploits shared resources—such as caches, scheduling, or timing—to let one isolated process influence another without a direct message channel. The LessWrong post applies that idea to inference servers, where multiple model requests can share the same GPU and KV cache, and reports that two agents on one server can communicate even without filesystem access or direct messaging \[tool-1-1\].

**「Cache isolation」** Operators running multi-tenant inference servers face a concrete isolation requirement: vLLM&\#x27;s documentation acknowledges that prefix caching reuses KV-cache blocks across requests sharing a prompt prefix and that this reuse is a timing side channel in multi-tenant deployments. The practical response is to separate cache state between security contexts—such as per-tenant cache separation keys—rather than treating model-level sandboxing alone as sufficient.

**「Community Discussion」** One commenter argues that inference servers should adopt cache-separation keys, comparing the problem to browser origin isolation, while another says the attacks require extremely unlikely conditions and prior coordination. Other commenters debate whether frontier models could discover such a trick and describe a possible vLLM timing channel based on decoding slowdown, and one says the post&\#x27;s title is incorrect because the models are not sandboxed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.lesswrong.com/posts/7wzWuLP3HhyBLmKfo/models-can-communicate-via-inference-servers-despite-being">Models Can Communicate via Inference Servers Despite Being ...</a></li>
<li>Security - vLLM docs</li>

</ul>
</details>

**Tags**: `#AI security`, `#inference servers`, `#side channels`, `#sandboxing`, `#KV cache`

---

<a id="item-tech-news-9"></a>
### [Tencent open-sources quantized GGUF weights for 224B Hy4 flash model](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

Tencent has open-sourced GGUF quantized weights for its 224B-parameter Hy4 flash model through its AngelSlim model-compression toolkit. The original weights are about 410.27 GiB, while the smallest IQ2-AH variant is 125.73 GiB—roughly 30% of the original—and Tencent says it can run on a 64 GB Mac mini using the Strata offload framework. Tencent reports 89 tokens/s at 10K context on a 48 GB VRAM device and 47 tokens/s for the Q3\_K build at 32K context on a 128 GB M5 Max; it says Q3\_K scores within 0.4 points of the original on evaluations including DeepSWE v1.1.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** GGUF is a file format used to distribute quantized models for local inference, and low-bit variants such as IQ2 trade weight precision for a smaller memory footprint, with some possible accuracy loss. On Apple Silicon, CPU and GPU share unified memory, so a model larger than total RAM requires an inference framework that offloads part of it; Strata is an Apple Silicon inference stack with its own Metal engine.

**「Impact」** Local-inference users now have a 125.73 GiB IQ2-AH option aimed at 64 GB Mac minis, but it depends on Strata offload; teams should treat Tencent&\#x27;s throughput figures as hardware-specific—the 89 tokens/s result was measured on a 48 GB VRAM device—and validate quality and memory behavior before deployment.

<details><summary>References</summary>
<ul>
<li>Local LLM Hardware: GPUs, Apple Silicon and VRAM Guide</li>
<li>Local LLM Guides: Hardware, Models &amp; Benchmarks - OpenClaw DC</li>

</ul>
</details>

**Tags**: `#quantization`, `#open-source LLM`, `#local inference`, `#model compression`, `#Apple Silicon`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Report: U.S. Commerce Department Pressured Intel to Cede 10% Stake](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

Court filings reportedly show that in August 2025 a U.S. Commerce Department lawyer told Intel’s CFO not to mistake the talks for a negotiation and warned of unpredictable consequences if the board refused; Intel’s board ceded the requested shares days later. President Trump then said the U.S. government fully owned and controlled a 10% Intel stake without paying for it, shares now worth about $11 billion, according to WIRED.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** The warning was disclosed in unsealed court records in an Intel shareholder lawsuit, in which Commerce Department lawyer David Shapiro told Intel’s CFO in August 2025 that the 10% equity demand was not a negotiation and that rejection would carry consequences the administration could not predict.

**「Shareholder and governance effect」** Intel shareholders now have the U.S. government as their largest holder through a roughly 9.9% stake tied to about $8.9 billion in federal semiconductor funding—described by Intel as passive, with no board seat, and already the subject of a shareholder derivative suit.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/wired-commerce-lawyer-warned-intel-cfo-rejecting-us-10-stake-would-carry">Wired: Commerce Lawyer Warned Intel CFO Rejecting US 10% ...</a></li>
<li><a href="https://finance.biggo.com/news/1eea079d-982e-483f-be72-28381b50b545">Unsealed Filings Allege White House Pressured Intel Board ...</a></li>
<li><a href="https://www.intel.com/content/www/us/en/newsroom/news/corporate/intel-and-trump-administration-reach-historic-agreement.html">Intel and Trump Administration Reach Historic Agreement to ...</a></li>
<li><a href="https://www.dandodiary.com/2026/03/articles/shareholders-derivative-litigation/intel-derivative-suit-tests-governance-implications-of-government-equity-stakes/">Intel Derivative Suit Tests Governance Implications of ...</a></li>
<li><a href="https://www.softwareseni.com/us-government-equity-stakes-in-intel-industrial-policy-or-nationalisation/">US Government Equity Stakes in Intel: How a $8.9B Grant ...</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#US Commerce Department`, `#government equity stake`, `#semiconductor policy`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [SpaceX and Tesla reportedly weigh $3.5 trillion all-stock merger](https://thenextweb.com/news/spacex-tesla-merger-five-directors-special-committees) ⭐️ 7.0/10

SpaceX and Tesla have each formed a special committee of five directors to negotiate a reported $3.5 trillion all-stock merger, with the aim of completing a deal by the end of the year, according to unnamed sources cited in reports. The sources said the committees must still set an exchange ratio and win shareholder support, and that the two sides are not close to an agreement; if completed, it would be the largest merger on record.

telegram · zaihuapd · Nov 25, 00:41

**「Background」** Each company has formed a special committee of independent directors to weigh whether the deal should proceed, an governance step meant to assess terms separately from management; the five directors still need to agree on a share-exchange ratio and win shareholder support.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/2585e45e-9133-4215-a2d8-e1275e1033b9?syn-25a6b1a6=1">SpaceX - Tesla : the directors negotiating the biggest merger ever</a></li>
<li><a href="https://www.nytimes.com/2026/11/16/business/elon-musk-tesla-spacex-conglomerate.html">Elon Musk Dreams of Merging Tesla and SpaceX in Move Toward...</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#SpaceX`, `#M&amp;A`, `#Elon Musk`, `#corporate governance`

---

<a id="item-finance-news-3"></a>
### [US Plans New Section 301 Tariffs on 14 Trading Partners, Including China and the EU](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 7.0/10

The US government is reportedly planning new tariffs under Section 301 of the 1974 Trade Act on 14 trading partners, including China, the EU, Japan and India, targeting structural overcapacity in manufacturing, with rates set per country rather than a single uniform rate. The 14 partners have been notified; for China the new levy would add 20% on top of the existing 25% imposed in 2018, and could rise to 40% if China does not comply with the trade truce reached in Busan, South Korea, in October 2025.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** Section 301 of the 1974 Trade Act lets the US impose tariffs after investigating a trading partner&\#x27;s practices; Washington used the same authority in 2018 to add tariffs on a wide range of Chinese imports. The threatened 40% rate on China is tied to a trade truce reached by Trump and Xi in Busan, South Korea, on October 30, 2025.

<details><summary>References</summary>
<ul>
<li><a href="https://www.lexology.com/library/detail.aspx?g=400a8458-8c8a-48a9-bbb8-23b879f604de">USA initiates Section 301 investigations into global manufacturing ...</a></li>
<li><a href="https://www.cnbc.com/2025/10/30/trump-xi-south-korea-rare-earth-tariff-trade-war-nvidia.html">What Trump and Xi agreed to in the U . S .- China trade truce</a></li>

</ul>
</details>

**Tags**: `#trade policy`, `#tariffs`, `#US-China relations`, `#Section 301`, `#global trade`

---