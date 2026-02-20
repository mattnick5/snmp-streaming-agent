# SNMP Streaming Agent

A lightweight **SNMP trap ingestion service** that **normalizes SNMP traps into structured events** and **streams them to Apache Kafka**.

> **Kafka-compatible**, production-oriented, and designed for telecom/operations environments where high-volume traps must be ingested reliably and processed downstream (e.g., CEP, OpenSearch, Data Lake, ticketing).

## Key Features

- ✅ SNMP trap receiver (v2c/v3) *(depending on configuration)*
- ✅ Stateless **normalization** into a stable JSON event model
- ✅ Kafka producer with retry strategy *(and optional DLQ topic)*
- ✅ Horizontal scaling (run multiple instances)
- ✅ Docker-ready
- ✅ Observability-friendly (structured logs, optional Prometheus metrics)

## Why this exists

Traditional NMS/OSS ingestion paths often couple **trap ingestion** with **alarm processing**. This project focuses on doing one job extremely well:

**Ingest traps → convert to events → publish to Kafka**

Downstream systems (Flink/CEP, OpenSearch, Oracle, etc.) can then handle correlation, deduplication, clear matching, enrichment, and storage.

## Architecture (high level)
