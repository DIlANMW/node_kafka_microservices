# Node.js Kafka Microservices

A simple Node.js microservices project demonstrating inter-service communication using **Apache Kafka**.  
This project includes:

- **Order Service**: Sends messages to a Kafka topic (`order-topic`).
- **Notification Service**: Listens to messages from the Kafka topic and logs them.

## 📁 Project Structure

nodejs-kafka-microservices/
├── order-service/
│ ├── src/
│ │ ├── kafka/
│ │ │ └── producer.js
│ │ ├── routes/
│ │ │ └── order.route.js
│ │ ├── app.js
│ │ └── server.js
│ ├── package.json
│ └── Dockerfile
│
├── notification-service/
│ ├── src/
│ │ ├── kafka/
│ │ │ └── consumer.js
│ │ └── server.js
│ ├── package.json
│ └── Dockerfile
│
├── docker-compose.yml
└── README.md

# Order Service
cd order-service
npm install

# Notification Service
cd ../notification-service
npm install

# Setup kafka manually in local

Download Apache Kafka

Download Kafka → choose a binary with Scala 2.12 or 2.13

Extract & Navigate
tar -xzf kafka_2.13-3.6.1.tgz
cd kafka_2.13-3.6.1

Start Zookeeper
bin/zookeeper-server-start.sh config/zookeeper.properties

Start Kafka Broker (in another terminal)
bin/kafka-server-start.sh config/server.properties
Kafka will now be available on localhost:9092.


# Start Order Service:
cd order-service
npm start

# Start Notification Service:
cd notification-service
npm start
