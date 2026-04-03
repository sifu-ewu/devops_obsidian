---
aliases: [Network Tools, Diagnostics, ping, traceroute, tcpdump, ss, netcat]
tags: [part5, networking-advanced, tools, diagnostics, tcpdump]
completed: false
chapter: 24
---

# 💡 Chapter 24 — Network Tools & Diagnostics

> [!info] **Part of** [[Part 5 — Networking Advanced]]

---

## 💻 Connectivity

```bash
ping google.com                 # ICMP echo
ping -c 4 google.com            # Exactly 4 pings

traceroute google.com           # Trace every hop
mtr google.com                  # Real-time ping + traceroute (BEST!)
mtr --report google.com         # Report mode
```

---

## 💻 Port & Socket Info

```bash
# ss (modern netstat)
ss -tuln                        # Listening ports
ss -tulpn                       # With process names (root)
ss -ta                          # All TCP connections
ss -s                           # Summary

# netcat (Swiss army knife)
nc -zv google.com 443           # Test if port open
nc -l 1234                      # Listen on port
nc hostname 1234 < file.txt     # Send file

# lsof
lsof -i :80                    # What's using port 80?
lsof -i TCP                    # All TCP connections
```

---

## 💻 Packet Capture

```bash
tcpdump -i eth0                         # All traffic
tcpdump -i eth0 port 80                 # HTTP only
tcpdump -i eth0 host 192.168.1.100      # Specific IP
tcpdump -i eth0 -w capture.pcap         # Save for Wireshark
tcpdump -i eth0 -c 100                  # Only 100 packets
tcpdump -i eth0 -A 'tcp port 80' | grep "GET\|POST\|Host:"
```

---

## 💻 Network Performance Testing

```bash
# iperf3
iperf3 -s                       # Server mode
iperf3 -c server_ip             # Client → measure bandwidth
iperf3 -c server_ip -P 4        # 4 parallel streams

# Bandwidth monitors
nload; iftop; nethogs; bmon
```

---

## Related

- [[Ch 22 — DNS]] — DNS tools (dig, nslookup)
- [[Ch 16 — Performance Tuning]] — System-level troubleshooting
- [[Ch 25 — Firewalls & Network Security]] — When ports are blocked

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> [[Part 5 — Networking Advanced]] | **Next →** [[Ch 25 — Firewalls & Network Security]]
