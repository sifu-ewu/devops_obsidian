---
aliases:
  - World Before Linux
  - UNIX History
tags:
  - part0
  - linux-history
  - unix
completed: false
chapter: 0.1
---

# 📖 Chapter 0.1 — The World Before Linux (1969–1991)

> [!info] **Part of** [[Part 0 — The Story of Linux]]

---

## 🌍 The State of Computing in the 1960s–70s

Imagine it's 1969. Computers exist, but they are **the size of entire rooms**, cost **millions of dollars**, and are owned only by governments, universities, and huge corporations.

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

---

## 🔑 UNIX is Born — AT&T Bell Labs (1969)

At **AT&T Bell Labs**, a group of incredibly smart engineers — **Ken Thompson, Dennis Ritchie, and Brian Kernighan** — built an operating system called **UNIX**.

**Why did they build it?** They were working on a massive project called Multics that collapsed. Frustrated, Ken Thompson sneaked some time on an old machine (PDP-7) and built a simpler system.

**UNIX was revolutionary:**
- Multiple users could use it at the same time
- Written in **C language** (also invented at Bell Labs)
- Had a **file system** we still recognize today
- Was **portable** — could run on different hardware

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

---

## 💰 The Big Problem: UNIX Was EXPENSIVE and CLOSED

In the 1980s, AT&T realized UNIX was valuable and started **charging enormous licensing fees**:

- Universities had to pay thousands of dollars per license
- The **source code was secret** — you couldn't see how it worked
- You couldn't modify it or share it

> [!warning] This created a huge problem
> - **Students** couldn't learn from the source code
> - **Developers** couldn't build on it freely
> - **Companies** were at the mercy of AT&T's pricing
> - Innovation was **locked behind a paywall**

---

## 🎓 The Academic Workaround: MINIX

In 1987, professor **Andrew Tanenbaum** wrote a small UNIX-like OS called **MINIX** for teaching purposes. It had one major limitation: Tanenbaum refused to let students modify the core.

A young Finnish student named **Linus Torvalds** used MINIX, wanted more from it, and decided to do something about it.

---

> [!success]- ✅ Mark this chapter as done
> Scroll to the **top of this note** → click the **`completed`** checkbox in the Properties panel → it automatically ticks in [[Progress Tracker]].

---
> [!tip] 🧭 Navigation
> [[Part 0 — The Story of Linux]] | **Next →** [[Ch 0.2 — Birth of Linux]]
