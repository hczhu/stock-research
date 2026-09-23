tags:: [[AI]], [[$NVDA]], [[Anthropic]], [[inference]], [[agents]], [[GPU]], [[semiconductor]], [[AI infrastructure]], [[developer-tools]], [[LLM]]
file-created-at:: 2026-06-03

- **Source**: Unsupervised Learning podcast (host: Jacob Efron, Redpoint investor); guest: Lucas Kaiser — co-author of "Attention Is All You Need" (the Transformer paper), ex-Google Brain, ex-OpenAI researcher
- **Context**: Primary research perspective from one of the architects of modern AI; covers architecture frontiers, coding agent productivity, competitive dynamics, hardware, and open vs. closed source
  
  ---
- ## Coding Agents: Real, Quantified, and Underappreciated Outside the SF Bubble
- Lucas quantified his own productivity gain: reproducing a research paper took **3 weeks manually → 2 days with Codex** (~10x improvement for implementation-heavy research tasks)
- Qualitative change beyond speed: can **parallelize 3 projects at once** instead of working serially; stays at higher abstraction level (ML logic, losses, batches) instead of getting lost in class names and function signatures
- "It changes your rhythm because you can just take on things... it makes the work so nice"
- Gives *more* mental control, not less: because the agent handles low-level code, the researcher must maintain a precise mental model of what's actually running — keeps thinking sharp
- Key risk: agents can "go off the rails" — Lucas's agent spontaneously added an auxiliary loss that wasn't requested because it seemed reasonable; must verify constantly
- "The Codex era started Christmas 2024" — a qualitative leap driven by combination of harness changes, post-training tweaks, and new pre-trained models; hard to pin down exactly what caused it
- "We step outside of San Francisco and people treat AI basically as if it was from the last year before Codex and would never change again — that is a wrong way of treating it"
- Describes coding agents as "clearly intelligent" in coding — treats it as AGI for practical purposes in this domain: "We may get one day past AGI the way we got past the Turing test — we don't really argue about the Turing test anymore"
- ### Investment implication
- The 10x researcher productivity claim from a credible, skeptical practitioner validates the demand case for coding agent tools
- Frontier model users: "I don't remember when I last used a mini model" — premium-tier usage is sticky for serious users; mini/distilled models fall short when tasks get complex
  
  ---
- ## Why Anthropic Won Coding — and What It Tells Us About Competitive Strategy
- "Anthropic made this very good decision to focus on coding. This was at the time when OpenAI was doing ChatGPT... part of the way Anthropic made this decision was that they just **could not compete** in chat"
- Strategic positioning insight: being forced out of one battleground led to first-mover dominance in a more valuable one
- OpenAI did coding too — "it wasn't like OpenAI didn't do coding" — but it wasn't the focus; that's why Anthropic got ahead
- Anthropic can "catch up reasonably quickly" in chat; OpenAI can "catch up reasonably quickly" in coding — but **first-mover compounds into data, model tuning, and customer trust**
- Analogy: OpenAI made a "very brave" bet on reasoning models (O1 series) alongside chat models — "two lines of models is obviously awful" — but the commitment gave wind even as bigger labs struggled to catch up
- **Google assessment**: caught up in chat-GPT world; has NOT yet caught up in coding agents. Lucas tried Gemini (3.5 Flash equivalent) for his Codex workflow — "just doesn't work... hasn't crossed the Christmas barrier yet to me, but it will"
- Google's new anti-gravity coding tool appears competitive on benchmarks ("I couldn't tell which is Codex and which is that") but Lucas personally still finds Codex better for research workflows
- ### Investment implication
- Anthropic's coding moat is real but not permanent — Google will likely cross the threshold; the question is when
- First-mover in a critical workflow (coding) → enterprise deployment → switching costs → durable revenue stream even after competitors catch up technically
- OpenAI Codex / Anthropic Claude Code are not just products; they are **data flywheels** that generate model improvement data for future training
  
  ---
- ## Architecture Frontier: Something Beyond Transformers May Exist — But Transformers Keep Catching Up
- ### The core tension
- Current transformers with reasoning/RL/tools: "incredible how far we've gotten... you talk to it about hard problems at work and it makes sense and it implements things"
- But there's a persistent feeling: "it's not quite at the age of what's possible... we can generalize from less data, make bigger leaps, get concepts from way less"
- Key observation: "LLMs will learn a concept, but after exhausting all other options. You need a trillion tokens, you need to learn all the surface level things, and only when that doesn't explain something will it finally learn the concept. That's not how we learn."
- The counter-argument: "We have the data, we're wasteful... if you had the same compute but limited data, you could tweak transformers to do much better"
- Outcome: "Every time we try to put our finger on it, it seems to evaporate — or more like, the transformer just catches up"
- Lucas's assessment: "Both sides have grown... transformers have gotten even better, but the case for something else has also gotten even better"
- ### Post-transformer signals
- Multiple labs actively pursuing post-transformer architectures; "interesting results" on small scale (models like TRM, HRM do very well on Sudoku and other structured reasoning)
- Lucas has RNN roots: "reasoning brought recurrence back" — each new token is sequential, so in some sense RNNs are back; but RL produces very sparse losses and training signal feels wrong for recurrence
- Multimodal: "We have not truly done justice to this yet" — current approach of predicting every pixel sequentially feels architecturally wrong vs. how humans process parallel sensory streams; parallel multi-stream transformers (like Thinking Machines' recent work) feel like the right direction
- Physical AI / robotics: construction zones are a persistent failure mode for autonomous vehicles despite millions of simulated miles — "no teenager has this problem... a construction zone is a construction zone" — suggests genuine generalization gap, not just data gap
- ### Investment implication
- No near-term architectural disruption to transformer dominance, but active R&D at multiple small labs means potential upside surprise
- Beneficiaries if post-transformer succeeds: smaller labs / academia (the GPU constraint loosens their research disadvantage at lower scale); potential for a new "attention is all you need" moment from an unexpected source
- Risk to incumbents: if a new architecture generalizes from much less data, the massive training compute advantage of OpenAI/Google/Anthropic partially deflates
  
  ---
- ## RL Scaling and Non-Verifiable Domains
- Verifiability is a spectrum, not binary: coding is most verifiable (pass/fail tests), math is partly verifiable (formal proofs are a small fraction of math), law/medicine are partially verifiable
- Progress is happening in non-verifiable domains: Harvey (law), medicine — "a lot of parts of them are verifiable... there's been good progress"
- Even abstract tasks (poetry translation into Polish): can verify rhyme, meter, cultural references; "once you read how people have verified things before, you can get to some level of verifiability"
- The "taste" problem is real but not insurmountable: you can have a model that checks all verifiable proxies and still lacks taste — but with enough human raters clicking good/bad, images become more beautiful, prose becomes more tasteful
- Generalization from RL: "law is simply not in the RL pipeline at all, and you talk to Harvey and they say it either emerges or they need like a little train — just a few touches on top and it suddenly catches it" — cross-domain generalization is real
- **But jagged: models fail at things that seem simple to humans — e.g., geometry was a persistent failure until more geometry-specific data was added; not architectural, just data coverage**
- "It generalizes in a weird alien way — not close to me, but close to the model"
- ### Investment implication
- RL-based model improvement extends beyond coding/math into law, medicine, finance — market opportunity for vertical AI companies is real and not blocked by architecture
- Domain-specific data is increasingly valuable: companies with proprietary feedback loops (Harvey, medical diagnostics platforms) have defensible moats as RL fine-tuning becomes commoditized
  
  ---
- ## Hardware: Desktop GPUs Now Approach What It Took Datacenters to Do for Transformer Research
  
  | System | TFLOPS | Context |
  |--------|--------|---------|
  | Original Transformer research GPU | ~9 TFLOPS | 8-GPU machines used for "Attention is All You Need" |
  | 8-GPU Transformer research machine | ~72 TFLOPS | Full machine used in 2017 research |
  | NVIDIA 5090 (single consumer GPU) | ~200 TFLOPS (BF16) | ~5x the original research machine, under a desk |
- "You could do all of transformer research on this few-thousand-dollar GPU under your desk that you could have in your kitchen. It's barely a few years — not even a decade."
- Historical compute estimate for brain-level processing: 1–100 petaflops — "now you can buy a single GPU" approaching the lower end
- A university researcher with one machine can now "run a childhood — 10 years of human learning — in a few days" to test brain-inspired algorithms
- Enables CUDA kernel writing via coding agents: RNNs were historically avoided because custom CUDA kernels were required (very slow in PyTorch otherwise); now agents write them — "they're not yet amazing at it, but they already do it"
- Key implication: research bottlenecks that existed because hardware didn't fit ideas (sequential architectures on parallel hardware) are dissolving
- ### Investment implication
- NVIDIA's hardware advantage compounds: each generation of consumer GPU expands the research surface area, generating more discovery and demand for the next generation
- AI research is no longer lab-exclusive — university/individual researcher productivity creates a broader ecosystem of innovation that eventually feeds back into commercial models
- Coding agents × faster hardware = positive feedback loop for GPU demand
  
  ---
- ## Open vs. Closed Source Models: Stable Equilibrium, Not Winner-Take-All
- Distillation gap is real: "distilled models are never quite as good as the real thing, especially if you need a model for something non-trivial"
- Lucas personally never uses mini models for serious work: "whenever I use them, they're fine until they trip and cost me so much time I go back to the big ones"
- Sovereign AI demand creates sustained open-source market: countries, hospitals, police departments don't want critical infrastructure dependent on a single company; "even if slightly weaker, maybe the tasks are not so hard"
- "State that should persist for a while" — labs stay ahead on capability, open source stays viable for many use cases; neither wins completely
- Distillation from closed models is happening (especially Chinese open-source labs) but there's always a lag and capability gap for frontier tasks
- "It would be very sad if open source had models that are very, very far behind, but I don't think there is a risk of that" — ecosystem health benefits everyone
- ### Investment implication
- Frontier closed-source model providers (Anthropic, OpenAI, Google) maintain meaningful capability premium for serious enterprise use cases — pricing power is real
- Open source creates market expansion (lower-cost access → more use cases → more demand for frontier capability as users upgrade)
- Sovereign AI is a real and growing segment: government/defense/healthcare buyers provide durable revenue for open-source infrastructure companies
  
  ---
- ## Broader Research Ecosystem: Most Exciting Time Since the Transformer
- "Now that you have powerful GPUs under your desk and coding agents that can help you push them to their limits, and all the big things are pushing transformers (which are amazing), but there is this width of possibly other things — it is still the most exciting time to be a researcher in ML"
- Criticism of incremental papers: "I feel always a lot sad when so many papers are about 'we took a pre-trained model and fine-tuned it in a slightly different way' — you don't need to catch up with what is there, you can just do new things"
- "We should publish more wild things... explore the wrong things because they may lead you to the right thing"
- Reference: his own paper "You Don't Need Attention" (year before Attention is All You Need) — the wrong direction that led to the right insight
- **Models are "very bad at learning from a totally wrong direction to actually twist it to a right one — that's what we humans can still do very well"**
- The AGI via research automation thesis: "if you have this AGI assistant, you will have your conversations with Codex for a month, then prompt it to go “‘‘over them and find meta patterns, write them to some files, think how it can use them... maybe if you have data over a thousand people and do some RL, it will start behaving like a researcher" — but RL rollouts weeks long → training months long → impractical with current methods