---
aliases: [What is a Network, Network Types, Data Travel]
tags: [part4, networking, fundamentals, network-types]
completed: false
chapter: 19
---

# 💡 Chapter 19 — What is a Network?

> [!info] **Part of** [[Part 4 — Networking Fundamentals]]

---

## 📖 Networks Are Everywhere

A **network** is simply a collection of devices that can communicate with each other. Every time you open a website, send a message, or stream video — networking is happening.

---

## 📖 The Postal System Analogy

```
YOU WRITE A LETTER (APPLICATION DATA)
         ↓
SEAL IN ENVELOPE (TCP HEADER — port numbers)
         ↓
PUT IN LARGER ENVELOPE (IP HEADER — IP addresses)
         ↓
LABEL OUTER BOX (ETHERNET HEADER — MAC addresses)
         ↓
POSTAL WORKER → POST OFFICE → TRUCKS → LOCAL DELIVERY
         ↓
RECIPIENT OPENS IN REVERSE → READS THE LETTER
```

---

## 📖 Network Types

| Type | Coverage | Example |
|------|----------|---------|
| PAN | 1-10 meters | Bluetooth, NFC |
| LAN | Up to 1km | Home WiFi, office |
| MAN | City-wide | City fiber |
| WAN | Country/Globe | Internet |
| VPN | Anywhere | Virtual private network |

---

## 📖 How Data Actually Travels

```
You open google.com:
1. Browser → HTTP request
2. OS → wraps in TCP (port 443)
3. OS → wraps in IP packet (your IP + Google's IP)
4. NIC → wraps in Ethernet frame (MAC addresses)
5-8. Router → ISP → ~10-20 hops → Google
9. Google → processes, sends response
10. Reverse path → response reaches you
Total time: ~200-400 milliseconds!
```

---

## Related

- [[Ch 20 — OSI & TCP-IP Models]] — The layered model behind this
- [[Ch 21 — IP Addressing & Subnetting]] — IP addresses explained
- [[Ch 18 — Linux Networking Config]] — Configuring network interfaces

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> [[Part 4 — Networking Fundamentals]] | **Next →** [[Ch 20 — OSI & TCP-IP Models]]
