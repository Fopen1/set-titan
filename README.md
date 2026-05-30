# TITAN NET X

Enterprise network operations platform for Windows — discovery, monitoring, security, packet analysis, and AI-driven insights in a unified SOC-style interface.

## Features (MVP + Roadmap)

- **Global scanning** — ARP, ICMP, TCP port discovery, SNMP, vendor/OS fingerprinting
- **3D network map** — real-time topology with WebGL (Three.js)
- **Security center** — ARP spoof, rogue DHCP, brute-force heuristics, anomaly alerts
- **Packet analyzer** — live capture pipeline (Npcap required on Windows)
- **Monitoring** — device metrics, bandwidth, latency graphs
- **AI engine** — anomaly scoring and operational recommendations
- **Enterprise** — JWT auth, RBAC, audit logs, LDAP-ready hooks

## Requirements

- Windows 10/11 or Windows Server 2019+
- Python 3.11+
- Node.js 20+
- Rust 1.75+ (for Tauri build)
- [Npcap](https://npcap.com/) (for packet capture)
- Optional: PostgreSQL 15+, Redis 7+

## Quick Start

### 1. Backend

```powershell
cd backend
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
copy .env.example .env
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Default login: `admin` / `TitanNetX2026!` (change in production)

### 2. Frontend (development)

```powershell
cd frontend
npm install
npm run dev
```

API proxy: `http://127.0.0.1:8000`

### 3. Desktop app (Tauri)

```powershell
cd frontend
npm run tauri build
```

### 4. Docker (full stack)

```powershell
docker compose up -d
```

## Project Structure

```
titan-net-x/
├── core/           # Rust performance engine
├── backend/        # FastAPI application
├── scanner/        # Network discovery engine
├── security/       # IDS and threat detection
├── ai/             # ML anomaly and recommendations
├── monitoring/     # Metrics collectors
├── packet_engine/  # Capture and protocol analysis
├── database/       # Shared schemas and migrations
├── frontend/       # Tauri + React UI
├── api/            # OpenAPI and proto definitions
├── installer/      # Windows installer scripts
├── tests/          # Integration and unit tests
└── docs/           # Architecture and guides
```

## Documentation

- [Architecture](docs/ARCHITECTURE.md)
- [API Reference](docs/API.md)
- [Security](docs/SECURITY.md)
- [Deployment](docs/DEPLOYMENT.md)

## License

Proprietary — TITAN NET X © 2026
