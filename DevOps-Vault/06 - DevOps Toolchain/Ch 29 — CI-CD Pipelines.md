---
aliases: [CI/CD, Continuous Integration, Continuous Deployment, GitHub Actions, Pipelines]
tags: [part6, devops-tools, ci-cd, github-actions, pipelines, automation]
chapter: 29
---

# 💡 Chapter 29 — CI/CD Pipelines

> [!info] **Part of** [[Part 6 — DevOps Toolchain]]

---

## 📖 What is CI/CD?

```
CI = Continuous Integration
  Every code push → auto: run tests, check style, build, report

CD = Continuous Delivery / Deployment
  On success → auto: deploy staging → integration tests → production

BEFORE: "Integration Hell" — weeks of separate work → massive merge conflicts
WITH:   Small changes daily → catch problems early → deploy multiple times/day
```

---

## 📖 GitHub Actions Pipeline

```yaml
# .github/workflows/deploy.yml
name: Build, Test and Deploy

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    services:
      postgres:
        image: postgres:15
        env: { POSTGRES_PASSWORD: testpass, POSTGRES_DB: testdb }
        ports: ["5432:5432"]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '18', cache: 'npm' }
      - run: npm ci
      - run: npm run lint
      - run: npm test
        env:
          DATABASE_URL: postgres://postgres:testpass@localhost:5432/testdb

  build:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v4
      - uses: docker/login-action@v3
        with:
          registry: ghcr.io
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}
      - uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: ghcr.io/${{ github.repository }}:${{ github.sha }}

  deploy-staging:
    needs: build
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: appleboy/ssh-action@v1.0.0
        with:
          host: ${{ secrets.STAGING_HOST }}
          username: deploy
          key: ${{ secrets.STAGING_SSH_KEY }}
          script: |
            cd /opt/myapp
            docker-compose up -d --no-deps app
            curl -sf http://localhost:3000/health || exit 1

  deploy-production:
    needs: deploy-staging
    runs-on: ubuntu-latest
    environment: production       # Requires manual approval!
    steps:
      - uses: appleboy/ssh-action@v1.0.0
        with:
          host: ${{ secrets.PROD_HOST }}
          username: deploy
          key: ${{ secrets.PROD_SSH_KEY }}
          script: |
            cd /opt/myapp
            docker-compose up -d --no-deps --scale app=3 app
            curl -sf http://localhost/health || exit 1
```

---

## Related

- [[Ch 28 — Docker & Containers]] — Building Docker images
- [[Ch 14 — SSH & Remote Access]] — SSH keys for deployment
- [[Ch 12 — Cron Jobs & Automation]] — Scheduled automation
- [[Ch 30 — Infrastructure as Code]] — Provisioning infra in pipelines

---

> **Navigation:** **← Prev** [[Ch 28 — Docker & Containers]] | [[Part 6 — DevOps Toolchain]] | **Next →** [[Ch 30 — Infrastructure as Code]]
