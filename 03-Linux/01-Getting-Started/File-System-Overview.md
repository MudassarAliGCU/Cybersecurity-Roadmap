# 🗂️ Linux File System Overview

> Everything you will ever do on Linux — installing software, reading logs, hardening a server, investigating a breach — happens somewhere inside one giant, organized tree of files. This chapter teaches you how that tree is built, why it's built that way, and how to move through it with confidence.

---

## 🎯 Learning Objectives

By the end of this chapter, you will be able to:

- Explain what a **file system** is and why every operating system needs one.
- Understand Linux's **hierarchical directory structure** starting from the root (`/`).
- Identify the **purpose of every major system directory**.
- **Navigate** the Linux file system confidently using core commands.
- Understand what a **mount point** is and why Linux doesn't use drive letters.
- Distinguish between **files, directories, links, and devices**.
- Explain why file system knowledge is essential for **cybersecurity** work.

---

## 📑 Table of Contents

- [Introduction](#-introduction)
- [What is the Linux File System?](#-what-is-the-linux-file-system)
- [Linux Directory Tree](#-linux-directory-tree)
- [Important Directories](#-important-directories)
- [How Linux Organizes Files](#-how-linux-organizes-files)
- [File Types in Linux](#-file-types-in-linux)
- [Mount Points](#-mount-points)
- [Absolute vs Relative Paths](#-absolute-vs-relative-paths)
- [Hidden Files](#-hidden-files)
- [Essential Navigation Commands](#-essential-navigation-commands)
- [Linux File System vs Windows File System](#-linux-file-system-vs-windows-file-system)
- [Real-World Examples](#-real-world-examples)
- [Cybersecurity Relevance](#-cybersecurity-relevance)
- [Common Beginner Mistakes](#-common-beginner-mistakes)
- [Best Practices](#-best-practices)
- [Visual Learning](#-visual-learning)
- [Practical Exercises](#-practical-exercises)
- [Interview Questions](#-interview-questions)
- [Quick Revision](#-quick-revision)
- [Key Takeaways](#-key-takeaways)
- [Further Reading](#-further-reading)
- [Next Chapter](#-next-chapter)

---

## 📖 Introduction

A **file system** is the method an operating system uses to organize, store, and retrieve data on a storage device. Without one, a disk would just be a meaningless block of raw bits — the file system is what turns that raw storage into files and folders you can actually work with.

**Why operating systems need this:** Every program you run needs to read configuration, write output, or load resources. A file system provides a consistent, predictable way for the OS and every application to locate and access data, no matter which physical disk it's actually stored on.

**Why Linux uses a hierarchical structure:** Linux organizes *everything* — user files, system configuration, even hardware devices — into a **single tree** starting from one root directory, written as `/`. Every file and folder on the system, regardless of which physical disk it lives on, has a defined place somewhere under that one tree.

**Windows vs. Linux organization** is one of the first real differences beginners notice:

| | Windows | Linux |
|---|---|---|
| **Structure** | Multiple separate trees, one per drive (`C:\`, `D:\`) | One single unified tree starting at `/` |
| **Storage access** | New drives appear as new drive letters | New drives are **mounted** into existing folders inside the tree |

> 💡 **Key Term:** A **hierarchy** is a system of organizing things in levels, where each level branches from the one above it — like a family tree, but for files and folders.

---

## 📂 What is the Linux File System?

In Linux, a **file** is simply a container for data — this includes documents, photos, and scripts, but also configuration settings and even connections to hardware.

A **directory** (what Windows calls a "folder") is a special kind of file that contains references to other files and directories, letting you group and organize things.

**"Everything is a file"** is one of Linux's foundational design philosophies. It means that not just documents and programs are treated as files — **hardware devices, running processes, and system information** are represented as files too. For example:

- `/dev/sda` represents your first storage disk as a file.
- `/proc/cpuinfo` represents live information about your CPU, readable like a text file.

This design means the same small set of tools (read, write, list, search) works consistently across almost everything on the system — a huge simplification once you understand it.

**The root directory (`/`)** is the very top of this entire structure — the single starting point every other file and folder branches out from. It is *not* the same as the `/root` folder (the home directory for the root user), a distinction that trips up many beginners — covered in [Common Beginner Mistakes](#-common-beginner-mistakes).

---

## 🌳 Linux Directory Tree

Every single file on a Linux system — no matter which physical disk it's stored on — fits somewhere inside this one tree, starting at `/`:

```
/
├── bin      → Essential user command binaries
├── boot     → Boot loader files and the kernel
├── dev      → Device files (hardware represented as files)
├── etc      → System-wide configuration files
├── home     → Personal directories for regular users
├── lib      → Shared libraries needed by binaries in /bin and /sbin
├── media    → Mount points for removable media (USB, DVD)
├── mnt      → Temporary mount points for manually mounted filesystems
├── opt      → Optional/add-on software packages
├── proc     → Virtual filesystem exposing kernel and process information
├── root     → Home directory for the root (superuser) account
├── run      → Runtime data for processes since the last boot
├── sbin     → Essential system administration binaries
├── srv      → Data for services provided by the system (e.g., web files)
├── sys      → Virtual filesystem exposing kernel/device information
├── tmp      → Temporary files, cleared on reboot
├── usr      → User-installed software, libraries, and documentation
└── var      → Variable data: logs, caches, spool files
```

> 📌 **Note:** This layout follows the **Filesystem Hierarchy Standard (FHS)** — a specification most major Linux distributions follow so that directory purposes stay consistent across different systems.

---

## 🧭 Important Directories

| Directory | Purpose | Typical Contents | Real-World Example |
|---|---|---|---|
| **/** | The root of the entire file system | Every other directory | The starting point for any absolute path |
| **/bin** | Essential commands available to all users | `ls`, `cp`, `mv`, `bash` | Running `ls` actually executes `/bin/ls` |
| **/sbin** | Essential commands for system administration | `reboot`, `iptables`, `fdisk` | A sysadmin running `fdisk` to manage disk partitions |
| **/boot** | Files needed to start the system | Kernel image, GRUB bootloader files | The Ubuntu kernel file loaded at every startup |
| **/dev** | Device files representing hardware | `/dev/sda` (disk), `/dev/null` (discard) | Writing to `/dev/null` to silently discard command output |
| **/etc** | System-wide configuration files | `passwd`, `ssh/sshd_config`, `hosts` | Editing `/etc/hosts` to manually map a domain to an IP |
| **/home** | Personal directories for each user | `/home/alice`, `/home/bob` | Your Desktop, Downloads, and Documents folders |
| **/root** | Home directory for the root (superuser) account | Root's personal files and configs | Root's own `.bashrc` file, separate from regular users |
| **/lib** | Shared libraries required by core binaries | `.so` shared object files | A library `/bin/ls` depends on to run correctly |
| **/media** | Automatic mount points for removable media | USB drive, DVD mount folders | Plugging in a USB stick, which appears under `/media/username/` |
| **/mnt** | Temporary, manual mount points | Empty by default, used ad hoc | An admin manually mounting a network share for one session |
| **/opt** | Optional third-party software packages | Vendor-installed applications | A commercial security tool installed under `/opt/toolname` |
| **/proc** | Virtual files exposing kernel/process data | `/proc/cpuinfo`, `/proc/[PID]` | Checking live CPU details via `cat /proc/cpuinfo` |
| **/run** | Runtime data since the last boot | PID files, sockets | A service's lock file confirming it's currently running |
| **/srv** | Data served by this system | Web server files, FTP data | An Apache site's files stored under `/srv/www` |
| **/sys** | Virtual files exposing kernel/device info | Device and driver details | Checking a network interface's live status |
| **/tmp** | Temporary files, cleared on reboot | Scratch files from applications | A program's temporary cache file during installation |
| **/usr** | Installed software, libraries, documentation | `/usr/bin`, `/usr/share` | Most user-installed apps live somewhere under `/usr` |
| **/var** | Variable, frequently changing data | Logs, mail spools, caches | Reading `/var/log/auth.log` to review login attempts |

---

## 🗃️ How Linux Organizes Files

Linux separates different categories of data into predictable locations, which keeps the system organized and predictable even as it grows:

- **User files** — Personal documents, downloads, and projects, stored under `/home/username`.
- **Configuration files** — System and application settings, stored under `/etc` (e.g., `/etc/ssh/sshd_config` controls SSH server behavior).
- **Executable files** — Programs and commands, mainly under `/bin`, `/sbin`, and `/usr/bin`.
- **Device files** — Representations of hardware, under `/dev` (e.g., `/dev/sr0` for an optical drive).
- **Log files** — Records of system and application activity, under `/var/log` (e.g., `/var/log/syslog`).
- **Temporary files** — Short-lived scratch data, under `/tmp`, automatically cleared on reboot.

This separation is exactly why professionals can jump onto almost *any* Linux server and immediately know roughly where to look for logs, configs, or user data — the structure is consistent by design.

---

## 📄 File Types in Linux

Linux recognizes several distinct file types, each serving a different purpose:

| File Type | Symbol (in `ls -l`) | Common Use |
|---|---|---|
| **Regular file** | `-` | Documents, scripts, images, binaries |
| **Directory** | `d` | Containers organizing other files |
| **Symbolic link** | `l` | A shortcut pointing to another file's path (like a Windows shortcut) |
| **Hard link** | `-` (shares the same inode) | An additional direct reference to the same underlying file data |
| **Character device** | `c` | Devices transferring data one character at a time (e.g., keyboards, serial ports) |
| **Block device** | `b` | Devices transferring data in fixed-size blocks (e.g., hard disks, `/dev/sda`) |
| **Named pipe (FIFO)** | `p` | Allows two processes to communicate by writing/reading data in order |
| **Socket** | `s` | Enables communication between processes, often over a network |

> 💡 **Key Term:** An **inode** is a data structure storing all the metadata about a file (permissions, owner, size, location on disk) — everything except the file's actual name.

**Symbolic vs. hard links, in practice:** if you delete the *original* file, a symbolic link breaks (it was only pointing to a path), while a hard link keeps working (it points directly to the same underlying data).

---

## 💽 Mount Points

**Mounting** is the process of attaching a storage device's filesystem to a specific folder (a "mount point") within the existing Linux directory tree, making its contents accessible as if they were simply another folder on your system.

**Why Linux mounts drives instead of assigning letters:** Because everything lives in one unified tree, adding a new disk doesn't require inventing a new top-level structure (like Windows' `D:\`) — it just attaches into an existing folder, keeping the single-tree design consistent no matter how much storage you add.

```
Before mounting a USB drive:
/media/username/            (empty folder)

After mounting a USB drive:
/media/username/USB_DRIVE/
        ├── photos/
        └── documents/
```

- **External USB drives** are typically auto-mounted under `/media/username/`.
- **SSDs and internal disks** are usually mounted at boot time based on rules in `/etc/fstab`, often directly at `/` or under `/home`.
- **Network storage** (like an NFS or SMB share) can be mounted at any folder you choose, commonly under `/mnt`, making a remote server's files appear local.

```bash
mount /dev/sdb1 /mnt/usb_drive     # Manually mount a device to a folder
umount /mnt/usb_drive               # Safely detach it
```

---

## 🧭 Absolute vs Relative Paths

An **absolute path** always starts from the root (`/`) and describes the complete location of a file, no matter where you currently are in the file system.

A **relative path** describes a location **relative to your current directory** — shorter, but only meaningful from where you're currently standing.

```
Absolute Path:  /home/student/Documents/report.txt
                       (always works, from anywhere)

Relative Path:  Documents/report.txt
                       (only works if you're currently inside /home/student)
```

```
Current directory: /home/student
        │
        ▼
   Documents/report.txt   →  resolves to  →  /home/student/Documents/report.txt
```

> ✅ **Tip:** When writing scripts meant to run reliably from anywhere, prefer **absolute paths** — relative paths depend on the shell's current directory at the time of execution, which can easily be wrong.

---

## 🙈 Hidden Files

Any file or directory whose name begins with a **dot (`.`)** is treated as **hidden** by Linux and won't appear in a normal directory listing. This convention is used heavily for **configuration files**, keeping a user's home directory visually clean while still storing plenty of settings.

Common examples:
- **`.bashrc`** — Configuration script run every time a new terminal (Bash shell) session starts.
- **`.profile`** — Executed when a user logs in, often setting environment variables.
- **`.gitconfig`** — Stores a user's personal Git settings (name, email, preferences).

```bash
ls -a        # Lists all files, including hidden ones
```

> ⚠️ **Note:** Hidden files aren't a security feature — they're purely a display convention. Anyone with access to the directory can still view them with the right command or flag.

---

## 🧑‍💻 Essential Navigation Commands

| Command | Purpose | Example |
|---|---|---|
| `pwd` | Prints your current working directory | `pwd` → `/home/student` |
| `ls` | Lists directory contents | `ls -la` → shows all files with details |
| `cd` | Changes your current directory | `cd /var/log` |
| `tree` | Displays a directory's contents as a visual tree | `tree /etc -L 1` |
| `find` | Searches for files by name, type, or other criteria, scanning in real time | `find / -name "*.conf"` |
| `locate` | Searches a prebuilt index of file names — much faster than `find`, but may be slightly outdated | `locate passwd` |

```bash
$ pwd
/home/student

$ ls -la
drwxr-xr-x  5 student student 4096 Jul  6 10:15 .
drwxr-xr-x  3 root    root    4096 Jul  1 09:00 ..
-rw-r--r--  1 student student  220 Jul  1 09:00 .bashrc
drwxr-xr-x  2 student student 4096 Jul  6 10:14 Documents

$ cd Documents
$ pwd
/home/student/Documents
```

> 💡 **Tip:** `find` searches live (slower, always accurate), while `locate` checks a cached database (faster, but needs to be refreshed with `sudo updatedb` to reflect very recent changes).

---

## 🆚 Linux File System vs Windows File System

| Feature | Windows | Linux |
|---|---|---|
| **Drive Letters** | Uses letters like `C:\`, `D:\` for each drive | No drive letters — everything mounts into one tree |
| **Directory Structure** | Multiple separate trees, one per drive | Single unified tree starting at `/` |
| **Path Separator** | Backslash `\` | Forward slash `/` |
| **Case Sensitivity** | Not case-sensitive (`Report.txt` = `report.txt`) | Case-sensitive (`Report.txt` ≠ `report.txt`) |
| **Configuration Files** | Stored in the Registry (binary database) | Stored as plain-text files, mostly under `/etc` |
| **Executable Files** | Identified by extension (`.exe`, `.bat`) | Identified by permission bits, not file extension |
| **Permissions** | ACL-based, more complex GUI-driven model | Owner/Group/Other model with read/write/execute bits |

---

## 🌐 Real-World Examples

- **Google Chrome** stores its user profile and configuration under `~/.config/google-chrome/` (where `~` means the current user's home directory).
- **Apache web server** typically stores its configuration under `/etc/apache2/` (Debian-based) and serves website files from `/var/www/html/`.
- **System and application logs** live under `/var/log/`, such as `/var/log/syslog` or `/var/log/nginx/access.log`.
- **SSH keys** are stored under `~/.ssh/`, with `~/.ssh/authorized_keys` controlling which public keys are allowed to log in.

---

## 🛡️ Cybersecurity Relevance

Understanding the Linux file system isn't academic — it directly shapes how security work gets done:

- **Penetration Testing** — Knowing where configuration files, credentials, and SUID binaries typically live speeds up privilege escalation during authorized assessments.
- **Digital Forensics** — Investigators examine specific directories (`/var/log`, `/tmp`, `/home`) and file metadata (timestamps, ownership) to reconstruct what happened on a system.
- **Incident Response** — Responders need to quickly locate relevant logs and configuration to understand and contain a breach, often under serious time pressure.
- **Malware Analysis** — Malware often hides in predictable locations (`/tmp`, `/dev/shm`, disguised names in `/usr/bin`), so recognizing what's "normal" makes anomalies obvious.
- **System Hardening** — Properly securing a server means understanding which directories hold sensitive configuration (`/etc/shadow`, `/etc/ssh/`) and restricting access accordingly.
- **Log Analysis** — Nearly every investigation starts with logs in `/var/log`, so navigating there confidently is a foundational skill.
- **Privilege Escalation** — Attackers and testers alike look for misconfigured permissions on system files and directories as a path to higher access.

> 🧪 **Practical Example:** A penetration tester finds a world-writable script in `/etc/cron.d/` — since cron jobs often run as root, this misconfiguration could allow a low-privilege user to escalate to root by editing that script.

---

## ❌ Common Beginner Mistakes

> ⚠️ **Thinking Linux uses `C:\` drives.** Linux has no drive letters — new storage devices are mounted into the existing single directory tree instead.

> ⚠️ **Deleting system files accidentally.** Running destructive commands (like `rm -rf`) inside directories such as `/etc` or `/bin` without understanding their purpose can break the entire system.

> ⚠️ **Confusing `/root` with `/`.** `/` is the top of the entire file system; `/root` is simply the home directory belonging to the root (superuser) account — two very different things.

> ⚠️ **Not understanding hidden files.** Beginners often can't find configuration files because they forget dotfiles (like `.bashrc`) don't appear in a normal `ls` listing — remember to use `ls -a`.

---

## 🏆 Best Practices

- Always double-check your current directory (`pwd`) before running destructive commands.
- Avoid working as the **root** user for everyday tasks — use `sudo` only when necessary.
- Get comfortable with `ls -la` early — hidden files matter more than they first appear to.
- Use **absolute paths** in scripts to avoid unexpected behavior based on your current directory.
- Before editing any file under `/etc`, make a backup copy first.
- Practice navigating with `cd`, `pwd`, and `tree` daily until it feels automatic — it's the foundation for every later chapter.

---

## 🖼️ Visual Learning

Some of these are well-suited to stable Wikimedia/official diagrams; others are specific enough that building or capturing your own keeps them accurate. Use this table as your shopping list:

| # | Suggested Visual | What It Should Show | Best Source |
|---|---|---|---|
| 1 | **Linux directory tree** | Visual version of the ASCII tree shown above | Already covered by the ASCII diagram — image optional |
| 2 | **"Standard-unix-filesystem-hierarchy.svg"** | Official-style Unix/Linux filesystem hierarchy chart | Wikimedia Commons (search this exact title) |
| 3 | **Mount point diagram** | Before/after view of a USB drive mounting into `/media` | Already covered by the ASCII diagram above — optional |
| 4 | **Absolute vs. relative path diagram** | Visual path resolution, like the ASCII example above | Already covered — optional |
| 5 | **Linux storage layout (partitions)** | Disk divided into EFI/root/swap/home sections | Reuse the partition diagram from `Installation.md`, if already in your repo |
| 6 | **Directory hierarchy chart (FHS)** | Formal Filesystem Hierarchy Standard chart | Official source: refspecs.linuxfoundation.org (FHS 3.0 spec PDF) |
| 7 | **File type icons** | Simple icon set distinguishing files, directories, links, devices | Build your own using a consistent icon set (e.g., Font Awesome / Material Icons) |
| 8 | **Terminal screenshot — `ls -la` output** | Your own terminal showing hidden files and permission bits | Take your own screenshot |
| 9 | **Terminal screenshot — `tree` output** | Your own terminal showing a folder rendered as a tree | Take your own screenshot |
| 10 | **`/proc` and `/sys` example** | Screenshot of `cat /proc/cpuinfo` output | Take your own screenshot |

```html
<p align="center">
<img src="IMAGE_URL" width="700">
</p>
```

---

## 🧪 Practical Exercises

1. Navigate to `/home` and list its contents.
2. Explore `/etc` and identify three configuration files you recognize.
3. Use `find` to locate a `.conf` file anywhere on the system.
4. Display your current directory using `pwd`.
5. View hidden files in your home directory with `ls -a`.
6. List directory contents in long format, including hidden files (`ls -la`).
7. Explore `/var/log` and open one log file with `less` or `cat`.

---

## ❓ Interview Questions

1. **What is the Linux root directory?**
   The single top-level directory (`/`) that every other file and folder on the system branches from.

2. **What is stored inside `/etc`?**
   System-wide configuration files controlling how services, users, and the system itself behave.

3. **Difference between `/home` and `/root`?**
   `/home` contains personal directories for regular users; `/root` is the dedicated home directory for the root (superuser) account only.

4. **What is a mount point?**
   A folder in the existing Linux directory tree where a storage device's filesystem is attached, making its contents accessible.

5. **Explain absolute and relative paths.**
   An absolute path always starts from `/` and works from anywhere; a relative path is based on your current directory and only resolves correctly from there.

6. **What are hidden files?**
   Files or directories whose names start with a dot (`.`), excluded from a normal `ls` listing and commonly used for configuration.

---

## 📝 Quick Revision

| Concept | One-Line Summary |
|---|---|
| **File system** | The method Linux uses to organize and access data on storage |
| **Root (`/`)** | The single starting point of the entire directory tree |
| **Everything is a file** | Devices, processes, and configs are all represented as files |
| **Mounting** | Attaching a storage device to a folder in the existing tree |
| **Absolute path** | Full location starting from `/`, works from anywhere |
| **Relative path** | Location based on your current directory |
| **Hidden files** | Names starting with `.`, hidden from normal listings |

---

## 🔑 Key Takeaways

- Linux organizes everything — files, devices, and processes — into **one unified tree** starting at `/`.
- Each top-level directory (`/etc`, `/var`, `/home`, etc.) has a **specific, standardized purpose**.
- Linux **mounts** storage into the existing tree instead of using drive letters like Windows.
- Understanding **absolute vs. relative paths** and **hidden files** prevents common beginner confusion.
- File system knowledge directly supports **forensics, incident response, hardening, and privilege escalation** work in cybersecurity.

---

## 📚 Further Reading

- **Filesystem Hierarchy Standard (FHS):** [refspecs.linuxfoundation.org](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html)
- **Linux Foundation documentation:** [linuxfoundation.org](https://www.linuxfoundation.org/)
- **Ubuntu official documentation:** [help.ubuntu.com](https://help.ubuntu.com/)
- **Official man pages:** run `man hier` in any terminal for a manual page describing the entire directory layout.

---

