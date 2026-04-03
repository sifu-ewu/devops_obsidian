---
aliases: [Load Balancing, Reverse Proxy, Nginx, Proxy]
tags: [part5, networking-advanced, load-balancing, nginx, reverse-proxy]
completed: false
chapter: 26
---

# 💡 Chapter 26 — Load Balancing & Reverse Proxies

> [!info] **Part of** [[Part 5 — Networking Advanced]]

---

## 📖 The Problem

```
ONE SERVER:
Users (100k req/sec) ──► Server (500 req/sec capacity) ← DIES

WITH LOAD BALANCER:
                        ┌─► Server 1 (500 req/sec)
Users ──► Load Balancer ┼─► Server 2 (500 req/sec)
                        └─► Server 3 (500 req/sec)
                        Total: 1,500 req/sec + redundancy!
```

---

## 📖 Load Balancing Algorithms

| Algorithm | How It Works | Best For |
|-----------|-------------|----------|
| **Round Robin** | Requests cycle through servers 1→2→3→1 | Uniform, stateless apps |
| **Least Connections** | Always to server with fewest connections | Varying request duration |
| **IP Hash** | Hash client IP → always same server | Session persistence |
| **Weighted** | 60%→Server 1, 40%→Server 2 | Different-capacity servers |

---

## 💻 Nginx as Load Balancer & Reverse Proxy

```nginx
upstream app_servers {
    least_conn;
    server app1.internal:8080 weight=3;
    server app2.internal:8080 weight=2;
    server app3.internal:8080 weight=1;
    server app4.internal:8080 backup;
    keepalive 32;
}

server {
    listen 80;
    server_name example.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name example.com;

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;

    # Security headers
    add_header X-Frame-Options DENY;
    add_header X-Content-Type-Options nosniff;
    add_header Strict-Transport-Security "max-age=31536000";

    location / {
        proxy_pass http://app_servers;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

    location /static/ {
        root /var/www/example.com;
        expires 1y;
    }

    location /health {
        access_log off;
        return 200 "healthy\n";
    }
}
```

```bash
nginx -t                # Test config
systemctl reload nginx  # Apply without downtime
```

---

## Related

- [[Ch 23 — HTTP HTTPS & Web]] — HTTP methods and status codes
- [[Ch 28 — Docker & Containers]] — Container orchestration
- [[Ch 31 — Monitoring & Observability]] — Monitor your load balancer

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 25 — Firewalls & Network Security]] | [[Part 5 — Networking Advanced]] | **Next →** [[Ch 27 — VPN Tunneling & Cloud Networking]]
