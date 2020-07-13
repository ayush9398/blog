---
layout: post
title: Kafka  Quickstart with python
date: 2020-04-05 22:04
summary: Start with Kafka immediately through python!
category: beginner
---

I have been working as a DevOps intern at Bobble.ai for almost 2 months now. My first task when I joined the internship was researching about Kafka, and believe me, I had no idea about kafka. I have seen the name many times in the requirements section of many internships but never got a chance to really work on it up close.

## What is Kafka?!

![](https://media.giphy.com/media/XQvhpuryrPGnK/giphy.gif)

In very simpler terms, it lets you stream data from one end to another but it handles some other things too. There are three parts to Kafka workflow, just like any market:

- Producer
- Broker
- Consumer

In terms of data streaming, we can get a clue from the names itself. Producer and consumer are the endpoints, while broker handles recieving and then passing on of data packets to consumer.

![courtesy of kafka main website.](https://kafka.apache.org/23/images/kafka-apis.png)

The above picture already gives an idea about another benefit of kafka, one broker can get data from multiple producers and can give data to multiple consumers. So, maybe you want to use get logs from one server into multipe other servers.

Basically, by streaming you may think there is no data storage..... true to an extent. Kafka stores recent data only depends on how you choose it, and deletes it as it becomes outdated.

You can install Kafka [here](https://kafka.apache.org/downloads).

## Python and Kafka

![](https://media.giphy.com/media/mBhfvDOd7n8FPGBs6B/giphy.gif)

If you code, you may already know that python can work with almost everything. There is a python module by the name kafka, install through pip, `pip install kafka-python`. This is used for creating consumer and producer scripts. You need kafka broker service to connect to also, you can start it on your local system.

Now, `KafkaConsumer` is simple to work with, you just need to mention a topic and the link to the broker, other details are optional.

`cons = KafkaConsumer('my-topic', bootstrap_servers="localhost:9092", api_version=(0, 10, 1), group_id = 'my-group')`

In the above line, I have mentioned the topic to be `my-topic` and I have mentioned link for kafka broker to be my locally hosted kafka, on default port `9092`. The other mentioned params are optional but can come into handy. There seems to be multiple kafka api available, maybe based on stable and I was encountering an error so I found a solution to select the particular `api_vesrion` like this. I used multiple kafka consumers in order to keep serving it's purpose even though any one kafka consumer encounters any error.

`for msg in cons`

Now, I can get the recieved messages just like this. You can see the contents of the msg through `msg.value`.

After recieving the data you can work on it in any way you want to with the help of Python. There are many other functions that Kafka allows to use and which can help in solving more complex problems.

Like consumer, there is also `KafkaProducer` class available to use.

`self.producer = KafkaProducer(bootstrap_servers=kafka_brokers max_request_size=3173440261)`

In order to send data, you have to mention the kafka broker.

`KafkaProducer` has a function `send()` in order to send the data. 

`result = self.producer.send(topic, key=b'log', value=data)`

Thats it!! I hope you find Kafka easy to work, with the help of python. Btw, the documentation is pretty good and there are many helper function for different complex operations.

Happy coding! Cheers!!!