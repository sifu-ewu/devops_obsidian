---
aliases: [Text Processing, grep, awk, sed]
tags: [part2, linux-intermediate, grep, awk, sed, text-processing]
completed: false
chapter: 9
---

# 💡 Chapter 9 — Text Processing Power Tools

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 Why These Tools Matter

As a DevOps engineer, you'll constantly deal with log files (millions of lines), config files, CSV/JSON output. These tools process text **without writing a full program**.

---

## 💻 grep — Search Master

```bash
grep "error" /var/log/syslog            # Lines containing "error"
grep -i "error" file.log                # Case insensitive
grep -n "error" file.txt                # Show line numbers
grep -c "error" file.txt                # Count matches
grep -v "error" file.txt                # Invert: lines WITHOUT
grep -r "password" /etc/                # Recursive search
grep -A 3 "ERROR" app.log              # 3 lines AFTER match
grep -B 3 "ERROR" app.log              # 3 lines BEFORE
grep -E "error|warning|critical" file   # OR conditions (extended regex)

# Real DevOps:
grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -rn
# ↑ Find IPs with failed SSH logins — detect brute force!
```

---

## 💻 awk — The Swiss Army Knife

```bash
awk '{print $1}' file.txt               # Print first field
awk -F: '{print $1}' /etc/passwd        # Use : as delimiter
awk '$3 > 100' data.txt                 # Lines where field 3 > 100
awk '{sum += $1} END {print sum}' nums  # Sum a column

# DevOps examples:
df -h | awk 'NR>1 {print $5, $6}'      # Disk usage %
ps aux | awk 'NR>1 {print $2, $3, $11}' # PID, CPU%, command
```

---

## 💻 sed — Stream Editor

```bash
sed 's/old/new/g' file.txt              # Replace all occurrences
sed -i 's/old/new/g' file.txt           # Edit file in-place
sed -i.bak 's/old/new/g' file.txt      # With backup
sed '5d' file.txt                       # Delete line 5
sed '/^#/d; /^$/d' file.txt             # Remove comments AND empty lines

# DevOps examples:
sed -i 's/^Port 22$/Port 2222/' /etc/ssh/sshd_config
sed -i 's/192\.168\.1\.100/192.168.1.200/g' /etc/nginx/nginx.conf
```

---

## 💻 Other Text Tools

```bash
cut -d: -f1 /etc/passwd         # Extract field 1 (delimiter :)
sort file.txt                   # Alphabetical sort
sort -n numbers.txt             # Numeric sort
sort file.txt | uniq -c         # Count duplicates
wc -l file.txt                  # Count lines
tr 'a-z' 'A-Z'                 # Translate characters
echo "a:b:c" | tr ':' ','      # Replace characters
find /tmp -name "*.tmp" | xargs rm   # Build commands from input
tee errors.txt                  # Write to file AND stdout
```

---

> [!lab]- 🔬 Mini Lab 6: Text Processing
> ```bash
> # Create sample access log and practice:
> # 1. Count total requests: wc -l
> # 2. Find 500 errors: grep " 500 "
> # 3. Count per IP: awk '{print $1}' | sort | uniq -c | sort -rn
> # 4. HTTP status distribution: awk '{print $9}' | sort | uniq -c
> ```

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 08 — Bash Shell Scripting]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 10 — Storage & Disk Management]]
