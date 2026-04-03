---
aliases: [OSI Model, TCP/IP, TCP vs UDP, Ports, 3-Way Handshake]
tags: [part4, networking, osi, tcp-ip, tcp, udp, ports]
chapter: 20
---

# 💡 Chapter 20 — OSI & TCP/IP Models

> [!info] **Part of** [[Part 4 — Networking Fundamentals]]

---

## 📖 OSI Model — 7 Layers

```
Layer 7 — APPLICATION    HTTP, DNS, SSH, FTP       → "Data"
Layer 6 — PRESENTATION   TLS/SSL, JPEG, MPEG       → Translator
Layer 5 — SESSION        NetBIOS, RPC               → Call manager
Layer 4 — TRANSPORT ⭐   TCP, UDP; Port numbers     → "Segment"
Layer 3 — NETWORK ⭐     IP, ICMP; IP addresses     → "Packet"
Layer 2 — DATA LINK ⭐   Ethernet, WiFi; MAC addrs  → "Frame"
Layer 1 — PHYSICAL       Cables, radio, fiber       → "Bit"
```

> [!tip] **Memory Trick** (top→bottom): "**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing"

---

## 📖 TCP/IP Model (What's Used in Practice)

| TCP/IP Layer | OSI Equivalent | Protocols |
|---|---|---|
| Application | Layers 5-7 | HTTP, DNS, SSH |
| Transport | Layer 4 | TCP, UDP |
| Internet | Layer 3 | IP, ICMP, ARP |
| Network Access | Layers 1-2 | Ethernet, WiFi |

---

## 📖 TCP vs UDP

| | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented | Connectionless |
| Delivery | Guaranteed, in-order | Best effort |
| Speed | Slower (overhead) | Faster |
| Use cases | Web, SSH, email, FTP | DNS, streaming, gaming, VoIP |

---

## 📖 TCP 3-Way Handshake

```
Client ──── SYN ──────────────► Server
Client ◄─── SYN-ACK ─────────── Server
Client ──── ACK ──────────────► Server
       [DATA TRANSFER BEGINS]
```

```bash
ss -tan    # See TCP states: LISTEN, ESTABLISHED, FIN-WAIT, etc.
```

---

## 📖 Common Port Numbers

| Port | Protocol | Service |
|------|----------|---------|
| 22 | TCP | SSH |
| 53 | TCP/UDP | DNS |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |
| 3306 | TCP | MySQL |
| 5432 | TCP | PostgreSQL |
| 6379 | TCP | Redis |
| 8080 | TCP | HTTP Alt |
| 27017 | TCP | MongoDB |

---

> [!quiz]- 🧠 Quiz 5 — OSI & TCP/IP
> 1. At which OSI layer do IP addresses operate?
> 2. At which OSI layer do port numbers operate?
> 3. TCP or UDP for live video streaming? Why?
> 4. What is the sequence of a TCP handshake?
> 5. Router = which layer? Switch = which layer?
> 6. Why does HTTPS use port 443, HTTP port 80?
>
> See [[Quiz Answers#Quiz 5 Answers — OSI & TCP/IP]]

---

## Related

- [[Ch 19 — What is a Network]] — Foundation concepts
- [[Ch 21 — IP Addressing & Subnetting]] — Layer 3 deep dive
- [[Ch 23 — HTTP HTTPS & Web]] — Layer 7 HTTP/HTTPS

---

> **Navigation:** **← Prev** [[Ch 19 — What is a Network]] | [[Part 4 — Networking Fundamentals]] | **Next →** [[Ch 21 — IP Addressing & Subnetting]]
