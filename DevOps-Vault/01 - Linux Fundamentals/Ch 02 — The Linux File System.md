---
aliases: [Linux File System, Directory Structure, FHS]
tags: [part1, linux-fundamentals, filesystem, directories]
chapter: 2
---

# 💡 Chapter 2 — The Linux File System

> [!info] **Part of** [[Part 1 — Linux Fundamentals]]

---

## 📖 The Most Important Concept: EVERYTHING Is a File

In Linux, **everything is a file**: text documents, programs, your keyboard (`/dev/input/event0`), your hard disk (`/dev/sda`), running processes (`/proc/`), network sockets, and even RAM.

This unification is what makes Linux so powerful and consistent.

---

## 📖 The Tree Structure

Linux has ONE filesystem tree. Everything starts at `/` (called "root" or "slash").

```
/ ─────────────────────── Root directory (top of everything)
│
├── bin/ ──────────────── Essential programs (ls, cp, cat, grep)
├── sbin/ ─────────────── System programs (fdisk, iptables, useradd)
├── etc/ ──────────────── Configuration files (text files!)
│   ├── passwd            User accounts → see [[Ch 05 — Users & Groups]]
│   ├── shadow            Encrypted passwords  
│   ├── hosts             Hostname to IP → see [[Ch 22 — DNS]]
│   ├── fstab             Disk mount points → see [[Ch 10 — Storage & Disk Management]]
│   ├── ssh/              SSH config → see [[Ch 14 — SSH & Remote Access]]
│   └── cron.d/           Scheduled tasks → see [[Ch 12 — Cron Jobs & Automation]]
│
├── home/ ─────────────── Regular user home directories
├── root/ ─────────────── ROOT USER's home (not /home/root!)
├── var/ ──────────────── Variable data (changes frequently)
│   ├── log/              ALL system and app logs → see [[Ch 13 — Logs & System Monitoring]]
│   └── www/              Web files (websites)
│
├── tmp/ ──────────────── Temporary files (wiped on reboot)
├── usr/ ──────────────── User programs (most software goes here)
├── opt/ ──────────────── Optional/third-party software (Docker, etc.)
├── proc/ ─────────────── VIRTUAL: Running kernel/process info
├── sys/ ───────────────── VIRTUAL: Hardware info
├── dev/ ──────────────── Device files (sda, null, zero, random)
├── boot/ ─────────────── Boot files (kernel, GRUB)
├── lib/ ───────────────── System libraries (.so files)
├── mnt/ ──────────────── Manual mount point (external drives)
└── media/ ─────────────── Auto-mount (USB, CDs)
```

---

## 📖 Absolute vs Relative Paths

| Type | Starts from | Example |
|------|-------------|---------|
| **Absolute** | Always from `/` | `/home/john/documents/report.txt` |
| **Relative** | Current location | `documents/report.txt` |

**Special shortcuts:**

| Symbol | Meaning |
|--------|---------|
| `~` | Your home directory (`/home/john`) |
| `.` | Current directory |
| `..` | Parent directory (one level up) |
| `-` | Previous directory you were in |

---

## 💻 Exploring the Filesystem

```bash
pwd                     # Where are you?
ls /                    # List root directory
ls /etc                 # List config directory
ls /var/log             # List log directory

sudo apt install tree
tree /etc -L 2          # Show /etc 2 levels deep

cat /proc/cpuinfo       # Your CPU information
cat /proc/meminfo       # Memory information  
df -h                   # How full are each filesystems?
lsblk                   # What disks/partitions exist?
```

---

> [!quiz]- 🧠 Quiz 1 — File System
> 1. What does `/` mean in Linux?
> 2. Where would you find web server logs?
> 3. Your home is `/home/john`. What does `cd ../alice` do?
> 4. What's in `/proc`? Is it a real directory on disk?
> 5. Where do configuration files go?
> 6. Why is `/dev/null` called "the black hole"?
> 
> **→** [[Quiz Answers#Quiz 1 Answers — File System|Check Answers]]

---

> **Navigation:** **← Prev** [[Ch 01 — Your First Day on Linux]] | [[Part 1 — Linux Fundamentals]] | **Next →** [[Ch 03 — Files & Directories Mastery]]
