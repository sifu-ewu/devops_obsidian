---
aliases: [Performance Tuning, Troubleshooting, USE Method]
tags: [part3, linux-advanced, performance, troubleshooting, monitoring]
completed: false
chapter: 16
---

# 💡 Chapter 16 — Performance Tuning & Troubleshooting

> [!info] **Part of** [[Part 3 — Linux Advanced]]

---

## 📖 The Troubleshooting Methodology

```
1. CHECK SYMPTOMS  → What errors do you see?
2. GATHER INFO     → Logs, metrics, recent changes
3. FORM HYPOTHESIS → What could cause this?
4. TEST            → Make one change at a time
5. VERIFY FIX      → Did it solve the problem?
6. DOCUMENT        → What was wrong and how you fixed it
```

---

## 💻 The USE Method: Utilization, Saturation, Errors

### CPU

```bash
top / htop                      # Interactive
mpstat -P ALL 1                 # Per-CPU utilization
uptime                          # Load average
ps aux --sort=-%cpu | head -10  # CPU-hungry processes

# Load average interpretation:
# Load > number of CPUs = investigate
```

### Memory

```bash
free -h                         # Memory + swap
cat /proc/meminfo               # Detailed
ps aux --sort=-%mem | head -10  # Memory-hungry processes

# "Available" = Free + reclaimable cache (THIS is what matters)
```

### Disk I/O

```bash
iostat -xz 1                    # Extended disk stats
iotop -o                        # I/O per process
# %util > 80% = problem; await > 10ms (SSD) = investigate
```

### Network

```bash
ss -s                           # Summary
nethogs                         # Per-process bandwidth
iftop                           # Connection-level view
```

---

## 💻 Common Troubleshooting Scenarios

```bash
# "Application is slow"
top; free -h; iostat -x 1; netstat -s | grep retransmit

# "Disk is full"
df -h; du -sh /var/* | sort -rh; find / -type f -size +1G

# "Service won't start"
systemctl status myapp; journalctl -u myapp -n 50

# "Can't connect to server"
ping server; nc -zv server 80; ss -tulpn | grep :80; ufw status

# "Out of memory (OOM killed)"
dmesg | grep -i "killed process"
```

---

## Related

- [[Ch 13 — Logs & System Monitoring]] — Log analysis basics
- [[Ch 31 — Monitoring & Observability]] — Prometheus + Grafana
- [[Ch 07 — Process Management]] — Process investigation

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 15 — Linux Kernel & Namespaces]] | [[Part 3 — Linux Advanced]] | **Next →** [[Ch 17 — Security Hardening]]
