file-created-at:: 2026-03-28

### **Document Summary**

The provided report outlines an optimistic outlook for MongoDB (MDB) heading into 2026, emphasizing that AI has become a primary growth driver. According to feedback from various channel partners, MDB is experiencing an acceleration in AI-driven Atlas cloud migrations and significant growth in vector database usage. This growth is heavily supported by MDB's integration with VoyageAI, which has enhanced its vector search capabilities and positioned MDB as a preferred platform for AI-native workloads.

A major architectural shift highlighted in the report is the transition of Large Language Model (LLM) developers away from PostgreSQL. While PostgreSQL performs well for read-intensive tasks, it struggles with the write-intensive demands of AI agents that continuously process and generate new data. As a result, industry leaders are encountering performance bottlenecks and migrating to flexible-schema NoSQL databases.

**Customer Cases Mentioned**

**Insurance Sector Client:** This client was originally spending approximately $1M annually on MDB's Atlas and about $2M on Elastic for vector search. Because Elastic only covered around 2,000 vector dimensions while VoyageAI supports nearly 5,000, the client chose to consolidate their vector search into MDB. They also shifted their Pinecone and OpenAI embedding usage to MDB, and their total MDB spend is expected to exceed $4M within 6 to 12 months.

**Software Client:** This client previously spent $5M annually using MDB for basic storage. After deploying OpenAI to build an internal AI knowledge assistant, their vector search usage and metadata storage volume surged. Within three quarters, their total MDB consumption rose by 40%, requiring a tier upgrade, and their spend is projected to increase by 50-70% as the application's usage grows.

**Anthropic:** Anthropic was confirmed as a key MDB customer, validating NoSQL's architectural advantages over PostgreSQL for high-usage workloads. They use MDB for persistent data storage, including model context metadata and user conversation history. Following a recommendation from AWS to move away from object storage, Anthropic transitioned from AWS-hosted PostgreSQL and S3 Object Storage to MDB to utilize its combined object storage and VectorDB capabilities.

**OpenAI:** The report notes OpenAI published a post discussing changes to their single-primary-node PostgreSQL database architecture. To address performance challenges caused by the severe bottlenecks of write-intensive AI agent workflows, OpenAI is shifting these workloads to Azure Cosmos DB. While Cosmos DB is a direct competitor to MDB, the report notes this migration further validates the necessity of NoSQL architectures in the AI era.