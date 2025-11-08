<h1>KAFKA INTRODUCTION</h1>

---

**Contents**:

- [Preliminary ideas](#preliminary-ideas)
  - [Database vs. logs](#database-vs-logs)
  - [Topic](#topic)
  - [Event streaming](#event-streaming)
- [What is Apache Kafka?](#what-is-apache-kafka)
- [Connectors and Kafka Connect](#connectors-and-kafka-connect)
- [Kafka Stream](#kafka-stream)

---

**References**:

- [*Introduction*, **kafka.apache.org/intro**](https://kafka.apache.org/intro)
- [*Apache Kafka Quickstart*, **kafka.apache.org/quickstart**](https://kafka.apache.org/quickstart)
- [*What is Apache Kafka?* by The ASF, **youtube.com**](https://www.youtube.com/watch?v=vHbvbwSEYGo)
- [*Kafka Connect*, **docs.confluent.io**](https://docs.confluent.io/platform/current/connect/index.html)

# Preliminary ideas
## Database vs. logs
We have the following paradigms:

- Store states of things => Database
- Store states of events => Logs

## Topic
Ordered collection of events stored durably.

=> Topics help manage logs.

Topics as an architecture are highly scalable and de-scalable.

## Event streaming
Practice of capturing data in real-time from "event sources"...

- in the form of ordered collections of events, i.e. "event streams"
- storing these event streams durably (for later retrieval)
- manipulating, processing and/or reacting event streams <br> *Either real-time or retrospectively*
- routing event streams to different destination technologies as needed

In short:

```
Event sources
   |
(events)
   |
   v
Event streams
   |
(topics)
   |
   v
Manipulating, processing, reacting + routing
```

# What is Apache Kafka?
An event streaming platform.

Key ideas that help define Kafka:

- Events
- Topics
- Independent services
- Real-time communication and processing

In other terms, Apache is a platform that enables:

*Persistent distributed logs with asynchronous communication and computation.*

# Connectors and Kafka Connect
**Kafka Connect**:

Tool for scalably and reliably streaming data between Apache Kafka and other data systems.

**NOTE**: *Other data systems can be databases, application servers, etc.*

**Connectors**:

Pluggable modules to perform read-write operations between systems/sub-systems.

---

Key points:

- Kafka Connect and connectors can be configured declaratively
- Connectors are created and managed by the Kafka Connect process
- Configuration for the Kafka Connect process contains:
    - Common configuration, e.g.:
        - Kafka brokers to connect to
        - Serialisation format for data
    - Other configuration files each specifying a connector to create <br> **NOTE**: *These files contain*...
        - Unique connector name
        - Connector class to instantiate
        - Any other configuration required by the connector

# Kafka Stream
A Java API that handles all framework and infrastructure to facilitate building services.

=> It is framework code for building services in Kafka.