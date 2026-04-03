---
aliases: [Storage, Disk Management, LVM, Partitions, fstab]
tags: [part2, linux-intermediate, storage, lvm, disk]
chapter: 10
---

# 💡 Chapter 10 — Storage & Disk Management

> [!info] **Part of** [[Part 2 — Linux Intermediate]]

---

## 📖 Understanding Storage (Analogy)

```
Disk          → A physical filing cabinet
Partition     → Drawers in the cabinet
Filesystem    → Filing system within drawer (alphabetical, etc.)
Mount point   → The door you use to access the drawer (/mnt/data)
```

---

## 💻 Disk Information

```bash
lsblk                   # Block devices in tree format
lsblk -f                # With filesystem types and UUIDs
fdisk -l                # All disks and partitions (root)
df -h                   # Human-readable disk usage
df -i                   # Inode usage
du -sh /var/*           # Size of each item in /var
du -sh /* | sort -rh | head -10   # Top 10 biggest directories
find / -type f -size +500M 2>/dev/null  # Files > 500MB

sudo apt install ncdu   # Interactive disk usage explorer
ncdu /
```

---

## 💻 Filesystems

```bash
mkfs.ext4 /dev/sdb1     # ext4 (most common)
mkfs.xfs /dev/sdb2      # XFS (great for large files, RHEL default)
fsck /dev/sdb1           # Check for errors (must be unmounted!)
```

---

## 💻 Mounting

```bash
mount /dev/sdb1 /mnt/data           # Temporary mount
umount /mnt/data                    # Unmount

# Permanent mount via /etc/fstab:
blkid /dev/sdb1                     # Get UUID
# Add to /etc/fstab:
# UUID=a1b2c3d4-xxxx /mnt/data ext4 defaults 0 2
mount -a                            # Mount everything in fstab
```

---

## 💻 LVM — Logical Volume Manager (DevOps Essential!)

> [!devops] ⚡ Why LVM?
> Without LVM, if your disk fills up, you're stuck. With LVM, you can resize volumes **without downtime**, add new disks, and create snapshots. Used extensively in [[Ch 28 — Docker & Containers|Docker]] and cloud environments.

```
Physical Disk(s) → Physical Volume(s) → Volume Group → Logical Volume(s)

/dev/sdb (500GB) ─┐
                   ├─ Volume Group "data_vg" (800GB total)
/dev/sdc (300GB) ─┘   ├─ Logical Volume "app_lv" (200GB) → /opt/app
                       ├─ Logical Volume "db_lv" (400GB)  → /var/lib/mysql
                       └─ Logical Volume "log_lv" (100GB) → /var/log
```

```bash
# Create
pvcreate /dev/sdb /dev/sdc
vgcreate data_vg /dev/sdb /dev/sdc
lvcreate -L 200G -n app_lv data_vg
mkfs.ext4 /dev/data_vg/app_lv
mount /dev/data_vg/app_lv /opt/app

# Extend (NO DOWNTIME!)
lvextend -L +100G /dev/data_vg/db_lv
resize2fs /dev/data_vg/db_lv           # Grow ext4
```

---

> **Navigation:** **← Prev** [[Ch 09 — Text Processing]] | [[Part 2 — Linux Intermediate]] | **Next →** [[Ch 11 — Environment Systemd & Services]]
