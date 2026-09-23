- tags:: [[LLM]], [[Anthropic]], [[xAI]], [[Grok]], [[Claude]], [[model-size]], [[AI-compute]]
  file-created-at:: 2026-04-09

- ## LLM Model Sizes — Grok, Claude Sonnet, Claude Opus (Leaked via Elon Musk)
	- **Source**: @elonmusk on X.com, reposted by Matti Vilola; screenshot via @agenda2033 thread (2026-04-09, ~18h ago from screenshot)
	- **Context**: @agenda2033 asked whether Grok 4.20 is truly 500B parameters or 500B *active* parameters inside a larger MoE (Mixture of Experts) architecture. Elon Musk replied with Grok's size and implicitly confirmed Claude's sizes.

- ## Model Size Table

	| Model | Parameters | Notes |
	|---|---:|---|
	| Grok (current) | 0.5T (500B) | Elon Musk confirmed; may be active params in a larger MoE |
	| Claude Sonnet | 1T | Leaked via Elon Musk's relative sizing comment |
	| Claude Opus | 5T | Leaked via Elon Musk's relative sizing comment |

	- Grok is **½ the size of Sonnet** and **1/10th the size of Opus**
	- Elon Musk's characterization: *"Very strong model for its size"* — framing Grok as efficient relative to its parameter count

- ## Context & Investment Implications
	- Claude Opus at 5T parameters is an extraordinarily large model — roughly 25x GPT-4's commonly cited ~200B scale
	- Models of this size require massive inference compute: HBM memory capacity and bandwidth become the binding constraint, not just FLOPS
	- Anthropic's inference workload at Opus scale directly supports the bull case for HBM demand (SK Hynix, Micron, Samsung) and for NVIDIA/TSMC
	- The MoE question on Grok matters: if 500B is *active* params inside a much larger sparse model, total memory footprint is far larger than the active param count implies
	- Sonnet at 1T and Opus at 5T suggest Anthropic's training and inference compute bill is enormous — consistent with Google's TPU commitment and Anthropic's fundraising scale
