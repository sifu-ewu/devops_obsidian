---
aliases: [Monitoring, Observability, Prometheus, Grafana, Alerting]
tags: [part6, devops-tools, monitoring, prometheus, grafana, observability]
completed: false
chapter: 31
---

# 💡 Chapter 31 — Monitoring & Observability

> [!info] **Part of** [[Part 6 — DevOps Toolchain]]

---

## 📖 The Three Pillars of Observability

| Pillar | What | Tools |
|--------|------|-------|
| **Metrics** | Numbers over time (CPU 80%, 1000 req/s) | Prometheus, Grafana, DataDog |
| **Logs** | Text records of events | ELK Stack, Loki + Grafana |
| **Traces** | Follow a request through services | Jaeger, Zipkin, X-Ray |

---

## 📖 Prometheus + Grafana

```yaml
# prometheus.yml
global:
  scrape_interval: 15s

alerting:
  alertmanagers:
    - static_configs:
        - targets: ['alertmanager:9093']

rule_files:
  - "alerts.yml"

scrape_configs:
  - job_name: 'node-exporter'
    static_configs:
      - targets: ['web1:9100', 'web2:9100', 'db1:9100']

  - job_name: 'nginx'
    static_configs:
      - targets: ['nginx:9113']

  - job_name: 'myapp'
    static_configs:
      - targets: ['app:3000']
```

---

## 📖 Alert Rules

```yaml
# alerts.yml
groups:
  - name: system
    rules:
      - alert: HighCPUUsage
        expr: 100 - (avg by(instance)(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100) > 90
        for: 5m
        labels: { severity: warning }
        annotations:
          summary: "CPU > 90% for 5 minutes on {{ $labels.instance }}"

      - alert: HighMemoryUsage
        expr: (node_memory_MemTotal_bytes - node_memory_MemAvailable_bytes) / node_memory_MemTotal_bytes * 100 > 90
        for: 5m
        labels: { severity: critical }

      - alert: DiskAlmostFull
        expr: (node_filesystem_size_bytes - node_filesystem_free_bytes) / node_filesystem_size_bytes * 100 > 85
        for: 10m
        labels: { severity: warning }

      - alert: ServiceDown
        expr: up == 0
        for: 1m
        labels: { severity: critical }
```

---

## Related

- [[Ch 13 — Logs & System Monitoring]] — Linux-level monitoring
- [[Ch 16 — Performance Tuning]] — Troubleshooting methodology
- [[Ch 28 — Docker & Containers]] — Monitoring containers

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 30 — Infrastructure as Code]] | [[Part 6 — DevOps Toolchain]] | **Next Part →** [[Part 7 — Practice]]
