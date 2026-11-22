# Monitoring Lab

## Architecture

Docker containers
       │
       ▼
Grafana Alloy
       │
       ▼
Loki
       │
       ▼
Grafana

## Components

- Grafana
- Loki
- Grafana Alloy
- Docker
- Nginx

## Log pipeline

discovery.docker
       ↓
discovery.relabel
       ↓
loki.source.docker
       ↓
loki.process
       ↓
loki.write
       ↓
Loki
       ↓
Grafana

## Labels

platform
environment
container

## Validation

- Grafana accessible
- Loki receiving logs
- Alloy collecting Docker logs
- Nginx logs visible in Grafana
- LogQL queries working

## Example LogQL

{platform="docker"}

{environment="lab"}

{container="nginx-test-2"}

{platform="docker"} |= "GET /"