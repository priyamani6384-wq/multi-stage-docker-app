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
