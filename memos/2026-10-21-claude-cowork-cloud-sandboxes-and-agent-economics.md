tags:: [[Anthropic]], [[Claude]], [[Cowork]], [[agents]], [[inference]], [[cloud]], [[product-strategy]], [[cybersecurity]]
file-created-at:: 2026-10-21

- ## Claude Cowork: Moving Execution, Not Inference, to the Cloud
	- **Source**: User-provided product explanation comparing old and new Cowork architectures; author, publication date, and original link not supplied. Product details below reflect that account, not independently verified rollout status.
	- **Thesis**: Moving Cowork’s execution environment off the laptop removes a practical adoption bottleneck and enables background work, while shifting sandbox operating costs to Anthropic. The change is in where tools run—not where the model runs.
- ## Architecture Changes
	- | Component | Old Cowork | New Cowork |
	  | --- | --- | --- |
	  | Model inference | Cloud | Cloud; unchanged |
	  | Tool execution | Anthropic-provided VM on the user’s computer | Cloud VM, with a separate sandbox for each session |
	  | Local-file access | Explicitly added data mapped into the local VM | Desktop app handles file-access tool calls, restricted to folders explicitly added to the session |
	  | Session isolation and lifecycle | Not detailed in the excerpt | Sandboxes do not share state across sessions and are destroyed when the session ends |
- ## Adoption: Less Device Friction, More Background Work
	- **Reported user complaints were operational:** disk usage, battery drain, performance overhead, and work stopping when the laptop closed. The account says users valued Claude’s capabilities but disliked hosting its VM locally; it supplies no adoption or satisfaction figures.
	- **Cloud execution separates work from the device interface.** The stated goals include phone access and keeping tasks running without the laptop hosting the VM. This moves Cowork toward delegated background work rather than a tool requiring the user’s computer to remain active.
	- **Local resources remain a dependency.** Because the desktop app still performs local-file tool calls, cloud execution does not establish that every workflow can finish with the laptop offline. Tasks needing additional local files may still require the device; offline behavior is not specified.
- ## Business and Infrastructure Economics
	- **Lower friction could expand usage — inference:** Removing the local VM burden may improve activation and allow longer tasks. Neither higher paid conversion nor greater engagement is demonstrated in the excerpt.
	- **Execution cost shifts to the provider — inference:** Anthropic now hosts the sandbox as well as inference, adding server compute, memory, storage, and orchestration requirements per active workload. Better utilization could offset some expense, but no cost-per-session, pricing, or margin data are supplied.
	- **Do not double-count inference demand.** Model inference was already cloud-based. The direct infrastructure shift is tool execution; additional inference demand would depend on users doing more work, not simply on moving the VM.
	- **Ephemeral sandboxes separate execution from durable workflow state.** Session isolation limits cross-session state sharing, but sandbox destruction does not establish deletion of chat history, uploaded files, logs, or other service records. The excerpt does not describe those retention policies or how unfinished work persists across sessions.
	- **Related memo**: [[2026-07-19-anthropic-cowork-claude-superapp-heath]] covers the broader product direction from a different source; this note focuses on the execution architecture and its cost trade-off.
