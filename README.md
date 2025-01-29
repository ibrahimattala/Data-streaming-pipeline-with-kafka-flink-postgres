# Real-Time Data Processing with Kafka, Flink, and PostgreSQL

## Overview
This project sets up a real-time data processing pipeline using Kafka, Flink, and PostgreSQL. The architecture includes:
- **Zookeeper**: Manages Kafka brokers.
- **Kafka**: Message broker for event streaming.
- **Kafka Producer**: Generates and sends data to Kafka topics.
- **Flink Processor**: Consumes, processes, and transforms Kafka messages.
- **PostgreSQL**: Stores processed data.

## Prerequisites
Ensure you have the following installed:
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Setup & Running
1. Clone the repository:
   ```sh
   git clone https://github.com/ibrahimattala/Data-streaming-pipeline-with-kafka-flink-postgres.git
   cd Data-streaming-pipeline-with-kafka-flink-postgres
   ```
2. Start the services:
   ```sh
   docker-compose up -d
   ```
3. Verify the setup:
   - Kafka is running at `localhost:9092`
   - PostgreSQL is accessible on `localhost:5438`

## Services Details
| Service          | Description                                     | Ports        |
|-----------------|-------------------------------------------------|-------------|
| Zookeeper       | Kafka dependency for broker management         | 32181       |
| Kafka          | Message broker for event-driven data            | 9092        |
| Kafka Producer | Generates and pushes events to Kafka            | -           |
| Flink Processor | Consumes and processes Kafka events            | -           |
| PostgreSQL      | Database for storing processed data            | 5438->5432  |

## Environment Variables
| Variable           | Description                 | Default Value     |
|--------------------|----------------------------|------------------|
| KAFKA_SERVER      | Kafka broker address       | kafka:9092       |
| ZOOKEEPER_SERVER  | Zookeeper server address  | zookeeper:32181  |
| PRODUCER_INTERVAL | Interval for producing data | 100              |

## Stopping the Services
To stop the services, run:
```sh
docker-compose down
```

## Logs & Debugging
To check logs for a specific service:
```sh
docker-compose logs -f <service-name>
```
Example:
```sh
docker-compose logs -f kafka
```

