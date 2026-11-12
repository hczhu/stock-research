tags:: [[$GOOGL]], [[Google]], [[DeepMind]], [[Gemini]], [[Demis-Hassabis]], [[AGI]], [[scaling-laws]], [[compute]], [[inference]], [[TPU]], [[world-models]], [[Veo]], [[AlphaEvolve]], [[Isomorphic]], [[AI-for-science]], [[AI-coding]], [[fusion]], [[quantum-computing]], [[Lex-Fridman]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2025-07-23

- ## Demis Hassabis on Lex Fridman #475: his predictions for AI
	- **Source**: Lex Fridman Podcast #475, "Demis Hassabis: Future of AI, Simulating Reality, Physics and Video Games," released July 23, 2025. User-provided transcript; timestamps are given as (h:mm:ss). Hassabis was Google DeepMind CEO at the time.
	- **Thesis**: Hassabis's forecasts favor compute suppliers more than any one model owner. He expects compute demand to keep rising, with inference becoming the larger share, and gives a **50% chance of AGI by 2030**. But he also gives **50/50 odds that scaling alone gets there**, and he says no system has yet made a real research leap. His case for Google is its research depth rather than its scale.
	- Related: [[2026-08-06-semianalysis-gemini-cooked-gcp-cooking]] (Hassabis left day-to-day operations in Aug 2026), [[2026-07-19-google-deepmind-talent-exits-anthropic-openai]].
- ## The predictions
	- | Prediction | Horizon | Where |
	  |---|---|---|
	  | **AGI: 50% chance**, using a high bar (consistent across all human cognitive functions, not "jagged") | By 2030 | 0:52:33 |
	  | Scaling alone vs new breakthroughs needed: **"kind of 50/50"**. DeepMind puts about **half its resources** on blue-sky research | Open | 1:04:17 |
	  | Compute demand keeps growing. Training "may even become the smaller part" next to inference | Ongoing | 1:06:42 |
	  | High-quality data won't run out, because simulations can generate synthetic data | Now | 1:05:37 |
	  | Chat text boxes "quite archaic" | "Just a couple of years" | 1:26:13 |
	  | Input and output bandwidth about **100×** today's, via glasses, earbuds, and eventually neural devices | Not given | 1:27:00 |
	  | AI that materially helps with solar materials, room-temperature superconductors and batteries | About 5 years | 1:08:38 |
	  | Programmers who adopt the tools become about **10×** more productive; top engineers keep their edge | 5–10 years | 1:43:27 |
	  | Societal impact about **10× the Industrial Revolution, 10× faster** (about 10 years instead of 100) | About a decade | 1:45:37 |
	  | Interactive, playable video world models; fully generative open-world games | 5–10 years | 0:19:55 |
	  | Virtual cell (yeast first) that runs experiments in silico, potentially a **100× speedup** | Not given | 0:42:41 |
	  | Fusion and solar as the main energy sources; a Kardashev Type I civilization would not surprise him | 20–40 yrs; 100 yrs | 1:09:15 |
- ## AGI: his test, and what's still missing
	- **His definition is stricter than most labs' timelines assume**: the system has to have *all* human cognitive capabilities with no jagged gaps, and "that's what we currently have with today's systems. They're not consistent." (0:53:06)
	- **His test**: a brute-force battery of "tens of thousands of cognitive tasks," plus giving a few hundred top experts ("the Terence Taos of each subject area") a month or two to find a flaw. (0:53:28)
	- **"Lighthouse" signs** (0:55:14): proposing a new physics conjecture, for example rediscovering relativity from a back-test using only knowledge up to 1900; or inventing a game "as deep… as elegant as Go." The system would need to do several of these, not just one.
	- **Two capabilities he says are still missing**:
		- Research taste. Proposing a conjecture worth studying is "far harder" than proving one, and "today's systems clearly can't do that." (0:38:03)
		- Large leaps. AlphaEvolve-type systems only hill-climb. "I don't think anyone has systems that can have shown, unequivocally those big leaps." (1:02:44)
	- **Recursive self-improvement**: possible end to end, but "I'm not sure it's even desirable because that's a kind of hard takeoff scenario." Current systems handle narrow targets such as faster matrix multiplication, but not "make a better version of yourself." (1:00:06)
	- **The open question**: whether incremental hill-climbing is enough "or do we actually need one or two more big breakthroughs." (1:02:03)
	- **Promising architecture**: hybrid systems that put search on top of foundation models (evolutionary methods, Monte Carlo tree search), as in AlphaEvolve and AlphaGo's Move 37. (0:31:28)
- ## Compute, chips and energy
	- **Three kinds of scaling at once** (pre-training, post-training and inference time), with "a lot more room" in each. (1:03:13)
	- **Inference demand**: models now serve "billions of people," and thinking models get better the longer they run at test time. "I don't really see that slowing down… as AI systems become better… there'll be more demand for them." (1:06:42)
	- **Training constraints**: the largest runs need co-located compute, so "even bandwidth constraints between data centers" limit them. (1:06:42)
	- **Silicon**: Google has its own TPU line and is "looking at inference-only things, inference-only chips." (1:07:57)
	- **AI for energy**: data center cooling and grid optimization are already in use. DeepMind works with Commonwealth Fusion on plasma containment, and reactor design may follow. (1:08:15)
	- *My note*: an inference-heavy mix and dedicated inference chips are the parts of this most relevant to compute suppliers. Data center interconnect matters because the largest training runs need co-located compute, which makes the network between data centers a constraint.
- ## Google's position as Hassabis argued it in July 2025
	- **Research depth**: "80–90% of the breakthroughs that underpins modern AI" came from Google Brain, Google Research and DeepMind. If a new breakthrough is needed, "I would back us to be the place that does that… It's harder to invent things than to fast follow." (1:03:47, 1:05:13)
	- **Release cadence**: about **6 months** per "giant hero training run" plus productization. Point-release versions such as 2.5 are post-training patches on the same base. Flash and Flash-Lite are distilled from Pro to cover "the Pareto frontier" of cost and latency against performance. (1:29:16, 1:30:51)
	- **Product design**: design for what models will do "in a year's time," and "get out of the way of the model." He expects AI-generated, personalized interfaces. (1:25:26, 1:27:58)
	- **Distribution**: the advantage is plugging research into surfaces with billions of users, often unseen, inside Maps and Search. (1:20:37, 1:22:34)
	- **AI for science**: other labs "talk about science, but I think we're really the only ones using it for science." Isomorphic's drug discovery is "going really well." He says the weather models beat traditional supercomputer simulations, including on cyclone paths. (1:39:01, 0:50:22)
	- **Talent**: Meta "are not at the frontier… it's probably rational what they're doing from their perspective because they're behind." He calls pay a side issue next to post-AGI economics. (1:40:21)
	- *My note*: many of these claims can now be checked against later events. Gemini 3 shipped in Nov 2025, consistent with the cadence he described. By Aug 2026, SemiAnalysis was calling Gemini "cooked," and Hassabis had stepped back from day-to-day operations ([[2026-08-06-semianalysis-gemini-cooked-gcp-cooking]]). His "breakthroughs, not scale" argument for Google therefore no longer has him running it.
- ## World models, video and games
	- **Veo learned physics by watching**: it models liquids, lighting and materials from video alone. That goes against his own earlier view that understanding physics needs embodiment or action. "It seems like you can understand it through passive observation." (0:17:27)
	- **Next step**: interactive video you can step into. That leads to "what I would call a world model… what you would need for a true AGI system." (0:18:06)
	- **Games**: within "five, 10 years," games generated on the fly around the player: "the ultimate choose your own adventure." This replaces hand-built assets, since "you can't create infinite amounts of game assets." (0:19:55, 0:22:46)
	- *My note*: if this is right, it reduces the moat of hand-built AAA content and game engines, and favors whoever owns the generative world model.
- ## Coding and labor
	- **Coding falls first** because code and math produce verifiable synthetic data. Over 5–10 years, people who adopt the tools become "superhumanly productive." Top programmers still win at specifying architecture and checking output. (1:42:58, 1:44:05)
	- **Scale of disruption**: "10 times the impact the Industrial Revolution had, but 10 times faster… like a 100X, the impact and the speed combined." He calls for "universal basic provision" and new governance institutions, with abundance coming first and distribution second. (1:45:37, 1:48:19)
	- Related coding memos: [[2026-04-06-future-of-coding-agents]], [[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]].
- ## Classical vs quantum computing
	- **Conjecture from his Nobel lecture**: any pattern found in nature can be "efficiently discovered and modeled by a classical learning algorithm." The reason is that natural systems were shaped by selection ("survival of the stablest") and so have structure that can be learned. (0:02:32, 0:04:03)
	- **Where quantum still matters**: problems with no learnable structure, such as factoring large numbers, "you maybe need a quantum computer." He also bets that the brain is classical, not quantum. (0:04:31, 2:06:26)
	- *My note*: this is a bearish frame for quantum computing's main promised market, simulating chemistry and materials. If classical neural networks keep doing what AlphaFold and the weather models did, quantum's advantage shrinks to structureless problems such as cryptography.
- ## Risk
	- **p(doom)**: he gives no number, but calls it "definitely non-zero and it's probably non-negligible." Both bad actors and loss of control matter, on different timescales. He thinks safety needs "10 times more effort" as AGI nears. (1:58:14, 2:00:00)
	- **Governance he prefers**: a CERN-like collaboration rather than a Manhattan Project, plus "some agreement internationally, at least between China and the U.S." on basic standards. (1:56:27, 2:02:14)
