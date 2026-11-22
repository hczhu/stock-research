tags:: [[$AMZN]], [[$GOOGL]], [[$WMT]], [[$KO]], [[$PG]], [[Bayer]], [[e-commerce]], [[search]], [[agentic-commerce]], [[shopping-agents]], [[Rufus]], [[Alexa]], [[product-data]], [[advertising]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-22
file-updated-at:: 2026-11-22

- ## Amazon's "World Product Graph": owning the world's product information
	- **Source**: Reuters, San Francisco, November 13, 2026, based on an internal Amazon PR/FAQ document reviewed by Reuters and people familiar with the matter (user-provided screenshots).
	- **Thesis**: Amazon's **World Product Graph** aims to collect data on virtually every product for sale, whether Amazon stocks it or not, so shoppers never need to leave Amazon to research a purchase.
		- **Defensive aims**: take product research away from Google, fend off Walmart, and stop third-party AI shopping agents from sending traffic to sites with better data.
		- **Fixing its own agent**: the internal document admits Amazon's shopping agent (Rufus, now Alexa for Shopping) often gives **wrong or incomplete answers** and is **expensive** to run. Better data would fix both.
		- **Not yet committed**: the plan is still a PR/FAQ and could be modified or abandoned.

- ## The plan
	- **The goal**: "Amazon cannot be the go-destination for every shopping mission if customers must leave to research product relationships on Google, brand websites, and review sites," according to the document. "These answers exist, but the only way to find them has been to leave Amazon for painstaking research on brand websites, third party review sites and tech forums."
	- **How the data gets collected**:
		- The graph "depends on discovering how brands organize their products on their own websites."
		- **Two channels**: brands and retailers contribute product data continuously, and **Amazon independently crawls other retailers' websites**. Reuters could not determine how Amazon would crawl those sites, or whether it would seek permission in every case.
	- **Early partners**:
		- **Coca-Cola** and **Bayer**, among others, have signed up to contribute product data.
		- Amazon held a "**CEO-level P&G/Amazon summit**" about a trial with **Procter & Gamble**.
		- None of the companies responded to Reuters.
	- **What shoppers would get**:
		- **Objective facts**: more certainty on which is the latest model or colorway of, say, a vacuum or tablet.
		- **Personal fit**: guidance on subjective criteria, such as which product suits a shopper based on purchase history and other data.
		- The document's imagined customer quote: "I used to spend an hour on Reddit figuring this stuff out… It's like the store finally knows what it's selling."
	- **Status**:
		- Amazon is moving staff internally to get the project started.
		- The PR/FAQ set **October 1** as a date for making the plan public. Reuters could not tell whether that was realistic.
		- A PR/FAQ is Amazon's six-page narrative memo for a proposed product. Not all lead to launches, and the project "could be modified or aborted due to financial or other concerns."

- ## Data points
	- **Where US online shoppers start product research** (Morgan Stanley, 2025):
		- | Starting point | All product research | When the shopper knows exactly what to buy |
		  |---|---|---|
		  | Google | **57%** | 23% |
		  | Amazon | 16% | **41%** |
		  | Walmart | — | 18% |
		- *Memo's reading*: Amazon wins when the purchase decision is already made. Google wins the earlier **research** stage, where shoppers compare and choose, and that is the stage the World Product Graph targets.
	- **Rufus / Alexa for Shopping**:
		- | Item | Detail |
		  |---|---|
		  | Name | Rufus, renamed "**Alexa for Shopping**" in May 2026 |
		  | Accuracy, per the internal document | "Many Rufus answers are **factually wrong or incomplete**, but customers lack expertise to detect these errors" |
		  | Usage and cost, per the internal document | About **83M searches a week**, and running them is "**expensive**." More complete data would let Amazon use cheaper models more efficiently |
		  | Amazon's response to Reuters | "The usage figures are **significantly outdated**." Alexa for Shopping is "roughly **97% accurate** globally" |
		- *Memo calculation*: 83M weekly searches is about 4.3B a year. That compares with 400M+ customers using Alexa for Shopping in the last twelve months and interactions up 570% YoY, as reported on the Q3 call ([[AMZN-2026-Q3]]). The gap fits Amazon's statement that the document's usage figures are outdated.

- ## Shopping agents
	- **What Amazon says in public**: on the Q3 2026 call, Jassy said "few customers are doing much shopping this way yet" and that the ads business has been minimally affected. He expects Alexa for Shopping to be "the primary shopping agent customers use to shop Amazon."
	- **What executives worry about in private**: according to people familiar with the matter, executives have grown wary of AI shopping agents that may send traffic to **other sites with greater or more complete data**. The World Product Graph would help defend against that.
	- *Memo's reading*:
		- **Who competes for the discovery layer**: shopping agents, whether Google's AI Mode, ChatGPT or Perplexity-style browser agents, compete to own the moment when a shopper chooses a product.
		- **Amazon's bet**: Amazon's ads business monetizes that moment through sponsored products and brand prompts in Rufus. If the best product answers live elsewhere, both traffic and ad leverage leak out. Amazon is betting that better data **inside** its own agent keeps the research step on Amazon.
		- **A tension**: Amazon plans to crawl other retailers' sites for its graph, while restricting outside agents' access to its own site. That raises the same permission and scraping questions that platforms use against third-party agents ([[2026-06-20-moffettnathanson-morton-ecommerce-ai-grocery-waymo]]).
	- **Why brands might share data**: Coca-Cola, Bayer and P&G supplying data directly suggests large brands see Amazon's agent as a channel worth feeding. That matches Seufert's point that retailers and brands open their catalogs when an agent brings new demand ([[2026-11-19-stratechery-eric-seufert-agentic-commerce]]).

- ## Read-across
	- **Google**: the plan aims at Google's 57% share of where product research starts, which includes Google's most commercial queries.
		- In SparkToro's panel, only about 15% of Google searches are commercial or transactional, so these few queries carry much of Search revenue ([[2026-11-20-sparktoro-google-search-query-concentration-intent]]).
		- Google is pushing the same research step into AI Mode ([[2026-11-20-mdm-seufert-alphabet-q3-ai-mode-monetization-penalty]]).
	- **Walmart**: cited as the rival e-commerce business the plan helps fend off. Walmart is already third, at 18%, among shoppers who know what they want.
	- **Amazon advertising**: a better research experience on Amazon supports the run rate of about \$69B and its 20%+ growth ([[Amazon-AMZN-thesis]], [[2026-06-04-amazon-advertising-advantages-identity-spine-dsp-ctv]]).
