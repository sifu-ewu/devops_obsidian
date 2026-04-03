---
aliases: [IP Addressing, Subnetting, CIDR, IPv4, Public Private IP]
tags: [part4, networking, ip, subnetting, cidr]
completed: false
chapter: 21
---

# 💡 Chapter 21 — IP Addressing & Subnetting

> [!info] **Part of** [[Part 4 — Networking Fundamentals]]

---

## 📖 What is an IP Address?

An IP address is like a **postal address for a device** — every device on a network needs a unique one.

```
192.168.1.100  →  4 octets, each 0-255
```

---

## 📖 Public vs Private IPs

```
PRIVATE (not routable on internet):
  10.0.0.0    – 10.255.255.255    (Class A)
  172.16.0.0  – 172.31.255.255    (Class B)
  192.168.0.0 – 192.168.255.255   (Class C)

SPECIAL:
  127.0.0.1       → Loopback (localhost)
  0.0.0.0         → All interfaces
  255.255.255.255 → Broadcast
```

---

## 📖 Subnet Masks & CIDR

```
IP:   192.168.1.100
Mask: 255.255.255.0  (= /24)

Network: 192.168.1.0
Hosts:   192.168.1.1 – 192.168.1.254  (254 usable)
Broadcast: 192.168.1.255
```

### CIDR Quick Reference

| CIDR | Subnet Mask | Hosts | Use case |
|------|------------|-------|----------|
| /24 | 255.255.255.0 | 254 | Small office/home |
| /25 | 255.255.255.128 | 126 | Medium subnet |
| /26 | 255.255.255.192 | 62 | Small subnet |
| /27 | 255.255.255.224 | 30 | Small segment |
| /28 | 255.255.255.240 | 14 | Very small |
| /30 | 255.255.255.252 | 2 | Point-to-point |

> Hosts = 2^(32 - prefix) - 2

---

## 📖 Subnetting Example (AWS VPC Style)

```
Company gets: 10.0.0.0/16  (65,534 hosts)
├── Production:  10.0.1.0/24  → web servers
├── Database:    10.0.2.0/24  → db servers
├── Development: 10.0.3.0/24  → dev machines
└── Management:  10.0.4.0/24  → monitoring, bastion
```

---

## 💻 IP Commands

```bash
ip addr show; hostname -I; ip -4 addr
curl ifconfig.me                    # Public IP
ip route show default               # Default gateway
sudo apt install ipcalc; ipcalc 192.168.1.0/24
```

---

## Related

- [[Ch 20 — OSI & TCP-IP Models]] — Layer 3 context
- [[Ch 18 — Linux Networking Config]] — Configuring IPs on Linux
- [[Ch 27 — VPN Tunneling & Cloud Networking]] — VPC subnets in the cloud

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 20 — OSI & TCP-IP Models]] | [[Part 4 — Networking Fundamentals]] | **Next →** [[Ch 22 — DNS]]
