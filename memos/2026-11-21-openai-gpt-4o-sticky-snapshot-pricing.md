tags:: [[OpenAI]], [[AI]], [[inference]], [[pricing]], [[ai-model:GPT-6.2 Sol]], [[ai-effort:medium]]
file-created-at:: 2026-11-21
file-updated-at:: 2026-11-21

- ## GPT-4o’s price fell when the default model changed
	- **Thesis**: OpenAI’s GPT-4o price history looks like a step followed by a plateau. A cheaper snapshot arrived in August 2024, the default alias moved to it in October, and the output list price was still USD 10 per million tokens in November 2026. A customer who pinned the May snapshot had to change versions to get the cheaper rate.
	- **Source**: OpenAI’s release announcements, model price cards and API retirement schedule, checked November 21, 2026. Prices are standard API text-token list rates in USD per million tokens. Input rates are for uncached tokens.

- ## The August release and the October alias change were separate events
	- | Date | What changed | Input rate | Output rate |
	  | --- | --- | ---: | ---: |
	  | May 13, 2024 | OpenAI releases GPT-4o. The original pinned ID is `gpt-4o-2024-05-13`. | 5.00 | 15.00 |
	  | Aug 6, 2024 | OpenAI releases `gpt-4o-2024-08-06`. Customers can select the lower-priced version directly. | 2.50 | 10.00 |
	  | Early Oct 2024 | OpenAI repoints the floating `gpt-4o` alias to the August snapshot, confirmed in an Oct 3 announcement. | 2.50 | 10.00 |
	  | Nov 20, 2024 | A new pinned snapshot, `gpt-4o-2024-11-20`, carries the same standard rates. | 2.50 | 10.00 |
	  | Nov 21, 2026 | OpenAI’s GPT-4o price card still lists the same rates. | 2.50 | 10.00 |
	- The August release lowered input by 50% and output by 33.3% relative to the May snapshot. The October change extended that rate to alias users. The public price points show a plateau of more than two years from the alias change through this check. [August release and price comparison](https://openai.com/index/introducing-structured-outputs-in-the-api/) · [October alias announcement](https://community.openai.com/t/latest-gpt-4o-snapshot-is-cheaper-and-supports-structured-outputs/966408) · [November snapshot release](https://developers.openai.com/api/docs/changelog#november-2024) · [GPT-4o price card](https://developers.openai.com/api/docs/models/gpt-4o)
	- OpenAI retired the May snapshot on October 23, 2026. It gave notice on October 14, 2026 that the remaining GPT-4o snapshots and GPT-4o mini were scheduled to shut down on January 14, 2027, with GPT-6 Luna listed as the replacement. This is the API schedule. [OpenAI API deprecations](https://developers.openai.com/api/docs/deprecations)

- ## Other 2024 models show both sticky rates and an exception
	- | Model | Early output rate | Latest or last documented output rate | API status as of Nov 21, 2026 |
	  | --- | ---: | ---: | --- |
	  | `gpt-4o-mini` | USD 0.60 at July 2024 launch | USD 0.60 | Scheduled retirement Jan 14, 2027 |
	  | `o1-preview` | USD 60.00 in Oct 2024 | USD 60.00 | Shut down Jul 28, 2025 |
	  | `o1` | USD 60.00 for Dec 2024 API release | USD 60.00 | Shut down Oct 23, 2026 |
	  | `o1-mini` | USD 12.00 in Oct 2024 | USD 4.40 | Shut down Oct 27, 2025 |
	- The checked price points show a 63.3% cut for o1-mini, evidence that OpenAI also reprices existing models. The matched early and late prices for the other rows give a useful comparison without establishing the path between every observation. [GPT-4o mini launch](https://openai.com/index/gpt-4o-mini-advancing-cost-efficient-intelligence/) · [October 2024 rate table](https://openai.com/index/api-prompt-caching/) · [o1-preview](https://developers.openai.com/api/docs/models/o1-preview) · [o1](https://developers.openai.com/api/docs/models/o1) · [o1-mini](https://developers.openai.com/api/docs/models/o1-mini) · [API deprecations](https://developers.openai.com/api/docs/deprecations)

- ## Why the model mix matters more than a smooth token-price curve
	- **Cheaper prices can arrive through migration.** GPT-4.1 launched at USD 8.00 per million output tokens. GPT-6 Luna lists USD 0.50 at the standard short-context rate, 95% below GPT-4o’s USD 10.00. This is a comparison of posted unit rates. Application cost also depends on input and reasoning tokens, retries, output quality, cache use and any engineering work needed to move. [GPT-4.1 launch](https://openai.com/index/gpt-4-1/) · [GPT-6 Luna price card](https://developers.openai.com/api/docs/models/gpt-6-luna)
	- **Compatibility can sustain a price premium.** Customers may pin a model to preserve evaluated behavior, latency or output formats. That makes it plausible that some traffic stays at old rates until an alias change, a planned migration or a shutdown. OpenAI’s public rate cards do not disclose serving costs by model, negotiated rates or traffic mix, so legacy margins cannot be inferred from the list price.
	- **For revenue models, separate SKU pricing from traffic mix.** Hold a legacy rate flat until a documented pricing event in the base case. Model migration and shutdown dates separately, then estimate how much traffic is retained, lost or expanded and how many billable tokens each workload consumes. The blended selling price can fall sharply even when individual rates barely move. For customers, track cost per successful task alongside cost per million tokens.
