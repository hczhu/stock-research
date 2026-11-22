tags:: [[$AMZN]], [[Amazon]], [[AWS]], [[Trainium]], [[Graviton]], [[Bedrock]], [[Firecracker]], [[agents]], [[advertising]], [[e-commerce]], [[logistics]], [[robotics]], [[Amazon Leo]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-22
file-updated-at:: 2026-11-22

- **Company**: Amazon (\$AMZN)
- **Date**: 2026-11-22. Converted from the owner's Google Doc ["Amazon \$AMZN Investment thesis"](https://docs.google.com/document/d/16qpoPIxdRiEW-KMB-GVKHFt7OYmWykVjYNSMEgCMHe4/edit).
- **State of the doc**: the narrative, earnings notes, anecdotes and data points have content. The template sections (napkin math, value drivers, moats, competition, risks, people) are still empty and are marked "Not yet filled in." The generic checklist and investing maxims are left out; they're in [[investment-thesis-template]].
  
  ---
- ## References
	- [Patents](https://patents.google.com/?assignee=Facebook%2c+Inc.) and [PDFs from .gov sites](https://www.google.com/search?q=filetype%3APDF+site%3A.gov+microsoft). The doc's links still search Facebook, Inc. and Microsoft, carried over from the template.
	- **Earnings notes in the repo**: [[AMZN-2026-Q2]], [[AMZN-2026-Q3]].
	  
	  ---
- ## Main Narrative
	- What the business will look like in 5–10 years, quality-wise. The doc's confidence column is still empty.
	- | Narrative | Notes |
	  |---|---|
	  | **Amazon's delivery network** | "You make money where something's scarce, and I think that Amazon's delivery capabilities are a pretty scarce resource" |
	  | **AI agents boost CPU and cloud service usage** | AWS's **Graviton** CPUs are more efficient than x86. AWS has rock-solid storage, database and container services, such as **Firecracker** |
	  | **Consistent AWS revenue growth in the AI era** | AWS can be a **neutral place for model providers**. AWS also has its own AI chip, **Trainium**, for both training and inference |
	  
	  ---
- ## Napkin Math
	- Not yet filled in. For reference, Jassy said on the Q3 2026 call that AWS should grow **40%+ in each of 2027 and 2028** and become a **trillion-dollar revenue business in five to ten years** ([[AMZN-2026-Q3]]).
	  
	  ---
- ## Key Value Drivers Not Yet Priced In
	- Not yet filled in.
	  
	  ---
- ## Durable and Unfair Competitive Advantages
	- Not yet filled in.
	  
	  ---
- ## Competition
	- Not yet filled in. For how enterprises choose between AWS and Azure for AI, see [[2026-11-04-expert-call-aws-bedrock-sales-motion-anthropic-economics]].
	  
	  ---
- ## Secular Trends
	- Not yet filled in.
	  
	  ---
- ## Innovative Culture
	- Not yet filled in.
	  
	  ---
- ## What Can Go Wrong?
	- Not yet filled in.
	  
	  ---
- ## People
	- Executives' ability to execute and adapt, shareholder friendliness, and employee happiness: not yet filled in.
	  
	  ---
- ## Anecdotes & Opinions
	- **Claude Code on the web uses AWS Firecracker microVMs (2026-02)**:
		- AWS is behind other hyperscalers on AI workloads. But AI agents shift the focus back to AWS's lead in traditional software infrastructure.
		- AI agents need secure, isolated, lightweight environments to run tools, and containers are often not isolated enough. That requirement resembles some non-AI workloads, such as Databricks' large-scale multi-tenant data processing, which AWS has supported for years.
		- AWS released Firecracker in 2018 and published a paper on it in 2020. Claude Code on the web running on Firecracker microVMs is a good example of AWS applying that lead to the AI agent ecosystem.
		- **Related**: [[2026-09-18-cpu-shortage-agents-cloud-capacity]], [[2026-11-19-modal-bernhardsson-gpu-prices-capacity-sandboxes]].
	- **Amazon bought Globalstar**: the doc has only the heading. Bloomberg puts the deal at **\$11.6B**, alongside about 300 Leo satellites in orbit ([[2026-06-28-bloomberg-andy-jassy-amazon-ai-boom]]).
	- **Are customers and users happy? Are vendors and partners happy?** Not yet filled in.
	  
	  ---
- ## Appendix: Earnings, Letters and Events
	- ### 2026Q2 earnings
		- **Graviton**: "the strongest CPU chip," with up to **30–40% better price performance** than other options.
		- **The investment cycle**: data centers, servers and networking gear are long-term, high-return investments **as long as supply matches demand**. AWS went through this investment cycle before in the cloud era, though demand built up more gradually than AI demand is building now ([[2026-07-30-jassy-aws-data-center-server-capital-cycle]]).
		- **Scale**: AWS will "very possibly" be a **trillion-dollar business**.
		- Full notes: [[AMZN-2026-Q2]].
	- ### 2026Q1 earnings
		- **AWS commitments and partnerships**:
			- **2 GW of Trainium capacity** through AWS, ramping from 2027. The doc doesn't name the customer; the repo attributes 2 GW to **OpenAI** ([[2026-08-28-aws-15gw-base-capacity-doubling-by-2027]]).
			- **4 GW** of current and future Trainium generations to train and run a customer's AI models. The customer isn't named; a later memo puts Anthropic's Trainium commitment at 5 GW.
			- AWS will be the **only cloud offering Cerebras fast inference**, through Bedrock.
			- **Meta**: tens of millions of **Graviton cores** for CPU-intensive agentic workloads.
			- **New models on Bedrock**: OpenAI's latest model, Claude Mythos Preview and Claude Opus 4.7.
			- **The majority of Bedrock's workloads run on Trainium.**
			- **Memory prices push on-prem to cloud**: surging memory prices are pushing on-prem infrastructure to the cloud, because memory vendors favor hyperscalers.
		- **Advertising**: persistent **20%+ growth**, at an annual run rate of **\$69B**. Advantages: Amazon's exclusive signals from shopping, browsing and streaming, plus sponsored product and brand prompts in **Rufus** ([[2026-06-04-amazon-advertising-advantages-identity-spine-dsp-ctv]]).
	- ### 2025Q4 earnings
		- **Early AI compute demand is barbell-shaped**:
			- At one end: AI labs and runaway apps.
			- At the other end: enterprises using AI for productivity and cost reduction, such as customer service and business-process automation.
			- In the middle: all enterprise production workloads, which **will be the largest**.
		- **Chips**: the chip business (Graviton plus Trainium) had a **\$10B run rate**. Graviton alone grew **50%+ YoY**.
	- ### OpenAI partnership (2026-04)
		- **Launches**: **Codex on Amazon Bedrock** and **Amazon Bedrock Managed Agents, powered by OpenAI**.
		- **How it works**: per the doc, "OpenAI models are not allowed in AWS." OpenAI's frontier models are instead packaged inside an AWS-native agent runtime that handles identity, permission state, logging, governance and deployment.
		- **Possible conflict**: this sits awkwardly with the Q1 note above that OpenAI's latest model is on Bedrock. The restriction may apply only to OpenAI's frontier models.
	- ### Shareholder letter (2026-04-09)
		- **Robotics**: "a step-level change" for faster delivery, cheaper wide selection, and automating movements that cause strain and injuries. **Over one million robots** work in fulfillment centers, still at an early stage.
		- **Rural delivery network**: **\$4B** committed.
		- **Amazon Leo**: a low-Earth-orbit satellite network with **200+ satellites** and a few thousand more coming. It will be integrated with AWS.
		- **AWS and AI**:
			- **AWS AI** has a **\$15B+ run rate** (Q1 2026), with deep service integration and a large customer base.
			- **Demand is high**: two large customers want all of 2026's Graviton capacity.
			- **Graviton** has **40% better price performance than x86** and is used by **98% of the top 1,000 customers**.
			- **Trainium**:
				- | Generation | Status |
				  |---|---|
				  | Trainium2 | **30% better price performance** than comparable GPUs (the doc marks this "??"); largely sold out |
				  | Trainium3 | **30–40% better than Trainium2**; nearly fully subscribed |
				  | Trainium4 | Significant pre-reservations ahead of availability |
			- The **chip business** has a **\$20B+ run rate** with **triple-digit YoY growth**. That is double the \$10B noted for 2025Q4.
			- **Useful lives**: **30+ years** for data centers and **5–6 years** for chips, servers and networking gear.
		- **Related**: [[2026-04-09-Trainium]], [[2026-03-20-asic-vs-gpu-trainium]], [[2026-11-18-trainium-tpu-native-pytorch-backends-privateuse1]].
	- **Proxy statements**: not yet filled in.
	  
	  ---
- ## Appendix: Data Points & Facts
	- **Amazon Supply Chain Services (ASCS)**: Amazon has announced ASCS, which offers other companies access to its "full portfolio" of supply-chain and distribution services.
	- **Rural retail, "a \$1 trillion market" (2026-03)**:
		- | Data point | Value | Source |
		  |---|---|---|
		  | Amazon 24-hour delivery of everyday essentials | Reaches **1 in 5 households** in rural and small-town America | Amazon |
		  | Americans within 10 miles of a Walmart store | **90%** | Walmart |
		  | Annual spending by rural US shoppers on clothing, electronics, household goods and other items | **\$1 trillion**, about **20%** of retail purchases excluding cars and gasoline | Morgan Stanley |
		- The \$4B rural delivery commitment in the April 2026 shareholder letter targets this market.
	- **More AWS context**:
		- [[2026-05-27-aws-bedrock-anthropic-hyperscaler-margins]]
		- [[2026-08-28-aws-15gw-base-capacity-doubling-by-2027]]
		- [[2026-10-21-hard-budget-caps-aws-gcp-agent-era-consumption-billing]]
		- [[2026-11-21-wsj-amazon-nyc-delivery-protection-act]]
