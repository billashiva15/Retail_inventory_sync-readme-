# 🚀 API-Led Retail Inventory Sync & Automated Stock Pipeline

[![MuleSoft](https://img.shields.io/badge/MuleSoft-Runtime%204.12-00A1E0?logo=mulesoft&logoColor=white)](https://www.mulesoft.com/)
[![DataWeave](https://img.shields.io/badge/DataWeave-2.0-00A1E0)](https://docs.mulesoft.com/dataweave/latest/)
[![RabbitMQ](https://img.shields.io/badge/Messaging-RabbitMQ%20%2F%20CloudAMQP-FF6600?logo=rabbitmq&logoColor=white)](https://www.rabbitmq.com/)
[![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Build-Apache%20Maven-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![GitHub](https://img.shields.io/badge/Version%20Control-GitHub-181717?logo=github&logoColor=white)](https://github.com/)

A robust, enterprise-grade, API-led MuleSoft integration solution engineered for the **Cognizant Hackathon**. The pipeline seamlessly synchronizes retail inventory, validates incoming warehouse feeds, handles asynchronous reorder events, integrates with external supplier systems, and securely persists critical inventory data.

> **Project Goal:** Deliver a decoupled, highly maintainable, and observable multi-layered integration pipeline leveraging Experience, Process, and System API patterns.

---

## 📌 Table of Contents

- [Architecture Overview](#-architecture-overview)
- [Core Capabilities](#-core-capabilities)
- [Technology Stack](#-technology-stack)
- [Repository Structure](#-repository-structure)
- [End-to-End Workflow](#-end-to-end-workflow)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [Reliability and Security](#-reliability-and-security)
- [Development & Testing](#-development--testing-workflow)
- [Roadmap](#-roadmap)
- [Author & Project Info](#-author--project-info)

---

## 🏗️ Architecture Overview

The solution strictly adheres to the **API-Led Connectivity** methodology, cleanly separating consumer experiences, business process orchestration, and backend system connectivity into independent layers.

### Layer Responsibilities

| Layer | Primary Responsibility | Typical Operations |
| :--- | :--- | :--- |
| **Experience API** | Client-facing entry point; exposes REST resources and applies consumer-level validation, rate limiting, and security policies. | Inventory lookups, manual reorder requests, purchase-order status queries. |
| **Process API** | Coordinates business rules, data transformations, asynchronous event messaging, and downstream orchestration. | Validating inventory deltas, determining reorder thresholds, publishing/consuming queue events. |
| **System API** | Encapsulates backend connectivity, abstracting database operations and vendor API complexities. | Persisting inventory and audit logs, querying database records, communicating with supplier endpoints. |

---

## ✨ Core Capabilities

* **Warehouse File Ingestion:** Automated file-driven workflow for processing incoming warehouse CSV inventory snapshots safely.
* **Safe File Validation:** Rigorous validation of naming conventions, file stability, and readiness flags to prevent reading partial or corrupted writes.
* **Inventory Synchronization:** High-performance transformations via DataWeave to map source data into standardized domain models.
* **Asynchronous Event-Driven Messaging:** Utilization of RabbitMQ / CloudAMQP to decouple resource-heavy reorder workflows from immediate ingestion blocks.
* **Automated Reorder Orchestration:** Dynamic threshold evaluation triggering automated purchase order creation pipelines.
* **Supplier System Integration:** Secure outbound calls to vendor systems through dedicated system boundaries.
* **Comprehensive Auditability:** Robust persistence layers capturing item state, reorder history, and processing execution telemetry in MySQL.

---

## 🧰 Technology Stack

| Category | Technology / Tool |
| :--- | :--- |
| **Integration Runtime** | Anypoint Studio / Mule Runtime 4.12 |
| **API Specification** | RAML 1.0 |
| **Data Transformation** | DataWeave 2.0 |
| **Messaging Broker** | RabbitMQ / CloudAMQP |
| **Database Persistence** | MySQL 8.0 |
| **Build Tool** | Apache Maven |
| **Version Control** | Git & GitHub |

---

## 📂 Repository Structure

```text
NPN_Cognizant_Hackathon_usecase18/
├── experience-api/       # Client-facing Experience API layer & RAML specs
├── process-api/          # Business logic, orchestration, and messaging flows
├── system-api/           # Database connectors and supplier integration layer
├── docs/                 # Architectural diagrams and assets
└── README.md
