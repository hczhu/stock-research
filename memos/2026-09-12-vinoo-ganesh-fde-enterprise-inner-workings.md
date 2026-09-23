- tags:: [[$PLTR]], [[FDE]], [[forward-deployed-engineers]], [[AI]], [[enterprise]], [[SaaS]], [[moat]], [[AI-services]]
  file-created-at:: 2026-09-12

- ## FDEs: What Being Inside the Customer Reveals
	- **Source**: Vinoo Ganesh, “The Rise of the Forward Deployed Engineer — and How To Do the Job Right,” Latent.Space guest post, September 12, 2026; user-provided text. Ganesh draws on Palantir, Citadel, and Kepler experience; his platform argument also reflects his perspective as Kepler's co-founder.
	- **Thesis**: Enterprise AI's difficult work is discovering how a company actually operates, including undocumented definitions, manual checks, and exceptions. An FDE creates a scalable software asset only when those discoveries improve a reusable platform; otherwise, growth retains the labor and maintenance burden of bespoke services.

- ## Firsthand Glimpses Inside Large Companies
	- **A bank's production data broke a technically sound design**: Palantir's Phoenix transaction store worked against its specifications and test environments. At a bank, blank timestamps defaulted to 1970, triggering runaway retention-bucket creation and an out-of-memory failure.
		- The bank's bad data was routine to customer-facing staff and never became an explicit design requirement. The failure exposed a gap in ownership between the people who understood the customer and those building the product.
		- Deploying Ganesh into the field turned repair work into product discovery. Phoenix subsequently supported cybersecurity, KYC, AML, and other uses beyond its initial scope.
	- **A nearly year-long migration stalemate concealed a missing viewer**: A data-quality engineer repeatedly blocked CSV-to-Parquet migration despite arguments about storage savings and compute efficiency. Watching her work revealed that she downloaded CSVs from S3 to a Windows laptop, opened them, and visually inspected rows. That was the quality-control process.
		- Parquet would remove her existing inspection tool without replacing it. The team built a viewer overnight; she approved the migration two days later. **Pipeline execution fell from about 17 hours to 2 hours**—approximately **8.5× faster**, or **88% less elapsed time** (derived from the reported times).
		- Resistance to change protected an essential control. A small interface fix unlocked a much larger infrastructure improvement; interviews had missed the dependency because it seemed obvious to the operator.
	- **Temporary code becomes permanent infrastructure**: Ganesh wrote a one-afternoon retention script, `vinoo.groovy`, intended to last less than a week. A year later it was still running at a customer with nearly 100,000 employees, and the team maintained the workaround for years.
		- Solving the immediate request can create a lasting support obligation. Customer satisfaction alone does not demonstrate product scalability.
	- **One business object has several departmental identities**: Sales says “customer,” operations says “client,” finance records a billing entity, and engineering uses `org_id`. Translating across those names requires knowing when they refer to the same entity and when they do not.
		- In finance, a “position” differs between credit and equities desks; two funds can describe a return calculation identically while using different denominators. A database schema captures stored fields, but not necessarily their economic meaning.
	- **The real operating manual lives in people and spreadsheets**: Book-closing conditions, late-night exception approvals, and substitutes when an approver is away are often unwritten. Old decisions outlive their authors; critical spreadsheets persist because teams quietly depend on them.

- ## Why FDE Work Must Feed the Product
	- **Field insight can disappear inside the vendor too**: Early Palantir product teams learned from deployments through personal relationships rather than a systematic process. Whether an insight reached the platform depended on which FDE knew which product engineer.
	- **Ganesh's definition**: An FDE solves customer problems to discover what the platform must support next. A successful engagement changes what future customers receive, beyond satisfying the account in front of the engineer.
	- **Reporting lines shape the output**: Ganesh places Kepler's FDE function under product. He argues that sales incentives favor closing the current account, while product incentives favor reusable capabilities. The FDE title itself proves little: practitioners he met described sales engineering, quota-carrying sales, and consulting under the same label.
	- **Repeated workarounds are product signals**: Several customers requesting a feature may be less informative than engineers repeatedly bypassing the same platform limitation. The latter identifies a missing capability in the underlying system.
	- **Reuse changes deployment economics**: A capability added to the platform should reduce the cost of the next implementation and make experimentation cheaper. If each account starts from zero, revenue still depends heavily on incremental delivery labor.

- ## Verified Business Meaning as a Software Asset
	- **Kepler's design principle**: Financial numbers must carry provenance so a user can explain why they are correct. Ganesh says an incorrectly encoded business definition should surface as a failure rather than a plausible answer.
	- **The scarce knowledge is the corrected map**: Drafting a description of an enterprise is increasingly easy. Learning which definitions are wrong, correcting them in production, and keeping them current takes repeated customer exposure.
	- **Operations drift**: A previously correct definition can become stale as a company changes. Ganesh's proposed moat is accumulated, current, verified knowledge of a vertical's operations, encoded in a platform that can demonstrate its reasoning.
	- **Customization and scale can coexist**: Customer-specific vocabulary and policies need not mean entirely bespoke software. Shared capabilities can represent those differences while preserving each firm's actual rules.

- ## Enterprise Software Economics — Interpretation
	- **Palantir**: The Phoenix story supports the logic of using deployments to improve a common platform and expand into adjacent workflows. It illustrates a mechanism for differentiation; the article does not quantify current margins, retention, or deployment productivity.
	- **AI adoption**: Better models cannot independently recover undocumented approval rules or determine which return denominator a firm intends. Deployment effort can remain substantial even as coding and model access become cheaper.
	- **Software versus services valuation**: The useful distinction is whether successive deployments require less work and improve the shared product. Calling engineers “FDEs” does not establish recurring software economics.
	- **Ganesh's broader prediction**: Value is moving toward the customized final portion of enterprise workflows that determines whether standard software is usable. This is his strategic judgment, not evidence that the market for standardized SaaS is exhausted.
