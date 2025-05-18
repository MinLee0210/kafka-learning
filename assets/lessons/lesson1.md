# Lesson 1: Introduction & Setting Up Kafka for Computer Vision

---

**Goal:**  
Introduce the problem, explain why Kafka is useful in AI/computer vision pipelines, and guide the reader through setting up Kafka and a basic producer.

## Schema

### 1. Introduction
- Real-time data in computer vision
- Why Kafka? (Scalability, decoupling, streaming)

### 2. Kafka Basics
- What is Kafka?
- Key concepts: brokers, topics, producers, consumers

### 3. Setup
- Install Kafka ([official docs](https://kafka.apache.org/documentation/))
- Start Zookeeper & Kafka server (with commands)

### 4. Implementing basic Kafka producer and listener
- Simple Python (or preferred language) producer script
- Send sample image/frame data to a Kafka topic
- Simple Python (or preferred language) listener script
- Listen to the Kafka topic and print messages

### 5. Summary & Next Steps
- Wrap up and preview the next lesson.

---


## Introduction

I am learning about Kafka and this is my first lesson. My goal is to create an event streaming module for sending data from whatever source to relevant services. 

For example, imagine streaming video frames into Kafka, where each frame is processed by AI models to detect objects in real time. Along the way, I want to tap into the stream at any point to perform additional analysis, gather metrics, or log specific events. This flexibility allows me to build powerful, modular data pipelines that can adapt to a wide range of use cases.

In this lesson, I will focus on its fundamental knowledge as well as its architecture, and do my best to show you how to set up Kafka and create a basic producer to send data to a Kafka topic. 

## Fundamental Knowledge



## Code Implementation

### Environment Setup




### Implementing basic Kafka producer and listener

Producer

```Python
import time
import httpx

from kafka import KafkaProducer


TOPIC = "TEST_KAFKA"
BOOTSTRAP_SERVERS = '0.0.0.0:9092'
SAMPLES_URL = "https://catfact.ninja/fact"

producer = KafkaProducer(bootstrap_servers=[BOOTSTRAP_SERVERS])

while True:

    cat_rsp = httpx.get(SAMPLES_URL)
    if cat_rsp.status_code != 200: 
        print(f"Fetch data from {SAMPLES_URL} failed!!!")
        
    value = cat_rsp.json()  # ex: {"fact":"A female cat can be referred to as a molly or a queen, and a male cat is often labeled as a tom.","length":96}
    msg = value.get("fact")
    print(f"[Producer] Kafka send: {msg}")
    value = bytes(value.get("fact"), encoding="utf-8")
    producer.send(topic=TOPIC, 
                  value=value)
    

    time.sleep(10)
```


Listener

```Python
from kafka import KafkaConsumer

TOPIC = "TEST_KAFKA"
BOOTSTRAP_SERVERS = 'localhost:9092'

consumer = KafkaConsumer(
    TOPIC, 
    bootstrap_servers=[BOOTSTRAP_SERVERS]
)
for msg in consumer:

    print(f"[Listener] Kafka received: {msg.value}")
```



## Summary


In this lesson, I have learned the fundamental knowledge of Kafka and its architecture. I have also shown you how to set up Kafka and create a basic producer to send data to a Kafka topic. 

Kafka is a distributed streaming platform that can be used to build real-time data pipelines and streaming applications. It is a high-throughput, low-latency, and fault-tolerant system that can handle trillions of events per day.

In the AI field, especially in Computer Vision, Kafka can be used to build real-time data pipelines and streaming applications. It can be used to send video frames to a Kafka topic, where each frame is processed by AI models to detect objects in real time. Along the way, I want to tap into the stream at any point to perform additional analysis, gather metrics, or log specific events. This flexibility allows me to build powerful, modular data pipelines that can adapt to a wide range of use cases.

I hope you have learned something new and interesting from this lesson. I will continue to learn and share my knowledge with you in the next lesson. Thank you for reading!


## Reference

1. Kafka - Documentation - URL: https://kafka.apache.org/documentation/
2. Vu Trinh - If you're learning Kafka, this article is for you - URL: https://vutr.substack.com/p/if-youre-learning-kafka-this-article