tags:: [[software-engineering]], [[SRE]], [[reliability]], [[observability]], [[DevOps]], [[SaaS]], [[vibe-coding]], [[AI-coding]], [[$DDOG]], [[Swizec-Teller]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-01-24
file-updated-at:: 2026-01-24

- ## Swizec Teller: when code gets cheap, operational excellence wins
	- **Source**: Swizec Teller, "The future of software engineering is SRE," swizec.com, Jan 24, 2026 (user-provided PDF of the post).
	- ^^**"People don't buy software, they hire a service."**^^
	- **Thesis**: AI makes writing code cheap, but customers pay for a service that keeps working: uptime, fast recovery, security, and someone accountable when it breaks. Value moves from writing code to running it. That supports SaaS vendors and reliability tooling more than the "everyone will build their own software" bear case allows.
	- Related: [[2026-07-27-vibe-coding-demand-destruction-vs-saas-operating-cost]], [[2026-07-26-vibe-coded-jira-replacement-reverts-to-linear]], [[2026-11-11-horizontal-saas-build-vs-buy-in-the-ai-era]], [[2026-11-13-bainbridge-ironies-of-automation-ai-agents-human-oversight]].
- ## The argument
	- **Code was always the easy part.** "Software engineering is programming over time. It's about how systems change." The hard part is keeping code running for years.
	- **Swizec's prediction**: "SRE about to become the most hired job in engineering. Everybody wants to write a greenfield demo. Nobody wants to run a service." Even if AI removed most coding jobs, the remaining ones go to engineers who can run systems.
	- **The no-code lesson**: an accountant automates a 10-hour weekly task with no-code tools and spreadsheet macros, cutting it to 1 hour.
		- Then the business changes, accounting rules shift, and timezone and daylight-saving bugs appear. A new edge case shows up every week.
		- The tool's owner can't take a vacation, can't hand it to anyone else, and dreads every run. The custom, throwaway software people call the future becomes a personal on-call burden.
	- **"The computer disease"** (Feynman's phrase): automating is fun, so people tinker. Karpathy says programmers could be "10X more powerful" by stringing together the new AI tools; dax replies that "the most common use of all these new knobs and levers is procrastination."
	- **Good software is invisible.** Nobody cares how iCloud syncs photos, how a document editor merges changes, or how a payment terminal talks to the bank, only that it works every time. "The first 90% to get a working demo is easy. It's the other 190% that matters."
- ## What a buyer is actually hiring
	- Swizec's list of questions a customer asks, grouped:
	- | What the buyer needs | Swizec's questions |
	  |---|---|
	  | **Reliability** | What's your uptime? Defect rate? How quickly do you recover? Will you know before I do? |
	  | **Dependency management** | Can you own upstream dependencies? When a vendor misbehaves, will you notice before users complain? |
	  | **Engineering at scale** | How do you keep engineers from breaking each other's systems? Can you build software bigger than fits in one person's brain? |
	  | **Coverage** | If I'm 12 hours away and your engineers are asleep, will a big issue be fixed before I give up? |
	  | **Data safety and security** | Can you recover from your own and upstream failures without losing data? Are you keeping up with security updates? Will you leak my data? |
	  | **Trust and accountability** | Do I trust you? Can I rely on you? Will you sign a legally binding guarantee that your software works when I need it? |
	- "Those are the ~~fun~~ hard engineering challenges. Writing code is easy."
- ## My notes
	- **The tagline reframes the AI-coding bear case for SaaS.** Coding agents cut the cost of producing software. Almost none of the table above is code production. Uptime, on-call coverage, security patching, dependency monitoring and a contractual guarantee are ongoing costs, and a SaaS vendor spreads them across every customer ([[2026-11-11-horizontal-saas-build-vs-buy-in-the-ai-era]]).
		- The vibe-coded Jira replacement that went back to Linear fits this exactly: building it was easy, and owning it wasn't ([[2026-07-26-vibe-coded-jira-replacement-reverts-to-linear]]).
		- The exposure is in software that is single-user and disposable, where no one needs an SLA. That is where demand destruction is real ([[2026-07-27-vibe-coding-demand-destruction-vs-saas-operating-cost]]).
	- **"Will you know before me?" is the observability business.** More AI-written code means more services to run and more failures to catch early. That supports $DDOG and agentic monitoring ([[2026-11-09-ben-congdon-agentic-monitoring-observability]]). Bainbridge's irony points the same way: automating the routine work makes the remaining operational work harder ([[2026-11-13-bainbridge-ironies-of-automation-ai-agents-human-oversight]]).
	- **Accountability can't be generated.** The last question, a legally binding guarantee, is something an in-house AI-built tool can't offer and a vendor can. *My note*: enterprise buyers pay partly for someone to hold responsible, which favors vendors with long reliability records.
	- **Labor read-through**: this matches the DeepMind essay's view that coordinators and people who keep systems running keep their wage premium while individual coding is commoditized ([[2026-10-29-deepmind-economics-of-intelligence-competence-coordination-agi-regimes]]), and Yegge's finding that human attention and quality control are the bottleneck in agent factories ([[2026-11-12-steve-yegge-agent-factories-human-bottlenecks]]).
	- **Limits**: this is an opinion post with no data. The SRE hiring prediction is asserted, not measured.
