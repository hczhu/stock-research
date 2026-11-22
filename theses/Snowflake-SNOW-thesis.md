tags:: [[$SNOW]], [[Snowflake]], [[data-warehouse]], [[lakehouse]], [[Iceberg]], [[Databricks]], [[Snowpark]], [[Cortex]], [[SQL]], [[AI]], [[SaaS]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-22
file-updated-at:: 2026-11-22

- **Company**: Snowflake (\$SNOW)
- **Date**: 2026-11-22. Converted from the owner's Google Doc ["Snowflake \$SNOW - Investment thesis"](https://docs.google.com/document/d/1cDN7k0QT72eQnVoUUW2tY4LaNf2ZWwuj9mDQhqpkkFg/edit).
- **Vintage**: most of the doc's evidence dates from **mid-2024** (customer and expert quotes, the UBS survey, earnings notes). The earnings sections labeled 2024Q1–Q3 are calendar 2024, Snowflake's **fiscal 2025** Q1–Q3.
	- For 2026 developments, see [[SNOW-2026-Q1]] and [[SNOW-2026-Q2]]. Those notes cover Snowflake's fiscal 2027 Q1 and Q2.
	- The generic research checklist and investing maxims are left out; they're in [[investment-thesis-template]].
  
  ---
- ## References
	- [Numbers spreadsheet](https://docs.google.com/spreadsheets/d/1IDxwB4HbwnnsgAgapuSO3yvdJDr3Z-5hVCS3QletOpM/edit?usp=sharing)
	- [Patents](https://patents.google.com/?assignee=Facebook%2c+Inc.). The doc's link still searches Facebook, Inc., carried over from the template.
	- [PDFs from .gov sites mentioning Snowflake](https://www.google.com/search?q=filetype%3APDF+site%3A.gov+snowflake)
	- [Chart source (Snowflake demos repo)](https://github.com/sfc-gh-skhara/skhara-demos/tree/main)
	  
	  ---
- ## Main Narrative
	- What the business will look like in 5–10 years, quality-wise.
	- | # | Narrative |
	  |---|---|
	  | 1 | **A long runway for analytics on structured data**, especially because AI can convert unstructured data into structured data |
	  | 2 | **A turnkey virtual data warehouse with a deep technological moat**. Snowflake owns ease of use |
	  | 3 | Snowflake (in management's words) "is often at the center of all of the interesting data in companies… We started out as a warehouse, but increasingly, we are the **data backplane** that provides a single unified view" |
	  | 4 | Management: "Our bet is really that AI and machine learning are going to go where the data is. **Data is going to have a strong gravity**" |
	  | 5 | **Pursue the mid-market in Europe, and APJ** (Asia-Pacific and Japan) |
	  
	  ---
- ## Napkin Math
	- Not yet filled in.
	  
	  ---
- ## Key Value Drivers Not Yet Priced In
	- | Driver | Notes |
	  |---|---|
	  | **Support open data-lake formats (Iceberg) and unlock 100× more data** | See the bullets below |
	  | **More business users can write SQL, build ETL pipelines or ML models with AI help** | Management: "We see a lot of usage on customers getting assistance on how to write better SQL queries, which also drives consumption back into Snowflake" |
	- **Iceberg as a value driver**:
		- **The size of the prize**: data lakes and cloud storage hold **100–200×** the data sitting inside Snowflake. With Iceberg support, Snowflake can run workloads directly on that data, and refined data can be mixed with operational data in the lake.
		- **Performance promise**: management said it shifted plans "to make sure that there are no trade-offs on performance. We will give customers that choose to use open file formats and open table formats, performance comparable to what they see with Snowflake internal tables."
		- **Microsoft OneLake**: Snowflake customers can store data in OneLake and query it in Snowflake through Iceberg. That could hurt Databricks, which is closely tied to Microsoft.
		- **The open question**: "which compute engine can perform best at scale on open data stacks – specifically via Iceberg – rather than on pre-processed data ingested into the data warehouse?" Snowflake is widely seen as the most performant data warehouse. It is far less obvious that it has an edge in Iceberg query performance.
		- **Skeptical voices**:
			- "For Iceberg Tables, Snowflake certainly wants you to think you will query more data in Snowflake using Iceberg since more of your data is exposed. I can't even tell if that will be the case because an enterprise doesn't know what kind of queries they could run yet if they had all their data available to them." The doc adds that Snowflake needs ML and AI capability to capture this.
			- "Regarding Snowflake, I don't buy that argument that there's more data to query therefore we'll grow quicker. There's always more data to query, that's generally true."
	  
	  ---
- ## Durable and Unfair Competitive Advantages
	- Not yet filled in. Narrative 2 (turnkey ease of use) is the doc's implicit answer.
	  
	  ---
- ## Competition
	- | Competitor | Advantages against this competitor (per the doc) |
	  |---|---|
	  | **Databricks** | Better SQL querying and better for non-IT users. Databricks is catching up on SQL and has a TCO edge as a unified platform. Details below |
	  | **AWS Redshift, Google BigQuery, Microsoft Synapse** | All rooted in traditional data-warehouse technology |
	- ### Databricks (2024-07)
		- "Databricks is coming from the data science world and is not as good as Snowflake in terms of SQL querying, although they're catching up."
		- "Databricks has always had problems with the non-IT departments where those individuals don't understand python and other things they need to interact with Databricks."
		- **Lost migrations**: "We've had 4 large customers who had plans to migrate their data from on-prem to Snowflake but they decided to land the data in open table formats on cheap storage environments in the cloud… They're basically lighter data warehouses. These four customers are using Databricks for processing work on the data. I haven't seen what SQL query engine they'll use on the data."
		- **Fujitsu's comparison**: "Databricks holds a competitive edge for TCO-sensitive organizations seeking a unified analytics platform that supports all their data, all their users and all their use cases."
	- ### AWS Redshift: how it is built
		- **PostgreSQL** foundation for SQL. PostgreSQL itself stores data in rows.
		- **Massively parallel processing (MPP)** on a distributed architecture.
		- **Columnar storage** for query performance.
		- **Redshift Spectrum** queries exabytes of data in S3 without loading it.
		- **Advanced compression** to reduce storage and speed up queries.
	  
	  ---
- ## Secular Trends
	- **On-prem data warehouses move to the cloud.** The doc asks whether this is already priced in.
	- **Data warehouse to lakehouse?**
	  
	  ---
- ## Innovative Culture
	- Not yet filled in.
	  
	  ---
- ## What Can Go Wrong?
	- ### Risk 1: Snowflake's lead in data warehousing erodes
		- Databricks and now Microsoft Fabric are building more modern **lakehouses** on open table formats.
		- **The trend** (2024-07): enterprises increasingly prefer to store all data types in open data lakes on AWS or Azure, and to process and query them using Iceberg or Delta Lake.
		- **When it started** (2024-07): this began in the second half of 2023, with more anecdotes of enterprises considering **Databricks SQL** as an alternative to Snowflake for data-warehouse jobs.
		- **Cost pressure**: "If we are using Snowflake to query from Iceberg, we're using more compute because it's slower, so we pay more to Snowflake… if Iceberg is performing well with Athena or Databricks, companies will move there as they want to cut down the cost."
		- **Lost loading revenue**: "if you load data within Snowflake… there's compute that gets burnt to convert that data into Snowflake's proprietary format. If I don't even load it… all that loading, the L goes away… that's lost compute revs… Now that it's sitting in open table formats, you have competition from Databricks SQL on it."
		- **Two strategies at the conferences**: "Snowflake is saying still load all your data into Snowflake, and then export it to Iceberg… They're pushing to stay in the middle with customers. I went to Databricks conference the week after. Databricks is saying don't do this. Don't give us your data. Keep it in open table formats and let the best query engine win. Databricks is pushing Iceberg hard."
		- **A counterpoint on governance**: "It sounds good that you can use open tables but who's going to track data lineage, how is my security going to work, how is sharing going to work? I recommend sticking to the native format at this time."
	- ### Risk 2: open data formats eat Snowflake's storage business
		- **Which formats matter**: only **Delta** and **Iceberg** can centralize data, upgrading a data lake to data-warehouse performance. Hive and Hudi are "not technologically there." The difference between Delta and Iceberg is mainly about open source.
		- **The exposure**: Snowflake put storage at **10–11% of revenue**, about **\$375–400M** in CY24 / FY25. If customers using Iceberg tables no longer store data in Snowflake, this revenue declines.
			- "One of our top 3 customers, a well-known technology company, is already not paying us for storage today."
		- **The offset**: compute, not storage, is where Snowflake makes money.
			- "Our Snowflake bill could definitely go up as we have more data to query because of how Snowflake charges. Storage is very tiny. They make the money from the compute engine."
			- "We pay Snowflake the exact same amount as we do on AWS for a terabyte of data. They honor our pricing."
	  
	  ---
- ## People
	- Executives' ability to execute and adapt, and shareholder friendliness: not yet filled in.
	- **Employees** (Glassdoor and Blind, 2024-08):
		- Like the previous quarter, employees say customers love the product, with some angst about new leadership and execution.
		- "The product is very good and customers are enthusiastic about it."
		- "Our strategy is vague and uninspired and tends to be secondary to just shipping something every quarter. Feels like we're absorbing the worst of Google and Microsoft culture."
		- "New CEO making a lot of changes for the worse, messed up tech stack trying to be Google crammed into a database that's now AI."
	  
	  ---
- ## Are Customers and Users Happy?
	- **Snowpark is not plain Python** (2024-08): a user found that Snowpark doesn't run plain Python or pandas but needs its own syntax, which in some cases is "much more cumbersome than python/pandas/pyspark." Notebooks also lag Databricks' Jupyter-style notebooks, which allow multiple queries per page, different languages in different blocks, and shared variables across blocks.
	- **A customer moving to an open data lake** (2024-07):
		- **The setup**: its data platform is almost entirely on AWS. It uses Llama 2 but not yet Bedrock, and is moving to an **open data lake**.
		- **The problem**: "We built our data lake and then found we're replicating all the data from our data lake into Snowflake, why are we doing this?"
		- **The plan**: it is pushing Snowflake to run queries on Iceberg directly on the lake, to cut costs and improve performance. That would reduce what it pays Snowflake for storage. The customer added that Snowflake makes more margin on compute anyway, and "you could see customers end up using MORE compute" with Iceberg.
		- **The verdict**: Snowflake is "a great relational database" and is building ML. Users love its interface. "We'll continue to use Snowflake for this, Databricks for that." The same customer is quoted by Fujitsu in the Snowflake vs. Databricks comparison.
	- **Iceberg performance** (2024-07):
		- On Iceberg tables in S3, Snowflake "is still very good." Iceberg is about **5× faster than an external table**, but native Snowflake is faster still, because it organizes data into micro-partitions (for 1GB of data, 50MB chunks) and knows where the data is, making it about 20× faster.
		- An Iceberg table with 10 monthly partitions still has to scan those S3 files. "For a medium workload, you can use Iceberg, but if you have a heavy workload, it's better to use Snowflake."
		- Snowflake's engine performs much better on **managed** Iceberg tables than on **open** ones.
	  
	  ---
- ## Appendix: Earnings Notes (calendar 2024)
	- ### 2024Q3 (fiscal Q3 2025)
		- **Products**:
			- **Snowpark** is on track for about **3% of revenue**.
			- More than **3,200 accounts** use Snowflake's AI and ML features.
			- **Unistore** is generally available.
			- **Snowflake Intelligence**, a platform for building data agents, was introduced.
		- **Iceberg**: about **500 accounts** have adopted Iceberg, and storage remains **11%** of consumption. Management has seen "minimal headwinds" from customers moving to Iceberg, and some customers are bringing **new workloads** to Snowflake on Iceberg tables.
		- **Markets**:
			- The focus has been the high end of the market. Snowflake will now push into the **mid-market in Europe**.
			- In APJ, growth is strong in **Japan**, with early activity in India and Korea. Australia has always done well, and New Zealand is small but strong.
	- ### 2024Q2 (fiscal Q2 2025)
		- **Security**: after multiple investigations by internal and external cybersecurity experts, Snowflake found **no evidence that its platform was breached** or compromised.
		- **Products and adoption**:
			- **Snowpark**: the only newer product in the fiscal 2025 guide, at about **3% of revenue (\$100M)**, and tracking to that.
			- **Notebooks**: more than **1,600 accounts** in public preview.
			- **Iceberg**: more than **400 accounts** at quarter end.
			- **Snowflake AI**: more than **2,500 accounts** using it weekly.
		- **Customers**:
			- Snowflake Summit had **15,000 attendees** on site, up 28% YoY. The doc says "SMBs," likely a typo. The first-ever Developers Day drew more than 3,000.
			- The new customer-acquisition motion is ramping and should matter more in fiscal 2026.
		- **Financials**:
			- **Storage** still runs about **11% of revenue**. Snowflake hasn't seen storage leave yet; it always forecast some would leave in the second half, and that is in guidance.
			- **Two nine-figure deals** signed in the quarter.
			- **80% of customers pay annually in advance.**
			- The gap between revenue and RPO "continues to be one of the highest we've seen."
	- ### 2024Q1 (fiscal Q1 2025)
		- **Margins**: full-year margin guidance was **lowered** because of higher **GPU costs** for AI initiatives.
		- **AI and Iceberg**:
			- More than **750 customers** are developing on the AI platform.
			- Management called Iceberg support "an exciting new chapter for all players in data."
		- **Unistore**: GA later in the year, for transactional rather than analytical workloads. Close to **300 customers** actively use **Hybrid Tables**.
		- **Customers**:
			- A **\$100M** deal was signed with a customer that pays monthly, and another \$100M deal is possible. Both are for core data warehousing.
			- Financial services remains the largest vertical.
		- **Storage**: a stable **11%** of revenue.
	- **Events and proxy statements**: not yet filled in.
	  
	  ---
- ## Appendix: Data Points & Facts
	- **OpenAI data processing**: Snowflake is listed as a subprocessor of OpenAI customer data for **data warehousing**, in the United States. Covered services: the API (except zero-retention data), ChatGPT Enterprise, ChatGPT Edu and ChatGPT Business.
	- **UBS customer survey (2024-07)**:
		- UBS found early evidence of a shift in data analytics toward storing all data types in **open data lakes on AWS or Azure**, using Iceberg or Delta Lake to process and query them.
		- UBS concludes that this shift (querying data directly in a lake, with no need to copy, migrate or store it in Snowflake) "is not a prospective change but is already well underway and will take years to fully play out." Even by Snowflake's admission, it "levels the playing field," which is "often bad for incumbents and good for disruptors."
	  
	  ---
- ## Appendix: Anecdotes & Opinions
	- **A tech fund on 2024Q2 earnings**:
		- **RPO is misleading**: "big customers sign big, multi-year deals to lock-in price… don't confuse stronger growth in RPO vs the slowing growth in actual usage of the platform."
		- **Deferred revenue**: current deferred revenue shrank **4.5% QoQ** and grew only **21.4% YoY**. With 80% of customers prepaying annually but gradually moving to paying monthly in arrears, as with most cloud infrastructure providers, the fund expects "a material headwind to FCF."
		- **New products**: field work suggests they are "flimsy and will not move the needle." The biggest "success," Snowpark, gets poor reviews and is still only about 3% of revenue.
	- **A Databricks perspective on Snowpark (2024-08)**:
		- Some ad-tech and finance customers (VideoAmp, CTC and others) first landed in Snowflake 5–6 years ago, when Databricks' SQL lagged and it had no marketplace. Their flow was Snowflake, then pyspark ETL and light ML in Databricks, then back to Snowflake for BI.
		- With **Snowpark**, they replace the pyspark ETL with Snowpark ETL. For them, cost and performance are **better** without the round trips.
	  
	  ---
- ## Related in the Repo
	- **Recent earnings**: [[SNOW-2026-Q1]], [[SNOW-2026-Q2]].
	- **The lakehouse and Databricks**:
		- [[2026-07-18-databricks-lakebase-ltap-database-from-storage-up]]
		- [[2026-11-15-palantir-user-experiences-databricks-compute-layer]]
		- [[2026-06-19-ubs-tokenmaxxing-software-call-palantir-databricks]]
	- **Analytics engines on object storage**: [[2026-11-13-data-warehouses-on-object-stores-anyblob-umbra]], [[2026-03-28-analytics-databases-performance-tiers-serving-laptop-clustered-very-big]].
	- **AI writing SQL**: [[2026-10-15-text-to-sql-benchmarks-spider-bird-enterprise-gap]].
