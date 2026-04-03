---
aliases: [VPN, SSH Tunneling, Cloud Networking, VPC, Security Groups]
tags: [part5, networking-advanced, vpn, ssh-tunnel, cloud, vpc]
completed: false
chapter: 27
---

# 💡 Chapter 27 — VPN, Tunneling & Cloud Networking

> [!info] **Part of** [[Part 5 — Networking Advanced]]

---

## 💻 SSH Port Forwarding (DevOps Secret Weapon)

```bash
# LOCAL PORT FORWARDING — access remote service locally
ssh -L 3306:db.internal:3306 user@bastion.example.com
# Now: mysql -h 127.0.0.1 → connects to remote DB via SSH tunnel!

# REMOTE PORT FORWARDING — expose local service on remote
ssh -R 8080:localhost:3000 user@public-server.com
# Anyone accessing public-server:8080 reaches your localhost:3000

# DYNAMIC (SOCKS PROXY)
ssh -D 1080 user@server.com
# Browser SOCKS proxy → localhost:1080 → all traffic tunneled

# Persistent tunnels
sudo apt install autossh
autossh -M 0 -N -L 3306:db.internal:3306 user@bastion &
```

---

## 📖 Cloud Networking Concepts (AWS/GCP/Azure)

```
┌──────────────────────────────────────────────┐
│  VPC: 10.0.0.0/16                            │
│  ┌──────────────┐    ┌──────────────┐        │
│  │ Public Subnet│    │Private Subnet│        │
│  │ 10.0.1.0/24  │    │ 10.0.2.0/24  │        │
│  │ [Web Server] │    │ [DB Server]  │        │
│  │ [Bastion]    │    │ [App Server] │        │
│  └──────┬───────┘    └──────────────┘        │
│   Internet GW          Only from public      │
└─────────┼────────────────────────────────────┘
       Internet
```

---

## 📖 Security Groups vs NACLs

| Feature | Security Groups | NACLs |
|---------|----------------|-------|
| Stateful | Yes (return traffic auto-allowed) | No |
| Applied to | Per resource (EC2, RDS) | Per subnet |
| Rules | Allow only | Allow + Deny |
| Evaluation | All rules checked | Numbered order |

> [!devops] **Best Practice — Layered Security:**
> Internet → NACLs → Security Groups → Instance

---

## Related

- [[Ch 14 — SSH & Remote Access]] — SSH fundamentals
- [[Ch 25 — Firewalls & Network Security]] — Linux firewalls
- [[Ch 21 — IP Addressing & Subnetting]] — VPC subnet design
- [[Ch 30 — Infrastructure as Code]] — Terraform VPC provisioning

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 26 — Load Balancing & Proxies]] | [[Part 5 — Networking Advanced]] | **Next Part →** [[Part 6 — DevOps Toolchain]]
