---
aliases: [Logs, System Monitoring, Log Analysis]
tags: [part2, linux-intermediate, logs, monitoring, syslog]
completed: false
chapter: 13
---

# 💡 Chapter 13 — Logs & System Monitoring

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 Why Logs Are Your Best Friend

Logs are the **flight recorder** of your system. When things break in production, logs tell you what happened, when, what caused it, and what the system was doing.

---

## 💻 Key Log Files

| Log File | Content |
|----------|---------|
| `/var/log/syslog` | General system activity (Ubuntu) |
| `/var/log/messages` | General system activity (RHEL) |
| `/var/log/auth.log` | SSH logins, sudo, su |
| `/var/log/kern.log` | Kernel messages |
| `/var/log/nginx/access.log` | HTTP requests |
| `/var/log/nginx/error.log` | Nginx errors |
| `/var/log/apt/history.log` | Package installs/removes |

---

## 💻 Log Analysis

```bash
# Monitor live
tail -f /var/log/syslog
journalctl -f -u nginx

# Search
grep "ERROR" /var/log/syslog
grep "Failed password" /var/log/auth.log

# Find SSH brute force attackers
grep "Failed password" /var/log/auth.log | \
  awk '{print $11}' | sort | uniq -c | sort -rn | head -10

# Nginx traffic: top 10 IPs
awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -rn | head -10
```

---

## 💻 System Monitoring Commands

```bash
# CPU
top / htop                      # Interactive
mpstat -P ALL 1                 # Per-CPU utilization
uptime                          # Load average

# Memory
free -h                         # Memory + swap usage

# Disk I/O
iostat -xz 1                    # Extended disk stats
iotop                           # I/O per process

# Network
ss -s                           # Summary
nethogs                         # Network per process
```

---

## Related

- [[Ch 11 — Environment Systemd & Services]] — `journalctl` for systemd logs
- [[Ch 16 — Performance Tuning]] — Advanced troubleshooting
- [[Ch 31 — Monitoring & Observability]] — Prometheus + Grafana

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 12 — Cron Jobs & Automation]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 14 — SSH & Remote Access]]
