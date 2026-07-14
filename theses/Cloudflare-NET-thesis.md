tags:: [[Cloudflare]], [[NET]], [[SaaS]], [[networking]], [[security]], [[CDN]], [[edge-computing]], [[developer-tools]], [[AI]]

- **Company**: Cloudflare, Inc. (NET)
- **Date**: 2026-06-09
  
  ---
- ## References
  
  |  |  |
  |---|---|
  | [Cloudflare numbers](https://ir.cloudflare.com/) | [Founder CEO’s Hackernews comments](https://hn.algolia.com/?dateRange=all&page=0&prefix=true&query=Matthew%20Prince%20Cloudflare&sort=byDate&type=comment) |
  | [Patents](https://patents.google.com/?assignee=Cloudflare) | [The Verge interview in 2024/04](https://www.theverge.com/search?q=Cloudflare%20Matthew%20Prince%20April%202024) |
  | [PDFs from .gov sites](https://www.sec.gov/edgar/browse/?CIK=1477333&owner=exclude) | [Fedramp Cloudflare](https://marketplace.fedramp.gov/products?sort=productName&order=asc&search=Cloudflare) |
  | [Muji piece](https://www.google.com/search?q=MUJI+Cloudflare) | [SaaS data benchmarks](https://www.saas-capital.com/saas-metrics-benchmarks/) |
  | [Protocol Cloudflare](https://www.protocol.com/search?q=Cloudflare) | [Cloudflare community](https://community.cloudflare.com/) |
  | [Cloudflare Sub-reddit](https://www.reddit.com/r/CloudFlare/) | [Websites on RP](https://w3techs.com/technologies/overview/reverse_proxy) |
  | [Websites with domain names on Cloudflare DNS](https://w3techs.com/technologies/details/ns-cloudflare) | [Reverse Proxy market shares](https://w3techs.com/technologies/history_overview/reverse_proxy) |
  
  ---
- ## Main Narrative
	- > What will the business look like in 5–10 years, qualitatively and quantitatively? Is the market large enough to support a much larger business? Can Cloudflare move from a CDN/security vendor into a broader connectivity and developer platform?
	- **The one-line story**: *Cloudflare is building a one-stop connectivity cloud for the internet: DNS and reverse proxy get the customer in the door, security and networking deepen the relationship, and Workers/R2 provide upside from edge compute and storage.*
	- **DNS and reverse proxy are the distribution wedge.** Once a customer moves its domain to Cloudflare DNS authoritative servers or fronts traffic through Cloudflare’s reverse proxy, the rest of the product suite becomes “just clicks away.” This is an unusually strong attach motion because the customer has already entrusted Cloudflare with the control plane of its internet traffic.
	- **The company is evolving from point product to bundled platform.** The PDF’s core argument is that Cloudflare’s strategy resembles Microsoft’s enterprise bundling playbook: the individual product is not always best-of-breed, but the integrated suite creates operational simplicity, lower vendor sprawl, and faster deployment for customers.
	- **The long-term aspiration is broader than CDN.** The platform spans security, performance, reliability, connectivity, programmable edge, and storage. Cloudflare increasingly describes this as a “connectivity cloud,” which is a more ambitious framing than legacy CDN or DDoS mitigation.
	- **Workers and R2 are the option value.** If the base business is already attractive as a global network-security platform, the upside comes from developer adoption of Workers, Durable Objects, and R2. These products let Cloudflare capture workloads that historically would have defaulted to a hyperscaler.
	- **Enterprise and government adoption are the proof points that matter.** The thesis repeatedly emphasizes Cloudflare’s move upmarket: FedRAMP, `.gov` registry work, larger Zero Trust contracts, and multi-million-dollar expansions suggest the company is no longer just an SMB/web performance tool.
	- **AI and agents may widen the opportunity set.** By 2025Q3–Q4, management is framing Cloudflare as infrastructure for the “agentic internet.” That matters because AI-native companies appear to buy Cloudflare first for security, traffic management, crawl control, and cost control before they buy pure inference services.
	- ---
- ## Napkin Math
	- > Back-of-the-envelope TAM framing from the source thesis rather than a precise valuation model.
	- The source uses older HashiCorp S-1 TAM cuts as a rough bridge for Cloudflare’s core markets. Even these appear underinclusive because they exclude much of the newer developer platform and storage opportunity.
	
	| Segment | 2021 TAM | 2026 TAM | Why it matters for Cloudflare |
	|---|---:|---:|---|
	| Security | $16.3B | $20.8B | WAF, DDoS, Zero Trust, email security, bot management, IAM-style controls |
	| Networking | $22.6B | $30.9B | WAN, application connectivity, DNS, traffic acceleration, load balancing |
	| Developer edge / storage | Not included | Not included | Workers, Durable Objects, R2, programmable network services are upside not captured in the legacy TAM cuts |
	
	- **Takeaway**: even the narrow security + networking frame gets to **$51.7B** by 2026. If Workers and R2 become meaningful, the real opportunity is larger than the source TAM math suggests.
	- **What has to happen for the stock to work**:
		- Cloudflare must keep moving from SMB and self-serve into larger enterprise and government accounts.
		- Zero Trust, application security, and networking need to remain the main monetization engine.
		- Workers and R2 do not need to kill AWS; they only need to become large enough to add a second leg of growth.
	- ---
- ## Competition Landscape
  
  | Competitor | Where they compete | Cloudflare advantage | Cloudflare weakness / risk |
  |---|---|---|---|
  | Vercel | Full-stack hosting, edge/serverless compute, analytics, image optimization, app-layer security | First-mover network scale; broader suite; stronger “one-stop shop” positioning; 20% of websites on Cloudflare reverse proxy | Vercel has stronger developer reputation in some indie/full-stack circles |
  | Zscaler / Palo Alto / Netskope | Zero Trust, SASE, enterprise network security | Cloudflare can bundle security with its global network and DDoS/bot heritage; easier deployment and good performance are common positives | Source anecdotes say Cloudflare still lacks some enterprise-grade functionality, especially for complex on-prem routing and legacy environments |
  | Hyperscalers (AWS / Azure / GCP) | Compute, storage, security adjacencies, front-door traffic, object storage | Neutral positioning across clouds; R2 no-egress story; global edge architecture; lower-latency network primitives | Hyperscalers have deeper compute/storage stacks and can match Cloudflare in many workloads over time |
  | Akamai / Fastly | CDN, application delivery, security services | Higher-margin product mix, broader security/networking bundle, disciplined avoidance of low-margin bandwidth arbitrage | Legacy CDN pricing pressure can still compress lower-end use cases |
	- ---
- ## Durable and Unfair Competitive Advantages
	- **The control-plane wedge is powerful.** DNS authoritative hosting and reverse proxy placement are not isolated products; they are distribution. Once Cloudflare controls the traffic path, it can sell security, reliability, performance, and developer products with much lower friction.
	- **One software stack on every server.** A durable architectural advantage described in the source is that every server across the network runs every bit of Cloudflare software. This makes the network flexible, allows dynamic resource allocation, and means new products can be layered onto the same footprint without standing up an entirely separate stack.
	- **The network gets more valuable as more products run on it.** The company’s better products increasingly consume compute rather than just bandwidth. The 2022Q1 data point that CPU growth outpaced traffic growth is important because it signals more intelligence being sold on top of the network, not just commoditized delivery.
	- **Idle-capacity monetization is real.** Cloudflare’s architecture lets it turn excess network, compute, and storage capacity into new products such as Workers, R2, or other software primitives. That is a different economic model from a vendor that sells only bandwidth.
	- **Predictable pricing and developer goodwill matter.** Fixed or more predictable pricing is a real differentiator versus surprise usage bills. The freemium funnel, developer goodwill, and low-friction onboarding also create a wider top-of-funnel than a pure enterprise appliance vendor.
	- **Vendor consolidation is a structural moat enhancer.** The more enterprises want fewer network/security vendors, the more Cloudflare’s breadth starts to matter. The suite does not need to be perfect everywhere; it only needs to be “good enough” across enough adjacent categories to replace point tools.
	- ---
- ## Key Value Drivers
  
  | Driver | Notes | Metrics to watch |
  |---|---|---|
  | Network scale and ubiquity | The source cites ~20% of websites on Cloudflare reverse proxy and ~17% of global internet traffic touching the platform | POP count, network capacity, traffic growth, reverse proxy share |
  | Enterprise and government penetration | FedRAMP, `.gov` registry work, cabinet-level agencies, and larger Fortune 500 expansions are the highest-quality proof points | $100K+ / $500K+ / $1M+ customer counts, FedRAMP portfolio wins, public sector deal sizes |
  | Workers adoption | Workers is the highest-upside non-core product because it can become a developer platform rather than a feature | Active developers, active Workers apps, large Workers contracts |
  | R2 storage adoption | R2’s no-egress positioning can pull data toward Cloudflare and support adjacent workloads | R2 paying customer count, large R2 logos, storage-heavy AI customers |
  | Security bundle expansion | Bot management, DDoS, WAF, Zero Trust, email security, and AI crawl control fit naturally onto the same network | Zero Trust attach, channel partner growth, app security wins, multi-product expansion deals |
  | AI / agentic internet demand | AI companies seem to start with Cloudflare for security and traffic control; the platform may benefit from a world with dramatically more automated traffic | AI logo count, crawl-control contracts, Workers/AI-related contract value |
	- ---
- ## Secular Trends as Tailwinds
  
  | Trend | Why Cloudflare benefits |
  |---|---|
  | Vendor consolidation in network and security | Enterprises increasingly want fewer tools and fewer vendors; Cloudflare’s bundle is the product |
  | Hardware boxes to software-defined networking | Legacy network appliances migrate toward software and cloud-delivered services |
  | More security spending | Security software remains a high CIO priority and keeps expanding into adjacent workflows |
  | Zero Trust / application access proxy | BeyondCorp-style architecture remains a long-duration enterprise transition |
  | Some workloads moving closer to the edge | Not every workload belongs at the edge, but latency-sensitive and internet-facing workloads create real openings for Workers |
  | AI-driven traffic growth | More bots, crawlers, agents, and automated application traffic increase demand for visibility, control, and protection |
	- ---
- ## Innovative Culture
	- Cloudflare appears to have a deliberately layered R&D model rather than a pure near-term roadmap culture.
	- Management describes a second R&D organization, `ETI` (Emerging Technology and Incubation), representing roughly **10% to 20%** of the company and operating on a **2-to-3-year** horizon.
	- There is also a smaller third group thinking on a **five-year** horizon around fundamental internet technologies.
	- This matters because several of Cloudflare’s newer TAM-expanding products, including Workers and Cloudflare for Teams, are presented as outputs of this incubation engine rather than as obvious line extensions.
	- The CEO’s willingness to reflect on customer feedback and rethink strategy is flagged positively in the source thesis.
	- Hiring selectivity is another soft signal: in 2020Q3 Cloudflare reportedly received **60,000+ applications** and extended offers to only **0.4%**.
	- ---
- ## Vibe Checks
	- **What do you like most?**
		- The architectural coherence. “Every server runs every product” is the kind of systems-level design choice that can compound for a decade.
		- The distribution wedge is unusually clean: DNS and reverse proxy can seed an entire suite.
		- The platform has real second-act and third-act optionality. Security and networking can drive the base case; Workers and R2 provide the upside.
		- Cloudflare seems particularly well-placed for vendor consolidation because it can bundle performance, security, and developer services on one control plane.
	- **What do you hate most?**
		- Enterprise deal sizes still look smaller than those of PANW and Zscaler, which suggests the upmarket motion is real but early.
		- Source anecdotes say some enterprise-grade functionality still lags, especially in complex on-prem and legacy-routing environments.
		- The sales organization historically lacked rigor and structure, which can delay monetization even when product quality is strong.
		- Edge compute is not obviously a hyperscaler killer; the better case is niche displacement plus adjacency revenue, not wholesale replacement of AWS/Azure/GCP.
	- **How popular is the product or service?**
		- The network footprint is already massive: 1.1.1.1 reportedly surpassed **1 trillion requests per day**, and the programmable edge network reached **250 POPs**, **100 Tbps**, and **95%** of internet users within **50 ms**.
		- Cloudflare Workers benchmarks well on latency in third-party comparisons.
		- Safari / iCloud Private Relay and Microsoft privacy-browsing features are meaningful ecosystem credibility signals.
		- ---
- ## Pre-Mortem — What Can Go Wrong?
	- 1. **Enterprise motion stays subscale.** Cloudflare wins logos but continues to land smaller ACVs than the security incumbents, limiting operating leverage.
	- 2. **Sales execution lags product execution.** The company can build faster than it can sell, especially in larger accounts where procurement, channel, and field enablement matter.
	- 3. **Reverse proxy and CDN become less differentiated.** If the network wedge is commoditized or abstracted away, Cloudflare loses the easiest distribution path for its suite.
	- 4. **Workers/R2 never become material enough.** If edge compute and object storage stay niche, the market may continue to value Cloudflare primarily as a security/networking vendor.
	- 5. **Enterprise functionality gaps persist.** Customers may like Cloudflare for internet-facing traffic but still keep PANW, Zscaler, or Netskope for harder internal networking use cases.
	- 6. **The low end is not big enough, while the high end is crowded.** If SMB TAM is smaller than expected and enterprise takeout is slower than expected, the growth algorithm gets tougher.
	- 7. **R&D intensity does not translate into monetization.** The source explicitly flags R&D expense per employee as a concern.
	- ---
- ## Friendly to Shareholders?
  
  | Factor | Signal | Assessment |
  |---|---|---|
  | Founder / management alignment | Founder-CEO still drives strategy and appears long-term oriented | Positive |
  | Capital allocation | Willingness to fund long-horizon ETI / research groups | Positive if monetized; needs continued proof |
  | Explicit shareholder-return policy | The source deck does not make buybacks or dividends part of the thesis | Neutral / not a reason to own it |
  | Sales and operating discipline | Historical GTM looseness and concern around R&D efficiency | Needs monitoring |
	- ---
- ## Anecdotes & Opinions
	- **Enterprise adoption looks real, but still early.** One of the more useful external reads in the source deck is that Cloudflare is winning real enterprise work, but not yet at the same ACV level as the most mature security incumbents. That supports the thesis that the platform is moving upmarket, while also arguing the motion is not fully proven.
	
		> Since 3Q21, these highlighted deals have represented an average of $715k in ACV.
		
		> One partner we spoke to told us that his average deal size with Cloudflare is $130k ... compared to the $200K+ he is doing with Zscaler.
	
	- **Workers seems genuinely respected by developers.** The source deck includes a third-party benchmark where Workers outperformed peers on latency. That matters because the developer-platform thesis only works if the product is not just strategically interesting but actually loved in practice.
	
		> Cloudflare workers outperforms the rest by a big margin (~80ms avg)
	
	- **The anti-thesis on edge compute is worth taking seriously.** A useful Chinese-language anecdote in the source argues that Cloudflare’s opportunity is much larger in network security and optimization than in trying to overturn the hyperscaler data-center model. That is a good check against overpaying for the “AWS killer” narrative.
	
		> 我不觉得edge compute会颠覆AWS这样的数据中心业务，最多能抢一些市场份额。
	
	- **Sales rigor used to lag product ambition.** The source’s anecdotal channel checks suggest Cloudflare built a very large business before building a fully mature enterprise sales machine. That can be bullish if fixed, but it is still a real execution risk.
	
		> They got to $1B in revenue ARR without a lot of "rigor and structure" in their sales org.
	
	- **Cloudflare’s original goodwill among technical users matters.** The deck includes a memorable anecdote from the MMORPG private-server world: talented but under-resourced operators could still afford Cloudflare to stop DDoS attacks. This is not a hard data point, but it helps explain why the brand has deep roots among internet-native builders.
	- ---
- ## Appendix
	- ### Long-shelf-life data points
	  
	  | Date | Data point | Why it matters |
	  |---|---|---|
	  | 2022/07 | 13 of the world’s 20 largest companies were customers of Cloudflare security services | Validates large-enterprise relevance |
	  | 2022/05 | 1.1.1.1 surpassed 1T requests per day | Shows consumer/internet-scale network footprint |
	  | 2023/02 | OpenAI used R2 for ChatGPT storage | Early high-quality validation for R2 |
	  | 2023/05 | Large-customer ARPC around $340k | Useful benchmark for enterprise monetization maturity |
	  | 2024/05 | Enterprises often deploy 50+ security tools and still want consolidation | Strengthens the suite thesis |
	  | Early 2021 to late 2022 | Network expanded from ~200 to 250 POPs, ~58 Tbps to 100 Tbps, and from 99% of internet users within 100 ms to 95% within 50 ms | Scale and performance continue compounding |
