---
aliases: [Kernel, Namespaces, cgroups, Docker Internals]
tags: [part3, linux-advanced, kernel, namespaces, cgroups, containers]
completed: false
chapter: 15
---

# 💡 Chapter 15 — Linux Kernel & Namespaces (Why Docker Exists)

> [!info] **Part of** [[Part 3 — Linux Advanced]]

---

## 📖 The Linux Kernel — The Core

The **kernel** is the central part of Linux that talks directly to hardware. Everything else (bash, nginx, python) talks to the kernel, which talks to hardware.

```
Applications (nginx, python, mysql)
         ↕ system calls
Linux Kernel
         ↕ hardware drivers
Hardware (CPU, RAM, Disk, NIC)
```

---

## 📖 Namespaces — The Magic Behind Containers

Linux **namespaces** isolate resources so one process sees a different "view" than another. This is exactly how [[Ch 28 — Docker & Containers|Docker containers]] work!

```
Without namespaces:          With namespaces (containers):
All processes share:         Container 1 sees:
  - Same hostname              - Its own hostname (web1)
  - Same PID list              - Its own PIDs (starts at 1!)
  - Same network               - Its own network (10.0.0.1)
  - Same filesystem            - Its own filesystem
  - Same users                 - Its own users
```

---

## 💻 Namespace Types

```bash
ls -la /proc/self/ns/

# Types:
# mnt    → Mount namespace (filesystem)
# pid    → PID namespace (process IDs)
# net    → Network namespace (interfaces, routing)
# ipc    → IPC namespace (inter-process communication)
# uts    → UTS namespace (hostname, domain name)
# user   → User namespace (user/group IDs)
# cgroup → cgroup namespace

# Create a new network namespace
sudo ip netns add myns
sudo ip netns list
sudo ip netns exec myns ip addr     # Run command in namespace
sudo ip netns exec myns bash        # Shell in namespace
sudo ip netns delete myns
```

---

## 📖 cgroups — Resource Control

**Control Groups** limit how much CPU, RAM, disk, network a process can use. This is how Docker limits container resources.

```bash
ls /sys/fs/cgroup/
cat /sys/fs/cgroup/memory/memory.limit_in_bytes

# Docker uses cgroups internally:
# docker run --memory=512m --cpus=1 myapp
# → Creates cgroups that limit container to 512MB RAM, 1 CPU
```

---

## 📖 The Linux Boot Process

```
Power On → BIOS/UEFI → GRUB → Linux Kernel → systemd (PID 1) → Login
```

```bash
cat /etc/default/grub               # GRUB settings
systemctl get-default                # Current default target
systemctl set-default multi-user.target  # Server mode (no GUI)
```

---

## Related

- [[Ch 28 — Docker & Containers]] — Uses namespaces + cgroups
- [[Ch 07 — Process Management]] — PIDs and process tree
- [[Ch 11 — Environment Systemd & Services]] — systemd boot target

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 14 — SSH & Remote Access]] | [[Part 3 — Linux Advanced]] | **Next →** [[Ch 16 — Performance Tuning]]
