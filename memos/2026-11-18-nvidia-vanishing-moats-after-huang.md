tags:: [[$NVDA]], [[CUDA]], [[moat]], [[networking]], [[supply-chain]], [[$TSM]], [[TPU]], [[Trainium]], [[Anthropic]], [[neoclouds]], [[vendor-financing]], [[key-person-risk]], [[Jensen Huang]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Nvidia's vanishing moats after Jensen Huang
	- **Source**: user-provided article excerpt, "Nvidia, Most Valuable Company in the World, 2024–2026," written after Huang's November 12, 2026 resignation. The author and publication were not given.
	- **Thesis**: The author argues that Nvidia's four moats are weakening at different speeds, and that Huang's departure removes the two that depended on him personally: supply-chain trust and a startup-style organization. Margins were already exposed as LLMs made CUDA matter less.
	- Event context: [[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]].

- ## The four moats, as the author ranks them
	- | Moat | Why it worked | What is eroding it | Author's durability read |
	  |---|---|---|---|
	  | **1. CUDA software platform** | An API plus a huge set of libraries for every accelerated-computing market made it "a nearly impenetrable moat." GPT-era LLMs were written on CUDA | See the three LLM-driven risks below | Drying up |
	  | **2. Networking and systems** | Nvidia sells full systems, the easy answer for enterprises and governments that want to own hardware, and for neoclouds building data centers independent of the hyperscalers | Google's TPU systems, and by extension Anthropic. Neoclouds are running short of available power and political permission, and their funding increasingly comes from Nvidia itself | More durable, but challenged |
	  | **3. Supply-chain mastery** | Huang says he never signed a contract with TSMC in three decades. The relationship rests on a handshake and mutual trust with Huang specifically, "a very Asian way of doing business" | It is unclear whether TSMC's trust and willingness to commit will survive "when the handshake is no longer there" | **Suddenly much more tenuous** |
	  | **4. Not a normal company** | Huang organized Nvidia "as an exoskeleton around one man." He had 60 direct reports, little management and no succession plan, so Nvidia behaved like a real startup and made fast, aggressive bets | The same structure left no checks on Huang. With him gone, the exoskeleton "is much more poised to collapse than you might expect" | The most important moat, and the most at risk |

- ## How LLMs undercut CUDA
	- The author says LLMs brought Nvidia its success and also seeded its three biggest risks:
		- 1. **Developers moved up the stack**: most developer energy now targets an LLM's API as the platform. For most companies CUDA no longer matters.
		  2. **The leading lab proved it can leave**: Anthropic was funded by Amazon and Google, originally also-rans to the Microsoft–OpenAI partnership, so it had to learn Trainium and TPUs. That was hard, but it means the leading LLM has **no Nvidia dependency**. Anthropic still runs on Nvidia chips because it learned to run on anything.
		  3. **AI writes the software** (the author calls this the most devastating): LLMs are so good at writing software that "any software-based moat will inevitably dry up."

- ## Related evidence in the repo
	- **Culture**: an earlier HQ visit described "Jensen" coming up every few minutes, and flagged key-person and succession risk ([[2026-06-25-nvidia-hq-culture-visit-notes]]).
	- **Competitors using the gap**: Nvidia's leadership uncertainty helps Google pitch TPUs for customers' post-2028 plans ([[2026-11-15-google-tpu-openai-anthropic-orders-2029-mediatek-quillfish]]).
	- **Supplier relationships**: memory suppliers' HBM contracts are insulated by long-term agreements and prepayments, but chairman-level deal-making with Huang is the exposed part ([[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]]). This parallels the author's TSMC handshake point.
