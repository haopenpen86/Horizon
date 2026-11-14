---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 32 items, 7 important content pieces were selected

---

**Technology News**
1. [Lovable-built apps exposed passport data and over 200K messages via RLS flaws](#item-tech-news-1) ⭐️ 8.0/10
2. [SpaceX catches Starship upper stage to end Flight 15](#item-tech-news-2) ⭐️ 8.0/10
3. [EFF Warns Tech Companies Are Redefining Privacy Again](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI Reportedly Disbands Standalone Robotics Team for General Models](#item-tech-news-4) ⭐️ 7.0/10
5. [Italy Fines Meta €805M Over Facebook Android Gallery Access](#item-tech-news-5) ⭐️ 7.0/10

**Technology Blog**
1. [Finding Meaning in Large Tech Companies](#item-tech-blog-1) ⭐️ 5.0/10

**Financial News**
1. [Cantor Fitzgerald cut reported Nvidia stake amid Lutnick scrutiny](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lovable-built apps exposed passport data and over 200K messages via RLS flaws](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

Security research from Crissy Field reports that misconfigured Row-Level Security in apps built with Lovable exposed passport details and more than 200,000 private messages. Lovable&\#x27;s head of security acknowledged in comments that insufficient RLS was the root cause and said the platform scans every app automatically before publish and offers a deeper SAST scan, both free, with a &quot;Fix&quot; option and background auto-fix for findings. The disclosure does not quantify how many apps or users were affected beyond those exposed records.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「Background」** Row-Level Security is a PostgreSQL feature, used by Supabase, that determines which rows a client can read or write. In a Lovable app backed by Supabase, missing or overly broad policies can let a public client key reach private tables even when the interface does not expose them.

**「Impact」** Developers running Lovable/Supabase apps should audit each table&\#x27;s RLS policies and test access with the public client key before treating the deployment as safe; the reported exposures stemmed from insufficient policies, not a defeated login system. Lovable presents scanning and auto-fix as backstops, but teams still need to verify the deployed database configuration and restrict public access to sensitive tables.

**「Community discussion」** Commenters debated where responsibility lies: one argued that Supabase&\#x27;s permissive defaults were a deliberate onboarding tradeoff and cited a Supabase discussion in which the issue was supposedly fixed on October 30, but said reports indicate existing projects still use the old defaults. Another called for deny-by-default databases, least-privilege APIs, and automated authorization tests so that AI-generated apps are harder to deploy insecurely.

**Tags**: `#security`, `#row-level-security`, `#supabase`, `#lovable`, `#data-exposure`

---

<a id="item-tech-news-2"></a>
### [SpaceX catches Starship upper stage to end Flight 15](https://x.com/i/broadcasts/2brajgZlOKRMka) ⭐️ 8.0/10

SpaceX caught the Starship upper stage at its Starbase launch tower to end Flight 15, the Nov. 13 test launch from Texas, according to the broadcast-linked report. The booster missed its planned tower catch: after a technical issue aborted its return, it made a controlled splashdown in the Gulf of Mexico and exploded, and SpaceX did not disclose the cause. The ship reached orbit, deployed all 26 Starlink V3 satellites—three carrying cameras to inspect the heat shield—and returned for what the report described as the first tower catch of an orbital-class ship.

hackernews · ls612 · Nov 14, 21:22 · [Discussion](https://news.ycombinator.com/item?id=50500963)

**「Background」** A tower catch uses the launch tower’s mechanical arms to grab a returning vehicle at the pad rather than landing it on legs or splashing down. Flight 15 was the first Starship test in which SpaceX tried to recover both stages this way: the Super Heavy booster after ascent and the Ship after about 22 hours in orbit, following deployment of 26 Starlink V3 satellites. The booster missed its catch and splashed down in the Gulf, while the Ship returned to Starbase for the first orbital-class ship catch.

**「Payload design and the cost case」** Satellite operators planning around Starship can build larger spacecraft that skip complex folding mechanisms, an industry analysis notes, and Flight 15&\#x27;s deployment of all 26 Starlink V3 satellites on one ship illustrates the per-launch capacity that makes that worthwhile. The cost benefit remains a target rather than a measured result: third-party analyses put SpaceX&\#x27;s marginal cost goal at $20–30 million per flight, which depends on re-flying ships and reusable heat shields — three of the 26 satellites carried cameras to inspect tile condition, and no post-flight assessment has been reported.

**「Community discussion」** Commenters celebrated the catch, with one arguing that the next step is re-flying the same ships and repeating the catch so orbital payloads become significantly cheaper, contingent on the heat shield holding up. Another focused on the booster miss, suggesting that a couple more tonnes of propellant might have allowed a dual catch and noting uncertainty over Starship&\#x27;s final mass fraction to orbit.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/14/spacex-plans-to-try-first-ever-catch-of-starship-rocket-from-orbit.html">SpaceX catches upper stage of Starship rocket in historic first</a></li>
<li><a href="https://www.floridatoday.com/story/tech/science/space/spacex/2026/11/13/spacexs-starship-flight-15-launches-from-texas-reaches-orbit-but-misses-booster-catch/92758185007/">SpaceX&#x27;s Starship Flight 15 launches from Texas, misses ...</a></li>
<li><a href="https://www.usatoday.com/story/tech/space/2026/11/14/spacex-flight-15-catches-starship-makes-history/92785462007/">SpaceX catches Starship for first time at Texas launch tower</a></li>
<li><a href="https://newspaceeconomy.ca/2026/02/10/the-economics-and-logistics-of-starship-operations-2026-status-and-future-outlook/">The Economics and Logistics of Starship Operations: 2026 ...</a></li>
<li><a href="https://spaceodysseyhub.com/articles/starship-economics-investor-analysis-2026">Starship Economics: An Investor&#x27;s Field Manual (2026)</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#reusable launch`, `#spaceflight hardware`, `#engineering milestone`

---

<a id="item-tech-news-3"></a>
### [EFF Warns Tech Companies Are Redefining Privacy Again](https://www.eff.org/deeplinks/2026/11/tech-companies-are-trying-shift-entire-concept-privacy-again) ⭐️ 7.0/10

The EFF published a critique arguing that technology companies are renewing efforts to redefine the concept of privacy, framing the shift as a policy and digital-rights concern rather than a new product launch. The piece does not announce a specific technical change; it warns that industry rhetoric is being used to reshape how privacy is understood. The accompanying discussion focuses on workplace AI notetakers and practical ways individuals might limit data exposure.

hackernews · gslin · Nov 14, 12:45 · [Discussion](https://news.ycombinator.com/item?id=50496602)

**「Context: from personal choice to bystander exposure」** The EFF piece is by Thorin Klosowski, who frames the shift as privacy moving from an individual choice to a bystander problem: people who never agreed to be recorded are exposed by devices worn or used by others. It cites concrete ambient-recording products as the driver — Meta and Google smart glasses that record what the wearer sees and use AI to describe it, Apple&\#x27;s Audio Intelligence feature turning the Apple Watch into a transcription device, and Amazon&\#x27;s Bee devices that can record and transcribe continuously. The argument is that pendants, rings, and similar wearables make recording and summarizing other people&\#x27;s daily activity routine rather than exceptional.

**「Practical impact」** For employees and meeting participants, opting out of AI notetaking depends on workplace policy rather than any technical control: consent requirements vary by jurisdiction, and notetakers differ in how they store transcripts and whether data is used for model training, so those practices must be verified per tool \(tool-3-1, tool-3-3\). Organizations deploying notetakers therefore need an explicit consent and retention policy before recording 1:1s, because a colleague&\#x27;s request to switch the bot off carries no built-in enforcement.

**「Community Discussion」** Commenters described workplace AI notetakers recording even 1:1 manager conversations, with one asking whether employees can establish a norm of turning transcription off when it is not needed. Others argued that data fusion violates privacy protections such as Article 12 of the Universal Declaration of Human Rights, while another questioned why current recording products should face less backlash than Google Glass did.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.my/items/46520/tech-companies-are-trying-to-shift-the-concept-of-privacy-again">Tech Companies Are Trying to Shift the Concept of Privacy (Again)</a></li>
<li><a href="https://briefly.co/anchor/Privacy_technologies/story/tech-companies-are-trying-to-shift-the-entire-concept-of-privacy-again">Key takeaways: Tech Companies Are Trying to Shift the Entire ...</a></li>
<li><a href="https://smartkeys.org/ai-meeting-notetaker-policy/">AI Note-Takers in Meetings: Consent, Privacy and Etiquette Rules</a></li>
<li><a href="https://fireflies.ai/blog/are-ai-notetakers-safe">Are AI Notetakers Safe? Privacy Risks, Consent Laws, and What ...</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#AI notetakers`, `#surveillance`, `#data fusion`, `#digital rights`

---

<a id="item-tech-news-4"></a>
### [OpenAI Reportedly Disbands Standalone Robotics Team for General Models](https://fortune.com/2026/11/13/openai-disbands-robotics-team-as-its-general-models-start-running-robots/) ⭐️ 7.0/10

OpenAI has reportedly disbanded its independent robotics team and reassigned its researchers to more general research groups, according to a brief secondhand summary citing Fortune. The company said robotics remains central to its long-term vision and that the change reflects general frontier models, including the unverified GPT-6 Astra, being able to control robots directly without a dedicated robotics team. The item provides no technical detail or primary confirmation, and its claims about GPT-6 Astra and a 2027 public demonstration remain unverified. It also notes that OpenAI&\#x27;s earlier robotics team was dissolved in 2020, a team was rebuilt in 2024 with a Figure partnership that ended in February 2025, and OpenAI is still developing a humanoid robot, with its CEO targeting a first public showing in 2027.

telegram · zaihuapd · Nov 14, 04:00

**「Background」** OpenAI has cycled through robotics work before: it disbanded an earlier robotics team in 2020, rebuilt robotics efforts in 2024, and partnered with Figure AI before that partnership ended in February 2025. The company has also said it still aims to show a humanoid robot publicly in 2027, so the latest reorganization changes the team structure rather than abandoning the stated goal.

**「Impact」** For developers and researchers tracking OpenAI&\#x27;s embodied-AI work, the reported reorganization removes a standalone robotics group as a visible point of contact and makes general model releases, rather than a dedicated robotics program, the main signal of progress; the stated 2027 demonstration target is the concrete checkpoint mentioned, though it is unconfirmed.

<details><summary>References</summary>
<ul>
<li><a href="https://theroboticsmedia.com/article/openai-disbands-robotics-team-gpt-6-astra">OpenAI Disbands Robotics Team, Bets on GPT-6 Astra Instead</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#robotics`, `#general-purpose AI`, `#humanoid robots`, `#organizational change`

---

<a id="item-tech-news-5"></a>
### [Italy Fines Meta €805M Over Facebook Android Gallery Access](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10321080) ⭐️ 7.0/10

Italy&\#x27;s data protection authority fined Meta €805 million, saying Facebook&\#x27;s Android app accessed the photos, videos, and metadata of about 20 million Italian users without specific consent. The regulator tied the case to a gallery-recommendation feature introduced in 2023 that was enabled by default and used a vague permission prompt. It ordered Meta to make the feature default-off with separate consent within 60 days; otherwise it cannot be enabled for users who have not validly authorized it.

telegram · zaihuapd · Nov 14, 14:37

**「Background」** The penalty concerns a Facebook feature available since 2023 that suggests photos and videos from a smartphone gallery for users to post. Italy’s data-protection authority examined how the Android app accessed those gallery files without explicit consent.

**「Impact」** Meta must within 60 days change the gallery-recommendation feature to default-off and obtain separate consent in Italy, or disable it for users without valid authorization. The order makes the permission prompt and default setting, not just the underlying data access, the compliance target for the Android app.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/articles/italy-fines-meta-805-million-161834604.html?fr=sycsrp_catchall">Italy fines Meta €805 million over Android app&#x27;s photo access</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-14/italy-fines-meta-805-million-over-access-to-users-photos">Italy Fines Meta €805 Million Over Access to Users’ Photos</a></li>

</ul>
</details>

**Tags**: `#隐私监管`, `#Meta`, `#Android 权限`, `#用户同意`, `#科技行业合规`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Finding Meaning in Large Tech Companies](https://seangoedecke.com/how-to-find-meaning-in-large-tech-companies/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 14, 00:00

**「Background」** Sean Goedecke asks why engineers often dislike working in large tech companies. He rejects the simple explanation that organizational dysfunction merely blocks them from shipping code, arguing instead that many engineers have a visceral compulsion toward neatness and avoid even thinking about mess.

**「Solution」** The author also points to alienation from role-playing: pretending that OKRs, deadlines, internal training, and hype are deeply important can eventually make importance itself feel illusory. Drawing on his philosophy background, he suggests the existential response is to stop over-philosophizing and stay in contact with things that matter outside work. Yet he argues that large tech companies still offer a real source of meaning: improving software used by millions. A niche app may let an engineer take satisfaction from craft, but making Teams slightly better improves millions of lives; each bug fix or feature can save cumulative months or years of users’ time. This remains true, he says, even for enterprise software that is steadily getting worse, because slowing the decline is valuable. The work is hard—technical difficulty intersects with organizational difficulty—and requires tolerance for mess plus a rich enough personal life to treat office politics with detachment.

**「Takeaway」** Goedecke’s conclusion is that large tech companies can be a rich source of meaning, not despite their mess but through the valuable, difficult work of improving widely used software at scale; engineers need perspective and detachment to access it.

**Tags**: `#large tech companies`, `#workplace meaning`, `#organizational dysfunction`, `#software engineering careers`, `#career essay`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Cantor Fitzgerald cut reported Nvidia stake amid Lutnick scrutiny](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

Cantor Fitzgerald, formerly led by Commerce Secretary Howard Lutnick and now run by his sons, reported a 49% drop in the number of Nvidia shares it held between September 2025 and March 2026, to 1.78 million shares, while keeping financing ties to the chipmaker amid scrutiny of Lutnick’s export-control decisions, CNBC reported. CNBC found no evidence that the stake change was tied to intelligence warnings about Nvidia CEO Jensen Huang or that Cantor’s business interests influenced Lutnick’s decisions.

rss · CNBC Finance · Nov 13, 23:42

**「Background」** Jensen Huang resigned as Nvidia&\#x27;s chief executive this week amid reports that a woman linked to him was suspected of being a Chinese spy; he and Commerce Secretary Howard Lutnick have been summoned to testify before a Senate committee next month. The Commerce Department, which Lutnick leads, enforces U.S. chip export controls, and Axios reported that Lutnick repeatedly resisted curbs on Megaspeed, a Singapore-based data-center company suspected of funneling Nvidia chips to China.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/live/2026/11/12/business/nvidia-jensen-huang-resigns">Nvidia Updates: Huang ’s Resignation Reverberates Through...</a></li>
<li><a href="https://www.theguardian.com/technology/live/2026/nov/13/nvidia-jensen-huang-to-testify-before-congress-live-latest-updates">Calls for crackdown on China chip exports – as it happened | Nvidia</a></li>
<li><a href="https://www.axios.com/2026/11/11/trump-lutnick-nvidia-china-chip-export-controls">Trump backed Nvidia chip controls aimed at China 3 times as...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#conflict of interest`

---