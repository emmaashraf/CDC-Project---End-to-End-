🚀 Real-Time E-commerce CDC System
A complete Change Data Capture (CDC) implementation for a real-time e-commerce platform using Debezium, Kafka, and multiple data consumers.
🎯 What This Project Does
This system captures every change (INSERT, UPDATE, DELETE) from a PostgreSQL database in real-time and automatically:

🔍 Indexes data in Elasticsearch - for fast product/order search
💾 Caches hot data in Redis - for lightning-fast access
📊 Stores in MongoDB warehouse - for analytics with full version history
📧 Sends notifications - email, SMS, and push notifications to customers

All of this happens automatically without changing a single line of application code!
🏗️ Architecture

┌─────────────────┐
│   PostgreSQL    │  (Source Database)
│  E-commerce DB  │
└────────┬────────┘
         │ WAL (Write-Ahead Log)
         ↓
    ┌────────────┐
    │  Debezium  │  (CDC Engine - reads WAL)
    └─────┬──────┘
          │
          ↓
    ┌──────────┐
    │  Kafka   │  (Message Broker)
    └────┬─────┘
         │
    ┌────┴─────────────────────────────────┐
    │                                      │
    ↓                ↓                     ↓                ↓
┌──────────┐  ┌──────────┐  ┌──────────────┐  ┌──────────────┐
│Elastic-  │  │  Redis   │  │   MongoDB    │  │Notifications │
│search    │  │  Cache   │  │  Warehouse   │  │ (Email/SMS)  │
└──────────┘  └──────────┘  └──────────────┘  └──────────────┘
