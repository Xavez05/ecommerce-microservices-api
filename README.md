# 🛒 E-Commerce Microservices Platform

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)

A fully distributed e-commerce backend built with a **microservices architecture** using Spring Boot, Spring Cloud (Eureka + API Gateway), and Docker Compose.

---

## 📐 Architecture Overview

```
                        ┌──────────────────────────────────────────┐
                        │              Docker Compose               │
                        │                                          │
  Client ──REST──►      │  ┌─────────────────┐                    │
                        │  │   API Gateway   │◄── Entry point      │
                        │  └────────┬────────┘                    │
                        │           │ routes requests              │
                        │  ┌────────▼────────┐                    │
                        │  │  Eureka Server  │  Service Discovery  │
                        │  └────────┬────────┘                    │
                        │           │ registers & discovers        │
                        │  ┌────────┴──────────────────────┐      │
                        │  │                               │      │
                        │  ▼           ▼           ▼       ▼      │
                        │ ┌──────┐ ┌──────┐ ┌─────────┐ ┌──────┐ │
                        │ │Orders│ │Paymt.│ │Products │ │Secur.│ │
                        │ │:8082 │ │:8083 │ │  :8084  │ │:8085 │ │
                        │ └──────┘ └──────┘ └─────────┘ └──────┘ │
                        └──────────────────────────────────────────┘
```

---

## 🧩 Services

### 🌐 API Gateway — `localhost:8080`
Single entry point for all client requests. Routes traffic to the appropriate microservice and handles cross-cutting concerns.

### 🔍 Eureka Server — `localhost:8761`
Service registry that allows microservices to discover and communicate with each other dynamically.

### 📦 Products Service — `localhost:8084`
Manages the product catalog: creation, updates, queries, and inventory tracking.

### 🧾 Orders Service — `localhost:8082`
Handles order creation, status tracking, and coordination with the payment and products services.

### 💳 Payment Service — `localhost:8083`
Processes payment transactions associated with orders.

### 🔐 Security Service — `localhost:8085`
Manages authentication and authorization across the platform.

---

## 🚀 Getting Started

### Prerequisites
- Java 21+
- Maven 3.9+
- Docker & Docker Compose

### Build all services
```bash
mvn clean package -DskipTests
```

### Run with Docker
```bash
docker-compose up --build
```

### Service URLs

| Service | URL |
|---|---|
| API Gateway | http://localhost:8080 |
| Eureka Dashboard | http://localhost:8761 |
| Orders Service | http://localhost:8082 |
| Payment Service | http://localhost:8083 |
| Products Service | http://localhost:8084 |
| Security Service | http://localhost:8085 |

---

## 📬 Postman Collection

A ready-to-use Postman collection is included in the root of the project:

```
collection.json
```

Import it directly into Postman to test all available endpoints across every service.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Java |
| Framework | Spring Boot |
| Service Discovery | Spring Cloud Netflix Eureka |
| API Routing | Spring Cloud Gateway |
| Containerization | Docker · Docker Compose |
| Build Tool | Maven |

---

## 👨‍💻 Author

**Antony Chávez** — Backend Developer
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/antonychavez)
[![GitHub](https://img.shields.io/badge/GitHub-Xavez05-181717?style=flat&logo=github&logoColor=white)](https://github.com/Xavez05)
