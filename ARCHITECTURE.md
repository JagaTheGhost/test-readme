# System Architecture: visualmark-studio 🏛️

<!-- System diagrams can be visually designed and updated using the Mermaid Diagram Studio (mermaid) -->

This document details the architectural topology, data pipelines, layer boundaries, and reliability principles governing **visualmark-studio**.

---

## 🗺️ Architectural Layer Topology

| Tier | Component / Module | Technology Stack | Transport / Protocol | Key Responsibility |
| :--- | :--- | :--- | :--- | :--- |
| **Client Presentation Layer** | Web Application SPA | React 18 / TypeScript / Vite | HTTPS / JSON REST | Responsive user interface, client routing, optimistic state hydration |
| **API & Routing Gateway** | REST Service Gateway | FastAPI / Python 3.11 | OpenAPI 3.1 / HTTP 2 | Request routing, Pydantic validation, CORS & auth token verification |
| **Domain Logic Layer** | Business Services Engine | Asynchronous Workers | Internal Python Modules | Data processing, schema synthesis, business validation workflows |
| **Data & Persistence Layer**| Primary Database | PostgreSQL / Connection Pool | TCP Wire Protocol | ACID transactional persistence, indexed models & automated schema migrations |
| **Caching & Session Layer** | Memory State Store | Redis Cache | Redis Protocol | Sub-millisecond session validation, rate limiting & 300s TTL cache |

---

## 🔄 End-to-End Request Lifecycle Pipeline

| Step | Initiator | Target Component | Protocol | Description & Error Boundary |
| :--- | :--- | :--- | :--- | :--- |
| **1. Inbound Request** | Client Browser | API Gateway | HTTPS | User dispatches action; TLS terminated at edge |
| **2. Auth & Validation**| API Gateway | Security Middleware | Internal | Bearer JWT parsed; schema checked against typed contract |
| **3. Cache Lookup** | API Gateway | Redis Store | TCP | Checks for cached response key; on hit, returns immediately |
| **4. Domain Execution** | API Gateway | Domain Service | Async Call | Core business execution executed in thread-pool |
| **5. Data Query** | Domain Service | PostgreSQL DB | Pooled SQL | Parameterized SQL query executed within transactional session |
| **6. Cache Writeback** | Domain Service | Redis Store | Async Pipe | Fresh data serialized and stored with time-to-live |
| **7. Outbound Response**| API Gateway | Client Browser | HTTP 200 OK | Serialized JSON payload returned with security headers |

---

## 🏗️ Directory Boundary Architecture

| Directory / Package | Architectural Role | Boundary Rules & Constraints |
| :--- | :--- | :--- |
| `backend/api/` | Route Controllers | Responsible only for HTTP serialization and parameter parsing |
| `backend/core/` | System Configuration | Houses environment variables, security tokens, and DB engines |
| `backend/models/`| Data Schema Entities | Declares persistent entities; strictly isolated from presentation |
| `backend/services/`| Domain Logic | Houses reusable business workflows; fully decoupled and testable |
| `frontend/src/components/`| Presentation Units | UI components with predictable props and zero direct network calls |
| `frontend/src/utils/`| Client Transformers | Pure functions for data formatting, export, and client validations |

---

## 🛡️ Security & Reliability Principles

1. **Strict Input Sanitization:** Every inbound payload is validated against strict Pydantic models before execution.
2. **Stateless Compute:** Backend nodes maintain zero sticky session state, enabling rapid auto-scaling behind reverse proxies.
3. **Least Privilege Governance:** Database credentials and external secrets are injected exclusively via sanitized environment variables.
4. **Resilient Degradation:** In the event of external service rate limits or timeouts, fallback heuristic models maintain operational uptime.
