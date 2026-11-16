---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 44 items, 9 important content pieces were selected

---

**Technology News**
1. [vLLM v0.34.0 defaults to extensible KV cache and removes Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Alibaba launches Qwen4-Max with 2.4T sparse MoE and million-token context](#item-tech-news-2) ⭐️ 8.0/10
3. [Jiff 1.0 Released: A Datetime Library for Rust](#item-tech-news-3) ⭐️ 7.0/10
4. [Marimba: frozen ASR encoder for calibrated speech queries](#item-tech-news-4) ⭐️ 7.0/10
5. [duetto steers a pretrained music transformer for live jazz without fine-tuning](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s October retail sales, industrial output and investment all miss forecasts](#item-finance-news-1) ⭐️ 8.0/10
2. [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties and holdings](#item-finance-news-2) ⭐️ 8.0/10
3. [美国将先进 AI 芯片出口管制延伸至远程访问](#item-finance-news-3) ⭐️ 8.0/10
4. [Intel and CEO Face Shareholder Class Action Over Weak PC Demand Disclosures](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 defaults to extensible KV cache and removes Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 makes extensible KV cache sizing the default on CUDA and ROCm: the cache is sized from memory actually free after warmup, which the project says raises capacity \(for example, MiniMax-M3 on H200 from 433k to 672k tokens\) and improves throughput at high concurrency. The release also removes Model Runner V1, leaving V2 as the only GPU runner, and changes the default \`--block-size\` from 16 to 64. It adds 10 models, including Mistral Large 4 and NVIDIA Nemotron-3.5-Transcribe, and reports speedups such as up to 1.95× decode for Step5 on 4×GB200. Upgraders must remove \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\`, use ROCm 10.0 artifacts because ROCm 7.2 images are no longer published, and install \`huggingface\_hub &gt;= 2.0.0\`; the project warns that per-token decode latency can rise 6–18% on some H200 models at concurrency 128.

github · khluu · Nov 16, 23:22

**「Background」** vLLM allocates a KV cache at startup to hold the attention keys and values for requests in flight; before this release, capacity was derived from a configured GPU-memory-utilization estimate. v0.34.0 instead measures memory left after CUDA graph capture and warmup, and it completes the move to Model Runner V2 by removing the older V1 runner, so configurations that explicitly selected V1 now fail at startup.

**「Impact」** Existing deployments that relied on the old KV-cache estimate or the V1 runner need configuration changes before upgrading: setting \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\` now fails at startup, and retaining the previous cache sizing requires \`--gpu-memory-utilization 0.9\` or \`--no-enable-extensible-kv-cache\`. Teams that accept the new default should validate per-token latency, because the release reports TPOT increases of 6–18% on some H200 models at concurrency 128 even as high-concurrency throughput improves.

**Tags**: `#vLLM`, `#LLM inference`, `#KV cache`, `#model serving`, `#hardware acceleration`

---

<a id="item-tech-news-2"></a>
### [Alibaba launches Qwen4-Max with 2.4T sparse MoE and million-token context](https://mp.weixin.qq.com/s/pJUt0xwD6H-WMyzd8TjZaQ) ⭐️ 8.0/10

Alibaba&\#x27;s Qwen team launched Qwen4-Max, a flagship sparse mixture-of-experts model with 2.4 trillion total parameters, native vision understanding, and a million-token context window. The model is live now, and the team says it plans to release smaller Qwen4-series models with public weights later. The launch post claims strong coding, office, and long-horizon task performance, including front-end coding results near the top of a Code Arena blind test, but those rankings have not been independently verified. It also claims average cost per task fell from 26.58 yuan to 11.16 yuan, about 58%, while token consumption dropped nearly 50% and API prices were lowered; these cost figures are vendor claims.

telegram · zaihuapd · Nov 16, 02:52

**「Background」** Qwen4-Max is the latest flagship in Alibaba&\#x27;s Qwen model family; Alibaba Cloud&\#x27;s release describes it as the family&\#x27;s most capable model to date. It uses a sparse mixture-of-experts design, which spreads a very large total parameter count across many expert subnetworks but activates only a subset for each token, so the 2.4 trillion total is not the amount of computation used per token.

**「Impact」** Developers can use the million-token context and lower stated API prices for long coding or document tasks, but the open-weight plan announced so far names smaller Qwen4 models rather than the 2.4T-parameter flagship, so self-hosting teams have no release date or weight availability for Qwen4-Max.

<details><summary>References</summary>
<ul>
<li><a href="https://www.alibabacloud.com/en/press-room/alibaba-unveils-qwen4-max?_p_lc=1">Alibaba Unveils Qwen4-Max: New AI Teammate for Work ...</a></li>
<li><a href="https://www.alibabacloud.com/blog/alibaba-unveils-qwen4-max-new-ai-teammate-for-work-creativity-and-discovery_603783">Alibaba Unveils Qwen4-Max: New AI Teammate for Work ...</a></li>

</ul>
</details>

**Tags**: `#Qwen`, `#Mixture-of-Experts`, `#large language models`, `#multimodal AI`, `#open-weight models`

---

<a id="item-tech-news-3"></a>
### [Jiff 1.0 Released: A Datetime Library for Rust](https://burntsushi.net/jiff/) ⭐️ 7.0/10

Jiff has reached version 1.0, a stable release of the Rust datetime library from author burntsushi. The release matters to Rust developers choosing among date-and-time crates, where chrono has long been the established option. The supplied material does not include release notes, API specifics, or migration guidance, so the concrete changes from pre-1.0 versions are not established here.

hackernews · burntsushi · Nov 16, 16:53 · [Discussion](https://news.ycombinator.com/item?id=50519744)

**「Why a second Rust datetime crate matters」** Rust&\#x27;s ecosystem has long relied on chrono as its established date-and-time crate, and commenters frame Jiff&\#x27;s 1.0 release largely as a question of whether that default will shift. A commenter who says they maintained chrono for roughly half a decade describes the trap that made improving it hard: users depended on its stable API, so even small steps toward a better design met resistance. That tension over API stability versus redesign is the context in which Jiff arrives.

**「Impact for Rust developers」** Developers starting new Rust projects can adopt Jiff 1.0 where DST-gap and ambiguous-local-time handling matters, since a September 2026 comparison found Jiff handles those cases that chrono leaves to the caller. Teams with large existing codebases or dependencies already built on chrono face a migration cost, and that comparison recommends staying on chrono in those situations.

**「Community Discussion」** A former chrono maintainer, quodlibetor, said he took on that project hoping to improve its API but encountered resistance to changes and left because of burnout, and he thanked burntsushi for writing Jiff. Other commenters praised Jiff&\#x27;s explicit acknowledgment that it is not always the right tool and hoped for wider adoption over chrono, while one user asked whether additional time scales such as UT1 could be supported for long-span orbital simulations.

<details><summary>References</summary>
<ul>
<li><a href="https://www.pistack.xyz/posts/2026-09-21-rust-datetime-libraries-chrono-jiff-time-hifitime-comparison/">Tired of Timezone Bugs in Rust? chrono vs jiff vs time vs ...</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/">jiff - Rust - Docs.rs</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#datetime`, `#library release`, `#open source`, `#time zones`

---

<a id="item-tech-news-4"></a>
### [Marimba: frozen ASR encoder for calibrated speech queries](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

A Reddit post summarizes Marimba, a lightweight speech-query model for researchers and developers: it answers typed yes/no, multiple-choice, and score questions about 8-second audio windows using one frozen Qwen3-ASR-0.6B encoder pass and calibrated readouts, returning a probability. The post reports that Marimba matches or beats Qwen3-Omni \(30B-A3B\) on 6 of 9 public tests, reaches 100% language ID on 300 FLEURS clips, and achieves speaker-change AUROC of 0.966–0.980 on AMI and VoxConverse; these results are self-reported, and the turn-end row is in-distribution because its readout was trained on Smart Turn data. It trails Smart Turn v3.2 on turn-end detection \(0.930 vs 0.982 AUROC\), ties on ICSI meetings \(0.716 vs 0.712\), and every head is at chance on CochlScene, so it does not generalize to unseen tasks. Code and Apache-2.0 weights are available, with \`pip install marimba-audio\` and a Hugging Face demo.

reddit · r/MachineLearning · /u/solanotodesch · Nov 16, 15:47

**「Background」** Qwen3-ASR-0.6B is the compact open-weight member of the Qwen3-ASR family, which also includes a 1.7B model; its documentation covers multilingual speech recognition and language identification across 30 languages and 22 Chinese dialects. Marimba uses that pretrained ASR encoder as a fixed feature extractor rather than fine-tuning the encoder itself.

**「Deployment trade-off」** Teams can replace several single-purpose speech models with one frozen Qwen3-ASR-0.6B encoder pass per 8 s window, since term spotting, language ID, turn end, and speaker change/count all read out from that shared pass, and the Apache-2.0 weights plus \`pip install marimba-audio\` make it directly testable. The trade-off is task coverage: every head sat at chance on CochlScene scene classification, and turn-end detection trails Smart Turn v3.2 \(AUROC 0.930 vs 0.982\) on Smart Turn&\#x27;s own test set, so adopters should validate each head on their own data rather than assume the combined model matches dedicated systems.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/Qwen/Qwen3-ASR-0.6B">Qwen/ Qwen 3 - ASR - 0 . 6 B · Hugging Face</a></li>
<li><a href="https://deepinfra.com/Qwen/Qwen3-ASR-0.6B/api">Qwen 3 ASR 0 . 6 B API - Documentation - DeepInfra</a></li>
<li><a href="https://benchlm.ai/models/qwen3-asr-0-6b">Qwen 3 - ASR 0 . 6 B Context, Specs &amp; Sources (September 2026)</a></li>

</ul>
</details>

**Tags**: `#speech recognition`, `#audio foundation models`, `#calibration`, `#model efficiency`, `#zero-shot learning`

---

<a id="item-tech-news-5"></a>
### [duetto steers a pretrained music transformer for live jazz without fine-tuning](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

duetto, a project shared on Reddit, is a real-time jazz MIDI partner that can solo, comp, or play walking bass alongside a keyboardist and takes a solo when the player stops. Instead of fine-tuning, it steers a pretrained Anticipatory Music Transformer at sampling time: a rule layer masks disallowed events and biases likely ones, including chord tones, downbeat guide tones, and phrases from the Weimar Jazz Database segmented at breath points. A demo and code are available, with the code free for noncommercial use; in the demo about 61% of solo notes come from quoted phrases or the theme, and the author reports roughly 12 ms per note for the medium model and 18 ms per note for the large model on a 3080 Ti, versus about 90 ms per note for the large model on a Jetson Orin Nano. The server keeps about one second of music sampled ahead and resamples unplayed music when the player plays, but the author says it can drift from the player, respond unpredictably, and become fragile when balancing model ideas against rule-based bias.

reddit · r/MachineLearning · /u/GGAllin43 · Nov 16, 09:19

**「Background」** The project builds on the Anticipatory Music Transformer, a pretrained autoregressive model for symbolic music introduced by Thickstun et al. in 2023 \(arXiv:2306.08620\). Its design interleaves musical events with control sequences for music-control tasks. Duetto leaves that model unchanged and adds its rule-based control only at sampling time.

**「Practical consequence」** For developers building real-time symbolic music systems, the author&\#x27;s reported throughput—roughly 12–18 ms per note on a desktop RTX 3080 Ti and about 90 ms per note on a Jetson Orin Nano—indicates that sampling-time steering can fit a live-play latency budget without fine-tuning. The same report notes that the model can drift from the player and that the bias strength is fragile to tune, and the released code is free only for noncommercial use.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer</a></li>
<li><a href="https://github.com/jthickstun/anticipation">GitHub - jthickstun/ anticipation : Anticipatory Autoregressive Models</a></li>

</ul>
</details>

**Tags**: `#music generation`, `#transformer models`, `#sampling-time control`, `#real-time inference`, `#open-source code`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s October retail sales, industrial output and investment all miss forecasts](https://www.cnbc.com/2026/11/16/china-retail-sales-october-industrial-output-investment.html) ⭐️ 8.0/10

China&\#x27;s October retail sales, industrial output and fixed-asset investment all came in below economists&\#x27; estimates, with retail sales up just 0.4% from a year earlier against a forecast 0.8% rise \(September: 1.1%\), and fixed-asset investment down 8.1% in the first ten months of the year versus an expected 7% decline.

rss · CNBC Finance · Nov 16, 03:53

**「Background」** Consumption has lagged industrial output — which grew 4.8% in October versus a forecast 5.3% — as a property downturn now in its fifth year erodes household wealth, while the investment measure covers spending on property, infrastructure and equipment and is contracting at a pace the report says is unprecedented outside the Covid-19 period.

**「Impact」** With exports up 35.2% in October, growth is leaning more heavily on foreign demand, and Citi Research analysts cited in the report said additional EU trade measures are a plausible risk for China&\#x27;s export-reliant manufacturers next year.

**Tags**: `#China economy`, `#macroeconomic data`, `#retail sales`, `#industrial output`, `#fixed-asset investment`

---

<a id="item-finance-news-2"></a>
### [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties and holdings](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

Commerce Secretary Howard Lutnick faces questions over his former firm Cantor Fitzgerald&\#x27;s ties to Nvidia and a nearly 50% decline in the number of Nvidia shares it reported holding between September 2025 and March 2026, CNBC reported, citing securities filings. The scrutiny follows an Axios report dated Nov. 11 that Lutnick repeatedly resisted pressure to crack down on Megaspeed, a Singapore-based company suspected of funneling Nvidia AI chips to China; no wrongdoing has been proven, and Cantor said its Nvidia positions were immaterial and entered into in the ordinary course of business tied to client swap transactions.

rss · CNBC Finance · Nov 16, 12:14

**「Background」** Howard Lutnick ran the Wall Street firm Cantor Fitzgerald before becoming commerce secretary in February 2025; his sons now lead it, and his department is the agency responsible for the entity list, which names companies that U.S. firms are restricted from selling to. The scrutiny follows reports that Nvidia CEO Jensen Huang acknowledged an affair with an executive at Megaspeed, a Singapore-based cloud provider suspected of funneling Nvidia chips to China.

**「Impact」** Nvidia faces heightened U.S. scrutiny over alleged China-related chip sales—Treasury Secretary Scott Bessent has pressed it for answers and CEO Jensen Huang has resigned—creating leadership and export-control risk for the chipmaker and partners such as IREN.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/09/megaspeed-nvidia-jensen-huang-alice-huang.html">What is Megaspeed? Nvidia customer in spotlight after Jensen ...</a></li>
<li><a href="https://edition.cnn.com/2026/11/16/tech/nvidia-sex-spies-serious-problems">Lies, spies and sex are just one part of the Nvidia story.</a></li>
<li><a href="https://www.globaltimes.cn/page/202611/1374387.shtml">US Treasury chief presses Nvidia over alleged chip sales to China ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#US-China relations`, `#Commerce Department`, `#conflict of interest`

---

<a id="item-finance-news-3"></a>
### [美国将先进 AI 芯片出口管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 8.0/10

美国商务部于11月16日发布临时最终规则，将先进 AI 芯片和服务器的出口管制扩大至远程访问，以阻止通过第三国数据中心规避限制；据 The Verge 报道，该规则还要求向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口 AI 芯片须申请许可。来源报道称，这可能会进一步收紧中国获取先进芯片的渠道，但该规则的具体条文和生效日期尚未披露。

telegram · zaihuapd · Nov 16, 14:44

**「Background」** Washington already restricted direct exports of advanced AI chips to China, and renting computing power from data centers abroad had remained a way around those limits. The Commerce Department&\#x27;s Bureau of Industry and Security issued the change as an interim final rule, a regulation that takes effect before public comment is complete.

**「Impact」** Data-center operators in Singapore, Malaysia, Thailand, Indonesia and Brazil would need US licenses before renting advanced AI chips to foreign users, hitting Nvidia, whose chips are rented to Chinese AI developers through Southeast Asian data centers, according to Politico.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/the-u-s-shuts-chinas-access-to-advanced-chips-via-singapore-brazil-indonesia-malaysia-and-thailand-as-scott-bessent-gives-nvidia-10-days-to-show-it-did-not-goose-its-revenues/">The U.S. Shuts China&#x27;s Access To Advanced Chips Via Singapore...</a></li>
<li><a href="https://blog.prompt20.com/posts/ai-chip-export-controls-complete-guide/">AI Chip Export Controls : The Complete Guide</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/commerce-closes-chinas-backdoor-to-nvidia-chips-after-white-house-steps-in-01167199">Commerce closes China’s backdoor to Nvidia chips after White ...</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China’s Remote Access to Nvidia’s AI Chips</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#US Commerce Department`, `#data centers`, `#semiconductor policy`

---

<a id="item-finance-news-4"></a>
### [Intel and CEO Face Shareholder Class Action Over Weak PC Demand Disclosures](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

Intel, CEO Lip-Bu Tan and CFO David Zinsner were sued in a proposed shareholder class action in San Jose federal court alleging the chipmaker concealed soft PC demand and inventory buildup before its October 29 guidance. The day after Intel&\#x27;s fourth-quarter revenue and profit forecast fell short of expectations, the shares dropped 28.6% — a loss of roughly $140 billion in market value — and the suit, led by a Michigan pension fund, seeks damages for investors who bought stock between July 23 and October 29, 2026.

telegram · zaihuapd · Nov 16, 11:10

**「Background」** The lawsuit follows Intel’s Oct. 29 forecast, which flagged weak PC demand and supply-chain constraints and came before an almost 29% one-day stock drop — the company’s worst rout in more than four decades, according to Bloomberg.

**「Affected investors」** The proposed class covers investors who bought Intel shares between July 23 and October 29, 2026, so those shareholders could be directly affected as potential class members; the claims are allegations and have not been proven.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-10-29/intel-outlook-hurt-by-weak-market-for-personal-computer-chips">Intel Earnings: (INTC) Stock Sinks After PC Slump, Supply ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/intel-shares-fall-6-shareholders-171000158.html?fr=sycsrp_catchall">Intel shares fall 6% as shareholders sue over October stock ...</a></li>
<li><a href="https://www.techpowerup.com/354906/intel-faces-class-action-lawsuit-over-pc-sales-slowdown-disclosures">Intel Faces Class Action Lawsuit Over PC Sales Slowdown ...</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#shareholder class action`, `#stock plunge`, `#earnings guidance`, `#semiconductor`

---