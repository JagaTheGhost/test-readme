
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:6366f1,70:3b82f6,100:10b981&height=220&section=header&text=visualmark-studio&fontSize=42&fontAlignY=36&desc=Modern%20Code%20%2B%20Visual%20Desktop%20IDE%20for%20Markdown%20authoring%2C%20Mermaid%20diagramming%2C%20and%20com&descAlignY=60&descAlign=50" width="100%" alt="visualmark-studio Banner" />
</p>

# visualmark-studio

> **Modern Code + Visual Desktop IDE for Markdown authoring, Mermaid diagramming, and complete documentation suites.**

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=0969da)](https://github.com/JagaTheGhost/visualmark-studio/stargazers) [![GitHub Forks](https://img.shields.io/github/forks/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=0969da)](https://github.com/JagaTheGhost/visualmark-studio/network/members) [![Issues](https://img.shields.io/github/issues/JagaTheGhost/visualmark-studio?style=for-the-badge&logo=github&color=e11d48)](https://github.com/JagaTheGhost/visualmark-studio/issues) [![License](https://img.shields.io/badge/License-MIT-10b981.svg?style=for-the-badge)](https://github.com/JagaTheGhost/visualmark-studio/blob/main/LICENSE)
<br/>
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=FFD62E) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white) ![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

</div>

<div align="center">

[🚀 Getting Started](#getting-started) &nbsp;•&nbsp; [✨ Features](#features) &nbsp;•&nbsp; [🛠️ Tech Stack](#tech-stack) &nbsp;•&nbsp; [🏛️ Architecture](#architecture) &nbsp;•&nbsp; [📖 Usage](#usage) &nbsp;•&nbsp; [⚙️ Configuration](#configuration) &nbsp;•&nbsp; [🔧 Troubleshooting](#troubleshooting) &nbsp;•&nbsp; [🤝 Contributing](#contributing)

</div>

## ✨ Features

- **Zero-Latency AST & Diagnostics:** Real-time incremental syntax parsing with deterministic error boundaries and diagnostic reporting.
- **Multi-Pane Visual Workspace:** Decoupled split-view synchronization pairing code editor buffers with live reactive previews.
- **Local-First Offline Architecture:** Direct native filesystem I/O without cloud dependency, telemetry leakage, or network latency.
- **Containerized Orchestration:** Production-ready multi-stage Docker builds and unified compose configurations for reproducible dev/prod parity.
- **Asynchronous Concurrency:** Non-blocking async event loop execution maximizing single-instance throughput.
- **Automated QA Test Suite:** High-coverage unit, integration, and regression test suites with continuous CI verification.

## 🛠️ Tech Stack

`JavaScript` | `Python` | `Docker` | `GitHub Actions` | `Vite` | `FastAPI` | `Pytest`

## 🏗️ Project Structure

```
.
├── .env.example
├── .github
│   ├── ISSUE_TEMPLATE
│   │   ├── bug_report.yml
│   │   ├── config.yml
│   │   └── feature_request.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   ├── dependabot.yml
│   └── workflows
│       ├── ci.yml
│       ├── release.yml
│       └── security-scan.yml
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── DEPLOYMENT.md
├── DESIGN_SYSTEM.md
├── DESKTOP.md
├── DOCUMENTATION.md
├── EXAMPLE_OUTPUT.md
├── FEATURES.md
├── LICENSE
├── README.md
├── SECURITY.md
├── SETUP.md
├── TESTING_GUIDE.md
├── assets
│   ├── VisualMark Studio Banner.gif
│   ├── logo.png
│   └── visualmark-studio-card.svg
├── backend
│   ├── Dockerfile
│   ├── Procfile
```

## 🚀 Getting Started

### Prerequisites

- **Python**: `3.10+` (Recommended via `pyenv` or `conda`)
- **Node.js**: `18.0.0+` (LTS) & `npm` `9.0+` (or `pnpm` / `bun`)
- **Docker Engine**: `24.0+` & **Docker Compose**: `v2.20+`

### Quick Start

```bash
# 1. Clone working repository
$ git clone https://github.com/JagaTheGhost/visualmark-studio.git
$ cd visualmark-studio

# 2. Configure & initialize backend runtime
$ cd backend
$ python -m venv .venv
# Windows: .\.venv\Scripts\Activate.ps1 | macOS/Linux: source .venv/bin/activate
$ pip install --upgrade pip
$ pip install -r requirements.txt
$ cp .env.example .env
$ cd ..

# 3. Configure & initialize frontend client
$ cd frontend
$ npm install
$ cd ..
```

## 📖 Usage

```bash
# Terminal 1: Launch Backend API
$ cd backend && uvicorn app:app --reload --port 8000

# Terminal 2: Launch Frontend Client
$ cd frontend && npm run dev
```

> [!TIP]
> Access the live client application in your browser at `http://localhost:5173` or `http://localhost:3000`.

## ⚙️ Configuration

```env
# Server Configuration
PORT=8000
ENV=development
LOG_LEVEL=info
DATABASE_URL=sqlite:///./data.db
VITE_API_BASE_URL=http://localhost:8000
```

### ⚙️ Environment Parameters Specification

| Environment Variable | Description | Default | Required |
| :--- | :--- | :--- | :--- |
| `PORT` | Local network binding port | `8000` | No |
| `ENV` | Execution environment (`development` / `production`) | `development` | Yes |
| `LOG_LEVEL` | Logging verbosity (`debug`, `info`, `warn`, `error`) | `info` | No |
| `DATABASE_URL` | Primary persistent datastore connection URI | *Local URI* | Yes |

## 🏛️ Architecture

### 🏛️ System Topology & Component Matrix

| Layer | Component Identifier | Technology | Protocol / Transport | Architectural Boundary |
| :--- | :--- | :--- | :--- | :--- |
| **Presentation Layer** | `Client["Web Client (Web Client (React / Vite))"]` | Responsive Client Interface | `|"HTTPS / REST"|` | Client state hydration, optimistic rendering |
| **API Gateway Layer** | `API["API Gateway (API Gateway (FastAPI))"]` | Asynchronous Service Engine | OpenAPI / HTTP 1.1 & 2 | Route dispatching, serialization & auth tokens |
| **Persistence Layer** | `DB["Data Store (Data Store (PostgreSQL))"]` | Persistent Storage Engine | TCP / Connection Pool | ACID transactions, indexed models & migrations |
| **State & Cache Layer** | `Cache["State Cache (Redis)"]` | In-Memory Cache Store | Binary Socket Protocol | Session storage, rate limits & 300s TTL cache |

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
# Run backend test suite with coverage report
$ pytest -v --cov=.

# Run frontend test suite
$ npm test
```

### 🧪 Testing Strategy Matrix

| Test Suite | Runner / Framework | Target Scope | Coverage Target |
| :--- | :--- | :--- | :--- |
| **Unit Tests** | `pytest` / `vitest` | Pure functions, models, utility helpers | 90%+ code coverage |
| **Integration Tests** | `pytest-asyncio` / `supertest` | Route handlers, auth middleware, DB transactions | All critical workflows |
| **Lint & Formatting** | `ruff` / `eslint` / `prettier` | Syntax conformance & type-checking | 0 lint warnings |

## 🔧 Troubleshooting

<details>
<summary><b>Q: Port 8000 or 3000 is already occupied?</b></summary>

Terminate any orphaned processes holding the local socket:

```bash
# macOS / Linux
lsof -ti:8000 | xargs kill -9

# Windows PowerShell
Get-Process -Id (Get-NetTCPConnection -LocalPort 8000).OwningProcess | Stop-Process
```

</details>

<details>
<summary><b>Q: Database connection refused or connection timeout?</b></summary>

Verify your local database service or Docker container is healthy:

```bash
docker compose ps
docker compose up -d
```

</details>

<details>
<summary><b>Q: Corrupted dependencies or lockfile desynchronization?</b></summary>

Perform a clean purge and fresh install:

```bash
# Node.js
rm -rf node_modules package-lock.json && npm install

# Python
pip install --force-reinstall -r requirements.txt
```

</details>

> [!TIP]
> Append `--verbose` or run with `LOG_LEVEL=debug` to output granular stack traces.

## 🚢 Deployment

### ☁️ Instant Cloud Deployment

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new) &nbsp; [![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com)

### 🐳 Multi-Stage Docker Containerization

```bash
# Build images and launch services in background
$ docker compose up --build -d

# Inspect cluster runtime status
$ docker compose ps
```

## 🤝 Contributing & License

Contributions are what make the open-source community an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

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