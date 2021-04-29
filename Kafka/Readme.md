# Apache Kafka

- A messaging system
- A distributed streaming platform

## Who's Who

### Topic
Data is stored in **topics**. The topic is the most important abstraction provided by Kafka: it is a category or feed name to which data is published by producers. Data in topic can stay for specific time, by default its 1 week.

### Producer
**Producers** publish data to topics. It automatically knows which partition to write data to. 
Acknowledgement of data write to Producer are of 3 types:
	- acks=0 : Producer wont wait for ack.
	- acks=1 : Producer waits for leader to ack
	- acks=2 : Producer waits for leader and all replicas to ack  
Producer can choose to send key with a message. If key not sent producer round robins the messages over the brokers to distribute the load.

### key
A message key is the identifier for the messages.
For eg : In a truck management eventing system a truckId will be the key.
If the key is sent with the message, the msg goes to specific broker, specific partition.

### Consumer
**Consumers** read published data from Kafka topic partition.
It can read from single partition or multiple partitions. The read order within a single partition is always maintained.

### Broker
- Producers and consumers are totally decoupled, and both run outside the Kafka **brokers** in the perimeter of a Kafka cluster. A broker contains certain topic partitions. **Brokers** are generally 3 in a cluster.
It is also called boot strap server. Every broker has all the information of other brokers, like which partition is handled by which broker.
Any client connects to any broker in the cluster & gets details of all other brokers. Then the client connects to specific broker.

### Cluster
- A Kafka **cluster** consists of one or more brokers.

### Streams
- An application that uses the Kafka **Streams** API acts as both a producer and a consumer. The Streams API allows an application to act as a stream processor, consuming an input stream from one or more topics and producing an output stream to one or more output topics, effectively transforming the input streams to output streams.

### Connector
- The **Connector** API allows building and running reusable producers or consumers that connect Kafka topics to existing applications or data systems. For example, a connector to a relational database might capture every change to a table.

### Partitions
-A topic has multiple partitions. For HA, slave partition lies on multiple brokers, depending on the replication factor. There is 1 master partition and rest are ISR (In sync replicas)
- Every topic in Kafka is split into one or more **partitions**. Kafka partitions data for storing, transporting, and replicating it. Kafka Streams partitions data for processing it. In both cases, this partitioning enables elasticity, scalability, high performance, and fault tolerance. The messages are ordered in a particulat partition, but this can be said for different partitions. For eg Msg1 in Partition 0 will be before Msg2 in Partition 0. But Msg 1 in Partition 0 might be/not before Msg 0 in Partition 1. 

### Offset
- The only metadata retained on a per-consumer basis is the **offset** or position of that consumer in the log. This offset is controlled by the consumer: normally a consumer will advance its offset linearly as it reads records, but, in fact, since the position is controlled by the consumer it can consume records in any order it likes.

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/Consumer_Offset.PNG)
### consumer group
-Consumers label themselves with a consumer **group** name, and each record published to a topic is delivered to one consumer instance within each subscribing consumer group. 
If all the consumer instances have the same consumer group, then the records will effectively be load balanced over the consumer instances. 
If all the consumer instances have different consumer groups, then each record will be broadcast to all the consumer processes.

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/ConsumerGroup.PNG)

### Message Key
- A message has an optional parameter **Message Key**, if this is provided with the message, its guaranteed that message will be reaching same partition, if partition not mentioned.

### Zookeeper
- **Zookeeper** manages brokers. Kafka cant work without zookeeper. It helps in performing leader election for a partition. It always wants odd number of brokers. Kafka writes metadata into zeekeeper.
Zookeeper has leader and followers, in its cluster.

## Install and run kafka

Download binary from : https://kafka.apache.org/downloads
 kafka ui tool: http://www.kafkatool.com/

run below commands for windows 
1) To start the zookeeper
`zookeeper-server-start.sh config\zookeeper.properties`

2) To start kafka broker
`kafka-server-start.bat config\server.properties`

3) To create topic:
`kafka-topics.bat --create --topic my_topic1 --zookeeper localhost:2181 --replication-factor 1 --partitions 1`

4) To list the topics created: 
`kafka-topics.bat --list --zookeeper localhost:2181`

5) To start a producer:
`kafka-console-producer.bat --broker-list localhost:9092 --topic my_topic1`

6) TO start the consumer:
`kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my_topic1 --from-beginning`
with from-beginning flag we state that consumer has to consume from beginning, if we dont give this flag, consumer will consume messages that are produced after the consumer has started.
To start a consumer for a group add `--group <groupName>`

7) To get information about a topic
`kafka-topics.bat --describe --topic my_topic1 --zookeeper localhost:2181`
Result:
![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/TopicDescribe_0Partition_0Replica.PNG)


## To see fault tolerant
1) run 3 brokers:
`.\bin\windows\kafka-server-start.bat .\config\server-0.properties`

`.\bin\windows\kafka-server-start.bat .\config\server-1.properties`

`.\bin\windows\kafka-server-start.bat .\config\server-2.properties`

In every sever.properties just change the `broker.id`, `listeners`, `log.dirs`

Now we create a topic with replication factor 3
`.\bin\windows\kafka-topics.sh --create --topic my_replication_topic1 --zookeeper localhost:2181 --replication-factor 3 --partitions 1`

Now if we execute the describe command: 

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/TopicDescribe_0Partition_3Replica_AllBrokersUp.PNG)

Now we kill the leader that is broker 2, after this the describe command result:

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/TopicDescribe_0Partition_3Replica.PNG)

So now the leader changed and the isr (in sync replicas) reduced 

- Producer logs:

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/ProducerWhenLeaderBrokerKilled.PNG)

It got disconnected with leader broker 2 and got connected with the new leader broker.

Same happens with consumer:

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/ConsumerWhenLeaderBrokerKilled.PNG)

but it didnt loose any msg from producer.


## Description
Kafka is based on topics.
Each topic is further divided into partitions.
A topic with 1 partition can be distributed over multiple brokers.
But a topic with multiple partition, every partition is managed by a broker. Broker has replica sets.

## How is Kafka Distributed
As Kafka is based on topics. Topic has partitions. Every partititon runs on a separate broker. 
When we send message on topic, suppose with 3 partitions, the load on the topic is distributed over 3 partitions. 


![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/TopicDistributedIntoPartitions.PNG)

A producer sends message to a topic. The load is distributed over multiple partitions. The distribution happens depending on the scheme selected. One of the scheme is round robin.
Consumer/s subscribes to the topic and gets the messages from different partitions.

When we create a topic with multiple partitions, zookeeper checks the cluster available and assigns a partition to a broker in the cluster. Every partition has a leader broker. 
If that broker goes down, zookeeper helps in electing the next leader for that partition. Along with zookeeper, every broker has the metadata of the partitions managed by the brokers.
Brokers keep on sharing their status with the zookeeper.

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/TopicCreationManagedByZookeeper.PNG)

When a producer wants to connect to a topic, it should have knowledge of atleast one broker. on connecting to a broker, producer gets the metadata of the partitions managed by the brokers. After that producer starts sending the message to the respective broker of the partition.
Same goes with consumer.

## How is Kafka fault tolerant : Replication

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/BrokerWithReplicas.PNG)

Every broker has replica sets which provides fault tolerant.

## How Kafka indentifies the partition of the topic

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/ProducerIdentifyingPartitionStrategy.PNG)


## Sample Java code of kafka producer consumer

https://github.com/himkak/KafkaProducerConsumer

https://github.com/himkak/TwitterTweetConsumer

# Architectures based on Kafka

## CQRS
Command Query Responsibility Segregation
Its about separating commands from queries. Separate the interfaces for reads and writes.

## Event Sourcing
We can query an application's state to find out the current state of the world, and this answers many questions. However there are times when we don't just want to see where we are, we also want to know how we got there.

Event Sourcing ensures that all changes to application state are stored as a sequence of events. Not just can we query these events, we can also use the event log to reconstruct past states, and as a foundation to automatically adjust the state to cope with retroactive changes.

The fundamental idea of Event Sourcing is that of ensuring every change to the state of an application is captured in an event object, and that these event objects are themselves stored in the sequence they were applied for the same lifetime as the application state itself.


## Saga Design Pattern

## Event Driven Architecture
Every thing evolves around events and not data.


# Kafka Connect
Processing data events one by one.
![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/KafkaConnect_UseCases.PNG)

Kafka connect are already written code (producer/consumer), which can be used to transfer data.

## Sample Twitter Connect

Download tar.gz : https://github.com/jcustenborder/kafka-connect-twitter/releases
Extract the jars
copy the connect-standalone.properties from kafka config directory
Leave all the configurations to default. Except one, set the `plugin.path=<path of jars>` 
create a twitter.properties file.
Create a topic : twitter_status_connect `kafka-topics.sh --create --topic twitter_status_connect --zookeeper localhost:2181 --replication-factor 1 --partitions 1`
Create another topic: twitter_delete_connect `kafka-topics.sh --create --topic twitter_delete_connect --zookeeper localhost:2181 --replication-factor 1 --partitions 1`
Run the command : `connect-standalone.bat" connect-standalone.properties`
Start a consumer on the topic twitter_status_connect, and we will be able to see the tweets as events

Sample: https://github.com/himkak/SampleKafkaTwitterConnect

# Kafka Streams
Used to consume and process the data.
TO transform the data.

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/kafkaStream.PNG)

## usage
Create a java maven project

add the kafka streams dependency
set the stream configuartion

Sample code  
https://github.com/himkak/KafkaStreamsFilterTweets

# Schema Registry

Used to validate the messages produced by producer or consumed by consumer against a contract, which is published in schema registry.
The supported format is Apache Avro.

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/SchemaRegistryNeed.PNG)

![IMAGE](https://github.com/himkak/notes/blob/master/Kafka/KafkaWithSchemaRegistry.PNG)

# AVRO
Avro is a row-oriented remote procedure call and data serialization framework developed within Apache's Hadoop project. It uses JSON for defining data types and protocols, and serializes data in a compact binary format.


# References

- https://www.youtube.com/playlist?list=PLa7VYi0yPIH0KbnJQcMv5N9iW8HkZHztH : overview of kafka (good)
- Kafka getting started: https://kafka.apache.org/documentation.html#gettingStarted
- Kafka tutorial oreilly : https://learning.oreilly.com/videos/apache-kafka-series/9781789342604
- Kafka tutorial pluralsight: https://app.pluralsight.com/library/courses/apache-kafka-getting-started
- CQRS : https://martinfowler.com/bliki/CQRS.html

- https://medium.com/javarevisited/top-10-apache-kafka-online-training-courses-and-certifications-621f3c13b38c : Top 10 Apache Kafka Online Training Courses and Certifications

- https://kafka.apache.org/11/documentation/streams/architecture : KAFKA STREAMS Architecture

- https://www.confluent.io/blog/apache-kafka-intro-how-kafka-works/

- https://www.youtube.com/playlist?list=PLa7VYi0yPIH0KbnJQcMv5N9iW8HkZHztH : Kafka tutorial for beginners, by Confluent