---
aliases: [Cron Jobs, Crontab, Automation, Scheduling]
tags: [part2, linux-intermediate, cron, automation, scheduling]
completed: false
chapter: 12
---

# 💡 Chapter 12 — Cron Jobs & Automation

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 What are Cron Jobs?

Cron is like an **alarm clock for your computer**. You set it to run a command at a specific time. It's how DevOps engineers automate: daily backups, hourly log rotation, weekly security updates, continuous health checks.

---

## 📖 Cron Syntax

```
┌────────── Minute (0-59)
│ ┌──────── Hour (0-23)
│ │ ┌────── Day of Month (1-31)
│ │ │ ┌──── Month (1-12)
│ │ │ │ ┌── Day of Week (0-7, 0 and 7 = Sunday)
│ │ │ │ │
* * * * *  command
```

| Symbol | Meaning |
|--------|---------|
| `*` | Every value |
| `*/5` | Every 5 units |
| `1,3,5` | Specific values |
| `1-5` | Range |

---

## 💻 Cron Examples

```bash
crontab -e          # Edit YOUR crontab
crontab -l          # List your crontab
crontab -r          # REMOVE your crontab

# Examples:
* * * * *     /opt/scripts/check.sh         # Every minute
*/5 * * * *   /opt/scripts/check.sh         # Every 5 minutes
30 2 * * *    /opt/scripts/backup.sh        # 2:30 AM daily
0 0 * * 0     /opt/scripts/weekly.sh        # Midnight Sunday
0 9 * * 1-5   /opt/scripts/morning.sh       # 9 AM weekdays

# Special keywords:
@reboot     /opt/scripts/startup.sh         # Run once at boot
@daily      /opt/scripts/daily.sh           # Daily at midnight
@hourly     /opt/scripts/hourly.sh          # Every hour

# ALWAYS log output!
30 2 * * * /opt/scripts/backup.sh >> /var/log/backup.log 2>&1
```

---

> [!lab]- 🔬 Mini Lab 7: Cron Jobs
> Create a disk monitoring script that checks if any filesystem is over 80% and logs warnings, then schedule it with cron every 5 minutes. See [[Ch 13 — Logs & System Monitoring]] for more monitoring patterns.

---

## Related

- [[Ch 08 — Bash Shell Scripting]] — Scripts that cron runs
- [[Ch 13 — Logs & System Monitoring]] — Monitoring + alerting
- [[Ch 29 — CI-CD Pipelines]] — Automation at pipeline level

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 11 — Environment Systemd & Services]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 13 — Logs & System Monitoring]]
