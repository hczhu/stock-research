tags:: [[legal-AI]], [[evals]], [[LLM]], [[$GOOGL]], [[Anthropic]], [[OpenAI]], [[enterprise-AI]], [[agents]], [[AI]]
file-created-at:: 2026-06-05

- ## "Law Professors Prefer AI Over Peer Answers" — Salinas et al. (Stanford et al., May 27 2026)
	- **Source**: Salinas, Frieders, Guha, Ma, … Nyarko, "Law Professors Prefer AI Over Peer Answers," May 27 2026 (Stanford + 14 U.S. law schools). All facts below are from the paper only.
	- **Thesis**: In a blinded, expert evaluation of short-answer contract-law tutoring, law professors preferred **LLM answers over those written by their fellow professors** — average win rate **75.33%** — with top models matching the best human instructor and flagged as harmful far less often. The study argues LLMs can capture a *latent professional standard of judgment* in a domain with no single ground-truth answer.
- ## Study Design
	- **16 U.S. contract-law professors** from 14 law schools, all teaching from the same casebook, acted as both **question authors, answer authors, and blinded judges**
	- **40 representative questions** across 4 categories: Recall-Case/Code, Recall-Doctrine, Hypotheticals, Policy
	- Answers written by the professors themselves or by two LLMs; neither humans nor models grounded in section-specific lecture notes
	- **2,918 blinded, forced-choice pairwise comparisons** (median 200 per judge): "which answer would you rather give a student?" + flag if "pedagogically harmful"
	- LLMs used at **default platform settings** (no temperature/decoding tuning) — authors call this realistic but conservative
	- Human evaluation ran **August 2025**; the two human-tested models were **Gemini 2.5 Pro** (stock) and **NotebookLM** (RAG-grounded in the casebook)
- ## Headline Results
  
  | Metric | Value |
  |---|---|
  | Average LLM win rate vs human instructors | **75.33%** |
  | Gemini 2.5 Pro avg win rate (vs all instructors) | 75.92% — beat all but one instructor |
  | NotebookLM avg win rate | 74.75% — beat every instructor (one tie) |
  | Pooled instructor average win rate (vs both LLMs) | 24.67% |
  | Individual instructor win-rate range | 2.96%–51.15% |
  | Median judge LLM-preference rate (human-vs-LLM) | 75.81% |
  | Minimum judge-level LLM win rate | 56% (every judge preferred LLMs) |
- ## Harmfulness (rarely flagged for LLMs; wide spread for humans)
  
  | Responder | Harmful rate |
  |---|---|
  | Gemini 2.5 Pro | 3.41% |
  | NotebookLM | 3.64% |
  | LLMs pooled | 3.53% (95% CI 2.44–4.61) |
  | Instructors (average) | **12.06%** (95% CI 9.02–15.10), range 1.00–39.75% |
	- Difference is highly significant (p = 4.7×10⁻⁷); LLM harm risk is comparable to the *best* human instructors
- ## Consistency of the LLM Advantage
	- **Across question types**: Gemini win rate 74.24% (Hypotheticals) → 77.17% (Recall-Case/Code); NotebookLM 72.69% → 76.80% — advantage holds in every category
	- **Shared standard, not idiosyncratic taste**: inter-coder agreement among judges exceeded the level implied by a mere LLM preference — strongest for Policy (≈0.77), then Recall-Case/Code (≈0.68), Hypotheticals & Recall-Doctrine (≈0.65). Judges applied a tacit common rubric even without ground-truth answers
	- **Not explained by style**: engineered textual features (length, clarity, structure, legal anchors, confidence tone, pedagogical support) only *partially* predict win rate; observed LLM wins systematically exceed style-predicted wins → advantage is at least partly **substantive content quality**, not surface polish
- ## Extended Model Ranking (LLM-as-judge: Llama-4 Maverick, validated vs human majority)
	- Bradley-Terry latent-strength order (strongest → weakest); **every AI model beat human instructors**:
	  
	  | Rank | Model |
	  |---:|---|
	  | 1 | Claude Opus 4.7 (highest) |
	  | 2 | ChatGPT 5.4 |
	  | 3 | Gemini 2.5 Pro |
	  | 4 | ChatGPT 5 |
	  | 5 | Claude Opus 4.1 |
	  | 6 | Gemini 3.1 Pro |
	  | 7 | Gemini 2.5 Flash Thinking |
	  | 8 | NotebookLM |
	  | 9 | Commercial AI Tutor |
	  | 10 | Gemini 2.5 Flash No Thinking |
	  | 11 | Gemini 2.0 Flash |
	  | 12 | Human instructors (lowest) |
	- **The gap is widening over time**: newest-generation models (Claude Opus 4.7, ChatGPT 5.4) rank highest; the strongest LLMs have pulled further ahead of experts since the Aug 2025 human eval
	- **Reasoning matters**: Gemini 2.5 Flash *Thinking* significantly outranks *No Thinking* — reasoning capability is central to legal-question quality
	- **Recency isn't monotonic**: Gemini 3.1 Pro ranks *below* Gemini 2.5 Pro (authors hypothesize Google deprioritized education-optimization, e.g. LearnLM, after 2.5 Pro)
- ## A Surprise: stock model beat RAG-grounded variants
	- **Stock Gemini 2.5 Pro outperformed both casebook-grounded systems** (NotebookLM and the commercial AI tutor built on Gemini 2.5 Pro), despite their retrieval grounding
	- Hypothesized causes: base model already encodes 1L Contracts doctrine (retrieval adds little); **"lost in the middle" / context-saturation** from feeding whole chapters dilutes relevant material; platform system prompts may counteract helpful base-model features
	- Implication: naïve RAG over long documents can *hurt* in a domain the base model already knows well
- ## Caveats (from the paper)
	- **Answer quality, not learning outcomes**: measures which answer an expert would prefer to deliver, not student learning gains
	- **Constrained setting**: short, office-hours-style answers — not full tutoring interactions
	- **Sample skew**: 16 of 60 eligible professors consented; over-represents T14 schools (38% vs 22% of pool), under-represents women (25% vs 33%), more tenured (94% vs 83%) — the "shared standard" is this subset's
	- **LLM-as-judge limits**: position/verbosity/in-family biases acknowledged; Maverick validated against human leave-one-out majority, giving confidence in the broad pattern if not exact ordering of close models
	- **Diverges from prior legal-AI studies** (Ouellette, Dahl, Magesh, Choi, Shojaee, Petrov) that found models "not yet acceptable" — authors attribute the difference to task design (expert *preference between plausible answers* vs accuracy-vs-rubric), a same-population human baseline, and being the first to test *reasoning* models
- ## Investment Implications
	- **Frontier reasoning models clear an expert bar in a judgment-rich vertical**: This is rigorous, blinded, expert-validated evidence that LLMs reach professional-standard quality in law — supporting the legal-AI monetization thesis and the broader "AI is good enough for high-stakes knowledge work" case
	- **Reasoning is the differentiator**: Thinking > No-Thinking and newest-gen models on top — bullish read-through to demand for reasoning-grade inference (more tokens/compute per query), reinforcing the agentic-token → inference → memory chain ([[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]])
	- **Model competition is close at the top**: Claude (Anthropic) and ChatGPT (OpenAI) outrank Google's own models here even though the study used Google models — no durable single-vendor moat at the frontier; $GOOGL did well but not best
	- **Naïve RAG isn't a free win**: stock models beating casebook-grounded variants cautions against assuming retrieval/grounding automatically wins — relevant to vertical-AI product design and the incumbent-data-moat debate in legal AI
	- **Caveat for the bull case**: the study measures *answer preference*, not learning outcomes or full tutoring — a reminder that "experts prefer the output" ≠ proven downstream value