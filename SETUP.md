# Setup & Local Development Guide: visualmark-studio 💻

This guide provides end-to-end instructions for configuring your local development workstation, configuring environment parameters, and running visualmark-studio.

---

## 📋 System Prerequisites

Before you begin the installation and setup process, ensure your workstation meets the following runtime, tool, and hardware specifications.

### Software Runtimes & Tools

- **Node.js**: `v18.0.0+` (Recommended: `v20.x` LTS) 
  - *Verify via*: `node -v`
- **npm**: `v9.0.0+` (comes bundled with Node.js)
  - *Verify via*: `npm -v`
- **Python**: `v3.10+` (Recommended: `v3.11+` for optimal performance)
  - *Verify via*: `python --version`
- **pip**: Latest stable release matching your Python installation
  - *Verify via*: `pip --version`
- **Docker Engine**: `v24.0+` with container virtualization enabled
  - *Verify via*: `docker --version`
- **Docker Compose**: `v2.0+` (integrated with Docker Desktop or installed as a plugin)
  - *Verify via*: `docker compose version`
- **Git**: `v2.30+` configured with appropriate SSH or credential helpers
  - *Verify via*: `git --version`

### Recommended Hardware Specifications

- **CPU**: Quad-core processor (Intel Core i5 / AMD Ryzen 5 or better)
- **Memory (RAM)**: 16 GB minimum (32 GB recommended if running multiple containerized services simultaneously)
- **Storage**: SSD with at least 10 GB of free space for dependencies, images, and build caches
---

## 🔌 Default Service Ports & Endpoints

| Service | Protocol | Default URL / Port | Role & Responsibility |
| :--- | :--- | :--- | :--- |
| **Web Frontend Client** | HTTP | `http://localhost:3000` | User interface and live hot-reloader |
| **REST API Backend** | HTTP | `http://localhost:8000` | Primary application REST endpoints |
| **OpenAPI Swagger UI** | HTTP | `http://localhost:8000/docs` | Interactive API documentation console |
| **ReDoc Specification** | HTTP | `http://localhost:8000/redoc` | OpenAPI schema reference |
| **PostgreSQL / Storage**| TCP | `localhost:5432` | Relational persistent database |
| **Redis Cache** | TCP | `localhost:6379` | In-memory cache & session store |

---

## 🛠️ Step-by-Step Local Setup

### 1. Clone Working Tree
```bash
git clone https://github.com/owner/project.git
cd project
```

### 2. Configure Environment Parameters
```bash
cp .env.example .env
```

> [!TIP]
> Open `.env` and verify database connection strings and secrets before launching services.

### 3. Multi-Package Manager Installation

<details open>
<summary><b>npm & pip (Standard)</b></summary>

```bash
# Backend installation
cd backend && pip install -r requirements.txt
python -m uvicorn app:app --reload --port 8000

# In a separate terminal: Frontend installation
cd frontend && npm install
npm run dev
```

</details>

<details>
<summary><b>pnpm & uv (Blazing Fast)</b></summary>

```bash
# Backend installation
cd backend && uv pip install -r requirements.txt
python -m uvicorn app:app --reload --port 8000

# Frontend installation
cd frontend && pnpm install
pnpm dev
```

</details>

---

## 🐳 Docker Container Quickstart

To launch the full containerized cluster with persistent volume mounts:

```bash
# Build images and start services in background
docker compose up --build -d

# Inspect live cluster health
docker compose ps
```

---

## 🔧 Troubleshooting FAQ

<details>
<summary><b>Port 8000 or 3000 Conflict?</b></summary>

```bash
# Terminate lingering processes on port 8000
lsof -ti:8000 | xargs kill -9
```

</details>

<details>
<summary><b>Database Authentication Failure?</b></summary>

Verify that PostgreSQL credentials in `.env` match those declared in `docker-compose.yml`.

</details>
