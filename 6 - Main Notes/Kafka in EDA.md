2025-09-14 10:52

Status:

Tags: [[Event Driven Architecture]]

# Kafka in EDA
### What is Apache Kafka
- It is a distributed steaming platform that serves as a backbone for building real-time data pipelines and streaming applications.
- Designed to handle high throughput, fault tolerant, and scalable event streaming.
- Built around the publish-subscribe model.
	- Producers publish messages (events) to topics, and consumers subscribe to those topics to receive and process the messages.
	- Events are stored in Kafka in an immutable and append-only manner, allowing both real-time and historical data processing.

### Key Concepts
- Topics
	- Channels for publishing and subscribing to events
- Producers
	- Services that produce and send events to Kafka topics.
- Consumers
	- Services that subscribe to topics and process incoming events
- Partitions
	- Each topic is divided into partitions, allowing for parallel processing and load distribution

### Role of Kafka in EDA
Plays a pivotal role by acting as a scalable and durable event bus for communication between microservices. Allows microservices to communicate asynchronously without direct dependencies on each other

- Event Broker
	- Kafka acts as a central event broker, serving as a highly scalable and reliable middleware to handle event streams. It efficiently manages the routing, storage, and distribution of events between various services.
- Event log
	- An append-only log-like storage allows events to be durably stored and retained for a configurable period.
	- An ideal source of truth for event sourcing, auditing, and data replay scenarios
- Decoupling services
	- Decouples services by enabling producers to publish events without needing to know which specific services will consume them. Similarly, consumers do not need to be aware of the producers generating the events.
- Reliability and Fault Tolerance
	- Provides strong guarantees of data durability and fault tolerance.
	- Events are replicated across multiple brokers

# References

