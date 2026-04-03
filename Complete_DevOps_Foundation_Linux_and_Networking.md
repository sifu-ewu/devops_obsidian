# 🚀 The Complete DevOps Foundation: Linux & Networking
### From Absolute Zero → Job-Ready DevOps Engineer

> **👋 Hey! Before you start reading:** This guide is written for YOU — someone who uses computers but never went deep. No CS degree needed. No jargon without explanation. Every concept starts with a real-world analogy before the technical part. You WILL understand this.

---

> **📊 What you'll achieve:** After completing this guide, you'll have **~75-80% of the core DevOps foundation** that companies actually test in interviews and use on the job.

---

## 🗺️ How to Use This Guide

```
📖 Read  →  💻 Try it yourself  →  🧠 Quiz yourself  →  🔬 Do the Lab  →  Move on
```

**Each section has:**
- 📖 **Concept** — plain English explanation with analogies
- 💻 **Hands-on** — commands to actually run
- 🧠 **Quick Quiz** — test yourself (answers at end of section)
- 🔬 **Mini Lab** — small project to build
- ⚡ **DevOps Connection** — why this matters in your future job

**One rule: Always type the commands yourself. Never copy-paste when learning.**

---

## 📚 Full Table of Contents

### 🏛️ PART 0: THE STORY — Why Linux Exists
- [Chapter 0.1 — The World Before Linux](#chapter-0-1)
- [Chapter 0.2 — Linus Torvalds & The Birth of Linux](#chapter-0-2)
- [Chapter 0.3 — Why Linux Won The World](#chapter-0-3)
- [Chapter 0.4 — What Problems Linux Solves TODAY](#chapter-0-4)

### 🐧 PART 1: LINUX FUNDAMENTALS (Beginner)
- [Chapter 1 — Your First Day on Linux](#chapter-1)
- [Chapter 2 — The Linux File System](#chapter-2)
- [Chapter 3 — Files & Directories Mastery](#chapter-3)
- [Chapter 4 — File Permissions — Linux Security Core](#chapter-4)
- [Chapter 5 — Users & Groups](#chapter-5)

### ⚙️ PART 2: LINUX INTERMEDIATE
- [Chapter 6 — Package Management](#chapter-6)
- [Chapter 7 — Process Management](#chapter-7)
- [Chapter 8 — Bash Shell Scripting](#chapter-8)
- [Chapter 9 — Text Processing Power Tools](#chapter-9)
- [Chapter 10 — Storage & Disk Management](#chapter-10)
- [Chapter 11 — Environment, Systemd & Services](#chapter-11)
- [Chapter 12 — Cron Jobs & Automation](#chapter-12)
- [Chapter 13 — Logs & System Monitoring](#chapter-13)
- [Chapter 14 — SSH & Remote Access](#chapter-14)

### 🔥 PART 3: LINUX ADVANCED (DevOps Level)
- [Chapter 15 — Linux Kernel & Namespaces](#chapter-15)
- [Chapter 16 — Performance Tuning & Troubleshooting](#chapter-16)
- [Chapter 17 — Security Hardening](#chapter-17)
- [Chapter 18 — Linux Networking Configuration](#chapter-18)

### 🌐 PART 4: NETWORKING FUNDAMENTALS (Beginner)
- [Chapter 19 — What is a Network? (Real World Analogies)](#chapter-19)
- [Chapter 20 — OSI & TCP/IP Models](#chapter-20)
- [Chapter 21 — IP Addressing & Subnetting](#chapter-21)
- [Chapter 22 — DNS — The Internet's Phone Book](#chapter-22)
- [Chapter 23 — HTTP, HTTPS & How Web Works](#chapter-23)

### 🔥 PART 5: NETWORKING ADVANCED (DevOps Level)
- [Chapter 24 — Network Tools & Diagnostics](#chapter-24)
- [Chapter 25 — Firewalls & Security](#chapter-25)
- [Chapter 26 — Load Balancing & Proxies](#chapter-26)
- [Chapter 27 — VPN, Tunneling & Cloud Networking](#chapter-27)

### ⚙️ PART 6: DEVOPS TOOLCHAIN (Built on Linux + Networking)
- [Chapter 28 — Docker & Containers](#chapter-28)
- [Chapter 29 — CI/CD Pipelines](#chapter-29)
- [Chapter 30 — Infrastructure as Code](#chapter-30)
- [Chapter 31 — Monitoring & Observability](#chapter-31)

### 🎯 PART 7: PRACTICE
- [Quizzes & Answers](#quiz-answers)
- [Lab Projects](#lab-projects)
- [DevOps Learning Roadmap](#your-devops-roadmap)

---

---

# 🏛️ PART 0: THE STORY — Why Linux Exists

> **Why read this?** Most people skip history and dive into commands. But knowing WHY something was built makes you 10x better at understanding HOW it works. This section will change how you think about computers.

---

## <a id="chapter-0-1">📖</a> Chapter 0.1 — The World Before Linux (1969–1991)

### 🌍 The State of Computing in the 1960s–70s

Imagine it's 1969. Computers exist, but they are **the size of entire rooms**, cost **millions of dollars**, and are owned only by governments, universities, and huge corporations.

Ordinary people have **no access** to computers. Programming is done by punching holes in cards and handing them to a computer operator.

```
1969 Reality:
┌────────────────────────────────────────────────────────┐
│  Who had computers?    │  Governments, NASA, IBM, MIT  │
│  Size of a computer?   │  Fills an entire room         │
│  Cost?                 │  $1M – $10M (in 1969 dollars) │
│  Could you own one?    │  ABSOLUTELY NOT               │
│  Programming style?    │  Punch cards handed to ops    │
└────────────────────────────────────────────────────────┘
```

### 🔑 UNIX is Born — AT&T Bell Labs (1969)

At **AT&T Bell Labs**, a group of incredibly smart engineers — **Ken Thompson, Dennis Ritchie, and Brian Kernighan** — built an operating system called **UNIX**.

**Why did they build it?**

They were working on a massive project called Multics (a shared computing system) that collapsed. Frustrated, Ken Thompson sneaked some time on an old machine (PDP-7) and built a simpler system — what would become UNIX.

**UNIX was revolutionary:**
- Multiple users could use it at the same time
- It was written in **C language** (also invented at Bell Labs)
- It had a **file system** we still recognize today
- It was **portable** — could run on different hardware

```
UNIX Family Tree (simplified):
                AT&T UNIX (1969)
                     │
         ┌───────────┼────────────┐
         │           │            │
    BSD Unix      System V      Xenix
    (Berkeley)   (AT&T)        (Microsoft!)
         │
    ┌────┴────────────┐
    │                 │
  SunOS           FreeBSD ─── macOS (YES, Mac is Unix!)
```

### 💰 The Big Problem: UNIX Was EXPENSIVE and CLOSED

In the 1980s, AT&T realized UNIX was valuable and started **charging enormous licensing fees**:

- Universities had to pay thousands of dollars per license
- Companies paid even more
- The **source code was secret** — you couldn't see how it worked
- You couldn't modify it or share it

This created a huge problem:
- **Students** couldn't learn from the source code
- **Developers** couldn't build on it freely
- **Companies** were at the mercy of AT&T's pricing
- Innovation was **locked behind a paywall**

### 🎓 The Academic Workaround: MINIX

In 1987, a professor named **Andrew Tanenbaum** wrote a small UNIX-like OS called **MINIX** for teaching purposes. It had one major limitation: Tanenbaum refused to let students modify the core — he wanted it to stay clean for teaching.

A young Finnish student named **Linus Torvalds** used MINIX, wanted more from it, and decided to do something about it.

---

## <a id="chapter-0-2"></a>📖 Chapter 0.2 — Linus Torvalds & The Birth of Linux

### 👦 Who is Linus Torvalds?

```
┌─────────────────────────────────────────────┐
│  Name:        Linus Benedict Torvalds       │
│  Born:        December 28, 1969 — Helsinki  │
│  Nationality: Finnish                       │
│  Education:   University of Helsinki        │
│  Age in 1991: 21 years old                 │
└─────────────────────────────────────────────┘
```

Linus was a 21-year-old **computer science student** at the University of Helsinki in Finland. He was brilliant, introverted, and deeply passionate about computers — especially operating systems.

He had a problem: He wanted to use UNIX on his new personal computer (an Intel 386 PC), but UNIX was too expensive. MINIX worked, but it was limited.

### ✉️ The Famous Email — August 25, 1991

On **August 25, 1991**, Linus posted this message to a USENET newsgroup (like an early internet forum):

```
From: torvalds@klaava.Helsinki.FI (Linus Benedict Torvalds)
To: comp.os.minix
Subject: What would you like to see most in minix?

Hello everybody out there using minix —

I'm doing a (free) operating system (just a hobby, won't be big and 
professional like gnu) for 386(486) AT clones. This has been brewing 
since april, and is starting to get ready. I'd like any feedback on 
things people like/dislike in minix...

— Linus
```

**"Just a hobby, won't be big and professional"**

That hobby became the operating system that runs **the entire modern internet**.

### 🤝 Linux + GNU = Freedom

Around the same time, a hacker named **Richard Stallman** had been building something called the **GNU Project** — a collection of free tools (compiler, editor, utilities) but with NO kernel (the heart of the OS).

Linux provided the **kernel** (the core). GNU provided the **tools**.

Together they created a complete, free operating system: **GNU/Linux**.

```
THE COMPLETE EQUATION:

GNU Tools (Stallman, 1983)    +    Linux Kernel (Torvalds, 1991)
──────────────────────────────────────────────────────────────────
 gcc (compiler)                      Hardware management
 bash (shell)                        Process management  
 ls, cp, grep, awk...                Memory management
 GNU libc (C library)                Device drivers
                │                           │
                └────────────┬──────────────┘
                             │
                     GNU/Linux OS
                    (What we call Linux)
```

### 🌍 The Open Source Revolution

Linus did something radical: **he made Linux free and open source**.

Anyone could:
- ✅ Download the code for FREE
- ✅ Read every line and understand it
- ✅ Modify it for their needs
- ✅ Share their modifications
- ✅ Build products on top of it

This was the **opposite** of how software worked at the time. It created a global community of developers all contributing to one project.

```
CONTRIBUTORS TO LINUX KERNEL (2024):
──────────────────────────────────────
Every release: ~4,000+ developers contribute
Companies paying engineers to contribute:
  ✓ Google   ✓ Microsoft   ✓ Amazon
  ✓ Intel    ✓ IBM         ✓ Red Hat
  ✓ Samsung  ✓ Oracle      ✓ Huawei

Lines of code in Linux kernel: ~30 MILLION
```

---

## <a id="chapter-0-3"></a>📖 Chapter 0.3 — Why Linux Won The World

### 🏆 The Numbers Don't Lie

Let's look at where Linux runs today:

```
WHERE LINUX RUNS (2024 data):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🌐 Web Servers      →  96.4% run Linux
☁️  Cloud Servers   →  ~90% of cloud is Linux
📱 Android Phones   →  Linux kernel (3 billion devices)
🖥️  Supercomputers  →  100% of Top 500 run Linux
🚀 Space            →  SpaceX rockets, ISS use Linux
🏦 Stock Exchanges  →  NYSE, London Stock Ex use Linux
🚗 Cars             →  Tesla, BMW, Toyota infotainment
📺 Smart TVs        →  Samsung, LG use Linux
🎮 Gaming           →  PlayStation 3,4,5 use Linux
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Windows runs on desktops. Linux runs the world.
```

### 🆚 Linux vs Windows vs macOS

| Feature | Linux | Windows | macOS |
|---------|-------|---------|-------|
| **Cost** | FREE | ~$100–200 | Free (but Mac costs $1000+) |
| **Source Code** | Open — anyone reads it | Closed/Secret | Partially open |
| **Security** | Excellent | Frequent patches needed | Good |
| **Stability** | Runs for YEARS without reboot | Regular restarts needed | Good |
| **Customization** | Unlimited | Limited | Very Limited |
| **Resource Usage** | Very low (can run on 512MB RAM) | Heavy (4GB+ recommended) | Heavy |
| **Viruses/Malware** | Very rare | Very common | Occasionally |
| **For Servers** | ✅ Best choice | ❌ Rarely used | ❌ Not for servers |
| **For Development** | ✅ Excellent | ✅ OK | ✅ Excellent |
| **Package Manager** | apt, yum, pacman | ❌ (winget is new) | homebrew |
| **Shell Scripting** | Powerful (bash) | Limited (PowerShell) | bash/zsh |

### 🧠 WHY is Linux so stable and secure?

**1. Separation of privileges**
Linux separates users from the system. You can't accidentally (or maliciously) damage the core OS without root permission.

**2. Open source = more eyes**
When millions of developers can read the code, bugs and security issues get found and fixed faster.

**3. Designed for servers from day 1**
UNIX (Linux's ancestor) was designed for multi-user, always-on systems — not personal desktops.

**4. No bloatware**
Linux installs only what you need. A minimal server install is ~300MB. Windows Server is ~15GB+.

**5. Package management**
Linux has one central trusted place to install software (like an app store, but for everything). Windows has no equivalent — you download random .exe files from the internet.

---

## <a id="chapter-0-4"></a>📖 Chapter 0.4 — What Problems Linux Solves TODAY

### Problem 1: Cost at Scale 💰
> A company runs 10,000 servers. Windows Server license: ~$900/server = **$9,000,000/year**. Linux: **$0**.

This is why Amazon, Google, Facebook all run Linux. They save **hundreds of millions of dollars**.

### Problem 2: Containers & Cloud ☁️
Docker (containers) and Kubernetes are **only possible because of Linux**. Linux features called **namespaces** and **cgroups** (built into the kernel) make containers work. This is the heart of modern cloud computing.

### Problem 3: Automation 🤖
Linux's shell and scripting tools let you automate almost anything. Want to deploy an app to 100 servers at midnight automatically? Linux makes this easy.

### Problem 4: Consistency 🔄
Every Linux server behaves predictably. A script that works on your laptop works on an AWS server, a Google Cloud VM, or a Raspberry Pi.

### Problem 5: IoT & Edge Computing 📡
Linux runs on tiny devices (Raspberry Pi uses 1GB RAM). The same kernel that runs a 100-core supercomputer also runs a $35 computer in your thermostat.

---

### 🧠 Quiz 0 — The Story of Linux

**Answer these before moving on:**

```
Q1: Who created Linux, and in what year?
Q2: What was the BIG problem with UNIX that motivated Linux?
Q3: What does "open source" mean?
Q4: What did GNU provide that Linux didn't have? What did Linux provide?
Q5: Name 3 places Linux runs that might surprise you.
Q6: Why do companies like Amazon/Google use Linux instead of Windows for servers?

[Answers at the end of this document — Quiz 0 Answers]
```

---

---

# 🐧 PART 1: LINUX FUNDAMENTALS

---

## <a id="chapter-1"></a>💡 Chapter 1 — Your First Day on Linux

### 📖 The Big Mental Shift: Linux vs Windows/Mac

If you've used Windows or Mac, you're used to clicking icons, menus, and buttons. Linux has that too (called a **Desktop Environment** — Ubuntu uses GNOME). But the **real power** of Linux is the **Terminal** (also called Command Line, Shell, CLI).

Think of it this way:
```
GUI (Graphical User Interface) = Driving with automatic transmission
CLI (Command Line Interface)   = Driving with manual/stick shift

Automatic: Easy to start, limited control
Manual:    Takes learning, gives full control, faster once you know it
```

As a DevOps engineer, you will use the CLI **constantly**. Servers don't have screens — you connect via terminal and type commands.

### 📖 What Is a Shell?

A **shell** is the program that reads your commands and executes them.

```
You type:   ls
Shell reads: "list files" command
Shell talks to: Linux Kernel
Kernel does: Look at filesystem
Result displayed: Files listed on screen
```

The most common shell is **Bash** (Bourne Again Shell). When you open a terminal, you're in Bash.

### 💻 Opening the Terminal

**Ubuntu/Debian GUI:**
- Press `Ctrl + Alt + T` → Terminal opens
- Or search "Terminal" in apps

**What you see:**
```bash
john@myserver:~$
│    │         │└─ $ = regular user  (# = root/admin user)
│    │         └── ~ = current directory (~ means home directory)
│    └──────────── myserver = machine hostname
└───────────────── john = your username
```

This is called the **prompt**. It's always waiting for your commands.

### 💻 Your First 10 Commands

Type each one and observe what happens:

```bash
# COMMAND 1: Who am I?
whoami
# Output: john (or whatever your username is)

# COMMAND 2: Where am I?
pwd
# Output: /home/john  (your home directory)

# COMMAND 3: What's the date?
date
# Output: Monday March 09 2026

# COMMAND 4: Who is logged in?
who
# Output: shows logged in users

# COMMAND 5: What computer is this?
hostname
# Output: myserver (or your machine name)

# COMMAND 6: What OS/kernel is this?
uname -a
# Output: Linux myserver 5.15.0 ... (kernel version + info)

# COMMAND 7: How long has this been running?
uptime
# Output: 10:30:00 up 5 days, 2:15, 1 user, load average: 0.10, 0.08, 0.05

# COMMAND 8: Display something
echo "Hello, Linux!"
# Output: Hello, Linux!

# COMMAND 9: Clear the screen
clear
# Screen clears (Ctrl+L also works)

# COMMAND 10: Get help for any command
man ls
# Shows manual page for 'ls'. Press 'q' to quit.
```

### 📖 Understanding Command Structure

Every Linux command follows a pattern:

```
command  [options]  [arguments]
   │         │           │
   │         │           └── WHAT to act on (file, directory, etc.)
   │         └──────────── HOW to do it (flags modify behavior)
   └────────────────────── WHAT to do

Examples:
ls             → just list
ls -l          → list with details (-l is an option)
ls -la         → list with details + hidden files
ls -la /var    → list /var directory with details + hidden
```

**Options can be combined:**
```bash
ls -l -a -h    # separate options
ls -lah        # combined (same thing!)
```

### 📖 Getting Help (Super Important!)

```bash
man command         # Full manual (press q to quit)
command --help      # Quick help
command -h          # Short help (for some commands)
info command        # Detailed info (alternative to man)
whatis command      # One-line description
apropos keyword     # Search man pages for keyword

Examples:
man ls
ls --help
whatis grep
apropos "disk usage"    # Find commands related to disk usage
```

### 🔬 Mini Lab 1: Terminal Exploration

**Do this right now:**

```bash
# 1. Open terminal
# 2. Run all 10 commands above
# 3. Try these exploration commands:
history             # See your command history!
history | tail -20  # Last 20 commands
!!                  # Re-run last command
!ls                 # Re-run last command starting with 'ls'
Ctrl+R              # Search command history (type to search)

# 4. Navigate history with arrow keys ↑↓

# 5. Use TAB completion:
# Type: ls /et  then press TAB
# Linux will auto-complete to: ls /etc/

# 6. Try these keyboard shortcuts:
Ctrl+C    # Cancel current command
Ctrl+Z    # Suspend current command
Ctrl+A    # Go to beginning of line
Ctrl+E    # Go to end of line
Ctrl+U    # Clear line
Ctrl+L    # Clear screen
```

**🎯 Task:** Find out how many CPUs your computer has using a command. Hint: look in `/proc/cpuinfo`. Research how!

---

## <a id="chapter-2"></a>💡 Chapter 2 — The Linux File System

### 📖 The Most Important Concept: EVERYTHING Is a File

In Linux, **everything is a file**:
- Text documents → files
- Programs/Applications → files  
- Your keyboard → a file (`/dev/input/event0`)
- Your hard disk → a file (`/dev/sda`)
- A running process → a file in `/proc/`
- A network socket → a file
- RAM → accessible as a file

This unification is what makes Linux so powerful and consistent. One tool (`cat`, `echo`, etc.) can work on any of them.

### 📖 The Tree Structure

Linux has ONE filesystem tree. Everything starts at `/` (called "root" or "slash").

```
Think of it like a company org chart:

         / (Root — CEO of everything)
         │
    ┌────┼────┬────┬────┐
   etc  home var  tmp  usr
    │    │    │
  configs │  logs
       john  
        │
     Documents
     Downloads
     Desktop
```

### 📖 Directory Deep Dive

```
/ ─────────────────────── Root directory (top of everything)
│
├── bin/ ──────────────── Essential programs (ls, cp, cat, grep)
│                         "bin" = binaries = programs
│
├── sbin/ ─────────────── System programs (for admin use only)
│                         fdisk, iptables, useradd
│
├── etc/ ──────────────── Configuration files (text files!)
│   ├── passwd            User accounts
│   ├── shadow            Encrypted passwords  
│   ├── hosts             Hostname to IP mapping
│   ├── fstab             Disk mount points
│   ├── ssh/              SSH server configuration
│   ├── nginx/            Nginx web server config
│   └── cron.d/           Scheduled tasks
│
├── home/ ─────────────── Regular user home directories
│   ├── john/             John's personal space
│   └── alice/            Alice's personal space
│
├── root/ ─────────────── ROOT USER's home (not /home/root!)
│
├── var/ ──────────────── Variable data (changes frequently)
│   ├── log/              ALL system and app logs
│   │   ├── syslog        System messages
│   │   ├── auth.log      Login attempts
│   │   └── nginx/        Web server logs
│   ├── www/              Web files (websites)
│   └── lib/              Application state data
│
├── tmp/ ──────────────── Temporary files (wiped on reboot)
│
├── usr/ ──────────────── User programs (most software goes here)
│   ├── bin/              Non-essential user programs
│   ├── lib/              Program libraries
│   ├── local/            Manually compiled software
│   └── share/            Documentation, icons, etc.
│
├── opt/ ──────────────── Optional/third-party software
│                         (Docker, custom apps often here)
│
├── proc/ ─────────────── VIRTUAL: Running kernel/process info
│   ├── cpuinfo           CPU details
│   ├── meminfo           Memory details
│   └── [number]/         Directory for each running process
│
├── sys/ ───────────────── VIRTUAL: Hardware info
│
├── dev/ ──────────────── Device files
│   ├── sda               First hard disk
│   ├── sda1              First partition of first disk
│   ├── null              Black hole (discard anything sent here)
│   ├── zero              Infinite zeros
│   └── random            Random data
│
├── boot/ ─────────────── Boot files (kernel image, GRUB)
│   └── grub/             Bootloader config
│
├── lib/ ───────────────── System libraries (.so files)
│
├── mnt/ ──────────────── Manual mount point (external drives)
│
└── media/ ─────────────── Auto-mount (USB, CDs)
```

### 📖 Absolute vs Relative Paths

**Absolute path:** Always starts from `/` — works from anywhere
```bash
/home/john/documents/report.txt    # Always means the same thing
/etc/nginx/nginx.conf
/var/log/syslog
```

**Relative path:** Relative to where you currently are
```bash
# If you're in /home/john:
documents/report.txt    # Same as /home/john/documents/report.txt
../alice/               # Goes up one level, then into alice/
./script.sh             # Current directory's script.sh
```

**Special shortcuts:**
```bash
~       # Your home directory (/home/john)
.       # Current directory
..      # Parent directory (one level up)
-       # Previous directory you were in
```

### 💻 Exploring the Filesystem

```bash
# Navigate and explore
pwd                     # Where are you?
ls /                    # List root directory
ls /etc                 # List config directory
ls /var/log             # List log directory

# The 'tree' command (install if needed)
sudo apt install tree
tree /etc -L 2          # Show /etc 2 levels deep

# Explore virtual filesystems
cat /proc/cpuinfo       # Your CPU information
cat /proc/meminfo       # Memory information  
cat /proc/version       # Linux kernel version
ls /proc/               # See running process IDs!

# Check disk structure
df -h                   # How full are each filesystems?
lsblk                   # What disks/partitions exist?
```

### 🧠 Quiz 1 — File System

```
Q1: What does / mean in Linux?
Q2: Where would you find web server logs?
Q3: Your home directory is /home/john. You're currently there.
    What does cd ../alice do?
Q4: What's in /proc? Is it a real directory on disk?
Q5: Where do you put configuration files for your applications?
Q6: /dev/null is called "the black hole". Why?
```

---

## <a id="chapter-3"></a>💡 Chapter 3 — Files & Directories Mastery

### 📖 Navigation Commands

```bash
pwd             # Print Working Directory (where am I?)
cd /var/log     # Change Directory — go to /var/log
cd ..           # Go up one level
cd ~            # Go home
cd -            # Go to previous directory
cd              # (no argument) = go home

ls              # List files
ls -l           # Long format (detailed)
ls -a           # Show hidden files (files starting with .)
ls -h           # Human-readable sizes (KB, MB, GB)
ls -t           # Sort by modification time
ls -S           # Sort by file size
ls -R           # List recursively (all subdirectories)
ls -lah         # Combine: long + all + human-readable

# What does -l output mean?
ls -l /etc/hosts
# -rw-r--r-- 1 root root 221 Jan 15 2024 /etc/hosts
#  ↑          ↑ ↑    ↑    ↑   ↑           ↑
#  permissions │ owner group size date    filename
#              link count
```

### 📖 Hidden Files

Files starting with `.` are hidden in Linux. They're usually config files.

```bash
ls -a ~         # See ALL files in home, including hidden
# You'll see:
# .bashrc       → Bash configuration
# .bash_history → Your command history
# .ssh/         → SSH keys and config
# .gitconfig    → Git configuration
```

### 📖 Creating Files & Directories

```bash
# Create an empty file (or update timestamp if exists)
touch myfile.txt
touch file1.txt file2.txt file3.txt     # Create multiple

# Create directories
mkdir mydir                              # Create one directory
mkdir -p projects/webApp/src            # Create nested dirs at once
mkdir dir1 dir2 dir3                    # Create multiple

# Create file with content
echo "Hello World" > myfile.txt         # Creates file with content
echo "More content" >> myfile.txt       # Appends to file
cat > newfile.txt << EOF                # Multi-line creation
This is line 1
This is line 2
This is line 3
EOF
```

### 📖 Viewing File Contents

```bash
cat file.txt            # Print entire file at once
less file.txt           # Scroll through (q=quit, space=page down, /=search)
more file.txt           # Page through (older, less features than less)
head file.txt           # First 10 lines
head -20 file.txt       # First 20 lines
tail file.txt           # Last 10 lines
tail -20 file.txt       # Last 20 lines
tail -f /var/log/syslog # LIVE: follow as new lines are added

# View without cat (useful for special chars)
xxd file.txt | head     # Hex dump
od -c file.txt          # Octal dump

# Compare files
diff file1.txt file2.txt        # Show differences
diff -u file1.txt file2.txt     # Unified format (used in git patches)
```

### 📖 Copying, Moving & Deleting

```bash
# COPY
cp source.txt destination.txt       # Copy file
cp source.txt /tmp/                 # Copy to directory
cp -r sourcedir/ destdir/           # Copy directory recursively
cp -p file.txt backup.txt           # Preserve permissions/timestamps
cp -i file.txt backup.txt           # Interactive (ask before overwrite)
cp -u *.txt /backup/                # Copy only if newer

# MOVE/RENAME
mv oldname.txt newname.txt          # Rename file
mv file.txt /tmp/                   # Move to directory
mv dir1/ /tmp/dir2/                 # Move directory
mv -i file.txt dest.txt             # Interactive (ask before overwrite)

# DELETE — BE VERY CAREFUL!
rm file.txt                         # Delete file
rm file1.txt file2.txt              # Delete multiple files
rm *.txt                            # Delete all .txt files
rm -r mydir/                        # Delete directory recursively
rm -rf mydir/                       # Force delete (no confirmation!)
rm -i file.txt                      # Interactive (ask before deleting)

# ⚠️  DANGER ZONE:
# rm -rf /    → DELETES ENTIRE SYSTEM (modern Linux protects against this)
# rm -rf /*   → ALSO EXTREMELY DANGEROUS
# ALWAYS double-check before running rm -rf!
```

### 📖 Finding Files

```bash
# find — most powerful, searches filesystem
find /home -name "*.txt"            # Find all .txt in /home
find / -name "nginx.conf"           # Find nginx config
find /var -type f -size +100M       # Files over 100MB in /var
find /tmp -mtime +7 -delete         # Find & delete files older than 7 days
find /etc -name "*.conf" -readable  # Readable .conf files
find . -empty                       # Empty files in current directory
find /home -user john               # Files owned by john
find / -perm 777                    # Files with 777 permissions

# locate — faster but uses database (may be outdated)
locate nginx.conf
updatedb                            # Update locate database

# which — find where a command is
which python3                       # Output: /usr/bin/python3
which nginx

# whereis — find binary + manual + source
whereis nginx                       # nginx: /usr/sbin/nginx /etc/nginx
```

### 📖 File Links

Think of links like **shortcuts** in Windows or **aliases** in Mac.

```bash
# Symbolic (soft) link — like a shortcut
ln -s /var/log/nginx/access.log ./nginx-log    # Create symlink
ls -la nginx-log                               # Shows → target

# Hard link — two names for the SAME file (same data on disk)
ln original.txt hardlink.txt
ls -li original.txt hardlink.txt    # Same inode number!

# DevOps Example: nginx sites
# Sites live in sites-available, symlinked to sites-enabled:
ln -s /etc/nginx/sites-available/myapp /etc/nginx/sites-enabled/myapp
```

### 📖 Archiving & Compression

```bash
# TAR — most common in Linux world
# Flags: c=create, x=extract, v=verbose, f=file, z=gzip, j=bzip2

# Create archives
tar -cvf archive.tar /home/john/          # Create tar (no compression)
tar -czvf archive.tar.gz /home/john/      # Create gzipped tar
tar -cjvf archive.tar.bz2 /home/john/    # Create bzip2 tar

# Extract archives
tar -xvf archive.tar                      # Extract tar
tar -xzvf archive.tar.gz                  # Extract gzipped tar
tar -xzvf archive.tar.gz -C /opt/         # Extract to specific dir

# List contents without extracting
tar -tzvf archive.tar.gz

# ZIP (common for cross-platform)
zip -r myfiles.zip /home/john/Documents/
unzip myfiles.zip
unzip -l myfiles.zip          # List contents

# GZIP — compress single files
gzip bigfile.txt              # Creates bigfile.txt.gz, removes original
gunzip bigfile.txt.gz         # Decompress
gzip -k bigfile.txt           # Keep original too
```

### 🔬 Mini Lab 2: File System Practice

```bash
# Create a project structure:
mkdir -p ~/practice/project/{src,tests,docs,config}
cd ~/practice/project

# Create files
touch src/main.py src/utils.py
touch tests/test_main.py
echo "# My Project" > docs/README.md
echo "DEBUG=true" > config/settings.env

# Explore what you created
tree ~/practice/          # Visual tree

# Practice copying and moving
cp docs/README.md docs/README.bak
mv config/settings.env config/settings.env.bak

# Find files
find ~/practice -name "*.py"
find ~/practice -name "*.bak"

# Archive your project
tar -czvf ~/my_project_backup.tar.gz ~/practice/

# Extract to verify
tar -tzvf ~/my_project_backup.tar.gz    # List contents

# Clean up
rm ~/practice -rf
rm ~/my_project_backup.tar.gz
```

**🎯 Task:** Create a directory structure for a web application with folders: `frontend/`, `backend/`, `database/`, `nginx/`, and `scripts/`. Inside `scripts/`, create 3 empty shell scripts: `deploy.sh`, `backup.sh`, `healthcheck.sh`. Archive the whole thing.

---

## <a id="chapter-4"></a>💡 Chapter 4 — File Permissions — Linux Security Core

### 📖 Why Permissions Exist (Real-World Analogy)

Think of an apartment building:
- The **building owner** (root) can access every apartment
- Each **tenant** (user) can only access their own apartment
- Some **shared spaces** (group) can be accessed by specific tenants
- **Visitors** (others) can only access the lobby

Linux permissions work the same way. Every file has an owner, belongs to a group, and has rules for everyone else.

### 📖 Reading Permission Notation

```bash
ls -l /etc/hosts
# Output:
# -rw-r--r-- 1 root root 221 Jan 15 2024 /etc/hosts
# ↑↑↑↑↑↑↑↑↑↑
# Let's decode this:

Position 1:    - (dash)    = regular file
               d           = directory
               l           = symbolic link
               c           = character device
               b           = block device

Positions 2-4: rw-         = Owner permissions (root)
Positions 5-7: r--         = Group permissions (root group)
Positions 8-10: r--        = Others permissions (everyone else)
```

### 📖 Permission Values

```
r = read    = 4   (can see/open)
w = write   = 2   (can modify/delete)
x = execute = 1   (can run as program)
- = no permission = 0

Examples:
rwx = 4+2+1 = 7   (full access)
rw- = 4+2+0 = 6   (read + write)
r-x = 4+0+1 = 5   (read + execute)
r-- = 4+0+0 = 4   (read only)
--- = 0+0+0 = 0   (no access)
```

### 📖 Common Permission Patterns

```
PERMISSION    NUMERIC    MEANING                       USE CASE
-----------   -------    -------                       --------
rwxrwxrwx      777      Everyone can do everything    DANGEROUS — avoid!
rwxr-xr-x      755      Owner full, others read+exec  Scripts, directories
rw-r--r--      644      Owner rw, others read         Config files, web files
rw-------      600      Owner only (read+write)       SSH private keys!
rwx------      700      Owner full, no one else       Private scripts
r--------      400      Read only (not even owner write)  Critical configs
```

### 📖 chmod — Change Permissions

```bash
# Numeric method
chmod 755 script.sh         # rwxr-xr-x
chmod 644 config.txt        # rw-r--r--
chmod 600 ~/.ssh/id_rsa     # rw------- (SSH key!)
chmod 777 dangerous.sh      # rwxrwxrwx (avoid!)
chmod -R 755 /var/www/      # Recursive: all files in /var/www/

# Symbolic method (easier to remember)
chmod u+x script.sh         # Add execute for user (owner)
chmod g-w file.txt          # Remove write from group
chmod o+r file.txt          # Add read for others
chmod a+x script.sh         # Add execute for ALL (user+group+others)
chmod u=rw,g=r,o= file.txt  # Set exact permissions
```

### 📖 chown — Change Ownership

```bash
chown john file.txt                   # Change owner to john
chown john:developers file.txt        # Change owner AND group
chown :developers file.txt            # Change only group
chown -R www-data:www-data /var/www/html/   # Recursive (web server files)
```

### 📖 Special Permissions (Advanced)

```bash
# SUID (Set User ID) — Run as file's owner, not executor
ls -la /usr/bin/passwd
# -rwsr-xr-x  ← 's' in owner execute = SUID
# When you run passwd, it runs as ROOT even though you're not root
# This allows non-root users to change their own password

chmod u+s /path/to/program    # Set SUID

# SGID (Set Group ID) — New files inherit directory's group
mkdir /shared
chown :developers /shared
chmod g+s /shared
# Now: any file created in /shared belongs to 'developers' group

# Sticky Bit — Only owner can delete (even if others have write)
ls -ld /tmp
# drwxrwxrwt  ← 't' at end = sticky bit
# Anyone can create files in /tmp, but only owner can delete their files
chmod +t /shared/folder
```

### 📖 umask — Default Permission Mask

```bash
umask               # Show current umask (usually 022)

# How umask works:
# Files max: 666 (rw-rw-rw-)  minus umask
# Dirs max:  777 (rwxrwxrwx)  minus umask

# umask 022:
# Files: 666 - 022 = 644 (rw-r--r--)  ← new files default
# Dirs:  777 - 022 = 755 (rwxr-xr-x)  ← new dirs default

# umask 027:
# Files: 666 - 027 = 640 (rw-r-----)
# Dirs:  777 - 027 = 750 (rwxr-x---)
```

### 🧠 Quiz 2 — Permissions

```
Q1: What do the permissions rwxr-xr-- mean for owner, group, and others?
Q2: What numeric value represents rwxr-xr-x?
Q3: Why does /usr/bin/passwd have SUID set?
Q4: You want only the owner to read a file. What chmod command?
Q5: What does chmod -R 755 /var/www mean?
Q6: You created a file. Default permissions are 644. What is your umask?

[Quiz 2 Answers at end]
```

### 🔬 Mini Lab 3: Permissions Playground

```bash
# Create test directory
mkdir ~/permtest && cd ~/permtest

# Create test files
touch file1.txt file2.sh file3.conf

# See default permissions
ls -la

# Practice changing permissions
chmod 600 file3.conf    # Protect config file
chmod 755 file2.sh      # Make script executable
chmod 644 file1.txt     # Normal text file

# Try to see the difference
ls -la

# Create a directory with sticky bit
mkdir /tmp/shared_test
chmod 1777 /tmp/shared_test
ls -ld /tmp/shared_test

# Clean up
cd ~ && rm -rf ~/permtest
```

---

## <a id="chapter-5"></a>💡 Chapter 5 — Users & Groups

### 📖 The User System (Analogy)

Think of a hotel:
- **Root** = Hotel Manager (has master key to everything)
- **System users** = Hotel staff (run specific services, no login)
- **Regular users** = Hotel guests (access their own room)
- **Groups** = Groups of people (VIP guests, staff, maintenance)

### 📖 User Types in Linux

```
ROOT (UID 0):
  - Superuser / Administrator
  - Bypasses ALL permissions
  - Can do anything, including destroy the system
  - Use with extreme care

SYSTEM USERS (UID 1-999):
  - Created for running services (not real people)
  - Usually no login shell
  - Examples: www-data (web server), mysql (database), sshd (SSH)

REGULAR USERS (UID 1000+):
  - Real people
  - Have home directories (/home/username)
  - Limited to their own files + group permissions
```

### 📖 The User Database Files

```bash
cat /etc/passwd
# john:x:1001:1001:John Doe:/home/john:/bin/bash
#  │   │  │    │    │         │          └── Login shell
#  │   │  │    │    │         └──────────── Home directory
#  │   │  │    │    └────────────────────── GECOS (display name)
#  │   │  │    └─────────────────────────── Primary GID
#  │   │  └──────────────────────────────── UID
#  │   └─────────────────────────────────── x = password in /etc/shadow
#  └─────────────────────────────────────── Username

cat /etc/shadow     # Encrypted passwords (root only can read)
cat /etc/group      # Groups and their members
```

### 💻 Managing Users

```bash
# CREATE USER
useradd john                                    # Basic (no home dir!)
useradd -m john                                 # Create with home dir
useradd -m -s /bin/bash john                    # With bash shell
useradd -m -s /bin/bash -c "John Doe" john      # With full name
useradd -m -u 1500 -G sudo,docker john          # Custom UID, groups

adduser john        # Interactive friendly command (Ubuntu/Debian)
                    # Asks for password, name etc.

# SET PASSWORD
passwd john                 # Set/change john's password
passwd                      # Change YOUR OWN password

# MODIFY USER
usermod -s /bin/zsh john            # Change shell
usermod -d /home/newdir john        # Change home directory
usermod -aG sudo john               # ADD to sudo group (-a = append!)
usermod -aG docker,developers john  # Add to multiple groups
usermod -L john                     # Lock account (prefix ! in shadow)
usermod -U john                     # Unlock account

# DELETE USER
userdel john                # Delete user (keeps home dir)
userdel -r john             # Delete user + home + mail

# VIEW USER INFO
id                          # Your own UID, GID, groups
id john                     # john's info
groups                      # Your groups
groups john                 # john's groups
finger john                 # User info (if installed)
```

### 💻 Managing Groups

```bash
groupadd developers             # Create group
groupadd -g 1100 developers     # Create with specific GID
groupmod -n devteam developers  # Rename group
groupdel developers             # Delete group

# Add/remove users from groups
gpasswd -a john developers      # Add john to developers
gpasswd -d john developers      # Remove john from developers

# Show group memberships
cat /etc/group | grep developers
getent group developers
```

### 📖 sudo — The Right Way to Be Root

```bash
# NEVER work as root directly. Use sudo instead.
sudo command                    # Run ONE command as root
sudo -i                         # Open ROOT shell (use sparingly)
sudo -u john command            # Run command as different user
sudo !!                         # Re-run last command with sudo

# Who can use sudo?
cat /etc/sudoers                # Main config (DON'T edit directly!)
visudo                          # SAFE way to edit sudoers

# /etc/sudoers syntax:
# username  HOST=(USER:GROUP) COMMANDS
john        ALL=(ALL:ALL) ALL              # Full sudo access
john        ALL=(ALL) NOPASSWD: /bin/apt  # No password for apt
%sudo       ALL=(ALL:ALL) ALL             # sudo GROUP has full access
%developers ALL=(ALL) /usr/sbin/nginx     # developers can control nginx only
```

### 🧠 Quiz 3 — Users & Groups

```
Q1: What is the difference between useradd and adduser?
Q2: What's wrong with always working as root?
Q3: How do you add john to the docker group WITHOUT removing him from other groups?
Q4: What does UID 0 represent?
Q5: Why do services like nginx run as www-data instead of root?
Q6: You want alice to run apt with sudo but NOT need a password. What sudoers line?
```

---

---

# ⚙️ PART 2: LINUX INTERMEDIATE

---

## <a id="chapter-6"></a>💡 Chapter 6 — Package Management

### 📖 What is a Package Manager? (Analogy)

Think of your phone's **App Store**:
- Central trusted place to get apps
- Handles downloads automatically
- Manages dependencies (App A needs Framework B)
- Updates everything with one command
- Removes cleanly without leftover files

Linux package managers work the same way — but for **everything** (programs, libraries, fonts, drivers).

```
WITHOUT Package Manager:           WITH Package Manager:
1. Go to website                   apt install nginx
2. Find correct version
3. Download .zip/.exe
4. Install manually
5. Find all dependencies
6. Install each dependency
7. Configure manually
8. Update manually each time
```

### 💻 APT — Debian/Ubuntu (The Most Common)

```bash
# === UPDATE ===
apt update              # Refresh package list (what's available)
                        # Does NOT install anything — just refreshes list
apt upgrade             # Install available upgrades
apt full-upgrade        # Upgrade + handle dependency changes
apt dist-upgrade        # Same as full-upgrade

# GOLDEN RULE: Always apt update before apt install

# === INSTALL ===
apt install nginx                   # Install nginx
apt install -y nginx                # Install without confirmation
apt install nginx curl wget git     # Multiple packages
apt install ./mypackage.deb         # Install a local .deb file

# === REMOVE ===
apt remove nginx                    # Remove but keep config files
apt purge nginx                     # Remove + all config files
apt autoremove                      # Remove unused dependencies

# === SEARCH & INFO ===
apt search nginx                    # Search for packages
apt show nginx                      # Package details + dependencies
apt list --installed                # All installed packages
apt list --installed | grep nginx   # Check if nginx installed
dpkg -l                             # Alternative: all installed packages
dpkg -l | grep "^ii" | grep nginx   # Check specific package

# === PACKAGE FILES ===
dpkg -L nginx                       # What files did nginx install?
dpkg -S /usr/sbin/nginx             # Which package owns this file?
dpkg -i package.deb                 # Install a local .deb file directly

# === CACHE MANAGEMENT ===
apt clean                           # Remove downloaded package files
apt autoclean                       # Remove only outdated packages
du -sh /var/cache/apt/              # How much space used by cache
```

### 💻 YUM/DNF — RHEL/CentOS/Amazon Linux

```bash
# CentOS 7 = yum | CentOS 8+, Fedora, RHEL 8+ = dnf
yum update -y                   # Update all (CentOS 7)
dnf update -y                   # Update all (CentOS 8+)

yum install nginx -y
dnf install nginx -y

yum remove nginx
yum search nginx
yum info nginx
rpm -qa | grep nginx            # List all installed RPM packages
rpm -ql nginx                   # Files installed by nginx package
rpm -qf /usr/sbin/nginx         # Which package owns this file?
```

### 📖 Installing Software (Other Methods)

```bash
# SNAP — Ubuntu snap packages
snap install code --classic     # VS Code
snap install docker
snap list                       # Installed snaps
snap refresh                    # Update all snaps
snap remove code

# PIP — Python packages
pip3 install ansible            # Install ansible
pip3 install -r requirements.txt # Install from requirements file
pip3 list                       # Installed python packages

# NPM — Node.js packages
npm install -g pm2              # Install PM2 process manager
npm install express             # Local project package

# Compile from source (last resort)
wget https://example.com/software-1.0.tar.gz
tar -xzvf software-1.0.tar.gz
cd software-1.0/
./configure --prefix=/usr/local
make
sudo make install
```

### 🔬 Mini Lab 4: Package Management

```bash
# Update package list
sudo apt update

# Install useful tools for DevOps
sudo apt install -y \
  curl wget git vim tree \
  htop ncdu net-tools \
  nmap tcpdump \
  jq unzip

# Verify what was installed
which curl
which jq
curl --version
jq --version

# Check what files curl installed
dpkg -L curl | head -20

# Find which package provides a command
dpkg -S $(which curl)

# Search for monitoring tools
apt search monitoring | head -20

# Remove something you don't need
sudo apt remove cowsay 2>/dev/null || echo "cowsay not installed"
sudo apt install cowsay -y
cowsay "I know package management!"
sudo apt purge cowsay
```

---

## <a id="chapter-7"></a>💡 Chapter 7 — Process Management

### 📖 What is a Process? (Analogy)

When you double-click a program, it becomes a **process** — a running instance of that program. Your computer can run hundreds of processes simultaneously.

```
Program (firefox) → stored on disk (a file)
Process (firefox) → running in memory (using CPU + RAM)

You can have ONE program with MULTIPLE processes:
  nginx program → master process (PID 1234)
                → worker process (PID 1235)
                → worker process (PID 1236)
```

### 📖 Process Hierarchy

Every process has a **parent**. The first process (PID 1) is `systemd`, which is the parent of everything.

```
systemd (PID 1)
    ├── sshd (PID 234)
    │     └── bash (PID 892)        ← your SSH session
    │           └── vim (PID 1100)  ← vim running in your session
    ├── nginx (PID 456)
    │     ├── nginx worker (PID 457)
    │     └── nginx worker (PID 458)
    └── cron (PID 789)
```

### 💻 Viewing Processes

```bash
# ps — snapshot of current processes
ps                          # Only YOUR processes in current terminal
ps aux                      # ALL processes, detailed
# a = all users | u = user-oriented format | x = without terminal
ps aux | grep nginx         # Find nginx processes
ps -ef                      # Full format (shows parent PID)
ps -p 1234                  # Specific process
ps --forest                 # Tree view

# Understanding ps aux output:
# USER  PID  %CPU %MEM  VSZ    RSS   TTY  STAT  START  TIME   COMMAND
# root  1234  0.0  0.1  1234  5678   ?    Ss    10:00  0:00   nginx

# STAT codes:
# R = Running   S = Sleeping   D = Disk sleep   Z = Zombie
# T = Stopped   < = High priority   N = Low priority   s = session leader

# pgrep — get PID by name
pgrep nginx             # Returns PID(s) of nginx
pgrep -l nginx          # With name
pgrep -a nginx          # Full command

# pidof
pidof nginx             # Get PID of nginx
```

### 💻 top — Interactive Process Monitor

```bash
top             # Opens interactive monitor
# While in top:
# q = quit
# k = kill a process (enter PID)
# r = renice (change priority)
# P = sort by CPU (default)
# M = sort by Memory
# T = sort by Time
# 1 = show individual CPUs
# u = filter by user
# f = fields management

# top output header:
# top - 10:30:00 up 5 days, 2:15,  2 users,  load average: 0.52, 0.58, 0.59
#        ↑time    ↑uptime             ↑users    ↑1min ↑5min ↑15min avg load
#
# Tasks: 123 total, 1 running, 122 sleeping
# %Cpu(s):  5.3 us,  1.2 sy,  0.0 ni, 93.2 id,  0.3 wa
#            ↑user    ↑system          ↑idle       ↑wait (disk I/O wait)
```

### 💻 htop — Better top (install separately)

```bash
sudo apt install htop
htop
# Color-coded, mouse support, easier to use
# F5 = tree view, F6 = sort, F9 = kill, F10 = quit
```

### 📖 Foreground & Background Jobs

```bash
command &           # Start in background
sleep 100 &         # Background sleep example

jobs                # List background jobs
# [1]+ Running    sleep 100 &
# [2]- Running    sleep 200 &

fg                  # Bring last background job to foreground
fg %1               # Bring job #1 to foreground
fg %2               # Bring job #2 to foreground
bg                  # Resume stopped job in background

# Ctrl+Z = suspend current foreground job (pauses it)
# Ctrl+C = terminate current foreground job

# nohup — run process that survives logout
nohup python3 server.py &           # Continues even if you log out
nohup python3 server.py > output.log 2>&1 &   # Log output

# disown — detach job from shell (won't be killed when shell closes)
python3 server.py &
disown %1
```

### 📖 Killing Processes

```bash
# Signals
kill -l             # List all signals
kill -15 PID        # SIGTERM: polite shutdown (default)
kill PID            # Same as -15
kill -9 PID         # SIGKILL: force kill (cannot be ignored)
kill -1 PID         # SIGHUP: reload config (many daemons respond to this)
kill -2 PID         # SIGINT: same as Ctrl+C
kill -19 PID        # SIGSTOP: pause process
kill -18 PID        # SIGCONT: continue paused process

# Kill by name
killall nginx               # Kill ALL nginx processes
pkill nginx                 # Kill by name pattern
pkill -9 -u john            # Kill all processes by user john
pkill -HUP nginx            # Send reload signal to nginx

# The "cannot be killed" issue:
# If kill -15 PID doesn't work, try kill -9 PID
# Zombie processes CAN'T be killed — kill the parent instead
```

### 📖 Process Priority (Nice)

```bash
# Nice values range: -20 (highest priority) to 19 (lowest)
# Regular users can only increase nice value (lower priority)
# Root can set any value

nice -n 10 python3 heavy_script.py          # Start with low priority
nice -n -10 critical_process &              # High priority (root only)

renice -n 5 -p 1234             # Change running process priority
renice -n 10 -u john            # Lower priority for all of john's processes
```

### 🔬 Mini Lab 5: Process Management

```bash
# Start some background processes
sleep 1000 &
sleep 2000 &
sleep 3000 &

# View them
jobs
ps aux | grep sleep

# Practice killing
kill %1                     # Kill job 1
killall sleep               # Kill remaining sleep processes

# Monitor resources
top &                       # Run top in background (weird, but educational)
# Press q immediately to quit top
# Kill the top process
killall top

# Real world: find what's using a port
sudo lsof -i :80            # What's on port 80?
sudo ss -tulpn | grep :80   # Alternative

# Check system load
uptime
cat /proc/loadavg           # Load average values
```

---

## <a id="chapter-8"></a>💡 Chapter 8 — Bash Shell Scripting

### 📖 Why Shell Scripting? (The DevOps Superpower)

A shell script is a **list of commands saved in a file** that runs automatically. It's how DevOps engineers automate repetitive tasks.

```
Without scripting:                  With scripting:
- Deploy manually (30 mins)         - Run one script (2 mins, no errors)
- Check 50 servers manually         - Script checks all in seconds
- Forget a step and break prod      - Script never forgets
- Come in at 2AM for backup         - Cron job does it at 2AM
```

### 📖 Script Basics

```bash
#!/bin/bash
# The first line is called "shebang" - tells the OS which interpreter to use
# #!/bin/bash    = use bash
# #!/bin/sh      = use sh (POSIX shell, more portable)
# #!/usr/bin/env python3   = use python3

# This is a comment

echo "Hello, DevOps World!"
```

```bash
# Make it executable and run it
chmod +x myscript.sh
./myscript.sh           # Run it (needs execute permission)
bash myscript.sh        # Run with bash explicitly (no chmod needed)
sh myscript.sh          # Run with sh
source myscript.sh      # Run in CURRENT shell (shares variables)
. myscript.sh           # Same as source
```

### 📖 Variables

```bash
#!/bin/bash
# No spaces around = !
NAME="John"                 # String
AGE=25                      # Integer
PI=3.14                     # No float type in bash — treat as string
EMPTY=""                    # Empty string

# Use variables with $
echo $NAME
echo "Hello, $NAME!"        # Double quotes: variable expanded
echo 'Hello, $NAME!'        # Single quotes: literal (NO expansion)

# Command substitution — store command output in variable
TODAY=$(date +%Y-%m-%d)     # Modern syntax (preferred)
TODAY=`date +%Y-%m-%d`      # Old syntax (backticks)
FILES=$(ls /var/log | wc -l)

echo "Today is: $TODAY"
echo "Log files: $FILES"

# Arithmetic
A=10
B=3
echo $((A + B))     # 13
echo $((A * B))     # 30
echo $((A / B))     # 3 (integer division)
echo $((A % B))     # 1 (remainder)
echo $((A ** 2))    # 100 (power)

# Multiple arithmetic
RESULT=$((A * B + 5))

# readonly — constants
readonly MAX_RETRIES=3
# MAX_RETRIES=5   ← This would error!

# unset
unset NAME
echo $NAME          # Prints nothing
```

### 📖 Special Variables

```bash
$0              # Script name/path
$1, $2, $3...   # Positional arguments (passed when calling script)
$@              # All arguments as list
$*              # All arguments as single string
$#              # Number of arguments passed
$?              # Exit code of last command (0=success, non-zero=error)
$$              # PID of current script
$!              # PID of last background command
$USER           # Current username
$HOME           # Home directory
$PATH           # Command search path
$HOSTNAME       # Machine hostname
$RANDOM         # Random number between 0-32767
$LINENO         # Current line number in script

# Example:
#!/bin/bash
echo "Script name: $0"
echo "First arg: $1"
echo "All args: $@"
echo "Arg count: $#"
echo "My PID: $$"
```

### 📖 Input/Output

```bash
# Output
echo "Hello"                        # Print with newline
echo -e "Hello\nWorld"             # -e enables escape sequences
echo -n "No newline"               # -n = no trailing newline
printf "Name: %s, Age: %d\n" "John" 25   # Formatted output

# Input
read VARIABLE                       # Read from user
read -p "Enter your name: " NAME    # With prompt message
read -s PASSWORD                    # Silent (for passwords)
read -t 10 ANSWER                   # Timeout after 10 seconds
read -n 1 CHAR                      # Read only 1 character

# Example:
echo -n "Enter environment (dev/staging/prod): "
read ENV
echo "Deploying to: $ENV"
```

### 📖 Conditionals

```bash
# Basic if
if [ condition ]; then
    # commands
fi

# if-else
if [ condition ]; then
    # commands
else
    # commands
fi

# if-elif-else
if [ condition1 ]; then
    # commands
elif [ condition2 ]; then
    # commands
else
    # commands
fi

# === COMPARISON OPERATORS ===

# Integer comparisons:
-eq     # equal               [ $A -eq $B ]
-ne     # not equal           [ $A -ne $B ]
-gt     # greater than        [ $A -gt $B ]
-lt     # less than           [ $A -lt $B ]
-ge     # greater or equal    [ $A -ge $B ]
-le     # less or equal       [ $A -le $B ]

# String comparisons:
==      # equal               [ "$A" == "$B" ]
!=      # not equal           [ "$A" != "$B" ]
-z      # empty string        [ -z "$A" ]
-n      # not empty           [ -n "$A" ]
<       # alphabetically less (use in [[ ]])
>       # alphabetically greater

# File tests:
-f      # is a regular file        [ -f /etc/hosts ]
-d      # is a directory           [ -d /var/log ]
-e      # exists (any type)        [ -e /etc/nginx ]
-r      # is readable              [ -r file.txt ]
-w      # is writable              [ -w file.txt ]
-x      # is executable            [ -x script.sh ]
-s      # exists and not empty     [ -s file.txt ]
-L      # is a symlink             [ -L /etc/nginx/sites-enabled/app ]

# Double brackets [[ ]] — more powerful, bash-specific
if [[ $NAME == J* ]]; then echo "Name starts with J"; fi
if [[ $NAME =~ ^[A-Z] ]]; then echo "Starts with uppercase"; fi

# Logical operators
if [ $A -gt 0 ] && [ $B -gt 0 ]; then  # AND
if [ $A -gt 0 ] || [ $B -gt 0 ]; then  # OR
if [[ $A -gt 0 && $B -gt 0 ]]; then    # AND (double brackets)
if ! [ -f file.txt ]; then              # NOT
```

### 📖 Loops

```bash
# For loop — iterate over list
for item in apple banana cherry; do
    echo "Fruit: $item"
done

# For loop — over command output
for file in /var/log/*.log; do
    echo "Processing: $file"
    wc -l "$file"
done

# For loop — C style
for ((i=1; i<=10; i++)); do
    echo "Number: $i"
done

# For loop — range
for i in {1..10}; do
    echo $i
done

for i in {0..100..10}; do    # 0 10 20 30... 100
    echo $i
done

# While loop
COUNT=0
while [ $COUNT -lt 5 ]; do
    echo "Count: $COUNT"
    COUNT=$((COUNT + 1))
done

# Until loop (runs UNTIL condition is true)
until [ -f /tmp/ready ]; do
    echo "Waiting for ready file..."
    sleep 2
done
echo "Ready file found!"

# Loop control
for i in {1..10}; do
    if [ $i -eq 5 ]; then
        continue    # Skip this iteration
    fi
    if [ $i -eq 8 ]; then
        break       # Exit loop entirely
    fi
    echo $i
done

# Read lines from file
while IFS= read -r line; do
    echo "Line: $line"
done < /etc/hosts
```

### 📖 Functions

```bash
#!/bin/bash

# Define function
say_hello() {
    local name=$1       # local = only visible inside function
    echo "Hello, $name!"
}

# Function with return value
get_timestamp() {
    echo $(date +%Y%m%d_%H%M%S)
}

# Function with exit code
check_service() {
    local service=$1
    if systemctl is-active --quiet "$service"; then
        echo "✓ $service is running"
        return 0        # Success
    else
        echo "✗ $service is NOT running"
        return 1        # Failure
    fi
}

# Call functions
say_hello "DevOps"
TIMESTAMP=$(get_timestamp)
echo "Timestamp: $TIMESTAMP"

check_service nginx
if [ $? -eq 0 ]; then
    echo "All good!"
else
    echo "Service down!"
fi
```

### 📖 Error Handling

```bash
#!/bin/bash
set -e              # Exit immediately if ANY command fails
set -u              # Error on undefined variables
set -o pipefail     # Pipe failures count too
set -euo pipefail   # All three combined (put at top of every script!)

# Custom error handling
trap 'echo "Error at line $LINENO"; exit 1' ERR
trap 'cleanup' EXIT     # Run cleanup function on exit (even on error)

cleanup() {
    echo "Cleaning up..."
    rm -f /tmp/my_temp_file
}

# Check exit codes explicitly
if ! mkdir /restricted/dir 2>/dev/null; then
    echo "ERROR: Could not create directory"
    exit 1
fi

# || and && for simple error handling
mkdir -p /opt/myapp || { echo "Failed to create dir"; exit 1; }
cd /opt/myapp && echo "Changed to /opt/myapp"
```

### 🔬 Real-World Script: Complete Deployment Script

```bash
#!/bin/bash
# ============================================================
# deploy.sh — Application Deployment Script
# Usage: ./deploy.sh [app_name] [version] [environment]
# Example: ./deploy.sh myapp v1.2.3 production
# ============================================================

set -euo pipefail

# ─── Configuration ────────────────────────────────────────
APP_NAME=${1:-"myapp"}
VERSION=${2:-"latest"}
ENVIRONMENT=${3:-"staging"}
DEPLOY_DIR="/opt/${APP_NAME}"
LOG_FILE="/var/log/deploy_${APP_NAME}.log"
TIMESTAMP=$(date +%Y%m%d_%H%M%S)
BACKUP_DIR="/opt/backups/${APP_NAME}_${TIMESTAMP}"

# ─── Colors for output ────────────────────────────────────
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
BLUE='\033[0;34m'
NC='\033[0m'   # No Color

# ─── Logging Function ─────────────────────────────────────
log() {
    local level=$1
    shift
    local message="$@"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    
    case $level in
        INFO)  echo -e "${GREEN}[INFO]${NC}  $timestamp - $message" | tee -a "$LOG_FILE" ;;
        WARN)  echo -e "${YELLOW}[WARN]${NC}  $timestamp - $message" | tee -a "$LOG_FILE" ;;
        ERROR) echo -e "${RED}[ERROR]${NC} $timestamp - $message" | tee -a "$LOG_FILE" ;;
        STEP)  echo -e "${BLUE}[STEP]${NC}  $timestamp - $message" | tee -a "$LOG_FILE" ;;
    esac
}

# ─── Functions ────────────────────────────────────────────
check_prerequisites() {
    log STEP "Checking prerequisites..."
    
    # Check if running as correct user
    if [ "$USER" != "deploy" ] && [ "$EUID" -ne 0 ]; then
        log ERROR "Must run as 'deploy' user or root"
        exit 1
    fi
    
    # Check required tools
    for tool in nginx systemctl curl; do
        if ! command -v "$tool" &>/dev/null; then
            log ERROR "Required tool not found: $tool"
            exit 1
        fi
    done
    
    log INFO "Prerequisites check passed"
}

backup_current() {
    log STEP "Creating backup..."
    
    if [ -d "$DEPLOY_DIR" ]; then
        mkdir -p "$BACKUP_DIR"
        cp -r "$DEPLOY_DIR"/* "$BACKUP_DIR/"
        log INFO "Backup created at: $BACKUP_DIR"
    else
        log WARN "No existing deployment found, skipping backup"
    fi
}

deploy_application() {
    log STEP "Deploying $APP_NAME version $VERSION to $ENVIRONMENT..."
    
    mkdir -p "$DEPLOY_DIR"
    
    # Download application (example)
    # wget -O /tmp/${APP_NAME}-${VERSION}.tar.gz "https://releases.example.com/${VERSION}.tar.gz"
    # tar -xzvf /tmp/${APP_NAME}-${VERSION}.tar.gz -C "$DEPLOY_DIR"
    
    # Set permissions
    chown -R www-data:www-data "$DEPLOY_DIR"
    chmod -R 755 "$DEPLOY_DIR"
    
    log INFO "Application deployed successfully"
}

health_check() {
    log STEP "Running health check..."
    
    local max_attempts=5
    local attempt=1
    local url="http://localhost:8080/health"
    
    while [ $attempt -le $max_attempts ]; do
        log INFO "Health check attempt $attempt/$max_attempts..."
        
        if curl -sf --max-time 5 "$url" > /dev/null 2>&1; then
            log INFO "✓ Health check PASSED!"
            return 0
        fi
        
        attempt=$((attempt + 1))
        sleep 5
    done
    
    log ERROR "Health check FAILED after $max_attempts attempts"
    return 1
}

rollback() {
    log ERROR "Deployment failed! Rolling back..."
    
    if [ -d "$BACKUP_DIR" ]; then
        rm -rf "$DEPLOY_DIR"
        cp -r "$BACKUP_DIR" "$DEPLOY_DIR"
        systemctl restart "$APP_NAME" || true
        log INFO "Rollback completed"
    else
        log ERROR "No backup found for rollback!"
    fi
}

# ─── Main Execution ───────────────────────────────────────
trap rollback ERR      # Rollback automatically on any error

log STEP "=== Starting deployment of $APP_NAME v$VERSION to $ENVIRONMENT ==="

check_prerequisites
backup_current
deploy_application

if ! health_check; then
    rollback
    exit 1
fi

log INFO "=== Deployment SUCCESSFUL! $APP_NAME v$VERSION is live ==="
```

### 🧠 Quiz 4 — Shell Scripting

```
Q1: What does #!/bin/bash at the top of a script mean?
Q2: What is the difference between single quotes and double quotes?
Q3: How do you check if a file exists before trying to use it?
Q4: What does $? contain?
Q5: Why use set -euo pipefail at the top of scripts?
Q6: What's the difference between local variables and global variables in functions?

[Quiz 4 Answers at end]
```

---

## <a id="chapter-9"></a>💡 Chapter 9 — Text Processing Power Tools

### 📖 Why These Tools Matter (DevOps Daily Use)

As a DevOps engineer, you will constantly deal with:
- Log files with millions of lines
- Config files that need automated changes
- CSV/JSON output from tools
- Reports generated from multiple sources

These tools let you process text **without writing a full program**.

### 💻 grep — Search Master

```bash
# Basic search
grep "error" /var/log/syslog            # Lines containing "error"
grep "ERROR" /var/log/app.log           # Case-sensitive (default)
grep -i "error" /var/log/app.log        # Case insensitive

# Useful flags
grep -n "error" file.txt                # Show line numbers
grep -c "error" file.txt                # Count matching lines (not lines!)
grep -v "error" file.txt                # Invert: lines WITHOUT "error"
grep -l "error" *.log                   # Show filenames only (not content)
grep -r "password" /etc/               # Recursive: search all files
grep -w "error" file.txt               # Whole word only (not "errors")
grep -A 3 "ERROR" app.log              # 3 lines AFTER match
grep -B 3 "ERROR" app.log              # 3 lines BEFORE match
grep -C 3 "ERROR" app.log              # 3 lines before AND after

# Regular expressions
grep "^ERROR" file.txt                  # Lines STARTING with ERROR
grep "error$" file.txt                  # Lines ENDING with error
grep "err.r" file.txt                   # . matches any character
grep "[Ee]rror" file.txt                # E or e followed by rror
grep "[0-9]\{3\}" file.txt              # Three consecutive digits

# Extended regex with -E
grep -E "error|warning|critical" file.txt   # OR conditions
grep -E "err(or)?" file.txt             # Optional group

# Real DevOps use:
grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -rn
# ↑ Find IPs with failed SSH login attempts — detect brute force attacks!

tail -f /var/log/nginx/access.log | grep --line-buffered "500"
# ↑ Watch for HTTP 500 errors in real time
```

### 💻 awk — The Swiss Army Knife of Text

```bash
# awk processes text line by line, field by field
# Default field separator: whitespace
# $0 = entire line, $1 = field 1, $2 = field 2, etc.

# Basic field extraction
awk '{print $1}' file.txt               # Print first field
awk '{print $1, $3}' file.txt           # Print 1st and 3rd
awk '{print NR, $0}' file.txt           # Print with line numbers (NR)

# Custom delimiter
awk -F: '{print $1}' /etc/passwd        # Use : as delimiter
awk -F, '{print $2, $4}' data.csv       # CSV: fields 2 and 4
awk -F'\t' '{print $1}' file.tsv        # Tab-separated

# Conditions
awk 'NR==5' file.txt                    # Print only line 5
awk 'NR>=5 && NR<=10' file.txt          # Print lines 5-10
awk '/error/{print}' file.txt           # Lines matching pattern
awk '$3 > 100' data.txt                 # Lines where field 3 > 100
awk 'NF > 3' file.txt                   # Lines with more than 3 fields

# Calculations
awk '{sum += $1} END {print "Total:", sum}' numbers.txt
awk '{sum += $1; count++} END {print "Average:", sum/count}' numbers.txt

# BEGIN and END blocks
awk 'BEGIN {print "Starting..."} {print $1} END {print "Done!"}' file.txt

# Format output
awk '{printf "%-20s %5d\n", $1, $2}' data.txt  # Column-aligned

# Real DevOps examples:
df -h | awk 'NR>1 {print $5, $6}'              # Disk usage percentages
ps aux | awk 'NR>1 {print $2, $3, $11}'        # PID, CPU%, command
awk -F: '$3 >= 1000 {print $1, $3}' /etc/passwd  # Regular users (UID >= 1000)
netstat -an | awk '/ESTABLISHED/ {print $5}' | cut -d: -f1 | sort | uniq -c
# ↑ Count established connections per IP address
```

### 💻 sed — Stream Editor

```bash
# sed edits text as it streams through
# s/old/new/flags = substitution (most common use)

# Basic substitution
sed 's/old/new/' file.txt               # Replace FIRST occurrence per line
sed 's/old/new/g' file.txt              # Replace ALL occurrences (global)
sed 's/old/new/gi' file.txt             # Case insensitive global
sed 's/old/new/2' file.txt              # Replace only 2nd occurrence

# In-place editing (modify the actual file)
sed -i 's/old/new/g' file.txt           # Edit file directly
sed -i.bak 's/old/new/g' file.txt       # Edit + create .bak backup

# Line operations
sed '5d' file.txt                       # Delete line 5
sed '5,10d' file.txt                    # Delete lines 5-10
sed '/pattern/d' file.txt               # Delete lines matching pattern
sed -n '5,10p' file.txt                 # Print ONLY lines 5-10 (-n suppresses default)
sed '1i\First line' file.txt            # Insert before line 1
sed '$a\Last line' file.txt             # Append after last line
sed '3a\New line after 3' file.txt      # Append after line 3

# Multiple operations
sed -e 's/foo/bar/g' -e 's/baz/qux/g' file.txt
sed '/^#/d; /^$/d' file.txt             # Remove comments AND empty lines

# Real DevOps examples:
# Update port in config file
sed -i 's/^Port 22$/Port 2222/' /etc/ssh/sshd_config

# Enable a commented setting
sed -i 's/^#PasswordAuthentication/PasswordAuthentication/' /etc/ssh/sshd_config

# Replace all occurrences of old server IP with new
sed -i 's/192\.168\.1\.100/192.168.1.200/g' /etc/nginx/nginx.conf

# Remove blank lines
sed '/^[[:space:]]*$/d' file.txt
```

### 💻 Other Text Tools

```bash
# cut — Extract columns
cut -d: -f1 /etc/passwd             # Username (field 1, delimiter :)
cut -d, -f2,4 file.csv              # CSV fields 2 and 4
cut -c1-10 file.txt                 # Characters 1-10 of each line

# sort — Sort lines
sort file.txt                       # Alphabetical
sort -r file.txt                    # Reverse
sort -n numbers.txt                 # Numeric sort
sort -k2 data.txt                   # Sort by column 2
sort -t: -k3 -n /etc/passwd         # Sort /etc/passwd by UID
sort -u file.txt                    # Sort + unique (remove dups)

# uniq — Remove/count duplicates (input must be SORTED!)
sort file.txt | uniq                # Remove duplicates
sort file.txt | uniq -c            # Count occurrences
sort file.txt | uniq -d            # Show only duplicates
sort file.txt | uniq -u            # Show only unique lines

# wc — Count things
wc file.txt                         # Lines words bytes
wc -l file.txt                      # Lines only
wc -w file.txt                      # Words only
ls /var/log | wc -l                 # How many log files?

# tr — Translate/delete characters
echo "hello" | tr 'a-z' 'A-Z'      # Lowercase to uppercase
echo "Hello World" | tr -d ' '     # Delete spaces
echo "a:b:c" | tr ':' ','          # Replace : with ,
cat file.txt | tr -s ' '           # Squeeze multiple spaces to one

# xargs — Build commands from input
find /tmp -name "*.tmp" | xargs rm          # Delete all .tmp files
echo "file1.txt file2.txt" | xargs ls -la  # Run ls on each

# tee — Write to file AND stdout simultaneously
cat /var/log/syslog | grep error | tee errors.txt | wc -l
# ↑ Saves errors to file AND shows count at same time
```

### 🔬 Mini Lab 6: Text Processing Power

```bash
# Create a sample access log
cat > /tmp/access.log << 'EOF'
192.168.1.10 - - [09/Mar/2026:10:00:01] "GET /index.html HTTP/1.1" 200 1234
192.168.1.20 - - [09/Mar/2026:10:00:02] "POST /login HTTP/1.1" 401 567
192.168.1.10 - - [09/Mar/2026:10:00:03] "GET /dashboard HTTP/1.1" 200 8901
192.168.1.30 - - [09/Mar/2026:10:00:04] "GET /missing HTTP/1.1" 404 234
192.168.1.10 - - [09/Mar/2026:10:00:05] "GET /api/data HTTP/1.1" 500 100
192.168.1.20 - - [09/Mar/2026:10:00:06] "POST /login HTTP/1.1" 401 567
192.168.1.40 - - [09/Mar/2026:10:00:07] "GET /index.html HTTP/1.1" 200 1234
192.168.1.30 - - [09/Mar/2026:10:00:08] "GET /about HTTP/1.1" 200 2345
EOF

# 1. Count total requests
wc -l /tmp/access.log

# 2. Find all 500 errors
grep " 500 " /tmp/access.log

# 3. Find all 4xx errors
grep -E " 4[0-9]{2} " /tmp/access.log

# 4. Count requests per IP
awk '{print $1}' /tmp/access.log | sort | uniq -c | sort -rn

# 5. Find most requested URLs
awk '{print $7}' /tmp/access.log | sort | uniq -c | sort -rn

# 6. Count HTTP status codes
awk '{print $9}' /tmp/access.log | sort | uniq -c | sort -rn

# 7. Find IPs with 401 errors (brute force candidates)
grep " 401 " /tmp/access.log | awk '{print $1}' | sort | uniq -c | sort -rn
```

---

## <a id="chapter-10"></a>💡 Chapter 10 — Storage & Disk Management

### 📖 Understanding Storage (Analogy)

```
DISK = A physical storage device (like a filing cabinet)
PARTITION = Dividing the cabinet into sections
FILESYSTEM = How files are organized inside a section
MOUNT = Attaching a section so Linux can use it

Analogy:
Disk          → A physical filing cabinet
Partition     → Drawers in the cabinet
Filesystem    → Filing system within drawer (alphabetical, by date, etc.)
Mount point   → The door you use to access the drawer (/mnt/data)
```

### 💻 Disk Information

```bash
# View disk layout
lsblk                           # Block devices in tree format
lsblk -f                        # With filesystem types and UUIDs
fdisk -l                        # All disks and partitions (root)
parted -l                       # Alternative to fdisk

# Filesystem usage
df -h                           # Human-readable disk usage
df -h /                         # Just root filesystem
df -i                           # Inode usage (important too!)
df -T                           # With filesystem type

# Directory sizes
du -sh /var/                    # Total size of /var
du -sh /var/*                   # Size of each item in /var
du -sh /* | sort -rh | head -10 # Top 10 biggest directories
du -sh /home/* | sort -rh       # Home directory sizes

# Find large files
find / -type f -size +500M 2>/dev/null  # Files > 500MB
find /var -size +100M -exec ls -lh {} \;

# ncdu — interactive disk usage (install separately)
sudo apt install ncdu
ncdu /
```

### 💻 Partitioning

```bash
# fdisk — partition editor (older style, < 2TB disks)
fdisk /dev/sdb      # Open disk for editing
# Commands inside fdisk:
#   p = print partition table
#   n = new partition
#   d = delete partition
#   t = change partition type (82=Linux swap, 83=Linux, 8e=LVM)
#   w = write and exit
#   q = quit without saving

# parted — modern, supports GPT and >2TB
parted /dev/sdb
(parted) print                  # Show partitions
(parted) mklabel gpt            # Create GPT partition table
(parted) mkpart primary ext4 0% 50%    # First partition (50%)
(parted) mkpart primary ext4 50% 100%  # Second partition (remaining)
(parted) quit
```

### 💻 Filesystems

```bash
# Create filesystem (format a partition)
mkfs.ext4 /dev/sdb1             # ext4 (most common Linux filesystem)
mkfs.xfs /dev/sdb2              # XFS (great for large files, used by RHEL)
mkfs.btrfs /dev/sdb3            # Btrfs (modern, snapshots support)
mkfs.vfat -F 32 /dev/sdb4      # FAT32 (USB drives, Windows compatible)

# Filesystem comparison
# ext4: stable, widely supported, good for most uses
# XFS: great for large files, parallel I/O, no shrinking
# Btrfs: snapshots, copy-on-write, still maturing
# ZFS: advanced, enterprise, not in mainline kernel

# Check filesystem
fsck /dev/sdb1                  # Check for errors (must be unmounted!)
fsck -y /dev/sdb1               # Auto-fix errors
e2fsck -f /dev/sdb1             # Force check ext4

# Filesystem info
tune2fs -l /dev/sdb1            # ext4 filesystem info
dumpe2fs /dev/sdb1 | head -30   # Detailed ext4 info
xfs_info /dev/sdb2              # XFS info
```

### 💻 Mounting

```bash
# Temporary mount (lost on reboot)
mount /dev/sdb1 /mnt/data               # Mount partition
mount -t xfs /dev/sdb2 /mnt/data2      # Specify filesystem type
mount -o ro /dev/sdb1 /mnt/data        # Mount read-only
mount                                   # Show all mounted filesystems
umount /mnt/data                        # Unmount
umount -l /mnt/data                     # Lazy unmount (even if busy)

# Find mount point of a file
df /var/log/syslog          # Which filesystem contains this file?

# Permanent mount — /etc/fstab
cat /etc/fstab
# Device          MountPoint  Type  Options    Dump  Pass
# UUID=xxx-xxx    /           ext4  defaults   0     1
# UUID=yyy-yyy    /boot       ext4  defaults   0     2
# UUID=zzz-zzz    /mnt/data   ext4  defaults   0     2
# /swapfile       none        swap  sw         0     0

# Get UUID for fstab (use UUID instead of /dev/sdb1 — more reliable)
blkid /dev/sdb1
# /dev/sdb1: UUID="a1b2c3d4-..." TYPE="ext4"

# Add to fstab:
echo 'UUID=a1b2c3d4-xxxx /mnt/data ext4 defaults 0 2' >> /etc/fstab
mount -a        # Mount everything in fstab (test your entry!)
```

### 💻 LVM — Logical Volume Manager (DevOps Essential!)

**Why LVM?** Without LVM, if your disk fills up, you're stuck. With LVM, you can resize volumes **without downtime**, add new disks, and create snapshots.

```
Physical Disk(s) → Physical Volume(s) → Volume Group → Logical Volume(s)

Example:
/dev/sdb (500GB) ─┐
                   ├─ Volume Group "data_vg" (800GB total)
/dev/sdc (300GB) ─┘   ├─ Logical Volume "app_lv" (200GB) → /opt/app
                       ├─ Logical Volume "db_lv" (400GB)  → /var/lib/mysql
                       └─ Logical Volume "log_lv" (100GB) → /var/log
```

```bash
# Step 1: Create Physical Volumes
pvcreate /dev/sdb /dev/sdc
pvdisplay                       # Show PVs
pvs                             # Summary

# Step 2: Create Volume Group
vgcreate data_vg /dev/sdb /dev/sdc
vgdisplay
vgs                             # Summary

# Step 3: Create Logical Volumes
lvcreate -L 200G -n app_lv data_vg      # 200GB named app_lv
lvcreate -L 400G -n db_lv data_vg       # 400GB named db_lv
lvcreate -l 100%FREE -n log_lv data_vg  # Use ALL remaining space
lvdisplay
lvs                             # Summary

# Step 4: Create filesystem and mount
mkfs.ext4 /dev/data_vg/app_lv
mkfs.ext4 /dev/data_vg/db_lv
mount /dev/data_vg/app_lv /opt/app

# Step 5: Extend volume (disk getting full → add space with NO DOWNTIME!)
lvextend -L +100G /dev/data_vg/db_lv     # Add 100GB
resize2fs /dev/data_vg/db_lv            # Grow ext4 filesystem
# OR for XFS:
xfs_growfs /var/lib/mysql               # Grow XFS filesystem

# Snapshots (for backups)
lvcreate -L 10G -s -n db_snapshot /dev/data_vg/db_lv
# Take database backup from snapshot while production runs!
```

---

## <a id="chapter-11"></a>💡 Chapter 11 — Environment, Systemd & Services

### 💻 Environment Variables

```bash
env                             # All environment variables
printenv PATH                   # Specific variable
echo $PATH                      # Same

# Set temporarily
export MY_VAR="hello"           # Available in current shell + children
MY_VAR="hello"                  # Only current shell

# Permanent (for current user)
echo 'export MY_VAR="hello"' >> ~/.bashrc
source ~/.bashrc                # Apply now without restart

# System-wide
echo 'MY_VAR=hello' | sudo tee -a /etc/environment
# Or create /etc/profile.d/myvars.sh
```

### 💻 Systemd — The Service Manager

```bash
# The basics
systemctl start nginx           # Start a service
systemctl stop nginx            # Stop a service
systemctl restart nginx         # Restart (stop then start)
systemctl reload nginx          # Reload config (usually no downtime)
systemctl status nginx          # Detailed status

systemctl enable nginx          # Auto-start on boot
systemctl disable nginx         # Don't auto-start
systemctl enable --now nginx    # Enable AND start immediately

systemctl is-active nginx       # active / inactive
systemctl is-enabled nginx      # enabled / disabled

# List services
systemctl list-units --type=service         # All loaded services
systemctl list-units --type=service --state=running  # Only running
systemctl list-unit-files | grep nginx      # Find nginx unit file

# System control
systemctl daemon-reload         # ALWAYS run after changing unit files!
systemctl reboot
systemctl poweroff
```

### 📖 Creating a Custom Systemd Service (DevOps Must-Know!)

```bash
# Create: /etc/systemd/system/myapp.service
sudo vim /etc/systemd/system/myapp.service
```

```ini
[Unit]
Description=My Web Application
Documentation=https://github.com/mycompany/myapp
After=network.target postgresql.service    # Start after network and db
Requires=postgresql.service               # Hard dependency on postgres

[Service]
Type=simple                         # simple, forking, oneshot, notify
User=www-data                       # Run as this user (NOT root!)
Group=www-data
WorkingDirectory=/opt/myapp
ExecStart=/usr/bin/node /opt/myapp/server.js
ExecReload=/bin/kill -HUP $MAINPID  # Reload command
Restart=always                      # always, on-failure, on-abnormal
RestartSec=5                        # Wait 5s before restart
StartLimitInterval=60               # In 60 seconds...
StartLimitBurst=3                   # ...allow max 3 restarts

# Resource limits
MemoryLimit=512M
CPUQuota=50%

# Environment
Environment=NODE_ENV=production
Environment=PORT=3000
EnvironmentFile=/opt/myapp/.env     # Load from file

# Logging
StandardOutput=journal
StandardError=journal
SyslogIdentifier=myapp

[Install]
WantedBy=multi-user.target          # Start in normal multi-user mode
```

```bash
# Apply and start
sudo systemctl daemon-reload
sudo systemctl enable myapp
sudo systemctl start myapp
sudo systemctl status myapp
```

### 💻 journalctl — Reading Logs

```bash
journalctl                          # All logs (oldest first)
journalctl -r                       # Reverse (newest first)
journalctl -f                       # Follow live (like tail -f)
journalctl -n 100                   # Last 100 lines
journalctl -u nginx                 # Logs for nginx service
journalctl -u nginx -f              # Follow nginx logs live
journalctl -u nginx -n 50           # Last 50 lines of nginx

# Time filtering
journalctl --since "1 hour ago"
journalctl --since "2026-03-01" --until "2026-03-09"
journalctl --since today
journalctl --since yesterday

# Priority filtering
journalctl -p err                   # Only errors
journalctl -p warning               # Only warnings and above
journalctl -p 0..3                  # Emergency to error

# System-wide
journalctl -k                       # Kernel messages only
journalctl -b                       # Current boot only
journalctl -b -1                    # Previous boot

# Disk management
journalctl --disk-usage             # How much space logs use
journalctl --vacuum-size=500M       # Trim logs to 500MB
journalctl --vacuum-time=7d         # Remove logs older than 7 days
```

---

## <a id="chapter-12"></a>💡 Chapter 12 — Cron Jobs & Automation

### 📖 What are Cron Jobs? (Analogy)

Cron is like an **alarm clock for your computer**. You set it to run a command at a specific time, repeatedly. It's how DevOps engineers automate:
- Daily database backups
- Hourly log rotation
- Weekly security updates
- Continuous health checks

### 📖 Cron Syntax Deep Dive

```
┌────────── Minute (0-59)
│ ┌──────── Hour (0-23)
│ │ ┌────── Day of Month (1-31)
│ │ │ ┌──── Month (1-12 or jan,feb,mar...)
│ │ │ │ ┌── Day of Week (0-7, both 0 and 7=Sunday, or sun,mon,tue...)
│ │ │ │ │
* * * * *  command

Special values:
*       = any value (every)
*/5     = every 5 units
1,3,5   = specific values (1, 3, and 5)
1-5     = range (1 through 5)
```

### 💻 Cron Examples

```bash
# Edit crontab
crontab -e          # Edit YOUR crontab (opens in editor)
crontab -l          # List your crontab
crontab -r          # REMOVE your crontab (careful!)
sudo crontab -u john -e     # Edit john's crontab (as root)

# TIMING EXAMPLES:
# Run every minute:
* * * * * /opt/scripts/check.sh

# Run every 5 minutes:
*/5 * * * * /opt/scripts/check.sh

# Run at 2:30 AM every day:
30 2 * * * /opt/scripts/backup.sh

# Run at midnight on Sundays:
0 0 * * 0 /opt/scripts/weekly_report.sh
0 0 * * sun /opt/scripts/weekly_report.sh   # Same, with name

# Run at 9 AM on weekdays (Mon-Fri):
0 9 * * 1-5 /opt/scripts/morning_job.sh

# Run on 1st of every month at 3 AM:
0 3 1 * * /opt/scripts/monthly.sh

# Run every 15 minutes during business hours (9AM-5PM, Mon-Fri):
*/15 9-17 * * 1-5 /opt/scripts/business_check.sh

# Special keywords (easier to remember):
@reboot     /opt/scripts/startup.sh         # Run once at boot
@daily      /opt/scripts/daily.sh           # Daily at midnight
@weekly     /opt/scripts/weekly.sh          # Weekly on Sunday midnight
@monthly    /opt/scripts/monthly.sh         # 1st of month at midnight
@hourly     /opt/scripts/hourly.sh          # Every hour at :00

# ALWAYS log output! Cron errors are silent without logging:
30 2 * * * /opt/scripts/backup.sh >> /var/log/backup.log 2>&1
#                                              ↑ stderr to stdout ↑ both to file

# Use full paths in cron (PATH is limited):
30 2 * * * /usr/bin/python3 /opt/scripts/backup.py >> /var/log/backup.log 2>&1
```

### 🔬 Mini Lab 7: Cron Jobs

```bash
# Create a monitoring script
cat > /opt/disk_monitor.sh << 'EOF'
#!/bin/bash
THRESHOLD=80
LOGFILE="/var/log/disk_monitor.log"
DATE=$(date '+%Y-%m-%d %H:%M:%S')

while IFS= read -r line; do
    USAGE=$(echo "$line" | awk '{gsub(/%/,""); print $5}')
    MOUNT=$(echo "$line" | awk '{print $6}')
    
    if [ "$USAGE" -ge "$THRESHOLD" ] 2>/dev/null; then
        echo "$DATE WARNING: $MOUNT is ${USAGE}% full!" >> "$LOGFILE"
    fi
done < <(df -h | tail -n +2)
EOF

chmod +x /opt/disk_monitor.sh

# Test it
/opt/disk_monitor.sh
cat /var/log/disk_monitor.log

# Add to crontab (every 5 minutes)
(crontab -l 2>/dev/null; echo "*/5 * * * * /opt/disk_monitor.sh") | crontab -

# Verify
crontab -l
```

---

## <a id="chapter-13"></a>💡 Chapter 13 — Logs & System Monitoring

### 📖 Why Logs Are Your Best Friend

Logs are the **flight recorder** of your system. When things break in production (and they will), logs tell you:
- What happened
- When it happened
- What caused it
- What the system was doing at the time

### 💻 Key Log Files

```bash
# System logs
/var/log/syslog             # General system activity (Ubuntu/Debian)
/var/log/messages           # General system activity (RHEL/CentOS)
/var/log/kern.log           # Kernel messages
/var/log/dmesg              # Boot messages + hardware
dmesg                       # View kernel ring buffer (recent boot messages)
dmesg -T                    # With timestamps

# Authentication logs
/var/log/auth.log           # SSH logins, sudo, su (Ubuntu/Debian)
/var/log/secure             # Same for RHEL/CentOS

# Application logs
/var/log/nginx/access.log   # All HTTP requests to nginx
/var/log/nginx/error.log    # Nginx errors
/var/log/apache2/           # Apache logs
/var/log/mysql/             # MySQL logs
/var/log/postgresql/        # PostgreSQL logs

# Package management
/var/log/apt/history.log    # What packages were installed/removed
/var/log/dpkg.log           # Low-level dpkg operations
```

### 💻 Log Analysis

```bash
# Monitor live
tail -f /var/log/syslog
tail -f /var/log/nginx/access.log
journalctl -f -u nginx

# Search logs
grep "ERROR" /var/log/syslog
grep "Failed password" /var/log/auth.log        # SSH brute force attempts
grep "refused connect" /var/log/nginx/error.log

# Find brute force attackers
grep "Failed password" /var/log/auth.log | \
  awk '{print $11}' | sort | uniq -c | sort -rn | head -10
# Output: number_of_attempts  IP_address

# Check for SSH login successes
grep "Accepted" /var/log/auth.log

# Nginx traffic analysis
awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -rn | head -10
# Top 10 IPs by request count

awk '{print $9}' /var/log/nginx/access.log | sort | uniq -c | sort -rn
# HTTP status code distribution

# Count log lines from today
grep "$(date '+%b %e')" /var/log/syslog | wc -l
```

### 💻 System Monitoring Commands

```bash
# CPU monitoring
top                             # Interactive (press P to sort by CPU)
htop                            # Enhanced interactive
mpstat 1 5                      # CPU stats every 1 sec, 5 times
sar -u 1 10                     # CPU usage 10 times at 1-sec intervals
vmstat 1 5                      # Virtual memory stats

# Memory monitoring
free -h                         # Memory + swap usage
free -h -s 2                    # Refresh every 2 seconds
cat /proc/meminfo               # Detailed memory info
vmstat -s                       # Memory stats
sar -r 1 10                     # Memory usage history

# Disk I/O monitoring
iostat -xz 1                    # Extended I/O stats (install sysstat)
iotop                           # I/O usage per process (like top for disk)
sar -d 1 10                     # Disk activity

# Network monitoring
ss -s                           # Network stats summary
sar -n DEV 1 5                  # Network interface stats
nethogs                         # Network per process (install)
iftop                           # Network connections (install)
nload                           # Bandwidth in/out (install)
```

### 🔬 Full Monitoring Script

```bash
#!/bin/bash
# system_monitor.sh — Comprehensive System Health Report

print_header() {
    echo "=================================================="
    echo "  SYSTEM HEALTH REPORT — $(date '+%Y-%m-%d %H:%M:%S')"
    echo "=================================================="
}

print_section() {
    echo ""
    echo "── $1 ─────────────────────────────────────────"
}

print_header

print_section "SYSTEM INFO"
echo "Hostname:  $(hostname)"
echo "OS:        $(cat /etc/os-release | grep PRETTY_NAME | cut -d'"' -f2)"
echo "Kernel:    $(uname -r)"
echo "Uptime:    $(uptime -p)"

print_section "CPU LOAD"
echo "Load Avg:  $(cat /proc/loadavg | awk '{print $1, $2, $3}')"
echo "CPU Count: $(nproc)"
LOAD=$(cat /proc/loadavg | awk '{print $1}')
CPUS=$(nproc)
if (( $(echo "$LOAD > $CPUS" | bc -l) )); then
    echo "⚠️  WARNING: System is overloaded!"
fi

print_section "MEMORY"
free -h | grep -E "Mem|Swap"
MEM_USED=$(free | awk '/Mem:/{printf "%.0f", $3/$2*100}')
echo "Memory Used: ${MEM_USED}%"
[ "$MEM_USED" -gt 90 ] && echo "⚠️  WARNING: Memory critically high!"

print_section "DISK USAGE"
df -h | grep -v tmpfs | awk 'NR>1 {
    usage = substr($5, 1, length($5)-1)
    if (usage+0 >= 80) print "⚠️  WARNING:", $6, "is", $5, "full"
    else print "OK:", $6, "-", $5, "used"
}'

print_section "TOP 5 PROCESSES (CPU)"
ps aux --sort=-%cpu | head -6

print_section "LAST 5 AUTH EVENTS"
tail -5 /var/log/auth.log 2>/dev/null || journalctl -u sshd -n 5 --no-pager
```

---

## <a id="chapter-14"></a>💡 Chapter 14 — SSH & Remote Access

### 📖 What is SSH? (Analogy)

SSH (Secure Shell) is like a **secure telephone line** between you and a remote computer. Without SSH, you'd need to be physically at the server to type commands. With SSH, you can manage servers from anywhere in the world securely.

```
Your Laptop ══════════════ encrypted tunnel ══════════════ Remote Server
(SSH Client)              (SSH = port 22)                  (SSH Server/sshd)
```

### 💻 Basic SSH Usage

```bash
# Connect
ssh username@hostname
ssh ubuntu@192.168.1.100                # By IP
ssh -p 2222 john@server.example.com     # Custom port
ssh john@server "ls /var/log"           # Run command without interactive session

# SSH options
ssh -v john@server          # Verbose (debug connection problems)
ssh -X john@server          # Forward GUI applications (X11)
ssh -A john@server          # Forward SSH agent (for jumping through servers)
ssh -L 8080:localhost:80 john@server   # Local port forwarding
```

### 📖 SSH Keys — THE Most Important DevOps Skill

**Password authentication is weak.** SSH keys are:
- Nearly impossible to brute force (4096-bit RSA)
- Can be used without typing passwords
- Can be restricted (only allow specific commands)
- Essential for automation (CI/CD pipelines)

```bash
# KEY PAIR = PRIVATE KEY + PUBLIC KEY
# Private key: YOURS ALONE. Never share it. Keep it secret.
# Public key: Share freely with servers you want to access.

# Analogy:
# Public key  = A padlock you give to someone
# Private key = The key to that padlock (only you have it)
# Server puts the padlock on their door
# You unlock it with your key to prove you're the owner
```

### 💻 Generating SSH Keys

```bash
# Generate RSA key (traditional, widely supported)
ssh-keygen -t rsa -b 4096 -C "john@company.com"
# -t = type (rsa, ed25519, ecdsa)
# -b = bits (higher = more secure but slower)
# -C = comment (email/description)

# Generate Ed25519 key (modern, faster, more secure, RECOMMENDED)
ssh-keygen -t ed25519 -C "john@company.com"

# When prompted:
# "Enter file in which to save the key": Press Enter (use default ~/.ssh/id_ed25519)
# "Enter passphrase": Enter a password (optional but recommended for security)

# Result:
ls -la ~/.ssh/
# -rw------- 1 john john 411 Mar 9 10:00 id_ed25519      ← PRIVATE (600 perms!)
# -rw-r--r-- 1 john john 102 Mar 9 10:00 id_ed25519.pub  ← PUBLIC (can share)
```

### 💻 Distributing Your Public Key

```bash
# Method 1: ssh-copy-id (easiest)
ssh-copy-id john@server.example.com
ssh-copy-id -i ~/.ssh/id_ed25519.pub john@192.168.1.100

# What this does: appends your public key to server's ~/.ssh/authorized_keys

# Method 2: Manual
cat ~/.ssh/id_ed25519.pub
# Copy the output, then on the server:
mkdir -p ~/.ssh
echo "paste-your-public-key-here" >> ~/.ssh/authorized_keys
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys

# Test
ssh john@server.example.com     # Should connect WITHOUT password!

# CRITICAL PERMISSIONS (SSH will refuse to work if wrong!):
chmod 700 ~/.ssh                    # Directory: owner only
chmod 600 ~/.ssh/id_ed25519         # Private key: owner read/write only
chmod 644 ~/.ssh/id_ed25519.pub     # Public key: readable
chmod 600 ~/.ssh/authorized_keys    # Authorized keys: owner only
chmod 600 ~/.ssh/config             # Config file: owner only
```

### 💻 SSH Config File (~/.ssh/config)

```bash
# This file makes SSH much more convenient
cat ~/.ssh/config

# Example config:
Host webserver
    HostName 192.168.1.100
    User ubuntu
    Port 22
    IdentityFile ~/.ssh/id_ed25519

Host db-server
    HostName 10.0.0.50
    User postgres
    Port 2222
    IdentityFile ~/.ssh/db_key

Host jump-host
    HostName bastion.company.com
    User ec2-user
    IdentityFile ~/.ssh/aws-key.pem

Host private-app
    HostName 10.0.1.100
    User ubuntu
    ProxyJump jump-host     # SSH THROUGH jump-host to reach private-app!

# Now instead of:
# ssh -i ~/.ssh/id_ed25519 ubuntu@192.168.1.100
# You just type:
ssh webserver

# Instead of complex jump commands:
# ssh -J ec2-user@bastion.company.com ubuntu@10.0.1.100
# You just type:
ssh private-app
```

### 💻 SSH Server Hardening

```bash
# Edit SSH server config
sudo vim /etc/ssh/sshd_config

# CRITICAL SECURITY SETTINGS:
Port 2222                       # Change from default 22 (minor security)
PermitRootLogin no              # NEVER allow root to SSH in!
PasswordAuthentication no       # ONLY key-based auth
PubkeyAuthentication yes        # Enable key auth
AuthorizedKeysFile .ssh/authorized_keys
MaxAuthTries 3                  # Lock after 3 failed attempts
LoginGraceTime 20               # Disconnect if not authenticated in 20s
AllowUsers john alice deploy    # Whitelist specific users
AllowGroups ssh-users           # Or whitelist by group
ClientAliveInterval 300         # Send keepalive every 5 minutes
ClientAliveCountMax 2           # Disconnect after 2 missed keepalives
X11Forwarding no                # Disable unless needed
UseDNS no                       # Faster connections

# Apply changes (careful — if something is wrong, you'll lock yourself out!)
# ALWAYS test config before applying:
sshd -t                         # Test configuration syntax
sudo systemctl reload sshd      # Apply without killing existing connections
```

### 🔬 Mini Lab 8: SSH Setup

```bash
# On your local machine:
# 1. Generate a key pair
ssh-keygen -t ed25519 -C "mylab@test" -f ~/.ssh/lab_key

# 2. Look at what was created
ls -la ~/.ssh/lab_key*
cat ~/.ssh/lab_key.pub      # Your public key

# 3. Set up SSH config for a server (use your own server or a cloud VM)
cat >> ~/.ssh/config << 'EOF'
Host mylab
    HostName YOUR_SERVER_IP
    User ubuntu
    IdentityFile ~/.ssh/lab_key
EOF

# 4. Copy key to server (you'll need password this one time)
ssh-copy-id -i ~/.ssh/lab_key.pub ubuntu@YOUR_SERVER_IP

# 5. Now connect without password!
ssh mylab

# 6. On the server, check the auth log:
sudo tail -20 /var/log/auth.log | grep "Accepted"
```

---

---

# 🔥 PART 3: LINUX ADVANCED (DevOps Level)

---

## <a id="chapter-15"></a>💡 Chapter 15 — Linux Kernel & Namespaces (Why Docker Exists)

### 📖 The Linux Kernel — The Core

The **kernel** is the central part of Linux that talks directly to hardware. Everything else (bash, nginx, python) talks to the kernel, which talks to hardware.

```
Applications (nginx, python, mysql)
         ↕ system calls
Linux Kernel
         ↕ hardware drivers
Hardware (CPU, RAM, Disk, NIC)
```

### 📖 Namespaces — The Magic Behind Containers

Linux **namespaces** isolate resources so one process sees a different "view" than another. This is how Docker containers work!

```
Without namespaces:          With namespaces (containers):
All processes share:         Container 1 sees:
  - Same hostname              - Its own hostname (web1)
  - Same PID list              - Its own PIDs (starts at 1!)
  - Same network               - Its own network (10.0.0.1)
  - Same filesystem            - Its own filesystem
  - Same users                 - Its own users

                             Container 2 sees:
                               - Different hostname (db1)
                               - Different PIDs
                               - Different network
                               - Different filesystem
```

### 💻 Namespace Types

```bash
# View namespaces of current process
ls -la /proc/self/ns/

# Types:
# mnt    → Mount namespace (filesystem)
# pid    → PID namespace (process IDs)
# net    → Network namespace (network interfaces, routing)
# ipc    → IPC namespace (inter-process communication)
# uts    → UTS namespace (hostname, domain name)
# user   → User namespace (user/group IDs)
# cgroup → cgroup namespace

# Create a new network namespace (mini container network example)
sudo ip netns add myns
sudo ip netns list
sudo ip netns exec myns ip addr     # Run command in namespace
sudo ip netns exec myns bash        # Shell in namespace
sudo ip netns delete myns
```

### 📖 cgroups — Resource Control

**Control Groups (cgroups)** limit how much CPU, RAM, disk, network a process can use. This is how Docker limits container resources.

```bash
# View cgroup hierarchy
ls /sys/fs/cgroup/
cat /sys/fs/cgroup/memory/memory.limit_in_bytes   # System memory limit

# Docker uses cgroups internally:
# docker run --memory=512m --cpus=1 myapp
# → Creates cgroups that limit container to 512MB RAM, 1 CPU
```

### 📖 The Linux Boot Process

```
Power On
  ↓
BIOS/UEFI (firmware) — hardware initialization, POST
  ↓
GRUB (bootloader) — shows boot menu, loads kernel
  ↓
Linux Kernel — initializes hardware, mounts root filesystem
  ↓
systemd (PID 1) — initializes system services
  ↓
Login prompt / Display Manager
```

```bash
# GRUB configuration
cat /etc/default/grub          # GRUB settings
cat /boot/grub/grub.cfg        # Full GRUB config (auto-generated)
update-grub                    # Regenerate grub.cfg

# Boot targets
systemctl get-default          # Current default target
# graphical.target = GUI login
# multi-user.target = Server (no GUI)
# rescue.target = Single user (recovery)

systemctl set-default multi-user.target    # Set server to no-GUI mode
systemctl isolate rescue.target            # Switch to rescue mode NOW
```

---

## <a id="chapter-16"></a>💡 Chapter 16 — Performance Tuning & Troubleshooting

### 📖 The Troubleshooting Methodology

When something is wrong, follow this order:
```
1. CHECK SYMPTOMS  → What errors do you see?
2. GATHER INFO     → Logs, metrics, recent changes
3. FORM HYPOTHESIS → What could cause this?
4. TEST            → Make one change at a time
5. VERIFY FIX      → Did it solve the problem?
6. DOCUMENT        → What was wrong and how you fixed it
```

### 💻 Performance Investigation Toolkit

```bash
# The USE Method: Utilization, Saturation, Errors
# For every resource: CPU, Memory, Disk, Network

# ─── CPU ───────────────────────────────────────────────────
top                             # Real-time (sort by P=CPU)
htop                            # Better interactive view
mpstat -P ALL 1                 # Per-CPU utilization
sar -u 1 10                     # CPU usage over time
uptime                          # Load average
cat /proc/loadavg               # Load: 1min 5min 15min

# Load average interpretation:
# Load = number of tasks waiting for/using CPU
# Load 1.0 on 1 CPU = fully utilized
# Load 2.0 on 1 CPU = overloaded (queue of 1)
# Load 2.0 on 4 CPUs = 50% utilized (fine!)
# Rule: load > number of CPUs = investigate

# Find CPU-hungry processes
ps aux --sort=-%cpu | head -10
pidstat -u 1 5                  # CPU per process

# ─── MEMORY ────────────────────────────────────────────────
free -h
vmstat -s
cat /proc/meminfo

# Memory terminology:
# Total: Physical RAM installed
# Used: Used by OS + apps
# Free: Literally unused (usually low — Linux uses free RAM for cache)
# Buff/Cache: Used as disk cache (can be reclaimed if needed)
# Available: Free + reclaim-able cache (THIS is what matters)

# Find memory-hungry processes
ps aux --sort=-%mem | head -10
pidstat -r 1 5

# ─── DISK I/O ──────────────────────────────────────────────
iostat -xz 1                    # Extended disk stats
iotop -o                        # I/O per process (install first)
sar -d 1 5                      # Disk activity

# Key iostat metrics:
# %util: % of time disk was busy (>80% = problem)
# await: avg wait time in ms (<10ms is fine for SSD)
# r/s, w/s: reads and writes per second

# Find disk-hungry processes
iotop -o -P                     # Only show active, by PID

# ─── NETWORK ───────────────────────────────────────────────
ss -s                           # Network stats summary
sar -n DEV 1 5                  # Network interface stats
nethogs                         # Network per process
iftop                           # Connection-level view
```

### 💻 Common Troubleshooting Scenarios

```bash
# SCENARIO 1: "Application is slow" 
# → Check all resources
top                             # Is CPU maxed?
free -h                         # Is memory low?
iostat -x 1                     # Is disk I/O high?
netstat -s | grep retransmit    # Network packet loss?

# SCENARIO 2: "Disk is full"
df -h                           # Which filesystem is full?
du -sh /var/* | sort -rh        # What's taking up space?
du -sh /var/log/*               # Log files?
find / -type f -size +1G        # Files over 1GB
journalctl --vacuum-time=30d    # Clear old journal logs
apt clean                       # Clear apt cache

# SCENARIO 3: "Service won't start"
systemctl status myapp          # What error?
journalctl -u myapp -n 50       # Last 50 log lines
journalctl -u myapp --since "1 hour ago"    # Recent logs
# Check: file permissions, config syntax, port conflicts

# SCENARIO 4: "Can't connect to server"
ping server                     # Is it reachable?
telnet server 80                # Is port 80 open?
nc -zv server 80                # Check port (modern)
ss -tulpn | grep :80            # Is anything listening on 80?
ufw status                      # Firewall blocking?
iptables -L -n                  # iptables rules?

# SCENARIO 5: "Out of memory (OOM killed)"
dmesg | grep -i "killed process"    # OOM killer messages
grep -i "out of memory" /var/log/syslog
# OOM killer kills processes to free memory when RAM is critically low
```

---

## <a id="chapter-17"></a>💡 Chapter 17 — Security Hardening

### 📖 The Security Mindset (Defense in Depth)

Security is not one thing — it's **layers**:
```
Layer 1: Physical security (lock the datacenter door)
Layer 2: Network security (firewall, VPN)
Layer 3: Host security (OS hardening)
Layer 4: Application security (patches, config)
Layer 5: Data security (encryption, backups)
Layer 6: Monitoring (logs, alerts)

If one layer fails, others protect you.
```

### 💻 Security Hardening Checklist

```bash
# ── 1. Keep System Updated ─────────────────────────────────
sudo apt update && sudo apt upgrade -y
sudo apt install unattended-upgrades
sudo dpkg-reconfigure -plow unattended-upgrades   # Enable auto-updates

# ── 2. SSH Hardening ────────────────────────────────────────
# (Already covered in SSH chapter)
# Key settings:
# PermitRootLogin no
# PasswordAuthentication no
# AllowUsers your_user

# ── 3. Firewall (ufw) ──────────────────────────────────────
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 2222/tcp             # SSH (your custom port)
sudo ufw allow 80/tcp               # HTTP
sudo ufw allow 443/tcp              # HTTPS
sudo ufw enable
sudo ufw status verbose

# ── 4. fail2ban — Auto-ban Brute Force ─────────────────────
sudo apt install fail2ban

cat /etc/fail2ban/jail.conf         # Default config
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local   # Custom config

# /etc/fail2ban/jail.local:
[DEFAULT]
bantime  = 1h               # Ban for 1 hour
findtime = 10m              # In last 10 minutes
maxretry = 5                # After 5 failures

[sshd]
enabled = true
port    = 2222              # Your SSH port

sudo systemctl enable --now fail2ban
sudo fail2ban-client status             # Status
sudo fail2ban-client status sshd        # SSH jail status
sudo fail2ban-client unban 1.2.3.4      # Unban an IP

# ── 5. User Security ────────────────────────────────────────
# Set strong password policy
sudo apt install libpam-pwquality
sudo vim /etc/security/pwquality.conf
# minlen = 12
# minclass = 3      (uppercase, lowercase, digits, special)
# maxrepeat = 2

# Lock inactive accounts
passwd -l username          # Lock account
chage -E 0 username         # Expire account immediately

# ── 6. Audit Logs ───────────────────────────────────────────
sudo apt install auditd
sudo auditctl -w /etc/passwd -p wa -k passwd_changes    # Watch /etc/passwd
sudo auditctl -w /etc/shadow -p wa -k shadow_changes
sudo ausearch -k passwd_changes         # Search audit log
sudo aureport --auth                    # Authentication summary

# ── 7. File Integrity ───────────────────────────────────────
sudo apt install aide
sudo aideinit                           # Initialize database
sudo aide --check                       # Check for changes

# ── 8. Check for Rootkits ──────────────────────────────────
sudo apt install rkhunter chkrootkit
sudo rkhunter --update
sudo rkhunter --check
sudo chkrootkit

# ── 9. Disable Unnecessary Services ────────────────────────
systemctl list-units --type=service --state=running  # What's running?
sudo systemctl disable --now bluetooth.service  # Disable if not needed
sudo systemctl disable --now cups.service       # Print service (if no printers)

# ── 10. Check Open Ports ───────────────────────────────────
ss -tulpn                   # All listening ports
# Each open port is an attack surface — close unused ones
```

---

## <a id="chapter-18"></a>💡 Chapter 18 — Linux Networking Configuration

### 💻 Network Interfaces

```bash
# View interfaces
ip addr show                    # All interfaces
ip addr show eth0               # Specific interface
ip link show                    # Link layer info

# Typical interfaces:
# lo          → Loopback (127.0.0.1, always exists)
# eth0/ens3   → Wired ethernet
# wlan0       → WiFi
# docker0     → Docker bridge network
# veth*       → Virtual ethernet (for containers)
# br0         → Bridge interface

# Interface operations
ip link set eth0 up             # Enable interface
ip link set eth0 down           # Disable interface
ip addr add 192.168.1.100/24 dev eth0   # Add IP address
ip addr del 192.168.1.100/24 dev eth0   # Remove IP address

# Routing
ip route show                   # Routing table
ip route add default via 192.168.1.1    # Set default gateway
ip route add 10.0.0.0/8 via 10.1.1.1 dev eth1   # Static route
ip route del 10.0.0.0/8        # Remove route
```

### 💻 Netplan (Ubuntu 18.04+)

```yaml
# /etc/netplan/00-installer-config.yaml

# DHCP (automatic IP from router):
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: true
      dhcp6: false

# Static IP:
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: false
      addresses:
        - 192.168.1.100/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
```

```bash
sudo netplan apply              # Apply changes
sudo netplan try                # Test (auto-reverts if you don't confirm)
sudo netplan generate           # Just generate config
```

---

---

# 🌐 PART 4: NETWORKING FUNDAMENTALS

---

## <a id="chapter-19"></a>💡 Chapter 19 — What is a Network? (Real World Analogies)

### 📖 Networks Are Everywhere

You probably use networks hundreds of times a day without thinking about it:
- Opening Instagram → your phone talks to Instagram's servers
- Sending a WhatsApp message → your message travels across the world
- Loading a Google search → data travels from Google's datacenters to you

A **network** is simply a collection of devices that can communicate with each other.

### 📖 The Postal System Analogy (How Networking Really Works)

```
YOU WRITE A LETTER (APPLICATION DATA)
         ↓
YOU SEAL IT IN AN ENVELOPE (ADD TCP HEADER — port numbers)
         ↓
YOU PUT IT IN A LARGER ENVELOPE (ADD IP HEADER — IP addresses)
         ↓
YOU LABEL THE OUTER BOX (ADD ETHERNET HEADER — MAC addresses)
         ↓
POSTAL WORKER PICKS IT UP (LOCAL NETWORK DELIVERS TO ROUTER)
         ↓
SORTED AT POST OFFICE (ROUTER DECIDES NEXT HOP)
         ↓
TRAVELS VIA POSTAL TRUCKS (INTERNET BACKBONE)
         ↓
LOCAL DELIVERY PERSON (LAST-MILE NETWORK DELIVERY)
         ↓
RECIPIENT OPENS ENVELOPES IN REVERSE ORDER (DESTINATION UNPACKS)
         ↓
RECIPIENT READS THE LETTER (APPLICATION PROCESSES DATA)
```

### 📖 Network Types

```
Network Type    Coverage         Example
─────────────────────────────────────────────────────
PAN             1-10 meters      Bluetooth, NFC (your devices)
LAN             Up to 1km        Home WiFi, office network
MAN             City-wide        City fiber network
WAN             Country/Globe    Internet, leased lines
VPN             Anywhere         Virtual private network over internet
```

### 📖 How Data Actually Travels

```
Scenario: You open google.com from Bangladesh

1. YOUR BROWSER → creates HTTP request
2. YOUR OS       → wraps it in TCP segment (adds port 443)
3. YOUR OS       → wraps in IP packet (adds your IP + Google's IP)
4. YOUR NIC      → wraps in Ethernet frame (adds MAC addresses)
5. YOUR ROUTER   → receives frame, reads IP, forwards toward Google
6. ISP ROUTERS   → each hop reads IP, forwards toward destination
7. ~10-20 HOPS   → data crosses internet backbone
8. GOOGLE ROUTER → delivers to correct server
9. GOOGLE SERVER → processes request, sends back response
10. REVERSE PATH → response travels back to you
Total time: ~200-400 milliseconds!
```

---

## <a id="chapter-20"></a>💡 Chapter 20 — OSI & TCP/IP Models

### 📖 WHY Do These Models Exist?

Imagine building a network where every company's hardware and software had to perfectly work with every other company's. Chaos!

The OSI model is like a **contract** — "if every layer does its job using these rules, everything will work together." Each layer only talks to the layer above and below it.

### 📖 OSI Model — 7 Layers Deep

```
LAYER 7 — APPLICATION
  What: What the user/application does with data
  Who: Your web browser, email client, curl
  Examples: HTTP, HTTPS, FTP, DNS, SMTP, SSH
  Data unit: "Data" or "Message"
  ─────────────────────────────────────────────
LAYER 6 — PRESENTATION  
  What: Translate data format, encryption, compression
  Who: TLS/SSL encryption, JPEG/MP4 encoding
  Examples: SSL, TLS, JPEG, MPEG, ASCII
  Think of it as: Translator/encoder
  ─────────────────────────────────────────────
LAYER 5 — SESSION
  What: Manage communication sessions (start/stop)
  Who: OS networking stack
  Examples: NetBIOS, RPC, SQL sessions
  Think of it as: Call manager (maintains connection)
  ─────────────────────────────────────────────
LAYER 4 — TRANSPORT ⭐ (Very Important!)
  What: End-to-end communication, error checking
  Who: TCP/UDP protocols
  Data unit: "Segment" (TCP) or "Datagram" (UDP)
  Port numbers live here! (80, 443, 22, 3306...)
  ─────────────────────────────────────────────
LAYER 3 — NETWORK ⭐ (Very Important!)
  What: Logical addressing and routing
  Who: Routers
  Data unit: "Packet"
  IP addresses live here! (192.168.1.1)
  ─────────────────────────────────────────────
LAYER 2 — DATA LINK ⭐ (Very Important!)
  What: Physical addressing, error detection per hop
  Who: Switches, Network Interface Cards (NIC)
  Data unit: "Frame"
  MAC addresses live here! (AA:BB:CC:DD:EE:FF)
  ─────────────────────────────────────────────
LAYER 1 — PHYSICAL
  What: Raw bits over physical medium
  Who: Cables, WiFi radio, fiber optic, hubs
  Data unit: "Bit" (0 or 1)
  This is actual electricity/light/radio waves
```

**Memory Trick (top to bottom): "All People Seem To Need Data Processing"**
**Memory Trick (bottom to top): "Please Do Not Throw Sausage Pizza Away"**

### 📖 TCP/IP Model (What's Used in Practice)

The real internet uses a 4-layer model (TCP/IP):

```
TCP/IP Layer        OSI Equivalent      Protocols
─────────────────────────────────────────────────────────
Application         Layers 5, 6, 7      HTTP, DNS, SSH, FTP
Transport           Layer 4             TCP, UDP
Internet            Layer 3             IP, ICMP, ARP
Network Access      Layers 1, 2         Ethernet, WiFi
```

### 📖 TCP vs UDP — The Core Protocol Choice

```
                    TCP                         UDP
Purpose:        Reliable delivery           Fast delivery
Connection:     Connection-oriented         Connectionless
Handshake:      Yes (SYN-SYN/ACK-ACK)      No
Delivery:       Guaranteed                  Best effort
Order:          In-order                    No guarantee
Error check:    Yes (ACK system)            Checksum only
Speed:          Slower (overhead)           Faster (less overhead)
Use when:       Data must arrive intact     Speed > reliability

TCP use cases:                  UDP use cases:
  - Web (HTTP/HTTPS)              - DNS (quick queries)
  - SSH                           - Video streaming
  - Email (SMTP, IMAP)            - Online gaming
  - File transfer (FTP)           - VoIP / video calls
  - Database connections          - Live broadcasts
```

### 📖 The TCP 3-Way Handshake (Connection Establishment)

```
Client                              Server
  │                                   │
  │──── SYN (seq=100) ───────────────►│   "I want to connect, my seq# is 100"
  │                                   │
  │◄─── SYN-ACK (seq=300, ack=101) ──│   "OK! My seq# is 300, got your 100"
  │                                   │
  │──── ACK (ack=301) ───────────────►│   "Got it! Starting data transfer"
  │                                   │
  │     [DATA TRANSFER BEGINS]        │
  │                                   │
  │    4-WAY CLOSE (FIN-ACK-FIN-ACK)  │
```

```bash
# See TCP connections and their states
ss -tan
# STATES: LISTEN, SYN-SENT, SYN-RECV, ESTABLISHED, FIN-WAIT, CLOSE-WAIT, CLOSED
```

### 📖 Common Port Numbers (Know These!)

```
PORT   PROTOCOL  SERVICE           NOTES
───────────────────────────────────────────────────────────
20     TCP       FTP Data          File transfer data
21     TCP       FTP Control       File transfer commands
22     TCP       SSH               Secure remote access
23     TCP       Telnet            INSECURE — don't use!
25     TCP       SMTP              Email sending
53     TCP/UDP   DNS               Domain name resolution
67/68  UDP       DHCP              Automatic IP assignment
80     TCP       HTTP              Web (unencrypted)
110    TCP       POP3              Email download
143    TCP       IMAP              Email access
389    TCP       LDAP              Directory services
443    TCP       HTTPS             Web (encrypted)
465    TCP       SMTPS             Secure email
587    TCP       Submission        Email submission
636    TCP       LDAPS             Secure LDAP
993    TCP       IMAPS             Secure IMAP
3306  TCP       MySQL             Database
5432  TCP       PostgreSQL        Database
6379  TCP       Redis             Cache/database
8080  TCP       HTTP Alt          Dev/proxy servers
8443  TCP       HTTPS Alt         Dev/proxy
27017 TCP       MongoDB           Database
```

### 🧠 Quiz 5 — OSI & TCP/IP

```
Q1: At which OSI layer do IP addresses operate?
Q2: At which OSI layer do port numbers operate?
Q3: Which protocol would you use for streaming live video — TCP or UDP? Why?
Q4: What is the sequence of a TCP handshake?
Q5: A router operates at which OSI layer? A switch?
Q6: Why does HTTPS run on port 443 while HTTP runs on port 80?
```

---

## <a id="chapter-21"></a>💡 Chapter 21 — IP Addressing & Subnetting

### 📖 What is an IP Address? (Real World Analogy)

An IP address is like a **postal address for a device**:
- Just as every house needs a unique address for mail delivery
- Every device on a network needs a unique IP for data delivery

```
192.168.1.100
│  │ │ │  │
│  │ │ │  └── Host number (which device on this network)
│  │ │ └───── Network/host boundary changes with subnet mask
│  │ └─────── Second octet
│  └─────────── First octet  
└──────────────── IP address (4 octets, 0-255 each)
```

### 📖 Public vs Private IPs

```
PRIVATE IPs (used inside networks — NOT routable on internet):
10.0.0.0   to  10.255.255.255   → Class A private (10.x.x.x)
172.16.0.0 to  172.31.255.255   → Class B private (172.16-31.x.x)
192.168.0.0 to 192.168.255.255  → Class C private (192.168.x.x)

Your home router probably gave you: 192.168.1.xxx or 10.0.0.xxx

PUBLIC IPs (assigned by ISP, unique worldwide):
Everything else = public IP
Your ISP gives you one public IP, your router shares it with all home devices

SPECIAL:
127.0.0.1       → Loopback (localhost — talking to yourself)
0.0.0.0         → All interfaces / any address
255.255.255.255 → Broadcast (send to everyone on network)
```

### 📖 Subnet Masks & CIDR — Explained Simply

A **subnet mask** tells your device: "which part of the IP address is the network, and which part is the host?"

```
IP:   192.168.1.100
Mask: 255.255.255.0  (or /24)

In binary:
IP:   11000000.10101000.00000001.01100100
Mask: 11111111.11111111.11111111.00000000
      ─────────────────────────────────────
      Network portion (fixed)  │Host portion
      192.168.1.              │.100

This means:
  Network: 192.168.1.0    (the network itself)
  Hosts:   192.168.1.1 to 192.168.1.254  (254 usable hosts)
  Broadcast: 192.168.1.255
```

### 📖 CIDR Quick Reference

```
CIDR  Subnet Mask       # Hosts  # Networks  Use case
/8    255.0.0.0         16M      1 Class A   ISP backbone
/16   255.255.0.0       65534    256         Large enterprise
/24   255.255.255.0     254      -           Small office/home
/25   255.255.255.128   126      -           Medium subnet
/26   255.255.255.192   62       -           Small subnet
/27   255.255.255.224   30       -           Small segment
/28   255.255.255.240   14       -           Very small
/29   255.255.255.248   6        -           Tiny (4 servers + GW)
/30   255.255.255.252   2        -           Point-to-point links
/32   255.255.255.255   1        -           Single host

# Hosts = 2^(32-prefix) - 2  (subtract network and broadcast)
```

### 📖 Subnetting Example (AWS VPC Style)

```
Company gets: 10.0.0.0/16  (65,534 hosts)

Divide into departments:
├── Production:   10.0.1.0/24  (254 hosts) → web servers
├── Database:     10.0.2.0/24  (254 hosts) → db servers
├── Development:  10.0.3.0/24  (254 hosts) → dev machines
├── Management:   10.0.4.0/24  (254 hosts) → monitoring, bastion
└── Reserved:     10.0.5.0/24+ → future expansion
```

### 💻 IP Commands

```bash
# View your IP
ip addr show                    # All interfaces
ip addr show eth0               # Specific interface
hostname -I                     # Just the IPs
ip -4 addr                      # IPv4 only

# Your public IP (from internet's perspective)
curl ifconfig.me
curl ipinfo.io/ip
curl https://api.ipify.org

# Default gateway
ip route show default           # Shows: default via 192.168.1.1 dev eth0

# Calculate subnets
# Install ipcalc:
sudo apt install ipcalc
ipcalc 192.168.1.0/24
ipcalc 10.0.0.0/8
```

---

## <a id="chapter-22"></a>💡 Chapter 22 — DNS — The Internet's Phone Book

### 📖 DNS Without Jargon

You know phone books? You look up "Pizza Restaurant" and it gives you the phone number. DNS does the same for websites:
- You type: `google.com`
- DNS tells your browser: `142.250.80.46`
- Browser connects to that IP address

Without DNS, you'd have to remember numbers like `142.250.80.46` instead of `google.com`.

### 📖 DNS Resolution — Step by Step

```
You type: www.example.com
         ↓
Browser checks its cache → not there
         ↓
OS checks /etc/hosts → not there
         ↓
OS asks configured DNS resolver (e.g., 8.8.8.8)
         ↓
Resolver checks its cache → not there
         ↓
Resolver asks ROOT nameserver (.) — "who handles .com?"
         ↓
Root says: "Ask 192.5.6.30 (Verisign — .com TLD server)"
         ↓
Resolver asks .com TLD server — "who handles example.com?"
         ↓
TLD says: "Ask ns1.examplehost.com (example.com's nameserver)"
         ↓
Resolver asks example.com's nameserver — "IP for www.example.com?"
         ↓
Answer: 93.184.216.34
         ↓
Resolver caches result (TTL) and returns to browser
         ↓
Browser connects to 93.184.216.34
```

### 📖 DNS Record Types — The Full Picture

```
A Record      → Hostname → IPv4 address
  example.com  IN A  93.184.216.34

AAAA Record   → Hostname → IPv6 address
  example.com  IN AAAA  2606:2800:220:1:248:1893:25c8:1946

CNAME Record  → Alias → another hostname
  www          IN CNAME  example.com  (www.example.com points to example.com)
  mail         IN CNAME  mail.provider.com

MX Record     → Mail server for a domain
  example.com  IN MX  10  mail1.example.com  (lower number = higher priority)
  example.com  IN MX  20  mail2.example.com

TXT Record    → Text information
  Used for: SPF (email anti-spam), DKIM, domain verification
  example.com  IN TXT  "v=spf1 include:mailprovider.com ~all"

NS Record     → Nameservers for a domain
  example.com  IN NS  ns1.digitalocean.com
  example.com  IN NS  ns2.digitalocean.com

PTR Record    → IP → Hostname (reverse DNS)
  34.216.184.93.in-addr.arpa  IN PTR  example.com

SOA Record    → Start of Authority (zone admin info)
SRV Record    → Service location (_service._proto.name TTL class SRV priority weight port target)
```

### 💻 DNS Tools

```bash
# nslookup — basic DNS lookup
nslookup google.com
nslookup -type=MX gmail.com         # MX records
nslookup -type=TXT google.com       # TXT records
nslookup google.com 1.1.1.1         # Query Cloudflare DNS

# dig — detailed DNS lookup (most powerful)
dig google.com                      # Default A record
dig google.com A                    # Explicit A record
dig google.com MX                   # Mail servers
dig google.com NS                   # Nameservers
dig google.com TXT                  # TXT records
dig google.com ANY                  # All records
dig +short google.com               # Just the IP
dig @8.8.8.8 google.com             # Query specific DNS server
dig -x 8.8.8.8                      # Reverse DNS (PTR lookup)
dig +trace google.com               # TRACE full resolution path!

# host — simple lookup
host google.com
host -t MX google.com
host 8.8.8.8                        # Reverse lookup

# Real DevOps: test DNS propagation after change
dig @8.8.8.8 example.com +short     # Check Google DNS
dig @1.1.1.1 example.com +short     # Check Cloudflare DNS
dig @ns1.digitalocean.com example.com +short  # Check authoritative server
```

### 💻 DNS Configuration Files

```bash
# /etc/hosts — local DNS override (checked BEFORE DNS!)
cat /etc/hosts
# 127.0.0.1    localhost
# 192.168.1.100 myserver myserver.local
# 10.0.0.5     database db.internal

# DevOps use: Block ads by pointing to 127.0.0.1
# DevOps use: Override DNS for testing before going live

# Add an entry:
echo "192.168.1.50 staging.myapp.com" | sudo tee -a /etc/hosts

# /etc/resolv.conf — which DNS servers to use
cat /etc/resolv.conf
# nameserver 8.8.8.8         ← Google DNS
# nameserver 8.8.4.4         ← Google DNS backup
# search mycompany.com       ← Try appending this domain

# /etc/nsswitch.conf — lookup order
cat /etc/nsswitch.conf | grep hosts
# hosts: files dns myhostname
#         ↑     ↑  → lookup order: /etc/hosts first, then DNS
```

---

## <a id="chapter-23"></a>💡 Chapter 23 — HTTP, HTTPS & How the Web Works

### 📖 HTTP — The Language of the Web

HTTP (HyperText Transfer Protocol) is the language browsers and servers use to communicate. Every time you load a webpage, HTTP is happening.

```
Browser: "GET /index.html HTTP/1.1\r\nHost: example.com\r\n\r\n"
          ↑ Method  ↑ Path  ↑ Version

Server:  "HTTP/1.1 200 OK\r\nContent-Type: text/html\r\n\r\n<html>..."
                   ↑ Status code
```

### 📖 HTTP Request Structure

```
GET /api/users HTTP/1.1
Host: api.example.com
Authorization: Bearer eyJhbGci...
Content-Type: application/json
Accept: application/json
User-Agent: Mozilla/5.0 ...

[blank line]
{request body — for POST/PUT}
```

### 📖 HTTP Response Structure

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 256
Date: Mon, 09 Mar 2026 10:00:00 GMT
Server: nginx/1.24.0
Cache-Control: max-age=3600

[blank line]
{"users": [...], "total": 150}
```

### 📖 HTTP Methods Explained

```
GET     → Read/retrieve data. Should NOT modify anything.
          Like: read a file, view a user profile

POST    → Create new resource. Data in request body.
          Like: create a new user, submit a form

PUT     → Replace entire resource.
          Like: completely update a user record

PATCH   → Partial update. Change only specified fields.
          Like: update just the email address

DELETE  → Remove a resource.
          Like: delete a user

HEAD    → Like GET but no response body (just headers)
          Use: check if resource exists, get metadata

OPTIONS → Ask server what methods are allowed
          Use: CORS preflight requests (browser security)
```

### 📖 HTTP Status Codes — Know Them Cold

```
1xx INFORMATIONAL
  100 Continue        → Server got headers, send body

2xx SUCCESS ✅
  200 OK              → Standard success
  201 Created         → Resource created (POST response)
  204 No Content      → Success but nothing to return (DELETE)

3xx REDIRECTION ↩️
  301 Moved Permanently → URL has changed forever (update bookmarks)
  302 Found            → Temporary redirect
  304 Not Modified     → Use cached version (unchanged since last request)

4xx CLIENT ERRORS ❌ (Your fault — bad request)
  400 Bad Request      → Malformed request
  401 Unauthorized     → Not logged in / bad credentials
  403 Forbidden        → Logged in but no permission
  404 Not Found        → Resource doesn't exist
  405 Method Not Allowed → Can't GET a POST-only endpoint
  409 Conflict         → Resource already exists
  422 Unprocessable    → Validation error
  429 Too Many Requests → Rate limited (slow down!)

5xx SERVER ERRORS 💥 (Server's fault)
  500 Internal Server Error → Bug in server code
  502 Bad Gateway           → Upstream server error (nginx → app server)
  503 Service Unavailable   → Server down/overloaded
  504 Gateway Timeout       → Upstream server didn't respond in time
```

### 📖 HTTPS & TLS/SSL

```
HTTP  = Unencrypted (like sending a postcard — anyone can read)
HTTPS = Encrypted (like sending sealed letter in secure courier)

TLS (Transport Layer Security) provides:
  ✓ Encryption (data scrambled — only sender/receiver can read)
  ✓ Authentication (proves you're talking to REAL google.com)
  ✓ Integrity (detect if data was tampered in transit)

HOW TLS WORKS (simplified):
1. Browser connects to server (port 443)
2. Server sends its CERTIFICATE (contains public key + identity)
3. Browser verifies certificate is signed by trusted CA (Certificate Authority)
4. Browser and server negotiate encryption keys
5. Encrypted tunnel established
6. All data now encrypted

CERTIFICATES:
  - Let's Encrypt: Free! Widely used for websites
  - DigiCert, Comodo: Paid, used by enterprises
  - Self-signed: Free, but browsers don't trust them (show warning)
```

### 💻 curl — HTTP from Command Line

```bash
# GET request
curl https://api.github.com                     # Basic GET
curl -I https://google.com                      # Headers ONLY (-I = HEAD request)
curl -v https://google.com                      # Verbose (see full request/response)
curl -s https://api.github.com | python3 -m json.tool  # Pretty-print JSON

# POST request
curl -X POST https://api.example.com/users \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer TOKEN" \
  -d '{"name": "John", "email": "john@example.com"}'

# File upload
curl -F "file=@/path/to/file.txt" https://api.example.com/upload

# Download file
curl -O https://example.com/file.tar.gz         # Save with original name
curl -o myfile.tar.gz https://example.com/file  # Save with custom name
curl -L https://example.com                     # Follow redirects
curl -k https://self-signed.example.com        # Skip SSL verification

# Auth
curl -u username:password https://api.example.com    # Basic auth

# Check HTTP response code only
curl -o /dev/null -s -w "%{http_code}" https://example.com

# Useful for health checks in scripts:
if curl -sf https://myapp.com/health > /dev/null; then
    echo "App is healthy!"
else
    echo "App is DOWN!"
fi
```

---

# 🔥 PART 5: NETWORKING ADVANCED

---

## <a id="chapter-24"></a>💡 Chapter 24 — Network Tools & Diagnostics

### 💻 The Full Toolkit

```bash
# ─── CONNECTIVITY ──────────────────────────────────────────
ping google.com                 # ICMP echo — basic connectivity
ping -c 4 google.com            # Send exactly 4 pings
ping -i 0.2 google.com          # 200ms interval (faster)
ping6 google.com                # IPv6 ping

# traceroute — trace every hop from you to destination
traceroute google.com           # Linux (UDP probes)
traceroute -T google.com        # TCP traceroute (bypasses some firewalls)
mtr google.com                  # Real-time combined ping+traceroute (BEST!)
mtr --report google.com         # Report mode

# Reading traceroute:
# Hop  RTT  Hostname/IP
# 1.   1ms  192.168.1.1   (your router)
# 2.   10ms 103.55.1.1    (ISP first hop)
# 3.   20ms 103.55.2.1    (ISP backbone)
# ...
# 15.  200ms 216.58.196.4  (Google!)

# nc (netcat) — the network swiss army knife
nc -zv google.com 443           # Test if port 443 is open
nc -zv 192.168.1.100 22         # Test SSH port
nc -l 1234                      # Listen on port 1234 (server mode)
nc hostname 1234                # Connect to port 1234 (client mode)
echo "test" | nc hostname 1234  # Send data
nc -l 1234 > received_file.txt  # Receive file
nc hostname 1234 < file.txt     # Send file

# ─── PORT & SOCKET INFO ─────────────────────────────────────
# ss — modern netstat
ss -tuln                        # TCP/UDP listening ports (no DNS)
ss -tulpn                       # With process names (needs root)
ss -ta                          # All TCP connections
ss -s                           # Summary statistics
ss state established            # Only established connections
ss -tn dst 8.8.8.8              # Connections to specific IP

# netstat (older but still common)
netstat -tuln                   # Listening ports
netstat -an                     # All connections
netstat -rn                     # Routing table
netstat -i                      # Interface stats
netstat -s                      # Protocol statistics

# lsof — list open files (including network sockets)
lsof -i :80                     # What's using port 80?
lsof -i :443
lsof -i TCP                     # All TCP connections
lsof -i TCP:22 -i TCP:80        # SSH and HTTP
lsof -p 1234 -i                 # Network connections for PID 1234

# ─── PACKET CAPTURE ─────────────────────────────────────────
# tcpdump — capture raw network packets
tcpdump -i eth0                         # All traffic on eth0
tcpdump -i any                          # All interfaces
tcpdump -i eth0 port 80                 # HTTP traffic only
tcpdump -i eth0 host 192.168.1.100      # Traffic to/from specific IP
tcpdump -i eth0 'tcp port 443'          # HTTPS traffic
tcpdump -i eth0 -n                      # Don't resolve names (faster)
tcpdump -i eth0 -w capture.pcap         # Save to file (open in Wireshark!)
tcpdump -r capture.pcap                 # Read saved capture
tcpdump -i eth0 -c 100                  # Capture only 100 packets

# Example: capture HTTP requests and show URLs
tcpdump -i eth0 -A 'tcp port 80' | grep "GET\|POST\|Host:"

# ─── DNS TOOLS ──────────────────────────────────────────────
dig google.com +short           # Quick IP lookup
dig google.com ANY              # All record types
dig @8.8.8.8 google.com         # Query specific DNS
dig +trace google.com           # Full DNS resolution trace
nslookup google.com
host google.com
```

### 💻 Network Performance Testing

```bash
# iperf3 — measure network bandwidth
# On server: 
iperf3 -s                       # Start iperf server (listen mode)
# On client:
iperf3 -c server_ip             # Connect and measure bandwidth
iperf3 -c server_ip -t 30       # Test for 30 seconds
iperf3 -c server_ip -P 4        # 4 parallel streams
iperf3 -c server_ip -u -b 100m  # UDP test at 100Mbps

# Bandwidth monitoring
nload                           # Real-time in/out bandwidth
iftop                           # Per-connection bandwidth
nethogs                         # Bandwidth per process
bmon                            # Interface monitoring

# Latency testing
ping -c 100 google.com | tail -2    # 100-ping stats summary
```

---

## <a id="chapter-25"></a>💡 Chapter 25 — Firewalls & Network Security

### 📖 What is a Firewall? (Analogy)

A firewall is like a **security guard** at the entrance of a building:
- Has a list of allowed visitors (rules)
- Checks every person entering and leaving
- Blocks anyone not on the list
- Logs who comes and goes

A network firewall checks every packet of data.

### 💻 ufw — Ubuntu Firewall

```bash
# Status
ufw status                      # Current status + rules
ufw status verbose              # More detail
ufw status numbered             # With rule numbers

# Basic setup
ufw default deny incoming       # Block all incoming (start from zero)
ufw default allow outgoing      # Allow all outgoing

# Allow specific services/ports
ufw allow ssh                   # Allow SSH (port 22)
ufw allow 22/tcp                # Same, explicit
ufw allow 80/tcp                # HTTP
ufw allow 443/tcp               # HTTPS
ufw allow 8080/tcp              # Custom port

# Allow from specific IP
ufw allow from 192.168.1.10             # Allow all from this IP
ufw allow from 192.168.1.0/24           # Allow from subnet
ufw allow from 192.168.1.10 to any port 22   # Allow SSH from specific IP only

# Deny
ufw deny 23/tcp                 # Block Telnet
ufw deny from 1.2.3.4           # Block specific IP

# Delete rules
ufw delete allow 80/tcp
ufw status numbered
ufw delete 3                    # Delete rule #3

# Enable/Disable
ufw enable
ufw disable
ufw reload                      # Reload rules

# Rate limiting (anti-brute force)
ufw limit ssh                   # Rate limit SSH connections

# Logging
ufw logging on
ufw logging medium
tail -f /var/log/ufw.log
```

### 💻 iptables — The Underlying Engine

```bash
# iptables uses CHAINS and TABLES
# Tables: filter (default), nat, mangle, raw
# Chains: INPUT (incoming), OUTPUT (outgoing), FORWARD (routing through)

# View rules
iptables -L                     # All rules (filter table)
iptables -L -n                  # No hostname resolution
iptables -L -n -v               # With packet counts
iptables -L --line-numbers      # With line numbers
iptables -t nat -L              # NAT table rules

# Basic rules
iptables -A INPUT -p tcp --dport 22 -j ACCEPT      # Allow SSH
iptables -A INPUT -p tcp --dport 80 -j ACCEPT      # Allow HTTP
iptables -A INPUT -i lo -j ACCEPT                  # Allow loopback
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -P INPUT DROP                              # Default deny incoming

# Delete rules
iptables -D INPUT 3             # Delete rule #3 in INPUT
iptables -F INPUT               # Flush (clear) all INPUT rules
iptables -F                     # Flush all rules (CAREFUL!)

# Persist rules
apt install iptables-persistent
netfilter-persistent save
netfilter-persistent reload

# NAT — masquerade (for router/gateway servers)
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
echo 1 > /proc/sys/net/ipv4/ip_forward
```

---

## <a id="chapter-26"></a>💡 Chapter 26 — Load Balancing & Reverse Proxies

### 📖 The Problem Load Balancers Solve

```
ONE SERVER (Problem):
Users ─────────────────────► Server (overwhelmed, single point of failure)
100,000 req/sec               500 req/sec capacity ← DIES

WITH LOAD BALANCER (Solution):
                              ┌─► Server 1 (500 req/sec)
Users ─────► Load Balancer ──┼─► Server 2 (500 req/sec)
100,000 req/sec               └─► Server 3 (500 req/sec)
                              Total: 1,500 req/sec + redundancy!
```

### 📖 Load Balancing Algorithms

```
ROUND ROBIN:
  Request 1 → Server 1
  Request 2 → Server 2
  Request 3 → Server 3
  Request 4 → Server 1 (repeat)
  Best for: uniform load, stateless apps

LEAST CONNECTIONS:
  Always sends to server with FEWEST active connections
  Best for: varying request duration

IP HASH:
  Hash client IP → always same server
  Best for: session persistence (sticky sessions)

WEIGHTED:
  Server 1 gets 60%, Server 2 gets 40%
  Best for: servers with different capacities

HEALTH CHECK:
  Load balancer checks if servers are alive
  Removes unhealthy servers automatically
  This is how you get zero-downtime deployments!
```

### 💻 Nginx as Load Balancer & Reverse Proxy

```nginx
# /etc/nginx/nginx.conf or /etc/nginx/conf.d/loadbalancer.conf

# Define upstream servers
upstream app_servers {
    least_conn;                         # Use least connections algorithm
    server app1.internal:8080 weight=3;  # Gets 3x more traffic
    server app2.internal:8080 weight=2;
    server app3.internal:8080 weight=1;
    server app4.internal:8080 backup;   # Only used when others fail

    keepalive 32;                       # Keep 32 connections alive
}

server {
    listen 80;
    server_name example.com www.example.com;
    
    # Redirect HTTP to HTTPS
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name example.com;

    # SSL Configuration
    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers HIGH:!aNULL:!MD5;

    # Security headers
    add_header X-Frame-Options DENY;
    add_header X-Content-Type-Options nosniff;
    add_header X-XSS-Protection "1; mode=block";
    add_header Strict-Transport-Security "max-age=31536000";

    # Proxy to upstream
    location / {
        proxy_pass http://app_servers;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;

        # Timeouts
        proxy_connect_timeout 5s;
        proxy_send_timeout 60s;
        proxy_read_timeout 60s;
    }

    # Serve static files directly (don't send to app servers)
    location /static/ {
        root /var/www/example.com;
        expires 1y;                     # Cache for 1 year
        add_header Cache-Control "public, immutable";
    }

    # Health check endpoint
    location /health {
        access_log off;
        return 200 "healthy\n";
        add_header Content-Type text/plain;
    }

    # Logging
    access_log /var/log/nginx/example.com.access.log;
    error_log /var/log/nginx/example.com.error.log;
}
```

```bash
nginx -t                        # Test config syntax
systemctl reload nginx          # Apply without downtime
```

---

## <a id="chapter-27"></a>💡 Chapter 27 — VPN, Tunneling & Cloud Networking

### 💻 SSH Port Forwarding (The DevOps Secret Weapon)

```bash
# LOCAL PORT FORWARDING: access remote service locally
# "Forward my local port 3306 to the remote db on port 3306 via the jump server"
ssh -L 3306:db.internal:3306 user@bastion.example.com

# Now: mysql -h 127.0.0.1 -P 3306  → connects to remote DB through SSH tunnel!
# Perfect for: accessing private databases securely

# REMOTE PORT FORWARDING: expose local service on remote server
ssh -R 8080:localhost:3000 user@public-server.com
# Anyone accessing public-server:8080 reaches your localhost:3000
# Perfect for: demos, sharing dev environment

# DYNAMIC (SOCKS PROXY):
ssh -D 1080 user@server.com
# Configure browser's SOCKS proxy: localhost:1080
# All browser traffic tunneled through server
# Perfect for: browsing from server's location/network

# PERSISTENT TUNNELS with autossh
sudo apt install autossh
autossh -M 0 -N -L 3306:db.internal:3306 user@bastion.example.com &
# -N = don't execute command (tunnel only)
# -M 0 = use SSH's built-in keepalive
```

### 📖 Cloud Networking Concepts (AWS/GCP/Azure)

```
VPC (Virtual Private Cloud):
  = Your private network in the cloud
  = Isolated from other customers
  = You control IP ranges, subnets, routing

Typical AWS VPC Architecture:
┌──────────────────────────────────────────────────────────┐
│  VPC: 10.0.0.0/16                                       │
│                                                          │
│  ┌──────────────┐        ┌──────────────┐               │
│  │ Public Subnet│        │Private Subnet│               │
│  │ 10.0.1.0/24  │        │ 10.0.2.0/24  │               │
│  │              │        │              │               │
│  │ [Web Server] │        │ [DB Server]  │               │
│  │ [Load Bal.]  │        │ [App Server] │               │
│  │ [Bastion]    │        │              │               │
│  └──────┬───────┘        └──────────────┘               │
│         │                       ↑                       │
│  Internet Gateway            Only accessible from       │
│         │                    public subnet              │
└─────────┼────────────────────────────────────────────── ┘
          │
       Internet
```

```
Security Groups (Cloud Firewalls):
  - Stateful (allow return traffic automatically)
  - Applied per resource (EC2, RDS, etc.)
  - Inbound and outbound rules separately

Network ACLs (NACL):
  - Stateless (must explicitly allow return traffic)
  - Applied per subnet
  - Numbered rules, evaluated in order
  - More complex, but more powerful

Best Practice — Layered Security:
Internet → NACLs → Security Groups → Instance
```

---

---

# ⚙️ PART 6: DEVOPS TOOLCHAIN

---

## <a id="chapter-28"></a>💡 Chapter 28 — Docker & Containers (Linux in a Box)

### 📖 What Problem Does Docker Solve?

```
THE CLASSIC PROBLEM:
Developer: "It works on my machine! 🤷"
Operations: "It crashes on the server! 💥"

The difference:
  Dev machine: Ubuntu 22.04, Python 3.11, Node 18, MySQL 8
  Server:      CentOS 7, Python 2.7, Node 12, MySQL 5.7

DOCKER'S SOLUTION:
Package the APPLICATION + ALL ITS DEPENDENCIES together as a "container"
The container runs identically everywhere!

"Build once, run anywhere" — like a shipping container
Shipping containers: standard size, any ship/truck/crane can handle them
Docker containers: standard format, any Docker host can run them
```

### 📖 Docker Architecture

```
Docker CLI (docker command)
        ↓
Docker Daemon (dockerd) — manages containers
        ↓
containerd — container runtime
        ↓
Linux Kernel (namespaces + cgroups)
        ↓
Hardware

Images = templates (read-only layers)
Containers = running instances of images
Registry = where images are stored (Docker Hub, ECR, GCR)
```

### 💻 Docker Commands

```bash
# ─── IMAGES ────────────────────────────────────────────────
docker images                           # List local images
docker pull nginx                       # Download nginx image
docker pull nginx:1.24                  # Specific version
docker pull ubuntu:22.04                # Ubuntu image
docker rmi nginx                        # Remove image
docker image prune                      # Remove unused images
docker build -t myapp:v1.0 .            # Build from Dockerfile in current dir
docker push myrepo/myapp:v1.0           # Push to registry

# ─── CONTAINERS ─────────────────────────────────────────────
docker run nginx                        # Run (foreground)
docker run -d nginx                     # Run detached (background)
docker run -d -p 8080:80 nginx          # Map host:8080 → container:80
docker run -d --name mycontainer nginx  # Named container
docker run -it ubuntu bash              # Interactive terminal

docker ps                               # Running containers
docker ps -a                            # All containers (incl. stopped)
docker stop mycontainer                 # Graceful stop (SIGTERM)
docker kill mycontainer                 # Force stop (SIGKILL)
docker start mycontainer                # Start stopped container
docker restart mycontainer
docker rm mycontainer                   # Remove stopped container
docker rm -f mycontainer                # Force remove running container

# ─── CONTAINER INTERACTION ──────────────────────────────────
docker exec -it mycontainer bash        # Open shell inside container
docker exec mycontainer ls /var/log     # Run command in container
docker logs mycontainer                 # Container logs
docker logs -f mycontainer              # Follow logs (like tail -f)
docker logs --since 1h mycontainer      # Last 1 hour of logs
docker inspect mycontainer             # Full container details
docker stats                            # Live resource usage
docker cp myfile.txt mycontainer:/tmp/  # Copy file to container

# ─── VOLUMES ────────────────────────────────────────────────
docker volume create mydata
docker volume ls
docker run -d -v mydata:/var/lib/mysql mysql   # Named volume
docker run -d -v /host/path:/container/path nginx  # Bind mount

# ─── NETWORKING ─────────────────────────────────────────────
docker network ls
docker network create mynetwork
docker run -d --network mynetwork --name web nginx
docker run -d --network mynetwork --name db mysql
# 'web' container can now connect to 'db' by hostname!
```

### 📖 Dockerfile — Building Custom Images

```dockerfile
# Dockerfile — recipe for building an image

# Base image (start from something)
FROM node:18-alpine

# Set working directory inside container
WORKDIR /app

# Copy dependency files first (for caching)
COPY package*.json ./

# Install dependencies
RUN npm ci --only=production

# Copy application code
COPY . .

# Create non-root user (security!)
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

# Expose port (documentation only — doesn't publish!)
EXPOSE 3000

# Set environment variables
ENV NODE_ENV=production
ENV PORT=3000

# Health check
HEALTHCHECK --interval=30s --timeout=3s --retries=3 \
  CMD curl -f http://localhost:3000/health || exit 1

# Start command
CMD ["node", "server.js"]
```

```bash
# Build and run
docker build -t myapp:v1.0 .
docker run -d -p 3000:3000 --name myapp myapp:v1.0
```

### 📖 Docker Compose — Multi-Container Apps

```yaml
# docker-compose.yml
version: '3.8'

services:
  web:
    image: nginx:1.24
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf:ro
      - ./static:/var/www/html:ro
    depends_on:
      - app
    restart: always

  app:
    build: ./app/
    expose:
      - "3000"
    environment:
      - NODE_ENV=production
      - DB_HOST=database
      - DB_PORT=5432
      - DB_NAME=myapp
    depends_on:
      database:
        condition: service_healthy
    restart: always

  database:
    image: postgres:15
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: appuser
      POSTGRES_PASSWORD: ${DB_PASSWORD}    # From .env file
    volumes:
      - postgres_data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U appuser"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: always

  redis:
    image: redis:7-alpine
    volumes:
      - redis_data:/data
    restart: always

volumes:
  postgres_data:
  redis_data:

networks:
  default:
    name: myapp_network
```

```bash
docker-compose up -d                # Start all services
docker-compose ps                   # Status
docker-compose logs -f app          # Follow app logs
docker-compose exec app bash        # Shell into app container
docker-compose down                 # Stop and remove containers
docker-compose down -v              # Also remove volumes
```

---

## <a id="chapter-29"></a>💡 Chapter 29 — CI/CD Pipelines

### 📖 What is CI/CD?

```
CI = Continuous Integration
  Every code push → automatically:
  ✓ Run tests
  ✓ Check code style
  ✓ Build the app
  ✓ Report results

CD = Continuous Delivery / Continuous Deployment
  On success → automatically:
  ✓ Deploy to staging
  ✓ Run integration tests
  ✓ Deploy to production (with approval gates)

BEFORE CI/CD:
"Integration Hell" — developers work separately for weeks
Then try to merge → massive conflicts, bugs, broken features

WITH CI/CD:
Merge small changes every day → catch problems early
Deploy to production multiple times per day safely
```

### 📖 GitHub Actions — CI/CD Pipeline

```yaml
# .github/workflows/deploy.yml

name: Build, Test and Deploy

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  test:
    name: Run Tests
    runs-on: ubuntu-latest
    
    services:
      postgres:
        image: postgres:15
        env:
          POSTGRES_PASSWORD: testpass
          POSTGRES_DB: testdb
        ports:
          - 5432:5432
        options: >-
          --health-cmd pg_isready
          --health-interval 10s
          --health-timeout 5s
          --health-retries 5

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Run linting
        run: npm run lint

      - name: Run unit tests
        run: npm test
        env:
          DATABASE_URL: postgres://postgres:testpass@localhost:5432/testdb

      - name: Run coverage report
        run: npm run coverage

  build:
    name: Build Docker Image
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'

    outputs:
      image-tag: ${{ steps.meta.outputs.tags }}

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Log in to registry
        uses: docker/login-action@v3
        with:
          registry: ${{ env.REGISTRY }}
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}

      - name: Extract metadata
        id: meta
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}
          tags: |
            type=sha,prefix={{branch}}-

      - name: Build and push
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: ${{ steps.meta.outputs.tags }}
          cache-from: type=gha
          cache-to: type=gha,mode=max

  deploy-staging:
    name: Deploy to Staging
    needs: build
    runs-on: ubuntu-latest
    environment: staging

    steps:
      - name: Deploy to staging server
        uses: appleboy/ssh-action@v1.0.0
        with:
          host: ${{ secrets.STAGING_HOST }}
          username: deploy
          key: ${{ secrets.STAGING_SSH_KEY }}
          script: |
            cd /opt/myapp
            docker pull ${{ needs.build.outputs.image-tag }}
            docker-compose up -d --no-deps app
            sleep 5
            curl -sf http://localhost:3000/health || exit 1
            echo "Staging deployment successful!"

  deploy-production:
    name: Deploy to Production
    needs: deploy-staging
    runs-on: ubuntu-latest
    environment: production    # Requires manual approval!

    steps:
      - name: Deploy to production
        uses: appleboy/ssh-action@v1.0.0
        with:
          host: ${{ secrets.PROD_HOST }}
          username: deploy
          key: ${{ secrets.PROD_SSH_KEY }}
          script: |
            cd /opt/myapp
            docker pull ${{ needs.build.outputs.image-tag }}
            docker-compose up -d --no-deps --scale app=3 app
            sleep 10
            curl -sf http://localhost/health || exit 1
            echo "Production deployment successful!"
```

---

## <a id="chapter-30"></a>💡 Chapter 30 — Infrastructure as Code (IaC)

### 📖 What is IaC?

```
WITHOUT IaC (ClickOps):
  Go to AWS console → Click to create server → Click to configure
  → Result: undocumented, hard to reproduce, no version control

WITH IaC:
  Write code describing your infrastructure
  → Git commit it
  → Apply with one command
  → Recreate identical infrastructure anywhere, anytime
```

### 📖 Terraform — The IaC Standard

```hcl
# main.tf — Create an AWS web server

terraform {
  required_version = ">= 1.0"
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "production/terraform.tfstate"
    region = "us-east-1"
  }
}

provider "aws" {
  region = var.aws_region
}

# Variables
variable "aws_region" {
  default = "us-east-1"
}

variable "instance_type" {
  default = "t3.medium"
}

# Data sources
data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]   # Canonical (Ubuntu)
  
  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-*"]
  }
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  
  tags = {
    Name        = "main-vpc"
    Environment = "production"
  }
}

# Subnet
resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  map_public_ip_on_launch = true
  
  tags = { Name = "public-subnet" }
}

# Security group
resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

# EC2 instance
resource "aws_instance" "web" {
  ami                    = data.aws_ami.ubuntu.id
  instance_type          = var.instance_type
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]
  key_name               = "my-key-pair"

  user_data = <<-EOF
    #!/bin/bash
    apt update && apt install -y nginx
    systemctl enable --now nginx
  EOF

  tags = {
    Name = "web-server"
  }
}

# Output
output "public_ip" {
  value = aws_instance.web.public_ip
}
```

```bash
terraform init          # Initialize (download providers)
terraform plan          # Show what will change (DRY RUN!)
terraform apply         # Apply changes (with confirmation)
terraform destroy       # Destroy all resources
terraform show          # Show current state
```

### 📖 Ansible — Configuration Management

```yaml
# playbook.yml — configure a web server

---
- name: Configure Web Server
  hosts: webservers
  become: yes         # Use sudo

  vars:
    app_user: www-data
    app_dir: /var/www/myapp
    nginx_port: 80

  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes
        cache_valid_time: 3600

    - name: Install required packages
      apt:
        name:
          - nginx
          - python3
          - python3-pip
          - git
        state: present

    - name: Create application directory
      file:
        path: "{{ app_dir }}"
        state: directory
        owner: "{{ app_user }}"
        group: "{{ app_user }}"
        mode: '0755'

    - name: Deploy application from git
      git:
        repo: https://github.com/mycompany/myapp.git
        dest: "{{ app_dir }}"
        version: main
      notify: restart nginx

    - name: Copy nginx configuration
      template:
        src: nginx.conf.j2
        dest: /etc/nginx/sites-available/myapp
        mode: '0644'
      notify: restart nginx

    - name: Enable nginx site
      file:
        src: /etc/nginx/sites-available/myapp
        dest: /etc/nginx/sites-enabled/myapp
        state: link
      notify: restart nginx

    - name: Ensure nginx is enabled and running
      systemd:
        name: nginx
        enabled: yes
        state: started

  handlers:
    - name: restart nginx
      systemd:
        name: nginx
        state: reloaded
```

---

## <a id="chapter-31"></a>💡 Chapter 31 — Monitoring & Observability

### 📖 The Three Pillars of Observability

```
METRICS      → Numbers over time (CPU 80%, 1000 req/sec)
              Tools: Prometheus, Grafana, DataDog
              
LOGS         → Text records of events
              Tools: ELK Stack (Elasticsearch, Logstash, Kibana)
                     Loki + Grafana
                     
TRACES       → Follow a request through multiple services
              Tools: Jaeger, Zipkin, X-Ray
```

### 📖 Prometheus + Grafana (The Standard Stack)

```yaml
# prometheus.yml

global:
  scrape_interval: 15s        # How often to collect metrics
  evaluation_interval: 15s    # How often to evaluate rules

alerting:
  alertmanagers:
    - static_configs:
        - targets: ['alertmanager:9093']

rule_files:
  - "alerts.yml"

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']

  - job_name: 'node-exporter'           # Linux system metrics
    static_configs:
      - targets:
          - 'web1:9100'
          - 'web2:9100'
          - 'db1:9100'

  - job_name: 'nginx'
    static_configs:
      - targets: ['nginx:9113']          # nginx-prometheus-exporter

  - job_name: 'myapp'
    static_configs:
      - targets: ['app:3000']            # App exposes /metrics
```

```yaml
# alerts.yml — Alert rules

groups:
  - name: system
    rules:
      - alert: HighCPUUsage
        expr: 100 - (avg by(instance)(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100) > 90
        for: 5m
        labels:
          severity: warning
        annotations:
          summary: "CPU usage > 90% for 5 minutes"
          description: "Instance {{ $labels.instance }} CPU is at {{ $value }}%"

      - alert: HighMemoryUsage
        expr: (node_memory_MemTotal_bytes - node_memory_MemAvailable_bytes) / node_memory_MemTotal_bytes * 100 > 90
        for: 5m
        labels:
          severity: critical
        annotations:
          summary: "Memory usage > 90%"

      - alert: DiskAlmostFull
        expr: (node_filesystem_size_bytes - node_filesystem_free_bytes) / node_filesystem_size_bytes * 100 > 85
        for: 10m
        labels:
          severity: warning
        annotations:
          summary: "Disk {{ $labels.mountpoint }} is {{ $value }}% full"

      - alert: ServiceDown
        expr: up == 0
        for: 1m
        labels:
          severity: critical
        annotations:
          summary: "Service {{ $labels.job }} is DOWN"
```

---

---

# <a id="quiz-answers"></a>🧠 Quiz Answers

## Quiz 0 Answers — The Story of Linux
```
A1: Linus Torvalds created Linux in 1991.
A2: UNIX was expensive (high license fees), closed source (can't modify),
    and gave AT&T monopoly control over enterprise computing.
A3: Open source = source code is publicly available, free to use, 
    modify, and distribute.
A4: GNU provided the tools (compiler, shell, utilities).
    Linux provided the kernel (hardware management core).
A5: Answers may include: Android phones, Tesla cars, ISS, PlayStation,
    smart TVs, SpaceX rockets, stock exchanges.
A6: Cost (Linux is free vs $900/server for Windows), stability,
    security, better tooling for servers, package management.
```

## Quiz 1 Answers — File System
```
A1: / is the root directory — the starting point of the entire 
    Linux filesystem. Everything branches from here.
A2: /var/log/ (web server logs would be in /var/log/nginx/ or 
    /var/log/apache2/)
A3: cd ../alice goes up one level from /home/john to /home, 
    then into /home/alice
A4: /proc contains runtime information about the kernel and running 
    processes. It's a VIRTUAL filesystem — nothing is stored on disk.
    It's generated dynamically by the kernel.
A5: Configuration files go in /etc/
A6: Anything sent to /dev/null is discarded permanently. It's used to 
    suppress output: command > /dev/null
```

## Quiz 2 Answers — Permissions
```
A1: rwxr-xr--
    Owner (rwx): read, write, execute — full access
    Group (r-x): read, execute — can run but not modify
    Others (r--): read only — can see but not run or modify
A2: rwxr-xr-x = 7(4+2+1) 5(4+0+1) 5(4+0+1) = 755
A3: /usr/bin/passwd has SUID so that when ANY user runs it, 
    it executes with root privileges (needed to modify /etc/shadow
    which only root can write to).
A4: chmod 400 file.txt  (or chmod u=r,go= file.txt)
A5: Set permissions of ALL files/directories in /var/www recursively 
    to 755 (owner full, others read+execute)
A6: Default is 644 for files. 666 - 644 = umask 022
```

## Quiz 3 Answers — Users & Groups
```
A1: useradd is the base command (minimal, no home dir by default)
    adduser is a friendlier interactive script on Ubuntu/Debian
    that asks questions and creates home dir automatically
A2: Root can accidentally delete system files, misconfigure everything,
    security risk if account is compromised, no audit trail
A3: usermod -aG docker john  (-a means APPEND, don't replace groups!)
A4: UID 0 = root user (superuser/administrator)
A5: Security principle of least privilege. If nginx was compromised,
    attacker would have www-data access (limited), not root access
A6: alice ALL=(ALL) NOPASSWD: /usr/bin/apt
```

## Quiz 4 Answers — Shell Scripting
```
A1: Shebang line — tells OS which interpreter to use for this script.
    Without it, OS guesses (may use /bin/sh which lacks bash features)
A2: Double quotes "": variables ARE expanded ($VAR is replaced)
    Single quotes '': everything is LITERAL ($VAR stays as $VAR)
A3: if [ -f /path/to/file ]; then ... fi  OR  [ -f file ] && ...
A4: $? contains the exit code of the last executed command.
    0 = success, non-zero = some kind of error
A5: -e: exit if any command fails (catch errors early)
    -u: error if undefined variable used (catch typos)
    -o pipefail: catch failures inside pipes
    Together: makes scripts fail fast and loudly on errors
A6: local variables (local VAR=) are only visible inside the function.
    Global variables are visible everywhere in the script.
```

## Quiz 5 Answers — OSI & TCP/IP
```
A1: Layer 3 — Network layer
A2: Layer 4 — Transport layer
A3: UDP — because video streaming prioritizes speed over reliability.
    A lost frame is better than a delayed video (buffering).
    With TCP, lost packets cause retransmit → video freezes.
A4: Client sends SYN → Server responds SYN-ACK → Client sends ACK
    (3-way handshake)
A5: Router = Layer 3 (reads IP addresses)
    Switch = Layer 2 (reads MAC addresses)
A6: Convention/standard. IANA (Internet Assigned Numbers Authority)
    assigned these port numbers. Applications are configured to use
    these standard ports so clients know where to connect.
```

---

# <a id="lab-projects"></a>🔬 Lab Projects

## 🔬 Lab Project 1: Complete Linux Server Setup

**Goal:** Set up a production-ready Ubuntu server from scratch.

```bash
# STEP 1: Initial setup
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget git vim htop ufw fail2ban

# STEP 2: Create deployment user
sudo useradd -m -s /bin/bash deploy
sudo usermod -aG sudo deploy
sudo mkdir -p /home/deploy/.ssh
sudo chmod 700 /home/deploy/.ssh
# Copy your public key:
sudo cp ~/.ssh/authorized_keys /home/deploy/.ssh/
sudo chown -R deploy:deploy /home/deploy/.ssh

# STEP 3: Harden SSH
sudo tee /etc/ssh/sshd_config.d/hardening.conf << 'EOF'
PermitRootLogin no
PasswordAuthentication no
MaxAuthTries 3
LoginGraceTime 20
EOF
sudo systemctl reload sshd

# STEP 4: Configure firewall
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable

# STEP 5: Set up fail2ban
sudo systemctl enable --now fail2ban

# STEP 6: Create monitoring script
sudo tee /opt/health_check.sh << 'SCRIPT'
#!/bin/bash
LOG="/var/log/health.log"
DATE=$(date '+%Y-%m-%d %H:%M:%S')
CPU_LOAD=$(uptime | awk -F'average:' '{print $2}' | cut -d, -f1 | tr -d ' ')
MEM_USED=$(free | awk '/Mem:/{printf "%.0f", $3/$2*100}')
DISK_USED=$(df / | awk 'NR==2{gsub(/%/,""); print $5}')
echo "$DATE CPU:${CPU_LOAD} MEM:${MEM_USED}% DISK:${DISK_USED}%" >> $LOG
[ "$MEM_USED" -gt 90 ] && echo "$DATE ALERT: High memory!" >> $LOG
[ "$DISK_USED" -gt 85 ] && echo "$DATE ALERT: Disk nearly full!" >> $LOG
SCRIPT
sudo chmod +x /opt/health_check.sh

# STEP 7: Schedule monitoring
(crontab -l 2>/dev/null; echo "*/5 * * * * /opt/health_check.sh") | crontab -

echo "Server setup complete! Check /var/log/health.log for monitoring."
```

## 🔬 Lab Project 2: Web Server with Load Balancing

**Goal:** Set up nginx load balancing across multiple app instances.

```bash
# Install nginx
sudo apt install -y nginx

# Create two simple "app servers" (simulated with Python)
mkdir -p /opt/apps/app1 /opt/apps/app2

# App 1 on port 8081
cat > /opt/apps/app1/server.py << 'EOF'
#!/usr/bin/env python3
from http.server import HTTPServer, BaseHTTPRequestHandler

class Handler(BaseHTTPRequestHandler):
    def do_GET(self):
        if self.path == '/health':
            self.send_response(200)
            self.end_headers()
            self.wfile.write(b'{"status": "ok", "server": "app1"}')
        else:
            self.send_response(200)
            self.end_headers()
            self.wfile.write(b'Hello from App Server 1!')
    def log_message(self, format, *args):
        pass  # Suppress output

HTTPServer(('0.0.0.0', 8081), Handler).serve_forever()
EOF

# Similar for app2 on port 8082
sed 's/8081/8082/g; s/app1/app2/g' /opt/apps/app1/server.py > /opt/apps/app2/server.py

# Start both
python3 /opt/apps/app1/server.py &
python3 /opt/apps/app2/server.py &

# Configure nginx load balancer
sudo tee /etc/nginx/sites-available/loadbalancer << 'EOF'
upstream apps {
    least_conn;
    server 127.0.0.1:8081;
    server 127.0.0.1:8082;
}

server {
    listen 80;
    server_name _;

    location / {
        proxy_pass http://apps;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }

    location /health {
        access_log off;
        proxy_pass http://apps;
    }
}
EOF

sudo ln -sf /etc/nginx/sites-available/loadbalancer /etc/nginx/sites-enabled/
sudo rm -f /etc/nginx/sites-enabled/default
sudo nginx -t && sudo systemctl reload nginx

# Test
for i in {1..10}; do curl -s http://localhost; echo; done
# Should alternate between "App Server 1" and "App Server 2"!
```

## 🔬 Lab Project 3: Log Analysis Dashboard

```bash
#!/bin/bash
# log_analyzer.sh — Analyze nginx access log

LOG_FILE="/var/log/nginx/access.log"

echo "═══════════════════════════════════════"
echo "    NGINX ACCESS LOG ANALYSIS"
echo "    $(date '+%Y-%m-%d %H:%M:%S')"
echo "═══════════════════════════════════════"

echo ""
echo "📊 Total Requests:"
wc -l < "$LOG_FILE"

echo ""
echo "📊 Status Code Distribution:"
awk '{print $9}' "$LOG_FILE" | sort | uniq -c | sort -rn

echo ""
echo "📊 Top 10 IPs by Request Count:"
awk '{print $1}' "$LOG_FILE" | sort | uniq -c | sort -rn | head -10

echo ""
echo "📊 Top 10 Requested URLs:"
awk '{print $7}' "$LOG_FILE" | sort | uniq -c | sort -rn | head -10

echo ""
echo "📊 Error Requests (4xx and 5xx):"
awk '$9 ~ /^[45]/' "$LOG_FILE" | wc -l

echo ""
echo "📊 Requests per Hour (last 24h):"
awk '{print substr($4, 2, 14)}' "$LOG_FILE" | \
  awk -F: '{print $1":"$2":00"}' | \
  sort | uniq -c | tail -24
```

---

# <a id="your-devops-roadmap"></a>🗺️ Your DevOps Roadmap

## After Completing This Guide (What to Learn Next)

```
PHASE 1 — FOUNDATION (This Guide ✅)
  ✅ Linux Fundamentals & Advanced
  ✅ Networking Fundamentals & Advanced
  ✅ Bash Scripting
  ✅ SSH & Remote Access

PHASE 2 — CONTAINERIZATION (Next: 2-4 weeks)
  → Docker deep dive
  → Docker Compose
  → Container security
  → Container registries

PHASE 3 — ORCHESTRATION (4-6 weeks)
  → Kubernetes (k8s) fundamentals
  → Pods, Services, Deployments
  → Helm charts
  → kubectl commands

PHASE 4 — CI/CD (2-3 weeks)
  → GitHub Actions
  → Jenkins
  → GitLab CI
  → ArgoCD (GitOps)

PHASE 5 — CLOUD (4-6 weeks)
  → AWS / GCP / Azure fundamentals
  → EC2, S3, RDS, VPC
  → IAM (Identity and Access Management)
  → Cloud networking

PHASE 6 — IaC (3-4 weeks)
  → Terraform advanced
  → Ansible deep dive
  → Packer (image building)

PHASE 7 — MONITORING (2-3 weeks)
  → Prometheus + Grafana
  → ELK Stack (Elasticsearch, Logstash, Kibana)
  → Alerting strategies
  → SLOs, SLAs, error budgets

PHASE 8 — ADVANCED TOPICS
  → Service meshes (Istio)
  → GitOps (FluxCD, ArgoCD)
  → Security (DevSecOps)
  → Platform Engineering

TOTAL TIME: 6-12 months to job-ready DevOps Engineer
```

## 📚 Recommended Resources

```
FREE PLATFORMS:
  🌐 KodeKloud Play (free tier)    → https://kodekloud.com
  🌐 Linux Foundation (free labs)  → https://training.linuxfoundation.org
  🌐 AWS Skill Builder             → https://skillbuilder.aws
  🌐 Google Cloud Skills Boost     → https://cloudskillsboost.google
  🌐 Play with Docker              → https://labs.play-with-docker.com
  🌐 Katacoda Scenarios            → https://killercoda.com (free scenarios)
  🌐 OverTheWire Wargames          → https://overthewire.org (Linux via SSH)

BOOKS:
  📗 "The Linux Command Line" by William Shotts (FREE online)
  📗 "How Linux Works" by Brian Ward
  📗 "UNIX and Linux System Administration Handbook"
  📗 "Computer Networking: A Top-Down Approach" (textbook)

YOUTUBE CHANNELS:
  🎥 NetworkChuck        → Great for networking + cloud
  🎥 TechWorld with Nana → Best DevOps explanations
  🎥 Fireship            → Quick concept videos
  🎥 Linus Tech Tips     → Hardware/networking visually
```

---

*📖 This guide was built for absolute beginners who want to learn Linux, Networking, and DevOps from the ground up.*  
*🎯 Complete all lab projects and quizzes before moving to the next phase.*  
*💡 The best way to learn is to have a real Linux server to practice on — AWS Free Tier gives you one for free!*
