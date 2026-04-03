---
aliases: [Package Management, apt, yum, dnf]
tags: [part2, linux-intermediate, packages, apt, yum]
completed: false
chapter: 6
---

# 💡 Chapter 6 — Package Management

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 What is a Package Manager? (Analogy)

Think of your phone's **App Store**: central trusted place to get apps, handles dependencies, updates everything with one command.

```
WITHOUT Package Manager:           WITH Package Manager:
1. Go to website                   apt install nginx
2. Find correct version
3. Download manually
4. Install all dependencies
5. Update manually each time
```

---

## 💻 APT — Debian/Ubuntu (Most Common)

```bash
# === UPDATE ===
apt update              # Refresh package list (what's available)
apt upgrade             # Install available upgrades

# GOLDEN RULE: Always apt update before apt install

# === INSTALL ===
apt install nginx                   # Install nginx
apt install -y nginx curl wget git  # Multiple, no confirmation

# === REMOVE ===
apt remove nginx                    # Remove but keep config
apt purge nginx                     # Remove + all config files
apt autoremove                      # Remove unused dependencies

# === SEARCH & INFO ===
apt search nginx                    # Search for packages
apt show nginx                      # Package details
apt list --installed | grep nginx   # Check if installed
dpkg -L nginx                       # What files did nginx install?
dpkg -S /usr/sbin/nginx             # Which package owns this file?

# === CACHE ===
apt clean                           # Remove downloaded package files
```

---

## 💻 YUM/DNF — RHEL/CentOS/Amazon Linux

```bash
yum update -y           # CentOS 7
dnf update -y           # CentOS 8+, Fedora
dnf install nginx -y
rpm -qa | grep nginx    # List all installed RPM packages
```

---

## 📖 Other Installation Methods

```bash
snap install code --classic     # Snap packages
pip3 install ansible            # Python packages
npm install -g pm2              # Node.js packages

# Compile from source (last resort)
./configure && make && sudo make install
```

---

> [!lab]- 🔬 Mini Lab 4: Package Management
> ```bash
> sudo apt update
> sudo apt install -y curl wget git vim tree htop ncdu net-tools jq unzip
> which curl && curl --version
> dpkg -L curl | head -20
> apt search monitoring | head -20
> ```

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 07 — Process Management]]
