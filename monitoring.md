# Monitoring & Health Checks

## Health Endpoint
app.js la /health route implemented - 200 OK return pannum

## Uptime Monitoring
- Tool: UptimeRobot.com (Free)
- Monitor Type: HTTP(s)
- URL: https://your-app-url.onrender.com/health
- Interval: 5 minutes
- Alert: Email notification

## Prometheus Config
prometheus.yml:
scrape_configs:
    - job_name: 'node-app'
    static_configs:
            - targets: ['localhost:3000']

## Grafana
- Dashboard for request count, latency, CPU
- AlertManager for downtime
