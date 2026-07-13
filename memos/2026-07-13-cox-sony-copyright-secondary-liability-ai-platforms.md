- tags:: [[$SONY]], [[$GOOGL]], [[$META]], [[$MSFT]], [[$AMZN]], [[$CMCSA]], [[$CHTR]], [[$T]], [[$VZ]], [[$WMG]], [[$DIS]], [[OpenAI]], [[Anthropic]], [[copyright]], [[AI]], [[generative-AI]], [[legal-risk]], [[platform]], [[DMCA]], [[internet-service-providers]]

- **Source**: Pamela Samuelson, "Overturning a $1 Billion Copyright Award Against a Broadband Provider," *Communications of the ACM*, July 2026, Vol. 69, No. 7, pp. 43-45, DOI: 10.1145/3815491. Extracted from local PDF `/Users/hc/Downloads/3815491.pdf`. The legal holding was cross-checked against the U.S. Supreme Court's [official opinion in *Cox Communications v. Sony Music Entertainment*, No. 24-171](https://www.supremecourt.gov/opinions/25pdf/24-171_diff_086c.pdf), decided March 25, 2026.
- **Thesis**: *Cox v. Sony Music* materially narrows U.S. contributory copyright liability for general-purpose technology and communications platforms. Knowledge that some customers infringe, combined with failure to stop them, is no longer enough: plaintiffs must show intent through active inducement or a product/service tailored to infringement. This is favorable for ISPs and potentially for generative-AI platforms facing claims based on infringing user outputs, but it does not protect direct infringement, induced infringement, infringement-specific products, or vicarious liability. The ruling shifts litigation toward evidence of product design, marketing, control, and direct financial benefit, while increasing pressure on copyright owners to seek statutory change.

- ## Decision Snapshot

	| Item | Data Point / Holding | Investment Read-through |
	|---|---|---|
	| Decision | Unanimous judgment reversing the contributory-liability ruling against Cox on **March 25, 2026**. | Strong Supreme Court protection for general-purpose service providers absent intent to facilitate infringement. |
	| Original verdict | Jury awarded **$1B** in statutory damages. | Demonstrates the extreme tail risk that secondary copyright claims previously created for intermediaries. |
	| Works at issue | Official opinion identifies **10,017 copyrighted works**; article describes approximately **10,000 infringements**. | Large catalogs can generate enormous statutory-damages exposure even without measurable economic loss per work. |
	| Approximate damages per work | Article calculates roughly **$100K per infringement**. | Statutory damages create nonlinear exposure for scaled platforms. |
	| Maximum alleged exposure | Official opinion says Sony alleged up to **\$1.5B** in statutory damages. | The reversed \$1B verdict was below the theoretical maximum. |
	| Cox subscribers | Approximately **six million** subscriber accounts. | At platform scale, account termination can disconnect many innocent users associated with institutions or shared networks. |
	| Infringement notices | MarkMonitor sent Cox **163,148 notices** over roughly **two years**, according to the official opinion. | Actual knowledge at scale still did not establish contributory liability without intent. |
	| Plaintiff monitoring vendor | Sony Music hired **MarkMonitor** to identify file-sharing IP addresses and notify Cox. | Rights owners can establish notice and repeat activity, but notice alone no longer proves contributory intent. |
	| Supreme Court vote | Justice Thomas wrote for seven justices; Justices Sotomayor and Jackson concurred in the judgment. | All justices agreed Cox should win, though the concurrence disputed how narrowly future secondary-liability theories should be confined. |

- ## The New Contributory-Liability Standard
	- A provider is contributorily liable for a user's copyright infringement only if it intended the service to be used for infringement.
	- The majority recognizes two ways to establish that intent:
		- **Inducement**: the provider affirmatively encourages, promotes, instructs, or otherwise takes active steps to cause infringement.
		- **Tailoring**: the product or service is designed for infringement and lacks substantial or commercially significant lawful uses.
	- The following combination is insufficient by itself:
		- The provider knows that some customers infringe.
		- The provider continues offering a general-purpose service.
		- The provider takes inadequate action to prevent repeat infringement.
	- Cox offered the same broadband service on standard terms to all customers and neither induced infringement nor designed broadband around infringement.

- ## What Changed From the Lower-Court Rule

	| Liability Theory | Before *Cox* / Lower-Court Approach | After *Cox* |
	|---|---|---|
	| Knowledge + material contribution | Providing a service while knowing recipients would use it to infringe could support liability. | Knowledge plus insufficient prevention is not enough without intent. |
	| General-purpose service | Substantial lawful use did not necessarily prevent liability when repeat infringement notices accumulated. | A standard service with substantial lawful uses is protected unless induced or tailored to infringement. |
	| Failure to terminate | Cox's rare termination of repeat-infringer accounts was central to Sony's claim. | Nontermination alone does not transform the ISP into a contributory infringer. |
	| Product design and promotion | Relevant, but plaintiffs could rely heavily on notice and continued service. | Becomes central evidence: plaintiffs must prove inducement or infringement-oriented tailoring. |

- ## Copyright Doctrine Behind the Decision
	- The Copyright Act expressly makes direct infringers liable but does not contain a detailed contributory-infringement provision comparable to patent law.
	- Section 106 gives copyright owners exclusive rights "to do and to authorize" certain uses, but Sony did not allege that Cox authorized subscribers' copying.
	- The Court was unwilling to expand judge-made secondary liability beyond previously recognized categories.
	- The doctrine rests on three major precedents:

	| Case | Year | Relevant Rule |
	|---|---|---|
	| *Sony v. Universal City Studios* / Betamax | **1984** | Selling a technology capable of substantial noninfringing uses does not create contributory liability merely because the seller knows some buyers will infringe. |
	| *MGM v. Grokster* | **2005** | A general-purpose product can still create liability when the provider actively induces infringement through promotion or other purposeful conduct. |
	| *Twitter v. Taamneh* | **2023** | Providing a general communications platform on standard terms does not establish aiding-and-abetting liability without purposeful assistance and a causal nexus; Samuelson argues this reasoning likely influenced *Cox*. |

- ## DMCA Safe Harbor: Important but No Longer the Main Defense
	- The 1998 DMCA provides safe harbors for qualifying online service providers, including a requirement to adopt and reasonably implement a policy for terminating repeat infringers in appropriate circumstances.
	- Cox could not use the DMCA safe harbor for the relevant period because an earlier decision found its repeat-infringer implementation inadequate.
	- The Supreme Court nevertheless held that failure to qualify for safe harbor does not create infringement liability.
	- The DMCA supplies an additional defense; it does not define the underlying offense.
	- Practical effect: a platform may lose safe-harbor protection yet still defeat contributory liability because the plaintiff cannot establish inducement or infringement-tailored design.

- ## Justice Sotomayor's Concurrence
	- Justice Sotomayor, joined by Justice Jackson, agreed Cox lacked the intent necessary for liability.
	- She objected to treating inducement and infringement-tailored services as the only possible common-law bases for secondary copyright liability.
	- The concurrence leaves conceptual room for aiding-and-abetting theories when a defendant intends to facilitate infringement.
	- It warns that the majority weakens incentives for intermediaries to process notices and enforce repeat-infringer policies.
	- Her hypothetical: under the majority's approach, an ISP might avoid liability even if it knowingly serves a company whose website exclusively hosts stolen copyrighted material, unless inducement or tailoring can be shown.
	- Investment implication: future plaintiffs will likely test the boundary between mere knowledge and purposeful assistance, especially where platform conduct is more specific than Cox's uniform broadband service.

- ## Vicarious Liability Remains Available
	- *Cox* addressed contributory liability; it did not eliminate vicarious copyright liability.
	- Vicarious liability generally requires:
		- The right and ability to supervise or control the infringement.
		- A direct financial benefit from the infringement.
	- Sony also won a vicarious-liability verdict at trial, but the Fourth Circuit reversed because Cox charged standard subscription prices and did not receive a direct financial benefit specifically from infringement.
	- The Supreme Court declined Sony's request to review that vicarious-liability ruling.
	- Platforms monetizing infringing activity directly, sharing revenue with infringers, or controlling specific content may therefore face materially different outcomes from Cox.

- ## Implications for Generative AI Copyright Cases
	- Samuelson argues that claims accusing generative-AI developers of contributory infringement merely because their systems materially contribute to infringing outputs they know will sometimes occur are "almost certainly" defeated by *Cox*.
	- This is a meaningful but limited protection:

	| Claim Type Against AI Provider | Likely Effect of *Cox* |
	|---|---|
	| User produces an infringing output; provider only knows such outputs sometimes occur | Materially harder contributory claim; generalized knowledge is insufficient. |
	| Provider actively promotes infringement or instructs users how to reproduce protected works | Inducement remains viable. |
	| Model/product is specifically designed around infringing uses and lacks substantial lawful utility | Tailored-service liability remains viable. |
	| Training itself allegedly copies protected works without authorization | Largely unaffected; this is primarily a direct-infringement/fair-use question, not secondary liability for user conduct. |
	| Provider controls infringing conduct and earns a direct financial benefit from it | Vicarious liability may remain viable. |
	| Generated output itself infringes and conduct is attributable directly to provider | Direct-liability theories remain outside the narrow *Cox* holding. |

- ## Public-Company Read-Through
	- **ISPs: [[$CMCSA]], [[$CHTR]], [[$T]], [[$VZ]]**
		- Positive legal precedent for standard broadband services provided uniformly to large customer bases.
		- Reduces catastrophic statutory-damages risk based solely on repeat-infringer notices and continued service.
		- Does not eliminate DMCA compliance costs, direct participation risk, or liability for services designed to facilitate infringement.
	- **AI and platform companies: [[$GOOGL]], [[$META]], [[$MSFT]], [[$AMZN]], OpenAI, Anthropic**
		- Positive for secondary-liability claims involving user misuse of general-purpose AI or communications tools.
		- Product marketing, safety controls, system prompts, fine-tuning, and responses to known infringement can become evidence of intent.
		- Training-data lawsuits remain largely untouched because many allege direct copying by the model developer.
	- **Copyright owners: [[$SONY]], [[$WMG]], [[$DIS]] and other media companies**
		- Negative for enforcement leverage against neutral intermediaries; notice volume and platform inaction no longer suffice.
		- Raises the cost of proving purposeful conduct and shifts enforcement toward direct infringers, inducement evidence, licensing, technical controls, and legislative lobbying.
		- Catalog owners retain direct, vicarious, and inducement claims where facts support them.

- ## Investment Implications
	- **Tail-risk reduction for neutral platforms**: Reversing a $1B verdict materially lowers the perceived U.S. copyright liability ceiling for general-purpose networks and tools.
	- **Intent becomes the key litigation battleground**: Internal documents, product decisions, marketing copy, monetization design, and refusal to add feasible controls will matter more than raw notice counts.
	- **AI legal risk shifts rather than disappears**: Secondary-output claims weaken, but direct training-copy claims and fair-use disputes remain central.
	- **Uniform terms are protective**: Cox benefited from offering the same service at standard prices; platforms that create special tools or commercial programs for infringement-heavy users may lose that factual advantage.
	- **Direct financial benefit is a crucial line**: Subscription revenue available regardless of infringement was insufficient; ad revenue, commissions, or usage fees tightly linked to infringing activity could support vicarious claims.
	- **DMCA compliance still matters operationally**: The ruling weakens the liability consequence of losing safe harbor, but repeat-infringer policies remain relevant to other claims, regulator relations, licensing negotiations, and litigation optics.
	- **Legislative risk rises**: Copyright industries may ask Congress to restore a knowledge-plus-material-contribution standard, though Samuelson expects strong opposition and doubts near-term congressional action.

- ## Variant Perception
	- **Overly bullish interpretation**: AI companies are now broadly immune from copyright liability.
		- Why wrong: *Cox* addresses secondary liability for another party's infringement; it does not resolve whether model training or provider-generated outputs directly infringe.
	- **Overly bearish interpretation for copyright owners**: Platforms can knowingly ignore all infringement without consequence.
		- Why incomplete: inducement, tailored-service, direct, vicarious, and potentially future aiding-and-abetting theories remain; Congress can also amend the statute.
	- **More precise view**: *Cox* materially protects neutral, multi-use infrastructure but increases the importance of facts showing purposeful facilitation, control, and infringement-linked monetization.

- ## What to Monitor
	- How lower courts apply "tailored to infringement" to generative-AI products with broad lawful uses but specialized reproduction features.
	- Whether AI copyright plaintiffs amend complaints to emphasize inducement, direct infringement, or vicarious financial benefit.
	- Discovery of internal model-provider documents discussing copyrighted-output use cases, guardrails, and monetization.
	- Continued enforcement of DMCA repeat-infringer policies despite the reduced contributory-liability threat.
	- Congressional proposals to codify a broader secondary-liability standard after *Cox*.
	- Licensing agreements between AI developers and music, publishing, news, film, and image-rights owners.
	- Whether courts adopt Justice Sotomayor's invitation to recognize aiding-and-abetting theories outside inducement and tailoring.
	- Differences between U.S. treatment and copyright regimes in the EU, UK, and other major AI markets.
