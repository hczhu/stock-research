- tags:: [[AI]], [[RAG]], [[Confluence]], [[Jira Service Management]], [[enterprise]], [[knowledge-management]], [[unstructured-data]], [[Slack]]
  file-created-at:: 2026-05-02

- ## RAG Over Confluence in JSM Workflows: Why The First Attempt Failed
	- **Source context**: user-provided implementation anecdote
	- **Use case**:
		- build an AI layer on top of Confluence content to answer internal IT request questions inside Jira Service Management workflows
		- initial premise: a few thousand IT runbook articles existed in Confluence, were reasonably well written, and seemed like a strong base for retrieval-augmented answering
	- **Outcome**:
		- the project ran for roughly `6 weeks`
		- it ultimately failed in its original form
		- management later agreed that internal engineering time was less valuable than buying a purpose-built vendor solution

- ## Summary
	- The core lesson is that enterprise unstructured data is much messier than it appears when viewed as a static document corpus.
	- The initial assumption was straightforward: if the organization already had a couple thousand IT runbooks in Confluence, then a RAG layer should be able to sit on top of that corpus and answer repetitive support questions.
	- In practice, the content quality problem was large enough that retrieval over the raw wiki was not safe. The Confluence corpus contained stale pages, duplicates, abandoned drafts, and pages written for one team that were still discoverable by others. That creates a retrieval ranking problem before any model logic even starts.
	- The team found that a usable AI layer required either:
		- a serious content cleanup pass first, or
		- strong freshness / ownership metadata so the system could prefer current and authoritative documents
	- They chose the cleanup path, and that cleanup alone took about `1 month`.
	- The second, deeper problem was source-of-truth fragmentation. Many of the real answers employees needed were not in Confluence at all. They lived in Slack threads, email chains, Jira ticket comments, and even direct messages with senior engineers.
	- That meant a Confluence-only RAG layer could answer the easy, documented questions, but would systematically miss the harder operational questions whose true resolution history lived in fragmented conversational systems.
	- The anecdote also highlights an organizational constraint: not all employees had Jira / Confluence seats, and many employees did not consistently use Confluence anyway. The knowledge base was therefore structurally incomplete, not just poorly maintained.
	- The eventual resolution was to stop spending more internal time on bespoke automation and adopt a commercial tool instead. The team chose [[Risotto]] because management liked the product experience, and because it could bridge Slack threads and Confluence content better than the internal attempt. Even then, the underlying knowledge-quality problem remained unresolved.

- ## Preserved Technical Data Points

	| Topic | Data point | Value | Context |
	|---|---|---:|---|
	| Project duration | Time spent on the failed internal attempt | `~6 weeks` | Total time spent trying to make Confluence content useful for IT request answering via an AI layer. |
	| Knowledge base size | IT runbook corpus size | `a couple thousand` articles | Confluence was described as containing a few thousand IT runbook articles. |
	| Cleanup duration | Content audit / cleanup time | `~1 month` | The team chose to clean up Confluence content before trying to rely on it, and that work alone took about a month. |
	| Licensing / coverage issue | Seat coverage | not everyone had Jira / Confluence seats | One stated reason the knowledge base was incomplete was that the company had not licensed everyone. |
	| Vendor alternatives | Number of viable off-the-shelf tools considered | `~3-4` | The anecdote says there were at least three to four good external tools available. |

- ## Technical Failure Modes
	- **Corpus freshness failure**:
		- out-of-date pages
		- duplicate pages
		- half-finished drafts that were never archived
		- pages written for one team but retrievable by another
	- **Metadata failure**:
		- the corpus needed dating metadata and owner metadata so ranking could prefer fresh and authoritative content
		- without that, retrieval quality is degraded even before generation begins
	- **Source coverage failure**:
		- the actual resolution path for difficult questions often existed outside the wiki
		- critical problem-solving content was stored in:
			- Slack threads
			- email threads
			- Jira ticket comments
			- direct messages with senior engineers
	- **Workflow mismatch**:
		- a Confluence-only RAG layer can answer “easy” documented questions
		- it misses “gnarly” questions whose real answer lives in conversational or ticketing history

- ## Why This Matters For Enterprise AI
	- This example is a concrete reminder that enterprise AI success depends less on the model and more on data hygiene, metadata quality, and source-system coverage.
	- A wiki is not the same thing as an organization’s true operational memory.
	- If the real knowledge graph is split across docs, chat, tickets, and DMs, then a single-source RAG deployment will likely underperform unless it can unify those systems or impose much stricter knowledge-management discipline first.

- ## Investment Framing
	- The example is supportive of vendors that sit above fragmented enterprise systems and unify knowledge across chat, tickets, and documentation.
	- It is also supportive of the view that data cleanup, integration, and metadata governance are persistent bottlenecks in enterprise AI adoption.
	- The anecdote is mildly negative for the idea that enterprises can cheaply “just add RAG” on top of existing documentation and get high-quality automation without workflow and data remediation.

- ## Caveats
	- This is a single implementation anecdote, not a broad benchmark study.
	- The example is still useful because it preserves concrete operational details: corpus size, project duration, cleanup duration, seat-coverage gaps, and where the missing knowledge actually lived.
