---
aliases: [HTTP, HTTPS, TLS, SSL, curl, Status Codes, REST]
tags: [part4, networking, http, https, tls, web, curl]
completed: false
chapter: 23
---

# 💡 Chapter 23 — HTTP, HTTPS & How the Web Works

> [!info] **Part of** [[Part 4 — Networking Fundamentals]]

---

## 📖 HTTP Methods

| Method | Purpose | Analogy |
|--------|---------|---------|
| **GET** | Read/retrieve | View a profile |
| **POST** | Create new | Submit a form |
| **PUT** | Replace entire resource | Full update |
| **PATCH** | Partial update | Change just email |
| **DELETE** | Remove | Delete a user |
| **HEAD** | Headers only | Check if resource exists |
| **OPTIONS** | What methods allowed | CORS preflight |

---

## 📖 HTTP Status Codes — Know Them Cold

| Code | Meaning | Remember |
|------|---------|----------|
| **200** | OK | Success |
| **201** | Created | POST success |
| **301** | Moved Permanently | URL changed forever |
| **302** | Found | Temporary redirect |
| **400** | Bad Request | Malformed |
| **401** | Unauthorized | Not logged in |
| **403** | Forbidden | No permission |
| **404** | Not Found | Doesn't exist |
| **429** | Too Many Requests | Rate limited |
| **500** | Internal Server Error | Bug in server |
| **502** | Bad Gateway | Upstream error |
| **503** | Service Unavailable | Server down |
| **504** | Gateway Timeout | Upstream timeout |

---

## 📖 HTTPS & TLS

```
HTTP  = Unencrypted (postcard — anyone can read)
HTTPS = Encrypted (sealed letter in secure courier)

TLS provides:
  ✓ Encryption     (only sender/receiver can read)
  ✓ Authentication (proves you're talking to REAL server)
  ✓ Integrity      (detect if data was tampered)
```

---

## 💻 curl — HTTP from Command Line

```bash
curl https://api.github.com                     # GET
curl -I https://google.com                      # Headers only
curl -v https://google.com                      # Verbose

# POST with JSON
curl -X POST https://api.example.com/users \
  -H "Content-Type: application/json" \
  -d '{"name": "John", "email": "john@example.com"}'

curl -O https://example.com/file.tar.gz         # Download
curl -L https://example.com                     # Follow redirects

# Health check in scripts
curl -o /dev/null -s -w "%{http_code}" https://example.com
```

---

## Related

- [[Ch 22 — DNS]] — What happens before HTTP
- [[Ch 26 — Load Balancing & Proxies]] — Nginx reverse proxy
- [[Ch 29 — CI-CD Pipelines]] — API testing in pipelines

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 22 — DNS]] | [[Part 4 — Networking Fundamentals]] | **Next Part →** [[Part 5 — Networking Advanced]]
