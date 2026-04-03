---
aliases: [DNS, Domain Name System, dig, nslookup, DNS Records]
tags: [part4, networking, dns, domain, resolution]
completed: false
chapter: 22
---

# 💡 Chapter 22 — DNS — The Internet's Phone Book

> [!info] **Part of** [[Part 4 — Networking Fundamentals]]

---

## 📖 DNS Without Jargon

You type `google.com` → DNS tells your browser `142.250.80.46` → browser connects. Without DNS, you'd remember IP addresses instead of names.

---

## 📖 DNS Resolution — Step by Step

```
Browser cache → OS /etc/hosts → DNS resolver cache
  → ROOT nameserver (.) → .com TLD server
  → example.com's nameserver → Answer: 93.184.216.34
  → Resolver caches (TTL) → Browser connects
```

---

## 📖 DNS Record Types

| Record | Purpose | Example |
|--------|---------|---------|
| **A** | Hostname → IPv4 | `example.com → 93.184.216.34` |
| **AAAA** | Hostname → IPv6 | `example.com → 2606:2800:...` |
| **CNAME** | Alias → hostname | `www → example.com` |
| **MX** | Mail server | `example.com → mail1.example.com` |
| **TXT** | Text info (SPF, DKIM) | `v=spf1 include:...` |
| **NS** | Nameservers | `example.com → ns1.digitalocean.com` |
| **PTR** | Reverse DNS (IP → name) | |
| **SRV** | Service location | |

---

## 💻 DNS Tools

```bash
# nslookup
nslookup google.com
nslookup -type=MX gmail.com

# dig (most powerful)
dig google.com
dig google.com MX
dig +short google.com
dig @8.8.8.8 google.com        # Query specific DNS
dig +trace google.com           # Full resolution trace!
dig -x 8.8.8.8                  # Reverse DNS

# host (simple)
host google.com
host -t MX google.com
```

---

## 💻 DNS Configuration Files

```bash
cat /etc/hosts          # Local override (checked BEFORE DNS!)
cat /etc/resolv.conf    # Which DNS servers to use
cat /etc/nsswitch.conf | grep hosts  # Lookup order

# DevOps use: Override DNS for testing
echo "192.168.1.50 staging.myapp.com" | sudo tee -a /etc/hosts
```

---

## Related

- [[Ch 20 — OSI & TCP-IP Models]] — DNS at Layer 7
- [[Ch 23 — HTTP HTTPS & Web]] — What happens after DNS resolution
- [[Ch 24 — Network Tools & Diagnostics]] — More DNS tools

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 21 — IP Addressing & Subnetting]] | [[Part 4 — Networking Fundamentals]] | **Next →** [[Ch 23 — HTTP HTTPS & Web]]
