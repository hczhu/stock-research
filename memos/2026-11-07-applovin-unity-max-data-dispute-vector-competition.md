tags:: [[$APP]], [[$U]], [[AppLovin]], [[Unity]], [[ironSource]], [[AXON]], [[Vector]], [[MAX]], [[LevelPlay]], [[ad-mediation]], [[header-bidding]], [[take-rate]], [[mobile-gaming]], [[advertising]], [[litigation]], [[Mintegral]]
file-created-at:: 2026-11-07

- ## AppLovin vs Unity: the MAX data dispute, and what it says about the Vector threat
	- **Source**: Third-party research note on the AppLovin–Unity rivalry (excerpt: the litigation analysis and the technical setup for a publisher survey; the five-publisher findings themselves weren't included). Allegations come from AppLovin's filings and letters, and Unity's positions from its Sept 4 and later letters, as summarized by the note. None of it has been decided. Related: [[APP-2026-Q3]], [[2026-03-28-Unity-thiughts-from-a-Applovin-bull-2026-02]], [[2026-03-28-applovin-vs-meta-ad-monetization-2025q4]].
	- **Thesis**: The dispute is evidence that **Unity's Vector became a real competitor inside MAX in Q2 2026**. The note argues that Unity's in-app-ad (IAA) D28 business grew as much in one quarter as its in-app-purchase (IAP) D28 business had over several, and that this hit AppLovin's core ads business. AppLovin's Q2 revenue was about 1% below the top of its guide, a weak result by its standards. Three weeks later it sent a cease-and-desist letter. AppLovin alleges that Unity's Ad Quality SDK has scraped data on the ads AppLovin wins in MAX since at least May 2025. Unity says it collects ad data, but not from AppLovin, and that AppLovin's own tool does more. For investors the legal outcome matters less than two economic questions: did the data help Vector catch up, and does turning it off widen the gap with AXON again?
- ## What AppLovin alleges
	- **The contract**: under the Oct 13, 2021 "AppLovin Header Bidding Agreement," Unity bids into MAX. Section 2.4(c) limits bid-request data to use "solely to bid on Inventory made available via the Mediation Platform."
	- **The data**: since at least May 2025, Unity's Ad Quality SDK allegedly collected data on ads AppLovin won and displayed. That includes creatives, landing pages, advertiser and campaign IDs, device and user IDs, revenue per impression, MAX bidding and waterfall data, and the coordinates of the user's last screen tap.
	- **The method**: Unity allegedly "hook[ed] into AppLovin callbacks and inject[ed] Unity code into its ads." That is active interception, not passive observation.
	- **The motive (speculative)**: AppLovin suspects the data trained Vector, but its public filings contain no direct evidence of that.
- ## Timeline
	- | Date | Event |
	  |---|---|
	  | Oct 13, 2021 | Header bidding agreement signed; Unity becomes a MAX bidder |
	  | May 28, 2025 | Unity LevelPlay 8.9.0 starts bundling Ad Quality; AppLovin says collection began by then |
	  | Aug 5, 2026 | AppLovin Q2: revenue ~1% below the guide high end, but a Q3 guide implying QoQ acceleration |
	  | Aug 21, 2026 | Cease-and-desist letter, 14 days to respond |
	  | Sep 4, 2026 | Unity refuses: "Ad Quality does not collect any data from AppLovin" |
	  | Sep 8 and Sep 14, 2026 | AppLovin issues 72-hour, then 48-hour ultimatums with added demands |
	  | Sep 11, 2026 | First concession: tell publishers within 5 business days to disable Ad Quality on MAX; ship an SDK without it within 30 days |
	  | Sep 16, 2026 | Second concession: remotely switch off collection in MAX bidding (including ironSource Ads) and delete data under normal retention. Refuses to retrain or remove its model. Conditional on AppLovin confirming in writing that the dispute is settled |
	  | Sep 27, 2026 | AppLovin files for JAMS arbitration |
	  | Oct 2, 2026 | Court denies a TRO and a preliminary-injunction hearing |
	- **What the sequence suggests**: Unity moved from flat denial to two concessions in 12 days, which suggests it saw real legal exposure. But it never agreed to touch Vector, which suggests it sees the model as the asset worth protecting. AppLovin turned down the conditional offer and filed for arbitration, so it wants more than an off-switch. The court's refusal of emergency relief means arbitration will be slow, and nothing forces Unity to change its model in the meantime.
	- **Unknown from the excerpt**: whether Unity actually switched off collection after AppLovin rejected the conditional terms. The Sept 11 publisher notice wasn't described as conditional; the Sept 16 remote switch-off was.
- ## Unity's defense
	- **Collection admitted, source disputed**: Unity says collection began "since well before the parties entered into those agreements," targeted ads won in MAX bidding, and drew on publisher apps and user devices with authorization. It denies the data came from AppLovin but doesn't deny collecting data on MAX-won ads.
	- **AppLovin knew**: Unity argues AppLovin has known about it for a long time. If so, the timing of the complaint (just after a weak quarter) looks commercially motivated, not a new discovery.
	- **Remote control**: Unity can switch collection off remotely, including Ad Quality inside ironSource Ads. That undercuts its implied claim that the SDK merely observes passively.
	- **Counteraccusation**: Unity says AppLovin's own Ad Review is more invasive, is on by default for all MAX publishers, collects impression data on Unity Ads and other networks, and that MAX gives AppLovin's own DSP extra support. This contradicts AppLovin's Q3-call statement that AXON sees only win/loss and clearing prices ([[APP-2026-Q3]]), and it is the self-preferencing argument in a new form.
- ## Can other ad networks do this?
	- **The precedent**: in 2020, Mintegral's SDK intercepted competitors' ad-click data in thousands of apps. Once that came out, platforms delisted it and Mintegral stopped. AppLovin calls Ad Quality the same kind of conduct, only more serious.
	- **Only mediation owners can**: most DSPs don't have an SDK in the app that can see other networks' ads. Companies that run both a DSP and a mediation layer can, through ad-quality tools: AppLovin (MAX plus Ad Review) and Unity (LevelPlay plus Ad Quality). These tools exist to record creatives and block non-compliant ads (adult, clickbait, auto-redirects, crashes). That same legitimate purpose gives them a view of competitors' ads.
	- **Others are narrower**: Google AdMob's Ad review center covers only ads Google sells. Independent tools such as AppHarbr and Boltive have no DSP to feed.
	- **Read**: this is a structural problem for mediation, not just a dispute between two companies. Whoever runs the mediation SDK and a DSP has both the means and the incentive. AppLovin pressing the point invites scrutiny of its own Ad Review.
- ## How take rate links to the competition
	- **Definition**: AppLovin's take rate = (advertiser spend − payments to publishers) / advertiser spend.
	- **The signal**: if Unity's bids in MAX rise, its model is competing better for inventory. If AppLovin's own MAX bids also rise faster YoY at the same time, AppLovin is paying more to defend share, and its take rate falls. DSP share within MAX and AppLovin's YoY bid growth are therefore indirect take-rate indicators. The publisher survey was designed to measure these, but its results aren't in the excerpt.
	- **The same mechanism in management's words**: on the Q3 call, AppLovin said take rate holds if it improves at the market's pace and contracts "if we fall way behind" ([[APP-2026-Q3]]). A stronger Vector is exactly the force that would push inventory prices up.
- ## The note's open questions, with what Q3 has since shown
	- | Question | What we know now |
	  |---|---|
	  | Did Unity's data use explain AppLovin's Q2 miss and Unity's IAA share gains? | Not settled. The timing fits, but Unity says collection predates the agreements, which would mean it was in place long before Q2 |
	  | Did AppLovin's Q3 guide (set Aug 5) assume the Unity issue would be resolved? | The guide came before the cease-and-desist letter. Q3 then beat the high end by ~\$100M, so the guide was conservative either way |
	  | Will a stronger Vector raise AppLovin's bid costs and cut its take rate? | Q3's ~87% incremental EBITDA margin shows no visible take-rate squeeze yet |
	  | Will the AXON–Vector gap widen once collection stops? | Q3 gaming reaccelerated to ~50% YoY with the next-gen AXON rollout ([[APP-2026-Q3]]). That fits a widening gap, but the model upgrade and any switch-off happened at the same time, so the two effects can't be separated |
	- **Overall**: Q3 suggests AppLovin got its lead back through its own model upgrade, whatever happens in arbitration. The lasting point is that Vector closed enough of the gap in Q2 to dent AppLovin's numbers. AppLovin's margin depends on staying well ahead of competing models, and Unity has shown it can narrow that lead.
