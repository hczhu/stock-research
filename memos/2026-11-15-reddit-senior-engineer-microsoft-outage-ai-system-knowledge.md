tags:: [[software-engineering]], [[AI-coding]], [[coding-agents]], [[$MSFT]], [[reliability]], [[SRE]], [[layoffs]], [[labor]], [[India]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-15
file-updated-at:: 2026-11-16

- ## A Senior Engineer on Reddit: AI Writes the Code, but Humans Still Hold the System Knowledge
	- **Source**: u/icaneatassanyday (flair: Full-Stack Developer), "The Microsoft incident proved what I always thought about AI," r/developersIndia, posted about Nov 15, 2026. From a screenshot the user supplied on Nov 16, when the post was a day old, with **542 upvotes and 155 comments**. The thread URL and comments were not included. The poster's background is self-reported and unverified.
	- **Thesis (poster's view)**: AI is now very good at the "low layer" of software engineering: code, applications, tests and docs. The hard part is understanding large systems well enough to diagnose a failure, and AI is still bad at that. Companies that replace experienced engineers with AI will find out only after an expensive incident.
	- Related: [[2026-01-24-swizec-future-of-software-engineering-is-sre]] makes a similar argument, that value shifts from writing code to running it.
- ## The Poster's Argument
	- **Background claimed**: senior engineer who has built large projects from scratch at companies in the US, Europe and Korea, both before and after AI.
	- **What AI does well**: "AI is extremely good at writing code, developing applications, tests, docs and pretty much all things. But that's a very low layer in software engineering."
	- **What it does badly**: production systems are combinations of other complex systems. In Microsoft's case, that meant database, infrastructure, application and network "entangled together," with failure possible at "any of the thousands of checkpoints." AI lacks that cross-system context.
	- **Rollback still needs diagnosis**: "For even to rollback you need to point out what to rollback." The poster says Microsoft took "a whole 15 hours" to figure it out, which "probably cost the company the combined salaries of all employees laid off."
	- **System knowledge sits with the original builders**: a problem in a system the poster built might take them an hour to figure out, but "may take a day even with AI" for someone who hasn't worked on it.
	- **Conclusion**: "AI at best should still be an assistant to an engineer not the developer itself. Unfortunately companies will only realise it after the damage has been already done."
- ## The Incident, per Public Reporting
	- **Source**: [Wikipedia, "2026 Microsoft outage"](https://en.wikipedia.org/wiki/2026_Microsoft_outage), accessed Nov 16, 2026. The post doesn't name the incident. This is the Microsoft outage that matches its timing and description.
	- | Item | Reported detail |
	  | --- | --- |
	  | Timing | Began Nov 12, 2026, between 17:00 and 18:00 UTC. Microsoft reported broad recovery at 17:50 UTC on Nov 13, and services were fully restored by the morning of Nov 14 |
	  | Scope | Microsoft 365, including Outlook, Teams, Copilot and Exchange Online mailboxes. Issues were reported in 70+ countries, and about 430M people use Microsoft 365 |
	  | Cause (Charles Lamanna, Microsoft EVP) | Three issues in networking gateway servers combined: a previously undetected defect that left servers unresponsive under certain loads, a traffic-allocation change that raised load, and maintenance that cut fleet capacity by 14% |
	  | Why rollback didn't fix it | The defect shipped in **July 2026**, so automated rollback of the recent changes couldn't remove it. When the code fix was deployed, traffic overwhelmed the servers as they came back up, causing a cascading failure |
	  | AI's role | Microsoft said the outage was not caused by a cyberattack or by AI agents |
	  | Estimated cost | Anderson Economic Group put lost productivity at about **\$7B**. That cost fell on customers, not on Microsoft's own payroll |
	- **Differences from the post**: the post's "15 hours" refers to the time Microsoft took to diagnose the problem. Public reporting doesn't give a diagnosis time, but puts broad recovery at about 24 hours after the start. Microsoft attributes the outage to a latent gateway defect combined with load and capacity changes. It says AI agents were not involved and does not link the outage to layoffs.
