---
layout: page
title:  "Publisher/Subscriber Messaging"
mathjax: true
---

{% include head/custom.html %}


This is a very popular paradigm (model) for messaging. The key concept is that publishers 'publish' a message and a subscriber subscribes to messages.  To give greater granularity, messages can belong to a certain "topic" which is like a category.  These topics are like dedicated "channels" or pipes, where each pipe exclusives handles messages belonging to a specific topic.  Subscribers choose which topic they want to subscribe to and get notified of messages in that topic.  The advantage of this system is that the publisher and the subscriber can be completely de-coupled - i.e. they don't need to know about each other.  The publisher announces, and the subscriber listens for announcements for topics that it is on the lookout for.

A server is often the publisher of messages and there are usually several topics (channels) that gets published to.  The consumer of a specific topic subscribes to those topics. There is no direct communication between the server (publisher) and the subscriber (could be another server). The only interaction is between publisher and topic, and topic and subscriber.

The messages in the topic are just data that needs to be communicated, and can take on whatever forms you need. So that gives you four players in Pub/Sub: Publisher, Subscriber, Topics and Messages.

- **Topic** – An intermediary channel that maintains a list of subscribers to relay messages to that are received from publishers
- **Message** – Serialized messages sent to a topic by a publisher which has no knowledge of the subscribers
- **Publisher** – The application that publishes a message to a topic
- **Subscriber** – An application that registers itself with the desired topic in order to receive the appropriate messages

Publishers/Subscriber models is sometimes also callsed Producer/Consumer model. One popular tool to implement this model is Apache Kafka.
![](/assets/pubsub.png)

The structure of a topic can vary depending on the streaming system that we implement, if you use Apache Kafka you will have more than one partition that ensures replication and increases the availability of information on the topic.

What is common to all systems is that topics are composed of ordered, immutable sequence of records that is continually appended to — a structured commit log. The records in the topics are each assigned a sequential id number called the offset that uniquely identifies each record within the topic.

![](/assets/anatomy-kafka.png)

## Advantages of pub/sub
- **Loose coupling** - Publishers are never aware of the existence of subscribers so that both systems can operate independently of each other. This methodology removes service dependencies that are present in traditional coupling.
- **Scalability** - Pub/sub messaging can scale to volumes beyond the capability of a single traditional data center. This level of scalability is primarily due to parallel operations, message caching, tree-based routing, and multiple other features built into the pub/sub model.

## Disadvantages of pub/sub
Message delivery issues
- A publisher may only deliver messages for a certain period of time regardless of whether the message was received or not.
- Since the publisher does not have a window into the subscriber it will always assume that the appropriate subscriber is listening. If the subscriber isn’t listening and misses an important message it can be disastrous for production systems.

You might want to read following references
- [Microsoft article on Pub/Sub](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/ff649664(v=pandp.10))