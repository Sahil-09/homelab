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
* RAM: 8GB
* Storage: 1 TB
* Network: Airtel Xstream Fiber
* Static LAN IP: 192.168.1.50

## Operating System

* Ubuntu Live Server
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
* [x] Dashboard Route

---

## Cloudflared

Purpose:

* Secure Remote Access
* Zero Open Ports

Status:

* [x] Installed
* [x] Tunnel Created
* [x] Wildcard Route Configured
* [x] Final Validation

---

## Portainer

Purpose:

* Docker Management

Status:

* [x] Installed
* [x] Traefik Route Validation

---

## Code Server

Purpose:

* Remote VS Code

Status:

* [x] Installed
* [x] GitHub Login
* [x] NodeJS
* [x] pnpm
* [x] Nest CLI
* [x] Angular CLI

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

* [x] Installed

---

## Prometheus

Purpose:

* Metrics Collection

Status:

* [x] Installed

---

## Node Exporter

Purpose:

* CPU
* RAM
* Disk
* Network Monitoring

Status:

* [x] Installed

---

## cAdvisor

Purpose:

* Docker Metrics

Status:

* [x] Installed

---

## Grafana

Purpose:

* Dashboards
* Alerting

Status:

* [x] Installed

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

* [x] Installed

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

* [x] Installed

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

* [x] Installed

---

# AI Platform

## Ollama

Purpose:

* Local LLM Runtime

Status:

* [ ] Skipped (Using Free Cloud APIs to save CPU/RAM)

---

## Open WebUI

Purpose:

* Self-hosted ChatGPT

Status:

* [x] Installed

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

1. [x] Fix Portainer Traefik Routing
2. [x] Validate Wildcard Tunnel
3. [x] Install NodeJS via NVM
4. [x] Install pnpm
5. [x] Install Homepage Dashboard
6. [x] Install Uptime Kuma
7. [x] Install Prometheus
8. [x] Install Grafana
9. [x] Install n8n
10. [x] Install Nextcloud
11. [ ] Configure Grafana System Alerting
12. [ ] Install Wiki.js (Documentation)
13. [ ] Install Loki (Centralized Logs)
14. [ ] Install Immich (Photo Backup)

Target Outcome:

A fully remote-accessible personal cloud and development environment managed through Docker, Traefik, Cloudflare Tunnel, and Code Server.
