---
aliases: [Network Config, Netplan, ip command, Interfaces]
tags: [part3, linux-advanced, networking, netplan, interfaces]
completed: false
chapter: 18
---

# 💡 Chapter 18 — Linux Networking Configuration

> [!info] **Part of** [[Part 3 — Linux Advanced]]

---

## 💻 Network Interfaces

```bash
ip addr show                    # All interfaces
ip link show                    # Link layer info

# Typical interfaces:
# lo        → Loopback (127.0.0.1)
# eth0/ens3 → Wired ethernet
# docker0   → Docker bridge network
# veth*     → Virtual ethernet (containers)

ip link set eth0 up             # Enable interface
ip link set eth0 down           # Disable interface
ip addr add 192.168.1.100/24 dev eth0   # Add IP
ip addr del 192.168.1.100/24 dev eth0   # Remove IP
```

---

## 💻 Routing

```bash
ip route show                   # Routing table
ip route add default via 192.168.1.1
ip route add 10.0.0.0/8 via 10.1.1.1 dev eth1
ip route del 10.0.0.0/8
```

---

## 💻 Netplan (Ubuntu 18.04+)

```yaml
# /etc/netplan/00-installer-config.yaml

# DHCP:
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: true

# Static IP:
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: false
      addresses:
        - 192.168.1.100/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
```

```bash
sudo netplan apply      # Apply changes
sudo netplan try        # Test (auto-reverts if you don't confirm)
```

---

## Related

- [[Ch 21 — IP Addressing & Subnetting]] — IP fundamentals
- [[Ch 24 — Network Tools & Diagnostics]] — Testing connectivity
- [[Ch 27 — VPN Tunneling & Cloud Networking]] — Cloud VPC networking

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 17 — Security Hardening]] | [[Part 3 — Linux Advanced]] | **Next Part →** [[Part 4 — Networking Fundamentals]]
