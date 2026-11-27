tags:: [[$GOOGL]], [[Gemini]], [[Anthropic]], [[Claude]], [[Vercel]], [[coding-agents]], [[evals]], [[developer-sentiment]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-23
file-updated-at:: 2026-11-27

- ## Google's Gemini Neon vs. Claude Opus 5.5: a developer's "personal eval"
	- **Source**: X post by Guillermo Rauch (@rauchg, CEO of Vercel), November 23, 2026, about 75K views at capture (user-provided screenshot).
	- **The setup**: Rauch asked **Fable** to study all his **fx.sh** coding sessions and decide whether **Opus 5.5** or **Gemini Neon** is better. He calls it a "personal eval." Fable and Opus are Anthropic models.
	- **Thesis**: Fable picked **Neon, narrowly**: 7 edges and 1 tie, against 5 edges for Opus. Rauch: "Google being so, so back seems widely (and wildly) under-discussed."
		- **The split**: Neon produced far fewer **user-dissatisfaction** follow-ups. Opus was more **reliable at tool use** and much **faster**.
		- **Corroboration**: together with DHH's report the same day ([[2026-11-23-dhh-gemini-4-neon-coding-agent-harness]]), this is a second high-profile developer saying Google's new model is at or near the coding frontier.

- ## The scorecard
	- | Dimension | Opus 5.5 | Neon | Edge |
	  |---|---|---|---|
	  | "Not what I meant" follow-ups | 26/810 (3.2%) | 2/209 (1.0%) | Neon |
	  | "Undo / remove that" follow-ups | 6/810 (0.7%) | 0/209 | Neon |
	  | "Don't like it, redo" follow-ups | 45/810 (5.6%) | 2/209 (1.0%) | Neon |
	  | "It's broken / still broken" follow-ups | 59/810 (7.3%) | 8/209 (3.8%) | Neon |
	  | Intent + broken + undo, interactive work only | 13% | 13% | Tie |
	  | Turns the user cancelled | 68/731 (9.3%) | 2/138 (1.4%) | Neon |
	  | Failed file edits | 5/1,260 (0.4%) | 27/1,247 (2.2%) | Opus |
	  | Failed shell commands | 184/4,534 (4.1%) | 173/1,988 (8.7%) | Opus |
	  | Empty replies needing a nudge | 0 | 2 | Opus |
	  | Malformed tool calls | 12 | 0 | Neon |
	  | Own lines rewritten within the same turn | 3.5% | 4.8% | Opus |
	  | Own lines removed in a later turn | 5.7% | 3.8% | Neon |
	  | Median turn duration | **59 s** | **202 s** | Opus |
	  | **Overall** | 5 edges | 7 edges, 1 tie | **Neon, narrowly** |

- ## Reading the numbers (memo calculations)
	- **Sample size**: Neon has about a quarter of Opus's follow-up turns (209 vs. 810) and under a fifth of the user-cancellable turns (138 vs. 731). Rates such as 0/209 or 2/138 rest on very few events.
	- **The tie is the most telling row**:
		- Summed raw dissatisfaction rates favor Neon by about 3× (Opus about 16.8% across the four follow-up types, Neon about 5.8%).
		- But restricted to **interactive work only**, the combined intent, broken and undo rate is **13% for both**.
		- That suggests much of Neon's raw advantage reflects **session mix**, with Neon used more for long, autonomous tasks, rather than better answers like-for-like.
	- **Tool reliability favors Opus**: Neon's failed file edits run 5.5× Opus's rate (2.2% vs. 0.4%) and failed shell commands about 2.1× (8.7% vs. 4.1%). Neon had no malformed tool calls, against Opus's 12.
	- **Speed favors Opus**: Neon's median turn takes **3.4× longer** (202 s vs. 59 s). That matches DHH's description of Neon as a "quiet cat" that "goes off with very little output… and then, BAM, here's everything."
	- **Code churn is mixed**: Neon rewrites more of its own lines within a turn (4.8% vs. 3.5%) but has fewer lines removed later (3.8% vs. 5.7%). It iterates more inside a turn and its output survives longer.

- ## Memo's reading
	- **Two developers in one day**: Rauch and DHH, both influential with developers, report that Google's new model is at least competitive with Anthropic's best for coding. This extends Google's Q3 claim that Gemini 4 closed the coding gap ([[GOOG-2026-Q3]]).
	- **Two different styles**: Opus is fast and interactive, with reliable tools. Neon is slower and more autonomous, with fewer corrections from the user. Which wins depends on how a developer works. Like-for-like on interactive work, the two tie.
	- **The evaluator is notable**: an Anthropic model (Fable) running the evaluation and picking Google's model is a small credibility point for the result.
	- **Implications for Anthropic**: coding is Anthropic's main profit pool ([[2026-10-26-anthropic-s1-financials-compute-economics]]). A narrowing model gap moves competition toward speed, tool reliability and harness quality, where both developers favor Claude. This fits the short exclusive-window argument in [[2026-11-23-frontier-model-rd-nonlinear-returns-coding-sweet-spot]].
	- **Limits**: this is one user's sessions, judged by an LLM, with uneven sample sizes and no controls for task difficulty. It is a directional signal, not a benchmark.
	- **Update (2026-11-27)**: SemiAnalysis's GDPx follow-up ranks Neon behind OpenAI's 6.2 Astra and Anthropic's Fable 5.2 on most hard domains. It attributes Neon's popularity to **behavior, not intelligence**, and finds Google's weaker prompt caching makes Neon 18–32% costlier to run ([[2026-11-27-semianalysis-gdpx-gemini-neon-behavior-not-intelligence-caching]]).
