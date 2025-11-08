<h1>KAFKA BASICS</h1>

---

**Contents**:

- [Apache Kafka](#apache-kafka)
- [Concepts](#concepts)
  - [Servers](#servers)
  - [Clients](#clients)
  - [Event](#event)
  - [Producer and consumer](#producer-and-consumer)
  - [Topics](#topics)

---

> **Necessary reading**: [*Kafka Introduction](./kafka-introduction.md)

# Apache Kafka
A distributed system of servers and clients...

... that communicate via high-performance TCP network protocol.

# Concepts
## Servers
- Kafka is run as a cluster (allocation of compute and memory) on 1 or more servers
- Some servers form the storage layer, called "brokers"

**NOTE**: *Kafka clusters are highly scalable and can be made highly fault-tolerant.*

## Clients
- Software components that read, write and/or processes event streams <br> **NOTE**: *Software components => Apps, microservices, etc.*
- There are a number of clients Kafka provides out-of-box
- Clients are available for Java, Scala, Go, Python, C, C++ and more
- Clients can also take and respond to requests using REST API

## Event
*Also called "message" or "record.*

A log entry of an action/transaction consisting of the following fields:

- Key
- Value
- Timestamp
- Optional metadata

## Producer and consumer
**Producer**:

Client app that publishes (writes) events to Kafka.

**Consumer**:

Client app that subscribes to (reads and processes) events written to Kafka.

---

Key points:

- In Kafka, producers and consumers are fully decoupled and agnostic of each other
- Kafka also provides guarantees, e.g. ability to process events exactly once

## Topics
*See ["Topic", *Kafka Introduction*](./kafka-introduction.md#topic)*

Ordered collection of events stored durably.

---

Key points:

- Events are organised and durably stored in topics <br> **Analogy**: <br> Topic -> Directory <br> Event -> File
- Topics are always multi-producer and multi-consumer <br> **NOTE**: *Multi => 0 or more*
- Events in topics are not deleted after consumption <br> **NOTE**: *This is unlike traditional messaging systems*
    - Hence, events in a topic can be read as often as needed
    - You can define how long Kafka should retain events before discarding them <br> *This is a topic-wise configuration*
- Distributed placement of topic data:
    - Topics are partitioned => spread over a number of buckets on different brokers
    - Distributed placement of data is key to scalability
    - Events of the same key are written to the same topic partition
    - Kafka guarantees consumers of topic partitions always read their events in their write-order
- Replication of topics:
    - Every topic can be replicated to make data fault-tolerant and highly available <br> *Even across geo-centres and datacentres*
    - Replication is performed at the level of topic partitions