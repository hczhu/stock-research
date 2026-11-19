tags:: [[$NET]], [[Cloudflare]], [[agents]], [[Workers]], [[SASE]], [[zero-trust]], [[CDN]], [[bot-management]], [[agentic-commerce]], [[MCP]], [[sandboxes]], [[serverless]], [[vibe-coding]], [[$ZS]], [[$PANW]], [[$SNOW]], [[Databricks]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-19
file-updated-at:: 2026-11-19

- ## Cloudflare's agentic flywheel across Acts 1–4
	- **Source**: HHHYPERGROWTH, "Premium: Agentic flywheel," by Muji, October 22, 2026; email copy supplied by the user. The piece covers Cloudflare's Q2 2026 results, Content Independence Day (July 1), Agents Week (August) and Birthday Week (September). Figures are management disclosures and web-tracker data relayed by the author, and have not been independently verified. Opinions are the author's.
	- Earlier issues from the same author: [[2026-06-29-hhh-hypergrowth-cloudflare-agentic-leverage]] and [[2026-07-01-hhh-hypergrowth-cloudflare-agentic-waves]]. Latest results: [[NET-2026-Q3]].
	- **Thesis**: the more work enterprises give AI agents, the more of Cloudflare's network they use. Agents generate web traffic (Act 1), need secure connections to enterprise systems (Act 2), run code and tools on serverless infrastructure (Act 3), and will soon pay for content and services (Act 4). Coding AIs also create more developers and deployed apps, which feeds back into Act 1 and Act 3.
	- **Company-wide scale**:
		- Cloudflare sits over **~30% of websites** and serves **more than 45% of the Fortune 500**.
		- **About 80% of frontier AI labs** use Cloudflare, and the top two use both Act 1 and Act 3.
		- Bot traffic **overtook human traffic around May 2026**. Management "wouldn't be surprised" if bot traffic grew **1,000× over five years**, and says agentic workloads generate **an order of magnitude more outbound web requests** than user-driven apps.
	- **The CEO's framing**: "we win when AI applications are built on Cloudflare Workers, but we also win just from the increased usage of all of our products that agentic Internet drives." AI is "not putting pressure on Cloudflare."

- ## Act 1: Application services (security and performance for websites and APIs)
	- **What it is**: Cloudflare's core product line. It includes CDN, DNS, DDoS protection, bot management, load balancing, WAF, API Shield, traffic encryption, smart routing and Magic Transit (network-level DDoS protection). Workers makes all of it programmable, for example with custom traffic routing or WAF rules.
	- **Use cases**:
		- | Customer need | How Act 1 helps | Example |
		  |---|---|---|
		  | Control AI crawlers and agents hitting a site | Bot Management, AI Crawl Control, the BotBase bot database, a bot-traffic Insights dashboard, and a new "Disallow AI Training" option that separates training bots from search bots. Adaptive Intelligence keeps retraining the detection models | A media company signed a **5-year \$31.8M extension** for content control in Q2, which the author reads as early Act 4 interest |
		  | Secure a company's own LLM chatbots | AI Security for Apps (formerly Firewall for AI), released March 2026, monitors and secures LLM chatbot use | Enterprises deploying customer-facing chatbots |
		  | Protect legacy apps that can't be patched quickly | As a reverse proxy, Cloudflare shields vulnerable origins until customers patch. The WAF now correlates requests and responses so it can block a malicious response | Automatic patches for newly found vulnerabilities in legacy PHP apps and a Citrix web appliance |
		  | Meet sovereignty and government rules | Data Localization Suite; Cloudflare for Government authorized at **FedRAMP High** and GovRAMP Moderate (August); Korean ISMS certification | Federal and state agencies; a Deutsche Telekom partnership for EU adoption across Acts 1–3 |
		  | Serve AI apps at scale | Reverse proxy and web serving | W3Tech shows **ChatGPT and Claude** both use Cloudflare |
	- **Scale**:
		- **Traffic growth (Cloudflare Radar)**:
			- | Period | Global traffic | Global HTTP requests | US traffic | US HTTP requests |
			  |---|---|---|---|---|
			  | 2025 | +57% | +43% | +72% | +64% |
			  | 2026 YTD | **+69%** | **+53%** | **+133%** | **+71%** |
			- Bot web requests are up about **75%** YTD.
			- US bandwidth (+133%) is growing much faster than US request counts (+71%), with a big jump since July. The author thinks large customers with private networks or heavy content joined in Q3, or that non-web traffic grew in Act 1 or Act 2.
		- **Share of the web**:
			- | Measure | A year ago | Now |
			  |---|---|---|
			  | W3Tech, websites using Cloudflare as a reverse proxy | 20% | **27%+**, an estimated ~86% share of measurable reverse proxies, far ahead of Akamai and Fastly |
			  | W3Tech, websites using Cloudflare as a web server | 25% | **32%**, overtaking nginx |
			  | Netcraft, top 1M busiest sites | 22.9% | **28.3%** |

- ## Act 2: Cloudflare One (SASE and Zero Trust)
	- **What it is**: Cloudflare's secure access and private networking suite, launched in late 2020 and competing with Zscaler, Netskope and Palo Alto. It covers:
		- **Private network security (SASE)**: Cloudflare WAN and Magic Firewall.
		- **User access security (SSE)**: Access, Gateway, CASB, DLP and Browser Isolation.
		- **Posture management**: CSPM, SSPM and AI-SPM.
		- **Interconnects**: WAN Connector, Tunnel and Multi-Cloud Networking.
		- **Bundled Act 1 services**: such as Argo Smart Routing and Magic Transit.
	- **Use cases**:
		- | Customer need | How Act 2 helps | Example |
		  |---|---|---|
		  | Let AI agents reach internal data and tools securely | **Cloudflare Mesh** (April) combines Cloudflare One with agents built on Workers in one private network. Agents can also live inside that network | A large UK government agency **canceled an RFP** with a "first-generation" Zero Trust vendor to re-evaluate with an agents-first approach (CEO) |
		  | Govern agents' use of outside AI services and SaaS | Cloudflare One now secures and monitors **MCP traffic**, and SSE enforces Zero Trust access to apps and agents deployed on Workers | Enterprises rolling out internal agents |
		  | Replace legacy remote access and firewalls | A global edge network with Workers programmability | A **Federal agency replaced a legacy vendor after a major outage** (Q2 win) |
		  | Stop agents from making dangerous cloud changes | **Cloud Workload Security** (beta) puts programmable guardrails on cloud API calls, blocking risky infrastructure changes | Multi-cloud teams with autonomous agents |
		  | Get ahead of quantum threats | End-to-end post-quantum encryption: SSE last year, SASE interconnects and tunnels in February 2026, post-quantum identity by early 2028 | Regulated and government customers |
		  | Outsource security operations | **Managed Defense** (renamed SOC-as-a-service) uses internal agents running OpenAI's Daybreak security models. A new Vulnerability Discovery and Remediation service (early access) reviews code using Cloudflare-specific context and recommends code and WAF fixes | Customers without a full in-house security team |
	- **Scale**:
		- **Cloudflare One ARR grew 43% in FY2025** (IR Day).
		- **The channel is growing faster**: +67% vs. +36% for the company overall. Partners make up 31% of the mix today, with a target of **50–60%** over time, and are expanding from SASE into Workers.
		- **Gartner**: Cloudflare is the **sole "Visionary"** in Gartner's SASE and SSE Magic Quadrants. It trails Leaders Zscaler, Palo Alto and Netskope on CASB, SSPM, CSPM and DLP breadth, and on speed to features such as sovereign SSE.
	- **Differentiators**: Cloudflare runs its traffic over its own global backbone. Palo Alto relies on Google's network and Zscaler on the public internet. Netskope is the one competitor with its own edge network (NewEdge). Workers also lets customers program the SASE and SSE services themselves.

- ## Act 3: Workers developer platform (serverless infrastructure for apps and agents)
	- **What it is**: Workers is Cloudflare's serverless platform. It now spans compute, storage, databases, AI inference, media, real-time services, observability, and a growing set of tools built for agents. Cloudflare also uses Workers to build its own products quickly.
	- **Use cases**:
		- | Customer need | How Act 3 helps | Examples |
		  |---|---|---|
		  | Host apps generated by AI coding tools | Fully managed or self-deployed serverless hosting | **Lovable** (whole dev platform on Workers), **Base44** (Wix), Webflow Cloud, Wix Vibe. **OpenAI's Sites** plugin in Codex and ChatGPT deploys apps to Workers using R2 and D1. Supported coding agents include Claude Code, Codex, Cursor, OpenCode, Devin and GitHub Copilot |
		  | Give agents a safe place to run code and call tools | Two sandbox types: container-based **Cloudflare Sandbox** (full Linux, GA April) and isolate-based **Dynamic Workers** (faster and cheaper). **Cloudflare Computer** (research preview) wraps them into a reusable virtual machine with a shell and file system | **Figma** Make, **Anthropic** Claude Managed Agents, **Devin** Outposts, **Cursor** Cloud Agents, **OpenAI** Agents API, **Kilo** Cloud Agents. Anthropic also uses Cloudflare tunnels for private connections to MCP servers |
		  | Build and run long-running agents | Agent Cloud for building and observing autonomous agents. The Agents SDK provides memory, scheduling, email, real-time and voice. The **Project Think** harness, Browser Run and Kitesurf for web browsing, Web Search API, AI Search (a managed RAG memory), Agent Memory, Email Service, **Artifacts** (git-based files), Dynamic Workflows and CI Workflows | Developers building agents and sub-agents |
		  | Serve many customers cheaply | Isolate-level multi-tenancy: "idle tenants cost approximately nothing." Cloudflare says a platform that once capped out at thousands of paying customers can now reasonably serve tens of millions | Multi-tenant SaaS and agent platforms |
		  | Run analytics and data streams without egress fees | **Basin**, a serverless lakehouse on Apache Iceberg in R2, readable by DuckDB, Snowflake and Spark. **K2** event streaming with Kafka compatibility planned. Hyperdrive for external Postgres and MySQL, plus KV Instant | Competes with Snowflake, Databricks, BigQuery, Redshift and Confluent. Basin went GA in Birthday Week and **contributes from Q4** |
		  | Route and control a company's model use | **AI Gateway** plus Workers AI as one inference layer: automated model routing, per-employee usage tracking, OpenAI frontier models, MCP Server Portals (GA). Small in-house models handle routing decisions (Clef) and data extraction (Claric). Replicate and Ensemble AI were acquired | Enterprises managing AI cost and access |
		  | Run an "AI operating system" for the workforce | **Cloudflare OS**: an enterprise platform where each team builds its own agentic workflows and apps on a shared knowledge base. Models are routed between Workers AI, OpenAI and Anthropic, and each agent gets the same access as its employee. Open-sourced in August, with a managed service in early access. **Not priced separately**: it drives Workers consumption | Systems-integrator partners; integrations with Asana, Box, GitHub, ClickHouse and Notion |
	- **Scale**:
		- **Workers ARR grew 137% in FY2025** (IR Day). Consumption-based Workers usage drove much of Cloudflare's reacceleration in 1H 2026 and large pool-of-funds deals.
		- **Developers on Workers**: **7.4M** in Q2 (+2M in a quarter, more than all of 2025), then **over 10M** at Connect in October (about +2.6M in Q3). Python became Workers' fourth supported language.
		- **Ecosystem acquisitions in 2026**: Astro (web framework), VoidZero (build tools) and Deno (an open-source TypeScript runtime that lets Workers and Cloudflare OS run self-hosted). Outerbase was acquired in 2025 for database management.
	- **The author's wish list**: a managed Postgres or MySQL service. Cloudflare currently relies on partners such as Supabase, PlanetScale, Xata and Neon (now Databricks).

- ## Act 4: Monetization rails for the agentic internet
	- **What it is**: using Act 1's position over about 30% of the web to become a toll layer where content owners and AI agents transact. The goal is to be "not a seat at the table, but the table itself." The CEO says the next 27 years of the internet's business model will differ from the last 27, which Google defined through advertising.
	- **Use cases**:
		- | Customer need | Product | How it works |
		  |---|---|---|
		  | A publisher charges AI crawlers for access | **Pay Per Crawl** (2025) | Charges for each crawl |
		  | A publisher gets paid when AI actually uses its content | **Pay Per Use** (Birthday Week) | Each AI company sets a price per use, publishers accept offers, and Cloudflare handles enrollment, usage records, billing and payment. The rationale: "AI products fetch far more than they use" |
		  | Sell any resource to agents | **Monetization Gateway** (July 1; private beta) | Sells access to web pages, documents, media, datasets, APIs and MCP tools. Uses x402 micropayments with Coinbase, and Cloudflare takes a cut before paying the publisher |
		  | Let agents pay autonomously | **Cloudflare Wallet** and **cloudflare.pay** (Agents Week) | Stablecoin-based programmable wallets, plus identity and trust tools for merchants and buyers |
		  | Track visibility in AI search | **Answer Engine Optimization (AEO)** tool (early access) | Shows the top queries that surface a customer's content in AI results, the snippet used and the average ranking. It is the AI-era version of SEO tools |
	- **Payment partners**: Visa (Trusted Agent Protocol), Mastercard (Agent Pay), American Express, PayPal and Coinbase (x402 Foundation). The NET Dollar stablecoin has not progressed.
	- **Scale**: still nascent. Act 4 is **not included in FY2026 guidance, long-term margin targets or TAM**.
		- **The CFO**: Cloudflare needs "millions or tens of millions of transactions in small value, high volume." He expects Act 4 to "dwarf whatever we have done so far," with high margins because "Act 4 will live off the infrastructure that Act 3 has built."
		- **Cloudflare's own claim**: more than 20% of the web and nearly 80% of leading AI companies sit behind its network, so it sees both sides of this market.

- ## How the Acts reinforce each other
	- An enterprise can secure its agents with Act 2, run them on Act 3, connect them to content and services protected by Act 1, and eventually pay for that access through Act 4. Every step earns Cloudflare revenue on the same network.
	- **The CFO on cross-subsidy**: SASE has high gross margins because it "live[s] off the infrastructure that Act 1 has built," and Act 4 will do the same with Act 3.
	- **Product lines blur**: AI Security for Apps grew out of the Act 1 WAF but is listed under Act 2, and AI Gateway grew out of Act 1's API Gateway but is listed under Act 3.
