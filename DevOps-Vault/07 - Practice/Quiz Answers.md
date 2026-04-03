---
aliases: [Quiz Answers, Answers]
tags: [part7, practice, quiz, answers]
---

# 🧠 Quiz Answers

> [!info] **Return to** [[Part 7 — Practice]] | [[Home]]

---

## Quiz 0 Answers — The Story of Linux

> From [[Ch 0.4 — Problems Linux Solves]]

| # | Answer |
|---|--------|
| A1 | Linus Torvalds created Linux in 1991. |
| A2 | UNIX was expensive, closed source, and AT&T had monopoly control. |
| A3 | Open source = source code publicly available, free to use, modify, distribute. |
| A4 | GNU provided tools (compiler, shell, utilities). Linux provided the kernel. |
| A5 | Android phones, Tesla cars, ISS, PlayStation, smart TVs, SpaceX rockets. |
| A6 | Cost (free vs $900/server), stability, security, better server tooling. |

---

## Quiz 1 Answers — File System

> From [[Ch 02 — The Linux File System]]

| # | Answer |
|---|--------|
| A1 | `/` is the root directory — starting point of the entire filesystem. |
| A2 | `/var/log/` (web server logs in `/var/log/nginx/` or `/var/log/apache2/`) |
| A3 | `cd ../alice` goes up from `/home/john` to `/home`, then into `/home/alice`. |
| A4 | `/proc` = virtual filesystem with runtime kernel/process info (not on disk). |
| A5 | Configuration files go in `/etc/`. |
| A6 | `/dev/null` discards everything. Used to suppress output: `command > /dev/null`. |

---

## Quiz 2 Answers — Permissions

> From [[Ch 04 — File Permissions]]

| # | Answer |
|---|--------|
| A1 | `rwxr-xr--` → Owner: full, Group: read+execute, Others: read only. |
| A2 | `rwxr-xr-x` = 7(4+2+1) 5(4+0+1) 5(4+0+1) = **755** |
| A3 | `/usr/bin/passwd` has SUID so any user runs it with root privileges (to edit `/etc/shadow`). |
| A4 | `chmod 400 file.txt` |
| A5 | Sets ALL files/dirs in `/var/www` recursively to 755. |
| A6 | Default 644 for files → 666 - 644 = umask **022**. |

---

## Quiz 3 Answers — Users & Groups

> From [[Ch 05 — Users & Groups]]

| # | Answer |
|---|--------|
| A1 | `useradd` = minimal base command. `adduser` = friendly interactive script (Ubuntu/Debian). |
| A2 | Root can accidentally delete system files, security risk if compromised, no audit trail. |
| A3 | `usermod -aG docker john` (-a = APPEND, don't replace groups!) |
| A4 | UID 0 = root user (superuser/administrator). |
| A5 | Principle of least privilege — if nginx compromised, attacker only has `www-data` access. |
| A6 | `alice ALL=(ALL) NOPASSWD: /usr/bin/apt` |

---

## Quiz 4 Answers — Shell Scripting

> From [[Ch 08 — Bash Shell Scripting]]

| # | Answer |
|---|--------|
| A1 | Shebang `#!/bin/bash` — tells OS which interpreter. Without it, OS may use `/bin/sh`. |
| A2 | Double `""`: variables expanded. Single `''`: everything literal. |
| A3 | `if [ -f /path/to/file ]; then ... fi` or `[ -f file ] && ...` |
| A4 | `$?` = exit code of last command. 0 = success, non-zero = error. |
| A5 | `-e`: exit on error, `-u`: error on undefined var, `-o pipefail`: catch pipe failures. |
| A6 | `local` vars visible only inside function. Global vars visible everywhere in script. |

---

## Quiz 5 Answers — OSI & TCP/IP

> From [[Ch 20 — OSI & TCP-IP Models]]

| # | Answer |
|---|--------|
| A1 | Layer 3 — Network layer. |
| A2 | Layer 4 — Transport layer. |
| A3 | UDP — speed > reliability for video. Lost frames better than buffering delays. |
| A4 | SYN → SYN-ACK → ACK (3-way handshake). |
| A5 | Router = Layer 3 (IP). Switch = Layer 2 (MAC). |
| A6 | Convention — IANA assigned standard port numbers so clients know where to connect. |

---

> **Navigation:** [[Part 7 — Practice]] | [[Home]]
