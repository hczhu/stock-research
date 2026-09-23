- tags:: [[$MSFT]], [[Satya Nadella]], [[Stratechery]], [[OpenAI]], [[Anthropic]], [[MAI]], [[agentic-AI]], [[capex]], [[Azure]], [[GitHub Copilot]], [[enterprise-AI]], [[Project Solara]], [[business-models]], [[$2454.TW]], [[$QCOM]]
  file-created-at:: 2026-06-04

- ## Stratechery Interview — Satya Nadella on Microsoft's Core Competencies
	- **Source**: Stratechery by Ben Thompson, "An Interview with Microsoft CEO Satya Nadella About Finding Core Competencies," Jun 4 2026 — conducted right after Nadella's **Build** keynote (he was sole presenter outside demos → notably more hands-on). Companion to the keynote-analysis memo [[2026-06-04-stratechery-nvidia-ai-pc-microsoft-solara-mai]].
	- **Central frame**: platform shifts are **not zero-sum**; the question is "what is Microsoft *uniquely* capable of doing." Microsoft's role = **trusted purveyor of a platform** with **brand permission** to let others build on top. "The world wants you to do *the one thing*" (Microsoft is worst "when it acts out of envy" — Zune as the cautionary tale).
	- **Conceptual evolution of "what is a model"**: stateless APIs → databases → **processors (the Intel-partnership analogy)** → ultimately a **"learning machine."** Nadella's goal: a **multi-tenant learning system** so every customer gets its own **"hill-climbing machine."**
	- **Thesis of the firm in the AI age**: a company = **human capital + token capital**; token capital "isn't a bunch of API calls — it's some set of weights they have." Your **moat = your tacit knowledge**, captured via your own hill-climbing machine.

- ## MAI Models — Clean Lineage + Enterprise Hill-Climbing
	| Data point | Detail |
	| --- | --- |
	| New MAI models released | **7**, built **from scratch** — no distillation, no other models as teachers ("clean lineage") |
	| Two frontiers | Microsoft's own (MAI) **+** OpenAI — used to **"eval match"** against each other |
	| Use of OpenAI IP | **RKLD (reverse knowledge distillation) + RL on top** for performance gains; distillation only at the very end, never during own hill-climbing |
	| OpenAI IP access runway | **~5 years** remaining ("clock is ticking") |
	| Harness | **GitHub Copilot harness is model-independent**, used everywhere across Microsoft |
	| Deep customization | Enterprise RL environments incorporating their data far deeper than "slap-on RAG" — **only possible with MAI models** |
	- **"Private evals are the most important IP a firm creates"** — dynamic (today's failure cases continuously reshape the benchmark), they define a customer's own **RL environment**; then "invite all the models to show up" and switch between them. MAI is "one more lineage" you can drop in — proven to hill-climb on customer traces **more token-efficiently**.
	- **Long-run ambition**: MAI models **fully competitive on the frontier**. Logic: if you believe there'll be only 2 firms, you need only 2 frontier models; if you believe there'll be as many firms as today + more, each needs its own token capital (weights) → "do you want to accrue that advantage or give it to OpenAI and Anthropic?"

- ## OpenAI Partnership & Capital Allocation
	| Data point | Detail |
	| --- | --- |
	| Partnership analogy | Microsoft–Intel; also **SQL Server-with-SAP** (both win, then each does its own thing) |
	| OpenAI outlook | May go public, become a **trillion-dollar company** |
	| IP / partnership term | Runs **until 2032**; "every day OpenAI does well, Microsoft does well" |
	| Self-identity | "We are an **operating company**, investment is just an accident" |
	| Three compute buckets | **hyperscale**, **own application business**, **own research compute** — allocate with discipline across all three |
	| Hyperscale rule | Need a few big customers **+ a massive long tail**; "can't have a book of business that is … one model company" → deliberate decision **not to allocate all compute to one player** (OpenAI/Anthropic will build their own over time) |
	| Buildout shape | Not "10 GW in Texas" — spread plants around the US/world |
	| Early-mover edge | Got good power-generation spots **+ ~2 years of cash flow** head start |
	| Jan 2026 Azure | Missed Azure by **~0.1%**; allocated more compute to **internal R&D + applications** |
	| Margin mix | **Infrastructure-business margin *dollars* are already close to / higher than total margin dollars from the high-margin businesses** (not higher margin %, but higher absolute) |
	| Discipline | **Supply-constrained**; **won't sell raw GPUs to "Neolabs"** (turns away "easy money" short-term Azure revenue to protect enterprise customers) |
	| Hyperscaler differentiation | **tokens-per-dollar-per-watt** (a systems problem: co-design model + accelerator + network); "can't build accelerators without building a model" |
	| Agent domains | Three primary: **coding, security, knowledge work** (science also enabled). "The new apps are agents." |
	| Industry context | **Google just issued equity** that week to fund buildout (Nadella hadn't studied it yet) |

- ## The Software Business — Hybrid (Per-Seat + Consumption)
	- "Software is **alive**." The SaaS meme of "software is dead" comes from the old coupling of **data model + business-logic tier + UI tier + business model**. AI decouples this: **WorkIQ** (the database under M365) is now exposed as a **skill/MCP** so agents can continuously interrogate/reason/act over it from anywhere.
	- **New business model is mandatory**: Cowork hitting WorkIQ = **usage-based**. The future is a **hybrid: per-user (seat) + consumption** — Nadella: "100%."
		- **Per-seat = a set of usage entitlements** — survives because budgeting teams want predictability ("people don't like [pure] usage"). Bundle usage into the seat so it's budgetable.
		- **E7** (new tier) ≈ **double the price** of E5 — bundles more usage; a response to a **secular decline in seats by lifting ARPU**. Lure = **Cowork** (Anthropic's on-PC Cowork brought to the cloud with permissions/controls) + **Agent 365**; bundling because each agent needs security, observability, and a sandbox.
		- **Outcome-based pricing = "royalty"** — customers with a great outcome don't want to share it; so the realistic model is consumption (there's now "real marginal cost to software, priced through").
	- **What changed his mind = agents.** Pre-agents, software rode Moore's Law: **M365 didn't raise prices for a decade+** while adding functionality. Now **1,000 autonomous agents running 24/7** hitting WorkIQ is a lot of real cost → customers will become disciplined on evals/outcomes ("what exactly did this do for me?").
	- **Optimization era arrives**: Land O'Lakes demo — swapped a **500B-param model for a 5B model** at the same outcome. "Once you have consumption, everyone will optimize" — unlike the PC era, which "never got" to optimization because compute wasn't priced for it ("you will be found out if you don't optimize").

- ## GitHub Copilot & Coding
	- "Coding is everything" — what was a **tools business is now *the* business.** Microsoft was first to market with autocomplete but got caught flat-footed: started at code-completion → chat → tasks, then **Anthropic "showed up with a model" and the agent loop** redefined the category.
	- On **Cursor**: forked VS Code, "did a good job," but framed as "Borland vs us" — the real shift was **agentic coding becoming real**; Cursor faces the same disruption.
	- **GitHub reliability**: agents "all showed up to work… in GitHub" → scaling strain; customers unhappy; Nadella owns it as "job number one."
	- **Multi-model harness** (same harness across GitHub, Copilot, security, Cowork): **MAI by default**, plus GPT, Anthropic, and **any open-weight model** — e.g. fine-tune an open-weight model from **Fireworks** and drop it into Copilot. Cowork "is already **mostly defaulted GPT**" per Nadella *(editor's note: the Cowork FAQ still says it uses Anthropic models)*.
	- **Auto-routing** ("I'm mostly auto") is "perhaps one of the biggest continuous-learning things" at Microsoft. Favorite feature: **"rubber duck"** (use one model to check the others).

- ## Windows vs Project Solara
	- Two opposing center-of-gravity bets in the same keynote: **Nvidia-based Windows AI PCs** (local, "unmetered intelligence") vs **Project Solara** (devices as thin access points to **cloud agents** — ambient/ubiquitous computing, a frame Nadella traces to 2014).
	- **Wearable limitation**: continuous human-in-the-loop interaction is tiring → utility is capped. Solara's pitch: ask an agent, **it runs in the background** while you do something else.
	- **Windows enterprise value prop = "unmetered intelligence"** — amortize a Windows machine instead of an ever-rising cloud bill (demo: **8 agents running continuously** analyzing logs, all unmetered). "A billion users having that is not a side quest."
	- **Solara = a platform built for the agent era** (open platform rules, not porting phone apps); **enterprise-first** (a healthcare provider builds its own agent), partners **MediaTek + Qualcomm**. The opening: incumbents are **vertical/phone-stuck** ("can Apple make an agent that works everywhere while stuck on the phone?") → enterprises will "order a bunch of these from a no-name ODM."

- ## Datacenters & "Permission to Build"
	- On community programs (pay for electricity, no water use, build the tax base, education), Ben asks: why not just **pay residents a dividend** (effectively backing into UBI by "paying people to build data centers")?
	- Nadella: open to ideas, but wants **communities to keep control/agency and humans to keep dignity in work** — the real issue is the industry earning **"permission" to build out**. On job losses: **"If you're not creating opportunity, why would anybody want you to succeed? That's the fundamental memo that needs to be re-sent to everyone across our industry."**

- ## Investment Implications / Cross-Links
	- **Microsoft is deliberately de-risking from single-tenant (OpenAI) hyperscale** toward a diversified long-tail + own-apps + research-compute portfolio — explains the capex "underinvestment" optics and the Azure-vs-internal allocation trade-off (Jan-2026 0.1% miss). Read with the GPU-rental/neocloud economics ([[2026-06-05-gpu-cluster-rental-unit-economics-spacex-google-anthropic]], [[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]]).
	- **Infra margin *dollars* overtaking the software franchise** is a structural mix-shift signal for $MSFT — high ROIC in aggregate but an infrastructure-like ROIC layer underneath the agent/app layer.
	- **Hybrid pricing (seat + consumption) + the optimization era** is the monetization counter to "software is dead" and ties directly to model-routing / token-efficiency and the subscription-margin math ([[2026-06-11-ai-subscription-margin-by-utilization]], [[2026-06-03-foundation-model-pricing-power-bear-case]]). E7 ≈ 2× E5 is the ARPU lever against seat erosion.
	- **Enterprise-owned models (MAI + private evals/RLEs)** is a structural counter-position vs OpenAI/Anthropic on enterprise TAM — same thesis as the keynote memo, now in Nadella's own words; the unproven risk is whether "own model" customers fall behind frontier capability.
	- **Won't sell raw GPUs to Neolabs** = capacity-scarcity confirmation and a discipline signal (margin/ROIC over easy Azure revenue).
	- **MediaTek + Qualcomm as Solara/agent-device beneficiaries** ([[MediaTek-MTK-thesis]]); **multi-model harness commoditizes the model slot** (MAI/GPT/Anthropic/open-weight interchangeable) — pressure on any single model's lock-in, tailwind for routing/eval tooling.
