<h1>KAFKA BASICS</h1>

---

**Contents**:

- [Apache Kafka](#apache-kafka)

---

> **Necessary reading**: [*Kafka Introduction](./kafka-introduction.md)

# Apache Kafka
A distributed system of servers and clients...

... that communicate via high-performance TCP network protocol.

---

**Servers**:

- Kafka is run as a cluster (allocation of compute and memory) on 1 or more servers
- Some servers form the storage layer, called "brokers"

**NOTE**: *Kafka clusters are highly scalable and can be made highly fault-tolerant.*

**Clients**:

- Software components that read, write and/or processes event streams <br> **NOTE**: *Software components => Apps, microservices, etc.*
- There are a number of clients Kafka provides out-of-box
- Clients are available for Java, Scala, Go, Python, C, C++ and more
- Clients can also take and respond to requests using REST API