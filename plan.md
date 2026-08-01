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
home.patelsahil.in
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
vault.patelsahil.in
```

## Automation

```text
n8n.patelsahil.in
```

## AI

```text
ai.patelsahil.in
```

---

# Folder Structure

```text
/home/kraddy/homelab

├── apps
│   ├── code-server
│   ├── docmost
│   ├── n8n
│   ├── nextcloud
│   ├── open-webui
│   └── vaultwarden
│
├── databases
│   ├── postgres
│   └── redis
│
├── infra
│   ├── cloudflared
│   ├── homepage
│   ├── portainer
│   ├── traefik
│   └── twingate
│
├── monitoring
│   ├── grafana
│   ├── loki
│   ├── prometheus
│   └── uptime-kuma
│
├── data
│   ├── postgres
│   ├── redis
│   ├── uptime-kuma
│   ├── nextcloud
│   ├── loki
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
* [x] Set exposedByDefault=false for security

---

## Cloudflared

Purpose:

* Secure Remote Access
* Zero Open Ports

Status:

* [x] Installed
* [x] Tunnel Created
* [x] Wildcard Route Configured
* [x] Single Root env-file Configuration

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
* [x] Cleaned up Dockerfile with external initialization script

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

## Grafana Loki & Promtail

Purpose:

* Centralized Log Aggregation
* Docker Container Log Scraping
* Query logs inside Grafana using LogQL

Status:

* [x] Installed

---

# Data Services

## PostgreSQL 17

Purpose:

* Primary Database

Status:

* [x] Installed

---

## Redis (Standalone)

Purpose:

* Cache
* Pub/Sub

Status:

* [x] Decoupled into standalone databases service

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

## Docmost (Wiki.js alternative)

Purpose:

* Documentation
* SOPs
* Technical Notes

Status:

* [x] Installed

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

* [ ] Skipped (Using Nextcloud Photos instead)

---

# Security

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

## Monthly

* Full Docker Volume Backup

Destination:

* External HDD
* Cloud Storage

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
11. [x] Configure Grafana System Alerting
12. [x] Install Docmost (Documentation)
13. [x] Reorganize scrambled service folders into apps/, databases/, monitoring/, and infra/
14. [x] Consolidate multiple individual .env files into single root .env
15. [x] Decouple Redis from Nextcloud into standalone databases/redis service
16. [x] Refactor code-server initialization logic to externalize startup scripts
17. [x] Secure Traefik default routing (exposedByDefault=false)
18. [x] Install Grafana Loki & Promtail (Log Aggregation)

Target Outcome:

A fully remote-accessible personal cloud and development environment systematically organized and managed through Docker, Traefik, Cloudflare Tunnel, and Code Server.
