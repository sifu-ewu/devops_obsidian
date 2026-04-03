---
aliases: [Process Management, ps, top, kill]
tags: [part2, linux-intermediate, processes, monitoring]
chapter: 7
---

# 💡 Chapter 7 — Process Management

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 What is a Process?

When you run a program, it becomes a **process** — a running instance.

```
Program (nginx) → stored on disk (a file)
Process (nginx) → running in memory (using CPU + RAM)

nginx program → master process (PID 1234)
             → worker process (PID 1235)
             → worker process (PID 1236)
```

Every process has a parent. PID 1 is `systemd` ([[Ch 11 — Environment Systemd & Services|systemd]]).

---

## 💻 Viewing Processes

```bash
ps                          # YOUR processes in current terminal
ps aux                      # ALL processes, detailed
ps aux | grep nginx         # Find nginx processes
ps --forest                 # Tree view

pgrep -a nginx              # Get PIDs by name

# STAT codes: R=Running S=Sleeping Z=Zombie T=Stopped
```

---

## 💻 top & htop — Interactive Monitors

```bash
top     # Interactive (q=quit, P=sort CPU, M=sort Memory, k=kill)
htop    # Better: color-coded, mouse support (sudo apt install htop)
```

---

## 📖 Foreground & Background Jobs

```bash
command &           # Start in background
jobs                # List background jobs
fg %1               # Bring job #1 to foreground
bg                  # Resume stopped job in background
Ctrl+Z              # Suspend foreground job
Ctrl+C              # Terminate foreground job

nohup python3 server.py &   # Continues even after logout
```

---

## 📖 Killing Processes

```bash
kill PID            # SIGTERM: polite shutdown (default)
kill -9 PID         # SIGKILL: force kill (cannot be ignored)
kill -1 PID         # SIGHUP: reload config

killall nginx       # Kill ALL nginx processes
pkill nginx         # Kill by name pattern
pkill -9 -u john    # Kill all of john's processes
```

---

## 📖 Process Priority (Nice)

```bash
nice -n 10 python3 heavy_script.py   # Start with low priority
renice -n 5 -p 1234                  # Change running process priority
# Nice range: -20 (highest) to 19 (lowest)
```

---

> [!lab]- 🔬 Mini Lab 5: Process Management
> ```bash
> sleep 1000 & ; sleep 2000 & ; sleep 3000 &
> jobs
> ps aux | grep sleep
> kill %1 ; killall sleep
> sudo lsof -i :80            # What's on port 80?
> sudo ss -tulpn | grep :80   # Alternative
> ```

---

> **Navigation:** **← Prev** [[Ch 06 — Package Management]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 08 — Bash Shell Scripting]]
