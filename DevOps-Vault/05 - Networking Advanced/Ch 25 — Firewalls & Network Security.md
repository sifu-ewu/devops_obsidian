---
aliases: [Firewalls, ufw, iptables, Network Security, NAT]
tags: [part5, networking-advanced, firewall, ufw, iptables, security]
completed: false
chapter: 25
---

# 💡 Chapter 25 — Firewalls & Network Security

> [!info] **Part of** [[Part 5 — Networking Advanced]]

---

## 📖 What is a Firewall?

A firewall is like a **security guard** — checks every packet against a list of rules, blocks anything not explicitly allowed.

---

## 💻 ufw — Ubuntu Firewall

```bash
ufw status verbose              # Current status + rules
ufw status numbered             # With rule numbers

# Basic setup
ufw default deny incoming
ufw default allow outgoing
ufw allow ssh                   # Port 22
ufw allow 80/tcp; ufw allow 443/tcp

# From specific IP
ufw allow from 192.168.1.10 to any port 22
ufw allow from 192.168.1.0/24

# Deny & delete
ufw deny 23/tcp; ufw deny from 1.2.3.4
ufw delete allow 80/tcp; ufw delete 3

# Rate limiting
ufw limit ssh                   # Anti-brute force

ufw enable; ufw reload
ufw logging on
```

---

## 💻 iptables — The Underlying Engine

```bash
# View rules
iptables -L -n -v --line-numbers
iptables -t nat -L              # NAT table

# Rules
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -P INPUT DROP          # Default deny

# Persist
apt install iptables-persistent
netfilter-persistent save

# NAT masquerade
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
echo 1 > /proc/sys/net/ipv4/ip_forward
```

---

## Related

- [[Ch 17 — Security Hardening]] — Broader security checklist
- [[Ch 14 — SSH & Remote Access]] — SSH hardening
- [[Ch 27 — VPN Tunneling & Cloud Networking]] — Cloud security groups

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 24 — Network Tools & Diagnostics]] | [[Part 5 — Networking Advanced]] | **Next →** [[Ch 26 — Load Balancing & Proxies]]
