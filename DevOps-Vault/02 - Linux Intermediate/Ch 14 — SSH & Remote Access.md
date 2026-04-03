---
aliases: [SSH, Remote Access, SSH Keys, SSH Config]
tags: [part2, linux-intermediate, ssh, security, remote-access]
chapter: 14
---

# 💡 Chapter 14 — SSH & Remote Access

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 What is SSH?

SSH (Secure Shell) is a **secure encrypted tunnel** between you and a remote computer. Without SSH, you'd need to be physically at the server.

```
Your Laptop ═══════ encrypted tunnel ═══════ Remote Server
(SSH Client)       (SSH = port 22)           (SSH Server/sshd)
```

---

## 💻 Basic Usage

```bash
ssh username@hostname
ssh ubuntu@192.168.1.100
ssh -p 2222 john@server.example.com     # Custom port
ssh john@server "ls /var/log"           # Run command remotely
```

---

## 📖 SSH Keys — THE Most Important DevOps Skill

> [!warning] Password authentication is weak. SSH keys are nearly impossible to brute force, can be used without typing passwords, and are essential for [[Ch 29 — CI-CD Pipelines|CI/CD automation]].

```
Public key  = A padlock you give to someone (share freely!)
Private key = The key to that padlock (NEVER share!)
```

---

## 💻 Generating SSH Keys

```bash
# Ed25519 (RECOMMENDED — modern, faster, more secure)
ssh-keygen -t ed25519 -C "john@company.com"

# Result:
# ~/.ssh/id_ed25519      ← PRIVATE key (chmod 600!)
# ~/.ssh/id_ed25519.pub  ← PUBLIC key (share this)
```

---

## 💻 Distributing Your Public Key

```bash
ssh-copy-id john@server.example.com     # Easiest method
# Now: ssh john@server.example.com → connects WITHOUT password!

# CRITICAL PERMISSIONS:
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519
chmod 600 ~/.ssh/authorized_keys
```

---

## 💻 SSH Config File (~/.ssh/config)

```bash
Host webserver
    HostName 192.168.1.100
    User ubuntu
    IdentityFile ~/.ssh/id_ed25519

Host private-app
    HostName 10.0.1.100
    User ubuntu
    ProxyJump jump-host     # SSH through jump-host!

# Now just: ssh webserver
```

---

## 💻 SSH Server Hardening

```bash
# /etc/ssh/sshd_config — CRITICAL SETTINGS:
Port 2222                       # Change from default 22
PermitRootLogin no              # NEVER allow root SSH!
PasswordAuthentication no       # ONLY key-based auth
MaxAuthTries 3                  # Lock after 3 failures
AllowUsers john alice deploy    # Whitelist users

sshd -t                         # Test config syntax
sudo systemctl reload sshd      # Apply changes
```

> [!danger] Always test SSH config before applying. If wrong, you'll lock yourself out!

---

## Related

- [[Ch 17 — Security Hardening]] — Broader security practices
- [[Ch 04 — File Permissions]] — SSH key file permissions
- [[Ch 27 — VPN Tunneling & Cloud Networking]] — SSH tunneling deep dive

---

> **Navigation:** **← Prev** [[Ch 13 — Logs & System Monitoring]] | [[Part 2 — Linux Intermediate]] | **Next Part →** [[Part 3 — Linux Advanced]]
