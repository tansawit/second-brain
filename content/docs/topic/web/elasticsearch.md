---
title: "Elastic Search"
---

# Elasticsearch

Elasticsearch is a distributed, JSON-based, and RESTful search and analytics engine.

## Notes

### Query and Analysis

It allows you to perform and combine many types of searches (structured, unstructured, geo, metric) any way you want. Its aggregation feature also allows you to explore trends and pattern in your data.

### Implementation

Elasticsearch is implemented using

- inverted indices with finite state transducers for full-text querying
- BKD trees for storing numeric/geo data
- column store for analytics

### Scalability

Elasticseh can be set to run anywhere from laptops to large servers. The user talk to an instance running on a single node the same way they would with a large node-cluster. It scales horizontally and automatically manage how indices and queries are distributed across the cluster for smooth operations.

### Relevance

Search results can be set based on a variety of factors (term frequency, recency, popularity, etc.). It can also handle 'human errors' such as typos.

### Resiliency

Elasticsearch detects failures to keep data and cluster safe and available. Cross-cluster replication means a second cluster can be used as a hot backup.

### Features

- Security
- Monitoring
- Alerting
- Elasticsearch SQL
- Time Series Data Management
- Machine Learning

### Use Cases

- Logs
- Infrastructure
- APM
- Uptime
- Maps
- SIEM
- Site Search
- App Search
- Enterprise Search

## References

- [Elastic Site](https://www.elastic.co/)
