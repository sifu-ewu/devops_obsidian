---
aliases: [Security Hardening, Defense in Depth, fail2ban, auditd]
tags: [part3, linux-advanced, security, hardening, firewall]
completed: false
chapter: 17
---

# 💡 Chapter 17 — Security Hardening

> [!info] **Part of** [[Part 3 — Linux Advanced]]

---

## 📖 The Security Mindset (Defense in Depth)

```
Layer 1: Physical security (lock the datacenter door)
Layer 2: Network security (firewall, VPN)
Layer 3: Host security (OS hardening)
Layer 4: Application security (patches, config)
Layer 5: Data security (encryption, backups)
Layer 6: Monitoring (logs, alerts)

If one layer fails, others protect you.
```

---

## 💻 Security Hardening Checklist

### 1. Keep System Updated

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install unattended-upgrades
sudo dpkg-reconfigure -plow unattended-upgrades
```

### 2. SSH Hardening

> See [[Ch 14 — SSH & Remote Access]] for full SSH hardening guide.

### 3. Firewall (ufw)

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 2222/tcp     # SSH custom port
sudo ufw allow 80/tcp       # HTTP
sudo ufw allow 443/tcp      # HTTPS
sudo ufw enable
```

> See also [[Ch 25 — Firewalls & Network Security]] for iptables deep dive.

### 4. fail2ban — Auto-ban Brute Force

```bash
sudo apt install fail2ban
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

# /etc/fail2ban/jail.local:
# [DEFAULT]
# bantime  = 1h
# findtime = 10m
# maxretry = 5

sudo systemctl enable --now fail2ban
sudo fail2ban-client status sshd
```

### 5. User Security

```bash
sudo apt install libpam-pwquality
# /etc/security/pwquality.conf: minlen=12, minclass=3
passwd -l username              # Lock account
```

### 6. Audit Logs

```bash
sudo apt install auditd
sudo auditctl -w /etc/passwd -p wa -k passwd_changes
sudo auditctl -w /etc/shadow -p wa -k shadow_changes
sudo ausearch -k passwd_changes
```

### 7. File Integrity

```bash
sudo apt install aide
sudo aideinit
sudo aide --check
```

### 8. Rootkit Detection

```bash
sudo apt install rkhunter chkrootkit
sudo rkhunter --update && sudo rkhunter --check
```

### 9. Disable Unnecessary Services

```bash
systemctl list-units --type=service --state=running
sudo systemctl disable --now bluetooth.service
```

### 10. Check Open Ports

```bash
ss -tulpn    # Each open port is an attack surface
```

---

## Related

- [[Ch 14 — SSH & Remote Access]] — SSH key-based auth, server hardening
- [[Ch 25 — Firewalls & Network Security]] — ufw and iptables
- [[Ch 04 — File Permissions]] — Permission security basics

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 16 — Performance Tuning]] | [[Part 3 — Linux Advanced]] | **Next →** [[Ch 18 — Linux Networking Config]]
