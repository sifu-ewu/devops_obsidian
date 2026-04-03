---
aliases: [Problems Linux Solves, Linux Use Cases]
tags: [part0, linux-history, devops]
completed: false
chapter: 0.4
---

# 📖 Chapter 0.4 — What Problems Linux Solves TODAY

> [!info] **Part of** [[Part 0 — The Story of Linux]]

---

## Problem 1: Cost at Scale 💰

> A company runs 10,000 servers. Windows Server license: ~$900/server = **$9,000,000/year**. Linux: **$0**.

This is why Amazon, Google, Facebook all run Linux. They save **hundreds of millions of dollars**.

## Problem 2: Containers & Cloud ☁️

[[Ch 28 — Docker & Containers|Docker]] and Kubernetes are **only possible because of Linux**. Linux features called [[Ch 15 — Linux Kernel & Namespaces|namespaces and cgroups]] (built into the kernel) make containers work. This is the heart of modern cloud computing.

## Problem 3: Automation 🤖

Linux's [[Ch 08 — Bash Shell Scripting|shell and scripting tools]] let you automate almost anything. Want to deploy an app to 100 servers at midnight automatically? Linux + [[Ch 12 — Cron Jobs & Automation|cron]] makes this easy.

## Problem 4: Consistency 🔄

Every Linux server behaves predictably. A script that works on your laptop works on an AWS server, a Google Cloud VM, or a Raspberry Pi.

## Problem 5: IoT & Edge Computing 📡

Linux runs on tiny devices (Raspberry Pi uses 1GB RAM). The same kernel that runs a 100-core supercomputer also runs a $35 computer.

---

> [!quiz]- 🧠 Quiz 0 — The Story of Linux
> **Answer these before moving on:**
> 
> 1. Who created Linux, and in what year?
> 2. What was the BIG problem with UNIX that motivated Linux?
> 3. What does "open source" mean?
> 4. What did GNU provide that Linux didn't have? What did Linux provide?
> 5. Name 3 places Linux runs that might surprise you.
> 6. Why do companies like Amazon/Google use Linux instead of Windows for servers?
> 
> **→** [[Quiz Answers#Quiz 0 Answers — The Story of Linux|Check Answers]]

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 0.3 — Why Linux Won]] | [[Part 0 — The Story of Linux]] | **Next Part →** [[Part 1 — Linux Fundamentals]]
