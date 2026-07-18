- tags:: [[Anthropic]], [[OpenAI]], [[Claude]], [[Codex]], [[coding-agents]], [[agents]], [[developer-tools]], [[post-training]], [[reinforcement-learning]], [[tool-calling]], [[constrained-decoding]], [[model-labs]], [[AI]], [[$MSFT]], [[$AMZN]], [[$GOOG]]

- ## Better Models, Worse Tools — Tool Calling as a Model-Lab Moat
	- **Source**: [Armin Ronacher, “Better Models: Worse Tools”](https://lucumr.pocoo.org/2026/7/4/better-models-worse-tools/), July 4, 2026. The supplied text also included [Simon Willison's summary](https://simonwillison.net/2026/Jul/4/better-models-worse-tools/).
	- **Core thesis**: Tool calling is not a neutral capability that automatically improves with general model intelligence. Model labs can post-train models—potentially through reinforcement learning inside their proprietary agent harnesses—to use the labs' own tools exceptionally well. This creates vertical differentiation for Claude Code and Codex, but can make the same models less reliable with semantically equivalent third-party tool schemas.
	- **Investment takeaway**: The integrated **model + harness + tool schema + recovery logic + usage-data flywheel** can become a meaningful moat. The downside is declining portability: third-party coding products may need provider-specific tool definitions, strict constrained decoding, and compatibility layers merely to recover the performance the model delivers natively.
	- **Evidence boundary**: Ronacher directly observed a regression in newer Claude models on Pi's edit schema. His explanation—that Claude Code-oriented post-training and forgiving recovery logic caused it—is a strong, technically grounded hypothesis, not confirmed disclosure from Anthropic.

- ## The Observed Failure
	- Pi exposes an edit tool with a nested `edits[]` array; each entry permits only `oldText` and `newText`.
	- Claude Opus 4.8 and Sonnet 5 sometimes generated the byte-correct edit payload, then appended invented fields such as `requireUnique`, `matchCase`, `in_file`, `forceMatchCount`, `oldText2`, `children`, `notes`, or even `event.0.additionalProperties`.
	- Pi correctly rejected these calls because they violated the declared schema. Older Claude models did not exhibit the same regression in Ronacher's testing.
	- The failure appeared during realistic agent histories—after file reads, diagnosis, reasoning, and construction of a multiline edit—not in a clean one-turn “edit this file” test.
	- In a reproducible transcript, Opus 4.8 failed approximately **20% of continued attempts**. Removing thinking blocks from the retained history cut the failure rate roughly in half; Anthropic's strict tool invocation eliminated it in Ronacher's runs.
	- Codex models tested by Ronacher did not show the same regression, though he had not tested version 5.6.
	- **Important nuance**: The model understood the desired code change. Reliability failed at the final serialization boundary, showing that reasoning quality and tool-execution quality are distinct axes.

- ## How Tool Calling Actually Works
	- Tool calls are model-generated text surrounded by special tokens or markers. The client/API interprets that text as a structured invocation, validates the arguments, runs the tool, and returns the result to the model.
	- Without sampling constraints, the schema is only a learned convention: the model can understand the contract yet still emit an invalid key or structure.
	- **Grammar-aware / constrained decoding** masks tokens that would violate JSON syntax or the declared schema. In Pi's case, strict decoding can prevent the model from sampling any key except `oldText` and `newText`.
	- Nested arrays of objects containing long multiline strings are harder than flat tool parameters. After generating hundreds of escaped tokens inside `newText`, the model reaches a high-entropy choice between closing the object and inventing another field.
	- OpenAI's Harmony format explicitly marks a tool-call body as constrained JSON, allowing the inference stack to change sampling rules at the tool boundary. OpenAI also supports custom grammars for tools; Anthropic's strict mode appears to provide a comparable server-side guarantee, although implementation details are closed.
	- **Implication**: Tool reliability depends on the entire serving stack—prompt encoding, learned tool priors, schema shape, decoding constraints, validation, retries, coercion, and repair—not the model checkpoint alone.

- ## The Post-Training Hypothesis
	- Claude Code's native edit tool is comparatively flat: a file path, an old string, a new string, and an optional replacement flag. Pi asks the model to express the same intent through a nested array of edit objects.
	- Ronacher found that Claude Code's client tolerates substantial output variation:
		- Parameter aliases such as `old_str`, `old_string`, `new_str`, `new_string`, `path`, and `file_path`.
		- Silent removal of unknown keys.
		- Type coercion and Unicode-escape repair.
		- Detection and retry of leaked internal invocation markup.
	- If reinforcement learning occurs inside this forgiving environment, malformed calls can still complete the task and receive reward. The harness absorbs the mistake, leaving little negative training signal against aliases, extra fields, or slightly incorrect serialization.
	- At the same time, the model can develop a strong prior for the native Claude Code edit shape. An alternative schema with the same semantic purpose becomes off-distribution, and a newer, more heavily optimized model may resist it more than an older, less specialized model.
	- **Paradox**: More post-training can improve end-to-end success inside the lab's product while reducing compliance with third-party schemas. “Better model” and “better component” are no longer synonymous.

- ## Tool Schemas Are Becoming Model-Specific ABIs
	- A tool schema increasingly resembles an application binary interface: it is a technical contract, but actual performance depends on conventions embedded during training and on undocumented runtime behavior.
	- Model labs can differentiate through proprietary tool affordances even when competing models appear similar on general benchmarks:
		- Anthropic can optimize Claude for Claude Code's edit, shell, search, and agent-control primitives.
		- OpenAI can optimize Codex models for `apply_patch`, shell execution, structured commentary, and its own orchestration patterns.
		- Google can do the same for Gemini's native developer and Workspace tools.
	- Tool-specific RL makes the harness strategically important training infrastructure, not a thin user interface. Real usage generates failure traces and successful trajectories that can improve the next model and the recovery layer together.
	- Provider-native tools therefore benefit from a compounding loop: more users → more tool trajectories → better post-training and repairs → higher success rate → more users.
	- **Variant perception**: Open model weights alone may not replicate the commercial product's performance. The hidden asset is the tool-use distribution, reward environment, eval suite, and production harness accumulated around the model.

- ## Strategic Implications by Layer
	- | Layer | Benefit or risk | Strategic response |
	  |---|---|---|
	  | Frontier model labs | Native harnesses can outperform third-party wrappers using the same underlying model | Co-design schemas, post-training, decoding, and recovery; keep collecting proprietary tool trajectories |
	  | Native coding agents | Claude Code and Codex can deliver reliability that API benchmarks miss | Expand from coding into general knowledge-work tools while retaining control of the execution loop |
	  | Third-party coding harnesses | Model upgrades can silently degrade existing tools even when intelligence improves | Maintain provider-specific schemas/adapters; run transcript-level regression evals before changing defaults |
	  | Multi-model agent platforms | “Swap the model” becomes less credible when each model expects a different tool ecology | Route both model and compatible tool set; expose multiple edit tools or translate a canonical internal representation |
	  | Enterprise software vendors | Owning tool definitions and workflow telemetry can create a domain-specific post-training asset | Partner deeply with labs, train adapters/models, or enforce schemas through constrained decoding |
	  | Open-source models/harnesses | Transparency enables joint optimization and reduces dependence on hidden provider quirks | Standardize prompt formats and publish tool-use training/eval data, but accept fragmentation by model family |
	  | Model API customers | General benchmark gains may not translate into production agent reliability | Evaluate end-to-end task completion, invalid-call rate, retries, latency, and token waste—not intelligence alone |

- ## The Moat for AI Model Labs
	- **Vertical integration**: A lab controls the checkpoint, post-training environment, system prompt, serialization format, sampler, tool APIs, validators, repair logic, and product telemetry. Each layer can compensate for weaknesses elsewhere.
	- **Private data flywheel**: Successful and failed real-world tool trajectories are unusually valuable because they contain action, feedback, environment state, and task outcome—not merely preference labels.
	- **Hidden product performance**: A model may look unreliable through a third-party API harness while appearing highly reliable in the lab's product because the native client repairs the same output silently.
	- **Distribution advantage**: Users gravitate toward the product where the model works best, feeding more trajectories back to the native lab and weakening independent wrappers.
	- **Switching costs**: Enterprises that encode workflows around provider-native tool schemas and behaviors face more migration work than API compatibility suggests.
	- **Economic benefit**: Better native tool use reduces retries, wasted tokens, latency, and human intervention. It can support premium pricing even if base-model intelligence converges.

- ## Why This Is Also a Strategic Risk for Labs
	- **API ecosystem damage**: If newer models regress on non-native schemas, developers may view the API as unstable or conclude that the lab is privileging its own application over partners.
	- **Channel conflict**: Claude Code competes with products built on Claude; Codex competes with developer tools that might otherwise buy OpenAI inference. Tool-specific optimization deepens this conflict.
	- **Over-specialization**: Training too strongly on one harness can reduce general tool adaptability and make novel enterprise schemas harder to use.
	- **Opaque reliability**: Silent repair can hide raw model failure rates. Partners cannot reproduce native performance if the schema, aliases, retry state machine, or RL environment are undocumented.
	- **Standards pressure**: Customers may demand strict schema enforcement, portable tool protocols, published conformance tests, or open prompt formats if proprietary quirks become costly.

- ## Likely Responses From Third-Party Harnesses
	- **Provider-specific tool variants**: Present Claude with a Claude-Code-like edit schema, Codex with `apply_patch`, and other models with their preferred form rather than forcing one universal abstraction.
	- **Canonical internal action layer**: Let each model emit its native tool call, then translate it into a provider-neutral edit plan internally.
	- **Strict constrained decoding**: Turn on schema enforcement for high-consequence tools, accepting potential schema-complexity limits and possible quality tradeoffs.
	- **Forgiving compatibility layer**: Filter unknown fields, accept aliases, repair Unicode, coerce types, and retry malformed calls. This improves completion but can mask model regressions and create safety risks if used indiscriminately.
	- **Schema design for models**: Prefer flat, short, low-entropy parameters; avoid deeply nested objects containing long escaped content where possible.
	- **Model-version regression tests**: Replay long, realistic agent transcripts rather than relying on fresh single-turn tool benchmarks.
	- **Tool-set routing**: Route not only to the best model for a task, but to the matching bundle of tool schemas, prompts, validators, and recovery rules.

- ## Predictions and Falsifiable Checks
	- | Prediction | Expected direction | What to monitor |
	  |---|---|---|
	  | Native harness advantage widens | Claude performs better in Claude Code and Codex models perform better in Codex than in generic wrappers | Same-model, same-task completion comparisons across first- and third-party harnesses |
	  | Tool portability declines | Upgrading a frontier model causes schema-specific regressions despite higher general benchmarks | Invalid-call rates and retry counts by model version and tool schema |
	  | Multi-model products add provider-specific tools | Universal edit/search tools fragment into model-family variants | Cursor, OpenCode, Pi, and enterprise-agent tool definitions |
	  | Strict decoding becomes standard for consequential actions | Reliability and safety outweigh modest generation-quality costs | API defaults, schema complexity limits, adoption for payments, code changes, and enterprise actions |
	  | Harness telemetry becomes core training data | Labs increasingly describe product usage as a model-improvement flywheel | Disclosures on tool-use RL, synthetic environments, trajectory data, and evals |
	  | Agent benchmarks move end-to-end | Raw reasoning scores lose relevance relative to completed tasks, invalid actions, and recovery cost | SWE-style benchmarks that report tool errors, retries, tokens, latency, and human intervention |
	  | Model labs expand vertically into applications | Native tool specialization makes owning the product more valuable than remaining an API supplier | New lab-owned coding, research, browser, enterprise, and productivity agents |
	  | Enterprises demand portability controls | Large buyers resist undocumented harness dependence | Standard tool protocols, conformance suites, contractual version stability, and self-hosted gateways |

- ## Public-Market Read-Throughs
	- **[[$AMZN]] / [[$GOOG]] and Anthropic**: Anthropic's potential moat is broader than the Claude checkpoint. Claude Code supplies a proprietary tool-use distribution and usage flywheel that can reinforce model quality, enterprise adoption, and Bedrock/Google Cloud inference demand. The risk is partner disintermediation if Anthropic's native product captures the customer relationship.
	- **[[$MSFT]] / OpenAI / GitHub**: OpenAI's Codex-specific `apply_patch` training supports an integrated Codex moat, while Microsoft owns the largest developer distribution surface through GitHub and VS Code. The strategic tension is whether developers standardize on Microsoft's Copilot harness or OpenAI's native Codex environment.
	- **[[$GOOG]] / Gemini**: Google has the components to repeat the model-harness flywheel across coding and Workspace. Execution depends on integrating model post-training with stable, high-quality tool interfaces rather than treating Gemini as a replaceable API layer.
	- **Enterprise agent platforms**: Companies controlling systems of record and workflow actions can create valuable domain tool trajectories. Their defensibility improves if they own the action schema, permissions, evals, and feedback loop; it weakens if native model-lab agents can directly operate the same systems more reliably.
	- **Independent AI application vendors**: Wrappers face both margin pressure and technical dependence. Even with access to the best model, they may receive a less compatible component than the lab's internal product and bear the cost of adapters, retries, and cross-version regressions.
	- **Developer-tool market structure**: The likely equilibrium is not one interchangeable model API. It is a small number of vertically integrated stacks plus multi-model products that invest heavily in compatibility engineering and proprietary evals.

- ## Risks and Counterarguments
	- The observed result comes from a narrow Pi edit schema and a limited set of transcripts; it may be a temporary model or API bug rather than a durable strategic pattern.
	- Strict mode eliminated the failure, suggesting platform-level constrained decoding can restore portability without recreating the native harness.
	- Claude Code's repair logic may reflect pragmatic production hardening rather than the RL environment used to train Claude; no direct evidence links the two.
	- General model improvements could eventually overwhelm schema-specific priors and restore flexible tool following.
	- Open standards such as MCP can standardize tool discovery and transport, although they do not by themselves guarantee that models will faithfully emit every schema shape.
	- Third-party harnesses can differentiate through superior context management, UX, routing, permissions, and enterprise integration even if native tools retain a reliability advantage.
	- A lab that over-optimizes for its own applications may sacrifice high-margin API ecosystem revenue and drive customers toward competing or open-weight models.

- ## What to Monitor
	- Invalid tool-call and retry rates for each new Claude, Codex, and Gemini model on identical third-party schemas.
	- Whether strict schema enforcement remains optional or becomes the default, and how its complexity limits evolve.
	- Same-model performance gaps between native products and API-based third-party harnesses.
	- Model-lab disclosures about RL environments, tool-use training, trajectory data, and product-to-model feedback loops.
	- Cursor, OpenCode, Pi, and enterprise-agent support for provider-specific edit tools or schema translation.
	- Standardized agent benchmarks that include malformed calls, repair overhead, token waste, latency, and task success.
	- Evidence that enterprises are locked into provider-specific tool behavior despite nominal API or MCP portability.
