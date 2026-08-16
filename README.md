# Real-Time Financial Fraud Detection Pipeline

## Project Overview

A real-time financial fraud detection system that monitors incoming transactions, processes them through a streaming pipeline, and identifies potentially fraudulent transactions using machine learning.

The system demonstrates how modern streaming technologies can be combined to detect suspicious financial activity with low latency.

## Key Features

- Real-time transaction streaming
- Apache Kafka for event ingestion
- Apache Spark Structured Streaming for real-time processing
- Machine learning based fraud detection
- TimescaleDB for storing transaction and fraud-alert data
- Grafana dashboard for monitoring
- Separate simulation of normal and suspicious transactions
- Real-time fraud alerts and transaction analytics

## System Architecture

Transaction Producers
        |
        v
Apache Kafka
        |
        v
Spark Structured Streaming
        |
        v
Machine Learning Fraud Detector
        |
        +------------------+
        |                  |
        v                  v
Normal Transaction     Fraud Alert
        |                  |
        +--------+---------+
                 |
                 v
             TimescaleDB
                 |
                 v
              Grafana

## Technology Stack

| Component | Technology |
|---|---|
| Programming | Python |
| Streaming | Apache Kafka |
| Stream Processing | Apache Spark |
| Machine Learning | Scikit-learn |
| Database | TimescaleDB |
| Monitoring | Grafana |
| Infrastructure | Docker / Docker Compose |

## Project Structure

```text
streaming_fraud_detection/
│
├── data_processor/
│   ├── fraud_detector.py
│   ├── fraud_detection_model.pkl
│   └── Dockerfile.spark
│
├── data_producer/
│   ├── normal_transaction_producer.py
│   ├── hacker_transaction_producer.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── model_build/
│   ├── ml_model.py
│   ├── training_data_generation.py
│   ├── synthetic_fraud_data.csv
│   └── requirements.txt
│
├── monitoring/
│   └── grafana-dashboard/
│
├── init.sql
├── docker-compose.yml
└── README.md