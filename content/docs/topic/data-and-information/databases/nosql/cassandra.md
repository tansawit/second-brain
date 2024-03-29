---
title: "Apache Cassandra"
---

# Apache Cassandra

Apache Cassandra is is a highly scalable, high-performance distributed database created by Facebook. It is designed to handle large amounts of data across multiple commodity server, allowing for high availability without single point of failure. 

## Features

- **Elastic scalability** - allows adding more hardware to accommodate more customers and more data as per requirement
- **Always-on architecture** - continuously available for business-critical applications due to no single-failure point
- **Fast linear-scale performance** - Increases throughout as you increase the number of nodes, thus maintaining a quick response time
- **Flexible data storage** - Accommodates structured, semi-structured, and unstructured data types, and can dynamically accommodate changes to data based on your need
- **Easy data-distribution*** - Distributes data where you need by replicating the data across multiple data centers
- **Transaction support*** - Supports properties like Cassandra supports properties like Atomicity, Consistency, Isolation, and Durability (ACID).
- **Fast writes** - Designed to run on cheap commodity hardware

## History

Cassandra was originally developed at Facebook for use with their inbox search. It was later open-sourced by the company in July 2008

## Architecture

The design goal of Cassandra is to handle big data workloads across multiple nodes without any single point of failure.

- All nodes in a cluster play the same role. Each node is independent and at the same time interconnected to other nodes.
- Each node in a cluster can accept read and write requests, regardless of where the data is actually located in the cluster.
- When a node goes down, read/write requests can be served from other nodes in the network

### Data Replication

One or more nodes in a cluster acts as replicas for a given piece of data. If a node ever responds with an out-of-date value, Cassandra will return the most recent value to the client while performing a read-repair in the background to update the incorrect value.

### Components

- **Nodes**: Where the data is stored
- **Data center**: A collection of related nodes
- **Cluster**: A component that contains one or more data centers
- **Commit log**: A crash-recovery mechanism. Every write operation is written to the commit log
- **Mem-table**: A memory-resident data structure. After commit-log, the data will be written to the mem-table.
- **SSTable**: A disk to which the data is flushed from the mem-table when its content reach a threshold valu 
- **Bloomer filter**: Quick, non-deterministic algorithms to test whether an element is a member of a set (a special kind of cache). Bloom accessed are accessed after every query

### Cassandra Query Language

Users access Cassandra through its nodes using the [Cassandra Query Language](http://cassandra.apache.org/doc/latest/cql/) (CQL). The language treats the database, or keyspace, as a container of tables. Developers use [cqlsh](http://cassandra.apache.org/doc/latest/tools/cqlsh.html) a prompt to work with CQL or separate application language drivers.

Clients approach any of the nodes, called the coordinator, for their read-write operations, which acts as a proxy between the client and the nodes holding the data.

#### Write Operations

Every node write activity is captured by the commit logs written in the nodes. The data is later captured and stored in the mem-tables. Whenever the mem-table is full, data will be written into the SStable data file. All writes are automatically partitioned and replicated throughout the cluster. Cassandra periodically consolidates the SSTables, discarding unnecessary data.

#### Read Operations

During read operations, Cassandra gets values from the mem-table and checks the bloom filter to find the appropriate SSTable that holds the required data.

### Data Model



