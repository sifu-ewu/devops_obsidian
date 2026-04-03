---
aliases: [Docker, Containers, Dockerfile, Docker Compose]
tags: [part6, devops-tools, docker, containers, compose]
completed: false
chapter: 28
---

# 💡 Chapter 28 — Docker & Containers (Linux in a Box)

> [!info] **Part of** [[Part 6 — DevOps Toolchain]]

---

## 📖 What Problem Does Docker Solve?

```
THE CLASSIC PROBLEM:
Developer: "It works on my machine! 🤷"
Operations: "It crashes on the server! 💥"

DOCKER'S SOLUTION:
Package APP + ALL DEPENDENCIES together as a "container"
Runs identically everywhere. "Build once, run anywhere."
```

---

## 📖 Docker Architecture

```
Docker CLI → Docker Daemon (dockerd) → containerd → Linux Kernel
                                                      (namespaces + cgroups)
```

> [!tip] Docker uses the same [[Ch 15 — Linux Kernel & Namespaces|namespaces & cgroups]] you learned in Part 3!

---

## 💻 Docker Commands

```bash
# ─── IMAGES ─────────────────────────────────────────
docker images; docker pull nginx:1.24; docker rmi nginx
docker build -t myapp:v1.0 .; docker push myrepo/myapp:v1.0

# ─── CONTAINERS ─────────────────────────────────────
docker run -d -p 8080:80 --name web nginx
docker ps; docker ps -a; docker stop web; docker rm web
docker run -it ubuntu bash              # Interactive

# ─── INTERACTION ────────────────────────────────────
docker exec -it web bash; docker logs -f web
docker inspect web; docker stats; docker cp file.txt web:/tmp/

# ─── VOLUMES ────────────────────────────────────────
docker volume create mydata
docker run -d -v mydata:/var/lib/mysql mysql
docker run -d -v /host/path:/container/path nginx

# ─── NETWORKING ─────────────────────────────────────
docker network create mynet
docker run -d --network mynet --name web nginx
docker run -d --network mynet --name db mysql
# 'web' can reach 'db' by hostname!
```

---

## 📖 Dockerfile

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
EXPOSE 3000
ENV NODE_ENV=production
HEALTHCHECK --interval=30s --timeout=3s --retries=3 \
  CMD curl -f http://localhost:3000/health || exit 1
CMD ["node", "server.js"]
```

---

## 📖 Docker Compose

```yaml
# docker-compose.yml
version: '3.8'
services:
  web:
    image: nginx:1.24
    ports: ["80:80", "443:443"]
    depends_on: [app]
    restart: always

  app:
    build: ./app/
    environment:
      - NODE_ENV=production
      - DB_HOST=database
    depends_on:
      database:
        condition: service_healthy
    restart: always

  database:
    image: postgres:15
    environment:
      POSTGRES_DB: myapp
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    volumes: [postgres_data:/var/lib/postgresql/data]
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U appuser"]
    restart: always

volumes:
  postgres_data:
```

```bash
docker-compose up -d; docker-compose ps; docker-compose logs -f app
docker-compose down; docker-compose down -v
```

---

## Related

- [[Ch 15 — Linux Kernel & Namespaces]] — The Linux features Docker uses
- [[Ch 29 — CI-CD Pipelines]] — Building Docker images in CI
- [[Ch 07 — Process Management]] — Container process isolation

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> [[Part 6 — DevOps Toolchain]] | **Next →** [[Ch 29 — CI-CD Pipelines]]
