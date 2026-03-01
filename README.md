# Toparius — Network Topology Manager for MSPs

Toparius discovers, maps, and monitors your network infrastructure. Built for managed service providers who need visibility across multiple client environments.

## What It Does

- **Auto-discovery** — Infrastructure-first discovery: SNMP-walks routers/switches first, then recursively crawls CDP/LLDP neighbors, harvests ARP/MAC/route tables, and optionally ping-sweeps endpoints; passive listeners for ARP, mDNS, SSDP, and DHCP
- **Topology mapping** — Interactive network maps with auto-layout (hierarchical, radial, force-directed), global multi-site map, alert overlays, STP visualization, and VLAN grouping
- **Monitoring** — SNMP polling for CPU, memory, interface stats, uptime; SNMP trap receiver; syslog collector; real-time WebSocket updates
- **Alerting** — Threshold-based alert rules with email, Slack, Discord, Teams, webhook, and PSA ticket creation; alert library with pre-built templates
- **Credential management** — Centralized SNMP v1/v2c/v3 and SSH credential vault with scoped assignment (global, site, network), automated device testing, and per-device verification status
- **Multi-tenant** — Client/site/network hierarchy with RBAC (admin, manager, technician, viewer, client_admin) and scoped client portal
- **Integrations** — UniFi controller, Tactical RMM, HaloPSA, ConnectWise Manage
- **IPAM** — IP address tracking per subnet with conflict detection, utilization metrics, and reservations
- **Config backup** — SSH-based device config backup with change detection, diff comparison, and scheduled backups
- **Device Knowledge Base** — 65,000+ device profiles from IANA enterprise OIDs; auto-classifies devices by sysObjectID and sysDescr; self-healing device types on re-scan
- **Reports & SLA** — Scheduled PDF/CSV reports, uptime tracking, SLA compliance per client
- **Documentation** — Built-in documentation wiki per client/site with Markdown support
- **Agent-based** — Lightweight agents deployed per site with auto-update, Windows service support, and one-line installer

## Architecture

```
┌─────────────────────────────────────────┐
│           Toparius Server               │
│  REST API · Web UI · Alert Engine       │
│  SQLite or PostgreSQL                   │
└────────────────┬────────────────────────┘
                 │ HTTPS
        ┌────────┼────────┐
        │        │        │
   ┌────▼──┐ ┌──▼────┐ ┌─▼─────┐
   │ Agent │ │ Agent │ │ Agent │
   │Site A │ │Site B │ │Site C │
   └───────┘ └───────┘ └───────┘
```

**Server**: Go binary with embedded React frontend. Single binary, zero runtime dependencies. Hosts the web UI, REST API, alert engine, and database. Runs on Linux (amd64, armv7).

**Agent**: Lightweight Go binary deployed to each site. Discovers devices, polls SNMP metrics, and reports back to the server over HTTPS. Auto-updates from the server. Runs on Linux (amd64, armv7) and Windows (installed as a service).

---

## Install

### Requirements

- **Server OS**: Ubuntu/Debian (amd64 or armv7)
- **Agent OS**: Linux (amd64, armv7) or Windows (amd64)
- **Server**: 1 CPU, 512 MB RAM minimum
- **Agent**: Minimal — runs on any Linux box or Windows machine at the site
- **Database**: SQLite (default, zero-config) or PostgreSQL
- **Network**: Agent needs ICMP and SNMP access to target subnets; server needs to be reachable from agents on port 8080 (default, HTTPS)

### Option 1: `.deb` Packages (Recommended)

Download the latest `.deb` packages from [Releases](https://github.com/DiAhman-Contracting/Toparius-Official/releases).

**Server:**

```bash
# Download and install (use _armhf.deb for Raspberry Pi / ARM devices)
wget https://github.com/DiAhman-Contracting/Toparius-Official/releases/latest/download/toparius-server_amd64.deb
sudo dpkg -i toparius-server_amd64.deb

# Edit config (change jwt_secret!)
sudo nano /etc/toparius/toparius-server.yaml

# Start
sudo systemctl enable --now toparius-server

# Open https://your-server:8080 and complete the setup wizard
```

**Agent (Linux):**

```bash
# Download and install (use _armhf.deb for Raspberry Pi / ARM devices)
wget https://github.com/DiAhman-Contracting/Toparius-Official/releases/latest/download/toparius-agent_amd64.deb
sudo dpkg -i toparius-agent_amd64.deb

# Edit config (set server URL and API key from the server UI)
sudo nano /etc/toparius/toparius-agent.yaml

# Start
sudo systemctl enable --now toparius-agent
```

**Agent (Windows):**

Download the Windows installer from the server UI (Agents page), or use the one-line deploy command.

Or use the **one-line deploy** from the Toparius server UI — go to Agents, create an agent, and copy the install command. Supports Linux (amd64, armv7) and Windows.

### Option 2: Docker

```bash
# Pull images
docker pull ghcr.io/diahman-contracting/toparius-server:latest
docker pull ghcr.io/diahman-contracting/toparius-agent:latest

# Or use docker-compose (download from this repo)
wget https://raw.githubusercontent.com/DiAhman-Contracting/Toparius-Official/main/docker/docker-compose.yml
wget https://raw.githubusercontent.com/DiAhman-Contracting/Toparius-Official/main/docker/toparius-server.yaml
wget https://raw.githubusercontent.com/DiAhman-Contracting/Toparius-Official/main/docker/toparius-agent.yaml

docker compose up -d
```

> **Note**: The agent container requires `network_mode: host` and `CAP_NET_RAW` for ICMP/SNMP discovery on the local network.

---

## Configuration

### Server (`/etc/toparius/toparius-server.yaml`)

```yaml
server:
  host: "0.0.0.0"
  port: 8080

database:
  driver: "sqlite"              # or "postgres"
  dsn: "/var/lib/toparius/toparius.db"

auth:
  # CHANGE THIS — generate with: openssl rand -hex 32
  jwt_secret: "change-me-in-production"
  access_token_ttl: "15m"
  refresh_token_ttl: "168h"

security:
  rate_limit_rps: 20
  rate_limit_burst: 40

# TLS mode: "auto" (self-signed cert, default), "manual" (your own cert), "off" (HTTP only)
tls:
  mode: "auto"
  # For manual mode, uncomment and set paths:
  # cert_file: "/etc/toparius/tls/cert.pem"
  # key_file: "/etc/toparius/tls/key.pem"

log:
  level: "info"
  format: "text"
```

Environment variables override config with the `TOPARIUS_` prefix (e.g., `TOPARIUS_SERVER_PORT=9090`).

### Agent (`/etc/toparius/toparius-agent.yaml`)

```yaml
server:
  url: "https://your-server:8080"
  api_key: ""  # from Toparius server UI

# Skip TLS verification (required when server uses self-signed cert)
tls_skip_verify: true

agent:
  site_id: ""  # assigned during registration
  discovery_interval: "1h"
  monitor_interval: "5m"

update:
  enabled: true

log:
  level: "info"
```

---

## Upgrading

**`.deb` packages:**

```bash
# Download the new version and install over the existing one
sudo dpkg -i toparius-server_amd64.deb
sudo systemctl restart toparius-server
```

Agents auto-update from the server when a new version is available. The server `.deb` bundles the matching agent binary.

**Docker:**

```bash
docker compose pull
docker compose up -d
```

---

## Getting Started

1. Install the server and open `https://your-server:8080` (HTTPS with auto-generated certificate by default)
2. Complete the setup wizard (creates admin account, optionally configures PostgreSQL)
3. Create a Client > Site > Network in the hierarchy
4. Create an agent and deploy it to the site using the one-line installer
5. The agent auto-discovers devices on the network and reports back
6. View your topology map, configure monitoring thresholds, set up credential tests, and enable alerts

---

## Support & Feedback

- **Issues**: [GitHub Issues](https://github.com/DiAhman-Contracting/Toparius-Official/issues)
- **Email**: contact@di-ahman.com

---

## License

Toparius is proprietary software. Copyright (c) 2024-2026 DiAhman Contracting, LLC. All rights reserved.

See [THIRD-PARTY-LICENSES](THIRD-PARTY-LICENSES) for open-source dependency attribution.
