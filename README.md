# Homelab

Production-style self-hosted homelab running on Ubuntu Server 24.04.

## Core Structure

*   **apps/**: End-user applications and productivity tools (Nextcloud, Docmost, n8n, etc.)
*   **databases/**: Standalone core database engines and caches (PostgreSQL, Redis)
*   **infra/**: Gateway routers, portals, reverse-proxies, and VPN connectors (Traefik, Cloudflared, Portainer, Homepage)
*   **monitoring/**: Metrics, alert rules, dashboards, and system monitoring (Prometheus, Grafana, Uptime Kuma)

---

## Folder Layout

```text
homelab/
│
├── README.md
├── plan.md
├── .env                  # Single unified git-ignored env file for all stacks
│
├── apps/
│   ├── code-server/      # VS Code Remote IDE
│   ├── docmost/          # Collaborative wiki platform
│   ├── n8n/              # Workflow automation engine
│   ├── nextcloud/        # Personal Cloud file storage
│   ├── open-webui/       # AI chat interface
│   └── vaultwarden/      # Secure password manager
│
├── databases/
│   ├── postgres/         # Shared PostgreSQL database
│   └── redis/            # Standalone shared Redis caching
│
├── infra/
│   ├── cloudflared/      # Cloudflare Tunnel for secure edge connectivity
│   ├── homepage/         # Portal Dashboard
│   ├── portainer/        # Docker GUI administrator
│   ├── traefik/          # Main Edge Reverse Proxy
│   └── twingate/         # Secure zero-trust VPN connector
│
├── monitoring/
│   ├── grafana/          # Telemetry and logging visualizer
│   ├── prometheus/       # System metrics scraper
│   └── uptime-kuma/      # Uptime monitors & status reporting
│
├── data/                 # Dynamic persistent application databases and volumes
└── scripts/              # Local utilities and automation scripts
```

## Setup & Deployment

Every compose stack is configured to uniformly load environment variables from the single root `.env` file via relative configuration paths (`../../.env`).

To start any stack independently, navigate to its directory and run:

```bash
docker compose up -d
```

Or run directly from the workspace root specifying the unified env file:

```bash
docker compose --env-file .env -f apps/nextcloud/docker-compose.yml up -d
```
