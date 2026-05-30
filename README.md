Real‑Time Compliance Data Lake with Kafka + CocoIndex


📌 Overview
This project demonstrates how to build a real‑time compliance data pipeline using Apache Kafka and the CocoIndex Kafka connector.
It simulates financial transactions and loan applications flowing through Kafka, enriched with AI models, and validated against compliance rules.

The pipeline ensures at‑least‑once delivery, partition rebalancing, and automated deletion handling (via Kafka tombstones) — critical for HIPAA/GDPR/PCI environments.


🏗 Architecture
Producers → Publish events (transactions, loan_applications) into Kafka topics.

CocoIndex Consumers →

KafkaTopicStream: raw event stream for audit logs.

KafkaTopicMap: keyed state for latest compliance status per customer.

Processing Layer → PySpark + ONNX models for fraud detection, credit scoring, and compliance checks.

Compliance Layer → Tombstone messages automatically remove sensitive records when retention policies require.

Downstream → Enriched data published back to Kafka (compliance-validated topic), visualized in Power BI/Tableau dashboards.
