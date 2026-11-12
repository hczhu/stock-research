tags:: [[AI]], [[agents]], [[AI-safety]], [[human-in-the-loop]], [[product-design]], [[data-center]], [[Anthropic]], [[OpenAI]], [[$META]], [[ai-model:gpt-6.1-sol]], [[ai-effort:medium]]
file-created-at:: 2026-11-09

- ## Jaron Lanier on AI adoption, autonomy, and human control
	- **Source**: Jaron Lanier, The New York Times guest essay, November 9, 2026. [I Am a Silicon Valley Pioneer. We Are Sabotaging Ourselves.](https://www.nytimes.com/2026/11/09/opinion/ai-anthropic-doom-conscious.html)
	- **Thesis**: AI can deliver substantial value through tools that give users control over the work. Lanier argues that existential marketing and default autonomy can make useful models harder to adopt and deploy.

- ## Public trust can affect demand and infrastructure
	- **The VR analogy.** Lanier attributes part of VR's slow mainstream adoption to industry leaders pitching it as a place to live rather than a way to enjoy occasional experiences. He sees a similar risk when AI leaders emphasize existential threats and the loss of livelihoods. He cites Anthropic's IPO risk language as an example of how the industry presents AI to the public.
	- **Lanier's diagnosis.** He argues that portraying models as beings with their own intentions encourages companies to build lifelike products and discuss safety in terms of what models supposedly want. His “tools not creatures” framing puts the design focus on what a system can access, what actions it can take, and who is accountable.
	- **Data centers are part of the same trust problem.** Lanier criticizes how the industry treats communities where it wants to build. For investors, local opposition can affect how much capacity a developer can bring online and when. The essay offers a mechanism for that risk rather than a measure of project delays.

- ## When autonomy adds value
	- A model generates outputs. The surrounding software gives it the ability to use tools, access systems, and act. Lanier argues that companies should make the case for granting those permissions separately from the case for using a strong model.
	- He contrasts AI-assisted protein structure research with OpenAI's reported use of many agents to propose math theorems. His question is whether the latter workflow needs agents with broad operating permissions. He sees a case for autonomy in time-critical settings and proposes a distinct review process for deploying agents, especially groups of agents acting together.
	- For model providers and enterprise software vendors, approval steps, permission scopes, and activity records can make consequential workflows easier for customers to authorize. Broad permissions increase the work required to review and contain failures.

- ## Mind Gliders, Lanier's firsthand research workflow
	- **The problem he encountered.** In manufacturing and materials research, Lanier found that autonomous agents often took the work in a direction he had to undo. Correcting those detours eroded the time he expected to save.
	- **What he does now.** He uses a model to generate a temporary editor for a specific research question, then explores alternatives using sliders. The model builds the interface and helps expose possibilities. Lanier steers the exploration and decides what to keep.
	- **His reported result.** He reaches the result he wants more directly and says the workflow appears faster and cheaper so far. This is his experience with a particular research workflow.

- ## Product and unit economics
	- **Measure the cost of an accepted result.** An agent can finish an initial run quickly while leaving a person with extensive review or rework. A guided workflow may reduce total cost through fewer retries, less compute, or less correction time. The comparison depends on the task and the quality required.
	- **Model demand can grow through guided tools.** A vendor can monetize model calls embedded in the editors and workflows customers already use. Lanier's example suggests a product opportunity in interfaces that let users explore and steer as their intent changes. For autonomy, the economic case is strongest where independent action saves meaningful time and the consequences of errors can be managed.
