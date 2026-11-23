tags:: [[$GOOGL]], [[Gemini]], [[Anthropic]], [[Claude-Code]], [[coding-agents]], [[agent-harness]], [[developer-sentiment]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-23
file-updated-at:: 2026-11-23

- ## DHH on Gemini 4 Neon: frontier coding from Google, with a rough agent harness
	- **Source**: X posts by DHH (@dhh, David Heinemeier Hansson, creator of Ruby on Rails and co-founder of 37signals), November 23, 2026, reposted by Elon Musk (user-provided screenshot). The first post had about **207K views** and 3.9K likes at capture.
	- **Thesis**: a high-profile, opinionated developer reports that **Gemini 4 Neon** produced large real-world optimizations on his own Linux distribution.
		- **The model is competitive**: consistent with Google's Q3 claim that Gemini 4 closed its coding gap.
		- **The harness is the gap**: he calls Google's agent harness "a little rough" and says it should copy **Claude's agent overview**.
		- **Why it matters**: model quality looks close to parity at the frontier, so the agent product and UX around the model is becoming a differentiator.

- ## What DHH said
	- **Results**: "Gemini 4 Neon is indeed crazy good. **Cut Omarchy boot time in half!!** Big optimizations on install as well." Omarchy is DHH's opinionated Arch Linux and Hyprland setup.
	- **Working style**: "It's a quiet cat, though. Just goes off with very little output while it's working, and then, BAM, here's everything and it's perfect. Love it."
	- **The harness** (follow-up post): "The harness is a little rough, and they really need to **steal Claude's agent overview**, but who cares. We are so utterly spoiled to have this much frontier intelligence on tap. Incredible time to be alive!"

- ## Context in the repo
	- **The Gemini 4 family**: Google's Q3 call introduced **Argon** and **Carbon**. Carbon was No. 1 on the updated Artificial Analysis Intelligence Index at 59. Google teams using Argon shipped **35% more code with 30% fewer errors**. Coding, which management conceded was behind in Q2, became the headline ([[GOOG-2026-Q3]]). "Neon" appears to be another Gemini 4 model, and this post is the first mention of it in the repo.
	- **Agent benchmarks**: SemiAnalysis's agent benchmark had Gemini 4 Carbon narrowly leading software engineering ([[2026-11-06-semianalysis-gdpx-frontier-agent-performance]]).
	- **Earlier doubts**: Bloomberg reported internal skepticism about Gemini 4 ([[2026-10-01-bloomberg-openai-dots-meta-muse-agents-public-trust]]). SemiAnalysis framed August's DeepMind reshuffle as Google conceding the frontier ([[2026-08-06-semianalysis-gemini-cooked-gcp-cooking]]). DHH's post is a data point against those views on coding.

- ## Memo's reading
	- **Pressure on the coding profit pool**: Anthropic's growth is concentrated in coding ([[2026-10-26-anthropic-s1-financials-compute-economics]]). A credible Google coding model narrows that lead. This fits the claim in [[2026-11-23-frontier-model-rd-nonlinear-returns-coding-sweet-spot]] that exclusive windows at the frontier last months, not years.
	- **The harness becomes the moat**: DHH's complaint is about the **agent experience**, not the model. He wants visibility into what the agent is doing, which Claude's agent overview provides. If models converge, Claude Code's product polish, workflow integration and habits become Anthropic's defense, and harness quality becomes the next battleground.
	- **Second data point the same day**: Guillermo Rauch's "personal eval" of Neon vs. Opus 5.5 picked Neon narrowly. It also found Neon's median turn 3.4× longer, matching the "quiet cat" description ([[2026-11-23-google-gemini-neon-vs-opus-rauch-personal-eval]]).
	- **Why the post traveled**: DHH is influential with developers, and Elon Musk's repost spread it widely. It is one anecdote on a single codebase, not a benchmark.
