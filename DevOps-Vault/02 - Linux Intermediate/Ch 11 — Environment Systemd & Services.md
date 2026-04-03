---
aliases: [Systemd, Services, journalctl, Environment Variables]
tags: [part2, linux-intermediate, systemd, services, systemctl]
completed: false
chapter: 11
---

# 💡 Chapter 11 — Environment, Systemd & Services

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 💻 Environment Variables

```bash
env                             # All environment variables
echo $PATH                      # Specific variable
export MY_VAR="hello"           # Available in current shell + children

# Permanent (current user):
echo 'export MY_VAR="hello"' >> ~/.bashrc
source ~/.bashrc
```

---

## 💻 Systemd — The Service Manager

```bash
systemctl start nginx           # Start
systemctl stop nginx            # Stop
systemctl restart nginx         # Restart (stop then start)
systemctl reload nginx          # Reload config (usually no downtime)
systemctl status nginx          # Detailed status

systemctl enable nginx          # Auto-start on boot
systemctl enable --now nginx    # Enable AND start immediately

systemctl list-units --type=service --state=running
systemctl daemon-reload         # ALWAYS after changing unit files!
```

---

## 📖 Creating a Custom Systemd Service (DevOps Must-Know!)

```ini
# /etc/systemd/system/myapp.service
[Unit]
Description=My Web Application
After=network.target postgresql.service

[Service]
Type=simple
User=www-data
WorkingDirectory=/opt/myapp
ExecStart=/usr/bin/node /opt/myapp/server.js
Restart=always
RestartSec=5
Environment=NODE_ENV=production
EnvironmentFile=/opt/myapp/.env

[Install]
WantedBy=multi-user.target
```

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now myapp
sudo systemctl status myapp
```

---

## 💻 journalctl — Reading Logs

```bash
journalctl -u nginx -f              # Follow nginx logs live
journalctl -u nginx -n 50           # Last 50 lines
journalctl --since "1 hour ago"
journalctl -p err                   # Only errors
journalctl -b                       # Current boot only
journalctl --vacuum-size=500M       # Trim logs to 500MB
```

---

## Related

- [[Ch 13 — Logs & System Monitoring]] — Understanding system logs
- [[Ch 07 — Process Management]] — How processes relate to services
- [[Ch 12 — Cron Jobs & Automation]] — Scheduled execution

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 10 — Storage & Disk Management]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 12 — Cron Jobs & Automation]]
