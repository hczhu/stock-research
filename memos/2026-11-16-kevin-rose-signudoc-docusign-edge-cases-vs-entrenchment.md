tags:: [[$DOCU]], [[$DBX]], [[$GOOGL]], [[SaaS]], [[vibe-coding]], [[open-source]], [[switching-costs]], [[moat]], [[legal]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-16
file-updated-at:: 2026-11-16

- ## DocuSign Replacements: Edge Cases vs. Entrenchment, per an X Thread
	- **Source**: X thread on Nov 16, 2026, from two phone screenshots supplied by the user. The thread starts with a Kevin Rose (@kevinrose) post and continues with replies from Salina Mendoza (@inababi) and Lucas Dickey (@Lucasdickey). Post URLs weren't included. Practitioners' backgrounds are self-reported and unverified.
	- **Thesis**: The thread offers two explanations for why DocuSign alternatives fail. **Mendoza**, who has built a DocuSign replacement twice, says it's the edge cases and legal defensibility. **Dickey** says it's enterprise lawyers' habit of asking for "a DocuSign." Both explanations place DocuSign's moat outside the core signing feature that Rose rebuilt.
	- Related: [[2026-07-26-vibe-coded-jira-replacement-reverts-to-linear]] and [[2026-11-11-horizontal-saas-build-vs-buy-in-the-ai-era]].
- ## The Trigger: Kevin Rose's SignuDoc
	- **Claim**: "DocuSign wants **\$8,100/yr from a 15-person team** just to sign PDFs." That works out to about \$540 per seat per year (*my math*).
	- **SignuDoc**: open source, one-click deploy to the user's own Vercel account, **\$0 per seat**. Features: white-label branding, full audit trails, tamper-evident seals, and documents that never leave the user's cloud.
	- **Engagement** two hours after posting: **330K views, 4.8K likes, 333 reposts, 259 replies**.
- ## Salina Mendoza's First-Hand Experience
	- **Background**: Mendoza reports building this "twice," for platforms, "to replace docusign and their competitor," and is "deeply familiar with this work unfortunately."
	- **First reply (12:24, Nov 16)**: "The edge cases will get ya for sure but Godspeed."
	- **Second reply, after Dickey's pushback**:
		- "The edge cases will kill u. It's why many die in the space."
		- ^^"Legally defensible is the part that you do not learn until you have to defend it."^^
	- Mendoza's point, in short: the hard part isn't the signing flow but legal defensibility, and that only gets tested in a dispute, after the tool is in use.
- ## Lucas Dickey's Counterpoint: Adoption, Not Edge Cases
	- "Edge cases aren't the issue -- it's that DocuSign is an entrenched player and every attorney asks for 'a DocuSign'." Dickey otherwise vouched for Rose's competence.
	- **Alternatives already exist**: "Both Docsend and Google have built it." DocSend is part of Dropbox, and Google offers eSignature in Workspace.
	- **What limits their spread**: "adoption by enterprise, specifically because of corporate counsel and external counsel adhering to the IBM decision." This is likely a reference to the adage "nobody gets fired for buying IBM." Dickey calls it a "classic channel of deep entrenchment of an early player."
