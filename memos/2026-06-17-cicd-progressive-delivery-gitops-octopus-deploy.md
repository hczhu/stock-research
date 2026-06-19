- tags:: [[CI/CD]], [[DevOps]], [[GitOps]], [[progressive-delivery]], [[platform-engineering]], [[feature-flags]], [[Octopus-Deploy]], [[developer-tools]], [[Kubernetes]], [[infrastructure]]

- **Source**: The Pragmatic Engineer Podcast — Rob Errors (CI/CD expert, ~10+ yrs; ex-Skype for Web; early engineer #8-9 at Octopus Deploy), interviewed by host (ex-Skype teammate)

- ## CI/CD Maturity Ladder

	- | Stage | Description |
	  |---|---|
	  | **YOLO** | Deploy directly to prod (SSH into the box, write in prod) |
	  | **Continuous Integration** | Merge code changes to a single branch continuously; run tests against every merge |
	  | **Continuous Delivery** | Any commit is deployable to production at any time; the deployment process itself is tested; human still clicks the final button |
	  | **Continuous Deployment** | Changes are automatically shipped all the way to production with zero human intervention |
	- Key distinction between Delivery vs. Deployment: in CD, the code is ready and could flow through automatically — but doesn't have to. In continuous deployment, it always does.
	- Not every org should pursue continuous deployment. Regulated industries (finance, gov) often require change advisory boards (CAB) and sign-off windows. Reaching continuous delivery is the high-value milestone; the final gate to prod can remain manual for compliance reasons.

- ## GitOps: The Four Formal Pillars (None Require Git)

	- Term coined by Weaveworks in 2017; formalized in early 2020s around Kubernetes.
	- | Pillar | What it means |
	  |---|---|
	  | **1. Declarative State** | Infrastructure/app state defined as a desired end-state (what you want), not an imperative sequence of steps |
	  | **2. Versioned & Immutable** | Desired state stored in a versioned, immutable store — so you can point to a concrete commit SHA or tag, not a moving target |
	  | **3. Pull-based (not push)** | A GitOps agent inside the cluster *pulls* the desired state from the store and applies it — external systems do not push into the cluster |
	  | **4. Continuous Reconciliation** | The system continuously monitors live environment vs. desired state and auto-corrects any drift |
	- **Key insight**: nothing in the four pillars mandates Git. The name "GitOps" causes engineers to assume *everything must go in Git*, which breaks down for secrets (raw secrets in Git are dangerous; Sealed Secrets is widely considered a workaround, not a solution).
	- The "everything in Git" absolutism is a conference-talk pattern; most customers just want to ship software. Use GitOps mechanics where declarative Kubernetes state fits naturally; use imperative orchestration steps (smoke tests, DB migrations, notifications) where they fit better.
	- Tools like Argo Workflows and Argo Rollouts exist precisely to layer orchestration on top of a GitOps core.

- ## Progressive Delivery Strategies

	- Progressive delivery = releasing changes in a controlled, gradual way rather than a single "big bang" drop to 100% of users.

	- ### Canary Deployments
		- Deploy the new version side-by-side with the old; use a traffic manager to route a small % of real traffic to the new version.
		- Gradually ramp the traffic % up, using observability metrics to decide whether to continue or roll back.
		- Unit of change: **the entire application artifact** (all commits since the last release ship together).

	- ### Blue-Green Deployments
		- Old version (Blue) stays live; new version (Green) spins up alongside it.
		- Run validation tests and warm up the Green environment before switching; then flip the traffic router to send 100% to Green in one move.
		- Effectively a canary that jumps straight from 0% to 100% after side-channel validation — eliminates cold-start issues.

	- ### Feature Toggles / Feature Flags (Most Powerful)
		- A conditional variable in code linked to an external config service; the active code path is determined at runtime by whether the flag is on or off.
		- | Dimension | Feature Flag | Canary / Versioned Deployment |
		  |---|---|---|
		  | **Unit of change** | Single line of code — all other code is identical | Entire app artifact — all commits since last release |
		  | **Targeting granularity** | Arbitrary rules (country, user attribute, cart contents, etc.) | Network-layer traffic split — very coarse |
		  | **Rollback speed** | Seconds — flip the toggle off | Minutes — redeploy previous artifact |
		  | **Deploy ↔ Release coupling** | Fully decoupled — ship binary Monday, release feature Tuesday | Coupled — feature goes live when deployment finishes |
		  | **Blast radius control** | Extremely fine | Bounded only by traffic % |
		- Decoupling deploy from release is the core superpower: ship the binary on a Monday, then release the feature on Tuesday morning when you're in the office, focused, with dashboards open — not at the exact moment ten other teams are also deploying.
		- Limitation: doesn't replace versioned deployments for infrastructure-layer changes (no app-level toggle applies) or for database schema changes.

- ## Database Schema Changes: The Hardest Problem

	- Schema changes are the canonical blocker for progressive delivery. The recommended pattern is **expand-and-contract** (also called "parallel change"):
		1. **Expand**: add new column/table while keeping old structure intact; both old and new code can run simultaneously.
		2. **Migrate**: backfill existing data; run both code versions in parallel.
		3. **Contract**: once the new code path is fully live and verified, remove the old column/structure.
	- This is straightforward for SaaS (you control what version is running) but extremely hard for self-hosted products — customers may skip multiple versions, so you can't force them through intermediate migration phases.
	- Octopus Deploy challenge: must ensure a DB migration script can successfully upgrade a schema that is potentially 3+ years old (e.g., 2023 → 2026 in one hop).

- ## Rollback vs. Roll-Forward

	- **The "rollback button" fallacy**: customers expect a simple undo button, but for any system with database state, a naive rollback is dangerous.
		- Rolling back app code while the DB schema remains at the new version causes old code to crash (it doesn't understand the new schema).
		- Even with down-migrations, data written to new columns during the outage window may be lost or corrupted.
	- **Preferred practice: roll forward**.
		- Create a hotfix branch, build it, push it through the pipeline immediately.
		- The bottleneck is pipeline speed — fast pipelines make roll-forward viable.
		- Your "rollback target" is logically version N+1 (explicit reversion of the broken code path), not version N-1.
	- **Feature flags as the ideal roll-forward tool**: flipping a flag off is not a rollback — it's a forward change that deactivates a code path. Safe, instant, no artifact redeployment.
	- **Only safe instant revert**: purely stateless logic changes (e.g., an if-else that touches no data model). Even then, best practice is to wrap it in a flag anyway.
	- Common self-deception: teams claim they roll back frequently without issues — until asked what happens when a DB schema change is involved. Usually they realize it's been luck.

- ## Platform Engineering: The Evolution of DevOps

	- DevOps anti-pattern at scale: individual app teams each build their own pipelines from scratch → wild bifurcation of processes + context overload for developers who just want to write code.
	- Platform teams solve this by:
		- Defining company-wide best practices and golden-path templates.
		- Providing a self-service mechanism (Internal Developer Portal / IDP) so teams can spin up new projects without reinventing deployment infrastructure.
		- **Keeping operational ownership inside the app team** — the app team still feels the production pain and fixes it (preserving the core DevOps benefit), but doesn't have to become cloud-infrastructure experts.
	- Not necessary for small orgs; becomes high-value when there are multiple teams with multiple projects and visible bifurcation of deployment patterns.

- ## Ephemeral / Preview Environments

	- Static "Dev" environments are becoming less useful. Trend: **ephemeral environments per pull request**.
		- PR is opened → CI pipeline provisions a completely isolated environment (microservices, containers, dependencies) from scratch → unique URL handed to the developer.
		- PM/designer/QA can review at that URL without coordinating on a shared staging slot.
		- PR merged or closed → environment torn down automatically.
	- Eliminates scheduling fights over a shared test environment; each feature branch gets a clean deployment.
	- **AI agent use case**: an AI agent can spin up an ephemeral environment, run end-to-end tests, validate UI behavior, and tear it down — without a human ever logging in. Changes how we think about environment provisioning at scale.
	- Key unsolved complexity: distributed microservice state (seeding the right stateful data for meaningful testing).

- ## AI's Impact on CI/CD

	- Still early; impacts are tightly coupled to how dev teams adopt AI agents.
	- **Pipeline speed becomes less critical**: if an AI agent owns the development loop and can babysit a 30-min build, the human attention cost of a slow pipeline disappears.
	- **Risk management becomes more critical**: higher code velocity from AI agents → higher inherent risk per unit time → more pressure on progressive delivery and feature flags to control blast radius.
	- **Feature toggles become essential infrastructure for AI agents**: agents can react to production signals (error rates, metrics) and flip toggles autonomously without needing a full redeploy cycle.
	- Octopus's internal position: deliberately avoided "AI" marketing at KubeCon; focus is on meaningful AI features — MCP server integration, deployment log review agent, recovery automation.

- ## Octopus Deploy Architecture Notes

	- | Phase | Architecture | Unit economics |
	  |---|---|---|
	  | SaaS v1 (~2020) | One dedicated VM per customer | ~\$100/customer/month cost vs \$20/month price |
	  | SaaS v2 (current) | Cell-based "Reef" architecture on Kubernetes in Azure; customer instances as isolated pods within shared cluster | Profitable |
	- "Reef" = isolated Kubernetes cluster containing shared infrastructure; each customer runs as a pod inside it.
	- Current infra project: making the deployment engine fully stateless and resilient so platform upgrades produce **zero downtime** (currently requires a brief draining window to cycle pods safely).
	- On-prem adoption curve: new version ships → **200 days for 50% of on-prem customers to upgrade; 400+ days for 75%**. Some enterprise customers run versions 5-6 years old.
	- Business rationale for maintaining on-prem: largest revenue customers are banks, financial institutions, and government agencies — they require absolute control over network perimeters and refuse to hand deployment pipeline keys to a SaaS provider.
	- Strategic insight for developer-tool founders: **supporting on-prem is a competitive moat**. SaaS-only is easier to build but hyper-competitive. A robust on-prem offering unlocks enterprise segments that SaaS-only products cannot close.

- ## Feature Flag Hygiene

	- Octopus internal practice:
		- Uses OpenFeature SDK with a custom wrapper.
		- Every toggle instantiation requires: **owning team metadata** + **explicit expiry date**.
		- When expiry passes: CI detects it and fires an auto-notification to the owning team ("this toggle looks fully rolled out — time to clean it up"). Nothing breaks in prod.
	- Observability signal: if a flag has been evaluated 100% as "true" for a month and 0% as "false" → safe to remove.
	- Cleanup sequence: remove the flag from app code via PR → let it travel through envs to prod → wait 1-2 weeks for stability confirmation → delete the config entry from the flag platform.
	- Metaphor: **code gardening** — feature flag cleanup is weeding. Without discipline, rolled-out flags become permanent technical debt ("just in case" leftovers).

- ## Book Recommendations (from Rob)

	- *The Phoenix Project* — foundational; aligns engineering understanding of prod behavior with business goals. Dated tech examples but timeless message.
	- *Radical Candor* (Kim Scott) — how to challenge directly while caring personally; counteracts the engineer tendency to be blunt on facts while missing the human empathy layer.
	- Greg Egan sci-fi (*Diaspora*, *Schild's Ladder*) — ultra-hard sci-fi by an Australian mathematician; builds entire narratives around rigorous physics premises.
