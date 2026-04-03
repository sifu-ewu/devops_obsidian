---
aliases: [First Day on Linux, Terminal Basics, Shell]
tags: [part1, linux-fundamentals, terminal, shell, beginner]
chapter: 1
---

# 💡 Chapter 1 — Your First Day on Linux

> [!info] **Part of** [[Part 1 — Linux Fundamentals]]

---

## 📖 The Big Mental Shift: Linux vs Windows/Mac

```
GUI (Graphical User Interface) = Driving with automatic transmission
CLI (Command Line Interface)   = Driving with manual/stick shift

Automatic: Easy to start, limited control
Manual:    Takes learning, gives full control, faster once you know it
```

---

## 📖 What Is a Shell?

A **shell** is the program that reads your commands and executes them. The most common shell is **Bash** (Bourne Again Shell).

```
You type:   ls
Shell reads: "list files" command
Shell talks to: Linux Kernel
Kernel does: Look at filesystem
Result displayed: Files listed on screen
```

> [!tip] The shell is also the foundation of [[Ch 08 — Bash Shell Scripting|Bash scripting]] — automating tasks by saving commands in a file.

---

## 💻 Opening the Terminal

**Ubuntu/Debian GUI:** Press `Ctrl + Alt + T`

**What you see:**
```bash
john@myserver:~$
│    │         │└─ $ = regular user  (# = root/admin user)
│    │         └── ~ = current directory (~ means home directory)
│    └──────────── myserver = machine hostname
└───────────────── john = your username
```

---

## 💻 Your First 10 Commands

```bash
whoami              # Who am I?
pwd                 # Where am I? (Print Working Directory)
date                # What's the date?
who                 # Who is logged in?
hostname            # What computer is this?
uname -a            # What OS/kernel is this?
uptime              # How long has this been running?
echo "Hello!"       # Display something
clear               # Clear the screen (Ctrl+L also works)
man ls              # Get help for any command (q to quit)
```

---

## 📖 Understanding Command Structure

```
command  [options]  [arguments]
   │         │           │
   │         │           └── WHAT to act on (file, directory, etc.)
   │         └──────────── HOW to do it (flags modify behavior)
   └────────────────────── WHAT to do

Examples:
ls             → just list
ls -l          → list with details
ls -la         → list with details + hidden files
ls -la /var    → list /var directory with details + hidden
```

**Options can be combined:** `ls -l -a -h` = `ls -lah`

---

## 📖 Getting Help

```bash
man command         # Full manual (press q to quit)
command --help      # Quick help
whatis command      # One-line description
apropos keyword     # Search man pages for keyword
```

---

> [!lab]- 🔬 Mini Lab 1: Terminal Exploration
> ```bash
> # Run all 10 commands above, then try:
> history             # See your command history!
> history | tail -20  # Last 20 commands
> !!                  # Re-run last command
> Ctrl+R              # Search command history
> 
> # TAB completion:
> # Type: ls /et  then press TAB → auto-completes to ls /etc/
> 
> # Keyboard shortcuts:
> # Ctrl+C → Cancel command | Ctrl+A → Beginning of line
> # Ctrl+E → End of line    | Ctrl+U → Clear line
> ```
> 
> **Task:** Find out how many CPUs your computer has. Hint: look in `/proc/cpuinfo`.

---

> **Navigation:** [[Part 1 — Linux Fundamentals]] | **Next →** [[Ch 02 — The Linux File System]]
