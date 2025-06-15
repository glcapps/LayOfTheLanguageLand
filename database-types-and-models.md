# 🗃️ Database Types and Models

Understanding the variety of database models helps in choosing the right tool for the problem at hand. While all databases aim to persist and retrieve structured data, they differ in their underlying models and trade-offs.

---

## 🔑 Key-Value Stores

- **Examples**: Redis, DynamoDB, RocksDB
- **Model**: Simple map of key ➝ value
- **Strengths**: Blazing fast lookup, great for caching and ephemeral state
- **Limitations**: No structured querying or joins

---

## 📄 Document Stores

- **Examples**: MongoDB, CouchDB, Firestore
- **Model**: JSON-like documents indexed by keys, schema-flexible
- **Strengths**: Nested data, easy to evolve schema, good for loosely structured data
- **Limitations**: Querying inside deep structures can be inefficient; limited joins

---

## 📊 Relational Databases (RDBMS)

- **Examples**: PostgreSQL, MySQL, Oracle, SQL Server
- **Model**: Tables with typed columns, rows, foreign keys, constraints
- **Strengths**: ACID guarantees, complex joins, mature ecosystem, transactional logic
- **Limitations**: Schema rigidity, performance tradeoffs for high-write distributed use

---

## 🧩 Wide-Column Stores

- **Examples**: Cassandra, HBase, ScyllaDB
- **Model**: Rows with variable-length columns grouped into column families
- **Strengths**: Scales horizontally, good for sparse or time-series data
- **Limitations**: Write-optimized; less expressive than RDBMS

---

## 🕸️ Graph Databases

- **Examples**: Neo4j, ArangoDB, JanusGraph
- **Model**: Nodes and edges, often with properties
- **Strengths**: Natural for relationship-heavy data (social networks, permissions)
- **Limitations**: Specialized query languages (Cypher, Gremlin); niche optimizations

---

## ⏱️ Time-Series Databases

- **Examples**: InfluxDB, TimescaleDB, Prometheus
- **Model**: Optimized for timestamped events
- **Strengths**: Fast aggregations, retention policies, compression
- **Limitations**: Limited general-purpose querying

---

## 📚 Columnar Databases

- **Examples**: ClickHouse, Apache Parquet, Amazon Redshift
- **Model**: Data stored by column instead of row
- **Strengths**: High compression, fast analytical queries across columns, ideal for OLAP workloads
- **Limitations**: Less suited for frequent row-wise updates or transactional use

---

## 🔎 Search Engines (Semi-Structured)

- **Examples**: Elasticsearch, OpenSearch, Solr
- **Model**: Index-based document stores with full-text search capabilities
- **Strengths**: Fuzzy text matching, analytics, distributed querying
- **Limitations**: Not meant for transactional storage; eventual consistency

---

## 🔄 Multimodel Databases

- **Examples**: ArangoDB, OrientDB, PostgreSQL (with JSON, XML, Graph extensions)
- **Model**: Support multiple paradigms within a single engine
- **Strengths**: Flexibility, polyglot modeling in one place
- **Limitations**: Mixed performance, steeper learning curve

---

## 🧠 When to Choose What

| Model           | Best For                          |
|----------------|------------------------------------|
| Key-Value       | Caching, session data             |
| Document        | APIs, content management, logs    |
| Relational      | Business data, reporting, finance |
| Columnar        | Analytics, dashboards, OLAP       |
| Graph           | Networks, fraud detection         |
| Time-Series     | Monitoring, metrics, telemetry    |
| Search Engine   | Logs, search bars, discovery UX   |

No one model rules them all — understanding these shapes your system’s performance, queryability, and evolvability.