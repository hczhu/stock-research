- tags:: [[foundation models]], [[model labs]], [[AI]], [[Anthropic]], [[$GOOGL]], [[OpenAI]], [[SaaS]], [[pricing power]], [[bear-case]]
  file-created-at:: 2026-06-03

- ## Foundation Model Pricing Power Bear Case
	- **Source**:
		- user-provided essay excerpt titled `A foundational model thesis`
		- the essay argues that foundation model labs may be strategically important but still lack durable pricing power once supply and demand normalize
	- **Thesis**:
		- Foundation models may become essential infrastructure, but essential infrastructure does not automatically earn premium economics.
		- The bear case is that models become commodity inputs for application companies, with limited network effects, weak leverage up the stack, and price competition once capacity normalizes.
	- **Context**:
		- today's model pricing exists in a period of disequilibrium: rapid demand growth, scarce inference capacity, huge capex, and unstable supply.
		- the long-term question is what happens when there are `3-6` model providers with broadly comparable capabilities and supply roughly matches demand.

- ## Core Arguments Against Foundation Model Pricing Power
	| Argument | Claim | Why it weakens pricing power | Stock read-through |
	| --- | --- | --- | --- |
	| Chatbots are a limited interface | Chat is a poor substitute for domain-specific product workflows. | If users need workflows, scaffolding, and institutional product knowledge, the value accrues to applications rather than raw model access. | Bullish for vertical SaaS and workflow software that embeds AI; less bullish for standalone model interfaces. |
	| GUI is institutional knowledge | A good interface helps users discover what they want to do and how the workflow should operate. | The model has to solve the same product-design problem as the user if the UI is generated from scratch. | Product craft remains a moat for application companies. |
	| Tool builders and tool users are different people | Building a durable workflow product is a different skill from using a model to complete a task. | Model labs cannot simply expose a general model and replace all software categories. | Application-layer companies can still own workflow design and customer context. |
	| Model labs cannot build every tool | Anthropic's Claude-for-finance / law / small-business style products resemble templates, not full products. | Templates are useful starters, but many categories need dedicated products, distribution, support, compliance, and workflow depth. | The app ecosystem should remain broad, like Windows or iPhone apps rather than first-party-only software. |
	| Models have limited leverage up the stack | Developers can choose one model, swap models, or use several models for different capabilities. | Model providers lack a Windows-style app/user network effect that forces standardization. | Model APIs risk becoming substitutable inputs inside SaaS products. |
	| Users buy outcomes, not model brands | Customers will buy software that solves their need and generally will not care whether it runs on Claude, Gemini, or another model. | If model brand is hidden inside apps, model labs cannot easily extract application-layer surplus. | SaaS vendors may capture more end-customer value than model suppliers. |
	| Normalized competition should pressure margins | With `3-6` comparable model companies, excess capacity can be sold at marginal cost. | One provider cutting price to fill capacity can force the others to follow. | Long-term model margins may resemble competitive infrastructure returns rather than software margins. |
	| Telecom analogy | Mobile networks changed the world and generate over `$1T` of revenue, but earn utility-like returns. | Infrastructure can be huge, necessary, and low-return if differentiation is weak and capex is high. | Model labs could be strategically central but economically mediocre. |

- ## Disequilibrium vs Normalized Market
	| Phase | Description | Pricing implication |
	| --- | --- | --- |
	| Current market | Demand, capex, capacity, and pricing are in major disequilibrium. | Scarcity can support high prices temporarily. |
	| Transition | Multiple labs race to add training and inference capacity while applications experiment with model choice. | Prices may remain volatile; model differentiation can matter for frontier use cases. |
	| Normalized market | `3-6` companies offer roughly equivalent model capabilities to developers, with supply and demand more balanced. | Commodity competition increases; providers may price near marginal cost to fill capacity. |
	| Mature infrastructure market | Model access becomes a standard input into software products. | Returns may look more like cloud / telecom infrastructure than high-margin application software. |

- ## Why The Essay Separates Models From Applications
	| Layer | What creates value | Who may capture value |
	| --- | --- | --- |
	| Foundation model | General reasoning, generation, coding, retrieval, and multimodal capability. | Model labs, but only if differentiation and scarcity persist. |
	| Interface / workflow | Product judgment, workflow design, user scaffolding, permissions, collaboration, and domain-specific UX. | Application software companies. |
	| Domain product | Compliance, integrations, data model, customer support, distribution, and business-process fit. | Vertical SaaS / workflow software vendors. |
	| End-user outcome | The actual business or consumer task being solved. | The product closest to the workflow and buyer. |

- ## Stock Implications
	- **Model labs**:
		- revenue can be very large while margins still compress if model access becomes a competitive commodity
		- first-party apps may help, but labs are unlikely to build every vertical workflow themselves
	- **Application software**:
		- app companies can preserve pricing power if they own workflow context, domain data, interface design, and distribution
		- AI can become an input cost rather than the whole product
	- **Cloud and infrastructure**:
		- if models become infrastructure, large cloud providers may still benefit from scale, utilization, and capex financing
		- returns may be capped by competition, similar to telecom or utility infrastructure
	- **AI infrastructure suppliers**:
		- the thesis does not deny near-term demand for compute
		- the risk is that long-term model-provider economics may not justify the most aggressive capex assumptions if pricing collapses toward marginal cost

- ## What Would Prove The Bear Case Right
	| Signal | Interpretation |
	| --- | --- |
	| Apps routinely switch or multi-source models | Model APIs are substitutable. |
	| Model prices fall sharply as inference capacity expands | Scarcity pricing was temporary. |
	| End users show low loyalty to model brands inside apps | Application layer captures the customer relationship. |
	| Labs launch many vertical templates but few durable vertical products | Model labs struggle to become full-stack app companies. |
	| Developer tooling abstracts away model choice | The model becomes an interchangeable backend component. |

- ## What Would Weaken The Bear Case
	| Signal | Interpretation |
	| --- | --- |
	| One model family becomes clearly superior for a large set of workflows | Technical differentiation can sustain pricing power. |
	| Model-specific ecosystems or agent platforms create network effects | Labs gain leverage up the stack. |
	| Enterprise buyers standardize on a single model brand | Brand and trust become a purchasing moat. |
	| First-party model-lab apps become category leaders | Labs prove they can capture application-layer value. |
	| Inference remains structurally supply-constrained | Scarcity can support pricing for longer. |

- ## Model Access Tiers (counterpoint — tiering as a moat)
	- **Source**: user-provided commentary excerpt on AI access tiers (named in source: **Fable** = the frontier model now limited to usage credits; **Mythos** = Anthropic's full internal model; **Siri AI** = Apple's on-device intelligence announced at WWDC).
	- **Argument**: the debate over capping Fable to usage credits framed the market as **two tiers** (subsidized vs paid), but there are really **five** — and the top one is the labs' own internal model, which is the structural counter to the commodity/bear case. **The extent to which internal access pays off is the extent to which the lab pulls ahead — and can then act "imperiously" (e.g. on data retention).**
	| Tier | What it provides | Provider / example | Read-through |
	| --- | --- | --- | --- |
	| 1 — On-device baseline (free) | Chatbot with personal context; competitive with the AI labs' free offerings | Apple Siri AI (WWDC) on-device intelligence | Anchors a "good-enough" free floor; commoditizes basic chat |
	| 2 — Cheaper paid plans | Better models, more image generation, higher limits | AI-lab low-cost consumer plans | Modest upsell; thin differentiation vs the free floor |
	| 3 — Serious subscriptions | Top consumer / prosumer subscription tiers | Pro / Max-style plans | Where consumer monetization concentrates (see [[2026-06-11-ai-subscription-margin-by-utilization]]) |
	| 4 — API usage (metered) | Pay-for-usage access to the frontier model | Fable, limited to usage credits | Heavy / enterprise demand; metering protects margin and pushes smart routing |
	| 5 — Lab-internal frontier | Full internal model, not sold externally; openly credited with accelerating the lab's own R&D | Anthropic internal devs → full Mythos model | The decisive moat: internal access compounds the capability lead → pricing power and leverage to dictate terms |
	- **Why it matters for the pricing-power debate**: this is a concrete version of the "[[#What Would Weaken The Bear Case]]" signal — *one model family becomes clearly superior*. If a lab's internal frontier model (Mythos) measurably speeds its own development, the lead **self-reinforces**, undercutting the assumption of `3-6` roughly-equivalent providers converging to marginal-cost pricing. The same dynamic also explains the move to **usage credits / metered API** (tier 4) and the rise of **smart-routing** to use the expensive frontier model only when necessary.

- ## Memo Takeaway
	- The argument is not that foundation models are unimportant.
	- The argument is that importance and pricing power are different things.
	- If models lack network effects, are substitutable for developers, and sit underneath domain-specific applications, then model labs may become the telecom networks of AI: massive, essential, capex-heavy, and lower-return than the apps built on top.
