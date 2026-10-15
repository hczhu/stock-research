tags:: [[text-to-SQL]], [[evals]], [[benchmarks]], [[LLM]], [[agents]], [[RAG]], [[enterprise-software]], [[data-warehouse]], [[BI]], [[data-quality]], [[Michael-Stonebraker]], [[$SNOW]], [[$MSFT]], [[$CRM]], [[$GOOGL]], [[$ORCL]], [[Databricks]], [[AI]], [[regulation]]

- ## Stonebraker: Real-World Text-to-SQL Collapses to 0-30% vs 80-90%+ on Public Benchmarks
	- **Source**: BLOG@CACM, *Communications of the ACM*, October 2026 (Vol. 69, No. 10, p. 10) — "Converting Text to SQL, and Computing to Fix Red Tape." Lead post: **"If You Think You Can Do Real-World Text-to-SQL"** by **Michael Stonebraker** (MIT, 2014 ACM Turing Award, database management) and **Peter Baile Chen** (MIT CSAIL PhD student), DOI 10.1145/3838721. Extracted from user-provided photos of the printed page. Benchmark scale figures marked *(public)* are added context from the benchmark sites, not the article.
	- **Thesis**: Public text-to-SQL leaderboards (Spider 1.0, BIRD, Spider 2.0) report 80-90%+ accuracy, but on **Beaver** — built from real enterprise warehouse query logs — a pure LLM scores **zero**, RAG + prompt engineering + agentic AI reaches **10+%**, and even handing the model the gold `from`-clause tables and join clauses only reaches **30+%**. Stonebraker calls the gap "the difference between 'the technology has promise' and 'the technology does not work.'" The investable read: NL-over-warehouse is **not** a solved commodity. Value accrues to whoever curates per-customer semantics and metadata, and AI BI lands first on **greenfield, clean-schema** warehouses — not the rotted Oracle estates where most enterprise data actually lives.

- ## Why Text-to-SQL Matters Commercially (article setup)
	- Data warehouses arose in the **1990s** for historical customer-facing data, especially sales. At the time they were "widely reported" to **pay for themselves on better stock rotation in less than six months** — the article's example: if pet rocks are "in" and Barbie dolls are "out," discount the pet rocks and move them to the front; tie up the Barbie manufacturer with a big order so competitors cannot get merchandise.
	- Though some traffic is repeated reporting ("produce the weekly sales report"), **much of the workload is ad hoc**.
	- Historically warehouses were fronted by BI tools — **Business Objects, Power BI, Tableau** — letting business users build queries through a GUI. Natural language would **further empower non-programmers** and remove the need to learn a bespoke interface. With LLMs and agentic AI "this becomes a real possibility."

- ## The Four Issues With Public Benchmarks
	- **1. "The data is in 'the pile,' so LLMs can train on it."** An LLM "can only find data it has seen before." Almost all real warehouses sit **behind serious enterprise access controls and are not publicly available**, so a score on a published schema is not evidence of performance on a private one.
	- **2. Schema rot.** A warehouse "begins life with a well-structured schema," but it is updated as business conditions change, the company **buys or sells business units**, and regulations change — **often multiple times a year**. Enterprises rarely invest in a clean replacement schema, so schemas "rot," leaving **non-intuitive table and column names**. The article's example: **six different columns across various tables labeled "salary,"** with overlapping undocumented semantics — one meaning "net after taxes and commissions," another "gross salary." **Materialized views** used to accelerate popular queries add further ambiguity. These give an LLM "multiple ways to solve a query and to generate headaches."
	- **3. Idiosyncratic data.** The MIT administration warehouse (students, faculty, buildings, classes) contains **"J-term"** (a one-month January term between fall and spring semesters) and **numbered rather than named buildings**. "Such bespoke information is difficult for an LLM."
	- **4. Query complexity.** Real warehouse queries are **more complex than the student-generated ones** in Spider and BIRD — they "rarely have just one join and often two or three."
	- **Spider 2.0 addresses only the fourth issue, not the first three.** Its agentic-AI leaderboard is in the **90+% range**.
	- Authors' standard (pull quote): *"Any text-to-SQL benchmark should address the difficulties of real-world data stores. Those that do not are of academic interest only, and do not reflect reality."*

- ## Benchmark Landscape
	- | Benchmark | Scale *(public)* | What it tests | Reported accuracy |
	  |---|---|---|---|
	  | **Spider 1.0** (Yale, 2018) | 10,181 questions / 5,693 SQL queries, **200 databases**, 138 domains | Cross-domain generalization to unseen schemas | Article: **80+%**. Public leaderboard tops ≈91% |
	  | **BIRD-SQL** (HKU + Alibaba DAMO, 2023) | 12,751 pairs, **95 real databases**, 33.4 GB, 37 professional domains | Dirty values, required domain knowledge, query efficiency (Valid Efficiency Score) | Article: **above 90%**. Public leaderboard ≈82% vs 92.96% human |
	  | **Spider 2.0** (2024-25) | Real enterprise Snowflake/BigQuery warehouses, large schemas | Adds **query complexity** only | **90+%** for agentic-AI solutions (≈2-24% at 2024 launch) |
	  | **Beaver** (MIT, Stonebraker/Chen) | **9,128 queries over 812 tables, 19 domains**; 7,978 public, remainder held private | **All four** real-warehouse issues | **0% / 10+% / 30+%** depending on scaffolding |

- ## Beaver: Construction and Results
	- Built over **two years** of running LLM-based text-to-SQL on **real workloads from real data warehouses**. Started with the MIT administrative warehouse — an **Oracle warehouse of 1,400+ tables** queried by many MIT units including CSAIL.
	- **Ground-truth methodology**: business users normally pose a question to IT personnel, who translate it to SQL "often with clarifying dialog between the two people." The team pulled **real queries from the Oracle log** and generated the corresponding natural language **with the assistance of real users**, producing (natural language, gold SQL) pairs. The same methodology was then applied to **three other data warehouses**; queries and data were **anonymized and extended with permission**.
	- All **four issues are present by construction**, so the authors "do not expect to get the same high accuracy as Spider/Bird."
	- **Accuracy ladder** — the core result:
	- | Configuration | Beaver accuracy |
	  |---|---|
	  | Pure LLM | **Zero** |
	  | + RAG, prompt engineering, and agentic AI | **10+%** |
	  | + gold `from`-clause tables and actual `join` clauses supplied to the LLM | **30+%** |
	  | Public benchmarks for contrast (Spider / BIRD / Spider 2.0) | **80-90+%** |
	- Even the 30+% figure is **not an honest end-to-end score** — it hands the model the schema-linking answer (which tables, which joins), which is precisely the step schema rot breaks. The unaided real-world number is the **10+%** row.
	- Authors' framing: the gap is **"50+% lower in accuracy than the public benchmarks"** and is "the difference between 'the technology has promise' and 'the technology does not work.'"
	- Beaver is **publicly available** with a leaderboard; the authors explicitly solicit better systems ("So have at it!"). Their own approach is the **Rubicon** system.
	- **Closing conclusion**: *"Good results using traditional LLM/agentic AI technology are likely only on data warehouses with clean schemas, simple queries, and little idiosyncratic data. Otherwise, try Rubicon or your good idea."*

- ## Cross-Checks Against Public Data
	- **The article's two headline numbers run opposite to the public leaderboards.** It cites Spider 1.0 at "80+%" and BIRD "above 90%"; publicly Spider 1.0 tops ≈91% while BIRD's best test-set system is ≈82%, still **below the 92.96% human baseline** (dev-set figures run higher than test, which may explain the BIRD number). Directionally immaterial to the argument — both are saturated relative to Beaver.
	- **Spider 2.0's trajectory is itself evidence of saturation**: built in 2024 to be enterprise-hard, early systems scored ≈2.2% (DAIL-SQL + GPT-4o) to ≈23.6% (Spider-Agent + o1-preview); roughly two years later the agentic leaderboard is at **90+%**. A benchmark that is public gets solved — which is Stonebraker's first issue restated as a time series.
	- Independent work supports measurement caution on the enterprise suites: a CIDR 2026 analysis found a **66.1% annotation error rate** among the 121 Spider 2.0-Snow problems with open-sourced gold SQL.
	- **Monitorable signal**: the Beaver leaderboard is the series to track, not Spider/BIRD saturation. The question is whether unaided agentic systems climb out of the 10+% band toward the ~90% public numbers, or stall.

- ## Companion Post on the Same Page
	- **"Computing Can Help Fix Red Tape, but It Shouldn't Write the Rules"** — Vinay K. Chaudhri and Patrick A. McLaughlin, DOI 10.1145/3838734. Separate authors, same BLOG@CACM spread.
	- Argues regulatory accumulation is "a gigantic hidden tax" on the U.S. economy. Cites an influential estimate (co-written by one of the authors) that had federal regulation **remained at its 1980 level, the economy would have been nearly 25% larger by 2012** — equivalent to roughly **\$47,000 per household today**. The figure was informed by **QuantGov**, which analyzed millions of words of regulatory text.
	- Proposes AI, knowledge representation, and cryptographic infrastructure to make regulation "more easily understood, efficiently executed, and continuously improved," per a **CRA-I** (Computing Research Association Industry Committee) white paper — explicitly **supplementing, not replacing, human judgment**; "not a call for automated lawmaking," since decisions about risk, fairness, property, and innovation "are fundamentally human."

- ## Related Memos
	- [[2026-06-05-software-tollbooths-saas-pricing-bear-geninnov]] — agent access to enterprise data as a pricing layer
	- [[2026-06-12-agent-clearinghouse-thesis-source-of-permission]] — permission/metadata as the durable layer
	- [[2026-06-08-datadog-state-of-ai-engineering]] — enterprise AI adoption telemetry
	- [[2026-07-02-acm-big-memory-persistence-stock-memo]] — prior ACM extraction
