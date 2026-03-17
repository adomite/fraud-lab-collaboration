## 🏗️ Architecture Diagram

![Architecture](docs/txnflow3.png)

> 📐 Editable diagram: [docs/txnflow3.drawio](docs/txnflow3.drawio)

## 🔄 Transaction Flow

1. **Client** sends HTTPS payment request
2. **API Gateway** (Traefik) routes to Auth Service
3. **Auth Service** sends Score Request to Fraud Service
4. **Fraud Service** runs ML Scoring Engine + Rules Engine
5. **Decision** returned to Auth Service
6. **Auth Service** stores transaction in PostgreSQL
7. **Auth Service** caches result in Redis
8. **Response** returned to Client (APPROVED/DECLINED)

Architecture in construction