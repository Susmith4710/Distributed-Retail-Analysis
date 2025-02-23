# Distributed-Retail-Analysis
Architectured multi-datacenter Cassandra Cluster and implemented a real-time Kafka pipeline with materialized views.

Data Replication: The storage layer consists of Cassandra Nodes spread across geographically
distributed data centers. (Europe DC, America DC, Asia-Pacific DC)
Cassandra uses a replication factor, which essentially means every piece of data is duplicated on several nodes in a data center or across the data centers. This ensures that the data is always available and durable, even if some nodes or an entire data center goes down.
Data Partitioning: Cassandra uses partitioning strategies like consistent hashing to distribute data effectively across nodes. This ensures that related data is grouped together, optimizing queries while also balancing the load to avoid any potential bottlenecks.
Load Balancing: It uses Kafka to balance messages evenly across partitions as part of ingestion and Cassandra's token ring design for dynamic load balancing and redistribution of data across nodes.
Flow Example: Data coming from Kafka is partitioned by key and then consumed by the Data Pipeline, streaming to Cassandra.
Cassandra replicates data across all Europe DC, America DC, and Asia-Pacific DC according to the provided replication strategy.
Real-time monitoring via Prometheus and dashboards in Grafana track performance, ensuring proper load distribution and triggering alerts for imbalances.
This approach allows for scalable and fault-tolerant access to efficiently manage data in the global infrastructure.
