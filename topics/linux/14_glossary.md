# Chapter 14: Linux Glossary

This glossary provides concise definitions for the core concepts, components, and commands covered in this track. Use it as a quick reference when troubleshooting or architecting Linux-based systems.

---

## 14.1 Core System Terms
| Term | Definition |
| :--- | :--- |
| **Kernel** | The heart of the OS that manages hardware, memory, and process scheduling. |
| **Distribution (Distro)** | A version of Linux (like Ubuntu or Fedora) that bundles the kernel with tools and a package manager. |
| **Shell** | The command-line interpreter (e.g., Bash or Zsh) that acts as the interface between the user and the kernel. |
| **User Space** | The memory area where user applications run, isolated from the critical system resources of the Kernel Space. |
| **Root** | The "Superuser" account that has unrestricted access to all files and commands on the system. |
| **Systemd** | The modern "init" system used to bootstrap the user space and manage system services (daemons). |

---

## 14.2 Filesystem & Permissions
| Term | Definition |
| :--- | :--- |
| **FHS** | Filesystem Hierarchy Standard: The standardized layout of directories in Linux (e.g., `/etc` for configs, `/var` for logs). |
| **Inode** | A data structure that stores metadata about a file (size, owner, permissions) but not its name or actual data. |
| **Symbolic Link (Symlink)** | A special type of file that serves as a shortcut or pointer to another file or directory. |
| **Permissions (rwx)** | Read, Write, and Execute. These define what actions a User, Group, or Others can take on a file. |
| **Sticky Bit** | A permission bit set on directories that prevents users from deleting files owned by others within that directory. |

---

## 14.3 Processes & Execution
| Term | Definition |
| :--- | :--- |
| **PID** | Process ID: A unique numerical identifier assigned by the kernel to every running process. |
| **Daemon** | A background process that runs non-interactively (e.g., a web server or database engine). |
| **Fork** | The operation where a process creates a copy of itself to execute a new task. |
| **Zombie Process** | A process that has finished execution but still has an entry in the process table because its parent hasn't "reaped" it. |
| **Signal** | A notification sent to a process to trigger a specific action (e.g., `SIGTERM` to stop or `SIGHUP` to reload). |

---

## 14.4 Networking & Streams
| Term | Definition |
| :--- | :--- |
| **Standard Streams** | The three default communication channels for a process: `stdin` (0), `stdout` (1), and `stderr` (2). |
| **Pipe (|)** | A redirection operator that feeds the output of one command into the input of another. |
| **SSH** | Secure Shell: A protocol for encrypted remote login and command execution over a network. |
| **Port** | A logical endpoint for network communication (e.g., Port 80 for HTTP). |
| **IP Address** | A numerical label assigned to each device connected to a computer network. |

---

## 14.5 Automation & Scripting
| Term | Definition |
| :--- | :--- |
| **Shebang (#!)** | The first line of a script that tells the OS which interpreter (like `/bin/bash`) to use to run the file. |
| **Environment Variable** | A dynamic-named value that can affect the way running processes behave on a computer (e.g., `$PATH`). |
| **One-Liner** | A complex sequence of commands joined by pipes or logical operators to perform a task in a single terminal entry. |
| **Cron** | A time-based job scheduler used to run scripts or commands automatically at specific intervals. |

---

## 14.6 Troubleshooting & Maintenance
| Term | Definition |
| :--- | :--- |
| **Kernel Panic** | A safety measure taken by the kernel upon detecting a fatal error from which it cannot safely recover. |
| **Dependency** | A software library or package required by another program to function correctly. |
| **Repository** | A centralized server where software packages are stored and made available for installation. |
| **Log Rotation** | The process of archiving old log files and starting new ones to prevent the disk from filling up. |

---

> **Congratulations!** You have completed the Linux Systems Engineering track. You now possess the foundational skills required to navigate, manage, and automate the world's most powerful operating system.
