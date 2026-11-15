---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 31 items, 9 important content pieces were selected

---

**Technology News**
1. [Meta FAIR and NYU: Vision Encoder Pretraining Optional, Vision-Only Parameters Essential](#item-tech-news-1) ⭐️ 8.0/10
2. [Meituan open-sources LongCat-2.5, a 1.6T-parameter agent model it says trained without Nvidia GPUs](#item-tech-news-2) ⭐️ 8.0/10
3. [MacBook Pro OLED PWM flicker article draws measurement dispute](#item-tech-news-3) ⭐️ 7.0/10
4. [Explainer Examines Positional Embeddings in Modern LLMs](#item-tech-news-4) ⭐️ 7.0/10
5. [SpaceX Starship returns from orbit and is caught by tower arm](#item-tech-news-5) ⭐️ 7.0/10
6. [Tesla Cybercab terms require $299 monthly subscription to operate](#item-tech-news-6) ⭐️ 7.0/10
7. [FAA ground stop traced to router fault after copper-to-fiber work](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [Lutnick faces questions over Nvidia as sons&\#x27; firm cuts reported stake](#item-finance-news-1) ⭐️ 7.0/10
2. [U.S. judge denies dismissal motion in DRAM price-fixing lawsuit](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meta FAIR and NYU: Vision Encoder Pretraining Optional, Vision-Only Parameters Essential](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Meta FAIR and NYU researchers trained more than 200 multimodal LLMs from scratch, including the language model, on the same data with lifetime compute budgets that charged encoder pretraining against multimodal training; main comparisons used Qwen3-1.7B and 4B backbones, with a scaling ladder from 0.6B to 6.4B. They report that separate vision-encoder pretraining is optional: encoders pretrained with contrastive, self-supervised, or captioning objectives at best tied a from-scratch encoder at matched compute, and extending MetaCLIP pretraining 6.5× raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA. Vision-only parameters were required: encoder-free models trailed at every size from 0.6B to 6.4B and needed about 3× the compute to catch up, while giving the LLM the encoder’s parameters improved text but not VQA. Placement before the LLM was also optional: an “in-fusion” design adding zero-initialized vision-only weights to the first eight LLM layers matched an encoder from 1.7B to 6.4B with about 13% lower time to first token, scoring 45.0 VQA at 1.7B versus 44.4 for the encoder, 42.3 with shared parameters, and 35.1 with vision branches in the last eight layers; the work is a preprint, not peer-reviewed, and used 16 Cambrian VQA benchmarks at 448 px plus 12 language benchmarks.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Background」** Standard multimodal LLM recipes bolt a separately pretrained vision encoder — often a contrastively pretrained one such as MetaCLIP — onto the front of a language model, so that a single component carries three things at once: a visual prior from upstream pretraining, parameters used only by vision tokens, and a position ahead of the LLM. As the paper&\#x27;s abstract notes, most models still use such a pretrained encoder, while some recent recipes train it from scratch alongside the language model or remove it entirely, and published models differ too much in data and compute to settle which of the three ingredients actually matters.

**「What builders should budget」** For teams designing multimodal models, the study&\#x27;s actionable result is to budget dedicated parameters rather than encoder pretraining: encoder-free models trailed at every backbone size from 0.6B to 6.4B and needed roughly 3x the compute to catch up, while pretraining the encoder at matched lifetime compute at best tied training from scratch. If an architecture removes the separate encoder entirely — as Gemma 4 12B does with its encoder-free design — the reported fix is zero-initialized vision-only branches in the LLM&\#x27;s first 8 layers, which reached 45.0 VQA versus 42.3 when text tokens shared those weights, with about 13% lower time to first token. These are preprint results on 1.7B–6.4B backbones and 16 Cambrian VQA benchmarks, not an independently verified or peer-reviewed claim.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.17334">[2611.17334] Unbundling Multimodal Vision Encoding - arXiv.org</a></li>
<li><a href="https://casrai.org/news/unbundling-multimodal-vision-encoding-nyu-meta-fair-2026">NYU and Meta FAIR Unbundle MLLM Vision Encoding — CASRAI</a></li>
<li><a href="https://developers.googleblog.com/gemma-4-12b-the-developer-guide/">Gemma 4 12 B : The Developer Guide - Google Developers Blog</a></li>

</ul>
</details>

**Tags**: `#multimodal LLMs`, `#vision encoders`, `#pretraining`, `#model architecture`, `#empirical study`

---

<a id="item-tech-news-2"></a>
### [Meituan open-sources LongCat-2.5, a 1.6T-parameter agent model it says trained without Nvidia GPUs](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team published the weights for LongCat-2.5 one week after the model&\#x27;s release, under an MIT license that permits commercial use. The model has 1.6 trillion total parameters with roughly 48 billion activated per token, accepts text, image and video input, and is built for agents that complete long, multi-step tasks, especially coding. The team says training ran entirely on Chinese chips — Huawei Ascend accelerator cards — with no Nvidia GPUs used. It reports a Terminal Bench v2.1 score of 88.4, just below Claude Opus 5&\#x27;s 89.1; these are vendor-supplied figures relayed by The Decoder, with no independent verification provided.

telegram · zaihuapd · Nov 15, 11:08

**「Context」** The weights arrived a week after the model itself was announced, so LongCat-2.5 moved from a launch presentation to a downloadable artifact. The reported ~48B active parameters out of a 1.6T total indicate a sparse model that activates only a fraction of its parameters per token, which keeps serving costs well below what a dense model of that size would require.

**「What it means」** Because the MIT license allows commercial use, teams can self-host and adapt a trillion-parameter-class agent model rather than only calling it through an API. If the training claim holds, it also gives buyers an example of a frontier-scale model built without Nvidia hardware — relevant to organizations that cannot or prefer not to depend on Nvidia supply. The 0.7-point Terminal Bench gap to Claude Opus 5 and the absence of independent evaluation mean developers should validate it on their own coding and agent workloads before treating it as a substitute.

**Tags**: `#LongCat-2.5`, `#open-weight models`, `#Huawei Ascend`, `#AI agents`, `#AI hardware`

---

<a id="item-tech-news-3"></a>
### [MacBook Pro OLED PWM flicker article draws measurement dispute](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

An article on MacAnorak examines PWM flicker on the MacBook Pro&\#x27;s OLED display, focusing on measurement scrutiny and reports of display sensitivity. The central technical dispute concerns the reported 240 Hz PWM rate: commenters challenge that result, with one arguing that the tandem OLED&\#x27;s two layers run at 480 Hz and 180 degrees out of phase, giving an effective 960 Hz over most of the usable brightness range. No hardware or software change is announced; the exact rate and the prevalence of PWM sensitivity remain unresolved.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「Background」** OLED displays often regulate brightness with pulse-width modulation \(PWM\), rapidly switching pixels on and off; at low enough frequencies, sensitive viewers can perceive flicker or experience eye strain. A Notebookcheck review of the MacBook Pro&\#x27;s tandem OLED panel measured PWM at 240 Hz and noted that this could still bother flicker-sensitive users even with DC dimming.

**「What this means for flicker-sensitive buyers」** For people with flicker sensitivity, the practical consequence is that an OLED MacBook Pro can cause discomfort even though its refresh-rate specification looks high, because PWM dimming and refresh rate are separate characteristics; the research cited in the thread found that flicker artifacts can be perceived at rates above 500 Hz when high-frequency spatial edges are present. Buyers who already react to PWM should test the exact configuration in person rather than relying on the headline numbers, since the panel&\#x27;s precise PWM frequency remains disputed in the discussion rather than settled.

**「Community discussion」** Beyond the frequency dispute, readers described a wider range of sensitivities: low-CRI white LEDs and LCD motion blur were cited alongside OLED flicker, and one reader who had suffered a concussion said nearly all screens affected them. Another commenter called for more research into how many people experience PWM problems, noting they personally had not.

<details><summary>References</summary>
<ul>
<li><a href="https://www.notebookcheck.net/Amazing-OLED-panel-Apple-MacBook-Pro-14-PROLED-XDR-Review.1438048.0.html">Amazing OLED panel - Apple MacBook Pro ... - Notebookcheck Review</a></li>
<li><a href="https://www.nature.com/articles/srep07861">Humans perceive flicker artifacts at 500 Hz | Scientific Reports</a></li>

</ul>
</details>

**Tags**: `#OLED PWM`, `#display flicker`, `#MacBook Pro`, `#hardware ergonomics`, `#HN discussion`

---

<a id="item-tech-news-4"></a>
### [Explainer Examines Positional Embeddings in Modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

The item is a technical explainer on positional embeddings in modern large language models, aimed at readers seeking to understand how these embeddings are implemented. The supplied metadata describes it as an educational deep-dive rather than an announcement of a new model, method, or measured result; no article body was provided. The accompanying Hacker News discussion focuses on the theory underlying positional embeddings.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** Self-attention does not by itself distinguish between different token orders, so transformer-based large language models need positional information encoded alongside token representations. Rotary positional embeddings \(RoPE\) are one approach, representing each position as a rotation in embedding space rather than as a separate additive vector.

**「Community Discussion」** Commenter programjames argued that the article covers implementation but that fully understanding positional embeddings requires theory, describing them as group representations and citing rotary positional embeddings as representations of the translation group. The supplied comment is truncated, so the rest of that argument is unavailable.

<details><summary>References</summary>
<ul>
<li><a href="https://medium.com/ai-insights-cobet/rotary-positional-embeddings-a-detailed-look-and-comprehensive-understanding-4ff66a874d83">Rotary Positional Embeddings : A Detailed Look and... | Medium</a></li>

</ul>
</details>

**Tags**: `#positional embeddings`, `#large language models`, `#transformer architecture`, `#deep learning`, `#technical deep-dive`

---

<a id="item-tech-news-5"></a>
### [SpaceX Starship returns from orbit and is caught by tower arm](https://www.spacex.com/launches/starship-flight-15) ⭐️ 7.0/10

SpaceX announced that its Starship spacecraft completed Flight 15, flying for about 22.5 hours and roughly 14 orbits before returning to its Texas launch site, where the launch tower&\#x27;s mechanical arm caught it for the first time after an orbital return. The mission also deployed 26 next-generation Starlink V3 satellites, according to the supplied summary. The Super Heavy booster missed its planned tower return and splashed down in the Gulf of Mexico, so SpaceX did not recover both stages on the same flight. The supplied account did not include independent confirmation of the company&\#x27;s claims.

telegram · zaihuapd · Nov 14, 23:49

**「Background」** SpaceX&\#x27;s Starship is a two-stage, reusable launch system; its recovery plan calls for both the Super Heavy booster and the upper stage to return to the launch site, where the tower&\#x27;s mechanical arms catch the vehicle. Flight 15 was the first recovery of the Starship upper stage from orbit, according to mission records, so the tower catch tested the final step after reentry.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Starship_flight_15">Starship flight 15 - Wikipedia</a></li>
<li><a href="https://aerospaceamerica.aiaa.org/spacex-achieves-first-starship-tower-catch/">SpaceX achieves first Starship tower catch - Aerospace America</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#reusable spaceflight`, `#Starlink`, `#aerospace`

---

<a id="item-tech-news-6"></a>
### [Tesla Cybercab terms require $299 monthly subscription to operate](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

Tesla&\#x27;s Cybercab configurator terms set a $29,990 vehicle price and require a $299-per-month autonomous-driving subscription for the vehicle to operate, according to a brief Telegram post citing Electrek and Reuters. The terms allow Tesla to change the subscription price with one month&\#x27;s notice; nonpayment or misuse can lead to suspension or cancellation, and three accumulated warnings disable autonomous driving for one week. They also restrict the car to designated operating areas and prohibit unauthorized use on ride-hailing, delivery or rental platforms. The post gives no launch date or independent confirmation.

telegram · zaihuapd · Nov 15, 01:10

**「Background」** Tesla&\#x27;s consumer FSD still requires a human supervisor, while its Robotaxi program uses the same AI4 hardware and autonomous-driving software in vehicles such as the Model Y, according to the source. Electrek&\#x27;s report on the Cybercab order page said Tesla was offering the personal-use two-seater at $29,990 plus a mandatory $299 monthly subscription, with operation limited to Robotaxi geofences.

**「Impact」** Buyers would face a recurring $299 monthly fee on top of the purchase price, and the car&\#x27;s operation would depend on remaining in good standing with Tesla. The prohibition on unauthorized commercial-platform use also means owners could not treat the Cybercab as an open robotaxi business without Tesla&\#x27;s approval.

<details><summary>References</summary>
<ul>
<li><a href="https://electrek.co/2026/11/13/tesla-cybercab-personal-use-orders-299-subscription-geofence/">Tesla Cybercab orders open at $29,990 + $299/mo, only in ...</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription model`, `#robotaxi`

---

<a id="item-tech-news-7"></a>
### [FAA ground stop traced to router fault after copper-to-fiber work](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

Transportation Secretary Sean Duffy said the FAA’s Friday nationwide ground stop followed routine maintenance at a remote facility that replaced aging copper lines with fiber, after which a newly installed router had problems and thousands of flights were grounded. He said the root cause is not yet established and could be a hardware fault, a configuration error, or a mistake by contractor L3Harris. According to Duffy, the router sent more than 1,000 connection requests every 4 to 5 seconds to other routers, interfering with radar signals and aircraft communications. He called for additional congressional funding for air traffic control modernization.

telegram · zaihuapd · Nov 15, 02:10

**「Background」** The contractor named in the FAA&\#x27;s account, L3Harris, was partially blamed for a 2025 air traffic control outage in Dallas, the Dallas Morning News reported. The maintenance also comes amid a broader FAA modernization push: Congress provided $12.5 billion to upgrade aging air traffic control and telecom systems, and Transportation Secretary Sean Duffy has requested $50 billion more, according to Reuters.

**「Impact」** Because the cause has not been narrowed to hardware, configuration, or contractor work, the FAA cannot yet specify whether the corrective action is equipment replacement, configuration controls, or contractor oversight for the affected routing path.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dallasnews.com/business/airlines/article/l3harris-router-texas-faa-outage-22531968.php">L3Harris routers probed in FAA nationwide ground stop</a></li>
<li><a href="https://www.reuters.com/business/aerospace-defense/us-aviation-shutdown-blamed-l3-harris-installed-router-2026-11-14/">US aviation shutdown blamed on L3 Harris installed router</a></li>

</ul>
</details>

**Tags**: `#FAA`, `#network outage`, `#routing failure`, `#infrastructure reliability`, `#aviation`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick faces questions over Nvidia as sons&\#x27; firm cuts reported stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reported that Cantor Fitzgerald, the Wall Street firm now led by Commerce Secretary Howard Lutnick&\#x27;s sons, cut the number of Nvidia shares it reported holding by 49% between September 2025 and March 2026, to 1.78 million, while continuing to help arrange billions of dollars in financing for the chipmaker&\#x27;s business partners. The report follows Axios&\#x27;s Nov. 11 allegation that Lutnick resisted a crackdown on suspected smuggling of Nvidia chips to China; CNBC said there is no evidence of wrongdoing, and Cantor called its stand-alone Nvidia positions immaterial.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Nvidia CEO Jensen Huang resigned this week after reports that he had an affair with a suspected Chinese spy, and the controversy has renewed scrutiny of Commerce Secretary Howard Lutnick, whose sons now lead Cantor Fitzgerald, the Wall Street firm he formerly ran.

**「Impact」** Because Commerce has delayed new Entity List additions, Singapore-based Megaspeed remains outside the restricted-party export rules despite four other agencies backing its inclusion over the alleged diversion of Nvidia chips to China.

<details><summary>References</summary>
<ul>
<li><a href="https://www.npr.org/2026/11/12/nx-s1-6037833/jensen-huang-nvidia-stepped-down">Nvidia CEO Jensen Huang resigns amid spy scandal : NPR</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html">Howard Lutnick&#x27;s sons&#x27; Nvidia ties amid Jensen Huang China ...</a></li>
<li><a href="https://aiweekly.co/alerts/commerce-delays-entity-list-additions-megaspeed-stays-off">Commerce delays Entity List additions, Megaspeed stays off</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#China export controls`, `#conflict of interest`, `#semiconductors`

---

<a id="item-finance-news-2"></a>
### [U.S. judge denies dismissal motion in DRAM price-fixing lawsuit](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

U.S. Judge Noël Wise denied a motion by Micron, Samsung, and SK Hynix to dismiss a DRAM price-fixing class action, finding the plaintiffs&\#x27; evidence of synchronized supply restrictions plausible enough for the case to proceed; the 17 individual and small-business plaintiffs allege four parallel supply actions within a year raised prices by as much as 500%. The ruling is procedural and does not establish wrongdoing, and the companies must respond by December 7.

telegram · zaihuapd · Nov 15, 16:39

**「Background」** The case is a proposed class action in California federal court brought by 17 individuals and small businesses; the ruling lets them pursue discovery, the evidence-gathering stage, and is not a finding that the companies fixed prices for DRAM, the memory chips used in computers and phones.

**「Impact」** The ruling keeps Micron, Samsung and SK Hynix in the litigation, while PC and smartphone makers already face tight DRAM supply and rising memory costs that IDC warns threaten 2026 device pricing and specifications.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/articles/judge-denies-motion-dismiss-dram-152445837.html?fr=sycsrp_catchall">Judge denies motion to dismiss DRAM price-fixing lawsuit ...</a></li>
<li><a href="https://wccftech.com/federal-judge-rejects-memory-makers-defense-samsung-micron-sk-hynix-dram-shortage-lawsuit/">Federal Judge Rejects Memory Makers’ Defense To Advance Class ...</a></li>
<li><a href="https://www.idc.com/resource-center/blog/global-memory-shortage-crisis-market-analysis-and-the-potential-impact-on-the-smartphone-and-pc-markets-in-2026/">Global Memory Shortage Crisis: Market Analysis and the ... - IDC</a></li>

</ul>
</details>

**Tags**: `#DRAM`, `#antitrust litigation`, `#price fixing`, `#Micron`, `#Samsung/SK Hynix`

---