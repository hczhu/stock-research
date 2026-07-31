- tags:: [[ontology]], [[Semantic-Web]], [[knowledge-graph]], [[agents]], [[AI]], [[enterprise]], [[data-governance]], [[RDF]], [[OWL]], [[graph-database]], [[Neo4j]], [[$PLTR]], [[$NOW]], [[software-engineering]]

- ## Ontologies Are So Back: Why AI Agents Are Reviving the Semantic Web
	- **Source**: Richard MacManus, Latent.Space, July 30, 2026; synthesizing presentations by UC Berkeley professor Frank Coyle and Neo4j CEO Emil Eifrem at AI Engineer World's Fair 2026
	- **Thesis**: Ontologies are re-emerging because probabilistic LLM agents need a deterministic layer that defines what entities exist, how they relate, and which actions are valid. The likely enterprise architecture is not a collection of self-contained "thick agents," but thinner agents operating on a shared semantic and governance layer that centralizes business meaning, data metadata, and execution history.

- ## What an Ontology Adds to an Agent
	- An ontology represents a domain as classes, properties, relationships, and constraints - what Coyle summarizes as "data as graphs."
	- LLMs contribute flexible language understanding and probabilistic reasoning; ontologies contribute formal definitions and machine-enforceable rules.
	- Coyle calls the combination **neurosymbolic AI**: the agent proposes an interpretation or action, while the ontology determines whether it is permitted and internally consistent.
	- The ontology turns language into computable context. "Customer," "order," and "refund" become typed entities with explicit relationships rather than ambiguous words embedded in a prompt.
	- This is especially important for agents because errors compound inside loops. A plausible but invalid output can otherwise become the input to the next tool call and push the workflow further off course.

- ## The Shared Semantic Layer
	- | Layer | What it represents | Agent value |
	  |---|---|---|
	  | Business-facing ontology | Real-world concepts, relationships, and rules that users recognize | Gives agents a common model of the organization rather than app-specific interpretations |
	  | Technical ontology | Data locations, schemas, attributes, ownership, and other metadata | Lets agents discover and correctly use data across fragmented systems |
	  | Execution traces | Agent decisions, paths, outcomes, errors, and runtime signals | Creates an auditable feedback layer for evaluation, repair, and ontology updates |
	- Neo4j's architectural claim is that these layers allow enterprises to replace agents with manually wired data sources and embedded business logic with **thin agents on a smart shared substrate**.
	- Centralizing semantics reduces duplicated integration work: an account-opening agent, AML agent, and customer-service agent can reuse the same definitions and governed relationships.
	- The shared ontology can therefore become both infrastructure and organizational memory. New agents inherit the accumulated context instead of rebuilding it in prompts, connectors, and application code.

- ## Agent Loop and Validation Pattern
	- Coyle's example places two gates around a tool call:
		- **Input gate**: schema validation checks the proposed tool name and arguments before execution.
		- **Output gate**: an ontology and reasoner check whether the result is coherent after execution.
	- The model emits candidate graph statements; the reasoner checks them against the ontology and returns a verdict such as **flag, reject, or repair**.
	- OWL rules can enforce constraints that prose only suggests:
		- An order can be refunded at most once.
		- Buyer and support-agent identities must be disjoint.
		- Order status must come from a fixed set rather than free text.
		- A refund must reference an entity typed as an order.
	- Other formal properties - transitivity, inverse relationships, symmetry, disjoint relationships, and domain/range typing - provide reusable consistency checks across workflows.
	- The practical design principle is a **bounded set of rules around an unbounded loop**: leave open-ended reasoning to the model, but constrain state changes and tool outputs with deterministic checks.

- ## Why the Semantic Web Is More Useful Now
	- Earlier Semantic Web efforts struggled because ontology creation and maintenance required extensive manual work while most applications did not provide enough economic payoff.
	- LLMs change both sides of that equation:
		- Established standards such as Schema.org, FOAF, Dublin Core, SKOS, RDF/RDFS, and OWL already appear in model training data and can be generated or interpreted through natural language.
		- Models can extract candidate entities and relationships from documents and reviews, reducing the cost of bottom-up ontology construction.
		- Agents can propose updates when runtime edge cases reveal missing or incorrect definitions.
	- The recommended construction method combines top-down expert definitions with bottom-up extraction and reuses established general or domain ontologies such as Wikidata, DBpedia, FIBO, and GoodRelations.
	- This makes old standards newly accessible: the LLM becomes the natural-language interface to a formal semantic system that previously required specialized developers.

- ## Adoption Constraints
	- Ontologies become stale when business concepts, schemas, policies, or source systems change. Automating proposed updates reduces labor but does not remove the need for ownership, approval, and version control.
	- A self-maintaining ontology can amplify errors if agents are allowed to rewrite definitions from noisy edge cases without human review.
	- Enterprises must reconcile competing definitions across teams. The hard problem is often organizational agreement about what a "customer," "active account," or "completed order" means, not graph technology.
	- Formal rules work best in bounded domains with clear invariants. They cannot encode every judgment call, so humans remain necessary for ambiguous, high-impact exceptions.
	- The architecture adds operational complexity and latency: reasoners, provenance, policy checks, and repair loops must be observable and performant enough for production workflows.

- ## Public-Company Synthesis
	- **Neo4j** is positioning the graph database as the semantic substrate for agent fleets rather than merely a database queried by individual applications.
	- **[[$PLTR]]** is closely aligned with the source's architecture: its ontology-centered model, governed actions, and deployment work address the business-definition and operational-maintenance problems that model capability alone does not solve.
	- **[[$NOW]]** has a similar structural opportunity through CMDB, workflow relationships, permissions, and execution history. Agent value should rise when these assets are exposed as a governed semantic layer rather than isolated records.
	- Model vendors benefit if ontologies increase production-agent reliability and token consumption, but the durable enterprise moat may sit above the model in proprietary definitions, relationships, policies, and execution traces.
	- Standalone graph and semantic vendors face platform-bundling pressure from enterprise software and cloud providers that already control identity, metadata, workflows, and distribution.

- ## Predictions
	- Enterprise agent platforms will make entity models, relationship schemas, policy constraints, and provenance first-class product objects rather than hiding them inside prompts.
	- Runtime traces will increasingly feed evaluation systems and proposed ontology changes, creating a loop between agent behavior and the semantic layer.
	- The most scalable agent deployments will use many thin, task-specific agents sharing centrally governed business logic instead of duplicating logic in every agent.
	- RDF, OWL, Schema.org, and other Semantic Web standards will return selectively where interoperability and deterministic validation matter, without reviving the original vision of semantically marking up the entire public web.
	- Near-term production adoption will concentrate in bounded, auditable workflows such as compliance, payments, identity, customer service, and industrial operations, where invalid state transitions have measurable costs.
