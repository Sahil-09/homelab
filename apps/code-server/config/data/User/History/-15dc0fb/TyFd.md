# HomeLab Master Plan

## Goal

Build a self-hosted development and automation platform on an old laptop that provides:

* Remote Development Environment
* Personal Cloud
* Monitoring & Observability
* AI & Automation Platform
* Backup & Disaster Recovery
* Self-hosted Alternatives to SaaS Tools

---

# Current Infrastructure

## Hardware

* Host: Old Laptop
* RAM: TBD
* Storage: TBD
* Network: Airtel Xstream Fiber
* Static LAN IP: 192.168.1.4

## Operating System

* Linux Mint
* Docker Engine
* Docker Compose

---

# Network Architecture

Internet
↓
Cloudflare DNS
↓
Cloudflare Tunnel
↓
Traefik Reverse Proxy
↓
Docker Services

---

# Domain Strategy

Wildcard Tunnel:

```text
*.patelsahil.in
```

Cloudflare Tunnel Target:

```text
HTTP
traefik:80
```

---

# Service Domains

## Infrastructure

```text
portainer.patelsahil.in
traefik.patelsahil.in
uptime.patelsahil.in
grafana.patelsahil.in
```

## Development

```text
code.patelsahil.in
gitea.patelsahil.in
registry.patelsahil.in
```

## Productivity

```text
nextcloud.patelsahil.in
wiki.patelsahil.in
```

## Media

```text
immich.patelsahil.in
```

## Automation

```text
n8n.patelsahil.in
```

## AI

```text
ai.patelsahil.in
ollama.patelsahil.in
openwebui.patelsahil.in
```

---

# Folder Structure

```text
/home/kraddy/homelab

├── infra
│   ├── traefik
│   ├── cloudflared
│   └── homepage
│
├── services
│   ├── code-server
│   ├── portainer
│   ├── gitea
│   ├── nextcloud
│   ├── immich
│   ├── n8n
│   ├── uptime-kuma
│   ├── grafana
│   ├── prometheus
│   ├── loki
│   ├── wiki
│   ├── open-webui
│   └── ollama
│
├── data
│   ├── postgres
│   ├── redis
│   ├── rabbitmq
│   └── backups
│
├── logs
│
├── scripts
│
└── docs
```

---

# Development Workspace

```text
/home/kraddy/dev
```

## Repositories

```text
/home/kraddy/dev

├── personal
├── veenaworld
├── experiments
├── mobile
├── automation
└── learning
```

Code Server default workspace:

```text
/home/kraddy/dev
```

---

# Core Infrastructure

## Traefik

Purpose:

* Reverse Proxy
* Service Discovery
* Routing

Status:

* [x] Installed
* [x] Docker Provider
* [x] Cloudflare Integration
* [ ] Dashboard Route

---

## Cloudflared

Purpose:

* Secure Remote Access
* Zero Open Ports

Status:

* [x] Installed
* [x] Tunnel Created
* [x] Wildcard Route Configured
* [ ] Final Validation

---

## Portainer

Purpose:

* Docker Management

Status:

* [x] Installed
* [ ] Traefik Route Validation

---

## Code Server

Purpose:

* Remote VS Code

Status:

* [x] Installed
* [x] GitHub Login
* [ ] NodeJS
* [ ] pnpm
* [ ] Nest CLI
* [ ] Angular CLI

---

# Monitoring Stack

## Uptime Kuma

Purpose:

* Uptime Monitoring
* SSL Monitoring
* Alerts

Priority:

HIGH

Status:

* [ ] Pending

---

## Prometheus

Purpose:

* Metrics Collection

Status:

* [ ] Pending

---

## Node Exporter

Purpose:

* CPU
* RAM
* Disk
* Network Monitoring

Status:

* [ ] Pending

---

## cAdvisor

Purpose:

* Docker Metrics

Status:

* [ ] Pending

---

## Grafana

Purpose:

* Dashboards
* Alerting

Status:

* [ ] Pending

---

## Loki

Purpose:

* Centralized Logs

Status:

* [ ] Pending

---

# Data Services

## PostgreSQL 17

Purpose:

* Primary Database

Status:

* [ ] Pending

---

## Redis

Purpose:

* Cache
* Pub/Sub

Status:

* [ ] Pending

---

## RabbitMQ

Purpose:

* Queue Processing

Status:

* [ ] Pending

---

# Productivity Platform

## Nextcloud

Purpose:

* Google Drive Alternative
* Calendar
* Contacts
* Notes
* Documents

Priority:

HIGH

Status:

* [ ] Pending

---

## Wiki.js

Purpose:

* Documentation
* SOPs
* Technical Notes

Status:

* [ ] Pending

---

# Automation Platform

## n8n

Purpose:

* AI Workflows
* Company Automations
* WhatsApp Flows
* YouTrack Automation

Priority:

HIGH

Status:

* [ ] Pending

---

# AI Platform

## Ollama

Purpose:

* Local LLM Runtime

Status:

* [ ] Pending

---

## Open WebUI

Purpose:

* Self-hosted ChatGPT

Status:

* [ ] Pending

---

# Media Platform

## Immich

Purpose:

* Google Photos Alternative

Status:

* [ ] Pending

---

# Security

## Cloudflare Access

Protect:

* Portainer
* Grafana
* Code Server
* Gitea

Status:

* [ ] Pending

---

## Fail2Ban

Status:

* [ ] Pending

---

## Automated Updates

Status:

* [ ] Pending

---

# Backup Strategy

## Daily

* PostgreSQL Dump
* Gitea Backup
* n8n Backup

## Weekly

* Nextcloud Backup
* Immich Backup

## Monthly

* Full Docker Volume Backup

Destination:

* External HDD
* Cloud Storage

---

# Future Roadmap

## Phase 2

* Authentik SSO
* Docker Registry
* GitHub Actions Runner

## Phase 3

* Paperless-NGX
* Home Assistant
* WireGuard VPN

## Phase 4

* MCP Servers
* Vector Database
* AI Agents

---

# Immediate Next Tasks

1. Fix Portainer Traefik Routing
2. Validate Wildcard Tunnel
3. Install NodeJS via NVM
4. Install pnpm
5. Install Homepage Dashboard
6. Install Uptime Kuma
7. Install Prometheus
8. Install Grafana
9. Install Gitea
10. Install n8n

Target Outcome:

A fully remote-accessible personal cloud and development environment managed through Docker, Traefik, Cloudflare Tunnel, and Code Server.
