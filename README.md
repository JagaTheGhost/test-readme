# visualmark-studio

> **Modern Code + Visual Desktop IDE for Markdown authoring, Mermaid diagramming, and complete documentation suites.**

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=0969da)](https://github.com/JagaTheGhost/visualmark-studio/stargazers) [![GitHub Forks](https://img.shields.io/github/forks/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=0969da)](https://github.com/JagaTheGhost/visualmark-studio/network/members) [![Issues](https://img.shields.io/github/issues/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=e11d48)](https://github.com/JagaTheGhost/visualmark-studio/issues) [![License](https://img.shields.io/badge/License-MIT-10b981.svg?style=for-the-badge)](https://github.com/JagaTheGhost/visualmark-studio/blob/main/LICENSE) [![Code Size](https://img.shields.io/github/languages/code-size/JagaTheGhost/visualmark-studio?style=for-the-badge&color=8b5cf6)](https://github.com/JagaTheGhost/visualmark-studio)
<br/>
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=FFD62E) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white) ![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

</div>

<div align="center">

[🚀 Getting Started](#getting-started) &nbsp;•&nbsp; [✨ Features](#features) &nbsp;•&nbsp; [🛠️ Tech Stack](#tech-stack) &nbsp;•&nbsp; [🏛️ Architecture](#architecture) &nbsp;•&nbsp; [📖 Usage](#usage) &nbsp;•&nbsp; [⚙️ Configuration](#configuration) &nbsp;•&nbsp; [🔧 Troubleshooting](#troubleshooting) &nbsp;•&nbsp; [🤝 Contributing](#contributing)

</div>

## ✨ Features

- **⚡ Autonomous High-Throughput Core**
  - **Low-Latency Execution:** Engineered from the ground up for minimal memory overhead and near-instantaneous response cycles.
  - **Asynchronous Processing:** Non-blocking event loops capable of handling heavy concurrent workloads without thread starvation.
  - **Resource Optimization:** Dynamic garbage collection tuning and efficient memory pooling for sustained peak performance.

- **🎨 Stitch-Engineered Developer Workspace**
  - **Visual Hierarchy:** Polished UI/UX design featuring intuitive navigation and contextual tooltips.
  - **Glassmorphic Aesthetics:** Modern dark-mode styling with subtle backdrop filters and crisp typography.
  - **Fluid Responsiveness:** Adaptive layouts that scale seamlessly from ultra-wide monitors to compact mobile viewports.

- **🔒 Validated REST & API Gateways**
  - **Strict Typing:** End-to-end serialization schemas utilizing robust payload validation (e.g., JSON Schema / Zod).
  - **Automated Documentation:** Self-updating OpenAPI/Swagger specs generated directly from route controllers.
  - **Resilient Error Recovery:** Graceful degradation, circuit-breaker patterns, and standardized RFC 7807 error payloads.

- **🌐 Reactive Real-Time Client**
  - **Optimistic UI:** Instantaneous state updates on the client side with seamless background synchronization.
  - **Fast Hydration:** Server-side rendering (SSR) support for rapid initial page loads and optimal SEO.
  - **Layout Stability:** Zero Cumulative Layout Shift (CLS) architecture for a jank-free user experience.

- **🐳 Containerized Orchestration**
  - **Multi-Stage Builds:** Minimized production image footprints by separating build-time dependencies from runtime binaries.
  - **Unified Compose:** Pre-configured `docker-compose` stacks for local development, staging, and integration testing.
  - **Health Monitoring:** Built-in liveness and readiness probes for zero-downtime rolling deployments.

- **🛡️ Zero-Trust Security Posture**
  - **Rigid Sanitization:** Comprehensive input scrubbing to prevent SQL injection, XSS, and CSRF vectors.
  - **Secure Configuration:** Strict environment variable parsing with no hardcoded secrets or default credentials.
  - **Accessibility Compliance:** Fully audited against WCAG AAA contrast and keyboard navigation standards.
<details>
<summary>Click to expand</summary>

Add hidden detailed content, logs, or long outputs here.

</details>


<details>
<summary>Click to expand</summary>

Add hidden detailed content, logs, or long outputs here.

</details>


### 📊 Capability & Feature Matrix

| Module / Capability | Status | Target / Protocol | Scope & Architecture |
| :--- | :---: | :--- | :--- |
| **Core Processing Engine** | ✅ Active | Sub-millisecond Async | High-throughput asynchronous pipeline |
| **Reactive Web Client** | ✅ Active | React 18 / Vite HMR | Modern responsive interface with instant feedback |
| **REST API Gateway** | ✅ Active | OpenAPI 3.1 / Pydantic | Validated request/response serialization |
| **State & Cache Store** | ✅ Active | Redis / Memory Cache | Transient session state & distributed caching |
| **Containerized Deploy** | ✅ Active | Multi-Stage Docker | Optimized production builds under 150MB |

> [!NOTE]
> **Production-Ready & Actively Maintained**
> Seamlessly toggle between local development and containerized modes with unified environment variable flags.

## 🛠️ Tech Stack

- **Frontend & UI:** `JavaScript`
- **Backend & APIs:** `Python`, `FastAPI`
- **DevOps & Tooling:** `Docker`, `GitHub Actions`, `Vite`, `Pytest`

### 🛠️ Architecture Specification Matrix

| Technology | Layer | Role | Purpose & Implementation |
| :--- | :--- | :--- | :--- |
| `JavaScript` | Language | Production integration | High performance, typed architecture |
| `Python` | Language | Production integration | High performance, typed architecture |
| `Docker` | DevOps | Production integration | High performance, typed architecture |
| `GitHub Actions` | CI/CD | Production integration | High performance, typed architecture |
| `Vite` | Tooling | Production integration | High performance, typed architecture |
| `FastAPI` | Backend | Production integration | High performance, typed architecture |
| `Pytest` | Testing | Production integration | High performance, typed architecture |

## 🏗️ Project Structure

```
.
├── .github/
│   ├── workflows/
│   ├── dependabot.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── assets/
│   ├── logo.png
│   └── VisualMark Studio Banner.gif
├── backend/
│   ├── tests/
│   ├── app.py
│   ├── build_sidecar.py
│   ├── desktop_server.py
│   ├── Dockerfile
│   ├── main.py
│   ├── Procfile
│   ├── prompts.py
│   └── requirements.txt
├── frontend/
│   ├── electron/
│   ├── public/
│   ├── scripts/
│   ├── src/
│   ├── Dockerfile
│   ├── index.html
│   ├── package-lock.json
│   ├── package.json
│   └── vite.config.js
├── .env.example
├── .gitignore
├── CHANGELOG.md
├── DEPLOYMENT.md
├── DESIGN_SYSTEM.md
├── DESKTOP.md
├── docker-compose.yml
└── ... (additional repository files)
```

## 🚀 Getting Started

### Prerequisites

- **Node.js**: `v18.0.0+` (Recommended `v20+`) & **npm** `v9.0.0+`
- **Python**: `3.10+` (Recommended `3.11+`) & **pip**
- **Docker Engine**: `v24.0+` & **Docker Compose**

### Quick Start

```bash
# [zsh — 80×24]
$ git clone https://github.com/JagaTheGhost/visualmark-studio.git && cd visualmark-studio
➜ Verifying runtime prerequisites (Node.js / Python)... Done
✓ Repository cloned and ready for package installation.
```

#### Dependency Installation Across Package Managers

<details open>
<summary><b>npm & pip (Standard)</b></summary>

```bash
# 1. Setup backend virtual environment & dependencies
cd backend && pip install -r requirements.txt

# 2. Setup frontend dependencies
cd ../frontend && npm install
```

</details>

<details>
<summary><b>pnpm & uv (High-Speed)</b></summary>

```bash
# 1. Fast backend sync with uv
cd backend && uv pip install -r requirements.txt

# 2. Fast frontend sync with pnpm
cd ../frontend && pnpm install
```

</details>

<details>
<summary><b>bun & poetry</b></summary>

```bash
# 1. Backend with poetry
cd backend && poetry install

# 2. Frontend with bun
cd ../frontend && bun install
```

</details>

> [!IMPORTANT]
> Always duplicate `.env.example` into `.env` and fill in necessary API credentials before starting development services.

## 📖 Usage

```bash
# Terminal 1: Launch API Backend Service
cd backend && python -m uvicorn app:app --reload --port 8000

# Terminal 2: Launch Web Frontend Client
cd frontend && npm run dev
```

1. **Launch the development servers** using the multi-service command sequence above.
2. **Open the client application** at `http://localhost:3000` (or `http://localhost:8000`).
3. **Experience live synchronization** via automated hot module reloading.

### ⌨️ Keycaps & Global Keyboard Shortcuts

| Shortcut | Action | Scope |
| :--- | :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>K</kbd> / <kbd>⌘</kbd> + <kbd>K</kbd> | Open Global Command Palette | Global Application |
| <kbd>Ctrl</kbd> + <kbd>S</kbd> / <kbd>⌘</kbd> + <kbd>S</kbd> | Save Active Document & State | Editor Workspace |
| <kbd>Ctrl</kbd> + <kbd>Enter</kbd> | Trigger Autonomous Execution | Action Runner |
| <kbd>Shift</kbd> + <kbd>Alt</kbd> + <kbd>F</kbd> | Format Code & Markdown | Active File |

### 📡 Interactive API Documentation

- **Swagger UI:** Visit `http://localhost:8000/docs` to test all endpoints interactively.
- **ReDoc Console:** Visit `http://localhost:8000/redoc` for detailed OpenAPI specifications.

## ⚙️ Configuration

Create a `.env` file in the root directory:

```env
# Local server HTTP listening port # [Required]
PORT=8000

# Runtime mode (`development` | `production`) # [Required]
NODE_ENV=development

# Cryptographic signing and session JWT secret # [Required]
SECRET_KEY=your_super_secret_key_here

# Verbosity level (`debug`, `info`, `warn`, `error`) # [Optional]
LOG_LEVEL=info
```

### ⚙️ Environment Specification Table

| Variable | Type | Default | Requirement | Description |
| :--- | :--- | :--- | :--- | :--- |
| `PORT` | `number` | `8000` | ✅ Required | Local server HTTP listening port |
| `NODE_ENV` | `string` | `development` | ✅ Required | Runtime mode (`development` | `production`) |
| `SECRET_KEY` | `string` | `your_super_secret_key_here` | ✅ Required | Cryptographic signing and session JWT secret |
| `LOG_LEVEL` | `string` | `info` | ⚪ Optional | Verbosity level (`debug`, `info`, `warn`, `error`) |

> [!CAUTION]
> **Security Advisory: Protect Credentials**
> Never commit production secrets, database credentials, or API keys to version control. Maintain private parameters in `.env.local`.

## 🏛️ Architecture

### 🏛️ System Topology & Component Matrix

| Layer | Component Identifier | Technology | Protocol / Transport | Architectural Boundary |
| :--- | :--- | :--- | :--- | :--- |
| **Presentation Layer** | `Client["Web Client (Web Client)"]` | Responsive SPA / SSR | `|"HTTPS / REST"|` | Client state hydration, optimistic rendering |
| **API Gateway Layer** | `API["API Gateway (FastAPI Service)"]` | Asynchronous Service | OpenAPI / HTTP 1.1 & 2 | Route dispatching, serialization & auth tokens |
| **Persistence Layer** | `DB["Data Store (Database)"]` | Relational Storage | TCP / Connection Pool | ACID transactions, indexed models & migrations |
| **State & Cache Layer** | `Cache["State Cache (Redis)"]` | In-Memory Cache | Binary Socket Protocol | Session storage, rate limits & 300s TTL cache |

### 🔄 Dataflow & Pipeline Execution

| Stage | Source | Destination | Transport | Payload Type | Caching Policy |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Client Request** | `Client["Web Client"]` | `API["API Gateway"]` | `|"HTTPS / REST"|` | JSON Payload | No-Store / ETag |
| **Authentication** | `API["API Gateway"]` | Session Cache | Memory Query | Bearer Token | In-Memory Token Verify |
| **Data Query** | `API["API Gateway"]` | Database Store | Pooled Connection | Parameterized SQL | Query Result Caching |
| **Response Pipeline**| `API["API Gateway"]` | Client Browser | HTTP 200 OK | Serialized JSON | Client SWR Cache |

- **Decoupled Architecture:** Presentation logic is strictly isolated from core domain rules.
- **Stateless Compute:** Backend workers scale horizontally behind reverse proxies without session lock-in.
- **Predictable Data Contracts:** Strictly typed Pydantic and TypeScript definitions eliminate runtime boundary mismatches.

## 🧪 Testing

```bash
# Run backend test suite with coverage
pytest -v --cov=.

# Run frontend unit & integration tests
npm test
```

### 🧪 Testing Strategy Matrix

| Test Suite | Runner / Framework | Target Scope | Coverage Target |
| :--- | :--- | :--- | :--- |
| **Unit Tests** | `pytest` / `vitest` | Pure functions, models, utility helpers | 90%+ code coverage |
| **Integration Tests** | `pytest-asyncio` / `supertest` | Route handlers, auth middleware, DB transactions | All critical workflows |
| **Lint & Formatting** | `ruff` / `eslint` / `prettier` | Syntax conformance & type-checking | 0 lint warnings |

## 🔧 Troubleshooting

<details>
<summary><b>Q: Port 8000 or 3000 is already in use?</b></summary>

Terminate any orphaned processes occupying the port:

```bash
# macOS / Linux
lsof -ti:8000 | xargs kill -9

# Windows PowerShell
Get-Process -Id (Get-NetTCPConnection -LocalPort 8000).OwningProcess | Stop-Process
```

</details>

<details>
<summary><b>Q: Database connection refused or timeout?</b></summary>

Ensure your local PostgreSQL service or Docker container is healthy:

```bash
docker compose ps
docker compose up -d postgres
```

</details>

<details>
<summary><b>Q: Dependencies failing or corrupted lockfile?</b></summary>

Purge local lockfiles and perform a clean installation:

```bash
# Node.js / Frontend
rm -rf node_modules package-lock.json && npm install

# Python / Backend
pip install --no-cache-dir -r requirements.txt
```

</details>

> [!TIP]
> Enable verbose logs by running with `LOG_LEVEL=debug` or appending `--verbose` to any CLI command.

## 🚢 Deployment

### ☁️ One-Click Cloud Deployments

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new) &nbsp; [![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com)

### 🐳 Multi-Stage Docker Deployment

```bash
# Build and launch all services in detached container mode
docker compose up --build -d

# Inspect container cluster status
docker compose ps
```

## 🤝 Contributing & License

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

### 📝 Conventional Commits Reference

| Type | Badge | Scope & Description |
| :--- | :--- | :--- |
| `feat` | `![Feat](https://img.shields.io/badge/-Feature-007ACC?style=flat-square)` | New user-facing feature or enhancement |
| `fix` | `![Fix](https://img.shields.io/badge/-Fix-E05D44?style=flat-square)` | Bug fix or patch |
| `docs` | `![Docs](https://img.shields.io/badge/-Docs-4C1?style=flat-square)` | Documentation adjustments only |
| `refactor` | `![Refactor](https://img.shields.io/badge/-Refactor-9B59B6?style=flat-square)` | Code change without behavioral change |
| `test` | `![Test](https://img.shields.io/badge/-Test-00C7B7?style=flat-square)` | Adding or fixing test suites |
| `chore` | `![Chore](https://img.shields.io/badge/-Chore-7F8C8D?style=flat-square)` | Maintenance tasks, deps, and build tooling |

> [!TIP]
> Please review [CONTRIBUTING.md](CONTRIBUTING.md) for details on code of conduct and pull request etiquette.

### 📄 License

Distributed under the **MIT License**. See [`LICENSE`](./LICENSE) for full details.

Copyright (c) 2026 JagaTheGhost. All rights reserved.
