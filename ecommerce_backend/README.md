# Backend Microservices Project

A **backend microservices system** built with **User, Product, Order, and Notification services**, demonstrating **event‑driven architecture** using **RabbitMQ** and **Apache Kafka**. The project focuses on scalability, loose coupling, and real‑world asynchronous communication patterns.

---

## Microservices Overview

### 1️⃣ User Service

* User registration & management
* Authentication/authorization (JWT-ready)
* Publishes user-related events

### 2️⃣ Product Service

* Product catalog management
* Inventory handling
* Emits product update events

### 3️⃣ Order Service

* Order creation & lifecycle management
* Communicates with User & Product services
* Publishes order events

### 4️⃣ Notification Service

* Consumes events from Kafka & RabbitMQ
* Sends notifications (email/SMS/log-based)
* Fully asynchronous, no direct service dependency

---

##  Event‑Driven Communication

This project uses **both RabbitMQ and Apache Kafka** to demonstrate different messaging patterns:

### RabbitMQ

* Used for **command-style messaging**
* Point-to-point communication
* Reliable delivery with acknowledgements

### Apache Kafka

* Used for **event streaming**
* High-throughput, scalable event consumption
* Ideal for audit logs & notifications

```text
Order Service  ──▶  Kafka Topic  ──▶  Notification Service
Product Service ─▶ RabbitMQ Queue ─▶ Notification Service
```

---

## Architecture

* Microservices Architecture
* Event‑Driven Design
* Loose coupling via message brokers
* Independent service deployment

```text
Client
  │
  ▼
API Gateway (optional)
  │
  ├── User Service
  ├── Product Service
  ├── Order Service
  │        │
  │        ├── Kafka
  │        └── RabbitMQ
  ▼
Notification Service
```

---

##  Tech Stack

* **Backend:** Spring Boot / ASP.NET Core (microservice-ready)
* **Messaging:** RabbitMQ, Apache Kafka
* **Database:** MySQL / PostgreSQL (per service)
* **API Style:** REST APIs
* **Build Tool:** Maven / Gradle / .NET CLI
* **Containerization:** Docker (optional)

---

##  Key Features

* Scalable microservice design
* Asynchronous communication
* Fault-tolerant messaging
* Clean separation of concerns
* Production‑style architecture

---

##  Project Structure

```text
backend-microservices-project/
│
├── user-service/
├── product-service/
├── order-service/
├── notification-service/
├── docker-compose.yml
└── README.md
```

---

## How to Run

1. Start Kafka & RabbitMQ

```bash
docker-compose up -d
```

2. Start each microservice

```bash
cd user-service
mvn spring-boot:run
```

3. Repeat for all services

---

## Use Cases Covered

* User places an order
* Order event published to Kafka
* Notification service consumes event
* Inventory update via RabbitMQ

---


##  License

This project is for **learning and demonstration purposes**.

---
