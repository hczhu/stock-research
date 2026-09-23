tags:: [[AI]], [[agents]], [[enterprise]], [[implementation]], [[workflow]], [[security]], [[evals]], [[consulting]]
file-created-at:: 2026-05-03

- ## Critical Steps For Implementing AI Agents In Large Enterprises
	- **Source context**: user-provided enterprise implementation thesis
	- **Core claim**:
		- implementing agents inside large enterprises is much harder than consumer chat adoption
		- the work required to make agents safe and useful at scale will likely create a large services and internal-operations opportunity
	- **Who may capture the opportunity**:
		- existing consulting firms
		- new specialist consultancies
		- field / forward-deployed engineers from agent vendors
		- new internal agent-engineering or AI-operations roles
- ## Summary
	- The memo’s central idea is that the enterprise AI opportunity is not just about model vendors. A large share of value creation will come from the hard implementation work required to make agents function inside messy, legacy, high-risk organizations.
	- The transition from chat-style usage to agents participating in meaningful workflows changes the problem completely. Enterprises are no longer only asking whether an LLM can generate a good answer. They need systems that can access data, operate across applications, take bounded actions, and be monitored safely inside real business processes.
	- That implementation burden is why the labor demand around agents may be much larger than many people expect today. The challenge is not simply deploying a model, but redesigning enterprise operating systems around agent participation.
- ## Critical Implementation Steps
  
  | Step | What has to be done | Why it is hard in large enterprises | Implication |
  |---|---|---|---|
  | 1. Data connectivity and modernization | Get agents to talk securely to enterprise data across systems | Valuable context is often trapped in decades of legacy infrastructure that was not designed for agent access | Modernization, integration, and data access layers become prerequisite work |
  | 2. Security, entitlements, and scopes | Define access controls, entitlements, and safe scopes for agent actions | Agents can take actions across sensitive systems, so permissioning must be explicit rather than inherited loosely from human workflow norms | Identity, policy, and agent-governance layers become strategic |
  | 3. Monitoring, logging, and security operations | Build ways to monitor, log, and secure the work agents do | Enterprises need auditability, incident response, and post-mortem visibility for agent behavior | Observability and control planes are mandatory, not optional |
  | 4. Process documentation for agent use | Document organizational processes in a way agents can actually consume and execute against | Many real processes are tribal, undocumented, or inconsistent across teams | Knowledge capture and process formalization become bottlenecks |
  | 5. Human-agent workflow redesign | Decide what the new workflow looks like when agents and people work together, including who intervenes and where | Simply copying the old human-only workflow limits productivity gains and can introduce new failure modes | Workflow redesign is required to realize real ROI |
  | 6. End-state process evals | Build evals for the new target workflows and outcomes | Agent systems need process-level evaluation, not just model-level benchmark scores | Evals become part of production process engineering |
  | 7. Architecture and best-practice adaptation | Keep up with rapidly changing agent architectures and implementation best practices | What changes quickly for an individual user is much harder to re-platform inside a business process | Large enterprises face a constant tradeoff between stability and staying current |
- ## Preserved Technical Points
	- Agents must be able to access enterprise data **securely across systems**.
	- In many enterprises, the valuable context for agents still sits inside **decades of legacy infrastructure**.
	- Before agents can be used safely, enterprises need:
		- the right **access controls**
		- the right **entitlements**
		- the right **scopes**
		- reliable **monitoring**
		- reliable **logging**
		- security controls around agent work
	- Organizations must document processes in a machine-usable way, not just in a human-readable way.
	- The new workflow must explicitly define:
		- what agents do
		- what humans do
		- when humans step in
		- how exceptions are handled
	- Reproducing the old human-only workflow with agents layered on top will **mute the gains**.
	- Enterprises likely need **evals** tied to their most important end-state workflows, not just generic model evals.
	- The speed of change in the agent ecosystem is both a blessing and a curse:
		- innovation is rapid
		- stable enterprise system design becomes much harder
		- changing a production business process is far harder than swapping personal productivity tools
- ## Why This Creates A Services Opportunity
	- The amount of work implied by the steps above supports a large implementation market around enterprise agents.
	- That work can be delivered through:
		- internal agent-engineering teams
		- vendor FDE / implementation teams
		- consulting and integration firms
		- vertical agent companies that specialize deeply in one business domain
	- This is part of the rationale for **vertical AI agents**: domain-specific systems can go deep on one workflow family and help enterprises bridge the gap from model capability to production automation.
- ## Investment Framing
	- Positive for:
		- consulting and systems-integration firms that can own enterprise agent deployment
		- infrastructure and security vendors that sit in the control plane
		- workflow / API-centric software vendors that are easier for agents to integrate with
		- vertical agent companies with strong domain-specific implementation depth
	- Negative for:
		- simplistic “just add a model” narratives
		- vendors that underestimate integration, governance, and workflow-redesign costs
- ## Caveats
	- This is a thesis memo, not a benchmark study with quantified implementation ROI.
	- The strongest claim is directional: the operational work around enterprise agents will be much larger than the market often assumes.