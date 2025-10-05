cdc-ecommerce-project/
├── docker-compose.yml          # All services
├── postgres/
│   └── init.sql               # Database schema
├── debezium/
│   └── connector-config.json  # Debezium setup
├── consumers/
│   ├── elasticsearch_consumer.py
│   ├── redis_consumer.py
│   ├── warehouse_consumer.py
│   └── notification_consumer.py
├── api/
│   └── app.py                 # Simple API to test
├── requirements.txt
└── README.md
