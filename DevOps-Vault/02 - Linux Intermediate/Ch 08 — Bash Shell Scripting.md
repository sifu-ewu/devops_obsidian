---
aliases: [Bash Scripting, Shell Script, Bash]
tags: [part2, linux-intermediate, bash, scripting, automation]
chapter: 8
---

# 💡 Chapter 8 — Bash Shell Scripting

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 Why Shell Scripting? (The DevOps Superpower)

```
Without scripting:                  With scripting:
- Deploy manually (30 mins)         - Run one script (2 mins, no errors)
- Check 50 servers manually         - Script checks all in seconds
- Forget a step and break prod      - Script never forgets
```

---

## 📖 Script Basics

```bash
#!/bin/bash
# Shebang — tells OS which interpreter to use
echo "Hello, DevOps World!"
```

```bash
chmod +x myscript.sh    # Make executable
./myscript.sh           # Run it
bash myscript.sh        # Run explicitly (no chmod needed)
source myscript.sh      # Run in CURRENT shell (shares variables)
```

---

## 📖 Variables

```bash
NAME="John"                 # No spaces around =
echo "Hello, $NAME!"        # Double quotes: variable expanded
echo 'Hello, $NAME!'        # Single quotes: literal (NO expansion)

TODAY=$(date +%Y-%m-%d)     # Command substitution
echo $((10 + 5))            # Arithmetic: 15
readonly MAX_RETRIES=3      # Constant
```

## 📖 Special Variables

| Variable | Meaning |
|----------|---------|
| `$0` | Script name |
| `$1`, `$2`... | Positional arguments |
| `$@` | All arguments as list |
| `$#` | Number of arguments |
| `$?` | Exit code of last command (0=success) |
| `$$` | PID of current script |

---

## 📖 Input/Output

```bash
read -p "Enter name: " NAME    # Read with prompt
read -s PASSWORD                # Silent (for passwords)
printf "Name: %s\n" "$NAME"    # Formatted output
```

---

## 📖 Conditionals

```bash
if [ "$A" -gt 10 ]; then
    echo "A is greater than 10"
elif [ "$A" -eq 10 ]; then
    echo "A is 10"
else
    echo "A is less than 10"
fi
```

| Integer | String | File |
|---------|--------|------|
| `-eq` equal | `==` equal | `-f` is file |
| `-ne` not equal | `!=` not equal | `-d` is directory |
| `-gt` greater | `-z` empty | `-e` exists |
| `-lt` less | `-n` not empty | `-r` readable |

---

## 📖 Loops

```bash
# For loop
for item in apple banana cherry; do echo "$item"; done
for file in /var/log/*.log; do wc -l "$file"; done
for ((i=1; i<=10; i++)); do echo $i; done

# While loop
while [ $COUNT -lt 5 ]; do
    echo "Count: $COUNT"; COUNT=$((COUNT + 1))
done

# Read lines from file
while IFS= read -r line; do echo "$line"; done < /etc/hosts
```

---

## 📖 Functions

```bash
check_service() {
    local service=$1
    if systemctl is-active --quiet "$service"; then
        echo "✓ $service is running"; return 0
    else
        echo "✗ $service is NOT running"; return 1
    fi
}
check_service nginx
```

---

## 📖 Error Handling

```bash
set -euo pipefail   # PUT AT TOP OF EVERY SCRIPT!
# -e: exit if any command fails
# -u: error on undefined variables
# -o pipefail: pipe failures count too

trap 'echo "Error at line $LINENO"; exit 1' ERR
trap 'cleanup' EXIT
```

---

> [!devops] ⚡ Real-World Script: Deployment
> See the complete deployment script in the source file — it includes backup, health checks, rollback, and colored logging. This is the kind of script you'll write on the job.

---

> [!quiz]- 🧠 Quiz 4 — Shell Scripting
> 1. What does `#!/bin/bash` mean?
> 2. Difference between single and double quotes?
> 3. How to check if a file exists?
> 4. What does `$?` contain?
> 5. Why use `set -euo pipefail`?
> 6. Difference between `local` and global variables in functions?
> 
> **→** [[Quiz Answers#Quiz 4 Answers — Shell Scripting|Check Answers]]

---

> **Navigation:** **← Prev** [[Ch 07 — Process Management]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 09 — Text Processing]]
