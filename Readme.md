# Apache Kafka

Apache Kafka is an open-source distributed event streaming platform used for building real-time data pipelines and streaming applications. It was originally developed by LinkedIn and later open-sourced as an Apache project.

## Table of Contents

1. [Introduction](#introduction)
2. [Key Concepts](#key-concepts)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Producers and Consumers](#producers-and-consumers)
6. [Topics](#topics)
7. [Brokers](#brokers)
8. [Zookeeper](#zookeeper)
9. [Scaling](#scaling)
10. [Monitoring](#monitoring)
11. [Security](#security)
12. [Resources](#resources)

## Introduction

Apache Kafka is designed to handle real-time data streams efficiently. It provides a high-throughput, fault-tolerant, and scalable platform for ingesting, storing, processing, and distributing data. Kafka is widely used in various industries for use cases such as log aggregation, event sourcing, stream processing, and more.

## Key Concepts

### 1. Topics

- Topics are logical channels for publishing and subscribing to data streams in Kafka.
- Data is organized into topics, and each topic can have multiple producers and consumers.

### 2. Producers

- Producers are responsible for publishing data to Kafka topics.
- They push data to specific topics, which is then made available for consumption.

### 3. Consumers

- Consumers subscribe to one or more topics and process the data published to those topics.
- Kafka allows both single and consumer groups for scalability.

### 4. Brokers

- Kafka brokers are the servers that store data, handle client requests, and manage the distribution of data across topics.

### 5. Partitions

- Topics can be divided into partitions to distribute data and allow parallel processing.
- Each partition is stored on a broker and replicated for fault tolerance.

### 6. Zookeeper

- Zookeeper is used for managing Kafka cluster metadata and leader election.
- Kafka 2.8+ versions no longer require Zookeeper for cluster coordination.

## Installation

[Official Kafka Downloads](https://kafka.apache.org/downloads)

Follow the installation instructions provided for your operating system.

## Usage

1. **Start Zookeeper (For Kafka versions prior to 2.8):**

   ```shell
   bin/zookeeper-server-start.sh config/zookeeper.properties
   ```

2. **Start Kafka:**

   ```shell
   bin/kafka-server-start.sh config/server.properties
   ```

3. **Create a Topic:**

   ```shell
   bin/kafka-topics.sh --create --topic my-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 2
   ```

4. **Produce Messages:**

   ```shell
   bin/kafka-console-producer.sh --topic my-topic --bootstrap-server localhost:9092
   ```

5. **Consume Messages:**
   ```shell
   bin/kafka-console-consumer.sh --topic my-topic --bootstrap-server localhost:9092 --from-beginning
   ```

## Producers and Consumers

Producers and consumers can be implemented using various programming languages. Kafka provides client libraries for Java, Python, Go, and more.

## Topics

Topics represent different data streams. You can create, manage, and configure topics to suit your data processing needs.

## Brokers

Brokers are the Kafka server instances. They store and serve the data, manage partitions, and communicate with producers and consumers.

## Zookeeper

Zookeeper is used for managing Kafka cluster metadata and leader election. Note that Kafka 2.8+ versions no longer require Zookeeper for cluster coordination.

## Scaling

Kafka is designed to scale horizontally. You can add more brokers, partitions, and consumers to handle increasing data loads.

## Monitoring

Kafka provides various tools and metrics for monitoring the health and performance of your Kafka cluster. You can use tools like Kafka Manager and Prometheus for monitoring.

## Security

Kafka supports security features like SSL/TLS encryption, authentication, and authorization to protect your data.

## Resources

- [Official Kafka Documentation](https://kafka.apache.org/documentation/)
- [Confluent Platform](https://www.confluent.io/): Offers additional tools and support for Kafka.
- [Kafka Tutorials](https://www.confluent.io/resources/kafka-tutorials/): Hands-on tutorials for various Kafka use cases.
