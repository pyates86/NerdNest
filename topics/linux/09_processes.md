# Chapter 9: Process Management

Every time you run a command, start a script, or open an application, the Linux Kernel creates a **Process**. A process is simply an executing instance of a program. Because Linux is a multi-tasking system, it is constantly juggling hundreds of processes, giving each a tiny slice of CPU time.

As an engineer, you must know how to monitor these processes, identify resource hogs, and terminate "zombie" or runaway tasks.

---

## 9.1 Anatomy of a Process
Every process in Linux is identified by a unique number called a **PID (Process ID)**. 

### The Process Hierarchy
Processes follow a "Parent-Child" relationship.
* When you open a terminal, your **Shell** (Bash) is a process.
* When you run `ls` inside that terminal, Bash "forks" a new process to run `ls`. 
* In this case, Bash is the **Parent** and `ls` is the **Child**.
* The very first process that starts when Linux boots is `systemd` (PID 1). It is the ancestor of every other process on the system.

---

## 9.2 Monitoring Processes
To see what is happening on your system right now, use these core tools:

* **`ps` (Process Status):** A snapshot of current processes.
    * `ps aux`: Shows every process running on the system by every user.
* **`top`:** A real-time, interactive view of processes, CPU usage, and memory.
* **`htop`:** A modern, colorized, and more user-friendly version of `top` (requires installation on some systems).

---

## 9.3 Foreground vs. Background
When you run a command, it usually "owns" your terminal until it finishes. This is a **Foreground** process.

* **Moving to Background:** Add an `&` to the end of a command to run it in the background.
    * `python3 long_script.py &`
* **Suspending:** Press `Ctrl + Z` to "pause" a running foreground process.
* **Resuming:** * `bg`: Resumes a paused process in the background.
    * `fg`: Brings a background process back to the foreground.
* **`jobs`:** Lists all processes currently running in your shell session.

---

## 9.4 Killing Processes: Signals
Linux communicates with processes using **Signals**. The `kill` command is used to send these signals to a specific PID.

| Signal | Name | Effect |
| :--- | :--- | :--- |
| **15** | `SIGTERM` | The "Polite" kill. Asks the process to save its data and shut down. |
| **9** | `SIGKILL` | The "Hard" kill. Instantly stops the process. Use this only if `15` fails. |
| **2** | `SIGINT` | Interrupt. What happens when you press `Ctrl + C`. |

**Usage:**
```bash
kill 1234       # Sends SIGTERM to PID 1234
kill -9 1234    # Forcefully kills PID 1234
```

---

## 9.5 Nice Values: CPU Priority
Not all processes are equally important. Linux uses a "Niceness" scale from **-20** (Highest priority) to **19** (Lowest priority). 
* A "nice" process is polite and lets others use the CPU first.
* `renice +10 1234`: Makes process 1234 "nicer" (lower priority) so it doesn't slow down the system.

---

## 🛠 Hands-on: Managing a Runaway Task
Try this sequence to practice process control:

1.  **Start a "fake" long task:** `sleep 1000 &`
2.  **Find its PID:** Run `jobs -l` or `ps aux | grep sleep`.
3.  **Bring it to the foreground:** `fg %1` (assuming it is job #1).
4.  **Pause it:** Press `Ctrl + Z`.
5.  **See it in the list:** `jobs` (it should say "Stopped").
6.  **Kill it for good:** `kill %1` or use the PID found in step 2.
7.  **Verify:** `jobs` (it should now be gone).

---

> **Note:** Managing processes on your own machine is one thing, but managing them on a remote server requires networking. In **Chapter 10: Networking & SSH**, we will learn how to connect to other Linux systems securely across the internet.
