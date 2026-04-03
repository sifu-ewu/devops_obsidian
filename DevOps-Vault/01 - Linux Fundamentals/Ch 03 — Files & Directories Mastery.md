---
aliases: [Files and Directories, File Operations, find, tar]
tags: [part1, linux-fundamentals, files, directories]
completed: false
chapter: 3
---

# 💡 Chapter 3 — Files & Directories Mastery

> [!info] **Part of** [[Part 1 — Linux Fundamentals]]

---

## 📖 Navigation Commands

```bash
pwd             # Print Working Directory
cd /var/log     # Change Directory
cd ..           # Go up one level
cd ~            # Go home
cd -            # Go to previous directory

ls              # List files
ls -l           # Long format (detailed)
ls -a           # Show hidden files (files starting with .)
ls -lah         # Combine: long + all + human-readable
```

**Understanding `ls -l` output:**
```
-rw-r--r-- 1 root root 221 Jan 15 2024 /etc/hosts
 ↑          ↑ ↑    ↑    ↑   ↑           ↑
 permissions │ owner group size date    filename
             link count
```

---

## 📖 Hidden Files

Files starting with `.` are hidden — usually config files:
```bash
ls -a ~
# .bashrc       → Bash configuration
# .bash_history → Your command history
# .ssh/         → SSH keys and config
```

---

## 📖 Creating Files & Directories

```bash
touch myfile.txt                        # Create empty file
mkdir mydir                             # Create directory
mkdir -p projects/webApp/src            # Create nested dirs at once

echo "Hello World" > myfile.txt         # Create file with content
echo "More content" >> myfile.txt       # Append to file
```

---

## 📖 Viewing File Contents

```bash
cat file.txt            # Print entire file
less file.txt           # Scroll through (q=quit, /=search)
head -20 file.txt       # First 20 lines
tail -20 file.txt       # Last 20 lines
tail -f /var/log/syslog # LIVE: follow as new lines are added
diff file1.txt file2.txt        # Show differences
```

---

## 📖 Copying, Moving & Deleting

```bash
# COPY
cp source.txt dest.txt              # Copy file
cp -r sourcedir/ destdir/           # Copy directory recursively

# MOVE/RENAME
mv oldname.txt newname.txt          # Rename file
mv file.txt /tmp/                   # Move to directory

# DELETE — BE VERY CAREFUL!
rm file.txt                         # Delete file
rm -r mydir/                        # Delete directory recursively
rm -i file.txt                      # Interactive (ask before deleting)
```

> [!danger] **DANGER ZONE**
> `rm -rf /` → DELETES ENTIRE SYSTEM. Always double-check before running `rm -rf`!

---

## 📖 Finding Files

```bash
find /home -name "*.txt"            # Find all .txt in /home
find / -name "nginx.conf"           # Find nginx config
find /var -type f -size +100M       # Files over 100MB
find /tmp -mtime +7 -delete         # Delete files older than 7 days

locate nginx.conf                   # Faster (uses database)
which python3                       # Find where a command is
whereis nginx                       # Find binary + manual + source
```

---

## 📖 File Links

```bash
# Symbolic (soft) link — like a shortcut
ln -s /var/log/nginx/access.log ./nginx-log

# Hard link — two names for the SAME file
ln original.txt hardlink.txt
```

---

## 📖 Archiving & Compression

```bash
# TAR — c=create, x=extract, v=verbose, f=file, z=gzip
tar -czvf archive.tar.gz /home/john/      # Create gzipped tar
tar -xzvf archive.tar.gz                  # Extract
tar -xzvf archive.tar.gz -C /opt/         # Extract to specific dir

# ZIP
zip -r myfiles.zip /home/john/Documents/
unzip myfiles.zip
```

---

> [!lab]- 🔬 Mini Lab 2: File System Practice
> ```bash
> mkdir -p ~/practice/project/{src,tests,docs,config}
> cd ~/practice/project
> touch src/main.py src/utils.py tests/test_main.py
> echo "# My Project" > docs/README.md
> echo "DEBUG=true" > config/settings.env
> tree ~/practice/
> find ~/practice -name "*.py"
> tar -czvf ~/my_project_backup.tar.gz ~/practice/
> ```
> **Task:** Create a web app directory with `frontend/`, `backend/`, `database/`, `nginx/`, `scripts/`. Inside `scripts/`, create 3 shell scripts. Archive everything.

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 02 — The Linux File System]] | [[Part 1 — Linux Fundamentals]] | **Next →** [[Ch 04 — File Permissions]]
