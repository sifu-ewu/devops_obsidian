---
aliases: [Lab Projects, Labs, Hands-on]
tags: [part7, practice, labs, hands-on]
---

# 🔬 Lab Projects

> [!info] **Return to** [[Part 7 — Practice]] | [[Home]]

---

## 🔬 Lab Project 1: Complete Linux Server Setup

**Goal:** Set up a production-ready Ubuntu server from scratch.

```bash
# STEP 1: Initial setup
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget git vim htop ufw fail2ban

# STEP 2: Create deployment user
sudo useradd -m -s /bin/bash deploy
sudo usermod -aG sudo deploy
sudo mkdir -p /home/deploy/.ssh
sudo chmod 700 /home/deploy/.ssh
sudo cp ~/.ssh/authorized_keys /home/deploy/.ssh/
sudo chown -R deploy:deploy /home/deploy/.ssh

# STEP 3: Harden SSH
sudo tee /etc/ssh/sshd_config.d/hardening.conf << 'EOF'
PermitRootLogin no
PasswordAuthentication no
MaxAuthTries 3
LoginGraceTime 20
EOF
sudo systemctl reload sshd

# STEP 4: Configure firewall
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp; sudo ufw allow 80/tcp; sudo ufw allow 443/tcp
sudo ufw enable

# STEP 5: Set up fail2ban
sudo systemctl enable --now fail2ban

# STEP 6: Create monitoring script
sudo tee /opt/health_check.sh << 'SCRIPT'
#!/bin/bash
LOG="/var/log/health.log"
DATE=$(date '+%Y-%m-%d %H:%M:%S')
CPU_LOAD=$(uptime | awk -F'average:' '{print $2}' | cut -d, -f1 | tr -d ' ')
MEM_USED=$(free | awk '/Mem:/{printf "%.0f", $3/$2*100}')
DISK_USED=$(df / | awk 'NR==2{gsub(/%/,""); print $5}')
echo "$DATE CPU:${CPU_LOAD} MEM:${MEM_USED}% DISK:${DISK_USED}%" >> $LOG
[ "$MEM_USED" -gt 90 ] && echo "$DATE ALERT: High memory!" >> $LOG
[ "$DISK_USED" -gt 85 ] && echo "$DATE ALERT: Disk nearly full!" >> $LOG
SCRIPT
sudo chmod +x /opt/health_check.sh

# STEP 7: Schedule monitoring (every 5 min)
(crontab -l 2>/dev/null; echo "*/5 * * * * /opt/health_check.sh") | crontab -
```

> [!tip] Skills used: [[Ch 05 — Users & Groups]], [[Ch 14 — SSH & Remote Access]], [[Ch 17 — Security Hardening]], [[Ch 12 — Cron Jobs & Automation]], [[Ch 13 — Logs & System Monitoring]]

---

## 🔬 Lab Project 2: Web Server with Load Balancing

**Goal:** Set up nginx load balancing across multiple app instances.

```bash
sudo apt install -y nginx
mkdir -p /opt/apps/app1 /opt/apps/app2

# App 1 on port 8081
cat > /opt/apps/app1/server.py << 'EOF'
#!/usr/bin/env python3
from http.server import HTTPServer, BaseHTTPRequestHandler
class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        if self.path == '/health':
            self.send_response(200); self.end_headers()
            self.wfile.write(b'{"status":"ok","server":"app1"}')
        else:
            self.send_response(200); self.end_headers()
            self.wfile.write(b'Hello from App Server 1!')
    def log_message(self, format, *args): pass
HTTPServer(('0.0.0.0', 8081), Handler).serve_forever()
EOF

# App 2 on port 8082
sed 's/8081/8082/g; s/app1/app2/g' /opt/apps/app1/server.py > /opt/apps/app2/server.py

python3 /opt/apps/app1/server.py &
python3 /opt/apps/app2/server.py &

# Nginx load balancer config
sudo tee /etc/nginx/sites-available/loadbalancer << 'EOF'
upstream apps {
    least_conn;
    server 127.0.0.1:8081;
    server 127.0.0.1:8082;
}
server {
    listen 80;
    server_name _;
    location / { proxy_pass http://apps; proxy_set_header Host $host; }
    location /health { access_log off; proxy_pass http://apps; }
}
EOF

sudo ln -sf /etc/nginx/sites-available/loadbalancer /etc/nginx/sites-enabled/
sudo rm -f /etc/nginx/sites-enabled/default
sudo nginx -t && sudo systemctl reload nginx

# Test — should alternate between servers
for i in {1..10}; do curl -s http://localhost; echo; done
```

> [!tip] Skills used: [[Ch 26 — Load Balancing & Proxies]], [[Ch 11 — Environment Systemd & Services]], [[Ch 23 — HTTP HTTPS & Web]]

---

## 🔬 Lab Project 3: Log Analysis Dashboard

```bash
#!/bin/bash
# log_analyzer.sh — Analyze nginx access log
LOG_FILE="/var/log/nginx/access.log"

echo "═══════════════════════════════════════"
echo "    NGINX ACCESS LOG ANALYSIS"
echo "    $(date '+%Y-%m-%d %H:%M:%S')"
echo "═══════════════════════════════════════"

echo ""; echo "📊 Total Requests:"
wc -l < "$LOG_FILE"

echo ""; echo "📊 Status Code Distribution:"
awk '{print $9}' "$LOG_FILE" | sort | uniq -c | sort -rn

echo ""; echo "📊 Top 10 IPs:"
awk '{print $1}' "$LOG_FILE" | sort | uniq -c | sort -rn | head -10

echo ""; echo "📊 Top 10 URLs:"
awk '{print $7}' "$LOG_FILE" | sort | uniq -c | sort -rn | head -10

echo ""; echo "📊 Error Requests (4xx/5xx):"
awk '$9 ~ /^[45]/' "$LOG_FILE" | wc -l

echo ""; echo "📊 Requests per Hour (last 24h):"
awk '{print substr($4, 2, 14)}' "$LOG_FILE" | \
  awk -F: '{print $1":"$2":00"}' | sort | uniq -c | tail -24
```

> [!tip] Skills used: [[Ch 09 — Text Processing]], [[Ch 13 — Logs & System Monitoring]], [[Ch 08 — Bash Shell Scripting]]

---

> **Navigation:** [[Part 7 — Practice]] | [[Home]]
