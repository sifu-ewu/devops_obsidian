---
aliases: [Users and Groups, useradd, sudo]
tags: [part1, linux-fundamentals, users, groups, sudo]
completed: false
chapter: 5
---

# 💡 Chapter 5 — Users & Groups

> [!info] **Part of** [[Part 1 — Linux Fundamentals]]

---

## 📖 The User System (Analogy)

| Role | Linux Equivalent | Access |
|------|-----------------|--------|
| Hotel Manager | `root` (UID 0) | Master key to everything |
| Hotel Staff | System users (UID 1–999) | Run services, no login |
| Hotel Guests | Regular users (UID 1000+) | Own room + group areas |
| Guest Groups | Groups | VIP guests, maintenance crew |

---

## 📖 The User Database Files

```bash
cat /etc/passwd
# john:x:1001:1001:John Doe:/home/john:/bin/bash
#  │   │  │    │    │         │          └── Login shell
#  │   │  │    │    │         └──────────── Home directory
#  │   │  │    │    └────────────────────── Display name
#  │   │  │    └─────────────────────────── Primary GID
#  │   │  └──────────────────────────────── UID
#  │   └─────────────────────────────────── password in /etc/shadow
#  └─────────────────────────────────────── Username

cat /etc/shadow     # Encrypted passwords (root only)
cat /etc/group      # Groups and their members
```

---

## 💻 Managing Users

```bash
useradd -m -s /bin/bash -c "John Doe" john  # Create user
adduser john                                 # Interactive (Ubuntu/Debian)

passwd john                     # Set/change password
usermod -aG sudo john           # ADD to sudo group (-a = append!)
usermod -aG docker,developers john  # Add to multiple groups
usermod -L john                 # Lock account

userdel john                    # Delete user (keeps home)
userdel -r john                 # Delete user + home + mail

id john                         # Show UID, GID, groups
groups john                     # Show groups
```

---

## 💻 Managing Groups

```bash
groupadd developers             # Create group
gpasswd -a john developers      # Add john to group
gpasswd -d john developers      # Remove john from group
getent group developers         # Show group members
```

---

## 📖 sudo — The Right Way to Be Root

```bash
sudo command                    # Run ONE command as root
sudo -i                         # Open ROOT shell (use sparingly)
sudo !!                         # Re-run last command with sudo
```

> [!warning] **NEVER work as root directly. Use `sudo` instead.**

```bash
# /etc/sudoers syntax (edit with visudo!):
john        ALL=(ALL:ALL) ALL              # Full sudo access
john        ALL=(ALL) NOPASSWD: /bin/apt   # No password for apt
%sudo       ALL=(ALL:ALL) ALL              # sudo GROUP has full access
%developers ALL=(ALL) /usr/sbin/nginx      # developers can control nginx only
```

---

> [!quiz]- 🧠 Quiz 3 — Users & Groups
> 1. Difference between `useradd` and `adduser`?
> 2. What's wrong with always working as root?
> 3. Add john to docker group without removing other groups?
> 4. What does UID 0 represent?
> 5. Why do services like nginx run as `www-data` instead of root?
> 6. Allow alice to run `apt` with sudo without password?
> 
> **→** [[Quiz Answers#Quiz 3 Answers — Users & Groups|Check Answers]]

---

## Related

- [[Ch 04 — File Permissions]] — How permissions interact with users
- [[Ch 17 — Security Hardening]] — Advanced user security
- [[Ch 14 — SSH & Remote Access]] — Remote user access

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 04 — File Permissions]] | [[Part 1 — Linux Fundamentals]] | **Next Part →** [[Part 2 — Linux Intermediate]]
