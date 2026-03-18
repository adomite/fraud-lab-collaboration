## 🏗️ Architecture Diagram

![Architecture](docs/txnflow3.png)

> 📐 Editable diagram: [docs/txnflow3.drawio](docs/txnflow3.drawio)

Architecture in construction
---

## 🔄 Transaction Flow

| Step | Component | Action |
|------|-----------|--------|
| 1 | 💳 Client | Sends HTTPS payment request |
| 2 | 🌐 API Gateway | Routes to Auth Service :8000 |
| 3 | 🏦 Auth Service | Sends Score Request to Fraud Service |
| 4 | 🤖 ML Scoring Engine | Calculates fraud score 0.0-1.0 |
| 5 | 📋 Rules Engine | Applies business rules |
| 6 | 🔍 Fraud Service | Returns Decision to Auth Service |
| 7 | 🏦 Auth Service | Stores transaction in PostgreSQL |
| 8 | ⚡ Redis | Caches result |
| 9 | 💳 Client | Receives APPROVED ✅ or DECLINED ❌ |

---

## 📦 Components

| Component | Technology | Port | Purpose |
|-----------|-----------|------|---------|
| API Gateway | Traefik | :80 | Routing & Load Balancing |
| Auth Service | FastAPI | :8000 | Transaction Authorization |
| Fraud Service | FastAPI | :8001 | Fraud Detection |
| Database | PostgreSQL | :5432 | Transaction Storage |
| Cache | Redis | :6379 | Speed Layer |
| Metrics | Prometheus | :9090 | Metrics Collection |
| Dashboard | Grafana | :3000 | Visualization |
| Tracing | Jaeger | :16686 | Distributed Tracing |

---

## 🚀 Quick Start
