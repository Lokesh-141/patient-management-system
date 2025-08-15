# 🏥 Patient Management System
A modular, production-grade backend for healthcare platforms—built with Spring Boot, gRPC, Kafka, and Protobuf. Designed for clarity, scalability, and real-world hospital workflows.

> ⚠️ This repository contains **backend services only**. There is **no UI layer**. All modules are API-first, integration-ready, and built for reviewer-grade clarity.

---

## 🧠 What This System Solves

Modern healthcare platforms require:

- Secure onboarding of patients with validated data
- Automated billing tied to patient creation
- Real-time analytics for operational insights
- Stateless authentication and role-based access
- Clear service boundaries for scalability and maintainability

This system delivers those capabilities through a clean, event-driven architecture.

---

## 🧱 Project Structure

```
patient-management/
├── patient-service/             # Manages patient records and emits Kafka events
├── auth-service/                # Handles authentication and JWT issuance
├── billing-service/             # gRPC-based billing account creation
├── analytics-service/           # Consumes Kafka events for reporting and insights
├── api-gateway/                 # Centralized routing and request forwarding
├── api-requests/                # REST + Swagger contracts for external clients
├── grpc-requests/               # Protobuf contracts for gRPC communication
├── infrastructure/              # Dockerfiles, config templates, secrets
├── integration-tests/           # End-to-end test suite across services
└── patient-management.iml       # IntelliJ project descriptor
```

---

## 🧱 Tech Stack

| Layer        | Technology                          |
|--------------|--------------------------------------|
| Framework    | Spring Boot 3.4.8                    |
| Language     | Java 21                              |
| Database     | PostgreSQL / H2 (dev)                |
| Messaging    | Apache Kafka                         |
| RPC          | gRPC + Protobuf                      |
| Docs         | SpringDoc OpenAPI                    |
| Build Tool   | Maven                                |
| Container    | Docker (multi-stage build)           |
| Testing      | JUnit 5 + RestAssured                |

---

## 🧮 Compatibility Notice

This system is developed and verified on:

- **Java:** 21  
- **Spring Boot:** 3.4.8  
- **Kafka:** bitnami/kafka:latest  
- **Docker Desktop:** 4.x  
- **PostgreSQL:** 15.x  
- **Maven:** 3.9.x

>  ⚠️ Versions must be strictly followed for compatibility. Deviations may cause unexpected behavior or failures.
---

## 🔗 Service Interactions

| Source           | Target            | Protocol | Contract             |
|------------------|-------------------|----------|----------------------|
| `patient-service`| `billing-service` | gRPC     | `billing_service.proto` |
| `patient-service`| `analytics-service`| Kafka   | `patient_event.proto`   |
| `api-gateway`    | All services      | HTTP     | REST + Swagger       |

---

## 🧩 Module Highlights

### `patient-service`
- RESTful CRUD for patient records
- DTO validation with group constraints
- gRPC call to billing-service
- Kafka event emission (`PatientCreated`)
- PostgreSQL persistence with UUIDs

### `auth-service`
- Stateless JWT authentication
- Login and token refresh endpoints
- Role-based access control

### `billing-service`
- gRPC server exposing `CreateBillingAccount`
- Protobuf-based request/response
- Isolated billing logic

### `analytics-service`
- Kafka consumer for patient events
- Aggregates metrics for reporting
- Exposes REST endpoints for insights

### `api-gateway`
- Routes external requests to internal services
- Handles fallback, CORS, and routing logic

---

## 🧠 Real-World Justification

- **Event-Driven Design:** Patient creation triggers billing and analytics asynchronously—mirroring real hospital workflows.
- **gRPC for Internal RPC:** Fast, typed communication between services with Protobuf contracts—ideal for low-latency backend calls.
- **Kafka for Observability:** Decoupled event stream enables real-time insights without impacting core flows.
- **Strict Boundaries:** Each module owns its domain—no shared databases, no cross-service leaks.
- **Infrastructure-as-Code Ready:** Dockerfiles, secrets, and configs are modular and production-grade.
- **Reviewer-Grade Clarity:** Every folder, contract, and interaction is annotated for instant understanding.

---

## 📘 Notes

- This system is backend-only. There is no frontend or UI layer.
- All services are designed for API-level integration and orchestration.
- Folder boundaries are strictly maintained for clarity and reproducibility.
- Use exact versions for compatibility.

---

## 🐳 Kafka (Docker Image)

| Property         | Value                          |
|------------------|--------------------------------|
| Image            | `bitnami/kafka:latest`         |
| Container Name   | `kafka`                        |
| Bind Ports       | `9092:9092`, `9094:9094`       |
| Run Options      | `--network internal`           |

### Enviroment Variables
```
KAFKA_CFG_ADVERTISED_LISTENERS=PLAINTEXT://kafka:9092,EXTERNAL://localhost:9094;
KAFKA_CFG_CONTROLLER_LISTENER_NAMES=CONTROLLER;
KAFKA_CFG_CONTROLLER_QUORUM_VOTERS=0@kafka:9093;
KAFKA_CFG_LISTENER_SECURITY_PROTOCOL_MAP=CONTROLLER:PLAINTEXT,EXTERNAL:PLAINTEXT,PLAINTEXT:PLAINTEXT;
KAFKA_CFG_LISTENERS=PLAINTEXT://:9092,CONTROLLER://:9093,EXTERNAL://:9094;
KAFKA_CFG_NODE_ID=0;
KAFKA_CFG_PROCESS_ROLES=controller,broker
```

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

## 🌟 About Me

Hi there! I'm Kairav Singh.. I’m an IT professional and passionate YouTuber on a mission to share knowledge and make working with data enjoyable and engaging!
