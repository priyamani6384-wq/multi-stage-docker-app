# Multi-Stage Docker Containerization & Optimization

## Objective
Create optimized multi-stage Dockerfile with <150MB size, non-root user, and health checks.

## Features Implemented
- Multi-stage build (builder + final)
- Final image ~118MB (node:18-alpine)
- Non-root user: appuser
- Health check for web and db
- Named volumes: db-data, app-data
- PostgreSQL 15-alpine for DB

## How to Run
docker build -t multi-stage-app .
docker images multi-stage-app (check <150MB)
docker-compose up -d
docker-compose ps
curl localhost:3000/health

## Files
- Dockerfile - Multi-stage optimized
- docker-compose.yml - Web + DB with healthcheck
- app.js - Express app with /health endpoint
- package.json
## Task 06 - Cloud Infrastructure & Monitoring

### Live Deployment
- **Live URL:** https://multi-stage-docker-app.onrender.com
- **Health Endpoint:** /health - returns 200 OK

### Architecture
User -> Nginx (SSL + Reverse Proxy) -> Docker Container (Node.js App) -> Prometheus/Grafana

### Deployment Pipeline
1. Code push to GitHub main
2. GitHub Actions: lint -> test -> build Docker
3. Auto deploy to Render via webhook
4. UptimeRobot monitors /health every 5 mins

### Monitoring Setup
- Health check: GET /health
- Uptime: UptimeRobot (email alerts)
- Metrics: /metrics endpoint for Prometheus
- Grafana dashboard for CPU/Memory

### Expected Proof
GitHub Repo + Live Cloud URL (Render deployment)
