---
aliases: [File Permissions, chmod, chown, SUID, umask]
tags: [part1, linux-fundamentals, permissions, security]
completed: false
chapter: 4
---

# 💡 Chapter 4 — File Permissions — Linux Security Core

> [!info] **Part of** [[Part 1 — Linux Fundamentals]]

---

## 📖 Why Permissions Exist (Real-World Analogy)

Think of an apartment building:
- The **building owner** (`root`) can access every apartment
- Each **tenant** ([[Ch 05 — Users & Groups|user]]) can only access their own apartment
- **Shared spaces** (group) can be accessed by specific tenants
- **Visitors** (others) can only access the lobby

---

## 📖 Reading Permission Notation

```bash
ls -l /etc/hosts
# -rw-r--r-- 1 root root 221 Jan 15 2024 /etc/hosts

# Position 1:    - = file | d = directory | l = symlink
# Positions 2-4: rw-  = Owner permissions
# Positions 5-7: r--  = Group permissions
# Positions 8-10: r-- = Others permissions
```

---

## 📖 Permission Values

```
r = read    = 4     w = write   = 2     x = execute = 1     - = none = 0

Examples:
rwx = 4+2+1 = 7   (full access)
rw- = 4+2+0 = 6   (read + write)
r-x = 4+0+1 = 5   (read + execute)
r-- = 4+0+0 = 4   (read only)
```

---

## 📖 Common Permission Patterns

| Permission | Numeric | Use Case |
|-----------|---------|----------|
| `rwxr-xr-x` | 755 | Scripts, directories |
| `rw-r--r--` | 644 | Config files, web files |
| `rw-------` | 600 | [[Ch 14 — SSH & Remote Access\|SSH]] private keys! |
| `rwx------` | 700 | Private scripts |
| `rwxrwxrwx` | 777 | **DANGEROUS — avoid!** |

---

## 📖 chmod — Change Permissions

```bash
# Numeric method
chmod 755 script.sh         # rwxr-xr-x
chmod 644 config.txt        # rw-r--r--
chmod 600 ~/.ssh/id_rsa     # rw------- (SSH key!)
chmod -R 755 /var/www/      # Recursive

# Symbolic method
chmod u+x script.sh         # Add execute for user (owner)
chmod g-w file.txt          # Remove write from group
chmod a+x script.sh         # Add execute for ALL
```

---

## 📖 chown — Change Ownership

```bash
chown john file.txt                   # Change owner
chown john:developers file.txt        # Change owner AND group
chown -R www-data:www-data /var/www/  # Recursive (web server files)
```

---

## 📖 Special Permissions

```bash
# SUID — Run as file's owner, not executor
ls -la /usr/bin/passwd    # -rwsr-xr-x  ← 's' = SUID
chmod u+s /path/to/prog  # Set SUID

# SGID — New files inherit directory's group
chmod g+s /shared

# Sticky Bit — Only owner can delete (even if others have write)
ls -ld /tmp               # drwxrwxrwt  ← 't' = sticky bit
chmod +t /shared/folder
```

---

## 📖 umask — Default Permission Mask

```bash
umask               # Show current (usually 022)
# Files: 666 - 022 = 644 (rw-r--r--) ← new files default
# Dirs:  777 - 022 = 755 (rwxr-xr-x) ← new dirs default
```

---

> [!quiz]- 🧠 Quiz 2 — Permissions
> 1. What do `rwxr-xr--` mean for owner, group, others?
> 2. What numeric value is `rwxr-xr-x`?
> 3. Why does `/usr/bin/passwd` have SUID?
> 4. Make only owner able to read a file. Which `chmod`?
> 5. What does `chmod -R 755 /var/www` mean?
> 6. You created a file with 644 permissions. What's your umask?
> 
> **→** [[Quiz Answers#Quiz 2 Answers — Permissions|Check Answers]]

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 03 — Files & Directories Mastery]] | [[Part 1 — Linux Fundamentals]] | **Next →** [[Ch 05 — Users & Groups]]
